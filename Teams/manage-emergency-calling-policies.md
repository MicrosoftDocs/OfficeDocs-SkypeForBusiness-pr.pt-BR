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
ms.openlocfilehash: 1cd358453aa349fde51e4d66de412e8f9e2b72d5
ms.sourcegitcommit: 021c86bf579e315f15815dcddf232a0c651cbf6b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/26/2019
ms.locfileid: "39615741"
---
# <a name="manage-emergency-calling-policies-in-microsoft-teams"></a><span data-ttu-id="e2c61-103">Gerenciar políticas de chamadas de emergência no Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="e2c61-103">Manage emergency calling policies in Microsoft Teams</span></span>

[!INCLUDE [preview-feature](includes/preview-feature.md)]

<span data-ttu-id="e2c61-104">Se a sua organização usar planos de chamadas ou roteamento direto do sistema telefônico implantado, você poderá usar políticas de chamadas de emergência no Microsoft Teams para definir o que acontece quando um usuário do teams na sua organização faz uma chamada de emergência.</span><span class="sxs-lookup"><span data-stu-id="e2c61-104">If your organization uses Calling Plans or deployed Phone System Direct Routing, you can use emergency calling policies in Microsoft Teams to define what happens when a Teams user in your organization makes an emergency call.</span></span> <span data-ttu-id="e2c61-105">Você pode definir quem deseja notificar e como eles são notificados quando um usuário ao qual a política é atribuída faz chamadas de serviços de emergência.</span><span class="sxs-lookup"><span data-stu-id="e2c61-105">You can set who to notify and how they are notified when a user who is assigned the policy calls emergency services.</span></span> <span data-ttu-id="e2c61-106">Por exemplo, você pode definir as configurações de política para notificar automaticamente a equipe de segurança da sua organização e fazer com que elas escutem em chamadas de emergência.</span><span class="sxs-lookup"><span data-stu-id="e2c61-106">For example, you can configure policy settings to automatically notify your organization's security desk and have them listen in emergency calls.</span></span>  

<span data-ttu-id="e2c61-107">Para gerenciar as políticas de chamadas de emergência, acesse**as políticas de emergência** de **voz** > no centro de administração do Microsoft Teams ou usando o Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="e2c61-107">You manage emergency calling policies by going to **Voice** > **Emergency policies** in the Microsoft Teams admin center or by using Windows PowerShell.</span></span> <span data-ttu-id="e2c61-108">As políticas podem ser atribuídas a usuários e [sites de rede](cloud-voice-network-settings.md).</span><span class="sxs-lookup"><span data-stu-id="e2c61-108">The policies can be assigned to users and [network sites](cloud-voice-network-settings.md).</span></span>

<span data-ttu-id="e2c61-109">Para os usuários, você pode usar a política global (padrão para toda a organização) ou criar e atribuir políticas personalizadas.</span><span class="sxs-lookup"><span data-stu-id="e2c61-109">For users, you can use the global (Org-wide default) policy or create and assign custom policies.</span></span> <span data-ttu-id="e2c61-110">Os usuários receberão automaticamente a política global, a menos que você crie e atribua uma política personalizada.</span><span class="sxs-lookup"><span data-stu-id="e2c61-110">Users will automatically get the global policy unless you create and assign a custom policy.</span></span> <span data-ttu-id="e2c61-111">Lembre-se de que você pode editar as configurações na política global, mas não pode renomeá-la ou excluí-la.</span><span class="sxs-lookup"><span data-stu-id="e2c61-111">Keep in mind that you can edit the settings in the global policy but you can't rename or delete it.</span></span> <span data-ttu-id="e2c61-112">Para sites de rede, você cria e atribui políticas personalizadas.</span><span class="sxs-lookup"><span data-stu-id="e2c61-112">For network sites, you create and assign custom policies.</span></span>

<span data-ttu-id="e2c61-113">Se você tiver atribuído uma política de chamadas de emergência a um site de rede e a um usuário e se esse usuário estiver nesse site de rede, a política que é atribuída ao site da rede substituirá a política atribuída ao usuário.</span><span class="sxs-lookup"><span data-stu-id="e2c61-113">If you assigned an emergency calling policy to a network site and to a user and if that user is at that network site, the policy that's assigned to the network site overrides the policy that's assigned to the user.</span></span>

