---
title: Gerenciar pacotes de política no Microsoft Teams
author: lanachin
ms.author: v-lanac
manager: serdars
ms.reviewer: sekrantz
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
f1keywords: ms.teamsadmincenter.policypackages.overview
localization_priority: Normal
search.appverid: MET150
description: Saiba como usar e gerenciar pacotes de política no Microsoft Teams.
ms.openlocfilehash: fb01a7e15d43c18e115ecfbd0edb73b4808c2a59
ms.sourcegitcommit: 30b4b979e20066253e32ab9e44d79c48a97e6211
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/05/2019
ms.locfileid: "37972432"
---
# <a name="manage-policy-packages-in-microsoft-teams"></a><span data-ttu-id="b1e0b-103">Gerenciar pacotes de política no Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="b1e0b-103">Manage policy packages in Microsoft Teams</span></span>

<span data-ttu-id="b1e0b-104">Um pacote de política no Microsoft Teams é uma coleção de políticas predefinidas e configurações de política que você pode atribuir aos usuários que têm funções semelhantes em sua organização.</span><span class="sxs-lookup"><span data-stu-id="b1e0b-104">A policy package in Microsoft Teams is a collection of predefined policies and policy settings that you can assign to users who have similar roles in your organization.</span></span> <span data-ttu-id="b1e0b-105">Nós criamos pacotes de políticas para simplificar, simplificar e ajudar a fornecer consistência ao gerenciar políticas para grupos de usuários em toda a sua organização.</span><span class="sxs-lookup"><span data-stu-id="b1e0b-105">We built policy packages to simplify, streamline, and help provide consistency when managing policies for groups of users across your organization.</span></span>  

<span data-ttu-id="b1e0b-106">Quando você atribui um pacote de política aos usuários, as políticas no pacote são criadas e você pode personalizar as configurações das políticas do pacote para atender às necessidades da sua organização.</span><span class="sxs-lookup"><span data-stu-id="b1e0b-106">When you assign a policy package to users, the policies in the package are created and you can then customize the settings of the policies in the package to meet your organization's needs.</span></span>

## <a name="what-is-a-policy-package"></a><span data-ttu-id="b1e0b-107">O que é um pacote de política?</span><span class="sxs-lookup"><span data-stu-id="b1e0b-107">What is a policy package?</span></span>

<span data-ttu-id="b1e0b-108">Os pacotes de política permitem controlar os recursos da equipe que você deseja permitir ou restringir para conjuntos específicos de pessoas em toda a organização.</span><span class="sxs-lookup"><span data-stu-id="b1e0b-108">Policy packages let you control Teams features that you want to allow or restrict for specific sets of people across your organization.</span></span> <span data-ttu-id="b1e0b-109">Cada pacote de política no Teams é projetado em torno de uma função de usuário e inclui políticas predefinidas e configurações de política que dão suporte a atividades de colaboração e comunicação que são típicas para essa função.</span><span class="sxs-lookup"><span data-stu-id="b1e0b-109">Each policy package in Teams is designed around a user role and includes predefined policies and policy settings that support the collaboration and communication activities that are typical for that role.</span></span>

<span data-ttu-id="b1e0b-110">Atualmente, o Microsoft Teams inclui os seguintes pacotes de política.</span><span class="sxs-lookup"><span data-stu-id="b1e0b-110">Teams currently includes the following policy packages.</span></span>

|<span data-ttu-id="b1e0b-111">**Nome do pacote**</span><span class="sxs-lookup"><span data-stu-id="b1e0b-111">**Package name**</span></span>  |<span data-ttu-id="b1e0b-112">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="b1e0b-112">**Description**</span></span> |
|---------|---------|
|<span data-ttu-id="b1e0b-113">Pacote Education_Teacher</span><span class="sxs-lookup"><span data-stu-id="b1e0b-113">Education_Teacher package</span></span>     |<span data-ttu-id="b1e0b-114">Cria um conjunto de políticas e configurações de política que se aplicam a professores.</span><span class="sxs-lookup"><span data-stu-id="b1e0b-114">Creates a set of policies and policy settings that apply to teachers.</span></span>      |
|<span data-ttu-id="b1e0b-115">Pacote Education_PrimaryStudent</span><span class="sxs-lookup"><span data-stu-id="b1e0b-115">Education_PrimaryStudent package</span></span>    |<span data-ttu-id="b1e0b-116">Cria um conjunto de políticas e configurações de política que se aplicam a alunos principais.</span><span class="sxs-lookup"><span data-stu-id="b1e0b-116">Creates a set of policies and policy settings that apply to primary students.</span></span>|
|<span data-ttu-id="b1e0b-117">Pacote Education_SecondaryStudent</span><span class="sxs-lookup"><span data-stu-id="b1e0b-117">Education_SecondaryStudent package</span></span>    |<span data-ttu-id="b1e0b-118">Cria um conjunto de políticas e configurações de política que se aplicam a alunos secundários.</span><span class="sxs-lookup"><span data-stu-id="b1e0b-118">Creates a set of policies and policy settings that apply to secondary students.</span></span>         |
|<span data-ttu-id="b1e0b-119">Pacote Education_HigherEducationStudent</span><span class="sxs-lookup"><span data-stu-id="b1e0b-119">Education_HigherEducationStudent package</span></span>    |<span data-ttu-id="b1e0b-120">Cria um conjunto de políticas e configurações de política que se aplicam a alunos de ensino superior.</span><span class="sxs-lookup"><span data-stu-id="b1e0b-120">Creates a set of policies and policy settings that apply to higher education students.</span></span>|

