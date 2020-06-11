---
title: Gerenciar políticas do teams no Microsoft Teams
author: lanachin
ms.author: v-lanac
manager: serdars
ms.reviewer: jastark
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: Saiba como usar e gerenciar políticas de equipe em sua organização para controlar o que os usuários podem fazer em equipes e canais.
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.teams.teamspolicies.new.tooltip.discoverteams
- ms.teamsadmincenter.teams.teamspolicies.new.tooltip.createchannels
- ms.teamsadmincenter.teams.teamsandchannelpolicies.overview
- ms.teamsadmincenter.teamsandchannelpolicies.overview
- ms.teamsadmincenter.teams.teamspolicies.new.tooltip.discover
- ms.teamsadmincenter.teams.teamspolicies.new.tooltip.create
ms.openlocfilehash: f046a21ee0ff0bf4fe49feea2c4a38702516227a
ms.sourcegitcommit: 1807ea5509f8efa6abba8462bce2f3646117e8bf
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/10/2020
ms.locfileid: "44690957"
---
# <a name="manage-teams-policies-in-microsoft-teams"></a><span data-ttu-id="10c32-103">Gerenciar políticas do teams no Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="10c32-103">Manage teams policies in Microsoft Teams</span></span>

<span data-ttu-id="10c32-104">Como administrador, você pode usar políticas do teams no Microsoft Teams para controlar o que os usuários em sua organização podem fazer em equipes e canais.</span><span class="sxs-lookup"><span data-stu-id="10c32-104">As an admin, you can use teams policies in Microsoft Teams to control what users in your organization can do in teams and channels.</span></span> <span data-ttu-id="10c32-105">Por exemplo, você pode definir se os usuários podem descobrir equipes particulares nos resultados da pesquisa e na Galeria da equipe e se os usuários podem criar canais privados.</span><span class="sxs-lookup"><span data-stu-id="10c32-105">For example, you can set whether users are allowed to discover private teams in search results and in the team gallery and whether users are allowed to create private channels.</span></span>

<span data-ttu-id="10c32-106">Você gerencia políticas do teams acessando políticas **do teams**  >  **Team** no centro de administração do Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="10c32-106">You manage teams policies by going to **Teams** > **Teams policies** in the Microsoft Teams admin center.</span></span> <span data-ttu-id="10c32-107">Você pode usar a política global (padrão para toda a organização) ou criar políticas personalizadas e atribuí-las aos usuários.</span><span class="sxs-lookup"><span data-stu-id="10c32-107">You can use the global (Org-wide default) policy or create custom policies and assign them to users.</span></span> <span data-ttu-id="10c32-108">Os usuários da sua organização terão automaticamente a política global, a menos que você crie e atribua uma política personalizada.</span><span class="sxs-lookup"><span data-stu-id="10c32-108">Users in your organization will automatically get the global policy unless you create and assign a custom policy.</span></span>

<span data-ttu-id="10c32-109">Você pode editar a política global ou criar e atribuir uma política personalizada.</span><span class="sxs-lookup"><span data-stu-id="10c32-109">You can edit the global policy or create and assign a custom policy.</span></span> <span data-ttu-id="10c32-110">Se for atribuída uma política personalizada a um usuário, essa política se aplicará ao usuário.</span><span class="sxs-lookup"><span data-stu-id="10c32-110">If a user is assigned a custom policy, that policy applies to the user.</span></span> <span data-ttu-id="10c32-111">Se um usuário não estiver atribuído a uma política personalizada, a política global se aplicará ao usuário.</span><span class="sxs-lookup"><span data-stu-id="10c32-111">If a user isn't assigned a custom policy, the global policy applies to the user.</span></span> <span data-ttu-id="10c32-112">Depois de editar a política global ou atribuir uma política, pode demorar algumas horas para que as alterações entrem em vigor.</span><span class="sxs-lookup"><span data-stu-id="10c32-112">After you edit the global policy or assign a policy, it can take a few hours for changes to take effect.</span></span>

## <a name="create-a-custom-teams-policy"></a><span data-ttu-id="10c32-113">Criar uma política personalizada do Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="10c32-113">Create a custom teams policy</span></span>