## <a name="create-a-custom-emergency-calling-policy"></a><span data-ttu-id="e2c61-114">Criar uma política de chamadas de emergência personalizada</span><span class="sxs-lookup"><span data-stu-id="e2c61-114">Create a custom emergency calling policy</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="e2c61-115">Usar o centro de administração do Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="e2c61-115">Using the Microsoft Teams admin center</span></span>

1. <span data-ttu-id="e2c61-116">Na navegação à esquerda do centro de administração do Microsoft Teams, vá para**políticas de emergência**de **voz** > e clique na guia **políticas de chamadas** .</span><span class="sxs-lookup"><span data-stu-id="e2c61-116">In the left navigation of the Microsoft Teams admin center, go to **Voice** > **Emergency policies**, and then click the **Calling policies** tab.</span></span>
2. <span data-ttu-id="e2c61-117">Clique em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="e2c61-117">Click **Add**.</span></span>
3. <span data-ttu-id="e2c61-118">Insira um nome e uma descrição para a política.</span><span class="sxs-lookup"><span data-stu-id="e2c61-118">Enter a name and description for the policy.</span></span>
4. <span data-ttu-id="e2c61-119">Defina como você deseja notificar as pessoas em sua organização, geralmente a segurança, quando uma chamada de emergência é feita.</span><span class="sxs-lookup"><span data-stu-id="e2c61-119">Set how you want to notify people in your organization, typically the security desk, when an emergency call is made.</span></span> <span data-ttu-id="e2c61-120">Para fazer isso, em **modo de notificação**, selecione uma das seguintes opções:</span><span class="sxs-lookup"><span data-stu-id="e2c61-120">To do this, under **Notification mode**, select one of the following:</span></span>
    - <span data-ttu-id="e2c61-121">**Somente notificação**: uma mensagem de chat do teams é enviada aos usuários e grupos que você especificar.</span><span class="sxs-lookup"><span data-stu-id="e2c61-121">**Notification only**: A Teams chat message is sent to the users and groups that you specify.</span></span>
    - <span data-ttu-id="e2c61-122">**Em conferência, mas com mudo ativado**: uma mensagem de chat do teams é enviada aos usuários e grupos que você especifica e podem ouvir (mas não participar) da conversa entre o chamador e o operador PSAP.</span><span class="sxs-lookup"><span data-stu-id="e2c61-122">**Conferenced in but are muted**: A Teams chat message is sent to the users and groups that you specify and they can listen (but not participate) in the conversation between the caller and the PSAP operator.</span></span>
5.  <span data-ttu-id="e2c61-123">Se você tiver selecionado o modo de notificação **em conferência, mas estiver mudo** , na caixa **número para discagem para notificações** , você pode digitar um número de telefone PSTN de um usuário ou grupo para chamar e ingressar na chamada de emergência.</span><span class="sxs-lookup"><span data-stu-id="e2c61-123">If you selected the **Conferenced in but are muted** notification mode, in the **Dial-out number for notifications** box, you can enter a PSTN phone number of a user or group to call and join the emergency call.</span></span> <span data-ttu-id="e2c61-124">Por exemplo, digite o número da central de segurança da sua organização, que receberá uma chamada quando uma chamada de emergência for feita e poderá ouvi-la ou participar da chamada.</span><span class="sxs-lookup"><span data-stu-id="e2c61-124">For example, enter the number of your organization's security desk, who will receive a call when an emergency call is made and can then listen in or participate in the call.</span></span>
6. <span data-ttu-id="e2c61-125">Procure e selecione um ou mais usuários ou grupos, como a mesa de segurança da sua organização, para notificar quando uma chamada de emergência é feita.</span><span class="sxs-lookup"><span data-stu-id="e2c61-125">Search for and select one or more users or groups, such as your organization's security desk, to notify when an emergency call is made.</span></span>  <span data-ttu-id="e2c61-126">A notificação pode ser enviada para endereços de email de usuários, grupos de distribuição e grupos de segurança.</span><span class="sxs-lookup"><span data-stu-id="e2c61-126">The notification can be sent to email addresses of users, distribution groups, and security groups.</span></span> <span data-ttu-id="e2c61-127">Um máximo de 50 usuários pode ser notificado.</span><span class="sxs-lookup"><span data-stu-id="e2c61-127">A maximum of 50 users can be notified.</span></span>
7. <span data-ttu-id="e2c61-128">Clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="e2c61-128">Click **Save**.</span></span>

