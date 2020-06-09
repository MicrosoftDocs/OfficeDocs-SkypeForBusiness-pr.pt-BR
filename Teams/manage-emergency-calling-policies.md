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
f1.keywords: ms.teamsadmincenter.voice.emergencycallingpolicies.overview
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: Saiba como usar e gerenciar políticas de chamadas de emergência no Microsoft Teams para definir o que acontece quando um usuário do teams na sua organização faz uma chamada de emergência.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 79332a8675273e86476a68f43489c202b03faea9
ms.sourcegitcommit: 3323c86f31c5ab304944a34892601fcc7b448025
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/09/2020
ms.locfileid: "44638680"
---
# <a name="manage-emergency-calling-policies-in-microsoft-teams"></a><span data-ttu-id="e15dc-103">Gerenciar políticas de chamadas de emergência no Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="e15dc-103">Manage emergency calling policies in Microsoft Teams</span></span>

<span data-ttu-id="e15dc-104">Se a sua organização usar [planos de chamadas](set-up-calling-plans.md) ou [Roteamento direto do sistema telefônico](direct-routing-landing-page.md)implantado, você poderá usar políticas de chamadas de emergência no Microsoft Teams para definir o que acontece quando um usuário do teams na sua organização faz uma chamada de emergência.</span><span class="sxs-lookup"><span data-stu-id="e15dc-104">If your organization uses [Calling Plans](set-up-calling-plans.md) or deployed [Phone System Direct Routing](direct-routing-landing-page.md), you can use emergency calling policies in Microsoft Teams to define what happens when a Teams user in your organization makes an emergency call.</span></span> <span data-ttu-id="e15dc-105">Você pode definir quem deseja notificar e como eles são notificados quando um usuário ao qual a política é atribuída faz chamadas de serviços de emergência.</span><span class="sxs-lookup"><span data-stu-id="e15dc-105">You can set who to notify and how they are notified when a user who is assigned the policy calls emergency services.</span></span> <span data-ttu-id="e15dc-106">Por exemplo, você pode definir as configurações de política para notificar automaticamente a equipe de segurança da sua organização e fazer com que elas escutem em chamadas de emergência.</span><span class="sxs-lookup"><span data-stu-id="e15dc-106">For example, you can configure policy settings to automatically notify your organization's security desk and have them listen in emergency calls.</span></span>  

<span data-ttu-id="e15dc-107">Para gerenciar as políticas de chamadas de emergência **Voice**,  >  acesse**as políticas de emergência** de voz no centro de administração do Microsoft Teams ou usando o Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="e15dc-107">You manage emergency calling policies by going to **Voice** > **Emergency policies** in the Microsoft Teams admin center or by using Windows PowerShell.</span></span> <span data-ttu-id="e15dc-108">As políticas podem ser atribuídas a usuários e [sites de rede](cloud-voice-network-settings.md).</span><span class="sxs-lookup"><span data-stu-id="e15dc-108">The policies can be assigned to users and [network sites](cloud-voice-network-settings.md).</span></span>

<span data-ttu-id="e15dc-109">Para os usuários, você pode usar a política global (padrão para toda a organização) ou criar e atribuir políticas personalizadas.</span><span class="sxs-lookup"><span data-stu-id="e15dc-109">For users, you can use the global (Org-wide default) policy or create and assign custom policies.</span></span> <span data-ttu-id="e15dc-110">Os usuários receberão automaticamente a política global, a menos que você crie e atribua uma política personalizada.</span><span class="sxs-lookup"><span data-stu-id="e15dc-110">Users will automatically get the global policy unless you create and assign a custom policy.</span></span> <span data-ttu-id="e15dc-111">Lembre-se de que você pode editar as configurações na política global, mas não pode renomeá-la ou excluí-la.</span><span class="sxs-lookup"><span data-stu-id="e15dc-111">Keep in mind that you can edit the settings in the global policy but you can't rename or delete it.</span></span> <span data-ttu-id="e15dc-112">Para sites de rede, você cria e atribui políticas personalizadas.</span><span class="sxs-lookup"><span data-stu-id="e15dc-112">For network sites, you create and assign custom policies.</span></span>

