---
title: Planejar o bypass de mídia com Roteamento Direto
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.audience: ITPro
ms.reviewer: NMuravlyannikov
ms.topic: article
ms.service:
- msteams
ms.prod: skype-for-business-itpro
localization_priority: Normal
search.appverid: MET150
ms.collection: Teams_ITAdmin_Help
appliesto:
- Microsoft Teams
description: Leia este tópico para saber como planejar o bypass de mídia com roteamento direto de sistema do telefone.
ms.openlocfilehash: 308150121733f5f135d248404c663634ddaeea7c
ms.sourcegitcommit: 58fec9aebd80029e1f1e71376efe222f9abf707e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/08/2019
ms.locfileid: "31517243"
---
# <a name="plan-for-media-bypass-with-direct-routing"></a><span data-ttu-id="afa0b-103">Planejar o bypass de mídia com Roteamento Direto</span><span class="sxs-lookup"><span data-stu-id="afa0b-103">Plan for media bypass with Direct Routing</span></span>

## <a name="about-media-bypass-with-direct-routing"></a><span data-ttu-id="afa0b-104">Sobre o bypass de mídia com o roteamento direto</span><span class="sxs-lookup"><span data-stu-id="afa0b-104">About media bypass with Direct Routing</span></span>

<span data-ttu-id="afa0b-105">Bypass de mídia permite diminuir o caminho de tráfego de mídia e reduzir o número de saltos em trânsito para melhor desempenho.</span><span class="sxs-lookup"><span data-stu-id="afa0b-105">Media bypass enables you to shorten the path of media traffic and reduce the number of hops in transit for better performance.</span></span> <span data-ttu-id="afa0b-106">Com o bypass de mídia, será mantida entre o controlador de borda de sessão (SBC) e o cliente em vez de enviá-la por meio do sistema de telefone da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="afa0b-106">With media bypass, media is kept between the Session Border Controller (SBC) and the client instead of sending it via the Microsoft Phone System.</span></span> <span data-ttu-id="afa0b-107">Para configurar o media bypass, o SBC e o cliente devem ser no mesmo local ou na rede.</span><span class="sxs-lookup"><span data-stu-id="afa0b-107">To configure media bypass, the SBC and the client must be in the same location or network.</span></span>

<span data-ttu-id="afa0b-108">Você pode controlar o bypass de mídia para cada SBC usando o comando **Set-CSOnlinePSTNGateway** com o parâmetro **- MediaBypass** definido como true ou false.</span><span class="sxs-lookup"><span data-stu-id="afa0b-108">You can control media bypass for each SBC by using the **Set-CSOnlinePSTNGateway** command with the **-MediaBypass** parameter set to true or false.</span></span> <span data-ttu-id="afa0b-109">Se você habilitar o bypass de mídia, isso significa que todo o tráfego de mídia permanecerão dentro da rede corporativa.</span><span class="sxs-lookup"><span data-stu-id="afa0b-109">If you enable media bypass, this does not mean that all media traffic will stay within the corporate network.</span></span> <span data-ttu-id="afa0b-110">Este artigo descreve o fluxo de chamadas em diferentes cenários.</span><span class="sxs-lookup"><span data-stu-id="afa0b-110">This article describes the call flow in different scenarios.</span></span>    

<span data-ttu-id="afa0b-111">Os diagramas a seguir ilustram a diferença no fluxo de chamadas com e sem desvio de mídia.</span><span class="sxs-lookup"><span data-stu-id="afa0b-111">The diagrams below illustrate the difference in call flow with and without media bypass.</span></span>

<span data-ttu-id="afa0b-112">Sem bypass de mídia, quando um cliente faz ou recebe uma chamada, sinalização e mídia flua entre o SBC, o sistema de telefone da Microsoft e o cliente de equipes, conforme mostrado no diagrama a seguir:</span><span class="sxs-lookup"><span data-stu-id="afa0b-112">Without media bypass, when a client makes or receives a call, both signaling and media flow between the SBC, the Microsoft Phone System, and the Teams client, as shown in the following diagram:</span></span>

![Mostra a sinalização e fluxo de mídia sem desvio de mídia](media/direct-routing-media-bypass-1.png)


<span data-ttu-id="afa0b-114">Mas vamos supor que um usuário está na mesma rede como o SBC ou construção.</span><span class="sxs-lookup"><span data-stu-id="afa0b-114">But let's assume that a user is in the same building or network as the SBC.</span></span> <span data-ttu-id="afa0b-115">Por exemplo, suponha que um usuário que está em um edifício no faz de Frankfurt uma chamada para um usuário por PSTN:</span><span class="sxs-lookup"><span data-stu-id="afa0b-115">For example, assume a user who is in a building in Frankfurt makes a call to a PSTN user:</span></span> 

- <span data-ttu-id="afa0b-116">**Sem media bypass**, mídia fluirá via Amsterdã ou Dublin (onde os data centers da Microsoft estão implantados) e voltar para o SBC em Frankfurt.</span><span class="sxs-lookup"><span data-stu-id="afa0b-116">**Without media bypass**, media will flow via either Amsterdam or Dublin (where Microsoft datacenters are deployed) and back to the SBC in Frankfurt.</span></span> 

  <span data-ttu-id="afa0b-117">O datacenter na Europa está selecionado porque o SBC está na Europa e a Microsoft usa o datacenter mais próximo ao SBC.</span><span class="sxs-lookup"><span data-stu-id="afa0b-117">The datacenter in Europe is selected because the SBC is in Europe, and Microsoft uses the datacenter closest to the SBC.</span></span> <span data-ttu-id="afa0b-118">Embora essa abordagem não afeta a qualidade da chamada devido à otimização de fluxo de tráfego dentro de redes Microsoft na maioria das regiões, o tráfego tem um loop desnecessário.</span><span class="sxs-lookup"><span data-stu-id="afa0b-118">While this approach does not affect call quality due to optimization of traffic flow within Microsoft networks in most geographies, the traffic has an unnecessary loop.</span></span>     

- <span data-ttu-id="afa0b-119">**Com o media bypass**, a mídia é mantida diretamente entre o usuário de equipes e o SBC, conforme mostrado no diagrama a seguir:</span><span class="sxs-lookup"><span data-stu-id="afa0b-119">**With media bypass**, the media is kept directly between the Teams user and the SBC as shown in the following diagram:</span></span>

![Mostra a sinalização e o fluxo de mídia com bypass de mídia](media/direct-routing-media-bypass-2.png)

<span data-ttu-id="afa0b-121">Protocolos aproveita chamados conectividade ICE (estabelecimento interativa) no cliente de equipes e ICE luz do SBC de desvio de mídia.</span><span class="sxs-lookup"><span data-stu-id="afa0b-121">Media bypass leverages protocols called Interactive Connectivity Establishment (ICE) on the Teams client and ICE light on the SBC.</span></span> <span data-ttu-id="afa0b-122">Esses protocolos habilite o roteamento direto usar o caminho de mídia mais direto para a melhor qualidade.</span><span class="sxs-lookup"><span data-stu-id="afa0b-122">These protocols enable Direct Routing to use the most direct media path for optimal quality.</span></span> <span data-ttu-id="afa0b-123">ICE e ICE Lite são WebRTC padrões.</span><span class="sxs-lookup"><span data-stu-id="afa0b-123">ICE and ICE Lite are WebRTC standards.</span></span> <span data-ttu-id="afa0b-124">Para obter informações detalhadas sobre esses protocolos, consulte RFC 5245.</span><span class="sxs-lookup"><span data-stu-id="afa0b-124">For detailed information about these protocols, see RFC 5245.</span></span>


## <a name="call-flow-and-firewall-planning"></a><span data-ttu-id="afa0b-125">Planejamento de firewall e de fluxo de chamadas</span><span class="sxs-lookup"><span data-stu-id="afa0b-125">Call flow and firewall planning</span></span>

