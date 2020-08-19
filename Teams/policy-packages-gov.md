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
ms.openlocfilehash: 738197a82303c1149ebc89a8e3ad7c6b37df90eb
ms.sourcegitcommit: bd13aecbb25c14e17d1b64343df6d80c90b2aa45
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/19/2020
ms.locfileid: "46804003"
---
# <a name="teams-policy-packages-for-government"></a><span data-ttu-id="cb0d2-103">Pacotes de política de equipe para o governo</span><span class="sxs-lookup"><span data-stu-id="cb0d2-103">Teams policy packages for government</span></span>

> [!NOTE]
> <span data-ttu-id="cb0d2-104">Atualmente, os pacotes de política não estão disponíveis nas implantações do Microsoft 365 governo GCC High ou DoD.</span><span class="sxs-lookup"><span data-stu-id="cb0d2-104">Policy packages are currently not available in Microsoft 365 Government GCC High or DoD deployments.</span></span>

## <a name="overview"></a><span data-ttu-id="cb0d2-105">Visão geral</span><span class="sxs-lookup"><span data-stu-id="cb0d2-105">Overview</span></span>

<span data-ttu-id="cb0d2-106">Um [pacote de política](manage-policy-packages.md) no Microsoft Teams é uma coleção de políticas predefinidas e configurações de política que você pode atribuir aos usuários que têm funções semelhantes em sua organização.</span><span class="sxs-lookup"><span data-stu-id="cb0d2-106">A [policy package](manage-policy-packages.md) in Microsoft Teams is a collection of predefined policies and policy settings that you can assign to users who have similar roles in your organization.</span></span> <span data-ttu-id="cb0d2-107">Os pacotes de políticas simplificam, otimizam e ajudam a fornecer consistência ao gerenciar políticas.</span><span class="sxs-lookup"><span data-stu-id="cb0d2-107">Policy packages simplify, streamline, and help provide consistency when managing policies.</span></span> <span data-ttu-id="cb0d2-108">Você pode personalizar as configurações das políticas do pacote para atender às necessidades dos seus usuários.</span><span class="sxs-lookup"><span data-stu-id="cb0d2-108">You can customize the settings of the policies in the package to suit the needs of your users.</span></span> <span data-ttu-id="cb0d2-109">Quando você altera as configurações de políticas em um pacote de política, todos os usuários atribuídos a esse pacote obtêm as configurações atualizadas.</span><span class="sxs-lookup"><span data-stu-id="cb0d2-109">When you change the settings of policies in a policy package, all users who are assigned to that package get the updated settings.</span></span> <span data-ttu-id="cb0d2-110">Você pode gerenciar pacotes de política usando o centro de administração do Microsoft Teams ou o PowerShell.</span><span class="sxs-lookup"><span data-stu-id="cb0d2-110">You can manage policy packages by using the Microsoft Teams admin center or PowerShell.</span></span>

<span data-ttu-id="cb0d2-111">Pacotes de política pré-defina políticas para o seguinte, dependendo do pacote:</span><span class="sxs-lookup"><span data-stu-id="cb0d2-111">Policy packages pre-define policies for the following, depending on the package:</span></span>

- <span data-ttu-id="cb0d2-112">Mensagens</span><span class="sxs-lookup"><span data-stu-id="cb0d2-112">Messaging</span></span>
- <span data-ttu-id="cb0d2-113">Reuniões</span><span class="sxs-lookup"><span data-stu-id="cb0d2-113">Meetings</span></span>
- <span data-ttu-id="cb0d2-114">Chamadas</span><span class="sxs-lookup"><span data-stu-id="cb0d2-114">Calling</span></span>
- <span data-ttu-id="cb0d2-115">Configuração do aplicativo</span><span class="sxs-lookup"><span data-stu-id="cb0d2-115">App setup</span></span>
- <span data-ttu-id="cb0d2-116">Eventos ao vivo</span><span class="sxs-lookup"><span data-stu-id="cb0d2-116">Live events</span></span>

<span data-ttu-id="cb0d2-117">Atualmente, o Teams inclui os seguintes pacotes de política para o governo.</span><span class="sxs-lookup"><span data-stu-id="cb0d2-117">Teams currently includes the following policy packages for government.</span></span>

