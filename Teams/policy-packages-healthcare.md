---
title: Pacotes de política de equipe para assistência médica
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
- microsoftcloud-healthcare
appliesto:
- Microsoft Teams
f1.keywords: ''
ms.custom: ''
localization_priority: Normal
search.appverid: MET150
searchScope:
- Microsoft Teams
- Microsoft Cloud for Healthcare
description: Saiba como usar e gerenciar pacotes de política de equipe para sua organização de assistência médica.
ms.openlocfilehash: b8317a7f860d0ab8510a6170b69a50f7a3387ebd
ms.sourcegitcommit: ee217e1d7188842c7becd19387fd421b485c3575
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/04/2020
ms.locfileid: "48908510"
---
# <a name="teams-policy-packages-for-healthcare"></a><span data-ttu-id="d0f2a-103">Pacotes de política de equipe para assistência médica</span><span class="sxs-lookup"><span data-stu-id="d0f2a-103">Teams policy packages for healthcare</span></span>

## <a name="overview"></a><span data-ttu-id="d0f2a-104">Visão geral</span><span class="sxs-lookup"><span data-stu-id="d0f2a-104">Overview</span></span>

<span data-ttu-id="d0f2a-105">Um [pacote de política](manage-policy-packages.md) no Microsoft Teams é uma coleção de políticas predefinidas e configurações de política que você pode atribuir aos usuários que têm funções semelhantes em sua organização.</span><span class="sxs-lookup"><span data-stu-id="d0f2a-105">A [policy package](manage-policy-packages.md) in Microsoft Teams is a collection of predefined policies and policy settings that you can assign to users who have similar roles in your organization.</span></span> <span data-ttu-id="d0f2a-106">Os pacotes de políticas simplificam, otimizam e ajudam a fornecer consistência ao gerenciar políticas.</span><span class="sxs-lookup"><span data-stu-id="d0f2a-106">Policy packages simplify, streamline, and help provide consistency when managing policies.</span></span> <span data-ttu-id="d0f2a-107">Você pode personalizar as configurações das políticas do pacote para atender às necessidades dos seus usuários.</span><span class="sxs-lookup"><span data-stu-id="d0f2a-107">You can customize the settings of the policies in the package to suit the needs of your users.</span></span> <span data-ttu-id="d0f2a-108">Quando você altera as configurações de políticas em um pacote de política, todos os usuários atribuídos a esse pacote obtêm as configurações atualizadas.</span><span class="sxs-lookup"><span data-stu-id="d0f2a-108">When you change the settings of policies in a policy package, all users who are assigned to that package get the updated settings.</span></span> <span data-ttu-id="d0f2a-109">Você pode gerenciar pacotes de política usando o centro de administração do Microsoft Teams ou o PowerShell.</span><span class="sxs-lookup"><span data-stu-id="d0f2a-109">You can manage policy packages by using the Microsoft Teams admin center or PowerShell.</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4Ht2o]

<span data-ttu-id="d0f2a-110">Pacotes de política pré-defina políticas para o seguinte, dependendo do pacote:</span><span class="sxs-lookup"><span data-stu-id="d0f2a-110">Policy packages pre-define policies for the following, depending on the package:</span></span>

- <span data-ttu-id="d0f2a-111">Mensagens</span><span class="sxs-lookup"><span data-stu-id="d0f2a-111">Messaging</span></span>
- <span data-ttu-id="d0f2a-112">Reuniões</span><span class="sxs-lookup"><span data-stu-id="d0f2a-112">Meetings</span></span>
- <span data-ttu-id="d0f2a-113">Chamadas</span><span class="sxs-lookup"><span data-stu-id="d0f2a-113">Calling</span></span>
- <span data-ttu-id="d0f2a-114">Configuração do aplicativo</span><span class="sxs-lookup"><span data-stu-id="d0f2a-114">App setup</span></span>
- <span data-ttu-id="d0f2a-115">Eventos ao vivo</span><span class="sxs-lookup"><span data-stu-id="d0f2a-115">Live events</span></span>

<span data-ttu-id="d0f2a-116">Atualmente, o Microsoft Teams inclui os seguintes pacotes de política de assistência médica.</span><span class="sxs-lookup"><span data-stu-id="d0f2a-116">Teams currently includes the following healthcare policy packages.</span></span>

