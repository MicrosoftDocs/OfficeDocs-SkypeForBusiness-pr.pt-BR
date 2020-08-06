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
appliesto:
- Microsoft Teams
f1.keywords: ''
ms.custom: ''
localization_priority: Normal
search.appverid: MET150
description: Saiba como usar e gerenciar pacotes de política de equipe para sua organização de assistência médica.
ms.openlocfilehash: e7b01935969105abae447ae896480e1faf67fa40
ms.sourcegitcommit: 2aea6ec07149a3054ee4434c8a0bffabf1a16d25
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/06/2020
ms.locfileid: "46578182"
---
# <a name="teams-policy-packages-for-healthcare"></a><span data-ttu-id="f8c24-103">Pacotes de política de equipe para assistência médica</span><span class="sxs-lookup"><span data-stu-id="f8c24-103">Teams policy packages for healthcare</span></span>

## <a name="overview"></a><span data-ttu-id="f8c24-104">Visão geral</span><span class="sxs-lookup"><span data-stu-id="f8c24-104">Overview</span></span>

<span data-ttu-id="f8c24-105">Um [pacote de política](manage-policy-packages.md) no Microsoft Teams é uma coleção de políticas predefinidas e configurações de política que você pode atribuir aos usuários que têm funções semelhantes em sua organização.</span><span class="sxs-lookup"><span data-stu-id="f8c24-105">A [policy package](manage-policy-packages.md) in Microsoft Teams is a collection of predefined policies and policy settings that you can assign to users who have similar roles in your organization.</span></span> <span data-ttu-id="f8c24-106">Os pacotes de políticas simplificam, otimizam e ajudam a fornecer consistência ao gerenciar políticas.</span><span class="sxs-lookup"><span data-stu-id="f8c24-106">Policy packages simplify, streamline, and help provide consistency when managing policies.</span></span> <span data-ttu-id="f8c24-107">Você pode personalizar as configurações das políticas do pacote para atender às necessidades dos seus usuários.</span><span class="sxs-lookup"><span data-stu-id="f8c24-107">You can customize the settings of the policies in the package to suit the needs of your users.</span></span> <span data-ttu-id="f8c24-108">Quando você altera as configurações de políticas em um pacote de política, todos os usuários atribuídos a esse pacote obtêm as configurações atualizadas.</span><span class="sxs-lookup"><span data-stu-id="f8c24-108">When you change the settings of policies in a policy package, all users who are assigned to that package get the updated settings.</span></span> <span data-ttu-id="f8c24-109">Você pode gerenciar pacotes de política usando o centro de administração do Microsoft Teams ou o PowerShell.</span><span class="sxs-lookup"><span data-stu-id="f8c24-109">You can manage policy packages by using the Microsoft Teams admin center or PowerShell.</span></span>

<span data-ttu-id="f8c24-110">Pacotes de política pré-defina políticas para o seguinte, dependendo do pacote:</span><span class="sxs-lookup"><span data-stu-id="f8c24-110">Policy packages pre-define policies for the following, depending on the package:</span></span>

- <span data-ttu-id="f8c24-111">Reuniões</span><span class="sxs-lookup"><span data-stu-id="f8c24-111">Meetings</span></span>
- <span data-ttu-id="f8c24-112">Eventos ao vivo</span><span class="sxs-lookup"><span data-stu-id="f8c24-112">Live events</span></span>
- <span data-ttu-id="f8c24-113">Chamadas</span><span class="sxs-lookup"><span data-stu-id="f8c24-113">Calling</span></span>
- <span data-ttu-id="f8c24-114">Mensagens</span><span class="sxs-lookup"><span data-stu-id="f8c24-114">Messaging</span></span>
- <span data-ttu-id="f8c24-115">Teams</span><span class="sxs-lookup"><span data-stu-id="f8c24-115">Teams</span></span>
- <span data-ttu-id="f8c24-116">Configuração do aplicativo</span><span class="sxs-lookup"><span data-stu-id="f8c24-116">App setup</span></span>

<span data-ttu-id="f8c24-117">Atualmente, o Microsoft Teams inclui os seguintes pacotes de política de assistência médica.</span><span class="sxs-lookup"><span data-stu-id="f8c24-117">Teams currently includes the following healthcare policy packages.</span></span>

