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
ms.openlocfilehash: 061e8066e06c4514a27ea302dab96acfad004ac4
ms.sourcegitcommit: ee2b4c207b3c9f993309f66cf8016e137c001c7f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/23/2020
ms.locfileid: "44350185"
---
# <a name="manage-voice-routing-policies-in-microsoft-teams"></a><span data-ttu-id="d76f7-103">Gerenciar políticas de roteamento de voz no Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="d76f7-103">Manage voice routing policies in Microsoft Teams</span></span>

<span data-ttu-id="d76f7-104">Se você implantou o [Roteamento direto do sistema telefônico](direct-routing-landing-page.md) em sua organização, use as políticas de roteamento de voz para permitir que as equipes e usuários do Skype for Business online recebam e façam chamadas telefônicas para a rede telefônica comutada pública (PSTN) usando sua infraestrutura de telefonia local.</span><span class="sxs-lookup"><span data-stu-id="d76f7-104">If you've deployed [Phone System Direct Routing](direct-routing-landing-page.md) in your organization, you use voice routing policies to allow Teams and Skype for Business Online users to receive and make phone calls to the Public Switched Telephone Network (PSTN) using your on-premises telephony infrastructure.</span></span>

<span data-ttu-id="d76f7-105">Uma política de roteamento de voz é um contêiner de registros de uso de PSTN.</span><span class="sxs-lookup"><span data-stu-id="d76f7-105">A voice routing policy is a container for PSTN usage records.</span></span> <span data-ttu-id="d76f7-106">Crie e gerencie políticas de roteamento de voz indo **Voice**para  >  **políticas de roteamento de voz** de voz no centro de administração do Microsoft Teams ou usando o Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="d76f7-106">You create and manage voice routing policies by going to **Voice** > **Voice routing policies** in the Microsoft Teams admin center or by using Windows PowerShell.</span></span>

<span data-ttu-id="d76f7-107">Você pode usar a política global (padrão para toda a organização) ou criar e atribuir políticas personalizadas.</span><span class="sxs-lookup"><span data-stu-id="d76f7-107">You can use the global (Org-wide default) policy or create and assign custom policies.</span></span> <span data-ttu-id="d76f7-108">Os usuários receberão automaticamente a política global, a menos que você crie e atribua uma política personalizada.</span><span class="sxs-lookup"><span data-stu-id="d76f7-108">Users will automatically get the global policy unless you create and assign a custom policy.</span></span> <span data-ttu-id="d76f7-109">Lembre-se de que você pode editar as configurações na política global, mas não pode renomeá-la ou excluí-la.</span><span class="sxs-lookup"><span data-stu-id="d76f7-109">Keep in mind that you can edit the settings in the global policy but you can't rename or delete it.</span></span>

<span data-ttu-id="d76f7-110">É importante saber que atribuir uma política de roteamento de voz a um usuário não permite que elas façam chamadas PSTN no Teams.</span><span class="sxs-lookup"><span data-stu-id="d76f7-110">It's important to know that assigning a voice routing policy to a user doesn't enable them to make PSTN calls in Teams.</span></span> <span data-ttu-id="d76f7-111">Você também precisará habilitar o usuário para o roteamento direto do sistema telefônico e concluir outras etapas de configuração.</span><span class="sxs-lookup"><span data-stu-id="d76f7-111">You'll also need to enable the user for Phone System Direct Routing and complete other configuration steps.</span></span> <span data-ttu-id="d76f7-112">Para saber mais, consulte [Configurar o roteamento direto](direct-routing-configure.md).</span><span class="sxs-lookup"><span data-stu-id="d76f7-112">To learn more, see [Configure Direct Routing](direct-routing-configure.md).</span></span>

## <a name="create-a-custom-voice-routing-policy"></a><span data-ttu-id="d76f7-113">Criar uma política de roteamento de voz personalizada</span><span class="sxs-lookup"><span data-stu-id="d76f7-113">Create a custom voice routing policy</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="d76f7-114">Usando o centro de administração do Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="d76f7-114">Using the Microsoft Teams admin center</span></span>

1. <span data-ttu-id="d76f7-115">Na navegação à esquerda do centro de administração do Microsoft Teams, vá para políticas de roteamento de voz de **voz**  >  **Voice routing policies**e clique em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="d76f7-115">In the left navigation of the Microsoft Teams admin center, go to **Voice** > **Voice routing policies**, and then click **Add**.</span></span><br>
    <span data-ttu-id="d76f7-116">![Captura de tela da página Adicionar política de roteamento de voz no centro de administração do Microsoft Teams](media/manage-voice-routing-policies.png)</span><span class="sxs-lookup"><span data-stu-id="d76f7-116">![Screenshot of the Add voice routing policy page in the Microsoft Teams admin center ](media/manage-voice-routing-policies.png)</span></span> 
