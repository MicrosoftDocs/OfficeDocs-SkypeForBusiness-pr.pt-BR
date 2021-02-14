---
title: Conferência na rede para Audioconferência
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.reviewer: oscarr
ms.topic: conceptual
ms.tgt.pltfrm: cloud
audience: admin
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
- M365-collaboration
- m365initiative-meetings
localization_priority: Normal
f1.keywords:
- NOCSH
ms.custom:
- Audio Conferencing
description: A seguir, descreve a funcionalidade Abrir Visualização para Conferência de Áudio na rede.
ms.openlocfilehash: 1ae61034ef083c89e14c67cef0effa1c105de758
ms.sourcegitcommit: 57fddb045f4a9df14cc421b1f6a228df91f334de
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/13/2020
ms.locfileid: "49031857"
---
# <a name="open-preview-of-on-network-conferencing-for-audio-conferencing"></a><span data-ttu-id="4eb7e-103">Abrir a visualização da conferência na rede para audioconferência</span><span class="sxs-lookup"><span data-stu-id="4eb7e-103">Open Preview of On-network Conferencing for Audio Conferencing</span></span>

<span data-ttu-id="4eb7e-104">A Visualização Aberta da Conferência Local está disponível para todos os clientes.</span><span class="sxs-lookup"><span data-stu-id="4eb7e-104">The Open Preview of On-network Conferencing is available to all customers.</span></span> <span data-ttu-id="4eb7e-105">A Conferência na rede permite que as organizações enviem chamadas de AudioConferência de entrada e saída para números de discagem da Microsoft por meio do Roteamento Direto.</span><span class="sxs-lookup"><span data-stu-id="4eb7e-105">On-network Conferencing allows organizations to send inbound and outbound Audio Conferencing calls to Microsoft dial-in numbers through Direct Routing.</span></span> <span data-ttu-id="4eb7e-106">Esse recurso não se destina a estender o suporte da AudioConferência para números de discagem de terceiros.</span><span class="sxs-lookup"><span data-stu-id="4eb7e-106">This capability is not intended to extend the support of Audio Conferencing to third party dial-in numbers.</span></span> <span data-ttu-id="4eb7e-107">A Conferência na rede não será suportada se for usada para encaminhar chamadas de entrada para o serviço de Audioconferência por meio de números de telefone de discagem de terceiros.</span><span class="sxs-lookup"><span data-stu-id="4eb7e-107">On-network Conferencing is not supported if it is used to route inbound calls to the Audio Conferencing service through third party dial-in phone numbers.</span></span>

<span data-ttu-id="4eb7e-108">Este artigo descreve os pré-requisitos e as etapas de configuração necessárias para habilitar a Conferência Local para sua organização.</span><span class="sxs-lookup"><span data-stu-id="4eb7e-108">This article describes the prerequisites and configuration steps required to enable On-network Conferencing for your organization.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="4eb7e-109">A Conferência Na Rede NÃO deve ser implantada com nenhum equipamento de telefonia na Índia.</span><span class="sxs-lookup"><span data-stu-id="4eb7e-109">On-network Conferencing must NOT be deployed with any telephony equipment in India.</span></span>
  
## <a name="prerequisites"></a><span data-ttu-id="4eb7e-110">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="4eb7e-110">Prerequisites</span></span>

<span data-ttu-id="4eb7e-111">Antes de configurar a Conferência na rede, certifique-se de que sua organização atenda aos seguintes pré-requisitos:</span><span class="sxs-lookup"><span data-stu-id="4eb7e-111">Before configuring On-network Conferencing, make sure your organization meets the following prerequisites:</span></span> 

- <span data-ttu-id="4eb7e-112">Certifique-se de que todos os usuários em sua organização habilitados ou habilitados para Audioconferência estão usando o Teams para todas as Reuniões.</span><span class="sxs-lookup"><span data-stu-id="4eb7e-112">Ensure that all users in your organization who are enabled, or will be enabled, for Audio Conferencing are using Teams for all Meetings.</span></span> <span data-ttu-id="4eb7e-113">O roteamento de chamadas de Audioconferência de entrada e saída por meio de Conferências na rede só tem suporte para reuniões do Teams.</span><span class="sxs-lookup"><span data-stu-id="4eb7e-113">The routing of inbound and outbound Audio Conferencing calls through On-network Conferencing is only supported for Teams meetings.</span></span>

