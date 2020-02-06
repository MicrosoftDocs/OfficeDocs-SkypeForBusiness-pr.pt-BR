---
title: Cenários do servidor de borda no Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
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
description: 'Resumo: revise esses cenários para ajudá-lo a planejar a topologia do servidor de borda no Skype for Business Server.'
ms.openlocfilehash: a1d721ffabb78985d90848784cd587bda96300d5
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41803351"
---
# <a name="edge-server-scenarios-in-skype-for-business-server"></a><span data-ttu-id="959ac-103">Cenários do servidor de borda no Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="959ac-103">Edge Server scenarios in Skype for Business Server</span></span>
 
<span data-ttu-id="959ac-104">**Resumo:** Revise esses cenários para ajudá-lo a planejar a topologia do servidor de borda no Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="959ac-104">**Summary:** Review these scenarios to help you plan your Edge Server topology in Skype for Business Server.</span></span>
  
<span data-ttu-id="959ac-105">Temos alguns diagramas de cenários para auxiliar na visualização e na decisão sobre qual topologia do servidor de borda do Skype for Business Server você deseja implementar.</span><span class="sxs-lookup"><span data-stu-id="959ac-105">We have some scenarios diagrams to assist with visualizing and deciding on what Skype for Business Server Edge Server topology you want to implement.</span></span> <span data-ttu-id="959ac-106">Depois de escolher um bom candidato, você pode ler mais informações sobre quais requisitos ambientais serão necessários.</span><span class="sxs-lookup"><span data-stu-id="959ac-106">Once you've picked a good candidate, you can go read up on the environmental requirements you'll need to address.</span></span> <span data-ttu-id="959ac-107">Os seguintes são aplicados a qualquer um dos cenários, por isso, vamos mencioná-los primeiro.</span><span class="sxs-lookup"><span data-stu-id="959ac-107">The following is applicable to any of the scenarios, so we're mentioning it first.</span></span>
  
<span data-ttu-id="959ac-p102">Estes números, mostrados apenas para fins de exemplo (e, como tal, contêm dados IPv4 e IPv6 de exemplo), não representam o fluxo de comunicação real, mas uma visualização de alto nível de seu tráfego possível. Os detalhes da porta também podem ser observados nos diagramas de porta de cada cenário abaixo.</span><span class="sxs-lookup"><span data-stu-id="959ac-p102">These figures, which are shown for example purposes only (and as such contains sample IPv4 and IPv6 data), don't represent the actual communication flow, but rather a high-level view of your possible traffic. Port details can also be seen in the Port diagrams for each scenario below.</span></span>
  
<span data-ttu-id="959ac-110">Os diagramas mostram .com para a interface externa e .net para a interna, que também é material de amostra. Suas entradas podem ser bem diferentes na criação de seu próprio plano de Borda final.</span><span class="sxs-lookup"><span data-stu-id="959ac-110">The diagrams show .com for the external interface and .net for the internal, which is also sample material; of course your own entries may be quite different when you're putting together your own final Edge plan.</span></span>
  
<span data-ttu-id="959ac-111">Não incluímos o diretor (que é um componente opcional) em qualquer um dos diagramas, mas você pode ler sobre isso separadamente (ele é mencionado em outros tópicos de planejamento).</span><span class="sxs-lookup"><span data-stu-id="959ac-111">We don't include the Director (which is an optional component) in any of the diagrams, but you can read about that separately (it's mentioned in other Planning topics).</span></span>
  
<span data-ttu-id="959ac-112">Conforme observado acima, há dados IPv6 de amostra nos esquemas.</span><span class="sxs-lookup"><span data-stu-id="959ac-112">As noted above, there is sample IPv6 data in the diagrams.</span></span> <span data-ttu-id="959ac-113">A maior parte da documentação do [plano para implantações do servidor de borda no Skype for Business Server](edge-server-deployments.md) se refere a IPv4, mas você certamente terá suporte se quiser usar o IPv6.</span><span class="sxs-lookup"><span data-stu-id="959ac-113">Most of the documentation in [Plan for Edge Server deployments in Skype for Business Server](edge-server-deployments.md) will refer to IPv4, but you are certainly supported if you want to use IPv6.</span></span> <span data-ttu-id="959ac-114">Observe que você precisará endereços IPv6 em seu espaço de endereços atribuído e lá eles precisarão funcionar com endereços internos e externos, assim como os IPs IPv4.</span><span class="sxs-lookup"><span data-stu-id="959ac-114">Note that you'll need IPv6 addresses in your assigned address space, and they'll need to work with internal and external addressing, as with IPv4 IPs.</span></span> <span data-ttu-id="959ac-115">É possível, graças ao Windows, usar  o recurso de pilha dupla, que é uma pilha de rede separada e distinta para IPv4 e IPv6.</span><span class="sxs-lookup"><span data-stu-id="959ac-115">You can, thanks to Windows, employ the dual stack feature, which is a separate and distinct network stack for IPv4 and IPv6.</span></span> <span data-ttu-id="959ac-116">Se for necessário, isso permitirá que você atribua endereços IPv4 e IPv6 ao mesmo tempo.</span><span class="sxs-lookup"><span data-stu-id="959ac-116">This will, if you need, allow you to assign IPv4 and IPv6 addresses concurrently.</span></span>
  
