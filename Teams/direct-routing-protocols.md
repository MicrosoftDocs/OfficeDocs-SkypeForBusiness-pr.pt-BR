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
description: Protocolos de Roteamento Direto
appliesto:
- Microsoft Teams
ms.openlocfilehash: 7462822626b698f95b80a716a55f94dfe92148ff
ms.sourcegitcommit: ed3d7ebb193229cab9e0e5be3dc1c28c3f622c1b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41835021"
---
# <a name="direct-routing---definitions-and-rfc-standards"></a><span data-ttu-id="e546e-103">Roteamento Direto – Definições e padrões de RFC</span><span class="sxs-lookup"><span data-stu-id="e546e-103">Direct Routing - Definitions and RFC standards</span></span>

<span data-ttu-id="e546e-104">Este artigo descreve como o Roteamento Direto do Sistema de Telefonia do Microsoft Phone implementa protocolos padrão RFC.</span><span class="sxs-lookup"><span data-stu-id="e546e-104">This article describes how Microsoft Phone System Direct Routing implements RFC standard protocols.</span></span> <span data-ttu-id="e546e-105">Este artigo destina-se aos administradores de voz que são responsáveis por configurar a conexão entre o SBC (Controlador de Borda de Sessão) local e o serviço proxy SIP (Session Initiation Protocol).</span><span class="sxs-lookup"><span data-stu-id="e546e-105">This article is intended for voice administrators who are responsible for configuring the connection between the on-premises Session Border Controller (SBC) and the Session Initiation Protocol (SIP) proxy service.</span></span>

<span data-ttu-id="e546e-106">As interfaces SBC do cliente com os seguintes componentes no back-end do Microsoft Teams:</span><span class="sxs-lookup"><span data-stu-id="e546e-106">The customer SBC interfaces with the following components in the Microsoft Teams backend:</span></span> 

- <span data-ttu-id="e546e-107">**O proxy SIP** para sinalização.</span><span class="sxs-lookup"><span data-stu-id="e546e-107">**The SIP proxy** for signaling.</span></span> <span data-ttu-id="e546e-108">Esse é o componente voltado para a Internet do Roteamento Direto que lida com conexões SIP (TLS) entre os SBCs e o Roteamento Direto.</span><span class="sxs-lookup"><span data-stu-id="e546e-108">This is the Internet-facing component of Direct Routing that handles SIP (TLS) connections between the SBCs and Direct Routing.</span></span>

- <span data-ttu-id="e546e-109">**Os processadores de mídia** para mídia.</span><span class="sxs-lookup"><span data-stu-id="e546e-109">**The media processors** for media.</span></span> <span data-ttu-id="e546e-110">Esse é o componente voltado para a Internet do Roteamento Direto que lida com o tráfego de mídia.</span><span class="sxs-lookup"><span data-stu-id="e546e-110">This is the Internet-facing component of Direct Routing that handles media traffic.</span></span> <span data-ttu-id="e546e-111">Esse componente usa protocolos SRTP e SRTCP.</span><span class="sxs-lookup"><span data-stu-id="e546e-111">This component uses SRTP and SRTCP protocols.</span></span>


<span data-ttu-id="e546e-112">Para obter mais informações sobre Roteamento Direto, consulte [Roteamento Direto do Sistema de Telefonia.](direct-routing-landing-page.md)</span><span class="sxs-lookup"><span data-stu-id="e546e-112">For more information about Direct Routing, see [Phone System Direct Routing](direct-routing-landing-page.md).</span></span>

<span data-ttu-id="e546e-113">Para saber mais sobre como o Roteamento Direto implementa o protocolo SIP, consulte [Roteamento](direct-routing-protocols-sip.md)Direto – protocolo SIP.</span><span class="sxs-lookup"><span data-stu-id="e546e-113">For more information about how Direct Routing implements the SIP protocol, see [Direct Routing - SIP protocol](direct-routing-protocols-sip.md).</span></span>

