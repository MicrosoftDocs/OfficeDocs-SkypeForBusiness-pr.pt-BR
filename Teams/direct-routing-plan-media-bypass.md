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
description: Saiba como planejar o bypass de mídia com Sistema de Telefonia Roteamento Direto, que permite reduzir o caminho do tráfego de mídia e melhorar o desempenho.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 4978c7ce2a69f23164a3869dd69368b3aaad2c4e
ms.sourcegitcommit: 50ec59b454e751d952cde9fd13c8017529d0e1d6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/13/2021
ms.locfileid: "52469623"
---
# <a name="plan-for-media-bypass-with-direct-routing"></a><span data-ttu-id="645f8-103">Planejar o bypass de mídia com Roteamento Direto</span><span class="sxs-lookup"><span data-stu-id="645f8-103">Plan for media bypass with Direct Routing</span></span>

## <a name="about-media-bypass-with-direct-routing"></a><span data-ttu-id="645f8-104">Sobre desvio de mídia com Roteamento Direto</span><span class="sxs-lookup"><span data-stu-id="645f8-104">About media bypass with Direct Routing</span></span>

<span data-ttu-id="645f8-105">O bypass de mídia permite reduzir o caminho do tráfego de mídia e reduzir o número de saltos em trânsito para melhorar o desempenho.</span><span class="sxs-lookup"><span data-stu-id="645f8-105">Media bypass enables you to shorten the path of media traffic and reduce the number of hops in transit for better performance.</span></span> <span data-ttu-id="645f8-106">Com o bypass de mídia, a mídia é mantida entre o Controlador de Borda de Sessão (SBC) e o cliente, em vez de enviá-lo por meio do Telefone Microsoft System.</span><span class="sxs-lookup"><span data-stu-id="645f8-106">With media bypass, media is kept between the Session Border Controller (SBC) and the client instead of sending it via the Microsoft Phone System.</span></span> <span data-ttu-id="645f8-107">Para configurar o bypass de mídia, o SBC e o cliente devem estar no mesmo local ou rede.</span><span class="sxs-lookup"><span data-stu-id="645f8-107">To configure media bypass, the SBC and the client must be in the same location or network.</span></span>

<span data-ttu-id="645f8-108">Você pode controlar o bypass de mídia para cada SBC usando o comando **Set-CSOnlinePSTNGateway** com o parâmetro **-MediaBypass** definido como true ou false.</span><span class="sxs-lookup"><span data-stu-id="645f8-108">You can control media bypass for each SBC by using the **Set-CSOnlinePSTNGateway** command with the **-MediaBypass** parameter set to true or false.</span></span> <span data-ttu-id="645f8-109">Se você habilitar o bypass de mídia, isso não significa que todo o tráfego de mídia ficará dentro da rede corporativa.</span><span class="sxs-lookup"><span data-stu-id="645f8-109">If you enable media bypass, this does not mean that all media traffic will stay within the corporate network.</span></span> <span data-ttu-id="645f8-110">Este artigo descreve o fluxo de chamada em diferentes cenários.</span><span class="sxs-lookup"><span data-stu-id="645f8-110">This article describes the call flow in different scenarios.</span></span>

<span data-ttu-id="645f8-111">Os diagramas a seguir ilustram a diferença no fluxo de chamada com e sem bypass de mídia.</span><span class="sxs-lookup"><span data-stu-id="645f8-111">The diagrams below illustrate the difference in call flow with and without media bypass.</span></span>

<span data-ttu-id="645f8-112">Sem bypass de mídia, quando um cliente faz ou recebe uma chamada, a sinalização e o fluxo de mídia entre o SBC, o sistema Telefone Microsoft e o cliente Teams, conforme mostrado no diagrama a seguir:</span><span class="sxs-lookup"><span data-stu-id="645f8-112">Without media bypass, when a client makes or receives a call, both signaling and media flow between the SBC, the Microsoft Phone System, and the Teams client, as shown in the following diagram:</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="645f8-113">![Mostra sinalização e fluxo de mídia sem bypass de mídia](media/direct-routing-media-bypass-1.png)</span><span class="sxs-lookup"><span data-stu-id="645f8-113">![Shows signaling and media flow without media bypass](media/direct-routing-media-bypass-1.png)</span></span>


<span data-ttu-id="645f8-114">Mas vamos supor que um usuário está no mesmo edifício ou rede que o SBC.</span><span class="sxs-lookup"><span data-stu-id="645f8-114">But let's assume that a user is in the same building or network as the SBC.</span></span> <span data-ttu-id="645f8-115">Por exemplo, suponha que um usuário que está em um edifício em Frankfurt faça uma chamada para um usuário PSTN:</span><span class="sxs-lookup"><span data-stu-id="645f8-115">For example, assume a user who is in a building in Frankfurt makes a call to a PSTN user:</span></span> 

- <span data-ttu-id="645f8-116">**Sem o bypass de** mídia, a mídia fluirá por Meio de Amsterdã ou Dublin (onde os datacenters da Microsoft são implantados) e de volta para o SBC em Frankfurt.</span><span class="sxs-lookup"><span data-stu-id="645f8-116">**Without media bypass**, media will flow via either Amsterdam or Dublin (where Microsoft datacenters are deployed) and back to the SBC in Frankfurt.</span></span> 

  <span data-ttu-id="645f8-117">O datacenter na Europa é selecionado porque o SBC está na Europa e a Microsoft usa o datacenter mais próximo do SBC.</span><span class="sxs-lookup"><span data-stu-id="645f8-117">The datacenter in Europe is selected because the SBC is in Europe, and Microsoft uses the datacenter closest to the SBC.</span></span> <span data-ttu-id="645f8-118">Embora essa abordagem não afete a qualidade das chamada devido à otimização do fluxo de tráfego nas redes da Microsoft na maioria das regiões geográficas, o tráfego tem um loop desnecessário.</span><span class="sxs-lookup"><span data-stu-id="645f8-118">While this approach does not affect call quality due to optimization of traffic flow within Microsoft networks in most geographies, the traffic has an unnecessary loop.</span></span>     

- <span data-ttu-id="645f8-119">**Com o bypass de** mídia, a mídia é mantida diretamente entre o usuário Teams e o SBC, conforme mostrado no diagrama a seguir:</span><span class="sxs-lookup"><span data-stu-id="645f8-119">**With media bypass**, the media is kept directly between the Teams user and the SBC as shown in the following diagram:</span></span>

  > [!div class="mx-imgBorder"]
  > <span data-ttu-id="645f8-120">![Mostra sinalização e fluxo de mídia com bypass de mídia](media/direct-routing-media-bypass-2.png)</span><span class="sxs-lookup"><span data-stu-id="645f8-120">![Shows signaling and media flow with media bypass](media/direct-routing-media-bypass-2.png)</span></span>

<span data-ttu-id="645f8-121">O bypass de mídia aproveita protocolos chamados Desodorado Interativo de Conectividade (ICE) no cliente Teams e no ICE lite no SBC.</span><span class="sxs-lookup"><span data-stu-id="645f8-121">Media bypass leverages protocols called Interactive Connectivity Establishment (ICE) on the Teams client and ICE lite on the SBC.</span></span> <span data-ttu-id="645f8-122">Esses protocolos permitem que o Roteamento Direto use o caminho de mídia mais direto para obter a melhor qualidade.</span><span class="sxs-lookup"><span data-stu-id="645f8-122">These protocols enable Direct Routing to use the most direct media path for optimal quality.</span></span> <span data-ttu-id="645f8-123">ICE e ICE Lite são padrões WebRTC.</span><span class="sxs-lookup"><span data-stu-id="645f8-123">ICE and ICE Lite are WebRTC standards.</span></span> <span data-ttu-id="645f8-124">Para obter informações detalhadas sobre esses protocolos, consulte RFC 5245.</span><span class="sxs-lookup"><span data-stu-id="645f8-124">For detailed information about these protocols, see RFC 5245.</span></span>


## <a name="call-flow-and-firewall-planning"></a><span data-ttu-id="645f8-125">Planejamento de fluxo de chamada e firewall</span><span class="sxs-lookup"><span data-stu-id="645f8-125">Call flow and firewall planning</span></span>

<span data-ttu-id="645f8-126">O planejamento do fluxo de chamada e do firewall depende se o usuário tem acesso direto ao endereço IP público do SBC e se o usuário está dentro ou fora da rede.</span><span class="sxs-lookup"><span data-stu-id="645f8-126">Call flow and firewall planning depends on whether the user has direct access to the public IP address of the SBC, and whether the user is inside or outside of the network.</span></span>

### <a name="call-flow-if-the-user-has-direct-access-to-the-public-ip-address-of-the-sbc"></a><span data-ttu-id="645f8-127">Fluxo de chamada se o usuário tiver acesso direto ao endereço IP público do SBC</span><span class="sxs-lookup"><span data-stu-id="645f8-127">Call flow if the user has direct access to the public IP address of the SBC</span></span>

<span data-ttu-id="645f8-128">Se o usuário tiver acesso direto ao endereço IP público do SBC, o fluxo de chamada será o seguinte:</span><span class="sxs-lookup"><span data-stu-id="645f8-128">If the user has direct access to the public IP address of the SBC, the call flow is as follows:</span></span>

