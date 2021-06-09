---
title: Teams de política para o governo
author: cichur
ms.author: v-cichur
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
description: Saiba como usar e gerenciar pacotes de Teams de política para sua organização governamental.
ms.openlocfilehash: 41ae937323b37948c03128efd565f40c02bbd6a2
ms.sourcegitcommit: 8ad05b37c0b714adb069bc2503e88366ab75c57d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/07/2021
ms.locfileid: "52796865"
---
# <a name="teams-policy-packages-for-government"></a><span data-ttu-id="47e68-103">Teams de política para o governo</span><span class="sxs-lookup"><span data-stu-id="47e68-103">Teams policy packages for government</span></span>

> [!NOTE]
> <span data-ttu-id="47e68-104">No momento, os pacotes de política não estão disponíveis Microsoft 365 implantações GCC Alta ou DoD.</span><span class="sxs-lookup"><span data-stu-id="47e68-104">Policy packages are currently not available in Microsoft 365 Government GCC High or DoD deployments.</span></span>

## <a name="overview"></a><span data-ttu-id="47e68-105">Visão Geral</span><span class="sxs-lookup"><span data-stu-id="47e68-105">Overview</span></span>

<span data-ttu-id="47e68-106">Um [pacote de política](manage-policy-packages.md) no Microsoft Teams é um conjunto de políticas e configurações de política predefinidas que você pode atribuir a usuários com funções semelhantes em sua organização.</span><span class="sxs-lookup"><span data-stu-id="47e68-106">A [policy package](manage-policy-packages.md) in Microsoft Teams is a collection of predefined policies and policy settings that you can assign to users who have similar roles in your organization.</span></span> <span data-ttu-id="47e68-107">Os pacotes de políticas simplificam, otimizam e ajudam a fornecer consistência ao gerenciar políticas.</span><span class="sxs-lookup"><span data-stu-id="47e68-107">Policy packages simplify, streamline, and help provide consistency when managing policies.</span></span> <span data-ttu-id="47e68-108">Você pode personalizar as configurações das políticas no pacote para atender às necessidades dos usuários.</span><span class="sxs-lookup"><span data-stu-id="47e68-108">You can customize the settings of the policies in the package to suit the needs of your users.</span></span> <span data-ttu-id="47e68-109">Quando você altera as configurações de políticas em um pacote de política, todos os usuários atribuídos a esse pacote têm as configurações atualizadas.</span><span class="sxs-lookup"><span data-stu-id="47e68-109">When you change the settings of policies in a policy package, all users who are assigned to that package get the updated settings.</span></span> <span data-ttu-id="47e68-110">Você pode gerenciar pacotes de política usando o Centro de Administração do Microsoft Teams ou o Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="47e68-110">You can manage policy packages by using the Microsoft Teams admin center or PowerShell.</span></span>

<span data-ttu-id="47e68-111">Pacotes de política pré-definem políticas para o seguinte, dependendo do pacote:</span><span class="sxs-lookup"><span data-stu-id="47e68-111">Policy packages pre-define policies for the following, depending on the package:</span></span>

- <span data-ttu-id="47e68-112">Mensagens</span><span class="sxs-lookup"><span data-stu-id="47e68-112">Messaging</span></span>
- <span data-ttu-id="47e68-113">Reuniões</span><span class="sxs-lookup"><span data-stu-id="47e68-113">Meetings</span></span>
- <span data-ttu-id="47e68-114">Chamadas</span><span class="sxs-lookup"><span data-stu-id="47e68-114">Calling</span></span>
- <span data-ttu-id="47e68-115">Configuração do aplicativo</span><span class="sxs-lookup"><span data-stu-id="47e68-115">App setup</span></span>
- <span data-ttu-id="47e68-116">Eventos ao vivo</span><span class="sxs-lookup"><span data-stu-id="47e68-116">Live events</span></span>

<span data-ttu-id="47e68-117">Teams atualmente inclui os seguintes pacotes de política para o governo.</span><span class="sxs-lookup"><span data-stu-id="47e68-117">Teams currently includes the following policy packages for government.</span></span>

