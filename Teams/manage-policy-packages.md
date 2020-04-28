---
title: Gerenciar pacotes de política no Microsoft Teams
author: lanachin
ms.author: v-lanac
manager: serdars
ms.reviewer: sekrantz, aaglick
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.policypackages.overview
- seo-marvel-apr2020
localization_priority: Normal
search.appverid: MET150
description: Saiba como usar e gerenciar pacotes de política no Microsoft Teams para simplificar, simplificar e ajudar a fornecer consistência ao gerenciar políticas para grupos de usuários.
ms.openlocfilehash: b69ce06d01af624ff73386531d7ef2b77bef3b4e
ms.sourcegitcommit: a9e16aa3539103f3618427ffc7ebbda6919b5176
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/27/2020
ms.locfileid: "43914049"
---
# <a name="manage-policy-packages-in-microsoft-teams"></a><span data-ttu-id="fedce-103">Gerenciar pacotes de política no Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="fedce-103">Manage policy packages in Microsoft Teams</span></span>

<span data-ttu-id="fedce-104">Um pacote de política no Microsoft Teams é uma coleção de políticas predefinidas e configurações de política que você pode atribuir aos usuários que têm funções semelhantes em sua organização.</span><span class="sxs-lookup"><span data-stu-id="fedce-104">A policy package in Microsoft Teams is a collection of predefined policies and policy settings that you can assign to users who have similar roles in your organization.</span></span> <span data-ttu-id="fedce-105">Nós criamos pacotes de políticas para simplificar, simplificar e ajudar a fornecer consistência ao gerenciar políticas para grupos de usuários em toda a sua organização.</span><span class="sxs-lookup"><span data-stu-id="fedce-105">We built policy packages to simplify, streamline, and help provide consistency when managing policies for groups of users across your organization.</span></span>  

<span data-ttu-id="fedce-106">Quando você atribui um pacote de política aos usuários, as políticas no pacote são criadas e você pode personalizar as configurações das políticas do pacote para atender às necessidades da sua organização.</span><span class="sxs-lookup"><span data-stu-id="fedce-106">When you assign a policy package to users, the policies in the package are created and you can then customize the settings of the policies in the package to meet your organization's needs.</span></span>

<span data-ttu-id="fedce-107">Os pacotes de política não estão disponíveis para organizações da comunidade de nuvens (GCC) do governo dos EUA.</span><span class="sxs-lookup"><span data-stu-id="fedce-107">Policy packages aren't available for US Government Cloud Community (GCC) organizations.</span></span>

## <a name="what-is-a-policy-package"></a><span data-ttu-id="fedce-108">O que é um pacote de política?</span><span class="sxs-lookup"><span data-stu-id="fedce-108">What is a policy package?</span></span>

<span data-ttu-id="fedce-109">Os pacotes de política permitem controlar os recursos da equipe que você deseja permitir ou restringir para conjuntos específicos de pessoas em toda a organização.</span><span class="sxs-lookup"><span data-stu-id="fedce-109">Policy packages let you control Teams features that you want to allow or restrict for specific sets of people across your organization.</span></span> <span data-ttu-id="fedce-110">Cada pacote de política no Teams é projetado em torno de uma função de usuário e inclui políticas predefinidas e configurações de política que dão suporte a atividades de colaboração e comunicação que são típicas para essa função.</span><span class="sxs-lookup"><span data-stu-id="fedce-110">Each policy package in Teams is designed around a user role and includes predefined policies and policy settings that support the collaboration and communication activities that are typical for that role.</span></span>

<span data-ttu-id="fedce-111">Atualmente, o Microsoft Teams inclui os seguintes pacotes de política.</span><span class="sxs-lookup"><span data-stu-id="fedce-111">Teams currently includes the following policy packages.</span></span>

