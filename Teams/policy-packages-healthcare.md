---
title: Pacotes de políticas do Teams para a área de saúde
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
description: Saiba como usar e gerenciar pacotes de política do Teams para sua organização da área de saúde.
ms.openlocfilehash: 19c0fee14138b248c4e25d88a9103df4a5618598
ms.sourcegitcommit: 8ad05b37c0b714adb069bc2503e88366ab75c57d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/07/2021
ms.locfileid: "52796805"
---
# <a name="teams-policy-packages-for-healthcare"></a><span data-ttu-id="f8dcd-103">Pacotes de políticas do Teams para a área de saúde</span><span class="sxs-lookup"><span data-stu-id="f8dcd-103">Teams policy packages for healthcare</span></span>

## <a name="overview"></a><span data-ttu-id="f8dcd-104">Visão Geral</span><span class="sxs-lookup"><span data-stu-id="f8dcd-104">Overview</span></span>

<span data-ttu-id="f8dcd-105">Um [pacote de política](manage-policy-packages.md) no Microsoft Teams é um conjunto de políticas e configurações de política predefinidas que você pode atribuir a usuários com funções semelhantes em sua organização.</span><span class="sxs-lookup"><span data-stu-id="f8dcd-105">A [policy package](manage-policy-packages.md) in Microsoft Teams is a collection of predefined policies and policy settings that you can assign to users who have similar roles in your organization.</span></span> <span data-ttu-id="f8dcd-106">Os pacotes de políticas simplificam, otimizam e ajudam a fornecer consistência ao gerenciar políticas.</span><span class="sxs-lookup"><span data-stu-id="f8dcd-106">Policy packages simplify, streamline, and help provide consistency when managing policies.</span></span> <span data-ttu-id="f8dcd-107">Você pode personalizar as configurações das políticas no pacote para atender às necessidades dos usuários.</span><span class="sxs-lookup"><span data-stu-id="f8dcd-107">You can customize the settings of the policies in the package to suit the needs of your users.</span></span> <span data-ttu-id="f8dcd-108">Quando você altera as configurações de políticas em um pacote de política, todos os usuários atribuídos a esse pacote têm as configurações atualizadas.</span><span class="sxs-lookup"><span data-stu-id="f8dcd-108">When you change the settings of policies in a policy package, all users who are assigned to that package get the updated settings.</span></span> <span data-ttu-id="f8dcd-109">Você pode gerenciar pacotes de política usando o Centro de Administração do Microsoft Teams ou o Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="f8dcd-109">You can manage policy packages by using the Microsoft Teams admin center or PowerShell.</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4Ht2o]

<span data-ttu-id="f8dcd-110">Pacotes de política pré-definem políticas para o seguinte, dependendo do pacote:</span><span class="sxs-lookup"><span data-stu-id="f8dcd-110">Policy packages pre-define policies for the following, depending on the package:</span></span>

- <span data-ttu-id="f8dcd-111">Mensagens</span><span class="sxs-lookup"><span data-stu-id="f8dcd-111">Messaging</span></span>
- <span data-ttu-id="f8dcd-112">Reuniões</span><span class="sxs-lookup"><span data-stu-id="f8dcd-112">Meetings</span></span>
- <span data-ttu-id="f8dcd-113">Chamadas</span><span class="sxs-lookup"><span data-stu-id="f8dcd-113">Calling</span></span>
- <span data-ttu-id="f8dcd-114">Configuração do aplicativo</span><span class="sxs-lookup"><span data-stu-id="f8dcd-114">App setup</span></span>
- <span data-ttu-id="f8dcd-115">Eventos ao vivo</span><span class="sxs-lookup"><span data-stu-id="f8dcd-115">Live events</span></span>

<span data-ttu-id="f8dcd-116">No momento, o Microsoft Teams inclui os seguintes pacotes de políticas.</span><span class="sxs-lookup"><span data-stu-id="f8dcd-116">Teams currently includes the following healthcare policy packages.</span></span>

