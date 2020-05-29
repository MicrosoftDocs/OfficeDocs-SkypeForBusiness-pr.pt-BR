---
title: Atribuir políticas a grandes conjuntos de usuários na sua escola
author: lanachin
ms.author: v-lanac
manager: serdars
ms.reviewer: saragava,karsmith
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
description: Saiba como usar a atribuição de política em lote para atribuir políticas a grandes conjuntos de usuários em sua instituição educacional em grande parte para fins escolares remotos (teleescolares, tele-School).
f1keywords: ''
ms.openlocfilehash: 5772a260642b09232e4df5eec57751a39ec2a74a
ms.sourcegitcommit: 86b0956680b867b8bedb2e969220b8006829ee53
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/28/2020
ms.locfileid: "44410436"
---
# <a name="assign-policies-to-large-sets-of-users-in-your-school"></a><span data-ttu-id="c05ec-103">Atribuir políticas a grandes conjuntos de usuários na sua escola</span><span class="sxs-lookup"><span data-stu-id="c05ec-103">Assign policies to large sets of users in your school</span></span>

<span data-ttu-id="c05ec-104">Você precisa dar aos alunos e professores acesso a diferentes recursos do Microsoft Teams?</span><span class="sxs-lookup"><span data-stu-id="c05ec-104">Do you need to give your students and educators access to different features in Microsoft Teams?</span></span> <span data-ttu-id="c05ec-105">Você pode identificar rapidamente os usuários da sua organização por tipo de licença e, em seguida, atribuí-los à política apropriada.</span><span class="sxs-lookup"><span data-stu-id="c05ec-105">You can quickly identify the users in your organization by license type and then assign them the appropriate policy.</span></span> <span data-ttu-id="c05ec-106">Este tutorial mostra como usar a [atribuição de política de lote](assign-policies.md#assign-a-policy-to-a-batch-of-users) para atribuir uma política de reunião a usuários em massa.</span><span class="sxs-lookup"><span data-stu-id="c05ec-106">This tutorial shows you how to use [batch policy assignment](assign-policies.md#assign-a-policy-to-a-batch-of-users) to assign a meeting policy to users in bulk.</span></span>

<span data-ttu-id="c05ec-107">Lembre-se de que, no Teams, os usuários obtêm automaticamente a política global (padrão para toda a organização) para um tipo de política de equipe, a menos que você crie e atribua uma política personalizada.</span><span class="sxs-lookup"><span data-stu-id="c05ec-107">Remember that in Teams, users automatically get the Global (Org-wide default) policy for a Teams policy type unless you create and assign a custom policy.</span></span> <span data-ttu-id="c05ec-108">Como a população dos alunos costuma ser o maior conjunto de usuários e muitas vezes recebem as configurações mais restritivas, recomendamos que você faça o seguinte:</span><span class="sxs-lookup"><span data-stu-id="c05ec-108">Because the student population is often the largest set of users and they often receive the most restrictive settings, we recommend that you do the following:</span></span>

- <span data-ttu-id="c05ec-109">Edite e aplique a política global (padrão para toda a organização) para restringir recursos para os alunos.</span><span class="sxs-lookup"><span data-stu-id="c05ec-109">Edit and apply the Global (Org-wide default) policy to restrict capabilities for students.</span></span> 
- <span data-ttu-id="c05ec-110">Crie uma política personalizada que permita recursos essenciais, como chat particular e agendamento de reunião e atribuir a política a seus funcionários e educadores.</span><span class="sxs-lookup"><span data-stu-id="c05ec-110">Create a custom policy that allows core capabilities such as private chat and meeting scheduling and assign the policy to your staff and educators.</span></span>

<span data-ttu-id="c05ec-111">Lembre-se de que a política global será aplicada a todos os usuários de sua escola até você criar uma política personalizada e atribuí-la a seus funcionários e professores.</span><span class="sxs-lookup"><span data-stu-id="c05ec-111">Keep in mind that the Global policy will apply to all users in your school until you create a custom policy and assign it to your staff and educators.</span></span>

<span data-ttu-id="c05ec-112">Neste tutorial, os alunos receberão a política de reunião global e usaremos o PowerShell para atribuir uma política de reunião personalizada chamada EducatorMeetingPolicy à equipe e educadores em massa.</span><span class="sxs-lookup"><span data-stu-id="c05ec-112">In this tutorial, students will get the Global meeting policy and we use PowerShell to assign a custom meeting policy named EducatorMeetingPolicy to staff and educators in bulk.</span></span> <span data-ttu-id="c05ec-113">Presumimos que você tenha editado a política global para personalizar as configurações de reunião para os alunos e criou uma política personalizada que define a experiência da reunião para funcionários e educadores.</span><span class="sxs-lookup"><span data-stu-id="c05ec-113">We assume that you've edited the Global policy to tailor meeting settings for students and created a custom policy that defines the meeting experience for staff and educators.</span></span>

![Captura de tela da página políticas de reunião no centro de administração do teams](media/edu-batch-policy-assignment.png)

<span data-ttu-id="c05ec-115">Siga estas etapas para atribuir uma política de reunião personalizada a funcionários e professores em massa.</span><span class="sxs-lookup"><span data-stu-id="c05ec-115">Follow these steps to assign a custom meeting policy to staff and educators in bulk.</span></span>

## <a name="connect-to-the-azure-ad-powershell-for-graph-module-and-the-teams-powershell-module"></a><span data-ttu-id="c05ec-116">Conectar-se ao módulo do Azure AD PowerShell para Graph e ao módulo do PowerShell do teams</span><span class="sxs-lookup"><span data-stu-id="c05ec-116">Connect to the Azure AD PowerShell for Graph module and the Teams PowerShell module</span></span>

<span data-ttu-id="c05ec-117">Antes de executar as etapas deste artigo, você precisará instalar e se conectar ao módulo Azure AD PowerShell para Graph (para identificar os usuários por suas licenças atribuídas) e ao módulo do Microsoft Teams PowerShell (para atribuir as políticas a esses usuários).</span><span class="sxs-lookup"><span data-stu-id="c05ec-117">Before you perform the steps in this article, you'll need to install and connect to the Azure AD PowerShell for Graph module (to identify users by their assigned licenses) and the Microsoft Teams PowerShell module (to assign the policies to those users).</span></span>

### <a name="install-and-connect-to-the-azure-ad-powershell-for-graph-module"></a><span data-ttu-id="c05ec-118">Instalar e conectar-se ao módulo do Azure AD PowerShell para Graph</span><span class="sxs-lookup"><span data-stu-id="c05ec-118">Install and connect to the Azure AD PowerShell for Graph module</span></span>

<span data-ttu-id="c05ec-119">Abra um prompt de comando do Windows PowerShell com privilégios elevados (execute o Windows PowerShell como administrador) e execute o seguinte procedimento para instalar o módulo do Azure Active Directory PowerShell para Graph.</span><span class="sxs-lookup"><span data-stu-id="c05ec-119">Open an elevated Windows PowerShell command prompt (run Windows PowerShell as an administrator), and then run the following to install the Azure Active Directory PowerShell for Graph module.</span></span>

```powershell
Install-Module -Name AzureAD
```

<span data-ttu-id="c05ec-120">Execute o seguinte para se conectar ao Azure AD.</span><span class="sxs-lookup"><span data-stu-id="c05ec-120">Run the following to connect to Azure AD.</span></span>

```powershell
Connect-AzureAD
```

<span data-ttu-id="c05ec-121">Quando for solicitado, entre usando suas credenciais de administrador.</span><span class="sxs-lookup"><span data-stu-id="c05ec-121">When you're prompted, sign in using your admin credentials.</span></span>

<span data-ttu-id="c05ec-122">Para saber mais, consulte [conectar-se com o módulo do PowerShell do Azure Active Directory para Graph](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell#connect-with-the-azure-active-directory-powershell-for-graph-module).</span><span class="sxs-lookup"><span data-stu-id="c05ec-122">To learn more, see [Connect with the Azure Active Directory PowerShell for Graph module](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell#connect-with-the-azure-active-directory-powershell-for-graph-module).</span></span>

### <a name="install-and-connect-to-the-microsoft-teams-powershell-module"></a><span data-ttu-id="c05ec-123">Instalar e conectar-se ao módulo do PowerShell do Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="c05ec-123">Install and connect to the Microsoft Teams PowerShell module</span></span>

<span data-ttu-id="c05ec-124">Execute o seguinte para instalar o [módulo do Microsoft Teams PowerShell](https://www.powershellgallery.com/packages/MicrosoftTeams).</span><span class="sxs-lookup"><span data-stu-id="c05ec-124">Run the following to install the [Microsoft Teams PowerShell module](https://www.powershellgallery.com/packages/MicrosoftTeams).</span></span> <span data-ttu-id="c05ec-125">Verifique se você instalou a versão 1.0.5 ou posterior.</span><span class="sxs-lookup"><span data-stu-id="c05ec-125">Make sure you install version 1.0.5 or later.</span></span>

```powershell
Install-Module -Name MicrosoftTeams
```

<span data-ttu-id="c05ec-126">Execute o seguinte para se conectar ao Microsoft Teams e iniciar uma sessão.</span><span class="sxs-lookup"><span data-stu-id="c05ec-126">Run the following to connect to Teams and start a session.</span></span>

```powershell
Connect-MicrosoftTeams
```
<span data-ttu-id="c05ec-127">Quando for solicitado, entre usando as mesmas credenciais de administrador usadas para se conectar ao Azure AD.</span><span class="sxs-lookup"><span data-stu-id="c05ec-127">When you're prompted, sign in using the same admin credentials you used to connect to Azure AD.</span></span>

## <a name="identify-your-users"></a><span data-ttu-id="c05ec-128">Identifique seus usuários</span><span class="sxs-lookup"><span data-stu-id="c05ec-128">Identify your users</span></span>

<span data-ttu-id="c05ec-129">Primeiro, execute o seguinte procedimento para identificar seus funcionários e professores por tipo de licença.</span><span class="sxs-lookup"><span data-stu-id="c05ec-129">First, run the following to identify your staff and educators by license type.</span></span> <span data-ttu-id="c05ec-130">Isso informa quais SKUs estão em uso em sua organização.</span><span class="sxs-lookup"><span data-stu-id="c05ec-130">This tells you what SKUs are in use in your organization.</span></span> <span data-ttu-id="c05ec-131">Em seguida, você pode identificar os funcionários e professores que têm uma SKU com docente atribuída.</span><span class="sxs-lookup"><span data-stu-id="c05ec-131">You can then identify staff and educators that have a Faculty SKU assigned.</span></span>

```powershell
Get-AzureAdSubscribedSku | Select-Object -Property SkuPartNumber,SkuId
```

<span data-ttu-id="c05ec-132">Que retorna:</span><span class="sxs-lookup"><span data-stu-id="c05ec-132">Which returns:</span></span>

```
SkuPartNumber      SkuId
-------------      -----
M365EDU_A5_FACULTY e97c048c-37a4-45fb-ab50-922fbf07a370
M365EDU_A5_STUDENT 46c119d4-0379-4a9d-85e4-97c66d3f909e
```

<span data-ttu-id="c05ec-133">Neste exemplo, a saída mostra que a licença doce SkuId é "e97c048c-37a4-45fb-ab50-922fbf07a370".</span><span class="sxs-lookup"><span data-stu-id="c05ec-133">In this example, the output shows that the Faculty license SkuId is "e97c048c-37a4-45fb-ab50-922fbf07a370".</span></span>

> [!NOTE]
> <span data-ttu-id="c05ec-134">Para ver uma lista de SKUs educacionais e IDs de SKU, consulte referência sobre o [SKU educacional](sku-reference-edu.md).</span><span class="sxs-lookup"><span data-stu-id="c05ec-134">To see a list of Education SKUs and SKU IDs, see [Education SKU reference](sku-reference-edu.md).</span></span>

<span data-ttu-id="c05ec-135">Em seguida, executamos o seguinte para identificar os usuários que têm essa licença e reuni-los juntos.</span><span class="sxs-lookup"><span data-stu-id="c05ec-135">Next, we run the following to identify the users that have this license and collect them all together.</span></span>

```powershell
$faculty = Get-AzureADUser -All $true | Where-Object {($_.assignedLicenses).SkuId -contains "e97c048c-37a4-45fb-ab50-922fbf07a370"}
```

## <a name="assign-a-policy-in-bulk"></a><span data-ttu-id="c05ec-136">Atribuir uma política em massa</span><span class="sxs-lookup"><span data-stu-id="c05ec-136">Assign a policy in bulk</span></span>

<span data-ttu-id="c05ec-137">Agora, atribuímos as políticas adequadas aos usuários em massa.</span><span class="sxs-lookup"><span data-stu-id="c05ec-137">Now, we assign the appropriate policies to users in bulk.</span></span> <span data-ttu-id="c05ec-138">O número máximo de usuários para os quais você pode atribuir ou atualizar políticas é de 5.000 de cada vez.</span><span class="sxs-lookup"><span data-stu-id="c05ec-138">The maximum number of users for which you can assign or update policies is 5,000 at a time.</span></span> <span data-ttu-id="c05ec-139">Por exemplo, se você tiver mais de 5.000 funcionários e professores, será necessário enviar vários lotes.</span><span class="sxs-lookup"><span data-stu-id="c05ec-139">For example, if you have more than 5,000 staff and educators, you'll need to submit multiple batches.</span></span>


<span data-ttu-id="c05ec-140">Execute o seguinte para atribuir a política de reunião chamada EducatorMeetingPolicy à sua equipe e educadores.</span><span class="sxs-lookup"><span data-stu-id="c05ec-140">Run the following to assign the meeting policy named EducatorMeetingPolicy to your staff and educators.</span></span>

```powershell
New-CsBatchPolicyAssignmentOperation -PolicyType TeamsMeetingPolicy -PolicyName EducatorMeetingPolicy -Identity $faculty.ObjectId
```

> [!NOTE]
> <span data-ttu-id="c05ec-141">Para atribuir um tipo de política diferente em massa, como TeamsMessagingPolicy, você precisará mudar ```PolicyType``` para a política que está atribuindo e ```PolicyName``` para o nome da política.</span><span class="sxs-lookup"><span data-stu-id="c05ec-141">To assign a different policy type in bulk, like TeamsMessagingPolicy, you'll need to change ```PolicyType``` to the policy that you're assigning and ```PolicyName``` to the policy name.</span></span>

## <a name="get-the-status-of-a-bulk-assignment"></a><span data-ttu-id="c05ec-142">Obter o status de uma atribuição em massa</span><span class="sxs-lookup"><span data-stu-id="c05ec-142">Get the status of a bulk assignment</span></span>

<span data-ttu-id="c05ec-143">Cada atribuição em massa retorna uma ID de operação, que você pode usar para acompanhar o andamento das tarefas de política ou identificar quaisquer falhas que possam ocorrer.</span><span class="sxs-lookup"><span data-stu-id="c05ec-143">Each bulk assignment returns an operation ID, which you can use to track the progress of the policy assignments or identify any failures that might occur.</span></span> <span data-ttu-id="c05ec-144">Por exemplo, execute o seguinte:</span><span class="sxs-lookup"><span data-stu-id="c05ec-144">For example, run the following:</span></span>

```powershell
Get-CsBatchPolicyAssignmentOperation -OperationId 3964004e-caa8-4eb4-b0d2-7dd2c8173c8c | fl
```

<span data-ttu-id="c05ec-145">Para exibir o status da atribuição de cada usuário na operação em lotes, execute o seguinte.</span><span class="sxs-lookup"><span data-stu-id="c05ec-145">To view the assignment status of each user in the batch operation, run the following.</span></span> <span data-ttu-id="c05ec-146">Os detalhes de cada usuário estão na ```UserState``` propriedade.</span><span class="sxs-lookup"><span data-stu-id="c05ec-146">Details of each user are in the ```UserState``` property.</span></span>

```powershell
Get-CsBatchPolicyAssignmentOperation -OperationId 3964004e-caa8-4eb4-b0d2-7dd2c8173c8c | Select -ExpandProperty UserState
```

## <a name="assign-a-policy-in-bulk-if-you-have-more-than-5000-users"></a><span data-ttu-id="c05ec-147">Atribuir uma política em massa se você tiver mais de 5.000 usuários</span><span class="sxs-lookup"><span data-stu-id="c05ec-147">Assign a policy in bulk if you have more than 5,000 users</span></span>

<span data-ttu-id="c05ec-148">Primeiro, execute o seguinte procedimento para ver quantas pessoas e professores você tem:</span><span class="sxs-lookup"><span data-stu-id="c05ec-148">First, run the following to see how many staff and educators you have:</span></span>

```powershell
$faculty.count
```

<span data-ttu-id="c05ec-149">Em vez de fornecer toda a lista de IDs de usuário, execute o seguinte para especificar o primeiro 5.000 e, em seguida, o próximo 5.000 e assim por diante.</span><span class="sxs-lookup"><span data-stu-id="c05ec-149">Instead of providing the whole list of user IDs, run the following to specify the first 5,000, and then the next 5,000, and so on.</span></span>

```powershell
New-CsBatchPolicyAssignmentOperation -PolicyType TeamsMeetingPolicy -PolicyName EducatorMeetingPolicy -Identity $faculty[0..19999].ObjectId
```

<span data-ttu-id="c05ec-150">Você pode alterar o intervalo de IDs de usuário até chegar à lista completa de usuários.</span><span class="sxs-lookup"><span data-stu-id="c05ec-150">You can change the range of user IDs until you reach the full list of users.</span></span> <span data-ttu-id="c05ec-151">Por exemplo, insira ```$faculty[0..4999``` para o primeiro lote, use ```$faculty[5000..9999``` para o segundo lote, insira ```$faculty[10000..14999``` para o terceiro lote e assim por diante.</span><span class="sxs-lookup"><span data-stu-id="c05ec-151">For example, enter ```$faculty[0..4999``` for the first batch, use ```$faculty[5000..9999``` for the second batch, enter ```$faculty[10000..14999``` for the third batch, and so on.</span></span>

## <a name="get-the-policies-assigned-to-a-user"></a><span data-ttu-id="c05ec-152">Obter as políticas atribuídas a um usuário</span><span class="sxs-lookup"><span data-stu-id="c05ec-152">Get the policies assigned to a user</span></span>

<span data-ttu-id="c05ec-153">Execute o seguinte para ver todas as políticas atribuídas a um usuário específico.</span><span class="sxs-lookup"><span data-stu-id="c05ec-153">Run the following to see all the policies that are assigned to a specific user.</span></span> <span data-ttu-id="c05ec-154">O exemplo a seguir mostra como obter as políticas atribuídas ao hannah@contoso.com.</span><span class="sxs-lookup"><span data-stu-id="c05ec-154">The following example shows you how to get the policies that are assigned to hannah@contoso.com.</span></span>

```powershell
Get-CsUserPolicyAssignment -Identity hannah@contoso.com
```

## <a name="faq"></a><span data-ttu-id="c05ec-155">Perguntas frequentes</span><span class="sxs-lookup"><span data-stu-id="c05ec-155">FAQ</span></span>

<span data-ttu-id="c05ec-156">**Quero ter certeza de que todos os usuários que sejam alunos, funcionários e educados recebam automaticamente as políticas atribuídas. Como posso fazer isso?**</span><span class="sxs-lookup"><span data-stu-id="c05ec-156">**I want to make sure that all users that are students, staff, and educators automatically get policies assigned. How can I do that?**</span></span>

<span data-ttu-id="c05ec-157">A equipe de produto do teams está trabalhando para dar suporte à atribuição de políticas a grupos de segurança.</span><span class="sxs-lookup"><span data-stu-id="c05ec-157">The Teams product team is doing work to support assigning policies to security groups.</span></span> <span data-ttu-id="c05ec-158">Nesse momento, você poderá criar grupos para seus alunos e professores e, em seguida, as políticas apropriadas a esses grupos.</span><span class="sxs-lookup"><span data-stu-id="c05ec-158">At that time, you'll be able to create groups for your students and teachers, and then the appropriate policies to those groups.</span></span> <span data-ttu-id="c05ec-159">Observe que atribuições explícitas de usuários (como as políticas que você atribuiu usando este tutorial) substituirão as políticas herdadas de um grupo.</span><span class="sxs-lookup"><span data-stu-id="c05ec-159">Note that explicit user assignments (such as the policies that you've assigned using this tutorial) will override policies inherited from a group.</span></span> <span data-ttu-id="c05ec-160">Quando esse recurso tiver suporte, forneceremos mais instruções sobre como usar a atribuição de política para grupos e atualizar os usuários para garantir que eles recebam as políticas de grupo herdadas.</span><span class="sxs-lookup"><span data-stu-id="c05ec-160">When this feature is supported, we'll provide more instructions on how to use policy assignment to groups and update your users to ensure they get the inherited group policies.</span></span>

<span data-ttu-id="c05ec-161">**Não estou familiarizado com o PowerShell para Teams. Onde posso saber mais?**</span><span class="sxs-lookup"><span data-stu-id="c05ec-161">**I'm not familiar with PowerShell for Teams. Where can I learn more?**</span></span>

<span data-ttu-id="c05ec-162">Consulte [visão geral do teams PowerShell](teams-powershell-overview.md).</span><span class="sxs-lookup"><span data-stu-id="c05ec-162">See [Teams Powershell overview](teams-powershell-overview.md).</span></span>

## <a name="related-topics"></a><span data-ttu-id="c05ec-163">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="c05ec-163">Related topics</span></span>

- [<span data-ttu-id="c05ec-164">Atribuir políticas aos usuários</span><span class="sxs-lookup"><span data-stu-id="c05ec-164">Assign policies to your users</span></span>](assign-policies.md)
- [<span data-ttu-id="c05ec-165">New-CsBatchPolicyAssignmentOperation</span><span class="sxs-lookup"><span data-stu-id="c05ec-165">New-CsBatchPolicyAssignmentOperation</span></span>](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation)
- [<span data-ttu-id="c05ec-166">Get-CsBatchPolicyAssignmentOperation</span><span class="sxs-lookup"><span data-stu-id="c05ec-166">Get-CsBatchPolicyAssignmentOperation</span></span>](https://docs.microsoft.com/powershell/module/teams/get-csbatchpolicyassignmentoperation)
- [<span data-ttu-id="c05ec-167">Get-CsUserPolicyAssignment</span><span class="sxs-lookup"><span data-stu-id="c05ec-167">Get-CsUserPolicyAssignment</span></span>](https://docs.microsoft.com/powershell/module/teams/get-csuserpolicyassignment)
