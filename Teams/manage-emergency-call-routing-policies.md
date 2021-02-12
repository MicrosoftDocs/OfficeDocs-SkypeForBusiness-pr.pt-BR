---
title: Gerenciar políticas de roteamento de chamada
author: cichur
ms.author: v-cichur
manager: serdars
ms.reviewer: jastark, roykuntz
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
f1.keywords:
- NOCSH
- ms.teamsadmincenter.voice.emergencycallroutingpolicies.overview
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: Saiba como usar e gerenciar políticas de roteamento de chamadas de emergência no Microsoft Teams para configurar números de emergência e especificar como as chamadas de emergência são roteada.
ms.custom:
- seo-marvel-apr2020
- ms.teamsadmincenter.voice.emergencycallroutingpolicies.overview
ms.openlocfilehash: f2e7ce7ee2557745f3819efc84dada77b4a70635
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49804671"
---
# <a name="manage-emergency-call-routing-policies-in-microsoft-teams"></a><span data-ttu-id="72f7f-103">Gerenciar políticas de roteamento de chamadas de emergência no Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="72f7f-103">Manage emergency call routing policies in Microsoft Teams</span></span>

<span data-ttu-id="72f7f-104">Se você implantou o Roteamento Direto do Sistema telefônico em sua organização, pode usar políticas de roteamento de chamadas de emergência no Microsoft Teams para configurar números de emergência e especificar como as chamadas de emergência são roteadas. [](direct-routing-landing-page.md)</span><span class="sxs-lookup"><span data-stu-id="72f7f-104">If you've deployed [Phone System Direct Routing](direct-routing-landing-page.md) in your organization, you can use emergency call routing policies in Microsoft Teams to set up emergency numbers and specify how emergency calls are routed.</span></span> <span data-ttu-id="72f7f-105">Uma política de roteamento de chamadas de emergência determina se os serviços de emergência aprimorados estão habilitados para usuários que têm a política atribuída, os números usados para ligar para serviços de emergência (por exemplo, 911 nos Estados Unidos) e como as chamadas para serviços de emergência são roteadas.</span><span class="sxs-lookup"><span data-stu-id="72f7f-105">An emergency call routing policy determines whether enhanced emergency services is enabled for users who are assigned the policy, the numbers used to call emergency services (for example, 911 in the United States), and how calls to emergency services are routed.</span></span>

<span data-ttu-id="72f7f-106">Você gerencia políticas de roteamento de chamadas de emergência indo para **políticas** de Emergência de Voz no Centro de administração do  >   Microsoft Teams ou usando o Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="72f7f-106">You manage emergency call routing policies by going to **Voice** > **Emergency policies** in the Microsoft Teams admin center or by using Windows PowerShell.</span></span> <span data-ttu-id="72f7f-107">As políticas podem ser atribuídas a usuários e [sites de rede.](cloud-voice-network-settings.md)</span><span class="sxs-lookup"><span data-stu-id="72f7f-107">The policies can be assigned to users and [network sites](cloud-voice-network-settings.md).</span></span>

<span data-ttu-id="72f7f-108">Para os usuários, você pode usar a política global (padrão de toda a organização) ou criar e atribuir políticas personalizadas.</span><span class="sxs-lookup"><span data-stu-id="72f7f-108">For users, you can use the global (Org-wide default) policy or create and assign custom policies.</span></span> <span data-ttu-id="72f7f-109">Os usuários receberão automaticamente a política global, a menos que você crie e atribua uma política personalizada.</span><span class="sxs-lookup"><span data-stu-id="72f7f-109">Users will automatically get the global policy unless you create and assign a custom policy.</span></span> <span data-ttu-id="72f7f-110">Lembre-se de que você pode editar as configurações na política global, mas não pode renomeá-la ou excluí-la.</span><span class="sxs-lookup"><span data-stu-id="72f7f-110">Keep in mind that you can edit the settings in the global policy but you can't rename or delete it.</span></span> <span data-ttu-id="72f7f-111">Para sites de rede, você cria e atribui políticas personalizadas.</span><span class="sxs-lookup"><span data-stu-id="72f7f-111">For network sites, you create and assign custom policies.</span></span>

<span data-ttu-id="72f7f-112">Se você atribuiu uma política de roteamento de chamada de emergência a um site de rede e a um usuário e se esse usuário estiver nesse site de rede, a política atribuída ao site de rede substituirá a política atribuída ao usuário.</span><span class="sxs-lookup"><span data-stu-id="72f7f-112">If you assigned an emergency call routing policy to a network site and to a user and if that user is at that network site, the policy that's assigned to the network site overrides the policy that's assigned to the user.</span></span>

