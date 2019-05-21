---
title: Componentes de conectividade PSTN no Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 6b2a3f7d-760f-4f09-8432-312c98a7e6b7
description: Saiba mais sobre o entroncamento SIP e os gateways PSTN para Enterprise Voice no Skype for Business Server.
ms.openlocfilehash: 6d11ea3204c9b924c9e700194ee04beb9a0df56c
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34276480"
---
# <a name="pstn-connectivity-components-in-skype-for-business-server"></a>Componentes de conectividade PSTN no Skype for Business Server
 
Saiba mais sobre o entroncamento SIP e os gateways PSTN para Enterprise Voice no Skype for Business Server.
  
Uma solução de VoIP em nível empresarial deve fornecer chamadas de e para a PSTN (rede telefônica pública comutada), sem redução de QoS (Qualidade de Serviço). Além disso, os usuários não devem perceber a tecnologia subjacente ao fazer e receber chamadas. Da perspectiva do usuário, uma chamada entre a infraestrutura Enterprise Voice e a PSTN deve parecer apenas com outra sessão SIP.
  
Para conexões PSTN, você pode implantar um tronco SIP ou um gateway PSTN (com um PBX, também conhecido como um link do SIP Direto, ou sem um PBX).
  
## <a name="sip-trunking"></a>Tronco SIP

Como uma alternativa para o uso de gateways PSTN, você pode conectar sua solução Enterprise Voice à PSTN usando o entroncamento SIP. O tronco SIP permite os seguintes cenários:
  
- Um usuário corporativo dentro ou fora do firewall corporativo pode fazer uma chamada local ou interurbana especificada por um número em conformidade com E.164 que é encerrado no PSTN como um serviço do provedor de serviços correspondente.
    
- Qualquer assinante do PSTN pode entrar em contato com um usuário corporativo dentro ou fora do firewall corporativo ao discar um número DID (Discagem Direta Interna) associado àquele usuário.
    
O uso dessa solução de implantação requer um provedor de serviços de tronco SIP. 
  
## <a name="pstn-gateways"></a>Gateways PSTN

Os gateways PSTN são dispositivos de terceiros que traduzem sinais e mídias entre a infraestrutura do Enterprise Voice e uma PSTN ou PBX. Os gateways PSTN funcionam com o servidor de mediação para apresentar uma PSTN ou uma chamada PBX para um cliente Enterprise Voice. O servidor de mediação também apresenta chamadas de clientes do Enterprise Voice para o gateway PSTN para roteamento para a PSTN ou PBX. Para obter uma lista dos parceiros que trabalham com a Microsoft para fornecer dispositivos que funcionam com o Skype for Business Server, consulte [o website Microsoft Unified Communications Partners](https://go.microsoft.com/fwlink/p/?linkId=202836). 
  
## <a name="private-branch-exchanges"></a>Centrais privadas de comutação telefônica

 Se você tiver uma infraestrutura de voz existente que usa um PBX (Private Branch Exchange), você pode usar seu PBX com o Enterprise Voice.
  
Os cenários de integração de Enterprise Voice-PBX compatíveis são os seguintes:
  
- PBX IP que dá suporte ao bypass de mídia, com um servidor de mediação.
    
- IP-PBX que requer um gateway PSTN autônomo.
    
- Conexão PBX TDM, com um gateway PSTN autônomo.
    
> [!NOTE]
> O bypass de mídia não irá interoperar com cada gateway PSTN, IP-PBX e SBC. A Microsoft testou um conjunto de gateways PSTN e SBCs com os parceiros certificados e realizou alguns testes com IP-PBXs da Cisco. O bypass de mídia só tem suporte com produtos e versões listados no programa de interoperabilidade [aberta da comunicação unificada-Lync Server](https://go.microsoft.com/fwlink/p/?linkId=214406). 
  
Para obter detalhes sobre os parceiros que oferecem soluções Enterprise Voice, consulte o [website Microsoft Unified Communications Partners](https://go.microsoft.com/fwlink/p/?linkId=202836).
  
Para obter detalhes sobre os parceiros que oferecem soluções de hardware de Voice Enterprise, incluindo gateways PSTN, consulte o [website Microsoft Unified Communications Partners](https://go.microsoft.com/fwlink/p/?linkId=202836).
  