<span data-ttu-id="e15dc-113">Se você tiver atribuído uma política de chamadas de emergência a um site de rede e a um usuário e se esse usuário estiver nesse site de rede, a política que é atribuída ao site da rede substituirá a política atribuída ao usuário.</span><span class="sxs-lookup"><span data-stu-id="e15dc-113">If you assigned an emergency calling policy to a network site and to a user and if that user is at that network site, the policy that's assigned to the network site overrides the policy that's assigned to the user.</span></span>

## <a name="create-a-custom-emergency-calling-policy"></a><span data-ttu-id="e15dc-114">Criar uma política de chamadas de emergência personalizada</span><span class="sxs-lookup"><span data-stu-id="e15dc-114">Create a custom emergency calling policy</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="e15dc-115">Usando o centro de administração do Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="e15dc-115">Using the Microsoft Teams admin center</span></span>

1. <span data-ttu-id="e15dc-116">Na navegação à esquerda do centro de administração do Microsoft Teams, vá para políticas de emergência de **voz**  >  **Emergency policies**e clique na guia **políticas de chamadas** .</span><span class="sxs-lookup"><span data-stu-id="e15dc-116">In the left navigation of the Microsoft Teams admin center, go to **Voice** > **Emergency policies**, and then click the **Calling policies** tab.</span></span>
2. <span data-ttu-id="e15dc-117">Clique em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="e15dc-117">Click **Add**.</span></span>
3. <span data-ttu-id="e15dc-118">Insira um nome e uma descrição para a política.</span><span class="sxs-lookup"><span data-stu-id="e15dc-118">Enter a name and description for the policy.</span></span>
4. <span data-ttu-id="e15dc-119">Defina como você deseja notificar as pessoas em sua organização, geralmente a segurança, quando uma chamada de emergência é feita.</span><span class="sxs-lookup"><span data-stu-id="e15dc-119">Set how you want to notify people in your organization, typically the security desk, when an emergency call is made.</span></span> <span data-ttu-id="e15dc-120">Para fazer isso, em **modo de notificação**, selecione uma das seguintes opções:</span><span class="sxs-lookup"><span data-stu-id="e15dc-120">To do this, under **Notification mode**, select one of the following:</span></span>
    - <span data-ttu-id="e15dc-121">**Enviar somente notificação**: uma mensagem de chat do teams é enviada aos usuários e grupos que você especificar.</span><span class="sxs-lookup"><span data-stu-id="e15dc-121">**Send notification only**: A Teams chat message is sent to the users and groups that you specify.</span></span>
    - <span data-ttu-id="e15dc-122">**Em conferência, mas com mudo ativado**: uma mensagem de chat do teams é enviada aos usuários e grupos que você especifica e podem ouvir (mas não participar) da conversa entre o chamador e o operador PSAP.</span><span class="sxs-lookup"><span data-stu-id="e15dc-122">**Conferenced in but are muted**: A Teams chat message is sent to the users and groups that you specify and they can listen (but not participate) in the conversation between the caller and the PSAP operator.</span></span>
    - <span data-ttu-id="e15dc-123">**Em conferência e com mudo ativado (em** **breve)**: uma mensagem de chat do teams é enviada para os usuários e grupos que você especifica e pode desativar o mudo para ouvir e participar da conversa entre o chamador e o operador PSAP.</span><span class="sxs-lookup"><span data-stu-id="e15dc-123">**Conferenced in and are unmuted** **(coming soon)**: A Teams chat message is sent to the users and groups that you specify and they can unmute to listen and participate in the conversation between the caller and the PSAP operator.</span></span>