|<span data-ttu-id="cb0d2-118">Nome do pacote no centro de administração do Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="cb0d2-118">Package name in the Microsoft Teams admin center</span></span>|<span data-ttu-id="cb0d2-119">Melhor usado para</span><span class="sxs-lookup"><span data-stu-id="cb0d2-119">Best used for</span></span>|<span data-ttu-id="cb0d2-120">Descrição</span><span class="sxs-lookup"><span data-stu-id="cb0d2-120">Description</span></span> |
|---------|---------|---------|
|<span data-ttu-id="cb0d2-121">Diretor de segurança pública</span><span class="sxs-lookup"><span data-stu-id="cb0d2-121">Public safety officer</span></span>  |<span data-ttu-id="cb0d2-122">Diretores de segurança públicos em sua organização governamental</span><span class="sxs-lookup"><span data-stu-id="cb0d2-122">Public safety officers in your government organization</span></span>  |<span data-ttu-id="cb0d2-123">Cria um conjunto de políticas e configurações de política que se aplicam a órgãos públicos de segurança em sua organização.</span><span class="sxs-lookup"><span data-stu-id="cb0d2-123">Creates a set of policies and policy settings that apply to public safety officers in your organization.</span></span> |
|<span data-ttu-id="cb0d2-124">Gerente da primeira mão</span><span class="sxs-lookup"><span data-stu-id="cb0d2-124">Firstline manager</span></span>  |<span data-ttu-id="cb0d2-125">Gerentes de primeira mão em sua organização governamental</span><span class="sxs-lookup"><span data-stu-id="cb0d2-125">Firstline Managers in your government organization</span></span> |<span data-ttu-id="cb0d2-126">Cria um conjunto de políticas e aplica essas configurações aos gerentes de primeira empresa.</span><span class="sxs-lookup"><span data-stu-id="cb0d2-126">Creates a set of policies and applies those settings to Firstline Managers in your organization.</span></span>|
|<span data-ttu-id="cb0d2-127">Trabalho da primeira</span><span class="sxs-lookup"><span data-stu-id="cb0d2-127">Firstline worker</span></span>  |<span data-ttu-id="cb0d2-128">Trabalhadores de primeira mão em sua organização governamental</span><span class="sxs-lookup"><span data-stu-id="cb0d2-128">Firstline Workers in your government organization</span></span> |<span data-ttu-id="cb0d2-129">Cria um conjunto de políticas e aplica essas configurações aos trabalhos iniciais em sua organização.</span><span class="sxs-lookup"><span data-stu-id="cb0d2-129">Creates a set of policies and applies those settings to Firstline Workers in your organization.</span></span>|

![Captura de tela dos pacotes de política da assistência médica](media/policy-packages-gov.png)

<span data-ttu-id="cb0d2-131">Cada política individual recebe o nome do pacote de política para que você possa facilmente identificar as políticas que estão vinculadas a um pacote de política.</span><span class="sxs-lookup"><span data-stu-id="cb0d2-131">Each individual policy is given the name of the policy package so you can easily identify the policies that are linked to a policy package.</span></span> <span data-ttu-id="cb0d2-132">Por exemplo, quando você atribui o pacote de política do diretor de segurança pública aos usuários em sua organização, uma política chamada PublicSafety_Officer é criada para cada política no pacote.</span><span class="sxs-lookup"><span data-stu-id="cb0d2-132">For example, when you assign the Public safety officer policy package to users in your organization, a policy named PublicSafety_Officer is created for each policy in the package.</span></span>

![Captura de tela de políticas no pacote de trabalho clínico da assistência médica](media/policy-packages-public-safety-officer.png)

## <a name="manage-policy-packages"></a><span data-ttu-id="cb0d2-134">Gerenciar pacotes de política</span><span class="sxs-lookup"><span data-stu-id="cb0d2-134">Manage policy packages</span></span>

### <a name="view"></a><span data-ttu-id="cb0d2-135">View</span><span class="sxs-lookup"><span data-stu-id="cb0d2-135">View</span></span>

<span data-ttu-id="cb0d2-136">Exiba as configurações de cada política em um pacote de política antes de atribuir um pacote.</span><span class="sxs-lookup"><span data-stu-id="cb0d2-136">View the settings of each policy in a policy package before you assign a package.</span></span> <span data-ttu-id="cb0d2-137">Na navegação à esquerda do centro de administração do Microsoft Teams, selecione **pacotes de política**, selecione o nome do pacote e, em seguida, selecione o nome da política.</span><span class="sxs-lookup"><span data-stu-id="cb0d2-137">In the left navigation of the Microsoft Teams admin center, select **Policy packages**, select the package name, and then select the policy name.</span></span>

<span data-ttu-id="cb0d2-138">Decida se os valores predefinidos são adequados para sua organização ou se você precisa personalizá-los para serem mais restritivos ou lenient com base nas necessidades da sua organização.</span><span class="sxs-lookup"><span data-stu-id="cb0d2-138">Decide whether the predefined values are appropriate for your organization or whether you need to customize them to be more restrictive or lenient based on your organization's needs.</span></span>

