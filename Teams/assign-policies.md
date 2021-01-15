---
title: Atribuir políticas aos usuários no Microsoft Teams
author: cichur
ms.author: v-cichur
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
description: Saiba as diferentes maneiras de atribuir políticas aos seus usuários no Microsoft Teams.
f1keywords:
- ms.teamsadmincenter.bulkoperations.users.edit
- ms.teamsadmincenter.bulkoperations.edit
ms.openlocfilehash: 5d213c53de22994d46e7d7faf54a8dfd687806d7
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49821301"
---
# <a name="assign-policies-to-your-users-in-microsoft-teams"></a><span data-ttu-id="cd6a1-103">Atribuir políticas aos usuários no Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="cd6a1-103">Assign policies to your users in Microsoft Teams</span></span>

<span data-ttu-id="cd6a1-104">Como administrador, você usa políticas para controlar os recursos do Teams que estão disponíveis para os usuários em sua organização.</span><span class="sxs-lookup"><span data-stu-id="cd6a1-104">As an admin, you use policies to control the Teams features that are available to users in your organization.</span></span> <span data-ttu-id="cd6a1-105">Por exemplo, há políticas de chamada, políticas de reunião e políticas de mensagens, para citar apenas algumas.</span><span class="sxs-lookup"><span data-stu-id="cd6a1-105">For example, there are calling policies, meeting policies, and messaging policies, to name just a few.</span></span>

<span data-ttu-id="cd6a1-106">As organizações têm diferentes tipos de usuários com necessidades exclusivas e políticas personalizadas que você cria e atribui permitem adaptar as configurações de política a diferentes conjuntos de usuários com base nessas necessidades.</span><span class="sxs-lookup"><span data-stu-id="cd6a1-106">Organizations have different types of users with unique needs and custom policies that you create and assign let you tailor policy settings to different sets of users based on those needs.</span></span>

<span data-ttu-id="cd6a1-107">Para facilitar o gerenciamento de políticas em sua organização, o Teams oferece várias maneiras de atribuir políticas aos usuários.</span><span class="sxs-lookup"><span data-stu-id="cd6a1-107">To make it easier to manage policies in your organization, Teams offers several ways to assign policies to users.</span></span> <span data-ttu-id="cd6a1-108">Você pode atribuir uma política diretamente aos usuários, individualmente ou em escala por meio de uma atribuição em lotes ou a um grupo do que os usuários são membros.</span><span class="sxs-lookup"><span data-stu-id="cd6a1-108">You can assign a policy directly to users, either individually or at scale through a batch assignment, or to a group that the users are members of.</span></span> <span data-ttu-id="cd6a1-109">Você também pode usar pacotes de política para atribuir uma coleção predefinida de políticas a usuários em sua organização que tenham funções semelhantes.</span><span class="sxs-lookup"><span data-stu-id="cd6a1-109">You can also use policy packages to assign a preset collection of policies to users in your organization who have similar roles.</span></span> <span data-ttu-id="cd6a1-110">A opção escolhida depende do número de políticas que você está gerenciando e do número de usuários aos quais você está atribuindo.</span><span class="sxs-lookup"><span data-stu-id="cd6a1-110">The option that you choose depends on the number of policies that you're managing and the number of users that you're assigning to.</span></span> <span data-ttu-id="cd6a1-111">Ao definir as políticas globais (padrão em toda a organização) para que elas se apliquem ao maior número de usuários em sua organização, você só precisa atribuir políticas aos usuários que exigem políticas especializadas.</span><span class="sxs-lookup"><span data-stu-id="cd6a1-111">By setting the global (Org-wide default) policies so that they apply to the largest number of users in your organization, you only have to assign policies to those users that require specialized policies.</span></span>

<span data-ttu-id="cd6a1-112">Este artigo descreve as diferentes maneiras pelas quais você pode atribuir políticas aos usuários e os cenários recomendados para quando usar o quê.</span><span class="sxs-lookup"><span data-stu-id="cd6a1-112">This article describes the different ways that you can assign policies to users and the recommended scenarios for when to use what.</span></span>

## <a name="which-policy-takes-precedence"></a><span data-ttu-id="cd6a1-113">Qual política tem precedência?</span><span class="sxs-lookup"><span data-stu-id="cd6a1-113">Which policy takes precedence?</span></span>

<span data-ttu-id="cd6a1-114">Um usuário tem uma política efetiva para cada tipo de política.</span><span class="sxs-lookup"><span data-stu-id="cd6a1-114">A user has one effective policy for each policy type.</span></span> <span data-ttu-id="cd6a1-115">É possível ou até mesmo provável que um usuário tenha uma política atribuída diretamente e também seja membro de um ou mais grupos que tenha atribuído uma política do mesmo tipo.</span><span class="sxs-lookup"><span data-stu-id="cd6a1-115">It's possible or even likely that a user is directly assigned a policy and is also a member of one or more groups that's assigned a policy of the same type.</span></span> <span data-ttu-id="cd6a1-116">Nesses tipos de cenários, qual política tem precedência?</span><span class="sxs-lookup"><span data-stu-id="cd6a1-116">In these kinds of scenarios, which policy takes precedence?</span></span>  <span data-ttu-id="cd6a1-117">A política efetiva de um usuário é determinada de acordo com as regras de precedência, da seguinte maneira.</span><span class="sxs-lookup"><span data-stu-id="cd6a1-117">A user's effective policy is determined according to rules of precedence, as follows.</span></span>

<span data-ttu-id="cd6a1-118">Se um usuário for atribuído diretamente a uma política (individualmente ou por meio de uma atribuição em lotes), essa política tem precedência.</span><span class="sxs-lookup"><span data-stu-id="cd6a1-118">If a user is directly assigned a policy (either individually or through a batch assignment), that policy takes precedence.</span></span> <span data-ttu-id="cd6a1-119">No exemplo a seguir, a política efetiva do usuário é a política de reunião square Square, que é atribuída diretamente ao usuário.</span><span class="sxs-lookup"><span data-stu-id="cd6a1-119">In the following example, the user's effective policy is the Lincoln Square meeting policy, which is directly assigned to the user.</span></span>

![Diagrama mostrando como uma política atribuída diretamente tem precedência](media/assign-policies-example-directly-assigned.png)

<span data-ttu-id="cd6a1-121">Se um usuário não for atribuído diretamente a uma política de um determinado tipo, a política atribuída a um grupo do qual o usuário é membro tem precedência.</span><span class="sxs-lookup"><span data-stu-id="cd6a1-121">If a user isn't directly assigned a policy of a given type, the policy assigned to a group that the user is a member of takes precedence.</span></span> <span data-ttu-id="cd6a1-122">Se um usuário for membro de vários grupos, [](#group-assignment-ranking) a política que tiver a classificação de atribuição de grupo mais alta para o tipo de política determinado terá precedência.</span><span class="sxs-lookup"><span data-stu-id="cd6a1-122">If a user is a member of multiple groups, the policy that has the highest [group assignment ranking](#group-assignment-ranking) for the given policy type takes precedence.</span></span>

<span data-ttu-id="cd6a1-123">Neste exemplo, a política efetiva do usuário é a política Exec Teams e HD, que tem a classificação de atribuição mais alta em relação a outros grupos dos quais o usuário é membro e que também recebe uma política do mesmo tipo de política.</span><span class="sxs-lookup"><span data-stu-id="cd6a1-123">In this example, the user's effective policy is the Exec Teams and HD policy, which has the highest assignment ranking relative to other groups that the user is a member of and that are also assigned a policy of the same policy type.</span></span>  

![Diagrama mostrando como uma política herdada do grupo tem precedência](media/assign-policies-example-group.png)

<span data-ttu-id="cd6a1-125">Se um usuário não for atribuído diretamente a uma política ou não for membro de nenhum grupo atribuído a uma política, o usuário obtém a política global (padrão em toda a organização) para esse tipo de política.</span><span class="sxs-lookup"><span data-stu-id="cd6a1-125">If a user isn't directly assigned a policy or isn't a member of any groups that are assigned a policy, the user gets the global (Org-wide default) policy for that policy type.</span></span> <span data-ttu-id="cd6a1-126">Veja um exemplo.</span><span class="sxs-lookup"><span data-stu-id="cd6a1-126">Here's an example.</span></span>

![Diagrama mostrando como uma política global tem precedência](media/assign-policies-example-global.png)

