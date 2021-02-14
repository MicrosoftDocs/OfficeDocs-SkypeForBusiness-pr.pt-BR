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
# <a name="overview"></a>Visão Geral

Este artigo descreve como o Roteamento Direto dá suporte ao bypass de mídia com um Controlador de Borda de Sessão (SBC) habilitado para ICE Lite, conforme descrito no [RFC 5245.](https://tools.ietf.org/html/rfc5245) Este artigo destina-se aos administradores de voz que são responsáveis por configurar a conexão entre o SBC local e o serviço proxy SIP.

Este artigo fornece uma visão geral dos cenários e requisitos do ICE Lite para interoperabilidade. O artigo descreve os formatos de mensagem e as transições de máquina de estado necessárias para garantir um fluxo confiável de chamada e mídia.

## <a name="terminology"></a>Terminologia

- First Hello – The first words spoken by the caller and callee. É importante que todos os esforços sejam feitos para garantir que os primeiros pacotes dos pontos de extremidade sejam entregues de forma confiável para a maioria dos casos de uso.

- Tinta – A oferta do chamador pode ser entregue em vários pontos de extremidade de chamador se o chamador estiver disponível em vários dispositivos (por exemplo, um usuário do Teams pode estar conectado ao Teams para Windows e ao Teams para Android ou iPhone).

- Resposta indébil (183) – Os pontos de extremidade do chamador para a configuração de chamada mais rápida enviam uma resposta com os candidatos e as chaves necessárias para estabelecer o fluxo de mídia. Isso é feito em antecipação do usuário potencialmente atendendo a chamada(200OK) dessa instância de chamador específica. Com a execução de à toa, o chamador deve estar pronto para receber várias respostas prontas.

- Re-Invite – Oferta com os candidatos finais selecionados pelo ponto de extremidade de controle ICE. Isso terá o atributo a=candidato remoto para resolver quaisquer condições de corrida ao lidar com vários bifurcações.

- Ponto de extremidade do Teams : pode ser um servidor (Processador de Mídia, Retransmissão de Transporte) ou o cliente do Teams.

## <a name="message-format"></a>Formato da mensagem

A infraestrutura do Teams segue o RFC 5245 para ICE-Lite. Isso implica que todas as mensagens STUN estarão em conformidade com [o RFC 5389.](https://tools.ietf.org/html/rfc5389)

Os SBCs conforme exigido pelo RFC 5389 devem ignorar quaisquer atributos STUN que não reconhecerem e continuar a processar as mensagens com os atributos conhecidos. 

Se algum pacote malformido for recebido, os pacotes deverão ser descartados sem afetar o estabelecimento da sessão de mídia.

## <a name="ice-lite-requirements"></a>Requisitos do ICE Lite

Esta seção captura brevemente os requisitos do ICE Lite.

### <a name="candidate-gathering"></a>Reunião de candidatos

O SBC deve oferecer apenas um candidato que seja publicamente acessível. Atualmente, somente os candidatos IPV4 têm suporte.


#### <a name="connectivity-checks"></a>Verificações de conectividade

A implementação do ICE Lite deve responder a todas as verificações de conectividade recebidas. O ponto de extremidade ICE Lite não deve enviar solicitações de verificação de conectividade. (Se as verificações de conectividade são enviadas em violação, a implementação completa responderá, o que pode resultar na descoberta inesperada de candidatos derivados por pares e potencialmente resultar em falhas de chamada.)

#### <a name="nominations"></a>Nomeações

O ponto de extremidade de implementação total ICE sempre será o ponto de extremidade Controlando e seguirá as políticas "Regulares" para selecionar os candidatos finais a serem usados para o fluxo de mídia. O ponto de extremidade ICE Lite pode usar as políticas para concluir o caminho a ser usado para mídia e concluir a chamada.

Observação: no caso de forcar com pontos de extremidade de ponto de extremidade enviando 183 respostas inoperantes, o SBC deve estar pronto para responder a verificações de vários pontos de extremidade e também a reações de vários pontos de extremidade se as reações acontecerem antes de 200OK. Dependendo da densidade da máquina de estado ICE no caminho final e no tempo da resposta do usuário, as indicação podem acontecer antes ou depois de 200OK. O SBC deve ser capaz de lidar com ambos os casos.

#### <a name="converging-for-forking"></a>Convergindo para a forcar

Se a oferta do SBC for bifurcada para vários pontos de extremidade do Teams, os pontos de extremidade do Teams poderão responder com uma resposta errada e iniciar verificações de conectividade. O SBC deve estar preparado para receber verificações de conectividade e responder a verificações de conectividade de vários pontos de extremidade de ponto de extremidade. Por exemplo, o usuário do Teams pode estar com uma área de trabalho e um telefone celular. Os dois dispositivos serão notificados sobre a chamada de entrada e tentarão verificar a conectividade com o SBC.

Eventualmente, apenas um dos pontos de extremidade atenderá a chamada (200OK). Ao receber a 200OK, o SBC pode configurar o contexto certo para processar os pacotes de mídia.

## <a name="scenarios"></a>Cenários

###  <a name="inbound-call-from-sbc"></a>Chamada de entrada do SBC

Para esse cenário, há vários pontos de extremidade de ponto possíveis que o SBC deve lidar:

- Os pontos de extremidade do servidor normalmente responderão diretamente com a 200OK. Esses são pontos de extremidade ICE completos que normalmente estão envolvidos em cenários de Caixa Postal, Fila de chamada e Atendedor automático.

- Os pontos de extremidade do cliente podem enviar várias respostas erradas com diferentes marcas De/Para (183) seguidas por uma 200OK do ponto de extremidade que responde à chamada. Esses são pontos de extremidade ICE completos que normalmente representam clientes do usuário final.

- Outros pontos de extremidade SBC. Estes são pontos de extremidade ICE Lite normalmente envolvidos no cenário de toque simultâneo dos pontos de extremidade do cliente e outros números de telefone.

O SBC deve responder a todas as solicitações válidas de verificação de conectividade recebidas dos pontos de extremidade ICE completos. Por RFC, os pontos de extremidade ICE completos se tornarão pontos de extremidade Controlando. Os pontos de extremidade do Teams (cliente/servidor) executarão políticas "Regulares" para concluir verificações de conectividade. O final 200Ok pode ser de um ponto de extremidade que enviou mídia antecipada ou de um ponto de extremidade diferente. Ao receber a 200Ok, o SBC deve configurar o contexto certo para o fluxo de mídia. 

###  <a name="early-media"></a>Mídia antecipada

Se houver um fluxo de mídia antecipado, o SBC deverá ir para o primeiro ponto de extremidade que inicia o streaming de mídia; o fluxo de mídia pode começar antes que os candidatos sejam indicados. O SBC deve ter suporte para o envio de DTMF durante essa fase para habilitar cenários de IVR/caixa postal. O SBC deve usar o caminho de prioridade mais alta no qual recebeu verificações se não foram concluídas.

### <a name="outbound-call-to-sbc"></a>Chamada de saída para SBC

Os pontos de extremidade do Teams são o Chamador desse cenário e serão o Ponto de Extremidade de Controle. Ao receber uma resposta 183 (183) ou uma resposta final(200OK), o ponto de extremidade do Teams iniciará verificações de conectividade e prosseguirá para "Regular" para concluir as verificações de conectividade.

Observação: se o SBC enviar uma resposta inoperante (183), o SBC deverá estar pronto para receber solicitações de verificação de conectividade e, potencialmente, concluir as reações antes que a 200OK seja enviada pelo SBC. Se as verificações e/ou reações foram concluídas antes que a 200OK seja recebida, as verificações e/ou reações não serão executadas novamente depois que 200OK for recebida. O SBC não deve alterar candidatos ICE, senha e chave (fragmento de nome de usuário) entre 183 e 200.

Para dar suporte à mídia antecipada, o SBC pode começar a transmitir a mídia para o candidato ICE, com a prioridade mais alta com base em verificações de conectividade recebidas, mesmo antes da conclusão das conversas pelo ponto de extremidade do Teams. O SBC deve esperar mídia do Teams em qualquer candidato até que as afirmações sejam concluídas. Depois que um candidato for nomeado, o SBC deverá redefinir para o contexto certo para enviar e receber pacotes de mídia.

## <a name="srtp-support-requirements"></a>Requisitos de suporte SRTP

O SBC deve dar suporte à criptografia SRTP AES_CM_128_HMAC_SHA1_80 dados para oferta e resposta no seguinte formato:

```console
"inline:" <key||salt> ["|" lifetime]
```

Veja a seguir um exemplo do atributo cripto na oferta SDP do SBC:

```console
a=crypto:1 AES_CM_128_HMAC_SHA1_80 inline:V/Lr6Lsvhad/crSB9kCQ28jrYDxR2Yfk5bXryH5V|2^31
```

Os parâmetros MKI e Comprimento não são necessários.

Para obter mais informações, consulte [RFC 4568, seção 6.1.](https://tools.ietf.org/html/rfc4568#section-6.1)

## <a name="sdes-support-requirements"></a>Requisitos de suporte do SDES

O dispositivo deve ser capaz de oferecer SDES no formato conforme descrito abaixo. Os processadores de mídia da Microsoft sempre preferem SDES.

- Com o bypass de fora da mídia, mesmo que um cliente só seja compatível com DTLS, os Processadores de Mídia serão convertidos em SDES.

- Com o bypass de mídia, se um cliente for apenas DTLS (futuro estado do Google Chrome), o Roteamento Direto inserirá uma MP no caminho, convertendo a chamada de bypass de mídia em bypass sem mídia. Entre o SBC e o componente do processador de mídia do Roteamento Direto, o SDES é sempre usado.

Atualmente, não há nenhum cliente do Teams que ofereça apenas DTLS; no entanto, o Google anunciou que, em algum momento, eles deixarão de oferecer suporte ao SDES.

## <a name="format-for-offer-from-sbc-in-bypass-mode"></a>Formatar para oferta do SBC no modo de bypass 

A oferta deve conter SDES e pode conter DTLS opcional no seguinte formato:

```console
m=audio 54056 UDP/TLS/RTP/SAVP 0 8 76 77 18 9 101 13
a=rtcp:54056
a=crypto:1 AES_CM_128_HMAC_SHA1_80 inline:krXco0QRglwErMqtbMs2zSw29tBdmdgXpEYZhQmp|2^31
a=fingerprint:sha-256 AE:24:07:15:5C:B7:45:1A:E4:45:60:C1:1E:68:0E:CC:8D:A6:78:3B:76:65:BB:B0:77:88:07:F8:98:18:62:34
a=setup:actpass
a=rtcp-mux
```

### <a name="format-for-answer-containing-sdes-to-sbc"></a>Formato de resposta que contém SDES para SBC

```console
m=audio 54056 RTP/SAVP 111 103 104 9 0 8 description 106 13 110 112 113 126
a=rtcp:54056
a=crypto:2 AES_CM_128_HMAC_SHA1_80 inline:fBc61ikv1kMy0sF85DblNqTzVAbFa7hJQ9GKb6Yj|2^31|1:1
a=crypto:3 AES_CM_128_HMAC_SHA1_80 inline:O1qT9tWbs/NwJVwhfrgF5tCrbNOxnVDqkIqTx4rz|2^31
a=rtcp-mux

```

## <a name="format-for-offer-from-teams-to-sbc"></a>Formatar para oferta do Teams para o SBC 

### <a name="format-for-sdes-only-offer-to-sbc"></a>Formato para oferta somente SDES para SBC

```console
m=audio 52884 RTP/SAVP 111 103 104 9 0 8 106 13 110 112 113 126
a=crypto:0 AES_CM_128_HMAC_SHA1_32 inline:Hr4D2cgUu9+Uza5Igz/JkVx59DAxDbaxJg862ibQ|2^31
a=crypto:1 AES_CM_128_HMAC_SHA1_80 inline:JPEaIxHegfuv53ykBPZk8hV0GO8kTiiqRMfHimEE|2^31
a=rtcp:52884
a=rtcp-mux
```

