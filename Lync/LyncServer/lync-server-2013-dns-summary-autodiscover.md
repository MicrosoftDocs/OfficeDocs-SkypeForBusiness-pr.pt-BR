---
title: 'Lync Server 2013: Resumo de DNS-descoberta automática'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: DNS summary - Autodiscover
ms:assetid: b336a2ae-0e58-4b74-b606-aedbbd411587
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945644(v=OCS.15)
ms:contentKeyID: 51541504
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fc30b787d938825f229f28b10d54907ad26a4d35
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48501318"
---
# <a name="dns-summary---autodiscover-in-lync-server-2013"></a>Resumo de DNS-descoberta automática no Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2013-02-13_

A descoberta automática é um serviço flexível, pois aceitará comunicação por HTTP ou HTTPS. Para fazer isso, o DNS (sistema de nomes de domínio) e os certificados usados por servidores que hospedam o serviço de descoberta automática devem estar configurados corretamente. Os requisitos de certificado são cobertos no [Resumo de certificados-descoberta automática no Lync Server 2013](lync-server-2013-certificate-summary-autodiscover.md).

<div>


> [!IMPORTANT]  
> A lógica de pesquisa de DNS para os clientes do Lync Server usa uma ordem específica de resolução. Você deve sempre incluir o lyncdiscoverinternal. &lt; domínio &gt; e lyncdiscover. &lt; domínio &gt; no seu DNS. Excluindo o lyncdiscoverinternal. &lt; &gt; o registro de domínio fará com que os clientes internos não consigam se conectar aos serviços pretendidos ou recebam a resposta de descoberta automática incorreta.



</div>

### <a name="internal-dns-records"></a>Registros DNS internos

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Tipo de registro</th>
<th>Nome do Host</th>
<th>Resolve para</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>CNAME</p></td>
<td><p>Lyncdiscoverinternal. &lt; nome de domínio interno&gt;</p></td>
<td><p>FQDN de serviços Web internos para seu pool de diretores, se você tiver um, ou para seu pool de front-ends, se não tiver um diretor.</p></td>
</tr>
<tr class="even">
<td><p>A (host, se IPv6, AAAA)</p></td>
<td><p>lyncdiscoverinternal. &lt; nome de domínio interno&gt;</p></td>
<td><p>Endereço IP de serviços Web interno (VIP (IP virtual) se você usar um balanceador de carga) do seu pool de diretores, se você tiver um, ou do seu pool de front-ends, se não tiver um diretor.</p></td>
</tr>
</tbody>
</table>


É necessário criar um dos seguintes registros DNS externos:

### <a name="external-dns-records"></a>Registros DNS externos

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Tipo de registro</th>
<th>Nome do Host</th>
<th>Resolve para</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>CNAME</p></td>
<td><p>lyncdiscover. &lt; sipdomain&gt;</p></td>
<td><p>FQDN de serviços Web externos para seu pool de diretor, se você tiver um, ou para seu pool de front-ends, se não tiver um diretor.</p></td>
</tr>
<tr class="even">
<td><p>A (host, se IPv6, AAAA)</p></td>
<td><p>lyncdiscover. &lt; sipdomain&gt;</p></td>
<td><p>Endereço IP externo ou público do proxy reverso.</p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> O tráfego externo passa pelo proxy reverso.



</div>

<div>


> [!NOTE]  
> Os clientes de dispositivo móvel não suportam vários certificados de SSL (Secure Sockets Layer) de domínios diferentes. Portanto, não há redirecionamento CNAME para diferentes domínios por HTTPS. Por exemplo, um registro DNS CNAME para lyncdiscover.contoso.com que redireciona a um endereço de director.contoso.net não é suportado por HTTPS. Na topologia, um cliente de dispositivo móvel precisa usar HTTP para a primeira solicitação, para que o redirecionamento de CNAME seja resolvido por HTTP. As solicitações subseqüentes usam HTTPS. Para oferecer suporte a esse cenário, você precisará configurar o proxy inverso com uma regra de publicação na web para a porta 80 (HTTP). Para obter detalhes, consulte "criar uma regra de publicação na Web para a porta 80" em <A href="lync-server-2013-configuring-the-reverse-proxy-for-mobility.md">Configurando o proxy reverso para mobilidade no Lync Server 2013</A>. O redirecionamento de CNAME ao mesmo domínio é suportado por HTTPS. Nesse caso, o certificado do domínio de destino abrange o domínio de origem.



</div>

<div>

## <a name="see-also"></a>Confira também


[Configurando o proxy reverso para mobilidade no Lync Server 2013](lync-server-2013-configuring-the-reverse-proxy-for-mobility.md)  


[Resumo de certificado-descoberta automática no Lync Server 2013](lync-server-2013-certificate-summary-autodiscover.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