|<span data-ttu-id="47e68-118">Nome do pacote listado no Centro de Administração do Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="47e68-118">Package name in the Microsoft Teams admin center</span></span>|<span data-ttu-id="47e68-119">Melhor usado para</span><span class="sxs-lookup"><span data-stu-id="47e68-119">Best used for</span></span>|<span data-ttu-id="47e68-120">Descrição</span><span class="sxs-lookup"><span data-stu-id="47e68-120">Description</span></span> |
|---------|---------|---------|
|<span data-ttu-id="47e68-121">Oficial de segurança pública</span><span class="sxs-lookup"><span data-stu-id="47e68-121">Public safety officer</span></span>  |<span data-ttu-id="47e68-122">Agentes de segurança pública em sua organização governamental</span><span class="sxs-lookup"><span data-stu-id="47e68-122">Public safety officers in your government organization</span></span>  |<span data-ttu-id="47e68-123">Cria um conjunto de políticas e configurações de política que se aplicam aos agentes de segurança pública em sua organização.</span><span class="sxs-lookup"><span data-stu-id="47e68-123">Creates a set of policies and policy settings that apply to public safety officers in your organization.</span></span> |
|<span data-ttu-id="47e68-124">Gerenciador de frontline</span><span class="sxs-lookup"><span data-stu-id="47e68-124">Frontline manager</span></span>  |<span data-ttu-id="47e68-125">Gerentes de linha de frente em sua organização governamental</span><span class="sxs-lookup"><span data-stu-id="47e68-125">Frontline Managers in your government organization</span></span> |<span data-ttu-id="47e68-126">Cria um conjunto de políticas e aplica essas configurações aos Gerentes de Linha de Frente em sua organização.</span><span class="sxs-lookup"><span data-stu-id="47e68-126">Creates a set of policies and applies those settings to Frontline Managers in your organization.</span></span>|
|<span data-ttu-id="47e68-127">Trabalhador de linha de frente</span><span class="sxs-lookup"><span data-stu-id="47e68-127">Frontline worker</span></span>  |<span data-ttu-id="47e68-128">Trabalhadores de linha de frente em sua organização governamental</span><span class="sxs-lookup"><span data-stu-id="47e68-128">Frontline Workers in your government organization</span></span> |<span data-ttu-id="47e68-129">Cria um conjunto de políticas e aplica essas configurações aos Trabalhadores de Linha de Frente em sua organização.</span><span class="sxs-lookup"><span data-stu-id="47e68-129">Creates a set of policies and applies those settings to Frontline Workers in your organization.</span></span>|

![Captura de tela dos pacotes de política de saúde](media/policy-packages-gov.png)

<span data-ttu-id="47e68-131">Cada política individual recebe o nome do pacote de políticas, para que você possa identificar facilmente políticas vinculadas a um pacote de políticas.</span><span class="sxs-lookup"><span data-stu-id="47e68-131">Each individual policy is given the name of the policy package so you can easily identify the policies that are linked to a policy package.</span></span> <span data-ttu-id="47e68-132">Por exemplo, quando você atribui o pacote de política de agente de segurança pública aos usuários em sua organização, uma política chamada PublicSafety_Officer é criada para cada política no pacote.</span><span class="sxs-lookup"><span data-stu-id="47e68-132">For example, when you assign the Public safety officer policy package to users in your organization, a policy named PublicSafety_Officer is created for each policy in the package.</span></span>

![Captura de tela das políticas no pacote de funcionários clínicos da área de saúde](media/policy-packages-public-safety-officer.png)

## <a name="manage-policy-packages"></a><span data-ttu-id="47e68-134">Gerenciar pacotes de política</span><span class="sxs-lookup"><span data-stu-id="47e68-134">Manage policy packages</span></span>

### <a name="view"></a><span data-ttu-id="47e68-135">Exibir</span><span class="sxs-lookup"><span data-stu-id="47e68-135">View</span></span>

<span data-ttu-id="47e68-136">Exibir as configurações de cada política em um pacote de política antes de atribuir um pacote.</span><span class="sxs-lookup"><span data-stu-id="47e68-136">View the settings of each policy in a policy package before you assign a package.</span></span> <span data-ttu-id="47e68-137">Na barra de navegação à esquerda do centro de administração do Microsoft Teams, selecione **Pacotes de Política**, selecione o nome do pacote e, em seguida, selecione o nome da política.</span><span class="sxs-lookup"><span data-stu-id="47e68-137">In the left navigation of the Microsoft Teams admin center, select **Policy packages**, select the package name, and then select the policy name.</span></span>

<span data-ttu-id="47e68-138">Decida se os valores predefinidos são apropriados para a sua organização ou se você precisa personalizá-los para serem mais restritivos ou leniente com base nas necessidades da sua organização.</span><span class="sxs-lookup"><span data-stu-id="47e68-138">Decide whether the predefined values are appropriate for your organization or whether you need to customize them to be more restrictive or lenient based on your organization's needs.</span></span>

### <a name="customize"></a><span data-ttu-id="47e68-139">Personalizar</span><span class="sxs-lookup"><span data-stu-id="47e68-139">Customize</span></span>

