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
ms.openlocfilehash: 88fb4459192ad9ff5af8702878d1cbf6a59d8e9d
ms.sourcegitcommit: 6227667c9941cc3289029099b7b6781581f16ea7
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/19/2021
ms.locfileid: "52569199"
---
# <a name="direct-routing---definitions-and-rfc-standards"></a><span data-ttu-id="76128-103">Roteamento Direto - Definições e padrões RFC</span><span class="sxs-lookup"><span data-stu-id="76128-103">Direct Routing - Definitions and RFC standards</span></span>

<span data-ttu-id="76128-104">Este artigo descreve como o Telefone Microsoft roteamento direto do sistema implementa protocolos padrão RFC.</span><span class="sxs-lookup"><span data-stu-id="76128-104">This article describes how Microsoft Phone System Direct Routing implements RFC standard protocols.</span></span> <span data-ttu-id="76128-105">Este artigo destina-se aos administradores de voz responsáveis por configurar a conexão entre o SBC (Controlador de Borda de Sessão) local e o serviço proxy SIP (Session Initiation Protocol).</span><span class="sxs-lookup"><span data-stu-id="76128-105">This article is intended for voice administrators who are responsible for configuring the connection between the on-premises Session Border Controller (SBC) and the Session Initiation Protocol (SIP) proxy service.</span></span>

<span data-ttu-id="76128-106">As interfaces SBC do cliente com os seguintes componentes no back-Microsoft Teams back-back:</span><span class="sxs-lookup"><span data-stu-id="76128-106">The customer SBC interfaces with the following components in the Microsoft Teams backend:</span></span> 

- <span data-ttu-id="76128-107">**O proxy SIP** para sinalização.</span><span class="sxs-lookup"><span data-stu-id="76128-107">**The SIP proxy** for signaling.</span></span> <span data-ttu-id="76128-108">Esse é o componente voltado para a Internet do Roteamento Direto que lida com conexões SIP (TLS) entre os SBCs e o Roteamento Direto.</span><span class="sxs-lookup"><span data-stu-id="76128-108">This is the Internet-facing component of Direct Routing that handles SIP (TLS) connections between the SBCs and Direct Routing.</span></span>

- <span data-ttu-id="76128-109">**Os processadores de mídia** para mídia.</span><span class="sxs-lookup"><span data-stu-id="76128-109">**The media processors** for media.</span></span> <span data-ttu-id="76128-110">Esse é o componente voltado para a Internet do Roteamento Direto que lida com o tráfego de mídia.</span><span class="sxs-lookup"><span data-stu-id="76128-110">This is the Internet-facing component of Direct Routing that handles media traffic.</span></span> <span data-ttu-id="76128-111">Esse componente usa protocolos SRTP e SRTCP.</span><span class="sxs-lookup"><span data-stu-id="76128-111">This component uses SRTP and SRTCP protocols.</span></span>


<span data-ttu-id="76128-112">Para obter mais informações sobre Roteamento Direto, [consulte Sistema de Telefonia Roteamento Direto.](direct-routing-landing-page.md)</span><span class="sxs-lookup"><span data-stu-id="76128-112">For more information about Direct Routing, see [Phone System Direct Routing](direct-routing-landing-page.md).</span></span>

<span data-ttu-id="76128-113">Para obter mais informações sobre como o Roteamento Direto implementa o protocolo SIP, consulte [Roteamento Direto - protocolo SIP](direct-routing-protocols-sip.md).</span><span class="sxs-lookup"><span data-stu-id="76128-113">For more information about how Direct Routing implements the SIP protocol, see [Direct Routing - SIP protocol](direct-routing-protocols-sip.md).</span></span>

## <a name="rfc-standards"></a><span data-ttu-id="76128-114">Padrões RFC</span><span class="sxs-lookup"><span data-stu-id="76128-114">RFC standards</span></span>

<span data-ttu-id="76128-115">O Roteamento Direto está em conformidade com os padrões RFC.</span><span class="sxs-lookup"><span data-stu-id="76128-115">Direct Routing complies with RFC standards.</span></span>  <span data-ttu-id="76128-116">O SBC conectado ao Roteamento Direto também deve estar em conformidade com os seguintes RFCs (ou seus sucessores).</span><span class="sxs-lookup"><span data-stu-id="76128-116">The SBC connected to Direct Routing must also comply with the following RFCs (or their successors).</span></span> 

### <a name="standards-applicable-to-devices-that-support-non-media-bypass-mode"></a><span data-ttu-id="76128-117">Padrões aplicáveis a dispositivos que suportam o modo de bypass sem mídia</span><span class="sxs-lookup"><span data-stu-id="76128-117">Standards applicable to devices that support non-media bypass mode</span></span> 