- <span data-ttu-id="4eb7e-114">Atribua licenças de Audioconferência a todos os usuários que usarão a Conferência na rede.</span><span class="sxs-lookup"><span data-stu-id="4eb7e-114">Assign Audio Conferencing licenses to all users who will be using On-network Conferencing.</span></span>

- <span data-ttu-id="4eb7e-115">Configurar o serviço de Audioconferência.</span><span class="sxs-lookup"><span data-stu-id="4eb7e-115">Set up the Audio Conferencing service.</span></span> <span data-ttu-id="4eb7e-116">Para obter mais informações, [consulte Configurar a Audioconferência para o Microsoft Teams.](set-up-audio-conferencing-in-teams.md)</span><span class="sxs-lookup"><span data-stu-id="4eb7e-116">For additional information, see [Set up Audio Conferencing for Microsoft Teams](set-up-audio-conferencing-in-teams.md).</span></span>

- <span data-ttu-id="4eb7e-117">Configurar seu Controlador de Borda de Sessão (SBC) para Roteamento Direto.</span><span class="sxs-lookup"><span data-stu-id="4eb7e-117">Set up your Session Border Controller (SBC) for Direct Routing.</span></span> <span data-ttu-id="4eb7e-118">Para obter informações adicionais, consulte [Planejar Roteamento Direto e](direct-routing-plan.md) Configurar [Roteamento Direto.](direct-routing-configure.md)</span><span class="sxs-lookup"><span data-stu-id="4eb7e-118">For additional information, see [Plan Direct Routing](direct-routing-plan.md) and [Configure Direct Routing](direct-routing-configure.md).</span></span> 

  <span data-ttu-id="4eb7e-119">Se você estiver configurando o Roteamento Direto somente para fins de AudioConferência, precisará apenas concluir a "Etapa 1: Conectar seu SBC" para Conferências na rede.</span><span class="sxs-lookup"><span data-stu-id="4eb7e-119">If you are setting up Direct Routing only for the purposes of Audio Conferencing, then you need only complete “Step 1: Connect your SBC” for On-network Conferencing.</span></span>
  
## <a name="enable-the-routing-of-dial-in-calls-to-microsoft-audio-conferencing-through-direct-routing"></a><span data-ttu-id="4eb7e-120">Habilitar o roteamento de chamadas de discagem para a Audioconferência da Microsoft por meio do Roteamento Direto</span><span class="sxs-lookup"><span data-stu-id="4eb7e-120">Enable the routing of dial-in calls to Microsoft Audio Conferencing through Direct Routing</span></span> 

<span data-ttu-id="4eb7e-121">Para rotear chamadas discadas feitas por seus usuários locais para o serviço de Audioconferência por meio do Roteamento Direto, você precisa configurar as regras de roteamento apropriadas para seus SBCs e PBXs (Private Branch Exchange).</span><span class="sxs-lookup"><span data-stu-id="4eb7e-121">To route dial-in calls made by your on-premises users to the Audio Conferencing service through Direct Routing, you need to configure appropriate routing rules for your SBCs and Private Branch Exchange(s) (PBXs).</span></span>

<span data-ttu-id="4eb7e-122">Você precisa configurar o equipamento de telefonia de seus sites para encaminhar chamadas para qualquer número de serviço da ponte de conferência da sua organização por meio de um tronco de Roteamento Direto.</span><span class="sxs-lookup"><span data-stu-id="4eb7e-122">You need to configure the telephony equipment of your sites to route calls to any service number of the conference bridge of your organization through a Direct Routing trunk.</span></span>

