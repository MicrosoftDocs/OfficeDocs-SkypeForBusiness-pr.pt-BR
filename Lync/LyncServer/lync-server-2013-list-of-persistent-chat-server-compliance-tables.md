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

# <a name="list-of-persistent-chat-server-compliance-tables-in-lync-server-2013"></a><span data-ttu-id="3e09d-102">Lista de tabelas de conformidade do Servidor de Chat Persistente no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3e09d-102">List of Persistent Chat Server compliance tables in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3e09d-103">_**Tópico da última modificação:** 2012-10-06_</span><span class="sxs-lookup"><span data-stu-id="3e09d-103">_**Topic Last Modified:** 2012-10-06_</span></span>

<span data-ttu-id="3e09d-104">O esquema de banco de dados de conformidade de chat persistente consiste nas tabelas a seguir.</span><span class="sxs-lookup"><span data-stu-id="3e09d-104">The Persistent Chat compliance database schema consists of the following tables.</span></span>

<div>

## <a name="list-of-persistent-chat-server-compliance-tables"></a><span data-ttu-id="3e09d-105">Lista de tabelas de conformidade do servidor de chat persistente</span><span class="sxs-lookup"><span data-stu-id="3e09d-105">List of Persistent Chat Server Compliance Tables</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="3e09d-106">Tabela</span><span class="sxs-lookup"><span data-stu-id="3e09d-106">Table</span></span></th>
<th><span data-ttu-id="3e09d-107">Descrição</span><span class="sxs-lookup"><span data-stu-id="3e09d-107">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="3e09d-108"><a href="lync-server-2013-tblcompliancedata.md">tblComplianceData no Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="3e09d-108"><a href="lync-server-2013-tblcompliancedata.md">tblComplianceData in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="3e09d-109">Contém os eventos de conformidade que ainda não foram processados pelo adaptador configurado.</span><span class="sxs-lookup"><span data-stu-id="3e09d-109">Contains the compliance events that have not yet been processed by the configured adapter.</span></span></p>
<p><span data-ttu-id="3e09d-110">Esta tabela inclui eventos persistentes relacionados a chats, como mensagens de chat e downloads de arquivos.</span><span class="sxs-lookup"><span data-stu-id="3e09d-110">This table includes Persistent Chat-related events, such as chat messages and file downloads.</span></span> <span data-ttu-id="3e09d-111">(Os eventos do participante são rastreados pela tabela tblComplianceParticipant.)</span><span class="sxs-lookup"><span data-stu-id="3e09d-111">(Participant events are tracked by the tblComplianceParticipant table.)</span></span></p>
<p><span data-ttu-id="3e09d-112">(Os servidores que processaram os eventos nessa tabela estão listados na tabela tblComplianceFanout.)</span><span class="sxs-lookup"><span data-stu-id="3e09d-112">(The servers that processed the events in this table are listed in the tblComplianceFanout table.)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3e09d-113"><a href="lync-server-2013-tblcompliancefanout.md">tblComplianceFanout no Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="3e09d-113"><a href="lync-server-2013-tblcompliancefanout.md">tblComplianceFanout in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="3e09d-114">Contém os servidores que processaram um evento de conformidade.</span><span class="sxs-lookup"><span data-stu-id="3e09d-114">Contains the servers that processed a compliance event.</span></span> <span data-ttu-id="3e09d-115">Esta tabela está rigidamente acoplada à tabela tblComplianceData.</span><span class="sxs-lookup"><span data-stu-id="3e09d-115">This table is tightly coupled with the tblComplianceData table.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3e09d-116"><a href="lync-server-2013-tblcomplianceparticipant.md">tblComplianceParticipant no Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="3e09d-116"><a href="lync-server-2013-tblcomplianceparticipant.md">tblComplianceParticipant in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="3e09d-117">Contém os participantes atuais por serviço de chat e por servidor.</span><span class="sxs-lookup"><span data-stu-id="3e09d-117">Contains current participants per chat service and per server.</span></span> <span data-ttu-id="3e09d-118">Ele é mantido com base nos eventos de conformidade do ingresso e na parte recebidos do serviço de chat persistente.</span><span class="sxs-lookup"><span data-stu-id="3e09d-118">It is maintained based on join and part compliance events received from the Persistent Chat service.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3e09d-119"><a href="lync-server-2013-tblcompliancestate.md">tblComplianceState no Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="3e09d-119"><a href="lync-server-2013-tblcompliancestate.md">tblComplianceState in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="3e09d-120">Contém informações de estado de conformidade em todo o pool.</span><span class="sxs-lookup"><span data-stu-id="3e09d-120">Contains pool-wide compliance state information.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