> [!NOTE]
> <span data-ttu-id="b1e0b-121">Vamos adicionar mais pacotes de política em lançamentos futuros do Teams, portanto verifique as informações mais atualizadas.</span><span class="sxs-lookup"><span data-stu-id="b1e0b-121">We'll be adding more policy packages in future releases of Teams, so check back for the most up-to-date information.</span></span>  

<span data-ttu-id="b1e0b-122">Cada política individual recebe o nome do pacote de política para que você possa facilmente identificar as políticas que estão vinculadas a um pacote de política.</span><span class="sxs-lookup"><span data-stu-id="b1e0b-122">Each individual policy is given the name of the policy package so you can easily identify the policies that are linked to a policy package.</span></span>
<span data-ttu-id="b1e0b-123">Por exemplo, quando você atribui o pacote de política de Education_Teacher a professores em sua escola, uma política nomeada Education_Teacher é criada para cada política no pacote.</span><span class="sxs-lookup"><span data-stu-id="b1e0b-123">For example, when you assign the Education_Teacher policy package to teachers in your school, a policy that's named Education_Teacher is created for each policy in the package.</span></span>

![Captura de tela do pacote da política Education_Teacher](media/policy-packages-education_teacher.png)

## <a name="how-to-use-policy-packages"></a><span data-ttu-id="b1e0b-125">Como usar pacotes de política</span><span class="sxs-lookup"><span data-stu-id="b1e0b-125">How to use policy packages</span></span>

<span data-ttu-id="b1e0b-126">O seguinte descreve como usar pacotes de política em sua organização.</span><span class="sxs-lookup"><span data-stu-id="b1e0b-126">The following outlines how to use policy packages in your organization.</span></span>

![Visão geral de como usar pacotes de política](media/manage-policy-packages-overview.png)