5.  <span data-ttu-id="e15dc-124">Se você tiver selecionado o modo de notificação **em conferência mas estiver mudo** , na caixa **números para discar para notificações de chamadas de emergência** , você pode digitar um número de telefone PSTN de um usuário ou grupo para chamar e ingressar na chamada de emergência.</span><span class="sxs-lookup"><span data-stu-id="e15dc-124">If you selected the **Conferenced in but are muted** notification mode, in the **Numbers to dial for emergency calls notifications** box, you can enter a PSTN phone number of a user or group to call and join the emergency call.</span></span> <span data-ttu-id="e15dc-125">Por exemplo, digite o número da central de segurança da sua organização, que receberá uma chamada quando uma chamada de emergência for feita e poderá ouvi-la na chamada.</span><span class="sxs-lookup"><span data-stu-id="e15dc-125">For example, enter the number of your organization's security desk, who will receive a call when an emergency call is made and can then listen in on the call.</span></span>
6. <span data-ttu-id="e15dc-126">Procure e selecione um ou mais usuários ou grupos, como a mesa de segurança da sua organização, para notificar quando uma chamada de emergência é feita.</span><span class="sxs-lookup"><span data-stu-id="e15dc-126">Search for and select one or more users or groups, such as your organization's security desk, to notify when an emergency call is made.</span></span>  <span data-ttu-id="e15dc-127">A notificação pode ser enviada para endereços de email de usuários, grupos de distribuição e grupos de segurança.</span><span class="sxs-lookup"><span data-stu-id="e15dc-127">The notification can be sent to email addresses of users, distribution groups, and security groups.</span></span> <span data-ttu-id="e15dc-128">Um máximo de 50 usuários pode ser notificado.</span><span class="sxs-lookup"><span data-stu-id="e15dc-128">A maximum of 50 users can be notified.</span></span>
7. <span data-ttu-id="e15dc-129">Clique em **Aplicar**.</span><span class="sxs-lookup"><span data-stu-id="e15dc-129">Click **Apply**.</span></span>

### <a name="using-powershell"></a><span data-ttu-id="e15dc-130">Usando o PowerShell</span><span class="sxs-lookup"><span data-stu-id="e15dc-130">Using PowerShell</span></span>

<span data-ttu-id="e15dc-131">Veja [New-CsTeamsEmergencyCallingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csteamsemergencycallingpolicy).</span><span class="sxs-lookup"><span data-stu-id="e15dc-131">See [New-CsTeamsEmergencyCallingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csteamsemergencycallingpolicy).</span></span>

## <a name="edit-an-emergency-calling-policy"></a><span data-ttu-id="e15dc-132">Editar uma política de chamadas de emergência</span><span class="sxs-lookup"><span data-stu-id="e15dc-132">Edit an emergency calling policy</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="e15dc-133">Usando o centro de administração do Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="e15dc-133">Using the Microsoft Teams admin center</span></span>

<span data-ttu-id="e15dc-134">Você pode editar a política global ou qualquer política personalizada criada.</span><span class="sxs-lookup"><span data-stu-id="e15dc-134">You can edit the global policy or any custom policies that you create.</span></span>

1. <span data-ttu-id="e15dc-135">Na navegação à esquerda do centro de administração do Microsoft Teams, vá para políticas de emergência de **voz**  >  **Emergency policies**e clique na guia **políticas de chamadas** .</span><span class="sxs-lookup"><span data-stu-id="e15dc-135">In the left navigation of the Microsoft Teams admin center, go to **Voice** > **Emergency policies**, and then click the **Calling policies** tab.</span></span>
2. <span data-ttu-id="e15dc-136">Selecione a política clicando à esquerda do nome da política e, em seguida, clique em **Editar**.</span><span class="sxs-lookup"><span data-stu-id="e15dc-136">Select the policy by clicking to the left of the policy name, and then click **Edit**.</span></span>
3. <span data-ttu-id="e15dc-137">Faça as alterações desejadas e clique em **salvar**.</span><span class="sxs-lookup"><span data-stu-id="e15dc-137">Make the changes that you want, and then click **Save**.</span></span>

### <a name="using-powershell"></a><span data-ttu-id="e15dc-138">Usando o PowerShell</span><span class="sxs-lookup"><span data-stu-id="e15dc-138">Using PowerShell</span></span>