<span data-ttu-id="4eb7e-123">Você pode encontrar os números de serviço no Centro de administração do Teams em **Pontes** de Conferência > Reuniões ou usando o cmdlet Get-CsOnlineDialInConferencingBridge do Skype for Business Online.</span><span class="sxs-lookup"><span data-stu-id="4eb7e-123">You can find the service numbers in Teams admin center under **Meetings -> Conferencing Bridges** or by using the Skype for Business Online PowerShell cmdlet Get-CsOnlineDialInConferencingBridge.</span></span> <span data-ttu-id="4eb7e-124">Para obter informações adicionais, consulte uma lista de números [de Audioconferência no Microsoft Teams.](see-a-list-of-audio-conferencing-numbers-in-teams.md)</span><span class="sxs-lookup"><span data-stu-id="4eb7e-124">For additional information, see a list of [Audio Conferencing numbers in Microsoft Teams](see-a-list-of-audio-conferencing-numbers-in-teams.md).</span></span>

> [!NOTE]
> <span data-ttu-id="4eb7e-125">Esse recurso não está disponível para usuários com a licença de Audioconferência paga por minuto.</span><span class="sxs-lookup"><span data-stu-id="4eb7e-125">This feature is not available to users with the pay-per-minute Audio Conferencing license.</span></span>

## <a name="enable-the-routing-of-teams-meeting-dial-out-calls-through-direct-routing"></a><span data-ttu-id="4eb7e-126">Habilitar o roteamento de chamadas de discagem de reunião do Teams por meio do Roteamento Direto</span><span class="sxs-lookup"><span data-stu-id="4eb7e-126">Enable the routing of Teams meeting dial-out calls through Direct Routing</span></span>

<span data-ttu-id="4eb7e-127">As chamadas de discagem de reunião do Teams são iniciadas a partir de uma reunião em sua organização para números PSTN, incluindo chamadas e chamadas para trazer novos participantes para uma reunião.</span><span class="sxs-lookup"><span data-stu-id="4eb7e-127">Teams meeting dial-out calls are initiated from within a meeting in your organization to PSTN numbers, including call-me-at calls and calls to bring new participants to a meeting.</span></span> 

<span data-ttu-id="4eb7e-128">Para habilitar o roteamento de discagem de reunião do Teams por meio do Roteamento Direto para usuários na rede, você precisa criar e atribuir uma política de roteamento de Audioconferência chamada "OnlineAudioConferencingRoutingPolicy".</span><span class="sxs-lookup"><span data-stu-id="4eb7e-128">To enable Teams meeting dial-out routing through Direct Routing to on-network users, you need to create and assign an Audio Conferencing routing policy called “OnlineAudioConferencingRoutingPolicy”.</span></span> 

<span data-ttu-id="4eb7e-129">A política OnlineAudioConferencingRoutingPolicy é equivalente à CsOnlineVoiceRoutingPolicy para chamadas PSTN 1:1 via Roteamento Direto.</span><span class="sxs-lookup"><span data-stu-id="4eb7e-129">The OnlineAudioConferencingRoutingPolicy policy is equivalent to the CsOnlineVoiceRoutingPolicy for 1:1 PSTN calls via Direct Routing.</span></span> <span data-ttu-id="4eb7e-130">A política OnlineAudioConferencingRoutingPolicy pode ser gerenciada usando os seguintes cmdlets:</span><span class="sxs-lookup"><span data-stu-id="4eb7e-130">The OnlineAudioConferencingRoutingPolicy policy can be managed by using the following cmdlets:</span></span>

-   <span data-ttu-id="4eb7e-131">New-CsOnlineAudioConferencingRoutingPolicy</span><span class="sxs-lookup"><span data-stu-id="4eb7e-131">New-CsOnlineAudioConferencingRoutingPolicy</span></span>
- <span data-ttu-id="4eb7e-132">Set-CsOnlineAudioConferencingRoutingPolicy</span><span class="sxs-lookup"><span data-stu-id="4eb7e-132">Set-CsOnlineAudioConferencingRoutingPolicy</span></span>
- <span data-ttu-id="4eb7e-133">Get-CsOnlineAudioConferencingRoutingPolicy</span><span class="sxs-lookup"><span data-stu-id="4eb7e-133">Get-CsOnlineAudioConferencingRoutingPolicy</span></span>
- <span data-ttu-id="4eb7e-134">Grant-CsOnlineAudioConferencingRoutingPolicy</span><span class="sxs-lookup"><span data-stu-id="4eb7e-134">Grant-CsOnlineAudioConferencingRoutingPolicy</span></span>
- <span data-ttu-id="4eb7e-135">Remove-CsOnlineAudioConferencingRoutingPolicy</span><span class="sxs-lookup"><span data-stu-id="4eb7e-135">Remove-CsOnlineAudioConferencingRoutingPolicy</span></span>

