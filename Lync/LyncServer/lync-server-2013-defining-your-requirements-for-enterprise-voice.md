---
title: 'Lync Server 2013: definindo seus requisitos para o Enterprise Voice'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Defining your organization's requirements for Enterprise Voice
ms:assetid: 3310f78e-c658-4557-95fa-159ce3c22953
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425826(v=OCS.15)
ms:contentKeyID: 48183816
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d88a70796282fe09941ce7632d8c13258defc515
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42032153"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="defining-your-requirements-for-enterprise-voice-in-lync-server-2013"></a><span data-ttu-id="4f669-102">Definindo seus requisitos para o Enterprise Voice no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4f669-102">Defining your requirements for Enterprise Voice in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4f669-103">_**Última modificação do tópico:** 2012-08-07_</span><span class="sxs-lookup"><span data-stu-id="4f669-103">_**Topic Last Modified:** 2012-08-07_</span></span>

<span data-ttu-id="4f669-104">Este tópico fornece uma visão geral das considerações que você precisa tomar sobre as regiões, sites e os links entre sites em sua topologia e como eles são importantes ao implantar o Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="4f669-104">This topic provides an overview of the considerations you need to make about the regions, sites, and the links between sites in your topology and how those are important when you deploy Enterprise Voice.</span></span> <span data-ttu-id="4f669-105">Para obter detalhes para ajudá-lo a tomar essas decisões, consulte [Network Settings for the Advanced Enterprise Voice Features in Lync Server 2013](lync-server-2013-network-settings-for-the-advanced-enterprise-voice-features.md) na documentação de planejamento.</span><span class="sxs-lookup"><span data-stu-id="4f669-105">For details to help you make these decisions, see [Network settings for the advanced Enterprise Voice features in Lync Server 2013](lync-server-2013-network-settings-for-the-advanced-enterprise-voice-features.md) in the Planning documentation.</span></span>

<div>

## <a name="sites-and-regions"></a><span data-ttu-id="4f669-106">Sites e regiões</span><span class="sxs-lookup"><span data-stu-id="4f669-106">Sites and Regions</span></span>

<span data-ttu-id="4f669-107">Primeiro, identifique os sites em sua topologia onde você implantará o Enterprise Voice e as regiões de rede às quais esses sites pertencem.</span><span class="sxs-lookup"><span data-stu-id="4f669-107">First, identify the sites in your topology where you will deploy Enterprise Voice and the network regions to which those sites belong.</span></span> <span data-ttu-id="4f669-108">Especificamente, considere como será fornecida a conectividade PSTN (rede telefônica pública comutada) a cada site.</span><span class="sxs-lookup"><span data-stu-id="4f669-108">In particular, consider how you will provide public switched telephone network (PSTN) connectivity to each site.</span></span> <span data-ttu-id="4f669-109">Para motivos de gerenciamento e logística, as regiões às quais esses sites pertencem podem ser um fator decisivo.</span><span class="sxs-lookup"><span data-stu-id="4f669-109">For manageability and logistical reasons, the regions to which these sites belong can be a deciding factor.</span></span> <span data-ttu-id="4f669-110">Decida onde os gateways serão implantados localmente, onde os aparelhos de filial persistentes (SBAs) serão implantados e onde você pode configurar troncos SIP (localmente ou no site central) para um provedor de serviços de telefonia da Internet (ITSP).</span><span class="sxs-lookup"><span data-stu-id="4f669-110">Decide where gateways will be deployed locally, where Survivable Branch Appliances (SBAs) will be deployed, and where you can configure SIP trunks (either locally or at the central site) to an Internet telephony service provider (ITSP).</span></span>

</div>

<div>

## <a name="network-links-between-sites"></a><span data-ttu-id="4f669-111">Links de rede entre sites</span><span class="sxs-lookup"><span data-stu-id="4f669-111">Network Links Between Sites</span></span>

<span data-ttu-id="4f669-112">Você também precisa considerar o uso da largura de banda que você espera nos links de rede entre seu site central e seus sites de filial.</span><span class="sxs-lookup"><span data-stu-id="4f669-112">You also need to consider the bandwidth usage that you expect on the network links between your central site and its branch sites.</span></span> <span data-ttu-id="4f669-113">Se você tem ou planeja implantar links de WAN resilientes entre sites, recomendamos que você implante um gateway em cada site de filial para fornecer finalidades de discagem direta local (DID) para usuários nesses sites.</span><span class="sxs-lookup"><span data-stu-id="4f669-113">If you have, or plan to deploy, resilient WAN links between sites, we recommend that you deploy a gateway at each branch site to provide local direct inward dial (DID) termination for users at those sites.</span></span> <span data-ttu-id="4f669-114">Se você tiver links WAN resilientes, mas a largura de banda em um link WAN provavelmente for restrita, configure o controle de admissão de chamada para esse link.</span><span class="sxs-lookup"><span data-stu-id="4f669-114">If you have resilient WAN links, but the bandwidth on a WAN link is likely to be constrained, configure call admission control for that link.</span></span> <span data-ttu-id="4f669-115">Se você não tiver links de WAN resistentes, hospede menos de 1000 usuários no seu site de filial e não tiver administradores do Lync Server treinados e locais disponíveis, recomendamos que você implante um aparelho de filial persistente no site de filial.</span><span class="sxs-lookup"><span data-stu-id="4f669-115">If you do not have resilient WAN links, host fewer than 1000 users at your branch site, and do not have local trained Lync Server administrators available, we recommend that you deploy a Survivable Branch Appliance at the branch site.</span></span> <span data-ttu-id="4f669-116">Se você hospedar entre 1000 e 5000 usuários no seu site de filial, sem uma conexão WAN resiliente e tiver administradores treinados do Lync Server disponíveis, recomendamos implantar um servidor de filial persistente com um pequeno gateway no site de filial.</span><span class="sxs-lookup"><span data-stu-id="4f669-116">If you host between 1000 and 5000 users at your branch site, lack a resilient WAN connection, and have trained Lync Server administrators available, we recommend that you deploy a Survivable Branch Server with a small gateway at the branch site.</span></span> <span data-ttu-id="4f669-117">Considere também a habilitação de bypass de mídia em links restritos se você tiver um gateway par que suporte bypass de mídia.</span><span class="sxs-lookup"><span data-stu-id="4f669-117">Consider also enabling media bypass on constrained links if you have a gateway peer that supports media bypass.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="4f669-118">Confira também</span><span class="sxs-lookup"><span data-stu-id="4f669-118">See Also</span></span>


[<span data-ttu-id="4f669-119">Configurações de rede para os recursos avançados do Enterprise Voice no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4f669-119">Network settings for the advanced Enterprise Voice features in Lync Server 2013</span></span>](lync-server-2013-network-settings-for-the-advanced-enterprise-voice-features.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

