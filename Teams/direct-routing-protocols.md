---
title: Roteamento Direto do Sistema de Telefonia
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 12/16/2019
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- Teams_ITAdmin_Help
- M365-voice
ms.reviewer: nmurav
search.appverid: MET150
f1.keywords:
- NOCSH
description: Protocolos de roteamento direto
appliesto:
- Microsoft Teams
ms.openlocfilehash: 7462822626b698f95b80a716a55f94dfe92148ff
ms.sourcegitcommit: ed3d7ebb193229cab9e0e5be3dc1c28c3f622c1b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41835021"
---
# <a name="direct-routing---definitions-and-rfc-standards"></a><span data-ttu-id="33a14-103">Definições de roteamento direto e padrões RFC</span><span class="sxs-lookup"><span data-stu-id="33a14-103">Direct Routing - Definitions and RFC standards</span></span>

<span data-ttu-id="33a14-104">Este artigo descreve como o roteamento direto do sistema de telefone da Microsoft implementa protocolos padrão RFC.</span><span class="sxs-lookup"><span data-stu-id="33a14-104">This article describes how Microsoft Phone System Direct Routing implements RFC standard protocols.</span></span> <span data-ttu-id="33a14-105">Este artigo destina-se a administradores de voz responsáveis por configurar a conexão entre o controlador de borda de sessão local (SBC) e o serviço de proxy SIP (protocolo de inicialização de sessão).</span><span class="sxs-lookup"><span data-stu-id="33a14-105">This article is intended for voice administrators who are responsible for configuring the connection between the on-premises Session Border Controller (SBC) and the Session Initiation Protocol (SIP) proxy service.</span></span>

<span data-ttu-id="33a14-106">As interfaces SBC do cliente com os seguintes componentes no backend do Microsoft Teams:</span><span class="sxs-lookup"><span data-stu-id="33a14-106">The customer SBC interfaces with the following components in the Microsoft Teams backend:</span></span> 

- <span data-ttu-id="33a14-107">**O proxy SIP** para sinalização.</span><span class="sxs-lookup"><span data-stu-id="33a14-107">**The SIP proxy** for signaling.</span></span> <span data-ttu-id="33a14-108">Esse é o componente de roteamento direto da Internet que manipula conexões SIP (TLS) entre o SBCs e o roteamento direto.</span><span class="sxs-lookup"><span data-stu-id="33a14-108">This is the Internet-facing component of Direct Routing that handles SIP (TLS) connections between the SBCs and Direct Routing.</span></span>

- <span data-ttu-id="33a14-109">**Os processadores de mídia** para mídia.</span><span class="sxs-lookup"><span data-stu-id="33a14-109">**The media processors** for media.</span></span> <span data-ttu-id="33a14-110">Esse é o componente de roteamento direto para a Internet que manipula o tráfego de mídia.</span><span class="sxs-lookup"><span data-stu-id="33a14-110">This is the Internet-facing component of Direct Routing that handles media traffic.</span></span> <span data-ttu-id="33a14-111">Esse componente usa protocolos SRTP e SRTCP.</span><span class="sxs-lookup"><span data-stu-id="33a14-111">This component uses SRTP and SRTCP protocols.</span></span>


<span data-ttu-id="33a14-112">Para obter mais informações sobre roteamento direto, consulte [Roteamento direto do sistema telefônico](direct-routing-landing-page.md).</span><span class="sxs-lookup"><span data-stu-id="33a14-112">For more information about Direct Routing, see [Phone System Direct Routing](direct-routing-landing-page.md).</span></span>

<span data-ttu-id="33a14-113">Para obter mais informações sobre como o roteamento direto implementa o protocolo SIP, consulte [protocolo Routing-SIP direto](direct-routing-protocols-sip.md).</span><span class="sxs-lookup"><span data-stu-id="33a14-113">For more information about how Direct Routing implements the SIP protocol, see [Direct Routing - SIP protocol](direct-routing-protocols-sip.md).</span></span>

