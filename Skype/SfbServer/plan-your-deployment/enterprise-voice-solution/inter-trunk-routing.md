---
title: Sobre o roteamento entre troncos no Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
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
ms.assetid: f687a548-1f2e-48ed-9745-a13dc1f3698f
description: Saiba como Skype for Business Server Enterprise Voice dá suporte ao roteamento entre troncos.
ms.openlocfilehash: 5a44f9e269985312e31d827254dd7bbfae10bcfd
ms.sourcegitcommit: 15e90083c47eb5bcb03ca80c2e83feffe67646f2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/30/2021
ms.locfileid: "58731810"
---
# <a name="about-inter-trunk-routing-in-skype-for-business-server"></a>Sobre o roteamento entre troncos Skype for Business Server
 
Saiba como Skype for Business Server Enterprise Voice dá suporte ao roteamento entre troncos.
  
Skype for Business Server fornece gerenciamento básico de sessão por meio do suporte ao roteamento entre confianças. Isso permite que Skype for Business Server funcionalidades de controle de chamada para sistemas de telefonia downstream. O roteamento entre troncos pode interconectar um IP-PBX a um gateway de rede de telefone pública comutada (PSTN) de forma que as chamadas de um telefone de central privada de comutação telefônica (PBX) possam ser encaminhadas para o PSTN, e as chamas PSTN de entrada possam ser encaminhadas para um telefone PBX. Da mesma forma, Skype for Business Server pode interconectar dois ou mais sistemas IP-PBX para que as chamadas possam ser feitas e recebidas entre telefones PBX dos diferentes sistemas IP-PBX. 
  
A figura a seguir ilustra Skype for Business Server a interconectividade entre um gateway PSTN e um IP-PBX.
  
![Lync Server conectando o gateway PSTN/diagrama IP-PBX.](../../media/inter_trunk01.jpg)
  
A próxima figura ilustra Skype for Business Server conectar dois sistemas IP-PBX.
  
![Diagrama de sistemas IP-PAX de interconexão do Lync Server.](../../media/inter_trunk02.jpg)
  

