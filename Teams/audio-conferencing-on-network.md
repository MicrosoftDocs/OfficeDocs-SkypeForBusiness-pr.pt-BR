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
description: O seguinte descreve On-network para Audioconferência.
ms.openlocfilehash: b7851bd2457debe8ee0de3144e24a15edb521222
ms.sourcegitcommit: b39bd1de0219a9e3a3b0c97fc485c9578ddb643c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/01/2021
ms.locfileid: "53230558"
---
# <a name="on-network-conferencing-for-audio-conferencing"></a><span data-ttu-id="b8a47-103">Conferência na rede para Audioconferência</span><span class="sxs-lookup"><span data-stu-id="b8a47-103">On-network Conferencing for Audio Conferencing</span></span>

<span data-ttu-id="b8a47-104">A Conferência na rede permite que as organizações enviem chamadas de Audioconferência de entrada e saída para números de discagem da Microsoft por meio do Roteamento Direto.</span><span class="sxs-lookup"><span data-stu-id="b8a47-104">On-network Conferencing allows organizations to send inbound and outbound Audio Conferencing calls to Microsoft dial-in numbers through Direct Routing.</span></span> <span data-ttu-id="b8a47-105">Esse recurso não se destina a estender o suporte da Audioconferência para números de discagem de terceiros.</span><span class="sxs-lookup"><span data-stu-id="b8a47-105">This capability is not intended to extend the support of Audio Conferencing to third party dial-in numbers.</span></span> <span data-ttu-id="b8a47-106">A Conferência na rede não será suportada se ela for usada para rotear chamadas de entrada para o serviço de Audioconferência por meio de números de telefone de discagem de terceiros ou chamadas de saída para o PSTN da Ponte de Audioconferência da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="b8a47-106">On-network Conferencing is not supported if it is used to route inbound calls to the Audio Conferencing service through third party dial-in phone numbers or outbound calls to the PSTN from Microsoft Audio Conferencing Bridge.</span></span> 

<span data-ttu-id="b8a47-107">Este artigo descreve os pré-requisitos e as etapas de configuração necessárias para habilitar a Conferência na rede para sua organização.</span><span class="sxs-lookup"><span data-stu-id="b8a47-107">This article describes the prerequisites and configuration steps required to enable On-network Conferencing for your organization.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="b8a47-108">A Conferência na rede NÃO deve ser implantada com qualquer equipamento de telefonia na Índia.</span><span class="sxs-lookup"><span data-stu-id="b8a47-108">On-network Conferencing must NOT be deployed with any telephony equipment in India.</span></span>
  
## <a name="prerequisites"></a><span data-ttu-id="b8a47-109">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="b8a47-109">Prerequisites</span></span>

<span data-ttu-id="b8a47-110">Antes de configurar a Conferência na rede, certifique-se de que sua organização atenda aos seguintes pré-requisitos:</span><span class="sxs-lookup"><span data-stu-id="b8a47-110">Before configuring On-network Conferencing, make sure your organization meets the following prerequisites:</span></span> 

- <span data-ttu-id="b8a47-111">Certifique-se de que todos os usuários da sua organização que estão habilitados ou serão habilitados para Audioconferência estão usando Teams para todas as Reuniões.</span><span class="sxs-lookup"><span data-stu-id="b8a47-111">Ensure that all users in your organization who are enabled, or will be enabled, for Audio Conferencing are using Teams for all Meetings.</span></span> <span data-ttu-id="b8a47-112">O roteamento de chamadas de Audioconferência de entrada e saída por meio de Conferência na rede só é suportado para reuniões Teams de entrada.</span><span class="sxs-lookup"><span data-stu-id="b8a47-112">The routing of inbound and outbound Audio Conferencing calls through On-network Conferencing is only supported for Teams meetings.</span></span>

- <span data-ttu-id="b8a47-113">Atribua licenças de Audioconferência a todos os usuários que usarão Conferência na rede.</span><span class="sxs-lookup"><span data-stu-id="b8a47-113">Assign Audio Conferencing licenses to all users who will be using On-network Conferencing.</span></span>

