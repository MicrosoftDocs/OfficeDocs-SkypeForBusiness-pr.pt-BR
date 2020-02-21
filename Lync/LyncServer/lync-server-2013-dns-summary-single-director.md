---
title: 'Lync Server 2013: Resumo de DNS-diretor único'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: DNS summary - Single Director
ms:assetid: 790ecb56-92cd-41f4-baf6-c290a707aa4d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205021(v=OCS.15)
ms:contentKeyID: 48184568
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 692cfd5f04a80a674fffb5e3a0f2f1890309c371
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42192834"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="dns-summary---single-director-in-lync-server-2013"></a>Resumo de DNS-diretor único no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2012-10-20_

A tabela a seguir contém um resumo dos registros DNS necessários para dar suporte ao diretor único. A função do diretor requer registros DNS similares como o servidor front-end. O número de registros necessários é refletido nos nomes alternativos da entidade necessários no certificado do diretor. Diferente do servidor front-end, o diretor não hospeda contas de usuário ou hospeda os serviços de mobilidade.

### <a name="dns-records-required-for-the-director"></a>Registros DNS necessários para o diretor

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
<td><p>Be</p></td>
<td><p>Registro de host do diretor usado para replicação e servidor para servidor</p></td>
</tr>
<tr class="even">
<td><p>DNS/A interno</p></td>
<td><p>sip.contoso.com</p></td>
<td><p>Be</p></td>
<td><p>SIP (protocolo de iniciação de sessão de entrada) da interface de borda interna do servidor de borda</p></td>
</tr>
<tr class="odd">
<td><p>DNS/A interno</p></td>
<td><p>dialin.contoso.com</p></td>
<td><p>Be</p></td>
<td><p>Serviços Web de discagem publicados do proxy reverso</p></td>
</tr>
<tr class="even">
<td><p>DNS/A inverso</p></td>
<td><p>meet.contoso.com</p></td>
<td><p>Be</p></td>
<td><p>Serviços Web de reunião publicados do proxy reverso</p></td>
</tr>
<tr class="odd">
<td><p>DNS interno/A</p></td>
<td><p>webdirexternal.contoso.com</p></td>
<td><p>Be</p></td>
<td><p>Publicado e definido pelos serviços Web externos de tíquete da Web de proxy reverso para o diretor</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