- <span data-ttu-id="645f8-129">Para bypass de mídia, o Teams cliente deve ter acesso ao endereço IP público do SBC, mesmo de uma rede interna.</span><span class="sxs-lookup"><span data-stu-id="645f8-129">For media bypass, the Teams client must have access to the public IP address of the SBC even from an internal network.</span></span> <span data-ttu-id="645f8-130">Se a mídia direta não for desejada, a mídia poderá fluir por meio de Retransmissão de Transporte.</span><span class="sxs-lookup"><span data-stu-id="645f8-130">If direct media is not desired, the media can flow via Transport Relays.</span></span>

- <span data-ttu-id="645f8-131">Essa é a solução recomendada quando um usuário está no mesmo edifício e/ou rede que o SBC – remova os componentes do Microsoft Cloud do caminho de mídia.</span><span class="sxs-lookup"><span data-stu-id="645f8-131">This is the recommended solution when a user is in the same building and/or network as the SBC – remove Microsoft Cloud components from the media path.</span></span>

- <span data-ttu-id="645f8-132">A sinalização sempre flui por meio da nuvem da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="645f8-132">Signaling always flows via the Microsoft cloud.</span></span>

<span data-ttu-id="645f8-133">O diagrama a seguir mostra o fluxo de chamada quando o bypass de mídia está habilitado, o cliente é interno e o cliente pode alcançar o endereço IP público do SBC (mídia direta):</span><span class="sxs-lookup"><span data-stu-id="645f8-133">The following diagram shows call flow when media bypass is enabled, the client is internal, and the client can reach the public IP address of the SBC (direct media):</span></span> 

- <span data-ttu-id="645f8-134">As setas e os valores numéricos dos caminhos estão de acordo com Microsoft Teams [fluxos de chamada](./microsoft-teams-online-call-flows.md).</span><span class="sxs-lookup"><span data-stu-id="645f8-134">The arrows and numeric values of the paths are in accordance with [Microsoft Teams call flows](./microsoft-teams-online-call-flows.md).</span></span>

- <span data-ttu-id="645f8-135">A sinalização SIP sempre tem caminhos 4 e 4' (dependendo da direção do tráfego).</span><span class="sxs-lookup"><span data-stu-id="645f8-135">The SIP signaling always takes paths 4 and 4' (depending on the direction of the traffic).</span></span> <span data-ttu-id="645f8-136">A mídia permanece local e segue o caminho 5b.</span><span class="sxs-lookup"><span data-stu-id="645f8-136">Media stays local and takes path 5b.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="645f8-137">![Mostra o fluxo de chamada com o Bypass de Mídia habilitado, o cliente é interno](media/direct-routing-media-bypass-3.png)</span><span class="sxs-lookup"><span data-stu-id="645f8-137">![Shows Call flow with Media Bypass enabled, client is internal](media/direct-routing-media-bypass-3.png)</span></span>


### <a name="call-flow-if-the-user-does-not-have-access-to-the-public-ip-address-of-the-sbc"></a><span data-ttu-id="645f8-138">Fluxo de chamada se o usuário não tiver acesso ao endereço IP público do SBC</span><span class="sxs-lookup"><span data-stu-id="645f8-138">Call flow if the user does not have access to the public IP address of the SBC</span></span>

<span data-ttu-id="645f8-139">O seguinte descreve o fluxo de chamada se o usuário não tiver acesso ao endereço IP público do SBC.</span><span class="sxs-lookup"><span data-stu-id="645f8-139">The following describes call flow if the user does not have access to the public IP address of the SBC.</span></span> 

<span data-ttu-id="645f8-140">Por exemplo, suponha que o usuário seja externo e o administrador do locatário decidiu não abrir o endereço IP público do SBC para todos na Internet, mas apenas para o Microsoft Cloud.</span><span class="sxs-lookup"><span data-stu-id="645f8-140">For example, assume the user is external, and the tenant administrator decided not to open the public IP address of the SBC to everyone in the Internet, but only to the Microsoft Cloud.</span></span> <span data-ttu-id="645f8-141">Os componentes internos do tráfego podem fluir por meio do Teams Retransmissão de Transporte.</span><span class="sxs-lookup"><span data-stu-id="645f8-141">The internal components of traffic can flow via the Teams Transport Relays.</span></span> <span data-ttu-id="645f8-142">Considere o seguinte:</span><span class="sxs-lookup"><span data-stu-id="645f8-142">Consider the following:</span></span>

- <span data-ttu-id="645f8-143">Teams Retransmissão de transporte são usadas.</span><span class="sxs-lookup"><span data-stu-id="645f8-143">Teams Transport Relays are used.</span></span>

- <span data-ttu-id="645f8-144">Para bypass de mídia, a Microsoft usa uma versão de Retransmissão de Transporte que requer a abertura de portas 50 000 a 59 999 entre retransmissão de transporte Teams e o SBC (no futuro, planejamos mover para a versão que exige portas 3478-3481).</span><span class="sxs-lookup"><span data-stu-id="645f8-144">For media bypass, Microsoft uses a version of Transport Relays that requires opening ports 50 000 to 59 999 between the Teams Transport Relays and the SBC (in the future we plan to move to the version which requires 3478-3481 ports).</span></span>


<span data-ttu-id="645f8-145">O diagrama a seguir mostra o fluxo de chamada quando o bypass de mídia está habilitado, o cliente é externo e o cliente não pode alcançar o endereço IP público do Controlador de Borda de Sessão (a mídia é retransmitida pelo Teams Transport Relay).</span><span class="sxs-lookup"><span data-stu-id="645f8-145">The following diagram shows call flow when media bypass is enabled, the client is external, and the client cannot reach the public IP address of the Session Border Controller (media is relayed by Teams Transport Relay).</span></span>

- <span data-ttu-id="645f8-146">As setas e os valores numéricos dos caminhos estão de acordo com Microsoft Teams [fluxos de chamada](./microsoft-teams-online-call-flows.md).</span><span class="sxs-lookup"><span data-stu-id="645f8-146">The arrows and numeric values of the paths are in accordance with [Microsoft Teams call flows](./microsoft-teams-online-call-flows.md).</span></span>

- <span data-ttu-id="645f8-147">A mídia é repassada pelos caminhos 3, 3', 4 e 4'</span><span class="sxs-lookup"><span data-stu-id="645f8-147">Media is relayed via paths 3, 3', 4 and 4'</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="645f8-148">![Mostra o fluxo de chamada se o usuário não tiver acesso ao IP público do SBC](media/direct-routing-media-bypass-4.png)</span><span class="sxs-lookup"><span data-stu-id="645f8-148">![Shows Call flow if user does not have access to public IP of the SBC](media/direct-routing-media-bypass-4.png)</span></span>


### <a name="call-flow-if-a-user-is-outside-the-network-and-has-access-to-the-public-ip-of-the-sbc"></a><span data-ttu-id="645f8-149">Fluxo de chamada se um usuário estiver fora da rede e tiver acesso ao IP público do SBC</span><span class="sxs-lookup"><span data-stu-id="645f8-149">Call flow if a user is outside the network and has access to the public IP of the SBC</span></span>

> [!NOTE]
> <span data-ttu-id="645f8-150">Essa não é uma configuração recomendada porque não tira proveito de Teams Retransmissão de Transporte.</span><span class="sxs-lookup"><span data-stu-id="645f8-150">This is not a recommended configuration because it does not take advantage of Teams Transport Relays.</span></span> <span data-ttu-id="645f8-151">Em vez disso, você deve considerar o cenário anterior em que o usuário não tem acesso ao endereço IP público do SBC.</span><span class="sxs-lookup"><span data-stu-id="645f8-151">Instead, you should consider the previous scenario where the user does not have access to the public IP address of the SBC.</span></span> 

<span data-ttu-id="645f8-152">O diagrama a seguir mostra o fluxo de chamada quando o bypass de mídia está habilitado, o cliente é externo e o cliente pode alcançar o endereço IP público do SBC (mídia direta).</span><span class="sxs-lookup"><span data-stu-id="645f8-152">The following diagram shows call flow when media bypass is enabled, the client is external, and the client can reach the public IP address of the SBC (direct media).</span></span>

- <span data-ttu-id="645f8-153">As setas e os valores numéricos dos caminhos estão de acordo com o artigo Microsoft Teams [fluxos de](./microsoft-teams-online-call-flows.md) chamada.</span><span class="sxs-lookup"><span data-stu-id="645f8-153">The arrows and numeric values of the paths are in accordance with the [Microsoft Teams call flows](./microsoft-teams-online-call-flows.md) article.</span></span>

- <span data-ttu-id="645f8-154">A sinalização SIP sempre tem caminhos 3 e 3' (dependendo da direção do tráfego).</span><span class="sxs-lookup"><span data-stu-id="645f8-154">The SIP signaling always takes paths 3 and 3' (depending on the direction of the traffic).</span></span> <span data-ttu-id="645f8-155">Fluxos de mídia usando o caminho 2.</span><span class="sxs-lookup"><span data-stu-id="645f8-155">Media flows using path 2.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="645f8-156">![Mostra o fluxo de chamada se o usuário não tiver acesso ao IP público do SBC](media/direct-routing-media-bypass-5.png)</span><span class="sxs-lookup"><span data-stu-id="645f8-156">![Shows Call flow if user does not have access to public IP of the SBC](media/direct-routing-media-bypass-5.png)</span></span>


