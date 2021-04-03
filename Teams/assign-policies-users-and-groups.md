---
title: Atribuir políticas a usuários e grupos
author: KarliStites
ms.author: kastites
ms.reviewer: tomkau, saragava, ritikag, jastark
manager: serdars
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
description: Saiba as diferentes maneiras de atribuir políticas a usuários e grupos no Microsoft Teams.
f1keywords:
- ms.teamsadmincenter.bulkoperations.users.edit
- ms.teamsadmincenter.bulkoperations.edit
ms.openlocfilehash: 6b0db8c3da93e561bf374b32d08750d705ded8a2
ms.sourcegitcommit: 2bb8556650120b4f7cf509d8ff93d7e4d058829b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/02/2021
ms.locfileid: "51574287"
---
# <a name="assign-policies-to-users-and-groups"></a><span data-ttu-id="b8fe0-103">Atribuir políticas a usuários e grupos</span><span class="sxs-lookup"><span data-stu-id="b8fe0-103">Assign policies to users and groups</span></span>

<span data-ttu-id="b8fe0-104">Este artigo analisa as diferentes maneiras de atribuir políticas a usuários e grupos no Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="b8fe0-104">This article reviews the different ways to assign policies to users and groups in Microsoft Teams.</span></span> <span data-ttu-id="b8fe0-105">Antes de ler, certifique-se de que você leu [Atribuir políticas no Teams - começando.](policy-assignment-overview.md)</span><span class="sxs-lookup"><span data-stu-id="b8fe0-105">Before reading, be sure you've read [Assign policies in Teams - getting started](policy-assignment-overview.md).</span></span>

## <a name="assign-a-policy-to-individual-users"></a><span data-ttu-id="b8fe0-106">Atribuir uma política a usuários individuais</span><span class="sxs-lookup"><span data-stu-id="b8fe0-106">Assign a policy to individual users</span></span>

<span data-ttu-id="b8fe0-107">Siga estas etapas para atribuir uma política a um usuário individual ou a um pequeno número de usuários por vez.</span><span class="sxs-lookup"><span data-stu-id="b8fe0-107">Follow these steps to assign a policy to an individual user or to a small number of users at a time.</span></span>

### <a name="use-the-microsoft-teams-admin-center"></a><span data-ttu-id="b8fe0-108">Usar o centro de administração do Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="b8fe0-108">Use the Microsoft Teams admin center</span></span>

<span data-ttu-id="b8fe0-109">Para atribuir uma política a um usuário:</span><span class="sxs-lookup"><span data-stu-id="b8fe0-109">To assign a policy to a user:</span></span>

1. <span data-ttu-id="b8fe0-110">Na navegação à esquerda do centro de administração do Microsoft Teams, vá para **Usuários** e selecione o usuário.</span><span class="sxs-lookup"><span data-stu-id="b8fe0-110">In the left navigation of the Microsoft Teams admin center, go to **Users**, and then select the user.</span></span>
2. <span data-ttu-id="b8fe0-111">Selecione o usuário clicando à esquerda do nome do usuário e selecione **Editar configurações**.</span><span class="sxs-lookup"><span data-stu-id="b8fe0-111">Select the user by clicking to the left of the user name, and then select **Edit settings**.</span></span>
3. <span data-ttu-id="b8fe0-112">Selecione a política que deseja atribuir e selecione **Aplicar**.</span><span class="sxs-lookup"><span data-stu-id="b8fe0-112">Select the policy you want to assign, and then select **Apply**.</span></span>

![Atribuir uma política a um usuário no centro de administração do Teams](media/assign-policy-user.png)

<span data-ttu-id="b8fe0-114">Ou você também pode fazer o seguinte:</span><span class="sxs-lookup"><span data-stu-id="b8fe0-114">Or, you can also do the following:</span></span>

1. <span data-ttu-id="b8fe0-115">Na navegação à esquerda do Centro de administração do Microsoft Teams, vá para a página de política.</span><span class="sxs-lookup"><span data-stu-id="b8fe0-115">In the left navigation of the Microsoft Teams admin center, go to the policy page.</span></span>
2. <span data-ttu-id="b8fe0-116">Selecione a política que você deseja atribuir clicando à esquerda do nome da política.</span><span class="sxs-lookup"><span data-stu-id="b8fe0-116">Select the policy you want to assign by clicking to the left of the policy name.</span></span>
3. <span data-ttu-id="b8fe0-117">Escolha **Gerenciar usuários**.</span><span class="sxs-lookup"><span data-stu-id="b8fe0-117">Select **Manage users**.</span></span>
4. <span data-ttu-id="b8fe0-118">No painel **Gerenciar usuários**, procure o usuário pelo nome de exibição ou pelo nome de usuário, escolha o nome e marque **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="b8fe0-118">In the **Manage users** pane, search for the user by display name or by user name, select the name, and then select **Add**.</span></span> <span data-ttu-id="b8fe0-119">Repita esta etapa para cada usuário que você deseja adicionar.</span><span class="sxs-lookup"><span data-stu-id="b8fe0-119">Repeat this step for each user that you want to add.</span></span>
5. <span data-ttu-id="b8fe0-120">Quando terminar de adicionar usuários, selecione **Aplicar**.</span><span class="sxs-lookup"><span data-stu-id="b8fe0-120">When you're finished adding users, select **Apply**.</span></span>

![Atribuir uma política a um usuário no centro de administração do Teams por meio do segundo método](media/assign-policy-user2.png)

### <a name="use-powershell"></a><span data-ttu-id="b8fe0-122">Usar o PowerShell</span><span class="sxs-lookup"><span data-stu-id="b8fe0-122">Use PowerShell</span></span>

