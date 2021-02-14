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
description: Saiba como planejar o bypass de mídia com o Roteamento Direto do Sistema de Telefone, que permite reduzir o caminho do tráfego de mídia e melhorar o desempenho.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: efd6d4275d1e83df7821f178ddac8027039b6fce
ms.sourcegitcommit: 62d5ccf10202a50755166e3b8de0bd31d1f94fef
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/28/2020
ms.locfileid: "48790653"
---
# <a name="plan-for-media-bypass-with-direct-routing"></a><span data-ttu-id="ffd7f-103">Planejar o bypass de mídia com Roteamento Direto</span><span class="sxs-lookup"><span data-stu-id="ffd7f-103">Plan for media bypass with Direct Routing</span></span>

## <a name="about-media-bypass-with-direct-routing"></a><span data-ttu-id="ffd7f-104">Sobre o bypass de mídia com Roteamento Direto</span><span class="sxs-lookup"><span data-stu-id="ffd7f-104">About media bypass with Direct Routing</span></span>

<span data-ttu-id="ffd7f-105">O bypass de mídia permite reduzir o caminho do tráfego de mídia e reduzir o número de saltos em trânsito para melhorar o desempenho.</span><span class="sxs-lookup"><span data-stu-id="ffd7f-105">Media bypass enables you to shorten the path of media traffic and reduce the number of hops in transit for better performance.</span></span> <span data-ttu-id="ffd7f-106">Com o bypass de mídia, a mídia é mantida entre o Controlador de Borda de Sessão (SBC) e o cliente, em vez de enviá-lo por meio do Microsoft Phone System.</span><span class="sxs-lookup"><span data-stu-id="ffd7f-106">With media bypass, media is kept between the Session Border Controller (SBC) and the client instead of sending it via the Microsoft Phone System.</span></span> <span data-ttu-id="ffd7f-107">Para configurar o bypass de mídia, o SBC e o cliente devem estar no mesmo local ou rede.</span><span class="sxs-lookup"><span data-stu-id="ffd7f-107">To configure media bypass, the SBC and the client must be in the same location or network.</span></span>

<span data-ttu-id="ffd7f-108">Você pode controlar o bypass de mídia para cada SBC usando o comando **Set-CSOnlinePSTNGateway** com o parâmetro **-MediaBypass** definido como verdadeiro ou falso.</span><span class="sxs-lookup"><span data-stu-id="ffd7f-108">You can control media bypass for each SBC by using the **Set-CSOnlinePSTNGateway** command with the **-MediaBypass** parameter set to true or false.</span></span> <span data-ttu-id="ffd7f-109">Se você habilitar o bypass de mídia, isso não significa que todo o tráfego de mídia ficará dentro da rede corporativa.</span><span class="sxs-lookup"><span data-stu-id="ffd7f-109">If you enable media bypass, this does not mean that all media traffic will stay within the corporate network.</span></span> <span data-ttu-id="ffd7f-110">Este artigo descreve o fluxo de chamada em diferentes cenários.</span><span class="sxs-lookup"><span data-stu-id="ffd7f-110">This article describes the call flow in different scenarios.</span></span>    

<span data-ttu-id="ffd7f-111">Os diagramas a seguir ilustram a diferença no fluxo de chamada com e sem bypass de mídia.</span><span class="sxs-lookup"><span data-stu-id="ffd7f-111">The diagrams below illustrate the difference in call flow with and without media bypass.</span></span>

<span data-ttu-id="ffd7f-112">Sem bypass de mídia, quando um cliente faz ou recebe uma chamada, a sinalização e a mídia fluem entre o SBC, o Microsoft Phone System e o cliente teams, conforme mostrado no diagrama a seguir:</span><span class="sxs-lookup"><span data-stu-id="ffd7f-112">Without media bypass, when a client makes or receives a call, both signaling and media flow between the SBC, the Microsoft Phone System, and the Teams client, as shown in the following diagram:</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="ffd7f-113">![Mostra a sinalização e o fluxo de mídia sem bypass de mídia](media/direct-routing-media-bypass-1.png)</span><span class="sxs-lookup"><span data-stu-id="ffd7f-113">![Shows signaling and media flow without media bypass](media/direct-routing-media-bypass-1.png)</span></span>


<span data-ttu-id="ffd7f-114">Mas vamos supor que um usuário está no mesmo edifício ou rede que o SBC.</span><span class="sxs-lookup"><span data-stu-id="ffd7f-114">But let's assume that a user is in the same building or network as the SBC.</span></span> <span data-ttu-id="ffd7f-115">Por exemplo, suponha que um usuário que está em um prédio noTase faça uma chamada para um usuário PSTN:</span><span class="sxs-lookup"><span data-stu-id="ffd7f-115">For example, assume a user who is in a building in Frankfurt makes a call to a PSTN user:</span></span> 

- <span data-ttu-id="ffd7f-116">**Sem o bypass de** mídia, a mídia fluirá por Amsterdã ou Dublin (onde os datacenters da Microsoft são implantados) e voltarão para o SBC em Dublin.</span><span class="sxs-lookup"><span data-stu-id="ffd7f-116">**Without media bypass**, media will flow via either Amsterdam or Dublin (where Microsoft datacenters are deployed) and back to the SBC in Frankfurt.</span></span> 

  <span data-ttu-id="ffd7f-117">O datacenter na Europa é selecionado porque o SBC está na Europa e a Microsoft usa o datacenter mais próximo do SBC.</span><span class="sxs-lookup"><span data-stu-id="ffd7f-117">The datacenter in Europe is selected because the SBC is in Europe, and Microsoft uses the datacenter closest to the SBC.</span></span> <span data-ttu-id="ffd7f-118">Embora essa abordagem não afete a qualidade das chamada devido à otimização do fluxo de tráfego nas redes da Microsoft na maioria das regiões geográficas, o tráfego tem um loop desnecessário.</span><span class="sxs-lookup"><span data-stu-id="ffd7f-118">While this approach does not affect call quality due to optimization of traffic flow within Microsoft networks in most geographies, the traffic has an unnecessary loop.</span></span>     

- <span data-ttu-id="ffd7f-119">**Com o bypass de** mídia, a mídia é mantida diretamente entre o usuário do Teams e o SBC, conforme mostrado no diagrama a seguir:</span><span class="sxs-lookup"><span data-stu-id="ffd7f-119">**With media bypass**, the media is kept directly between the Teams user and the SBC as shown in the following diagram:</span></span>

  > [!div class="mx-imgBorder"]
  > <span data-ttu-id="ffd7f-120">![Mostra a sinalização e o fluxo de mídia com bypass de mídia](media/direct-routing-media-bypass-2.png)</span><span class="sxs-lookup"><span data-stu-id="ffd7f-120">![Shows signaling and media flow with media bypass](media/direct-routing-media-bypass-2.png)</span></span>

<span data-ttu-id="ffd7f-121">O bypass de mídia aproveita protocolos chamados Desaquecimento Interativo de Conectividade (ICE) no cliente teams e ICE lite no SBC.</span><span class="sxs-lookup"><span data-stu-id="ffd7f-121">Media bypass leverages protocols called Interactive Connectivity Establishment (ICE) on the Teams client and ICE lite on the SBC.</span></span> <span data-ttu-id="ffd7f-122">Esses protocolos permitem que o Roteamento Direto use o caminho de mídia mais direto para obter a melhor qualidade.</span><span class="sxs-lookup"><span data-stu-id="ffd7f-122">These protocols enable Direct Routing to use the most direct media path for optimal quality.</span></span> <span data-ttu-id="ffd7f-123">ICE e ICE Lite são padrões WebRTC.</span><span class="sxs-lookup"><span data-stu-id="ffd7f-123">ICE and ICE Lite are WebRTC standards.</span></span> <span data-ttu-id="ffd7f-124">Para obter informações detalhadas sobre esses protocolos, consulte RFC 5245.</span><span class="sxs-lookup"><span data-stu-id="ffd7f-124">For detailed information about these protocols, see RFC 5245.</span></span>


## <a name="call-flow-and-firewall-planning"></a><span data-ttu-id="ffd7f-125">Planejamento de fluxo de chamada e firewall</span><span class="sxs-lookup"><span data-stu-id="ffd7f-125">Call flow and firewall planning</span></span>

<span data-ttu-id="ffd7f-126">O planejamento do fluxo de chamada e do firewall depende se o usuário tem acesso direto ao endereço IP público do SBC e se o usuário está dentro ou fora da rede.</span><span class="sxs-lookup"><span data-stu-id="ffd7f-126">Call flow and firewall planning depends on whether the user has direct access to the public IP address of the SBC, and whether the user is inside or outside of the network.</span></span>

### <a name="call-flow-if-the-user-has-direct-access-to-the-public-ip-address-of-the-sbc"></a><span data-ttu-id="ffd7f-127">Fluxo de chamada se o usuário tiver acesso direto ao endereço IP público do SBC</span><span class="sxs-lookup"><span data-stu-id="ffd7f-127">Call flow if the user has direct access to the public IP address of the SBC</span></span>

<span data-ttu-id="ffd7f-128">Se o usuário tiver acesso direto ao endereço IP público do SBC, o fluxo de chamada será o seguinte:</span><span class="sxs-lookup"><span data-stu-id="ffd7f-128">If the user has direct access to the public IP address of the SBC, the call flow is as follows:</span></span>

- <span data-ttu-id="ffd7f-129">Para ignorar mídia, o cliente do Teams deve ter acesso ao endereço IP público do SBC, mesmo a partir de uma rede interna.</span><span class="sxs-lookup"><span data-stu-id="ffd7f-129">For media bypass, the Teams client must have access to the public IP address of the SBC even from an internal network.</span></span> <span data-ttu-id="ffd7f-130">Se a mídia direta não for desejada, a mídia poderá fluir por meio de Retransmissão de Transporte.</span><span class="sxs-lookup"><span data-stu-id="ffd7f-130">If direct media is not desired, the media can flow via Transport Relays.</span></span>

