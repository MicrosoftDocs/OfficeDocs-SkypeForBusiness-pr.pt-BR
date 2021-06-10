---
title: Atribuir políticas a grandes conjuntos de usuários em sua escola
author: cichur
ms.author: v-cichur
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
description: Saiba como atribuir políticas a grandes conjuntos de usuários em sua instituição educacional com base na associação ao grupo ou diretamente por meio de uma atribuição em lotes para fins de escola remota (teleescola, teleescola).
f1keywords: ''
ms.openlocfilehash: f2d36db6a96f6a9a42590ada6600ef38738b30a9
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51092899"
---
# <a name="assign-policies-to-large-sets-of-users-in-your-school"></a><span data-ttu-id="6f08f-103">Atribuir políticas a grandes conjuntos de usuários em sua escola</span><span class="sxs-lookup"><span data-stu-id="6f08f-103">Assign policies to large sets of users in your school</span></span>

[!INCLUDE [policy-wizard-edu](includes/policy-wizard-edu.md)]

> [!NOTE]
> <span data-ttu-id="6f08f-104">Para saber mais sobre como atribuir políticas em Microsoft Teams, consulte Atribuir políticas aos usuários [em Teams](assign-policies.md).</span><span class="sxs-lookup"><span data-stu-id="6f08f-104">For the larger story on assigning policies in Microsoft Teams, see [Assign policies to your users in Teams](assign-policies.md).</span></span>

## <a name="overview"></a><span data-ttu-id="6f08f-105">Visão Geral</span><span class="sxs-lookup"><span data-stu-id="6f08f-105">Overview</span></span>

<span data-ttu-id="6f08f-106">Você precisa dar aos alunos e educadores acesso a diferentes recursos no Microsoft Teams?</span><span class="sxs-lookup"><span data-stu-id="6f08f-106">Do you need to give your students and educators access to different features in Microsoft Teams?</span></span> <span data-ttu-id="6f08f-107">Você pode identificar rapidamente os usuários em sua organização por tipo de licença e atribuí-los a política apropriada.</span><span class="sxs-lookup"><span data-stu-id="6f08f-107">You can quickly identify the users in your organization by license type and then assign them the appropriate policy.</span></span> <span data-ttu-id="6f08f-108">Este tutorial mostra como atribuir uma política de reunião a grandes conjuntos de usuários em sua escola.</span><span class="sxs-lookup"><span data-stu-id="6f08f-108">This tutorial shows you how to assign a meeting policy to large sets of users in your school.</span></span> <span data-ttu-id="6f08f-109">Você pode atribuir políticas usando o centro de administração Microsoft Teams e o PowerShell e mostraremos as duas maneiras.</span><span class="sxs-lookup"><span data-stu-id="6f08f-109">You can assign policies using the Microsoft Teams admin center and PowerShell and we'll show you both ways.</span></span>

<span data-ttu-id="6f08f-110">Você pode atribuir uma política de reunião a um grupo de segurança de que os usuários são membros ou diretamente aos usuários em escala por meio de uma atribuição de política em lotes.</span><span class="sxs-lookup"><span data-stu-id="6f08f-110">You can assign a meeting policy to a security group that the users are members of or directly to users at scale through a batch policy assignment.</span></span> <span data-ttu-id="6f08f-111">Você aprenderá a:</span><span class="sxs-lookup"><span data-stu-id="6f08f-111">You'll learn how to:</span></span>

