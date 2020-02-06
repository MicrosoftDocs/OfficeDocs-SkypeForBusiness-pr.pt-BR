---
title: Plano para Enterprise Voice no Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
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
ms.assetid: fd8d5867-0ac9-47f8-94f0-1c3ee5e25575
description: Noções básicas de planejamento do Enterprise Voice no Skype for Business Server, incluindo sites, regiões, links de rede entre sites e estimativa do tráfego de uso de voz.
ms.openlocfilehash: 7ef2a37a1ab39dd9c2e40544e06cfb995e846f7a
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41802891"
---
# <a name="plan-for-enterprise-voice-in-skype-for-business-server"></a><span data-ttu-id="2b7c4-103">Plano para Enterprise Voice no Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="2b7c4-103">Plan for Enterprise Voice in Skype for Business Server</span></span>
 
<span data-ttu-id="2b7c4-104">Noções básicas de planejamento do Enterprise Voice no Skype for Business Server, incluindo sites, regiões, links de rede entre sites e estimativa do tráfego de uso de voz.</span><span class="sxs-lookup"><span data-stu-id="2b7c4-104">Enterprise Voice planning basics in Skype for Business Server, including sites, regions, network links between sites, and estimating voice usage traffic.</span></span>
  
<span data-ttu-id="2b7c4-105">O processo de implantação do Enterprise Voice depende da topologia existente, da infraestrutura e da funcionalidade do Enterprise Voice às quais você deseja dar suporte.</span><span class="sxs-lookup"><span data-stu-id="2b7c4-105">The deployment process for Enterprise Voice depends on your existing topology, infrastructure, and the Enterprise Voice functionality that you want to support.</span></span> <span data-ttu-id="2b7c4-106">Os procedimentos necessários dependem dos recursos que você escolher, mas há outras considerações de planejamento a fazer em um nível elevado.</span><span class="sxs-lookup"><span data-stu-id="2b7c4-106">The required procedures will depend on what features you choose, but there are other planning considerations that you must make at a high level.</span></span>
  
<span data-ttu-id="2b7c4-107">Em geral, considere o tipo e o número de sites que você deseja implantar e seus locais geográficos, o volume da chamada em cada site, os tipos de links de rede que conectam sites, se você deseja fornecer redundância e failover para funcionalidade de voz para cada e se você deseja usar equipamento PBX existente.</span><span class="sxs-lookup"><span data-stu-id="2b7c4-107">In general, consider the type and number of sites that you want to deploy and their geographical locations, the call volume at each site, the types of network links that connect sites, whether you want to provide redundancy and failover for voice functionality for each site, and whether you want to use existing PBX equipment.</span></span> <span data-ttu-id="2b7c4-108">Há certas considerações, como alta disponibilidade, que você deve considerar ao planejar o Skype for Business Server como um todo.</span><span class="sxs-lookup"><span data-stu-id="2b7c4-108">There are certain considerations, such as high availability, that you should consider when you plan for Skype for Business Server as a whole.</span></span> <span data-ttu-id="2b7c4-109">Essas considerações são discutidas em tópicos em toda esta seção, conforme necessário.</span><span class="sxs-lookup"><span data-stu-id="2b7c4-109">These considerations are discussed in topics throughout this section, as needed.</span></span>
  
## <a name="sites-and-regions"></a><span data-ttu-id="2b7c4-110">Locais e regiões</span><span class="sxs-lookup"><span data-stu-id="2b7c4-110">Sites and regions</span></span>

<span data-ttu-id="2b7c4-111">Em primeiro lugar, identifique os sites na sua topologia em que você vai implantar o Enterprise Voice e as regiões de rede às quais esses sites pertencem.</span><span class="sxs-lookup"><span data-stu-id="2b7c4-111">First, identify the sites in your topology where you will deploy Enterprise Voice and the network regions to which those sites belong.</span></span> <span data-ttu-id="2b7c4-112">Especificamente, considere como será fornecida a conectividade PSTN (rede telefônica pública comutada) a cada site.</span><span class="sxs-lookup"><span data-stu-id="2b7c4-112">In particular, consider how you will provide public switched telephone network (PSTN) connectivity to each site.</span></span> <span data-ttu-id="2b7c4-113">Para motivos de gerenciamento e logística, as regiões às quais esses sites pertencem podem ser um fator decisivo.</span><span class="sxs-lookup"><span data-stu-id="2b7c4-113">For manageability and logistical reasons, the regions to which these sites belong can be a deciding factor.</span></span> <span data-ttu-id="2b7c4-114">Decida onde os gateways serão implantados localmente, onde utensílios de ramificação sobreviventes (SBAs) serão implantados e onde você pode configurar troncos SIP (localmente ou no site central) para um provedor de serviços de telefonia pela Internet (ITSP).</span><span class="sxs-lookup"><span data-stu-id="2b7c4-114">Decide where gateways will be deployed locally, where Survivable Branch Appliances (SBAs) will be deployed, and where you can configure SIP trunks (either locally or at the central site) to an Internet telephony service provider (ITSP).</span></span>
  
