---
title: Roteamento inter-trunk no Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: f687a548-1f2e-48ed-9745-a13dc1f3698f
description: Saiba como o Skype for Business Server Enterprise Voice oferece suporte ao roteamento de inter-trunk.
ms.openlocfilehash: f590463eced61cf2e8b19a27f7cfc2dd648c63c1
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34276828"
---
# <a name="inter-trunk-routing-in-skype-for-business-server"></a><span data-ttu-id="577bd-103">Roteamento inter-trunk no Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="577bd-103">Inter-trunk routing in Skype for Business Server</span></span>
 
<span data-ttu-id="577bd-104">Saiba como o Skype for Business Server Enterprise Voice oferece suporte ao roteamento de inter-trunk.</span><span class="sxs-lookup"><span data-stu-id="577bd-104">Learn how Skype for Business Server Enterprise Voice supports inter-trunk routing.</span></span>
  
<span data-ttu-id="577bd-105">O Skype for Business Server oferece gerenciamento de sessão básico por meio do suporte a roteamento de intertronco.</span><span class="sxs-lookup"><span data-stu-id="577bd-105">Skype for Business Server provides basic session management through the support of intertrunk routing.</span></span> <span data-ttu-id="577bd-106">Isso permite que o Skype for Business Server forneça funcionalidades de controle de chamadas para sistemas de telefonia downstream.</span><span class="sxs-lookup"><span data-stu-id="577bd-106">This enables Skype for Business Server to provide call control functionalities to downstream telephony systems.</span></span> <span data-ttu-id="577bd-107">O roteamento entre troncos pode interconectar um IP-PBX a um gateway de rede de telefone pública comutada (PSTN) de forma que as chamadas de um telefone de central privada de comutação telefônica (PBX) possam ser encaminhadas para o PSTN, e as chamas PSTN de entrada possam ser encaminhadas para um telefone PBX.</span><span class="sxs-lookup"><span data-stu-id="577bd-107">Intertrunk routing can interconnect an IP-PBX to a public switched telephone network (PSTN) gateway so that calls from a private branch exchange (PBX) phone can be routed to the PSTN, and incoming PSTN calls can be routed to a PBX phone.</span></span> <span data-ttu-id="577bd-108">Da mesma forma, o Skype for Business Server pode interconectar dois ou mais sistemas de PBX IP para que chamadas possam ser feitas e recebidas entre telefones PBX dos diferentes sistemas de IP-PBX.</span><span class="sxs-lookup"><span data-stu-id="577bd-108">Similarly, Skype for Business Server can interconnect two or more IP-PBX systems so that calls can be placed and received between PBX phones from the different IP-PBX systems.</span></span> 
  
<span data-ttu-id="577bd-109">A figura a seguir ilustra o Skype for Business Server que oferece interconectividade entre um gateway PSTN e um IP-PBX.</span><span class="sxs-lookup"><span data-stu-id="577bd-109">The following figure illustrates Skype for Business Server providing interconnectivity between a PSTN gateway and an IP-PBX.</span></span>
  
![O servidor do Lync conectando o diagrama PSTN gateway/IP-PBX](../../media/inter_trunk01.jpg)
  
<span data-ttu-id="577bd-111">A próxima figura ilustra o Skype for Business Server conectando dois sistemas de PBX IP.</span><span class="sxs-lookup"><span data-stu-id="577bd-111">The next figure illustrates Skype for Business Server connecting two IP-PBX systems.</span></span>
  
![Diagrama de sistemas IP-PAX de interconexão do Lync Server](../../media/inter_trunk02.jpg)
  

