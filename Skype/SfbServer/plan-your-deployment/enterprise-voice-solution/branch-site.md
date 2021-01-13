---
title: Tronco SIP do site de filial no Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: c4d9dfcd-8baa-41ea-9677-48b0e429429d
description: Saiba mais sobre o tronco SIP em sites de filial no Skype for Business Server Enterprise Voice.
ms.openlocfilehash: f8b875fca8adc1ac78c0b24cf3e53fab2ec2cd89
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49813711"
---
# <a name="branch-site-sip-trunking-in-skype-for-business-server"></a><span data-ttu-id="09086-103">Tronco SIP do site de filial no Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="09086-103">Branch site SIP trunking in Skype for Business Server</span></span>
 
<span data-ttu-id="09086-104">Saiba mais sobre o tronco SIP em sites de filial no Skype for Business Server Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="09086-104">Learn about SIP trunking at branch sites in Skype for Business Server Enterprise Voice.</span></span>
  
<span data-ttu-id="09086-105">Em alguns casos, talvez seja necessário implementar o tronco SIP distribuído em sites de filial selecionados.</span><span class="sxs-lookup"><span data-stu-id="09086-105">In some cases, you may need to implement distributed SIP trunking at selected branch sites.</span></span> <span data-ttu-id="09086-106">Para determinar se um tronco SIP é necessário para um site de filial e para obter detalhes sobre as opções de topologia com suporte para implantar troncos SIP em sites de filial, consulte tronco SIP no [Skype for Business Server.](sip-trunking.md)</span><span class="sxs-lookup"><span data-stu-id="09086-106">To determine whether a SIP trunk is needed for a branch site, and for details about the supported topology options for deploying SIP trunks in branch sites, see [SIP trunking in Skype for Business Server](sip-trunking.md).</span></span>
  
## <a name="example-branch-site-sip-trunk-requirements-analysis"></a><span data-ttu-id="09086-107">Análise de requisitos do tronco SIP do exemplo de site de filial</span><span class="sxs-lookup"><span data-stu-id="09086-107">Example Branch Site SIP Trunk Requirements Analysis</span></span>

<span data-ttu-id="09086-108">Ao decidir implantar um tronco SIP do site de filial, você precisa executar uma análise de custo específica do site.</span><span class="sxs-lookup"><span data-stu-id="09086-108">When you decide to deploy a branch site SIP trunk, you need to perform a site-specific cost analysis.</span></span> <span data-ttu-id="09086-109">Por exemplo, uma empresa que tenha um site central em Redmond, Washington e um site de filial em Nova York, deve fazer uma análise para determinar se deve implementar um tronco SIP do site de Nova York para um provedor de serviços local.</span><span class="sxs-lookup"><span data-stu-id="09086-109">For example, an enterprise that has a central site in Redmond, Washington, and a branch site in New York, should do an analysis to determine whether to implement a SIP trunk from the New York site to a local service provider.</span></span>
  
<span data-ttu-id="09086-110">Para determinar se um tronco SIP distribuído em Nova Iorque é uma opção com bom custo benefício, identifique quais números DID usarão o tronco SIP e analise o número de chamadas feitas de Nova Iorque para áreas diferentes de Redmond (425).</span><span class="sxs-lookup"><span data-stu-id="09086-110">To determine whether a distributed SIP trunk in New York is cost-effective, identify which Direct Inward Dialing (DID) numbers will use the SIP trunk, and analyze the number of calls New York makes to areas other than Redmond (425).</span></span> <span data-ttu-id="09086-111">Você pode ter a terminação DID para o site de filial no site central.</span><span class="sxs-lookup"><span data-stu-id="09086-111">You can have DID termination for the branch site at the central site.</span></span> <span data-ttu-id="09086-112">Por exemplo, o site central redmond pode hospedar números DID para o site de filial de Nova York.</span><span class="sxs-lookup"><span data-stu-id="09086-112">For example, the Redmond central site can host DID numbers for the New York branch site.</span></span> <span data-ttu-id="09086-113">Se o custo da implementação de um tronco SIP distribuído for menor do que o custo dessas chamadas, considere a implementação de um tronco SIP no site de filial de Nova York.</span><span class="sxs-lookup"><span data-stu-id="09086-113">If the cost of implementing a distributed SIP trunk is less than the cost of those calls, consider implementing a SIP trunk at the New York branch site.</span></span> 
  
## <a name="other-branch-site-sip-trunk-requirements"></a><span data-ttu-id="09086-114">Outros requisitos de tronco SIP do site de filial</span><span class="sxs-lookup"><span data-stu-id="09086-114">Other Branch Site SIP Trunk Requirements</span></span>

<span data-ttu-id="09086-115">A opção entre uma implantação de um tronco SIP em vez de um gateway tem base na diferença entre as cobranças de PSTN de longa distância de cada opção.</span><span class="sxs-lookup"><span data-stu-id="09086-115">The choice between a deploying a SIP trunk instead of a gateway is based on the difference between the public switched telephone network (PSTN) long distance toll charges of each option.</span></span> <span data-ttu-id="09086-116">Se você implantar um tronco SIP do site de filial, também precisará determinar seus requisitos de resiliência e largura de banda.</span><span class="sxs-lookup"><span data-stu-id="09086-116">If you deploy a branch site SIP trunk, you also need to determine your resiliency and bandwidth requirements.</span></span> <span data-ttu-id="09086-117">Se o link entre o site de filial e o site central for resiliente e tiver largura de banda suficiente, você poderá implantar um tronco SIP ou um gateway.</span><span class="sxs-lookup"><span data-stu-id="09086-117">If the link between your branch site and central site is resilient and has sufficient bandwidth, you can deploy a SIP trunk or a gateway.</span></span> <span data-ttu-id="09086-118">Não é necessário implantar um Aparelho de FilialVivível no site de filial.</span><span class="sxs-lookup"><span data-stu-id="09086-118">You do not need to deploy a Survivable Branch Appliance at the branch site.</span></span> <span data-ttu-id="09086-119">Se o link entre o site de filial e o site central não for resiliente, implante um Aparelho de Filial Persistente ou implante um Servidor de Filial Persistente com um gateway ou tronco SIP no site de filial.</span><span class="sxs-lookup"><span data-stu-id="09086-119">If the link between your branch site and central site is not resilient, deploy a Survivable Branch Appliance, or deploy a Survivable Branch Server with either a gateway or SIP trunk at the branch site.</span></span> 
  

