---
title: Cenários do Servidor de Borda no Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
audience: ITPro
ms.topic: conceptual
manager: serdars
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 7b9c211b-deb0-479d-b184-973f08b96d07
description: 'Resumo: Revise estes cenários para ajudá-lo a planejar sua topologia do Servidor de Borda no Skype for Business Server.'
ms.openlocfilehash: cfcc1e8b34576fbec85464fb8d5e35903b47d8ef
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49813787"
---
# <a name="edge-server-scenarios-in-skype-for-business-server"></a><span data-ttu-id="6b88f-103">Cenários do Servidor de Borda no Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="6b88f-103">Edge Server scenarios in Skype for Business Server</span></span>
 
<span data-ttu-id="6b88f-104">**Resumo:** Revise esses cenários para ajudá-lo a planejar sua topologia de Servidor de Borda no Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="6b88f-104">**Summary:** Review these scenarios to help you plan your Edge Server topology in Skype for Business Server.</span></span>
  
<span data-ttu-id="6b88f-105">Temos alguns diagramas de cenários para ajudar a visualizar e decidir qual topologia do Servidor de Borda do Skype for Business Server você deseja implementar.</span><span class="sxs-lookup"><span data-stu-id="6b88f-105">We have some scenarios diagrams to assist with visualizing and deciding on what Skype for Business Server Edge Server topology you want to implement.</span></span> <span data-ttu-id="6b88f-106">Depois de escolher um bom candidato, leia os requisitos ambientais necessários.</span><span class="sxs-lookup"><span data-stu-id="6b88f-106">Once you've picked a good candidate, you can go read up on the environmental requirements you'll need to address.</span></span> <span data-ttu-id="6b88f-107">O exemplo a seguir é aplicável a qualquer um dos cenários, portanto, vamos mencioná-lo primeiro.</span><span class="sxs-lookup"><span data-stu-id="6b88f-107">The following is applicable to any of the scenarios, so we're mentioning it first.</span></span>
  
<span data-ttu-id="6b88f-108">Esses números, que são mostrados apenas para fins de exemplo (e, como tal, contêm dados de IPv4 e IPv6 de exemplo), não representam o fluxo de comunicação real, mas sim uma visão de alto nível do seu tráfego possível.</span><span class="sxs-lookup"><span data-stu-id="6b88f-108">These figures, which are shown for example purposes only (and as such contains sample IPv4 and IPv6 data), don't represent the actual communication flow, but rather a high-level view of your possible traffic.</span></span> <span data-ttu-id="6b88f-109">Os detalhes da porta também podem ser vistos nos diagramas de porta para cada cenário abaixo.</span><span class="sxs-lookup"><span data-stu-id="6b88f-109">Port details can also be seen in the Port diagrams for each scenario below.</span></span>
  
<span data-ttu-id="6b88f-110">Os diagramas mostram .com para a interface externa e .net para o interno, que também é material de exemplo; É claro que suas próprias entradas podem ser bem diferentes quando você estiver reunindo seu próprio plano de Borda final.</span><span class="sxs-lookup"><span data-stu-id="6b88f-110">The diagrams show .com for the external interface and .net for the internal, which is also sample material; of course your own entries may be quite different when you're putting together your own final Edge plan.</span></span>
  
<span data-ttu-id="6b88f-111">Não incluímos o Diretor (que é um componente opcional) em nenhum dos diagramas, mas você pode ler sobre isso separadamente (isso é mencionado em outros tópicos de Planejamento).</span><span class="sxs-lookup"><span data-stu-id="6b88f-111">We don't include the Director (which is an optional component) in any of the diagrams, but you can read about that separately (it's mentioned in other Planning topics).</span></span>
  
<span data-ttu-id="6b88f-112">Conforme mencionado acima, há dados IPv6 de exemplo nos diagramas.</span><span class="sxs-lookup"><span data-stu-id="6b88f-112">As noted above, there is sample IPv6 data in the diagrams.</span></span> <span data-ttu-id="6b88f-113">A maior parte da documentação em [Plan for Edge Server deployments in Skype for Business Server](edge-server-deployments.md) se referirá a IPv4, mas você certamente terá suporte se quiser usar IPv6.</span><span class="sxs-lookup"><span data-stu-id="6b88f-113">Most of the documentation in [Plan for Edge Server deployments in Skype for Business Server](edge-server-deployments.md) will refer to IPv4, but you are certainly supported if you want to use IPv6.</span></span> <span data-ttu-id="6b88f-114">Observe que você precisará de endereços IPv6 em seu espaço de endereçamento atribuído, e eles precisarão trabalhar com endereçamento interno e externo, como com IPs IPv4.</span><span class="sxs-lookup"><span data-stu-id="6b88f-114">Note that you'll need IPv6 addresses in your assigned address space, and they'll need to work with internal and external addressing, as with IPv4 IPs.</span></span> <span data-ttu-id="6b88f-115">Você pode, graças ao Windows, empregar o recurso de pilha dupla, que é uma pilha de rede separada e distinta para IPv4 e IPv6.</span><span class="sxs-lookup"><span data-stu-id="6b88f-115">You can, thanks to Windows, employ the dual stack feature, which is a separate and distinct network stack for IPv4 and IPv6.</span></span> <span data-ttu-id="6b88f-116">Isso permitirá, se necessário, atribuir endereços IPv4 e IPv6 simultaneamente.</span><span class="sxs-lookup"><span data-stu-id="6b88f-116">This will, if you need, allow you to assign IPv4 and IPv6 addresses concurrently.</span></span>
  
