---
title: 'Lync Server 2013: Resumo de DNS - Diretor Único'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: DNS summary - Single Director
ms:assetid: 790ecb56-92cd-41f4-baf6-c290a707aa4d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205021(v=OCS.15)
ms:contentKeyID: 48184568
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ca7fea825267dcdc5aa03a2e6c3c9fb3fc26a84b
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34829340"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="dns-summary---single-director-in-lync-server-2013"></a>Resumo de DNS - Diretor Único no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2012-10-20_

A tabela a seguir contém um resumo dos registros DNS necessários para dar suporte ao diretor único. A função do diretor requer registros DNS semelhantes ao servidor front-end. O número de registros necessários se reflete nos nomes alternativos da entidade obrigatórios no certificado do diretor. Diferente do servidor front-end, o diretor não hospeda contas de usuário nem hospeda os serviços de mobilidade.

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
<td><p>sip.contoso.com</p></td>
<td><p>Diretor</p></td>
<td><p>Protocolo de iniciação de sessão de entrada (SIP) da interface de borda interna do servidor de borda</p></td>
</tr>
<tr class="odd">
<td><p>DNS interno/A</p></td>
<td><p>dialin.contoso.com</p></td>
<td><p>Diretor</p></td>
<td><p>Serviços da discagem publicados do proxy reverso</p></td>
</tr>
<tr class="even">
<td><p>DNS interno/A</p></td>
<td><p>meet.contoso.com</p></td>
<td><p>Diretor</p></td>
<td><p>Serviços Web de reunião publicados do proxy reverso</p></td>
</tr>
<tr class="odd">
<td><p>DNS interno/A</p></td>
<td><p>webdirexternal.contoso.com</p></td>
<td><p>Diretor</p></td>
<td><p>Publicado e definido pelos serviços Web externos de tíquete de proxy reverso para o diretor</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

