---
title: Cenários de servidor de borda no Skype para Business Server
ms.reviewer: ''
ms.author: heidip
author: microsoftheidi
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 7b9c211b-deb0-479d-b184-973f08b96d07
description: 'Resumo: Revise esses cenários para ajudá-lo a planejar sua topologia de servidor de borda no Skype Business Server.'
ms.openlocfilehash: 26bdb7e007c3ba0da6c5590db4c1e6953e43e701
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32208905"
---
# <a name="edge-server-scenarios-in-skype-for-business-server"></a><span data-ttu-id="3b415-103">Cenários de servidor de borda no Skype para Business Server</span><span class="sxs-lookup"><span data-stu-id="3b415-103">Edge Server scenarios in Skype for Business Server</span></span>
 
<span data-ttu-id="3b415-104">**Resumo:** Examine esses cenários para ajudá-lo a planejar sua topologia de servidor de borda no Skype Business Server.</span><span class="sxs-lookup"><span data-stu-id="3b415-104">**Summary:** Review these scenarios to help you plan your Edge Server topology in Skype for Business Server.</span></span>
  
<span data-ttu-id="3b415-105">Temos alguns diagramas de cenários para auxiliar com visualizando e decidir sobre qual Skype para topologia de servidor de borda do servidor de negócios que você deseja implementar.</span><span class="sxs-lookup"><span data-stu-id="3b415-105">We have some scenarios diagrams to assist with visualizing and deciding on what Skype for Business Server Edge Server topology you want to implement.</span></span> <span data-ttu-id="3b415-106">Depois de escolher um bom candidato, você pode ler mais informações sobre quais requisitos ambientais serão necessários.</span><span class="sxs-lookup"><span data-stu-id="3b415-106">Once you've picked a good candidate, you can go read up on the environmental requirements you'll need to address.</span></span> <span data-ttu-id="3b415-107">Os seguintes são aplicados a qualquer um dos cenários, por isso, vamos mencioná-los primeiro.</span><span class="sxs-lookup"><span data-stu-id="3b415-107">The following is applicable to any of the scenarios, so we're mentioning it first.</span></span>
  
<span data-ttu-id="3b415-p102">Estes números, mostrados apenas para fins de exemplo (e, como tal, contêm dados IPv4 e IPv6 de exemplo), não representam o fluxo de comunicação real, mas uma visualização de alto nível de seu tráfego possível. Os detalhes da porta também podem ser observados nos diagramas de porta de cada cenário abaixo.</span><span class="sxs-lookup"><span data-stu-id="3b415-p102">These figures, which are shown for example purposes only (and as such contains sample IPv4 and IPv6 data), don't represent the actual communication flow, but rather a high-level view of your possible traffic. Port details can also be seen in the Port diagrams for each scenario below.</span></span>
  
<span data-ttu-id="3b415-110">Os diagramas mostram .com para a interface externa e .net para a interna, que também é material de amostra. Suas entradas podem ser bem diferentes na criação de seu próprio plano de Borda final.</span><span class="sxs-lookup"><span data-stu-id="3b415-110">The diagrams show .com for the external interface and .net for the internal, which is also sample material; of course your own entries may be quite different when you're putting together your own final Edge plan.</span></span>
  
<span data-ttu-id="3b415-111">Não incluímos o Diretor (que é um componente opcional) em qualquer um dos diagramas, mas você pode ler sobre que separadamente (mencionado em outros tópicos de planejamento).</span><span class="sxs-lookup"><span data-stu-id="3b415-111">We don't include the Director (which is an optional component) in any of the diagrams, but you can read about that separately (it's mentioned in other Planning topics).</span></span>
  
<span data-ttu-id="3b415-112">Conforme observado acima, há dados IPv6 de amostra nos esquemas.</span><span class="sxs-lookup"><span data-stu-id="3b415-112">As noted above, there is sample IPv6 data in the diagrams.</span></span> <span data-ttu-id="3b415-113">A maioria da documentação no [plano para implantações de servidor de borda no Skype para Business Server](edge-server-deployments.md) fará referência ao IPv4, mas você certamente é suportados, se você quiser usar o IPv6.</span><span class="sxs-lookup"><span data-stu-id="3b415-113">Most of the documentation in [Plan for Edge Server deployments in Skype for Business Server](edge-server-deployments.md) will refer to IPv4, but you are certainly supported if you want to use IPv6.</span></span> <span data-ttu-id="3b415-114">Observe que você precisará endereços IPv6 em seu espaço de endereços atribuído e lá eles precisarão funcionar com endereços internos e externos, assim como os IPs IPv4.</span><span class="sxs-lookup"><span data-stu-id="3b415-114">Note that you'll need IPv6 addresses in your assigned address space, and they'll need to work with internal and external addressing, as with IPv4 IPs.</span></span> <span data-ttu-id="3b415-115">É possível, graças ao Windows, usar  o recurso de pilha dupla, que é uma pilha de rede separada e distinta para IPv4 e IPv6.</span><span class="sxs-lookup"><span data-stu-id="3b415-115">You can, thanks to Windows, employ the dual stack feature, which is a separate and distinct network stack for IPv4 and IPv6.</span></span> <span data-ttu-id="3b415-116">Se for necessário, isso permitirá que você atribua endereços IPv4 e IPv6 ao mesmo tempo.</span><span class="sxs-lookup"><span data-stu-id="3b415-116">This will, if you need, allow you to assign IPv4 and IPv6 addresses concurrently.</span></span>
  
