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
ms.openlocfilehash: 12d2e114a53c47e6c938c6c2cb4bf3cb83c81180
ms.sourcegitcommit: 60b859dcb8ac727a38bf28cdb63ff762e7338af8
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/30/2020
ms.locfileid: "44938430"
---
# <a name="manage-emergency-calling-policies-in-microsoft-teams"></a><span data-ttu-id="4126d-103">Gerenciar políticas de chamadas de emergência no Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="4126d-103">Manage emergency calling policies in Microsoft Teams</span></span>

<span data-ttu-id="4126d-104">Se a sua organização usar [planos de chamadas](set-up-calling-plans.md) ou [Roteamento direto do sistema telefônico](direct-routing-landing-page.md)implantado, você poderá usar políticas de chamadas de emergência no Microsoft Teams para definir o que acontece quando um usuário do teams na sua organização faz uma chamada de emergência.</span><span class="sxs-lookup"><span data-stu-id="4126d-104">If your organization uses [Calling Plans](set-up-calling-plans.md) or deployed [Phone System Direct Routing](direct-routing-landing-page.md), you can use emergency calling policies in Microsoft Teams to define what happens when a Teams user in your organization makes an emergency call.</span></span> <span data-ttu-id="4126d-105">Você pode definir quem deseja notificar e como eles são notificados quando um usuário ao qual a política é atribuída faz chamadas de serviços de emergência.</span><span class="sxs-lookup"><span data-stu-id="4126d-105">You can set who to notify and how they are notified when a user who is assigned the policy calls emergency services.</span></span> <span data-ttu-id="4126d-106">Por exemplo, você pode definir as configurações de política para notificar automaticamente a equipe de segurança da sua organização e fazer com que elas escutem em chamadas de emergência.</span><span class="sxs-lookup"><span data-stu-id="4126d-106">For example, you can configure policy settings to automatically notify your organization's security desk and have them listen in emergency calls.</span></span>  

<span data-ttu-id="4126d-107">Para gerenciar as políticas de chamadas de emergência **Voice**,  >  acesse**as políticas de emergência** de voz no centro de administração do Microsoft Teams ou usando o Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="4126d-107">You manage emergency calling policies by going to **Voice** > **Emergency policies** in the Microsoft Teams admin center or by using Windows PowerShell.</span></span> <span data-ttu-id="4126d-108">As políticas podem ser atribuídas a usuários e [sites de rede](cloud-voice-network-settings.md).</span><span class="sxs-lookup"><span data-stu-id="4126d-108">The policies can be assigned to users and [network sites](cloud-voice-network-settings.md).</span></span>

<span data-ttu-id="4126d-109">Para os usuários, você pode usar a política global (padrão para toda a organização) ou criar e atribuir políticas personalizadas.</span><span class="sxs-lookup"><span data-stu-id="4126d-109">For users, you can use the global (Org-wide default) policy or create and assign custom policies.</span></span> <span data-ttu-id="4126d-110">Os usuários receberão automaticamente a política global, a menos que você crie e atribua uma política personalizada.</span><span class="sxs-lookup"><span data-stu-id="4126d-110">Users will automatically get the global policy unless you create and assign a custom policy.</span></span> <span data-ttu-id="4126d-111">Lembre-se de que você pode editar as configurações na política global, mas não pode renomeá-la ou excluí-la.</span><span class="sxs-lookup"><span data-stu-id="4126d-111">Keep in mind that you can edit the settings in the global policy but you can't rename or delete it.</span></span> <span data-ttu-id="4126d-112">Para sites de rede, você cria e atribui políticas personalizadas.</span><span class="sxs-lookup"><span data-stu-id="4126d-112">For network sites, you create and assign custom policies.</span></span>

<span data-ttu-id="4126d-113">Se você tiver atribuído uma política de chamadas de emergência a um site de rede e a um usuário e se esse usuário estiver nesse site de rede, a política que é atribuída ao site da rede substituirá a política atribuída ao usuário.</span><span class="sxs-lookup"><span data-stu-id="4126d-113">If you assigned an emergency calling policy to a network site and to a user and if that user is at that network site, the policy that's assigned to the network site overrides the policy that's assigned to the user.</span></span>

## <a name="create-a-custom-emergency-calling-policy"></a><span data-ttu-id="4126d-114">Criar uma política de chamadas de emergência personalizada</span><span class="sxs-lookup"><span data-stu-id="4126d-114">Create a custom emergency calling policy</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="4126d-115">Usando o centro de administração do Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="4126d-115">Using the Microsoft Teams admin center</span></span>