<span data-ttu-id="76128-118">Os seguintes padrões são aplicáveis a dispositivos que suportam apenas o modo de desvio de mídia:</span><span class="sxs-lookup"><span data-stu-id="76128-118">The following standards are applicable to devices that support only non-media bypass mode:</span></span>

- <span data-ttu-id="76128-119">[RFC 3261 SIP](https://tools.ietf.org/html/rfc3261): Protocolo de Iniciação de Sessão</span><span class="sxs-lookup"><span data-stu-id="76128-119">[RFC 3261 SIP](https://tools.ietf.org/html/rfc3261): Session Initiation Protocol</span></span>
- <span data-ttu-id="76128-120">[RFC 3325](https://www.ietf.org/rfc/rfc3325).</span><span class="sxs-lookup"><span data-stu-id="76128-120">[RFC 3325](https://www.ietf.org/rfc/rfc3325).</span></span> <span data-ttu-id="76128-121">Extensão privada para o Protocolo de Iniciação de Sessão para identidade afirmada em Redes Confiáveis-- Seções sobre como manipular o header P-Asserted-Identity.</span><span class="sxs-lookup"><span data-stu-id="76128-121">Private Extension to the Session Initiation Protocol for asserted identity within Trusted Networks--Sections about handling P-Asserted-Identity header.</span></span> <span data-ttu-id="76128-122">O Roteamento Direto envia P-Asserted-Identity com headers de ID de Privacidade.</span><span class="sxs-lookup"><span data-stu-id="76128-122">Direct Routing sends P-Asserted-Identity with Privacy ID headers.</span></span> 
- <span data-ttu-id="76128-123">[RFC 4244](https://www.ietf.org/rfc/rfc4244.txt) Uma extensão para SIP (Session Initiation Protocol) para informações de histórico necessárias.</span><span class="sxs-lookup"><span data-stu-id="76128-123">[RFC 4244](https://www.ietf.org/rfc/rfc4244.txt) An extension to Session Initiation Protocol (SIP) for required History Information.</span></span> <span data-ttu-id="76128-124">Consulte também: Roteamento de descrição do Protocolo SIP para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="76128-124">See also: Routing SIP Protocol description for more information.</span></span>
- <span data-ttu-id="76128-125">[RFC 3892](https://www.ietf.org/rfc/rfc3892.txt) O mecanismo de Referred-By de iniciação de sessão</span><span class="sxs-lookup"><span data-stu-id="76128-125">[RFC 3892](https://www.ietf.org/rfc/rfc3892.txt) The Session Initiation Protocol Referred-By mechanism</span></span>
- <span data-ttu-id="76128-126">[RFC 3891](https://www.ietf.org/rfc/rfc3891.txt) O Protocolo de Iniciação de Sessão (SIP) "Substitui" o Header</span><span class="sxs-lookup"><span data-stu-id="76128-126">[RFC 3891](https://www.ietf.org/rfc/rfc3891.txt) The Session Initiation Protocol (SIP) "Replaces" Header</span></span> 
- <span data-ttu-id="76128-127">[RFC 6337](https://tools.ietf.org/html/rfc6337) Uso do Sip (Protocolo de Iniciação de Sessão) do modelo de oferta/resposta.</span><span class="sxs-lookup"><span data-stu-id="76128-127">[RFC 6337](https://tools.ietf.org/html/rfc6337) Session Initiation Protocol (SIP) Usage of the Offer/Answer Model.</span></span>
  <span data-ttu-id="76128-128">Consulte a seção "Desvios de RFC".</span><span class="sxs-lookup"><span data-stu-id="76128-128">See the “Deviations from RFC” section.</span></span>
- <span data-ttu-id="76128-129">[RFC 3711](https://tools.ietf.org/html/rfc3711) e [RFC 4771](https://tools.ietf.org/html/rfc4771).</span><span class="sxs-lookup"><span data-stu-id="76128-129">[RFC 3711](https://tools.ietf.org/html/rfc3711) and [RFC 4771](https://tools.ietf.org/html/rfc4771).</span></span> <span data-ttu-id="76128-130">Proteja o tráfego RTP usando SRTP.</span><span class="sxs-lookup"><span data-stu-id="76128-130">Protect RTP traffic using SRTP.</span></span> <span data-ttu-id="76128-131">O SBC deve ser capaz de estabelecer chaves usando o SDES.</span><span class="sxs-lookup"><span data-stu-id="76128-131">The SBC must be able to establish keys using SDES.</span></span> 
- <span data-ttu-id="76128-132">[RFC 8035](https://www.ietf.org/rfc/rfc8035.txt) Protocolo de Descrição da Sessão (SDP) Esclarecimentos de oferta/resposta para multiplexação RTP/RTCP</span><span class="sxs-lookup"><span data-stu-id="76128-132">[RFC 8035](https://www.ietf.org/rfc/rfc8035.txt) Session Description Protocol (SDP) Offer/Answer Clarifications for RTP/RTCP Multiplexing</span></span>

### <a name="standards-applicable-to-devices-that-support-media-bypass-mode"></a><span data-ttu-id="76128-133">Padrões aplicáveis a dispositivos que suportam o modo de bypass de mídia</span><span class="sxs-lookup"><span data-stu-id="76128-133">Standards applicable to devices that support media bypass mode</span></span>

<span data-ttu-id="76128-134">Além dos padrões listados como aplicáveis ao modo não bypass, os seguintes padrões são usados para o modo de bypass de mídia:</span><span class="sxs-lookup"><span data-stu-id="76128-134">In addition to the standards listed as applicable to non-bypass mode, the following standards are used for media bypass mode:</span></span>

- <span data-ttu-id="76128-135">[RFC 5245 Interactive Connectivity Establishment (ICE) para bypass de mídia.](https://tools.ietf.org/html/rfc5245)</span><span class="sxs-lookup"><span data-stu-id="76128-135">[RFC 5245 Interactive Connectivity Establishment (ICE) for media bypass](https://tools.ietf.org/html/rfc5245).</span></span>  <span data-ttu-id="76128-136">O SBC deve dar suporte ao seguinte:</span><span class="sxs-lookup"><span data-stu-id="76128-136">The SBC must support the following:</span></span>
  - <span data-ttu-id="76128-137">ICE Lite - os clientes Teams são clientes ICE completos</span><span class="sxs-lookup"><span data-stu-id="76128-137">ICE Lite - the Teams clients are full ICE clients</span></span>
  - <span data-ttu-id="76128-138">[O ICE reinicia](https://tools.ietf.org/html/rfc5245#section-9.1.1.1).</span><span class="sxs-lookup"><span data-stu-id="76128-138">[ICE Restarts](https://tools.ietf.org/html/rfc5245#section-9.1.1.1).</span></span> <span data-ttu-id="76128-139">Consulte mais em Reinicializações de ICE use case e exemplos em Ice Restart: Chamada de desvio de mídia transferida para um ponto de extremidade que não dá suporte a bypass de mídia</span><span class="sxs-lookup"><span data-stu-id="76128-139">See more on ICE restarts use case and examples in ICE Restart:  Media bypass call transferred to an endpoint which does not support media bypass</span></span>   
- <span data-ttu-id="76128-140">Controle de chamada SIP (Protocolo de Iniciação de [Sessão) RFC RFC 5589 – Transfer](https://tools.ietf.org/html/rfc5589).</span><span class="sxs-lookup"><span data-stu-id="76128-140">[RFC RFC 5589 Session Initiation Protocol (SIP) Call Control – Transfer](https://tools.ietf.org/html/rfc5589).</span></span> 
- <span data-ttu-id="76128-141">[RFC 3960 Early Media and Ringing Tone Generation in the Session Initiation Protocol (SIP),](https://tools.ietf.org/html/rfc3960)see sections 3.1, Forking, and 3.2, Ringing Tone Generation</span><span class="sxs-lookup"><span data-stu-id="76128-141">[RFC 3960 Early Media and Ringing Tone Generation in the Session Initiation Protocol (SIP)](https://tools.ietf.org/html/rfc3960), see sections 3.1, Forking, and 3.2, Ringing Tone Generation</span></span> 
- [<span data-ttu-id="76128-142">Utilitários de Translúção de Sessão RFC 5389 para NAT (STUN)</span><span class="sxs-lookup"><span data-stu-id="76128-142">RFC 5389 Session Traversal Utilities for NAT (STUN)</span></span>](https://tools.ietf.org/html/rfc5389)
- [<span data-ttu-id="76128-143">RFC 5766 Traversal Using Relays around NAT (TURN): Relay Extensions to Session Traversal Utilities for NAT (STUN)</span><span class="sxs-lookup"><span data-stu-id="76128-143">RFC 5766 Traversal Using Relays around NAT (TURN): Relay Extensions to Session Traversal Utilities for NAT (STUN)</span></span>](https://tools.ietf.org/html/rfc5766)

### <a name="standards-applicable-to-support-conveying-location-information-to-e911-providers"></a><span data-ttu-id="76128-144">Padrões aplicáveis para dar suporte a informações de local de transporte para provedores E911</span><span class="sxs-lookup"><span data-stu-id="76128-144">Standards applicable to support conveying location information to E911 providers</span></span>

- [<span data-ttu-id="76128-145">RFC 6442, Transporte de Local para o Protocolo de Iniciação de Sessão</span><span class="sxs-lookup"><span data-stu-id="76128-145">RFC 6442, Location Conveyance for the Session Initiation Protocol</span></span>](https://tools.ietf.org/html/rfc6442)

### <a name="deviations-from-the-rfcs"></a><span data-ttu-id="76128-146">Desvios do RFC</span><span class="sxs-lookup"><span data-stu-id="76128-146">Deviations from the RFC's</span></span>

<span data-ttu-id="76128-147">A tabela a seguir lista as seções dos RFC(s) em que a implementação da Microsoft do SIP ou da pilha de mídia se desvia do padrão:</span><span class="sxs-lookup"><span data-stu-id="76128-147">The following table lists the sections of the RFC(s) in which Microsoft's implementation of the SIP or media stack deviates from the standard:</span></span>

| <span data-ttu-id="76128-148">RFC e seções</span><span class="sxs-lookup"><span data-stu-id="76128-148">RFC and sections</span></span> | <span data-ttu-id="76128-149">Descrição</span><span class="sxs-lookup"><span data-stu-id="76128-149">Description</span></span> | <span data-ttu-id="76128-150">Desvio</span><span class="sxs-lookup"><span data-stu-id="76128-150">Deviation</span></span> |
| :---------------------  |:---------------------- |:-----------------------|
| [<span data-ttu-id="76128-151">RFC 6337, seção 5.3 Hold e Resume of Media</span><span class="sxs-lookup"><span data-stu-id="76128-151">RFC 6337, section 5.3 Hold and Resume of Media</span></span>](https://tools.ietf.org/html/rfc6337#section-5.3) | <span data-ttu-id="76128-152">RFC permite usar "a=inativo", "a=sendonly", a=recvonly" para colocar uma chamada em espera.</span><span class="sxs-lookup"><span data-stu-id="76128-152">RFC allows using “a=inactive”, “a=sendonly”, a=recvonly” to place a call on hold.</span></span> |<span data-ttu-id="76128-153">O proxy SIP só dá suporte a "a=inativo" e não entende se o SBC envia "a=sendonly" ou "a=recvonly".</span><span class="sxs-lookup"><span data-stu-id="76128-153">The SIP proxy only supports “a=inactive” and does not understand if the SBC sends “a=sendonly” or “a=recvonly”.</span></span>
| [<span data-ttu-id="76128-154">RFC 6337, seção 5.4 "Comportamento no recebimento de SDP com c=0,0.0.0</span><span class="sxs-lookup"><span data-stu-id="76128-154">RFC 6337, section 5.4 “Behavior on Receiving SDP with c=0.0.0.0</span></span>](https://tools.ietf.org/html/rfc6337#section-5.4) | <span data-ttu-id="76128-155">[RFC3264](https://tools.ietf.org/html/rfc3264) exige que um agente seja capaz de receber SDP com um endereço de conexão de 0.0.0.0, nesse caso significa que nem RTP nem RTCP devem ser enviados para o par.</span><span class="sxs-lookup"><span data-stu-id="76128-155">[RFC3264](https://tools.ietf.org/html/rfc3264) requires that an agent is capable of receiving SDP with a connection address of 0.0.0.0, in which case it means that neither  RTP nor RTCP should be sent to the peer.</span></span> | <span data-ttu-id="76128-156">O proxy SIP não dá suporte a essa opção.</span><span class="sxs-lookup"><span data-stu-id="76128-156">The SIP proxy does not support this option.</span></span> |

## <a name="operational-modes"></a><span data-ttu-id="76128-157">Modos operacionais</span><span class="sxs-lookup"><span data-stu-id="76128-157">Operational modes</span></span>

<span data-ttu-id="76128-158">Há dois modos operacionais para Roteamento Direto:</span><span class="sxs-lookup"><span data-stu-id="76128-158">There are two operational modes for Direct Routing:</span></span>

- <span data-ttu-id="76128-159">**Sem bypass de mídia** no qual todo o tráfego RTP flui entre o cliente Teams, os processadores de mídia e o SBC.</span><span class="sxs-lookup"><span data-stu-id="76128-159">**Without media bypass** in which all RTP traffic flows between the Teams client, the media processors, and the SBC.</span></span>  

- <span data-ttu-id="76128-160">**Com o bypass de mídia** no qual todas as mídias RTP fluem entre os Teams e o SBC.</span><span class="sxs-lookup"><span data-stu-id="76128-160">**With media bypass** in which all RTP media flows between the Teams endpoints and the SBC.</span></span> 

<span data-ttu-id="76128-161">Observe que o tráfego SIP sempre flui por meio do proxy SIP.</span><span class="sxs-lookup"><span data-stu-id="76128-161">Note that SIP traffic always flows via the SIP proxy.</span></span> 

## <a name="dtmf"></a><span data-ttu-id="76128-162">DTMF</span><span class="sxs-lookup"><span data-stu-id="76128-162">DTMF</span></span>
<span data-ttu-id="76128-163">A DTMF em banda não é suportada pela pilha de mídia.</span><span class="sxs-lookup"><span data-stu-id="76128-163">In-band DTMF is not supported by media stack.</span></span>
