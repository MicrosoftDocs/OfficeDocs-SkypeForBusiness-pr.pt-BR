---
title: Administração configuração de Pais no Teams para Educação
author: DaniEASmith
ms.author: danismith
manager: serdars
ms.topic: reference
ms.service: msteams
audience: admin
ms.reviewer: ''
description: Artigo do Microsoft Teams documentando os pré-requisitos e a configuração de Pais Teams para Educação.
ms.localizationpriority: Normal
ROBOTS: NOINDEX, NOFOLLOW
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 5edde0613c9092a7ed48d57a4a22761e56eee142
ms.sourcegitcommit: d3eb876e58c9e4a0a11a21b9292d3a6177508d81
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/03/2022
ms.locfileid: "68329055"
---
# <a name="set-up-parent-connection-in-microsoft-teams-for-education"></a>Configurar a Conexão Pai no Microsoft Teams para Educação

A Conexão Pai no Teams para Educação ajuda os educadores a se conectarem com segurança e interagirem com os pais e responsáveis dos alunos em suas equipes de classe usando o Teams.

Este artigo fornece diretrizes para profissionais de TI de educação sobre os requisitos e a configuração da Conexão Pai.

## <a name="share-guardian-and-educator-resources"></a>Compartilhar recursos de tutor e educador

Aqui estão alguns recursos que os administradores de TI podem compartilhar com tutores e educadores sobre como eles podem começar a usar a Conexão Pai.