## <a name="network-links-between-sites"></a><span data-ttu-id="2b7c4-115">Links de rede entre locais</span><span class="sxs-lookup"><span data-stu-id="2b7c4-115">Network links between sites</span></span>

<span data-ttu-id="2b7c4-116">Você também precisa considerar o uso de largura de banda esperado nos links de rede entre o seu site central e seus sites de filiais.</span><span class="sxs-lookup"><span data-stu-id="2b7c4-116">You also need to consider the bandwidth usage that you expect on the network links between your central site and its branch sites.</span></span> <span data-ttu-id="2b7c4-117">Se você tem, ou planeja implantar, links de WAN resistentes entre sites, recomendamos que implante um gateway em cada site de filial para fornecer cancelamento local direto do Direct Inward (DID) para usuários naqueles sites.</span><span class="sxs-lookup"><span data-stu-id="2b7c4-117">If you have, or plan to deploy, resilient WAN links between sites, we recommend that you deploy a gateway at each branch site to provide local direct inward dial (DID) termination for users at those sites.</span></span> <span data-ttu-id="2b7c4-118">Se você tiver links WAN resilientes, mas a largura de banda em um link WAN provavelmente for restrita, configure o controle de admissão de chamada para esse link.</span><span class="sxs-lookup"><span data-stu-id="2b7c4-118">If you have resilient WAN links, but the bandwidth on a WAN link is likely to be constrained, configure call admission control for that link.</span></span> <span data-ttu-id="2b7c4-119">Se você não tiver links de WAN resilientes, hospede menos de 1000 usuários no seu site de filial e não tiver administradores do Skype for Business Server treinados, recomendamos que você implante um aparelho de ramificação sobreviventes no site da filial.</span><span class="sxs-lookup"><span data-stu-id="2b7c4-119">If you do not have resilient WAN links, host fewer than 1000 users at your branch site, and do not have local trained Skype for Business Server administrators available, we recommend that you deploy a Survivable Branch Appliance at the branch site.</span></span> <span data-ttu-id="2b7c4-120">Se você estiver hospedando entre os usuários do 1000 e do 5000 no seu site da sua filial, não há uma conexão WAN resistente e tiver os administradores do Skype for Business Server treinados, recomendamos implantar um servidor de ramificação sobreviventes com um pequeno gateway no site da filial.</span><span class="sxs-lookup"><span data-stu-id="2b7c4-120">If you host between 1000 and 5000 users at your branch site, lack a resilient WAN connection, and have trained Skype for Business Server administrators available, we recommend that you deploy a Survivable Branch Server with a small gateway at the branch site.</span></span> <span data-ttu-id="2b7c4-121">Considere também a habilitação de bypass de mídia em links restritos se você tiver um gateway par que suporte bypass de mídia.</span><span class="sxs-lookup"><span data-stu-id="2b7c4-121">Consider also enabling media bypass on constrained links if you have a gateway peer that supports media bypass.</span></span>
  
## <a name="estimating-voice-usage-and-traffic"></a><span data-ttu-id="2b7c4-122">Estimando uso e tráfego de voz</span><span class="sxs-lookup"><span data-stu-id="2b7c4-122">Estimating voice usage and traffic</span></span>

<span data-ttu-id="2b7c4-123">O Microsoft Lync Server 2013, ferramenta de planejamento usa a métrica a seguir para estimar o tráfego do usuário em cada site e o número de portas necessárias para dar suporte a esse tráfego.</span><span class="sxs-lookup"><span data-stu-id="2b7c4-123">The Microsoft Lync Server 2013, Planning Tool uses the following metric to estimate user traffic at each site and the number of ports that are required to support that traffic.</span></span>
  
> <span data-ttu-id="2b7c4-124">No caso de **Tráfego leve** (uma chamada PSTN por usuário por hora), calcula-se 15 usuários por porta.</span><span class="sxs-lookup"><span data-stu-id="2b7c4-124">For **Light traffic** (one PSTN call per user per hour), figure 15 users per port.</span></span>
> 
> <span data-ttu-id="2b7c4-125">No caso de **Tráfego médio** (duas chamadas PSTN por usuário por hora), calcula-se 10 usuários por porta.</span><span class="sxs-lookup"><span data-stu-id="2b7c4-125">For **Medium traffic** (2 PSTN calls per user per hour), figure 10 users per port.</span></span>
> 
> <span data-ttu-id="2b7c4-126">No caso de **Tráfego pesado** (três ou mais chamadas PSTN por usuário por hora), calcula-se 5 usuários por porta.</span><span class="sxs-lookup"><span data-stu-id="2b7c4-126">For **Heavy traffic** (3 or more PSTN per user calls per hour), figure 5 users per port.</span></span>
    
