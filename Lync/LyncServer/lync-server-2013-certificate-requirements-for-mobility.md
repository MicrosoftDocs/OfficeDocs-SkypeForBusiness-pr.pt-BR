---
title: 'Lync Server 2013: requisitos de certificado para mobilidade'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Certificate requirements for mobility
ms:assetid: bb0e97af-cf60-4271-a0ab-654429d884ea
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh690044(v=OCS.15)
ms:contentKeyID: 48185251
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: bbf7dd0f3ce9868fbeac5c757fce5371ad77fba4
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42038413"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="certificate-requirements-for-mobility-in-lync-server-2013"></a><span data-ttu-id="b66d5-102">Requisitos de certificado para mobilidade no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b66d5-102">Certificate requirements for mobility in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b66d5-103">_**Última modificação do tópico:** 2012-06-24_</span><span class="sxs-lookup"><span data-stu-id="b66d5-103">_**Topic Last Modified:** 2012-06-24_</span></span>

<span data-ttu-id="b66d5-104">Se você implantar o recurso de mobilidade e suportar a descoberta automática para clientes móveis, será necessário incluir determinadas entradas de nome de entidade alternativo nos certificados a fim de suportar conexões seguras de clientes móveis.</span><span class="sxs-lookup"><span data-stu-id="b66d5-104">If you deploy the mobility feature and support automatic discovery for mobile clients, you need to include certain subject alternative name entries on certificates to support secure connections from the mobile clients.</span></span>

<span data-ttu-id="b66d5-105">É necessário incluir entradas de nome de entidade alternativo para a descoberta automática nos certificados a seguir:</span><span class="sxs-lookup"><span data-stu-id="b66d5-105">You need to include subject alternative name entries for automatic discovery on the following certificates:</span></span>

  - <span data-ttu-id="b66d5-106">Director pool</span><span class="sxs-lookup"><span data-stu-id="b66d5-106">Director pool</span></span>

  - <span data-ttu-id="b66d5-107">Pool de Front-Ends</span><span class="sxs-lookup"><span data-stu-id="b66d5-107">Front End pool</span></span>

  - <span data-ttu-id="b66d5-108">Proxy reverso</span><span class="sxs-lookup"><span data-stu-id="b66d5-108">Reverse proxy</span></span>

<span data-ttu-id="b66d5-109">Esta seção descreve as entradas de nome de entidade alternativo necessárias em seus certificados para descoberta automática.</span><span class="sxs-lookup"><span data-stu-id="b66d5-109">This section describes the subject alternative name entries that are required on your certificates for automatic discovery.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="b66d5-110">A reemissão de certificados usando uma autoridade de certificação interna é normalmente um processo simples, mas a adição de múltiplas entradas de nome de entidade alternativo aos certificados públicos usados pelo proxy reverso pode ser cara.</span><span class="sxs-lookup"><span data-stu-id="b66d5-110">Reissuing certificates by using an internal certificate authority is typically a simple process, but adding multiple subject alternative name entries to public certificates used by the reverse proxy can be expensive.</span></span> <span data-ttu-id="b66d5-111">Se você tiver muitos domínios SIP, tornando a adição de nomes de entidade alternativos muito cara, será possível configurar o proxy reverso para usar HTTP para a solicitação do Serviço de Descoberta Automática, em vez de usar HTTPS (a configuração padrão).</span><span class="sxs-lookup"><span data-stu-id="b66d5-111">If you have many SIP domains, making the addition of subject alternative names very expensive, you can configure the reverse proxy to use HTTP for the initial Autodiscover Service request, instead of using HTTPS (the default configuration).</span></span> <span data-ttu-id="b66d5-112">Para obter detalhes, consulte <A href="lync-server-2013-technical-requirements-for-mobility.md">Technical Requirements for Mobility in Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="b66d5-112">For details, see <A href="lync-server-2013-technical-requirements-for-mobility.md">Technical requirements for mobility in Lync Server 2013</A>.</span></span>



</div>