- <span data-ttu-id="b8a47-114">Configurar o serviço de Audioconferência.</span><span class="sxs-lookup"><span data-stu-id="b8a47-114">Set up the Audio Conferencing service.</span></span> <span data-ttu-id="b8a47-115">Para obter informações adicionais, [consulte Configurar Audioconferência para Microsoft Teams](set-up-audio-conferencing-in-teams.md).</span><span class="sxs-lookup"><span data-stu-id="b8a47-115">For additional information, see [Set up Audio Conferencing for Microsoft Teams](set-up-audio-conferencing-in-teams.md).</span></span>

- <span data-ttu-id="b8a47-116">Configurar o Controlador de Borda de Sessão (SBC) para Roteamento Direto.</span><span class="sxs-lookup"><span data-stu-id="b8a47-116">Set up your Session Border Controller (SBC) for Direct Routing.</span></span> <span data-ttu-id="b8a47-117">Para obter informações adicionais, consulte [Plan Direct Routing](direct-routing-plan.md) and Configure Direct [Routing](direct-routing-configure.md).</span><span class="sxs-lookup"><span data-stu-id="b8a47-117">For additional information, see [Plan Direct Routing](direct-routing-plan.md) and [Configure Direct Routing](direct-routing-configure.md).</span></span> 

  <span data-ttu-id="b8a47-118">Se você estiver configurando o Roteamento Direto somente para fins de Audioconferência, será necessário concluir apenas a "Etapa 1: Conexão seu SBC" para Conferência na rede.</span><span class="sxs-lookup"><span data-stu-id="b8a47-118">If you are setting up Direct Routing only for the purposes of Audio Conferencing, then you need only complete “Step 1: Connect your SBC” for On-network Conferencing.</span></span>
  
## <a name="enable-the-routing-of-dial-in-calls-to-microsoft-audio-conferencing-through-direct-routing"></a><span data-ttu-id="b8a47-119">Habilitar o roteamento de chamadas discar para a Audioconferência da Microsoft por meio do Roteamento Direto</span><span class="sxs-lookup"><span data-stu-id="b8a47-119">Enable the routing of dial-in calls to Microsoft Audio Conferencing through Direct Routing</span></span> 

<span data-ttu-id="b8a47-120">Para rotear chamadas discadas feitas por seus usuários locais para o serviço de Audioconferência por meio de Roteamento Direto, você precisa configurar regras de roteamento apropriadas para seus SBCs e pbxs (pbxs) de filial Exchange privada.</span><span class="sxs-lookup"><span data-stu-id="b8a47-120">To route dial-in calls made by your on-premises users to the Audio Conferencing service through Direct Routing, you need to configure appropriate routing rules for your SBCs and Private Branch Exchange(s) (PBXs).</span></span>

<span data-ttu-id="b8a47-121">Você precisa configurar o equipamento de telefonia de seus sites para rotear chamadas para qualquer número de serviço da ponte de conferência da sua organização por meio de um tronco de Roteamento Direto.</span><span class="sxs-lookup"><span data-stu-id="b8a47-121">You need to configure the telephony equipment of your sites to route calls to any service number of the conference bridge of your organization through a Direct Routing trunk.</span></span>

<span data-ttu-id="b8a47-122">Você pode encontrar os números de serviço no centro de administração Teams **em Pontes** de Conferência de Reuniões -> ou usando o cmdlet do Skype for Business Online PowerShell Get-CsOnlineDialInConferencingBridge.</span><span class="sxs-lookup"><span data-stu-id="b8a47-122">You can find the service numbers in Teams admin center under **Meetings -> Conferencing Bridges** or by using the Skype for Business Online PowerShell cmdlet Get-CsOnlineDialInConferencingBridge.</span></span> <span data-ttu-id="b8a47-123">Para obter informações adicionais, consulte uma lista de números de [Audioconferência em Microsoft Teams](see-a-list-of-audio-conferencing-numbers-in-teams.md).</span><span class="sxs-lookup"><span data-stu-id="b8a47-123">For additional information, see a list of [Audio Conferencing numbers in Microsoft Teams](see-a-list-of-audio-conferencing-numbers-in-teams.md).</span></span>

