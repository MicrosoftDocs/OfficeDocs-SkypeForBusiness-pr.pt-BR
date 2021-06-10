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
description: Saiba como usar e gerenciar políticas de roteamento de chamadas de emergência Microsoft Teams configurar números de emergência e especificar como as chamadas de emergência são roteada.
ms.custom:
- seo-marvel-apr2020
- ms.teamsadmincenter.voice.emergencycallroutingpolicies.overview
ms.openlocfilehash: 0fb3a80bf5c1a064435754c4f999f6a62214b021
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51096175"
---
# <a name="manage-emergency-call-routing-policies-in-microsoft-teams"></a><span data-ttu-id="c8d69-103">Gerenciar políticas de roteamento de chamadas de emergência Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="c8d69-103">Manage emergency call routing policies in Microsoft Teams</span></span>

<span data-ttu-id="c8d69-104">Se você tiver [](direct-routing-landing-page.md) implantado Sistema de Telefonia Roteamento Direto em sua organização, poderá usar políticas de roteamento de chamadas de emergência em Microsoft Teams para configurar números de emergência e especificar como as chamadas de emergência são roteadas.</span><span class="sxs-lookup"><span data-stu-id="c8d69-104">If you've deployed [Phone System Direct Routing](direct-routing-landing-page.md) in your organization, you can use emergency call routing policies in Microsoft Teams to set up emergency numbers and specify how emergency calls are routed.</span></span> <span data-ttu-id="c8d69-105">Uma política de roteamento de chamadas de emergência determina se os serviços de emergência aprimorados estão habilitados para usuários que têm a política atribuída, os números usados para chamar serviços de emergência (por exemplo, 911 nos Estados Unidos) e como as chamadas aos serviços de emergência são roteadas.</span><span class="sxs-lookup"><span data-stu-id="c8d69-105">An emergency call routing policy determines whether enhanced emergency services is enabled for users who are assigned the policy, the numbers used to call emergency services (for example, 911 in the United States), and how calls to emergency services are routed.</span></span>

<span data-ttu-id="c8d69-106">Você gerencia políticas de roteamento de chamadas de emergência indo para políticas de Emergência de Voz no centro de administração Microsoft Teams   >   ou usando Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="c8d69-106">You manage emergency call routing policies by going to **Voice** > **Emergency policies** in the Microsoft Teams admin center or by using Windows PowerShell.</span></span> <span data-ttu-id="c8d69-107">As políticas podem ser atribuídas a usuários e [sites de rede.](cloud-voice-network-settings.md)</span><span class="sxs-lookup"><span data-stu-id="c8d69-107">The policies can be assigned to users and [network sites](cloud-voice-network-settings.md).</span></span>

<span data-ttu-id="c8d69-108">Para usuários, você pode usar a política global (padrão em toda a organização) ou criar e atribuir políticas personalizadas.</span><span class="sxs-lookup"><span data-stu-id="c8d69-108">For users, you can use the global (Org-wide default) policy or create and assign custom policies.</span></span> <span data-ttu-id="c8d69-109">Os usuários receberão automaticamente a política global, a menos que você crie e atribua uma política personalizada.</span><span class="sxs-lookup"><span data-stu-id="c8d69-109">Users will automatically get the global policy unless you create and assign a custom policy.</span></span> <span data-ttu-id="c8d69-110">Lembre-se de que você pode editar as configurações na política global, mas não pode renomeá-la ou excluí-la.</span><span class="sxs-lookup"><span data-stu-id="c8d69-110">Keep in mind that you can edit the settings in the global policy but you can't rename or delete it.</span></span> <span data-ttu-id="c8d69-111">Para sites de rede, você cria e atribui políticas personalizadas.</span><span class="sxs-lookup"><span data-stu-id="c8d69-111">For network sites, you create and assign custom policies.</span></span>

<span data-ttu-id="c8d69-112">Se você atribuiu uma política de roteamento de chamadas de emergência a um site de rede e a um usuário e se esse usuário estiver nesse site de rede, a política atribuída ao site de rede substituirá a política atribuída ao usuário.</span><span class="sxs-lookup"><span data-stu-id="c8d69-112">If you assigned an emergency call routing policy to a network site and to a user and if that user is at that network site, the policy that's assigned to the network site overrides the policy that's assigned to the user.</span></span>

## <a name="create-a-custom-emergency-call-routing-policy"></a><span data-ttu-id="c8d69-113">Criar uma política de roteamento de chamadas de emergência personalizada</span><span class="sxs-lookup"><span data-stu-id="c8d69-113">Create a custom emergency call routing policy</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="c8d69-114">Usando o centro de administração do Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="c8d69-114">Using the Microsoft Teams admin center</span></span>

