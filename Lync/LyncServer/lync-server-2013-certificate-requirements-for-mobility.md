---
title: 'Lync Server 2013: Requisitos de certificado para mobilidade'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Certificate requirements for mobility
ms:assetid: bb0e97af-cf60-4271-a0ab-654429d884ea
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh690044(v=OCS.15)
ms:contentKeyID: 48185251
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8f62b05fd77151250e352c62cad7084d1bb90926
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34836651"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="certificate-requirements-for-mobility-in-lync-server-2013"></a><span data-ttu-id="17277-102">Requisitos de certificado para mobilidade no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="17277-102">Certificate requirements for mobility in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="17277-103">_**Tópico da última modificação:** 2012-06-24_</span><span class="sxs-lookup"><span data-stu-id="17277-103">_**Topic Last Modified:** 2012-06-24_</span></span>

<span data-ttu-id="17277-104">Se você implantar o recurso de mobilidade e oferecer suporte à descoberta automática para clientes móveis, será necessário incluir certas entradas de nomes alternativos de entidades nos certificados para dar suporte a conexões seguras de clientes móveis.</span><span class="sxs-lookup"><span data-stu-id="17277-104">If you deploy the mobility feature and support automatic discovery for mobile clients, you need to include certain subject alternative name entries on certificates to support secure connections from the mobile clients.</span></span>

<span data-ttu-id="17277-105">Você precisa incluir entradas de nomes alternativos de entidades para descoberta automática nos seguintes certificados:</span><span class="sxs-lookup"><span data-stu-id="17277-105">You need to include subject alternative name entries for automatic discovery on the following certificates:</span></span>

  - <span data-ttu-id="17277-106">Pool de diretores</span><span class="sxs-lookup"><span data-stu-id="17277-106">Director pool</span></span>

  - <span data-ttu-id="17277-107">Pool de Front-Ends</span><span class="sxs-lookup"><span data-stu-id="17277-107">Front End pool</span></span>

  - <span data-ttu-id="17277-108">Proxy reverso</span><span class="sxs-lookup"><span data-stu-id="17277-108">Reverse proxy</span></span>

<span data-ttu-id="17277-109">Esta seção descreve as entradas de nome alternativo do assunto que são necessárias em seus certificados para descoberta automática.</span><span class="sxs-lookup"><span data-stu-id="17277-109">This section describes the subject alternative name entries that are required on your certificates for automatic discovery.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="17277-110">A emissão de certificados por meio de uma autoridade de certificação interna geralmente é um processo simples, mas adicionar várias entradas de nome alternativo à entidade para certificados públicos usados pelo proxy reverso pode ser caro.</span><span class="sxs-lookup"><span data-stu-id="17277-110">Reissuing certificates by using an internal certificate authority is typically a simple process, but adding multiple subject alternative name entries to public certificates used by the reverse proxy can be expensive.</span></span> <span data-ttu-id="17277-111">Se você tiver muitos domínios SIP, o que faz com que a adição dos nomes alternativos de assunto seja muito cara, você pode configurar o proxy reverso para usar HTTP para a solicitação inicial de serviço de descoberta automática, em vez de usar HTTPS (a configuração padrão).</span><span class="sxs-lookup"><span data-stu-id="17277-111">If you have many SIP domains, making the addition of subject alternative names very expensive, you can configure the reverse proxy to use HTTP for the initial Autodiscover Service request, instead of using HTTPS (the default configuration).</span></span> <span data-ttu-id="17277-112">Para obter detalhes, consulte <A href="lync-server-2013-technical-requirements-for-mobility.md">requisitos técnicos de mobilidade no Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="17277-112">For details, see <A href="lync-server-2013-technical-requirements-for-mobility.md">Technical requirements for mobility in Lync Server 2013</A>.</span></span>



</div>

