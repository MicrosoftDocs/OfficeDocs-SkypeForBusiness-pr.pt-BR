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
description: Saiba as diferentes maneiras de atribuir políticas aos usuários em Microsoft Teams.
f1keywords:
- ms.teamsadmincenter.bulkoperations.users.edit
- ms.teamsadmincenter.bulkoperations.edit
ms.openlocfilehash: 05ed811c38b3f49e21933d575c82128360ca3390
ms.sourcegitcommit: 3840d72f9ad1c0c7803dc3662a0318f558fe92ab
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/03/2021
ms.locfileid: "52739711"
---
# <a name="assign-policies-to-your-users-in-microsoft-teams"></a><span data-ttu-id="cc1b0-103">Atribuir políticas aos usuários no Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="cc1b0-103">Assign policies to your users in Microsoft Teams</span></span>

<span data-ttu-id="cc1b0-104">Como administrador, você usa políticas para controlar os recursos Teams que estão disponíveis para os usuários em sua organização.</span><span class="sxs-lookup"><span data-stu-id="cc1b0-104">As an admin, you use policies to control the Teams features that are available to users in your organization.</span></span> <span data-ttu-id="cc1b0-105">Por exemplo, há políticas de chamada, políticas de reunião e políticas de mensagens, para nomear apenas algumas.</span><span class="sxs-lookup"><span data-stu-id="cc1b0-105">For example, there are calling policies, meeting policies, and messaging policies, to name just a few.</span></span>

<span data-ttu-id="cc1b0-106">As organizações têm diferentes tipos de usuários com necessidades exclusivas.</span><span class="sxs-lookup"><span data-stu-id="cc1b0-106">Organizations have different types of users with unique needs.</span></span> <span data-ttu-id="cc1b0-107">As políticas personalizadas que você cria e atribui permitem que você adapte as configurações de política a diferentes conjuntos de usuários com base nessas necessidades.</span><span class="sxs-lookup"><span data-stu-id="cc1b0-107">Custom policies that you create and assign let you tailor policy settings to different sets of users based on those needs.</span></span>

<span data-ttu-id="cc1b0-108">Para gerenciar facilmente as políticas em sua organização, Teams oferece várias maneiras de atribuir políticas aos usuários.</span><span class="sxs-lookup"><span data-stu-id="cc1b0-108">To easily manage policies in your organization, Teams offers several ways to assign policies to users.</span></span> <span data-ttu-id="cc1b0-109">Atribua uma política diretamente aos usuários, individualmente ou em escala por meio de uma atribuição em lotes ou a um grupo do que os usuários são membros.</span><span class="sxs-lookup"><span data-stu-id="cc1b0-109">Assign a policy directly to users, either individually or at scale through a batch assignment, or to a group that the users are members of.</span></span> <span data-ttu-id="cc1b0-110">Você também pode usar pacotes de política para atribuir uma coleção predefinida de políticas a usuários em sua organização que tenham funções semelhantes.</span><span class="sxs-lookup"><span data-stu-id="cc1b0-110">You can also use policy packages to assign a preset collection of policies to users in your organization who have similar roles.</span></span> <span data-ttu-id="cc1b0-111">A opção escolhida depende do número de políticas que você está gerenciando e do número de usuários aos quais você está atribuindo políticas.</span><span class="sxs-lookup"><span data-stu-id="cc1b0-111">The option that you choose depends on the number of policies that you're managing and the number of users you're assigning policies to.</span></span> <span data-ttu-id="cc1b0-112">As políticas globais (padrão em toda a organização) se aplicam ao maior número de usuários em sua organização.</span><span class="sxs-lookup"><span data-stu-id="cc1b0-112">Global (Org-wide default) policies apply to the largest number of users in your organization.</span></span> <span data-ttu-id="cc1b0-113">Você só precisa atribuir políticas a esses usuários que exigem políticas especializadas.</span><span class="sxs-lookup"><span data-stu-id="cc1b0-113">You only have to assign policies to those users that require specialized policies.</span></span>

<span data-ttu-id="cc1b0-114">Este artigo descreve as diferentes maneiras pelas quais você pode atribuir políticas aos usuários e os cenários recomendados para quando usar o quê.</span><span class="sxs-lookup"><span data-stu-id="cc1b0-114">This article describes the different ways that you can assign policies to users and the recommended scenarios for when to use what.</span></span>

## <a name="which-policy-takes-precedence"></a><span data-ttu-id="cc1b0-115">Qual política tem precedência?</span><span class="sxs-lookup"><span data-stu-id="cc1b0-115">Which policy takes precedence?</span></span>

<span data-ttu-id="cc1b0-116">Um usuário tem uma política efetiva para cada tipo de política.</span><span class="sxs-lookup"><span data-stu-id="cc1b0-116">A user has one effective policy for each policy type.</span></span> <span data-ttu-id="cc1b0-117">É possível, ou mesmo provável, que um usuário tenha uma política atribuída diretamente e também seja membro de um ou mais grupos que tenha atribuído uma política do mesmo tipo.</span><span class="sxs-lookup"><span data-stu-id="cc1b0-117">It's possible, or even likely, that a user is directly assigned a policy and is also a member of one or more groups that's assigned a policy of the same type.</span></span> <span data-ttu-id="cc1b0-118">Nesses tipos de cenários, qual política tem precedência?</span><span class="sxs-lookup"><span data-stu-id="cc1b0-118">In these kinds of scenarios, which policy takes precedence?</span></span> <span data-ttu-id="cc1b0-119">A política efetiva de um usuário é determinada de acordo com as regras de precedência, da seguinte maneira.</span><span class="sxs-lookup"><span data-stu-id="cc1b0-119">A user's effective policy is determined according to rules of precedence, as follows.</span></span>

<span data-ttu-id="cc1b0-120">Se um usuário for atribuído diretamente a uma política (individualmente ou por meio de uma atribuição em lotes), essa política tem precedência.</span><span class="sxs-lookup"><span data-stu-id="cc1b0-120">If a user is directly assigned a policy (either individually or through a batch assignment), that policy takes precedence.</span></span> <span data-ttu-id="cc1b0-121">No exemplo visual a seguir, a política efetiva do usuário é a política de reunião do Quadrado do Lincoln, que é atribuída diretamente ao usuário.</span><span class="sxs-lookup"><span data-stu-id="cc1b0-121">In the following visual example, the user's effective policy is the Lincoln Square meeting policy, which is directly assigned to the user.</span></span>

![Diagrama mostrando como uma política atribuída diretamente tem precedência](media/assign-policies-example-directly-assigned.png)

<span data-ttu-id="cc1b0-123">Se um usuário não receber diretamente uma política de um determinado tipo, a política atribuída a um grupo do qual o usuário é membro tem precedência.</span><span class="sxs-lookup"><span data-stu-id="cc1b0-123">If a user isn't directly assigned a policy of a given type, the policy assigned to a group that the user is a member of takes precedence.</span></span> <span data-ttu-id="cc1b0-124">Se um usuário for membro de vários grupos, [](#group-assignment-ranking) a política com a classificação de atribuição de grupo mais alta para o tipo de política determinado terá precedência.</span><span class="sxs-lookup"><span data-stu-id="cc1b0-124">If a user is a member of multiple groups, the policy that has the highest [group assignment ranking](#group-assignment-ranking) for the given policy type takes precedence.</span></span>

<span data-ttu-id="cc1b0-125">Neste exemplo visual, a política efetiva do usuário é a política Teams e HD do Exec, que tem a classificação de atribuição mais alta em relação a outros grupos dos quais o usuário é membro e que também recebe uma política do mesmo tipo de política.</span><span class="sxs-lookup"><span data-stu-id="cc1b0-125">In this visual example, the user's effective policy is the Exec Teams and HD policy, which has the highest assignment ranking relative to other groups that the user is a member of and that are also assigned a policy of the same policy type.</span></span>  

![Diagrama mostrando como uma política herdada do grupo tem precedência](media/assign-policies-example-group.png)

<span data-ttu-id="cc1b0-127">Se um usuário não recebe uma política diretamente ou não é membro de nenhum grupo atribuído a uma política, o usuário obtém a política global (padrão em toda a organização) para esse tipo de política.</span><span class="sxs-lookup"><span data-stu-id="cc1b0-127">If a user isn't directly assigned a policy or isn't a member of any groups that are assigned a policy, the user gets the global (Org-wide default) policy for that policy type.</span></span> <span data-ttu-id="cc1b0-128">Veja um exemplo visual.</span><span class="sxs-lookup"><span data-stu-id="cc1b0-128">Here's a visual example.</span></span>

![Diagrama mostrando como uma política global tem precedência](media/assign-policies-example-global.png)

