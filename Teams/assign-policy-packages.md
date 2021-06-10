---
title: Atribuir pacotes de política a usuários e grupos
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
description: Saiba as diferentes maneiras de atribuir pacotes de política a usuários e grupos em Microsoft Teams.
f1keywords:
- ms.teamsadmincenter.bulkoperations.users.edit
- ms.teamsadmincenter.bulkoperations.edit
ms.openlocfilehash: 820cc280e7168dee5a0e059005a1b7e6cebf5ff1
ms.sourcegitcommit: 36bc47b2b9ee0e738fa814c31accacfe816da4a3
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/09/2021
ms.locfileid: "52856420"
---
# <a name="assign-policy-packages-to-users-and-groups"></a><span data-ttu-id="7af3b-103">Atribuir pacotes de política a usuários e grupos</span><span class="sxs-lookup"><span data-stu-id="7af3b-103">Assign policy packages to users and groups</span></span>

<span data-ttu-id="7af3b-104">Este artigo analisa as diferentes maneiras de atribuir pacotes de política a usuários e grupos em Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="7af3b-104">This article reviews the different ways to assign policy packages to users and groups in Microsoft Teams.</span></span> <span data-ttu-id="7af3b-105">Antes de ler, certifique-se de ler [Atribuir políticas em](policy-assignment-overview.md)Teams - começando .</span><span class="sxs-lookup"><span data-stu-id="7af3b-105">Before reading, be sure you've read [Assign policies in Teams - getting started](policy-assignment-overview.md).</span></span>

> [!NOTE]
> <span data-ttu-id="7af3b-106">Cada usuário exigirá o complemento de Comunicações Avançadas para receber uma atribuição de pacote de políticas personalizadas.</span><span class="sxs-lookup"><span data-stu-id="7af3b-106">Each user will require the Advanced Communications add-on in order to receive a custom policy package assignment.</span></span> <span data-ttu-id="7af3b-107">Para obter mais informações, consulte [Complemento de Comunicações Avançadas para o Microsoft Teams ](/microsoftteams/teams-add-on-licensing/advanced-communications).</span><span class="sxs-lookup"><span data-stu-id="7af3b-107">For more information, see [Advanced Communications add-on for Microsoft Teams](/microsoftteams/teams-add-on-licensing/advanced-communications).</span></span>

## <a name="assign-a-policy-package-to-users"></a><span data-ttu-id="7af3b-108">Atribuir um pacote de política aos usuários</span><span class="sxs-lookup"><span data-stu-id="7af3b-108">Assign a policy package to users</span></span>

<span data-ttu-id="7af3b-109">Um pacote de política no Teams é uma coleção de políticas e configurações de política predefinidas que você pode atribuir aos usuários que têm as mesmas funções ou funções semelhantes em sua organização.</span><span class="sxs-lookup"><span data-stu-id="7af3b-109">A policy package in Teams is a collection of predefined policies and policy settings that you can assign to users who have the same or similar roles in your organization.</span></span> <span data-ttu-id="7af3b-110">Cada pacote de política é projetado em torno de uma função de usuário e inclui políticas predefinidas e configurações de política que suportam atividades típicas para essa função.</span><span class="sxs-lookup"><span data-stu-id="7af3b-110">Each policy package is designed around a user role and includes predefined policies and policy settings that support activities typical for that role.</span></span> <span data-ttu-id="7af3b-111">Alguns exemplos de pacotes de política são o pacote Educação (Professor) e o pacote Assistência Médica (Trabalho Médico).</span><span class="sxs-lookup"><span data-stu-id="7af3b-111">Some examples of policy packages are the Education (Teacher) package and Healthcare (Clinical worker) package.</span></span> <span data-ttu-id="7af3b-112">Para saber mais, confira [Gerenciar pacotes de política em Teams](manage-policy-packages.md).</span><span class="sxs-lookup"><span data-stu-id="7af3b-112">To learn more, see [Manage policy packages in Teams](manage-policy-packages.md).</span></span>

