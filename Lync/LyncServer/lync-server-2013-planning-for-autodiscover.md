---
title: 'Lync Server 2013: planejando para descoberta automática'
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
ms.openlocfilehash: 709b27059e1908a45b4b473f5380215bbd499d27
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41725521"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="planning-for-autodiscover-in-lync-server-2013"></a><span data-ttu-id="4941d-102">Planejando a descoberta automática no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4941d-102">Planning for Autodiscover in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4941d-103">_**Tópico da última modificação:** 2013-02-16_</span><span class="sxs-lookup"><span data-stu-id="4941d-103">_**Topic Last Modified:** 2013-02-16_</span></span>

<span data-ttu-id="4941d-104">A descoberta automática foi introduzida para o Lync Server na atualização cumulativa do Lync Server 2010:2011 de novembro.</span><span class="sxs-lookup"><span data-stu-id="4941d-104">Autodiscover was introduced for Lync Server in the Cumulative Update for Lync Server 2010: November 2011.</span></span> <span data-ttu-id="4941d-105">A principal finalidade dessa implementação inicial da descoberta automática era fornecer um meio para o Lync Mobile localizar o serviço de mobilidade (MCX).</span><span class="sxs-lookup"><span data-stu-id="4941d-105">The primary purpose for this initial implementation of Autodiscover was to provide a means for Lync Mobile to locate the Mobility service (Mcx).</span></span> <span data-ttu-id="4941d-106">O serviço de descoberta automática no Lync Server 2013 agora é um serviço usado por todos os clientes para localizar serviços de servidor e usuário.</span><span class="sxs-lookup"><span data-stu-id="4941d-106">The Autodiscover service in Lync Server 2013 is now a service used by all clients to locate server and user services.</span></span> <span data-ttu-id="4941d-107">O serviço de descoberta automática do Microsoft Lync Server 2013 é executado em directors e servidores front-end.</span><span class="sxs-lookup"><span data-stu-id="4941d-107">The Microsoft Lync Server 2013 Autodiscover service runs on Directors and Front End Servers.</span></span>

<div>


> [!TIP]  
> <span data-ttu-id="4941d-108">Para obter uma compreensão técnica do autodiscover e do que é comunicado a clientes, consulte <A href="lync-server-2013-understanding-autodiscover.md">compreendendo a descoberta automática no Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="4941d-108">For a more technical understanding of Autodiscover and what is communicated to clients, see <A href="lync-server-2013-understanding-autodiscover.md">Understanding Autodiscover in Lync Server 2013</A>.</span></span><BR><span data-ttu-id="4941d-109">A mobilidade ainda é um cenário distinto, e os serviços de mobilidade ainda exigem um planejamento especial.</span><span class="sxs-lookup"><span data-stu-id="4941d-109">Mobility is still a distinct scenario and the Mobility services still require some special planning.</span></span> <span data-ttu-id="4941d-110">Para obter mais detalhes, consulte <A href="lync-server-2013-planning-for-mobility.md">planejamento de mobilidade no Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="4941d-110">For additional details, see <A href="lync-server-2013-planning-for-mobility.md">Planning for mobility in Lync Server 2013</A>.</span></span>



</div>

<span data-ttu-id="4941d-111">Quando a descoberta automática foi introduzida no Lync Server 2010, havia comprometimentos que precisavam ser feito para implementar um serviço que exigisse alterações de certificado em potencial em implantações de servidor existentes.</span><span class="sxs-lookup"><span data-stu-id="4941d-111">When Autodiscover was introduced in Lync Server 2010, there were compromises that needed to be made in order to implement a service that required potential certificate changes to existing server deployments.</span></span> <span data-ttu-id="4941d-112">A descoberta automática pode ser usada na porta TCP 443 para HTTPS ou na porta TCP 80 para HTTP.</span><span class="sxs-lookup"><span data-stu-id="4941d-112">Autodiscover could be used over port TCP 443 for HTTPS or over port TCP 80 for HTTP.</span></span> <span data-ttu-id="4941d-113">Se a decisão foi feita para usar HTTPS, os certificados em proxies reverso, directors e servidores front-end precisarão ser reemitidos a fim de `lyncdiscover.<domain>` acomodar `lyncdiscoverinternal.<domain>` os registros obrigatórios e DNS.</span><span class="sxs-lookup"><span data-stu-id="4941d-113">If the decision was made to use HTTPS, certificates on reverse proxies, Directors, and Front End Servers needed to be reissued in order to accommodate the required `lyncdiscover.<domain>` and `lyncdiscoverinternal.<domain>` DNS records.</span></span> <span data-ttu-id="4941d-114">Se a decisão era usar HTTP, a reemissão de certificados pode ser evitada usando registros CNAME (ou alias) DNS para usar os nomes existentes nos certificados.</span><span class="sxs-lookup"><span data-stu-id="4941d-114">If the decision was to use HTTP, the reissue of certificates could be avoided by using DNS CNAME (or alias) records to use existing names on the certificates.</span></span> <span data-ttu-id="4941d-115">Usar HTTP significa que as comunicações iniciais não foram criptografadas.</span><span class="sxs-lookup"><span data-stu-id="4941d-115">Using HTTP did mean that the initial communications were unencrypted.</span></span>

