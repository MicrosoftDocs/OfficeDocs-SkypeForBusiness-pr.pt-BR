---
title: Gerenciar políticas de chamadas de emergência no Microsoft Teams
author: cichur
ms.author: v-cichur
manager: serdars
ms.reviewer: jastark, roykuntz
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-voice
f1.keywords:
- CSH
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: Saiba como usar e gerenciar políticas de chamadas de emergência no Microsoft Teams para definir o que acontece quando um usuário do teams na sua organização faz uma chamada de emergência.
ms.custom:
- seo-marvel-apr2020
- ms.teamsadmincenter.voice.emergencycallingpolicies.overview
ms.openlocfilehash: e58f428fbaa25b03534ce9f168ecf347b183eda3
ms.sourcegitcommit: d6e97621b1bfe9c3fbd8bc41b30a94bafd17b28f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/25/2021
ms.locfileid: "49973135"
---
# <a name="manage-emergency-calling-policies-in-microsoft-teams"></a><span data-ttu-id="b317a-103">Gerenciar políticas de chamadas de emergência no Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="b317a-103">Manage emergency calling policies in Microsoft Teams</span></span>

<span data-ttu-id="b317a-104">Se a sua organização usar [planos de chamadas](set-up-calling-plans.md) ou [Roteamento direto do sistema telefônico](direct-routing-landing-page.md)implantado, você poderá usar políticas de chamadas de emergência no Microsoft Teams para definir o que acontece quando um usuário do teams na sua organização faz uma chamada de emergência.</span><span class="sxs-lookup"><span data-stu-id="b317a-104">If your organization uses [Calling Plans](set-up-calling-plans.md) or deployed [Phone System Direct Routing](direct-routing-landing-page.md), you can use emergency calling policies in Microsoft Teams to define what happens when a Teams user in your organization makes an emergency call.</span></span> <span data-ttu-id="b317a-105">Você pode definir quem deseja notificar e como eles são notificados quando um usuário ao qual a política é atribuída faz chamadas de serviços de emergência.</span><span class="sxs-lookup"><span data-stu-id="b317a-105">You can set who to notify and how they are notified when a user who is assigned the policy calls emergency services.</span></span> <span data-ttu-id="b317a-106">Por exemplo, você pode definir as configurações de política para notificar automaticamente a equipe de segurança da sua organização e fazer com que elas escutem em chamadas de emergência.</span><span class="sxs-lookup"><span data-stu-id="b317a-106">For example, you can configure policy settings to automatically notify your organization's security desk and have them listen in emergency calls.</span></span>  

<span data-ttu-id="b317a-107">Para gerenciar as políticas de chamadas de emergência ,  >  acesse **as políticas de emergência** de voz no centro de administração do Microsoft Teams ou usando o Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="b317a-107">You manage emergency calling policies by going to **Voice** > **Emergency policies** in the Microsoft Teams admin center or by using Windows PowerShell.</span></span> <span data-ttu-id="b317a-108">As políticas podem ser atribuídas a usuários e [sites de rede](cloud-voice-network-settings.md).</span><span class="sxs-lookup"><span data-stu-id="b317a-108">The policies can be assigned to users and [network sites](cloud-voice-network-settings.md).</span></span>

<span data-ttu-id="b317a-109">Para os usuários, você pode usar a política global (padrão para toda a organização) ou criar e atribuir políticas personalizadas.</span><span class="sxs-lookup"><span data-stu-id="b317a-109">For users, you can use the global (Org-wide default) policy or create and assign custom policies.</span></span> <span data-ttu-id="b317a-110">Os usuários receberão automaticamente a política global, a menos que você crie e atribua uma política personalizada.</span><span class="sxs-lookup"><span data-stu-id="b317a-110">Users will automatically get the global policy unless you create and assign a custom policy.</span></span> <span data-ttu-id="b317a-111">Lembre-se de que você pode editar as configurações na política global, mas não pode renomeá-la ou excluí-la.</span><span class="sxs-lookup"><span data-stu-id="b317a-111">Keep in mind that you can edit the settings in the global policy but you can't rename or delete it.</span></span> <span data-ttu-id="b317a-112">Para sites de rede, você cria e atribui políticas personalizadas.</span><span class="sxs-lookup"><span data-stu-id="b317a-112">For network sites, you create and assign custom policies.</span></span>

<span data-ttu-id="b317a-113">Se você tiver atribuído uma política de chamadas de emergência a um site de rede e a um usuário e se esse usuário estiver nesse site de rede, a política que é atribuída ao site da rede substituirá a política atribuída ao usuário.</span><span class="sxs-lookup"><span data-stu-id="b317a-113">If you assigned an emergency calling policy to a network site and to a user and if that user is at that network site, the policy that's assigned to the network site overrides the policy that's assigned to the user.</span></span>

## <a name="create-a-custom-emergency-calling-policy"></a><span data-ttu-id="b317a-114">Criar uma política de chamadas de emergência personalizada</span><span class="sxs-lookup"><span data-stu-id="b317a-114">Create a custom emergency calling policy</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="b317a-115">Usando o centro de administração do Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="b317a-115">Using the Microsoft Teams admin center</span></span>

