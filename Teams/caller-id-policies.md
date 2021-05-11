---
title: Gerenciar políticas de identificação de chamadas no Microsoft Teams
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.reviewer: roykuntz; jens
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
description: Saiba como usar e gerenciar políticas de ID do chamador Microsoft Teams alterar ou bloquear a ID do chamador de Teams usuários em sua organização.
ms.openlocfilehash: cd928af5213a1e6fa927662adaba0fefecb687d5
ms.sourcegitcommit: 83f14c4c79559ef28357ff076938e52b369fc0c7
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/10/2021
ms.locfileid: "52308370"
---
# <a name="manage-caller-id-policies-in-microsoft-teams"></a><span data-ttu-id="6dd41-103">Gerenciar políticas de identificação de chamadas no Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="6dd41-103">Manage caller ID policies in Microsoft Teams</span></span>

> [!NOTE]
> <span data-ttu-id="6dd41-104">Para definir a ID do chamador como um número de telefone da conta de recurso e definir o nome da parte de chamada, use os cmdlets do PowerShell New-CsCallingLineIdentity ou Set-CsCallingLineIdentity no módulo 2.3.1 do Teams PowerShell ou posterior.</span><span class="sxs-lookup"><span data-stu-id="6dd41-104">To set the caller ID to a resource account phone number and to set the calling party name, use the PowerShell cmdlets New-CsCallingLineIdentity or Set-CsCallingLineIdentity in the Teams PowerShell module 2.3.1 or later.</span></span> <span data-ttu-id="6dd41-105">(Essas opções não estão disponíveis no Microsoft Teams de administração.)</span><span class="sxs-lookup"><span data-stu-id="6dd41-105">(These options are not currently available in the Microsoft Teams admin center.)</span></span> 

<span data-ttu-id="6dd41-106">Por padrão, quando um Teams faz uma chamada para um telefone PSTN, o número de telefone do Teams usuário fica visível.</span><span class="sxs-lookup"><span data-stu-id="6dd41-106">By default, when a Teams user makes a call to a PSTN phone, the phone number of the Teams user is visible.</span></span> <span data-ttu-id="6dd41-107">Da mesma forma, quando um chamador PSTN faz uma chamada para um usuário Teams, o número de telefone do chamador PSTN fica visível.</span><span class="sxs-lookup"><span data-stu-id="6dd41-107">Likewise, when a PSTN caller makes a call to a Teams user, the PSTN caller's phone number is visible.</span></span>

<span data-ttu-id="6dd41-108">Como administrador, você pode usar políticas de ID do chamador para alterar ou bloquear a ID do chamador (também conhecida como ID de linha de chamada).</span><span class="sxs-lookup"><span data-stu-id="6dd41-108">As an administrator, you can use caller ID policies to change or block the caller ID (also known as calling line ID).</span></span> <span data-ttu-id="6dd41-109">Você pode usar políticas de ID do chamador para exibir um número de telefone alternativo para usuários Teams sua organização, bloquear o número de telefone de saída, impedir que um número de entrada seja exibido ou definir o Nome da Parte de Chamada (CNAM).</span><span class="sxs-lookup"><span data-stu-id="6dd41-109">You can use caller ID policies to display an alternate phone number for Teams users in your organization, block the outbound phone number, block an incoming number from being displayed, or set the Calling Party Name (CNAM).</span></span> <span data-ttu-id="6dd41-110">Por exemplo, quando um usuário faz uma chamada, você pode alterar a ID do chamador para exibir o número de telefone principal e o nome da empresa da sua organização, em vez do número de telefone do usuário.</span><span class="sxs-lookup"><span data-stu-id="6dd41-110">For example, when a user makes a call, you can change the caller ID to display your organization's main phone number and company name instead of the user's phone number.</span></span>

