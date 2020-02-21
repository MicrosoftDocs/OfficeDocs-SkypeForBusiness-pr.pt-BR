---
title: 'Lync Server 2013: planejamento para descoberta automática'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Planning for Autodiscover
ms:assetid: 51f1ff94-1d64-4e6d-a878-b86fa07edc2d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945628(v=OCS.15)
ms:contentKeyID: 51541474
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 990e58dc01171001e896b03e5a32fc8175c93b2f
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42184504"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="planning-for-autodiscover-in-lync-server-2013"></a><span data-ttu-id="623e6-102">Planejamento para descoberta automática no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="623e6-102">Planning for Autodiscover in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="623e6-103">_**Última modificação do tópico:** 2013-02-16_</span><span class="sxs-lookup"><span data-stu-id="623e6-103">_**Topic Last Modified:** 2013-02-16_</span></span>

<span data-ttu-id="623e6-104">A descoberta automática foi introduzida no Lync Server na atualização cumulativa do Lync Server 2010:2011 de novembro.</span><span class="sxs-lookup"><span data-stu-id="623e6-104">Autodiscover was introduced for Lync Server in the Cumulative Update for Lync Server 2010: November 2011.</span></span> <span data-ttu-id="623e6-105">O principal objetivo dessa implementação inicial da descoberta automática foi fornecer um meio para que o Lync Mobile localize o serviço de mobilidade (MCX).</span><span class="sxs-lookup"><span data-stu-id="623e6-105">The primary purpose for this initial implementation of Autodiscover was to provide a means for Lync Mobile to locate the Mobility service (Mcx).</span></span> <span data-ttu-id="623e6-106">O serviço de descoberta automática no Lync Server 2013 agora é um serviço usado por todos os clientes para localizar serviços de servidor e usuário.</span><span class="sxs-lookup"><span data-stu-id="623e6-106">The Autodiscover service in Lync Server 2013 is now a service used by all clients to locate server and user services.</span></span> <span data-ttu-id="623e6-107">O serviço de descoberta automática do Microsoft Lync Server 2013 é executado em diretores e servidores front-end.</span><span class="sxs-lookup"><span data-stu-id="623e6-107">The Microsoft Lync Server 2013 Autodiscover service runs on Directors and Front End Servers.</span></span>

<div>


> [!TIP]  
> <span data-ttu-id="623e6-108">Para obter uma compreensão mais técnica da descoberta automática e o que é comunicado aos clientes, consulte <A href="lync-server-2013-understanding-autodiscover.md">Understanding autodiscover in Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="623e6-108">For a more technical understanding of Autodiscover and what is communicated to clients, see <A href="lync-server-2013-understanding-autodiscover.md">Understanding Autodiscover in Lync Server 2013</A>.</span></span><BR><span data-ttu-id="623e6-109">A mobilidade ainda é um cenário distinto, e os serviços de mobilidade ainda exigem alguns planejamentos especiais.</span><span class="sxs-lookup"><span data-stu-id="623e6-109">Mobility is still a distinct scenario and the Mobility services still require some special planning.</span></span> <span data-ttu-id="623e6-110">Para obter detalhes adicionais, consulte <A href="lync-server-2013-planning-for-mobility.md">Planning for Mobility in Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="623e6-110">For additional details, see <A href="lync-server-2013-planning-for-mobility.md">Planning for mobility in Lync Server 2013</A>.</span></span>



</div>