1. <span data-ttu-id="b317a-116">Na navegação à esquerda do centro de administração do Microsoft Teams, vá para políticas de emergência de **voz**  >  e clique na guia **políticas de chamadas** .</span><span class="sxs-lookup"><span data-stu-id="b317a-116">In the left navigation of the Microsoft Teams admin center, go to **Voice** > **Emergency policies**, and then click the **Calling policies** tab.</span></span>
2. <span data-ttu-id="b317a-117">Clique em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="b317a-117">Click **Add**.</span></span>
3. <span data-ttu-id="b317a-118">Insira um nome e uma descrição para a política.</span><span class="sxs-lookup"><span data-stu-id="b317a-118">Enter a name and description for the policy.</span></span>
4. <span data-ttu-id="b317a-119">Defina como você deseja notificar as pessoas em sua organização, geralmente a segurança, quando uma chamada de emergência é feita.</span><span class="sxs-lookup"><span data-stu-id="b317a-119">Set how you want to notify people in your organization, typically the security desk, when an emergency call is made.</span></span> <span data-ttu-id="b317a-120">Para fazer isso, em **modo de notificação**, selecione uma das seguintes opções:</span><span class="sxs-lookup"><span data-stu-id="b317a-120">To do this, under **Notification mode**, select one of the following:</span></span>
    - <span data-ttu-id="b317a-121">**Enviar somente notificação**: uma mensagem de chat do teams é enviada aos usuários e grupos que você especificar.</span><span class="sxs-lookup"><span data-stu-id="b317a-121">**Send notification only**: A Teams chat message is sent to the users and groups that you specify.</span></span>
    - <span data-ttu-id="b317a-122">**Em conferência com mudo ativado e não é possível desativar o mudo**: uma mensagem de chat do teams é enviada para os usuários e grupos que você especifica e podem ouvir (mas não participar) da conversa entre o chamador e o operador PSAP.</span><span class="sxs-lookup"><span data-stu-id="b317a-122">**Conferenced in muted and unable to unmute**: A Teams chat message is sent to the users and groups that you specify and they can listen (but not participate) in the conversation between the caller and the PSAP operator.</span></span>
    - <span data-ttu-id="b317a-123">**Em conferência desativada, mas** pode desativar o mudo: uma mensagem de chat do teams é enviada para os usuários e grupos que você especifica e pode desativar mudo para ouvir e participar da conversa entre o chamador e o operador PSAP.</span><span class="sxs-lookup"><span data-stu-id="b317a-123">**Conferenced in muted but are able to unmute**: A Teams chat message is sent to the users and groups that you specify and they can unmute to listen and participate in the conversation between the caller and the PSAP operator.</span></span>
5.  <span data-ttu-id="b317a-124">Se você selecionou um dos modos de notificação **em mudo** , na caixa **números para discar para notificações de chamadas de emergência** , você pode digitar um número de telefone PSTN de um usuário ou grupo para chamar e ingressar na chamada de emergência.</span><span class="sxs-lookup"><span data-stu-id="b317a-124">If you selected either of the **Conference in muted** notification modes, in the **Numbers to dial for emergency calls notifications** box, you can enter a PSTN phone number of a user or group to call and join the emergency call.</span></span> <span data-ttu-id="b317a-125">Por exemplo, digite o número da central de segurança da sua organização, que receberá uma chamada quando uma chamada de emergência for feita e poderá ouvi-la na chamada.</span><span class="sxs-lookup"><span data-stu-id="b317a-125">For example, enter the number of your organization's security desk, who will receive a call when an emergency call is made and can then listen in on the call.</span></span> <span data-ttu-id="b317a-126">Não é possível desativar o mudo do telefone PSTN mesmo quando o modo está definido como **em conferência em mudo, mas é possível desativar o mudo**.</span><span class="sxs-lookup"><span data-stu-id="b317a-126">The PSTN phone cannot be unmuted even when the mode is set to **Conferenced in muted but are able to unmute**.</span></span>
6. <span data-ttu-id="b317a-127">Procure e selecione um ou mais usuários ou grupos, como a mesa de segurança da sua organização, para notificar quando uma chamada de emergência é feita.</span><span class="sxs-lookup"><span data-stu-id="b317a-127">Search for and select one or more users or groups, such as your organization's security desk, to notify when an emergency call is made.</span></span>  <span data-ttu-id="b317a-128">A notificação pode ser enviada para endereços de email de usuários, grupos de distribuição e grupos de segurança.</span><span class="sxs-lookup"><span data-stu-id="b317a-128">The notification can be sent to email addresses of users, distribution groups, and security groups.</span></span> <span data-ttu-id="b317a-129">Um máximo de 50 usuários pode ser notificado.</span><span class="sxs-lookup"><span data-stu-id="b317a-129">A maximum of 50 users can be notified.</span></span>
7. <span data-ttu-id="b317a-130">Clique em **Aplicar**.</span><span class="sxs-lookup"><span data-stu-id="b317a-130">Click **Apply**.</span></span>

