---
title: Gerenciar políticas de roteamento de voz no Microsoft Teams
author: lanachin
ms.author: v-lanac
manager: serdars
ms.reviewer: jastark
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
f1.keywords: ''
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: Saiba como criar e gerenciar políticas de roteamento de voz no Microsoft Teams.
ms.openlocfilehash: 7fa2530e170d398598e56d4b4f846cc316871b16
ms.sourcegitcommit: 6e24ea8aa9cccf8a1a964c8ed414ef5c7de3dc17
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/07/2020
ms.locfileid: "44160964"
---
# <a name="manage-voice-routing-policies-in-microsoft-teams"></a><span data-ttu-id="9a7dd-103">Gerenciar políticas de roteamento de voz no Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="9a7dd-103">Manage voice routing policies in Microsoft Teams</span></span>

<span data-ttu-id="9a7dd-104">Se você implantou o [Roteamento direto do sistema telefônico](direct-routing-landing-page.md) em sua organização, use as políticas de roteamento de voz para permitir que as equipes e usuários do Skype for Business online recebam e façam chamadas telefônicas para a rede telefônica comutada pública (PSTN) usando sua infraestrutura de telefonia local.</span><span class="sxs-lookup"><span data-stu-id="9a7dd-104">If you've deployed [Phone System Direct Routing](direct-routing-landing-page.md) in your organization, you use voice routing policies to allow Teams and Skype for Business Online users to receive and make phone calls to the Public Switched Telephone Network (PSTN) using your on-premises telephony infrastructure.</span></span>

<span data-ttu-id="9a7dd-105">Uma política de roteamento de voz é um contêiner de registros de uso de PSTN.</span><span class="sxs-lookup"><span data-stu-id="9a7dd-105">A voice routing policy is a container for PSTN usage records.</span></span> <span data-ttu-id="9a7dd-106">Crie e gerencie políticas de roteamento de voz indo para**políticas de roteamento de voz** de **voz** > no centro de administração do Microsoft Teams ou usando o Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="9a7dd-106">You create and manage voice routing policies by going to **Voice** > **Voice routing policies** in the Microsoft Teams admin center or by using Windows PowerShell.</span></span>

<span data-ttu-id="9a7dd-107">Você pode usar a política global (padrão para toda a organização) ou criar e atribuir políticas personalizadas.</span><span class="sxs-lookup"><span data-stu-id="9a7dd-107">You can use the global (Org-wide default) policy or create and assign custom policies.</span></span> <span data-ttu-id="9a7dd-108">Os usuários receberão automaticamente a política global, a menos que você crie e atribua uma política personalizada.</span><span class="sxs-lookup"><span data-stu-id="9a7dd-108">Users will automatically get the global policy unless you create and assign a custom policy.</span></span> <span data-ttu-id="9a7dd-109">Lembre-se de que você pode editar as configurações na política global, mas não pode renomeá-la ou excluí-la.</span><span class="sxs-lookup"><span data-stu-id="9a7dd-109">Keep in mind that you can edit the settings in the global policy but you can't rename or delete it.</span></span>

<span data-ttu-id="9a7dd-110">É importante saber que atribuir uma política de roteamento de voz a um usuário não permite que elas façam chamadas PSTN no Teams.</span><span class="sxs-lookup"><span data-stu-id="9a7dd-110">It's important to know that assigning a voice routing policy to a user doesn't enable them to make PSTN calls in Teams.</span></span> <span data-ttu-id="9a7dd-111">Você também precisará habilitar o usuário para o roteamento direto do sistema telefônico e concluir outras etapas de configuração.</span><span class="sxs-lookup"><span data-stu-id="9a7dd-111">You'll also need to enable the user for Phone System Direct Routing and complete other configuration steps.</span></span> <span data-ttu-id="9a7dd-112">Para saber mais, consulte [Configurar o roteamento direto](direct-routing-configure.md).</span><span class="sxs-lookup"><span data-stu-id="9a7dd-112">To learn more, see [Configure Direct Routing](direct-routing-configure.md).</span></span>

## <a name="create-a-custom-voice-routing-policy"></a><span data-ttu-id="9a7dd-113">Criar uma política de roteamento de voz personalizada</span><span class="sxs-lookup"><span data-stu-id="9a7dd-113">Create a custom voice routing policy</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="9a7dd-114">Usando o centro de administração do Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="9a7dd-114">Using the Microsoft Teams admin center</span></span>

