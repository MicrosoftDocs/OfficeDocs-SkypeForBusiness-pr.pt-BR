---
title: 'Lync Server 2013: planejando para descoberta automática'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Planning for Autodiscover
ms:assetid: 51f1ff94-1d64-4e6d-a878-b86fa07edc2d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945628(v=OCS.15)
ms:contentKeyID: 51541474
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0a1d0ce7a775bc73c5f3afa10d1f9c148395b0eb
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34825118"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="planning-for-autodiscover-in-lync-server-2013"></a>Planejando a descoberta automática no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2013-02-16_

A descoberta automática foi introduzida para o Lync Server na atualização cumulativa do Lync Server 2010:2011 de novembro. A principal finalidade dessa implementação inicial da descoberta automática era fornecer um meio para o Lync Mobile localizar o serviço de mobilidade (MCX). O serviço de descoberta automática no Lync Server 2013 agora é um serviço usado por todos os clientes para localizar serviços de servidor e usuário. O serviço de descoberta automática do Microsoft Lync Server 2013 é executado em directors e servidores front-end.

<div>


> [!TIP]  
> Para obter uma compreensão técnica do autodiscover e do que é comunicado a clientes, consulte <A href="lync-server-2013-understanding-autodiscover.md">compreendendo a descoberta automática no Lync Server 2013</A>.<BR>A mobilidade ainda é um cenário distinto, e os serviços de mobilidade ainda exigem um planejamento especial. Para obter mais detalhes, consulte <A href="lync-server-2013-planning-for-mobility.md">planejamento de mobilidade no Lync Server 2013</A>.



</div>

Quando a descoberta automática foi introduzida no Lync Server 2010, havia comprometimentos que precisavam ser feito para implementar um serviço que exigisse alterações de certificado em potencial em implantações de servidor existentes. A descoberta automática pode ser usada na porta TCP 443 para HTTPS ou na porta TCP 80 para HTTP. Se a decisão foi feita para usar HTTPS, os certificados em proxies reverso, directors e servidores front-end precisarão ser reemitidos a fim de `lyncdiscover.<domain>` acomodar `lyncdiscoverinternal.<domain>` os registros obrigatórios e DNS. Se a decisão era usar HTTP, a reemissão de certificados pode ser evitada usando registros CNAME (ou alias) DNS para usar os nomes existentes nos certificados. Usar HTTP significa que as comunicações iniciais não foram criptografadas.

Como o Lync Server 2013 usa a descoberta automática para todos os clientes, o cenário principal é usar HTTPS exclusivamente e criar certificados com o lyncdiscover. \<domínio\> como parte da configuração de proxies reverso, diretores e servidores front-end. Se você estiver implementando a descoberta automática em uma implantação atualizada do Lync Server 2010, talvez queira usar HTTP para evitar a reemissão de certificados. As diretrizes para ambos os cenários são fornecidas nas seções a seguir.

<div>


> [!IMPORTANT]  
> A lista de nomes alternativos de entidades nos certificados usados pela regra de publicação de serviços Web externos deve conter um <EM>lyncdiscover.&lt; entrada&gt; sipdomain</EM> para cada domínio SIP em sua organização. Para obter detalhes sobre as entradas de nome alternativo do assunto que são necessárias para os directors, servidores front-end e proxies reverso, consulte <A href="lync-server-2013-certificate-summary-autodiscover.md">Resumo de certificados-descoberta automática no Lync Server 2013</A>.



</div>

<div>

## <a name="in-this-section"></a>Nesta seção

  - [Resumo do certificado-descoberta automática no Lync Server 2013](lync-server-2013-certificate-summary-autodiscover.md)

  - [Resumo da porta-descoberta automática no Lync Server 2013](lync-server-2013-port-summary-autodiscover.md)

  - [Resumo de DNS-descoberta automática no Lync Server 2013](lync-server-2013-dns-summary-autodiscover.md)

  - [Descoberta automática de domínio híbrido e dividido no Lync Server 2013](lync-server-2013-hybrid-and-split-domain-autodiscover.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