<span data-ttu-id="4941d-116">Como o Lync Server 2013 usa a descoberta automática para todos os clientes, o cenário principal é usar HTTPS exclusivamente e criar certificados com o lyncdiscover. \<domínio\> como parte da configuração de proxies reverso, diretores e servidores front-end.</span><span class="sxs-lookup"><span data-stu-id="4941d-116">Because Lync Server 2013 uses Autodiscover for all clients, the main scenario is to use HTTPS exclusively and to create certificates with lyncdiscover.\<domain\> as part of the configuration of reverse proxies, Directors and Front End Servers.</span></span> <span data-ttu-id="4941d-117">Se você estiver implementando a descoberta automática em uma implantação atualizada do Lync Server 2010, talvez queira usar HTTP para evitar a reemissão de certificados.</span><span class="sxs-lookup"><span data-stu-id="4941d-117">If you are implementing Autodiscover into an upgraded deployment from Lync Server 2010, you may want to use HTTP to avoid reissuing certificates.</span></span> <span data-ttu-id="4941d-118">As diretrizes para ambos os cenários são fornecidas nas seções a seguir.</span><span class="sxs-lookup"><span data-stu-id="4941d-118">Guidance for both scenarios is provided in the following sections.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="4941d-119">A lista de nomes alternativos de entidades nos certificados usados pela regra de publicação de serviços Web externos deve conter um <EM>lyncdiscover.&lt; entrada&gt; sipdomain</EM> para cada domínio SIP em sua organização.</span><span class="sxs-lookup"><span data-stu-id="4941d-119">The subject alternative name list on certificates used by the external web services publishing rule must contain a <EM>lyncdiscover.&lt;sipdomain&gt;</EM> entry for each SIP domain within your organization.</span></span> <span data-ttu-id="4941d-120">Para obter detalhes sobre as entradas de nome alternativo do assunto que são necessárias para os directors, servidores front-end e proxies reverso, consulte <A href="lync-server-2013-certificate-summary-autodiscover.md">Resumo de certificados-descoberta automática no Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="4941d-120">For details about the subject alternative name entries that are required for Directors, Front End Servers, and reverse proxies, see <A href="lync-server-2013-certificate-summary-autodiscover.md">Certificate summary - Autodiscover in Lync Server 2013</A>.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="4941d-121">Nesta seção</span><span class="sxs-lookup"><span data-stu-id="4941d-121">In This Section</span></span>

  - [<span data-ttu-id="4941d-122">Resumo do certificado-descoberta automática no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4941d-122">Certificate summary - Autodiscover in Lync Server 2013</span></span>](lync-server-2013-certificate-summary-autodiscover.md)

  - [<span data-ttu-id="4941d-123">Resumo da porta-descoberta automática no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4941d-123">Port summary - Autodiscover in Lync Server 2013</span></span>](lync-server-2013-port-summary-autodiscover.md)

  - [<span data-ttu-id="4941d-124">Resumo de DNS-descoberta automática no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4941d-124">DNS summary - Autodiscover in Lync Server 2013</span></span>](lync-server-2013-dns-summary-autodiscover.md)

  - [<span data-ttu-id="4941d-125">Descoberta automática de domínio híbrido e dividido no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4941d-125">Hybrid and split-domain - Autodiscover in Lync Server 2013</span></span>](lync-server-2013-hybrid-and-split-domain-autodiscover.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

