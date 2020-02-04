---
title: 'Lync Server 2013: Suporte a certificado curinga'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Wildcard certificate support
ms:assetid: 0bae2aa8-b6dc-46f5-a3be-3fe7581809d4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202161(v=OCS.15)
ms:contentKeyID: 48183382
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8a3e64dcfd16212e618a8ebe152bd2516a25b26d
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41727491"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="wildcard-certificate-support-in-lync-server-2013"></a><span data-ttu-id="4982b-102">Suporte a certificado curinga no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4982b-102">Wildcard certificate support in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4982b-103">_**Tópico da última modificação:** 2013-03-21_</span><span class="sxs-lookup"><span data-stu-id="4982b-103">_**Topic Last Modified:** 2013-03-21_</span></span>

<span data-ttu-id="4982b-104">O Lync Server 2013 usa certificados para fornecer criptografia de comunicação e autenticação de identidade do servidor.</span><span class="sxs-lookup"><span data-stu-id="4982b-104">Lync Server 2013 uses certificates to provide communications encryption and server identity authentication.</span></span> <span data-ttu-id="4982b-105">Em alguns casos, como a publicação na Web por meio do proxy inverso, a entrada de nome alternativo de assunto (SAN) forte para o nome de domínio totalmente qualificado (FQDN) do servidor que está apresentando o serviço não é necessária.</span><span class="sxs-lookup"><span data-stu-id="4982b-105">In some cases, such as web publishing through the reverse proxy, strong subject alternative name (SAN) entry matching to the fully qualified domain name (FQDN) of the server presenting the service is not required.</span></span> <span data-ttu-id="4982b-106">Nesses casos, você pode usar certificados com entradas de SAN curinga (geralmente conhecidas como "certificados curinga") para reduzir o custo de um certificado solicitado de uma autoridade de certificação pública e para reduzir a complexidade do processo de planejamento de certificados .</span><span class="sxs-lookup"><span data-stu-id="4982b-106">In these cases, you can use certificates with wildcard SAN entries (commonly known as “wildcard certificates”) to reduce the cost of a certificate requested from a public certification authority and to reduce the complexity of the planning process for certificates.</span></span>

<div>


> [!WARNING]  
> <span data-ttu-id="4982b-107">Para manter a funcionalidade dos dispositivos de comunicação unificada (UC) (por exemplo, telefones de mesa), você deve testar cuidadosamente o certificado implantado para garantir que os dispositivos funcionarão corretamente após a implementação de um certificado curinga.</span><span class="sxs-lookup"><span data-stu-id="4982b-107">To retain the functionality of unified communications (UC) devices (for example, desk phones), you should test the deployed certificate carefully to ensure that devices function properly after you implement a wildcard certificate.</span></span>



</div>

<span data-ttu-id="4982b-108">Não há suporte para uma entrada de curinga como o nome do requerente (também conhecido como o nome comum ou CN) para qualquer função.</span><span class="sxs-lookup"><span data-stu-id="4982b-108">There is no support for a wildcard entry as the subject name (also referred to as the common name or CN) for any role.</span></span> <span data-ttu-id="4982b-109">As seguintes funções de servidor são suportadas ao usar entradas de curinga na SAN:</span><span class="sxs-lookup"><span data-stu-id="4982b-109">The following server roles are supported when using wildcard entries in the SAN:</span></span>

  - <span></span>  
    <span data-ttu-id="4982b-110">**Proxy reverso.**    Há suporte para a entrada de San curinga para o certificado de publicação URL simples (reunião e discagem).</span><span class="sxs-lookup"><span data-stu-id="4982b-110">**Reverse proxy.**   Wildcard SAN entry is supported for Simple URL (meet and dialin) publishing certificate.</span></span>

  - <span></span>  
    <span data-ttu-id="4982b-111">**Proxy reverso.**    Há suporte para a entrada de San curinga nas entradas de San para LyncDiscover no certificado de publicação.</span><span class="sxs-lookup"><span data-stu-id="4982b-111">**Reverse proxy.**   Wildcard SAN entry is supported for the SAN entries for LyncDiscover on the publishing certificate.</span></span>

  - <span></span>  
    <span data-ttu-id="4982b-112">**Diretor.**    Há suporte para a entrada de San curinga para URLs simples (atender e fazer chamadas) e para entradas de San para LyncDiscover e LyncDiscoverInternal em Web Components do director.</span><span class="sxs-lookup"><span data-stu-id="4982b-112">**Director.**   Wildcard SAN entry is supported for Simple URLs (meet and dialin) and for SAN entries for LyncDiscover and LyncDiscoverInternal in Director web components.</span></span>

  - <span></span>  
    <span data-ttu-id="4982b-113">**Servidor front-end (Standard Edition) e pool de front-end (Enterprise Edition).**</span><span class="sxs-lookup"><span data-stu-id="4982b-113">**Front End Server (Standard Edition) and Front End pool (Enterprise Edition).**</span></span> <span data-ttu-id="4982b-114">Há suporte para a entrada de SAN curinga para URLs simples (atender e discagem) e para entradas de SAN para LyncDiscover e LyncDiscoverInternal em componentes de front-end Web.</span><span class="sxs-lookup"><span data-stu-id="4982b-114">Wildcard SAN entry is supported for Simple URLs (meet and dialin) and for SAN entries for LyncDiscover and LyncDiscoverInternal in Front End web components.</span></span>

  - <span></span>  
    <span data-ttu-id="4982b-115">**Exchange Unified Messaging (UM).**    O servidor não usa entradas de San quando implantado como um servidor autônomo.</span><span class="sxs-lookup"><span data-stu-id="4982b-115">**Exchange Unified Messaging (UM).**   The server does not use SAN entries when deployed as a stand-alone server.</span></span>

  - <span></span>  
    <span data-ttu-id="4982b-116">**Servidor de acesso para cliente do Microsoft Exchange Server.**    As entradas CURINGA na San têm suporte para clientes internos e externos.</span><span class="sxs-lookup"><span data-stu-id="4982b-116">**Microsoft Exchange Server Client Access server.**   Wildcard entries in the SAN are supported for internal and external clients.</span></span>

  - <span></span>  
    <span data-ttu-id="4982b-117">**Exchange Unified Messaging (UM) e servidor de acesso para cliente do Microsoft Exchange Server no mesmo servidor.**    Há suporte para entradas de San curinga.</span><span class="sxs-lookup"><span data-stu-id="4982b-117">**Exchange Unified Messaging (UM) and Microsoft Exchange Server Client Access server on same server.**   Wildcard SAN entries are supported.</span></span>

