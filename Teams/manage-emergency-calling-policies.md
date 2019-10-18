---
title: Gerenciar políticas de chamadas de emergência no Microsoft Teams
author: lanachin
ms.author: v-lanac
manager: serdars
ms.reviewer: jastark, roykuntz
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: Saiba como usar e gerenciar políticas de chamadas de emergência para o recurso de E911 dinâmico no Microsoft Teams.
f1keywords: ms.teamsadmincenter.voice.emergencycallingpolicies.overview
ms.openlocfilehash: 4a1846217734142388fdf3466f68ccadea49c829
ms.sourcegitcommit: 0dcd078947a455a388729fd50c7a939dd93b0b61
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2019
ms.locfileid: "37573171"
---
# <a name="manage-emergency-calling-policies-in-microsoft-teams"></a>Gerenciar políticas de chamadas de emergência no Microsoft Teams

[!INCLUDE [preview-feature](includes/preview-feature.md)]

Se a sua organização usar planos de chamadas ou roteamento direto do sistema telefônico implantado, você poderá usar políticas de chamadas de emergência no Microsoft Teams para definir o que acontece quando um usuário do teams na sua organização faz uma chamada de emergência. Você pode definir quem deseja notificar e como eles são notificados quando um usuário ao qual a política é atribuída faz chamadas de serviços de emergência. Por exemplo, você pode definir as configurações de política para notificar automaticamente a equipe de segurança da sua organização e fazer com que elas escutem em chamadas de emergência.  

Para gerenciar as políticas de chamadas de emergência, acesse**as políticas de emergência** de **voz** > no centro de administração do Microsoft Teams ou usando o Windows PowerShell. As políticas podem ser atribuídas a usuários e [sites de rede](location-based-routing-terminology.md).

Para os usuários, você pode usar a política global (padrão para toda a organização) ou criar e atribuir políticas personalizadas. Os usuários receberão automaticamente a política global, a menos que você crie e atribua uma política personalizada. Lembre-se de que você pode editar as configurações na política global, mas não pode renomeá-la ou excluí-la. Para sites de rede, você cria e atribui políticas personalizadas.

Se você tiver atribuído uma política de chamadas de emergência a um site de rede e a um usuário e se esse usuário estiver nesse site de rede, a política que é atribuída ao site da rede substituirá a política atribuída ao usuário.

## <a name="create-a-custom-emergency-calling-policy"></a>Criar uma política de chamadas de emergência personalizada

### <a name="using-the-microsoft-teams-admin-center"></a>Usar o centro de administração do Microsoft Teams

1. Na navegação à esquerda do centro de administração do Microsoft Teams, vá para**políticas de emergência**de **voz** > e clique na guia **políticas de chamadas** .
2. Clique em **Adicionar**.
3. Insira um nome e uma descrição para a política.
4. Defina como você deseja notificar as pessoas em sua organização, geralmente a segurança, quando uma chamada de emergência é feita. Para fazer isso, em **modo de notificação**, selecione uma das seguintes opções:
    - **Somente notificação**: uma mensagem de chat do teams é enviada aos usuários e grupos que você especificar.
    - **Em conferência, mas com mudo ativado**: uma mensagem de chat do teams é enviada aos usuários e grupos que você especifica e podem ouvir (mas não participar) da conversa entre o chamador e o operador PSAP.
5.  Se você tiver selecionado o modo de notificação **em conferência, mas estiver mudo** , na caixa **número para discagem para notificações** , você pode digitar um número de telefone PSTN de um usuário ou grupo para chamar e ingressar na chamada de emergência. Por exemplo, digite o número da central de segurança da sua organização, que receberá uma chamada quando uma chamada de emergência for feita e poderá ouvi-la ou participar da chamada.
6. Procure e selecione um ou mais usuários ou grupos, como a mesa de segurança da sua organização, para notificar quando uma chamada de emergência é feita.  A notificação pode ser enviada para endereços de email de usuários, grupos de distribuição e grupos de segurança. Um máximo de 50 usuários pode ser notificado.
7. Clique em **Salvar**.

### <a name="using-powershell"></a>Usando o PowerShell

Veja [New-CsTeamsEmergencyCallingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csteamsemergencycallingpolicy).

## <a name="edit-an-emergency-calling-policy"></a>Editar uma política de chamadas de emergência

### <a name="using-the-microsoft-teams-admin-center"></a>Usar o centro de administração do Microsoft Teams

Você pode editar a política global ou qualquer política personalizada criada.

