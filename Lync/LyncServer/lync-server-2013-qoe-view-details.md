---
title: 'Lync Server 2013: detalhes de exibição do QoE'
description: 'Lync Server 2013: detalhes de exibição do QoE.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: QoE view details
ms:assetid: 6a658318-a317-4546-a44c-a9c473d8e86a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688081(v=OCS.15)
ms:contentKeyID: 49733677
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b20eb083295a5f3d3ecb5be7a8c96d9c4b7cfab2
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48579097"
---
# <a name="qoe-view-details-in-lync-server-2013"></a><span data-ttu-id="93728-103">Detalhes da exibição de QoE no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="93728-103">QoE view details in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="93728-104">_**Última modificação do tópico:** 2012-10-03_</span><span class="sxs-lookup"><span data-stu-id="93728-104">_**Topic Last Modified:** 2012-10-03_</span></span>

<span data-ttu-id="93728-105">Os modos de exibição abrangem os cenários mais comuns para retornar dados do banco de dados SQL QoE.</span><span class="sxs-lookup"><span data-stu-id="93728-105">Views cover the most common scenarios for returning data from the QoE SQL database.</span></span> <span data-ttu-id="93728-106">É recomendada as exibições usadas para criar relatórios personalizados, em vez de acessar diretamente as tabelas de banco de dados; Isso ocorre porque os modos de exibição são mais prováveis de manter a compatibilidade com versões anteriores.</span><span class="sxs-lookup"><span data-stu-id="93728-106">It is recommended views used for building custom reports instead of directly accessing the database tables; that’s because views are more likely to maintain backwards compatibility with future releases.</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="93728-107">Nome de exibição</span><span class="sxs-lookup"><span data-stu-id="93728-107">View Name</span></span></th>
<th><span data-ttu-id="93728-108">Descrição</span><span class="sxs-lookup"><span data-stu-id="93728-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="93728-109"><a href="lync-server-2013-audiostreamdetail-view.md">Exibição AudioStreamDetail no Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="93728-109"><a href="lync-server-2013-audiostreamdetail-view.md">AudioStreamDetail view in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="93728-110">Armazena informações sobre cada fluxo de áudio no banco de dados.</span><span class="sxs-lookup"><span data-stu-id="93728-110">Stores information about each audio stream in the database.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="93728-111"><a href="lync-server-2013-medialine-view.md">Modo de exibição de mídia no Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="93728-111"><a href="lync-server-2013-medialine-view.md">MediaLine view in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="93728-112">Armazena informações sobre cada linha de mídia no banco de dados.</span><span class="sxs-lookup"><span data-stu-id="93728-112">Stores information about each media line in the database.</span></span> <span data-ttu-id="93728-113">Uma sessão de áudio normalmente contém uma linha de mídia de áudio.</span><span class="sxs-lookup"><span data-stu-id="93728-113">One audio session typically contains one audio media line.</span></span> <span data-ttu-id="93728-114">Uma sessão de áudio e vídeo (A/V) normalmente contém uma linha de mídia de áudio e uma linha de mídia de vídeo; no entanto, a sessão pode conter duas linhas de mídia de vídeo se um dispositivo de conferência ou o modo de exibição de galeria for usado.</span><span class="sxs-lookup"><span data-stu-id="93728-114">One audio and video (A/V) session typically contains one audio media line and one video media line; however, the session might contain two video media lines if a conferencing device is used or if Gallery View is used.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="93728-115"><a href="lync-server-2013-networkconfigurationsettings-view.md">Exibição NetworkConfigurationSettings no Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="93728-115"><a href="lync-server-2013-networkconfigurationsettings-view.md">NetworkConfigurationSettings view in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="93728-116">Armazena informações sobre a configuração de rede.</span><span class="sxs-lookup"><span data-stu-id="93728-116">Stores information about the network configuration.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="93728-117"><a href="lync-server-2013-session-view.md">Exibição de sessão no Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="93728-117"><a href="lync-server-2013-session-view.md">Session view in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="93728-118">Armazena informações sobre as sessões que têm registros no banco de dados.</span><span class="sxs-lookup"><span data-stu-id="93728-118">Stores information about sessions that have records in the database.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="93728-119"><a href="lync-server-2013-useragent-view.md">Exibição UserAgent no Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="93728-119"><a href="lync-server-2013-useragent-view.md">UserAgent view in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="93728-120">Armazena informações sobre os agentes de usuário que estão envolvidos em sessões que têm registros no banco de dados.</span><span class="sxs-lookup"><span data-stu-id="93728-120">Stores information about the user agents that have been involved in sessions that have records in the database.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="93728-121"><a href="lync-server-2013-videostreamdetail-view.md">Exibição VideoStreamDetail no Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="93728-121"><a href="lync-server-2013-videostreamdetail-view.md">VideoStreamDetail view in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="93728-122">Armazena informações sobre cada fluxo de vídeo no banco de dados.</span><span class="sxs-lookup"><span data-stu-id="93728-122">Stores information about each video stream in the database.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