|<span data-ttu-id="f8dcd-117">Nome do pacote listado no Centro de Administração do Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="f8dcd-117">Package name in the Microsoft Teams admin center</span></span>|<span data-ttu-id="f8dcd-118">Melhor usado para</span><span class="sxs-lookup"><span data-stu-id="f8dcd-118">Best used for</span></span>|<span data-ttu-id="f8dcd-119">Descrição</span><span class="sxs-lookup"><span data-stu-id="f8dcd-119">Description</span></span> |
|---------|---------|---------|
|<span data-ttu-id="f8dcd-120">Profissional clínico da área de saúde</span><span class="sxs-lookup"><span data-stu-id="f8dcd-120">Healthcare clinical worker</span></span>  |<span data-ttu-id="f8dcd-121">Colaboradores clínicos em sua organização da área de saúde</span><span class="sxs-lookup"><span data-stu-id="f8dcd-121">Clinical workers in your healthcare organization</span></span>  |<span data-ttu-id="f8dcd-122">Cria um conjunto de políticas e configurações de política que dão a funcionários da área de saúde, como enfermeiros registrados, enfermeiros chefe, médicos e assistentes sociais acesso total ao chat, chamadas, gerenciamento de turnos e reuniões.</span><span class="sxs-lookup"><span data-stu-id="f8dcd-122">Creates a set of policies and policy settings that give clinical workers such as registered nurses, charge nurses, physicians, and social workers full access to chat, calling, shift management, and meetings.</span></span> |
|<span data-ttu-id="f8dcd-123">Profissional de informações da área de saúde</span><span class="sxs-lookup"><span data-stu-id="f8dcd-123">Healthcare information worker</span></span>  |<span data-ttu-id="f8dcd-124">Operadores de informações em sua organização da área de saúde</span><span class="sxs-lookup"><span data-stu-id="f8dcd-124">Information workers in your healthcare organization</span></span> |<span data-ttu-id="f8dcd-125">Cria um conjunto de políticas e configurações de política que dão aos operadores de informações na sua organização da área de saúde, como equipe de TI, de informática, equipe financeira e responsáveis pela conformidade acesso total ao chat, chamadas e reuniões.</span><span class="sxs-lookup"><span data-stu-id="f8dcd-125">Creates a set of policies and policy settings that give information workers such as IT personnel, informatics staff, finance personnel, and compliance officers, full access to chat, calling, and meetings.</span></span>|
|<span data-ttu-id="f8dcd-126">Quartos dos pacientes de saúde</span><span class="sxs-lookup"><span data-stu-id="f8dcd-126">Healthcare patient room</span></span>  |<span data-ttu-id="f8dcd-127">Dispositivos de quarto dos pacientes</span><span class="sxs-lookup"><span data-stu-id="f8dcd-127">Patient room devices</span></span>|<span data-ttu-id="f8dcd-128">Cria um conjunto de políticas e configurações de política que se aplicam aos quartos dos pacientes em sua organização de saúde.</span><span class="sxs-lookup"><span data-stu-id="f8dcd-128">Creates a set of policies and policy settings that apply to patient rooms in your healthcare organization.</span></span>|

![Captura de tela dos pacotes de política de saúde](media/policy-packages-healthcare.png)

<span data-ttu-id="f8dcd-130">Cada política individual recebe o nome do pacote de políticas, para que você possa identificar facilmente políticas vinculadas a um pacote de políticas.</span><span class="sxs-lookup"><span data-stu-id="f8dcd-130">Each individual policy is given the name of the policy package so you can easily identify the policies that are linked to a policy package.</span></span> <span data-ttu-id="f8dcd-131">Por exemplo, quando você atribui o pacote de políticas para trabalhadores clínicos da área de saúde a clínicos de sua organização, uma política chamada Healthcare_ClinicalWorker é criada para cada política do pacote.</span><span class="sxs-lookup"><span data-stu-id="f8dcd-131">For example, when you assign the Healthcare clinical worker policy package to clinicians in your organization, a policy named Healthcare_ClinicalWorker is created for each policy in the package.</span></span>

![Captura de tela das políticas no pacote de funcionários clínicos da área de saúde](media/policy-packages-healthcare-clinical-worker.png)

## <a name="get-started-with-policy-packages"></a><span data-ttu-id="f8dcd-133">Começar a trabalhar com pacotes de política</span><span class="sxs-lookup"><span data-stu-id="f8dcd-133">Get started with policy packages</span></span>

<span data-ttu-id="f8dcd-134">Para começar a trabalhar com pacotes de política da área de saúde, no hub de integração do Centro de Administração da Microsoft, selecione **Healthcare** e, então, selecione **Atribuir configurações de política por função**.</span><span class="sxs-lookup"><span data-stu-id="f8dcd-134">To get you started with Healthcare policy packages, on the Microsoft Admin Center onboarding hub, select **Healthcare**, and then select **Assign policy settings by role**.</span></span> <span data-ttu-id="f8dcd-135">Quando estiver pronto para começar, decida a quais pacotes de política você gostaria de atribuir a indivíduos em sua organização.</span><span class="sxs-lookup"><span data-stu-id="f8dcd-135">Once you’re ready to get started, decide which policy packages you'd like to assign individuals in your organization to.</span></span>