<span data-ttu-id="959ac-117">Há dispositivos NAT que permitem NAT64 (IPv6 a IPv4) e NAT66 (IPv6 para IPv6)) e são válidos para uso com o Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="959ac-117">There are NAT devices that allow for NAT64 (IPv6 to IPv4) and NAT66 (IPv6 to IPv6)), and this is valid for use with Skype for Business Server.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="959ac-118">Se você estiver usando o serviço de controle de admissão de chamadas (CAC), é preciso usar IPv4 na interface interna para que ele funcione.</span><span class="sxs-lookup"><span data-stu-id="959ac-118">If you're using Call Admission Control (CAC) you do have to use IPv4 on the internal interface for it to work.</span></span> 
  
## <a name="single-consolidated-skype-for-business-server-edge-server-with-private-ip-addresses-and-nat"></a><span data-ttu-id="959ac-119">Servidor de borda único do Skype for Business Server consolidado com endereços IP privados e NAT</span><span class="sxs-lookup"><span data-stu-id="959ac-119">Single consolidated Skype for Business Server Edge Server with private IP addresses and NAT</span></span>

<span data-ttu-id="959ac-p104">Com este cenário, não há opção para alta disponibilidade. Isso significa que você gastará menos no hardware e terá uma implantação mais simples. Se alta disponibilidade for necessária, verifique os cenários consolidados em escala abaixo.</span><span class="sxs-lookup"><span data-stu-id="959ac-p104">With this scenario, there is no option for high availability. This will mean you spend less on hardware and have a simpler deployment. If high availability is a must, check out the Scaled consolidated scenarios below.</span></span>
  
![Cenário de borda para a aresta consolidada única com o IP privado usando NAT](../../media/Plan_LyncServer_Edge_Scenario_SingleConsolidatedEdgePrivateIP.jpg)
  
### <a name="port-diagram"></a><span data-ttu-id="959ac-124">Diagrama de porta</span><span class="sxs-lookup"><span data-stu-id="959ac-124">Port diagram</span></span>

<span data-ttu-id="959ac-125">Também temos um diagrama para portas para servidores Single Edge consolidados.</span><span class="sxs-lookup"><span data-stu-id="959ac-125">We also have a diagram for ports for single consolidated Edge Servers.</span></span>
  
![Perímetro de rede para cenário de Edge consolidado único](../../media/Plan_LyncServer_Edge_NetPerimeter_SingleConsolidatedEdge.jpg)
  
## <a name="single-consolidated-skype-for-business-server-edge-server-with-public-ip-addresses"></a><span data-ttu-id="959ac-127">Servidor de borda único do Skype for Business Server consolidado com endereços IP públicos</span><span class="sxs-lookup"><span data-stu-id="959ac-127">Single consolidated Skype for Business Server Edge Server with public IP addresses</span></span>

<span data-ttu-id="959ac-p105">Com este cenário, não há opção para alta disponibilidade. Isso significa que você gastará menos no hardware e terá uma implantação mais simples. Se alta disponibilidade for necessária, verifique os cenários consolidados em escala abaixo.</span><span class="sxs-lookup"><span data-stu-id="959ac-p105">With this scenario, there is no option for high availability. This will mean you spend less on hardware and have a simpler deployment. If high availability is a must, check out the Scaled consolidated scenarios below.</span></span>
  
![Cenário de borda para a aresta consolidada única com o IP público](../../media/Plan_LyncServer_Edge_Scenario_SingleConsolidatedEdgePublicIP.jpg)
  
### <a name="port-diagram"></a><span data-ttu-id="959ac-132">Diagrama de porta</span><span class="sxs-lookup"><span data-stu-id="959ac-132">Port diagram</span></span>

<span data-ttu-id="959ac-133">Também temos um diagrama para portas para servidores Single Edge consolidados.</span><span class="sxs-lookup"><span data-stu-id="959ac-133">We also have a diagram for ports for single consolidated Edge Servers.</span></span>
  