<span data-ttu-id="4eb7e-136">Para obter mais informações sobre roteamento para Roteamento Direto, consulte [Configurar roteamento de voz para Roteamento Direto.](direct-routing-voice-routing.md)</span><span class="sxs-lookup"><span data-stu-id="4eb7e-136">For more information about routing for Direct Routing, see [Configure voice routing for Direct Routing](direct-routing-voice-routing.md).</span></span>


<span data-ttu-id="4eb7e-137">Para habilitar o roteamento de chamadas de discagem de reunião por meio do Roteamento Direto, você precisa:</span><span class="sxs-lookup"><span data-stu-id="4eb7e-137">To enable the routing of meeting dial-out calls through Direct Routing, you need to:</span></span> 

- <span data-ttu-id="4eb7e-138">Configurar políticas de roteamento de audioconferência</span><span class="sxs-lookup"><span data-stu-id="4eb7e-138">Configure Audio Conferencing routing policies</span></span>
- <span data-ttu-id="4eb7e-139">Configurar o roteamento no equipamento de telefonia de sua organização</span><span class="sxs-lookup"><span data-stu-id="4eb7e-139">Configure the routing on the telephony equipment of your organization</span></span>
- <span data-ttu-id="4eb7e-140">(Opcional) Configurar um plano de discagem</span><span class="sxs-lookup"><span data-stu-id="4eb7e-140">(Optional) Configure a dial plan</span></span>

<span data-ttu-id="4eb7e-141">As chamadas de discagem de reuniões do Teams vêm do número de serviço padrão na ponte de conferência.</span><span class="sxs-lookup"><span data-stu-id="4eb7e-141">Dial-out calls from Teams meetings are coming from the default service number on the conference bridge.</span></span> <span data-ttu-id="4eb7e-142">Para obter informações adicionais sobre o número de serviço padrão da ponte de Audioconferência, consulte Alterar os números de telefone em sua ponte [de Audioconferência.](change-the-phone-numbers-on-your-audio-conferencing-bridge.md)</span><span class="sxs-lookup"><span data-stu-id="4eb7e-142">For additional information on the default service number of your Audio Conferencing bridge, see [Change the phone numbers on your Audio Conferencing bridge](change-the-phone-numbers-on-your-audio-conferencing-bridge.md).</span></span>

### <a name="configure-audio-conferencing-routing-policies"></a><span data-ttu-id="4eb7e-143">Configurar políticas de roteamento de audioconferência</span><span class="sxs-lookup"><span data-stu-id="4eb7e-143">Configure Audio Conferencing routing policies</span></span>

<span data-ttu-id="4eb7e-144">A política de roteamento de AudioConferência OnlineAudioConferencingRoutingPolicy determina quais chamadas de discagem de reunião são roteada para troncos de Roteamento Direto.</span><span class="sxs-lookup"><span data-stu-id="4eb7e-144">The Audio Conferencing routing policy OnlineAudioConferencingRoutingPolicy determines which meeting dial-out calls are routed to Direct Routing trunks.</span></span> <span data-ttu-id="4eb7e-145">Se você estiver familiarizado com a política CsOnlineVoiceRoutingPolicy, essa política funciona de maneira muito semelhante.</span><span class="sxs-lookup"><span data-stu-id="4eb7e-145">If you are familiar with the CsOnlineVoiceRoutingPolicy policy, this policy works in a very similar way.</span></span>

