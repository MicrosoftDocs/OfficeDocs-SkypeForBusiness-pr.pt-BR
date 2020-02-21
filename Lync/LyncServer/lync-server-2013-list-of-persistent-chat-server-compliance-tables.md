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

# <a name="list-of-persistent-chat-server-compliance-tables-in-lync-server-2013"></a><span data-ttu-id="0d7dc-102">Lista de tabelas de conformidade do servidor de chat persistente no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0d7dc-102">List of Persistent Chat Server compliance tables in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0d7dc-103">_**Última modificação do tópico:** 2012-10-06_</span><span class="sxs-lookup"><span data-stu-id="0d7dc-103">_**Topic Last Modified:** 2012-10-06_</span></span>

<span data-ttu-id="0d7dc-104">O esquema do banco de dados de conformidade de chat persistente consiste nas seguintes tabelas.</span><span class="sxs-lookup"><span data-stu-id="0d7dc-104">The Persistent Chat compliance database schema consists of the following tables.</span></span>

<div>

## <a name="list-of-persistent-chat-server-compliance-tables"></a><span data-ttu-id="0d7dc-105">Lista das tabelas de conformidade do servidor de chat persistente</span><span class="sxs-lookup"><span data-stu-id="0d7dc-105">List of Persistent Chat Server Compliance Tables</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="0d7dc-106">Tabela</span><span class="sxs-lookup"><span data-stu-id="0d7dc-106">Table</span></span></th>
<th><span data-ttu-id="0d7dc-107">Descrição</span><span class="sxs-lookup"><span data-stu-id="0d7dc-107">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="0d7dc-108"><a href="lync-server-2013-tblcompliancedata.md">tblComplianceData no Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="0d7dc-108"><a href="lync-server-2013-tblcompliancedata.md">tblComplianceData in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="0d7dc-109">Contém eventos de conformidade que ainda não foram processados pelo adaptador configurado.</span><span class="sxs-lookup"><span data-stu-id="0d7dc-109">Contains the compliance events that have not yet been processed by the configured adapter.</span></span></p>
<p><span data-ttu-id="0d7dc-110">Esta tabela inclui eventos relacionados a chat persistente, como mensagens de chat e downloads de arquivos.</span><span class="sxs-lookup"><span data-stu-id="0d7dc-110">This table includes Persistent Chat-related events, such as chat messages and file downloads.</span></span> <span data-ttu-id="0d7dc-111">(Os eventos participantes são rastreados pela tabela tblComplianceParticipant.)</span><span class="sxs-lookup"><span data-stu-id="0d7dc-111">(Participant events are tracked by the tblComplianceParticipant table.)</span></span></p>
<p><span data-ttu-id="0d7dc-112">Os servidores que processaram os eventos dessa tabela estão listados na tabela tblComplianceFanout.</span><span class="sxs-lookup"><span data-stu-id="0d7dc-112">(The servers that processed the events in this table are listed in the tblComplianceFanout table.)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0d7dc-113"><a href="lync-server-2013-tblcompliancefanout.md">tblComplianceFanout no Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="0d7dc-113"><a href="lync-server-2013-tblcompliancefanout.md">tblComplianceFanout in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="0d7dc-114">Contém os servidores que processaram um evento de conformidade.</span><span class="sxs-lookup"><span data-stu-id="0d7dc-114">Contains the servers that processed a compliance event.</span></span> <span data-ttu-id="0d7dc-115">Esta tabela está diretamente relacionada à tabela tblComplianceData.</span><span class="sxs-lookup"><span data-stu-id="0d7dc-115">This table is tightly coupled with the tblComplianceData table.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0d7dc-116"><a href="lync-server-2013-tblcomplianceparticipant.md">tblComplianceParticipant no Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="0d7dc-116"><a href="lync-server-2013-tblcomplianceparticipant.md">tblComplianceParticipant in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="0d7dc-117">Contém os participantes atuais por serviço de chat e por servidor.</span><span class="sxs-lookup"><span data-stu-id="0d7dc-117">Contains current participants per chat service and per server.</span></span> <span data-ttu-id="0d7dc-118">Ele é mantido com base nos eventos de conformidade de parte e de ingresso recebidos do serviço de chat persistente.</span><span class="sxs-lookup"><span data-stu-id="0d7dc-118">It is maintained based on join and part compliance events received from the Persistent Chat service.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0d7dc-119"><a href="lync-server-2013-tblcompliancestate.md">tblComplianceState no Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="0d7dc-119"><a href="lync-server-2013-tblcompliancestate.md">tblComplianceState in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="0d7dc-120">Contém informações sobre o estado de conformidade de todo o pool.</span><span class="sxs-lookup"><span data-stu-id="0d7dc-120">Contains pool-wide compliance state information.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

