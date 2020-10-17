---
title: 'Lync Server 2013: Resumo de certificado-descoberta automática'
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
ms.openlocfilehash: 196b3dacec792097a4760ef134ead91f267a53d1
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48499308"
---
# <a name="certificate-summary---autodiscover-in-lync-server-2013"></a><span data-ttu-id="5edfb-102">Resumo de certificado-descoberta automática no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5edfb-102">Certificate summary - Autodiscover in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5edfb-103">_**Última modificação do tópico:** 2013-02-14_</span><span class="sxs-lookup"><span data-stu-id="5edfb-103">_**Topic Last Modified:** 2013-02-14_</span></span>

<span data-ttu-id="5edfb-104">O serviço de descoberta automática do Lync Server 2013 é executado nos servidores do diretor e do pool de front-ends e, quando publicado no DNS, pode ser usado por clientes do Lync para localizar serviços de servidor e usuário.</span><span class="sxs-lookup"><span data-stu-id="5edfb-104">The Lync Server 2013 Autodiscover Service runs on the Director and Front End pool servers, and when published in DNS, can be used by Lync clients to locate server and user services.</span></span> <span data-ttu-id="5edfb-105">Se você estiver atualizando do Lync Server 2010 e não tiver implantado a mobilidade, antes que os clientes possam usar a descoberta automática, você deve modificar listas de nomes alternativos de entidades de certificado em qualquer diretor e servidor front-end executando o serviço de descoberta automática.</span><span class="sxs-lookup"><span data-stu-id="5edfb-105">If you are upgrading from Lync Server 2010 and did not deploy Mobility, before clients can use automatic discovery, you must modify certificate subject alternative name lists on any Director and Front End Server running the Autodiscover Service.</span></span> <span data-ttu-id="5edfb-106">Além disso, pode ser necessário modificar as listas de nomes alternativos de entidade nos certificados usados pelas regras de publicação de serviços de Web externa em proxies reversos.</span><span class="sxs-lookup"><span data-stu-id="5edfb-106">In addition, it may be necessary to modify the subject alternative name lists on certificates used for external web service publishing rules on reverse proxies.</span></span>

<span data-ttu-id="5edfb-107">A decisão sobre a utilização de listas de nomes alternativos de entidades em proxies reversos baseia-se no fato de você publicar o serviço de descoberta automática na porta 80 ou na porta 443:</span><span class="sxs-lookup"><span data-stu-id="5edfb-107">The decision about whether to use subject alternative name lists on reverse proxies is based on whether you publish the Autodiscover Service on port 80 or on port 443:</span></span>

  - <span data-ttu-id="5edfb-108">**Publicado na porta 80**     Nenhuma alteração de certificado será necessária se a consulta inicial para o serviço de descoberta automática ocorrer na porta 80.</span><span class="sxs-lookup"><span data-stu-id="5edfb-108">**Published on port 80**   No certificate changes are required if the initial query to the Autodiscover Service occurs over port 80.</span></span> <span data-ttu-id="5edfb-109">Isso ocorre porque os dispositivos móveis que executam o Lync acessarão o proxy reverso na porta 80 externamente e, em seguida, serão ligados ao diretor ou servidor front-end na porta 8080 internamente.</span><span class="sxs-lookup"><span data-stu-id="5edfb-109">This is because mobile devices running Lync will access the reverse proxy on port 80 externally and then be bridged to a Director or Front End Server on port 8080 internally.</span></span> <span data-ttu-id="5edfb-110">Para obter detalhes, consulte a seção sobre requisitos técnicos de "processo de descoberta automática inicial usando a porta 80" [para mobilidade no Lync Server 2013](lync-server-2013-technical-requirements-for-mobility.md).</span><span class="sxs-lookup"><span data-stu-id="5edfb-110">For details, see the "Initial Autodiscover Process Using Port 80" section [Technical requirements for mobility in Lync Server 2013](lync-server-2013-technical-requirements-for-mobility.md).</span></span>

  - <span data-ttu-id="5edfb-111">**Publicado na porta 443**     A lista de nomes alternativos da entidade em certificados usados pela regra de publicação dos serviços Web externos deve conter um \*lyncdiscover. \<sipdomain\> \*</span><span class="sxs-lookup"><span data-stu-id="5edfb-111">**Published on port 443**   The subject alternative name list on certificates used by the external web services publishing rule must contain a *lyncdiscover.\<sipdomain\>*</span></span> <span data-ttu-id="5edfb-112">entrada para cada domínio SIP em sua organização.</span><span class="sxs-lookup"><span data-stu-id="5edfb-112">entry for each SIP domain within your organization.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="5edfb-113">É altamente recomendável usar HTTPS sobre HTTP.</span><span class="sxs-lookup"><span data-stu-id="5edfb-113">We highly recommend using HTTPS over HTTP.</span></span> <span data-ttu-id="5edfb-114">HTTPS usa certificados para criptografar o tráfego.</span><span class="sxs-lookup"><span data-stu-id="5edfb-114">HTTPS uses certificates to encrypt traffic.</span></span> <span data-ttu-id="5edfb-115">HTTP não fornece criptografia e todos os dados enviados serão texto sem formatação.</span><span class="sxs-lookup"><span data-stu-id="5edfb-115">HTTP does not provide for encryption, and any data sent will be plain text.</span></span>

    
    </div>