<span data-ttu-id="4eb7e-146">As etapas a seguir são necessárias para configurar políticas de roteamento de Audioconferência:</span><span class="sxs-lookup"><span data-stu-id="4eb7e-146">The following steps are needed to set up Audio Conferencing routing policies:</span></span>
1.  <span data-ttu-id="4eb7e-147">Criar usos de PSTN</span><span class="sxs-lookup"><span data-stu-id="4eb7e-147">Create PSTN usages</span></span>
2.  <span data-ttu-id="4eb7e-148">Configurar rotas de voz</span><span class="sxs-lookup"><span data-stu-id="4eb7e-148">Configure voice routes</span></span>
3.  <span data-ttu-id="4eb7e-149">Criar políticas de roteamento de voz de audioconferência</span><span class="sxs-lookup"><span data-stu-id="4eb7e-149">Create Audio Conferencing voice routing policies</span></span>
4.  <span data-ttu-id="4eb7e-150">Atribuir uma política aos usuários</span><span class="sxs-lookup"><span data-stu-id="4eb7e-150">Assign a policy to your users</span></span>


#### <a name="create-pstn-usages"></a><span data-ttu-id="4eb7e-151">Criar usos de PSTN</span><span class="sxs-lookup"><span data-stu-id="4eb7e-151">Create PSTN usages</span></span>

<span data-ttu-id="4eb7e-152">Os usos de PSTN são coleções de rotas de voz.</span><span class="sxs-lookup"><span data-stu-id="4eb7e-152">PSTN usages are collections of voice routes.</span></span> <span data-ttu-id="4eb7e-153">Quando uma chamada discada é iniciada a partir da reunião de um determinado organizador, as rotas de voz são usadas para determinar o caminho de roteamento da chamada com base nos usos PSTN associados ao usuário por meio da política de roteamento de voz do usuário.</span><span class="sxs-lookup"><span data-stu-id="4eb7e-153">When a dial-out call is initiated from the meeting of a given organizer, voice routes will be used to determine the routing path of the call based on the PSTN usages that are associated to the user via the user’s voice routing policy.</span></span>

<span data-ttu-id="4eb7e-154">Você pode criar um uso PSTN usando o cmdlet "Set-CsOnlinePstnUsage".</span><span class="sxs-lookup"><span data-stu-id="4eb7e-154">You can create a PSTN usage by using the “Set-CsOnlinePstnUsage” cmdlet.</span></span> <span data-ttu-id="4eb7e-155">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="4eb7e-155">For Example:</span></span>

```powershell
Set-CsOnlinePstnUsage -Identity Global -Usage @{Add="US and Canada"}
```

#### <a name="configure-voice-routes"></a><span data-ttu-id="4eb7e-156">Configurar rotas de voz</span><span class="sxs-lookup"><span data-stu-id="4eb7e-156">Configure voice routes</span></span>

<span data-ttu-id="4eb7e-157">As rotas de voz determinam o gateway PSTN que deve ser usado para rotear uma chamada com base no número de telefone que é discado de uma reunião do Teams.</span><span class="sxs-lookup"><span data-stu-id="4eb7e-157">Voice routes determine the PSTN gateway that should be used to route a call based on the phone number that is dialed from a Teams meeting.</span></span> <span data-ttu-id="4eb7e-158">As rotas de voz determinam o gateway PSTN que deve ser usado para rotear uma determinada chamada, combinando o número de telefone discado de uma reunião do Teams com um padrão regex.</span><span class="sxs-lookup"><span data-stu-id="4eb7e-158">Voice routes determine the PSTN gateway that should be used to route a given call by matching the phone number dialed from a Teams meeting with a regex pattern.</span></span> <span data-ttu-id="4eb7e-159">Ao criar uma rota de voz, a rota deve estar associada a um ou mais usos de PSTN.</span><span class="sxs-lookup"><span data-stu-id="4eb7e-159">When creating a voice route, the route must be associated to one or more PSTN usages.</span></span>

