---
title: Roteamento intertronco no Skype para Business Server
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 'Skype para Business Server fornece gerenciamento de sessão básica por meio do suporte de roteamento entre troncos. '
ms.openlocfilehash: 66ee1f0cb9e37587d3c581b895528e27e7fad6c0
ms.sourcegitcommit: 5576463b0295e48e0506f7e4b44006ffc0b38a95
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/10/2018
ms.locfileid: "27222811"
---
# <a name="inter-trunk-routing-in-skype-for-business-server"></a><span data-ttu-id="8b7de-103">Roteamento intertronco no Skype para Business Server</span><span class="sxs-lookup"><span data-stu-id="8b7de-103">Inter-trunk routing in Skype for Business Server</span></span>

<span data-ttu-id="8b7de-104">Skype para Business Server fornece gerenciamento de sessão básica por meio do suporte de roteamento entre troncos.</span><span class="sxs-lookup"><span data-stu-id="8b7de-104">Skype for Business Server provides basic session management through the support of intertrunk routing.</span></span> <span data-ttu-id="8b7de-105">Essa capacidade permite Skype para Business Server fornecer funcionalidades de controle de chamada aos sistemas de telefonia de downstream.</span><span class="sxs-lookup"><span data-stu-id="8b7de-105">This capability enables Skype for Business Server to provide call control functionalities to downstream telephony systems.</span></span> <span data-ttu-id="8b7de-106">O roteamento entre troncos pode interconectar um IP-PBX a um gateway de rede de telefone pública comutada (PSTN) de forma que as chamadas de um telefone de central privada de comutação telefônica (PBX) possam ser encaminhadas para o PSTN, e as chamas PSTN de entrada possam ser encaminhadas para um telefone PBX.</span><span class="sxs-lookup"><span data-stu-id="8b7de-106">Intertrunk routing can interconnect an IP-PBX to a public switched telephone network (PSTN) gateway so that calls from a private branch exchange (PBX) phone can be routed to the PSTN, and incoming PSTN calls can be routed to a PBX phone.</span></span> <span data-ttu-id="8b7de-107">Da mesma forma, Skype para Business Server pode interconexão dois ou mais sistemas IP-PBX para que as chamadas podem ser colocadas e recebidas em telefones PBX dos diferentes sistemas IP-PBX.</span><span class="sxs-lookup"><span data-stu-id="8b7de-107">Similarly, Skype for Business Server can interconnect two or more IP-PBX systems so that calls can be placed and received between PBX phones from the different IP-PBX systems.</span></span> 


<span data-ttu-id="8b7de-108">A figura a seguir ilustra o Skype para Business Server fornecendo interconectividade entre um gateway PSTN e um IP-PBX.</span><span class="sxs-lookup"><span data-stu-id="8b7de-108">The following figure illustrates Skype for Business Server providing interconnectivity between a PSTN gateway and an IP-PBX.</span></span>

![Interconectividade entre um gateway PSTN e um IP-PBX](../../media/pstn-gateway-ip-pbx.jpg)

<span data-ttu-id="8b7de-110">A próxima figura ilustra o Skype para Business Server conectando dois sistemas IP-PBX.</span><span class="sxs-lookup"><span data-stu-id="8b7de-110">The next figure illustrates Skype for Business Server connecting two IP-PBX systems.</span></span>

![Skype para Business Server conectando dois sistemas IP-PGX](../../media/two-ip-pbx-systems.jpg)

