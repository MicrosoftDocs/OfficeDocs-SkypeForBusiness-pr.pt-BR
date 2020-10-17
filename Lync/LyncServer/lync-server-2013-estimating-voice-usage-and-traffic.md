---
title: 'Lync Server 2013: estimando o uso e o tráfego de voz'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Estimating voice usage and traffic
ms:assetid: 621b08fb-f894-4d91-ac38-e443401b098b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398439(v=OCS.15)
ms:contentKeyID: 48184332
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9541619578c69a571d93d8c4960b3ecb33476027
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48531998"
---
# <a name="estimating-voice-usage-and-traffic-for-lync-server-2013"></a><span data-ttu-id="9d446-102">Estimando o uso de voz e o tráfego do Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9d446-102">Estimating voice usage and traffic for Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9d446-103">_**Última modificação do tópico:** 2012-08-07_</span><span class="sxs-lookup"><span data-stu-id="9d446-103">_**Topic Last Modified:** 2012-08-07_</span></span>

<span data-ttu-id="9d446-104">A ferramenta de planejamento do Microsoft Lync Server 2013 usa a métrica a seguir para estimar o tráfego de usuários em cada local e o número de portas necessárias para dar suporte a esse tráfego.</span><span class="sxs-lookup"><span data-stu-id="9d446-104">The Microsoft Lync Server 2013, Planning Tool uses the following metric to estimate user traffic at each site and the number of ports that are required to support that traffic.</span></span>

  - <span></span>  
    <span data-ttu-id="9d446-105">Para **Tráfego leve** (uma chamada PSTN por usuário por hora), calcula-se 15 usuários por porta</span><span class="sxs-lookup"><span data-stu-id="9d446-105">For **Light traffic** (one PSTN call per user per hour), figure 15 users per port.</span></span>

  - <span></span>  
    <span data-ttu-id="9d446-106">Para **Tráfego médio**, (duas chamadas PSTN por usuário por hora), calcula-se 10 usuários por porta</span><span class="sxs-lookup"><span data-stu-id="9d446-106">For **Medium traffic** (2 PSTN calls per user per hour), figure 10 users per port.</span></span>

  - <span></span>  
    <span data-ttu-id="9d446-107">Para **Tráfego pesado** (três ou mais chamadas PSTN por usuário por hora), calcula-se 5 usuários por porta</span><span class="sxs-lookup"><span data-stu-id="9d446-107">For **Heavy traffic** (3 or more PSTN per user calls per hour), figure 5 users per port.</span></span>

<span data-ttu-id="9d446-108">O número de portas, por sua vez, determina o número de servidores de mediação e gateways que serão necessários.</span><span class="sxs-lookup"><span data-stu-id="9d446-108">The number of ports in turn determines the number of Mediation Servers and gateways that will be required.</span></span> <span data-ttu-id="9d446-109">Os gateways PSTN (rede telefônica pública comutada) que a maioria das organizações consideram implantando intervalo em tamanho de duas portas para até 960 portas.</span><span class="sxs-lookup"><span data-stu-id="9d446-109">The public switched telephone network (PSTN) gateways that most organizations consider deploying range in size from 2 ports to as many as 960 ports.</span></span> <span data-ttu-id="9d446-110">(Há até gateways maiores, mas eles são usados principalmente por provedores de serviços de telefonia.)</span><span class="sxs-lookup"><span data-stu-id="9d446-110">(There are even larger gateways, but these are used mainly by telephony service providers.)</span></span>

<span data-ttu-id="9d446-p102">Por exemplo, uma organização com 10.000 usuários e tráfego médio exigiria 1000 portas. O número de gateways necessário seria igual o número total de portas necessárias, conforme determinado pela capacidade total dos gateways.</span><span class="sxs-lookup"><span data-stu-id="9d446-p102">For example, an organization with 10,000 users and medium traffic would require 1000 ports. The number of gateways required would equal the total number of ports required as determined by the total capacity of the gateways.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