<span data-ttu-id="e15dc-139">Consulte [set-CsTeamsEmergencyCallingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsemergencycallingpolicy).</span><span class="sxs-lookup"><span data-stu-id="e15dc-139">See [Set-CsTeamsEmergencyCallingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsemergencycallingpolicy).</span></span>

## <a name="assign-a-custom-emergency-calling-policy-to-users"></a><span data-ttu-id="e15dc-140">Atribuir uma política de chamadas de emergência personalizada aos usuários</span><span class="sxs-lookup"><span data-stu-id="e15dc-140">Assign a custom emergency calling policy to users</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="e15dc-141">Usando o centro de administração do Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="e15dc-141">Using the Microsoft Teams admin center</span></span>

<span data-ttu-id="e15dc-142">Para atribuir uma política a um usuário:</span><span class="sxs-lookup"><span data-stu-id="e15dc-142">To assign a policy to one user:</span></span>

1. <span data-ttu-id="e15dc-143">Na barra de navegação à esquerda do centro de administração do Microsoft Teams, vá para **Usuários** e clique no usuário.</span><span class="sxs-lookup"><span data-stu-id="e15dc-143">In the left navigation of the Microsoft Teams admin center, go to **Users**, and then click the user.</span></span>
2. <span data-ttu-id="e15dc-144">Clique em **políticas**e, em seguida, ao lado de **políticas atribuídas**, clique em **Editar**.</span><span class="sxs-lookup"><span data-stu-id="e15dc-144">Click **Policies**, and then next to **Assigned policies**, click **Edit**.</span></span>
3. <span data-ttu-id="e15dc-145">Em **política de chamadas de emergência**, selecione a política que você deseja atribuir e clique em **salvar**.</span><span class="sxs-lookup"><span data-stu-id="e15dc-145">Under **Emergency calling policy**, select the policy you want to assign, and then click **Save**.</span></span>

<span data-ttu-id="e15dc-146">Para atribuir uma política a vários usuários por vez:</span><span class="sxs-lookup"><span data-stu-id="e15dc-146">To assign a policy to multiple users at a time:</span></span>

1. <span data-ttu-id="e15dc-147">Na barra de navegação à esquerda do centro de administração do Microsoft Teams, vá para **Usuários** e, em seguida, pesquise os usuários ou filtre o modo de exibição para mostrar os usuários que você deseja.</span><span class="sxs-lookup"><span data-stu-id="e15dc-147">In the left navigation of the Microsoft Teams admin center, go to **Users**, and then search for the users or filter the view to show the users you want.</span></span>
2. <span data-ttu-id="e15dc-148">Na coluna **&#x2713;** (marca de seleção), selecione os usuários.</span><span class="sxs-lookup"><span data-stu-id="e15dc-148">In the **&#x2713;** (check mark) column, select the users.</span></span> <span data-ttu-id="e15dc-149">Para selecionar todos os usuários, clique na (marca de seleção) &#x2713; na parte superior da tabela.</span><span class="sxs-lookup"><span data-stu-id="e15dc-149">To select all users, click the &#x2713; (check mark) at the top of the table.</span></span>
3. <span data-ttu-id="e15dc-150">Clique em **Editar configurações**, faça as alterações desejadas e, em seguida, clique em **Aplicar**.</span><span class="sxs-lookup"><span data-stu-id="e15dc-150">Click **Edit settings**, make the changes that you want, and then click **Apply**.</span></span>  

<span data-ttu-id="e15dc-151">Ou, você também pode fazer o seguinte:</span><span class="sxs-lookup"><span data-stu-id="e15dc-151">Or, you can also do the following:</span></span>