<span data-ttu-id="afa0b-126">Fluxo de chamadas e planejamento de firewall depende se o usuário tem acesso direto para o endereço IP público do SBC e se o usuário está dentro ou fora da rede.</span><span class="sxs-lookup"><span data-stu-id="afa0b-126">Call flow and firewall planning depends on whether the user has direct access to the public IP address of the SBC, and whether the user is inside or outside of the network.</span></span>

### <a name="call-flow-if-the-user-has-direct-access-to-the-public-ip-address-of-the-sbc"></a><span data-ttu-id="afa0b-127">Fluxo de chamadas se o usuário tem acesso direto para o endereço IP público do SBC</span><span class="sxs-lookup"><span data-stu-id="afa0b-127">Call flow if the user has direct access to the public IP address of the SBC</span></span>

<span data-ttu-id="afa0b-128">Se o usuário tem acesso direto para o endereço IP público do SBC, o fluxo de chamadas é o seguinte:</span><span class="sxs-lookup"><span data-stu-id="afa0b-128">If the user has direct access to the public IP address of the SBC, the call flow is as follows:</span></span>

- <span data-ttu-id="afa0b-129">Bypass de mídia, o cliente de equipes deve ter acesso ao endereço IP público do SBC até mesmo a partir de uma rede interna.</span><span class="sxs-lookup"><span data-stu-id="afa0b-129">For media bypass, the Teams client must have access to the public IP address of the SBC even from an internal network.</span></span> <span data-ttu-id="afa0b-130">Se a mídia direta não for desejada, a mídia pode fluir via retransmissões de transporte.</span><span class="sxs-lookup"><span data-stu-id="afa0b-130">If direct media is not desired, the media can flow via Transport Relays.</span></span>

- <span data-ttu-id="afa0b-131">Esta é a solução recomendada quando um usuário estar participando de rede como o SBC e/ou mesmo prédio – remova componentes do Microsoft Cloud o caminho de mídia.</span><span class="sxs-lookup"><span data-stu-id="afa0b-131">This is the recommended solution when a user is in the same building and/or network as the SBC – remove Microsoft Cloud components from the media path.</span></span>

- <span data-ttu-id="afa0b-132">Sinalização sempre flui por meio de nuvem da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="afa0b-132">Signaling always flows via the Microsoft cloud.</span></span>

<span data-ttu-id="afa0b-133">O diagrama a seguir mostra o fluxo de chamadas quando o desvio de mídia está habilitado, o cliente é interno e o cliente pode alcançar o endereço IP público do SBC (direct media):</span><span class="sxs-lookup"><span data-stu-id="afa0b-133">The following diagram shows call flow when media bypass is enabled, the client is internal, and the client can reach the public IP address of the SBC (direct media):</span></span> 

- <span data-ttu-id="afa0b-134">As setas e os valores numéricos dos caminhos estejam de acordo com o documento Microsoft equipes Online fluxos de chamada.</span><span class="sxs-lookup"><span data-stu-id="afa0b-134">The arrows and numeric values of the paths are in accordance with the Microsoft Teams Online Call Flows document.</span></span>

- <span data-ttu-id="afa0b-135">Sempre a sinalização SIP leva caminhos 4 e 4' (dependendo da direção do tráfego).</span><span class="sxs-lookup"><span data-stu-id="afa0b-135">The SIP signaling always takes paths 4 and 4’ (depending on the direction of the traffic).</span></span> <span data-ttu-id="afa0b-136">Mídia permanece local e leva 5b caminho.</span><span class="sxs-lookup"><span data-stu-id="afa0b-136">Media stays local and takes path 5b.</span></span>

![Mostra o fluxo de chamadas com Bypass de mídia habilitado, o cliente interno e pode alcançar o IP público do controlador de borda de sessão (direct mídia)](media/direct-routing-media-bypass-3.png)


### <a name="call-flow-if-the-user-does-not-have-access-to-the-public-ip-address-of-the-sbc"></a><span data-ttu-id="afa0b-138">Fluxo de chamadas se o usuário não tem acesso para o endereço IP público do SBC</span><span class="sxs-lookup"><span data-stu-id="afa0b-138">Call flow if the user does not have access to the public IP address of the SBC</span></span>

<span data-ttu-id="afa0b-139">A seguir descreve o fluxo de chamada se o usuário não tem acesso para o endereço IP público do SBC.</span><span class="sxs-lookup"><span data-stu-id="afa0b-139">The following describes call flow if the user does not have access to the public IP address of the SBC.</span></span> 

<span data-ttu-id="afa0b-140">Por exemplo, suponha que o usuário seja externo, e o administrador de locatário decidiu não abrir o endereço IP público do SBC para todos na Internet, mas somente para o Microsoft Cloud.</span><span class="sxs-lookup"><span data-stu-id="afa0b-140">For example, assume the user is external, and the tenant administrator decided not to open the public IP address of the SBC to everyone in the Internet, but only to the Microsoft Cloud.</span></span> <span data-ttu-id="afa0b-141">Os componentes internos do tráfego podem fluir através de retransmissões de transporte de equipes.</span><span class="sxs-lookup"><span data-stu-id="afa0b-141">The internal components of traffic can flow via the Teams Transport Relays.</span></span> <span data-ttu-id="afa0b-142">Esta é a configuração recomendada para usuários fora da rede corporativa.</span><span class="sxs-lookup"><span data-stu-id="afa0b-142">This is the recommended configuration for users outside of the corporate network.</span></span> <span data-ttu-id="afa0b-143">Considere o seguinte:</span><span class="sxs-lookup"><span data-stu-id="afa0b-143">Consider the following:</span></span>

- <span data-ttu-id="afa0b-144">As equipes retransmissões de transporte são usadas.</span><span class="sxs-lookup"><span data-stu-id="afa0b-144">Teams Transport Relays are used.</span></span>

- <span data-ttu-id="afa0b-145">Bypass de mídia, a Microsoft usa uma versão do retransmissões de transporte que requer a abertura de portas 50 000 para 59 999 entre as equipes transporte retransmissões e o SBC (no futuro que pretendemos para mover para a versão que exige portas apenas 3478 e 3479).</span><span class="sxs-lookup"><span data-stu-id="afa0b-145">For media bypass, Microsoft uses a version of Transport Relays that requires opening ports 50 000 to 59 999 between the Teams Transport Relays and the SBC (in the future we plan to move to the version which requires only 3478 and 3479 ports).</span></span>

- <span data-ttu-id="afa0b-146">Para fins de otimização de mídia, a Microsoft recomenda abrindo o endereço IP público do SBC apenas ao transporte as equipes retransmissões.</span><span class="sxs-lookup"><span data-stu-id="afa0b-146">For media optimization purposes, Microsoft recommends opening the public IP address of the SBC only to Teams Transport Relays.</span></span> <span data-ttu-id="afa0b-147">Para clientes fora da rede corporativa, a Microsoft recomenda usar retransmissões de transporte em vez de está atingindo o endereço IP público do SBC diretamente.</span><span class="sxs-lookup"><span data-stu-id="afa0b-147">For clients outside of the corporate network, Microsoft recommends using Transport Relays instead of reaching the public IP address of the SBC directly.</span></span>

<span data-ttu-id="afa0b-148">O diagrama a seguir mostra o fluxo de chamadas quando o desvio de mídia está habilitado, o cliente for externo e o cliente não consegue acessar o endereço IP público do controlador de borda de sessão (mídia é retransmitida por equipes retransmissão de transporte).</span><span class="sxs-lookup"><span data-stu-id="afa0b-148">The following diagram shows call flow when media bypass is enabled, the client is external, and the client cannot reach the public IP address of the Session Border Controller (media is relayed by Teams Transport Relay).</span></span>

