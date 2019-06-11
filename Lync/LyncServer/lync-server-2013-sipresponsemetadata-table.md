---
title: 'Lync Server 2013: tabela SIPResponseMetaData'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: SIPResponseMetaData table
ms:assetid: cf723737-4a75-4352-829b-f4954aa59716
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205294(v=OCS.15)
ms:contentKeyID: 48185510
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 31df563172cce2e6ac9780511665ef563532a7d9
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34844897"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="sipresponsemetadata-table-in-lync-server-2013"></a><span data-ttu-id="0c4b4-102">Tabela SIPResponseMetaData no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0c4b4-102">SIPResponseMetaData table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0c4b4-103">_**Tópico da última modificação:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="0c4b4-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="0c4b4-104">O SIPResponseMetaDataTable contém uma lista de códigos de resposta SIP e a classificação e definição de cada um desses códigos.</span><span class="sxs-lookup"><span data-stu-id="0c4b4-104">The SIPResponseMetaDataTable contains a list of SIP response codes and the classification and definition of each of those codes.</span></span> <span data-ttu-id="0c4b4-105">Esses códigos são gerados em resposta a eventos que afetam dispositivos SIP e sessões de comunicação SIP; por exemplo, o código de resposta 403 é gerado quando um dispositivo SIP faz uma solicitação, mas o servidor recusa para honrar essa solicitação.</span><span class="sxs-lookup"><span data-stu-id="0c4b4-105">These codes are generated in response to events affecting SIP devices and SIP communication sessions; for example, the response code 403 is generated when a SIP device makes a request, but the server declines to honor that request.</span></span>

<span data-ttu-id="0c4b4-106">Esta tabela foi introduzida no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="0c4b4-106">This table was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="0c4b4-107">Coluna</span><span class="sxs-lookup"><span data-stu-id="0c4b4-107">Column</span></span></th>
<th><span data-ttu-id="0c4b4-108">Tipo de dados</span><span class="sxs-lookup"><span data-stu-id="0c4b4-108">Data Type</span></span></th>
<th><span data-ttu-id="0c4b4-109">Chave/índice</span><span class="sxs-lookup"><span data-stu-id="0c4b4-109">Key/Index</span></span></th>
<th><span data-ttu-id="0c4b4-110">Detalhes</span><span class="sxs-lookup"><span data-stu-id="0c4b4-110">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="0c4b4-111"><strong>ResponseCode</strong></span><span class="sxs-lookup"><span data-stu-id="0c4b4-111"><strong>ResponseCode</strong></span></span></p></td>
<td><p><span data-ttu-id="0c4b4-112">int</span><span class="sxs-lookup"><span data-stu-id="0c4b4-112">int</span></span></p></td>
<td><p><span data-ttu-id="0c4b4-113">Primária</span><span class="sxs-lookup"><span data-stu-id="0c4b4-113">Primary</span></span></p></td>
<td><p><span data-ttu-id="0c4b4-114">Valor numérico que representa o código de resposta SIP.</span><span class="sxs-lookup"><span data-stu-id="0c4b4-114">Numeric value that represents the SIP response code.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0c4b4-115"><strong>Classe</strong></span><span class="sxs-lookup"><span data-stu-id="0c4b4-115"><strong>Class</strong></span></span></p></td>
<td><p><span data-ttu-id="0c4b4-116">int</span><span class="sxs-lookup"><span data-stu-id="0c4b4-116">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="0c4b4-117">Classificação geral do código de resposta.</span><span class="sxs-lookup"><span data-stu-id="0c4b4-117">General classification for the response code.</span></span> <span data-ttu-id="0c4b4-118">As classificações incluem:</span><span class="sxs-lookup"><span data-stu-id="0c4b4-118">Classifications include:</span></span></p>
<ul>
<li><p><span data-ttu-id="0c4b4-119">1 – respostas informativas</span><span class="sxs-lookup"><span data-stu-id="0c4b4-119">1 – Informational Responses</span></span></p></li>
<li><p><span data-ttu-id="0c4b4-120">2 – respostas bem-sucedidas</span><span class="sxs-lookup"><span data-stu-id="0c4b4-120">2 – Successful Responses</span></span></p></li>
<li><p><span data-ttu-id="0c4b4-121">3 – respostas de redirecionamento</span><span class="sxs-lookup"><span data-stu-id="0c4b4-121">3 – Redirection Responses</span></span></p></li>
<li><p><span data-ttu-id="0c4b4-122">4 – respostas de falha do cliente</span><span class="sxs-lookup"><span data-stu-id="0c4b4-122">4 – Client Failure Responses</span></span></p></li>
<li><p><span data-ttu-id="0c4b4-123">5--respostas de falha do servidor</span><span class="sxs-lookup"><span data-stu-id="0c4b4-123">5 -- Server Failure Responses</span></span></p></li>
<li><p><span data-ttu-id="0c4b4-124">6 – resposta de falha global</span><span class="sxs-lookup"><span data-stu-id="0c4b4-124">6 – Global Failure Response</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0c4b4-125"><strong>Descrição</strong></span><span class="sxs-lookup"><span data-stu-id="0c4b4-125"><strong>Description</strong></span></span></p></td>
<td><p><span data-ttu-id="0c4b4-126">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="0c4b4-126">nvarchar(256)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="0c4b4-127">Descrição do código de resposta SIP.</span><span class="sxs-lookup"><span data-stu-id="0c4b4-127">Description of the SIP response code.</span></span> <span data-ttu-id="0c4b4-128">Por exemplo, o código de resposta 181 tem a seguinte descrição:</span><span class="sxs-lookup"><span data-stu-id="0c4b4-128">For example, response code 181 has the following description:</span></span></p>
<p><span data-ttu-id="0c4b4-129">A chamada está sendo encaminhada</span><span class="sxs-lookup"><span data-stu-id="0c4b4-129">Call Is Being Forwarded</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

