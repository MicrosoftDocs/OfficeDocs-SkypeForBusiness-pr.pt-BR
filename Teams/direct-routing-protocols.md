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
ms.openlocfilehash: 88fb4459192ad9ff5af8702878d1cbf6a59d8e9d
ms.sourcegitcommit: 6227667c9941cc3289029099b7b6781581f16ea7
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/19/2021
ms.locfileid: "52569199"
---
# <a name="direct-routing---definitions-and-rfc-standards"></a><span data-ttu-id="d3ff2-103">Roteamento Direto - Definições e padrões RFC</span><span class="sxs-lookup"><span data-stu-id="d3ff2-103">Direct Routing - Definitions and RFC standards</span></span>

<span data-ttu-id="d3ff2-104">Este artigo descreve como o roteamento direto do sistema de Telefone Microsoft implementa protocolos padrão RFC.</span><span class="sxs-lookup"><span data-stu-id="d3ff2-104">This article describes how Microsoft Phone System Direct Routing implements RFC standard protocols.</span></span> <span data-ttu-id="d3ff2-105">Este artigo destina-se a administradores de voz responsáveis pela configuração da conexão entre o SBC (Session Border Controller, controlador de borda de sessão) no local e o serviço de proxy Do Protocolo de Iniciação de Sessão (SIP).</span><span class="sxs-lookup"><span data-stu-id="d3ff2-105">This article is intended for voice administrators who are responsible for configuring the connection between the on-premises Session Border Controller (SBC) and the Session Initiation Protocol (SIP) proxy service.</span></span>

<span data-ttu-id="d3ff2-106">O SBC do cliente interfaces com os seguintes componentes no backend Microsoft Teams:</span><span class="sxs-lookup"><span data-stu-id="d3ff2-106">The customer SBC interfaces with the following components in the Microsoft Teams backend:</span></span> 

- <span data-ttu-id="d3ff2-107">**O proxy SIP** para sinalização.</span><span class="sxs-lookup"><span data-stu-id="d3ff2-107">**The SIP proxy** for signaling.</span></span> <span data-ttu-id="d3ff2-108">Este é o componente voltado para a Internet do Direct Routing que lida com conexões SIP (TLS) entre os SBCs e o Direct Routing.</span><span class="sxs-lookup"><span data-stu-id="d3ff2-108">This is the Internet-facing component of Direct Routing that handles SIP (TLS) connections between the SBCs and Direct Routing.</span></span>

- <span data-ttu-id="d3ff2-109">**Os processadores de mídia** para mídia.</span><span class="sxs-lookup"><span data-stu-id="d3ff2-109">**The media processors** for media.</span></span> <span data-ttu-id="d3ff2-110">Este é o componente voltado para a Internet do Direct Routing que lida com o tráfego de mídia.</span><span class="sxs-lookup"><span data-stu-id="d3ff2-110">This is the Internet-facing component of Direct Routing that handles media traffic.</span></span> <span data-ttu-id="d3ff2-111">Este componente usa protocolos SRTP e SRTCP.</span><span class="sxs-lookup"><span data-stu-id="d3ff2-111">This component uses SRTP and SRTCP protocols.</span></span>


<span data-ttu-id="d3ff2-112">Para obter mais informações sobre o Direct Routing, consulte [Sistema de Telefonia Direct Routing](direct-routing-landing-page.md).</span><span class="sxs-lookup"><span data-stu-id="d3ff2-112">For more information about Direct Routing, see [Phone System Direct Routing](direct-routing-landing-page.md).</span></span>

<span data-ttu-id="d3ff2-113">Para obter mais informações sobre como o Direct Routing implementa o protocolo SIP, consulte [Direct Routing - Protocolo SIP](direct-routing-protocols-sip.md).</span><span class="sxs-lookup"><span data-stu-id="d3ff2-113">For more information about how Direct Routing implements the SIP protocol, see [Direct Routing - SIP protocol](direct-routing-protocols-sip.md).</span></span>

## <a name="rfc-standards"></a><span data-ttu-id="d3ff2-114">Normas RFC</span><span class="sxs-lookup"><span data-stu-id="d3ff2-114">RFC standards</span></span>

