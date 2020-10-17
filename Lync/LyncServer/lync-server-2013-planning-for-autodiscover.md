---
title: 'Lync Server 2013: planejamento para descoberta automática'
description: 'Lync Server 2013: planejamento para descoberta automática.'
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
ms.openlocfilehash: e28a6a3a317f063151eadde7c5de51b02a46b482
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48544627"
---
# <a name="planning-for-autodiscover-in-lync-server-2013"></a><span data-ttu-id="75887-103">Planejamento para descoberta automática no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="75887-103">Planning for Autodiscover in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="75887-104">_**Última modificação do tópico:** 2013-02-16_</span><span class="sxs-lookup"><span data-stu-id="75887-104">_**Topic Last Modified:** 2013-02-16_</span></span>

<span data-ttu-id="75887-105">A descoberta automática foi introduzida no Lync Server na atualização cumulativa do Lync Server 2010:2011 de novembro.</span><span class="sxs-lookup"><span data-stu-id="75887-105">Autodiscover was introduced for Lync Server in the Cumulative Update for Lync Server 2010: November 2011.</span></span> <span data-ttu-id="75887-106">O principal objetivo dessa implementação inicial da descoberta automática foi fornecer um meio para que o Lync Mobile localize o serviço de mobilidade (MCX).</span><span class="sxs-lookup"><span data-stu-id="75887-106">The primary purpose for this initial implementation of Autodiscover was to provide a means for Lync Mobile to locate the Mobility service (Mcx).</span></span> <span data-ttu-id="75887-107">O serviço de descoberta automática no Lync Server 2013 agora é um serviço usado por todos os clientes para localizar serviços de servidor e usuário.</span><span class="sxs-lookup"><span data-stu-id="75887-107">The Autodiscover service in Lync Server 2013 is now a service used by all clients to locate server and user services.</span></span> <span data-ttu-id="75887-108">O serviço de descoberta automática do Microsoft Lync Server 2013 é executado em diretores e servidores front-end.</span><span class="sxs-lookup"><span data-stu-id="75887-108">The Microsoft Lync Server 2013 Autodiscover service runs on Directors and Front End Servers.</span></span>

<div>


> [!TIP]  
> <span data-ttu-id="75887-109">Para obter uma compreensão mais técnica da descoberta automática e o que é comunicado aos clientes, consulte <A href="lync-server-2013-understanding-autodiscover.md">Understanding autodiscover in Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="75887-109">For a more technical understanding of Autodiscover and what is communicated to clients, see <A href="lync-server-2013-understanding-autodiscover.md">Understanding Autodiscover in Lync Server 2013</A>.</span></span><BR><span data-ttu-id="75887-110">A mobilidade ainda é um cenário distinto, e os serviços de mobilidade ainda exigem alguns planejamentos especiais.</span><span class="sxs-lookup"><span data-stu-id="75887-110">Mobility is still a distinct scenario and the Mobility services still require some special planning.</span></span> <span data-ttu-id="75887-111">Para obter detalhes adicionais, consulte <A href="lync-server-2013-planning-for-mobility.md">Planning for Mobility in Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="75887-111">For additional details, see <A href="lync-server-2013-planning-for-mobility.md">Planning for mobility in Lync Server 2013</A>.</span></span>



</div>

<span data-ttu-id="75887-112">Quando a descoberta automática foi introduzida no Lync Server 2010, houve comprometimentos que precisavam ser feitos para implementar um serviço que exigia alterações potenciais de certificado para implantações de servidor existentes.</span><span class="sxs-lookup"><span data-stu-id="75887-112">When Autodiscover was introduced in Lync Server 2010, there were compromises that needed to be made in order to implement a service that required potential certificate changes to existing server deployments.</span></span> <span data-ttu-id="75887-113">A descoberta automática pode ser usada na porta TCP 443 para HTTPS ou over Port TCP 80 para HTTP.</span><span class="sxs-lookup"><span data-stu-id="75887-113">Autodiscover could be used over port TCP 443 for HTTPS or over port TCP 80 for HTTP.</span></span> <span data-ttu-id="75887-114">Se a decisão foi feita para usar HTTPS, os certificados em proxies reversos, diretores e servidores front-end precisam ser reemitidos para acomodar os `lyncdiscover.<domain>` registros necessários e `lyncdiscoverinternal.<domain>` DNS.</span><span class="sxs-lookup"><span data-stu-id="75887-114">If the decision was made to use HTTPS, certificates on reverse proxies, Directors, and Front End Servers needed to be reissued in order to accommodate the required `lyncdiscover.<domain>` and `lyncdiscoverinternal.<domain>` DNS records.</span></span> <span data-ttu-id="75887-115">Se a decisão era usar HTTP, a reemissão de certificados pode ser evitada usando registros CNAME (ou alias) DNS para usar os nomes existentes nos certificados.</span><span class="sxs-lookup"><span data-stu-id="75887-115">If the decision was to use HTTP, the reissue of certificates could be avoided by using DNS CNAME (or alias) records to use existing names on the certificates.</span></span> <span data-ttu-id="75887-116">O uso de HTTP significa que as comunicações iniciais não foram criptografadas.</span><span class="sxs-lookup"><span data-stu-id="75887-116">Using HTTP did mean that the initial communications were unencrypted.</span></span>

