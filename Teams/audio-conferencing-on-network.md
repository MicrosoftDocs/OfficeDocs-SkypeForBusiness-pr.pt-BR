---
title: Conferência na rede para videoconferência
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
localization_priority: Normal
f1.keywords:
- NOCSH
ms.custom:
- Audio Conferencing
description: A seguir, a descrição da funcionalidade de visualização aberta para videoconferência na rede.
ms.openlocfilehash: 38b8be382ccd1b80002688cdb7fce9aa166efc2c
ms.sourcegitcommit: f9daef3213a305676127cf5140af907e3b96d046
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/07/2020
ms.locfileid: "48369175"
---
# <a name="open-preview-of-on-network-conferencing-for-audio-conferencing"></a><span data-ttu-id="a8710-103">Abrir a visualização de conferências na rede para videoconferências</span><span class="sxs-lookup"><span data-stu-id="a8710-103">Open Preview of On-network Conferencing for Audio Conferencing</span></span>

<span data-ttu-id="a8710-104">A visualização aberta de conferências na rede está disponível para todos os clientes.</span><span class="sxs-lookup"><span data-stu-id="a8710-104">The Open Preview of On-network Conferencing is available to all customers.</span></span> <span data-ttu-id="a8710-105">A conferência on-Network permite que as organizações enviem chamadas de videoconferências de entrada e saída para números de discagem da Microsoft por meio do roteamento direto.</span><span class="sxs-lookup"><span data-stu-id="a8710-105">On-network Conferencing allows organizations to send inbound and outbound Audio Conferencing calls to Microsoft dial-in numbers through Direct Routing.</span></span> <span data-ttu-id="a8710-106">Essa funcionalidade não se destina a estender o suporte de videoconferência a outros números de discagem.</span><span class="sxs-lookup"><span data-stu-id="a8710-106">This capability is not intended to extend the support of Audio Conferencing to third party dial-in numbers.</span></span> <span data-ttu-id="a8710-107">A conferência pela rede não é suportada se é usada para rotear chamadas recebidas para o serviço de audioconferência por meio de números de telefone de discagem de terceiros.</span><span class="sxs-lookup"><span data-stu-id="a8710-107">On-network Conferencing is not supported if it is used to route inbound calls to the Audio Conferencing service through third party dial-in phone numbers.</span></span>

<span data-ttu-id="a8710-108">Este artigo descreve os pré-requisitos e as etapas de configuração necessárias para habilitar a conferência na rede de sua organização.</span><span class="sxs-lookup"><span data-stu-id="a8710-108">This article describes the prerequisites and configuration steps required to enable On-network Conferencing for your organization.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="a8710-109">A conferência na rede não deve ser implantada com nenhum equipamento de telefonia na Índia.</span><span class="sxs-lookup"><span data-stu-id="a8710-109">On-network Conferencing must NOT be deployed with any telephony equipment in India.</span></span>
  
## <a name="prerequisites"></a><span data-ttu-id="a8710-110">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="a8710-110">Prerequisites</span></span>

<span data-ttu-id="a8710-111">Antes de configurar a conferência na rede, certifique-se de que sua organização atenda aos seguintes pré-requisitos:</span><span class="sxs-lookup"><span data-stu-id="a8710-111">Before configuring On-network Conferencing, make sure your organization meets the following prerequisites:</span></span> 

- <span data-ttu-id="a8710-112">Certifique-se de que todos os usuários de sua organização estejam habilitados, ou serão habilitados, para videoconferências no modo somente Teams.</span><span class="sxs-lookup"><span data-stu-id="a8710-112">Ensure that all users in your organization who are enabled, or will be enabled, for Audio Conferencing are in Teams Only mode.</span></span> <span data-ttu-id="a8710-113">O roteamento de chamadas de videoconferência de entrada e saída para a conferência pela rede só tem suporte em reuniões de equipe.</span><span class="sxs-lookup"><span data-stu-id="a8710-113">The routing of inbound and outbound Audio Conferencing calls through On-network Conferencing is only supported for Teams meetings.</span></span>

