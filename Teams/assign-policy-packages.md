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
description: Saiba as diferentes maneiras de atribuir pacotes de política a usuários e grupos no Microsoft Teams.
f1keywords:
- ms.teamsadmincenter.bulkoperations.users.edit
- ms.teamsadmincenter.bulkoperations.edit
ms.openlocfilehash: 0266cb5c34a13df0dac62be2258134e553a357d8
ms.sourcegitcommit: 2bb8556650120b4f7cf509d8ff93d7e4d058829b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/02/2021
ms.locfileid: "51574286"
---
# <a name="assign-policy-packages-to-users-and-groups"></a><span data-ttu-id="347ff-103">Atribuir pacotes de política a usuários e grupos</span><span class="sxs-lookup"><span data-stu-id="347ff-103">Assign policy packages to users and groups</span></span>

<span data-ttu-id="347ff-104">Este artigo analisa as diferentes maneiras de atribuir pacotes de política a usuários e grupos no Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="347ff-104">This article reviews the different ways to assign policy packages to users and groups in Microsoft Teams.</span></span> <span data-ttu-id="347ff-105">Antes de ler, certifique-se de que você leu [Atribuir políticas no Teams - começando.](policy-assignment-overview.md)</span><span class="sxs-lookup"><span data-stu-id="347ff-105">Before reading, be sure you've read [Assign policies in Teams - getting started](policy-assignment-overview.md).</span></span>

## <a name="assign-a-policy-package-to-users"></a><span data-ttu-id="347ff-106">Atribuir um pacote de política aos usuários</span><span class="sxs-lookup"><span data-stu-id="347ff-106">Assign a policy package to users</span></span>

<span data-ttu-id="347ff-107">Um pacote de política no Teams é um conjunto de políticas e configurações de política predefinidas que você pode atribuir aos usuários que têm as mesmas funções ou funções semelhantes em sua organização.</span><span class="sxs-lookup"><span data-stu-id="347ff-107">A policy package in Teams is a collection of predefined policies and policy settings that you can assign to users who have the same or similar roles in your organization.</span></span> <span data-ttu-id="347ff-108">Cada pacote de política é projetado em torno de uma função de usuário e inclui políticas predefinidas e configurações de política que suportam atividades típicas para essa função.</span><span class="sxs-lookup"><span data-stu-id="347ff-108">Each policy package is designed around a user role and includes predefined policies and policy settings that support activities typical for that role.</span></span> <span data-ttu-id="347ff-109">Alguns exemplos de pacotes de política são o pacote Educação (Professor) e o pacote Assistência Médica (Trabalho Médico).</span><span class="sxs-lookup"><span data-stu-id="347ff-109">Some examples of policy packages are the Education (Teacher) package and Healthcare (Clinical worker) package.</span></span> <span data-ttu-id="347ff-110">Para saber mais, confira [Gerenciar pacotes de política no Teams](manage-policy-packages.md).</span><span class="sxs-lookup"><span data-stu-id="347ff-110">To learn more, see [Manage policy packages in Teams](manage-policy-packages.md).</span></span>

### <a name="assign-a-policy-package-to-one-user"></a><span data-ttu-id="347ff-111">Atribuir um pacote de política a um usuário</span><span class="sxs-lookup"><span data-stu-id="347ff-111">Assign a policy package to one user</span></span>

1. <span data-ttu-id="347ff-112">Na navegação à esquerda do centro de administração do Microsoft Teams, vá para **Usuários** e selecione o usuário.</span><span class="sxs-lookup"><span data-stu-id="347ff-112">In the left navigation of the Microsoft Teams admin center, go to **Users**, and then select the user.</span></span>
2. <span data-ttu-id="347ff-113">Na página do usuário, selecione **Políticas** e, ao lado de **Pacote de Política,** selecione **Editar**.</span><span class="sxs-lookup"><span data-stu-id="347ff-113">On the user's page, select **Policies**, and then next to **Policy package**, select **Edit**.</span></span>
3. <span data-ttu-id="347ff-114">No painel **Atribuir pacote de** política, selecione o pacote que você deseja atribuir e selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="347ff-114">In the **Assign policy package** pane, select the package you want to assign, and then select **Save**.</span></span>