### <a name="using-powershell"></a><span data-ttu-id="e2c61-129">Usando o PowerShell</span><span class="sxs-lookup"><span data-stu-id="e2c61-129">Using PowerShell</span></span>

<span data-ttu-id="e2c61-130">Veja [New-CsTeamsEmergencyCallingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csteamsemergencycallingpolicy).</span><span class="sxs-lookup"><span data-stu-id="e2c61-130">See [New-CsTeamsEmergencyCallingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csteamsemergencycallingpolicy).</span></span>

## <a name="edit-an-emergency-calling-policy"></a><span data-ttu-id="e2c61-131">Editar uma política de chamadas de emergência</span><span class="sxs-lookup"><span data-stu-id="e2c61-131">Edit an emergency calling policy</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="e2c61-132">Usar o centro de administração do Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="e2c61-132">Using the Microsoft Teams admin center</span></span>

<span data-ttu-id="e2c61-133">Você pode editar a política global ou qualquer política personalizada criada.</span><span class="sxs-lookup"><span data-stu-id="e2c61-133">You can edit the global policy or any custom policies that you create.</span></span>

1. <span data-ttu-id="e2c61-134">Na navegação à esquerda do centro de administração do Microsoft Teams, vá para**políticas de emergência**de **voz** > e clique na guia **políticas de chamadas** .</span><span class="sxs-lookup"><span data-stu-id="e2c61-134">In the left navigation of the Microsoft Teams admin center, go to **Voice** > **Emergency policies**, and then click the **Calling policies** tab.</span></span>
2. <span data-ttu-id="e2c61-135">Selecione a política clicando à esquerda do nome da política e, em seguida, clique em **Editar**.</span><span class="sxs-lookup"><span data-stu-id="e2c61-135">Select the policy by clicking to the left of the policy name, and then click **Edit**.</span></span>
3. <span data-ttu-id="e2c61-136">Faça as alterações desejadas e clique em **salvar**.</span><span class="sxs-lookup"><span data-stu-id="e2c61-136">Make the changes that you want, and then click **Save**.</span></span>

### <a name="using-powershell"></a><span data-ttu-id="e2c61-137">Usando o PowerShell</span><span class="sxs-lookup"><span data-stu-id="e2c61-137">Using PowerShell</span></span>

<span data-ttu-id="e2c61-138">Consulte [set-CsTeamsEmergencyCallingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsemergencycallingpolicy).</span><span class="sxs-lookup"><span data-stu-id="e2c61-138">See [Set-CsTeamsEmergencyCallingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsemergencycallingpolicy).</span></span>

## <a name="assign-a-custom-emergency-calling-policy-to-users"></a><span data-ttu-id="e2c61-139">Atribuir uma política de chamadas de emergência personalizada aos usuários</span><span class="sxs-lookup"><span data-stu-id="e2c61-139">Assign a custom emergency calling policy to users</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="e2c61-140">Usar o centro de administração do Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="e2c61-140">Using the Microsoft Teams admin center</span></span>

1. <span data-ttu-id="e2c61-141">Na navegação à esquerda do centro de administração do Microsoft Teams, vá para **usuários**e, em seguida, clique no usuário.</span><span class="sxs-lookup"><span data-stu-id="e2c61-141">In the left navigation of the Microsoft Teams admin center, go to **Users**, and then click the user.</span></span>
2. <span data-ttu-id="e2c61-142">Clique em **políticas**e, em seguida, ao lado de **políticas atribuídas**, clique em **Editar**.</span><span class="sxs-lookup"><span data-stu-id="e2c61-142">Click **Policies**, and then next to **Assigned policies**, click **Edit**.</span></span>
3. <span data-ttu-id="e2c61-143">Em **política de chamadas de emergência**, selecione a política que você deseja atribuir e clique em **salvar**.</span><span class="sxs-lookup"><span data-stu-id="e2c61-143">Under **Emergency calling policy**, select the policy you want to assign, and then click **Save**.</span></span>

<span data-ttu-id="e2c61-144">Para atribuir uma política personalizada do teams a vários usuários de uma só vez, consulte [Editar configurações de usuários do teams em massa](edit-user-settings-in-bulk.md).</span><span class="sxs-lookup"><span data-stu-id="e2c61-144">To assign a custom teams policy to multiple users at a time, see [Edit Teams user settings in bulk](edit-user-settings-in-bulk.md).</span></span>