<span data-ttu-id="5edfb-116">A reemissão de certificados usando uma autoridade de certificação interna geralmente é um processo simples.</span><span class="sxs-lookup"><span data-stu-id="5edfb-116">Reissuing certificates by using an internal certificate authority is typically a simple process.</span></span> <span data-ttu-id="5edfb-117">Mas para certificados públicos usados na regra de publicação do serviço Web, adicionar várias entradas de nome alternativo de entidade pode se tornar caro.</span><span class="sxs-lookup"><span data-stu-id="5edfb-117">But for public certificates used on the web service publishing rule, adding multiple subject alternative name entries can become expensive.</span></span> <span data-ttu-id="5edfb-118">Para contornar esse problema, oferecemos suporte à conexão de descoberta automática inicial na porta 80, que é então redirecionada para a porta 8080 no diretor ou servidor front-end.</span><span class="sxs-lookup"><span data-stu-id="5edfb-118">To work around this issue, we support the initial automatic discovery connection over port 80, which is then redirected to port 8080 on the Director or Front End Server.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="5edfb-119">Se sua infraestrutura do Lync Server 2013 usa certificados internos emitidos por uma autoridade de certificação interna (CA) e você planeja suportar dispositivos móveis que se conectam sem fio, a cadeia de certificados raiz da autoridade de certificação interna deve ser instalada nos dispositivos móveis ou você deve alterar para um certificado público em sua infraestrutura do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="5edfb-119">If your Lync Server 2013 infrastructure uses internal certificates that are issued from an internal certification authority (CA) and you plan to support mobile devices connecting wirelessly, either the root certificate chain from the internal CA must be installed on the mobile devices or you must change to a public certificate on your Lync Server 2013 infrastructure.</span></span>



</div>

<span data-ttu-id="5edfb-120">Este tópico descreve os nomes alternativos de entidade adicionados necessários para o diretor, servidor front-end e proxy reverso.</span><span class="sxs-lookup"><span data-stu-id="5edfb-120">This topic describes the added subject alternative names required for the Director, Front End Server and reverse proxy.</span></span> <span data-ttu-id="5edfb-121">Somente os nomes alternativos da entidade (SAN) adicionados são referenciados.</span><span class="sxs-lookup"><span data-stu-id="5edfb-121">Only the added subject alternative names (SAN) are referenced.</span></span> <span data-ttu-id="5edfb-122">Consulte as seções de planejamento para obter orientação sobre as outras entradas de certificados.</span><span class="sxs-lookup"><span data-stu-id="5edfb-122">Refer to the planning sections for guidance on the other entries on certificates.</span></span> <span data-ttu-id="5edfb-123">Para obter detalhes, consulte [cenários para o diretor no Lync server 2013](lync-server-2013-scenarios-for-the-director.md), [cenários para acesso de usuário externo no Lync Server 2013](lync-server-2013-scenarios-for-external-user-access.md)e [cenários de proxy reverso no Lync Server 2013](lync-server-2013-scenarios-for-reverse-proxy.md).</span><span class="sxs-lookup"><span data-stu-id="5edfb-123">For details, see [Scenarios for the Director in Lync Server 2013](lync-server-2013-scenarios-for-the-director.md), [Scenarios for external user access in Lync Server 2013](lync-server-2013-scenarios-for-external-user-access.md), and [Scenarios for reverse proxy in Lync Server 2013](lync-server-2013-scenarios-for-reverse-proxy.md).</span></span>

<span data-ttu-id="5edfb-124">As tabelas a seguir definem as entradas de SAN de descoberta automática para o pool de diretores, o pool de front-ends e o proxy reverso:</span><span class="sxs-lookup"><span data-stu-id="5edfb-124">The following tables define the Autodiscover SAN entries for the Director pool, the Front End pool, and the reverse proxy:</span></span>

