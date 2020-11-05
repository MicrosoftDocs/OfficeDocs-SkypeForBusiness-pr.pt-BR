---
title: Pacotes de política de equipe para o governo
author: lanachin
ms.author: v-lanac
manager: serdars
ms.reviewer: aaglick
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
f1.keywords: ''
ms.custom: ''
localization_priority: Normal
search.appverid: MET150
description: Saiba como usar e gerenciar pacotes de política de equipe para sua organização governamental.
ms.openlocfilehash: 8ef632689cb52180e8fd18cf4047fb9a25150885
ms.sourcegitcommit: ee217e1d7188842c7becd19387fd421b485c3575
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/04/2020
ms.locfileid: "48908590"
---
# <a name="teams-policy-packages-for-government"></a><span data-ttu-id="58d02-103">Pacotes de política de equipe para o governo</span><span class="sxs-lookup"><span data-stu-id="58d02-103">Teams policy packages for government</span></span>

> [!NOTE]
> <span data-ttu-id="58d02-104">Atualmente, os pacotes de política não estão disponíveis nas implantações do Microsoft 365 governo GCC High ou DoD.</span><span class="sxs-lookup"><span data-stu-id="58d02-104">Policy packages are currently not available in Microsoft 365 Government GCC High or DoD deployments.</span></span>

## <a name="overview"></a><span data-ttu-id="58d02-105">Visão geral</span><span class="sxs-lookup"><span data-stu-id="58d02-105">Overview</span></span>

<span data-ttu-id="58d02-106">Um [pacote de política](manage-policy-packages.md) no Microsoft Teams é uma coleção de políticas predefinidas e configurações de política que você pode atribuir aos usuários que têm funções semelhantes em sua organização.</span><span class="sxs-lookup"><span data-stu-id="58d02-106">A [policy package](manage-policy-packages.md) in Microsoft Teams is a collection of predefined policies and policy settings that you can assign to users who have similar roles in your organization.</span></span> <span data-ttu-id="58d02-107">Os pacotes de políticas simplificam, otimizam e ajudam a fornecer consistência ao gerenciar políticas.</span><span class="sxs-lookup"><span data-stu-id="58d02-107">Policy packages simplify, streamline, and help provide consistency when managing policies.</span></span> <span data-ttu-id="58d02-108">Você pode personalizar as configurações das políticas do pacote para atender às necessidades dos seus usuários.</span><span class="sxs-lookup"><span data-stu-id="58d02-108">You can customize the settings of the policies in the package to suit the needs of your users.</span></span> <span data-ttu-id="58d02-109">Quando você altera as configurações de políticas em um pacote de política, todos os usuários atribuídos a esse pacote obtêm as configurações atualizadas.</span><span class="sxs-lookup"><span data-stu-id="58d02-109">When you change the settings of policies in a policy package, all users who are assigned to that package get the updated settings.</span></span> <span data-ttu-id="58d02-110">Você pode gerenciar pacotes de política usando o centro de administração do Microsoft Teams ou o PowerShell.</span><span class="sxs-lookup"><span data-stu-id="58d02-110">You can manage policy packages by using the Microsoft Teams admin center or PowerShell.</span></span>

<span data-ttu-id="58d02-111">Pacotes de política pré-defina políticas para o seguinte, dependendo do pacote:</span><span class="sxs-lookup"><span data-stu-id="58d02-111">Policy packages pre-define policies for the following, depending on the package:</span></span>

- <span data-ttu-id="58d02-112">Mensagens</span><span class="sxs-lookup"><span data-stu-id="58d02-112">Messaging</span></span>
- <span data-ttu-id="58d02-113">Reuniões</span><span class="sxs-lookup"><span data-stu-id="58d02-113">Meetings</span></span>
- <span data-ttu-id="58d02-114">Chamadas</span><span class="sxs-lookup"><span data-stu-id="58d02-114">Calling</span></span>
- <span data-ttu-id="58d02-115">Configuração do aplicativo</span><span class="sxs-lookup"><span data-stu-id="58d02-115">App setup</span></span>
- <span data-ttu-id="58d02-116">Eventos ao vivo</span><span class="sxs-lookup"><span data-stu-id="58d02-116">Live events</span></span>

<span data-ttu-id="58d02-117">Atualmente, o Teams inclui os seguintes pacotes de política para o governo.</span><span class="sxs-lookup"><span data-stu-id="58d02-117">Teams currently includes the following policy packages for government.</span></span>