- <span data-ttu-id="a8710-114">Atribua licenças de audioconferência a todos os usuários que usarão conferências na rede.</span><span class="sxs-lookup"><span data-stu-id="a8710-114">Assign Audio Conferencing licenses to all users who will be using On-network Conferencing.</span></span>

- <span data-ttu-id="a8710-115">Configurar o serviço de audioconferência.</span><span class="sxs-lookup"><span data-stu-id="a8710-115">Set up the Audio Conferencing service.</span></span> <span data-ttu-id="a8710-116">Para obter informações adicionais, consulte [Configurar a conferência de áudio para o Microsoft Teams](set-up-audio-conferencing-in-teams.md).</span><span class="sxs-lookup"><span data-stu-id="a8710-116">For additional information, see [Set up Audio Conferencing for Microsoft Teams](set-up-audio-conferencing-in-teams.md).</span></span>

- <span data-ttu-id="a8710-117">Configure o seu controlador de borda de sessão (SBC) para roteamento direto.</span><span class="sxs-lookup"><span data-stu-id="a8710-117">Set up your Session Border Controller (SBC) for Direct Routing.</span></span> <span data-ttu-id="a8710-118">Para obter informações adicionais, consulte [planejar o roteamento direto](direct-routing-plan.md) e [Configurar o roteamento direto](direct-routing-configure.md).</span><span class="sxs-lookup"><span data-stu-id="a8710-118">For additional information, see [Plan Direct Routing](direct-routing-plan.md) and [Configure Direct Routing](direct-routing-configure.md).</span></span> 

  <span data-ttu-id="a8710-119">Se você estiver configurando o roteamento direto somente para fins de videoconferência, será necessário concluir "etapa 1: conectar seu SBC" para conferência na rede.</span><span class="sxs-lookup"><span data-stu-id="a8710-119">If you are setting up Direct Routing only for the purposes of Audio Conferencing, then you need only complete “Step 1: Connect your SBC” for On-network Conferencing.</span></span>
  
## <a name="enable-the-routing-of-dial-in-calls-to-microsoft-audio-conferencing-through-direct-routing"></a><span data-ttu-id="a8710-120">Habilitar o roteamento de chamadas discadas para a conferência de áudio da Microsoft por meio do roteamento direto</span><span class="sxs-lookup"><span data-stu-id="a8710-120">Enable the routing of dial-in calls to Microsoft Audio Conferencing through Direct Routing</span></span> 

<span data-ttu-id="a8710-121">Para direcionar as chamadas de discagem feitas por seus usuários locais para o serviço de audioconferência por meio do roteamento direto, você precisa configurar as regras de roteamento adequadas para o SBCs e os Exchange (s) filiais (s).</span><span class="sxs-lookup"><span data-stu-id="a8710-121">To route dial-in calls made by your on-premises users to the Audio Conferencing service through Direct Routing, you need to configure appropriate routing rules for your SBCs and Private Branch Exchange(s) (PBXs).</span></span>

<span data-ttu-id="a8710-122">Você precisa configurar o equipamento de telefonia dos seus sites para direcionar chamadas para qualquer número de serviço da ponte de conferência da sua organização por meio de um tronco de roteamento direto.</span><span class="sxs-lookup"><span data-stu-id="a8710-122">You need to configure the telephony equipment of your sites to route calls to any service number of the conference bridge of your organization through a Direct Routing trunk.</span></span>

