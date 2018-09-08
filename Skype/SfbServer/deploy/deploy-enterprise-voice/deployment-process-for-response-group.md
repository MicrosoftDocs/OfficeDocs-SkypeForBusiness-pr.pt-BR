---
title: Processo de implantação do grupo de resposta no Skype para negócios
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: d390c8a1-dc6e-44d8-b386-2be1fca9877c
description: Processo de implantação e etapas para o grupo de resposta no Skype para Business Server Enterprise Voice.
ms.openlocfilehash: 290db10e0a306217462015c43d9abb68e18ccb8a
ms.sourcegitcommit: 940cb253923e3537cb7fb4d7ce875ed9bfbb72db
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/07/2018
ms.locfileid: "23884179"
---
# <a name="deployment-process-for-response-group-in-skype-for-business"></a>Processo de implantação do grupo de resposta no Skype para negócios

Processo de implantação e etapas para o grupo de resposta no Skype para Business Server Enterprise Voice.

Grupo de resposta é um recurso de Enterprise Voice que roteia e enfileira chamadas recebidas para grupos de pessoas, chamados agentes, como um help desk ou um service desk do cliente.

Os componentes que o grupo de resposta requer estão instalados e ativados automaticamente no servidor do servidor Front-End ou Standard Edition, quando você implanta o Enterprise Voice. Para tornar o grupo de resposta disponível aos usuários, você deve configurar fluxos de trabalho e em seguida, filas e grupos de operadores. Além disso, um administrador de grupo de resposta pode delegar a configuração de um fluxo de trabalho existente ao gerente do grupo uma resposta, que pode, em seguida, modificar e reconfigurar o fluxo de trabalho e seus grupos de operadores associado e filas.

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
> **(1)** o objeto de usuário de um Active Directory Domain Services deve ser um membro do grupo de segurança de Active Directory especificado listado. Um administrador ou outro membro do grupo do Active Directory delegado com as permissões apropriadas para adicionar usuários a um grupo de segurança (por exemplo, administrador, operadores de conta) deve adicionar um objeto de usuário ao grupo de segurança listados ou grupo para o usuário possam Execute as funções listadas. **(2)** só para fluxos de trabalho que o CsResponseGroupAdministrator tiver atribuído a CsResponseGroupManager. **(3)** o gerente do grupo de resposta de uma pode atribuir outro membro do CsResponseGroupManager a um fluxo de trabalho que já gerencia o gerente atual. **(4)** CsViewOnlyAdministrator só poderá executar verbo "Get" cmdlets.

## <a name="response-group-configuration-prerequisites"></a>Pré-requisitos de configuração de grupo de resposta

Grupo de resposta requer os seguintes componentes:

- Serviço de aplicativos

- Aplicativo Grupo de Resposta

- Pacotes de idioma

- Repositório de arquivos (para manter arquivos de áudio)

- Serviços da Web (inclui a ferramenta de configuração de grupo de resposta e o console de entrada e saída dos agentes)

Todos estes componentes são instalados por padrão, quando você implanta o Enterprise Voice.

Você pode precisar executar as seguintes tarefas antes de configurar o grupo de resposta:

- Habilite usuários para o Lync Server 2013 e Enterprise Voice.

- Modificar um arquivo de configuração para estar em conformidade com os Padrões de Processamento de Informação Federal (FIPS).

- Modificar o agrupamento do banco de dados para suportar caracteres Yi, Meng, e Zang para nomes de fila e nomes de grupo de agentes.

### <a name="enabling-users"></a>Ativando usuários