<span data-ttu-id="47e68-140">Personalize as configurações das políticas no pacote de política, conforme necessário, para atender às necessidades da sua organização.</span><span class="sxs-lookup"><span data-stu-id="47e68-140">Customize the settings of policies in the policy package, as needed, to fit the needs of your organization.</span></span> <span data-ttu-id="47e68-141">As alterações que você fizer nas configurações da política serão automaticamente aplicadas aos usuários que recebem o pacote.</span><span class="sxs-lookup"><span data-stu-id="47e68-141">Any changes you make to policy settings are automatically applied to users who are assigned the package.</span></span> <span data-ttu-id="47e68-142">Para editar as configurações de uma política em um pacote de política, no centro de administração do Microsoft Teams, selecione o pacote de política, selecione o nome da política que você deseja editar e, em seguida, selecione **Editar**.</span><span class="sxs-lookup"><span data-stu-id="47e68-142">To edit the settings of a policy in a policy package, in the Microsoft Teams admin center, select the policy package, select the name of the policy you want to edit, and then select **Edit**.</span></span>

<span data-ttu-id="47e68-143">Lembre-se de que você também pode alterar as configurações das políticas em um pacote após atribuir o pacote de política.</span><span class="sxs-lookup"><span data-stu-id="47e68-143">Keep in mind that you can also change the settings of policies in a package after you assign the policy package.</span></span> <span data-ttu-id="47e68-144">Para saber mais, confira [Personalizar políticas em um pacote de política](manage-policy-packages.md#customize-policies-in-a-policy-package).</span><span class="sxs-lookup"><span data-stu-id="47e68-144">To learn more, see [Customize policies in a policy package](manage-policy-packages.md#customize-policies-in-a-policy-package).</span></span> 

### <a name="assign"></a><span data-ttu-id="47e68-145">Atribuir</span><span class="sxs-lookup"><span data-stu-id="47e68-145">Assign</span></span>

<span data-ttu-id="47e68-p106">Atribua o pacote de política aos usuários. Se um usuário tiver uma política atribuída e, mais tarde, você atribuir uma política diferente, a atribuição mais recente terá prioridade.</span><span class="sxs-lookup"><span data-stu-id="47e68-p106">Assign the policy package to users. If a user has a policy assigned, and then later you assign a different policy, the most recent assignment will take priority.</span></span>

> [!NOTE]
> <span data-ttu-id="47e68-148">Cada usuário exigirá o complemento Comunicações Avançadas para receber uma atribuição de pacote de política personalizada.</span><span class="sxs-lookup"><span data-stu-id="47e68-148">Each user will require the Advanced Communications add-on in order to receive a custom policy package assignment.</span></span> <span data-ttu-id="47e68-149">Para obter mais informações, consulte [Advanced Communications add-on for Microsoft Teams](/microsoftteams/teams-add-on-licensing/advanced-communications).</span><span class="sxs-lookup"><span data-stu-id="47e68-149">For more information, see [Advanced Communications add-on for Microsoft Teams](/microsoftteams/teams-add-on-licensing/advanced-communications).</span></span>

#### <a name="assign-a-policy-package-to-one-or-several-users"></a><span data-ttu-id="47e68-150">Atribuir um pacote de política a um ou vários usuários</span><span class="sxs-lookup"><span data-stu-id="47e68-150">Assign a policy package to one or several users</span></span>

<span data-ttu-id="47e68-151">Para atribuir um pacote de política a um ou vários usuários, na barra de navegação à esquerda do centro de administração do Microsoft Teams, vá para **Pacotes de política** e, em seguida, selecione **Gerenciar usuários**.</span><span class="sxs-lookup"><span data-stu-id="47e68-151">To assign a policy package to one or multiple users, in the left navigation of the Microsoft Teams admin center, go to **Policy packages**, and then select **Manage users**.</span></span>  

![Captura de tela de como atribuir um pacote de política no centro de administração](media/policy-packages-healthcare-assign.png)

<span data-ttu-id="47e68-153">Para saber mais, confira [Atribuir um pacote de política](manage-policy-packages.md#assign-a-policy-package).</span><span class="sxs-lookup"><span data-stu-id="47e68-153">To learn more, see [Assign a policy package](manage-policy-packages.md#assign-a-policy-package).</span></span>

<span data-ttu-id="47e68-154">Se um usuário tiver uma política atribuída e, em seguida, você atribuir uma política diferente, a atribuição mais recente terá prioridade.</span><span class="sxs-lookup"><span data-stu-id="47e68-154">If a user has a policy assigned, and then later you assign a different policy, the most recent assignment will take priority.</span></span>

#### <a name="assign-a-policy-package-to-a-group"></a><span data-ttu-id="47e68-155">Atribua o pacote de política a um grupo.</span><span class="sxs-lookup"><span data-stu-id="47e68-155">Assign a policy package to a group</span></span>

<span data-ttu-id="47e68-156">**Este recurso está na visualização particular**</span><span class="sxs-lookup"><span data-stu-id="47e68-156">**This feature is in private preview**</span></span>

<span data-ttu-id="47e68-157">As atribuições de pacote de política aos grupos permitem atribuir várias políticas a um grupo de usuários, como uma lista de distribuição ou grupo de segurança.</span><span class="sxs-lookup"><span data-stu-id="47e68-157">Policy package assignment to groups let you assign multiple policies to a group of users, such as a security group or distribution list.</span></span> <span data-ttu-id="47e68-158">As atribuições de política serão propagadas para os membros do grupo, de acordo com as regras de precedência.</span><span class="sxs-lookup"><span data-stu-id="47e68-158">The policy assignment is propagated to members of the group according to precedence rules.</span></span> <span data-ttu-id="47e68-159">À medida que os membros forem adicionados ou removidos de um grupo, as atribuições de política herdadas serão atualizadas.</span><span class="sxs-lookup"><span data-stu-id="47e68-159">As members are added to or removed from a group, their inherited policy assignments are updated accordingly.</span></span> <span data-ttu-id="47e68-160">Esse método é recomendado para grupos de até 50.000 usuários, mas também funcionará com grupos maiores.</span><span class="sxs-lookup"><span data-stu-id="47e68-160">This method is recommended for groups of up to 50,000 users but will also work with larger groups.</span></span>

<span data-ttu-id="47e68-161">Para saber mais, confira [Atribuir um pacote de política a um grupo](assign-policies.md#assign-a-policy-package-to-a-group).</span><span class="sxs-lookup"><span data-stu-id="47e68-161">To learn more, see [Assign a policy package to a group](assign-policies.md#assign-a-policy-package-to-a-group).</span></span>

#### <a name="assign-a-policy-package-to-a-large-set-batch-of-users"></a><span data-ttu-id="47e68-162">Atribuir um pacote de política a um conjunto grande (lote) de usuários</span><span class="sxs-lookup"><span data-stu-id="47e68-162">Assign a policy package to a large set (batch) of users</span></span>

<span data-ttu-id="47e68-163">Use a tarefa de pacote de política de lote para atribuir um pacote de política a grandes conjuntos de usuários por vez.</span><span class="sxs-lookup"><span data-stu-id="47e68-163">Use batch policy package assignment to assign a policy package to large sets of users at a time.</span></span> <span data-ttu-id="47e68-164">Use o cmdlet [New-CsBatchPolicyPackageAssignmentOperation](/powershell/module/teams/new-csbatchpolicypackageassignmentoperation) para enviar um lote de usuários e o pacote de política que você deseja atribuir.</span><span class="sxs-lookup"><span data-stu-id="47e68-164">You use the [New-CsBatchPolicyPackageAssignmentOperation](/powershell/module/teams/new-csbatchpolicypackageassignmentoperation) cmdlet to submit a batch of users and the policy package that you want to assign.</span></span> <span data-ttu-id="47e68-165">As atribuições são processadas como uma operação de plano de fundo e uma ID de operação é gerada para cada lote.</span><span class="sxs-lookup"><span data-stu-id="47e68-165">The assignments are processed as a background operation and an operation ID is generated for each batch.</span></span>

<span data-ttu-id="47e68-166">Um lote pode conter até 5.000 usuários.</span><span class="sxs-lookup"><span data-stu-id="47e68-166">A batch can contain up to 5,000 users.</span></span> <span data-ttu-id="47e68-167">Você pode especificar os usuários por ID do objeto, UPN, endereço SIP ou endereço de email.</span><span class="sxs-lookup"><span data-stu-id="47e68-167">You can specify users by their object Id, UPN, SIP address, or email address.</span></span> <span data-ttu-id="47e68-168">Para saber mais, confira [Atribuir um pacote de política a um lote de usuários](assign-policies.md#assign-a-policy-package-to-a-batch-of-users).</span><span class="sxs-lookup"><span data-stu-id="47e68-168">To learn more, see [Assign a policy package to a batch of users](assign-policies.md#assign-a-policy-package-to-a-batch-of-users).</span></span>

## <a name="related-topics"></a><span data-ttu-id="47e68-169">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="47e68-169">Related topics</span></span>

[<span data-ttu-id="47e68-170">Gerenciar pacotes de política em equipes</span><span class="sxs-lookup"><span data-stu-id="47e68-170">Manage policy packages in Teams</span></span>](manage-policy-packages.md)

[<span data-ttu-id="47e68-171">Atribuir pacotes de política a usuários e grupos</span><span class="sxs-lookup"><span data-stu-id="47e68-171">Assign policy packages to users and groups</span></span>](assign-policy-packages.md)