|<span data-ttu-id="fedce-112">**Nome do pacote**</span><span class="sxs-lookup"><span data-stu-id="fedce-112">**Package name**</span></span>  |<span data-ttu-id="fedce-113">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="fedce-113">**Description**</span></span> |
|---------|---------|
|<span data-ttu-id="fedce-114">Educação (aluno de ensino superior)</span><span class="sxs-lookup"><span data-stu-id="fedce-114">Education (Higher education student)</span></span>    |<span data-ttu-id="fedce-115">Cria um conjunto de políticas e configurações de política que se aplicam a alunos de ensino superior.</span><span class="sxs-lookup"><span data-stu-id="fedce-115">Creates a set of policies and policy settings that apply to higher education students.</span></span>|
|<span data-ttu-id="fedce-116">Educação (aluno da escola principal)</span><span class="sxs-lookup"><span data-stu-id="fedce-116">Education (Primary school student)</span></span>   |<span data-ttu-id="fedce-117">Cria um conjunto de políticas e configurações de política que se aplicam a alunos principais.</span><span class="sxs-lookup"><span data-stu-id="fedce-117">Creates a set of policies and policy settings that apply to primary students.</span></span>|
|<span data-ttu-id="fedce-118">Educação (aluno escolar secundário)</span><span class="sxs-lookup"><span data-stu-id="fedce-118">Education (Secondary school student)</span></span>    |<span data-ttu-id="fedce-119">Cria um conjunto de políticas e configurações de política que se aplicam a alunos secundários.</span><span class="sxs-lookup"><span data-stu-id="fedce-119">Creates a set of policies and policy settings that apply to secondary students.</span></span>         |
|<span data-ttu-id="fedce-120">Educação (professor)</span><span class="sxs-lookup"><span data-stu-id="fedce-120">Education (Teacher)</span></span>    |<span data-ttu-id="fedce-121">Cria um conjunto de políticas e configurações de política que se aplicam a professores.</span><span class="sxs-lookup"><span data-stu-id="fedce-121">Creates a set of policies and policy settings that apply to teachers.</span></span>      |
|<span data-ttu-id="fedce-122">Usuário para empresas de pequeno e médio porte (Business Voice)</span><span class="sxs-lookup"><span data-stu-id="fedce-122">Small and medium business user (Business Voice)</span></span> |<span data-ttu-id="fedce-123">Cria uma política de configuração de aplicativo que inclui os aplicativos para uma experiência de voz empresarial.</span><span class="sxs-lookup"><span data-stu-id="fedce-123">Creates an app setup policy that includes the apps for a business voice experience.</span></span>|
|<span data-ttu-id="fedce-124">Usuário para empresas de pequeno e médio porte (sem Business Voice)</span><span class="sxs-lookup"><span data-stu-id="fedce-124">Small and medium business user (without Business Voice)</span></span> |<span data-ttu-id="fedce-125">Este pacote de política foi projetado para criar um conjunto de políticas e aplicar essas configurações a usuários de empresas de pequeno e médio porte sem nenhum recurso de voz comercial.</span><span class="sxs-lookup"><span data-stu-id="fedce-125">This policy package is designed to create a set of policies and apply those settings to small and medium sized business users without any Business Voice features.</span></span>|
|<span data-ttu-id="fedce-126">Diretor de segurança pública</span><span class="sxs-lookup"><span data-stu-id="fedce-126">Public safety officer</span></span>   |<span data-ttu-id="fedce-127">Cria um conjunto de políticas e configurações de política que se aplicam a órgãos públicos de segurança em sua organização.</span><span class="sxs-lookup"><span data-stu-id="fedce-127">Creates a set of policies and policy settings that apply to public safety officers in your organization.</span></span>|
|<span data-ttu-id="fedce-128">Assistência médica (funcionário clínico)</span><span class="sxs-lookup"><span data-stu-id="fedce-128">Healthcare (Clinical worker)</span></span>  |<span data-ttu-id="fedce-129">Cria um conjunto de políticas e configurações de política que dão a funcionários clínicos, como as mensagens de mão registradas, recarga de mão, médicos e funcionários sociais acesso total a chats, chamadas, gerenciamento de turnos e reuniões.</span><span class="sxs-lookup"><span data-stu-id="fedce-129">Creates a set of policies and policy settings that give clinical workers such as registered nurses, charge nurses, physicians, and social workers full access to chat, calling, shift management, and meetings.</span></span> |
|<span data-ttu-id="fedce-130">Assistência médica (operador de informações)</span><span class="sxs-lookup"><span data-stu-id="fedce-130">Healthcare (Information worker)</span></span>  |<span data-ttu-id="fedce-131">Cria um conjunto de políticas e configurações de política que fornecem aos operadores de informações, como pessoal de ti, pessoal de informática, pessoal de finanças e órgãos de conformidade, acesso total a chats, chamadas e reuniões.</span><span class="sxs-lookup"><span data-stu-id="fedce-131">Creates a set of policies and policy settings that give information workers such as IT personnel, informatics staff, finance personnel, and compliance officers, full access to chat, calling, and meetings.</span></span>|


