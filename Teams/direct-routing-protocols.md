---
title: 'Roteamento direto do sistema de telefonia do Teams: definições e padrões RFC'
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 12/16/2019
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-voice
ms.reviewer: nmurav
search.appverid: MET150
f1.keywords:
- NOCSH
description: Como o Roteamento Direto do Sistema de Telefonia da Microsoft implementa protocolos padrão RFC.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 01dbd61748d14ef21a600b2e4f44a306517e46d9
ms.sourcegitcommit: 173bdbaea41893d39a951d79d050526b897044d5
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/07/2022
ms.locfileid: "67271236"
---
# <a name="direct-routing---definitions-and-rfc-standards"></a>Roteamento direto – definições e padrões RFC

Este artigo descreve como o Roteamento Direto do Sistema de Telefonia da Microsoft implementa protocolos padrão RFC. Este artigo destina-se a administradores de voz responsáveis por configurar a conexão entre o SBC (Controlador de Borda de Sessão) local e o serviço proxy SIP (Session Initiation Protocol).

As interfaces SBC do cliente com os seguintes componentes no back-end do Microsoft Teams: 

- **O proxy SIP** para sinalização. Esse é o componente voltado para a Internet do Roteamento Direto que manipula conexões SIP (TLS) entre os SBCs e o Roteamento Direto.

- **Os processadores de mídia** para mídia. Esse é o componente voltado para a Internet do Roteamento Direto que manipula o tráfego de mídia. Esse componente usa protocolos SRTP e SRTCP.


Para obter mais informações sobre Roteamento Direto, consulte [Roteamento Direto do Sistema de Telefonia](direct-routing-landing-page.md).

Para obter mais informações sobre como o Roteamento Direto implementa o protocolo SIP, consulte [Roteamento Direto – protocolo SIP](direct-routing-protocols-sip.md).

## <a name="rfc-standards"></a>Padrões RFC

O Roteamento Direto está em conformidade com os padrões RFC.  O SBC conectado ao Roteamento Direto também deve estar em conformidade com os seguintes RFCs (ou seus sucessores). 

### <a name="standards-applicable-to-devices-that-support-non-media-bypass-mode"></a>Padrões aplicáveis a dispositivos que dão suporte ao modo de bypass sem mídia 

Os seguintes padrões são aplicáveis a dispositivos que dão suporte apenas ao modo de bypass de não mídia:

- [RFC 3261 SIP](https://tools.ietf.org/html/rfc3261): Protocolo de Iniciação de Sessão
- [RFC 3325](https://www.ietf.org/rfc/rfc3325). Extensão privada para o Protocolo de Iniciação de Sessão para identidade declarada em Redes Confiáveis – Seções sobre como manipular o cabeçalho P-Asserted-Identity. O Roteamento Direto envia identidade P-Asserted com cabeçalhos de ID de privacidade. 
- [RFC 4244](https://www.ietf.org/rfc/rfc4244.txt) Uma extensão para SIP (Session Initiation Protocol) para obter informações de histórico necessárias. Consulte também: Roteamento de descrição do protocolo SIP para obter mais informações.
- [RFC 3892](https://www.ietf.org/rfc/rfc3892.txt) O mecanismo de protocolo Referred-By sessão
- [RFC 3891](https://www.ietf.org/rfc/rfc3891.txt) O cabeçalho "Replaces" do protocolo SIP 
- [RFC 6337](https://tools.ietf.org/html/rfc6337) Uso do protocolo SIP do modelo de oferta/resposta.
  Consulte a seção "Desvios do RFC".
- [RFC 3711](https://tools.ietf.org/html/rfc3711) e [RFC 4771](https://tools.ietf.org/html/rfc4771). Proteja o tráfego RTP usando SRTP. O SBC deve ser capaz de estabelecer chaves usando o SDES. 
- [RFC 8035](https://www.ietf.org/rfc/rfc8035.txt) Esclarecimentos de oferta/resposta do protocolo SDP para multiplexação RTP/RTCP

### <a name="standards-applicable-to-devices-that-support-media-bypass-mode"></a>Padrões aplicáveis a dispositivos que dão suporte ao modo de bypass de mídia

Além dos padrões listados como aplicáveis ao modo não bypass, os seguintes padrões são usados para o modo de bypass de mídia:

- [RFC 5245 INTERACTIVE Connectivity Establishment (ICE) para bypass de mídia](https://tools.ietf.org/html/rfc5245).  O SBC deve dar suporte ao seguinte:
  - ICE Lite – os clientes do Teams são clientes ICE completos
  - [O ICE é reiniciado](https://tools.ietf.org/html/rfc5245#section-9.1.1.1). Veja mais sobre o caso de uso de reinicializações do ICE e exemplos em Reinicialização do ICE: chamada de bypass de mídia transferida para um ponto de extremidade que não dá suporte a bypass de mídia   
- [Controle de chamada SIP (Protocolo de Iniciação de Sessão) RFC RFC 5589 – Transferência](https://tools.ietf.org/html/rfc5589). 
- [RFC 3960 Early Media and Ringing Tone Generation in the Session Initiation Protocol (SIP)](https://tools.ietf.org/html/rfc3960), see sections 3.1, Forking, and 3.2, Ringing Tone Generation 
- [Utilitários de passagem de sessão RFC 5389 para NAT (STUN)](https://tools.ietf.org/html/rfc5389)
- [Passagem RFC 5766 usando retransmissões em torno de NAT (TURN): Extensões de retransmissão para utilitários de passagem de sessão para NAT (STUN)](https://tools.ietf.org/html/rfc5766)

### <a name="standards-applicable-to-support-conveying-location-information-to-e911-providers"></a>Padrões aplicáveis para dar suporte ao transporte de informações de localização para provedores E911

- [RFC 6442, Transporte de Localização para o Protocolo de Iniciação de Sessão](https://tools.ietf.org/html/rfc6442)

### <a name="deviations-from-the-rfcs"></a>Desvios do RFC

A tabela a seguir lista as seções das RFC(s) nas quais a implementação da Microsoft do SIP ou da pilha de mídia se desvia do padrão:

| RFC e seções | Descrição | Desvio |
| :---------------------  |:---------------------- |:-----------------------|
| [RFC 6337, seção 5.3 Retenção e Retomada de Mídia](https://tools.ietf.org/html/rfc6337#section-5.3) | O RFC permite usar "a=inactive", "a=sendonly", a=recvonly" para colocar uma chamada em espera. |O proxy SIP só dá suporte a "a=inativo" e não entende se o SBC envia "a=sendonly" ou "a=recvonly".
| [RFC 6337, seção 5.4 "Comportamento ao receber SDP com c=0.0.0.0](https://tools.ietf.org/html/rfc6337#section-5.4) | [RFC3264](https://tools.ietf.org/html/rfc3264) requer que um agente seja capaz de receber SDP com um endereço de conexão 0.0.0.0, caso em que isso significa que nem RTP nem RTCP devem ser enviados para o par. | O proxy SIP não dá suporte a essa opção. |

## <a name="operational-modes"></a>Modos operacionais

Há dois modos operacionais para Roteamento Direto:

- **Sem bypass de mídia** no qual todo o tráfego RTP flui entre o cliente do Teams, os processadores de mídia e o SBC.  

- **Com o bypass de mídia** no qual todas as mídias RTP fluem entre os pontos de extremidade do Teams e o SBC. 

Observe que o tráfego SIP sempre flui por meio do proxy SIP. 

## <a name="dtmf"></a>DTMF
Não há suporte para DTMF em banda na pilha de mídia.