### <a name="assign-a-policy-package-to-one-user"></a><span data-ttu-id="7af3b-113">Atribuir um pacote de política a um usuário</span><span class="sxs-lookup"><span data-stu-id="7af3b-113">Assign a policy package to one user</span></span>

1. <span data-ttu-id="7af3b-114">Na navegação à esquerda do centro de administração Microsoft Teams, vá para **Usuários** e selecione o usuário.</span><span class="sxs-lookup"><span data-stu-id="7af3b-114">In the left navigation of the Microsoft Teams admin center, go to **Users**, and then select the user.</span></span>
2. <span data-ttu-id="7af3b-115">Na página do usuário, selecione **Políticas** e, ao lado de **Pacote de Política,** selecione **Editar**.</span><span class="sxs-lookup"><span data-stu-id="7af3b-115">On the user's page, select **Policies**, and then next to **Policy package**, select **Edit**.</span></span>
3. <span data-ttu-id="7af3b-116">No painel **Atribuir pacote de** política, selecione o pacote que você deseja atribuir e selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="7af3b-116">In the **Assign policy package** pane, select the package you want to assign, and then select **Save**.</span></span>

![Teams captura de tela do centro de administração para atribuição de pacote de política a um usuário](media/assign-policypackages-user.png)

### <a name="assign-a-policy-package-to-multiple-users"></a><span data-ttu-id="7af3b-118">Atribuir um pacote de política a vários usuários</span><span class="sxs-lookup"><span data-stu-id="7af3b-118">Assign a policy package to multiple users</span></span>

1. <span data-ttu-id="7af3b-119">Na navegação à esquerda do centro de administração Microsoft Teams, vá para Pacotes de Política **e** selecione o pacote de política que você deseja atribuir clicando à esquerda do nome do pacote.</span><span class="sxs-lookup"><span data-stu-id="7af3b-119">In the left navigation of the Microsoft Teams admin center, go to **Policy packages**, and then select the policy package you want to assign by clicking to the left of the package name.</span></span>
2. <span data-ttu-id="7af3b-120">Escolha **Gerenciar usuários**.</span><span class="sxs-lookup"><span data-stu-id="7af3b-120">Select **Manage users**.</span></span>
3. <span data-ttu-id="7af3b-121">No painel **Gerenciar usuários**, procure o usuário pelo nome de exibição ou pelo nome de usuário, escolha o nome e marque **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="7af3b-121">In the **Manage users** pane, search for the user by display name or by user name, select the name, and then select **Add**.</span></span> <span data-ttu-id="7af3b-122">Repita esta etapa para cada usuário que você deseja adicionar.</span><span class="sxs-lookup"><span data-stu-id="7af3b-122">Repeat this step for each user that you want to add.</span></span>
4. <span data-ttu-id="7af3b-123">Quando terminar de adicionar usuários, selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="7af3b-123">When you're finished adding users, select **Save**.</span></span>

![Teams captura de tela do centro de administração para atribuição de pacote de política a vários usuários](media/assign-policypackages-multipleusers.png)

## <a name="assign-a-policy-package-to-a-group"></a><span data-ttu-id="7af3b-125">Atribua o pacote de política a um grupo.</span><span class="sxs-lookup"><span data-stu-id="7af3b-125">Assign a policy package to a group</span></span>

<span data-ttu-id="7af3b-126">As atribuições de pacote de política aos grupos permitem atribuir várias políticas a um grupo de usuários, como uma lista de distribuição ou grupo de segurança.</span><span class="sxs-lookup"><span data-stu-id="7af3b-126">Policy package assignment to groups let you assign multiple policies to a group of users, such as a security group or distribution list.</span></span> <span data-ttu-id="7af3b-127">As atribuições de política serão propagadas para os membros do grupo, de acordo com as regras de precedência.</span><span class="sxs-lookup"><span data-stu-id="7af3b-127">The policy assignment is propagated to members of the group according to precedence rules.</span></span> <span data-ttu-id="7af3b-128">À medida que os membros forem adicionados ou removidos de um grupo, as atribuições de política herdadas serão atualizadas.</span><span class="sxs-lookup"><span data-stu-id="7af3b-128">As members are added to or removed from a group, their inherited policy assignments are updated accordingly.</span></span>

