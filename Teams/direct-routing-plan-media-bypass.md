---
title: Planejar o bypass de mídia com Roteamento Direto
ms.author: crowe
author: CarolynRowe
manager: serdars
audience: ITPro
ms.reviewer: NMuravlyannikov
ms.topic: article
ms.service: msteams
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
f1.keywords:
- NOCSH
description: Saiba como planejar a bypass de mídia com o roteamento direto do sistema telefônico, o que permite reduzir o caminho do tráfego de mídia e melhorar o desempenho.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 316e94a2baafcecc9fb690f3d836e7c96c0b30ea
ms.sourcegitcommit: a9e16aa3539103f3618427ffc7ebbda6919b5176
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/27/2020
ms.locfileid: "43901836"
---
# <a name="plan-for-media-bypass-with-direct-routing"></a><span data-ttu-id="99984-103">Planejar o bypass de mídia com Roteamento Direto</span><span class="sxs-lookup"><span data-stu-id="99984-103">Plan for media bypass with Direct Routing</span></span>

## <a name="about-media-bypass-with-direct-routing"></a><span data-ttu-id="99984-104">Sobre o bypass de mídia com roteamento direto</span><span class="sxs-lookup"><span data-stu-id="99984-104">About media bypass with Direct Routing</span></span>

<span data-ttu-id="99984-105">O bypass de mídia permite reduzir o caminho do tráfego de mídia e reduzir o número de saltos em trânsito para melhorar o desempenho.</span><span class="sxs-lookup"><span data-stu-id="99984-105">Media bypass enables you to shorten the path of media traffic and reduce the number of hops in transit for better performance.</span></span> <span data-ttu-id="99984-106">Com o bypass de mídia, a mídia é mantida entre o controlador de borda de sessão (SBC) e o cliente, em vez de enviá-lo por meio do sistema telefônico da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="99984-106">With media bypass, media is kept between the Session Border Controller (SBC) and the client instead of sending it via the Microsoft Phone System.</span></span> <span data-ttu-id="99984-107">Para configurar o bypass de mídia, o SBC e o cliente devem estar no mesmo local ou na rede.</span><span class="sxs-lookup"><span data-stu-id="99984-107">To configure media bypass, the SBC and the client must be in the same location or network.</span></span>

<span data-ttu-id="99984-108">Você pode controlar o bypass de mídia para cada SBC usando o comando **set-CSOnlinePSTNGateway** com o parâmetro **-MediaBypass** definido como true ou false.</span><span class="sxs-lookup"><span data-stu-id="99984-108">You can control media bypass for each SBC by using the **Set-CSOnlinePSTNGateway** command with the **-MediaBypass** parameter set to true or false.</span></span> <span data-ttu-id="99984-109">Se você habilitar o bypass de mídia, isso não significa que todo o tráfego de mídia permaneça dentro da rede corporativa.</span><span class="sxs-lookup"><span data-stu-id="99984-109">If you enable media bypass, this does not mean that all media traffic will stay within the corporate network.</span></span> <span data-ttu-id="99984-110">Este artigo descreve o fluxo de chamadas em diferentes cenários.</span><span class="sxs-lookup"><span data-stu-id="99984-110">This article describes the call flow in different scenarios.</span></span>    

<span data-ttu-id="99984-111">Os diagramas a seguir ilustram a diferença no fluxo de chamadas com e sem bypass de mídia.</span><span class="sxs-lookup"><span data-stu-id="99984-111">The diagrams below illustrate the difference in call flow with and without media bypass.</span></span>

<span data-ttu-id="99984-112">Sem bypass de mídia, quando um cliente faz ou recebe uma chamada, tanto a sinalização quanto o fluxo de mídia entre o SBC, o sistema telefônico da Microsoft e o cliente da equipe, conforme mostrado no diagrama a seguir:</span><span class="sxs-lookup"><span data-stu-id="99984-112">Without media bypass, when a client makes or receives a call, both signaling and media flow between the SBC, the Microsoft Phone System, and the Teams client, as shown in the following diagram:</span></span>

![Mostra a sinalização e o fluxo de mídia sem bypass de mídia](media/direct-routing-media-bypass-1.png)


<span data-ttu-id="99984-114">Mas vamos pressupor que um usuário esteja no mesmo prédio ou na mesma rede do SBC.</span><span class="sxs-lookup"><span data-stu-id="99984-114">But let's assume that a user is in the same building or network as the SBC.</span></span> <span data-ttu-id="99984-115">Por exemplo, suponha que um usuário que está em um edifício em Frankfurt faça uma chamada para um usuário PSTN:</span><span class="sxs-lookup"><span data-stu-id="99984-115">For example, assume a user who is in a building in Frankfurt makes a call to a PSTN user:</span></span> 

- <span data-ttu-id="99984-116">**Sem bypass de mídia**, a mídia fluirá via Amsterdã ou Dublin (em que o Microsoft datacenters será implantado) e voltará para o SBC em Frankfurt.</span><span class="sxs-lookup"><span data-stu-id="99984-116">**Without media bypass**, media will flow via either Amsterdam or Dublin (where Microsoft datacenters are deployed) and back to the SBC in Frankfurt.</span></span> 

  <span data-ttu-id="99984-117">O datacenter na Europa está selecionado porque o SBC está na Europa e a Microsoft usa o datacenter mais próximo do SBC.</span><span class="sxs-lookup"><span data-stu-id="99984-117">The datacenter in Europe is selected because the SBC is in Europe, and Microsoft uses the datacenter closest to the SBC.</span></span> <span data-ttu-id="99984-118">Embora essa abordagem não afete a qualidade da chamada devido à otimização do fluxo de tráfego nas redes Microsoft na maioria dos países, o tráfego tem um loop desnecessário.</span><span class="sxs-lookup"><span data-stu-id="99984-118">While this approach does not affect call quality due to optimization of traffic flow within Microsoft networks in most geographies, the traffic has an unnecessary loop.</span></span>     

- <span data-ttu-id="99984-119">**Com o bypass de mídia**, a mídia é mantida diretamente entre o usuário do Teams e o SBC, conforme mostrado no diagrama a seguir:</span><span class="sxs-lookup"><span data-stu-id="99984-119">**With media bypass**, the media is kept directly between the Teams user and the SBC as shown in the following diagram:</span></span>

![Mostra a sinalização e o fluxo de mídia com bypass de mídia](media/direct-routing-media-bypass-2.png)

<span data-ttu-id="99984-121">O bypass de mídia aproveita protocolos chamados de ICE (estabelecimento de conectividade interativa) no cliente de equipes e ICE Lite no SBC.</span><span class="sxs-lookup"><span data-stu-id="99984-121">Media bypass leverages protocols called Interactive Connectivity Establishment (ICE) on the Teams client and ICE lite on the SBC.</span></span> <span data-ttu-id="99984-122">Esses protocolos permitem o roteamento direto usar o caminho de mídia mais direto para obter a melhor qualidade.</span><span class="sxs-lookup"><span data-stu-id="99984-122">These protocols enable Direct Routing to use the most direct media path for optimal quality.</span></span> <span data-ttu-id="99984-123">ICE e ICE Lite são padrões de WebRTC.</span><span class="sxs-lookup"><span data-stu-id="99984-123">ICE and ICE Lite are WebRTC standards.</span></span> <span data-ttu-id="99984-124">Para obter informações detalhadas sobre esses protocolos, consulte RFC 5245.</span><span class="sxs-lookup"><span data-stu-id="99984-124">For detailed information about these protocols, see RFC 5245.</span></span>


## <a name="call-flow-and-firewall-planning"></a><span data-ttu-id="99984-125">Fluxo de chamadas e planejamento de firewall</span><span class="sxs-lookup"><span data-stu-id="99984-125">Call flow and firewall planning</span></span>

<span data-ttu-id="99984-126">O fluxo de chamadas e o planejamento de firewalls dependem se o usuário tem acesso direto ao endereço IP público do SBC e se o usuário está dentro ou fora da rede.</span><span class="sxs-lookup"><span data-stu-id="99984-126">Call flow and firewall planning depends on whether the user has direct access to the public IP address of the SBC, and whether the user is inside or outside of the network.</span></span>

### <a name="call-flow-if-the-user-has-direct-access-to-the-public-ip-address-of-the-sbc"></a><span data-ttu-id="99984-127">Fluxo de chamadas se o usuário tiver acesso direto ao endereço IP público do SBC</span><span class="sxs-lookup"><span data-stu-id="99984-127">Call flow if the user has direct access to the public IP address of the SBC</span></span>

<span data-ttu-id="99984-128">Se o usuário tiver acesso direto ao endereço IP público do SBC, o fluxo de chamadas será o seguinte:</span><span class="sxs-lookup"><span data-stu-id="99984-128">If the user has direct access to the public IP address of the SBC, the call flow is as follows:</span></span>

