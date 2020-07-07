---
title: Atribuir políticas aos usuários no Microsoft Teams
author: lanachin
ms.author: v-lanac
manager: serdars
ms.reviewer: tomkau, saragava, ritikag, jastark
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
f1keywords:
- ms.teamsadmincenter.bulkoperations.users.edit
- ms.teamsadmincenter.bulkoperations.edit
ms.openlocfilehash: 161a979578f24b351c93e870a562e6c4104b52d0
ms.sourcegitcommit: ac36d3923095a4321dad14fdf23c98358affd10c
ms.contentlocale: pt-BR
ms.lasthandoff: 07/07/2020
ms.locfileid: "45049438"
---
# <a name="assign-policies-to-your-users-in-microsoft-teams"></a><span data-ttu-id="b12f4-103">Atribuir políticas aos usuários no Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="b12f4-103">Assign policies to your users in Microsoft Teams</span></span>

> [!NOTE]
> <span data-ttu-id="b12f4-104">Um dos recursos discutidos neste artigo, [atribuição de política a grupos usando o centro de administração do Microsoft Teams](#using-the-microsoft-teams-admin-center-3)ainda não foi lançado.</span><span class="sxs-lookup"><span data-stu-id="b12f4-104">One of the features discussed in this article, [policy assignment to groups using the Microsoft Teams admin center](#using-the-microsoft-teams-admin-center-3), hasn't yet been released.</span></span> <span data-ttu-id="b12f4-105">Ele foi anunciado e estará disponível em breve.</span><span class="sxs-lookup"><span data-stu-id="b12f4-105">It's been announced, and it's coming soon.</span></span>
> <span data-ttu-id="b12f4-106">Para ficar por dentro do status do lançamento desse recurso, consulte o mapa do [Microsoft 365](https://www.microsoft.com/microsoft-365/roadmap?filters=&searchterms=61185).</span><span class="sxs-lookup"><span data-stu-id="b12f4-106">To stay on top of the release status of this feature, check out the [Microsoft 365 Roadmap](https://www.microsoft.com/microsoft-365/roadmap?filters=&searchterms=61185).</span></span>

<span data-ttu-id="b12f4-107">Como administrador, você usa políticas para controlar os recursos do teams que estão disponíveis para os usuários da sua organização.</span><span class="sxs-lookup"><span data-stu-id="b12f4-107">As an admin, you use policies to control the Teams features that are available to users in your organization.</span></span> <span data-ttu-id="b12f4-108">Por exemplo, há políticas de chamada, políticas de reunião e políticas de mensagens, para citar apenas alguns.</span><span class="sxs-lookup"><span data-stu-id="b12f4-108">For example, there are calling policies, meeting policies, and messaging policies, to name just a few.</span></span>

<span data-ttu-id="b12f4-109">As organizações têm diferentes tipos de usuários com necessidades exclusivas e políticas personalizadas que você cria e atribui permite que você ajuste as configurações de política para diferentes conjuntos de usuários com base nessas necessidades.</span><span class="sxs-lookup"><span data-stu-id="b12f4-109">Organizations have different types of users with unique needs and custom policies that you create and assign let you tailor policy settings to different sets of users based on those needs.</span></span>

<span data-ttu-id="b12f4-110">Para facilitar o gerenciamento de políticas em sua organização, o Teams oferece várias maneiras de atribuir políticas a usuários.</span><span class="sxs-lookup"><span data-stu-id="b12f4-110">To make it easier to manage policies in your organization, Teams offers several ways to assign policies to users.</span></span> <span data-ttu-id="b12f4-111">Você pode atribuir uma política diretamente aos usuários, individualmente ou em escalabilidade por meio de uma atribuição de lote ou a um grupo do qual os usuários são membros.</span><span class="sxs-lookup"><span data-stu-id="b12f4-111">You can assign a policy directly to users, either individually or at scale through a batch assignment, or to a group that the users are members of.</span></span> <span data-ttu-id="b12f4-112">Você também pode usar pacotes de política para atribuir uma coleção predefinida de políticas para os usuários de sua organização que têm funções semelhantes.</span><span class="sxs-lookup"><span data-stu-id="b12f4-112">You can also use policy packages to assign a preset collection of policies to users in your organization who have similar roles.</span></span> <span data-ttu-id="b12f4-113">A opção que você escolher depende do número de políticas que você está gerenciando e do número de usuários aos quais está fazendo a atribuição.</span><span class="sxs-lookup"><span data-stu-id="b12f4-113">The option that you choose depends on the number of policies that you're managing and the number of users that you're assigning to.</span></span> <span data-ttu-id="b12f4-114">Ao definir as políticas globais (padrão para toda a organização) para que elas se apliquem ao maior número de usuários em sua organização, você só precisa atribuir políticas a esses usuários que exigem políticas especializadas.</span><span class="sxs-lookup"><span data-stu-id="b12f4-114">By setting the global (Org-wide default) policies so that they apply to the largest number of users in your organization, you only have to assign policies to those users that require specialized policies.</span></span>

<span data-ttu-id="b12f4-115">Este artigo descreve as diferentes maneiras pelas quais você pode atribuir políticas a usuários e os cenários recomendados para quando usar o quê.</span><span class="sxs-lookup"><span data-stu-id="b12f4-115">This article describes the different ways that you can assign policies to users and the recommended scenarios for when to use what.</span></span>

## <a name="which-policy-takes-precedence"></a><span data-ttu-id="b12f4-116">Qual política tem precedência?</span><span class="sxs-lookup"><span data-stu-id="b12f4-116">Which policy takes precedence?</span></span>

<span data-ttu-id="b12f4-117">Um usuário tem uma política em vigor para cada tipo de política.</span><span class="sxs-lookup"><span data-stu-id="b12f4-117">A user has one effective policy for each policy type.</span></span> <span data-ttu-id="b12f4-118">É possível ou até mesmo provável que um usuário esteja diretamente atribuído a uma política e também seja um membro de um ou mais grupos que tenha atribuído uma política do mesmo tipo.</span><span class="sxs-lookup"><span data-stu-id="b12f4-118">It's possible or even likely that a user is directly assigned a policy and is also a member of one or more groups that's assigned a policy of the same type.</span></span> <span data-ttu-id="b12f4-119">Nesses tipos de cenários, qual política tem precedência?</span><span class="sxs-lookup"><span data-stu-id="b12f4-119">In these kinds of scenarios, which policy takes precedence?</span></span>  <span data-ttu-id="b12f4-120">A política efetiva de um usuário é determinada de acordo com as regras de precedência, da seguinte maneira.</span><span class="sxs-lookup"><span data-stu-id="b12f4-120">A user's effective policy is determined according to rules of precedence, as follows.</span></span>

<span data-ttu-id="b12f4-121">Se um usuário for diretamente atribuído a uma política (individualmente ou por meio de uma atribuição em lotes), essa política terá precedência.</span><span class="sxs-lookup"><span data-stu-id="b12f4-121">If a user is directly assigned a policy (either individually or through a batch assignment), that policy takes precedence.</span></span> <span data-ttu-id="b12f4-122">No exemplo a seguir, a política efetiva do usuário é a política de reunião quadrada Lincoln, que é atribuída diretamente ao usuário.</span><span class="sxs-lookup"><span data-stu-id="b12f4-122">In the following example, the user's effective policy is the Lincoln Square meeting policy, which is directly assigned to the user.</span></span>

![Diagrama mostrando como uma política atribuída diretamente tem prioridade](media/assign-policies-example-directly-assigned.png)

<span data-ttu-id="b12f4-124">Se um usuário não estiver diretamente atribuído a uma política de um determinado tipo, a política atribuída a um grupo do qual o usuário é membro terá precedência.</span><span class="sxs-lookup"><span data-stu-id="b12f4-124">If a user isn't directly assigned a policy of a given type, the policy assigned to a group that the user is a member of takes precedence.</span></span> <span data-ttu-id="b12f4-125">Se um usuário for membro de vários grupos, a política que tem a classificação de [atribuição de grupo](#group-assignment-ranking) mais alta para o tipo de política específico tem precedência.</span><span class="sxs-lookup"><span data-stu-id="b12f4-125">If a user is a member of multiple groups, the policy that has the highest [group assignment ranking](#group-assignment-ranking) for the given policy type takes precedence.</span></span>

<span data-ttu-id="b12f4-126">Neste exemplo, a política efetiva do usuário é o Teams exec e a política de HD, que tem a classificação de atribuição mais alta em relação a outros grupos dos quais o usuário é membro e que também são atribuídas uma política do mesmo tipo de política.</span><span class="sxs-lookup"><span data-stu-id="b12f4-126">In this example, the user's effective policy is the Exec Teams and HD policy, which has the highest assignment ranking relative to other groups that the user is a member of and that are also assigned a policy of the same policy type.</span></span>  

![Diagrama mostrando como uma política herdada do grupo tem prioridade](media/assign-policies-example-group.png)

<span data-ttu-id="b12f4-128">Se um usuário não estiver diretamente atribuído a uma política ou não for membro de nenhum grupo ao qual a política atribuiu uma política, o usuário terá a política global (padrão para toda a organização) para esse tipo de política.</span><span class="sxs-lookup"><span data-stu-id="b12f4-128">If a user isn't directly assigned a policy or isn't a member of any groups that are assigned a policy, the user gets the global (Org-wide default) policy for that policy type.</span></span> <span data-ttu-id="b12f4-129">Aqui está um exemplo.</span><span class="sxs-lookup"><span data-stu-id="b12f4-129">Here's an example.</span></span>

![Diagrama mostrando como uma política global tem precedência](media/assign-policies-example-global.png)

<span data-ttu-id="b12f4-131">Para saber mais, consulte [regras de precedência](#precedence-rules).</span><span class="sxs-lookup"><span data-stu-id="b12f4-131">To learn more, see [Precedence rules](#precedence-rules).</span></span>

## <a name="ways-to-assign-policies"></a><span data-ttu-id="b12f4-132">Maneiras de atribuir políticas</span><span class="sxs-lookup"><span data-stu-id="b12f4-132">Ways to assign policies</span></span>

<span data-ttu-id="b12f4-133">Aqui está uma visão geral de como você pode atribuir políticas a usuários e os cenários recomendados para cada um deles.</span><span class="sxs-lookup"><span data-stu-id="b12f4-133">Here's an overview of the ways that you can assign policies to users and the recommended scenarios for each.</span></span> <span data-ttu-id="b12f4-134">Clique nos links para saber mais.</span><span class="sxs-lookup"><span data-stu-id="b12f4-134">Click the links to learn more.</span></span>

<span data-ttu-id="b12f4-135">Antes de atribuir políticas a usuários ou grupos individuais, comece [definindo as políticas globais (padrão para toda](#set-the-global-policies) a organização) para que elas se apliquem ao maior número de usuários em sua organização.</span><span class="sxs-lookup"><span data-stu-id="b12f4-135">Before assigning policies to individual users or groups, start by [setting the global (Org-wide default) policies](#set-the-global-policies) so that they apply to the largest number of users in your organization.</span></span>  <span data-ttu-id="b12f4-136">Depois que as políticas globais estiverem definidas, você só precisará atribuir políticas a esses usuários que exigem políticas especializadas.</span><span class="sxs-lookup"><span data-stu-id="b12f4-136">Once the global policies are set, you will only need to assign policies to those users that require specialized policies.</span></span>

|<span data-ttu-id="b12f4-137">Faça isto</span><span class="sxs-lookup"><span data-stu-id="b12f4-137">Do this</span></span>  |<span data-ttu-id="b12f4-138">Se...</span><span class="sxs-lookup"><span data-stu-id="b12f4-138">If...</span></span>  | <span data-ttu-id="b12f4-139">Usar...</span><span class="sxs-lookup"><span data-stu-id="b12f4-139">Using...</span></span>
|---------|---------|----|
|[<span data-ttu-id="b12f4-140">Atribuir uma política a usuários individuais</span><span class="sxs-lookup"><span data-stu-id="b12f4-140">Assign a policy to individual users</span></span>](#assign-a-policy-to-individual-users)    | <span data-ttu-id="b12f4-141">Você está começando a usar o Microsoft Teams e simplesmente está começando ou só precisa atribuir uma ou algumas políticas a um pequeno número de usuários.</span><span class="sxs-lookup"><span data-stu-id="b12f4-141">You're new to Teams and just getting started or you only need to assign one or a couple of policies to a small number of users.</span></span> |<span data-ttu-id="b12f4-142">O centro de administração do Microsoft Teams ou cmdlets do PowerShell no módulo do PowerShell do Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="b12f4-142">The Microsoft Teams admin center or PowerShell cmdlets in the Skype for Business Online PowerShell module</span></span>
| [<span data-ttu-id="b12f4-143">Atribuir um pacote de política</span><span class="sxs-lookup"><span data-stu-id="b12f4-143">Assign a policy package</span></span>](#assign-a-policy-package)   | <span data-ttu-id="b12f4-144">Você precisa atribuir várias políticas a conjuntos específicos de usuários em sua organização que tenham funções iguais ou semelhantes.</span><span class="sxs-lookup"><span data-stu-id="b12f4-144">You need to assign multiple policies to specific sets of users in your organization who have the same or similar roles.</span></span> <span data-ttu-id="b12f4-145">Por exemplo, atribua o pacote de política de educação (professor) a professores em sua escola para dar a eles acesso total a chats, chamadas e reuniões e ao pacote de política Education (aluno da escola secundária) para os alunos secundários limitarem determinados recursos como chamadas privadas.</span><span class="sxs-lookup"><span data-stu-id="b12f4-145">For example, assign the Education (Teacher) policy package to teachers in your school to give them full access to chats, calling, and meetings and the Education (Secondary school student) policy package to secondary students to limit certain capabilities like private calling.</span></span>  |<span data-ttu-id="b12f4-146">O centro de administração do Microsoft Teams ou cmdlets do PowerShell no módulo Teams PowerShell</span><span class="sxs-lookup"><span data-stu-id="b12f4-146">The Microsoft Teams admin center or PowerShell cmdlets in the Teams PowerShell module</span></span>|
|[<span data-ttu-id="b12f4-147">Atribuir uma política a um lote de usuários</span><span class="sxs-lookup"><span data-stu-id="b12f4-147">Assign a policy to a batch of users</span></span>](#assign-a-policy-to-a-batch-of-users)   | <span data-ttu-id="b12f4-148">Você precisa atribuir políticas a grandes conjuntos de usuários.</span><span class="sxs-lookup"><span data-stu-id="b12f4-148">You need to assign policies to large sets of users.</span></span> <span data-ttu-id="b12f4-149">Por exemplo, você deseja atribuir uma política para centenas ou milhares de usuários em sua organização de cada vez.</span><span class="sxs-lookup"><span data-stu-id="b12f4-149">For example, you want to assign a policy to hundreds or thousands of users in your organization at a time.</span></span>  |<span data-ttu-id="b12f4-150">O centro de administração do Microsoft Teams ou cmdlets do PowerShell no módulo Teams PowerShell</span><span class="sxs-lookup"><span data-stu-id="b12f4-150">The Microsoft Teams admin center or PowerShell cmdlets in the Teams PowerShell module</span></span>|
|[<span data-ttu-id="b12f4-151">Atribuir uma política a um grupo</span><span class="sxs-lookup"><span data-stu-id="b12f4-151">Assign a policy to a group</span></span>](#assign-a-policy-to-a-group) |<span data-ttu-id="b12f4-152">Você precisa atribuir políticas com base nas associações de grupo de um usuário.</span><span class="sxs-lookup"><span data-stu-id="b12f4-152">You need to assign policies based on a user's group membership.</span></span> <span data-ttu-id="b12f4-153">Por exemplo, você deseja atribuir uma política a todos os usuários em um grupo de segurança ou unidade organizacional.</span><span class="sxs-lookup"><span data-stu-id="b12f4-153">For example, you want to assign a policy to all users in a security group or organizational unit.</span></span>| <span data-ttu-id="b12f4-154">O centro de administração do Microsoft Teams (disponível em breve) ou cmdlets do PowerShell no módulo do PowerShell para Teams</span><span class="sxs-lookup"><span data-stu-id="b12f4-154">The Microsoft Teams admin center (coming soon) or PowerShell cmdlets in the Teams PowerShell module</span></span>|
| [<span data-ttu-id="b12f4-155">Atribuir um pacote de política a um lote de usuários</span><span class="sxs-lookup"><span data-stu-id="b12f4-155">Assign a policy package to a batch of users</span></span>](#assign-a-policy-package-to-a-batch-of-users)|<span data-ttu-id="b12f4-156">Você precisa atribuir várias políticas a um lote de usuários em sua organização que tenham funções iguais ou semelhantes.</span><span class="sxs-lookup"><span data-stu-id="b12f4-156">You need to assign multiple policies to a batch of users in your organization who have the same or similar roles.</span></span> <span data-ttu-id="b12f4-157">Por exemplo, atribua o pacote de política de educação (professor) a todos os professores da sua escola usando a atribuição de lote para dar a eles acesso total a chats, chamadas e reuniões e atribuir o pacote de política de educação (aluno secundária da escola) a um lote de alunos secundários para limitar determinados recursos como chamadas privadas.</span><span class="sxs-lookup"><span data-stu-id="b12f4-157">For example, assign the Education (Teacher) policy package to all teachers in your school using batch assignment to give them full access to chats, calling, and meetings and assign the Education (Secondary school student) policy package to a batch of secondary students to limit certain capabilities like private calling.</span></span>|<span data-ttu-id="b12f4-158">Cmdlets do PowerShell no módulo do teams PowerShell</span><span class="sxs-lookup"><span data-stu-id="b12f4-158">PowerShell cmdlets in the Teams PowerShell module</span></span>|
| <span data-ttu-id="b12f4-159">Atribuir um pacote de política a um grupo (disponível em breve)</span><span class="sxs-lookup"><span data-stu-id="b12f4-159">Assign a policy package to a group (coming soon)</span></span>   | ||

## <a name="set-the-global-policies"></a><span data-ttu-id="b12f4-160">Definir as políticas globais</span><span class="sxs-lookup"><span data-stu-id="b12f4-160">Set the global policies</span></span>

<span data-ttu-id="b12f4-161">Siga estas etapas para definir as políticas globais (padrão para toda a organização) para cada tipo de política.</span><span class="sxs-lookup"><span data-stu-id="b12f4-161">Follow these steps to set the global (Org-wide default) policies for each policy type.</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="b12f4-162">Usando o centro de administração do Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="b12f4-162">Using the Microsoft Teams admin center</span></span>

1. <span data-ttu-id="b12f4-163">Na navegação à esquerda do centro de administração do Microsoft Teams, vá para a página política do tipo de política que você deseja atualizar.</span><span class="sxs-lookup"><span data-stu-id="b12f4-163">In the left navigation of the Microsoft Teams admin center, go to the policy page for the policy type you want to update.</span></span> <span data-ttu-id="b12f4-164">Por exemplo, políticas **Teams**  >  de**equipes**de equipe, políticas de reuniões de **reuniões**  >  **Meetings policies**, políticas de **mensagens**ou políticas de chamadas de **voz**  >  **Calling policies**.</span><span class="sxs-lookup"><span data-stu-id="b12f4-164">For example, **Teams** > **Teams policies**, **Meetings** > **Meetings policies**, **Messaging policies**, or **Voice** > **Calling policies**.</span></span>
2. <span data-ttu-id="b12f4-165">Selecione a política **global (padrão para toda a organização)** para exibir as configurações atuais.</span><span class="sxs-lookup"><span data-stu-id="b12f4-165">Select the **Global (Org-wide default)** policy to view the current settings.</span></span>
3. <span data-ttu-id="b12f4-166">Atualize a política conforme necessário e selecione **aplicar**.</span><span class="sxs-lookup"><span data-stu-id="b12f4-166">Update the policy as needed, and then select **Apply**.</span></span>

### <a name="using-powershell"></a><span data-ttu-id="b12f4-167">Usando o PowerShell</span><span class="sxs-lookup"><span data-stu-id="b12f4-167">Using PowerShell</span></span>

<span data-ttu-id="b12f4-168">Para definir as políticas globais usando o PowerShell, use o identificador global.</span><span class="sxs-lookup"><span data-stu-id="b12f4-168">To set the global policies using PowerShell, use the Global identifier.</span></span>  <span data-ttu-id="b12f4-169">Comece analisando a política global atual para determinar qual configuração você deseja alterar.</span><span class="sxs-lookup"><span data-stu-id="b12f4-169">Start by reviewing the current Global policy to determine which setting you want to change.</span></span>

```powershell
Get-CsTeamsMessagingPolicy -Identity Global
 
Identity                      : Global
Description                   :
AllowUrlPreviews              : True
AllowOwnerDeleteMessage       : False
AllowUserEditMessage          : True
AllowUserDeleteMessage        : True
AllowUserChat                 : True
AllowRemoveUser               : True
AllowGiphy                    : True
GiphyRatingType               : Moderate
AllowMemes                    : True
AllowImmersiveReader          : True
AllowStickers                 : True
AllowUserTranslation          : False
ReadReceiptsEnabledType       : UserPreference
AllowPriorityMessages         : True
ChannelsInChatListEnabledType : DisabledUserOverride
AudioMessageEnabledType       : ChatsAndChannels
Expand (20 lines) Collapse 
```

<span data-ttu-id="b12f4-170">Em seguida, atualize a política global conforme necessário.</span><span class="sxs-lookup"><span data-stu-id="b12f4-170">Next, update the Global policy as needed.</span></span>  <span data-ttu-id="b12f4-171">Você só precisa especificar valores para as configurações que você deseja alterar.</span><span class="sxs-lookup"><span data-stu-id="b12f4-171">You only need to specify values for the settings that you want to change.</span></span> 
 
```powershell
Set-CsTeamsMessagingPolicy -Identity Global -AllowUserEditMessage $false
```

## <a name="assign-a-policy-to-individual-users"></a><span data-ttu-id="b12f4-172">Atribuir uma política a usuários individuais</span><span class="sxs-lookup"><span data-stu-id="b12f4-172">Assign a policy to individual users</span></span>

<span data-ttu-id="b12f4-173">Siga estas etapas para atribuir uma política a um usuário individual ou a um pequeno número de usuários por vez.</span><span class="sxs-lookup"><span data-stu-id="b12f4-173">Follow these steps to assign a policy to an individual user or to a small number of users at a time.</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="b12f4-174">Usando o centro de administração do Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="b12f4-174">Using the Microsoft Teams admin center</span></span>

<span data-ttu-id="b12f4-175">Para atribuir uma política a um usuário:</span><span class="sxs-lookup"><span data-stu-id="b12f4-175">To assign a policy to a user:</span></span>

1. <span data-ttu-id="b12f4-176">Na barra de navegação à esquerda do centro de administração do Microsoft Teams, vá para **Usuários** e clique no usuário.</span><span class="sxs-lookup"><span data-stu-id="b12f4-176">In the left navigation of the Microsoft Teams admin center, go to **Users**, and then click the user.</span></span>
2. <span data-ttu-id="b12f4-177">Selecione o usuário clicando à esquerda do nome de exibição do usuário e clique em **Editar configurações**.</span><span class="sxs-lookup"><span data-stu-id="b12f4-177">Select the user by clicking to the left of the user name, and then click **Edit settings**.</span></span>
3. <span data-ttu-id="b12f4-178">Selecione a política que você deseja atribuir e clique em **aplicar**.</span><span class="sxs-lookup"><span data-stu-id="b12f4-178">Select the policy you want to assign, and then click **Apply**.</span></span>

<span data-ttu-id="b12f4-179">Ou, você também pode fazer o seguinte:</span><span class="sxs-lookup"><span data-stu-id="b12f4-179">Or, you can also do the following:</span></span>

1. <span data-ttu-id="b12f4-180">Na navegação à esquerda do centro de administração do Microsoft Teams, vá para a página política.</span><span class="sxs-lookup"><span data-stu-id="b12f4-180">In the left navigation of the Microsoft Teams admin center, go to the policy page.</span></span>
2. <span data-ttu-id="b12f4-181">Selecione a política que você deseja atribuir clicando à esquerda do nome da política.</span><span class="sxs-lookup"><span data-stu-id="b12f4-181">Select the policy you want to assign by clicking to the left of the policy name.</span></span>
3. <span data-ttu-id="b12f4-182">Escolha **Gerenciar usuários**.</span><span class="sxs-lookup"><span data-stu-id="b12f4-182">Select **Manage users**.</span></span>
4. <span data-ttu-id="b12f4-183">No painel **Gerenciar usuários**, procure o usuário pelo nome de exibição ou pelo nome de usuário, escolha o nome e marque **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="b12f4-183">In the **Manage users** pane, search for the user by display name or by user name, select the name, and then select **Add**.</span></span> <span data-ttu-id="b12f4-184">Repita esta etapa para cada usuário que você deseja adicionar.</span><span class="sxs-lookup"><span data-stu-id="b12f4-184">Repeat this step for each user that you want to add.</span></span>
5. <span data-ttu-id="b12f4-185">Quando tiver terminado de adicionar usuários, selecione **aplicar**.</span><span class="sxs-lookup"><span data-stu-id="b12f4-185">When you're finished adding users, select **Apply**.</span></span>

### <a name="using-powershell"></a><span data-ttu-id="b12f4-186">Usando o PowerShell</span><span class="sxs-lookup"><span data-stu-id="b12f4-186">Using PowerShell</span></span>

<span data-ttu-id="b12f4-187">Cada tipo de política tem seu próprio conjunto de cmdlets para gerenciá-lo.</span><span class="sxs-lookup"><span data-stu-id="b12f4-187">Each policy type has its own set of cmdlets for managing it.</span></span> <span data-ttu-id="b12f4-188">Use o ```Grant-``` cmdlet para um determinado tipo de política para atribuir a política.</span><span class="sxs-lookup"><span data-stu-id="b12f4-188">Use the ```Grant-``` cmdlet for a given policy type to assign the policy.</span></span> <span data-ttu-id="b12f4-189">Por exemplo, use o ```Grant-CsTeamsMeetingPolicy``` cmdlet para atribuir uma política de reunião do teams aos usuários.</span><span class="sxs-lookup"><span data-stu-id="b12f4-189">For example, use the ```Grant-CsTeamsMeetingPolicy``` cmdlet to assign a Teams meeting policy to users.</span></span> <span data-ttu-id="b12f4-190">Esses cmdlets estão incluídos no módulo do PowerShell do Skype for Business Online e são documentados na [referência do cmdlet do Skype for Business](https://docs.microsoft.com/powershell/skype/intro?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="b12f4-190">These cmdlets are included in the Skype for Business Online PowerShell module and are documented in the [Skype for Business cmdlet reference](https://docs.microsoft.com/powershell/skype/intro?view=skype-ps).</span></span>

 <span data-ttu-id="b12f4-191">Baixe e instale o [módulo do PowerShell do Skype for Business online](https://www.microsoft.com/en-us/download/details.aspx?id=39366) (caso ainda não tenha sido feito) e, em seguida, execute o seguinte para se conectar ao Skype for Business Online e iniciar uma sessão.</span><span class="sxs-lookup"><span data-stu-id="b12f4-191">Download and install the [Skype for Business Online PowerShell module](https://www.microsoft.com/en-us/download/details.aspx?id=39366) (if you haven't already), and then run the following to connect to Skype for Business Online and start a session.</span></span>

```powershell
Import-Module SkypeOnlineConnector
$Cred = Get-Credential
$CSSession = New-CsOnlineSession -Credential $Cred
Import-PSSession -Session $CSSession
```

<span data-ttu-id="b12f4-192">Neste exemplo, atribuímos uma política de reunião do teams chamada política de reunião do aluno a um usuário chamado Reda.</span><span class="sxs-lookup"><span data-stu-id="b12f4-192">In this example, we assign a Teams meeting policy named Student Meeting Policy to a user named Reda.</span></span>

```powershell
Grant-CsTeamsMeetingPolicy -Identity reda@contoso.com -PolicyName "Student Meeting Policy"
```

<span data-ttu-id="b12f4-193">Para saber mais, leia [gerenciar políticas pelo PowerShell](teams-powershell-managing-teams.md#manage-policies-via-powershell).</span><span class="sxs-lookup"><span data-stu-id="b12f4-193">To learn more, read [Managing policies via PowerShell](teams-powershell-managing-teams.md#manage-policies-via-powershell).</span></span>

## <a name="assign-a-policy-package"></a><span data-ttu-id="b12f4-194">Atribuir um pacote de política</span><span class="sxs-lookup"><span data-stu-id="b12f4-194">Assign a policy package</span></span>

<span data-ttu-id="b12f4-195">Um pacote de política no Teams é uma coleção de políticas predefinidas e configurações de política que você pode atribuir aos usuários que têm funções iguais ou semelhantes em sua organização.</span><span class="sxs-lookup"><span data-stu-id="b12f4-195">A policy package in Teams is a collection of predefined policies and policy settings that you can assign to users who have the same or similar roles in your organization.</span></span> <span data-ttu-id="b12f4-196">Cada pacote de política é projetado em torno de uma função de usuário e inclui políticas predefinidas e configurações de política que dão suporte a atividades típicas para essa função.</span><span class="sxs-lookup"><span data-stu-id="b12f4-196">Each policy package is designed around a user role and includes predefined policies and policy settings that support activities typical for that role.</span></span> <span data-ttu-id="b12f4-197">Alguns exemplos de pacotes de política são o pacote de educação (professor) e o pacote de assistência médica (funcionário clínico).</span><span class="sxs-lookup"><span data-stu-id="b12f4-197">Some examples of policy packages are the Education (Teacher) package and Healthcare (Clinical worker) package.</span></span>

<span data-ttu-id="b12f4-198">Quando você atribui um pacote de política aos usuários, as políticas no pacote são criadas e você pode personalizar as configurações de cada política no pacote para atender às necessidades dos usuários.</span><span class="sxs-lookup"><span data-stu-id="b12f4-198">When you assign a policy package to users, the policies in the package are created and you can then customize the settings of each policy in the package to meet users' needs.</span></span>

<span data-ttu-id="b12f4-199">Para saber mais sobre pacotes de política, incluindo orientação passo a passo sobre como atribuí-los e gerenciá-los, consulte [gerenciar pacotes de política no Microsoft Teams](manage-policy-packages.md).</span><span class="sxs-lookup"><span data-stu-id="b12f4-199">To learn more about policy packages, including step-by-step guidance on how to assign and manage them, see [Manage policy packages in Teams](manage-policy-packages.md).</span></span>

## <a name="assign-a-policy-to-a-batch-of-users"></a><span data-ttu-id="b12f4-200">Atribuir uma política a um lote de usuários</span><span class="sxs-lookup"><span data-stu-id="b12f4-200">Assign a policy to a batch of users</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="b12f4-201">Usando o centro de administração do Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="b12f4-201">Using the Microsoft Teams admin center</span></span>

<span data-ttu-id="b12f4-202">Para atribuir uma política a usuários em massa:</span><span class="sxs-lookup"><span data-stu-id="b12f4-202">To assign a policy to users in bulk:</span></span>

1. <span data-ttu-id="b12f4-203">Na navegação à esquerda do centro de administração do Microsoft Teams, selecione **usuários**.</span><span class="sxs-lookup"><span data-stu-id="b12f4-203">In the left navigation of the Microsoft Teams admin center, select **Users**.</span></span>
2. <span data-ttu-id="b12f4-204">Procure os usuários para os quais você deseja atribuir a política ou filtre o modo de exibição para mostrar os usuários que você deseja.</span><span class="sxs-lookup"><span data-stu-id="b12f4-204">Search for the users you want to assign the policy to or filter the view to show the users you want.</span></span>
3. <span data-ttu-id="b12f4-205">Na coluna **&#x2713;** (marca de seleção), selecione os usuários.</span><span class="sxs-lookup"><span data-stu-id="b12f4-205">In the **&#x2713;** (check mark) column, select the users.</span></span> <span data-ttu-id="b12f4-206">Para selecionar todos os usuários, clique na (marca de seleção) &#x2713; na parte superior da tabela.</span><span class="sxs-lookup"><span data-stu-id="b12f4-206">To select all users, click the &#x2713; (check mark) at the top of the table.</span></span>
4. <span data-ttu-id="b12f4-207">Clique em **Editar configurações**, faça as alterações desejadas e, em seguida, clique em **Aplicar**.</span><span class="sxs-lookup"><span data-stu-id="b12f4-207">Click **Edit settings**, make the changes that you want, and then click **Apply**.</span></span>

<span data-ttu-id="b12f4-208">Para exibir o status da atribuição da política, na faixa exibida na parte superior da página **usuários** depois que você clicar em **aplicar** para enviar a atribuição de política, clique em **registro de atividades**.</span><span class="sxs-lookup"><span data-stu-id="b12f4-208">To view the status of your policy assignment, in the banner that appears at the top of the **Users** page after you click **Apply** to submit your policy assignment, click **Activity log**.</span></span> <span data-ttu-id="b12f4-209">Ou, no painel de navegação esquerdo do centro de administração do Microsoft Teams, vá até **painel**e, em **registro de atividades**, clique em **Exibir detalhes**.</span><span class="sxs-lookup"><span data-stu-id="b12f4-209">Or, in the left navigation of the Microsoft Teams admin center, go to **Dashboard**, and then under **Activity log**, click **View details**.</span></span> <span data-ttu-id="b12f4-210">O registro de atividades mostra as atribuições de política para lotes de mais de 20 usuários por meio do centro de administração do Microsoft Teams dos últimos 30 dias.</span><span class="sxs-lookup"><span data-stu-id="b12f4-210">The Activity log shows policy assignments to batches of more than 20 users through the Microsoft Teams admin center from the last 30 days.</span></span> <span data-ttu-id="b12f4-211">Para saber mais, consulte [exibir suas atribuições de política no log de atividades](activity-log.md).</span><span class="sxs-lookup"><span data-stu-id="b12f4-211">To learn more, see [View your policy assignments in the Activity log](activity-log.md).</span></span>

### <a name="using-powershell"></a><span data-ttu-id="b12f4-212">Usando o PowerShell</span><span class="sxs-lookup"><span data-stu-id="b12f4-212">Using PowerShell</span></span>

> [!NOTE]
> <span data-ttu-id="b12f4-213">No momento, a atribuição de política em lote usando o PowerShell não está disponível para todos os tipos de política de equipe.</span><span class="sxs-lookup"><span data-stu-id="b12f4-213">Currently, batch policy assignment using PowerShell isn't available for all Teams policy types.</span></span> <span data-ttu-id="b12f4-214">Consulte [New-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation) para obter a lista de tipos de política com suporte.</span><span class="sxs-lookup"><span data-stu-id="b12f4-214">See [New-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation) for the list of supported policy types.</span></span>
 
<span data-ttu-id="b12f4-215">Com a atribuição de política em lotes, você pode atribuir uma política a grandes conjuntos de usuários de uma vez sem precisar usar um script.</span><span class="sxs-lookup"><span data-stu-id="b12f4-215">With batch policy assignment, you can assign a policy to large sets of users at a time without having to use a script.</span></span> <span data-ttu-id="b12f4-216">Use o ```New-CsBatchPolicyAssignmentOperation``` cmdlet para enviar um lote de usuários e a política que você deseja atribuir.</span><span class="sxs-lookup"><span data-stu-id="b12f4-216">You use the ```New-CsBatchPolicyAssignmentOperation``` cmdlet to submit a batch of users and the policy that you want to assign.</span></span> <span data-ttu-id="b12f4-217">As atribuições são processadas como uma operação em segundo plano e uma ID de operação é gerada para cada lote.</span><span class="sxs-lookup"><span data-stu-id="b12f4-217">The assignments are processed as a background operation and an operation ID is generated for each batch.</span></span> <span data-ttu-id="b12f4-218">Em seguida, você pode usar o ```Get-CsBatchPolicyAssignmentOperation``` cmdlet para acompanhar o progresso e o status das tarefas em um lote.</span><span class="sxs-lookup"><span data-stu-id="b12f4-218">You can then use the ```Get-CsBatchPolicyAssignmentOperation``` cmdlet to track the progress and status of the assignments in a batch.</span></span>

<span data-ttu-id="b12f4-219">Você pode especificar os usuários por seu ID de objeto ou endereço SIP (protocolo de iniciação de sessão).</span><span class="sxs-lookup"><span data-stu-id="b12f4-219">You can specify users by their object Id or Session Initiation Protocol (SIP) address.</span></span> <span data-ttu-id="b12f4-220">Observe que o endereço SIP de um usuário geralmente tem o mesmo valor que o nome UPN ou endereço de email, mas isso não é necessário.</span><span class="sxs-lookup"><span data-stu-id="b12f4-220">Note that a user's SIP address often has the same value as the User Principal Name (UPN) or email address, but this is not required.</span></span> <span data-ttu-id="b12f4-221">Se um usuário for especificado usando seu UPN ou email, mas tiver um valor diferente do endereço SIP, a atribuição de política falhará para o usuário.</span><span class="sxs-lookup"><span data-stu-id="b12f4-221">If a user is specified using their UPN or email, but it has a different value than their SIP address, then policy assignment will fail for the user.</span></span> <span data-ttu-id="b12f4-222">Se um lote incluir usuários duplicados, as duplicatas serão removidas do lote antes do processamento e o status só será fornecido para os usuários exclusivos restantes no lote.</span><span class="sxs-lookup"><span data-stu-id="b12f4-222">If a batch includes duplicate users, the duplicates will be removed from the batch before processing and status will only be provided for the unique users remaining in the batch.</span></span> 

<span data-ttu-id="b12f4-223">Um lote pode conter até 5.000 usuários.</span><span class="sxs-lookup"><span data-stu-id="b12f4-223">A batch can contain up to 5,000 users.</span></span> <span data-ttu-id="b12f4-224">Para obter melhores resultados, não envie mais do que alguns lotes de cada vez.</span><span class="sxs-lookup"><span data-stu-id="b12f4-224">For best results, do not submit more than a few batches at a time.</span></span> <span data-ttu-id="b12f4-225">Permitir que os lotes concluam o processamento antes de enviar mais lotes.</span><span class="sxs-lookup"><span data-stu-id="b12f4-225">Allow batches to complete processing before submitting more batches.</span></span>

#### <a name="install-and-connect-to-the-microsoft-teams-powershell-module"></a><span data-ttu-id="b12f4-226">Instalar e conectar-se ao módulo do PowerShell do Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="b12f4-226">Install and connect to the Microsoft Teams PowerShell module</span></span>

<span data-ttu-id="b12f4-227">Execute o seguinte para instalar o [módulo do Microsoft Teams PowerShell](https://www.powershellgallery.com/packages/MicrosoftTeams).</span><span class="sxs-lookup"><span data-stu-id="b12f4-227">Run the following to install the [Microsoft Teams PowerShell module](https://www.powershellgallery.com/packages/MicrosoftTeams).</span></span> <span data-ttu-id="b12f4-228">Verifique se você instalou a versão 1.0.5 ou posterior.</span><span class="sxs-lookup"><span data-stu-id="b12f4-228">Make sure you install version 1.0.5 or later.</span></span>

```powershell
Install-Module -Name MicrosoftTeams
```

<span data-ttu-id="b12f4-229">Execute o seguinte para se conectar ao Microsoft Teams e iniciar uma sessão.</span><span class="sxs-lookup"><span data-stu-id="b12f4-229">Run the following to connect to Teams and start a session.</span></span>

```powershell
Connect-MicrosoftTeams
```

<span data-ttu-id="b12f4-230">Quando for solicitado, entre usando suas credenciais de administrador.</span><span class="sxs-lookup"><span data-stu-id="b12f4-230">When you're prompted, sign in using your admin credentials.</span></span>

#### <a name="install-and-connect-to-the-azure-ad-powershell-for-graph-module-optional"></a><span data-ttu-id="b12f4-231">Instalar e conectar-se ao módulo do Azure AD PowerShell para Graph (opcional)</span><span class="sxs-lookup"><span data-stu-id="b12f4-231">Install and connect to the Azure AD PowerShell for Graph module (optional)</span></span>

<span data-ttu-id="b12f4-232">Você também pode [fazer o download e instalar o módulo do Azure ad PowerShell para Graph](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2) (se ainda não tiver feito isso) e se conectar ao Azure ad para que você possa recuperar uma lista de usuários em sua organização.</span><span class="sxs-lookup"><span data-stu-id="b12f4-232">You may also want to [download and install the Azure AD PowerShell for Graph module](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2) (if you haven't already) and connect to Azure AD so that you can retrieve a list of users in your organization.</span></span>

<span data-ttu-id="b12f4-233">Execute o seguinte para se conectar ao Azure AD.</span><span class="sxs-lookup"><span data-stu-id="b12f4-233">Run the following to connect to Azure AD.</span></span>

```powershell
Connect-AzureAD
```

<span data-ttu-id="b12f4-234">Quando for solicitado, entre usando as mesmas credenciais de administrador usadas para se conectar ao Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="b12f4-234">When you're prompted, sign in using the same admin credentials that you used to connect to Teams.</span></span>

#### <a name="assign-a-policy-to-a-batch-of-users"></a><span data-ttu-id="b12f4-235">Atribuir uma política a um lote de usuários</span><span class="sxs-lookup"><span data-stu-id="b12f4-235">Assign a policy to a batch of users</span></span>

<span data-ttu-id="b12f4-236">Neste exemplo, usamos o ```New-CsBatchPolicyAssignmentOperation``` cmdlet para atribuir uma política de configuração de aplicativo chamada política de configuração de aplicativo de RH a um lote de usuários listados no arquivo Users_ids. texto.</span><span class="sxs-lookup"><span data-stu-id="b12f4-236">In this example, we use the ```New-CsBatchPolicyAssignmentOperation``` cmdlet to assign an app setup policy named HR App Setup Policy to a batch of users listed in the Users_ids.text file.</span></span>

```powershell
$user_ids = Get-Content .\users_ids.txt
New-CsBatchPolicyAssignmentOperation -PolicyType TeamsAppSetupPolicy -PolicyName "HR App Setup Policy" -Identity $users_ids -OperationName "Example 1 batch"
```

<span data-ttu-id="b12f4-237">Neste exemplo, nós nos conectamos ao Azure AD para recuperar uma coleção de usuários e atribuir uma política de mensagens chamada novo contratar política de mensagens a um lote de usuários especificados usando o endereço SIP.</span><span class="sxs-lookup"><span data-stu-id="b12f4-237">In this example, we connect to Azure AD to retrieve a collection of users and then assign a messaging policy named New Hire Messaging Policy to a batch of users specified by using their SIP address.</span></span>

```powershell
Connect-AzureAD
$users = Get-AzureADUser
New-CsBatchPolicyAssignmentOperation -PolicyType TeamsMessagingPolicy -PolicyName "New Hire Messaging Policy" -Identity $users.SipProxyAddress -OperationName "Example 2 batch"
```

<span data-ttu-id="b12f4-238">Para saber mais, confira [novo – CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation).</span><span class="sxs-lookup"><span data-stu-id="b12f4-238">To learn more, see [New-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation).</span></span>

#### <a name="get-the-status-of-a-batch-assignment"></a><span data-ttu-id="b12f4-239">Obter o status de uma atribuição em lote</span><span class="sxs-lookup"><span data-stu-id="b12f4-239">Get the status of a batch assignment</span></span>

<span data-ttu-id="b12f4-240">Execute o seguinte para obter o status de uma atribuição em lotes, em que operationId é a ID da operação retornada pelo ```New-CsBatchPolicyAssignmentOperation``` cmdlet para um determinado lote.</span><span class="sxs-lookup"><span data-stu-id="b12f4-240">Run the following to get the status of a batch assignment, where OperationId is the operation ID that's returned by the ```New-CsBatchPolicyAssignmentOperation``` cmdlet for a given batch.</span></span>

```powershell
$Get-CsBatchPolicyAssignmentOperation -OperationId f985e013-0826-40bb-8c94-e5f367076044 | fl
```

<span data-ttu-id="b12f4-241">Se a saída mostrar que ocorreu um erro, execute o seguinte para obter mais informações sobre erros, que estão na ```UserState``` propriedade.</span><span class="sxs-lookup"><span data-stu-id="b12f4-241">If the output shows that an error occurred, run the following to get more information about errors, which are in the ```UserState``` property.</span></span>

```powershell
Get-CsBatchPolicyAssignmentOperation -OperationId f985e013-0826-40bb-8c94-e5f367076044 | Select -ExpandProperty UserState
```

<span data-ttu-id="b12f4-242">Para saber mais, consulte [Get-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/get-csbatchpolicyassignmentoperation).</span><span class="sxs-lookup"><span data-stu-id="b12f4-242">To learn more, see [Get-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/get-csbatchpolicyassignmentoperation).</span></span>

## <a name="assign-a-policy-to-a-group"></a><span data-ttu-id="b12f4-243">Atribuir uma política a um grupo</span><span class="sxs-lookup"><span data-stu-id="b12f4-243">Assign a policy to a group</span></span>

<span data-ttu-id="b12f4-244">A atribuição de política a grupos permite atribuir uma política a um grupo de usuários, como um grupo de segurança ou unidade organizacional.</span><span class="sxs-lookup"><span data-stu-id="b12f4-244">Policy assignment to groups lets you assign a policy to a group of users, such as a security group or organizational unit.</span></span> <span data-ttu-id="b12f4-245">A atribuição de política é propagada para os membros do grupo de acordo com as regras de precedência.</span><span class="sxs-lookup"><span data-stu-id="b12f4-245">The policy assignment is propagated to members of the group according to precedence rules.</span></span> <span data-ttu-id="b12f4-246">Conforme os membros são adicionados ou removidos de um grupo, suas atribuições de política herdadas são atualizadas de acordo.</span><span class="sxs-lookup"><span data-stu-id="b12f4-246">As members are added to or removed from a group, their inherited policy assignments are updated accordingly.</span></span>

<span data-ttu-id="b12f4-247">A atribuição de política a grupos é recomendada para grupos de até 50.000 usuários, mas também funciona com grupos maiores.</span><span class="sxs-lookup"><span data-stu-id="b12f4-247">Policy assignment to groups is recommended for groups of up to 50,000 users but it will also work with larger groups.</span></span>

<span data-ttu-id="b12f4-248">Quando você atribui a política, ela é imediatamente atribuída ao grupo.</span><span class="sxs-lookup"><span data-stu-id="b12f4-248">When you assign the policy, it's immediately assigned to the group.</span></span> <span data-ttu-id="b12f4-249">No entanto, observe que a propagação da atribuição da política para os membros do grupo é realizada como uma operação em segundo plano e pode demorar algum tempo, dependendo do tamanho do grupo.</span><span class="sxs-lookup"><span data-stu-id="b12f4-249">However, note that the propagation of the policy assignment to members of the group is performed as a background operation and may take some time, depending on the size of the group.</span></span> <span data-ttu-id="b12f4-250">O mesmo é verdadeiro quando uma política é desatribuída de um grupo ou quando os membros são adicionados ou removidos de um grupo.</span><span class="sxs-lookup"><span data-stu-id="b12f4-250">The same is true when a policy is unassigned from a group, or when members are added to or removed from a group.</span></span>

### <a name="what-you-need-to-know-about-policy-assignment-to-groups"></a><span data-ttu-id="b12f4-251">O que você precisa saber sobre atribuição de política a grupos</span><span class="sxs-lookup"><span data-stu-id="b12f4-251">What you need to know about policy assignment to groups</span></span>

<span data-ttu-id="b12f4-252">Antes de começar, é importante entender as regras de precedência e a classificação de atribuição de grupo.</span><span class="sxs-lookup"><span data-stu-id="b12f4-252">Before you get started, it's important to understand precedence rules and group assignment ranking.</span></span>

#### <a name="precedence-rules"></a><span data-ttu-id="b12f4-253">Regras de precedência</span><span class="sxs-lookup"><span data-stu-id="b12f4-253">Precedence rules</span></span>

<span data-ttu-id="b12f4-254">Para um determinado tipo de política, a política efetiva de um usuário é determinada de acordo com o seguinte:</span><span class="sxs-lookup"><span data-stu-id="b12f4-254">For a given policy type, a user's effective policy is determined according to the following:</span></span>

- <span data-ttu-id="b12f4-255">Uma política que é atribuída diretamente a um usuário tem precedência sobre qualquer outra política do mesmo tipo que esteja atribuída a um grupo.</span><span class="sxs-lookup"><span data-stu-id="b12f4-255">A policy that's directly assigned to a user takes precedence over any other policy of the same type that's assigned to a group.</span></span> <span data-ttu-id="b12f4-256">Em outras palavras, se um usuário estiver diretamente atribuído a uma política de um determinado tipo, esse usuário não herdará uma política do mesmo tipo de um grupo.</span><span class="sxs-lookup"><span data-stu-id="b12f4-256">In other words, if a user is directly assigned a policy of a given type, that user won't inherit a policy of the same type from a group.</span></span> <span data-ttu-id="b12f4-257">Isso também significa que, se um usuário tiver uma política de um determinado tipo que foi atribuído diretamente a ele, será necessário remover essa política do usuário antes de poder herdar uma política do mesmo tipo de um grupo.</span><span class="sxs-lookup"><span data-stu-id="b12f4-257">This also means that if a user has a policy of a given type that was directly assigned to them, you have to remove that policy from the user before they can inherit a policy of the same type from a group.</span></span>
- <span data-ttu-id="b12f4-258">Se um usuário não tiver uma política diretamente atribuída a ele e for um membro de dois ou mais grupos e cada grupo tiver uma política do mesmo tipo atribuído a ele, o usuário herdará a política da atribuição de grupo que tem a classificação mais alta.</span><span class="sxs-lookup"><span data-stu-id="b12f4-258">If a user doesn't have a policy directly assigned to them and is a member of two or more groups and each group has a policy of the same type assigned to it, the user inherits the policy of the group assignment that has the highest ranking.</span></span>
- <span data-ttu-id="b12f4-259">Se um usuário não for membro de nenhum grupo ao qual uma política atribuiu uma política, a política global (padrão para toda a organização) para esse tipo de política se aplicará ao usuário.</span><span class="sxs-lookup"><span data-stu-id="b12f4-259">If a user isn't a member of any groups that are assigned a policy, the global (Org-wide default) policy for that policy type applies to the user.</span></span>

<span data-ttu-id="b12f4-260">A política efetiva de um usuário é atualizada de acordo com essas regras quando um usuário é adicionado ou removido de um grupo que é atribuído a uma política, uma política é desatribuída de um grupo ou uma política diretamente atribuída ao usuário é removida.</span><span class="sxs-lookup"><span data-stu-id="b12f4-260">A user's effective policy is updated according to these rules when a user is added to or removed from a group that's assigned a policy, a policy is unassigned from a group, or a policy that's directly assigned to the user is removed.</span></span>

#### <a name="group-assignment-ranking"></a><span data-ttu-id="b12f4-261">Classificação de atribuição de grupo</span><span class="sxs-lookup"><span data-stu-id="b12f4-261">Group assignment ranking</span></span>
 
<span data-ttu-id="b12f4-262">Ao atribuir uma política a um grupo, você especifica uma classificação para a atribuição de grupo.</span><span class="sxs-lookup"><span data-stu-id="b12f4-262">When you assign a policy to a group, you specify a ranking for the group assignment.</span></span> <span data-ttu-id="b12f4-263">Isso é usado para determinar qual política um usuário deve herdar como política efetiva se o usuário for membro de dois ou mais grupos e cada grupo tiver atribuído uma política do mesmo tipo.</span><span class="sxs-lookup"><span data-stu-id="b12f4-263">This is used to determine which policy a user should inherit as their effective policy if the user is a member of two or more groups and each group is assigned a policy of the same type.</span></span>

<span data-ttu-id="b12f4-264">A classificação da atribuição de grupo é relativa a outras tarefas de grupo do mesmo tipo.</span><span class="sxs-lookup"><span data-stu-id="b12f4-264">The group assignment ranking is relative to other group assignments of the same type.</span></span> <span data-ttu-id="b12f4-265">Por exemplo, se você estiver atribuindo uma política de chamada a dois grupos, defina a classificação de uma tarefa como 1 e a outra como 2, com 1 sendo a classificação mais alta.</span><span class="sxs-lookup"><span data-stu-id="b12f4-265">For example, if you're assigning a calling policy to two groups, set the ranking of one assignment to 1 and the other to 2, with 1 being the highest ranking.</span></span> <span data-ttu-id="b12f4-266">A classificação de atribuição de grupo indica qual associação de grupo é mais importante ou mais relevante do que outras associações de grupo em relação à herança.</span><span class="sxs-lookup"><span data-stu-id="b12f4-266">The group assignment ranking indicates which group membership is more important or more relevant than other group memberships with regards to inheritance.</span></span>
 
<span data-ttu-id="b12f4-267">Digamos, por exemplo, que você tem dois grupos, armazenar funcionários e gerentes da loja.</span><span class="sxs-lookup"><span data-stu-id="b12f4-267">Say, for example, you have two groups, Store Employees and Store Managers.</span></span> <span data-ttu-id="b12f4-268">Os dois grupos recebem uma política de chamada de equipes, armazenando a política de chamadas de gerentes de loja e a política de chamadas de gerentes de loja</span><span class="sxs-lookup"><span data-stu-id="b12f4-268">Both groups are assigned a Teams calling policy, Store Employees Calling Policy and Store Managers Calling Policy, respectively.</span></span> <span data-ttu-id="b12f4-269">Para um gerente de loja que está em ambos os grupos, sua função como gerente é mais relevante do que a função de um funcionário, portanto, a política de chamada atribuída ao grupo de gerentes da loja deve ter uma classificação mais alta.</span><span class="sxs-lookup"><span data-stu-id="b12f4-269">For a store manager who is in both groups, their role as a manager is more relevant than their role as an employee, so the calling policy that's assigned to the Store Managers group should have a higher ranking.</span></span>

|<span data-ttu-id="b12f4-270">Grupos</span><span class="sxs-lookup"><span data-stu-id="b12f4-270">Group</span></span> |<span data-ttu-id="b12f4-271">Nome da política de chamada de equipes</span><span class="sxs-lookup"><span data-stu-id="b12f4-271">Teams calling policy name</span></span>  |<span data-ttu-id="b12f4-272">Classificação</span><span class="sxs-lookup"><span data-stu-id="b12f4-272">Rank</span></span>|
|---------|---------|---|
|<span data-ttu-id="b12f4-273">Gerentes da loja</span><span class="sxs-lookup"><span data-stu-id="b12f4-273">Store Managers</span></span>   |<span data-ttu-id="b12f4-274">Política de chamadas de gerentes de loja</span><span class="sxs-lookup"><span data-stu-id="b12f4-274">Store Managers Calling Policy</span></span>         |<span data-ttu-id="b12f4-275">1</span><span class="sxs-lookup"><span data-stu-id="b12f4-275">1</span></span>|
|<span data-ttu-id="b12f4-276">Loja de funcionários</span><span class="sxs-lookup"><span data-stu-id="b12f4-276">Store Employees</span></span>    |<span data-ttu-id="b12f4-277">Política de chamadas de funcionários da loja</span><span class="sxs-lookup"><span data-stu-id="b12f4-277">Store Employees Calling Policy</span></span>      |<span data-ttu-id="b12f4-278">2</span><span class="sxs-lookup"><span data-stu-id="b12f4-278">2</span></span>|

<span data-ttu-id="b12f4-279">Se você não especificar uma classificação, a atribuição de política terá a classificação mais baixa.</span><span class="sxs-lookup"><span data-stu-id="b12f4-279">If you don't specify a ranking, the policy assignment is given the lowest ranking.</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="b12f4-280">Usando o centro de administração do Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="b12f4-280">Using the Microsoft Teams admin center</span></span>

<span data-ttu-id="b12f4-281">**Este recurso ainda não foi lançado. Ele foi anunciado e estará disponível em breve.**</span><span class="sxs-lookup"><span data-stu-id="b12f4-281">**This feature hasn't yet been released. It's been announced, and it's coming soon.**</span></span>

> [!NOTE]
> <span data-ttu-id="b12f4-282">Atualmente, a atribuição de política a grupos usando o centro de administração do Microsoft Teams está disponível apenas para política de chamada de equipes, política de reunião do Teams e política de mensagens de equipe.</span><span class="sxs-lookup"><span data-stu-id="b12f4-282">Currently, policy assignment to groups using the Microsoft Teams admin center is only available for Teams calling policy, Teams meeting policy, and Teams messaging policy.</span></span> <span data-ttu-id="b12f4-283">Para outros tipos de política, use o PowerShell.</span><span class="sxs-lookup"><span data-stu-id="b12f4-283">For other policy types, use PowerShell.</span></span>

1. <span data-ttu-id="b12f4-284">Na navegação à esquerda do centro de administração do Microsoft Teams, vá para a página tipo de política.</span><span class="sxs-lookup"><span data-stu-id="b12f4-284">In the left navigation of the Microsoft Teams admin center, go to the policy type page.</span></span> <span data-ttu-id="b12f4-285">Por exemplo, acesse **Meetings**  >  **políticas de reunião**de reuniões.</span><span class="sxs-lookup"><span data-stu-id="b12f4-285">For example, go to **Meetings** > **Meeting policies**.</span></span>
2. <span data-ttu-id="b12f4-286">Selecione a guia **atribuição de política de grupo** .</span><span class="sxs-lookup"><span data-stu-id="b12f4-286">Select the **Group policy assignment** tab.</span></span>
3. <span data-ttu-id="b12f4-287">Selecione **Adicionar grupo**e, em seguida, no painel **atribuir política ao grupo** , faça o seguinte:</span><span class="sxs-lookup"><span data-stu-id="b12f4-287">Select **Add group**, and then in the **Assign policy to group** pane, do the following:</span></span>
    1. <span data-ttu-id="b12f4-288">Procure e adicione o grupo ao qual você deseja atribuir a política.</span><span class="sxs-lookup"><span data-stu-id="b12f4-288">Search for and add the group you want to assign the policy to.</span></span>
    2. <span data-ttu-id="b12f4-289">Defina a classificação para a atribuição de grupo.</span><span class="sxs-lookup"><span data-stu-id="b12f4-289">Set the ranking for the group assignment.</span></span>
    3. <span data-ttu-id="b12f4-290">Selecione a política que você deseja atribuir.</span><span class="sxs-lookup"><span data-stu-id="b12f4-290">Select the policy that you want to assign.</span></span> 
    4. <span data-ttu-id="b12f4-291">Selecione **aplicar**.</span><span class="sxs-lookup"><span data-stu-id="b12f4-291">Select **Apply**.</span></span>

<span data-ttu-id="b12f4-292">Para remover uma atribuição de política de grupo, na guia **atribuição de política de grupo** da página política, selecione a atribuição de grupo e, em seguida, selecione **remover**.</span><span class="sxs-lookup"><span data-stu-id="b12f4-292">To remove a group policy assignment, on the **Group policy assignment** tab of the policy page, select the group assignment, and then select **Remove**.</span></span>

<span data-ttu-id="b12f4-293">Para alterar a classificação de uma atribuição de grupo, primeiro você precisa remover a atribuição de política de grupo.</span><span class="sxs-lookup"><span data-stu-id="b12f4-293">To change the ranking of a group assignment, you have to first remove the group policy assignment.</span></span> <span data-ttu-id="b12f4-294">Em seguida, siga as etapas acima para atribuir a política a um grupo.</span><span class="sxs-lookup"><span data-stu-id="b12f4-294">Then, follow the steps above to assign the policy to a group.</span></span>

### <a name="using-powershell"></a><span data-ttu-id="b12f4-295">Usando o PowerShell</span><span class="sxs-lookup"><span data-stu-id="b12f4-295">Using PowerShell</span></span>

> [!NOTE]
> <span data-ttu-id="b12f4-296">Atualmente, a atribuição de política a grupos usando o PowerShell não está disponível para todos os tipos de política de equipe.</span><span class="sxs-lookup"><span data-stu-id="b12f4-296">Currently, policy assignment to groups using PowerShell isn't available for all Teams policy types.</span></span> <span data-ttu-id="b12f4-297">Consulte [New-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/new-csgrouppolicyassignment) para obter a lista de tipos de política com suporte.</span><span class="sxs-lookup"><span data-stu-id="b12f4-297">See [New-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/new-csgrouppolicyassignment) for the list of supported policy types.</span></span>

#### <a name="install-and-connect-to-the-microsoft-teams-powershell-module"></a><span data-ttu-id="b12f4-298">Instalar e conectar-se ao módulo do PowerShell do Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="b12f4-298">Install and connect to the Microsoft Teams PowerShell module</span></span>

<span data-ttu-id="b12f4-299">Para obter orientação passo a passo, consulte instalar o PowerShell do Microsoft [Teams](teams-powershell-install.md).</span><span class="sxs-lookup"><span data-stu-id="b12f4-299">For step-by-step guidance, see [Install Teams PowerShell](teams-powershell-install.md).</span></span>

#### <a name="assign-a-policy-to-a-group"></a><span data-ttu-id="b12f4-300">Atribuir uma política a um grupo</span><span class="sxs-lookup"><span data-stu-id="b12f4-300">Assign a policy to a group</span></span>

<span data-ttu-id="b12f4-301">Use o ```New-CsGroupPolicyAssignment``` cmdlet para atribuir uma política a um grupo.</span><span class="sxs-lookup"><span data-stu-id="b12f4-301">You use the ```New-CsGroupPolicyAssignment``` cmdlet to assign a policy to a group.</span></span> <span data-ttu-id="b12f4-302">Você pode especificar um grupo usando a identificação do objeto, o endereço SIP ou o endereço de email.</span><span class="sxs-lookup"><span data-stu-id="b12f4-302">You can specify a group by using the object Id, SIP address, or email address.</span></span>

<span data-ttu-id="b12f4-303">Neste exemplo, usamos o ```New-CsGroupPolicyAssignment``` cmdlet para atribuir uma política de reunião do teams chamada política de reunião de gerentes de revenda a um grupo com uma classificação de atribuição de 1.</span><span class="sxs-lookup"><span data-stu-id="b12f4-303">In this example, we use the ```New-CsGroupPolicyAssignment``` cmdlet to assign a Teams meeting policy named Retail Managers Meeting Policy to a group with an assignment ranking of 1.</span></span>

```powershell
New-CsGroupPolicyAssignment -GroupId d8ebfa45-0f28-4d2d-9bcc-b158a49e2d17 -PolicyType TeamsMeetingPolicy -PolicyName "Retail Managers Meeting Policy" -Rank 1
```

<span data-ttu-id="b12f4-304">Para saber mais, confira [novo – CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/new-csgrouppolicyassignment).</span><span class="sxs-lookup"><span data-stu-id="b12f4-304">To learn more, see [New-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/new-csgrouppolicyassignment).</span></span>

#### <a name="get-policy-assignments-for-a-group"></a><span data-ttu-id="b12f4-305">Obter atribuições de política para um grupo</span><span class="sxs-lookup"><span data-stu-id="b12f4-305">Get policy assignments for a group</span></span>

<span data-ttu-id="b12f4-306">Use o ```Get-CsGroupPolicyAssignment``` cmdlet para obter todas as políticas atribuídas a um grupo.</span><span class="sxs-lookup"><span data-stu-id="b12f4-306">Use the ```Get-CsGroupPolicyAssignment``` cmdlet to get all policies assigned to a group.</span></span> <span data-ttu-id="b12f4-307">Observe que os grupos são sempre listados pela ID do grupo mesmo se seu endereço SIP ou endereço de email foi usado para atribuir a política.</span><span class="sxs-lookup"><span data-stu-id="b12f4-307">Note that groups are always listed by their group Id even if its SIP address or email address was used to assign the policy.</span></span>

<span data-ttu-id="b12f4-308">Neste exemplo, recuperamos todas as políticas atribuídas a um grupo específico.</span><span class="sxs-lookup"><span data-stu-id="b12f4-308">In this example, we retrieve all policies assigned to a specific group.</span></span>

```powershell
Get-CsGroupPolicyAssignment -GroupId e050ce51-54bc-45b7-b3e6-c00343d31274
```

<span data-ttu-id="b12f4-309">Neste exemplo, retornamos todos os grupos que recebem uma política de reunião do teams.</span><span class="sxs-lookup"><span data-stu-id="b12f4-309">In this example, we return all groups that are assigned a Teams meeting policy.</span></span>

```powershell
Get-CsGroupPolicyAssignment -PolicyType TeamsMeetingPolicy
```

<span data-ttu-id="b12f4-310">Para saber mais, consulte [Get-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/get-csgrouppolicyassignment).</span><span class="sxs-lookup"><span data-stu-id="b12f4-310">To learn more, see [Get-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/get-csgrouppolicyassignment).</span></span>

#### <a name="remove-a-policy-from-a-group"></a><span data-ttu-id="b12f4-311">Remover uma política de um grupo</span><span class="sxs-lookup"><span data-stu-id="b12f4-311">Remove a policy from a group</span></span>

<span data-ttu-id="b12f4-312">Use o ```Remove-CsGroupPolicyAssignment``` cmdlet para remover uma política de um grupo.</span><span class="sxs-lookup"><span data-stu-id="b12f4-312">Use the ```Remove-CsGroupPolicyAssignment``` cmdlet to remove a policy from a group.</span></span> <span data-ttu-id="b12f4-313">Quando você remove uma política de um grupo, as prioridades de outras políticas do mesmo tipo atribuídas a esse grupo e que têm uma classificação mais baixa são atualizadas.</span><span class="sxs-lookup"><span data-stu-id="b12f4-313">When you remove a policy from a group, the priorities of other policies of the same type assigned to that group and that have a lower ranking are updated.</span></span> <span data-ttu-id="b12f4-314">Por exemplo, se você remover uma política que tem uma classificação de 2, as políticas que têm uma classificação de 3 e 4 são atualizadas para refletir a nova classificação.</span><span class="sxs-lookup"><span data-stu-id="b12f4-314">For example, if you remove a policy that has a ranking of 2, policies that have a ranking of 3 and 4 are updated to reflect their new ranking.</span></span> <span data-ttu-id="b12f4-315">As duas tabelas a seguir mostram este exemplo.</span><span class="sxs-lookup"><span data-stu-id="b12f4-315">The following two tables show this example.</span></span>

<span data-ttu-id="b12f4-316">Aqui está uma lista das atribuições e prioridades de política para uma política de reunião do teams.</span><span class="sxs-lookup"><span data-stu-id="b12f4-316">Here's a list of the policy assignments and priorities for a Teams meeting policy.</span></span>

|<span data-ttu-id="b12f4-317">Nome do grupo</span><span class="sxs-lookup"><span data-stu-id="b12f4-317">Group name</span></span>  |<span data-ttu-id="b12f4-318">Nome da política</span><span class="sxs-lookup"><span data-stu-id="b12f4-318">Policy name</span></span>  |<span data-ttu-id="b12f4-319">Classificação</span><span class="sxs-lookup"><span data-stu-id="b12f4-319">Rank</span></span>|
|---------|---------|---------|
|<span data-ttu-id="b12f4-320">Vendas</span><span class="sxs-lookup"><span data-stu-id="b12f4-320">Sales</span></span>    |<span data-ttu-id="b12f4-321">Política de vendas</span><span class="sxs-lookup"><span data-stu-id="b12f4-321">Sales policy</span></span>       | <span data-ttu-id="b12f4-322">1</span><span class="sxs-lookup"><span data-stu-id="b12f4-322">1</span></span>        |
|<span data-ttu-id="b12f4-323">Região oeste</span><span class="sxs-lookup"><span data-stu-id="b12f4-323">West Region</span></span>     |<span data-ttu-id="b12f4-324">Política de região oeste</span><span class="sxs-lookup"><span data-stu-id="b12f4-324">West Region policy</span></span>         |<span data-ttu-id="b12f4-325">2</span><span class="sxs-lookup"><span data-stu-id="b12f4-325">2</span></span>         |
|<span data-ttu-id="b12f4-326">Visões</span><span class="sxs-lookup"><span data-stu-id="b12f4-326">Division</span></span>    |<span data-ttu-id="b12f4-327">Política de divisão</span><span class="sxs-lookup"><span data-stu-id="b12f4-327">Division policy</span></span>         |<span data-ttu-id="b12f4-328">3</span><span class="sxs-lookup"><span data-stu-id="b12f4-328">3</span></span>         |
|<span data-ttu-id="b12f4-329">Subsidiária da</span><span class="sxs-lookup"><span data-stu-id="b12f4-329">Subsidiary</span></span>   |<span data-ttu-id="b12f4-330">Política da subsidiária</span><span class="sxs-lookup"><span data-stu-id="b12f4-330">Subsidiary policy</span></span>        |<span data-ttu-id="b12f4-331">4</span><span class="sxs-lookup"><span data-stu-id="b12f4-331">4</span></span>         |

<span data-ttu-id="b12f4-332">Se removermos a política de região oeste do grupo região oeste, as atribuições e prioridades de política serão atualizadas da maneira a seguir.</span><span class="sxs-lookup"><span data-stu-id="b12f4-332">If we remove the West Region policy from the West Region group, the policy assignments and priorities are updated as follows.</span></span>

|<span data-ttu-id="b12f4-333">Nome do grupo</span><span class="sxs-lookup"><span data-stu-id="b12f4-333">Group name</span></span>  |<span data-ttu-id="b12f4-334">Nome da política</span><span class="sxs-lookup"><span data-stu-id="b12f4-334">Policy name</span></span>  |<span data-ttu-id="b12f4-335">Classificação</span><span class="sxs-lookup"><span data-stu-id="b12f4-335">Rank</span></span>|
|---------|---------|---------|
|<span data-ttu-id="b12f4-336">Vendas</span><span class="sxs-lookup"><span data-stu-id="b12f4-336">Sales</span></span>    |<span data-ttu-id="b12f4-337">Política de vendas</span><span class="sxs-lookup"><span data-stu-id="b12f4-337">Sales policy</span></span>       | <span data-ttu-id="b12f4-338">1</span><span class="sxs-lookup"><span data-stu-id="b12f4-338">1</span></span>        |
|<span data-ttu-id="b12f4-339">Visões</span><span class="sxs-lookup"><span data-stu-id="b12f4-339">Division</span></span>    |<span data-ttu-id="b12f4-340">Política de divisão</span><span class="sxs-lookup"><span data-stu-id="b12f4-340">Division policy</span></span>         |<span data-ttu-id="b12f4-341">2</span><span class="sxs-lookup"><span data-stu-id="b12f4-341">2</span></span>         |
|<span data-ttu-id="b12f4-342">Subsidiária da</span><span class="sxs-lookup"><span data-stu-id="b12f4-342">Subsidiary</span></span>   |<span data-ttu-id="b12f4-343">Política da subsidiária</span><span class="sxs-lookup"><span data-stu-id="b12f4-343">Subsidiary policy</span></span>        |<span data-ttu-id="b12f4-344">3</span><span class="sxs-lookup"><span data-stu-id="b12f4-344">3</span></span>        |

<span data-ttu-id="b12f4-345">Neste exemplo, removemos a política de reunião do teams de um grupo.</span><span class="sxs-lookup"><span data-stu-id="b12f4-345">In this example, we remove the Teams meeting policy from a group.</span></span>

```powershell
Remove-CsGroupPolicyAssignment -PolicyType TeamsMeetingPolicy -GroupId f985e013-0826-40bb-8c94-e5f367076044
```

<span data-ttu-id="b12f4-346">Para saber mais, veja [Remove-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/remove-csgrouppolicyassignment).</span><span class="sxs-lookup"><span data-stu-id="b12f4-346">To learn more, see [Remove-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/remove-csgrouppolicyassignment).</span></span>

#### <a name="change-a-policy-assignment-for-a-group"></a><span data-ttu-id="b12f4-347">Alterar uma atribuição de política para um grupo</span><span class="sxs-lookup"><span data-stu-id="b12f4-347">Change a policy assignment for a group</span></span>

> [!NOTE]
> <span data-ttu-id="b12f4-348">O ```Set-CsGroupPolicyAssignment``` cmdlet estará disponível em breve.</span><span class="sxs-lookup"><span data-stu-id="b12f4-348">The ```Set-CsGroupPolicyAssignment``` cmdlet will be available soon.</span></span> <span data-ttu-id="b12f4-349">Enquanto isso, para alterar uma atribuição de política de grupo, você pode remover a atribuição de política atual do grupo e, em seguida, adicionar uma nova atribuição de política.</span><span class="sxs-lookup"><span data-stu-id="b12f4-349">In the meantime, to change a group policy assignment, you can remove the current policy assignment from the group, and then add a new policy assignment.</span></span>

<span data-ttu-id="b12f4-350">Depois de atribuir uma política a um grupo, você pode usar o ```Set-CsGroupPolicyAssignment``` cmdlet para alterar a atribuição da política desse grupo da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="b12f4-350">After you assign a policy to a group, you can use the ```Set-CsGroupPolicyAssignment``` cmdlet to change that group's policy assignment as follows:</span></span>

- <span data-ttu-id="b12f4-351">Alterar a classificação</span><span class="sxs-lookup"><span data-stu-id="b12f4-351">Change the ranking</span></span>
- <span data-ttu-id="b12f4-352">Alterar a política de um determinado tipo de política</span><span class="sxs-lookup"><span data-stu-id="b12f4-352">Change the policy of a given policy type</span></span>
- <span data-ttu-id="b12f4-353">Alterar a política de um determinado tipo de política e a classificação</span><span class="sxs-lookup"><span data-stu-id="b12f4-353">Change the policy of a given policy type and the ranking</span></span>

<span data-ttu-id="b12f4-354">Neste exemplo, alteramos a política de estacionamento de chamada de equipe de um grupo para uma política chamada SupportCallPark e a classificação de atribuição para 3.</span><span class="sxs-lookup"><span data-stu-id="b12f4-354">In this example, we change a group's Teams call park policy to a policy named SupportCallPark and the assignment ranking to 3.</span></span>

```powershell
Set-CsGroupPolicyAssignment -GroupId 566b8d39-5c5c-4aaa-bc07-4f36278a1b38 -PolicyType TeamsMeetingPolicy -PolicyName SupportCallPark -Rank 3
```

<span data-ttu-id="b12f4-355">Para saber mais, consulte [set-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/set-csgrouppolicyassignment).</span><span class="sxs-lookup"><span data-stu-id="b12f4-355">To learn more, see [Set-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/set-csgrouppolicyassignment).</span></span>



#### <a name="change-the-effective-policy-for-a-user"></a><span data-ttu-id="b12f4-356">Alterar a política em vigor para um usuário</span><span class="sxs-lookup"><span data-stu-id="b12f4-356">Change the effective policy for a user</span></span>

<span data-ttu-id="b12f4-357">Aqui está um exemplo de como alterar a política efetiva para um usuário que recebe diretamente uma política.</span><span class="sxs-lookup"><span data-stu-id="b12f4-357">Here's an example of how to change the effective policy for a user who is directly assigned a policy.</span></span>

<span data-ttu-id="b12f4-358">Primeiro, usamos o ```Get-CsUserPolicyAssignment``` cmdlet em conjunto com o ```PolicySource``` parâmetro para obter detalhes das políticas de transmissão de reunião do teams associadas ao usuário.</span><span class="sxs-lookup"><span data-stu-id="b12f4-358">First, we use the ```Get-CsUserPolicyAssignment``` cmdlet together with the ```PolicySource``` parameter to get details of the Teams meeting broadcast policies associated with the user.</span></span> <span data-ttu-id="b12f4-359">Para saber mais, consulte [Get-CsUserPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/get-csuserpolicyassignment).</span><span class="sxs-lookup"><span data-stu-id="b12f4-359">To learn more, see [Get-CsUserPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/get-csuserpolicyassignment).</span></span>

```powershell
Get-CsUserPolicyAssignment -Identity daniel@contoso.com -PolicyType TeamsMeetingBroadcastPolicy | select -ExpandProperty PolicySource
```

<span data-ttu-id="b12f4-360">A saída mostra que o usuário foi diretamente atribuído a uma política de transmissão de reunião do teams chamada eventos do funcionário, que tem precedência sobre a política denominada eventos dinâmicos do fornecedor que é atribuída a um grupo ao qual o usuário pertence.</span><span class="sxs-lookup"><span data-stu-id="b12f4-360">The output shows that the user was directly assigned a Teams meeting broadcast policy named Employee Events, which takes precedence over the policy named Vendor Live Events that's assigned to a group the user belongs to.</span></span>

```console
AssignmentType PolicyName         Reference
-------------- ----------         ---------
Direct         Employee Events
Group          Vendor Live Events 566b8d39-5c5c-4aaa-bc07-4f36278a1b38
```

<span data-ttu-id="b12f4-361">Agora, removemos a política de eventos de funcionários do usuário.</span><span class="sxs-lookup"><span data-stu-id="b12f4-361">Now, we remove the Employee Events policy from the user.</span></span> <span data-ttu-id="b12f4-362">Isso significa que o usuário não tem mais uma política de transmissão de reunião do teams diretamente atribuída a elas e herdará a política de eventos dinâmicos do fornecedor que é atribuída ao grupo ao qual o usuário pertence.</span><span class="sxs-lookup"><span data-stu-id="b12f4-362">This means that the user no longer has a Teams meeting broadcast policy directly assigned to them and will inherit the Vendor Live Events policy that's assigned to the group the user belongs to.</span></span> 

<span data-ttu-id="b12f4-363">Use o cmdlet a seguir no módulo do PowerShell do Skype for Business para fazer isso.</span><span class="sxs-lookup"><span data-stu-id="b12f4-363">Use the following cmdlet in the Skype for Business PowerShell module to do this.</span></span>

```powershell
Grant-CsTeamsMeetingBroadcastPolicy -Identity daniel@contoso.com -PolicyName $null
```

<span data-ttu-id="b12f4-364">Você pode usar o cmdlet a seguir no módulo do PowerShell Teams para fazer isso em escala durante uma atribuição de política em lotes, onde $users é uma lista de usuários que você especifica.</span><span class="sxs-lookup"><span data-stu-id="b12f4-364">You can use following cmdlet in the Teams Powershell module to do this at scale though a batch policy assignment, where $users is a list of users that you specify.</span></span>

```powershell
New-CsBatchPolicyAssignmentOperation -OperationName "Assigning null at bulk" -PolicyType TeamsMeetingBroadcastPolicy -PolicyName $null -Identity $users  
```

## <a name="assign-a-policy-package-to-a-batch-of-users"></a><span data-ttu-id="b12f4-365">Atribuir um pacote de política a um lote de usuários</span><span class="sxs-lookup"><span data-stu-id="b12f4-365">Assign a policy package to a batch of users</span></span>

<span data-ttu-id="b12f4-366">Com a atribuição de pacote de política em lotes, você pode atribuir um pacote de política a grandes conjuntos de usuários por vez sem ter que usar um script.</span><span class="sxs-lookup"><span data-stu-id="b12f4-366">With batch policy package assignment, you can assign a policy package to large sets of users at a time without having to use a script.</span></span> <span data-ttu-id="b12f4-367">Use o ```New-CsBatchPolicyPackageAssignmentOperation``` cmdlet para enviar um lote de usuários e o pacote de política que você deseja atribuir.</span><span class="sxs-lookup"><span data-stu-id="b12f4-367">You use the ```New-CsBatchPolicyPackageAssignmentOperation``` cmdlet to submit a batch of users and the policy package that you want to assign.</span></span> <span data-ttu-id="b12f4-368">As atribuições são processadas como uma operação em segundo plano e uma ID de operação é gerada para cada lote.</span><span class="sxs-lookup"><span data-stu-id="b12f4-368">The assignments are processed as a background operation and an operation ID is generated for each batch.</span></span> <span data-ttu-id="b12f4-369">Em seguida, você pode usar o ```Get-CsBatchPolicyAssignmentOperation``` cmdlet para acompanhar o progresso e o status das tarefas em um lote.</span><span class="sxs-lookup"><span data-stu-id="b12f4-369">You can then use the ```Get-CsBatchPolicyAssignmentOperation``` cmdlet to track the progress and status of the assignments in a batch.</span></span>

<span data-ttu-id="b12f4-370">Você pode especificar os usuários por seu ID de objeto ou endereço SIP (protocolo de iniciação de sessão).</span><span class="sxs-lookup"><span data-stu-id="b12f4-370">You can specify users by their object Id or Session Initiation Protocol (SIP) address.</span></span> <span data-ttu-id="b12f4-371">Observe que o endereço SIP de um usuário geralmente tem o mesmo valor que o nome UPN ou endereço de email, mas isso não é necessário.</span><span class="sxs-lookup"><span data-stu-id="b12f4-371">Note that a user's SIP address often has the same value as the User Principal Name (UPN) or email address, but this is not required.</span></span> <span data-ttu-id="b12f4-372">Se um usuário for especificado usando seu UPN ou email, mas tiver um valor diferente do endereço SIP, a atribuição de política falhará para o usuário.</span><span class="sxs-lookup"><span data-stu-id="b12f4-372">If a user is specified using their UPN or email, but it has a different value than their SIP address, then policy assignment will fail for the user.</span></span> <span data-ttu-id="b12f4-373">Se um lote incluir usuários duplicados, as duplicatas serão removidas do lote antes do processamento e o status só será fornecido para os usuários exclusivos restantes no lote.</span><span class="sxs-lookup"><span data-stu-id="b12f4-373">If a batch includes duplicate users, the duplicates will be removed from the batch before processing and status will only be provided for the unique users remaining in the batch.</span></span> 

<span data-ttu-id="b12f4-374">Um lote pode conter até 5.000 usuários.</span><span class="sxs-lookup"><span data-stu-id="b12f4-374">A batch can contain up to 5,000 users.</span></span> <span data-ttu-id="b12f4-375">Para obter melhores resultados, não envie mais do que alguns lotes de cada vez.</span><span class="sxs-lookup"><span data-stu-id="b12f4-375">For best results, do not submit more than a few batches at a time.</span></span> <span data-ttu-id="b12f4-376">Permitir que os lotes concluam o processamento antes de enviar mais lotes.</span><span class="sxs-lookup"><span data-stu-id="b12f4-376">Allow batches to complete processing before submitting more batches.</span></span>

### <a name="install-and-connect-to-the-microsoft-teams-powershell-module"></a><span data-ttu-id="b12f4-377">Instalar e conectar-se ao módulo do PowerShell do Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="b12f4-377">Install and connect to the Microsoft Teams PowerShell module</span></span>

<span data-ttu-id="b12f4-378">Execute o seguinte para instalar o [módulo do Microsoft Teams PowerShell](https://www.powershellgallery.com/packages/MicrosoftTeams) (se ainda não tiver feito isso).</span><span class="sxs-lookup"><span data-stu-id="b12f4-378">Run the following to install the [Microsoft Teams PowerShell module](https://www.powershellgallery.com/packages/MicrosoftTeams) (if you haven't already).</span></span> <span data-ttu-id="b12f4-379">Verifique se você instalou a versão 1.0.5 ou posterior.</span><span class="sxs-lookup"><span data-stu-id="b12f4-379">Make sure you install version 1.0.5 or later.</span></span>

```powershell
Install-Module -Name MicrosoftTeams
```

<span data-ttu-id="b12f4-380">Execute o seguinte para se conectar ao Microsoft Teams e iniciar uma sessão.</span><span class="sxs-lookup"><span data-stu-id="b12f4-380">Run the following to connect to Teams and start a session.</span></span>

```powershell
Connect-MicrosoftTeams
```

<span data-ttu-id="b12f4-381">Quando for solicitado, entre usando suas credenciais de administrador.</span><span class="sxs-lookup"><span data-stu-id="b12f4-381">When you're prompted, sign in using your admin credentials.</span></span>

### <a name="assign-a-policy-package-to-a-batch-of-users"></a><span data-ttu-id="b12f4-382">Atribuir um pacote de política a um lote de usuários</span><span class="sxs-lookup"><span data-stu-id="b12f4-382">Assign a policy package to a batch of users</span></span>

<span data-ttu-id="b12f4-383">Neste exemplo, usamos o ```New-CsBatchPolicyPackageAssignmentOperation``` cmdlet para atribuir o pacote de política Education_PrimaryStudent a um lote de usuários.</span><span class="sxs-lookup"><span data-stu-id="b12f4-383">In this example, we use the ```New-CsBatchPolicyPackageAssignmentOperation``` cmdlet to assign the Education_PrimaryStudent policy package to a batch of users.</span></span>

```powershell
New-CsBatchPolicyPackageAssignmentOperation -Identity 1bc0b35f-095a-4a37-a24c-c4b6049816ab,user1@econtoso.com,user2@contoso.com -PackageName Education_PrimaryStudent
```

<span data-ttu-id="b12f4-384">Para saber mais, confira [novo – CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation).</span><span class="sxs-lookup"><span data-stu-id="b12f4-384">To learn more, see [New-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation).</span></span>

### <a name="get-the-status-of-a-batch-assignment"></a><span data-ttu-id="b12f4-385">Obter o status de uma atribuição em lote</span><span class="sxs-lookup"><span data-stu-id="b12f4-385">Get the status of a batch assignment</span></span>

<span data-ttu-id="b12f4-386">Execute o seguinte para obter o status de uma atribuição em lotes, em que operationId é a ID da operação retornada pelo ```New-CsBatchPolicyAssignmentOperation``` cmdlet para um determinado lote.</span><span class="sxs-lookup"><span data-stu-id="b12f4-386">Run the following to get the status of a batch assignment, where OperationId is the operation ID that's returned by the ```New-CsBatchPolicyAssignmentOperation``` cmdlet for a given batch.</span></span>

```powershell
$Get-CsBatchPolicyAssignmentOperation -OperationId f985e013-0826-40bb-8c94-e5f367076044 | fl
```

<span data-ttu-id="b12f4-387">Se a saída mostrar que ocorreu um erro, execute o seguinte para obter mais informações sobre erros, que estão na ```UserState``` propriedade.</span><span class="sxs-lookup"><span data-stu-id="b12f4-387">If the output shows that an error occurred, run the following to get more information about errors, which are in the ```UserState``` property.</span></span>

```powershell
Get-CsBatchPolicyAssignmentOperation -OperationId f985e013-0826-40bb-8c94-e5f367076044 | Select -ExpandProperty UserState
```

<span data-ttu-id="b12f4-388">Para saber mais, consulte [Get-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/get-csbatchpolicyassignmentoperation).</span><span class="sxs-lookup"><span data-stu-id="b12f4-388">To learn more, see [Get-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/get-csbatchpolicyassignmentoperation).</span></span> 

## <a name="related-topics"></a><span data-ttu-id="b12f4-389">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="b12f4-389">Related topics</span></span>

[<span data-ttu-id="b12f4-390">Visão Geral do PowerShell do Teams</span><span class="sxs-lookup"><span data-stu-id="b12f4-390">Teams PowerShell Overview</span></span>](teams-powershell-overview.md)