- <span data-ttu-id="b1e0b-128">**[Exibir](#view-the-settings-of-a-policy-in-a-policy-package)**: exibir as configurações de cada política em um pacote de política antes de atribuir um pacote.</span><span class="sxs-lookup"><span data-stu-id="b1e0b-128">**[View](#view-the-settings-of-a-policy-in-a-policy-package)**: View the settings of each policy in a policy package before you assign a package.</span></span> <span data-ttu-id="b1e0b-129">Certifique-se de que você compreende cada configuração e, em seguida, decida se os valores predefinidos são adequados para a sua organização ou se é necessário alterá-los para serem mais restritivos ou lenient com base nas necessidades da sua organização.</span><span class="sxs-lookup"><span data-stu-id="b1e0b-129">Make sure that you understand each setting and then decide whether the predefined values are appropriate for your organization or whether you need to change them to be more restrictive or lenient based on your organization's needs.</span></span>

    <span data-ttu-id="b1e0b-130">Se uma política for excluída, ainda será possível exibir as configurações, mas você não poderá alterar as configurações.</span><span class="sxs-lookup"><span data-stu-id="b1e0b-130">If a policy is deleted, you can still view the settings but you won't be able to change any settings.</span></span> <span data-ttu-id="b1e0b-131">Uma política excluída é recriada com as configurações predefinidas ao atribuir o pacote de política.</span><span class="sxs-lookup"><span data-stu-id="b1e0b-131">A deleted policy is re-created with the predefined settings when you assign the policy package.</span></span>

- <span data-ttu-id="b1e0b-132">**[Atribuir](#assign-a-policy-package)**: atribuir o pacote de política aos usuários.</span><span class="sxs-lookup"><span data-stu-id="b1e0b-132">**[Assign](#assign-a-policy-package)**: Assign the policy package to users.</span></span> <span data-ttu-id="b1e0b-133">Lembre-se de que as políticas em um pacote de política não são criadas até você atribuir o pacote, após o qual você pode alterar as configurações de políticas individuais no pacote.</span><span class="sxs-lookup"><span data-stu-id="b1e0b-133">Remember that policies in a policy package aren't created until you assign the package, after which you can change the settings of individual policies in the package.</span></span>  

- <span data-ttu-id="b1e0b-134">**[Personalizar](#customize-policies-in-a-policy-package)**: personalizar as configurações das políticas no pacote de políticas para atender às necessidades da sua organização.</span><span class="sxs-lookup"><span data-stu-id="b1e0b-134">**[Customize](#customize-policies-in-a-policy-package)**: Customize the settings of policies in the policy package to fit the needs of your organization.</span></span> <span data-ttu-id="b1e0b-135">Todas as alterações feitas nas configurações de política são automaticamente aplicadas a usuários atribuídos ao pacote.</span><span class="sxs-lookup"><span data-stu-id="b1e0b-135">Any changes you make to policy settings are automatically applied to users who are assigned the package.</span></span>

<span data-ttu-id="b1e0b-136">Veja a seguir as etapas sobre como exibir, atribuir e personalizar pacotes de política no centro de administração do Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="b1e0b-136">Here are the steps for how to view, assign, and customize policy packages in the Microsoft Teams admin center.</span></span>

### <a name="view-the-settings-of-a-policy-in-a-policy-package"></a><span data-ttu-id="b1e0b-137">Exibir as configurações de uma política em um pacote de política</span><span class="sxs-lookup"><span data-stu-id="b1e0b-137">View the settings of a policy in a policy package</span></span>

1. <span data-ttu-id="b1e0b-138">Na navegação à esquerda do centro de administração do Microsoft Teams, clique em **pacotes de política**e selecione um pacote de política clicando à esquerda do nome do pacote.</span><span class="sxs-lookup"><span data-stu-id="b1e0b-138">In the left navigation of the Microsoft Teams admin center, click **Policy packages**, and then select a policy package by clicking to the left of the package name.</span></span>
2. <span data-ttu-id="b1e0b-139">Clique na política que você deseja exibir.</span><span class="sxs-lookup"><span data-stu-id="b1e0b-139">Click the policy you want to view.</span></span>

### <a name="assign-a-policy-package"></a><span data-ttu-id="b1e0b-140">Atribuir um pacote de política</span><span class="sxs-lookup"><span data-stu-id="b1e0b-140">Assign a policy package</span></span>

#### <a name="assign-a-policy-package-to-one-user"></a><span data-ttu-id="b1e0b-141">Atribuir um pacote de política a um usuário</span><span class="sxs-lookup"><span data-stu-id="b1e0b-141">Assign a policy package to one user</span></span>

1. <span data-ttu-id="b1e0b-142">Na navegação à esquerda do centro de administração do Microsoft Teams, vá para **usuários**e, em seguida, clique no usuário.</span><span class="sxs-lookup"><span data-stu-id="b1e0b-142">In the left navigation of the Microsoft Teams admin center, go to **Users**, and then click the user.</span></span>
2. <span data-ttu-id="b1e0b-143">Na página do usuário, clique em **políticas**e, em seguida, ao lado de **pacote de política**, clique em **Editar**.</span><span class="sxs-lookup"><span data-stu-id="b1e0b-143">On the user's page, click **Policies**, and then next to **Policy package**, click **Edit**.</span></span>
3. <span data-ttu-id="b1e0b-144">No painel **atribuir pacote de política** , selecione o pacote que você deseja atribuir e clique em **salvar**.</span><span class="sxs-lookup"><span data-stu-id="b1e0b-144">In the **Assign policy package** pane, select the package you want to assign, and then click **Save**.</span></span>

#### <a name="assign-a-policy-package-to-multiple-users"></a><span data-ttu-id="b1e0b-145">Atribuir um pacote de política a vários usuários</span><span class="sxs-lookup"><span data-stu-id="b1e0b-145">Assign a policy package to multiple users</span></span>

1. <span data-ttu-id="b1e0b-146">Na navegação à esquerda do centro de administração do Microsoft Teams, vá para **pacotes de política**e, em seguida, selecione o pacote de política que você deseja atribuir clicando à esquerda do nome do pacote.</span><span class="sxs-lookup"><span data-stu-id="b1e0b-146">In the left navigation of the Microsoft Teams admin center, go to **Policy packages**, and then select the policy package you want to assign by clicking to the left of the package name.</span></span>
2. <span data-ttu-id="b1e0b-147">Clique em **gerenciar usuários**.</span><span class="sxs-lookup"><span data-stu-id="b1e0b-147">Click **Manage users**.</span></span>
3. <span data-ttu-id="b1e0b-148">No painel **gerenciar usuários** , procure pelo usuário por nome para exibição ou por nome de usuário, selecione o nome e clique em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="b1e0b-148">In the **Manage users** pane, search for the user by display name or by user name, select the name, and then click **Add**.</span></span> <span data-ttu-id="b1e0b-149">Repita esta etapa para cada usuário que você deseja adicionar.</span><span class="sxs-lookup"><span data-stu-id="b1e0b-149">Repeat this step for each user that you want to add.</span></span>
4. <span data-ttu-id="b1e0b-150">Quando tiver terminado de adicionar usuários, clique em **salvar**.</span><span class="sxs-lookup"><span data-stu-id="b1e0b-150">When you're finished adding users, click **Save**.</span></span>

### <a name="customize-policies-in-a-policy-package"></a><span data-ttu-id="b1e0b-151">Personalizar políticas em um pacote de política</span><span class="sxs-lookup"><span data-stu-id="b1e0b-151">Customize policies in a policy package</span></span>

<span data-ttu-id="b1e0b-152">Você pode editar as configurações de uma política por meio da página **pacotes de política** ou indo diretamente para a página política no centro de administração do Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="b1e0b-152">You can edit the settings of a policy through the **Policy packages** page or by going directly to the policy page in the Microsoft Teams admin center.</span></span>

1. <span data-ttu-id="b1e0b-153">Na navegação à esquerda do centro de administração do Microsoft Teams, siga um destes procedimentos:</span><span class="sxs-lookup"><span data-stu-id="b1e0b-153">In the left navigation of the Microsoft Teams admin center, do one of the following:</span></span>
    - <span data-ttu-id="b1e0b-154">Clique em **pacotes de política**e selecione o pacote de política clicando à esquerda do nome do pacote.</span><span class="sxs-lookup"><span data-stu-id="b1e0b-154">Click **Policy packages**, and then select the policy package by clicking to the left of the package name.</span></span>
    - <span data-ttu-id="b1e0b-155">Clique no tipo de política.</span><span class="sxs-lookup"><span data-stu-id="b1e0b-155">Click the policy type.</span></span>  <span data-ttu-id="b1e0b-156">Por exemplo, clique em **políticas de mensagens**.</span><span class="sxs-lookup"><span data-stu-id="b1e0b-156">For example, click **Messaging policies**.</span></span>
2. <span data-ttu-id="b1e0b-157">Clique na política que você deseja editar.</span><span class="sxs-lookup"><span data-stu-id="b1e0b-157">Click the policy you want to edit.</span></span> <span data-ttu-id="b1e0b-158">As políticas vinculadas a um pacote de política têm o mesmo nome que o pacote de política.</span><span class="sxs-lookup"><span data-stu-id="b1e0b-158">Policies that are linked to a policy package have the same name as the policy package.</span></span>
3. <span data-ttu-id="b1e0b-159">Faça as alterações desejadas e clique em **salvar**.</span><span class="sxs-lookup"><span data-stu-id="b1e0b-159">Make the changes that you want, and then click **Save**.</span></span>

## <a name="troubleshooting"></a><span data-ttu-id="b1e0b-160">Solução de problemas</span><span class="sxs-lookup"><span data-stu-id="b1e0b-160">Troubleshooting</span></span>

<span data-ttu-id="b1e0b-161">**Você recebe um erro ao atribuir um pacote de política**</span><span class="sxs-lookup"><span data-stu-id="b1e0b-161">**You receive an error when you assign a policy package**</span></span>

<span data-ttu-id="b1e0b-162">Isso pode ocorrer se uma ou mais políticas do pacote não foram criadas ou aplicadas com sucesso.</span><span class="sxs-lookup"><span data-stu-id="b1e0b-162">This may occur if one or more policies in the package weren't created or applied successfully.</span></span> <span data-ttu-id="b1e0b-163">Reatribuir o pacote de política para seus usuários.</span><span class="sxs-lookup"><span data-stu-id="b1e0b-163">Reassign the policy package to your users.</span></span> <span data-ttu-id="b1e0b-164">Repetir a operação normalmente corrige esse problema.</span><span class="sxs-lookup"><span data-stu-id="b1e0b-164">Retrying the operation typically fixes this issue.</span></span>