|<span data-ttu-id="58d02-118">Nome do pacote no centro de administração do Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="58d02-118">Package name in the Microsoft Teams admin center</span></span>|<span data-ttu-id="58d02-119">Melhor usado para</span><span class="sxs-lookup"><span data-stu-id="58d02-119">Best used for</span></span>|<span data-ttu-id="58d02-120">Descrição</span><span class="sxs-lookup"><span data-stu-id="58d02-120">Description</span></span> |
|---------|---------|---------|
|<span data-ttu-id="58d02-121">Diretor de segurança pública</span><span class="sxs-lookup"><span data-stu-id="58d02-121">Public safety officer</span></span>  |<span data-ttu-id="58d02-122">Diretores de segurança públicos em sua organização governamental</span><span class="sxs-lookup"><span data-stu-id="58d02-122">Public safety officers in your government organization</span></span>  |<span data-ttu-id="58d02-123">Cria um conjunto de políticas e configurações de política que se aplicam a órgãos públicos de segurança em sua organização.</span><span class="sxs-lookup"><span data-stu-id="58d02-123">Creates a set of policies and policy settings that apply to public safety officers in your organization.</span></span> |
|<span data-ttu-id="58d02-124">Gerente da primeira mão</span><span class="sxs-lookup"><span data-stu-id="58d02-124">Firstline manager</span></span>  |<span data-ttu-id="58d02-125">Gerentes de primeira mão em sua organização governamental</span><span class="sxs-lookup"><span data-stu-id="58d02-125">Firstline Managers in your government organization</span></span> |<span data-ttu-id="58d02-126">Cria um conjunto de políticas e aplica essas configurações aos gerentes de primeira empresa.</span><span class="sxs-lookup"><span data-stu-id="58d02-126">Creates a set of policies and applies those settings to Firstline Managers in your organization.</span></span>|
|<span data-ttu-id="58d02-127">Trabalho da primeira</span><span class="sxs-lookup"><span data-stu-id="58d02-127">Firstline worker</span></span>  |<span data-ttu-id="58d02-128">Trabalhadores de primeira mão em sua organização governamental</span><span class="sxs-lookup"><span data-stu-id="58d02-128">Firstline Workers in your government organization</span></span> |<span data-ttu-id="58d02-129">Cria um conjunto de políticas e aplica essas configurações aos trabalhos iniciais em sua organização.</span><span class="sxs-lookup"><span data-stu-id="58d02-129">Creates a set of policies and applies those settings to Firstline Workers in your organization.</span></span>|

![Captura de tela dos pacotes de política da assistência médica](media/policy-packages-gov.png)

<span data-ttu-id="58d02-131">Cada política individual recebe o nome do pacote de política para que você possa facilmente identificar as políticas que estão vinculadas a um pacote de política.</span><span class="sxs-lookup"><span data-stu-id="58d02-131">Each individual policy is given the name of the policy package so you can easily identify the policies that are linked to a policy package.</span></span> <span data-ttu-id="58d02-132">Por exemplo, quando você atribui o pacote de política do diretor de segurança pública aos usuários em sua organização, uma política chamada PublicSafety_Officer é criada para cada política no pacote.</span><span class="sxs-lookup"><span data-stu-id="58d02-132">For example, when you assign the Public safety officer policy package to users in your organization, a policy named PublicSafety_Officer is created for each policy in the package.</span></span>

![Captura de tela de políticas no pacote de trabalho clínico da assistência médica](media/policy-packages-public-safety-officer.png)

## <a name="manage-policy-packages"></a><span data-ttu-id="58d02-134">Gerenciar pacotes de política</span><span class="sxs-lookup"><span data-stu-id="58d02-134">Manage policy packages</span></span>

### <a name="view"></a><span data-ttu-id="58d02-135">View</span><span class="sxs-lookup"><span data-stu-id="58d02-135">View</span></span>

<span data-ttu-id="58d02-136">Exiba as configurações de cada política em um pacote de política antes de atribuir um pacote.</span><span class="sxs-lookup"><span data-stu-id="58d02-136">View the settings of each policy in a policy package before you assign a package.</span></span> <span data-ttu-id="58d02-137">Na navegação à esquerda do centro de administração do Microsoft Teams, selecione **pacotes de política** , selecione o nome do pacote e, em seguida, selecione o nome da política.</span><span class="sxs-lookup"><span data-stu-id="58d02-137">In the left navigation of the Microsoft Teams admin center, select **Policy packages** , select the package name, and then select the policy name.</span></span>

<span data-ttu-id="58d02-138">Decida se os valores predefinidos são adequados para sua organização ou se você precisa personalizá-los para serem mais restritivos ou lenient com base nas necessidades da sua organização.</span><span class="sxs-lookup"><span data-stu-id="58d02-138">Decide whether the predefined values are appropriate for your organization or whether you need to customize them to be more restrictive or lenient based on your organization's needs.</span></span>

