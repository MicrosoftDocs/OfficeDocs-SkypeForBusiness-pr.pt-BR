---
title: Roteamento Direto do Sistema de Telefonia
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 01/28/2019
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- Teams_ITAdmin_Help
- M365-voice
ms.reviewer: nmurav
search.appverid: MET150
description: Protocolos de roteamento direto
appliesto:
- Microsoft Teams
ms.openlocfilehash: 08b022799b2c8bf80ee30cbb0a5ef3e74f0a29e1
ms.sourcegitcommit: 89106cfda0d900d8be541943b7d1537bc69ed57f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/16/2019
ms.locfileid: "40065661"
---
# <a name="overview"></a><span data-ttu-id="b653a-103">Visão geral</span><span class="sxs-lookup"><span data-stu-id="b653a-103">Overview</span></span>

<span data-ttu-id="b653a-104">Este artigo descreve como o roteamento direto oferece suporte a bypass de mídia com um controlador de borda de sessão (SBC) habilitado para ICE Lite, conforme descrito em [RFC 5245](https://tools.ietf.org/html/rfc5245).</span><span class="sxs-lookup"><span data-stu-id="b653a-104">This article describes how Direct Routing supports media bypass with a Session Border Controller (SBC) enabled for ICE Lite as described in [RFC 5245](https://tools.ietf.org/html/rfc5245).</span></span> <span data-ttu-id="b653a-105">Este artigo destina-se a administradores de voz responsáveis por configurar a conexão entre o SBC local e o serviço de proxy SIP.</span><span class="sxs-lookup"><span data-stu-id="b653a-105">This article is intended for voice administrators who are responsible for configuring the connection between the on-premises SBC and the SIP proxy service.</span></span>

<span data-ttu-id="b653a-106">Este artigo fornece uma visão geral dos cenários e requisitos do ICE Lite para interoperabilidade.</span><span class="sxs-lookup"><span data-stu-id="b653a-106">This article provides an overview of the ICE Lite scenarios and requirements for interoperability.</span></span> <span data-ttu-id="b653a-107">O artigo descreve os formatos de mensagem e as transições de máquina de estado necessárias para garantir um fluxo de chamadas e mídias confiáveis.</span><span class="sxs-lookup"><span data-stu-id="b653a-107">The article describes the message formats and the required state machine transitions for ensuring reliable call and media flow.</span></span>

## <a name="terminology"></a><span data-ttu-id="b653a-108">Terminologia</span><span class="sxs-lookup"><span data-stu-id="b653a-108">Terminology</span></span>

- <span data-ttu-id="b653a-109">Primeira saudação – as primeiras palavras faladas pelo chamador e pelo chamado.</span><span class="sxs-lookup"><span data-stu-id="b653a-109">First Hello – The first words spoken by the caller and callee.</span></span> <span data-ttu-id="b653a-110">É importante que todos os esforços sejam feitos para garantir que os primeiros pacotes dos pontos de extremidade sejam entregues de forma confiável para a maioria dos casos de uso.</span><span class="sxs-lookup"><span data-stu-id="b653a-110">It is important that all efforts are made to ensure that the first packets from the endpoints are delivered reliably for most use cases.</span></span>

- <span data-ttu-id="b653a-111">Forking – a oferta do chamador pode ser entregue a vários pontos de extremidade do chamado se o receptor estiver disponível em vários dispositivos (por exemplo, um usuário do teams pode estar conectado ao Teams para Windows e Teams para Android ou iPhone).</span><span class="sxs-lookup"><span data-stu-id="b653a-111">Forking – The offer from the caller might be delivered to multiple callee endpoints if the callee is available on multiple devices (for example, a Teams user might be signed into Teams for Windows and Teams for Android or iPhone).</span></span>

- <span data-ttu-id="b653a-112">Atendimento provisório (183) – os pontos de extremidade do chamador para uma configuração de chamada mais rápida envie uma resposta com os candidatos e as chaves necessárias para estabelecer o fluxo de mídia.</span><span class="sxs-lookup"><span data-stu-id="b653a-112">Provisional Answer (183) – The callee endpoints for faster call setup send an answer with the candidates and keys required to establish media flow.</span></span> <span data-ttu-id="b653a-113">Isso é feito de previsão do usuário que pode atender a chamada (200OK) dessa instância específica do chamador.</span><span class="sxs-lookup"><span data-stu-id="b653a-113">This is done in anticipation of the user potentially answering the call(200OK) from that specific callee instance.</span></span> <span data-ttu-id="b653a-114">Com a bifurcação, o chamador deve estar pronto para receber várias respostas de provisórios.</span><span class="sxs-lookup"><span data-stu-id="b653a-114">With forking, the caller should be ready to receive multiple provisional answers.</span></span>

- <span data-ttu-id="b653a-115">Convidar novamente – oferta com candidatos finais selecionados pelo ponto de extremidade de controle do ICE.</span><span class="sxs-lookup"><span data-stu-id="b653a-115">Re-Invite – Offer with final candidates selected by the ICE controlling endpoint.</span></span> <span data-ttu-id="b653a-116">Isso terá o atributo a = candidato remoto para resolver qualquer condição de corrida da manipulação de várias bifurcações.</span><span class="sxs-lookup"><span data-stu-id="b653a-116">This will have the a=remote-candidate attribute to resolve any race conditions from handling multiple forks.</span></span>

- <span data-ttu-id="b653a-117">Ponto de extremidade do teams – pode ser um servidor (processador de mídia, retransmissão de transporte) ou o cliente do teams.</span><span class="sxs-lookup"><span data-stu-id="b653a-117">Teams Endpoint – This could either be a server (Media Processor, Transport Relay) or the Teams client.</span></span>

## <a name="message-format"></a><span data-ttu-id="b653a-118">Formato da mensagem</span><span class="sxs-lookup"><span data-stu-id="b653a-118">Message format</span></span>

<span data-ttu-id="b653a-119">A infraestrutura de equipe segue a RFC 5245 para ICE-Lite.</span><span class="sxs-lookup"><span data-stu-id="b653a-119">The Teams infrastructure follows RFC 5245 for ICE-Lite.</span></span> <span data-ttu-id="b653a-120">Isso significa que todas as mensagens STUN serão compatíveis com [RFC 5389](https://tools.ietf.org/html/rfc5389).</span><span class="sxs-lookup"><span data-stu-id="b653a-120">This implies that all the STUN messages will be compliant with [RFC 5389](https://tools.ietf.org/html/rfc5389).</span></span>

<span data-ttu-id="b653a-121">O SBCs conforme exigido pela RFC 5389 deve ignorar qualquer atributo STUN que ele não reconhece, e continuar a processar as mensagens com os atributos conhecidos.</span><span class="sxs-lookup"><span data-stu-id="b653a-121">The SBCs as required by RFC 5389 must ignore any STUN attributes that they do not recognize, and continue to process the messages with the known attributes.</span></span> 

<span data-ttu-id="b653a-122">Se forem recebidos pacotes malformados, os pacotes deverão ser descartados sem afetar o estabelecimento da sessão de mídia.</span><span class="sxs-lookup"><span data-stu-id="b653a-122">If any malformed packets are received, the packets must be discarded without impacting the media session establishment.</span></span>

## <a name="ice-lite-requirements"></a><span data-ttu-id="b653a-123">Requisitos do ICE Lite</span><span class="sxs-lookup"><span data-stu-id="b653a-123">ICE Lite requirements</span></span>

<span data-ttu-id="b653a-124">Esta seção captura brevemente os requisitos do ICE Lite.</span><span class="sxs-lookup"><span data-stu-id="b653a-124">This section briefly captures the requirements for ICE Lite.</span></span>

### <a name="candidate-gathering"></a><span data-ttu-id="b653a-125">Reunião de candidatos</span><span class="sxs-lookup"><span data-stu-id="b653a-125">Candidate gathering</span></span>

<span data-ttu-id="b653a-126">O SBC deve oferecer apenas um candidato que seja alcançável publicamente.</span><span class="sxs-lookup"><span data-stu-id="b653a-126">The SBC must offer only one candidate that is publicly reachable.</span></span> <span data-ttu-id="b653a-127">No momento, somente há suporte para os candidatos IPV4.</span><span class="sxs-lookup"><span data-stu-id="b653a-127">Currently, only IPV4 candidates are supported.</span></span>


#### <a name="connectivity-checks"></a><span data-ttu-id="b653a-128">Verificações de conectividade</span><span class="sxs-lookup"><span data-stu-id="b653a-128">Connectivity checks</span></span>

<span data-ttu-id="b653a-129">A implementação do ICE Lite deve responder a todas as verificações de conectividade recebidas.</span><span class="sxs-lookup"><span data-stu-id="b653a-129">The ICE Lite implementation must respond to any connectivity checks received.</span></span> <span data-ttu-id="b653a-130">O ponto de extremidade Lite ICE não deve enviar nenhuma solicitação de verificação de conectividade.</span><span class="sxs-lookup"><span data-stu-id="b653a-130">The ICE Lite endpoint must not send any connectivity check requests.</span></span> <span data-ttu-id="b653a-131">(Se verificações de conectividade forem enviadas em violação, a implementação completa responderá, o que pode resultar na descoberta de candidatos derivados de pares inesperados e resultar em falhas de chamadas.)</span><span class="sxs-lookup"><span data-stu-id="b653a-131">(If connectivity checks are sent in violation, the full implementation will respond, which can result in unexpected peer-derived candidates being discovered and potentially result in call failures.)</span></span>

#### <a name="nominations"></a><span data-ttu-id="b653a-132">Indicações</span><span class="sxs-lookup"><span data-stu-id="b653a-132">Nominations</span></span>

<span data-ttu-id="b653a-133">O ponto de extremidade de implementação completa do ICE será sempre o ponto de extremidade de controle e seguirá indicações "regulares" para a seleção dos candidatos finais a serem usados para o fluxo de mídia.</span><span class="sxs-lookup"><span data-stu-id="b653a-133">The ICE full implementation endpoint will always be the Controlling endpoint, and will follow “Regular” nominations for selecting the final candidates to be used for media flow.</span></span> <span data-ttu-id="b653a-134">O ponto de extremidade Lite ICE pode usar as indicações para concluir o caminho a ser usado para a mídia e para o estabelecimento da chamada completa.</span><span class="sxs-lookup"><span data-stu-id="b653a-134">The ICE Lite endpoint can use the nominations to conclude the path to be used for media and complete call establishment.</span></span>

<span data-ttu-id="b653a-135">Observação: no caso de bifurcação com pontos de extremidade de ponto de extremidade que enviam respostas do 183, o SBC deve estar pronto para responder a cheques de vários pontos de extremidade e também indicações de vários pontos de extremidade se as indicações acontecerem antes de 200OK.</span><span class="sxs-lookup"><span data-stu-id="b653a-135">Note: In the case of forking with peer endpoints sending 183 provisional answers, the SBC must be ready to respond to checks from multiple endpoints and also nominations from multiple endpoints if the nominations happen before 200OK.</span></span> <span data-ttu-id="b653a-136">Dependendo da convergência da máquina de estado do ICE no caminho final e na temporização da resposta do usuário, as indicações podem acontecer antes ou depois de 200OK.</span><span class="sxs-lookup"><span data-stu-id="b653a-136">Depending on the convergence of the ICE state machine on the final path and timing of the user answering, the nominations can happen before or after 200OK.</span></span> <span data-ttu-id="b653a-137">O SBC deve ser capaz de manipular os dois casos.</span><span class="sxs-lookup"><span data-stu-id="b653a-137">The SBC must be able to handle both cases.</span></span>

#### <a name="converging-for-forking"></a><span data-ttu-id="b653a-138">Convergente para bifurcação</span><span class="sxs-lookup"><span data-stu-id="b653a-138">Converging for forking</span></span>

<span data-ttu-id="b653a-139">Se a oferta das bifurcações SBC para vários pontos de extremidade de equipes, os pontos de extremidade das equipes podem responder com uma resposta provisório e iniciar verificações de conectividade.</span><span class="sxs-lookup"><span data-stu-id="b653a-139">If the offer from the SBC forks to multiple Teams endpoints, the Teams endpoints may respond with a provisional answer and start connectivity checks.</span></span> <span data-ttu-id="b653a-140">O SBC deve estar preparado para receber verificações de conectividade e responder às verificações de conectividade de vários pontos de extremidade do ponto.</span><span class="sxs-lookup"><span data-stu-id="b653a-140">The SBC must be prepared to receive connectivity checks and respond to connectivity checks from multiple peer endpoints.</span></span> <span data-ttu-id="b653a-141">Por exemplo, o usuário do teams pode estar conectado a uma área de trabalho e a um telefone celular.</span><span class="sxs-lookup"><span data-stu-id="b653a-141">For example, the Teams user could be signed on to both a desktop and a cell phone.</span></span> <span data-ttu-id="b653a-142">Os dois dispositivos serão notificados sobre a chamada de entrada e tentarão verificações de conectividade com o SBC.</span><span class="sxs-lookup"><span data-stu-id="b653a-142">Both devices will be notified of the inbound call and will attempt connectivity checks with the SBC.</span></span>

<span data-ttu-id="b653a-143">Eventualmente, apenas um dos pontos de extremidade atenderá à chamada (200OK).</span><span class="sxs-lookup"><span data-stu-id="b653a-143">Eventually only one of the endpoints will answer the call (200OK).</span></span> <span data-ttu-id="b653a-144">Ao receber o 200OK, o SBC pode configurar o contexto correto para processar os pacotes de mídia.</span><span class="sxs-lookup"><span data-stu-id="b653a-144">On receiving the 200OK, the SBC can set up the right context for processing the media packets.</span></span>

## <a name="scenarios"></a><span data-ttu-id="b653a-145">Cenários</span><span class="sxs-lookup"><span data-stu-id="b653a-145">Scenarios</span></span>

###  <a name="inbound-call-from-sbc"></a><span data-ttu-id="b653a-146">Chamada de entrada do SBC</span><span class="sxs-lookup"><span data-stu-id="b653a-146">Inbound call from SBC</span></span>

<span data-ttu-id="b653a-147">Para esse cenário, há vários pontos de extremidade de pares possíveis que o SBC deve manipular:</span><span class="sxs-lookup"><span data-stu-id="b653a-147">For this scenario, there are several possible peer endpoints that the SBC must handle:</span></span>

- <span data-ttu-id="b653a-148">Os pontos de extremidade do servidor geralmente respondem diretamente com o 200OK.</span><span class="sxs-lookup"><span data-stu-id="b653a-148">Server endpoints will typically respond directly with 200OK.</span></span> <span data-ttu-id="b653a-149">Estes são pontos de extremidade de ICE completos que são tipicamente envolvidos no correio de voz, na fila de chamadas e nos cenários de atendedor automático.</span><span class="sxs-lookup"><span data-stu-id="b653a-149">These are full ICE endpoints that are typically involved in Voicemail, Call queue, and Auto attendant scenarios.</span></span>

- <span data-ttu-id="b653a-150">Os pontos de extremidade do cliente podem enviar várias respostas de provisório com diferentes marcas de/para (183) seguidas por uma 200OK da empresa que atende a chamada.</span><span class="sxs-lookup"><span data-stu-id="b653a-150">Client endpoints can send multiple provisional answers with different From/To tags (183) followed by a 200OK from the endpoint that answers the call.</span></span> <span data-ttu-id="b653a-151">Esses pontos de extremidade de ICE completos geralmente representam clientes de usuários finais.</span><span class="sxs-lookup"><span data-stu-id="b653a-151">These are full ICE endpoints typically representing end user clients.</span></span>

- <span data-ttu-id="b653a-152">Outros pontos de extremidade de SBC.</span><span class="sxs-lookup"><span data-stu-id="b653a-152">Other SBC endpoints.</span></span> <span data-ttu-id="b653a-153">Estes são pontos de extremidade do ICE Lite geralmente envolvidos no cenário de tocar simultaneamente pontos de extremidade do cliente e outro número de telefone.</span><span class="sxs-lookup"><span data-stu-id="b653a-153">These are ICE Lite endpoints typically involved in the scenario of simultaneously ringing client endpoints and another phone number(s).</span></span>

<span data-ttu-id="b653a-154">O SBC deve responder a todas as solicitações de verificação de conectividade válidas recebidas dos pontos de extremidade do ICE completo.</span><span class="sxs-lookup"><span data-stu-id="b653a-154">The SBC must respond to all valid connectivity check requests received from the full ICE endpoints.</span></span> <span data-ttu-id="b653a-155">Por RFC, os pontos de extremidade de ICE completos ficarão controlando pontos de extremidade.</span><span class="sxs-lookup"><span data-stu-id="b653a-155">Per RFC, the full ICE endpoints will become Controlling endpoints.</span></span> <span data-ttu-id="b653a-156">Os pontos de extremidade do Teams (cliente/servidor) executarão as indicações "regular" para concluir as verificações de conectividade.</span><span class="sxs-lookup"><span data-stu-id="b653a-156">The Teams (client/server) endpoints will perform “Regular” nominations to complete connectivity checks.</span></span> <span data-ttu-id="b653a-157">A 200Ok final pode ser de um ponto de extremidade que enviava uma mídia antecipada ou de um ponto de extremidade diferente.</span><span class="sxs-lookup"><span data-stu-id="b653a-157">The final 200Ok can either be from an endpoint that sent early media or from a different endpoint.</span></span> <span data-ttu-id="b653a-158">Ao receber o 200Ok, o SBC deve configurar o contexto correto para o fluxo de mídia.</span><span class="sxs-lookup"><span data-stu-id="b653a-158">On receiving the 200Ok, the SBC must set up the right context for media flow.</span></span> 

###  <a name="early-media"></a><span data-ttu-id="b653a-159">Mídia inicial</span><span class="sxs-lookup"><span data-stu-id="b653a-159">Early media</span></span>

<span data-ttu-id="b653a-160">Se houver um fluxo de mídia inicial, o SBC deve travar no primeiro ponto de extremidade que inicia a mídia de streaming; o fluxo de mídia pode começar antes de os candidatos serem nomeados.</span><span class="sxs-lookup"><span data-stu-id="b653a-160">If there is early media flow, the SBC must latch to the first endpoint that starts streaming media; media flow can start before candidates are nominated.</span></span> <span data-ttu-id="b653a-161">O SBC deve ter suporte para o envio de DTMF durante essa fase para habilitar cenários de IVR/correio de voz.</span><span class="sxs-lookup"><span data-stu-id="b653a-161">The SBC should have support for sending DTMF during this phase to enable IVR/voicemail scenarios.</span></span> <span data-ttu-id="b653a-162">O SBC deve usar o caminho de prioridade mais alta no qual ele recebeu cheques se as indicações não tiverem sido concluídas.</span><span class="sxs-lookup"><span data-stu-id="b653a-162">The SBC should use the highest priority path on which it has received checks if nominations have not completed.</span></span>

### <a name="outbound-call-to-sbc"></a><span data-ttu-id="b653a-163">Chamada de saída para SBC</span><span class="sxs-lookup"><span data-stu-id="b653a-163">Outbound call to SBC</span></span>

<span data-ttu-id="b653a-164">Os pontos de extremidade do teams são o chamador para esse cenário e será o ponto de extremidade de controle.</span><span class="sxs-lookup"><span data-stu-id="b653a-164">The Teams endpoints are the Caller for this scenario and will be the Controlling Endpoint.</span></span> <span data-ttu-id="b653a-165">Ao receber uma resposta de provisório (183) ou uma resposta final (200OK), o ponto de extremidade do teams começará a verificar a conectividade e passará para as indicações "regular" para concluir as verificações de conectividade.</span><span class="sxs-lookup"><span data-stu-id="b653a-165">On receiving either a provisional answer (183) or a final answer(200OK), the Teams endpoint  will start connectivity checks and proceed to “Regular” nominations to complete the connectivity checks.</span></span>

<span data-ttu-id="b653a-166">Observação: se o SBC enviar uma resposta de provisório (183), o SBC deve estar pronto para receber solicitações de verificação de conectividade e possivelmente concluir as indicações antes de o 200OK ser enviado pelo SBC.</span><span class="sxs-lookup"><span data-stu-id="b653a-166">Note: If the SBC sends a provisional answer (183), the SBC must be ready to receive connectivity check requests and potentially complete the nominations  before the 200OK is sent by the SBC.</span></span> <span data-ttu-id="b653a-167">Se verificações e/ou indicações forem concluídas antes de o 200OK ser recebido, as verificações e/ou indicações não serão executadas novamente depois que 200OK for recebido.</span><span class="sxs-lookup"><span data-stu-id="b653a-167">If checks and/or nominations are completed before the 200OK is received, checks and/or nominations will not be performed again after 200OK is received.</span></span> <span data-ttu-id="b653a-168">O SBC não deve alterar os candidatos do ICE, a senha e o ufrag (nome de usuário do fragmento) entre 183 e 200.</span><span class="sxs-lookup"><span data-stu-id="b653a-168">The SBC must not change ICE candidates, password, and ufrag (username fragment) between 183 and 200.</span></span>

<span data-ttu-id="b653a-169">Para dar suporte à mídia inicial, o SBC pode começar a transmitir a mídia para o candidato do ICE de par, com a prioridade mais alta com base nas verificações de conectividade recebidas, mesmo antes de as indicações serem concluídas pelo ponto de extremidade do teams.</span><span class="sxs-lookup"><span data-stu-id="b653a-169">To support early media, the SBC may start streaming the media to the peer ICE candidate, with the highest priority based on received connectivity checks, even before nominations are completed by Teams endpoint.</span></span> <span data-ttu-id="b653a-170">O SBC deve esperar mídia do teams em qualquer candidato até que as indicações sejam concluídas.</span><span class="sxs-lookup"><span data-stu-id="b653a-170">The SBC should expect media from Teams on any candidate until nominations are completed.</span></span> <span data-ttu-id="b653a-171">Depois que um candidato é indicado, o SBC deve redefinir para o contexto correto para enviar e receber pacotes de mídia.</span><span class="sxs-lookup"><span data-stu-id="b653a-171">Once a candidate is nominated, the SBC must reset to the right context to send and receive media packets.</span></span>

## <a name="srtp-support-requirements"></a><span data-ttu-id="b653a-172">Requisitos de suporte do SRTP</span><span class="sxs-lookup"><span data-stu-id="b653a-172">SRTP support requirements</span></span>

<span data-ttu-id="b653a-173">O SBC deve suportar a codificação de criptografia do SRTP AES_CM_128_HMAC_SHA1_80 para oferta e resposta no seguinte formato:</span><span class="sxs-lookup"><span data-stu-id="b653a-173">The SBC must support SRTP encryption cipher AES_CM_128_HMAC_SHA1_80 for offer and answer in the following format:</span></span>

```
"inline:" <key||salt> ["|" lifetime]
```

<span data-ttu-id="b653a-174">Veja a seguir um exemplo do atributo crypto na oferta SDP do SBC:</span><span class="sxs-lookup"><span data-stu-id="b653a-174">The following is an example of the crypto attribute in the SDP offer from the SBC:</span></span>

```
a=crypto:1 AES_CM_128_HMAC_SHA1_80 inline:V/Lr6Lsvhad/crSB9kCQ28jrYDxR2Yfk5bXryH5V|2^31
```

<span data-ttu-id="b653a-175">Os parâmetros MKI e length não são necessários.</span><span class="sxs-lookup"><span data-stu-id="b653a-175">MKI and Length parameters are not required.</span></span>

<span data-ttu-id="b653a-176">Para obter mais informações, consulte [RFC 4568, seção 6,1](https://tools.ietf.org/html/rfc4568#section-6.1).</span><span class="sxs-lookup"><span data-stu-id="b653a-176">For more information, see [RFC 4568, section 6.1](https://tools.ietf.org/html/rfc4568#section-6.1).</span></span>

## <a name="sdes-support-requirements"></a><span data-ttu-id="b653a-177">Requisitos de suporte do SDES</span><span class="sxs-lookup"><span data-stu-id="b653a-177">SDES support requirements</span></span>

<span data-ttu-id="b653a-178">O dispositivo deve ser capaz de oferecer SDES no formato conforme descrito abaixo.</span><span class="sxs-lookup"><span data-stu-id="b653a-178">The device must be able to offer SDES in the format as described below.</span></span> <span data-ttu-id="b653a-179">Os processadores de mídia da Microsoft sempre preferem SDES.</span><span class="sxs-lookup"><span data-stu-id="b653a-179">Microsoft Media Processors always prefer SDES.</span></span>

- <span data-ttu-id="b653a-180">Com o bypass não relacionado à mídia, mesmo se um cliente só oferecer suporte a DTLS, os processadores de mídia serão convertidos em SDES.</span><span class="sxs-lookup"><span data-stu-id="b653a-180">With non-media bypass, even if a client only supports DTLS, the Media Processors will convert to SDES.</span></span>

- <span data-ttu-id="b653a-181">Com o bypass de mídia, se um cliente só for DTLS (estado futuro do Google Chrome), o roteamento direto inserirá um MP no caminho, convertendo a chamada de bypass de mídia para bypass de não mídia.</span><span class="sxs-lookup"><span data-stu-id="b653a-181">With media bypass, if a client is DTLS only (future Google Chrome state), Direct Routing will insert an MP in the path, converting the call from media bypass to non-media bypass.</span></span> <span data-ttu-id="b653a-182">Entre o componente do processador de SBC e de mídia do roteamento direto, SDES é sempre usado.</span><span class="sxs-lookup"><span data-stu-id="b653a-182">Between the SBC and media processor component of Direct Routing, SDES is always used.</span></span>

<span data-ttu-id="b653a-183">Atualmente, não há nenhum cliente de equipes que ofereça apenas DTLS; no entanto, o Google anunciou que, em algum momento, ele pare de oferecer suporte a SDES.</span><span class="sxs-lookup"><span data-stu-id="b653a-183">Currently, there are no Teams client that offer only DTLS; however Google has announced that at some point in time they will stop supporting SDES.</span></span>

## <a name="format-for-offer-from-sbc-in-bypass-mode"></a><span data-ttu-id="b653a-184">Formato de oferta do SBC no modo ignorar</span><span class="sxs-lookup"><span data-stu-id="b653a-184">Format for offer from SBC in bypass mode</span></span> 

<span data-ttu-id="b653a-185">A oferta deve conter SDES e pode conter DTLS opcional no seguinte formato:</span><span class="sxs-lookup"><span data-stu-id="b653a-185">Offer must contain SDES and can contain DTLS optional in the following format:</span></span>

```
m=audio 54056 UDP/TLS/RTP/SAVP 0 8 76 77 18 9 101 13
a=rtcp:54056
a=crypto:1 AES_CM_128_HMAC_SHA1_80 inline:krXco0QRglwErMqtbMs2zSw29tBdmdgXpEYZhQmp|2^31
a=fingerprint:sha-256 AE:24:07:15:5C:B7:45:1A:E4:45:60:C1:1E:68:0E:CC:8D:A6:78:3B:76:65:BB:B0:77:88:07:F8:98:18:62:34
a=setup:actpass
a=rtcp-mux
```

### <a name="format-for-answer-containing-sdes-to-sbc"></a><span data-ttu-id="b653a-186">Formatar para resposta que contém SDES para SBC</span><span class="sxs-lookup"><span data-stu-id="b653a-186">Format for answer containing SDES to SBC</span></span>

```
m=audio 54056 RTP/SAVP 111 103 104 9 0 8 description 106 13 110 112 113 126
a=rtcp:54056
a=crypto:2 AES_CM_128_HMAC_SHA1_80 inline:fBc61ikv1kMy0sF85DblNqTzVAbFa7hJQ9GKb6Yj|2^31|1:1
a=crypto:3 AES_CM_128_HMAC_SHA1_80 inline:O1qT9tWbs/NwJVwhfrgF5tCrbNOxnVDqkIqTx4rz|2^31
a=rtcp-mux

```

## <a name="format-for-offer-from-teams-to-sbc"></a><span data-ttu-id="b653a-187">Formato da oferta de Teams para SBC</span><span class="sxs-lookup"><span data-stu-id="b653a-187">Format for offer from Teams to SBC</span></span> 

### <a name="format-for-sdes-only-offer-to-sbc"></a><span data-ttu-id="b653a-188">Format for SDES somente oferta para SBC</span><span class="sxs-lookup"><span data-stu-id="b653a-188">Format for SDES only offer to SBC</span></span>

```
m=audio 52884 RTP/SAVP 111 103 104 9 0 8 106 13 110 112 113 126
a=crypto:0 AES_CM_128_HMAC_SHA1_32 inline:Hr4D2cgUu9+Uza5Igz/JkVx59DAxDbaxJg862ibQ|2^31
a=crypto:1 AES_CM_128_HMAC_SHA1_80 inline:JPEaIxHegfuv53ykBPZk8hV0GO8kTiiqRMfHimEE|2^31
a=rtcp:52884
a=rtcp-mux
```

