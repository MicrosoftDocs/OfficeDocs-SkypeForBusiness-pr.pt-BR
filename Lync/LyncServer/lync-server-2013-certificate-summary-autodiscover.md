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
ms.openlocfilehash: 7424d0c002e5b14335a6d0256fc72a3beff733cc
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42187474"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="certificate-summary---autodiscover-in-lync-server-2013"></a><span data-ttu-id="8d56a-102">Resumo de certificado-descoberta automática no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8d56a-102">Certificate summary - Autodiscover in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8d56a-103">_**Última modificação do tópico:** 2013-02-14_</span><span class="sxs-lookup"><span data-stu-id="8d56a-103">_**Topic Last Modified:** 2013-02-14_</span></span>

<span data-ttu-id="8d56a-104">O serviço de descoberta automática do Lync Server 2013 é executado nos servidores do diretor e do pool de front-ends e, quando publicado no DNS, pode ser usado por clientes do Lync para localizar serviços de servidor e usuário.</span><span class="sxs-lookup"><span data-stu-id="8d56a-104">The Lync Server 2013 Autodiscover Service runs on the Director and Front End pool servers, and when published in DNS, can be used by Lync clients to locate server and user services.</span></span> <span data-ttu-id="8d56a-105">Se você estiver atualizando do Lync Server 2010 e não tiver implantado a mobilidade, antes que os clientes possam usar a descoberta automática, você deve modificar listas de nomes alternativos de entidades de certificado em qualquer diretor e servidor front-end executando o serviço de descoberta automática.</span><span class="sxs-lookup"><span data-stu-id="8d56a-105">If you are upgrading from Lync Server 2010 and did not deploy Mobility, before clients can use automatic discovery, you must modify certificate subject alternative name lists on any Director and Front End Server running the Autodiscover Service.</span></span> <span data-ttu-id="8d56a-106">Além disso, pode ser necessário modificar as listas de nomes alternativos de entidade nos certificados usados pelas regras de publicação de serviços de Web externa em proxies reversos.</span><span class="sxs-lookup"><span data-stu-id="8d56a-106">In addition, it may be necessary to modify the subject alternative name lists on certificates used for external web service publishing rules on reverse proxies.</span></span>

<span data-ttu-id="8d56a-107">A decisão sobre a utilização de listas de nomes alternativos de entidades em proxies reversos baseia-se no fato de você publicar o serviço de descoberta automática na porta 80 ou na porta 443:</span><span class="sxs-lookup"><span data-stu-id="8d56a-107">The decision about whether to use subject alternative name lists on reverse proxies is based on whether you publish the Autodiscover Service on port 80 or on port 443:</span></span>

  - <span data-ttu-id="8d56a-108">**Publicado na porta 80**   nenhuma alteração de certificado será necessária se a consulta inicial para o serviço de descoberta automática ocorrer pela porta 80.</span><span class="sxs-lookup"><span data-stu-id="8d56a-108">**Published on port 80**   No certificate changes are required if the initial query to the Autodiscover Service occurs over port 80.</span></span> <span data-ttu-id="8d56a-109">Isso ocorre porque os dispositivos móveis que executam o Lync acessarão o proxy reverso na porta 80 externamente e, em seguida, serão ligados ao diretor ou servidor front-end na porta 8080 internamente.</span><span class="sxs-lookup"><span data-stu-id="8d56a-109">This is because mobile devices running Lync will access the reverse proxy on port 80 externally and then be bridged to a Director or Front End Server on port 8080 internally.</span></span> <span data-ttu-id="8d56a-110">Para obter detalhes, consulte a seção sobre requisitos técnicos de "processo de descoberta automática inicial usando a porta 80" [para mobilidade no Lync Server 2013](lync-server-2013-technical-requirements-for-mobility.md).</span><span class="sxs-lookup"><span data-stu-id="8d56a-110">For details, see the "Initial Autodiscover Process Using Port 80" section [Technical requirements for mobility in Lync Server 2013](lync-server-2013-technical-requirements-for-mobility.md).</span></span>

  - <span data-ttu-id="8d56a-111">**Publicado na porta 443**   a lista de nomes alternativos da entidade em certificados usados pela regra de publicação dos serviços Web externos deve conter um \*lyncdiscover.\< sipdomain\> \* entrada para cada domínio SIP em sua organização.</span><span class="sxs-lookup"><span data-stu-id="8d56a-111">**Published on port 443**   The subject alternative name list on certificates used by the external web services publishing rule must contain a *lyncdiscover.\<sipdomain\>* entry for each SIP domain within your organization.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="8d56a-112">É altamente recomendável usar HTTPS sobre HTTP.</span><span class="sxs-lookup"><span data-stu-id="8d56a-112">We highly recommend using HTTPS over HTTP.</span></span> <span data-ttu-id="8d56a-113">HTTPS usa certificados para criptografar o tráfego.</span><span class="sxs-lookup"><span data-stu-id="8d56a-113">HTTPS uses certificates to encrypt traffic.</span></span> <span data-ttu-id="8d56a-114">HTTP não fornece criptografia e todos os dados enviados serão texto sem formatação.</span><span class="sxs-lookup"><span data-stu-id="8d56a-114">HTTP does not provide for encryption, and any data sent will be plain text.</span></span>

    
    </div>