<span data-ttu-id="e2c61-145">Ou, você também pode fazer o seguinte:</span><span class="sxs-lookup"><span data-stu-id="e2c61-145">Or, you can also do the following:</span></span>

1. <span data-ttu-id="e2c61-146">Na navegação à esquerda do centro de administração do Microsoft Teams, vá para**políticas de emergência**de **voz** > e clique na guia **políticas de chamadas** .</span><span class="sxs-lookup"><span data-stu-id="e2c61-146">In the left navigation of the Microsoft Teams admin center, go to **Voice** > **Emergency policies**, and then click the **Calling policies** tab.</span></span>
2. <span data-ttu-id="e2c61-147">Escolha a política clicando à esquerda do nome da política.</span><span class="sxs-lookup"><span data-stu-id="e2c61-147">Select the policy by clicking to the left of the policy name.</span></span>
3. <span data-ttu-id="e2c61-148">Escolha **Gerenciar usuários**.</span><span class="sxs-lookup"><span data-stu-id="e2c61-148">Select **Manage users**.</span></span>
4. <span data-ttu-id="e2c61-149">No painel **Gerenciar usuários**, procure o usuário pelo nome de exibição ou pelo nome de usuário, escolha o nome e marque **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="e2c61-149">In the **Manage users** pane, search for the user by display name or by user name, select the name, and then select **Add**.</span></span> <span data-ttu-id="e2c61-150">Repita esta etapa para cada usuário que você deseja adicionar.</span><span class="sxs-lookup"><span data-stu-id="e2c61-150">Repeat this step for each user that you want to add.</span></span>
5. <span data-ttu-id="e2c61-151">Quando tiver terminado de adicionar usuários, clique em **salvar**.</span><span class="sxs-lookup"><span data-stu-id="e2c61-151">When you're finished adding users, click **Save**.</span></span>

### <a name="using-powershell"></a><span data-ttu-id="e2c61-152">Usando o PowerShell</span><span class="sxs-lookup"><span data-stu-id="e2c61-152">Using PowerShell</span></span>

#### <a name="assign-a-custom-emergency-calling-policy-to-a-user"></a><span data-ttu-id="e2c61-153">Atribuir uma política de chamadas de emergência personalizada a um usuário</span><span class="sxs-lookup"><span data-stu-id="e2c61-153">Assign a custom emergency calling policy to a user</span></span>

<span data-ttu-id="e2c61-154">Veja [Grant-CsTeamsEmergencyCallingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsemergencycallingpolicy).</span><span class="sxs-lookup"><span data-stu-id="e2c61-154">See [Grant-CsTeamsEmergencyCallingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsemergencycallingpolicy).</span></span>

#### <a name="assign-a-custom-emergency-calling-policy-to-users-in-a-group"></a><span data-ttu-id="e2c61-155">Atribuir uma política de chamadas de emergência personalizada a usuários em um grupo</span><span class="sxs-lookup"><span data-stu-id="e2c61-155">Assign a custom emergency calling policy to users in a group</span></span>

<span data-ttu-id="e2c61-156">Você pode querer atribuir uma política de chamadas de emergência personalizada a vários usuários que você já tenha identificado.</span><span class="sxs-lookup"><span data-stu-id="e2c61-156">You may want to assign a custom emergency calling policy to multiple users that you’ve already identified.</span></span> <span data-ttu-id="e2c61-157">Por exemplo, você pode querer atribuir uma política a todos os usuários de um grupo de segurança.</span><span class="sxs-lookup"><span data-stu-id="e2c61-157">For example, you may want to assign a policy to all users in a security group.</span></span> <span data-ttu-id="e2c61-158">Você pode fazer isso conectando-se ao módulo do PowerShell do Azure Active Directory e ao módulo do PowerShell do Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="e2c61-158">You can do this by connecting to the Azure Active Directory PowerShell for Graph module and the Skype for Business PowerShell module.</span></span>

<span data-ttu-id="e2c61-159">Neste exemplo, atribuímos uma política chamada política de chamadas de emergência de operações a todos os usuários no grupo de operações da contoso.</span><span class="sxs-lookup"><span data-stu-id="e2c61-159">In this example, we assign a policy called Operations Emergency Calling Policy to all users in the Contoso Operations group.</span></span>  

