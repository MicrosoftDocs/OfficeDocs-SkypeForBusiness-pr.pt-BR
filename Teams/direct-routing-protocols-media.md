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
ms.openlocfilehash: 550836275a1ea060d6004c75e0f2bf301f3094a7752ae80ad44dc2c91bbf96bd
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2021
ms.locfileid: "54339777"
---
# <a name="overview"></a>Visão Geral

Este artigo descreve como o Roteamento Direto dá suporte ao bypass de mídia com um Controlador de Borda de Sessão (SBC) habilitado para ICE Lite, conforme descrito em [RFC 5245](https://tools.ietf.org/html/rfc5245). Este artigo destina-se aos administradores de voz responsáveis por configurar a conexão entre o SBC local e o serviço proxy SIP.

Este artigo fornece uma visão geral dos cenários e requisitos do ICE Lite para interoperabilidade. O artigo descreve os formatos de mensagem e as transições de máquina de estado necessárias para garantir o fluxo confiável de chamada e mídia.

## <a name="terminology"></a>Terminologia

- Primeiro Hello – As primeiras palavras faladas pelo chamador e pelo chamador. É importante que todos os esforços sejam feitos para garantir que os primeiros pacotes dos pontos de extremidade sejam entregues de forma confiável para a maioria dos casos de uso.

- Forking – A oferta do chamador pode ser entregue a vários pontos de extremidade do chamador se o chamador estiver disponível em vários dispositivos (por exemplo, um usuário do Teams pode ser conectado ao Teams para Windows e Teams para Android ou iPhone).

- Resposta Provisória (183) – Os pontos de extremidade do chamador para configuração de chamada mais rápida enviam uma resposta com os candidatos e as chaves necessárias para estabelecer o fluxo de mídia. Isso é feito em antecipação do usuário potencialmente respondendo a chamada(200OK) dessa instância de chamador específica. Com a forking, o chamador deve estar pronto para receber várias respostas provisórias.

- Re-Invite – Oferta com os candidatos finais selecionados pelo ponto de extremidade de controle ICE. Isso terá o atributo a=remote-candidate para resolver qualquer condição de corrida de manipular vários bifurcações.

- Teams Ponto de extremidade – Pode ser um servidor (Processador de Mídia, Retransmissão de Transporte) ou o Teams cliente.

## <a name="message-format"></a>Formato de mensagem

A Teams segue a RFC 5245 para ICE-Lite. Isso implica que todas as mensagens STUN estarão em conformidade com [o RFC 5389](https://tools.ietf.org/html/rfc5389).

Os SBCs conforme exigido pela RFC 5389 devem ignorar todos os atributos do STUN que não reconhecem e continuar a processar as mensagens com os atributos conhecidos. 

Se algum pacote malformado for recebido, os pacotes devem ser descartados sem afetar o estabelecimento da sessão de mídia.

## <a name="ice-lite-requirements"></a>Requisitos do ICE Lite

Esta seção captura brevemente os requisitos do ICE Lite.

### <a name="candidate-gathering"></a>Reunião de candidatos

O SBC deve oferecer apenas um candidato que seja publicamente acessível. Atualmente, apenas os candidatos IPV4 são suportados.


#### <a name="connectivity-checks"></a>Verificações de conectividade

A implementação do ICE Lite deve responder a todas as verificações de conectividade recebidas. O ponto de extremidade ICE Lite não deve enviar solicitações de verificação de conectividade. (Se as verificações de conectividade são enviadas em violação, a implementação completa responderá, o que pode resultar em candidatos inesperados derivados por pares sendo descobertos e potencialmente resultar em falhas de chamada.)

#### <a name="nominations"></a>Indicações

O ponto de extremidade de implementação total do ICE sempre será o ponto de extremidade De controle e seguirá as indicações "Regulares" para selecionar os candidatos finais a serem usados para o fluxo de mídia. O ponto de extremidade ICE Lite pode usar as nomeações para concluir o caminho a ser usado para mídia e concluir o estabelecimento de chamada.

Observação: no caso de forcar com pontos de extremidade pares enviando 183 respostas provisórias, o SBC deve estar pronto para responder a verificações de vários pontos de extremidade e também a nomeações de vários pontos de extremidade se as nomeações acontecerem antes de 200OK. Dependendo da convergência da máquina de estado ICE no caminho final e no tempo da resposta do usuário, as nomeações podem acontecer antes ou depois de 200OK. O SBC deve ser capaz de lidar com ambos os casos.

#### <a name="converging-for-forking"></a>Convergindo para a forcar

Se a oferta do SBC for bifurcada para vários pontos de extremidade Teams, os pontos de extremidade Teams podem responder com uma resposta provisória e iniciar verificações de conectividade. O SBC deve estar preparado para receber verificações de conectividade e responder a verificações de conectividade de vários pontos de extremidade pares. Por exemplo, o Teams usuário pode ser assinado em uma área de trabalho e em um telefone celular. Ambos os dispositivos serão notificados da chamada de entrada e tentarão verificações de conectividade com o SBC.

Eventualmente, apenas um dos pontos de extremidade atenderá à chamada (200OK). Ao receber o 200OK, o SBC pode configurar o contexto certo para processar os pacotes de mídia.

## <a name="scenarios"></a>Cenários

###  <a name="inbound-call-from-sbc"></a>Chamada de entrada do SBC

Para esse cenário, há vários pontos de extremidade de par possíveis que o SBC deve manipular:

- Os pontos de extremidade do servidor normalmente responderão diretamente com o 200OK. Esses são pontos de extremidade ICE completos que normalmente estão envolvidos nos cenários caixa postal, fila de chamada e Atendedor Automático.

- Os pontos de extremidade do cliente podem enviar várias respostas provisórias com diferentes marcas De/Para (183) seguidas por um 200OK do ponto de extremidade que atende à chamada. Esses são pontos de extremidade ICE completos geralmente representando clientes de usuário final.

- Outros pontos de extremidade SBC. Esses são pontos de extremidade ICE Lite geralmente envolvidos no cenário de pontos de extremidade do cliente simultaneamente tocando e outro número de telefone.

O SBC deve responder a todas as solicitações de verificação de conectividade válidas recebidas dos pontos de extremidade ICE completos. Por RFC, os pontos de extremidade ICE completos se tornarão pontos de extremidade controlando. Os Teams de extremidade (cliente/servidor) executarão indicações "Regulares" para concluir verificações de conectividade. O final 200Ok pode ser de um ponto de extremidade que enviou mídia inicial ou de um ponto de extremidade diferente. Ao receber o 200Ok, o SBC deve configurar o contexto certo para o fluxo de mídia. 

###  <a name="early-media"></a>Mídia inicial

Se houver um fluxo de mídia inicial, o SBC deverá ser travado no primeiro ponto de extremidade que inicia a transmissão de mídia; O fluxo de mídia pode começar antes que os candidatos sejam nomeados. O SBC deve ter suporte para o envio de DTMF durante essa fase para habilitar cenários de IVR/caixa postal. O SBC deve usar o caminho de prioridade mais alta no qual recebeu verificações se as nomeações não foram concluídas.

### <a name="outbound-call-to-sbc"></a>Chamada de saída para SBC

Os Teams de extremidade são o Chamador deste cenário e serão o Ponto de Extremidade de Controle. Ao receber uma resposta provisória (183) ou uma resposta final(200OK), o ponto de extremidade Teams iniciará verificações de conectividade e prosseguirá para nomeações "Regulares" para concluir as verificações de conectividade.

Observação: se o SBC enviar uma resposta provisória (183), o SBC deverá estar pronto para receber solicitações de verificação de conectividade e potencialmente concluir as nomeações antes que o 200OK seja enviado pelo SBC. Se as verificações e/ou indicações são concluídas antes que o 200OK seja recebido, as verificações e/ou nomeações não serão executadas novamente depois que 200OK for recebido. O SBC não deve alterar candidatos ICE, senha e ufrag (fragmento de nome de usuário) entre 183 e 200.

Para dar suporte à mídia inicial, o SBC pode começar a transmitir a mídia para o candidato ICE par, com a maior prioridade com base nas verificações de conectividade recebidas, mesmo antes que as nomeações sejam concluídas por Teams ponto de extremidade. O SBC deve esperar que a mídia Teams em qualquer candidato até que as nomeações sejam concluídas. Depois que um candidato é nomeado, o SBC deve redefinir para o contexto certo para enviar e receber pacotes de mídia.

## <a name="srtp-support-requirements"></a>Requisitos de suporte SRTP

O SBC deve oferecer suporte à codificação de criptografia SRTP AES_CM_128_HMAC_SHA1_80 para oferta e resposta no seguinte formato:

```console
"inline:" <key||salt> ["|" lifetime]
```

Veja a seguir um exemplo do atributo crypto na oferta SDP do SBC:

```console
a=crypto:1 AES_CM_128_HMAC_SHA1_80 inline:V/Lr6Lsvhad/crSB9kCQ28jrYDxR2Yfk5bXryH5V|2^31
```

Os parâmetros MKI e Length não são necessários.

Para obter mais informações, [consulte RFC 4568, seção 6.1](https://tools.ietf.org/html/rfc4568#section-6.1).

## <a name="sdes-support-requirements"></a>Requisitos de suporte do SDES

O dispositivo deve ser capaz de oferecer SDES no formato conforme descrito abaixo. Os processadores de mídia da Microsoft sempre preferem o SDES.

- Com o bypass que não seja de mídia, mesmo que um cliente suporte apenas DTLS, os Processadores de Mídia serão convertidos em SDES.

- Com o bypass de mídia, se um cliente for apenas DTLS (futuro estado do Google Chrome), o Roteamento Direto inserirá um MP no caminho, convertendo a chamada de bypass de mídia em bypass de não mídia. Entre o SBC e o componente do processador de mídia do Roteamento Direto, o SDES é sempre usado.

Atualmente, não há nenhum cliente Teams que ofereça apenas DTLS; no entanto, o Google anuncia que, em algum momento, eles param de dar suporte ao SDES.

## <a name="format-for-offer-from-sbc-in-bypass-mode"></a>Format for offer from SBC in bypass mode 

A oferta deve conter SDES e pode conter DTLS opcional no seguinte formato:

```console
m=audio 54056 UDP/TLS/RTP/SAVP 0 8 76 77 18 9 101 13
a=rtcp:54056
a=crypto:1 AES_CM_128_HMAC_SHA1_80 inline:krXco0QRglwErMqtbMs2zSw29tBdmdgXpEYZhQmp|2^31
a=fingerprint:sha-256 AE:24:07:15:5C:B7:45:1A:E4:45:60:C1:1E:68:0E:CC:8D:A6:78:3B:76:65:BB:B0:77:88:07:F8:98:18:62:34
a=setup:actpass
a=rtcp-mux
```

### <a name="format-for-answer-containing-sdes-to-sbc"></a>Format for answer containing SDES to SBC

```console
m=audio 54056 RTP/SAVP 111 103 104 9 0 8 description 106 13 110 112 113 126
a=rtcp:54056
a=crypto:2 AES_CM_128_HMAC_SHA1_80 inline:fBc61ikv1kMy0sF85DblNqTzVAbFa7hJQ9GKb6Yj|2^31|1:1
a=crypto:3 AES_CM_128_HMAC_SHA1_80 inline:O1qT9tWbs/NwJVwhfrgF5tCrbNOxnVDqkIqTx4rz|2^31
a=rtcp-mux

```

## <a name="format-for-offer-from-teams-to-sbc"></a>Format for offer from Teams to SBC 

### <a name="format-for-sdes-only-offer-to-sbc"></a>Format for SDES only offer to SBC

```console
m=audio 52884 RTP/SAVP 111 103 104 9 0 8 106 13 110 112 113 126
a=crypto:0 AES_CM_128_HMAC_SHA1_32 inline:Hr4D2cgUu9+Uza5Igz/JkVx59DAxDbaxJg862ibQ|2^31
a=crypto:1 AES_CM_128_HMAC_SHA1_80 inline:JPEaIxHegfuv53ykBPZk8hV0GO8kTiiqRMfHimEE|2^31
a=rtcp:52884
a=rtcp-mux
```

