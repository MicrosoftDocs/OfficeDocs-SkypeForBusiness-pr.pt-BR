---
title: Gerenciar pacotes de política no Microsoft Teams
author: cichur
ms.author: v-cichur
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
ms.openlocfilehash: 1173f5a626d6ea559dadd75149a0517f515d821b
ms.sourcegitcommit: cfef9dd41cac0df83bd02b35036d8f8f1b472feb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/13/2021
ms.locfileid: "51699339"
---
# <a name="manage-policy-packages-in-microsoft-teams"></a><span data-ttu-id="d8aac-103">Gerenciar pacotes de política no Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="d8aac-103">Manage policy packages in Microsoft Teams</span></span>

<span data-ttu-id="d8aac-104">Um pacote de política no Microsoft Teams é um conjunto de políticas e configurações de política predefinidas que você pode atribuir a usuários com funções semelhantes em sua organização.</span><span class="sxs-lookup"><span data-stu-id="d8aac-104">A policy package in Microsoft Teams is a collection of predefined policies and policy settings that you can assign to users who have similar roles in your organization.</span></span> <span data-ttu-id="d8aac-105">Construímos pacotes de política para simplificar, simplificar e ajudar a fornecer consistência ao gerenciar políticas para grupos de usuários em toda a sua organização.</span><span class="sxs-lookup"><span data-stu-id="d8aac-105">We built policy packages to simplify, streamline, and help provide consistency when managing policies for groups of users across your organization.</span></span>  