2. <span data-ttu-id="d76f7-117">Insira um nome e uma descrição para a política.</span><span class="sxs-lookup"><span data-stu-id="d76f7-117">Enter a name and description for the policy.</span></span>
3. <span data-ttu-id="d76f7-118">Em **registros de uso de PSTN**, clique em **Adicionar uso PSTN**e, em seguida, selecione os registros que você deseja adicionar.</span><span class="sxs-lookup"><span data-stu-id="d76f7-118">Under **PSTN usage records**, click **Add PSTN usage**, and then select the records that you want to add.</span></span> <span data-ttu-id="d76f7-119">Se você precisar criar um novo registro de uso PSTN, clique em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="d76f7-119">If you need to create a new PSTN usage record, click **Add**.</span></span>
4. <span data-ttu-id="d76f7-120">Se você adicionou vários registros de uso de PSTN, organize-os na ordem desejada.</span><span class="sxs-lookup"><span data-stu-id="d76f7-120">If you added multiple PSTN usage records, arrange them in the order that you want.</span></span>
5. <span data-ttu-id="d76f7-121">Quando tiver terminado, clique em **aplicar**.</span><span class="sxs-lookup"><span data-stu-id="d76f7-121">When you're done, click **Apply**.</span></span>
6. <span data-ttu-id="d76f7-122">Clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="d76f7-122">Click **Save**.</span></span>

### <a name="using-powershell"></a><span data-ttu-id="d76f7-123">Usando o PowerShell</span><span class="sxs-lookup"><span data-stu-id="d76f7-123">Using PowerShell</span></span>

<span data-ttu-id="d76f7-124">Veja [New-CsOnlineVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csonlinevoiceroutingpolicy).</span><span class="sxs-lookup"><span data-stu-id="d76f7-124">See [New-CsOnlineVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csonlinevoiceroutingpolicy).</span></span>

## <a name="edit-a-voice-routing-policy"></a><span data-ttu-id="d76f7-125">Editar uma política de roteamento de voz</span><span class="sxs-lookup"><span data-stu-id="d76f7-125">Edit a voice routing policy</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="d76f7-126">Usando o centro de administração do Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="d76f7-126">Using the Microsoft Teams admin center</span></span>

<span data-ttu-id="d76f7-127">Você pode editar a política global ou qualquer política personalizada criada.</span><span class="sxs-lookup"><span data-stu-id="d76f7-127">You can edit the global policy or any custom policies that you create.</span></span>

1. <span data-ttu-id="d76f7-128">Na navegação à esquerda do centro de administração do Microsoft Teams, acesse políticas **de**  >  **Roteamento de voz**.</span><span class="sxs-lookup"><span data-stu-id="d76f7-128">In the left navigation of the Microsoft Teams admin center, go to **Voice** > **Voice routing policies**.</span></span>
2. <span data-ttu-id="d76f7-129">Selecione a política clicando à esquerda do nome da política e, em seguida, clique em **Editar**.</span><span class="sxs-lookup"><span data-stu-id="d76f7-129">Select the policy by clicking to the left of the policy name, and then click **Edit**.</span></span>
3. <span data-ttu-id="d76f7-130">Clique em **Adicionar/remover registros de uso PSTN**, faça as alterações desejadas e clique em **salvar**.</span><span class="sxs-lookup"><span data-stu-id="d76f7-130">Click **Add/remove PSTN usage records**, make the changes that you want, and then click **Save**.</span></span>

### <a name="using-powershell"></a><span data-ttu-id="d76f7-131">Usando o PowerShell</span><span class="sxs-lookup"><span data-stu-id="d76f7-131">Using PowerShell</span></span>

<span data-ttu-id="d76f7-132">Consulte [set-CsOnlineVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csonlinevoiceroutingpolicy).</span><span class="sxs-lookup"><span data-stu-id="d76f7-132">See [Set-CsOnlineVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csonlinevoiceroutingpolicy).</span></span>

## <a name="assign-a-custom-voice-routing-policy-to-users"></a><span data-ttu-id="d76f7-133">Atribuir uma política de roteamento de voz personalizada a usuários</span><span class="sxs-lookup"><span data-stu-id="d76f7-133">Assign a custom voice routing policy to users</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="d76f7-134">Usando o centro de administração do Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="d76f7-134">Using the Microsoft Teams admin center</span></span>

<span data-ttu-id="d76f7-135">Para atribuir uma política a um usuário:</span><span class="sxs-lookup"><span data-stu-id="d76f7-135">To assign a policy to one user:</span></span>

1. <span data-ttu-id="d76f7-136">Na barra de navegação à esquerda do centro de administração do Microsoft Teams, vá para **Usuários** e clique no usuário.</span><span class="sxs-lookup"><span data-stu-id="d76f7-136">In the left navigation of the Microsoft Teams admin center, go to **Users**, and then click the user.</span></span>
2. <span data-ttu-id="d76f7-137">Clique em **políticas**e, em seguida, ao lado de **políticas atribuídas**, clique em **Editar**.</span><span class="sxs-lookup"><span data-stu-id="d76f7-137">Click **Policies**, and then next to **Assigned policies**, click **Edit**.</span></span>
3. <span data-ttu-id="d76f7-138">Em **política de roteamento de voz**, selecione a política que você deseja atribuir e clique em **salvar**.</span><span class="sxs-lookup"><span data-stu-id="d76f7-138">Under **Voice routing policy**, select the policy you want to assign, and then click **Save**.</span></span>

