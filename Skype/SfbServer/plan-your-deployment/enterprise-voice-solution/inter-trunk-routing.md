---
title: Roteamento entre troncos no Skype for Business Server 2015
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 8/17/2015
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.custom: Strat_SB_Admin
ms.assetid: f687a548-1f2e-48ed-9745-a13dc1f3698f
description: Saiba como Skype para Business Server Enterprise Voice oferece suporte ao roteamento intertronco.
ms.openlocfilehash: 58872fccca335792ccbdf03c2c8475c328197426
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/28/2018
---
# <a name="inter-trunk-routing-in-skype-for-business-server-2015"></a><span data-ttu-id="ef100-103">Roteamento entre troncos no Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="ef100-103">Inter-trunk routing in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="ef100-104">Saiba como Skype para Business Server Enterprise Voice oferece suporte ao roteamento intertronco.</span><span class="sxs-lookup"><span data-stu-id="ef100-104">Learn how Skype for Business Server Enterprise Voice supports inter-trunk routing.</span></span>
  
<span data-ttu-id="ef100-105">Skype para Business Server fornece gerenciamento de sessão básica por meio do suporte de roteamento entre troncos.</span><span class="sxs-lookup"><span data-stu-id="ef100-105">Skype for Business Server provides basic session management through the support of intertrunk routing.</span></span> <span data-ttu-id="ef100-106">Isso permite que o Skype para Business Server fornecer funcionalidades de controle de chamada aos sistemas de telefonia de downstream.</span><span class="sxs-lookup"><span data-stu-id="ef100-106">This enables Skype for Business Server to provide call control functionalities to downstream telephony systems.</span></span> <span data-ttu-id="ef100-107">O roteamento entre troncos pode interconectar um IP-PBX a um gateway de rede de telefone pública comutada (PSTN) de forma que as chamadas de um telefone de central privada de comutação telefônica (PBX) possam ser encaminhadas para o PSTN, e as chamas PSTN de entrada possam ser encaminhadas para um telefone PBX.</span><span class="sxs-lookup"><span data-stu-id="ef100-107">Intertrunk routing can interconnect an IP-PBX to a public switched telephone network (PSTN) gateway so that calls from a private branch exchange (PBX) phone can be routed to the PSTN, and incoming PSTN calls can be routed to a PBX phone.</span></span> <span data-ttu-id="ef100-108">Da mesma forma, Skype para Business Server pode interconexão dois ou mais sistemas IP-PBX para que as chamadas podem ser colocadas e recebidas em telefones PBX dos diferentes sistemas IP-PBX.</span><span class="sxs-lookup"><span data-stu-id="ef100-108">Similarly, Skype for Business Server can interconnect two or more IP-PBX systems so that calls can be placed and received between PBX phones from the different IP-PBX systems.</span></span> 
  
<span data-ttu-id="ef100-109">A figura a seguir ilustra o Skype para Business Server fornecendo interconectividade entre um gateway PSTN e um IP-PBX.</span><span class="sxs-lookup"><span data-stu-id="ef100-109">The following figure illustrates Skype for Business Server providing interconnectivity between a PSTN gateway and an IP-PBX.</span></span>
  
![Diagrama do gateway PSTN de conexão/IP-PBX do Lync Server](../../media/inter_trunk01.jpg)
  
<span data-ttu-id="ef100-111">A próxima figura ilustra o Skype para Business Server conectando dois sistemas IP-PBX.</span><span class="sxs-lookup"><span data-stu-id="ef100-111">The next figure illustrates Skype for Business Server connecting two IP-PBX systems.</span></span>
  
![Diagrama de sistemas IP-PAX de interconexão do Lync Server](../../media/inter_trunk02.jpg)
  

