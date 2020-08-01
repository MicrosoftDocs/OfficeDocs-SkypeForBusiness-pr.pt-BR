---
title: Atribuir políticas a grandes conjuntos de usuários na sua escola
author: lanachin
ms.author: v-lanac
manager: serdars
ms.reviewer: karsmith, angch, cebulnes
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
- remotework
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: Saiba como atribuir políticas a grandes conjuntos de usuários em sua instituição educacional com base em associação a um grupo ou diretamente por meio de uma atribuição em lote para fins de escola remota (teleescolar, tele-School).
f1keywords: ''
ms.openlocfilehash: 0b4fd804b51fef9537d30230aed400bb0cb7e0aa
ms.sourcegitcommit: dc3e8ae454c42981f037f4de2e48005428b6078e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/31/2020
ms.locfileid: "46534060"
---
# <a name="assign-policies-to-large-sets-of-users-in-your-school"></a><span data-ttu-id="6741a-103">Atribuir políticas a grandes conjuntos de usuários na sua escola</span><span class="sxs-lookup"><span data-stu-id="6741a-103">Assign policies to large sets of users in your school</span></span>

> [!NOTE]
> <span data-ttu-id="6741a-104">Para obter uma história maior sobre como atribuir políticas no Microsoft Teams, consulte [atribuir políticas a seus usuários no Teams](assign-policies.md).</span><span class="sxs-lookup"><span data-stu-id="6741a-104">For the larger story on assigning policies in Microsoft Teams, see [Assign policies to your users in Teams](assign-policies.md).</span></span>

## <a name="overview"></a><span data-ttu-id="6741a-105">Visão geral</span><span class="sxs-lookup"><span data-stu-id="6741a-105">Overview</span></span>

<span data-ttu-id="6741a-106">Você precisa dar aos alunos e professores acesso a diferentes recursos do Microsoft Teams?</span><span class="sxs-lookup"><span data-stu-id="6741a-106">Do you need to give your students and educators access to different features in Microsoft Teams?</span></span> <span data-ttu-id="6741a-107">Você pode identificar rapidamente os usuários da sua organização por tipo de licença e, em seguida, atribuí-los à política apropriada.</span><span class="sxs-lookup"><span data-stu-id="6741a-107">You can quickly identify the users in your organization by license type and then assign them the appropriate policy.</span></span> <span data-ttu-id="6741a-108">Este tutorial mostra como atribuir uma política de reunião a grandes conjuntos de usuários na sua escola.</span><span class="sxs-lookup"><span data-stu-id="6741a-108">This tutorial shows you how to assign a meeting policy to large sets of users in your school.</span></span> <span data-ttu-id="6741a-109">Você pode atribuir políticas usando o centro de administração do Microsoft Teams e o PowerShell e mostraremos as duas maneiras.</span><span class="sxs-lookup"><span data-stu-id="6741a-109">You can assign policies using the Microsoft Teams admin center and PowerShell and we'll show you both ways.</span></span>

<span data-ttu-id="6741a-110">Você pode atribuir uma política de reunião a um grupo de segurança do qual os usuários são membros ou diretamente para os usuários em escala por meio de uma atribuição de política em lotes.</span><span class="sxs-lookup"><span data-stu-id="6741a-110">You can assign a meeting policy to a security group that the users are members of or directly to users at scale through a batch policy assignment.</span></span> <span data-ttu-id="6741a-111">Você aprenderá a:</span><span class="sxs-lookup"><span data-stu-id="6741a-111">You'll learn how to:</span></span>

