---
title: 'Lync Server 2013: requisitos técnicos para bypass de mídia'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Technical requirements for media bypass
ms:assetid: 6162a204-0e7c-460a-8eb2-e592c6590a8a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398435(v=OCS.15)
ms:contentKeyID: 48184321
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5ad685e59616f7f2a90cc8a9d3feb5f4ea669587
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42141807"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="technical-requirements-for-media-bypass-in-lync-server-2013"></a><span data-ttu-id="c5f9c-102">Requisitos técnicos para bypass de mídia no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c5f9c-102">Technical requirements for media bypass in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c5f9c-103">_**Última modificação do tópico:** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="c5f9c-103">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="c5f9c-104">Para cada chamada à PSTN, o servidor de mediação determina se a mídia do ponto de origem do Lync pode ser enviada diretamente para um ponto de servidor de mediação sem atravessar o servidor de mediação.</span><span class="sxs-lookup"><span data-stu-id="c5f9c-104">For each call to the PSTN, the Mediation Server determines whether media from the Lync endpoint of origin can be sent directly to a Mediation Server peer without traversing the Mediation Server.</span></span> <span data-ttu-id="c5f9c-105">O par pode ser um gateway PSTN, um IP-PBX ou um SBC (Controlador de Borda de Sessão) em um ITSP (provedor de serviços de telefonia da Internet) associado ao tronco entre o Servidor de Mediação para o qual a chamada é encaminhada.</span><span class="sxs-lookup"><span data-stu-id="c5f9c-105">The peer can be a PSTN gateway, IP-PBX, or Session Border Controller (SBC) at an Internet telephony service provider (ITSP) that is associated with the trunk between the Mediation Server where the call is routed.</span></span>

<span data-ttu-id="c5f9c-106">O desvio de mídia pode ser empregado quando os seguintes requisitos são atendidos:</span><span class="sxs-lookup"><span data-stu-id="c5f9c-106">Media bypass can be employed when the following requirements are met:</span></span>

  - <span data-ttu-id="c5f9c-107">Um ponto de servidor de mediação deve suportar os recursos necessários para o bypass de mídia, o mais importante é a capacidade de lidar com várias respostas bifurcadas (conhecidas como "caixas de diálogo iniciais").</span><span class="sxs-lookup"><span data-stu-id="c5f9c-107">A Mediation Server peer must support the necessary capabilities for media bypass, the most important being the ability to handle multiple forked responses (known as “early dialogs”).</span></span> <span data-ttu-id="c5f9c-108">Contate o fabricante do seu gateway ou PBX ou seu ITSP para obter o valor do número máximo de caixas de diálogo iniciais que o gateway, o PBX ou o SBC pode aceitar.</span><span class="sxs-lookup"><span data-stu-id="c5f9c-108">Contact the manufacturer of your gateway or PBX, or your ITSP, to obtain the value for the maximum number of early dialogs that the gateway, PBX, or SBC can accept.</span></span>

  - <span data-ttu-id="c5f9c-109">O ponto do servidor de mediação deve aceitar o tráfego de mídia diretamente dos pontos de extremidade do Lync.</span><span class="sxs-lookup"><span data-stu-id="c5f9c-109">The Mediation Server peer must accept media traffic directly from Lync endpoints.</span></span> <span data-ttu-id="c5f9c-110">Muitos ITSPs permitem que o SBC receba tráfego apenas do servidor de mediação.</span><span class="sxs-lookup"><span data-stu-id="c5f9c-110">Many ITSPs allow their SBC to receive traffic only from the Mediation Server.</span></span> <span data-ttu-id="c5f9c-111">Entre em contato com seu ITSP para determinar se o SBC aceita tráfego de mídia diretamente dos pontos de extremidade do Lync.</span><span class="sxs-lookup"><span data-stu-id="c5f9c-111">Contact your ITSP to determine whether its SBC accepts media traffic directly from Lync endpoints.</span></span>

  - <span data-ttu-id="c5f9c-112">Os clientes do Lync e um par de servidor de mediação devem estar bem conectados, o que significa que eles estão localizados na mesma região de rede ou em sites de rede que se conectam à região em links WAN que não têm restrições de largura de banda</span><span class="sxs-lookup"><span data-stu-id="c5f9c-112">Lync clients and a Mediation Server peer must be well connected, meaning that they are either located in the same network region or at network sites that connect to the region over WAN links that have no bandwidth constraints</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="c5f9c-113">Confira também</span><span class="sxs-lookup"><span data-stu-id="c5f9c-113">See Also</span></span>


[<span data-ttu-id="c5f9c-114">Modos de bypass de mídia no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c5f9c-114">Media bypass modes in Lync Server 2013</span></span>](lync-server-2013-media-bypass-modes.md)  
[<span data-ttu-id="c5f9c-115">Bypass de mídia e controle de admissão de chamadas no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c5f9c-115">Media bypass and call admission control in Lync Server 2013</span></span>](lync-server-2013-media-bypass-and-call-admission-control.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