![Perímetro de rede para cenário de Edge consolidado único](../../media/Plan_LyncServer_Edge_NetPerimeter_SingleConsolidatedEdge.jpg)
  
## <a name="scaled-consolidated-skype-for-business-server-edge-pool-with-dns-load-balancing-and-private-ip-addresses-and-nat"></a><span data-ttu-id="959ac-135">Conjunto de bordas do Skype for Business Server consolidado com balanceamento de carga de DNS e endereços IP privados e NAT</span><span class="sxs-lookup"><span data-stu-id="959ac-135">Scaled consolidated Skype for Business Server Edge pool, with DNS load balancing, and private IP addresses and NAT</span></span>

<span data-ttu-id="959ac-136">Com este cenário, você poderá ter alta disponibilidade em sua implantação de Borda, o que oferece vantagens de escalabilidade e suporte a failover.</span><span class="sxs-lookup"><span data-stu-id="959ac-136">With this scenario, you are able to have high availability in your Edge deployment, which gives you the advantages of scalability and failover support.</span></span>
  
![Cenário de borda para borda consolidada dimensionada, DNS LB com IP privado usando NAT](../../media/Plan_LyncServer_Edge_Scenario_ScaledConsolidatedEdgeDNSLBPrivateIP.jpg)
  
### <a name="port-diagram"></a><span data-ttu-id="959ac-138">Diagrama de porta</span><span class="sxs-lookup"><span data-stu-id="959ac-138">Port diagram</span></span>

<span data-ttu-id="959ac-139">Também temos um diagrama para pools de bordas consolidadas em escala com balanceamento de carga de DNS.</span><span class="sxs-lookup"><span data-stu-id="959ac-139">We also have a diagram for scaled consolidated Edge pools with DNS load balancing.</span></span>
  
![Perímetro de rede para cenário de Edge com borda consolidada dimensionada usando DNS LB](../../media/Plan_LyncServer_Edge_NetPerimeter_ScaledConsolidatedEdgeDNSLB.jpg)
  
## <a name="scaled-consolidated-skype-for-business-server-edge-pool-with-dns-load-balancing-and-public-ip-addresses"></a><span data-ttu-id="959ac-141">Pool de bordas do Skype for Business Server consolidado com dimensionamento de carga de DNS e endereços IP públicos</span><span class="sxs-lookup"><span data-stu-id="959ac-141">Scaled consolidated Skype for Business Server Edge pool, with DNS load balancing and public IP addresses</span></span>

<span data-ttu-id="959ac-142">Com este cenário, você poderá ter alta disponibilidade em sua implantação de Borda, o que oferece vantagens de escalabilidade e suporte a failover.</span><span class="sxs-lookup"><span data-stu-id="959ac-142">With this scenario, you are able to have high availability in your Edge deployment, which gives you the advantages of scalability and failover support.</span></span>
  
![Cenário de borda para borda consolidada dimensionada, DNS LB com IP público](../../media/Plan_LyncServer_Edge_Scenario_ScaledConsolidatedEdgeDNSLBPublicIP.jpg)
  
### <a name="port-diagram"></a><span data-ttu-id="959ac-144">Diagrama de porta</span><span class="sxs-lookup"><span data-stu-id="959ac-144">Port diagram</span></span>

<span data-ttu-id="959ac-145">Também temos um diagrama para pools de bordas consolidadas em escala com balanceamento de carga de DNS.</span><span class="sxs-lookup"><span data-stu-id="959ac-145">We also have a diagram for scaled consolidated Edge pools with DNS load balancing.</span></span>
  
![Perímetro de rede para cenário de Edge com borda consolidada dimensionada usando DNS LB](../../media/Plan_LyncServer_Edge_NetPerimeter_ScaledConsolidatedEdgeDNSLB.jpg)
  
## <a name="scaled-consolidated-skype-for-business-server-edge-pool-with-hardware-load-balancing"></a><span data-ttu-id="959ac-147">Conjunto de bordas do Skype for Business Server consolidado com balanceamento de carga de hardware</span><span class="sxs-lookup"><span data-stu-id="959ac-147">Scaled consolidated Skype for Business Server Edge pool, with hardware load balancing</span></span>

<span data-ttu-id="959ac-148">Com este cenário, você poderá ter alta disponibilidade em sua implantação de Borda, o que oferece vantagens de escalabilidade e suporte a failover.</span><span class="sxs-lookup"><span data-stu-id="959ac-148">With this scenario, you are able to have high availability in your Edge deployment, which gives you the advantages of scalability and failover support.</span></span>
  
![Cenário de borda para borda consolidada dimensionada com HLB](../../media/Plan_LyncServer_Edge_Scenario_ScaledConsolidatedEdgeHLB.jpg)
 