<span data-ttu-id="7af3b-129">A atribuição de pacote de política a grupos é recomendada para grupos de até 50.000 usuários, mas também funcionará com grupos maiores.</span><span class="sxs-lookup"><span data-stu-id="7af3b-129">Policy package assignment to groups is recommended for groups of up to 50,000 users, but it will also work with larger groups.</span></span>

<span data-ttu-id="7af3b-130">Quando você atribui o pacote de política, ele é imediatamente atribuído ao grupo.</span><span class="sxs-lookup"><span data-stu-id="7af3b-130">When you assign the policy package, it's immediately assigned to the group.</span></span> <span data-ttu-id="7af3b-131">No entanto, a propagação da atribuição de política aos membros do grupo é executada como uma operação em segundo plano e pode levar algum tempo, dependendo do tamanho do grupo.</span><span class="sxs-lookup"><span data-stu-id="7af3b-131">However, the propagation of the policy assignment to members of the group is performed as a background operation and might take some time, depending on the size of the group.</span></span> <span data-ttu-id="7af3b-132">O mesmo acontece quando uma política não é atribuída a um grupo ou quando os membros são adicionados ou removidos de um grupo.</span><span class="sxs-lookup"><span data-stu-id="7af3b-132">The same is true when a policy is unassigned from a group, or when members are added to or removed from a group.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="7af3b-133">Antes de começar, é importante entender ( regras[de precedência](assign-policies-users-and-groups.md#precedence-rules)) e ( classificação[de atribuição de grupo](assign-policies-users-and-groups.md#group-assignment-ranking)).</span><span class="sxs-lookup"><span data-stu-id="7af3b-133">Before you get started, it's important to understand ([precedence rules](assign-policies-users-and-groups.md#precedence-rules)) and ([group assignment ranking](assign-policies-users-and-groups.md#group-assignment-ranking)).</span></span> <span data-ttu-id="7af3b-134">Leia e entenda os conceitos em ([O que](assign-policies-users-and-groups.md#what-you-need-to-know-about-policy-assignment-to-groups)você precisa saber sobre atribuição de política para grupos ) anteriormente neste artigo.</span><span class="sxs-lookup"><span data-stu-id="7af3b-134">Make sure you read and understand the concepts in ([What you need to know about policy assignment to groups](assign-policies-users-and-groups.md#what-you-need-to-know-about-policy-assignment-to-groups)) earlier in this article.</span></span>

### <a name="assign-a-policy-package-to-a-group-of-users-in-the-admin-center"></a><span data-ttu-id="7af3b-135">Atribuir um pacote de política a um grupo de usuários no centro de administração</span><span class="sxs-lookup"><span data-stu-id="7af3b-135">Assign a policy package to a group of users in the admin center</span></span>

1. <span data-ttu-id="7af3b-136">Entre no Centro de administração do Teams.</span><span class="sxs-lookup"><span data-stu-id="7af3b-136">Sign in to the Teams admin center.</span></span>
2. <span data-ttu-id="7af3b-137">Na navegação à esquerda, vá para a página pacote de política.</span><span class="sxs-lookup"><span data-stu-id="7af3b-137">In the left navigation, go to the policy package page.</span></span>
3. <span data-ttu-id="7af3b-138">Selecione a guia Atribuição de política de grupo.</span><span class="sxs-lookup"><span data-stu-id="7af3b-138">Select the Group policy assignment tab.</span></span>
4. <span data-ttu-id="7af3b-139">Selecione **Adicionar grupo** e, em seguida, no painel Atribuir um pacote de política ao grupo, faça o seguinte:</span><span class="sxs-lookup"><span data-stu-id="7af3b-139">Select **Add group**, and then in the Assign a policy package to group pane, do the following:</span></span>

    <span data-ttu-id="7af3b-140">a.</span><span class="sxs-lookup"><span data-stu-id="7af3b-140">a.</span></span> <span data-ttu-id="7af3b-141">Pesquise e adicione o grupo ao que você deseja atribuir o pacote de política.</span><span class="sxs-lookup"><span data-stu-id="7af3b-141">Search for and add the group you want to assign the policy package to.</span></span>

    <span data-ttu-id="7af3b-142">b.</span><span class="sxs-lookup"><span data-stu-id="7af3b-142">b.</span></span> <span data-ttu-id="7af3b-143">Selecione um pacote de política.</span><span class="sxs-lookup"><span data-stu-id="7af3b-143">Select a policy package.</span></span>

    <span data-ttu-id="7af3b-144">c.</span><span class="sxs-lookup"><span data-stu-id="7af3b-144">c.</span></span> <span data-ttu-id="7af3b-145">De definir a classificação para cada tipo de política.</span><span class="sxs-lookup"><span data-stu-id="7af3b-145">Set the ranking for each policy type.</span></span>

    <span data-ttu-id="7af3b-146">d.</span><span class="sxs-lookup"><span data-stu-id="7af3b-146">d.</span></span> <span data-ttu-id="7af3b-147">Selecione **Aplicar**.</span><span class="sxs-lookup"><span data-stu-id="7af3b-147">Select **Apply**.</span></span>

![mostra a atribuição de política de grupo](media/group-pkg-assignment.png)

5. <span data-ttu-id="7af3b-149">Para gerenciar a classificação de um tipo de política específico, navegue até a página de política específica.</span><span class="sxs-lookup"><span data-stu-id="7af3b-149">To manage ranking for a specific policy type, navigate to the specific policy page.</span></span>
6. <span data-ttu-id="7af3b-150">Para reatribuir um pacote de política a um grupo, primeiro remova a atribuição de política de grupo.</span><span class="sxs-lookup"><span data-stu-id="7af3b-150">To reassign a policy package to a group, first remove the group policy assignment.</span></span> <span data-ttu-id="7af3b-151">Em seguida, siga as etapas acima para atribuir o pacote de política a um grupo.</span><span class="sxs-lookup"><span data-stu-id="7af3b-151">Then, follow the steps above to assign the policy package to a group.</span></span>

### <a name="work-with-powershell"></a><span data-ttu-id="7af3b-152">Trabalhar com o PowerShell</span><span class="sxs-lookup"><span data-stu-id="7af3b-152">Work with PowerShell</span></span>

#### <a name="get-the-teams-powershell-module"></a><span data-ttu-id="7af3b-153">Obter o módulo Teams PowerShell</span><span class="sxs-lookup"><span data-stu-id="7af3b-153">Get the Teams PowerShell module</span></span>

<span data-ttu-id="7af3b-154">Para obter orientações passo a passo, consulte [Install Teams PowerShell](teams-powershell-install.md).</span><span class="sxs-lookup"><span data-stu-id="7af3b-154">For step-by-step guidance, see [Install Teams PowerShell](teams-powershell-install.md).</span></span>

#### <a name="assign-a-policy-package-to-a-group-of-users"></a><span data-ttu-id="7af3b-155">Atribuir um pacote de política a um grupo de usuários</span><span class="sxs-lookup"><span data-stu-id="7af3b-155">Assign a policy package to a group of users</span></span>

<span data-ttu-id="7af3b-156">Use o cmdlet [Grant-CsGroupPolicyPackageAssignment](/powershell/module/teams/grant-csgrouppolicypackageassignment) para atribuir um pacote de política a um grupo.</span><span class="sxs-lookup"><span data-stu-id="7af3b-156">Use the [Grant-CsGroupPolicyPackageAssignment](/powershell/module/teams/grant-csgrouppolicypackageassignment) cmdlet to assign a policy package to a group.</span></span> <span data-ttu-id="7af3b-157">Você pode especificar um grupo usando a ID do objeto, endereço SIP ou endereço de email.</span><span class="sxs-lookup"><span data-stu-id="7af3b-157">You can specify a group by using the object ID, SIP address, or email address.</span></span> <span data-ttu-id="7af3b-158">Ao atribuir o pacote de política, especifique um ( classificação de atribuição de[grupo](assign-policies-users-and-groups.md#group-assignment-ranking)) para cada tipo de política no pacote de política.</span><span class="sxs-lookup"><span data-stu-id="7af3b-158">When you assign the policy package, specify a ([group assignment ranking](assign-policies-users-and-groups.md#group-assignment-ranking)) for each policy type in the policy package.</span></span>

<span data-ttu-id="7af3b-159">Neste exemplo, atribuímos o pacote de política Education_Teacher a um grupo com uma classificação de atribuição de 1 para TeamsAppSetupPolicy e TeamsMeetingBroadcastPolicy e uma classificação de 2 para TeamsMeetingPolicy.</span><span class="sxs-lookup"><span data-stu-id="7af3b-159">In this example, we assign the Education_Teacher policy package to a group with an assignment ranking of 1 for TeamsAppSetupPolicy and TeamsMeetingBroadcastPolicy and a ranking of 2 for TeamsMeetingPolicy.</span></span>

```powershell
Grant-CsGroupPolicyPackageAssignment -GroupId "dae90bb4-120f-4a3e-a15d-30f142e79f69" -PackageName "Education_Teacher" -PolicyRankings "TeamsAppSetupPolicy, 1", "TeamsMeetingBroadcastPolicy, 1", "TeamsMeetingPolicy, 2"
```

## <a name="assign-a-policy-package-to-a-batch-of-users"></a><span data-ttu-id="7af3b-160">Atribuir um pacote de política a um lote de usuários</span><span class="sxs-lookup"><span data-stu-id="7af3b-160">Assign a policy package to a batch of users</span></span>

<span data-ttu-id="7af3b-161">Com a atribuição de pacote de política em lote, você pode atribuir um pacote de política a grandes conjuntos de usuários por vez sem precisar usar um script.</span><span class="sxs-lookup"><span data-stu-id="7af3b-161">With batch policy package assignment, you can assign a policy package to large sets of users at a time without having to use a script.</span></span> <span data-ttu-id="7af3b-162">Use o cmdlet [New-CsBatchPolicyAssignmentOperation](/powershell/module/teams/new-csbatchpolicyassignmentoperation) para enviar um lote de usuários e o pacote de política que você deseja atribuir.</span><span class="sxs-lookup"><span data-stu-id="7af3b-162">You use the [New-CsBatchPolicyAssignmentOperation](/powershell/module/teams/new-csbatchpolicyassignmentoperation) cmdlet to submit a batch of users and the policy package that you want to assign.</span></span> <span data-ttu-id="7af3b-163">As atribuições são processadas como uma operação de plano de fundo e uma ID de operação é gerada para cada lote.</span><span class="sxs-lookup"><span data-stu-id="7af3b-163">The assignments are processed as a background operation and an operation ID is generated for each batch.</span></span> <span data-ttu-id="7af3b-164">Em seguida, você pode usar o cmdlet [Get-CsBatchPolicyAssignmentOperation](/powershell/module/teams/get-csbatchpolicyassignmentoperation) para rastrear o progresso e o status das atribuições em um lote.</span><span class="sxs-lookup"><span data-stu-id="7af3b-164">You can then use the [Get-CsBatchPolicyAssignmentOperation](/powershell/module/teams/get-csbatchpolicyassignmentoperation) cmdlet to track the progress and status of the assignments in a batch.</span></span>

<span data-ttu-id="7af3b-165">Especifique os usuários por sua ID de objeto ou endereço SIP (Session Initiation Protocol).</span><span class="sxs-lookup"><span data-stu-id="7af3b-165">Specify users by their object ID or Session Initiation Protocol (SIP) address.</span></span> <span data-ttu-id="7af3b-166">O endereço SIP de um usuário geralmente tem o mesmo valor que o UPN (Nome principal do usuário) ou o endereço de email, mas isso não é necessário.</span><span class="sxs-lookup"><span data-stu-id="7af3b-166">A user's SIP address often has the same value as the User Principal Name (UPN) or email address, but this isn't required.</span></span> <span data-ttu-id="7af3b-167">Se um usuário for especificado usando seu UPN ou email, mas tiver um valor diferente do endereço SIP, a atribuição de política falhará para o usuário.</span><span class="sxs-lookup"><span data-stu-id="7af3b-167">If a user is specified using their UPN or email, but it has a different value than their SIP address, then policy assignment will fail for the user.</span></span> <span data-ttu-id="7af3b-168">Se um lote incluir usuários duplicados, as duplicatas serão removidas do lote antes do processamento e o status só será fornecido para os usuários exclusivos restantes no lote.</span><span class="sxs-lookup"><span data-stu-id="7af3b-168">If a batch includes duplicate users, the duplicates will be removed from the batch before processing and status will only be provided for the unique users remaining in the batch.</span></span>

<span data-ttu-id="7af3b-169">Um lote contém até 5.000 usuários.</span><span class="sxs-lookup"><span data-stu-id="7af3b-169">A batch contains up to 5,000 users.</span></span> <span data-ttu-id="7af3b-170">Para obter melhores resultados, não envie mais de alguns lotes por vez.</span><span class="sxs-lookup"><span data-stu-id="7af3b-170">For best results, don't submit more than a few batches at a time.</span></span> <span data-ttu-id="7af3b-171">Permitir que lotes concluam o processamento antes de enviar mais lotes.</span><span class="sxs-lookup"><span data-stu-id="7af3b-171">Allow batches to complete processing before submitting more batches.</span></span>

### <a name="use-the-teams-powershell-module"></a><span data-ttu-id="7af3b-172">Usar o módulo Teams PowerShell</span><span class="sxs-lookup"><span data-stu-id="7af3b-172">Use the Teams PowerShell module</span></span>

<span data-ttu-id="7af3b-173">Execute o seguinte para instalar o [Microsoft Teams do PowerShell](https://www.powershellgallery.com/packages/MicrosoftTeams) (caso ainda não tenha feito isso).</span><span class="sxs-lookup"><span data-stu-id="7af3b-173">Run the following to install the [Microsoft Teams PowerShell module](https://www.powershellgallery.com/packages/MicrosoftTeams) (if you haven't already).</span></span> <span data-ttu-id="7af3b-174">Instale a versão 1.0.5 ou posterior.</span><span class="sxs-lookup"><span data-stu-id="7af3b-174">Make sure you install version 1.0.5 or later.</span></span>

```powershell
Install-Module -Name MicrosoftTeams
```

<span data-ttu-id="7af3b-175">Execute o seguinte para se conectar ao Teams e iniciar uma sessão.</span><span class="sxs-lookup"><span data-stu-id="7af3b-175">Run the following to connect to Teams and start a session.</span></span>

```powershell
Connect-MicrosoftTeams
```

<span data-ttu-id="7af3b-176">Quando for solicitado, entre usando suas credenciais de administrador.</span><span class="sxs-lookup"><span data-stu-id="7af3b-176">When you're prompted, sign in using your admin credentials.</span></span>

### <a name="assign-policy-packages-to-a-batch-of-users"></a><span data-ttu-id="7af3b-177">Atribuir pacotes de política a um lote de usuários</span><span class="sxs-lookup"><span data-stu-id="7af3b-177">Assign policy packages to a batch of users</span></span>

<span data-ttu-id="7af3b-178">Neste exemplo, usamos o cmdlet [New-CsBatchPolicyAssignmentOperation](/powershell/module/teams/new-csbatchpolicyassignmentoperation) para atribuir o pacote de política Education_PrimaryStudent a um lote de usuários.</span><span class="sxs-lookup"><span data-stu-id="7af3b-178">In this example, we use the [New-CsBatchPolicyAssignmentOperation](/powershell/module/teams/new-csbatchpolicyassignmentoperation) cmdlet to assign the Education_PrimaryStudent policy package to a batch of users.</span></span>

```powershell
New-CsBatchPolicyPackageAssignmentOperation -Identity 1bc0b35f-095a-4a37-a24c-c4b6049816ab,user1@econtoso.com,user2@contoso.com -PackageName Education_PrimaryStudent
```

### <a name="see-the-status-of-a-batch-assignment"></a><span data-ttu-id="7af3b-179">Consulte o status de uma atribuição em lotes</span><span class="sxs-lookup"><span data-stu-id="7af3b-179">See the status of a batch assignment</span></span>

<span data-ttu-id="7af3b-180">Execute o seguinte para obter o status de uma atribuição em lotes, onde OperationId é a ID da operação retornada pelo ```New-CsBatchPolicyAssignmentOperation``` cmdlet para um determinado lote.</span><span class="sxs-lookup"><span data-stu-id="7af3b-180">Run the following to get the status of a batch assignment, where OperationId is the operation ID that's returned by the ```New-CsBatchPolicyAssignmentOperation``` cmdlet for a given batch.</span></span>

```powershell
$Get-CsBatchPolicyAssignmentOperation -OperationId f985e013-0826-40bb-8c94-e5f367076044 | fl
```

<span data-ttu-id="7af3b-181">Se a saída mostrar que ocorreu um erro, execute o seguinte para obter mais informações sobre erros, que estão na ```UserState``` propriedade.</span><span class="sxs-lookup"><span data-stu-id="7af3b-181">If the output shows that an error occurred, run the following to get more information about errors, which are in the ```UserState``` property.</span></span>

```powershell
Get-CsBatchPolicyAssignmentOperation -OperationId f985e013-0826-40bb-8c94-e5f367076044 | Select -ExpandProperty UserState
```

<span data-ttu-id="7af3b-182">Para saber mais, confira [Get-CsBatchPolicyAssignmentOperation](/powershell/module/teams/get-csbatchpolicyassignmentoperation).</span><span class="sxs-lookup"><span data-stu-id="7af3b-182">To learn more, see [Get-CsBatchPolicyAssignmentOperation](/powershell/module/teams/get-csbatchpolicyassignmentoperation).</span></span>

## <a name="related-topics"></a><span data-ttu-id="7af3b-183">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="7af3b-183">Related topics</span></span>

- [<span data-ttu-id="7af3b-184">Gerenciar Teams com políticas</span><span class="sxs-lookup"><span data-stu-id="7af3b-184">Manage Teams with policies</span></span>](manage-teams-with-policies.md)
- [<span data-ttu-id="7af3b-185">Gerenciar pacotes de política em Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="7af3b-185">Manage policy packages in Microsoft Teams</span></span>](manage-policy-packages.md)
- [<span data-ttu-id="7af3b-186">Visão Geral do PowerShell do Teams</span><span class="sxs-lookup"><span data-stu-id="7af3b-186">Teams PowerShell Overview</span></span>](teams-powershell-overview.md)
- [<span data-ttu-id="7af3b-187">Atribuir políticas em Teams - iniciando</span><span class="sxs-lookup"><span data-stu-id="7af3b-187">Assign policies in Teams - getting started</span></span>](policy-assignment-overview.md)