<span data-ttu-id="6dd41-111">Você gerencia políticas de ID do chamador indo para **políticas** de ID do Chamador de Voz no centro de administração  >   Microsoft Teams de voz.</span><span class="sxs-lookup"><span data-stu-id="6dd41-111">You manage caller ID policies by going to **Voice** > **Caller ID policies** in the Microsoft Teams admin center.</span></span> <span data-ttu-id="6dd41-112">Você pode usar a política global (padrão para toda a organização) ou criar e atribuir políticas personalizadas.</span><span class="sxs-lookup"><span data-stu-id="6dd41-112">You can use the global (Org-wide default) policy or create and assign custom policies.</span></span> <span data-ttu-id="6dd41-113">Os usuários em sua organização obterão automaticamente a política global, a menos que você crie e atribua uma política personalizada.</span><span class="sxs-lookup"><span data-stu-id="6dd41-113">Users in your organization will automatically get the global policy unless you create and assign a custom policy.</span></span>

## <a name="create-a-custom-caller-id-policy"></a><span data-ttu-id="6dd41-114">Criar uma política de ID do chamador personalizado</span><span class="sxs-lookup"><span data-stu-id="6dd41-114">Create a custom caller ID policy</span></span>

1. <span data-ttu-id="6dd41-115">Na navegação à esquerda do centro de administração Microsoft Teams, vá para **Políticas** de  >  **ID do Chamador de Voz.**</span><span class="sxs-lookup"><span data-stu-id="6dd41-115">In the left navigation of the Microsoft Teams admin center, go to **Voice** > **Caller ID policies**.</span></span>
2. <span data-ttu-id="6dd41-116">Clique em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="6dd41-116">Click **Add**.</span></span> <br>
<span data-ttu-id="6dd41-117">![Captura de tela da nova página de política de ID do chamador no centro de administração](media/caller-id-policies-add-policy.png)</span><span class="sxs-lookup"><span data-stu-id="6dd41-117">![Screenshot of new caller ID policy page in the admin center](media/caller-id-policies-add-policy.png)</span></span>
3. <span data-ttu-id="6dd41-118">Insira um nome e uma descrição para a política.</span><span class="sxs-lookup"><span data-stu-id="6dd41-118">Enter a name and description for the policy.</span></span>
4. <span data-ttu-id="6dd41-119">A partir daqui, escolha as configurações que você deseja:</span><span class="sxs-lookup"><span data-stu-id="6dd41-119">From here, choose the settings that you want:</span></span>

    - <span data-ttu-id="6dd41-120">**Bloquear a ID do chamador** de entrada: a opção Ativar essa configuração para impedir que a ID do chamador de chamadas de entrada seja exibida.</span><span class="sxs-lookup"><span data-stu-id="6dd41-120">**Block incoming caller ID**: Turn on this setting to block the caller ID of incoming calls from being displayed.</span></span>
    - <span data-ttu-id="6dd41-121">**Substituir a política** de ID do chamador : ativação dessa configuração para permitir que os usuários substituam as configurações na política em relação à exibição do número para os chamador ou não.</span><span class="sxs-lookup"><span data-stu-id="6dd41-121">**Override the caller ID policy**: Turn on this setting to let users override the settings in the policy regarding displaying their number to callees or not.</span></span> <span data-ttu-id="6dd41-122">Isso significa que os usuários podem escolher se exibirão a ID do chamador.</span><span class="sxs-lookup"><span data-stu-id="6dd41-122">This means that users can choose whether to display their caller ID.</span></span> <span data-ttu-id="6dd41-123">Para obter mais informações, [consulte End user control of outbound caller ID](./how-can-caller-id-be-used-in-your-organization.md#end-user-control-of-outbound-caller-id).</span><span class="sxs-lookup"><span data-stu-id="6dd41-123">For more information, see [End user control of outbound caller ID](./how-can-caller-id-be-used-in-your-organization.md#end-user-control-of-outbound-caller-id).</span></span>
    - <span data-ttu-id="6dd41-124">**Substitua a ID do chamador por**: De definir a ID do chamador a ser exibida para os usuários selecionando um dos seguintes:</span><span class="sxs-lookup"><span data-stu-id="6dd41-124">**Replace the caller ID with**: Set the caller ID to be displayed for users by selecting one of the following:</span></span>

        - <span data-ttu-id="6dd41-125">**Número do usuário**: Exibe o número do usuário.</span><span class="sxs-lookup"><span data-stu-id="6dd41-125">**User's number**: Displays the user's number.</span></span> 
        - <span data-ttu-id="6dd41-126">**Número de** serviço : Permite definir um número de telefone de serviço a ser exibido como a ID do chamador.</span><span class="sxs-lookup"><span data-stu-id="6dd41-126">**Service number**: Lets you set a service phone number to display as the caller ID.</span></span>
        - <span data-ttu-id="6dd41-127">**Anônimo**: exibe a ID do chamador como Anônima.</span><span class="sxs-lookup"><span data-stu-id="6dd41-127">**Anonymous**: Displays the caller ID as Anonymous.</span></span>

    - <span data-ttu-id="6dd41-128">**Substitua a ID do chamador por esse número de** serviço : escolha um número de serviço para substituir a ID do chamador dos usuários.</span><span class="sxs-lookup"><span data-stu-id="6dd41-128">**Replace the caller ID with this service number**: Choose a service number to replace the caller ID of users.</span></span> <span data-ttu-id="6dd41-129">Essa opção estará disponível se você selecionou **Número de serviço** em Substituir a **ID do chamador por**.</span><span class="sxs-lookup"><span data-stu-id="6dd41-129">This option is available if you selected **Service number** in **Replace the caller ID with**.</span></span>

5. <span data-ttu-id="6dd41-130">Clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="6dd41-130">Click **Save**.</span></span>

## <a name="edit-a-caller-id-policy"></a><span data-ttu-id="6dd41-131">Editar uma política de ID do chamador</span><span class="sxs-lookup"><span data-stu-id="6dd41-131">Edit a caller ID policy</span></span>

<span data-ttu-id="6dd41-132">Você pode editar a política global ou quaisquer políticas personalizadas que você criar.</span><span class="sxs-lookup"><span data-stu-id="6dd41-132">You can edit the global policy or any custom policies that you create.</span></span> 

1. <span data-ttu-id="6dd41-133">Na navegação à esquerda do centro de administração Microsoft Teams, vá para **Políticas** de  >  **ID do Chamador de Voz.**</span><span class="sxs-lookup"><span data-stu-id="6dd41-133">In the left navigation of the Microsoft Teams admin center, go to **Voice** > **Caller ID policies**.</span></span>
2. <span data-ttu-id="6dd41-134">Selecione a política clicando à esquerda do nome da política e, a seguir, clique em **Editar**.</span><span class="sxs-lookup"><span data-stu-id="6dd41-134">Select the policy by clicking to the left of the policy name, and then click **Edit**.</span></span>
3. <span data-ttu-id="6dd41-135">Altere as configurações que você deseja e clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="6dd41-135">Change the settings that you want, and then click **Save**.</span></span>

## <a name="assign-a-custom-caller-id-policy-to-users"></a><span data-ttu-id="6dd41-136">Atribuir uma política de ID de chamador personalizada aos usuários</span><span class="sxs-lookup"><span data-stu-id="6dd41-136">Assign a custom caller ID policy to users</span></span>

[!INCLUDE [assign-policy](includes/assign-policy.md)]

## <a name="related-topics"></a><span data-ttu-id="6dd41-137">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="6dd41-137">Related topics</span></span>

[<span data-ttu-id="6dd41-138">New-CsCallingLineIdentity</span><span class="sxs-lookup"><span data-stu-id="6dd41-138">New-CsCallingLineIdentity</span></span>](/powershell/module/skype/new-cscallinglineidentity?view=skype-ps)

[<span data-ttu-id="6dd41-139">Set-CsCallingLineIdentity</span><span class="sxs-lookup"><span data-stu-id="6dd41-139">Set-CsCallingLineIdentity</span></span>](/powershell/module/skype/set-cscallinglineidentity?view=skype-ps)

[<span data-ttu-id="6dd41-140">Atribua políticas a seus usuários no Teams</span><span class="sxs-lookup"><span data-stu-id="6dd41-140">Assign policies to your users in Teams</span></span>](assign-policies.md)