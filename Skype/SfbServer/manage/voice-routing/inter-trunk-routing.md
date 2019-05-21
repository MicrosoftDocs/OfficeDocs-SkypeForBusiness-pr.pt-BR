---
title: Roteamento inter-trunk no Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 'O Skype for Business Server oferece gerenciamento de sessão básico por meio do suporte a roteamento de intertronco. '
ms.openlocfilehash: 2c5438f78da78870a5dae8c697d4d30d19a316ce
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34274965"
---
# <a name="inter-trunk-routing-in-skype-for-business-server"></a><span data-ttu-id="dee39-103">Roteamento inter-trunk no Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="dee39-103">Inter-trunk routing in Skype for Business Server</span></span>

<span data-ttu-id="dee39-104">O Skype for Business Server oferece gerenciamento de sessão básico por meio do suporte a roteamento de intertronco.</span><span class="sxs-lookup"><span data-stu-id="dee39-104">Skype for Business Server provides basic session management through the support of intertrunk routing.</span></span> <span data-ttu-id="dee39-105">Esse recurso permite que o Skype for Business Server forneça funcionalidades de controle de chamadas para sistemas de telefonia downstream.</span><span class="sxs-lookup"><span data-stu-id="dee39-105">This capability enables Skype for Business Server to provide call control functionalities to downstream telephony systems.</span></span> <span data-ttu-id="dee39-106">O roteamento entre troncos pode interconectar um IP-PBX a um gateway de rede de telefone pública comutada (PSTN) de forma que as chamadas de um telefone de central privada de comutação telefônica (PBX) possam ser encaminhadas para o PSTN, e as chamas PSTN de entrada possam ser encaminhadas para um telefone PBX.</span><span class="sxs-lookup"><span data-stu-id="dee39-106">Intertrunk routing can interconnect an IP-PBX to a public switched telephone network (PSTN) gateway so that calls from a private branch exchange (PBX) phone can be routed to the PSTN, and incoming PSTN calls can be routed to a PBX phone.</span></span> <span data-ttu-id="dee39-107">Da mesma forma, o Skype for Business Server pode interconectar dois ou mais sistemas de PBX IP para que chamadas possam ser feitas e recebidas entre telefones PBX dos diferentes sistemas de IP-PBX.</span><span class="sxs-lookup"><span data-stu-id="dee39-107">Similarly, Skype for Business Server can interconnect two or more IP-PBX systems so that calls can be placed and received between PBX phones from the different IP-PBX systems.</span></span> 


<span data-ttu-id="dee39-108">A figura a seguir ilustra o Skype for Business Server que oferece interconectividade entre um gateway PSTN e um IP-PBX.</span><span class="sxs-lookup"><span data-stu-id="dee39-108">The following figure illustrates Skype for Business Server providing interconnectivity between a PSTN gateway and an IP-PBX.</span></span>

![Interconectividade entre um gateway PSTN e um IP-PBX](../../media/pstn-gateway-ip-pbx.jpg)

<span data-ttu-id="dee39-110">A próxima figura ilustra o Skype for Business Server conectando dois sistemas de PBX IP.</span><span class="sxs-lookup"><span data-stu-id="dee39-110">The next figure illustrates Skype for Business Server connecting two IP-PBX systems.</span></span>

![Skype for Business Server conectando dois sistemas de PGX de IP](../../media/two-ip-pbx-systems.jpg)