<span data-ttu-id="cc1b0-130">Para saber mais, confira [Regras de precedência.](#precedence-rules)</span><span class="sxs-lookup"><span data-stu-id="cc1b0-130">To learn more, see [Precedence rules](#precedence-rules).</span></span>

## <a name="ways-to-assign-policies"></a><span data-ttu-id="cc1b0-131">Maneiras de atribuir políticas</span><span class="sxs-lookup"><span data-stu-id="cc1b0-131">Ways to assign policies</span></span>

<span data-ttu-id="cc1b0-132">Aqui está uma visão geral das maneiras pelas quais você pode atribuir políticas aos usuários e aos cenários recomendados para cada um.</span><span class="sxs-lookup"><span data-stu-id="cc1b0-132">Here's an overview of the ways that you can assign policies to users and the recommended scenarios for each.</span></span> <span data-ttu-id="cc1b0-133">Selecione os links para saber mais.</span><span class="sxs-lookup"><span data-stu-id="cc1b0-133">Select the links to learn more.</span></span>

<span data-ttu-id="cc1b0-134">Antes de atribuir políticas a usuários ou grupos individuais, comece definindo as políticas [globais (padrão](#set-the-global-policies) em toda a organização) para que elas se apliquem ao maior número de usuários em sua organização.</span><span class="sxs-lookup"><span data-stu-id="cc1b0-134">Before assigning policies to individual users or groups, start by [setting the global (Org-wide default) policies](#set-the-global-policies) so that they apply to the largest number of users in your organization.</span></span>  <span data-ttu-id="cc1b0-135">Depois que as políticas globais são definidas, você só precisará atribuir políticas aos usuários que exigem políticas especializadas.</span><span class="sxs-lookup"><span data-stu-id="cc1b0-135">Once the global policies are set, you'll only need to assign policies to those users that require specialized policies.</span></span>

|<span data-ttu-id="cc1b0-136">Faça isso</span><span class="sxs-lookup"><span data-stu-id="cc1b0-136">Do this</span></span>  |<span data-ttu-id="cc1b0-137">Se...</span><span class="sxs-lookup"><span data-stu-id="cc1b0-137">If...</span></span>  | <span data-ttu-id="cc1b0-138">Usando...</span><span class="sxs-lookup"><span data-stu-id="cc1b0-138">Using...</span></span>
|---------|---------|----|
|[<span data-ttu-id="cc1b0-139">Atribuir uma política a usuários individuais</span><span class="sxs-lookup"><span data-stu-id="cc1b0-139">Assign a policy to individual users</span></span>](#assign-a-policy-to-individual-users)    | <span data-ttu-id="cc1b0-140">Você é novo no Teams e apenas começando ou só precisa atribuir uma ou duas políticas a um pequeno número de usuários.</span><span class="sxs-lookup"><span data-stu-id="cc1b0-140">You're new to Teams and just getting started or you only need to assign one or a couple of policies to a small number of users.</span></span> |<span data-ttu-id="cc1b0-141">O Microsoft Teams de administração ou cmdlets do PowerShell no módulo Teams PowerShell</span><span class="sxs-lookup"><span data-stu-id="cc1b0-141">The Microsoft Teams admin center or PowerShell cmdlets in the Teams PowerShell module</span></span>
|[<span data-ttu-id="cc1b0-142">Atribuir uma política a um grupo</span><span class="sxs-lookup"><span data-stu-id="cc1b0-142">Assign a policy to a group</span></span>](#assign-a-policy-to-a-group) |<span data-ttu-id="cc1b0-143">Atribua políticas com base na associação de grupo de um usuário.</span><span class="sxs-lookup"><span data-stu-id="cc1b0-143">Assign policies based on a user's group membership.</span></span> <span data-ttu-id="cc1b0-144">Por exemplo, atribua uma política a todos os usuários em um grupo de segurança ou lista de distribuição.</span><span class="sxs-lookup"><span data-stu-id="cc1b0-144">For example, assign a policy to all users in a security group or distribution list.</span></span>| <span data-ttu-id="cc1b0-145">O Microsoft Teams de administração ou cmdlets do PowerShell no módulo Teams PowerShell</span><span class="sxs-lookup"><span data-stu-id="cc1b0-145">The Microsoft Teams admin center or PowerShell cmdlets in the Teams PowerShell module</span></span>|
|[<span data-ttu-id="cc1b0-146">Atribuir uma política a um lote de usuários</span><span class="sxs-lookup"><span data-stu-id="cc1b0-146">Assign a policy to a batch of users</span></span>](#assign-a-policy-to-a-batch-of-users)   | <span data-ttu-id="cc1b0-147">Atribua políticas a grandes conjuntos de usuários.</span><span class="sxs-lookup"><span data-stu-id="cc1b0-147">Assign policies to large sets of users.</span></span> <span data-ttu-id="cc1b0-148">Por exemplo, atribua uma política a centenas ou milhares de usuários em sua organização por vez.</span><span class="sxs-lookup"><span data-stu-id="cc1b0-148">For example, assign a policy to hundreds or thousands of users in your organization at a time.</span></span> |<span data-ttu-id="cc1b0-149">O Microsoft Teams de administração ou cmdlets do PowerShell no módulo Teams PowerShell</span><span class="sxs-lookup"><span data-stu-id="cc1b0-149">The Microsoft Teams admin center or PowerShell cmdlets in the Teams PowerShell module</span></span>|
| [<span data-ttu-id="cc1b0-150">Atribuir um pacote de política aos usuários</span><span class="sxs-lookup"><span data-stu-id="cc1b0-150">Assign a policy package to users</span></span>](#assign-a-policy-package-to-users)  |<span data-ttu-id="cc1b0-151">Atribua várias políticas a conjuntos específicos de usuários em sua organização que tenham as mesmas funções ou funções semelhantes.</span><span class="sxs-lookup"><span data-stu-id="cc1b0-151">Assign multiple policies to specific sets of users in your organization who have the same or similar roles.</span></span> <span data-ttu-id="cc1b0-152">Por exemplo, atribua o pacote de política Educação (Professor) aos professores em sua escola para dar a eles acesso total a chats, chamada e reuniões.</span><span class="sxs-lookup"><span data-stu-id="cc1b0-152">For example, assign the Education (Teacher) policy package to teachers in your school to give them full access to chats, calling, and meetings.</span></span> <span data-ttu-id="cc1b0-153">Atribua o pacote de política educação (estudante secundário) a alunos secundários para limitar determinados recursos, como chamada privada.</span><span class="sxs-lookup"><span data-stu-id="cc1b0-153">Assign the Education (Secondary school student) policy package to secondary students to limit certain capabilities such as private calling.</span></span>  |<span data-ttu-id="cc1b0-154">O Microsoft Teams de administração ou cmdlets do PowerShell no módulo Teams PowerShell</span><span class="sxs-lookup"><span data-stu-id="cc1b0-154">The Microsoft Teams admin center or PowerShell cmdlets in the Teams PowerShell module</span></span>|
| <span data-ttu-id="cc1b0-155">[Atribuir um pacote de política a um grupo](#assign-a-policy-package-to-a-group) (em visualização privada)</span><span class="sxs-lookup"><span data-stu-id="cc1b0-155">[Assign a policy package to a group](#assign-a-policy-package-to-a-group) (in private preview)</span></span>   |<span data-ttu-id="cc1b0-156">Atribua várias políticas a um grupo de usuários em sua organização que tenham as mesmas funções ou funções semelhantes.</span><span class="sxs-lookup"><span data-stu-id="cc1b0-156">Assign multiple policies to a group of users in your organization who have the same or similar roles.</span></span> <span data-ttu-id="cc1b0-157">Por exemplo, atribua um pacote de política a todos os usuários em um grupo de segurança ou lista de distribuição.</span><span class="sxs-lookup"><span data-stu-id="cc1b0-157">For example, assign a policy package to all users in a security group or distribution list.</span></span> |<span data-ttu-id="cc1b0-158">O Microsoft Teams de administração (em breve) ou cmdlets do PowerShell no módulo Teams PowerShell</span><span class="sxs-lookup"><span data-stu-id="cc1b0-158">The Microsoft Teams admin center (coming soon) or PowerShell cmdlets in the Teams PowerShell module</span></span>|
| [<span data-ttu-id="cc1b0-159">Atribuir um pacote de política a um lote de usuários</span><span class="sxs-lookup"><span data-stu-id="cc1b0-159">Assign a policy package to a batch of users</span></span>](#assign-a-policy-package-to-a-batch-of-users)|<span data-ttu-id="cc1b0-160">Atribua várias políticas a um lote de usuários em sua organização que tenham as mesmas funções ou funções semelhantes.</span><span class="sxs-lookup"><span data-stu-id="cc1b0-160">Assign multiple policies to a batch of users in your organization who have the same or similar roles.</span></span> <span data-ttu-id="cc1b0-161">Por exemplo, atribua o pacote de política Educação (Professor) a todos os professores em sua escola usando a atribuição em lotes para dar a eles acesso total a chats, chamada e reuniões.</span><span class="sxs-lookup"><span data-stu-id="cc1b0-161">For example, assign the Education (Teacher) policy package to all teachers in your school using batch assignment to give them full access to chats, calling, and meetings.</span></span> <span data-ttu-id="cc1b0-162">Atribua o pacote de política educação (estudante secundário) a um lote de alunos secundários para limitar determinados recursos, como chamada privada.</span><span class="sxs-lookup"><span data-stu-id="cc1b0-162">Assign the Education (Secondary school student) policy package to a batch of secondary students to limit certain capabilities such as private calling.</span></span>|<span data-ttu-id="cc1b0-163">Cmdlets do PowerShell no módulo Teams PowerShell</span><span class="sxs-lookup"><span data-stu-id="cc1b0-163">PowerShell cmdlets in the Teams PowerShell module</span></span>|

## <a name="set-the-global-policies"></a><span data-ttu-id="cc1b0-164">Definir as políticas globais</span><span class="sxs-lookup"><span data-stu-id="cc1b0-164">Set the global policies</span></span>

<span data-ttu-id="cc1b0-165">Siga estas etapas para definir as políticas globais (padrão em toda a organização) para cada tipo de política.</span><span class="sxs-lookup"><span data-stu-id="cc1b0-165">Follow these steps to set the global (Org-wide default) policies for each policy type.</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="cc1b0-166">Usando o centro de administração do Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="cc1b0-166">Using the Microsoft Teams admin center</span></span>

1. <span data-ttu-id="cc1b0-167">Na navegação à esquerda do centro de administração Microsoft Teams, vá para a página de política para o tipo de política que você deseja atualizar.</span><span class="sxs-lookup"><span data-stu-id="cc1b0-167">In the left navigation of the Microsoft Teams admin center, go to the policy page for the policy type you want to update.</span></span> <span data-ttu-id="cc1b0-168">Por exemplo, **Teams**  >  **Teams** políticas, políticas   >  **de Reuniões,** políticas **de** mensagens ou políticas **de Chamada** de  >  **Voz.**</span><span class="sxs-lookup"><span data-stu-id="cc1b0-168">For example, **Teams** > **Teams policies**, **Meetings** > **Meetings policies**, **Messaging policies**, or **Voice** > **Calling policies**.</span></span>
2. <span data-ttu-id="cc1b0-169">Selecione a **política Global (padrão em toda** a organização) para exibir as configurações atuais.</span><span class="sxs-lookup"><span data-stu-id="cc1b0-169">Select the **Global (Org-wide default)** policy to view the current settings.</span></span>
3. <span data-ttu-id="cc1b0-170">Atualize a política conforme necessário e selecione **Aplicar**.</span><span class="sxs-lookup"><span data-stu-id="cc1b0-170">Update the policy as needed, and then select **Apply**.</span></span>

### <a name="using-powershell"></a><span data-ttu-id="cc1b0-171">Usando o Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="cc1b0-171">Using PowerShell</span></span>

<span data-ttu-id="cc1b0-172">Para definir as políticas globais usando o PowerShell, use o identificador Global.</span><span class="sxs-lookup"><span data-stu-id="cc1b0-172">To set the global policies using PowerShell, use the Global identifier.</span></span>  <span data-ttu-id="cc1b0-173">Comece revendo a política global atual para determinar qual configuração você deseja alterar.</span><span class="sxs-lookup"><span data-stu-id="cc1b0-173">Start by reviewing the current Global policy to determine which setting you want to change.</span></span>

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

<span data-ttu-id="cc1b0-174">Em seguida, atualize a política Global conforme necessário.</span><span class="sxs-lookup"><span data-stu-id="cc1b0-174">Next, update the Global policy as needed.</span></span>  <span data-ttu-id="cc1b0-175">Você só precisa especificar valores para as configurações que deseja alterar.</span><span class="sxs-lookup"><span data-stu-id="cc1b0-175">You only need to specify values for the settings that you want to change.</span></span>

```powershell
Set-CsTeamsMessagingPolicy -Identity Global -AllowUserEditMessage $false
```

## <a name="assign-a-policy-to-individual-users"></a><span data-ttu-id="cc1b0-176">Atribuir uma política a usuários individuais</span><span class="sxs-lookup"><span data-stu-id="cc1b0-176">Assign a policy to individual users</span></span>

<span data-ttu-id="cc1b0-177">Siga estas etapas para atribuir uma política a um usuário individual ou a um pequeno número de usuários por vez.</span><span class="sxs-lookup"><span data-stu-id="cc1b0-177">Follow these steps to assign a policy to an individual user or to a small number of users at a time.</span></span>

### <a name="use-the-microsoft-teams-admin-center"></a><span data-ttu-id="cc1b0-178">Usar o Microsoft Teams de administração</span><span class="sxs-lookup"><span data-stu-id="cc1b0-178">Use the Microsoft Teams admin center</span></span>

<span data-ttu-id="cc1b0-179">Para atribuir uma política a um usuário:</span><span class="sxs-lookup"><span data-stu-id="cc1b0-179">To assign a policy to a user:</span></span>

1. <span data-ttu-id="cc1b0-180">Na navegação à esquerda do centro de administração Microsoft Teams, vá para **Usuários** e selecione o usuário.</span><span class="sxs-lookup"><span data-stu-id="cc1b0-180">In the left navigation of the Microsoft Teams admin center, go to **Users**, and then select the user.</span></span>
2. <span data-ttu-id="cc1b0-181">Selecione o usuário clicando à esquerda do nome do usuário e selecione **Editar configurações**.</span><span class="sxs-lookup"><span data-stu-id="cc1b0-181">Select the user by clicking to the left of the user name, and then select **Edit settings**.</span></span>
3. <span data-ttu-id="cc1b0-182">Selecione a política que deseja atribuir e selecione **Aplicar**.</span><span class="sxs-lookup"><span data-stu-id="cc1b0-182">Select the policy you want to assign, and then select **Apply**.</span></span>

<span data-ttu-id="cc1b0-183">Ou você também pode fazer o seguinte:</span><span class="sxs-lookup"><span data-stu-id="cc1b0-183">Or, you can also do the following:</span></span>

1. <span data-ttu-id="cc1b0-184">Na navegação à esquerda do centro de administração Microsoft Teams, vá para a página de política.</span><span class="sxs-lookup"><span data-stu-id="cc1b0-184">In the left navigation of the Microsoft Teams admin center, go to the policy page.</span></span>
2. <span data-ttu-id="cc1b0-185">Selecione a política que você deseja atribuir clicando à esquerda do nome da política.</span><span class="sxs-lookup"><span data-stu-id="cc1b0-185">Select the policy you want to assign by clicking to the left of the policy name.</span></span>
3. <span data-ttu-id="cc1b0-186">Escolha **Gerenciar usuários**.</span><span class="sxs-lookup"><span data-stu-id="cc1b0-186">Select **Manage users**.</span></span>
4. <span data-ttu-id="cc1b0-187">No painel **Gerenciar usuários**, procure o usuário pelo nome de exibição ou pelo nome de usuário, escolha o nome e marque **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="cc1b0-187">In the **Manage users** pane, search for the user by display name or by user name, select the name, and then select **Add**.</span></span> <span data-ttu-id="cc1b0-188">Repita esta etapa para cada usuário que você deseja adicionar.</span><span class="sxs-lookup"><span data-stu-id="cc1b0-188">Repeat this step for each user that you want to add.</span></span>
5. <span data-ttu-id="cc1b0-189">Quando terminar de adicionar usuários, selecione **Aplicar**.</span><span class="sxs-lookup"><span data-stu-id="cc1b0-189">When you're finished adding users, select **Apply**.</span></span>

### <a name="use-powershell"></a><span data-ttu-id="cc1b0-190">Usar o PowerShell</span><span class="sxs-lookup"><span data-stu-id="cc1b0-190">Use PowerShell</span></span>

<span data-ttu-id="cc1b0-191">Cada tipo de política tem seu próprio conjunto de cmdlets para gere-lo.</span><span class="sxs-lookup"><span data-stu-id="cc1b0-191">Each policy type has its own set of cmdlets for managing it.</span></span> <span data-ttu-id="cc1b0-192">Use o ```Grant-``` cmdlet para um determinado tipo de política para atribuir a política.</span><span class="sxs-lookup"><span data-stu-id="cc1b0-192">Use the ```Grant-``` cmdlet for a given policy type to assign the policy.</span></span> <span data-ttu-id="cc1b0-193">Por exemplo, use o ```Grant-CsTeamsMeetingPolicy``` cmdlet para atribuir uma Teams de reunião aos usuários.</span><span class="sxs-lookup"><span data-stu-id="cc1b0-193">For example, use the ```Grant-CsTeamsMeetingPolicy``` cmdlet to assign a Teams meeting policy to users.</span></span> <span data-ttu-id="cc1b0-194">Esses cmdlets estão incluídos no módulo Teams PowerShell e estão documentados na referência Skype for Business [cmdlet .](/powershell/skype/intro?view=skype-ps)</span><span class="sxs-lookup"><span data-stu-id="cc1b0-194">These cmdlets are included in the Teams PowerShell module and are documented in the [Skype for Business cmdlet reference](/powershell/skype/intro?view=skype-ps).</span></span>

<span data-ttu-id="cc1b0-195">Baixe e instale o Teams versão pública do [PowerShell](https://www.powershellgallery.com/packages/MicrosoftTeams/) (caso ainda não tenha feito isso) e execute o seguinte para se conectar.</span><span class="sxs-lookup"><span data-stu-id="cc1b0-195">Download and install the [Teams PowerShell public release](https://www.powershellgallery.com/packages/MicrosoftTeams/) (if you haven't already), and then run the following to connect.</span></span>

> [!NOTE]
> <span data-ttu-id="cc1b0-196">O Conector Skype for Business Online atualmente faz parte do módulo mais recente do PowerShell do Teams.</span><span class="sxs-lookup"><span data-stu-id="cc1b0-196">Skype for Business Online Connector is currently part of the latest Teams PowerShell module.</span></span>
>
> <span data-ttu-id="cc1b0-197">Se você estiver usando a versão pública mais [recente Teams PowerShell,](https://www.powershellgallery.com/packages/MicrosoftTeams/)não será necessário instalar o conector Skype for Business Online.</span><span class="sxs-lookup"><span data-stu-id="cc1b0-197">If you're using the latest [Teams PowerShell public release](https://www.powershellgallery.com/packages/MicrosoftTeams/), you don't need to install the Skype for Business Online Connector.</span></span>

```powershell
# When using Teams PowerShell Module

Import-Module MicrosoftTeams
$credential = Get-Credential
Connect-MicrosoftTeams -Credential $credential
```

<span data-ttu-id="cc1b0-198">Neste exemplo, atribuímos uma política de reunião Teams chamada Diretiva de Reunião de Alunos a um usuário chamado Reda.</span><span class="sxs-lookup"><span data-stu-id="cc1b0-198">In this example, we assign a Teams meeting policy named Student Meeting Policy to a user named Reda.</span></span>

```powershell
Grant-CsTeamsMeetingPolicy -Identity reda@contoso.com -PolicyName "Student Meeting Policy"
```

<span data-ttu-id="cc1b0-199">Para saber mais, leia [Gerenciar políticas por meio do PowerShell](teams-powershell-managing-teams.md#manage-policies-via-powershell).</span><span class="sxs-lookup"><span data-stu-id="cc1b0-199">To learn more, read [Manage policies via PowerShell](teams-powershell-managing-teams.md#manage-policies-via-powershell).</span></span>

## <a name="assign-a-policy-to-a-group"></a><span data-ttu-id="cc1b0-200">Atribuir uma política a um grupo</span><span class="sxs-lookup"><span data-stu-id="cc1b0-200">Assign a policy to a group</span></span>

<span data-ttu-id="cc1b0-201">A atribuição de política a grupos permite atribuir uma política a um grupo de usuários, como um grupo de segurança ou uma lista de distribuição.</span><span class="sxs-lookup"><span data-stu-id="cc1b0-201">Policy assignment to groups lets you assign a policy to a group of users, such as a security group or distribution list.</span></span> <span data-ttu-id="cc1b0-202">As atribuições de política serão propagadas para os membros do grupo, de acordo com as regras de precedência.</span><span class="sxs-lookup"><span data-stu-id="cc1b0-202">The policy assignment is propagated to members of the group according to precedence rules.</span></span> <span data-ttu-id="cc1b0-203">À medida que os membros forem adicionados ou removidos de um grupo, as atribuições de política herdadas serão atualizadas.</span><span class="sxs-lookup"><span data-stu-id="cc1b0-203">As members are added to or removed from a group, their inherited policy assignments are updated accordingly.</span></span>

<span data-ttu-id="cc1b0-204">A atribuição de política a grupos é recomendada para grupos de até 50.000 usuários, mas também funcionará com grupos maiores.</span><span class="sxs-lookup"><span data-stu-id="cc1b0-204">Policy assignment to groups is recommended for groups of up to 50,000 users but it will also work with larger groups.</span></span>

<span data-ttu-id="cc1b0-205">Quando você atribui a política, ela é imediatamente atribuída ao grupo.</span><span class="sxs-lookup"><span data-stu-id="cc1b0-205">When you assign the policy, it's immediately assigned to the group.</span></span> <span data-ttu-id="cc1b0-206">No entanto, a propagação da atribuição de política aos membros do grupo é executada como uma operação em segundo plano e pode levar algum tempo, dependendo do tamanho do grupo.</span><span class="sxs-lookup"><span data-stu-id="cc1b0-206">However, the propagation of the policy assignment to members of the group is performed as a background operation and might take some time, depending on the size of the group.</span></span> <span data-ttu-id="cc1b0-207">O mesmo acontece quando uma política não é atribuída a um grupo ou quando os membros são adicionados ou removidos de um grupo.</span><span class="sxs-lookup"><span data-stu-id="cc1b0-207">The same is true when a policy is unassigned from a group, or when members are added to or removed from a group.</span></span>

<span data-ttu-id="cc1b0-208">As atribuições de política de grupo são propagadas apenas para usuários que são membros diretos do grupo.</span><span class="sxs-lookup"><span data-stu-id="cc1b0-208">Group policy assignments are only propagated to users who are direct members of the group.</span></span> <span data-ttu-id="cc1b0-209">As atribuições não são propagadas para membros de grupos aninhados.</span><span class="sxs-lookup"><span data-stu-id="cc1b0-209">The assignments aren't propagated to members of nested groups.</span></span>

### <a name="what-you-need-to-know-about-policy-assignment-to-groups"></a><span data-ttu-id="cc1b0-210">O que você precisa saber sobre a atribuição de política a grupos</span><span class="sxs-lookup"><span data-stu-id="cc1b0-210">What you need to know about policy assignment to groups</span></span>

<span data-ttu-id="cc1b0-211">Antes de começar, é importante entender as regras de precedência e a classificação de atribuição de grupo.</span><span class="sxs-lookup"><span data-stu-id="cc1b0-211">Before you get started, it's important to understand precedence rules and group assignment ranking.</span></span>

#### <a name="precedence-rules"></a><span data-ttu-id="cc1b0-212">Regras de precedência</span><span class="sxs-lookup"><span data-stu-id="cc1b0-212">Precedence rules</span></span>

<span data-ttu-id="cc1b0-213">Para um determinado tipo de política, a política efetiva de um usuário é determinada de acordo com o seguinte:</span><span class="sxs-lookup"><span data-stu-id="cc1b0-213">For a given policy type, a user's effective policy is determined according to the following:</span></span>

- <span data-ttu-id="cc1b0-214">Uma política atribuída diretamente a um usuário tem precedência sobre qualquer outra política do mesmo tipo atribuída a um grupo.</span><span class="sxs-lookup"><span data-stu-id="cc1b0-214">A policy that's directly assigned to a user takes precedence over any other policy of the same type that's assigned to a group.</span></span> <span data-ttu-id="cc1b0-215">Em outras palavras, se um usuário receber diretamente uma política de um determinado tipo, esse usuário não herdará uma política do mesmo tipo de um grupo.</span><span class="sxs-lookup"><span data-stu-id="cc1b0-215">In other words, if a user is directly assigned a policy of a given type, that user won't inherit a policy of the same type from a group.</span></span> <span data-ttu-id="cc1b0-216">Isso também significa que, se um usuário tiver uma política de um determinado tipo atribuído diretamente a ele, você terá que remover essa política do usuário antes que ele possa herdar uma política do mesmo tipo de um grupo.</span><span class="sxs-lookup"><span data-stu-id="cc1b0-216">This also means that if a user has a policy of a given type that was directly assigned to them, you have to remove that policy from the user before they can inherit a policy of the same type from a group.</span></span>

- <span data-ttu-id="cc1b0-217">Se um usuário não tiver uma política atribuída diretamente a ele e for membro de dois ou mais grupos e cada grupo tiver uma política do mesmo tipo atribuído a ela, o usuário herdará a política da atribuição de grupo com a classificação mais alta.</span><span class="sxs-lookup"><span data-stu-id="cc1b0-217">If a user doesn't have a policy directly assigned to them and is a member of two or more groups and each group has a policy of the same type assigned to it, the user inherits the policy of the group assignment that has the highest ranking.</span></span>

- <span data-ttu-id="cc1b0-218">Se um usuário não for membro de nenhum grupo atribuído a uma política, a política global (padrão em toda a organização) para esse tipo de política se aplica ao usuário.</span><span class="sxs-lookup"><span data-stu-id="cc1b0-218">If a user isn't a member of any groups that are assigned a policy, the global (Org-wide default) policy for that policy type applies to the user.</span></span>

<span data-ttu-id="cc1b0-219">A política efetiva de um usuário é atualizada de acordo com estas regras:</span><span class="sxs-lookup"><span data-stu-id="cc1b0-219">A user's effective policy is updated according to these rules:</span></span>

- <span data-ttu-id="cc1b0-220">quando um usuário é adicionado ou removido de um grupo atribuído a uma política.</span><span class="sxs-lookup"><span data-stu-id="cc1b0-220">when a user is added to or removed from a group that's assigned a policy.</span></span>
- <span data-ttu-id="cc1b0-221">uma política não é atribuída a partir de um grupo.</span><span class="sxs-lookup"><span data-stu-id="cc1b0-221">a policy is unassigned from a group.</span></span>
- <span data-ttu-id="cc1b0-222">uma política atribuída diretamente ao usuário é removida.</span><span class="sxs-lookup"><span data-stu-id="cc1b0-222">a policy that's directly assigned to the user is removed.</span></span>

#### <a name="group-assignment-ranking"></a><span data-ttu-id="cc1b0-223">Classificação de atribuição de grupo</span><span class="sxs-lookup"><span data-stu-id="cc1b0-223">Group assignment ranking</span></span>

<span data-ttu-id="cc1b0-224">Quando você atribui uma política a um grupo, especifica uma classificação para a atribuição de grupo.</span><span class="sxs-lookup"><span data-stu-id="cc1b0-224">When you assign a policy to a group, you specify a ranking for the group assignment.</span></span> <span data-ttu-id="cc1b0-225">Isso é usado para determinar qual política um usuário deve herdar como sua política efetiva se o usuário for membro de dois ou mais grupos e cada grupo receber uma política do mesmo tipo.</span><span class="sxs-lookup"><span data-stu-id="cc1b0-225">This is used to determine which policy a user should inherit as their effective policy if the user is a member of two or more groups and each group is assigned a policy of the same type.</span></span>

<span data-ttu-id="cc1b0-226">A classificação de atribuição de grupo é relativa a outras atribuições de grupo do mesmo tipo.</span><span class="sxs-lookup"><span data-stu-id="cc1b0-226">The group assignment ranking is relative to other group assignments of the same type.</span></span> <span data-ttu-id="cc1b0-227">Por exemplo, se você estiver atribuindo uma política de chamada a dois grupos, de definir a classificação de uma atribuição como 1 e a outra como 2, sendo 1 a classificação mais alta.</span><span class="sxs-lookup"><span data-stu-id="cc1b0-227">For example, if you're assigning a calling policy to two groups, set the ranking of one assignment to 1 and the other to 2, with 1 being the highest ranking.</span></span> <span data-ttu-id="cc1b0-228">A classificação de atribuição de grupo indica qual associação de grupo é mais importante ou mais relevante do que outras associações de grupo em relação à herança.</span><span class="sxs-lookup"><span data-stu-id="cc1b0-228">The group assignment ranking indicates which group membership is more important or more relevant than other group memberships regarding inheritance.</span></span>

<span data-ttu-id="cc1b0-229">Por exemplo, você tem dois grupos, Funcionários da Loja e Gerentes da Loja.</span><span class="sxs-lookup"><span data-stu-id="cc1b0-229">Say, for example, you have two groups, Store Employees and Store Managers.</span></span> <span data-ttu-id="cc1b0-230">Ambos os grupos são atribuídos a uma política de Teams de chamada, a Política de Chamada de Funcionários da Loja e a Política de Chamada de Gerentes de Loja, respectivamente.</span><span class="sxs-lookup"><span data-stu-id="cc1b0-230">Both groups are assigned a Teams calling policy, Store Employees Calling Policy and Store Managers Calling Policy, respectively.</span></span> <span data-ttu-id="cc1b0-231">Para um gerente de loja que está em ambos os grupos, sua função como gerente é mais relevante do que sua função como funcionário, portanto, a política de chamada atribuída ao grupo Gerentes de Loja deve ter uma classificação mais alta.</span><span class="sxs-lookup"><span data-stu-id="cc1b0-231">For a store manager who is in both groups, their role as a manager is more relevant than their role as an employee, so the calling policy that's assigned to the Store Managers group should have a higher ranking.</span></span>

|<span data-ttu-id="cc1b0-232">Grupo</span><span class="sxs-lookup"><span data-stu-id="cc1b0-232">Group</span></span> |<span data-ttu-id="cc1b0-233">Teams nome da política de chamada</span><span class="sxs-lookup"><span data-stu-id="cc1b0-233">Teams calling policy name</span></span>  |<span data-ttu-id="cc1b0-234">Classificação</span><span class="sxs-lookup"><span data-stu-id="cc1b0-234">Rank</span></span>|
|---------|---------|---|
|<span data-ttu-id="cc1b0-235">Gerentes da Loja</span><span class="sxs-lookup"><span data-stu-id="cc1b0-235">Store Managers</span></span>   |<span data-ttu-id="cc1b0-236">Política de Chamada de Gerentes de Loja</span><span class="sxs-lookup"><span data-stu-id="cc1b0-236">Store Managers Calling Policy</span></span>         |<span data-ttu-id="cc1b0-237">1</span><span class="sxs-lookup"><span data-stu-id="cc1b0-237">1</span></span>|
|<span data-ttu-id="cc1b0-238">Funcionários da Loja</span><span class="sxs-lookup"><span data-stu-id="cc1b0-238">Store Employees</span></span>    |<span data-ttu-id="cc1b0-239">Política de Chamada de Funcionários da Loja</span><span class="sxs-lookup"><span data-stu-id="cc1b0-239">Store Employees Calling Policy</span></span>      |<span data-ttu-id="cc1b0-240">2</span><span class="sxs-lookup"><span data-stu-id="cc1b0-240">2</span></span>|

<span data-ttu-id="cc1b0-241">Se você não especificar uma classificação, a atribuição de política recebe a classificação mais baixa.</span><span class="sxs-lookup"><span data-stu-id="cc1b0-241">If you don't specify a ranking, the policy assignment is given the lowest ranking.</span></span>

### <a name="in-the-teams-admin-center"></a><span data-ttu-id="cc1b0-242">No centro de Teams de administração</span><span class="sxs-lookup"><span data-stu-id="cc1b0-242">In the Teams admin center</span></span>

> [!NOTE]
> <span data-ttu-id="cc1b0-243">Atualmente, a atribuição de política para grupos usando o centro de administração do Microsoft Teams está disponível apenas para a política de chamada do Teams, a política de estacionamento de chamada do Teams, Teams política de Teams, Teams política de eventos ao vivo, Teams política de reunião e Teams de mensagens.</span><span class="sxs-lookup"><span data-stu-id="cc1b0-243">Currently, policy assignment to groups using the Microsoft Teams admin center is only available for Teams calling policy, Teams call park policy, Teams policy, Teams live events policy, Teams meeting policy, and Teams messaging policy.</span></span> <span data-ttu-id="cc1b0-244">Para outros tipos de política, use o PowerShell.</span><span class="sxs-lookup"><span data-stu-id="cc1b0-244">For other policy types, use PowerShell.</span></span>

1. <span data-ttu-id="cc1b0-245">Na navegação à esquerda do centro de administração Microsoft Teams, vá para a página tipo de política.</span><span class="sxs-lookup"><span data-stu-id="cc1b0-245">In the left navigation of the Microsoft Teams admin center, go to the policy type page.</span></span> <span data-ttu-id="cc1b0-246">Por exemplo, vá para **Políticas de Reunião** de  >  **Reuniões.**</span><span class="sxs-lookup"><span data-stu-id="cc1b0-246">For example, go to **Meetings** > **Meeting policies**.</span></span>

2. <span data-ttu-id="cc1b0-247">Selecione a **guia Atribuição de política de** grupo.</span><span class="sxs-lookup"><span data-stu-id="cc1b0-247">Select the **Group policy assignment** tab.</span></span>

3. <span data-ttu-id="cc1b0-248">Selecione **Adicionar grupo** e, em seguida, no painel Atribuir **política** ao grupo, faça o seguinte:</span><span class="sxs-lookup"><span data-stu-id="cc1b0-248">Select **Add group**, and then in the **Assign policy to group** pane, do the following:</span></span>
    1. <span data-ttu-id="cc1b0-249">Pesquise e adicione o grupo ao que você deseja atribuir a política.</span><span class="sxs-lookup"><span data-stu-id="cc1b0-249">Search for and add the group you want to assign the policy to.</span></span>
    2. <span data-ttu-id="cc1b0-250">De definir a classificação para a atribuição de grupo.</span><span class="sxs-lookup"><span data-stu-id="cc1b0-250">Set the ranking for the group assignment.</span></span>
    3. <span data-ttu-id="cc1b0-251">Selecione a política que você deseja atribuir.</span><span class="sxs-lookup"><span data-stu-id="cc1b0-251">Select the policy that you want to assign.</span></span>
    4. <span data-ttu-id="cc1b0-252">Selecione **Aplicar**.</span><span class="sxs-lookup"><span data-stu-id="cc1b0-252">Select **Apply**.</span></span>

<span data-ttu-id="cc1b0-253">Para remover uma atribuição de política de grupo, na **guia** Atribuição de política de grupo da página de política, selecione a atribuição de grupo e selecione **Remover**.</span><span class="sxs-lookup"><span data-stu-id="cc1b0-253">To remove a group policy assignment, on the **Group policy assignment** tab of the policy page, select the group assignment, and then select **Remove**.</span></span>

<span data-ttu-id="cc1b0-254">Para alterar a classificação de uma atribuição de grupo, você precisa primeiro remover a atribuição de política de grupo.</span><span class="sxs-lookup"><span data-stu-id="cc1b0-254">To change the ranking of a group assignment, you have to first remove the group policy assignment.</span></span> <span data-ttu-id="cc1b0-255">Em seguida, siga as etapas acima para atribuir a política a um grupo.</span><span class="sxs-lookup"><span data-stu-id="cc1b0-255">Then, follow the steps above to assign the policy to a group.</span></span>

### <a name="use-the-powershell-option"></a><span data-ttu-id="cc1b0-256">Usar a opção PowerShell</span><span class="sxs-lookup"><span data-stu-id="cc1b0-256">Use the PowerShell option</span></span>

> [!NOTE]
> <span data-ttu-id="cc1b0-257">Atualmente, a atribuição de política a grupos usando o PowerShell não está disponível para todos os tipos Teams de política.</span><span class="sxs-lookup"><span data-stu-id="cc1b0-257">Currently, policy assignment to groups using PowerShell isn't available for all Teams policy types.</span></span> <span data-ttu-id="cc1b0-258">Consulte [New-CsGroupPolicyAssignment para](/powershell/module/teams/new-csgrouppolicyassignment) a lista de tipos de política com suporte.</span><span class="sxs-lookup"><span data-stu-id="cc1b0-258">See [New-CsGroupPolicyAssignment](/powershell/module/teams/new-csgrouppolicyassignment) for the list of supported policy types.</span></span>

#### <a name="install-and-connect-to-the-microsoft-teams-powershell-module"></a><span data-ttu-id="cc1b0-259">Instalar e conectar ao módulo Microsoft Teams PowerShell</span><span class="sxs-lookup"><span data-stu-id="cc1b0-259">Install and connect to the Microsoft Teams PowerShell module</span></span>

<span data-ttu-id="cc1b0-260">Para obter orientações passo a passo, consulte [Install Teams PowerShell](teams-powershell-install.md).</span><span class="sxs-lookup"><span data-stu-id="cc1b0-260">For step-by-step guidance, see [Install Teams PowerShell](teams-powershell-install.md).</span></span>

#### <a name="assign-a-policy-to-a-group-of-users"></a><span data-ttu-id="cc1b0-261">Atribuir uma política a um grupo de usuários</span><span class="sxs-lookup"><span data-stu-id="cc1b0-261">Assign a policy to a group of users</span></span>

<span data-ttu-id="cc1b0-262">Use o cmdlet [New-CsGroupPolicyAssignment](/powershell/module/teams/new-csgrouppolicyassignment) para atribuir uma política a um grupo.</span><span class="sxs-lookup"><span data-stu-id="cc1b0-262">Use the [New-CsGroupPolicyAssignment](/powershell/module/teams/new-csgrouppolicyassignment) cmdlet to assign a policy to a group.</span></span> <span data-ttu-id="cc1b0-263">Você pode especificar um grupo usando a ID do objeto, endereço SIP ou endereço de email.</span><span class="sxs-lookup"><span data-stu-id="cc1b0-263">You can specify a group by using the object ID, SIP address, or email address.</span></span>

<span data-ttu-id="cc1b0-264">Neste exemplo, atribuímos uma política de reunião Teams chamada Política de Reunião de Gerentes de Varejo a um grupo com uma classificação de atribuição de 1.</span><span class="sxs-lookup"><span data-stu-id="cc1b0-264">In this example, we assign a Teams meeting policy named Retail Managers Meeting Policy to a group with an assignment ranking of 1.</span></span>

```powershell
New-CsGroupPolicyAssignment -GroupId d8ebfa45-0f28-4d2d-9bcc-b158a49e2d17 -PolicyType TeamsMeetingPolicy -PolicyName "Retail Managers Meeting Policy" -Rank 1
```

#### <a name="get-policy-assignments-for-a-group"></a><span data-ttu-id="cc1b0-265">Obter atribuições de política para um grupo</span><span class="sxs-lookup"><span data-stu-id="cc1b0-265">Get policy assignments for a group</span></span>

<span data-ttu-id="cc1b0-266">Use o cmdlet [Get-CsGroupPolicyAssignment](/powershell/module/teams/get-csgrouppolicyassignment) para obter todas as políticas atribuídas a um grupo.</span><span class="sxs-lookup"><span data-stu-id="cc1b0-266">Use the [Get-CsGroupPolicyAssignment](/powershell/module/teams/get-csgrouppolicyassignment) cmdlet to get all policies assigned to a group.</span></span> <span data-ttu-id="cc1b0-267">Observe que os grupos sempre são listados pela ID do grupo, mesmo que seu endereço SIP ou endereço de email seja usado para atribuir a política.</span><span class="sxs-lookup"><span data-stu-id="cc1b0-267">Note that groups are always listed by their group ID even if its SIP address or email address was used to assign the policy.</span></span>

<span data-ttu-id="cc1b0-268">Neste exemplo, recuperamos todas as políticas atribuídas a um grupo específico.</span><span class="sxs-lookup"><span data-stu-id="cc1b0-268">In this example, we retrieve all policies assigned to a specific group.</span></span>

```powershell
Get-CsGroupPolicyAssignment -GroupId e050ce51-54bc-45b7-b3e6-c00343d31274
```

<span data-ttu-id="cc1b0-269">Neste exemplo, retornamos todos os grupos que são atribuídos a uma Teams de reunião.</span><span class="sxs-lookup"><span data-stu-id="cc1b0-269">In this example, we return all groups that are assigned a Teams meeting policy.</span></span>

```powershell
Get-CsGroupPolicyAssignment -PolicyType TeamsMeetingPolicy
```

#### <a name="remove-a-policy-from-a-group"></a><span data-ttu-id="cc1b0-270">Remover uma política de um grupo</span><span class="sxs-lookup"><span data-stu-id="cc1b0-270">Remove a policy from a group</span></span>

<span data-ttu-id="cc1b0-271">Use o cmdlet [Remove-CsGroupPolicyAssignment](/powershell/module/teams/remove-csgrouppolicyassignment) para remover uma política de um grupo.</span><span class="sxs-lookup"><span data-stu-id="cc1b0-271">Use the [Remove-CsGroupPolicyAssignment](/powershell/module/teams/remove-csgrouppolicyassignment) cmdlet to remove a policy from a group.</span></span> <span data-ttu-id="cc1b0-272">Quando você remove uma política de um grupo, as prioridades de outras políticas do mesmo tipo atribuído a esse grupo, e que têm uma classificação mais baixa, são atualizadas.</span><span class="sxs-lookup"><span data-stu-id="cc1b0-272">When you remove a policy from a group, the priorities of other policies of the same type assigned to that group, and that have a lower ranking, are updated.</span></span> <span data-ttu-id="cc1b0-273">Por exemplo, se você remover uma política que tenha uma classificação de 2, as políticas que têm uma classificação de 3 e 4 serão atualizadas para refletir sua nova classificação.</span><span class="sxs-lookup"><span data-stu-id="cc1b0-273">For example, if you remove a policy that has a ranking of 2, policies that have a ranking of 3 and 4 are updated to reflect their new ranking.</span></span> <span data-ttu-id="cc1b0-274">As duas tabelas a seguir mostram este exemplo.</span><span class="sxs-lookup"><span data-stu-id="cc1b0-274">The following two tables show this example.</span></span>

<span data-ttu-id="cc1b0-275">Aqui está uma lista das atribuições de política e prioridades para uma Teams de reunião.</span><span class="sxs-lookup"><span data-stu-id="cc1b0-275">Here's a list of the policy assignments and priorities for a Teams meeting policy.</span></span>

|<span data-ttu-id="cc1b0-276">Nome do grupo</span><span class="sxs-lookup"><span data-stu-id="cc1b0-276">Group name</span></span>  |<span data-ttu-id="cc1b0-277">Nome da política</span><span class="sxs-lookup"><span data-stu-id="cc1b0-277">Policy name</span></span>  |<span data-ttu-id="cc1b0-278">Classificação</span><span class="sxs-lookup"><span data-stu-id="cc1b0-278">Rank</span></span>|
|---------|---------|---------|
|<span data-ttu-id="cc1b0-279">Vendas</span><span class="sxs-lookup"><span data-stu-id="cc1b0-279">Sales</span></span>    |<span data-ttu-id="cc1b0-280">Política de vendas</span><span class="sxs-lookup"><span data-stu-id="cc1b0-280">Sales policy</span></span>       | <span data-ttu-id="cc1b0-281">1</span><span class="sxs-lookup"><span data-stu-id="cc1b0-281">1</span></span>        |
|<span data-ttu-id="cc1b0-282">Região Oeste</span><span class="sxs-lookup"><span data-stu-id="cc1b0-282">West Region</span></span>     |<span data-ttu-id="cc1b0-283">Política da Região Oeste</span><span class="sxs-lookup"><span data-stu-id="cc1b0-283">West Region policy</span></span>         |<span data-ttu-id="cc1b0-284">2</span><span class="sxs-lookup"><span data-stu-id="cc1b0-284">2</span></span>         |
|<span data-ttu-id="cc1b0-285">Division</span><span class="sxs-lookup"><span data-stu-id="cc1b0-285">Division</span></span>    |<span data-ttu-id="cc1b0-286">Política de divisão</span><span class="sxs-lookup"><span data-stu-id="cc1b0-286">Division policy</span></span>         |<span data-ttu-id="cc1b0-287">3</span><span class="sxs-lookup"><span data-stu-id="cc1b0-287">3</span></span>         |
|<span data-ttu-id="cc1b0-288">Subsidiária</span><span class="sxs-lookup"><span data-stu-id="cc1b0-288">Subsidiary</span></span>   |<span data-ttu-id="cc1b0-289">Política de subsidiária</span><span class="sxs-lookup"><span data-stu-id="cc1b0-289">Subsidiary policy</span></span>        |<span data-ttu-id="cc1b0-290">4</span><span class="sxs-lookup"><span data-stu-id="cc1b0-290">4</span></span>         |

<span data-ttu-id="cc1b0-291">Se removermos a política da Região Oeste do grupo da Região Oeste, as atribuições e prioridades de política serão atualizadas da seguinte forma.</span><span class="sxs-lookup"><span data-stu-id="cc1b0-291">If we remove the West Region policy from the West Region group, the policy assignments and priorities are updated as follows.</span></span>

|<span data-ttu-id="cc1b0-292">Nome do grupo</span><span class="sxs-lookup"><span data-stu-id="cc1b0-292">Group name</span></span>  |<span data-ttu-id="cc1b0-293">Nome da política</span><span class="sxs-lookup"><span data-stu-id="cc1b0-293">Policy name</span></span>  |<span data-ttu-id="cc1b0-294">Classificação</span><span class="sxs-lookup"><span data-stu-id="cc1b0-294">Rank</span></span>|
|---------|---------|---------|
|<span data-ttu-id="cc1b0-295">Vendas</span><span class="sxs-lookup"><span data-stu-id="cc1b0-295">Sales</span></span>    |<span data-ttu-id="cc1b0-296">Política de vendas</span><span class="sxs-lookup"><span data-stu-id="cc1b0-296">Sales policy</span></span>       | <span data-ttu-id="cc1b0-297">1</span><span class="sxs-lookup"><span data-stu-id="cc1b0-297">1</span></span>        |
|<span data-ttu-id="cc1b0-298">Division</span><span class="sxs-lookup"><span data-stu-id="cc1b0-298">Division</span></span>    |<span data-ttu-id="cc1b0-299">Política de divisão</span><span class="sxs-lookup"><span data-stu-id="cc1b0-299">Division policy</span></span>         |<span data-ttu-id="cc1b0-300">2</span><span class="sxs-lookup"><span data-stu-id="cc1b0-300">2</span></span>         |
|<span data-ttu-id="cc1b0-301">Subsidiária</span><span class="sxs-lookup"><span data-stu-id="cc1b0-301">Subsidiary</span></span>   |<span data-ttu-id="cc1b0-302">Política de subsidiária</span><span class="sxs-lookup"><span data-stu-id="cc1b0-302">Subsidiary policy</span></span>        |<span data-ttu-id="cc1b0-303">3</span><span class="sxs-lookup"><span data-stu-id="cc1b0-303">3</span></span>        |

<span data-ttu-id="cc1b0-304">Neste exemplo, removemos a política Teams reunião de um grupo.</span><span class="sxs-lookup"><span data-stu-id="cc1b0-304">In this example, we remove the Teams meeting policy from a group.</span></span>

```powershell
Remove-CsGroupPolicyAssignment -PolicyType TeamsMeetingPolicy -GroupId f985e013-0826-40bb-8c94-e5f367076044
```

#### <a name="change-a-policy-assignment-for-a-group"></a><span data-ttu-id="cc1b0-305">Alterar uma atribuição de política para um grupo</span><span class="sxs-lookup"><span data-stu-id="cc1b0-305">Change a policy assignment for a group</span></span>

> [!NOTE]
> <span data-ttu-id="cc1b0-306">O cmdlet [Set-CsGroupPolicyAssignment](/powershell/module/teams/set-csgrouppolicyassignment) estará disponível em breve.</span><span class="sxs-lookup"><span data-stu-id="cc1b0-306">The [Set-CsGroupPolicyAssignment](/powershell/module/teams/set-csgrouppolicyassignment) cmdlet will be available soon.</span></span> <span data-ttu-id="cc1b0-307">Enquanto isso, para alterar uma atribuição de política de grupo, você pode remover a atribuição de política atual do grupo e adicionar uma nova atribuição de política.</span><span class="sxs-lookup"><span data-stu-id="cc1b0-307">In the meantime, to change a group policy assignment, you can remove the current policy assignment from the group, and then add a new policy assignment.</span></span>

<span data-ttu-id="cc1b0-308">Depois de atribuir uma política a um grupo, você pode usar o cmdlet [Set-CsGroupPolicyAssignment](/powershell/module/teams/set-csgrouppolicyassignment) para alterar a atribuição de política desse grupo da seguinte forma:</span><span class="sxs-lookup"><span data-stu-id="cc1b0-308">After you assign a policy to a group, you can use the [Set-CsGroupPolicyAssignment](/powershell/module/teams/set-csgrouppolicyassignment) cmdlet to change that group's policy assignment as follows:</span></span>

- <span data-ttu-id="cc1b0-309">Alterar a classificação</span><span class="sxs-lookup"><span data-stu-id="cc1b0-309">Change the ranking</span></span>
- <span data-ttu-id="cc1b0-310">Alterar a política de um determinado tipo de política</span><span class="sxs-lookup"><span data-stu-id="cc1b0-310">Change the policy of a given policy type</span></span>
- <span data-ttu-id="cc1b0-311">Alterar a política de um determinado tipo de política e a classificação</span><span class="sxs-lookup"><span data-stu-id="cc1b0-311">Change the policy of a given policy type and the ranking</span></span>

<span data-ttu-id="cc1b0-312">Neste exemplo, alteramos a política de estacionamento de chamada Teams grupo para uma política chamada SupportCallPark e a classificação de atribuição como 3.</span><span class="sxs-lookup"><span data-stu-id="cc1b0-312">In this example, we change a group's Teams call park policy to a policy named SupportCallPark and the assignment ranking to 3.</span></span>

```powershell
Set-CsGroupPolicyAssignment -GroupId 566b8d39-5c5c-4aaa-bc07-4f36278a1b38 -PolicyType TeamsMeetingPolicy -PolicyName SupportCallPark -Rank 3
```

#### <a name="change-the-effective-policy-for-a-user"></a><span data-ttu-id="cc1b0-313">Alterar a política efetiva para um usuário</span><span class="sxs-lookup"><span data-stu-id="cc1b0-313">Change the effective policy for a user</span></span>

<span data-ttu-id="cc1b0-314">Aqui está um exemplo de como alterar a política efetiva para um usuário que recebe diretamente uma política.</span><span class="sxs-lookup"><span data-stu-id="cc1b0-314">Here's an example of how to change the effective policy for a user who is directly assigned a policy.</span></span>

<span data-ttu-id="cc1b0-315">Primeiro, usamos o cmdlet [Get-CsUserPolicyAssignment](/powershell/module/teams/get-csuserpolicyassignment) juntamente com o parâmetro para obter detalhes das políticas de transmissão de reunião Teams associadas ao `PolicySource` usuário.</span><span class="sxs-lookup"><span data-stu-id="cc1b0-315">First, we use the [Get-CsUserPolicyAssignment](/powershell/module/teams/get-csuserpolicyassignment) cmdlet together with the `PolicySource` parameter to get details of the Teams meeting broadcast policies associated with the user.</span></span>

```powershell
Get-CsUserPolicyAssignment -Identity daniel@contoso.com -PolicyType TeamsMeetingBroadcastPolicy | select -ExpandProperty PolicySource
```

<span data-ttu-id="cc1b0-316">A saída mostra que o usuário recebeu diretamente uma política de transmissão de reunião Teams chamada Eventos de Funcionários, que tem precedência sobre a política chamada Vendor Live Events atribuída a um grupo ao qual o usuário pertence.</span><span class="sxs-lookup"><span data-stu-id="cc1b0-316">The output shows that the user was directly assigned a Teams meeting broadcast policy named Employee Events, which takes precedence over the policy named Vendor Live Events that's assigned to a group the user belongs to.</span></span>

```console
AssignmentType PolicyName         Reference
-------------- ----------         ---------
Direct         Employee Events
Group          Vendor Live Events 566b8d39-5c5c-4aaa-bc07-4f36278a1b38
```

<span data-ttu-id="cc1b0-317">Agora, removemos a política Eventos de Funcionários do usuário.</span><span class="sxs-lookup"><span data-stu-id="cc1b0-317">Now, we remove the Employee Events policy from the user.</span></span> <span data-ttu-id="cc1b0-318">Isso significa que o usuário não tem mais uma política de transmissão de reunião Teams atribuída diretamente a ele e herdará a política eventos ao vivo do fornecedor atribuída ao grupo ao que o usuário pertence.</span><span class="sxs-lookup"><span data-stu-id="cc1b0-318">This means that the user no longer has a Teams meeting broadcast policy directly assigned to them and will inherit the Vendor Live Events policy that's assigned to the group the user belongs to.</span></span>

<span data-ttu-id="cc1b0-319">Use o seguinte cmdlet no módulo Skype for Business PowerShell para fazer isso.</span><span class="sxs-lookup"><span data-stu-id="cc1b0-319">Use the following cmdlet in the Skype for Business PowerShell module to do this.</span></span>

```powershell
Grant-CsTeamsMeetingBroadcastPolicy -Identity daniel@contoso.com -PolicyName $null
```

<span data-ttu-id="cc1b0-320">Use o seguinte cmdlet no módulo Teams PowerShell para fazer isso em escala, embora uma atribuição de política em lote, onde $users é uma lista de usuários que você especificar.</span><span class="sxs-lookup"><span data-stu-id="cc1b0-320">Use following cmdlet in the Teams PowerShell module to do this at scale though a batch policy assignment, where $users is a list of users that you specify.</span></span>

```powershell
New-CsBatchPolicyAssignmentOperation -OperationName "Assigning null at bulk" -PolicyType TeamsMeetingBroadcastPolicy -PolicyName $null -Identity $users  
```

## <a name="assign-a-policy-to-a-batch-of-users"></a><span data-ttu-id="cc1b0-321">Atribuir uma política a um lote de usuários</span><span class="sxs-lookup"><span data-stu-id="cc1b0-321">Assign a policy to a batch of users</span></span>

### <a name="use-the-admin-center"></a><span data-ttu-id="cc1b0-322">Usar o centro de administração</span><span class="sxs-lookup"><span data-stu-id="cc1b0-322">Use the admin center</span></span>

<span data-ttu-id="cc1b0-323">Para atribuir uma política aos usuários em massa:</span><span class="sxs-lookup"><span data-stu-id="cc1b0-323">To assign a policy to users in bulk:</span></span>

1. <span data-ttu-id="cc1b0-324">Na navegação à esquerda do centro de administração Microsoft Teams, selecione **Usuários**.</span><span class="sxs-lookup"><span data-stu-id="cc1b0-324">In the left navigation of the Microsoft Teams admin center, select **Users**.</span></span>

2. <span data-ttu-id="cc1b0-325">Pesquise os usuários aos que você deseja atribuir a política ou filtre a exibição para mostrar os usuários que você deseja.</span><span class="sxs-lookup"><span data-stu-id="cc1b0-325">Search for the users you want to assign the policy to or filter the view to show the users you want.</span></span>

3. <span data-ttu-id="cc1b0-326">Na coluna **&#x2713;** (marca de seleção), selecione os usuários.</span><span class="sxs-lookup"><span data-stu-id="cc1b0-326">In the **&#x2713;** (check mark) column, select the users.</span></span> <span data-ttu-id="cc1b0-327">Para selecionar todos os usuários, clique na (marca de seleção) &#x2713; na parte superior da tabela.</span><span class="sxs-lookup"><span data-stu-id="cc1b0-327">To select all users, click the &#x2713; (check mark) at the top of the table.</span></span>

4. <span data-ttu-id="cc1b0-328">Selecione **Editar configurações,** faça as alterações que você deseja e selecione **Aplicar**.</span><span class="sxs-lookup"><span data-stu-id="cc1b0-328">Select **Edit settings**, make the changes that you want, and then select **Apply**.</span></span>

<span data-ttu-id="cc1b0-329">Para exibir o status da atribuição de política, na  faixa que  aparece na parte superior da página Usuários depois de selecionar Aplicar para enviar sua atribuição de política, selecione Log **de atividades.**</span><span class="sxs-lookup"><span data-stu-id="cc1b0-329">To view the status of your policy assignment, in the banner that appears at the top of the **Users** page after you select **Apply** to submit your policy assignment, select **Activity log**.</span></span> <span data-ttu-id="cc1b0-330">Ou, na navegação à esquerda do centro de administração Microsoft Teams, vá para **Painel** e, em log de **atividades,** selecione **Exibir detalhes**.</span><span class="sxs-lookup"><span data-stu-id="cc1b0-330">Or, in the left navigation of the Microsoft Teams admin center, go to **Dashboard**, and then under **Activity log**, select **View details**.</span></span> <span data-ttu-id="cc1b0-331">O log de atividades mostra atribuições de política para lotes de mais de 20 usuários por meio do Microsoft Teams de administração dos últimos 30 dias.</span><span class="sxs-lookup"><span data-stu-id="cc1b0-331">The Activity log shows policy assignments to batches of more than 20 users through the Microsoft Teams admin center from the last 30 days.</span></span> <span data-ttu-id="cc1b0-332">Para saber mais, confira [Exibir suas atribuições de política no log de atividades](activity-log.md).</span><span class="sxs-lookup"><span data-stu-id="cc1b0-332">To learn more, see [View your policy assignments in the Activity log](activity-log.md).</span></span>

### <a name="use-powershell-method"></a><span data-ttu-id="cc1b0-333">Usar o método PowerShell</span><span class="sxs-lookup"><span data-stu-id="cc1b0-333">Use PowerShell method</span></span>

> [!NOTE]
> <span data-ttu-id="cc1b0-334">Atualmente, a atribuição de política em lote usando o PowerShell não está disponível para todos os tipos Teams de política.</span><span class="sxs-lookup"><span data-stu-id="cc1b0-334">Currently, batch policy assignment using PowerShell isn't available for all Teams policy types.</span></span> <span data-ttu-id="cc1b0-335">Consulte [New-CsBatchPolicyAssignmentOperation para](/powershell/module/teams/new-csbatchpolicyassignmentoperation) ver a lista de tipos de política com suporte.</span><span class="sxs-lookup"><span data-stu-id="cc1b0-335">See [New-CsBatchPolicyAssignmentOperation](/powershell/module/teams/new-csbatchpolicyassignmentoperation) for the list of supported policy types.</span></span>

<span data-ttu-id="cc1b0-336">Com a atribuição de política em lote, você pode atribuir uma política a grandes conjuntos de usuários por vez sem precisar usar um script.</span><span class="sxs-lookup"><span data-stu-id="cc1b0-336">With batch policy assignment, you can assign a policy to large sets of users at a time without having to use a script.</span></span> <span data-ttu-id="cc1b0-337">Você usa o cmdlet [New-CsBatchPolicyAssignmentOperation](/powershell/module/teams/new-csbatchpolicyassignmentoperation) para enviar um lote de usuários e a política que deseja atribuir.</span><span class="sxs-lookup"><span data-stu-id="cc1b0-337">You use the [New-CsBatchPolicyAssignmentOperation](/powershell/module/teams/new-csbatchpolicyassignmentoperation) cmdlet to submit a batch of users and the policy that you want to assign.</span></span> <span data-ttu-id="cc1b0-338">As atribuições são processadas como uma operação de plano de fundo e uma ID de operação é gerada para cada lote.</span><span class="sxs-lookup"><span data-stu-id="cc1b0-338">The assignments are processed as a background operation and an operation ID is generated for each batch.</span></span> <span data-ttu-id="cc1b0-339">Em seguida, você pode usar o cmdlet [Get-CsBatchPolicyAssignmentOperation](/powershell/module/teams/get-csbatchpolicyassignmentoperation) para rastrear o progresso e o status das atribuições em um lote.</span><span class="sxs-lookup"><span data-stu-id="cc1b0-339">You can then use the [Get-CsBatchPolicyAssignmentOperation](/powershell/module/teams/get-csbatchpolicyassignmentoperation) cmdlet to track the progress and status of the assignments in a batch.</span></span>

<span data-ttu-id="cc1b0-340">Especifique os usuários por sua ID de objeto ou endereço SIP (Session Initiation Protocol).</span><span class="sxs-lookup"><span data-stu-id="cc1b0-340">Specify users by their object ID or Session Initiation Protocol (SIP) address.</span></span> <span data-ttu-id="cc1b0-341">O endereço SIP de um usuário geralmente tem o mesmo valor que o UPN (Nome principal do usuário) ou o endereço de email, mas isso não é necessário.</span><span class="sxs-lookup"><span data-stu-id="cc1b0-341">A user's SIP address often has the same value as the User Principal Name (UPN) or email address, but this is not required.</span></span> <span data-ttu-id="cc1b0-342">Se um usuário for especificado usando seu UPN ou email, mas tiver um valor diferente do endereço SIP, a atribuição de política falhará para o usuário.</span><span class="sxs-lookup"><span data-stu-id="cc1b0-342">If a user is specified using their UPN or email, but it has a different value than their SIP address, then policy assignment will fail for the user.</span></span> <span data-ttu-id="cc1b0-343">Se um lote incluir usuários duplicados, as duplicatas serão removidas do lote antes do processamento e o status só será fornecido para os usuários exclusivos restantes no lote.</span><span class="sxs-lookup"><span data-stu-id="cc1b0-343">If a batch includes duplicate users, the duplicates will be removed from the batch before processing and status will only be provided for the unique users remaining in the batch.</span></span>

<span data-ttu-id="cc1b0-344">Um lote pode conter até 5.000 usuários.</span><span class="sxs-lookup"><span data-stu-id="cc1b0-344">A batch can contain up to 5,000 users.</span></span> <span data-ttu-id="cc1b0-345">Para obter melhores resultados, não envie mais de alguns lotes por vez.</span><span class="sxs-lookup"><span data-stu-id="cc1b0-345">For best results, don't submit more than a few batches at a time.</span></span> <span data-ttu-id="cc1b0-346">Permitir que lotes concluam o processamento antes de enviar mais lotes.</span><span class="sxs-lookup"><span data-stu-id="cc1b0-346">Allow batches to complete processing before submitting more batches.</span></span>

#### <a name="install-and-connect-to-the-teams-powershell-module"></a><span data-ttu-id="cc1b0-347">Instalar e conectar ao módulo Teams PowerShell</span><span class="sxs-lookup"><span data-stu-id="cc1b0-347">Install and connect to the Teams PowerShell module</span></span>

<span data-ttu-id="cc1b0-348">Execute o seguinte para instalar o [módulo Microsoft Teams PowerShell](https://www.powershellgallery.com/packages/MicrosoftTeams).</span><span class="sxs-lookup"><span data-stu-id="cc1b0-348">Run the following to install the [Microsoft Teams PowerShell module](https://www.powershellgallery.com/packages/MicrosoftTeams).</span></span> <span data-ttu-id="cc1b0-349">Instale a versão 1.0.5 ou posterior.</span><span class="sxs-lookup"><span data-stu-id="cc1b0-349">Make sure you install version 1.0.5 or later.</span></span>

```powershell
Install-Module -Name MicrosoftTeams
```

<span data-ttu-id="cc1b0-350">Execute o seguinte para se conectar ao Teams e iniciar uma sessão.</span><span class="sxs-lookup"><span data-stu-id="cc1b0-350">Run the following to connect to Teams and start a session.</span></span>

```powershell
Connect-MicrosoftTeams
```

<span data-ttu-id="cc1b0-351">Quando for solicitado, entre usando suas credenciais de administrador.</span><span class="sxs-lookup"><span data-stu-id="cc1b0-351">When you're prompted, sign in using your admin credentials.</span></span>

#### <a name="install-and-connect-to-the-azure-ad-powershell-for-graph-module-optional"></a><span data-ttu-id="cc1b0-352">Instalar e conectar ao PowerShell do Azure AD para Graph módulo (opcional)</span><span class="sxs-lookup"><span data-stu-id="cc1b0-352">Install and connect to the Azure AD PowerShell for Graph module (optional)</span></span>

<span data-ttu-id="cc1b0-353">Talvez você também queira baixar e instalar o módulo do [Azure AD PowerShell](/powershell/azure/active-directory/install-adv2) para Graph (se ainda não o fez) e se conectar ao Azure AD para poder recuperar uma lista de usuários em sua organização.</span><span class="sxs-lookup"><span data-stu-id="cc1b0-353">You might also want to [download and install the Azure AD PowerShell for Graph module](/powershell/azure/active-directory/install-adv2) (if you haven't already) and connect to Azure AD so that you can retrieve a list of users in your organization.</span></span>

<span data-ttu-id="cc1b0-354">Execute o seguinte para se conectar ao Azure AD.</span><span class="sxs-lookup"><span data-stu-id="cc1b0-354">Run the following to connect to Azure AD.</span></span>

```powershell
Connect-AzureAD
```

<span data-ttu-id="cc1b0-355">Quando for solicitado, entre usando as mesmas credenciais de administrador usadas para se conectar Teams.</span><span class="sxs-lookup"><span data-stu-id="cc1b0-355">When you're prompted, sign in using the same admin credentials that you used to connect to Teams.</span></span>

#### <a name="assign-a-setup-policy-to-a-batch-of-users"></a><span data-ttu-id="cc1b0-356">Atribuir uma política de instalação a um lote de usuários</span><span class="sxs-lookup"><span data-stu-id="cc1b0-356">Assign a setup policy to a batch of users</span></span>

<span data-ttu-id="cc1b0-357">Neste exemplo, usamos o cmdlet [New-CsBatchPolicyAssignmentOperation](/powershell/module/teams/new-csbatchpolicyassignmentoperation) para atribuir uma política de configuração de aplicativo chamada Política de Instalação de Aplicativos de RH a um lote de usuários listados no arquivo Users_ids.txt.</span><span class="sxs-lookup"><span data-stu-id="cc1b0-357">In this example, we use the [New-CsBatchPolicyAssignmentOperation](/powershell/module/teams/new-csbatchpolicyassignmentoperation) cmdlet to assign an app setup policy named HR App Setup Policy to a batch of users listed in the Users_ids.txt file.</span></span>

```powershell
$users_ids = Get-Content .\users_ids.txt
New-CsBatchPolicyAssignmentOperation -PolicyType TeamsAppSetupPolicy -PolicyName "HR App Setup Policy" -Identity $users_ids -OperationName "Example 1 batch"
```

<span data-ttu-id="cc1b0-358">Neste exemplo, nos conectamos ao Azure AD para recuperar uma coleção de usuários e atribuir uma política de mensagens chamada New Hire Messaging Policy a um lote de usuários especificado usando seu endereço SIP.</span><span class="sxs-lookup"><span data-stu-id="cc1b0-358">In this example, we connect to Azure AD to retrieve a collection of users and then assign a messaging policy named New Hire Messaging Policy to a batch of users specified by using their SIP address.</span></span>

```powershell
Connect-AzureAD
$users = Get-AzureADUser
New-CsBatchPolicyAssignmentOperation -PolicyType TeamsMessagingPolicy -PolicyName "New Hire Messaging Policy" -Identity $users.SipProxyAddress -OperationName "Example 2 batch"
```

#### <a name="get-the-status-of-a-batch-assignment"></a><span data-ttu-id="cc1b0-359">Obter o status de uma atribuição em lotes</span><span class="sxs-lookup"><span data-stu-id="cc1b0-359">Get the status of a batch assignment</span></span>

<span data-ttu-id="cc1b0-360">Execute o seguinte para obter o status de uma atribuição em lotes, onde OperationId é a ID da operação retornada pelo `New-CsBatchPolicyAssignmentOperation` cmdlet para um determinado lote.</span><span class="sxs-lookup"><span data-stu-id="cc1b0-360">Run the following to get the status of a batch assignment, where OperationId is the operation ID that's returned by the `New-CsBatchPolicyAssignmentOperation` cmdlet for a given batch.</span></span>

```powershell
$Get-CsBatchPolicyAssignmentOperation -OperationId f985e013-0826-40bb-8c94-e5f367076044 | fl
```

<span data-ttu-id="cc1b0-361">Se a saída mostrar que ocorreu um erro, execute o seguinte para obter mais informações sobre erros, que estão na `UserState` propriedade.</span><span class="sxs-lookup"><span data-stu-id="cc1b0-361">If the output shows that an error occurred, run the following to get more information about errors, which are in the `UserState` property.</span></span>

```powershell
Get-CsBatchPolicyAssignmentOperation -OperationId f985e013-0826-40bb-8c94-e5f367076044 | Select -ExpandProperty UserState
```

<span data-ttu-id="cc1b0-362">Para saber mais, confira [Get-CsBatchPolicyAssignmentOperation](/powershell/module/teams/get-csbatchpolicyassignmentoperation).</span><span class="sxs-lookup"><span data-stu-id="cc1b0-362">To learn more, see [Get-CsBatchPolicyAssignmentOperation](/powershell/module/teams/get-csbatchpolicyassignmentoperation).</span></span>

## <a name="assign-a-policy-package-to-users"></a><span data-ttu-id="cc1b0-363">Atribuir um pacote de política aos usuários</span><span class="sxs-lookup"><span data-stu-id="cc1b0-363">Assign a policy package to users</span></span>

<span data-ttu-id="cc1b0-364">Um pacote de política no Teams é uma coleção de políticas e configurações de política predefinidas que você pode atribuir aos usuários que têm as mesmas funções ou funções semelhantes em sua organização.</span><span class="sxs-lookup"><span data-stu-id="cc1b0-364">A policy package in Teams is a collection of predefined policies and policy settings that you can assign to users who have the same or similar roles in your organization.</span></span> <span data-ttu-id="cc1b0-365">Cada pacote de política é projetado em torno de uma função de usuário e inclui políticas predefinidas e configurações de política que suportam atividades típicas para essa função.</span><span class="sxs-lookup"><span data-stu-id="cc1b0-365">Each policy package is designed around a user role and includes predefined policies and policy settings that support activities typical for that role.</span></span> <span data-ttu-id="cc1b0-366">Alguns exemplos de pacotes de política são o pacote Educação (Professor) e o pacote Assistência Médica (Trabalho Médico).</span><span class="sxs-lookup"><span data-stu-id="cc1b0-366">Some examples of policy packages are the Education (Teacher) package and Healthcare (Clinical worker) package.</span></span> <span data-ttu-id="cc1b0-367">Para saber mais, confira [Gerenciar pacotes de política em Teams](manage-policy-packages.md).</span><span class="sxs-lookup"><span data-stu-id="cc1b0-367">To learn more, see [Manage policy packages in Teams](manage-policy-packages.md).</span></span>

### <a name="assign-a-policy-package-to-one-user"></a><span data-ttu-id="cc1b0-368">Atribuir um pacote de política a um usuário</span><span class="sxs-lookup"><span data-stu-id="cc1b0-368">Assign a policy package to one user</span></span>

1. <span data-ttu-id="cc1b0-369">Na navegação à esquerda do centro de administração Microsoft Teams, vá para **Usuários** e selecione o usuário.</span><span class="sxs-lookup"><span data-stu-id="cc1b0-369">In the left navigation of the Microsoft Teams admin center, go to **Users**, and then select the user.</span></span>

2. <span data-ttu-id="cc1b0-370">Na página do usuário, selecione **Políticas** e, ao lado de **Pacote de Política,** selecione **Editar**.</span><span class="sxs-lookup"><span data-stu-id="cc1b0-370">On the user's page, select **Policies**, and then next to **Policy package**, select **Edit**.</span></span>

3. <span data-ttu-id="cc1b0-371">No painel **Atribuir pacote de** política, selecione o pacote que você deseja atribuir e selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="cc1b0-371">In the **Assign policy package** pane, select the package you want to assign, and then select **Save**.</span></span>

### <a name="assign-a-policy-package-to-multiple-users"></a><span data-ttu-id="cc1b0-372">Atribuir um pacote de política a vários usuários</span><span class="sxs-lookup"><span data-stu-id="cc1b0-372">Assign a policy package to multiple users</span></span>

1. <span data-ttu-id="cc1b0-373">Na navegação à esquerda do centro de administração Microsoft Teams, vá para Pacotes de Política **e** selecione o pacote de política que você deseja atribuir clicando à esquerda do nome do pacote.</span><span class="sxs-lookup"><span data-stu-id="cc1b0-373">In the left navigation of the Microsoft Teams admin center, go to **Policy packages**, and then select the policy package you want to assign by clicking to the left of the package name.</span></span>

2. <span data-ttu-id="cc1b0-374">Escolha **Gerenciar usuários**.</span><span class="sxs-lookup"><span data-stu-id="cc1b0-374">Select **Manage users**.</span></span>

3. <span data-ttu-id="cc1b0-375">No painel **Gerenciar usuários**, procure o usuário pelo nome de exibição ou pelo nome de usuário, escolha o nome e marque **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="cc1b0-375">In the **Manage users** pane, search for the user by display name or by user name, select the name, and then select **Add**.</span></span> <span data-ttu-id="cc1b0-376">Repita esta etapa para cada usuário que você deseja adicionar.</span><span class="sxs-lookup"><span data-stu-id="cc1b0-376">Repeat this step for each user that you want to add.</span></span>

4. <span data-ttu-id="cc1b0-377">Quando terminar de adicionar usuários, selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="cc1b0-377">When you're finished adding users, select **Save**.</span></span>

## <a name="assign-a-policy-package-to-a-group"></a><span data-ttu-id="cc1b0-378">Atribua o pacote de política a um grupo.</span><span class="sxs-lookup"><span data-stu-id="cc1b0-378">Assign a policy package to a group</span></span>

<span data-ttu-id="cc1b0-379">As atribuições de pacote de política aos grupos permitem atribuir várias políticas a um grupo de usuários, como uma lista de distribuição ou grupo de segurança.</span><span class="sxs-lookup"><span data-stu-id="cc1b0-379">Policy package assignment to groups let you assign multiple policies to a group of users, such as a security group or distribution list.</span></span> <span data-ttu-id="cc1b0-380">As atribuições de política serão propagadas para os membros do grupo, de acordo com as regras de precedência.</span><span class="sxs-lookup"><span data-stu-id="cc1b0-380">The policy assignment is propagated to members of the group according to precedence rules.</span></span> <span data-ttu-id="cc1b0-381">À medida que os membros forem adicionados ou removidos de um grupo, as atribuições de política herdadas serão atualizadas.</span><span class="sxs-lookup"><span data-stu-id="cc1b0-381">As members are added to or removed from a group, their inherited policy assignments are updated accordingly.</span></span>

<span data-ttu-id="cc1b0-382">A atribuição de pacote de política a grupos é recomendada para grupos de até 50.000 usuários, mas também funcionará com grupos maiores.</span><span class="sxs-lookup"><span data-stu-id="cc1b0-382">Policy package assignment to groups is recommended for groups of up to 50,000 users, but it will also work with larger groups.</span></span>

<span data-ttu-id="cc1b0-383">Quando você atribui o pacote de política, ele é imediatamente atribuído ao grupo.</span><span class="sxs-lookup"><span data-stu-id="cc1b0-383">When you assign the policy package, it's immediately assigned to the group.</span></span> <span data-ttu-id="cc1b0-384">No entanto, a propagação da atribuição de política aos membros do grupo é executada como uma operação em segundo plano e pode levar algum tempo, dependendo do tamanho do grupo.</span><span class="sxs-lookup"><span data-stu-id="cc1b0-384">However, the propagation of the policy assignment to members of the group is performed as a background operation and might take some time, depending on the size of the group.</span></span> <span data-ttu-id="cc1b0-385">O mesmo acontece quando uma política não é atribuída a um grupo ou quando os membros são adicionados ou removidos de um grupo.</span><span class="sxs-lookup"><span data-stu-id="cc1b0-385">The same is true when a policy is unassigned from a group, or when members are added to or removed from a group.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="cc1b0-386">Antes de começar, é importante entender as regras [de precedência](#precedence-rules) e a classificação [de atribuição de grupo.](#group-assignment-ranking)</span><span class="sxs-lookup"><span data-stu-id="cc1b0-386">Before you get started, it's important to understand [precedence rules](#precedence-rules) and [group assignment ranking](#group-assignment-ranking).</span></span> <span data-ttu-id="cc1b0-387">Leia e entenda os conceitos em [O que você precisa](#what-you-need-to-know-about-policy-assignment-to-groups) saber sobre a atribuição de política a grupos anteriormente neste artigo.</span><span class="sxs-lookup"><span data-stu-id="cc1b0-387">Make sure you read and understand the concepts in [What you need to know about policy assignment to groups](#what-you-need-to-know-about-policy-assignment-to-groups) earlier in this article.</span></span>

### <a name="assign-a-policy-package-to-a-group-of-users-in-the-admin-center"></a><span data-ttu-id="cc1b0-388">Atribuir um pacote de política a um grupo de usuários no centro de administração</span><span class="sxs-lookup"><span data-stu-id="cc1b0-388">Assign a policy package to a group of users in the admin center</span></span>

1. <span data-ttu-id="cc1b0-389">Entre no Centro de administração do Teams.</span><span class="sxs-lookup"><span data-stu-id="cc1b0-389">Sign in to the Teams admin center.</span></span>

2. <span data-ttu-id="cc1b0-390">Na navegação à esquerda, vá para a página pacote de política.</span><span class="sxs-lookup"><span data-stu-id="cc1b0-390">In the left navigation, go to the policy package page.</span></span>

3. <span data-ttu-id="cc1b0-391">Selecione a guia Atribuição de política de grupo.</span><span class="sxs-lookup"><span data-stu-id="cc1b0-391">Select the Group policy assignment tab.</span></span>

4. <span data-ttu-id="cc1b0-392">Selecione **Adicionar grupo** e, em seguida, no painel Atribuir um pacote de política ao grupo, faça o seguinte:</span><span class="sxs-lookup"><span data-stu-id="cc1b0-392">Select **Add group**, and then in the Assign a policy package to group pane, do the following:</span></span>

    1. <span data-ttu-id="cc1b0-393">Pesquise e adicione o grupo ao que você deseja atribuir o pacote de política.</span><span class="sxs-lookup"><span data-stu-id="cc1b0-393">Search for and add the group you want to assign the policy package to.</span></span>
    
    1. <span data-ttu-id="cc1b0-394">Selecione um pacote de política.</span><span class="sxs-lookup"><span data-stu-id="cc1b0-394">Select a policy package.</span></span>
    
    1. <span data-ttu-id="cc1b0-395">De definir a classificação para cada tipo de política.</span><span class="sxs-lookup"><span data-stu-id="cc1b0-395">Set the ranking for each policy type.</span></span>
    
    1. <span data-ttu-id="cc1b0-396">Selecione **Aplicar**.</span><span class="sxs-lookup"><span data-stu-id="cc1b0-396">Select **Apply**.</span></span>
    
    ![mostra a atribuição de política de grupo](media/group-pkg-assignment.png)

5. <span data-ttu-id="cc1b0-398">Para gerenciar a classificação de um tipo de política específico, navegue até a página de política específica.</span><span class="sxs-lookup"><span data-stu-id="cc1b0-398">To manage ranking for a specific policy type, navigate to the specific policy page.</span></span>

6. <span data-ttu-id="cc1b0-399">Para reatribuir um pacote de política a um grupo, primeiro remova a atribuição de política de grupo.</span><span class="sxs-lookup"><span data-stu-id="cc1b0-399">To reassign a policy package to a group, first remove the group policy assignment.</span></span> <span data-ttu-id="cc1b0-400">Em seguida, siga as etapas acima para atribuir o pacote de política a um grupo.</span><span class="sxs-lookup"><span data-stu-id="cc1b0-400">Then, follow the steps above to assign the policy package to a group.</span></span>

### <a name="work-with-powershell"></a><span data-ttu-id="cc1b0-401">Trabalhar com o PowerShell</span><span class="sxs-lookup"><span data-stu-id="cc1b0-401">Work with PowerShell</span></span>

#### <a name="get-the-teams-powershell-module"></a><span data-ttu-id="cc1b0-402">Obter o módulo Teams PowerShell</span><span class="sxs-lookup"><span data-stu-id="cc1b0-402">Get the Teams PowerShell module</span></span>

<span data-ttu-id="cc1b0-403">Para obter orientações passo a passo, consulte [Install Teams PowerShell](teams-powershell-install.md).</span><span class="sxs-lookup"><span data-stu-id="cc1b0-403">For step-by-step guidance, see [Install Teams PowerShell](teams-powershell-install.md).</span></span>

#### <a name="assign-a-policy-package-to-a-group-of-users"></a><span data-ttu-id="cc1b0-404">Atribuir um pacote de política a um grupo de usuários</span><span class="sxs-lookup"><span data-stu-id="cc1b0-404">Assign a policy package to a group of users</span></span>

<span data-ttu-id="cc1b0-405">Use o cmdlet [Grant-CsGroupPolicyPackageAssignment](/powershell/module/teams/grant-csgrouppolicypackageassignment) para atribuir um pacote de política a um grupo.</span><span class="sxs-lookup"><span data-stu-id="cc1b0-405">Use the [Grant-CsGroupPolicyPackageAssignment](/powershell/module/teams/grant-csgrouppolicypackageassignment) cmdlet to assign a policy package to a group.</span></span> <span data-ttu-id="cc1b0-406">Você pode especificar um grupo usando a ID do objeto, endereço SIP ou endereço de email.</span><span class="sxs-lookup"><span data-stu-id="cc1b0-406">You can specify a group by using the object ID, SIP address, or email address.</span></span> <span data-ttu-id="cc1b0-407">Ao atribuir o pacote de política, especifique uma classificação de atribuição [de grupo](#group-assignment-ranking) para cada tipo de política no pacote de política.</span><span class="sxs-lookup"><span data-stu-id="cc1b0-407">When you assign the policy package, specify a [group assignment ranking](#group-assignment-ranking) for each policy type in the policy package.</span></span>

<span data-ttu-id="cc1b0-408">Neste exemplo, atribuímos o pacote de política Education_Teacher a um grupo com uma classificação de atribuição de 1 para TeamsAppSetupPolicy e TeamsMeetingBroadcastPolicy e uma classificação de 2 para TeamsMeetingPolicy.</span><span class="sxs-lookup"><span data-stu-id="cc1b0-408">In this example, we assign the Education_Teacher policy package to a group with an assignment ranking of 1 for TeamsAppSetupPolicy and TeamsMeetingBroadcastPolicy and a ranking of 2 for TeamsMeetingPolicy.</span></span>

```powershell
Grant-CsGroupPolicyPackageAssignment -GroupId "dae90bb4-120f-4a3e-a15d-30f142e79f69" -PackageName "Education_Teacher" -PolicyRankings "TeamsAppSetupPolicy, 1", "TeamsMeetingBroadcastPolicy, 1", "TeamsMeetingPolicy, 2"
```

## <a name="assign-a-policy-package-to-a-batch-of-users"></a><span data-ttu-id="cc1b0-409">Atribuir um pacote de política a um lote de usuários</span><span class="sxs-lookup"><span data-stu-id="cc1b0-409">Assign a policy package to a batch of users</span></span>

<span data-ttu-id="cc1b0-410">Com a atribuição de pacote de política em lote, você pode atribuir um pacote de política a grandes conjuntos de usuários por vez sem precisar usar um script.</span><span class="sxs-lookup"><span data-stu-id="cc1b0-410">With batch policy package assignment, you can assign a policy package to large sets of users at a time without having to use a script.</span></span> <span data-ttu-id="cc1b0-411">Use o cmdlet [New-CsBatchPolicyAssignmentOperation](/powershell/module/teams/new-csbatchpolicyassignmentoperation) para enviar um lote de usuários e o pacote de política que você deseja atribuir.</span><span class="sxs-lookup"><span data-stu-id="cc1b0-411">You use the [New-CsBatchPolicyAssignmentOperation](/powershell/module/teams/new-csbatchpolicyassignmentoperation) cmdlet to submit a batch of users and the policy package that you want to assign.</span></span> <span data-ttu-id="cc1b0-412">As atribuições são processadas como uma operação de plano de fundo e uma ID de operação é gerada para cada lote.</span><span class="sxs-lookup"><span data-stu-id="cc1b0-412">The assignments are processed as a background operation and an operation ID is generated for each batch.</span></span> <span data-ttu-id="cc1b0-413">Em seguida, você pode usar o cmdlet [Get-CsBatchPolicyAssignmentOperation](/powershell/module/teams/get-csbatchpolicyassignmentoperation) para rastrear o progresso e o status das atribuições em um lote.</span><span class="sxs-lookup"><span data-stu-id="cc1b0-413">You can then use the [Get-CsBatchPolicyAssignmentOperation](/powershell/module/teams/get-csbatchpolicyassignmentoperation) cmdlet to track the progress and status of the assignments in a batch.</span></span>

<span data-ttu-id="cc1b0-414">Especifique os usuários por sua ID de objeto ou endereço SIP (Session Initiation Protocol).</span><span class="sxs-lookup"><span data-stu-id="cc1b0-414">Specify users by their object ID or Session Initiation Protocol (SIP) address.</span></span> <span data-ttu-id="cc1b0-415">O endereço SIP de um usuário geralmente tem o mesmo valor que o UPN (Nome principal do usuário) ou o endereço de email, mas isso não é necessário.</span><span class="sxs-lookup"><span data-stu-id="cc1b0-415">A user's SIP address often has the same value as the User Principal Name (UPN) or email address, but this isn't required.</span></span> <span data-ttu-id="cc1b0-416">Se um usuário for especificado usando seu UPN ou email, mas tiver um valor diferente do endereço SIP, a atribuição de política falhará para o usuário.</span><span class="sxs-lookup"><span data-stu-id="cc1b0-416">If a user is specified using their UPN or email, but it has a different value than their SIP address, then policy assignment will fail for the user.</span></span> <span data-ttu-id="cc1b0-417">Se um lote incluir usuários duplicados, as duplicatas serão removidas do lote antes do processamento e o status só será fornecido para os usuários exclusivos restantes no lote.</span><span class="sxs-lookup"><span data-stu-id="cc1b0-417">If a batch includes duplicate users, the duplicates will be removed from the batch before processing and status will only be provided for the unique users remaining in the batch.</span></span>

<span data-ttu-id="cc1b0-418">Um lote contém até 5.000 usuários.</span><span class="sxs-lookup"><span data-stu-id="cc1b0-418">A batch contains up to 5,000 users.</span></span> <span data-ttu-id="cc1b0-419">Para obter melhores resultados, não envie mais de alguns lotes por vez.</span><span class="sxs-lookup"><span data-stu-id="cc1b0-419">For best results, don't submit more than a few batches at a time.</span></span> <span data-ttu-id="cc1b0-420">Permitir que lotes concluam o processamento antes de enviar mais lotes.</span><span class="sxs-lookup"><span data-stu-id="cc1b0-420">Allow batches to complete processing before submitting more batches.</span></span>

### <a name="use-the-teams-powershell-module"></a><span data-ttu-id="cc1b0-421">Usar o módulo Teams PowerShell</span><span class="sxs-lookup"><span data-stu-id="cc1b0-421">Use the Teams PowerShell module</span></span>

<span data-ttu-id="cc1b0-422">Execute o seguinte para instalar o [Microsoft Teams do PowerShell](https://www.powershellgallery.com/packages/MicrosoftTeams) (caso ainda não tenha feito isso).</span><span class="sxs-lookup"><span data-stu-id="cc1b0-422">Run the following to install the [Microsoft Teams PowerShell module](https://www.powershellgallery.com/packages/MicrosoftTeams) (if you haven't already).</span></span> <span data-ttu-id="cc1b0-423">Instale a versão 1.0.5 ou posterior.</span><span class="sxs-lookup"><span data-stu-id="cc1b0-423">Make sure you install version 1.0.5 or later.</span></span>

```powershell
Install-Module -Name MicrosoftTeams
```

<span data-ttu-id="cc1b0-424">Execute o seguinte para se conectar ao Teams e iniciar uma sessão.</span><span class="sxs-lookup"><span data-stu-id="cc1b0-424">Run the following to connect to Teams and start a session.</span></span>

```powershell
Connect-MicrosoftTeams
```

<span data-ttu-id="cc1b0-425">Quando for solicitado, entre usando suas credenciais de administrador.</span><span class="sxs-lookup"><span data-stu-id="cc1b0-425">When you're prompted, sign in using your admin credentials.</span></span>

### <a name="assign-policy-packages-to-a-batch-of-users"></a><span data-ttu-id="cc1b0-426">Atribuir pacotes de política a um lote de usuários</span><span class="sxs-lookup"><span data-stu-id="cc1b0-426">Assign policy packages to a batch of users</span></span>

<span data-ttu-id="cc1b0-427">Neste exemplo, usamos o cmdlet [New-CsBatchPolicyAssignmentOperation](/powershell/module/teams/new-csbatchpolicyassignmentoperation) para atribuir o pacote de política Education_PrimaryStudent a um lote de usuários.</span><span class="sxs-lookup"><span data-stu-id="cc1b0-427">In this example, we use the [New-CsBatchPolicyAssignmentOperation](/powershell/module/teams/new-csbatchpolicyassignmentoperation) cmdlet to assign the Education_PrimaryStudent policy package to a batch of users.</span></span>

```powershell
New-CsBatchPolicyPackageAssignmentOperation -Identity 1bc0b35f-095a-4a37-a24c-c4b6049816ab,user1@econtoso.com,user2@contoso.com -PackageName Education_PrimaryStudent
```

### <a name="see-the-status-of-a-batch-assignment"></a><span data-ttu-id="cc1b0-428">Consulte o status de uma atribuição em lotes</span><span class="sxs-lookup"><span data-stu-id="cc1b0-428">See the status of a batch assignment</span></span>

<span data-ttu-id="cc1b0-429">Execute o seguinte para obter o status de uma atribuição em lotes, onde OperationId é a ID da operação retornada pelo `New-CsBatchPolicyAssignmentOperation` cmdlet para um determinado lote.</span><span class="sxs-lookup"><span data-stu-id="cc1b0-429">Run the following to get the status of a batch assignment, where OperationId is the operation ID that's returned by the `New-CsBatchPolicyAssignmentOperation` cmdlet for a given batch.</span></span>

```powershell
Get-CsBatchPolicyAssignmentOperation -OperationId f985e013-0826-40bb-8c94-e5f367076044 | fl
```

<span data-ttu-id="cc1b0-430">Se a saída mostrar que ocorreu um erro, execute o seguinte para obter mais informações sobre erros, que estão na `UserState` propriedade.</span><span class="sxs-lookup"><span data-stu-id="cc1b0-430">If the output shows that an error occurred, run the following to get more information about errors, which are in the `UserState` property.</span></span>

```powershell
Get-CsBatchPolicyAssignmentOperation -OperationId f985e013-0826-40bb-8c94-e5f367076044 | Select -ExpandProperty UserState
```

<span data-ttu-id="cc1b0-431">Para saber mais, confira [Get-CsBatchPolicyAssignmentOperation](/powershell/module/teams/get-csbatchpolicyassignmentoperation).</span><span class="sxs-lookup"><span data-stu-id="cc1b0-431">To learn more, see [Get-CsBatchPolicyAssignmentOperation](/powershell/module/teams/get-csbatchpolicyassignmentoperation).</span></span>

## <a name="related-topics"></a><span data-ttu-id="cc1b0-432">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="cc1b0-432">Related topics</span></span>

[<span data-ttu-id="cc1b0-433">Visão Geral do PowerShell do Teams</span><span class="sxs-lookup"><span data-stu-id="cc1b0-433">Teams PowerShell Overview</span></span>](teams-powershell-overview.md)
