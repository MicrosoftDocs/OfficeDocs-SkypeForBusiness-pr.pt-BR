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
ms.openlocfilehash: 6ed7d6edb44ebca8656a50aec432fe3c0ac669d8
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41737341"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="dns-summary---autodiscover-in-lync-server-2013"></a>Resumo de DNS-descoberta automática no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2013-02-13_

A descoberta automática é um serviço flexível, pois ele aceitará comunicação via HTTP ou HTTPS. Para fazer isso, o sistema de nomes de domínio (DNS) e os certificados usados por servidores que hospedam o serviço de descoberta automática devem ser configurados corretamente. Os requisitos de certificado são abordados no [Resumo do certificado-descoberta automática no Lync Server 2013](lync-server-2013-certificate-summary-autodiscover.md).

<div>


> [!IMPORTANT]  
> A lógica de pesquisa de DNS para os clientes do Lync Server usa uma ordem específica de resolução. Você deve sempre incluir o lyncdiscoverinternal. &lt;domínio&gt; e lyncdiscover. &lt;domínio&gt; no seu DNS. Excluindo o lyncdiscoverinternal. &lt;o&gt; registro de domínio causará falha nos clientes internos para se conectar aos serviços pretendidos ou receber a resposta de descoberta automática incorreta.



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
<th>Nome do host</th>
<th>Resolve para</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>CNAME</p></td>
<td><p>Lyncdiscoverinternal. &lt;nome de domínio interno&gt;</p></td>
<td><p>FQDN de serviços Web internos para seu pool de directors, se você tiver um ou para o seu pool de front-ends se não tiver um director.</p></td>
</tr>
<tr class="even">
<td><p>A (host, se IPv6, AAAA)</p></td>
<td><p>lyncdiscoverinternal. &lt;nome de domínio interno&gt;</p></td>
<td><p>Endereço IP interno dos serviços Web (VIP) se você usar um balanceador de carga de seu pool de directors, se você tiver um ou do seu pool Front-End se não tiver um director.</p></td>
</tr>
</tbody>
</table>


Você precisa criar um dos seguintes registros de DNS externo:

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
<th>Nome do host</th>
<th>Resolve para</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>CNAME</p></td>
<td><p>lyncdiscover. &lt;sipdomain&gt;</p></td>
<td><p>FQDN de serviços Web externos para o seu pool de directors, se você tiver um ou para o seu pool de front-end se não tiver um director.</p></td>
</tr>
<tr class="even">
<td><p>A (host, se IPv6, AAAA)</p></td>
<td><p>lyncdiscover. &lt;sipdomain&gt;</p></td>
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
> Os clientes de dispositivos móveis não dão suporte a vários certificados SSL (Secure Sockets Layer) de domínios diferentes. Portanto, não há suporte para o redirecionamento CNAME para domínios diferentes em HTTPS. Por exemplo, um registro CNAME de DNS para lyncdiscover.contoso.com que redireciona para um endereço de director.contoso.net não é compatível com HTTPS. Em uma topologia como essa, um cliente de dispositivo móvel precisa usar HTTP para a primeira solicitação, para que o redirecionamento CNAME seja resolvido por HTTP. Solicitações subsequentes e, em seguida, use HTTPS. Para dar suporte a esse cenário, você precisa configurar seu proxy reverso com uma regra de publicação na Web para a porta 80 (HTTP). Para obter detalhes, consulte "criar uma regra de publicação na Web para a porta 80" em <A href="lync-server-2013-configuring-the-reverse-proxy-for-mobility.md">Configurando o proxy reverso para a mobilidade no Lync Server 2013</A>. O redirecionamento CNAME para o mesmo domínio é compatível com HTTPS. Nesse caso, o certificado do domínio de destino abrange o domínio de origem.



</div>

<div>

## <a name="see-also"></a>Confira também


[Configurando o proxy reverso para mobilidade no Lync Server 2013](lync-server-2013-configuring-the-reverse-proxy-for-mobility.md)  


[Resumo do certificado-descoberta automática no Lync Server 2013](lync-server-2013-certificate-summary-autodiscover.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

