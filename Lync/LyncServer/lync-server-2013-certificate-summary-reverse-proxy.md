---
title: 'Lync Server 2013: Resumo de certificado-proxy reverso'
description: 'Lync Server 2013: Resumo de certificado-proxy reverso.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Certificate summary - Reverse proxy
ms:assetid: f2b9a53f-aead-413d-81e9-4a294a010fbb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205381(v=OCS.15)
ms:contentKeyID: 48185820
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0cc250d6de2eb1a0b6c3ad3495c8df62942f9a81
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48572297"
---
# <a name="certificate-summary---reverse-proxy-in-lync-server-2013"></a><span data-ttu-id="28a45-103">Resumo de certificado-proxy reverso no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="28a45-103">Certificate summary - Reverse proxy in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="28a45-104">_**Última modificação do tópico:** 2012-11-14_</span><span class="sxs-lookup"><span data-stu-id="28a45-104">_**Topic Last Modified:** 2012-11-14_</span></span>

<span data-ttu-id="28a45-105">Os requisitos de certificado para o proxy reverso são muito mais simples do que os servidores de borda.</span><span class="sxs-lookup"><span data-stu-id="28a45-105">Certificate requirements for the reverse proxy are much simpler than that for the Edge Servers.</span></span> <span data-ttu-id="28a45-106">O fluxograma fornecido apresenta os requisitos necessários.</span><span class="sxs-lookup"><span data-stu-id="28a45-106">The provided flowchart presents the requirements necessary.</span></span> <span data-ttu-id="28a45-107">A tabela a seguir apresenta os nomes de entidade de certificado típicos e os nomes alternativos da entidade em relação aos cenários que foram revisados nas discussões do servidor de borda.</span><span class="sxs-lookup"><span data-stu-id="28a45-107">The accompanying table presents typical certificate subject name and subject alternative names in relation to the scenarios that we have been reviewed in the Edge Server discussions.</span></span> <span data-ttu-id="28a45-108">Para obter mais detalhes sobre os cenários de servidor de borda, consulte [cenários para acesso de usuário externo no Lync Server 2013](lync-server-2013-scenarios-for-external-user-access.md).</span><span class="sxs-lookup"><span data-stu-id="28a45-108">For more details on the Edge Server scenarios, see [Scenarios for external user access in Lync Server 2013](lync-server-2013-scenarios-for-external-user-access.md).</span></span>

<span data-ttu-id="28a45-109">**Fluxograma de certificados para proxy reverso**</span><span class="sxs-lookup"><span data-stu-id="28a45-109">**Certificates Flow Chart for Reverse Proxy**</span></span>

<span data-ttu-id="28a45-110">![Fluxograma de certificados do Servidor de Borda](images/JJ205381.026045d7-1b4b-4651-b32f-2d43a7161198(OCS.15).jpg "Fluxograma de certificados do Servidor de Borda")</span><span class="sxs-lookup"><span data-stu-id="28a45-110">![Certificates Flow Chart for Edge Server](images/JJ205381.026045d7-1b4b-4651-b32f-2d43a7161198(OCS.15).jpg "Certificates Flow Chart for Edge Server")</span></span>