> [!NOTE]
> <span data-ttu-id="b8a47-124">Esse recurso não está disponível para usuários com a licença de Audioconferência paga por minuto.</span><span class="sxs-lookup"><span data-stu-id="b8a47-124">This feature is not available to users with the pay-per-minute Audio Conferencing license.</span></span>

## <a name="enable-the-routing-of-teams-meeting-dial-out-calls-through-direct-routing"></a><span data-ttu-id="b8a47-125">Habilitar o roteamento Teams chamadas discagem de reunião por meio do Roteamento Direto</span><span class="sxs-lookup"><span data-stu-id="b8a47-125">Enable the routing of Teams meeting dial-out calls through Direct Routing</span></span>

<span data-ttu-id="b8a47-126">Teams chamadas de discagem de reunião são iniciadas de dentro de uma reunião em sua organização para números PSTN, incluindo chamadas de chamada e chamadas para trazer novos participantes para uma reunião.</span><span class="sxs-lookup"><span data-stu-id="b8a47-126">Teams meeting dial-out calls are initiated from within a meeting in your organization to PSTN numbers, including call-me-at calls and calls to bring new participants to a meeting.</span></span> 

<span data-ttu-id="b8a47-127">Para habilitar Teams roteamento de discagem de reunião por meio do Roteamento Direto para usuários na rede, você precisa criar e atribuir uma política de roteamento de Audioconferência chamada "OnlineAudioConferencingRoutingPolicy".</span><span class="sxs-lookup"><span data-stu-id="b8a47-127">To enable Teams meeting dial-out routing through Direct Routing to on-network users, you need to create and assign an Audio Conferencing routing policy called “OnlineAudioConferencingRoutingPolicy”.</span></span> 

<span data-ttu-id="b8a47-128">A política OnlineAudioConferencingRoutingPolicy é equivalente à CsOnlineVoiceRoutingPolicy para chamadas PSTN 1:1 via Roteamento Direto.</span><span class="sxs-lookup"><span data-stu-id="b8a47-128">The OnlineAudioConferencingRoutingPolicy policy is equivalent to the CsOnlineVoiceRoutingPolicy for 1:1 PSTN calls via Direct Routing.</span></span> <span data-ttu-id="b8a47-129">A política OnlineAudioConferencingRoutingPolicy pode ser gerenciada usando os seguintes cmdlets:</span><span class="sxs-lookup"><span data-stu-id="b8a47-129">The OnlineAudioConferencingRoutingPolicy policy can be managed by using the following cmdlets:</span></span>

-   <span data-ttu-id="b8a47-130">New-CsOnlineAudioConferencingRoutingPolicy</span><span class="sxs-lookup"><span data-stu-id="b8a47-130">New-CsOnlineAudioConferencingRoutingPolicy</span></span>
- <span data-ttu-id="b8a47-131">Set-CsOnlineAudioConferencingRoutingPolicy</span><span class="sxs-lookup"><span data-stu-id="b8a47-131">Set-CsOnlineAudioConferencingRoutingPolicy</span></span>
- <span data-ttu-id="b8a47-132">Get-CsOnlineAudioConferencingRoutingPolicy</span><span class="sxs-lookup"><span data-stu-id="b8a47-132">Get-CsOnlineAudioConferencingRoutingPolicy</span></span>
- <span data-ttu-id="b8a47-133">Grant-CsOnlineAudioConferencingRoutingPolicy</span><span class="sxs-lookup"><span data-stu-id="b8a47-133">Grant-CsOnlineAudioConferencingRoutingPolicy</span></span>
- <span data-ttu-id="b8a47-134">Remove-CsOnlineAudioConferencingRoutingPolicy</span><span class="sxs-lookup"><span data-stu-id="b8a47-134">Remove-CsOnlineAudioConferencingRoutingPolicy</span></span>

<span data-ttu-id="b8a47-135">Para obter mais informações sobre roteamento para Roteamento Direto, consulte [Configure voice routing for Direct Routing](direct-routing-voice-routing.md).</span><span class="sxs-lookup"><span data-stu-id="b8a47-135">For more information about routing for Direct Routing, see [Configure voice routing for Direct Routing](direct-routing-voice-routing.md).</span></span>