1. <span data-ttu-id="c8d69-115">Na navegação à esquerda do centro de administração Microsoft Teams, vá para Políticas de Emergência de Voz e clique na guia Políticas de  >   **roteamento de** chamadas.</span><span class="sxs-lookup"><span data-stu-id="c8d69-115">In the left navigation of the Microsoft Teams admin center, go to **Voice** > **Emergency policies**, and then click the **Call routing policies** tab.</span></span>
2. <span data-ttu-id="c8d69-116">Clique em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="c8d69-116">Click **Add**.</span></span>
3. <span data-ttu-id="c8d69-117">Insira um nome e uma descrição para a política.</span><span class="sxs-lookup"><span data-stu-id="c8d69-117">Enter a name and description for the policy.</span></span>
4. <span data-ttu-id="c8d69-118">Para habilitar a chamada de emergência dinâmica, ative **a chamada de emergência dinâmica.**</span><span class="sxs-lookup"><span data-stu-id="c8d69-118">To enable dynamic emergency calling, turn on **Dynamic emergency calling**.</span></span> <span data-ttu-id="c8d69-119">Quando a chamada de emergência dinâmica é habilitada, Teams recupera informações de política e local do serviço e inclui essas informações como parte da chamada de emergência.</span><span class="sxs-lookup"><span data-stu-id="c8d69-119">When dynamic emergency calling is enabled, Teams retrieves policy and location information from the service and includes that information as part of the emergency call.</span></span>
5. <span data-ttu-id="c8d69-120">Defina um ou mais números de emergência.</span><span class="sxs-lookup"><span data-stu-id="c8d69-120">Define one or more emergency numbers.</span></span> <span data-ttu-id="c8d69-121">Para fazer isso, em **Números de emergência,** clique em **Adicionar** e faça o seguinte:</span><span class="sxs-lookup"><span data-stu-id="c8d69-121">To do this, under **Emergency numbers**, click **Add**, and then do the following:</span></span>
    1. <span data-ttu-id="c8d69-122">**Cadeia de caracteres de discagem** de emergência : Insira a cadeia de caracteres de discagem de emergência.</span><span class="sxs-lookup"><span data-stu-id="c8d69-122">**Emergency dial string**: Enter the emergency dial string.</span></span> <span data-ttu-id="c8d69-123">Essa cadeia de caracteres de discagem indica que uma chamada é uma chamada de emergência.</span><span class="sxs-lookup"><span data-stu-id="c8d69-123">This dial string indicates that a call is an emergency call.</span></span>
        > [!NOTE]
        > <span data-ttu-id="c8d69-124">Para Roteamento Direto, estamos fazendo a transição Teams clientes que enviam chamadas de emergência com um "+" em frente à cadeia de caracteres de discagem de emergência.</span><span class="sxs-lookup"><span data-stu-id="c8d69-124">For Direct Routing, we're transitioning away from Teams clients sending emergency calls with a "+" in front of the emergency dial string.</span></span> <span data-ttu-id="c8d69-125">Até que a transição seja concluída, o padrão de rota de voz para corresponder a uma cadeia de caracteres de discagem de emergência deve garantir que uma combinação seja feita para cadeias de caracteres que tenham e não tenham um "+" anterior, como 911 e +911.</span><span class="sxs-lookup"><span data-stu-id="c8d69-125">Until the transition is completed, the voice route pattern to match an emergency dial string should ensure a match is made for strings that have and don't have a preceding "+", such as 911 and +911.</span></span> <span data-ttu-id="c8d69-126">Por exemplo, ^ \\ +?911 ou .\*.</span><span class="sxs-lookup"><span data-stu-id="c8d69-126">For example, ^\\+?911 or .\*.</span></span>
    2. <span data-ttu-id="c8d69-127">**Máscara de discagem de** emergência : Para cada número de emergência, você pode especificar zero ou mais máscaras de discagem de emergência.</span><span class="sxs-lookup"><span data-stu-id="c8d69-127">**Emergency dial mask**: For each emergency number, you can specify zero or more emergency dial masks.</span></span> <span data-ttu-id="c8d69-128">Uma máscara de discagem é o número que você deseja converter no valor da cadeia de caracteres de discagem de emergência.</span><span class="sxs-lookup"><span data-stu-id="c8d69-128">A dial mask is the number that you want to translate into the value of the emergency dial string.</span></span> <span data-ttu-id="c8d69-129">Isso permite que números de emergência alternativos sejam discados e ainda tenham a chamada para alcançar os serviços de emergência.</span><span class="sxs-lookup"><span data-stu-id="c8d69-129">This allows for alternate emergency numbers to be dialed and still have the call reach emergency services.</span></span> <br><span data-ttu-id="c8d69-130">Por exemplo, você adiciona 112 como máscara de discagem de emergência, que é o número de serviço de emergência para a maioria da Europa e 911 como a cadeia de caracteres de discagem de emergência.</span><span class="sxs-lookup"><span data-stu-id="c8d69-130">For example, you add 112 as the emergency dial mask, which is the emergency service number for most of Europe, and 911 as the emergency dial string.</span></span> <span data-ttu-id="c8d69-131">Um Teams da Europa que está visitando pode não saber que o 911 é o número de emergência nos Estados Unidos e, quando ele disca 112, a chamada é feita para 911.</span><span class="sxs-lookup"><span data-stu-id="c8d69-131">A Teams user from Europe who is visiting may not know that 911 is the emergency number in the United States, and when they dial 112, the call is made to 911.</span></span> <span data-ttu-id="c8d69-132">Para definir várias máscaras de discagem, separe cada valor por ponto e vírgula.</span><span class="sxs-lookup"><span data-stu-id="c8d69-132">To define multiple dial masks, separate each value by a semicolon.</span></span> <span data-ttu-id="c8d69-133">Por exemplo, 112;212.</span><span class="sxs-lookup"><span data-stu-id="c8d69-133">For example, 112;212.</span></span>
    3. <span data-ttu-id="c8d69-134">**Registro de uso PSTN**: Selecione o registro de uso PSTN (Rede Telefônica Pública Comutado).</span><span class="sxs-lookup"><span data-stu-id="c8d69-134">**PSTN usage record**: Select the Public Switched Telephone Network (PSTN) usage record.</span></span> <span data-ttu-id="c8d69-135">O registro de uso PSTN é usado para determinar qual rota é usada para rotear chamadas de emergência de usuários autorizados a usá-las.</span><span class="sxs-lookup"><span data-stu-id="c8d69-135">The PSTN usage record is used to determine which route is used to route emergency calls from users who are authorized to use them.</span></span> <span data-ttu-id="c8d69-136">A rota associada a esse uso deve apontar para um tronco SIP (Session Initiation Protocol) dedicado a chamadas de emergência ou a um gateway ELIN (Número de Identificação de Local de Emergência) que encaminha chamadas de emergência para o PSAP (Ponto de Atendimento de Segurança Pública) mais próximo.</span><span class="sxs-lookup"><span data-stu-id="c8d69-136">The route associated with this usage should point to a Session Initiation Protocol (SIP) trunk dedicated to emergency calls or to an Emergency Location Identification Number (ELIN) gateway that routes emergency calls to the nearest Public Safety Answering Point (PSAP).</span></span>

    > [!NOTE]
    > <span data-ttu-id="c8d69-137">As cadeias de caracteres de discagem e as máscaras de discagem devem ser exclusivas em uma política.</span><span class="sxs-lookup"><span data-stu-id="c8d69-137">Dial strings and dial masks must be unique within a policy.</span></span> <span data-ttu-id="c8d69-138">Isso significa que, para uma política, você pode definir vários números de emergência e definir várias máscaras de discagem para uma cadeia de caracteres de discagem, mas cada cadeia de caracteres de discagem e máscara de discagem só devem ser usadas uma vez.</span><span class="sxs-lookup"><span data-stu-id="c8d69-138">This means that for a policy, you can define multiple emergency numbers and you can set multiple dial masks for a dial string, but each dial string and dial mask must only be used one time.</span></span>

