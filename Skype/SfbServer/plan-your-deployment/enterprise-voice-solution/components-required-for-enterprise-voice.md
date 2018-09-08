---
title: Componentes necessários para o Enterprise Voice no Skype para Business Server
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: ee219976-c39a-4b2f-988d-886c339700f7
description: Um resumo dos componentes do Enterprise Voice no Skype para Business Server.
ms.openlocfilehash: 513f116f1c92bbe931e9015bc8507b0c1f16fc1a
ms.sourcegitcommit: 940cb253923e3537cb7fb4d7ce875ed9bfbb72db
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/07/2018
ms.locfileid: "23881801"
---
# <a name="components-required-for-enterprise-voice-in-skype-for-business-server"></a>Componentes necessários para o Enterprise Voice no Skype para Business Server
 
Um resumo dos componentes do Enterprise Voice no Skype para Business Server.
  
Para implantar o Enterprise Voice, os seguintes componentes são necessários na sua topologia. 
  
- Um ou mais servidores de mediação, que convertem a sinalização e, em algumas configurações, mídia entre seu Skype interno para Business Server, a infraestrutura do Enterprise Voice e um gateway PSTN (rede) telefônica comutada pública ou um protocolo de iniciação de sessão Tronco (SIP). Os servidores de mediação são o componente mais crucial na sua implantação do Enterprise Voice. Para obter mais informações, consulte [componente de servidor de mediação em Skype para Business Server](mediation-server.md).
    
    Servidores de mediação podem ser colocados com servidores Front-End ou instalados como servidores autônomos.
    
- Componentes de conectividade PSTN, que podem incluir troncos SIP ou gateways PSTN gateways. Para obter mais informações, consulte [componentes de conectividade PSTN em Skype para Business Server](pstn-connectivity.md).
    
- Servidores de borda, que permite o uso dos recursos do Enterprise Voice pelos usuários quando eles estão fora do firewall da organização. 
    
    O serviço de borda de acesso oferece sinalização SIP para chamadas do Skype para usuários comerciais que estão fora do firewall da organização. O Serviço de Borda A/V permite o percurso de mídia de NAT e firewalls. Um chamador que usa um cliente UC (comunicações unificadas) de fora do firewall corporativo depende do serviço de Borda A/V para chamadas individuais e de conferência.
    
    O serviço de Autenticação A/V está colocado no serviço de Borda A/V e fornece a este serviços de autenticação. Os usuários externos que tentam se conectar ao serviço de Borda A/V necessitam um token de autenticação fornecido pelo Serviço de Autenticação A/V, antes que suas chamadas possam ser feitas.
    
- Além disso, alguns componentes do Enterprise Voice executados nos servidores Front-End. Para obter detalhes sobre esses componentes, consulte [componentes de VoIP de servidor Front End para Skype para Business Server](front-end-server-voip.md)
    