|<span data-ttu-id="f8c24-118">Nome do pacote no centro de administração do Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="f8c24-118">Package name in the Microsoft Teams admin center</span></span>|<span data-ttu-id="f8c24-119">Melhor usado para</span><span class="sxs-lookup"><span data-stu-id="f8c24-119">Best used for</span></span>|<span data-ttu-id="f8c24-120">Descrição</span><span class="sxs-lookup"><span data-stu-id="f8c24-120">Description</span></span> |
|---------|---------|---------|
|<span data-ttu-id="f8c24-121">Trabalhador clínico da assistência médica</span><span class="sxs-lookup"><span data-stu-id="f8c24-121">Healthcare clinical worker</span></span>  |<span data-ttu-id="f8c24-122">Trabalhadores clínicos na sua organização de assistência médica</span><span class="sxs-lookup"><span data-stu-id="f8c24-122">Clinical workers in your healthcare organization</span></span>  |<span data-ttu-id="f8c24-123">Cria um conjunto de políticas e configurações de política que dão a funcionários clínicos, como as mensagens de mão registradas, recarga de mão, médicos e funcionários sociais acesso total a chats, chamadas, gerenciamento de turnos e reuniões.</span><span class="sxs-lookup"><span data-stu-id="f8c24-123">Creates a set of policies and policy settings that give clinical workers such as registered nurses, charge nurses, physicians, and social workers full access to chat, calling, shift management, and meetings.</span></span> |
|<span data-ttu-id="f8c24-124">Operador de informações da assistência médica</span><span class="sxs-lookup"><span data-stu-id="f8c24-124">Healthcare information worker</span></span>  |<span data-ttu-id="f8c24-125">Operadores de informações em sua organização de assistência médica</span><span class="sxs-lookup"><span data-stu-id="f8c24-125">Information workers in your healthcare organization</span></span> |<span data-ttu-id="f8c24-126">Cria um conjunto de políticas e configurações de política que fornecem aos operadores de informações, como pessoal de ti, pessoal de informática, pessoal de finanças e órgãos de conformidade, acesso total a chats, chamadas e reuniões.</span><span class="sxs-lookup"><span data-stu-id="f8c24-126">Creates a set of policies and policy settings that give information workers such as IT personnel, informatics staff, finance personnel, and compliance officers, full access to chat, calling, and meetings.</span></span>|
|<span data-ttu-id="f8c24-127">Sala de pacientes de assistência médica</span><span class="sxs-lookup"><span data-stu-id="f8c24-127">Healthcare patient room</span></span>  |<span data-ttu-id="f8c24-128">Dispositivos da sala de pacientes</span><span class="sxs-lookup"><span data-stu-id="f8c24-128">Patient room devices</span></span>|<span data-ttu-id="f8c24-129">Cria um conjunto de políticas e configurações de política que se aplicam a salas de pacientes em sua organização de assistência médica.</span><span class="sxs-lookup"><span data-stu-id="f8c24-129">Creates a set of policies and policy settings that apply to patient rooms in your healthcare organization.</span></span>|

![Captura de tela dos pacotes de política da assistência médica](media/policy-packages-healthcare.png)

<span data-ttu-id="f8c24-131">Cada política individual recebe o nome do pacote de política para que você possa facilmente identificar as políticas que estão vinculadas a um pacote de política.</span><span class="sxs-lookup"><span data-stu-id="f8c24-131">Each individual policy is given the name of the policy package so you can easily identify the policies that are linked to a policy package.</span></span> <span data-ttu-id="f8c24-132">Por exemplo, quando você atribui o pacote de política do funcionário clínico à assistência médica a clínicos em sua organização, uma política chamada Healthcare_ClinicalWorker é criada para cada política do pacote.</span><span class="sxs-lookup"><span data-stu-id="f8c24-132">For example, when you assign the Healthcare clinical worker policy package to clinicians in your organization, a policy named Healthcare_ClinicalWorker is created for each policy in the package.</span></span>

![Captura de tela de políticas no pacote de trabalho clínico da assistência médica](media/policy-packages-healthcare-clinical-worker.png)

## <a name="manage-policy-packages"></a><span data-ttu-id="f8c24-134">Gerenciar pacotes de política</span><span class="sxs-lookup"><span data-stu-id="f8c24-134">Manage policy packages</span></span>

### <a name="view"></a><span data-ttu-id="f8c24-135">View</span><span class="sxs-lookup"><span data-stu-id="f8c24-135">View</span></span>

<span data-ttu-id="f8c24-136">Exiba as configurações de cada política em um pacote de política antes de atribuir um pacote.</span><span class="sxs-lookup"><span data-stu-id="f8c24-136">View the settings of each policy in a policy package before you assign a package.</span></span> <span data-ttu-id="f8c24-137">Na navegação à esquerda do centro de administração do Microsoft Teams, selecione **pacotes de política**, selecione o nome do pacote e, em seguida, selecione o nome da política.</span><span class="sxs-lookup"><span data-stu-id="f8c24-137">In the left navigation of the Microsoft Teams admin center, select **Policy packages**, select the package name, and then select the policy name.</span></span>

