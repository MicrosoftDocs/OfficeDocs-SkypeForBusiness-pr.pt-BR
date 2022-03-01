---
title: Configuração de administradores de Pais Teams para Educação
author: DaniEASmith
ms.author: danismith
manager: serdars
ms.topic: reference
ms.service: msteams
audience: admin
ms.reviewer: ''
description: Microsoft Teams artigo documentando os pré-requisitos e a instalação dos Pais no Teams para Educação.
ms.localizationpriority: Normal
ROBOTS: NOINDEX, NOFOLLOW
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: af6433cb3e5ca0e1849322bdd128915e826e219b
ms.sourcegitcommit: 2044fdcb0c5db10dbc77c5d66e382c1b927ccdc4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/01/2022
ms.locfileid: "63040059"
---
# <a name="set-up-parent-connection-in-microsoft-teams-for-education"></a>Configurar a conexão pai no Microsoft Teams para Educação

A Conexão Pai no Teams para Educação ajuda os educadores a se conectarem e se envolverem com os pais e responsáveis dos alunos em suas equipes de classe usando Teams chat, que será dimensionado na organização do educador. Todos os dados pai e responsável são provisionados usando School Data Sync, permitindo que a equipe de IT desem conjunto suavemente as coisas.

Depois que pais e responsáveis são definidos, eles podem conversar com os educadores de seus alunos usando Teams chat. Para obter orientações sobre como conectar pais e responsáveis aos educadores, consulte [Conexão com educadores em Teams](https://support.microsoft.com/topic/connect-with-educators-in-teams-ec2430c3-952a-4ba4-9891-1d1cab577960).

Os pais também trabalham com Chat Supervisionado. Pais e responsáveis não terão permissões de Teams completas, o que significa que eles não podem iniciar conversas com alunos ou remover usuários de permissões completas (como educadores) de chats. Para obter mais informações sobre o Chat Supervisionado, [consulte Use supervised chats in Microsoft Teams](supervise-chats-edu.md).

## <a name="requirements"></a>Requisitos

### <a name="school-data-sync"></a>School Data Sync

- Você precisa School Data Sync (SDS) para preencher as informações de contato relacionadas ao pai e ao tutor **de** cada aluno.
  - [Implantar SDS](/schooldatasync/parents-and-guardians-in-sds)

- Se você precisar de ajuda para configurar o SDS e preencher contatos relacionados a  pais e responsáveis para os alunos em seu locatário, entre em contato com a equipe de Sucesso do Cliente EDU:
  - Concluindo o processo RFA em [FastTrack](https://www.microsoft.com/fasttrack?rtc=1).
  - Abrindo um tíquete no [Suporte](https://aka.ms/sdssupport).

- Atualmente, o SDS só dá suporte à ingestão de dados baseada em CSV para contatos pai; no entanto, você pode usar a Sincronização de [API do PowerSchool](/schooldatasync/how-to-deploy-school-data-sync-by-using-powerschool-sync) ou a Sincronização da [API do OneRoster](/schooldatasync/how-to-deploy-school-data-sync-by-using-oneroster-sync) para todos os dados de lista de participantes e apenas adicionar contatos pai usando cSV.
  - Crie um segundo perfil de sincronização usando o [formato SDS v1 CSV Sync](/schooldatasync/school-data-sync-format-csv-files-for-sds).
  - Puxe os dois arquivos [Pai preenchidos](/schooldatasync/parent-contact-sync-file-format) com o restante dos arquivos v1 vazios (apenas os headers).
    - User.csv
    - Guardianrelationship.csv
  - Para exibir um conjunto de exemplos dos arquivos CSV v1, consulte Os atributos mínimos [necessários GitHub arquivos](https://github.com/OfficeDev/O365-EDU-Tools/tree/master/CSV%20Samples/SDS%20Format/Min%20Required%20Attributes).
  - Se você quiser automatizar a retirada nos arquivos CSV após a sincronização inicial, leia nosso documento de Automação de Sincronização de Arquivos [CSV](/schooldatasync/csv-file-sync-automation).
  - Para ajudar a configurar a sincronização de dados do SDS, entre em contato com nossa equipe de sucesso do [cliente](https://www.microsoft.com/fasttrack?rtc=1) ou [abra um tíquete de suporte](https://edusupport.microsoft.com/support?product_id=data_sync).

### <a name="teams-admin-center---policies"></a>Teams Admin Center - Políticas

- Os proprietários da equipe de classe devem Teams chat ligado.
- Os proprietários da equipe de classe devem ter acesso **externo Teams contas não gerenciadas por uma organização** ativas.
  - Isso deve ser ligado no nível do locatário e no nível do usuário. A configuração de nível de locatário pode ser encontrada em **Usuários > Acesso** Externo no Teams Admin Center. Essa configuração também pode ser acessada por meio do PowerShell. As políticas de acesso externo no nível do usuário só podem ser acessadas por meio do PowerShell. Consulte os comandos do PowerShell abaixo para obter mais orientações.

> [!NOTE]
>Pais e responsáveis são classificados como usuários externos no recurso Pais, o que significa que eles não têm direitos de locatário completos. Eles só têm acesso ao chat ou chat aos que são adicionados, bem como arquivos, imagens e outros conteúdos compartilhados no chat.
>
>Além disso, os usuários externos podem ver a presença (offline, disponível, ocupado etc.) dos usuários da sua organização, mas isso pode ser desativado usando o PowerShell para proteger a privacidade dos usuários. No PowerShell, use [Set-CsPrivacyConfiguration](/powershell/module/skype/set-csprivacyconfiguration?view=skype-ps) e definir ``EnablePrivacyMode=true``.
>
>Mesmo que pais e responsáveis sejam usuários externos, suas contribuições para chats podem ser descobertas. Saiba como conduzir uma investigação de descoberta Teams eDiscovery lendo Conduzir uma investigação de [Descoberta Microsoft Teams](ediscovery-investigation.md).

## <a name="allow-external-access-with-teams-accounts-not-managed-by-an-organization"></a>Permitir acesso externo com Teams contas não gerenciadas por uma organização

Para permitir que os educadores se comuniquem com pais e responsáveis no Teams, o administrador de IT do locatário de educação precisa atualizar as políticas do locatário para permitir o acesso externo Teams contas fora do locatário. Para obter mais informações sobre como gerenciar o acesso externo, consulte [Manage external access in Microsoft Teams](manage-external-access.md).

Aqui estão as etapas para ativar o acesso externo para pais e responsáveis.

1. Instale a versão Microsoft Teams versão mais recente do módulo do PowerShell.

    ```powershell
    Install-Module -Name PowerShellGet -Force -AllowClobber
    Install-Module -Name MicrosoftTeams -AllowPrerelease -Force –AllowClobber
    ```

2. Usando credenciais com privilégios de administrador, execute os seguintes comandos:

    ```powershell
    $credential = Get-Credential
    Connect-MicrosoftTeams -Credential $credential
    ```

    A configuração de política que liga o acesso externo com Teams contas não gerenciadas por uma organização no nível do usuário (`EnableTeamsConsumerAccess`) é ativa por padrão para todas as políticas de acesso externo no nível do usuário. A configuração de nível de locatário e a configuração de política no nível do usuário precisam ser ativas para que um usuário tenha acesso externo com Teams contas não gerenciadas por uma organização. Se você não quiser que todos os usuários do locatário tenham esse acesso ligado, verifique se a configuração no nível do locatário está desligada, atualize as políticas de acesso externo no nível do usuário atribuídas aos seus usuários e, em seguida, a opção ativar a configuração no nível do locatário.

    Para verificar quais políticas de acesso externo no nível do usuário existem e a quem elas são atribuídas, você pode usar as seguintes etapas:

3. Verifique se existem políticas de acesso externo no nível do usuário.

    ```powershell
    Get-CsExternalAccessPolicy
    ```

4. Para cada política diferente da política "Global", verifique quais usuários têm a política atribuída.

   > [!NOTE]
   > Todos os usuários que não têm uma política específica atribuída retornarão à política "Global". Todos os novos usuários adicionados ao locatário terão a política "Global" atribuída.

    ```powershell
    Get-CsOnlineUser -Filter {ExternalAccessPolicy -eq "<PolicyName>"} | Select-Object DisplayName,ObjectId,UserPrincipalName
    ```

`EnableTeamsConsumerAccess` Como todas as políticas de acesso externo no nível do usuário foram definidas como true por padrão, `EnableTeamsConsumerAccess` se você quiser ajustar a configuração para usuários específicos, você pode criar/modificar políticas de acesso externo existentes com configurações ajustadas e/ou reatribuir usuários a políticas novas ou existentes usando os seguintes cmdlets do PowerShell:

- Criar uma nova política de acesso externo: [New-CsExternalAccessPolicy](/powershell/module/skype/new-csexternalaccesspolicy)

- Personalizar uma política de acesso externo existente (incluindo a política 'Global'): [Set-CsExternalAccessPolicy](/powershell/module/skype/set-csexternalaccesspolicy)

> [!NOTE]
> As seguintes políticas padrão de assinatura não podem ser modificadas: 'FederationAndPICDefault', 'FederationOnly', 'NoFederationAndPIC'. A política 'FederationAndPICDefault' costumava ser atribuída a todos os usuários por padrão, no entanto, os novos usuários agora são atribuídos à política 'Global' por padrão. Se você precisar alterar as configurações de política para usuários que têm essas políticas padrão de assinatura atribuídas, atribua políticas diferentes com as configurações corretas a esses usuários.

- Atribuir uma política de acesso externo a um único usuário: [Grant-CsExternalAccessPolicy](/powershell/module/skype/grant-csexternalaccesspolicy)

- Atribuir uma política a um conjunto de usuários: [New-CsBatchPolicyAssignmentOperation](/powershell/module/teams/new-csbatchpolicyassignmentoperation)

Depois que as políticas de acesso externo no nível do usuário são definidas corretamente para os usuários em seu locatário, você pode ativar a configuração de nível de locatário (`AllowTeamsConsumer`) para o locatário usando o seguinte cmdlet:

- Definir as configurações de federação para seu locatário: [Set-CsTenantFederationConfiguration](/powershell/module/skype/set-cstenantfederationconfiguration)

## <a name="turn-on-the-parents-app-in-the-teams-admin-center"></a>Ativar o aplicativo Pais no Teams de administração

O aplicativo Pais está desligado por padrão, portanto, os proprietários da equipe de classe não o verão em suas equipes de classe até que ele seja permitido por meio do centro de administração Teams de classe. O aplicativo Pais está Teams centro de administração usando [Permitir aplicativos bloqueados por editores](manage-apps.md#apps-blocked-by-publishers).

A qualquer momento, o aplicativo pode ser desligado no nível do locatário usando [Permitir e bloquear aplicativos](manage-apps.md#allow-and-block-apps) no Teams de administração. Se estiver desligado no nível do locatário, ele será bloqueado para todos os usuários, mesmo que as permissões no nível do usuário sejam ativas.

O aplicativo Pais também pode ser desligado no nível do usuário usando Gerenciar políticas de permissão do aplicativo [em](teams-app-permission-policies.md) Microsoft Teams.

## <a name="more-information"></a>Mais informações

- [CsExternalAccessPolicy](/powershell/module/skype/set-csexternalaccesspolicy)
- [CsTenantFederationConfiguration](/powershell/module/skype/set-cstenantfederationconfiguration)