## <a name="use-of-media-processors-and-transport-relays"></a><span data-ttu-id="645f8-157">Uso de Processadores de Mídia e Retransmissão de Transporte</span><span class="sxs-lookup"><span data-stu-id="645f8-157">Use of Media Processors and Transport Relays</span></span>

<span data-ttu-id="645f8-158">Há dois componentes no Microsoft Cloud que podem estar no caminho do tráfego de mídia: Processadores de Mídia e Retransmissão de Transporte.</span><span class="sxs-lookup"><span data-stu-id="645f8-158">There are two components in the Microsoft Cloud that can be in the path of media traffic: Media Processors and Transport Relays.</span></span> 

- <span data-ttu-id="645f8-159">O Processador de Mídia é um componente voltado para o público que lida com mídia em casos que não ignoram e lida com mídia para aplicativos de voz.</span><span class="sxs-lookup"><span data-stu-id="645f8-159">The Media Processor is a public facing component that handles media in non-bypass cases and handles media for voice applications.</span></span>

   <span data-ttu-id="645f8-160">Processadores de mídia estão sempre no caminho para chamadas não ignoradas pelo usuário final, mas nunca no caminho para chamadas ignoradas.</span><span class="sxs-lookup"><span data-stu-id="645f8-160">Media Processors are always in the path for end user non-bypassed calls, but never in the path for bypassed calls.</span></span> <span data-ttu-id="645f8-161">Processadores de mídia estão sempre no caminho para todos os aplicativos de voz, como Estacionamento de Chamadas, Atendedor Automático Organizacionais e Filas de Chamadas.</span><span class="sxs-lookup"><span data-stu-id="645f8-161">Media Processors are always in the path for all voice applications such as Call Park, Organizational Auto Attendant, and Call Queues.</span></span>

- <span data-ttu-id="645f8-162">O Retransmissão de Transporte é usado para se conectar ao Serviço de Transporte mais próximo para enviar tráfego em tempo real.</span><span class="sxs-lookup"><span data-stu-id="645f8-162">The Transport Relay is used to connect to the closest Transport Service to send real time traffic.</span></span>

   <span data-ttu-id="645f8-163">Retransmissão de transporte pode ou não estar no caminho para chamadas ignoradas, originadas ou destinadas a usuários finais, dependendo de onde o usuário está e como a rede está configurada .</span><span class="sxs-lookup"><span data-stu-id="645f8-163">Transport Relays might or might not be in the path for bypassed calls--originating from or destined to end users--depending on where the user is and how the network is configured .</span></span>

<span data-ttu-id="645f8-164">O diagrama a seguir mostra dois fluxos de chamada – um com bypass de mídia habilitado e o segundo com bypass de mídia desabilitado.</span><span class="sxs-lookup"><span data-stu-id="645f8-164">The following diagram shows two call flows – one with media bypass enabled and the second with media bypass disabled.</span></span>

> [!NOTE]
> <span data-ttu-id="645f8-165">O diagrama ilustra apenas o tráfego proveniente de ou destinado a usuários finais.</span><span class="sxs-lookup"><span data-stu-id="645f8-165">The diagram only illustrates traffic originating from--or destined to--end users.</span></span>  

- <span data-ttu-id="645f8-166">O Controlador de Mídia é um microserviço no Azure que atribui processadores de mídia e cria ofertas de Protocolo de Descrição de Sessão (SDP).</span><span class="sxs-lookup"><span data-stu-id="645f8-166">The Media Controller is a microservice in Azure that assigns Media Processors and creates Session Description Protocol (SDP) offers.</span></span>

- <span data-ttu-id="645f8-167">O Proxy SIP é um componente que converte a sinalização REST HTTP usada Teams para SIP.</span><span class="sxs-lookup"><span data-stu-id="645f8-167">The SIP Proxy is a component that translates HTTP REST signaling used in Teams to SIP.</span></span>    

> [!div class="mx-imgBorder"]
> <span data-ttu-id="645f8-168">![Mostra fluxos de chamada com Bypass de Mídia habilitado e desabilitado](media/direct-routing-media-bypass-6.png)</span><span class="sxs-lookup"><span data-stu-id="645f8-168">![Shows call flows with Media Bypass enabled and disabled](media/direct-routing-media-bypass-6.png)</span></span>


<span data-ttu-id="645f8-169">A tabela a seguir resume a diferença entre Processadores de Mídia e Retransmissão de Transporte.</span><span class="sxs-lookup"><span data-stu-id="645f8-169">The table below summarizes the difference between Media Processors and Transport Relays.</span></span>

|    | <span data-ttu-id="645f8-170">Processadores de mídia</span><span class="sxs-lookup"><span data-stu-id="645f8-170">Media Processors</span></span> | <span data-ttu-id="645f8-171">Retransmissão de transporte</span><span class="sxs-lookup"><span data-stu-id="645f8-171">Transport Relays</span></span>|
| :--------------|:---------------|:------------|
<span data-ttu-id="645f8-172">No caminho de mídia para chamadas não ignoradas para usuários finais</span><span class="sxs-lookup"><span data-stu-id="645f8-172">In media path for non-bypassed calls for end users</span></span> | <span data-ttu-id="645f8-173">Always</span><span class="sxs-lookup"><span data-stu-id="645f8-173">Always</span></span> | <span data-ttu-id="645f8-174">Se o cliente não puder acessar diretamente o Processador de Mídia</span><span class="sxs-lookup"><span data-stu-id="645f8-174">If client cannot reach the Media Processor directly</span></span> | 
<span data-ttu-id="645f8-175">No caminho da mídia para chamadas ignoradas para usuários finais</span><span class="sxs-lookup"><span data-stu-id="645f8-175">In media path for bypassed calls for end users</span></span> | <span data-ttu-id="645f8-176">Never</span><span class="sxs-lookup"><span data-stu-id="645f8-176">Never</span></span> | <span data-ttu-id="645f8-177">Se o cliente não puder alcançar o SBC no endereço IP público</span><span class="sxs-lookup"><span data-stu-id="645f8-177">If client cannot reach the SBC on the public IP address</span></span> | 
<span data-ttu-id="645f8-178">No caminho de mídia para aplicativos de voz</span><span class="sxs-lookup"><span data-stu-id="645f8-178">In media path for voice applications</span></span> | <span data-ttu-id="645f8-179">Always</span><span class="sxs-lookup"><span data-stu-id="645f8-179">Always</span></span> | <span data-ttu-id="645f8-180">Never</span><span class="sxs-lookup"><span data-stu-id="645f8-180">Never</span></span> | 
<span data-ttu-id="645f8-181">Pode fazer transcodificação (B2BUA)\*</span><span class="sxs-lookup"><span data-stu-id="645f8-181">Can do transcoding (B2BUA)\*</span></span> | <span data-ttu-id="645f8-182">Sim</span><span class="sxs-lookup"><span data-stu-id="645f8-182">Yes</span></span> | <span data-ttu-id="645f8-183">Não, somente retransmite áudio entre pontos de extremidade</span><span class="sxs-lookup"><span data-stu-id="645f8-183">No, only relays audio between endpoints</span></span> | 
<span data-ttu-id="645f8-184">Número de instâncias em todo o mundo e local</span><span class="sxs-lookup"><span data-stu-id="645f8-184">Number of instances worldwide and location</span></span> | <span data-ttu-id="645f8-185">10 total: 2 nos EUA Leste e Oeste; 2 em Amsterdã e Dublin; 2 em Hong Kong e Cingapura; 2 no Japão; 2 na Austrália Leste e Sudeste</span><span class="sxs-lookup"><span data-stu-id="645f8-185">10 total: 2 in US East and West; 2 in Amsterdam and Dublin; 2 in Hong Kong and Singapore; 2 in Japan ; 2 in Australia East and Southeast</span></span> | <span data-ttu-id="645f8-186">Vários</span><span class="sxs-lookup"><span data-stu-id="645f8-186">Multiple</span></span>

<span data-ttu-id="645f8-187">Os intervalos de IP são:</span><span class="sxs-lookup"><span data-stu-id="645f8-187">The IP ranges are:</span></span>
- <span data-ttu-id="645f8-188">52.112.0.0/14 (endereços IP de 52.112.0.1 a 52.115.255.254)</span><span class="sxs-lookup"><span data-stu-id="645f8-188">52.112.0.0/14 (IP addresses from 52.112.0.1 to 52.115.255.254)</span></span>
- <span data-ttu-id="645f8-189">52.120.0.0/14 (endereços IP de 52.120.0.1 a 52.123.255.254)</span><span class="sxs-lookup"><span data-stu-id="645f8-189">52.120.0.0/14 (IP addresses from 52.120.0.1 to 52.123.255.254)</span></span>

<span data-ttu-id="645f8-190">\* Explicação de transcodificação:</span><span class="sxs-lookup"><span data-stu-id="645f8-190">\* Transcoding explanation:</span></span> 

- <span data-ttu-id="645f8-191">O Processador de Mídia é B2BUA, o que significa que ele pode alterar um codecs (por exemplo, SILK de um cliente Teams para MP e G.711 entre MP e SBC).</span><span class="sxs-lookup"><span data-stu-id="645f8-191">Media Processor is B2BUA, which means it can change a codecs (for example, SILK from Teams client to MP and G.711 between MP and SBC).</span></span>