- <span data-ttu-id="6741a-112">**Use [a atribuição de política para grupos](#assign-a-policy-to-a-group) para atribuir uma política de reunião a um grupo de segurança (recomendado)**.</span><span class="sxs-lookup"><span data-stu-id="6741a-112">**Use [policy assignment to groups](#assign-a-policy-to-a-group) to assign a meeting policy to a security group (recommended)**.</span></span> <span data-ttu-id="6741a-113">Esse método permite atribuir uma política com base em associação a um grupo.</span><span class="sxs-lookup"><span data-stu-id="6741a-113">This method lets you assign a policy based on group membership.</span></span> <span data-ttu-id="6741a-114">Você pode atribuir uma política a um grupo de segurança ou lista de distribuição.</span><span class="sxs-lookup"><span data-stu-id="6741a-114">You can assign a policy to a security group or distribution list.</span></span> <span data-ttu-id="6741a-115">Conforme os membros são adicionados ou removidos do grupo, suas atribuições de política herdadas são atualizadas de acordo.</span><span class="sxs-lookup"><span data-stu-id="6741a-115">As members are added to or removed from the group, their inherited policy assignments are updated accordingly.</span></span> <span data-ttu-id="6741a-116">Recomendamos que você use esse método, pois ele reduz o tempo para gerenciar políticas para novos usuários ou quando as funções dos usuários mudam.</span><span class="sxs-lookup"><span data-stu-id="6741a-116">We recommend you use this method because it reduces the time to manage policies for new users or when users' roles change.</span></span> <span data-ttu-id="6741a-117">Esse método funciona melhor para grupos de até 50.000 usuários, mas também funcionará com grupos maiores.</span><span class="sxs-lookup"><span data-stu-id="6741a-117">This method works best for groups of up to 50,000 users but will also work with larger groups.</span></span>

- <span data-ttu-id="6741a-118">**Use a [atribuição de política em lote](assign-policies.md#assign-a-policy-to-a-batch-of-users) para atribuir uma política de reunião diretamente aos usuários em massa**.</span><span class="sxs-lookup"><span data-stu-id="6741a-118">**Use [batch policy assignment](assign-policies.md#assign-a-policy-to-a-batch-of-users) to assign a meeting policy directly to users in bulk**.</span></span> <span data-ttu-id="6741a-119">Você pode atribuir uma política de até 5.000 usuários de cada vez.</span><span class="sxs-lookup"><span data-stu-id="6741a-119">You can assign a policy for up to 5,000 users at a time.</span></span> <span data-ttu-id="6741a-120">Se você tiver mais de 5.000 usuários, poderá enviar vários lotes.</span><span class="sxs-lookup"><span data-stu-id="6741a-120">If you have more than 5,000 users, you can submit multiple batches.</span></span> <span data-ttu-id="6741a-121">Com esse método, quando você tiver novos usuários, será necessário executar novamente a atribuição de lote para atribuir a política a esses novos usuários.</span><span class="sxs-lookup"><span data-stu-id="6741a-121">With this method, when you have new users, you'll need to re-run the batch assignment to assign the policy to those new users.</span></span>

<span data-ttu-id="6741a-122">Lembre-se de que, no Teams, os usuários obtêm automaticamente a política global (padrão para toda a organização) para um tipo de política de equipe, a menos que você crie e atribua uma política personalizada.</span><span class="sxs-lookup"><span data-stu-id="6741a-122">Remember that in Teams, users automatically get the Global (Org-wide default) policy for a Teams policy type unless you create and assign a custom policy.</span></span> <span data-ttu-id="6741a-123">Como a população dos alunos costuma ser o maior conjunto de usuários e muitas vezes recebem as configurações mais restritivas, recomendamos que você faça o seguinte:</span><span class="sxs-lookup"><span data-stu-id="6741a-123">Because the student population is often the largest set of users and they often receive the most restrictive settings, we recommend that you do the following:</span></span>

- <span data-ttu-id="6741a-124">Crie uma política personalizada que permita recursos essenciais, como chat particular e agendamento de reunião e atribuir a política a seus funcionários e educadores.</span><span class="sxs-lookup"><span data-stu-id="6741a-124">Create a custom policy that allows core capabilities such as private chat and meeting scheduling and assign the policy to your staff and educators.</span></span>
- <span data-ttu-id="6741a-125">Atribua a política personalizada a seus funcionários e educadores.</span><span class="sxs-lookup"><span data-stu-id="6741a-125">Assign the custom policy to your staff and educators.</span></span>
- <span data-ttu-id="6741a-126">Edite e aplique a política global (padrão para toda a organização) para restringir recursos para os alunos.</span><span class="sxs-lookup"><span data-stu-id="6741a-126">Edit and apply the Global (Org-wide default) policy to restrict capabilities for students.</span></span>

<span data-ttu-id="6741a-127">Lembre-se de que a política global será aplicada a todos os usuários de sua escola até você criar uma política personalizada e atribuí-la a seus funcionários e professores.</span><span class="sxs-lookup"><span data-stu-id="6741a-127">Keep in mind that the Global policy will apply to all users in your school until you create a custom policy and assign it to your staff and educators.</span></span>

<span data-ttu-id="6741a-128">Neste tutorial, os alunos receberão a política de reunião global e atribuiremos uma política de reunião personalizada chamada EducatorMeetingPolicy à equipe e educadores.</span><span class="sxs-lookup"><span data-stu-id="6741a-128">In this tutorial, students will get the Global meeting policy and we'll assign a custom meeting policy named EducatorMeetingPolicy to staff and educators.</span></span> <span data-ttu-id="6741a-129">Presumimos que você tenha editado a política global para personalizar as configurações de reunião para os alunos e [criou uma política personalizada](policy-packages-edu.md) que define a experiência da reunião para funcionários e educadores.</span><span class="sxs-lookup"><span data-stu-id="6741a-129">We assume that you've edited the Global policy to tailor meeting settings for students and [created a custom policy](policy-packages-edu.md) that defines the meeting experience for staff and educators.</span></span>

![Captura de tela da página políticas de reunião no centro de administração do teams](media/batch-group-policy-assignment-edu-meeting-policies.png)

## <a name="assign-a-policy-to-a-group"></a><span data-ttu-id="6741a-131">Atribuir uma política a um grupo</span><span class="sxs-lookup"><span data-stu-id="6741a-131">Assign a policy to a group</span></span>

<span data-ttu-id="6741a-132">Siga estas etapas para criar um grupo de segurança para seus funcionários e professores e, em seguida, atribuir uma política de reunião personalizada chamada EducatorMeetingPolicy a esse grupo de segurança.</span><span class="sxs-lookup"><span data-stu-id="6741a-132">Follow these steps to create a security group for your staff and educators, and then assign a custom meeting policy named EducatorMeetingPolicy to that security group.</span></span>

### <a name="before-you-get-started"></a><span data-ttu-id="6741a-133">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="6741a-133">Before you get started</span></span>

> [!IMPORTANT]
> <span data-ttu-id="6741a-134">Quando você atribui uma política a um grupo, a atribuição de política é propagada para os membros do grupo de acordo com as regras de precedência.</span><span class="sxs-lookup"><span data-stu-id="6741a-134">When you assign a policy to a group, the policy assignment is propagated to members of the group according to precedence rules.</span></span> <span data-ttu-id="6741a-135">Por exemplo, se um usuário for diretamente atribuído a uma política (individualmente ou por meio de uma atribuição em lotes), essa política terá precedência sobre uma política herdada de um grupo.</span><span class="sxs-lookup"><span data-stu-id="6741a-135">For example, if a user is directly assigned a policy (either individually or through a batch assignment), that policy takes precedence over a policy that's inherited from a group.</span></span> <span data-ttu-id="6741a-136">Isso também significa que, se um usuário tiver uma política de reunião atribuída diretamente a ele, você terá que remover essa política de reunião do usuário antes de poder herdar uma política de reunião de um grupo de segurança.</span><span class="sxs-lookup"><span data-stu-id="6741a-136">This also means that if a user has a meeting policy that was directly assigned to them, you'll have to remove that meeting policy from the user before they can inherit a meeting policy from a security group.</span></span>

<span data-ttu-id="6741a-137">Antes de começar, é importante entender [as regras de precedência](assign-policies.md#precedence-rules) e a [classificação de atribuição de grupo](assign-policies.md#group-assignment-ranking).</span><span class="sxs-lookup"><span data-stu-id="6741a-137">Before you get started, it's important to understand [precedence rules](assign-policies.md#precedence-rules) and [group assignment ranking](assign-policies.md#group-assignment-ranking).</span></span> <span data-ttu-id="6741a-138">Certifique-se de **ler e entender os conceitos do [que você precisa saber sobre a atribuição de política a grupos](assign-policies.md#what-you-need-to-know-about-policy-assignment-to-groups)**.</span><span class="sxs-lookup"><span data-stu-id="6741a-138">**Make sure that you read and understand the concepts in [What you need to know about policy assignment to groups](assign-policies.md#what-you-need-to-know-about-policy-assignment-to-groups)**.</span></span>

<span data-ttu-id="6741a-139">Você precisará completar todas essas etapas para que seus funcionários e professores herdem uma política de reunião de um grupo de segurança.</span><span class="sxs-lookup"><span data-stu-id="6741a-139">You'll need to complete all these steps for your staff and educators to inherit a meeting policy from a security group.</span></span>

1. <span data-ttu-id="6741a-140">[Criar grupos de segurança](#create-security-groups).</span><span class="sxs-lookup"><span data-stu-id="6741a-140">[Create security groups](#create-security-groups).</span></span>
2. <span data-ttu-id="6741a-141">[Atribuir uma política a um grupo de segurança](#assign-a-policy-to-a-security-group).</span><span class="sxs-lookup"><span data-stu-id="6741a-141">[Assign a policy to a security group](#assign-a-policy-to-a-security-group).</span></span>
3. <span data-ttu-id="6741a-142">[Remover uma política que foi atribuída diretamente aos usuários](#remove-a-policy-that-was-directly-assigned-to-users).</span><span class="sxs-lookup"><span data-stu-id="6741a-142">[Remove a policy that was directly assigned to users](#remove-a-policy-that-was-directly-assigned-to-users).</span></span>

### <a name="create-security-groups"></a><span data-ttu-id="6741a-143">Criar grupos de segurança</span><span class="sxs-lookup"><span data-stu-id="6741a-143">Create security groups</span></span>

<span data-ttu-id="6741a-144">Primeiro, crie um grupo de segurança para seus funcionários e educadores.</span><span class="sxs-lookup"><span data-stu-id="6741a-144">First, create a security group for your staff and educators.</span></span>

<span data-ttu-id="6741a-145">Com a [data de sincronização da escola](https://docs.microsoft.com/SchoolDataSync/) (SDS), você pode [criar facilmente grupos de segurança para professores e alunos](https://docs.microsoft.com/SchoolDataSync/edu-security-groups) da sua escola.</span><span class="sxs-lookup"><span data-stu-id="6741a-145">With [School Data Sync](https://docs.microsoft.com/SchoolDataSync/) (SDS), you can [easily create security groups educators and students](https://docs.microsoft.com/SchoolDataSync/edu-security-groups) in your school.</span></span> <span data-ttu-id="6741a-146">Recomendamos que você use o SDS para criar os grupos de segurança necessários para gerenciar políticas para sua escola.</span><span class="sxs-lookup"><span data-stu-id="6741a-146">We recommend that you use SDS to create the security groups you need to manage policies for your school.</span></span>

<span data-ttu-id="6741a-147">Se não for possível implantar o SDS em seu ambiente, use [esse script do PowerShell](scripts/powershell-script-security-groups-edu.md) para criar dois grupos de segurança, um para todos os funcionários e professores que têm uma licença docente atribuída e outro para todos os alunos que têm uma licença de aluno atribuída.</span><span class="sxs-lookup"><span data-stu-id="6741a-147">If you're unable to deploy SDS within your environment, use [this PowerShell script](scripts/powershell-script-security-groups-edu.md) to create two security groups, one for all staff and educators who have a Faculty license assigned and another for all students who have a Student license assigned.</span></span> <span data-ttu-id="6741a-148">Você precisará executar esse script rotineiramente para manter atualizados os grupos e até o momento.</span><span class="sxs-lookup"><span data-stu-id="6741a-148">You'll need to run this script routinely to keep the groups fresh and up to date.</span></span>

### <a name="assign-a-policy-to-a-security-group"></a><span data-ttu-id="6741a-149">Atribuir uma política a um grupo de segurança</span><span class="sxs-lookup"><span data-stu-id="6741a-149">Assign a policy to a security group</span></span>

#### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="6741a-150">Usando o centro de administração do Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="6741a-150">Using the Microsoft Teams admin center</span></span>

> [!NOTE]
> <span data-ttu-id="6741a-151">Atualmente, a atribuição de política a grupos usando o centro de administração do Microsoft Teams está disponível apenas para política de chamada de equipes, política de estacionamento de chamada de equipe, política de equipe, política de eventos do Teams, política de reunião do Teams e política de mensagens de equipe.</span><span class="sxs-lookup"><span data-stu-id="6741a-151">Currently, policy assignment to groups using the Microsoft Teams admin center is only available for Teams calling policy, Teams call park policy, Teams policy, Teams live events policy, Teams meeting policy, and Teams messaging policy.</span></span> <span data-ttu-id="6741a-152">Para outros tipos de política, use o PowerShell.</span><span class="sxs-lookup"><span data-stu-id="6741a-152">For other policy types, use PowerShell.</span></span>

1. <span data-ttu-id="6741a-153">Na navegação à esquerda do centro de administração do Microsoft Teams, vá para políticas de reunião de **reuniões**  >  **Meeting policies**.</span><span class="sxs-lookup"><span data-stu-id="6741a-153">In the left navigation of the Microsoft Teams admin center, go to **Meetings** > **Meeting policies**.</span></span>
2. <span data-ttu-id="6741a-154">Selecione a guia **atribuição de política de grupo** .</span><span class="sxs-lookup"><span data-stu-id="6741a-154">Select the **Group policy assignment** tab.</span></span>
3. <span data-ttu-id="6741a-155">Selecione **Adicionar grupo**e, em seguida, no painel **atribuir política ao grupo** , faça o seguinte:</span><span class="sxs-lookup"><span data-stu-id="6741a-155">Select **Add group**, and then in the **Assign policy to group** pane, do the following:</span></span>

    ![Captura de tela do painel Editar configurações, mostrando política de reunião](media/batch-group-policy-assignment-edu-group.png)
    1. <span data-ttu-id="6741a-157">Na caixa **selecionar um grupo** , procure e adicione o grupo de segurança que contém seus funcionários e educadores.</span><span class="sxs-lookup"><span data-stu-id="6741a-157">In the **Select a group** box, search for and add the security group that contains your staff and educators.</span></span>
    2. <span data-ttu-id="6741a-158">Na caixa **selecionar classificação** , insira **1**.</span><span class="sxs-lookup"><span data-stu-id="6741a-158">In the **Select rank** box, enter **1**.</span></span>
    3. <span data-ttu-id="6741a-159">Na caixa **selecionar uma política** , selecione **EducatorMeetingPolicy**.</span><span class="sxs-lookup"><span data-stu-id="6741a-159">In the **Select a policy** box, select **EducatorMeetingPolicy**.</span></span>
    4. <span data-ttu-id="6741a-160">Selecione **aplicar**.</span><span class="sxs-lookup"><span data-stu-id="6741a-160">Select **Apply**.</span></span>

<span data-ttu-id="6741a-161">Para remover uma atribuição de política de grupo, na guia **atribuição de política de grupo** da página política, selecione a atribuição de grupo e, em seguida, selecione **remover**.</span><span class="sxs-lookup"><span data-stu-id="6741a-161">To remove a group policy assignment, on the **Group policy assignment** tab of the policy page, select the group assignment, and then select **Remove**.</span></span>

<span data-ttu-id="6741a-162">Para alterar a classificação de uma atribuição de grupo, primeiro você precisa remover a atribuição de política de grupo.</span><span class="sxs-lookup"><span data-stu-id="6741a-162">To change the ranking of a group assignment, you have to first remove the group policy assignment.</span></span> <span data-ttu-id="6741a-163">Em seguida, siga as etapas acima para atribuir a política a um grupo.</span><span class="sxs-lookup"><span data-stu-id="6741a-163">Then, follow the steps above to assign the policy to a group.</span></span>

#### <a name="using-powershell"></a><span data-ttu-id="6741a-164">Usando o PowerShell</span><span class="sxs-lookup"><span data-stu-id="6741a-164">Using PowerShell</span></span>

> [!NOTE]
> <span data-ttu-id="6741a-165">Atualmente, a atribuição de política a grupos usando o PowerShell não está disponível para todos os tipos de política de equipe.</span><span class="sxs-lookup"><span data-stu-id="6741a-165">Currently, policy assignment to groups using PowerShell isn't available for all Teams policy types.</span></span> <span data-ttu-id="6741a-166">Consulte [New-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/new-csgrouppolicyassignment) para obter a lista de tipos de política com suporte.</span><span class="sxs-lookup"><span data-stu-id="6741a-166">See [New-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/new-csgrouppolicyassignment) for the list of supported policy types.</span></span>

##### <a name="install-and-connect-to-the-microsoft-teams-powershell-module"></a><span data-ttu-id="6741a-167">Instalar e conectar-se ao módulo do PowerShell do Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="6741a-167">Install and connect to the Microsoft Teams PowerShell module</span></span>

<span data-ttu-id="6741a-168">Execute o seguinte para instalar o [módulo do teams PowerShell](https://www.powershellgallery.com/packages/MicrosoftTeams) (se ainda não estiver instalado).</span><span class="sxs-lookup"><span data-stu-id="6741a-168">Run the following to install the [Teams PowerShell module](https://www.powershellgallery.com/packages/MicrosoftTeams) (if it's not already installed).</span></span> <span data-ttu-id="6741a-169">Verifique se você instalou a versão 1.0.5 ou posterior.</span><span class="sxs-lookup"><span data-stu-id="6741a-169">Make sure you install version 1.0.5 or later.</span></span>

```powershell
Install-Module -Name MicrosoftTeams
```

<span data-ttu-id="6741a-170">Execute o seguinte para se conectar ao Microsoft Teams e iniciar uma sessão.</span><span class="sxs-lookup"><span data-stu-id="6741a-170">Run the following to connect to Teams and start a session.</span></span>

```powershell
Connect-MicrosoftTeams
```

<span data-ttu-id="6741a-171">Quando for solicitado, entre usando suas credenciais de administrador.</span><span class="sxs-lookup"><span data-stu-id="6741a-171">When you're prompted, sign in using your admin credentials.</span></span>

##### <a name="assign-a-policy-to-a-group"></a><span data-ttu-id="6741a-172">Atribuir uma política a um grupo</span><span class="sxs-lookup"><span data-stu-id="6741a-172">Assign a policy to a group</span></span>

<span data-ttu-id="6741a-173">Execute o seguinte para atribuir a política de reunião chamada EducatorMeetingPolicy ao grupo de segurança que contém seus funcionários e educadores e defina a classificação de atribuição como 1.</span><span class="sxs-lookup"><span data-stu-id="6741a-173">Run the following to assign the meeting policy named EducatorMeetingPolicy to the security group that contains your staff and educators and set the assignment ranking to 1.</span></span> <span data-ttu-id="6741a-174">Você pode especificar um grupo de segurança usando a ID do objeto, o endereço SIP ou o endereço de email.</span><span class="sxs-lookup"><span data-stu-id="6741a-174">You can specify a security group by using the object Id, Session Initiation Protocol (SIP) address, or email address.</span></span> <span data-ttu-id="6741a-175">Neste exemplo, usamos um endereço de email (staff-faculty@contoso.com).</span><span class="sxs-lookup"><span data-stu-id="6741a-175">In this example, we use an email address (staff-faculty@contoso.com).</span></span>

```powershell
New-CsGroupPolicyAssignment -GroupId staff-faculty@contoso.com -PolicyType TeamsMeetingPolicy -PolicyName "EducatorMeetingPolicy" -Rank 1
```

### <a name="remove-a-policy-that-was-directly-assigned-to-users"></a><span data-ttu-id="6741a-176">Remover uma política que foi diretamente atribuída aos usuários</span><span class="sxs-lookup"><span data-stu-id="6741a-176">Remove a policy that was directly assigned to users</span></span>

<span data-ttu-id="6741a-177">Lembre-se de que, se um usuário foi diretamente atribuído a uma política (individualmente ou por meio de uma atribuição em lotes), essa política terá precedência.</span><span class="sxs-lookup"><span data-stu-id="6741a-177">Remember that if a user was directly assigned a policy (either individually or through a batch assignment), that policy takes precedence.</span></span> <span data-ttu-id="6741a-178">Isso significa que, se um usuário tiver uma política de reunião atribuída diretamente a ele, você terá que remover essa política de reunião do usuário antes de poder herdar uma política de reunião de um grupo de segurança.</span><span class="sxs-lookup"><span data-stu-id="6741a-178">This means that if a user has a meeting policy that was directly assigned to them, you'll have to remove that meeting policy from the user before they can inherit a meeting policy from a security group.</span></span>

<span data-ttu-id="6741a-179">Para saber mais, confira [o que você precisa saber sobre atribuição de política a grupos](assign-policies.md#what-you-need-to-know-about-policy-assignment-to-groups).</span><span class="sxs-lookup"><span data-stu-id="6741a-179">To learn more, see [What you need to know about policy assignment to groups](assign-policies.md#what-you-need-to-know-about-policy-assignment-to-groups).</span></span>

<span data-ttu-id="6741a-180">Siga estas etapas para remover a política de reunião atribuída diretamente a seus funcionários e professores.</span><span class="sxs-lookup"><span data-stu-id="6741a-180">Follow these steps to remove the meeting policy that was directly assigned to your staff and educators.</span></span>

#### <a name="install-and-connect-to-the-microsoft-teams-powershell-module"></a><span data-ttu-id="6741a-181">Instalar e conectar-se ao módulo do PowerShell do Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="6741a-181">Install and connect to the Microsoft Teams PowerShell module</span></span>

<span data-ttu-id="6741a-182">Execute o seguinte para instalar o [módulo do teams PowerShell](https://www.powershellgallery.com/packages/MicrosoftTeams) (se ainda não estiver instalado).</span><span class="sxs-lookup"><span data-stu-id="6741a-182">Run the following to install the [Teams PowerShell module](https://www.powershellgallery.com/packages/MicrosoftTeams) (if it's not already installed).</span></span> <span data-ttu-id="6741a-183">Verifique se você instalou a versão 1.0.5 ou posterior.</span><span class="sxs-lookup"><span data-stu-id="6741a-183">Make sure you install version 1.0.5 or later.</span></span>

```powershell
Install-Module -Name MicrosoftTeams
```

<span data-ttu-id="6741a-184">Execute o seguinte para se conectar ao Microsoft Teams e iniciar uma sessão.</span><span class="sxs-lookup"><span data-stu-id="6741a-184">Run the following to connect to Teams and start a session.</span></span>

```powershell
Connect-MicrosoftTeams
```
<span data-ttu-id="6741a-185">Quando for solicitado, entre usando as mesmas credenciais de administrador usadas para se conectar ao Azure AD.</span><span class="sxs-lookup"><span data-stu-id="6741a-185">When you're prompted, sign in using the same admin credentials you used to connect to Azure AD.</span></span>

#### <a name="unassign-a-policy-that-was-directly-assigned-to-users"></a><span data-ttu-id="6741a-186">Cancelar a atribuição de uma política que foi atribuída diretamente aos usuários</span><span class="sxs-lookup"><span data-stu-id="6741a-186">Unassign a policy that was directly assigned to users</span></span>

<span data-ttu-id="6741a-187">Execute o seguinte para remover uma política de reunião de usuários que receberam essa política diretamente.</span><span class="sxs-lookup"><span data-stu-id="6741a-187">Run the following to remove a meeting policy from users who were directly assigned that policy.</span></span> <span data-ttu-id="6741a-188">Você pode especificar os usuários por endereço de email ou ID de objeto.</span><span class="sxs-lookup"><span data-stu-id="6741a-188">You can specify users by email address or object ID.</span></span>

<span data-ttu-id="6741a-189">Neste exemplo, a política de reunião é removida de usuários especificados pelo endereço de e-mail.</span><span class="sxs-lookup"><span data-stu-id="6741a-189">In this example, the meeting policy is removed from users specified by their email address.</span></span>

```powershell
$users_ids = @("reda@contoso.com", "nikica@contoso.com", "jamie@contoso.com")
New-CsBatchPolicyAssignmentOperation -PolicyType TeamsMeetingPolicy -PolicyName $null -Identity $users_ids -OperationName "Unassign meeting policy"
```

<span data-ttu-id="6741a-190">Neste exemplo, a política de reunião é removida da lista de usuários em um arquivo de texto chamado user_ids.txt.</span><span class="sxs-lookup"><span data-stu-id="6741a-190">In this example, the meeting policy is removed from the list of users in a text file named user_ids.txt.</span></span> 

```powershell
$user_ids = Get-Content .\users_ids.txt
New-CsBatchPolicyAssignmentOperation -PolicyType TeamsMeetingPolicy -PolicyName $null -Identity $users_ids -OperationName "Unassign meeting policy"
```

##### <a name="get-policy-assignments-for-a-group"></a><span data-ttu-id="6741a-191">Obter atribuições de política para um grupo</span><span class="sxs-lookup"><span data-stu-id="6741a-191">Get policy assignments for a group</span></span>

<span data-ttu-id="6741a-192">Execute o seguinte para ver todas as políticas atribuídas a um grupo de segurança específico.</span><span class="sxs-lookup"><span data-stu-id="6741a-192">Run the following to see all the policies assigned to a specific security group.</span></span> <span data-ttu-id="6741a-193">Observe que os grupos são sempre listados pela ID do grupo mesmo se seu endereço SIP ou endereço de email foi usado para atribuir a política.</span><span class="sxs-lookup"><span data-stu-id="6741a-193">Note that groups are always listed by their group Id even if its SIP address or email address was used to assign the policy.</span></span>

```powershell
Get-CsGroupPolicyAssignment -GroupId staff-faculty@contoso.com

```

##### <a name="get-the-policies-assigned-to-a-user"></a><span data-ttu-id="6741a-194">Obter as políticas atribuídas a um usuário</span><span class="sxs-lookup"><span data-stu-id="6741a-194">Get the policies assigned to a user</span></span>

<span data-ttu-id="6741a-195">Execute o seguinte para ver todas as políticas atribuídas a um usuário específico.</span><span class="sxs-lookup"><span data-stu-id="6741a-195">Run the following to see all the policies that are assigned to a specific user.</span></span> <span data-ttu-id="6741a-196">O exemplo a seguir mostra como obter as políticas atribuídas ao reda@contoso.com.</span><span class="sxs-lookup"><span data-stu-id="6741a-196">The following example shows you how to get the policies that are assigned to reda@contoso.com.</span></span>

```powershell
Get-CsUserPolicyAssignment -Identity reda@contoso.com
```

## <a name="assign-a-policy-to-a-batch-of-users"></a><span data-ttu-id="6741a-197">Atribuir uma política a um lote de usuários</span><span class="sxs-lookup"><span data-stu-id="6741a-197">Assign a policy to a batch of users</span></span>

<span data-ttu-id="6741a-198">Siga estas etapas para atribuir uma política de reunião personalizada chamada EducatorMeetingPolicy diretamente a seus funcionários e professores em massa.</span><span class="sxs-lookup"><span data-stu-id="6741a-198">Follow these steps to assign a custom meeting policy named EducatorMeetingPolicy directly to your staff and educators in bulk.</span></span>

### <a name="using-powershell"></a><span data-ttu-id="6741a-199">Usando o PowerShell</span><span class="sxs-lookup"><span data-stu-id="6741a-199">Using PowerShell</span></span>

#### <a name="connect-to-the-azure-ad-powershell-for-graph-module-and-the-teams-powershell-module"></a><span data-ttu-id="6741a-200">Conectar-se ao módulo do Azure AD PowerShell para Graph e ao módulo do PowerShell do teams</span><span class="sxs-lookup"><span data-stu-id="6741a-200">Connect to the Azure AD PowerShell for Graph module and the Teams PowerShell module</span></span>

<span data-ttu-id="6741a-201">Antes de executar as etapas deste artigo, você precisará instalar e se conectar ao módulo Azure AD PowerShell para Graph (para identificar os usuários por suas licenças atribuídas) e ao módulo do Microsoft Teams PowerShell (para atribuir as políticas a esses usuários).</span><span class="sxs-lookup"><span data-stu-id="6741a-201">Before you perform the steps in this article, you'll need to install and connect to the Azure AD PowerShell for Graph module (to identify users by their assigned licenses) and the Microsoft Teams PowerShell module (to assign the policies to those users).</span></span>

##### <a name="install-and-connect-to-the-azure-ad-powershell-for-graph-module"></a><span data-ttu-id="6741a-202">Instalar e conectar-se ao módulo do Azure AD PowerShell para Graph</span><span class="sxs-lookup"><span data-stu-id="6741a-202">Install and connect to the Azure AD PowerShell for Graph module</span></span>

<span data-ttu-id="6741a-203">Abra um prompt de comando do Windows PowerShell com privilégios elevados (execute o Windows PowerShell como administrador) e execute o seguinte procedimento para instalar o módulo do Azure Active Directory PowerShell para Graph.</span><span class="sxs-lookup"><span data-stu-id="6741a-203">Open an elevated Windows PowerShell command prompt (run Windows PowerShell as an administrator), and then run the following to install the Azure Active Directory PowerShell for Graph module.</span></span>

```powershell
Install-Module -Name AzureAD
```

<span data-ttu-id="6741a-204">Execute o seguinte para se conectar ao Azure AD.</span><span class="sxs-lookup"><span data-stu-id="6741a-204">Run the following to connect to Azure AD.</span></span>

```powershell
Connect-AzureAD
```

<span data-ttu-id="6741a-205">Quando for solicitado, entre usando suas credenciais de administrador.</span><span class="sxs-lookup"><span data-stu-id="6741a-205">When you're prompted, sign in using your admin credentials.</span></span>

<span data-ttu-id="6741a-206">Para saber mais, consulte [conectar-se com o módulo do PowerShell do Azure Active Directory para Graph](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell#connect-with-the-azure-active-directory-powershell-for-graph-module).</span><span class="sxs-lookup"><span data-stu-id="6741a-206">To learn more, see [Connect with the Azure Active Directory PowerShell for Graph module](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell#connect-with-the-azure-active-directory-powershell-for-graph-module).</span></span>

##### <a name="install-and-connect-to-the-microsoft-teams-powershell-module"></a><span data-ttu-id="6741a-207">Instalar e conectar-se ao módulo do PowerShell do Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="6741a-207">Install and connect to the Microsoft Teams PowerShell module</span></span>

<span data-ttu-id="6741a-208">Execute o seguinte para instalar o [módulo do teams PowerShell](https://www.powershellgallery.com/packages/MicrosoftTeams) (se ainda não estiver instalado).</span><span class="sxs-lookup"><span data-stu-id="6741a-208">Run the following to install the [Teams PowerShell module](https://www.powershellgallery.com/packages/MicrosoftTeams) (if it's not already installed).</span></span> <span data-ttu-id="6741a-209">Verifique se você instalou a versão 1.0.5 ou posterior.</span><span class="sxs-lookup"><span data-stu-id="6741a-209">Make sure you install version 1.0.5 or later.</span></span>

```powershell
Install-Module -Name MicrosoftTeams
```

<span data-ttu-id="6741a-210">Execute o seguinte para se conectar ao Microsoft Teams e iniciar uma sessão.</span><span class="sxs-lookup"><span data-stu-id="6741a-210">Run the following to connect to Teams and start a session.</span></span>

```powershell
Connect-MicrosoftTeams
```
<span data-ttu-id="6741a-211">Quando for solicitado, entre usando as mesmas credenciais de administrador usadas para se conectar ao Azure AD.</span><span class="sxs-lookup"><span data-stu-id="6741a-211">When you're prompted, sign in using the same admin credentials you used to connect to Azure AD.</span></span>

#### <a name="identify-your-users"></a><span data-ttu-id="6741a-212">Identifique seus usuários</span><span class="sxs-lookup"><span data-stu-id="6741a-212">Identify your users</span></span>

<span data-ttu-id="6741a-213">Primeiro, execute o seguinte procedimento para identificar seus funcionários e professores por tipo de licença.</span><span class="sxs-lookup"><span data-stu-id="6741a-213">First, run the following to identify your staff and educators by license type.</span></span> <span data-ttu-id="6741a-214">Isso informa quais SKUs estão em uso em sua organização.</span><span class="sxs-lookup"><span data-stu-id="6741a-214">This tells you what SKUs are in use in your organization.</span></span> <span data-ttu-id="6741a-215">Em seguida, você pode identificar os funcionários e professores que têm uma SKU com docente atribuída.</span><span class="sxs-lookup"><span data-stu-id="6741a-215">You can then identify staff and educators that have a Faculty SKU assigned.</span></span>

```powershell
Get-AzureAdSubscribedSku | Select-Object -Property SkuPartNumber,SkuId
```

<span data-ttu-id="6741a-216">Que retorna:</span><span class="sxs-lookup"><span data-stu-id="6741a-216">Which returns:</span></span>

```
SkuPartNumber      SkuId
-------------      -----
M365EDU_A5_FACULTY e97c048c-37a4-45fb-ab50-922fbf07a370
M365EDU_A5_STUDENT 46c119d4-0379-4a9d-85e4-97c66d3f909e
```

<span data-ttu-id="6741a-217">Neste exemplo, a saída mostra que a licença doce SkuId é "e97c048c-37a4-45fb-ab50-922fbf07a370".</span><span class="sxs-lookup"><span data-stu-id="6741a-217">In this example, the output shows that the Faculty license SkuId is "e97c048c-37a4-45fb-ab50-922fbf07a370".</span></span>

> [!NOTE]
> <span data-ttu-id="6741a-218">Para ver uma lista de SKUs educacionais e IDs de SKU, consulte referência sobre o [SKU educacional](sku-reference-edu.md).</span><span class="sxs-lookup"><span data-stu-id="6741a-218">To see a list of Education SKUs and SKU IDs, see [Education SKU reference](sku-reference-edu.md).</span></span>

<span data-ttu-id="6741a-219">Em seguida, executamos o seguinte para identificar os usuários que têm essa licença e reuni-los juntos.</span><span class="sxs-lookup"><span data-stu-id="6741a-219">Next, we run the following to identify the users that have this license and collect them all together.</span></span>

```powershell
$faculty = Get-AzureADUser -All $true | Where-Object {($_.assignedLicenses).SkuId -contains "e97c048c-37a4-45fb-ab50-922fbf07a370"}
```

#### <a name="assign-a-policy-in-bulk"></a><span data-ttu-id="6741a-220">Atribuir uma política em massa</span><span class="sxs-lookup"><span data-stu-id="6741a-220">Assign a policy in bulk</span></span>

<span data-ttu-id="6741a-221">Agora, atribuímos as políticas adequadas aos usuários em massa.</span><span class="sxs-lookup"><span data-stu-id="6741a-221">Now, we assign the appropriate policies to users in bulk.</span></span> <span data-ttu-id="6741a-222">O número máximo de usuários para os quais você pode atribuir ou atualizar políticas é de 5.000 de cada vez.</span><span class="sxs-lookup"><span data-stu-id="6741a-222">The maximum number of users for which you can assign or update policies is 5,000 at a time.</span></span> <span data-ttu-id="6741a-223">Por exemplo, se você tiver mais de 5.000 funcionários e professores, será necessário enviar vários lotes.</span><span class="sxs-lookup"><span data-stu-id="6741a-223">For example, if you have more than 5,000 staff and educators, you'll need to submit multiple batches.</span></span>

<span data-ttu-id="6741a-224">Execute o seguinte para atribuir uma política de reunião personalizada chamada EducatorMeetingPolicy à sua equipe e educadores.</span><span class="sxs-lookup"><span data-stu-id="6741a-224">Run the following to assign a custom meeting policy named EducatorMeetingPolicy to your staff and educators.</span></span>

```powershell
New-CsBatchPolicyAssignmentOperation -PolicyType TeamsMeetingPolicy -PolicyName EducatorMeetingPolicy -Identity $faculty.ObjectId
```

> [!NOTE]
> <span data-ttu-id="6741a-225">Para atribuir um tipo de política diferente em massa, como TeamsMessagingPolicy, você precisará mudar ```PolicyType``` para a política que está atribuindo e ```PolicyName``` para o nome da política.</span><span class="sxs-lookup"><span data-stu-id="6741a-225">To assign a different policy type in bulk, like TeamsMessagingPolicy, you'll need to change ```PolicyType``` to the policy that you're assigning and ```PolicyName``` to the policy name.</span></span>

#### <a name="get-the-status-of-a-bulk-assignment"></a><span data-ttu-id="6741a-226">Obter o status de uma atribuição em massa</span><span class="sxs-lookup"><span data-stu-id="6741a-226">Get the status of a bulk assignment</span></span>

<span data-ttu-id="6741a-227">Cada atribuição em massa retorna uma ID de operação, que você pode usar para acompanhar o andamento das tarefas de política ou identificar quaisquer falhas que possam ocorrer.</span><span class="sxs-lookup"><span data-stu-id="6741a-227">Each bulk assignment returns an operation ID, which you can use to track the progress of the policy assignments or identify any failures that might occur.</span></span> <span data-ttu-id="6741a-228">Por exemplo, execute o seguinte:</span><span class="sxs-lookup"><span data-stu-id="6741a-228">For example, run the following:</span></span>

```powershell
Get-CsBatchPolicyAssignmentOperation -OperationId 3964004e-caa8-4eb4-b0d2-7dd2c8173c8c | fl
```

<span data-ttu-id="6741a-229">Para exibir o status da atribuição de cada usuário na operação em lotes, execute o seguinte.</span><span class="sxs-lookup"><span data-stu-id="6741a-229">To view the assignment status of each user in the batch operation, run the following.</span></span> <span data-ttu-id="6741a-230">Os detalhes de cada usuário estão na ```UserState``` propriedade.</span><span class="sxs-lookup"><span data-stu-id="6741a-230">Details of each user are in the ```UserState``` property.</span></span>

```powershell
Get-CsBatchPolicyAssignmentOperation -OperationId 3964004e-caa8-4eb4-b0d2-7dd2c8173c8c | Select -ExpandProperty UserState
```

#### <a name="assign-a-policy-in-bulk-if-you-have-more-than-5000-users"></a><span data-ttu-id="6741a-231">Atribuir uma política em massa se você tiver mais de 5.000 usuários</span><span class="sxs-lookup"><span data-stu-id="6741a-231">Assign a policy in bulk if you have more than 5,000 users</span></span>

<span data-ttu-id="6741a-232">Primeiro, execute o seguinte procedimento para ver quantas pessoas e professores você tem:</span><span class="sxs-lookup"><span data-stu-id="6741a-232">First, run the following to see how many staff and educators you have:</span></span>

```powershell
$faculty.count
```

<span data-ttu-id="6741a-233">Em vez de fornecer toda a lista de IDs de usuário, execute o seguinte para especificar o primeiro 5.000 e, em seguida, o próximo 5.000 e assim por diante.</span><span class="sxs-lookup"><span data-stu-id="6741a-233">Instead of providing the whole list of user IDs, run the following to specify the first 5,000, and then the next 5,000, and so on.</span></span>

```powershell
New-CsBatchPolicyAssignmentOperation -PolicyType TeamsMeetingPolicy -PolicyName EducatorMeetingPolicy -Identity $faculty[0..19999].ObjectId
```

<span data-ttu-id="6741a-234">Você pode alterar o intervalo de IDs de usuário até chegar à lista completa de usuários.</span><span class="sxs-lookup"><span data-stu-id="6741a-234">You can change the range of user IDs until you reach the full list of users.</span></span> <span data-ttu-id="6741a-235">Por exemplo, insira ```$faculty[0..4999``` para o primeiro lote, use ```$faculty[5000..9999``` para o segundo lote, insira ```$faculty[10000..14999``` para o terceiro lote e assim por diante.</span><span class="sxs-lookup"><span data-stu-id="6741a-235">For example, enter ```$faculty[0..4999``` for the first batch, use ```$faculty[5000..9999``` for the second batch, enter ```$faculty[10000..14999``` for the third batch, and so on.</span></span>

#### <a name="get-the-policies-assigned-to-a-user"></a><span data-ttu-id="6741a-236">Obter as políticas atribuídas a um usuário</span><span class="sxs-lookup"><span data-stu-id="6741a-236">Get the policies assigned to a user</span></span>

<span data-ttu-id="6741a-237">Execute o seguinte para ver todas as políticas atribuídas a um usuário específico.</span><span class="sxs-lookup"><span data-stu-id="6741a-237">Run the following to see all the policies that are assigned to a specific user.</span></span> <span data-ttu-id="6741a-238">O exemplo a seguir mostra como obter as políticas atribuídas ao hannah@contoso.com.</span><span class="sxs-lookup"><span data-stu-id="6741a-238">The following example shows you how to get the policies that are assigned to hannah@contoso.com.</span></span>

```powershell
Get-CsUserPolicyAssignment -Identity hannah@contoso.com
```

## <a name="faq"></a><span data-ttu-id="6741a-239">Perguntas frequentes</span><span class="sxs-lookup"><span data-stu-id="6741a-239">FAQ</span></span>

<span data-ttu-id="6741a-240">**Não estou familiarizado com o PowerShell para Teams. Onde posso saber mais?**</span><span class="sxs-lookup"><span data-stu-id="6741a-240">**I'm not familiar with PowerShell for Teams. Where can I learn more?**</span></span>

<span data-ttu-id="6741a-241">Para obter uma visão geral sobre como usar o PowerShell para gerenciar equipes, consulte [visão geral do teams PowerShell](teams-powershell-overview.md).</span><span class="sxs-lookup"><span data-stu-id="6741a-241">For an overview of using PowerShell to manage Teams, see [Teams PowerShell overview](teams-powershell-overview.md).</span></span> <span data-ttu-id="6741a-242">Para obter mais informações sobre os cmdlets usados neste artigo, consulte:</span><span class="sxs-lookup"><span data-stu-id="6741a-242">For more information about the cmdlets used in this article, see:</span></span>

- [<span data-ttu-id="6741a-243">New-CsGroupPolicyAssignment</span><span class="sxs-lookup"><span data-stu-id="6741a-243">New-CsGroupPolicyAssignment</span></span>](https://docs.microsoft.com/powershell/module/teams/new-csgrouppolicyassignment)
- [<span data-ttu-id="6741a-244">Get-CsGroupPolicyAssignment</span><span class="sxs-lookup"><span data-stu-id="6741a-244">Get-CsGroupPolicyAssignment</span></span>](https://docs.microsoft.com/powershell/module/teams/get-csgrouppolicyassignment)
- [<span data-ttu-id="6741a-245">New-CsBatchPolicyAssignmentOperation</span><span class="sxs-lookup"><span data-stu-id="6741a-245">New-CsBatchPolicyAssignmentOperation</span></span>](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation)
- [<span data-ttu-id="6741a-246">Get-CsBatchPolicyAssignmentOperation</span><span class="sxs-lookup"><span data-stu-id="6741a-246">Get-CsBatchPolicyAssignmentOperation</span></span>](https://docs.microsoft.com/powershell/module/teams/get-csbatchpolicyassignmentoperation)
- [<span data-ttu-id="6741a-247">Get-CsUserPolicyAssignment</span><span class="sxs-lookup"><span data-stu-id="6741a-247">Get-CsUserPolicyAssignment</span></span>](https://docs.microsoft.com/powershell/module/teams/get-csuserpolicyassignment)

## <a name="related-topics"></a><span data-ttu-id="6741a-248">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="6741a-248">Related topics</span></span>

- [<span data-ttu-id="6741a-249">Atribuir políticas aos usuários</span><span class="sxs-lookup"><span data-stu-id="6741a-249">Assign policies to your users</span></span>](assign-policies.md)
- [<span data-ttu-id="6741a-250">Políticas de equipe e pacotes de política para educação</span><span class="sxs-lookup"><span data-stu-id="6741a-250">Teams policies and policy packages for Education</span></span>](policy-packages-edu.md)
- [<span data-ttu-id="6741a-251">Gerenciar políticas de reunião no Teams</span><span class="sxs-lookup"><span data-stu-id="6741a-251">Manage meeting policies in Teams</span></span>](meeting-policies-in-teams.md)
