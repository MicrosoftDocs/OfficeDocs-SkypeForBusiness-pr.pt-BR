---
title: Roteamento intertronco no Skype para Business Server
ms.reviewer: ''
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
ms.openlocfilehash: 281e722898655e463c3db281014421ae224c2cec
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32207297"
---
# <a name="inter-trunk-routing-in-skype-for-business-server"></a><span data-ttu-id="819ff-103">Roteamento intertronco no Skype para Business Server</span><span class="sxs-lookup"><span data-stu-id="819ff-103">Inter-trunk routing in Skype for Business Server</span></span>
 
<span data-ttu-id="819ff-104">Saiba como Skype para Business Server Enterprise Voice oferece suporte ao roteamento intertronco.</span><span class="sxs-lookup"><span data-stu-id="819ff-104">Learn how Skype for Business Server Enterprise Voice supports inter-trunk routing.</span></span>
  
<span data-ttu-id="819ff-105">Skype para Business Server fornece gerenciamento de sessão básica por meio do suporte de roteamento entre troncos.</span><span class="sxs-lookup"><span data-stu-id="819ff-105">Skype for Business Server provides basic session management through the support of intertrunk routing.</span></span> <span data-ttu-id="819ff-106">Isso permite que o Skype para Business Server fornecer funcionalidades de controle de chamada aos sistemas de telefonia de downstream.</span><span class="sxs-lookup"><span data-stu-id="819ff-106">This enables Skype for Business Server to provide call control functionalities to downstream telephony systems.</span></span> <span data-ttu-id="819ff-107">O roteamento entre troncos pode interconectar um IP-PBX a um gateway de rede de telefone pública comutada (PSTN) de forma que as chamadas de um telefone de central privada de comutação telefônica (PBX) possam ser encaminhadas para o PSTN, e as chamas PSTN de entrada possam ser encaminhadas para um telefone PBX.</span><span class="sxs-lookup"><span data-stu-id="819ff-107">Intertrunk routing can interconnect an IP-PBX to a public switched telephone network (PSTN) gateway so that calls from a private branch exchange (PBX) phone can be routed to the PSTN, and incoming PSTN calls can be routed to a PBX phone.</span></span> <span data-ttu-id="819ff-108">Da mesma forma, Skype para Business Server pode interconexão dois ou mais sistemas IP-PBX para que as chamadas podem ser colocadas e recebidas em telefones PBX dos diferentes sistemas IP-PBX.</span><span class="sxs-lookup"><span data-stu-id="819ff-108">Similarly, Skype for Business Server can interconnect two or more IP-PBX systems so that calls can be placed and received between PBX phones from the different IP-PBX systems.</span></span> 
  
<span data-ttu-id="819ff-109">A figura a seguir ilustra o Skype para Business Server fornecendo interconectividade entre um gateway PSTN e um IP-PBX.</span><span class="sxs-lookup"><span data-stu-id="819ff-109">The following figure illustrates Skype for Business Server providing interconnectivity between a PSTN gateway and an IP-PBX.</span></span>
  
![Conectando o diagrama IP-PBX/gateway PSTN do Lync Server](../../media/inter_trunk01.jpg)
  
<span data-ttu-id="819ff-111">A próxima figura ilustra o Skype para Business Server conectando dois sistemas IP-PBX.</span><span class="sxs-lookup"><span data-stu-id="819ff-111">The next figure illustrates Skype for Business Server connecting two IP-PBX systems.</span></span>
  
![Diagrama de sistemas IP-PAX de interconexão do Lync Server](../../media/inter_trunk02.jpg)
  

