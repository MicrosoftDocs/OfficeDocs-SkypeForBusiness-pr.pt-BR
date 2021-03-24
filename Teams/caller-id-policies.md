---
title: Gerenciar políticas de identificação de chamadas no Microsoft Teams
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.reviewer: jastark
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-voice
f1.keywords:
- CSH
ms.custom: ms.teamsadmincenter.voice.callinglineid.overview
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: Saiba como usar e gerenciar políticas de ID do chamador no Microsoft Teams para alterar ou bloquear a ID do chamador dos usuários do Teams em sua organização.
ms.openlocfilehash: cd15245523cdc3f5fb3625a2b4cfdae4deebb7d3
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51102777"
---
# <a name="manage-caller-id-policies-in-microsoft-teams"></a><span data-ttu-id="d4257-103">Gerenciar políticas de identificação de chamadas no Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="d4257-103">Manage caller ID policies in Microsoft Teams</span></span>

>[!INCLUDE [new-feature-teams-admin-center](includes/new-feature-teams-admin-center.md)]

<span data-ttu-id="d4257-104">Como administrador, você pode usar políticas de ID do chamador no Microsoft Teams para alterar ou bloquear a ID do chamador (também conhecida como ID de linha de chamada).</span><span class="sxs-lookup"><span data-stu-id="d4257-104">As an admin, you can use caller ID policies in Microsoft Teams to change or block the caller ID (also known as calling line ID).</span></span> <span data-ttu-id="d4257-105">Por padrão, o número de telefone dos usuários do Teams pode ser visto quando eles fazem uma chamada para um telefone PSTN e o número de telefone de chamadores PSTN pode ser visto quando eles chamam um usuário do Teams.</span><span class="sxs-lookup"><span data-stu-id="d4257-105">By default, the phone number of Teams users can be seen when they make a call to a PSTN phone and the phone number of PSTN callers can be seen when they call a Teams user.</span></span> <span data-ttu-id="d4257-106">Você pode usar políticas de ID do chamador para exibir um número de telefone alternativo para usuários do Teams em sua organização ou impedir que um número de entrada seja exibido.</span><span class="sxs-lookup"><span data-stu-id="d4257-106">You can use caller ID policies to display an alternate phone number for Teams users in your organization or block an incoming number from being displayed.</span></span>

<span data-ttu-id="d4257-107">Por exemplo, quando os usuários fazem uma chamada, você pode alterar a ID do chamador para exibir o número de telefone principal da sua organização em vez dos números de telefone dos usuários.</span><span class="sxs-lookup"><span data-stu-id="d4257-107">For example, when users make a call, you can change the caller ID to display your organization's main phone number instead of users' phone numbers.</span></span>

<span data-ttu-id="d4257-108">Você gerencia políticas de ID do chamador indo para **políticas** de ID do Chamador de Voz  >   no centro de administração do Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="d4257-108">You manage caller ID policies by going to **Voice** > **Caller ID policies** in the Microsoft Teams admin center.</span></span> <span data-ttu-id="d4257-109">Você pode usar a política global (padrão para toda a organização) ou criar e atribuir políticas personalizadas.</span><span class="sxs-lookup"><span data-stu-id="d4257-109">You can use the global (Org-wide default) policy or create and assign custom policies.</span></span> <span data-ttu-id="d4257-110">Os usuários em sua organização obterão automaticamente a política global, a menos que você crie e atribua uma política personalizada.</span><span class="sxs-lookup"><span data-stu-id="d4257-110">Users in your organization will automatically get the global policy unless you create and assign a custom policy.</span></span>

## <a name="create-a-custom-caller-id-policy"></a><span data-ttu-id="d4257-111">Criar uma política de ID do chamador personalizado</span><span class="sxs-lookup"><span data-stu-id="d4257-111">Create a custom caller ID policy</span></span>

