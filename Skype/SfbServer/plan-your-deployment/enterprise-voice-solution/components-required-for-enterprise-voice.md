---
title: Componentes necessários para o Enterprise Voice no Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
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
ms.assetid: ee219976-c39a-4b2f-988d-886c339700f7
description: Um resumo dos componentes Enterprise Voice no Skype for Business Server.
ms.openlocfilehash: a2e32e2301a404afd06038d438fbb62a13235d65
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41803101"
---
# <a name="components-required-for-enterprise-voice-in-skype-for-business-server"></a>Componentes necessários para o Enterprise Voice no Skype for Business Server
 
Um resumo dos componentes Enterprise Voice no Skype for Business Server.
  
Para implantar o Enterprise Voice, os seguintes componentes são necessários na sua topologia. 
  
- Um ou mais servidores de mediação, que convertem a sinalização e, em algumas configurações, mídia entre o Skype for Business Server interno, a infraestrutura do Enterprise Voice e um gateway PSTN (rede telefônica pública comutada) ou um protocolo de inicialização de sessão (SIP) trunk. Os servidores de mediação são os componentes mais cruciais na sua implantação do Enterprise Voice. Para obter mais informações, consulte [componente do servidor de mediação no Skype for Business Server](mediation-server.md).
    
    Os servidores de mediação podem ser posicionados com servidores front-end ou instalados como servidores autônomos.
    
- Componentes de conectividade PSTN, que podem incluir troncos SIP ou gateways PSTN gateways. Para obter mais informações, consulte [componentes de conectividade PSTN no Skype for Business Server](pstn-connectivity.md).
    
- Servidores de borda, que permitem o uso de recursos do Enterprise Voice pelos seus usuários quando eles estão fora do firewall da sua organização. 
    
    O serviço de borda de acesso fornece sinalização de SIP para chamadas de usuários do Skype for Business que estão fora do firewall da sua organização. O Serviço de Borda A/V permite o percurso de mídia de NAT e firewalls. Um chamador que usa um cliente UC (comunicações unificadas) de fora do firewall corporativo depende do serviço de Borda A/V para chamadas individuais e de conferência.
    
    O serviço de Autenticação A/V está colocado no serviço de Borda A/V e fornece a este serviços de autenticação. Os usuários externos que tentam se conectar ao serviço de Borda A/V necessitam um token de autenticação fornecido pelo Serviço de Autenticação A/V, antes que suas chamadas possam ser feitas.
    
- Além disso, alguns componentes do Enterprise Voice são executados em servidores front-end. Para obter detalhes sobre esses componentes, consulte [componentes de VoIP do servidor front-end para o Skype for Business Server](front-end-server-voip.md)
    

