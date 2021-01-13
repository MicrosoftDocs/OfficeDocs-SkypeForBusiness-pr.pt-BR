---
title: Roteamento entre troncos no Skype for Business Server
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
ms.assetid: f687a548-1f2e-48ed-9745-a13dc1f3698f
description: Saiba como o Skype for Business Server Enterprise Voice oferece suporte ao roteamento entre troncos.
ms.openlocfilehash: fc03f0df530be12ad1d08148850c11d8f92a2791
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49825591"
---
# <a name="inter-trunk-routing-in-skype-for-business-server"></a>Roteamento entre troncos no Skype for Business Server
 
Saiba como o Skype for Business Server Enterprise Voice oferece suporte ao roteamento entre troncos.
  
O Skype for Business Server fornece gerenciamento básico de sessão por meio do suporte ao roteamento entre confianças. Isso permite que o Skype for Business Server forneça funcionalidades de controle de chamada para sistemas de telefonia downstream. O roteamento entre troncos pode interconectar um IP-PBX a um gateway de rede de telefone pública comutada (PSTN) de forma que as chamadas de um telefone de central privada de comutação telefônica (PBX) possam ser encaminhadas para o PSTN, e as chamas PSTN de entrada possam ser encaminhadas para um telefone PBX. Da mesma forma, o Skype for Business Server pode interconectar dois ou mais sistemas IP-PBX para que as chamadas possam ser feitas e recebidas entre telefones PBX de diferentes sistemas IP-PBX. 
  
A figura a seguir ilustra o Skype for Business Server fornecendo interconectividade entre um gateway PSTN e um IP-PBX.
  
![Lync Server conectando o gateway PSTN/diagrama IP-PBX](../../media/inter_trunk01.jpg)
  
A próxima figura ilustra a conexão do Skype for Business Server com dois sistemas IP-PBX.
  
![Diagrama de sistemas IP-PAX de interconexão do Lync Server](../../media/inter_trunk02.jpg)
  