6. <span data-ttu-id="c8d69-139">Clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="c8d69-139">Click **Save**.</span></span>

### <a name="using-powershell"></a><span data-ttu-id="c8d69-140">Usando o Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="c8d69-140">Using PowerShell</span></span>

<span data-ttu-id="c8d69-141">Consulte [New-CsTeamsEmergencyCallRoutingPolicy](/powershell/module/skype/new-csteamsemergencycallroutingpolicy).</span><span class="sxs-lookup"><span data-stu-id="c8d69-141">See [New-CsTeamsEmergencyCallRoutingPolicy](/powershell/module/skype/new-csteamsemergencycallroutingpolicy).</span></span>

## <a name="edit-an-emergency-call-routing-policy"></a><span data-ttu-id="c8d69-142">Editar uma política de roteamento de chamadas de emergência</span><span class="sxs-lookup"><span data-stu-id="c8d69-142">Edit an emergency call routing policy</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="c8d69-143">Usando o centro de administração do Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="c8d69-143">Using the Microsoft Teams admin center</span></span>

<span data-ttu-id="c8d69-144">Você pode editar a política global ou quaisquer políticas personalizadas que você criar.</span><span class="sxs-lookup"><span data-stu-id="c8d69-144">You can edit the global policy or any custom policies that you create.</span></span>

