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
# <a name="direct-routing---definitions-and-rfc-standards"></a>Roteamento Direto - Definições e padrões RFC

Este artigo descreve como o roteamento direto do sistema de Telefone Microsoft implementa protocolos padrão RFC. Este artigo destina-se a administradores de voz responsáveis pela configuração da conexão entre o SBC (Session Border Controller, controlador de borda de sessão) no local e o serviço de proxy Do Protocolo de Iniciação de Sessão (SIP).

O SBC do cliente interfaces com os seguintes componentes no backend Microsoft Teams: 

- **O proxy SIP** para sinalização. Este é o componente voltado para a Internet do Direct Routing que lida com conexões SIP (TLS) entre os SBCs e o Direct Routing.

- **Os processadores de mídia** para mídia. Este é o componente voltado para a Internet do Direct Routing que lida com o tráfego de mídia. Este componente usa protocolos SRTP e SRTCP.


Para obter mais informações sobre o Direct Routing, consulte [Sistema de Telefonia Direct Routing](direct-routing-landing-page.md).

Para obter mais informações sobre como o Direct Routing implementa o protocolo SIP, consulte [Direct Routing - Protocolo SIP](direct-routing-protocols-sip.md).

## <a name="rfc-standards"></a>Normas RFC

O Roteamento Direto está em conformidade com as normas RFC.  O SBC conectado ao Roteamento Direto também deve cumprir com os seguintes RFCs (ou seus sucessores). 

### <a name="standards-applicable-to-devices-that-support-non-media-bypass-mode"></a>Padrões aplicáveis a dispositivos que suportam o modo de bypass não-media 

Os seguintes padrões são aplicáveis a dispositivos que suportam apenas o modo de bypass não-media:

- [RFC 3261 SIP](https://tools.ietf.org/html/rfc3261): Protocolo de Iniciação de Sessão
- [RFC 3325](https://www.ietf.org/rfc/rfc3325). Extensão privada ao Protocolo de Iniciação de Sessão para identidade afirmada em redes confiáveis - seções sobre o manuseio do cabeçalho P-Asserted-Identity. O roteamento direto envia P-Asserted-Identity com cabeçalhos de ID de privacidade. 
- [RFC 4244](https://www.ietf.org/rfc/rfc4244.txt) Uma extensão do Protocolo de Iniciação de Sessão (SIP) para informações de histórico necessárias. Veja também: Roteamento SIP Protocol descrição para obter mais informações.
- [RFC 3892](https://www.ietf.org/rfc/rfc3892.txt) O protocolo de iniciação da sessão Referred-By mecanismo
- [RFC 3891](https://www.ietf.org/rfc/rfc3891.txt) O cabeçalho "Substitui" do Protocolo de Iniciação da Sessão (SIP) 
- [RFC 6337](https://tools.ietf.org/html/rfc6337) Uso do Protocolo de Iniciação de Sessão (SIP) do Modelo de Oferta/Resposta.
  Consulte a seção "Desvios do RFC".
- [RFC 3711](https://tools.ietf.org/html/rfc3711) e [RFC 4771](https://tools.ietf.org/html/rfc4771). Proteja o tráfego RTP usando sRTP. O SBC deve ser capaz de estabelecer chaves usando SDES. 
- [RFC 8035](https://www.ietf.org/rfc/rfc8035.txt) Protocolo de Descrição da Sessão (SDP) Esclarecimentos de oferta/resposta para multiplexing RTP/RTCP

### <a name="standards-applicable-to-devices-that-support-media-bypass-mode"></a>Padrões aplicáveis a dispositivos que suportam o modo de desvio de mídia

Além das normas listadas como aplicáveis ao modo não-bypass, os seguintes padrões são usados para o modo de desvio de mídia:

- [RFC 5245 Interactive Connectivity Establishment (ICE) para desvio de mídia](https://tools.ietf.org/html/rfc5245).  O SBC deve apoiar o seguinte:
  - ICE Lite - os clientes Teams são clientes ice completos
  - [Restarts ICE](https://tools.ietf.org/html/rfc5245#section-9.1.1.1). Veja mais sobre o caso de uso do ICE e exemplos no ICE Restart: Chamada de bypass de mídia transferida para um ponto final que não suporta desvio de mídia   
- [RFC RFC 5589 Session Initiation Protocol (SIP) Call Control – Transfer](https://tools.ietf.org/html/rfc5589). 
- [RFC 3960 Early Media and Ringing Tone Generation in the Session Initiation Protocol (SIP)](https://tools.ietf.org/html/rfc3960), veja as seções 3.1, Forking e 3.2, Ringing Tone Generation 
- [RFC 5389 Session Traversal Utilities for NAT (STUN)](https://tools.ietf.org/html/rfc5389)
- [RFC 5766 Travessia Usando Relés em torno de NAT (TURN): Extensões de relé para utilitários transversais de sessão para NAT (STUN)](https://tools.ietf.org/html/rfc5766)

### <a name="standards-applicable-to-support-conveying-location-information-to-e911-providers"></a>Padrões aplicáveis ao suporte de transporte de informações de localização aos provedores E911

- [RFC 6442, Transporte de localização para o Protocolo de Iniciação da Sessão](https://tools.ietf.org/html/rfc6442)

### <a name="deviations-from-the-rfcs"></a>Desvios dos RFC's

A tabela a seguir lista as seções dos RFC(s) em que a implementação da microsoft do SIP ou pilha de mídia se desvia do padrão:

| RFC e seções | Descrição | desvio |
| :---------------------  |:---------------------- |:-----------------------|
| [RFC 6337, seção 5.3 Hold e Currículo de Mídia](https://tools.ietf.org/html/rfc6337#section-5.3) | O RFC permite usar "a=inativo", "a=sendonly", a=recvonly" para colocar uma chamada em espera. |O proxy SIP só suporta "a=inativo" e não entende se o SBC envia "a=sendonly" ou "a=recvonly".
| [RFC 6337, seção 5.4 "Comportamento sobre recebimento de SDP com c=0.0.0.0](https://tools.ietf.org/html/rfc6337#section-5.4) | [RFC3264](https://tools.ietf.org/html/rfc3264) requer que um agente seja capaz de receber SDP com um endereço de conexão de 0.0.0.0, nesse caso significa que nem o RTP nem o RTCP devem ser enviados para o peer. | O proxy SIP não suporta essa opção. |

## <a name="operational-modes"></a>Modos operacionais

Existem dois modos operacionais para roteamento direto:

- **Sem desvio de mídia** em que todo o tráfego RTP flui entre o cliente Teams, os processadores de mídia e o SBC.  

- **Com o desvio de mídia** em que todas as mídias RTP fluem entre os Teams pontos finais e o SBC. 

Observe que o tráfego SIP sempre flui através do proxy SIP. 

## <a name="dtmf"></a>Dtmf
O DTMF na banda não é suportado pela pilha de mídia.
