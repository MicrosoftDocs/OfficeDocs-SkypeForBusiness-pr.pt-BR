---
title: 'Lync Server 2013: planejamento para descoberta automática'
description: 'Lync Server 2013: planejamento para descoberta automática.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Planning for Autodiscover
ms:assetid: 51f1ff94-1d64-4e6d-a878-b86fa07edc2d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945628(v=OCS.15)
ms:contentKeyID: 51541474
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e28a6a3a317f063151eadde7c5de51b02a46b482
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48544627"
---
# <a name="planning-for-autodiscover-in-lync-server-2013"></a>Planejamento para descoberta automática no Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2013-02-16_

A descoberta automática foi introduzida no Lync Server na atualização cumulativa do Lync Server 2010:2011 de novembro. O principal objetivo dessa implementação inicial da descoberta automática foi fornecer um meio para que o Lync Mobile localize o serviço de mobilidade (MCX). O serviço de descoberta automática no Lync Server 2013 agora é um serviço usado por todos os clientes para localizar serviços de servidor e usuário. O serviço de descoberta automática do Microsoft Lync Server 2013 é executado em diretores e servidores front-end.

<div>


> [!TIP]  
> Para obter uma compreensão mais técnica da descoberta automática e o que é comunicado aos clientes, consulte <A href="lync-server-2013-understanding-autodiscover.md">Understanding autodiscover in Lync Server 2013</A>.<BR>A mobilidade ainda é um cenário distinto, e os serviços de mobilidade ainda exigem alguns planejamentos especiais. Para obter detalhes adicionais, consulte <A href="lync-server-2013-planning-for-mobility.md">Planning for Mobility in Lync Server 2013</A>.



</div>

Quando a descoberta automática foi introduzida no Lync Server 2010, houve comprometimentos que precisavam ser feitos para implementar um serviço que exigia alterações potenciais de certificado para implantações de servidor existentes. A descoberta automática pode ser usada na porta TCP 443 para HTTPS ou over Port TCP 80 para HTTP. Se a decisão foi feita para usar HTTPS, os certificados em proxies reversos, diretores e servidores front-end precisam ser reemitidos para acomodar os `lyncdiscover.<domain>` registros necessários e `lyncdiscoverinternal.<domain>` DNS. Se a decisão era usar HTTP, a reemissão de certificados pode ser evitada usando registros CNAME (ou alias) DNS para usar os nomes existentes nos certificados. O uso de HTTP significa que as comunicações iniciais não foram criptografadas.

Como o Lync Server 2013 usa a descoberta automática para todos os clientes, o cenário principal é usar o HTTPS exclusivamente e criar certificados com o lyncdiscover.\<domain\> como parte da configuração de proxies reversos, diretores e servidores front-end. Se você estiver implementando a descoberta automática em uma implantação atualizada do Lync Server 2010, convém usar HTTP para evitar a reemissão de certificados. As orientações para ambos os cenários são fornecidas nas seções a seguir.

<div>


> [!IMPORTANT]  
> A lista de nomes alternativos da entidade em certificados usados pela regra de publicação dos serviços Web externos deve conter um <EM>lyncdiscover. &lt; sipdomain &gt; </EM> entrada para cada domínio SIP em sua organização. Para obter detalhes sobre as entradas de nome alternativo de entidade que são necessárias para diretores, servidores front-end e proxies reverso, consulte <A href="lync-server-2013-certificate-summary-autodiscover.md">Resumo de certificado-descoberta automática no Lync Server 2013</A>.



</div>

<div>

## <a name="in-this-section"></a>Nesta seção

  - [Resumo de certificado-descoberta automática no Lync Server 2013](lync-server-2013-certificate-summary-autodiscover.md)

  - [Resumo de porta-descoberta automática no Lync Server 2013](lync-server-2013-port-summary-autodiscover.md)

  - [Resumo de DNS-descoberta automática no Lync Server 2013](lync-server-2013-dns-summary-autodiscover.md)

  - [Descoberta automática de domínio e híbrido no Lync Server 2013](lync-server-2013-hybrid-and-split-domain-autodiscover.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

