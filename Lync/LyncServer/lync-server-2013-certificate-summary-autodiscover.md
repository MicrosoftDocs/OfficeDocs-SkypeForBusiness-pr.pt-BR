---
title: 'Lync Server 2013: Resumo do certificado-descoberta automática'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Certificate summary - Autodiscover
ms:assetid: 16ac96bb-882a-4141-b75c-9530637548d9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945616(v=OCS.15)
ms:contentKeyID: 51541451
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8956c8a0ed4e149f336e6670aaf5b262f1868748
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41736661"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="certificate-summary---autodiscover-in-lync-server-2013"></a><span data-ttu-id="b03ac-102">Resumo do certificado-descoberta automática no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b03ac-102">Certificate summary - Autodiscover in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b03ac-103">_**Tópico da última modificação:** 2013-02-14_</span><span class="sxs-lookup"><span data-stu-id="b03ac-103">_**Topic Last Modified:** 2013-02-14_</span></span>

<span data-ttu-id="b03ac-104">O serviço de descoberta automática do Lync Server 2013 é executado nos servidores do diretor e do pool de front-end e, quando publicados no DNS, pode ser usado pelos clientes do Lync para localizar serviços de servidor e usuário.</span><span class="sxs-lookup"><span data-stu-id="b03ac-104">The Lync Server 2013 Autodiscover Service runs on the Director and Front End pool servers, and when published in DNS, can be used by Lync clients to locate server and user services.</span></span> <span data-ttu-id="b03ac-105">Se você estiver atualizando do Lync Server 2010 e não implantou a mobilidade, antes que os clientes possam usar a descoberta automática, você deve modificar listas de nomes alternativos de entidades de certificado em qualquer director e servidor front-end executando o serviço descoberta automática.</span><span class="sxs-lookup"><span data-stu-id="b03ac-105">If you are upgrading from Lync Server 2010 and did not deploy Mobility, before clients can use automatic discovery, you must modify certificate subject alternative name lists on any Director and Front End Server running the Autodiscover Service.</span></span> <span data-ttu-id="b03ac-106">Além disso, pode ser necessário modificar as listas de nomes alternativos de entidades nos certificados usados para regras de publicação de serviço Web externo em proxies reverso.</span><span class="sxs-lookup"><span data-stu-id="b03ac-106">In addition, it may be necessary to modify the subject alternative name lists on certificates used for external web service publishing rules on reverse proxies.</span></span>

<span data-ttu-id="b03ac-107">A decisão sobre se deve usar listas de nomes alternativos de entidades em proxies invertidos se baseia se você publica o serviço de descoberta automática na porta 80 ou na porta 443:</span><span class="sxs-lookup"><span data-stu-id="b03ac-107">The decision about whether to use subject alternative name lists on reverse proxies is based on whether you publish the Autodiscover Service on port 80 or on port 443:</span></span>

  - <span data-ttu-id="b03ac-108">**Publicado na porta 80**   nenhuma alteração de certificado será necessária se a consulta inicial para o serviço descoberta automática ocorrer na porta 80.</span><span class="sxs-lookup"><span data-stu-id="b03ac-108">**Published on port 80**   No certificate changes are required if the initial query to the Autodiscover Service occurs over port 80.</span></span> <span data-ttu-id="b03ac-109">Isso ocorre porque os dispositivos móveis que executam o Lync acessam o proxy reverso na porta 80 externamente e, em seguida, ligados a um diretor ou servidor front-end na porta 8080 internamente.</span><span class="sxs-lookup"><span data-stu-id="b03ac-109">This is because mobile devices running Lync will access the reverse proxy on port 80 externally and then be bridged to a Director or Front End Server on port 8080 internally.</span></span> <span data-ttu-id="b03ac-110">Para obter detalhes, consulte a seção requisitos técnicos da seção "processo de descoberta automática inicial usando a porta 80" [para mobilidade no Lync Server 2013](lync-server-2013-technical-requirements-for-mobility.md).</span><span class="sxs-lookup"><span data-stu-id="b03ac-110">For details, see the "Initial Autodiscover Process Using Port 80" section [Technical requirements for mobility in Lync Server 2013](lync-server-2013-technical-requirements-for-mobility.md).</span></span>

  - <span data-ttu-id="b03ac-111">**Publicado na porta 443**   a lista de nomes alternativos de entidades nos certificados usados pela regra de publicação de serviços Web externos deve conter um *lyncdiscover.\< entrada\> sipdomain* para cada domínio SIP em sua organização.</span><span class="sxs-lookup"><span data-stu-id="b03ac-111">**Published on port 443**   The subject alternative name list on certificates used by the external web services publishing rule must contain a *lyncdiscover.\<sipdomain\>* entry for each SIP domain within your organization.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="b03ac-112">É altamente recomendável usar HTTPS sobre HTTP.</span><span class="sxs-lookup"><span data-stu-id="b03ac-112">We highly recommend using HTTPS over HTTP.</span></span> <span data-ttu-id="b03ac-113">HTTPS usa certificados para criptografar o tráfego.</span><span class="sxs-lookup"><span data-stu-id="b03ac-113">HTTPS uses certificates to encrypt traffic.</span></span> <span data-ttu-id="b03ac-114">O HTTP não fornece criptografia, e todos os dados enviados serão texto sem formatação.</span><span class="sxs-lookup"><span data-stu-id="b03ac-114">HTTP does not provide for encryption, and any data sent will be plain text.</span></span>

    
    </div>

