---
title: 'Lync Server 2013: Lista de tabelas de conformidade do Servidor de Chat Persistente'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: List of Persistent Chat Server compliance tables
ms:assetid: 8563446e-90cc-47cc-8a8e-4883decfe195
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ215878(v=OCS.15)
ms:contentKeyID: 48706007
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 31d3df9a0bfd5fa4b8b4acdda15ed86940c2572a
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34828939"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="list-of-persistent-chat-server-compliance-tables-in-lync-server-2013"></a>Lista de tabelas de conformidade do Servidor de Chat Persistente no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2012-10-06_

O esquema de banco de dados de conformidade de chat persistente consiste nas tabelas a seguir.

<div>

## <a name="list-of-persistent-chat-server-compliance-tables"></a>Lista de tabelas de conformidade do servidor de chat persistente


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Tabela</th>
<th>Descrição</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><a href="lync-server-2013-tblcompliancedata.md">tblComplianceData no Lync Server 2013</a></p></td>
<td><p>Contém os eventos de conformidade que ainda não foram processados pelo adaptador configurado.</p>
<p>Esta tabela inclui eventos persistentes relacionados a chats, como mensagens de chat e downloads de arquivos. (Os eventos do participante são rastreados pela tabela tblComplianceParticipant.)</p>
<p>(Os servidores que processaram os eventos nessa tabela estão listados na tabela tblComplianceFanout.)</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-tblcompliancefanout.md">tblComplianceFanout no Lync Server 2013</a></p></td>
<td><p>Contém os servidores que processaram um evento de conformidade. Esta tabela está rigidamente acoplada à tabela tblComplianceData.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-tblcomplianceparticipant.md">tblComplianceParticipant no Lync Server 2013</a></p></td>
<td><p>Contém os participantes atuais por serviço de chat e por servidor. Ele é mantido com base nos eventos de conformidade do ingresso e na parte recebidos do serviço de chat persistente.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-tblcompliancestate.md">tblComplianceState no Lync Server 2013</a></p></td>
<td><p>Contém informações de estado de conformidade em todo o pool.</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