- <span data-ttu-id="645f8-192">Retransmissão de transporte não são B2BUA, o que significa que o codec nunca é alterado entre o cliente e o SBC , mesmo que o tráfego flua por retransmissão.</span><span class="sxs-lookup"><span data-stu-id="645f8-192">Transport Relays are not B2BUA, which means the codec is never changed between the client and the SBC--even if traffic flows via relays.</span></span>

### <a name="use-of-teams-media-processors-if-trunk-is-configured-for-media-bypass"></a><span data-ttu-id="645f8-193">Uso de Teams processadores de mídia se o tronco estiver configurado para bypass de mídia</span><span class="sxs-lookup"><span data-stu-id="645f8-193">Use of Teams Media Processors if trunk is configured for media bypass</span></span>

<span data-ttu-id="645f8-194">Teams Processadores de mídia são sempre inseridos no caminho da mídia nos seguintes cenários:</span><span class="sxs-lookup"><span data-stu-id="645f8-194">Teams Media Processors are always inserted in the media path in the following scenarios:</span></span>

- <span data-ttu-id="645f8-195">A chamada é escalonada de 1:1 para uma chamada de grupo</span><span class="sxs-lookup"><span data-stu-id="645f8-195">Call is escalated from 1:1 to a group call</span></span>
- <span data-ttu-id="645f8-196">A chamada será para um usuário federado Teams usuário</span><span class="sxs-lookup"><span data-stu-id="645f8-196">Call is going to a federated Teams user</span></span>
- <span data-ttu-id="645f8-197">A chamada é encaminhada ou transferida para um Skype for Business usuário</span><span class="sxs-lookup"><span data-stu-id="645f8-197">Call is forwarded or transferred to a Skype for Business user</span></span>

<span data-ttu-id="645f8-198">Verifique se o SBC tem acesso aos intervalos processadores de mídia e retransmissão de transporte conforme descrito abaixo.</span><span class="sxs-lookup"><span data-stu-id="645f8-198">Ensure your SBC has access to the Media Processors and Transport Relays ranges as described below.</span></span>    


## <a name="sip-signaling-fqdns"></a><span data-ttu-id="645f8-199">Sinalização SIP: FQDNs</span><span class="sxs-lookup"><span data-stu-id="645f8-199">SIP Signaling: FQDNs</span></span>

<span data-ttu-id="645f8-200">Para sinalização SIP, os requisitos de FQDN e firewall são os mesmos para casos não ignorados.</span><span class="sxs-lookup"><span data-stu-id="645f8-200">For SIP signaling, the FQDN and firewall requirements are the same as for non-bypassed cases.</span></span> 

<span data-ttu-id="645f8-201">O Roteamento Direto é oferecido nos seguintes Microsoft 365 ou Office 365 ambientes:</span><span class="sxs-lookup"><span data-stu-id="645f8-201">Direct Routing is offered in the following Microsoft 365 or Office 365 environments:</span></span>
- <span data-ttu-id="645f8-202">Microsoft 365 ou Office 365</span><span class="sxs-lookup"><span data-stu-id="645f8-202">Microsoft 365 or Office 365</span></span>
- <span data-ttu-id="645f8-203">Office 365 GCC</span><span class="sxs-lookup"><span data-stu-id="645f8-203">Office 365 GCC</span></span>
- <span data-ttu-id="645f8-204">Office 365 GCC Alta</span><span class="sxs-lookup"><span data-stu-id="645f8-204">Office 365 GCC High</span></span>
- <span data-ttu-id="645f8-205">Office 365 DoD Saiba mais sobre [Office 365 e ambientes](/office365/servicedescriptions/office-365-platform-service-description/office-365-us-government/office-365-us-government) do Governo dos EUA, como GCC, GCC Alta e DoD.</span><span class="sxs-lookup"><span data-stu-id="645f8-205">Office 365 DoD Learn more about [Office 365 and US Government environments](/office365/servicedescriptions/office-365-platform-service-description/office-365-us-government/office-365-us-government) such as GCC, GCC High, and DoD.</span></span>

### <a name="microsoft-365-office-365-and-office-365-gcc-environments"></a><span data-ttu-id="645f8-206">Microsoft 365, Office 365 ambientes Office 365 GCC ambientes</span><span class="sxs-lookup"><span data-stu-id="645f8-206">Microsoft 365, Office 365, and Office 365 GCC environments</span></span>

<span data-ttu-id="645f8-207">Os pontos de conexão para Roteamento Direto são os três FQDNs a seguir:</span><span class="sxs-lookup"><span data-stu-id="645f8-207">The connection points for Direct Routing are the following three FQDNs:</span></span>

- <span data-ttu-id="645f8-208">**sip.pstnhub.microsoft.com** – FQDN Global – deve ser experimentado primeiro.</span><span class="sxs-lookup"><span data-stu-id="645f8-208">**sip.pstnhub.microsoft.com** – Global FQDN – must be tried first.</span></span> <span data-ttu-id="645f8-209">Quando o SBC envia uma solicitação para resolver esse nome, os servidores DNS Microsoft Azure retornam um endereço IP apontando para o datacenter principal do Azure atribuído ao SBC.</span><span class="sxs-lookup"><span data-stu-id="645f8-209">When the SBC sends a request to resolve this name, the Microsoft Azure DNS servers return an IP address pointing to the primary Azure datacenter assigned to the SBC.</span></span> <span data-ttu-id="645f8-210">A atribuição é baseada em métricas de desempenho dos datacenters e proximidade geográfica com o SBC.</span><span class="sxs-lookup"><span data-stu-id="645f8-210">The assignment is based on performance metrics of the datacenters and geographical proximity to the SBC.</span></span> <span data-ttu-id="645f8-211">O endereço IP retornado corresponde ao FQDN principal.</span><span class="sxs-lookup"><span data-stu-id="645f8-211">The IP address returned corresponds to the primary FQDN.</span></span>

- <span data-ttu-id="645f8-212">**sip2.pstnhub.microsoft.com** – FQDN secundário – mapeia geograficamente para a região de segunda prioridade.</span><span class="sxs-lookup"><span data-stu-id="645f8-212">**sip2.pstnhub.microsoft.com** – Secondary FQDN – geographically maps to the second priority region.</span></span>

- <span data-ttu-id="645f8-213">**sip3.pstnhub.microsoft.com** – FQDN terciário – mapeia geograficamente para a região de terceira prioridade.</span><span class="sxs-lookup"><span data-stu-id="645f8-213">**sip3.pstnhub.microsoft.com** – Tertiary FQDN – geographically maps to the third priority region.</span></span>

<span data-ttu-id="645f8-214">Você deve colocar esses três FQDNs para:</span><span class="sxs-lookup"><span data-stu-id="645f8-214">You must place these three FQDNs in order to:</span></span>

- <span data-ttu-id="645f8-215">Forneça uma experiência ideal (menos carregada e mais próxima do datacenter SBC atribuído consultando o primeiro FQDN).</span><span class="sxs-lookup"><span data-stu-id="645f8-215">Provide optimal experience (less loaded and closest to the SBC datacenter assigned by querying the first FQDN).</span></span>

- <span data-ttu-id="645f8-216">Forneça failover quando uma conexão de um SBC é estabelecida com um datacenter que está enfrentando um problema temporário.</span><span class="sxs-lookup"><span data-stu-id="645f8-216">Provide failover when a connection from an SBC is established to a datacenter that is experiencing a temporary issue.</span></span> <span data-ttu-id="645f8-217">Para obter mais informações, consulte Mecanismo de failover abaixo.</span><span class="sxs-lookup"><span data-stu-id="645f8-217">For more information, see Failover mechanism below.</span></span>


<span data-ttu-id="645f8-218">Os FQDNs **sip.pstnhub.microsoft.com,** **sip2.pstnhub.microsoft.com** e **sip3.pstnhub.microsoft.com** serão resolvidos para um dos seguintes endereços IP:</span><span class="sxs-lookup"><span data-stu-id="645f8-218">The FQDNs **sip.pstnhub.microsoft.com**, **sip2.pstnhub.microsoft.com**, and **sip3.pstnhub.microsoft.com** will be resolved to one of the following IP addresses:</span></span>
- <span data-ttu-id="645f8-219">52.114.148.0</span><span class="sxs-lookup"><span data-stu-id="645f8-219">52.114.148.0</span></span>
- <span data-ttu-id="645f8-220">52.114.132.46</span><span class="sxs-lookup"><span data-stu-id="645f8-220">52.114.132.46</span></span> 
- <span data-ttu-id="645f8-221">52.114.75.24</span><span class="sxs-lookup"><span data-stu-id="645f8-221">52.114.75.24</span></span> 
- <span data-ttu-id="645f8-222">52.114.76.76</span><span class="sxs-lookup"><span data-stu-id="645f8-222">52.114.76.76</span></span> 
- <span data-ttu-id="645f8-223">52.114.7.24</span><span class="sxs-lookup"><span data-stu-id="645f8-223">52.114.7.24</span></span> 
- <span data-ttu-id="645f8-224">52.114.14.70</span><span class="sxs-lookup"><span data-stu-id="645f8-224">52.114.14.70</span></span>
- <span data-ttu-id="645f8-225">52.114.16.74</span><span class="sxs-lookup"><span data-stu-id="645f8-225">52.114.16.74</span></span>
- <span data-ttu-id="645f8-226">52.114.20.29</span><span class="sxs-lookup"><span data-stu-id="645f8-226">52.114.20.29</span></span>
- <span data-ttu-id="645f8-227">52.114.36.156</span><span class="sxs-lookup"><span data-stu-id="645f8-227">52.114.36.156</span></span> 
- <span data-ttu-id="645f8-228">52.114.32.169</span><span class="sxs-lookup"><span data-stu-id="645f8-228">52.114.32.169</span></span>