![Captura de tela do Centro de administração do Teams para atribuição de pacote de política a um usuário](media/assign-policypackages-user.png)

### <a name="assign-a-policy-package-to-multiple-users"></a><span data-ttu-id="347ff-116">Atribuir um pacote de política a vários usuários</span><span class="sxs-lookup"><span data-stu-id="347ff-116">Assign a policy package to multiple users</span></span>

1. <span data-ttu-id="347ff-117">Na navegação à esquerda do centro de administração do Microsoft Teams, vá para Pacotes de Política **e** selecione o pacote de política que você deseja atribuir clicando à esquerda do nome do pacote.</span><span class="sxs-lookup"><span data-stu-id="347ff-117">In the left navigation of the Microsoft Teams admin center, go to **Policy packages**, and then select the policy package you want to assign by clicking to the left of the package name.</span></span>
2. <span data-ttu-id="347ff-118">Escolha **Gerenciar usuários**.</span><span class="sxs-lookup"><span data-stu-id="347ff-118">Select **Manage users**.</span></span>
3. <span data-ttu-id="347ff-119">No painel **Gerenciar usuários**, procure o usuário pelo nome de exibição ou pelo nome de usuário, escolha o nome e marque **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="347ff-119">In the **Manage users** pane, search for the user by display name or by user name, select the name, and then select **Add**.</span></span> <span data-ttu-id="347ff-120">Repita esta etapa para cada usuário que você deseja adicionar.</span><span class="sxs-lookup"><span data-stu-id="347ff-120">Repeat this step for each user that you want to add.</span></span>
4. <span data-ttu-id="347ff-121">Quando terminar de adicionar usuários, selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="347ff-121">When you're finished adding users, select **Save**.</span></span>

![Captura de tela do Centro de administração do Teams para atribuição de pacote de política a vários usuários](media/assign-policypackages-multipleusers.png)

## <a name="assign-a-policy-package-to-a-group"></a><span data-ttu-id="347ff-123">Atribua o pacote de política a um grupo.</span><span class="sxs-lookup"><span data-stu-id="347ff-123">Assign a policy package to a group</span></span>

<span data-ttu-id="347ff-124">As atribuições de pacote de política aos grupos permitem atribuir várias políticas a um grupo de usuários, como uma lista de distribuição ou grupo de segurança.</span><span class="sxs-lookup"><span data-stu-id="347ff-124">Policy package assignment to groups let you assign multiple policies to a group of users, such as a security group or distribution list.</span></span> <span data-ttu-id="347ff-125">As atribuições de política serão propagadas para os membros do grupo, de acordo com as regras de precedência.</span><span class="sxs-lookup"><span data-stu-id="347ff-125">The policy assignment is propagated to members of the group according to precedence rules.</span></span> <span data-ttu-id="347ff-126">À medida que os membros forem adicionados ou removidos de um grupo, as atribuições de política herdadas serão atualizadas.</span><span class="sxs-lookup"><span data-stu-id="347ff-126">As members are added to or removed from a group, their inherited policy assignments are updated accordingly.</span></span>

<span data-ttu-id="347ff-127">A atribuição de pacote de política a grupos é recomendada para grupos de até 50.000 usuários, mas também funcionará com grupos maiores.</span><span class="sxs-lookup"><span data-stu-id="347ff-127">Policy package assignment to groups is recommended for groups of up to 50,000 users, but it will also work with larger groups.</span></span>

