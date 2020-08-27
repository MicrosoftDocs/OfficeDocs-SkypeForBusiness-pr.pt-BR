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
description: Saiba como usar e gerenciar políticas de identificação de chamadas no Microsoft Teams para alterar ou bloquear a identificação de chamadas de usuários do teams em sua organização.
ms.openlocfilehash: c3eabc5a9e906fd514ce92864e08cad5015f6670
ms.sourcegitcommit: 2874aec7768bb46ed4506c1a2d431841f47190bf
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/26/2020
ms.locfileid: "47255524"
---
# <a name="manage-caller-id-policies-in-microsoft-teams"></a><span data-ttu-id="7999e-103">Gerenciar políticas de identificação de chamadas no Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="7999e-103">Manage caller ID policies in Microsoft Teams</span></span>

>[!INCLUDE [new-feature-teams-admin-center](includes/new-feature-teams-admin-center.md)]

<span data-ttu-id="7999e-104">Como administrador, você pode usar as políticas de identificação de chamada no Microsoft Teams para alterar ou bloquear a identificação de chamadas (também conhecida como identificação da linha de chamada).</span><span class="sxs-lookup"><span data-stu-id="7999e-104">As an admin, you can use caller ID policies in Microsoft Teams to change or block the caller ID (also known as calling line ID).</span></span> <span data-ttu-id="7999e-105">Por padrão, o número de telefone dos usuários do teams pode ser visto ao fazer uma chamada para um telefone PSTN, e o número de telefone PSTN pode ser visto quando ele chama um usuário do teams.</span><span class="sxs-lookup"><span data-stu-id="7999e-105">By default, the phone number of Teams users can be seen when they make a call to a PSTN phone and the phone number of PSTN callers can be seen when they call a Teams user.</span></span> <span data-ttu-id="7999e-106">Você pode usar as políticas de identificação de chamadas para exibir um número de telefone alternativo para usuários do teams em sua organização ou impedir que um número recebido seja exibido.</span><span class="sxs-lookup"><span data-stu-id="7999e-106">You can use caller ID policies to display an alternate phone number for Teams users in your organization or block an incoming number from being displayed.</span></span>

<span data-ttu-id="7999e-107">Por exemplo, quando os usuários fazem uma chamada, você pode alterar a identificação de chamadas para exibir o número de telefone principal da sua organização, em vez de números de telefone dos usuários.</span><span class="sxs-lookup"><span data-stu-id="7999e-107">For example, when users make a call, you can change the caller ID to display your organization's main phone number instead of users' phone numbers.</span></span>

<span data-ttu-id="7999e-108">Você gerencia as políticas de identificação de chamadas **Voice**indo para  >  **políticas de identificação de chamadas** de voz no centro de administração do Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="7999e-108">You manage caller ID policies by going to **Voice** > **Caller ID policies** in the Microsoft Teams admin center.</span></span> <span data-ttu-id="7999e-109">Você pode usar a política global (padrão para toda a organização) ou criar e atribuir políticas personalizadas.</span><span class="sxs-lookup"><span data-stu-id="7999e-109">You can use the global (Org-wide default) policy or create and assign custom policies.</span></span> <span data-ttu-id="7999e-110">Os usuários da sua organização terão automaticamente a política global, a menos que você crie e atribua uma política personalizada.</span><span class="sxs-lookup"><span data-stu-id="7999e-110">Users in your organization will automatically get the global policy unless you create and assign a custom policy.</span></span>

## <a name="create-a-custom-caller-id-policy"></a><span data-ttu-id="7999e-111">Criar uma política de identificação de chamadas personalizada</span><span class="sxs-lookup"><span data-stu-id="7999e-111">Create a custom caller ID policy</span></span>