1. <span data-ttu-id="c8d69-145">Na navegação à esquerda do centro de administração Microsoft Teams, vá para Políticas de Emergência de Voz e clique na guia Políticas de  >   **roteamento de** chamadas.</span><span class="sxs-lookup"><span data-stu-id="c8d69-145">In the left navigation of the Microsoft Teams admin center, go to **Voice** > **Emergency policies**, and then click the **Call routing policies** tab.</span></span>
2. <span data-ttu-id="c8d69-146">Selecione a política clicando à esquerda do nome da política e, a seguir, clique em **Editar**.</span><span class="sxs-lookup"><span data-stu-id="c8d69-146">Select the policy by clicking to the left of the policy name, and then click **Edit**.</span></span>
3. <span data-ttu-id="c8d69-147">Faça as alterações que você deseja e clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="c8d69-147">Make the changes that you want, and then click **Save**.</span></span>

### <a name="using-powershell"></a><span data-ttu-id="c8d69-148">Usando o Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="c8d69-148">Using PowerShell</span></span>

<span data-ttu-id="c8d69-149">Consulte [Set-CsTeamsEmergencyCallRoutingPolicy](/powershell/module/skype/set-csteamsemergencycallroutingpolicy).</span><span class="sxs-lookup"><span data-stu-id="c8d69-149">See [Set-CsTeamsEmergencyCallRoutingPolicy](/powershell/module/skype/set-csteamsemergencycallroutingpolicy).</span></span>

## <a name="assign-a-custom-emergency-call-routing-policy-to-users"></a><span data-ttu-id="c8d69-150">Atribuir uma política de roteamento de chamadas de emergência personalizada aos usuários</span><span class="sxs-lookup"><span data-stu-id="c8d69-150">Assign a custom emergency call routing policy to users</span></span>

[!INCLUDE [assign-policy](includes/assign-policy.md)]

<span data-ttu-id="c8d69-151">Consulte também [Grant-CsTeamsEmergencyCallRoutingPolicy](/powershell/module/skype/grant-csteamsemergencycallroutingpolicy).</span><span class="sxs-lookup"><span data-stu-id="c8d69-151">See also [Grant-CsTeamsEmergencyCallRoutingPolicy](/powershell/module/skype/grant-csteamsemergencycallroutingpolicy).</span></span>

## <a name="assign-a-custom-emergency-call-routing-policy-to-a-network-site"></a><span data-ttu-id="c8d69-152">Atribuir uma política de roteamento de chamadas de emergência personalizada a um site de rede</span><span class="sxs-lookup"><span data-stu-id="c8d69-152">Assign a custom emergency call routing policy to a network site</span></span>

<span data-ttu-id="c8d69-153">Use o cmdlet [Set-CsTenantNetworkSite](/powershell/module/skype/set-cstenantnetworksite) para atribuir uma política de roteamento de chamadas de emergência a um site de rede.</span><span class="sxs-lookup"><span data-stu-id="c8d69-153">Use the [Set-CsTenantNetworkSite](/powershell/module/skype/set-cstenantnetworksite) cmdlet to assign an emergency calling routing policy to a network site.</span></span>

<span data-ttu-id="c8d69-154">Este exemplo mostra como atribuir uma política chamada Política de Roteamento de Chamadas de Emergência 1 ao site Site1.</span><span class="sxs-lookup"><span data-stu-id="c8d69-154">This example shows how to assign a policy called Emergency Call Routing Policy 1 to the Site1 site.</span></span>

```PowerShell
Set-CsTenantNetworkSite -identity "site1" -EmergencyCallRoutingPolicy "Emergency Call Routing Policy 1"
```

## <a name="related-topics"></a><span data-ttu-id="c8d69-155">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="c8d69-155">Related topics</span></span>

[<span data-ttu-id="c8d69-156">Gerenciar políticas de chamada de emergência em Teams</span><span class="sxs-lookup"><span data-stu-id="c8d69-156">Manage emergency calling policies in Teams</span></span>](manage-emergency-calling-policies.md)

[<span data-ttu-id="c8d69-157">Visão Geral do PowerShell do Teams</span><span class="sxs-lookup"><span data-stu-id="c8d69-157">Teams PowerShell overview</span></span>](teams-powershell-overview.md)

[<span data-ttu-id="c8d69-158">Atribuir políticas aos usuários no Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="c8d69-158">Assign policies to your users in Teams</span></span>](assign-policies.md)