1. Na navegação à esquerda do centro de administração do Microsoft Teams, vá para**políticas de emergência**de **voz** > e clique na guia **políticas de chamadas** .
2. Selecione a política clicando à esquerda do nome da política e, em seguida, clique em **Editar**.
3. Faça as alterações desejadas e clique em **salvar**.

### <a name="using-powershell"></a>Usando o PowerShell

Consulte [set-CsTeamsEmergencyCallingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsemergencycallingpolicy).

## <a name="assign-a-custom-emergency-calling-policy-to-users"></a>Atribuir uma política de chamadas de emergência personalizada aos usuários

### <a name="using-the-microsoft-teams-admin-center"></a>Usar o centro de administração do Microsoft Teams

1. Na navegação à esquerda do centro de administração do Microsoft Teams, vá para **usuários**e, em seguida, clique no usuário.
2. Clique em **políticas**e, em seguida, ao lado de **políticas atribuídas**, clique em **Editar**.
3. Em **política de chamadas de emergência**, selecione a política que você deseja atribuir e clique em **salvar**.

Para atribuir uma política personalizada do teams a vários usuários de uma só vez, consulte [Editar configurações de usuários do teams em massa](edit-user-settings-in-bulk.md).

Ou, você também pode fazer o seguinte:

1. Na navegação à esquerda do centro de administração do Microsoft Teams, vá para**políticas de emergência**de **voz** > e clique na guia **políticas de chamadas** .
2. Selecione a política clicando à esquerda do nome da política.
3. Selecione **gerenciar usuários**.
4. No painel **gerenciar usuários** , procure pelo usuário por nome para exibição ou por nome de usuário, selecione o nome e, em seguida, selecione **Adicionar**. Repita esta etapa para cada usuário que você deseja adicionar.
5. Quando tiver terminado de adicionar usuários, clique em **salvar**.

### <a name="using-powershell"></a>Usando o PowerShell

#### <a name="assign-a-custom-emergency-calling-policy-to-a-user"></a>Atribuir uma política de chamadas de emergência personalizada a um usuário

Veja [Grant-CsTeamsEmergencyCallingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsemergencycallingpolicy).

#### <a name="assign-a-custom-emergency-calling-policy-to-users-in-a-group"></a>Atribuir uma política de chamadas de emergência personalizada a usuários em um grupo

Você pode querer atribuir uma política de chamadas de emergência personalizada a vários usuários que você já tenha identificado. Por exemplo, você pode querer atribuir uma política a todos os usuários de um grupo de segurança. Você pode fazer isso conectando-se ao módulo do PowerShell do Azure Active Directory e ao módulo do PowerShell do Skype for Business.

Neste exemplo, atribuímos uma política chamada política de chamadas de emergência de operações a todos os usuários no grupo de operações da contoso.  

> [!NOTE]
> Verifique se você se conectou primeiro ao módulo do PowerShell do Azure Active Directory e do módulo do PowerShell do Skype for Business seguindo as etapas em [conectar a todos os serviços do Office 365 em uma única janela do Windows PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-all-office-365-services-in-a-single-windows-powershell-window).

Obtenha o GroupObjectId do grupo específico.
```
$group = Get-AzureADGroup -SearchString "Contoso Operations"
```
Obter os membros do grupo especificado.
```
$members = Get-AzureADGroupMember -ObjectId $group.ObjectId -All $true | Where-Object {$_.ObjectType -eq "User"}
```
Atribua todos os usuários do grupo a uma política específica do teams. Neste exemplo, a política de roteamento de chamadas de emergência de emergência.
```
$members | ForEach-Object { Grant-CsTeamsChannelsPolicy -PolicyName "Operations Emergency Calling Policy" -Identity $_.EmailAddress}
``` 
Dependendo do número de membros do grupo, esse comando pode levar alguns minutos para ser executado.

## <a name="assign-a-custom-emergency-calling-policy-to-a-network-site"></a>Atribuir uma política de chamadas de emergência personalizada a um site de rede

Use o cmdlet [set-CsTenantNetworkSite](https://docs.microsoft.com/powershell/module/skype/set-cstenantnetworksite) para atribuir uma política de chamadas de emergência a um site de rede.

O exemplo a seguir mostra como atribuir uma política chamada política de chamada de emergência da Contoso 1 ao site do site1.

    ```
    Set-CsTenantNetworkSite -identity "site1" -EmergencyCallingPolicy "Contoso Emergency Calling Policy 1"
    ```

## <a name="related-topics"></a>Tópicos relacionados

- [Gerenciar políticas de roteamento de chamadas de emergência no Teams](manage-emergency-call-routing-policies.md)
- [Visão Geral do PowerShell do Teams](teams-powershell-overview.md)
