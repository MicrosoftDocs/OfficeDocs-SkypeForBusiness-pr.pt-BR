---
title: 'Lync Server 2013: Tabela MediaLine'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: MediaLine table
ms:assetid: 414b1d63-ae97-4c27-bac0-c9ad0f808ff0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425920(v=OCS.15)
ms:contentKeyID: 48183956
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4828f67614115eb4d6f46ab0a0a7c315e02d1924
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34827435"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="medialine-table-in-lync-server-2013"></a><span data-ttu-id="4c1d4-102">Tabela MediaLine no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4c1d4-102">MediaLine table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4c1d4-103">_**Tópico da última modificação:** 2014-02-21_</span><span class="sxs-lookup"><span data-stu-id="4c1d4-103">_**Topic Last Modified:** 2014-02-21_</span></span>

<span data-ttu-id="4c1d4-104">Cada registro representa uma linha de mídia.</span><span class="sxs-lookup"><span data-stu-id="4c1d4-104">Each record represents one media line.</span></span> <span data-ttu-id="4c1d4-105">(Uma sessão de áudio geralmente contém uma linha de mídia de áudio.</span><span class="sxs-lookup"><span data-stu-id="4c1d4-105">(One audio session usually contains one audio media line.</span></span> <span data-ttu-id="4c1d4-106">Uma sessão de áudio e vídeo (A/V) geralmente contém uma linha de mídia de áudio e uma linha de mídia de vídeo, embora a sessão possa conter duas linhas de mídia de vídeo se um dispositivo de conferência for usado ou se o modo de exibição de galeria for usado.</span><span class="sxs-lookup"><span data-stu-id="4c1d4-106">One audio and video (A/V) session usually contains one audio media line and one video media line, although the session might contain two video media lines if a conferencing device is used or if Gallery View is used.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="4c1d4-107"><strong>Coluna</strong></span><span class="sxs-lookup"><span data-stu-id="4c1d4-107"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="4c1d4-108"><strong>Tipo de dados</strong></span><span class="sxs-lookup"><span data-stu-id="4c1d4-108"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="4c1d4-109"><strong>Chave/índice</strong></span><span class="sxs-lookup"><span data-stu-id="4c1d4-109"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="4c1d4-110"><strong>Detalhes</strong></span><span class="sxs-lookup"><span data-stu-id="4c1d4-110"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="4c1d4-111"><strong>ConferenceDateTime</strong></span><span class="sxs-lookup"><span data-stu-id="4c1d4-111"><strong>ConferenceDateTime</strong></span></span></p></td>
<td><p><span data-ttu-id="4c1d4-112">datetime</span><span class="sxs-lookup"><span data-stu-id="4c1d4-112">datetime</span></span></p></td>
<td><p><span data-ttu-id="4c1d4-113">Primária</span><span class="sxs-lookup"><span data-stu-id="4c1d4-113">Primary</span></span></p></td>
<td><p><span data-ttu-id="4c1d4-114">Referenciado da <a href="lync-server-2013-session-table.md">tabela de sessão no Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="4c1d4-114">Referenced from the <a href="lync-server-2013-session-table.md">Session table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4c1d4-115"><strong>SessionSeq</strong></span><span class="sxs-lookup"><span data-stu-id="4c1d4-115"><strong>SessionSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="4c1d4-116">int</span><span class="sxs-lookup"><span data-stu-id="4c1d4-116">int</span></span></p></td>
<td><p><span data-ttu-id="4c1d4-117">Primária</span><span class="sxs-lookup"><span data-stu-id="4c1d4-117">Primary</span></span></p></td>
<td><p><span data-ttu-id="4c1d4-118">Referenciado da <a href="lync-server-2013-session-table.md">tabela de sessão no Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="4c1d4-118">Referenced from the <a href="lync-server-2013-session-table.md">Session table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4c1d4-119"><strong>MediaLineLabel</strong></span><span class="sxs-lookup"><span data-stu-id="4c1d4-119"><strong>MediaLineLabel</strong></span></span></p></td>
<td><p><span data-ttu-id="4c1d4-120">tinyint</span><span class="sxs-lookup"><span data-stu-id="4c1d4-120">tinyint</span></span></p></td>
<td><p><span data-ttu-id="4c1d4-121">Primária</span><span class="sxs-lookup"><span data-stu-id="4c1d4-121">Primary</span></span></p></td>
<td><p><span data-ttu-id="4c1d4-122">0 é o áudio principal, 1 é o vídeo principal e 2 é o vídeo panorâmico, 3 é o compartilhamento de aplicativos/desktop.</span><span class="sxs-lookup"><span data-stu-id="4c1d4-122">0 is main audio, 1 is main video, and 2 is panoramic video, 3 is Application/Desktop Sharing.</span></span> <span data-ttu-id="4c1d4-123">Esse rótulo deve ser exclusivo em uma única sessão.</span><span class="sxs-lookup"><span data-stu-id="4c1d4-123">This label must be unique within a single session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4c1d4-124"><strong>ConnectivityIce</strong></span><span class="sxs-lookup"><span data-stu-id="4c1d4-124"><strong>ConnectivityIce</strong></span></span></p></td>
<td><p><span data-ttu-id="4c1d4-125">tinyint</span><span class="sxs-lookup"><span data-stu-id="4c1d4-125">tinyint</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="4c1d4-126">Esta coluna está presente, mas não é usada no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="4c1d4-126">This column is present but not used in Microsoft Lync Server 2013.</span></span> <span data-ttu-id="4c1d4-127">Informações sobre a conectividade usada para uma linha de mídia são capturadas nas colunas CallerConnectivityICE e CalleeConnectivityICE.</span><span class="sxs-lookup"><span data-stu-id="4c1d4-127">Information about the connectivity used for a media line is captured in the CallerConnectivityICE and CalleeConnectivityICE columns.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4c1d4-128"><strong>CallerIceWarningFlags</strong></span><span class="sxs-lookup"><span data-stu-id="4c1d4-128"><strong>CallerIceWarningFlags</strong></span></span></p></td>
<td><p><span data-ttu-id="4c1d4-129">int</span><span class="sxs-lookup"><span data-stu-id="4c1d4-129">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="4c1d4-130">Informações sobre o processo de estabelecimento de conectividade interativa (ICE) descrito em sinalizadores de bits.</span><span class="sxs-lookup"><span data-stu-id="4c1d4-130">Information about Interactive Connectivity Establishment (ICE) process described in bits flags.</span></span> <span data-ttu-id="4c1d4-131">Para obter detalhes, consulte a <em>especificação de protocolo de servidor do monitoramento de qualidade de experiência</em>, disponível para download.</span><span class="sxs-lookup"><span data-stu-id="4c1d4-131">For details, refer to the <em>Quality of Experience Monitoring Server Protocol Specification</em>, available for download.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4c1d4-132"><strong>CalleeIceWarningFlags</strong></span><span class="sxs-lookup"><span data-stu-id="4c1d4-132"><strong>CalleeIceWarningFlags</strong></span></span></p></td>
<td><p><span data-ttu-id="4c1d4-133">int</span><span class="sxs-lookup"><span data-stu-id="4c1d4-133">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="4c1d4-134">Mesmo que CallerIceWarningFlags, mas no lado do chamador.</span><span class="sxs-lookup"><span data-stu-id="4c1d4-134">Same as CallerIceWarningFlags, but on the callee side.</span></span> <span data-ttu-id="4c1d4-135">Para obter detalhes, consulte a <em>especificação de protocolo de servidor do monitoramento de qualidade de experiência</em>, disponível para download.</span><span class="sxs-lookup"><span data-stu-id="4c1d4-135">For details, refer to the <em>Quality of Experience Monitoring Server Protocol Specification</em>, available for download.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4c1d4-136"><strong>Segurança</strong></span><span class="sxs-lookup"><span data-stu-id="4c1d4-136"><strong>Security</strong></span></span></p></td>
<td><p><span data-ttu-id="4c1d4-137">tinyint</span><span class="sxs-lookup"><span data-stu-id="4c1d4-137">tinyint</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="4c1d4-138">O perfil de segurança em uso.</span><span class="sxs-lookup"><span data-stu-id="4c1d4-138">The security profile in use.</span></span> <span data-ttu-id="4c1d4-139">0 é nenhum, 1 é SRTP; 2 é v1.</span><span class="sxs-lookup"><span data-stu-id="4c1d4-139">0 is NONE, 1 is SRTP, 2 is V1.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4c1d4-140"><strong>SMTP</strong></span><span class="sxs-lookup"><span data-stu-id="4c1d4-140"><strong>Transport</strong></span></span></p></td>
<td><p><span data-ttu-id="4c1d4-141">tinyint</span><span class="sxs-lookup"><span data-stu-id="4c1d4-141">tinyint</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="4c1d4-142">0 é UDP; 1 é TCP.</span><span class="sxs-lookup"><span data-stu-id="4c1d4-142">0 is UDP, 1 is TCP.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4c1d4-143"><strong>CallerIPAddr</strong></span><span class="sxs-lookup"><span data-stu-id="4c1d4-143"><strong>CallerIPAddr</strong></span></span></p></td>
<td><p><span data-ttu-id="4c1d4-144">int</span><span class="sxs-lookup"><span data-stu-id="4c1d4-144">int</span></span></p></td>
<td><p><span data-ttu-id="4c1d4-145">Exterior</span><span class="sxs-lookup"><span data-stu-id="4c1d4-145">Foreign</span></span></p></td>
<td><p><span data-ttu-id="4c1d4-146">Endereço IP do chamador.</span><span class="sxs-lookup"><span data-stu-id="4c1d4-146">IP Address of the caller.</span></span> <span data-ttu-id="4c1d4-147">Consulte a <a href="lync-server-2013-ipaddress-table.md">tabela IPAddress no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="4c1d4-147">See the <a href="lync-server-2013-ipaddress-table.md">IPAddress table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4c1d4-148"><strong>CallerPort</strong></span><span class="sxs-lookup"><span data-stu-id="4c1d4-148"><strong>CallerPort</strong></span></span></p></td>
<td><p><span data-ttu-id="4c1d4-149">int</span><span class="sxs-lookup"><span data-stu-id="4c1d4-149">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="4c1d4-150">Porta usada pelo chamador.</span><span class="sxs-lookup"><span data-stu-id="4c1d4-150">Port used by the caller.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4c1d4-151"><strong>CallerSubnet</strong></span><span class="sxs-lookup"><span data-stu-id="4c1d4-151"><strong>CallerSubnet</strong></span></span></p></td>
<td><p><span data-ttu-id="4c1d4-152">int</span><span class="sxs-lookup"><span data-stu-id="4c1d4-152">int</span></span></p></td>
<td><p><span data-ttu-id="4c1d4-153"> Exterior</span><span class="sxs-lookup"><span data-stu-id="4c1d4-153"> Foreign</span></span></p></td>
<td><p><span data-ttu-id="4c1d4-154">A sub-rede do chamador.</span><span class="sxs-lookup"><span data-stu-id="4c1d4-154">The subnet of the caller.</span></span> <span data-ttu-id="4c1d4-155">Consulte a <a href="lync-server-2013-ipaddress-table.md">tabela IPAddress no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="4c1d4-155">See the <a href="lync-server-2013-ipaddress-table.md">IPAddress table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4c1d4-156"><strong>CallerInside</strong></span><span class="sxs-lookup"><span data-stu-id="4c1d4-156"><strong>CallerInside</strong></span></span></p></td>
<td><p><span data-ttu-id="4c1d4-157">bit</span><span class="sxs-lookup"><span data-stu-id="4c1d4-157">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="4c1d4-158">1 significa que a chamada está dentro da rede corporativa, 0 significa que o chamador está fora da rede.</span><span class="sxs-lookup"><span data-stu-id="4c1d4-158">1 means caller is inside the enterprise network, 0 means the caller is outside the network.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4c1d4-159"><strong>CallerMacAddress</strong></span><span class="sxs-lookup"><span data-stu-id="4c1d4-159"><strong>CallerMacAddress</strong></span></span></p></td>
<td><p><span data-ttu-id="4c1d4-160">int</span><span class="sxs-lookup"><span data-stu-id="4c1d4-160">int</span></span></p></td>
<td><p><span data-ttu-id="4c1d4-161">Exterior</span><span class="sxs-lookup"><span data-stu-id="4c1d4-161">Foreign</span></span></p></td>
<td><p><span data-ttu-id="4c1d4-162">Endereço MAC do chamador, referenciado na <a href="lync-server-2013-macaddress-table.md">tabela MACAddress no Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="4c1d4-162">Caller’s mac address, referenced from <a href="lync-server-2013-macaddress-table.md">MacAddress table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4c1d4-163"><strong>CallerRelayIPAddr</strong></span><span class="sxs-lookup"><span data-stu-id="4c1d4-163"><strong>CallerRelayIPAddr</strong></span></span></p></td>
<td><p><span data-ttu-id="4c1d4-164">int</span><span class="sxs-lookup"><span data-stu-id="4c1d4-164">int</span></span></p></td>
<td><p><span data-ttu-id="4c1d4-165">Exterior</span><span class="sxs-lookup"><span data-stu-id="4c1d4-165">Foreign</span></span></p></td>
<td><p><span data-ttu-id="4c1d4-166">Endereço IP do serviço de borda a/V do Lync Server usado pelo chamador.</span><span class="sxs-lookup"><span data-stu-id="4c1d4-166">IP Address of the Lync Server A/V Edge service used by the caller.</span></span> <span data-ttu-id="4c1d4-167">Consulte a <a href="lync-server-2013-ipaddress-table.md">tabela IPAddress no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="4c1d4-167">See the <a href="lync-server-2013-ipaddress-table.md">IPAddress table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4c1d4-168"><strong>CallerRelayPort</strong></span><span class="sxs-lookup"><span data-stu-id="4c1d4-168"><strong>CallerRelayPort</strong></span></span></p></td>
<td><p><span data-ttu-id="4c1d4-169">int</span><span class="sxs-lookup"><span data-stu-id="4c1d4-169">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="4c1d4-170">Porta usada no serviço de borda A/V pelo chamador.</span><span class="sxs-lookup"><span data-stu-id="4c1d4-170">Port used on the A/V Edge service by the caller.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4c1d4-171"><strong>CallerCaptureDev</strong></span><span class="sxs-lookup"><span data-stu-id="4c1d4-171"><strong>CallerCaptureDev</strong></span></span></p></td>
<td><p><span data-ttu-id="4c1d4-172">int</span><span class="sxs-lookup"><span data-stu-id="4c1d4-172">int</span></span></p></td>
<td><p><span data-ttu-id="4c1d4-173">Exterior</span><span class="sxs-lookup"><span data-stu-id="4c1d4-173">Foreign</span></span></p></td>
<td><p><span data-ttu-id="4c1d4-174">Dispositivo de captura usado pelo chamador.</span><span class="sxs-lookup"><span data-stu-id="4c1d4-174">Capture device used by the caller.</span></span> <span data-ttu-id="4c1d4-175">Referenciado da <a href="lync-server-2013-device-table.md">tabela de dispositivos no Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="4c1d4-175">Referenced from the <a href="lync-server-2013-device-table.md">Device table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4c1d4-176"><strong>CallerRenderDev</strong></span><span class="sxs-lookup"><span data-stu-id="4c1d4-176"><strong>CallerRenderDev</strong></span></span></p></td>
<td><p><span data-ttu-id="4c1d4-177">int</span><span class="sxs-lookup"><span data-stu-id="4c1d4-177">int</span></span></p></td>
<td><p><span data-ttu-id="4c1d4-178">Exterior</span><span class="sxs-lookup"><span data-stu-id="4c1d4-178">Foreign</span></span></p></td>
<td><p><span data-ttu-id="4c1d4-179">Processar o dispositivo usado pelo chamador.</span><span class="sxs-lookup"><span data-stu-id="4c1d4-179">Render device used by caller.</span></span> <span data-ttu-id="4c1d4-180">Referenciado da <a href="lync-server-2013-device-table.md">tabela de dispositivos no Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="4c1d4-180">Referenced from the <a href="lync-server-2013-device-table.md">Device table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4c1d4-181"><strong>CallerCaptureDevDriver</strong></span><span class="sxs-lookup"><span data-stu-id="4c1d4-181"><strong>CallerCaptureDevDriver</strong></span></span></p></td>
<td><p><span data-ttu-id="4c1d4-182">int</span><span class="sxs-lookup"><span data-stu-id="4c1d4-182">int</span></span></p></td>
<td><p><span data-ttu-id="4c1d4-183">Exterior</span><span class="sxs-lookup"><span data-stu-id="4c1d4-183">Foreign</span></span></p></td>
<td><p><span data-ttu-id="4c1d4-184">Driver para o dispositivo de captura do chamador, referenciado na <a href="lync-server-2013-devicedriver-table.md">tabela DeviceDriver no Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="4c1d4-184">Driver for the caller’s capture device, referenced from the <a href="lync-server-2013-devicedriver-table.md">DeviceDriver table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4c1d4-185"><strong>CallerRenderDevDriver</strong></span><span class="sxs-lookup"><span data-stu-id="4c1d4-185"><strong>CallerRenderDevDriver</strong></span></span></p></td>
<td><p><span data-ttu-id="4c1d4-186">int</span><span class="sxs-lookup"><span data-stu-id="4c1d4-186">int</span></span></p></td>
<td><p><span data-ttu-id="4c1d4-187">Exterior</span><span class="sxs-lookup"><span data-stu-id="4c1d4-187">Foreign</span></span></p></td>
<td><p><span data-ttu-id="4c1d4-188">Driver para o dispositivo de renderização do chamador, referenciado na <a href="lync-server-2013-devicedriver-table.md">tabela DeviceDriver no Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="4c1d4-188">Driver for the caller’s render device, referenced from the <a href="lync-server-2013-devicedriver-table.md">DeviceDriver table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4c1d4-189"><strong>CallerNetworkConnectionType</strong></span><span class="sxs-lookup"><span data-stu-id="4c1d4-189"><strong>CallerNetworkConnectionType</strong></span></span></p></td>
<td><p><span data-ttu-id="4c1d4-190">tinyint</span><span class="sxs-lookup"><span data-stu-id="4c1d4-190">tinyint</span></span></p></td>
<td><p><span data-ttu-id="4c1d4-191">Exterior</span><span class="sxs-lookup"><span data-stu-id="4c1d4-191">Foreign</span></span></p></td>
<td><p><span data-ttu-id="4c1d4-192">Indica como o chamador está conectado à rede.</span><span class="sxs-lookup"><span data-stu-id="4c1d4-192">Indicates how the caller connected to the network.</span></span> <span data-ttu-id="4c1d4-193">Os valores são obtidos na <a href="lync-server-2013-networkconnectiondetail-table.md">tabela NetworkConnectionDetail no Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="4c1d4-193">Values are obtained from the <a href="lync-server-2013-networkconnectiondetail-table.md">NetworkConnectionDetail table in Lync Server 2013</a>.</span></span> <span data-ttu-id="4c1d4-194">Os valores típicos são 0 para uma conexão com fio ' 1 para conexão WiFi; e 3 para uma conexão Ethernet.</span><span class="sxs-lookup"><span data-stu-id="4c1d4-194">Typical values are 0 for a wired connection’ 1 for a WiFi connection; and 3 for an Ethernet connection.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4c1d4-195"><strong>CallerBssid</strong></span><span class="sxs-lookup"><span data-stu-id="4c1d4-195"><strong>CallerBssid</strong></span></span></p></td>
<td><p><span data-ttu-id="4c1d4-196">int</span><span class="sxs-lookup"><span data-stu-id="4c1d4-196">int</span></span></p></td>
<td><p><span data-ttu-id="4c1d4-197">Exterior</span><span class="sxs-lookup"><span data-stu-id="4c1d4-197">Foreign</span></span></p></td>
<td><p><span data-ttu-id="4c1d4-198">BSSID do chamador se for usada uma conexão sem fio.</span><span class="sxs-lookup"><span data-stu-id="4c1d4-198">Caller’s BSSID if wireless is used.</span></span> <span data-ttu-id="4c1d4-199">Referenciado da <a href="lync-server-2013-macaddress-table.md">tabela MACAddress no Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="4c1d4-199">Referenced from <a href="lync-server-2013-macaddress-table.md">MacAddress table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4c1d4-200"><strong>CallerVPN</strong></span><span class="sxs-lookup"><span data-stu-id="4c1d4-200"><strong>CallerVPN</strong></span></span></p></td>
<td><p><span data-ttu-id="4c1d4-201">bit</span><span class="sxs-lookup"><span data-stu-id="4c1d4-201">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="4c1d4-202">O link do chamador.</span><span class="sxs-lookup"><span data-stu-id="4c1d4-202">The caller's link.</span></span> <span data-ttu-id="4c1d4-203">1 é uma rede virtual privada (VPN), 0 não é VPN.</span><span class="sxs-lookup"><span data-stu-id="4c1d4-203">1 is virtual private network (VPN), 0 is non-VPN.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4c1d4-204"><strong>CallerLinkSpeed</strong></span><span class="sxs-lookup"><span data-stu-id="4c1d4-204"><strong>CallerLinkSpeed</strong></span></span></p></td>
<td><p><span data-ttu-id="4c1d4-205">decimal (18, 0)</span><span class="sxs-lookup"><span data-stu-id="4c1d4-205">decimal(18,0)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="4c1d4-206">A velocidade do link de rede, em bps, para o ponto de extremidade do chamador.</span><span class="sxs-lookup"><span data-stu-id="4c1d4-206">The network link speed, in bps, for the caller's endpoint.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4c1d4-207"><strong>CalleeIPAddr</strong></span><span class="sxs-lookup"><span data-stu-id="4c1d4-207"><strong>CalleeIPAddr</strong></span></span></p></td>
<td><p><span data-ttu-id="4c1d4-208">int</span><span class="sxs-lookup"><span data-stu-id="4c1d4-208">int</span></span></p></td>
<td><p><span data-ttu-id="4c1d4-209">Exterior</span><span class="sxs-lookup"><span data-stu-id="4c1d4-209">Foreign</span></span></p></td>
<td><p><span data-ttu-id="4c1d4-210">Endereço IP do receptor da chamada.</span><span class="sxs-lookup"><span data-stu-id="4c1d4-210">IP Address of the call receiver.</span></span> <span data-ttu-id="4c1d4-211">Consulte a <a href="lync-server-2013-ipaddress-table.md">tabela IPAddress no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="4c1d4-211">See the <a href="lync-server-2013-ipaddress-table.md">IPAddress table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4c1d4-212"><strong>CalleePort</strong></span><span class="sxs-lookup"><span data-stu-id="4c1d4-212"><strong>CalleePort</strong></span></span></p></td>
<td><p><span data-ttu-id="4c1d4-213">bit</span><span class="sxs-lookup"><span data-stu-id="4c1d4-213">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="4c1d4-214">Porta usada pelo receptor da chamada.</span><span class="sxs-lookup"><span data-stu-id="4c1d4-214">Port used by the call receiver.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4c1d4-215"><strong>CalleeSubnet</strong></span><span class="sxs-lookup"><span data-stu-id="4c1d4-215"><strong>CalleeSubnet</strong></span></span></p></td>
<td><p><span data-ttu-id="4c1d4-216">int</span><span class="sxs-lookup"><span data-stu-id="4c1d4-216">int</span></span></p></td>
<td><p><span data-ttu-id="4c1d4-217">Exterior</span><span class="sxs-lookup"><span data-stu-id="4c1d4-217">Foreign</span></span></p></td>
<td><p><span data-ttu-id="4c1d4-218">Sub-rede do chamado.</span><span class="sxs-lookup"><span data-stu-id="4c1d4-218">Subnet of callee.</span></span> <span data-ttu-id="4c1d4-219">Consulte a <a href="lync-server-2013-ipaddress-table.md">tabela IPAddress no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="4c1d4-219">See the <a href="lync-server-2013-ipaddress-table.md">IPAddress table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4c1d4-220"><strong>CalleeInside</strong></span><span class="sxs-lookup"><span data-stu-id="4c1d4-220"><strong>CalleeInside</strong></span></span></p></td>
<td><p><span data-ttu-id="4c1d4-221">bit</span><span class="sxs-lookup"><span data-stu-id="4c1d4-221">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="4c1d4-222">1 significa que o receptor da chamada está dentro da rede corporativa, 0 significa que o receptor da chamada está fora da rede.</span><span class="sxs-lookup"><span data-stu-id="4c1d4-222">1 means call receiver is inside the enterprise network, 0 means the call receiver is outside the network.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4c1d4-223"><strong>CalleeMacAddress</strong></span><span class="sxs-lookup"><span data-stu-id="4c1d4-223"><strong>CalleeMacAddress</strong></span></span></p></td>
<td><p><span data-ttu-id="4c1d4-224">int</span><span class="sxs-lookup"><span data-stu-id="4c1d4-224">int</span></span></p></td>
<td><p><span data-ttu-id="4c1d4-225">Exterior</span><span class="sxs-lookup"><span data-stu-id="4c1d4-225">Foreign</span></span></p></td>
<td><p><span data-ttu-id="4c1d4-226">Endereço MAC do chamador.</span><span class="sxs-lookup"><span data-stu-id="4c1d4-226">Callee Mac address.</span></span> <span data-ttu-id="4c1d4-227">Referenciada na <a href="lync-server-2013-macaddress-table.md">tabela MACAddress no Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="4c1d4-227">Referenced from the <a href="lync-server-2013-macaddress-table.md">MacAddress table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4c1d4-228"><strong>CalleeRelayIPAddr</strong></span><span class="sxs-lookup"><span data-stu-id="4c1d4-228"><strong>CalleeRelayIPAddr</strong></span></span></p></td>
<td><p><span data-ttu-id="4c1d4-229">int</span><span class="sxs-lookup"><span data-stu-id="4c1d4-229">int</span></span></p></td>
<td><p><span data-ttu-id="4c1d4-230">Exterior</span><span class="sxs-lookup"><span data-stu-id="4c1d4-230">Foreign</span></span></p></td>
<td><p><span data-ttu-id="4c1d4-231">Endereço IP do serviço de borda A/V usado pelo receptor de chamadas.</span><span class="sxs-lookup"><span data-stu-id="4c1d4-231">IP Address of the A/V Edge service used by the call receiver.</span></span> <span data-ttu-id="4c1d4-232">Consulte a <a href="lync-server-2013-ipaddress-table.md">tabela IPAddress no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="4c1d4-232">See the <a href="lync-server-2013-ipaddress-table.md">IPAddress table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4c1d4-233"><strong>CalleeRelayPort</strong></span><span class="sxs-lookup"><span data-stu-id="4c1d4-233"><strong>CalleeRelayPort</strong></span></span></p></td>
<td><p><span data-ttu-id="4c1d4-234">int</span><span class="sxs-lookup"><span data-stu-id="4c1d4-234">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="4c1d4-235">Porta usada no serviço de borda a/V pelo receptor da chamada.</span><span class="sxs-lookup"><span data-stu-id="4c1d4-235">Port used on the A/V Edge Service by the call receiver.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4c1d4-236"><strong>CalleeCaptureDev</strong></span><span class="sxs-lookup"><span data-stu-id="4c1d4-236"><strong>CalleeCaptureDev</strong></span></span></p></td>
<td><p><span data-ttu-id="4c1d4-237">int</span><span class="sxs-lookup"><span data-stu-id="4c1d4-237">int</span></span></p></td>
<td><p><span data-ttu-id="4c1d4-238">exterior</span><span class="sxs-lookup"><span data-stu-id="4c1d4-238">foreign</span></span></p></td>
<td><p><span data-ttu-id="4c1d4-239">Dispositivo de captura usado pelo receptor de chamadas.</span><span class="sxs-lookup"><span data-stu-id="4c1d4-239">Capture device used by the call receiver.</span></span> <span data-ttu-id="4c1d4-240">Referenciado da <a href="lync-server-2013-device-table.md">tabela de dispositivos no Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="4c1d4-240">Referenced from the <a href="lync-server-2013-device-table.md">Device table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4c1d4-241"><strong>CalleeRenderDev</strong></span><span class="sxs-lookup"><span data-stu-id="4c1d4-241"><strong>CalleeRenderDev</strong></span></span></p></td>
<td><p><span data-ttu-id="4c1d4-242">int</span><span class="sxs-lookup"><span data-stu-id="4c1d4-242">int</span></span></p></td>
<td><p><span data-ttu-id="4c1d4-243">Exterior</span><span class="sxs-lookup"><span data-stu-id="4c1d4-243">Foreign</span></span></p></td>
<td><p><span data-ttu-id="4c1d4-244">Processar o dispositivo usado pelo receptor da chamada.</span><span class="sxs-lookup"><span data-stu-id="4c1d4-244">Render device used by the call receiver.</span></span> <span data-ttu-id="4c1d4-245">Referenciado da <a href="lync-server-2013-device-table.md">tabela de dispositivos no Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="4c1d4-245">Referenced from the <a href="lync-server-2013-device-table.md">Device table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4c1d4-246"><strong>CalleeCaptureDevDriver</strong></span><span class="sxs-lookup"><span data-stu-id="4c1d4-246"><strong>CalleeCaptureDevDriver</strong></span></span></p></td>
<td><p><span data-ttu-id="4c1d4-247">int</span><span class="sxs-lookup"><span data-stu-id="4c1d4-247">int</span></span></p></td>
<td><p><span data-ttu-id="4c1d4-248">Exterior</span><span class="sxs-lookup"><span data-stu-id="4c1d4-248">Foreign</span></span></p></td>
<td><p><span data-ttu-id="4c1d4-249">Driver para o dispositivo de captura do receptor da chamada.</span><span class="sxs-lookup"><span data-stu-id="4c1d4-249">Driver for the call receiver’s capture device.</span></span> <span data-ttu-id="4c1d4-250">Referenciado pela <a href="lync-server-2013-devicedriver-table.md">tabela DeviceDriver no Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="4c1d4-250">Referenced from <a href="lync-server-2013-devicedriver-table.md">DeviceDriver table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4c1d4-251"><strong>CalleeRenderDevDriver</strong></span><span class="sxs-lookup"><span data-stu-id="4c1d4-251"><strong>CalleeRenderDevDriver</strong></span></span></p></td>
<td><p><span data-ttu-id="4c1d4-252">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="4c1d4-252">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="4c1d4-253">Exterior</span><span class="sxs-lookup"><span data-stu-id="4c1d4-253">Foreign</span></span></p></td>
<td><p><span data-ttu-id="4c1d4-254">Driver para o dispositivo de renderização do receptor da chamada.</span><span class="sxs-lookup"><span data-stu-id="4c1d4-254">Driver for the call receiver’s render device.</span></span> <span data-ttu-id="4c1d4-255">Referenciado pela <a href="lync-server-2013-devicedriver-table.md">tabela DeviceDriver no Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="4c1d4-255">Referenced from <a href="lync-server-2013-devicedriver-table.md">DeviceDriver table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4c1d4-256"><strong>CalleeNetworkConnectionType</strong></span><span class="sxs-lookup"><span data-stu-id="4c1d4-256"><strong>CalleeNetworkConnectionType</strong></span></span></p></td>
<td><p><span data-ttu-id="4c1d4-257">tinyint</span><span class="sxs-lookup"><span data-stu-id="4c1d4-257">tinyint</span></span></p></td>
<td><p><span data-ttu-id="4c1d4-258">Exterior</span><span class="sxs-lookup"><span data-stu-id="4c1d4-258">Foreign</span></span></p></td>
<td><p><span data-ttu-id="4c1d4-259">Indica como o chamador está conectado à rede.</span><span class="sxs-lookup"><span data-stu-id="4c1d4-259">Indicates how the callee connected to the network.</span></span> <span data-ttu-id="4c1d4-260">Os valores são obtidos na <a href="lync-server-2013-networkconnectiondetail-table.md">tabela NetworkConnectionDetail no Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="4c1d4-260">Values are obtained from the <a href="lync-server-2013-networkconnectiondetail-table.md">NetworkConnectionDetail table in Lync Server 2013</a>.</span></span> <span data-ttu-id="4c1d4-261">Os valores típicos são 0 para uma conexão com fio ' 1 para conexão WiFi; e 3 para uma conexão Ethernet.</span><span class="sxs-lookup"><span data-stu-id="4c1d4-261">Typical values are 0 for a wired connection’ 1 for a WiFi connection; and 3 for an Ethernet connection.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4c1d4-262"><strong>CalleeBssid</strong></span><span class="sxs-lookup"><span data-stu-id="4c1d4-262"><strong>CalleeBssid</strong></span></span></p></td>
<td><p><span data-ttu-id="4c1d4-263">int</span><span class="sxs-lookup"><span data-stu-id="4c1d4-263">int</span></span></p></td>
<td><p><span data-ttu-id="4c1d4-264">Exterior</span><span class="sxs-lookup"><span data-stu-id="4c1d4-264">Foreign</span></span></p></td>
<td><p><span data-ttu-id="4c1d4-265">BSSID do chamador se for usada uma conexão sem fio.</span><span class="sxs-lookup"><span data-stu-id="4c1d4-265">Callee’s BSSID if wireless is used.</span></span> <span data-ttu-id="4c1d4-266">Referenciado da <a href="lync-server-2013-macaddress-table.md">tabela MACAddress no Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="4c1d4-266">Referenced from <a href="lync-server-2013-macaddress-table.md">MacAddress table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4c1d4-267"><strong>CalleeVPN</strong></span><span class="sxs-lookup"><span data-stu-id="4c1d4-267"><strong>CalleeVPN</strong></span></span></p></td>
<td><p><span data-ttu-id="4c1d4-268">bit</span><span class="sxs-lookup"><span data-stu-id="4c1d4-268">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="4c1d4-269">O link do receptor da chamada; 1 é uma rede virtual privada (VPN), 0 não é VPN.</span><span class="sxs-lookup"><span data-stu-id="4c1d4-269">The call receiver’s link; 1 is virtual private network (VPN), 0 is non-VPN.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4c1d4-270"><strong>CalleeLinkSpeed</strong></span><span class="sxs-lookup"><span data-stu-id="4c1d4-270"><strong>CalleeLinkSpeed</strong></span></span></p></td>
<td><p><span data-ttu-id="4c1d4-271">decimal (18, 0)</span><span class="sxs-lookup"><span data-stu-id="4c1d4-271">decimal(18,0)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="4c1d4-272">A velocidade do link de rede, em bps, para o ponto de extremidade do receptor da chamada.</span><span class="sxs-lookup"><span data-stu-id="4c1d4-272">The network link speed, in bps, for the call receiver’s endpoint.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4c1d4-273"><strong>ConversationalMOS</strong></span><span class="sxs-lookup"><span data-stu-id="4c1d4-273"><strong>ConversationalMOS</strong></span></span></p></td>
<td><p><span data-ttu-id="4c1d4-274">decimal (3; 2)</span><span class="sxs-lookup"><span data-stu-id="4c1d4-274">decimal(3,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="4c1d4-275">O MOS de conversa de banda estreita das sessões de áudio (com base nos dois fluxos de áudio).</span><span class="sxs-lookup"><span data-stu-id="4c1d4-275">Narrowband Conversational MOS of the audio sessions (based on both audio streams).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4c1d4-276"><strong>AppliedBandwidthLimit</strong></span><span class="sxs-lookup"><span data-stu-id="4c1d4-276"><strong>AppliedBandwidthLimit</strong></span></span></p></td>
<td><p><span data-ttu-id="4c1d4-277">int</span><span class="sxs-lookup"><span data-stu-id="4c1d4-277">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="4c1d4-278">Esta é a largura de banda real aplicada ao fluxo de envios do lado fornecido com várias configurações de política (ativar, API, SDP, servidor de política e assim por diante).</span><span class="sxs-lookup"><span data-stu-id="4c1d4-278">This is the actual bandwidth applied to the given send side stream given various policy settings (TURN, API, SDP, Policy Server, and so on).</span></span> <span data-ttu-id="4c1d4-279">Isso não deve ser confundido com a largura de banda efetiva porque pode haver uma largura de banda mais econômica com base na estimativa de largura de banda.</span><span class="sxs-lookup"><span data-stu-id="4c1d4-279">This is not to be confused with the effective bandwidth because there can be a lower effective bandwidth based on the bandwidth estimate.</span></span> <span data-ttu-id="4c1d4-280">Isso é basicamente a largura de banda máxima que o fluxo de envio pode ter limites de bloqueio impostos pela estimativa da largura de banda.</span><span class="sxs-lookup"><span data-stu-id="4c1d4-280">This is basically the maximum bandwidth the send stream can take barring limits imposed by the bandwidth estimate.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4c1d4-281"><strong>AppliedBandwidthSourceKey</strong></span><span class="sxs-lookup"><span data-stu-id="4c1d4-281"><strong>AppliedBandwidthSourceKey</strong></span></span></p></td>
<td><p><span data-ttu-id="4c1d4-282">smallint</span><span class="sxs-lookup"><span data-stu-id="4c1d4-282">smallint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="4c1d4-283">Essa é a origem do limite de largura de banda que está sendo imposto.</span><span class="sxs-lookup"><span data-stu-id="4c1d4-283">This is the source of the bandwidth cap being imposed.</span></span> <span data-ttu-id="4c1d4-284">Ele descreve onde o limite de largura de banda é proveniente de ("servidor de políticas", "Ativar servidor", "Janelarestritaidade" e assim por diante).</span><span class="sxs-lookup"><span data-stu-id="4c1d4-284">It describes where the bandwidth limit is coming from (“Policy Server”, “TURN Server”, “Modality”, and so on).</span></span> <span data-ttu-id="4c1d4-285">Referenciado pela <a href="lync-server-2013-appliedbandwidthsource-table.md">tabela AppliedBandwidthSource no Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="4c1d4-285">Referenced from the <a href="lync-server-2013-appliedbandwidthsource-table.md">AppliedBandwidthSource table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4c1d4-286"><strong>Chamador</strong></span><span class="sxs-lookup"><span data-stu-id="4c1d4-286"><strong>Caller</strong></span></span></p></td>
<td><p><span data-ttu-id="4c1d4-287">bit</span><span class="sxs-lookup"><span data-stu-id="4c1d4-287">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="4c1d4-288">Indica se as métricas do autor foram recebidas; 1 é sim, um valor nulo é não.</span><span class="sxs-lookup"><span data-stu-id="4c1d4-288">Indicates whether metrics from the caller were received; 1 is yes, a null value is no.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4c1d4-289"><strong>Receptor</strong></span><span class="sxs-lookup"><span data-stu-id="4c1d4-289"><strong>Callee</strong></span></span></p></td>
<td><p><span data-ttu-id="4c1d4-290">bit</span><span class="sxs-lookup"><span data-stu-id="4c1d4-290">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="4c1d4-291">Indica se as métricas do receptor da chamada foram recebidas; 1 é sim, um valor nulo é não.</span><span class="sxs-lookup"><span data-stu-id="4c1d4-291">Indicates whether metrics from the call receiver were received; 1 is yes, a null value is no.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4c1d4-292"><strong>MidCallReport</strong></span><span class="sxs-lookup"><span data-stu-id="4c1d4-292"><strong>MidCallReport</strong></span></span></p></td>
<td><p><span data-ttu-id="4c1d4-293">bit</span><span class="sxs-lookup"><span data-stu-id="4c1d4-293">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="4c1d4-294">Indica se o relatório é para uma parte da sessão ou para a sessão completa.</span><span class="sxs-lookup"><span data-stu-id="4c1d4-294">Indicates whether the report is for a portion of the session or for the complete session.</span></span></p>
<p><span data-ttu-id="4c1d4-295">Esta coluna foi introduzida no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="4c1d4-295">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4c1d4-296"><strong>ClassifiedPoorCall</strong></span><span class="sxs-lookup"><span data-stu-id="4c1d4-296"><strong>ClassifiedPoorCall</strong></span></span></p></td>
<td><p><span data-ttu-id="4c1d4-297">bit</span><span class="sxs-lookup"><span data-stu-id="4c1d4-297">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="4c1d4-298">Indica se uma chamada foi classificada como uma chamada ruim (valor 1) ou uma boa chamada (0).</span><span class="sxs-lookup"><span data-stu-id="4c1d4-298">Indicates whether a call was classified as a poor call (value of 1) or as a good call (0).</span></span></p>
<p><span data-ttu-id="4c1d4-299">Esta coluna foi introduzida no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="4c1d4-299">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4c1d4-300"><strong>CallerConnectivityICE</strong></span><span class="sxs-lookup"><span data-stu-id="4c1d4-300"><strong>CallerConnectivityICE</strong></span></span></p></td>
<td><p><span data-ttu-id="4c1d4-301">tinyInt</span><span class="sxs-lookup"><span data-stu-id="4c1d4-301">tinyInt</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="4c1d4-302">Indica se o chamador está conectado à rede usando o protocolo ICE (estabelecimento de conectividade com a Internet).</span><span class="sxs-lookup"><span data-stu-id="4c1d4-302">Indicates whether the caller connected to the network using the ICE protocol (Internet Connectivity Establishment).</span></span></p>
<p><span data-ttu-id="4c1d4-303">Esta coluna foi introduzida no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="4c1d4-303">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4c1d4-304"><strong>CalleeConnectivityICE</strong></span><span class="sxs-lookup"><span data-stu-id="4c1d4-304"><strong>CalleeConnectivityICE</strong></span></span></p></td>
<td><p><span data-ttu-id="4c1d4-305">tinyint</span><span class="sxs-lookup"><span data-stu-id="4c1d4-305">tinyint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="4c1d4-306">Indica se o chamador está conectado à rede usando o protocolo ICE (estabelecimento de conectividade com a Internet).</span><span class="sxs-lookup"><span data-stu-id="4c1d4-306">Indicates whether the caller connected to the network using the ICE protocol (Internet Connectivity Establishment).</span></span></p>
<p><span data-ttu-id="4c1d4-307">Esta coluna foi introduzida no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="4c1d4-307">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4c1d4-308"><strong>CallerReflexiveLocalIPAddr</strong></span><span class="sxs-lookup"><span data-stu-id="4c1d4-308"><strong>CallerReflexiveLocalIPAddr</strong></span></span></p></td>
<td><p><span data-ttu-id="4c1d4-309">int</span><span class="sxs-lookup"><span data-stu-id="4c1d4-309">int</span></span></p></td>
<td><p><span data-ttu-id="4c1d4-310">Exterior</span><span class="sxs-lookup"><span data-stu-id="4c1d4-310">Foreign</span></span></p></td>
<td><p><span data-ttu-id="4c1d4-311">Endereço IP reflexivo do usuário que fez a chamada.</span><span class="sxs-lookup"><span data-stu-id="4c1d4-311">Reflexive IP address of the user who placed the call.</span></span> <span data-ttu-id="4c1d4-312">Em organizações que usam NAT (Network Address Translation), o endereço IP reflexivo é o endereço IP do servidor proxy.</span><span class="sxs-lookup"><span data-stu-id="4c1d4-312">In organizations that use NAT (network address translation), the reflexive IP address is the IP address of the proxy server.</span></span></p>
<p><span data-ttu-id="4c1d4-313">Esta coluna foi introduzida no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="4c1d4-313">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4c1d4-314"><strong>CallerWiFiDriverDevicesDesc</strong></span><span class="sxs-lookup"><span data-stu-id="4c1d4-314"><strong>CallerWiFiDriverDevicesDesc</strong></span></span></p></td>
<td><p><span data-ttu-id="4c1d4-315">int</span><span class="sxs-lookup"><span data-stu-id="4c1d4-315">int</span></span></p></td>
<td><p><span data-ttu-id="4c1d4-316">Exterior</span><span class="sxs-lookup"><span data-stu-id="4c1d4-316">Foreign</span></span></p></td>
<td><p><span data-ttu-id="4c1d4-317">Descrição do dispositivo para o driver WiFi empregado pelo usuário que fez a chamada.</span><span class="sxs-lookup"><span data-stu-id="4c1d4-317">Device description for the WiFi driver employed by the user who placed the call.</span></span></p>
<p><span data-ttu-id="4c1d4-318">Esta coluna foi introduzida no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="4c1d4-318">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4c1d4-319"><strong>CallerWiFiDriverVersion</strong></span><span class="sxs-lookup"><span data-stu-id="4c1d4-319"><strong>CallerWiFiDriverVersion</strong></span></span></p></td>
<td><p><span data-ttu-id="4c1d4-320">int</span><span class="sxs-lookup"><span data-stu-id="4c1d4-320">int</span></span></p></td>
<td><p><span data-ttu-id="4c1d4-321">Exterior</span><span class="sxs-lookup"><span data-stu-id="4c1d4-321">Foreign</span></span></p></td>
<td><p><span data-ttu-id="4c1d4-322">Número da versão do driver WiFi empregado pelo usuário que fez a chamada.</span><span class="sxs-lookup"><span data-stu-id="4c1d4-322">Version number for the WiFi driver employed by the user who placed the call.</span></span></p>
<p><span data-ttu-id="4c1d4-323">Esta coluna foi introduzida no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="4c1d4-323">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4c1d4-324"><strong>CalleReflexiveLocalIPAddr</strong></span><span class="sxs-lookup"><span data-stu-id="4c1d4-324"><strong>CalleReflexiveLocalIPAddr</strong></span></span></p></td>
<td><p><span data-ttu-id="4c1d4-325">int</span><span class="sxs-lookup"><span data-stu-id="4c1d4-325">int</span></span></p></td>
<td><p><span data-ttu-id="4c1d4-326">Exterior</span><span class="sxs-lookup"><span data-stu-id="4c1d4-326">Foreign</span></span></p></td>
<td><p><span data-ttu-id="4c1d4-327">Endereço IP reflexivo do usuário que recebeu a chamada.</span><span class="sxs-lookup"><span data-stu-id="4c1d4-327">Reflexive IP address of the user who received the call.</span></span> <span data-ttu-id="4c1d4-328">Em organizações que usam NAT (Network Address Translation), o endereço IP reflexivo é o endereço IP do servidor proxy.</span><span class="sxs-lookup"><span data-stu-id="4c1d4-328">In organizations that use NAT (network address translation), the reflexive IP address is the IP address of the proxy server.</span></span></p>
<p><span data-ttu-id="4c1d4-329">Esta coluna foi introduzida no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="4c1d4-329">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4c1d4-330"><strong>CalleeWiFiDriverDevicesDesc</strong></span><span class="sxs-lookup"><span data-stu-id="4c1d4-330"><strong>CalleeWiFiDriverDevicesDesc</strong></span></span></p></td>
<td><p><span data-ttu-id="4c1d4-331">int</span><span class="sxs-lookup"><span data-stu-id="4c1d4-331">int</span></span></p></td>
<td><p><span data-ttu-id="4c1d4-332">Exterior</span><span class="sxs-lookup"><span data-stu-id="4c1d4-332">Foreign</span></span></p></td>
<td><p><span data-ttu-id="4c1d4-333">Descrição do dispositivo para o driver WiFi empregado pelo usuário que recebeu a chamada.</span><span class="sxs-lookup"><span data-stu-id="4c1d4-333">Device description for the WiFi driver employed by the user who received the call.</span></span></p>
<p><span data-ttu-id="4c1d4-334">Esta coluna foi introduzida no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="4c1d4-334">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4c1d4-335"><strong>CalleeWiFiDriverVersion</strong></span><span class="sxs-lookup"><span data-stu-id="4c1d4-335"><strong>CalleeWiFiDriverVersion</strong></span></span></p></td>
<td><p><span data-ttu-id="4c1d4-336">int</span><span class="sxs-lookup"><span data-stu-id="4c1d4-336">int</span></span></p></td>
<td><p><span data-ttu-id="4c1d4-337">Exterior</span><span class="sxs-lookup"><span data-stu-id="4c1d4-337">Foreign</span></span></p></td>
<td><p><span data-ttu-id="4c1d4-338">Número da versão do driver WiFi empregado pelo usuário que recebeu a chamada.</span><span class="sxs-lookup"><span data-stu-id="4c1d4-338">Version number for the WiFi driver employed by the user who received the call.</span></span></p>
<p><span data-ttu-id="4c1d4-339">Esta coluna foi introduzida no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="4c1d4-339">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