1. <span data-ttu-id="d4257-112">Na navegação à esquerda do Centro de administração do Microsoft Teams, acesse **Políticas** de  >  **ID do Chamador de Voz.**</span><span class="sxs-lookup"><span data-stu-id="d4257-112">In the left navigation of the Microsoft Teams admin center, go to **Voice** > **Caller ID policies**.</span></span>
2. <span data-ttu-id="d4257-113">Clique em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="d4257-113">Click **Add**.</span></span> <br>
<span data-ttu-id="d4257-114">![Captura de tela da nova página de política de ID do chamador no centro de administração](media/caller-id-policies-add-policy.png)</span><span class="sxs-lookup"><span data-stu-id="d4257-114">![Screenshot of new caller ID policy page in the admin center](media/caller-id-policies-add-policy.png)</span></span>
3. <span data-ttu-id="d4257-115">Insira um nome e uma descrição para a política.</span><span class="sxs-lookup"><span data-stu-id="d4257-115">Enter a name and description for the policy.</span></span>
4. <span data-ttu-id="d4257-116">A partir daqui, escolha as configurações que você deseja:</span><span class="sxs-lookup"><span data-stu-id="d4257-116">From here, choose the settings that you want:</span></span>

    - <span data-ttu-id="d4257-117">**Bloquear a ID do chamador** de entrada: a opção Ativar essa configuração para impedir que a ID do chamador de chamadas de entrada seja exibida.</span><span class="sxs-lookup"><span data-stu-id="d4257-117">**Block incoming caller ID**: Turn on this setting to block the caller ID of incoming calls from being displayed.</span></span>
    - <span data-ttu-id="d4257-118">**Substituir a política** de ID do chamador : ativação dessa configuração para permitir que os usuários substituam as configurações na política em relação à exibição do número para os chamador ou não.</span><span class="sxs-lookup"><span data-stu-id="d4257-118">**Override the caller ID policy**: Turn on this setting to let users override the settings in the policy regarding displaying their number to callees or not.</span></span> <span data-ttu-id="d4257-119">Isso significa que os usuários podem escolher se exibirão a ID do chamador.</span><span class="sxs-lookup"><span data-stu-id="d4257-119">This means that users can choose whether to display their caller ID.</span></span> <span data-ttu-id="d4257-120">Para obter mais informações, [consulte End user control of outbound caller ID](./how-can-caller-id-be-used-in-your-organization.md#end-user-control-of-outbound-caller-id).</span><span class="sxs-lookup"><span data-stu-id="d4257-120">For more information, see [End user control of outbound caller ID](./how-can-caller-id-be-used-in-your-organization.md#end-user-control-of-outbound-caller-id).</span></span>
    - <span data-ttu-id="d4257-121">**Substitua a ID do chamador por**: De definir a ID do chamador a ser exibida para os usuários selecionando um dos seguintes:</span><span class="sxs-lookup"><span data-stu-id="d4257-121">**Replace the caller ID with**: Set the caller ID to be displayed for users by selecting one of the following:</span></span>

        - <span data-ttu-id="d4257-122">**Número do usuário**: Exibe o número do usuário.</span><span class="sxs-lookup"><span data-stu-id="d4257-122">**User's number**: Displays the user's number.</span></span> 
        - <span data-ttu-id="d4257-123">**Número de** serviço : Permite definir um número de telefone de serviço a ser exibido como a ID do chamador.</span><span class="sxs-lookup"><span data-stu-id="d4257-123">**Service number**: Lets you set a service phone number to display as the caller ID.</span></span>
        - <span data-ttu-id="d4257-124">**Anônimo**: exibe a ID do chamador como Anônima.</span><span class="sxs-lookup"><span data-stu-id="d4257-124">**Anonymous**: Displays the caller ID as Anonymous.</span></span>

    - <span data-ttu-id="d4257-125">**Substitua a ID do chamador por esse número de** serviço : escolha um número de serviço para substituir a ID do chamador dos usuários.</span><span class="sxs-lookup"><span data-stu-id="d4257-125">**Replace the caller ID with this service number**: Choose a service number to replace the caller ID of users.</span></span> <span data-ttu-id="d4257-126">Essa opção estará disponível se você selecionou **Número de serviço** em Substituir a **ID do chamador por**.</span><span class="sxs-lookup"><span data-stu-id="d4257-126">This option is available if you selected **Service number** in **Replace the caller ID with**.</span></span>

5. <span data-ttu-id="d4257-127">Clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="d4257-127">Click **Save**.</span></span>

## <a name="edit-a-caller-id-policy"></a><span data-ttu-id="d4257-128">Editar uma política de ID do chamador</span><span class="sxs-lookup"><span data-stu-id="d4257-128">Edit a caller ID policy</span></span>

<span data-ttu-id="d4257-129">Você pode editar a política global ou quaisquer políticas personalizadas que você criar.</span><span class="sxs-lookup"><span data-stu-id="d4257-129">You can edit the global policy or any custom policies that you create.</span></span> 

1. <span data-ttu-id="d4257-130">Na navegação à esquerda do Centro de administração do Microsoft Teams, acesse **Políticas** de  >  **ID do Chamador de Voz.**</span><span class="sxs-lookup"><span data-stu-id="d4257-130">In the left navigation of the Microsoft Teams admin center, go to **Voice** > **Caller ID policies**.</span></span>
2. <span data-ttu-id="d4257-131">Selecione a política clicando à esquerda do nome da política e, a seguir, clique em **Editar**.</span><span class="sxs-lookup"><span data-stu-id="d4257-131">Select the policy by clicking to the left of the policy name, and then click **Edit**.</span></span>
3. <span data-ttu-id="d4257-132">Altere as configurações que você deseja e clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="d4257-132">Change the settings that you want, and then click **Save**.</span></span>

## <a name="assign-a-custom-caller-id-policy-to-users"></a><span data-ttu-id="d4257-133">Atribuir uma política de ID de chamador personalizada aos usuários</span><span class="sxs-lookup"><span data-stu-id="d4257-133">Assign a custom caller ID policy to users</span></span>

[!INCLUDE [assign-policy](includes/assign-policy.md)]

## <a name="related-topics"></a><span data-ttu-id="d4257-134">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="d4257-134">Related topics</span></span>

[<span data-ttu-id="d4257-135">New-CsCallingLineIdentity</span><span class="sxs-lookup"><span data-stu-id="d4257-135">New-CsCallingLineIdentity</span></span>](/powershell/module/skype/new-cscallinglineidentity?view=skype-ps)

[<span data-ttu-id="d4257-136">Atribua políticas a seus usuários no Teams</span><span class="sxs-lookup"><span data-stu-id="d4257-136">Assign policies to your users in Teams</span></span>](assign-policies.md)