<span data-ttu-id="f8c24-138">Decida se os valores predefinidos são adequados para sua organização ou se você precisa personalizá-los para serem mais restritivos ou lenient com base nas necessidades da sua organização.</span><span class="sxs-lookup"><span data-stu-id="f8c24-138">Decide whether the predefined values are appropriate for your organization or whether you need to customize them to be more restrictive or lenient based on your organization's needs.</span></span>

### <a name="customize"></a><span data-ttu-id="f8c24-139">Personalizar</span><span class="sxs-lookup"><span data-stu-id="f8c24-139">Customize</span></span>

<span data-ttu-id="f8c24-140">Personalize as configurações das políticas no pacote de política, conforme necessário, para atender às necessidades da sua organização.</span><span class="sxs-lookup"><span data-stu-id="f8c24-140">Customize the settings of policies in the policy package, as needed, to fit the needs of your organization.</span></span> <span data-ttu-id="f8c24-141">Todas as alterações feitas nas configurações de política são automaticamente aplicadas a usuários atribuídos ao pacote.</span><span class="sxs-lookup"><span data-stu-id="f8c24-141">Any changes you make to policy settings are automatically applied to users who are assigned the package.</span></span> <span data-ttu-id="f8c24-142">Para editar as configurações de uma política em um pacote de política, no centro de administração do Microsoft Teams, selecione o pacote de política, selecione o nome da política que você deseja editar e, em seguida, selecione **Editar**.</span><span class="sxs-lookup"><span data-stu-id="f8c24-142">To edit the settings of a policy in a policy package, in the Microsoft Teams admin center, select the policy package, select the name of the policy you want to edit, and then select **Edit**.</span></span>

<span data-ttu-id="f8c24-143">Lembre-se de que você também pode alterar as configurações de políticas em um pacote após atribuir o pacote de política.</span><span class="sxs-lookup"><span data-stu-id="f8c24-143">Keep in mind that you can also change the settings of policies in a package after you assign the policy package.</span></span> <span data-ttu-id="f8c24-144">Para saber mais, consulte [Personalizar políticas em um pacote de política](manage-policy-packages.md#customize-policies-in-a-policy-package).</span><span class="sxs-lookup"><span data-stu-id="f8c24-144">To learn more, see [Customize policies in a policy package](manage-policy-packages.md#customize-policies-in-a-policy-package).</span></span> 

### <a name="assign"></a><span data-ttu-id="f8c24-145">Atribuição</span><span class="sxs-lookup"><span data-stu-id="f8c24-145">Assign</span></span>

<span data-ttu-id="f8c24-146">Atribua o pacote de política aos usuários.</span><span class="sxs-lookup"><span data-stu-id="f8c24-146">Assign the policy package to users.</span></span> <span data-ttu-id="f8c24-147">Para atribuir um pacote de política a um ou vários usuários, clique em **gerenciar usuários**.</span><span class="sxs-lookup"><span data-stu-id="f8c24-147">To assign a policy package to one or multiple users, click **Manage users**.</span></span> <span data-ttu-id="f8c24-148">Você também pode usar o PowerShell para atribuir um pacote de política a lotes grandes de usuários.</span><span class="sxs-lookup"><span data-stu-id="f8c24-148">You can also use PowerShell to assign a policy package to large batches of users.</span></span> <span data-ttu-id="f8c24-149">Para ver as etapas sobre como atribuir um pacote de política, consulte [atribuir um pacote de política](manage-policy-packages.md#assign-a-policy-package).</span><span class="sxs-lookup"><span data-stu-id="f8c24-149">For steps on how to assign a policy package, see [Assign a policy package](manage-policy-packages.md#assign-a-policy-package).</span></span>

![Captura de tela de como atribuir um pacote de política no centro de administração](media/policy-packages-healthcare-assign.png)

<span data-ttu-id="f8c24-151">Se um usuário tiver uma política atribuída e depois você atribuir uma política diferente, a atribuição mais recente terá prioridade.</span><span class="sxs-lookup"><span data-stu-id="f8c24-151">If a user has a policy assigned, and then later you assign a different policy, the most recent assignment will take priority.</span></span>

## <a name="related-topics"></a><span data-ttu-id="f8c24-152">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="f8c24-152">Related topics</span></span>

[<span data-ttu-id="f8c24-153">Gerenciar pacotes de política em equipes</span><span class="sxs-lookup"><span data-stu-id="f8c24-153">Manage policy packages in Teams</span></span>](manage-policy-packages.md)

[<span data-ttu-id="f8c24-154">Atribuir políticas a seus usuários no Teams</span><span class="sxs-lookup"><span data-stu-id="f8c24-154">Assign policies to your users in Teams</span></span>](assign-policies.md)