- <span data-ttu-id="afa0b-149">As setas e os valores numéricos dos caminhos estejam de acordo com o documento Microsoft equipes Online fluxos de chamada.</span><span class="sxs-lookup"><span data-stu-id="afa0b-149">The arrows and numeric values of the paths are in accordance with the Microsoft Teams Online Call Flows document.</span></span>

- <span data-ttu-id="afa0b-150">Mídia é retransmitida via caminhos 3, 3', 4 e 4'</span><span class="sxs-lookup"><span data-stu-id="afa0b-150">Media is relayed via paths 3, 3', 4 and 4'</span></span>

![Mostra o fluxo de chamadas se o usuário não tem acesso ao IP público do SBC)](media/direct-routing-media-bypass-4.png)


### <a name="call-flow-if-a-user-is-outside-the-network-and-has-access-to-the-public-ip-of-the-sbc"></a><span data-ttu-id="afa0b-152">Fluxo de chamadas se um usuário está fora da rede e tenha acesso ao IP público do SBC</span><span class="sxs-lookup"><span data-stu-id="afa0b-152">Call flow if a user is outside the network and has access to the public IP of the SBC</span></span>

> [!NOTE]
> <span data-ttu-id="afa0b-153">Isso não é uma configuração recomendada porque ele não tirar proveito das equipes retransmissões de transporte.</span><span class="sxs-lookup"><span data-stu-id="afa0b-153">This is not a recommended configuration because it does not take advantage of Teams Transport Relays.</span></span> <span data-ttu-id="afa0b-154">Em vez disso, você deve considerar o cenário anterior, onde o usuário não tem acesso para o endereço IP público do SBC.</span><span class="sxs-lookup"><span data-stu-id="afa0b-154">Instead, you should consider the previous scenario where the user does not have access to the public IP address of the SBC.</span></span> 

<span data-ttu-id="afa0b-155">O diagrama a seguir mostra o fluxo de chamadas quando o desvio de mídia está habilitado, o cliente for externo e o cliente pode alcançar o endereço IP público do SBC (direct mídia).</span><span class="sxs-lookup"><span data-stu-id="afa0b-155">The following diagram shows call flow when media bypass is enabled, the client is external, and the client can reach the public IP address of the SBC (direct media).</span></span>

- <span data-ttu-id="afa0b-156">As setas e os valores numéricos dos caminhos estejam de acordo com o documento Microsoft equipes Online fluxos de chamada.</span><span class="sxs-lookup"><span data-stu-id="afa0b-156">The arrows and numeric values of the paths are in accordance with the Microsoft Teams Online Call Flows document.</span></span>

- <span data-ttu-id="afa0b-157">Sempre a sinalização SIP leva caminhos 3 e 3' (dependendo da direção do tráfego).</span><span class="sxs-lookup"><span data-stu-id="afa0b-157">The SIP signaling always takes paths 3 and 3’ (depending on the direction of the traffic).</span></span> <span data-ttu-id="afa0b-158">Fluxos de mídia usando o caminho 2.</span><span class="sxs-lookup"><span data-stu-id="afa0b-158">Media flows using path 2.</span></span>

![Mostra o fluxo de chamadas se o usuário não tem acesso ao IP público do SBC)](media/direct-routing-media-bypass-5.png)


## <a name="use-of-media-processors-and-transport-relays"></a><span data-ttu-id="afa0b-160">Uso de processadores de mídia e retransmissões de transporte</span><span class="sxs-lookup"><span data-stu-id="afa0b-160">Use of Media Processors and Transport Relays</span></span>

<span data-ttu-id="afa0b-161">Existem dois componentes no Microsoft Cloud que podem ser no caminho do tráfego de mídia: processadores de mídia e retransmissões de transporte.</span><span class="sxs-lookup"><span data-stu-id="afa0b-161">There are two components in the Microsoft Cloud that can be in the path of media traffic: Media Processors and Transport Relays.</span></span> 

- <span data-ttu-id="afa0b-162">O processador de mídia é um componente de voltada público que trata a mídia em casos não ignorar e trata a mídia para aplicativos de voz.</span><span class="sxs-lookup"><span data-stu-id="afa0b-162">The Media Processor is a public facing component that handles media in non-bypass cases and handles media for voice applications.</span></span>

   <span data-ttu-id="afa0b-163">Processadores de mídia são sempre no caminho para o usuário final não ignorada chamadas, mas nunca no caminho para chamadas ignorados.</span><span class="sxs-lookup"><span data-stu-id="afa0b-163">Media Processors are always in the path for end user non-bypassed calls, but never in the path for bypassed calls.</span></span> <span data-ttu-id="afa0b-164">Processadores de mídia são sempre no caminho para todos os aplicativos de voz como Call Park, atendedor automático da organizacional e filas de chamada.</span><span class="sxs-lookup"><span data-stu-id="afa0b-164">Media Processors are always in the path for all voice applications such as Call Park, Organizational Auto Attendant, and Call Queues.</span></span>

- <span data-ttu-id="afa0b-165">A retransmissão de transporte é usada para se conectar ao serviço de transporte mais próximos, para enviar o tráfego de tempo real.</span><span class="sxs-lookup"><span data-stu-id="afa0b-165">The Transport Relay is used to connect to the closest Transport Service to send real time traffic.</span></span>

   <span data-ttu-id="afa0b-166">Transporte retransmissões podem ou não ser no caminho para chamadas ignorados – provenientes de ou destinados aos usuários finais – dependendo de onde o usuário está e como a rede está configurada.</span><span class="sxs-lookup"><span data-stu-id="afa0b-166">Transport Relays might or might not be in the path for bypassed calls--originating from or destined to end users--depending on where the user is and how the network is configured .</span></span>

<span data-ttu-id="afa0b-167">O diagrama a seguir mostra dois fluxos de chamada – um com bypass de mídia habilitado e o segundo com mídia desvio desabilitado.</span><span class="sxs-lookup"><span data-stu-id="afa0b-167">The following diagram shows two call flows – one with media bypass enabled and the second with media bypass disabled.</span></span> <span data-ttu-id="afa0b-168">Observação o diagrama apenas ilustra o tráfego provenientes de – ou destinados a – os usuários finais.</span><span class="sxs-lookup"><span data-stu-id="afa0b-168">Note the diagram only illustrates traffic originating from--or destined to--end users.</span></span>  
- <span data-ttu-id="afa0b-169">O controlador de mídia é um microservice no Azure que atribui processadores de mídia e cria ofertas de protocolo de descrição de sessão (SDP).</span><span class="sxs-lookup"><span data-stu-id="afa0b-169">The Media Controller is a microservice in Azure that assigns Media Processors and creates Session Description Protocol (SDP) offers.</span></span>

- <span data-ttu-id="afa0b-170">O Proxy SIP é um componente que converte a sinalização de HTTP REST usados em equipes para SIP.</span><span class="sxs-lookup"><span data-stu-id="afa0b-170">The SIP Proxy is a component that translates HTTP REST signaling used in Teams to SIP.</span></span>    

![Mostra mostra dois fluxos de chamada – um com Bypass de mídia habilitado e o segundo com Bypass de mídia é desabilitado)](media/direct-routing-media-bypass-6.png)


<span data-ttu-id="afa0b-172">A tabela a seguir resume a diferença entre os processadores de mídia e retransmissões de transporte.</span><span class="sxs-lookup"><span data-stu-id="afa0b-172">The table below summarizes the difference between Media Processors and Transport Relays.</span></span>

