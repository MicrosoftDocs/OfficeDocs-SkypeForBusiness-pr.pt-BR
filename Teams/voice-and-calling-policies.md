---
title: Gerenciar políticas de voz e chamadas em Teams
author: karlistites
ms.author: kastites
manager: serdars
ms.topic: conceptual
ms.service: msteams
ms.reviewer: ''
search.appverid: ''
description: Saiba mais sobre Teams de voz e chamadas.
audience: admin
localization_priority: Normal
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 9056c9b81fcda9c0e7408c63b4af00c1aabbffd0
ms.sourcegitcommit: d62e6cefceebe481eb207c59872f1aa67f0fc528
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/05/2021
ms.locfileid: "50460581"
---
# <a name="manage-voice-and-calling-policies-in-microsoft-teams"></a><span data-ttu-id="8ff2d-103">Gerenciar políticas de voz e chamadas em Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="8ff2d-103">Manage voice and calling policies in Microsoft Teams</span></span>

<span data-ttu-id="8ff2d-104">As políticas de voz e chamada são usadas para controlar voz e chamadas em Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="8ff2d-104">Voice and calling policies are used to control voice and calling in Microsoft Teams.</span></span>

## <a name="emergency-calling-policies"></a><span data-ttu-id="8ff2d-105">Políticas de chamada de emergência</span><span class="sxs-lookup"><span data-stu-id="8ff2d-105">Emergency calling policies</span></span>

<span data-ttu-id="8ff2d-106">Você usa [políticas de chamada de](manage-emergency-calling-policies.md) emergência para configurar o que acontece quando um usuário em sua organização faz uma chamada de emergência.</span><span class="sxs-lookup"><span data-stu-id="8ff2d-106">You use [emergency calling policies](manage-emergency-calling-policies.md) to configure what happens when a user in your organization makes an emergency call.</span></span> <span data-ttu-id="8ff2d-107">Essas políticas são gerenciadas no centro de administração Teams ou usando Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="8ff2d-107">These policies are managed in the Teams admin center or using Windows PowerShell.</span></span>

![Captura de tela da política de chamada de emergência.](media/emergency-calling-policy2.png)

## <a name="emergency-call-routing-policies"></a><span data-ttu-id="8ff2d-109">Políticas de roteamento de chamadas de emergência</span><span class="sxs-lookup"><span data-stu-id="8ff2d-109">Emergency call routing policies</span></span>

<span data-ttu-id="8ff2d-110">Se sua organização tiver implantado Sistema de Telefonia Roteamento **Direto,** você poderá usar políticas de roteamento de chamadas de emergência para determinar para onde as chamadas de emergência são roteadas, se os serviços de emergência aprimorados estão habilitados e quais números são usados para serviços de emergência. [](manage-emergency-call-routing-policies.md)</span><span class="sxs-lookup"><span data-stu-id="8ff2d-110">If your organization has deployed **Phone System Direct Routing**, you can use [emergency call routing policies](manage-emergency-call-routing-policies.md) to determine where emergency calls are routed, whether enhanced emergency services are enabled, and which numbers are used for emergency services.</span></span> <span data-ttu-id="8ff2d-111">Essas políticas são gerenciadas usando o PowerShell ou no Microsoft Teams de administração.</span><span class="sxs-lookup"><span data-stu-id="8ff2d-111">These policies are managed using PowerShell or in the Microsoft Teams admin center.</span></span>

![Captura de tela da política de roteamento de chamadas de emergência.](media/emergency-call-routing-policy.png)

## <a name="caller-id-policies"></a><span data-ttu-id="8ff2d-113">Políticas de ID do chamador</span><span class="sxs-lookup"><span data-stu-id="8ff2d-113">Caller ID policies</span></span>

<span data-ttu-id="8ff2d-114">[As políticas de ID do chamador](caller-id-policies.md) são usadas para alterar ou bloquear a ID do chamador.</span><span class="sxs-lookup"><span data-stu-id="8ff2d-114">[Caller ID policies](caller-id-policies.md) are used to change or block caller ID.</span></span>

![Captura de tela da política de ID do chamador.](media/caller-id-policy.png)

## <a name="voice-routing-policies"></a><span data-ttu-id="8ff2d-116">Políticas de roteamento de voz</span><span class="sxs-lookup"><span data-stu-id="8ff2d-116">Voice routing policies</span></span>

<span data-ttu-id="8ff2d-117">Uma [política de roteamento de](manage-voice-routing-policies.md) voz é um contêiner para registros de uso da PSTN (Rede Telefônica Pública Comugada).</span><span class="sxs-lookup"><span data-stu-id="8ff2d-117">A [voice routing policy](manage-voice-routing-policies.md) is a container for Public Switched Telephone Network (PSTN) usage records.</span></span> <span data-ttu-id="8ff2d-118">Você pode usar essas políticas se sua organização tiver implantado Sistema de Telefonia **Roteamento Direto.**</span><span class="sxs-lookup"><span data-stu-id="8ff2d-118">You can use these policies if your organization has deployed **Phone System Direct Routing**.</span></span> <span data-ttu-id="8ff2d-119">As políticas de roteamento de voz podem ser gerenciadas com o PowerShell ou no Teams de administração.</span><span class="sxs-lookup"><span data-stu-id="8ff2d-119">Voice routing policies can be managed with PowerShell or in the Teams admin center.</span></span>

