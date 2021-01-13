---
title: Roteamento entre troncos no Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: 'O Skype for Business Server fornece gerenciamento básico de sessão por meio do suporte ao roteamento entre confianças. '
ms.openlocfilehash: d509b4f9de489e65ed8443fd1aad92e24363fb55
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49814121"
---
# <a name="inter-trunk-routing-in-skype-for-business-server"></a><span data-ttu-id="d136b-103">Roteamento entre troncos no Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="d136b-103">Inter-trunk routing in Skype for Business Server</span></span>

<span data-ttu-id="d136b-104">O Skype for Business Server fornece gerenciamento básico de sessão por meio do suporte ao roteamento entre confianças.</span><span class="sxs-lookup"><span data-stu-id="d136b-104">Skype for Business Server provides basic session management through the support of intertrunk routing.</span></span> <span data-ttu-id="d136b-105">Esse recurso permite que o Skype for Business Server forneça funcionalidades de controle de chamada para sistemas de telefonia downstream.</span><span class="sxs-lookup"><span data-stu-id="d136b-105">This capability enables Skype for Business Server to provide call control functionalities to downstream telephony systems.</span></span> <span data-ttu-id="d136b-106">O roteamento entre troncos pode interconectar um IP-PBX a um gateway de rede de telefone pública comutada (PSTN) de forma que as chamadas de um telefone de central privada de comutação telefônica (PBX) possam ser encaminhadas para o PSTN, e as chamas PSTN de entrada possam ser encaminhadas para um telefone PBX.</span><span class="sxs-lookup"><span data-stu-id="d136b-106">Intertrunk routing can interconnect an IP-PBX to a public switched telephone network (PSTN) gateway so that calls from a private branch exchange (PBX) phone can be routed to the PSTN, and incoming PSTN calls can be routed to a PBX phone.</span></span> <span data-ttu-id="d136b-107">Da mesma forma, o Skype for Business Server pode interconectar dois ou mais sistemas IP-PBX para que as chamadas possam ser feitas e recebidas entre telefones PBX de diferentes sistemas IP-PBX.</span><span class="sxs-lookup"><span data-stu-id="d136b-107">Similarly, Skype for Business Server can interconnect two or more IP-PBX systems so that calls can be placed and received between PBX phones from the different IP-PBX systems.</span></span> 


<span data-ttu-id="d136b-108">A figura a seguir ilustra o Skype for Business Server fornecendo interconectividade entre um gateway PSTN e um IP-PBX.</span><span class="sxs-lookup"><span data-stu-id="d136b-108">The following figure illustrates Skype for Business Server providing interconnectivity between a PSTN gateway and an IP-PBX.</span></span>

![Interconexão entre um gateway PSTN e um IP-PBX](../../media/pstn-gateway-ip-pbx.jpg)

<span data-ttu-id="d136b-110">A próxima figura ilustra o Skype for Business Server conectando dois sistemas IP-PBX.</span><span class="sxs-lookup"><span data-stu-id="d136b-110">The next figure illustrates Skype for Business Server connecting two IP-PBX systems.</span></span>

![Skype for Business Server conectando dois sistemas IP-PGX](../../media/two-ip-pbx-systems.jpg)

