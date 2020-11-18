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
ms.openlocfilehash: ada58a9abf07e606f91d48b7ac71ba06d4c1496a
ms.sourcegitcommit: b282acc1633c2d62bbff0ea77b6b647775ae6dfe
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/17/2020
ms.locfileid: "49085695"
---
# <a name="assign-policies-to-your-users-in-microsoft-teams"></a><span data-ttu-id="52612-103">Atribuir políticas aos usuários no Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="52612-103">Assign policies to your users in Microsoft Teams</span></span>

<span data-ttu-id="52612-104">Como administrador, você usa políticas para controlar os recursos do teams que estão disponíveis para os usuários da sua organização.</span><span class="sxs-lookup"><span data-stu-id="52612-104">As an admin, you use policies to control the Teams features that are available to users in your organization.</span></span> <span data-ttu-id="52612-105">Por exemplo, há políticas de chamada, políticas de reunião e políticas de mensagens, para citar apenas alguns.</span><span class="sxs-lookup"><span data-stu-id="52612-105">For example, there are calling policies, meeting policies, and messaging policies, to name just a few.</span></span>

<span data-ttu-id="52612-106">As organizações têm diferentes tipos de usuários com necessidades exclusivas e políticas personalizadas que você cria e atribui permite que você ajuste as configurações de política para diferentes conjuntos de usuários com base nessas necessidades.</span><span class="sxs-lookup"><span data-stu-id="52612-106">Organizations have different types of users with unique needs and custom policies that you create and assign let you tailor policy settings to different sets of users based on those needs.</span></span>

<span data-ttu-id="52612-107">Para facilitar o gerenciamento de políticas em sua organização, o Teams oferece várias maneiras de atribuir políticas a usuários.</span><span class="sxs-lookup"><span data-stu-id="52612-107">To make it easier to manage policies in your organization, Teams offers several ways to assign policies to users.</span></span> <span data-ttu-id="52612-108">Você pode atribuir uma política diretamente aos usuários, individualmente ou em escalabilidade por meio de uma atribuição de lote ou a um grupo do qual os usuários são membros.</span><span class="sxs-lookup"><span data-stu-id="52612-108">You can assign a policy directly to users, either individually or at scale through a batch assignment, or to a group that the users are members of.</span></span> <span data-ttu-id="52612-109">Você também pode usar pacotes de política para atribuir uma coleção predefinida de políticas para os usuários de sua organização que têm funções semelhantes.</span><span class="sxs-lookup"><span data-stu-id="52612-109">You can also use policy packages to assign a preset collection of policies to users in your organization who have similar roles.</span></span> <span data-ttu-id="52612-110">A opção que você escolher depende do número de políticas que você está gerenciando e do número de usuários aos quais está fazendo a atribuição.</span><span class="sxs-lookup"><span data-stu-id="52612-110">The option that you choose depends on the number of policies that you're managing and the number of users that you're assigning to.</span></span> <span data-ttu-id="52612-111">Ao definir as políticas globais (padrão para toda a organização) para que elas se apliquem ao maior número de usuários em sua organização, você só precisa atribuir políticas a esses usuários que exigem políticas especializadas.</span><span class="sxs-lookup"><span data-stu-id="52612-111">By setting the global (Org-wide default) policies so that they apply to the largest number of users in your organization, you only have to assign policies to those users that require specialized policies.</span></span>

<span data-ttu-id="52612-112">Este artigo descreve as diferentes maneiras pelas quais você pode atribuir políticas a usuários e os cenários recomendados para quando usar o quê.</span><span class="sxs-lookup"><span data-stu-id="52612-112">This article describes the different ways that you can assign policies to users and the recommended scenarios for when to use what.</span></span>

## <a name="which-policy-takes-precedence"></a><span data-ttu-id="52612-113">Qual política tem precedência?</span><span class="sxs-lookup"><span data-stu-id="52612-113">Which policy takes precedence?</span></span>

<span data-ttu-id="52612-114">Um usuário tem uma política em vigor para cada tipo de política.</span><span class="sxs-lookup"><span data-stu-id="52612-114">A user has one effective policy for each policy type.</span></span> <span data-ttu-id="52612-115">É possível ou até mesmo provável que um usuário esteja diretamente atribuído a uma política e também seja um membro de um ou mais grupos que tenha atribuído uma política do mesmo tipo.</span><span class="sxs-lookup"><span data-stu-id="52612-115">It's possible or even likely that a user is directly assigned a policy and is also a member of one or more groups that's assigned a policy of the same type.</span></span> <span data-ttu-id="52612-116">Nesses tipos de cenários, qual política tem precedência?</span><span class="sxs-lookup"><span data-stu-id="52612-116">In these kinds of scenarios, which policy takes precedence?</span></span>  <span data-ttu-id="52612-117">A política efetiva de um usuário é determinada de acordo com as regras de precedência, da seguinte maneira.</span><span class="sxs-lookup"><span data-stu-id="52612-117">A user's effective policy is determined according to rules of precedence, as follows.</span></span>

<span data-ttu-id="52612-118">Se um usuário for diretamente atribuído a uma política (individualmente ou por meio de uma atribuição em lotes), essa política terá precedência.</span><span class="sxs-lookup"><span data-stu-id="52612-118">If a user is directly assigned a policy (either individually or through a batch assignment), that policy takes precedence.</span></span> <span data-ttu-id="52612-119">No exemplo a seguir, a política efetiva do usuário é a política de reunião quadrada Lincoln, que é atribuída diretamente ao usuário.</span><span class="sxs-lookup"><span data-stu-id="52612-119">In the following example, the user's effective policy is the Lincoln Square meeting policy, which is directly assigned to the user.</span></span>

![Diagrama mostrando como uma política atribuída diretamente tem prioridade](media/assign-policies-example-directly-assigned.png)

<span data-ttu-id="52612-121">Se um usuário não estiver diretamente atribuído a uma política de um determinado tipo, a política atribuída a um grupo do qual o usuário é membro terá precedência.</span><span class="sxs-lookup"><span data-stu-id="52612-121">If a user isn't directly assigned a policy of a given type, the policy assigned to a group that the user is a member of takes precedence.</span></span> <span data-ttu-id="52612-122">Se um usuário for membro de vários grupos, a política que tem a classificação de [atribuição de grupo](#group-assignment-ranking) mais alta para o tipo de política específico tem precedência.</span><span class="sxs-lookup"><span data-stu-id="52612-122">If a user is a member of multiple groups, the policy that has the highest [group assignment ranking](#group-assignment-ranking) for the given policy type takes precedence.</span></span>

<span data-ttu-id="52612-123">Neste exemplo, a política efetiva do usuário é o Teams exec e a política de HD, que tem a classificação de atribuição mais alta em relação a outros grupos dos quais o usuário é membro e que também são atribuídas uma política do mesmo tipo de política.</span><span class="sxs-lookup"><span data-stu-id="52612-123">In this example, the user's effective policy is the Exec Teams and HD policy, which has the highest assignment ranking relative to other groups that the user is a member of and that are also assigned a policy of the same policy type.</span></span>  

![Diagrama mostrando como uma política herdada do grupo tem prioridade](media/assign-policies-example-group.png)

<span data-ttu-id="52612-125">Se um usuário não estiver diretamente atribuído a uma política ou não for membro de nenhum grupo ao qual a política atribuiu uma política, o usuário terá a política global (padrão para toda a organização) para esse tipo de política.</span><span class="sxs-lookup"><span data-stu-id="52612-125">If a user isn't directly assigned a policy or isn't a member of any groups that are assigned a policy, the user gets the global (Org-wide default) policy for that policy type.</span></span> <span data-ttu-id="52612-126">Aqui está um exemplo.</span><span class="sxs-lookup"><span data-stu-id="52612-126">Here's an example.</span></span>

![Diagrama mostrando como uma política global tem precedência](media/assign-policies-example-global.png)