|    | <span data-ttu-id="afa0b-173">Processadores de mídia</span><span class="sxs-lookup"><span data-stu-id="afa0b-173">Media Processors</span></span> | <span data-ttu-id="afa0b-174">Retransmissões de transporte</span><span class="sxs-lookup"><span data-stu-id="afa0b-174">Transport Relays</span></span>|
| :--------------|:---------------|:------------|
<span data-ttu-id="afa0b-175">No caminho de mídia das chamadas não desviada para usuários finais</span><span class="sxs-lookup"><span data-stu-id="afa0b-175">In media path for non-bypassed calls for end users</span></span> | <span data-ttu-id="afa0b-176">Sempre</span><span class="sxs-lookup"><span data-stu-id="afa0b-176">Always</span></span> | <span data-ttu-id="afa0b-177">Nunca</span><span class="sxs-lookup"><span data-stu-id="afa0b-177">Never</span></span> | 
<span data-ttu-id="afa0b-178">No caminho de mídia para ignorados chamadas para usuários finais</span><span class="sxs-lookup"><span data-stu-id="afa0b-178">In media path for bypassed calls for end users</span></span> | <span data-ttu-id="afa0b-179">Nunca</span><span class="sxs-lookup"><span data-stu-id="afa0b-179">Never</span></span> | <span data-ttu-id="afa0b-180">Se o cliente não consegue acessar o SBC no endereço IP público</span><span class="sxs-lookup"><span data-stu-id="afa0b-180">If client cannot reach the SBC on the public IP address</span></span> | 
<span data-ttu-id="afa0b-181">No caminho de mídia para aplicativos de voz</span><span class="sxs-lookup"><span data-stu-id="afa0b-181">In media path for voice applications</span></span> | <span data-ttu-id="afa0b-182">Sempre</span><span class="sxs-lookup"><span data-stu-id="afa0b-182">Always</span></span> | <span data-ttu-id="afa0b-183">Nunca</span><span class="sxs-lookup"><span data-stu-id="afa0b-183">Never</span></span> | 
<span data-ttu-id="afa0b-184">Pode fazer a transcodificação (B2BUA)\*</span><span class="sxs-lookup"><span data-stu-id="afa0b-184">Can do transcoding (B2BUA)\*</span></span> | <span data-ttu-id="afa0b-185">Sim</span><span class="sxs-lookup"><span data-stu-id="afa0b-185">Yes</span></span> | <span data-ttu-id="afa0b-186">Não, retransmite apenas áudio entre os pontos de extremidade</span><span class="sxs-lookup"><span data-stu-id="afa0b-186">No, only relays audio between endpoints</span></span> | 
<span data-ttu-id="afa0b-187">Número de instâncias mundiais e local</span><span class="sxs-lookup"><span data-stu-id="afa0b-187">Number of instances worldwide and location</span></span> | <span data-ttu-id="afa0b-188">total de 8: 2 pol conosco Leste e Oeste; 2 pol Amsterdã e Dublin; 2 de Hong Kong e Cingapura; 2 no Japão (que está sendo adicionado ao Q1CY2019)</span><span class="sxs-lookup"><span data-stu-id="afa0b-188">8 total: 2 in US East and West; 2 in Amsterdam and Dublin; 2 in Hong Kong and Singapore; 2 in Japan (being added in Q1CY2019)</span></span>  | <span data-ttu-id="afa0b-189">Vários</span><span class="sxs-lookup"><span data-stu-id="afa0b-189">Multiple</span></span>

<span data-ttu-id="afa0b-190">O intervalo IP é 52.112.0.0 /14 (endereços IP de 52.112.0.1 a 52.115.255.254).</span><span class="sxs-lookup"><span data-stu-id="afa0b-190">The IP range is 52.112.0.0 /14 (IP addresses from 52.112.0.1 to 52.115.255.254).</span></span> 

<span data-ttu-id="afa0b-191">\*Explicação transcodificação:</span><span class="sxs-lookup"><span data-stu-id="afa0b-191">\* Transcoding explanation:</span></span> 

- <span data-ttu-id="afa0b-192">Processador de mídia é B2BUA, o que significa que ele pode alterar um codecs (por exemplo, SILK do cliente de equipes MP e g. 711 entre MP e SBC).</span><span class="sxs-lookup"><span data-stu-id="afa0b-192">Media Processor is B2BUA, which means it can change a codecs (for example, SILK from Teams client to MP and G.711 between MP and SBC).</span></span>

- <span data-ttu-id="afa0b-193">Transporte retransmissões não são B2BUA, o que significa que o codec nunca é alterado entre o cliente e o SBC – mesmo se o tráfego flui via retransmissões.</span><span class="sxs-lookup"><span data-stu-id="afa0b-193">Transport Relays are not B2BUA, which means the codec is never changed between the client and the SBC--even if traffic flows via relays.</span></span>

### <a name="use-of-teams-transport-relays-in-escalation-scenarios-if-trunk-is-configured-for-media-bypass"></a><span data-ttu-id="afa0b-194">Uso das equipes retransmissões de transporte em cenários de escalonamento se tronco estiver configurado para o media bypass</span><span class="sxs-lookup"><span data-stu-id="afa0b-194">Use of Teams Transport Relays in escalation scenarios if trunk is configured for media bypass</span></span>

<span data-ttu-id="afa0b-195">As equipes retransmissões de transporte são sempre no caminho de mídia nos seguintes cenários:</span><span class="sxs-lookup"><span data-stu-id="afa0b-195">Teams Transport Relays are always in the media path in the following scenarios:</span></span>

- <span data-ttu-id="afa0b-196">Chamada será escalonada de 1:1 para uma chamada do grupo</span><span class="sxs-lookup"><span data-stu-id="afa0b-196">Call is escalated from 1:1 to a group call</span></span>
- <span data-ttu-id="afa0b-197">Chamada será um usuário federado de equipes</span><span class="sxs-lookup"><span data-stu-id="afa0b-197">Call is going to a federated Teams user</span></span>
- <span data-ttu-id="afa0b-198">Chamada é encaminhada ou transferida para um Skype para o usuário de negócios</span><span class="sxs-lookup"><span data-stu-id="afa0b-198">Call is forwarded or transferred to a Skype for Business user</span></span>

<span data-ttu-id="afa0b-199">Certifique-se de que seu SBC tem acesso a retransmissões de transporte, conforme descrito abaixo.</span><span class="sxs-lookup"><span data-stu-id="afa0b-199">Ensure your SBC has access to the Transport Relays as described below.</span></span>    


## <a name="sip-signaling-fqdns-and-firewall-ports"></a><span data-ttu-id="afa0b-200">Sinalização SIP: FQDNs e portas de firewall</span><span class="sxs-lookup"><span data-stu-id="afa0b-200">SIP Signaling: FQDNs and firewall ports</span></span>

<span data-ttu-id="afa0b-201">De sinalização SIP, os requisitos de firewall e FQDN são iguais às propriedades casos não ignorada.</span><span class="sxs-lookup"><span data-stu-id="afa0b-201">For SIP signaling, the FQDN and firewall requirements are the same as for non-bypassed cases.</span></span> 

<span data-ttu-id="afa0b-202">Os pontos de conexão para roteamento direto são os FQDNs de três seguintes:</span><span class="sxs-lookup"><span data-stu-id="afa0b-202">The connection points for Direct Routing are the following three FQDNs:</span></span>

- <span data-ttu-id="afa0b-203">**sip.pstnhub.microsoft.com** – Global FQDN – deve ser tentado primeiro.</span><span class="sxs-lookup"><span data-stu-id="afa0b-203">**sip.pstnhub.microsoft.com** – Global FQDN – must be tried first.</span></span> <span data-ttu-id="afa0b-204">Quando o SBC envia uma solicitação para resolver esse nome, os servidores DNS da Microsoft Azure retornam um endereço IP apontando para o datacenter do Windows Azure primário atribuído para o SBC.</span><span class="sxs-lookup"><span data-stu-id="afa0b-204">When the SBC sends a request to resolve this name, the Microsoft Azure DNS servers return an IP address pointing to the primary Azure datacenter assigned to the SBC.</span></span> <span data-ttu-id="afa0b-205">Sobre as métricas de desempenho dos centros de dados e proximidade geográfica com o SBC baseia-se a atribuição.</span><span class="sxs-lookup"><span data-stu-id="afa0b-205">The assignment is based on performance metrics of the datacenters and geographical proximity to the SBC.</span></span> <span data-ttu-id="afa0b-206">O endereço IP retornado corresponde ao FQDN principal.</span><span class="sxs-lookup"><span data-stu-id="afa0b-206">The IP address returned corresponds to the primary FQDN.</span></span>

