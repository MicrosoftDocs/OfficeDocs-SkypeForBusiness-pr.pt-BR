---
title: 'Lync Server 2013: Fornecendo conectividade de PSTN ao site da filial'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Providing PSTN connectivity at a branch site
ms:assetid: d78d76fb-2dd1-42cb-b25a-bfaff9650a70
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398945(v=OCS.15)
ms:contentKeyID: 48185633
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: cf7ba3c77c789d10e80319542cd163186eef2d4c
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34823620"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="providing-pstn-connectivity-at-a-branch-site-in-lync-server-2013"></a><span data-ttu-id="f99f9-102">Fornecendo conectividade de PSTN ao site da filial no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f99f9-102">Providing PSTN connectivity at a branch site in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f99f9-103">_**Tópico da última modificação:** 2012-10-05_</span><span class="sxs-lookup"><span data-stu-id="f99f9-103">_**Topic Last Modified:** 2012-10-05_</span></span>

<span data-ttu-id="f99f9-104">Recomendamos usar o Microsoft Lync Server 2013, a ferramenta de planejamento para adicionar sites de filiais à sua topologia e para configurar sua infraestrutura de voz em sites de filiais.</span><span class="sxs-lookup"><span data-stu-id="f99f9-104">We recommend using the Microsoft Lync Server 2013, Planning Tool to add branch sites to your topology and to set up your voice infrastructure in branch sites.</span></span>

<span data-ttu-id="f99f9-105">Se você não estiver usando a ferramenta de planejamento, use os procedimentos nos tópicos desta seção — primeiro, para adicionar os sites de ramificação e, em seguida, para configurar sua infraestrutura de voz definindo o gateway PSTN (rede telefônica comutada de IP/pública) e/ou configurando o SIP tronco (com ou sem bypass de mídia).</span><span class="sxs-lookup"><span data-stu-id="f99f9-105">If you are not using the Planning Tool, use the procedures in the topics in this section—first, to add the branch sites, and then, to set up your voice infrastructure by defining the IP/public switched telephone network (PSTN) gateway and/or by configuring the SIP trunk (with or without media bypass).</span></span> <span data-ttu-id="f99f9-106">Conectar um PBX (Private Branch Exchange) ao site da filial é outra opção.</span><span class="sxs-lookup"><span data-stu-id="f99f9-106">Connecting a private branch exchange (PBX) to the branch site is another option.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="f99f9-107">Se você quiser fornecer resiliência em filiais, você deve implantar um aparelho de ramificação sobreviventes, um servidor de ramificação sobreviventes ou um servidor Standard Edition no site da filial.</span><span class="sxs-lookup"><span data-stu-id="f99f9-107">If you want to provide branch-site resiliency, you must deploy a Survivable Branch Appliance, a Survivable Branch Server, or Standard Edition server at the branch site.</span></span> <span data-ttu-id="f99f9-108">Para obter detalhes, consulte Implantando <A href="lync-server-2013-deploying-a-survivable-branch-appliance-or-server.md">um servidor ou um aplicativo de ramificação sobreviventes com o Lync server 2013</A> ou implantando o <A href="lync-server-2013-deploying-lync-server.md">Lync Server 2013</A>, conforme apropriado, na documentação de implantação.</span><span class="sxs-lookup"><span data-stu-id="f99f9-108">For details, see <A href="lync-server-2013-deploying-a-survivable-branch-appliance-or-server.md">Deploying a Survivable Branch Appliance or Server with Lync Server 2013</A> or <A href="lync-server-2013-deploying-lync-server.md">Deploying Lync Server 2013</A>, as appropriate, in the Deployment documentation.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="f99f9-109">Nesta seção</span><span class="sxs-lookup"><span data-stu-id="f99f9-109">In This Section</span></span>

  - [<span data-ttu-id="f99f9-110">Adicionar sites de filial a sua topologia no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f99f9-110">Add branch sites to your topology in Lync Server 2013</span></span>](lync-server-2013-add-branch-sites-to-your-topology.md)

  - [<span data-ttu-id="f99f9-111">Definir um gateway de PSTN para um site de filial no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f99f9-111">Define a PSTN gateway for a branch site in Lync Server 2013</span></span>](lync-server-2013-define-a-pstn-gateway-for-a-branch-site.md)

  - [<span data-ttu-id="f99f9-112">Configure a trunk with media bypass in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f99f9-112">Configure a trunk with media bypass in Lync Server 2013</span></span>](lync-server-2013-configure-a-trunk-with-media-bypass.md)

  - [<span data-ttu-id="f99f9-113">Configurar um tronco sem bypass de mídia no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f99f9-113">Configure a trunk without media bypass in Lync Server 2013</span></span>](lync-server-2013-configure-a-trunk-without-media-bypass.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="f99f9-114">Confira também</span><span class="sxs-lookup"><span data-stu-id="f99f9-114">See Also</span></span>


[<span data-ttu-id="f99f9-115">Planejamento de bypass de mídia no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f99f9-115">Planning for media bypass in Lync Server 2013</span></span>](lync-server-2013-planning-for-media-bypass.md)  
[<span data-ttu-id="f99f9-116">Planejando a conectividade PSTN no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f99f9-116">Planning for PSTN connectivity in Lync Server 2013</span></span>](lync-server-2013-planning-for-pstn-connectivity.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