> [!NOTE]
> <span data-ttu-id="fedce-132">Vamos adicionar mais pacotes de política em lançamentos futuros do Teams, portanto verifique as informações mais atualizadas.</span><span class="sxs-lookup"><span data-stu-id="fedce-132">We'll be adding more policy packages in future releases of Teams, so check back for the most up-to-date information.</span></span>  

<span data-ttu-id="fedce-133">Cada política individual recebe o nome do pacote de política para que você possa facilmente identificar as políticas que estão vinculadas a um pacote de política.</span><span class="sxs-lookup"><span data-stu-id="fedce-133">Each individual policy is given the name of the policy package so you can easily identify the policies that are linked to a policy package.</span></span>
<span data-ttu-id="fedce-134">Por exemplo, quando você atribui o pacote de política de formação educacional (professor) a professores em sua escola, uma política nomeada Education_Teacher é criada para cada política do pacote.</span><span class="sxs-lookup"><span data-stu-id="fedce-134">For example, when you assign the Education (Teacher) policy package to teachers in your school, a policy that's named Education_Teacher is created for each policy in the package.</span></span>

![Captura de tela do pacote de política de educação (professor)](media/policy-packages-education_teacher.png)

## <a name="how-to-use-policy-packages"></a><span data-ttu-id="fedce-136">Como usar pacotes de política</span><span class="sxs-lookup"><span data-stu-id="fedce-136">How to use policy packages</span></span>

<span data-ttu-id="fedce-137">O seguinte descreve como usar pacotes de política em sua organização.</span><span class="sxs-lookup"><span data-stu-id="fedce-137">The following outlines how to use policy packages in your organization.</span></span>

![Visão geral de como usar pacotes de política](media/manage-policy-packages-overview.png)