<span data-ttu-id="3b415-117">Existem dispositivos NAT que permitem NAT64 (IPv6 para IPv4) e NAT66 (IPv6 para IPv6)), e isso é válido para uso com Skype para Business Server.</span><span class="sxs-lookup"><span data-stu-id="3b415-117">There are NAT devices that allow for NAT64 (IPv6 to IPv4) and NAT66 (IPv6 to IPv6)), and this is valid for use with Skype for Business Server.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="3b415-118">Se você estiver usando o serviço de controle de admissão de chamadas (CAC), é preciso usar IPv4 na interface interna para que ele funcione.</span><span class="sxs-lookup"><span data-stu-id="3b415-118">If you're using Call Admission Control (CAC) you do have to use IPv4 on the internal interface for it to work.</span></span> 
  
## <a name="single-consolidated-skype-for-business-server-edge-server-with-private-ip-addresses-and-nat"></a><span data-ttu-id="3b415-119">Único consolidado Skype para servidor de borda do servidor de negócios com endereços IP de privados e NAT</span><span class="sxs-lookup"><span data-stu-id="3b415-119">Single consolidated Skype for Business Server Edge Server with private IP addresses and NAT</span></span>

<span data-ttu-id="3b415-p104">Com este cenário, não há opção para alta disponibilidade. Isso significa que você gastará menos no hardware e terá uma implantação mais simples. Se alta disponibilidade for necessária, verifique os cenários consolidados em escala abaixo.</span><span class="sxs-lookup"><span data-stu-id="3b415-p104">With this scenario, there is no option for high availability. This will mean you spend less on hardware and have a simpler deployment. If high availability is a must, check out the Scaled consolidated scenarios below.</span></span>
  
![Cenário de borda de única borda consolidada com IP privados usando NAT](../../media/Plan_LyncServer_Edge_Scenario_SingleConsolidatedEdgePrivateIP.jpg)
  
### <a name="port-diagram"></a><span data-ttu-id="3b415-124">Diagrama de porta</span><span class="sxs-lookup"><span data-stu-id="3b415-124">Port diagram</span></span>

<span data-ttu-id="3b415-125">Também temos um diagrama para portas para servidores de borda consolidada única.</span><span class="sxs-lookup"><span data-stu-id="3b415-125">We also have a diagram for ports for single consolidated Edge Servers.</span></span>
  
![Borda consolidada do perímetro de rede de um único cenário de borda](../../media/Plan_LyncServer_Edge_NetPerimeter_SingleConsolidatedEdge.jpg)
  
## <a name="single-consolidated-skype-for-business-server-edge-server-with-public-ip-addresses"></a><span data-ttu-id="3b415-127">Único consolidado Skype para servidor de borda do servidor de negócios com endereços IP públicos</span><span class="sxs-lookup"><span data-stu-id="3b415-127">Single consolidated Skype for Business Server Edge Server with public IP addresses</span></span>

<span data-ttu-id="3b415-p105">Com este cenário, não há opção para alta disponibilidade. Isso significa que você gastará menos no hardware e terá uma implantação mais simples. Se alta disponibilidade for necessária, verifique os cenários consolidados em escala abaixo.</span><span class="sxs-lookup"><span data-stu-id="3b415-p105">With this scenario, there is no option for high availability. This will mean you spend less on hardware and have a simpler deployment. If high availability is a must, check out the Scaled consolidated scenarios below.</span></span>
  
![Cenário de borda de única borda consolidada com IP públicos](../../media/Plan_LyncServer_Edge_Scenario_SingleConsolidatedEdgePublicIP.jpg)
  
### <a name="port-diagram"></a><span data-ttu-id="3b415-132">Diagrama de porta</span><span class="sxs-lookup"><span data-stu-id="3b415-132">Port diagram</span></span>

<span data-ttu-id="3b415-133">Também temos um diagrama para portas para servidores de borda consolidada única.</span><span class="sxs-lookup"><span data-stu-id="3b415-133">We also have a diagram for ports for single consolidated Edge Servers.</span></span>
  
![Borda consolidada do perímetro de rede de um único cenário de borda](../../media/Plan_LyncServer_Edge_NetPerimeter_SingleConsolidatedEdge.jpg)
  
## <a name="scaled-consolidated-skype-for-business-server-edge-pool-with-dns-load-balancing-and-private-ip-addresses-and-nat"></a><span data-ttu-id="3b415-135">Skype consolidada em escala para o pool de borda do servidor de negócios, com o DNS de carga balanceamento e particulares endereços IP e NAT</span><span class="sxs-lookup"><span data-stu-id="3b415-135">Scaled consolidated Skype for Business Server Edge pool, with DNS load balancing, and private IP addresses and NAT</span></span>