- Para obter diretrizes sobre como configurar tutores, consulte [Conectar-se com educadores no Teams](https://support.microsoft.com/topic/connect-with-educators-in-teams-ec2430c3-952a-4ba4-9891-1d1cab577960).
- Para obter diretrizes sobre como configurar educadores, consulte [Comunicar-se com responsáveis no Microsoft Teams](https://support.microsoft.com/topic/communicate-with-guardians-in-microsoft-teams-01471ecd-eb5d-4eda-9c5d-0064d672960e?ui=en-us&rs=en-us&ad=us).

## <a name="benefits-of-parent-connection"></a>Benefícios da conexão pai

A Conexão de Pais permite que educadores e responsáveis conversem, enviem emails e liguem usando o Teams.

- Os educadores podem iniciar chats com responsáveis.
  - Se o responsável não tiver uma conta de consumidor do Teams ou ainda não tiver ingressado no Teams, ele receberá a mensagem do educador juntamente com um convite por email para ir para o Teams. Isso só se aplica em casos em que os limites de convite não foram atingidos e o chat é um novo chat ou um chat existente que foi inserido novamente da Conexão Pai.
- Funciona com chat supervisionado. Para obter mais informações, [consulte Usar chats supervisionados no Microsoft Teams](supervise-chats-edu.md).
  - Por padrão, os tutores têm permissões restritas, portanto, eles não podem conversar com os alunos ou remover usuários de chats.
  - Essa configuração pode ser alterada pelo administrador do locatário.
- Os educadores podem clicar no email de um responsável para e-mail usando seu cliente de email nativo.
- Os educadores podem clicar no número de telefone de um responsável para chamá-los no Teams.

> [!IMPORTANT]
> Para clicar para chamar a funcionalidade no Teams, seu locatário precisa:
>
> - Funcionalidades do PBX (Exchange de Branch Público).
> - Conexão com o PSTN.
>
> Microsoft 365 A1 e planos A3 não incluem recursos PBX nem conexão PSTN. Você pode comprar [licenças de complemento para cada uma delas](/microsoftteams/teams-add-on-licensing/microsoft-teams-add-on-licensing).
>
> Microsoft 365 A5 planos incluem apenas recursos PBX usando o Sistema de Telefonia do Teams. Você ainda precisará comprar um Plano de [Chamadas do Teams ou usar](pstn-connectivity.md) uma solução de terceiros para se conectar a números externos no PSTN.
>
> Para obter mais informações sobre todas as opções para obter conectividade PSTN, consulte as [opções de conectividade PSTN](pstn-connectivity.md).
>
> Para obter mais informações sobre o licenciamento de chamadas do Teams, consulte [as opções de licenciamento de complemento do Teams](/microsoftteams/teams-add-on-licensing/microsoft-teams-add-on-licensing).

## <a name="requirements"></a>Requisitos

Você precisa usar o Microsoft Graph ou o SDS (School Data Sync) para preencher as informações de contato relacionadas ao pai e ao responsável de cada aluno.

### <a name="graph-api"></a>API do Graph

Se você já usar o [SDK do PowerShell do Microsoft Graph](/powershell/microsoftgraph/overview) para criar identidades de aluno, poderá incluir facilmente o tipo de recurso [relatedContact](/graph/api/resources/relatedcontact).

### <a name="school-data-sync"></a>School Data Sync

Os dados de contato do guardião do Teams permanecem atualizados com o SIS usando o SDS (School Data Sync), quando o SDS está configurado para sincronizar regularmente.

Se o guardião for removido dos *registros de um* Aluno, quaisquer chats existentes que o envolvam conterão uma faixa visível para o proprietário do chat. Essa faixa fará com que o proprietário do chat fique ciente da alteração, solicitando que ele remova o guardião do chat. A Microsoft não atualizará automaticamente a associação de chat para remover o guardião.

- Você precisa do SDS (School Data Sync) para preencher as informações de contato relacionadas ao pai e **ao responsável de cada** aluno.
  - [Implantar SDS](/schooldatasync/parents-and-guardians-in-sds)

- Se você precisar de ajuda para configurar o SDS e preencher contatos relacionados a  pais e responsáveis para os alunos em seu locatário, entre em contato com a equipe de Sucesso do Cliente EDU:
  - Concluindo o processo de RFA no [FastTrack](https://www.microsoft.com/fasttrack?rtc=1).
  - Abrindo um tíquete no [Suporte](https://aka.ms/sdssupport).

- Atualmente, o SDS dá suporte apenas à ingestão de dados baseada em CSV para Contatos Pai; No entanto, você pode usar a Sincronização de [API do PowerSchool](/schooldatasync/how-to-deploy-school-data-sync-by-using-powerschool-sync) ou a Sincronização de [API do OneRoster](/schooldatasync/how-to-deploy-school-data-sync-by-using-oneroster-sync) para todos os dados da lista de participantes e apenas adicionar contatos pai usando CSV.
  - Crie um segundo perfil de sincronização usando o [formato de Sincronização CSV do SDS v1](/schooldatasync/school-data-sync-format-csv-files-for-sds).
  - Efetue pull dos dois [arquivos pai preenchidos](/schooldatasync/parent-contact-sync-file-format) com o restante dos arquivos v1 vazios (apenas os cabeçalhos).
    - User.csv
    - Guardianrelationship.csv
      - O *valor* da função precisa ser concluído para cada pai e responsável para indicar se eles são *pais ou* *responsáveis*.
  - Para exibir um conjunto de exemplos dos arquivos CSV v1, consulte os arquivos [GitHub de atributos mínimos necessários](https://github.com/OfficeDev/O365-EDU-Tools/tree/master/CSV%20Samples/SDS%20Format/Min%20Required%20Attributes).
  - Se você quiser automatizar a extração dos arquivos CSV após a sincronização inicial, leia nosso [documento CSV Sincronização de Arquivos Automação](/schooldatasync/csv-file-sync-automation).
  - Para obter ajuda com a configuração da sincronização de dados do SDS, entre em contato com nossa [equipe](https://www.microsoft.com/fasttrack?rtc=1) de sucesso do cliente ou [abra um tíquete de suporte](https://edusupport.microsoft.com/support?product_id=data_sync).

### <a name="teams-admin-center-policies"></a>Políticas do centro de administração do Teams

- Os proprietários da equipe de classe devem ter o chat do Teams ativado.
- Os proprietários da equipe de classe devem ter acesso externo com **contas do Teams não gerenciadas por uma organização** ativadas.
  - Isso deve ser ativado no nível do locatário e no nível do usuário. A configuração de nível de locatário pode ser encontrada em **Usuários > Acesso** Externo no centro de administração do Teams. Essa configuração também pode ser acessada por meio do PowerShell. As políticas de acesso externo no nível do usuário só podem ser acessadas por meio do PowerShell. Consulte os comandos do PowerShell abaixo para obter mais diretrizes.

#### <a name="parent-and-guardian-restrictions"></a>Restrições de pais e responsáveis

Pais e responsáveis são classificados como usuários *externos* na Conexão de Pais, o que significa que eles não têm direitos de locatário completos. Eles só têm acesso ao chat ou chat dos quais fazem parte e os arquivos, imagens e outros conteúdos compartilhados no chat.

Para chats externos, os usuários internos e externos podem adicionar usuários ao chat. Para saber mais sobre a experiência de chat externo, consulte [Gerenciar reuniões externas e chat no Microsoft Teams](manage-external-access.md).

Além disso, os usuários externos podem ver a presença (offline, disponível, ocupada etc.) dos usuários da sua organização, mas isso pode ser desativado usando o PowerShell para proteger a privacidade dos usuários. No PowerShell, use [Set-CsPrivacyConfiguration](/powershell/module/skype/set-csprivacyconfiguration) e defina ``EnablePrivacyMode=true``.

Embora pais e responsáveis sejam usuários externos, suas contribuições para chats são detectáveis. Saiba como conduzir uma investigação de Descoberta Eletrônica do Teams lendo Realizar uma investigação de Descoberta Eletrônica [do conteúdo no Microsoft Teams](ediscovery-investigation.md).

> [!IMPORTANT]
> Os administradores de TI devem instruir todos os Proprietários de Classe sobre as práticas recomendadas para compartilhar informações dos alunos por chat, incluindo riscos à privacidade dos alunos.

#### <a name="blocking-a-parent-or-guardian-in-a-chat"></a>Bloqueando um pai ou responsável em um chat

Os educadores podem bloquear um guardião no chat iniciado na Conexão Pai.

O proprietário da classe pode:

1. Abra o cartão de perfil do guardião, selecione a elipse e Bloquear **Usuário**.
2. Em seguida, remova o guardião do chat.

O usuário bloqueado não poderá iniciar chats adicionais com o proprietário da classe.

## <a name="allow-external-access-with-teams-accounts-not-managed-by-an-organization"></a>Permitir acesso externo com contas do Teams não gerenciadas por uma organização

Para permitir que os educadores se comuniquem com pais e responsáveis no Teams, o administrador de TI do locatário de educação precisa atualizar as políticas do locatário para permitir o acesso externo para contas do Teams fora do locatário. Para obter mais informações sobre como gerenciar o acesso externo, veja [Gerenciar acesso externo no Microsoft Teams](manage-external-access.md).

Aqui estão as etapas para ativar o acesso externo para pais e responsáveis.

1. Instale a versão prévia mais recente do módulo do PowerShell do Microsoft Teams.

    ```powershell
    Install-Module -Name PowerShellGet -Force -AllowClobber
    Install-Module -Name MicrosoftTeams -AllowPrerelease -Force –AllowClobber
    ```

2. Usando credenciais que têm privilégios de administrador, execute os seguintes comandos:

    ```powershell
    $credential = Get-Credential
    Connect-MicrosoftTeams -Credential $credential
    ```

    A configuração de política que ativa o acesso externo com contas do Teams não gerenciadas por uma organização no nível do usuário (`EnableTeamsConsumerAccess`) é ativada por padrão para todas as políticas de acesso externo no nível do usuário. A configuração no nível do locatário e a configuração de política no nível do usuário precisam ser ativadas para que um usuário tenha acesso externo com contas do Teams não gerenciadas por uma organização. Se você não quiser que todos os usuários em seu locatário tenham esse acesso ativado, verifique se a configuração no nível do locatário está desativada, atualize as políticas de acesso externo no nível do usuário atribuídas aos usuários e, em seguida, ative a configuração no nível do locatário.

    Para verificar quais políticas de acesso externo no nível do usuário existem e a quem elas estão atribuídas, você pode usar as seguintes etapas:

3. Verifique se existem políticas de acesso externo no nível do usuário.

    ```powershell
    Get-CsExternalAccessPolicy
    ```

4. Para cada política diferente da política "Global", verifique quais usuários têm a política atribuída.

   > [!NOTE]
   > Todos os usuários que não tiverem uma política específica atribuída retornarão à política "Global". Todos os novos usuários adicionados ao locatário terão a política "Global" atribuída.

    ```powershell
    Get-CsOnlineUser -Filter {ExternalAccessPolicy -eq "<PolicyName>"} | Select-Object DisplayName,ObjectId,UserPrincipalName
    ```

`EnableTeamsConsumerAccess` Como todas as políticas de acesso externo no nível do usuário foram definidas como true por padrão, `EnableTeamsConsumerAccess` se você quiser ajustar a configuração para usuários específicos, poderá criar/modificar políticas de acesso externo existentes com configurações ajustadas e/ou reatribuir usuários a políticas novas ou existentes usando os seguintes cmdlets do PowerShell:

- Criar uma nova política de acesso externo: [New-CsExternalAccessPolicy](/powershell/module/skype/new-csexternalaccesspolicy)

- Personalizar uma política de acesso externo existente (incluindo a política 'Global'): [Set-CsExternalAccessPolicy](/powershell/module/skype/set-csexternalaccesspolicy)

> [!NOTE]
> As seguintes políticas padrão de assinatura não podem ser modificadas: 'FederationAndPICDefault', 'FederationOnly', 'NoFederationAndPIC'. A política 'FederationAndPICDefault' costumava ser atribuída a todos os usuários por padrão, no entanto, novos usuários agora recebem a política 'Global' por padrão. Se você precisar alterar as configurações de política para usuários que têm essas políticas padrão de assinatura atribuídas, atribua políticas diferentes com as configurações corretas a esses usuários.

- Atribuir uma política de acesso externo a um único usuário: [Grant-CsExternalAccessPolicy](/powershell/module/skype/grant-csexternalaccesspolicy)

- Atribuir uma política a um conjunto de usuários: [New-CsBatchPolicyAssignmentOperation](/powershell/module/teams/new-csbatchpolicyassignmentoperation)

Depois que as políticas de acesso externo no nível do usuário forem definidas corretamente para os usuários em seu locatário, você poderá ativar a configuração no nível do locatário (`AllowTeamsConsumer`) para o locatário usando o seguinte cmdlet:

- Defina as definições de configuração de federação para seu locatário: [Set-CsTenantFederationConfiguration](/powershell/module/skype/set-cstenantfederationconfiguration)

## <a name="turn-on-the-parents-app-in-the-teams-admin-center"></a>Ativar o aplicativo Pais no Centro de administração do Teams

O aplicativo Pais é desativado por padrão, portanto, os proprietários da equipe de classe não o verão em suas equipes de classe até que ele seja permitido por meio do centro de administração do Teams. O aplicativo Pais é ativado no centro de administração do Teams usando Permitir [aplicativos bloqueados por desenvolvedores](manage-apps.md#allow-the-apps-that-are-blocked-by-the-developers).

A qualquer momento, o aplicativo pode ser desativado no nível do locatário usando Permitir e bloquear aplicativos [no centro](manage-apps.md#allow-and-block-apps) de administração do Teams. Se ele estiver desativado no nível do locatário, ele será bloqueado para todos os usuários, mesmo que as permissões no nível do usuário estejam ativadas.

O aplicativo Pais também pode ser desativado no nível do usuário usando [Gerenciar políticas de permissão de aplicativo no Microsoft Teams](teams-app-permission-policies.md).

## <a name="more-information"></a>Mais informações

- [CsExternalAccessPolicy](/powershell/module/skype/set-csexternalaccesspolicy)
- [CsTenantFederationConfiguration](/powershell/module/skype/set-cstenantfederationconfiguration)