<span data-ttu-id="75887-117">Como o Lync Server 2013 usa a descoberta automática para todos os clientes, o cenário principal é usar o HTTPS exclusivamente e criar certificados com o lyncdiscover.\<domain\></span><span class="sxs-lookup"><span data-stu-id="75887-117">Because Lync Server 2013 uses Autodiscover for all clients, the main scenario is to use HTTPS exclusively and to create certificates with lyncdiscover.\<domain\></span></span> <span data-ttu-id="75887-118">como parte da configuração de proxies reversos, diretores e servidores front-end.</span><span class="sxs-lookup"><span data-stu-id="75887-118">as part of the configuration of reverse proxies, Directors and Front End Servers.</span></span> <span data-ttu-id="75887-119">Se você estiver implementando a descoberta automática em uma implantação atualizada do Lync Server 2010, convém usar HTTP para evitar a reemissão de certificados.</span><span class="sxs-lookup"><span data-stu-id="75887-119">If you are implementing Autodiscover into an upgraded deployment from Lync Server 2010, you may want to use HTTP to avoid reissuing certificates.</span></span> <span data-ttu-id="75887-120">As orientações para ambos os cenários são fornecidas nas seções a seguir.</span><span class="sxs-lookup"><span data-stu-id="75887-120">Guidance for both scenarios is provided in the following sections.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="75887-121">A lista de nomes alternativos da entidade em certificados usados pela regra de publicação dos serviços Web externos deve conter um <EM>lyncdiscover. &lt; sipdomain &gt; </EM> entrada para cada domínio SIP em sua organização.</span><span class="sxs-lookup"><span data-stu-id="75887-121">The subject alternative name list on certificates used by the external web services publishing rule must contain a <EM>lyncdiscover.&lt;sipdomain&gt;</EM> entry for each SIP domain within your organization.</span></span> <span data-ttu-id="75887-122">Para obter detalhes sobre as entradas de nome alternativo de entidade que são necessárias para diretores, servidores front-end e proxies reverso, consulte <A href="lync-server-2013-certificate-summary-autodiscover.md">Resumo de certificado-descoberta automática no Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="75887-122">For details about the subject alternative name entries that are required for Directors, Front End Servers, and reverse proxies, see <A href="lync-server-2013-certificate-summary-autodiscover.md">Certificate summary - Autodiscover in Lync Server 2013</A>.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="75887-123">Nesta seção</span><span class="sxs-lookup"><span data-stu-id="75887-123">In This Section</span></span>

  - [<span data-ttu-id="75887-124">Resumo de certificado-descoberta automática no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="75887-124">Certificate summary - Autodiscover in Lync Server 2013</span></span>](lync-server-2013-certificate-summary-autodiscover.md)

  - [<span data-ttu-id="75887-125">Resumo de porta-descoberta automática no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="75887-125">Port summary - Autodiscover in Lync Server 2013</span></span>](lync-server-2013-port-summary-autodiscover.md)

  - [<span data-ttu-id="75887-126">Resumo de DNS-descoberta automática no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="75887-126">DNS summary - Autodiscover in Lync Server 2013</span></span>](lync-server-2013-dns-summary-autodiscover.md)

  - [<span data-ttu-id="75887-127">Descoberta automática de domínio e híbrido no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="75887-127">Hybrid and split-domain - Autodiscover in Lync Server 2013</span></span>](lync-server-2013-hybrid-and-split-domain-autodiscover.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