1. <span data-ttu-id="e15dc-152">Na navegação à esquerda do centro de administração do Microsoft Teams, vá para políticas de emergência de **voz**  >  **Emergency policies**e clique na guia **políticas de chamadas** .</span><span class="sxs-lookup"><span data-stu-id="e15dc-152">In the left navigation of the Microsoft Teams admin center, go to **Voice** > **Emergency policies**, and then click the **Calling policies** tab.</span></span>
2. <span data-ttu-id="e15dc-153">Escolha a política clicando à esquerda do nome da política.</span><span class="sxs-lookup"><span data-stu-id="e15dc-153">Select the policy by clicking to the left of the policy name.</span></span>
3. <span data-ttu-id="e15dc-154">Escolha **Gerenciar usuários**.</span><span class="sxs-lookup"><span data-stu-id="e15dc-154">Select **Manage users**.</span></span>
4. <span data-ttu-id="e15dc-155">No painel **Gerenciar usuários**, procure o usuário pelo nome de exibição ou pelo nome de usuário, escolha o nome e marque **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="e15dc-155">In the **Manage users** pane, search for the user by display name or by user name, select the name, and then select **Add**.</span></span> <span data-ttu-id="e15dc-156">Repita esta etapa para cada usuário que você deseja adicionar.</span><span class="sxs-lookup"><span data-stu-id="e15dc-156">Repeat this step for each user that you want to add.</span></span>
5. <span data-ttu-id="e15dc-157">Quando tiver terminado de adicionar usuários, clique em **salvar**.</span><span class="sxs-lookup"><span data-stu-id="e15dc-157">When you're finished adding users, click **Save**.</span></span>

### <a name="using-powershell"></a><span data-ttu-id="e15dc-158">Usando o PowerShell</span><span class="sxs-lookup"><span data-stu-id="e15dc-158">Using PowerShell</span></span>

#### <a name="assign-a-custom-emergency-calling-policy-to-a-user"></a><span data-ttu-id="e15dc-159">Atribuir uma política de chamadas de emergência personalizada a um usuário</span><span class="sxs-lookup"><span data-stu-id="e15dc-159">Assign a custom emergency calling policy to a user</span></span>

<span data-ttu-id="e15dc-160">Veja [Grant-CsTeamsEmergencyCallingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsemergencycallingpolicy).</span><span class="sxs-lookup"><span data-stu-id="e15dc-160">See [Grant-CsTeamsEmergencyCallingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsemergencycallingpolicy).</span></span>

#### <a name="assign-a-custom-emergency-calling-policy-to-users-in-a-group"></a><span data-ttu-id="e15dc-161">Atribuir uma política de chamadas de emergência personalizada a usuários em um grupo</span><span class="sxs-lookup"><span data-stu-id="e15dc-161">Assign a custom emergency calling policy to users in a group</span></span>

<span data-ttu-id="e15dc-162">Você pode querer atribuir uma política de chamadas de emergência personalizada a vários usuários que você já tenha identificado.</span><span class="sxs-lookup"><span data-stu-id="e15dc-162">You may want to assign a custom emergency calling policy to multiple users that you've already identified.</span></span> <span data-ttu-id="e15dc-163">Por exemplo, você pode querer atribuir uma política a todos os usuários de um grupo de segurança.</span><span class="sxs-lookup"><span data-stu-id="e15dc-163">For example, you may want to assign a policy to all users in a security group.</span></span> <span data-ttu-id="e15dc-164">Você pode fazer isso conectando-se ao módulo do PowerShell do Azure Active Directory e ao módulo do PowerShell do Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="e15dc-164">You can do this by connecting to the Azure Active Directory PowerShell for Graph module and the Skype for Business PowerShell module.</span></span>

<span data-ttu-id="e15dc-165">Neste exemplo, atribuímos uma política chamada política de chamadas de emergência de operações a todos os usuários no grupo de operações da contoso.</span><span class="sxs-lookup"><span data-stu-id="e15dc-165">In this example, we assign a policy called Operations Emergency Calling Policy to all users in the Contoso Operations group.</span></span>  

> [!NOTE]
> <span data-ttu-id="e15dc-166">Verifique se você se conectou primeiro ao módulo do PowerShell do Azure Active Directory e do módulo do PowerShell do Skype for Business seguindo as etapas em [conectar a todos os serviços do Microsoft 365 ou do Office 365 em uma única janela do Windows PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-all-office-365-services-in-a-single-windows-powershell-window).</span><span class="sxs-lookup"><span data-stu-id="e15dc-166">Make sure you first connect to the Azure Active Directory PowerShell for Graph module and Skype for Business PowerShell module by following the steps in [Connect to all Microsoft 365 or Office 365 services in a single Windows PowerShell window](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-all-office-365-services-in-a-single-windows-powershell-window).</span></span>

