---
title: 'Lync Server 2013: planejando para Enterprise Voice'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Planning for Enterprise Voice
ms:assetid: fd8d5867-0ac9-47f8-94f0-1c3ee5e25575
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg413081(v=OCS.15)
ms:contentKeyID: 48185959
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 29732d1690e1934f811df6fc448596e987205791
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34824845"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="planning-for-enterprise-voice-in-lync-server-2013"></a><span data-ttu-id="5b8ee-102">Planejando para Enterprise Voice no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5b8ee-102">Planning for Enterprise Voice in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5b8ee-103">_**Tópico da última modificação:** 2013-11-01_</span><span class="sxs-lookup"><span data-stu-id="5b8ee-103">_**Topic Last Modified:** 2013-11-01_</span></span>

<span data-ttu-id="5b8ee-104">O processo de implantação do Enterprise Voice depende da topologia existente, da infraestrutura e da funcionalidade do Enterprise Voice às quais você deseja dar suporte.</span><span class="sxs-lookup"><span data-stu-id="5b8ee-104">The deployment process for Enterprise Voice depends on your existing topology, infrastructure, and the Enterprise Voice functionality that you want to support.</span></span> <span data-ttu-id="5b8ee-105">Os procedimentos necessários dependem dos recursos que você escolher, mas há outras considerações de planejamento a fazer em um nível elevado.</span><span class="sxs-lookup"><span data-stu-id="5b8ee-105">The required procedures will depend on what features you choose, but there are other planning considerations that you must make at a high level.</span></span>

<span data-ttu-id="5b8ee-106">Em geral, considere o tipo e o número de sites que você deseja implantar e seus locais geográficos, o volume da chamada em cada site, os tipos de links de rede que conectam sites, se você deseja fornecer redundância e failover para funcionalidade de voz para cada e se você deseja usar equipamento PBX existente.</span><span class="sxs-lookup"><span data-stu-id="5b8ee-106">In general, consider the type and number of sites that you want to deploy and their geographical locations, the call volume at each site, the types of network links that connect sites, whether you want to provide redundancy and failover for voice functionality for each site, and whether you want to use existing PBX equipment.</span></span> <span data-ttu-id="5b8ee-107">Há certas considerações, como alta disponibilidade, que você deve considerar ao planejar o software de comunicação do Lync Server como um todo.</span><span class="sxs-lookup"><span data-stu-id="5b8ee-107">There are certain considerations, such as high availability, that you should consider when you plan for Lync Server  communications software as a whole.</span></span> <span data-ttu-id="5b8ee-108">Essas considerações são discutidas em tópicos em toda esta seção, conforme necessário.</span><span class="sxs-lookup"><span data-stu-id="5b8ee-108">These considerations are discussed in topics throughout this section, as needed.</span></span>

<div>

## <a name="planning-considerations"></a><span data-ttu-id="5b8ee-109">Considerações de planejamento</span><span class="sxs-lookup"><span data-stu-id="5b8ee-109">Planning Considerations</span></span>

<span data-ttu-id="5b8ee-110">Para decisões de planejamento que pertencem à implantação de uma determinada funcionalidade ou componente de voz ou componente da empresa, consulte os tópicos desta seção.</span><span class="sxs-lookup"><span data-stu-id="5b8ee-110">For planning decisions that pertain to the deployment of a particular Enterprise Voice capability or deployment scenario or component, consult the topics in this section.</span></span>

  - [<span data-ttu-id="5b8ee-111">Definindo seus requisitos para Enterprise Voice no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5b8ee-111">Defining your requirements for Enterprise Voice in Lync Server 2013</span></span>](lync-server-2013-defining-your-requirements-for-enterprise-voice.md)

  - [<span data-ttu-id="5b8ee-112">Estimando uso e tráfego de voz para Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5b8ee-112">Estimating voice usage and traffic for Lync Server 2013</span></span>](lync-server-2013-estimating-voice-usage-and-traffic.md)

  - [<span data-ttu-id="5b8ee-113">Network settings for the advanced Enterprise Voice features in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5b8ee-113">Network settings for the advanced Enterprise Voice features in Lync Server 2013</span></span>](lync-server-2013-network-settings-for-the-advanced-enterprise-voice-features.md)

  - [<span data-ttu-id="5b8ee-114">Components required for Enterprise Voice in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5b8ee-114">Components required for Enterprise Voice in Lync Server 2013</span></span>](lync-server-2013-components-required-for-enterprise-voice.md)

  - [<span data-ttu-id="5b8ee-115">Planejamento para resiliência do Enterprise Voice no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5b8ee-115">Planning for Enterprise Voice resiliency in Lync Server 2013</span></span>](lync-server-2013-planning-for-enterprise-voice-resiliency.md)

  - [<span data-ttu-id="5b8ee-116">Planejamento para integração de Unificação de Mensagens do Exchange no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5b8ee-116">Planning for Exchange Unified Messaging integration in Lync Server 2013</span></span>](lync-server-2013-planning-for-exchange-unified-messaging-integration.md)

  - [<span data-ttu-id="5b8ee-117">Planejamento para controle de admissão de chamada no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5b8ee-117">Planning for call admission control in Lync Server 2013</span></span>](lync-server-2013-planning-for-call-admission-control.md)

  - [<span data-ttu-id="5b8ee-118">Planejamento para serviços de emergência (E9-1-1) no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5b8ee-118">Planning for emergency services (E9-1-1) in Lync Server 2013</span></span>](lync-server-2013-planning-for-emergency-services-e9-1-1.md)

  - [<span data-ttu-id="5b8ee-119">Planejamento de bypass de mídia no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5b8ee-119">Planning for media bypass in Lync Server 2013</span></span>](lync-server-2013-planning-for-media-bypass.md)

  - [<span data-ttu-id="5b8ee-120">Planejando linhas telefônicas particulares com o Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5b8ee-120">Planning for private telephone lines with Lync Server 2013</span></span>](lync-server-2013-planning-for-private-telephone-lines.md)

  - [<span data-ttu-id="5b8ee-121">Planejamento de Roteamento Baseado em Local no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5b8ee-121">Planning for Location-Based Routing in Lync Server 2013</span></span>](lync-server-2013-planning-for-location-based-routing.md)

  - [<span data-ttu-id="5b8ee-122">Planejamento para resiliência do Enterprise Voice no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5b8ee-122">Planning for Enterprise Voice resiliency in Lync Server 2013</span></span>](lync-server-2013-planning-for-enterprise-voice-resiliency.md)

  - [<span data-ttu-id="5b8ee-123">Orientações de implantação para Enterprise Voice no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5b8ee-123">Deployment guidelines for Enterprise Voice in Lync Server 2013</span></span>](lync-server-2013-deployment-guidelines-for-enterprise-voice.md)

  - [<span data-ttu-id="5b8ee-124">Visão geral do processo de implantação para Enterprise Voice no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5b8ee-124">Deployment process overview for Enterprise Voice in Lync Server 2013</span></span>](lync-server-2013-deployment-process-overview-for-enterprise-voice.md)

  - [<span data-ttu-id="5b8ee-125">Movendo usuários para o Enterprise Voice no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5b8ee-125">Moving users to Enterprise Voice in Lync Server 2013</span></span>](lync-server-2013-moving-users-to-enterprise-voice.md)

  - [<span data-ttu-id="5b8ee-126">Ferramenta de diagnóstico de chamadas do Lync no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5b8ee-126">Lync PreCall Diagnostics Tool in Lync Server 2013</span></span>](lync-server-2013-lync-precall-diagnostics-tool.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