<span data-ttu-id="645f8-229">Você precisa abrir portas para todos esses endereços IP no firewall para permitir que o tráfego de entrada e saída entre e os endereços para sinalização.</span><span class="sxs-lookup"><span data-stu-id="645f8-229">You need to open ports for all these IP addresses in your firewall to allow incoming and outgoing traffic to and from the addresses for signaling.</span></span> <span data-ttu-id="645f8-230">Se o firewall dá suporte a nomes DNS, o FQDN **sip-all.pstnhub.microsoft.com** resolvido para todos esses endereços IP.</span><span class="sxs-lookup"><span data-stu-id="645f8-230">If your firewall supports DNS names, the FQDN **sip-all.pstnhub.microsoft.com** resolves to all these IP addresses.</span></span> 

### <a name="office-365-gcc-dod-environment"></a><span data-ttu-id="645f8-231">Office 365 GCC ambiente do DoD</span><span class="sxs-lookup"><span data-stu-id="645f8-231">Office 365 GCC DoD environment</span></span>

<span data-ttu-id="645f8-232">O ponto de conexão para Roteamento Direto é o seguinte FQDN:</span><span class="sxs-lookup"><span data-stu-id="645f8-232">The connection point for Direct Routing is the following FQDN:</span></span>

<span data-ttu-id="645f8-233">**sip.pstnhub.dod.teams.microsoft.us** – FQDN Global.</span><span class="sxs-lookup"><span data-stu-id="645f8-233">**sip.pstnhub.dod.teams.microsoft.us** – Global FQDN.</span></span> <span data-ttu-id="645f8-234">Como o Office 365 do DoD existe apenas nos data centers dos EUA, não há FQDNs secundários e terciários.</span><span class="sxs-lookup"><span data-stu-id="645f8-234">As the Office 365 DoD environment exists only in the US data centers, there is no secondary and tertiary FQDNs.</span></span>

<span data-ttu-id="645f8-235">Os FQDNs – sip.pstnhub.dod.teams.microsoft.us serão resolvidos para um dos seguintes endereços IP:</span><span class="sxs-lookup"><span data-stu-id="645f8-235">The FQDNs – sip.pstnhub.dod.teams.microsoft.us will be resolved to one of the following IP addresses:</span></span>

- <span data-ttu-id="645f8-236">52.127.64.33</span><span class="sxs-lookup"><span data-stu-id="645f8-236">52.127.64.33</span></span>
- <span data-ttu-id="645f8-237">52.127.68.34</span><span class="sxs-lookup"><span data-stu-id="645f8-237">52.127.68.34</span></span>

<span data-ttu-id="645f8-238">Você precisa abrir portas para todos esses endereços IP no firewall para permitir que o tráfego de entrada e saída entre e os endereços para sinalização.</span><span class="sxs-lookup"><span data-stu-id="645f8-238">You need to open ports for all these IP addresses in your firewall to allow incoming and outgoing traffic to and from the addresses for signaling.</span></span>  <span data-ttu-id="645f8-239">Se o firewall dá suporte a nomes DNS, o FQDN sip.pstnhub.dod.teams.microsoft.us resolvido para todos esses endereços IP.</span><span class="sxs-lookup"><span data-stu-id="645f8-239">If your firewall supports DNS names, the FQDN  sip.pstnhub.dod.teams.microsoft.us resolves to all these IP addresses.</span></span> 

### <a name="office-365-gcc-high-environment"></a><span data-ttu-id="645f8-240">Office 365 GCC ambiente high</span><span class="sxs-lookup"><span data-stu-id="645f8-240">Office 365 GCC High environment</span></span>

<span data-ttu-id="645f8-241">O ponto de conexão para Roteamento Direto é o seguinte FQDN:</span><span class="sxs-lookup"><span data-stu-id="645f8-241">The connection point for Direct Routing is the following FQDN:</span></span>

<span data-ttu-id="645f8-242">**sip.pstnhub.gov.teams.microsoft.us** – FQDN Global.</span><span class="sxs-lookup"><span data-stu-id="645f8-242">**sip.pstnhub.gov.teams.microsoft.us** – Global FQDN.</span></span> <span data-ttu-id="645f8-243">Como o GCC ambiente High existe apenas nos data centers dos EUA, não há FQDNs secundários e terciários.</span><span class="sxs-lookup"><span data-stu-id="645f8-243">As the GCC High environment exists only in the US data centers, there is no secondary and tertiary FQDNs.</span></span>

<span data-ttu-id="645f8-244">Os FQDNs – sip.pstnhub.gov.teams.microsoft.us serão resolvidos para um dos seguintes endereços IP:</span><span class="sxs-lookup"><span data-stu-id="645f8-244">The FQDNs – sip.pstnhub.gov.teams.microsoft.us will be resolved to one of the following IP addresses:</span></span>

- <span data-ttu-id="645f8-245">52.127.88.59</span><span class="sxs-lookup"><span data-stu-id="645f8-245">52.127.88.59</span></span>
- <span data-ttu-id="645f8-246">52.127.92.64</span><span class="sxs-lookup"><span data-stu-id="645f8-246">52.127.92.64</span></span>

<span data-ttu-id="645f8-247">Você precisa abrir portas para todos esses endereços IP no firewall para permitir que o tráfego de entrada e saída entre e os endereços para sinalização.</span><span class="sxs-lookup"><span data-stu-id="645f8-247">You need to open ports for all these IP addresses in your firewall to allow incoming and outgoing traffic to and from the addresses for signaling.</span></span>  <span data-ttu-id="645f8-248">Se o firewall dá suporte a nomes DNS, o FQDN sip.pstnhub.gov.teams.microsoft.us resolvido para todos esses endereços IP.</span><span class="sxs-lookup"><span data-stu-id="645f8-248">If your firewall supports DNS names, the FQDN  sip.pstnhub.gov.teams.microsoft.us resolves to all these IP addresses.</span></span> 

## <a name="sip-signaling-ports"></a><span data-ttu-id="645f8-249">Sinalização SIP: Portas</span><span class="sxs-lookup"><span data-stu-id="645f8-249">SIP Signaling: Ports</span></span>

<span data-ttu-id="645f8-250">Os requisitos de porta são os mesmos para todos os ambientes Office 365 em que o Roteamento Direto é oferecido:</span><span class="sxs-lookup"><span data-stu-id="645f8-250">Port requirements are the same for all Office 365 environments where Direct Routing is offered:</span></span>
- <span data-ttu-id="645f8-251">Microsoft 365 ou Office 365</span><span class="sxs-lookup"><span data-stu-id="645f8-251">Microsoft 365 or Office 365</span></span>
- <span data-ttu-id="645f8-252">Office 365 GCC</span><span class="sxs-lookup"><span data-stu-id="645f8-252">Office 365 GCC</span></span>
- <span data-ttu-id="645f8-253">Office 365 GCC Alta</span><span class="sxs-lookup"><span data-stu-id="645f8-253">Office 365 GCC High</span></span>
- <span data-ttu-id="645f8-254">Office 365 DoD</span><span class="sxs-lookup"><span data-stu-id="645f8-254">Office 365 DoD</span></span>

<span data-ttu-id="645f8-255">Você deve usar as seguintes portas:</span><span class="sxs-lookup"><span data-stu-id="645f8-255">You must use the following ports:</span></span>

| <span data-ttu-id="645f8-256">Tráfego</span><span class="sxs-lookup"><span data-stu-id="645f8-256">Traffic</span></span> | <span data-ttu-id="645f8-257">De</span><span class="sxs-lookup"><span data-stu-id="645f8-257">From</span></span> | <span data-ttu-id="645f8-258">Até</span><span class="sxs-lookup"><span data-stu-id="645f8-258">To</span></span> | <span data-ttu-id="645f8-259">Porta de origem</span><span class="sxs-lookup"><span data-stu-id="645f8-259">Source port</span></span> | <span data-ttu-id="645f8-260">Porta de destino</span><span class="sxs-lookup"><span data-stu-id="645f8-260">Destination port</span></span>|
| :-------- | :-------- |:-----------|:--------|:---------|
<span data-ttu-id="645f8-261">SIP/TLS</span><span class="sxs-lookup"><span data-stu-id="645f8-261">SIP/TLS</span></span>| <span data-ttu-id="645f8-262">SIP Proxy</span><span class="sxs-lookup"><span data-stu-id="645f8-262">SIP Proxy</span></span> | <span data-ttu-id="645f8-263">SBC</span><span class="sxs-lookup"><span data-stu-id="645f8-263">SBC</span></span> | <span data-ttu-id="645f8-264">1024 - 65535</span><span class="sxs-lookup"><span data-stu-id="645f8-264">1024 - 65535</span></span> | <span data-ttu-id="645f8-265">Definido no SBC</span><span class="sxs-lookup"><span data-stu-id="645f8-265">Defined on the SBC</span></span> |
| <span data-ttu-id="645f8-266">SIP/TLS</span><span class="sxs-lookup"><span data-stu-id="645f8-266">SIP/TLS</span></span> | <span data-ttu-id="645f8-267">SBC</span><span class="sxs-lookup"><span data-stu-id="645f8-267">SBC</span></span> | <span data-ttu-id="645f8-268">SIP Proxy</span><span class="sxs-lookup"><span data-stu-id="645f8-268">SIP Proxy</span></span> | <span data-ttu-id="645f8-269">Definido no SBC</span><span class="sxs-lookup"><span data-stu-id="645f8-269">Defined on the SBC</span></span> | <span data-ttu-id="645f8-270">5061</span><span class="sxs-lookup"><span data-stu-id="645f8-270">5061</span></span> |