- <span data-ttu-id="afa0b-207">**sip2.pstnhub.microsoft.com** – secundário FQDN – geograficamente mapeia à segunda região prioridade.</span><span class="sxs-lookup"><span data-stu-id="afa0b-207">**sip2.pstnhub.microsoft.com** – Secondary FQDN – geographically maps to the second priority region.</span></span>

- <span data-ttu-id="afa0b-208">**sip3.pstnhub.microsoft.com** – terciária FQDN – geograficamente mapeia para a região de prioridade de terceiro.</span><span class="sxs-lookup"><span data-stu-id="afa0b-208">**sip3.pstnhub.microsoft.com** – Tertiary FQDN – geographically maps to the third priority region.</span></span>

<span data-ttu-id="afa0b-209">Você deve colocar esses três FQDNs para:</span><span class="sxs-lookup"><span data-stu-id="afa0b-209">You must place these three FQDNs in order to:</span></span>

- <span data-ttu-id="afa0b-210">Fornecer uma experiência ideal (menos carregada e mais próxima para o datacenter SBC atribuído consultando o FQDN do primeiro).</span><span class="sxs-lookup"><span data-stu-id="afa0b-210">Provide optimal experience (less loaded and closest to the SBC datacenter assigned by querying the first FQDN).</span></span>

- <span data-ttu-id="afa0b-211">Fornece failover quando uma conexão de um SBC é estabelecida com um datacenter que está experimentando um problema temporário.</span><span class="sxs-lookup"><span data-stu-id="afa0b-211">Provide failover when a connection from an SBC is established to a datacenter that is experiencing a temporary issue.</span></span> <span data-ttu-id="afa0b-212">Para obter mais informações, consulte abaixo do mecanismo de Failover.</span><span class="sxs-lookup"><span data-stu-id="afa0b-212">For more information, see Failover mechanism below.</span></span>


<span data-ttu-id="afa0b-213">Os FQDNs **sip.pstnhub.microsoft.com**, **sip2.pstnhub.microsoft.com**e **sip3.pstnhub.microsoft.com** serão resolvidos para um dos seguintes endereços IP:</span><span class="sxs-lookup"><span data-stu-id="afa0b-213">The FQDNs **sip.pstnhub.microsoft.com**, **sip2.pstnhub.microsoft.com**, and **sip3.pstnhub.microsoft.com** will be resolved to one of the following IP addresses:</span></span>
- <span data-ttu-id="afa0b-214">52.114.148.0</span><span class="sxs-lookup"><span data-stu-id="afa0b-214">52.114.148.0</span></span>
- <span data-ttu-id="afa0b-215">52.114.132.46</span><span class="sxs-lookup"><span data-stu-id="afa0b-215">52.114.132.46</span></span>
- <span data-ttu-id="afa0b-216">52.114.75.24</span><span class="sxs-lookup"><span data-stu-id="afa0b-216">52.114.75.24</span></span>
- <span data-ttu-id="afa0b-217">52.114.76.76</span><span class="sxs-lookup"><span data-stu-id="afa0b-217">52.114.76.76</span></span>
- <span data-ttu-id="afa0b-218">52.114.7.24</span><span class="sxs-lookup"><span data-stu-id="afa0b-218">52.114.7.24</span></span>
- <span data-ttu-id="afa0b-219">52.114.14.70</span><span class="sxs-lookup"><span data-stu-id="afa0b-219">52.114.14.70</span></span>

<span data-ttu-id="afa0b-220">Você precisará abrir portas para todos esses endereços IP no seu firewall para permitir o tráfego de entrada e saído de e para os endereços de sinalização.</span><span class="sxs-lookup"><span data-stu-id="afa0b-220">You will need to open ports for all these IP addresses in your firewall to allow incoming and outgoing traffic to and from the addresses for signaling.</span></span> <span data-ttu-id="afa0b-221">Se seu firewall suporta nomes DNS, o FQDN **sip-all.pstnhub.microsoft.com** resolve para todos os endereços IP acima.</span><span class="sxs-lookup"><span data-stu-id="afa0b-221">If your firewall supports DNS names, the FQDN **sip-all.pstnhub.microsoft.com** resolves to all the IP addresses above.</span></span> <span data-ttu-id="afa0b-222">Você deve usar as seguintes portas:</span><span class="sxs-lookup"><span data-stu-id="afa0b-222">You must use the following ports:</span></span>

| <span data-ttu-id="afa0b-223">Tráfego</span><span class="sxs-lookup"><span data-stu-id="afa0b-223">Traffic</span></span> | <span data-ttu-id="afa0b-224">De</span><span class="sxs-lookup"><span data-stu-id="afa0b-224">From</span></span> | <span data-ttu-id="afa0b-225">Até</span><span class="sxs-lookup"><span data-stu-id="afa0b-225">To</span></span> | <span data-ttu-id="afa0b-226">Porta de origem</span><span class="sxs-lookup"><span data-stu-id="afa0b-226">Source port</span></span> | <span data-ttu-id="afa0b-227">Porta de destino</span><span class="sxs-lookup"><span data-stu-id="afa0b-227">Destination port</span></span>|
| :-------- | :-------- |:-----------|:--------|:---------|
<span data-ttu-id="afa0b-228">SIP/TLS</span><span class="sxs-lookup"><span data-stu-id="afa0b-228">SIP/TLS</span></span>| <span data-ttu-id="afa0b-229">Proxy SIP</span><span class="sxs-lookup"><span data-stu-id="afa0b-229">SIP Proxy</span></span> | <span data-ttu-id="afa0b-230">SBC</span><span class="sxs-lookup"><span data-stu-id="afa0b-230">SBC</span></span> | <span data-ttu-id="afa0b-231">1024 - 65535</span><span class="sxs-lookup"><span data-stu-id="afa0b-231">1024 - 65535</span></span> | <span data-ttu-id="afa0b-232">Definidos no SBC</span><span class="sxs-lookup"><span data-stu-id="afa0b-232">Defined on the SBC</span></span> |
| <span data-ttu-id="afa0b-233">SIP/TLS</span><span class="sxs-lookup"><span data-stu-id="afa0b-233">SIP/TLS</span></span> | <span data-ttu-id="afa0b-234">SBC</span><span class="sxs-lookup"><span data-stu-id="afa0b-234">SBC</span></span> | <span data-ttu-id="afa0b-235">Proxy SIP</span><span class="sxs-lookup"><span data-stu-id="afa0b-235">SIP Proxy</span></span> | <span data-ttu-id="afa0b-236">Definidos no SBC</span><span class="sxs-lookup"><span data-stu-id="afa0b-236">Defined on the SBC</span></span> | <span data-ttu-id="afa0b-237">5061</span><span class="sxs-lookup"><span data-stu-id="afa0b-237">5061</span></span> |


## <a name="media-traffic-ip-and-port-ranges"></a><span data-ttu-id="afa0b-238">Tráfego de mídia: intervalos IP e porta</span><span class="sxs-lookup"><span data-stu-id="afa0b-238">Media traffic: IP and Port ranges</span></span>