<span data-ttu-id="623e6-111">Quando a descoberta automática foi introduzida no Lync Server 2010, houve comprometimentos que precisavam ser feitos para implementar um serviço que exigia alterações potenciais de certificado para implantações de servidor existentes.</span><span class="sxs-lookup"><span data-stu-id="623e6-111">When Autodiscover was introduced in Lync Server 2010, there were compromises that needed to be made in order to implement a service that required potential certificate changes to existing server deployments.</span></span> <span data-ttu-id="623e6-112">A descoberta automática pode ser usada na porta TCP 443 para HTTPS ou over Port TCP 80 para HTTP.</span><span class="sxs-lookup"><span data-stu-id="623e6-112">Autodiscover could be used over port TCP 443 for HTTPS or over port TCP 80 for HTTP.</span></span> <span data-ttu-id="623e6-113">Se a decisão foi feita para usar HTTPS, os certificados em proxies reversos, diretores e servidores front-end precisam ser reemitidos para acomodar os registros `lyncdiscover.<domain>` necessários `lyncdiscoverinternal.<domain>` e DNS.</span><span class="sxs-lookup"><span data-stu-id="623e6-113">If the decision was made to use HTTPS, certificates on reverse proxies, Directors, and Front End Servers needed to be reissued in order to accommodate the required `lyncdiscover.<domain>` and `lyncdiscoverinternal.<domain>` DNS records.</span></span> <span data-ttu-id="623e6-114">Se a decisão era usar HTTP, a reemissão de certificados pode ser evitada usando registros CNAME (ou alias) DNS para usar os nomes existentes nos certificados.</span><span class="sxs-lookup"><span data-stu-id="623e6-114">If the decision was to use HTTP, the reissue of certificates could be avoided by using DNS CNAME (or alias) records to use existing names on the certificates.</span></span> <span data-ttu-id="623e6-115">O uso de HTTP significa que as comunicações iniciais não foram criptografadas.</span><span class="sxs-lookup"><span data-stu-id="623e6-115">Using HTTP did mean that the initial communications were unencrypted.</span></span>

<span data-ttu-id="623e6-116">Como o Lync Server 2013 usa a descoberta automática para todos os clientes, o cenário principal é usar o HTTPS exclusivamente e criar certificados com o lyncdiscover. \<domínio\> como parte da configuração de proxies reversos, diretores e servidores front-end.</span><span class="sxs-lookup"><span data-stu-id="623e6-116">Because Lync Server 2013 uses Autodiscover for all clients, the main scenario is to use HTTPS exclusively and to create certificates with lyncdiscover.\<domain\> as part of the configuration of reverse proxies, Directors and Front End Servers.</span></span> <span data-ttu-id="623e6-117">Se você estiver implementando a descoberta automática em uma implantação atualizada do Lync Server 2010, convém usar HTTP para evitar a reemissão de certificados.</span><span class="sxs-lookup"><span data-stu-id="623e6-117">If you are implementing Autodiscover into an upgraded deployment from Lync Server 2010, you may want to use HTTP to avoid reissuing certificates.</span></span> <span data-ttu-id="623e6-118">As orientações para ambos os cenários são fornecidas nas seções a seguir.</span><span class="sxs-lookup"><span data-stu-id="623e6-118">Guidance for both scenarios is provided in the following sections.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="623e6-119">A lista de nomes alternativos da entidade em certificados usados pela regra de publicação dos serviços Web externos deve conter um <EM>lyncdiscover.&lt; sipdomain&gt; </EM> entrada para cada domínio SIP em sua organização.</span><span class="sxs-lookup"><span data-stu-id="623e6-119">The subject alternative name list on certificates used by the external web services publishing rule must contain a <EM>lyncdiscover.&lt;sipdomain&gt;</EM> entry for each SIP domain within your organization.</span></span> <span data-ttu-id="623e6-120">Para obter detalhes sobre as entradas de nome alternativo de entidade que são necessárias para diretores, servidores front-end e proxies reverso, consulte <A href="lync-server-2013-certificate-summary-autodiscover.md">Resumo de certificado-descoberta automática no Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="623e6-120">For details about the subject alternative name entries that are required for Directors, Front End Servers, and reverse proxies, see <A href="lync-server-2013-certificate-summary-autodiscover.md">Certificate summary - Autodiscover in Lync Server 2013</A>.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="623e6-121">Nesta seção</span><span class="sxs-lookup"><span data-stu-id="623e6-121">In This Section</span></span>

  - [<span data-ttu-id="623e6-122">Resumo de certificado-descoberta automática no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="623e6-122">Certificate summary - Autodiscover in Lync Server 2013</span></span>](lync-server-2013-certificate-summary-autodiscover.md)

  - [<span data-ttu-id="623e6-123">Resumo de porta-descoberta automática no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="623e6-123">Port summary - Autodiscover in Lync Server 2013</span></span>](lync-server-2013-port-summary-autodiscover.md)

  - [<span data-ttu-id="623e6-124">Resumo de DNS-descoberta automática no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="623e6-124">DNS summary - Autodiscover in Lync Server 2013</span></span>](lync-server-2013-dns-summary-autodiscover.md)

  - [<span data-ttu-id="623e6-125">Descoberta automática de domínio e híbrido no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="623e6-125">Hybrid and split-domain - Autodiscover in Lync Server 2013</span></span>](lync-server-2013-hybrid-and-split-domain-autodiscover.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