<span data-ttu-id="6b88f-117">Há dispositivos NAT que permitem NAT64 (IPv6 a IPv4) e NAT66 (IPv6 para IPv6)), e isso é válido para uso com o Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="6b88f-117">There are NAT devices that allow for NAT64 (IPv6 to IPv4) and NAT66 (IPv6 to IPv6)), and this is valid for use with Skype for Business Server.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="6b88f-118">Se você estiver usando o Controle de Admissão de Chamada (CAC), será preciso usar o IPv4 na interface interna para que ele funcione.</span><span class="sxs-lookup"><span data-stu-id="6b88f-118">If you're using Call Admission Control (CAC) you do have to use IPv4 on the internal interface for it to work.</span></span> 
  
## <a name="single-consolidated-skype-for-business-server-edge-server-with-private-ip-addresses-and-nat"></a><span data-ttu-id="6b88f-119">Servidor de Borda do Skype for Business Server único consolidado com endereços IP privados e NAT</span><span class="sxs-lookup"><span data-stu-id="6b88f-119">Single consolidated Skype for Business Server Edge Server with private IP addresses and NAT</span></span>

<span data-ttu-id="6b88f-120">Com esse cenário, não há opção para alta disponibilidade.</span><span class="sxs-lookup"><span data-stu-id="6b88f-120">With this scenario, there is no option for high availability.</span></span> <span data-ttu-id="6b88f-121">Isso significa que você gastará menos em hardware e terá uma implantação mais simples.</span><span class="sxs-lookup"><span data-stu-id="6b88f-121">This will mean you spend less on hardware and have a simpler deployment.</span></span> <span data-ttu-id="6b88f-122">Se a alta disponibilidade for uma im necessário, confira os cenários consolidados em escala abaixo.</span><span class="sxs-lookup"><span data-stu-id="6b88f-122">If high availability is a must, check out the Scaled consolidated scenarios below.</span></span>
  
![Cenário de borda para borda consolidada única com IP privado usando NAT](../../media/Plan_LyncServer_Edge_Scenario_SingleConsolidatedEdgePrivateIP.jpg)
  
### <a name="port-diagram"></a><span data-ttu-id="6b88f-124">Diagrama de porta</span><span class="sxs-lookup"><span data-stu-id="6b88f-124">Port diagram</span></span>

<span data-ttu-id="6b88f-125">Também temos um diagrama para portas para Servidores de Borda consolidados individuais.</span><span class="sxs-lookup"><span data-stu-id="6b88f-125">We also have a diagram for ports for single consolidated Edge Servers.</span></span>
  
![Perímetro de rede para o cenário de borda única borda consolidada](../../media/Plan_LyncServer_Edge_NetPerimeter_SingleConsolidatedEdge.jpg)
  
## <a name="single-consolidated-skype-for-business-server-edge-server-with-public-ip-addresses"></a><span data-ttu-id="6b88f-127">Servidor de Borda do Skype for Business Server único consolidado com endereços IP públicos</span><span class="sxs-lookup"><span data-stu-id="6b88f-127">Single consolidated Skype for Business Server Edge Server with public IP addresses</span></span>

<span data-ttu-id="6b88f-128">Com esse cenário, não há opção para alta disponibilidade.</span><span class="sxs-lookup"><span data-stu-id="6b88f-128">With this scenario, there is no option for high availability.</span></span> <span data-ttu-id="6b88f-129">Isso significa que você gastará menos em hardware e terá uma implantação mais simples.</span><span class="sxs-lookup"><span data-stu-id="6b88f-129">This will mean you spend less on hardware and have a simpler deployment.</span></span> <span data-ttu-id="6b88f-130">Se a alta disponibilidade for uma im necessário, confira os cenários consolidados em escala abaixo.</span><span class="sxs-lookup"><span data-stu-id="6b88f-130">If high availability is a must, check out the Scaled consolidated scenarios below.</span></span>
  
![Cenário de borda para borda consolidada única com IP público](../../media/Plan_LyncServer_Edge_Scenario_SingleConsolidatedEdgePublicIP.jpg)
  
### <a name="port-diagram"></a><span data-ttu-id="6b88f-132">Diagrama de porta</span><span class="sxs-lookup"><span data-stu-id="6b88f-132">Port diagram</span></span>