- <span data-ttu-id="ffd7f-131">Essa é a solução recomendada quando um usuário está no mesmo edifício e/ou rede que o SBC – remova os componentes do Microsoft Cloud do caminho de mídia.</span><span class="sxs-lookup"><span data-stu-id="ffd7f-131">This is the recommended solution when a user is in the same building and/or network as the SBC – remove Microsoft Cloud components from the media path.</span></span>

- <span data-ttu-id="ffd7f-132">A sinalização sempre flui pela nuvem da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="ffd7f-132">Signaling always flows via the Microsoft cloud.</span></span>

<span data-ttu-id="ffd7f-133">O diagrama a seguir mostra o fluxo de chamada quando o bypass de mídia está habilitado, o cliente é interno e o cliente pode alcançar o endereço IP público do SBC (mídia direta):</span><span class="sxs-lookup"><span data-stu-id="ffd7f-133">The following diagram shows call flow when media bypass is enabled, the client is internal, and the client can reach the public IP address of the SBC (direct media):</span></span> 

- <span data-ttu-id="ffd7f-134">As setas e os valores numéricos dos caminhos estão de acordo com os fluxos de [chamada do Microsoft Teams.](https://docs.microsoft.com/microsoftteams/microsoft-teams-online-call-flows)</span><span class="sxs-lookup"><span data-stu-id="ffd7f-134">The arrows and numeric values of the paths are in accordance with [Microsoft Teams call flows](https://docs.microsoft.com/microsoftteams/microsoft-teams-online-call-flows).</span></span>

- <span data-ttu-id="ffd7f-135">A sinalização SIP sempre leva caminhos 4 e 4' (dependendo da direção do tráfego).</span><span class="sxs-lookup"><span data-stu-id="ffd7f-135">The SIP signaling always takes paths 4 and 4' (depending on the direction of the traffic).</span></span> <span data-ttu-id="ffd7f-136">A mídia permanece local e segue o caminho 5b.</span><span class="sxs-lookup"><span data-stu-id="ffd7f-136">Media stays local and takes path 5b.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="ffd7f-137">![Mostra o fluxo de chamada com Bypass de Mídia habilitado, o cliente é interno](media/direct-routing-media-bypass-3.png)</span><span class="sxs-lookup"><span data-stu-id="ffd7f-137">![Shows Call flow with Media Bypass enabled, client is internal](media/direct-routing-media-bypass-3.png)</span></span>


### <a name="call-flow-if-the-user-does-not-have-access-to-the-public-ip-address-of-the-sbc"></a><span data-ttu-id="ffd7f-138">Fluxo de chamada se o usuário não tiver acesso ao endereço IP público do SBC</span><span class="sxs-lookup"><span data-stu-id="ffd7f-138">Call flow if the user does not have access to the public IP address of the SBC</span></span>

<span data-ttu-id="ffd7f-139">O seguinte descreve o fluxo de chamada se o usuário não tiver acesso ao endereço IP público do SBC.</span><span class="sxs-lookup"><span data-stu-id="ffd7f-139">The following describes call flow if the user does not have access to the public IP address of the SBC.</span></span> 

<span data-ttu-id="ffd7f-140">Por exemplo, suponha que o usuário seja externo e o administrador do locatário decidiu não abrir o endereço IP público do SBC para todos na Internet, mas somente para o Microsoft Cloud.</span><span class="sxs-lookup"><span data-stu-id="ffd7f-140">For example, assume the user is external, and the tenant administrator decided not to open the public IP address of the SBC to everyone in the Internet, but only to the Microsoft Cloud.</span></span> <span data-ttu-id="ffd7f-141">Os componentes internos do tráfego podem fluir por meio das Retransmissão de Transporte do Teams.</span><span class="sxs-lookup"><span data-stu-id="ffd7f-141">The internal components of traffic can flow via the Teams Transport Relays.</span></span> <span data-ttu-id="ffd7f-142">Considere o seguinte:</span><span class="sxs-lookup"><span data-stu-id="ffd7f-142">Consider the following:</span></span>

- <span data-ttu-id="ffd7f-143">As Retransmissão de Transporte do Teams são usadas.</span><span class="sxs-lookup"><span data-stu-id="ffd7f-143">Teams Transport Relays are used.</span></span>

- <span data-ttu-id="ffd7f-144">Para ignorar mídia, a Microsoft usa uma versão de Retransmissão de Transporte que requer a abertura de portas de 50 000 a 59 999 entre as Retransmissão de Transporte do Teams e o SBC (no futuro planejamos mover para a versão que requer apenas 3478 e 3479 portas).</span><span class="sxs-lookup"><span data-stu-id="ffd7f-144">For media bypass, Microsoft uses a version of Transport Relays that requires opening ports 50 000 to 59 999 between the Teams Transport Relays and the SBC (in the future we plan to move to the version which requires only 3478 and 3479 ports).</span></span>


<span data-ttu-id="ffd7f-145">O diagrama a seguir mostra o fluxo de chamada quando o bypass de mídia está habilitado, o cliente é externo e o cliente não pode alcançar o endereço IP público do Controlador de Borda de Sessão (a mídia é retransmitida pela Retransmissão de Transporte do Teams).</span><span class="sxs-lookup"><span data-stu-id="ffd7f-145">The following diagram shows call flow when media bypass is enabled, the client is external, and the client cannot reach the public IP address of the Session Border Controller (media is relayed by Teams Transport Relay).</span></span>

- <span data-ttu-id="ffd7f-146">As setas e os valores numéricos dos caminhos estão de acordo com os fluxos de [chamada do Microsoft Teams.](https://docs.microsoft.com/microsoftteams/microsoft-teams-online-call-flows)</span><span class="sxs-lookup"><span data-stu-id="ffd7f-146">The arrows and numeric values of the paths are in accordance with [Microsoft Teams call flows](https://docs.microsoft.com/microsoftteams/microsoft-teams-online-call-flows).</span></span>

- <span data-ttu-id="ffd7f-147">A mídia é reeddiada por meio dos caminhos 3, 3', 4 e 4'</span><span class="sxs-lookup"><span data-stu-id="ffd7f-147">Media is relayed via paths 3, 3', 4 and 4'</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="ffd7f-148">![Mostra o fluxo de chamada se o usuário não tiver acesso ao IP público do SBC](media/direct-routing-media-bypass-4.png)</span><span class="sxs-lookup"><span data-stu-id="ffd7f-148">![Shows Call flow if user does not have access to public IP of the SBC](media/direct-routing-media-bypass-4.png)</span></span>


### <a name="call-flow-if-a-user-is-outside-the-network-and-has-access-to-the-public-ip-of-the-sbc"></a><span data-ttu-id="ffd7f-149">Fluxo de chamada se um usuário estiver fora da rede e tiver acesso ao IP público do SBC</span><span class="sxs-lookup"><span data-stu-id="ffd7f-149">Call flow if a user is outside the network and has access to the public IP of the SBC</span></span>

> [!NOTE]
> <span data-ttu-id="ffd7f-150">Essa não é uma configuração recomendada porque não tira proveito das Retransmissão de Transporte do Teams.</span><span class="sxs-lookup"><span data-stu-id="ffd7f-150">This is not a recommended configuration because it does not take advantage of Teams Transport Relays.</span></span> <span data-ttu-id="ffd7f-151">Em vez disso, você deve considerar o cenário anterior em que o usuário não tem acesso ao endereço IP público do SBC.</span><span class="sxs-lookup"><span data-stu-id="ffd7f-151">Instead, you should consider the previous scenario where the user does not have access to the public IP address of the SBC.</span></span> 

<span data-ttu-id="ffd7f-152">O diagrama a seguir mostra o fluxo de chamada quando o bypass de mídia está habilitado, o cliente é externo e o cliente pode alcançar o endereço IP público do SBC (mídia direta).</span><span class="sxs-lookup"><span data-stu-id="ffd7f-152">The following diagram shows call flow when media bypass is enabled, the client is external, and the client can reach the public IP address of the SBC (direct media).</span></span>

- <span data-ttu-id="ffd7f-153">As setas e os valores numéricos dos caminhos estão de acordo com o artigo de fluxos de chamada [do Microsoft Teams.](https://docs.microsoft.com/microsoftteams/microsoft-teams-online-call-flows)</span><span class="sxs-lookup"><span data-stu-id="ffd7f-153">The arrows and numeric values of the paths are in accordance with the [Microsoft Teams call flows](https://docs.microsoft.com/microsoftteams/microsoft-teams-online-call-flows) article.</span></span>

- <span data-ttu-id="ffd7f-154">A sinalização SIP sempre leva caminhos 3 e 3' (dependendo da direção do tráfego).</span><span class="sxs-lookup"><span data-stu-id="ffd7f-154">The SIP signaling always takes paths 3 and 3' (depending on the direction of the traffic).</span></span> <span data-ttu-id="ffd7f-155">A mídia flui usando o caminho 2.</span><span class="sxs-lookup"><span data-stu-id="ffd7f-155">Media flows using path 2.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="ffd7f-156">![Mostra o fluxo de chamada se o usuário não tiver acesso ao IP público do SBC](media/direct-routing-media-bypass-5.png)</span><span class="sxs-lookup"><span data-stu-id="ffd7f-156">![Shows Call flow if user does not have access to public IP of the SBC](media/direct-routing-media-bypass-5.png)</span></span>


## <a name="use-of-media-processors-and-transport-relays"></a><span data-ttu-id="ffd7f-157">Uso de Processadores de Mídia e Retransmissão de Transporte</span><span class="sxs-lookup"><span data-stu-id="ffd7f-157">Use of Media Processors and Transport Relays</span></span>

<span data-ttu-id="ffd7f-158">Há dois componentes no Microsoft Cloud que podem estar no caminho do tráfego de mídia: Processadores de Mídia e Retransmissão de Transporte.</span><span class="sxs-lookup"><span data-stu-id="ffd7f-158">There are two components in the Microsoft Cloud that can be in the path of media traffic: Media Processors and Transport Relays.</span></span> 

- <span data-ttu-id="ffd7f-159">O Processador de Mídia é um componente voltado para o público que lida com mídia em casos que não ignoram e lida com mídia para aplicativos de voz.</span><span class="sxs-lookup"><span data-stu-id="ffd7f-159">The Media Processor is a public facing component that handles media in non-bypass cases and handles media for voice applications.</span></span>

   <span data-ttu-id="ffd7f-160">Os Processadores de Mídia estão sempre no caminho para chamadas não ignoradas pelo usuário final, mas nunca no caminho para chamadas ignoradas.</span><span class="sxs-lookup"><span data-stu-id="ffd7f-160">Media Processors are always in the path for end user non-bypassed calls, but never in the path for bypassed calls.</span></span> <span data-ttu-id="ffd7f-161">Os Processadores de Mídia estão sempre no caminho para todos os aplicativos de voz, como Call Park, Organizational Auto Attendant e Filas de Chamadas.</span><span class="sxs-lookup"><span data-stu-id="ffd7f-161">Media Processors are always in the path for all voice applications such as Call Park, Organizational Auto Attendant, and Call Queues.</span></span>

- <span data-ttu-id="ffd7f-162">A Retransmissão de Transporte é usada para se conectar ao Serviço de Transporte mais próximo para enviar tráfego em tempo real.</span><span class="sxs-lookup"><span data-stu-id="ffd7f-162">The Transport Relay is used to connect to the closest Transport Service to send real time traffic.</span></span>

   <span data-ttu-id="ffd7f-163">As Retransmissão de Transporte podem ou não estar no caminho para chamadas ignoradas, provenientes ou destinadas a usuários finais, dependendo de onde o usuário está e de como a rede está configurada.</span><span class="sxs-lookup"><span data-stu-id="ffd7f-163">Transport Relays might or might not be in the path for bypassed calls--originating from or destined to end users--depending on where the user is and how the network is configured .</span></span>

<span data-ttu-id="ffd7f-164">O diagrama a seguir mostra dois fluxos de chamada: um com bypass de mídia habilitado e o segundo com bypass de mídia desabilitado.</span><span class="sxs-lookup"><span data-stu-id="ffd7f-164">The following diagram shows two call flows – one with media bypass enabled and the second with media bypass disabled.</span></span> <span data-ttu-id="ffd7f-165">Observe que o diagrama apenas ilustra o tráfego proveniente de usuários finais ou destinados a.</span><span class="sxs-lookup"><span data-stu-id="ffd7f-165">Note the diagram only illustrates traffic originating from--or destined to--end users.</span></span>  
- <span data-ttu-id="ffd7f-166">O Controlador de Mídia é um microservidor do Azure que atribui processadores de mídia e cria ofertas SDP (Session Description Protocol).</span><span class="sxs-lookup"><span data-stu-id="ffd7f-166">The Media Controller is a microservice in Azure that assigns Media Processors and creates Session Description Protocol (SDP) offers.</span></span>

- <span data-ttu-id="ffd7f-167">O Proxy SIP é um componente que converte a sinalização HTTP REST usada no Teams para SIP.</span><span class="sxs-lookup"><span data-stu-id="ffd7f-167">The SIP Proxy is a component that translates HTTP REST signaling used in Teams to SIP.</span></span>    

> [!div class="mx-imgBorder"]
> <span data-ttu-id="ffd7f-168">![Mostra os fluxos de chamada com o Bypass de Mídia habilitado e desabilitado](media/direct-routing-media-bypass-6.png)</span><span class="sxs-lookup"><span data-stu-id="ffd7f-168">![Shows call flows with Media Bypass enabled and disabled](media/direct-routing-media-bypass-6.png)</span></span>


<span data-ttu-id="ffd7f-169">A tabela a seguir resume a diferença entre Processadores de Mídia e Retransmissão de Transporte.</span><span class="sxs-lookup"><span data-stu-id="ffd7f-169">The table below summarizes the difference between Media Processors and Transport Relays.</span></span>

|    | <span data-ttu-id="ffd7f-170">Processadores de Mídia</span><span class="sxs-lookup"><span data-stu-id="ffd7f-170">Media Processors</span></span> | <span data-ttu-id="ffd7f-171">Retransmissão de Transporte</span><span class="sxs-lookup"><span data-stu-id="ffd7f-171">Transport Relays</span></span>|
| :--------------|:---------------|:------------|
<span data-ttu-id="ffd7f-172">No caminho de mídia para chamadas não ignoradas para usuários finais</span><span class="sxs-lookup"><span data-stu-id="ffd7f-172">In media path for non-bypassed calls for end users</span></span> | <span data-ttu-id="ffd7f-173">Sempre</span><span class="sxs-lookup"><span data-stu-id="ffd7f-173">Always</span></span> | <span data-ttu-id="ffd7f-174">Nunca</span><span class="sxs-lookup"><span data-stu-id="ffd7f-174">Never</span></span> | 
<span data-ttu-id="ffd7f-175">No caminho da mídia para chamadas ignoradas para usuários finais</span><span class="sxs-lookup"><span data-stu-id="ffd7f-175">In media path for bypassed calls for end users</span></span> | <span data-ttu-id="ffd7f-176">Nunca</span><span class="sxs-lookup"><span data-stu-id="ffd7f-176">Never</span></span> | <span data-ttu-id="ffd7f-177">Se o cliente não conseguir alcançar o SBC no endereço IP público</span><span class="sxs-lookup"><span data-stu-id="ffd7f-177">If client cannot reach the SBC on the public IP address</span></span> | 
<span data-ttu-id="ffd7f-178">No caminho de mídia para aplicativos de voz</span><span class="sxs-lookup"><span data-stu-id="ffd7f-178">In media path for voice applications</span></span> | <span data-ttu-id="ffd7f-179">Sempre</span><span class="sxs-lookup"><span data-stu-id="ffd7f-179">Always</span></span> | <span data-ttu-id="ffd7f-180">Nunca</span><span class="sxs-lookup"><span data-stu-id="ffd7f-180">Never</span></span> | 
<span data-ttu-id="ffd7f-181">Pode fazer transcodificação (B2BUA)\*</span><span class="sxs-lookup"><span data-stu-id="ffd7f-181">Can do transcoding (B2BUA)\*</span></span> | <span data-ttu-id="ffd7f-182">Sim</span><span class="sxs-lookup"><span data-stu-id="ffd7f-182">Yes</span></span> | <span data-ttu-id="ffd7f-183">Não, apenas retransmiti áudio entre pontos de extremidade</span><span class="sxs-lookup"><span data-stu-id="ffd7f-183">No, only relays audio between endpoints</span></span> | 
<span data-ttu-id="ffd7f-184">Número de instâncias em todo o mundo e localização</span><span class="sxs-lookup"><span data-stu-id="ffd7f-184">Number of instances worldwide and location</span></span> | <span data-ttu-id="ffd7f-185">10 total: 2 no Leste e no Oeste dos EUA; 2 em Amsterdã e Dublin; 2 em Hong Kong e Cingapura; 2 no Japão; 2 na Austrália Leste e Sudeste</span><span class="sxs-lookup"><span data-stu-id="ffd7f-185">10 total: 2 in US East and West; 2 in Amsterdam and Dublin; 2 in Hong Kong and Singapore; 2 in Japan ; 2 in Australia East and Southeast</span></span> | <span data-ttu-id="ffd7f-186">Vários</span><span class="sxs-lookup"><span data-stu-id="ffd7f-186">Multiple</span></span>

<span data-ttu-id="ffd7f-187">Os intervalos de IP são:</span><span class="sxs-lookup"><span data-stu-id="ffd7f-187">The IP ranges are:</span></span>
- <span data-ttu-id="ffd7f-188">52.112.0.0/14 (endereços IP de 52.112.0.1 a 52.115.255.254)</span><span class="sxs-lookup"><span data-stu-id="ffd7f-188">52.112.0.0/14 (IP addresses from 52.112.0.1 to 52.115.255.254)</span></span>
- <span data-ttu-id="ffd7f-189">52.120.0.0/14 (endereços IP de 52.120.0.1 a 52.123.255.254)</span><span class="sxs-lookup"><span data-stu-id="ffd7f-189">52.120.0.0/14 (IP addresses from 52.120.0.1 to 52.123.255.254)</span></span>

<span data-ttu-id="ffd7f-190">\* Explicação de transcodificação:</span><span class="sxs-lookup"><span data-stu-id="ffd7f-190">\* Transcoding explanation:</span></span> 

- <span data-ttu-id="ffd7f-191">O processador de mídia é B2BUA, o que significa que ele pode alterar um codecs (por exemplo, SILK do cliente Teams para MP e G.711 entre MP e SBC).</span><span class="sxs-lookup"><span data-stu-id="ffd7f-191">Media Processor is B2BUA, which means it can change a codecs (for example, SILK from Teams client to MP and G.711 between MP and SBC).</span></span>

- <span data-ttu-id="ffd7f-192">As Retransmissão de Transporte não são B2BUA, o que significa que o codec nunca é alterado entre o cliente e o SBC, mesmo que o tráfego flua por retransmissão.</span><span class="sxs-lookup"><span data-stu-id="ffd7f-192">Transport Relays are not B2BUA, which means the codec is never changed between the client and the SBC--even if traffic flows via relays.</span></span>

### <a name="use-of-teams-media-processors-if-trunk-is-configured-for-media-bypass"></a><span data-ttu-id="ffd7f-193">Uso dos Processadores de Mídia do Teams se o tronco estiver configurado para bypass de mídia</span><span class="sxs-lookup"><span data-stu-id="ffd7f-193">Use of Teams Media Processors if trunk is configured for media bypass</span></span>

<span data-ttu-id="ffd7f-194">Os Processadores de Mídia do Teams sempre são inseridos no caminho de mídia nos seguintes cenários:</span><span class="sxs-lookup"><span data-stu-id="ffd7f-194">Teams Media Processors are always inserted in the media path in the following scenarios:</span></span>

- <span data-ttu-id="ffd7f-195">A chamada é escalonada de 1:1 para uma chamada em grupo</span><span class="sxs-lookup"><span data-stu-id="ffd7f-195">Call is escalated from 1:1 to a group call</span></span>
- <span data-ttu-id="ffd7f-196">A chamada será para um usuário federado do Teams</span><span class="sxs-lookup"><span data-stu-id="ffd7f-196">Call is going to a federated Teams user</span></span>
- <span data-ttu-id="ffd7f-197">A chamada é encaminhada ou transferida para um usuário do Skype for Business</span><span class="sxs-lookup"><span data-stu-id="ffd7f-197">Call is forwarded or transferred to a Skype for Business user</span></span>

<span data-ttu-id="ffd7f-198">Verifique se o SBC tem acesso aos intervalos de Processadores de Mídia e Retransmissão de Transporte conforme descrito abaixo.</span><span class="sxs-lookup"><span data-stu-id="ffd7f-198">Ensure your SBC has access to the Media Processors and Transport Relays ranges as described below.</span></span>    


## <a name="sip-signaling-fqdns"></a><span data-ttu-id="ffd7f-199">Sinalização SIP: FQDNs</span><span class="sxs-lookup"><span data-stu-id="ffd7f-199">SIP Signaling: FQDNs</span></span>

<span data-ttu-id="ffd7f-200">Para a sinalização SIP, os requisitos de FQDN e firewall são os mesmos para casos não ignorados.</span><span class="sxs-lookup"><span data-stu-id="ffd7f-200">For SIP signaling, the FQDN and firewall requirements are the same as for non-bypassed cases.</span></span> 

<span data-ttu-id="ffd7f-201">O Roteamento Direto é oferecido nos seguintes ambientes do Microsoft 365 ou office 365:</span><span class="sxs-lookup"><span data-stu-id="ffd7f-201">Direct Routing is offered in the following Microsoft 365 or Office 365 environments:</span></span>
- <span data-ttu-id="ffd7f-202">Microsoft 365 ou Office 365</span><span class="sxs-lookup"><span data-stu-id="ffd7f-202">Microsoft 365 or Office 365</span></span>
- <span data-ttu-id="ffd7f-203">Cc do Office 365</span><span class="sxs-lookup"><span data-stu-id="ffd7f-203">Office 365 GCC</span></span>
- <span data-ttu-id="ffd7f-204">Office 365 GCC High</span><span class="sxs-lookup"><span data-stu-id="ffd7f-204">Office 365 GCC High</span></span>
- <span data-ttu-id="ffd7f-205">Office 365 DoD Saiba mais sobre ambientes do [Office 365](https://docs.microsoft.com/office365/servicedescriptions/office-365-platform-service-description/office-365-us-government/office-365-us-government) e do Governo dos EUA, como GCC, GCC High e DoD.</span><span class="sxs-lookup"><span data-stu-id="ffd7f-205">Office 365 DoD Learn more about [Office 365 and US Government environments](https://docs.microsoft.com/office365/servicedescriptions/office-365-platform-service-description/office-365-us-government/office-365-us-government) such as GCC, GCC High, and DoD.</span></span>

### <a name="microsoft-365-office-365-and-office-365-gcc-environments"></a><span data-ttu-id="ffd7f-206">Ambientes do Microsoft 365, Office 365 e Office 365 GCC</span><span class="sxs-lookup"><span data-stu-id="ffd7f-206">Microsoft 365, Office 365, and Office 365 GCC environments</span></span>

<span data-ttu-id="ffd7f-207">Os pontos de conexão para Roteamento Direto são os três FQDNs a seguir:</span><span class="sxs-lookup"><span data-stu-id="ffd7f-207">The connection points for Direct Routing are the following three FQDNs:</span></span>

- <span data-ttu-id="ffd7f-208">**sip.pstnhub.microsoft.com** – FQDN Global – deve ser tentado primeiro.</span><span class="sxs-lookup"><span data-stu-id="ffd7f-208">**sip.pstnhub.microsoft.com** – Global FQDN – must be tried first.</span></span> <span data-ttu-id="ffd7f-209">Quando o SBC envia uma solicitação para resolver esse nome, os servidores DNS do Microsoft Azure retornam um endereço IP apontando para o datacenter principal do Azure atribuído ao SBC.</span><span class="sxs-lookup"><span data-stu-id="ffd7f-209">When the SBC sends a request to resolve this name, the Microsoft Azure DNS servers return an IP address pointing to the primary Azure datacenter assigned to the SBC.</span></span> <span data-ttu-id="ffd7f-210">A atribuição se baseia nas métricas de desempenho dos datacenters e da proximidade geográfica do SBC.</span><span class="sxs-lookup"><span data-stu-id="ffd7f-210">The assignment is based on performance metrics of the datacenters and geographical proximity to the SBC.</span></span> <span data-ttu-id="ffd7f-211">O endereço IP retornado corresponde ao FQDN principal.</span><span class="sxs-lookup"><span data-stu-id="ffd7f-211">The IP address returned corresponds to the primary FQDN.</span></span>

- <span data-ttu-id="ffd7f-212">**sip2.pstnhub.microsoft.com** – FQDN Secundário – mapeia geograficamente a região de segunda prioridade.</span><span class="sxs-lookup"><span data-stu-id="ffd7f-212">**sip2.pstnhub.microsoft.com** – Secondary FQDN – geographically maps to the second priority region.</span></span>

- <span data-ttu-id="ffd7f-213">**sip3.pstnhub.microsoft.com** – FQDN terciário – mapeia geograficamente a região de terceira prioridade.</span><span class="sxs-lookup"><span data-stu-id="ffd7f-213">**sip3.pstnhub.microsoft.com** – Tertiary FQDN – geographically maps to the third priority region.</span></span>

<span data-ttu-id="ffd7f-214">Você deve colocar esses três FQDNs para:</span><span class="sxs-lookup"><span data-stu-id="ffd7f-214">You must place these three FQDNs in order to:</span></span>

- <span data-ttu-id="ffd7f-215">Forneça uma experiência ideal (menos carregada e mais próxima do datacenter SBC atribuído consultando o primeiro FQDN).</span><span class="sxs-lookup"><span data-stu-id="ffd7f-215">Provide optimal experience (less loaded and closest to the SBC datacenter assigned by querying the first FQDN).</span></span>

- <span data-ttu-id="ffd7f-216">Forneça failover quando uma conexão de um SBC é estabelecida com um datacenter que está enfrentando um problema temporário.</span><span class="sxs-lookup"><span data-stu-id="ffd7f-216">Provide failover when a connection from an SBC is established to a datacenter that is experiencing a temporary issue.</span></span> <span data-ttu-id="ffd7f-217">Para obter mais informações, consulte o mecanismo failover abaixo.</span><span class="sxs-lookup"><span data-stu-id="ffd7f-217">For more information, see Failover mechanism below.</span></span>


<span data-ttu-id="ffd7f-218">Os FQDNs **sip.pstnhub.microsoft.com,** **sip2.pstnhub.microsoft.com** e **sip3.pstnhub.microsoft.com** serão resolvidos para um dos seguintes endereços IP:</span><span class="sxs-lookup"><span data-stu-id="ffd7f-218">The FQDNs **sip.pstnhub.microsoft.com**, **sip2.pstnhub.microsoft.com**, and **sip3.pstnhub.microsoft.com** will be resolved to one of the following IP addresses:</span></span>
- <span data-ttu-id="ffd7f-219">52.114.148.0</span><span class="sxs-lookup"><span data-stu-id="ffd7f-219">52.114.148.0</span></span>
- <span data-ttu-id="ffd7f-220">52.114.132.46</span><span class="sxs-lookup"><span data-stu-id="ffd7f-220">52.114.132.46</span></span>
- <span data-ttu-id="ffd7f-221">52.114.16.74</span><span class="sxs-lookup"><span data-stu-id="ffd7f-221">52.114.16.74</span></span>
- <span data-ttu-id="ffd7f-222">52.114.20.29</span><span class="sxs-lookup"><span data-stu-id="ffd7f-222">52.114.20.29</span></span>
- <span data-ttu-id="ffd7f-223">52.114.75.24</span><span class="sxs-lookup"><span data-stu-id="ffd7f-223">52.114.75.24</span></span>
- <span data-ttu-id="ffd7f-224">52.114.76.76</span><span class="sxs-lookup"><span data-stu-id="ffd7f-224">52.114.76.76</span></span>
- <span data-ttu-id="ffd7f-225">52.114.7.24</span><span class="sxs-lookup"><span data-stu-id="ffd7f-225">52.114.7.24</span></span>
- <span data-ttu-id="ffd7f-226">52.114.14.70</span><span class="sxs-lookup"><span data-stu-id="ffd7f-226">52.114.14.70</span></span>

<span data-ttu-id="ffd7f-227">Você precisa abrir portas para todos esses endereços IP no firewall para permitir o tráfego de entrada e saída de e para os endereços para sinalização.</span><span class="sxs-lookup"><span data-stu-id="ffd7f-227">You need to open ports for all these IP addresses in your firewall to allow incoming and outgoing traffic to and from the addresses for signaling.</span></span> <span data-ttu-id="ffd7f-228">Se o firewall for compatível com  nomes DNS, a sip-all.pstnhub.microsoft.com FQDN será resolvida para todos esses endereços IP.</span><span class="sxs-lookup"><span data-stu-id="ffd7f-228">If your firewall supports DNS names, the FQDN **sip-all.pstnhub.microsoft.com** resolves to all these IP addresses.</span></span> 

### <a name="office-365-gcc-dod-environment"></a><span data-ttu-id="ffd7f-229">Ambiente de DoD GCC do Office 365</span><span class="sxs-lookup"><span data-stu-id="ffd7f-229">Office 365 GCC DoD environment</span></span>

<span data-ttu-id="ffd7f-230">O ponto de conexão do Roteamento Direto é o seguinte FQDN:</span><span class="sxs-lookup"><span data-stu-id="ffd7f-230">The connection point for Direct Routing is the following FQDN:</span></span>

<span data-ttu-id="ffd7f-231">**sip.pstnhub.dod.teams.microsoft.us** – FQDN global.</span><span class="sxs-lookup"><span data-stu-id="ffd7f-231">**sip.pstnhub.dod.teams.microsoft.us** – Global FQDN.</span></span> <span data-ttu-id="ffd7f-232">Como o ambiente do Office 365 DoD existe apenas nos data centers dos EUA, não há FQDNs secundários e terciários.</span><span class="sxs-lookup"><span data-stu-id="ffd7f-232">As the Office 365 DoD environment exists only in the US data centers, there is no secondary and tertiary FQDNs.</span></span>

<span data-ttu-id="ffd7f-233">Os FQDNs – sip.pstnhub.dod.teams.microsoft.us serão resolvidos para um dos seguintes endereços IP:</span><span class="sxs-lookup"><span data-stu-id="ffd7f-233">The FQDNs – sip.pstnhub.dod.teams.microsoft.us will be resolved to one of the following IP addresses:</span></span>

- <span data-ttu-id="ffd7f-234">52.127.64.33</span><span class="sxs-lookup"><span data-stu-id="ffd7f-234">52.127.64.33</span></span>
- <span data-ttu-id="ffd7f-235">52.127.68.34</span><span class="sxs-lookup"><span data-stu-id="ffd7f-235">52.127.68.34</span></span>

<span data-ttu-id="ffd7f-236">Você precisa abrir portas para todos esses endereços IP no firewall para permitir o tráfego de entrada e saída de e para os endereços para sinalização.</span><span class="sxs-lookup"><span data-stu-id="ffd7f-236">You need to open ports for all these IP addresses in your firewall to allow incoming and outgoing traffic to and from the addresses for signaling.</span></span>  <span data-ttu-id="ffd7f-237">Se o firewall for compatível com nomes DNS, o FQDN sip.pstnhub.dod.teams.microsoft.us resolverá todos esses endereços IP.</span><span class="sxs-lookup"><span data-stu-id="ffd7f-237">If your firewall supports DNS names, the FQDN  sip.pstnhub.dod.teams.microsoft.us resolves to all these IP addresses.</span></span> 

### <a name="office-365-gcc-high-environment"></a><span data-ttu-id="ffd7f-238">Ambiente do Office 365 GCC High</span><span class="sxs-lookup"><span data-stu-id="ffd7f-238">Office 365 GCC High environment</span></span>

<span data-ttu-id="ffd7f-239">O ponto de conexão do Roteamento Direto é o seguinte FQDN:</span><span class="sxs-lookup"><span data-stu-id="ffd7f-239">The connection point for Direct Routing is the following FQDN:</span></span>

<span data-ttu-id="ffd7f-240">**sip.pstnhub.gov.teams.microsoft.us** – FQDN global.</span><span class="sxs-lookup"><span data-stu-id="ffd7f-240">**sip.pstnhub.gov.teams.microsoft.us** – Global FQDN.</span></span> <span data-ttu-id="ffd7f-241">Como o ambiente GCC High existe apenas nos data centers dos EUA, não há FQDNs secundários e terciários.</span><span class="sxs-lookup"><span data-stu-id="ffd7f-241">As the GCC High environment exists only in the US data centers, there is no secondary and tertiary FQDNs.</span></span>

<span data-ttu-id="ffd7f-242">Os FQDNs – sip.pstnhub.gov.teams.microsoft.us serão resolvidos para um dos seguintes endereços IP:</span><span class="sxs-lookup"><span data-stu-id="ffd7f-242">The FQDNs – sip.pstnhub.gov.teams.microsoft.us will be resolved to one of the following IP addresses:</span></span>

- <span data-ttu-id="ffd7f-243">52.127.88.59</span><span class="sxs-lookup"><span data-stu-id="ffd7f-243">52.127.88.59</span></span>
- <span data-ttu-id="ffd7f-244">52.127.92.64</span><span class="sxs-lookup"><span data-stu-id="ffd7f-244">52.127.92.64</span></span>

<span data-ttu-id="ffd7f-245">Você precisa abrir portas para todos esses endereços IP no firewall para permitir o tráfego de entrada e saída de e para os endereços para sinalização.</span><span class="sxs-lookup"><span data-stu-id="ffd7f-245">You need to open ports for all these IP addresses in your firewall to allow incoming and outgoing traffic to and from the addresses for signaling.</span></span>  <span data-ttu-id="ffd7f-246">Se o firewall for compatível com nomes DNS, o FQDN sip.pstnhub.gov.teams.microsoft.us resolverá para todos esses endereços IP.</span><span class="sxs-lookup"><span data-stu-id="ffd7f-246">If your firewall supports DNS names, the FQDN  sip.pstnhub.gov.teams.microsoft.us resolves to all these IP addresses.</span></span> 

## <a name="sip-signaling-ports"></a><span data-ttu-id="ffd7f-247">Sinalização SIP: Portas</span><span class="sxs-lookup"><span data-stu-id="ffd7f-247">SIP Signaling: Ports</span></span>

<span data-ttu-id="ffd7f-248">Os requisitos de portabilidade são os mesmos para todos os ambientes do Office 365 em que o Roteamento Direto é oferecido:</span><span class="sxs-lookup"><span data-stu-id="ffd7f-248">Port requirements are the same for all Office 365 environments where Direct Routing is offered:</span></span>
- <span data-ttu-id="ffd7f-249">Microsoft 365 ou Office 365</span><span class="sxs-lookup"><span data-stu-id="ffd7f-249">Microsoft 365 or Office 365</span></span>
- <span data-ttu-id="ffd7f-250">Cc do Office 365</span><span class="sxs-lookup"><span data-stu-id="ffd7f-250">Office 365 GCC</span></span>
- <span data-ttu-id="ffd7f-251">Office 365 GCC High</span><span class="sxs-lookup"><span data-stu-id="ffd7f-251">Office 365 GCC High</span></span>
- <span data-ttu-id="ffd7f-252">Office 365 DoD</span><span class="sxs-lookup"><span data-stu-id="ffd7f-252">Office 365 DoD</span></span>

<span data-ttu-id="ffd7f-253">Você deve usar as seguintes portas:</span><span class="sxs-lookup"><span data-stu-id="ffd7f-253">You must use the following ports:</span></span>

| <span data-ttu-id="ffd7f-254">Tráfego</span><span class="sxs-lookup"><span data-stu-id="ffd7f-254">Traffic</span></span> | <span data-ttu-id="ffd7f-255">De</span><span class="sxs-lookup"><span data-stu-id="ffd7f-255">From</span></span> | <span data-ttu-id="ffd7f-256">Até</span><span class="sxs-lookup"><span data-stu-id="ffd7f-256">To</span></span> | <span data-ttu-id="ffd7f-257">Porta de origem</span><span class="sxs-lookup"><span data-stu-id="ffd7f-257">Source port</span></span> | <span data-ttu-id="ffd7f-258">Porta de destino</span><span class="sxs-lookup"><span data-stu-id="ffd7f-258">Destination port</span></span>|
| :-------- | :-------- |:-----------|:--------|:---------|
<span data-ttu-id="ffd7f-259">SIP/TLS</span><span class="sxs-lookup"><span data-stu-id="ffd7f-259">SIP/TLS</span></span>| <span data-ttu-id="ffd7f-260">SIP Proxy</span><span class="sxs-lookup"><span data-stu-id="ffd7f-260">SIP Proxy</span></span> | <span data-ttu-id="ffd7f-261">Sbc</span><span class="sxs-lookup"><span data-stu-id="ffd7f-261">SBC</span></span> | <span data-ttu-id="ffd7f-262">1024 - 65535</span><span class="sxs-lookup"><span data-stu-id="ffd7f-262">1024 - 65535</span></span> | <span data-ttu-id="ffd7f-263">Definido no SBC</span><span class="sxs-lookup"><span data-stu-id="ffd7f-263">Defined on the SBC</span></span> |
| <span data-ttu-id="ffd7f-264">SIP/TLS</span><span class="sxs-lookup"><span data-stu-id="ffd7f-264">SIP/TLS</span></span> | <span data-ttu-id="ffd7f-265">Sbc</span><span class="sxs-lookup"><span data-stu-id="ffd7f-265">SBC</span></span> | <span data-ttu-id="ffd7f-266">SIP Proxy</span><span class="sxs-lookup"><span data-stu-id="ffd7f-266">SIP Proxy</span></span> | <span data-ttu-id="ffd7f-267">Definido no SBC</span><span class="sxs-lookup"><span data-stu-id="ffd7f-267">Defined on the SBC</span></span> | <span data-ttu-id="ffd7f-268">5061</span><span class="sxs-lookup"><span data-stu-id="ffd7f-268">5061</span></span> |


## <a name="media-traffic-ip-and-port-ranges"></a><span data-ttu-id="ffd7f-269">Tráfego de mídia: intervalos de IP e Porta</span><span class="sxs-lookup"><span data-stu-id="ffd7f-269">Media traffic: IP and Port ranges</span></span>

<span data-ttu-id="ffd7f-270">O tráfego de mídia fluirá entre o cliente SBC e o cliente do Teams se a conectividade direta estiver disponível ou por meio de Retransmissão de Transporte do Teams se o cliente não puder alcançar o SBC usando o endereço IP público.</span><span class="sxs-lookup"><span data-stu-id="ffd7f-270">Media traffic flows between the SBC and Teams client if direct connectivity is available or via Teams Transport Relays if the client cannot reach the SBC using the public IP address.</span></span>

### <a name="requirements-for-direct-media-traffic-between-the-teams-client-and-the-sbc"></a><span data-ttu-id="ffd7f-271">Requisitos para tráfego direto de mídia (entre o cliente do Teams e o SBC)</span><span class="sxs-lookup"><span data-stu-id="ffd7f-271">Requirements for direct media traffic (between the Teams client and the SBC)</span></span> 

<span data-ttu-id="ffd7f-272">O cliente deve ter acesso às portas especificadas (ver tabela) no endereço IP público do SBC.</span><span class="sxs-lookup"><span data-stu-id="ffd7f-272">The client must have access to the specified ports (see table) on the public IP address of the SBC.</span></span> 

<span data-ttu-id="ffd7f-273">Observação: se o cliente estiver em uma rede interna, a mídia fluirá para o endereço IP público do SBC.</span><span class="sxs-lookup"><span data-stu-id="ffd7f-273">Note: If the client is in an internal network, the media flows to the public IP address of the SBC.</span></span> <span data-ttu-id="ffd7f-274">Você pode configurar o fixamento de pelos em seu dispositivo NAT para que o tráfego nunca deixe o equipamento de rede corporativa.</span><span class="sxs-lookup"><span data-stu-id="ffd7f-274">You can configure hair pinning on your NAT device so traffic never leaves the enterprise network equipment.</span></span>

| <span data-ttu-id="ffd7f-275">Tráfego</span><span class="sxs-lookup"><span data-stu-id="ffd7f-275">Traffic</span></span> | <span data-ttu-id="ffd7f-276">De</span><span class="sxs-lookup"><span data-stu-id="ffd7f-276">From</span></span> | <span data-ttu-id="ffd7f-277">Até</span><span class="sxs-lookup"><span data-stu-id="ffd7f-277">To</span></span> | <span data-ttu-id="ffd7f-278">Porta de origem</span><span class="sxs-lookup"><span data-stu-id="ffd7f-278">Source port</span></span> | <span data-ttu-id="ffd7f-279">Porta de destino</span><span class="sxs-lookup"><span data-stu-id="ffd7f-279">Destination port</span></span>|
| :-------- | :-------- |:-----------|:--------|:---------|
<span data-ttu-id="ffd7f-280">UDP/SRTP</span><span class="sxs-lookup"><span data-stu-id="ffd7f-280">UDP/SRTP</span></span> | <span data-ttu-id="ffd7f-281">Cliente</span><span class="sxs-lookup"><span data-stu-id="ffd7f-281">Client</span></span> | <span data-ttu-id="ffd7f-282">Sbc</span><span class="sxs-lookup"><span data-stu-id="ffd7f-282">SBC</span></span> | <span data-ttu-id="ffd7f-283">50 000 – 50 019</span><span class="sxs-lookup"><span data-stu-id="ffd7f-283">50 000 – 50 019</span></span>  | <span data-ttu-id="ffd7f-284">Definido no SBC</span><span class="sxs-lookup"><span data-stu-id="ffd7f-284">Defined on the SBC</span></span> |
| <span data-ttu-id="ffd7f-285">UDP/SRTP</span><span class="sxs-lookup"><span data-stu-id="ffd7f-285">UDP/SRTP</span></span> | <span data-ttu-id="ffd7f-286">Sbc</span><span class="sxs-lookup"><span data-stu-id="ffd7f-286">SBC</span></span> | <span data-ttu-id="ffd7f-287">Cliente</span><span class="sxs-lookup"><span data-stu-id="ffd7f-287">Client</span></span> | <span data-ttu-id="ffd7f-288">Definido no SBC</span><span class="sxs-lookup"><span data-stu-id="ffd7f-288">Defined on the SBC</span></span> | <span data-ttu-id="ffd7f-289">50 000 – 50 019</span><span class="sxs-lookup"><span data-stu-id="ffd7f-289">50 000 – 50 019</span></span>  |


> [!NOTE]
> <span data-ttu-id="ffd7f-290">Se você tiver um dispositivo de rede que traduz as portas de origem do cliente, verifique se as portas traduzidas estão abertas entre o equipamento de rede e o SBC.</span><span class="sxs-lookup"><span data-stu-id="ffd7f-290">If you have a network device that translates the client's source ports, please make sure that translated ports are opened between the network equipment and the SBC.</span></span> 

### <a name="requirements-for-using-transport-relays"></a><span data-ttu-id="ffd7f-291">Requisitos para usar retransmissão de transporte</span><span class="sxs-lookup"><span data-stu-id="ffd7f-291">Requirements for using Transport Relays</span></span>

<span data-ttu-id="ffd7f-292">As Retransmissão de Transporte estão no mesmo intervalo que os Processadores de Mídia (para casos não ignorados):</span><span class="sxs-lookup"><span data-stu-id="ffd7f-292">Transport Relays are in the same range as Media Processors (for non-bypass cases):</span></span> 

### <a name="microsoft-365-office-365-and-office-365-gcc-environments"></a><span data-ttu-id="ffd7f-293">Ambientes do Microsoft 365, Office 365 e Office 365 GCC</span><span class="sxs-lookup"><span data-stu-id="ffd7f-293">Microsoft 365, Office 365, and Office 365 GCC environments</span></span>

- <span data-ttu-id="ffd7f-294">52.112.0.0 /14 (endereços IP de 52.112.0.1 a 52.115.255.254)</span><span class="sxs-lookup"><span data-stu-id="ffd7f-294">52.112.0.0 /14 (IP addresses from 52.112.0.1 to 52.115.255.254)</span></span>

## <a name="office-365-gcc-dod-environment"></a><span data-ttu-id="ffd7f-295">Ambiente de DoD GCC do Office 365</span><span class="sxs-lookup"><span data-stu-id="ffd7f-295">Office 365 GCC DoD environment</span></span>

- <span data-ttu-id="ffd7f-296">52.127.64.0/21</span><span class="sxs-lookup"><span data-stu-id="ffd7f-296">52.127.64.0/21</span></span>

### <a name="office-365-gcc-high-environment"></a><span data-ttu-id="ffd7f-297">Ambiente do Office 365 GCC High</span><span class="sxs-lookup"><span data-stu-id="ffd7f-297">Office 365 GCC High environment</span></span>

- <span data-ttu-id="ffd7f-298">52.127.88.0/21</span><span class="sxs-lookup"><span data-stu-id="ffd7f-298">52.127.88.0/21</span></span>


<span data-ttu-id="ffd7f-299">O intervalo de portas das Retransmissão de Transporte do Teams (aplicável a todos os ambientes) é mostrado na tabela a seguir:</span><span class="sxs-lookup"><span data-stu-id="ffd7f-299">The port range of the Teams Transport Relays (applicable to all environments) is shown in the following table:</span></span>


| <span data-ttu-id="ffd7f-300">Tráfego</span><span class="sxs-lookup"><span data-stu-id="ffd7f-300">Traffic</span></span> | <span data-ttu-id="ffd7f-301">De</span><span class="sxs-lookup"><span data-stu-id="ffd7f-301">From</span></span> | <span data-ttu-id="ffd7f-302">Até</span><span class="sxs-lookup"><span data-stu-id="ffd7f-302">To</span></span> | <span data-ttu-id="ffd7f-303">Porta de origem</span><span class="sxs-lookup"><span data-stu-id="ffd7f-303">Source port</span></span> | <span data-ttu-id="ffd7f-304">Porta de destino</span><span class="sxs-lookup"><span data-stu-id="ffd7f-304">Destination port</span></span>|
| :-------- | :-------- |:-----------|:--------|:---------|
<span data-ttu-id="ffd7f-305">UDP/SRTP</span><span class="sxs-lookup"><span data-stu-id="ffd7f-305">UDP/SRTP</span></span> | <span data-ttu-id="ffd7f-306">Retransmissão de Transporte</span><span class="sxs-lookup"><span data-stu-id="ffd7f-306">Transport Relay</span></span> | <span data-ttu-id="ffd7f-307">Sbc</span><span class="sxs-lookup"><span data-stu-id="ffd7f-307">SBC</span></span> | <span data-ttu-id="ffd7f-308">50 000 -59 999</span><span class="sxs-lookup"><span data-stu-id="ffd7f-308">50 000 -59 999</span></span>    | <span data-ttu-id="ffd7f-309">Definido no SBC</span><span class="sxs-lookup"><span data-stu-id="ffd7f-309">Defined on the SBC</span></span> |
| <span data-ttu-id="ffd7f-310">UDP/SRTP</span><span class="sxs-lookup"><span data-stu-id="ffd7f-310">UDP/SRTP</span></span> | <span data-ttu-id="ffd7f-311">Sbc</span><span class="sxs-lookup"><span data-stu-id="ffd7f-311">SBC</span></span> | <span data-ttu-id="ffd7f-312">Retransmissão de Transporte</span><span class="sxs-lookup"><span data-stu-id="ffd7f-312">Transport Relay</span></span> | <span data-ttu-id="ffd7f-313">Definido no SBC</span><span class="sxs-lookup"><span data-stu-id="ffd7f-313">Defined on the SBC</span></span> | <span data-ttu-id="ffd7f-314">50 000 – 59 999, 3478, 3479</span><span class="sxs-lookup"><span data-stu-id="ffd7f-314">50 000 – 59 999, 3478, 3479</span></span>     |


> [!NOTE]
> <span data-ttu-id="ffd7f-315">A Microsoft recomenda pelo menos duas portas por chamada simultânea no SBC.</span><span class="sxs-lookup"><span data-stu-id="ffd7f-315">Microsoft recommends at least two ports per concurrent call on the SBC.</span></span> <span data-ttu-id="ffd7f-316">Como a Microsoft tem duas versões de Retransmissão de Transporte, os seguintes são necessários:</span><span class="sxs-lookup"><span data-stu-id="ffd7f-316">Because Microsoft has two versions of Transport Relays, the following are required:</span></span>
> 
> - <span data-ttu-id="ffd7f-317">v4, que só pode funcionar com o intervalo de portas de 50 000 a 59 999</span><span class="sxs-lookup"><span data-stu-id="ffd7f-317">v4, which can only work with port range 50 000 to 59 999</span></span>
> 
> - <span data-ttu-id="ffd7f-318">v6, que funciona com as portas 3478, 3479</span><span class="sxs-lookup"><span data-stu-id="ffd7f-318">v6, which works with ports 3478, 3479</span></span>

<span data-ttu-id="ffd7f-319">No momento, o bypass de mídia só dá suporte à versão v4 das Retransmissão de Transporte.</span><span class="sxs-lookup"><span data-stu-id="ffd7f-319">At this time, media bypass only supports v4 version of Transport Relays.</span></span> <span data-ttu-id="ffd7f-320">Apresentaremos o suporte do v6 no futuro.</span><span class="sxs-lookup"><span data-stu-id="ffd7f-320">We will introduce support of v6 in the future.</span></span> 

<span data-ttu-id="ffd7f-321">Você precisa abrir as portas 3478 e 3479 para transição.</span><span class="sxs-lookup"><span data-stu-id="ffd7f-321">You need to open ports 3478 and 3479 for transitioning.</span></span> <span data-ttu-id="ffd7f-322">Quando a Microsoft introduz suporte para retransmissão de transporte v6 com Bypass de Mídia, você não precisará reconfigurar seu equipamento de rede ou SBCs.</span><span class="sxs-lookup"><span data-stu-id="ffd7f-322">When Microsoft introduces support for v6 Transport Relays with Media Bypass, you will not need to reconfigure your network equipment or SBCs.</span></span> 

### <a name="requirements-for-using-media-processors"></a><span data-ttu-id="ffd7f-323">Requisitos para usar processadores de mídia</span><span class="sxs-lookup"><span data-stu-id="ffd7f-323">Requirements for using media processors</span></span>

<span data-ttu-id="ffd7f-324">Os Processadores de Mídia estão sempre no caminho de mídia para aplicativos de voz e para clientes Web (por exemplo, clientes do Teams no Edge ou no Google Chrome).</span><span class="sxs-lookup"><span data-stu-id="ffd7f-324">Media Processors are always in the media path for voice applications and for Web clients (for example, Teams clients in Edge or Google Chrome).</span></span> <span data-ttu-id="ffd7f-325">Os requisitos são os mesmos para configurações que não ignoram.</span><span class="sxs-lookup"><span data-stu-id="ffd7f-325">The requirements are the same as for non-bypass configuration.</span></span>


<span data-ttu-id="ffd7f-326">O intervalo IP para tráfego de mídia é</span><span class="sxs-lookup"><span data-stu-id="ffd7f-326">The IP range for media traffic is</span></span> 

### <a name="office-365-and-office-365-gcc-environments"></a><span data-ttu-id="ffd7f-327">Ambientes do Office 365 e do Office 365 GCC</span><span class="sxs-lookup"><span data-stu-id="ffd7f-327">Office 365 and Office 365 GCC environments</span></span>

- <span data-ttu-id="ffd7f-328">52.112.0.0 /14 (endereços IP de 52.112.0.1 a 52.115.255.254)</span><span class="sxs-lookup"><span data-stu-id="ffd7f-328">52.112.0.0 /14 (IP addresses from 52.112.0.1 to 52.115.255.254)</span></span>

## <a name="office-365-gcc-dod-environment"></a><span data-ttu-id="ffd7f-329">Ambiente de DoD GCC do Office 365</span><span class="sxs-lookup"><span data-stu-id="ffd7f-329">Office 365 GCC DoD environment</span></span>

- <span data-ttu-id="ffd7f-330">52.127.64.0/21</span><span class="sxs-lookup"><span data-stu-id="ffd7f-330">52.127.64.0/21</span></span>

### <a name="office-365-gcc-high-environment"></a><span data-ttu-id="ffd7f-331">Ambiente do Office 365 GCC High</span><span class="sxs-lookup"><span data-stu-id="ffd7f-331">Office 365 GCC High environment</span></span>

- <span data-ttu-id="ffd7f-332">52.127.88.0/21</span><span class="sxs-lookup"><span data-stu-id="ffd7f-332">52.127.88.0/21</span></span>

<span data-ttu-id="ffd7f-333">O intervalo de portas dos Processadores de Mídia (aplicável a todos os ambientes) é mostrado na tabela a seguir:</span><span class="sxs-lookup"><span data-stu-id="ffd7f-333">The port range of the Media Processors (applicable to all environments) is shown in the following table:</span></span>

| <span data-ttu-id="ffd7f-334">Tráfego</span><span class="sxs-lookup"><span data-stu-id="ffd7f-334">Traffic</span></span> | <span data-ttu-id="ffd7f-335">De</span><span class="sxs-lookup"><span data-stu-id="ffd7f-335">From</span></span> | <span data-ttu-id="ffd7f-336">Até</span><span class="sxs-lookup"><span data-stu-id="ffd7f-336">To</span></span> | <span data-ttu-id="ffd7f-337">Porta de origem</span><span class="sxs-lookup"><span data-stu-id="ffd7f-337">Source port</span></span> | <span data-ttu-id="ffd7f-338">Porta de destino</span><span class="sxs-lookup"><span data-stu-id="ffd7f-338">Destination port</span></span>|
| :-------- | :-------- |:-----------|:--------|:---------|
<span data-ttu-id="ffd7f-339">UDP/SRTP</span><span class="sxs-lookup"><span data-stu-id="ffd7f-339">UDP/SRTP</span></span> | <span data-ttu-id="ffd7f-340">Processador de Mídia</span><span class="sxs-lookup"><span data-stu-id="ffd7f-340">Media Processor</span></span> | <span data-ttu-id="ffd7f-341">Sbc</span><span class="sxs-lookup"><span data-stu-id="ffd7f-341">SBC</span></span> | <span data-ttu-id="ffd7f-342">3478, 3479 e 49 152 – 53 247</span><span class="sxs-lookup"><span data-stu-id="ffd7f-342">3478, 3479 and 49 152 – 53 247</span></span>    | <span data-ttu-id="ffd7f-343">Definido no SBC</span><span class="sxs-lookup"><span data-stu-id="ffd7f-343">Defined on the SBC</span></span> |
| <span data-ttu-id="ffd7f-344">UDP/SRTP</span><span class="sxs-lookup"><span data-stu-id="ffd7f-344">UDP/SRTP</span></span> | <span data-ttu-id="ffd7f-345">Sbc</span><span class="sxs-lookup"><span data-stu-id="ffd7f-345">SBC</span></span> | <span data-ttu-id="ffd7f-346">Processador de Mídia</span><span class="sxs-lookup"><span data-stu-id="ffd7f-346">Media Processor</span></span> | <span data-ttu-id="ffd7f-347">Definido no SBC</span><span class="sxs-lookup"><span data-stu-id="ffd7f-347">Defined on the SBC</span></span> | <span data-ttu-id="ffd7f-348">3478, 3479 e 49 152 – 53 247</span><span class="sxs-lookup"><span data-stu-id="ffd7f-348">3478, 3479 and 49 152 – 53 247</span></span>     |

## <a name="configure-separate-trunks-for-media-bypass-and-non-media-bypass"></a><span data-ttu-id="ffd7f-349">Configurar troncos separados para bypass de mídia e bypass sem mídia</span><span class="sxs-lookup"><span data-stu-id="ffd7f-349">Configure separate trunks for media bypass and non-media bypass</span></span>  

<span data-ttu-id="ffd7f-350">Se estiver migrando para o bypass de mídia de bypass que não seja mídia e quiser confirmar a funcionalidade antes de migrar todo o uso para bypass de mídia, você pode criar um tronco separado e separar a política de Roteamento de Voz Online para rotear para o tronco de bypass de mídia e atribuir a usuários específicos.</span><span class="sxs-lookup"><span data-stu-id="ffd7f-350">If you are migrating to media bypass from non-media bypass and want to confirm functionality before migrating all usage to media bypass, you can create a separate trunk and separate Online Voice Routing policy to route to the media bypass trunk and assign to specific users.</span></span> 

<span data-ttu-id="ffd7f-351">Etapas de configuração de alto nível:</span><span class="sxs-lookup"><span data-stu-id="ffd7f-351">High-level configuration steps:</span></span>

- <span data-ttu-id="ffd7f-352">Identifique os usuários para testar o bypass de mídia.</span><span class="sxs-lookup"><span data-stu-id="ffd7f-352">Identify users to test media bypass.</span></span>

- <span data-ttu-id="ffd7f-353">Crie dois troncos separados com FQDNs diferentes: um habilitado para bypass de mídia; o outro não.</span><span class="sxs-lookup"><span data-stu-id="ffd7f-353">Create two separate trunks with different FQDNs: one enabled for media bypass; the other not.</span></span> 

  <span data-ttu-id="ffd7f-354">Ambos os troncos apontam para o mesmo SBC.</span><span class="sxs-lookup"><span data-stu-id="ffd7f-354">Both trunks point to the same SBC.</span></span> <span data-ttu-id="ffd7f-355">As portas para sinalização SIP TLS devem ser diferentes.</span><span class="sxs-lookup"><span data-stu-id="ffd7f-355">The ports for TLS SIP signaling must be different.</span></span> <span data-ttu-id="ffd7f-356">As portas para mídia devem ser as mesmas.</span><span class="sxs-lookup"><span data-stu-id="ffd7f-356">The ports for media must be the same.</span></span>

- <span data-ttu-id="ffd7f-357">Crie uma nova política de Roteamento de Voz Online e atribua o tronco de bypass de mídia às rotas correspondentes associadas ao uso de PSTN para essa política.</span><span class="sxs-lookup"><span data-stu-id="ffd7f-357">Create a new Online Voice Routing policy and assign the media bypass trunk to the corresponding routes associated with the PSTN usage for this policy.</span></span>

- <span data-ttu-id="ffd7f-358">Atribua a nova política de Roteamento de Voz Online aos usuários que você identificou para testar o bypass de mídia.</span><span class="sxs-lookup"><span data-stu-id="ffd7f-358">Assign the new Online Voice Routing policy to users you have identified to test media bypass.</span></span>

<span data-ttu-id="ffd7f-359">O exemplo a seguir ilustra essa lógica.</span><span class="sxs-lookup"><span data-stu-id="ffd7f-359">The example below illustrates this logic.</span></span>

| <span data-ttu-id="ffd7f-360">Conjunto de usuários</span><span class="sxs-lookup"><span data-stu-id="ffd7f-360">Set of users</span></span> | <span data-ttu-id="ffd7f-361">Número de usuários</span><span class="sxs-lookup"><span data-stu-id="ffd7f-361">Number of users</span></span> | <span data-ttu-id="ffd7f-362">FQDN do tronco atribuído no OVRP</span><span class="sxs-lookup"><span data-stu-id="ffd7f-362">Trunk FQDN assigned in OVRP</span></span> | <span data-ttu-id="ffd7f-363">Ignorar mídia habilitado</span><span class="sxs-lookup"><span data-stu-id="ffd7f-363">Media bypass enabled</span></span> |
| :------------ |:----------------- |:--------------|:--------------|
<span data-ttu-id="ffd7f-364">Usuários com tronco de bypass que não seja mídia</span><span class="sxs-lookup"><span data-stu-id="ffd7f-364">Users with non-media bypass trunk</span></span> | <span data-ttu-id="ffd7f-365">980</span><span class="sxs-lookup"><span data-stu-id="ffd7f-365">980</span></span> | <span data-ttu-id="ffd7f-366">sbc1.contoso.com:5060</span><span class="sxs-lookup"><span data-stu-id="ffd7f-366">sbc1.contoso.com:5060</span></span> | <span data-ttu-id="ffd7f-367">Verdade</span><span class="sxs-lookup"><span data-stu-id="ffd7f-367">true</span></span>
<span data-ttu-id="ffd7f-368">Usuários com tronco de bypass de mídia</span><span class="sxs-lookup"><span data-stu-id="ffd7f-368">Users with media bypass trunk</span></span> | <span data-ttu-id="ffd7f-369">20</span><span class="sxs-lookup"><span data-stu-id="ffd7f-369">20</span></span> | <span data-ttu-id="ffd7f-370">sbc2.contoso.com:5061</span><span class="sxs-lookup"><span data-stu-id="ffd7f-370">sbc2.contoso.com:5061</span></span> | <span data-ttu-id="ffd7f-371">False</span><span class="sxs-lookup"><span data-stu-id="ffd7f-371">false</span></span> | 

<span data-ttu-id="ffd7f-372">Ambos os troncos podem apontar para o mesmo SBC com o mesmo endereço IP público.</span><span class="sxs-lookup"><span data-stu-id="ffd7f-372">Both trunks can point to the same SBC with the same public IP address.</span></span> <span data-ttu-id="ffd7f-373">As portas de sinalização TLS no SBC devem ser diferentes, conforme mostrado no diagrama a seguir.</span><span class="sxs-lookup"><span data-stu-id="ffd7f-373">The TLS signaling ports on the SBC must be different, as shown in the following diagram.</span></span> <span data-ttu-id="ffd7f-374">Observe que você precisará garantir que seu certificado seja compatível com ambos os troncos.</span><span class="sxs-lookup"><span data-stu-id="ffd7f-374">Note you will need to make sure that your certificate supports both trunks.</span></span> <span data-ttu-id="ffd7f-375">Em SAN, você precisa ter dois nomes (**sbc1.contoso.com** e **sbc2.contoso.com**) ou ter um certificado curinga.</span><span class="sxs-lookup"><span data-stu-id="ffd7f-375">In SAN, you need to have two names (**sbc1.contoso.com** and **sbc2.contoso.com**) or have a wildcard certificate.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="ffd7f-376">![Mostra que os dois troncos podem apontar para o mesmo SBC com o mesmo IP público](media/direct-routing-media-bypass-7.png)</span><span class="sxs-lookup"><span data-stu-id="ffd7f-376">![Shows both trunks can point to the same SBC with the same public IP](media/direct-routing-media-bypass-7.png)</span></span>

<span data-ttu-id="ffd7f-377">Para obter informações sobre como configurar dois troncos no mesmo SBC, consulte a documentação fornecida pelo fornecedor do SBC:</span><span class="sxs-lookup"><span data-stu-id="ffd7f-377">For information about how to configure two trunks on the same SBC, see the documentation provided by your SBC vendor:</span></span>

 - [<span data-ttu-id="ffd7f-378">Documentação de implantação de AudioCodes</span><span class="sxs-lookup"><span data-stu-id="ffd7f-378">AudioCodes deployment documentation</span></span>](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/direct-routing-for-microsoft-teams)
- [<span data-ttu-id="ffd7f-379">Documentação de implantação oracle</span><span class="sxs-lookup"><span data-stu-id="ffd7f-379">Oracle deployment documentation</span></span>](https://www.oracle.com/industries/communications/enterprise-session-border-controller/microsoft.html)
- [<span data-ttu-id="ffd7f-380">Documentação de implantação de Comunicações da Faixa de Opções</span><span class="sxs-lookup"><span data-stu-id="ffd7f-380">Ribbon Communications deployment documentation</span></span>](https://ribboncommunications.com/solutions/enterprise-solutions/microsoft-solutions/direct-routing-microsoft-teams-calling)
- [<span data-ttu-id="ffd7f-381">Documentação de implantação do TE-Systems (qualquernode)</span><span class="sxs-lookup"><span data-stu-id="ffd7f-381">TE-Systems (anynode) deployment documentation</span></span>](https://www.anynode.de/anynode-and-microsoft-teams/)

## <a name="client-endpoints-supported-with-media-bypass"></a><span data-ttu-id="ffd7f-382">Pontos de extremidade do cliente com suporte com bypass de mídia</span><span class="sxs-lookup"><span data-stu-id="ffd7f-382">Client endpoints supported with media bypass</span></span>

<span data-ttu-id="ffd7f-383">O bypass de mídia é compatível com todos os clientes autônomos da área de trabalho do Teams, clientes Android e iOS e dispositivos de telefone do Teams.</span><span class="sxs-lookup"><span data-stu-id="ffd7f-383">Media bypass is supported with all standalone Teams Desktop clients, Android and iOS clients and Teams Phone Devices.</span></span> 

<span data-ttu-id="ffd7f-384">Para todos os outros pontos de extremidade que não suportam bypass de mídia, converteremos a chamada em não ignorar, mesmo que ela seja iniciada como uma chamada de bypass.</span><span class="sxs-lookup"><span data-stu-id="ffd7f-384">For all other endpoints that do not support media bypass, we will convert the call to non-bypass even if it started as a bypass call.</span></span> <span data-ttu-id="ffd7f-385">Isso acontece automaticamente e não requer ações do administrador.</span><span class="sxs-lookup"><span data-stu-id="ffd7f-385">This happens automatically and does not require any actions from the administrator.</span></span> <span data-ttu-id="ffd7f-386">Isso inclui telefones Skype for Business 3PIP e Clientes Web do Teams que são compatíveis com chamadas de Roteamento Direto (clientes baseados na WebRTC que executam no Microsoft Edge, Google Chrome, Mozilla Firefox).</span><span class="sxs-lookup"><span data-stu-id="ffd7f-386">This includes Skype for Business 3PIP Phones, and Teams Web Clients that support Direct Routing calling (WebRTC based clients running on Microsoft Edge, Google Chrome, Mozilla Firefox).</span></span> 
 
## <a name="see-also"></a><span data-ttu-id="ffd7f-387">Confira também</span><span class="sxs-lookup"><span data-stu-id="ffd7f-387">See also</span></span>

[<span data-ttu-id="ffd7f-388">Configurar o bypass de mídia com Roteamento Direto</span><span class="sxs-lookup"><span data-stu-id="ffd7f-388">Configure media bypass with Direct Routing</span></span>](direct-routing-configure-media-bypass.md)