1. <span data-ttu-id="10c32-114">Na navegação à esquerda do centro de administração do Microsoft Teams, **vá para políticas do teams**  >  **Teams**.</span><span class="sxs-lookup"><span data-stu-id="10c32-114">In the left navigation of the Microsoft Teams admin center, go to **Teams** > **Teams policies**.</span></span>
2. <span data-ttu-id="10c32-115">Clique em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="10c32-115">Click **Add**.</span></span>
3. <span data-ttu-id="10c32-116">Insira um nome e uma descrição para a política.</span><span class="sxs-lookup"><span data-stu-id="10c32-116">Enter a name and description for the policy.</span></span>

    ![Captura de tela das configurações de política de equipes](media/teams-policies.png)
4. <span data-ttu-id="10c32-118">Escolha as configurações desejadas:</span><span class="sxs-lookup"><span data-stu-id="10c32-118">Choose the settings that you want:</span></span>

- <span data-ttu-id="10c32-119">**Descubra equipes particulares**:<a name="discoverteams"> </a> Ative essa configuração para permitir que os usuários descubram equipes particulares nos resultados da pesquisa e na Galeria de equipe.</span><span class="sxs-lookup"><span data-stu-id="10c32-119">**Discover private teams**:<a name="discoverteams"> </a> Turn on this setting to allow users to discover private teams in search results and in the team gallery.</span></span>
- <span data-ttu-id="10c32-120">**Criar canais privados**: <a name="createchannels"> </a>Ative essa configuração para permitir que os usuários criem canais privados.</span><span class="sxs-lookup"><span data-stu-id="10c32-120">**Create private channels**: <a name="createchannels"> </a>Turn on this setting to allow users to create private channels.</span></span>

5. <span data-ttu-id="10c32-121">Clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="10c32-121">Click **Save**.</span></span>

## <a name="edit-a-teams-policy"></a><span data-ttu-id="10c32-122">Editar uma política de equipe</span><span class="sxs-lookup"><span data-stu-id="10c32-122">Edit a teams policy</span></span>

<span data-ttu-id="10c32-123">Você pode editar a política global ou qualquer política personalizada criada.</span><span class="sxs-lookup"><span data-stu-id="10c32-123">You can edit the global policy or any custom policies that you create.</span></span>

1. <span data-ttu-id="10c32-124">Na navegação à esquerda do centro de administração do Microsoft Teams, **vá para políticas do teams**  >  **Teams**.</span><span class="sxs-lookup"><span data-stu-id="10c32-124">In the left navigation of the Microsoft Teams admin center, go to **Teams** > **Teams policies**.</span></span>
2. <span data-ttu-id="10c32-125">Selecione a política clicando à esquerda do nome da política e, em seguida, clique em **Editar**.</span><span class="sxs-lookup"><span data-stu-id="10c32-125">Select the policy by clicking to the left of the policy name, and then click **Edit**.</span></span>
3. <span data-ttu-id="10c32-126">Ative ou desative as configurações desejadas e clique em **salvar**.</span><span class="sxs-lookup"><span data-stu-id="10c32-126">Turn on or turn off the settings that you want, and then click **Save**.</span></span>

## <a name="assign-a-custom-teams-policy-to-users"></a><span data-ttu-id="10c32-127">Atribuir uma política personalizada do teams aos usuários</span><span class="sxs-lookup"><span data-stu-id="10c32-127">Assign a custom teams policy to users</span></span>

<span data-ttu-id="10c32-128">Você pode usar o centro de administração do Microsoft Teams para atribuir uma política personalizada a um ou mais usuários ou ao módulo do PowerShell do Skype for Business para atribuir uma política personalizada a grupos de usuários, como um grupo de segurança ou grupo de distribuição.</span><span class="sxs-lookup"><span data-stu-id="10c32-128">You can use the Microsoft Teams admin center to assign a custom policy to one or more users or the Skype for Business PowerShell module to assign a custom policy to groups of users, such as a security group or distribution group.</span></span>

### <a name="assign-a-custom-teams-policy-to-users"></a><span data-ttu-id="10c32-129">Atribuir uma política personalizada do teams aos usuários</span><span class="sxs-lookup"><span data-stu-id="10c32-129">Assign a custom teams policy to users</span></span>

<span data-ttu-id="10c32-130">Para atribuir uma política a um usuário:</span><span class="sxs-lookup"><span data-stu-id="10c32-130">To assign a policy to one user:</span></span>

