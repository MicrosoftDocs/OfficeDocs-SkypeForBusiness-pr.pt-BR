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
description: Protocolos de roteamento direto
appliesto:
- Microsoft Teams
ms.openlocfilehash: 3f21a4532a841a23f6bbb78a57e223616ae539fa
ms.sourcegitcommit: ed3d7ebb193229cab9e0e5be3dc1c28c3f622c1b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41835131"
---
# <a name="overview"></a>Visão geral

Este artigo descreve como o roteamento direto oferece suporte a bypass de mídia com um controlador de borda de sessão (SBC) habilitado para ICE Lite, conforme descrito em [RFC 5245](https://tools.ietf.org/html/rfc5245). Este artigo destina-se a administradores de voz responsáveis por configurar a conexão entre o SBC local e o serviço de proxy SIP.

Este artigo fornece uma visão geral dos cenários e requisitos do ICE Lite para interoperabilidade. O artigo descreve os formatos de mensagem e as transições de máquina de estado necessárias para garantir um fluxo de chamadas e mídias confiáveis.

## <a name="terminology"></a>Terminologia

- Primeira saudação – as primeiras palavras faladas pelo chamador e pelo chamado. É importante que todos os esforços sejam feitos para garantir que os primeiros pacotes dos pontos de extremidade sejam entregues de forma confiável para a maioria dos casos de uso.

- Forking – a oferta do chamador pode ser entregue a vários pontos de extremidade do chamado se o receptor estiver disponível em vários dispositivos (por exemplo, um usuário do teams pode estar conectado ao Teams para Windows e Teams para Android ou iPhone).

- Atendimento provisório (183) – os pontos de extremidade do chamador para uma configuração de chamada mais rápida envie uma resposta com os candidatos e as chaves necessárias para estabelecer o fluxo de mídia. Isso é feito de previsão do usuário que pode atender a chamada (200OK) dessa instância específica do chamador. Com a bifurcação, o chamador deve estar pronto para receber várias respostas de provisórios.

- Convidar novamente – oferta com candidatos finais selecionados pelo ponto de extremidade de controle do ICE. Isso terá o atributo a = candidato remoto para resolver qualquer condição de corrida da manipulação de várias bifurcações.

- Ponto de extremidade do teams – pode ser um servidor (processador de mídia, retransmissão de transporte) ou o cliente do teams.

## <a name="message-format"></a>Formato da mensagem

A infraestrutura de equipe segue a RFC 5245 para ICE-Lite. Isso significa que todas as mensagens STUN serão compatíveis com [RFC 5389](https://tools.ietf.org/html/rfc5389).

O SBCs conforme exigido pela RFC 5389 deve ignorar qualquer atributo STUN que ele não reconhece, e continuar a processar as mensagens com os atributos conhecidos. 

Se forem recebidos pacotes malformados, os pacotes deverão ser descartados sem afetar o estabelecimento da sessão de mídia.

## <a name="ice-lite-requirements"></a>Requisitos do ICE Lite

Esta seção captura brevemente os requisitos do ICE Lite.

### <a name="candidate-gathering"></a>Reunião de candidatos

O SBC deve oferecer apenas um candidato que seja alcançável publicamente. No momento, somente há suporte para os candidatos IPV4.


#### <a name="connectivity-checks"></a>Verificações de conectividade

A implementação do ICE Lite deve responder a todas as verificações de conectividade recebidas. O ponto de extremidade Lite ICE não deve enviar nenhuma solicitação de verificação de conectividade. (Se verificações de conectividade forem enviadas em violação, a implementação completa responderá, o que pode resultar na descoberta de candidatos derivados de pares inesperados e resultar em falhas de chamadas.)

#### <a name="nominations"></a>Indicações

O ponto de extremidade de implementação completa do ICE será sempre o ponto de extremidade de controle e seguirá indicações "regulares" para a seleção dos candidatos finais a serem usados para o fluxo de mídia. O ponto de extremidade Lite ICE pode usar as indicações para concluir o caminho a ser usado para a mídia e para o estabelecimento da chamada completa.

Observação: no caso de bifurcação com pontos de extremidade de ponto de extremidade que enviam respostas do 183, o SBC deve estar pronto para responder a cheques de vários pontos de extremidade e também indicações de vários pontos de extremidade se as indicações acontecerem antes de 200OK. Dependendo da convergência da máquina de estado do ICE no caminho final e na temporização da resposta do usuário, as indicações podem acontecer antes ou depois de 200OK. O SBC deve ser capaz de manipular os dois casos.

#### <a name="converging-for-forking"></a>Convergente para bifurcação

Se a oferta das bifurcações SBC para vários pontos de extremidade de equipes, os pontos de extremidade das equipes podem responder com uma resposta provisório e iniciar verificações de conectividade. O SBC deve estar preparado para receber verificações de conectividade e responder às verificações de conectividade de vários pontos de extremidade do ponto. Por exemplo, o usuário do teams pode estar conectado a uma área de trabalho e a um telefone celular. Os dois dispositivos serão notificados sobre a chamada de entrada e tentarão verificações de conectividade com o SBC.

Eventualmente, apenas um dos pontos de extremidade atenderá à chamada (200OK). Ao receber o 200OK, o SBC pode configurar o contexto correto para processar os pacotes de mídia.

## <a name="scenarios"></a>Cenários

###  <a name="inbound-call-from-sbc"></a>Chamada de entrada do SBC

Para esse cenário, há vários pontos de extremidade de pares possíveis que o SBC deve manipular:

- Os pontos de extremidade do servidor geralmente respondem diretamente com o 200OK. Estes são pontos de extremidade de ICE completos que são tipicamente envolvidos no correio de voz, na fila de chamadas e nos cenários de atendedor automático.

- Os pontos de extremidade do cliente podem enviar várias respostas de provisório com diferentes marcas de/para (183) seguidas por uma 200OK da empresa que atende a chamada. Esses pontos de extremidade de ICE completos geralmente representam clientes de usuários finais.

- Outros pontos de extremidade de SBC. Estes são pontos de extremidade do ICE Lite geralmente envolvidos no cenário de tocar simultaneamente pontos de extremidade do cliente e outro número de telefone.

O SBC deve responder a todas as solicitações de verificação de conectividade válidas recebidas dos pontos de extremidade do ICE completo. Por RFC, os pontos de extremidade de ICE completos ficarão controlando pontos de extremidade. Os pontos de extremidade do Teams (cliente/servidor) executarão as indicações "regular" para concluir as verificações de conectividade. A 200Ok final pode ser de um ponto de extremidade que enviava uma mídia antecipada ou de um ponto de extremidade diferente. Ao receber o 200Ok, o SBC deve configurar o contexto correto para o fluxo de mídia. 

###  <a name="early-media"></a>Mídia inicial

Se houver um fluxo de mídia inicial, o SBC deve travar no primeiro ponto de extremidade que inicia a mídia de streaming; o fluxo de mídia pode começar antes de os candidatos serem nomeados. O SBC deve ter suporte para o envio de DTMF durante essa fase para habilitar cenários de IVR/correio de voz. O SBC deve usar o caminho de prioridade mais alta no qual ele recebeu cheques se as indicações não tiverem sido concluídas.

### <a name="outbound-call-to-sbc"></a>Chamada de saída para SBC

Os pontos de extremidade do teams são o chamador para esse cenário e será o ponto de extremidade de controle. Ao receber uma resposta de provisório (183) ou uma resposta final (200OK), o ponto de extremidade do teams começará a verificar a conectividade e passará para as indicações "regular" para concluir as verificações de conectividade.

Observação: se o SBC enviar uma resposta de provisório (183), o SBC deve estar pronto para receber solicitações de verificação de conectividade e possivelmente concluir as indicações antes de o 200OK ser enviado pelo SBC. Se verificações e/ou indicações forem concluídas antes de o 200OK ser recebido, as verificações e/ou indicações não serão executadas novamente depois que 200OK for recebido. O SBC não deve alterar os candidatos do ICE, a senha e o ufrag (nome de usuário do fragmento) entre 183 e 200.

Para dar suporte à mídia inicial, o SBC pode começar a transmitir a mídia para o candidato do ICE de par, com a prioridade mais alta com base nas verificações de conectividade recebidas, mesmo antes de as indicações serem concluídas pelo ponto de extremidade do teams. O SBC deve esperar mídia do teams em qualquer candidato até que as indicações sejam concluídas. Depois que um candidato é indicado, o SBC deve redefinir para o contexto correto para enviar e receber pacotes de mídia.

## <a name="srtp-support-requirements"></a>Requisitos de suporte do SRTP

O SBC deve suportar a codificação de criptografia do SRTP AES_CM_128_HMAC_SHA1_80 para oferta e resposta no seguinte formato:

```
"inline:" <key||salt> ["|" lifetime]
```

Veja a seguir um exemplo do atributo crypto na oferta SDP do SBC:

```
a=crypto:1 AES_CM_128_HMAC_SHA1_80 inline:V/Lr6Lsvhad/crSB9kCQ28jrYDxR2Yfk5bXryH5V|2^31
```

Os parâmetros MKI e length não são necessários.

Para obter mais informações, consulte [RFC 4568, seção 6,1](https://tools.ietf.org/html/rfc4568#section-6.1).

## <a name="sdes-support-requirements"></a>Requisitos de suporte do SDES

O dispositivo deve ser capaz de oferecer SDES no formato conforme descrito abaixo. Os processadores de mídia da Microsoft sempre preferem SDES.

- Com o bypass não relacionado à mídia, mesmo se um cliente só oferecer suporte a DTLS, os processadores de mídia serão convertidos em SDES.

- Com o bypass de mídia, se um cliente só for DTLS (estado futuro do Google Chrome), o roteamento direto inserirá um MP no caminho, convertendo a chamada de bypass de mídia para bypass de não mídia. Entre o componente do processador de SBC e de mídia do roteamento direto, SDES é sempre usado.

Atualmente, não há nenhum cliente de equipes que ofereça apenas DTLS; no entanto, o Google anunciou que, em algum momento, ele pare de oferecer suporte a SDES.

## <a name="format-for-offer-from-sbc-in-bypass-mode"></a>Formato de oferta do SBC no modo ignorar 

A oferta deve conter SDES e pode conter DTLS opcional no seguinte formato:

```
m=audio 54056 UDP/TLS/RTP/SAVP 0 8 76 77 18 9 101 13
a=rtcp:54056
a=crypto:1 AES_CM_128_HMAC_SHA1_80 inline:krXco0QRglwErMqtbMs2zSw29tBdmdgXpEYZhQmp|2^31
a=fingerprint:sha-256 AE:24:07:15:5C:B7:45:1A:E4:45:60:C1:1E:68:0E:CC:8D:A6:78:3B:76:65:BB:B0:77:88:07:F8:98:18:62:34
a=setup:actpass
a=rtcp-mux
```

### <a name="format-for-answer-containing-sdes-to-sbc"></a>Formatar para resposta que contém SDES para SBC

```
m=audio 54056 RTP/SAVP 111 103 104 9 0 8 description 106 13 110 112 113 126
a=rtcp:54056
a=crypto:2 AES_CM_128_HMAC_SHA1_80 inline:fBc61ikv1kMy0sF85DblNqTzVAbFa7hJQ9GKb6Yj|2^31|1:1
a=crypto:3 AES_CM_128_HMAC_SHA1_80 inline:O1qT9tWbs/NwJVwhfrgF5tCrbNOxnVDqkIqTx4rz|2^31
a=rtcp-mux

```

## <a name="format-for-offer-from-teams-to-sbc"></a>Formato da oferta de Teams para SBC 

### <a name="format-for-sdes-only-offer-to-sbc"></a>Format for SDES somente oferta para SBC

```
m=audio 52884 RTP/SAVP 111 103 104 9 0 8 106 13 110 112 113 126
a=crypto:0 AES_CM_128_HMAC_SHA1_32 inline:Hr4D2cgUu9+Uza5Igz/JkVx59DAxDbaxJg862ibQ|2^31
a=crypto:1 AES_CM_128_HMAC_SHA1_80 inline:JPEaIxHegfuv53ykBPZk8hV0GO8kTiiqRMfHimEE|2^31
a=rtcp:52884
a=rtcp-mux
```