<span data-ttu-id="f8dcd-136">Selecione **Exibir detalhes da política** para saber mais sobre as políticas específicas em um pacote e suas respectivas configurações.</span><span class="sxs-lookup"><span data-stu-id="f8dcd-136">Select **View policy details** to learn more about the specific policies in a package and their respective settings.</span></span> <span data-ttu-id="f8dcd-137">Essas [podem ser personalizadas](manage-policy-packages.md#customize-policies-in-a-policy-package) após a atribuição no Centro de Administração do Teams.</span><span class="sxs-lookup"><span data-stu-id="f8dcd-137">These [can be customized](manage-policy-packages.md#customize-policies-in-a-policy-package) after assignment in the Teams Admin Center.</span></span>

<span data-ttu-id="f8dcd-138">Escolha um ou vários pacotes para atribuir e clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="f8dcd-138">Choose one or multiple packages to assign and then click **Next**.</span></span> <span data-ttu-id="f8dcd-139">Você pode pesquisar e adicionar pessoas ao pacote de políticas mais adequado para sua função.</span><span class="sxs-lookup"><span data-stu-id="f8dcd-139">You can search for and add people to the policy package best suited for their role.</span></span> <span data-ttu-id="f8dcd-140">Um indivíduo não pode ser atribuído a mais de um pacote de política ao mesmo tempo.</span><span class="sxs-lookup"><span data-stu-id="f8dcd-140">An individual can't be assigned to more than one policy package at one time.</span></span>

<span data-ttu-id="f8dcd-141">Depois de adicionar pessoas ao pacote de política correto, você **Concluir** finaliza suas seleções.</span><span class="sxs-lookup"><span data-stu-id="f8dcd-141">Once you’ve added people to the right policy package, **Finish** finalizes your selections.</span></span> <span data-ttu-id="f8dcd-142">Você pode continuar a personalizar e gerenciar pacotes de política no Centro de Administração do Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="f8dcd-142">You can continue to customize and manage policy packages in the Microsoft Teams admin center.</span></span>

## <a name="manage-policy-packages"></a><span data-ttu-id="f8dcd-143">Gerenciar pacotes de política</span><span class="sxs-lookup"><span data-stu-id="f8dcd-143">Manage policy packages</span></span>

### <a name="view"></a><span data-ttu-id="f8dcd-144">Exibir</span><span class="sxs-lookup"><span data-stu-id="f8dcd-144">View</span></span>

<span data-ttu-id="f8dcd-145">Exibir as configurações de cada política em um pacote de política antes de atribuir um pacote.</span><span class="sxs-lookup"><span data-stu-id="f8dcd-145">View the settings of each policy in a policy package before you assign a package.</span></span> <span data-ttu-id="f8dcd-146">Na navegação à esquerda do Centro de Administração do Microsoft Teams, selecione **Pacotes de Política**, selecione o nome do pacote e, em seguida, selecione o nome da política.</span><span class="sxs-lookup"><span data-stu-id="f8dcd-146">In the left navigation of the Microsoft Teams admin center, go to **Policy packages**, select the package name, and then select the policy name.</span></span>

<span data-ttu-id="f8dcd-147">Decida se os valores predefinidos são apropriados para a sua organização ou se você precisa personalizá-los para serem mais restritivos ou leniente com base nas necessidades da sua organização.</span><span class="sxs-lookup"><span data-stu-id="f8dcd-147">Decide whether the predefined values are appropriate for your organization or whether you need to customize them to be more restrictive or lenient based on your organization's needs.</span></span>

### <a name="customize"></a><span data-ttu-id="f8dcd-148">Personalizar</span><span class="sxs-lookup"><span data-stu-id="f8dcd-148">Customize</span></span>

<span data-ttu-id="f8dcd-149">Personalize as configurações das políticas no pacote de política, conforme necessário, para atender às necessidades da sua organização.</span><span class="sxs-lookup"><span data-stu-id="f8dcd-149">Customize the settings of policies in the policy package, as needed, to fit the needs of your organization.</span></span> <span data-ttu-id="f8dcd-150">As alterações que você fizer nas configurações da política serão automaticamente aplicadas aos usuários que recebem o pacote.</span><span class="sxs-lookup"><span data-stu-id="f8dcd-150">Any changes you make to policy settings are automatically applied to users who are assigned the package.</span></span> <span data-ttu-id="f8dcd-151">Para editar as configurações de uma política em um pacote de política, na navegação à esquerda do Centro de Administração do Microsoft Teams, vá para **Pacotes de política**, selecione o pacote de política, selecione o nome da política que você deseja editar e selecione **Editar**.</span><span class="sxs-lookup"><span data-stu-id="f8dcd-151">To edit the settings of a policy in a policy package, in the left navigation of the Microsoft Teams admin center, go to **Policy packages**, select the policy package, select the name of the policy you want to edit, and then select **Edit**.</span></span>

<span data-ttu-id="f8dcd-152">Lembre-se de que você também pode alterar as configurações das políticas em um pacote após atribuir o pacote de política.</span><span class="sxs-lookup"><span data-stu-id="f8dcd-152">Keep in mind that you can also change the settings of policies in a package after you assign the policy package.</span></span> <span data-ttu-id="f8dcd-153">Para saber mais, confira [Personalizar políticas em um pacote de política](manage-policy-packages.md#customize-policies-in-a-policy-package).</span><span class="sxs-lookup"><span data-stu-id="f8dcd-153">To learn more, see [Customize policies in a policy package](manage-policy-packages.md#customize-policies-in-a-policy-package).</span></span>

### <a name="assign"></a><span data-ttu-id="f8dcd-154">Atribuir</span><span class="sxs-lookup"><span data-stu-id="f8dcd-154">Assign</span></span>

<span data-ttu-id="f8dcd-p110">Atribua o pacote de política aos usuários. Se um usuário tiver uma política atribuída e, mais tarde, você atribuir uma política diferente, a atribuição mais recente terá prioridade.</span><span class="sxs-lookup"><span data-stu-id="f8dcd-p110">Assign the policy package to users. If a user has a policy assigned, and then later you assign a different policy, the most recent assignment will take priority.</span></span>

> [!NOTE]
> <span data-ttu-id="f8dcd-157">Cada usuário exigirá o complemento Comunicações Avançadas para receber uma atribuição de pacote de política personalizada.</span><span class="sxs-lookup"><span data-stu-id="f8dcd-157">Each user will require the Advanced Communications add-on in order to receive a custom policy package assignment.</span></span> <span data-ttu-id="f8dcd-158">Para obter mais informações, consulte [Advanced Communications add-on for Microsoft Teams](/microsoftteams/teams-add-on-licensing/advanced-communications).</span><span class="sxs-lookup"><span data-stu-id="f8dcd-158">For more information, see [Advanced Communications add-on for Microsoft Teams](/microsoftteams/teams-add-on-licensing/advanced-communications).</span></span>

#### <a name="assign-a-policy-package-to-one-or-several-users"></a><span data-ttu-id="f8dcd-159">Atribuir um pacote de política a um ou vários usuários</span><span class="sxs-lookup"><span data-stu-id="f8dcd-159">Assign a policy package to one or several users</span></span>

<span data-ttu-id="f8dcd-160">Para atribuir um pacote de política a um ou vários usuários, na barra de navegação à esquerda do centro de administração do Microsoft Teams, vá para **Pacotes de política** e, em seguida, selecione **Gerenciar usuários**.</span><span class="sxs-lookup"><span data-stu-id="f8dcd-160">To assign a policy package to one or multiple users, in the left navigation of the Microsoft Teams admin center, go to **Policy packages**, and then select **Manage users**.</span></span>  

![Captura de tela de como atribuir um pacote de política no centro de administração](media/policy-packages-healthcare-assign.png)

<span data-ttu-id="f8dcd-162">Para saber mais, confira [Atribuir um pacote de política](manage-policy-packages.md#assign-a-policy-package).</span><span class="sxs-lookup"><span data-stu-id="f8dcd-162">To learn more, see [Assign a policy package](manage-policy-packages.md#assign-a-policy-package).</span></span>

<span data-ttu-id="f8dcd-163">Se um usuário tiver uma política atribuída e, em seguida, você atribuir uma política diferente, a atribuição mais recente terá prioridade.</span><span class="sxs-lookup"><span data-stu-id="f8dcd-163">If a user has a policy assigned, and then later you assign a different policy, the most recent assignment will take priority.</span></span>

#### <a name="assign-a-policy-package-to-a-group"></a><span data-ttu-id="f8dcd-164">Atribua o pacote de política a um grupo.</span><span class="sxs-lookup"><span data-stu-id="f8dcd-164">Assign a policy package to a group</span></span>

<span data-ttu-id="f8dcd-165">**Este recurso está na visualização particular**</span><span class="sxs-lookup"><span data-stu-id="f8dcd-165">**This feature is in private preview**</span></span>

<span data-ttu-id="f8dcd-166">As atribuições de pacote de política aos grupos permitem atribuir várias políticas a um grupo de usuários, como uma lista de distribuição ou grupo de segurança.</span><span class="sxs-lookup"><span data-stu-id="f8dcd-166">Policy package assignment to groups let you assign multiple policies to a group of users, such as a security group or distribution list.</span></span> <span data-ttu-id="f8dcd-167">As atribuições de política serão propagadas para os membros do grupo, de acordo com as regras de precedência.</span><span class="sxs-lookup"><span data-stu-id="f8dcd-167">The policy assignment is propagated to members of the group according to precedence rules.</span></span> <span data-ttu-id="f8dcd-168">À medida que os membros forem adicionados ou removidos de um grupo, as atribuições de política herdadas serão atualizadas.</span><span class="sxs-lookup"><span data-stu-id="f8dcd-168">As members are added to or removed from a group, their inherited policy assignments are updated accordingly.</span></span> <span data-ttu-id="f8dcd-169">Esse método é recomendado para grupos de até 50.000 usuários, mas também funcionará com grupos maiores.</span><span class="sxs-lookup"><span data-stu-id="f8dcd-169">This method is recommended for groups of up to 50,000 users but will also work with larger groups.</span></span>

<span data-ttu-id="f8dcd-170">Para saber mais, confira [Atribuir um pacote de política a um grupo](assign-policies.md#assign-a-policy-package-to-a-group).</span><span class="sxs-lookup"><span data-stu-id="f8dcd-170">To learn more, see [Assign a policy package to a group](assign-policies.md#assign-a-policy-package-to-a-group).</span></span>

#### <a name="assign-a-policy-package-to-a-large-set-batch-of-users"></a><span data-ttu-id="f8dcd-171">Atribuir um pacote de política a um conjunto grande (lote) de usuários</span><span class="sxs-lookup"><span data-stu-id="f8dcd-171">Assign a policy package to a large set (batch) of users</span></span>

<span data-ttu-id="f8dcd-172">Use a tarefa de pacote de política de lote para atribuir um pacote de política a grandes conjuntos de usuários por vez.</span><span class="sxs-lookup"><span data-stu-id="f8dcd-172">Use batch policy package assignment to assign a policy package to large sets of users at a time.</span></span> <span data-ttu-id="f8dcd-173">Use o cmdlet [New-CsBatchPolicyPackageAssignmentOperation](/powershell/module/teams/new-csbatchpolicypackageassignmentoperation) para enviar um lote de usuários e o pacote de política que você deseja atribuir.</span><span class="sxs-lookup"><span data-stu-id="f8dcd-173">You use the [New-CsBatchPolicyPackageAssignmentOperation](/powershell/module/teams/new-csbatchpolicypackageassignmentoperation) cmdlet to submit a batch of users and the policy package that you want to assign.</span></span> <span data-ttu-id="f8dcd-174">As atribuições são processadas como uma operação de plano de fundo e uma ID de operação é gerada para cada lote.</span><span class="sxs-lookup"><span data-stu-id="f8dcd-174">The assignments are processed as a background operation and an operation ID is generated for each batch.</span></span>

<span data-ttu-id="f8dcd-175">Um lote pode conter até 5.000 usuários.</span><span class="sxs-lookup"><span data-stu-id="f8dcd-175">A batch can contain up to 5,000 users.</span></span> <span data-ttu-id="f8dcd-176">Você pode especificar os usuários por ID do objeto, UPN, endereço SIP ou endereço de email.</span><span class="sxs-lookup"><span data-stu-id="f8dcd-176">You can specify users by their object Id, UPN, SIP address, or email address.</span></span> <span data-ttu-id="f8dcd-177">Para saber mais, confira [Atribuir um pacote de política a um lote de usuários](assign-policies.md#assign-a-policy-package-to-a-batch-of-users).</span><span class="sxs-lookup"><span data-stu-id="f8dcd-177">To learn more, see [Assign a policy package to a batch of users](assign-policies.md#assign-a-policy-package-to-a-batch-of-users).</span></span>

## <a name="related-topics"></a><span data-ttu-id="f8dcd-178">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="f8dcd-178">Related topics</span></span>

[<span data-ttu-id="f8dcd-179">Gerenciar pacotes de política em equipes</span><span class="sxs-lookup"><span data-stu-id="f8dcd-179">Manage policy packages in Teams</span></span>](manage-policy-packages.md)

[<span data-ttu-id="f8dcd-180">Atribuir pacotes de política a usuários e grupos</span><span class="sxs-lookup"><span data-stu-id="f8dcd-180">Assign policy packages to users and groups</span></span>](assign-policy-packages.md)
