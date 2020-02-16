---
title: Atribuir políticas a seus usuários no Microsoft Teams
author: lanachin
ms.author: v-lanac
manager: serdars
ms.reviewer: tomkau, saragava, ritikag
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
description: Aprenda as diferentes maneiras de atribuir políticas a seus usuários no Microsoft Teams.
f1keywords: ''
ms.openlocfilehash: a4d50f6182441e97f5d7290610e254bd82e91e96
ms.sourcegitcommit: c8d16d5e61d66d7b5e7391a800978b920612ea4d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42052529"
---
# <a name="assign-policies-to-your-users-in-microsoft-teams"></a><span data-ttu-id="1ff8e-103">Atribuir políticas a seus usuários no Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="1ff8e-103">Assign policies to your users in Microsoft Teams</span></span>

> [!NOTE]
> <span data-ttu-id="1ff8e-104">**Dois dos recursos do Microsoft Teams discutidos neste artigo, [atribuição de política em lotes](#assign-a-policy-to-a-batch-of-users) e [atribuição de política de grupo](#assign-a-policy-to-a-group)estão atualmente em visualização.**</span><span class="sxs-lookup"><span data-stu-id="1ff8e-104">**Two of the Microsoft Teams features discussed in this article, [batch policy assignment](#assign-a-policy-to-a-batch-of-users) and [group policy assignment](#assign-a-policy-to-a-group), are currently in preview.**</span></span>

<span data-ttu-id="1ff8e-105">Como administrador, você usa políticas para controlar os recursos do teams que estão disponíveis para os usuários da sua organização.</span><span class="sxs-lookup"><span data-stu-id="1ff8e-105">As an admin, you use policies to control the Teams features that are available to users in your organization.</span></span> <span data-ttu-id="1ff8e-106">Por exemplo, há políticas de chamada, políticas de reunião e políticas de mensagens, para citar apenas alguns.</span><span class="sxs-lookup"><span data-stu-id="1ff8e-106">For example, there are calling policies, meeting policies, and messaging policies, to name just a few.</span></span>

<span data-ttu-id="1ff8e-107">As organizações têm diferentes tipos de usuários com necessidades exclusivas e políticas personalizadas que você cria e atribui permite que você ajuste as configurações de política para diferentes conjuntos de usuários com base nessas necessidades.</span><span class="sxs-lookup"><span data-stu-id="1ff8e-107">Organizations have different types of users with unique needs and custom policies that you create and assign let you tailor policy settings to different sets of users based on those needs.</span></span>

<span data-ttu-id="1ff8e-108">Para facilitar o gerenciamento de políticas em sua organização, o Teams oferece várias maneiras de atribuir políticas a usuários.</span><span class="sxs-lookup"><span data-stu-id="1ff8e-108">To make it easier to manage policies in your organization, Teams offers several ways to assign policies to users.</span></span> <span data-ttu-id="1ff8e-109">Você pode atribuir uma política diretamente aos usuários, individualmente ou em escalabilidade por meio de uma atribuição de lote ou a um grupo do qual o usuário é membro.</span><span class="sxs-lookup"><span data-stu-id="1ff8e-109">You can assign a policy directly to users, either individually or at scale through a batch assignment, or to a group that the user is a member of.</span></span> <span data-ttu-id="1ff8e-110">Você também pode usar pacotes de política para atribuir uma coleção predefinida de políticas para os usuários de sua organização que têm funções semelhantes.</span><span class="sxs-lookup"><span data-stu-id="1ff8e-110">You can also use policy packages to assign a preset collection of policies to users in your organization who have similar roles.</span></span> <span data-ttu-id="1ff8e-111">A opção que você escolher depende do número de políticas que você está gerenciando e do número de usuários aos quais está fazendo a atribuição.</span><span class="sxs-lookup"><span data-stu-id="1ff8e-111">The option that you choose depends on the number of policies that you're managing and the number of users that you're assigning to.</span></span>

<span data-ttu-id="1ff8e-112">Este artigo descreve as diferentes maneiras pelas quais você pode atribuir políticas a usuários e os cenários recomendados para quando usar o quê.</span><span class="sxs-lookup"><span data-stu-id="1ff8e-112">This article describes the different ways that you can assign policies to users and the recommended scenarios for when to use what.</span></span>

## <a name="which-policy-takes-precedence"></a><span data-ttu-id="1ff8e-113">Qual política tem precedência?</span><span class="sxs-lookup"><span data-stu-id="1ff8e-113">Which policy takes precedence?</span></span>

<span data-ttu-id="1ff8e-114">Um usuário tem uma política em vigor para cada tipo de política.</span><span class="sxs-lookup"><span data-stu-id="1ff8e-114">A user has one effective policy for each policy type.</span></span> <span data-ttu-id="1ff8e-115">É possível ou até mesmo provável que um usuário esteja diretamente atribuído a uma política e também seja um membro de um ou mais grupos que tenha atribuído uma política do mesmo tipo.</span><span class="sxs-lookup"><span data-stu-id="1ff8e-115">It's possible or even likely that a user is directly assigned a policy and is also a member of one or more groups that's assigned a policy of the same type.</span></span> <span data-ttu-id="1ff8e-116">Nesses tipos de cenários, qual política tem precedência?</span><span class="sxs-lookup"><span data-stu-id="1ff8e-116">In these kinds of scenarios, which policy takes precedence?</span></span>  <span data-ttu-id="1ff8e-117">A política efetiva de um usuário é determinada de acordo com as regras de precedência, da seguinte maneira.</span><span class="sxs-lookup"><span data-stu-id="1ff8e-117">A user's effective policy is determined according to rules of precedence, as follows.</span></span>

<span data-ttu-id="1ff8e-118">Se um usuário for diretamente atribuído a uma política (individualmente ou por meio de uma atribuição em lotes), essa política terá precedência.</span><span class="sxs-lookup"><span data-stu-id="1ff8e-118">If a user is directly assigned a policy (either individually or through a batch assignment), that policy takes precedence.</span></span> <span data-ttu-id="1ff8e-119">No exemplo a seguir, a política efetiva do usuário é a política de reunião quadrada Lincoln, que é atribuída diretamente ao usuário.</span><span class="sxs-lookup"><span data-stu-id="1ff8e-119">In the following example, the user's effective policy is the Lincoln Square meeting policy, which is directly assigned to the user.</span></span>

![Diagrama mostrando como uma política atribuída diretamente tem prioridade](media/assign-policies-example-directly-assigned.png)

<span data-ttu-id="1ff8e-121">Se um usuário não estiver diretamente atribuído a uma política de um determinado tipo, a política atribuída a um grupo do qual o usuário é membro terá precedência.</span><span class="sxs-lookup"><span data-stu-id="1ff8e-121">If a user isn't directly assigned a policy of a given type, the policy assigned to a group that the user is a member of takes precedence.</span></span> <span data-ttu-id="1ff8e-122">Se um usuário for membro de vários grupos, a política que tem a classificação de [atribuição de grupo](#group-assignment-ranking) mais alta para o tipo de política específico tem precedência.</span><span class="sxs-lookup"><span data-stu-id="1ff8e-122">If a user is a member of multiple groups, the policy that has the highest [group assignment ranking](#group-assignment-ranking) for the given policy type takes precedence.</span></span>

<span data-ttu-id="1ff8e-123">Neste exemplo, a política efetiva do usuário é o Teams exec e a política de HD, que tem a classificação de atribuição mais alta em relação a outros grupos dos quais o usuário é membro e que também são atribuídas uma política do mesmo tipo de política.</span><span class="sxs-lookup"><span data-stu-id="1ff8e-123">In this example, the user's effective policy is the Exec Teams and HD policy, which has the highest assignment ranking relative to other groups that the user is a member of and that are also assigned a policy of the same policy type.</span></span>  

![Diagrama mostrando como uma política herdada do grupo tem prioridade](media/assign-policies-example-group.png)

<span data-ttu-id="1ff8e-125">Se um usuário não estiver diretamente atribuído a uma política ou não for membro de nenhum grupo ao qual a política atribuiu uma política, o usuário terá a política global (padrão para toda a organização) para esse tipo de política.</span><span class="sxs-lookup"><span data-stu-id="1ff8e-125">If a user isn't directly assigned a policy or isn't a member of any groups that are assigned a policy, the user gets the global (Org-wide default) policy for that policy type.</span></span> <span data-ttu-id="1ff8e-126">Aqui está um exemplo.</span><span class="sxs-lookup"><span data-stu-id="1ff8e-126">Here's an example.</span></span>

![Diagrama mostrando como uma política global tem precedência](media/assign-policies-example-global.png)

<span data-ttu-id="1ff8e-128">Para saber mais, consulte [regras de precedência](#precedence-rules).</span><span class="sxs-lookup"><span data-stu-id="1ff8e-128">To learn more, see [Precedence rules](#precedence-rules).</span></span>

## <a name="ways-to-assign-policies"></a><span data-ttu-id="1ff8e-129">Maneiras de atribuir políticas</span><span class="sxs-lookup"><span data-stu-id="1ff8e-129">Ways to assign policies</span></span>

<span data-ttu-id="1ff8e-130">Aqui está uma visão geral de como você pode atribuir políticas a usuários e os cenários recomendados para cada um deles.</span><span class="sxs-lookup"><span data-stu-id="1ff8e-130">Here's an overview of the ways that you can assign policies to users and the recommended scenarios for each.</span></span> <span data-ttu-id="1ff8e-131">Clique nos links para saber mais.</span><span class="sxs-lookup"><span data-stu-id="1ff8e-131">Click the links to learn more.</span></span>

|<span data-ttu-id="1ff8e-132">Fazer isso</span><span class="sxs-lookup"><span data-stu-id="1ff8e-132">Do this</span></span>  |<span data-ttu-id="1ff8e-133">Se...</span><span class="sxs-lookup"><span data-stu-id="1ff8e-133">If...</span></span>  | <span data-ttu-id="1ff8e-134">Usar...</span><span class="sxs-lookup"><span data-stu-id="1ff8e-134">Using...</span></span>
|---------|---------|----|
|[<span data-ttu-id="1ff8e-135">Atribuir uma política a usuários individuais</span><span class="sxs-lookup"><span data-stu-id="1ff8e-135">Assign a policy to individual users</span></span>](#assign-a-policy-to-individual-users)    | <span data-ttu-id="1ff8e-136">Você está começando a usar o Microsoft Teams e simplesmente está começando ou só precisa atribuir uma ou algumas políticas a um pequeno número de usuários.</span><span class="sxs-lookup"><span data-stu-id="1ff8e-136">You're new to Teams and just getting started or you only need to assign one or a couple of policies to a small number of users.</span></span> |<span data-ttu-id="1ff8e-137">O centro de administração do Microsoft Teams ou cmdlets do PowerShell no módulo do PowerShell do Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="1ff8e-137">The Microsoft Teams admin center or PowerShell cmdlets in the Skype for Business Online PowerShell module</span></span>
| [<span data-ttu-id="1ff8e-138">Atribuir um pacote de política</span><span class="sxs-lookup"><span data-stu-id="1ff8e-138">Assign a policy package</span></span>](#assign-a-policy-package)   | <span data-ttu-id="1ff8e-139">Você precisa atribuir várias políticas a conjuntos específicos de usuários em sua organização que tenham funções iguais ou semelhantes.</span><span class="sxs-lookup"><span data-stu-id="1ff8e-139">You need to assign multiple policies to specific sets of users in your organization who have the same or similar roles.</span></span> <span data-ttu-id="1ff8e-140">Por exemplo, atribua o pacote de política de educação (professor) a professores em sua escola para dar a eles acesso total a chats, chamadas e reuniões e ao pacote de política de educação (aluno secundária) para estudantes secundários limitarem determinados recursos como chamadas privadas.</span><span class="sxs-lookup"><span data-stu-id="1ff8e-140">For example, assign the Education (Teacher) policy package to teachers in your school to give them full access to chats, calling, and meetings and the Education (Secondary school student) policy package to secondary students to limit certain capabilities like private calling.</span></span>  |<span data-ttu-id="1ff8e-141">O centro de administração do Microsoft Teams ou cmdlets do PowerShell no módulo Teams PowerShell</span><span class="sxs-lookup"><span data-stu-id="1ff8e-141">The Microsoft Teams admin center or PowerShell cmdlets in the Teams PowerShell module</span></span>|
|<span data-ttu-id="1ff8e-142">[Atribuir uma política a um lote de usuários](#assign-a-policy-to-a-batch-of-users) (na visualização)</span><span class="sxs-lookup"><span data-stu-id="1ff8e-142">[Assign a policy to a batch of users](#assign-a-policy-to-a-batch-of-users) (in preview)</span></span>   | <span data-ttu-id="1ff8e-143">Você precisa atribuir políticas a grandes conjuntos de usuários.</span><span class="sxs-lookup"><span data-stu-id="1ff8e-143">You need to assign policies to large sets of users.</span></span> <span data-ttu-id="1ff8e-144">Por exemplo, você deseja atribuir uma política para centenas ou milhares de usuários em sua organização de cada vez.</span><span class="sxs-lookup"><span data-stu-id="1ff8e-144">For example, you want to assign a policy to hundreds or thousands of users in your organization at a time.</span></span>  |<span data-ttu-id="1ff8e-145">Cmdlets do PowerShell no módulo do teams PowerShell</span><span class="sxs-lookup"><span data-stu-id="1ff8e-145">PowerShell cmdlets in the Teams PowerShell module</span></span>|
|<span data-ttu-id="1ff8e-146">[Atribuir uma política a um grupo](#assign-a-policy-to-a-group) (na visualização)</span><span class="sxs-lookup"><span data-stu-id="1ff8e-146">[Assign a policy to a group](#assign-a-policy-to-a-group) (in preview)</span></span>   |<span data-ttu-id="1ff8e-147">Você precisa atribuir políticas com base nas associações de grupo de um usuário.</span><span class="sxs-lookup"><span data-stu-id="1ff8e-147">You need to assign policies based on a user's group membership.</span></span> <span data-ttu-id="1ff8e-148">Por exemplo, você deseja atribuir uma política a todos os usuários em um grupo de segurança ou unidade organizacional.</span><span class="sxs-lookup"><span data-stu-id="1ff8e-148">For example, you want to assign a policy to all users in a security group or organizational unit.</span></span>| <span data-ttu-id="1ff8e-149">Cmdlets do PowerShell no módulo do teams PowerShell</span><span class="sxs-lookup"><span data-stu-id="1ff8e-149">PowerShell cmdlets in the Teams PowerShell module</span></span>|
| <span data-ttu-id="1ff8e-150">Atribuir um pacote de política a um lote de usuários (em breve)</span><span class="sxs-lookup"><span data-stu-id="1ff8e-150">Assign a policy package to a batch of users (coming soon)</span></span> |||
| <span data-ttu-id="1ff8e-151">Atribuir um pacote de política a um grupo (disponível em breve)</span><span class="sxs-lookup"><span data-stu-id="1ff8e-151">Assign a policy package to a group (coming soon)</span></span>   | ||

## <a name="assign-a-policy-to-individual-users"></a><span data-ttu-id="1ff8e-152">Atribuir uma política a usuários individuais</span><span class="sxs-lookup"><span data-stu-id="1ff8e-152">Assign a policy to individual users</span></span>

<span data-ttu-id="1ff8e-153">Siga estas etapas para atribuir uma política a um usuário individual ou a um pequeno número de usuários por vez.</span><span class="sxs-lookup"><span data-stu-id="1ff8e-153">Follow these steps to assign a policy to an individual user or to a small number of users at a time.</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="1ff8e-154">Usar o centro de administração do Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="1ff8e-154">Using the Microsoft Teams admin center</span></span>

<span data-ttu-id="1ff8e-155">Para atribuir uma política a um usuário:</span><span class="sxs-lookup"><span data-stu-id="1ff8e-155">To assign a policy to a user:</span></span>

1. <span data-ttu-id="1ff8e-156">Na navegação à esquerda do centro de administração do Microsoft Teams, vá para **usuários**e, em seguida, clique no usuário.</span><span class="sxs-lookup"><span data-stu-id="1ff8e-156">In the left navigation of the Microsoft Teams admin center, go to **Users**, and then click the user.</span></span>
2. <span data-ttu-id="1ff8e-157">Selecione o usuário clicando à esquerda do nome do usuário e, em seguida, clique em **Editar configurações**.</span><span class="sxs-lookup"><span data-stu-id="1ff8e-157">Select the user by clicking to the left of the user name, and then click **Edit settings**.</span></span>
3. <span data-ttu-id="1ff8e-158">Selecione a política que você deseja atribuir e clique em **aplicar**.</span><span class="sxs-lookup"><span data-stu-id="1ff8e-158">Select the policy you want to assign, and then click **Apply**.</span></span>

<span data-ttu-id="1ff8e-159">Para atribuir uma política a até 20 usuários de uma vez, consulte [Editar configurações de usuários do teams em massa](edit-user-settings-in-bulk.md).</span><span class="sxs-lookup"><span data-stu-id="1ff8e-159">To assign a policy to up to 20 users at a time, see [Edit Teams user settings in bulk](edit-user-settings-in-bulk.md).</span></span>

<span data-ttu-id="1ff8e-160">Ou, você também pode fazer o seguinte:</span><span class="sxs-lookup"><span data-stu-id="1ff8e-160">Or, you can also do the following:</span></span>

1. <span data-ttu-id="1ff8e-161">Na navegação à esquerda do centro de administração do Microsoft Teams, vá para a página política.</span><span class="sxs-lookup"><span data-stu-id="1ff8e-161">In the left navigation of the Microsoft Teams admin center, go to the policy page.</span></span>
2. <span data-ttu-id="1ff8e-162">Selecione a política que você deseja atribuir clicando à esquerda do nome da política.</span><span class="sxs-lookup"><span data-stu-id="1ff8e-162">Select the policy you want to assign by clicking to the left of the policy name.</span></span>
3. <span data-ttu-id="1ff8e-163">Escolha **Gerenciar usuários**.</span><span class="sxs-lookup"><span data-stu-id="1ff8e-163">Select **Manage users**.</span></span>
4. <span data-ttu-id="1ff8e-164">No painel **Gerenciar usuários**, procure o usuário pelo nome de exibição ou pelo nome de usuário, escolha o nome e marque **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="1ff8e-164">In the **Manage users** pane, search for the user by display name or by user name, select the name, and then select **Add**.</span></span> <span data-ttu-id="1ff8e-165">Repita esta etapa para cada usuário que você deseja adicionar.</span><span class="sxs-lookup"><span data-stu-id="1ff8e-165">Repeat this step for each user that you want to add.</span></span>
5. <span data-ttu-id="1ff8e-166">Quando tiver terminado de adicionar usuários, selecione **salvar**.</span><span class="sxs-lookup"><span data-stu-id="1ff8e-166">When you're finished adding users, select **Save**.</span></span>

### <a name="using-powershell"></a><span data-ttu-id="1ff8e-167">Usando o PowerShell</span><span class="sxs-lookup"><span data-stu-id="1ff8e-167">Using PowerShell</span></span>

<span data-ttu-id="1ff8e-168">Cada tipo de política tem o próprio conjunto de cmdlets para gerenciá-lo.</span><span class="sxs-lookup"><span data-stu-id="1ff8e-168">Each policy type has it's own set of cmdlets for managing it.</span></span> <span data-ttu-id="1ff8e-169">Use o ```Grant-``` cmdlet para um determinado tipo de política para atribuir a política.</span><span class="sxs-lookup"><span data-stu-id="1ff8e-169">Use the ```Grant-``` cmdlet for a given policy type to assign the policy.</span></span> <span data-ttu-id="1ff8e-170">Por exemplo, use o ```Grant-CsTeamsMeetingPolicy``` cmdlet para atribuir uma política de reunião do teams aos usuários.</span><span class="sxs-lookup"><span data-stu-id="1ff8e-170">For example, use the ```Grant-CsTeamsMeetingPolicy``` cmdlet to assign a Teams meeting policy to users.</span></span> <span data-ttu-id="1ff8e-171">Esses cmdlets estão incluídos no módulo do PowerShell do Skype for Business Online e são documentados na [referência do cmdlet do Skype for Business](https://docs.microsoft.com/powershell/skype/intro?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="1ff8e-171">These cmdlets are included in the Skype for Business Online PowerShell module and are documented in the [Skype for Business cmdlet reference](https://docs.microsoft.com/powershell/skype/intro?view=skype-ps).</span></span>

 <span data-ttu-id="1ff8e-172">Baixe e instale o [módulo do PowerShell do Skype for Business online](https://www.microsoft.com/en-us/download/details.aspx?id=39366) (caso ainda não tenha sido feito) e, em seguida, execute o seguinte para se conectar ao Skype for Business Online e iniciar uma sessão.</span><span class="sxs-lookup"><span data-stu-id="1ff8e-172">Download and install the [Skype for Business Online PowerShell module](https://www.microsoft.com/en-us/download/details.aspx?id=39366) (if you haven't already), and then run the following to connect to Skype for Business Online and start a session.</span></span>

```powershell
Import-Module SkypeOnlineConnector
$Cred = Get-Credential
$CSSession = New-CsOnlineSession -Credential $Cred
Import-PSSession -Session $CSSession
```

<span data-ttu-id="1ff8e-173">Neste exemplo, atribuímos uma política de reunião do teams chamada política de reunião do aluno a um usuário chamado Reda.</span><span class="sxs-lookup"><span data-stu-id="1ff8e-173">In this example, we assign a Teams meeting policy named Student Meeting Policy to a user named Reda.</span></span>

```powershell
Grant-CsTeamsMeetingPolicy -Identity reda@contoso.com -PolicyName "Student Meeting Policy"
```

<span data-ttu-id="1ff8e-174">Para saber mais, consulte [Gerenciando políticas pelo PowerShell](teams-powershell-overview.md#managing-policies-via-powershell).</span><span class="sxs-lookup"><span data-stu-id="1ff8e-174">To learn more, see [Managing policies via PowerShell](teams-powershell-overview.md#managing-policies-via-powershell).</span></span>

## <a name="assign-a-policy-package"></a><span data-ttu-id="1ff8e-175">Atribuir um pacote de política</span><span class="sxs-lookup"><span data-stu-id="1ff8e-175">Assign a policy package</span></span>

<span data-ttu-id="1ff8e-176">Um pacote de política no Teams é uma coleção de políticas predefinidas e configurações de política que você pode atribuir aos usuários que têm funções iguais ou semelhantes em sua organização.</span><span class="sxs-lookup"><span data-stu-id="1ff8e-176">A policy package in Teams is a collection of predefined policies and policy settings that you can assign to users who have the same or similar roles in your organization.</span></span> <span data-ttu-id="1ff8e-177">Cada pacote de política é projetado em torno de uma função de usuário e inclui políticas predefinidas e configurações de política que dão suporte a atividades típicas para essa função.</span><span class="sxs-lookup"><span data-stu-id="1ff8e-177">Each policy package is designed around a user role and includes predefined policies and policy settings that support activities typical for that role.</span></span> <span data-ttu-id="1ff8e-178">Alguns exemplos de pacotes de política são o pacote de educação (professor) e o pacote de assistência médica (funcionário clínico).</span><span class="sxs-lookup"><span data-stu-id="1ff8e-178">Some examples of policy packages are the Education (Teacher) package and Healthcare (Clinical worker) package.</span></span>

<span data-ttu-id="1ff8e-179">Quando você atribui um pacote de política aos usuários, as políticas no pacote são criadas e você pode personalizar as configurações de cada política no pacote para atender às necessidades dos usuários.</span><span class="sxs-lookup"><span data-stu-id="1ff8e-179">When you assign a policy package to users, the policies in the package are created and you can then customize the settings of each policy in the package to meet users' needs.</span></span>

<span data-ttu-id="1ff8e-180">Para saber mais sobre pacotes de política, incluindo orientação passo a passo sobre como atribuí-los e gerenciá-los, consulte [gerenciar pacotes de política no Microsoft Teams](manage-policy-packages.md).</span><span class="sxs-lookup"><span data-stu-id="1ff8e-180">To learn more about policy packages, including step-by-step guidance on how to assign and manage them, see [Manage policy packages in Teams](manage-policy-packages.md).</span></span>

## <a name="assign-a-policy-to-a-batch-of-users"></a><span data-ttu-id="1ff8e-181">Atribuir uma política a um lote de usuários</span><span class="sxs-lookup"><span data-stu-id="1ff8e-181">Assign a policy to a batch of users</span></span>

[!INCLUDE [preview-feature](includes/preview-feature.md)]
 
<span data-ttu-id="1ff8e-182">Com a atribuição de política em lotes, você pode atribuir uma política a grandes conjuntos de usuários de uma vez sem precisar usar um script.</span><span class="sxs-lookup"><span data-stu-id="1ff8e-182">With batch policy assignment, you can assign a policy to large sets of users at a time without having to use a script.</span></span> <span data-ttu-id="1ff8e-183">Use o ```New-CsBatchPolicyAssignmentOperationd``` cmdlet para enviar um lote de usuários e a política que você deseja atribuir.</span><span class="sxs-lookup"><span data-stu-id="1ff8e-183">You use the ```New-CsBatchPolicyAssignmentOperationd``` cmdlet to submit a batch of users and the policy that you want to assign.</span></span> <span data-ttu-id="1ff8e-184">As atribuições são processadas como uma operação em segundo plano e uma ID de operação é gerada para cada lote.</span><span class="sxs-lookup"><span data-stu-id="1ff8e-184">The assignments are processed as a background operation and an operation ID is generated for each batch.</span></span> <span data-ttu-id="1ff8e-185">Em seguida, você pode ```Get-CsBatchPolicyAssignmentOperation``` usar o cmdlet para acompanhar o progresso e o status das tarefas em um lote.</span><span class="sxs-lookup"><span data-stu-id="1ff8e-185">You can then use the ```Get-CsBatchPolicyAssignmentOperation``` cmdlet to track the progress and status of the assignments in a batch.</span></span>

<span data-ttu-id="1ff8e-186">Um lote pode conter até 20.000 usuários.</span><span class="sxs-lookup"><span data-stu-id="1ff8e-186">A batch can contain up to 20,000 users.</span></span> <span data-ttu-id="1ff8e-187">Você pode especificar os usuários por sua ID de objeto, nome de usuário principal (UPN), endereço de protocolo de iniciação de sessão (SIP) ou endereço de email.</span><span class="sxs-lookup"><span data-stu-id="1ff8e-187">You can specify users by their object Id, user principal name (UPN), Session Initiation Protocol (SIP) address, or email address.</span></span>

> [!NOTE]
> <span data-ttu-id="1ff8e-188">No momento, a atribuição de política em lote não está disponível para todos os tipos de política de equipe.</span><span class="sxs-lookup"><span data-stu-id="1ff8e-188">Currently, batch policy assignment isn't available for all Teams policy types.</span></span> <span data-ttu-id="1ff8e-189">Consulte [New-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation) para obter a lista de tipos de política com suporte.</span><span class="sxs-lookup"><span data-stu-id="1ff8e-189">See [New-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation) for the list of supported policy types.</span></span>

### <a name="install-and-connect-to-the-microsoft-teams-powershell-module"></a><span data-ttu-id="1ff8e-190">Instalar e conectar-se ao módulo do PowerShell do Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="1ff8e-190">Install and connect to the Microsoft Teams PowerShell module</span></span>

> [!NOTE]
> <span data-ttu-id="1ff8e-191">Os cmdlets estão na versão de pré-lançamento do módulo do teams PowerShell.</span><span class="sxs-lookup"><span data-stu-id="1ff8e-191">The cmdlets are in the pre-release version of the Teams PowerShell module.</span></span> <span data-ttu-id="1ff8e-192">Siga estas etapas para desinstalar primeiro a versão geralmente disponível do módulo do teams PowerShell (se ele estiver instalado) e instale a versão de pré-lançamento mais recente do módulo a partir da Galeria de teste do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="1ff8e-192">Follow these steps to first uninstall the Generally Available version of the Teams PowerShell module (if it's installed), and then install the latest pre-release version of the module from the PowerShell Test Gallery.</span></span>

<span data-ttu-id="1ff8e-193">Se você ainda não fez isso, execute o seguinte para registrar a Galeria de teste do PowerShell como uma fonte confiável.</span><span class="sxs-lookup"><span data-stu-id="1ff8e-193">If you haven't already, run the following to register the PowerShell Test Gallery as a trusted source.</span></span>

```powershell
Register-PSRepository -SourceLocation https://www.poshtestgallery.com/api/v2 -Name PsTestGallery -InstallationPolicy Trusted
```

<span data-ttu-id="1ff8e-194">Se você tiver a versão geralmente disponível do módulo Teams PowerShell instalada, execute o seguinte para desinstalá-lo.</span><span class="sxs-lookup"><span data-stu-id="1ff8e-194">If you have the Generally Available version of the Teams PowerShell module installed, run the following to uninstall it.</span></span>

```powershell
Uninstall-Module MicrosoftTeams -AllVersions
```

<span data-ttu-id="1ff8e-195">Execute o seguinte para instalar o módulo do Microsoft Teams PowerShell mais recente da Galeria de teste do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="1ff8e-195">Run the following to install the latest Microsoft Teams PowerShell module from the PowerShell Test Gallery.</span></span>

```powershell
Install-Module MicrosoftTeams -Repository PSTestGallery
```

<span data-ttu-id="1ff8e-196">Execute o seguinte para se conectar ao Microsoft Teams e iniciar uma sessão.</span><span class="sxs-lookup"><span data-stu-id="1ff8e-196">Run the following to connect to Teams and start a session.</span></span>

```powershell
Connect-MicrosoftTeams
```

<span data-ttu-id="1ff8e-197">Quando for solicitado, entre usando suas credenciais de administrador.</span><span class="sxs-lookup"><span data-stu-id="1ff8e-197">When you're prompted, sign in using your admin credentials.</span></span>

### <a name="install-and-connect-to-the-azure-ad-powershell-for-graph-module-optional"></a><span data-ttu-id="1ff8e-198">Instalar e conectar-se ao módulo do Azure AD PowerShell para Graph (opcional)</span><span class="sxs-lookup"><span data-stu-id="1ff8e-198">Install and connect to the Azure AD PowerShell for Graph module (optional)</span></span>

<span data-ttu-id="1ff8e-199">Você também pode [fazer o download e instalar o módulo do Azure ad PowerShell para Graph](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2) (se ainda não tiver feito isso) e se conectar ao Azure ad para que você possa recuperar uma lista de usuários em sua organização.</span><span class="sxs-lookup"><span data-stu-id="1ff8e-199">You may also want to [download and install the Azure AD PowerShell for Graph module](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2) (if you haven't already) and connect to Azure AD so that you can retrieve a list of users in your organization.</span></span>

<span data-ttu-id="1ff8e-200">Execute o seguinte para se conectar ao Azure AD.</span><span class="sxs-lookup"><span data-stu-id="1ff8e-200">Run the following to connect to Azure AD.</span></span>

```powershell
Connect-AzureAD
```

<span data-ttu-id="1ff8e-201">Quando for solicitado, entre usando as mesmas credenciais de administrador usadas para se conectar ao Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="1ff8e-201">When you're prompted, sign in using the same admin credentials that you used to connect to Teams.</span></span>

### <a name="assign-a-policy-to-a-batch-of-users"></a><span data-ttu-id="1ff8e-202">Atribuir uma política a um lote de usuários</span><span class="sxs-lookup"><span data-stu-id="1ff8e-202">Assign a policy to a batch of users</span></span>

<span data-ttu-id="1ff8e-203">Neste exemplo, usamos o ```New-CsBatchPolicyAssignmentOperation``` cmdlet para atribuir uma política de configuração de aplicativo chamada política de configuração de aplicativo de RH a um lote de usuários listados no arquivo Users_ids. texto.</span><span class="sxs-lookup"><span data-stu-id="1ff8e-203">In this example, we use the ```New-CsBatchPolicyAssignmentOperation``` cmdlet to assign an app setup policy named HR App Setup Policy to a batch of users listed in the Users_ids.text file.</span></span>

```powershell
$user_ids = Get-Content .\users_ids.txt
New-CsBatchPolicyAssignmentOperation -PolicyType TeamsAppSetupPolicy -PolicyName "HR App Setup Policy" -Identity $users_ids -OperationName "Example 1 batch"
```

<span data-ttu-id="1ff8e-204">Neste exemplo, nós nos conectamos ao Azure AD para recuperar uma coleção de usuários e atribuir uma política de mensagem nomeada nova contratação de política de serviço a um lote de usuários especificados usando seus UPNs.</span><span class="sxs-lookup"><span data-stu-id="1ff8e-204">In this example, we connect to Azure AD to retrieve a collection of users and then assign a messaging policy named New Hire Messaging Policy to a batch of users specified by using their UPNs.</span></span>

```powershell
Connect-AzureAD
$users = Get-AzureADUser
New-CsBatchPolicyAssignmentOperation -PolicyType TeamsMessagingPolicy -PolicyName "New Hire Messaging Policy" -Identity $users.UserPrincipalName -OperationName "Example 2 batch"
```

<span data-ttu-id="1ff8e-205">Para saber mais, confira [novo – CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation).</span><span class="sxs-lookup"><span data-stu-id="1ff8e-205">To learn more, see [New-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation).</span></span>

### <a name="get-the-status-of-a-batch-assignment"></a><span data-ttu-id="1ff8e-206">Obter o status de uma atribuição em lote</span><span class="sxs-lookup"><span data-stu-id="1ff8e-206">Get the status of a batch assignment</span></span>

<span data-ttu-id="1ff8e-207">Execute o seguinte para obter o status de uma atribuição em lotes, em que operationId é a ID da operação retornada pelo ```New-CsBatchPolicyAssignmentOperation``` cmdlet para um determinado lote.</span><span class="sxs-lookup"><span data-stu-id="1ff8e-207">Run the following to get the status of a batch assignment, where OperationId is the operation ID that's returned by the ```New-CsBatchPolicyAssignmentOperation``` cmdlet for a given batch.</span></span>

```powershell
$Get-CsBatchPolicyAssignmentOperation -OperationId f985e013-0826-40bb-8c94-e5f367076044 | fl
```

<span data-ttu-id="1ff8e-208">Se a saída mostrar que ocorreu um erro, execute o seguinte para obter mais informações sobre erros, que estão na ```UserState``` propriedade.</span><span class="sxs-lookup"><span data-stu-id="1ff8e-208">If the output shows that an error occurred, run the following to get more information about errors, which are in the ```UserState``` property.</span></span>

```powershell
Get-CsBatchPolicyAssignmentOperation -OperationId f985e013-0826-40bb-8c94-e5f367076044 | Select -ExpandProperty UserState
```

<span data-ttu-id="1ff8e-209">Para saber mais, consulte [Get-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/get-csbatchpolicyassignmentoperation).</span><span class="sxs-lookup"><span data-stu-id="1ff8e-209">To learn more, see [Get-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/get-csbatchpolicyassignmentoperation).</span></span>

## <a name="assign-a-policy-to-a-group"></a><span data-ttu-id="1ff8e-210">Atribuir uma política a um grupo</span><span class="sxs-lookup"><span data-stu-id="1ff8e-210">Assign a policy to a group</span></span>

[!INCLUDE [preview-feature](includes/preview-feature.md)]

<span data-ttu-id="1ff8e-211">A atribuição de política de grupo permite atribuir uma política a um grupo de usuários, como um grupo de segurança ou unidade organizacional.</span><span class="sxs-lookup"><span data-stu-id="1ff8e-211">Group policy assignment lets you assign a policy to a group of users, such as a security group or organizational unit.</span></span> <span data-ttu-id="1ff8e-212">A atribuição de política é propagada para os membros do grupo de acordo com as regras de precedência.</span><span class="sxs-lookup"><span data-stu-id="1ff8e-212">The policy assignment is propagated to members of the group according to precedence rules.</span></span> <span data-ttu-id="1ff8e-213">Conforme os membros são adicionados ou removidos de um grupo, suas atribuições de política herdadas são atualizadas de acordo.</span><span class="sxs-lookup"><span data-stu-id="1ff8e-213">As members are added to or removed from a group, their inherited policy assignments are updated accordingly.</span></span>

<span data-ttu-id="1ff8e-214">Use o ```New-CsGroupPolicyAssignment``` cmdlet para atribuir uma política a um grupo.</span><span class="sxs-lookup"><span data-stu-id="1ff8e-214">You use the ```New-CsGroupPolicyAssignment``` cmdlet to assign a policy to a group.</span></span> <span data-ttu-id="1ff8e-215">Você pode especificar um grupo usando a identificação do objeto, o endereço SIP ou o endereço de email.</span><span class="sxs-lookup"><span data-stu-id="1ff8e-215">You can specify a group by using the object Id, SIP address, or email address.</span></span>

<span data-ttu-id="1ff8e-216">Quando você atribui a política, ela é imediatamente atribuída ao grupo.</span><span class="sxs-lookup"><span data-stu-id="1ff8e-216">When you assign the policy, it's immediately assigned to the group.</span></span> <span data-ttu-id="1ff8e-217">No entanto, observe que a propagação da atribuição da política para os membros do grupo é realizada como uma operação em segundo plano e pode demorar algum tempo, dependendo do tamanho do grupo.</span><span class="sxs-lookup"><span data-stu-id="1ff8e-217">However, note that the propagation of the policy assignment to members of the group is performed as a background operation and may take some time, depending on the size of the group.</span></span> <span data-ttu-id="1ff8e-218">O mesmo é verdadeiro quando uma política é desatribuída de um grupo ou quando os membros são adicionados ou removidos de um grupo.</span><span class="sxs-lookup"><span data-stu-id="1ff8e-218">The same is true when a policy is unassigned from a group, or when members are added to or removed from a group.</span></span>

> [!NOTE]
> <span data-ttu-id="1ff8e-219">No momento, a atribuição de política de grupo não está disponível para todos os tipos de política de equipe.</span><span class="sxs-lookup"><span data-stu-id="1ff8e-219">Currently, group policy assignment isn't available for all Teams policy types.</span></span> <span data-ttu-id="1ff8e-220">Consulte [New-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/new-csgrouppolicyassignment) para obter a lista de tipos de política com suporte.</span><span class="sxs-lookup"><span data-stu-id="1ff8e-220">See [New-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/new-csgrouppolicyassignment) for the list of supported policy types.</span></span>

### <a name="what-you-need-to-know-about-group-policy-assignment"></a><span data-ttu-id="1ff8e-221">O que você precisa saber sobre a atribuição de política de grupo</span><span class="sxs-lookup"><span data-stu-id="1ff8e-221">What you need to know about group policy assignment</span></span>

<span data-ttu-id="1ff8e-222">Antes de começar, é importante entender as regras de precedência e a classificação da atribuição da política de grupo.</span><span class="sxs-lookup"><span data-stu-id="1ff8e-222">Before you get started, it's important to understand precedence rules and group policy assignment ranking.</span></span>

#### <a name="precedence-rules"></a><span data-ttu-id="1ff8e-223">Regras de precedência</span><span class="sxs-lookup"><span data-stu-id="1ff8e-223">Precedence rules</span></span>

<span data-ttu-id="1ff8e-224">Para um determinado tipo de política, a política efetiva de um usuário é determinada de acordo com o seguinte:</span><span class="sxs-lookup"><span data-stu-id="1ff8e-224">For a given policy type, a user's effective policy is determined according to the following:</span></span>

- <span data-ttu-id="1ff8e-225">Uma política que é atribuída diretamente a um usuário tem precedência sobre qualquer outra política do mesmo tipo que esteja atribuída a um grupo.</span><span class="sxs-lookup"><span data-stu-id="1ff8e-225">A policy that's directly assigned to a user takes precedence over any other policy of the same type that's assigned to a group.</span></span> <span data-ttu-id="1ff8e-226">Em outras palavras, se um usuário estiver diretamente atribuído a uma política de um determinado tipo, esse usuário não herdará uma política do mesmo tipo de um grupo.</span><span class="sxs-lookup"><span data-stu-id="1ff8e-226">In other words, if a user is directly assigned a policy of a given type, that user won't inherit a policy of the same type from a group.</span></span> <span data-ttu-id="1ff8e-227">Isso também significa que, se um usuário tiver uma política de um determinado tipo que foi atribuído diretamente a ele, será necessário remover essa política do usuário antes de poder herdar uma política do mesmo tipo de um grupo.</span><span class="sxs-lookup"><span data-stu-id="1ff8e-227">This also means that if a user has a policy of a given type that was directly assigned to them, you have to remove that policy from the user before they can inherit a policy of the same type from a group.</span></span>
- <span data-ttu-id="1ff8e-228">Se um usuário não tiver uma política diretamente atribuída a ele e for um membro de dois ou mais grupos e cada grupo tiver uma política do mesmo tipo atribuído a ele, o usuário herdará a política da atribuição de grupo que tem a classificação mais alta.</span><span class="sxs-lookup"><span data-stu-id="1ff8e-228">If a user doesn't have a policy directly assigned to them and is a member of two or more groups and each group has a policy of the same type assigned to it, the user inherits the policy of the group assignment that has the highest ranking.</span></span>
- <span data-ttu-id="1ff8e-229">Se um usuário não for membro de nenhum grupo ao qual uma política atribuiu uma política, a política global (padrão para toda a organização) para esse tipo de política se aplicará ao usuário.</span><span class="sxs-lookup"><span data-stu-id="1ff8e-229">If a user isn't a member of any groups that are assigned a policy, the global (Org-wide default) policy for that policy type applies to the user.</span></span>

<span data-ttu-id="1ff8e-230">A política efetiva de um usuário é atualizada de acordo com essas regras quando um usuário é adicionado ou removido de um grupo que é atribuído a uma política, uma política é desatribuída de um grupo ou uma política diretamente atribuída ao usuário é removida.</span><span class="sxs-lookup"><span data-stu-id="1ff8e-230">A user's effective policy is updated according to these rules when a user is added to or removed from a group that's assigned a policy, a policy is unassigned from a group, or a policy that's directly assigned to the user is removed.</span></span>

#### <a name="group-assignment-ranking"></a><span data-ttu-id="1ff8e-231">Classificação de atribuição de grupo</span><span class="sxs-lookup"><span data-stu-id="1ff8e-231">Group assignment ranking</span></span>
 
<span data-ttu-id="1ff8e-232">Ao atribuir uma política a um grupo, você especifica uma classificação para a atribuição de grupo.</span><span class="sxs-lookup"><span data-stu-id="1ff8e-232">When you assign a policy to a group, you specify a ranking for the group assignment.</span></span> <span data-ttu-id="1ff8e-233">Isso é usado para determinar qual política um usuário deve herdar como política efetiva se o usuário for membro de dois ou mais grupos e cada grupo tiver atribuído uma política do mesmo tipo.</span><span class="sxs-lookup"><span data-stu-id="1ff8e-233">This is used to determine which policy a user should inherit as their effective policy if the user is a member of two or more groups and each group is assigned a policy of the same type.</span></span>

<span data-ttu-id="1ff8e-234">A classificação da atribuição de grupo é relativa a outras atribuições de política de grupo do mesmo tipo.</span><span class="sxs-lookup"><span data-stu-id="1ff8e-234">The group assignment ranking is relative to other group policy assignments of the same type.</span></span> <span data-ttu-id="1ff8e-235">Por exemplo, se você estiver atribuindo uma política de chamada a dois grupos, defina a classificação de uma tarefa como 1 e a outra como 2, com 1 sendo a classificação mais alta.</span><span class="sxs-lookup"><span data-stu-id="1ff8e-235">For example, if you're assigning a calling policy to two groups, set the ranking of one assignment to 1 and the other to 2, with 1 being the highest ranking.</span></span> <span data-ttu-id="1ff8e-236">A classificação de atribuição de grupo indica qual associação de grupo é mais importante ou mais relevante do que outras associações de grupo em relação à herança.</span><span class="sxs-lookup"><span data-stu-id="1ff8e-236">The group assignment ranking indicates which group membership is more important or more relevant than other group memberships with regards to inheritance.</span></span>
 
<span data-ttu-id="1ff8e-237">Digamos, por exemplo, que você tem dois grupos, armazenar funcionários e gerentes da loja.</span><span class="sxs-lookup"><span data-stu-id="1ff8e-237">Say, for example, you have two groups, Store Employees and Store Managers.</span></span> <span data-ttu-id="1ff8e-238">Os dois grupos recebem uma política de chamada de equipes, armazenando a política de chamadas de gerentes de loja e a política de chamadas de gerentes de loja</span><span class="sxs-lookup"><span data-stu-id="1ff8e-238">Both groups are assigned a Teams calling policy, Store Employees Calling Policy and Store Managers Calling Policy, respectively.</span></span> <span data-ttu-id="1ff8e-239">Para um gerente de loja que está em ambos os grupos, sua função como gerente é mais relevante do que a função de um funcionário, portanto, a política de chamada atribuída ao grupo de gerentes da loja deve ter uma classificação mais alta.</span><span class="sxs-lookup"><span data-stu-id="1ff8e-239">For a store manager who is in both groups, their role as a manager is more relevant than their role as an employee, so the calling policy that's assigned to the Store Managers group should have a higher ranking.</span></span>

|<span data-ttu-id="1ff8e-240">Grupos</span><span class="sxs-lookup"><span data-stu-id="1ff8e-240">Group</span></span> |<span data-ttu-id="1ff8e-241">Nome da política de chamada de equipes</span><span class="sxs-lookup"><span data-stu-id="1ff8e-241">Teams calling policy name</span></span>  |<span data-ttu-id="1ff8e-242">Classificação</span><span class="sxs-lookup"><span data-stu-id="1ff8e-242">Rank</span></span>|
|---------|---------|---|
|<span data-ttu-id="1ff8e-243">Gerentes da loja</span><span class="sxs-lookup"><span data-stu-id="1ff8e-243">Store Managers</span></span>   |<span data-ttu-id="1ff8e-244">Política de chamadas de gerentes de loja</span><span class="sxs-lookup"><span data-stu-id="1ff8e-244">Store Managers Calling Policy</span></span>         |<span data-ttu-id="1ff8e-245">1</span><span class="sxs-lookup"><span data-stu-id="1ff8e-245">1</span></span>|
|<span data-ttu-id="1ff8e-246">Loja de funcionários</span><span class="sxs-lookup"><span data-stu-id="1ff8e-246">Store Employees</span></span>    |<span data-ttu-id="1ff8e-247">Política de chamadas de funcionários da loja</span><span class="sxs-lookup"><span data-stu-id="1ff8e-247">Store Employees Calling Policy</span></span>      |<span data-ttu-id="1ff8e-248">2</span><span class="sxs-lookup"><span data-stu-id="1ff8e-248">2</span></span>|

<span data-ttu-id="1ff8e-249">Se você não especificar uma classificação, a atribuição de política terá a classificação mais baixa.</span><span class="sxs-lookup"><span data-stu-id="1ff8e-249">If you don't specify a ranking, the policy assignment is given the lowest ranking.</span></span>

### <a name="install-and-connect-to-the-microsoft-teams-powershell-module"></a><span data-ttu-id="1ff8e-250">Instalar e conectar-se ao módulo do PowerShell do Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="1ff8e-250">Install and connect to the Microsoft Teams PowerShell module</span></span>

> [!NOTE]
> <span data-ttu-id="1ff8e-251">Os cmdlets estão na versão de pré-lançamento do módulo do teams PowerShell.</span><span class="sxs-lookup"><span data-stu-id="1ff8e-251">The cmdlets are in the pre-release version of the Teams PowerShell module.</span></span> <span data-ttu-id="1ff8e-252">Siga estas etapas para desinstalar primeiro a versão geralmente disponível do módulo do teams PowerShell (se ele estiver instalado) e instale a versão de pré-lançamento mais recente do módulo a partir da Galeria de teste do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="1ff8e-252">Follow these steps to first uninstall the Generally Available version of the Teams PowerShell module (if it's installed), and then install the latest pre-release version of the module from the PowerShell Test Gallery.</span></span>

<span data-ttu-id="1ff8e-253">Se você ainda não fez isso, execute o seguinte para registrar a Galeria de teste do PowerShell como uma fonte confiável.</span><span class="sxs-lookup"><span data-stu-id="1ff8e-253">If you haven't already, run the following to register the PowerShell Test Gallery as a trusted source.</span></span>

```powershell
Register-PSRepository -SourceLocation https://www.poshtestgallery.com/api/v2 -Name PsTestGallery -InstallationPolicy Trusted
```

<span data-ttu-id="1ff8e-254">Se você tiver a versão geralmente disponível do módulo Teams PowerShell instalada, execute o seguinte para desinstalá-lo.</span><span class="sxs-lookup"><span data-stu-id="1ff8e-254">If you have the Generally Available version of the Teams PowerShell module installed, run the following to uninstall it.</span></span>

```powershell
Uninstall-Module MicrosoftTeams -AllVersions
```

<span data-ttu-id="1ff8e-255">Execute o seguinte para instalar o módulo do Microsoft Teams PowerShell mais recente da Galeria de teste do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="1ff8e-255">Run the following to install the latest Microsoft Teams PowerShell module from the PowerShell Test Gallery.</span></span>

```powershell
Install-Module MicrosoftTeams -Repository PSTestGallery
```

<span data-ttu-id="1ff8e-256">Execute o seguinte para se conectar ao Microsoft Teams e iniciar uma sessão.</span><span class="sxs-lookup"><span data-stu-id="1ff8e-256">Run the following to connect to Teams and start a session.</span></span>

```powershell
Connect-MicrosoftTeams
```

<span data-ttu-id="1ff8e-257">Quando for solicitado, entre usando suas credenciais de administrador.</span><span class="sxs-lookup"><span data-stu-id="1ff8e-257">When you're prompted, sign in using your admin credentials.</span></span>

### <a name="assign-a-policy-to-a-group"></a><span data-ttu-id="1ff8e-258">Atribuir uma política a um grupo</span><span class="sxs-lookup"><span data-stu-id="1ff8e-258">Assign a policy to a group</span></span>

<span data-ttu-id="1ff8e-259">Neste exemplo, usamos o ```New-CsGroupPolicyAssignment``` cmdlet para atribuir uma política de reunião do teams chamada política de reunião de gerentes de revenda a um grupo com uma classificação de atribuição de 1.</span><span class="sxs-lookup"><span data-stu-id="1ff8e-259">In this example, we use the ```New-CsGroupPolicyAssignment``` cmdlet to assign a Teams meeting policy named Retail Managers Meeting Policy to a group with an assignment ranking of 1.</span></span>

```powershell
New-CsGroupPolicyAssignment -GroupId d8ebfa45-0f28-4d2d-9bcc-b158a49e2d17 -PolicyType TeamsMeetingPolicy -PolicyName "Retail Managers Meeting Policy" -Rank 1
```

<span data-ttu-id="1ff8e-260">Para saber mais, confira [novo – CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/new-csgrouppolicyassignment).</span><span class="sxs-lookup"><span data-stu-id="1ff8e-260">To learn more, see [New-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/new-csgrouppolicyassignment).</span></span>

### <a name="get-policy-assignments-for-a-group"></a><span data-ttu-id="1ff8e-261">Obter atribuições de política para um grupo</span><span class="sxs-lookup"><span data-stu-id="1ff8e-261">Get policy assignments for a group</span></span>

<span data-ttu-id="1ff8e-262">Use o ```Get-CsGroupPolicyAssignment``` cmdlet para obter todas as políticas atribuídas a um grupo.</span><span class="sxs-lookup"><span data-stu-id="1ff8e-262">Use the ```Get-CsGroupPolicyAssignment``` cmdlet to get all policies assigned to a group.</span></span> <span data-ttu-id="1ff8e-263">Observe que os grupos são sempre listados pela ID do grupo mesmo se seu endereço SIP ou endereço de email foi usado para atribuir a política.</span><span class="sxs-lookup"><span data-stu-id="1ff8e-263">Note that groups are always listed by their group Id even if its SIP address or email address was used to assign the policy.</span></span>

<span data-ttu-id="1ff8e-264">Neste exemplo, recuperamos todas as políticas atribuídas a um grupo específico.</span><span class="sxs-lookup"><span data-stu-id="1ff8e-264">In this example, we retrieve all policies assigned to a specific group.</span></span>

```powershell
Get-CsGroupPolicyAssignment -GroupId e050ce51-54bc-45b7-b3e6-c00343d31274
```

<span data-ttu-id="1ff8e-265">Neste exemplo, retornamos todos os grupos que recebem uma política de reunião do teams.</span><span class="sxs-lookup"><span data-stu-id="1ff8e-265">In this example, we return all groups that are assigned a Teams meeting policy.</span></span>

```powershell
Get-CsGroupPolicyAssignment -PolicyType TeamsMeetingPolicy
```

<span data-ttu-id="1ff8e-266">Para saber mais, consulte [Get-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/get-csgrouppolicyassignment).</span><span class="sxs-lookup"><span data-stu-id="1ff8e-266">To learn more, see [Get-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/get-csgrouppolicyassignment).</span></span>

### <a name="remove-a-policy-from-a-group"></a><span data-ttu-id="1ff8e-267">Remover uma política de um grupo</span><span class="sxs-lookup"><span data-stu-id="1ff8e-267">Remove a policy from a group</span></span>

<span data-ttu-id="1ff8e-268">Use o ```Remove-CsGroupPolicyAssignment``` cmdlet para remover uma política de um grupo.</span><span class="sxs-lookup"><span data-stu-id="1ff8e-268">Use the ```Remove-CsGroupPolicyAssignment``` cmdlet to remove a policy from a group.</span></span> <span data-ttu-id="1ff8e-269">Quando você remove uma política de um grupo, as prioridades de outras políticas do mesmo tipo atribuídas a esse grupo e que têm uma classificação mais baixa são atualizadas.</span><span class="sxs-lookup"><span data-stu-id="1ff8e-269">When you remove a policy from a group, the priorities of other policies of the same type assigned to that group and that have a lower ranking are updated.</span></span> <span data-ttu-id="1ff8e-270">Por exemplo, se você remover uma política que tem uma classificação de 2, as políticas que têm uma classificação de 3 e 4 são atualizadas para refletir a nova classificação.</span><span class="sxs-lookup"><span data-stu-id="1ff8e-270">For example, if you remove a policy that has a ranking of 2, policies that have a ranking of 3 and 4 are updated to reflect their new ranking.</span></span> <span data-ttu-id="1ff8e-271">As duas tabelas a seguir mostram este exemplo.</span><span class="sxs-lookup"><span data-stu-id="1ff8e-271">The following two tables show this example.</span></span>

<span data-ttu-id="1ff8e-272">Aqui está uma lista das atribuições e prioridades de política para uma política de reunião do teams.</span><span class="sxs-lookup"><span data-stu-id="1ff8e-272">Here's a list of the policy assignments and priorities for a Teams meeting policy.</span></span>

|<span data-ttu-id="1ff8e-273">Nome do grupo</span><span class="sxs-lookup"><span data-stu-id="1ff8e-273">Group name</span></span>  |<span data-ttu-id="1ff8e-274">Nome da política</span><span class="sxs-lookup"><span data-stu-id="1ff8e-274">Policy name</span></span>  |<span data-ttu-id="1ff8e-275">Classificação</span><span class="sxs-lookup"><span data-stu-id="1ff8e-275">Rank</span></span>|
|---------|---------|---------|
|<span data-ttu-id="1ff8e-276">Vendas</span><span class="sxs-lookup"><span data-stu-id="1ff8e-276">Sales</span></span>    |<span data-ttu-id="1ff8e-277">Política de vendas</span><span class="sxs-lookup"><span data-stu-id="1ff8e-277">Sales policy</span></span>       | <span data-ttu-id="1ff8e-278">1</span><span class="sxs-lookup"><span data-stu-id="1ff8e-278">1</span></span>        |
|<span data-ttu-id="1ff8e-279">Região oeste</span><span class="sxs-lookup"><span data-stu-id="1ff8e-279">West Region</span></span>     |<span data-ttu-id="1ff8e-280">Política de região oeste</span><span class="sxs-lookup"><span data-stu-id="1ff8e-280">West Region policy</span></span>         |<span data-ttu-id="1ff8e-281">2</span><span class="sxs-lookup"><span data-stu-id="1ff8e-281">2</span></span>         |
|<span data-ttu-id="1ff8e-282">Visões</span><span class="sxs-lookup"><span data-stu-id="1ff8e-282">Division</span></span>    |<span data-ttu-id="1ff8e-283">Política de divisão</span><span class="sxs-lookup"><span data-stu-id="1ff8e-283">Division policy</span></span>         |<span data-ttu-id="1ff8e-284">3</span><span class="sxs-lookup"><span data-stu-id="1ff8e-284">3</span></span>         |
|<span data-ttu-id="1ff8e-285">Subsidiária da</span><span class="sxs-lookup"><span data-stu-id="1ff8e-285">Subsidiary</span></span>   |<span data-ttu-id="1ff8e-286">Política da subsidiária</span><span class="sxs-lookup"><span data-stu-id="1ff8e-286">Subsidiary policy</span></span>        |<span data-ttu-id="1ff8e-287">4</span><span class="sxs-lookup"><span data-stu-id="1ff8e-287">4</span></span>         |

<span data-ttu-id="1ff8e-288">Se removermos a política de região oeste do grupo região oeste, as atribuições e prioridades de política serão atualizadas da maneira a seguir.</span><span class="sxs-lookup"><span data-stu-id="1ff8e-288">If we remove the West Region policy from the West Region group, the policy assignments and priorities are updated as follows.</span></span>

|<span data-ttu-id="1ff8e-289">Nome do grupo</span><span class="sxs-lookup"><span data-stu-id="1ff8e-289">Group name</span></span>  |<span data-ttu-id="1ff8e-290">Nome da política</span><span class="sxs-lookup"><span data-stu-id="1ff8e-290">Policy name</span></span>  |<span data-ttu-id="1ff8e-291">Classificação</span><span class="sxs-lookup"><span data-stu-id="1ff8e-291">Rank</span></span>|
|---------|---------|---------|
|<span data-ttu-id="1ff8e-292">Vendas</span><span class="sxs-lookup"><span data-stu-id="1ff8e-292">Sales</span></span>    |<span data-ttu-id="1ff8e-293">Política de vendas</span><span class="sxs-lookup"><span data-stu-id="1ff8e-293">Sales policy</span></span>       | <span data-ttu-id="1ff8e-294">1</span><span class="sxs-lookup"><span data-stu-id="1ff8e-294">1</span></span>        |
|<span data-ttu-id="1ff8e-295">Visões</span><span class="sxs-lookup"><span data-stu-id="1ff8e-295">Division</span></span>    |<span data-ttu-id="1ff8e-296">Política de divisão</span><span class="sxs-lookup"><span data-stu-id="1ff8e-296">Division policy</span></span>         |<span data-ttu-id="1ff8e-297">2</span><span class="sxs-lookup"><span data-stu-id="1ff8e-297">2</span></span>         |
|<span data-ttu-id="1ff8e-298">Subsidiária da</span><span class="sxs-lookup"><span data-stu-id="1ff8e-298">Subsidiary</span></span>   |<span data-ttu-id="1ff8e-299">Política da subsidiária</span><span class="sxs-lookup"><span data-stu-id="1ff8e-299">Subsidiary policy</span></span>        |<span data-ttu-id="1ff8e-300">3</span><span class="sxs-lookup"><span data-stu-id="1ff8e-300">3</span></span>        |

<span data-ttu-id="1ff8e-301">Neste exemplo, removemos a política de reunião do teams de um grupo.</span><span class="sxs-lookup"><span data-stu-id="1ff8e-301">In this example, we remove the Teams meeting policy from a group.</span></span>

```powershell
Remove-CsGroupPolicyAssignment -PolicyType TeamsMeetingPolicy -GroupId f985e013-0826-40bb-8c94-e5f367076044
```

<span data-ttu-id="1ff8e-302">Para saber mais, veja [Remove-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/remove-csgrouppolicyassignment).</span><span class="sxs-lookup"><span data-stu-id="1ff8e-302">To learn more, see [Remove-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/remove-csgrouppolicyassignment).</span></span>

### <a name="change-a-policy-assignment-for-a-group"></a><span data-ttu-id="1ff8e-303">Alterar uma atribuição de política para um grupo</span><span class="sxs-lookup"><span data-stu-id="1ff8e-303">Change a policy assignment for a group</span></span>

<span data-ttu-id="1ff8e-304">Depois de atribuir uma política a um grupo, você pode usar o ```Set-CsGroupPolicyAssignmentd``` cmdlet para alterar a atribuição da política desse grupo da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="1ff8e-304">After you assign a policy to a group, you can use the ```Set-CsGroupPolicyAssignmentd``` cmdlet to change that group's policy assignment as follows:</span></span>

- <span data-ttu-id="1ff8e-305">Alterar a classificação</span><span class="sxs-lookup"><span data-stu-id="1ff8e-305">Change the ranking</span></span>
- <span data-ttu-id="1ff8e-306">Alterar a política de um determinado tipo de política</span><span class="sxs-lookup"><span data-stu-id="1ff8e-306">Change the policy of a given policy type</span></span>
- <span data-ttu-id="1ff8e-307">Alterar a política de um determinado tipo de política e a classificação</span><span class="sxs-lookup"><span data-stu-id="1ff8e-307">Change the policy of a given policy type and the ranking</span></span>

<span data-ttu-id="1ff8e-308">Neste exemplo, alteramos a política de estacionamento de chamada de equipe de um grupo para uma política chamada SupportCallPark e a classificação de atribuição para 3.</span><span class="sxs-lookup"><span data-stu-id="1ff8e-308">In this example, we change a group's Teams call park policy to a policy named SupportCallPark and the assignment ranking to 3.</span></span>

```powershell
Set-CsGroupPolicyAssignment -GroupId 566b8d39-5c5c-4aaa-bc07-4f36278a1b38 -PolicyType TeamsMeetingPolicy -PolicyName SupportCallPark -Rank 3
```

<span data-ttu-id="1ff8e-309">Para saber mais, consulte [set-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/set-csgrouppolicyassignment).</span><span class="sxs-lookup"><span data-stu-id="1ff8e-309">To learn more, see [Set-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/set-csgrouppolicyassignment).</span></span>

### <a name="change-the-effective-policy-for-a-user"></a><span data-ttu-id="1ff8e-310">Alterar a política em vigor para um usuário</span><span class="sxs-lookup"><span data-stu-id="1ff8e-310">Change the effective policy for a user</span></span>

<span data-ttu-id="1ff8e-311">Aqui está um exemplo de como alterar a política efetiva para um usuário que recebe diretamente uma política.</span><span class="sxs-lookup"><span data-stu-id="1ff8e-311">Here's an example of how to change the effective policy for a user who is directly assigned a policy.</span></span>

<span data-ttu-id="1ff8e-312">Primeiro, usamos o ```Get-CsUserPolicyAssignment``` cmdlet em conjunto com o ```PolicySource``` parâmetro para obter detalhes das políticas de transmissão de reunião do teams associadas ao usuário.</span><span class="sxs-lookup"><span data-stu-id="1ff8e-312">First, we use the ```Get-CsUserPolicyAssignment``` cmdlet together with the ```PolicySource``` parameter to get details of the Teams meeting broadcast policies associated with the user.</span></span> <span data-ttu-id="1ff8e-313">Para saber mais, consulte [Get-CsUserPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/get-csuserpolicyassignment).</span><span class="sxs-lookup"><span data-stu-id="1ff8e-313">To learn more, see [Get-CsUserPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/get-csuserpolicyassignment).</span></span>

```powershell
Get-CsUserPolicyAssignment -Identity daniel@contoso.com -PolicyType TeamsMeetingBroadcastPolicy | select -ExpandProperty PolicySource
```

<span data-ttu-id="1ff8e-314">A saída mostra que o usuário foi diretamente atribuído a uma política de transmissão de reunião do teams chamada eventos do funcionário, que tem precedência sobre a política denominada eventos dinâmicos do fornecedor que é atribuída a um grupo ao qual o usuário pertence.</span><span class="sxs-lookup"><span data-stu-id="1ff8e-314">The output shows that the user was directly assigned a Teams meeting broadcast policy named Employee Events, which takes precedence over the policy named Vendor Live Events that's assigned to a group the user belongs to.</span></span>

```
AssignmentType PolicyName         Reference
-------------- ----------         ---------
Direct         Employee Events
Group          Vendor Live Events 566b8d39-5c5c-4aaa-bc07-4f36278a1b38
```

<span data-ttu-id="1ff8e-315">Agora, removemos a política de eventos de funcionários do usuário.</span><span class="sxs-lookup"><span data-stu-id="1ff8e-315">Now, we remove the Employee Events policy from the user.</span></span> <span data-ttu-id="1ff8e-316">Isso significa que o usuário não tem mais uma política de transmissão de reunião do teams diretamente atribuída a elas e herdará a política de eventos dinâmicos do fornecedor que é atribuída ao grupo ao qual o usuário pertence.</span><span class="sxs-lookup"><span data-stu-id="1ff8e-316">This means that the user no longer has a Teams meeting broadcast policy directly assigned to them and will inherit the Vendor Live Events policy that's assigned to the group the user belongs to.</span></span> 

<span data-ttu-id="1ff8e-317">Use o cmdlet a seguir no módulo do PowerShell do Skype for Business para fazer isso.</span><span class="sxs-lookup"><span data-stu-id="1ff8e-317">Use the following cmdlet in the Skype for Business PowerShell module to do this.</span></span>

```powershell
Grant-CsTeamsMeetingBroadcastPolicy -Identity daniel@contoso.com -PolicyName $null
```

<span data-ttu-id="1ff8e-318">Você pode usar o cmdlet a seguir no módulo do PowerShell Teams para fazer isso em escala durante uma atribuição de política em lotes, onde $users é uma lista de usuários que você especifica.</span><span class="sxs-lookup"><span data-stu-id="1ff8e-318">You can use following cmdlet in the Teams Powershell module to do this at scale though a batch policy assignment, where $users is a list of users that you specify.</span></span>

```powershell
New-CsBatchPolicyAssignmentOperation -OperationName "Assigning null at bulk" -PolicyType TeamsMeetingBroadcastPolicy -PolicyName $null -Identity $users  
```

## <a name="related-topics"></a><span data-ttu-id="1ff8e-319">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="1ff8e-319">Related topics</span></span>

- [<span data-ttu-id="1ff8e-320">Visão Geral do PowerShell do Teams</span><span class="sxs-lookup"><span data-stu-id="1ff8e-320">Teams PowerShell Overview</span></span>](teams-powershell-overview.md)