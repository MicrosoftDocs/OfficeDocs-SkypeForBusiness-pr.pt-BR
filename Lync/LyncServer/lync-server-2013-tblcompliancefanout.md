---
title: 'Lync Server 2013: tblComplianceFanout'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: tblComplianceFanout
ms:assetid: f5d9f342-a7cb-4b54-baa6-e656256b75ad
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615050(v=OCS.15)
ms:contentKeyID: 48185828
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3df687926940aa98f3bf803f9a991527f19fa58f
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48509438"
---
# <a name="tblcompliancefanout-in-lync-server-2013"></a><span data-ttu-id="899cb-102">tblComplianceFanout no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="899cb-102">tblComplianceFanout in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="899cb-103">_**Última modificação do tópico:** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="899cb-103">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="899cb-104">A tabela tblComplianceFanout contém todos os servidores que processaram um evento de conformidade.</span><span class="sxs-lookup"><span data-stu-id="899cb-104">tblComplianceFanout contains all servers that processed a compliance event.</span></span>

### <a name="columns"></a><span data-ttu-id="899cb-105">Colunas</span><span class="sxs-lookup"><span data-stu-id="899cb-105">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="899cb-106">Coluna</span><span class="sxs-lookup"><span data-stu-id="899cb-106">Column</span></span></th>
<th><span data-ttu-id="899cb-107">Tipo</span><span class="sxs-lookup"><span data-stu-id="899cb-107">Type</span></span></th>
<th><span data-ttu-id="899cb-108">Descrição</span><span class="sxs-lookup"><span data-stu-id="899cb-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="899cb-109">fanoutEventID</span><span class="sxs-lookup"><span data-stu-id="899cb-109">fanoutEventID</span></span></p></td>
<td><p><span data-ttu-id="899cb-110">int</span><span class="sxs-lookup"><span data-stu-id="899cb-110">int</span></span></p></td>
<td><p><span data-ttu-id="899cb-111">ID do evento.</span><span class="sxs-lookup"><span data-stu-id="899cb-111">Event ID.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="899cb-112">fanoutServerID</span><span class="sxs-lookup"><span data-stu-id="899cb-112">fanoutServerID</span></span></p></td>
<td><p><span data-ttu-id="899cb-113">int</span><span class="sxs-lookup"><span data-stu-id="899cb-113">int</span></span></p></td>
<td><p><span data-ttu-id="899cb-114">Identidade do servidor (correspondente à tabela tblServerIdentity.serverID).</span><span class="sxs-lookup"><span data-stu-id="899cb-114">Server identity (corresponding to tblServerIdentity.serverID table).</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="key"></a><span data-ttu-id="899cb-115">Chave</span><span class="sxs-lookup"><span data-stu-id="899cb-115">Key</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="899cb-116">Coluna</span><span class="sxs-lookup"><span data-stu-id="899cb-116">Column</span></span></th>
<th><span data-ttu-id="899cb-117">Descrição</span><span class="sxs-lookup"><span data-stu-id="899cb-117">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="899cb-118">fanoutEventID</span><span class="sxs-lookup"><span data-stu-id="899cb-118">fanoutEventID</span></span></p></td>
<td><p><span data-ttu-id="899cb-119">Chave estrangeira com pesquisa na tabela tblComplianceData.cmplEventID.</span><span class="sxs-lookup"><span data-stu-id="899cb-119">Foreign key with lookup in tblComplianceData.cmplEventID table.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

