---
title: 'Lync Server 2013: detalhes da exibição de QoE'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: QoE view details
ms:assetid: 6a658318-a317-4546-a44c-a9c473d8e86a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688081(v=OCS.15)
ms:contentKeyID: 49733677
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8e223ff2adee63eb8e13304e4df6db519e85014f
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34823683"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="qoe-view-details-in-lync-server-2013"></a><span data-ttu-id="9f88d-102">Detalhes do modo de exibição de QoE no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9f88d-102">QoE view details in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9f88d-103">_**Tópico da última modificação:** 2012-10-03_</span><span class="sxs-lookup"><span data-stu-id="9f88d-103">_**Topic Last Modified:** 2012-10-03_</span></span>

<span data-ttu-id="9f88d-104">Os modos de exibição abrangem os cenários mais comuns para retornar dados do banco de dados do QoE SQL.</span><span class="sxs-lookup"><span data-stu-id="9f88d-104">Views cover the most common scenarios for returning data from the QoE SQL database.</span></span> <span data-ttu-id="9f88d-105">Ele é recomendado para a criação de relatórios personalizados, em vez de acessar diretamente as tabelas de banco de dados; Isso porque os modos de exibição são mais prováveis de manter a compatibilidade retroativa com versões futuras.</span><span class="sxs-lookup"><span data-stu-id="9f88d-105">It is recommended views used for building custom reports instead of directly accessing the database tables; that’s because views are more likely to maintain backwards compatibility with future releases.</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="9f88d-106">Nome do modo de exibição</span><span class="sxs-lookup"><span data-stu-id="9f88d-106">View Name</span></span></th>
<th><span data-ttu-id="9f88d-107">Descrição</span><span class="sxs-lookup"><span data-stu-id="9f88d-107">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="9f88d-108"><a href="lync-server-2013-audiostreamdetail-view.md">Exibição AudioStreamDetail no Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="9f88d-108"><a href="lync-server-2013-audiostreamdetail-view.md">AudioStreamDetail view in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="9f88d-109">Armazena informações sobre cada fluxo de áudio no banco de dados.</span><span class="sxs-lookup"><span data-stu-id="9f88d-109">Stores information about each audio stream in the database.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9f88d-110"><a href="lync-server-2013-medialine-view.md">Modo de exibição de mídia no Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="9f88d-110"><a href="lync-server-2013-medialine-view.md">MediaLine view in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="9f88d-111">Armazena informações sobre cada linha de mídia no banco de dados.</span><span class="sxs-lookup"><span data-stu-id="9f88d-111">Stores information about each media line in the database.</span></span> <span data-ttu-id="9f88d-112">Uma sessão de áudio geralmente contém uma linha de mídia de áudio.</span><span class="sxs-lookup"><span data-stu-id="9f88d-112">One audio session typically contains one audio media line.</span></span> <span data-ttu-id="9f88d-113">Uma sessão de áudio e vídeo (A/V) geralmente contém uma linha de mídia de áudio e uma linha de mídia de vídeo; no entanto, a sessão pode conter duas linhas de mídia de vídeo se um dispositivo de conferência for usado ou se o modo de exibição de galeria for usado.</span><span class="sxs-lookup"><span data-stu-id="9f88d-113">One audio and video (A/V) session typically contains one audio media line and one video media line; however, the session might contain two video media lines if a conferencing device is used or if Gallery View is used.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9f88d-114"><a href="lync-server-2013-networkconfigurationsettings-view.md">Exibição NetworkConfigurationSettings no Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="9f88d-114"><a href="lync-server-2013-networkconfigurationsettings-view.md">NetworkConfigurationSettings view in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="9f88d-115">Armazena informações sobre a configuração de rede.</span><span class="sxs-lookup"><span data-stu-id="9f88d-115">Stores information about the network configuration.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9f88d-116"><a href="lync-server-2013-session-view.md">Modo de exibição de sessão no Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="9f88d-116"><a href="lync-server-2013-session-view.md">Session view in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="9f88d-117">Armazena informações sobre sessões que têm registros no banco de dados.</span><span class="sxs-lookup"><span data-stu-id="9f88d-117">Stores information about sessions that have records in the database.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9f88d-118"><a href="lync-server-2013-useragent-view.md">Modo de exibição do UserAgent no Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="9f88d-118"><a href="lync-server-2013-useragent-view.md">UserAgent view in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="9f88d-119">Armazena informações sobre os agentes de usuário envolvidos em sessões que têm registros no banco de dados.</span><span class="sxs-lookup"><span data-stu-id="9f88d-119">Stores information about the user agents that have been involved in sessions that have records in the database.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9f88d-120"><a href="lync-server-2013-videostreamdetail-view.md">Exibição VideoStreamDetail no Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="9f88d-120"><a href="lync-server-2013-videostreamdetail-view.md">VideoStreamDetail view in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="9f88d-121">Armazena informações sobre cada fluxo de vídeo no banco de dados.</span><span class="sxs-lookup"><span data-stu-id="9f88d-121">Stores information about each video stream in the database.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

