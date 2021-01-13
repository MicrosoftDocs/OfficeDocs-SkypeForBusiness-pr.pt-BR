---
title: Componentes necessários para o Enterprise Voice no Skype for Business Server
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
ms.assetid: ee219976-c39a-4b2f-988d-886c339700f7
description: Um resumo dos componentes do Enterprise Voice no Skype for Business Server.
ms.openlocfilehash: 1a7f13cc171af44ecbd0f48706ec12d882e50b33
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49825821"
---
# <a name="components-required-for-enterprise-voice-in-skype-for-business-server"></a>Componentes necessários para o Enterprise Voice no Skype for Business Server
 
Um resumo dos componentes do Enterprise Voice no Skype for Business Server.
  
Para implantar o Enterprise Voice, os seguintes componentes são necessários em sua topologia. 
  
- Um ou mais Servidores de Mediação, que convertem a sinalização e, em algumas configurações, mídia entre o Skype for Business Server interno, a infraestrutura do Enterprise Voice e um gateway PSTN (rede telefônica pública comutado) ou um tronco SIP. Os Servidores de Mediação são o componente mais crucial em sua implantação do Enterprise Voice. Para obter mais informações, consulte [o componente do Servidor de Mediação no Skype for Business Server.](mediation-server.md)
    
    Os Servidores de Mediação podem ser alocados com Servidores Front-End ou instalados como servidores autônomos.
    
- Componentes de conectividade PSTN, que podem incluir troncos SIP ou gateways PSTN. Para obter mais informações, [consulte componentes de conectividade PSTN no Skype for Business Server.](pstn-connectivity.md)
    
- Servidores de Borda, que permitem o uso de recursos do Enterprise Voice por seus usuários quando eles estão fora do firewall da sua organização. 
    
    O serviço de Borda de Acesso fornece sinalização SIP para chamadas de usuários do Skype for Business que estão fora do firewall da sua organização. O Serviço de Borda A/V permite o percurso de mídia de NAT e firewalls. Um chamador que usa um cliente UC (comunicações unificadas) de fora do firewall corporativo depende do serviço de Borda A/V para chamadas individuais e de conferência.
    
    O serviço de Autenticação A/V está colocado no serviço de Borda A/V e fornece a este serviços de autenticação. Os usuários externos que tentam se conectar ao serviço de Borda A/V necessitam um token de autenticação fornecido pelo Serviço de Autenticação A/V, antes que suas chamadas possam ser feitas.
    
- Além disso, alguns componentes do Enterprise Voice são executados em Servidores Front-End. Para obter detalhes sobre esses componentes, consulte [Componentes VoIP](front-end-server-voip.md) do Servidor Front End para o Skype for Business Server
    