- <span data-ttu-id="fedce-139">**[Exibir](#view-the-settings-of-a-policy-in-a-policy-package)**: exibir as configurações de cada política em um pacote de política antes de atribuir um pacote.</span><span class="sxs-lookup"><span data-stu-id="fedce-139">**[View](#view-the-settings-of-a-policy-in-a-policy-package)**: View the settings of each policy in a policy package before you assign a package.</span></span> <span data-ttu-id="fedce-140">Certifique-se de que você compreende cada configuração e, em seguida, decida se os valores predefinidos são adequados para a sua organização ou se é necessário alterá-los para serem mais restritivos ou lenient com base nas necessidades da sua organização.</span><span class="sxs-lookup"><span data-stu-id="fedce-140">Make sure that you understand each setting and then decide whether the predefined values are appropriate for your organization or whether you need to change them to be more restrictive or lenient based on your organization's needs.</span></span>

    <span data-ttu-id="fedce-141">Se uma política for excluída, ainda será possível exibir as configurações, mas você não poderá alterar as configurações.</span><span class="sxs-lookup"><span data-stu-id="fedce-141">If a policy is deleted, you can still view the settings but you won't be able to change any settings.</span></span> <span data-ttu-id="fedce-142">Uma política excluída é recriada com as configurações predefinidas ao atribuir o pacote de política.</span><span class="sxs-lookup"><span data-stu-id="fedce-142">A deleted policy is re-created with the predefined settings when you assign the policy package.</span></span>

- <span data-ttu-id="fedce-143">**[Atribuir](#assign-a-policy-package)**: atribuir o pacote de política aos usuários.</span><span class="sxs-lookup"><span data-stu-id="fedce-143">**[Assign](#assign-a-policy-package)**: Assign the policy package to users.</span></span> <span data-ttu-id="fedce-144">Lembre-se de que as políticas em um pacote de política não são criadas até você atribuir o pacote, após o qual você pode alterar as configurações de políticas individuais no pacote.</span><span class="sxs-lookup"><span data-stu-id="fedce-144">Remember that policies in a policy package aren't created until you assign the package, after which you can change the settings of individual policies in the package.</span></span>  

- <span data-ttu-id="fedce-145">**[Personalizar](#customize-policies-in-a-policy-package)**: personalizar as configurações das políticas no pacote de políticas para atender às necessidades da sua organização.</span><span class="sxs-lookup"><span data-stu-id="fedce-145">**[Customize](#customize-policies-in-a-policy-package)**: Customize the settings of policies in the policy package to fit the needs of your organization.</span></span> <span data-ttu-id="fedce-146">Todas as alterações feitas nas configurações de política são automaticamente aplicadas a usuários atribuídos ao pacote.</span><span class="sxs-lookup"><span data-stu-id="fedce-146">Any changes you make to policy settings are automatically applied to users who are assigned the package.</span></span>

<span data-ttu-id="fedce-147">Veja a seguir as etapas sobre como exibir, atribuir e personalizar pacotes de política no centro de administração do Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="fedce-147">Here are the steps for how to view, assign, and customize policy packages in the Microsoft Teams admin center.</span></span>

### <a name="view-the-settings-of-a-policy-in-a-policy-package"></a><span data-ttu-id="fedce-148">Exibir as configurações de uma política em um pacote de política</span><span class="sxs-lookup"><span data-stu-id="fedce-148">View the settings of a policy in a policy package</span></span>

1. <span data-ttu-id="fedce-149">Na navegação à esquerda do centro de administração do Microsoft Teams, clique em **pacotes de política**e selecione um pacote de política clicando à esquerda do nome do pacote.</span><span class="sxs-lookup"><span data-stu-id="fedce-149">In the left navigation of the Microsoft Teams admin center, click **Policy packages**, and then select a policy package by clicking to the left of the package name.</span></span>
2. <span data-ttu-id="fedce-150">Clique na política que você deseja exibir.</span><span class="sxs-lookup"><span data-stu-id="fedce-150">Click the policy you want to view.</span></span>

### <a name="assign-a-policy-package"></a><span data-ttu-id="fedce-151">Atribuir um pacote de política</span><span class="sxs-lookup"><span data-stu-id="fedce-151">Assign a policy package</span></span>

#### <a name="assign-a-policy-package-to-one-user"></a><span data-ttu-id="fedce-152">Atribuir um pacote de política a um usuário</span><span class="sxs-lookup"><span data-stu-id="fedce-152">Assign a policy package to one user</span></span>

1. <span data-ttu-id="fedce-153">Na barra de navegação à esquerda do centro de administração do Microsoft Teams, vá para **Usuários** e clique no usuário.</span><span class="sxs-lookup"><span data-stu-id="fedce-153">In the left navigation of the Microsoft Teams admin center, go to **Users**, and then click the user.</span></span>
2. <span data-ttu-id="fedce-154">Na página do usuário, clique em **políticas**e, em seguida, ao lado de **pacote de política**, clique em **Editar**.</span><span class="sxs-lookup"><span data-stu-id="fedce-154">On the user's page, click **Policies**, and then next to **Policy package**, click **Edit**.</span></span>
3. <span data-ttu-id="fedce-155">No painel **atribuir pacote de política** , selecione o pacote que você deseja atribuir e clique em **salvar**.</span><span class="sxs-lookup"><span data-stu-id="fedce-155">In the **Assign policy package** pane, select the package you want to assign, and then click **Save**.</span></span>

#### <a name="assign-a-policy-package-to-multiple-users"></a><span data-ttu-id="fedce-156">Atribuir um pacote de política a vários usuários</span><span class="sxs-lookup"><span data-stu-id="fedce-156">Assign a policy package to multiple users</span></span>

1. <span data-ttu-id="fedce-157">Na navegação à esquerda do centro de administração do Microsoft Teams, vá para **pacotes de política**e, em seguida, selecione o pacote de política que você deseja atribuir clicando à esquerda do nome do pacote.</span><span class="sxs-lookup"><span data-stu-id="fedce-157">In the left navigation of the Microsoft Teams admin center, go to **Policy packages**, and then select the policy package you want to assign by clicking to the left of the package name.</span></span>
2. <span data-ttu-id="fedce-158">Clique em **gerenciar usuários**.</span><span class="sxs-lookup"><span data-stu-id="fedce-158">Click **Manage users**.</span></span>
3. <span data-ttu-id="fedce-159">No painel **Gerenciar usuários**, procure o usuário pelo nome de exibição ou pelo nome de usuário, escolha o nome e clique em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="fedce-159">In the **Manage users** pane, search for the user by display name or by user name, select the name, and then click **Add**.</span></span> <span data-ttu-id="fedce-160">Repita esta etapa para cada usuário que você deseja adicionar.</span><span class="sxs-lookup"><span data-stu-id="fedce-160">Repeat this step for each user that you want to add.</span></span>
4. <span data-ttu-id="fedce-161">Quando tiver terminado de adicionar usuários, clique em **salvar**.</span><span class="sxs-lookup"><span data-stu-id="fedce-161">When you're finished adding users, click **Save**.</span></span>

### <a name="customize-policies-in-a-policy-package"></a><span data-ttu-id="fedce-162">Personalizar políticas em um pacote de política</span><span class="sxs-lookup"><span data-stu-id="fedce-162">Customize policies in a policy package</span></span>

<span data-ttu-id="fedce-163">Você pode editar as configurações de uma política por meio da página **pacotes de política** ou indo diretamente para a página política no centro de administração do Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="fedce-163">You can edit the settings of a policy through the **Policy packages** page or by going directly to the policy page in the Microsoft Teams admin center.</span></span>

1. <span data-ttu-id="fedce-164">Na navegação à esquerda do centro de administração do Microsoft Teams, siga um destes procedimentos:</span><span class="sxs-lookup"><span data-stu-id="fedce-164">In the left navigation of the Microsoft Teams admin center, do one of the following:</span></span>
    - <span data-ttu-id="fedce-165">Clique em **pacotes de política**e selecione o pacote de política clicando à esquerda do nome do pacote.</span><span class="sxs-lookup"><span data-stu-id="fedce-165">Click **Policy packages**, and then select the policy package by clicking to the left of the package name.</span></span>
    - <span data-ttu-id="fedce-166">Clique no tipo de política.</span><span class="sxs-lookup"><span data-stu-id="fedce-166">Click the policy type.</span></span>  <span data-ttu-id="fedce-167">Por exemplo, clique em **políticas de mensagens**.</span><span class="sxs-lookup"><span data-stu-id="fedce-167">For example, click **Messaging policies**.</span></span>
2. <span data-ttu-id="fedce-168">Clique na política que você deseja editar.</span><span class="sxs-lookup"><span data-stu-id="fedce-168">Click the policy you want to edit.</span></span> <span data-ttu-id="fedce-169">As políticas vinculadas a um pacote de política têm o mesmo nome que o pacote de política.</span><span class="sxs-lookup"><span data-stu-id="fedce-169">Policies that are linked to a policy package have the same name as the policy package.</span></span>
3. <span data-ttu-id="fedce-170">Faça as alterações desejadas e clique em **salvar**.</span><span class="sxs-lookup"><span data-stu-id="fedce-170">Make the changes that you want, and then click **Save**.</span></span>

## <a name="troubleshooting"></a><span data-ttu-id="fedce-171">Solução de problemas</span><span class="sxs-lookup"><span data-stu-id="fedce-171">Troubleshooting</span></span>

<span data-ttu-id="fedce-172">**Você recebe um erro ao atribuir um pacote de política**</span><span class="sxs-lookup"><span data-stu-id="fedce-172">**You receive an error when you assign a policy package**</span></span>

<span data-ttu-id="fedce-173">Isso pode ocorrer se uma ou mais políticas do pacote não foram criadas ou aplicadas com sucesso.</span><span class="sxs-lookup"><span data-stu-id="fedce-173">This may occur if one or more policies in the package weren't created or applied successfully.</span></span> <span data-ttu-id="fedce-174">Reatribuir o pacote de política para seus usuários.</span><span class="sxs-lookup"><span data-stu-id="fedce-174">Reassign the policy package to your users.</span></span> <span data-ttu-id="fedce-175">Repetir a operação normalmente corrige esse problema.</span><span class="sxs-lookup"><span data-stu-id="fedce-175">Retrying the operation typically fixes this issue.</span></span>

## <a name="related-topics"></a><span data-ttu-id="fedce-176">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="fedce-176">Related topics</span></span>

[<span data-ttu-id="fedce-177">Pacotes de política do Microsoft Teams para administradores EDU</span><span class="sxs-lookup"><span data-stu-id="fedce-177">Microsoft Teams policy packages for EDU admins</span></span>](policy-packages-edu.md)