## <a name="media-traffic-ip-and-port-ranges"></a><span data-ttu-id="645f8-271">Tráfego de mídia: intervalos de IP e porta</span><span class="sxs-lookup"><span data-stu-id="645f8-271">Media traffic: IP and Port ranges</span></span>

<span data-ttu-id="645f8-272">O tráfego de mídia flui entre o SBC e o cliente Teams se a conectividade direta estiver disponível ou por meio de retransmissão de transporte Teams se o cliente não puder alcançar o SBC usando o endereço IP público.</span><span class="sxs-lookup"><span data-stu-id="645f8-272">Media traffic flows between the SBC and Teams client if direct connectivity is available or via Teams Transport Relays if the client cannot reach the SBC using the public IP address.</span></span>

### <a name="requirements-for-direct-media-traffic-between-the-teams-client-and-the-sbc"></a><span data-ttu-id="645f8-273">Requisitos para tráfego de mídia direta (entre o cliente Teams e o SBC)</span><span class="sxs-lookup"><span data-stu-id="645f8-273">Requirements for direct media traffic (between the Teams client and the SBC)</span></span> 

<span data-ttu-id="645f8-274">O cliente deve ter acesso às portas especificadas (consulte tabela) no endereço IP público do SBC.</span><span class="sxs-lookup"><span data-stu-id="645f8-274">The client must have access to the specified ports (see table) on the public IP address of the SBC.</span></span> 

> [!NOTE]
> <span data-ttu-id="645f8-275">Se o cliente estiver em uma rede interna, a mídia flui para o endereço IP público do SBC.</span><span class="sxs-lookup"><span data-stu-id="645f8-275">If the client is in an internal network, the media flows to the public IP address of the SBC.</span></span> <span data-ttu-id="645f8-276">Você pode configurar o fixamento de pelos em seu dispositivo NAT para que o tráfego nunca saia do equipamento de rede empresarial.</span><span class="sxs-lookup"><span data-stu-id="645f8-276">You can configure hair pinning on your NAT device so traffic never leaves the enterprise network equipment.</span></span>

| <span data-ttu-id="645f8-277">Tráfego</span><span class="sxs-lookup"><span data-stu-id="645f8-277">Traffic</span></span> | <span data-ttu-id="645f8-278">De</span><span class="sxs-lookup"><span data-stu-id="645f8-278">From</span></span> | <span data-ttu-id="645f8-279">Até</span><span class="sxs-lookup"><span data-stu-id="645f8-279">To</span></span> | <span data-ttu-id="645f8-280">Porta de origem</span><span class="sxs-lookup"><span data-stu-id="645f8-280">Source port</span></span> | <span data-ttu-id="645f8-281">Porta de destino</span><span class="sxs-lookup"><span data-stu-id="645f8-281">Destination port</span></span>|
| :-------- | :-------- |:-----------|:--------|:---------|
<span data-ttu-id="645f8-282">UDP/SRTP</span><span class="sxs-lookup"><span data-stu-id="645f8-282">UDP/SRTP</span></span> | <span data-ttu-id="645f8-283">Cliente</span><span class="sxs-lookup"><span data-stu-id="645f8-283">Client</span></span> | <span data-ttu-id="645f8-284">SBC</span><span class="sxs-lookup"><span data-stu-id="645f8-284">SBC</span></span> | <span data-ttu-id="645f8-285">3478-3481 e 49152 – 53247</span><span class="sxs-lookup"><span data-stu-id="645f8-285">3478-3481 and 49152 – 53247</span></span>| <span data-ttu-id="645f8-286">Definido no SBC</span><span class="sxs-lookup"><span data-stu-id="645f8-286">Defined on the SBC</span></span> |
| <span data-ttu-id="645f8-287">UDP/SRTP</span><span class="sxs-lookup"><span data-stu-id="645f8-287">UDP/SRTP</span></span> | <span data-ttu-id="645f8-288">SBC</span><span class="sxs-lookup"><span data-stu-id="645f8-288">SBC</span></span> | <span data-ttu-id="645f8-289">Cliente</span><span class="sxs-lookup"><span data-stu-id="645f8-289">Client</span></span> | <span data-ttu-id="645f8-290">Definido no SBC</span><span class="sxs-lookup"><span data-stu-id="645f8-290">Defined on the SBC</span></span> | <span data-ttu-id="645f8-291">3478-3481 e 49152 – 53247</span><span class="sxs-lookup"><span data-stu-id="645f8-291">3478-3481 and 49152 – 53247</span></span>  |


> [!NOTE]
> <span data-ttu-id="645f8-292">Se você tiver um dispositivo de rede que traduza as portas de origem do cliente, verifique se as portas traduzidas são abertas entre o equipamento de rede e o SBC.</span><span class="sxs-lookup"><span data-stu-id="645f8-292">If you have a network device that translates the client's source ports, please make sure that translated ports are opened between the network equipment and the SBC.</span></span> 

### <a name="requirements-for-using-transport-relays"></a><span data-ttu-id="645f8-293">Requisitos para usar retransmissão de transporte</span><span class="sxs-lookup"><span data-stu-id="645f8-293">Requirements for using Transport Relays</span></span>

<span data-ttu-id="645f8-294">Retransmissão de transporte estão no mesmo intervalo que processadores de mídia (para casos que não são de bypass):</span><span class="sxs-lookup"><span data-stu-id="645f8-294">Transport Relays are in the same range as Media Processors (for non-bypass cases):</span></span> 

### <a name="microsoft-365-office-365-and-office-365-gcc-environments"></a><span data-ttu-id="645f8-295">Microsoft 365, Office 365 ambientes Office 365 GCC ambientes</span><span class="sxs-lookup"><span data-stu-id="645f8-295">Microsoft 365, Office 365, and Office 365 GCC environments</span></span>

- <span data-ttu-id="645f8-296">52.112.0.0 /14 (endereços IP de 52.112.0.1 a 52.115.255.254)</span><span class="sxs-lookup"><span data-stu-id="645f8-296">52.112.0.0 /14 (IP addresses from 52.112.0.1 to 52.115.255.254)</span></span>

### <a name="office-365-gcc-dod-environment"></a><span data-ttu-id="645f8-297">Office 365 GCC ambiente do DoD</span><span class="sxs-lookup"><span data-stu-id="645f8-297">Office 365 GCC DoD environment</span></span>

- <span data-ttu-id="645f8-298">52.127.64.0/21</span><span class="sxs-lookup"><span data-stu-id="645f8-298">52.127.64.0/21</span></span>

### <a name="office-365-gcc-high-environment"></a><span data-ttu-id="645f8-299">Office 365 GCC ambiente high</span><span class="sxs-lookup"><span data-stu-id="645f8-299">Office 365 GCC High environment</span></span>

- <span data-ttu-id="645f8-300">52.127.88.0/21</span><span class="sxs-lookup"><span data-stu-id="645f8-300">52.127.88.0/21</span></span>


<span data-ttu-id="645f8-301">O intervalo de portas do Teams Retransmissão de Transporte (aplicável a todos os ambientes) é mostrado na tabela a seguir:</span><span class="sxs-lookup"><span data-stu-id="645f8-301">The port range of the Teams Transport Relays (applicable to all environments) is shown in the following table:</span></span>


| <span data-ttu-id="645f8-302">Tráfego</span><span class="sxs-lookup"><span data-stu-id="645f8-302">Traffic</span></span> | <span data-ttu-id="645f8-303">De</span><span class="sxs-lookup"><span data-stu-id="645f8-303">From</span></span> | <span data-ttu-id="645f8-304">Até</span><span class="sxs-lookup"><span data-stu-id="645f8-304">To</span></span> | <span data-ttu-id="645f8-305">Porta de origem</span><span class="sxs-lookup"><span data-stu-id="645f8-305">Source port</span></span> | <span data-ttu-id="645f8-306">Porta de destino</span><span class="sxs-lookup"><span data-stu-id="645f8-306">Destination port</span></span>|
| :-------- | :-------- |:-----------|:--------|:---------|
<span data-ttu-id="645f8-307">UDP/SRTP</span><span class="sxs-lookup"><span data-stu-id="645f8-307">UDP/SRTP</span></span> | <span data-ttu-id="645f8-308">Retransmissão de transporte</span><span class="sxs-lookup"><span data-stu-id="645f8-308">Transport Relay</span></span> | <span data-ttu-id="645f8-309">SBC</span><span class="sxs-lookup"><span data-stu-id="645f8-309">SBC</span></span> | <span data-ttu-id="645f8-310">50 000 -59 999</span><span class="sxs-lookup"><span data-stu-id="645f8-310">50 000 -59 999</span></span>    | <span data-ttu-id="645f8-311">Definido no SBC</span><span class="sxs-lookup"><span data-stu-id="645f8-311">Defined on the SBC</span></span> |
| <span data-ttu-id="645f8-312">UDP/SRTP</span><span class="sxs-lookup"><span data-stu-id="645f8-312">UDP/SRTP</span></span> | <span data-ttu-id="645f8-313">SBC</span><span class="sxs-lookup"><span data-stu-id="645f8-313">SBC</span></span> | <span data-ttu-id="645f8-314">Retransmissão de transporte</span><span class="sxs-lookup"><span data-stu-id="645f8-314">Transport Relay</span></span> | <span data-ttu-id="645f8-315">Definido no SBC</span><span class="sxs-lookup"><span data-stu-id="645f8-315">Defined on the SBC</span></span> | <span data-ttu-id="645f8-316">50 000 – 59 999, 3478-3481</span><span class="sxs-lookup"><span data-stu-id="645f8-316">50 000 – 59 999, 3478-3481</span></span>     |