<span data-ttu-id="4eb7e-160">Você pode criar uma rota de voz e definir o regex e os gateways a serem associados à rota de voz usando o cmdlet "New-CsOnlineVoiceRoute".</span><span class="sxs-lookup"><span data-stu-id="4eb7e-160">You can create a voice route and define the regex and gateways to be associated with the voice route by using the “New-CsOnlineVoiceRoute” cmdlet.</span></span> <span data-ttu-id="4eb7e-161">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="4eb7e-161">For Example:</span></span>

```powershell
New-CsOnlineVoiceRoute -Identity "Redmond 1" -NumberPattern "^\+1(425|206)(\d{7})$" -OnlinePstnGatewayList sbc1.contoso.biz, sbc2.contoso.biz -Priority 1 -OnlinePstnUsages "US and Canada"
```

#### <a name="create-audio-conferencing-voice-routing-policies"></a><span data-ttu-id="4eb7e-162">Criar políticas de roteamento de voz de audioconferência</span><span class="sxs-lookup"><span data-stu-id="4eb7e-162">Create Audio Conferencing voice routing policies</span></span>

<span data-ttu-id="4eb7e-163">As políticas de roteamento de voz de audioconferência determinam as possíveis rotas que podem ser usadas para rotear uma chamada proveniente das reuniões de um organizador com base no número de telefone de destino da chamada discada da reunião.</span><span class="sxs-lookup"><span data-stu-id="4eb7e-163">Audio Conferencing voice routing policies determine the possible routes that can be used to route a call originating from the meetings of an organizer based on the target phone number of the meeting dial-out call.</span></span> <span data-ttu-id="4eb7e-164">As políticas de roteamento de voz de audioconferência estão associadas a um ou mais usos de PSTN, que, por sua vez, determinam as possíveis rotas que serão usadas para as chamadas de discagem de reunião dos organizadores associados à política.</span><span class="sxs-lookup"><span data-stu-id="4eb7e-164">Audio Conferencing voice routing policies are associated to one or more PSTN usages, which in turn, determine the possible routes that will be attempted to be used for the meeting dial-out calls of the organizers associated to the policy.</span></span>

<span data-ttu-id="4eb7e-165">Você pode criar uma política de roteamento de voz de AudioConferência usando o cmdlet "New-CsOnlineAudioConferencingRoutingPolicy".</span><span class="sxs-lookup"><span data-stu-id="4eb7e-165">You can create an Audio Conferencing voice routing policy by using the “New- CsOnlineAudioConferencingRoutingPolicy” cmdlet.</span></span> <span data-ttu-id="4eb7e-166">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="4eb7e-166">For Example:</span></span>

```powershell
New-CsOnlineAudioConferencingRoutingPolicy "Policy 1" -OnlinePstnUsages "US and Canada"
```

<span data-ttu-id="4eb7e-167">Depois que a política for atribuída a um usuário e quando uma chamada de discagem de reunião for iniciada em uma das reuniões do usuário, as rotas de voz nos usos de PSTN associados ao organizador por meio da política de roteamento de voz do usuário serão avaliadas.</span><span class="sxs-lookup"><span data-stu-id="4eb7e-167">After the policy is assigned to a user, and when a meeting dial-out call is initiated from one of the user's meetings, the voice routes in the PSTN usages that are associated to the organizer through the user's voice routing policy will be evaluated.</span></span> <span data-ttu-id="4eb7e-168">Se o destino da chamada discada da reunião corresponde a um regex em uma das rotas de voz associadas ao organizador, a chamada discada da reunião será roteada para o gateway PSTN definido na rota de voz.</span><span class="sxs-lookup"><span data-stu-id="4eb7e-168">If the meeting dial-out call destination matches a regex in one of the voice routes that are associated to the organizer, the meeting dial-out call will be routed to the PSTN gateway defined in the voice route.</span></span> <span data-ttu-id="4eb7e-169">Se o destino da chamada discada da reunião não corresponder a nenhuma das rotas de voz associadas ao organizador, a chamada discada da reunião será roteada pela Microsoft.</span><span class="sxs-lookup"><span data-stu-id="4eb7e-169">If the meeting dial-out call destination does not match any of the voice routes associated to the organizer, the meeting dial-out call will be routed by Microsoft.</span></span>