### <a name="director-pool-certificate-requirements"></a><span data-ttu-id="17277-113">Requisitos de certificado do pool do director</span><span class="sxs-lookup"><span data-stu-id="17277-113">Director Pool Certificate Requirements</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="17277-114">Descrição</span><span class="sxs-lookup"><span data-stu-id="17277-114">Description</span></span></th>
<th><span data-ttu-id="17277-115">Entrada de nome alternativo do assunto</span><span class="sxs-lookup"><span data-stu-id="17277-115">Subject alternative name entry</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="17277-116">URL interna do serviço de descoberta automática</span><span class="sxs-lookup"><span data-stu-id="17277-116">Internal Autodiscover Service URL</span></span></p></td>
<td><p><span data-ttu-id="17277-117">SAN = lyncdiscoverinternal. &lt;sipdomain&gt;</span><span class="sxs-lookup"><span data-stu-id="17277-117">SAN=lyncdiscoverinternal.&lt;sipdomain&gt;</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="17277-118">URL do serviço de descoberta automática externo</span><span class="sxs-lookup"><span data-stu-id="17277-118">External Autodiscover Service URL</span></span></p></td>
<td><p><span data-ttu-id="17277-119">SAN = lyncdiscover. &lt;sipdomain&gt;</span><span class="sxs-lookup"><span data-stu-id="17277-119">SAN=lyncdiscover.&lt;sipdomain&gt;</span></span></p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <span data-ttu-id="17277-120">Você também pode usar SAN = \*. &lt;sipdomain&gt;</span><span class="sxs-lookup"><span data-stu-id="17277-120">Alternatively, you can use SAN=\*.&lt;sipdomain&gt;</span></span>



</div>

### <a name="front-end-pool-certificate-requirements"></a><span data-ttu-id="17277-121">Requisitos de certificado de pool de front-end</span><span class="sxs-lookup"><span data-stu-id="17277-121">Front End Pool Certificate Requirements</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="17277-122">Descrição</span><span class="sxs-lookup"><span data-stu-id="17277-122">Description</span></span></th>
<th><span data-ttu-id="17277-123">Entrada de nome alternativo do assunto</span><span class="sxs-lookup"><span data-stu-id="17277-123">Subject alternative name entry</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="17277-124">URL interna do serviço de descoberta automática</span><span class="sxs-lookup"><span data-stu-id="17277-124">Internal Autodiscover Service URL</span></span></p></td>
<td><p><span data-ttu-id="17277-125">SAN = lyncdiscoverinternal. &lt;sipdomain&gt;</span><span class="sxs-lookup"><span data-stu-id="17277-125">SAN=lyncdiscoverinternal.&lt;sipdomain&gt;</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="17277-126">URL do serviço de descoberta automática externo</span><span class="sxs-lookup"><span data-stu-id="17277-126">External Autodiscover Service URL</span></span></p></td>
<td><p><span data-ttu-id="17277-127">SAN = lyncdiscover. &lt;sipdomain&gt;</span><span class="sxs-lookup"><span data-stu-id="17277-127">SAN=lyncdiscover.&lt;sipdomain&gt;</span></span></p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <span data-ttu-id="17277-128">Você também pode usar SAN = \*. &lt;sipdomain&gt;</span><span class="sxs-lookup"><span data-stu-id="17277-128">Alternatively, you can use SAN=\*.&lt;sipdomain&gt;</span></span>



</div>

### <a name="reverse-proxy-public-ca-certificate-requirements"></a><span data-ttu-id="17277-129">Requisitos de certificado de proxy reverso (CA pública)</span><span class="sxs-lookup"><span data-stu-id="17277-129">Reverse Proxy (Public CA) Certificate Requirements</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="17277-130">Descrição</span><span class="sxs-lookup"><span data-stu-id="17277-130">Description</span></span></th>
<th><span data-ttu-id="17277-131">Entrada de nome alternativo do assunto</span><span class="sxs-lookup"><span data-stu-id="17277-131">Subject alternative name entry</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="17277-132">URL do serviço de descoberta automática externo</span><span class="sxs-lookup"><span data-stu-id="17277-132">External Autodiscover Service URL</span></span></p></td>
<td><p><span data-ttu-id="17277-133">SAN = lyncdiscover. &lt;sipdomain&gt;</span><span class="sxs-lookup"><span data-stu-id="17277-133">SAN=lyncdiscover.&lt;sipdomain&gt;</span></span></p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <span data-ttu-id="17277-134">Você atribui esta SAN ao certificado atribuído ao ouvinte SSL no proxy reverso.</span><span class="sxs-lookup"><span data-stu-id="17277-134">You assign this SAN to the certificate assigned to the SSL Listener on the reverse proxy.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="17277-135">Seu ouvinte de proxy reverso terá nomes alternativos de entidades para seus serviços Web externos (por exemplo, SAN = lyncwebextpool01. contoso. com e dirwebexternal.contoso.com se você tiver implantado o diretor opcional).</span><span class="sxs-lookup"><span data-stu-id="17277-135">Your reverse proxy listener will have subject alternative names for your external Web Services URL(s) (for example, SAN=lyncwebextpool01.contoso.com, and dirwebexternal.contoso.com if you have deployed the optional Director).</span></span>



</div>

</div>

<span> </span>

</div>

</div>

</div>