> [!NOTE]
> <span data-ttu-id="645f8-317">A Microsoft recomenda pelo menos duas portas por chamada simultânea no SBC.</span><span class="sxs-lookup"><span data-stu-id="645f8-317">Microsoft recommends at least two ports per concurrent call on the SBC.</span></span> <span data-ttu-id="645f8-318">Como a Microsoft tem duas versões de Retransmissão de Transporte, o seguinte é necessário:</span><span class="sxs-lookup"><span data-stu-id="645f8-318">Because Microsoft has two versions of Transport Relays, the following are required:</span></span>
> 
> - <span data-ttu-id="645f8-319">v4, que só pode funcionar com o intervalo de portas de 50 000 a 59 999</span><span class="sxs-lookup"><span data-stu-id="645f8-319">v4, which can only work with port range 50 000 to 59 999</span></span>
> 
> - <span data-ttu-id="645f8-320">v6, que funciona com as portas 3478-3481</span><span class="sxs-lookup"><span data-stu-id="645f8-320">v6, which works with ports 3478-3481</span></span>

<span data-ttu-id="645f8-321">Neste momento, o bypass de mídia só dá suporte à versão v4 de Retransmissão de Transporte.</span><span class="sxs-lookup"><span data-stu-id="645f8-321">At this time, media bypass only supports v4 version of Transport Relays.</span></span> <span data-ttu-id="645f8-322">Apresentaremos o suporte do v6 no futuro.</span><span class="sxs-lookup"><span data-stu-id="645f8-322">We will introduce support of v6 in the future.</span></span> 

<span data-ttu-id="645f8-323">Você precisa abrir as portas 3478-3481 para transição.</span><span class="sxs-lookup"><span data-stu-id="645f8-323">You need to open ports 3478-3481 for transitioning.</span></span> <span data-ttu-id="645f8-324">Quando a Microsoft apresentar suporte para retransmissão de transporte v6 com Bypass de Mídia, você não precisará reconfigurar seu equipamento de rede ou SBCs.</span><span class="sxs-lookup"><span data-stu-id="645f8-324">When Microsoft introduces support for v6 Transport Relays with Media Bypass, you will not need to reconfigure your network equipment or SBCs.</span></span> 

### <a name="requirements-for-using-media-processors"></a><span data-ttu-id="645f8-325">Requisitos para usar processadores de mídia</span><span class="sxs-lookup"><span data-stu-id="645f8-325">Requirements for using media processors</span></span>

<span data-ttu-id="645f8-326">Processadores de mídia estão sempre no caminho de mídia para aplicativos de voz e para clientes Web (por exemplo, Teams clientes no Edge ou no Google Chrome).</span><span class="sxs-lookup"><span data-stu-id="645f8-326">Media Processors are always in the media path for voice applications and for Web clients (for example, Teams clients in Edge or Google Chrome).</span></span> <span data-ttu-id="645f8-327">Os requisitos são os mesmos da configuração que não ignora.</span><span class="sxs-lookup"><span data-stu-id="645f8-327">The requirements are the same as for non-bypass configuration.</span></span>


<span data-ttu-id="645f8-328">O intervalo de IP para tráfego de mídia é</span><span class="sxs-lookup"><span data-stu-id="645f8-328">The IP range for media traffic is</span></span> 

### <a name="office-365-and-office-365-gcc-environments"></a><span data-ttu-id="645f8-329">Office 365 e Office 365 GCC ambientes</span><span class="sxs-lookup"><span data-stu-id="645f8-329">Office 365 and Office 365 GCC environments</span></span>

- <span data-ttu-id="645f8-330">52.112.0.0 /14 (endereços IP de 52.112.0.1 a 52.115.255.254)</span><span class="sxs-lookup"><span data-stu-id="645f8-330">52.112.0.0 /14 (IP addresses from 52.112.0.1 to 52.115.255.254)</span></span>

### <a name="office-365-gcc-dod-environment"></a><span data-ttu-id="645f8-331">Office 365 GCC ambiente do DoD</span><span class="sxs-lookup"><span data-stu-id="645f8-331">Office 365 GCC DoD environment</span></span>

- <span data-ttu-id="645f8-332">52.127.64.0/21</span><span class="sxs-lookup"><span data-stu-id="645f8-332">52.127.64.0/21</span></span>

### <a name="office-365-gcc-high-environment"></a><span data-ttu-id="645f8-333">Office 365 GCC ambiente high</span><span class="sxs-lookup"><span data-stu-id="645f8-333">Office 365 GCC High environment</span></span>

- <span data-ttu-id="645f8-334">52.127.88.0/21</span><span class="sxs-lookup"><span data-stu-id="645f8-334">52.127.88.0/21</span></span>

<span data-ttu-id="645f8-335">O intervalo de portas dos Processadores de Mídia (aplicável a todos os ambientes) é mostrado na tabela a seguir:</span><span class="sxs-lookup"><span data-stu-id="645f8-335">The port range of the Media Processors (applicable to all environments) is shown in the following table:</span></span>

| <span data-ttu-id="645f8-336">Tráfego</span><span class="sxs-lookup"><span data-stu-id="645f8-336">Traffic</span></span> | <span data-ttu-id="645f8-337">De</span><span class="sxs-lookup"><span data-stu-id="645f8-337">From</span></span> | <span data-ttu-id="645f8-338">Até</span><span class="sxs-lookup"><span data-stu-id="645f8-338">To</span></span> | <span data-ttu-id="645f8-339">Porta de origem</span><span class="sxs-lookup"><span data-stu-id="645f8-339">Source port</span></span> | <span data-ttu-id="645f8-340">Porta de destino</span><span class="sxs-lookup"><span data-stu-id="645f8-340">Destination port</span></span>|
| :-------- | :-------- |:-----------|:--------|:---------|
<span data-ttu-id="645f8-341">UDP/SRTP</span><span class="sxs-lookup"><span data-stu-id="645f8-341">UDP/SRTP</span></span> | <span data-ttu-id="645f8-342">Processador de Mídia</span><span class="sxs-lookup"><span data-stu-id="645f8-342">Media Processor</span></span> | <span data-ttu-id="645f8-343">SBC</span><span class="sxs-lookup"><span data-stu-id="645f8-343">SBC</span></span> | <span data-ttu-id="645f8-344">3478-3481 e 49 152 – 53 247</span><span class="sxs-lookup"><span data-stu-id="645f8-344">3478-3481 and 49 152 – 53 247</span></span>    | <span data-ttu-id="645f8-345">Definido no SBC</span><span class="sxs-lookup"><span data-stu-id="645f8-345">Defined on the SBC</span></span> |
| <span data-ttu-id="645f8-346">UDP/SRTP</span><span class="sxs-lookup"><span data-stu-id="645f8-346">UDP/SRTP</span></span> | <span data-ttu-id="645f8-347">SBC</span><span class="sxs-lookup"><span data-stu-id="645f8-347">SBC</span></span> | <span data-ttu-id="645f8-348">Processador de Mídia</span><span class="sxs-lookup"><span data-stu-id="645f8-348">Media Processor</span></span> | <span data-ttu-id="645f8-349">Definido no SBC</span><span class="sxs-lookup"><span data-stu-id="645f8-349">Defined on the SBC</span></span> | <span data-ttu-id="645f8-350">3478-3481 e 49 152 – 53 247</span><span class="sxs-lookup"><span data-stu-id="645f8-350">3478-3481 and 49 152 – 53 247</span></span>     |

## <a name="configure-separate-trunks-for-media-bypass-and-non-media-bypass"></a><span data-ttu-id="645f8-351">Configurar troncos separados para bypass de mídia e bypass sem mídia</span><span class="sxs-lookup"><span data-stu-id="645f8-351">Configure separate trunks for media bypass and non-media bypass</span></span>  

<span data-ttu-id="645f8-352">Se você estiver migrando para o bypass de mídia de desvio de não mídia e quiser confirmar a funcionalidade antes de migrar todo o uso para o bypass de mídia, você pode criar um tronco separado e uma política de Roteamento de Voz Online separada para rotear para o tronco de bypass de mídia e atribuir a usuários específicos.</span><span class="sxs-lookup"><span data-stu-id="645f8-352">If you are migrating to media bypass from non-media bypass and want to confirm functionality before migrating all usage to media bypass, you can create a separate trunk and separate Online Voice Routing policy to route to the media bypass trunk and assign to specific users.</span></span> 

<span data-ttu-id="645f8-353">Etapas de configuração de alto nível:</span><span class="sxs-lookup"><span data-stu-id="645f8-353">High-level configuration steps:</span></span>

