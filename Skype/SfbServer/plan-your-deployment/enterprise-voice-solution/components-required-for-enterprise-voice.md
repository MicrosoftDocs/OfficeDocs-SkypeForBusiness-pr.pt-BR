---
title: Componentes necessários para Enterprise Voice no Skype for Business Server
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: ee219976-c39a-4b2f-988d-886c339700f7
description: Um resumo dos componentes Enterprise Voice de Skype for Business Server.
ms.openlocfilehash: 80fce2f32521f2d4d5e493efafebbc344cba0e26
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/04/2021
ms.locfileid: "60768519"
---
# <a name="components-required-for-enterprise-voice-in-skype-for-business-server"></a>Componentes necessários para Enterprise Voice no Skype for Business Server
 
Um resumo dos componentes Enterprise Voice de Skype for Business Server.
  
Para implantar Enterprise Voice, os seguintes componentes são necessários em sua topologia. 
  
- Um ou mais Servidores de Mediação, que traduzem a sinalização e, em algumas configurações, a mídia entre sua Skype for Business Server interna, Enterprise Voice infraestrutura e um gateway PSTN (rede telefônica pública comutado) ou um tronco SIP (Session Initiation Protocol). Os Servidores de Mediação são o componente mais importante em sua implantação Enterprise Voice segurança. Para obter mais informações, consulte [Componente do Servidor de Mediação em Skype for Business Server](mediation-server.md).
    
    Os Servidores de Mediação podem ser alocados com Servidores Front-End ou instalados como servidores autônomos.
    
- Componentes de conectividade PSTN, que podem incluir troncos SIP ou gateways PSTN. Para obter mais informações, consulte [PSTN connectivity components in Skype for Business Server](pstn-connectivity.md).
    
- Servidores de Borda, que permite o uso de recursos Enterprise Voice por seus usuários quando eles estão fora do firewall da sua organização. 
    
    O serviço de Borda de Acesso fornece sinalização SIP para chamadas Skype for Business usuários que estão fora do firewall da sua organização. O Serviço de Borda A/V permite o percurso de mídia de NAT e firewalls. Um chamador que usa um cliente UC (comunicações unificadas) de fora do firewall corporativo depende do serviço de Borda A/V para chamadas individuais e de conferência.
    
    O serviço de Autenticação A/V está colocado no serviço de Borda A/V e fornece a este serviços de autenticação. Os usuários externos que tentam se conectar ao serviço de Borda A/V necessitam um token de autenticação fornecido pelo Serviço de Autenticação A/V, antes que suas chamadas possam ser feitas.
    
- Além disso, alguns componentes Enterprise Voice são executados em Servidores Front-End. Para obter detalhes sobre esses componentes, consulte [Front End Server VoIP components for Skype for Business Server](front-end-server-voip.md)
    

