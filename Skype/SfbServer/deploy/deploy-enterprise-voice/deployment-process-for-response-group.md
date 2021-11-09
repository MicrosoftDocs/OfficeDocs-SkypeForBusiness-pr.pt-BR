---
title: Processo de implantação do Grupo de Resposta Skype for Business
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: d390c8a1-dc6e-44d8-b386-2be1fca9877c
description: Processo de implantação e etapas para o Grupo de Resposta Skype for Business Server Enterprise Voice.
ms.openlocfilehash: 13a83c5fbedc2a7b38118b0e7935c4722e3855ca
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/08/2021
ms.locfileid: "60853695"
---
# <a name="deployment-process-for-response-group-in-skype-for-business"></a>Processo de implantação do Grupo de Resposta Skype for Business

Processo de implantação e etapas para o Grupo de Resposta Skype for Business Server Enterprise Voice.

O Grupo de Resposta é um recurso Enterprise Voice que encaminha e enfileria chamadas de entrada para grupos de pessoas, chamados de agentes, como um suporte de ajuda ou um atendimento ao cliente.

Os componentes necessários para o Grupo de Resposta são instalados e habilitados automaticamente no servidor Front-End ou servidor Standard Edition quando você implanta o Enterprise Voice. Para disponibilizar o Grupo de Resposta aos usuários, configure os grupos de operadores, as filas e as cargas de trabalho. Além disso, um Administrador de Grupo de Resposta pode delegar a configuração de um fluxo de trabalho existente a um Gerente de Grupo de Resposta, que pode modificar e reconfigurar o fluxo de trabalho e seus grupos e filas de agentes associados.

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
> **(1) Um** objeto de usuário dos Serviços de Domínio do Active Directory deve ser membro do grupo de segurança especificado do Active Directory listado. Um administrador ou outro membro do grupo do Active Directory delegado com permissões apropriadas para adicionar usuários a um grupo de segurança (Por exemplo, Administrador, Operadores de Conta) deve adicionar um objeto de usuário ao grupo ou grupo de segurança listado para que o usuário possa executar as funções listadas. **(2)** Somente para fluxos de trabalho que o CsResponseGroupAdministrator atribuiu ao CsResponseGroupManager. **(3)** Um Gerente de Grupo de Resposta pode atribuir outro membro do CsResponseGroupManager a um fluxo de trabalho que o gerente atual já gerencia. **(4)** CsViewOnlyAdministrator só pode executar cmdlets do verbo "Get".

## <a name="response-group-configuration-prerequisites"></a>Pré-requisitos da configuração do Grupo de Resposta

O Grupo de Resposta requer os seguintes componentes:

- Serviço de aplicativos

- Aplicativo Grupo de Resposta

- Pacotes de idiomas

- Repositório de arquivos (para armazenar arquivos de áudio)

- Serviços Web (inclui a Ferramenta de Configuração do Grupo de Resposta e o console de entrada e saída dos agentes)

Todos estes componentes são instalados por padrão ao implantar o Enterprise Voice.

Talvez seja necessário executar as seguintes tarefas antes de configurar o Grupo de Resposta:

- Habilitar usuários para Lync Server 2013 e Enterprise Voice.

- Modificar um arquivo de configuração para ser compatível com o FIPS (Federal Information Processing Standards).

- Modificar o agrupamento de banco de dados para oferecer suporte a caracteres Yi, Meng e Zang para nomes de fila e nomes de grupo de agente.

### <a name="enabling-users"></a>Permitir usuários

A primeira etapa na configuração do Grupo de Resposta é criar grupos de agentes. Antes de criar um grupo de agentes, você deve habilitar os usuários que serão agentes do Grupo de Resposta para Skype for Business e Enterprise Voice. A habilitação de usuários para Skype for Business geralmente é uma etapa na implantação do servidor Edição Enterprise ou Edição Standard servidor. Para obter detalhes sobre como habilitar usuários para Skype for Business, consulte [Enable or Disable Users for Lync Server 2013 Preview](/previous-versions/office/lync-server-2013/lync-server-2013-disable-or-re-enable-user-account-for-lync-server). Habilitar usuários para Enterprise Voice geralmente é uma etapa na implantação de Enterprise Voice. Para obter detalhes, [consulte Enable users for Enterprise Voice in Skype for Business Server](enable-users-for-enterprise-voice.md).

### <a name="complying-with-fips-requirements"></a>Conformidade com os requisitos FIPS

Esta seção somente se aplica a você sea  sua organização precisa cumprir com o FIPS (Federal Information Processing Standards).