<span data-ttu-id="8d56a-115">A reemissão de certificados usando uma autoridade de certificação interna geralmente é um processo simples.</span><span class="sxs-lookup"><span data-stu-id="8d56a-115">Reissuing certificates by using an internal certificate authority is typically a simple process.</span></span> <span data-ttu-id="8d56a-116">Mas para certificados públicos usados na regra de publicação do serviço Web, adicionar várias entradas de nome alternativo de entidade pode se tornar caro.</span><span class="sxs-lookup"><span data-stu-id="8d56a-116">But for public certificates used on the web service publishing rule, adding multiple subject alternative name entries can become expensive.</span></span> <span data-ttu-id="8d56a-117">Para contornar esse problema, oferecemos suporte à conexão de descoberta automática inicial na porta 80, que é então redirecionada para a porta 8080 no diretor ou servidor front-end.</span><span class="sxs-lookup"><span data-stu-id="8d56a-117">To work around this issue, we support the initial automatic discovery connection over port 80, which is then redirected to port 8080 on the Director or Front End Server.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="8d56a-118">Se sua infraestrutura do Lync Server 2013 usa certificados internos emitidos por uma autoridade de certificação interna (CA) e você planeja suportar dispositivos móveis que se conectam sem fio, a cadeia de certificados raiz da autoridade de certificação interna deve ser instalada nos dispositivos móveis ou você deve alterar para um certificado público em sua infraestrutura do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="8d56a-118">If your Lync Server 2013 infrastructure uses internal certificates that are issued from an internal certification authority (CA) and you plan to support mobile devices connecting wirelessly, either the root certificate chain from the internal CA must be installed on the mobile devices or you must change to a public certificate on your Lync Server 2013 infrastructure.</span></span>



</div>

<span data-ttu-id="8d56a-119">Este tópico descreve os nomes alternativos de entidade adicionados necessários para o diretor, servidor front-end e proxy reverso.</span><span class="sxs-lookup"><span data-stu-id="8d56a-119">This topic describes the added subject alternative names required for the Director, Front End Server and reverse proxy.</span></span> <span data-ttu-id="8d56a-120">Somente os nomes alternativos da entidade (SAN) adicionados são referenciados.</span><span class="sxs-lookup"><span data-stu-id="8d56a-120">Only the added subject alternative names (SAN) are referenced.</span></span> <span data-ttu-id="8d56a-121">Consulte as seções de planejamento para obter orientação sobre as outras entradas de certificados.</span><span class="sxs-lookup"><span data-stu-id="8d56a-121">Refer to the planning sections for guidance on the other entries on certificates.</span></span> <span data-ttu-id="8d56a-122">Para obter detalhes, consulte [cenários para o diretor no Lync server 2013](lync-server-2013-scenarios-for-the-director.md), [cenários para acesso de usuário externo no Lync Server 2013](lync-server-2013-scenarios-for-external-user-access.md)e [cenários de proxy reverso no Lync Server 2013](lync-server-2013-scenarios-for-reverse-proxy.md).</span><span class="sxs-lookup"><span data-stu-id="8d56a-122">For details, see [Scenarios for the Director in Lync Server 2013](lync-server-2013-scenarios-for-the-director.md), [Scenarios for external user access in Lync Server 2013](lync-server-2013-scenarios-for-external-user-access.md), and [Scenarios for reverse proxy in Lync Server 2013](lync-server-2013-scenarios-for-reverse-proxy.md).</span></span>

<span data-ttu-id="8d56a-123">As tabelas a seguir definem as entradas de SAN de descoberta automática para o pool de diretores, o pool de front-ends e o proxy reverso:</span><span class="sxs-lookup"><span data-stu-id="8d56a-123">The following tables define the Autodiscover SAN entries for the Director pool, the Front End pool, and the reverse proxy:</span></span>

