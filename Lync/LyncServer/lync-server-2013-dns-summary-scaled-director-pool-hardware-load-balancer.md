---
title: 'Lync Server 2013: Resumo de DNS-pool de diretores em escala, balanceador de carga de hardware'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: DNS summary - Scaled Director pool, hardware load balancer
ms:assetid: 08ba48e6-bfa1-4ab0-bc89-d58ddb9c20af
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204655(v=OCS.15)
ms:contentKeyID: 48183340
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c7755acc815da690312d2f60c2348076b2231cc5
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48501258"
---
# <a name="dns-summary---scaled-director-pool-hardware-load-balancer-in-lync-server-2013"></a>Resumo de DNS-pool de diretores em escala, balanceador de carga de hardware no Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2012-10-20_

A tabela a seguir contém um resumo dos registros DNS necessários para dar suporte ao diretor de carga balanceada do hardware. A função do diretor requer registros DNS similares como o servidor front-end. O número de registros necessários é refletido nos nomes alternativos da entidade necessários no certificado do diretor. Diferente do servidor front-end, o pool de diretores não hospeda contas de usuário ou hospeda os serviços de mobilidade.

### <a name="dns-records-required-for-the-director-pool-using-a-hardware-load-balancer-and-dns-load-balancing"></a>Registros DNS necessários para o pool de diretores usando um balanceador de carga de hardware e balanceamento de carga de DNS

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
<th>Mapeia para/Comentários</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>DNS/A interno</p></td>
<td><p>dir01.contoso.net</p></td>
<td><p>Diretor</p></td>
<td><p>Registro de host do diretor usado para a comunicação de replicação e servidor</p></td>
</tr>
<tr class="even">
<td><p>DNS/A interno</p></td>
<td><p>dirpool01.contoso.net</p></td>
<td><p>VIP HLB do pool de diretor</p></td>
<td><p>Registro de host para o pool de diretor balanceado de carga DNS</p></td>
</tr>
<tr class="odd">
<td><p>DNS/A interno</p></td>
<td><p>sip.contoso.com</p></td>
<td><p>VIP HLB do pool de diretor</p></td>
<td><p>SIP (protocolo de iniciação de sessão de entrada) da interface interna do servidor de borda</p></td>
</tr>
<tr class="even">
<td><p>DNS/A interno</p></td>
<td><p>dialin.contoso.com</p></td>
<td><p>VIP HLB do pool de diretor</p></td>
<td><p>Carga de hardware balanceada publicada nos serviços da Web de discagem do proxy inverso</p></td>
</tr>
<tr class="odd">
<td><p>DNS/A inverso</p></td>
<td><p>meet.contoso.com</p></td>
<td><p>VIP HLB do pool de diretor</p></td>
<td><p>Carga de hardware balanceada publicada pelos serviços da Web de reunião do proxy inverso</p></td>
</tr>
<tr class="even">
<td><p>DNS/A interno</p></td>
<td><p>webdirexternal.contoso.com</p></td>
<td><p>VIP HLB do pool de diretor</p></td>
<td><p>Carga de hardware balanceada publicada e definida pelos Serviços da Web externos de Ticket da Web do proxy inverso do pool de Diretores</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