<span data-ttu-id="6b88f-133">Também temos um diagrama para portas para Servidores de Borda consolidados individuais.</span><span class="sxs-lookup"><span data-stu-id="6b88f-133">We also have a diagram for ports for single consolidated Edge Servers.</span></span>
  
![Perímetro de rede para o cenário de borda única borda consolidada](../../media/Plan_LyncServer_Edge_NetPerimeter_SingleConsolidatedEdge.jpg)
  
## <a name="scaled-consolidated-skype-for-business-server-edge-pool-with-dns-load-balancing-and-private-ip-addresses-and-nat"></a><span data-ttu-id="6b88f-135">Pool de Borda do Skype for Business Server consolidado em escala, com balanceamento de carga DNS e endereços IP privados e NAT</span><span class="sxs-lookup"><span data-stu-id="6b88f-135">Scaled consolidated Skype for Business Server Edge pool, with DNS load balancing, and private IP addresses and NAT</span></span>

<span data-ttu-id="6b88f-136">Com esse cenário, você pode ter alta disponibilidade em sua implantação de Borda, o que oferece as vantagens de escalabilidade e suporte a failover.</span><span class="sxs-lookup"><span data-stu-id="6b88f-136">With this scenario, you are able to have high availability in your Edge deployment, which gives you the advantages of scalability and failover support.</span></span>
  
![Cenário de borda para borda consolidada em escala, DNS LB com IP privado usando NAT](../../media/Plan_LyncServer_Edge_Scenario_ScaledConsolidatedEdgeDNSLBPrivateIP.jpg)
  
### <a name="port-diagram"></a><span data-ttu-id="6b88f-138">Diagrama de porta</span><span class="sxs-lookup"><span data-stu-id="6b88f-138">Port diagram</span></span>

<span data-ttu-id="6b88f-139">Também temos um diagrama para pools de Borda consolidados em escala com balanceamento de carga DNS.</span><span class="sxs-lookup"><span data-stu-id="6b88f-139">We also have a diagram for scaled consolidated Edge pools with DNS load balancing.</span></span>
  
![Perímetro de rede para borda consolidada em escala do cenário de borda usando DNS LB](../../media/Plan_LyncServer_Edge_NetPerimeter_ScaledConsolidatedEdgeDNSLB.jpg)
  
## <a name="scaled-consolidated-skype-for-business-server-edge-pool-with-dns-load-balancing-and-public-ip-addresses"></a><span data-ttu-id="6b88f-141">Pool de Borda do Skype for Business Server consolidado em escala, com balanceamento de carga DNS e endereços IP públicos</span><span class="sxs-lookup"><span data-stu-id="6b88f-141">Scaled consolidated Skype for Business Server Edge pool, with DNS load balancing and public IP addresses</span></span>

<span data-ttu-id="6b88f-142">Com esse cenário, você pode ter alta disponibilidade em sua implantação de Borda, o que oferece as vantagens de escalabilidade e suporte a failover.</span><span class="sxs-lookup"><span data-stu-id="6b88f-142">With this scenario, you are able to have high availability in your Edge deployment, which gives you the advantages of scalability and failover support.</span></span>
  
![Cenário de borda para borda consolidada em escala, DNS LB com IP público](../../media/Plan_LyncServer_Edge_Scenario_ScaledConsolidatedEdgeDNSLBPublicIP.jpg)
  
### <a name="port-diagram"></a><span data-ttu-id="6b88f-144">Diagrama de porta</span><span class="sxs-lookup"><span data-stu-id="6b88f-144">Port diagram</span></span>

<span data-ttu-id="6b88f-145">Também temos um diagrama para pools de Borda consolidados em escala com balanceamento de carga DNS.</span><span class="sxs-lookup"><span data-stu-id="6b88f-145">We also have a diagram for scaled consolidated Edge pools with DNS load balancing.</span></span>
  
![Perímetro de rede para borda consolidada em escala do cenário de borda usando DNS LB](../../media/Plan_LyncServer_Edge_NetPerimeter_ScaledConsolidatedEdgeDNSLB.jpg)
  
## <a name="scaled-consolidated-skype-for-business-server-edge-pool-with-hardware-load-balancing"></a><span data-ttu-id="6b88f-147">Pool de Borda do Skype for Business Server consolidado em escala, com balanceamento de carga de hardware</span><span class="sxs-lookup"><span data-stu-id="6b88f-147">Scaled consolidated Skype for Business Server Edge pool, with hardware load balancing</span></span>

<span data-ttu-id="6b88f-148">Com esse cenário, você pode ter alta disponibilidade em sua implantação de Borda, o que oferece as vantagens de escalabilidade e suporte a failover.</span><span class="sxs-lookup"><span data-stu-id="6b88f-148">With this scenario, you are able to have high availability in your Edge deployment, which gives you the advantages of scalability and failover support.</span></span>
  
![Cenário de borda para borda consolidada em escala com HLB](../../media/Plan_LyncServer_Edge_Scenario_ScaledConsolidatedEdgeHLB.jpg)
 