<span data-ttu-id="b8fe0-123">Cada tipo de política tem seu próprio conjunto de cmdlets para gere-lo.</span><span class="sxs-lookup"><span data-stu-id="b8fe0-123">Each policy type has its own set of cmdlets for managing it.</span></span> <span data-ttu-id="b8fe0-124">Use o ```Grant-``` cmdlet para um determinado tipo de política para atribuir a política.</span><span class="sxs-lookup"><span data-stu-id="b8fe0-124">Use the ```Grant-``` cmdlet for a given policy type to assign the policy.</span></span> <span data-ttu-id="b8fe0-125">Por exemplo, use o ```Grant-CsTeamsMeetingPolicy``` cmdlet para atribuir uma política de reunião do Teams aos usuários.</span><span class="sxs-lookup"><span data-stu-id="b8fe0-125">For example, use the ```Grant-CsTeamsMeetingPolicy``` cmdlet to assign a Teams meeting policy to users.</span></span> <span data-ttu-id="b8fe0-126">Esses cmdlets estão incluídos no módulo do Teams PowerShell e estão documentados na [referência de cmdlet](https://docs.microsoft.com/powershell/skype)do Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="b8fe0-126">These cmdlets are included in the Teams PowerShell module and are documented in the [Skype for Business cmdlet reference](https://docs.microsoft.com/powershell/skype).</span></span>

 <span data-ttu-id="b8fe0-127">Baixe e instale o lançamento público do [Teams PowerShell](https://www.powershellgallery.com/packages/MicrosoftTeams/) (caso ainda não tenha feito isso) e execute o seguinte para se conectar.</span><span class="sxs-lookup"><span data-stu-id="b8fe0-127">Download and install the [Teams PowerShell public release](https://www.powershellgallery.com/packages/MicrosoftTeams/) (if you haven't already), and then run the following to connect.</span></span>

> [!NOTE]
> <span data-ttu-id="b8fe0-128">O Conector Skype for Business Online atualmente faz parte do módulo mais recente do PowerShell do Teams.</span><span class="sxs-lookup"><span data-stu-id="b8fe0-128">Skype for Business Online Connector is currently part of the latest Teams PowerShell module.</span></span>
>
> <span data-ttu-id="b8fe0-129">Se você estiver usando a versão pública mais recente do [Teams PowerShell,](https://www.powershellgallery.com/packages/MicrosoftTeams/)não será necessário instalar o Conector do Skype for Business Online.</span><span class="sxs-lookup"><span data-stu-id="b8fe0-129">If you're using the latest [Teams PowerShell public release](https://www.powershellgallery.com/packages/MicrosoftTeams/), you don't need to install the Skype for Business Online Connector.</span></span>

```powershell
  # When using Teams PowerShell Module

   Import-Module MicrosoftTeams
   $credential = Get-Credential
   Connect-MicrosoftTeams -Credential $credential
```

<span data-ttu-id="b8fe0-130">Neste exemplo, atribuímos uma política de reunião do Teams chamada Diretiva de Reunião de Alunos a um usuário chamado Reda.</span><span class="sxs-lookup"><span data-stu-id="b8fe0-130">In this example, we assign a Teams meeting policy named Student Meeting Policy to a user named Reda.</span></span>

```powershell
Grant-CsTeamsMeetingPolicy -Identity reda@contoso.com -PolicyName "Student Meeting Policy"
```

<span data-ttu-id="b8fe0-131">Para saber mais, leia [Gerenciar políticas por meio do PowerShell](teams-powershell-managing-teams.md#manage-policies-via-powershell).</span><span class="sxs-lookup"><span data-stu-id="b8fe0-131">To learn more, read [Manage policies via PowerShell](teams-powershell-managing-teams.md#manage-policies-via-powershell).</span></span>

## <a name="assign-a-policy-to-a-group"></a><span data-ttu-id="b8fe0-132">Atribuir uma política a um grupo</span><span class="sxs-lookup"><span data-stu-id="b8fe0-132">Assign a policy to a group</span></span>

<span data-ttu-id="b8fe0-133">A atribuição de política a grupos permite atribuir uma política a um grupo de usuários, como um grupo de segurança ou uma lista de distribuição.</span><span class="sxs-lookup"><span data-stu-id="b8fe0-133">Policy assignment to groups lets you assign a policy to a group of users, such as a security group or distribution list.</span></span> <span data-ttu-id="b8fe0-134">As atribuições de política serão propagadas para os membros do grupo, de acordo com as regras de precedência.</span><span class="sxs-lookup"><span data-stu-id="b8fe0-134">The policy assignment is propagated to members of the group according to precedence rules.</span></span> <span data-ttu-id="b8fe0-135">À medida que os membros forem adicionados ou removidos de um grupo, as atribuições de política herdadas serão atualizadas.</span><span class="sxs-lookup"><span data-stu-id="b8fe0-135">As members are added to or removed from a group, their inherited policy assignments are updated accordingly.</span></span>

<span data-ttu-id="b8fe0-136">A atribuição de política a grupos é recomendada para grupos de até 50.000 usuários, mas também funcionará com grupos maiores.</span><span class="sxs-lookup"><span data-stu-id="b8fe0-136">Policy assignment to groups is recommended for groups of up to 50,000 users but it will also work with larger groups.</span></span>

<span data-ttu-id="b8fe0-137">Quando você atribui a política, ela é imediatamente atribuída ao grupo.</span><span class="sxs-lookup"><span data-stu-id="b8fe0-137">When you assign the policy, it's immediately assigned to the group.</span></span> <span data-ttu-id="b8fe0-138">No entanto, a propagação da atribuição de política aos membros do grupo é executada como uma operação em segundo plano e pode levar algum tempo, dependendo do tamanho do grupo.</span><span class="sxs-lookup"><span data-stu-id="b8fe0-138">However, the propagation of the policy assignment to members of the group is performed as a background operation and might take some time, depending on the size of the group.</span></span> <span data-ttu-id="b8fe0-139">O mesmo acontece quando uma política não é atribuída a um grupo ou quando os membros são adicionados ou removidos de um grupo.</span><span class="sxs-lookup"><span data-stu-id="b8fe0-139">The same is true when a policy is unassigned from a group, or when members are added to or removed from a group.</span></span>

<span data-ttu-id="b8fe0-140">As atribuições de política de grupo são propagadas apenas para usuários que são membros diretos do grupo.</span><span class="sxs-lookup"><span data-stu-id="b8fe0-140">Group policy assignments are only propagated to users who are direct members of the group.</span></span> <span data-ttu-id="b8fe0-141">As atribuições não são propagadas para membros de grupos aninhados.</span><span class="sxs-lookup"><span data-stu-id="b8fe0-141">The assignments aren't propagated to members of nested groups.</span></span>

### <a name="what-you-need-to-know-about-policy-assignment-to-groups"></a><span data-ttu-id="b8fe0-142">O que você precisa saber sobre a atribuição de política a grupos</span><span class="sxs-lookup"><span data-stu-id="b8fe0-142">What you need to know about policy assignment to groups</span></span>

<span data-ttu-id="b8fe0-143">Antes de começar, é importante entender as regras de precedência e a classificação de atribuição de grupo.</span><span class="sxs-lookup"><span data-stu-id="b8fe0-143">Before you get started, it's important to understand precedence rules and group assignment ranking.</span></span>

#### <a name="precedence-rules"></a><span data-ttu-id="b8fe0-144">Regras de precedência</span><span class="sxs-lookup"><span data-stu-id="b8fe0-144">Precedence rules</span></span>

<span data-ttu-id="b8fe0-145">Para um determinado tipo de política, a política efetiva de um usuário é determinada de acordo com o seguinte:</span><span class="sxs-lookup"><span data-stu-id="b8fe0-145">For a given policy type, a user's effective policy is determined according to the following:</span></span>

- <span data-ttu-id="b8fe0-146">Uma política atribuída diretamente a um usuário tem precedência sobre qualquer outra política do mesmo tipo atribuída a um grupo.</span><span class="sxs-lookup"><span data-stu-id="b8fe0-146">A policy that's directly assigned to a user takes precedence over any other policy of the same type that's assigned to a group.</span></span> <span data-ttu-id="b8fe0-147">Em outras palavras, se um usuário receber diretamente uma política de um determinado tipo, esse usuário não herdará uma política do mesmo tipo de um grupo.</span><span class="sxs-lookup"><span data-stu-id="b8fe0-147">In other words, if a user is directly assigned a policy of a given type, that user won't inherit a policy of the same type from a group.</span></span> <span data-ttu-id="b8fe0-148">Isso também significa que, se um usuário tiver uma política de um determinado tipo atribuído diretamente a ele, você terá que remover essa política do usuário antes que ele possa herdar uma política do mesmo tipo de um grupo.</span><span class="sxs-lookup"><span data-stu-id="b8fe0-148">This also means that if a user has a policy of a given type that was directly assigned to them, you have to remove that policy from the user before they can inherit a policy of the same type from a group.</span></span>
- <span data-ttu-id="b8fe0-149">Se um usuário não tiver uma política atribuída diretamente a ele e for membro de dois ou mais grupos e cada grupo tiver uma política do mesmo tipo atribuído a ela, o usuário herdará a política da atribuição de grupo com a classificação mais alta.</span><span class="sxs-lookup"><span data-stu-id="b8fe0-149">If a user doesn't have a policy directly assigned to them and is a member of two or more groups and each group has a policy of the same type assigned to it, the user inherits the policy of the group assignment that has the highest ranking.</span></span>
- <span data-ttu-id="b8fe0-150">Se um usuário não for membro de nenhum grupo atribuído a uma política, a política global (padrão em toda a organização) para esse tipo de política se aplica ao usuário.</span><span class="sxs-lookup"><span data-stu-id="b8fe0-150">If a user isn't a member of any groups that are assigned a policy, the global (Org-wide default) policy for that policy type applies to the user.</span></span>

<span data-ttu-id="b8fe0-151">A política efetiva de um usuário é atualizada de acordo com estas regras:</span><span class="sxs-lookup"><span data-stu-id="b8fe0-151">A user's effective policy is updated according to these rules:</span></span>

- <span data-ttu-id="b8fe0-152">quando um usuário é adicionado ou removido de um grupo atribuído a uma política.</span><span class="sxs-lookup"><span data-stu-id="b8fe0-152">when a user is added to or removed from a group that's assigned a policy.</span></span>
- <span data-ttu-id="b8fe0-153">uma política não é atribuída a partir de um grupo.</span><span class="sxs-lookup"><span data-stu-id="b8fe0-153">a policy is unassigned from a group.</span></span>
- <span data-ttu-id="b8fe0-154">uma política atribuída diretamente ao usuário é removida.</span><span class="sxs-lookup"><span data-stu-id="b8fe0-154">a policy that's directly assigned to the user is removed.</span></span>

#### <a name="group-assignment-ranking"></a><span data-ttu-id="b8fe0-155">Classificação de atribuição de grupo</span><span class="sxs-lookup"><span data-stu-id="b8fe0-155">Group assignment ranking</span></span>

<span data-ttu-id="b8fe0-156">Quando você atribui uma política a um grupo, especifica uma classificação para a atribuição de grupo.</span><span class="sxs-lookup"><span data-stu-id="b8fe0-156">When you assign a policy to a group, you specify a ranking for the group assignment.</span></span> <span data-ttu-id="b8fe0-157">Isso é usado para determinar qual política um usuário deve herdar como sua política efetiva se o usuário for membro de dois ou mais grupos e cada grupo receber uma política do mesmo tipo.</span><span class="sxs-lookup"><span data-stu-id="b8fe0-157">This is used to determine which policy a user should inherit as their effective policy if the user is a member of two or more groups and each group is assigned a policy of the same type.</span></span>

<span data-ttu-id="b8fe0-158">A classificação de atribuição de grupo é relativa a outras atribuições de grupo do mesmo tipo.</span><span class="sxs-lookup"><span data-stu-id="b8fe0-158">The group assignment ranking is relative to other group assignments of the same type.</span></span> <span data-ttu-id="b8fe0-159">Por exemplo, se você estiver atribuindo uma política de chamada a dois grupos, de definir a classificação de uma atribuição como 1 e a outra como 2, sendo 1 a classificação mais alta.</span><span class="sxs-lookup"><span data-stu-id="b8fe0-159">For example, if you're assigning a calling policy to two groups, set the ranking of one assignment to 1 and the other to 2, with 1 being the highest ranking.</span></span> <span data-ttu-id="b8fe0-160">A classificação de atribuição de grupo indica qual associação de grupo é mais importante ou mais relevante do que outras associações de grupo em relação à herança.</span><span class="sxs-lookup"><span data-stu-id="b8fe0-160">The group assignment ranking indicates which group membership is more important or more relevant than other group memberships with regards to inheritance.</span></span>

<span data-ttu-id="b8fe0-161">Por exemplo, você tem dois grupos, Funcionários da Loja e Gerentes da Loja.</span><span class="sxs-lookup"><span data-stu-id="b8fe0-161">Say, for example, you have two groups, Store Employees and Store Managers.</span></span> <span data-ttu-id="b8fe0-162">Ambos os grupos são atribuídos a uma política de chamada do Teams, a Política de Chamada de Funcionários da Loja e a Política de Chamada de Gerentes de Loja, respectivamente.</span><span class="sxs-lookup"><span data-stu-id="b8fe0-162">Both groups are assigned a Teams calling policy, Store Employees Calling Policy and Store Managers Calling Policy, respectively.</span></span> <span data-ttu-id="b8fe0-163">Para um gerente de loja que está em ambos os grupos, sua função como gerente é mais relevante do que sua função como funcionário, portanto, a política de chamada atribuída ao grupo Gerentes de Loja deve ter uma classificação mais alta.</span><span class="sxs-lookup"><span data-stu-id="b8fe0-163">For a store manager who is in both groups, their role as a manager is more relevant than their role as an employee, so the calling policy that's assigned to the Store Managers group should have a higher ranking.</span></span>

|<span data-ttu-id="b8fe0-164">Grupo</span><span class="sxs-lookup"><span data-stu-id="b8fe0-164">Group</span></span> |<span data-ttu-id="b8fe0-165">Nome da política de chamada do Teams</span><span class="sxs-lookup"><span data-stu-id="b8fe0-165">Teams calling policy name</span></span>  |<span data-ttu-id="b8fe0-166">Classificação</span><span class="sxs-lookup"><span data-stu-id="b8fe0-166">Rank</span></span>|
|---------|---------|---|
|<span data-ttu-id="b8fe0-167">Gerentes da Loja</span><span class="sxs-lookup"><span data-stu-id="b8fe0-167">Store Managers</span></span>   |<span data-ttu-id="b8fe0-168">Política de Chamada de Gerentes de Loja</span><span class="sxs-lookup"><span data-stu-id="b8fe0-168">Store Managers Calling Policy</span></span>         |<span data-ttu-id="b8fe0-169">1</span><span class="sxs-lookup"><span data-stu-id="b8fe0-169">1</span></span>|
|<span data-ttu-id="b8fe0-170">Funcionários da Loja</span><span class="sxs-lookup"><span data-stu-id="b8fe0-170">Store Employees</span></span>    |<span data-ttu-id="b8fe0-171">Política de Chamada de Funcionários da Loja</span><span class="sxs-lookup"><span data-stu-id="b8fe0-171">Store Employees Calling Policy</span></span>      |<span data-ttu-id="b8fe0-172">2</span><span class="sxs-lookup"><span data-stu-id="b8fe0-172">2</span></span>|

<span data-ttu-id="b8fe0-173">Se você não especificar uma classificação, a atribuição de política recebe a classificação mais baixa.</span><span class="sxs-lookup"><span data-stu-id="b8fe0-173">If you don't specify a ranking, the policy assignment is given the lowest ranking.</span></span>

### <a name="in-the-teams-admin-center"></a><span data-ttu-id="b8fe0-174">No centro de administração do Teams</span><span class="sxs-lookup"><span data-stu-id="b8fe0-174">In the Teams admin center</span></span>

> [!NOTE]
> <span data-ttu-id="b8fe0-175">Atualmente, a atribuição de política a grupos usando o Centro de administração do Microsoft Teams está disponível apenas para a política de chamada do Teams, política de estacionamento de chamada do Teams, política do Teams, política de eventos ao vivo do Teams, política de reunião do Teams e política de mensagens do Teams.</span><span class="sxs-lookup"><span data-stu-id="b8fe0-175">Currently, policy assignment to groups using the Microsoft Teams admin center is only available for Teams calling policy, Teams call park policy, Teams policy, Teams live events policy, Teams meeting policy, and Teams messaging policy.</span></span> <span data-ttu-id="b8fe0-176">Para outros tipos de política, use o PowerShell.</span><span class="sxs-lookup"><span data-stu-id="b8fe0-176">For other policy types, use PowerShell.</span></span>

1. <span data-ttu-id="b8fe0-177">Na navegação à esquerda do centro de administração do Microsoft Teams, vá para a página tipo de política.</span><span class="sxs-lookup"><span data-stu-id="b8fe0-177">In the left navigation of the Microsoft Teams admin center, go to the policy type page.</span></span> <span data-ttu-id="b8fe0-178">Por exemplo, vá para **Políticas de Reunião** de  >  **Reuniões.**</span><span class="sxs-lookup"><span data-stu-id="b8fe0-178">For example, go to **Meetings** > **Meeting policies**.</span></span>
2. <span data-ttu-id="b8fe0-179">Selecione a **guia Atribuição de política de** grupo.</span><span class="sxs-lookup"><span data-stu-id="b8fe0-179">Select the **Group policy assignment** tab.</span></span>
3. <span data-ttu-id="b8fe0-180">Selecione **Adicionar grupo** e, em seguida, no painel Atribuir **política** ao grupo, faça o seguinte:</span><span class="sxs-lookup"><span data-stu-id="b8fe0-180">Select **Add group**, and then in the **Assign policy to group** pane, do the following:</span></span>
    1. <span data-ttu-id="b8fe0-181">Pesquise e adicione o grupo ao que você deseja atribuir a política.</span><span class="sxs-lookup"><span data-stu-id="b8fe0-181">Search for and add the group you want to assign the policy to.</span></span>
    2. <span data-ttu-id="b8fe0-182">De definir a classificação para a atribuição de grupo.</span><span class="sxs-lookup"><span data-stu-id="b8fe0-182">Set the ranking for the group assignment.</span></span>
    3. <span data-ttu-id="b8fe0-183">Selecione a política que você deseja atribuir.</span><span class="sxs-lookup"><span data-stu-id="b8fe0-183">Select the policy that you want to assign.</span></span>
    4. <span data-ttu-id="b8fe0-184">Selecione **Aplicar**.</span><span class="sxs-lookup"><span data-stu-id="b8fe0-184">Select **Apply**.</span></span>
    
![Atribuir uma política a um grupo no centro de administração do Teams](media/assign-policy-group.png)

<span data-ttu-id="b8fe0-186">Para remover uma atribuição de política de grupo, na **guia** Atribuição de política de grupo da página de política, selecione a atribuição de grupo e selecione **Remover**.</span><span class="sxs-lookup"><span data-stu-id="b8fe0-186">To remove a group policy assignment, on the **Group policy assignment** tab of the policy page, select the group assignment, and then select **Remove**.</span></span>

<span data-ttu-id="b8fe0-187">Para alterar a classificação de uma atribuição de grupo, você precisa primeiro remover a atribuição de política de grupo.</span><span class="sxs-lookup"><span data-stu-id="b8fe0-187">To change the ranking of a group assignment, you have to first remove the group policy assignment.</span></span> <span data-ttu-id="b8fe0-188">Em seguida, siga as etapas acima para atribuir a política a um grupo.</span><span class="sxs-lookup"><span data-stu-id="b8fe0-188">Then, follow the steps above to assign the policy to a group.</span></span>

### <a name="use-the-powershell-option"></a><span data-ttu-id="b8fe0-189">Usar a opção PowerShell</span><span class="sxs-lookup"><span data-stu-id="b8fe0-189">Use the PowerShell option</span></span>

> [!NOTE]
> <span data-ttu-id="b8fe0-190">Atualmente, a atribuição de política a grupos usando o PowerShell não está disponível para todos os tipos de política do Teams.</span><span class="sxs-lookup"><span data-stu-id="b8fe0-190">Currently, policy assignment to groups using PowerShell isn't available for all Teams policy types.</span></span> <span data-ttu-id="b8fe0-191">Consulte [New-CsGroupPolicyAssignment para](https://docs.microsoft.com/powershell/module/teams/new-csgrouppolicyassignment) a lista de tipos de política com suporte.</span><span class="sxs-lookup"><span data-stu-id="b8fe0-191">See [New-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/new-csgrouppolicyassignment) for the list of supported policy types.</span></span>

#### <a name="install-and-connect-to-the-microsoft-teams-powershell-module"></a><span data-ttu-id="b8fe0-192">Instalar e conectar-se ao módulo do Microsoft Teams PowerShell</span><span class="sxs-lookup"><span data-stu-id="b8fe0-192">Install and connect to the Microsoft Teams PowerShell module</span></span>

<span data-ttu-id="b8fe0-193">Para obter orientações passo a passo, consulte [Install Teams PowerShell](teams-powershell-install.md).</span><span class="sxs-lookup"><span data-stu-id="b8fe0-193">For step-by-step guidance, see [Install Teams PowerShell](teams-powershell-install.md).</span></span>

#### <a name="assign-a-policy-to-a-group-of-users"></a><span data-ttu-id="b8fe0-194">Atribuir uma política a um grupo de usuários</span><span class="sxs-lookup"><span data-stu-id="b8fe0-194">Assign a policy to a group of users</span></span>

<span data-ttu-id="b8fe0-195">Use o cmdlet [New-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/new-csgrouppolicyassignment) para atribuir uma política a um grupo.</span><span class="sxs-lookup"><span data-stu-id="b8fe0-195">Use the [New-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/new-csgrouppolicyassignment) cmdlet to assign a policy to a group.</span></span> <span data-ttu-id="b8fe0-196">Você pode especificar um grupo usando a ID do objeto, endereço SIP ou endereço de email.</span><span class="sxs-lookup"><span data-stu-id="b8fe0-196">You can specify a group by using the object ID, SIP address, or email address.</span></span>

<span data-ttu-id="b8fe0-197">Neste exemplo, atribuímos uma política de reunião do Teams chamada Política de Reunião de Gerentes de Varejo a um grupo com uma classificação de atribuição de 1.</span><span class="sxs-lookup"><span data-stu-id="b8fe0-197">In this example, we assign a Teams meeting policy named Retail Managers Meeting Policy to a group with an assignment ranking of 1.</span></span>

```powershell
New-CsGroupPolicyAssignment -GroupId d8ebfa45-0f28-4d2d-9bcc-b158a49e2d17 -PolicyType TeamsMeetingPolicy -PolicyName "Retail Managers Meeting Policy" -Rank 1
```

#### <a name="get-policy-assignments-for-a-group"></a><span data-ttu-id="b8fe0-198">Obter atribuições de política para um grupo</span><span class="sxs-lookup"><span data-stu-id="b8fe0-198">Get policy assignments for a group</span></span>

<span data-ttu-id="b8fe0-199">Use o cmdlet [Get-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/get-csgrouppolicyassignment) para obter todas as políticas atribuídas a um grupo.</span><span class="sxs-lookup"><span data-stu-id="b8fe0-199">Use the [Get-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/get-csgrouppolicyassignment) cmdlet to get all policies assigned to a group.</span></span> <span data-ttu-id="b8fe0-200">Observe que os grupos sempre são listados pela ID do grupo, mesmo que seu endereço SIP ou endereço de email seja usado para atribuir a política.</span><span class="sxs-lookup"><span data-stu-id="b8fe0-200">Note that groups are always listed by their group ID even if its SIP address or email address was used to assign the policy.</span></span>

<span data-ttu-id="b8fe0-201">Neste exemplo, recuperamos todas as políticas atribuídas a um grupo específico.</span><span class="sxs-lookup"><span data-stu-id="b8fe0-201">In this example, we retrieve all policies assigned to a specific group.</span></span>

```powershell
Get-CsGroupPolicyAssignment -GroupId e050ce51-54bc-45b7-b3e6-c00343d31274
```

<span data-ttu-id="b8fe0-202">Neste exemplo, retornamos todos os grupos atribuídos a uma política de reunião do Teams.</span><span class="sxs-lookup"><span data-stu-id="b8fe0-202">In this example, we return all groups that are assigned a Teams meeting policy.</span></span>

```powershell
Get-CsGroupPolicyAssignment -PolicyType TeamsMeetingPolicy
```

#### <a name="remove-a-policy-from-a-group"></a><span data-ttu-id="b8fe0-203">Remover uma política de um grupo</span><span class="sxs-lookup"><span data-stu-id="b8fe0-203">Remove a policy from a group</span></span>

<span data-ttu-id="b8fe0-204">Use o cmdlet [Remove-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/remove-csgrouppolicyassignment) para remover uma política de um grupo.</span><span class="sxs-lookup"><span data-stu-id="b8fe0-204">Use the [Remove-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/remove-csgrouppolicyassignment) cmdlet to remove a policy from a group.</span></span> <span data-ttu-id="b8fe0-205">Quando você remove uma política de um grupo, as prioridades de outras políticas do mesmo tipo atribuído a esse grupo, e que têm uma classificação mais baixa, são atualizadas.</span><span class="sxs-lookup"><span data-stu-id="b8fe0-205">When you remove a policy from a group, the priorities of other policies of the same type assigned to that group, and that have a lower ranking, are updated.</span></span> <span data-ttu-id="b8fe0-206">Por exemplo, se você remover uma política que tenha uma classificação de 2, as políticas que têm uma classificação de 3 e 4 serão atualizadas para refletir sua nova classificação.</span><span class="sxs-lookup"><span data-stu-id="b8fe0-206">For example, if you remove a policy that has a ranking of 2, policies that have a ranking of 3 and 4 are updated to reflect their new ranking.</span></span> <span data-ttu-id="b8fe0-207">As duas tabelas a seguir mostram este exemplo.</span><span class="sxs-lookup"><span data-stu-id="b8fe0-207">The following two tables show this example.</span></span>

<span data-ttu-id="b8fe0-208">Aqui está uma lista das atribuições de política e prioridades para uma política de reunião do Teams.</span><span class="sxs-lookup"><span data-stu-id="b8fe0-208">Here's a list of the policy assignments and priorities for a Teams meeting policy.</span></span>

|<span data-ttu-id="b8fe0-209">Nome do grupo</span><span class="sxs-lookup"><span data-stu-id="b8fe0-209">Group name</span></span>  |<span data-ttu-id="b8fe0-210">Nome da política</span><span class="sxs-lookup"><span data-stu-id="b8fe0-210">Policy name</span></span>  |<span data-ttu-id="b8fe0-211">Classificação</span><span class="sxs-lookup"><span data-stu-id="b8fe0-211">Rank</span></span>|
|---------|---------|---------|
|<span data-ttu-id="b8fe0-212">Vendas</span><span class="sxs-lookup"><span data-stu-id="b8fe0-212">Sales</span></span>    |<span data-ttu-id="b8fe0-213">Política de vendas</span><span class="sxs-lookup"><span data-stu-id="b8fe0-213">Sales policy</span></span>       | <span data-ttu-id="b8fe0-214">1</span><span class="sxs-lookup"><span data-stu-id="b8fe0-214">1</span></span>        |
|<span data-ttu-id="b8fe0-215">Região Oeste</span><span class="sxs-lookup"><span data-stu-id="b8fe0-215">West Region</span></span>     |<span data-ttu-id="b8fe0-216">Política da Região Oeste</span><span class="sxs-lookup"><span data-stu-id="b8fe0-216">West Region policy</span></span>         |<span data-ttu-id="b8fe0-217">2</span><span class="sxs-lookup"><span data-stu-id="b8fe0-217">2</span></span>         |
|<span data-ttu-id="b8fe0-218">Division</span><span class="sxs-lookup"><span data-stu-id="b8fe0-218">Division</span></span>    |<span data-ttu-id="b8fe0-219">Política de divisão</span><span class="sxs-lookup"><span data-stu-id="b8fe0-219">Division policy</span></span>         |<span data-ttu-id="b8fe0-220">3</span><span class="sxs-lookup"><span data-stu-id="b8fe0-220">3</span></span>         |
|<span data-ttu-id="b8fe0-221">Subsidiária</span><span class="sxs-lookup"><span data-stu-id="b8fe0-221">Subsidiary</span></span>   |<span data-ttu-id="b8fe0-222">Política de subsidiária</span><span class="sxs-lookup"><span data-stu-id="b8fe0-222">Subsidiary policy</span></span>        |<span data-ttu-id="b8fe0-223">4</span><span class="sxs-lookup"><span data-stu-id="b8fe0-223">4</span></span>         |

<span data-ttu-id="b8fe0-224">Se removermos a política da Região Oeste do grupo da Região Oeste, as atribuições e prioridades de política serão atualizadas da seguinte forma.</span><span class="sxs-lookup"><span data-stu-id="b8fe0-224">If we remove the West Region policy from the West Region group, the policy assignments and priorities are updated as follows.</span></span>

|<span data-ttu-id="b8fe0-225">Nome do grupo</span><span class="sxs-lookup"><span data-stu-id="b8fe0-225">Group name</span></span>  |<span data-ttu-id="b8fe0-226">Nome da política</span><span class="sxs-lookup"><span data-stu-id="b8fe0-226">Policy name</span></span>  |<span data-ttu-id="b8fe0-227">Classificação</span><span class="sxs-lookup"><span data-stu-id="b8fe0-227">Rank</span></span>|
|---------|---------|---------|
|<span data-ttu-id="b8fe0-228">Vendas</span><span class="sxs-lookup"><span data-stu-id="b8fe0-228">Sales</span></span>    |<span data-ttu-id="b8fe0-229">Política de vendas</span><span class="sxs-lookup"><span data-stu-id="b8fe0-229">Sales policy</span></span>       | <span data-ttu-id="b8fe0-230">1</span><span class="sxs-lookup"><span data-stu-id="b8fe0-230">1</span></span>        |
|<span data-ttu-id="b8fe0-231">Division</span><span class="sxs-lookup"><span data-stu-id="b8fe0-231">Division</span></span>    |<span data-ttu-id="b8fe0-232">Política de divisão</span><span class="sxs-lookup"><span data-stu-id="b8fe0-232">Division policy</span></span>         |<span data-ttu-id="b8fe0-233">2</span><span class="sxs-lookup"><span data-stu-id="b8fe0-233">2</span></span>         |
|<span data-ttu-id="b8fe0-234">Subsidiária</span><span class="sxs-lookup"><span data-stu-id="b8fe0-234">Subsidiary</span></span>   |<span data-ttu-id="b8fe0-235">Política de subsidiária</span><span class="sxs-lookup"><span data-stu-id="b8fe0-235">Subsidiary policy</span></span>        |<span data-ttu-id="b8fe0-236">3</span><span class="sxs-lookup"><span data-stu-id="b8fe0-236">3</span></span>        |

<span data-ttu-id="b8fe0-237">Neste exemplo, removemos a política de reunião do Teams de um grupo.</span><span class="sxs-lookup"><span data-stu-id="b8fe0-237">In this example, we remove the Teams meeting policy from a group.</span></span>

```powershell
Remove-CsGroupPolicyAssignment -PolicyType TeamsMeetingPolicy -GroupId f985e013-0826-40bb-8c94-e5f367076044
```

#### <a name="change-a-policy-assignment-for-a-group"></a><span data-ttu-id="b8fe0-238">Alterar uma atribuição de política para um grupo</span><span class="sxs-lookup"><span data-stu-id="b8fe0-238">Change a policy assignment for a group</span></span>

> [!NOTE]
> <span data-ttu-id="b8fe0-239">O cmdlet [Set-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/set-csgrouppolicyassignment) estará disponível em breve.</span><span class="sxs-lookup"><span data-stu-id="b8fe0-239">The [Set-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/set-csgrouppolicyassignment) cmdlet will be available soon.</span></span> <span data-ttu-id="b8fe0-240">Enquanto isso, para alterar uma atribuição de política de grupo, você pode remover a atribuição de política atual do grupo e adicionar uma nova atribuição de política.</span><span class="sxs-lookup"><span data-stu-id="b8fe0-240">In the meantime, to change a group policy assignment, you can remove the current policy assignment from the group, and then add a new policy assignment.</span></span>

<span data-ttu-id="b8fe0-241">Depois de atribuir uma política a um grupo, você pode usar o cmdlet [Set-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/set-csgrouppolicyassignment) para alterar a atribuição de política desse grupo da seguinte forma:</span><span class="sxs-lookup"><span data-stu-id="b8fe0-241">After you assign a policy to a group, you can use the [Set-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/set-csgrouppolicyassignment) cmdlet to change that group's policy assignment as follows:</span></span>

- <span data-ttu-id="b8fe0-242">Alterar a classificação</span><span class="sxs-lookup"><span data-stu-id="b8fe0-242">Change the ranking</span></span>
- <span data-ttu-id="b8fe0-243">Alterar a política de um determinado tipo de política</span><span class="sxs-lookup"><span data-stu-id="b8fe0-243">Change the policy of a given policy type</span></span>
- <span data-ttu-id="b8fe0-244">Alterar a política de um determinado tipo de política e a classificação</span><span class="sxs-lookup"><span data-stu-id="b8fe0-244">Change the policy of a given policy type and the ranking</span></span>

<span data-ttu-id="b8fe0-245">Neste exemplo, alteramos a política de estacionamento de chamada do Teams de um grupo para uma política chamada SupportCallPark e a classificação de atribuição como 3.</span><span class="sxs-lookup"><span data-stu-id="b8fe0-245">In this example, we change a group's Teams call park policy to a policy named SupportCallPark and the assignment ranking to 3.</span></span>

```powershell
Set-CsGroupPolicyAssignment -GroupId 566b8d39-5c5c-4aaa-bc07-4f36278a1b38 -PolicyType TeamsMeetingPolicy -PolicyName SupportCallPark -Rank 3
```

#### <a name="change-the-effective-policy-for-a-user"></a><span data-ttu-id="b8fe0-246">Alterar a política efetiva para um usuário</span><span class="sxs-lookup"><span data-stu-id="b8fe0-246">Change the effective policy for a user</span></span>

<span data-ttu-id="b8fe0-247">Aqui está um exemplo de como alterar a política efetiva para um usuário que recebe diretamente uma política.</span><span class="sxs-lookup"><span data-stu-id="b8fe0-247">Here's an example of how to change the effective policy for a user who is directly assigned a policy.</span></span>

<span data-ttu-id="b8fe0-248">Primeiro, usamos o cmdlet [Get-CsUserPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/get-csuserpolicyassignment) juntamente com o parâmetro para obter detalhes das políticas de transmissão de reunião do Teams associadas ao ```PolicySource``` usuário.</span><span class="sxs-lookup"><span data-stu-id="b8fe0-248">First, we use the [Get-CsUserPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/get-csuserpolicyassignment) cmdlet together with the ```PolicySource``` parameter to get details of the Teams meeting broadcast policies associated with the user.</span></span>

```powershell
Get-CsUserPolicyAssignment -Identity daniel@contoso.com -PolicyType TeamsMeetingBroadcastPolicy | select -ExpandProperty PolicySource
```

<span data-ttu-id="b8fe0-249">A saída mostra que o usuário recebeu diretamente uma política de transmissão de reunião do Teams chamada Eventos de Funcionários, que tem precedência sobre a política chamada Vendor Live Events atribuída a um grupo ao qual o usuário pertence.</span><span class="sxs-lookup"><span data-stu-id="b8fe0-249">The output shows that the user was directly assigned a Teams meeting broadcast policy named Employee Events, which takes precedence over the policy named Vendor Live Events that's assigned to a group the user belongs to.</span></span>

```console
AssignmentType PolicyName         Reference
-------------- ----------         ---------
Direct         Employee Events
Group          Vendor Live Events 566b8d39-5c5c-4aaa-bc07-4f36278a1b38
```

<span data-ttu-id="b8fe0-250">Agora, removemos a política Eventos de Funcionários do usuário.</span><span class="sxs-lookup"><span data-stu-id="b8fe0-250">Now, we remove the Employee Events policy from the user.</span></span> <span data-ttu-id="b8fe0-251">Isso significa que o usuário não tem mais uma política de transmissão de reunião do Teams atribuída diretamente a ele e herdará a política eventos ao vivo do fornecedor atribuída ao grupo ao que o usuário pertence.</span><span class="sxs-lookup"><span data-stu-id="b8fe0-251">This means that the user no longer has a Teams meeting broadcast policy directly assigned to them and will inherit the Vendor Live Events policy that's assigned to the group the user belongs to.</span></span>

<span data-ttu-id="b8fe0-252">Use o cmdlet a seguir no módulo do PowerShell do Skype for Business para fazer isso.</span><span class="sxs-lookup"><span data-stu-id="b8fe0-252">Use the following cmdlet in the Skype for Business PowerShell module to do this.</span></span>

```powershell
Grant-CsTeamsMeetingBroadcastPolicy -Identity daniel@contoso.com -PolicyName $null
```

<span data-ttu-id="b8fe0-253">Use o cmdlet a seguir no módulo do PowerShell do Teams para fazer isso em escala, embora uma atribuição de política em lotes, onde $users é uma lista de usuários que você especificar.</span><span class="sxs-lookup"><span data-stu-id="b8fe0-253">Use following cmdlet in the Teams PowerShell module to do this at scale though a batch policy assignment, where $users is a list of users that you specify.</span></span>

```powershell
New-CsBatchPolicyAssignmentOperation -OperationName "Assigning null at bulk" -PolicyType TeamsMeetingBroadcastPolicy -PolicyName $null -Identity $users  
```

## <a name="assign-a-policy-to-a-batch-of-users"></a><span data-ttu-id="b8fe0-254">Atribuir uma política a um lote de usuários</span><span class="sxs-lookup"><span data-stu-id="b8fe0-254">Assign a policy to a batch of users</span></span>

### <a name="use-the-admin-center"></a><span data-ttu-id="b8fe0-255">Usar o centro de administração</span><span class="sxs-lookup"><span data-stu-id="b8fe0-255">Use the admin center</span></span>

<span data-ttu-id="b8fe0-256">Para atribuir uma política aos usuários em massa:</span><span class="sxs-lookup"><span data-stu-id="b8fe0-256">To assign a policy to users in bulk:</span></span>

1. <span data-ttu-id="b8fe0-257">Na navegação à esquerda do centro de administração do Microsoft Teams, selecione **Usuários**.</span><span class="sxs-lookup"><span data-stu-id="b8fe0-257">In the left navigation of the Microsoft Teams admin center, select **Users**.</span></span>
2. <span data-ttu-id="b8fe0-258">Pesquise os usuários aos que você deseja atribuir a política ou filtre a exibição para mostrar os usuários que você deseja.</span><span class="sxs-lookup"><span data-stu-id="b8fe0-258">Search for the users you want to assign the policy to or filter the view to show the users you want.</span></span>
3. <span data-ttu-id="b8fe0-259">Na coluna **&#x2713;** (marca de seleção), selecione os usuários.</span><span class="sxs-lookup"><span data-stu-id="b8fe0-259">In the **&#x2713;** (check mark) column, select the users.</span></span> <span data-ttu-id="b8fe0-260">Para selecionar todos os usuários, clique na (marca de seleção) &#x2713; na parte superior da tabela.</span><span class="sxs-lookup"><span data-stu-id="b8fe0-260">To select all users, click the &#x2713; (check mark) at the top of the table.</span></span>
4. <span data-ttu-id="b8fe0-261">Selecione **Editar configurações,** faça as alterações que você deseja e selecione **Aplicar**.</span><span class="sxs-lookup"><span data-stu-id="b8fe0-261">Select **Edit settings**, make the changes that you want, and then select **Apply**.</span></span>

<span data-ttu-id="b8fe0-262">Para exibir o status da atribuição de política, na  faixa que  aparece na parte superior da página Usuários depois de selecionar Aplicar para enviar sua atribuição de política, selecione Log **de atividades.**</span><span class="sxs-lookup"><span data-stu-id="b8fe0-262">To view the status of your policy assignment, in the banner that appears at the top of the **Users** page after you select **Apply** to submit your policy assignment, select **Activity log**.</span></span> <span data-ttu-id="b8fe0-263">Ou, na navegação à esquerda do centro de administração do Microsoft Teams, vá para **Painel** e, em log de **atividades,** selecione **Exibir detalhes.**</span><span class="sxs-lookup"><span data-stu-id="b8fe0-263">Or, in the left navigation of the Microsoft Teams admin center, go to **Dashboard**, and then under **Activity log**, select **View details**.</span></span> <span data-ttu-id="b8fe0-264">O log de atividades mostra atribuições de política para lotes de mais de 20 usuários por meio do Centro de administração do Microsoft Teams dos últimos 30 dias.</span><span class="sxs-lookup"><span data-stu-id="b8fe0-264">The Activity log shows policy assignments to batches of more than 20 users through the Microsoft Teams admin center from the last 30 days.</span></span> <span data-ttu-id="b8fe0-265">Para saber mais, confira [Exibir suas atribuições de política no log de atividades](activity-log.md).</span><span class="sxs-lookup"><span data-stu-id="b8fe0-265">To learn more, see [View your policy assignments in the Activity log](activity-log.md).</span></span>

### <a name="use-powershell-method"></a><span data-ttu-id="b8fe0-266">Usar o método PowerShell</span><span class="sxs-lookup"><span data-stu-id="b8fe0-266">Use PowerShell method</span></span>

> [!NOTE]
> <span data-ttu-id="b8fe0-267">Atualmente, a atribuição de política em lote usando o PowerShell não está disponível para todos os tipos de política do Teams.</span><span class="sxs-lookup"><span data-stu-id="b8fe0-267">Currently, batch policy assignment using PowerShell isn't available for all Teams policy types.</span></span> <span data-ttu-id="b8fe0-268">Consulte [New-CsBatchPolicyAssignmentOperation para](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation) ver a lista de tipos de política com suporte.</span><span class="sxs-lookup"><span data-stu-id="b8fe0-268">See [New-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation) for the list of supported policy types.</span></span>

<span data-ttu-id="b8fe0-269">Com a atribuição de política em lote, você pode atribuir uma política a grandes conjuntos de usuários por vez sem precisar usar um script.</span><span class="sxs-lookup"><span data-stu-id="b8fe0-269">With batch policy assignment, you can assign a policy to large sets of users at a time without having to use a script.</span></span> <span data-ttu-id="b8fe0-270">Você usa o cmdlet [New-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation) para enviar um lote de usuários e a política que deseja atribuir.</span><span class="sxs-lookup"><span data-stu-id="b8fe0-270">You use the [New-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation) cmdlet to submit a batch of users and the policy that you want to assign.</span></span> <span data-ttu-id="b8fe0-271">As atribuições são processadas como uma operação de plano de fundo e uma ID de operação é gerada para cada lote.</span><span class="sxs-lookup"><span data-stu-id="b8fe0-271">The assignments are processed as a background operation and an operation ID is generated for each batch.</span></span> <span data-ttu-id="b8fe0-272">Em seguida, você pode usar o cmdlet [Get-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/get-csbatchpolicyassignmentoperation) para rastrear o progresso e o status das atribuições em um lote.</span><span class="sxs-lookup"><span data-stu-id="b8fe0-272">You can then use the [Get-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/get-csbatchpolicyassignmentoperation) cmdlet to track the progress and status of the assignments in a batch.</span></span>

<span data-ttu-id="b8fe0-273">Especifique os usuários por sua ID de objeto ou endereço SIP (Session Initiation Protocol).</span><span class="sxs-lookup"><span data-stu-id="b8fe0-273">Specify users by their object ID or Session Initiation Protocol (SIP) address.</span></span> <span data-ttu-id="b8fe0-274">O endereço SIP de um usuário geralmente tem o mesmo valor que o UPN (Nome principal do usuário) ou o endereço de email, mas isso não é necessário.</span><span class="sxs-lookup"><span data-stu-id="b8fe0-274">A user's SIP address often has the same value as the User Principal Name (UPN) or email address, but this is not required.</span></span> <span data-ttu-id="b8fe0-275">Se um usuário for especificado usando seu UPN ou email, mas tiver um valor diferente do endereço SIP, a atribuição de política falhará para o usuário.</span><span class="sxs-lookup"><span data-stu-id="b8fe0-275">If a user is specified using their UPN or email, but it has a different value than their SIP address, then policy assignment will fail for the user.</span></span> <span data-ttu-id="b8fe0-276">Se um lote incluir usuários duplicados, as duplicatas serão removidas do lote antes do processamento e o status só será fornecido para os usuários exclusivos restantes no lote.</span><span class="sxs-lookup"><span data-stu-id="b8fe0-276">If a batch includes duplicate users, the duplicates will be removed from the batch before processing and status will only be provided for the unique users remaining in the batch.</span></span>

<span data-ttu-id="b8fe0-277">Um lote pode conter até 5.000 usuários.</span><span class="sxs-lookup"><span data-stu-id="b8fe0-277">A batch can contain up to 5,000 users.</span></span> <span data-ttu-id="b8fe0-278">Para obter melhores resultados, não envie mais de alguns lotes por vez.</span><span class="sxs-lookup"><span data-stu-id="b8fe0-278">For best results, don't submit more than a few batches at a time.</span></span> <span data-ttu-id="b8fe0-279">Permitir que lotes concluam o processamento antes de enviar mais lotes.</span><span class="sxs-lookup"><span data-stu-id="b8fe0-279">Allow batches to complete processing before submitting more batches.</span></span>

#### <a name="install-and-connect-to-the-teams-powershell-module"></a><span data-ttu-id="b8fe0-280">Instalar e conectar-se ao módulo do Teams PowerShell</span><span class="sxs-lookup"><span data-stu-id="b8fe0-280">Install and connect to the Teams PowerShell module</span></span>

<span data-ttu-id="b8fe0-281">Execute o seguinte para instalar o [módulo do Microsoft Teams PowerShell](https://www.powershellgallery.com/packages/MicrosoftTeams).</span><span class="sxs-lookup"><span data-stu-id="b8fe0-281">Run the following to install the [Microsoft Teams PowerShell module](https://www.powershellgallery.com/packages/MicrosoftTeams).</span></span> <span data-ttu-id="b8fe0-282">Instale a versão 1.0.5 ou posterior.</span><span class="sxs-lookup"><span data-stu-id="b8fe0-282">Make sure you install version 1.0.5 or later.</span></span>

```powershell
Install-Module -Name MicrosoftTeams
```

<span data-ttu-id="b8fe0-283">Execute o seguinte para se conectar ao Teams e iniciar uma sessão.</span><span class="sxs-lookup"><span data-stu-id="b8fe0-283">Run the following to connect to Teams and start a session.</span></span>

```powershell
Connect-MicrosoftTeams
```

<span data-ttu-id="b8fe0-284">Quando for solicitado, entre usando suas credenciais de administrador.</span><span class="sxs-lookup"><span data-stu-id="b8fe0-284">When you're prompted, sign in using your admin credentials.</span></span>

#### <a name="install-and-connect-to-the-azure-ad-powershell-for-graph-module-optional"></a><span data-ttu-id="b8fe0-285">Instalar e conectar ao módulo powershell do Azure AD para Graph (opcional)</span><span class="sxs-lookup"><span data-stu-id="b8fe0-285">Install and connect to the Azure AD PowerShell for Graph module (optional)</span></span>

<span data-ttu-id="b8fe0-286">Você também pode baixar e instalar o módulo do [Azure AD PowerShell para Graph](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2) (se ainda não o fez) e se conectar ao Azure AD para que possa recuperar uma lista de usuários em sua organização.</span><span class="sxs-lookup"><span data-stu-id="b8fe0-286">You might also want to [download and install the Azure AD PowerShell for Graph module](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2) (if you haven't already) and connect to Azure AD so that you can retrieve a list of users in your organization.</span></span>

<span data-ttu-id="b8fe0-287">Execute o seguinte para se conectar ao Azure AD.</span><span class="sxs-lookup"><span data-stu-id="b8fe0-287">Run the following to connect to Azure AD.</span></span>

```powershell
Connect-AzureAD
```

<span data-ttu-id="b8fe0-288">Quando for solicitado, entre usando as mesmas credenciais de administrador que você usou para se conectar ao Teams.</span><span class="sxs-lookup"><span data-stu-id="b8fe0-288">When you're prompted, sign in using the same admin credentials that you used to connect to Teams.</span></span>

#### <a name="assign-a-setup-policy-to-a-batch-of-users"></a><span data-ttu-id="b8fe0-289">Atribuir uma política de instalação a um lote de usuários</span><span class="sxs-lookup"><span data-stu-id="b8fe0-289">Assign a setup policy to a batch of users</span></span>

<span data-ttu-id="b8fe0-290">Neste exemplo, usamos o cmdlet [New-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation) para atribuir uma política de configuração de aplicativo chamada Política de Configuração de Aplicativo de RH a um lote de usuários listados no arquivo Users_ids.text.</span><span class="sxs-lookup"><span data-stu-id="b8fe0-290">In this example, we use the [New-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation) cmdlet to assign an app setup policy named HR App Setup Policy to a batch of users listed in the Users_ids.text file.</span></span>

```powershell
$user_ids = Get-Content .\users_ids.txt
New-CsBatchPolicyAssignmentOperation -PolicyType TeamsAppSetupPolicy -PolicyName "HR App Setup Policy" -Identity $users_ids -OperationName "Example 1 batch"
```

<span data-ttu-id="b8fe0-291">Neste exemplo, nos conectamos ao Azure AD para recuperar uma coleção de usuários e atribuir uma política de mensagens chamada New Hire Messaging Policy a um lote de usuários especificado usando seu endereço SIP.</span><span class="sxs-lookup"><span data-stu-id="b8fe0-291">In this example, we connect to Azure AD to retrieve a collection of users and then assign a messaging policy named New Hire Messaging Policy to a batch of users specified by using their SIP address.</span></span>

```powershell
Connect-AzureAD
$users = Get-AzureADUser
New-CsBatchPolicyAssignmentOperation -PolicyType TeamsMessagingPolicy -PolicyName "New Hire Messaging Policy" -Identity $users.SipProxyAddress -OperationName "Example 2 batch"
```

#### <a name="get-the-status-of-a-batch-assignment"></a><span data-ttu-id="b8fe0-292">Obter o status de uma atribuição em lotes</span><span class="sxs-lookup"><span data-stu-id="b8fe0-292">Get the status of a batch assignment</span></span>

<span data-ttu-id="b8fe0-293">Execute o seguinte para obter o status de uma atribuição em lotes, onde OperationId é a ID da operação retornada pelo ```New-CsBatchPolicyAssignmentOperation``` cmdlet para um determinado lote.</span><span class="sxs-lookup"><span data-stu-id="b8fe0-293">Run the following to get the status of a batch assignment, where OperationId is the operation ID that's returned by the ```New-CsBatchPolicyAssignmentOperation``` cmdlet for a given batch.</span></span>

```powershell
$Get-CsBatchPolicyAssignmentOperation -OperationId f985e013-0826-40bb-8c94-e5f367076044 | fl
```

<span data-ttu-id="b8fe0-294">Se a saída mostrar que ocorreu um erro, execute o seguinte para obter mais informações sobre erros, que estão na ```UserState``` propriedade.</span><span class="sxs-lookup"><span data-stu-id="b8fe0-294">If the output shows that an error occurred, run the following to get more information about errors, which are in the ```UserState``` property.</span></span>

```powershell
Get-CsBatchPolicyAssignmentOperation -OperationId f985e013-0826-40bb-8c94-e5f367076044 | Select -ExpandProperty UserState
```

<span data-ttu-id="b8fe0-295">Para saber mais, confira [Get-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/get-csbatchpolicyassignmentoperation).</span><span class="sxs-lookup"><span data-stu-id="b8fe0-295">To learn more, see [Get-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/get-csbatchpolicyassignmentoperation).</span></span>

## <a name="related-topics"></a><span data-ttu-id="b8fe0-296">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="b8fe0-296">Related topics</span></span>

- [<span data-ttu-id="b8fe0-297">Gerenciar o Teams com políticas</span><span class="sxs-lookup"><span data-stu-id="b8fe0-297">Manage Teams with policies</span></span>](manage-teams-with-policies.md)
- [<span data-ttu-id="b8fe0-298">Visão Geral do PowerShell do Teams</span><span class="sxs-lookup"><span data-stu-id="b8fe0-298">Teams PowerShell Overview</span></span>](teams-powershell-overview.md)
- [<span data-ttu-id="b8fe0-299">Atribuir políticas no Teams - iniciando</span><span class="sxs-lookup"><span data-stu-id="b8fe0-299">Assign policies in Teams - getting started</span></span>](policy-assignment-overview.md)