### <a name="reverse-proxy-external-interface"></a><span data-ttu-id="28a45-111">Proxy Reverso: Interface Externa</span><span class="sxs-lookup"><span data-stu-id="28a45-111">Reverse Proxy: External Interface</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="28a45-112">Componente</span><span class="sxs-lookup"><span data-stu-id="28a45-112">Component</span></span></th>
<th><span data-ttu-id="28a45-113">Nome da entidade</span><span class="sxs-lookup"><span data-stu-id="28a45-113">Subject name</span></span></th>
<th><span data-ttu-id="28a45-114">Ordem/Nome de entidade alternativo (SAN)</span><span class="sxs-lookup"><span data-stu-id="28a45-114">Subject alternative name (SAN)/Order</span></span></th>
<th><span data-ttu-id="28a45-115">Comments</span><span class="sxs-lookup"><span data-stu-id="28a45-115">Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="28a45-116">Proxy reverso</span><span class="sxs-lookup"><span data-stu-id="28a45-116">Reverse Proxy</span></span></p></td>
<td><p><span data-ttu-id="28a45-117">webext.contoso.com</span><span class="sxs-lookup"><span data-stu-id="28a45-117">webext.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="28a45-118">webext.contoso.com</span><span class="sxs-lookup"><span data-stu-id="28a45-118">webext.contoso.com</span></span></p>
<p><span data-ttu-id="28a45-119">webdirext.contoso.com</span><span class="sxs-lookup"><span data-stu-id="28a45-119">webdirext.contoso.com</span></span></p>
<p><span data-ttu-id="28a45-120">dialin.contoso.com</span><span class="sxs-lookup"><span data-stu-id="28a45-120">dialin.contoso.com</span></span></p>
<p><span data-ttu-id="28a45-121">meet.contoso.com</span><span class="sxs-lookup"><span data-stu-id="28a45-121">meet.contoso.com</span></span></p>
<p><span data-ttu-id="28a45-122">officewebapps01.contoso.com</span><span class="sxs-lookup"><span data-stu-id="28a45-122">officewebapps01.contoso.com</span></span></p>
<p><span data-ttu-id="28a45-123">lyncdiscover.contoso.com</span><span class="sxs-lookup"><span data-stu-id="28a45-123">lyncdiscover.contoso.com</span></span></p>
<p><span data-ttu-id="28a45-124">(Opcional):\*. contoso.com</span><span class="sxs-lookup"><span data-stu-id="28a45-124">(Optional):\*.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="28a45-125">O certificado deve ser emitido por um CA público e com o EKU do servidor.</span><span class="sxs-lookup"><span data-stu-id="28a45-125">Certificate must be issued by a public CA and with the server EKU.</span></span> <span data-ttu-id="28a45-126">Os serviços incluem serviço de catálogo de endereços, expansão de grupo de distribuição do Office Web Apps para conferência e regras de publicação de dispositivo IP do Lync.</span><span class="sxs-lookup"><span data-stu-id="28a45-126">Services include Address Book Service, distribution group expansion Office Web Apps for conferencing, and Lync IP Device publishing rules.</span></span> <span data-ttu-id="28a45-127">Os nomes de entidade alternativos incluem:</span><span class="sxs-lookup"><span data-stu-id="28a45-127">Subject alternative name includes:</span></span></p>
<ul>
<li><p><span data-ttu-id="28a45-128">FQDN de serviços Web externos para o servidor front-end ou o pool de front-ends</span><span class="sxs-lookup"><span data-stu-id="28a45-128">External Web Services FQDN for Front End Server or Front End pool</span></span></p></li>
<li><p><span data-ttu-id="28a45-129">FQDN de serviços Web externos para diretor ou pool de diretor</span><span class="sxs-lookup"><span data-stu-id="28a45-129">External Web Services FQDN for Director or Director pool</span></span></p></li>
<li><p><span data-ttu-id="28a45-130">Conferência Discada</span><span class="sxs-lookup"><span data-stu-id="28a45-130">Dial-in conferencing</span></span></p></li>
<li><p><span data-ttu-id="28a45-131">Regra de publicação da reunião online</span><span class="sxs-lookup"><span data-stu-id="28a45-131">Online meeting publishing rule</span></span></p></li>
<li><p><span data-ttu-id="28a45-132">Office Web Apps para conferência</span><span class="sxs-lookup"><span data-stu-id="28a45-132">Office Web Apps for conferencing</span></span></p></li>
<li><p><span data-ttu-id="28a45-133">Lyncdiscover (Descoberta automática)</span><span class="sxs-lookup"><span data-stu-id="28a45-133">Lyncdiscover (Autodiscover)</span></span></p></li>
</ul>
<p><span data-ttu-id="28a45-134">O curinga opcional substitui o SAN discado e reunião</span><span class="sxs-lookup"><span data-stu-id="28a45-134">The optional wildcard replaces both meet and dialin SAN</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