> [!NOTE]
> <span data-ttu-id="e2c61-160">Verifique se você se conectou primeiro ao módulo do PowerShell do Azure Active Directory e do módulo do PowerShell do Skype for Business seguindo as etapas em [conectar a todos os serviços do Office 365 em uma única janela do Windows PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-all-office-365-services-in-a-single-windows-powershell-window).</span><span class="sxs-lookup"><span data-stu-id="e2c61-160">Make sure you first connect to the Azure Active Directory PowerShell for Graph module and Skype for Business PowerShell module by following the steps in [Connect to all Office 365 services in a single Windows PowerShell window](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-all-office-365-services-in-a-single-windows-powershell-window).</span></span>

<span data-ttu-id="e2c61-161">Obtenha o GroupObjectId do grupo específico.</span><span class="sxs-lookup"><span data-stu-id="e2c61-161">Get the GroupObjectId of the particular group.</span></span>
```
$group = Get-AzureADGroup -SearchString "Contoso Operations"
```
<span data-ttu-id="e2c61-162">Obter os membros do grupo especificado.</span><span class="sxs-lookup"><span data-stu-id="e2c61-162">Get the members of the specified group.</span></span>
```
$members = Get-AzureADGroupMember -ObjectId $group.ObjectId -All $true | Where-Object {$_.ObjectType -eq "User"}
```
<span data-ttu-id="e2c61-163">Atribua todos os usuários do grupo a uma política específica do teams.</span><span class="sxs-lookup"><span data-stu-id="e2c61-163">Assign all users in the group to a particular teams policy.</span></span> <span data-ttu-id="e2c61-164">Neste exemplo, a política de roteamento de chamadas de emergência de emergência.</span><span class="sxs-lookup"><span data-stu-id="e2c61-164">In this example, it's Operations Emergency Call Routing Policy.</span></span>
```
$members | ForEach-Object { Grant-CsTeamsChannelsPolicy -PolicyName "Operations Emergency Calling Policy" -Identity $_.EmailAddress}
``` 
<span data-ttu-id="e2c61-165">Dependendo do número de membros do grupo, esse comando pode levar alguns minutos para ser executado.</span><span class="sxs-lookup"><span data-stu-id="e2c61-165">Depending on the number of members in the group, this command may take several minutes to execute.</span></span>

## <a name="assign-a-custom-emergency-calling-policy-to-a-network-site"></a><span data-ttu-id="e2c61-166">Atribuir uma política de chamadas de emergência personalizada a um site de rede</span><span class="sxs-lookup"><span data-stu-id="e2c61-166">Assign a custom emergency calling policy to a network site</span></span>

<span data-ttu-id="e2c61-167">Use o cmdlet [set-CsTenantNetworkSite](https://docs.microsoft.com/powershell/module/skype/set-cstenantnetworksite) para atribuir uma política de chamadas de emergência a um site de rede.</span><span class="sxs-lookup"><span data-stu-id="e2c61-167">Use the [Set-CsTenantNetworkSite](https://docs.microsoft.com/powershell/module/skype/set-cstenantnetworksite) cmdlet to assign an emergency calling policy to a network site.</span></span>

<span data-ttu-id="e2c61-168">O exemplo a seguir mostra como atribuir uma política chamada política de chamada de emergência da Contoso 1 ao site do site1.</span><span class="sxs-lookup"><span data-stu-id="e2c61-168">The following example shows how to assign a policy called Contoso Emergency Calling Policy 1 to the Site1 site.</span></span>

    ```
    Set-CsTenantNetworkSite -identity "site1" -EmergencyCallingPolicy "Contoso Emergency Calling Policy 1"
    ```

## <a name="related-topics"></a><span data-ttu-id="e2c61-169">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="e2c61-169">Related topics</span></span>

- [<span data-ttu-id="e2c61-170">Gerenciar políticas de roteamento de chamadas de emergência no Teams</span><span class="sxs-lookup"><span data-stu-id="e2c61-170">Manage emergency call routing policies in Teams</span></span>](manage-emergency-call-routing-policies.md)
- [<span data-ttu-id="e2c61-171">Visão Geral do PowerShell do Teams</span><span class="sxs-lookup"><span data-stu-id="e2c61-171">Teams PowerShell overview</span></span>](teams-powershell-overview.md)