1. <span data-ttu-id="9a7dd-115">Na navegação à esquerda do centro de administração do Microsoft Teams, vá para**políticas de roteamento de voz**de **voz** > e clique em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="9a7dd-115">In the left navigation of the Microsoft Teams admin center, go to **Voice** > **Voice routing policies**, and then click **Add**.</span></span><br>
    <span data-ttu-id="9a7dd-116">![Captura de tela da página Adicionar política de roteamento de voz no centro de administração do Microsoft Teams](media/manage-voice-routing-policies.png)</span><span class="sxs-lookup"><span data-stu-id="9a7dd-116">![Screenshot of the Add voice routing policy page in the Microsoft Teams admin center ](media/manage-voice-routing-policies.png)</span></span> 
2. <span data-ttu-id="9a7dd-117">Insira um nome e uma descrição para a política.</span><span class="sxs-lookup"><span data-stu-id="9a7dd-117">Enter a name and description for the policy.</span></span>
3. <span data-ttu-id="9a7dd-118">Em **registros de uso de PSTN**, clique em **Adicionar uso PSTN**e, em seguida, selecione os registros que você deseja adicionar.</span><span class="sxs-lookup"><span data-stu-id="9a7dd-118">Under **PSTN usage records**, click **Add PSTN usage**, and then select the records that you want to add.</span></span> <span data-ttu-id="9a7dd-119">Se você precisar criar um novo registro de uso PSTN, clique em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="9a7dd-119">If you need to create a new PSTN usage record, click **Add**.</span></span>
4. <span data-ttu-id="9a7dd-120">Se você adicionou vários registros de uso de PSTN, organize-os na ordem desejada.</span><span class="sxs-lookup"><span data-stu-id="9a7dd-120">If you added multiple PSTN usage records, arrange them in the order that you want.</span></span>
5. <span data-ttu-id="9a7dd-121">Quando tiver terminado, clique em **aplicar**.</span><span class="sxs-lookup"><span data-stu-id="9a7dd-121">When you're done, click **Apply**.</span></span>
6. <span data-ttu-id="9a7dd-122">Clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="9a7dd-122">Click **Save**.</span></span>

### <a name="using-powershell"></a><span data-ttu-id="9a7dd-123">Usando o PowerShell</span><span class="sxs-lookup"><span data-stu-id="9a7dd-123">Using PowerShell</span></span>

<span data-ttu-id="9a7dd-124">Veja [New-CsOnlineVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csonlinevoiceroutingpolicy).</span><span class="sxs-lookup"><span data-stu-id="9a7dd-124">See [New-CsOnlineVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csonlinevoiceroutingpolicy).</span></span>

## <a name="edit-a-voice-routing-policy"></a><span data-ttu-id="9a7dd-125">Editar uma política de roteamento de voz</span><span class="sxs-lookup"><span data-stu-id="9a7dd-125">Edit a voice routing policy</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="9a7dd-126">Usando o centro de administração do Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="9a7dd-126">Using the Microsoft Teams admin center</span></span>

<span data-ttu-id="9a7dd-127">Você pode editar a política global ou qualquer política personalizada criada.</span><span class="sxs-lookup"><span data-stu-id="9a7dd-127">You can edit the global policy or any custom policies that you create.</span></span>

1. <span data-ttu-id="9a7dd-128">Na navegação à esquerda do centro de administração do Microsoft Teams, acesse políticas **de** > **Roteamento de voz**.</span><span class="sxs-lookup"><span data-stu-id="9a7dd-128">In the left navigation of the Microsoft Teams admin center, go to **Voice** > **Voice routing policies**.</span></span>
2. <span data-ttu-id="9a7dd-129">Selecione a política clicando à esquerda do nome da política e, em seguida, clique em **Editar**.</span><span class="sxs-lookup"><span data-stu-id="9a7dd-129">Select the policy by clicking to the left of the policy name, and then click **Edit**.</span></span>
3. <span data-ttu-id="9a7dd-130">Clique em **Adicionar/remover registros de uso PSTN**, faça as alterações desejadas e clique em **salvar**.</span><span class="sxs-lookup"><span data-stu-id="9a7dd-130">Click **Add/remove PSTN usage records**, make the changes that you want, and then click **Save**.</span></span>

### <a name="using-powershell"></a><span data-ttu-id="9a7dd-131">Usando o PowerShell</span><span class="sxs-lookup"><span data-stu-id="9a7dd-131">Using PowerShell</span></span>

<span data-ttu-id="9a7dd-132">Consulte [set-CsOnlineVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csonlinevoiceroutingpolicy).</span><span class="sxs-lookup"><span data-stu-id="9a7dd-132">See [Set-CsOnlineVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csonlinevoiceroutingpolicy).</span></span>

## <a name="assign-a-custom-voice-routing-policy-to-users"></a><span data-ttu-id="9a7dd-133">Atribuir uma política de roteamento de voz personalizada a usuários</span><span class="sxs-lookup"><span data-stu-id="9a7dd-133">Assign a custom voice routing policy to users</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="9a7dd-134">Usando o centro de administração do Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="9a7dd-134">Using the Microsoft Teams admin center</span></span>