<span data-ttu-id="d76f7-139">Para atribuir uma política a vários usuários de uma só vez:</span><span class="sxs-lookup"><span data-stu-id="d76f7-139">To assign a policy to multiple users at a time:</span></span>

1. <span data-ttu-id="d76f7-140">Na navegação à esquerda do centro de administração do Microsoft Teams, vá para **usuários**e procure os usuários ou filtre o modo de exibição para mostrar os usuários que você deseja.</span><span class="sxs-lookup"><span data-stu-id="d76f7-140">In the left navigation of the Microsoft Teams admin center, go to **Users**, and then search for the users or filter the view to show the users you want.</span></span>
2. <span data-ttu-id="d76f7-141">Na coluna **&#x2713;** (marca de seleção), selecione os usuários.</span><span class="sxs-lookup"><span data-stu-id="d76f7-141">In the **&#x2713;** (check mark) column, select the users.</span></span> <span data-ttu-id="d76f7-142">Para selecionar todos os usuários, clique no &#x2713; (marca de seleção) na parte superior da tabela.</span><span class="sxs-lookup"><span data-stu-id="d76f7-142">To select all users, click the &#x2713; (check mark) at the top of the table.</span></span>
3. <span data-ttu-id="d76f7-143">Clique em **Editar configurações**, faça as alterações desejadas e, em seguida, clique em **aplicar**.</span><span class="sxs-lookup"><span data-stu-id="d76f7-143">Click **Edit settings**, make the changes that you want, and then click **Apply**.</span></span>  

<span data-ttu-id="d76f7-144">Ou, você também pode fazer o seguinte:</span><span class="sxs-lookup"><span data-stu-id="d76f7-144">Or, you can also do the following:</span></span>

1. <span data-ttu-id="d76f7-145">Na navegação à esquerda do centro de administração do Microsoft Teams, acesse políticas **de**  >  **Roteamento de voz**.</span><span class="sxs-lookup"><span data-stu-id="d76f7-145">In the left navigation of the Microsoft Teams admin center, go to **Voice** > **Voice routing policies**.</span></span>
2. <span data-ttu-id="d76f7-146">Escolha a política clicando à esquerda do nome da política.</span><span class="sxs-lookup"><span data-stu-id="d76f7-146">Select the policy by clicking to the left of the policy name.</span></span>
3. <span data-ttu-id="d76f7-147">Escolha **Gerenciar usuários**.</span><span class="sxs-lookup"><span data-stu-id="d76f7-147">Select **Manage users**.</span></span>
4. <span data-ttu-id="d76f7-148">No painel **Gerenciar usuários**, procure o usuário pelo nome de exibição ou pelo nome de usuário, escolha o nome e marque **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="d76f7-148">In the **Manage users** pane, search for the user by display name or by user name, select the name, and then select **Add**.</span></span> <span data-ttu-id="d76f7-149">Repita esta etapa para cada usuário que você deseja adicionar.</span><span class="sxs-lookup"><span data-stu-id="d76f7-149">Repeat this step for each user that you want to add.</span></span>
5. <span data-ttu-id="d76f7-150">Quando tiver terminado de adicionar usuários, clique em **salvar**.</span><span class="sxs-lookup"><span data-stu-id="d76f7-150">When you're finished adding users, click **Save**.</span></span>

### <a name="using-powershell"></a><span data-ttu-id="d76f7-151">Usando o PowerShell</span><span class="sxs-lookup"><span data-stu-id="d76f7-151">Using PowerShell</span></span>

<span data-ttu-id="d76f7-152">Veja [Grant-CsOnlineVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csonlinevoiceroutingpolicy).</span><span class="sxs-lookup"><span data-stu-id="d76f7-152">See [Grant-CsOnlineVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csonlinevoiceroutingpolicy).</span></span>

## <a name="related-topics"></a><span data-ttu-id="d76f7-153">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="d76f7-153">Related topics</span></span>

- [<span data-ttu-id="d76f7-154">Visão Geral do PowerShell do Teams</span><span class="sxs-lookup"><span data-stu-id="d76f7-154">Teams PowerShell overview</span></span>](teams-powershell-overview.md)
- [<span data-ttu-id="d76f7-155">Configurar o roteamento de voz para roteamento direto</span><span class="sxs-lookup"><span data-stu-id="d76f7-155">Configure voice routing for Direct Routing</span></span>](direct-routing-voice-routing.md)
- [<span data-ttu-id="d76f7-156">Habilitar o Roteamento baseado na localização para o Roteamento direto</span><span class="sxs-lookup"><span data-stu-id="d76f7-156">Enable Location-Based Routing for Direct Routing</span></span>](location-based-routing-enable.md)
- [<span data-ttu-id="d76f7-157">Atribuir políticas a seus usuários no Teams</span><span class="sxs-lookup"><span data-stu-id="d76f7-157">Assign policies to your users in Teams</span></span>](assign-policies.md)
