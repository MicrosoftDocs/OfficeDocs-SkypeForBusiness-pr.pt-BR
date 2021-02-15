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
description: Conheça as diferentes maneiras de atribuir políticas aos usuários no Microsoft Teams.
f1keywords:
- ms.teamsadmincenter.bulkoperations.users.edit
- ms.teamsadmincenter.bulkoperations.edit
ms.openlocfilehash: 3a788ff2712c065d0273d4dfb6233f03e2272337
ms.sourcegitcommit: bfada4fd06c5cff12b0eefd3384bb3c10d10787f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/12/2021
ms.locfileid: "50196285"
---
# <a name="assign-policies-to-your-users-in-microsoft-teams"></a><span data-ttu-id="ae404-103">Atribuir políticas aos usuários no Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="ae404-103">Assign policies to your users in Microsoft Teams</span></span>

<span data-ttu-id="ae404-104">Como administrador, você usa políticas para controlar os recursos do Teams que estão disponíveis para os usuários em sua organização.</span><span class="sxs-lookup"><span data-stu-id="ae404-104">As an admin, you use policies to control the Teams features that are available to users in your organization.</span></span> <span data-ttu-id="ae404-105">Por exemplo, há políticas de chamada, políticas de reunião e políticas de mensagens, para citar apenas algumas.</span><span class="sxs-lookup"><span data-stu-id="ae404-105">For example, there are calling policies, meeting policies, and messaging policies, to name just a few.</span></span>

<span data-ttu-id="ae404-106">As organizações têm diferentes tipos de usuários com necessidades exclusivas.</span><span class="sxs-lookup"><span data-stu-id="ae404-106">Organizations have different types of users with unique needs.</span></span> <span data-ttu-id="ae404-107">As políticas personalizadas que você cria e atribui permitem adaptar as configurações de política a diferentes conjuntos de usuários com base nessas necessidades.</span><span class="sxs-lookup"><span data-stu-id="ae404-107">Custom policies that you create and assign let you tailor policy settings to different sets of users based on those needs.</span></span>

<span data-ttu-id="ae404-108">Para gerenciar facilmente as políticas em sua organização, o Teams oferece várias maneiras de atribuir políticas aos usuários.</span><span class="sxs-lookup"><span data-stu-id="ae404-108">To easily manage policies in your organization, Teams offers several ways to assign policies to users.</span></span> <span data-ttu-id="ae404-109">Atribua uma política diretamente aos usuários, individualmente ou em escala por meio de uma atribuição em lotes, ou a um grupo do que os usuários são membros.</span><span class="sxs-lookup"><span data-stu-id="ae404-109">Assign a policy directly to users, either individually or at scale through a batch assignment, or to a group that the users are members of.</span></span> <span data-ttu-id="ae404-110">Você também pode usar pacotes de política para atribuir um conjunto predefinido de políticas aos usuários em sua organização que têm funções semelhantes.</span><span class="sxs-lookup"><span data-stu-id="ae404-110">You can also use policy packages to assign a preset collection of policies to users in your organization who have similar roles.</span></span> <span data-ttu-id="ae404-111">A opção escolhida depende do número de políticas que você está gerenciando e do número de usuários aos quais está atribuindo políticas.</span><span class="sxs-lookup"><span data-stu-id="ae404-111">The option that you choose depends on the number of policies that you're managing and the number of users you're assigning policies to.</span></span> <span data-ttu-id="ae404-112">As políticas globais (padrão em toda a organização) se aplicam ao maior número de usuários em sua organização.</span><span class="sxs-lookup"><span data-stu-id="ae404-112">Global (Org-wide default) policies apply to the largest number of users in your organization.</span></span> <span data-ttu-id="ae404-113">Você só precisa atribuir políticas aos usuários que exigem políticas especializadas.</span><span class="sxs-lookup"><span data-stu-id="ae404-113">You only have to assign policies to those users that require specialized policies.</span></span>

<span data-ttu-id="ae404-114">Este artigo descreve as diferentes maneiras de atribuir políticas aos usuários e os cenários recomendados para quando usar o quê.</span><span class="sxs-lookup"><span data-stu-id="ae404-114">This article describes the different ways that you can assign policies to users and the recommended scenarios for when to use what.</span></span>

## <a name="which-policy-takes-precedence"></a><span data-ttu-id="ae404-115">Qual política tem precedência?</span><span class="sxs-lookup"><span data-stu-id="ae404-115">Which policy takes precedence?</span></span>

<span data-ttu-id="ae404-116">Um usuário tem uma política eficaz para cada tipo de política.</span><span class="sxs-lookup"><span data-stu-id="ae404-116">A user has one effective policy for each policy type.</span></span> <span data-ttu-id="ae404-117">É possível, ou até mesmo provável, que um usuário tenha atribuído uma política diretamente e também seja membro de um ou mais grupos que recebe uma política do mesmo tipo.</span><span class="sxs-lookup"><span data-stu-id="ae404-117">It's possible, or even likely, that a user is directly assigned a policy and is also a member of one or more groups that's assigned a policy of the same type.</span></span> <span data-ttu-id="ae404-118">Nesses tipos de cenários, qual política tem precedência?</span><span class="sxs-lookup"><span data-stu-id="ae404-118">In these kinds of scenarios, which policy takes precedence?</span></span> <span data-ttu-id="ae404-119">A política efetiva de um usuário é determinada de acordo com as regras de precedência, da seguinte maneira.</span><span class="sxs-lookup"><span data-stu-id="ae404-119">A user's effective policy is determined according to rules of precedence, as follows.</span></span>

<span data-ttu-id="ae404-120">Se um usuário recebe diretamente uma política (individualmente ou por meio de uma atribuição em lotes), essa política tem precedência.</span><span class="sxs-lookup"><span data-stu-id="ae404-120">If a user is directly assigned a policy (either individually or through a batch assignment), that policy takes precedence.</span></span> <span data-ttu-id="ae404-121">No exemplo visual a seguir, a política efetiva do usuário é a política de reunião do Square Square, que é atribuída diretamente ao usuário.</span><span class="sxs-lookup"><span data-stu-id="ae404-121">In the following visual example, the user's effective policy is the Lincoln Square meeting policy, which is directly assigned to the user.</span></span>

![Diagrama mostrando como uma política atribuída diretamente tem precedência](media/assign-policies-example-directly-assigned.png)

<span data-ttu-id="ae404-123">Se um usuário não receber diretamente uma política de um determinado tipo, a política atribuída a um grupo do qual o usuário é membro tem precedência.</span><span class="sxs-lookup"><span data-stu-id="ae404-123">If a user isn't directly assigned a policy of a given type, the policy assigned to a group that the user is a member of takes precedence.</span></span> <span data-ttu-id="ae404-124">Se um usuário for membro de vários grupos, [](#group-assignment-ranking) a política que tem a classificação de atribuição de grupo mais alta para determinado tipo de política terá precedência.</span><span class="sxs-lookup"><span data-stu-id="ae404-124">If a user is a member of multiple groups, the policy that has the highest [group assignment ranking](#group-assignment-ranking) for the given policy type takes precedence.</span></span>

<span data-ttu-id="ae404-125">Neste exemplo visual, a política efetiva do usuário é a política Exec Teams e HD, que tem a classificação de atribuição mais alta em relação a outros grupos dos quais o usuário é membro e que também recebe uma política do mesmo tipo de política.</span><span class="sxs-lookup"><span data-stu-id="ae404-125">In this visual example, the user's effective policy is the Exec Teams and HD policy, which has the highest assignment ranking relative to other groups that the user is a member of and that are also assigned a policy of the same policy type.</span></span>  

![Diagrama mostrando como uma política herdada do grupo tem precedência](media/assign-policies-example-group.png)

<span data-ttu-id="ae404-127">Se um usuário não recebe uma política diretamente ou não é membro de nenhum grupo que recebe uma política, o usuário obtém a política global (padrão de toda a organização) para esse tipo de política.</span><span class="sxs-lookup"><span data-stu-id="ae404-127">If a user isn't directly assigned a policy or isn't a member of any groups that are assigned a policy, the user gets the global (Org-wide default) policy for that policy type.</span></span> <span data-ttu-id="ae404-128">Veja um exemplo visual.</span><span class="sxs-lookup"><span data-stu-id="ae404-128">Here's a visual example.</span></span>

![Diagrama mostrando como uma política global tem precedência](media/assign-policies-example-global.png)