<span data-ttu-id="d8aac-106">Você pode usar os pacotes [de política incluídos no Teams](#policy-packages-included-in-teams) ou criar seus próprios pacotes de política [personalizados.](#custom-policy-packages)</span><span class="sxs-lookup"><span data-stu-id="d8aac-106">You can use the [policy packages included in Teams](#policy-packages-included-in-teams) or [create your own custom policy packages](#custom-policy-packages).</span></span>

:::image type="content" source="media/policy-packages-admin-center.png" alt-text="Captura de tela da página Pacotes de política no centro de administração":::

<span data-ttu-id="d8aac-108">Você pode personalizar as configurações das políticas em um pacote de política para atender às necessidades de seus usuários.</span><span class="sxs-lookup"><span data-stu-id="d8aac-108">You can customize the settings of the policies in a policy package to suit the needs of your users.</span></span> <span data-ttu-id="d8aac-109">Quando você altera as configurações de políticas em um pacote, todos os usuários atribuídos a esse pacote obterão as configurações atualizadas.</span><span class="sxs-lookup"><span data-stu-id="d8aac-109">When you change the settings of policies in a package, all users who are assigned to that package get the updated settings.</span></span> <span data-ttu-id="d8aac-110">Você gerencia pacotes de política usando o Centro de administração do Microsoft Teams ou o PowerShell.</span><span class="sxs-lookup"><span data-stu-id="d8aac-110">You manage policy packages by using the Microsoft Teams admin center or PowerShell.</span></span>

## <a name="what-is-a-policy-package"></a><span data-ttu-id="d8aac-111">O que é um pacote de política?</span><span class="sxs-lookup"><span data-stu-id="d8aac-111">What is a policy package?</span></span>

<span data-ttu-id="d8aac-112">Os pacotes de política permitem que você controle os recursos do Teams que você deseja permitir ou restringir para conjuntos específicos de pessoas em toda a sua organização.</span><span class="sxs-lookup"><span data-stu-id="d8aac-112">Policy packages let you control Teams features that you want to allow or restrict for specific sets of people across your organization.</span></span> <span data-ttu-id="d8aac-113">Cada pacote de política no Teams é projetado em torno de uma função de usuário e inclui políticas predefinidas e configurações de política que suportam as atividades de colaboração e comunicação típicas para essa função.</span><span class="sxs-lookup"><span data-stu-id="d8aac-113">Each policy package in Teams is designed around a user role and includes predefined policies and policy settings that support the collaboration and communication activities that are typical for that role.</span></span>

<span data-ttu-id="d8aac-114">Os pacotes de política suportam os seguintes tipos de política do Teams:</span><span class="sxs-lookup"><span data-stu-id="d8aac-114">Policy packages support the following Teams policy types:</span></span>

- <span data-ttu-id="d8aac-115">Políticas de mensagens</span><span class="sxs-lookup"><span data-stu-id="d8aac-115">Messaging policy</span></span>
- <span data-ttu-id="d8aac-116">Políticas de reunião</span><span class="sxs-lookup"><span data-stu-id="d8aac-116">Meeting policy</span></span>
- <span data-ttu-id="d8aac-117">Política de configuração de aplicativo</span><span class="sxs-lookup"><span data-stu-id="d8aac-117">App setup policy</span></span>
- <span data-ttu-id="d8aac-118">Políticas de chamada</span><span class="sxs-lookup"><span data-stu-id="d8aac-118">Calling policy</span></span>
- <span data-ttu-id="d8aac-119">Políticas de eventos ao vivo</span><span class="sxs-lookup"><span data-stu-id="d8aac-119">Live events policy</span></span>

## <a name="policy-packages-included-in-teams"></a><span data-ttu-id="d8aac-120">Pacotes de política incluídos no Teams</span><span class="sxs-lookup"><span data-stu-id="d8aac-120">Policy packages included in Teams</span></span>

<span data-ttu-id="d8aac-121">Atualmente, o Teams inclui os seguintes pacotes de política.</span><span class="sxs-lookup"><span data-stu-id="d8aac-121">Teams currently includes the following policy packages.</span></span>

| <span data-ttu-id="d8aac-122">Nome do pacote</span><span class="sxs-lookup"><span data-stu-id="d8aac-122">Package name</span></span> | <span data-ttu-id="d8aac-123">Descrição</span><span class="sxs-lookup"><span data-stu-id="d8aac-123">Description</span></span> |
|---------|---------|
|<span data-ttu-id="d8aac-124">Educação (estudante de ensino superior)</span><span class="sxs-lookup"><span data-stu-id="d8aac-124">Education (Higher education student)</span></span>    |<span data-ttu-id="d8aac-125">Cria um conjunto de políticas e configurações de política que se aplicam aos alunos do ensino superior.</span><span class="sxs-lookup"><span data-stu-id="d8aac-125">Creates a set of policies and policy settings that apply to higher education students.</span></span>|
|<span data-ttu-id="d8aac-126">Educação (aluno do primário)</span><span class="sxs-lookup"><span data-stu-id="d8aac-126">Education (Primary school student)</span></span>   |<span data-ttu-id="d8aac-127">Cria um conjunto de políticas e configurações de política que se aplicam aos alunos primários.</span><span class="sxs-lookup"><span data-stu-id="d8aac-127">Creates a set of policies and policy settings that apply to primary students.</span></span>|
|<span data-ttu-id="d8aac-128">Educação (estudante do ensino médio)</span><span class="sxs-lookup"><span data-stu-id="d8aac-128">Education (Secondary school student)</span></span>    |<span data-ttu-id="d8aac-129">Cria um conjunto de políticas e configurações de política que se aplicam a alunos secundários.</span><span class="sxs-lookup"><span data-stu-id="d8aac-129">Creates a set of policies and policy settings that apply to secondary students.</span></span>         |
|<span data-ttu-id="d8aac-130">Educação (Professor)</span><span class="sxs-lookup"><span data-stu-id="d8aac-130">Education (Teacher)</span></span>    |<span data-ttu-id="d8aac-131">Cria um conjunto de políticas e configurações de política que se aplicam aos professores.</span><span class="sxs-lookup"><span data-stu-id="d8aac-131">Creates a set of policies and policy settings that apply to teachers.</span></span>      |
|<span data-ttu-id="d8aac-132">Educação (professor primário usando aprendizagem remota)</span><span class="sxs-lookup"><span data-stu-id="d8aac-132">Education (Primary school teacher using remote learning)</span></span>    |<span data-ttu-id="d8aac-133">Cria um conjunto de políticas que se aplicam aos professores primários para maximizar a segurança e a colaboração dos alunos ao usar o aprendizado remoto.</span><span class="sxs-lookup"><span data-stu-id="d8aac-133">Creates a set of policies that apply to primary teachers to maximize student safety and collaboration when using remote learning.</span></span>      |
|<span data-ttu-id="d8aac-134">Educação (aluno do ensino fundamental usando o aprendizado remoto)</span><span class="sxs-lookup"><span data-stu-id="d8aac-134">Education (Primary school student using remote learning)</span></span>    |<span data-ttu-id="d8aac-135">Cria um conjunto de políticas que se aplicam aos alunos do ensino fundamental para maximizar a segurança e a colaboração dos alunos ao usarem o aprendizado remoto.</span><span class="sxs-lookup"><span data-stu-id="d8aac-135">Creates a set of policies that apply to primary students to maximize student safety and collaboration when using remote learning.</span></span>      |
|<span data-ttu-id="d8aac-136">Gerenciador de frontline</span><span class="sxs-lookup"><span data-stu-id="d8aac-136">Frontline manager</span></span> |<span data-ttu-id="d8aac-137">Cria um conjunto de políticas e aplica essas configurações aos gerentes de Linha de Frente em sua organização.</span><span class="sxs-lookup"><span data-stu-id="d8aac-137">Creates a set of policies and applies those settings to Frontline managers in your organization.</span></span> |
|<span data-ttu-id="d8aac-138">Trabalhador de linha de frente</span><span class="sxs-lookup"><span data-stu-id="d8aac-138">Frontline worker</span></span> |<span data-ttu-id="d8aac-139">Cria um conjunto de políticas e aplica essas configurações aos trabalhadores frontline em sua organização.</span><span class="sxs-lookup"><span data-stu-id="d8aac-139">Creates a set of policies and applies those settings to Frontline workers in your organization.</span></span> |
|<span data-ttu-id="d8aac-140">Profissional clínico da área de saúde</span><span class="sxs-lookup"><span data-stu-id="d8aac-140">Healthcare clinical worker</span></span>  |<span data-ttu-id="d8aac-141">Cria um conjunto de políticas e configurações de política que dão a funcionários da área de saúde, como enfermeiros registrados, enfermeiros chefe, médicos e assistentes sociais acesso total ao chat, chamadas, gerenciamento de turnos e reuniões.</span><span class="sxs-lookup"><span data-stu-id="d8aac-141">Creates a set of policies and policy settings that give clinical workers such as registered nurses, charge nurses, physicians, and social workers full access to chat, calling, shift management, and meetings.</span></span> |
|<span data-ttu-id="d8aac-142">Profissional de informações da área de saúde</span><span class="sxs-lookup"><span data-stu-id="d8aac-142">Healthcare information worker</span></span>  |<span data-ttu-id="d8aac-143">Cria um conjunto de políticas e configurações de política que dão aos operadores de informações na sua organização da área de saúde, como equipe de TI, de informática, equipe financeira e responsáveis pela conformidade acesso total ao chat, chamadas e reuniões.</span><span class="sxs-lookup"><span data-stu-id="d8aac-143">Creates a set of policies and policy settings that give information workers such as IT personnel, informatics staff, finance personnel, and compliance officers, full access to chat, calling, and meetings.</span></span>|
|<span data-ttu-id="d8aac-144">Quartos dos pacientes de saúde</span><span class="sxs-lookup"><span data-stu-id="d8aac-144">Healthcare patient room</span></span>  |<span data-ttu-id="d8aac-145">Cria um conjunto de políticas e configurações de política que se aplicam aos quartos dos pacientes em sua organização de saúde.</span><span class="sxs-lookup"><span data-stu-id="d8aac-145">Creates a set of policies and policy settings that apply to patient rooms in your healthcare organization.</span></span>|
|<span data-ttu-id="d8aac-146">Usuário de pequenas e médias empresas (Business Voice)</span><span class="sxs-lookup"><span data-stu-id="d8aac-146">Small and medium business user (Business Voice)</span></span> |<span data-ttu-id="d8aac-147">Cria uma política de configuração de aplicativo que inclui os aplicativos para uma experiência de voz comercial.</span><span class="sxs-lookup"><span data-stu-id="d8aac-147">Creates an app setup policy that includes the apps for a business voice experience.</span></span>|
|<span data-ttu-id="d8aac-148">Usuário de pequenas e médias empresas (sem o Business Voice)</span><span class="sxs-lookup"><span data-stu-id="d8aac-148">Small and medium business user (without Business Voice)</span></span> |<span data-ttu-id="d8aac-149">Cria uma política de configuração de aplicativo relevante para usuários do Teams de pequeno e médio porte (experiência que não é do Business Voice).</span><span class="sxs-lookup"><span data-stu-id="d8aac-149">Creates an app setup policy relevant for a small and medium sized business Teams users (non-Business Voice experience).</span></span>
|<span data-ttu-id="d8aac-150">Oficial de segurança pública</span><span class="sxs-lookup"><span data-stu-id="d8aac-150">Public safety officer</span></span>   |<span data-ttu-id="d8aac-151">Cria um conjunto de políticas e configurações de política que se aplicam aos agentes de segurança pública em sua organização.</span><span class="sxs-lookup"><span data-stu-id="d8aac-151">Creates a set of policies and policy settings that apply to public safety officers in your organization.</span></span>|

> [!NOTE]
> <span data-ttu-id="d8aac-152">Adicionaremos mais pacotes de política em versões futuras do Teams, portanto, verifique se há informações mais atualizadas.</span><span class="sxs-lookup"><span data-stu-id="d8aac-152">We'll be adding more policy packages in future releases of Teams, so check back for the most up-to-date information.</span></span>  

<span data-ttu-id="d8aac-153">Cada política individual recebe o nome do pacote de políticas, para que você possa identificar facilmente políticas vinculadas a um pacote de políticas.</span><span class="sxs-lookup"><span data-stu-id="d8aac-153">Each individual policy is given the name of the policy package so you can easily identify the policies that are linked to a policy package.</span></span>
<span data-ttu-id="d8aac-154">Por exemplo, quando você atribui o pacote de política de Educação (Professor) aos professores em sua escola, uma política chamada Education_Teacher é criada para cada política no pacote.</span><span class="sxs-lookup"><span data-stu-id="d8aac-154">For example, when you assign the Education (Teacher) policy package to teachers in your school, a policy that's named Education_Teacher is created for each policy in the package.</span></span>

![Captura de tela do pacote de política educação (professor)](media/policy-packages-education_teacher.png)

## <a name="custom-policy-packages"></a><span data-ttu-id="d8aac-156">Pacotes de política personalizados</span><span class="sxs-lookup"><span data-stu-id="d8aac-156">Custom policy packages</span></span>

<span data-ttu-id="d8aac-157">**Pacotes de política personalizados ainda não estão disponíveis para a Nuvem da Comunidade Governamental (GCC)**</span><span class="sxs-lookup"><span data-stu-id="d8aac-157">**Custom policy packages is not yet available for the Government Community Cloud (GCC)**</span></span>

<span data-ttu-id="d8aac-158">Pacotes de política personalizados permitem que você empacote seu próprio conjunto de políticas para usuários com funções semelhantes em sua organização.</span><span class="sxs-lookup"><span data-stu-id="d8aac-158">Custom policy packages let you bundle your own set of policies for users with similar roles in you organization.</span></span> <span data-ttu-id="d8aac-159">Crie seus próprios pacotes de política adicionando os tipos de política e as políticas de que você precisa.</span><span class="sxs-lookup"><span data-stu-id="d8aac-159">Create your own policy packages by adding the policy types and policies that you need.</span></span>

<span data-ttu-id="d8aac-160">Para criar um novo pacote de política personalizado:</span><span class="sxs-lookup"><span data-stu-id="d8aac-160">To create a new custom policy package:</span></span>

1. <span data-ttu-id="d8aac-161">Na navegação à esquerda do centro de administração do Microsoft Teams, selecione **Pacotes de política** e clique em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="d8aac-161">In the left navigation of the Microsoft Teams admin center,  select **Policy packages**, and then click **Add**.</span></span>

    :::image type="content" source="media/policy-packages-add.png" alt-text="Captura de tela do botão Adicionar em pacotes de política no centro de administração":::

2. <span data-ttu-id="d8aac-163">Insira um nome e uma descrição para o pacote.</span><span class="sxs-lookup"><span data-stu-id="d8aac-163">Enter a name and description for your package.</span></span>

    :::image type="content" source="media/policy-packages-add-custom.png" alt-text="Captura de tela da adição de um novo pacote de política personalizado":::

3. <span data-ttu-id="d8aac-165">Selecione os tipos de política e os nomes de política a incluir no pacote.</span><span class="sxs-lookup"><span data-stu-id="d8aac-165">Select the policy types and policy names to include in the package.</span></span>

4. <span data-ttu-id="d8aac-166">Clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="d8aac-166">Click **Save**.</span></span>

## <a name="how-to-use-policy-packages"></a><span data-ttu-id="d8aac-167">Como usar pacotes de política</span><span class="sxs-lookup"><span data-stu-id="d8aac-167">How to use policy packages</span></span>

<span data-ttu-id="d8aac-168">As estruturas a seguir explicam como usar pacotes de política em sua organização.</span><span class="sxs-lookup"><span data-stu-id="d8aac-168">The following outlines how to use policy packages in your organization.</span></span>

![Visão geral de como usar pacotes de política](media/manage-policy-packages-overview.png)

- <span data-ttu-id="d8aac-170">**[Exibir](#view-the-settings-of-a-policy-in-a-policy-package)**: Exibir as políticas em um pacote de política.</span><span class="sxs-lookup"><span data-stu-id="d8aac-170">**[View](#view-the-settings-of-a-policy-in-a-policy-package)**: View the policies in a policy package.</span></span> <span data-ttu-id="d8aac-171">Em seguida, exibir as configurações de cada política em um pacote antes de atribuir o pacote.</span><span class="sxs-lookup"><span data-stu-id="d8aac-171">Then, view the settings of each policy in a package before you assign the package.</span></span> <span data-ttu-id="d8aac-172">Certifique-se de entender cada configuração.</span><span class="sxs-lookup"><span data-stu-id="d8aac-172">Make sure that you understand each setting.</span></span> <span data-ttu-id="d8aac-173">Decida se os valores predefinidos são apropriados para sua organização ou se você precisa alterá-los para que sejam mais restritivos ou tolerantes com base nas necessidades da sua organização.</span><span class="sxs-lookup"><span data-stu-id="d8aac-173">Decide whether the predefined values are appropriate for your organization or whether you need to change them to be more restrictive or lenient based on your organization's needs.</span></span>

    <span data-ttu-id="d8aac-174">Se uma política for excluída, você ainda poderá exibir as configurações, mas não poderá alterar nenhuma configuração.</span><span class="sxs-lookup"><span data-stu-id="d8aac-174">If a policy is deleted, you can still view the settings but you won't be able to change any settings.</span></span> <span data-ttu-id="d8aac-175">Uma política excluída é re-criada com as configurações predefinida quando você atribui o pacote de política.</span><span class="sxs-lookup"><span data-stu-id="d8aac-175">A deleted policy is re-created with the predefined settings when you assign the policy package.</span></span>

- <span data-ttu-id="d8aac-176">**[Personalizar](#customize-policies-in-a-policy-package)**: personalizar as configurações de políticas no pacote de política para se ajustar às necessidades da sua organização.</span><span class="sxs-lookup"><span data-stu-id="d8aac-176">**[Customize](#customize-policies-in-a-policy-package)**: Customize the settings of policies in the policy package to fit the needs of your organization.</span></span>

- <span data-ttu-id="d8aac-177">**[Atribuir](#assign-a-policy-package)**: atribuir o pacote de política aos usuários.</span><span class="sxs-lookup"><span data-stu-id="d8aac-177">**[Assign](#assign-a-policy-package)**: Assign the policy package to users.</span></span>  

> [!NOTE]
> <span data-ttu-id="d8aac-178">Você também pode alterar as configurações de políticas em um pacote de política depois de atribuir um pacote.</span><span class="sxs-lookup"><span data-stu-id="d8aac-178">You can also change the settings of policies in a policy package after you assign a package.</span></span> <span data-ttu-id="d8aac-179">As alterações que você fizer nas configurações da política serão automaticamente aplicadas aos usuários que recebem o pacote.</span><span class="sxs-lookup"><span data-stu-id="d8aac-179">Any changes you make to policy settings are automatically applied to users who are assigned the package.</span></span>

<span data-ttu-id="d8aac-180">Aqui estão as etapas de como exibir, atribuir e personalizar pacotes de política no centro de administração do Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="d8aac-180">Here are the steps for how to view, assign, and customize policy packages in the Microsoft Teams admin center.</span></span>

### <a name="view-the-settings-of-a-policy-in-a-policy-package"></a><span data-ttu-id="d8aac-181">Exibir as configurações de uma política em um pacote de política</span><span class="sxs-lookup"><span data-stu-id="d8aac-181">View the settings of a policy in a policy package</span></span>

1. <span data-ttu-id="d8aac-182">Na navegação à esquerda do centro de administração do Microsoft Teams, selecione Pacotes de política **e** selecione um pacote de política clicando à esquerda do nome do pacote.</span><span class="sxs-lookup"><span data-stu-id="d8aac-182">In the left navigation of the Microsoft Teams admin center, select **Policy packages**, and then select a policy package by clicking to the left of the package name.</span></span>

2. <span data-ttu-id="d8aac-183">Clique na política que você deseja exibir.</span><span class="sxs-lookup"><span data-stu-id="d8aac-183">Click the policy you want to view.</span></span>

### <a name="customize-policies-in-a-policy-package"></a><span data-ttu-id="d8aac-184">Personalizar políticas em um pacote de política</span><span class="sxs-lookup"><span data-stu-id="d8aac-184">Customize policies in a policy package</span></span>

<span data-ttu-id="d8aac-185">Você pode editar as configurações  de uma política por meio da página Pacotes de Política ou indo diretamente para a página de política no centro de administração do Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="d8aac-185">You can edit the settings of a policy through the **Policy packages** page or by going directly to the policy page in the Microsoft Teams admin center.</span></span>

1. <span data-ttu-id="d8aac-186">Na navegação à esquerda do Centro de administração do Microsoft Teams, faça um dos seguintes:</span><span class="sxs-lookup"><span data-stu-id="d8aac-186">In the left navigation of the Microsoft Teams admin center, do one of the following:</span></span>
    - <span data-ttu-id="d8aac-187">Clique **em Pacotes de** Política e selecione o pacote de política clicando à esquerda do nome do pacote.</span><span class="sxs-lookup"><span data-stu-id="d8aac-187">Click **Policy packages**, and then select the policy package by clicking to the left of the package name.</span></span>
    - <span data-ttu-id="d8aac-188">Clique no tipo de política.</span><span class="sxs-lookup"><span data-stu-id="d8aac-188">Click the policy type.</span></span>  <span data-ttu-id="d8aac-189">Por exemplo, clique em **Políticas de mensagens.**</span><span class="sxs-lookup"><span data-stu-id="d8aac-189">For example, click **Messaging policies**.</span></span>

2. <span data-ttu-id="d8aac-190">Selecione a política que você deseja editar.</span><span class="sxs-lookup"><span data-stu-id="d8aac-190">Select the policy you want to edit.</span></span> <span data-ttu-id="d8aac-191">As políticas vinculadas a um pacote de política têm o mesmo nome do pacote de política.</span><span class="sxs-lookup"><span data-stu-id="d8aac-191">Policies that are linked to a policy package have the same name as the policy package.</span></span>

3. <span data-ttu-id="d8aac-192">Faça as alterações que você deseja e clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="d8aac-192">Make the changes that you want, and then click **Save**.</span></span>

### <a name="assign-a-policy-package"></a><span data-ttu-id="d8aac-193">Atribuir um pacote de política</span><span class="sxs-lookup"><span data-stu-id="d8aac-193">Assign a policy package</span></span>

<span data-ttu-id="d8aac-194">Você pode atribuir um pacote de política a um usuário individual, a um grupo ou a um lote de usuários.</span><span class="sxs-lookup"><span data-stu-id="d8aac-194">You can assign a policy package to an individual user, a group, or a batch of users.</span></span> <span data-ttu-id="d8aac-195">Para obter mais informações sobre como atribuir pacotes de política, consulte [Atribuir pacotes de política a usuários e grupos.](assign-policy-packages.md)</span><span class="sxs-lookup"><span data-stu-id="d8aac-195">For more information on how to assign policy packages, see [Assign policy packages to users and groups](assign-policy-packages.md).</span></span>

## <a name="related-topics"></a><span data-ttu-id="d8aac-196">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="d8aac-196">Related topics</span></span>

- [<span data-ttu-id="d8aac-197">Atribuir pacotes de política</span><span class="sxs-lookup"><span data-stu-id="d8aac-197">Assign policy packages</span></span>](assign-policy-packages.md)
- [<span data-ttu-id="d8aac-198">Pacotes de política do Teams para administradores EDU</span><span class="sxs-lookup"><span data-stu-id="d8aac-198">Teams policy packages for EDU admins</span></span>](policy-packages-edu.md)
- [<span data-ttu-id="d8aac-199">Pacotes de políticas do Teams para a área de saúde</span><span class="sxs-lookup"><span data-stu-id="d8aac-199">Teams policy packages for healthcare</span></span>](policy-packages-healthcare.md)
- [<span data-ttu-id="d8aac-200">Pacotes de política do Teams para o governo</span><span class="sxs-lookup"><span data-stu-id="d8aac-200">Teams policy packages for government</span></span>](policy-packages-gov.md)