<span data-ttu-id="3b415-136">Com este cenário, você poderá ter alta disponibilidade em sua implantação de Borda, o que oferece vantagens de escalabilidade e suporte a failover.</span><span class="sxs-lookup"><span data-stu-id="3b415-136">With this scenario, you are able to have high availability in your Edge deployment, which gives you the advantages of scalability and failover support.</span></span>
  
![Cenário de borda para borda consolidada dimensionada, DNS LB com IP privados usando NAT](../../media/Plan_LyncServer_Edge_Scenario_ScaledConsolidatedEdgeDNSLBPrivateIP.jpg)
  
### <a name="port-diagram"></a><span data-ttu-id="3b415-138">Diagrama de porta</span><span class="sxs-lookup"><span data-stu-id="3b415-138">Port diagram</span></span>

<span data-ttu-id="3b415-139">Também temos um diagrama para pools de borda consolidados em escala com balanceamento de carga DNS.</span><span class="sxs-lookup"><span data-stu-id="3b415-139">We also have a diagram for scaled consolidated Edge pools with DNS load balancing.</span></span>
  
![Rede de perímetro para o cenário de borda dimensionado consolidada de borda usando o DNS LB](../../media/Plan_LyncServer_Edge_NetPerimeter_ScaledConsolidatedEdgeDNSLB.jpg)
  
## <a name="scaled-consolidated-skype-for-business-server-edge-pool-with-dns-load-balancing-and-public-ip-addresses"></a><span data-ttu-id="3b415-141">Os endereços IP públicos e balanceamento de carga do Skype consolidada em escala para o pool de borda do servidor de negócios, com DNS</span><span class="sxs-lookup"><span data-stu-id="3b415-141">Scaled consolidated Skype for Business Server Edge pool, with DNS load balancing and public IP addresses</span></span>

<span data-ttu-id="3b415-142">Com este cenário, você poderá ter alta disponibilidade em sua implantação de Borda, o que oferece vantagens de escalabilidade e suporte a failover.</span><span class="sxs-lookup"><span data-stu-id="3b415-142">With this scenario, you are able to have high availability in your Edge deployment, which gives you the advantages of scalability and failover support.</span></span>
  
![Cenário de borda para borda consolidada dimensionada, DNS LB com IP públicos](../../media/Plan_LyncServer_Edge_Scenario_ScaledConsolidatedEdgeDNSLBPublicIP.jpg)
  
### <a name="port-diagram"></a><span data-ttu-id="3b415-144">Diagrama de porta</span><span class="sxs-lookup"><span data-stu-id="3b415-144">Port diagram</span></span>

<span data-ttu-id="3b415-145">Também temos um diagrama para pools de borda consolidados em escala com balanceamento de carga DNS.</span><span class="sxs-lookup"><span data-stu-id="3b415-145">We also have a diagram for scaled consolidated Edge pools with DNS load balancing.</span></span>
  
![Rede de perímetro para o cenário de borda dimensionado consolidada de borda usando o DNS LB](../../media/Plan_LyncServer_Edge_NetPerimeter_ScaledConsolidatedEdgeDNSLB.jpg)
  
## <a name="scaled-consolidated-skype-for-business-server-edge-pool-with-hardware-load-balancing"></a><span data-ttu-id="3b415-147">Dimensionada consolidada Skype para pool de borda do servidor de negócios, com balanceamento de carga de hardware</span><span class="sxs-lookup"><span data-stu-id="3b415-147">Scaled consolidated Skype for Business Server Edge pool, with hardware load balancing</span></span>

<span data-ttu-id="3b415-148">Com este cenário, você poderá ter alta disponibilidade em sua implantação de Borda, o que oferece vantagens de escalabilidade e suporte a failover.</span><span class="sxs-lookup"><span data-stu-id="3b415-148">With this scenario, you are able to have high availability in your Edge deployment, which gives you the advantages of scalability and failover support.</span></span>
  
![Cenário de borda para borda consolidada dimensionada com HLB](../../media/Plan_LyncServer_Edge_Scenario_ScaledConsolidatedEdgeHLB.jpg)
  
### <a name="port-diagram"></a><span data-ttu-id="3b415-150">Diagrama de porta</span><span class="sxs-lookup"><span data-stu-id="3b415-150">Port diagram</span></span>

<span data-ttu-id="3b415-151">Também temos um diagrama para pools de borda consolidados em escala com balanceamento de carga de hardware</span><span class="sxs-lookup"><span data-stu-id="3b415-151">We also have a diagram for scaled consolidated Edge pools with hardware load balancing</span></span>
  
![Protocolos e portas de rede de perímetro do servidor de borda](../../media/Plan_LyncServer_Edge_NetPerimeter_ScaledConsolidatedEdgeHLB.jpg)
  