## <a name="rfc-standards"></a><span data-ttu-id="e546e-114">Padrões de RFC</span><span class="sxs-lookup"><span data-stu-id="e546e-114">RFC standards</span></span>

<span data-ttu-id="e546e-115">O Roteamento Direto atende aos padrões de RFC.</span><span class="sxs-lookup"><span data-stu-id="e546e-115">Direct Routing complies with RFC standards.</span></span>  <span data-ttu-id="e546e-116">O SBC conectado ao Roteamento Direto também deve estar em conformidade com as seguintes RFCs (ou suas sucessores).</span><span class="sxs-lookup"><span data-stu-id="e546e-116">The SBC connected to Direct Routing must also comply with the following RFCs (or their successors).</span></span> 

### <a name="standards-applicable-to-devices-that-support-non-media-bypass-mode"></a><span data-ttu-id="e546e-117">Padrões aplicáveis a dispositivos que são compatíveis com o modo de bypass sem mídia</span><span class="sxs-lookup"><span data-stu-id="e546e-117">Standards applicable to devices that support non-media bypass mode</span></span> 

<span data-ttu-id="e546e-118">Os seguintes padrões são aplicáveis a dispositivos que só suportam o modo de bypass de fora da mídia:</span><span class="sxs-lookup"><span data-stu-id="e546e-118">The following standards are applicable to devices that support only non-media bypass mode:</span></span>

