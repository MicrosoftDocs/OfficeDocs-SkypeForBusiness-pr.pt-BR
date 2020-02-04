---
title: 'Lync Server 2013: Estimando uso e tráfego de voz'
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
ms.openlocfilehash: 06093893c5de9a08322e1577fbbbe6779d4209cc
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41735241"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="estimating-voice-usage-and-traffic-for-lync-server-2013"></a><span data-ttu-id="2516c-102">Estimando uso e tráfego de voz para Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2516c-102">Estimating voice usage and traffic for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2516c-103">_**Tópico da última modificação:** 2012-08-07_</span><span class="sxs-lookup"><span data-stu-id="2516c-103">_**Topic Last Modified:** 2012-08-07_</span></span>

<span data-ttu-id="2516c-104">O Microsoft Lync Server 2013, ferramenta de planejamento usa a métrica a seguir para estimar o tráfego do usuário em cada site e o número de portas necessárias para dar suporte a esse tráfego.</span><span class="sxs-lookup"><span data-stu-id="2516c-104">The Microsoft Lync Server 2013, Planning Tool uses the following metric to estimate user traffic at each site and the number of ports that are required to support that traffic.</span></span>

  - <span></span>  
    <span data-ttu-id="2516c-105">No caso de **Tráfego leve** (uma chamada PSTN por usuário por hora), calcula-se 15 usuários por porta.</span><span class="sxs-lookup"><span data-stu-id="2516c-105">For **Light traffic** (one PSTN call per user per hour), figure 15 users per port.</span></span>

  - <span></span>  
    <span data-ttu-id="2516c-106">No caso de **Tráfego médio** (duas chamadas PSTN por usuário por hora), calcula-se 10 usuários por porta.</span><span class="sxs-lookup"><span data-stu-id="2516c-106">For **Medium traffic** (2 PSTN calls per user per hour), figure 10 users per port.</span></span>

  - <span></span>  
    <span data-ttu-id="2516c-107">No caso de **Tráfego pesado** (três ou mais chamadas PSTN por usuário por hora), calcula-se 5 usuários por porta.</span><span class="sxs-lookup"><span data-stu-id="2516c-107">For **Heavy traffic** (3 or more PSTN per user calls per hour), figure 5 users per port.</span></span>

<span data-ttu-id="2516c-108">O número de portas, por sua vez, determina o número de servidores e gateways de mediação que serão necessários.</span><span class="sxs-lookup"><span data-stu-id="2516c-108">The number of ports in turn determines the number of Mediation Servers and gateways that will be required.</span></span> <span data-ttu-id="2516c-109">Os gateways de rede telefônica pública comutada (PSTN) que a maioria das organizações considera implantando o tamanho de duas portas para até 960 portas.</span><span class="sxs-lookup"><span data-stu-id="2516c-109">The public switched telephone network (PSTN) gateways that most organizations consider deploying range in size from 2 ports to as many as 960 ports.</span></span> <span data-ttu-id="2516c-110">(Ainda há gateways maiores, mas eles são usados principalmente por provedores de serviços de telefonia.)</span><span class="sxs-lookup"><span data-stu-id="2516c-110">(There are even larger gateways, but these are used mainly by telephony service providers.)</span></span>

<span data-ttu-id="2516c-p102">Por exemplo, uma organização com 10.000 usuários e tráfego médio exigiria 1000 portas. O número de gateways necessário seria igual o número total de portas necessárias, conforme determinado pela capacidade total dos gateways.</span><span class="sxs-lookup"><span data-stu-id="2516c-p102">For example, an organization with 10,000 users and medium traffic would require 1000 ports. The number of gateways required would equal the total number of ports required as determined by the total capacity of the gateways.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

