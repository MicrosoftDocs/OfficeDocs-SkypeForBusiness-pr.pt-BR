---
title: 'Lync Server 2013: Resumo de DNS - Pool de diretores em escala, balanceadores de carga do hardware'
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
ms.openlocfilehash: 891b69339416c81d81e72e43edf5f09bbf9da3e3
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41741061"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="dns-summary---scaled-director-pool-hardware-load-balancer-in-lync-server-2013"></a>Resumo de DNS - Pool de diretores em escala, balanceadores de carga do hardware no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2012-10-20_

A tabela a seguir contém um resumo dos registros DNS necessários para dar suporte ao diretor de carga balanceada do hardware. A função do diretor requer registros DNS semelhantes ao servidor front-end. O número de registros necessários se reflete nos nomes alternativos da entidade obrigatórios no certificado do diretor. Diferente do servidor front-end, o pool de directors não hospeda contas de usuário nem hospeda os serviços de mobilidade.

### <a name="dns-records-required-for-the-director-pool-using-a-hardware-load-balancer-and-dns-load-balancing"></a>Registros DNS necessários para o pool diretor que usa um balanceador de carga de hardware e equilíbrio de carga de DNS

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
<td><p>Registro de host do diretor usado para a comunicação de servidor para replicação e servidor</p></td>
</tr>
<tr class="even">
<td><p>DNS interno/A</p></td>
<td><p>dirpool01.contoso.net</p></td>
<td><p>VIP de HLB do pool do diretor</p></td>
<td><p>Registro de host para o pool de directors de carga balanceada do DNS</p></td>
</tr>
<tr class="odd">
<td><p>DNS interno/A</p></td>
<td><p>sip.contoso.com</p></td>
<td><p>VIP de HLB do pool do diretor</p></td>
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