<span data-ttu-id="afa0b-239">Tráfego de mídia flui entre o cliente SBC e as equipes se conectividade direta estiver disponível ou através de equipes transporte retransmissões se o cliente não consegue acessar o SBC usando o endereço IP público.</span><span class="sxs-lookup"><span data-stu-id="afa0b-239">Media traffic flows between the SBC and Teams client if direct connectivity is available or via Teams Transport Relays if the client cannot reach the SBC using the public IP address.</span></span>

### <a name="requirements-for-direct-media-traffic-between-the-teams-client-and-the-sbc"></a><span data-ttu-id="afa0b-240">Requisitos para o tráfego de mídia direto (entre o cliente de equipes e o SBC)</span><span class="sxs-lookup"><span data-stu-id="afa0b-240">Requirements for direct media traffic (between the Teams client and the SBC)</span></span> 

<span data-ttu-id="afa0b-241">O cliente deve ter acesso às portas especificadas (veja tabela) no endereço IP público do SBC.</span><span class="sxs-lookup"><span data-stu-id="afa0b-241">The client must have access to the specified ports (see table) on the public IP address of the SBC.</span></span> 

<span data-ttu-id="afa0b-242">Observação: Se o cliente estiver em uma rede interna, a mídia flui para o endereço IP público do SBC.</span><span class="sxs-lookup"><span data-stu-id="afa0b-242">Note: If the client is in an internal network, the media flows to the public IP address of the SBC.</span></span> <span data-ttu-id="afa0b-243">Você pode configurar hairpinning no seu dispositivo NAT para que tráfego nunca deixa o equipamento de rede empresarial.</span><span class="sxs-lookup"><span data-stu-id="afa0b-243">You can configure hairpinning on your NAT device so traffic never leaves the enterprise network equipment.</span></span>

| <span data-ttu-id="afa0b-244">Tráfego</span><span class="sxs-lookup"><span data-stu-id="afa0b-244">Traffic</span></span> | <span data-ttu-id="afa0b-245">De</span><span class="sxs-lookup"><span data-stu-id="afa0b-245">From</span></span> | <span data-ttu-id="afa0b-246">Até</span><span class="sxs-lookup"><span data-stu-id="afa0b-246">To</span></span> | <span data-ttu-id="afa0b-247">Porta de origem</span><span class="sxs-lookup"><span data-stu-id="afa0b-247">Source port</span></span> | <span data-ttu-id="afa0b-248">Porta de destino</span><span class="sxs-lookup"><span data-stu-id="afa0b-248">Destination port</span></span>|
| :-------- | :-------- |:-----------|:--------|:---------|
<span data-ttu-id="afa0b-249">UDP/SRTP</span><span class="sxs-lookup"><span data-stu-id="afa0b-249">UDP/SRTP</span></span> | <span data-ttu-id="afa0b-250">Cliente</span><span class="sxs-lookup"><span data-stu-id="afa0b-250">Client</span></span> | <span data-ttu-id="afa0b-251">SBC</span><span class="sxs-lookup"><span data-stu-id="afa0b-251">SBC</span></span> | <span data-ttu-id="afa0b-252">50 000 – 50 019</span><span class="sxs-lookup"><span data-stu-id="afa0b-252">50 000 – 50 019</span></span>  | <span data-ttu-id="afa0b-253">Definidos no SBC</span><span class="sxs-lookup"><span data-stu-id="afa0b-253">Defined on the SBC</span></span> |
| <span data-ttu-id="afa0b-254">UDP/SRTP</span><span class="sxs-lookup"><span data-stu-id="afa0b-254">UDP/SRTP</span></span> | <span data-ttu-id="afa0b-255">SBC</span><span class="sxs-lookup"><span data-stu-id="afa0b-255">SBC</span></span> | <span data-ttu-id="afa0b-256">Cliente</span><span class="sxs-lookup"><span data-stu-id="afa0b-256">Client</span></span> | <span data-ttu-id="afa0b-257">Definidos no SBC</span><span class="sxs-lookup"><span data-stu-id="afa0b-257">Defined on the SBC</span></span> | <span data-ttu-id="afa0b-258">50 000 – 50 019</span><span class="sxs-lookup"><span data-stu-id="afa0b-258">50 000 – 50 019</span></span>  |


<span data-ttu-id="afa0b-259">Observação: Se você tiver um dispositivo de rede que converte a portas de origem do cliente, verifique se que serão abertas portas convertidas entre o equipamento de rede e o SBC.</span><span class="sxs-lookup"><span data-stu-id="afa0b-259">Note: If you have a network device that translates the client's source ports, please make sure that translated ports are opened between the network equipment and the SBC.</span></span> 

### <a name="requirements-for-using-transport-relays"></a><span data-ttu-id="afa0b-260">Requisitos de uso retransmissões de transporte</span><span class="sxs-lookup"><span data-stu-id="afa0b-260">Requirements for using Transport Relays</span></span>

<span data-ttu-id="afa0b-261">Transporte retransmissões estão no mesmo intervalo como processadores de mídia (para casos não ignorar): 52.112.0.0 /14 (endereços IP de 52.112.0.1 a 52.115.255.254).</span><span class="sxs-lookup"><span data-stu-id="afa0b-261">Transport Relays are in the same range as Media Processors (for non-bypass cases):  52.112.0.0 /14 (IP addresses from 52.112.0.1 to 52.115.255.254).</span></span>

<span data-ttu-id="afa0b-262">O intervalo de portas de retransmissões de transporte as equipes é mostrado na tabela a seguir:</span><span class="sxs-lookup"><span data-stu-id="afa0b-262">The port range of the Teams Transport Relays is shown in the following table:</span></span>


| <span data-ttu-id="afa0b-263">Tráfego</span><span class="sxs-lookup"><span data-stu-id="afa0b-263">Traffic</span></span> | <span data-ttu-id="afa0b-264">De</span><span class="sxs-lookup"><span data-stu-id="afa0b-264">From</span></span> | <span data-ttu-id="afa0b-265">Até</span><span class="sxs-lookup"><span data-stu-id="afa0b-265">To</span></span> | <span data-ttu-id="afa0b-266">Porta de origem</span><span class="sxs-lookup"><span data-stu-id="afa0b-266">Source port</span></span> | <span data-ttu-id="afa0b-267">Porta de destino</span><span class="sxs-lookup"><span data-stu-id="afa0b-267">Destination port</span></span>|
| :-------- | :-------- |:-----------|:--------|:---------|
<span data-ttu-id="afa0b-268">UDP/SRTP</span><span class="sxs-lookup"><span data-stu-id="afa0b-268">UDP/SRTP</span></span> | <span data-ttu-id="afa0b-269">Retransmissão de transporte</span><span class="sxs-lookup"><span data-stu-id="afa0b-269">Transport Relay</span></span> | <span data-ttu-id="afa0b-270">SBC</span><span class="sxs-lookup"><span data-stu-id="afa0b-270">SBC</span></span> | <span data-ttu-id="afa0b-271">50 000-59 999</span><span class="sxs-lookup"><span data-stu-id="afa0b-271">50 000 -59 999</span></span>    | <span data-ttu-id="afa0b-272">Definidos no SBC</span><span class="sxs-lookup"><span data-stu-id="afa0b-272">Defined on the SBC</span></span> |
| <span data-ttu-id="afa0b-273">UDP/SRTP</span><span class="sxs-lookup"><span data-stu-id="afa0b-273">UDP/SRTP</span></span> | <span data-ttu-id="afa0b-274">SBC</span><span class="sxs-lookup"><span data-stu-id="afa0b-274">SBC</span></span> | <span data-ttu-id="afa0b-275">Retransmissão de transporte</span><span class="sxs-lookup"><span data-stu-id="afa0b-275">Transport Relay</span></span> | <span data-ttu-id="afa0b-276">Definidos no SBC</span><span class="sxs-lookup"><span data-stu-id="afa0b-276">Defined on the SBC</span></span> | <span data-ttu-id="afa0b-277">50 000 – 59 999, 3478, 3479</span><span class="sxs-lookup"><span data-stu-id="afa0b-277">50 000 – 59 999, 3478, 3479</span></span>     |