1. <span data-ttu-id="10c32-131">Na barra de navegação à esquerda do centro de administração do Microsoft Teams, vá para **Usuários** e clique no usuário.</span><span class="sxs-lookup"><span data-stu-id="10c32-131">In the left navigation of the Microsoft Teams admin center, go to **Users**, and then click the user.</span></span>
2. <span data-ttu-id="10c32-132">Clique em **políticas**e, em seguida, ao lado de **políticas atribuídas**, clique em **Editar**.</span><span class="sxs-lookup"><span data-stu-id="10c32-132">Click **Policies**, and then next to **Assigned policies**, click **Edit**.</span></span>
3. <span data-ttu-id="10c32-133">Em **políticas do teams**, selecione a política que você deseja atribuir e clique em **salvar**.</span><span class="sxs-lookup"><span data-stu-id="10c32-133">Under **Teams policies**, select the policy you want to assign, and then click **Save**.</span></span>

<span data-ttu-id="10c32-134">Para atribuir uma política a vários usuários por vez:</span><span class="sxs-lookup"><span data-stu-id="10c32-134">To assign a policy to multiple users at a time:</span></span>

1. <span data-ttu-id="10c32-135">Na barra de navegação à esquerda do centro de administração do Microsoft Teams, vá para **Usuários** e, em seguida, pesquise os usuários ou filtre o modo de exibição para mostrar os usuários que você deseja.</span><span class="sxs-lookup"><span data-stu-id="10c32-135">In the left navigation of the Microsoft Teams admin center, go to **Users**, and then search for the users or filter the view to show the users you want.</span></span>
2. <span data-ttu-id="10c32-136">Na coluna **&#x2713;** (marca de seleção), selecione os usuários.</span><span class="sxs-lookup"><span data-stu-id="10c32-136">In the **&#x2713;** (check mark) column, select the users.</span></span> <span data-ttu-id="10c32-137">Para selecionar todos os usuários, clique na (marca de seleção) &#x2713; na parte superior da tabela.</span><span class="sxs-lookup"><span data-stu-id="10c32-137">To select all users, click the &#x2713; (check mark) at the top of the table.</span></span>
3. <span data-ttu-id="10c32-138">Clique em **Editar configurações**, faça as alterações desejadas e, em seguida, clique em **Aplicar**.</span><span class="sxs-lookup"><span data-stu-id="10c32-138">Click **Edit settings**, make the changes that you want, and then click **Apply**.</span></span>  

<span data-ttu-id="10c32-139">Ou, você também pode fazer o seguinte:</span><span class="sxs-lookup"><span data-stu-id="10c32-139">Or, you can also do the following:</span></span>

1. <span data-ttu-id="10c32-140">Na navegação à esquerda do centro de administração do Microsoft Teams, **vá para políticas do teams**  >  **Teams**.</span><span class="sxs-lookup"><span data-stu-id="10c32-140">In the left navigation of the Microsoft Teams admin center, go to **Teams** > **Teams policies**.</span></span>
2. <span data-ttu-id="10c32-141">Escolha a política clicando à esquerda do nome da política.</span><span class="sxs-lookup"><span data-stu-id="10c32-141">Select the policy by clicking to the left of the policy name.</span></span>
3. <span data-ttu-id="10c32-142">Escolha **Gerenciar usuários**.</span><span class="sxs-lookup"><span data-stu-id="10c32-142">Select **Manage users**.</span></span>
4. <span data-ttu-id="10c32-143">No painel **Gerenciar usuários**, procure o usuário pelo nome de exibição ou pelo nome de usuário, escolha o nome e marque **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="10c32-143">In the **Manage users** pane, search for the user by display name or by user name, select the name, and then select **Add**.</span></span> <span data-ttu-id="10c32-144">Repita esta etapa para cada usuário que você deseja adicionar.</span><span class="sxs-lookup"><span data-stu-id="10c32-144">Repeat this step for each user that you want to add.</span></span>
5. <span data-ttu-id="10c32-145">Quando tiver terminado de adicionar usuários, clique em **salvar**.</span><span class="sxs-lookup"><span data-stu-id="10c32-145">When you're finished adding users, click **Save**.</span></span>

### <a name="assign-a-custom-teams-policy-to-users-in-a-group"></a><span data-ttu-id="10c32-146">Atribuir uma política personalizada do teams a usuários em um grupo</span><span class="sxs-lookup"><span data-stu-id="10c32-146">Assign a custom teams policy to users in a group</span></span>

