---
title: 'Lync Server 2013: Resumo de certificado - Proxy reverso'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Certificate summary - Reverse proxy
ms:assetid: f2b9a53f-aead-413d-81e9-4a294a010fbb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205381(v=OCS.15)
ms:contentKeyID: 48185820
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b9a10259ac4a0beb6d79897b26bf446b109801a8
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34836642"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="certificate-summary---reverse-proxy-in-lync-server-2013"></a><span data-ttu-id="44b02-102">Resumo de certificado - Proxy reverso no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="44b02-102">Certificate summary - Reverse proxy in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="44b02-103">_**Tópico da última modificação:** 2012-11-14_</span><span class="sxs-lookup"><span data-stu-id="44b02-103">_**Topic Last Modified:** 2012-11-14_</span></span>

<span data-ttu-id="44b02-104">Os requisitos de certificado para o proxy reverso são muito mais simples do que os servidores de borda.</span><span class="sxs-lookup"><span data-stu-id="44b02-104">Certificate requirements for the reverse proxy are much simpler than that for the Edge Servers.</span></span> <span data-ttu-id="44b02-105">O fluxograma fornecido apresenta os requisitos necessários.</span><span class="sxs-lookup"><span data-stu-id="44b02-105">The provided flowchart presents the requirements necessary.</span></span> <span data-ttu-id="44b02-106">A tabela a seguir apresenta nomes de entidades de certificado típicos e nomes alternativos de assunto em relação aos cenários em que foi revisado nas discussões do servidor de borda.</span><span class="sxs-lookup"><span data-stu-id="44b02-106">The accompanying table presents typical certificate subject name and subject alternative names in relation to the scenarios that we have been reviewed in the Edge Server discussions.</span></span> <span data-ttu-id="44b02-107">Para obter mais detalhes sobre os cenários do servidor de borda, consulte [cenários para acesso de usuários externos no Lync Server 2013](lync-server-2013-scenarios-for-external-user-access.md).</span><span class="sxs-lookup"><span data-stu-id="44b02-107">For more details on the Edge Server scenarios, see [Scenarios for external user access in Lync Server 2013](lync-server-2013-scenarios-for-external-user-access.md).</span></span>

<span data-ttu-id="44b02-108">**Fluxograma de certificados para proxy reverso**</span><span class="sxs-lookup"><span data-stu-id="44b02-108">**Certificates Flow Chart for Reverse Proxy**</span></span>

<span data-ttu-id="44b02-109">![Fluxograma de certificados do servidor de borda] (images/JJ205381.026045d7-1b4b-4651-b32f-2d43a7161198(OCS.15).jpg "Fluxograma de certificados do servidor de borda")</span><span class="sxs-lookup"><span data-stu-id="44b02-109">![Certificates Flow Chart for Edge Server](images/JJ205381.026045d7-1b4b-4651-b32f-2d43a7161198(OCS.15).jpg "Certificates Flow Chart for Edge Server")</span></span>