<span data-ttu-id="b03ac-115">A emissão de certificados por meio de uma autoridade de certificação interna geralmente é um processo simples.</span><span class="sxs-lookup"><span data-stu-id="b03ac-115">Reissuing certificates by using an internal certificate authority is typically a simple process.</span></span> <span data-ttu-id="b03ac-116">Mas para certificados públicos usados na regra de publicação do serviço Web, adicionar várias entradas de nomes alternativos de entidades pode ficar caro.</span><span class="sxs-lookup"><span data-stu-id="b03ac-116">But for public certificates used on the web service publishing rule, adding multiple subject alternative name entries can become expensive.</span></span> <span data-ttu-id="b03ac-117">Para contornar esse problema, oferecemos suporte para a conexão de descoberta automática inicial na porta 80, que é redirecionada para a porta 8080 do diretor ou servidor front-end.</span><span class="sxs-lookup"><span data-stu-id="b03ac-117">To work around this issue, we support the initial automatic discovery connection over port 80, which is then redirected to port 8080 on the Director or Front End Server.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="b03ac-118">Se a sua infraestrutura do Lync Server 2013 usa certificados internos que são emitidos de uma CA (autoridade de certificação) interna e você planeja dar suporte a dispositivos móveis que se conectam sem fio, a cadeia de certificados raiz da autoridade de certificação interna deve ser instalada nos dispositivos móveis ou você deve mudar para um certificado público na sua infraestrutura do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="b03ac-118">If your Lync Server 2013 infrastructure uses internal certificates that are issued from an internal certification authority (CA) and you plan to support mobile devices connecting wirelessly, either the root certificate chain from the internal CA must be installed on the mobile devices or you must change to a public certificate on your Lync Server 2013 infrastructure.</span></span>



</div>

<span data-ttu-id="b03ac-119">Este tópico descreve os nomes alternativos de entidades adicionados necessários para o diretor, servidor front-end e proxy reverso.</span><span class="sxs-lookup"><span data-stu-id="b03ac-119">This topic describes the added subject alternative names required for the Director, Front End Server and reverse proxy.</span></span> <span data-ttu-id="b03ac-120">Somente os nomes alternativos de entidades (SAN) adicionados são referenciados.</span><span class="sxs-lookup"><span data-stu-id="b03ac-120">Only the added subject alternative names (SAN) are referenced.</span></span> <span data-ttu-id="b03ac-121">Consulte as seções de planejamento para obter diretrizes sobre as outras entradas em certificados.</span><span class="sxs-lookup"><span data-stu-id="b03ac-121">Refer to the planning sections for guidance on the other entries on certificates.</span></span> <span data-ttu-id="b03ac-122">Para obter detalhes, consulte [cenários do diretor do Lync server 2013](lync-server-2013-scenarios-for-the-director.md), [cenários para acesso de usuários externos no Lync Server 2013](lync-server-2013-scenarios-for-external-user-access.md)e [cenários para o proxy inverso no Lync Server 2013](lync-server-2013-scenarios-for-reverse-proxy.md).</span><span class="sxs-lookup"><span data-stu-id="b03ac-122">For details, see [Scenarios for the Director in Lync Server 2013](lync-server-2013-scenarios-for-the-director.md), [Scenarios for external user access in Lync Server 2013](lync-server-2013-scenarios-for-external-user-access.md), and [Scenarios for reverse proxy in Lync Server 2013](lync-server-2013-scenarios-for-reverse-proxy.md).</span></span>

<span data-ttu-id="b03ac-123">As tabelas a seguir definem as entradas de SAN de descoberta automática para o pool de diretor, o pool de front-ends e o proxy reverso:</span><span class="sxs-lookup"><span data-stu-id="b03ac-123">The following tables define the Autodiscover SAN entries for the Director pool, the Front End pool, and the reverse proxy:</span></span>