### <a name="customize"></a><span data-ttu-id="58d02-139">Personalizar</span><span class="sxs-lookup"><span data-stu-id="58d02-139">Customize</span></span>

<span data-ttu-id="58d02-140">Personalize as configurações das políticas no pacote de política, conforme necessário, para atender às necessidades da sua organização.</span><span class="sxs-lookup"><span data-stu-id="58d02-140">Customize the settings of policies in the policy package, as needed, to fit the needs of your organization.</span></span> <span data-ttu-id="58d02-141">Todas as alterações feitas nas configurações de política são automaticamente aplicadas a usuários atribuídos ao pacote.</span><span class="sxs-lookup"><span data-stu-id="58d02-141">Any changes you make to policy settings are automatically applied to users who are assigned the package.</span></span> <span data-ttu-id="58d02-142">Para editar as configurações de uma política em um pacote de política, no centro de administração do Microsoft Teams, selecione o pacote de política, selecione o nome da política que você deseja editar e, em seguida, selecione **Editar**.</span><span class="sxs-lookup"><span data-stu-id="58d02-142">To edit the settings of a policy in a policy package, in the Microsoft Teams admin center, select the policy package, select the name of the policy you want to edit, and then select **Edit**.</span></span>

<span data-ttu-id="58d02-143">Lembre-se de que você também pode alterar as configurações de políticas em um pacote após atribuir o pacote de política.</span><span class="sxs-lookup"><span data-stu-id="58d02-143">Keep in mind that you can also change the settings of policies in a package after you assign the policy package.</span></span> <span data-ttu-id="58d02-144">Para saber mais, consulte [Personalizar políticas em um pacote de política](manage-policy-packages.md#customize-policies-in-a-policy-package).</span><span class="sxs-lookup"><span data-stu-id="58d02-144">To learn more, see [Customize policies in a policy package](manage-policy-packages.md#customize-policies-in-a-policy-package).</span></span> 

### <a name="assign"></a><span data-ttu-id="58d02-145">Atribuição</span><span class="sxs-lookup"><span data-stu-id="58d02-145">Assign</span></span>

<span data-ttu-id="58d02-146">Atribua o pacote de política aos usuários.</span><span class="sxs-lookup"><span data-stu-id="58d02-146">Assign the policy package to users.</span></span> <span data-ttu-id="58d02-147">Se um usuário tiver uma política atribuída e depois você atribuir uma política diferente, a atribuição mais recente terá prioridade.</span><span class="sxs-lookup"><span data-stu-id="58d02-147">If a user has a policy assigned, and then later you assign a different policy, the most recent assignment will take priority.</span></span>

#### <a name="assign-a-policy-package-to-one-or-several-users"></a><span data-ttu-id="58d02-148">Atribuir um pacote de política a um ou vários usuários</span><span class="sxs-lookup"><span data-stu-id="58d02-148">Assign a policy package to one or several users</span></span>

<span data-ttu-id="58d02-149">Para atribuir um pacote de política a um ou vários usuários, no painel de navegação esquerdo do centro de administração do Microsoft Teams, vá para **pacotes de política** e selecione **gerenciar usuários**.</span><span class="sxs-lookup"><span data-stu-id="58d02-149">To assign a policy package to one or multiple users, in the left navigation of the Microsoft Teams admin center, go to **Policy packages** , and then select **Manage users**.</span></span>  

![Captura de tela de como atribuir um pacote de política no centro de administração](media/policy-packages-healthcare-assign.png)

<span data-ttu-id="58d02-151">Para saber mais, consulte [atribuir um pacote de política](manage-policy-packages.md#assign-a-policy-package).</span><span class="sxs-lookup"><span data-stu-id="58d02-151">To learn more, see [Assign a policy package](manage-policy-packages.md#assign-a-policy-package).</span></span>

<span data-ttu-id="58d02-152">Se um usuário tiver uma política atribuída e depois você atribuir uma política diferente, a atribuição mais recente terá prioridade.</span><span class="sxs-lookup"><span data-stu-id="58d02-152">If a user has a policy assigned, and then later you assign a different policy, the most recent assignment will take priority.</span></span>

#### <a name="assign-a-policy-package-to-a-group"></a><span data-ttu-id="58d02-153">Atribuir um pacote de política a um grupo</span><span class="sxs-lookup"><span data-stu-id="58d02-153">Assign a policy package to a group</span></span>

<span data-ttu-id="58d02-154">**Este recurso está em visualização particular**</span><span class="sxs-lookup"><span data-stu-id="58d02-154">**This feature is in private preview**</span></span>

<span data-ttu-id="58d02-155">A atribuição de pacote de política para grupos permite que você atribua várias políticas a um grupo de usuários, como um grupo de segurança ou lista de distribuição.</span><span class="sxs-lookup"><span data-stu-id="58d02-155">Policy package assignment to groups let you assign multiple policies to a group of users, such as a security group or distribution list.</span></span> <span data-ttu-id="58d02-156">A atribuição de política é propagada para os membros do grupo de acordo com as regras de precedência.</span><span class="sxs-lookup"><span data-stu-id="58d02-156">The policy assignment is propagated to members of the group according to precedence rules.</span></span> <span data-ttu-id="58d02-157">Conforme os membros são adicionados ou removidos de um grupo, suas atribuições de política herdadas são atualizadas de acordo.</span><span class="sxs-lookup"><span data-stu-id="58d02-157">As members are added to or removed from a group, their inherited policy assignments are updated accordingly.</span></span> <span data-ttu-id="58d02-158">Esse método é recomendado para grupos de até 50.000 usuários, mas também funcionará com grupos maiores.</span><span class="sxs-lookup"><span data-stu-id="58d02-158">This method is recommended for groups of up to 50,000 users but will also work with larger groups.</span></span>

<span data-ttu-id="58d02-159">Para saber mais, consulte [atribuir um pacote de política a um grupo](assign-policies.md#assign-a-policy-package-to-a-group).</span><span class="sxs-lookup"><span data-stu-id="58d02-159">To learn more, see [Assign a policy package to a group](assign-policies.md#assign-a-policy-package-to-a-group).</span></span>

#### <a name="assign-a-policy-package-to-a-large-set-batch-of-users"></a><span data-ttu-id="58d02-160">Atribuir um pacote de política a um grande conjunto (lote) de usuários</span><span class="sxs-lookup"><span data-stu-id="58d02-160">Assign a policy package to a large set (batch) of users</span></span>

<span data-ttu-id="58d02-161">Use a atribuição de pacote de política em lotes para atribuir um pacote de política a grandes conjuntos de usuários por vez.</span><span class="sxs-lookup"><span data-stu-id="58d02-161">Use batch policy package assignment to assign a policy package to large sets of users at a time.</span></span> <span data-ttu-id="58d02-162">Use o cmdlet [New-CsBatchPolicyPackageAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicypackageassignmentoperation) para enviar um lote de usuários e o pacote de política que você deseja atribuir.</span><span class="sxs-lookup"><span data-stu-id="58d02-162">You use the [New-CsBatchPolicyPackageAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicypackageassignmentoperation) cmdlet to submit a batch of users and the policy package that you want to assign.</span></span> <span data-ttu-id="58d02-163">As atribuições são processadas como uma operação em segundo plano e uma ID de operação é gerada para cada lote.</span><span class="sxs-lookup"><span data-stu-id="58d02-163">The assignments are processed as a background operation and an operation ID is generated for each batch.</span></span>

<span data-ttu-id="58d02-164">Um lote pode conter até 5.000 usuários.</span><span class="sxs-lookup"><span data-stu-id="58d02-164">A batch can contain up to 5,000 users.</span></span> <span data-ttu-id="58d02-165">Você pode especificar os usuários por sua ID de objeto, UPN, endereço SIP ou endereço de email.</span><span class="sxs-lookup"><span data-stu-id="58d02-165">You can specify users by their object Id, UPN, SIP address, or email address.</span></span> <span data-ttu-id="58d02-166">Para saber mais, consulte [atribuir um pacote de política a um lote de usuários](assign-policies.md#assign-a-policy-package-to-a-batch-of-users).</span><span class="sxs-lookup"><span data-stu-id="58d02-166">To learn more, see [Assign a policy package to a batch of users](assign-policies.md#assign-a-policy-package-to-a-batch-of-users).</span></span>

## <a name="related-topics"></a><span data-ttu-id="58d02-167">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="58d02-167">Related topics</span></span>

[<span data-ttu-id="58d02-168">Gerenciar pacotes de política em equipes</span><span class="sxs-lookup"><span data-stu-id="58d02-168">Manage policy packages in Teams</span></span>](manage-policy-packages.md)

[<span data-ttu-id="58d02-169">Atribuir políticas a seus usuários no Teams</span><span class="sxs-lookup"><span data-stu-id="58d02-169">Assign policies to your users in Teams</span></span>](assign-policies.md) 
