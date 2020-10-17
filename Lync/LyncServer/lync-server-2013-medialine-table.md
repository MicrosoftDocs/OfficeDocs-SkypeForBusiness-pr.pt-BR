---
title: 'Lync Server 2013: tabela de mídia'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: MediaLine table
ms:assetid: 414b1d63-ae97-4c27-bac0-c9ad0f808ff0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425920(v=OCS.15)
ms:contentKeyID: 48183956
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 03f967b50c2fa9eae4f2599ce96dc9c592a57006
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48516138"
---
# <a name="medialine-table-in-lync-server-2013"></a><span data-ttu-id="4f1cb-102">Tabela de mídia no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4f1cb-102">MediaLine table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4f1cb-103">_**Última modificação do tópico:** 2014-02-21_</span><span class="sxs-lookup"><span data-stu-id="4f1cb-103">_**Topic Last Modified:** 2014-02-21_</span></span>

<span data-ttu-id="4f1cb-104">Cada registro representa uma linha de mídia.</span><span class="sxs-lookup"><span data-stu-id="4f1cb-104">Each record represents one media line.</span></span> <span data-ttu-id="4f1cb-105">(Uma sessão de áudio normalmente contém uma linha de mídia de áudio.</span><span class="sxs-lookup"><span data-stu-id="4f1cb-105">(One audio session usually contains one audio media line.</span></span> <span data-ttu-id="4f1cb-106">Uma sessão de áudio e vídeo (A/V) normalmente contém uma linha de mídia de áudio e uma linha de mídia de vídeo, embora a sessão possa conter duas linhas de mídia de vídeo se um dispositivo de conferência for usado ou se o modo de exibição de galeria for usado.</span><span class="sxs-lookup"><span data-stu-id="4f1cb-106">One audio and video (A/V) session usually contains one audio media line and one video media line, although the session might contain two video media lines if a conferencing device is used or if Gallery View is used.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="4f1cb-107"><strong>Coluna</strong></span><span class="sxs-lookup"><span data-stu-id="4f1cb-107"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="4f1cb-108"><strong>Tipo de dados</strong></span><span class="sxs-lookup"><span data-stu-id="4f1cb-108"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="4f1cb-109"><strong>Chave/índice</strong></span><span class="sxs-lookup"><span data-stu-id="4f1cb-109"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="4f1cb-110"><strong>Detalhes</strong></span><span class="sxs-lookup"><span data-stu-id="4f1cb-110"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="4f1cb-111"><strong>ConferenceDateTime</strong></span><span class="sxs-lookup"><span data-stu-id="4f1cb-111"><strong>ConferenceDateTime</strong></span></span></p></td>
<td><p><span data-ttu-id="4f1cb-112">datetime</span><span class="sxs-lookup"><span data-stu-id="4f1cb-112">datetime</span></span></p></td>
<td><p><span data-ttu-id="4f1cb-113">Primário</span><span class="sxs-lookup"><span data-stu-id="4f1cb-113">Primary</span></span></p></td>
<td><p><span data-ttu-id="4f1cb-114">Referenciado da <a href="lync-server-2013-session-table.md">tabela de sessão no Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="4f1cb-114">Referenced from the <a href="lync-server-2013-session-table.md">Session table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4f1cb-115"><strong>SessionSeq</strong></span><span class="sxs-lookup"><span data-stu-id="4f1cb-115"><strong>SessionSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="4f1cb-116">int</span><span class="sxs-lookup"><span data-stu-id="4f1cb-116">int</span></span></p></td>
<td><p><span data-ttu-id="4f1cb-117">Primário</span><span class="sxs-lookup"><span data-stu-id="4f1cb-117">Primary</span></span></p></td>
<td><p><span data-ttu-id="4f1cb-118">Referenciado da <a href="lync-server-2013-session-table.md">tabela de sessão no Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="4f1cb-118">Referenced from the <a href="lync-server-2013-session-table.md">Session table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4f1cb-119"><strong>MediaLineLabel</strong></span><span class="sxs-lookup"><span data-stu-id="4f1cb-119"><strong>MediaLineLabel</strong></span></span></p></td>
<td><p><span data-ttu-id="4f1cb-120">tinyint</span><span class="sxs-lookup"><span data-stu-id="4f1cb-120">tinyint</span></span></p></td>
<td><p><span data-ttu-id="4f1cb-121">Primário</span><span class="sxs-lookup"><span data-stu-id="4f1cb-121">Primary</span></span></p></td>
<td><p><span data-ttu-id="4f1cb-122">0 é o áudio principal, 1 é o vídeo principal e 2 é o vídeo panorâmico, 3 é o compartilhamento de aplicativo/área de trabalho.</span><span class="sxs-lookup"><span data-stu-id="4f1cb-122">0 is main audio, 1 is main video, and 2 is panoramic video, 3 is Application/Desktop Sharing.</span></span> <span data-ttu-id="4f1cb-123">Este rótulo deve ser exclusivo em uma única sessão.</span><span class="sxs-lookup"><span data-stu-id="4f1cb-123">This label must be unique within a single session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4f1cb-124"><strong>ConnectivityIce</strong></span><span class="sxs-lookup"><span data-stu-id="4f1cb-124"><strong>ConnectivityIce</strong></span></span></p></td>
<td><p><span data-ttu-id="4f1cb-125">tinyint</span><span class="sxs-lookup"><span data-stu-id="4f1cb-125">tinyint</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="4f1cb-126">Esta coluna está presente, mas não é usada no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="4f1cb-126">This column is present but not used in Microsoft Lync Server 2013.</span></span> <span data-ttu-id="4f1cb-127">As informações sobre a conectividade usada para uma linha de mídia são capturadas nas colunas CallerConnectivityICE e CalleeConnectivityICE.</span><span class="sxs-lookup"><span data-stu-id="4f1cb-127">Information about the connectivity used for a media line is captured in the CallerConnectivityICE and CalleeConnectivityICE columns.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4f1cb-128"><strong>CallerIceWarningFlags</strong></span><span class="sxs-lookup"><span data-stu-id="4f1cb-128"><strong>CallerIceWarningFlags</strong></span></span></p></td>
<td><p><span data-ttu-id="4f1cb-129">int</span><span class="sxs-lookup"><span data-stu-id="4f1cb-129">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="4f1cb-130">Informações sobre o processo de estabelecimento de conectividade interativa (ICE) descrito em sinalizadores de bits.</span><span class="sxs-lookup"><span data-stu-id="4f1cb-130">Information about Interactive Connectivity Establishment (ICE) process described in bits flags.</span></span> <span data-ttu-id="4f1cb-131">Para obter detalhes, consulte a <em>especificação de protocolo do Monitoring Server de qualidade da experiência</em>, disponível para download.</span><span class="sxs-lookup"><span data-stu-id="4f1cb-131">For details, refer to the <em>Quality of Experience Monitoring Server Protocol Specification</em>, available for download.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4f1cb-132"><strong>CalleeIceWarningFlags</strong></span><span class="sxs-lookup"><span data-stu-id="4f1cb-132"><strong>CalleeIceWarningFlags</strong></span></span></p></td>
<td><p><span data-ttu-id="4f1cb-133">int</span><span class="sxs-lookup"><span data-stu-id="4f1cb-133">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="4f1cb-134">O mesmo que CallerIceWarningFlags, mas no lado do receptor.</span><span class="sxs-lookup"><span data-stu-id="4f1cb-134">Same as CallerIceWarningFlags, but on the callee side.</span></span> <span data-ttu-id="4f1cb-135">Para obter detalhes, consulte a <em>especificação de protocolo do Monitoring Server de qualidade da experiência</em>, disponível para download.</span><span class="sxs-lookup"><span data-stu-id="4f1cb-135">For details, refer to the <em>Quality of Experience Monitoring Server Protocol Specification</em>, available for download.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4f1cb-136"><strong>Segurança</strong></span><span class="sxs-lookup"><span data-stu-id="4f1cb-136"><strong>Security</strong></span></span></p></td>
<td><p><span data-ttu-id="4f1cb-137">tinyint</span><span class="sxs-lookup"><span data-stu-id="4f1cb-137">tinyint</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="4f1cb-138">O perfil de segurança em uso.</span><span class="sxs-lookup"><span data-stu-id="4f1cb-138">The security profile in use.</span></span> <span data-ttu-id="4f1cb-139">0 é NONE (nenhum), 1 é SRTP, 2 é V1.</span><span class="sxs-lookup"><span data-stu-id="4f1cb-139">0 is NONE, 1 is SRTP, 2 is V1.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4f1cb-140"><strong>Transport</strong></span><span class="sxs-lookup"><span data-stu-id="4f1cb-140"><strong>Transport</strong></span></span></p></td>
<td><p><span data-ttu-id="4f1cb-141">tinyint</span><span class="sxs-lookup"><span data-stu-id="4f1cb-141">tinyint</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="4f1cb-142">0 é UDP, 1 é TCP.</span><span class="sxs-lookup"><span data-stu-id="4f1cb-142">0 is UDP, 1 is TCP.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4f1cb-143"><strong>CallerIPAddr</strong></span><span class="sxs-lookup"><span data-stu-id="4f1cb-143"><strong>CallerIPAddr</strong></span></span></p></td>
<td><p><span data-ttu-id="4f1cb-144">int</span><span class="sxs-lookup"><span data-stu-id="4f1cb-144">int</span></span></p></td>
<td><p><span data-ttu-id="4f1cb-145">Estrangeira</span><span class="sxs-lookup"><span data-stu-id="4f1cb-145">Foreign</span></span></p></td>
<td><p><span data-ttu-id="4f1cb-146">Endereço IP do chamador.</span><span class="sxs-lookup"><span data-stu-id="4f1cb-146">IP Address of the caller.</span></span> <span data-ttu-id="4f1cb-147">Consulte a <a href="lync-server-2013-ipaddress-table.md">tabela IPAddress no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="4f1cb-147">See the <a href="lync-server-2013-ipaddress-table.md">IPAddress table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4f1cb-148"><strong>CallerPort</strong></span><span class="sxs-lookup"><span data-stu-id="4f1cb-148"><strong>CallerPort</strong></span></span></p></td>
<td><p><span data-ttu-id="4f1cb-149">int</span><span class="sxs-lookup"><span data-stu-id="4f1cb-149">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="4f1cb-150">Porta usada pelo chamador.</span><span class="sxs-lookup"><span data-stu-id="4f1cb-150">Port used by the caller.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4f1cb-151"><strong>CallerSubnet</strong></span><span class="sxs-lookup"><span data-stu-id="4f1cb-151"><strong>CallerSubnet</strong></span></span></p></td>
<td><p><span data-ttu-id="4f1cb-152">int</span><span class="sxs-lookup"><span data-stu-id="4f1cb-152">int</span></span></p></td>
<td><p><span data-ttu-id="4f1cb-153"> Estrangeira</span><span class="sxs-lookup"><span data-stu-id="4f1cb-153"> Foreign</span></span></p></td>
<td><p><span data-ttu-id="4f1cb-154">A sub-rede do chamador.</span><span class="sxs-lookup"><span data-stu-id="4f1cb-154">The subnet of the caller.</span></span> <span data-ttu-id="4f1cb-155">Consulte a <a href="lync-server-2013-ipaddress-table.md">tabela IPAddress no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="4f1cb-155">See the <a href="lync-server-2013-ipaddress-table.md">IPAddress table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4f1cb-156"><strong>CallerInside</strong></span><span class="sxs-lookup"><span data-stu-id="4f1cb-156"><strong>CallerInside</strong></span></span></p></td>
<td><p><span data-ttu-id="4f1cb-157">bits</span><span class="sxs-lookup"><span data-stu-id="4f1cb-157">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="4f1cb-158">1 significa que o chamador está dentro da rede da empresa, 0 significa que o chamador está fora da rede.</span><span class="sxs-lookup"><span data-stu-id="4f1cb-158">1 means caller is inside the enterprise network, 0 means the caller is outside the network.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4f1cb-159"><strong>CallerMacAddress</strong></span><span class="sxs-lookup"><span data-stu-id="4f1cb-159"><strong>CallerMacAddress</strong></span></span></p></td>
<td><p><span data-ttu-id="4f1cb-160">int</span><span class="sxs-lookup"><span data-stu-id="4f1cb-160">int</span></span></p></td>
<td><p><span data-ttu-id="4f1cb-161">Estrangeira</span><span class="sxs-lookup"><span data-stu-id="4f1cb-161">Foreign</span></span></p></td>
<td><p><span data-ttu-id="4f1cb-162">Endereço MAC do chamador, referenciado da <a href="lync-server-2013-macaddress-table.md">tabela MACAddress no Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="4f1cb-162">Caller’s mac address, referenced from <a href="lync-server-2013-macaddress-table.md">MacAddress table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4f1cb-163"><strong>CallerRelayIPAddr</strong></span><span class="sxs-lookup"><span data-stu-id="4f1cb-163"><strong>CallerRelayIPAddr</strong></span></span></p></td>
<td><p><span data-ttu-id="4f1cb-164">int</span><span class="sxs-lookup"><span data-stu-id="4f1cb-164">int</span></span></p></td>
<td><p><span data-ttu-id="4f1cb-165">Estrangeira</span><span class="sxs-lookup"><span data-stu-id="4f1cb-165">Foreign</span></span></p></td>
<td><p><span data-ttu-id="4f1cb-166">Endereço IP do serviço de borda a/V do Lync Server usado pelo chamador.</span><span class="sxs-lookup"><span data-stu-id="4f1cb-166">IP Address of the Lync Server A/V Edge service used by the caller.</span></span> <span data-ttu-id="4f1cb-167">Consulte a <a href="lync-server-2013-ipaddress-table.md">tabela IPAddress no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="4f1cb-167">See the <a href="lync-server-2013-ipaddress-table.md">IPAddress table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4f1cb-168"><strong>CallerRelayPort</strong></span><span class="sxs-lookup"><span data-stu-id="4f1cb-168"><strong>CallerRelayPort</strong></span></span></p></td>
<td><p><span data-ttu-id="4f1cb-169">int</span><span class="sxs-lookup"><span data-stu-id="4f1cb-169">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="4f1cb-170">Porta usada no serviço de borda A/V pelo chamador.</span><span class="sxs-lookup"><span data-stu-id="4f1cb-170">Port used on the A/V Edge service by the caller.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4f1cb-171"><strong>CallerCaptureDev</strong></span><span class="sxs-lookup"><span data-stu-id="4f1cb-171"><strong>CallerCaptureDev</strong></span></span></p></td>
<td><p><span data-ttu-id="4f1cb-172">int</span><span class="sxs-lookup"><span data-stu-id="4f1cb-172">int</span></span></p></td>
<td><p><span data-ttu-id="4f1cb-173">Estrangeira</span><span class="sxs-lookup"><span data-stu-id="4f1cb-173">Foreign</span></span></p></td>
<td><p><span data-ttu-id="4f1cb-174">Dispositivo de captura usado pelo chamador.</span><span class="sxs-lookup"><span data-stu-id="4f1cb-174">Capture device used by the caller.</span></span> <span data-ttu-id="4f1cb-175">Referenciado da <a href="lync-server-2013-device-table.md">tabela Device no Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="4f1cb-175">Referenced from the <a href="lync-server-2013-device-table.md">Device table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4f1cb-176"><strong>CallerRenderDev</strong></span><span class="sxs-lookup"><span data-stu-id="4f1cb-176"><strong>CallerRenderDev</strong></span></span></p></td>
<td><p><span data-ttu-id="4f1cb-177">int</span><span class="sxs-lookup"><span data-stu-id="4f1cb-177">int</span></span></p></td>
<td><p><span data-ttu-id="4f1cb-178">Estrangeira</span><span class="sxs-lookup"><span data-stu-id="4f1cb-178">Foreign</span></span></p></td>
<td><p><span data-ttu-id="4f1cb-179">Dispositivo de renderização usado pelo chamador.</span><span class="sxs-lookup"><span data-stu-id="4f1cb-179">Render device used by caller.</span></span> <span data-ttu-id="4f1cb-180">Referenciado da <a href="lync-server-2013-device-table.md">tabela Device no Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="4f1cb-180">Referenced from the <a href="lync-server-2013-device-table.md">Device table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4f1cb-181"><strong>CallerCaptureDevDriver</strong></span><span class="sxs-lookup"><span data-stu-id="4f1cb-181"><strong>CallerCaptureDevDriver</strong></span></span></p></td>
<td><p><span data-ttu-id="4f1cb-182">int</span><span class="sxs-lookup"><span data-stu-id="4f1cb-182">int</span></span></p></td>
<td><p><span data-ttu-id="4f1cb-183">Estrangeira</span><span class="sxs-lookup"><span data-stu-id="4f1cb-183">Foreign</span></span></p></td>
<td><p><span data-ttu-id="4f1cb-184">Driver do dispositivo de captura do chamador, referenciado na <a href="lync-server-2013-devicedriver-table.md">tabela DeviceDriver no Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="4f1cb-184">Driver for the caller’s capture device, referenced from the <a href="lync-server-2013-devicedriver-table.md">DeviceDriver table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4f1cb-185"><strong>CallerRenderDevDriver</strong></span><span class="sxs-lookup"><span data-stu-id="4f1cb-185"><strong>CallerRenderDevDriver</strong></span></span></p></td>
<td><p><span data-ttu-id="4f1cb-186">int</span><span class="sxs-lookup"><span data-stu-id="4f1cb-186">int</span></span></p></td>
<td><p><span data-ttu-id="4f1cb-187">Estrangeira</span><span class="sxs-lookup"><span data-stu-id="4f1cb-187">Foreign</span></span></p></td>
<td><p><span data-ttu-id="4f1cb-188">Driver do dispositivo de renderização do chamador, referenciado da <a href="lync-server-2013-devicedriver-table.md">tabela DeviceDriver no Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="4f1cb-188">Driver for the caller’s render device, referenced from the <a href="lync-server-2013-devicedriver-table.md">DeviceDriver table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4f1cb-189"><strong>CallerNetworkConnectionType</strong></span><span class="sxs-lookup"><span data-stu-id="4f1cb-189"><strong>CallerNetworkConnectionType</strong></span></span></p></td>
<td><p><span data-ttu-id="4f1cb-190">tinyint</span><span class="sxs-lookup"><span data-stu-id="4f1cb-190">tinyint</span></span></p></td>
<td><p><span data-ttu-id="4f1cb-191">Estrangeira</span><span class="sxs-lookup"><span data-stu-id="4f1cb-191">Foreign</span></span></p></td>
<td><p><span data-ttu-id="4f1cb-192">Indica como o chamador se conectou à rede.</span><span class="sxs-lookup"><span data-stu-id="4f1cb-192">Indicates how the caller connected to the network.</span></span> <span data-ttu-id="4f1cb-193">Os valores são obtidos da <a href="lync-server-2013-networkconnectiondetail-table.md">tabela NetworkConnectionDetail no Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="4f1cb-193">Values are obtained from the <a href="lync-server-2013-networkconnectiondetail-table.md">NetworkConnectionDetail table in Lync Server 2013</a>.</span></span> <span data-ttu-id="4f1cb-194">Os valores típicos são 0 para uma conexão com fio ' 1 para uma conexão WiFi; e 3 para uma conexão Ethernet.</span><span class="sxs-lookup"><span data-stu-id="4f1cb-194">Typical values are 0 for a wired connection’ 1 for a WiFi connection; and 3 for an Ethernet connection.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4f1cb-195"><strong>CallerBssid</strong></span><span class="sxs-lookup"><span data-stu-id="4f1cb-195"><strong>CallerBssid</strong></span></span></p></td>
<td><p><span data-ttu-id="4f1cb-196">int</span><span class="sxs-lookup"><span data-stu-id="4f1cb-196">int</span></span></p></td>
<td><p><span data-ttu-id="4f1cb-197">Estrangeira</span><span class="sxs-lookup"><span data-stu-id="4f1cb-197">Foreign</span></span></p></td>
<td><p><span data-ttu-id="4f1cb-198">BSSID do chamador se for usado sem fio.</span><span class="sxs-lookup"><span data-stu-id="4f1cb-198">Caller’s BSSID if wireless is used.</span></span> <span data-ttu-id="4f1cb-199">Referenciado da <a href="lync-server-2013-macaddress-table.md">tabela MACAddress no Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="4f1cb-199">Referenced from <a href="lync-server-2013-macaddress-table.md">MacAddress table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4f1cb-200"><strong>CallerVPN</strong></span><span class="sxs-lookup"><span data-stu-id="4f1cb-200"><strong>CallerVPN</strong></span></span></p></td>
<td><p><span data-ttu-id="4f1cb-201">bits</span><span class="sxs-lookup"><span data-stu-id="4f1cb-201">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="4f1cb-202">O link do chamador.</span><span class="sxs-lookup"><span data-stu-id="4f1cb-202">The caller's link.</span></span> <span data-ttu-id="4f1cb-203">1 é para rede virtual privada (VPN), 0 é para não-VPN.</span><span class="sxs-lookup"><span data-stu-id="4f1cb-203">1 is virtual private network (VPN), 0 is non-VPN.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4f1cb-204"><strong>CallerLinkSpeed</strong></span><span class="sxs-lookup"><span data-stu-id="4f1cb-204"><strong>CallerLinkSpeed</strong></span></span></p></td>
<td><p><span data-ttu-id="4f1cb-205">decimal (18, 0)</span><span class="sxs-lookup"><span data-stu-id="4f1cb-205">decimal(18,0)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="4f1cb-206">A velocidade do link de rede, em bps, para o ponto de extremidade do chamador.</span><span class="sxs-lookup"><span data-stu-id="4f1cb-206">The network link speed, in bps, for the caller's endpoint.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4f1cb-207"><strong>CalleeIPAddr</strong></span><span class="sxs-lookup"><span data-stu-id="4f1cb-207"><strong>CalleeIPAddr</strong></span></span></p></td>
<td><p><span data-ttu-id="4f1cb-208">int</span><span class="sxs-lookup"><span data-stu-id="4f1cb-208">int</span></span></p></td>
<td><p><span data-ttu-id="4f1cb-209">Estrangeira</span><span class="sxs-lookup"><span data-stu-id="4f1cb-209">Foreign</span></span></p></td>
<td><p><span data-ttu-id="4f1cb-210">Endereço IP do receptor de chamada.</span><span class="sxs-lookup"><span data-stu-id="4f1cb-210">IP Address of the call receiver.</span></span> <span data-ttu-id="4f1cb-211">Consulte a <a href="lync-server-2013-ipaddress-table.md">tabela IPAddress no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="4f1cb-211">See the <a href="lync-server-2013-ipaddress-table.md">IPAddress table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4f1cb-212"><strong>CalleePort</strong></span><span class="sxs-lookup"><span data-stu-id="4f1cb-212"><strong>CalleePort</strong></span></span></p></td>
<td><p><span data-ttu-id="4f1cb-213">bits</span><span class="sxs-lookup"><span data-stu-id="4f1cb-213">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="4f1cb-214">Porta usada pelo receptor de chamada.</span><span class="sxs-lookup"><span data-stu-id="4f1cb-214">Port used by the call receiver.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4f1cb-215"><strong>CalleeSubnet</strong></span><span class="sxs-lookup"><span data-stu-id="4f1cb-215"><strong>CalleeSubnet</strong></span></span></p></td>
<td><p><span data-ttu-id="4f1cb-216">int</span><span class="sxs-lookup"><span data-stu-id="4f1cb-216">int</span></span></p></td>
<td><p><span data-ttu-id="4f1cb-217">Estrangeira</span><span class="sxs-lookup"><span data-stu-id="4f1cb-217">Foreign</span></span></p></td>
<td><p><span data-ttu-id="4f1cb-218">Sub-rede do receptor.</span><span class="sxs-lookup"><span data-stu-id="4f1cb-218">Subnet of callee.</span></span> <span data-ttu-id="4f1cb-219">Consulte a <a href="lync-server-2013-ipaddress-table.md">tabela IPAddress no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="4f1cb-219">See the <a href="lync-server-2013-ipaddress-table.md">IPAddress table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4f1cb-220"><strong>CalleeInside</strong></span><span class="sxs-lookup"><span data-stu-id="4f1cb-220"><strong>CalleeInside</strong></span></span></p></td>
<td><p><span data-ttu-id="4f1cb-221">bits</span><span class="sxs-lookup"><span data-stu-id="4f1cb-221">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="4f1cb-222">1 significa que o receptor de chamada está dentro da rede corporativa, 0 significa que o receptor de chamadas está fora da rede.</span><span class="sxs-lookup"><span data-stu-id="4f1cb-222">1 means call receiver is inside the enterprise network, 0 means the call receiver is outside the network.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4f1cb-223"><strong>CalleeMacAddress</strong></span><span class="sxs-lookup"><span data-stu-id="4f1cb-223"><strong>CalleeMacAddress</strong></span></span></p></td>
<td><p><span data-ttu-id="4f1cb-224">int</span><span class="sxs-lookup"><span data-stu-id="4f1cb-224">int</span></span></p></td>
<td><p><span data-ttu-id="4f1cb-225">Estrangeira</span><span class="sxs-lookup"><span data-stu-id="4f1cb-225">Foreign</span></span></p></td>
<td><p><span data-ttu-id="4f1cb-226">Endereço MAC do receptor.</span><span class="sxs-lookup"><span data-stu-id="4f1cb-226">Callee Mac address.</span></span> <span data-ttu-id="4f1cb-227">Referenciado da <a href="lync-server-2013-macaddress-table.md">tabela MACAddress no Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="4f1cb-227">Referenced from the <a href="lync-server-2013-macaddress-table.md">MacAddress table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4f1cb-228"><strong>CalleeRelayIPAddr</strong></span><span class="sxs-lookup"><span data-stu-id="4f1cb-228"><strong>CalleeRelayIPAddr</strong></span></span></p></td>
<td><p><span data-ttu-id="4f1cb-229">int</span><span class="sxs-lookup"><span data-stu-id="4f1cb-229">int</span></span></p></td>
<td><p><span data-ttu-id="4f1cb-230">Estrangeira</span><span class="sxs-lookup"><span data-stu-id="4f1cb-230">Foreign</span></span></p></td>
<td><p><span data-ttu-id="4f1cb-231">Endereço IP do serviço de borda A/V usado pelo receptor de chamada.</span><span class="sxs-lookup"><span data-stu-id="4f1cb-231">IP Address of the A/V Edge service used by the call receiver.</span></span> <span data-ttu-id="4f1cb-232">Consulte a <a href="lync-server-2013-ipaddress-table.md">tabela IPAddress no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="4f1cb-232">See the <a href="lync-server-2013-ipaddress-table.md">IPAddress table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4f1cb-233"><strong>CalleeRelayPort</strong></span><span class="sxs-lookup"><span data-stu-id="4f1cb-233"><strong>CalleeRelayPort</strong></span></span></p></td>
<td><p><span data-ttu-id="4f1cb-234">int</span><span class="sxs-lookup"><span data-stu-id="4f1cb-234">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="4f1cb-235">Porta usada no serviço de borda A/V pelo receptor de chamada.</span><span class="sxs-lookup"><span data-stu-id="4f1cb-235">Port used on the A/V Edge Service by the call receiver.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4f1cb-236"><strong>CalleeCaptureDev</strong></span><span class="sxs-lookup"><span data-stu-id="4f1cb-236"><strong>CalleeCaptureDev</strong></span></span></p></td>
<td><p><span data-ttu-id="4f1cb-237">int</span><span class="sxs-lookup"><span data-stu-id="4f1cb-237">int</span></span></p></td>
<td><p><span data-ttu-id="4f1cb-238">estrangeira</span><span class="sxs-lookup"><span data-stu-id="4f1cb-238">foreign</span></span></p></td>
<td><p><span data-ttu-id="4f1cb-239">Dispositivo de captura usado pelo receptor de chamada.</span><span class="sxs-lookup"><span data-stu-id="4f1cb-239">Capture device used by the call receiver.</span></span> <span data-ttu-id="4f1cb-240">Referenciado da <a href="lync-server-2013-device-table.md">tabela Device no Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="4f1cb-240">Referenced from the <a href="lync-server-2013-device-table.md">Device table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4f1cb-241"><strong>CalleeRenderDev</strong></span><span class="sxs-lookup"><span data-stu-id="4f1cb-241"><strong>CalleeRenderDev</strong></span></span></p></td>
<td><p><span data-ttu-id="4f1cb-242">int</span><span class="sxs-lookup"><span data-stu-id="4f1cb-242">int</span></span></p></td>
<td><p><span data-ttu-id="4f1cb-243">Estrangeira</span><span class="sxs-lookup"><span data-stu-id="4f1cb-243">Foreign</span></span></p></td>
<td><p><span data-ttu-id="4f1cb-244">Dispositivo de renderização usado pelo receptor de chamada.</span><span class="sxs-lookup"><span data-stu-id="4f1cb-244">Render device used by the call receiver.</span></span> <span data-ttu-id="4f1cb-245">Referenciado da <a href="lync-server-2013-device-table.md">tabela Device no Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="4f1cb-245">Referenced from the <a href="lync-server-2013-device-table.md">Device table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4f1cb-246"><strong>CalleeCaptureDevDriver</strong></span><span class="sxs-lookup"><span data-stu-id="4f1cb-246"><strong>CalleeCaptureDevDriver</strong></span></span></p></td>
<td><p><span data-ttu-id="4f1cb-247">int</span><span class="sxs-lookup"><span data-stu-id="4f1cb-247">int</span></span></p></td>
<td><p><span data-ttu-id="4f1cb-248">Estrangeira</span><span class="sxs-lookup"><span data-stu-id="4f1cb-248">Foreign</span></span></p></td>
<td><p><span data-ttu-id="4f1cb-249">Driver do dispositivo de captura do receptor de chamada.</span><span class="sxs-lookup"><span data-stu-id="4f1cb-249">Driver for the call receiver’s capture device.</span></span> <span data-ttu-id="4f1cb-250">Referenciado da <a href="lync-server-2013-devicedriver-table.md">tabela DeviceDriver no Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="4f1cb-250">Referenced from <a href="lync-server-2013-devicedriver-table.md">DeviceDriver table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4f1cb-251"><strong>CalleeRenderDevDriver</strong></span><span class="sxs-lookup"><span data-stu-id="4f1cb-251"><strong>CalleeRenderDevDriver</strong></span></span></p></td>
<td><p><span data-ttu-id="4f1cb-252">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="4f1cb-252">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="4f1cb-253">Estrangeira</span><span class="sxs-lookup"><span data-stu-id="4f1cb-253">Foreign</span></span></p></td>
<td><p><span data-ttu-id="4f1cb-254">Driver para o dispositivo de renderização do receptor de chamada.</span><span class="sxs-lookup"><span data-stu-id="4f1cb-254">Driver for the call receiver’s render device.</span></span> <span data-ttu-id="4f1cb-255">Referenciado da <a href="lync-server-2013-devicedriver-table.md">tabela DeviceDriver no Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="4f1cb-255">Referenced from <a href="lync-server-2013-devicedriver-table.md">DeviceDriver table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4f1cb-256"><strong>CalleeNetworkConnectionType</strong></span><span class="sxs-lookup"><span data-stu-id="4f1cb-256"><strong>CalleeNetworkConnectionType</strong></span></span></p></td>
<td><p><span data-ttu-id="4f1cb-257">tinyint</span><span class="sxs-lookup"><span data-stu-id="4f1cb-257">tinyint</span></span></p></td>
<td><p><span data-ttu-id="4f1cb-258">Estrangeira</span><span class="sxs-lookup"><span data-stu-id="4f1cb-258">Foreign</span></span></p></td>
<td><p><span data-ttu-id="4f1cb-259">Indica como o receptor está conectado à rede.</span><span class="sxs-lookup"><span data-stu-id="4f1cb-259">Indicates how the callee connected to the network.</span></span> <span data-ttu-id="4f1cb-260">Os valores são obtidos da <a href="lync-server-2013-networkconnectiondetail-table.md">tabela NetworkConnectionDetail no Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="4f1cb-260">Values are obtained from the <a href="lync-server-2013-networkconnectiondetail-table.md">NetworkConnectionDetail table in Lync Server 2013</a>.</span></span> <span data-ttu-id="4f1cb-261">Os valores típicos são 0 para uma conexão com fio ' 1 para uma conexão WiFi; e 3 para uma conexão Ethernet.</span><span class="sxs-lookup"><span data-stu-id="4f1cb-261">Typical values are 0 for a wired connection’ 1 for a WiFi connection; and 3 for an Ethernet connection.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4f1cb-262"><strong>CalleeBssid</strong></span><span class="sxs-lookup"><span data-stu-id="4f1cb-262"><strong>CalleeBssid</strong></span></span></p></td>
<td><p><span data-ttu-id="4f1cb-263">int</span><span class="sxs-lookup"><span data-stu-id="4f1cb-263">int</span></span></p></td>
<td><p><span data-ttu-id="4f1cb-264">Estrangeira</span><span class="sxs-lookup"><span data-stu-id="4f1cb-264">Foreign</span></span></p></td>
<td><p><span data-ttu-id="4f1cb-265">BSSID do receptor da chamada se for usado sem fio.</span><span class="sxs-lookup"><span data-stu-id="4f1cb-265">Callee’s BSSID if wireless is used.</span></span> <span data-ttu-id="4f1cb-266">Referenciado da <a href="lync-server-2013-macaddress-table.md">tabela MACAddress no Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="4f1cb-266">Referenced from <a href="lync-server-2013-macaddress-table.md">MacAddress table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4f1cb-267"><strong>CalleeVPN</strong></span><span class="sxs-lookup"><span data-stu-id="4f1cb-267"><strong>CalleeVPN</strong></span></span></p></td>
<td><p><span data-ttu-id="4f1cb-268">bits</span><span class="sxs-lookup"><span data-stu-id="4f1cb-268">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="4f1cb-269">O link do receptor de chamada; 1 é VPN (rede virtual privada), 0 não é VPN.</span><span class="sxs-lookup"><span data-stu-id="4f1cb-269">The call receiver’s link; 1 is virtual private network (VPN), 0 is non-VPN.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4f1cb-270"><strong>CalleeLinkSpeed</strong></span><span class="sxs-lookup"><span data-stu-id="4f1cb-270"><strong>CalleeLinkSpeed</strong></span></span></p></td>
<td><p><span data-ttu-id="4f1cb-271">decimal (18, 0)</span><span class="sxs-lookup"><span data-stu-id="4f1cb-271">decimal(18,0)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="4f1cb-272">A velocidade do link de rede, em bps, para o ponto de extremidade do receptor de chamada.</span><span class="sxs-lookup"><span data-stu-id="4f1cb-272">The network link speed, in bps, for the call receiver’s endpoint.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4f1cb-273"><strong>ConversationalMOS</strong></span><span class="sxs-lookup"><span data-stu-id="4f1cb-273"><strong>ConversationalMOS</strong></span></span></p></td>
<td><p><span data-ttu-id="4f1cb-274">decimal (3, 2)</span><span class="sxs-lookup"><span data-stu-id="4f1cb-274">decimal(3,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="4f1cb-275">MOS da Conversa de Banda Estreita das sessões de áudio (com base nos dois fluxos de áudio).</span><span class="sxs-lookup"><span data-stu-id="4f1cb-275">Narrowband Conversational MOS of the audio sessions (based on both audio streams).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4f1cb-276"><strong>AppliedBandwidthLimit</strong></span><span class="sxs-lookup"><span data-stu-id="4f1cb-276"><strong>AppliedBandwidthLimit</strong></span></span></p></td>
<td><p><span data-ttu-id="4f1cb-277">int</span><span class="sxs-lookup"><span data-stu-id="4f1cb-277">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="4f1cb-278">Esta é a largura de banda real aplicada ao fluxo de envio enviado fornecido por várias configurações de política (TURN, API, SDP, servidor de política e assim por diante).</span><span class="sxs-lookup"><span data-stu-id="4f1cb-278">This is the actual bandwidth applied to the given send side stream given various policy settings (TURN, API, SDP, Policy Server, and so on).</span></span> <span data-ttu-id="4f1cb-279">Isso não deve ser confundido com a largura de banda efetiva porque pode haver uma largura de banda efetiva menor com base na estimativa de largura de banda.</span><span class="sxs-lookup"><span data-stu-id="4f1cb-279">This is not to be confused with the effective bandwidth because there can be a lower effective bandwidth based on the bandwidth estimate.</span></span> <span data-ttu-id="4f1cb-280">Esta é basicamente a largura de banda máxima que o stream de envio pode utilizar dos limites impostos pela estimativa de largura de banda.</span><span class="sxs-lookup"><span data-stu-id="4f1cb-280">This is basically the maximum bandwidth the send stream can take barring limits imposed by the bandwidth estimate.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4f1cb-281"><strong>AppliedBandwidthSourceKey</strong></span><span class="sxs-lookup"><span data-stu-id="4f1cb-281"><strong>AppliedBandwidthSourceKey</strong></span></span></p></td>
<td><p><span data-ttu-id="4f1cb-282">smallint</span><span class="sxs-lookup"><span data-stu-id="4f1cb-282">smallint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="4f1cb-283">Essa é a origem do cap de largura de banda que está sendo imposto.</span><span class="sxs-lookup"><span data-stu-id="4f1cb-283">This is the source of the bandwidth cap being imposed.</span></span> <span data-ttu-id="4f1cb-284">Descreve de onde o limite de largura de banda está vindo ("servidor de política", "Ativar servidor", "modalidade" e assim por diante).</span><span class="sxs-lookup"><span data-stu-id="4f1cb-284">It describes where the bandwidth limit is coming from (“Policy Server”, “TURN Server”, “Modality”, and so on).</span></span> <span data-ttu-id="4f1cb-285">Referenciado da <a href="lync-server-2013-appliedbandwidthsource-table.md">tabela AppliedBandwidthSource no Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="4f1cb-285">Referenced from the <a href="lync-server-2013-appliedbandwidthsource-table.md">AppliedBandwidthSource table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4f1cb-286"><strong>Caller</strong></span><span class="sxs-lookup"><span data-stu-id="4f1cb-286"><strong>Caller</strong></span></span></p></td>
<td><p><span data-ttu-id="4f1cb-287">bits</span><span class="sxs-lookup"><span data-stu-id="4f1cb-287">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="4f1cb-288">Indica se as métricas do chamador foram recebidas; 1 é sim, um valor nulo é não.</span><span class="sxs-lookup"><span data-stu-id="4f1cb-288">Indicates whether metrics from the caller were received; 1 is yes, a null value is no.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4f1cb-289"><strong>Receptor</strong></span><span class="sxs-lookup"><span data-stu-id="4f1cb-289"><strong>Callee</strong></span></span></p></td>
<td><p><span data-ttu-id="4f1cb-290">bits</span><span class="sxs-lookup"><span data-stu-id="4f1cb-290">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="4f1cb-291">Indica se as métricas do receptor de chamada foram recebidas; 1 é sim, um valor nulo é não.</span><span class="sxs-lookup"><span data-stu-id="4f1cb-291">Indicates whether metrics from the call receiver were received; 1 is yes, a null value is no.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4f1cb-292"><strong>MidCallReport</strong></span><span class="sxs-lookup"><span data-stu-id="4f1cb-292"><strong>MidCallReport</strong></span></span></p></td>
<td><p><span data-ttu-id="4f1cb-293">bits</span><span class="sxs-lookup"><span data-stu-id="4f1cb-293">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="4f1cb-294">Indica se o relatório é para uma parte da sessão ou para a sessão completa.</span><span class="sxs-lookup"><span data-stu-id="4f1cb-294">Indicates whether the report is for a portion of the session or for the complete session.</span></span></p>
<p><span data-ttu-id="4f1cb-295">Esta coluna foi introduzida no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="4f1cb-295">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4f1cb-296"><strong>ClassifiedPoorCall</strong></span><span class="sxs-lookup"><span data-stu-id="4f1cb-296"><strong>ClassifiedPoorCall</strong></span></span></p></td>
<td><p><span data-ttu-id="4f1cb-297">bits</span><span class="sxs-lookup"><span data-stu-id="4f1cb-297">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="4f1cb-298">Indica se uma chamada foi classificada como uma chamada ruim (valor 1) ou como uma boa chamada (0).</span><span class="sxs-lookup"><span data-stu-id="4f1cb-298">Indicates whether a call was classified as a poor call (value of 1) or as a good call (0).</span></span></p>
<p><span data-ttu-id="4f1cb-299">Esta coluna foi introduzida no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="4f1cb-299">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4f1cb-300"><strong>CallerConnectivityICE</strong></span><span class="sxs-lookup"><span data-stu-id="4f1cb-300"><strong>CallerConnectivityICE</strong></span></span></p></td>
<td><p><span data-ttu-id="4f1cb-301">tinyInt</span><span class="sxs-lookup"><span data-stu-id="4f1cb-301">tinyInt</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="4f1cb-302">Indica se o chamador se conectou à rede usando o protocolo ICE (Internet Connectivity Establishment).</span><span class="sxs-lookup"><span data-stu-id="4f1cb-302">Indicates whether the caller connected to the network using the ICE protocol (Internet Connectivity Establishment).</span></span></p>
<p><span data-ttu-id="4f1cb-303">Esta coluna foi introduzida no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="4f1cb-303">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4f1cb-304"><strong>CalleeConnectivityICE</strong></span><span class="sxs-lookup"><span data-stu-id="4f1cb-304"><strong>CalleeConnectivityICE</strong></span></span></p></td>
<td><p><span data-ttu-id="4f1cb-305">tinyint</span><span class="sxs-lookup"><span data-stu-id="4f1cb-305">tinyint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="4f1cb-306">Indica se o chamador se conectou à rede usando o protocolo ICE (Internet Connectivity Establishment).</span><span class="sxs-lookup"><span data-stu-id="4f1cb-306">Indicates whether the caller connected to the network using the ICE protocol (Internet Connectivity Establishment).</span></span></p>
<p><span data-ttu-id="4f1cb-307">Esta coluna foi introduzida no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="4f1cb-307">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4f1cb-308"><strong>CallerReflexiveLocalIPAddr</strong></span><span class="sxs-lookup"><span data-stu-id="4f1cb-308"><strong>CallerReflexiveLocalIPAddr</strong></span></span></p></td>
<td><p><span data-ttu-id="4f1cb-309">int</span><span class="sxs-lookup"><span data-stu-id="4f1cb-309">int</span></span></p></td>
<td><p><span data-ttu-id="4f1cb-310">Estrangeira</span><span class="sxs-lookup"><span data-stu-id="4f1cb-310">Foreign</span></span></p></td>
<td><p><span data-ttu-id="4f1cb-311">Endereço IP reflexivo do usuário que fez a chamada.</span><span class="sxs-lookup"><span data-stu-id="4f1cb-311">Reflexive IP address of the user who placed the call.</span></span> <span data-ttu-id="4f1cb-312">Nas organizações que usam o NAT (conversão de endereço de rede), o endereço IP reflexivo é o endereço IP do servidor proxy.</span><span class="sxs-lookup"><span data-stu-id="4f1cb-312">In organizations that use NAT (network address translation), the reflexive IP address is the IP address of the proxy server.</span></span></p>
<p><span data-ttu-id="4f1cb-313">Esta coluna foi introduzida no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="4f1cb-313">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4f1cb-314"><strong>CallerWiFiDriverDevicesDesc</strong></span><span class="sxs-lookup"><span data-stu-id="4f1cb-314"><strong>CallerWiFiDriverDevicesDesc</strong></span></span></p></td>
<td><p><span data-ttu-id="4f1cb-315">int</span><span class="sxs-lookup"><span data-stu-id="4f1cb-315">int</span></span></p></td>
<td><p><span data-ttu-id="4f1cb-316">Estrangeira</span><span class="sxs-lookup"><span data-stu-id="4f1cb-316">Foreign</span></span></p></td>
<td><p><span data-ttu-id="4f1cb-317">Descrição do dispositivo para o driver WiFi empregado pelo usuário que fez a chamada.</span><span class="sxs-lookup"><span data-stu-id="4f1cb-317">Device description for the WiFi driver employed by the user who placed the call.</span></span></p>
<p><span data-ttu-id="4f1cb-318">Esta coluna foi introduzida no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="4f1cb-318">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4f1cb-319"><strong>CallerWiFiDriverVersion</strong></span><span class="sxs-lookup"><span data-stu-id="4f1cb-319"><strong>CallerWiFiDriverVersion</strong></span></span></p></td>
<td><p><span data-ttu-id="4f1cb-320">int</span><span class="sxs-lookup"><span data-stu-id="4f1cb-320">int</span></span></p></td>
<td><p><span data-ttu-id="4f1cb-321">Estrangeira</span><span class="sxs-lookup"><span data-stu-id="4f1cb-321">Foreign</span></span></p></td>
<td><p><span data-ttu-id="4f1cb-322">Número de versão para o driver WiFi empregado pelo usuário que fez a chamada.</span><span class="sxs-lookup"><span data-stu-id="4f1cb-322">Version number for the WiFi driver employed by the user who placed the call.</span></span></p>
<p><span data-ttu-id="4f1cb-323">Esta coluna foi introduzida no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="4f1cb-323">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4f1cb-324"><strong>CalleReflexiveLocalIPAddr</strong></span><span class="sxs-lookup"><span data-stu-id="4f1cb-324"><strong>CalleReflexiveLocalIPAddr</strong></span></span></p></td>
<td><p><span data-ttu-id="4f1cb-325">int</span><span class="sxs-lookup"><span data-stu-id="4f1cb-325">int</span></span></p></td>
<td><p><span data-ttu-id="4f1cb-326">Estrangeira</span><span class="sxs-lookup"><span data-stu-id="4f1cb-326">Foreign</span></span></p></td>
<td><p><span data-ttu-id="4f1cb-327">Endereço IP reflexivo do usuário que recebeu a chamada.</span><span class="sxs-lookup"><span data-stu-id="4f1cb-327">Reflexive IP address of the user who received the call.</span></span> <span data-ttu-id="4f1cb-328">Nas organizações que usam o NAT (conversão de endereço de rede), o endereço IP reflexivo é o endereço IP do servidor proxy.</span><span class="sxs-lookup"><span data-stu-id="4f1cb-328">In organizations that use NAT (network address translation), the reflexive IP address is the IP address of the proxy server.</span></span></p>
<p><span data-ttu-id="4f1cb-329">Esta coluna foi introduzida no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="4f1cb-329">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4f1cb-330"><strong>CalleeWiFiDriverDevicesDesc</strong></span><span class="sxs-lookup"><span data-stu-id="4f1cb-330"><strong>CalleeWiFiDriverDevicesDesc</strong></span></span></p></td>
<td><p><span data-ttu-id="4f1cb-331">int</span><span class="sxs-lookup"><span data-stu-id="4f1cb-331">int</span></span></p></td>
<td><p><span data-ttu-id="4f1cb-332">Estrangeira</span><span class="sxs-lookup"><span data-stu-id="4f1cb-332">Foreign</span></span></p></td>
<td><p><span data-ttu-id="4f1cb-333">Descrição do dispositivo para o driver WiFi empregado pelo usuário que recebeu a chamada.</span><span class="sxs-lookup"><span data-stu-id="4f1cb-333">Device description for the WiFi driver employed by the user who received the call.</span></span></p>
<p><span data-ttu-id="4f1cb-334">Esta coluna foi introduzida no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="4f1cb-334">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4f1cb-335"><strong>CalleeWiFiDriverVersion</strong></span><span class="sxs-lookup"><span data-stu-id="4f1cb-335"><strong>CalleeWiFiDriverVersion</strong></span></span></p></td>
<td><p><span data-ttu-id="4f1cb-336">int</span><span class="sxs-lookup"><span data-stu-id="4f1cb-336">int</span></span></p></td>
<td><p><span data-ttu-id="4f1cb-337">Estrangeira</span><span class="sxs-lookup"><span data-stu-id="4f1cb-337">Foreign</span></span></p></td>
<td><p><span data-ttu-id="4f1cb-338">Número de versão para o driver WiFi empregado pelo usuário que recebeu a chamada.</span><span class="sxs-lookup"><span data-stu-id="4f1cb-338">Version number for the WiFi driver employed by the user who received the call.</span></span></p>
<p><span data-ttu-id="4f1cb-339">Esta coluna foi introduzida no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="4f1cb-339">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

