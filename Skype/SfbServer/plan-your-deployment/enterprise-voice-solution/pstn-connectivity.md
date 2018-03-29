---
title: Componentes de conectividade de PSTN no Skype for Business Server 2015
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 12/20/2016
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.custom: Strat_SB_Admin
ms.assetid: 6b2a3f7d-760f-4f09-8432-312c98a7e6b7
description: Saiba mais sobre o tronco SIP e gateways PSTN para o Enterprise Voice no Skype para Business Server.
ms.openlocfilehash: 051066643649f9f8f872f4a2795e5ea71417d810
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/28/2018
---
# <a name="pstn-connectivity-components-in-skype-for-business-server-2015"></a>Componentes de conectividade de PSTN no Skype for Business Server 2015
 
Saiba mais sobre o tronco SIP e gateways PSTN para o Enterprise Voice no Skype para Business Server.
  
Uma solução de VoIP em nível empresarial deve fornecer chamadas de e para a PSTN (rede telefônica pública comutada), sem redução de QoS (Qualidade de Serviço). Além disso, os usuários não devem perceber a tecnologia subjacente ao fazer e receber chamadas. Da perspectiva do usuário, uma chamada entre a infraestrutura do Enterprise Voice e a PSTN deve ser semelhante a uma outra sessão SIP.
  
Para conexões PSTN, você pode implantar um tronco SIP ou um gateway PSTN (com um PBX, também conhecido como um link do SIP Direto, ou sem um PBX).
  
## <a name="sip-trunking"></a>Tronco SIP

Como alternativa ao uso de gateways PSTN, você pode conectar a solução Enterprise Voice à PSTN usando o tronco SIP. O tronco SIP permite os seguintes cenários:
  
- Um usuário corporativo dentro ou fora do firewall corporativo pode fazer uma chamada local ou interurbana especificada por um número em conformidade com E.164 que é encerrado no PSTN como um serviço do provedor de serviços correspondente.
    
- Qualquer assinante do PSTN pode entrar em contato com um usuário corporativo dentro ou fora do firewall corporativo ao discar um número DID (Discagem Direta Interna) associado àquele usuário.
    
O uso dessa solução de implantação requer um provedor de serviços de tronco SIP. 
  
## <a name="pstn-gateways"></a>Gateways PSTN

Gateways PSTN são dispositivos de terceiros que convertem a sinalização e mídia entre a infraestrutura do Enterprise Voice e uma PSTN ou um PBX. Gateways PSTN funcionam com o servidor de mediação para apresentar uma chamada PSTN ou PBX para um cliente Enterprise Voice. O servidor de mediação também apresenta chamadas de clientes do Enterprise Voice para o gateway PSTN para rotear para a PSTN ou PBX. Para obter uma lista de parceiros que trabalham com a Microsoft para fornecer dispositivos que funcionem com Skype para Business Server, consulte [o site do Microsoft Unified Communications Partners](https://go.microsoft.com/fwlink/p/?linkId=202836). 
  
## <a name="private-branch-exchanges"></a>Centrais privadas de comutação telefônica

 Se você tiver uma infraestrutura de voz existente que usa uma troca privada de comutação (PBX), você pode usar sua PBX com o Enterprise Voice.
  
Cenários de integração de PBX Enterprise Voice com suporte são os seguintes:
  
- IP-PBX que suporta bypass de mídia com um servidor de mediação.
    
- IP-PBX que requer um gateway PSTN autônomo.
    
- Conexão PBX TDM, com um gateway PSTN autônomo.
    
> [!NOTE]
> O bypass de mídia não irá interoperar com cada gateway PSTN, IP-PBX e SBC. A Microsoft testou um conjunto de gateways PSTN e SBCs com parceiros certificados e fez alguns testes com IP-PBXs da Cisco. Bypass de mídia é suportado somente com produtos e versões listadas em [Unified Communications programa de interoperabilidade aberta - Lync Server](https://go.microsoft.com/fwlink/p/?linkId=214406). 
  
Para obter detalhes sobre parceiros que oferecem soluções do Enterprise Voice, consulte o [site do Microsoft Unified Communications Partners](https://go.microsoft.com/fwlink/p/?linkId=202836).
  
Para obter detalhes sobre parceiros que oferecem soluções de hardware do Enterprise Voice, incluindo os gateways PSTN, consulte o [site do Microsoft Unified Communications Partners](https://go.microsoft.com/fwlink/p/?linkId=202836).
  