|<span data-ttu-id="d0f2a-117">Nome do pacote no centro de administração do Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="d0f2a-117">Package name in the Microsoft Teams admin center</span></span>|<span data-ttu-id="d0f2a-118">Melhor usado para</span><span class="sxs-lookup"><span data-stu-id="d0f2a-118">Best used for</span></span>|<span data-ttu-id="d0f2a-119">Descrição</span><span class="sxs-lookup"><span data-stu-id="d0f2a-119">Description</span></span> |
|---------|---------|---------|
|<span data-ttu-id="d0f2a-120">Trabalhador clínico da assistência médica</span><span class="sxs-lookup"><span data-stu-id="d0f2a-120">Healthcare clinical worker</span></span>  |<span data-ttu-id="d0f2a-121">Trabalhadores clínicos na sua organização de assistência médica</span><span class="sxs-lookup"><span data-stu-id="d0f2a-121">Clinical workers in your healthcare organization</span></span>  |<span data-ttu-id="d0f2a-122">Cria um conjunto de políticas e configurações de política que dão a funcionários clínicos, como as mensagens de mão registradas, recarga de mão, médicos e funcionários sociais acesso total a chats, chamadas, gerenciamento de turnos e reuniões.</span><span class="sxs-lookup"><span data-stu-id="d0f2a-122">Creates a set of policies and policy settings that give clinical workers such as registered nurses, charge nurses, physicians, and social workers full access to chat, calling, shift management, and meetings.</span></span> |
|<span data-ttu-id="d0f2a-123">Operador de informações da assistência médica</span><span class="sxs-lookup"><span data-stu-id="d0f2a-123">Healthcare information worker</span></span>  |<span data-ttu-id="d0f2a-124">Operadores de informações em sua organização de assistência médica</span><span class="sxs-lookup"><span data-stu-id="d0f2a-124">Information workers in your healthcare organization</span></span> |<span data-ttu-id="d0f2a-125">Cria um conjunto de políticas e configurações de política que fornecem aos operadores de informações, como pessoal de ti, pessoal de informática, pessoal de finanças e órgãos de conformidade, acesso total a chats, chamadas e reuniões.</span><span class="sxs-lookup"><span data-stu-id="d0f2a-125">Creates a set of policies and policy settings that give information workers such as IT personnel, informatics staff, finance personnel, and compliance officers, full access to chat, calling, and meetings.</span></span>|
|<span data-ttu-id="d0f2a-126">Sala de pacientes de assistência médica</span><span class="sxs-lookup"><span data-stu-id="d0f2a-126">Healthcare patient room</span></span>  |<span data-ttu-id="d0f2a-127">Dispositivos da sala de pacientes</span><span class="sxs-lookup"><span data-stu-id="d0f2a-127">Patient room devices</span></span>|<span data-ttu-id="d0f2a-128">Cria um conjunto de políticas e configurações de política que se aplicam a salas de pacientes em sua organização de assistência médica.</span><span class="sxs-lookup"><span data-stu-id="d0f2a-128">Creates a set of policies and policy settings that apply to patient rooms in your healthcare organization.</span></span>|

![Captura de tela dos pacotes de política da assistência médica](media/policy-packages-healthcare.png)

<span data-ttu-id="d0f2a-130">Cada política individual recebe o nome do pacote de política para que você possa facilmente identificar as políticas que estão vinculadas a um pacote de política.</span><span class="sxs-lookup"><span data-stu-id="d0f2a-130">Each individual policy is given the name of the policy package so you can easily identify the policies that are linked to a policy package.</span></span> <span data-ttu-id="d0f2a-131">Por exemplo, quando você atribui o pacote de política do funcionário clínico à assistência médica a clínicos em sua organização, uma política chamada Healthcare_ClinicalWorker é criada para cada política do pacote.</span><span class="sxs-lookup"><span data-stu-id="d0f2a-131">For example, when you assign the Healthcare clinical worker policy package to clinicians in your organization, a policy named Healthcare_ClinicalWorker is created for each policy in the package.</span></span>

![Captura de tela de políticas no pacote de trabalho clínico da assistência médica](media/policy-packages-healthcare-clinical-worker.png)

## <a name="get-started-with-policy-packages"></a><span data-ttu-id="d0f2a-133">Introdução aos pacotes de política</span><span class="sxs-lookup"><span data-stu-id="d0f2a-133">Get started with policy packages</span></span>