## <a name="rfc-standards"></a><span data-ttu-id="33a14-114">Padrões RFC</span><span class="sxs-lookup"><span data-stu-id="33a14-114">RFC standards</span></span>

<span data-ttu-id="33a14-115">O roteamento direto está em conformidade com os padrões RFC.</span><span class="sxs-lookup"><span data-stu-id="33a14-115">Direct Routing complies with RFC standards.</span></span>  <span data-ttu-id="33a14-116">O SBC conectado ao roteamento direto também deve estar em conformidade com as seguintes RFCs (ou seus sucessores).</span><span class="sxs-lookup"><span data-stu-id="33a14-116">The SBC connected to Direct Routing must also comply with the following RFCs (or their successors).</span></span> 

### <a name="standards-applicable-to-devices-that-support-non-media-bypass-mode"></a><span data-ttu-id="33a14-117">Padrões aplicáveis a dispositivos que dão suporte ao modo de bypass sem mídia</span><span class="sxs-lookup"><span data-stu-id="33a14-117">Standards applicable to devices that support non-media bypass mode</span></span> 

<span data-ttu-id="33a14-118">Os seguintes padrões são aplicáveis aos dispositivos que dão suporte apenas ao modo de bypass de não mídia:</span><span class="sxs-lookup"><span data-stu-id="33a14-118">The following standards are applicable to devices that support only non-media bypass mode:</span></span>