### <a name="reverse-proxy-external-interface"></a><span data-ttu-id="44b02-110">Proxy inverso: interface externa</span><span class="sxs-lookup"><span data-stu-id="44b02-110">Reverse Proxy: External Interface</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="44b02-111">Componente</span><span class="sxs-lookup"><span data-stu-id="44b02-111">Component</span></span></th>
<th><span data-ttu-id="44b02-112">Nome do assunto</span><span class="sxs-lookup"><span data-stu-id="44b02-112">Subject name</span></span></th>
<th><span data-ttu-id="44b02-113">Nome alternativo do assunto (SAN)/Order</span><span class="sxs-lookup"><span data-stu-id="44b02-113">Subject alternative name (SAN)/Order</span></span></th>
<th><span data-ttu-id="44b02-114">Comentários</span><span class="sxs-lookup"><span data-stu-id="44b02-114">Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="44b02-115">Proxy reverso</span><span class="sxs-lookup"><span data-stu-id="44b02-115">Reverse Proxy</span></span></p></td>
<td><p><span data-ttu-id="44b02-116">webext.contoso.com</span><span class="sxs-lookup"><span data-stu-id="44b02-116">webext.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="44b02-117">webext.contoso.com</span><span class="sxs-lookup"><span data-stu-id="44b02-117">webext.contoso.com</span></span></p>
<p><span data-ttu-id="44b02-118">webdirext.contoso.com</span><span class="sxs-lookup"><span data-stu-id="44b02-118">webdirext.contoso.com</span></span></p>
<p><span data-ttu-id="44b02-119">dialin.contoso.com</span><span class="sxs-lookup"><span data-stu-id="44b02-119">dialin.contoso.com</span></span></p>
<p><span data-ttu-id="44b02-120">meet.contoso.com</span><span class="sxs-lookup"><span data-stu-id="44b02-120">meet.contoso.com</span></span></p>
<p><span data-ttu-id="44b02-121">officewebapps01.contoso.com</span><span class="sxs-lookup"><span data-stu-id="44b02-121">officewebapps01.contoso.com</span></span></p>
<p><span data-ttu-id="44b02-122">lyncdiscover.contoso.com</span><span class="sxs-lookup"><span data-stu-id="44b02-122">lyncdiscover.contoso.com</span></span></p>
<p><span data-ttu-id="44b02-123">(Opcional):\*. contoso.com</span><span class="sxs-lookup"><span data-stu-id="44b02-123">(Optional):\*.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="44b02-124">O certificado deve ser emitido por uma CA pública e com o EKU do servidor.</span><span class="sxs-lookup"><span data-stu-id="44b02-124">Certificate must be issued by a public CA and with the server EKU.</span></span> <span data-ttu-id="44b02-125">Serviços incluem serviço de catálogo de endereços, expansão do grupo de distribuição Office Web Apps para conferência e regras de publicação de dispositivo IP do Lync.</span><span class="sxs-lookup"><span data-stu-id="44b02-125">Services include Address Book Service, distribution group expansion Office Web Apps for conferencing, and Lync IP Device publishing rules.</span></span> <span data-ttu-id="44b02-126">O nome alternativo para o assunto inclui:</span><span class="sxs-lookup"><span data-stu-id="44b02-126">Subject alternative name includes:</span></span></p>
<ul>
<li><p><span data-ttu-id="44b02-127">FQDN de serviços Web externos para servidor front-end ou pool de front-end</span><span class="sxs-lookup"><span data-stu-id="44b02-127">External Web Services FQDN for Front End Server or Front End pool</span></span></p></li>
<li><p><span data-ttu-id="44b02-128">FQDN de serviços Web externos para o diretor ou pool do diretor</span><span class="sxs-lookup"><span data-stu-id="44b02-128">External Web Services FQDN for Director or Director pool</span></span></p></li>
<li><p><span data-ttu-id="44b02-129">Conferência discada</span><span class="sxs-lookup"><span data-stu-id="44b02-129">Dial-in conferencing</span></span></p></li>
<li><p><span data-ttu-id="44b02-130">Regra de publicação de reunião online</span><span class="sxs-lookup"><span data-stu-id="44b02-130">Online meeting publishing rule</span></span></p></li>
<li><p><span data-ttu-id="44b02-131">Office Web Apps para conferência</span><span class="sxs-lookup"><span data-stu-id="44b02-131">Office Web Apps for conferencing</span></span></p></li>
<li><p><span data-ttu-id="44b02-132">Lyncdiscover (descoberta automática)</span><span class="sxs-lookup"><span data-stu-id="44b02-132">Lyncdiscover (Autodiscover)</span></span></p></li>
</ul>
<p><span data-ttu-id="44b02-133">O curinga opcional substitui a SAN e a discagem</span><span class="sxs-lookup"><span data-stu-id="44b02-133">The optional wildcard replaces both meet and dialin SAN</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