<span data-ttu-id="10c32-147">Você pode querer atribuir uma política personalizada do teams a vários usuários que você já tenha identificado.</span><span class="sxs-lookup"><span data-stu-id="10c32-147">You may want to assign a custom teams policy to multiple users that you've already identified.</span></span> <span data-ttu-id="10c32-148">Por exemplo, você pode querer atribuir uma política a todos os usuários de um grupo de segurança.</span><span class="sxs-lookup"><span data-stu-id="10c32-148">For example, you may want to assign a policy to all users in a security group.</span></span> <span data-ttu-id="10c32-149">Você pode fazer isso conectando-se ao módulo do PowerShell do Azure Active Directory e ao módulo do PowerShell do Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="10c32-149">You can do this by connecting to the Azure Active Directory PowerShell for Graph module and the Skype for Business PowerShell module.</span></span> <span data-ttu-id="10c32-150">Para obter mais informações sobre como usar o PowerShell para gerenciar o Microsoft Teams, consulte [visão geral do teams PowerShell](teams-powershell-overview.md).</span><span class="sxs-lookup"><span data-stu-id="10c32-150">For more information about using PowerShell to manage Teams, see [Teams PowerShell Overview](teams-powershell-overview.md).</span></span>

<span data-ttu-id="10c32-151">Neste exemplo, atribuímos uma política de equipe chamada política de equipe de marketing a todos os usuários do grupo de marketing da contoso.</span><span class="sxs-lookup"><span data-stu-id="10c32-151">In this example, we assign a teams policy called Marketing Teams Policy to all users in the Contoso Marketing group.</span></span>  

> [!NOTE]
> <span data-ttu-id="10c32-152">Verifique se você se conectou primeiro ao módulo do PowerShell do Azure Active Directory e do módulo do PowerShell do Skype for Business seguindo as etapas em [conectar a todos os serviços do Microsoft 365 ou do Office 365 em uma única janela do Windows PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-all-office-365-services-in-a-single-windows-powershell-window).</span><span class="sxs-lookup"><span data-stu-id="10c32-152">Make sure you first connect to the Azure Active Directory PowerShell for Graph module and Skype for Business PowerShell module by following the steps in [Connect to all Microsoft 365 or Office 365 services in a single Windows PowerShell window](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-all-office-365-services-in-a-single-windows-powershell-window).</span></span>

<span data-ttu-id="10c32-153">Obtenha o GroupObjectId do grupo específico.</span><span class="sxs-lookup"><span data-stu-id="10c32-153">Get the GroupObjectId of the particular group.</span></span>
```PowerShell
$group = Get-AzureADGroup -SearchString "Contoso Marketing"
```
<span data-ttu-id="10c32-154">Obter os membros do grupo especificado.</span><span class="sxs-lookup"><span data-stu-id="10c32-154">Get the members of the specified group.</span></span>
```PowerShell
$members = Get-AzureADGroupMember -ObjectId $group.ObjectId -All $true | Where-Object {$_.ObjectType -eq "User"}
```
<span data-ttu-id="10c32-155">Atribua todos os usuários do grupo a uma política específica do teams.</span><span class="sxs-lookup"><span data-stu-id="10c32-155">Assign all users in the group to a particular teams policy.</span></span> <span data-ttu-id="10c32-156">Neste exemplo, a política de equipe de marketing.</span><span class="sxs-lookup"><span data-stu-id="10c32-156">In this example, it's Marketing Teams Policy.</span></span>
```PowerShell
$members | ForEach-Object { Grant-CsTeamsChannelsPolicy -PolicyName "Marketing Teams Policy" -Identity $_.UserPrincipalName}
``` 
<span data-ttu-id="10c32-157">Dependendo do número de membros do grupo, esse comando pode levar alguns minutos para ser executado.</span><span class="sxs-lookup"><span data-stu-id="10c32-157">Depending on the number of members in the group, this command may take several minutes to execute.</span></span>

## <a name="related-topics"></a><span data-ttu-id="10c32-158">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="10c32-158">Related topics</span></span>

- [<span data-ttu-id="10c32-159">Gerenciar a descoberta de equipes privadas no Teams</span><span class="sxs-lookup"><span data-stu-id="10c32-159">Manage discovery of private teams in Teams</span></span>](manage-discovery-of-private-teams.md)
- [<span data-ttu-id="10c32-160">Canais privados no Teams</span><span class="sxs-lookup"><span data-stu-id="10c32-160">Private channels in Teams</span></span>](private-channels.md)
- [<span data-ttu-id="10c32-161">Atribuir políticas a seus usuários no Teams</span><span class="sxs-lookup"><span data-stu-id="10c32-161">Assign policies to your users in Teams</span></span>](assign-policies.md)