![Captura de tela da política de roteamento de voz.](media/voice-routing-policy.png)

## <a name="calling-policies"></a><span data-ttu-id="8ff2d-121">Políticas de chamadas</span><span class="sxs-lookup"><span data-stu-id="8ff2d-121">Calling policies</span></span>

<span data-ttu-id="8ff2d-122">[As políticas de](teams-calling-policy.md) chamada controlam quais recursos de encaminhamento de chamadas e chamadas estão disponíveis para os usuários, incluindo se um usuário pode fazer chamadas privadas, enviar chamadas para grupos de chamadas e encaminhar chamadas para a caixa postal.</span><span class="sxs-lookup"><span data-stu-id="8ff2d-122">[Calling policies](teams-calling-policy.md) control which calling and call forwarding features are available to users including whether a user can make private calls, send calls to call groups, and route calls to voicemail.</span></span>

![Captura de tela da política de chamada.](media/calling-policy.png)

## <a name="call-park-and-retrieve-policies"></a><span data-ttu-id="8ff2d-124">Estacionamento de chamada e políticas de recuperação</span><span class="sxs-lookup"><span data-stu-id="8ff2d-124">Call park and retrieve policies</span></span>

<span data-ttu-id="8ff2d-125">[O estacionamento de chamada e a](call-park-and-retrieve.md) recuperação permitem que os usuários coloquem outros usuários em espera e habilitam o mesmo usuário ou outra pessoa a continuar a chamada.</span><span class="sxs-lookup"><span data-stu-id="8ff2d-125">[Call park and retrieve](call-park-and-retrieve.md) lets users put other users on hold and enables the same user or someone else to continue the call.</span></span>

![Captura de tela do estacionamento de chamada e política de recuperação.](media/call-park-policy.png)

## <a name="create-and-manage-dial-plans"></a><span data-ttu-id="8ff2d-127">Criar e gerenciar planos de discagem</span><span class="sxs-lookup"><span data-stu-id="8ff2d-127">Create and manage dial plans</span></span>

<span data-ttu-id="8ff2d-128">[Planos de discagem](create-and-manage-dial-plans.md) traduzem números de telefone discados para autorização e roteamento de chamadas.</span><span class="sxs-lookup"><span data-stu-id="8ff2d-128">[Dial plans](create-and-manage-dial-plans.md) translate dialed phone numbers for call authorization and routing.</span></span> <span data-ttu-id="8ff2d-129">Você pode criar e gerenciar planos de discagem por meio do PowerShell ou no Microsoft Teams de administração.</span><span class="sxs-lookup"><span data-stu-id="8ff2d-129">You can create and manage dial plans through PowerShell or in the Microsoft Teams admin center.</span></span>

![Captura de tela do plano de discagem.](media/dial-plans.png)

## <a name="related-topics"></a><span data-ttu-id="8ff2d-131">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="8ff2d-131">Related topics</span></span>

* [<span data-ttu-id="8ff2d-132">Gerenciar políticas de chamada de emergência em Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="8ff2d-132">Manage emergency calling policies in Microsoft Teams</span></span>](manage-emergency-calling-policies.md)
* [<span data-ttu-id="8ff2d-133">Gerenciar políticas de roteamento de chamada</span><span class="sxs-lookup"><span data-stu-id="8ff2d-133">Manage emergency call routing policies</span></span>](manage-emergency-call-routing-policies.md)
* [<span data-ttu-id="8ff2d-134">Gerenciar políticas de identificação de chamadas no Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="8ff2d-134">Manage caller ID policies in Microsoft Teams</span></span>](caller-id-policies.md)
* [<span data-ttu-id="8ff2d-135">Gerenciar políticas de roteamento de voz</span><span class="sxs-lookup"><span data-stu-id="8ff2d-135">Manage voice routing policies</span></span>](manage-voice-routing-policies.md)
* [<span data-ttu-id="8ff2d-136">Políticas de chamada no Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="8ff2d-136">Calling policies in Microsoft Teams</span></span>](teams-calling-policy.md)
* [<span data-ttu-id="8ff2d-137">Estacionamento e recuperação de chamadas no Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="8ff2d-137">Call park and retrieve in Microsoft Teams</span></span>](call-park-and-retrieve.md)
* [<span data-ttu-id="8ff2d-138">Criar e gerenciar planos de discagem</span><span class="sxs-lookup"><span data-stu-id="8ff2d-138">Create and manage dial plans</span></span>](create-and-manage-dial-plans.md)
* [<span data-ttu-id="8ff2d-139">Gerenciar Teams com políticas</span><span class="sxs-lookup"><span data-stu-id="8ff2d-139">Manage Teams with policies</span></span>](manage-teams-with-policies.md)