A primeira etapa na configuração de grupo de resposta é crie grupos de operadores. Antes de criar um grupo de operadores, você deverá habilitar os usuários que serão agentes para o grupo de resposta para Skype para Enterprise Voice e de negócios. Habilitando usuários para o Skype para negócios normalmente é uma etapa na implantação do servidor Standard Edition ou servidor Enterprise Edition. Para obter detalhes sobre como habilitar usuários para Skype for Business, consulte [Enable or Disable Users for Lync Server 2013 Preview](https://technet.microsoft.com/library/12497d00-f665-4a97-be68-854c5a8be4fc.aspx). Habilitando usuários para o Enterprise Voice é geralmente uma etapa na implantação do Enterprise Voice. Para obter detalhes, consulte [habilitar usuários para Enterprise Voice no Skype para Business Server](enable-users-for-enterprise-voice.md).

### <a name="complying-with-fips-requirements"></a>Em conformidade com os requisitos FIPS

Essa seção se aplica a você apenas se sua organização precisar estar em conformidade com os Padrões de Processamento de Informações Federais (FIPS).

Para estar em conformidade com FIPS, você precisa modificar o nível de aplicativo do arquivo Web.config para utilizar um algoritmo de criptografia diferente após instalar os Serviços Web. Você precisa especificar que o ASP.NET utiliza o algoritmo do Padrão de Criptografia de Dados Triplo (3DES) para processar dados de estado de visualização. Para o aplicativo grupo de resposta, esse requisito se aplica a ferramenta de configuração de grupo de resposta e o console de entrada e saída de agente. Para obter detalhes sobre esse requisito, consulte o artigo da Base de Conhecimento Microsoft 911722, "você pode receber uma mensagem de erro ao acessar páginas da Web ASP.NET que possuem ViewState habilitado após a atualização do ASP.NET 1.1 para o ASP.NET 2.0," em [https://go.microsoft.com/fwlink/p/?linkId=196183](https://go.microsoft.com/fwlink/p/?linkId=196183).

Para modificar o arquivo Web.config, faça o seguinte:

1. Em um editor de texto como o Notepad, abra o arquivo Web.config de nível de aplicativo.

2. No arquivo Web. config, localize o `<system.web>` seção.

3. Adicione a seguinte `<machineKey>` seção no `<system.web>` seção:

   ```
   <machineKey validationKey="AutoGenerate,IsolateApps" decryptionKey="AutoGenerate,IsolateApps" validation="3DES" decryption="3DES"/>
   ```

4. Salve o arquivo Web.config.

5. Reinicie o serviço de serviços de informações da Internet (IIS), executando o seguinte comando no prompt de comando:

   ```
   iisreset
   ```

### <a name="supporting-yi-meng-and-zang-characters"></a>Suporte a caracteres Yi, Meng e Zang

Essa seção se aplica apenas se a sua organização precisar suportar caracteres Yi, Meng ou Zang.

> [!NOTE]
> Para obter informações sobre quais são os caracteres Yi, Meng e Zang e por que eles podem ser importantes para sua implantação, consulte as informações sobre os conjuntos de caracteres GB18030 [https://go.microsoft.com/fwlink/p/?linkId=240223](https://go.microsoft.com/fwlink/p/?linkId=240223).

Para suportar caracteres Yi, Meng ou Zang, você precisa modificar o agrupamento para o banco de dados Rgsconfig. Altere o agrupamento da coluna  **Nome** nas seguintes tabelas em cada banco de dados Rgsconfig:

- dbo. AgentGroups

- dbo. BusinessHours

- dbo. HolidaySets

- dbo. Filas

- dbo. Fluxos de trabalho

Para o SQL Server 2008 R2 e o SQL Server 2012, o agrupamento do uso do Latin_General_100 (ênfase confidenciais). Se você utiliza tal agrupamento, todos os nomes de objeto não diferenciam maiúsculas de minúsculas.

Você pode mudar o agrupamento utilizando o Microsoft SQL Server Management Studio. Para obter detalhes sobre como usar essa ferramenta, consulte ["usando o SQL Server Management Studio"](https://go.microsoft.com/fwlink/p/?linkId=196184). Siga essas etapas para alterar o agrupamento:

1. Certifique-se de que o SQL Server Management Studio está configurado para permitir alterações que precisam que as tabelas sejam recriadas. Para obter detalhes, consulte ["Salvar (não permitido) caixa de diálogo"](https://go.microsoft.com/fwlink/p/?linkId=196186). Para obter detalhes sobre como definir um agrupamento da coluna, consulte em ["como: definir o agrupamento de coluna (ferramentas de banco de dados Visual)"](https://go.microsoft.com/fwlink/p/?linkId=196185).

2. Utilizando o Microsoft SQL Server Management Studio, conecte-se ao banco de dados Rgsconfig.

3. Encontre a tabela que deseja alterar no banco de dados Rgsconfig, clique com o botão direito na tabela e em **Design**.

4. Altere o agrupamento da coluna **Nome** e salve a tabela.

## <a name="response-group-deployment-steps"></a>Etapas de Implantação do Grupo de Resposta

**Processo de implantação do grupo de resposta**

|**Fase**|**Etapas**|**Permissões**|**Documentação de implantação**|
|:-----|:-----|:-----|:-----|
|Habilitar usuários para o Skype para negócios e para o Enterprise Voice  <br/> |Permitir que os usuários que serão agentes para Skype para Enterprise Voice e de negócios. Os usuários devem estar habilitados antes de você poderá adicioná-los a grupos de operadores. Normalmente, os usuários estão habilitados para Skype para negócios durante a implantação de servidor do Standard Edition ou Enterprise Edition. Os usuários estão habilitados para o Enterprise Voice durante a implantação do Enterprise Voice.  <br/> |RTCUniversalUserAdmins  <br/> CsUserAdministrator  <br/> CsAdministrator  <br/> |[Habilitar ou desabilitar usuários para o Lync Server 2013 Preview](https://technet.microsoft.com/library/12497d00-f665-4a97-be68-854c5a8be4fc.aspx) <br/> [Habilitar usuários para o Enterprise Voice no Skype para Business Server](enable-users-for-enterprise-voice.md) <br/> |
|Criar e configurar grupos de resposta, que consistem em grupos de agentes, filas e fluxos de trabalho  <br/> |1. use o Skype para painel de controle do Business Server ou Skype do Shell de gerenciamento do servidor de negócios para fazer o seguinte:  <br/> a. Criar e configurar grupos de agentes.  <br/> b. Criar e configurar filas.  <br/> 2. opcionalmente, use Skype para Business Server Management Shell para criar e feriados do horário comercial do grupo de resposta predefinido.  <br/> 3. use a ferramenta de configuração de grupo de resposta ou Skype para Business Server Management Shell para criar fluxos de trabalho (grupos de busca ou fluxos de chamada IVR (resposta) de voz interativa), incluindo e feriados do horário comercial do grupo de resposta personalizado.  <br/> Você pode acessar a ferramenta de configuração de grupo de resposta por meio do Skype para painel de controle do servidor de negócios.  <br/> |RTCUniversalServerAdmins  <br/> CsResponseGroupAdministrator  <br/> CsVoiceAdministrator  <br/> CsServerAdministrator  <br/> CsAdministrator  <br/> CsResponseGroupManager  <br/> |[Criar grupos de operadores do grupo de resposta](https://technet.microsoft.com/library/2a80de17-ead0-46e8-8a27-7a4e233dbde0.aspx) <br/> [Criar filas de espera do grupo de resposta](https://technet.microsoft.com/library/49cb86c7-2cfd-4a53-8408-d407475174ed.aspx) <br/> [(Opcional) Grupo de resposta definir expediente no Skype para negócios](optional-define-response-group-business-hours.md) <br/> [(Opcional) Conjuntos de feriados do grupo de resposta definir Skype para negócios](optional-define-response-group-holiday-sets.md) <br/> [Projetando e criando fluxos de trabalho do grupo de resposta no Skype para negócios](designing-and-creating-response-group-workflows.md) <br/> |
|(Opcional) Personalizar configurações no nível de aplicativo  <br/> |Use Skype do Shell de gerenciamento do servidor de negócios para personalizar a configuração de música de espera padrão, o arquivo de áudio de música de espera padrão, o período de cortesia de chamada de retorno do agente e a configuração do contexto da chamada.  <br/> |RTCUniversalServerAdmins  <br/> CsResponseGroupAdministrator  <br/> CsVoiceAdministrator  <br/> CsServerAdministrator  <br/> CsAdministrator  <br/> |[Gerenciando configurações de grupo de resposta de nível de aplicativo no Skype para negócios](managing-application-level-response-group-settings.md) <br/> |
|(Opcional) Delegar o gerenciamento dos grupos de resposta  <br/> |Atribua usuários à função CsResponseGroupManager para delegar a configuração dos grupos de resposta. Gerentes de grupo de resposta, em seguida, podem configurar os grupos de resposta atribuídos a eles.  <br/> |RTCUniversalServerAdmins  <br/> CsResponseGroupAdministrator  <br/> CsVoiceAdministrator  <br/> CsServerAdministrator  <br/> CsAdministrator  <br/> |[Planejamento de controle de acesso baseado em função](https://technet.microsoft.com/library/41204ba3-ce5b-41a8-a6c3-b444468fa328.aspx) <br/> |
|Verificar a implantação do grupo de respostas  <br/> |Teste o atendimento de chamadas para seus fluxos de trabalho de resposta interativa de voz e grupos de busca, a fim de garantir que sua configuração funcione da maneira esperada.  <br/> |-  <br/> |-  <br/> |

## <a name="overview-of-workflow-creation-scenarios"></a>Visão geral dos cenários de criação do fluxo de trabalho

Ao criar um fluxo de trabalho, há duas possibilidades de cenário:

- **O Administrador cria e configura o fluxo de trabalho** — O membro da função CsResponseGroupAdministrator (ou equivalente) cria e ativa o fluxo de trabalho e todos os elementos no fluxo de trabalho, tais como os grupos de agente, filas, férias e horário comercial, música de espera, etc.

- **O Administrador cria o fluxo de trabalho e o Gerente configura as opções** — O membro da função CsResponseGroupAdministrator (ou equivalente) define o o URI do SIP principal, Nome de exibição, atribui um membro ou membros da função CsResponseGroupManager e seleciona uma fila e ativa o fluxo de trabalho. O CsResponseGroupManager pode então fazer logon e editar a configuração do fluxo de trabalho criando grupos de agente e também atribui o grupo à fila, configurando o número de telefone, férias e horário comercial, música de espera, etc.

    > [!NOTE]
    > Quando quiser criar um fluxo de trabalho gerenciado, é necessário criar o fluxo como ativo. Após salvar um fluxo gerenciado e ativo, é possível modificar e desativar o fluxo de trabalho.


