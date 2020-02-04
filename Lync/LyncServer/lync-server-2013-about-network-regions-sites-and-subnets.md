---
title: 'Lync Server 2013: Sobre regiões de rede, sites e subredes'
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
ms.openlocfilehash: 1f85d392f7d5f987bf14197fd5027c6568965ae8
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41723421"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="about-network-regions-sites-and-subnets-in-lync-server-2013"></a><span data-ttu-id="44530-102">Sobre regiões de rede, sites e subredes no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="44530-102">About network regions, sites, and subnets in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="44530-103">_**Tópico da última modificação:** 2013-02-24_</span><span class="sxs-lookup"><span data-stu-id="44530-103">_**Topic Last Modified:** 2013-02-24_</span></span>

<span data-ttu-id="44530-104">Os recursos avançados de voz empresarial descritos nesta seção compartilham determinados requisitos de configuração para regiões de rede, sites de rede e sub-redes.</span><span class="sxs-lookup"><span data-stu-id="44530-104">The advanced Enterprise Voice features described in this section share certain configuration requirements for network regions, network sites, and subnets.</span></span> <span data-ttu-id="44530-105">Por exemplo, todos os três recursos avançados exigem que cada sub-rede na sua topologia seja associada a um *site de rede*específico, e cada site de rede deve estar associado a uma *região de rede*.</span><span class="sxs-lookup"><span data-stu-id="44530-105">For example, all three advanced features require that each subnet in your topology be associated with a specific *network site*, and each network site must be associated with a *network region*.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="44530-106">Antes de iniciar a configuração de rede para o controle de admissão de chamadas, o E9-1-1 ou o bypass de mídia, verifique se você revisou informações adicionais sobre as configurações de rede nas <A href="lync-server-2013-network-settings-for-the-advanced-enterprise-voice-features.md">configurações de voz do recurso Advanced Enterprise Voice do Lync Server 2013</A> na documentação de planejamento.</span><span class="sxs-lookup"><span data-stu-id="44530-106">Before you begin network configuration for call admission control, E9-1-1, or media bypass, make sure that you reviewed additional information about network settings in the <A href="lync-server-2013-network-settings-for-the-advanced-enterprise-voice-features.md">Network settings for the advanced Enterprise Voice features in Lync Server 2013</A> topic in the Planning documentation.</span></span> <span data-ttu-id="44530-107">Para obter detalhes sobre a configuração de rede principalmente sobre o controle de admissão de chamadas, consulte <A href="lync-server-2013-defining-your-requirements-for-call-admission-control.md">definir seus requisitos de controle de admissão de chamadas no Lync Server 2013</A> na documentação de planejamento.</span><span class="sxs-lookup"><span data-stu-id="44530-107">For details about network configuration primarily about call admission control, also see <A href="lync-server-2013-defining-your-requirements-for-call-admission-control.md">Defining your requirements for call admission control in Lync Server 2013</A> in the Planning documentation.</span></span>



</div>

<span data-ttu-id="44530-108">O controle de admissão de chamada e o E9-1-1 têm requisitos adicionais de configuração para os sites da rede:</span><span class="sxs-lookup"><span data-stu-id="44530-108">Call admission control and E9-1-1 have additional configuration requirements for network sites:</span></span>

  - <span data-ttu-id="44530-109">O serviço de controle de admissão de chamadas requer que um *perfil de política de largura de banda* seja especificado para cada site restrito pelas limitações de largura de banda WAN.</span><span class="sxs-lookup"><span data-stu-id="44530-109">Call admission control requires that a *bandwidth policy profile* be specified for each site that is constrained by WAN bandwidth limitations.</span></span> <span data-ttu-id="44530-110">Se você planeja implantar o controle de admissão de chamadas, deverá [criar perfis de política de largura de banda no Lync Server 2013](lync-server-2013-create-bandwidth-policy-profiles.md) antes de configurar seus sites de rede.</span><span class="sxs-lookup"><span data-stu-id="44530-110">If you plan to deploy call admission control, you must [Create bandwidth policy profiles in Lync Server 2013](lync-server-2013-create-bandwidth-policy-profiles.md) before you configure your network sites.</span></span>

  - <span data-ttu-id="44530-111">O E9-1-1 requer que uma *política local* seja especificada para cada site.</span><span class="sxs-lookup"><span data-stu-id="44530-111">E9-1-1 requires that a *location policy* be specified for each site.</span></span> <span data-ttu-id="44530-112">Se você planeja implantar o E9-1-1, será necessário [criar políticas de localização no Lync Server 2013](lync-server-2013-create-location-policies.md) antes de configurar seus sites de rede.</span><span class="sxs-lookup"><span data-stu-id="44530-112">If you plan to deploy E9-1-1, you must [Create location policies in Lync Server 2013](lync-server-2013-create-location-policies.md) before you configure your network sites.</span></span>

<div>

## <a name="create-or-modify-network-regions-network-sites-and-subnets"></a><span data-ttu-id="44530-113">Criar ou modificar regiões de rede, sites de rede e sub-redes</span><span class="sxs-lookup"><span data-stu-id="44530-113">Create or Modify Network Regions, Network Sites, and Subnets</span></span>

<span data-ttu-id="44530-114">Os tópicos a seguir fornecem etapas para criar ou modificar regiões de rede e sites de rede e para associar sub-redes a sites de rede.</span><span class="sxs-lookup"><span data-stu-id="44530-114">The following topics provide steps to create or modify network regions and network sites, and to associate subnets with network sites.</span></span> <span data-ttu-id="44530-115">Esses tópicos não são específicos para qualquer recurso avançado de Enterprise Voice específico.</span><span class="sxs-lookup"><span data-stu-id="44530-115">These topics are not specific to any particular advanced Enterprise Voice feature.</span></span>

  - [<span data-ttu-id="44530-116">Criar ou modificar uma região de rede no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="44530-116">Create or modify a network region in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-a-network-region.md)

  - [<span data-ttu-id="44530-117">Criar ou modificar um site da rede no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="44530-117">Create or modify a network site in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-a-network-site.md)

  - [<span data-ttu-id="44530-118">Associar uma subrede a um site de rede no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="44530-118">Associate a subnet with a network site in Lync Server 2013</span></span>](lync-server-2013-associate-a-subnet-with-a-network-site.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