<span data-ttu-id="b8a47-136">Para habilitar o roteamento de chamadas discagem de reunião por meio do Roteamento Direto, você precisa:</span><span class="sxs-lookup"><span data-stu-id="b8a47-136">To enable the routing of meeting dial-out calls through Direct Routing, you need to:</span></span> 

- <span data-ttu-id="b8a47-137">Configurar políticas de roteamento de audioconferência</span><span class="sxs-lookup"><span data-stu-id="b8a47-137">Configure Audio Conferencing routing policies</span></span>
- <span data-ttu-id="b8a47-138">Configurar o roteamento no equipamento de telefonia da sua organização</span><span class="sxs-lookup"><span data-stu-id="b8a47-138">Configure the routing on the telephony equipment of your organization</span></span>
- <span data-ttu-id="b8a47-139">(Opcional) Configurar um plano de discagem</span><span class="sxs-lookup"><span data-stu-id="b8a47-139">(Optional) Configure a dial plan</span></span>

<span data-ttu-id="b8a47-140">Chamadas discar de Teams reuniões vêm do número de serviço padrão na ponte de conferência.</span><span class="sxs-lookup"><span data-stu-id="b8a47-140">Dial-out calls from Teams meetings are coming from the default service number on the conference bridge.</span></span> <span data-ttu-id="b8a47-141">Para obter informações adicionais sobre o número de serviço padrão da ponte de Audioconferência, consulte Alterar os números de telefone em sua ponte [de Audioconferência](change-the-phone-numbers-on-your-audio-conferencing-bridge.md).</span><span class="sxs-lookup"><span data-stu-id="b8a47-141">For additional information on the default service number of your Audio Conferencing bridge, see [Change the phone numbers on your Audio Conferencing bridge](change-the-phone-numbers-on-your-audio-conferencing-bridge.md).</span></span>

### <a name="configure-audio-conferencing-routing-policies"></a><span data-ttu-id="b8a47-142">Configurar políticas de roteamento de audioconferência</span><span class="sxs-lookup"><span data-stu-id="b8a47-142">Configure Audio Conferencing routing policies</span></span>

<span data-ttu-id="b8a47-143">A política de roteamento de Audioconferência OnlineAudioConferencingRoutingPolicy determina quais chamadas de discagem de reunião são roteados para troncos de Roteamento Direto.</span><span class="sxs-lookup"><span data-stu-id="b8a47-143">The Audio Conferencing routing policy OnlineAudioConferencingRoutingPolicy determines which meeting dial-out calls are routed to Direct Routing trunks.</span></span> <span data-ttu-id="b8a47-144">Se você estiver familiarizado com a política CsOnlineVoiceRoutingPolicy, essa política funcionará de maneira muito semelhante.</span><span class="sxs-lookup"><span data-stu-id="b8a47-144">If you are familiar with the CsOnlineVoiceRoutingPolicy policy, this policy works in a very similar way.</span></span>

<span data-ttu-id="b8a47-145">As etapas a seguir são necessárias para configurar políticas de roteamento de Audioconferência:</span><span class="sxs-lookup"><span data-stu-id="b8a47-145">The following steps are needed to set up Audio Conferencing routing policies:</span></span>
1.  <span data-ttu-id="b8a47-146">Criar usos PSTN</span><span class="sxs-lookup"><span data-stu-id="b8a47-146">Create PSTN usages</span></span>
2.  <span data-ttu-id="b8a47-147">Configurar rotas de voz</span><span class="sxs-lookup"><span data-stu-id="b8a47-147">Configure voice routes</span></span>
3.  <span data-ttu-id="b8a47-148">Criar políticas de roteamento de voz de audioconferência</span><span class="sxs-lookup"><span data-stu-id="b8a47-148">Create Audio Conferencing voice routing policies</span></span>
4.  <span data-ttu-id="b8a47-149">Atribuir uma política aos usuários</span><span class="sxs-lookup"><span data-stu-id="b8a47-149">Assign a policy to your users</span></span>