## <a name="create-a-custom-emergency-call-routing-policy"></a><span data-ttu-id="72f7f-113">Criar uma política de roteamento de chamadas de emergência personalizada</span><span class="sxs-lookup"><span data-stu-id="72f7f-113">Create a custom emergency call routing policy</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="72f7f-114">Usando o centro de administração do Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="72f7f-114">Using the Microsoft Teams admin center</span></span>

1. <span data-ttu-id="72f7f-115">Na navegação à esquerda do Centro de administração do Microsoft Teams, vá para políticas de Emergência de Voz e clique na  >  guia Políticas **de roteamento de** chamadas.</span><span class="sxs-lookup"><span data-stu-id="72f7f-115">In the left navigation of the Microsoft Teams admin center, go to **Voice** > **Emergency policies**, and then click the **Call routing policies** tab.</span></span>
2. <span data-ttu-id="72f7f-116">Clique em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="72f7f-116">Click **Add**.</span></span>
3. <span data-ttu-id="72f7f-117">Insira um nome e uma descrição para a política.</span><span class="sxs-lookup"><span data-stu-id="72f7f-117">Enter a name and description for the policy.</span></span>
4. <span data-ttu-id="72f7f-118">Para habilitar uma chamada de emergência dinâmica, ative **as chamada de emergência dinâmicas.**</span><span class="sxs-lookup"><span data-stu-id="72f7f-118">To enable dynamic emergency calling, turn on **Dynamic emergency calling**.</span></span> <span data-ttu-id="72f7f-119">Quando a chamada de emergência dinâmica está habilitada, o Teams recupera informações de localização e política do serviço e inclui essas informações como parte da chamada de emergência.</span><span class="sxs-lookup"><span data-stu-id="72f7f-119">When dynamic emergency calling is enabled, Teams retrieves policy and location information from the service and includes that information as part of the emergency call.</span></span>
5. <span data-ttu-id="72f7f-120">Defina um ou mais números de emergência.</span><span class="sxs-lookup"><span data-stu-id="72f7f-120">Define one or more emergency numbers.</span></span> <span data-ttu-id="72f7f-121">Para fazer isso, em **Números de emergência,** clique em **Adicionar** e faça o seguinte:</span><span class="sxs-lookup"><span data-stu-id="72f7f-121">To do this, under **Emergency numbers**, click **Add**, and then do the following:</span></span>
    1. <span data-ttu-id="72f7f-122">**Cadeia de discagem de emergência:** insira a cadeia de caracteres de discagem de emergência.</span><span class="sxs-lookup"><span data-stu-id="72f7f-122">**Emergency dial string**: Enter the emergency dial string.</span></span> <span data-ttu-id="72f7f-123">Essa cadeia de caracteres de discagem indica que uma chamada é uma chamada de emergência.</span><span class="sxs-lookup"><span data-stu-id="72f7f-123">This dial string indicates that a call is an emergency call.</span></span>
        > [!NOTE]
        > <span data-ttu-id="72f7f-124">Para Roteamento Direto, estamos nos afastando dos clientes do Teams que enviam chamadas de emergência com um "+" na frente da cadeia de discagem de emergência.</span><span class="sxs-lookup"><span data-stu-id="72f7f-124">For Direct Routing, we're transitioning away from Teams clients sending emergency calls with a "+" in front of the emergency dial string.</span></span> <span data-ttu-id="72f7f-125">Até que a transição seja concluída, o padrão de rota de voz para corresponder a uma cadeia de discagem de emergência deve garantir que uma combinação seja feita para cadeias de caracteres que têm e não têm um "+", como 911 e +911.</span><span class="sxs-lookup"><span data-stu-id="72f7f-125">Until the transition is completed, the voice route pattern to match an emergency dial string should ensure a match is made for strings that have and don't have a preceding "+", such as 911 and +911.</span></span> <span data-ttu-id="72f7f-126">Por exemplo, ^ \\ +?911 ou .\*.</span><span class="sxs-lookup"><span data-stu-id="72f7f-126">For example, ^\\+?911 or .\*.</span></span>
    2. <span data-ttu-id="72f7f-127">**Máscara de discagem de** emergência: para cada número de emergência, você pode especificar zero ou mais máscaras de discagem de emergência.</span><span class="sxs-lookup"><span data-stu-id="72f7f-127">**Emergency dial mask**: For each emergency number, you can specify zero or more emergency dial masks.</span></span> <span data-ttu-id="72f7f-128">Uma máscara de discagem é o número que você deseja traduzir para o valor da cadeia de discagem de emergência.</span><span class="sxs-lookup"><span data-stu-id="72f7f-128">A dial mask is the number that you want to translate into the value of the emergency dial string.</span></span> <span data-ttu-id="72f7f-129">Isso permite que números de emergência alternativos sejam discados e ainda que a chamada chegue aos serviços de emergência.</span><span class="sxs-lookup"><span data-stu-id="72f7f-129">This allows for alternate emergency numbers to be dialed and still have the call reach emergency services.</span></span> <br><span data-ttu-id="72f7f-130">Por exemplo, você adiciona 112 como a máscara de discagem de emergência, que é o número de serviço de emergência da maioria da Europa, e 911 como a cadeia de discagem de emergência.</span><span class="sxs-lookup"><span data-stu-id="72f7f-130">For example, you add 112 as the emergency dial mask, which is the emergency service number for most of Europe, and 911 as the emergency dial string.</span></span> <span data-ttu-id="72f7f-131">Um usuário do Teams da Europa que está visitando pode não saber que 911 é o número de emergência nos Estados Unidos e, quando eles discam para 112, a chamada é feita para 911.</span><span class="sxs-lookup"><span data-stu-id="72f7f-131">A Teams user from Europe who is visiting may not know that 911 is the emergency number in the United States, and when they dial 112, the call is made to 911.</span></span> <span data-ttu-id="72f7f-132">Para definir várias máscaras de discagem, separe cada valor por ponto e vírgula.</span><span class="sxs-lookup"><span data-stu-id="72f7f-132">To define multiple dial masks, separate each value by a semicolon.</span></span> <span data-ttu-id="72f7f-133">Por exemplo, 112;212.</span><span class="sxs-lookup"><span data-stu-id="72f7f-133">For example, 112;212.</span></span>
    3. <span data-ttu-id="72f7f-134">**Registro de uso PSTN:** selecione o registro de uso de PSTN (Rede Telefônica Pública Comutado).</span><span class="sxs-lookup"><span data-stu-id="72f7f-134">**PSTN usage record**: Select the Public Switched Telephone Network (PSTN) usage record.</span></span> <span data-ttu-id="72f7f-135">O registro de uso PSTN é usado para determinar qual rota é usada para encaminhar chamadas de emergência de usuários autorizados a usá-las.</span><span class="sxs-lookup"><span data-stu-id="72f7f-135">The PSTN usage record is used to determine which route is used to route emergency calls from users who are authorized to use them.</span></span> <span data-ttu-id="72f7f-136">A rota associada a esse uso deve apontar para um tronco sip dedicado a chamadas de emergência ou a um gateway ELIN (Número de Identificação de Localização de Emergência) que encaminha chamadas de emergência para o PSAP (Ponto de Atendimento de Segurança Pública) mais próximo.</span><span class="sxs-lookup"><span data-stu-id="72f7f-136">The route associated with this usage should point to a Session Initiation Protocol (SIP) trunk dedicated to emergency calls or to an Emergency Location Identification Number (ELIN) gateway that routes emergency calls to the nearest Public Safety Answering Point (PSAP).</span></span>

    > [!NOTE]
    > <span data-ttu-id="72f7f-137">As cadeias de caracteres de discagem e as máscaras de discagem devem ser exclusivas em uma política.</span><span class="sxs-lookup"><span data-stu-id="72f7f-137">Dial strings and dial masks must be unique within a policy.</span></span> <span data-ttu-id="72f7f-138">Isso significa que, para uma política, você pode definir vários números de emergência e definir várias máscaras de discagem para uma cadeia de caracteres de discagem, mas cada cadeia de discagem e máscara de discagem só devem ser usadas uma vez.</span><span class="sxs-lookup"><span data-stu-id="72f7f-138">This means that for a policy, you can define multiple emergency numbers and you can set multiple dial masks for a dial string, but each dial string and dial mask must only be used one time.</span></span>