<span data-ttu-id="e15dc-167">Obtenha o GroupObjectId do grupo específico.</span><span class="sxs-lookup"><span data-stu-id="e15dc-167">Get the GroupObjectId of the particular group.</span></span>
```powershell
$group = Get-AzureADGroup -SearchString "Contoso Operations"
```
<span data-ttu-id="e15dc-168">Obter os membros do grupo especificado.</span><span class="sxs-lookup"><span data-stu-id="e15dc-168">Get the members of the specified group.</span></span>
```powershell
$members = Get-AzureADGroupMember -ObjectId $group.ObjectId -All $true | Where-Object {$_.ObjectType -eq "User"}
```
<span data-ttu-id="e15dc-169">Atribua todos os usuários do grupo a uma política específica do teams.</span><span class="sxs-lookup"><span data-stu-id="e15dc-169">Assign all users in the group to a particular teams policy.</span></span> <span data-ttu-id="e15dc-170">Neste exemplo, a política de roteamento de chamadas de emergência de emergência.</span><span class="sxs-lookup"><span data-stu-id="e15dc-170">In this example, it's Operations Emergency Call Routing Policy.</span></span>
```powershell
$members | ForEach-Object {Grant-CsTeamsEmergencyCallingPolicy -PolicyName "Operations Emergency Calling Policy" -Identity $_.UserPrincipalName}
``` 
<span data-ttu-id="e15dc-171">Dependendo do número de membros do grupo, esse comando pode levar alguns minutos para ser executado.</span><span class="sxs-lookup"><span data-stu-id="e15dc-171">Depending on the number of members in the group, this command may take several minutes to execute.</span></span>

## <a name="assign-a-custom-emergency-calling-policy-to-a-network-site"></a><span data-ttu-id="e15dc-172">Atribuir uma política de chamadas de emergência personalizada a um site de rede</span><span class="sxs-lookup"><span data-stu-id="e15dc-172">Assign a custom emergency calling policy to a network site</span></span>

<span data-ttu-id="e15dc-173">Use o cmdlet [set-CsTenantNetworkSite](https://docs.microsoft.com/powershell/module/skype/set-cstenantnetworksite) para atribuir uma política de chamadas de emergência a um site de rede.</span><span class="sxs-lookup"><span data-stu-id="e15dc-173">Use the [Set-CsTenantNetworkSite](https://docs.microsoft.com/powershell/module/skype/set-cstenantnetworksite) cmdlet to assign an emergency calling policy to a network site.</span></span>

<span data-ttu-id="e15dc-174">O exemplo a seguir mostra como atribuir uma política chamada política de chamada de emergência da Contoso 1 ao site do site1.</span><span class="sxs-lookup"><span data-stu-id="e15dc-174">The following example shows how to assign a policy called Contoso Emergency Calling Policy 1 to the Site1 site.</span></span>

```powershell
Set-CsTenantNetworkSite -identity "site1" -EmergencyCallingPolicy "Contoso Emergency Calling Policy 1"
```

## <a name="related-topics"></a><span data-ttu-id="e15dc-175">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="e15dc-175">Related topics</span></span>

- [<span data-ttu-id="e15dc-176">Gerenciar políticas de roteamento de chamadas de emergência no Teams</span><span class="sxs-lookup"><span data-stu-id="e15dc-176">Manage emergency call routing policies in Teams</span></span>](manage-emergency-call-routing-policies.md)
- [<span data-ttu-id="e15dc-177">Visão Geral do PowerShell do Teams</span><span class="sxs-lookup"><span data-stu-id="e15dc-177">Teams PowerShell overview</span></span>](teams-powershell-overview.md)
- [<span data-ttu-id="e15dc-178">Atribuir políticas a seus usuários no Teams</span><span class="sxs-lookup"><span data-stu-id="e15dc-178">Assign policies to your users in Teams</span></span>](assign-policies.md)