#### <a name="create-pstn-usages"></a><span data-ttu-id="b8a47-150">Criar usos PSTN</span><span class="sxs-lookup"><span data-stu-id="b8a47-150">Create PSTN usages</span></span>

<span data-ttu-id="b8a47-151">Os usos de PSTN são coleções de rotas de voz.</span><span class="sxs-lookup"><span data-stu-id="b8a47-151">PSTN usages are collections of voice routes.</span></span> <span data-ttu-id="b8a47-152">Quando uma chamada discada é iniciada a partir da reunião de um determinado organizador, as rotas de voz serão usadas para determinar o caminho de roteamento da chamada com base nos usos PSTN associados ao usuário por meio da política de roteamento de voz do usuário.</span><span class="sxs-lookup"><span data-stu-id="b8a47-152">When a dial-out call is initiated from the meeting of a given organizer, voice routes will be used to determine the routing path of the call based on the PSTN usages that are associated to the user via the user’s voice routing policy.</span></span>

<span data-ttu-id="b8a47-153">Você pode criar um uso PSTN usando o cmdlet "Set-CsOnlinePstnUsage".</span><span class="sxs-lookup"><span data-stu-id="b8a47-153">You can create a PSTN usage by using the “Set-CsOnlinePstnUsage” cmdlet.</span></span> <span data-ttu-id="b8a47-154">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="b8a47-154">For Example:</span></span>

```powershell
Set-CsOnlinePstnUsage -Identity Global -Usage @{Add="US and Canada"}
```

#### <a name="configure-voice-routes"></a><span data-ttu-id="b8a47-155">Configurar rotas de voz</span><span class="sxs-lookup"><span data-stu-id="b8a47-155">Configure voice routes</span></span>

<span data-ttu-id="b8a47-156">As rotas de voz determinam o gateway PSTN que deve ser usado para rotear uma chamada com base no número de telefone discado de uma reunião Teams.</span><span class="sxs-lookup"><span data-stu-id="b8a47-156">Voice routes determine the PSTN gateway that should be used to route a call based on the phone number that is dialed from a Teams meeting.</span></span> <span data-ttu-id="b8a47-157">As rotas de voz determinam o gateway PSTN que deve ser usado para rotear uma determinada chamada, correspondendo ao número de telefone discado de uma reunião Teams com um padrão regex.</span><span class="sxs-lookup"><span data-stu-id="b8a47-157">Voice routes determine the PSTN gateway that should be used to route a given call by matching the phone number dialed from a Teams meeting with a regex pattern.</span></span> <span data-ttu-id="b8a47-158">Ao criar uma rota de voz, a rota deve estar associada a um ou mais usos de PSTN.</span><span class="sxs-lookup"><span data-stu-id="b8a47-158">When creating a voice route, the route must be associated to one or more PSTN usages.</span></span>

<span data-ttu-id="b8a47-159">Você pode criar uma rota de voz e definir o regex e os gateways a serem associados à rota de voz usando o cmdlet "New-CsOnlineVoiceRoute".</span><span class="sxs-lookup"><span data-stu-id="b8a47-159">You can create a voice route and define the regex and gateways to be associated with the voice route by using the “New-CsOnlineVoiceRoute” cmdlet.</span></span> <span data-ttu-id="b8a47-160">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="b8a47-160">For Example:</span></span>

```powershell
New-CsOnlineVoiceRoute -Identity "Redmond 1" -NumberPattern "^\+1(425|206)(\d{7})$" -OnlinePstnGatewayList sbc1.contoso.biz, sbc2.contoso.biz -Priority 1 -OnlinePstnUsages "US and Canada"
```

#### <a name="create-audio-conferencing-voice-routing-policies"></a><span data-ttu-id="b8a47-161">Criar políticas de roteamento de voz de audioconferência</span><span class="sxs-lookup"><span data-stu-id="b8a47-161">Create Audio Conferencing voice routing policies</span></span>

