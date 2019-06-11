---
title: 'Lync Server 2013: troncos SIP do site de filial'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Branch site SIP trunking
ms:assetid: c4d9dfcd-8baa-41ea-9677-48b0e429429d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412974(v=OCS.15)
ms:contentKeyID: 48185350
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 955e920138021941db0e75832d56d06499738edd
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34836726"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="branch-site-sip-trunking-in-lync-server-2013"></a><span data-ttu-id="417f2-102">Branch site SIP trunking in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="417f2-102">Branch site SIP trunking in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="417f2-103">_**Tópico da última modificação:** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="417f2-103">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="417f2-104">Em alguns casos, talvez seja necessário implementar o entroncamento SIP distribuído em sites de filiais selecionados.</span><span class="sxs-lookup"><span data-stu-id="417f2-104">In some cases, you may need to implement distributed SIP trunking at selected branch sites.</span></span> <span data-ttu-id="417f2-105">Para determinar se um tronco SIP é necessário para um site de filial, examine as informações em [como implementar o entroncamento SIP no Lync Server 2013?](lync-server-2013-how-do-i-implement-sip-trunking.md).</span><span class="sxs-lookup"><span data-stu-id="417f2-105">To determine whether a SIP trunk is needed for a branch site, review the information in [How do I implement SIP trunking in Lync Server 2013?](lync-server-2013-how-do-i-implement-sip-trunking.md).</span></span>

<span data-ttu-id="417f2-106">Para obter detalhes sobre as opções de topologia com suporte para a implantação de troncos SIP em sites de filiais, consulte [soluções de resiliência de site de ramificação no Lync Server 2013](lync-server-2013-branch-site-resiliency-solutions.md).</span><span class="sxs-lookup"><span data-stu-id="417f2-106">For details about the supported topology options for deploying SIP trunks in branch sites, see [Branch-site resiliency solutions in Lync Server 2013](lync-server-2013-branch-site-resiliency-solutions.md).</span></span>

<div>

## <a name="example-branch-site-sip-trunk-requirements-analysis"></a><span data-ttu-id="417f2-107">Análise de requisitos do tronco SIP do exemplo de local de filial</span><span class="sxs-lookup"><span data-stu-id="417f2-107">Example Branch Site SIP Trunk Requirements Analysis</span></span>

<span data-ttu-id="417f2-108">Ao decidir implantar um tronco SIP de site de filial, você precisa executar uma análise de custo específica do site.</span><span class="sxs-lookup"><span data-stu-id="417f2-108">When you decide to deploy a branch site SIP trunk, you need to perform a site-specific cost analysis.</span></span> <span data-ttu-id="417f2-109">Por exemplo, uma empresa que tem um site central em Redmond, Washington e um site de filiais em Nova York, deve fazer uma análise para determinar se deve implementar um tronco SIP do site de Nova York para um provedor de serviços local.</span><span class="sxs-lookup"><span data-stu-id="417f2-109">For example, an enterprise that has a central site in Redmond, Washington, and a branch site in New York, should do an analysis to determine whether to implement a SIP trunk from the New York site to a local service provider.</span></span>

<span data-ttu-id="417f2-110">Para determinar se um tronco SIP distribuído em Nova Iorque é uma opção com bom custo benefício, identifique quais números DID usarão o tronco SIP e analise o número de chamadas feitas de Nova Iorque para áreas diferentes de Redmond (425).</span><span class="sxs-lookup"><span data-stu-id="417f2-110">To determine whether a distributed SIP trunk in New York is cost-effective, identify which Direct Inward Dialing (DID) numbers will use the SIP trunk, and analyze the number of calls New York makes to areas other than Redmond (425).</span></span> <span data-ttu-id="417f2-111">Você pode ter cancelamento para o site de filial no site central.</span><span class="sxs-lookup"><span data-stu-id="417f2-111">You can have DID termination for the branch site at the central site.</span></span> <span data-ttu-id="417f2-112">Por exemplo, o site central Redmond pode hospedar números para o site da filial de Nova York.</span><span class="sxs-lookup"><span data-stu-id="417f2-112">For example, the Redmond central site can host DID numbers for the New York branch site.</span></span> <span data-ttu-id="417f2-113">Se o custo da implementação de um tronco SIP distribuído for menor que o custo dessas chamadas, considere a implementação de um tronco SIP no site da filial de Nova York.</span><span class="sxs-lookup"><span data-stu-id="417f2-113">If the cost of implementing a distributed SIP trunk is less than the cost of those calls, consider implementing a SIP trunk at the New York branch site.</span></span>

</div>

<div>

## <a name="other-branch-site-sip-trunk-requirements"></a><span data-ttu-id="417f2-114">Outros requisitos de tronco SIP do local de filial</span><span class="sxs-lookup"><span data-stu-id="417f2-114">Other Branch Site SIP Trunk Requirements</span></span>

<span data-ttu-id="417f2-115">A opção entre uma implantação de um tronco SIP em vez de um gateway tem base na diferença entre as cobranças de PSTN de longa distância de cada opção.</span><span class="sxs-lookup"><span data-stu-id="417f2-115">The choice between a deploying a SIP trunk instead of a gateway is based on the difference between the public switched telephone network (PSTN) long distance toll charges of each option.</span></span> <span data-ttu-id="417f2-116">Se você implantar um tronco SIP de site de filial, também precisará determinar os requisitos de resiliência e largura de banda.</span><span class="sxs-lookup"><span data-stu-id="417f2-116">If you deploy a branch site SIP trunk, you also need to determine your resiliency and bandwidth requirements.</span></span> <span data-ttu-id="417f2-117">Se o link entre o site de sua filial e o site central for resistente e tiver largura de banda suficiente, você poderá implantar um tronco SIP ou um gateway.</span><span class="sxs-lookup"><span data-stu-id="417f2-117">If the link between your branch site and central site is resilient and has sufficient bandwidth, you can deploy a SIP trunk or a gateway.</span></span> <span data-ttu-id="417f2-118">Você não precisa implantar um aparelho de ramificação sobreviventes no site da filial.</span><span class="sxs-lookup"><span data-stu-id="417f2-118">You do not need to deploy a Survivable Branch Appliance at the branch site.</span></span> <span data-ttu-id="417f2-119">Se o link entre seu site de filial e o site central não for resistente, implante um aparelho de ramificação sobreviventes ou implante um servidor de ramificação sobreviventes com um tronco de gateway ou SIP no site da filial.</span><span class="sxs-lookup"><span data-stu-id="417f2-119">If the link between your branch site and central site is not resilient, deploy a Survivable Branch Appliance, or deploy a Survivable Branch Server with either a gateway or SIP trunk at the branch site.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

