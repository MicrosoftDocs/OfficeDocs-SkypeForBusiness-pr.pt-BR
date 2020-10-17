---
title: 'Lync Server 2013: tabela Medialist'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: MediaList table
ms:assetid: 1f440590-c1bc-483e-b7bc-6cc763847768
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398279(v=OCS.15)
ms:contentKeyID: 48183579
ms.date: 07/12/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7a22ef9b9e0ef429fcac96a7f7d5c87093f79a02
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48505718"
---
# <a name="medialist-table-in-lync-server-2013"></a><span data-ttu-id="cde5e-102">Tabela medialist no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="cde5e-102">MediaList table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="cde5e-103">_**Última modificação do tópico:** 2016-07-12_</span><span class="sxs-lookup"><span data-stu-id="cde5e-103">_**Topic Last Modified:** 2016-07-12_</span></span>

<span data-ttu-id="cde5e-104">MediaList é uma tabela estática que armazena a lista de vários tipos de mídia.</span><span class="sxs-lookup"><span data-stu-id="cde5e-104">The MediaList table is a static table that stores the list of various media types.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="cde5e-105">Coluna</span><span class="sxs-lookup"><span data-stu-id="cde5e-105">Column</span></span></th>
<th><span data-ttu-id="cde5e-106">Tipo de dados</span><span class="sxs-lookup"><span data-stu-id="cde5e-106">Data Type</span></span></th>
<th><span data-ttu-id="cde5e-107">Chave/índice</span><span class="sxs-lookup"><span data-stu-id="cde5e-107">Key/Index</span></span></th>
<th><span data-ttu-id="cde5e-108">Detalhes</span><span class="sxs-lookup"><span data-stu-id="cde5e-108">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="cde5e-109"><strong>Mediaid</strong></span><span class="sxs-lookup"><span data-stu-id="cde5e-109"><strong>MediaId</strong></span></span></p></td>
<td><p><span data-ttu-id="cde5e-110">tinyint</span><span class="sxs-lookup"><span data-stu-id="cde5e-110">tinyint</span></span></p></td>
<td><p><span data-ttu-id="cde5e-111">Primário</span><span class="sxs-lookup"><span data-stu-id="cde5e-111">Primary</span></span></p></td>
<td><p><span data-ttu-id="cde5e-112">Valores: 1-7</span><span class="sxs-lookup"><span data-stu-id="cde5e-112">Values: 1-7</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cde5e-113"><strong>Mídia</strong></span><span class="sxs-lookup"><span data-stu-id="cde5e-113"><strong>Media</strong></span></span></p></td>
<td><p><span data-ttu-id="cde5e-114">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="cde5e-114">nvarchar(256)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="cde5e-115">Mapeamento estático de mediaid e valores de mídia:</span><span class="sxs-lookup"><span data-stu-id="cde5e-115">Static mapping of MediaID and Media values:</span></span></p>
<ul>
<li><p><span data-ttu-id="cde5e-116">1 – IM</span><span class="sxs-lookup"><span data-stu-id="cde5e-116">1 – IM</span></span></p></li>
<li><p><span data-ttu-id="cde5e-117">2 – Transferência de arquivos</span><span class="sxs-lookup"><span data-stu-id="cde5e-117">2 – File Transfer</span></span></p></li>
<li><p><span data-ttu-id="cde5e-118">3 – Assistência Remota</span><span class="sxs-lookup"><span data-stu-id="cde5e-118">3 – Remote Assistance</span></span></p></li>
<li><p><span data-ttu-id="cde5e-119">4 – Compartilhamento de Aplicativos</span><span class="sxs-lookup"><span data-stu-id="cde5e-119">4 – Application Sharing</span></span></p></li>
<li><p><span data-ttu-id="cde5e-120">5 – áudio</span><span class="sxs-lookup"><span data-stu-id="cde5e-120">5 – Audio</span></span></p></li>
<li><p><span data-ttu-id="cde5e-121">6 – vídeo</span><span class="sxs-lookup"><span data-stu-id="cde5e-121">6 – Video</span></span></p></li>
<li><p><span data-ttu-id="cde5e-122">7 – Convite do Aplicativo</span><span class="sxs-lookup"><span data-stu-id="cde5e-122">7 – App Invite</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


<span data-ttu-id="cde5e-123">Se você estiver tentando determinar o tipo de modalidade para os valores em LcsCDR. SessionDetailsView. MediaTypes, será necessário usar o trecho de junção a seguir:</span><span class="sxs-lookup"><span data-stu-id="cde5e-123">If you are trying to determine the modality type for the values in LcsCDR.SessionDetailsView.MediaTypes, then you need to use the following Join snippet:</span></span>

    LEFT JOIN on Media.MediaId = MediaList.MediaId

</div>

<span> </span>

</div>

</div>

</div>