<span data-ttu-id="347ff-128">Quando você atribui o pacote de política, ele é imediatamente atribuído ao grupo.</span><span class="sxs-lookup"><span data-stu-id="347ff-128">When you assign the policy package, it's immediately assigned to the group.</span></span> <span data-ttu-id="347ff-129">No entanto, a propagação da atribuição de política aos membros do grupo é executada como uma operação em segundo plano e pode levar algum tempo, dependendo do tamanho do grupo.</span><span class="sxs-lookup"><span data-stu-id="347ff-129">However, the propagation of the policy assignment to members of the group is performed as a background operation and might take some time, depending on the size of the group.</span></span> <span data-ttu-id="347ff-130">O mesmo acontece quando uma política não é atribuída a um grupo ou quando os membros são adicionados ou removidos de um grupo.</span><span class="sxs-lookup"><span data-stu-id="347ff-130">The same is true when a policy is unassigned from a group, or when members are added to or removed from a group.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="347ff-131">Antes de começar, é importante entender ( regras[de precedência](assign-policies-users-and-groups.md#precedence-rules)) e ( classificação[de atribuição de grupo](assign-policies-users-and-groups.md#group-assignment-ranking)).</span><span class="sxs-lookup"><span data-stu-id="347ff-131">Before you get started, it's important to understand ([precedence rules](assign-policies-users-and-groups.md#precedence-rules)) and ([group assignment ranking](assign-policies-users-and-groups.md#group-assignment-ranking)).</span></span> <span data-ttu-id="347ff-132">Leia e entenda os conceitos em ([O que](assign-policies-users-and-groups.md#what-you-need-to-know-about-policy-assignment-to-groups)você precisa saber sobre atribuição de política para grupos ) anteriormente neste artigo.</span><span class="sxs-lookup"><span data-stu-id="347ff-132">Make sure you read and understand the concepts in ([What you need to know about policy assignment to groups](assign-policies-users-and-groups.md#what-you-need-to-know-about-policy-assignment-to-groups)) earlier in this article.</span></span>

### <a name="assign-a-policy-package-to-a-group-of-users-in-the-admin-center"></a><span data-ttu-id="347ff-133">Atribuir um pacote de política a um grupo de usuários no centro de administração</span><span class="sxs-lookup"><span data-stu-id="347ff-133">Assign a policy package to a group of users in the admin center</span></span>

1. <span data-ttu-id="347ff-134">Entre no Centro de administração do Teams.</span><span class="sxs-lookup"><span data-stu-id="347ff-134">Sign in to the Teams admin center.</span></span>
2. <span data-ttu-id="347ff-135">Na navegação à esquerda, vá para a página pacote de política.</span><span class="sxs-lookup"><span data-stu-id="347ff-135">In the left navigation, go to the policy package page.</span></span>
3. <span data-ttu-id="347ff-136">Selecione a guia Atribuição de política de grupo.</span><span class="sxs-lookup"><span data-stu-id="347ff-136">Select the Group policy assignment tab.</span></span>
4. <span data-ttu-id="347ff-137">Selecione **Adicionar grupo** e, em seguida, no painel Atribuir um pacote de política ao grupo, faça o seguinte:</span><span class="sxs-lookup"><span data-stu-id="347ff-137">Select **Add group**, and then in the Assign a policy package to group pane, do the following:</span></span>

    <span data-ttu-id="347ff-138">a.</span><span class="sxs-lookup"><span data-stu-id="347ff-138">a.</span></span> <span data-ttu-id="347ff-139">Pesquise e adicione o grupo ao que você deseja atribuir o pacote de política.</span><span class="sxs-lookup"><span data-stu-id="347ff-139">Search for and add the group you want to assign the policy package to.</span></span>

    <span data-ttu-id="347ff-140">b.</span><span class="sxs-lookup"><span data-stu-id="347ff-140">b.</span></span> <span data-ttu-id="347ff-141">Selecione um pacote de política.</span><span class="sxs-lookup"><span data-stu-id="347ff-141">Select a policy package.</span></span>

    <span data-ttu-id="347ff-142">c.</span><span class="sxs-lookup"><span data-stu-id="347ff-142">c.</span></span> <span data-ttu-id="347ff-143">De definir a classificação para cada tipo de política.</span><span class="sxs-lookup"><span data-stu-id="347ff-143">Set the ranking for each policy type.</span></span>

    <span data-ttu-id="347ff-144">d.</span><span class="sxs-lookup"><span data-stu-id="347ff-144">d.</span></span> <span data-ttu-id="347ff-145">Selecione **Aplicar**.</span><span class="sxs-lookup"><span data-stu-id="347ff-145">Select **Apply**.</span></span>

![mostra a atribuição de política de grupo](media/group-pkg-assignment.png)

5. <span data-ttu-id="347ff-147">Para gerenciar a classificação de um tipo de política específico, navegue até a página de política específica.</span><span class="sxs-lookup"><span data-stu-id="347ff-147">To manage ranking for a specific policy type, navigate to the specific policy page.</span></span>
6. <span data-ttu-id="347ff-148">Para reatribuir um pacote de política a um grupo, primeiro remova a atribuição de política de grupo.</span><span class="sxs-lookup"><span data-stu-id="347ff-148">To reassign a policy package to a group, first remove the group policy assignment.</span></span> <span data-ttu-id="347ff-149">Em seguida, siga as etapas acima para atribuir o pacote de política a um grupo.</span><span class="sxs-lookup"><span data-stu-id="347ff-149">Then, follow the steps above to assign the policy package to a group.</span></span>

### <a name="work-with-powershell"></a><span data-ttu-id="347ff-150">Trabalhar com o PowerShell</span><span class="sxs-lookup"><span data-stu-id="347ff-150">Work with PowerShell</span></span>

#### <a name="get-the-teams-powershell-module"></a><span data-ttu-id="347ff-151">Obter o módulo do Teams PowerShell</span><span class="sxs-lookup"><span data-stu-id="347ff-151">Get the Teams PowerShell module</span></span>

<span data-ttu-id="347ff-152">Para obter orientações passo a passo, consulte [Install Teams PowerShell](teams-powershell-install.md).</span><span class="sxs-lookup"><span data-stu-id="347ff-152">For step-by-step guidance, see [Install Teams PowerShell](teams-powershell-install.md).</span></span>

#### <a name="assign-a-policy-package-to-a-group-of-users"></a><span data-ttu-id="347ff-153">Atribuir um pacote de política a um grupo de usuários</span><span class="sxs-lookup"><span data-stu-id="347ff-153">Assign a policy package to a group of users</span></span>

<span data-ttu-id="347ff-154">Use o cmdlet [Grant-CsGroupPolicyPackageAssignment](https://docs.microsoft.com/powershell/module/teams/grant-csgrouppolicypackageassignment) para atribuir um pacote de política a um grupo.</span><span class="sxs-lookup"><span data-stu-id="347ff-154">Use the [Grant-CsGroupPolicyPackageAssignment](https://docs.microsoft.com/powershell/module/teams/grant-csgrouppolicypackageassignment) cmdlet to assign a policy package to a group.</span></span> <span data-ttu-id="347ff-155">Você pode especificar um grupo usando a ID do objeto, endereço SIP ou endereço de email.</span><span class="sxs-lookup"><span data-stu-id="347ff-155">You can specify a group by using the object ID, SIP address, or email address.</span></span> <span data-ttu-id="347ff-156">Ao atribuir o pacote de política, especifique um ( classificação de atribuição de[grupo](assign-policies-users-and-groups.md#group-assignment-ranking)) para cada tipo de política no pacote de política.</span><span class="sxs-lookup"><span data-stu-id="347ff-156">When you assign the policy package, specify a ([group assignment ranking](assign-policies-users-and-groups.md#group-assignment-ranking)) for each policy type in the policy package.</span></span>

<span data-ttu-id="347ff-157">Neste exemplo, atribuímos o pacote de política Education_Teacher a um grupo com uma classificação de atribuição de 1 para TeamsAppSetupPolicy e TeamsMeetingBroadcastPolicy e uma classificação de 2 para TeamsMeetingPolicy.</span><span class="sxs-lookup"><span data-stu-id="347ff-157">In this example, we assign the Education_Teacher policy package to a group with an assignment ranking of 1 for TeamsAppSetupPolicy and TeamsMeetingBroadcastPolicy and a ranking of 2 for TeamsMeetingPolicy.</span></span>

```powershell
Grant-CsGroupPolicyPackageAssignment -GroupId "dae90bb4-120f-4a3e-a15d-30f142e79f69" -PackageName "Education_Teacher" -PolicyRankings "TeamsAppSetupPolicy, 1", "TeamsMeetingBroadcastPolicy, 1", "TeamsMeetingPolicy, 2"
```

## <a name="assign-a-policy-package-to-a-batch-of-users"></a><span data-ttu-id="347ff-158">Atribuir um pacote de política a um lote de usuários</span><span class="sxs-lookup"><span data-stu-id="347ff-158">Assign a policy package to a batch of users</span></span>

<span data-ttu-id="347ff-159">Com a atribuição de pacote de política em lote, você pode atribuir um pacote de política a grandes conjuntos de usuários por vez sem precisar usar um script.</span><span class="sxs-lookup"><span data-stu-id="347ff-159">With batch policy package assignment, you can assign a policy package to large sets of users at a time without having to use a script.</span></span> <span data-ttu-id="347ff-160">Use o cmdlet [New-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation) para enviar um lote de usuários e o pacote de política que você deseja atribuir.</span><span class="sxs-lookup"><span data-stu-id="347ff-160">You use the [New-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation) cmdlet to submit a batch of users and the policy package that you want to assign.</span></span> <span data-ttu-id="347ff-161">As atribuições são processadas como uma operação de plano de fundo e uma ID de operação é gerada para cada lote.</span><span class="sxs-lookup"><span data-stu-id="347ff-161">The assignments are processed as a background operation and an operation ID is generated for each batch.</span></span> <span data-ttu-id="347ff-162">Em seguida, você pode usar o cmdlet [Get-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/get-csbatchpolicyassignmentoperation) para rastrear o progresso e o status das atribuições em um lote.</span><span class="sxs-lookup"><span data-stu-id="347ff-162">You can then use the [Get-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/get-csbatchpolicyassignmentoperation) cmdlet to track the progress and status of the assignments in a batch.</span></span>

<span data-ttu-id="347ff-163">Especifique os usuários por sua ID de objeto ou endereço SIP (Session Initiation Protocol).</span><span class="sxs-lookup"><span data-stu-id="347ff-163">Specify users by their object ID or Session Initiation Protocol (SIP) address.</span></span> <span data-ttu-id="347ff-164">O endereço SIP de um usuário geralmente tem o mesmo valor que o UPN (Nome principal do usuário) ou o endereço de email, mas isso não é necessário.</span><span class="sxs-lookup"><span data-stu-id="347ff-164">A user's SIP address often has the same value as the User Principal Name (UPN) or email address, but this isn't required.</span></span> <span data-ttu-id="347ff-165">Se um usuário for especificado usando seu UPN ou email, mas tiver um valor diferente do endereço SIP, a atribuição de política falhará para o usuário.</span><span class="sxs-lookup"><span data-stu-id="347ff-165">If a user is specified using their UPN or email, but it has a different value than their SIP address, then policy assignment will fail for the user.</span></span> <span data-ttu-id="347ff-166">Se um lote incluir usuários duplicados, as duplicatas serão removidas do lote antes do processamento e o status só será fornecido para os usuários exclusivos restantes no lote.</span><span class="sxs-lookup"><span data-stu-id="347ff-166">If a batch includes duplicate users, the duplicates will be removed from the batch before processing and status will only be provided for the unique users remaining in the batch.</span></span>

<span data-ttu-id="347ff-167">Um lote contém até 5.000 usuários.</span><span class="sxs-lookup"><span data-stu-id="347ff-167">A batch contains up to 5,000 users.</span></span> <span data-ttu-id="347ff-168">Para obter melhores resultados, não envie mais de alguns lotes por vez.</span><span class="sxs-lookup"><span data-stu-id="347ff-168">For best results, don't submit more than a few batches at a time.</span></span> <span data-ttu-id="347ff-169">Permitir que lotes concluam o processamento antes de enviar mais lotes.</span><span class="sxs-lookup"><span data-stu-id="347ff-169">Allow batches to complete processing before submitting more batches.</span></span>

### <a name="use-the-teams-powershell-module"></a><span data-ttu-id="347ff-170">Usar o módulo do Teams PowerShell</span><span class="sxs-lookup"><span data-stu-id="347ff-170">Use the Teams PowerShell module</span></span>

<span data-ttu-id="347ff-171">Execute o seguinte para instalar o [módulo do Microsoft Teams PowerShell](https://www.powershellgallery.com/packages/MicrosoftTeams) (caso ainda não tenha feito isso).</span><span class="sxs-lookup"><span data-stu-id="347ff-171">Run the following to install the [Microsoft Teams PowerShell module](https://www.powershellgallery.com/packages/MicrosoftTeams) (if you haven't already).</span></span> <span data-ttu-id="347ff-172">Instale a versão 1.0.5 ou posterior.</span><span class="sxs-lookup"><span data-stu-id="347ff-172">Make sure you install version 1.0.5 or later.</span></span>

```powershell
Install-Module -Name MicrosoftTeams
```

<span data-ttu-id="347ff-173">Execute o seguinte para se conectar ao Teams e iniciar uma sessão.</span><span class="sxs-lookup"><span data-stu-id="347ff-173">Run the following to connect to Teams and start a session.</span></span>

```powershell
Connect-MicrosoftTeams
```

<span data-ttu-id="347ff-174">Quando for solicitado, entre usando suas credenciais de administrador.</span><span class="sxs-lookup"><span data-stu-id="347ff-174">When you're prompted, sign in using your admin credentials.</span></span>

### <a name="assign-policy-packages-to-a-batch-of-users"></a><span data-ttu-id="347ff-175">Atribuir pacotes de política a um lote de usuários</span><span class="sxs-lookup"><span data-stu-id="347ff-175">Assign policy packages to a batch of users</span></span>

<span data-ttu-id="347ff-176">Neste exemplo, usamos o cmdlet [New-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation) para atribuir o pacote de política Education_PrimaryStudent a um lote de usuários.</span><span class="sxs-lookup"><span data-stu-id="347ff-176">In this example, we use the [New-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation) cmdlet to assign the Education_PrimaryStudent policy package to a batch of users.</span></span>

```powershell
New-CsBatchPolicyPackageAssignmentOperation -Identity 1bc0b35f-095a-4a37-a24c-c4b6049816ab,user1@econtoso.com,user2@contoso.com -PackageName Education_PrimaryStudent
```

### <a name="see-the-status-of-a-batch-assignment"></a><span data-ttu-id="347ff-177">Consulte o status de uma atribuição em lotes</span><span class="sxs-lookup"><span data-stu-id="347ff-177">See the status of a batch assignment</span></span>

<span data-ttu-id="347ff-178">Execute o seguinte para obter o status de uma atribuição em lotes, onde OperationId é a ID da operação retornada pelo ```New-CsBatchPolicyAssignmentOperation``` cmdlet para um determinado lote.</span><span class="sxs-lookup"><span data-stu-id="347ff-178">Run the following to get the status of a batch assignment, where OperationId is the operation ID that's returned by the ```New-CsBatchPolicyAssignmentOperation``` cmdlet for a given batch.</span></span>

```powershell
$Get-CsBatchPolicyAssignmentOperation -OperationId f985e013-0826-40bb-8c94-e5f367076044 | fl
```

<span data-ttu-id="347ff-179">Se a saída mostrar que ocorreu um erro, execute o seguinte para obter mais informações sobre erros, que estão na ```UserState``` propriedade.</span><span class="sxs-lookup"><span data-stu-id="347ff-179">If the output shows that an error occurred, run the following to get more information about errors, which are in the ```UserState``` property.</span></span>

```powershell
Get-CsBatchPolicyAssignmentOperation -OperationId f985e013-0826-40bb-8c94-e5f367076044 | Select -ExpandProperty UserState
```

<span data-ttu-id="347ff-180">Para saber mais, confira [Get-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/get-csbatchpolicyassignmentoperation).</span><span class="sxs-lookup"><span data-stu-id="347ff-180">To learn more, see [Get-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/get-csbatchpolicyassignmentoperation).</span></span>

## <a name="related-topics"></a><span data-ttu-id="347ff-181">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="347ff-181">Related topics</span></span>

- [<span data-ttu-id="347ff-182">Gerenciar o Teams com políticas</span><span class="sxs-lookup"><span data-stu-id="347ff-182">Manage Teams with policies</span></span>](manage-teams-with-policies.md)
- [<span data-ttu-id="347ff-183">Gerenciar pacotes de política no Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="347ff-183">Manage policy packages in Microsoft Teams</span></span>](manage-policy-packages.md)
- [<span data-ttu-id="347ff-184">Visão Geral do PowerShell do Teams</span><span class="sxs-lookup"><span data-stu-id="347ff-184">Teams PowerShell Overview</span></span>](teams-powershell-overview.md)
- [<span data-ttu-id="347ff-185">Atribuir políticas no Teams - iniciando</span><span class="sxs-lookup"><span data-stu-id="347ff-185">Assign policies in Teams - getting started</span></span>](policy-assignment-overview.md)