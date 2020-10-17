---
title: 'Lync Server 2013: fornecendo conectividade PSTN em um site de filial'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Providing PSTN connectivity at a branch site
ms:assetid: d78d76fb-2dd1-42cb-b25a-bfaff9650a70
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398945(v=OCS.15)
ms:contentKeyID: 48185633
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 38c76d378db31cb8a6619a18072ec0218260843e
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48513168"
---
# <a name="providing-pstn-connectivity-at-a-branch-site-in-lync-server-2013"></a><span data-ttu-id="98239-102">Fornecendo conectividade PSTN em um site de filial no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="98239-102">Providing PSTN connectivity at a branch site in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="98239-103">_**Última modificação do tópico:** 2012-10-05_</span><span class="sxs-lookup"><span data-stu-id="98239-103">_**Topic Last Modified:** 2012-10-05_</span></span>

<span data-ttu-id="98239-104">Recomendamos usar a ferramenta de planejamento do Microsoft Lync Server 2013 para adicionar sites de filial à sua topologia e configurar sua infraestrutura de voz em sites de filial.</span><span class="sxs-lookup"><span data-stu-id="98239-104">We recommend using the Microsoft Lync Server 2013, Planning Tool to add branch sites to your topology and to set up your voice infrastructure in branch sites.</span></span>

<span data-ttu-id="98239-105">Se você não estiver usando a ferramenta de planejamento, use os procedimentos nos tópicos desta seção para adicionar os sites de filial e, em seguida, para configurar sua infraestrutura de voz, definindo o gateway PSTN (rede telefônica pública comutada) e/ou configurando o tronco SIP (com ou sem o bypass de mídia).</span><span class="sxs-lookup"><span data-stu-id="98239-105">If you are not using the Planning Tool, use the procedures in the topics in this section—first, to add the branch sites, and then, to set up your voice infrastructure by defining the IP/public switched telephone network (PSTN) gateway and/or by configuring the SIP trunk (with or without media bypass).</span></span> <span data-ttu-id="98239-106">Conectar um PBX ao site de filial é outra opção.</span><span class="sxs-lookup"><span data-stu-id="98239-106">Connecting a private branch exchange (PBX) to the branch site is another option.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="98239-107">Se quiser fornecer resiliência de site de filial, você deve implantar um aparelho de filial persistente, um servidor de filial persistente ou um servidor Standard Edition no site de filial.</span><span class="sxs-lookup"><span data-stu-id="98239-107">If you want to provide branch-site resiliency, you must deploy a Survivable Branch Appliance, a Survivable Branch Server, or Standard Edition server at the branch site.</span></span> <span data-ttu-id="98239-108">Para obter detalhes, consulte <A href="lync-server-2013-deploying-a-survivable-branch-appliance-or-server.md">implantando um servidor ou aparelho de filial persistente com o Lync server 2013</A> ou <A href="lync-server-2013-deploying-lync-server.md">implantando o Lync Server 2013</A>, conforme apropriado, na documentação de implantação.</span><span class="sxs-lookup"><span data-stu-id="98239-108">For details, see <A href="lync-server-2013-deploying-a-survivable-branch-appliance-or-server.md">Deploying a Survivable Branch Appliance or Server with Lync Server 2013</A> or <A href="lync-server-2013-deploying-lync-server.md">Deploying Lync Server 2013</A>, as appropriate, in the Deployment documentation.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="98239-109">Nesta seção</span><span class="sxs-lookup"><span data-stu-id="98239-109">In This Section</span></span>

  - [<span data-ttu-id="98239-110">Adicionar sites de filial à sua topologia no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="98239-110">Add branch sites to your topology in Lync Server 2013</span></span>](lync-server-2013-add-branch-sites-to-your-topology.md)

  - [<span data-ttu-id="98239-111">Definir um gateway PSTN para um site de filial no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="98239-111">Define a PSTN gateway for a branch site in Lync Server 2013</span></span>](lync-server-2013-define-a-pstn-gateway-for-a-branch-site.md)

  - [<span data-ttu-id="98239-112">Configurar um tronco com bypass de mídia no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="98239-112">Configure a trunk with media bypass in Lync Server 2013</span></span>](lync-server-2013-configure-a-trunk-with-media-bypass.md)

  - [<span data-ttu-id="98239-113">Configurar um tronco sem bypass de mídia no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="98239-113">Configure a trunk without media bypass in Lync Server 2013</span></span>](lync-server-2013-configure-a-trunk-without-media-bypass.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="98239-114">Confira também</span><span class="sxs-lookup"><span data-stu-id="98239-114">See Also</span></span>


[<span data-ttu-id="98239-115">Planejamento de bypass de mídia no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="98239-115">Planning for media bypass in Lync Server 2013</span></span>](lync-server-2013-planning-for-media-bypass.md)  
[<span data-ttu-id="98239-116">Planejamento da conectividade PSTN no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="98239-116">Planning for PSTN connectivity in Lync Server 2013</span></span>](lync-server-2013-planning-for-pstn-connectivity.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