<span data-ttu-id="d3ff2-115">O Roteamento Direto está em conformidade com as normas RFC.</span><span class="sxs-lookup"><span data-stu-id="d3ff2-115">Direct Routing complies with RFC standards.</span></span>  <span data-ttu-id="d3ff2-116">O SBC conectado ao Roteamento Direto também deve cumprir com os seguintes RFCs (ou seus sucessores).</span><span class="sxs-lookup"><span data-stu-id="d3ff2-116">The SBC connected to Direct Routing must also comply with the following RFCs (or their successors).</span></span> 

### <a name="standards-applicable-to-devices-that-support-non-media-bypass-mode"></a><span data-ttu-id="d3ff2-117">Padrões aplicáveis a dispositivos que suportam o modo de bypass não-media</span><span class="sxs-lookup"><span data-stu-id="d3ff2-117">Standards applicable to devices that support non-media bypass mode</span></span> 

<span data-ttu-id="d3ff2-118">Os seguintes padrões são aplicáveis a dispositivos que suportam apenas o modo de bypass não-media:</span><span class="sxs-lookup"><span data-stu-id="d3ff2-118">The following standards are applicable to devices that support only non-media bypass mode:</span></span>

- <span data-ttu-id="d3ff2-119">[RFC 3261 SIP](https://tools.ietf.org/html/rfc3261): Protocolo de Iniciação de Sessão</span><span class="sxs-lookup"><span data-stu-id="d3ff2-119">[RFC 3261 SIP](https://tools.ietf.org/html/rfc3261): Session Initiation Protocol</span></span>
- <span data-ttu-id="d3ff2-120">[RFC 3325](https://www.ietf.org/rfc/rfc3325).</span><span class="sxs-lookup"><span data-stu-id="d3ff2-120">[RFC 3325](https://www.ietf.org/rfc/rfc3325).</span></span> <span data-ttu-id="d3ff2-121">Extensão privada ao Protocolo de Iniciação de Sessão para identidade afirmada em redes confiáveis - seções sobre o manuseio do cabeçalho P-Asserted-Identity.</span><span class="sxs-lookup"><span data-stu-id="d3ff2-121">Private Extension to the Session Initiation Protocol for asserted identity within Trusted Networks--Sections about handling P-Asserted-Identity header.</span></span> <span data-ttu-id="d3ff2-122">O roteamento direto envia P-Asserted-Identity com cabeçalhos de ID de privacidade.</span><span class="sxs-lookup"><span data-stu-id="d3ff2-122">Direct Routing sends P-Asserted-Identity with Privacy ID headers.</span></span> 
- <span data-ttu-id="d3ff2-123">[RFC 4244](https://www.ietf.org/rfc/rfc4244.txt) Uma extensão do Protocolo de Iniciação de Sessão (SIP) para informações de histórico necessárias.</span><span class="sxs-lookup"><span data-stu-id="d3ff2-123">[RFC 4244](https://www.ietf.org/rfc/rfc4244.txt) An extension to Session Initiation Protocol (SIP) for required History Information.</span></span> <span data-ttu-id="d3ff2-124">Veja também: Roteamento SIP Protocol descrição para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="d3ff2-124">See also: Routing SIP Protocol description for more information.</span></span>
- <span data-ttu-id="d3ff2-125">[RFC 3892](https://www.ietf.org/rfc/rfc3892.txt) O protocolo de iniciação da sessão Referred-By mecanismo</span><span class="sxs-lookup"><span data-stu-id="d3ff2-125">[RFC 3892](https://www.ietf.org/rfc/rfc3892.txt) The Session Initiation Protocol Referred-By mechanism</span></span>
- <span data-ttu-id="d3ff2-126">[RFC 3891](https://www.ietf.org/rfc/rfc3891.txt) O cabeçalho "Substitui" do Protocolo de Iniciação da Sessão (SIP)</span><span class="sxs-lookup"><span data-stu-id="d3ff2-126">[RFC 3891](https://www.ietf.org/rfc/rfc3891.txt) The Session Initiation Protocol (SIP) "Replaces" Header</span></span> 
- <span data-ttu-id="d3ff2-127">[RFC 6337](https://tools.ietf.org/html/rfc6337) Uso do Protocolo de Iniciação de Sessão (SIP) do Modelo de Oferta/Resposta.</span><span class="sxs-lookup"><span data-stu-id="d3ff2-127">[RFC 6337](https://tools.ietf.org/html/rfc6337) Session Initiation Protocol (SIP) Usage of the Offer/Answer Model.</span></span>
  <span data-ttu-id="d3ff2-128">Consulte a seção "Desvios do RFC".</span><span class="sxs-lookup"><span data-stu-id="d3ff2-128">See the “Deviations from RFC” section.</span></span>
- <span data-ttu-id="d3ff2-129">[RFC 3711](https://tools.ietf.org/html/rfc3711) e [RFC 4771](https://tools.ietf.org/html/rfc4771).</span><span class="sxs-lookup"><span data-stu-id="d3ff2-129">[RFC 3711](https://tools.ietf.org/html/rfc3711) and [RFC 4771](https://tools.ietf.org/html/rfc4771).</span></span> <span data-ttu-id="d3ff2-130">Proteja o tráfego RTP usando sRTP.</span><span class="sxs-lookup"><span data-stu-id="d3ff2-130">Protect RTP traffic using SRTP.</span></span> <span data-ttu-id="d3ff2-131">O SBC deve ser capaz de estabelecer chaves usando SDES.</span><span class="sxs-lookup"><span data-stu-id="d3ff2-131">The SBC must be able to establish keys using SDES.</span></span> 
- <span data-ttu-id="d3ff2-132">[RFC 8035](https://www.ietf.org/rfc/rfc8035.txt) Protocolo de Descrição da Sessão (SDP) Esclarecimentos de oferta/resposta para multiplexing RTP/RTCP</span><span class="sxs-lookup"><span data-stu-id="d3ff2-132">[RFC 8035](https://www.ietf.org/rfc/rfc8035.txt) Session Description Protocol (SDP) Offer/Answer Clarifications for RTP/RTCP Multiplexing</span></span>

### <a name="standards-applicable-to-devices-that-support-media-bypass-mode"></a><span data-ttu-id="d3ff2-133">Padrões aplicáveis a dispositivos que suportam o modo de desvio de mídia</span><span class="sxs-lookup"><span data-stu-id="d3ff2-133">Standards applicable to devices that support media bypass mode</span></span>

<span data-ttu-id="d3ff2-134">Além das normas listadas como aplicáveis ao modo não-bypass, os seguintes padrões são usados para o modo de desvio de mídia:</span><span class="sxs-lookup"><span data-stu-id="d3ff2-134">In addition to the standards listed as applicable to non-bypass mode, the following standards are used for media bypass mode:</span></span>

- <span data-ttu-id="d3ff2-135">[RFC 5245 Interactive Connectivity Establishment (ICE) para desvio de mídia](https://tools.ietf.org/html/rfc5245).</span><span class="sxs-lookup"><span data-stu-id="d3ff2-135">[RFC 5245 Interactive Connectivity Establishment (ICE) for media bypass](https://tools.ietf.org/html/rfc5245).</span></span>  <span data-ttu-id="d3ff2-136">O SBC deve apoiar o seguinte:</span><span class="sxs-lookup"><span data-stu-id="d3ff2-136">The SBC must support the following:</span></span>
  - <span data-ttu-id="d3ff2-137">ICE Lite - os clientes Teams são clientes ice completos</span><span class="sxs-lookup"><span data-stu-id="d3ff2-137">ICE Lite - the Teams clients are full ICE clients</span></span>
  - <span data-ttu-id="d3ff2-138">[Restarts ICE](https://tools.ietf.org/html/rfc5245#section-9.1.1.1).</span><span class="sxs-lookup"><span data-stu-id="d3ff2-138">[ICE Restarts](https://tools.ietf.org/html/rfc5245#section-9.1.1.1).</span></span> <span data-ttu-id="d3ff2-139">Veja mais sobre o caso de uso do ICE e exemplos no ICE Restart: Chamada de bypass de mídia transferida para um ponto final que não suporta desvio de mídia</span><span class="sxs-lookup"><span data-stu-id="d3ff2-139">See more on ICE restarts use case and examples in ICE Restart:  Media bypass call transferred to an endpoint which does not support media bypass</span></span>   
- <span data-ttu-id="d3ff2-140">[RFC RFC 5589 Session Initiation Protocol (SIP) Call Control – Transfer](https://tools.ietf.org/html/rfc5589).</span><span class="sxs-lookup"><span data-stu-id="d3ff2-140">[RFC RFC 5589 Session Initiation Protocol (SIP) Call Control – Transfer](https://tools.ietf.org/html/rfc5589).</span></span> 
- <span data-ttu-id="d3ff2-141">[RFC 3960 Early Media and Ringing Tone Generation in the Session Initiation Protocol (SIP)](https://tools.ietf.org/html/rfc3960), veja as seções 3.1, Forking e 3.2, Ringing Tone Generation</span><span class="sxs-lookup"><span data-stu-id="d3ff2-141">[RFC 3960 Early Media and Ringing Tone Generation in the Session Initiation Protocol (SIP)](https://tools.ietf.org/html/rfc3960), see sections 3.1, Forking, and 3.2, Ringing Tone Generation</span></span> 
- [<span data-ttu-id="d3ff2-142">RFC 5389 Session Traversal Utilities for NAT (STUN)</span><span class="sxs-lookup"><span data-stu-id="d3ff2-142">RFC 5389 Session Traversal Utilities for NAT (STUN)</span></span>](https://tools.ietf.org/html/rfc5389)
- [<span data-ttu-id="d3ff2-143">RFC 5766 Travessia Usando Relés em torno de NAT (TURN): Extensões de relé para utilitários transversais de sessão para NAT (STUN)</span><span class="sxs-lookup"><span data-stu-id="d3ff2-143">RFC 5766 Traversal Using Relays around NAT (TURN): Relay Extensions to Session Traversal Utilities for NAT (STUN)</span></span>](https://tools.ietf.org/html/rfc5766)

### <a name="standards-applicable-to-support-conveying-location-information-to-e911-providers"></a><span data-ttu-id="d3ff2-144">Padrões aplicáveis ao suporte de transporte de informações de localização aos provedores E911</span><span class="sxs-lookup"><span data-stu-id="d3ff2-144">Standards applicable to support conveying location information to E911 providers</span></span>

- [<span data-ttu-id="d3ff2-145">RFC 6442, Transporte de localização para o Protocolo de Iniciação da Sessão</span><span class="sxs-lookup"><span data-stu-id="d3ff2-145">RFC 6442, Location Conveyance for the Session Initiation Protocol</span></span>](https://tools.ietf.org/html/rfc6442)

### <a name="deviations-from-the-rfcs"></a><span data-ttu-id="d3ff2-146">Desvios dos RFC's</span><span class="sxs-lookup"><span data-stu-id="d3ff2-146">Deviations from the RFC's</span></span>

<span data-ttu-id="d3ff2-147">A tabela a seguir lista as seções dos RFC(s) em que a implementação da microsoft do SIP ou pilha de mídia se desvia do padrão:</span><span class="sxs-lookup"><span data-stu-id="d3ff2-147">The following table lists the sections of the RFC(s) in which Microsoft's implementation of the SIP or media stack deviates from the standard:</span></span>

| <span data-ttu-id="d3ff2-148">RFC e seções</span><span class="sxs-lookup"><span data-stu-id="d3ff2-148">RFC and sections</span></span> | <span data-ttu-id="d3ff2-149">Descrição</span><span class="sxs-lookup"><span data-stu-id="d3ff2-149">Description</span></span> | <span data-ttu-id="d3ff2-150">desvio</span><span class="sxs-lookup"><span data-stu-id="d3ff2-150">Deviation</span></span> |
| :---------------------  |:---------------------- |:-----------------------|
| [<span data-ttu-id="d3ff2-151">RFC 6337, seção 5.3 Hold e Currículo de Mídia</span><span class="sxs-lookup"><span data-stu-id="d3ff2-151">RFC 6337, section 5.3 Hold and Resume of Media</span></span>](https://tools.ietf.org/html/rfc6337#section-5.3) | <span data-ttu-id="d3ff2-152">O RFC permite usar "a=inativo", "a=sendonly", a=recvonly" para colocar uma chamada em espera.</span><span class="sxs-lookup"><span data-stu-id="d3ff2-152">RFC allows using “a=inactive”, “a=sendonly”, a=recvonly” to place a call on hold.</span></span> |<span data-ttu-id="d3ff2-153">O proxy SIP só suporta "a=inativo" e não entende se o SBC envia "a=sendonly" ou "a=recvonly".</span><span class="sxs-lookup"><span data-stu-id="d3ff2-153">The SIP proxy only supports “a=inactive” and does not understand if the SBC sends “a=sendonly” or “a=recvonly”.</span></span>
| [<span data-ttu-id="d3ff2-154">RFC 6337, seção 5.4 "Comportamento sobre recebimento de SDP com c=0.0.0.0</span><span class="sxs-lookup"><span data-stu-id="d3ff2-154">RFC 6337, section 5.4 “Behavior on Receiving SDP with c=0.0.0.0</span></span>](https://tools.ietf.org/html/rfc6337#section-5.4) | <span data-ttu-id="d3ff2-155">[RFC3264](https://tools.ietf.org/html/rfc3264) requer que um agente seja capaz de receber SDP com um endereço de conexão de 0.0.0.0, nesse caso significa que nem o RTP nem o RTCP devem ser enviados para o peer.</span><span class="sxs-lookup"><span data-stu-id="d3ff2-155">[RFC3264](https://tools.ietf.org/html/rfc3264) requires that an agent is capable of receiving SDP with a connection address of 0.0.0.0, in which case it means that neither  RTP nor RTCP should be sent to the peer.</span></span> | <span data-ttu-id="d3ff2-156">O proxy SIP não suporta essa opção.</span><span class="sxs-lookup"><span data-stu-id="d3ff2-156">The SIP proxy does not support this option.</span></span> |

## <a name="operational-modes"></a><span data-ttu-id="d3ff2-157">Modos operacionais</span><span class="sxs-lookup"><span data-stu-id="d3ff2-157">Operational modes</span></span>

<span data-ttu-id="d3ff2-158">Existem dois modos operacionais para roteamento direto:</span><span class="sxs-lookup"><span data-stu-id="d3ff2-158">There are two operational modes for Direct Routing:</span></span>

- <span data-ttu-id="d3ff2-159">**Sem desvio de mídia** em que todo o tráfego RTP flui entre o cliente Teams, os processadores de mídia e o SBC.</span><span class="sxs-lookup"><span data-stu-id="d3ff2-159">**Without media bypass** in which all RTP traffic flows between the Teams client, the media processors, and the SBC.</span></span>  

- <span data-ttu-id="d3ff2-160">**Com o desvio de mídia** em que todas as mídias RTP fluem entre os Teams pontos finais e o SBC.</span><span class="sxs-lookup"><span data-stu-id="d3ff2-160">**With media bypass** in which all RTP media flows between the Teams endpoints and the SBC.</span></span> 

<span data-ttu-id="d3ff2-161">Observe que o tráfego SIP sempre flui através do proxy SIP.</span><span class="sxs-lookup"><span data-stu-id="d3ff2-161">Note that SIP traffic always flows via the SIP proxy.</span></span> 

## <a name="dtmf"></a><span data-ttu-id="d3ff2-162">Dtmf</span><span class="sxs-lookup"><span data-stu-id="d3ff2-162">DTMF</span></span>
<span data-ttu-id="d3ff2-163">O DTMF na banda não é suportado pela pilha de mídia.</span><span class="sxs-lookup"><span data-stu-id="d3ff2-163">In-band DTMF is not supported by media stack.</span></span>