<span data-ttu-id="a8710-123">Você pode encontrar os números de serviço no centro de administração do teams em **reuniões-> pontes de conferência** ou usando o cmdlet do PowerShell Get-CsOnlineDialInConferencingBridge do Skype for Business online.</span><span class="sxs-lookup"><span data-stu-id="a8710-123">You can find the service numbers in Teams admin center under **Meetings -> Conferencing Bridges** or by using the Skype for Business Online PowerShell cmdlet Get-CsOnlineDialInConferencingBridge.</span></span> <span data-ttu-id="a8710-124">Para obter mais informações, consulte uma lista de [números de audioconferência no Microsoft Teams](see-a-list-of-audio-conferencing-numbers-in-teams.md).</span><span class="sxs-lookup"><span data-stu-id="a8710-124">For additional information, see a list of [Audio Conferencing numbers in Microsoft Teams](see-a-list-of-audio-conferencing-numbers-in-teams.md).</span></span>

> [!NOTE]
> <span data-ttu-id="a8710-125">Este recurso não está disponível para os usuários com a licença de conferência de áudio de pagamento por minuto.</span><span class="sxs-lookup"><span data-stu-id="a8710-125">This feature is not available to users with the pay-per-minute Audio Conferencing license.</span></span>

## <a name="enable-the-routing-of-teams-meeting-dial-out-calls-through-direct-routing"></a><span data-ttu-id="a8710-126">Habilitar o roteamento de chamadas discadas da reunião do teams por meio do direcionamento direto</span><span class="sxs-lookup"><span data-stu-id="a8710-126">Enable the routing of Teams meeting dial-out calls through Direct Routing</span></span>

<span data-ttu-id="a8710-127">As chamadas de reunião discada do teams são iniciadas dentro de uma reunião da sua organização até números PSTN, incluindo chamadas para mim e chamadas para trazer novos participantes para uma reunião.</span><span class="sxs-lookup"><span data-stu-id="a8710-127">Teams meeting dial-out calls are initiated from within a meeting in your organization to PSTN numbers, including call-me-at calls and calls to bring new participants to a meeting.</span></span> 

<span data-ttu-id="a8710-128">Para habilitar o roteamento de discagem externa da reunião do teams por meio do roteamento direto, você precisa criar e atribuir uma política de roteamento de audioconferência chamada "OnlineAudioConferencingRoutingPolicy".</span><span class="sxs-lookup"><span data-stu-id="a8710-128">To enable Teams meeting dial-out routing through Direct Routing, you need to create and assign an Audio Conferencing routing policy called “OnlineAudioConferencingRoutingPolicy”.</span></span> 

<span data-ttu-id="a8710-129">A política OnlineAudioConferencingRoutingPolicy é equivalente à CsOnlineVoiceRoutingPolicy de chamadas PSTN do 1:1 via roteamento direto.</span><span class="sxs-lookup"><span data-stu-id="a8710-129">The OnlineAudioConferencingRoutingPolicy policy is equivalent to the CsOnlineVoiceRoutingPolicy for 1:1 PSTN calls via Direct Routing.</span></span> <span data-ttu-id="a8710-130">A política OnlineAudioConferencingRoutingPolicy pode ser gerenciada usando os seguintes cmdlets:</span><span class="sxs-lookup"><span data-stu-id="a8710-130">The OnlineAudioConferencingRoutingPolicy policy can be managed by using the following cmdlets:</span></span>

-   <span data-ttu-id="a8710-131">New-CsOnlineAudioConferencingRoutingPolicy</span><span class="sxs-lookup"><span data-stu-id="a8710-131">New-CsOnlineAudioConferencingRoutingPolicy</span></span>
- <span data-ttu-id="a8710-132">Set-CsOnlineAudioConferencingRoutingPolicy</span><span class="sxs-lookup"><span data-stu-id="a8710-132">Set-CsOnlineAudioConferencingRoutingPolicy</span></span>
- <span data-ttu-id="a8710-133">Get-CsOnlineAudioConferencingRoutingPolicy</span><span class="sxs-lookup"><span data-stu-id="a8710-133">Get-CsOnlineAudioConferencingRoutingPolicy</span></span>
- <span data-ttu-id="a8710-134">Grant CsOnlineAudioConferencingRoutingPolicy</span><span class="sxs-lookup"><span data-stu-id="a8710-134">Grant-CsOnlineAudioConferencingRoutingPolicy</span></span>
- <span data-ttu-id="a8710-135">Remove-CsOnlineAudioConferencingRoutingPolicy</span><span class="sxs-lookup"><span data-stu-id="a8710-135">Remove-CsOnlineAudioConferencingRoutingPolicy</span></span>

