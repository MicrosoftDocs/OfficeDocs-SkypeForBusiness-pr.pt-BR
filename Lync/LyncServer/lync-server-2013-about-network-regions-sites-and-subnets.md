---
title: 'Lync Server 2013: sobre regiões de rede, sites e sub-redes'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: About network regions, sites, and subnets
ms:assetid: 6662123a-d011-408c-a290-92b2a8589943
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398467(v=OCS.15)
ms:contentKeyID: 48184335
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c8e4ee7d3f5a8976f8a4eee972be2d995f89c36c
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42199294"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="about-network-regions-sites-and-subnets-in-lync-server-2013"></a><span data-ttu-id="a9544-102">Sobre regiões de rede, sites e sub-redes no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a9544-102">About network regions, sites, and subnets in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a9544-103">_**Última modificação do tópico:** 2013-02-24_</span><span class="sxs-lookup"><span data-stu-id="a9544-103">_**Topic Last Modified:** 2013-02-24_</span></span>

<span data-ttu-id="a9544-104">Os recursos avançados do Enterprise Voice descritos nesta seção compartilham determinados requisitos de configuração para regiões de rede, sites de rede e sub-redes.</span><span class="sxs-lookup"><span data-stu-id="a9544-104">The advanced Enterprise Voice features described in this section share certain configuration requirements for network regions, network sites, and subnets.</span></span> <span data-ttu-id="a9544-105">Por exemplo, todos os três recursos avançados exigem que cada sub-rede em sua topologia seja associada a um *site de rede*específico e cada local de rede deve estar associado a uma *região de rede*.</span><span class="sxs-lookup"><span data-stu-id="a9544-105">For example, all three advanced features require that each subnet in your topology be associated with a specific *network site*, and each network site must be associated with a *network region*.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="a9544-106">Antes de iniciar a configuração de rede para controle de admissão de chamada, E9-1-1 ou desvio de mídia, verifique se você analisou informações adicionais sobre as configurações de rede nas configurações de rede do tópico <A href="lync-server-2013-network-settings-for-the-advanced-enterprise-voice-features.md">recursos avançados do Enterprise Voice no Lync Server 2013</A> na documentação de planejamento.</span><span class="sxs-lookup"><span data-stu-id="a9544-106">Before you begin network configuration for call admission control, E9-1-1, or media bypass, make sure that you reviewed additional information about network settings in the <A href="lync-server-2013-network-settings-for-the-advanced-enterprise-voice-features.md">Network settings for the advanced Enterprise Voice features in Lync Server 2013</A> topic in the Planning documentation.</span></span> <span data-ttu-id="a9544-107">Para obter detalhes sobre a configuração de rede primariamente sobre o controle de admissão de chamadas, confira a <A href="lync-server-2013-defining-your-requirements-for-call-admission-control.md">definição de seus requisitos para controle de admissão de chamadas no Lync Server 2013</A> na documentação de planejamento.</span><span class="sxs-lookup"><span data-stu-id="a9544-107">For details about network configuration primarily about call admission control, also see <A href="lync-server-2013-defining-your-requirements-for-call-admission-control.md">Defining your requirements for call admission control in Lync Server 2013</A> in the Planning documentation.</span></span>



</div>

<span data-ttu-id="a9544-108">O controle de admissão de chamada e o E9-1-1 têm requisitos adicionais de configuração para sites de rede:</span><span class="sxs-lookup"><span data-stu-id="a9544-108">Call admission control and E9-1-1 have additional configuration requirements for network sites:</span></span>

  - <span data-ttu-id="a9544-109">O controle de admissão de chamadas exige que um *perfil de política de largura de banda* seja especificado para cada site restrito por limitações de largura de banda de WAN.</span><span class="sxs-lookup"><span data-stu-id="a9544-109">Call admission control requires that a *bandwidth policy profile* be specified for each site that is constrained by WAN bandwidth limitations.</span></span> <span data-ttu-id="a9544-110">Se você planeja implantar o controle de admissão de chamadas, você deve [criar perfis de política de largura de banda no Lync Server 2013](lync-server-2013-create-bandwidth-policy-profiles.md) antes de configurar seus sites de rede.</span><span class="sxs-lookup"><span data-stu-id="a9544-110">If you plan to deploy call admission control, you must [Create bandwidth policy profiles in Lync Server 2013](lync-server-2013-create-bandwidth-policy-profiles.md) before you configure your network sites.</span></span>

  - <span data-ttu-id="a9544-111">E9-1-1 requer que uma *política de local* seja especificada para cada site.</span><span class="sxs-lookup"><span data-stu-id="a9544-111">E9-1-1 requires that a *location policy* be specified for each site.</span></span> <span data-ttu-id="a9544-112">Se você planeja implantar o E9-1-1, você deve [criar políticas de local no Lync Server 2013](lync-server-2013-create-location-policies.md) antes de configurar seus sites de rede.</span><span class="sxs-lookup"><span data-stu-id="a9544-112">If you plan to deploy E9-1-1, you must [Create location policies in Lync Server 2013](lync-server-2013-create-location-policies.md) before you configure your network sites.</span></span>

<div>

## <a name="create-or-modify-network-regions-network-sites-and-subnets"></a><span data-ttu-id="a9544-113">Criar ou modificar regiões de rede, sites de rede e sub-redes</span><span class="sxs-lookup"><span data-stu-id="a9544-113">Create or Modify Network Regions, Network Sites, and Subnets</span></span>

<span data-ttu-id="a9544-114">Os tópicos a seguir fornecem etapas para criar ou modificar regiões de rede e sites de rede e para associar sub-redes a sites de rede.</span><span class="sxs-lookup"><span data-stu-id="a9544-114">The following topics provide steps to create or modify network regions and network sites, and to associate subnets with network sites.</span></span> <span data-ttu-id="a9544-115">Esses tópicos não são específicos de qualquer recurso avançado do Enterprise Voice específico.</span><span class="sxs-lookup"><span data-stu-id="a9544-115">These topics are not specific to any particular advanced Enterprise Voice feature.</span></span>

  - [<span data-ttu-id="a9544-116">Criar ou modificar uma região de rede no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a9544-116">Create or modify a network region in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-a-network-region.md)

  - [<span data-ttu-id="a9544-117">Criar ou modificar um site de rede no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a9544-117">Create or modify a network site in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-a-network-site.md)

  - [<span data-ttu-id="a9544-118">Associar uma sub-rede a um site de rede no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a9544-118">Associate a subnet with a network site in Lync Server 2013</span></span>](lync-server-2013-associate-a-subnet-with-a-network-site.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