### <a name="director-pool-certificate-requirements"></a><span data-ttu-id="b03ac-124">Requisitos de certificado do pool do director</span><span class="sxs-lookup"><span data-stu-id="b03ac-124">Director Pool Certificate Requirements</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="b03ac-125">Descrição</span><span class="sxs-lookup"><span data-stu-id="b03ac-125">Description</span></span></th>
<th><span data-ttu-id="b03ac-126">Entrada de nome alternativo do assunto</span><span class="sxs-lookup"><span data-stu-id="b03ac-126">Subject alternative name entry</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b03ac-127">URL interna do serviço de descoberta automática</span><span class="sxs-lookup"><span data-stu-id="b03ac-127">Internal Autodiscover Service URL</span></span></p></td>
<td><p><span data-ttu-id="b03ac-128">SAN = lyncdiscoverinternal. &lt;nome de domínio interno&gt;</span><span class="sxs-lookup"><span data-stu-id="b03ac-128">SAN=lyncdiscoverinternal.&lt;internal domain name&gt;</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b03ac-129">URL do serviço de descoberta automática externo</span><span class="sxs-lookup"><span data-stu-id="b03ac-129">External Autodiscover Service URL</span></span></p></td>
<td><p><span data-ttu-id="b03ac-130">SAN = lyncdiscover. &lt;sipdomain&gt;</span><span class="sxs-lookup"><span data-stu-id="b03ac-130">SAN=lyncdiscover.&lt;sipdomain&gt;</span></span></p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <span data-ttu-id="b03ac-131">Você atribui o certificado recém atualizado com a nova entrada de SAN ao certificado padrão.</span><span class="sxs-lookup"><span data-stu-id="b03ac-131">You assign the newly updated certificate with the new SAN entry to the Default certificate.</span></span> <span data-ttu-id="b03ac-132">Você também pode usar SAN = \*. &lt;sipdomain&gt;.</span><span class="sxs-lookup"><span data-stu-id="b03ac-132">Alternatively, you can use SAN=\*.&lt;sipdomain&gt;.</span></span>



</div>

### <a name="front-end-pool-certificate-requirements"></a><span data-ttu-id="b03ac-133">Requisitos de certificado de pool de front-end</span><span class="sxs-lookup"><span data-stu-id="b03ac-133">Front End Pool Certificate Requirements</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="b03ac-134">Descrição</span><span class="sxs-lookup"><span data-stu-id="b03ac-134">Description</span></span></th>
<th><span data-ttu-id="b03ac-135">Entrada de nome alternativo do assunto</span><span class="sxs-lookup"><span data-stu-id="b03ac-135">Subject alternative name entry</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b03ac-136">URL interna do serviço de descoberta automática</span><span class="sxs-lookup"><span data-stu-id="b03ac-136">Internal Autodiscover Service URL</span></span></p></td>
<td><p><span data-ttu-id="b03ac-137">SAN = lyncdiscoverinternal. &lt;nome de domínio interno&gt;</span><span class="sxs-lookup"><span data-stu-id="b03ac-137">SAN=lyncdiscoverinternal.&lt;internal domain name&gt;</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b03ac-138">URL do serviço de descoberta automática externo</span><span class="sxs-lookup"><span data-stu-id="b03ac-138">External Autodiscover Service URL</span></span></p></td>
<td><p><span data-ttu-id="b03ac-139">SAN = lyncdiscover. &lt;sipdomain&gt;</span><span class="sxs-lookup"><span data-stu-id="b03ac-139">SAN=lyncdiscover.&lt;sipdomain&gt;</span></span></p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <span data-ttu-id="b03ac-140">Você atribui o certificado recém atualizado com a nova entrada de SAN ao certificado padrão.</span><span class="sxs-lookup"><span data-stu-id="b03ac-140">You assign the newly updated certificate with the new SAN entry to the Default certificate.</span></span> <span data-ttu-id="b03ac-141">Você também pode usar SAN = \*. &lt;sipdomain&gt;</span><span class="sxs-lookup"><span data-stu-id="b03ac-141">Alternatively, you can use SAN=\*.&lt;sipdomain&gt;</span></span>



</div>

### <a name="reverse-proxy-public-ca-certificate-requirements"></a><span data-ttu-id="b03ac-142">Requisitos de certificado de proxy reverso (CA pública)</span><span class="sxs-lookup"><span data-stu-id="b03ac-142">Reverse Proxy (Public CA) Certificate Requirements</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="b03ac-143">Descrição</span><span class="sxs-lookup"><span data-stu-id="b03ac-143">Description</span></span></th>
<th><span data-ttu-id="b03ac-144">Entrada de nome alternativo do assunto</span><span class="sxs-lookup"><span data-stu-id="b03ac-144">Subject alternative name entry</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b03ac-145">URL do serviço de descoberta automática externo</span><span class="sxs-lookup"><span data-stu-id="b03ac-145">External Autodiscover Service URL</span></span></p></td>
<td><p><span data-ttu-id="b03ac-146">SAN = lyncdiscover. &lt;sipdomain&gt;</span><span class="sxs-lookup"><span data-stu-id="b03ac-146">SAN=lyncdiscover.&lt;sipdomain&gt;</span></span></p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <span data-ttu-id="b03ac-147">Você atribui o certificado recém atualizado à nova entrada de SAN ao ouvinte SSL no proxy reverso.</span><span class="sxs-lookup"><span data-stu-id="b03ac-147">You assign the newly updated certificate with the new SAN entry to the SSL Listener on the reverse proxy.</span></span>



</div>

</div>

<span> </span>

</div>

</div>

</div>