<span data-ttu-id="a8710-136">Para obter mais informações sobre roteamento para roteamento direto, consulte [Configurar roteamento de voz para roteamento direto](direct-routing-voice-routing.md).</span><span class="sxs-lookup"><span data-stu-id="a8710-136">For more information about routing for Direct Routing, see [Configure voice routing for Direct Routing](direct-routing-voice-routing.md).</span></span>


<span data-ttu-id="a8710-137">Para habilitar o roteamento de chamadas discadas de uma reunião por meio do direcionamento direto, você precisa:</span><span class="sxs-lookup"><span data-stu-id="a8710-137">To enable the routing of meeting dial-out calls through Direct Routing, you need to:</span></span> 

- <span data-ttu-id="a8710-138">Configurar as políticas de roteamento de audioconferência</span><span class="sxs-lookup"><span data-stu-id="a8710-138">Configure Audio Conferencing routing policies</span></span>
- <span data-ttu-id="a8710-139">Configurar o roteamento no equipamento de telefonia da sua organização</span><span class="sxs-lookup"><span data-stu-id="a8710-139">Configure the routing on the telephony equipment of your organization</span></span>
- <span data-ttu-id="a8710-140">Adicionais Configurar um plano de discagem</span><span class="sxs-lookup"><span data-stu-id="a8710-140">(Optional) Configure a dial plan</span></span>

<span data-ttu-id="a8710-141">Chamadas discada de reuniões do teams estão chegando do número de serviço padrão na ponte de conferência.</span><span class="sxs-lookup"><span data-stu-id="a8710-141">Dial-out calls from Teams meetings are coming from the default service number on the conference bridge.</span></span> <span data-ttu-id="a8710-142">Para obter informações adicionais sobre o número de serviço padrão da ponte de videoconferência, consulte [alterar os números de telefone na sua ponte de videoconferência](change-the-phone-numbers-on-your-audio-conferencing-bridge.md).</span><span class="sxs-lookup"><span data-stu-id="a8710-142">For additional information on the default service number of your Audio Conferencing bridge, see [Change the phone numbers on your Audio Conferencing bridge](change-the-phone-numbers-on-your-audio-conferencing-bridge.md).</span></span>

### <a name="configure-audio-conferencing-routing-policies"></a><span data-ttu-id="a8710-143">Configurar as políticas de roteamento de audioconferência</span><span class="sxs-lookup"><span data-stu-id="a8710-143">Configure Audio Conferencing routing policies</span></span>

<span data-ttu-id="a8710-144">A política de roteamento de audioconferência OnlineAudioConferencingRoutingPolicy determina quais chamadas discadas de reunião são roteadas para troncos de roteamento direto.</span><span class="sxs-lookup"><span data-stu-id="a8710-144">The Audio Conferencing routing policy OnlineAudioConferencingRoutingPolicy determines which meeting dial-out calls are routed to Direct Routing trunks.</span></span> <span data-ttu-id="a8710-145">Se você estiver familiarizado com a política CsOnlineVoiceRoutingPolicy, essa política funciona de forma muito semelhante.</span><span class="sxs-lookup"><span data-stu-id="a8710-145">If you are familiar with the CsOnlineVoiceRoutingPolicy policy, this policy works in a very similar way.</span></span>