### <a name="director-pool-certificate-requirements"></a><span data-ttu-id="5edfb-125">Requisitos de certificado do Pool de Diretores</span><span class="sxs-lookup"><span data-stu-id="5edfb-125">Director Pool Certificate Requirements</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="5edfb-126">Descrição</span><span class="sxs-lookup"><span data-stu-id="5edfb-126">Description</span></span></th>
<th><span data-ttu-id="5edfb-127">Entrada de nome de entidade alternativo</span><span class="sxs-lookup"><span data-stu-id="5edfb-127">Subject alternative name entry</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="5edfb-128">URL interna do serviço de Descoberta Automática</span><span class="sxs-lookup"><span data-stu-id="5edfb-128">Internal Autodiscover Service URL</span></span></p></td>
<td><p><span data-ttu-id="5edfb-129">SAN = lyncdiscoverinternal. &lt; nome de domínio interno&gt;</span><span class="sxs-lookup"><span data-stu-id="5edfb-129">SAN=lyncdiscoverinternal.&lt;internal domain name&gt;</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5edfb-130">URL externa do serviço de Descoberta Automática</span><span class="sxs-lookup"><span data-stu-id="5edfb-130">External Autodiscover Service URL</span></span></p></td>
<td><p><span data-ttu-id="5edfb-131">SAN = lyncdiscover. &lt; sipdomain&gt;</span><span class="sxs-lookup"><span data-stu-id="5edfb-131">SAN=lyncdiscover.&lt;sipdomain&gt;</span></span></p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <span data-ttu-id="5edfb-132">Você atribui o certificado recentemente atualizado à nova entrada de SAN ao certificado padrão.</span><span class="sxs-lookup"><span data-stu-id="5edfb-132">You assign the newly updated certificate with the new SAN entry to the Default certificate.</span></span> <span data-ttu-id="5edfb-133">Como alternativa, você pode usar SAN = \*. &lt; sipdomain &gt; .</span><span class="sxs-lookup"><span data-stu-id="5edfb-133">Alternatively, you can use SAN=\*.&lt;sipdomain&gt;.</span></span>



</div>

### <a name="front-end-pool-certificate-requirements"></a><span data-ttu-id="5edfb-134">Requisitos de certificado do pool Front-End</span><span class="sxs-lookup"><span data-stu-id="5edfb-134">Front End Pool Certificate Requirements</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="5edfb-135">Descrição</span><span class="sxs-lookup"><span data-stu-id="5edfb-135">Description</span></span></th>
<th><span data-ttu-id="5edfb-136">Entrada de nome de entidade alternativo</span><span class="sxs-lookup"><span data-stu-id="5edfb-136">Subject alternative name entry</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="5edfb-137">URL interna do serviço de Descoberta Automática</span><span class="sxs-lookup"><span data-stu-id="5edfb-137">Internal Autodiscover Service URL</span></span></p></td>
<td><p><span data-ttu-id="5edfb-138">SAN = lyncdiscoverinternal. &lt; nome de domínio interno&gt;</span><span class="sxs-lookup"><span data-stu-id="5edfb-138">SAN=lyncdiscoverinternal.&lt;internal domain name&gt;</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5edfb-139">URL externa do serviço de Descoberta Automática</span><span class="sxs-lookup"><span data-stu-id="5edfb-139">External Autodiscover Service URL</span></span></p></td>
<td><p><span data-ttu-id="5edfb-140">SAN = lyncdiscover. &lt; sipdomain&gt;</span><span class="sxs-lookup"><span data-stu-id="5edfb-140">SAN=lyncdiscover.&lt;sipdomain&gt;</span></span></p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <span data-ttu-id="5edfb-141">Você atribui o certificado recentemente atualizado à nova entrada de SAN ao certificado padrão.</span><span class="sxs-lookup"><span data-stu-id="5edfb-141">You assign the newly updated certificate with the new SAN entry to the Default certificate.</span></span> <span data-ttu-id="5edfb-142">Como alternativa, você pode usar SAN = \*. &lt; sipdomain&gt;</span><span class="sxs-lookup"><span data-stu-id="5edfb-142">Alternatively, you can use SAN=\*.&lt;sipdomain&gt;</span></span>



</div>

### <a name="reverse-proxy-public-ca-certificate-requirements"></a><span data-ttu-id="5edfb-143">Requisitos de certificado de proxy reverso (CA pública)</span><span class="sxs-lookup"><span data-stu-id="5edfb-143">Reverse Proxy (Public CA) Certificate Requirements</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="5edfb-144">Descrição</span><span class="sxs-lookup"><span data-stu-id="5edfb-144">Description</span></span></th>
<th><span data-ttu-id="5edfb-145">Entrada de nome de entidade alternativo</span><span class="sxs-lookup"><span data-stu-id="5edfb-145">Subject alternative name entry</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="5edfb-146">URL externa do serviço de Descoberta Automática</span><span class="sxs-lookup"><span data-stu-id="5edfb-146">External Autodiscover Service URL</span></span></p></td>
<td><p><span data-ttu-id="5edfb-147">SAN = lyncdiscover. &lt; sipdomain&gt;</span><span class="sxs-lookup"><span data-stu-id="5edfb-147">SAN=lyncdiscover.&lt;sipdomain&gt;</span></span></p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <span data-ttu-id="5edfb-148">Você atribui o certificado recentemente atualizado à nova entrada de SAN ao ouvinte SSL no proxy reverso.</span><span class="sxs-lookup"><span data-stu-id="5edfb-148">You assign the newly updated certificate with the new SAN entry to the SSL Listener on the reverse proxy.</span></span>



</div>

</div>

<span> </span>

</div>

</div>

</div>