### <a name="director-pool-certificate-requirements"></a><span data-ttu-id="8d56a-124">Requisitos de certificado do Pool de Diretores</span><span class="sxs-lookup"><span data-stu-id="8d56a-124">Director Pool Certificate Requirements</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="8d56a-125">Descrição</span><span class="sxs-lookup"><span data-stu-id="8d56a-125">Description</span></span></th>
<th><span data-ttu-id="8d56a-126">Entrada de nome de entidade alternativo</span><span class="sxs-lookup"><span data-stu-id="8d56a-126">Subject alternative name entry</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="8d56a-127">URL interna do serviço de Descoberta Automática</span><span class="sxs-lookup"><span data-stu-id="8d56a-127">Internal Autodiscover Service URL</span></span></p></td>
<td><p><span data-ttu-id="8d56a-128">SAN = lyncdiscoverinternal. &lt;nome de domínio interno&gt;</span><span class="sxs-lookup"><span data-stu-id="8d56a-128">SAN=lyncdiscoverinternal.&lt;internal domain name&gt;</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8d56a-129">URL externa do serviço de Descoberta Automática</span><span class="sxs-lookup"><span data-stu-id="8d56a-129">External Autodiscover Service URL</span></span></p></td>
<td><p><span data-ttu-id="8d56a-130">SAN = lyncdiscover. &lt;sipdomain&gt;</span><span class="sxs-lookup"><span data-stu-id="8d56a-130">SAN=lyncdiscover.&lt;sipdomain&gt;</span></span></p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <span data-ttu-id="8d56a-131">Você atribui o certificado recentemente atualizado à nova entrada de SAN ao certificado padrão.</span><span class="sxs-lookup"><span data-stu-id="8d56a-131">You assign the newly updated certificate with the new SAN entry to the Default certificate.</span></span> <span data-ttu-id="8d56a-132">Como alternativa, você pode usar SAN = \*. &lt;sipdomain&gt;.</span><span class="sxs-lookup"><span data-stu-id="8d56a-132">Alternatively, you can use SAN=\*.&lt;sipdomain&gt;.</span></span>



</div>

### <a name="front-end-pool-certificate-requirements"></a><span data-ttu-id="8d56a-133">Requisitos de certificado do pool Front-End</span><span class="sxs-lookup"><span data-stu-id="8d56a-133">Front End Pool Certificate Requirements</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="8d56a-134">Descrição</span><span class="sxs-lookup"><span data-stu-id="8d56a-134">Description</span></span></th>
<th><span data-ttu-id="8d56a-135">Entrada de nome de entidade alternativo</span><span class="sxs-lookup"><span data-stu-id="8d56a-135">Subject alternative name entry</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="8d56a-136">URL interna do serviço de Descoberta Automática</span><span class="sxs-lookup"><span data-stu-id="8d56a-136">Internal Autodiscover Service URL</span></span></p></td>
<td><p><span data-ttu-id="8d56a-137">SAN = lyncdiscoverinternal. &lt;nome de domínio interno&gt;</span><span class="sxs-lookup"><span data-stu-id="8d56a-137">SAN=lyncdiscoverinternal.&lt;internal domain name&gt;</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8d56a-138">URL externa do serviço de Descoberta Automática</span><span class="sxs-lookup"><span data-stu-id="8d56a-138">External Autodiscover Service URL</span></span></p></td>
<td><p><span data-ttu-id="8d56a-139">SAN = lyncdiscover. &lt;sipdomain&gt;</span><span class="sxs-lookup"><span data-stu-id="8d56a-139">SAN=lyncdiscover.&lt;sipdomain&gt;</span></span></p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <span data-ttu-id="8d56a-140">Você atribui o certificado recentemente atualizado à nova entrada de SAN ao certificado padrão.</span><span class="sxs-lookup"><span data-stu-id="8d56a-140">You assign the newly updated certificate with the new SAN entry to the Default certificate.</span></span> <span data-ttu-id="8d56a-141">Como alternativa, você pode usar SAN = \*. &lt;sipdomain&gt;</span><span class="sxs-lookup"><span data-stu-id="8d56a-141">Alternatively, you can use SAN=\*.&lt;sipdomain&gt;</span></span>



</div>

### <a name="reverse-proxy-public-ca-certificate-requirements"></a><span data-ttu-id="8d56a-142">Requisitos de certificado de proxy reverso (CA pública)</span><span class="sxs-lookup"><span data-stu-id="8d56a-142">Reverse Proxy (Public CA) Certificate Requirements</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="8d56a-143">Descrição</span><span class="sxs-lookup"><span data-stu-id="8d56a-143">Description</span></span></th>
<th><span data-ttu-id="8d56a-144">Entrada de nome de entidade alternativo</span><span class="sxs-lookup"><span data-stu-id="8d56a-144">Subject alternative name entry</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="8d56a-145">URL externa do serviço de Descoberta Automática</span><span class="sxs-lookup"><span data-stu-id="8d56a-145">External Autodiscover Service URL</span></span></p></td>
<td><p><span data-ttu-id="8d56a-146">SAN = lyncdiscover. &lt;sipdomain&gt;</span><span class="sxs-lookup"><span data-stu-id="8d56a-146">SAN=lyncdiscover.&lt;sipdomain&gt;</span></span></p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <span data-ttu-id="8d56a-147">Você atribui o certificado recentemente atualizado à nova entrada de SAN ao ouvinte SSL no proxy reverso.</span><span class="sxs-lookup"><span data-stu-id="8d56a-147">You assign the newly updated certificate with the new SAN entry to the SSL Listener on the reverse proxy.</span></span>



</div>

</div>

<span> </span>

</div>

</div>

</div>

