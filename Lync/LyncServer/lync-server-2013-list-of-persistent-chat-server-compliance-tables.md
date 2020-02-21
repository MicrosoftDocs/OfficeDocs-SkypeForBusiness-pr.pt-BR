---
title: 'Lync Server 2013: lista de tabelas de conformidade do servidor de chat persistente'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: List of Persistent Chat Server compliance tables
ms:assetid: 8563446e-90cc-47cc-8a8e-4883decfe195
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ215878(v=OCS.15)
ms:contentKeyID: 48706007
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 322b700b807f8654e96572a3c040ddd7fe0d1e5f
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42186614"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="list-of-persistent-chat-server-compliance-tables-in-lync-server-2013"></a>Lista de tabelas de conformidade do servidor de chat persistente no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2012-10-06_

O esquema do banco de dados de conformidade de chat persistente consiste nas seguintes tabelas.

<div>

## <a name="list-of-persistent-chat-server-compliance-tables"></a>Lista das tabelas de conformidade do servidor de chat persistente


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
<td><p>Contém eventos de conformidade que ainda não foram processados pelo adaptador configurado.</p>
<p>Esta tabela inclui eventos relacionados a chat persistente, como mensagens de chat e downloads de arquivos. (Os eventos participantes são rastreados pela tabela tblComplianceParticipant.)</p>
<p>Os servidores que processaram os eventos dessa tabela estão listados na tabela tblComplianceFanout.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-tblcompliancefanout.md">tblComplianceFanout no Lync Server 2013</a></p></td>
<td><p>Contém os servidores que processaram um evento de conformidade. Esta tabela está diretamente relacionada à tabela tblComplianceData.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-tblcomplianceparticipant.md">tblComplianceParticipant no Lync Server 2013</a></p></td>
<td><p>Contém os participantes atuais por serviço de chat e por servidor. Ele é mantido com base nos eventos de conformidade de parte e de ingresso recebidos do serviço de chat persistente.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-tblcompliancestate.md">tblComplianceState no Lync Server 2013</a></p></td>
<td><p>Contém informações sobre o estado de conformidade de todo o pool.</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

