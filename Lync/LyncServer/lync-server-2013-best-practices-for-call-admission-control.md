---
title: 'Lync Server 2013: práticas recomendadas para controle de admissão de chamadas'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Best practices for call admission control
ms:assetid: 97173cca-8175-4ae2-a247-eb7ef809da93
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398770(v=OCS.15)
ms:contentKeyID: 48184913
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: be270859304236b0704bc8cc9e1bc29f3e80fcb9
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48514818"
---
# <a name="best-practices-for-call-admission-control-in-lync-server-2013"></a><span data-ttu-id="a87ce-102">Práticas recomendadas para controle de admissão de chamadas no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a87ce-102">Best practices for call admission control in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a87ce-103">_**Última modificação do tópico:** 2012-09-22_</span><span class="sxs-lookup"><span data-stu-id="a87ce-103">_**Topic Last Modified:** 2012-09-22_</span></span>

<span data-ttu-id="a87ce-104">Para aprimorar o desempenho e facilitar a implantação, aplique as práticas recomendadas a seguir quando implantar o controle de admissão de chamadas:</span><span class="sxs-lookup"><span data-stu-id="a87ce-104">To enhance performance and facilitate deployment, apply the following best practices when you deploy call admission control:</span></span>

  - <span data-ttu-id="a87ce-105">Garanta que as WANs estejam adequadamente provisionadas para o tráfego de mídia atual e antecipado.</span><span class="sxs-lookup"><span data-stu-id="a87ce-105">Ensure that WANs are adequately provisioned for current and anticipated media traffic.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="a87ce-p101">É recomendável que você leve em consideração um buffer para seus limites de largura de banda. Existem cenários como condições de corrida que afetam a largura de banda total usada e podem resultar em situações em que o limite da largura de banda é excedido. Por exemplo, se duas chamadas tentarem iniciar enquanto o tráfego de mídia está alcançando um limite da largura de banda, uma delas pode ser recusada porque a outra conseguiu iniciar primeiro.</span><span class="sxs-lookup"><span data-stu-id="a87ce-p101">We recommend that you factor in a buffer to your bandwidth limits. There are scenarios such as race conditions that affect the total bandwidth used and can result in situations where the bandwidth limit is exceeded. For example, if two calls try to start while media traffic is approaching a bandwidth limit, one of them may be denied because the other managed to start first.</span></span>

    
    </div>

  - <span data-ttu-id="a87ce-109">Monitore o uso da rede e registros de detalhes de chamadas para que possa escolher configurações de CAC ótimas e atualizá-las conforme o uso da rede muda.</span><span class="sxs-lookup"><span data-stu-id="a87ce-109">Monitor network usage and call detail records so that you can choose optimal CAC settings and update CAC settings as network usage changes.</span></span>

  - <span data-ttu-id="a87ce-110">Use políticas de largura de banda de CAC para complementar as configurações de QoS.</span><span class="sxs-lookup"><span data-stu-id="a87ce-110">Use CAC bandwidth policies to complement QoS settings.</span></span>

  - <span data-ttu-id="a87ce-111">Se você desejar rerotear chamadas bloqueadas para o PSTN, verifique a funcionalidade e a capacidade do PSTN.</span><span class="sxs-lookup"><span data-stu-id="a87ce-111">If you want to re-route blocked calls onto the PSTN, verify PSTN functionality and capacity.</span></span> <span data-ttu-id="a87ce-112">Para obter detalhes, consulte [Planning Outbound Voice Routing in Lync Server 2013](lync-server-2013-planning-outbound-voice-routing.md).</span><span class="sxs-lookup"><span data-stu-id="a87ce-112">For details, see [Planning outbound voice routing in Lync Server 2013](lync-server-2013-planning-outbound-voice-routing.md).</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="a87ce-113">A capacidade refere-se ao número de portas que precisam ser abertas para oferecer suporte a um possível reroteamento do PSTN.</span><span class="sxs-lookup"><span data-stu-id="a87ce-113">Capacity refers to the number of ports you need to open to support potential PSTN re-routing.</span></span>

    
    </div>

</div>

<span> </span>

</div>

</div>

</div>

