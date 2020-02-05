---
title: Processo de implantação do grupo de resposta no Skype for Business
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: d390c8a1-dc6e-44d8-b386-2be1fca9877c
description: Processo de implantação e etapas para o grupo de resposta no Skype for Business Server Enterprise Voice.
ms.openlocfilehash: 810bf635794f58ad8f28295549023a3ef2450f69
ms.sourcegitcommit: dd3a3ab4ddbdcfe772f30fb01ba3b97c45c43dd4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41767524"
---
# <a name="deployment-process-for-response-group-in-skype-for-business"></a>Processo de implantação do grupo de resposta no Skype for Business

Processo de implantação e etapas para o grupo de resposta no Skype for Business Server Enterprise Voice.

O grupo de resposta é um recurso de voz empresarial que roteia e enfileira chamadas de entrada para grupos de pessoas, chamados agentes, como um suporte técnico ou uma mesa de atendimento ao cliente.

Os componentes necessários para o grupo de resposta são instalados e habilitados automaticamente no servidor front-end ou no servidor Standard Edition ao implantar o Enterprise Voice. Para disponibilizar o grupo de resposta para os usuários, você deve configurar grupos de agente e, em seguida, filas e fluxos de trabalho. Além disso, um administrador de grupo de resposta pode delegar a configuração de um fluxo de trabalho existente a um gerente de grupo de resposta, que pode, em seguida, modificar e reconfigurar o fluxo de trabalho e seus grupos e filas de agente associados.

Para configurar grupos de resposta, você deve ser membro de pelo menos uma das funções administrativas a seguir:

|**Grupo de segurança do Diretório Ativo(1)** <br/> |Criar fluxo de trabalho  <br/> |Atribuir gerente  <br/> |Criar/atribuir agentes, filas  <br/> |Criar/gerenciar horas extras e de feriado  <br/> |Ativar/Desativar fluxo de trabalho  <br/> |Configurar fluxo de trabalho (IVR ou Grupo de busca)  <br/> |
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|**CsResponseGroupAdministrator** <br/> |√  <br/> |√  <br/> |√  <br/> |√  <br/> |√  <br/> |√  <br/> |
|**CsResponseGroupManager** <br/> ||√(2)  <br/> |√(3)  <br/> |√(3)  <br/> |√(3)  <br/> |√(3)  <br/> |
|**CsVoiceAdministrator** <br/> |√  <br/> |√  <br/> |√  <br/> |√  <br/> |√  <br/> |√  <br/> |
|**CsServerAdministrator** <br/> |√  <br/> |√  <br/> |√  <br/> |√  <br/> |√  <br/> |√  <br/> |
|**CsAdministrator** <br/> |√  <br/> |√  <br/> |√  <br/> |√  <br/> |√  <br/> |√  <br/> |
|**CsViewOnlyAdministrator** <br/> |√(4)  <br/> |√(4)  <br/> |√(4)  <br/> |√(4)  <br/> |√(4)  <br/> |√(4)  <br/> |

> [!NOTE]
> **(1)** um objeto de usuário dos serviços de domínio Active Directory deve ser um membro do grupo de segurança especificado do Active Directory listado. Um administrador ou outro membro de grupo delegado do Active Directory com permissões adequadas para adicionar usuários a um grupo de segurança (por exemplo, administrador, operadores de conta) devem adicionar um objeto de usuário ao grupo ou grupo de segurança listado para que o usuário possa executar as funções listadas. **(2)** somente para fluxos de trabalho que o CsResponseGroupAdministrator atribuiu ao CsResponseGroupManager. **(3)** um gerente de grupo de resposta pode atribuir outro membro de CsResponseGroupManager a um fluxo de trabalho que o gerente atual já gerencia. **(4)** CsViewOnlyAdministrator pode executar cmdlets "Get" de verbo.

## <a name="response-group-configuration-prerequisites"></a>Requisitos de configuração do grupo de resposta

O grupo de resposta requer os seguintes componentes:

- Serviço de aplicativos

- Aplicativo Grupo de Resposta

- Pacotes de idioma

- Repositório de arquivos (para manter arquivos de áudio)

- Serviços Web (inclui a ferramenta de configuração de grupo de resposta e o console de entrada e saída dos agentes)

Todos esses componentes são instalados por padrão quando você implanta o Enterprise Voice.

Talvez seja necessário executar as seguintes tarefas antes de configurar o grupo de resposta:

- Habilite os usuários do Lync Server 2013 e do Enterprise Voice.

- Modificar um arquivo de configuração para estar em conformidade com os Padrões de Processamento de Informação Federal (FIPS).

- Modificar o agrupamento do banco de dados para suportar caracteres Yi, Meng, e Zang para nomes de fila e nomes de grupo de agentes.

### <a name="enabling-users"></a>Ativando usuários

A primeira etapa na configuração do grupo de resposta é criar grupos de agente. Antes de criar um grupo de agente, você deve habilitar os usuários que serão agentes para o grupo de resposta do Skype for Business e Enterprise Voice. A habilitação de usuários para o Skype for Business geralmente é uma etapa da implantação do servidor Enterprise Edition ou do servidor Standard Edition. Para obter detalhes sobre como habilitar usuários do Skype for Business, consulte [habilitar ou desabilitar usuários do Lync Server 2013 Preview](https://technet.microsoft.com/library/12497d00-f665-4a97-be68-854c5a8be4fc.aspx). A habilitação dos usuários para o Enterprise Voice geralmente é uma etapa na implantação do Enterprise Voice. Para obter detalhes, consulte [habilitar usuários do Enterprise Voice no Skype for Business Server](enable-users-for-enterprise-voice.md).

### <a name="complying-with-fips-requirements"></a>Em conformidade com os requisitos FIPS

Essa seção se aplica a você apenas se sua organização precisar estar em conformidade com os Padrões de Processamento de Informações Federais (FIPS).

Para estar em conformidade com FIPS, você precisa modificar o nível de aplicativo do arquivo Web.config para utilizar um algoritmo de criptografia diferente após instalar os Serviços Web. Você precisa especificar que o ASP.NET utiliza o algoritmo do Padrão de Criptografia de Dados Triplo (3DES) para processar dados de estado de visualização. Para o aplicativo de grupo de resposta, esse requisito se aplica à ferramenta de configuração de grupo de resposta e ao console de entrada e saída do agente. Para obter detalhes sobre esse requisito, consulte o artigo 911722 da base de dados de conhecimento Microsoft, "você pode receber uma mensagem de erro ao acessar páginas da Web do ASP.NET com ViewState habilitado após a atualização do ASP.NET 1,1 [https://go.microsoft.com/fwlink/p/?linkId=196183](https://go.microsoft.com/fwlink/p/?linkId=196183)para o ASP.NET 2,0," at.

Para modificar o arquivo Web.config, faça o seguinte:

1. Em um editor de texto como o Notepad, abra o arquivo Web.config de nível de aplicativo.

2. No arquivo Web. config, localize a `<system.web>` seção.

3. Adicione a seguinte `<machineKey>` seção à `<system.web>` seção:

   ```xml
   <machineKey validationKey="AutoGenerate,IsolateApps" decryptionKey="AutoGenerate,IsolateApps" validation="3DES" decryption="3DES"/>
   ```

4. Salve o arquivo Web.config.

5. Reinicie o serviço de serviços de informações da Internet (IIS) executando o seguinte comando em um prompt de comando:

   ```console
   iisreset
   ```

### <a name="supporting-yi-meng-and-zang-characters"></a>Suporte a caracteres Yi, Meng e Zang

Essa seção se aplica apenas se a sua organização precisar suportar caracteres Yi, Meng ou Zang.

> [!NOTE]
> Para obter informações sobre o que são os caracteres Yi, Meng e Zang e por que eles podem ser importantes para a sua implantação, consulte as informações nos conjuntos [https://go.microsoft.com/fwlink/p/?linkId=240223](https://go.microsoft.com/fwlink/p/?linkId=240223)de caracteres do GB18030.

Para suportar caracteres Yi, Meng ou Zang, você precisa modificar o agrupamento para o banco de dados Rgsconfig. Altere o agrupamento da coluna  **Nome** nas seguintes tabelas em cada banco de dados Rgsconfig:

- dbo.AgentGroups

- dbo.BusinessHours

- dbo.HolidaySets

- dbo.Queues

- dbo.Workflows

Para SQL Server 2008 R2 e SQL Server 2012, use o agrupamento Latin_General_100 (sensível a acentos). Se você utiliza tal agrupamento, todos os nomes de objeto não diferenciam maiúsculas de minúsculas.

Você pode mudar o agrupamento utilizando o Microsoft SQL Server Management Studio. Para obter detalhes sobre como usar essa ferramenta, consulte ["usando o SQL Server Management Studio"](https://go.microsoft.com/fwlink/p/?linkId=196184). Siga essas etapas para alterar o agrupamento:

1. Certifique-se de que o SQL Server Management Studio está configurado para permitir alterações que precisam que as tabelas sejam recriadas. Para obter detalhes, consulte a [caixa de diálogo "salvar (não permitido)"](https://go.microsoft.com/fwlink/p/?linkId=196186). Para obter detalhes sobre como definir um agrupamento de colunas, consulte em ["como: definir o agrupamento de colunas (ferramentas de banco de dados Visual)"](https://go.microsoft.com/fwlink/p/?linkId=196185).

2. Utilizando o Microsoft SQL Server Management Studio, conecte-se ao banco de dados Rgsconfig.

3. Encontre a tabela que deseja alterar no banco de dados Rgsconfig, clique com o botão direito na tabela e em **Design**.

4. Altere o agrupamento da coluna **Nome** e salve a tabela.

## <a name="response-group-deployment-steps"></a>Etapas de Implantação do Grupo de Resposta

**Processo de implantação do grupo de resposta**

|**Fase**|**Etapas**|**Permissões**|**Documentação de Implantação**|
|:-----|:-----|:-----|:-----|
|Permitir que os usuários do Skype for Business e do Enterprise Voice  <br/> |Habilite os usuários que serão agentes do Skype for Business e do Enterprise Voice. Os usuários devem ser habilitados para que você possa adicioná-los a grupos de agente. Normalmente, os usuários estão habilitados para o Skype for Business durante a implantação do servidor Enterprise Edition ou Standard Edition. Os usuários estão habilitados para o Enterprise Voice durante a implantação do Enterprise Voice.  <br/> |RTCUniversalUserAdmins  <br/> CsUserAdministrator  <br/> CsAdministrator  <br/> |[Enable or Disable Users for Lync Server 2013 Preview](https://technet.microsoft.com/library/12497d00-f665-4a97-be68-854c5a8be4fc.aspx) <br/> [Habilitar usuários do Enterprise Voice no Skype for Business Server](enable-users-for-enterprise-voice.md) <br/> |
|Criar e configurar grupos de resposta, que consistem em grupos de agentes, filas e fluxos de trabalho  <br/> |1. Use o painel de controle do Skype for Business Server ou o Shell de gerenciamento do Skype for Business Server para fazer o seguinte:  <br/> a. Criar e configurar grupos de agentes.  <br/> b. Criar e configurar filas.  <br/> 2. opcionalmente, use o Shell de gerenciamento do Skype for Business Server para criar grupos de resposta predefinidos e horários comerciais e feriados.  <br/> 3. Use a ferramenta de configuração de grupo de resposta ou o Shell de gerenciamento do Skype for Business Server para criar fluxos de trabalho (grupos de chamadas ou fluxos de chamadas de chamadas de voz interativas (IVR)), incluindo horas comerciais e feriados do grupo de respostas personalizadas.  <br/> Você pode acessar a ferramenta de configuração de grupo de resposta por meio do painel de controle do Skype for Business Server.  <br/> |RTCUniversalServerAdmins  <br/> CsResponseGroupAdministrator  <br/> CsVoiceAdministrator  <br/> CsServerAdministrator  <br/> CsAdministrator  <br/> CsResponseGroupManager  <br/> |[Create Response Group Agent Groups](https://technet.microsoft.com/library/2a80de17-ead0-46e8-8a27-7a4e233dbde0.aspx) <br/> [Create Response Group Queues](https://technet.microsoft.com/library/49cb86c7-2cfd-4a53-8408-d407475174ed.aspx) <br/> [Adicionais Definir o horário comercial do grupo de resposta no Skype for Business](optional-define-response-group-business-hours.md) <br/> [Adicionais Definir conjuntos de feriados do grupo de resposta no Skype for Business](optional-define-response-group-holiday-sets.md) <br/> [Projetando e criando fluxos de trabalho de grupo de resposta no Skype for Business](designing-and-creating-response-group-workflows.md) <br/> |
|(Opcional) Personalizar configurações no nível de aplicativo  <br/> |Use o Shell de gerenciamento do Skype for Business Server para personalizar a configuração de música em espera padrão, o arquivo de áudio de música em espera padrão, o período de cortesia do agente e a configuração do contexto de chamada.  <br/> |RTCUniversalServerAdmins  <br/> CsResponseGroupAdministrator  <br/> CsVoiceAdministrator  <br/> CsServerAdministrator  <br/> CsAdministrator  <br/> |[Gerenciando configurações de grupo de resposta no nível do aplicativo no Skype for Business](managing-application-level-response-group-settings.md) <br/> |
|(Opcional) Delegar o gerenciamento dos grupos de resposta  <br/> |Atribua aos usuários a função CsResponseGroupManager para delegar a configuração de grupos de resposta. Os gerentes do grupo de resposta podem então configurar os grupos de resposta atribuídos a eles.  <br/> |RTCUniversalServerAdmins  <br/> CsResponseGroupAdministrator  <br/> CsVoiceAdministrator  <br/> CsServerAdministrator  <br/> CsAdministrator  <br/> |[Planning for Role-Based Access Control](https://technet.microsoft.com/library/41204ba3-ce5b-41a8-a6c3-b444468fa328.aspx) <br/> |
|Verificar a implantação do grupo de respostas  <br/> |Teste o atendimento de chamadas para seus fluxos de trabalho de resposta interativa de voz e grupos de busca, a fim de garantir que sua configuração funcione da maneira esperada.  <br/> |-  <br/> |-  <br/> |

## <a name="overview-of-workflow-creation-scenarios"></a>Visão geral dos cenários de criação do fluxo de trabalho

Ao criar um fluxo de trabalho, há duas possibilidades de cenário:

- **O Administrador cria e configura o fluxo de trabalho** — O membro da função CsResponseGroupAdministrator (ou equivalente) cria e ativa o fluxo de trabalho e todos os elementos no fluxo de trabalho, tais como os grupos de agente, filas, férias e horário comercial, música de espera, etc.

- **O Administrador cria o fluxo de trabalho e o Gerente configura as opções** — O membro da função CsResponseGroupAdministrator (ou equivalente) define o o URI do SIP principal, Nome de exibição, atribui um membro ou membros da função CsResponseGroupManager e seleciona uma fila e ativa o fluxo de trabalho. O CsResponseGroupManager pode então fazer logon e editar a configuração do fluxo de trabalho criando grupos de agente e também atribui o grupo à fila, configurando o número de telefone, férias e horário comercial, música de espera, etc.

    > [!NOTE]
    > Quando quiser criar um fluxo de trabalho gerenciado, é necessário criar o fluxo como ativo. Após salvar um fluxo gerenciado e ativo, é possível modificar e desativar o fluxo de trabalho.