- <span data-ttu-id="99984-129">Para bypass de mídia, o cliente de equipes deve ter acesso ao endereço IP público do SBC mesmo a partir de uma rede interna.</span><span class="sxs-lookup"><span data-stu-id="99984-129">For media bypass, the Teams client must have access to the public IP address of the SBC even from an internal network.</span></span> <span data-ttu-id="99984-130">Se a mídia direta não for desejada, a mídia poderá fluir por retransmissões de transporte.</span><span class="sxs-lookup"><span data-stu-id="99984-130">If direct media is not desired, the media can flow via Transport Relays.</span></span>

- <span data-ttu-id="99984-131">Esta é a solução recomendada quando um usuário está no mesmo prédio e/ou rede do SBC – remover componentes de nuvem da Microsoft do caminho de mídia.</span><span class="sxs-lookup"><span data-stu-id="99984-131">This is the recommended solution when a user is in the same building and/or network as the SBC – remove Microsoft Cloud components from the media path.</span></span>

- <span data-ttu-id="99984-132">A sinalização sempre flui via nuvem da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="99984-132">Signaling always flows via the Microsoft cloud.</span></span>

<span data-ttu-id="99984-133">O diagrama a seguir mostra o fluxo de chamadas quando o bypass de mídia está habilitado, o cliente é interno e o cliente pode alcançar o endereço IP público do SBC (mídia direta):</span><span class="sxs-lookup"><span data-stu-id="99984-133">The following diagram shows call flow when media bypass is enabled, the client is internal, and the client can reach the public IP address of the SBC (direct media):</span></span> 