1. <span data-ttu-id="4126d-116">Na navegação à esquerda do centro de administração do Microsoft Teams, vá para políticas de emergência de **voz**  >  **Emergency policies**e clique na guia **políticas de chamadas** .</span><span class="sxs-lookup"><span data-stu-id="4126d-116">In the left navigation of the Microsoft Teams admin center, go to **Voice** > **Emergency policies**, and then click the **Calling policies** tab.</span></span>
2. <span data-ttu-id="4126d-117">Clique em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="4126d-117">Click **Add**.</span></span>
3. <span data-ttu-id="4126d-118">Insira um nome e uma descrição para a política.</span><span class="sxs-lookup"><span data-stu-id="4126d-118">Enter a name and description for the policy.</span></span>
4. <span data-ttu-id="4126d-119">Defina como você deseja notificar as pessoas em sua organização, geralmente a segurança, quando uma chamada de emergência é feita.</span><span class="sxs-lookup"><span data-stu-id="4126d-119">Set how you want to notify people in your organization, typically the security desk, when an emergency call is made.</span></span> <span data-ttu-id="4126d-120">Para fazer isso, em **modo de notificação**, selecione uma das seguintes opções:</span><span class="sxs-lookup"><span data-stu-id="4126d-120">To do this, under **Notification mode**, select one of the following:</span></span>
    - <span data-ttu-id="4126d-121">**Enviar somente notificação**: uma mensagem de chat do teams é enviada aos usuários e grupos que você especificar.</span><span class="sxs-lookup"><span data-stu-id="4126d-121">**Send notification only**: A Teams chat message is sent to the users and groups that you specify.</span></span>
    - <span data-ttu-id="4126d-122">**Em conferência, mas com mudo ativado**: uma mensagem de chat do teams é enviada aos usuários e grupos que você especifica e podem ouvir (mas não participar) da conversa entre o chamador e o operador PSAP.</span><span class="sxs-lookup"><span data-stu-id="4126d-122">**Conferenced in but are muted**: A Teams chat message is sent to the users and groups that you specify and they can listen (but not participate) in the conversation between the caller and the PSAP operator.</span></span>
    - <span data-ttu-id="4126d-123">**Em conferência e com mudo ativado (em** **breve)**: uma mensagem de chat do teams é enviada para os usuários e grupos que você especifica e pode desativar o mudo para ouvir e participar da conversa entre o chamador e o operador PSAP.</span><span class="sxs-lookup"><span data-stu-id="4126d-123">**Conferenced in and are unmuted** **(coming soon)**: A Teams chat message is sent to the users and groups that you specify and they can unmute to listen and participate in the conversation between the caller and the PSAP operator.</span></span>
5.  <span data-ttu-id="4126d-124">Se você tiver selecionado o modo de notificação **em conferência mas estiver mudo** , na caixa **números para discar para notificações de chamadas de emergência** , você pode digitar um número de telefone PSTN de um usuário ou grupo para chamar e ingressar na chamada de emergência.</span><span class="sxs-lookup"><span data-stu-id="4126d-124">If you selected the **Conferenced in but are muted** notification mode, in the **Numbers to dial for emergency calls notifications** box, you can enter a PSTN phone number of a user or group to call and join the emergency call.</span></span> <span data-ttu-id="4126d-125">Por exemplo, digite o número da central de segurança da sua organização, que receberá uma chamada quando uma chamada de emergência for feita e poderá ouvi-la na chamada.</span><span class="sxs-lookup"><span data-stu-id="4126d-125">For example, enter the number of your organization's security desk, who will receive a call when an emergency call is made and can then listen in on the call.</span></span>
6. <span data-ttu-id="4126d-126">Procure e selecione um ou mais usuários ou grupos, como a mesa de segurança da sua organização, para notificar quando uma chamada de emergência é feita.</span><span class="sxs-lookup"><span data-stu-id="4126d-126">Search for and select one or more users or groups, such as your organization's security desk, to notify when an emergency call is made.</span></span>  <span data-ttu-id="4126d-127">A notificação pode ser enviada para endereços de email de usuários, grupos de distribuição e grupos de segurança.</span><span class="sxs-lookup"><span data-stu-id="4126d-127">The notification can be sent to email addresses of users, distribution groups, and security groups.</span></span> <span data-ttu-id="4126d-128">Um máximo de 50 usuários pode ser notificado.</span><span class="sxs-lookup"><span data-stu-id="4126d-128">A maximum of 50 users can be notified.</span></span>
7. <span data-ttu-id="4126d-129">Clique em **Aplicar**.</span><span class="sxs-lookup"><span data-stu-id="4126d-129">Click **Apply**.</span></span>

### <a name="using-powershell"></a><span data-ttu-id="4126d-130">Usando o PowerShell</span><span class="sxs-lookup"><span data-stu-id="4126d-130">Using PowerShell</span></span>

<span data-ttu-id="4126d-131">Veja [New-CsTeamsEmergencyCallingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csteamsemergencycallingpolicy).</span><span class="sxs-lookup"><span data-stu-id="4126d-131">See [New-CsTeamsEmergencyCallingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csteamsemergencycallingpolicy).</span></span>

