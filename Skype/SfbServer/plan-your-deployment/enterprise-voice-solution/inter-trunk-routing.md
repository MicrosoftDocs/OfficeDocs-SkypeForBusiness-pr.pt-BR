---
title: Roteamento intertronco no Skype para Business Server
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
ms.assetid: f687a548-1f2e-48ed-9745-a13dc1f3698f
description: Saiba como Skype para Business Server Enterprise Voice oferece suporte ao roteamento intertronco.
ms.openlocfilehash: c8c4232bbb4bb2007aa7d01bce1d26a7c5dd6901
ms.sourcegitcommit: 940cb253923e3537cb7fb4d7ce875ed9bfbb72db
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/07/2018
ms.locfileid: "23886155"
---
# <a name="inter-trunk-routing-in-skype-for-business-server"></a>Roteamento intertronco no Skype para Business Server
 
Saiba como Skype para Business Server Enterprise Voice oferece suporte ao roteamento intertronco.
  
Skype para Business Server fornece gerenciamento de sessão básica por meio do suporte de roteamento entre troncos. Isso permite que o Skype para Business Server fornecer funcionalidades de controle de chamada aos sistemas de telefonia de downstream. O roteamento entre troncos pode interconectar um IP-PBX a um gateway de rede de telefone pública comutada (PSTN) de forma que as chamadas de um telefone de central privada de comutação telefônica (PBX) possam ser encaminhadas para o PSTN, e as chamas PSTN de entrada possam ser encaminhadas para um telefone PBX. Da mesma forma, Skype para Business Server pode interconexão dois ou mais sistemas IP-PBX para que as chamadas podem ser colocadas e recebidas em telefones PBX dos diferentes sistemas IP-PBX. 
  
A figura a seguir ilustra o Skype para Business Server fornecendo interconectividade entre um gateway PSTN e um IP-PBX.
  
![Diagrama do gateway PSTN de conexão/IP-PBX do Lync Server](../../media/inter_trunk01.jpg)
  
A próxima figura ilustra o Skype para Business Server conectando dois sistemas IP-PBX.
  
![Diagrama de sistemas IP-PAX de interconexão do Lync Server](../../media/inter_trunk02.jpg)
  