Para ser compatível com o FIPS, você precisará modificar o arquivo Web.config de nível de aplicativo para usar um algoritmo de criptografia diferente depois de instalar os serviços da Web. Você precisa especificar que o ASP.NET usa o algoritmo Triple Data Encryption Standard (3DES) para processar os dados de estado de exibição. Para o aplicativo grupo de resposta, esse requisito se aplica à Ferramenta de Configuração do Grupo de Resposta e ao console de entrada e saída do agente.

Para modificar o arquivo Web.config, faça o seguinte:

1. Em um editor de texto como o Notepad, abra o arquivo Web.config de nível de aplicativo.

2. No arquivo Web.config, localize a  `<system.web>` seção.

3. Adicione a seção  `<machineKey>` a seguir à `<system.web>` seção:

   ```xml
   <machineKey validationKey="AutoGenerate,IsolateApps" decryptionKey="AutoGenerate,IsolateApps" validation="3DES" decryption="3DES"/>
   ```

4. Salve o arquivo Web.config.

5. Reinicie o Serviços de Informações da Internet (IIS) executando o seguinte comando em um prompt de comando:

   ```console
   iisreset
   ```

### <a name="supporting-yi-meng-and-zang-characters"></a>Suporte aos caracteres Yi, Meng e Zang

Esta seção se aplica a você somente se a sua organização precisa oferecer suporte a caracteres Yi, Meng ou Zang.

