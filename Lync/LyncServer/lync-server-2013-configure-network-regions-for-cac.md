---
title: 'Lync Server 2013: configurar regiões de rede para CAC'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure network regions for CAC
ms:assetid: ea3ff988-dd5a-4bc4-bec5-39a0fb09793a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg399051(v=OCS.15)
ms:contentKeyID: 48185906
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c029de2a7b6296dc81d365978c55d18c817e0894
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48520538"
---
# <a name="configure-network-regions-for-cac-in-lync-server-2013"></a><span data-ttu-id="49859-102">Configurar regiões de rede para CAC no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="49859-102">Configure network regions for CAC in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="49859-103">_**Última modificação do tópico:** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="49859-103">_**Topic Last Modified:** 2012-09-21_</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="49859-104">Se você já tiver criado regiões de rede para E9-1-1 ou desvio de mídia, você pode modificar as regiões de rede existentes adicionando configurações específicas ao controle de admissão de chamadas usando o cmdlet <STRONG>Set-CsNetworkRegion</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="49859-104">If you have already created network regions for E9-1-1 or media bypass, you can modify the existing network regions by adding settings specific to call admission control (CAC) by using the <STRONG>Set-CsNetworkRegion</STRONG> cmdlet.</span></span> <span data-ttu-id="49859-105">Para obter um exemplo de como modificar uma região de rede, confira <A href="lync-server-2013-create-or-modify-a-network-region.md">criar ou modificar uma região de rede no Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="49859-105">For an example of how to modify a network region, see <A href="lync-server-2013-create-or-modify-a-network-region.md">Create or modify a network region in Lync Server 2013</A>.</span></span>



</div>

<span data-ttu-id="49859-106">*Regiões de rede* são hubs de rede ou backbones usados na configuração do CAC (controle de admissão de chamadas), E9-1-1 e desvio de mídia.</span><span class="sxs-lookup"><span data-stu-id="49859-106">*Network regions* are the network hubs or backbones that are used in configuring CAC, E9-1-1, and media bypass.</span></span> <span data-ttu-id="49859-107">Use os procedimentos a seguir para criar regiões de rede que alinham as regiões de rede no exemplo de topologia de rede para CAC.</span><span class="sxs-lookup"><span data-stu-id="49859-107">Use the following procedure to create network regions that align to network regions in the example network topology for CAC.</span></span> <span data-ttu-id="49859-108">Para exibir a topologia de rede de exemplo, confira o [exemplo: reunindo seus requisitos para controle de admissão de chamadas no Lync Server 2013](lync-server-2013-example-of-gathering-your-requirements-for-call-admission-control.md) na documentação de planejamento.</span><span class="sxs-lookup"><span data-stu-id="49859-108">To view the example network topology, see [Example: Gathering your requirements for call admission control in Lync Server 2013](lync-server-2013-example-of-gathering-your-requirements-for-call-admission-control.md) in the Planning documentation.</span></span>

<span data-ttu-id="49859-109">O exemplo de topologia de rede para CAC tem três regiões: América do Norte, EMEA e APAC.</span><span class="sxs-lookup"><span data-stu-id="49859-109">The example network topology for CAC has three regions: North America, EMEA, and APAC.</span></span> <span data-ttu-id="49859-110">Cada região tem um site central especificado.</span><span class="sxs-lookup"><span data-stu-id="49859-110">Each region has a specified central site.</span></span> <span data-ttu-id="49859-111">Para a região da América do Norte, o site central designado é chamado CHICAGO.</span><span class="sxs-lookup"><span data-stu-id="49859-111">For the North America region, the designated central site is named CHICAGO.</span></span> <span data-ttu-id="49859-112">O procedimento a seguir mostra um exemplo de como é possível usar o cmdlet  **New-CsNetworkRegion** para criar a região América do Norte.</span><span class="sxs-lookup"><span data-stu-id="49859-112">The following procedure shows an example of how you can use the **New-CsNetworkRegion** cmdlet to create the North America region.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="49859-113">No procedimento a seguir, o Shell de gerenciamento do Lync Server é usado para criar uma região de rede.</span><span class="sxs-lookup"><span data-stu-id="49859-113">In the following procedure, Lync Server Management Shell is used to create a network region.</span></span> <span data-ttu-id="49859-114">Para obter detalhes sobre como usar o painel de controle do Lync Server para criar uma região de rede, consulte <A href="lync-server-2013-create-or-modify-a-network-region.md">criar ou modificar uma região de rede no Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="49859-114">For details about using Lync Server Control Panel to create a network region, see <A href="lync-server-2013-create-or-modify-a-network-region.md">Create or modify a network region in Lync Server 2013</A>.</span></span>



</div>

<div>

## <a name="to-create-a-network-region-for-call-admission-control"></a><span data-ttu-id="49859-115">Para criar uma região de rede para controle de admissão de chamada</span><span class="sxs-lookup"><span data-stu-id="49859-115">To create a network region for call admission control</span></span>

1.  <span data-ttu-id="49859-116">Inicie o Shell de Gerenciamento do Lync Server: clique em **Iniciar**, em **Todos os Programas**, em **Microsoft Lync Server 2013** e em **Shell de Gerenciamento do Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="49859-116">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="49859-117">Para cada região que você precisa criar, execute o cmdlet **New-CsNetworkRegion**.</span><span class="sxs-lookup"><span data-stu-id="49859-117">For each region that you need to create, run the **New-CsNetworkRegion** cmdlet.</span></span> <span data-ttu-id="49859-118">Por exemplo, para criar a região América do Norte, execute:</span><span class="sxs-lookup"><span data-stu-id="49859-118">For example, to create the North America region, run:</span></span>
    
        New-CsNetworkRegion -Identity NorthAmerica -CentralSite CHICAGO -Description "All North America Locations"

3.  <span data-ttu-id="49859-119">Repita a etapa 2 para criar as regiões de rede EMEA e APAC.</span><span class="sxs-lookup"><span data-stu-id="49859-119">Repeat step 2 to create the network regions, EMEA and APAC.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