#### <a name="assign-a-policy-to-your-users"></a><span data-ttu-id="4eb7e-170">Atribuir uma política aos usuários</span><span class="sxs-lookup"><span data-stu-id="4eb7e-170">Assign a policy to your users</span></span>

<span data-ttu-id="4eb7e-171">Depois que as políticas de roteamento de Audioconferência são definidas, agora você pode atribuí-las aos usuários.</span><span class="sxs-lookup"><span data-stu-id="4eb7e-171">After the Audio Conferencing routing policies are defined, you can now assign them to users.</span></span> <span data-ttu-id="4eb7e-172">Depois que as políticas são atribuídas a elas, as chamadas discadas da reunião serão avaliadas em relação a ela para determinar o caminho de roteamento.</span><span class="sxs-lookup"><span data-stu-id="4eb7e-172">After policies are assigned to them, the meeting dial-out calls will be evaluated against it to determine their routing path.</span></span> <span data-ttu-id="4eb7e-173">As políticas de roteamento de audioconferência são sempre avaliadas com base no organizador da reunião, independentemente do usuário na reunião que inicia uma chamada discada de reunião.</span><span class="sxs-lookup"><span data-stu-id="4eb7e-173">Audio Conferencing routing policies are always evaluated based on the organizer of the meeting, independently from the user in the meeting that initiates a meeting dial-out call.</span></span>

<span data-ttu-id="4eb7e-174">Você pode atribuir uma política de roteamento de voz de AudioConferência a um usuário usando o cmdlet "Grant-CsOnlineAudioConferencingRoutingPolicy".</span><span class="sxs-lookup"><span data-stu-id="4eb7e-174">You can assign an Audio Conferencing voice routing policy to a user by using the “Grant-CsOnlineAudioConferencingRoutingPolicy” cmdlet.</span></span> <span data-ttu-id="4eb7e-175">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="4eb7e-175">For example:</span></span>

```powershell
Grant-CsOnlineAudioConferencingRoutingPolicy -Identity "<User Identity>" -PolicyName "Policy 1”
```


### <a name="configure-routing-on-the-telephony-equipment-of-your-organization"></a><span data-ttu-id="4eb7e-176">Configurar o roteamento no equipamento de telefonia da sua organização</span><span class="sxs-lookup"><span data-stu-id="4eb7e-176">Configure routing on the telephony equipment of your organization</span></span>

<span data-ttu-id="4eb7e-177">No equipamento de telefonia da sua organização, você precisa garantir que as chamadas de discagem de reunião roteados pelo Roteamento Direto sejam roteados para o destino desejado na rede.</span><span class="sxs-lookup"><span data-stu-id="4eb7e-177">On the telephony equipment of your organization, you need to ensure that the meeting dial-out calls routed through Direct Routing are routed to the intended on-network destination.</span></span>


### <a name="optional-configure-a-dial-plan"></a><span data-ttu-id="4eb7e-178">(Opcional) Configurar um plano de discagem</span><span class="sxs-lookup"><span data-stu-id="4eb7e-178">(Optional) Configure a dial plan</span></span>

<span data-ttu-id="4eb7e-179">Um plano de discagem é um conjunto de regras de normalização que traduzem números de telefone discados por um usuário individual em um formato alternativo (normalmente E.164) para fins de autorização de chamada e roteamento de chamadas.</span><span class="sxs-lookup"><span data-stu-id="4eb7e-179">A dial plan is a set of normalization rules that translate dialed phone numbers by an individual user into an alternate format (typically E.164) for purposes of call authorization and call routing.</span></span>