<span data-ttu-id="a8710-146">As etapas a seguir são necessárias para configurar as políticas de roteamento de audioconferência:</span><span class="sxs-lookup"><span data-stu-id="a8710-146">The following steps are needed to set up Audio Conferencing routing policies:</span></span>
1.  <span data-ttu-id="a8710-147">Criar usos de PSTN</span><span class="sxs-lookup"><span data-stu-id="a8710-147">Create PSTN usages</span></span>
2.  <span data-ttu-id="a8710-148">Configurar rotas de voz</span><span class="sxs-lookup"><span data-stu-id="a8710-148">Configure voice routes</span></span>
3.  <span data-ttu-id="a8710-149">Criar políticas de roteamento de voz da conferência de áudio</span><span class="sxs-lookup"><span data-stu-id="a8710-149">Create Audio Conferencing voice routing policies</span></span>
4.  <span data-ttu-id="a8710-150">Atribuir uma política a seus usuários</span><span class="sxs-lookup"><span data-stu-id="a8710-150">Assign a policy to your users</span></span>


#### <a name="create-pstn-usages"></a><span data-ttu-id="a8710-151">Criar usos de PSTN</span><span class="sxs-lookup"><span data-stu-id="a8710-151">Create PSTN usages</span></span>

<span data-ttu-id="a8710-152">Os usos de PSTN são coleções de rotas de voz.</span><span class="sxs-lookup"><span data-stu-id="a8710-152">PSTN usages are collections of voice routes.</span></span> <span data-ttu-id="a8710-153">Quando uma chamada de discagem estiver iniciada da reunião de um determinado organizador, as rotas de voz serão usadas para determinar o caminho de roteamento da chamada com base nos usos de PSTN associados ao usuário por meio da política de roteamento de voz do usuário.</span><span class="sxs-lookup"><span data-stu-id="a8710-153">When a dial-out call is initiated from the meeting of a given organizer, voice routes will be used to determine the routing path of the call based on the PSTN usages that are associated to the user via the user’s voice routing policy.</span></span>

<span data-ttu-id="a8710-154">Você pode criar um uso de PSTN usando o cmdlet "Set-CsOnlinePstnUsage".</span><span class="sxs-lookup"><span data-stu-id="a8710-154">You can create a PSTN usage by using the “Set-CsOnlinePstnUsage” cmdlet.</span></span> <span data-ttu-id="a8710-155">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="a8710-155">For Example:</span></span>

```
Set-CsOnlinePstnUsage -Identity Global -Usage @{Add="US and Canada"}
```

#### <a name="configure-voice-routes"></a><span data-ttu-id="a8710-156">Configurar rotas de voz</span><span class="sxs-lookup"><span data-stu-id="a8710-156">Configure voice routes</span></span>

<span data-ttu-id="a8710-157">As rotas de voz determinam o gateway PSTN que deve ser usado para direcionar uma chamada com base no número de telefone discado de uma reunião do teams.</span><span class="sxs-lookup"><span data-stu-id="a8710-157">Voice routes determine the PSTN gateway that should be used to route a call based on the phone number that is dialed from a Teams meeting.</span></span> <span data-ttu-id="a8710-158">As rotas de voz determinam o gateway PSTN que deve ser usado para direcionar uma determinada chamada combinando o número de telefone discado de uma reunião do teams com um padrão Regex.</span><span class="sxs-lookup"><span data-stu-id="a8710-158">Voice routes determine the PSTN gateway that should be used to route a given call by matching the phone number dialed from a Teams meeting with a regex pattern.</span></span> <span data-ttu-id="a8710-159">Durante a criação de uma rota de voz, a rota deve estar associada a um ou mais usos de PSTN.</span><span class="sxs-lookup"><span data-stu-id="a8710-159">When creating a voice route, the route must be associated to one or more PSTN usages.</span></span>

<span data-ttu-id="a8710-160">Você pode criar uma rota de voz e definir o Regex e os gateways a serem associados à rota de voz usando o cmdlet "New-CsOnlineVoiceRoute".</span><span class="sxs-lookup"><span data-stu-id="a8710-160">You can create a voice route and define the regex and gateways to be associated with the voice route by using the “New-CsOnlineVoiceRoute” cmdlet.</span></span> <span data-ttu-id="a8710-161">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="a8710-161">For Example:</span></span>