- <span data-ttu-id="99984-134">As setas e os valores numéricos dos caminhos estão de acordo com o artigo [Microsoft Teams Call flui](https://docs.microsoft.com/microsoftteams/microsoft-teams-online-call-flows) .</span><span class="sxs-lookup"><span data-stu-id="99984-134">The arrows and numeric values of the paths are in accordance with the [Microsoft Teams call flows](https://docs.microsoft.com/microsoftteams/microsoft-teams-online-call-flows) article.</span></span>

- <span data-ttu-id="99984-135">O sinal SIP sempre usa os caminhos 4 e 4 (dependendo da direção do tráfego).</span><span class="sxs-lookup"><span data-stu-id="99984-135">The SIP signaling always takes paths 4 and 4' (depending on the direction of the traffic).</span></span> <span data-ttu-id="99984-136">A mídia permanece local e usa o caminho 5b.</span><span class="sxs-lookup"><span data-stu-id="99984-136">Media stays local and takes path 5b.</span></span>

![Mostra o fluxo de chamadas com bypass de mídia habilitado, o cliente é interno](media/direct-routing-media-bypass-3.png)


### <a name="call-flow-if-the-user-does-not-have-access-to-the-public-ip-address-of-the-sbc"></a><span data-ttu-id="99984-138">Fluxo de chamadas se o usuário não tiver acesso ao endereço IP público do SBC</span><span class="sxs-lookup"><span data-stu-id="99984-138">Call flow if the user does not have access to the public IP address of the SBC</span></span>

<span data-ttu-id="99984-139">O procedimento a seguir descreve o fluxo de chamadas se o usuário não tiver acesso ao endereço IP público do SBC.</span><span class="sxs-lookup"><span data-stu-id="99984-139">The following describes call flow if the user does not have access to the public IP address of the SBC.</span></span> 

<span data-ttu-id="99984-140">Por exemplo, suponha que o usuário seja externo, e o administrador de locatários decidiu não abrir o endereço IP público do SBC para todos na Internet, mas somente para a nuvem da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="99984-140">For example, assume the user is external, and the tenant administrator decided not to open the public IP address of the SBC to everyone in the Internet, but only to the Microsoft Cloud.</span></span> <span data-ttu-id="99984-141">Os componentes internos do tráfego podem fluir pelas retransmissões de transporte de equipe.</span><span class="sxs-lookup"><span data-stu-id="99984-141">The internal components of traffic can flow via the Teams Transport Relays.</span></span> <span data-ttu-id="99984-142">Esta é a configuração recomendada para usuários fora da rede corporativa.</span><span class="sxs-lookup"><span data-stu-id="99984-142">This is the recommended configuration for users outside of the corporate network.</span></span> <span data-ttu-id="99984-143">Considere o seguinte:</span><span class="sxs-lookup"><span data-stu-id="99984-143">Consider the following:</span></span>

- <span data-ttu-id="99984-144">As retransmissões de transporte de equipes são usadas.</span><span class="sxs-lookup"><span data-stu-id="99984-144">Teams Transport Relays are used.</span></span>

- <span data-ttu-id="99984-145">Para bypass de mídia, a Microsoft usa uma versão de retransmissões de transporte que requer as portas de abertura 50 000 a 59 999 entre as retransmissões de transporte de equipes e o SBC (no futuro, planejamos mudar para a versão que requer apenas as portas 3478 e 3479).</span><span class="sxs-lookup"><span data-stu-id="99984-145">For media bypass, Microsoft uses a version of Transport Relays that requires opening ports 50 000 to 59 999 between the Teams Transport Relays and the SBC (in the future we plan to move to the version which requires only 3478 and 3479 ports).</span></span>

- <span data-ttu-id="99984-146">Para fins de otimização de mídia, a Microsoft recomenda abrir o endereço IP público do SBC somente para retransmissões de transporte de equipe.</span><span class="sxs-lookup"><span data-stu-id="99984-146">For media optimization purposes, Microsoft recommends opening the public IP address of the SBC only to Teams Transport Relays.</span></span> <span data-ttu-id="99984-147">Para clientes fora da rede corporativa, a Microsoft recomenda usar retransmissões de transporte em vez de acessar o endereço IP público do SBC diretamente.</span><span class="sxs-lookup"><span data-stu-id="99984-147">For clients outside of the corporate network, Microsoft recommends using Transport Relays instead of reaching the public IP address of the SBC directly.</span></span>

<span data-ttu-id="99984-148">O diagrama a seguir mostra o fluxo de chamadas quando o bypass de mídia está habilitado, o cliente é externo, e o cliente não pode alcançar o endereço IP público do controlador de borda de sessão (a mídia é retransmitida pela retransmissão de transporte do Teams).</span><span class="sxs-lookup"><span data-stu-id="99984-148">The following diagram shows call flow when media bypass is enabled, the client is external, and the client cannot reach the public IP address of the Session Border Controller (media is relayed by Teams Transport Relay).</span></span>

- <span data-ttu-id="99984-149">As setas e os valores numéricos dos caminhos estão de acordo com o artigo [Microsoft Teams Call flui](https://docs.microsoft.com/microsoftteams/microsoft-teams-online-call-flows) .</span><span class="sxs-lookup"><span data-stu-id="99984-149">The arrows and numeric values of the paths are in accordance with the [Microsoft Teams call flows](https://docs.microsoft.com/microsoftteams/microsoft-teams-online-call-flows) article.</span></span>

- <span data-ttu-id="99984-150">A mídia é retransmitida pelos caminhos 3, 3 ', 4 e 4 '</span><span class="sxs-lookup"><span data-stu-id="99984-150">Media is relayed via paths 3, 3', 4 and 4'</span></span>

![Mostra o fluxo de chamadas se o usuário não tiver acesso ao IP público do SBC](media/direct-routing-media-bypass-4.png)


### <a name="call-flow-if-a-user-is-outside-the-network-and-has-access-to-the-public-ip-of-the-sbc"></a><span data-ttu-id="99984-152">Fluxo de chamadas se um usuário estiver fora da rede e tiver acesso ao IP público do SBC</span><span class="sxs-lookup"><span data-stu-id="99984-152">Call flow if a user is outside the network and has access to the public IP of the SBC</span></span>

> [!NOTE]
> <span data-ttu-id="99984-153">Essa não é uma configuração recomendada porque não aproveita as retransmissões de transporte de equipes.</span><span class="sxs-lookup"><span data-stu-id="99984-153">This is not a recommended configuration because it does not take advantage of Teams Transport Relays.</span></span> <span data-ttu-id="99984-154">Em vez disso, considere o cenário anterior em que o usuário não tem acesso ao endereço IP público do SBC.</span><span class="sxs-lookup"><span data-stu-id="99984-154">Instead, you should consider the previous scenario where the user does not have access to the public IP address of the SBC.</span></span> 

<span data-ttu-id="99984-155">O diagrama a seguir mostra o fluxo de chamadas quando o bypass de mídia está habilitado, o cliente é externo e o cliente pode alcançar o endereço IP público do SBC (Direct Media).</span><span class="sxs-lookup"><span data-stu-id="99984-155">The following diagram shows call flow when media bypass is enabled, the client is external, and the client can reach the public IP address of the SBC (direct media).</span></span>

- <span data-ttu-id="99984-156">As setas e os valores numéricos dos caminhos estão de acordo com o artigo [Microsoft Teams Call flui](https://docs.microsoft.com/microsoftteams/microsoft-teams-online-call-flows) .</span><span class="sxs-lookup"><span data-stu-id="99984-156">The arrows and numeric values of the paths are in accordance with the [Microsoft Teams call flows](https://docs.microsoft.com/microsoftteams/microsoft-teams-online-call-flows) article.</span></span>

- <span data-ttu-id="99984-157">O sinal SIP sempre usa os caminhos 3 e 3 ' (dependendo da direção do tráfego).</span><span class="sxs-lookup"><span data-stu-id="99984-157">The SIP signaling always takes paths 3 and 3' (depending on the direction of the traffic).</span></span> <span data-ttu-id="99984-158">Fluxos de mídia usando o caminho 2.</span><span class="sxs-lookup"><span data-stu-id="99984-158">Media flows using path 2.</span></span>

![Mostra o fluxo de chamadas se o usuário não tiver acesso ao IP público do SBC](media/direct-routing-media-bypass-5.png)


## <a name="use-of-media-processors-and-transport-relays"></a><span data-ttu-id="99984-160">Uso de processadores de mídia e retransmissões de transporte</span><span class="sxs-lookup"><span data-stu-id="99984-160">Use of Media Processors and Transport Relays</span></span>

<span data-ttu-id="99984-161">Há dois componentes na nuvem da Microsoft que podem estar no caminho do tráfego de mídia: processadores de mídia e retransmissões de transporte.</span><span class="sxs-lookup"><span data-stu-id="99984-161">There are two components in the Microsoft Cloud that can be in the path of media traffic: Media Processors and Transport Relays.</span></span> 

- <span data-ttu-id="99984-162">O processador de mídia é um componente voltado para o público que manipula mídia em casos não bypass e manipula mídia para aplicativos de voz.</span><span class="sxs-lookup"><span data-stu-id="99984-162">The Media Processor is a public facing component that handles media in non-bypass cases and handles media for voice applications.</span></span>

   <span data-ttu-id="99984-163">Processadores de mídia estão sempre no caminho para chamadas não ignoradas pelo usuário final, mas nunca no caminho para chamadas ignoradas.</span><span class="sxs-lookup"><span data-stu-id="99984-163">Media Processors are always in the path for end user non-bypassed calls, but never in the path for bypassed calls.</span></span> <span data-ttu-id="99984-164">Processadores de mídia estão sempre no caminho para todos os aplicativos de voz, como parque de chamadas, atendedor automático organizacional e filas de chamadas.</span><span class="sxs-lookup"><span data-stu-id="99984-164">Media Processors are always in the path for all voice applications such as Call Park, Organizational Auto Attendant, and Call Queues.</span></span>

- <span data-ttu-id="99984-165">A retransmissão de transporte é usada para se conectar ao serviço de transporte mais próximo para enviar tráfego em tempo real.</span><span class="sxs-lookup"><span data-stu-id="99984-165">The Transport Relay is used to connect to the closest Transport Service to send real time traffic.</span></span>

   <span data-ttu-id="99984-166">As retransmissões de transporte podem ou não estar no caminho para chamadas ignoradas – originadas de ou destinados a usuários finais, dependendo de onde o usuário está e como a rede está configurada.</span><span class="sxs-lookup"><span data-stu-id="99984-166">Transport Relays might or might not be in the path for bypassed calls--originating from or destined to end users--depending on where the user is and how the network is configured .</span></span>

<span data-ttu-id="99984-167">O diagrama a seguir mostra dois fluxos de chamadas – um com bypass de mídia habilitado e o segundo com bypass de mídia desabilitado.</span><span class="sxs-lookup"><span data-stu-id="99984-167">The following diagram shows two call flows – one with media bypass enabled and the second with media bypass disabled.</span></span> <span data-ttu-id="99984-168">Observação o diagrama só ilustra o tráfego originário de--ou de usuários destinados para usuários finais.</span><span class="sxs-lookup"><span data-stu-id="99984-168">Note the diagram only illustrates traffic originating from--or destined to--end users.</span></span>  
- <span data-ttu-id="99984-169">O controlador de mídia é um microserviço no Azure que atribui processadores de mídia e cria ofertas de protocolo de descrição de sessão (SDP).</span><span class="sxs-lookup"><span data-stu-id="99984-169">The Media Controller is a microservice in Azure that assigns Media Processors and creates Session Description Protocol (SDP) offers.</span></span>

- <span data-ttu-id="99984-170">O proxy SIP é um componente que traduz a sinalização REST HTTP usada no Teams para SIP.</span><span class="sxs-lookup"><span data-stu-id="99984-170">The SIP Proxy is a component that translates HTTP REST signaling used in Teams to SIP.</span></span>    

![Mostra fluxos de chamadas com o bypass de mídia habilitado e desabilitado](media/direct-routing-media-bypass-6.png)


<span data-ttu-id="99984-172">A tabela a seguir resume a diferença entre processadores de mídia e retransmissões de transporte.</span><span class="sxs-lookup"><span data-stu-id="99984-172">The table below summarizes the difference between Media Processors and Transport Relays.</span></span>

|    | <span data-ttu-id="99984-173">Processadores de mídia</span><span class="sxs-lookup"><span data-stu-id="99984-173">Media Processors</span></span> | <span data-ttu-id="99984-174">Retransmissões de transporte</span><span class="sxs-lookup"><span data-stu-id="99984-174">Transport Relays</span></span>|
| :--------------|:---------------|:------------|
<span data-ttu-id="99984-175">Em caminho de mídia para chamadas não ignoradas para usuários finais</span><span class="sxs-lookup"><span data-stu-id="99984-175">In media path for non-bypassed calls for end users</span></span> | <span data-ttu-id="99984-176">Ativa</span><span class="sxs-lookup"><span data-stu-id="99984-176">Always</span></span> | <span data-ttu-id="99984-177">Não</span><span class="sxs-lookup"><span data-stu-id="99984-177">Never</span></span> | 
<span data-ttu-id="99984-178">Em caminho de mídia para chamadas ignoradas para usuários finais</span><span class="sxs-lookup"><span data-stu-id="99984-178">In media path for bypassed calls for end users</span></span> | <span data-ttu-id="99984-179">Não</span><span class="sxs-lookup"><span data-stu-id="99984-179">Never</span></span> | <span data-ttu-id="99984-180">Se o cliente não puder alcançar o SBC no endereço IP público</span><span class="sxs-lookup"><span data-stu-id="99984-180">If client cannot reach the SBC on the public IP address</span></span> | 
<span data-ttu-id="99984-181">Em caminho de mídia para aplicativos de voz</span><span class="sxs-lookup"><span data-stu-id="99984-181">In media path for voice applications</span></span> | <span data-ttu-id="99984-182">Ativa</span><span class="sxs-lookup"><span data-stu-id="99984-182">Always</span></span> | <span data-ttu-id="99984-183">Não</span><span class="sxs-lookup"><span data-stu-id="99984-183">Never</span></span> | 
<span data-ttu-id="99984-184">Pode fazer transcodificação (B2BUA)\*</span><span class="sxs-lookup"><span data-stu-id="99984-184">Can do transcoding (B2BUA)\*</span></span> | <span data-ttu-id="99984-185">Sim</span><span class="sxs-lookup"><span data-stu-id="99984-185">Yes</span></span> | <span data-ttu-id="99984-186">Não, somente retransmite o áudio entre os pontos de extremidade</span><span class="sxs-lookup"><span data-stu-id="99984-186">No, only relays audio between endpoints</span></span> | 
<span data-ttu-id="99984-187">Número de instâncias mundiais e locais</span><span class="sxs-lookup"><span data-stu-id="99984-187">Number of instances worldwide and location</span></span> | <span data-ttu-id="99984-188">8 no total: 2 em leste dos EUA e oeste; 2 em Amsterdã e Dublin; 2 em Hong Kong e Cingapura; 2 no Japão</span><span class="sxs-lookup"><span data-stu-id="99984-188">8 total: 2 in US East and West; 2 in Amsterdam and Dublin; 2 in Hong Kong and Singapore; 2 in Japan</span></span>  | <span data-ttu-id="99984-189">Muitos</span><span class="sxs-lookup"><span data-stu-id="99984-189">Multiple</span></span>

<span data-ttu-id="99984-190">O intervalo IP é 52.112.0.0/14 (endereços IP de 52.112.0.1 a 52.115.255.254).</span><span class="sxs-lookup"><span data-stu-id="99984-190">The IP range is 52.112.0.0 /14 (IP addresses from 52.112.0.1 to 52.115.255.254).</span></span> 

<span data-ttu-id="99984-191">\*Explicação da transcodificação:</span><span class="sxs-lookup"><span data-stu-id="99984-191">\* Transcoding explanation:</span></span> 

- <span data-ttu-id="99984-192">O processador de mídia é B2BUA, o que significa que ele pode alterar codecs (por exemplo, SILK do cliente do teams para MP e G. 711 entre MP e SBC).</span><span class="sxs-lookup"><span data-stu-id="99984-192">Media Processor is B2BUA, which means it can change a codecs (for example, SILK from Teams client to MP and G.711 between MP and SBC).</span></span>

- <span data-ttu-id="99984-193">As retransmissões de transporte não são B2BUA, o que significa que o codec nunca é alterado entre o cliente e o SBC, mesmo se o tráfego fluir via retransmissões.</span><span class="sxs-lookup"><span data-stu-id="99984-193">Transport Relays are not B2BUA, which means the codec is never changed between the client and the SBC--even if traffic flows via relays.</span></span>

### <a name="use-of-teams-media-processors-if-trunk-is-configured-for-media-bypass"></a><span data-ttu-id="99984-194">Uso de processadores de mídia do teams se o tronco estiver configurado para bypass de mídia</span><span class="sxs-lookup"><span data-stu-id="99984-194">Use of Teams Media Processors if trunk is configured for media bypass</span></span>

<span data-ttu-id="99984-195">Os processadores de mídia de equipe sempre são inseridos no caminho de mídia nos seguintes cenários:</span><span class="sxs-lookup"><span data-stu-id="99984-195">Teams Media Processors are always inserted in the media path in the following scenarios:</span></span>

- <span data-ttu-id="99984-196">A chamada é escalonada de 1:1 para uma chamada em grupo</span><span class="sxs-lookup"><span data-stu-id="99984-196">Call is escalated from 1:1 to a group call</span></span>
- <span data-ttu-id="99984-197">A chamada está indo para um usuário de equipes federadas</span><span class="sxs-lookup"><span data-stu-id="99984-197">Call is going to a federated Teams user</span></span>
- <span data-ttu-id="99984-198">A chamada é encaminhada ou transferida para um usuário do Skype for Business</span><span class="sxs-lookup"><span data-stu-id="99984-198">Call is forwarded or transferred to a Skype for Business user</span></span>

<span data-ttu-id="99984-199">Verifique se o seu SBC tem acesso aos processadores de mídia e intervalos de transporte de transporte conforme descrito abaixo.</span><span class="sxs-lookup"><span data-stu-id="99984-199">Ensure your SBC has access to the Media Processors and Transport Relays ranges as described below.</span></span>    


## <a name="sip-signaling-fqdns"></a><span data-ttu-id="99984-200">Sinalização SIP: FQDNs</span><span class="sxs-lookup"><span data-stu-id="99984-200">SIP Signaling: FQDNs</span></span>

<span data-ttu-id="99984-201">Para sinalização SIP, os requisitos de FQDN e de firewall são iguais aos dos casos sem bypass.</span><span class="sxs-lookup"><span data-stu-id="99984-201">For SIP signaling, the FQDN and firewall requirements are the same as for non-bypassed cases.</span></span> 

<span data-ttu-id="99984-202">O roteamento direto é oferecido nos seguintes ambientes do Office 365:</span><span class="sxs-lookup"><span data-stu-id="99984-202">Direct Routing is offered in the following Office 365 environments:</span></span>
- <span data-ttu-id="99984-203">Office 365</span><span class="sxs-lookup"><span data-stu-id="99984-203">Office 365</span></span>
- <span data-ttu-id="99984-204">Office 365 GCC</span><span class="sxs-lookup"><span data-stu-id="99984-204">Office 365 GCC</span></span>
- <span data-ttu-id="99984-205">Office 365 GCC High</span><span class="sxs-lookup"><span data-stu-id="99984-205">Office 365 GCC High</span></span>
- <span data-ttu-id="99984-206">Office 365 DoD saiba mais sobre os [ambientes do office 365 e do governo dos EUA](https://docs.microsoft.com/office365/servicedescriptions/office-365-platform-service-description/office-365-us-government/office-365-us-government) , como GCC, gcc High e DOD.</span><span class="sxs-lookup"><span data-stu-id="99984-206">Office 365 DoD Learn more about [Office 365 and US Government environments](https://docs.microsoft.com/office365/servicedescriptions/office-365-platform-service-description/office-365-us-government/office-365-us-government) such as GCC, GCC High, and DoD.</span></span>

### <a name="office-365-and-office-365-gcc-environments"></a><span data-ttu-id="99984-207">Ambientes do Office 365 e do Office 365 GCC</span><span class="sxs-lookup"><span data-stu-id="99984-207">Office 365 and Office 365 GCC environments</span></span>

<span data-ttu-id="99984-208">Os pontos de conexão para roteamento direto são os três FQDNs a seguir:</span><span class="sxs-lookup"><span data-stu-id="99984-208">The connection points for Direct Routing are the following three FQDNs:</span></span>

- <span data-ttu-id="99984-209">**SIP.pstnhub.Microsoft.com** – FQDN global – deve ser tentado primeiro.</span><span class="sxs-lookup"><span data-stu-id="99984-209">**sip.pstnhub.microsoft.com** – Global FQDN – must be tried first.</span></span> <span data-ttu-id="99984-210">Quando o SBC envia uma solicitação para resolver esse nome, os servidores DNS do Microsoft Azure retornam um endereço IP apontando para o datacenter principal do Azure atribuído ao SBC.</span><span class="sxs-lookup"><span data-stu-id="99984-210">When the SBC sends a request to resolve this name, the Microsoft Azure DNS servers return an IP address pointing to the primary Azure datacenter assigned to the SBC.</span></span> <span data-ttu-id="99984-211">A atribuição se baseia em métricas de desempenho dos datacenters e da proximidade geográfica com o SBC.</span><span class="sxs-lookup"><span data-stu-id="99984-211">The assignment is based on performance metrics of the datacenters and geographical proximity to the SBC.</span></span> <span data-ttu-id="99984-212">O endereço IP retornado corresponde ao FQDN primário.</span><span class="sxs-lookup"><span data-stu-id="99984-212">The IP address returned corresponds to the primary FQDN.</span></span>

- <span data-ttu-id="99984-213">**SIP2.pstnhub.Microsoft.com** – FQDN secundário – mapas geograficamente para a segunda região de prioridade.</span><span class="sxs-lookup"><span data-stu-id="99984-213">**sip2.pstnhub.microsoft.com** – Secondary FQDN – geographically maps to the second priority region.</span></span>

- <span data-ttu-id="99984-214">**sip3.pstnhub.Microsoft.com** – FQDN (FQDN) – mapas geograficamente para a terceira região de prioridade.</span><span class="sxs-lookup"><span data-stu-id="99984-214">**sip3.pstnhub.microsoft.com** – Tertiary FQDN – geographically maps to the third priority region.</span></span>

<span data-ttu-id="99984-215">Você deve colocar esses três FQDNs em ordem para:</span><span class="sxs-lookup"><span data-stu-id="99984-215">You must place these three FQDNs in order to:</span></span>

- <span data-ttu-id="99984-216">Ofereça uma experiência ideal (menos carregada e mais próxima ao datacenter SBC atribuída consultando o primeiro FQDN).</span><span class="sxs-lookup"><span data-stu-id="99984-216">Provide optimal experience (less loaded and closest to the SBC datacenter assigned by querying the first FQDN).</span></span>

- <span data-ttu-id="99984-217">Fornecer failover quando uma conexão de um SBC é estabelecida com um datacenter que está apresentando um problema temporário.</span><span class="sxs-lookup"><span data-stu-id="99984-217">Provide failover when a connection from an SBC is established to a datacenter that is experiencing a temporary issue.</span></span> <span data-ttu-id="99984-218">Para obter mais informações, consulte o mecanismo de failover abaixo.</span><span class="sxs-lookup"><span data-stu-id="99984-218">For more information, see Failover mechanism below.</span></span>


<span data-ttu-id="99984-219">Os FQDNs **SIP.pstnhub.Microsoft.com**, **SIP2.pstnhub.Microsoft.com**e **sip3.pstnhub.Microsoft.com** serão resolvidos como um dos seguintes endereços IP:</span><span class="sxs-lookup"><span data-stu-id="99984-219">The FQDNs **sip.pstnhub.microsoft.com**, **sip2.pstnhub.microsoft.com**, and **sip3.pstnhub.microsoft.com** will be resolved to one of the following IP addresses:</span></span>
- <span data-ttu-id="99984-220">52.114.148.0</span><span class="sxs-lookup"><span data-stu-id="99984-220">52.114.148.0</span></span>
- <span data-ttu-id="99984-221">52.114.132.46</span><span class="sxs-lookup"><span data-stu-id="99984-221">52.114.132.46</span></span>
- <span data-ttu-id="99984-222">52.114.75.24</span><span class="sxs-lookup"><span data-stu-id="99984-222">52.114.75.24</span></span>
- <span data-ttu-id="99984-223">52.114.76.76</span><span class="sxs-lookup"><span data-stu-id="99984-223">52.114.76.76</span></span>
- <span data-ttu-id="99984-224">52.114.7.24</span><span class="sxs-lookup"><span data-stu-id="99984-224">52.114.7.24</span></span>
- <span data-ttu-id="99984-225">52.114.14.70</span><span class="sxs-lookup"><span data-stu-id="99984-225">52.114.14.70</span></span>

<span data-ttu-id="99984-226">Você precisa abrir portas para todos esses endereços IP no seu firewall para permitir o recebimento e o tráfego de entrada e saída dos endereços para sinalização.</span><span class="sxs-lookup"><span data-stu-id="99984-226">You need to open ports for all these IP addresses in your firewall to allow incoming and outgoing traffic to and from the addresses for signaling.</span></span> <span data-ttu-id="99984-227">Se o seu firewall der suporte a nomes DNS, a **SIP-ALL.PSTNHUB.Microsoft.com** FQDN será resolvida para todos esses endereços IP.</span><span class="sxs-lookup"><span data-stu-id="99984-227">If your firewall supports DNS names, the FQDN **sip-all.pstnhub.microsoft.com** resolves to all these IP addresses.</span></span> 

### <a name="office-365-gcc-dod-environment"></a><span data-ttu-id="99984-228">Ambiente do Office 365 GCC DoD</span><span class="sxs-lookup"><span data-stu-id="99984-228">Office 365 GCC DoD environment</span></span>

<span data-ttu-id="99984-229">O ponto de conexão para roteamento direto é o seguinte FQDN:</span><span class="sxs-lookup"><span data-stu-id="99984-229">The connection point for Direct Routing is the following FQDN:</span></span>

<span data-ttu-id="99984-230">**SIP.pstnhub.DoD.Teams.Microsoft.us** – FQDN global.</span><span class="sxs-lookup"><span data-stu-id="99984-230">**sip.pstnhub.dod.teams.microsoft.us** – Global FQDN.</span></span> <span data-ttu-id="99984-231">Como o ambiente DoD do Office 365 existe somente nos data centers dos EUA, não há FQDNs secundários e terciários.</span><span class="sxs-lookup"><span data-stu-id="99984-231">As the Office 365 DoD environment exists only in the US data centers, there is no secondary and tertiary FQDNs.</span></span>

<span data-ttu-id="99984-232">Os FQDNs – sip.pstnhub.dod.teams.microsoft.us serão resolvidos para um dos seguintes endereços IP:</span><span class="sxs-lookup"><span data-stu-id="99984-232">The FQDNs – sip.pstnhub.dod.teams.microsoft.us will be resolved to one of the following IP addresses:</span></span>

- <span data-ttu-id="99984-233">52.127.64.33</span><span class="sxs-lookup"><span data-stu-id="99984-233">52.127.64.33</span></span>
- <span data-ttu-id="99984-234">52.127.68.34</span><span class="sxs-lookup"><span data-stu-id="99984-234">52.127.68.34</span></span>

<span data-ttu-id="99984-235">Você precisa abrir portas para todos esses endereços IP no seu firewall para permitir o recebimento e o tráfego de entrada e saída dos endereços para sinalização.</span><span class="sxs-lookup"><span data-stu-id="99984-235">You need to open ports for all these IP addresses in your firewall to allow incoming and outgoing traffic to and from the addresses for signaling.</span></span>  <span data-ttu-id="99984-236">Se o seu firewall der suporte a nomes DNS, a sip.pstnhub.dod.teams.microsoft.us FQDN será resolvida para todos esses endereços IP.</span><span class="sxs-lookup"><span data-stu-id="99984-236">If your firewall supports DNS names, the FQDN  sip.pstnhub.dod.teams.microsoft.us resolves to all these IP addresses.</span></span> 

### <a name="office-365-gcc-high-environment"></a><span data-ttu-id="99984-237">Ambiente High do Office 365 GCC</span><span class="sxs-lookup"><span data-stu-id="99984-237">Office 365 GCC High environment</span></span>

<span data-ttu-id="99984-238">O ponto de conexão para roteamento direto é o seguinte FQDN:</span><span class="sxs-lookup"><span data-stu-id="99984-238">The connection point for Direct Routing is the following FQDN:</span></span>

<span data-ttu-id="99984-239">**SIP.pstnhub.gov.Teams.Microsoft.us** – FQDN global.</span><span class="sxs-lookup"><span data-stu-id="99984-239">**sip.pstnhub.gov.teams.microsoft.us** – Global FQDN.</span></span> <span data-ttu-id="99984-240">Como o ambiente High GCC existe apenas nos data centers dos EUA, não há FQDNs secundários e terciários.</span><span class="sxs-lookup"><span data-stu-id="99984-240">As the GCC High environment exists only in the US data centers, there is no secondary and tertiary FQDNs.</span></span>

<span data-ttu-id="99984-241">Os FQDNs – sip.pstnhub.gov.teams.microsoft.us serão resolvidos para um dos seguintes endereços IP:</span><span class="sxs-lookup"><span data-stu-id="99984-241">The FQDNs – sip.pstnhub.gov.teams.microsoft.us will be resolved to one of the following IP addresses:</span></span>

- <span data-ttu-id="99984-242">52.127.88.59</span><span class="sxs-lookup"><span data-stu-id="99984-242">52.127.88.59</span></span>
- <span data-ttu-id="99984-243">52.127.92.64</span><span class="sxs-lookup"><span data-stu-id="99984-243">52.127.92.64</span></span>

<span data-ttu-id="99984-244">Você precisa abrir portas para todos esses endereços IP no seu firewall para permitir o recebimento e o tráfego de entrada e saída dos endereços para sinalização.</span><span class="sxs-lookup"><span data-stu-id="99984-244">You need to open ports for all these IP addresses in your firewall to allow incoming and outgoing traffic to and from the addresses for signaling.</span></span>  <span data-ttu-id="99984-245">Se o seu firewall der suporte a nomes DNS, a sip.pstnhub.gov.teams.microsoft.us FQDN será resolvida para todos esses endereços IP.</span><span class="sxs-lookup"><span data-stu-id="99984-245">If your firewall supports DNS names, the FQDN  sip.pstnhub.gov.teams.microsoft.us resolves to all these IP addresses.</span></span> 

## <a name="sip-signaling-ports"></a><span data-ttu-id="99984-246">Sinalização SIP: portas</span><span class="sxs-lookup"><span data-stu-id="99984-246">SIP Signaling: Ports</span></span>

<span data-ttu-id="99984-247">Os requisitos de porta são iguais para todos os ambientes do Office 365 em que o roteamento direto é oferecido:</span><span class="sxs-lookup"><span data-stu-id="99984-247">Port requirements are the same for all Office 365 environments where Direct Routing is offered:</span></span>
- <span data-ttu-id="99984-248">Office 365</span><span class="sxs-lookup"><span data-stu-id="99984-248">Office 365</span></span>
- <span data-ttu-id="99984-249">Office 365 GCC</span><span class="sxs-lookup"><span data-stu-id="99984-249">Office 365 GCC</span></span>
- <span data-ttu-id="99984-250">Office 365 GCC High</span><span class="sxs-lookup"><span data-stu-id="99984-250">Office 365 GCC High</span></span>
- <span data-ttu-id="99984-251">Office 365 DoD</span><span class="sxs-lookup"><span data-stu-id="99984-251">Office 365 DoD</span></span>

<span data-ttu-id="99984-252">Você deve usar as seguintes portas:</span><span class="sxs-lookup"><span data-stu-id="99984-252">You must use the following ports:</span></span>

| <span data-ttu-id="99984-253">Traffic</span><span class="sxs-lookup"><span data-stu-id="99984-253">Traffic</span></span> | <span data-ttu-id="99984-254">De</span><span class="sxs-lookup"><span data-stu-id="99984-254">From</span></span> | <span data-ttu-id="99984-255">Até</span><span class="sxs-lookup"><span data-stu-id="99984-255">To</span></span> | <span data-ttu-id="99984-256">Porta de origem</span><span class="sxs-lookup"><span data-stu-id="99984-256">Source port</span></span> | <span data-ttu-id="99984-257">Porta de destino</span><span class="sxs-lookup"><span data-stu-id="99984-257">Destination port</span></span>|
| :-------- | :-------- |:-----------|:--------|:---------|
<span data-ttu-id="99984-258">SIP/TLS</span><span class="sxs-lookup"><span data-stu-id="99984-258">SIP/TLS</span></span>| <span data-ttu-id="99984-259">Proxy SIP</span><span class="sxs-lookup"><span data-stu-id="99984-259">SIP Proxy</span></span> | <span data-ttu-id="99984-260">SBC</span><span class="sxs-lookup"><span data-stu-id="99984-260">SBC</span></span> | <span data-ttu-id="99984-261">1024-65535</span><span class="sxs-lookup"><span data-stu-id="99984-261">1024 - 65535</span></span> | <span data-ttu-id="99984-262">Definido no SBC</span><span class="sxs-lookup"><span data-stu-id="99984-262">Defined on the SBC</span></span> |
| <span data-ttu-id="99984-263">SIP/TLS</span><span class="sxs-lookup"><span data-stu-id="99984-263">SIP/TLS</span></span> | <span data-ttu-id="99984-264">SBC</span><span class="sxs-lookup"><span data-stu-id="99984-264">SBC</span></span> | <span data-ttu-id="99984-265">Proxy SIP</span><span class="sxs-lookup"><span data-stu-id="99984-265">SIP Proxy</span></span> | <span data-ttu-id="99984-266">Definido no SBC</span><span class="sxs-lookup"><span data-stu-id="99984-266">Defined on the SBC</span></span> | <span data-ttu-id="99984-267">5061</span><span class="sxs-lookup"><span data-stu-id="99984-267">5061</span></span> |


## <a name="media-traffic-ip-and-port-ranges"></a><span data-ttu-id="99984-268">Tráfego de mídia: intervalos IP e de porta</span><span class="sxs-lookup"><span data-stu-id="99984-268">Media traffic: IP and Port ranges</span></span>

<span data-ttu-id="99984-269">O tráfego de mídia flui entre o cliente do SBC e do teams se a conectividade direta estiver disponível ou por meio das retransmissões de transporte do teams se o cliente não puder alcançar o SBC usando o endereço IP público.</span><span class="sxs-lookup"><span data-stu-id="99984-269">Media traffic flows between the SBC and Teams client if direct connectivity is available or via Teams Transport Relays if the client cannot reach the SBC using the public IP address.</span></span>

### <a name="requirements-for-direct-media-traffic-between-the-teams-client-and-the-sbc"></a><span data-ttu-id="99984-270">Requisitos para tráfego direto de mídia (entre o cliente de equipes e o SBC)</span><span class="sxs-lookup"><span data-stu-id="99984-270">Requirements for direct media traffic (between the Teams client and the SBC)</span></span> 

<span data-ttu-id="99984-271">O cliente deve ter acesso às portas especificadas (consulte Table) no endereço IP público do SBC.</span><span class="sxs-lookup"><span data-stu-id="99984-271">The client must have access to the specified ports (see table) on the public IP address of the SBC.</span></span> 

<span data-ttu-id="99984-272">Observação: se o cliente estiver em uma rede interna, a mídia flui para o endereço IP público do SBC.</span><span class="sxs-lookup"><span data-stu-id="99984-272">Note: If the client is in an internal network, the media flows to the public IP address of the SBC.</span></span> <span data-ttu-id="99984-273">Você pode configurar a fixação de cabelo em seu dispositivo NAT para que o tráfego nunca saia do equipamento de rede da empresa.</span><span class="sxs-lookup"><span data-stu-id="99984-273">You can configure hair pinning on your NAT device so traffic never leaves the enterprise network equipment.</span></span>

| <span data-ttu-id="99984-274">Traffic</span><span class="sxs-lookup"><span data-stu-id="99984-274">Traffic</span></span> | <span data-ttu-id="99984-275">De</span><span class="sxs-lookup"><span data-stu-id="99984-275">From</span></span> | <span data-ttu-id="99984-276">Até</span><span class="sxs-lookup"><span data-stu-id="99984-276">To</span></span> | <span data-ttu-id="99984-277">Porta de origem</span><span class="sxs-lookup"><span data-stu-id="99984-277">Source port</span></span> | <span data-ttu-id="99984-278">Porta de destino</span><span class="sxs-lookup"><span data-stu-id="99984-278">Destination port</span></span>|
| :-------- | :-------- |:-----------|:--------|:---------|
<span data-ttu-id="99984-279">UDP/SRTP</span><span class="sxs-lookup"><span data-stu-id="99984-279">UDP/SRTP</span></span> | <span data-ttu-id="99984-280">Cliente</span><span class="sxs-lookup"><span data-stu-id="99984-280">Client</span></span> | <span data-ttu-id="99984-281">SBC</span><span class="sxs-lookup"><span data-stu-id="99984-281">SBC</span></span> | <span data-ttu-id="99984-282">50 000 – 50 019</span><span class="sxs-lookup"><span data-stu-id="99984-282">50 000 – 50 019</span></span>  | <span data-ttu-id="99984-283">Definido no SBC</span><span class="sxs-lookup"><span data-stu-id="99984-283">Defined on the SBC</span></span> |
| <span data-ttu-id="99984-284">UDP/SRTP</span><span class="sxs-lookup"><span data-stu-id="99984-284">UDP/SRTP</span></span> | <span data-ttu-id="99984-285">SBC</span><span class="sxs-lookup"><span data-stu-id="99984-285">SBC</span></span> | <span data-ttu-id="99984-286">Cliente</span><span class="sxs-lookup"><span data-stu-id="99984-286">Client</span></span> | <span data-ttu-id="99984-287">Definido no SBC</span><span class="sxs-lookup"><span data-stu-id="99984-287">Defined on the SBC</span></span> | <span data-ttu-id="99984-288">50 000 – 50 019</span><span class="sxs-lookup"><span data-stu-id="99984-288">50 000 – 50 019</span></span>  |


<span data-ttu-id="99984-289">Observação: se você tiver um dispositivo de rede que traduz as portas de origem do cliente, certifique-se de que as portas convertidas sejam abertas entre o equipamento de rede e o SBC.</span><span class="sxs-lookup"><span data-stu-id="99984-289">Note: If you have a network device that translates the client's source ports, please make sure that translated ports are opened between the network equipment and the SBC.</span></span> 

### <a name="requirements-for-using-transport-relays"></a><span data-ttu-id="99984-290">Requisitos para usar retransmissões de transporte</span><span class="sxs-lookup"><span data-stu-id="99984-290">Requirements for using Transport Relays</span></span>

<span data-ttu-id="99984-291">As retransmissões de transporte estão no mesmo intervalo dos processadores de mídia (para casos que não podem ser ignorados):</span><span class="sxs-lookup"><span data-stu-id="99984-291">Transport Relays are in the same range as Media Processors (for non-bypass cases):</span></span> 

### <a name="office-365-and-office-365-gcc-environments"></a><span data-ttu-id="99984-292">Ambientes do Office 365 e do Office 365 GCC</span><span class="sxs-lookup"><span data-stu-id="99984-292">Office 365 and Office 365 GCC environments</span></span>

<span data-ttu-id="99984-293">-52.112.0.0/14 (endereços IP de 52.112.0.1 para 52.115.255.254)</span><span class="sxs-lookup"><span data-stu-id="99984-293">-52.112.0.0 /14 (IP addresses from 52.112.0.1 to 52.115.255.254)</span></span>

## <a name="office-365-gcc-dod-environment"></a><span data-ttu-id="99984-294">Ambiente do Office 365 GCC DoD</span><span class="sxs-lookup"><span data-stu-id="99984-294">Office 365 GCC DoD environment</span></span>

- <span data-ttu-id="99984-295">52.127.64.0/21</span><span class="sxs-lookup"><span data-stu-id="99984-295">52.127.64.0/21</span></span>

### <a name="office-365-gcc-high-environment"></a><span data-ttu-id="99984-296">Ambiente High do Office 365 GCC</span><span class="sxs-lookup"><span data-stu-id="99984-296">Office 365 GCC High environment</span></span>

- <span data-ttu-id="99984-297">52.127.88.0/21</span><span class="sxs-lookup"><span data-stu-id="99984-297">52.127.88.0/21</span></span>


<span data-ttu-id="99984-298">O intervalo de portas das retransmissões de transporte do Teams (aplicáveis a todos os ambientes) é mostrado na tabela a seguir:</span><span class="sxs-lookup"><span data-stu-id="99984-298">The port range of the Teams Transport Relays (applicable to all environments) is shown in the following table:</span></span>


| <span data-ttu-id="99984-299">Traffic</span><span class="sxs-lookup"><span data-stu-id="99984-299">Traffic</span></span> | <span data-ttu-id="99984-300">De</span><span class="sxs-lookup"><span data-stu-id="99984-300">From</span></span> | <span data-ttu-id="99984-301">Até</span><span class="sxs-lookup"><span data-stu-id="99984-301">To</span></span> | <span data-ttu-id="99984-302">Porta de origem</span><span class="sxs-lookup"><span data-stu-id="99984-302">Source port</span></span> | <span data-ttu-id="99984-303">Porta de destino</span><span class="sxs-lookup"><span data-stu-id="99984-303">Destination port</span></span>|
| :-------- | :-------- |:-----------|:--------|:---------|
<span data-ttu-id="99984-304">UDP/SRTP</span><span class="sxs-lookup"><span data-stu-id="99984-304">UDP/SRTP</span></span> | <span data-ttu-id="99984-305">Retransmissão de transporte</span><span class="sxs-lookup"><span data-stu-id="99984-305">Transport Relay</span></span> | <span data-ttu-id="99984-306">SBC</span><span class="sxs-lookup"><span data-stu-id="99984-306">SBC</span></span> | <span data-ttu-id="99984-307">50 000-59 999</span><span class="sxs-lookup"><span data-stu-id="99984-307">50 000 -59 999</span></span>    | <span data-ttu-id="99984-308">Definido no SBC</span><span class="sxs-lookup"><span data-stu-id="99984-308">Defined on the SBC</span></span> |
| <span data-ttu-id="99984-309">UDP/SRTP</span><span class="sxs-lookup"><span data-stu-id="99984-309">UDP/SRTP</span></span> | <span data-ttu-id="99984-310">SBC</span><span class="sxs-lookup"><span data-stu-id="99984-310">SBC</span></span> | <span data-ttu-id="99984-311">Retransmissão de transporte</span><span class="sxs-lookup"><span data-stu-id="99984-311">Transport Relay</span></span> | <span data-ttu-id="99984-312">Definido no SBC</span><span class="sxs-lookup"><span data-stu-id="99984-312">Defined on the SBC</span></span> | <span data-ttu-id="99984-313">50 000 – 59 999, 3478, 3479</span><span class="sxs-lookup"><span data-stu-id="99984-313">50 000 – 59 999, 3478, 3479</span></span>     |


<span data-ttu-id="99984-314">Observação: a Microsoft recomenda pelo menos duas portas por chamada simultânea no SBC.</span><span class="sxs-lookup"><span data-stu-id="99984-314">Note: Microsoft recommends at least two ports per concurrent call on the SBC.</span></span> <span data-ttu-id="99984-315">Como a Microsoft tem duas versões de relés de transporte, é preciso o seguinte:</span><span class="sxs-lookup"><span data-stu-id="99984-315">Because Microsoft has two versions of Transport Relays, the following are required:</span></span>

- <span data-ttu-id="99984-316">v4, que só pode funcionar com o intervalo de porta 50 000 a 59 999</span><span class="sxs-lookup"><span data-stu-id="99984-316">v4, which can only work with port range 50 000 to 59 999</span></span>

- <span data-ttu-id="99984-317">V6, que funciona com as portas 3478, 3479</span><span class="sxs-lookup"><span data-stu-id="99984-317">v6, which works with ports 3478, 3479</span></span>

<span data-ttu-id="99984-318">No momento, o bypass de mídia aceita apenas a versão v4 de retransmissões de transporte.</span><span class="sxs-lookup"><span data-stu-id="99984-318">At this time, media bypass only supports v4 version of Transport Relays.</span></span> <span data-ttu-id="99984-319">Apresentaremos o suporte do V6 no futuro.</span><span class="sxs-lookup"><span data-stu-id="99984-319">We will introduce support of v6 in the future.</span></span> 

<span data-ttu-id="99984-320">Você precisa abrir as portas 3478 e 3479 para fazer a transição.</span><span class="sxs-lookup"><span data-stu-id="99984-320">You need to open ports 3478 and 3479 for transitioning.</span></span> <span data-ttu-id="99984-321">Quando a Microsoft apresentar suporte para retransmissões de transporte V6 com bypass de mídia, você não precisará reconfigurar seu equipamento de rede ou o SBCs.</span><span class="sxs-lookup"><span data-stu-id="99984-321">When Microsoft introduces support for v6 Transport Relays with Media Bypass, you will not need to reconfigure your network equipment or SBCs.</span></span> 

### <a name="requirements-for-using-media-processors"></a><span data-ttu-id="99984-322">Requisitos para usar processadores de mídia</span><span class="sxs-lookup"><span data-stu-id="99984-322">Requirements for using media processors</span></span>

<span data-ttu-id="99984-323">Processadores de mídia estão sempre no caminho de mídia para aplicativos de voz e para clientes Web (por exemplo, clientes do teams no Microsoft Edge ou Google Chrome).</span><span class="sxs-lookup"><span data-stu-id="99984-323">Media Processors are always in the media path for voice applications and for Web clients (for example, Teams clients in Edge or Google Chrome).</span></span> <span data-ttu-id="99984-324">Os requisitos são iguais aos da configuração não bypass.</span><span class="sxs-lookup"><span data-stu-id="99984-324">The requirements are the same as for non-bypass configuration.</span></span>


<span data-ttu-id="99984-325">O intervalo IP para tráfego de mídia é</span><span class="sxs-lookup"><span data-stu-id="99984-325">The IP range for media traffic is</span></span> 

### <a name="office-365-and-office-365-gcc-environments"></a><span data-ttu-id="99984-326">Ambientes do Office 365 e do Office 365 GCC</span><span class="sxs-lookup"><span data-stu-id="99984-326">Office 365 and Office 365 GCC environments</span></span>

<span data-ttu-id="99984-327">-52.112.0.0/14 (endereços IP de 52.112.0.1 para 52.115.255.254)</span><span class="sxs-lookup"><span data-stu-id="99984-327">-52.112.0.0 /14 (IP addresses from 52.112.0.1 to 52.115.255.254)</span></span>

## <a name="office-365-gcc-dod-environment"></a><span data-ttu-id="99984-328">Ambiente do Office 365 GCC DoD</span><span class="sxs-lookup"><span data-stu-id="99984-328">Office 365 GCC DoD environment</span></span>

- <span data-ttu-id="99984-329">52.127.64.0/21</span><span class="sxs-lookup"><span data-stu-id="99984-329">52.127.64.0/21</span></span>

### <a name="office-365-gcc-high-environment"></a><span data-ttu-id="99984-330">Ambiente High do Office 365 GCC</span><span class="sxs-lookup"><span data-stu-id="99984-330">Office 365 GCC High environment</span></span>

- <span data-ttu-id="99984-331">52.127.88.0/21</span><span class="sxs-lookup"><span data-stu-id="99984-331">52.127.88.0/21</span></span>

<span data-ttu-id="99984-332">O intervalo de portas dos processadores de mídia (aplicáveis a todos os ambientes) é mostrado na tabela a seguir:</span><span class="sxs-lookup"><span data-stu-id="99984-332">The port range of the Media Processors (applicable to all environments) is shown in the following table:</span></span>

| <span data-ttu-id="99984-333">Traffic</span><span class="sxs-lookup"><span data-stu-id="99984-333">Traffic</span></span> | <span data-ttu-id="99984-334">De</span><span class="sxs-lookup"><span data-stu-id="99984-334">From</span></span> | <span data-ttu-id="99984-335">Até</span><span class="sxs-lookup"><span data-stu-id="99984-335">To</span></span> | <span data-ttu-id="99984-336">Porta de origem</span><span class="sxs-lookup"><span data-stu-id="99984-336">Source port</span></span> | <span data-ttu-id="99984-337">Porta de destino</span><span class="sxs-lookup"><span data-stu-id="99984-337">Destination port</span></span>|
| :-------- | :-------- |:-----------|:--------|:---------|
<span data-ttu-id="99984-338">UDP/SRTP</span><span class="sxs-lookup"><span data-stu-id="99984-338">UDP/SRTP</span></span> | <span data-ttu-id="99984-339">Processador de mídia</span><span class="sxs-lookup"><span data-stu-id="99984-339">Media Processor</span></span> | <span data-ttu-id="99984-340">SBC</span><span class="sxs-lookup"><span data-stu-id="99984-340">SBC</span></span> | <span data-ttu-id="99984-341">49 152 – 53 247</span><span class="sxs-lookup"><span data-stu-id="99984-341">49 152 – 53 247</span></span>    | <span data-ttu-id="99984-342">Definido no SBC</span><span class="sxs-lookup"><span data-stu-id="99984-342">Defined on the SBC</span></span> |
| <span data-ttu-id="99984-343">UDP/SRTP</span><span class="sxs-lookup"><span data-stu-id="99984-343">UDP/SRTP</span></span> | <span data-ttu-id="99984-344">SBC</span><span class="sxs-lookup"><span data-stu-id="99984-344">SBC</span></span> | <span data-ttu-id="99984-345">Processador de mídia</span><span class="sxs-lookup"><span data-stu-id="99984-345">Media Processor</span></span> | <span data-ttu-id="99984-346">Definido no SBC</span><span class="sxs-lookup"><span data-stu-id="99984-346">Defined on the SBC</span></span> | <span data-ttu-id="99984-347">49 152 – 53 247</span><span class="sxs-lookup"><span data-stu-id="99984-347">49 152 – 53 247</span></span>     |

## <a name="configure-separate-trunks-for-media-bypass-and-non-media-bypass"></a><span data-ttu-id="99984-348">Configurar troncos separados para ignorar a mídia e ignorar não relacionadas à mídia</span><span class="sxs-lookup"><span data-stu-id="99984-348">Configure separate trunks for media bypass and non-media bypass</span></span>  

<span data-ttu-id="99984-349">Se você estiver migrando para o bypass de mídia do bypass não relacionado à mídia e quiser confirmar a funcionalidade antes de migrar todo o uso para o bypass de mídia, você pode criar um tronco separado e uma política de roteamento de voz online separada para direcionar o tronco bypass de mídia e atribuir a usuários específicos.</span><span class="sxs-lookup"><span data-stu-id="99984-349">If you are migrating to media bypass from non-media bypass and want to confirm functionality before migrating all usage to media bypass, you can create a separate trunk and separate Online Voice Routing policy to route to the media bypass trunk and assign to specific users.</span></span> 

<span data-ttu-id="99984-350">Etapas de configuração de alto nível:</span><span class="sxs-lookup"><span data-stu-id="99984-350">High-level configuration steps:</span></span>

- <span data-ttu-id="99984-351">Identifique os usuários para testar o bypass de mídia.</span><span class="sxs-lookup"><span data-stu-id="99984-351">Identify users to test media bypass.</span></span>

- <span data-ttu-id="99984-352">Crie dois troncos separados com FQDNs diferentes: um habilitado para bypass de mídia; o outro não.</span><span class="sxs-lookup"><span data-stu-id="99984-352">Create two separate trunks with different FQDNs: one enabled for media bypass; the other not.</span></span> 

  <span data-ttu-id="99984-353">Ambos os troncos apontam para o mesmo SBC.</span><span class="sxs-lookup"><span data-stu-id="99984-353">Both trunks point to the same SBC.</span></span> <span data-ttu-id="99984-354">As portas para sinalização SIP TLS devem ser diferentes.</span><span class="sxs-lookup"><span data-stu-id="99984-354">The ports for TLS SIP signaling must be different.</span></span> <span data-ttu-id="99984-355">As portas para mídia devem ser iguais.</span><span class="sxs-lookup"><span data-stu-id="99984-355">The ports for media must be the same.</span></span>

- <span data-ttu-id="99984-356">Crie uma nova política de roteamento de voz online e atribua o tronco bypass de mídia às rotas correspondentes associadas ao uso de PSTN para esta política.</span><span class="sxs-lookup"><span data-stu-id="99984-356">Create a new Online Voice Routing policy and assign the media bypass trunk to the corresponding routes associated with the PSTN usage for this policy.</span></span>

- <span data-ttu-id="99984-357">Atribua a nova política de roteamento de voz online aos usuários que você identificou para testar o bypass de mídia.</span><span class="sxs-lookup"><span data-stu-id="99984-357">Assign the new Online Voice Routing policy to users you have identified to test media bypass.</span></span>

<span data-ttu-id="99984-358">O exemplo a seguir ilustra essa lógica.</span><span class="sxs-lookup"><span data-stu-id="99984-358">The example below illustrates this logic.</span></span>

| <span data-ttu-id="99984-359">Conjunto de usuários</span><span class="sxs-lookup"><span data-stu-id="99984-359">Set of users</span></span> | <span data-ttu-id="99984-360">Número de usuários</span><span class="sxs-lookup"><span data-stu-id="99984-360">Number of users</span></span> | <span data-ttu-id="99984-361">FQDN de tronco atribuído no OVRP</span><span class="sxs-lookup"><span data-stu-id="99984-361">Trunk FQDN assigned in OVRP</span></span> | <span data-ttu-id="99984-362">Bypass de mídia habilitado</span><span class="sxs-lookup"><span data-stu-id="99984-362">Media bypass enabled</span></span> |
| :------------ |:----------------- |:--------------|:--------------|
<span data-ttu-id="99984-363">Usuários com tronco bypass sem mídia</span><span class="sxs-lookup"><span data-stu-id="99984-363">Users with non-media bypass trunk</span></span> | <span data-ttu-id="99984-364">980</span><span class="sxs-lookup"><span data-stu-id="99984-364">980</span></span> | <span data-ttu-id="99984-365">sbc1.contoso.com:5060</span><span class="sxs-lookup"><span data-stu-id="99984-365">sbc1.contoso.com:5060</span></span> | <span data-ttu-id="99984-366">verdadeiro</span><span class="sxs-lookup"><span data-stu-id="99984-366">true</span></span>
<span data-ttu-id="99984-367">Usuários com tronco de bypass de mídia</span><span class="sxs-lookup"><span data-stu-id="99984-367">Users with media bypass trunk</span></span> | <span data-ttu-id="99984-368">cedido</span><span class="sxs-lookup"><span data-stu-id="99984-368">20</span></span> | <span data-ttu-id="99984-369">sbc2.contoso.com:5061</span><span class="sxs-lookup"><span data-stu-id="99984-369">sbc2.contoso.com:5061</span></span> | <span data-ttu-id="99984-370">falsas</span><span class="sxs-lookup"><span data-stu-id="99984-370">false</span></span> | 

<span data-ttu-id="99984-371">Os dois troncos podem apontar para o mesmo SBC com o mesmo endereço IP público.</span><span class="sxs-lookup"><span data-stu-id="99984-371">Both trunks can point to the same SBC with the same public IP address.</span></span> <span data-ttu-id="99984-372">As portas de sinalização TLS no SBC devem ser diferentes, conforme mostrado no diagrama a seguir.</span><span class="sxs-lookup"><span data-stu-id="99984-372">The TLS signaling ports on the SBC must be different, as shown in the following diagram.</span></span> <span data-ttu-id="99984-373">Observação Você precisará verificar se o seu certificado dá suporte a ambos troncos.</span><span class="sxs-lookup"><span data-stu-id="99984-373">Note you will need to make sure that your certificate supports both trunks.</span></span> <span data-ttu-id="99984-374">Na SAN, você precisa ter dois nomes (**sbc1.contoso.com** e **sbc2.contoso.com**) ou ter um certificado curinga.</span><span class="sxs-lookup"><span data-stu-id="99984-374">In SAN, you need to have two names (**sbc1.contoso.com** and **sbc2.contoso.com**) or have a wildcard certificate.</span></span>


![Mostra que os dois troncos podem apontar para o mesmo SBC com o mesmo IP público](media/direct-routing-media-bypass-7.png)

<span data-ttu-id="99984-376">Para obter informações sobre como configurar dois troncos no mesmo SBC, consulte a documentação fornecida pelo seu fornecedor de SBC:</span><span class="sxs-lookup"><span data-stu-id="99984-376">For information about how to configure two trunks on the same SBC, see the documentation provided by your SBC vendor:</span></span>

 - [<span data-ttu-id="99984-377">Documentação de implantação do AudioCodes</span><span class="sxs-lookup"><span data-stu-id="99984-377">AudioCodes deployment documentation</span></span>](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/direct-routing-for-microsoft-teams)
- [<span data-ttu-id="99984-378">Documentação de implantação do Oracle</span><span class="sxs-lookup"><span data-stu-id="99984-378">Oracle deployment documentation</span></span>](https://www.oracle.com/industries/communications/enterprise-session-border-controller/microsoft.html)
- [<span data-ttu-id="99984-379">Documentação da implantação de comunicações da faixa de opções</span><span class="sxs-lookup"><span data-stu-id="99984-379">Ribbon Communications deployment documentation</span></span>](https://ribboncommunications.com/solutions/enterprise-solutions/microsoft-solutions/direct-routing-microsoft-teams-calling)
- [<span data-ttu-id="99984-380">Documentação de implantação do anynode (File-Systems)</span><span class="sxs-lookup"><span data-stu-id="99984-380">TE-Systems (anynode) deployment documentation</span></span>](https://www.anynode.de/anynode-and-microsoft-teams/)

## <a name="client-endpoints-supported-with-media-bypass"></a><span data-ttu-id="99984-381">Pontos de extremidade do cliente com suporte com bypass de mídia</span><span class="sxs-lookup"><span data-stu-id="99984-381">Client endpoints supported with media bypass</span></span>

<span data-ttu-id="99984-382">O bypass de mídia é compatível com todos os clientes de desktop de equipe e dispositivos telefônicos de equipe.</span><span class="sxs-lookup"><span data-stu-id="99984-382">Media bypass is supported with all Teams Desktop clients and Teams Phone Devices.</span></span> 

<span data-ttu-id="99984-383">Para todos os outros pontos de extremidade que não são compatíveis com o bypass de mídia, veremos a chamada para non-bypass, mesmo que ele tenha começado como uma chamada de bypass.</span><span class="sxs-lookup"><span data-stu-id="99984-383">For all other endpoints that do not support media bypass, we will covert the call to non-bypass even if it started as a bypass call.</span></span> <span data-ttu-id="99984-384">Isso acontece automaticamente e não requer nenhuma ação do administrador.</span><span class="sxs-lookup"><span data-stu-id="99984-384">This happens automatically and does not require any actions from the administrator.</span></span> <span data-ttu-id="99984-385">Isso inclui os telefones do Skype for Business 3PIP e os clientes Web do teams que dão suporte a chamadas de roteamento direto (novo Microsoft Edge baseado no Chromium, Google Chrome, Mozilla Firefox).</span><span class="sxs-lookup"><span data-stu-id="99984-385">This includes Skype for Business 3PIP Phones, and Teams Web Clients that support Direct Routing calling (New Microsoft Edge based on Chromium, Google Chrome, Mozilla Firefox).</span></span> 
 
## <a name="see-also"></a><span data-ttu-id="99984-386">Confira também</span><span class="sxs-lookup"><span data-stu-id="99984-386">See also</span></span>

[<span data-ttu-id="99984-387">Configurar o bypass de mídia com Roteamento Direto</span><span class="sxs-lookup"><span data-stu-id="99984-387">Configure media bypass with Direct Routing</span></span>](direct-routing-configure-media-bypass.md)