<span data-ttu-id="d0f2a-134">Para começar a usar os pacotes de política da assistência médica, no Hub de integração do centro de administração do Microsoft, selecione **assistência médica** e escolha **atribuir configurações de política por função**.</span><span class="sxs-lookup"><span data-stu-id="d0f2a-134">To get you started with Healthcare policy packages, on the Microsoft Admin Center onboarding hub, select **Healthcare** , and then select **Assign policy settings by role**.</span></span> <span data-ttu-id="d0f2a-135">Quando estiver pronto para começar, decida de quais pacotes de política você gostaria de atribuir indivíduos à sua organização.</span><span class="sxs-lookup"><span data-stu-id="d0f2a-135">Once you’re ready to get started, decide which policy packages you'd like to assign individuals in your organization to.</span></span>

<span data-ttu-id="d0f2a-136">Selecione **Exibir detalhes da política** para saber mais sobre as políticas específicas em um pacote e suas respectivas configurações.</span><span class="sxs-lookup"><span data-stu-id="d0f2a-136">Select **View policy details** to learn more about the specific policies in a package and their respective settings.</span></span> <span data-ttu-id="d0f2a-137">Eles [podem ser personalizados](manage-policy-packages.md#customize-policies-in-a-policy-package) após a atribuição no centro de administração do teams.</span><span class="sxs-lookup"><span data-stu-id="d0f2a-137">These [can be customized](manage-policy-packages.md#customize-policies-in-a-policy-package) after assignment in the Teams Admin Center.</span></span>

<span data-ttu-id="d0f2a-138">Escolha um ou vários pacotes para atribuir e clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="d0f2a-138">Choose one or multiple packages to assign and then click **Next**.</span></span> <span data-ttu-id="d0f2a-139">Você pode procurar e adicionar pessoas ao pacote de políticas mais adequado para sua função.</span><span class="sxs-lookup"><span data-stu-id="d0f2a-139">You can search for and add people to the policy package best suited for their role.</span></span> <span data-ttu-id="d0f2a-140">Um indivíduo não pode ser atribuído a mais de um pacote de política ao mesmo tempo.</span><span class="sxs-lookup"><span data-stu-id="d0f2a-140">An individual can't be assigned to more than one policy package at one time.</span></span>

<span data-ttu-id="d0f2a-141">Depois de adicionar pessoas ao pacote de política correto, **concluir** finalizará suas seleções.</span><span class="sxs-lookup"><span data-stu-id="d0f2a-141">Once you’ve added people to the right policy package, **Finish** finalizes your selections.</span></span> <span data-ttu-id="d0f2a-142">Você pode continuar Personalizando e gerenciando pacotes de política no centro de administração do Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="d0f2a-142">You can continue to customize and manage policy packages in the Microsoft Teams admin center.</span></span>

## <a name="manage-policy-packages"></a><span data-ttu-id="d0f2a-143">Gerenciar pacotes de política</span><span class="sxs-lookup"><span data-stu-id="d0f2a-143">Manage policy packages</span></span>

### <a name="view"></a><span data-ttu-id="d0f2a-144">View</span><span class="sxs-lookup"><span data-stu-id="d0f2a-144">View</span></span>

<span data-ttu-id="d0f2a-145">Exiba as configurações de cada política em um pacote de política antes de atribuir um pacote.</span><span class="sxs-lookup"><span data-stu-id="d0f2a-145">View the settings of each policy in a policy package before you assign a package.</span></span> <span data-ttu-id="d0f2a-146">Na navegação à esquerda do centro de administração do Microsoft Teams, vá para **pacotes de política** , selecione o nome do pacote e, em seguida, selecione o nome da política.</span><span class="sxs-lookup"><span data-stu-id="d0f2a-146">In the left navigation of the Microsoft Teams admin center, go to **Policy packages** , select the package name, and then select the policy name.</span></span>

<span data-ttu-id="d0f2a-147">Decida se os valores predefinidos são adequados para sua organização ou se você precisa personalizá-los para serem mais restritivos ou lenient com base nas necessidades da sua organização.</span><span class="sxs-lookup"><span data-stu-id="d0f2a-147">Decide whether the predefined values are appropriate for your organization or whether you need to customize them to be more restrictive or lenient based on your organization's needs.</span></span>

### <a name="customize"></a><span data-ttu-id="d0f2a-148">Personalizar</span><span class="sxs-lookup"><span data-stu-id="d0f2a-148">Customize</span></span>

<span data-ttu-id="d0f2a-149">Personalize as configurações das políticas no pacote de política, conforme necessário, para atender às necessidades da sua organização.</span><span class="sxs-lookup"><span data-stu-id="d0f2a-149">Customize the settings of policies in the policy package, as needed, to fit the needs of your organization.</span></span> <span data-ttu-id="d0f2a-150">Todas as alterações feitas nas configurações de política são automaticamente aplicadas a usuários atribuídos ao pacote.</span><span class="sxs-lookup"><span data-stu-id="d0f2a-150">Any changes you make to policy settings are automatically applied to users who are assigned the package.</span></span> <span data-ttu-id="d0f2a-151">Para editar as configurações de uma política em um pacote de política, no painel de navegação esquerdo do centro de administração do Microsoft Teams, vá para **pacotes de política** , selecione o pacote de política, selecione o nome da política que você deseja editar e, em seguida, selecione **Editar**.</span><span class="sxs-lookup"><span data-stu-id="d0f2a-151">To edit the settings of a policy in a policy package, in the left navigation of the Microsoft Teams admin center, go to **Policy packages** , select the policy package, select the name of the policy you want to edit, and then select **Edit**.</span></span>

<span data-ttu-id="d0f2a-152">Lembre-se de que você também pode alterar as configurações de políticas em um pacote após atribuir o pacote de política.</span><span class="sxs-lookup"><span data-stu-id="d0f2a-152">Keep in mind that you can also change the settings of policies in a package after you assign the policy package.</span></span> <span data-ttu-id="d0f2a-153">Para saber mais, consulte [Personalizar políticas em um pacote de política](manage-policy-packages.md#customize-policies-in-a-policy-package).</span><span class="sxs-lookup"><span data-stu-id="d0f2a-153">To learn more, see [Customize policies in a policy package](manage-policy-packages.md#customize-policies-in-a-policy-package).</span></span>

### <a name="assign"></a><span data-ttu-id="d0f2a-154">Atribuição</span><span class="sxs-lookup"><span data-stu-id="d0f2a-154">Assign</span></span>

<span data-ttu-id="d0f2a-155">Atribua o pacote de política aos usuários.</span><span class="sxs-lookup"><span data-stu-id="d0f2a-155">Assign the policy package to users.</span></span> <span data-ttu-id="d0f2a-156">Se um usuário tiver uma política atribuída e depois você atribuir uma política diferente, a atribuição mais recente terá prioridade.</span><span class="sxs-lookup"><span data-stu-id="d0f2a-156">If a user has a policy assigned, and then later you assign a different policy, the most recent assignment will take priority.</span></span>

#### <a name="assign-a-policy-package-to-one-or-several-users"></a><span data-ttu-id="d0f2a-157">Atribuir um pacote de política a um ou vários usuários</span><span class="sxs-lookup"><span data-stu-id="d0f2a-157">Assign a policy package to one or several users</span></span>

<span data-ttu-id="d0f2a-158">Para atribuir um pacote de política a um ou vários usuários, no painel de navegação esquerdo do centro de administração do Microsoft Teams, vá para **pacotes de política** e selecione **gerenciar usuários**.</span><span class="sxs-lookup"><span data-stu-id="d0f2a-158">To assign a policy package to one or multiple users, in the left navigation of the Microsoft Teams admin center, go to **Policy packages** , and then select **Manage users**.</span></span>  

![Captura de tela de como atribuir um pacote de política no centro de administração](media/policy-packages-healthcare-assign.png)

<span data-ttu-id="d0f2a-160">Para saber mais, consulte [atribuir um pacote de política](manage-policy-packages.md#assign-a-policy-package).</span><span class="sxs-lookup"><span data-stu-id="d0f2a-160">To learn more, see [Assign a policy package](manage-policy-packages.md#assign-a-policy-package).</span></span>

<span data-ttu-id="d0f2a-161">Se um usuário tiver uma política atribuída e depois você atribuir uma política diferente, a atribuição mais recente terá prioridade.</span><span class="sxs-lookup"><span data-stu-id="d0f2a-161">If a user has a policy assigned, and then later you assign a different policy, the most recent assignment will take priority.</span></span>

#### <a name="assign-a-policy-package-to-a-group"></a><span data-ttu-id="d0f2a-162">Atribuir um pacote de política a um grupo</span><span class="sxs-lookup"><span data-stu-id="d0f2a-162">Assign a policy package to a group</span></span>

<span data-ttu-id="d0f2a-163">**Este recurso está em visualização particular**</span><span class="sxs-lookup"><span data-stu-id="d0f2a-163">**This feature is in private preview**</span></span>

<span data-ttu-id="d0f2a-164">A atribuição de pacote de política para grupos permite que você atribua várias políticas a um grupo de usuários, como um grupo de segurança ou lista de distribuição.</span><span class="sxs-lookup"><span data-stu-id="d0f2a-164">Policy package assignment to groups let you assign multiple policies to a group of users, such as a security group or distribution list.</span></span> <span data-ttu-id="d0f2a-165">A atribuição de política é propagada para os membros do grupo de acordo com as regras de precedência.</span><span class="sxs-lookup"><span data-stu-id="d0f2a-165">The policy assignment is propagated to members of the group according to precedence rules.</span></span> <span data-ttu-id="d0f2a-166">Conforme os membros são adicionados ou removidos de um grupo, suas atribuições de política herdadas são atualizadas de acordo.</span><span class="sxs-lookup"><span data-stu-id="d0f2a-166">As members are added to or removed from a group, their inherited policy assignments are updated accordingly.</span></span> <span data-ttu-id="d0f2a-167">Esse método é recomendado para grupos de até 50.000 usuários, mas também funcionará com grupos maiores.</span><span class="sxs-lookup"><span data-stu-id="d0f2a-167">This method is recommended for groups of up to 50,000 users but will also work with larger groups.</span></span>

<span data-ttu-id="d0f2a-168">Para saber mais, consulte [atribuir um pacote de política a um grupo](assign-policies.md#assign-a-policy-package-to-a-group).</span><span class="sxs-lookup"><span data-stu-id="d0f2a-168">To learn more, see [Assign a policy package to a group](assign-policies.md#assign-a-policy-package-to-a-group).</span></span>

#### <a name="assign-a-policy-package-to-a-large-set-batch-of-users"></a><span data-ttu-id="d0f2a-169">Atribuir um pacote de política a um grande conjunto (lote) de usuários</span><span class="sxs-lookup"><span data-stu-id="d0f2a-169">Assign a policy package to a large set (batch) of users</span></span>

<span data-ttu-id="d0f2a-170">Use a atribuição de pacote de política em lotes para atribuir um pacote de política a grandes conjuntos de usuários por vez.</span><span class="sxs-lookup"><span data-stu-id="d0f2a-170">Use batch policy package assignment to assign a policy package to large sets of users at a time.</span></span> <span data-ttu-id="d0f2a-171">Use o cmdlet [New-CsBatchPolicyPackageAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicypackageassignmentoperation) para enviar um lote de usuários e o pacote de política que você deseja atribuir.</span><span class="sxs-lookup"><span data-stu-id="d0f2a-171">You use the [New-CsBatchPolicyPackageAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicypackageassignmentoperation) cmdlet to submit a batch of users and the policy package that you want to assign.</span></span> <span data-ttu-id="d0f2a-172">As atribuições são processadas como uma operação em segundo plano e uma ID de operação é gerada para cada lote.</span><span class="sxs-lookup"><span data-stu-id="d0f2a-172">The assignments are processed as a background operation and an operation ID is generated for each batch.</span></span>

<span data-ttu-id="d0f2a-173">Um lote pode conter até 5.000 usuários.</span><span class="sxs-lookup"><span data-stu-id="d0f2a-173">A batch can contain up to 5,000 users.</span></span> <span data-ttu-id="d0f2a-174">Você pode especificar os usuários por sua ID de objeto, UPN, endereço SIP ou endereço de email.</span><span class="sxs-lookup"><span data-stu-id="d0f2a-174">You can specify users by their object Id, UPN, SIP address, or email address.</span></span> <span data-ttu-id="d0f2a-175">Para saber mais, consulte [atribuir um pacote de política a um lote de usuários](assign-policies.md#assign-a-policy-package-to-a-batch-of-users).</span><span class="sxs-lookup"><span data-stu-id="d0f2a-175">To learn more, see [Assign a policy package to a batch of users](assign-policies.md#assign-a-policy-package-to-a-batch-of-users).</span></span>

## <a name="related-topics"></a><span data-ttu-id="d0f2a-176">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="d0f2a-176">Related topics</span></span>

[<span data-ttu-id="d0f2a-177">Gerenciar pacotes de política em equipes</span><span class="sxs-lookup"><span data-stu-id="d0f2a-177">Manage policy packages in Teams</span></span>](manage-policy-packages.md)

[<span data-ttu-id="d0f2a-178">Atribuir políticas a seus usuários no Teams</span><span class="sxs-lookup"><span data-stu-id="d0f2a-178">Assign policies to your users in Teams</span></span>](assign-policies.md)
