---
title: 'Lync Server 2013: Resumo de DNS - Cargas de DNS e de HLB balanceadas'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: DNS summary - DNS and HLB load balanced
ms:assetid: d2132695-1956-4190-a98e-cd7255cbded6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205273(v=OCS.15)
ms:contentKeyID: 48185447
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ceccb52a8ef9fae810821ffe6b52b763dd8904c4
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34829346"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="dns-summary---dns-and-hlb-load-balanced-in-lync-server-2013"></a>Resumo de DNS - Cargas de DNS e de HLB balanceadas no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2012-10-20_

A tabela a seguir contém um resumo dos registros DNS necessários para dar suporte ao diretor de balanceamento de carga de hardware e carga balanceada do DNS. A função do diretor requer registros DNS semelhantes ao servidor front-end. O número de registros necessários se reflete nos nomes alternativos da entidade obrigatórios no certificado do diretor. Diferente do servidor front-end, o pool de directors não hospeda contas de usuário nem hospeda os serviços de mobilidade.

### <a name="dns-records-required-for-the-director-pool-using-dns-load-balancing-and-hardware-load-balancer"></a>Registros DNS necessários para o pool de diretor que usa o balanceamento de carga de DNS e o balanceador de carga de hardware

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Local/tipo/porta</th>
<th>Registro FQDN/DNS</th>
<th>Endereço IP/FQDN</th>
<th>Mapas para/comentários</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>DNS interno/A</p></td>
<td><p>dir01.contoso.net</p></td>
<td><p>Diretor</p></td>
<td><p>Registro de host do diretor usado para replicação e servidor para servidor</p></td>
</tr>
<tr class="even">
<td><p>DNS interno/A</p></td>
<td><p>dirpool01.contoso.net</p></td>
<td><p>Pool de diretores</p></td>
<td><p>Registro de host para o pool de directors de carga balanceada do DNS do servidor para o servidor</p></td>
</tr>
<tr class="odd">
<td><p>DNS interno/A</p></td>
<td><p>sip.contoso.com</p></td>
<td><p>Pool de diretores</p></td>
<td><p>Protocolo de iniciação de sessão de entrada (SIP) da interface interna do servidor de borda</p></td>
</tr>
<tr class="even">
<td><p>DNS interno/A</p></td>
<td><p>dialin.contoso.com</p></td>
<td><p>VIP de HLB do pool do diretor</p></td>
<td><p>Serviços Web de discagem com carga balanceada do hardware de proxy reverso</p></td>
</tr>
<tr class="odd">
<td><p>DNS interno/A</p></td>
<td><p>meet.contoso.com</p></td>
<td><p>VIP de HLB do pool do diretor</p></td>
<td><p>Publicação de carga de hardware com balanceamento de carga de serviços Web de proxy reverso</p></td>
</tr>
<tr class="even">
<td><p>DNS interno/A</p></td>
<td><p>webdirexternal.contoso.com</p></td>
<td><p>VIP de HLB do pool do diretor</p></td>
<td><p>Carga balanceada de carga de hardware publicada e definida pelos serviços Web externos de tíquete de proxy reverso para o pool de diretor</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

