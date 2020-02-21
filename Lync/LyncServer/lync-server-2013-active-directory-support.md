---
title: Lync Server 2013 suporte ao Active Directory
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
ms.openlocfilehash: 8a7da4487c376ceea4c5c3e41e20a55874b27f06
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42199994"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="active-directory-support-in-lync-server-2013"></a><span data-ttu-id="73fea-102">Suporte do Active Directory no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="73fea-102">Active Directory support in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="73fea-103">_**Última modificação do tópico:** 2012-12-04_</span><span class="sxs-lookup"><span data-stu-id="73fea-103">_**Topic Last Modified:** 2012-12-04_</span></span>

<span data-ttu-id="73fea-104">As topologias locais dos serviços de domínio Active Directory suportadas pelo Lync Server 2013 são as seguintes:</span><span class="sxs-lookup"><span data-stu-id="73fea-104">The Active Directory Domain Services on-premises topologies that are supported by Lync Server 2013 are as follows:</span></span>

  - <span data-ttu-id="73fea-105">Floresta única com domínio único</span><span class="sxs-lookup"><span data-stu-id="73fea-105">Single forest with single domain</span></span>

  - <span data-ttu-id="73fea-106">Floresta única com uma única árvore e vários domínios</span><span class="sxs-lookup"><span data-stu-id="73fea-106">Single forest with a single tree and multiple domains</span></span>

  - <span data-ttu-id="73fea-107">Floresta única com várias árvores e namespaces não contíguos</span><span class="sxs-lookup"><span data-stu-id="73fea-107">Single forest with multiple trees and disjoint namespaces</span></span>

  - <span data-ttu-id="73fea-108">Várias florestas em uma topologia de floresta central</span><span class="sxs-lookup"><span data-stu-id="73fea-108">Multiple forests in a central forest topology</span></span>

  - <span data-ttu-id="73fea-109">Várias florestas em uma topologia de floresta de recursos</span><span class="sxs-lookup"><span data-stu-id="73fea-109">Multiple forests in a resource forest topology</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="73fea-110">O Lync Server 2013 não dá suporte a domínios de rótulo único.</span><span class="sxs-lookup"><span data-stu-id="73fea-110">Lync Server 2013 does not support single-label domains.</span></span> <span data-ttu-id="73fea-111">Por exemplo, uma floresta com um domínio raiz chamado <STRONG>contoso. local</STRONG> é suportada, mas não há suporte para um domínio raiz de rótulo único chamado <STRONG>local</STRONG> .</span><span class="sxs-lookup"><span data-stu-id="73fea-111">For example, a forest with a root domain named <STRONG>contoso.local</STRONG> is supported, but a single-label root domain named <STRONG>local</STRONG> is not supported.</span></span> <span data-ttu-id="73fea-112">Para obter detalhes, consulte o artigo 300684 da base de dados de conhecimento da Microsoft, "informações sobre como configurar o Windows para domínios <A href="https://go.microsoft.com/fwlink/p/?linkid=143752">https://go.microsoft.com/fwlink/p/?linkId=143752</A>com nomes DNS de rótulo único" em.</span><span class="sxs-lookup"><span data-stu-id="73fea-112">For details, see Microsoft Knowledge Base article 300684, "Information about configuring Windows for domains with single-label DNS names," at <A href="https://go.microsoft.com/fwlink/p/?linkid=143752">https://go.microsoft.com/fwlink/p/?linkId=143752</A>.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="73fea-113">O Lync Server 2013 não dá suporte à renomeação de domínios.</span><span class="sxs-lookup"><span data-stu-id="73fea-113">Lync Server 2013 does not support renaming domains.</span></span> <span data-ttu-id="73fea-114">Se for necessário renomear um domínio em que o Lync Server está implantado, primeiro você precisa desinstalar o Lync Server, renomear o domínio e, em seguida, reinstalar o Lync Server.</span><span class="sxs-lookup"><span data-stu-id="73fea-114">If you need to rename a domain where Lync Server is deployed, you need to first uninstall Lync Server, then rename the domain, and then reinstall Lync Server.</span></span>



</div>

<span data-ttu-id="73fea-115">Para obter detalhes sobre as topologias e os requisitos suportados para implantações locais, consulte [Active Directory Domain Services requirements, support e topologias no Lync Server 2013](lync-server-2013-active-directory-domain-services-requirements-support-and-topologies.md) na documentação de planejamento.</span><span class="sxs-lookup"><span data-stu-id="73fea-115">For details about supported topologies and requirements for on-premises deployments, see [Active Directory Domain Services requirements, support, and topologies in Lync Server 2013](lync-server-2013-active-directory-domain-services-requirements-support-and-topologies.md) in the Planning documentation.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