<span data-ttu-id="cd6a1-128">Para saber mais, consulte [regras de precedência.](#precedence-rules)</span><span class="sxs-lookup"><span data-stu-id="cd6a1-128">To learn more, see [Precedence rules](#precedence-rules).</span></span>

## <a name="ways-to-assign-policies"></a><span data-ttu-id="cd6a1-129">Maneiras de atribuir políticas</span><span class="sxs-lookup"><span data-stu-id="cd6a1-129">Ways to assign policies</span></span>

<span data-ttu-id="cd6a1-130">Aqui está uma visão geral das maneiras pelas quais você pode atribuir políticas aos usuários e os cenários recomendados para cada um deles.</span><span class="sxs-lookup"><span data-stu-id="cd6a1-130">Here's an overview of the ways that you can assign policies to users and the recommended scenarios for each.</span></span> <span data-ttu-id="cd6a1-131">Clique nos links para saber mais.</span><span class="sxs-lookup"><span data-stu-id="cd6a1-131">Click the links to learn more.</span></span>

<span data-ttu-id="cd6a1-132">Antes de atribuir políticas a usuários ou grupos individuais, comece definindo as políticas [globais (padrão](#set-the-global-policies) em toda a organização) para que elas se apliquem ao maior número de usuários em sua organização.</span><span class="sxs-lookup"><span data-stu-id="cd6a1-132">Before assigning policies to individual users or groups, start by [setting the global (Org-wide default) policies](#set-the-global-policies) so that they apply to the largest number of users in your organization.</span></span>  <span data-ttu-id="cd6a1-133">Depois que as políticas globais são definidas, você só precisará atribuir políticas aos usuários que exigem políticas especializadas.</span><span class="sxs-lookup"><span data-stu-id="cd6a1-133">Once the global policies are set, you will only need to assign policies to those users that require specialized policies.</span></span>

|<span data-ttu-id="cd6a1-134">Faça isto</span><span class="sxs-lookup"><span data-stu-id="cd6a1-134">Do this</span></span>  |<span data-ttu-id="cd6a1-135">Se...</span><span class="sxs-lookup"><span data-stu-id="cd6a1-135">If...</span></span>  | <span data-ttu-id="cd6a1-136">Usando...</span><span class="sxs-lookup"><span data-stu-id="cd6a1-136">Using...</span></span>
|---------|---------|----|
|[<span data-ttu-id="cd6a1-137">Atribuir uma política a usuários individuais</span><span class="sxs-lookup"><span data-stu-id="cd6a1-137">Assign a policy to individual users</span></span>](#assign-a-policy-to-individual-users)    | <span data-ttu-id="cd6a1-138">Você é novo no Teams e está apenas começando ou só precisa atribuir uma ou duas políticas a um pequeno número de usuários.</span><span class="sxs-lookup"><span data-stu-id="cd6a1-138">You're new to Teams and just getting started or you only need to assign one or a couple of policies to a small number of users.</span></span> |<span data-ttu-id="cd6a1-139">O centro de administração do Microsoft Teams ou os cmdlets do PowerShell no módulo PowerShell do Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="cd6a1-139">The Microsoft Teams admin center or PowerShell cmdlets in the Skype for Business Online PowerShell module</span></span>
|[<span data-ttu-id="cd6a1-140">Atribuir uma política a um grupo</span><span class="sxs-lookup"><span data-stu-id="cd6a1-140">Assign a policy to a group</span></span>](#assign-a-policy-to-a-group) |<span data-ttu-id="cd6a1-141">Você precisa atribuir políticas com base na associação de grupo de um usuário.</span><span class="sxs-lookup"><span data-stu-id="cd6a1-141">You need to assign policies based on a user's group membership.</span></span> <span data-ttu-id="cd6a1-142">Por exemplo, você deseja atribuir uma política a todos os usuários em um grupo de segurança ou lista de distribuição.</span><span class="sxs-lookup"><span data-stu-id="cd6a1-142">For example, you want to assign a policy to all users in a security group or distribution list.</span></span>| <span data-ttu-id="cd6a1-143">O centro de administração do Microsoft Teams ou os cmdlets do PowerShell no módulo do PowerShell do Teams</span><span class="sxs-lookup"><span data-stu-id="cd6a1-143">The Microsoft Teams admin center or PowerShell cmdlets in the Teams PowerShell module</span></span>|
|[<span data-ttu-id="cd6a1-144">Atribuir uma política a um lote de usuários</span><span class="sxs-lookup"><span data-stu-id="cd6a1-144">Assign a policy to a batch of users</span></span>](#assign-a-policy-to-a-batch-of-users)   | <span data-ttu-id="cd6a1-145">Você precisa atribuir políticas a grandes conjuntos de usuários.</span><span class="sxs-lookup"><span data-stu-id="cd6a1-145">You need to assign policies to large sets of users.</span></span> <span data-ttu-id="cd6a1-146">Por exemplo, você deseja atribuir uma política a centenas ou milhares de usuários em sua organização por vez.</span><span class="sxs-lookup"><span data-stu-id="cd6a1-146">For example, you want to assign a policy to hundreds or thousands of users in your organization at a time.</span></span>  |<span data-ttu-id="cd6a1-147">O centro de administração do Microsoft Teams ou os cmdlets do PowerShell no módulo do PowerShell do Teams</span><span class="sxs-lookup"><span data-stu-id="cd6a1-147">The Microsoft Teams admin center or PowerShell cmdlets in the Teams PowerShell module</span></span>|
| [<span data-ttu-id="cd6a1-148">Atribuir um pacote de política aos usuários</span><span class="sxs-lookup"><span data-stu-id="cd6a1-148">Assign a policy package to users</span></span>](#assign-a-policy-package-to-users)  | <span data-ttu-id="cd6a1-149">Você precisa atribuir várias políticas a conjuntos específicos de usuários em sua organização que tenham as mesmas funções ou funções semelhantes.</span><span class="sxs-lookup"><span data-stu-id="cd6a1-149">You need to assign multiple policies to specific sets of users in your organization who have the same or similar roles.</span></span> <span data-ttu-id="cd6a1-150">Por exemplo, atribua o pacote de política Educação (Professor) aos professores em sua escola para dar a eles acesso total a chats, chamada e reuniões e ao pacote de política de Educação (aluno secundário) para alunos secundários para limitar determinados recursos, como chamada privada.</span><span class="sxs-lookup"><span data-stu-id="cd6a1-150">For example, assign the Education (Teacher) policy package to teachers in your school to give them full access to chats, calling, and meetings and the Education (Secondary school student) policy package to secondary students to limit certain capabilities like private calling.</span></span>  |<span data-ttu-id="cd6a1-151">O centro de administração do Microsoft Teams ou os cmdlets do PowerShell no módulo do PowerShell do Teams</span><span class="sxs-lookup"><span data-stu-id="cd6a1-151">The Microsoft Teams admin center or PowerShell cmdlets in the Teams PowerShell module</span></span>|
| <span data-ttu-id="cd6a1-152">[Atribuir um pacote de política a um grupo](#assign-a-policy-package-to-a-group) (em visualização privada)</span><span class="sxs-lookup"><span data-stu-id="cd6a1-152">[Assign a policy package to a group](#assign-a-policy-package-to-a-group) (in private preview)</span></span>   |<span data-ttu-id="cd6a1-153">Você precisa atribuir várias políticas a um grupo de usuários em sua organização que tenham as mesmas funções ou funções semelhantes.</span><span class="sxs-lookup"><span data-stu-id="cd6a1-153">You need to assign multiple policies to a group of users in your organization who have the same or similar roles.</span></span> <span data-ttu-id="cd6a1-154">Por exemplo, você deseja atribuir um pacote de política a todos os usuários em um grupo de segurança ou lista de distribuição.</span><span class="sxs-lookup"><span data-stu-id="cd6a1-154">For example, you want to assign a policy package to all users in a security group or distribution list.</span></span> |<span data-ttu-id="cd6a1-155">O centro de administração do Microsoft Teams (em breve) ou os cmdlets do PowerShell no módulo PowerShell do Teams</span><span class="sxs-lookup"><span data-stu-id="cd6a1-155">The Microsoft Teams admin center (coming soon) or PowerShell cmdlets in the Teams PowerShell module</span></span>|
| [<span data-ttu-id="cd6a1-156">Atribuir um pacote de política a um lote de usuários</span><span class="sxs-lookup"><span data-stu-id="cd6a1-156">Assign a policy package to a batch of users</span></span>](#assign-a-policy-package-to-a-batch-of-users)|<span data-ttu-id="cd6a1-157">Você precisa atribuir várias políticas a um lote de usuários em sua organização que têm as mesmas funções ou funções semelhantes.</span><span class="sxs-lookup"><span data-stu-id="cd6a1-157">You need to assign multiple policies to a batch of users in your organization who have the same or similar roles.</span></span> <span data-ttu-id="cd6a1-158">Por exemplo, atribua o pacote de política Educação (Professor) a todos os professores em sua escola usando a atribuição em lotes para dar a eles acesso total a chats, chamada e reuniões e atribua o pacote de política de educação (estudante secundário) a um lote de alunos secundários para limitar determinados recursos, como chamada privada.</span><span class="sxs-lookup"><span data-stu-id="cd6a1-158">For example, assign the Education (Teacher) policy package to all teachers in your school using batch assignment to give them full access to chats, calling, and meetings and assign the Education (Secondary school student) policy package to a batch of secondary students to limit certain capabilities like private calling.</span></span>|<span data-ttu-id="cd6a1-159">Cmdlets do PowerShell no módulo do PowerShell do Teams</span><span class="sxs-lookup"><span data-stu-id="cd6a1-159">PowerShell cmdlets in the Teams PowerShell module</span></span>|


## <a name="set-the-global-policies"></a><span data-ttu-id="cd6a1-160">Definir as políticas globais</span><span class="sxs-lookup"><span data-stu-id="cd6a1-160">Set the global policies</span></span>

<span data-ttu-id="cd6a1-161">Siga estas etapas para definir as políticas globais (padrão em toda a organização) para cada tipo de política.</span><span class="sxs-lookup"><span data-stu-id="cd6a1-161">Follow these steps to set the global (Org-wide default) policies for each policy type.</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="cd6a1-162">Usando o centro de administração do Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="cd6a1-162">Using the Microsoft Teams admin center</span></span>

1. <span data-ttu-id="cd6a1-163">Na navegação à esquerda do centro de administração do Microsoft Teams, vá para a página de política do tipo de política que você deseja atualizar.</span><span class="sxs-lookup"><span data-stu-id="cd6a1-163">In the left navigation of the Microsoft Teams admin center, go to the policy page for the policy type you want to update.</span></span> <span data-ttu-id="cd6a1-164">Por exemplo, políticas **do**  >  **Teams Teams,** políticas de   >  **Reuniões,** **políticas de mensagens** ou políticas de **Chamada** de  >  **Voz.**</span><span class="sxs-lookup"><span data-stu-id="cd6a1-164">For example, **Teams** > **Teams policies**, **Meetings** > **Meetings policies**, **Messaging policies**, or **Voice** > **Calling policies**.</span></span>
2. <span data-ttu-id="cd6a1-165">Selecione a **política Global (padrão em toda** a organização) para exibir as configurações atuais.</span><span class="sxs-lookup"><span data-stu-id="cd6a1-165">Select the **Global (Org-wide default)** policy to view the current settings.</span></span>
3. <span data-ttu-id="cd6a1-166">Atualize a política conforme necessário e selecione **Aplicar**.</span><span class="sxs-lookup"><span data-stu-id="cd6a1-166">Update the policy as needed, and then select **Apply**.</span></span>

### <a name="using-powershell"></a><span data-ttu-id="cd6a1-167">Usando o Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="cd6a1-167">Using PowerShell</span></span>

<span data-ttu-id="cd6a1-168">Para definir as políticas globais usando o PowerShell, use o identificador Global.</span><span class="sxs-lookup"><span data-stu-id="cd6a1-168">To set the global policies using PowerShell, use the Global identifier.</span></span>  <span data-ttu-id="cd6a1-169">Comece revendo a política global atual para determinar qual configuração você deseja alterar.</span><span class="sxs-lookup"><span data-stu-id="cd6a1-169">Start by reviewing the current Global policy to determine which setting you want to change.</span></span>

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

<span data-ttu-id="cd6a1-170">Em seguida, atualize a política global conforme necessário.</span><span class="sxs-lookup"><span data-stu-id="cd6a1-170">Next, update the Global policy as needed.</span></span>  <span data-ttu-id="cd6a1-171">Você só precisa especificar valores para as configurações que deseja alterar.</span><span class="sxs-lookup"><span data-stu-id="cd6a1-171">You only need to specify values for the settings that you want to change.</span></span> 
 
```powershell
Set-CsTeamsMessagingPolicy -Identity Global -AllowUserEditMessage $false
```

## <a name="assign-a-policy-to-individual-users"></a><span data-ttu-id="cd6a1-172">Atribuir uma política a usuários individuais</span><span class="sxs-lookup"><span data-stu-id="cd6a1-172">Assign a policy to individual users</span></span>

<span data-ttu-id="cd6a1-173">Siga estas etapas para atribuir uma política a um usuário individual ou a um pequeno número de usuários por vez.</span><span class="sxs-lookup"><span data-stu-id="cd6a1-173">Follow these steps to assign a policy to an individual user or to a small number of users at a time.</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="cd6a1-174">Usando o centro de administração do Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="cd6a1-174">Using the Microsoft Teams admin center</span></span>

<span data-ttu-id="cd6a1-175">Para atribuir uma política a um usuário:</span><span class="sxs-lookup"><span data-stu-id="cd6a1-175">To assign a policy to a user:</span></span>

1. <span data-ttu-id="cd6a1-176">Na barra de navegação à esquerda do centro de administração do Microsoft Teams, vá para **Usuários** e clique no usuário.</span><span class="sxs-lookup"><span data-stu-id="cd6a1-176">In the left navigation of the Microsoft Teams admin center, go to **Users**, and then click the user.</span></span>
2. <span data-ttu-id="cd6a1-177">Selecione o usuário clicando à esquerda do nome de exibição do usuário e clique em **Editar configurações**.</span><span class="sxs-lookup"><span data-stu-id="cd6a1-177">Select the user by clicking to the left of the user name, and then click **Edit settings**.</span></span>
3. <span data-ttu-id="cd6a1-178">Selecione a política que você deseja atribuir e clique em **Aplicar.**</span><span class="sxs-lookup"><span data-stu-id="cd6a1-178">Select the policy you want to assign, and then click **Apply**.</span></span>

<span data-ttu-id="cd6a1-179">Ou você também pode fazer o seguinte:</span><span class="sxs-lookup"><span data-stu-id="cd6a1-179">Or, you can also do the following:</span></span>

1. <span data-ttu-id="cd6a1-180">Na navegação à esquerda do centro de administração do Microsoft Teams, vá para a página de política.</span><span class="sxs-lookup"><span data-stu-id="cd6a1-180">In the left navigation of the Microsoft Teams admin center, go to the policy page.</span></span>
2. <span data-ttu-id="cd6a1-181">Selecione a política que você deseja atribuir clicando à esquerda do nome da política.</span><span class="sxs-lookup"><span data-stu-id="cd6a1-181">Select the policy you want to assign by clicking to the left of the policy name.</span></span>
3. <span data-ttu-id="cd6a1-182">Escolha **Gerenciar usuários**.</span><span class="sxs-lookup"><span data-stu-id="cd6a1-182">Select **Manage users**.</span></span>
4. <span data-ttu-id="cd6a1-183">No painel **Gerenciar usuários**, procure o usuário pelo nome de exibição ou pelo nome de usuário, escolha o nome e marque **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="cd6a1-183">In the **Manage users** pane, search for the user by display name or by user name, select the name, and then select **Add**.</span></span> <span data-ttu-id="cd6a1-184">Repita esta etapa para cada usuário que você deseja adicionar.</span><span class="sxs-lookup"><span data-stu-id="cd6a1-184">Repeat this step for each user that you want to add.</span></span>
5. <span data-ttu-id="cd6a1-185">Quando terminar de adicionar usuários, selecione **Aplicar**.</span><span class="sxs-lookup"><span data-stu-id="cd6a1-185">When you're finished adding users, select **Apply**.</span></span>

### <a name="using-powershell"></a><span data-ttu-id="cd6a1-186">Usando o Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="cd6a1-186">Using PowerShell</span></span>

<span data-ttu-id="cd6a1-187">Cada tipo de política tem seu próprio conjunto de cmdlets para gereí-lo.</span><span class="sxs-lookup"><span data-stu-id="cd6a1-187">Each policy type has its own set of cmdlets for managing it.</span></span> <span data-ttu-id="cd6a1-188">Use o ```Grant-``` cmdlet para um determinado tipo de política para atribuir a política.</span><span class="sxs-lookup"><span data-stu-id="cd6a1-188">Use the ```Grant-``` cmdlet for a given policy type to assign the policy.</span></span> <span data-ttu-id="cd6a1-189">Por exemplo, use o ```Grant-CsTeamsMeetingPolicy``` cmdlet para atribuir uma política de reunião do Teams aos usuários.</span><span class="sxs-lookup"><span data-stu-id="cd6a1-189">For example, use the ```Grant-CsTeamsMeetingPolicy``` cmdlet to assign a Teams meeting policy to users.</span></span> <span data-ttu-id="cd6a1-190">Esses cmdlets estão incluídos no módulo PowerShell do Skype for Business Online e estão documentados na referência [de cmdlet](https://docs.microsoft.com/powershell/skype/intro?view=skype-ps)do Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="cd6a1-190">These cmdlets are included in the Skype for Business Online PowerShell module and are documented in the [Skype for Business cmdlet reference](https://docs.microsoft.com/powershell/skype/intro?view=skype-ps).</span></span>

 <span data-ttu-id="cd6a1-191">Baixe e instale o módulo [do PowerShell](https://www.microsoft.com/download/details.aspx?id=39366) do Skype for Business Online (caso ainda não tenha feito isso) e execute o seguinte para se conectar ao Skype for Business Online e iniciar uma sessão.</span><span class="sxs-lookup"><span data-stu-id="cd6a1-191">Download and install the [Skype for Business Online PowerShell module](https://www.microsoft.com/download/details.aspx?id=39366) (if you haven't already), and then run the following to connect to Skype for Business Online and start a session.</span></span>

> [!NOTE]
> <span data-ttu-id="cd6a1-192">O Conector do Skype for Business Online atualmente faz parte do módulo mais recente do PowerShell do Teams.</span><span class="sxs-lookup"><span data-stu-id="cd6a1-192">Skype for Business Online Connector is currently part of the latest Teams PowerShell module.</span></span>
>
> <span data-ttu-id="cd6a1-193">Se você estiver usando a versão pública mais recente do PowerShell do [Teams,](https://www.powershellgallery.com/packages/MicrosoftTeams/)não será necessário instalar o Conector do Skype for Business Online.</span><span class="sxs-lookup"><span data-stu-id="cd6a1-193">If you're using the latest [Teams PowerShell public release](https://www.powershellgallery.com/packages/MicrosoftTeams/), you don't need to install the Skype for Business Online Connector.</span></span>

```powershell
Import-Module -Name MicrosoftTeams
$Cred = Get-Credential
$CSSession = New-CsOnlineSession -Credential $Cred
Import-PSSession -Session $CSSession
```

<span data-ttu-id="cd6a1-194">Neste exemplo, atribuímos uma política de reunião do Teams chamada Política de Reunião do Aluno a um usuário chamado Reda.</span><span class="sxs-lookup"><span data-stu-id="cd6a1-194">In this example, we assign a Teams meeting policy named Student Meeting Policy to a user named Reda.</span></span>

```powershell
Grant-CsTeamsMeetingPolicy -Identity reda@contoso.com -PolicyName "Student Meeting Policy"
```

<span data-ttu-id="cd6a1-195">Para saber mais, leia [Gerenciar políticas por meio do PowerShell.](teams-powershell-managing-teams.md#manage-policies-via-powershell)</span><span class="sxs-lookup"><span data-stu-id="cd6a1-195">To learn more, read [Manage policies via PowerShell](teams-powershell-managing-teams.md#manage-policies-via-powershell).</span></span>

## <a name="assign-a-policy-to-a-group"></a><span data-ttu-id="cd6a1-196">Atribuir uma política a um grupo</span><span class="sxs-lookup"><span data-stu-id="cd6a1-196">Assign a policy to a group</span></span>

<span data-ttu-id="cd6a1-197">A atribuição de política a grupos permite atribuir uma política a um grupo de usuários, como um grupo de segurança ou uma lista de distribuição.</span><span class="sxs-lookup"><span data-stu-id="cd6a1-197">Policy assignment to groups lets you assign a policy to a group of users, such as a security group or distribution list.</span></span> <span data-ttu-id="cd6a1-198">As atribuições de política serão propagadas para os membros do grupo, de acordo com as regras de precedência.</span><span class="sxs-lookup"><span data-stu-id="cd6a1-198">The policy assignment is propagated to members of the group according to precedence rules.</span></span> <span data-ttu-id="cd6a1-199">À medida que os membros forem adicionados ou removidos de um grupo, as atribuições de política herdadas serão atualizadas.</span><span class="sxs-lookup"><span data-stu-id="cd6a1-199">As members are added to or removed from a group, their inherited policy assignments are updated accordingly.</span></span>

<span data-ttu-id="cd6a1-200">A atribuição de política a grupos é recomendada para grupos de até 50.000 usuários, mas também funcionará com grupos maiores.</span><span class="sxs-lookup"><span data-stu-id="cd6a1-200">Policy assignment to groups is recommended for groups of up to 50,000 users but it will also work with larger groups.</span></span>

<span data-ttu-id="cd6a1-201">Quando você atribui a política, ela é atribuída imediatamente ao grupo.</span><span class="sxs-lookup"><span data-stu-id="cd6a1-201">When you assign the policy, it's immediately assigned to the group.</span></span> <span data-ttu-id="cd6a1-202">No entanto, observe que a propagação da atribuição de política aos membros do grupo é executada como uma operação em segundo plano e pode levar algum tempo, dependendo do tamanho do grupo.</span><span class="sxs-lookup"><span data-stu-id="cd6a1-202">However, note that the propagation of the policy assignment to members of the group is performed as a background operation and may take some time, depending on the size of the group.</span></span> <span data-ttu-id="cd6a1-203">O mesmo é verdadeiro quando uma política é não atribuída de um grupo ou quando membros são adicionados ou removidos de um grupo.</span><span class="sxs-lookup"><span data-stu-id="cd6a1-203">The same is true when a policy is unassigned from a group, or when members are added to or removed from a group.</span></span>

<span data-ttu-id="cd6a1-204">As atribuições de política de grupo são propagadas apenas para usuários que são membros diretos do grupo.</span><span class="sxs-lookup"><span data-stu-id="cd6a1-204">Group policy assignments are only propagated to users that are direct members of the group.</span></span> <span data-ttu-id="cd6a1-205">As atribuições não são propagadas para membros de grupos aninhados.</span><span class="sxs-lookup"><span data-stu-id="cd6a1-205">The assignments aren't propagated to members of nested groups.</span></span>

### <a name="what-you-need-to-know-about-policy-assignment-to-groups"></a><span data-ttu-id="cd6a1-206">O que você precisa saber sobre a atribuição de política a grupos</span><span class="sxs-lookup"><span data-stu-id="cd6a1-206">What you need to know about policy assignment to groups</span></span>

<span data-ttu-id="cd6a1-207">Antes de começar, é importante entender as regras de precedência e a classificação de atribuição de grupo.</span><span class="sxs-lookup"><span data-stu-id="cd6a1-207">Before you get started, it's important to understand precedence rules and group assignment ranking.</span></span>

#### <a name="precedence-rules"></a><span data-ttu-id="cd6a1-208">Regras de precedência</span><span class="sxs-lookup"><span data-stu-id="cd6a1-208">Precedence rules</span></span>

<span data-ttu-id="cd6a1-209">Para um determinado tipo de política, a política efetiva de um usuário é determinada de acordo com o seguinte:</span><span class="sxs-lookup"><span data-stu-id="cd6a1-209">For a given policy type, a user's effective policy is determined according to the following:</span></span>

- <span data-ttu-id="cd6a1-210">Uma política atribuída diretamente a um usuário tem precedência sobre qualquer outra política do mesmo tipo atribuída a um grupo.</span><span class="sxs-lookup"><span data-stu-id="cd6a1-210">A policy that's directly assigned to a user takes precedence over any other policy of the same type that's assigned to a group.</span></span> <span data-ttu-id="cd6a1-211">Em outras palavras, se um usuário receber diretamente uma política de um determinado tipo, esse usuário não herdará uma política do mesmo tipo de um grupo.</span><span class="sxs-lookup"><span data-stu-id="cd6a1-211">In other words, if a user is directly assigned a policy of a given type, that user won't inherit a policy of the same type from a group.</span></span> <span data-ttu-id="cd6a1-212">Isso também significa que, se um usuário tiver uma política de um determinado tipo que tenha sido atribuída diretamente a ele, você terá que remover essa política do usuário antes que ele possa herdar uma política do mesmo tipo de um grupo.</span><span class="sxs-lookup"><span data-stu-id="cd6a1-212">This also means that if a user has a policy of a given type that was directly assigned to them, you have to remove that policy from the user before they can inherit a policy of the same type from a group.</span></span>
- <span data-ttu-id="cd6a1-213">Se um usuário não tiver uma política atribuída diretamente a ele e for membro de dois ou mais grupos e cada grupo tiver uma política do mesmo tipo atribuído a ele, o usuário herdará a política da atribuição de grupo que tem a classificação mais alta.</span><span class="sxs-lookup"><span data-stu-id="cd6a1-213">If a user doesn't have a policy directly assigned to them and is a member of two or more groups and each group has a policy of the same type assigned to it, the user inherits the policy of the group assignment that has the highest ranking.</span></span>
- <span data-ttu-id="cd6a1-214">Se um usuário não for membro de nenhum grupo atribuído a uma política, a política global (padrão em toda a organização) desse tipo de política se aplicará ao usuário.</span><span class="sxs-lookup"><span data-stu-id="cd6a1-214">If a user isn't a member of any groups that are assigned a policy, the global (Org-wide default) policy for that policy type applies to the user.</span></span>

<span data-ttu-id="cd6a1-215">A política efetiva de um usuário é atualizada de acordo com essas regras quando um usuário é adicionado ou removido de um grupo que recebe uma política, uma política é não atribuída a um grupo ou uma política atribuída diretamente ao usuário é removida.</span><span class="sxs-lookup"><span data-stu-id="cd6a1-215">A user's effective policy is updated according to these rules when a user is added to or removed from a group that's assigned a policy, a policy is unassigned from a group, or a policy that's directly assigned to the user is removed.</span></span>

#### <a name="group-assignment-ranking"></a><span data-ttu-id="cd6a1-216">Classificação de atribuição de grupo</span><span class="sxs-lookup"><span data-stu-id="cd6a1-216">Group assignment ranking</span></span>
 
<span data-ttu-id="cd6a1-217">Ao atribuir uma política a um grupo, você especifica uma classificação para a atribuição de grupo.</span><span class="sxs-lookup"><span data-stu-id="cd6a1-217">When you assign a policy to a group, you specify a ranking for the group assignment.</span></span> <span data-ttu-id="cd6a1-218">Isso é usado para determinar qual política um usuário deve herdar como sua política efetiva se o usuário for membro de dois ou mais grupos e cada grupo receber uma política do mesmo tipo.</span><span class="sxs-lookup"><span data-stu-id="cd6a1-218">This is used to determine which policy a user should inherit as their effective policy if the user is a member of two or more groups and each group is assigned a policy of the same type.</span></span>

<span data-ttu-id="cd6a1-219">A classificação de atribuição de grupo é relativa a outras atribuições de grupo do mesmo tipo.</span><span class="sxs-lookup"><span data-stu-id="cd6a1-219">The group assignment ranking is relative to other group assignments of the same type.</span></span> <span data-ttu-id="cd6a1-220">Por exemplo, se você estiver atribuindo uma política de chamada a dois grupos, de definir a classificação de uma atribuição como 1 e a outra como 2, sendo 1 a classificação mais alta.</span><span class="sxs-lookup"><span data-stu-id="cd6a1-220">For example, if you're assigning a calling policy to two groups, set the ranking of one assignment to 1 and the other to 2, with 1 being the highest ranking.</span></span> <span data-ttu-id="cd6a1-221">A classificação de atribuição de grupo indica qual associação de grupo é mais importante ou mais relevante do que outras associações de grupo em relação à herança.</span><span class="sxs-lookup"><span data-stu-id="cd6a1-221">The group assignment ranking indicates which group membership is more important or more relevant than other group memberships with regards to inheritance.</span></span>
 
<span data-ttu-id="cd6a1-222">Por exemplo, você tem dois grupos, Funcionários da Loja e Gerentes da Loja.</span><span class="sxs-lookup"><span data-stu-id="cd6a1-222">Say, for example, you have two groups, Store Employees and Store Managers.</span></span> <span data-ttu-id="cd6a1-223">Ambos os grupos são atribuídos a uma política de chamada do Teams, a Política de Chamada de Funcionários da Loja e a Política de Chamada de Gerentes de Loja, respectivamente.</span><span class="sxs-lookup"><span data-stu-id="cd6a1-223">Both groups are assigned a Teams calling policy, Store Employees Calling Policy and Store Managers Calling Policy, respectively.</span></span> <span data-ttu-id="cd6a1-224">Para um gerente de loja que está em ambos os grupos, sua função como gerente é mais relevante do que sua função como funcionário, portanto, a política de chamada atribuída ao grupo Gerentes de Loja deve ter uma classificação mais alta.</span><span class="sxs-lookup"><span data-stu-id="cd6a1-224">For a store manager who is in both groups, their role as a manager is more relevant than their role as an employee, so the calling policy that's assigned to the Store Managers group should have a higher ranking.</span></span>

|<span data-ttu-id="cd6a1-225">Grupo</span><span class="sxs-lookup"><span data-stu-id="cd6a1-225">Group</span></span> |<span data-ttu-id="cd6a1-226">Nome da política de chamada do Teams</span><span class="sxs-lookup"><span data-stu-id="cd6a1-226">Teams calling policy name</span></span>  |<span data-ttu-id="cd6a1-227">Classificação</span><span class="sxs-lookup"><span data-stu-id="cd6a1-227">Rank</span></span>|
|---------|---------|---|
|<span data-ttu-id="cd6a1-228">Gerentes da Loja</span><span class="sxs-lookup"><span data-stu-id="cd6a1-228">Store Managers</span></span>   |<span data-ttu-id="cd6a1-229">Política de Chamada de Gerentes de Loja</span><span class="sxs-lookup"><span data-stu-id="cd6a1-229">Store Managers Calling Policy</span></span>         |<span data-ttu-id="cd6a1-230">1</span><span class="sxs-lookup"><span data-stu-id="cd6a1-230">1</span></span>|
|<span data-ttu-id="cd6a1-231">Armazenar funcionários</span><span class="sxs-lookup"><span data-stu-id="cd6a1-231">Store Employees</span></span>    |<span data-ttu-id="cd6a1-232">Armazenar Política de Chamada de Funcionários</span><span class="sxs-lookup"><span data-stu-id="cd6a1-232">Store Employees Calling Policy</span></span>      |<span data-ttu-id="cd6a1-233">2</span><span class="sxs-lookup"><span data-stu-id="cd6a1-233">2</span></span>|

<span data-ttu-id="cd6a1-234">Se você não especificar uma classificação, a atribuição de política recebe a classificação mais baixa.</span><span class="sxs-lookup"><span data-stu-id="cd6a1-234">If you don't specify a ranking, the policy assignment is given the lowest ranking.</span></span> 

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="cd6a1-235">Usando o centro de administração do Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="cd6a1-235">Using the Microsoft Teams admin center</span></span>

> [!NOTE]
> <span data-ttu-id="cd6a1-236">Atualmente, a atribuição de política a grupos usando o centro de administração do Microsoft Teams só está disponível para a política de chamada do Teams, a política de estacionamento de chamada do Teams, a política de eventos ao vivo do Teams, a política de reunião do Teams e a política de mensagens do Teams.</span><span class="sxs-lookup"><span data-stu-id="cd6a1-236">Currently, policy assignment to groups using the Microsoft Teams admin center is only available for Teams calling policy, Teams call park policy, Teams policy, Teams live events policy, Teams meeting policy, and Teams messaging policy.</span></span> <span data-ttu-id="cd6a1-237">Para outros tipos de política, use o PowerShell.</span><span class="sxs-lookup"><span data-stu-id="cd6a1-237">For other policy types, use PowerShell.</span></span>

1. <span data-ttu-id="cd6a1-238">Na navegação à esquerda do centro de administração do Microsoft Teams, vá para a página de tipo de política.</span><span class="sxs-lookup"><span data-stu-id="cd6a1-238">In the left navigation of the Microsoft Teams admin center, go to the policy type page.</span></span> <span data-ttu-id="cd6a1-239">Por exemplo, vá para políticas **de Reunião**  >  **de Reuniões.**</span><span class="sxs-lookup"><span data-stu-id="cd6a1-239">For example, go to **Meetings** > **Meeting policies**.</span></span>
2. <span data-ttu-id="cd6a1-240">Selecione a **guia atribuição de política de** grupo.</span><span class="sxs-lookup"><span data-stu-id="cd6a1-240">Select the **Group policy assignment** tab.</span></span>
3. <span data-ttu-id="cd6a1-241">Selecione **Adicionar grupo** e, em seguida, na política Atribuir **ao** painel de grupo, faça o seguinte:</span><span class="sxs-lookup"><span data-stu-id="cd6a1-241">Select **Add group**, and then in the **Assign policy to group** pane, do the following:</span></span>
    1. <span data-ttu-id="cd6a1-242">Pesquise e adicione o grupo ao que você deseja atribuir a política.</span><span class="sxs-lookup"><span data-stu-id="cd6a1-242">Search for and add the group you want to assign the policy to.</span></span>
    2. <span data-ttu-id="cd6a1-243">Definir a classificação para a atribuição de grupo.</span><span class="sxs-lookup"><span data-stu-id="cd6a1-243">Set the ranking for the group assignment.</span></span>
    3. <span data-ttu-id="cd6a1-244">Selecione a política que você deseja atribuir.</span><span class="sxs-lookup"><span data-stu-id="cd6a1-244">Select the policy that you want to assign.</span></span> 
    4. <span data-ttu-id="cd6a1-245">Selecione **Aplicar**.</span><span class="sxs-lookup"><span data-stu-id="cd6a1-245">Select **Apply**.</span></span>

<span data-ttu-id="cd6a1-246">Para remover uma atribuição  de política de grupo, na guia atribuição de política de grupo da página de política, selecione a atribuição de grupo e selecione **Remover**.</span><span class="sxs-lookup"><span data-stu-id="cd6a1-246">To remove a group policy assignment, on the **Group policy assignment** tab of the policy page, select the group assignment, and then select **Remove**.</span></span>

<span data-ttu-id="cd6a1-247">Para alterar a classificação de uma atribuição de grupo, você precisa primeiro remover a atribuição de política de grupo.</span><span class="sxs-lookup"><span data-stu-id="cd6a1-247">To change the ranking of a group assignment, you have to first remove the group policy assignment.</span></span> <span data-ttu-id="cd6a1-248">Em seguida, siga as etapas acima para atribuir a política a um grupo.</span><span class="sxs-lookup"><span data-stu-id="cd6a1-248">Then, follow the steps above to assign the policy to a group.</span></span>

### <a name="using-powershell"></a><span data-ttu-id="cd6a1-249">Usando o Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="cd6a1-249">Using PowerShell</span></span>

> [!NOTE]
> <span data-ttu-id="cd6a1-250">Atualmente, a atribuição de política a grupos usando o PowerShell não está disponível para todos os tipos de política do Teams.</span><span class="sxs-lookup"><span data-stu-id="cd6a1-250">Currently, policy assignment to groups using PowerShell isn't available for all Teams policy types.</span></span> <span data-ttu-id="cd6a1-251">Consulte [New-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/new-csgrouppolicyassignment) para ver a lista de tipos de política com suporte.</span><span class="sxs-lookup"><span data-stu-id="cd6a1-251">See [New-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/new-csgrouppolicyassignment) for the list of supported policy types.</span></span>

#### <a name="install-and-connect-to-the-microsoft-teams-powershell-module"></a><span data-ttu-id="cd6a1-252">Instalar e conectar-se ao módulo do PowerShell do Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="cd6a1-252">Install and connect to the Microsoft Teams PowerShell module</span></span>

<span data-ttu-id="cd6a1-253">Para obter orientações passo a passo, consulte [Instalar o PowerShell do Teams.](teams-powershell-install.md)</span><span class="sxs-lookup"><span data-stu-id="cd6a1-253">For step-by-step guidance, see [Install Teams PowerShell](teams-powershell-install.md).</span></span>

#### <a name="assign-a-policy-to-a-group-of-users"></a><span data-ttu-id="cd6a1-254">Atribuir uma política a um grupo de usuários</span><span class="sxs-lookup"><span data-stu-id="cd6a1-254">Assign a policy to a group of users</span></span>

<span data-ttu-id="cd6a1-255">Use o cmdlet [New-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/new-csgrouppolicyassignment) para atribuir uma política a um grupo.</span><span class="sxs-lookup"><span data-stu-id="cd6a1-255">You use the [New-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/new-csgrouppolicyassignment) cmdlet to assign a policy to a group.</span></span> <span data-ttu-id="cd6a1-256">Você pode especificar um grupo usando a ID do objeto, o endereço SIP ou o endereço de email.</span><span class="sxs-lookup"><span data-stu-id="cd6a1-256">You can specify a group by using the object Id, SIP address, or email address.</span></span>

<span data-ttu-id="cd6a1-257">Neste exemplo, atribuímos uma política de reunião do Teams chamada Política de Reunião de Gerentes de Varejo a um grupo com uma classificação de atribuição de 1.</span><span class="sxs-lookup"><span data-stu-id="cd6a1-257">In this example, we assign a Teams meeting policy named Retail Managers Meeting Policy to a group with an assignment ranking of 1.</span></span>

```powershell
New-CsGroupPolicyAssignment -GroupId d8ebfa45-0f28-4d2d-9bcc-b158a49e2d17 -PolicyType TeamsMeetingPolicy -PolicyName "Retail Managers Meeting Policy" -Rank 1
```

#### <a name="get-policy-assignments-for-a-group"></a><span data-ttu-id="cd6a1-258">Obter atribuições de política para um grupo</span><span class="sxs-lookup"><span data-stu-id="cd6a1-258">Get policy assignments for a group</span></span>

<span data-ttu-id="cd6a1-259">Use o cmdlet [Get-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/get-csgrouppolicyassignment) para obter todas as políticas atribuídas a um grupo.</span><span class="sxs-lookup"><span data-stu-id="cd6a1-259">Use the [Get-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/get-csgrouppolicyassignment) cmdlet to get all policies assigned to a group.</span></span> <span data-ttu-id="cd6a1-260">Observe que os grupos sempre são listados por sua ID de grupo, mesmo que seu endereço SIP ou endereço de email seja usado para atribuir a política.</span><span class="sxs-lookup"><span data-stu-id="cd6a1-260">Note that groups are always listed by their group Id even if its SIP address or email address was used to assign the policy.</span></span>

<span data-ttu-id="cd6a1-261">Neste exemplo, recuperamos todas as políticas atribuídas a um grupo específico.</span><span class="sxs-lookup"><span data-stu-id="cd6a1-261">In this example, we retrieve all policies assigned to a specific group.</span></span>

```powershell
Get-CsGroupPolicyAssignment -GroupId e050ce51-54bc-45b7-b3e6-c00343d31274
```

<span data-ttu-id="cd6a1-262">Neste exemplo, retornamos todos os grupos atribuídos a uma política de reunião do Teams.</span><span class="sxs-lookup"><span data-stu-id="cd6a1-262">In this example, we return all groups that are assigned a Teams meeting policy.</span></span>

```powershell
Get-CsGroupPolicyAssignment -PolicyType TeamsMeetingPolicy
```

#### <a name="remove-a-policy-from-a-group"></a><span data-ttu-id="cd6a1-263">Remover uma política de um grupo</span><span class="sxs-lookup"><span data-stu-id="cd6a1-263">Remove a policy from a group</span></span>

<span data-ttu-id="cd6a1-264">Use o cmdlet [Remove-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/remove-csgrouppolicyassignment) para remover uma política de um grupo.</span><span class="sxs-lookup"><span data-stu-id="cd6a1-264">Use the [Remove-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/remove-csgrouppolicyassignment) cmdlet to remove a policy from a group.</span></span> <span data-ttu-id="cd6a1-265">Quando você remove uma política de um grupo, as prioridades de outras políticas do mesmo tipo atribuídas a esse grupo e que têm uma classificação inferior são atualizadas.</span><span class="sxs-lookup"><span data-stu-id="cd6a1-265">When you remove a policy from a group, the priorities of other policies of the same type assigned to that group and that have a lower ranking are updated.</span></span> <span data-ttu-id="cd6a1-266">Por exemplo, se você remover uma política que tenha uma classificação de 2, as políticas com classificação 3 e 4 serão atualizadas para refletir sua nova classificação.</span><span class="sxs-lookup"><span data-stu-id="cd6a1-266">For example, if you remove a policy that has a ranking of 2, policies that have a ranking of 3 and 4 are updated to reflect their new ranking.</span></span> <span data-ttu-id="cd6a1-267">As duas tabelas a seguir mostram este exemplo.</span><span class="sxs-lookup"><span data-stu-id="cd6a1-267">The following two tables show this example.</span></span>

<span data-ttu-id="cd6a1-268">Aqui está uma lista de atribuições de política e prioridades para uma política de reunião do Teams.</span><span class="sxs-lookup"><span data-stu-id="cd6a1-268">Here's a list of the policy assignments and priorities for a Teams meeting policy.</span></span>

|<span data-ttu-id="cd6a1-269">Nome do grupo</span><span class="sxs-lookup"><span data-stu-id="cd6a1-269">Group name</span></span>  |<span data-ttu-id="cd6a1-270">Nome da política</span><span class="sxs-lookup"><span data-stu-id="cd6a1-270">Policy name</span></span>  |<span data-ttu-id="cd6a1-271">Classificação</span><span class="sxs-lookup"><span data-stu-id="cd6a1-271">Rank</span></span>|
|---------|---------|---------|
|<span data-ttu-id="cd6a1-272">Vendas</span><span class="sxs-lookup"><span data-stu-id="cd6a1-272">Sales</span></span>    |<span data-ttu-id="cd6a1-273">Política de vendas</span><span class="sxs-lookup"><span data-stu-id="cd6a1-273">Sales policy</span></span>       | <span data-ttu-id="cd6a1-274">1</span><span class="sxs-lookup"><span data-stu-id="cd6a1-274">1</span></span>        |
|<span data-ttu-id="cd6a1-275">Região Oeste</span><span class="sxs-lookup"><span data-stu-id="cd6a1-275">West Region</span></span>     |<span data-ttu-id="cd6a1-276">Política da Região Oeste</span><span class="sxs-lookup"><span data-stu-id="cd6a1-276">West Region policy</span></span>         |<span data-ttu-id="cd6a1-277">2</span><span class="sxs-lookup"><span data-stu-id="cd6a1-277">2</span></span>         |
|<span data-ttu-id="cd6a1-278">Divisão</span><span class="sxs-lookup"><span data-stu-id="cd6a1-278">Division</span></span>    |<span data-ttu-id="cd6a1-279">Política de divisão</span><span class="sxs-lookup"><span data-stu-id="cd6a1-279">Division policy</span></span>         |<span data-ttu-id="cd6a1-280">3</span><span class="sxs-lookup"><span data-stu-id="cd6a1-280">3</span></span>         |
|<span data-ttu-id="cd6a1-281">Subsidiária</span><span class="sxs-lookup"><span data-stu-id="cd6a1-281">Subsidiary</span></span>   |<span data-ttu-id="cd6a1-282">Política de subsidiária</span><span class="sxs-lookup"><span data-stu-id="cd6a1-282">Subsidiary policy</span></span>        |<span data-ttu-id="cd6a1-283">4</span><span class="sxs-lookup"><span data-stu-id="cd6a1-283">4</span></span>         |

<span data-ttu-id="cd6a1-284">Se removermos a política da Região Oeste do grupo Região Oeste, as atribuições e prioridades da política serão atualizadas da seguinte forma.</span><span class="sxs-lookup"><span data-stu-id="cd6a1-284">If we remove the West Region policy from the West Region group, the policy assignments and priorities are updated as follows.</span></span>

|<span data-ttu-id="cd6a1-285">Nome do grupo</span><span class="sxs-lookup"><span data-stu-id="cd6a1-285">Group name</span></span>  |<span data-ttu-id="cd6a1-286">Nome da política</span><span class="sxs-lookup"><span data-stu-id="cd6a1-286">Policy name</span></span>  |<span data-ttu-id="cd6a1-287">Classificação</span><span class="sxs-lookup"><span data-stu-id="cd6a1-287">Rank</span></span>|
|---------|---------|---------|
|<span data-ttu-id="cd6a1-288">Vendas</span><span class="sxs-lookup"><span data-stu-id="cd6a1-288">Sales</span></span>    |<span data-ttu-id="cd6a1-289">Política de vendas</span><span class="sxs-lookup"><span data-stu-id="cd6a1-289">Sales policy</span></span>       | <span data-ttu-id="cd6a1-290">1</span><span class="sxs-lookup"><span data-stu-id="cd6a1-290">1</span></span>        |
|<span data-ttu-id="cd6a1-291">Divisão</span><span class="sxs-lookup"><span data-stu-id="cd6a1-291">Division</span></span>    |<span data-ttu-id="cd6a1-292">Política de divisão</span><span class="sxs-lookup"><span data-stu-id="cd6a1-292">Division policy</span></span>         |<span data-ttu-id="cd6a1-293">2</span><span class="sxs-lookup"><span data-stu-id="cd6a1-293">2</span></span>         |
|<span data-ttu-id="cd6a1-294">Subsidiária</span><span class="sxs-lookup"><span data-stu-id="cd6a1-294">Subsidiary</span></span>   |<span data-ttu-id="cd6a1-295">Política de subsidiária</span><span class="sxs-lookup"><span data-stu-id="cd6a1-295">Subsidiary policy</span></span>        |<span data-ttu-id="cd6a1-296">3</span><span class="sxs-lookup"><span data-stu-id="cd6a1-296">3</span></span>        |

<span data-ttu-id="cd6a1-297">Neste exemplo, removemos a política de reunião do Teams de um grupo.</span><span class="sxs-lookup"><span data-stu-id="cd6a1-297">In this example, we remove the Teams meeting policy from a group.</span></span>

```powershell
Remove-CsGroupPolicyAssignment -PolicyType TeamsMeetingPolicy -GroupId f985e013-0826-40bb-8c94-e5f367076044
```

#### <a name="change-a-policy-assignment-for-a-group"></a><span data-ttu-id="cd6a1-298">Alterar uma atribuição de política para um grupo</span><span class="sxs-lookup"><span data-stu-id="cd6a1-298">Change a policy assignment for a group</span></span>

> [!NOTE]
> <span data-ttu-id="cd6a1-299">O cmdlet [Set-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/set-csgrouppolicyassignment) estará disponível em breve.</span><span class="sxs-lookup"><span data-stu-id="cd6a1-299">The [Set-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/set-csgrouppolicyassignment) cmdlet will be available soon.</span></span> <span data-ttu-id="cd6a1-300">Enquanto isso, para alterar uma atribuição de política de grupo, você pode remover a atribuição de política atual do grupo e adicionar uma nova atribuição de política.</span><span class="sxs-lookup"><span data-stu-id="cd6a1-300">In the meantime, to change a group policy assignment, you can remove the current policy assignment from the group, and then add a new policy assignment.</span></span>

<span data-ttu-id="cd6a1-301">Depois de atribuir uma política a um grupo, você pode usar o cmdlet [Set-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/set-csgrouppolicyassignment) para alterar a atribuição de política desse grupo da seguinte forma:</span><span class="sxs-lookup"><span data-stu-id="cd6a1-301">After you assign a policy to a group, you can use the [Set-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/set-csgrouppolicyassignment) cmdlet to change that group's policy assignment as follows:</span></span>

- <span data-ttu-id="cd6a1-302">Alterar a classificação</span><span class="sxs-lookup"><span data-stu-id="cd6a1-302">Change the ranking</span></span>
- <span data-ttu-id="cd6a1-303">Alterar a política de um determinado tipo de política</span><span class="sxs-lookup"><span data-stu-id="cd6a1-303">Change the policy of a given policy type</span></span>
- <span data-ttu-id="cd6a1-304">Alterar a política de um determinado tipo de política e a classificação</span><span class="sxs-lookup"><span data-stu-id="cd6a1-304">Change the policy of a given policy type and the ranking</span></span>

<span data-ttu-id="cd6a1-305">Neste exemplo, alteramos a política de estacionamento de chamada do Teams de um grupo para uma política chamada SupportCallPark e a classificação de atribuição para 3.</span><span class="sxs-lookup"><span data-stu-id="cd6a1-305">In this example, we change a group's Teams call park policy to a policy named SupportCallPark and the assignment ranking to 3.</span></span>

```powershell
Set-CsGroupPolicyAssignment -GroupId 566b8d39-5c5c-4aaa-bc07-4f36278a1b38 -PolicyType TeamsMeetingPolicy -PolicyName SupportCallPark -Rank 3
```

#### <a name="change-the-effective-policy-for-a-user"></a><span data-ttu-id="cd6a1-306">Alterar a política efetiva para um usuário</span><span class="sxs-lookup"><span data-stu-id="cd6a1-306">Change the effective policy for a user</span></span>

<span data-ttu-id="cd6a1-307">Veja um exemplo de como alterar a política efetiva para um usuário que recebe uma política diretamente atribuída.</span><span class="sxs-lookup"><span data-stu-id="cd6a1-307">Here's an example of how to change the effective policy for a user who is directly assigned a policy.</span></span>

<span data-ttu-id="cd6a1-308">Primeiro, usamos o cmdlet [Get-CsUserPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/get-csuserpolicyassignment) juntamente com o parâmetro para obter detalhes das políticas de transmissão de reunião do Teams associadas ```PolicySource``` ao usuário.</span><span class="sxs-lookup"><span data-stu-id="cd6a1-308">First, we use the [Get-CsUserPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/get-csuserpolicyassignment) cmdlet together with the ```PolicySource``` parameter to get details of the Teams meeting broadcast policies associated with the user.</span></span> 

```powershell
Get-CsUserPolicyAssignment -Identity daniel@contoso.com -PolicyType TeamsMeetingBroadcastPolicy | select -ExpandProperty PolicySource
```

<span data-ttu-id="cd6a1-309">A saída mostra que o usuário foi atribuído diretamente a uma política de transmissão de reunião do Teams chamada Eventos de Funcionários, que tem precedência sobre a política chamada Vendor Live Events atribuída a um grupo ao qual o usuário pertence.</span><span class="sxs-lookup"><span data-stu-id="cd6a1-309">The output shows that the user was directly assigned a Teams meeting broadcast policy named Employee Events, which takes precedence over the policy named Vendor Live Events that's assigned to a group the user belongs to.</span></span>

```console
AssignmentType PolicyName         Reference
-------------- ----------         ---------
Direct         Employee Events
Group          Vendor Live Events 566b8d39-5c5c-4aaa-bc07-4f36278a1b38
```

<span data-ttu-id="cd6a1-310">Agora, removemos a política eventos de funcionário do usuário.</span><span class="sxs-lookup"><span data-stu-id="cd6a1-310">Now, we remove the Employee Events policy from the user.</span></span> <span data-ttu-id="cd6a1-311">Isso significa que o usuário não tem mais uma política de transmissão de reunião do Teams atribuída diretamente a ele e herdará a política de Eventos ao Vivo do Fornecedor atribuída ao grupo ao que o usuário pertence.</span><span class="sxs-lookup"><span data-stu-id="cd6a1-311">This means that the user no longer has a Teams meeting broadcast policy directly assigned to them and will inherit the Vendor Live Events policy that's assigned to the group the user belongs to.</span></span> 

<span data-ttu-id="cd6a1-312">Use o seguinte cmdlet no módulo PowerShell do Skype for Business para fazer isso.</span><span class="sxs-lookup"><span data-stu-id="cd6a1-312">Use the following cmdlet in the Skype for Business PowerShell module to do this.</span></span>

```powershell
Grant-CsTeamsMeetingBroadcastPolicy -Identity daniel@contoso.com -PolicyName $null
```

<span data-ttu-id="cd6a1-313">Você pode usar o seguinte cmdlet no módulo do PowerShell do Teams para fazer isso em escala, embora uma atribuição de política em lotes, onde $users é uma lista de usuários que você especificar.</span><span class="sxs-lookup"><span data-stu-id="cd6a1-313">You can use following cmdlet in the Teams PowerShell module to do this at scale though a batch policy assignment, where $users is a list of users that you specify.</span></span>

```powershell
New-CsBatchPolicyAssignmentOperation -OperationName "Assigning null at bulk" -PolicyType TeamsMeetingBroadcastPolicy -PolicyName $null -Identity $users  
```

## <a name="assign-a-policy-to-a-batch-of-users"></a><span data-ttu-id="cd6a1-314">Atribuir uma política a um lote de usuários</span><span class="sxs-lookup"><span data-stu-id="cd6a1-314">Assign a policy to a batch of users</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="cd6a1-315">Usando o centro de administração do Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="cd6a1-315">Using the Microsoft Teams admin center</span></span>

<span data-ttu-id="cd6a1-316">Para atribuir uma política aos usuários em massa:</span><span class="sxs-lookup"><span data-stu-id="cd6a1-316">To assign a policy to users in bulk:</span></span>

1. <span data-ttu-id="cd6a1-317">Na navegação à esquerda do centro de administração do Microsoft Teams, selecione **Usuários**.</span><span class="sxs-lookup"><span data-stu-id="cd6a1-317">In the left navigation of the Microsoft Teams admin center, select **Users**.</span></span>
2. <span data-ttu-id="cd6a1-318">Pesquise os usuários aos quem você deseja atribuir a política ou filtre a exibição para mostrar os usuários que você deseja.</span><span class="sxs-lookup"><span data-stu-id="cd6a1-318">Search for the users you want to assign the policy to or filter the view to show the users you want.</span></span>
3. <span data-ttu-id="cd6a1-319">Na coluna **&#x2713;** (marca de seleção), selecione os usuários.</span><span class="sxs-lookup"><span data-stu-id="cd6a1-319">In the **&#x2713;** (check mark) column, select the users.</span></span> <span data-ttu-id="cd6a1-320">Para selecionar todos os usuários, clique na (marca de seleção) &#x2713; na parte superior da tabela.</span><span class="sxs-lookup"><span data-stu-id="cd6a1-320">To select all users, click the &#x2713; (check mark) at the top of the table.</span></span>
4. <span data-ttu-id="cd6a1-321">Clique em **Editar configurações**, faça as alterações desejadas e, em seguida, clique em **Aplicar**.</span><span class="sxs-lookup"><span data-stu-id="cd6a1-321">Click **Edit settings**, make the changes that you want, and then click **Apply**.</span></span>

<span data-ttu-id="cd6a1-322">Para exibir o status da atribuição de política, na  faixa exibida  na parte superior da página Usuários depois de clicar em Aplicar para enviar a atribuição de política, clique em **Log de atividades.**</span><span class="sxs-lookup"><span data-stu-id="cd6a1-322">To view the status of your policy assignment, in the banner that appears at the top of the **Users** page after you click **Apply** to submit your policy assignment, click **Activity log**.</span></span> <span data-ttu-id="cd6a1-323">Ou, na navegação à esquerda do centro de administração do Microsoft Teams, vá para o Painel **e,** em log de **atividades,** clique em **Exibir detalhes.**</span><span class="sxs-lookup"><span data-stu-id="cd6a1-323">Or, in the left navigation of the Microsoft Teams admin center, go to **Dashboard**, and then under **Activity log**, click **View details**.</span></span> <span data-ttu-id="cd6a1-324">O log de atividades mostra atribuições de política para lotes de mais de 20 usuários por meio do centro de administração do Microsoft Teams dos últimos 30 dias.</span><span class="sxs-lookup"><span data-stu-id="cd6a1-324">The Activity log shows policy assignments to batches of more than 20 users through the Microsoft Teams admin center from the last 30 days.</span></span> <span data-ttu-id="cd6a1-325">Para saber mais, consulte [Exibir suas atribuições de política no log de atividades.](activity-log.md)</span><span class="sxs-lookup"><span data-stu-id="cd6a1-325">To learn more, see [View your policy assignments in the Activity log](activity-log.md).</span></span>

### <a name="using-powershell"></a><span data-ttu-id="cd6a1-326">Usando o Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="cd6a1-326">Using PowerShell</span></span>

> [!NOTE]
> <span data-ttu-id="cd6a1-327">Atualmente, a atribuição de política em lote usando o PowerShell não está disponível para todos os tipos de política do Teams.</span><span class="sxs-lookup"><span data-stu-id="cd6a1-327">Currently, batch policy assignment using PowerShell isn't available for all Teams policy types.</span></span> <span data-ttu-id="cd6a1-328">Consulte [New-CsBatchPolicyAssignmentOperation para](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation) ver a lista de tipos de política com suporte.</span><span class="sxs-lookup"><span data-stu-id="cd6a1-328">See [New-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation) for the list of supported policy types.</span></span>
 
<span data-ttu-id="cd6a1-329">Com a atribuição de política em lote, você pode atribuir uma política a grandes conjuntos de usuários por vez sem precisar usar um script.</span><span class="sxs-lookup"><span data-stu-id="cd6a1-329">With batch policy assignment, you can assign a policy to large sets of users at a time without having to use a script.</span></span> <span data-ttu-id="cd6a1-330">Use o cmdlet [New-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation) para enviar um lote de usuários e a política que você deseja atribuir.</span><span class="sxs-lookup"><span data-stu-id="cd6a1-330">You use the [New-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation) cmdlet to submit a batch of users and the policy that you want to assign.</span></span> <span data-ttu-id="cd6a1-331">As atribuições são processadas como uma operação de plano de fundo e uma ID de operação é gerada para cada lote.</span><span class="sxs-lookup"><span data-stu-id="cd6a1-331">The assignments are processed as a background operation and an operation ID is generated for each batch.</span></span> <span data-ttu-id="cd6a1-332">Em seguida, você pode usar o cmdlet [Get-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/get-csbatchpolicyassignmentoperation) para controlar o progresso e o status das atribuições em um lote.</span><span class="sxs-lookup"><span data-stu-id="cd6a1-332">You can then use the [Get-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/get-csbatchpolicyassignmentoperation) cmdlet to track the progress and status of the assignments in a batch.</span></span>

<span data-ttu-id="cd6a1-333">Você pode especificar usuários por sua ID de objeto ou endereço SIP ( Session Initiation Protocol).</span><span class="sxs-lookup"><span data-stu-id="cd6a1-333">You can specify users by their object Id or Session Initiation Protocol (SIP) address.</span></span> <span data-ttu-id="cd6a1-334">Observe que o endereço SIP de um usuário geralmente tem o mesmo valor que o UPN (Nome Principal do Usuário) ou endereço de email, mas isso não é necessário.</span><span class="sxs-lookup"><span data-stu-id="cd6a1-334">Note that a user's SIP address often has the same value as the User Principal Name (UPN) or email address, but this is not required.</span></span> <span data-ttu-id="cd6a1-335">Se um usuário for especificado usando seu UPN ou email, mas tiver um valor diferente do endereço SIP, a atribuição de política falhará para o usuário.</span><span class="sxs-lookup"><span data-stu-id="cd6a1-335">If a user is specified using their UPN or email, but it has a different value than their SIP address, then policy assignment will fail for the user.</span></span> <span data-ttu-id="cd6a1-336">Se um lote incluir usuários duplicados, as duplicatas serão removidas do lote antes do processamento e o status só será fornecido para os usuários exclusivos restantes no lote.</span><span class="sxs-lookup"><span data-stu-id="cd6a1-336">If a batch includes duplicate users, the duplicates will be removed from the batch before processing and status will only be provided for the unique users remaining in the batch.</span></span> 

<span data-ttu-id="cd6a1-337">Um lote pode conter até 5.000 usuários.</span><span class="sxs-lookup"><span data-stu-id="cd6a1-337">A batch can contain up to 5,000 users.</span></span> <span data-ttu-id="cd6a1-338">Para obter melhores resultados, não envie mais do que alguns lotes por vez.</span><span class="sxs-lookup"><span data-stu-id="cd6a1-338">For best results, do not submit more than a few batches at a time.</span></span> <span data-ttu-id="cd6a1-339">Permitir que lotes concluam o processamento antes de enviar mais lotes.</span><span class="sxs-lookup"><span data-stu-id="cd6a1-339">Allow batches to complete processing before submitting more batches.</span></span>

#### <a name="install-and-connect-to-the-microsoft-teams-powershell-module"></a><span data-ttu-id="cd6a1-340">Instalar e conectar-se ao módulo do PowerShell do Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="cd6a1-340">Install and connect to the Microsoft Teams PowerShell module</span></span>

<span data-ttu-id="cd6a1-341">Execute o seguinte para instalar o módulo [do PowerShell do Microsoft Teams.](https://www.powershellgallery.com/packages/MicrosoftTeams)</span><span class="sxs-lookup"><span data-stu-id="cd6a1-341">Run the following to install the [Microsoft Teams PowerShell module](https://www.powershellgallery.com/packages/MicrosoftTeams).</span></span> <span data-ttu-id="cd6a1-342">Certifique-se de instalar a versão 1.0.5 ou posterior.</span><span class="sxs-lookup"><span data-stu-id="cd6a1-342">Make sure you install version 1.0.5 or later.</span></span>

```powershell
Install-Module -Name MicrosoftTeams
```

<span data-ttu-id="cd6a1-343">Execute o seguinte para se conectar ao Teams e iniciar uma sessão.</span><span class="sxs-lookup"><span data-stu-id="cd6a1-343">Run the following to connect to Teams and start a session.</span></span>

```powershell
Connect-MicrosoftTeams
```

<span data-ttu-id="cd6a1-344">Quando for solicitado, entre usando suas credenciais de administrador.</span><span class="sxs-lookup"><span data-stu-id="cd6a1-344">When you're prompted, sign in using your admin credentials.</span></span>

#### <a name="install-and-connect-to-the-azure-ad-powershell-for-graph-module-optional"></a><span data-ttu-id="cd6a1-345">Instalar e conectar-se ao Azure AD PowerShell para módulo do Graph (opcional)</span><span class="sxs-lookup"><span data-stu-id="cd6a1-345">Install and connect to the Azure AD PowerShell for Graph module (optional)</span></span>

<span data-ttu-id="cd6a1-346">Talvez você também queira baixar e instalar o módulo [do Azure AD PowerShell](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2) para Graph (caso ainda não tenha feito isso) e se conectar ao Azure AD para poder recuperar uma lista de usuários em sua organização.</span><span class="sxs-lookup"><span data-stu-id="cd6a1-346">You may also want to [download and install the Azure AD PowerShell for Graph module](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2) (if you haven't already) and connect to Azure AD so that you can retrieve a list of users in your organization.</span></span>

<span data-ttu-id="cd6a1-347">Execute o seguinte para se conectar ao Azure AD.</span><span class="sxs-lookup"><span data-stu-id="cd6a1-347">Run the following to connect to Azure AD.</span></span>

```powershell
Connect-AzureAD
```

<span data-ttu-id="cd6a1-348">Quando for solicitado, entre usando as mesmas credenciais de administrador usadas para se conectar ao Teams.</span><span class="sxs-lookup"><span data-stu-id="cd6a1-348">When you're prompted, sign in using the same admin credentials that you used to connect to Teams.</span></span>

#### <a name="assign-a-policy-to-a-batch-of-users"></a><span data-ttu-id="cd6a1-349">Atribuir uma política a um lote de usuários</span><span class="sxs-lookup"><span data-stu-id="cd6a1-349">Assign a policy to a batch of users</span></span>

<span data-ttu-id="cd6a1-350">Neste exemplo, usamos o cmdlet [New-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation) para atribuir uma política de configuração de aplicativo chamada Política de Configuração de Aplicativo de RH a um lote de usuários listados no arquivo Users_ids.text.</span><span class="sxs-lookup"><span data-stu-id="cd6a1-350">In this example, we use the [New-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation) cmdlet to assign an app setup policy named HR App Setup Policy to a batch of users listed in the Users_ids.text file.</span></span>

```powershell
$user_ids = Get-Content .\users_ids.txt
New-CsBatchPolicyAssignmentOperation -PolicyType TeamsAppSetupPolicy -PolicyName "HR App Setup Policy" -Identity $users_ids -OperationName "Example 1 batch"
```

<span data-ttu-id="cd6a1-351">Neste exemplo, conectamos-nos ao Azure AD para recuperar uma coleção de usuários e atribuir uma política de mensagens chamada Nova Política de Mensagens de Contratação a um lote de usuários especificado usando seu endereço SIP.</span><span class="sxs-lookup"><span data-stu-id="cd6a1-351">In this example, we connect to Azure AD to retrieve a collection of users and then assign a messaging policy named New Hire Messaging Policy to a batch of users specified by using their SIP address.</span></span>

```powershell
Connect-AzureAD
$users = Get-AzureADUser
New-CsBatchPolicyAssignmentOperation -PolicyType TeamsMessagingPolicy -PolicyName "New Hire Messaging Policy" -Identity $users.SipProxyAddress -OperationName "Example 2 batch"
```

#### <a name="get-the-status-of-a-batch-assignment"></a><span data-ttu-id="cd6a1-352">Obter o status de uma atribuição em lote</span><span class="sxs-lookup"><span data-stu-id="cd6a1-352">Get the status of a batch assignment</span></span>

<span data-ttu-id="cd6a1-353">Execute o seguinte para obter o status de uma atribuição em lotes, onde OperationId é a ID da operação retornada pelo ```New-CsBatchPolicyAssignmentOperation``` cmdlet para um determinado lote.</span><span class="sxs-lookup"><span data-stu-id="cd6a1-353">Run the following to get the status of a batch assignment, where OperationId is the operation ID that's returned by the ```New-CsBatchPolicyAssignmentOperation``` cmdlet for a given batch.</span></span>

```powershell
$Get-CsBatchPolicyAssignmentOperation -OperationId f985e013-0826-40bb-8c94-e5f367076044 | fl
```

<span data-ttu-id="cd6a1-354">Se a saída mostrar que ocorreu um erro, execute o seguinte para obter mais informações sobre erros, que estão na ```UserState``` propriedade.</span><span class="sxs-lookup"><span data-stu-id="cd6a1-354">If the output shows that an error occurred, run the following to get more information about errors, which are in the ```UserState``` property.</span></span>

```powershell
Get-CsBatchPolicyAssignmentOperation -OperationId f985e013-0826-40bb-8c94-e5f367076044 | Select -ExpandProperty UserState
```

<span data-ttu-id="cd6a1-355">Para saber mais, consulte [Get-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/get-csbatchpolicyassignmentoperation).</span><span class="sxs-lookup"><span data-stu-id="cd6a1-355">To learn more, see [Get-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/get-csbatchpolicyassignmentoperation).</span></span>

## <a name="assign-a-policy-package-to-users"></a><span data-ttu-id="cd6a1-356">Atribuir um pacote de política aos usuários</span><span class="sxs-lookup"><span data-stu-id="cd6a1-356">Assign a policy package to users</span></span>

<span data-ttu-id="cd6a1-357">Um pacote de política no Teams é um conjunto de políticas e configurações de política predefinidas que você pode atribuir aos usuários que têm as mesmas funções ou funções semelhantes em sua organização.</span><span class="sxs-lookup"><span data-stu-id="cd6a1-357">A policy package in Teams is a collection of predefined policies and policy settings that you can assign to users who have the same or similar roles in your organization.</span></span> <span data-ttu-id="cd6a1-358">Cada pacote de política é projetado em torno de uma função de usuário e inclui políticas e configurações de política predefinidas que suportam atividades típicas para essa função.</span><span class="sxs-lookup"><span data-stu-id="cd6a1-358">Each policy package is designed around a user role and includes predefined policies and policy settings that support activities typical for that role.</span></span> <span data-ttu-id="cd6a1-359">Alguns exemplos de pacotes de política são o pacote Educação (Professor) e o pacote Assistência Médica (Trabalhador médico).</span><span class="sxs-lookup"><span data-stu-id="cd6a1-359">Some examples of policy packages are the Education (Teacher) package and Healthcare (Clinical worker) package.</span></span> <span data-ttu-id="cd6a1-360">Para saber mais, confira [Gerenciar pacotes de política no Teams.](manage-policy-packages.md)</span><span class="sxs-lookup"><span data-stu-id="cd6a1-360">To learn more, see [Manage policy packages in Teams](manage-policy-packages.md).</span></span>

### <a name="assign-a-policy-package-to-one-user"></a><span data-ttu-id="cd6a1-361">Atribuir um pacote de política a um usuário</span><span class="sxs-lookup"><span data-stu-id="cd6a1-361">Assign a policy package to one user</span></span>

1. <span data-ttu-id="cd6a1-362">Na barra de navegação à esquerda do centro de administração do Microsoft Teams, vá para **Usuários** e clique no usuário.</span><span class="sxs-lookup"><span data-stu-id="cd6a1-362">In the left navigation of the Microsoft Teams admin center, go to **Users**, and then click the user.</span></span>
2. <span data-ttu-id="cd6a1-363">Na página do usuário, clique em **Políticas** e, ao lado do pacote **De política,** clique em **Editar**.</span><span class="sxs-lookup"><span data-stu-id="cd6a1-363">On the user's page, click **Policies**, and then next to **Policy package**, click **Edit**.</span></span>
3. <span data-ttu-id="cd6a1-364">No painel **Atribuir pacote de** política, selecione o pacote que você deseja atribuir e clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="cd6a1-364">In the **Assign policy package** pane, select the package you want to assign, and then click **Save**.</span></span>

### <a name="assign-a-policy-package-to-multiple-users"></a><span data-ttu-id="cd6a1-365">Atribuir um pacote de política a vários usuários</span><span class="sxs-lookup"><span data-stu-id="cd6a1-365">Assign a policy package to multiple users</span></span>

1. <span data-ttu-id="cd6a1-366">Na navegação à esquerda do centro de administração do Microsoft Teams, vá para pacotes de política e selecione o pacote de política que você deseja atribuir clicando à esquerda do nome do pacote.</span><span class="sxs-lookup"><span data-stu-id="cd6a1-366">In the left navigation of the Microsoft Teams admin center, go to **Policy packages**, and then select the policy package you want to assign by clicking to the left of the package name.</span></span>
2. <span data-ttu-id="cd6a1-367">Clique **em Gerenciar usuários.**</span><span class="sxs-lookup"><span data-stu-id="cd6a1-367">Click **Manage users**.</span></span>
3. <span data-ttu-id="cd6a1-368">No painel **Gerenciar usuários**, procure o usuário pelo nome de exibição ou pelo nome de usuário, escolha o nome e clique em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="cd6a1-368">In the **Manage users** pane, search for the user by display name or by user name, select the name, and then click **Add**.</span></span> <span data-ttu-id="cd6a1-369">Repita esta etapa para cada usuário que você deseja adicionar.</span><span class="sxs-lookup"><span data-stu-id="cd6a1-369">Repeat this step for each user that you want to add.</span></span>
4. <span data-ttu-id="cd6a1-370">Quando terminar de adicionar usuários, clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="cd6a1-370">When you're finished adding users, click **Save**.</span></span>

## <a name="assign-a-policy-package-to-a-group"></a><span data-ttu-id="cd6a1-371">Atribua o pacote de política a um grupo.</span><span class="sxs-lookup"><span data-stu-id="cd6a1-371">Assign a policy package to a group</span></span>

<span data-ttu-id="cd6a1-372">**Este recurso está na visualização particular**</span><span class="sxs-lookup"><span data-stu-id="cd6a1-372">**This feature is in private preview**</span></span>

<span data-ttu-id="cd6a1-373">As atribuições de pacote de política aos grupos permitem atribuir várias políticas a um grupo de usuários, como uma lista de distribuição ou grupo de segurança.</span><span class="sxs-lookup"><span data-stu-id="cd6a1-373">Policy package assignment to groups let you assign multiple policies to a group of users, such as a security group or distribution list.</span></span> <span data-ttu-id="cd6a1-374">As atribuições de política serão propagadas para os membros do grupo, de acordo com as regras de precedência.</span><span class="sxs-lookup"><span data-stu-id="cd6a1-374">The policy assignment is propagated to members of the group according to precedence rules.</span></span> <span data-ttu-id="cd6a1-375">À medida que os membros forem adicionados ou removidos de um grupo, as atribuições de política herdadas serão atualizadas.</span><span class="sxs-lookup"><span data-stu-id="cd6a1-375">As members are added to or removed from a group, their inherited policy assignments are updated accordingly.</span></span>

<span data-ttu-id="cd6a1-376">A atribuição de pacote de política a grupos é recomendada para grupos de até 50.000 usuários, mas também funcionará com grupos maiores.</span><span class="sxs-lookup"><span data-stu-id="cd6a1-376">Policy package assignment to groups is recommended for groups of up to 50,000 users but it will also work with larger groups.</span></span> 

<span data-ttu-id="cd6a1-377">Quando você atribui o pacote de política, ele é atribuído imediatamente ao grupo.</span><span class="sxs-lookup"><span data-stu-id="cd6a1-377">When you assign the policy package, it's immediately assigned to the group.</span></span> <span data-ttu-id="cd6a1-378">No entanto, observe que a propagação da atribuição de política aos membros do grupo é executada como uma operação em segundo plano e pode levar algum tempo, dependendo do tamanho do grupo.</span><span class="sxs-lookup"><span data-stu-id="cd6a1-378">However, note that the propagation of the policy assignment to members of the group is performed as a background operation and may take some time, depending on the size of the group.</span></span> <span data-ttu-id="cd6a1-379">O mesmo é verdadeiro quando uma política é não atribuída de um grupo ou quando membros são adicionados ou removidos de um grupo.</span><span class="sxs-lookup"><span data-stu-id="cd6a1-379">The same is true when a policy is unassigned from a group, or when members are added to or removed from a group.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="cd6a1-380">Antes de começar, é importante entender as regras de [precedência](#precedence-rules) e a classificação [de atribuição de grupo.](#group-assignment-ranking)</span><span class="sxs-lookup"><span data-stu-id="cd6a1-380">Before you get started, it's important to understand [precedence rules](#precedence-rules) and [group assignment ranking](#group-assignment-ranking).</span></span> <span data-ttu-id="cd6a1-381">Leia e entenda os conceitos no que você precisa saber sobre [a atribuição](#what-you-need-to-know-about-policy-assignment-to-groups) de política a grupos anteriormente neste artigo.</span><span class="sxs-lookup"><span data-stu-id="cd6a1-381">Make sure you read and understand the concepts in [What you need to know about policy assignment to groups](#what-you-need-to-know-about-policy-assignment-to-groups) earlier in this article.</span></span>

### <a name="using-the-microsoft-teams-admin-center-coming-soon"></a><span data-ttu-id="cd6a1-382">Usando o centro de administração do Microsoft Teams (em breve)</span><span class="sxs-lookup"><span data-stu-id="cd6a1-382">Using the Microsoft Teams admin center (coming soon)</span></span>

<span data-ttu-id="cd6a1-383">A atribuição de pacote de política a grupos no centro de administração do Microsoft Teams será em breve.</span><span class="sxs-lookup"><span data-stu-id="cd6a1-383">Policy package assignment to groups in the Microsoft Teams admin center is coming soon.</span></span> <span data-ttu-id="cd6a1-384">Confira aqui as atualizações mais recentes.</span><span class="sxs-lookup"><span data-stu-id="cd6a1-384">Check back here for the latest updates.</span></span>

### <a name="using-powershell"></a><span data-ttu-id="cd6a1-385">Usando o Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="cd6a1-385">Using PowerShell</span></span>

#### <a name="install-and-connect-to-the-microsoft-teams-powershell-module"></a><span data-ttu-id="cd6a1-386">Instalar e conectar-se ao módulo do PowerShell do Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="cd6a1-386">Install and connect to the Microsoft Teams PowerShell module</span></span>

<span data-ttu-id="cd6a1-387">Para obter orientações passo a passo, consulte [Instalar o PowerShell do Teams.](teams-powershell-install.md)</span><span class="sxs-lookup"><span data-stu-id="cd6a1-387">For step-by-step guidance, see [Install Teams PowerShell](teams-powershell-install.md).</span></span>

#### <a name="assign-a-policy-package-to-a-group-of-users"></a><span data-ttu-id="cd6a1-388">Atribuir um pacote de política a um grupo de usuários</span><span class="sxs-lookup"><span data-stu-id="cd6a1-388">Assign a policy package to a group of users</span></span>

<span data-ttu-id="cd6a1-389">Use o cmdlet [Grant-CsGroupPolicyPackageAssignment](https://docs.microsoft.com/powershell/module/teams/grant-csgrouppolicypackageassignment) para atribuir um pacote de política a um grupo.</span><span class="sxs-lookup"><span data-stu-id="cd6a1-389">You use the [Grant-CsGroupPolicyPackageAssignment](https://docs.microsoft.com/powershell/module/teams/grant-csgrouppolicypackageassignment) cmdlet to assign a policy package to a group.</span></span> <span data-ttu-id="cd6a1-390">Você pode especificar um grupo usando a ID do objeto, o endereço SIP ou o endereço de email.</span><span class="sxs-lookup"><span data-stu-id="cd6a1-390">You can specify a group by using the object Id, SIP address, or email address.</span></span> <span data-ttu-id="cd6a1-391">Ao atribuir o pacote de política, especifique uma classificação de atribuição [de grupo](#group-assignment-ranking) para cada tipo de política no pacote de política.</span><span class="sxs-lookup"><span data-stu-id="cd6a1-391">When you assign the policy package, specify a [group assignment ranking](#group-assignment-ranking) for each policy type in the policy package.</span></span> 

<span data-ttu-id="cd6a1-392">Neste exemplo, atribuímos o pacote de política Education_Teacher a um grupo com uma classificação de atribuição de 1 para TeamsAppSetupPolicy e TeamsMeetingBroadcastPolicy e uma classificação de 2 para TeamsMeetingPolicy.</span><span class="sxs-lookup"><span data-stu-id="cd6a1-392">In this example, we assign the Education_Teacher policy package to a group with an assignment ranking of 1 for TeamsAppSetupPolicy and TeamsMeetingBroadcastPolicy and a ranking of 2 for TeamsMeetingPolicy.</span></span>

```powershell
Grant-CsGroupPolicyPackageAssignment -GroupId "dae90bb4-120f-4a3e-a15d-30f142e79f69" -PackageName "Education_Teacher" -PolicyRankings "TeamsAppSetupPolicy, 1", "TeamsMeetingBroadcastPolicy, 1", "TeamsMeetingPolicy, 2"
```

## <a name="assign-a-policy-package-to-a-batch-of-users"></a><span data-ttu-id="cd6a1-393">Atribuir um pacote de política a um lote de usuários</span><span class="sxs-lookup"><span data-stu-id="cd6a1-393">Assign a policy package to a batch of users</span></span>

<span data-ttu-id="cd6a1-394">Com a atribuição de pacote de política de lote, você pode atribuir um pacote de política a grandes conjuntos de usuários por vez sem precisar usar um script.</span><span class="sxs-lookup"><span data-stu-id="cd6a1-394">With batch policy package assignment, you can assign a policy package to large sets of users at a time without having to use a script.</span></span> <span data-ttu-id="cd6a1-395">Use o cmdlet [New-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation) para enviar um lote de usuários e o pacote de política que você deseja atribuir.</span><span class="sxs-lookup"><span data-stu-id="cd6a1-395">You use the [New-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation) cmdlet to submit a batch of users and the policy package that you want to assign.</span></span> <span data-ttu-id="cd6a1-396">As atribuições são processadas como uma operação de plano de fundo e uma ID de operação é gerada para cada lote.</span><span class="sxs-lookup"><span data-stu-id="cd6a1-396">The assignments are processed as a background operation and an operation ID is generated for each batch.</span></span> <span data-ttu-id="cd6a1-397">Em seguida, você pode usar o cmdlet [Get-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/get-csbatchpolicyassignmentoperation) para controlar o progresso e o status das atribuições em um lote.</span><span class="sxs-lookup"><span data-stu-id="cd6a1-397">You can then use the [Get-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/get-csbatchpolicyassignmentoperation) cmdlet to track the progress and status of the assignments in a batch.</span></span>

<span data-ttu-id="cd6a1-398">Você pode especificar usuários por sua ID de objeto ou endereço SIP ( Session Initiation Protocol).</span><span class="sxs-lookup"><span data-stu-id="cd6a1-398">You can specify users by their object Id or Session Initiation Protocol (SIP) address.</span></span> <span data-ttu-id="cd6a1-399">Observe que o endereço SIP de um usuário geralmente tem o mesmo valor que o UPN (Nome Principal do Usuário) ou endereço de email, mas isso não é necessário.</span><span class="sxs-lookup"><span data-stu-id="cd6a1-399">Note that a user's SIP address often has the same value as the User Principal Name (UPN) or email address, but this is not required.</span></span> <span data-ttu-id="cd6a1-400">Se um usuário for especificado usando seu UPN ou email, mas tiver um valor diferente do endereço SIP, a atribuição de política falhará para o usuário.</span><span class="sxs-lookup"><span data-stu-id="cd6a1-400">If a user is specified using their UPN or email, but it has a different value than their SIP address, then policy assignment will fail for the user.</span></span> <span data-ttu-id="cd6a1-401">Se um lote incluir usuários duplicados, as duplicatas serão removidas do lote antes do processamento e o status só será fornecido para os usuários exclusivos restantes no lote.</span><span class="sxs-lookup"><span data-stu-id="cd6a1-401">If a batch includes duplicate users, the duplicates will be removed from the batch before processing and status will only be provided for the unique users remaining in the batch.</span></span> 

<span data-ttu-id="cd6a1-402">Um lote pode conter até 5.000 usuários.</span><span class="sxs-lookup"><span data-stu-id="cd6a1-402">A batch can contain up to 5,000 users.</span></span> <span data-ttu-id="cd6a1-403">Para obter melhores resultados, não envie mais do que alguns lotes por vez.</span><span class="sxs-lookup"><span data-stu-id="cd6a1-403">For best results, do not submit more than a few batches at a time.</span></span> <span data-ttu-id="cd6a1-404">Permitir que lotes concluam o processamento antes de enviar mais lotes.</span><span class="sxs-lookup"><span data-stu-id="cd6a1-404">Allow batches to complete processing before submitting more batches.</span></span>

### <a name="install-and-connect-to-the-microsoft-teams-powershell-module"></a><span data-ttu-id="cd6a1-405">Instalar e conectar-se ao módulo do PowerShell do Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="cd6a1-405">Install and connect to the Microsoft Teams PowerShell module</span></span>

<span data-ttu-id="cd6a1-406">Execute o seguinte para instalar o módulo [do PowerShell](https://www.powershellgallery.com/packages/MicrosoftTeams) do Microsoft Teams (caso ainda não tenha feito isso).</span><span class="sxs-lookup"><span data-stu-id="cd6a1-406">Run the following to install the [Microsoft Teams PowerShell module](https://www.powershellgallery.com/packages/MicrosoftTeams) (if you haven't already).</span></span> <span data-ttu-id="cd6a1-407">Certifique-se de instalar a versão 1.0.5 ou posterior.</span><span class="sxs-lookup"><span data-stu-id="cd6a1-407">Make sure you install version 1.0.5 or later.</span></span>

```powershell
Install-Module -Name MicrosoftTeams
```

<span data-ttu-id="cd6a1-408">Execute o seguinte para se conectar ao Teams e iniciar uma sessão.</span><span class="sxs-lookup"><span data-stu-id="cd6a1-408">Run the following to connect to Teams and start a session.</span></span>

```powershell
Connect-MicrosoftTeams
```

<span data-ttu-id="cd6a1-409">Quando for solicitado, entre usando suas credenciais de administrador.</span><span class="sxs-lookup"><span data-stu-id="cd6a1-409">When you're prompted, sign in using your admin credentials.</span></span>

### <a name="assign-a-policy-package-to-a-batch-of-users"></a><span data-ttu-id="cd6a1-410">Atribuir um pacote de política a um lote de usuários</span><span class="sxs-lookup"><span data-stu-id="cd6a1-410">Assign a policy package to a batch of users</span></span>

<span data-ttu-id="cd6a1-411">Neste exemplo, usamos o cmdlet [New-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation) para atribuir o pacote de política Education_PrimaryStudent a um lote de usuários.</span><span class="sxs-lookup"><span data-stu-id="cd6a1-411">In this example, we use the [New-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation) cmdlet to assign the Education_PrimaryStudent policy package to a batch of users.</span></span>

```powershell
New-CsBatchPolicyPackageAssignmentOperation -Identity 1bc0b35f-095a-4a37-a24c-c4b6049816ab,user1@econtoso.com,user2@contoso.com -PackageName Education_PrimaryStudent
```

### <a name="get-the-status-of-a-batch-assignment"></a><span data-ttu-id="cd6a1-412">Obter o status de uma atribuição em lote</span><span class="sxs-lookup"><span data-stu-id="cd6a1-412">Get the status of a batch assignment</span></span>

<span data-ttu-id="cd6a1-413">Execute o seguinte para obter o status de uma atribuição em lotes, onde OperationId é a ID da operação retornada pelo ```New-CsBatchPolicyAssignmentOperation``` cmdlet para um determinado lote.</span><span class="sxs-lookup"><span data-stu-id="cd6a1-413">Run the following to get the status of a batch assignment, where OperationId is the operation ID that's returned by the ```New-CsBatchPolicyAssignmentOperation``` cmdlet for a given batch.</span></span>

```powershell
$Get-CsBatchPolicyAssignmentOperation -OperationId f985e013-0826-40bb-8c94-e5f367076044 | fl
```

<span data-ttu-id="cd6a1-414">Se a saída mostrar que ocorreu um erro, execute o seguinte para obter mais informações sobre erros, que estão na ```UserState``` propriedade.</span><span class="sxs-lookup"><span data-stu-id="cd6a1-414">If the output shows that an error occurred, run the following to get more information about errors, which are in the ```UserState``` property.</span></span>

```powershell
Get-CsBatchPolicyAssignmentOperation -OperationId f985e013-0826-40bb-8c94-e5f367076044 | Select -ExpandProperty UserState
```

<span data-ttu-id="cd6a1-415">Para saber mais, consulte [Get-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/get-csbatchpolicyassignmentoperation).</span><span class="sxs-lookup"><span data-stu-id="cd6a1-415">To learn more, see [Get-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/get-csbatchpolicyassignmentoperation).</span></span> 

## <a name="related-topics"></a><span data-ttu-id="cd6a1-416">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="cd6a1-416">Related topics</span></span>

[<span data-ttu-id="cd6a1-417">Visão Geral do PowerShell do Teams</span><span class="sxs-lookup"><span data-stu-id="cd6a1-417">Teams PowerShell Overview</span></span>](teams-powershell-overview.md)