### <a name="using-powershell"></a><span data-ttu-id="b317a-131">Usando o Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="b317a-131">Using PowerShell</span></span>

<span data-ttu-id="b317a-132">Veja [New-CsTeamsEmergencyCallingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csteamsemergencycallingpolicy).</span><span class="sxs-lookup"><span data-stu-id="b317a-132">See [New-CsTeamsEmergencyCallingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csteamsemergencycallingpolicy).</span></span>

## <a name="edit-an-emergency-calling-policy"></a><span data-ttu-id="b317a-133">Editar uma política de chamadas de emergência</span><span class="sxs-lookup"><span data-stu-id="b317a-133">Edit an emergency calling policy</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="b317a-134">Usando o centro de administração do Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="b317a-134">Using the Microsoft Teams admin center</span></span>

<span data-ttu-id="b317a-135">Você pode editar a política global ou qualquer política personalizada criada.</span><span class="sxs-lookup"><span data-stu-id="b317a-135">You can edit the global policy or any custom policies that you create.</span></span>

1. <span data-ttu-id="b317a-136">Na navegação à esquerda do centro de administração do Microsoft Teams, vá para políticas de emergência de **voz**  >  e clique na guia **políticas de chamadas** .</span><span class="sxs-lookup"><span data-stu-id="b317a-136">In the left navigation of the Microsoft Teams admin center, go to **Voice** > **Emergency policies**, and then click the **Calling policies** tab.</span></span>
2. <span data-ttu-id="b317a-137">Selecione a política clicando à esquerda do nome da política e, em seguida, clique em **Editar**.</span><span class="sxs-lookup"><span data-stu-id="b317a-137">Select the policy by clicking to the left of the policy name, and then click **Edit**.</span></span>
3. <span data-ttu-id="b317a-138">Faça as alterações desejadas e clique em **aplicar**.</span><span class="sxs-lookup"><span data-stu-id="b317a-138">Make the changes that you want, and then click **Apply**.</span></span>

### <a name="using-powershell"></a><span data-ttu-id="b317a-139">Usando o Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="b317a-139">Using PowerShell</span></span>

<span data-ttu-id="b317a-140">Consulte [set-CsTeamsEmergencyCallingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsemergencycallingpolicy).</span><span class="sxs-lookup"><span data-stu-id="b317a-140">See [Set-CsTeamsEmergencyCallingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsemergencycallingpolicy).</span></span>

## <a name="assign-a-custom-emergency-calling-policy-to-users"></a><span data-ttu-id="b317a-141">Atribuir uma política de chamadas de emergência personalizada aos usuários</span><span class="sxs-lookup"><span data-stu-id="b317a-141">Assign a custom emergency calling policy to users</span></span>

[!INCLUDE [assign-policy](includes/assign-policy.md)]

<span data-ttu-id="b317a-142">Consulte também [Grant-CsTeamsEmergencyCallingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsemergencycallingpolicy).</span><span class="sxs-lookup"><span data-stu-id="b317a-142">See also [Grant-CsTeamsEmergencyCallingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsemergencycallingpolicy).</span></span>

## <a name="assign-a-custom-emergency-calling-policy-to-a-network-site"></a><span data-ttu-id="b317a-143">Atribuir uma política de chamadas de emergência personalizada a um site de rede</span><span class="sxs-lookup"><span data-stu-id="b317a-143">Assign a custom emergency calling policy to a network site</span></span>

<span data-ttu-id="b317a-144">Use o cmdlet [set-CsTenantNetworkSite](https://docs.microsoft.com/powershell/module/skype/set-cstenantnetworksite) para atribuir uma política de chamadas de emergência a um site de rede.</span><span class="sxs-lookup"><span data-stu-id="b317a-144">Use the [Set-CsTenantNetworkSite](https://docs.microsoft.com/powershell/module/skype/set-cstenantnetworksite) cmdlet to assign an emergency calling policy to a network site.</span></span>

<span data-ttu-id="b317a-145">O exemplo a seguir mostra como atribuir uma política chamada política de chamada de emergência da Contoso 1 ao site do site1.</span><span class="sxs-lookup"><span data-stu-id="b317a-145">The following example shows how to assign a policy called Contoso Emergency Calling Policy 1 to the Site1 site.</span></span>

```powershell
Set-CsTenantNetworkSite -identity "site1" -EmergencyCallingPolicy "Contoso Emergency Calling Policy 1"
```

## <a name="related-topics"></a><span data-ttu-id="b317a-146">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="b317a-146">Related topics</span></span>

[<span data-ttu-id="b317a-147">Gerenciar políticas de roteamento de chamadas de emergência no Teams</span><span class="sxs-lookup"><span data-stu-id="b317a-147">Manage emergency call routing policies in Teams</span></span>](manage-emergency-call-routing-policies.md)

[<span data-ttu-id="b317a-148">Visão Geral do PowerShell do Teams</span><span class="sxs-lookup"><span data-stu-id="b317a-148">Teams PowerShell overview</span></span>](teams-powershell-overview.md)

[<span data-ttu-id="b317a-149">Atribuir políticas aos usuários no Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="b317a-149">Assign policies to your users in Teams</span></span>](assign-policies.md)
