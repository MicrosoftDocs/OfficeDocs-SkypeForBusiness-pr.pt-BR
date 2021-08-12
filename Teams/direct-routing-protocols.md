---
title: 'Teams roteamento direto do sistema de telefonia: definições e padrões RFC'
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
description: Como Telefone Microsoft Roteamento Direto do Sistema implementa protocolos padrão RFC.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 19e3b459cef954bc432f97c93c90eaa92091d27bb17c77cecc17e8699e83e65b
ms.sourcegitcommit: 2a76435beaac1e5daa647e93f693ea8672ec0135
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/11/2021
ms.locfileid: "57848056"
---
# <a name="direct-routing---definitions-and-rfc-standards"></a>Roteamento direto - definições e padrões RFC

Este artigo descreve como o Telefone Microsoft roteamento direto do sistema implementa protocolos padrão RFC. Este artigo destina-se aos administradores de voz responsáveis por configurar a conexão entre o SBC (Controlador de Borda de Sessão) local e o serviço proxy SIP (Session Initiation Protocol).

As interfaces SBC do cliente com os seguintes componentes no back-Microsoft Teams back-back: 

- **O proxy SIP** para sinalização. Esse é o componente voltado para a Internet do Roteamento Direto que lida com conexões SIP (TLS) entre os SBCs e o Roteamento Direto.

- **Os processadores de mídia** para mídia. Esse é o componente voltado para a Internet do Roteamento Direto que lida com o tráfego de mídia. Esse componente usa protocolos SRTP e SRTCP.


Para obter mais informações sobre Roteamento Direto, [consulte Sistema de Telefonia Roteamento Direto.](direct-routing-landing-page.md)

Para obter mais informações sobre como o Roteamento Direto implementa o protocolo SIP, consulte [Roteamento Direto - protocolo SIP](direct-routing-protocols-sip.md).

## <a name="rfc-standards"></a>Padrões RFC

O Roteamento Direto está em conformidade com os padrões RFC.  O SBC conectado ao Roteamento Direto também deve estar em conformidade com os seguintes RFCs (ou seus sucessores). 

### <a name="standards-applicable-to-devices-that-support-non-media-bypass-mode"></a>Padrões aplicáveis a dispositivos que suportam o modo de bypass sem mídia 

Os seguintes padrões são aplicáveis a dispositivos que suportam apenas o modo de desvio de mídia:

- [RFC 3261 SIP](https://tools.ietf.org/html/rfc3261): Protocolo de Iniciação de Sessão
- [RFC 3325](https://www.ietf.org/rfc/rfc3325). Extensão privada para o Protocolo de Iniciação de Sessão para identidade afirmada em Redes Confiáveis-- Seções sobre como manipular o header P-Asserted-Identity. O Roteamento Direto envia P-Asserted-Identity com headers de ID de Privacidade. 
- [RFC 4244](https://www.ietf.org/rfc/rfc4244.txt) Uma extensão para SIP (Session Initiation Protocol) para informações de histórico necessárias. Consulte também: Roteamento de descrição do Protocolo SIP para obter mais informações.
- [RFC 3892](https://www.ietf.org/rfc/rfc3892.txt) O mecanismo de Referred-By de iniciação de sessão
- [RFC 3891](https://www.ietf.org/rfc/rfc3891.txt) O Protocolo de Iniciação de Sessão (SIP) "Substitui" o Header 
- [RFC 6337](https://tools.ietf.org/html/rfc6337) Uso do Sip (Protocolo de Iniciação de Sessão) do modelo de oferta/resposta.
  Consulte a seção "Desvios de RFC".
- [RFC 3711](https://tools.ietf.org/html/rfc3711) e [RFC 4771](https://tools.ietf.org/html/rfc4771). Proteja o tráfego RTP usando SRTP. O SBC deve ser capaz de estabelecer chaves usando o SDES. 
- [RFC 8035](https://www.ietf.org/rfc/rfc8035.txt) Protocolo de Descrição da Sessão (SDP) Esclarecimentos de oferta/resposta para multiplexação RTP/RTCP

### <a name="standards-applicable-to-devices-that-support-media-bypass-mode"></a>Padrões aplicáveis a dispositivos que suportam o modo de bypass de mídia

Além dos padrões listados como aplicáveis ao modo não bypass, os seguintes padrões são usados para o modo de bypass de mídia:

- [RFC 5245 Interactive Connectivity Establishment (ICE) para bypass de mídia.](https://tools.ietf.org/html/rfc5245)  O SBC deve dar suporte ao seguinte:
  - ICE Lite - os clientes Teams são clientes ICE completos
  - [O ICE reinicia](https://tools.ietf.org/html/rfc5245#section-9.1.1.1). Consulte mais em Reinicializações de ICE use case e exemplos em Ice Restart: Chamada de desvio de mídia transferida para um ponto de extremidade que não dá suporte a bypass de mídia   
- Controle de chamada SIP (Protocolo de Iniciação de [Sessão) RFC RFC 5589 – Transfer](https://tools.ietf.org/html/rfc5589). 
- [RFC 3960 Early Media and Ringing Tone Generation in the Session Initiation Protocol (SIP),](https://tools.ietf.org/html/rfc3960)see sections 3.1, Forking, and 3.2, Ringing Tone Generation 
- [Utilitários de Translúção de Sessão RFC 5389 para NAT (STUN)](https://tools.ietf.org/html/rfc5389)
- [RFC 5766 Traversal Using Relays around NAT (TURN): Relay Extensions to Session Traversal Utilities for NAT (STUN)](https://tools.ietf.org/html/rfc5766)

### <a name="standards-applicable-to-support-conveying-location-information-to-e911-providers"></a>Padrões aplicáveis para dar suporte a informações de local de transporte para provedores E911

- [RFC 6442, Transporte de Local para o Protocolo de Iniciação de Sessão](https://tools.ietf.org/html/rfc6442)

### <a name="deviations-from-the-rfcs"></a>Desvios do RFC

A tabela a seguir lista as seções dos RFC(s) em que a implementação da Microsoft do SIP ou da pilha de mídia se desvia do padrão:

| RFC e seções | Descrição | Desvio |
| :---------------------  |:---------------------- |:-----------------------|
| [RFC 6337, seção 5.3 Hold e Resume of Media](https://tools.ietf.org/html/rfc6337#section-5.3) | RFC permite usar "a=inativo", "a=sendonly", a=recvonly" para colocar uma chamada em espera. |O proxy SIP só dá suporte a "a=inativo" e não entende se o SBC envia "a=sendonly" ou "a=recvonly".
| [RFC 6337, seção 5.4 "Comportamento no recebimento de SDP com c=0,0.0.0](https://tools.ietf.org/html/rfc6337#section-5.4) | [RFC3264](https://tools.ietf.org/html/rfc3264) exige que um agente seja capaz de receber SDP com um endereço de conexão de 0.0.0.0, nesse caso significa que nem RTP nem RTCP devem ser enviados para o par. | O proxy SIP não dá suporte a essa opção. |

## <a name="operational-modes"></a>Modos operacionais

Há dois modos operacionais para Roteamento Direto:

- **Sem bypass de mídia** no qual todo o tráfego RTP flui entre o cliente Teams, os processadores de mídia e o SBC.  

- **Com o bypass de mídia** no qual todas as mídias RTP fluem entre os Teams e o SBC. 

Observe que o tráfego SIP sempre flui por meio do proxy SIP. 

## <a name="dtmf"></a>DTMF
A DTMF em banda não é suportada pela pilha de mídia.
