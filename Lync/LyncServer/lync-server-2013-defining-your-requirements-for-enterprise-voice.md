---
title: 'Lync Server 2013: Definindo seus requisitos para Enterprise Voice'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Defining your organization's requirements for Enterprise Voice
ms:assetid: 3310f78e-c658-4557-95fa-159ce3c22953
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425826(v=OCS.15)
ms:contentKeyID: 48183816
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f0ce05c39e3433ff949d82f583207aebfba871fc
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34829682"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="defining-your-requirements-for-enterprise-voice-in-lync-server-2013"></a><span data-ttu-id="9984e-102">Definindo seus requisitos para Enterprise Voice no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9984e-102">Defining your requirements for Enterprise Voice in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9984e-103">_**Tópico da última modificação:** 2012-08-07_</span><span class="sxs-lookup"><span data-stu-id="9984e-103">_**Topic Last Modified:** 2012-08-07_</span></span>

<span data-ttu-id="9984e-104">Este tópico fornece uma visão geral das considerações que você precisa fazer sobre as regiões, sites e os links entre sites na sua topologia e como eles são importantes ao implantar o Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="9984e-104">This topic provides an overview of the considerations you need to make about the regions, sites, and the links between sites in your topology and how those are important when you deploy Enterprise Voice.</span></span> <span data-ttu-id="9984e-105">Para obter detalhes sobre como fazer essas decisões, consulte [configurações de rede para os recursos avançados de voz empresarial no Lync Server 2013](lync-server-2013-network-settings-for-the-advanced-enterprise-voice-features.md) na documentação de planejamento.</span><span class="sxs-lookup"><span data-stu-id="9984e-105">For details to help you make these decisions, see [Network settings for the advanced Enterprise Voice features in Lync Server 2013](lync-server-2013-network-settings-for-the-advanced-enterprise-voice-features.md) in the Planning documentation.</span></span>

<div>

## <a name="sites-and-regions"></a><span data-ttu-id="9984e-106">Sites e regiões</span><span class="sxs-lookup"><span data-stu-id="9984e-106">Sites and Regions</span></span>

<span data-ttu-id="9984e-107">Em primeiro lugar, identifique os sites na sua topologia em que você vai implantar o Enterprise Voice e as regiões de rede às quais esses sites pertencem.</span><span class="sxs-lookup"><span data-stu-id="9984e-107">First, identify the sites in your topology where you will deploy Enterprise Voice and the network regions to which those sites belong.</span></span> <span data-ttu-id="9984e-108">Especificamente, considere como será fornecida a conectividade PSTN (rede telefônica pública comutada) a cada site.</span><span class="sxs-lookup"><span data-stu-id="9984e-108">In particular, consider how you will provide public switched telephone network (PSTN) connectivity to each site.</span></span> <span data-ttu-id="9984e-109">Para motivos de gerenciamento e logística, as regiões às quais esses sites pertencem podem ser um fator decisivo.</span><span class="sxs-lookup"><span data-stu-id="9984e-109">For manageability and logistical reasons, the regions to which these sites belong can be a deciding factor.</span></span> <span data-ttu-id="9984e-110">Decida onde os gateways serão implantados localmente, onde utensílios de ramificação sobreviventes (SBAs) serão implantados e onde você pode configurar troncos SIP (localmente ou no site central) para um provedor de serviços de telefonia pela Internet (ITSP).</span><span class="sxs-lookup"><span data-stu-id="9984e-110">Decide where gateways will be deployed locally, where Survivable Branch Appliances (SBAs) will be deployed, and where you can configure SIP trunks (either locally or at the central site) to an Internet telephony service provider (ITSP).</span></span>

</div>

<div>

## <a name="network-links-between-sites"></a><span data-ttu-id="9984e-111">Links de rede entre sites</span><span class="sxs-lookup"><span data-stu-id="9984e-111">Network Links Between Sites</span></span>

<span data-ttu-id="9984e-112">Você também precisa considerar o uso de largura de banda esperado nos links de rede entre o seu site central e seus sites de filiais.</span><span class="sxs-lookup"><span data-stu-id="9984e-112">You also need to consider the bandwidth usage that you expect on the network links between your central site and its branch sites.</span></span> <span data-ttu-id="9984e-113">Se você tem, ou planeja implantar, links de WAN resistentes entre sites, recomendamos que implante um gateway em cada site de filial para fornecer cancelamento local direto do Direct Inward (DID) para usuários naqueles sites.</span><span class="sxs-lookup"><span data-stu-id="9984e-113">If you have, or plan to deploy, resilient WAN links between sites, we recommend that you deploy a gateway at each branch site to provide local direct inward dial (DID) termination for users at those sites.</span></span> <span data-ttu-id="9984e-114">Se você tiver links WAN resilientes, mas a largura de banda em um link WAN provavelmente for restrita, configure o controle de admissão de chamada para esse link.</span><span class="sxs-lookup"><span data-stu-id="9984e-114">If you have resilient WAN links, but the bandwidth on a WAN link is likely to be constrained, configure call admission control for that link.</span></span> <span data-ttu-id="9984e-115">Se você não tiver links de WAN resilientes, hospede menos de 1000 usuários no seu site da sua filial e não tiver administradores do Lync Server treinados disponíveis, recomendamos que você implante um aparelho de ramificação sobreviventes no site da filial.</span><span class="sxs-lookup"><span data-stu-id="9984e-115">If you do not have resilient WAN links, host fewer than 1000 users at your branch site, and do not have local trained Lync Server administrators available, we recommend that you deploy a Survivable Branch Appliance at the branch site.</span></span> <span data-ttu-id="9984e-116">Se você estiver hospedando entre os usuários do 1000 e do 5000 no seu site da sua filial, sem conexão de WAN resistente e os administradores do Lync Server treinados estiverem disponíveis, recomendamos que você implante um servidor de ramificação sobreviventes com um pequeno gateway no site da filial.</span><span class="sxs-lookup"><span data-stu-id="9984e-116">If you host between 1000 and 5000 users at your branch site, lack a resilient WAN connection, and have trained Lync Server administrators available, we recommend that you deploy a Survivable Branch Server with a small gateway at the branch site.</span></span> <span data-ttu-id="9984e-117">Considere também a habilitação de bypass de mídia em links restritos se você tiver um gateway par que suporte bypass de mídia.</span><span class="sxs-lookup"><span data-stu-id="9984e-117">Consider also enabling media bypass on constrained links if you have a gateway peer that supports media bypass.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="9984e-118">Confira também</span><span class="sxs-lookup"><span data-stu-id="9984e-118">See Also</span></span>


[<span data-ttu-id="9984e-119">Network settings for the advanced Enterprise Voice features in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9984e-119">Network settings for the advanced Enterprise Voice features in Lync Server 2013</span></span>](lync-server-2013-network-settings-for-the-advanced-enterprise-voice-features.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