```
New-CsOnlineVoiceRoute -Identity "Redmond 1" -NumberPattern "^\+1(425|206)(\d{7})$" -OnlinePstnGatewayList sbc1.contoso.biz, sbc2.contoso.biz -Priority 1 -OnlinePstnUsages "US and Canada"
```

#### <a name="create-audio-conferencing-voice-routing-policies"></a><span data-ttu-id="a8710-162">Criar políticas de roteamento de voz da conferência de áudio</span><span class="sxs-lookup"><span data-stu-id="a8710-162">Create Audio Conferencing voice routing policies</span></span>

<span data-ttu-id="a8710-163">As políticas de roteamento de voz de audioconferência determinam as possíveis rotas que podem ser usadas para direcionar uma chamada originada das reuniões de um organizador com base no número de telefone de destino da chamada de discagem de reunião.</span><span class="sxs-lookup"><span data-stu-id="a8710-163">Audio Conferencing voice routing policies determine the possible routes that can be used to route a call originating from the meetings of an organizer based on the target phone number of the meeting dial-out call.</span></span> <span data-ttu-id="a8710-164">As políticas de roteamento de voz do áudio audioconferência são associadas a um ou mais usos de PSTN, que, por sua vez, determinam as possíveis rotas que serão tentadas para serem usadas para as chamadas discadas da reunião dos organizadores associados à política.</span><span class="sxs-lookup"><span data-stu-id="a8710-164">Audio Conferencing voice routing policies are associated to one or more PSTN usages, which in turn, determine the possible routes that will be attempted to be used for the meeting dial-out calls of the organizers associated to the policy.</span></span>

<span data-ttu-id="a8710-165">Você pode criar uma política de roteamento de voz de audioconferência usando o cmdlet "New-CsOnlineAudioConferencingRoutingPolicy".</span><span class="sxs-lookup"><span data-stu-id="a8710-165">You can create an Audio Conferencing voice routing policy by using the “New- CsOnlineAudioConferencingRoutingPolicy” cmdlet.</span></span> <span data-ttu-id="a8710-166">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="a8710-166">For Example:</span></span>

```
New-CsOnlineAudioConferencingRoutingPolicy "Policy 1" -OnlinePstnUsages "US and Canada"
```

<span data-ttu-id="a8710-167">Depois que a política é atribuída a um usuário e quando uma chamada de discagem externa da reunião é iniciada a partir de uma das reuniões do usuário, as rotas de voz nos usos PSTN associados ao organizador por meio da política de roteamento de voz do usuário serão avaliadas.</span><span class="sxs-lookup"><span data-stu-id="a8710-167">After the policy is assigned to a user, and when a meeting dial-out call is initiated from one of the user's meetings, the voice routes in the PSTN usages that are associated to the organizer through the user's voice routing policy will be evaluated.</span></span> <span data-ttu-id="a8710-168">Se o destino da chamada discada da reunião corresponder a um Regex em uma das rotas de voz associadas ao organizador, a chamada de discagem de reunião será roteada para o gateway PSTN definido na rota de voz.</span><span class="sxs-lookup"><span data-stu-id="a8710-168">If the meeting dial-out call destination matches a regex in one of the voice routes that are associated to the organizer, the meeting dial-out call will be routed to the PSTN gateway defined in the voice route.</span></span> <span data-ttu-id="a8710-169">Se o destino da chamada discada da reunião não corresponder a nenhuma das rotas de voz associadas ao organizador, a chamada de discagem de reunião será roteada pela Microsoft.</span><span class="sxs-lookup"><span data-stu-id="a8710-169">If the meeting dial-out call destination does not match any of the voice routes associated to the organizer, the meeting dial-out call will be routed by Microsoft.</span></span>

