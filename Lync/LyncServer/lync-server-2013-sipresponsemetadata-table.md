---
title: 'Lync Server 2013: tabela SIPResponseMetaData'
description: 'Lync Server 2013: tabela SIPResponseMetaData.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: SIPResponseMetaData table
ms:assetid: cf723737-4a75-4352-829b-f4954aa59716
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205294(v=OCS.15)
ms:contentKeyID: 48185510
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 402cff331f81a9b46028d76de69deeaace8d5ae1
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48558977"
---
# <a name="sipresponsemetadata-table-in-lync-server-2013"></a><span data-ttu-id="3b8f6-103">Tabela SIPResponseMetaData no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3b8f6-103">SIPResponseMetaData table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3b8f6-104">_**Última modificação do tópico:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="3b8f6-104">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="3b8f6-p101">O SIPResponseMetaDataTable contém uma lista de códigos de resposta SIP e a classificação e definição de cada um destes códigos. Estes códigos são gerados em resposta aos eventos que afetam dispositivos SIP e sessões de comunicação SIP. Por exemplo, o código de resposta 403 é gerado quando um dispositivo SIP faz uma solicitação, mas o servidor declina esta solicitação.</span><span class="sxs-lookup"><span data-stu-id="3b8f6-p101">The SIPResponseMetaDataTable contains a list of SIP response codes and the classification and definition of each of those codes. These codes are generated in response to events affecting SIP devices and SIP communication sessions; for example, the response code 403 is generated when a SIP device makes a request, but the server declines to honor that request.</span></span>

<span data-ttu-id="3b8f6-107">Esta tabela foi introduzida no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="3b8f6-107">This table was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="3b8f6-108">Coluna</span><span class="sxs-lookup"><span data-stu-id="3b8f6-108">Column</span></span></th>
<th><span data-ttu-id="3b8f6-109">Tipo de dados</span><span class="sxs-lookup"><span data-stu-id="3b8f6-109">Data Type</span></span></th>
<th><span data-ttu-id="3b8f6-110">Chave/índice</span><span class="sxs-lookup"><span data-stu-id="3b8f6-110">Key/Index</span></span></th>
<th><span data-ttu-id="3b8f6-111">Detalhes</span><span class="sxs-lookup"><span data-stu-id="3b8f6-111">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="3b8f6-112"><strong>ResponseCode</strong></span><span class="sxs-lookup"><span data-stu-id="3b8f6-112"><strong>ResponseCode</strong></span></span></p></td>
<td><p><span data-ttu-id="3b8f6-113">int</span><span class="sxs-lookup"><span data-stu-id="3b8f6-113">int</span></span></p></td>
<td><p><span data-ttu-id="3b8f6-114">Primário</span><span class="sxs-lookup"><span data-stu-id="3b8f6-114">Primary</span></span></p></td>
<td><p><span data-ttu-id="3b8f6-115">Valor numérico que representa o código de resposta SIP.</span><span class="sxs-lookup"><span data-stu-id="3b8f6-115">Numeric value that represents the SIP response code.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3b8f6-116"><strong>Classe</strong></span><span class="sxs-lookup"><span data-stu-id="3b8f6-116"><strong>Class</strong></span></span></p></td>
<td><p><span data-ttu-id="3b8f6-117">int</span><span class="sxs-lookup"><span data-stu-id="3b8f6-117">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="3b8f6-p102">Classificação geral do código de resposta. As classificações incluem:</span><span class="sxs-lookup"><span data-stu-id="3b8f6-p102">General classification for the response code. Classifications include:</span></span></p>
<ul>
<li><p><span data-ttu-id="3b8f6-120">1 – Respostas informacionais</span><span class="sxs-lookup"><span data-stu-id="3b8f6-120">1 – Informational Responses</span></span></p></li>
<li><p><span data-ttu-id="3b8f6-121">2 – Respostas de sucesso</span><span class="sxs-lookup"><span data-stu-id="3b8f6-121">2 – Successful Responses</span></span></p></li>
<li><p><span data-ttu-id="3b8f6-122">3 – Respostas de redirecionamento</span><span class="sxs-lookup"><span data-stu-id="3b8f6-122">3 – Redirection Responses</span></span></p></li>
<li><p><span data-ttu-id="3b8f6-123">4 – Respostas de falha do cliente</span><span class="sxs-lookup"><span data-stu-id="3b8f6-123">4 – Client Failure Responses</span></span></p></li>
<li><p><span data-ttu-id="3b8f6-124">5--respostas de falha do servidor</span><span class="sxs-lookup"><span data-stu-id="3b8f6-124">5 -- Server Failure Responses</span></span></p></li>
<li><p><span data-ttu-id="3b8f6-125">6 – Resposta de falha global</span><span class="sxs-lookup"><span data-stu-id="3b8f6-125">6 – Global Failure Response</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3b8f6-126"><strong>Descrição</strong></span><span class="sxs-lookup"><span data-stu-id="3b8f6-126"><strong>Description</strong></span></span></p></td>
<td><p><span data-ttu-id="3b8f6-127">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="3b8f6-127">nvarchar(256)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="3b8f6-p103">Descrição do código de resposta SIP. Por exemplo, o código de resposta 181 possui a seguinte descrição:</span><span class="sxs-lookup"><span data-stu-id="3b8f6-p103">Description of the SIP response code. For example, response code 181 has the following description:</span></span></p>
<p><span data-ttu-id="3b8f6-130">A chamada está sendo encaminhada</span><span class="sxs-lookup"><span data-stu-id="3b8f6-130">Call Is Being Forwarded</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

