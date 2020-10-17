---
title: 'Lync Server 2013: tronco SIP do site de filial'
description: 'Lync Server 2013: tronco SIP do site de filial.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Branch site SIP trunking
ms:assetid: c4d9dfcd-8baa-41ea-9677-48b0e429429d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412974(v=OCS.15)
ms:contentKeyID: 48185350
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 33e408a462c21ffa6df6e6a2aee50d7b87dca1f7
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48569317"
---
# <a name="branch-site-sip-trunking-in-lync-server-2013"></a><span data-ttu-id="14490-103">Tronco SIP do site de filial no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="14490-103">Branch site SIP trunking in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="14490-104">_**Última modificação do tópico:** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="14490-104">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="14490-105">Em alguns casos, talvez seja necessário implementar o tronco SIP distribuído em sites de filial selecionados.</span><span class="sxs-lookup"><span data-stu-id="14490-105">In some cases, you may need to implement distributed SIP trunking at selected branch sites.</span></span> <span data-ttu-id="14490-106">Para determinar se um tronco SIP é necessário para um site de filial, revise as informações em [como implementar o tronco SIP no Lync Server 2013?](lync-server-2013-how-do-i-implement-sip-trunking.md).</span><span class="sxs-lookup"><span data-stu-id="14490-106">To determine whether a SIP trunk is needed for a branch site, review the information in [How do I implement SIP trunking in Lync Server 2013?](lync-server-2013-how-do-i-implement-sip-trunking.md).</span></span>

<span data-ttu-id="14490-107">Para obter detalhes sobre as opções de topologia suportadas para implantação de troncos SIP em sites de filial, consulte [Branch-site resiliência Solutions in Lync Server 2013](lync-server-2013-branch-site-resiliency-solutions.md).</span><span class="sxs-lookup"><span data-stu-id="14490-107">For details about the supported topology options for deploying SIP trunks in branch sites, see [Branch-site resiliency solutions in Lync Server 2013](lync-server-2013-branch-site-resiliency-solutions.md).</span></span>

<div>

## <a name="example-branch-site-sip-trunk-requirements-analysis"></a><span data-ttu-id="14490-108">Análise de requisitos do tronco SIP do exemplo de site de filial</span><span class="sxs-lookup"><span data-stu-id="14490-108">Example Branch Site SIP Trunk Requirements Analysis</span></span>

<span data-ttu-id="14490-109">Quando você decidir implantar um tronco SIP de site de filial, precisará executar uma análise de custo específica do site.</span><span class="sxs-lookup"><span data-stu-id="14490-109">When you decide to deploy a branch site SIP trunk, you need to perform a site-specific cost analysis.</span></span> <span data-ttu-id="14490-110">Por exemplo, uma empresa que tenha um site central em Redmond, Washington e um site de filial em Nova York, deve fazer uma análise para determinar se deve implementar um tronco SIP do site de Nova York para um provedor de serviços local.</span><span class="sxs-lookup"><span data-stu-id="14490-110">For example, an enterprise that has a central site in Redmond, Washington, and a branch site in New York, should do an analysis to determine whether to implement a SIP trunk from the New York site to a local service provider.</span></span>

<span data-ttu-id="14490-111">Para determinar se um tronco SIP distribuído em Nova Iorque é uma opção com bom custo benefício, identifique quais números DID usarão o tronco SIP e analise o número de chamadas feitas de Nova Iorque para áreas diferentes de Redmond (425).</span><span class="sxs-lookup"><span data-stu-id="14490-111">To determine whether a distributed SIP trunk in New York is cost-effective, identify which Direct Inward Dialing (DID) numbers will use the SIP trunk, and analyze the number of calls New York makes to areas other than Redmond (425).</span></span> <span data-ttu-id="14490-112">Você pode ter cancelamento para o site de filial no site central.</span><span class="sxs-lookup"><span data-stu-id="14490-112">You can have DID termination for the branch site at the central site.</span></span> <span data-ttu-id="14490-113">Por exemplo, o site central Redmond pode hospedar números para o site de filial de Nova York.</span><span class="sxs-lookup"><span data-stu-id="14490-113">For example, the Redmond central site can host DID numbers for the New York branch site.</span></span> <span data-ttu-id="14490-114">Se o custo da implementação de um tronco SIP distribuído for menor do que o custo dessas chamadas, considere a implementação de um tronco SIP no site de filial de Nova York.</span><span class="sxs-lookup"><span data-stu-id="14490-114">If the cost of implementing a distributed SIP trunk is less than the cost of those calls, consider implementing a SIP trunk at the New York branch site.</span></span>

</div>

<div>

## <a name="other-branch-site-sip-trunk-requirements"></a><span data-ttu-id="14490-115">Outros requisitos de tronco SIP do site de filial</span><span class="sxs-lookup"><span data-stu-id="14490-115">Other Branch Site SIP Trunk Requirements</span></span>

<span data-ttu-id="14490-116">A opção entre uma implantação de um tronco SIP em vez de um gateway tem base na diferença entre as cobranças de PSTN de longa distância de cada opção.</span><span class="sxs-lookup"><span data-stu-id="14490-116">The choice between a deploying a SIP trunk instead of a gateway is based on the difference between the public switched telephone network (PSTN) long distance toll charges of each option.</span></span> <span data-ttu-id="14490-117">Se você implantar um tronco SIP de site de filial, também precisará determinar os requisitos de resiliência e largura de banda.</span><span class="sxs-lookup"><span data-stu-id="14490-117">If you deploy a branch site SIP trunk, you also need to determine your resiliency and bandwidth requirements.</span></span> <span data-ttu-id="14490-118">Se o link entre seu site de filial e o site central for resistente e tiver largura de banda suficiente, você poderá implantar um tronco SIP ou um gateway.</span><span class="sxs-lookup"><span data-stu-id="14490-118">If the link between your branch site and central site is resilient and has sufficient bandwidth, you can deploy a SIP trunk or a gateway.</span></span> <span data-ttu-id="14490-119">Não é necessário implantar um aparelho de filial persistente no site de filial.</span><span class="sxs-lookup"><span data-stu-id="14490-119">You do not need to deploy a Survivable Branch Appliance at the branch site.</span></span> <span data-ttu-id="14490-120">Se o link entre o seu site de filial e o site central não for resistente, implante um aparelho de filial persistente ou implante um servidor de filial persistente com um gateway ou tronco SIP no site de filial.</span><span class="sxs-lookup"><span data-stu-id="14490-120">If the link between your branch site and central site is not resilient, deploy a Survivable Branch Appliance, or deploy a Survivable Branch Server with either a gateway or SIP trunk at the branch site.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