### <a name="director-pool-certificate-requirements"></a><span data-ttu-id="b66d5-113">Requisitos de certificado do Pool de Diretores</span><span class="sxs-lookup"><span data-stu-id="b66d5-113">Director Pool Certificate Requirements</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="b66d5-114">Descrição</span><span class="sxs-lookup"><span data-stu-id="b66d5-114">Description</span></span></th>
<th><span data-ttu-id="b66d5-115">Entrada de nome de entidade alternativo</span><span class="sxs-lookup"><span data-stu-id="b66d5-115">Subject alternative name entry</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b66d5-116">URL interna do serviço de Descoberta Automática</span><span class="sxs-lookup"><span data-stu-id="b66d5-116">Internal Autodiscover Service URL</span></span></p></td>
<td><p><span data-ttu-id="b66d5-117">SAN = lyncdiscoverinternal. &lt;sipdomain&gt;</span><span class="sxs-lookup"><span data-stu-id="b66d5-117">SAN=lyncdiscoverinternal.&lt;sipdomain&gt;</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b66d5-118">URL externa do serviço de Descoberta Automática</span><span class="sxs-lookup"><span data-stu-id="b66d5-118">External Autodiscover Service URL</span></span></p></td>
<td><p><span data-ttu-id="b66d5-119">SAN = lyncdiscover. &lt;sipdomain&gt;</span><span class="sxs-lookup"><span data-stu-id="b66d5-119">SAN=lyncdiscover.&lt;sipdomain&gt;</span></span></p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <span data-ttu-id="b66d5-120">Como alternativa, você pode usar SAN = \*. &lt;sipdomain&gt;</span><span class="sxs-lookup"><span data-stu-id="b66d5-120">Alternatively, you can use SAN=\*.&lt;sipdomain&gt;</span></span>



</div>

### <a name="front-end-pool-certificate-requirements"></a><span data-ttu-id="b66d5-121">Requisitos de certificado do pool Front-End</span><span class="sxs-lookup"><span data-stu-id="b66d5-121">Front End Pool Certificate Requirements</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="b66d5-122">Descrição</span><span class="sxs-lookup"><span data-stu-id="b66d5-122">Description</span></span></th>
<th><span data-ttu-id="b66d5-123">Entrada de nome de entidade alternativo</span><span class="sxs-lookup"><span data-stu-id="b66d5-123">Subject alternative name entry</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b66d5-124">URL interna do serviço de Descoberta Automática</span><span class="sxs-lookup"><span data-stu-id="b66d5-124">Internal Autodiscover Service URL</span></span></p></td>
<td><p><span data-ttu-id="b66d5-125">SAN = lyncdiscoverinternal. &lt;sipdomain&gt;</span><span class="sxs-lookup"><span data-stu-id="b66d5-125">SAN=lyncdiscoverinternal.&lt;sipdomain&gt;</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b66d5-126">URL externa do serviço de Descoberta Automática</span><span class="sxs-lookup"><span data-stu-id="b66d5-126">External Autodiscover Service URL</span></span></p></td>
<td><p><span data-ttu-id="b66d5-127">SAN = lyncdiscover. &lt;sipdomain&gt;</span><span class="sxs-lookup"><span data-stu-id="b66d5-127">SAN=lyncdiscover.&lt;sipdomain&gt;</span></span></p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <span data-ttu-id="b66d5-128">Como alternativa, você pode usar SAN = \*. &lt;sipdomain&gt;</span><span class="sxs-lookup"><span data-stu-id="b66d5-128">Alternatively, you can use SAN=\*.&lt;sipdomain&gt;</span></span>



</div>

### <a name="reverse-proxy-public-ca-certificate-requirements"></a><span data-ttu-id="b66d5-129">Requisitos de certificado de proxy reverso (CA pública)</span><span class="sxs-lookup"><span data-stu-id="b66d5-129">Reverse Proxy (Public CA) Certificate Requirements</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="b66d5-130">Descrição</span><span class="sxs-lookup"><span data-stu-id="b66d5-130">Description</span></span></th>
<th><span data-ttu-id="b66d5-131">Entrada de nome de entidade alternativo</span><span class="sxs-lookup"><span data-stu-id="b66d5-131">Subject alternative name entry</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b66d5-132">URL externa do serviço de Descoberta Automática</span><span class="sxs-lookup"><span data-stu-id="b66d5-132">External Autodiscover Service URL</span></span></p></td>
<td><p><span data-ttu-id="b66d5-133">SAN = lyncdiscover. &lt;sipdomain&gt;</span><span class="sxs-lookup"><span data-stu-id="b66d5-133">SAN=lyncdiscover.&lt;sipdomain&gt;</span></span></p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <span data-ttu-id="b66d5-134">Atribua esse SAN ao certificado atribuído ao Ouvinte de SSL no proxy reverso.</span><span class="sxs-lookup"><span data-stu-id="b66d5-134">You assign this SAN to the certificate assigned to the SSL Listener on the reverse proxy.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="b66d5-135">Seu ouvinte de proxy reverso terá nomes alternativos de entidade para suas URLs de serviços Web externos (por exemplo, SAN = lyncwebextpool01. contoso. com e dirwebexternal.contoso.com se você tiver implantado o diretor opcional).</span><span class="sxs-lookup"><span data-stu-id="b66d5-135">Your reverse proxy listener will have subject alternative names for your external Web Services URL(s) (for example, SAN=lyncwebextpool01.contoso.com, and dirwebexternal.contoso.com if you have deployed the optional Director).</span></span>



</div>

</div>

<span> </span>

</div>

</div>

</div>

