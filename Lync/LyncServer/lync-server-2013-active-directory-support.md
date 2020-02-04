---
title: 'Lync Server 2013: Suporte a Active Directory'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Active Directory support
ms:assetid: 28ed9ac4-586d-4803-ad45-99c4fa793f54
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425756(v=OCS.15)
ms:contentKeyID: 48183679
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: cd35b9444f0ede4abc9b66ab6b5513d049df57ee
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41735181"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="active-directory-support-in-lync-server-2013"></a><span data-ttu-id="d49da-102">Suporte a Active Directory no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d49da-102">Active Directory support in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d49da-103">_**Tópico da última modificação:** 2012-12-04_</span><span class="sxs-lookup"><span data-stu-id="d49da-103">_**Topic Last Modified:** 2012-12-04_</span></span>

<span data-ttu-id="d49da-104">As topologias locais dos serviços de domínio Active Directory com suporte no Lync Server 2013 são as seguintes:</span><span class="sxs-lookup"><span data-stu-id="d49da-104">The Active Directory Domain Services on-premises topologies that are supported by Lync Server 2013 are as follows:</span></span>

  - <span data-ttu-id="d49da-105">Floresta única com domínio único</span><span class="sxs-lookup"><span data-stu-id="d49da-105">Single forest with single domain</span></span>

  - <span data-ttu-id="d49da-106">Floresta única com uma única árvore e vários domínios</span><span class="sxs-lookup"><span data-stu-id="d49da-106">Single forest with a single tree and multiple domains</span></span>

  - <span data-ttu-id="d49da-107">Floresta única com várias árvores e namespaces não contíguos</span><span class="sxs-lookup"><span data-stu-id="d49da-107">Single forest with multiple trees and disjoint namespaces</span></span>

  - <span data-ttu-id="d49da-108">Várias florestas em uma topologia de floresta central</span><span class="sxs-lookup"><span data-stu-id="d49da-108">Multiple forests in a central forest topology</span></span>

  - <span data-ttu-id="d49da-109">Várias florestas em uma topologia de floresta de recursos</span><span class="sxs-lookup"><span data-stu-id="d49da-109">Multiple forests in a resource forest topology</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="d49da-110">O Lync Server 2013 não é compatível com domínios de rótulo único.</span><span class="sxs-lookup"><span data-stu-id="d49da-110">Lync Server 2013 does not support single-label domains.</span></span> <span data-ttu-id="d49da-111">Por exemplo, uma floresta com um domínio raiz chamado <STRONG>contoso. local</STRONG> tem suporte, mas não há suporte para um domínio raiz de rótulo único chamado <STRONG>local</STRONG> .</span><span class="sxs-lookup"><span data-stu-id="d49da-111">For example, a forest with a root domain named <STRONG>contoso.local</STRONG> is supported, but a single-label root domain named <STRONG>local</STRONG> is not supported.</span></span> <span data-ttu-id="d49da-112">Para obter detalhes, consulte o artigo 300684 da base de dados de conhecimento Microsoft, "informações sobre como configurar o Windows para domínios com <A href="http://go.microsoft.com/fwlink/p/?linkid=143752">http://go.microsoft.com/fwlink/p/?linkId=143752</A>nomes DNS de rótulo único" em.</span><span class="sxs-lookup"><span data-stu-id="d49da-112">For details, see Microsoft Knowledge Base article 300684, "Information about configuring Windows for domains with single-label DNS names," at <A href="http://go.microsoft.com/fwlink/p/?linkid=143752">http://go.microsoft.com/fwlink/p/?linkId=143752</A>.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="d49da-113">O Lync Server 2013 não é compatível com a renomeação de domínios.</span><span class="sxs-lookup"><span data-stu-id="d49da-113">Lync Server 2013 does not support renaming domains.</span></span> <span data-ttu-id="d49da-114">Se você precisar renomear um domínio onde o Lync Server está implantado, primeiro você precisa desinstalar o Lync Server, depois renomear o domínio e depois reinstalar o Lync Server.</span><span class="sxs-lookup"><span data-stu-id="d49da-114">If you need to rename a domain where Lync Server is deployed, you need to first uninstall Lync Server, then rename the domain, and then reinstall Lync Server.</span></span>



</div>

<span data-ttu-id="d49da-115">Para obter detalhes sobre topologias e requisitos compatíveis para implantações locais, consulte [requisitos, suporte e topologias de serviços de domínio do Active Directory no Lync Server 2013](lync-server-2013-active-directory-domain-services-requirements-support-and-topologies.md) na documentação de planejamento.</span><span class="sxs-lookup"><span data-stu-id="d49da-115">For details about supported topologies and requirements for on-premises deployments, see [Active Directory Domain Services requirements, support, and topologies in Lync Server 2013](lync-server-2013-active-directory-domain-services-requirements-support-and-topologies.md) in the Planning documentation.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