1. <span data-ttu-id="9a7dd-135">Na barra de navegação à esquerda do centro de administração do Microsoft Teams, vá para **Usuários** e clique no usuário.</span><span class="sxs-lookup"><span data-stu-id="9a7dd-135">In the left navigation of the Microsoft Teams admin center, go to **Users**, and then click the user.</span></span>
2. <span data-ttu-id="9a7dd-136">Clique em **políticas**e, em seguida, ao lado de **políticas atribuídas**, clique em **Editar**.</span><span class="sxs-lookup"><span data-stu-id="9a7dd-136">Click **Policies**, and then next to **Assigned policies**, click **Edit**.</span></span>
3. <span data-ttu-id="9a7dd-137">Em **política de roteamento de voz**, selecione a política que você deseja atribuir e clique em **salvar**.</span><span class="sxs-lookup"><span data-stu-id="9a7dd-137">Under **Voice routing policy**, select the policy you want to assign, and then click **Save**.</span></span>

<span data-ttu-id="9a7dd-138">Para atribuir uma política personalizada do teams a vários usuários de uma só vez, consulte [Editar configurações de usuários do teams em massa](edit-user-settings-in-bulk.md).</span><span class="sxs-lookup"><span data-stu-id="9a7dd-138">To assign a custom teams policy to multiple users at a time, see [Edit Teams user settings in bulk](edit-user-settings-in-bulk.md).</span></span>

<span data-ttu-id="9a7dd-139">Ou, você também pode fazer o seguinte:</span><span class="sxs-lookup"><span data-stu-id="9a7dd-139">Or, you can also do the following:</span></span>

1. <span data-ttu-id="9a7dd-140">Na navegação à esquerda do centro de administração do Microsoft Teams, acesse políticas **de** > **Roteamento de voz**.</span><span class="sxs-lookup"><span data-stu-id="9a7dd-140">In the left navigation of the Microsoft Teams admin center, go to **Voice** > **Voice routing policies**.</span></span>
2. <span data-ttu-id="9a7dd-141">Escolha a política clicando à esquerda do nome da política.</span><span class="sxs-lookup"><span data-stu-id="9a7dd-141">Select the policy by clicking to the left of the policy name.</span></span>
3. <span data-ttu-id="9a7dd-142">Escolha **Gerenciar usuários**.</span><span class="sxs-lookup"><span data-stu-id="9a7dd-142">Select **Manage users**.</span></span>
4. <span data-ttu-id="9a7dd-143">No painel **Gerenciar usuários**, procure o usuário pelo nome de exibição ou pelo nome de usuário, escolha o nome e marque **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="9a7dd-143">In the **Manage users** pane, search for the user by display name or by user name, select the name, and then select **Add**.</span></span> <span data-ttu-id="9a7dd-144">Repita esta etapa para cada usuário que você deseja adicionar.</span><span class="sxs-lookup"><span data-stu-id="9a7dd-144">Repeat this step for each user that you want to add.</span></span>
5. <span data-ttu-id="9a7dd-145">Quando tiver terminado de adicionar usuários, clique em **salvar**.</span><span class="sxs-lookup"><span data-stu-id="9a7dd-145">When you're finished adding users, click **Save**.</span></span>

### <a name="using-powershell"></a><span data-ttu-id="9a7dd-146">Usando o PowerShell</span><span class="sxs-lookup"><span data-stu-id="9a7dd-146">Using PowerShell</span></span>

<span data-ttu-id="9a7dd-147">Veja [Grant-CsOnlineVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csonlinevoiceroutingpolicy).</span><span class="sxs-lookup"><span data-stu-id="9a7dd-147">See [Grant-CsOnlineVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csonlinevoiceroutingpolicy).</span></span>

## <a name="related-topics"></a><span data-ttu-id="9a7dd-148">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="9a7dd-148">Related topics</span></span>

- [<span data-ttu-id="9a7dd-149">Visão Geral do PowerShell do Teams</span><span class="sxs-lookup"><span data-stu-id="9a7dd-149">Teams PowerShell overview</span></span>](teams-powershell-overview.md)
- [<span data-ttu-id="9a7dd-150">Configurar o roteamento de voz para roteamento direto</span><span class="sxs-lookup"><span data-stu-id="9a7dd-150">Configure voice routing for Direct Routing</span></span>](direct-routing-voice-routing.md)
- [<span data-ttu-id="9a7dd-151">Habilitar o Roteamento baseado na localização para o Roteamento direto</span><span class="sxs-lookup"><span data-stu-id="9a7dd-151">Enable Location-Based Routing for Direct Routing</span></span>](location-based-routing-enable.md)