<span data-ttu-id="ae404-130">Para saber mais, confira [as regras de Precedência.](#precedence-rules)</span><span class="sxs-lookup"><span data-stu-id="ae404-130">To learn more, see [Precedence rules](#precedence-rules).</span></span>

## <a name="ways-to-assign-policies"></a><span data-ttu-id="ae404-131">Maneiras de atribuir políticas</span><span class="sxs-lookup"><span data-stu-id="ae404-131">Ways to assign policies</span></span>

<span data-ttu-id="ae404-132">Aqui está uma visão geral de como você pode atribuir políticas aos usuários e os cenários recomendados para cada um deles.</span><span class="sxs-lookup"><span data-stu-id="ae404-132">Here's an overview of the ways that you can assign policies to users and the recommended scenarios for each.</span></span> <span data-ttu-id="ae404-133">Selecione os links para saber mais.</span><span class="sxs-lookup"><span data-stu-id="ae404-133">Select the links to learn more.</span></span>

<span data-ttu-id="ae404-134">Antes de atribuir políticas a usuários ou grupos individuais, comece definindo as políticas [globais (padrão](#set-the-global-policies) em toda a organização) para que se apliquem ao maior número de usuários em sua organização.</span><span class="sxs-lookup"><span data-stu-id="ae404-134">Before assigning policies to individual users or groups, start by [setting the global (Org-wide default) policies](#set-the-global-policies) so that they apply to the largest number of users in your organization.</span></span>  <span data-ttu-id="ae404-135">Depois que as políticas globais são definidas, você só precisará atribuir políticas aos usuários que exigem políticas especializadas.</span><span class="sxs-lookup"><span data-stu-id="ae404-135">Once the global policies are set, you'll only need to assign policies to those users that require specialized policies.</span></span>

|<span data-ttu-id="ae404-136">Faça isto</span><span class="sxs-lookup"><span data-stu-id="ae404-136">Do this</span></span>  |<span data-ttu-id="ae404-137">Se...</span><span class="sxs-lookup"><span data-stu-id="ae404-137">If...</span></span>  | <span data-ttu-id="ae404-138">Usando...</span><span class="sxs-lookup"><span data-stu-id="ae404-138">Using...</span></span>
|---------|---------|----|
|[<span data-ttu-id="ae404-139">Atribuir uma política a usuários individuais</span><span class="sxs-lookup"><span data-stu-id="ae404-139">Assign a policy to individual users</span></span>](#assign-a-policy-to-individual-users)    | <span data-ttu-id="ae404-140">Você é novo no Teams e está apenas começando ou só precisa atribuir uma ou duas políticas a um pequeno número de usuários.</span><span class="sxs-lookup"><span data-stu-id="ae404-140">You're new to Teams and just getting started or you only need to assign one or a couple of policies to a small number of users.</span></span> |<span data-ttu-id="ae404-141">O centro de administração do Microsoft Teams ou cmdlets do PowerShell no módulo PowerShell do Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="ae404-141">The Microsoft Teams admin center or PowerShell cmdlets in the Skype for Business Online PowerShell module</span></span>
|[<span data-ttu-id="ae404-142">Atribuir uma política a um grupo</span><span class="sxs-lookup"><span data-stu-id="ae404-142">Assign a policy to a group</span></span>](#assign-a-policy-to-a-group) |<span data-ttu-id="ae404-143">Atribua políticas com base na associação de um usuário ao grupo.</span><span class="sxs-lookup"><span data-stu-id="ae404-143">Assign policies based on a user's group membership.</span></span> <span data-ttu-id="ae404-144">Por exemplo, atribua uma política a todos os usuários em um grupo de segurança ou lista de distribuição.</span><span class="sxs-lookup"><span data-stu-id="ae404-144">For example, assign a policy to all users in a security group or distribution list.</span></span>| <span data-ttu-id="ae404-145">O centro de administração do Microsoft Teams ou cmdlets do PowerShell no módulo do Teams PowerShell</span><span class="sxs-lookup"><span data-stu-id="ae404-145">The Microsoft Teams admin center or PowerShell cmdlets in the Teams PowerShell module</span></span>|
|[<span data-ttu-id="ae404-146">Atribuir uma política a um lote de usuários</span><span class="sxs-lookup"><span data-stu-id="ae404-146">Assign a policy to a batch of users</span></span>](#assign-a-policy-to-a-batch-of-users)   | <span data-ttu-id="ae404-147">Atribua políticas a grandes conjuntos de usuários.</span><span class="sxs-lookup"><span data-stu-id="ae404-147">Assign policies to large sets of users.</span></span> <span data-ttu-id="ae404-148">Por exemplo, atribua uma política a centenas ou milhares de usuários em sua organização por vez.</span><span class="sxs-lookup"><span data-stu-id="ae404-148">For example, assign a policy to hundreds or thousands of users in your organization at a time.</span></span> |<span data-ttu-id="ae404-149">O centro de administração do Microsoft Teams ou cmdlets do PowerShell no módulo do Teams PowerShell</span><span class="sxs-lookup"><span data-stu-id="ae404-149">The Microsoft Teams admin center or PowerShell cmdlets in the Teams PowerShell module</span></span>|
| [<span data-ttu-id="ae404-150">Atribuir um pacote de política aos usuários</span><span class="sxs-lookup"><span data-stu-id="ae404-150">Assign a policy package to users</span></span>](#assign-a-policy-package-to-users)  |<span data-ttu-id="ae404-151">Atribua várias políticas a conjuntos específicos de usuários em sua organização que tenham funções iguais ou semelhantes.</span><span class="sxs-lookup"><span data-stu-id="ae404-151">Assign multiple policies to specific sets of users in your organization who have the same or similar roles.</span></span> <span data-ttu-id="ae404-152">Por exemplo, atribua o pacote de política Educacional (Professor) aos professores da sua escola para que eles tenham acesso total a chats, chamada e reuniões.</span><span class="sxs-lookup"><span data-stu-id="ae404-152">For example, assign the Education (Teacher) policy package to teachers in your school to give them full access to chats, calling, and meetings.</span></span> <span data-ttu-id="ae404-153">Atribua o pacote de política Educacional (aluno do ensino médio) a alunos secundários para limitar determinados recursos, como chamada privada.</span><span class="sxs-lookup"><span data-stu-id="ae404-153">Assign the Education (Secondary school student) policy package to secondary students to limit certain capabilities such as private calling.</span></span>  |<span data-ttu-id="ae404-154">O centro de administração do Microsoft Teams ou cmdlets do PowerShell no módulo do Teams PowerShell</span><span class="sxs-lookup"><span data-stu-id="ae404-154">The Microsoft Teams admin center or PowerShell cmdlets in the Teams PowerShell module</span></span>|
| <span data-ttu-id="ae404-155">[Atribuir um pacote de política a um grupo](#assign-a-policy-package-to-a-group) (em visualização privada)</span><span class="sxs-lookup"><span data-stu-id="ae404-155">[Assign a policy package to a group](#assign-a-policy-package-to-a-group) (in private preview)</span></span>   |<span data-ttu-id="ae404-156">Atribua várias políticas a um grupo de usuários em sua organização que tenham funções iguais ou semelhantes.</span><span class="sxs-lookup"><span data-stu-id="ae404-156">Assign multiple policies to a group of users in your organization who have the same or similar roles.</span></span> <span data-ttu-id="ae404-157">Por exemplo, atribua um pacote de política a todos os usuários em um grupo de segurança ou lista de distribuição.</span><span class="sxs-lookup"><span data-stu-id="ae404-157">For example, assign a policy package to all users in a security group or distribution list.</span></span> |<span data-ttu-id="ae404-158">O Centro de administração do Microsoft Teams (em breve) ou cmdlets do PowerShell no módulo do Teams PowerShell</span><span class="sxs-lookup"><span data-stu-id="ae404-158">The Microsoft Teams admin center (coming soon) or PowerShell cmdlets in the Teams PowerShell module</span></span>|
| [<span data-ttu-id="ae404-159">Atribuir um pacote de política a um lote de usuários</span><span class="sxs-lookup"><span data-stu-id="ae404-159">Assign a policy package to a batch of users</span></span>](#assign-a-policy-package-to-a-batch-of-users)|<span data-ttu-id="ae404-160">Atribua várias políticas a um lote de usuários em sua organização que têm funções iguais ou semelhantes.</span><span class="sxs-lookup"><span data-stu-id="ae404-160">Assign multiple policies to a batch of users in your organization who have the same or similar roles.</span></span> <span data-ttu-id="ae404-161">Por exemplo, atribua o pacote de política Education (Professor) a todos os professores da sua escola usando atribuição em lotes para dar a eles acesso total a chats, chamada e reuniões.</span><span class="sxs-lookup"><span data-stu-id="ae404-161">For example, assign the Education (Teacher) policy package to all teachers in your school using batch assignment to give them full access to chats, calling, and meetings.</span></span> <span data-ttu-id="ae404-162">Atribua o pacote de política Educacional (aluno do ensino médio) a um lote de alunos secundários para limitar determinados recursos, como chamada privada.</span><span class="sxs-lookup"><span data-stu-id="ae404-162">Assign the Education (Secondary school student) policy package to a batch of secondary students to limit certain capabilities such as private calling.</span></span>|<span data-ttu-id="ae404-163">Cmdlets do PowerShell no módulo do Teams PowerShell</span><span class="sxs-lookup"><span data-stu-id="ae404-163">PowerShell cmdlets in the Teams PowerShell module</span></span>|

## <a name="set-the-global-policies"></a><span data-ttu-id="ae404-164">Definir as políticas globais</span><span class="sxs-lookup"><span data-stu-id="ae404-164">Set the global policies</span></span>

<span data-ttu-id="ae404-165">Siga estas etapas para definir as políticas globais (padrão em toda a organização) para cada tipo de política.</span><span class="sxs-lookup"><span data-stu-id="ae404-165">Follow these steps to set the global (Org-wide default) policies for each policy type.</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="ae404-166">Usando o centro de administração do Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="ae404-166">Using the Microsoft Teams admin center</span></span>

1. <span data-ttu-id="ae404-167">Na navegação à esquerda do Centro de administração do Microsoft Teams, vá para a página de política do tipo de política que você deseja atualizar.</span><span class="sxs-lookup"><span data-stu-id="ae404-167">In the left navigation of the Microsoft Teams admin center, go to the policy page for the policy type you want to update.</span></span> <span data-ttu-id="ae404-168">Por exemplo, políticas **do Teams**  >  **Teams,** **políticas reuniões** de reuniões, políticas de  >   **mensagens** ou políticas **de Chamada** de  >  **Voz.**</span><span class="sxs-lookup"><span data-stu-id="ae404-168">For example, **Teams** > **Teams policies**, **Meetings** > **Meetings policies**, **Messaging policies**, or **Voice** > **Calling policies**.</span></span>
2. <span data-ttu-id="ae404-169">Selecione a **política Global (padrão em toda a organização)** para exibir as configurações atuais.</span><span class="sxs-lookup"><span data-stu-id="ae404-169">Select the **Global (Org-wide default)** policy to view the current settings.</span></span>
3. <span data-ttu-id="ae404-170">Atualize a política conforme necessário e selecione **Aplicar.**</span><span class="sxs-lookup"><span data-stu-id="ae404-170">Update the policy as needed, and then select **Apply**.</span></span>

### <a name="using-powershell"></a><span data-ttu-id="ae404-171">Usando o Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="ae404-171">Using PowerShell</span></span>

<span data-ttu-id="ae404-172">Para definir as políticas globais usando o PowerShell, use o identificador global.</span><span class="sxs-lookup"><span data-stu-id="ae404-172">To set the global policies using PowerShell, use the Global identifier.</span></span>  <span data-ttu-id="ae404-173">Comece revendo a política global atual para determinar qual configuração você deseja alterar.</span><span class="sxs-lookup"><span data-stu-id="ae404-173">Start by reviewing the current Global policy to determine which setting you want to change.</span></span>

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

<span data-ttu-id="ae404-174">Em seguida, atualize a política Global conforme necessário.</span><span class="sxs-lookup"><span data-stu-id="ae404-174">Next, update the Global policy as needed.</span></span>  <span data-ttu-id="ae404-175">Você só precisa especificar valores para as configurações que deseja alterar.</span><span class="sxs-lookup"><span data-stu-id="ae404-175">You only need to specify values for the settings that you want to change.</span></span>

```powershell
Set-CsTeamsMessagingPolicy -Identity Global -AllowUserEditMessage $false
```

## <a name="assign-a-policy-to-individual-users"></a><span data-ttu-id="ae404-176">Atribuir uma política a usuários individuais</span><span class="sxs-lookup"><span data-stu-id="ae404-176">Assign a policy to individual users</span></span>

<span data-ttu-id="ae404-177">Siga estas etapas para atribuir uma política a um usuário individual ou a um pequeno número de usuários por vez.</span><span class="sxs-lookup"><span data-stu-id="ae404-177">Follow these steps to assign a policy to an individual user or to a small number of users at a time.</span></span>

### <a name="use-the-microsoft-teams-admin-center"></a><span data-ttu-id="ae404-178">Usar o Centro de administração do Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="ae404-178">Use the Microsoft Teams admin center</span></span>

<span data-ttu-id="ae404-179">Para atribuir uma política a um usuário:</span><span class="sxs-lookup"><span data-stu-id="ae404-179">To assign a policy to a user:</span></span>

1. <span data-ttu-id="ae404-180">Na navegação à esquerda do Centro de administração do Microsoft Teams, vá para **Usuários** e selecione o usuário.</span><span class="sxs-lookup"><span data-stu-id="ae404-180">In the left navigation of the Microsoft Teams admin center, go to **Users**, and then select the user.</span></span>
2. <span data-ttu-id="ae404-181">Selecione o usuário clicando à esquerda do nome de usuário e, em seguida, selecione **Editar configurações.**</span><span class="sxs-lookup"><span data-stu-id="ae404-181">Select the user by clicking to the left of the user name, and then select **Edit settings**.</span></span>
3. <span data-ttu-id="ae404-182">Selecione a política que você deseja atribuir e, em seguida, selecione **Aplicar.**</span><span class="sxs-lookup"><span data-stu-id="ae404-182">Select the policy you want to assign, and then select **Apply**.</span></span>

<span data-ttu-id="ae404-183">Ou você também pode fazer o seguinte:</span><span class="sxs-lookup"><span data-stu-id="ae404-183">Or, you can also do the following:</span></span>

1. <span data-ttu-id="ae404-184">Na navegação à esquerda do Centro de administração do Microsoft Teams, vá para a página de política.</span><span class="sxs-lookup"><span data-stu-id="ae404-184">In the left navigation of the Microsoft Teams admin center, go to the policy page.</span></span>
2. <span data-ttu-id="ae404-185">Selecione a política que você deseja atribuir clicando à esquerda do nome da política.</span><span class="sxs-lookup"><span data-stu-id="ae404-185">Select the policy you want to assign by clicking to the left of the policy name.</span></span>
3. <span data-ttu-id="ae404-186">Escolha **Gerenciar usuários**.</span><span class="sxs-lookup"><span data-stu-id="ae404-186">Select **Manage users**.</span></span>
4. <span data-ttu-id="ae404-187">No painel **Gerenciar usuários**, procure o usuário pelo nome de exibição ou pelo nome de usuário, escolha o nome e marque **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="ae404-187">In the **Manage users** pane, search for the user by display name or by user name, select the name, and then select **Add**.</span></span> <span data-ttu-id="ae404-188">Repita esta etapa para cada usuário que você deseja adicionar.</span><span class="sxs-lookup"><span data-stu-id="ae404-188">Repeat this step for each user that you want to add.</span></span>
5. <span data-ttu-id="ae404-189">Quando terminar de adicionar usuários, selecione **Aplicar.**</span><span class="sxs-lookup"><span data-stu-id="ae404-189">When you're finished adding users, select **Apply**.</span></span>

### <a name="use-powershell"></a><span data-ttu-id="ae404-190">Usar o PowerShell</span><span class="sxs-lookup"><span data-stu-id="ae404-190">Use PowerShell</span></span>

<span data-ttu-id="ae404-191">Cada tipo de política tem seu próprio conjunto de cmdlets para gereí-lo.</span><span class="sxs-lookup"><span data-stu-id="ae404-191">Each policy type has its own set of cmdlets for managing it.</span></span> <span data-ttu-id="ae404-192">Use o ```Grant-``` cmdlet para um determinado tipo de política para atribuir a política.</span><span class="sxs-lookup"><span data-stu-id="ae404-192">Use the ```Grant-``` cmdlet for a given policy type to assign the policy.</span></span> <span data-ttu-id="ae404-193">Por exemplo, use o ```Grant-CsTeamsMeetingPolicy``` cmdlet para atribuir uma política de reunião do Teams aos usuários.</span><span class="sxs-lookup"><span data-stu-id="ae404-193">For example, use the ```Grant-CsTeamsMeetingPolicy``` cmdlet to assign a Teams meeting policy to users.</span></span> <span data-ttu-id="ae404-194">Esses cmdlets estão incluídos no módulo powershell do Skype for Business Online e são documentados na referência [de cmdlet](https://docs.microsoft.com/powershell/skype/intro?view=skype-ps)do Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="ae404-194">These cmdlets are included in the Skype for Business Online PowerShell module and are documented in the [Skype for Business cmdlet reference](https://docs.microsoft.com/powershell/skype/intro?view=skype-ps).</span></span>

 <span data-ttu-id="ae404-195">Baixe e instale o módulo do [PowerShell](https://www.microsoft.com/download/details.aspx?id=39366) do Skype for Business Online (caso ainda não tenha feito isso) e execute o seguinte para se conectar ao Skype for Business Online e iniciar uma sessão.</span><span class="sxs-lookup"><span data-stu-id="ae404-195">Download and install the [Skype for Business Online PowerShell module](https://www.microsoft.com/download/details.aspx?id=39366) (if you haven't already), and then run the following to connect to Skype for Business Online and start a session.</span></span>

> [!NOTE]
> <span data-ttu-id="ae404-196">No momento, o Skype for Business Online Connector faz parte do módulo mais recente do PowerShell do Teams.</span><span class="sxs-lookup"><span data-stu-id="ae404-196">Skype for Business Online Connector is currently part of the latest Teams PowerShell module.</span></span>
>
> <span data-ttu-id="ae404-197">Se você estiver usando a versão pública mais recente do [Teams PowerShell,](https://www.powershellgallery.com/packages/MicrosoftTeams/)não será necessário instalar o Skype for Business Online Connector.</span><span class="sxs-lookup"><span data-stu-id="ae404-197">If you're using the latest [Teams PowerShell public release](https://www.powershellgallery.com/packages/MicrosoftTeams/), you don't need to install the Skype for Business Online Connector.</span></span>

```powershell
Import-Module -Name MicrosoftTeams
$Cred = Get-Credential
$CSSession = New-CsOnlineSession -Credential $Cred
Import-PSSession -Session $CSSession
```

<span data-ttu-id="ae404-198">Neste exemplo, atribuímos uma política de reunião do Teams chamada Política de Reunião do Aluno a um usuário chamado Reda.</span><span class="sxs-lookup"><span data-stu-id="ae404-198">In this example, we assign a Teams meeting policy named Student Meeting Policy to a user named Reda.</span></span>

```powershell
Grant-CsTeamsMeetingPolicy -Identity reda@contoso.com -PolicyName "Student Meeting Policy"
```

<span data-ttu-id="ae404-199">Para saber mais, leia [Gerenciar políticas por meio do PowerShell.](teams-powershell-managing-teams.md#manage-policies-via-powershell)</span><span class="sxs-lookup"><span data-stu-id="ae404-199">To learn more, read [Manage policies via PowerShell](teams-powershell-managing-teams.md#manage-policies-via-powershell).</span></span>

## <a name="assign-a-policy-to-a-group"></a><span data-ttu-id="ae404-200">Atribuir uma política a um grupo</span><span class="sxs-lookup"><span data-stu-id="ae404-200">Assign a policy to a group</span></span>

<span data-ttu-id="ae404-201">A atribuição de política a grupos permite atribuir uma política a um grupo de usuários, como um grupo de segurança ou uma lista de distribuição.</span><span class="sxs-lookup"><span data-stu-id="ae404-201">Policy assignment to groups lets you assign a policy to a group of users, such as a security group or distribution list.</span></span> <span data-ttu-id="ae404-202">As atribuições de política serão propagadas para os membros do grupo, de acordo com as regras de precedência.</span><span class="sxs-lookup"><span data-stu-id="ae404-202">The policy assignment is propagated to members of the group according to precedence rules.</span></span> <span data-ttu-id="ae404-203">À medida que os membros forem adicionados ou removidos de um grupo, as atribuições de política herdadas serão atualizadas.</span><span class="sxs-lookup"><span data-stu-id="ae404-203">As members are added to or removed from a group, their inherited policy assignments are updated accordingly.</span></span>

<span data-ttu-id="ae404-204">A atribuição de política a grupos é recomendada para grupos de até 50.000 usuários, mas também funcionará com grupos maiores.</span><span class="sxs-lookup"><span data-stu-id="ae404-204">Policy assignment to groups is recommended for groups of up to 50,000 users but it will also work with larger groups.</span></span>

<span data-ttu-id="ae404-205">Quando você atribui a política, ela é imediatamente atribuída ao grupo.</span><span class="sxs-lookup"><span data-stu-id="ae404-205">When you assign the policy, it's immediately assigned to the group.</span></span> <span data-ttu-id="ae404-206">No entanto, a propagação da atribuição de política aos membros do grupo é executada como uma operação em segundo plano e pode levar algum tempo, dependendo do tamanho do grupo.</span><span class="sxs-lookup"><span data-stu-id="ae404-206">However, the propagation of the policy assignment to members of the group is performed as a background operation and might take some time, depending on the size of the group.</span></span> <span data-ttu-id="ae404-207">O mesmo é verdadeiro quando uma política não é atribuída a um grupo ou quando os membros são adicionados ou removidos de um grupo.</span><span class="sxs-lookup"><span data-stu-id="ae404-207">The same is true when a policy is unassigned from a group, or when members are added to or removed from a group.</span></span>

<span data-ttu-id="ae404-208">As atribuições de política de grupo são propagadas apenas para usuários que são membros diretos do grupo.</span><span class="sxs-lookup"><span data-stu-id="ae404-208">Group policy assignments are only propagated to users who are direct members of the group.</span></span> <span data-ttu-id="ae404-209">As tarefas não são propagadas para membros de grupos aninhados.</span><span class="sxs-lookup"><span data-stu-id="ae404-209">The assignments aren't propagated to members of nested groups.</span></span>

### <a name="what-you-need-to-know-about-policy-assignment-to-groups"></a><span data-ttu-id="ae404-210">O que você precisa saber sobre a atribuição de política a grupos</span><span class="sxs-lookup"><span data-stu-id="ae404-210">What you need to know about policy assignment to groups</span></span>

<span data-ttu-id="ae404-211">Antes de começar, é importante entender as regras de precedência e a classificação da atribuição de grupo.</span><span class="sxs-lookup"><span data-stu-id="ae404-211">Before you get started, it's important to understand precedence rules and group assignment ranking.</span></span>

#### <a name="precedence-rules"></a><span data-ttu-id="ae404-212">Regras de precedência</span><span class="sxs-lookup"><span data-stu-id="ae404-212">Precedence rules</span></span>

<span data-ttu-id="ae404-213">Para um determinado tipo de política, a política efetiva de um usuário é determinada de acordo com o seguinte:</span><span class="sxs-lookup"><span data-stu-id="ae404-213">For a given policy type, a user's effective policy is determined according to the following:</span></span>

- <span data-ttu-id="ae404-214">Uma política atribuída diretamente a um usuário tem precedência sobre qualquer outra política do mesmo tipo atribuída a um grupo.</span><span class="sxs-lookup"><span data-stu-id="ae404-214">A policy that's directly assigned to a user takes precedence over any other policy of the same type that's assigned to a group.</span></span> <span data-ttu-id="ae404-215">Em outras palavras, se um usuário receber diretamente uma política de um determinado tipo, esse usuário não herdará uma política do mesmo tipo de um grupo.</span><span class="sxs-lookup"><span data-stu-id="ae404-215">In other words, if a user is directly assigned a policy of a given type, that user won't inherit a policy of the same type from a group.</span></span> <span data-ttu-id="ae404-216">Isso também significa que, se um usuário tiver uma política de um determinado tipo que foi atribuído diretamente a ele, será preciso remover essa política do usuário antes que ele possa herdar uma política do mesmo tipo de um grupo.</span><span class="sxs-lookup"><span data-stu-id="ae404-216">This also means that if a user has a policy of a given type that was directly assigned to them, you have to remove that policy from the user before they can inherit a policy of the same type from a group.</span></span>
- <span data-ttu-id="ae404-217">Se um usuário não tiver uma política atribuída diretamente a ele e for membro de dois ou mais grupos e cada grupo tiver uma política do mesmo tipo atribuída a ele, o usuário herdará a política da atribuição de grupo que tem a classificação mais alta.</span><span class="sxs-lookup"><span data-stu-id="ae404-217">If a user doesn't have a policy directly assigned to them and is a member of two or more groups and each group has a policy of the same type assigned to it, the user inherits the policy of the group assignment that has the highest ranking.</span></span>
- <span data-ttu-id="ae404-218">Se um usuário não for membro de nenhum grupo que recebe uma política, a política global (padrão de toda a organização) para esse tipo de política se aplicará ao usuário.</span><span class="sxs-lookup"><span data-stu-id="ae404-218">If a user isn't a member of any groups that are assigned a policy, the global (Org-wide default) policy for that policy type applies to the user.</span></span>

<span data-ttu-id="ae404-219">A política efetiva de um usuário é atualizada de acordo com estas regras:</span><span class="sxs-lookup"><span data-stu-id="ae404-219">A user's effective policy is updated according to these rules:</span></span>

- <span data-ttu-id="ae404-220">quando um usuário é adicionado ou removido de um grupo que recebe uma política.</span><span class="sxs-lookup"><span data-stu-id="ae404-220">when a user is added to or removed from a group that's assigned a policy.</span></span>
- <span data-ttu-id="ae404-221">uma política não é atribuída a partir de um grupo.</span><span class="sxs-lookup"><span data-stu-id="ae404-221">a policy is unassigned from a group.</span></span>
- <span data-ttu-id="ae404-222">uma política atribuída diretamente ao usuário é removida.</span><span class="sxs-lookup"><span data-stu-id="ae404-222">a policy that's directly assigned to the user is removed.</span></span>

#### <a name="group-assignment-ranking"></a><span data-ttu-id="ae404-223">Classificação de atribuições de grupo</span><span class="sxs-lookup"><span data-stu-id="ae404-223">Group assignment ranking</span></span>

<span data-ttu-id="ae404-224">Ao atribuir uma política a um grupo, você especifica uma classificação para a atribuição de grupo.</span><span class="sxs-lookup"><span data-stu-id="ae404-224">When you assign a policy to a group, you specify a ranking for the group assignment.</span></span> <span data-ttu-id="ae404-225">Isso é usado para determinar qual política um usuário deve herdar como sua política efetiva se o usuário for membro de dois ou mais grupos e cada grupo receber uma política do mesmo tipo.</span><span class="sxs-lookup"><span data-stu-id="ae404-225">This is used to determine which policy a user should inherit as their effective policy if the user is a member of two or more groups and each group is assigned a policy of the same type.</span></span>

<span data-ttu-id="ae404-226">A classificação da atribuição de grupo é relativa a outras atribuições de grupo do mesmo tipo.</span><span class="sxs-lookup"><span data-stu-id="ae404-226">The group assignment ranking is relative to other group assignments of the same type.</span></span> <span data-ttu-id="ae404-227">Por exemplo, se você estiver atribuindo uma política de chamada a dois grupos, de definir a classificação de uma tarefa como 1 e a outra para 2, sendo 1 a classificação mais alta.</span><span class="sxs-lookup"><span data-stu-id="ae404-227">For example, if you're assigning a calling policy to two groups, set the ranking of one assignment to 1 and the other to 2, with 1 being the highest ranking.</span></span> <span data-ttu-id="ae404-228">A classificação da atribuição de grupo indica qual associação ao grupo é mais importante ou mais relevante do que outras associações de grupo em relação à herança.</span><span class="sxs-lookup"><span data-stu-id="ae404-228">The group assignment ranking indicates which group membership is more important or more relevant than other group memberships with regards to inheritance.</span></span>

<span data-ttu-id="ae404-229">Por exemplo, você tem dois grupos: Funcionários da Loja e Gerentes de Loja.</span><span class="sxs-lookup"><span data-stu-id="ae404-229">Say, for example, you have two groups, Store Employees and Store Managers.</span></span> <span data-ttu-id="ae404-230">Os dois grupos têm uma política de chamada do Teams, Política de Chamada de Funcionários da Store e Política de Chamada de Gerentes de Loja, respectivamente.</span><span class="sxs-lookup"><span data-stu-id="ae404-230">Both groups are assigned a Teams calling policy, Store Employees Calling Policy and Store Managers Calling Policy, respectively.</span></span> <span data-ttu-id="ae404-231">Para um gerente de loja que está em ambos os grupos, sua função de gerente é mais relevante do que sua função como funcionário, portanto, a política de chamada atribuída ao grupo Gerentes de Loja deve ter uma classificação mais alta.</span><span class="sxs-lookup"><span data-stu-id="ae404-231">For a store manager who is in both groups, their role as a manager is more relevant than their role as an employee, so the calling policy that's assigned to the Store Managers group should have a higher ranking.</span></span>

|<span data-ttu-id="ae404-232">Grupo</span><span class="sxs-lookup"><span data-stu-id="ae404-232">Group</span></span> |<span data-ttu-id="ae404-233">Nome da política de chamada do Teams</span><span class="sxs-lookup"><span data-stu-id="ae404-233">Teams calling policy name</span></span>  |<span data-ttu-id="ae404-234">Classificação</span><span class="sxs-lookup"><span data-stu-id="ae404-234">Rank</span></span>|
|---------|---------|---|
|<span data-ttu-id="ae404-235">Gerentes de Loja</span><span class="sxs-lookup"><span data-stu-id="ae404-235">Store Managers</span></span>   |<span data-ttu-id="ae404-236">Política de Chamada de Gerentes de Loja</span><span class="sxs-lookup"><span data-stu-id="ae404-236">Store Managers Calling Policy</span></span>         |<span data-ttu-id="ae404-237">1</span><span class="sxs-lookup"><span data-stu-id="ae404-237">1</span></span>|
|<span data-ttu-id="ae404-238">Armazenar Funcionários</span><span class="sxs-lookup"><span data-stu-id="ae404-238">Store Employees</span></span>    |<span data-ttu-id="ae404-239">Política de Chamada de Funcionários da Store</span><span class="sxs-lookup"><span data-stu-id="ae404-239">Store Employees Calling Policy</span></span>      |<span data-ttu-id="ae404-240">2</span><span class="sxs-lookup"><span data-stu-id="ae404-240">2</span></span>|

<span data-ttu-id="ae404-241">Se você não especificar uma classificação, a atribuição de política será dada na classificação mais baixa.</span><span class="sxs-lookup"><span data-stu-id="ae404-241">If you don't specify a ranking, the policy assignment is given the lowest ranking.</span></span>

### <a name="in-the-teams-admin-center"></a><span data-ttu-id="ae404-242">No Centro de administração do Teams</span><span class="sxs-lookup"><span data-stu-id="ae404-242">In the Teams admin center</span></span>

> [!NOTE]
> <span data-ttu-id="ae404-243">Atualmente, a atribuição de política a grupos que usam o Centro de administração do Microsoft Teams só está disponível para a política de chamada do Teams, a política de parque de chamada do Teams, a política de eventos ao vivo do Teams, a política de reunião do Teams e a política de mensagens do Teams.</span><span class="sxs-lookup"><span data-stu-id="ae404-243">Currently, policy assignment to groups using the Microsoft Teams admin center is only available for Teams calling policy, Teams call park policy, Teams policy, Teams live events policy, Teams meeting policy, and Teams messaging policy.</span></span> <span data-ttu-id="ae404-244">Para outros tipos de política, use o PowerShell.</span><span class="sxs-lookup"><span data-stu-id="ae404-244">For other policy types, use PowerShell.</span></span>

1. <span data-ttu-id="ae404-245">Na navegação à esquerda do Centro de administração do Microsoft Teams, vá para a página de tipo de política.</span><span class="sxs-lookup"><span data-stu-id="ae404-245">In the left navigation of the Microsoft Teams admin center, go to the policy type page.</span></span> <span data-ttu-id="ae404-246">Por exemplo, vá para **políticas de Reunião** de  >  **Reuniões.**</span><span class="sxs-lookup"><span data-stu-id="ae404-246">For example, go to **Meetings** > **Meeting policies**.</span></span>
2. <span data-ttu-id="ae404-247">Selecione a **guia de atribuição de política de** grupo.</span><span class="sxs-lookup"><span data-stu-id="ae404-247">Select the **Group policy assignment** tab.</span></span>
3. <span data-ttu-id="ae404-248">Selecione **Adicionar grupo** e, no painel Atribuir **política** ao grupo, faça o seguinte:</span><span class="sxs-lookup"><span data-stu-id="ae404-248">Select **Add group**, and then in the **Assign policy to group** pane, do the following:</span></span>
    1. <span data-ttu-id="ae404-249">Pesquise e adicione o grupo ao que você deseja atribuir a política.</span><span class="sxs-lookup"><span data-stu-id="ae404-249">Search for and add the group you want to assign the policy to.</span></span>
    2. <span data-ttu-id="ae404-250">De definir a classificação para a atribuição de grupo.</span><span class="sxs-lookup"><span data-stu-id="ae404-250">Set the ranking for the group assignment.</span></span>
    3. <span data-ttu-id="ae404-251">Selecione a política que você deseja atribuir.</span><span class="sxs-lookup"><span data-stu-id="ae404-251">Select the policy that you want to assign.</span></span>
    4. <span data-ttu-id="ae404-252">Selecione **Aplicar.**</span><span class="sxs-lookup"><span data-stu-id="ae404-252">Select **Apply**.</span></span>

<span data-ttu-id="ae404-253">Para remover uma atribuição  de política de grupo, na guia de atribuição de política de grupo da página de política, selecione a atribuição de grupo e, em seguida, **selecione Remover.**</span><span class="sxs-lookup"><span data-stu-id="ae404-253">To remove a group policy assignment, on the **Group policy assignment** tab of the policy page, select the group assignment, and then select **Remove**.</span></span>

<span data-ttu-id="ae404-254">Para alterar a classificação de uma atribuição de grupo, primeiro é preciso remover a atribuição de política de grupo.</span><span class="sxs-lookup"><span data-stu-id="ae404-254">To change the ranking of a group assignment, you have to first remove the group policy assignment.</span></span> <span data-ttu-id="ae404-255">Em seguida, siga as etapas acima para atribuir a política a um grupo.</span><span class="sxs-lookup"><span data-stu-id="ae404-255">Then, follow the steps above to assign the policy to a group.</span></span>

### <a name="use-the-powershell-option"></a><span data-ttu-id="ae404-256">Usar a opção do PowerShell</span><span class="sxs-lookup"><span data-stu-id="ae404-256">Use the PowerShell option</span></span>

> [!NOTE]
> <span data-ttu-id="ae404-257">Atualmente, a atribuição de política a grupos que usam o PowerShell não está disponível para todos os tipos de política do Teams.</span><span class="sxs-lookup"><span data-stu-id="ae404-257">Currently, policy assignment to groups using PowerShell isn't available for all Teams policy types.</span></span> <span data-ttu-id="ae404-258">Consulte [New-CsGroupPolicyAssignment para](https://docs.microsoft.com/powershell/module/teams/new-csgrouppolicyassignment) a lista de tipos de política com suporte.</span><span class="sxs-lookup"><span data-stu-id="ae404-258">See [New-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/new-csgrouppolicyassignment) for the list of supported policy types.</span></span>

#### <a name="install-and-connect-to-the-microsoft-teams-powershell-module"></a><span data-ttu-id="ae404-259">Instalar e conectar-se ao módulo do PowerShell do Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="ae404-259">Install and connect to the Microsoft Teams PowerShell module</span></span>

<span data-ttu-id="ae404-260">Para obter orientações passo a passo, consulte [Instalar o PowerShell do Teams.](teams-powershell-install.md)</span><span class="sxs-lookup"><span data-stu-id="ae404-260">For step-by-step guidance, see [Install Teams PowerShell](teams-powershell-install.md).</span></span>

#### <a name="assign-a-policy-to-a-group-of-users"></a><span data-ttu-id="ae404-261">Atribuir uma política a um grupo de usuários</span><span class="sxs-lookup"><span data-stu-id="ae404-261">Assign a policy to a group of users</span></span>

<span data-ttu-id="ae404-262">Use o cmdlet [New-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/new-csgrouppolicyassignment) para atribuir uma política a um grupo.</span><span class="sxs-lookup"><span data-stu-id="ae404-262">Use the [New-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/new-csgrouppolicyassignment) cmdlet to assign a policy to a group.</span></span> <span data-ttu-id="ae404-263">Você pode especificar um grupo usando a ID do objeto, o endereço SIP ou o endereço de email.</span><span class="sxs-lookup"><span data-stu-id="ae404-263">You can specify a group by using the object ID, SIP address, or email address.</span></span>

<span data-ttu-id="ae404-264">Neste exemplo, atribuímos uma política de reunião do Teams chamada Política de Reunião de Gerentes de Varejo a um grupo com uma classificação de atribuição de 1.</span><span class="sxs-lookup"><span data-stu-id="ae404-264">In this example, we assign a Teams meeting policy named Retail Managers Meeting Policy to a group with an assignment ranking of 1.</span></span>

```powershell
New-CsGroupPolicyAssignment -GroupId d8ebfa45-0f28-4d2d-9bcc-b158a49e2d17 -PolicyType TeamsMeetingPolicy -PolicyName "Retail Managers Meeting Policy" -Rank 1
```

#### <a name="get-policy-assignments-for-a-group"></a><span data-ttu-id="ae404-265">Obter atribuições de política para um grupo</span><span class="sxs-lookup"><span data-stu-id="ae404-265">Get policy assignments for a group</span></span>

<span data-ttu-id="ae404-266">Use o cmdlet [Get-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/get-csgrouppolicyassignment) para obter todas as políticas atribuídas a um grupo.</span><span class="sxs-lookup"><span data-stu-id="ae404-266">Use the [Get-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/get-csgrouppolicyassignment) cmdlet to get all policies assigned to a group.</span></span> <span data-ttu-id="ae404-267">Observe que os grupos estão sempre listados por sua ID de grupo, mesmo que seu endereço sip ou endereço de email foi usado para atribuir a política.</span><span class="sxs-lookup"><span data-stu-id="ae404-267">Note that groups are always listed by their group ID even if its SIP address or email address was used to assign the policy.</span></span>

<span data-ttu-id="ae404-268">Neste exemplo, recuperamos todas as políticas atribuídas a um grupo específico.</span><span class="sxs-lookup"><span data-stu-id="ae404-268">In this example, we retrieve all policies assigned to a specific group.</span></span>

```powershell
Get-CsGroupPolicyAssignment -GroupId e050ce51-54bc-45b7-b3e6-c00343d31274
```

<span data-ttu-id="ae404-269">Neste exemplo, retornamos todos os grupos que têm uma política de reunião do Teams atribuída.</span><span class="sxs-lookup"><span data-stu-id="ae404-269">In this example, we return all groups that are assigned a Teams meeting policy.</span></span>

```powershell
Get-CsGroupPolicyAssignment -PolicyType TeamsMeetingPolicy
```

#### <a name="remove-a-policy-from-a-group"></a><span data-ttu-id="ae404-270">Remover uma política de um grupo</span><span class="sxs-lookup"><span data-stu-id="ae404-270">Remove a policy from a group</span></span>

<span data-ttu-id="ae404-271">Use o cmdlet [Remove-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/remove-csgrouppolicyassignment) para remover uma política de um grupo.</span><span class="sxs-lookup"><span data-stu-id="ae404-271">Use the [Remove-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/remove-csgrouppolicyassignment) cmdlet to remove a policy from a group.</span></span> <span data-ttu-id="ae404-272">Quando você remove uma política de um grupo, as prioridades de outras políticas do mesmo tipo atribuídas a esse grupo, e que têm uma classificação inferior, são atualizadas.</span><span class="sxs-lookup"><span data-stu-id="ae404-272">When you remove a policy from a group, the priorities of other policies of the same type assigned to that group, and that have a lower ranking, are updated.</span></span> <span data-ttu-id="ae404-273">Por exemplo, se você remover uma política que tenha uma classificação de 2, as políticas com classificação 3 e 4 serão atualizadas para refletir sua nova classificação.</span><span class="sxs-lookup"><span data-stu-id="ae404-273">For example, if you remove a policy that has a ranking of 2, policies that have a ranking of 3 and 4 are updated to reflect their new ranking.</span></span> <span data-ttu-id="ae404-274">As duas tabelas a seguir mostram este exemplo.</span><span class="sxs-lookup"><span data-stu-id="ae404-274">The following two tables show this example.</span></span>

<span data-ttu-id="ae404-275">Aqui está uma lista das atribuições de política e prioridades de uma política de reunião do Teams.</span><span class="sxs-lookup"><span data-stu-id="ae404-275">Here's a list of the policy assignments and priorities for a Teams meeting policy.</span></span>

|<span data-ttu-id="ae404-276">Nome do grupo</span><span class="sxs-lookup"><span data-stu-id="ae404-276">Group name</span></span>  |<span data-ttu-id="ae404-277">Nome da política</span><span class="sxs-lookup"><span data-stu-id="ae404-277">Policy name</span></span>  |<span data-ttu-id="ae404-278">Classificação</span><span class="sxs-lookup"><span data-stu-id="ae404-278">Rank</span></span>|
|---------|---------|---------|
|<span data-ttu-id="ae404-279">Vendas</span><span class="sxs-lookup"><span data-stu-id="ae404-279">Sales</span></span>    |<span data-ttu-id="ae404-280">Política de vendas</span><span class="sxs-lookup"><span data-stu-id="ae404-280">Sales policy</span></span>       | <span data-ttu-id="ae404-281">1</span><span class="sxs-lookup"><span data-stu-id="ae404-281">1</span></span>        |
|<span data-ttu-id="ae404-282">Região Oeste</span><span class="sxs-lookup"><span data-stu-id="ae404-282">West Region</span></span>     |<span data-ttu-id="ae404-283">Política da Região Oeste</span><span class="sxs-lookup"><span data-stu-id="ae404-283">West Region policy</span></span>         |<span data-ttu-id="ae404-284">2</span><span class="sxs-lookup"><span data-stu-id="ae404-284">2</span></span>         |
|<span data-ttu-id="ae404-285">Divisão</span><span class="sxs-lookup"><span data-stu-id="ae404-285">Division</span></span>    |<span data-ttu-id="ae404-286">Política de divisão</span><span class="sxs-lookup"><span data-stu-id="ae404-286">Division policy</span></span>         |<span data-ttu-id="ae404-287">3</span><span class="sxs-lookup"><span data-stu-id="ae404-287">3</span></span>         |
|<span data-ttu-id="ae404-288">Subsidiária</span><span class="sxs-lookup"><span data-stu-id="ae404-288">Subsidiary</span></span>   |<span data-ttu-id="ae404-289">Política de subsidiária</span><span class="sxs-lookup"><span data-stu-id="ae404-289">Subsidiary policy</span></span>        |<span data-ttu-id="ae404-290">4</span><span class="sxs-lookup"><span data-stu-id="ae404-290">4</span></span>         |

<span data-ttu-id="ae404-291">Se removermos a política da Região Oeste do grupo Região Oeste, as atribuições e prioridades da política serão atualizadas da seguinte forma.</span><span class="sxs-lookup"><span data-stu-id="ae404-291">If we remove the West Region policy from the West Region group, the policy assignments and priorities are updated as follows.</span></span>

|<span data-ttu-id="ae404-292">Nome do grupo</span><span class="sxs-lookup"><span data-stu-id="ae404-292">Group name</span></span>  |<span data-ttu-id="ae404-293">Nome da política</span><span class="sxs-lookup"><span data-stu-id="ae404-293">Policy name</span></span>  |<span data-ttu-id="ae404-294">Classificação</span><span class="sxs-lookup"><span data-stu-id="ae404-294">Rank</span></span>|
|---------|---------|---------|
|<span data-ttu-id="ae404-295">Vendas</span><span class="sxs-lookup"><span data-stu-id="ae404-295">Sales</span></span>    |<span data-ttu-id="ae404-296">Política de vendas</span><span class="sxs-lookup"><span data-stu-id="ae404-296">Sales policy</span></span>       | <span data-ttu-id="ae404-297">1</span><span class="sxs-lookup"><span data-stu-id="ae404-297">1</span></span>        |
|<span data-ttu-id="ae404-298">Divisão</span><span class="sxs-lookup"><span data-stu-id="ae404-298">Division</span></span>    |<span data-ttu-id="ae404-299">Política de divisão</span><span class="sxs-lookup"><span data-stu-id="ae404-299">Division policy</span></span>         |<span data-ttu-id="ae404-300">2</span><span class="sxs-lookup"><span data-stu-id="ae404-300">2</span></span>         |
|<span data-ttu-id="ae404-301">Subsidiária</span><span class="sxs-lookup"><span data-stu-id="ae404-301">Subsidiary</span></span>   |<span data-ttu-id="ae404-302">Política de subsidiária</span><span class="sxs-lookup"><span data-stu-id="ae404-302">Subsidiary policy</span></span>        |<span data-ttu-id="ae404-303">3</span><span class="sxs-lookup"><span data-stu-id="ae404-303">3</span></span>        |

<span data-ttu-id="ae404-304">Neste exemplo, removemos a política de reunião do Teams de um grupo.</span><span class="sxs-lookup"><span data-stu-id="ae404-304">In this example, we remove the Teams meeting policy from a group.</span></span>

```powershell
Remove-CsGroupPolicyAssignment -PolicyType TeamsMeetingPolicy -GroupId f985e013-0826-40bb-8c94-e5f367076044
```

#### <a name="change-a-policy-assignment-for-a-group"></a><span data-ttu-id="ae404-305">Alterar uma atribuição de política para um grupo</span><span class="sxs-lookup"><span data-stu-id="ae404-305">Change a policy assignment for a group</span></span>

> [!NOTE]
> <span data-ttu-id="ae404-306">O cmdlet [Set-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/set-csgrouppolicyassignment) estará disponível em breve.</span><span class="sxs-lookup"><span data-stu-id="ae404-306">The [Set-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/set-csgrouppolicyassignment) cmdlet will be available soon.</span></span> <span data-ttu-id="ae404-307">Enquanto isso, para alterar uma atribuição de política de grupo, você pode remover a atribuição de política atual do grupo e adicionar uma nova atribuição de política.</span><span class="sxs-lookup"><span data-stu-id="ae404-307">In the meantime, to change a group policy assignment, you can remove the current policy assignment from the group, and then add a new policy assignment.</span></span>

<span data-ttu-id="ae404-308">Depois de atribuir uma política a um grupo, você pode usar o cmdlet [Set-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/set-csgrouppolicyassignment) para alterar a atribuição de política desse grupo da seguinte forma:</span><span class="sxs-lookup"><span data-stu-id="ae404-308">After you assign a policy to a group, you can use the [Set-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/set-csgrouppolicyassignment) cmdlet to change that group's policy assignment as follows:</span></span>

- <span data-ttu-id="ae404-309">Alterar a classificação</span><span class="sxs-lookup"><span data-stu-id="ae404-309">Change the ranking</span></span>
- <span data-ttu-id="ae404-310">Alterar a política de um determinado tipo de política</span><span class="sxs-lookup"><span data-stu-id="ae404-310">Change the policy of a given policy type</span></span>
- <span data-ttu-id="ae404-311">Alterar a política de um determinado tipo de política e a classificação</span><span class="sxs-lookup"><span data-stu-id="ae404-311">Change the policy of a given policy type and the ranking</span></span>

<span data-ttu-id="ae404-312">Neste exemplo, alteramos a política de parque de chamadas do Teams de um grupo para uma política chamada SupportCallPark e a classificação da tarefa para 3.</span><span class="sxs-lookup"><span data-stu-id="ae404-312">In this example, we change a group's Teams call park policy to a policy named SupportCallPark and the assignment ranking to 3.</span></span>

```powershell
Set-CsGroupPolicyAssignment -GroupId 566b8d39-5c5c-4aaa-bc07-4f36278a1b38 -PolicyType TeamsMeetingPolicy -PolicyName SupportCallPark -Rank 3
```

#### <a name="change-the-effective-policy-for-a-user"></a><span data-ttu-id="ae404-313">Alterar a política efetiva de um usuário</span><span class="sxs-lookup"><span data-stu-id="ae404-313">Change the effective policy for a user</span></span>

<span data-ttu-id="ae404-314">Veja um exemplo de como alterar a política efetiva para um usuário que recebe uma política diretamente.</span><span class="sxs-lookup"><span data-stu-id="ae404-314">Here's an example of how to change the effective policy for a user who is directly assigned a policy.</span></span>

<span data-ttu-id="ae404-315">Em primeiro lugar, usamos o cmdlet [Get-CsUserPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/get-csuserpolicyassignment) juntamente com o parâmetro para obter detalhes das políticas de transmissão de reunião do Teams associadas ```PolicySource``` ao usuário.</span><span class="sxs-lookup"><span data-stu-id="ae404-315">First, we use the [Get-CsUserPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/get-csuserpolicyassignment) cmdlet together with the ```PolicySource``` parameter to get details of the Teams meeting broadcast policies associated with the user.</span></span>

```powershell
Get-CsUserPolicyAssignment -Identity daniel@contoso.com -PolicyType TeamsMeetingBroadcastPolicy | select -ExpandProperty PolicySource
```

<span data-ttu-id="ae404-316">A saída mostra que o usuário recebeu diretamente uma política de transmissão de reunião do Teams chamada Eventos de Funcionários, que tem precedência sobre a política chamada Eventos Ao Vivo do Fornecedor atribuída a um grupo ao qual o usuário pertence.</span><span class="sxs-lookup"><span data-stu-id="ae404-316">The output shows that the user was directly assigned a Teams meeting broadcast policy named Employee Events, which takes precedence over the policy named Vendor Live Events that's assigned to a group the user belongs to.</span></span>

```console
AssignmentType PolicyName         Reference
-------------- ----------         ---------
Direct         Employee Events
Group          Vendor Live Events 566b8d39-5c5c-4aaa-bc07-4f36278a1b38
```

<span data-ttu-id="ae404-317">Agora, removemos a política Eventos de Funcionários do usuário.</span><span class="sxs-lookup"><span data-stu-id="ae404-317">Now, we remove the Employee Events policy from the user.</span></span> <span data-ttu-id="ae404-318">Isso significa que o usuário não tem mais uma política de transmissão de reunião do Teams atribuída diretamente a ele e herdará a política de Eventos Ao Vivo do Fornecedor atribuída ao grupo ao que o usuário pertence.</span><span class="sxs-lookup"><span data-stu-id="ae404-318">This means that the user no longer has a Teams meeting broadcast policy directly assigned to them and will inherit the Vendor Live Events policy that's assigned to the group the user belongs to.</span></span>

<span data-ttu-id="ae404-319">Use o cmdlet a seguir no módulo do PowerShell do Skype for Business para fazer isso.</span><span class="sxs-lookup"><span data-stu-id="ae404-319">Use the following cmdlet in the Skype for Business PowerShell module to do this.</span></span>

```powershell
Grant-CsTeamsMeetingBroadcastPolicy -Identity daniel@contoso.com -PolicyName $null
```

<span data-ttu-id="ae404-320">Use o cmdlet a seguir no módulo do PowerShell do Teams para fazer isso em escala, embora seja uma atribuição de política em lotes, onde o $users é uma lista de usuários que você especificar.</span><span class="sxs-lookup"><span data-stu-id="ae404-320">Use following cmdlet in the Teams PowerShell module to do this at scale though a batch policy assignment, where $users is a list of users that you specify.</span></span>

```powershell
New-CsBatchPolicyAssignmentOperation -OperationName "Assigning null at bulk" -PolicyType TeamsMeetingBroadcastPolicy -PolicyName $null -Identity $users  
```

## <a name="assign-a-policy-to-a-batch-of-users"></a><span data-ttu-id="ae404-321">Atribuir uma política a um lote de usuários</span><span class="sxs-lookup"><span data-stu-id="ae404-321">Assign a policy to a batch of users</span></span>

### <a name="use-the-admin-center"></a><span data-ttu-id="ae404-322">Usar o centro de administração</span><span class="sxs-lookup"><span data-stu-id="ae404-322">Use the admin center</span></span>

<span data-ttu-id="ae404-323">Para atribuir uma política aos usuários em massa:</span><span class="sxs-lookup"><span data-stu-id="ae404-323">To assign a policy to users in bulk:</span></span>

1. <span data-ttu-id="ae404-324">Na navegação à esquerda do Centro de administração do Microsoft Teams, selecione **Usuários.**</span><span class="sxs-lookup"><span data-stu-id="ae404-324">In the left navigation of the Microsoft Teams admin center, select **Users**.</span></span>
2. <span data-ttu-id="ae404-325">Pesquise os usuários aos que você deseja atribuir a política ou filtre o exibição para mostrar os usuários que você deseja.</span><span class="sxs-lookup"><span data-stu-id="ae404-325">Search for the users you want to assign the policy to or filter the view to show the users you want.</span></span>
3. <span data-ttu-id="ae404-326">Na coluna **&#x2713;** (marca de seleção), selecione os usuários.</span><span class="sxs-lookup"><span data-stu-id="ae404-326">In the **&#x2713;** (check mark) column, select the users.</span></span> <span data-ttu-id="ae404-327">Para selecionar todos os usuários, clique na (marca de seleção) &#x2713; na parte superior da tabela.</span><span class="sxs-lookup"><span data-stu-id="ae404-327">To select all users, click the &#x2713; (check mark) at the top of the table.</span></span>
4. <span data-ttu-id="ae404-328">Selecione **Editar configurações,** faça as alterações que você deseja e selecione **Aplicar.**</span><span class="sxs-lookup"><span data-stu-id="ae404-328">Select **Edit settings**, make the changes that you want, and then select **Apply**.</span></span>

<span data-ttu-id="ae404-329">Para exibir o status da atribuição de política, na  faixa exibida  na parte superior da página Usuários depois que você selecionar Aplicar para enviar sua atribuição de política, selecione Log **de atividades.**</span><span class="sxs-lookup"><span data-stu-id="ae404-329">To view the status of your policy assignment, in the banner that appears at the top of the **Users** page after you select **Apply** to submit your policy assignment, select **Activity log**.</span></span> <span data-ttu-id="ae404-330">Ou, na navegação à esquerda do Centro de administração do Microsoft Teams, vá para **Painel** e, em log de **atividades,** selecione **Exibir detalhes.**</span><span class="sxs-lookup"><span data-stu-id="ae404-330">Or, in the left navigation of the Microsoft Teams admin center, go to **Dashboard**, and then under **Activity log**, select **View details**.</span></span> <span data-ttu-id="ae404-331">O log de atividades mostra atribuições de política para lotes de mais de 20 usuários por meio do Centro de administração do Microsoft Teams dos últimos 30 dias.</span><span class="sxs-lookup"><span data-stu-id="ae404-331">The Activity log shows policy assignments to batches of more than 20 users through the Microsoft Teams admin center from the last 30 days.</span></span> <span data-ttu-id="ae404-332">Para saber mais, consulte [Exibir suas atribuições de política no log de atividades.](activity-log.md)</span><span class="sxs-lookup"><span data-stu-id="ae404-332">To learn more, see [View your policy assignments in the Activity log](activity-log.md).</span></span>

### <a name="use-powershell-method"></a><span data-ttu-id="ae404-333">Usar o método do PowerShell</span><span class="sxs-lookup"><span data-stu-id="ae404-333">Use PowerShell method</span></span>

> [!NOTE]
> <span data-ttu-id="ae404-334">Atualmente, a atribuição de política em lotes usando o PowerShell não está disponível para todos os tipos de política do Teams.</span><span class="sxs-lookup"><span data-stu-id="ae404-334">Currently, batch policy assignment using PowerShell isn't available for all Teams policy types.</span></span> <span data-ttu-id="ae404-335">Consulte [New-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation) para ver a lista de tipos de política com suporte.</span><span class="sxs-lookup"><span data-stu-id="ae404-335">See [New-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation) for the list of supported policy types.</span></span>

<span data-ttu-id="ae404-336">Com a atribuição de política em lote, você pode atribuir uma política a grandes conjuntos de usuários por vez sem precisar usar um script.</span><span class="sxs-lookup"><span data-stu-id="ae404-336">With batch policy assignment, you can assign a policy to large sets of users at a time without having to use a script.</span></span> <span data-ttu-id="ae404-337">Use o cmdlet [New-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation) para enviar um lote de usuários e a política que você deseja atribuir.</span><span class="sxs-lookup"><span data-stu-id="ae404-337">You use the [New-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation) cmdlet to submit a batch of users and the policy that you want to assign.</span></span> <span data-ttu-id="ae404-338">As atribuições são processadas como uma operação de plano de fundo e uma ID de operação é gerada para cada lote.</span><span class="sxs-lookup"><span data-stu-id="ae404-338">The assignments are processed as a background operation and an operation ID is generated for each batch.</span></span> <span data-ttu-id="ae404-339">Em seguida, você pode usar o cmdlet [Get-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/get-csbatchpolicyassignmentoperation) para controlar o progresso e o status das atribuições em um lote.</span><span class="sxs-lookup"><span data-stu-id="ae404-339">You can then use the [Get-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/get-csbatchpolicyassignmentoperation) cmdlet to track the progress and status of the assignments in a batch.</span></span>

<span data-ttu-id="ae404-340">Especifique os usuários por sua ID de objeto ou endereço SIP (Session Initiation Protocol).</span><span class="sxs-lookup"><span data-stu-id="ae404-340">Specify users by their object ID or Session Initiation Protocol (SIP) address.</span></span> <span data-ttu-id="ae404-341">O endereço SIP de um usuário geralmente tem o mesmo valor que o nome de usuário principal (UPN) ou o endereço de email, mas isso não é necessário.</span><span class="sxs-lookup"><span data-stu-id="ae404-341">A user's SIP address often has the same value as the User Principal Name (UPN) or email address, but this is not required.</span></span> <span data-ttu-id="ae404-342">Se um usuário for especificado usando seu UPN ou email, mas tiver um valor diferente do endereço SIP, a atribuição de política falhará para o usuário.</span><span class="sxs-lookup"><span data-stu-id="ae404-342">If a user is specified using their UPN or email, but it has a different value than their SIP address, then policy assignment will fail for the user.</span></span> <span data-ttu-id="ae404-343">Se um lote incluir usuários duplicados, as duplicatas serão removidas do lote antes do processamento e o status só será fornecido para os usuários exclusivos restantes no lote.</span><span class="sxs-lookup"><span data-stu-id="ae404-343">If a batch includes duplicate users, the duplicates will be removed from the batch before processing and status will only be provided for the unique users remaining in the batch.</span></span>

<span data-ttu-id="ae404-344">Um lote pode conter até 5.000 usuários.</span><span class="sxs-lookup"><span data-stu-id="ae404-344">A batch can contain up to 5,000 users.</span></span> <span data-ttu-id="ae404-345">Para obter melhores resultados, não envie mais do que alguns lotes de cada vez.</span><span class="sxs-lookup"><span data-stu-id="ae404-345">For best results, don't submit more than a few batches at a time.</span></span> <span data-ttu-id="ae404-346">Permita que os lotes concluam o processamento antes de enviar mais lotes.</span><span class="sxs-lookup"><span data-stu-id="ae404-346">Allow batches to complete processing before submitting more batches.</span></span>

#### <a name="install-and-connect-to-the-teams-powershell-module"></a><span data-ttu-id="ae404-347">Instalar e conectar-se ao módulo do PowerShell do Teams</span><span class="sxs-lookup"><span data-stu-id="ae404-347">Install and connect to the Teams PowerShell module</span></span>

<span data-ttu-id="ae404-348">Execute o seguinte para instalar o módulo [do PowerShell do Microsoft Teams.](https://www.powershellgallery.com/packages/MicrosoftTeams)</span><span class="sxs-lookup"><span data-stu-id="ae404-348">Run the following to install the [Microsoft Teams PowerShell module](https://www.powershellgallery.com/packages/MicrosoftTeams).</span></span> <span data-ttu-id="ae404-349">Instale a versão 1.0.5 ou posterior.</span><span class="sxs-lookup"><span data-stu-id="ae404-349">Make sure you install version 1.0.5 or later.</span></span>

```powershell
Install-Module -Name MicrosoftTeams
```

<span data-ttu-id="ae404-350">Execute o seguinte para se conectar ao Teams e iniciar uma sessão.</span><span class="sxs-lookup"><span data-stu-id="ae404-350">Run the following to connect to Teams and start a session.</span></span>

```powershell
Connect-MicrosoftTeams
```

<span data-ttu-id="ae404-351">Quando for solicitado, entre usando suas credenciais de administrador.</span><span class="sxs-lookup"><span data-stu-id="ae404-351">When you're prompted, sign in using your admin credentials.</span></span>

#### <a name="install-and-connect-to-the-azure-ad-powershell-for-graph-module-optional"></a><span data-ttu-id="ae404-352">Instalar e conectar-se ao módulo do PowerShell do Azure AD para Graph (opcional)</span><span class="sxs-lookup"><span data-stu-id="ae404-352">Install and connect to the Azure AD PowerShell for Graph module (optional)</span></span>

<span data-ttu-id="ae404-353">Talvez você também queira baixar e instalar o módulo do PowerShell do [Azure AD](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2) para Graph (se ainda não tiver feito isso) e conectar-se ao Azure AD para recuperar uma lista de usuários em sua organização.</span><span class="sxs-lookup"><span data-stu-id="ae404-353">You might also want to [download and install the Azure AD PowerShell for Graph module](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2) (if you haven't already) and connect to Azure AD so that you can retrieve a list of users in your organization.</span></span>

<span data-ttu-id="ae404-354">Execute o seguinte para se conectar ao Azure AD.</span><span class="sxs-lookup"><span data-stu-id="ae404-354">Run the following to connect to Azure AD.</span></span>

```powershell
Connect-AzureAD
```

<span data-ttu-id="ae404-355">Quando for solicitado, entre usando as mesmas credenciais de administrador usadas para se conectar ao Teams.</span><span class="sxs-lookup"><span data-stu-id="ae404-355">When you're prompted, sign in using the same admin credentials that you used to connect to Teams.</span></span>

#### <a name="assign-a-setup-policy-to-a-batch-of-users"></a><span data-ttu-id="ae404-356">Atribuir uma política de configuração a um lote de usuários</span><span class="sxs-lookup"><span data-stu-id="ae404-356">Assign a setup policy to a batch of users</span></span>

<span data-ttu-id="ae404-357">Neste exemplo, usamos o cmdlet [New-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation) para atribuir uma política de configuração de aplicativo chamada Política de Configuração de Aplicativo RH a um lote de usuários listados no arquivo Users_ids.text.</span><span class="sxs-lookup"><span data-stu-id="ae404-357">In this example, we use the [New-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation) cmdlet to assign an app setup policy named HR App Setup Policy to a batch of users listed in the Users_ids.text file.</span></span>

```powershell
$user_ids = Get-Content .\users_ids.txt
New-CsBatchPolicyAssignmentOperation -PolicyType TeamsAppSetupPolicy -PolicyName "HR App Setup Policy" -Identity $users_ids -OperationName "Example 1 batch"
```

<span data-ttu-id="ae404-358">Neste exemplo, nos conectamos ao Azure AD para recuperar um conjunto de usuários e atribuir uma política de mensagens chamada Nova Política de Contratação de Mensagens a um lote de usuários especificados usando seu endereço SIP.</span><span class="sxs-lookup"><span data-stu-id="ae404-358">In this example, we connect to Azure AD to retrieve a collection of users and then assign a messaging policy named New Hire Messaging Policy to a batch of users specified by using their SIP address.</span></span>

```powershell
Connect-AzureAD
$users = Get-AzureADUser
New-CsBatchPolicyAssignmentOperation -PolicyType TeamsMessagingPolicy -PolicyName "New Hire Messaging Policy" -Identity $users.SipProxyAddress -OperationName "Example 2 batch"
```

#### <a name="get-the-status-of-a-batch-assignment"></a><span data-ttu-id="ae404-359">Obter o status de uma atribuição em lotes</span><span class="sxs-lookup"><span data-stu-id="ae404-359">Get the status of a batch assignment</span></span>

<span data-ttu-id="ae404-360">Execute o seguinte para obter o status de uma atribuição em lotes, onde OperationId é a ID de operação retornada pelo ```New-CsBatchPolicyAssignmentOperation``` cmdlet de um determinado lote.</span><span class="sxs-lookup"><span data-stu-id="ae404-360">Run the following to get the status of a batch assignment, where OperationId is the operation ID that's returned by the ```New-CsBatchPolicyAssignmentOperation``` cmdlet for a given batch.</span></span>

```powershell
$Get-CsBatchPolicyAssignmentOperation -OperationId f985e013-0826-40bb-8c94-e5f367076044 | fl
```

<span data-ttu-id="ae404-361">Se a saída mostrar que ocorreu um erro, execute o seguinte para obter mais informações sobre erros, que estão na ```UserState``` propriedade.</span><span class="sxs-lookup"><span data-stu-id="ae404-361">If the output shows that an error occurred, run the following to get more information about errors, which are in the ```UserState``` property.</span></span>

```powershell
Get-CsBatchPolicyAssignmentOperation -OperationId f985e013-0826-40bb-8c94-e5f367076044 | Select -ExpandProperty UserState
```

<span data-ttu-id="ae404-362">Para saber mais, consulte [Get-CsBatchPolicyAssignmentOperation.](https://docs.microsoft.com/powershell/module/teams/get-csbatchpolicyassignmentoperation)</span><span class="sxs-lookup"><span data-stu-id="ae404-362">To learn more, see [Get-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/get-csbatchpolicyassignmentoperation).</span></span>

## <a name="assign-a-policy-package-to-users"></a><span data-ttu-id="ae404-363">Atribuir um pacote de política aos usuários</span><span class="sxs-lookup"><span data-stu-id="ae404-363">Assign a policy package to users</span></span>

<span data-ttu-id="ae404-364">Um pacote de política no Teams é um conjunto de políticas e configurações de política predefinidas que você pode atribuir aos usuários que têm funções iguais ou semelhantes em sua organização.</span><span class="sxs-lookup"><span data-stu-id="ae404-364">A policy package in Teams is a collection of predefined policies and policy settings that you can assign to users who have the same or similar roles in your organization.</span></span> <span data-ttu-id="ae404-365">Cada pacote de política é projetado em torno de uma função de usuário e inclui políticas e configurações de política predefinidas que suportam atividades típicas para essa função.</span><span class="sxs-lookup"><span data-stu-id="ae404-365">Each policy package is designed around a user role and includes predefined policies and policy settings that support activities typical for that role.</span></span> <span data-ttu-id="ae404-366">Alguns exemplos de pacotes de política são o pacote Education (Professor) e o pacote Saúde (Trabalhador clínico).</span><span class="sxs-lookup"><span data-stu-id="ae404-366">Some examples of policy packages are the Education (Teacher) package and Healthcare (Clinical worker) package.</span></span> <span data-ttu-id="ae404-367">Para saber mais, consulte [Gerenciar pacotes de política no Teams.](manage-policy-packages.md)</span><span class="sxs-lookup"><span data-stu-id="ae404-367">To learn more, see [Manage policy packages in Teams](manage-policy-packages.md).</span></span>

### <a name="assign-a-policy-package-to-one-user"></a><span data-ttu-id="ae404-368">Atribuir um pacote de política a um usuário</span><span class="sxs-lookup"><span data-stu-id="ae404-368">Assign a policy package to one user</span></span>

1. <span data-ttu-id="ae404-369">Na navegação à esquerda do Centro de administração do Microsoft Teams, vá para **Usuários** e selecione o usuário.</span><span class="sxs-lookup"><span data-stu-id="ae404-369">In the left navigation of the Microsoft Teams admin center, go to **Users**, and then select the user.</span></span>
2. <span data-ttu-id="ae404-370">Na página do usuário, selecione Políticas **e,** em seguida, ao lado do pacote **de Política,** selecione **Editar.**</span><span class="sxs-lookup"><span data-stu-id="ae404-370">On the user's page, select **Policies**, and then next to **Policy package**, select **Edit**.</span></span>
3. <span data-ttu-id="ae404-371">No painel **Atribuir pacote de** política, selecione o pacote que você deseja atribuir e, em seguida, selecione **Salvar.**</span><span class="sxs-lookup"><span data-stu-id="ae404-371">In the **Assign policy package** pane, select the package you want to assign, and then select **Save**.</span></span>

### <a name="assign-a-policy-package-to-multiple-users"></a><span data-ttu-id="ae404-372">Atribuir um pacote de política a vários usuários</span><span class="sxs-lookup"><span data-stu-id="ae404-372">Assign a policy package to multiple users</span></span>

1. <span data-ttu-id="ae404-373">Na navegação à esquerda do Centro de administração do Microsoft Teams, vá para Pacotes de política e selecione o pacote de política que você deseja atribuir clicando à esquerda do nome do pacote.</span><span class="sxs-lookup"><span data-stu-id="ae404-373">In the left navigation of the Microsoft Teams admin center, go to **Policy packages**, and then select the policy package you want to assign by clicking to the left of the package name.</span></span>
2. <span data-ttu-id="ae404-374">Escolha **Gerenciar usuários**.</span><span class="sxs-lookup"><span data-stu-id="ae404-374">Select **Manage users**.</span></span>
3. <span data-ttu-id="ae404-375">No painel **Gerenciar usuários**, procure o usuário pelo nome de exibição ou pelo nome de usuário, escolha o nome e marque **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="ae404-375">In the **Manage users** pane, search for the user by display name or by user name, select the name, and then select **Add**.</span></span> <span data-ttu-id="ae404-376">Repita esta etapa para cada usuário que você deseja adicionar.</span><span class="sxs-lookup"><span data-stu-id="ae404-376">Repeat this step for each user that you want to add.</span></span>
4. <span data-ttu-id="ae404-377">Quando terminar de adicionar usuários, selecione **Salvar.**</span><span class="sxs-lookup"><span data-stu-id="ae404-377">When you're finished adding users, select **Save**.</span></span>

## <a name="assign-a-policy-package-to-a-group"></a><span data-ttu-id="ae404-378">Atribua o pacote de política a um grupo.</span><span class="sxs-lookup"><span data-stu-id="ae404-378">Assign a policy package to a group</span></span>

<span data-ttu-id="ae404-379">**Este recurso está na visualização particular**</span><span class="sxs-lookup"><span data-stu-id="ae404-379">**This feature is in private preview**</span></span>

<span data-ttu-id="ae404-380">As atribuições de pacote de política aos grupos permitem atribuir várias políticas a um grupo de usuários, como uma lista de distribuição ou grupo de segurança.</span><span class="sxs-lookup"><span data-stu-id="ae404-380">Policy package assignment to groups let you assign multiple policies to a group of users, such as a security group or distribution list.</span></span> <span data-ttu-id="ae404-381">As atribuições de política serão propagadas para os membros do grupo, de acordo com as regras de precedência.</span><span class="sxs-lookup"><span data-stu-id="ae404-381">The policy assignment is propagated to members of the group according to precedence rules.</span></span> <span data-ttu-id="ae404-382">À medida que os membros forem adicionados ou removidos de um grupo, as atribuições de política herdadas serão atualizadas.</span><span class="sxs-lookup"><span data-stu-id="ae404-382">As members are added to or removed from a group, their inherited policy assignments are updated accordingly.</span></span>

<span data-ttu-id="ae404-383">A atribuição de pacote de política a grupos é recomendada para grupos de até 50.000 usuários, mas também funcionará com grupos maiores.</span><span class="sxs-lookup"><span data-stu-id="ae404-383">Policy package assignment to groups is recommended for groups of up to 50,000 users, but it will also work with larger groups.</span></span>

<span data-ttu-id="ae404-384">Quando você atribui o pacote de política, ele é atribuído imediatamente ao grupo.</span><span class="sxs-lookup"><span data-stu-id="ae404-384">When you assign the policy package, it's immediately assigned to the group.</span></span> <span data-ttu-id="ae404-385">No entanto, a propagação da atribuição de política aos membros do grupo é executada como uma operação em segundo plano e pode levar algum tempo, dependendo do tamanho do grupo.</span><span class="sxs-lookup"><span data-stu-id="ae404-385">However, the propagation of the policy assignment to members of the group is performed as a background operation and might take some time, depending on the size of the group.</span></span> <span data-ttu-id="ae404-386">O mesmo é verdadeiro quando uma política não é atribuída a um grupo ou quando os membros são adicionados ou removidos de um grupo.</span><span class="sxs-lookup"><span data-stu-id="ae404-386">The same is true when a policy is unassigned from a group, or when members are added to or removed from a group.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="ae404-387">Antes de começar, é importante entender as regras de [precedência](#precedence-rules) e a classificação [da atribuição de grupo.](#group-assignment-ranking)</span><span class="sxs-lookup"><span data-stu-id="ae404-387">Before you get started, it's important to understand [precedence rules](#precedence-rules) and [group assignment ranking](#group-assignment-ranking).</span></span> <span data-ttu-id="ae404-388">Leia e entenda os conceitos [](#what-you-need-to-know-about-policy-assignment-to-groups) do que você precisa saber sobre a atribuição de política a grupos anteriormente neste artigo.</span><span class="sxs-lookup"><span data-stu-id="ae404-388">Make sure you read and understand the concepts in [What you need to know about policy assignment to groups](#what-you-need-to-know-about-policy-assignment-to-groups) earlier in this article.</span></span>

### <a name="assign-a-policy-package-to-a-group-of-users-in-the-admin-center"></a><span data-ttu-id="ae404-389">Atribuir um pacote de política a um grupo de usuários no centro de administração</span><span class="sxs-lookup"><span data-stu-id="ae404-389">Assign a policy package to a group of users in the admin center</span></span>

1. <span data-ttu-id="ae404-390">Entre no Centro de administração do Teams.</span><span class="sxs-lookup"><span data-stu-id="ae404-390">Sign in to the Teams admin center.</span></span>
2. <span data-ttu-id="ae404-391">Na navegação à esquerda, vá para a página do pacote de política.</span><span class="sxs-lookup"><span data-stu-id="ae404-391">In the left navigation, go to the policy package page.</span></span>
3. <span data-ttu-id="ae404-392">Selecione a guia de atribuição de política de grupo.</span><span class="sxs-lookup"><span data-stu-id="ae404-392">Select the Group policy assignment tab.</span></span>
4. <span data-ttu-id="ae404-393">Selecione **Adicionar grupo** e, em seguida, no painel Atribuir um pacote de política ao grupo, faça o seguinte:</span><span class="sxs-lookup"><span data-stu-id="ae404-393">Select **Add group**, and then in the Assign a policy package to group pane, do the following:</span></span>

    <span data-ttu-id="ae404-394">a.</span><span class="sxs-lookup"><span data-stu-id="ae404-394">a.</span></span> <span data-ttu-id="ae404-395">Pesquise e adicione o grupo ao que você deseja atribuir o pacote de política.</span><span class="sxs-lookup"><span data-stu-id="ae404-395">Search for and add the group you want to assign the policy package to.</span></span>

    <span data-ttu-id="ae404-396">b.</span><span class="sxs-lookup"><span data-stu-id="ae404-396">b.</span></span> <span data-ttu-id="ae404-397">Selecione um pacote de política.</span><span class="sxs-lookup"><span data-stu-id="ae404-397">Select a policy package.</span></span>

    <span data-ttu-id="ae404-398">c.</span><span class="sxs-lookup"><span data-stu-id="ae404-398">c.</span></span> <span data-ttu-id="ae404-399">Definir a classificação para cada tipo de política.</span><span class="sxs-lookup"><span data-stu-id="ae404-399">Set the ranking for each policy type.</span></span>

    <span data-ttu-id="ae404-400">d.</span><span class="sxs-lookup"><span data-stu-id="ae404-400">d.</span></span> <span data-ttu-id="ae404-401">Selecione **Aplicar.**</span><span class="sxs-lookup"><span data-stu-id="ae404-401">Select **Apply**.</span></span>

    ![mostra a atribuição de política de grupo](media/group-pkg-assignment.png)

5. <span data-ttu-id="ae404-403">Para gerenciar a classificação de um tipo de política específico, navegue até a página de política específica.</span><span class="sxs-lookup"><span data-stu-id="ae404-403">To manage ranking for a specific policy type, navigate to the specific policy page.</span></span>
6. <span data-ttu-id="ae404-404">Para reatribuir um pacote de política a um grupo, primeiro remova a atribuição de política de grupo.</span><span class="sxs-lookup"><span data-stu-id="ae404-404">To reassign a policy package to a group, first remove the group policy assignment.</span></span> <span data-ttu-id="ae404-405">Em seguida, siga as etapas acima para atribuir o pacote de política a um grupo.</span><span class="sxs-lookup"><span data-stu-id="ae404-405">Then, follow the steps above to assign the policy package to a group.</span></span>

### <a name="work-with-powershell"></a><span data-ttu-id="ae404-406">Trabalhar com o PowerShell</span><span class="sxs-lookup"><span data-stu-id="ae404-406">Work with PowerShell</span></span>

#### <a name="get-the-teams-powershell-module"></a><span data-ttu-id="ae404-407">Obter o módulo do PowerShell do Teams</span><span class="sxs-lookup"><span data-stu-id="ae404-407">Get the Teams PowerShell module</span></span>

<span data-ttu-id="ae404-408">Para obter orientações passo a passo, consulte [Instalar o PowerShell do Teams.](teams-powershell-install.md)</span><span class="sxs-lookup"><span data-stu-id="ae404-408">For step-by-step guidance, see [Install Teams PowerShell](teams-powershell-install.md).</span></span>

#### <a name="assign-a-policy-package-to-a-group-of-users"></a><span data-ttu-id="ae404-409">Atribuir um pacote de política a um grupo de usuários</span><span class="sxs-lookup"><span data-stu-id="ae404-409">Assign a policy package to a group of users</span></span>

<span data-ttu-id="ae404-410">Use o cmdlet [Grant-CsGroupPolicyPackageAssignment](https://docs.microsoft.com/powershell/module/teams/grant-csgrouppolicypackageassignment) para atribuir um pacote de política a um grupo.</span><span class="sxs-lookup"><span data-stu-id="ae404-410">Use the [Grant-CsGroupPolicyPackageAssignment](https://docs.microsoft.com/powershell/module/teams/grant-csgrouppolicypackageassignment) cmdlet to assign a policy package to a group.</span></span> <span data-ttu-id="ae404-411">Você pode especificar um grupo usando a ID do objeto, o endereço SIP ou o endereço de email.</span><span class="sxs-lookup"><span data-stu-id="ae404-411">You can specify a group by using the object ID, SIP address, or email address.</span></span> <span data-ttu-id="ae404-412">Ao atribuir o pacote de política, especifique uma classificação de atribuição [de grupo](#group-assignment-ranking) para cada tipo de política no pacote de política.</span><span class="sxs-lookup"><span data-stu-id="ae404-412">When you assign the policy package, specify a [group assignment ranking](#group-assignment-ranking) for each policy type in the policy package.</span></span>

<span data-ttu-id="ae404-413">Neste exemplo, atribuímos o pacote de política Education_Teacher a um grupo com uma classificação de atribuição de 1 para TeamsAppSetupPolicy e TeamsMeetingBroadcastPolicy e uma classificação de 2 para TeamsMeetingPolicy.</span><span class="sxs-lookup"><span data-stu-id="ae404-413">In this example, we assign the Education_Teacher policy package to a group with an assignment ranking of 1 for TeamsAppSetupPolicy and TeamsMeetingBroadcastPolicy and a ranking of 2 for TeamsMeetingPolicy.</span></span>

```powershell
Grant-CsGroupPolicyPackageAssignment -GroupId "dae90bb4-120f-4a3e-a15d-30f142e79f69" -PackageName "Education_Teacher" -PolicyRankings "TeamsAppSetupPolicy, 1", "TeamsMeetingBroadcastPolicy, 1", "TeamsMeetingPolicy, 2"
```

## <a name="assign-a-policy-package-to-a-batch-of-users"></a><span data-ttu-id="ae404-414">Atribuir um pacote de política a um lote de usuários</span><span class="sxs-lookup"><span data-stu-id="ae404-414">Assign a policy package to a batch of users</span></span>

<span data-ttu-id="ae404-415">Com a atribuição de pacote de política em lotes, você pode atribuir um pacote de política a grandes conjuntos de usuários por vez sem precisar usar um script.</span><span class="sxs-lookup"><span data-stu-id="ae404-415">With batch policy package assignment, you can assign a policy package to large sets of users at a time without having to use a script.</span></span> <span data-ttu-id="ae404-416">Use o cmdlet [New-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation) para enviar um lote de usuários e o pacote de política que você deseja atribuir.</span><span class="sxs-lookup"><span data-stu-id="ae404-416">You use the [New-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation) cmdlet to submit a batch of users and the policy package that you want to assign.</span></span> <span data-ttu-id="ae404-417">As atribuições são processadas como uma operação de plano de fundo e uma ID de operação é gerada para cada lote.</span><span class="sxs-lookup"><span data-stu-id="ae404-417">The assignments are processed as a background operation and an operation ID is generated for each batch.</span></span> <span data-ttu-id="ae404-418">Em seguida, você pode usar o cmdlet [Get-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/get-csbatchpolicyassignmentoperation) para controlar o progresso e o status das atribuições em um lote.</span><span class="sxs-lookup"><span data-stu-id="ae404-418">You can then use the [Get-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/get-csbatchpolicyassignmentoperation) cmdlet to track the progress and status of the assignments in a batch.</span></span>

<span data-ttu-id="ae404-419">Especifique os usuários por sua ID de objeto ou endereço SIP (Session Initiation Protocol).</span><span class="sxs-lookup"><span data-stu-id="ae404-419">Specify users by their object ID or Session Initiation Protocol (SIP) address.</span></span> <span data-ttu-id="ae404-420">O endereço SIP de um usuário geralmente tem o mesmo valor que o nome de usuário principal (UPN) ou o endereço de email, mas isso não é necessário.</span><span class="sxs-lookup"><span data-stu-id="ae404-420">A user's SIP address often has the same value as the User Principal Name (UPN) or email address, but this isn't required.</span></span> <span data-ttu-id="ae404-421">Se um usuário for especificado usando seu UPN ou email, mas tiver um valor diferente do endereço SIP, a atribuição de política falhará para o usuário.</span><span class="sxs-lookup"><span data-stu-id="ae404-421">If a user is specified using their UPN or email, but it has a different value than their SIP address, then policy assignment will fail for the user.</span></span> <span data-ttu-id="ae404-422">Se um lote incluir usuários duplicados, as duplicatas serão removidas do lote antes do processamento e o status só será fornecido para os usuários exclusivos restantes no lote.</span><span class="sxs-lookup"><span data-stu-id="ae404-422">If a batch includes duplicate users, the duplicates will be removed from the batch before processing and status will only be provided for the unique users remaining in the batch.</span></span>

<span data-ttu-id="ae404-423">Um lote contém até 5.000 usuários.</span><span class="sxs-lookup"><span data-stu-id="ae404-423">A batch contains up to 5,000 users.</span></span> <span data-ttu-id="ae404-424">Para obter melhores resultados, não envie mais do que alguns lotes de cada vez.</span><span class="sxs-lookup"><span data-stu-id="ae404-424">For best results, don't submit more than a few batches at a time.</span></span> <span data-ttu-id="ae404-425">Permita que os lotes concluam o processamento antes de enviar mais lotes.</span><span class="sxs-lookup"><span data-stu-id="ae404-425">Allow batches to complete processing before submitting more batches.</span></span>

### <a name="use-the-teams-powershell-module"></a><span data-ttu-id="ae404-426">Usar o módulo do PowerShell do Teams</span><span class="sxs-lookup"><span data-stu-id="ae404-426">Use the Teams PowerShell module</span></span>

<span data-ttu-id="ae404-427">Execute o seguinte para instalar o módulo [do PowerShell](https://www.powershellgallery.com/packages/MicrosoftTeams) do Microsoft Teams (caso ainda não o tenha feito).</span><span class="sxs-lookup"><span data-stu-id="ae404-427">Run the following to install the [Microsoft Teams PowerShell module](https://www.powershellgallery.com/packages/MicrosoftTeams) (if you haven't already).</span></span> <span data-ttu-id="ae404-428">Instale a versão 1.0.5 ou posterior.</span><span class="sxs-lookup"><span data-stu-id="ae404-428">Make sure you install version 1.0.5 or later.</span></span>

```powershell
Install-Module -Name MicrosoftTeams
```

<span data-ttu-id="ae404-429">Execute o seguinte para se conectar ao Teams e iniciar uma sessão.</span><span class="sxs-lookup"><span data-stu-id="ae404-429">Run the following to connect to Teams and start a session.</span></span>

```powershell
Connect-MicrosoftTeams
```

<span data-ttu-id="ae404-430">Quando for solicitado, entre usando suas credenciais de administrador.</span><span class="sxs-lookup"><span data-stu-id="ae404-430">When you're prompted, sign in using your admin credentials.</span></span>

### <a name="assign-policy-packages-to-a-batch-of-users"></a><span data-ttu-id="ae404-431">Atribuir pacotes de política a um lote de usuários</span><span class="sxs-lookup"><span data-stu-id="ae404-431">Assign policy packages to a batch of users</span></span>

<span data-ttu-id="ae404-432">Neste exemplo, usamos o cmdlet [New-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation) para atribuir o pacote de política Education_PrimaryStudent a um lote de usuários.</span><span class="sxs-lookup"><span data-stu-id="ae404-432">In this example, we use the [New-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation) cmdlet to assign the Education_PrimaryStudent policy package to a batch of users.</span></span>

```powershell
New-CsBatchPolicyPackageAssignmentOperation -Identity 1bc0b35f-095a-4a37-a24c-c4b6049816ab,user1@econtoso.com,user2@contoso.com -PackageName Education_PrimaryStudent
```

### <a name="see-the-status-of-a-batch-assignment"></a><span data-ttu-id="ae404-433">Ver o status de uma atribuição em lotes</span><span class="sxs-lookup"><span data-stu-id="ae404-433">See the status of a batch assignment</span></span>

<span data-ttu-id="ae404-434">Execute o seguinte para obter o status de uma atribuição em lotes, onde OperationId é a ID de operação retornada pelo ```New-CsBatchPolicyAssignmentOperation``` cmdlet de um determinado lote.</span><span class="sxs-lookup"><span data-stu-id="ae404-434">Run the following to get the status of a batch assignment, where OperationId is the operation ID that's returned by the ```New-CsBatchPolicyAssignmentOperation``` cmdlet for a given batch.</span></span>

```powershell
$Get-CsBatchPolicyAssignmentOperation -OperationId f985e013-0826-40bb-8c94-e5f367076044 | fl
```

<span data-ttu-id="ae404-435">Se a saída mostrar que ocorreu um erro, execute o seguinte para obter mais informações sobre erros, que estão na ```UserState``` propriedade.</span><span class="sxs-lookup"><span data-stu-id="ae404-435">If the output shows that an error occurred, run the following to get more information about errors, which are in the ```UserState``` property.</span></span>

```powershell
Get-CsBatchPolicyAssignmentOperation -OperationId f985e013-0826-40bb-8c94-e5f367076044 | Select -ExpandProperty UserState
```

<span data-ttu-id="ae404-436">Para saber mais, consulte [Get-CsBatchPolicyAssignmentOperation.](https://docs.microsoft.com/powershell/module/teams/get-csbatchpolicyassignmentoperation)</span><span class="sxs-lookup"><span data-stu-id="ae404-436">To learn more, see [Get-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/get-csbatchpolicyassignmentoperation).</span></span>

## <a name="related-topics"></a><span data-ttu-id="ae404-437">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="ae404-437">Related topics</span></span>

[<span data-ttu-id="ae404-438">Visão Geral do PowerShell do Teams</span><span class="sxs-lookup"><span data-stu-id="ae404-438">Teams PowerShell Overview</span></span>](teams-powershell-overview.md)