#### <a name="assign-a-policy-to-your-users"></a><span data-ttu-id="a8710-170">Atribuir uma política a seus usuários</span><span class="sxs-lookup"><span data-stu-id="a8710-170">Assign a policy to your users</span></span>

<span data-ttu-id="a8710-171">Depois que as políticas de roteamento de audioconferência são definidas, agora você pode atribuí-las aos usuários.</span><span class="sxs-lookup"><span data-stu-id="a8710-171">After the Audio Conferencing routing policies are defined, you can now assign them to users.</span></span> <span data-ttu-id="a8710-172">Depois que as políticas forem atribuídas a elas, as chamadas de discagem de reunião serão avaliadas para determinar o caminho de roteamento.</span><span class="sxs-lookup"><span data-stu-id="a8710-172">After policies are assigned to them, the meeting dial-out calls will be evaluated against it to determine their routing path.</span></span> <span data-ttu-id="a8710-173">As políticas de roteamento de audioconferência são sempre avaliadas com base no organizador da reunião, independentemente do usuário na reunião que inicia uma chamada de discagem de reunião.</span><span class="sxs-lookup"><span data-stu-id="a8710-173">Audio Conferencing routing policies are always evaluated based on the organizer of the meeting, independently from the user in the meeting that initiates a meeting dial-out call.</span></span>

<span data-ttu-id="a8710-174">Você pode atribuir uma política de roteamento de voz de audioconferência a um usuário usando o cmdlet "Grant-CsOnlineAudioConferencingRoutingPolicy".</span><span class="sxs-lookup"><span data-stu-id="a8710-174">You can assign an Audio Conferencing voice routing policy to a user by using the “Grant-CsOnlineAudioConferencingRoutingPolicy” cmdlet.</span></span> <span data-ttu-id="a8710-175">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="a8710-175">For example:</span></span>

```
Grant-CsOnlineAudioConferencingRoutingPolicy -Identity "<User Identity>" -PolicyName "Policy 1”
```


### <a name="configure-routing-on-the-telephony-equipment-of-your-organization"></a><span data-ttu-id="a8710-176">Configurar o roteamento no equipamento de telefonia da sua organização</span><span class="sxs-lookup"><span data-stu-id="a8710-176">Configure routing on the telephony equipment of your organization</span></span>

<span data-ttu-id="a8710-177">No equipamento de telefonia da sua organização, você precisa garantir que as chamadas de discagem externa da reunião roteadas pelo encaminhamento direto sejam roteadas para o destino pretendido.</span><span class="sxs-lookup"><span data-stu-id="a8710-177">On the telephony equipment of your organization, you need to ensure that the meeting dial-out calls routed through Direct Routing are routed to the intended destination.</span></span>


### <a name="optional-configure-a-dial-plan"></a><span data-ttu-id="a8710-178">Adicionais Configurar um plano de discagem</span><span class="sxs-lookup"><span data-stu-id="a8710-178">(Optional) Configure a dial plan</span></span>

<span data-ttu-id="a8710-179">Um plano de discagem é um conjunto de regras de normalização que traduz os números de telefone discados por um usuário individual em um formato alternativo (geralmente E. 164) para fins de autorização de chamadas e encaminhamento de chamadas.</span><span class="sxs-lookup"><span data-stu-id="a8710-179">A dial plan is a set of normalization rules that translate dialed phone numbers by an individual user into an alternate format (typically E.164) for purposes of call authorization and call routing.</span></span>

<span data-ttu-id="a8710-180">Por padrão, os usuários do teams podem discar para números PSTN no formato E. 164, isto é, + \<country code\> \<number\> .</span><span class="sxs-lookup"><span data-stu-id="a8710-180">By default, Teams users can dial-out to PSTN numbers in E.164 format, that is, +\<country code\>\<number\>.</span></span> <span data-ttu-id="a8710-181">No entanto, os planos de discagem podem ser usados para permitir que os usuários disquem números de telefone em outros formatos, por exemplo, extensões de 4 dígitos.</span><span class="sxs-lookup"><span data-stu-id="a8710-181">However, dial plans can be used to allow users to dial phone numbers in other formats, for instance 4-digit extensions.</span></span>