- <span data-ttu-id="e546e-119">[RFC 3261 SIP:](https://tools.ietf.org/html/rfc3261)Protocolo de Iniciação de Sessão</span><span class="sxs-lookup"><span data-stu-id="e546e-119">[RFC 3261 SIP](https://tools.ietf.org/html/rfc3261): Session Initiation Protocol</span></span>
- <span data-ttu-id="e546e-120">[RFC 3325.](https://www.ietf.org/rfc/rfc3325)</span><span class="sxs-lookup"><span data-stu-id="e546e-120">[RFC 3325](https://www.ietf.org/rfc/rfc3325).</span></span> <span data-ttu-id="e546e-121">Extensão privada para o Protocolo de Iniciação de Sessão para identidade afirmada em Redes Confiáveis, seções sobre como lidar com o header de identidade de P.</span><span class="sxs-lookup"><span data-stu-id="e546e-121">Private Extension to the Session Initiation Protocol for asserted identity within Trusted Networks--Sections about handling P-Asserted-Identity header.</span></span> <span data-ttu-id="e546e-122">O Roteamento Direto envia identidade de P-Asserted com os headers de ID de Privacidade.</span><span class="sxs-lookup"><span data-stu-id="e546e-122">Direct Routing sends P-Asserted-Identity with Privacy ID headers.</span></span> 
- <span data-ttu-id="e546e-123">[RFC 4244](https://www.ietf.org/rfc/rfc4244.txt) Uma extensão do PROTOCOLO (Session Initiation Protocol) para obter informações de histórico necessárias.</span><span class="sxs-lookup"><span data-stu-id="e546e-123">[RFC 4244](https://www.ietf.org/rfc/rfc4244.txt) An extension to Session Initiation Protocol (SIP) for required History Information.</span></span> <span data-ttu-id="e546e-124">Confira também: Roteamento da descrição do protocolo SIP para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="e546e-124">See also: Routing SIP Protocol description for more information.</span></span>
- <span data-ttu-id="e546e-125">[RFC 3892](https://www.ietf.org/rfc/rfc3892.txt) O mecanismo de Referred-By de Iniciação Referred-By Sessão</span><span class="sxs-lookup"><span data-stu-id="e546e-125">[RFC 3892](https://www.ietf.org/rfc/rfc3892.txt) The Session Initiation Protocol Referred-By mechanism</span></span>
- <span data-ttu-id="e546e-126">[RFC 3891](https://www.ietf.org/rfc/rfc3891.txt) O protocolo SIP (Session Initiation Protocol) "Substitui" Header</span><span class="sxs-lookup"><span data-stu-id="e546e-126">[RFC 3891](https://www.ietf.org/rfc/rfc3891.txt) The Session Initiation Protocol (SIP) "Replaces" Header</span></span> 
- <span data-ttu-id="e546e-127">[RFC 6337](https://tools.ietf.org/html/rfc6337) Uso do Protocolo SIP do Modelo de Oferta/Resposta.</span><span class="sxs-lookup"><span data-stu-id="e546e-127">[RFC 6337](https://tools.ietf.org/html/rfc6337) Session Initiation Protocol (SIP) Usage of the Offer/Answer Model.</span></span>
  <span data-ttu-id="e546e-128">Confira a seção "Desvios de RFC".</span><span class="sxs-lookup"><span data-stu-id="e546e-128">See the “Deviations from RFC” section.</span></span>
- <span data-ttu-id="e546e-129">[RFC 3711](https://tools.ietf.org/html/rfc3711) e [RFC 4771.](https://tools.ietf.org/html/rfc4771)</span><span class="sxs-lookup"><span data-stu-id="e546e-129">[RFC 3711](https://tools.ietf.org/html/rfc3711) and [RFC 4771](https://tools.ietf.org/html/rfc4771).</span></span> <span data-ttu-id="e546e-130">Proteja o tráfego RTP usando SRTP.</span><span class="sxs-lookup"><span data-stu-id="e546e-130">Protect RTP traffic using SRTP.</span></span> <span data-ttu-id="e546e-131">O SBC deve ser capaz de estabelecer chaves usando o SDES.</span><span class="sxs-lookup"><span data-stu-id="e546e-131">The SBC must be able to establish keys using SDES.</span></span> 
- <span data-ttu-id="e546e-132">[RFC 8035](https://www.ietf.org/rfc/rfc8035.txt) Esclarecimentos de protocolo SDP (Session Description Protocol) para Multiplexing RTP/RTCP</span><span class="sxs-lookup"><span data-stu-id="e546e-132">[RFC 8035](https://www.ietf.org/rfc/rfc8035.txt) Session Description Protocol (SDP) Offer/Answer Clarifications for RTP/RTCP Multiplexing</span></span>

### <a name="standards-applicable-to-devices-that-support-media-bypass-mode"></a><span data-ttu-id="e546e-133">Padrões aplicáveis a dispositivos que são compatíveis com o modo de bypass de mídia</span><span class="sxs-lookup"><span data-stu-id="e546e-133">Standards applicable to devices that support media bypass mode</span></span>

<span data-ttu-id="e546e-134">Além dos padrões listados conforme aplicável ao modo não bypass, os seguintes padrões são usados para o modo de bypass de mídia:</span><span class="sxs-lookup"><span data-stu-id="e546e-134">In addition to the standards listed as applicable to non-bypass mode, the following standards are used for media bypass mode:</span></span>

- <span data-ttu-id="e546e-135">[RFC 5245 Interactive Connectivity Bypass (ICE) para bypass de mídia.](https://tools.ietf.org/html/rfc5245)</span><span class="sxs-lookup"><span data-stu-id="e546e-135">[RFC 5245 Interactive Connectivity Establishment (ICE) for media bypass](https://tools.ietf.org/html/rfc5245).</span></span>  <span data-ttu-id="e546e-136">O SBC deve dar suporte ao seguinte:</span><span class="sxs-lookup"><span data-stu-id="e546e-136">The SBC must support the following:</span></span>
  - <span data-ttu-id="e546e-137">ICE Lite - os clientes do Teams são clientes ICE completos</span><span class="sxs-lookup"><span data-stu-id="e546e-137">ICE Lite - the Teams clients are full ICE clients</span></span>
  - <span data-ttu-id="e546e-138">[ICE reinicia.](https://tools.ietf.org/html/rfc5245#section-9.1.1.1)</span><span class="sxs-lookup"><span data-stu-id="e546e-138">[ICE Restarts](https://tools.ietf.org/html/rfc5245#section-9.1.1.1).</span></span> <span data-ttu-id="e546e-139">Veja mais sobre as reinicializações ice e exemplos de caso de uso no Ice Restart: Ignorar chamada de mídia transferida para um ponto de extremidade que não dá suporte a bypass de mídia</span><span class="sxs-lookup"><span data-stu-id="e546e-139">See more on ICE restarts use case and examples in ICE Restart:  Media bypass call transferred to an endpoint which does not support media bypass</span></span>   
- <span data-ttu-id="e546e-140">[Controle de chamada SIP (RFC RFC RFC 5589 Session Initiation Protocol) – Transferência.](https://tools.ietf.org/html/rfc5589)</span><span class="sxs-lookup"><span data-stu-id="e546e-140">[RFC RFC 5589 Session Initiation Protocol (SIP) Call Control – Transfer](https://tools.ietf.org/html/rfc5589).</span></span> 
- <span data-ttu-id="e546e-141">[RFC 3960 Early Media](https://tools.ietf.org/html/rfc3960)e Geração de Tom de Toque no PROTOCOLO ,confira as seções 3.1, Forking e 3.2, Geração de Tom de Toque</span><span class="sxs-lookup"><span data-stu-id="e546e-141">[RFC 3960 Early Media and Ringing Tone Generation in the Session Initiation Protocol (SIP)](https://tools.ietf.org/html/rfc3960), see sections 3.1, Forking, and 3.2, Ringing Tone Generation</span></span> 
- [<span data-ttu-id="e546e-142">RFC 5389 Session Traversal Utilities for NAT (STUN)</span><span class="sxs-lookup"><span data-stu-id="e546e-142">RFC 5389 Session Traversal Utilities for NAT (STUN)</span></span>](https://tools.ietf.org/html/rfc5389)
- [<span data-ttu-id="e546e-143">RFC 5766 Traversal Using Relays around NAT (TURN): Relay Extensions to Session Traversal Utilities for NAT (STUN)</span><span class="sxs-lookup"><span data-stu-id="e546e-143">RFC 5766 Traversal Using Relays around NAT (TURN): Relay Extensions to Session Traversal Utilities for NAT (STUN)</span></span>](https://tools.ietf.org/html/rfc5766)

### <a name="standards-applicable-to-support-conveying-location-information-to-e911-providers"></a><span data-ttu-id="e546e-144">Padrões aplicáveis ao suporte à transmissão de informações de localização para provedores E911</span><span class="sxs-lookup"><span data-stu-id="e546e-144">Standards applicable to support conveying location information to E911 providers</span></span>

- [<span data-ttu-id="e546e-145">RFC 6442, Transmissão de Local para o Protocolo de Início de Sessão</span><span class="sxs-lookup"><span data-stu-id="e546e-145">RFC 6442, Location Conveyance for the Session Initiation Protocol</span></span>](https://tools.ietf.org/html/rfc6442)

### <a name="deviations-from-the-rfcs"></a><span data-ttu-id="e546e-146">Desvios do RFC</span><span class="sxs-lookup"><span data-stu-id="e546e-146">Deviations from the RFC's</span></span>

<span data-ttu-id="e546e-147">A tabela a seguir lista as seções das RFC(s) nas quais a implementação da Microsoft do SIP ou da pilha de mídias se desvia do padrão:</span><span class="sxs-lookup"><span data-stu-id="e546e-147">The following table lists the sections of the RFC(s) in which Microsoft's implementation of the SIP or media stack deviates from the standard:</span></span>

| <span data-ttu-id="e546e-148">RFC e seções</span><span class="sxs-lookup"><span data-stu-id="e546e-148">RFC and sections</span></span> | <span data-ttu-id="e546e-149">Descrição</span><span class="sxs-lookup"><span data-stu-id="e546e-149">Description</span></span> | <span data-ttu-id="e546e-150">Desvio</span><span class="sxs-lookup"><span data-stu-id="e546e-150">Deviation</span></span> |
| :---------------------  |:---------------------- |:-----------------------|
| [<span data-ttu-id="e546e-151">RFC 6337, seção 5.3 Espera e Currículo de Mídia</span><span class="sxs-lookup"><span data-stu-id="e546e-151">RFC 6337, section 5.3 Hold and Resume of Media</span></span>](https://tools.ietf.org/html/rfc6337#section-5.3) | <span data-ttu-id="e546e-152">O RFC permite usar "a=inativo", "a=sendonly", a=rec recly" para colocar uma chamada em espera.</span><span class="sxs-lookup"><span data-stu-id="e546e-152">RFC allows using “a=inactive”, “a=sendonly”, a=recvonly” to place a call on hold.</span></span> |<span data-ttu-id="e546e-153">O proxy SIP só dá suporte a "a=inativo" e não entende se o SBC envia "a=sendonly" ou "a=rec rec</span><span class="sxs-lookup"><span data-stu-id="e546e-153">The SIP proxy only supports “a=inactive” and does not understand if the SBC sends “a=sendonly” or “a=recvonly”.</span></span>
| [<span data-ttu-id="e546e-154">RFC 6337, seção 5.4 "Comportamento ao receber SDP com c=0.0.0.0.0</span><span class="sxs-lookup"><span data-stu-id="e546e-154">RFC 6337, section 5.4 “Behavior on Receiving SDP with c=0.0.0.0</span></span>](https://tools.ietf.org/html/rfc6337#section-5.4) | <span data-ttu-id="e546e-155">[RFC3264](https://tools.ietf.org/html/rfc3264) requer que um agente seja capaz de receber SDP com um endereço de conexão de 0.0.0.0, nesse caso isso significa que nem RTP nem RTCP devem ser enviados para o ponto.</span><span class="sxs-lookup"><span data-stu-id="e546e-155">[RFC3264](https://tools.ietf.org/html/rfc3264) requires that an agent is capable of receiving SDP with a connection address of 0.0.0.0, in which case it means that neither  RTP nor RTCP should be sent to the peer.</span></span> | <span data-ttu-id="e546e-156">O proxy SIP não dá suporte a essa opção.</span><span class="sxs-lookup"><span data-stu-id="e546e-156">The SIP proxy does not support this option.</span></span> |

## <a name="operational-modes"></a><span data-ttu-id="e546e-157">Modos operacionais</span><span class="sxs-lookup"><span data-stu-id="e546e-157">Operational modes</span></span>

<span data-ttu-id="e546e-158">Há dois modos operacionais para Roteamento Direto:</span><span class="sxs-lookup"><span data-stu-id="e546e-158">There are two operational modes for Direct Routing:</span></span>

- <span data-ttu-id="e546e-159">**Sem bypass de mídia** em que todo o tráfego RTP flui entre o cliente do Teams, os processadores de mídia e o SBC.</span><span class="sxs-lookup"><span data-stu-id="e546e-159">**Without media bypass** in which all RTP traffic flows between the Teams client, the media processors, and the SBC.</span></span>  

- <span data-ttu-id="e546e-160">**Com o bypass de** mídia no qual todas as mídias RTP fluem entre os pontos de extremidade do Teams e o SBC.</span><span class="sxs-lookup"><span data-stu-id="e546e-160">**With media bypass** in which all RTP media flows between the Teams endpoints and the SBC.</span></span> 

<span data-ttu-id="e546e-161">Observe que o tráfego SIP sempre flui por meio do proxy SIP.</span><span class="sxs-lookup"><span data-stu-id="e546e-161">Note that SIP traffic always flows via the SIP proxy.</span></span>   