<span data-ttu-id="afa0b-278">Observação: A Microsoft recomenda pelo menos duas portas por chamada simultânea no SBC.</span><span class="sxs-lookup"><span data-stu-id="afa0b-278">Note: Microsoft recommends at least two ports per concurrent call on the SBC.</span></span> <span data-ttu-id="afa0b-279">Como a Microsoft tem duas versões do retransmissões de transporte, é necessário o seguinte:</span><span class="sxs-lookup"><span data-stu-id="afa0b-279">Because Microsoft has two versions of Transport Relays, the following are required:</span></span>

- <span data-ttu-id="afa0b-280">V4, que só pode trabalhar com o intervalo de portas 50 000 para 59 999</span><span class="sxs-lookup"><span data-stu-id="afa0b-280">v4, which can only work with port range 50 000 to 59 999</span></span>

- <span data-ttu-id="afa0b-281">v6, que funciona com portas 3478, 3479</span><span class="sxs-lookup"><span data-stu-id="afa0b-281">v6, which works with ports 3478, 3479</span></span>

<span data-ttu-id="afa0b-282">Neste momento, o desvio de mídia somente suporta a versão v4 de retransmissões de transporte.</span><span class="sxs-lookup"><span data-stu-id="afa0b-282">At this time, media bypass only supports v4 version of Transport Relays.</span></span> <span data-ttu-id="afa0b-283">Apresentaremos suporte de v6 no futuro.</span><span class="sxs-lookup"><span data-stu-id="afa0b-283">We will introduce support of v6 in the future.</span></span> 

<span data-ttu-id="afa0b-284">Você precisará abrir as portas 3478 e 3479 para a transição.</span><span class="sxs-lookup"><span data-stu-id="afa0b-284">You need to open ports 3478 and 3479 for transitioning.</span></span> <span data-ttu-id="afa0b-285">Quando o Microsoft introduz o suporte para v6 retransmissões de transporte com Bypass de mídia, você não precisará reconfigurar o equipamento de rede ou SBCs.</span><span class="sxs-lookup"><span data-stu-id="afa0b-285">When Microsoft introduces support for v6 Transport Relays with Media Bypass, you will not need to reconfigure your network equipment or SBCs.</span></span> 

### <a name="requirements-for-using-media-processors"></a><span data-ttu-id="afa0b-286">Requisitos para o uso de processadores de mídia</span><span class="sxs-lookup"><span data-stu-id="afa0b-286">Requirements for using media processors</span></span>

<span data-ttu-id="afa0b-287">Processadores de mídia são sempre no caminho de mídia para aplicativos de voz.</span><span class="sxs-lookup"><span data-stu-id="afa0b-287">Media Processors are always in the media path for voice applications.</span></span> <span data-ttu-id="afa0b-288">Os requisitos são iguais às propriedades de configuração não ignorar.</span><span class="sxs-lookup"><span data-stu-id="afa0b-288">The requirements are the same as for non-bypass configuration.</span></span>


<span data-ttu-id="afa0b-289">O intervalo IP para o tráfego de mídia é 52.112.0.0 /14 (endereços IP de 52.112.0.1 a 52.115.255.254).</span><span class="sxs-lookup"><span data-stu-id="afa0b-289">The IP range for media traffic is 52.112.0.0 /14 (IP addresses from 52.112.0.1 to 52.115.255.254).</span></span>

<span data-ttu-id="afa0b-290">O intervalo de portas dos processadores de mídia é mostrado na tabela a seguir:</span><span class="sxs-lookup"><span data-stu-id="afa0b-290">The port range of the Media Processors is shown in the following table:</span></span>

| <span data-ttu-id="afa0b-291">Tráfego</span><span class="sxs-lookup"><span data-stu-id="afa0b-291">Traffic</span></span> | <span data-ttu-id="afa0b-292">De</span><span class="sxs-lookup"><span data-stu-id="afa0b-292">From</span></span> | <span data-ttu-id="afa0b-293">Até</span><span class="sxs-lookup"><span data-stu-id="afa0b-293">To</span></span> | <span data-ttu-id="afa0b-294">Porta de origem</span><span class="sxs-lookup"><span data-stu-id="afa0b-294">Source port</span></span> | <span data-ttu-id="afa0b-295">Porta de destino</span><span class="sxs-lookup"><span data-stu-id="afa0b-295">Destination port</span></span>|
| :-------- | :-------- |:-----------|:--------|:---------|
<span data-ttu-id="afa0b-296">UDP/SRTP</span><span class="sxs-lookup"><span data-stu-id="afa0b-296">UDP/SRTP</span></span> | <span data-ttu-id="afa0b-297">Processador de mídia</span><span class="sxs-lookup"><span data-stu-id="afa0b-297">Media Processor</span></span> | <span data-ttu-id="afa0b-298">SBC</span><span class="sxs-lookup"><span data-stu-id="afa0b-298">SBC</span></span> | <span data-ttu-id="afa0b-299">49 152 – 53 247</span><span class="sxs-lookup"><span data-stu-id="afa0b-299">49 152 – 53 247</span></span>    | <span data-ttu-id="afa0b-300">Definidos no SBC</span><span class="sxs-lookup"><span data-stu-id="afa0b-300">Defined on the SBC</span></span> |
| <span data-ttu-id="afa0b-301">UDP/SRTP</span><span class="sxs-lookup"><span data-stu-id="afa0b-301">UDP/SRTP</span></span> | <span data-ttu-id="afa0b-302">SBC</span><span class="sxs-lookup"><span data-stu-id="afa0b-302">SBC</span></span> | <span data-ttu-id="afa0b-303">Processador de mídia</span><span class="sxs-lookup"><span data-stu-id="afa0b-303">Media Processor</span></span> | <span data-ttu-id="afa0b-304">Definidos no SBC</span><span class="sxs-lookup"><span data-stu-id="afa0b-304">Defined on the SBC</span></span> | <span data-ttu-id="afa0b-305">49 152 – 53 247</span><span class="sxs-lookup"><span data-stu-id="afa0b-305">49 152 – 53 247</span></span>     |

## <a name="considerations-if-you-have-skype-for-business-phones-in-your-network"></a><span data-ttu-id="afa0b-306">Considerações sobre se você tiver Skype para telefones de negócios em sua rede</span><span class="sxs-lookup"><span data-stu-id="afa0b-306">Considerations if you have Skype for Business phones in your network</span></span>  

<span data-ttu-id="afa0b-307">Se você tiver quaisquer Skype para pontos finais empresariais em sua rede que está usando o roteamento direto – por exemplo, um usuário pode ter um telefone 3PIP com base no Skype para o cliente de negócios – as equipes o bypass de mídia no tronco que serve a esses usuários deve ser desativado.</span><span class="sxs-lookup"><span data-stu-id="afa0b-307">If you have any Skype for Business end points in your network that are using Direct Routing--for example, a Teams user can have a 3PIP phone that is based on Skype for Business client--the media bypass on the trunk that serves these users must be turned off.</span></span>

<span data-ttu-id="afa0b-308">Você pode criar um tronco separado para esses usuários e atribuí-la uma política de roteamento de voz Online.</span><span class="sxs-lookup"><span data-stu-id="afa0b-308">You can create a separate trunk for these users and assign it an Online Voice Routing policy.</span></span>

<span data-ttu-id="afa0b-309">Etapas de configuração de alto nível:</span><span class="sxs-lookup"><span data-stu-id="afa0b-309">High-level configuration steps:</span></span>