- <span data-ttu-id="33a14-119">[RFC 3261 SIP](https://tools.ietf.org/html/rfc3261): protocolo de início de sessão</span><span class="sxs-lookup"><span data-stu-id="33a14-119">[RFC 3261 SIP](https://tools.ietf.org/html/rfc3261): Session Initiation Protocol</span></span>
- <span data-ttu-id="33a14-120">[RFC 3325](https://www.ietf.org/rfc/rfc3325).</span><span class="sxs-lookup"><span data-stu-id="33a14-120">[RFC 3325](https://www.ietf.org/rfc/rfc3325).</span></span> <span data-ttu-id="33a14-121">Extensão particular para o protocolo de início de sessão para identidade declarada em redes confiáveis – seções sobre manipulação de cabeçalho de identidade com P-declarada.</span><span class="sxs-lookup"><span data-stu-id="33a14-121">Private Extension to the Session Initiation Protocol for asserted identity within Trusted Networks--Sections about handling P-Asserted-Identity header.</span></span> <span data-ttu-id="33a14-122">O roteamento direto envia identidade P-declarada com cabeçalhos de ID de privacidade.</span><span class="sxs-lookup"><span data-stu-id="33a14-122">Direct Routing sends P-Asserted-Identity with Privacy ID headers.</span></span> 
- <span data-ttu-id="33a14-123">[RFC 4244](https://www.ietf.org/rfc/rfc4244.txt) Uma extensão do protocolo de iniciação de sessão (SIP) para informações necessárias do histórico.</span><span class="sxs-lookup"><span data-stu-id="33a14-123">[RFC 4244](https://www.ietf.org/rfc/rfc4244.txt) An extension to Session Initiation Protocol (SIP) for required History Information.</span></span> <span data-ttu-id="33a14-124">Consulte também: Descrição do protocolo SIP de roteamento para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="33a14-124">See also: Routing SIP Protocol description for more information.</span></span>
- <span data-ttu-id="33a14-125">[RFC 3892](https://www.ietf.org/rfc/rfc3892.txt) O protocolo de início de sessão referido pelo mecanismo</span><span class="sxs-lookup"><span data-stu-id="33a14-125">[RFC 3892](https://www.ietf.org/rfc/rfc3892.txt) The Session Initiation Protocol Referred-By mechanism</span></span>
- <span data-ttu-id="33a14-126">[RFC 3891](https://www.ietf.org/rfc/rfc3891.txt) O cabeçalho "substitui" do protocolo de iniciação de sessão (SIP)</span><span class="sxs-lookup"><span data-stu-id="33a14-126">[RFC 3891](https://www.ietf.org/rfc/rfc3891.txt) The Session Initiation Protocol (SIP) "Replaces" Header</span></span> 
- <span data-ttu-id="33a14-127">[RFC 6337](https://tools.ietf.org/html/rfc6337) Uso do protocolo SIP do modelo de oferta/resposta.</span><span class="sxs-lookup"><span data-stu-id="33a14-127">[RFC 6337](https://tools.ietf.org/html/rfc6337) Session Initiation Protocol (SIP) Usage of the Offer/Answer Model.</span></span>
  <span data-ttu-id="33a14-128">Consulte a seção "desvios da RFC".</span><span class="sxs-lookup"><span data-stu-id="33a14-128">See the “Deviations from RFC” section.</span></span>
- <span data-ttu-id="33a14-129">[Rfc 3711](https://tools.ietf.org/html/rfc3711) e [RFC 4771](https://tools.ietf.org/html/rfc4771).</span><span class="sxs-lookup"><span data-stu-id="33a14-129">[RFC 3711](https://tools.ietf.org/html/rfc3711) and [RFC 4771](https://tools.ietf.org/html/rfc4771).</span></span> <span data-ttu-id="33a14-130">Proteger o tráfego RTP usando o SRTP.</span><span class="sxs-lookup"><span data-stu-id="33a14-130">Protect RTP traffic using SRTP.</span></span> <span data-ttu-id="33a14-131">O SBC deve ser capaz de estabelecer chaves usando SDES.</span><span class="sxs-lookup"><span data-stu-id="33a14-131">The SBC must be able to establish keys using SDES.</span></span> 
- <span data-ttu-id="33a14-132">[RFC 8035](https://www.ietf.org/rfc/rfc8035.txt) O protocolo de descrição de sessão (SDP) oferece/soluciona esclarecimentos para multiplexação RTP/RTCP</span><span class="sxs-lookup"><span data-stu-id="33a14-132">[RFC 8035](https://www.ietf.org/rfc/rfc8035.txt) Session Description Protocol (SDP) Offer/Answer Clarifications for RTP/RTCP Multiplexing</span></span>

### <a name="standards-applicable-to-devices-that-support-media-bypass-mode"></a><span data-ttu-id="33a14-133">Padrões aplicáveis a dispositivos que dão suporte ao modo de bypass de mídia</span><span class="sxs-lookup"><span data-stu-id="33a14-133">Standards applicable to devices that support media bypass mode</span></span>

<span data-ttu-id="33a14-134">Além dos padrões listados como aplicáveis ao modo não bypass, os seguintes padrões são usados para o modo de bypass de mídia:</span><span class="sxs-lookup"><span data-stu-id="33a14-134">In addition to the standards listed as applicable to non-bypass mode, the following standards are used for media bypass mode:</span></span>

- <span data-ttu-id="33a14-135">O [estabelecimento da RFC 5245 Interactive Connectivity (ICE) para bypass de mídia](https://tools.ietf.org/html/rfc5245).</span><span class="sxs-lookup"><span data-stu-id="33a14-135">[RFC 5245 Interactive Connectivity Establishment (ICE) for media bypass](https://tools.ietf.org/html/rfc5245).</span></span>  <span data-ttu-id="33a14-136">O SBC deve oferecer suporte para o seguinte:</span><span class="sxs-lookup"><span data-stu-id="33a14-136">The SBC must support the following:</span></span>
  - <span data-ttu-id="33a14-137">ICE Lite – os clientes do teams são clientes ICE completos</span><span class="sxs-lookup"><span data-stu-id="33a14-137">ICE Lite - the Teams clients are full ICE clients</span></span>
  - <span data-ttu-id="33a14-138">[Reinícios do Ice](https://tools.ietf.org/html/rfc5245#section-9.1.1.1).</span><span class="sxs-lookup"><span data-stu-id="33a14-138">[ICE Restarts](https://tools.ietf.org/html/rfc5245#section-9.1.1.1).</span></span> <span data-ttu-id="33a14-139">Veja mais em reinícios do ICE e exemplos de uso na reinicialização do ICE: chamadas para ignorar mídia transferidas para um ponto de extremidade que não é compatível com o bypass de mídia</span><span class="sxs-lookup"><span data-stu-id="33a14-139">See more on ICE restarts use case and examples in ICE Restart:  Media bypass call transferred to an endpoint which does not support media bypass</span></span>   
- <span data-ttu-id="33a14-140">[Controle de chamada SIP rfc 5589 Session Initiation Protocol (SIP) – transferir](https://tools.ietf.org/html/rfc5589).</span><span class="sxs-lookup"><span data-stu-id="33a14-140">[RFC RFC 5589 Session Initiation Protocol (SIP) Call Control – Transfer](https://tools.ietf.org/html/rfc5589).</span></span> 
- <span data-ttu-id="33a14-141">[A mídia de início rápido da RFC 3960 e a geração de Tom de toque no protocolo de iniciação de sessão (SIP)](https://tools.ietf.org/html/rfc3960), consulte seções 3,1, bifurcação e 3,2, geração de Tom de toque</span><span class="sxs-lookup"><span data-stu-id="33a14-141">[RFC 3960 Early Media and Ringing Tone Generation in the Session Initiation Protocol (SIP)](https://tools.ietf.org/html/rfc3960), see sections 3.1, Forking, and 3.2, Ringing Tone Generation</span></span> 
- [<span data-ttu-id="33a14-142">Utilitários de passagem de sessão RFC 5389 para NAT (STUN)</span><span class="sxs-lookup"><span data-stu-id="33a14-142">RFC 5389 Session Traversal Utilities for NAT (STUN)</span></span>](https://tools.ietf.org/html/rfc5389)
- [<span data-ttu-id="33a14-143">Passagem RFC 5766 usando retransmissões em torno de NAT (ativar): extensões de retransmissão para utilitários de passagem de sessão para NAT (STUN)</span><span class="sxs-lookup"><span data-stu-id="33a14-143">RFC 5766 Traversal Using Relays around NAT (TURN): Relay Extensions to Session Traversal Utilities for NAT (STUN)</span></span>](https://tools.ietf.org/html/rfc5766)

### <a name="standards-applicable-to-support-conveying-location-information-to-e911-providers"></a><span data-ttu-id="33a14-144">Padrões aplicáveis ao suporte transmitir informações de localização a provedores de E911</span><span class="sxs-lookup"><span data-stu-id="33a14-144">Standards applicable to support conveying location information to E911 providers</span></span>

- [<span data-ttu-id="33a14-145">RFC 6442, a transmissão de localização para o protocolo de início de sessão</span><span class="sxs-lookup"><span data-stu-id="33a14-145">RFC 6442, Location Conveyance for the Session Initiation Protocol</span></span>](https://tools.ietf.org/html/rfc6442)

### <a name="deviations-from-the-rfcs"></a><span data-ttu-id="33a14-146">Desvios da RFC</span><span class="sxs-lookup"><span data-stu-id="33a14-146">Deviations from the RFC's</span></span>

<span data-ttu-id="33a14-147">A tabela a seguir lista as seções da (s) RFC (s) nas quais a implementação da Microsoft do SIP ou da pilha de mídia se desvia do padrão:</span><span class="sxs-lookup"><span data-stu-id="33a14-147">The following table lists the sections of the RFC(s) in which Microsoft's implementation of the SIP or media stack deviates from the standard:</span></span>

| <span data-ttu-id="33a14-148">RFC e seções</span><span class="sxs-lookup"><span data-stu-id="33a14-148">RFC and sections</span></span> | <span data-ttu-id="33a14-149">Descrição</span><span class="sxs-lookup"><span data-stu-id="33a14-149">Description</span></span> | <span data-ttu-id="33a14-150">Desvio</span><span class="sxs-lookup"><span data-stu-id="33a14-150">Deviation</span></span> |
| :---------------------  |:---------------------- |:-----------------------|
| [<span data-ttu-id="33a14-151">RFC 6337, seção 5,3 espera e retomada da mídia</span><span class="sxs-lookup"><span data-stu-id="33a14-151">RFC 6337, section 5.3 Hold and Resume of Media</span></span>](https://tools.ietf.org/html/rfc6337#section-5.3) | <span data-ttu-id="33a14-152">A RFC permite usar "a = inativo", "a = sendonly", a = recvonly "para colocar uma chamada em espera.</span><span class="sxs-lookup"><span data-stu-id="33a14-152">RFC allows using “a=inactive”, “a=sendonly”, a=recvonly” to place a call on hold.</span></span> |<span data-ttu-id="33a14-153">O proxy SIP só dá suporte a "a = inativo" e não entende se o SBC envia "a = sendonly" ou "a = recvonly".</span><span class="sxs-lookup"><span data-stu-id="33a14-153">The SIP proxy only supports “a=inactive” and does not understand if the SBC sends “a=sendonly” or “a=recvonly”.</span></span>
| [<span data-ttu-id="33a14-154">RFC 6337, seção 5,4 "comportamento no recebimento de SDP com c = 0.0.0.0</span><span class="sxs-lookup"><span data-stu-id="33a14-154">RFC 6337, section 5.4 “Behavior on Receiving SDP with c=0.0.0.0</span></span>](https://tools.ietf.org/html/rfc6337#section-5.4) | <span data-ttu-id="33a14-155">[RFC3264](https://tools.ietf.org/html/rfc3264) requer que um agente seja capaz de receber o SDP com um endereço de conexão de 0.0.0.0, nesse caso significa que nem RTP nem RTCP devem ser enviados para o par.</span><span class="sxs-lookup"><span data-stu-id="33a14-155">[RFC3264](https://tools.ietf.org/html/rfc3264) requires that an agent is capable of receiving SDP with a connection address of 0.0.0.0, in which case it means that neither  RTP nor RTCP should be sent to the peer.</span></span> | <span data-ttu-id="33a14-156">O proxy SIP não dá suporte a essa opção.</span><span class="sxs-lookup"><span data-stu-id="33a14-156">The SIP proxy does not support this option.</span></span> |

## <a name="operational-modes"></a><span data-ttu-id="33a14-157">Modos operacionais</span><span class="sxs-lookup"><span data-stu-id="33a14-157">Operational modes</span></span>

<span data-ttu-id="33a14-158">Há dois modos operacionais para roteamento direto:</span><span class="sxs-lookup"><span data-stu-id="33a14-158">There are two operational modes for Direct Routing:</span></span>

- <span data-ttu-id="33a14-159">**Sem bypass de mídia** , em que todo o tráfego RTP flui entre o cliente do Teams, os processadores de mídia e o SBC.</span><span class="sxs-lookup"><span data-stu-id="33a14-159">**Without media bypass** in which all RTP traffic flows between the Teams client, the media processors, and the SBC.</span></span>  

- <span data-ttu-id="33a14-160">**Com bypass de mídia** , em que todos os fluxos de mídia RTP entre os pontos de extremidade do Teams e o SBC.</span><span class="sxs-lookup"><span data-stu-id="33a14-160">**With media bypass** in which all RTP media flows between the Teams endpoints and the SBC.</span></span> 

<span data-ttu-id="33a14-161">Observe que o tráfego SIP sempre flui pelo proxy SIP.</span><span class="sxs-lookup"><span data-stu-id="33a14-161">Note that SIP traffic always flows via the SIP proxy.</span></span>   
