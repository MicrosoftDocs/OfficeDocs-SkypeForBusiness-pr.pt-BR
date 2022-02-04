---
title: Configuração de administrador para o aplicativo Pais do Microsoft EDU Teams
author: DaniEASmith
ms.author: danismith
manager: serdars
ms.topic: reference
ms.service: msteams
audience: admin
ms.reviewer: ''
description: Microsoft Teams artigo do EDU documentando pré-requisitos e configuração para o aplicativo Pais.
ms.localizationpriority: Normal
ROBOTS: NOINDEX, NOFOLLOW
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: f35d4f3037735f2122d26a2b9b24cf3a38f3bc99
ms.sourcegitcommit: 1129841e68e927fe7cc31de3ad63a3e9247253cd
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/03/2022
ms.locfileid: "62363227"
---
# <a name="deploying-the-parents-app-in-microsoft-teams"></a>Implantando o aplicativo Pais em Microsoft Teams

O aplicativo Pais ajuda os educadores a se conectarem e se envolverem com os pais e responsáveis pelos alunos em suas equipes de classe usando Teams chat, que será dimensionado na organização do educador. Todos os dados pai e responsável são provisionados usando School Data Sync, permitindo que a equipe de IT desem conjunto suavemente as coisas.

## <a name="requirements"></a>Requisitos

### <a name="school-data-sync"></a>School Data Sync

- Você precisa School Data Sync (SDS) para preencher as informações de contato relacionadas ao pai e ao tutor **de** cada aluno.
  - [Implantar SDS](/schooldatasync/parents-and-guardians-in-sds)

- Se você precisar de ajuda para configurar o SDS e preencher contatos relacionados a  pais e responsáveis para os alunos em seu locatário, entre em contato com a equipe de Sucesso do Cliente EDU:
  - Concluindo o processo RFA em [FastTrack](https://www.microsoft.com/fasttrack?rtc=1).
  - Abrindo um tíquete no [Suporte](https://aka.ms/sdssupport).

### <a name="teams-admin-center---policies"></a>Teams Admin Center - Políticas

- Os proprietários da equipe de classe devem Teams chat habilitado.
- Os proprietários da equipe de classe devem ter acesso **externo Teams contas não gerenciadas por uma organização** habilitada.
  - Isso deve ser habilitado no nível do locatário e no nível do usuário. A configuração de nível de locatário pode ser encontrada em **Usuários > Acesso** Externo no Teams Admin Center. Essa configuração também pode ser acessada por meio do PowerShell. As políticas de acesso externo no nível do usuário só podem ser acessadas por meio do PowerShell. Consulte os comandos do PowerShell abaixo para obter mais orientações.

## <a name="enabling-external-access-with-teams-accounts-not-managed-by-an-organization"></a>Habilitando o acesso externo com Teams contas não gerenciadas por uma organização

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

A configuração de política que permite o acesso externo Teams contas não gerenciadas por uma organização no nível do usuário (`EnableTeamsConsumerAccess`) está habilitada por padrão para todas as políticas de acesso externo no nível do usuário. A configuração de nível de locatário e a configuração de política no nível do usuário precisam estar habilitadas para que um usuário tenha acesso externo com contas Teams não gerenciadas por uma organização habilitada. Se você não quiser que todos os usuários em seu locatário tenham esse acesso habilitado, certifique-se de que sua configuração no nível de locatário está desabilitada, atualize as políticas de acesso externo no nível do usuário atribuídas aos usuários e habilita a configuração no nível do locatário.

Para verificar quais políticas de acesso externo no nível do usuário existem e a quem elas são atribuídas, você pode usar as seguintes etapas:
    
3. Verifique quais políticas de acesso externo no nível do usuário existem.

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

- Atribuir uma política a um conjunto de usuários: [New-CsBatchPolicyAssignmentOperation](/powershell/module/skype/new-csbatchpolicyassignmentoperation)

Depois que as políticas de acesso externo no nível do usuário são definidas corretamente para os usuários em seu locatário, você pode habilitar a configuração de nível de locatário (`AllowTeamsConsumer`) para o locatário usando o seguinte cmdlet:

- Definir as configurações de federação para seu locatário: [Set-CsTenantFederationConfiguration](/powershell/module/skype/set-cstenantfederationconfiguration)

## <a name="enabling-the-parents-app"></a>Habilitando o aplicativo Pais

O aplicativo Pais está desabilitado por padrão, portanto, os proprietários da equipe de classe não verão o aplicativo em suas equipes de classe até que o aplicativo seja permitido por meio do centro de administração Teams de classe. O aplicativo pode ser permitido por meio do Teams de administração usando [Permitir aplicativos bloqueados por editores](manage-apps.md#apps-blocked-by-publishers).

A qualquer momento, o aplicativo pode ser desabilitado no nível do locatário usando [Permitir e bloquear aplicativos](manage-apps.md#allow-and-block-apps) no Teams de administração. Se o aplicativo estiver desabilitado no nível do locatário, ele será bloqueado para todos os usuários, mesmo que as permissões no nível do usuário sejam habilitadas.

O aplicativo também pode ser desabilitado no nível do usuário usando [Gerenciar políticas de](teams-app-permission-policies.md) permissão do aplicativo Microsoft Teams.

## <a name="more-information"></a>Mais informações

- [CsExternalAccessPolicy](/powershell/module/skype/set-csexternalaccesspolicy)
- [CsTenantFederationConfiguration](/powershell/module/skype/set-cstenantfederationconfiguration)