- <span data-ttu-id="6f08f-112">**Use [a atribuição de política](#assign-a-policy-to-a-group) a grupos para atribuir uma política de reunião a um grupo de segurança (recomendado)**.</span><span class="sxs-lookup"><span data-stu-id="6f08f-112">**Use [policy assignment to groups](#assign-a-policy-to-a-group) to assign a meeting policy to a security group (recommended)**.</span></span> <span data-ttu-id="6f08f-113">Esse método permite atribuir uma política com base na associação ao grupo.</span><span class="sxs-lookup"><span data-stu-id="6f08f-113">This method lets you assign a policy based on group membership.</span></span> <span data-ttu-id="6f08f-114">Você pode atribuir uma política a um grupo de segurança ou lista de distribuição.</span><span class="sxs-lookup"><span data-stu-id="6f08f-114">You can assign a policy to a security group or distribution list.</span></span> <span data-ttu-id="6f08f-115">À medida que os membros são adicionados ou removidos do grupo, suas atribuições de política herdadas são atualizadas de acordo.</span><span class="sxs-lookup"><span data-stu-id="6f08f-115">As members are added to or removed from the group, their inherited policy assignments are updated accordingly.</span></span> <span data-ttu-id="6f08f-116">Recomendamos que você use esse método porque reduz o tempo para gerenciar políticas para novos usuários ou quando as funções dos usuários mudam.</span><span class="sxs-lookup"><span data-stu-id="6f08f-116">We recommend you use this method because it reduces the time to manage policies for new users or when users' roles change.</span></span> <span data-ttu-id="6f08f-117">Esse método funciona melhor para grupos de até 50.000 usuários, mas também funcionará com grupos maiores.</span><span class="sxs-lookup"><span data-stu-id="6f08f-117">This method works best for groups of up to 50,000 users but will also work with larger groups.</span></span>

- <span data-ttu-id="6f08f-118">**Use [a atribuição de política em lote](assign-policies.md#assign-a-policy-to-a-batch-of-users) para atribuir uma política de reunião diretamente aos usuários em massa.**</span><span class="sxs-lookup"><span data-stu-id="6f08f-118">**Use [batch policy assignment](assign-policies.md#assign-a-policy-to-a-batch-of-users) to assign a meeting policy directly to users in bulk**.</span></span> <span data-ttu-id="6f08f-119">Você pode atribuir uma política para até 5.000 usuários por vez.</span><span class="sxs-lookup"><span data-stu-id="6f08f-119">You can assign a policy for up to 5,000 users at a time.</span></span> <span data-ttu-id="6f08f-120">Se você tiver mais de 5.000 usuários, poderá enviar vários lotes.</span><span class="sxs-lookup"><span data-stu-id="6f08f-120">If you have more than 5,000 users, you can submit multiple batches.</span></span> <span data-ttu-id="6f08f-121">Com esse método, quando você tiver novos usuários, precisará executar a atribuição em lotes para atribuir a política a esses novos usuários.</span><span class="sxs-lookup"><span data-stu-id="6f08f-121">With this method, when you have new users, you'll need to re-run the batch assignment to assign the policy to those new users.</span></span>

<span data-ttu-id="6f08f-122">Lembre-se de Teams, os usuários receberão automaticamente a política Global (padrão em toda a organização) para um tipo de política Teams, a menos que você crie e atribua uma política personalizada.</span><span class="sxs-lookup"><span data-stu-id="6f08f-122">Remember that in Teams, users automatically get the Global (Org-wide default) policy for a Teams policy type unless you create and assign a custom policy.</span></span> <span data-ttu-id="6f08f-123">Como a população de alunos geralmente é o maior conjunto de usuários e eles geralmente recebem as configurações mais restritivas, recomendamos que você faça o seguinte:</span><span class="sxs-lookup"><span data-stu-id="6f08f-123">Because the student population is often the largest set of users and they often receive the most restrictive settings, we recommend that you do the following:</span></span>

- <span data-ttu-id="6f08f-124">Crie uma política personalizada que permita recursos fundamentais, como chat privado e agendamento de reuniões e atribua a política à sua equipe e educadores.</span><span class="sxs-lookup"><span data-stu-id="6f08f-124">Create a custom policy that allows core capabilities such as private chat and meeting scheduling and assign the policy to your staff and educators.</span></span>
- <span data-ttu-id="6f08f-125">Atribua a política personalizada aos seus funcionários e educadores.</span><span class="sxs-lookup"><span data-stu-id="6f08f-125">Assign the custom policy to your staff and educators.</span></span>
- <span data-ttu-id="6f08f-126">Edite e aplique a política Global (padrão em toda a organização) para restringir recursos para alunos.</span><span class="sxs-lookup"><span data-stu-id="6f08f-126">Edit and apply the Global (Org-wide default) policy to restrict capabilities for students.</span></span>

<span data-ttu-id="6f08f-127">Lembre-se de que a política Global será aplicada a todos os usuários em sua escola até que você crie uma política personalizada e atribua-a à sua equipe e educadores.</span><span class="sxs-lookup"><span data-stu-id="6f08f-127">Keep in mind that the Global policy will apply to all users in your school until you create a custom policy and assign it to your staff and educators.</span></span>

<span data-ttu-id="6f08f-128">Neste tutorial, os alunos receberão a política de reunião global e atribuiremos uma política de reunião personalizada chamada EducatorMeetingPolicy a funcionários e educadores.</span><span class="sxs-lookup"><span data-stu-id="6f08f-128">In this tutorial, students will get the Global meeting policy and we'll assign a custom meeting policy named EducatorMeetingPolicy to staff and educators.</span></span> <span data-ttu-id="6f08f-129">Presumimos que você editou a política global para adaptar as configurações de reunião para alunos e criou uma política personalizada que define [a](policy-packages-edu.md) experiência de reunião para funcionários e educadores.</span><span class="sxs-lookup"><span data-stu-id="6f08f-129">We assume that you've edited the Global policy to tailor meeting settings for students and [created a custom policy](policy-packages-edu.md) that defines the meeting experience for staff and educators.</span></span>

![Captura de tela da página Políticas de reunião no Teams de administração](media/batch-group-policy-assignment-edu-meeting-policies.png)

## <a name="assign-a-policy-to-a-group"></a><span data-ttu-id="6f08f-131">Atribuir uma política a um grupo</span><span class="sxs-lookup"><span data-stu-id="6f08f-131">Assign a policy to a group</span></span>

<span data-ttu-id="6f08f-132">Siga estas etapas para criar um grupo de segurança para sua equipe e educadores e atribuir uma política de reunião personalizada chamada EducatorMeetingPolicy a esse grupo de segurança.</span><span class="sxs-lookup"><span data-stu-id="6f08f-132">Follow these steps to create a security group for your staff and educators, and then assign a custom meeting policy named EducatorMeetingPolicy to that security group.</span></span>

### <a name="before-you-get-started"></a><span data-ttu-id="6f08f-133">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="6f08f-133">Before you get started</span></span>

> [!IMPORTANT]
> <span data-ttu-id="6f08f-134">Quando você atribui uma política a um grupo, a atribuição de política é propagada aos membros do grupo de acordo com as regras de precedência.</span><span class="sxs-lookup"><span data-stu-id="6f08f-134">When you assign a policy to a group, the policy assignment is propagated to members of the group according to precedence rules.</span></span> <span data-ttu-id="6f08f-135">Por exemplo, se um usuário recebe diretamente uma política (individualmente ou por meio de uma atribuição em lotes), essa política tem precedência sobre uma política herdada de um grupo.</span><span class="sxs-lookup"><span data-stu-id="6f08f-135">For example, if a user is directly assigned a policy (either individually or through a batch assignment), that policy takes precedence over a policy that's inherited from a group.</span></span> <span data-ttu-id="6f08f-136">Isso também significa que, se um usuário tiver uma política de reunião atribuída diretamente a ele, você terá que remover essa política de reunião do usuário antes que ele possa herdar uma política de reunião de um grupo de segurança.</span><span class="sxs-lookup"><span data-stu-id="6f08f-136">This also means that if a user has a meeting policy that was directly assigned to them, you'll have to remove that meeting policy from the user before they can inherit a meeting policy from a security group.</span></span>

<span data-ttu-id="6f08f-137">Antes de começar, é importante entender as regras [de precedência](assign-policies.md#precedence-rules) e a classificação [de atribuição de grupo.](assign-policies.md#group-assignment-ranking)</span><span class="sxs-lookup"><span data-stu-id="6f08f-137">Before you get started, it's important to understand [precedence rules](assign-policies.md#precedence-rules) and [group assignment ranking](assign-policies.md#group-assignment-ranking).</span></span> <span data-ttu-id="6f08f-138">Leia e entenda os conceitos em O que você precisa saber sobre a atribuição de **política a [grupos.](assign-policies.md#what-you-need-to-know-about-policy-assignment-to-groups)**</span><span class="sxs-lookup"><span data-stu-id="6f08f-138">**Make sure that you read and understand the concepts in [What you need to know about policy assignment to groups](assign-policies.md#what-you-need-to-know-about-policy-assignment-to-groups)**.</span></span>

<span data-ttu-id="6f08f-139">Você precisará concluir todas essas etapas para que sua equipe e educadores herdem uma política de reunião de um grupo de segurança.</span><span class="sxs-lookup"><span data-stu-id="6f08f-139">You'll need to complete all these steps for your staff and educators to inherit a meeting policy from a security group.</span></span>

1. <span data-ttu-id="6f08f-140">[Criar grupos de segurança](#create-security-groups).</span><span class="sxs-lookup"><span data-stu-id="6f08f-140">[Create security groups](#create-security-groups).</span></span>
2. <span data-ttu-id="6f08f-141">[Atribua uma política a um grupo de segurança](#assign-a-policy-to-a-security-group).</span><span class="sxs-lookup"><span data-stu-id="6f08f-141">[Assign a policy to a security group](#assign-a-policy-to-a-security-group).</span></span>
3. <span data-ttu-id="6f08f-142">[Remova uma política que foi atribuída diretamente aos usuários](#remove-a-policy-that-was-directly-assigned-to-users).</span><span class="sxs-lookup"><span data-stu-id="6f08f-142">[Remove a policy that was directly assigned to users](#remove-a-policy-that-was-directly-assigned-to-users).</span></span>

### <a name="create-security-groups"></a><span data-ttu-id="6f08f-143">Criar grupos de segurança</span><span class="sxs-lookup"><span data-stu-id="6f08f-143">Create security groups</span></span>

<span data-ttu-id="6f08f-144">Primeiro, crie um grupo de segurança para sua equipe e educadores.</span><span class="sxs-lookup"><span data-stu-id="6f08f-144">First, create a security group for your staff and educators.</span></span>

<span data-ttu-id="6f08f-145">Com [School Data Sync](/SchoolDataSync/) (SDS), você pode facilmente criar educadores e [alunos](/SchoolDataSync/edu-security-groups) de grupos de segurança em sua escola.</span><span class="sxs-lookup"><span data-stu-id="6f08f-145">With [School Data Sync](/SchoolDataSync/) (SDS), you can [easily create security groups educators and students](/SchoolDataSync/edu-security-groups) in your school.</span></span> <span data-ttu-id="6f08f-146">Recomendamos que você use o SDS para criar os grupos de segurança necessários para gerenciar políticas para sua escola.</span><span class="sxs-lookup"><span data-stu-id="6f08f-146">We recommend that you use SDS to create the security groups you need to manage policies for your school.</span></span>

<span data-ttu-id="6f08f-147">Se você não conseguir implantar o SDS em seu ambiente, use este script do [PowerShell](scripts/powershell-script-security-groups-edu.md) para criar dois grupos de segurança, um para todos os funcionários e educadores com uma licença de Docente atribuída e outro para todos os alunos que têm uma licença de aluno atribuída.</span><span class="sxs-lookup"><span data-stu-id="6f08f-147">If you're unable to deploy SDS within your environment, use [this PowerShell script](scripts/powershell-script-security-groups-edu.md) to create two security groups, one for all staff and educators who have a Faculty license assigned and another for all students who have a Student license assigned.</span></span> <span data-ttu-id="6f08f-148">Você precisará executar esse script rotineiramente para manter os grupos atualizados e atualizados.</span><span class="sxs-lookup"><span data-stu-id="6f08f-148">You'll need to run this script routinely to keep the groups fresh and up to date.</span></span>

### <a name="assign-a-policy-to-a-security-group"></a><span data-ttu-id="6f08f-149">Atribuir uma política a um grupo de segurança</span><span class="sxs-lookup"><span data-stu-id="6f08f-149">Assign a policy to a security group</span></span>

#### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="6f08f-150">Usando o centro de administração do Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="6f08f-150">Using the Microsoft Teams admin center</span></span>

> [!NOTE]
> <span data-ttu-id="6f08f-151">Atualmente, a atribuição de política para grupos usando o centro de administração do Microsoft Teams está disponível apenas para a política de chamada do Teams, a política de estacionamento de chamada do Teams, Teams política de Teams, Teams política de eventos ao vivo, Teams política de reunião e Teams de mensagens.</span><span class="sxs-lookup"><span data-stu-id="6f08f-151">Currently, policy assignment to groups using the Microsoft Teams admin center is only available for Teams calling policy, Teams call park policy, Teams policy, Teams live events policy, Teams meeting policy, and Teams messaging policy.</span></span> <span data-ttu-id="6f08f-152">Para outros tipos de política, use o PowerShell.</span><span class="sxs-lookup"><span data-stu-id="6f08f-152">For other policy types, use PowerShell.</span></span>

1. <span data-ttu-id="6f08f-153">Na barra de navegação à esquerda do Centro de Administração do Microsoft Teams, vá para **Reuniões** > **Políticas de Reunião**.</span><span class="sxs-lookup"><span data-stu-id="6f08f-153">In the left navigation of the Microsoft Teams admin center, go to **Meetings** > **Meeting policies**.</span></span>
2. <span data-ttu-id="6f08f-154">Selecione a **guia Atribuição de política de** grupo.</span><span class="sxs-lookup"><span data-stu-id="6f08f-154">Select the **Group policy assignment** tab.</span></span>
3. <span data-ttu-id="6f08f-155">Selecione **Adicionar grupo** e, em seguida, no painel Atribuir **política** ao grupo, faça o seguinte:</span><span class="sxs-lookup"><span data-stu-id="6f08f-155">Select **Add group**, and then in the **Assign policy to group** pane, do the following:</span></span>

    ![Captura de tela do painel Editar configurações, mostrando a política de reunião](media/batch-group-policy-assignment-edu-group.png)
    1. <span data-ttu-id="6f08f-157">Na caixa **Selecionar um grupo,** pesquise e adicione o grupo de segurança que contém sua equipe e educadores.</span><span class="sxs-lookup"><span data-stu-id="6f08f-157">In the **Select a group** box, search for and add the security group that contains your staff and educators.</span></span>
    2. <span data-ttu-id="6f08f-158">Na caixa **Selecionar classificação,** digite **1**.</span><span class="sxs-lookup"><span data-stu-id="6f08f-158">In the **Select rank** box, enter **1**.</span></span>
    3. <span data-ttu-id="6f08f-159">Na caixa **Selecionar uma política,** selecione **EducatorMeetingPolicy**.</span><span class="sxs-lookup"><span data-stu-id="6f08f-159">In the **Select a policy** box, select **EducatorMeetingPolicy**.</span></span>
    4. <span data-ttu-id="6f08f-160">Selecione **Aplicar**.</span><span class="sxs-lookup"><span data-stu-id="6f08f-160">Select **Apply**.</span></span>

<span data-ttu-id="6f08f-161">Para remover uma atribuição de política de grupo, na **guia** Atribuição de política de grupo da página de política, selecione a atribuição de grupo e selecione **Remover**.</span><span class="sxs-lookup"><span data-stu-id="6f08f-161">To remove a group policy assignment, on the **Group policy assignment** tab of the policy page, select the group assignment, and then select **Remove**.</span></span>

<span data-ttu-id="6f08f-162">Para alterar a classificação de uma atribuição de grupo, você precisa primeiro remover a atribuição de política de grupo.</span><span class="sxs-lookup"><span data-stu-id="6f08f-162">To change the ranking of a group assignment, you have to first remove the group policy assignment.</span></span> <span data-ttu-id="6f08f-163">Em seguida, siga as etapas acima para atribuir a política a um grupo.</span><span class="sxs-lookup"><span data-stu-id="6f08f-163">Then, follow the steps above to assign the policy to a group.</span></span>

#### <a name="using-powershell"></a><span data-ttu-id="6f08f-164">Usando o Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="6f08f-164">Using PowerShell</span></span>

> [!NOTE]
> <span data-ttu-id="6f08f-165">Atualmente, a atribuição de política a grupos usando o PowerShell não está disponível para todos os tipos Teams de política.</span><span class="sxs-lookup"><span data-stu-id="6f08f-165">Currently, policy assignment to groups using PowerShell isn't available for all Teams policy types.</span></span> <span data-ttu-id="6f08f-166">Consulte [New-CsGroupPolicyAssignment para](/powershell/module/teams/new-csgrouppolicyassignment) a lista de tipos de política com suporte.</span><span class="sxs-lookup"><span data-stu-id="6f08f-166">See [New-CsGroupPolicyAssignment](/powershell/module/teams/new-csgrouppolicyassignment) for the list of supported policy types.</span></span>

##### <a name="install-and-connect-to-the-microsoft-teams-powershell-module"></a><span data-ttu-id="6f08f-167">Instalar e conectar ao módulo Microsoft Teams PowerShell</span><span class="sxs-lookup"><span data-stu-id="6f08f-167">Install and connect to the Microsoft Teams PowerShell module</span></span>

<span data-ttu-id="6f08f-168">Execute o seguinte para instalar o [Teams do PowerShell](https://www.powershellgallery.com/packages/MicrosoftTeams) (se ainda não estiver instalado).</span><span class="sxs-lookup"><span data-stu-id="6f08f-168">Run the following to install the [Teams PowerShell module](https://www.powershellgallery.com/packages/MicrosoftTeams) (if it's not already installed).</span></span> <span data-ttu-id="6f08f-169">Instale a versão 1.0.5 ou posterior.</span><span class="sxs-lookup"><span data-stu-id="6f08f-169">Make sure you install version 1.0.5 or later.</span></span>

```powershell
Install-Module -Name MicrosoftTeams
```

<span data-ttu-id="6f08f-170">Execute o seguinte para se conectar ao Teams e iniciar uma sessão.</span><span class="sxs-lookup"><span data-stu-id="6f08f-170">Run the following to connect to Teams and start a session.</span></span>

```powershell
Connect-MicrosoftTeams
```

<span data-ttu-id="6f08f-171">Quando for solicitado, entre usando suas credenciais de administrador.</span><span class="sxs-lookup"><span data-stu-id="6f08f-171">When you're prompted, sign in using your admin credentials.</span></span>

##### <a name="assign-a-policy-to-a-group"></a><span data-ttu-id="6f08f-172">Atribuir uma política a um grupo</span><span class="sxs-lookup"><span data-stu-id="6f08f-172">Assign a policy to a group</span></span>

<span data-ttu-id="6f08f-173">Execute o seguinte para atribuir a política de reunião chamada EducatorMeetingPolicy ao grupo de segurança que contém sua equipe e educadores e definir a classificação de atribuição como 1.</span><span class="sxs-lookup"><span data-stu-id="6f08f-173">Run the following to assign the meeting policy named EducatorMeetingPolicy to the security group that contains your staff and educators and set the assignment ranking to 1.</span></span> <span data-ttu-id="6f08f-174">Você pode especificar um grupo de segurança usando a ID do objeto, o endereço SIP (Session Initiation Protocol) ou o endereço de email.</span><span class="sxs-lookup"><span data-stu-id="6f08f-174">You can specify a security group by using the object Id, Session Initiation Protocol (SIP) address, or email address.</span></span> <span data-ttu-id="6f08f-175">Neste exemplo, usamos um endereço de email (staff-faculty@contoso.com).</span><span class="sxs-lookup"><span data-stu-id="6f08f-175">In this example, we use an email address (staff-faculty@contoso.com).</span></span>

```powershell
New-CsGroupPolicyAssignment -GroupId staff-faculty@contoso.com -PolicyType TeamsMeetingPolicy -PolicyName "EducatorMeetingPolicy" -Rank 1
```

### <a name="remove-a-policy-that-was-directly-assigned-to-users"></a><span data-ttu-id="6f08f-176">Remover uma política que foi atribuída diretamente aos usuários</span><span class="sxs-lookup"><span data-stu-id="6f08f-176">Remove a policy that was directly assigned to users</span></span>

<span data-ttu-id="6f08f-177">Lembre-se de que, se um usuário tiver sido atribuído diretamente a uma política (individualmente ou por meio de uma atribuição em lotes), essa política tem precedência.</span><span class="sxs-lookup"><span data-stu-id="6f08f-177">Remember that if a user was directly assigned a policy (either individually or through a batch assignment), that policy takes precedence.</span></span> <span data-ttu-id="6f08f-178">Isso significa que, se um usuário tiver uma política de reunião atribuída diretamente a ele, você terá que remover essa política de reunião do usuário antes que ele possa herdar uma política de reunião de um grupo de segurança.</span><span class="sxs-lookup"><span data-stu-id="6f08f-178">This means that if a user has a meeting policy that was directly assigned to them, you'll have to remove that meeting policy from the user before they can inherit a meeting policy from a security group.</span></span>

<span data-ttu-id="6f08f-179">Para saber mais, confira [O que você precisa saber sobre a atribuição de política a grupos](assign-policies.md#what-you-need-to-know-about-policy-assignment-to-groups).</span><span class="sxs-lookup"><span data-stu-id="6f08f-179">To learn more, see [What you need to know about policy assignment to groups](assign-policies.md#what-you-need-to-know-about-policy-assignment-to-groups).</span></span>

<span data-ttu-id="6f08f-180">Siga estas etapas para remover a política de reunião que foi atribuída diretamente à sua equipe e educadores.</span><span class="sxs-lookup"><span data-stu-id="6f08f-180">Follow these steps to remove the meeting policy that was directly assigned to your staff and educators.</span></span>

#### <a name="install-and-connect-to-the-microsoft-teams-powershell-module"></a><span data-ttu-id="6f08f-181">Instalar e conectar ao módulo Microsoft Teams PowerShell</span><span class="sxs-lookup"><span data-stu-id="6f08f-181">Install and connect to the Microsoft Teams PowerShell module</span></span>

<span data-ttu-id="6f08f-182">Execute o seguinte para instalar o [Teams do PowerShell](https://www.powershellgallery.com/packages/MicrosoftTeams) (se ainda não estiver instalado).</span><span class="sxs-lookup"><span data-stu-id="6f08f-182">Run the following to install the [Teams PowerShell module](https://www.powershellgallery.com/packages/MicrosoftTeams) (if it's not already installed).</span></span> <span data-ttu-id="6f08f-183">Instale a versão 1.0.5 ou posterior.</span><span class="sxs-lookup"><span data-stu-id="6f08f-183">Make sure you install version 1.0.5 or later.</span></span>

```powershell
Install-Module -Name MicrosoftTeams
```

<span data-ttu-id="6f08f-184">Execute o seguinte para se conectar ao Teams e iniciar uma sessão.</span><span class="sxs-lookup"><span data-stu-id="6f08f-184">Run the following to connect to Teams and start a session.</span></span>

```powershell
Connect-MicrosoftTeams
```

<span data-ttu-id="6f08f-185">Quando for solicitado, entre usando as mesmas credenciais de administrador usadas para se conectar ao Azure AD.</span><span class="sxs-lookup"><span data-stu-id="6f08f-185">When you're prompted, sign in using the same admin credentials you used to connect to Azure AD.</span></span>

#### <a name="unassign-a-policy-that-was-directly-assigned-to-users"></a><span data-ttu-id="6f08f-186">Desaignar uma política que foi atribuída diretamente aos usuários</span><span class="sxs-lookup"><span data-stu-id="6f08f-186">Unassign a policy that was directly assigned to users</span></span>

<span data-ttu-id="6f08f-187">Execute o seguinte para remover uma política de reunião dos usuários que foram atribuídos diretamente a essa política.</span><span class="sxs-lookup"><span data-stu-id="6f08f-187">Run the following to remove a meeting policy from users who were directly assigned that policy.</span></span> <span data-ttu-id="6f08f-188">Você pode especificar usuários por endereço de email ou ID de objeto.</span><span class="sxs-lookup"><span data-stu-id="6f08f-188">You can specify users by email address or object ID.</span></span>

<span data-ttu-id="6f08f-189">Neste exemplo, a política de reunião é removida dos usuários especificados por seu endereço de email.</span><span class="sxs-lookup"><span data-stu-id="6f08f-189">In this example, the meeting policy is removed from users specified by their email address.</span></span>

```powershell
$users_ids = @("reda@contoso.com", "nikica@contoso.com", "jamie@contoso.com")
New-CsBatchPolicyAssignmentOperation -PolicyType TeamsMeetingPolicy -PolicyName $null -Identity $users_ids -OperationName "Unassign meeting policy"
```

<span data-ttu-id="6f08f-190">Neste exemplo, a política de reunião é removida da lista de usuários em um arquivo de texto chamado user_ids.txt.</span><span class="sxs-lookup"><span data-stu-id="6f08f-190">In this example, the meeting policy is removed from the list of users in a text file named user_ids.txt.</span></span>

```powershell
$user_ids = Get-Content .\users_ids.txt
New-CsBatchPolicyAssignmentOperation -PolicyType TeamsMeetingPolicy -PolicyName $null -Identity $users_ids -OperationName "Unassign meeting policy"
```

##### <a name="get-policy-assignments-for-a-group"></a><span data-ttu-id="6f08f-191">Obter atribuições de política para um grupo</span><span class="sxs-lookup"><span data-stu-id="6f08f-191">Get policy assignments for a group</span></span>

<span data-ttu-id="6f08f-192">Execute o seguinte para ver todas as políticas atribuídas a um grupo de segurança específico.</span><span class="sxs-lookup"><span data-stu-id="6f08f-192">Run the following to see all the policies assigned to a specific security group.</span></span> <span data-ttu-id="6f08f-193">Observe que os grupos sempre são listados pela ID do grupo, mesmo que seu endereço SIP ou endereço de email seja usado para atribuir a política.</span><span class="sxs-lookup"><span data-stu-id="6f08f-193">Note that groups are always listed by their group ID even if its SIP address or email address was used to assign the policy.</span></span>

```powershell
Get-CsGroupPolicyAssignment -GroupId staff-faculty@contoso.com

```

##### <a name="get-the-policies-assigned-to-a-user"></a><span data-ttu-id="6f08f-194">Obter as políticas atribuídas a um usuário</span><span class="sxs-lookup"><span data-stu-id="6f08f-194">Get the policies assigned to a user</span></span>

<span data-ttu-id="6f08f-195">Execute o seguinte para ver todas as políticas atribuídas a um usuário específico.</span><span class="sxs-lookup"><span data-stu-id="6f08f-195">Run the following to see all the policies that are assigned to a specific user.</span></span> <span data-ttu-id="6f08f-196">O exemplo a seguir mostra como obter as políticas atribuídas a reda@contoso.com.</span><span class="sxs-lookup"><span data-stu-id="6f08f-196">The following example shows you how to get the policies that are assigned to reda@contoso.com.</span></span>

```powershell
Get-CsUserPolicyAssignment -Identity reda@contoso.com
```

## <a name="assign-a-policy-to-a-batch-of-users"></a><span data-ttu-id="6f08f-197">Atribuir uma política a um lote de usuários</span><span class="sxs-lookup"><span data-stu-id="6f08f-197">Assign a policy to a batch of users</span></span>

<span data-ttu-id="6f08f-198">Siga estas etapas para atribuir uma política de reunião personalizada chamada EducatorMeetingPolicy diretamente à sua equipe e educadores em massa.</span><span class="sxs-lookup"><span data-stu-id="6f08f-198">Follow these steps to assign a custom meeting policy named EducatorMeetingPolicy directly to your staff and educators in bulk.</span></span>

### <a name="using-powershell"></a><span data-ttu-id="6f08f-199">Usando o Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="6f08f-199">Using PowerShell</span></span>

#### <a name="connect-to-the-azure-ad-powershell-for-graph-module-and-the-teams-powershell-module"></a><span data-ttu-id="6f08f-200">Conexão o módulo powershell do Azure AD para Graph e o módulo Teams PowerShell</span><span class="sxs-lookup"><span data-stu-id="6f08f-200">Connect to the Azure AD PowerShell for Graph module and the Teams PowerShell module</span></span>

<span data-ttu-id="6f08f-201">Antes de executar as etapas deste artigo, você precisará instalar e se conectar ao módulo do Azure AD PowerShell para Graph (para identificar usuários por suas licenças atribuídas) e ao módulo do Microsoft Teams PowerShell (para atribuir as políticas a esses usuários).</span><span class="sxs-lookup"><span data-stu-id="6f08f-201">Before you perform the steps in this article, you'll need to install and connect to the Azure AD PowerShell for Graph module (to identify users by their assigned licenses) and the Microsoft Teams PowerShell module (to assign the policies to those users).</span></span>

##### <a name="install-and-connect-to-the-azure-ad-powershell-for-graph-module"></a><span data-ttu-id="6f08f-202">Instalar e conectar-se ao Azure AD PowerShell para Graph módulo</span><span class="sxs-lookup"><span data-stu-id="6f08f-202">Install and connect to the Azure AD PowerShell for Graph module</span></span>

<span data-ttu-id="6f08f-203">Abra um prompt de Windows PowerShell de comando (execute o Windows PowerShell como administrador) e execute o seguinte para instalar o Azure Active Directory PowerShell para Graph módulo.</span><span class="sxs-lookup"><span data-stu-id="6f08f-203">Open an elevated Windows PowerShell command prompt (run Windows PowerShell as an administrator), and then run the following to install the Azure Active Directory PowerShell for Graph module.</span></span>

```powershell
Install-Module -Name AzureAD
```

<span data-ttu-id="6f08f-204">Execute o seguinte para se conectar ao Azure AD.</span><span class="sxs-lookup"><span data-stu-id="6f08f-204">Run the following to connect to Azure AD.</span></span>

```powershell
Connect-AzureAD
```

<span data-ttu-id="6f08f-205">Quando for solicitado, entre usando suas credenciais de administrador.</span><span class="sxs-lookup"><span data-stu-id="6f08f-205">When you're prompted, sign in using your admin credentials.</span></span>

<span data-ttu-id="6f08f-206">Para saber mais, consulte [Conexão o Azure Active Directory PowerShell para Graph módulo](/office365/enterprise/powershell/connect-to-office-365-powershell#connect-with-the-azure-active-directory-powershell-for-graph-module).</span><span class="sxs-lookup"><span data-stu-id="6f08f-206">To learn more, see [Connect with the Azure Active Directory PowerShell for Graph module](/office365/enterprise/powershell/connect-to-office-365-powershell#connect-with-the-azure-active-directory-powershell-for-graph-module).</span></span>

##### <a name="install-and-connect-to-the-microsoft-teams-powershell-module"></a><span data-ttu-id="6f08f-207">Instalar e conectar ao módulo Microsoft Teams PowerShell</span><span class="sxs-lookup"><span data-stu-id="6f08f-207">Install and connect to the Microsoft Teams PowerShell module</span></span>

<span data-ttu-id="6f08f-208">Execute o seguinte para instalar o [Teams do PowerShell](https://www.powershellgallery.com/packages/MicrosoftTeams) (se ainda não estiver instalado).</span><span class="sxs-lookup"><span data-stu-id="6f08f-208">Run the following to install the [Teams PowerShell module](https://www.powershellgallery.com/packages/MicrosoftTeams) (if it's not already installed).</span></span> <span data-ttu-id="6f08f-209">Instale a versão 1.0.5 ou posterior.</span><span class="sxs-lookup"><span data-stu-id="6f08f-209">Make sure you install version 1.0.5 or later.</span></span>

```powershell
Install-Module -Name MicrosoftTeams
```

<span data-ttu-id="6f08f-210">Execute o seguinte para se conectar ao Teams e iniciar uma sessão.</span><span class="sxs-lookup"><span data-stu-id="6f08f-210">Run the following to connect to Teams and start a session.</span></span>

```powershell
Connect-MicrosoftTeams
```

<span data-ttu-id="6f08f-211">Quando for solicitado, entre usando as mesmas credenciais de administrador usadas para se conectar ao Azure AD.</span><span class="sxs-lookup"><span data-stu-id="6f08f-211">When you're prompted, sign in using the same admin credentials you used to connect to Azure AD.</span></span>

#### <a name="identify-your-users"></a><span data-ttu-id="6f08f-212">Identificar seus usuários</span><span class="sxs-lookup"><span data-stu-id="6f08f-212">Identify your users</span></span>

<span data-ttu-id="6f08f-213">Primeiro, execute o seguinte para identificar sua equipe e educadores por tipo de licença.</span><span class="sxs-lookup"><span data-stu-id="6f08f-213">First, run the following to identify your staff and educators by license type.</span></span> <span data-ttu-id="6f08f-214">Isso informa quais SKUs estão em uso em sua organização.</span><span class="sxs-lookup"><span data-stu-id="6f08f-214">This tells you what SKUs are in use in your organization.</span></span> <span data-ttu-id="6f08f-215">Em seguida, você pode identificar funcionários e educadores que tenham um SKU docente atribuído.</span><span class="sxs-lookup"><span data-stu-id="6f08f-215">You can then identify staff and educators that have a Faculty SKU assigned.</span></span>

```powershell
Get-AzureAdSubscribedSku | Select-Object -Property SkuPartNumber,SkuId
```

<span data-ttu-id="6f08f-216">Que retorna:</span><span class="sxs-lookup"><span data-stu-id="6f08f-216">Which returns:</span></span>

```
SkuPartNumber      SkuId
-------------      -----
M365EDU_A5_FACULTY e97c048c-37a4-45fb-ab50-922fbf07a370
M365EDU_A5_STUDENT 46c119d4-0379-4a9d-85e4-97c66d3f909e
```

<span data-ttu-id="6f08f-217">Neste exemplo, a saída mostra que a licença de docente SkuId é "e97c048c-37a4-45fb-ab50-922fbf07a370".</span><span class="sxs-lookup"><span data-stu-id="6f08f-217">In this example, the output shows that the Faculty license SkuId is "e97c048c-37a4-45fb-ab50-922fbf07a370".</span></span>

> [!NOTE]
> <span data-ttu-id="6f08f-218">Para ver uma lista de IDs education SKUs e SKU, consulte [Education SKU reference](sku-reference-edu.md).</span><span class="sxs-lookup"><span data-stu-id="6f08f-218">To see a list of Education SKUs and SKU IDs, see [Education SKU reference](sku-reference-edu.md).</span></span>

<span data-ttu-id="6f08f-219">Em seguida, executemos o seguinte para identificar os usuários que têm essa licença e colecioná-los todos juntos.</span><span class="sxs-lookup"><span data-stu-id="6f08f-219">Next, we run the following to identify the users that have this license and collect them all together.</span></span>

```powershell
$faculty = Get-AzureADUser -All $true | Where-Object {($_.assignedLicenses).SkuId -contains "e97c048c-37a4-45fb-ab50-922fbf07a370"}
```

#### <a name="assign-a-policy-in-bulk"></a><span data-ttu-id="6f08f-220">Atribuir uma política em massa</span><span class="sxs-lookup"><span data-stu-id="6f08f-220">Assign a policy in bulk</span></span>

<span data-ttu-id="6f08f-221">Agora, atribuímos as políticas apropriadas aos usuários em massa.</span><span class="sxs-lookup"><span data-stu-id="6f08f-221">Now, we assign the appropriate policies to users in bulk.</span></span> <span data-ttu-id="6f08f-222">O número máximo de usuários para os quais você pode atribuir ou atualizar políticas é 5.000 por vez.</span><span class="sxs-lookup"><span data-stu-id="6f08f-222">The maximum number of users for which you can assign or update policies is 5,000 at a time.</span></span> <span data-ttu-id="6f08f-223">Por exemplo, se você tiver mais de 5.000 funcionários e educadores, precisará enviar vários lotes.</span><span class="sxs-lookup"><span data-stu-id="6f08f-223">For example, if you have more than 5,000 staff and educators, you'll need to submit multiple batches.</span></span>

<span data-ttu-id="6f08f-224">Execute o seguinte para atribuir uma política de reunião personalizada chamada EducatorMeetingPolicy à sua equipe e educadores.</span><span class="sxs-lookup"><span data-stu-id="6f08f-224">Run the following to assign a custom meeting policy named EducatorMeetingPolicy to your staff and educators.</span></span>

```powershell
New-CsBatchPolicyAssignmentOperation -PolicyType TeamsMeetingPolicy -PolicyName EducatorMeetingPolicy -Identity $faculty.ObjectId
```

> [!NOTE]
> <span data-ttu-id="6f08f-225">Para atribuir um tipo de política diferente em massa, como TeamsMessagingPolicy, você precisará alterar para a política que você está atribuindo e para o nome ```PolicyType``` ```PolicyName``` da política.</span><span class="sxs-lookup"><span data-stu-id="6f08f-225">To assign a different policy type in bulk, like TeamsMessagingPolicy, you'll need to change ```PolicyType``` to the policy that you're assigning and ```PolicyName``` to the policy name.</span></span>

#### <a name="get-the-status-of-a-bulk-assignment"></a><span data-ttu-id="6f08f-226">Obter o status de uma atribuição em massa</span><span class="sxs-lookup"><span data-stu-id="6f08f-226">Get the status of a bulk assignment</span></span>

<span data-ttu-id="6f08f-227">Cada atribuição em massa retorna uma ID de operação, que você pode usar para controlar o andamento das atribuições de política ou identificar quaisquer falhas que possam ocorrer.</span><span class="sxs-lookup"><span data-stu-id="6f08f-227">Each bulk assignment returns an operation ID, which you can use to track the progress of the policy assignments or identify any failures that might occur.</span></span> <span data-ttu-id="6f08f-228">Por exemplo, execute o seguinte:</span><span class="sxs-lookup"><span data-stu-id="6f08f-228">For example, run the following:</span></span>

```powershell
Get-CsBatchPolicyAssignmentOperation -OperationId 3964004e-caa8-4eb4-b0d2-7dd2c8173c8c | fl
```

<span data-ttu-id="6f08f-229">Para exibir o status de atribuição de cada usuário na operação em lotes, execute o seguinte.</span><span class="sxs-lookup"><span data-stu-id="6f08f-229">To view the assignment status of each user in the batch operation, run the following.</span></span> <span data-ttu-id="6f08f-230">Os detalhes de cada usuário estão na ```UserState``` propriedade.</span><span class="sxs-lookup"><span data-stu-id="6f08f-230">Details of each user are in the ```UserState``` property.</span></span>

```powershell
Get-CsBatchPolicyAssignmentOperation -OperationId 3964004e-caa8-4eb4-b0d2-7dd2c8173c8c | Select -ExpandProperty UserState
```

#### <a name="assign-a-policy-in-bulk-if-you-have-more-than-5000-users"></a><span data-ttu-id="6f08f-231">Atribuir uma política em massa se você tiver mais de 5.000 usuários</span><span class="sxs-lookup"><span data-stu-id="6f08f-231">Assign a policy in bulk if you have more than 5,000 users</span></span>

<span data-ttu-id="6f08f-232">Primeiro, execute o seguinte para ver quantos funcionários e educadores você tem:</span><span class="sxs-lookup"><span data-stu-id="6f08f-232">First, run the following to see how many staff and educators you have:</span></span>

```powershell
$faculty.count
```

<span data-ttu-id="6f08f-233">Em vez de fornecer toda a lista de IDs de usuário, execute o seguinte para especificar os primeiros 5.000 e, em seguida, os próximos 5.000 e assim por diante.</span><span class="sxs-lookup"><span data-stu-id="6f08f-233">Instead of providing the whole list of user IDs, run the following to specify the first 5,000, and then the next 5,000, and so on.</span></span>

```powershell
New-CsBatchPolicyAssignmentOperation -PolicyType TeamsMeetingPolicy -PolicyName EducatorMeetingPolicy -Identity $faculty[0..19999].ObjectId
```

<span data-ttu-id="6f08f-234">Você pode alterar o intervalo de IDs de usuário até chegar à lista completa de usuários.</span><span class="sxs-lookup"><span data-stu-id="6f08f-234">You can change the range of user IDs until you reach the full list of users.</span></span> <span data-ttu-id="6f08f-235">Por exemplo, insira o primeiro lote, use para o segundo lote, insira para o ```$faculty[0..4999``` terceiro lote e assim por ```$faculty[5000..9999``` ```$faculty[10000..14999``` diante.</span><span class="sxs-lookup"><span data-stu-id="6f08f-235">For example, enter ```$faculty[0..4999``` for the first batch, use ```$faculty[5000..9999``` for the second batch, enter ```$faculty[10000..14999``` for the third batch, and so on.</span></span>

#### <a name="get-the-policies-assigned-to-a-user"></a><span data-ttu-id="6f08f-236">Obter as políticas atribuídas a um usuário</span><span class="sxs-lookup"><span data-stu-id="6f08f-236">Get the policies assigned to a user</span></span>

<span data-ttu-id="6f08f-237">Execute o seguinte para ver todas as políticas atribuídas a um usuário específico.</span><span class="sxs-lookup"><span data-stu-id="6f08f-237">Run the following to see all the policies that are assigned to a specific user.</span></span> <span data-ttu-id="6f08f-238">O exemplo a seguir mostra como obter as políticas atribuídas a hannah@contoso.com.</span><span class="sxs-lookup"><span data-stu-id="6f08f-238">The following example shows you how to get the policies that are assigned to hannah@contoso.com.</span></span>

```powershell
Get-CsUserPolicyAssignment -Identity hannah@contoso.com
```

## <a name="faq"></a><span data-ttu-id="6f08f-239">Perguntas frequentes</span><span class="sxs-lookup"><span data-stu-id="6f08f-239">FAQ</span></span>

<span data-ttu-id="6f08f-240">**Não estou familiarizado com o PowerShell para Teams. Onde posso saber mais?**</span><span class="sxs-lookup"><span data-stu-id="6f08f-240">**I'm not familiar with PowerShell for Teams. Where can I learn more?**</span></span>

<span data-ttu-id="6f08f-241">Para ver uma visão geral sobre como usar o PowerShell para gerenciar Teams, [consulte Teams visão geral do PowerShell.](teams-powershell-overview.md)</span><span class="sxs-lookup"><span data-stu-id="6f08f-241">For an overview of using PowerShell to manage Teams, see [Teams PowerShell overview](teams-powershell-overview.md).</span></span> <span data-ttu-id="6f08f-242">Para obter mais informações sobre os cmdlets usados neste artigo, consulte:</span><span class="sxs-lookup"><span data-stu-id="6f08f-242">For more information about the cmdlets used in this article, see:</span></span>

- [<span data-ttu-id="6f08f-243">New-CsGroupPolicyAssignment</span><span class="sxs-lookup"><span data-stu-id="6f08f-243">New-CsGroupPolicyAssignment</span></span>](/powershell/module/teams/new-csgrouppolicyassignment)
- [<span data-ttu-id="6f08f-244">Get-CsGroupPolicyAssignment</span><span class="sxs-lookup"><span data-stu-id="6f08f-244">Get-CsGroupPolicyAssignment</span></span>](/powershell/module/teams/get-csgrouppolicyassignment)
- [<span data-ttu-id="6f08f-245">New-CsBatchPolicyAssignmentOperation</span><span class="sxs-lookup"><span data-stu-id="6f08f-245">New-CsBatchPolicyAssignmentOperation</span></span>](/powershell/module/teams/new-csbatchpolicyassignmentoperation)
- [<span data-ttu-id="6f08f-246">Get-CsBatchPolicyAssignmentOperation</span><span class="sxs-lookup"><span data-stu-id="6f08f-246">Get-CsBatchPolicyAssignmentOperation</span></span>](/powershell/module/teams/get-csbatchpolicyassignmentoperation)
- [<span data-ttu-id="6f08f-247">Get-CsUserPolicyAssignment</span><span class="sxs-lookup"><span data-stu-id="6f08f-247">Get-CsUserPolicyAssignment</span></span>](/powershell/module/teams/get-csuserpolicyassignment)

## <a name="related-topics"></a><span data-ttu-id="6f08f-248">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="6f08f-248">Related topics</span></span>

- [<span data-ttu-id="6f08f-249">Atribuir políticas aos usuários</span><span class="sxs-lookup"><span data-stu-id="6f08f-249">Assign policies to your users</span></span>](assign-policies.md)
- [<span data-ttu-id="6f08f-250">Políticas do Teams e pacotes de políticas para Educação</span><span class="sxs-lookup"><span data-stu-id="6f08f-250">Teams policies and policy packages for Education</span></span>](policy-packages-edu.md)
- [<span data-ttu-id="6f08f-251">Gerenciar políticas de reunião no Teams</span><span class="sxs-lookup"><span data-stu-id="6f08f-251">Manage meeting policies in Teams</span></span>](meeting-policies-in-teams.md)