<span data-ttu-id="a8710-182">Se quiser habilitar a discagem baseada na extensão por meio de conferências na rede, você pode configurar planos de discagem para que correspondam ao padrão de discagem de extensão para os intervalos de número de telefone do número de telefone de sua organização.</span><span class="sxs-lookup"><span data-stu-id="a8710-182">If you would like to enable extension-based dialing through On-network conferencing, you can set up dial plans to match the extension dialing pattern to the phone number ranges of the phone number of your organization.</span></span> <span data-ttu-id="a8710-183">Para configurar planos de discagem, consulte [criar e gerenciar planos de discagem](create-and-manage-dial-plans.md).</span><span class="sxs-lookup"><span data-stu-id="a8710-183">To set up dial plans, see [Create and manage dial plans](create-and-manage-dial-plans.md).</span></span>


## <a name="known-issues-in-open-preview"></a><span data-ttu-id="a8710-184">Problemas conhecidos do Open Preview</span><span class="sxs-lookup"><span data-stu-id="a8710-184">Known issues in Open Preview</span></span>

<span data-ttu-id="a8710-185">Veja a seguir uma lista de problemas conhecidos presentes atualmente na versão prévia aberta da conferência em rede.</span><span class="sxs-lookup"><span data-stu-id="a8710-185">The following is a list of known issues that are currently present in the Open Preview release of On-network conferencing.</span></span> <span data-ttu-id="a8710-186">A Microsoft está trabalhando para resolver esses problemas.</span><span class="sxs-lookup"><span data-stu-id="a8710-186">Microsoft is working on addressing these issues.</span></span>

| <span data-ttu-id="a8710-187">Problema</span><span class="sxs-lookup"><span data-stu-id="a8710-187">Issue</span></span> | <span data-ttu-id="a8710-188">Possíveis</span><span class="sxs-lookup"><span data-stu-id="a8710-188">Workaround</span></span> |
| :--- | :--- |
| <span data-ttu-id="a8710-189">Chamadas discadas com IDs de chamadas anônimas/ocultas que são roteadas através da conferência pela rede não podem ser conectadas à reunião.</span><span class="sxs-lookup"><span data-stu-id="a8710-189">Dial-in calls with anonymous/hidden caller IDs that are routed through On-network conferencing cannot be connected to the meeting.</span></span> | <span data-ttu-id="a8710-190">Se possível, defina uma configuração em seu PBX ou SBC para sempre enviar uma identificação de chamada para chamadas roteadas via Conferência na rede.</span><span class="sxs-lookup"><span data-stu-id="a8710-190">If possible, set a configuration in your PBX or SBC to always send a caller ID for calls routed via On-network conferencing.</span></span>|
| <span data-ttu-id="a8710-191">Em alguns casos, a mensagem de boas-vindas que é reproduzida aos usuários quando ele disca para o serviço ("bem-vindo ao serviço de audioconferência...") é truncada e os usuários não ouvem a palavra "bem-vindo".</span><span class="sxs-lookup"><span data-stu-id="a8710-191">In some cases, the welcome message that is played to users when they dial in to the service (“Welcome to the Audio Conferencing service…”) is truncated and users do not hear the “Welcome” word.</span></span>| <span data-ttu-id="a8710-192">Não há soluções alternativas para esse problema no momento.</span><span class="sxs-lookup"><span data-stu-id="a8710-192">There are no workarounds for this issue at the moment.</span></span> |




## <a name="related-topics"></a><span data-ttu-id="a8710-193">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="a8710-193">Related topics</span></span>