<span data-ttu-id="b8a47-162">As políticas de roteamento de voz de audioconferência determinam as possíveis rotas que podem ser usadas para rotear uma chamada proveniente das reuniões de um organizador com base no número de telefone de destino da chamada discada da reunião.</span><span class="sxs-lookup"><span data-stu-id="b8a47-162">Audio Conferencing voice routing policies determine the possible routes that can be used to route a call originating from the meetings of an organizer based on the target phone number of the meeting dial-out call.</span></span> <span data-ttu-id="b8a47-163">As políticas de roteamento de voz de audioconferência estão associadas a um ou mais usos de PSTN, que, por sua vez, determinam as possíveis rotas que serão tentadas para serem usadas para as chamadas de discagem de reunião dos organizadores associados à política.</span><span class="sxs-lookup"><span data-stu-id="b8a47-163">Audio Conferencing voice routing policies are associated to one or more PSTN usages, which in turn, determine the possible routes that will be attempted to be used for the meeting dial-out calls of the organizers associated to the policy.</span></span>

<span data-ttu-id="b8a47-164">Você pode criar uma política de roteamento de voz de Audioconferência usando o cmdlet "New-CsOnlineAudioConferencingRoutingPolicy".</span><span class="sxs-lookup"><span data-stu-id="b8a47-164">You can create an Audio Conferencing voice routing policy by using the “New- CsOnlineAudioConferencingRoutingPolicy” cmdlet.</span></span> <span data-ttu-id="b8a47-165">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="b8a47-165">For Example:</span></span>

```powershell
New-CsOnlineAudioConferencingRoutingPolicy "Policy 1" -OnlinePstnUsages "US and Canada"
```

<span data-ttu-id="b8a47-166">Depois que a política é atribuída a um usuário e quando uma chamada discada de reunião é iniciada em uma das reuniões do usuário, as rotas de voz nos usos PSTN associados ao organizador por meio da política de roteamento de voz do usuário serão avaliadas.</span><span class="sxs-lookup"><span data-stu-id="b8a47-166">After the policy is assigned to a user, and when a meeting dial-out call is initiated from one of the user's meetings, the voice routes in the PSTN usages that are associated to the organizer through the user's voice routing policy will be evaluated.</span></span> <span data-ttu-id="b8a47-167">Se o destino da chamada discada da reunião corresponde a um regex em uma das rotas de voz associadas ao organizador, a chamada discada da reunião será roteada para o gateway PSTN definido na rota de voz.</span><span class="sxs-lookup"><span data-stu-id="b8a47-167">If the meeting dial-out call destination matches a regex in one of the voice routes that are associated to the organizer, the meeting dial-out call will be routed to the PSTN gateway defined in the voice route.</span></span> <span data-ttu-id="b8a47-168">Se o destino da chamada discada da reunião não corresponder a nenhuma das rotas de voz associadas ao organizador, a chamada discada da reunião será roteada pela Microsoft.</span><span class="sxs-lookup"><span data-stu-id="b8a47-168">If the meeting dial-out call destination does not match any of the voice routes associated to the organizer, the meeting dial-out call will be routed by Microsoft.</span></span>

#### <a name="assign-a-policy-to-your-users"></a><span data-ttu-id="b8a47-169">Atribuir uma política aos usuários</span><span class="sxs-lookup"><span data-stu-id="b8a47-169">Assign a policy to your users</span></span>

<span data-ttu-id="b8a47-170">Depois que as políticas de roteamento de Audioconferência são definidas, agora você pode atribuí-las aos usuários.</span><span class="sxs-lookup"><span data-stu-id="b8a47-170">After the Audio Conferencing routing policies are defined, you can now assign them to users.</span></span> <span data-ttu-id="b8a47-171">Depois que as políticas são atribuídas a elas, as chamadas discadas da reunião serão avaliadas em relação a ela para determinar o caminho de roteamento.</span><span class="sxs-lookup"><span data-stu-id="b8a47-171">After policies are assigned to them, the meeting dial-out calls will be evaluated against it to determine their routing path.</span></span> <span data-ttu-id="b8a47-172">As políticas de roteamento de audioconferência sempre são avaliadas com base no organizador da reunião, independentemente do usuário na reunião que inicia uma chamada discada de reunião.</span><span class="sxs-lookup"><span data-stu-id="b8a47-172">Audio Conferencing routing policies are always evaluated based on the organizer of the meeting, independently from the user in the meeting that initiates a meeting dial-out call.</span></span>

