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
f1.keywords:
- NOCSH
description: Protocolos de Roteamento Direto
appliesto:
- Microsoft Teams
ms.openlocfilehash: 43673c2b6a1928ab2ca21579339324f01d5ada9e
ms.sourcegitcommit: 1a08ec9069332e19135312d35fc6a6c3247ce2d2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/11/2020
ms.locfileid: "41888570"
---
# <a name="overview"></a><span data-ttu-id="a9bda-103">Visão Geral</span><span class="sxs-lookup"><span data-stu-id="a9bda-103">Overview</span></span>

<span data-ttu-id="a9bda-104">Este artigo descreve como o Roteamento Direto dá suporte ao bypass de mídia com um Controlador de Borda de Sessão (SBC) habilitado para ICE Lite, conforme descrito em [RFC 5245](https://tools.ietf.org/html/rfc5245).</span><span class="sxs-lookup"><span data-stu-id="a9bda-104">This article describes how Direct Routing supports media bypass with a Session Border Controller (SBC) enabled for ICE Lite as described in [RFC 5245](https://tools.ietf.org/html/rfc5245).</span></span> <span data-ttu-id="a9bda-105">Este artigo destina-se aos administradores de voz responsáveis por configurar a conexão entre o SBC local e o serviço proxy SIP.</span><span class="sxs-lookup"><span data-stu-id="a9bda-105">This article is intended for voice administrators who are responsible for configuring the connection between the on-premises SBC and the SIP proxy service.</span></span>

<span data-ttu-id="a9bda-106">Este artigo fornece uma visão geral dos cenários e requisitos do ICE Lite para interoperabilidade.</span><span class="sxs-lookup"><span data-stu-id="a9bda-106">This article provides an overview of the ICE Lite scenarios and requirements for interoperability.</span></span> <span data-ttu-id="a9bda-107">O artigo descreve os formatos de mensagem e as transições de máquina de estado necessárias para garantir o fluxo confiável de chamada e mídia.</span><span class="sxs-lookup"><span data-stu-id="a9bda-107">The article describes the message formats and the required state machine transitions for ensuring reliable call and media flow.</span></span>

## <a name="terminology"></a><span data-ttu-id="a9bda-108">Terminologia</span><span class="sxs-lookup"><span data-stu-id="a9bda-108">Terminology</span></span>

- <span data-ttu-id="a9bda-109">Primeiro Hello – As primeiras palavras faladas pelo chamador e pelo chamador.</span><span class="sxs-lookup"><span data-stu-id="a9bda-109">First Hello – The first words spoken by the caller and callee.</span></span> <span data-ttu-id="a9bda-110">É importante que todos os esforços sejam feitos para garantir que os primeiros pacotes dos pontos de extremidade sejam entregues de forma confiável para a maioria dos casos de uso.</span><span class="sxs-lookup"><span data-stu-id="a9bda-110">It is important that all efforts are made to ensure that the first packets from the endpoints are delivered reliably for most use cases.</span></span>

- <span data-ttu-id="a9bda-111">Forking – A oferta do chamador pode ser entregue a vários pontos de extremidade do chamador se o chamador estiver disponível em vários dispositivos (por exemplo, um usuário do Teams pode ser conectado ao Teams para Windows e Teams para Android ou iPhone).</span><span class="sxs-lookup"><span data-stu-id="a9bda-111">Forking – The offer from the caller might be delivered to multiple callee endpoints if the callee is available on multiple devices (for example, a Teams user might be signed into Teams for Windows and Teams for Android or iPhone).</span></span>

- <span data-ttu-id="a9bda-112">Resposta Provisória (183) – Os pontos de extremidade do chamador para configuração de chamada mais rápida enviam uma resposta com os candidatos e as chaves necessárias para estabelecer o fluxo de mídia.</span><span class="sxs-lookup"><span data-stu-id="a9bda-112">Provisional Answer (183) – The callee endpoints for faster call setup send an answer with the candidates and keys required to establish media flow.</span></span> <span data-ttu-id="a9bda-113">Isso é feito em antecipação do usuário potencialmente respondendo a chamada(200OK) dessa instância de chamador específica.</span><span class="sxs-lookup"><span data-stu-id="a9bda-113">This is done in anticipation of the user potentially answering the call(200OK) from that specific callee instance.</span></span> <span data-ttu-id="a9bda-114">Com a forking, o chamador deve estar pronto para receber várias respostas provisórias.</span><span class="sxs-lookup"><span data-stu-id="a9bda-114">With forking, the caller should be ready to receive multiple provisional answers.</span></span>

- <span data-ttu-id="a9bda-115">Re-Invite – Oferta com os candidatos finais selecionados pelo ponto de extremidade de controle ICE.</span><span class="sxs-lookup"><span data-stu-id="a9bda-115">Re-Invite – Offer with final candidates selected by the ICE controlling endpoint.</span></span> <span data-ttu-id="a9bda-116">Isso terá o atributo a=remote-candidate para resolver qualquer condição de corrida de manipular vários bifurcações.</span><span class="sxs-lookup"><span data-stu-id="a9bda-116">This will have the a=remote-candidate attribute to resolve any race conditions from handling multiple forks.</span></span>

- <span data-ttu-id="a9bda-117">Teams Ponto de extremidade – Pode ser um servidor (Processador de Mídia, Retransmissão de Transporte) ou o Teams cliente.</span><span class="sxs-lookup"><span data-stu-id="a9bda-117">Teams Endpoint – This could either be a server (Media Processor, Transport Relay) or the Teams client.</span></span>

## <a name="message-format"></a><span data-ttu-id="a9bda-118">Formato de mensagem</span><span class="sxs-lookup"><span data-stu-id="a9bda-118">Message format</span></span>

<span data-ttu-id="a9bda-119">A Teams segue a RFC 5245 para ICE-Lite.</span><span class="sxs-lookup"><span data-stu-id="a9bda-119">The Teams infrastructure follows RFC 5245 for ICE-Lite.</span></span> <span data-ttu-id="a9bda-120">Isso implica que todas as mensagens STUN estarão em conformidade com [o RFC 5389](https://tools.ietf.org/html/rfc5389).</span><span class="sxs-lookup"><span data-stu-id="a9bda-120">This implies that all the STUN messages will be compliant with [RFC 5389](https://tools.ietf.org/html/rfc5389).</span></span>

<span data-ttu-id="a9bda-121">Os SBCs conforme exigido pela RFC 5389 devem ignorar todos os atributos do STUN que não reconhecem e continuar a processar as mensagens com os atributos conhecidos.</span><span class="sxs-lookup"><span data-stu-id="a9bda-121">The SBCs as required by RFC 5389 must ignore any STUN attributes that they do not recognize, and continue to process the messages with the known attributes.</span></span> 

<span data-ttu-id="a9bda-122">Se algum pacote malformado for recebido, os pacotes devem ser descartados sem afetar o estabelecimento da sessão de mídia.</span><span class="sxs-lookup"><span data-stu-id="a9bda-122">If any malformed packets are received, the packets must be discarded without impacting the media session establishment.</span></span>

## <a name="ice-lite-requirements"></a><span data-ttu-id="a9bda-123">Requisitos do ICE Lite</span><span class="sxs-lookup"><span data-stu-id="a9bda-123">ICE Lite requirements</span></span>

<span data-ttu-id="a9bda-124">Esta seção captura brevemente os requisitos do ICE Lite.</span><span class="sxs-lookup"><span data-stu-id="a9bda-124">This section briefly captures the requirements for ICE Lite.</span></span>

### <a name="candidate-gathering"></a><span data-ttu-id="a9bda-125">Reunião de candidatos</span><span class="sxs-lookup"><span data-stu-id="a9bda-125">Candidate gathering</span></span>

<span data-ttu-id="a9bda-126">O SBC deve oferecer apenas um candidato que seja publicamente acessível.</span><span class="sxs-lookup"><span data-stu-id="a9bda-126">The SBC must offer only one candidate that is publicly reachable.</span></span> <span data-ttu-id="a9bda-127">Atualmente, apenas os candidatos IPV4 são suportados.</span><span class="sxs-lookup"><span data-stu-id="a9bda-127">Currently, only IPV4 candidates are supported.</span></span>


#### <a name="connectivity-checks"></a><span data-ttu-id="a9bda-128">Verificações de conectividade</span><span class="sxs-lookup"><span data-stu-id="a9bda-128">Connectivity checks</span></span>

<span data-ttu-id="a9bda-129">A implementação do ICE Lite deve responder a todas as verificações de conectividade recebidas.</span><span class="sxs-lookup"><span data-stu-id="a9bda-129">The ICE Lite implementation must respond to any connectivity checks received.</span></span> <span data-ttu-id="a9bda-130">O ponto de extremidade ICE Lite não deve enviar solicitações de verificação de conectividade.</span><span class="sxs-lookup"><span data-stu-id="a9bda-130">The ICE Lite endpoint must not send any connectivity check requests.</span></span> <span data-ttu-id="a9bda-131">(Se as verificações de conectividade são enviadas em violação, a implementação completa responderá, o que pode resultar em candidatos inesperados derivados por pares sendo descobertos e potencialmente resultar em falhas de chamada.)</span><span class="sxs-lookup"><span data-stu-id="a9bda-131">(If connectivity checks are sent in violation, the full implementation will respond, which can result in unexpected peer-derived candidates being discovered and potentially result in call failures.)</span></span>

#### <a name="nominations"></a><span data-ttu-id="a9bda-132">Indicações</span><span class="sxs-lookup"><span data-stu-id="a9bda-132">Nominations</span></span>

<span data-ttu-id="a9bda-133">O ponto de extremidade de implementação total do ICE sempre será o ponto de extremidade De controle e seguirá as indicações "Regulares" para selecionar os candidatos finais a serem usados para o fluxo de mídia.</span><span class="sxs-lookup"><span data-stu-id="a9bda-133">The ICE full implementation endpoint will always be the Controlling endpoint, and will follow “Regular” nominations for selecting the final candidates to be used for media flow.</span></span> <span data-ttu-id="a9bda-134">O ponto de extremidade ICE Lite pode usar as nomeações para concluir o caminho a ser usado para mídia e concluir o estabelecimento de chamada.</span><span class="sxs-lookup"><span data-stu-id="a9bda-134">The ICE Lite endpoint can use the nominations to conclude the path to be used for media and complete call establishment.</span></span>

<span data-ttu-id="a9bda-135">Observação: no caso de forcar com pontos de extremidade pares enviando 183 respostas provisórias, o SBC deve estar pronto para responder a verificações de vários pontos de extremidade e também a nomeações de vários pontos de extremidade se as nomeações acontecerem antes de 200OK.</span><span class="sxs-lookup"><span data-stu-id="a9bda-135">Note: In the case of forking with peer endpoints sending 183 provisional answers, the SBC must be ready to respond to checks from multiple endpoints and also nominations from multiple endpoints if the nominations happen before 200OK.</span></span> <span data-ttu-id="a9bda-136">Dependendo da convergência da máquina de estado ICE no caminho final e no tempo da resposta do usuário, as nomeações podem acontecer antes ou depois de 200OK.</span><span class="sxs-lookup"><span data-stu-id="a9bda-136">Depending on the convergence of the ICE state machine on the final path and timing of the user answering, the nominations can happen before or after 200OK.</span></span> <span data-ttu-id="a9bda-137">O SBC deve ser capaz de lidar com ambos os casos.</span><span class="sxs-lookup"><span data-stu-id="a9bda-137">The SBC must be able to handle both cases.</span></span>

#### <a name="converging-for-forking"></a><span data-ttu-id="a9bda-138">Convergindo para a forcar</span><span class="sxs-lookup"><span data-stu-id="a9bda-138">Converging for forking</span></span>

<span data-ttu-id="a9bda-139">Se a oferta do SBC for bifurcada para vários pontos de extremidade Teams, os pontos de extremidade Teams podem responder com uma resposta provisória e iniciar verificações de conectividade.</span><span class="sxs-lookup"><span data-stu-id="a9bda-139">If the offer from the SBC forks to multiple Teams endpoints, the Teams endpoints may respond with a provisional answer and start connectivity checks.</span></span> <span data-ttu-id="a9bda-140">O SBC deve estar preparado para receber verificações de conectividade e responder a verificações de conectividade de vários pontos de extremidade pares.</span><span class="sxs-lookup"><span data-stu-id="a9bda-140">The SBC must be prepared to receive connectivity checks and respond to connectivity checks from multiple peer endpoints.</span></span> <span data-ttu-id="a9bda-141">Por exemplo, o Teams usuário pode ser assinado em uma área de trabalho e em um telefone celular.</span><span class="sxs-lookup"><span data-stu-id="a9bda-141">For example, the Teams user could be signed on to both a desktop and a cell phone.</span></span> <span data-ttu-id="a9bda-142">Ambos os dispositivos serão notificados da chamada de entrada e tentarão verificações de conectividade com o SBC.</span><span class="sxs-lookup"><span data-stu-id="a9bda-142">Both devices will be notified of the inbound call and will attempt connectivity checks with the SBC.</span></span>

<span data-ttu-id="a9bda-143">Eventualmente, apenas um dos pontos de extremidade atenderá à chamada (200OK).</span><span class="sxs-lookup"><span data-stu-id="a9bda-143">Eventually only one of the endpoints will answer the call (200OK).</span></span> <span data-ttu-id="a9bda-144">Ao receber o 200OK, o SBC pode configurar o contexto certo para processar os pacotes de mídia.</span><span class="sxs-lookup"><span data-stu-id="a9bda-144">On receiving the 200OK, the SBC can set up the right context for processing the media packets.</span></span>

## <a name="scenarios"></a><span data-ttu-id="a9bda-145">Cenários</span><span class="sxs-lookup"><span data-stu-id="a9bda-145">Scenarios</span></span>

###  <a name="inbound-call-from-sbc"></a><span data-ttu-id="a9bda-146">Chamada de entrada do SBC</span><span class="sxs-lookup"><span data-stu-id="a9bda-146">Inbound call from SBC</span></span>

<span data-ttu-id="a9bda-147">Para esse cenário, há vários pontos de extremidade de par possíveis que o SBC deve manipular:</span><span class="sxs-lookup"><span data-stu-id="a9bda-147">For this scenario, there are several possible peer endpoints that the SBC must handle:</span></span>

- <span data-ttu-id="a9bda-148">Os pontos de extremidade do servidor normalmente responderão diretamente com o 200OK.</span><span class="sxs-lookup"><span data-stu-id="a9bda-148">Server endpoints will typically respond directly with 200OK.</span></span> <span data-ttu-id="a9bda-149">Esses são pontos de extremidade ICE completos que normalmente estão envolvidos nos cenários caixa postal, fila de chamada e Atendedor Automático.</span><span class="sxs-lookup"><span data-stu-id="a9bda-149">These are full ICE endpoints that are typically involved in Voicemail, Call queue, and Auto attendant scenarios.</span></span>

- <span data-ttu-id="a9bda-150">Os pontos de extremidade do cliente podem enviar várias respostas provisórias com diferentes marcas De/Para (183) seguidas por um 200OK do ponto de extremidade que atende à chamada.</span><span class="sxs-lookup"><span data-stu-id="a9bda-150">Client endpoints can send multiple provisional answers with different From/To tags (183) followed by a 200OK from the endpoint that answers the call.</span></span> <span data-ttu-id="a9bda-151">Esses são pontos de extremidade ICE completos geralmente representando clientes de usuário final.</span><span class="sxs-lookup"><span data-stu-id="a9bda-151">These are full ICE endpoints typically representing end user clients.</span></span>

- <span data-ttu-id="a9bda-152">Outros pontos de extremidade SBC.</span><span class="sxs-lookup"><span data-stu-id="a9bda-152">Other SBC endpoints.</span></span> <span data-ttu-id="a9bda-153">Esses são pontos de extremidade ICE Lite geralmente envolvidos no cenário de pontos de extremidade do cliente simultaneamente tocando e outro número de telefone.</span><span class="sxs-lookup"><span data-stu-id="a9bda-153">These are ICE Lite endpoints typically involved in the scenario of simultaneously ringing client endpoints and another phone number(s).</span></span>

<span data-ttu-id="a9bda-154">O SBC deve responder a todas as solicitações de verificação de conectividade válidas recebidas dos pontos de extremidade ICE completos.</span><span class="sxs-lookup"><span data-stu-id="a9bda-154">The SBC must respond to all valid connectivity check requests received from the full ICE endpoints.</span></span> <span data-ttu-id="a9bda-155">Por RFC, os pontos de extremidade ICE completos se tornarão pontos de extremidade controlando.</span><span class="sxs-lookup"><span data-stu-id="a9bda-155">Per RFC, the full ICE endpoints will become Controlling endpoints.</span></span> <span data-ttu-id="a9bda-156">Os Teams de extremidade (cliente/servidor) executarão indicações "Regulares" para concluir verificações de conectividade.</span><span class="sxs-lookup"><span data-stu-id="a9bda-156">The Teams (client/server) endpoints will perform “Regular” nominations to complete connectivity checks.</span></span> <span data-ttu-id="a9bda-157">O final 200Ok pode ser de um ponto de extremidade que enviou mídia inicial ou de um ponto de extremidade diferente.</span><span class="sxs-lookup"><span data-stu-id="a9bda-157">The final 200Ok can either be from an endpoint that sent early media or from a different endpoint.</span></span> <span data-ttu-id="a9bda-158">Ao receber o 200Ok, o SBC deve configurar o contexto certo para o fluxo de mídia.</span><span class="sxs-lookup"><span data-stu-id="a9bda-158">On receiving the 200Ok, the SBC must set up the right context for media flow.</span></span> 

###  <a name="early-media"></a><span data-ttu-id="a9bda-159">Mídia inicial</span><span class="sxs-lookup"><span data-stu-id="a9bda-159">Early media</span></span>

<span data-ttu-id="a9bda-160">Se houver um fluxo de mídia inicial, o SBC deverá ser travado no primeiro ponto de extremidade que inicia a transmissão de mídia; O fluxo de mídia pode começar antes que os candidatos sejam nomeados.</span><span class="sxs-lookup"><span data-stu-id="a9bda-160">If there is early media flow, the SBC must latch to the first endpoint that starts streaming media; media flow can start before candidates are nominated.</span></span> <span data-ttu-id="a9bda-161">O SBC deve ter suporte para o envio de DTMF durante essa fase para habilitar cenários de IVR/caixa postal.</span><span class="sxs-lookup"><span data-stu-id="a9bda-161">The SBC should have support for sending DTMF during this phase to enable IVR/voicemail scenarios.</span></span> <span data-ttu-id="a9bda-162">O SBC deve usar o caminho de prioridade mais alta no qual recebeu verificações se as nomeações não foram concluídas.</span><span class="sxs-lookup"><span data-stu-id="a9bda-162">The SBC should use the highest priority path on which it has received checks if nominations have not completed.</span></span>

### <a name="outbound-call-to-sbc"></a><span data-ttu-id="a9bda-163">Chamada de saída para SBC</span><span class="sxs-lookup"><span data-stu-id="a9bda-163">Outbound call to SBC</span></span>

<span data-ttu-id="a9bda-164">Os Teams de extremidade são o Chamador deste cenário e serão o Ponto de Extremidade de Controle.</span><span class="sxs-lookup"><span data-stu-id="a9bda-164">The Teams endpoints are the Caller for this scenario and will be the Controlling Endpoint.</span></span> <span data-ttu-id="a9bda-165">Ao receber uma resposta provisória (183) ou uma resposta final(200OK), o ponto de extremidade Teams iniciará verificações de conectividade e prosseguirá para nomeações "Regulares" para concluir as verificações de conectividade.</span><span class="sxs-lookup"><span data-stu-id="a9bda-165">On receiving either a provisional answer (183) or a final answer(200OK), the Teams endpoint  will start connectivity checks and proceed to “Regular” nominations to complete the connectivity checks.</span></span>

<span data-ttu-id="a9bda-166">Observação: se o SBC enviar uma resposta provisória (183), o SBC deverá estar pronto para receber solicitações de verificação de conectividade e potencialmente concluir as nomeações antes que o 200OK seja enviado pelo SBC.</span><span class="sxs-lookup"><span data-stu-id="a9bda-166">Note: If the SBC sends a provisional answer (183), the SBC must be ready to receive connectivity check requests and potentially complete the nominations  before the 200OK is sent by the SBC.</span></span> <span data-ttu-id="a9bda-167">Se as verificações e/ou indicações são concluídas antes que o 200OK seja recebido, as verificações e/ou nomeações não serão executadas novamente depois que 200OK for recebido.</span><span class="sxs-lookup"><span data-stu-id="a9bda-167">If checks and/or nominations are completed before the 200OK is received, checks and/or nominations will not be performed again after 200OK is received.</span></span> <span data-ttu-id="a9bda-168">O SBC não deve alterar candidatos ICE, senha e ufrag (fragmento de nome de usuário) entre 183 e 200.</span><span class="sxs-lookup"><span data-stu-id="a9bda-168">The SBC must not change ICE candidates, password, and ufrag (username fragment) between 183 and 200.</span></span>

<span data-ttu-id="a9bda-169">Para dar suporte à mídia inicial, o SBC pode começar a transmitir a mídia para o candidato ICE par, com a maior prioridade com base nas verificações de conectividade recebidas, mesmo antes que as nomeações sejam concluídas por Teams ponto de extremidade.</span><span class="sxs-lookup"><span data-stu-id="a9bda-169">To support early media, the SBC may start streaming the media to the peer ICE candidate, with the highest priority based on received connectivity checks, even before nominations are completed by Teams endpoint.</span></span> <span data-ttu-id="a9bda-170">O SBC deve esperar que a mídia Teams em qualquer candidato até que as nomeações sejam concluídas.</span><span class="sxs-lookup"><span data-stu-id="a9bda-170">The SBC should expect media from Teams on any candidate until nominations are completed.</span></span> <span data-ttu-id="a9bda-171">Depois que um candidato é nomeado, o SBC deve redefinir para o contexto certo para enviar e receber pacotes de mídia.</span><span class="sxs-lookup"><span data-stu-id="a9bda-171">Once a candidate is nominated, the SBC must reset to the right context to send and receive media packets.</span></span>

## <a name="srtp-support-requirements"></a><span data-ttu-id="a9bda-172">Requisitos de suporte SRTP</span><span class="sxs-lookup"><span data-stu-id="a9bda-172">SRTP support requirements</span></span>

<span data-ttu-id="a9bda-173">O SBC deve oferecer suporte à codificação de criptografia SRTP AES_CM_128_HMAC_SHA1_80 para oferta e resposta no seguinte formato:</span><span class="sxs-lookup"><span data-stu-id="a9bda-173">The SBC must support SRTP encryption cipher AES_CM_128_HMAC_SHA1_80 for offer and answer in the following format:</span></span>

```console
"inline:" <key||salt> ["|" lifetime]
```

<span data-ttu-id="a9bda-174">Veja a seguir um exemplo do atributo crypto na oferta SDP do SBC:</span><span class="sxs-lookup"><span data-stu-id="a9bda-174">The following is an example of the crypto attribute in the SDP offer from the SBC:</span></span>

```console
a=crypto:1 AES_CM_128_HMAC_SHA1_80 inline:V/Lr6Lsvhad/crSB9kCQ28jrYDxR2Yfk5bXryH5V|2^31
```

<span data-ttu-id="a9bda-175">Os parâmetros MKI e Length não são necessários.</span><span class="sxs-lookup"><span data-stu-id="a9bda-175">MKI and Length parameters are not required.</span></span>

<span data-ttu-id="a9bda-176">Para obter mais informações, [consulte RFC 4568, seção 6.1](https://tools.ietf.org/html/rfc4568#section-6.1).</span><span class="sxs-lookup"><span data-stu-id="a9bda-176">For more information, see [RFC 4568, section 6.1](https://tools.ietf.org/html/rfc4568#section-6.1).</span></span>

## <a name="sdes-support-requirements"></a><span data-ttu-id="a9bda-177">Requisitos de suporte do SDES</span><span class="sxs-lookup"><span data-stu-id="a9bda-177">SDES support requirements</span></span>

<span data-ttu-id="a9bda-178">O dispositivo deve ser capaz de oferecer SDES no formato conforme descrito abaixo.</span><span class="sxs-lookup"><span data-stu-id="a9bda-178">The device must be able to offer SDES in the format as described below.</span></span> <span data-ttu-id="a9bda-179">Os processadores de mídia da Microsoft sempre preferem o SDES.</span><span class="sxs-lookup"><span data-stu-id="a9bda-179">Microsoft Media Processors always prefer SDES.</span></span>

- <span data-ttu-id="a9bda-180">Com o bypass que não seja de mídia, mesmo que um cliente suporte apenas DTLS, os Processadores de Mídia serão convertidos em SDES.</span><span class="sxs-lookup"><span data-stu-id="a9bda-180">With non-media bypass, even if a client only supports DTLS, the Media Processors will convert to SDES.</span></span>

- <span data-ttu-id="a9bda-181">Com o bypass de mídia, se um cliente for apenas DTLS (futuro estado do Google Chrome), o Roteamento Direto inserirá um MP no caminho, convertendo a chamada de bypass de mídia em bypass de não mídia.</span><span class="sxs-lookup"><span data-stu-id="a9bda-181">With media bypass, if a client is DTLS only (future Google Chrome state), Direct Routing will insert an MP in the path, converting the call from media bypass to non-media bypass.</span></span> <span data-ttu-id="a9bda-182">Entre o SBC e o componente do processador de mídia do Roteamento Direto, o SDES é sempre usado.</span><span class="sxs-lookup"><span data-stu-id="a9bda-182">Between the SBC and media processor component of Direct Routing, SDES is always used.</span></span>

<span data-ttu-id="a9bda-183">Atualmente, não há nenhum cliente Teams que ofereça apenas DTLS; no entanto, o Google anuncia que, em algum momento, eles param de dar suporte ao SDES.</span><span class="sxs-lookup"><span data-stu-id="a9bda-183">Currently, there are no Teams client that offer only DTLS; however Google has announced that at some point in time they will stop supporting SDES.</span></span>

## <a name="format-for-offer-from-sbc-in-bypass-mode"></a><span data-ttu-id="a9bda-184">Format for offer from SBC in bypass mode</span><span class="sxs-lookup"><span data-stu-id="a9bda-184">Format for offer from SBC in bypass mode</span></span> 

<span data-ttu-id="a9bda-185">A oferta deve conter SDES e pode conter DTLS opcional no seguinte formato:</span><span class="sxs-lookup"><span data-stu-id="a9bda-185">Offer must contain SDES and can contain DTLS optional in the following format:</span></span>

```console
m=audio 54056 UDP/TLS/RTP/SAVP 0 8 76 77 18 9 101 13
a=rtcp:54056
a=crypto:1 AES_CM_128_HMAC_SHA1_80 inline:krXco0QRglwErMqtbMs2zSw29tBdmdgXpEYZhQmp|2^31
a=fingerprint:sha-256 AE:24:07:15:5C:B7:45:1A:E4:45:60:C1:1E:68:0E:CC:8D:A6:78:3B:76:65:BB:B0:77:88:07:F8:98:18:62:34
a=setup:actpass
a=rtcp-mux
```

### <a name="format-for-answer-containing-sdes-to-sbc"></a><span data-ttu-id="a9bda-186">Format for answer containing SDES to SBC</span><span class="sxs-lookup"><span data-stu-id="a9bda-186">Format for answer containing SDES to SBC</span></span>

```console
m=audio 54056 RTP/SAVP 111 103 104 9 0 8 description 106 13 110 112 113 126
a=rtcp:54056
a=crypto:2 AES_CM_128_HMAC_SHA1_80 inline:fBc61ikv1kMy0sF85DblNqTzVAbFa7hJQ9GKb6Yj|2^31|1:1
a=crypto:3 AES_CM_128_HMAC_SHA1_80 inline:O1qT9tWbs/NwJVwhfrgF5tCrbNOxnVDqkIqTx4rz|2^31
a=rtcp-mux

```

## <a name="format-for-offer-from-teams-to-sbc"></a><span data-ttu-id="a9bda-187">Format for offer from Teams to SBC</span><span class="sxs-lookup"><span data-stu-id="a9bda-187">Format for offer from Teams to SBC</span></span> 

### <a name="format-for-sdes-only-offer-to-sbc"></a><span data-ttu-id="a9bda-188">Format for SDES only offer to SBC</span><span class="sxs-lookup"><span data-stu-id="a9bda-188">Format for SDES only offer to SBC</span></span>

```console
m=audio 52884 RTP/SAVP 111 103 104 9 0 8 106 13 110 112 113 126
a=crypto:0 AES_CM_128_HMAC_SHA1_32 inline:Hr4D2cgUu9+Uza5Igz/JkVx59DAxDbaxJg862ibQ|2^31
a=crypto:1 AES_CM_128_HMAC_SHA1_80 inline:JPEaIxHegfuv53ykBPZk8hV0GO8kTiiqRMfHimEE|2^31
a=rtcp:52884
a=rtcp-mux
```