<span data-ttu-id="4982b-118">Funções de servidor que não são abordadas neste tópico:</span><span class="sxs-lookup"><span data-stu-id="4982b-118">Server roles that are not addressed in this topic:</span></span>

  - <span data-ttu-id="4982b-119">Funções de servidor interno (incluindo, entre outros, o servidor de mediação, o servidor de monitoramento e o servidor de mediação, o aparelho de ramificação sobreviventes ou o servidor de ramificação sobreviventes)</span><span class="sxs-lookup"><span data-stu-id="4982b-119">Internal server roles (including, but not limited to the Mediation Server, Archiving and Monitoring Server, Survivable Branch Appliance, or Survivable Branch Server)</span></span>

  - <span data-ttu-id="4982b-120">Interfaces do servidor de borda externa</span><span class="sxs-lookup"><span data-stu-id="4982b-120">External Edge Server interfaces</span></span>

  - <span data-ttu-id="4982b-121">Servidor de borda interna</span><span class="sxs-lookup"><span data-stu-id="4982b-121">Internal Edge Server</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="4982b-122">Para a interface do servidor de borda interna, uma entrada de curinga pode ser atribuída à SAN e é compatível.</span><span class="sxs-lookup"><span data-stu-id="4982b-122">For the internal Edge Server interface, a wildcard entry can be assigned to the SAN, and is supported.</span></span> <span data-ttu-id="4982b-123">A SAN no servidor de borda interno não é consultada e uma entrada de SAN por curinga tem um valor limitado.</span><span class="sxs-lookup"><span data-stu-id="4982b-123">The SAN on the internal Edge Server is not queried, and a wildcard SAN entry is of limited value.</span></span>

    
    </div>

<span data-ttu-id="4982b-124">Para obter detalhes sobre configurações de certificado, incluindo o uso de caracteres curinga em certificados, consulte os seguintes tópicos:</span><span class="sxs-lookup"><span data-stu-id="4982b-124">For details about certificate configurations, including the use of wildcards in certificates, see the following topics:</span></span>

  - [<span data-ttu-id="4982b-125">Requisitos de certificado para servidores internos no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4982b-125">Certificate requirements for internal servers in Lync Server 2013</span></span>](lync-server-2013-certificate-requirements-for-internal-servers.md)

  - [<span data-ttu-id="4982b-126">Requisitos de certificado para acesso do usuário externo no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4982b-126">Certificate requirements for external user access in Lync Server 2013</span></span>](lync-server-2013-certificate-requirements-for-external-user-access.md)

  - [<span data-ttu-id="4982b-127">Resumo de certificado - Cargas de DNS e de HLB balanceadas no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4982b-127">Certificate summary - DNS and HLB load balanced in Lync Server 2013</span></span>](lync-server-2013-certificate-summary-dns-and-hlb-load-balanced.md)

  - [<span data-ttu-id="4982b-128">Resumo do certificado - Diretor único no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4982b-128">Certificate summary - Single Director in Lync Server 2013</span></span>](lync-server-2013-certificate-summary-single-director.md)

  - [<span data-ttu-id="4982b-129">Resumo de certificado - pool Certificate summary - pool de diretores em escala, balanceador de carga de hardware no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4982b-129">Certificate summary - Scaled Director pool, hardware load balancer in Lync Server 2013</span></span>](lync-server-2013-certificate-summary-scaled-director-pool-hardware-load-balancer.md)

  - [<span data-ttu-id="4982b-130">Resumo de certificado - Proxy reverso no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4982b-130">Certificate summary - Reverse proxy in Lync Server 2013</span></span>](lync-server-2013-certificate-summary-reverse-proxy.md)

  - [<span data-ttu-id="4982b-131">Orientações para integração de Unificação de Mensagens local e Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4982b-131">Guidelines for integrating on-premises Unified Messaging and Lync Server 2013</span></span>](lync-server-2013-guidelines-for-integrating-on-premises-unified-messaging.md)

<span data-ttu-id="4982b-132">Para obter detalhes sobre como configurar certificados para Exchange, incluindo o uso de caracteres curinga, consulte a documentação do produto Exchange 2013.</span><span class="sxs-lookup"><span data-stu-id="4982b-132">For details about configuring certificates for Exchange, including the use of wildcards, see the Exchange 2013 product documentation.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