<span data-ttu-id="52612-128">Para saber mais, consulte [regras de precedência](#precedence-rules).</span><span class="sxs-lookup"><span data-stu-id="52612-128">To learn more, see [Precedence rules](#precedence-rules).</span></span>

## <a name="ways-to-assign-policies"></a><span data-ttu-id="52612-129">Maneiras de atribuir políticas</span><span class="sxs-lookup"><span data-stu-id="52612-129">Ways to assign policies</span></span>

<span data-ttu-id="52612-130">Aqui está uma visão geral de como você pode atribuir políticas a usuários e os cenários recomendados para cada um deles.</span><span class="sxs-lookup"><span data-stu-id="52612-130">Here's an overview of the ways that you can assign policies to users and the recommended scenarios for each.</span></span> <span data-ttu-id="52612-131">Clique nos links para saber mais.</span><span class="sxs-lookup"><span data-stu-id="52612-131">Click the links to learn more.</span></span>

<span data-ttu-id="52612-132">Antes de atribuir políticas a usuários ou grupos individuais, comece [definindo as políticas globais (padrão para toda](#set-the-global-policies) a organização) para que elas se apliquem ao maior número de usuários em sua organização.</span><span class="sxs-lookup"><span data-stu-id="52612-132">Before assigning policies to individual users or groups, start by [setting the global (Org-wide default) policies](#set-the-global-policies) so that they apply to the largest number of users in your organization.</span></span>  <span data-ttu-id="52612-133">Depois que as políticas globais estiverem definidas, você só precisará atribuir políticas a esses usuários que exigem políticas especializadas.</span><span class="sxs-lookup"><span data-stu-id="52612-133">Once the global policies are set, you will only need to assign policies to those users that require specialized policies.</span></span>

|<span data-ttu-id="52612-134">Faça isto</span><span class="sxs-lookup"><span data-stu-id="52612-134">Do this</span></span>  |<span data-ttu-id="52612-135">Se...</span><span class="sxs-lookup"><span data-stu-id="52612-135">If...</span></span>  | <span data-ttu-id="52612-136">Usar...</span><span class="sxs-lookup"><span data-stu-id="52612-136">Using...</span></span>
|---------|---------|----|
|[<span data-ttu-id="52612-137">Atribuir uma política a usuários individuais</span><span class="sxs-lookup"><span data-stu-id="52612-137">Assign a policy to individual users</span></span>](#assign-a-policy-to-individual-users)    | <span data-ttu-id="52612-138">Você está começando a usar o Microsoft Teams e simplesmente está começando ou só precisa atribuir uma ou algumas políticas a um pequeno número de usuários.</span><span class="sxs-lookup"><span data-stu-id="52612-138">You're new to Teams and just getting started or you only need to assign one or a couple of policies to a small number of users.</span></span> |<span data-ttu-id="52612-139">O centro de administração do Microsoft Teams ou cmdlets do PowerShell no módulo do PowerShell do Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="52612-139">The Microsoft Teams admin center or PowerShell cmdlets in the Skype for Business Online PowerShell module</span></span>
|[<span data-ttu-id="52612-140">Atribuir uma política a um grupo</span><span class="sxs-lookup"><span data-stu-id="52612-140">Assign a policy to a group</span></span>](#assign-a-policy-to-a-group) |<span data-ttu-id="52612-141">Você precisa atribuir políticas com base nas associações de grupo de um usuário.</span><span class="sxs-lookup"><span data-stu-id="52612-141">You need to assign policies based on a user's group membership.</span></span> <span data-ttu-id="52612-142">Por exemplo, você deseja atribuir uma política a todos os usuários em um grupo de segurança ou lista de distribuição.</span><span class="sxs-lookup"><span data-stu-id="52612-142">For example, you want to assign a policy to all users in a security group or distribution list.</span></span>| <span data-ttu-id="52612-143">O centro de administração do Microsoft Teams ou cmdlets do PowerShell no módulo Teams PowerShell</span><span class="sxs-lookup"><span data-stu-id="52612-143">The Microsoft Teams admin center or PowerShell cmdlets in the Teams PowerShell module</span></span>|
|[<span data-ttu-id="52612-144">Atribuir uma política a um lote de usuários</span><span class="sxs-lookup"><span data-stu-id="52612-144">Assign a policy to a batch of users</span></span>](#assign-a-policy-to-a-batch-of-users)   | <span data-ttu-id="52612-145">Você precisa atribuir políticas a grandes conjuntos de usuários.</span><span class="sxs-lookup"><span data-stu-id="52612-145">You need to assign policies to large sets of users.</span></span> <span data-ttu-id="52612-146">Por exemplo, você deseja atribuir uma política para centenas ou milhares de usuários em sua organização de cada vez.</span><span class="sxs-lookup"><span data-stu-id="52612-146">For example, you want to assign a policy to hundreds or thousands of users in your organization at a time.</span></span>  |<span data-ttu-id="52612-147">O centro de administração do Microsoft Teams ou cmdlets do PowerShell no módulo Teams PowerShell</span><span class="sxs-lookup"><span data-stu-id="52612-147">The Microsoft Teams admin center or PowerShell cmdlets in the Teams PowerShell module</span></span>|
| [<span data-ttu-id="52612-148">Atribuir um pacote de política aos usuários</span><span class="sxs-lookup"><span data-stu-id="52612-148">Assign a policy package to users</span></span>](#assign-a-policy-package-to-users)  | <span data-ttu-id="52612-149">Você precisa atribuir várias políticas a conjuntos específicos de usuários em sua organização que tenham funções iguais ou semelhantes.</span><span class="sxs-lookup"><span data-stu-id="52612-149">You need to assign multiple policies to specific sets of users in your organization who have the same or similar roles.</span></span> <span data-ttu-id="52612-150">Por exemplo, atribua o pacote de política de educação (professor) a professores em sua escola para dar a eles acesso total a chats, chamadas e reuniões e ao pacote de política Education (aluno da escola secundária) para os alunos secundários limitarem determinados recursos como chamadas privadas.</span><span class="sxs-lookup"><span data-stu-id="52612-150">For example, assign the Education (Teacher) policy package to teachers in your school to give them full access to chats, calling, and meetings and the Education (Secondary school student) policy package to secondary students to limit certain capabilities like private calling.</span></span>  |<span data-ttu-id="52612-151">O centro de administração do Microsoft Teams ou cmdlets do PowerShell no módulo Teams PowerShell</span><span class="sxs-lookup"><span data-stu-id="52612-151">The Microsoft Teams admin center or PowerShell cmdlets in the Teams PowerShell module</span></span>|
| <span data-ttu-id="52612-152">[Atribuir um pacote de política a um grupo](#assign-a-policy-package-to-a-group) (em visualização particular)</span><span class="sxs-lookup"><span data-stu-id="52612-152">[Assign a policy package to a group](#assign-a-policy-package-to-a-group) (in private preview)</span></span>   |<span data-ttu-id="52612-153">Você precisa atribuir várias políticas a um grupo de usuários em sua organização que tenham funções iguais ou semelhantes.</span><span class="sxs-lookup"><span data-stu-id="52612-153">You need to assign multiple policies to a group of users in your organization who have the same or similar roles.</span></span> <span data-ttu-id="52612-154">Por exemplo, você deseja atribuir um pacote de política a todos os usuários em um grupo de segurança ou lista de distribuição.</span><span class="sxs-lookup"><span data-stu-id="52612-154">For example, you want to assign a policy package to all users in a security group or distribution list.</span></span> |<span data-ttu-id="52612-155">O centro de administração do Microsoft Teams (disponível em breve) ou cmdlets do PowerShell no módulo do PowerShell para Teams</span><span class="sxs-lookup"><span data-stu-id="52612-155">The Microsoft Teams admin center (coming soon) or PowerShell cmdlets in the Teams PowerShell module</span></span>|
| [<span data-ttu-id="52612-156">Atribuir um pacote de política a um lote de usuários</span><span class="sxs-lookup"><span data-stu-id="52612-156">Assign a policy package to a batch of users</span></span>](#assign-a-policy-package-to-a-batch-of-users)|<span data-ttu-id="52612-157">Você precisa atribuir várias políticas a um lote de usuários em sua organização que tenham funções iguais ou semelhantes.</span><span class="sxs-lookup"><span data-stu-id="52612-157">You need to assign multiple policies to a batch of users in your organization who have the same or similar roles.</span></span> <span data-ttu-id="52612-158">Por exemplo, atribua o pacote de política de educação (professor) a todos os professores da sua escola usando a atribuição de lote para dar a eles acesso total a chats, chamadas e reuniões e atribuir o pacote de política de educação (aluno secundária da escola) a um lote de alunos secundários para limitar determinados recursos como chamadas privadas.</span><span class="sxs-lookup"><span data-stu-id="52612-158">For example, assign the Education (Teacher) policy package to all teachers in your school using batch assignment to give them full access to chats, calling, and meetings and assign the Education (Secondary school student) policy package to a batch of secondary students to limit certain capabilities like private calling.</span></span>|<span data-ttu-id="52612-159">Cmdlets do PowerShell no módulo do teams PowerShell</span><span class="sxs-lookup"><span data-stu-id="52612-159">PowerShell cmdlets in the Teams PowerShell module</span></span>|


## <a name="set-the-global-policies"></a><span data-ttu-id="52612-160">Definir as políticas globais</span><span class="sxs-lookup"><span data-stu-id="52612-160">Set the global policies</span></span>

<span data-ttu-id="52612-161">Siga estas etapas para definir as políticas globais (padrão para toda a organização) para cada tipo de política.</span><span class="sxs-lookup"><span data-stu-id="52612-161">Follow these steps to set the global (Org-wide default) policies for each policy type.</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="52612-162">Usando o centro de administração do Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="52612-162">Using the Microsoft Teams admin center</span></span>

1. <span data-ttu-id="52612-163">Na navegação à esquerda do centro de administração do Microsoft Teams, vá para a página política do tipo de política que você deseja atualizar.</span><span class="sxs-lookup"><span data-stu-id="52612-163">In the left navigation of the Microsoft Teams admin center, go to the policy page for the policy type you want to update.</span></span> <span data-ttu-id="52612-164">Por exemplo, políticas **Teams**  >  de **equipes** de equipe, políticas de reuniões de **reuniões**  >  **Meetings policies**, políticas de **mensagens** ou políticas de chamadas de **voz**  >  **Calling policies**.</span><span class="sxs-lookup"><span data-stu-id="52612-164">For example, **Teams** > **Teams policies**, **Meetings** > **Meetings policies**, **Messaging policies**, or **Voice** > **Calling policies**.</span></span>
2. <span data-ttu-id="52612-165">Selecione a política **global (padrão para toda a organização)** para exibir as configurações atuais.</span><span class="sxs-lookup"><span data-stu-id="52612-165">Select the **Global (Org-wide default)** policy to view the current settings.</span></span>
3. <span data-ttu-id="52612-166">Atualize a política conforme necessário e selecione **aplicar**.</span><span class="sxs-lookup"><span data-stu-id="52612-166">Update the policy as needed, and then select **Apply**.</span></span>

### <a name="using-powershell"></a><span data-ttu-id="52612-167">Usando o PowerShell</span><span class="sxs-lookup"><span data-stu-id="52612-167">Using PowerShell</span></span>

<span data-ttu-id="52612-168">Para definir as políticas globais usando o PowerShell, use o identificador global.</span><span class="sxs-lookup"><span data-stu-id="52612-168">To set the global policies using PowerShell, use the Global identifier.</span></span>  <span data-ttu-id="52612-169">Comece analisando a política global atual para determinar qual configuração você deseja alterar.</span><span class="sxs-lookup"><span data-stu-id="52612-169">Start by reviewing the current Global policy to determine which setting you want to change.</span></span>

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

<span data-ttu-id="52612-170">Em seguida, atualize a política global conforme necessário.</span><span class="sxs-lookup"><span data-stu-id="52612-170">Next, update the Global policy as needed.</span></span>  <span data-ttu-id="52612-171">Você só precisa especificar valores para as configurações que você deseja alterar.</span><span class="sxs-lookup"><span data-stu-id="52612-171">You only need to specify values for the settings that you want to change.</span></span> 
 
```powershell
Set-CsTeamsMessagingPolicy -Identity Global -AllowUserEditMessage $false
```

## <a name="assign-a-policy-to-individual-users"></a><span data-ttu-id="52612-172">Atribuir uma política a usuários individuais</span><span class="sxs-lookup"><span data-stu-id="52612-172">Assign a policy to individual users</span></span>

<span data-ttu-id="52612-173">Siga estas etapas para atribuir uma política a um usuário individual ou a um pequeno número de usuários por vez.</span><span class="sxs-lookup"><span data-stu-id="52612-173">Follow these steps to assign a policy to an individual user or to a small number of users at a time.</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="52612-174">Usando o centro de administração do Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="52612-174">Using the Microsoft Teams admin center</span></span>

<span data-ttu-id="52612-175">Para atribuir uma política a um usuário:</span><span class="sxs-lookup"><span data-stu-id="52612-175">To assign a policy to a user:</span></span>

1. <span data-ttu-id="52612-176">Na barra de navegação à esquerda do centro de administração do Microsoft Teams, vá para **Usuários** e clique no usuário.</span><span class="sxs-lookup"><span data-stu-id="52612-176">In the left navigation of the Microsoft Teams admin center, go to **Users**, and then click the user.</span></span>
2. <span data-ttu-id="52612-177">Selecione o usuário clicando à esquerda do nome de exibição do usuário e clique em **Editar configurações**.</span><span class="sxs-lookup"><span data-stu-id="52612-177">Select the user by clicking to the left of the user name, and then click **Edit settings**.</span></span>
3. <span data-ttu-id="52612-178">Selecione a política que você deseja atribuir e clique em **aplicar**.</span><span class="sxs-lookup"><span data-stu-id="52612-178">Select the policy you want to assign, and then click **Apply**.</span></span>

<span data-ttu-id="52612-179">Ou, você também pode fazer o seguinte:</span><span class="sxs-lookup"><span data-stu-id="52612-179">Or, you can also do the following:</span></span>

1. <span data-ttu-id="52612-180">Na navegação à esquerda do centro de administração do Microsoft Teams, vá para a página política.</span><span class="sxs-lookup"><span data-stu-id="52612-180">In the left navigation of the Microsoft Teams admin center, go to the policy page.</span></span>
2. <span data-ttu-id="52612-181">Selecione a política que você deseja atribuir clicando à esquerda do nome da política.</span><span class="sxs-lookup"><span data-stu-id="52612-181">Select the policy you want to assign by clicking to the left of the policy name.</span></span>
3. <span data-ttu-id="52612-182">Escolha **Gerenciar usuários**.</span><span class="sxs-lookup"><span data-stu-id="52612-182">Select **Manage users**.</span></span>
4. <span data-ttu-id="52612-183">No painel **Gerenciar usuários**, procure o usuário pelo nome de exibição ou pelo nome de usuário, escolha o nome e marque **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="52612-183">In the **Manage users** pane, search for the user by display name or by user name, select the name, and then select **Add**.</span></span> <span data-ttu-id="52612-184">Repita esta etapa para cada usuário que você deseja adicionar.</span><span class="sxs-lookup"><span data-stu-id="52612-184">Repeat this step for each user that you want to add.</span></span>
5. <span data-ttu-id="52612-185">Quando tiver terminado de adicionar usuários, selecione **aplicar**.</span><span class="sxs-lookup"><span data-stu-id="52612-185">When you're finished adding users, select **Apply**.</span></span>

### <a name="using-powershell"></a><span data-ttu-id="52612-186">Usando o PowerShell</span><span class="sxs-lookup"><span data-stu-id="52612-186">Using PowerShell</span></span>

<span data-ttu-id="52612-187">Cada tipo de política tem seu próprio conjunto de cmdlets para gerenciá-lo.</span><span class="sxs-lookup"><span data-stu-id="52612-187">Each policy type has its own set of cmdlets for managing it.</span></span> <span data-ttu-id="52612-188">Use o ```Grant-``` cmdlet para um determinado tipo de política para atribuir a política.</span><span class="sxs-lookup"><span data-stu-id="52612-188">Use the ```Grant-``` cmdlet for a given policy type to assign the policy.</span></span> <span data-ttu-id="52612-189">Por exemplo, use o ```Grant-CsTeamsMeetingPolicy``` cmdlet para atribuir uma política de reunião do teams aos usuários.</span><span class="sxs-lookup"><span data-stu-id="52612-189">For example, use the ```Grant-CsTeamsMeetingPolicy``` cmdlet to assign a Teams meeting policy to users.</span></span> <span data-ttu-id="52612-190">Esses cmdlets estão incluídos no módulo do PowerShell do Skype for Business Online e são documentados na [referência do cmdlet do Skype for Business](https://docs.microsoft.com/powershell/skype/intro?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="52612-190">These cmdlets are included in the Skype for Business Online PowerShell module and are documented in the [Skype for Business cmdlet reference](https://docs.microsoft.com/powershell/skype/intro?view=skype-ps).</span></span>

 <span data-ttu-id="52612-191">Baixe e instale o [módulo do PowerShell do Skype for Business online](https://www.microsoft.com/download/details.aspx?id=39366) (caso ainda não tenha sido feito) e, em seguida, execute o seguinte para se conectar ao Skype for Business Online e iniciar uma sessão.</span><span class="sxs-lookup"><span data-stu-id="52612-191">Download and install the [Skype for Business Online PowerShell module](https://www.microsoft.com/download/details.aspx?id=39366) (if you haven't already), and then run the following to connect to Skype for Business Online and start a session.</span></span>

> [!NOTE]
> <span data-ttu-id="52612-192">O conector do Skype for Business online atualmente faz parte do módulo do PowerShell mais recente do teams.</span><span class="sxs-lookup"><span data-stu-id="52612-192">Skype for Business Online Connector is currently part of the latest Teams PowerShell module.</span></span>
>
> <span data-ttu-id="52612-193">Se você estiver usando a [versão pública do teams PowerShell](https://www.powershellgallery.com/packages/MicrosoftTeams/)mais recente, não será necessário instalar o conector do Skype for Business online.</span><span class="sxs-lookup"><span data-stu-id="52612-193">If you're using the latest [Teams PowerShell public release](https://www.powershellgallery.com/packages/MicrosoftTeams/), you don't need to install the Skype for Business Online Connector.</span></span>

```powershell
Import-Module -Name MicrosoftTeams
$Cred = Get-Credential
$CSSession = New-CsOnlineSession -Credential $Cred
Import-PSSession -Session $CSSession
```

<span data-ttu-id="52612-194">Neste exemplo, atribuímos uma política de reunião do teams chamada política de reunião do aluno a um usuário chamado Reda.</span><span class="sxs-lookup"><span data-stu-id="52612-194">In this example, we assign a Teams meeting policy named Student Meeting Policy to a user named Reda.</span></span>

```powershell
Grant-CsTeamsMeetingPolicy -Identity reda@contoso.com -PolicyName "Student Meeting Policy"
```

<span data-ttu-id="52612-195">Para saber mais, leia [gerenciar políticas pelo PowerShell](teams-powershell-managing-teams.md#manage-policies-via-powershell).</span><span class="sxs-lookup"><span data-stu-id="52612-195">To learn more, read [Manage policies via PowerShell](teams-powershell-managing-teams.md#manage-policies-via-powershell).</span></span>

## <a name="assign-a-policy-to-a-group"></a><span data-ttu-id="52612-196">Atribuir uma política a um grupo</span><span class="sxs-lookup"><span data-stu-id="52612-196">Assign a policy to a group</span></span>

<span data-ttu-id="52612-197">A atribuição de política a grupos permite atribuir uma política a um grupo de usuários, como um grupo de segurança ou lista de distribuição.</span><span class="sxs-lookup"><span data-stu-id="52612-197">Policy assignment to groups lets you assign a policy to a group of users, such as a security group or distribution list.</span></span> <span data-ttu-id="52612-198">As atribuições de política serão propagadas para os membros do grupo, de acordo com as regras de precedência.</span><span class="sxs-lookup"><span data-stu-id="52612-198">The policy assignment is propagated to members of the group according to precedence rules.</span></span> <span data-ttu-id="52612-199">À medida que os membros forem adicionados ou removidos de um grupo, as atribuições de política herdadas serão atualizadas.</span><span class="sxs-lookup"><span data-stu-id="52612-199">As members are added to or removed from a group, their inherited policy assignments are updated accordingly.</span></span>

<span data-ttu-id="52612-200">A atribuição de política a grupos é recomendada para grupos de até 50.000 usuários, mas também funciona com grupos maiores.</span><span class="sxs-lookup"><span data-stu-id="52612-200">Policy assignment to groups is recommended for groups of up to 50,000 users but it will also work with larger groups.</span></span>

<span data-ttu-id="52612-201">Quando você atribui a política, ela é imediatamente atribuída ao grupo.</span><span class="sxs-lookup"><span data-stu-id="52612-201">When you assign the policy, it's immediately assigned to the group.</span></span> <span data-ttu-id="52612-202">No entanto, observe que a propagação da atribuição da política para os membros do grupo é realizada como uma operação em segundo plano e pode demorar algum tempo, dependendo do tamanho do grupo.</span><span class="sxs-lookup"><span data-stu-id="52612-202">However, note that the propagation of the policy assignment to members of the group is performed as a background operation and may take some time, depending on the size of the group.</span></span> <span data-ttu-id="52612-203">O mesmo é verdadeiro quando uma política é desatribuída de um grupo ou quando os membros são adicionados ou removidos de um grupo.</span><span class="sxs-lookup"><span data-stu-id="52612-203">The same is true when a policy is unassigned from a group, or when members are added to or removed from a group.</span></span>

<span data-ttu-id="52612-204">As atribuições de política de grupo só são propagadas para os usuários que são membros diretos do grupo.</span><span class="sxs-lookup"><span data-stu-id="52612-204">Group policy assignments are only propagated to users that are direct members of the group.</span></span> <span data-ttu-id="52612-205">As tarefas não são propagadas para os membros de grupos aninhados.</span><span class="sxs-lookup"><span data-stu-id="52612-205">The assignments aren't propagated to members of nested groups.</span></span>

### <a name="what-you-need-to-know-about-policy-assignment-to-groups"></a><span data-ttu-id="52612-206">O que você precisa saber sobre atribuição de política a grupos</span><span class="sxs-lookup"><span data-stu-id="52612-206">What you need to know about policy assignment to groups</span></span>

<span data-ttu-id="52612-207">Antes de começar, é importante entender as regras de precedência e a classificação de atribuição de grupo.</span><span class="sxs-lookup"><span data-stu-id="52612-207">Before you get started, it's important to understand precedence rules and group assignment ranking.</span></span>

#### <a name="precedence-rules"></a><span data-ttu-id="52612-208">Regras de precedência</span><span class="sxs-lookup"><span data-stu-id="52612-208">Precedence rules</span></span>

<span data-ttu-id="52612-209">Para um determinado tipo de política, a política efetiva de um usuário é determinada de acordo com o seguinte:</span><span class="sxs-lookup"><span data-stu-id="52612-209">For a given policy type, a user's effective policy is determined according to the following:</span></span>

- <span data-ttu-id="52612-210">Uma política que é atribuída diretamente a um usuário tem precedência sobre qualquer outra política do mesmo tipo que esteja atribuída a um grupo.</span><span class="sxs-lookup"><span data-stu-id="52612-210">A policy that's directly assigned to a user takes precedence over any other policy of the same type that's assigned to a group.</span></span> <span data-ttu-id="52612-211">Em outras palavras, se um usuário estiver diretamente atribuído a uma política de um determinado tipo, esse usuário não herdará uma política do mesmo tipo de um grupo.</span><span class="sxs-lookup"><span data-stu-id="52612-211">In other words, if a user is directly assigned a policy of a given type, that user won't inherit a policy of the same type from a group.</span></span> <span data-ttu-id="52612-212">Isso também significa que, se um usuário tiver uma política de um determinado tipo que foi atribuído diretamente a ele, será necessário remover essa política do usuário antes de poder herdar uma política do mesmo tipo de um grupo.</span><span class="sxs-lookup"><span data-stu-id="52612-212">This also means that if a user has a policy of a given type that was directly assigned to them, you have to remove that policy from the user before they can inherit a policy of the same type from a group.</span></span>
- <span data-ttu-id="52612-213">Se um usuário não tiver uma política diretamente atribuída a ele e for um membro de dois ou mais grupos e cada grupo tiver uma política do mesmo tipo atribuído a ele, o usuário herdará a política da atribuição de grupo que tem a classificação mais alta.</span><span class="sxs-lookup"><span data-stu-id="52612-213">If a user doesn't have a policy directly assigned to them and is a member of two or more groups and each group has a policy of the same type assigned to it, the user inherits the policy of the group assignment that has the highest ranking.</span></span>
- <span data-ttu-id="52612-214">Se um usuário não for membro de nenhum grupo ao qual uma política atribuiu uma política, a política global (padrão para toda a organização) para esse tipo de política se aplicará ao usuário.</span><span class="sxs-lookup"><span data-stu-id="52612-214">If a user isn't a member of any groups that are assigned a policy, the global (Org-wide default) policy for that policy type applies to the user.</span></span>

<span data-ttu-id="52612-215">A política efetiva de um usuário é atualizada de acordo com essas regras quando um usuário é adicionado ou removido de um grupo que é atribuído a uma política, uma política é desatribuída de um grupo ou uma política diretamente atribuída ao usuário é removida.</span><span class="sxs-lookup"><span data-stu-id="52612-215">A user's effective policy is updated according to these rules when a user is added to or removed from a group that's assigned a policy, a policy is unassigned from a group, or a policy that's directly assigned to the user is removed.</span></span>

#### <a name="group-assignment-ranking"></a><span data-ttu-id="52612-216">Classificação de atribuição de grupo</span><span class="sxs-lookup"><span data-stu-id="52612-216">Group assignment ranking</span></span>
 
<span data-ttu-id="52612-217">Ao atribuir uma política a um grupo, você especifica uma classificação para a atribuição de grupo.</span><span class="sxs-lookup"><span data-stu-id="52612-217">When you assign a policy to a group, you specify a ranking for the group assignment.</span></span> <span data-ttu-id="52612-218">Isso é usado para determinar qual política um usuário deve herdar como política efetiva se o usuário for membro de dois ou mais grupos e cada grupo tiver atribuído uma política do mesmo tipo.</span><span class="sxs-lookup"><span data-stu-id="52612-218">This is used to determine which policy a user should inherit as their effective policy if the user is a member of two or more groups and each group is assigned a policy of the same type.</span></span>

<span data-ttu-id="52612-219">A classificação da atribuição de grupo é relativa a outras tarefas de grupo do mesmo tipo.</span><span class="sxs-lookup"><span data-stu-id="52612-219">The group assignment ranking is relative to other group assignments of the same type.</span></span> <span data-ttu-id="52612-220">Por exemplo, se você estiver atribuindo uma política de chamada a dois grupos, defina a classificação de uma tarefa como 1 e a outra como 2, com 1 sendo a classificação mais alta.</span><span class="sxs-lookup"><span data-stu-id="52612-220">For example, if you're assigning a calling policy to two groups, set the ranking of one assignment to 1 and the other to 2, with 1 being the highest ranking.</span></span> <span data-ttu-id="52612-221">A classificação de atribuição de grupo indica qual associação de grupo é mais importante ou mais relevante do que outras associações de grupo em relação à herança.</span><span class="sxs-lookup"><span data-stu-id="52612-221">The group assignment ranking indicates which group membership is more important or more relevant than other group memberships with regards to inheritance.</span></span>
 
<span data-ttu-id="52612-222">Digamos, por exemplo, que você tem dois grupos, armazenar funcionários e gerentes da loja.</span><span class="sxs-lookup"><span data-stu-id="52612-222">Say, for example, you have two groups, Store Employees and Store Managers.</span></span> <span data-ttu-id="52612-223">Os dois grupos recebem uma política de chamada de equipes, armazenando a política de chamadas de gerentes de loja e a política de chamadas de gerentes de loja</span><span class="sxs-lookup"><span data-stu-id="52612-223">Both groups are assigned a Teams calling policy, Store Employees Calling Policy and Store Managers Calling Policy, respectively.</span></span> <span data-ttu-id="52612-224">Para um gerente de loja que está em ambos os grupos, sua função como gerente é mais relevante do que a função de um funcionário, portanto, a política de chamada atribuída ao grupo de gerentes da loja deve ter uma classificação mais alta.</span><span class="sxs-lookup"><span data-stu-id="52612-224">For a store manager who is in both groups, their role as a manager is more relevant than their role as an employee, so the calling policy that's assigned to the Store Managers group should have a higher ranking.</span></span>

|<span data-ttu-id="52612-225">Grupos</span><span class="sxs-lookup"><span data-stu-id="52612-225">Group</span></span> |<span data-ttu-id="52612-226">Nome da política de chamada de equipes</span><span class="sxs-lookup"><span data-stu-id="52612-226">Teams calling policy name</span></span>  |<span data-ttu-id="52612-227">Classificação</span><span class="sxs-lookup"><span data-stu-id="52612-227">Rank</span></span>|
|---------|---------|---|
|<span data-ttu-id="52612-228">Gerentes da loja</span><span class="sxs-lookup"><span data-stu-id="52612-228">Store Managers</span></span>   |<span data-ttu-id="52612-229">Política de chamadas de gerentes de loja</span><span class="sxs-lookup"><span data-stu-id="52612-229">Store Managers Calling Policy</span></span>         |<span data-ttu-id="52612-230">1</span><span class="sxs-lookup"><span data-stu-id="52612-230">1</span></span>|
|<span data-ttu-id="52612-231">Loja de funcionários</span><span class="sxs-lookup"><span data-stu-id="52612-231">Store Employees</span></span>    |<span data-ttu-id="52612-232">Política de chamadas de funcionários da loja</span><span class="sxs-lookup"><span data-stu-id="52612-232">Store Employees Calling Policy</span></span>      |<span data-ttu-id="52612-233">2</span><span class="sxs-lookup"><span data-stu-id="52612-233">2</span></span>|

<span data-ttu-id="52612-234">Se você não especificar uma classificação, a atribuição de política terá a classificação mais baixa.</span><span class="sxs-lookup"><span data-stu-id="52612-234">If you don't specify a ranking, the policy assignment is given the lowest ranking.</span></span> 

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="52612-235">Usando o centro de administração do Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="52612-235">Using the Microsoft Teams admin center</span></span>

> [!NOTE]
> <span data-ttu-id="52612-236">Atualmente, a atribuição de política a grupos usando o centro de administração do Microsoft Teams está disponível apenas para política de chamada de equipes, política de estacionamento de chamada de equipe, política de equipe, política de eventos do Teams, política de reunião do Teams e política de mensagens de equipe.</span><span class="sxs-lookup"><span data-stu-id="52612-236">Currently, policy assignment to groups using the Microsoft Teams admin center is only available for Teams calling policy, Teams call park policy, Teams policy, Teams live events policy, Teams meeting policy, and Teams messaging policy.</span></span> <span data-ttu-id="52612-237">Para outros tipos de política, use o PowerShell.</span><span class="sxs-lookup"><span data-stu-id="52612-237">For other policy types, use PowerShell.</span></span>

1. <span data-ttu-id="52612-238">Na navegação à esquerda do centro de administração do Microsoft Teams, vá para a página tipo de política.</span><span class="sxs-lookup"><span data-stu-id="52612-238">In the left navigation of the Microsoft Teams admin center, go to the policy type page.</span></span> <span data-ttu-id="52612-239">Por exemplo, acesse **Meetings**  >  **políticas de reunião** de reuniões.</span><span class="sxs-lookup"><span data-stu-id="52612-239">For example, go to **Meetings** > **Meeting policies**.</span></span>
2. <span data-ttu-id="52612-240">Selecione a guia **atribuição de política de grupo** .</span><span class="sxs-lookup"><span data-stu-id="52612-240">Select the **Group policy assignment** tab.</span></span>
3. <span data-ttu-id="52612-241">Selecione **Adicionar grupo** e, em seguida, no painel **atribuir política ao grupo** , faça o seguinte:</span><span class="sxs-lookup"><span data-stu-id="52612-241">Select **Add group**, and then in the **Assign policy to group** pane, do the following:</span></span>
    1. <span data-ttu-id="52612-242">Procure e adicione o grupo ao qual você deseja atribuir a política.</span><span class="sxs-lookup"><span data-stu-id="52612-242">Search for and add the group you want to assign the policy to.</span></span>
    2. <span data-ttu-id="52612-243">Defina a classificação para a atribuição de grupo.</span><span class="sxs-lookup"><span data-stu-id="52612-243">Set the ranking for the group assignment.</span></span>
    3. <span data-ttu-id="52612-244">Selecione a política que você deseja atribuir.</span><span class="sxs-lookup"><span data-stu-id="52612-244">Select the policy that you want to assign.</span></span> 
    4. <span data-ttu-id="52612-245">Selecione **aplicar**.</span><span class="sxs-lookup"><span data-stu-id="52612-245">Select **Apply**.</span></span>

<span data-ttu-id="52612-246">Para remover uma atribuição de política de grupo, na guia **atribuição de política de grupo** da página política, selecione a atribuição de grupo e, em seguida, selecione **remover**.</span><span class="sxs-lookup"><span data-stu-id="52612-246">To remove a group policy assignment, on the **Group policy assignment** tab of the policy page, select the group assignment, and then select **Remove**.</span></span>

<span data-ttu-id="52612-247">Para alterar a classificação de uma atribuição de grupo, primeiro você precisa remover a atribuição de política de grupo.</span><span class="sxs-lookup"><span data-stu-id="52612-247">To change the ranking of a group assignment, you have to first remove the group policy assignment.</span></span> <span data-ttu-id="52612-248">Em seguida, siga as etapas acima para atribuir a política a um grupo.</span><span class="sxs-lookup"><span data-stu-id="52612-248">Then, follow the steps above to assign the policy to a group.</span></span>

### <a name="using-powershell"></a><span data-ttu-id="52612-249">Usando o PowerShell</span><span class="sxs-lookup"><span data-stu-id="52612-249">Using PowerShell</span></span>

> [!NOTE]
> <span data-ttu-id="52612-250">Atualmente, a atribuição de política a grupos usando o PowerShell não está disponível para todos os tipos de política de equipe.</span><span class="sxs-lookup"><span data-stu-id="52612-250">Currently, policy assignment to groups using PowerShell isn't available for all Teams policy types.</span></span> <span data-ttu-id="52612-251">Consulte [New-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/new-csgrouppolicyassignment) para obter a lista de tipos de política com suporte.</span><span class="sxs-lookup"><span data-stu-id="52612-251">See [New-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/new-csgrouppolicyassignment) for the list of supported policy types.</span></span>

#### <a name="install-and-connect-to-the-microsoft-teams-powershell-module"></a><span data-ttu-id="52612-252">Instalar e conectar-se ao módulo do PowerShell do Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="52612-252">Install and connect to the Microsoft Teams PowerShell module</span></span>

<span data-ttu-id="52612-253">Para obter orientação passo a passo, consulte instalar o PowerShell do Microsoft [Teams](teams-powershell-install.md).</span><span class="sxs-lookup"><span data-stu-id="52612-253">For step-by-step guidance, see [Install Teams PowerShell](teams-powershell-install.md).</span></span>

#### <a name="assign-a-policy-to-a-group-of-users"></a><span data-ttu-id="52612-254">Atribuir uma política a um grupo de usuários</span><span class="sxs-lookup"><span data-stu-id="52612-254">Assign a policy to a group of users</span></span>

<span data-ttu-id="52612-255">Use o cmdlet [New-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/new-csgrouppolicyassignment) para atribuir uma política a um grupo.</span><span class="sxs-lookup"><span data-stu-id="52612-255">You use the [New-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/new-csgrouppolicyassignment) cmdlet to assign a policy to a group.</span></span> <span data-ttu-id="52612-256">Você pode especificar um grupo usando a identificação do objeto, o endereço SIP ou o endereço de email.</span><span class="sxs-lookup"><span data-stu-id="52612-256">You can specify a group by using the object Id, SIP address, or email address.</span></span>

<span data-ttu-id="52612-257">Neste exemplo, atribuímos uma política de reunião do teams chamada política de reunião de gerentes de revenda a um grupo com uma classificação de atribuição de 1.</span><span class="sxs-lookup"><span data-stu-id="52612-257">In this example, we assign a Teams meeting policy named Retail Managers Meeting Policy to a group with an assignment ranking of 1.</span></span>

```powershell
New-CsGroupPolicyAssignment -GroupId d8ebfa45-0f28-4d2d-9bcc-b158a49e2d17 -PolicyType TeamsMeetingPolicy -PolicyName "Retail Managers Meeting Policy" -Rank 1
```

#### <a name="get-policy-assignments-for-a-group"></a><span data-ttu-id="52612-258">Obter atribuições de política para um grupo</span><span class="sxs-lookup"><span data-stu-id="52612-258">Get policy assignments for a group</span></span>

<span data-ttu-id="52612-259">Use o cmdlet [Get-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/get-csgrouppolicyassignment) para obter todas as políticas atribuídas a um grupo.</span><span class="sxs-lookup"><span data-stu-id="52612-259">Use the [Get-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/get-csgrouppolicyassignment) cmdlet to get all policies assigned to a group.</span></span> <span data-ttu-id="52612-260">Observe que os grupos são sempre listados pela ID do grupo mesmo se seu endereço SIP ou endereço de email foi usado para atribuir a política.</span><span class="sxs-lookup"><span data-stu-id="52612-260">Note that groups are always listed by their group Id even if its SIP address or email address was used to assign the policy.</span></span>

<span data-ttu-id="52612-261">Neste exemplo, recuperamos todas as políticas atribuídas a um grupo específico.</span><span class="sxs-lookup"><span data-stu-id="52612-261">In this example, we retrieve all policies assigned to a specific group.</span></span>

```powershell
Get-CsGroupPolicyAssignment -GroupId e050ce51-54bc-45b7-b3e6-c00343d31274
```

<span data-ttu-id="52612-262">Neste exemplo, retornamos todos os grupos que recebem uma política de reunião do teams.</span><span class="sxs-lookup"><span data-stu-id="52612-262">In this example, we return all groups that are assigned a Teams meeting policy.</span></span>

```powershell
Get-CsGroupPolicyAssignment -PolicyType TeamsMeetingPolicy
```

#### <a name="remove-a-policy-from-a-group"></a><span data-ttu-id="52612-263">Remover uma política de um grupo</span><span class="sxs-lookup"><span data-stu-id="52612-263">Remove a policy from a group</span></span>

<span data-ttu-id="52612-264">Use o cmdlet [Remove-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/remove-csgrouppolicyassignment) para remover uma política de um grupo.</span><span class="sxs-lookup"><span data-stu-id="52612-264">Use the [Remove-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/remove-csgrouppolicyassignment) cmdlet to remove a policy from a group.</span></span> <span data-ttu-id="52612-265">Quando você remove uma política de um grupo, as prioridades de outras políticas do mesmo tipo atribuídas a esse grupo e que têm uma classificação mais baixa são atualizadas.</span><span class="sxs-lookup"><span data-stu-id="52612-265">When you remove a policy from a group, the priorities of other policies of the same type assigned to that group and that have a lower ranking are updated.</span></span> <span data-ttu-id="52612-266">Por exemplo, se você remover uma política que tem uma classificação de 2, as políticas que têm uma classificação de 3 e 4 são atualizadas para refletir a nova classificação.</span><span class="sxs-lookup"><span data-stu-id="52612-266">For example, if you remove a policy that has a ranking of 2, policies that have a ranking of 3 and 4 are updated to reflect their new ranking.</span></span> <span data-ttu-id="52612-267">As duas tabelas a seguir mostram este exemplo.</span><span class="sxs-lookup"><span data-stu-id="52612-267">The following two tables show this example.</span></span>

<span data-ttu-id="52612-268">Aqui está uma lista das atribuições e prioridades de política para uma política de reunião do teams.</span><span class="sxs-lookup"><span data-stu-id="52612-268">Here's a list of the policy assignments and priorities for a Teams meeting policy.</span></span>

|<span data-ttu-id="52612-269">Nome do grupo</span><span class="sxs-lookup"><span data-stu-id="52612-269">Group name</span></span>  |<span data-ttu-id="52612-270">Nome da política</span><span class="sxs-lookup"><span data-stu-id="52612-270">Policy name</span></span>  |<span data-ttu-id="52612-271">Classificação</span><span class="sxs-lookup"><span data-stu-id="52612-271">Rank</span></span>|
|---------|---------|---------|
|<span data-ttu-id="52612-272">Vendas</span><span class="sxs-lookup"><span data-stu-id="52612-272">Sales</span></span>    |<span data-ttu-id="52612-273">Política de vendas</span><span class="sxs-lookup"><span data-stu-id="52612-273">Sales policy</span></span>       | <span data-ttu-id="52612-274">1</span><span class="sxs-lookup"><span data-stu-id="52612-274">1</span></span>        |
|<span data-ttu-id="52612-275">Região oeste</span><span class="sxs-lookup"><span data-stu-id="52612-275">West Region</span></span>     |<span data-ttu-id="52612-276">Política de região oeste</span><span class="sxs-lookup"><span data-stu-id="52612-276">West Region policy</span></span>         |<span data-ttu-id="52612-277">2</span><span class="sxs-lookup"><span data-stu-id="52612-277">2</span></span>         |
|<span data-ttu-id="52612-278">Visões</span><span class="sxs-lookup"><span data-stu-id="52612-278">Division</span></span>    |<span data-ttu-id="52612-279">Política de divisão</span><span class="sxs-lookup"><span data-stu-id="52612-279">Division policy</span></span>         |<span data-ttu-id="52612-280">3</span><span class="sxs-lookup"><span data-stu-id="52612-280">3</span></span>         |
|<span data-ttu-id="52612-281">Subsidiária da</span><span class="sxs-lookup"><span data-stu-id="52612-281">Subsidiary</span></span>   |<span data-ttu-id="52612-282">Política da subsidiária</span><span class="sxs-lookup"><span data-stu-id="52612-282">Subsidiary policy</span></span>        |<span data-ttu-id="52612-283">4</span><span class="sxs-lookup"><span data-stu-id="52612-283">4</span></span>         |

<span data-ttu-id="52612-284">Se removermos a política de região oeste do grupo região oeste, as atribuições e prioridades de política serão atualizadas da maneira a seguir.</span><span class="sxs-lookup"><span data-stu-id="52612-284">If we remove the West Region policy from the West Region group, the policy assignments and priorities are updated as follows.</span></span>

|<span data-ttu-id="52612-285">Nome do grupo</span><span class="sxs-lookup"><span data-stu-id="52612-285">Group name</span></span>  |<span data-ttu-id="52612-286">Nome da política</span><span class="sxs-lookup"><span data-stu-id="52612-286">Policy name</span></span>  |<span data-ttu-id="52612-287">Classificação</span><span class="sxs-lookup"><span data-stu-id="52612-287">Rank</span></span>|
|---------|---------|---------|
|<span data-ttu-id="52612-288">Vendas</span><span class="sxs-lookup"><span data-stu-id="52612-288">Sales</span></span>    |<span data-ttu-id="52612-289">Política de vendas</span><span class="sxs-lookup"><span data-stu-id="52612-289">Sales policy</span></span>       | <span data-ttu-id="52612-290">1</span><span class="sxs-lookup"><span data-stu-id="52612-290">1</span></span>        |
|<span data-ttu-id="52612-291">Visões</span><span class="sxs-lookup"><span data-stu-id="52612-291">Division</span></span>    |<span data-ttu-id="52612-292">Política de divisão</span><span class="sxs-lookup"><span data-stu-id="52612-292">Division policy</span></span>         |<span data-ttu-id="52612-293">2</span><span class="sxs-lookup"><span data-stu-id="52612-293">2</span></span>         |
|<span data-ttu-id="52612-294">Subsidiária da</span><span class="sxs-lookup"><span data-stu-id="52612-294">Subsidiary</span></span>   |<span data-ttu-id="52612-295">Política da subsidiária</span><span class="sxs-lookup"><span data-stu-id="52612-295">Subsidiary policy</span></span>        |<span data-ttu-id="52612-296">3</span><span class="sxs-lookup"><span data-stu-id="52612-296">3</span></span>        |

<span data-ttu-id="52612-297">Neste exemplo, removemos a política de reunião do teams de um grupo.</span><span class="sxs-lookup"><span data-stu-id="52612-297">In this example, we remove the Teams meeting policy from a group.</span></span>

```powershell
Remove-CsGroupPolicyAssignment -PolicyType TeamsMeetingPolicy -GroupId f985e013-0826-40bb-8c94-e5f367076044
```

#### <a name="change-a-policy-assignment-for-a-group"></a><span data-ttu-id="52612-298">Alterar uma atribuição de política para um grupo</span><span class="sxs-lookup"><span data-stu-id="52612-298">Change a policy assignment for a group</span></span>

> [!NOTE]
> <span data-ttu-id="52612-299">O cmdlet [set-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/set-csgrouppolicyassignment) estará disponível em breve.</span><span class="sxs-lookup"><span data-stu-id="52612-299">The [Set-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/set-csgrouppolicyassignment) cmdlet will be available soon.</span></span> <span data-ttu-id="52612-300">Enquanto isso, para alterar uma atribuição de política de grupo, você pode remover a atribuição de política atual do grupo e, em seguida, adicionar uma nova atribuição de política.</span><span class="sxs-lookup"><span data-stu-id="52612-300">In the meantime, to change a group policy assignment, you can remove the current policy assignment from the group, and then add a new policy assignment.</span></span>

<span data-ttu-id="52612-301">Depois de atribuir uma política a um grupo, você pode usar o cmdlet [set-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/set-csgrouppolicyassignment) para alterar a atribuição da política desse grupo da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="52612-301">After you assign a policy to a group, you can use the [Set-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/set-csgrouppolicyassignment) cmdlet to change that group's policy assignment as follows:</span></span>

- <span data-ttu-id="52612-302">Alterar a classificação</span><span class="sxs-lookup"><span data-stu-id="52612-302">Change the ranking</span></span>
- <span data-ttu-id="52612-303">Alterar a política de um determinado tipo de política</span><span class="sxs-lookup"><span data-stu-id="52612-303">Change the policy of a given policy type</span></span>
- <span data-ttu-id="52612-304">Alterar a política de um determinado tipo de política e a classificação</span><span class="sxs-lookup"><span data-stu-id="52612-304">Change the policy of a given policy type and the ranking</span></span>

<span data-ttu-id="52612-305">Neste exemplo, alteramos a política de estacionamento de chamada de equipe de um grupo para uma política chamada SupportCallPark e a classificação de atribuição para 3.</span><span class="sxs-lookup"><span data-stu-id="52612-305">In this example, we change a group's Teams call park policy to a policy named SupportCallPark and the assignment ranking to 3.</span></span>

```powershell
Set-CsGroupPolicyAssignment -GroupId 566b8d39-5c5c-4aaa-bc07-4f36278a1b38 -PolicyType TeamsMeetingPolicy -PolicyName SupportCallPark -Rank 3
```

#### <a name="change-the-effective-policy-for-a-user"></a><span data-ttu-id="52612-306">Alterar a política em vigor para um usuário</span><span class="sxs-lookup"><span data-stu-id="52612-306">Change the effective policy for a user</span></span>

<span data-ttu-id="52612-307">Aqui está um exemplo de como alterar a política efetiva para um usuário que recebe diretamente uma política.</span><span class="sxs-lookup"><span data-stu-id="52612-307">Here's an example of how to change the effective policy for a user who is directly assigned a policy.</span></span>

<span data-ttu-id="52612-308">Primeiro, usamos o cmdlet [Get-CsUserPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/get-csuserpolicyassignment) em conjunto com o ```PolicySource``` parâmetro para obter detalhes das políticas de transmissão de reunião do teams associadas ao usuário.</span><span class="sxs-lookup"><span data-stu-id="52612-308">First, we use the [Get-CsUserPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/get-csuserpolicyassignment) cmdlet together with the ```PolicySource``` parameter to get details of the Teams meeting broadcast policies associated with the user.</span></span> 

```powershell
Get-CsUserPolicyAssignment -Identity daniel@contoso.com -PolicyType TeamsMeetingBroadcastPolicy | select -ExpandProperty PolicySource
```

<span data-ttu-id="52612-309">A saída mostra que o usuário foi diretamente atribuído a uma política de transmissão de reunião do teams chamada eventos do funcionário, que tem precedência sobre a política denominada eventos dinâmicos do fornecedor que é atribuída a um grupo ao qual o usuário pertence.</span><span class="sxs-lookup"><span data-stu-id="52612-309">The output shows that the user was directly assigned a Teams meeting broadcast policy named Employee Events, which takes precedence over the policy named Vendor Live Events that's assigned to a group the user belongs to.</span></span>

```console
AssignmentType PolicyName         Reference
-------------- ----------         ---------
Direct         Employee Events
Group          Vendor Live Events 566b8d39-5c5c-4aaa-bc07-4f36278a1b38
```

<span data-ttu-id="52612-310">Agora, removemos a política de eventos de funcionários do usuário.</span><span class="sxs-lookup"><span data-stu-id="52612-310">Now, we remove the Employee Events policy from the user.</span></span> <span data-ttu-id="52612-311">Isso significa que o usuário não tem mais uma política de transmissão de reunião do teams diretamente atribuída a elas e herdará a política de eventos dinâmicos do fornecedor que é atribuída ao grupo ao qual o usuário pertence.</span><span class="sxs-lookup"><span data-stu-id="52612-311">This means that the user no longer has a Teams meeting broadcast policy directly assigned to them and will inherit the Vendor Live Events policy that's assigned to the group the user belongs to.</span></span> 

<span data-ttu-id="52612-312">Use o cmdlet a seguir no módulo do PowerShell do Skype for Business para fazer isso.</span><span class="sxs-lookup"><span data-stu-id="52612-312">Use the following cmdlet in the Skype for Business PowerShell module to do this.</span></span>

```powershell
Grant-CsTeamsMeetingBroadcastPolicy -Identity daniel@contoso.com -PolicyName $null
```

<span data-ttu-id="52612-313">Você pode usar o cmdlet a seguir no módulo do PowerShell Teams para fazer isso em escala durante uma atribuição de política em lotes, onde $users é uma lista de usuários que você especifica.</span><span class="sxs-lookup"><span data-stu-id="52612-313">You can use following cmdlet in the Teams PowerShell module to do this at scale though a batch policy assignment, where $users is a list of users that you specify.</span></span>

```powershell
New-CsBatchPolicyAssignmentOperation -OperationName "Assigning null at bulk" -PolicyType TeamsMeetingBroadcastPolicy -PolicyName $null -Identity $users  
```

## <a name="assign-a-policy-to-a-batch-of-users"></a><span data-ttu-id="52612-314">Atribuir uma política a um lote de usuários</span><span class="sxs-lookup"><span data-stu-id="52612-314">Assign a policy to a batch of users</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="52612-315">Usando o centro de administração do Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="52612-315">Using the Microsoft Teams admin center</span></span>

<span data-ttu-id="52612-316">Para atribuir uma política a usuários em massa:</span><span class="sxs-lookup"><span data-stu-id="52612-316">To assign a policy to users in bulk:</span></span>

1. <span data-ttu-id="52612-317">Na navegação à esquerda do centro de administração do Microsoft Teams, selecione **usuários**.</span><span class="sxs-lookup"><span data-stu-id="52612-317">In the left navigation of the Microsoft Teams admin center, select **Users**.</span></span>
2. <span data-ttu-id="52612-318">Procure os usuários para os quais você deseja atribuir a política ou filtre o modo de exibição para mostrar os usuários que você deseja.</span><span class="sxs-lookup"><span data-stu-id="52612-318">Search for the users you want to assign the policy to or filter the view to show the users you want.</span></span>
3. <span data-ttu-id="52612-319">Na coluna **&#x2713;** (marca de seleção), selecione os usuários.</span><span class="sxs-lookup"><span data-stu-id="52612-319">In the **&#x2713;** (check mark) column, select the users.</span></span> <span data-ttu-id="52612-320">Para selecionar todos os usuários, clique na (marca de seleção) &#x2713; na parte superior da tabela.</span><span class="sxs-lookup"><span data-stu-id="52612-320">To select all users, click the &#x2713; (check mark) at the top of the table.</span></span>
4. <span data-ttu-id="52612-321">Clique em **Editar configurações**, faça as alterações desejadas e, em seguida, clique em **Aplicar**.</span><span class="sxs-lookup"><span data-stu-id="52612-321">Click **Edit settings**, make the changes that you want, and then click **Apply**.</span></span>

<span data-ttu-id="52612-322">Para exibir o status da atribuição da política, na faixa exibida na parte superior da página **usuários** depois que você clicar em **aplicar** para enviar a atribuição de política, clique em **registro de atividades**.</span><span class="sxs-lookup"><span data-stu-id="52612-322">To view the status of your policy assignment, in the banner that appears at the top of the **Users** page after you click **Apply** to submit your policy assignment, click **Activity log**.</span></span> <span data-ttu-id="52612-323">Ou, no painel de navegação esquerdo do centro de administração do Microsoft Teams, vá até **painel** e, em **registro de atividades**, clique em **Exibir detalhes**.</span><span class="sxs-lookup"><span data-stu-id="52612-323">Or, in the left navigation of the Microsoft Teams admin center, go to **Dashboard**, and then under **Activity log**, click **View details**.</span></span> <span data-ttu-id="52612-324">O registro de atividades mostra as atribuições de política para lotes de mais de 20 usuários por meio do centro de administração do Microsoft Teams dos últimos 30 dias.</span><span class="sxs-lookup"><span data-stu-id="52612-324">The Activity log shows policy assignments to batches of more than 20 users through the Microsoft Teams admin center from the last 30 days.</span></span> <span data-ttu-id="52612-325">Para saber mais, consulte [exibir suas atribuições de política no log de atividades](activity-log.md).</span><span class="sxs-lookup"><span data-stu-id="52612-325">To learn more, see [View your policy assignments in the Activity log](activity-log.md).</span></span>

### <a name="using-powershell"></a><span data-ttu-id="52612-326">Usando o PowerShell</span><span class="sxs-lookup"><span data-stu-id="52612-326">Using PowerShell</span></span>

> [!NOTE]
> <span data-ttu-id="52612-327">No momento, a atribuição de política em lote usando o PowerShell não está disponível para todos os tipos de política de equipe.</span><span class="sxs-lookup"><span data-stu-id="52612-327">Currently, batch policy assignment using PowerShell isn't available for all Teams policy types.</span></span> <span data-ttu-id="52612-328">Consulte [New-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation) para obter a lista de tipos de política com suporte.</span><span class="sxs-lookup"><span data-stu-id="52612-328">See [New-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation) for the list of supported policy types.</span></span>
 
<span data-ttu-id="52612-329">Com a atribuição de política em lotes, você pode atribuir uma política a grandes conjuntos de usuários de uma vez sem precisar usar um script.</span><span class="sxs-lookup"><span data-stu-id="52612-329">With batch policy assignment, you can assign a policy to large sets of users at a time without having to use a script.</span></span> <span data-ttu-id="52612-330">Use o cmdlet [New-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation) para enviar um lote de usuários e a política que você deseja atribuir.</span><span class="sxs-lookup"><span data-stu-id="52612-330">You use the [New-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation) cmdlet to submit a batch of users and the policy that you want to assign.</span></span> <span data-ttu-id="52612-331">As atribuições são processadas como uma operação de plano de fundo e uma ID de operação é gerada para cada lote.</span><span class="sxs-lookup"><span data-stu-id="52612-331">The assignments are processed as a background operation and an operation ID is generated for each batch.</span></span> <span data-ttu-id="52612-332">Em seguida, você pode usar o cmdlet [Get-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/get-csbatchpolicyassignmentoperation) para controlar o progresso e o status das tarefas em um lote.</span><span class="sxs-lookup"><span data-stu-id="52612-332">You can then use the [Get-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/get-csbatchpolicyassignmentoperation) cmdlet to track the progress and status of the assignments in a batch.</span></span>

<span data-ttu-id="52612-333">Você pode especificar os usuários por seu ID de objeto ou endereço SIP (protocolo de iniciação de sessão).</span><span class="sxs-lookup"><span data-stu-id="52612-333">You can specify users by their object Id or Session Initiation Protocol (SIP) address.</span></span> <span data-ttu-id="52612-334">Observe que o endereço SIP de um usuário geralmente tem o mesmo valor que o nome UPN ou endereço de email, mas isso não é necessário.</span><span class="sxs-lookup"><span data-stu-id="52612-334">Note that a user's SIP address often has the same value as the User Principal Name (UPN) or email address, but this is not required.</span></span> <span data-ttu-id="52612-335">Se um usuário for especificado usando seu UPN ou email, mas tiver um valor diferente do endereço SIP, a atribuição de política falhará para o usuário.</span><span class="sxs-lookup"><span data-stu-id="52612-335">If a user is specified using their UPN or email, but it has a different value than their SIP address, then policy assignment will fail for the user.</span></span> <span data-ttu-id="52612-336">Se um lote incluir usuários duplicados, as duplicatas serão removidas do lote antes do processamento e o status só será fornecido para os usuários exclusivos restantes no lote.</span><span class="sxs-lookup"><span data-stu-id="52612-336">If a batch includes duplicate users, the duplicates will be removed from the batch before processing and status will only be provided for the unique users remaining in the batch.</span></span> 

<span data-ttu-id="52612-337">Um lote pode conter até 5.000 usuários.</span><span class="sxs-lookup"><span data-stu-id="52612-337">A batch can contain up to 5,000 users.</span></span> <span data-ttu-id="52612-338">Para obter melhores resultados, não envie mais do que alguns lotes de cada vez.</span><span class="sxs-lookup"><span data-stu-id="52612-338">For best results, do not submit more than a few batches at a time.</span></span> <span data-ttu-id="52612-339">Permitir que os lotes concluam o processamento antes de enviar mais lotes.</span><span class="sxs-lookup"><span data-stu-id="52612-339">Allow batches to complete processing before submitting more batches.</span></span>

#### <a name="install-and-connect-to-the-microsoft-teams-powershell-module"></a><span data-ttu-id="52612-340">Instalar e conectar-se ao módulo do PowerShell do Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="52612-340">Install and connect to the Microsoft Teams PowerShell module</span></span>

<span data-ttu-id="52612-341">Execute o seguinte para instalar o [módulo do Microsoft Teams PowerShell](https://www.powershellgallery.com/packages/MicrosoftTeams).</span><span class="sxs-lookup"><span data-stu-id="52612-341">Run the following to install the [Microsoft Teams PowerShell module](https://www.powershellgallery.com/packages/MicrosoftTeams).</span></span> <span data-ttu-id="52612-342">Verifique se você instalou a versão 1.0.5 ou posterior.</span><span class="sxs-lookup"><span data-stu-id="52612-342">Make sure you install version 1.0.5 or later.</span></span>

```powershell
Install-Module -Name MicrosoftTeams
```

<span data-ttu-id="52612-343">Execute o seguinte para se conectar ao Microsoft Teams e iniciar uma sessão.</span><span class="sxs-lookup"><span data-stu-id="52612-343">Run the following to connect to Teams and start a session.</span></span>

```powershell
Connect-MicrosoftTeams
```

<span data-ttu-id="52612-344">Quando for solicitado, entre usando suas credenciais de administrador.</span><span class="sxs-lookup"><span data-stu-id="52612-344">When you're prompted, sign in using your admin credentials.</span></span>

#### <a name="install-and-connect-to-the-azure-ad-powershell-for-graph-module-optional"></a><span data-ttu-id="52612-345">Instalar e conectar-se ao módulo do Azure AD PowerShell para Graph (opcional)</span><span class="sxs-lookup"><span data-stu-id="52612-345">Install and connect to the Azure AD PowerShell for Graph module (optional)</span></span>

<span data-ttu-id="52612-346">Você também pode [fazer o download e instalar o módulo do Azure ad PowerShell para Graph](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2) (se ainda não tiver feito isso) e se conectar ao Azure ad para que você possa recuperar uma lista de usuários em sua organização.</span><span class="sxs-lookup"><span data-stu-id="52612-346">You may also want to [download and install the Azure AD PowerShell for Graph module](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2) (if you haven't already) and connect to Azure AD so that you can retrieve a list of users in your organization.</span></span>

<span data-ttu-id="52612-347">Execute o seguinte para se conectar ao Azure AD.</span><span class="sxs-lookup"><span data-stu-id="52612-347">Run the following to connect to Azure AD.</span></span>

```powershell
Connect-AzureAD
```

<span data-ttu-id="52612-348">Quando for solicitado, entre usando as mesmas credenciais de administrador usadas para se conectar ao Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="52612-348">When you're prompted, sign in using the same admin credentials that you used to connect to Teams.</span></span>

#### <a name="assign-a-policy-to-a-batch-of-users"></a><span data-ttu-id="52612-349">Atribuir uma política a um lote de usuários</span><span class="sxs-lookup"><span data-stu-id="52612-349">Assign a policy to a batch of users</span></span>

<span data-ttu-id="52612-350">Neste exemplo, usamos o cmdlet [New-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation) para atribuir uma política de configuração de aplicativo chamada política de configuração de aplicativo de RH a um lote de usuários listados no arquivo Users_ids. Text.</span><span class="sxs-lookup"><span data-stu-id="52612-350">In this example, we use the [New-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation) cmdlet to assign an app setup policy named HR App Setup Policy to a batch of users listed in the Users_ids.text file.</span></span>

```powershell
$user_ids = Get-Content .\users_ids.txt
New-CsBatchPolicyAssignmentOperation -PolicyType TeamsAppSetupPolicy -PolicyName "HR App Setup Policy" -Identity $users_ids -OperationName "Example 1 batch"
```

<span data-ttu-id="52612-351">Neste exemplo, nós nos conectamos ao Azure AD para recuperar uma coleção de usuários e atribuir uma política de mensagens chamada novo contratar política de mensagens a um lote de usuários especificados usando o endereço SIP.</span><span class="sxs-lookup"><span data-stu-id="52612-351">In this example, we connect to Azure AD to retrieve a collection of users and then assign a messaging policy named New Hire Messaging Policy to a batch of users specified by using their SIP address.</span></span>

```powershell
Connect-AzureAD
$users = Get-AzureADUser
New-CsBatchPolicyAssignmentOperation -PolicyType TeamsMessagingPolicy -PolicyName "New Hire Messaging Policy" -Identity $users.SipProxyAddress -OperationName "Example 2 batch"
```

#### <a name="get-the-status-of-a-batch-assignment"></a><span data-ttu-id="52612-352">Obter o status de uma atribuição em lote</span><span class="sxs-lookup"><span data-stu-id="52612-352">Get the status of a batch assignment</span></span>

<span data-ttu-id="52612-353">Execute o seguinte para obter o status de uma atribuição em lotes, em que operationId é a ID da operação retornada pelo ```New-CsBatchPolicyAssignmentOperation``` cmdlet para um determinado lote.</span><span class="sxs-lookup"><span data-stu-id="52612-353">Run the following to get the status of a batch assignment, where OperationId is the operation ID that's returned by the ```New-CsBatchPolicyAssignmentOperation``` cmdlet for a given batch.</span></span>

```powershell
$Get-CsBatchPolicyAssignmentOperation -OperationId f985e013-0826-40bb-8c94-e5f367076044 | fl
```

<span data-ttu-id="52612-354">Se a saída mostrar que ocorreu um erro, execute o seguinte para obter mais informações sobre erros, que estão na ```UserState``` propriedade.</span><span class="sxs-lookup"><span data-stu-id="52612-354">If the output shows that an error occurred, run the following to get more information about errors, which are in the ```UserState``` property.</span></span>

```powershell
Get-CsBatchPolicyAssignmentOperation -OperationId f985e013-0826-40bb-8c94-e5f367076044 | Select -ExpandProperty UserState
```

<span data-ttu-id="52612-355">Para saber mais, consulte [Get-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/get-csbatchpolicyassignmentoperation).</span><span class="sxs-lookup"><span data-stu-id="52612-355">To learn more, see [Get-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/get-csbatchpolicyassignmentoperation).</span></span>

## <a name="assign-a-policy-package-to-users"></a><span data-ttu-id="52612-356">Atribuir um pacote de política aos usuários</span><span class="sxs-lookup"><span data-stu-id="52612-356">Assign a policy package to users</span></span>

<span data-ttu-id="52612-357">Um pacote de política no Teams é uma coleção de políticas predefinidas e configurações de política que você pode atribuir aos usuários que têm funções iguais ou semelhantes em sua organização.</span><span class="sxs-lookup"><span data-stu-id="52612-357">A policy package in Teams is a collection of predefined policies and policy settings that you can assign to users who have the same or similar roles in your organization.</span></span> <span data-ttu-id="52612-358">Cada pacote de política é projetado em torno de uma função de usuário e inclui políticas predefinidas e configurações de política que dão suporte a atividades típicas para essa função.</span><span class="sxs-lookup"><span data-stu-id="52612-358">Each policy package is designed around a user role and includes predefined policies and policy settings that support activities typical for that role.</span></span> <span data-ttu-id="52612-359">Alguns exemplos de pacotes de política são o pacote de educação (professor) e o pacote de assistência médica (funcionário clínico).</span><span class="sxs-lookup"><span data-stu-id="52612-359">Some examples of policy packages are the Education (Teacher) package and Healthcare (Clinical worker) package.</span></span> <span data-ttu-id="52612-360">Para saber mais, consulte [gerenciar pacotes de política no Microsoft Teams](manage-policy-packages.md).</span><span class="sxs-lookup"><span data-stu-id="52612-360">To learn more, see [Manage policy packages in Teams](manage-policy-packages.md).</span></span>

### <a name="assign-a-policy-package-to-one-user"></a><span data-ttu-id="52612-361">Atribuir um pacote de política a um usuário</span><span class="sxs-lookup"><span data-stu-id="52612-361">Assign a policy package to one user</span></span>

1. <span data-ttu-id="52612-362">Na barra de navegação à esquerda do centro de administração do Microsoft Teams, vá para **Usuários** e clique no usuário.</span><span class="sxs-lookup"><span data-stu-id="52612-362">In the left navigation of the Microsoft Teams admin center, go to **Users**, and then click the user.</span></span>
2. <span data-ttu-id="52612-363">Na página do usuário, clique em **políticas** e, em seguida, ao lado de **pacote de política**, clique em **Editar**.</span><span class="sxs-lookup"><span data-stu-id="52612-363">On the user's page, click **Policies**, and then next to **Policy package**, click **Edit**.</span></span>
3. <span data-ttu-id="52612-364">No painel **atribuir pacote de política** , selecione o pacote que você deseja atribuir e clique em **salvar**.</span><span class="sxs-lookup"><span data-stu-id="52612-364">In the **Assign policy package** pane, select the package you want to assign, and then click **Save**.</span></span>

### <a name="assign-a-policy-package-to-multiple-users"></a><span data-ttu-id="52612-365">Atribuir um pacote de política a vários usuários</span><span class="sxs-lookup"><span data-stu-id="52612-365">Assign a policy package to multiple users</span></span>

1. <span data-ttu-id="52612-366">Na navegação à esquerda do centro de administração do Microsoft Teams, vá para **pacotes de política** e, em seguida, selecione o pacote de política que você deseja atribuir clicando à esquerda do nome do pacote.</span><span class="sxs-lookup"><span data-stu-id="52612-366">In the left navigation of the Microsoft Teams admin center, go to **Policy packages**, and then select the policy package you want to assign by clicking to the left of the package name.</span></span>
2. <span data-ttu-id="52612-367">Clique em **gerenciar usuários**.</span><span class="sxs-lookup"><span data-stu-id="52612-367">Click **Manage users**.</span></span>
3. <span data-ttu-id="52612-368">No painel **Gerenciar usuários**, procure o usuário pelo nome de exibição ou pelo nome de usuário, escolha o nome e clique em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="52612-368">In the **Manage users** pane, search for the user by display name or by user name, select the name, and then click **Add**.</span></span> <span data-ttu-id="52612-369">Repita esta etapa para cada usuário que você deseja adicionar.</span><span class="sxs-lookup"><span data-stu-id="52612-369">Repeat this step for each user that you want to add.</span></span>
4. <span data-ttu-id="52612-370">Quando tiver terminado de adicionar usuários, clique em **salvar**.</span><span class="sxs-lookup"><span data-stu-id="52612-370">When you're finished adding users, click **Save**.</span></span>

## <a name="assign-a-policy-package-to-a-group"></a><span data-ttu-id="52612-371">Atribua o pacote de política a um grupo.</span><span class="sxs-lookup"><span data-stu-id="52612-371">Assign a policy package to a group</span></span>

<span data-ttu-id="52612-372">**Este recurso está na visualização particular**</span><span class="sxs-lookup"><span data-stu-id="52612-372">**This feature is in private preview**</span></span>

<span data-ttu-id="52612-373">As atribuições de pacote de política aos grupos permitem atribuir várias políticas a um grupo de usuários, como uma lista de distribuição ou grupo de segurança.</span><span class="sxs-lookup"><span data-stu-id="52612-373">Policy package assignment to groups let you assign multiple policies to a group of users, such as a security group or distribution list.</span></span> <span data-ttu-id="52612-374">As atribuições de política serão propagadas para os membros do grupo, de acordo com as regras de precedência.</span><span class="sxs-lookup"><span data-stu-id="52612-374">The policy assignment is propagated to members of the group according to precedence rules.</span></span> <span data-ttu-id="52612-375">À medida que os membros forem adicionados ou removidos de um grupo, as atribuições de política herdadas serão atualizadas.</span><span class="sxs-lookup"><span data-stu-id="52612-375">As members are added to or removed from a group, their inherited policy assignments are updated accordingly.</span></span>

<span data-ttu-id="52612-376">A atribuição de pacote de política para grupos é recomendada para grupos de até 50.000 usuários, mas também funciona com grupos maiores.</span><span class="sxs-lookup"><span data-stu-id="52612-376">Policy package assignment to groups is recommended for groups of up to 50,000 users but it will also work with larger groups.</span></span> 

<span data-ttu-id="52612-377">Quando você atribui o pacote de política, ele é imediatamente atribuído ao grupo.</span><span class="sxs-lookup"><span data-stu-id="52612-377">When you assign the policy package, it's immediately assigned to the group.</span></span> <span data-ttu-id="52612-378">No entanto, observe que a propagação da atribuição da política para os membros do grupo é realizada como uma operação em segundo plano e pode demorar algum tempo, dependendo do tamanho do grupo.</span><span class="sxs-lookup"><span data-stu-id="52612-378">However, note that the propagation of the policy assignment to members of the group is performed as a background operation and may take some time, depending on the size of the group.</span></span> <span data-ttu-id="52612-379">O mesmo é verdadeiro quando uma política é desatribuída de um grupo ou quando os membros são adicionados ou removidos de um grupo.</span><span class="sxs-lookup"><span data-stu-id="52612-379">The same is true when a policy is unassigned from a group, or when members are added to or removed from a group.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="52612-380">Antes de começar, é importante entender [as regras de precedência](#precedence-rules) e a [classificação de atribuição de grupo](#group-assignment-ranking).</span><span class="sxs-lookup"><span data-stu-id="52612-380">Before you get started, it's important to understand [precedence rules](#precedence-rules) and [group assignment ranking](#group-assignment-ranking).</span></span> <span data-ttu-id="52612-381">Certifique-se de ler e entender os conceitos do [que você precisa saber sobre a atribuição de política a grupos,](#what-you-need-to-know-about-policy-assignment-to-groups) anteriormente neste artigo.</span><span class="sxs-lookup"><span data-stu-id="52612-381">Make sure you read and understand the concepts in [What you need to know about policy assignment to groups](#what-you-need-to-know-about-policy-assignment-to-groups) earlier in this article.</span></span>

### <a name="using-the-microsoft-teams-admin-center-coming-soon"></a><span data-ttu-id="52612-382">Usar o centro de administração do Microsoft Teams (disponível em breve)</span><span class="sxs-lookup"><span data-stu-id="52612-382">Using the Microsoft Teams admin center (coming soon)</span></span>

<span data-ttu-id="52612-383">A atribuição de pacote de política a grupos no centro de administração do Microsoft Teams estará disponível em breve.</span><span class="sxs-lookup"><span data-stu-id="52612-383">Policy package assignment to groups in the Microsoft Teams admin center is coming soon.</span></span> <span data-ttu-id="52612-384">Verifique novamente aqui para obter as atualizações mais recentes.</span><span class="sxs-lookup"><span data-stu-id="52612-384">Check back here for the latest updates.</span></span>

### <a name="using-powershell"></a><span data-ttu-id="52612-385">Usando o PowerShell</span><span class="sxs-lookup"><span data-stu-id="52612-385">Using PowerShell</span></span>

#### <a name="install-and-connect-to-the-microsoft-teams-powershell-module"></a><span data-ttu-id="52612-386">Instalar e conectar-se ao módulo do PowerShell do Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="52612-386">Install and connect to the Microsoft Teams PowerShell module</span></span>

<span data-ttu-id="52612-387">Para obter orientação passo a passo, consulte instalar o PowerShell do Microsoft [Teams](teams-powershell-install.md).</span><span class="sxs-lookup"><span data-stu-id="52612-387">For step-by-step guidance, see [Install Teams PowerShell](teams-powershell-install.md).</span></span>

#### <a name="assign-a-policy-package-to-a-group-of-users"></a><span data-ttu-id="52612-388">Atribuir um pacote de política a um grupo de usuários</span><span class="sxs-lookup"><span data-stu-id="52612-388">Assign a policy package to a group of users</span></span>

<span data-ttu-id="52612-389">Use o cmdlet [Grant-CsGroupPolicyPackageAssignment](https://docs.microsoft.com/powershell/module/teams/grant-csgrouppolicypackageassignment) para atribuir um pacote de política a um grupo.</span><span class="sxs-lookup"><span data-stu-id="52612-389">You use the [Grant-CsGroupPolicyPackageAssignment](https://docs.microsoft.com/powershell/module/teams/grant-csgrouppolicypackageassignment) cmdlet to assign a policy package to a group.</span></span> <span data-ttu-id="52612-390">Você pode especificar um grupo usando a identificação do objeto, o endereço SIP ou o endereço de email.</span><span class="sxs-lookup"><span data-stu-id="52612-390">You can specify a group by using the object Id, SIP address, or email address.</span></span> <span data-ttu-id="52612-391">Ao atribuir o pacote de política, especifique uma [classificação de atribuição de grupo](#group-assignment-ranking) para cada tipo de política no pacote de política.</span><span class="sxs-lookup"><span data-stu-id="52612-391">When you assign the policy package, specify a [group assignment ranking](#group-assignment-ranking) for each policy type in the policy package.</span></span> 

<span data-ttu-id="52612-392">Neste exemplo, atribuímos o pacote de política Education_Teacher a um grupo com uma classificação de atribuição 1 para TeamsAppSetupPolicy e TeamsMeetingBroadcastPolicy e uma classificação de 2 para TeamsMeetingPolicy.</span><span class="sxs-lookup"><span data-stu-id="52612-392">In this example, we assign the Education_Teacher policy package to a group with an assignment ranking of 1 for TeamsAppSetupPolicy and TeamsMeetingBroadcastPolicy and a ranking of 2 for TeamsMeetingPolicy.</span></span>

```powershell
Grant-CsGroupPolicyPackageAssignment -GroupId "dae90bb4-120f-4a3e-a15d-30f142e79f69" -PackageName "Education_Teacher" -PolicyRankings "TeamsAppSetupPolicy, 1", "TeamsMeetingBroadcastPolicy, 1", "TeamsMeetingPolicy, 2"
```

## <a name="assign-a-policy-package-to-a-batch-of-users"></a><span data-ttu-id="52612-393">Atribuir um pacote de política a um lote de usuários</span><span class="sxs-lookup"><span data-stu-id="52612-393">Assign a policy package to a batch of users</span></span>

<span data-ttu-id="52612-394">Com a atribuição de pacote de política em lotes, você pode atribuir um pacote de política a grandes conjuntos de usuários por vez sem ter que usar um script.</span><span class="sxs-lookup"><span data-stu-id="52612-394">With batch policy package assignment, you can assign a policy package to large sets of users at a time without having to use a script.</span></span> <span data-ttu-id="52612-395">Use o cmdlet [New-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation) para enviar um lote de usuários e o pacote de política que você deseja atribuir.</span><span class="sxs-lookup"><span data-stu-id="52612-395">You use the [New-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation) cmdlet to submit a batch of users and the policy package that you want to assign.</span></span> <span data-ttu-id="52612-396">As atribuições são processadas como uma operação de plano de fundo e uma ID de operação é gerada para cada lote.</span><span class="sxs-lookup"><span data-stu-id="52612-396">The assignments are processed as a background operation and an operation ID is generated for each batch.</span></span> <span data-ttu-id="52612-397">Em seguida, você pode usar o cmdlet [Get-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/get-csbatchpolicyassignmentoperation) para controlar o progresso e o status das tarefas em um lote.</span><span class="sxs-lookup"><span data-stu-id="52612-397">You can then use the [Get-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/get-csbatchpolicyassignmentoperation) cmdlet to track the progress and status of the assignments in a batch.</span></span>

<span data-ttu-id="52612-398">Você pode especificar os usuários por seu ID de objeto ou endereço SIP (protocolo de iniciação de sessão).</span><span class="sxs-lookup"><span data-stu-id="52612-398">You can specify users by their object Id or Session Initiation Protocol (SIP) address.</span></span> <span data-ttu-id="52612-399">Observe que o endereço SIP de um usuário geralmente tem o mesmo valor que o nome UPN ou endereço de email, mas isso não é necessário.</span><span class="sxs-lookup"><span data-stu-id="52612-399">Note that a user's SIP address often has the same value as the User Principal Name (UPN) or email address, but this is not required.</span></span> <span data-ttu-id="52612-400">Se um usuário for especificado usando seu UPN ou email, mas tiver um valor diferente do endereço SIP, a atribuição de política falhará para o usuário.</span><span class="sxs-lookup"><span data-stu-id="52612-400">If a user is specified using their UPN or email, but it has a different value than their SIP address, then policy assignment will fail for the user.</span></span> <span data-ttu-id="52612-401">Se um lote incluir usuários duplicados, as duplicatas serão removidas do lote antes do processamento e o status só será fornecido para os usuários exclusivos restantes no lote.</span><span class="sxs-lookup"><span data-stu-id="52612-401">If a batch includes duplicate users, the duplicates will be removed from the batch before processing and status will only be provided for the unique users remaining in the batch.</span></span> 

<span data-ttu-id="52612-402">Um lote pode conter até 5.000 usuários.</span><span class="sxs-lookup"><span data-stu-id="52612-402">A batch can contain up to 5,000 users.</span></span> <span data-ttu-id="52612-403">Para obter melhores resultados, não envie mais do que alguns lotes de cada vez.</span><span class="sxs-lookup"><span data-stu-id="52612-403">For best results, do not submit more than a few batches at a time.</span></span> <span data-ttu-id="52612-404">Permitir que os lotes concluam o processamento antes de enviar mais lotes.</span><span class="sxs-lookup"><span data-stu-id="52612-404">Allow batches to complete processing before submitting more batches.</span></span>

### <a name="install-and-connect-to-the-microsoft-teams-powershell-module"></a><span data-ttu-id="52612-405">Instalar e conectar-se ao módulo do PowerShell do Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="52612-405">Install and connect to the Microsoft Teams PowerShell module</span></span>

<span data-ttu-id="52612-406">Execute o seguinte para instalar o [módulo do Microsoft Teams PowerShell](https://www.powershellgallery.com/packages/MicrosoftTeams) (se ainda não tiver feito isso).</span><span class="sxs-lookup"><span data-stu-id="52612-406">Run the following to install the [Microsoft Teams PowerShell module](https://www.powershellgallery.com/packages/MicrosoftTeams) (if you haven't already).</span></span> <span data-ttu-id="52612-407">Verifique se você instalou a versão 1.0.5 ou posterior.</span><span class="sxs-lookup"><span data-stu-id="52612-407">Make sure you install version 1.0.5 or later.</span></span>

```powershell
Install-Module -Name MicrosoftTeams
```

<span data-ttu-id="52612-408">Execute o seguinte para se conectar ao Microsoft Teams e iniciar uma sessão.</span><span class="sxs-lookup"><span data-stu-id="52612-408">Run the following to connect to Teams and start a session.</span></span>

```powershell
Connect-MicrosoftTeams
```

<span data-ttu-id="52612-409">Quando for solicitado, entre usando suas credenciais de administrador.</span><span class="sxs-lookup"><span data-stu-id="52612-409">When you're prompted, sign in using your admin credentials.</span></span>

### <a name="assign-a-policy-package-to-a-batch-of-users"></a><span data-ttu-id="52612-410">Atribuir um pacote de política a um lote de usuários</span><span class="sxs-lookup"><span data-stu-id="52612-410">Assign a policy package to a batch of users</span></span>

<span data-ttu-id="52612-411">Neste exemplo, usamos o cmdlet [New-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation) para atribuir o pacote de política de Education_PrimaryStudent a um lote de usuários.</span><span class="sxs-lookup"><span data-stu-id="52612-411">In this example, we use the [New-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation) cmdlet to assign the Education_PrimaryStudent policy package to a batch of users.</span></span>

```powershell
New-CsBatchPolicyPackageAssignmentOperation -Identity 1bc0b35f-095a-4a37-a24c-c4b6049816ab,user1@econtoso.com,user2@contoso.com -PackageName Education_PrimaryStudent
```

### <a name="get-the-status-of-a-batch-assignment"></a><span data-ttu-id="52612-412">Obter o status de uma atribuição em lote</span><span class="sxs-lookup"><span data-stu-id="52612-412">Get the status of a batch assignment</span></span>

<span data-ttu-id="52612-413">Execute o seguinte para obter o status de uma atribuição em lotes, em que operationId é a ID da operação retornada pelo ```New-CsBatchPolicyAssignmentOperation``` cmdlet para um determinado lote.</span><span class="sxs-lookup"><span data-stu-id="52612-413">Run the following to get the status of a batch assignment, where OperationId is the operation ID that's returned by the ```New-CsBatchPolicyAssignmentOperation``` cmdlet for a given batch.</span></span>

```powershell
$Get-CsBatchPolicyAssignmentOperation -OperationId f985e013-0826-40bb-8c94-e5f367076044 | fl
```

<span data-ttu-id="52612-414">Se a saída mostrar que ocorreu um erro, execute o seguinte para obter mais informações sobre erros, que estão na ```UserState``` propriedade.</span><span class="sxs-lookup"><span data-stu-id="52612-414">If the output shows that an error occurred, run the following to get more information about errors, which are in the ```UserState``` property.</span></span>

```powershell
Get-CsBatchPolicyAssignmentOperation -OperationId f985e013-0826-40bb-8c94-e5f367076044 | Select -ExpandProperty UserState
```

<span data-ttu-id="52612-415">Para saber mais, consulte [Get-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/get-csbatchpolicyassignmentoperation).</span><span class="sxs-lookup"><span data-stu-id="52612-415">To learn more, see [Get-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/get-csbatchpolicyassignmentoperation).</span></span> 

## <a name="related-topics"></a><span data-ttu-id="52612-416">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="52612-416">Related topics</span></span>

[<span data-ttu-id="52612-417">Visão Geral do PowerShell do Teams</span><span class="sxs-lookup"><span data-stu-id="52612-417">Teams PowerShell Overview</span></span>](teams-powershell-overview.md)