1. <span data-ttu-id="7999e-112">Na navegação à esquerda do centro de administração do Microsoft Teams, **Voice**vá para  >  **políticas de identificação de chamadas**de voz.</span><span class="sxs-lookup"><span data-stu-id="7999e-112">In the left navigation of the Microsoft Teams admin center, go to **Voice** > **Caller ID policies**.</span></span>
2. <span data-ttu-id="7999e-113">Clique em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="7999e-113">Click **Add**.</span></span> <br>
<span data-ttu-id="7999e-114">![Captura de tela da página nova política de identificação de chamadas no centro de administração](media/caller-id-policies-add-policy.png)</span><span class="sxs-lookup"><span data-stu-id="7999e-114">![Screenshot of new caller ID policy page in the admin center](media/caller-id-policies-add-policy.png)</span></span>
3. <span data-ttu-id="7999e-115">Insira um nome e uma descrição para a política.</span><span class="sxs-lookup"><span data-stu-id="7999e-115">Enter a name and description for the policy.</span></span>
4. <span data-ttu-id="7999e-116">Aqui, escolha as configurações desejadas:</span><span class="sxs-lookup"><span data-stu-id="7999e-116">From here, choose the settings that you want:</span></span>

    - <span data-ttu-id="7999e-117">**Bloquear a identificação**de chamadas de entrada: Ative essa configuração para impedir que a identificação de chamadas de chamadas de entrada seja exibida.</span><span class="sxs-lookup"><span data-stu-id="7999e-117">**Block incoming caller ID**: Turn on this setting to block the caller ID of incoming calls from being displayed.</span></span>
    - <span data-ttu-id="7999e-118">**Substituir a política de identificação de chamadas**: Ative essa configuração para permitir que os usuários substituam as configurações na política para exibir seu número para chamar ou não.</span><span class="sxs-lookup"><span data-stu-id="7999e-118">**Override the caller ID policy**: Turn on this setting to let users override the settings in the policy regarding displaying their number to callees or not.</span></span> <span data-ttu-id="7999e-119">Isso significa que os usuários podem escolher se desejam exibir a identificação de chamadas.</span><span class="sxs-lookup"><span data-stu-id="7999e-119">This means that users can choose whether to display their caller ID.</span></span> <span data-ttu-id="7999e-120">Para obter mais informações, consulte [controle do usuário final da identificação de chamadas de saída](https://docs.microsoft.com/microsoftteams/how-can-caller-id-be-used-in-your-organization#end-user-control-of-outbound-caller-id).</span><span class="sxs-lookup"><span data-stu-id="7999e-120">For more information, see [End user control of outbound caller ID](https://docs.microsoft.com/microsoftteams/how-can-caller-id-be-used-in-your-organization#end-user-control-of-outbound-caller-id).</span></span>
    - <span data-ttu-id="7999e-121">**Substituir a identificação de chamadas**por: definir a identificação de chamadas a ser exibida para os usuários selecionando uma das seguintes opções:</span><span class="sxs-lookup"><span data-stu-id="7999e-121">**Replace the caller ID with**: Set the caller ID to be displayed for users by selecting one of the following:</span></span>

        - <span data-ttu-id="7999e-122">**Número do usuário**: exibe o número do usuário.</span><span class="sxs-lookup"><span data-stu-id="7999e-122">**User's number**: Displays the user's number.</span></span> 
        - <span data-ttu-id="7999e-123">**Número do serviço**: permite que você defina um número de telefone de serviço para ser exibido como a identificação de chamadas.</span><span class="sxs-lookup"><span data-stu-id="7999e-123">**Service number**: Lets you set a service phone number to display as the caller ID.</span></span>
        - <span data-ttu-id="7999e-124">**Anônimo**: EXIBE a identificação de chamadas como anônima.</span><span class="sxs-lookup"><span data-stu-id="7999e-124">**Anonymous**: Displays the caller ID as Anonymous.</span></span>

    - <span data-ttu-id="7999e-125">**Substituir a identificação de chamadas por este número de serviço**: escolha um número de serviço para substituir a identificação de chamadas dos usuários.</span><span class="sxs-lookup"><span data-stu-id="7999e-125">**Replace the caller ID with this service number**: Choose a service number to replace the caller ID of users.</span></span> <span data-ttu-id="7999e-126">Essa opção estará disponível se você tiver selecionado **número de serviço** em **substituir a identificação de chamadas por**.</span><span class="sxs-lookup"><span data-stu-id="7999e-126">This option is available if you selected **Service number** in **Replace the caller ID with**.</span></span>

5. <span data-ttu-id="7999e-127">Clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="7999e-127">Click **Save**.</span></span>

## <a name="edit-a-caller-id-policy"></a><span data-ttu-id="7999e-128">Editar uma política de identificação de chamadas</span><span class="sxs-lookup"><span data-stu-id="7999e-128">Edit a caller ID policy</span></span>

<span data-ttu-id="7999e-129">Você pode editar a política global ou qualquer política personalizada criada.</span><span class="sxs-lookup"><span data-stu-id="7999e-129">You can edit the global policy or any custom policies that you create.</span></span> 

1. <span data-ttu-id="7999e-130">Na navegação à esquerda do centro de administração do Microsoft Teams, **Voice**vá para  >  **políticas de identificação de chamadas**de voz.</span><span class="sxs-lookup"><span data-stu-id="7999e-130">In the left navigation of the Microsoft Teams admin center, go to **Voice** > **Caller ID policies**.</span></span>
2. <span data-ttu-id="7999e-131">Selecione a política clicando à esquerda do nome da política e, em seguida, clique em **Editar**.</span><span class="sxs-lookup"><span data-stu-id="7999e-131">Select the policy by clicking to the left of the policy name, and then click **Edit**.</span></span>
3. <span data-ttu-id="7999e-132">Altere as configurações desejadas e clique em **salvar**.</span><span class="sxs-lookup"><span data-stu-id="7999e-132">Change the settings that you want, and then click **Save**.</span></span>

## <a name="assign-a-custom-caller-id-policy-to-users"></a><span data-ttu-id="7999e-133">Atribuir uma política de identificação de chamadas personalizada a usuários</span><span class="sxs-lookup"><span data-stu-id="7999e-133">Assign a custom caller ID policy to users</span></span>

[!INCLUDE [assign-policy](includes/assign-policy.md)]

## <a name="related-topics"></a><span data-ttu-id="7999e-134">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="7999e-134">Related topics</span></span>

[<span data-ttu-id="7999e-135">New-CsCallingLineIdentity</span><span class="sxs-lookup"><span data-stu-id="7999e-135">New-CsCallingLineIdentity</span></span>](https://docs.microsoft.com/powershell/module/skype/new-cscallinglineidentity?view=skype-ps)

[<span data-ttu-id="7999e-136">Atribuir políticas a seus usuários no Teams</span><span class="sxs-lookup"><span data-stu-id="7999e-136">Assign policies to your users in Teams</span></span>](assign-policies.md)
