---
title: Tronco SIP do site da filial no Skype for Business Server 2015
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 8/17/2015
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: c4d9dfcd-8baa-41ea-9677-48b0e429429d
description: Saiba mais sobre o tronco SIP em sites de filial em Skype para Business Server Enterprise Voice.
ms.openlocfilehash: 862a39e7472ab461725957cea6e5a89e0c156286
ms.sourcegitcommit: fa61d0b380a6ee559ad78e06bba85bc28d1045a6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/03/2018
---
# <a name="branch-site-sip-trunking-in-skype-for-business-server-2015"></a><span data-ttu-id="c1a67-103">Tronco SIP do site da filial no Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="c1a67-103">Branch site SIP trunking in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="c1a67-104">Saiba mais sobre o tronco SIP em sites de filial em Skype para Business Server Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="c1a67-104">Learn about SIP trunking at branch sites in Skype for Business Server Enterprise Voice.</span></span>
  
<span data-ttu-id="c1a67-105">Em alguns casos, você precisará implementar o tronco SIP distribuído em sites de filiais selecionado.</span><span class="sxs-lookup"><span data-stu-id="c1a67-105">In some cases, you may need to implement distributed SIP trunking at selected branch sites.</span></span> <span data-ttu-id="c1a67-106">Para determinar se um SIP tronco é necessária para um site de filial e para obter detalhes sobre as opções de topologia suportadas para a implantação de troncos SIP nos sites de filiais, consulte o [tronco SIP no Skype para Business Server 2015](sip-trunking.md).</span><span class="sxs-lookup"><span data-stu-id="c1a67-106">To determine whether a SIP trunk is needed for a branch site, and for details about the supported topology options for deploying SIP trunks in branch sites, see [SIP trunking in Skype for Business Server 2015](sip-trunking.md).</span></span>
  
## <a name="example-branch-site-sip-trunk-requirements-analysis"></a><span data-ttu-id="c1a67-107">Análise de requisitos do tronco SIP do exemplo de local de filial</span><span class="sxs-lookup"><span data-stu-id="c1a67-107">Example Branch Site SIP Trunk Requirements Analysis</span></span>

<span data-ttu-id="c1a67-108">Quando você decide implantar um tronco SIP do site de filial, você precisará executar uma análise de custo específicas do site.</span><span class="sxs-lookup"><span data-stu-id="c1a67-108">When you decide to deploy a branch site SIP trunk, you need to perform a site-specific cost analysis.</span></span> <span data-ttu-id="c1a67-109">Por exemplo, uma empresa que tenha um site central em Redmond, Washington e um site de filial em Nova York, deverá fazer uma análise para determinar se você implementar um tronco SIP do site Nova York a um provedor de serviço local.</span><span class="sxs-lookup"><span data-stu-id="c1a67-109">For example, an enterprise that has a central site in Redmond, Washington, and a branch site in New York, should do an analysis to determine whether to implement a SIP trunk from the New York site to a local service provider.</span></span>
  
<span data-ttu-id="c1a67-110">Para determinar se um tronco SIP distribuído em Nova Iorque é uma opção com bom custo benefício, identifique quais números DID usarão o tronco SIP e analise o número de chamadas feitas de Nova Iorque para áreas diferentes de Redmond (425).</span><span class="sxs-lookup"><span data-stu-id="c1a67-110">To determine whether a distributed SIP trunk in New York is cost-effective, identify which Direct Inward Dialing (DID) numbers will use the SIP trunk, and analyze the number of calls New York makes to areas other than Redmond (425).</span></span> <span data-ttu-id="c1a67-111">Você pode ter DID terminação para o site da filial no site central.</span><span class="sxs-lookup"><span data-stu-id="c1a67-111">You can have DID termination for the branch site at the central site.</span></span> <span data-ttu-id="c1a67-112">Por exemplo, o site central Redmond pode hospedar números DID para o site de filial de Nova York.</span><span class="sxs-lookup"><span data-stu-id="c1a67-112">For example, the Redmond central site can host DID numbers for the New York branch site.</span></span> <span data-ttu-id="c1a67-113">Se o custo de implementar um tronco SIP distribuído for menor que o custo dessas chamadas, considere a implementação de um tronco SIP no site da filial de Nova York.</span><span class="sxs-lookup"><span data-stu-id="c1a67-113">If the cost of implementing a distributed SIP trunk is less than the cost of those calls, consider implementing a SIP trunk at the New York branch site.</span></span> 
  
## <a name="other-branch-site-sip-trunk-requirements"></a><span data-ttu-id="c1a67-114">Outros requisitos de tronco SIP do local de filial</span><span class="sxs-lookup"><span data-stu-id="c1a67-114">Other Branch Site SIP Trunk Requirements</span></span>

<span data-ttu-id="c1a67-115">A opção entre uma implantação de um tronco SIP em vez de um gateway tem base na diferença entre as cobranças de PSTN de longa distância de cada opção.</span><span class="sxs-lookup"><span data-stu-id="c1a67-115">The choice between a deploying a SIP trunk instead of a gateway is based on the difference between the public switched telephone network (PSTN) long distance toll charges of each option.</span></span> <span data-ttu-id="c1a67-116">Se você implantar um tronco SIP do site de filial, você também precisará determinar os requisitos de resiliência e largura de banda.</span><span class="sxs-lookup"><span data-stu-id="c1a67-116">If you deploy a branch site SIP trunk, you also need to determine your resiliency and bandwidth requirements.</span></span> <span data-ttu-id="c1a67-117">Se o vínculo entre o seu site de filial e o site central é resiliente e tem a largura de banda suficiente, você pode implantar um tronco SIP ou um gateway.</span><span class="sxs-lookup"><span data-stu-id="c1a67-117">If the link between your branch site and central site is resilient and has sufficient bandwidth, you can deploy a SIP trunk or a gateway.</span></span> <span data-ttu-id="c1a67-118">Você não precisará implantar um aparelho de filial persistente no site da filial.</span><span class="sxs-lookup"><span data-stu-id="c1a67-118">You do not need to deploy a Survivable Branch Appliance at the branch site.</span></span> <span data-ttu-id="c1a67-119">Se o vínculo entre o seu site de filial e o site central não for resiliente, implante um aparelho de filial persistente ou implantar um servidor de filial persistente com um gateway ou tronco SIP no site da filial.</span><span class="sxs-lookup"><span data-stu-id="c1a67-119">If the link between your branch site and central site is not resilient, deploy a Survivable Branch Appliance, or deploy a Survivable Branch Server with either a gateway or SIP trunk at the branch site.</span></span> 
  

