---
title: 'Lync Server 2013: Resumo de certificado-proxy reverso'
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
ms.openlocfilehash: e5691b20031d9998877a64f34f6578b654494a99
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42151161"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="certificate-summary---reverse-proxy-in-lync-server-2013"></a><span data-ttu-id="d8480-102">Resumo de certificado-proxy reverso no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d8480-102">Certificate summary - Reverse proxy in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d8480-103">_**Última modificação do tópico:** 2012-11-14_</span><span class="sxs-lookup"><span data-stu-id="d8480-103">_**Topic Last Modified:** 2012-11-14_</span></span>

<span data-ttu-id="d8480-104">Os requisitos de certificado para o proxy reverso são muito mais simples do que os servidores de borda.</span><span class="sxs-lookup"><span data-stu-id="d8480-104">Certificate requirements for the reverse proxy are much simpler than that for the Edge Servers.</span></span> <span data-ttu-id="d8480-105">O fluxograma fornecido apresenta os requisitos necessários.</span><span class="sxs-lookup"><span data-stu-id="d8480-105">The provided flowchart presents the requirements necessary.</span></span> <span data-ttu-id="d8480-106">A tabela a seguir apresenta os nomes de entidade de certificado típicos e os nomes alternativos da entidade em relação aos cenários que foram revisados nas discussões do servidor de borda.</span><span class="sxs-lookup"><span data-stu-id="d8480-106">The accompanying table presents typical certificate subject name and subject alternative names in relation to the scenarios that we have been reviewed in the Edge Server discussions.</span></span> <span data-ttu-id="d8480-107">Para obter mais detalhes sobre os cenários de servidor de borda, consulte [cenários para acesso de usuário externo no Lync Server 2013](lync-server-2013-scenarios-for-external-user-access.md).</span><span class="sxs-lookup"><span data-stu-id="d8480-107">For more details on the Edge Server scenarios, see [Scenarios for external user access in Lync Server 2013](lync-server-2013-scenarios-for-external-user-access.md).</span></span>

<span data-ttu-id="d8480-108">**Fluxograma de certificados para proxy reverso**</span><span class="sxs-lookup"><span data-stu-id="d8480-108">**Certificates Flow Chart for Reverse Proxy**</span></span>

<span data-ttu-id="d8480-109">![Fluxograma de certificados do Servidor de Borda](images/JJ205381.026045d7-1b4b-4651-b32f-2d43a7161198(OCS.15).jpg "Fluxograma de certificados do Servidor de Borda")</span><span class="sxs-lookup"><span data-stu-id="d8480-109">![Certificates Flow Chart for Edge Server](images/JJ205381.026045d7-1b4b-4651-b32f-2d43a7161198(OCS.15).jpg "Certificates Flow Chart for Edge Server")</span></span>

### <a name="reverse-proxy-external-interface"></a><span data-ttu-id="d8480-110">Proxy Reverso: Interface Externa</span><span class="sxs-lookup"><span data-stu-id="d8480-110">Reverse Proxy: External Interface</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="d8480-111">Componente</span><span class="sxs-lookup"><span data-stu-id="d8480-111">Component</span></span></th>
<th><span data-ttu-id="d8480-112">Nome da entidade</span><span class="sxs-lookup"><span data-stu-id="d8480-112">Subject name</span></span></th>
<th><span data-ttu-id="d8480-113">Ordem/Nome de entidade alternativo (SAN)</span><span class="sxs-lookup"><span data-stu-id="d8480-113">Subject alternative name (SAN)/Order</span></span></th>
<th><span data-ttu-id="d8480-114">Comentários</span><span class="sxs-lookup"><span data-stu-id="d8480-114">Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d8480-115">Proxy reverso</span><span class="sxs-lookup"><span data-stu-id="d8480-115">Reverse Proxy</span></span></p></td>
<td><p><span data-ttu-id="d8480-116">webext.contoso.com</span><span class="sxs-lookup"><span data-stu-id="d8480-116">webext.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="d8480-117">webext.contoso.com</span><span class="sxs-lookup"><span data-stu-id="d8480-117">webext.contoso.com</span></span></p>
<p><span data-ttu-id="d8480-118">webdirext.contoso.com</span><span class="sxs-lookup"><span data-stu-id="d8480-118">webdirext.contoso.com</span></span></p>
<p><span data-ttu-id="d8480-119">dialin.contoso.com</span><span class="sxs-lookup"><span data-stu-id="d8480-119">dialin.contoso.com</span></span></p>
<p><span data-ttu-id="d8480-120">meet.contoso.com</span><span class="sxs-lookup"><span data-stu-id="d8480-120">meet.contoso.com</span></span></p>
<p><span data-ttu-id="d8480-121">officewebapps01.contoso.com</span><span class="sxs-lookup"><span data-stu-id="d8480-121">officewebapps01.contoso.com</span></span></p>
<p><span data-ttu-id="d8480-122">lyncdiscover.contoso.com</span><span class="sxs-lookup"><span data-stu-id="d8480-122">lyncdiscover.contoso.com</span></span></p>
<p><span data-ttu-id="d8480-123">(Opcional):\*. contoso.com</span><span class="sxs-lookup"><span data-stu-id="d8480-123">(Optional):\*.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="d8480-124">O certificado deve ser emitido por um CA público e com o EKU do servidor.</span><span class="sxs-lookup"><span data-stu-id="d8480-124">Certificate must be issued by a public CA and with the server EKU.</span></span> <span data-ttu-id="d8480-125">Os serviços incluem serviço de catálogo de endereços, expansão de grupo de distribuição do Office Web Apps para conferência e regras de publicação de dispositivo IP do Lync.</span><span class="sxs-lookup"><span data-stu-id="d8480-125">Services include Address Book Service, distribution group expansion Office Web Apps for conferencing, and Lync IP Device publishing rules.</span></span> <span data-ttu-id="d8480-126">Os nomes de entidade alternativos incluem:</span><span class="sxs-lookup"><span data-stu-id="d8480-126">Subject alternative name includes:</span></span></p>
<ul>
<li><p><span data-ttu-id="d8480-127">FQDN de serviços Web externos para o servidor front-end ou o pool de front-ends</span><span class="sxs-lookup"><span data-stu-id="d8480-127">External Web Services FQDN for Front End Server or Front End pool</span></span></p></li>
<li><p><span data-ttu-id="d8480-128">FQDN de serviços Web externos para diretor ou pool de diretor</span><span class="sxs-lookup"><span data-stu-id="d8480-128">External Web Services FQDN for Director or Director pool</span></span></p></li>
<li><p><span data-ttu-id="d8480-129">Conferência Discada</span><span class="sxs-lookup"><span data-stu-id="d8480-129">Dial-in conferencing</span></span></p></li>
<li><p><span data-ttu-id="d8480-130">Regra de publicação da reunião online</span><span class="sxs-lookup"><span data-stu-id="d8480-130">Online meeting publishing rule</span></span></p></li>
<li><p><span data-ttu-id="d8480-131">Office Web Apps para conferência</span><span class="sxs-lookup"><span data-stu-id="d8480-131">Office Web Apps for conferencing</span></span></p></li>
<li><p><span data-ttu-id="d8480-132">Lyncdiscover (Descoberta automática)</span><span class="sxs-lookup"><span data-stu-id="d8480-132">Lyncdiscover (Autodiscover)</span></span></p></li>
</ul>
<p><span data-ttu-id="d8480-133">O curinga opcional substitui o SAN discado e reunião</span><span class="sxs-lookup"><span data-stu-id="d8480-133">The optional wildcard replaces both meet and dialin SAN</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

