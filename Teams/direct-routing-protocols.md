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
description: Protocolos de roteamento direto
appliesto:
- Microsoft Teams
ms.openlocfilehash: a470c402ebfd4e70955f4e864d45dbaaca476dfd
ms.sourcegitcommit: 89106cfda0d900d8be541943b7d1537bc69ed57f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/16/2019
ms.locfileid: "40065621"
---
# <a name="direct-routing---definitions-and-rfc-standards"></a>Definições de roteamento direto e padrões RFC

Este artigo descreve como o roteamento direto do sistema de telefone da Microsoft implementa protocolos padrão RFC. Este artigo destina-se a administradores de voz responsáveis por configurar a conexão entre o controlador de borda de sessão local (SBC) e o serviço de proxy SIP (protocolo de inicialização de sessão).

As interfaces SBC do cliente com os seguintes componentes no backend do Microsoft Teams: 

- **O proxy SIP** para sinalização. Esse é o componente de roteamento direto da Internet que manipula conexões SIP (TLS) entre o SBCs e o roteamento direto.

- **Os processadores de mídia** para mídia. Esse é o componente de roteamento direto para a Internet que manipula o tráfego de mídia. Esse componente usa protocolos SRTP e SRTCP.


Para obter mais informações sobre roteamento direto, consulte [Roteamento direto do sistema telefônico](direct-routing-landing-page.md).

Para obter mais informações sobre como o roteamento direto implementa o protocolo SIP, consulte [protocolo Routing-SIP direto](direct-routing-protocols-sip.md).

## <a name="rfc-standards"></a>Padrões RFC

O roteamento direto está em conformidade com os padrões RFC.  O SBC conectado ao roteamento direto também deve estar em conformidade com as seguintes RFCs (ou seus sucessores). 

### <a name="standards-applicable-to-devices-that-support-non-media-bypass-mode"></a>Padrões aplicáveis a dispositivos que dão suporte ao modo de bypass sem mídia 

Os seguintes padrões são aplicáveis aos dispositivos que dão suporte apenas ao modo de bypass de não mídia:

- [RFC 3261 SIP](https://tools.ietf.org/html/rfc3261): protocolo de início de sessão
- [RFC 3325](https://www.ietf.org/rfc/rfc3325). Extensão particular para o protocolo de início de sessão para identidade declarada em redes confiáveis – seções sobre manipulação de cabeçalho de identidade com P-declarada. O roteamento direto envia identidade P-declarada com cabeçalhos de ID de privacidade. 
- [RFC 4244](https://www.ietf.org/rfc/rfc4244.txt) Uma extensão do protocolo de iniciação de sessão (SIP) para informações necessárias do histórico. Consulte também: Descrição do protocolo SIP de roteamento para obter mais informações.
- [RFC 3892](https://www.ietf.org/rfc/rfc3892.txt) O protocolo de início de sessão referido pelo mecanismo
- [RFC 3891](https://www.ietf.org/rfc/rfc3891.txt) O cabeçalho "substitui" do protocolo de iniciação de sessão (SIP) 
- [RFC 6337](https://tools.ietf.org/html/rfc6337) Uso do protocolo SIP do modelo de oferta/resposta.
  Consulte a seção "desvios da RFC".
- [Rfc 3711](https://tools.ietf.org/html/rfc3711) e [RFC 4771](https://tools.ietf.org/html/rfc4771). Proteger o tráfego RTP usando o SRTP. O SBC deve ser capaz de estabelecer chaves usando SDES. 
- [RFC 8035](https://www.ietf.org/rfc/rfc8035.txt) O protocolo de descrição de sessão (SDP) oferece/soluciona esclarecimentos para multiplexação RTP/RTCP

### <a name="standards-applicable-to-devices-that-support-media-bypass-mode"></a>Padrões aplicáveis a dispositivos que dão suporte ao modo de bypass de mídia

Além dos padrões listados como aplicáveis ao modo não bypass, os seguintes padrões são usados para o modo de bypass de mídia:

- O [estabelecimento da RFC 5245 Interactive Connectivity (ICE) para bypass de mídia](https://tools.ietf.org/html/rfc5245).  O SBC deve oferecer suporte para o seguinte:
  - ICE Lite – os clientes do teams são clientes ICE completos
  - [Reinícios do Ice](https://tools.ietf.org/html/rfc5245#section-9.1.1.1). Veja mais em reinícios do ICE e exemplos de uso na reinicialização do ICE: chamadas para ignorar mídia transferidas para um ponto de extremidade que não é compatível com o bypass de mídia   
- [Controle de chamada SIP rfc 5589 Session Initiation Protocol (SIP) – transferir](https://tools.ietf.org/html/rfc5589). 
- [A mídia de início rápido da RFC 3960 e a geração de Tom de toque no protocolo de iniciação de sessão (SIP)](https://tools.ietf.org/html/rfc3960), consulte seções 3,1, bifurcação e 3,2, geração de Tom de toque 
- [Utilitários de passagem de sessão RFC 5389 para NAT (STUN)](https://tools.ietf.org/html/rfc5389)
- [Passagem RFC 5766 usando retransmissões em torno de NAT (ativar): extensões de retransmissão para utilitários de passagem de sessão para NAT (STUN)](https://tools.ietf.org/html/rfc5766)

### <a name="standards-applicable-to-support-conveying-location-information-to-e911-providers"></a>Padrões aplicáveis ao suporte transmitir informações de localização a provedores de E911

- [RFC 6442, a transmissão de localização para o protocolo de início de sessão](https://tools.ietf.org/html/rfc6442)

### <a name="deviations-from-the-rfcs"></a>Desvios da RFC

A tabela a seguir lista as seções da (s) RFC (s) nas quais a implementação da Microsoft do SIP ou da pilha de mídia se desvia do padrão:

| RFC e seções | Descrição | Desvio |
| :---------------------  |:---------------------- |:-----------------------|
| [RFC 6337, seção 5,3 espera e retomada da mídia](https://tools.ietf.org/html/rfc6337#section-5.3) | A RFC permite usar "a = inativo", "a = sendonly", a = recvonly "para colocar uma chamada em espera. |O proxy SIP só dá suporte a "a = inativo" e não entende se o SBC envia "a = sendonly" ou "a = recvonly".
| [RFC 6337, seção 5,4 "comportamento no recebimento de SDP com c = 0.0.0.0](https://tools.ietf.org/html/rfc6337#section-5.4) | [RFC3264](https://tools.ietf.org/html/rfc3264) requer que um agente seja capaz de receber o SDP com um endereço de conexão de 0.0.0.0, nesse caso significa que nem RTP nem RTCP devem ser enviados para o par. | O proxy SIP não dá suporte a essa opção. |

## <a name="operational-modes"></a>Modos operacionais

Há dois modos operacionais para roteamento direto:

- **Sem bypass de mídia** , em que todo o tráfego RTP flui entre o cliente do Teams, os processadores de mídia e o SBC.  

- **Com bypass de mídia** , em que todos os fluxos de mídia RTP entre os pontos de extremidade do Teams e o SBC. 

Observe que o tráfego SIP sempre flui pelo proxy SIP.   
