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
# <a name="direct-routing---definitions-and-rfc-standards"></a>Roteamento Direto – Definições e padrões de RFC

Este artigo descreve como o Roteamento Direto do Sistema de Telefonia do Microsoft Phone implementa protocolos padrão RFC. Este artigo destina-se aos administradores de voz que são responsáveis por configurar a conexão entre o SBC (Controlador de Borda de Sessão) local e o serviço proxy SIP (Session Initiation Protocol).

As interfaces SBC do cliente com os seguintes componentes no back-end do Microsoft Teams: 

- **O proxy SIP** para sinalização. Esse é o componente voltado para a Internet do Roteamento Direto que lida com conexões SIP (TLS) entre os SBCs e o Roteamento Direto.

- **Os processadores de mídia** para mídia. Esse é o componente voltado para a Internet do Roteamento Direto que lida com o tráfego de mídia. Esse componente usa protocolos SRTP e SRTCP.


Para obter mais informações sobre Roteamento Direto, consulte [Roteamento Direto do Sistema de Telefonia.](direct-routing-landing-page.md)

Para saber mais sobre como o Roteamento Direto implementa o protocolo SIP, consulte [Roteamento](direct-routing-protocols-sip.md)Direto – protocolo SIP.

## <a name="rfc-standards"></a>Padrões de RFC

O Roteamento Direto atende aos padrões de RFC.  O SBC conectado ao Roteamento Direto também deve estar em conformidade com as seguintes RFCs (ou suas sucessores). 

### <a name="standards-applicable-to-devices-that-support-non-media-bypass-mode"></a>Padrões aplicáveis a dispositivos que são compatíveis com o modo de bypass sem mídia 

Os seguintes padrões são aplicáveis a dispositivos que só suportam o modo de bypass de fora da mídia:

- [RFC 3261 SIP:](https://tools.ietf.org/html/rfc3261)Protocolo de Iniciação de Sessão
- [RFC 3325.](https://www.ietf.org/rfc/rfc3325) Extensão privada para o Protocolo de Iniciação de Sessão para identidade afirmada em Redes Confiáveis, seções sobre como lidar com o header de identidade de P. O Roteamento Direto envia identidade de P-Asserted com os headers de ID de Privacidade. 
- [RFC 4244](https://www.ietf.org/rfc/rfc4244.txt) Uma extensão do PROTOCOLO (Session Initiation Protocol) para obter informações de histórico necessárias. Confira também: Roteamento da descrição do protocolo SIP para obter mais informações.
- [RFC 3892](https://www.ietf.org/rfc/rfc3892.txt) O mecanismo de Referred-By de Iniciação Referred-By Sessão
- [RFC 3891](https://www.ietf.org/rfc/rfc3891.txt) O protocolo SIP (Session Initiation Protocol) "Substitui" Header 
- [RFC 6337](https://tools.ietf.org/html/rfc6337) Uso do Protocolo SIP do Modelo de Oferta/Resposta.
  Confira a seção "Desvios de RFC".
- [RFC 3711](https://tools.ietf.org/html/rfc3711) e [RFC 4771.](https://tools.ietf.org/html/rfc4771) Proteja o tráfego RTP usando SRTP. O SBC deve ser capaz de estabelecer chaves usando o SDES. 
- [RFC 8035](https://www.ietf.org/rfc/rfc8035.txt) Esclarecimentos de protocolo SDP (Session Description Protocol) para Multiplexing RTP/RTCP

### <a name="standards-applicable-to-devices-that-support-media-bypass-mode"></a>Padrões aplicáveis a dispositivos que são compatíveis com o modo de bypass de mídia

Além dos padrões listados conforme aplicável ao modo não bypass, os seguintes padrões são usados para o modo de bypass de mídia:

- [RFC 5245 Interactive Connectivity Bypass (ICE) para bypass de mídia.](https://tools.ietf.org/html/rfc5245)  O SBC deve dar suporte ao seguinte:
  - ICE Lite - os clientes do Teams são clientes ICE completos
  - [ICE reinicia.](https://tools.ietf.org/html/rfc5245#section-9.1.1.1) Veja mais sobre as reinicializações ice e exemplos de caso de uso no Ice Restart: Ignorar chamada de mídia transferida para um ponto de extremidade que não dá suporte a bypass de mídia   
- [Controle de chamada SIP (RFC RFC RFC 5589 Session Initiation Protocol) – Transferência.](https://tools.ietf.org/html/rfc5589) 
- [RFC 3960 Early Media](https://tools.ietf.org/html/rfc3960)e Geração de Tom de Toque no PROTOCOLO ,confira as seções 3.1, Forking e 3.2, Geração de Tom de Toque 
- [RFC 5389 Session Traversal Utilities for NAT (STUN)](https://tools.ietf.org/html/rfc5389)
- [RFC 5766 Traversal Using Relays around NAT (TURN): Relay Extensions to Session Traversal Utilities for NAT (STUN)](https://tools.ietf.org/html/rfc5766)

### <a name="standards-applicable-to-support-conveying-location-information-to-e911-providers"></a>Padrões aplicáveis ao suporte à transmissão de informações de localização para provedores E911

- [RFC 6442, Transmissão de Local para o Protocolo de Início de Sessão](https://tools.ietf.org/html/rfc6442)

### <a name="deviations-from-the-rfcs"></a>Desvios do RFC

A tabela a seguir lista as seções das RFC(s) nas quais a implementação da Microsoft do SIP ou da pilha de mídias se desvia do padrão:

| RFC e seções | Descrição | Desvio |
| :---------------------  |:---------------------- |:-----------------------|
| [RFC 6337, seção 5.3 Espera e Currículo de Mídia](https://tools.ietf.org/html/rfc6337#section-5.3) | O RFC permite usar "a=inativo", "a=sendonly", a=rec recly" para colocar uma chamada em espera. |O proxy SIP só dá suporte a "a=inativo" e não entende se o SBC envia "a=sendonly" ou "a=rec rec
| [RFC 6337, seção 5.4 "Comportamento ao receber SDP com c=0.0.0.0.0](https://tools.ietf.org/html/rfc6337#section-5.4) | [RFC3264](https://tools.ietf.org/html/rfc3264) requer que um agente seja capaz de receber SDP com um endereço de conexão de 0.0.0.0, nesse caso isso significa que nem RTP nem RTCP devem ser enviados para o ponto. | O proxy SIP não dá suporte a essa opção. |

## <a name="operational-modes"></a>Modos operacionais

Há dois modos operacionais para Roteamento Direto:

- **Sem bypass de mídia** em que todo o tráfego RTP flui entre o cliente do Teams, os processadores de mídia e o SBC.  

- **Com o bypass de** mídia no qual todas as mídias RTP fluem entre os pontos de extremidade do Teams e o SBC. 

Observe que o tráfego SIP sempre flui por meio do proxy SIP.   