## <a name="edit-an-emergency-calling-policy"></a><span data-ttu-id="4126d-132">Editar uma política de chamadas de emergência</span><span class="sxs-lookup"><span data-stu-id="4126d-132">Edit an emergency calling policy</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="4126d-133">Usando o centro de administração do Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="4126d-133">Using the Microsoft Teams admin center</span></span>

<span data-ttu-id="4126d-134">Você pode editar a política global ou qualquer política personalizada criada.</span><span class="sxs-lookup"><span data-stu-id="4126d-134">You can edit the global policy or any custom policies that you create.</span></span>

1. <span data-ttu-id="4126d-135">Na navegação à esquerda do centro de administração do Microsoft Teams, vá para políticas de emergência de **voz**  >  **Emergency policies**e clique na guia **políticas de chamadas** .</span><span class="sxs-lookup"><span data-stu-id="4126d-135">In the left navigation of the Microsoft Teams admin center, go to **Voice** > **Emergency policies**, and then click the **Calling policies** tab.</span></span>
2. <span data-ttu-id="4126d-136">Selecione a política clicando à esquerda do nome da política e, em seguida, clique em **Editar**.</span><span class="sxs-lookup"><span data-stu-id="4126d-136">Select the policy by clicking to the left of the policy name, and then click **Edit**.</span></span>
3. <span data-ttu-id="4126d-137">Faça as alterações desejadas e clique em **aplicar**.</span><span class="sxs-lookup"><span data-stu-id="4126d-137">Make the changes that you want, and then click **Apply**.</span></span>

### <a name="using-powershell"></a><span data-ttu-id="4126d-138">Usando o PowerShell</span><span class="sxs-lookup"><span data-stu-id="4126d-138">Using PowerShell</span></span>

<span data-ttu-id="4126d-139">Consulte [set-CsTeamsEmergencyCallingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsemergencycallingpolicy).</span><span class="sxs-lookup"><span data-stu-id="4126d-139">See [Set-CsTeamsEmergencyCallingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsemergencycallingpolicy).</span></span>

## <a name="assign-a-custom-emergency-calling-policy-to-users"></a><span data-ttu-id="4126d-140">Atribuir uma política de chamadas de emergência personalizada aos usuários</span><span class="sxs-lookup"><span data-stu-id="4126d-140">Assign a custom emergency calling policy to users</span></span>

[!INCLUDE [assign-policy](includes/assign-policy.md)]

<span data-ttu-id="4126d-141">Consulte também [Grant-CsTeamsEmergencyCallingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsemergencycallingpolicy).</span><span class="sxs-lookup"><span data-stu-id="4126d-141">See also [Grant-CsTeamsEmergencyCallingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsemergencycallingpolicy).</span></span>

## <a name="assign-a-custom-emergency-calling-policy-to-a-network-site"></a><span data-ttu-id="4126d-142">Atribuir uma política de chamadas de emergência personalizada a um site de rede</span><span class="sxs-lookup"><span data-stu-id="4126d-142">Assign a custom emergency calling policy to a network site</span></span>

<span data-ttu-id="4126d-143">Use o cmdlet [set-CsTenantNetworkSite](https://docs.microsoft.com/powershell/module/skype/set-cstenantnetworksite) para atribuir uma política de chamadas de emergência a um site de rede.</span><span class="sxs-lookup"><span data-stu-id="4126d-143">Use the [Set-CsTenantNetworkSite](https://docs.microsoft.com/powershell/module/skype/set-cstenantnetworksite) cmdlet to assign an emergency calling policy to a network site.</span></span>

<span data-ttu-id="4126d-144">O exemplo a seguir mostra como atribuir uma política chamada política de chamada de emergência da Contoso 1 ao site do site1.</span><span class="sxs-lookup"><span data-stu-id="4126d-144">The following example shows how to assign a policy called Contoso Emergency Calling Policy 1 to the Site1 site.</span></span>

```powershell
Set-CsTenantNetworkSite -identity "site1" -EmergencyCallingPolicy "Contoso Emergency Calling Policy 1"
```

## <a name="related-topics"></a><span data-ttu-id="4126d-145">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="4126d-145">Related topics</span></span>

[<span data-ttu-id="4126d-146">Gerenciar políticas de roteamento de chamadas de emergência no Teams</span><span class="sxs-lookup"><span data-stu-id="4126d-146">Manage emergency call routing policies in Teams</span></span>](manage-emergency-call-routing-policies.md)

[<span data-ttu-id="4126d-147">Visão Geral do PowerShell do Teams</span><span class="sxs-lookup"><span data-stu-id="4126d-147">Teams PowerShell overview</span></span>](teams-powershell-overview.md)

[<span data-ttu-id="4126d-148">Atribuir políticas a seus usuários no Teams</span><span class="sxs-lookup"><span data-stu-id="4126d-148">Assign policies to your users in Teams</span></span>](assign-policies.md)