> [!NOTE]
> Para obter informações sobre o que são os caracteres Yi, Meng e Zang e por que eles podem ser importantes para sua implantação, consulte as informações sobre os conjuntos de caracteres GB18030 [https://go.microsoft.com/fwlink/p/?linkId=240223](/previous-versions/sql/sql-server-2008-r2/ms180991(v=sql.105)) .

Para oferecer suporte a caracteres Yi, Meng ou Zang, você precisará modificar o agrupamento para o banco de dados Rgsconfig. Altere o agrupamento da coluna **Nome** nas seguintes tabelas em cada banco de dados Rgsconfig:

- dbo. AgentGroups

- dbo. BusinessHours

- dbo. HolidaySets

- dbo. Filas

- dbo. Fluxos de trabalho

Para SQL Server 2008 R2 e SQL Server 2012, use o colamento Latin_General_100 (Accent Sensitive). Se você usar esse agrupamento, todos os nomes de objeto não se diferenciarão entre maiúsculas e minúsculas.

Você pode alterar o agrupamento usando o Microsoft SQL Server Management Studio. Para obter detalhes sobre como usar essa ferramenta, consulte ["Usando SQL Server Management Studio"](/sql/ssms/sql-server-management-studio-ssms). Siga essas etapas para alterar o agrupamento:

1. Certifique-se de que o SQL Server Management Studio está configurado para permitir alterações que precisam que as tabelas sejam recriadas. Para obter detalhes, consulte a caixa de diálogo ["Salvar (Não Permitido) "](/sql/ssms/visual-db-tools/save-not-permitted-dialog-box). Para obter detalhes sobre a configuração de um colamento de coluna, consulte ["How to: Set Column Collation (Visual Database Tools)"](/previous-versions/sql/sql-server-2008-r2/ms187473(v=sql.105)).

2. Usando o Microsoft SQL Server Management Studio, conecte-se com o banco de dados Rgsconfig.

3. Encontre a tabela que você deseja alterar no banco de dados Rgsconfig, clique com o botão direito na tabela e clique em **Design**.

4. Altere o agrupamento da coluna **Nome** e salve a tabela.

## <a name="response-group-deployment-steps"></a>Etapas de implantação do Grupo de Resposta

**Processo de implantação do grupo de resposta**

|**Fase**|**Etapas**|**Permissões**|**Documentação de Implantação**|
|:-----|:-----|:-----|:-----|
|Habilitar usuários para Skype for Business e para Enterprise Voice  <br/> |Habilitar usuários que serão agentes para Skype for Business e Enterprise Voice. Os usuários devem ser habilitados antes de adicioná-los a grupos de agente. Normalmente, os usuários são habilitados para Skype for Business durante a implantação Edição Enterprise ou Edição Standard servidor. Os usuários estão habilitados para Enterprise Voice durante Enterprise Voice implantação.  <br/> |RTCUniversalUserAdmins  <br/> CsUserAdministrator  <br/> CsAdministrator  <br/> |[Habilitar ou desabilitar usuários para Visualização do Lync Server 2013](/previous-versions/office/lync-server-2013/lync-server-2013-disable-or-re-enable-user-account-for-lync-server) <br/> [Habilitar usuários para Enterprise Voice em Skype for Business Server](enable-users-for-enterprise-voice.md) <br/> |
|Criar e configura grupos de resposta, que consistem de grupos de agentes, filas e fluxos de trabalho  <br/> |1. Use o painel de Skype for Business Server ou o Shell de Gerenciamento Skype for Business Server para fazer o seguinte:  <br/> a. Criar e configurar grupos de agentes.  <br/> b. Criar e configurar filas.  <br/> 2. Opcionalmente, use Skype for Business Server Shell de Gerenciamento para criar horários comerciais e feriados predefinidos do grupo de resposta.  <br/> 3. Use a Ferramenta de Configuração do Grupo de Resposta ou o Shell de Gerenciamento Skype for Business Server para criar fluxos de trabalho (grupos de busca ou fluxos de chamadas de ivr (resposta de voz interativa), incluindo horários comerciais e feriados personalizados do grupo de resposta.  <br/> Você pode acessar a Ferramenta de Configuração do Grupo de Resposta Skype for Business Server Painel de Controle.  <br/> |RTCUniversalServerAdmins  <br/> CsResponseGroupAdministrator  <br/> CsVoiceAdministrator  <br/> CsServerAdministrator  <br/> CsAdministrator  <br/> CsResponseGroupManager  <br/> |[Criar grupos de agentes dos grupos de resposta](/previous-versions/office/lync-server-2013/lync-server-2013-create-response-group-agent-groups) <br/> [Criar filas de grupos de resposta](/previous-versions/office/lync-server-2013/lync-server-2013-create-response-group-queues) <br/> [(Opcional) Definir o horário comercial do Grupo de Resposta em Skype for Business](optional-define-response-group-business-hours.md) <br/> [(Opcional) Definir conjuntos de feriados do Grupo de Resposta Skype for Business](optional-define-response-group-holiday-sets.md) <br/> [Criando e criando fluxos de trabalho de grupo de resposta Skype for Business](designing-and-creating-response-group-workflows.md) <br/> |
|(Opcional) Personalizar configurações a nível de aplicativo  <br/> |Use Skype for Business Server Shell de Gerenciamento para personalizar a configuração padrão de música em espera, o arquivo de áudio padrão de música em espera, o período de carência de toque do agente e a configuração de contexto de chamada.  <br/> |RTCUniversalServerAdmins  <br/> CsResponseGroupAdministrator  <br/> CsVoiceAdministrator  <br/> CsServerAdministrator  <br/> CsAdministrator  <br/> |[Gerenciando configurações do Grupo de Resposta no nível do aplicativo Skype for Business](managing-application-level-response-group-settings.md) <br/> |
|(Opcional) Delega o gerenciamento dos grupos de resposta  <br/> |Atribua aos usuários a função CsResponseGroupManager para delegar a configuração dos grupos de resposta. Em seguida, os Gerentes de Grupo de Resposta podem configurar os grupos de resposta atribuídos a eles.  <br/> |RTCUniversalServerAdmins  <br/> CsResponseGroupAdministrator  <br/> CsVoiceAdministrator  <br/> CsServerAdministrator  <br/> CsAdministrator  <br/> |[Planejando o controle de acesso baseado em função](/previous-versions/office/lync-server-2013/lync-server-2013-planning-for-role-based-access-control) <br/> |
|Verificar a implantação do grupo de respostas  <br/> |Teste responder chamadas para seu fluxo de trabalho de resposta de voz interativa e grupo coletivo para garantir que sua configuração funcione como esperado.  <br/> |-  <br/> |-  <br/> |

## <a name="overview-of-workflow-creation-scenarios"></a>Visão geral dos cenários de criação de fluxo de trabalho

Ao criar um fluxo de trabalho, há duas possibilidades de cenário:

- **O Administrasdor cria e configura o fluxo de trabalho** — O membro de função CsResponseGroupAdministrator (ou equivalente) cria e ativa o fluxo de trabalho e todos os elementos no fluxo de trabalho, tais como os grupos de agente, filas, férias e horário comercial, música de espera, etc.

- **O Administrador cria o fluxo de trabalho e oGerente configura as opções** — O membro de função CsResponseGroupAdministrator (ou equivalente) define o SIP URI primário, Nome de exibição, designa um mebro ou membros da função CsResponseGroupManager e seleciona uma fila e ativa o fluxo de trabalho. O CsResponseGroupManager pode então fazer o log e editar a configuração do fluxo de trabalho criando grupos de agente e também designando o grupo à fila, configurando o número de telefone, férias e horário comercial, música de espera, etc.

    > [!NOTE]
    > Quando quiser criar um fluxo de trabalho gerenciado, é necessário criar o fluxo como ativo. Após salvar um fluxo gerenciado e ativo, é possível modificar e desativar o fluxo de trabalho.