<span data-ttu-id="2b7c4-127">O número de portas, por sua vez, determina o número de servidores e gateways de mediação que serão necessários.</span><span class="sxs-lookup"><span data-stu-id="2b7c4-127">The number of ports in turn determines the number of Mediation Servers and gateways that will be required.</span></span> <span data-ttu-id="2b7c4-128">Os gateways de rede telefônica pública comutada (PSTN) que a maioria das organizações considera implantando o tamanho de duas portas para até 960 portas.</span><span class="sxs-lookup"><span data-stu-id="2b7c4-128">The public switched telephone network (PSTN) gateways that most organizations consider deploying range in size from 2 ports to as many as 960 ports.</span></span> <span data-ttu-id="2b7c4-129">(Ainda há gateways maiores, mas eles são usados principalmente por provedores de serviços de telefonia.)</span><span class="sxs-lookup"><span data-stu-id="2b7c4-129">(There are even larger gateways, but these are used mainly by telephony service providers.)</span></span>
  
<span data-ttu-id="2b7c4-p106">Por exemplo, uma organização com 10.000 usuários e tráfego médio exigiria 1000 portas. O número de gateways necessário seria igual o número total de portas necessárias, conforme determinado pela capacidade total dos gateways.</span><span class="sxs-lookup"><span data-stu-id="2b7c4-p106">For example, an organization with 10,000 users and medium traffic would require 1000 ports. The number of gateways required would equal the total number of ports required as determined by the total capacity of the gateways.</span></span>
  
## <a name="components-features-and-options-of-enterprise-voice"></a><span data-ttu-id="2b7c4-132">Componentes, recursos e opções do Enterprise Voice</span><span class="sxs-lookup"><span data-stu-id="2b7c4-132">Components, features, and options of Enterprise Voice</span></span>

<span data-ttu-id="2b7c4-133">Confira as seções a seguir para obter mais informações sobre como planejar a implantação do Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="2b7c4-133">See the following sections for more information on planning your Enterprise Voice deployment.</span></span>
  
- [<span data-ttu-id="2b7c4-134">Componentes necessários para o Enterprise Voice no Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="2b7c4-134">Components required for Enterprise Voice in Skype for Business Server</span></span>](components-required-for-enterprise-voice.md)
    
- [<span data-ttu-id="2b7c4-135">Planejar a conectividade PSTN no Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="2b7c4-135">Plan for PSTN connectivity in Skype for Business Server</span></span>](pstn-connectivity-0.md)
    
- [<span data-ttu-id="2b7c4-136">Configurações de rede para os recursos avançados de voz empresarial no Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="2b7c4-136">Network settings for the advanced Enterprise Voice features in Skype for Business Server</span></span>](network-settings-for-advanced-features.md)
    
- [<span data-ttu-id="2b7c4-137">Planejar o controle de admissão de chamadas no Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="2b7c4-137">Plan for call admission control in Skype for Business Server</span></span>](call-admission-control.md)
    
- [<span data-ttu-id="2b7c4-138">Planejar serviços de emergência no Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="2b7c4-138">Plan for emergency services in Skype for Business Server</span></span>](emergency-services.md)
    
- [<span data-ttu-id="2b7c4-139">Planejar a bypass de mídia no Skype for Business</span><span class="sxs-lookup"><span data-stu-id="2b7c4-139">Plan for media bypass in Skype for Business</span></span>](media-bypass.md)
    
- [<span data-ttu-id="2b7c4-140">Planejar linhas telefônicas particulares com o Skype for Business</span><span class="sxs-lookup"><span data-stu-id="2b7c4-140">Plan for private telephone lines with Skype for Business</span></span>](private-telephone-lines.md)
    
- [<span data-ttu-id="2b7c4-141">Planejar o roteamento baseado em localização no Skype for Business</span><span class="sxs-lookup"><span data-stu-id="2b7c4-141">Plan for Location-Based Routing in Skype for Business</span></span>](location-based-routing.md)
    
- [<span data-ttu-id="2b7c4-142">Planejar os recursos de gerenciamento de chamadas no Skype for Business</span><span class="sxs-lookup"><span data-stu-id="2b7c4-142">Plan for call management features in Skype for Business</span></span>](call-management-features.md)
    
- [<span data-ttu-id="2b7c4-143">Plan for Enterprise Voice resiliency in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="2b7c4-143">Plan for Enterprise Voice resiliency in Skype for Business Server</span></span>](enterprise-voice-resiliency.md)
    