<span data-ttu-id="b8a47-173">Você pode atribuir uma política de roteamento de voz de Audioconferência a um usuário usando o cmdlet "Grant-CsOnlineAudioConferencingRoutingPolicy".</span><span class="sxs-lookup"><span data-stu-id="b8a47-173">You can assign an Audio Conferencing voice routing policy to a user by using the “Grant-CsOnlineAudioConferencingRoutingPolicy” cmdlet.</span></span> <span data-ttu-id="b8a47-174">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="b8a47-174">For example:</span></span>

```powershell
Grant-CsOnlineAudioConferencingRoutingPolicy -Identity "<User Identity>" -PolicyName "Policy 1”
```


### <a name="configure-routing-on-the-telephony-equipment-of-your-organization"></a><span data-ttu-id="b8a47-175">Configurar o roteamento no equipamento de telefonia da sua organização</span><span class="sxs-lookup"><span data-stu-id="b8a47-175">Configure routing on the telephony equipment of your organization</span></span>

<span data-ttu-id="b8a47-176">No equipamento de telefonia da sua organização, você precisa garantir que as chamadas de discagem de reunião roteados por Roteamento Direto sejam roteados para o destino pretendido na rede.</span><span class="sxs-lookup"><span data-stu-id="b8a47-176">On the telephony equipment of your organization, you need to ensure that the meeting dial-out calls routed through Direct Routing are routed to the intended on-network destination.</span></span>


### <a name="optional-configure-a-dial-plan"></a><span data-ttu-id="b8a47-177">(Opcional) Configurar um plano de discagem</span><span class="sxs-lookup"><span data-stu-id="b8a47-177">(Optional) Configure a dial plan</span></span>

<span data-ttu-id="b8a47-178">Um plano de discagem é um conjunto de regras de normalização que convertem números de telefone discados por um usuário individual em um formato alternativo (normalmente E.164) para fins de autorização de chamada e roteamento de chamadas.</span><span class="sxs-lookup"><span data-stu-id="b8a47-178">A dial plan is a set of normalization rules that translate dialed phone numbers by an individual user into an alternate format (typically E.164) for purposes of call authorization and call routing.</span></span>

<span data-ttu-id="b8a47-179">Por padrão, Teams usuários podem discar para números PSTN no formato E.164, ou seja, + \<country code\> \<number\> .</span><span class="sxs-lookup"><span data-stu-id="b8a47-179">By default, Teams users can dial-out to PSTN numbers in E.164 format, that is, +\<country code\>\<number\>.</span></span> <span data-ttu-id="b8a47-180">No entanto, os planos de discagem podem ser usados para permitir que os usuários disquem números de telefone em outros formatos, por exemplo, extensões de 4 dígitos.</span><span class="sxs-lookup"><span data-stu-id="b8a47-180">However, dial plans can be used to allow users to dial phone numbers in other formats, for instance 4-digit extensions.</span></span>

<span data-ttu-id="b8a47-181">Se quiser habilitar a discagem baseada em extensão por meio de conferência na rede, você pode configurar planos de discagem para corresponder o padrão de discagem de extensão aos intervalos de número de telefone do número de telefone da sua organização.</span><span class="sxs-lookup"><span data-stu-id="b8a47-181">If you would like to enable extension-based dialing through On-network conferencing, you can set up dial plans to match the extension dialing pattern to the phone number ranges of the phone number of your organization.</span></span> <span data-ttu-id="b8a47-182">Para configurar planos de discagem, consulte [Create and manage dial plans](create-and-manage-dial-plans.md).</span><span class="sxs-lookup"><span data-stu-id="b8a47-182">To set up dial plans, see [Create and manage dial plans](create-and-manage-dial-plans.md).</span></span>

## <a name="related-topics"></a><span data-ttu-id="b8a47-183">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="b8a47-183">Related topics</span></span>