- <span data-ttu-id="afa0b-310">Dividir os usuários por tipo – dependendo se o usuário possui um telefone 3PIP ou não.</span><span class="sxs-lookup"><span data-stu-id="afa0b-310">Split users by type – depending on whether the user has a 3PIP phone or not.</span></span>

- <span data-ttu-id="afa0b-311">Criar dois troncos separados com diferentes FQDNs: um habilitado bypass de mídia; outro não.</span><span class="sxs-lookup"><span data-stu-id="afa0b-311">Create two separate trunks with different FQDNs: one enabled for media bypass; the other not.</span></span> 

  <span data-ttu-id="afa0b-312">Ambos os troncos apontam para o mesmo SBC.</span><span class="sxs-lookup"><span data-stu-id="afa0b-312">Both trunks point to the same SBC.</span></span> <span data-ttu-id="afa0b-313">As portas para a sinalização SIP TLS devem ser diferentes.</span><span class="sxs-lookup"><span data-stu-id="afa0b-313">The ports for TLS SIP signaling must be different.</span></span> <span data-ttu-id="afa0b-314">As portas de mídia devem ser o mesmo.</span><span class="sxs-lookup"><span data-stu-id="afa0b-314">The ports for media must be the same.</span></span>

- <span data-ttu-id="afa0b-315">Atribua o tronco correto, dependendo do tipo do usuário na política de roteamento de voz Online.</span><span class="sxs-lookup"><span data-stu-id="afa0b-315">Assign the correct trunk depending on the type of the user in the Online Voice Routing policy.</span></span>

<span data-ttu-id="afa0b-316">O exemplo a seguir ilustra essa lógica.</span><span class="sxs-lookup"><span data-stu-id="afa0b-316">The example below illustrates this logic.</span></span>

| <span data-ttu-id="afa0b-317">Conjunto de usuários</span><span class="sxs-lookup"><span data-stu-id="afa0b-317">Set of users</span></span> | <span data-ttu-id="afa0b-318">Número de usuários</span><span class="sxs-lookup"><span data-stu-id="afa0b-318">Number of users</span></span> | <span data-ttu-id="afa0b-319">Tronco FQDN atribuída no OVRP</span><span class="sxs-lookup"><span data-stu-id="afa0b-319">Trunk FQDN assigned in OVRP</span></span> | <span data-ttu-id="afa0b-320">Bypass de mídia habilitado</span><span class="sxs-lookup"><span data-stu-id="afa0b-320">Media bypass enabled</span></span> |
| :------------ |:----------------- |:--------------|:--------------|
<span data-ttu-id="afa0b-321">Usuários com clientes de equipes e telefones 3PIP</span><span class="sxs-lookup"><span data-stu-id="afa0b-321">Users with Teams clients and 3PIP phones</span></span> | <span data-ttu-id="afa0b-322">20</span><span class="sxs-lookup"><span data-stu-id="afa0b-322">20</span></span> | <span data-ttu-id="afa0b-323">sbc1.contoso.com:5061</span><span class="sxs-lookup"><span data-stu-id="afa0b-323">sbc1.contoso.com:5061</span></span> | <span data-ttu-id="afa0b-324">False</span><span class="sxs-lookup"><span data-stu-id="afa0b-324">false</span></span> | 
<span data-ttu-id="afa0b-325">Usuários com apenas equipes pontos de extremidade (incluindo novos telefones certificados para equipes)</span><span class="sxs-lookup"><span data-stu-id="afa0b-325">Users with only Teams end points (including new phones certified for Teams)</span></span> | <span data-ttu-id="afa0b-326">980</span><span class="sxs-lookup"><span data-stu-id="afa0b-326">980</span></span> | <span data-ttu-id="afa0b-327">sbc2.contoso.com:5060</span><span class="sxs-lookup"><span data-stu-id="afa0b-327">sbc2.contoso.com:5060</span></span> | <span data-ttu-id="afa0b-328">True</span><span class="sxs-lookup"><span data-stu-id="afa0b-328">true</span></span>

<span data-ttu-id="afa0b-329">Ambos os troncos podem apontar para o mesmo SBC com o mesmo endereço IP público.</span><span class="sxs-lookup"><span data-stu-id="afa0b-329">Both trunks can point to the same SBC with the same public IP address.</span></span> <span data-ttu-id="afa0b-330">Os TLS sinalização portas no SBC deve ser diferentes, conforme mostrado no diagrama a seguir.</span><span class="sxs-lookup"><span data-stu-id="afa0b-330">The TLS signaling ports on the SBC must be different, as shown in the following diagram.</span></span> <span data-ttu-id="afa0b-331">Observe que você precisará certificar-se de que seu certificado suporta ambos os troncos.</span><span class="sxs-lookup"><span data-stu-id="afa0b-331">Note you will need to make sure that your certificate supports both trunks.</span></span> <span data-ttu-id="afa0b-332">Em SAN, você precisa ter dois nomes (**sbc1.contoso.com** e **sbc2.contoso.com**) ou ter um certificado curinga.</span><span class="sxs-lookup"><span data-stu-id="afa0b-332">In SAN, you need to have two names (**sbc1.contoso.com** and **sbc2.contoso.com**) or have a wildcard certificate.</span></span>


![Mostra que os dois troncos podem apontar para o mesmo SBC com o mesmo IP público)](media/direct-routing-media-bypass-7.png)

<span data-ttu-id="afa0b-334">Para obter informações sobre como configurar dois troncos no mesmo SBC, consulte a documentação fornecida pelo seu fornecedor SBC:</span><span class="sxs-lookup"><span data-stu-id="afa0b-334">For information about how to configure two trunks on the same SBC, see the documentation provided by your SBC vendor:</span></span>

- <span data-ttu-id="afa0b-335">AudioCodes</span><span class="sxs-lookup"><span data-stu-id="afa0b-335">AudioCodes</span></span>
- <span data-ttu-id="afa0b-336">Faixa de opções</span><span class="sxs-lookup"><span data-stu-id="afa0b-336">Ribbon</span></span>
- <span data-ttu-id="afa0b-337">TE-Systems (Anynode)</span><span class="sxs-lookup"><span data-stu-id="afa0b-337">TE-Systems (Anynode)</span></span>   

## <a name="client-endpoints-supported-with-media-bypass"></a><span data-ttu-id="afa0b-338">Pontos de extremidade do cliente compatíveis com o media bypass</span><span class="sxs-lookup"><span data-stu-id="afa0b-338">Client endpoints supported with media bypass</span></span>

<span data-ttu-id="afa0b-339">Bypass de mídia é compatível com todos os pontos de extremidade equipes, exceto clientes Web equipes até notificação futura.</span><span class="sxs-lookup"><span data-stu-id="afa0b-339">Media bypass is supported with all Teams endpoints, except Teams Web clients until further notice.</span></span> 

<span data-ttu-id="afa0b-340">Se os usuários preferem aplicativos da Web de equipes em Microsoft Edge, Google Chrome ou Mozilla Firefox, o bypass de mídia para tais usuários deve ser desativado.</span><span class="sxs-lookup"><span data-stu-id="afa0b-340">If your users prefer Teams Web app in Microsoft Edge, Google Chrome or Mozilla Firefox, the media bypass for such users must be turned off.</span></span> <span data-ttu-id="afa0b-341">Apresentaremos chamadas usando um tronco habilitado de bypass de mídia no futuro.</span><span class="sxs-lookup"><span data-stu-id="afa0b-341">We will introduce calling using a media bypass enabled trunk in the future.</span></span>   
 
## <a name="see-also"></a><span data-ttu-id="afa0b-342">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="afa0b-342">See also</span></span>

[<span data-ttu-id="afa0b-343">Configurar o bypass de mídia com Roteamento Direto</span><span class="sxs-lookup"><span data-stu-id="afa0b-343">Configure media bypass with Direct Routing</span></span>](direct-routing-configure-media-bypass.md)