- <span data-ttu-id="645f8-354">Identifique os usuários para testar o bypass de mídia.</span><span class="sxs-lookup"><span data-stu-id="645f8-354">Identify users to test media bypass.</span></span>

- <span data-ttu-id="645f8-355">Crie dois troncos separados com FQDNs diferentes: um habilitado para bypass de mídia; o outro não.</span><span class="sxs-lookup"><span data-stu-id="645f8-355">Create two separate trunks with different FQDNs: one enabled for media bypass; the other not.</span></span> 

  <span data-ttu-id="645f8-356">Ambos os troncos apontam para o mesmo SBC.</span><span class="sxs-lookup"><span data-stu-id="645f8-356">Both trunks point to the same SBC.</span></span> <span data-ttu-id="645f8-357">As portas para sinalização SIP TLS devem ser diferentes.</span><span class="sxs-lookup"><span data-stu-id="645f8-357">The ports for TLS SIP signaling must be different.</span></span> <span data-ttu-id="645f8-358">As portas para mídia devem ser as mesmas.</span><span class="sxs-lookup"><span data-stu-id="645f8-358">The ports for media must be the same.</span></span>

- <span data-ttu-id="645f8-359">Crie uma nova política de Roteamento de Voz Online e atribua o tronco de bypass de mídia às rotas correspondentes associadas ao uso PSTN dessa política.</span><span class="sxs-lookup"><span data-stu-id="645f8-359">Create a new Online Voice Routing policy and assign the media bypass trunk to the corresponding routes associated with the PSTN usage for this policy.</span></span>

- <span data-ttu-id="645f8-360">Atribua a nova política de Roteamento de Voz Online aos usuários identificados para testar o bypass de mídia.</span><span class="sxs-lookup"><span data-stu-id="645f8-360">Assign the new Online Voice Routing policy to users you have identified to test media bypass.</span></span>

<span data-ttu-id="645f8-361">O exemplo a seguir ilustra essa lógica.</span><span class="sxs-lookup"><span data-stu-id="645f8-361">The example below illustrates this logic.</span></span>

| <span data-ttu-id="645f8-362">Conjunto de usuários</span><span class="sxs-lookup"><span data-stu-id="645f8-362">Set of users</span></span> | <span data-ttu-id="645f8-363">Número de usuários</span><span class="sxs-lookup"><span data-stu-id="645f8-363">Number of users</span></span> | <span data-ttu-id="645f8-364">FQDN de tronco atribuído no OVRP</span><span class="sxs-lookup"><span data-stu-id="645f8-364">Trunk FQDN assigned in OVRP</span></span> | <span data-ttu-id="645f8-365">Bypass de mídia habilitado</span><span class="sxs-lookup"><span data-stu-id="645f8-365">Media bypass enabled</span></span> |
| :------------ |:----------------- |:--------------|:--------------|
<span data-ttu-id="645f8-366">Usuários com tronco de bypass que não seja de mídia</span><span class="sxs-lookup"><span data-stu-id="645f8-366">Users with non-media bypass trunk</span></span> | <span data-ttu-id="645f8-367">980</span><span class="sxs-lookup"><span data-stu-id="645f8-367">980</span></span> | <span data-ttu-id="645f8-368">sbc1.contoso.com:5061</span><span class="sxs-lookup"><span data-stu-id="645f8-368">sbc1.contoso.com:5061</span></span> | <span data-ttu-id="645f8-369">false</span><span class="sxs-lookup"><span data-stu-id="645f8-369">false</span></span> |
<span data-ttu-id="645f8-370">Usuários com tronco de bypass de mídia</span><span class="sxs-lookup"><span data-stu-id="645f8-370">Users with media bypass trunk</span></span> | <span data-ttu-id="645f8-371">20</span><span class="sxs-lookup"><span data-stu-id="645f8-371">20</span></span> | <span data-ttu-id="645f8-372">sbc2.contoso.com:5060</span><span class="sxs-lookup"><span data-stu-id="645f8-372">sbc2.contoso.com:5060</span></span> | <span data-ttu-id="645f8-373">true</span><span class="sxs-lookup"><span data-stu-id="645f8-373">true</span></span> | 

<span data-ttu-id="645f8-374">Ambos os troncos podem apontar para o mesmo SBC com o mesmo endereço IP público.</span><span class="sxs-lookup"><span data-stu-id="645f8-374">Both trunks can point to the same SBC with the same public IP address.</span></span> <span data-ttu-id="645f8-375">As portas de sinalização TLS no SBC devem ser diferentes, conforme mostrado no diagrama a seguir.</span><span class="sxs-lookup"><span data-stu-id="645f8-375">The TLS signaling ports on the SBC must be different, as shown in the following diagram.</span></span> <span data-ttu-id="645f8-376">Observe que você precisará certificar-se de que seu certificado dá suporte a ambos os troncos.</span><span class="sxs-lookup"><span data-stu-id="645f8-376">Note you will need to make sure that your certificate supports both trunks.</span></span> <span data-ttu-id="645f8-377">Em SAN, você precisa ter dois nomes (**sbc1.contoso.com** e **sbc2.contoso.com**) ou ter um certificado curinga.</span><span class="sxs-lookup"><span data-stu-id="645f8-377">In SAN, you need to have two names (**sbc1.contoso.com** and **sbc2.contoso.com**) or have a wildcard certificate.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="645f8-378">![Mostra que ambos os troncos podem apontar para o mesmo SBC com o mesmo IP público](media/direct-routing-media-bypass-7.png)</span><span class="sxs-lookup"><span data-stu-id="645f8-378">![Shows both trunks can point to the same SBC with the same public IP](media/direct-routing-media-bypass-7.png)</span></span>

<span data-ttu-id="645f8-379">Para obter informações sobre como configurar dois troncos no mesmo SBC, consulte a documentação fornecida pelo fornecedor SBC:</span><span class="sxs-lookup"><span data-stu-id="645f8-379">For information about how to configure two trunks on the same SBC, see the documentation provided by your SBC vendor:</span></span>

 - [<span data-ttu-id="645f8-380">Documentação de implantação de AudioCodes</span><span class="sxs-lookup"><span data-stu-id="645f8-380">AudioCodes deployment documentation</span></span>](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/direct-routing-for-microsoft-teams)
- [<span data-ttu-id="645f8-381">Documentação de implantação do Oracle</span><span class="sxs-lookup"><span data-stu-id="645f8-381">Oracle deployment documentation</span></span>](https://www.oracle.com/industries/communications/enterprise-session-border-controller/microsoft.html)
- [<span data-ttu-id="645f8-382">Documentação de implantação do Ribbon Communications</span><span class="sxs-lookup"><span data-stu-id="645f8-382">Ribbon Communications deployment documentation</span></span>](https://ribboncommunications.com/solutions/enterprise-solutions/microsoft-solutions/direct-routing-microsoft-teams-calling)
- [<span data-ttu-id="645f8-383">Documentação de implantação do TE-Systems (anynode)</span><span class="sxs-lookup"><span data-stu-id="645f8-383">TE-Systems (anynode) deployment documentation</span></span>](https://www.anynode.de/anynode-and-microsoft-teams/)

## <a name="client-endpoints-supported-with-media-bypass"></a><span data-ttu-id="645f8-384">Pontos de extremidade do cliente com suporte com bypass de mídia</span><span class="sxs-lookup"><span data-stu-id="645f8-384">Client endpoints supported with media bypass</span></span>

<span data-ttu-id="645f8-385">O bypass de mídia é compatível com todos os clientes Teams desktop autônomos, clientes Android e iOS e Teams Telefone Dispositivos.</span><span class="sxs-lookup"><span data-stu-id="645f8-385">Media bypass is supported with all standalone Teams Desktop clients, Android and iOS clients and Teams Phone Devices.</span></span> 

<span data-ttu-id="645f8-386">Para todos os outros pontos de extremidade que não suportam bypass de mídia, converteremos a chamada em não ignorar, mesmo que ela seja iniciada como uma chamada de bypass.</span><span class="sxs-lookup"><span data-stu-id="645f8-386">For all other endpoints that do not support media bypass, we will convert the call to non-bypass even if it started as a bypass call.</span></span> <span data-ttu-id="645f8-387">Isso acontece automaticamente e não exige ações do administrador.</span><span class="sxs-lookup"><span data-stu-id="645f8-387">This happens automatically and does not require any actions from the administrator.</span></span> <span data-ttu-id="645f8-388">Isso inclui Skype for Business telefones 3PIP e Teams Web que suportam chamadas de Roteamento Direto (clientes baseados em WebRTC em execução no Microsoft Edge, Google Chrome, Mozilla Firefox).</span><span class="sxs-lookup"><span data-stu-id="645f8-388">This includes Skype for Business 3PIP Phones, and Teams Web Clients that support Direct Routing calling (WebRTC based clients running on Microsoft Edge, Google Chrome, Mozilla Firefox).</span></span> 
 
## <a name="see-also"></a><span data-ttu-id="645f8-389">Confira também</span><span class="sxs-lookup"><span data-stu-id="645f8-389">See also</span></span>

[<span data-ttu-id="645f8-390">Configurar o bypass de mídia com Roteamento Direto</span><span class="sxs-lookup"><span data-stu-id="645f8-390">Configure media bypass with Direct Routing</span></span>](direct-routing-configure-media-bypass.md)