6. <span data-ttu-id="72f7f-139">Clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="72f7f-139">Click **Save**.</span></span>

### <a name="using-powershell"></a><span data-ttu-id="72f7f-140">Usando o Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="72f7f-140">Using PowerShell</span></span>

<span data-ttu-id="72f7f-141">Consulte [New-CsTeamsEmergencyCallRoutingPolicy.](https://docs.microsoft.com/powershell/module/skype/new-csteamsemergencycallroutingpolicy)</span><span class="sxs-lookup"><span data-stu-id="72f7f-141">See [New-CsTeamsEmergencyCallRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csteamsemergencycallroutingpolicy).</span></span>

## <a name="edit-an-emergency-call-routing-policy"></a><span data-ttu-id="72f7f-142">Editar uma política de roteamento de chamadas de emergência</span><span class="sxs-lookup"><span data-stu-id="72f7f-142">Edit an emergency call routing policy</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="72f7f-143">Usando o centro de administração do Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="72f7f-143">Using the Microsoft Teams admin center</span></span>

<span data-ttu-id="72f7f-144">Você pode editar a política global ou quaisquer políticas personalizadas que criar.</span><span class="sxs-lookup"><span data-stu-id="72f7f-144">You can edit the global policy or any custom policies that you create.</span></span>

1. <span data-ttu-id="72f7f-145">Na navegação à esquerda do Centro de administração do Microsoft Teams, vá para políticas de Emergência de Voz e clique na  >  guia Políticas **de roteamento de** chamadas.</span><span class="sxs-lookup"><span data-stu-id="72f7f-145">In the left navigation of the Microsoft Teams admin center, go to **Voice** > **Emergency policies**, and then click the **Call routing policies** tab.</span></span>
2. <span data-ttu-id="72f7f-146">Selecione a política clicando à esquerda do nome da política e, a seguir, clique em **Editar**.</span><span class="sxs-lookup"><span data-stu-id="72f7f-146">Select the policy by clicking to the left of the policy name, and then click **Edit**.</span></span>
3. <span data-ttu-id="72f7f-147">Faça as alterações que você deseja e clique em **Salvar.**</span><span class="sxs-lookup"><span data-stu-id="72f7f-147">Make the changes that you want, and then click **Save**.</span></span>

### <a name="using-powershell"></a><span data-ttu-id="72f7f-148">Usando o Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="72f7f-148">Using PowerShell</span></span>

<span data-ttu-id="72f7f-149">Consulte [Set-CsTeamsEmergencyCallRoutingPolicy.](https://docs.microsoft.com/powershell/module/skype/set-csteamsemergencycallroutingpolicy)</span><span class="sxs-lookup"><span data-stu-id="72f7f-149">See [Set-CsTeamsEmergencyCallRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsemergencycallroutingpolicy).</span></span>

## <a name="assign-a-custom-emergency-call-routing-policy-to-users"></a><span data-ttu-id="72f7f-150">Atribuir uma política de roteamento de chamada de emergência personalizada aos usuários</span><span class="sxs-lookup"><span data-stu-id="72f7f-150">Assign a custom emergency call routing policy to users</span></span>

[!INCLUDE [assign-policy](includes/assign-policy.md)]

<span data-ttu-id="72f7f-151">Confira também [Grant-CsTeamsEmergencyCallRoutingPolicy.](https://docs.microsoft.com/powershell/module/skype/grant-csteamsemergencycallroutingpolicy)</span><span class="sxs-lookup"><span data-stu-id="72f7f-151">See also [Grant-CsTeamsEmergencyCallRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsemergencycallroutingpolicy).</span></span>

## <a name="assign-a-custom-emergency-call-routing-policy-to-a-network-site"></a><span data-ttu-id="72f7f-152">Atribuir uma política de roteamento de chamada de emergência personalizada a um site de rede</span><span class="sxs-lookup"><span data-stu-id="72f7f-152">Assign a custom emergency call routing policy to a network site</span></span>

<span data-ttu-id="72f7f-153">Use o cmdlet [Set-CsTenantNetworkSite](https://docs.microsoft.com/powershell/module/skype/set-cstenantnetworksite) para atribuir uma política de roteamento de chamadas de emergência a um site de rede.</span><span class="sxs-lookup"><span data-stu-id="72f7f-153">Use the [Set-CsTenantNetworkSite](https://docs.microsoft.com/powershell/module/skype/set-cstenantnetworksite) cmdlet to assign an emergency calling routing policy to a network site.</span></span>

<span data-ttu-id="72f7f-154">Este exemplo mostra como atribuir uma política chamada Política de Roteamento de Chamada de Emergência 1 ao site1.</span><span class="sxs-lookup"><span data-stu-id="72f7f-154">This example shows how to assign a policy called Emergency Call Routing Policy 1 to the Site1 site.</span></span>

```PowerShell
Set-CsTenantNetworkSite -identity "site1" -EmergencyCallRoutingPolicy "Emergency Call Routing Policy 1"
```

## <a name="related-topics"></a><span data-ttu-id="72f7f-155">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="72f7f-155">Related topics</span></span>

[<span data-ttu-id="72f7f-156">Gerenciar políticas de chamada de emergência no Teams</span><span class="sxs-lookup"><span data-stu-id="72f7f-156">Manage emergency calling policies in Teams</span></span>](manage-emergency-calling-policies.md)

[<span data-ttu-id="72f7f-157">Visão Geral do PowerShell do Teams</span><span class="sxs-lookup"><span data-stu-id="72f7f-157">Teams PowerShell overview</span></span>](teams-powershell-overview.md)

[<span data-ttu-id="72f7f-158">Atribua políticas a seus usuários no Teams</span><span class="sxs-lookup"><span data-stu-id="72f7f-158">Assign policies to your users in Teams</span></span>](assign-policies.md)