### <a name="customize"></a><span data-ttu-id="cb0d2-139">Personalizar</span><span class="sxs-lookup"><span data-stu-id="cb0d2-139">Customize</span></span>

<span data-ttu-id="cb0d2-140">Personalize as configurações das políticas no pacote de política, conforme necessário, para atender às necessidades da sua organização.</span><span class="sxs-lookup"><span data-stu-id="cb0d2-140">Customize the settings of policies in the policy package, as needed, to fit the needs of your organization.</span></span> <span data-ttu-id="cb0d2-141">Todas as alterações feitas nas configurações de política são automaticamente aplicadas a usuários atribuídos ao pacote.</span><span class="sxs-lookup"><span data-stu-id="cb0d2-141">Any changes you make to policy settings are automatically applied to users who are assigned the package.</span></span> <span data-ttu-id="cb0d2-142">Para editar as configurações de uma política em um pacote de política, no centro de administração do Microsoft Teams, selecione o pacote de política, selecione o nome da política que você deseja editar e, em seguida, selecione **Editar**.</span><span class="sxs-lookup"><span data-stu-id="cb0d2-142">To edit the settings of a policy in a policy package, in the Microsoft Teams admin center, select the policy package, select the name of the policy you want to edit, and then select **Edit**.</span></span>

<span data-ttu-id="cb0d2-143">Lembre-se de que você também pode alterar as configurações de políticas em um pacote após atribuir o pacote de política.</span><span class="sxs-lookup"><span data-stu-id="cb0d2-143">Keep in mind that you can also change the settings of policies in a package after you assign the policy package.</span></span> <span data-ttu-id="cb0d2-144">Para saber mais, consulte [Personalizar políticas em um pacote de política](manage-policy-packages.md#customize-policies-in-a-policy-package).</span><span class="sxs-lookup"><span data-stu-id="cb0d2-144">To learn more, see [Customize policies in a policy package](manage-policy-packages.md#customize-policies-in-a-policy-package).</span></span> 

### <a name="assign"></a><span data-ttu-id="cb0d2-145">Atribuição</span><span class="sxs-lookup"><span data-stu-id="cb0d2-145">Assign</span></span>

<span data-ttu-id="cb0d2-146">Atribua o pacote de política aos usuários.</span><span class="sxs-lookup"><span data-stu-id="cb0d2-146">Assign the policy package to users.</span></span> <span data-ttu-id="cb0d2-147">Para atribuir um pacote de política a um ou vários usuários, clique em **gerenciar usuários**.</span><span class="sxs-lookup"><span data-stu-id="cb0d2-147">To assign a policy package to one or multiple users, click **Manage users**.</span></span> <span data-ttu-id="cb0d2-148">Você também pode [usar o PowerShell](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicypackageassignmentoperation) para atribuir um pacote de política a lotes grandes de usuários.</span><span class="sxs-lookup"><span data-stu-id="cb0d2-148">You can also [use PowerShell](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicypackageassignmentoperation) to assign a policy package to large batches of users.</span></span> 

<span data-ttu-id="cb0d2-149">Para ver as etapas sobre como atribuir um pacote de política usando o centro de administração do Microsoft Teams ou o PowerShell, consulte [atribuir um pacote de política](manage-policy-packages.md#assign-a-policy-package).</span><span class="sxs-lookup"><span data-stu-id="cb0d2-149">For steps on how to assign a policy package using the Microsoft Teams admin center or PowerShell, see [Assign a policy package](manage-policy-packages.md#assign-a-policy-package).</span></span>

![Captura de tela de como atribuir um pacote de política no centro de administração](media/policy-packages-gov-assign.png)

<span data-ttu-id="cb0d2-151">Se um usuário tiver uma política atribuída e depois você atribuir uma política diferente, a atribuição mais recente terá prioridade.</span><span class="sxs-lookup"><span data-stu-id="cb0d2-151">If a user has a policy assigned, and then later you assign a different policy, the most recent assignment will take priority.</span></span>

## <a name="related-topics"></a><span data-ttu-id="cb0d2-152">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="cb0d2-152">Related topics</span></span>

[<span data-ttu-id="cb0d2-153">Gerenciar pacotes de política em equipes</span><span class="sxs-lookup"><span data-stu-id="cb0d2-153">Manage policy packages in Teams</span></span>](manage-policy-packages.md)

[<span data-ttu-id="cb0d2-154">Atribuir políticas a seus usuários no Teams</span><span class="sxs-lookup"><span data-stu-id="cb0d2-154">Assign policies to your users in Teams</span></span>](assign-policies.md) 
