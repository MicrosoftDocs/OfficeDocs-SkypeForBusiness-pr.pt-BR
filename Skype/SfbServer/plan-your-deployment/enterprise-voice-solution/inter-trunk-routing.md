---
title: Roteamento inter-trunk no Skype for Business Server
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
ms.assetid: f687a548-1f2e-48ed-9745-a13dc1f3698f
description: Saiba como o Skype for Business Server Enterprise Voice oferece suporte ao roteamento de inter-trunk.
ms.openlocfilehash: 85a77fea8fb414a90b556e5862c42e2c59046dec
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41802851"
---
# <a name="inter-trunk-routing-in-skype-for-business-server"></a>Roteamento inter-trunk no Skype for Business Server
 
Saiba como o Skype for Business Server Enterprise Voice oferece suporte ao roteamento de inter-trunk.
  
O Skype for Business Server oferece gerenciamento de sessão básico por meio do suporte a roteamento de intertronco. Isso permite que o Skype for Business Server forneça funcionalidades de controle de chamadas para sistemas de telefonia downstream. O roteamento entre troncos pode interconectar um IP-PBX a um gateway de rede de telefone pública comutada (PSTN) de forma que as chamadas de um telefone de central privada de comutação telefônica (PBX) possam ser encaminhadas para o PSTN, e as chamas PSTN de entrada possam ser encaminhadas para um telefone PBX. Da mesma forma, o Skype for Business Server pode interconectar dois ou mais sistemas de PBX IP para que chamadas possam ser feitas e recebidas entre telefones PBX dos diferentes sistemas de IP-PBX. 
  
A figura a seguir ilustra o Skype for Business Server que oferece interconectividade entre um gateway PSTN e um IP-PBX.
  
![O servidor do Lync conectando o diagrama PSTN gateway/IP-PBX](../../media/inter_trunk01.jpg)
  
A próxima figura ilustra o Skype for Business Server conectando dois sistemas de PBX IP.
  
![Diagrama de sistemas IP-PAX de interconexão do Lync Server](../../media/inter_trunk02.jpg)
  

