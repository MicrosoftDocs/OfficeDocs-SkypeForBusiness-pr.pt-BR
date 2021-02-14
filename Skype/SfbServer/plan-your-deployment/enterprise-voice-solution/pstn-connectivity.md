---
title: Componentes de conectividade PSTN no Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 6b2a3f7d-760f-4f09-8432-312c98a7e6b7
description: Saiba mais sobre tronco SIP e gateways PSTN para Enterprise Voice no Skype for Business Server.
ms.openlocfilehash: 6261b95906699777e62c025889d23e03d381f09d
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49813531"
---
# <a name="pstn-connectivity-components-in-skype-for-business-server"></a>Componentes de conectividade PSTN no Skype for Business Server
 
Saiba mais sobre tronco SIP e gateways PSTN para Enterprise Voice no Skype for Business Server.
  
Uma solução de VoIP em nível empresarial deve fornecer chamadas de e para a PSTN (rede telefônica pública comutada), sem redução de QoS (Qualidade de Serviço). Além disso, os usuários não devem perceber a tecnologia subjacente ao fazer e receber chamadas. Da perspectiva do usuário, uma chamada entre a infraestrutura do Enterprise Voice e a PSTN deve ser igual a qualquer outra sessão SIP.
  
Para conexões PSTN, você pode implantar um tronco SIP ou um gateway PSTN (com um PBX, também conhecido como link SIP Direto ou sem um PBX).
  
## <a name="sip-trunking"></a>Tronco SIP

Como alternativa ao uso de gateways PSTN, você pode conectar sua solução Enterprise Voice à PSTN usando o tronco SIP. O tronco SIP permite os seguintes cenários:
  
- Um usuário corporativo dentro ou fora do firewall corporativo pode fazer uma chamada local ou interurbana especificada por um número em conformidade com E.164 que é encerrado no PSTN como um serviço do provedor de serviços correspondente.
    
- Qualquer assinante do PSTN pode entrar em contato com um usuário corporativo dentro ou fora do firewall corporativo ao discar um número DID (Discagem Direta Interna) associado àquele usuário.
    
O uso dessa solução de implantação requer um provedor de serviços de tronco SIP. 
  
## <a name="pstn-gateways"></a>Gateways PSTN

Os gateways PSTN são dispositivos de terceiros que convertem a sinalização e a mídia entre a infraestrutura do Enterprise Voice e uma PSTN ou um PBX. Os gateways PSTN funcionam com o Servidor de Mediação para apresentar uma chamada PSTN ou PBX para um cliente do Enterprise Voice. O Servidor de Mediação também apresenta as chamadas dos clientes do Enterprise Voice ao gateway PSTN para roteamento para a PSTN ou o PBX. Para uma lista de parceiros que trabalham com a Microsoft para fornecer dispositivos que funcionam com o Skype for Business Server, consulte o site  [do Microsoft Unified Communications Partners](https://go.microsoft.com/fwlink/p/?linkId=202836). 
  
## <a name="private-branch-exchanges"></a>Centrais privadas de comutação telefônica

 Se você tiver uma infraestrutura de voz existente que use um PBX (central privada de com central privada), poderá usar seu PBX com o Enterprise Voice.
  
Os cenários de integração de PBX com o Enterprise Voice aceitos são:
  
- IP-PBX que oferece suporte ao desvio de mídia, com um Servidor de Mediação.
    
- IP-PBX que requer um gateway PSTN autônomo.
    
- Conexão PBX TDM, com um gateway PSTN autônomo.
    
> [!NOTE]
> O desvio de mídia não irá interoperar com cada gateway PSTN, IP-PBX e SBC. A Microsoft testou um conjunto de gateways PSTN e SBCs com parceiros certificados e realizou alguns testes com o IP-PBXs da Cisco. O bypass de mídia só é suportado com produtos e versões listados no Programa de Interoperabilidade Aberta de Comunicações [Unificadas - Lync Server.](https://go.microsoft.com/fwlink/p/?linkId=214406) 
  
Para obter detalhes sobre parceiros que oferecem soluções enterprise voice, consulte o [site do Microsoft Unified Communications Partners](https://go.microsoft.com/fwlink/p/?linkId=202836).
  
Para obter detalhes sobre parceiros que oferecem soluções de hardware do Enterprise Voice, incluindo gateways PSTN, consulte o site [do Microsoft Unified Communications Partners](https://go.microsoft.com/fwlink/p/?linkId=202836).
  