<span data-ttu-id="4eb7e-180">Por padrão, os usuários do Teams podem discar para números PSTN no formato E.164, ou seja, + \<country code\> \<number\> .</span><span class="sxs-lookup"><span data-stu-id="4eb7e-180">By default, Teams users can dial-out to PSTN numbers in E.164 format, that is, +\<country code\>\<number\>.</span></span> <span data-ttu-id="4eb7e-181">No entanto, os planos de discagem podem ser usados para permitir que os usuários disquem números de telefone em outros formatos, por exemplo, extensões de 4 dígitos.</span><span class="sxs-lookup"><span data-stu-id="4eb7e-181">However, dial plans can be used to allow users to dial phone numbers in other formats, for instance 4-digit extensions.</span></span>

<span data-ttu-id="4eb7e-182">Se quiser habilitar a discagem baseada em extensão por meio de conferência na rede, você pode configurar planos de discagem para corresponder ao padrão de discagem de extensão aos intervalos de número de telefone do número de telefone da sua organização.</span><span class="sxs-lookup"><span data-stu-id="4eb7e-182">If you would like to enable extension-based dialing through On-network conferencing, you can set up dial plans to match the extension dialing pattern to the phone number ranges of the phone number of your organization.</span></span> <span data-ttu-id="4eb7e-183">Para configurar planos de discagem, consulte [Criar e gerenciar planos de discagem.](create-and-manage-dial-plans.md)</span><span class="sxs-lookup"><span data-stu-id="4eb7e-183">To set up dial plans, see [Create and manage dial plans](create-and-manage-dial-plans.md).</span></span>


## <a name="known-issues-in-open-preview"></a><span data-ttu-id="4eb7e-184">Problemas conhecidos no Open Preview</span><span class="sxs-lookup"><span data-stu-id="4eb7e-184">Known issues in Open Preview</span></span>

<span data-ttu-id="4eb7e-185">Veja a seguir uma lista de problemas conhecidos que estão presentes no lançamento de Open Preview da conferência na rede.</span><span class="sxs-lookup"><span data-stu-id="4eb7e-185">The following is a list of known issues that are currently present in the Open Preview release of On-network conferencing.</span></span> <span data-ttu-id="4eb7e-186">A Microsoft está trabalhando para resolver esses problemas.</span><span class="sxs-lookup"><span data-stu-id="4eb7e-186">Microsoft is working on addressing these issues.</span></span>

| <span data-ttu-id="4eb7e-187">Problema</span><span class="sxs-lookup"><span data-stu-id="4eb7e-187">Issue</span></span> | <span data-ttu-id="4eb7e-188">Solução alternativa</span><span class="sxs-lookup"><span data-stu-id="4eb7e-188">Workaround</span></span> |
| :--- | :--- |
| <span data-ttu-id="4eb7e-189">Chamadas de discagem com IDs de chamadas anônimas/ocultas roteados por meio de conferência na rede não podem ser conectadas à reunião.</span><span class="sxs-lookup"><span data-stu-id="4eb7e-189">Dial-in calls with anonymous/hidden caller IDs that are routed through On-network conferencing cannot be connected to the meeting.</span></span> | <span data-ttu-id="4eb7e-190">Se possível, defina uma configuração em seu PBX ou SBC para sempre enviar uma ID de chamadas para chamadas roteada por meio de conferência na rede.</span><span class="sxs-lookup"><span data-stu-id="4eb7e-190">If possible, set a configuration in your PBX or SBC to always send a caller ID for calls routed via On-network conferencing.</span></span>|
| <span data-ttu-id="4eb7e-191">Em alguns casos, a mensagem de boas-vindas que é tocada aos usuários quando eles discam para o serviço ("Bem-vindo ao serviço de Audioconferência...") é truncada e os usuários não ouvem a palavra "Bem-vindo".</span><span class="sxs-lookup"><span data-stu-id="4eb7e-191">In some cases, the welcome message that is played to users when they dial in to the service (“Welcome to the Audio Conferencing service…”) is truncated and users do not hear the “Welcome” word.</span></span>| <span data-ttu-id="4eb7e-192">Não há soluções alternativas para esse problema no momento.</span><span class="sxs-lookup"><span data-stu-id="4eb7e-192">There are no workarounds for this issue at the moment.</span></span> |




## <a name="related-topics"></a><span data-ttu-id="4eb7e-193">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="4eb7e-193">Related topics</span></span>


