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
ms.openlocfilehash: 84aa652a51934a8b513392869a0875f60689f759
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42192744"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="medialine-table-in-lync-server-2013"></a><span data-ttu-id="89de4-102">Tabela de mídia no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="89de4-102">MediaLine table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="89de4-103">_**Última modificação do tópico:** 2014-02-21_</span><span class="sxs-lookup"><span data-stu-id="89de4-103">_**Topic Last Modified:** 2014-02-21_</span></span>

<span data-ttu-id="89de4-104">Cada registro representa uma linha de mídia.</span><span class="sxs-lookup"><span data-stu-id="89de4-104">Each record represents one media line.</span></span> <span data-ttu-id="89de4-105">(Uma sessão de áudio normalmente contém uma linha de mídia de áudio.</span><span class="sxs-lookup"><span data-stu-id="89de4-105">(One audio session usually contains one audio media line.</span></span> <span data-ttu-id="89de4-106">Uma sessão de áudio e vídeo (A/V) normalmente contém uma linha de mídia de áudio e uma linha de mídia de vídeo, embora a sessão possa conter duas linhas de mídia de vídeo se um dispositivo de conferência for usado ou se o modo de exibição de galeria for usado.</span><span class="sxs-lookup"><span data-stu-id="89de4-106">One audio and video (A/V) session usually contains one audio media line and one video media line, although the session might contain two video media lines if a conferencing device is used or if Gallery View is used.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="89de4-107"><strong>Coluna</strong></span><span class="sxs-lookup"><span data-stu-id="89de4-107"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="89de4-108"><strong>Tipo de dados</strong></span><span class="sxs-lookup"><span data-stu-id="89de4-108"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="89de4-109"><strong>Chave/índice</strong></span><span class="sxs-lookup"><span data-stu-id="89de4-109"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="89de4-110"><strong>Detalhes</strong></span><span class="sxs-lookup"><span data-stu-id="89de4-110"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="89de4-111"><strong>ConferenceDateTime</strong></span><span class="sxs-lookup"><span data-stu-id="89de4-111"><strong>ConferenceDateTime</strong></span></span></p></td>
<td><p><span data-ttu-id="89de4-112">datetime</span><span class="sxs-lookup"><span data-stu-id="89de4-112">datetime</span></span></p></td>
<td><p><span data-ttu-id="89de4-113">Primário</span><span class="sxs-lookup"><span data-stu-id="89de4-113">Primary</span></span></p></td>
<td><p><span data-ttu-id="89de4-114">Referenciado da <a href="lync-server-2013-session-table.md">tabela de sessão no Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="89de4-114">Referenced from the <a href="lync-server-2013-session-table.md">Session table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="89de4-115"><strong>SessionSeq</strong></span><span class="sxs-lookup"><span data-stu-id="89de4-115"><strong>SessionSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="89de4-116">int</span><span class="sxs-lookup"><span data-stu-id="89de4-116">int</span></span></p></td>
<td><p><span data-ttu-id="89de4-117">Primário</span><span class="sxs-lookup"><span data-stu-id="89de4-117">Primary</span></span></p></td>
<td><p><span data-ttu-id="89de4-118">Referenciado da <a href="lync-server-2013-session-table.md">tabela de sessão no Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="89de4-118">Referenced from the <a href="lync-server-2013-session-table.md">Session table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="89de4-119"><strong>MediaLineLabel</strong></span><span class="sxs-lookup"><span data-stu-id="89de4-119"><strong>MediaLineLabel</strong></span></span></p></td>
<td><p><span data-ttu-id="89de4-120">tinyint</span><span class="sxs-lookup"><span data-stu-id="89de4-120">tinyint</span></span></p></td>
<td><p><span data-ttu-id="89de4-121">Primário</span><span class="sxs-lookup"><span data-stu-id="89de4-121">Primary</span></span></p></td>
<td><p><span data-ttu-id="89de4-122">0 é o áudio principal, 1 é o vídeo principal e 2 é o vídeo panorâmico, 3 é o compartilhamento de aplicativo/área de trabalho.</span><span class="sxs-lookup"><span data-stu-id="89de4-122">0 is main audio, 1 is main video, and 2 is panoramic video, 3 is Application/Desktop Sharing.</span></span> <span data-ttu-id="89de4-123">Este rótulo deve ser exclusivo em uma única sessão.</span><span class="sxs-lookup"><span data-stu-id="89de4-123">This label must be unique within a single session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="89de4-124"><strong>ConnectivityIce</strong></span><span class="sxs-lookup"><span data-stu-id="89de4-124"><strong>ConnectivityIce</strong></span></span></p></td>
<td><p><span data-ttu-id="89de4-125">tinyint</span><span class="sxs-lookup"><span data-stu-id="89de4-125">tinyint</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="89de4-126">Esta coluna está presente, mas não é usada no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="89de4-126">This column is present but not used in Microsoft Lync Server 2013.</span></span> <span data-ttu-id="89de4-127">As informações sobre a conectividade usada para uma linha de mídia são capturadas nas colunas CallerConnectivityICE e CalleeConnectivityICE.</span><span class="sxs-lookup"><span data-stu-id="89de4-127">Information about the connectivity used for a media line is captured in the CallerConnectivityICE and CalleeConnectivityICE columns.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="89de4-128"><strong>CallerIceWarningFlags</strong></span><span class="sxs-lookup"><span data-stu-id="89de4-128"><strong>CallerIceWarningFlags</strong></span></span></p></td>
<td><p><span data-ttu-id="89de4-129">int</span><span class="sxs-lookup"><span data-stu-id="89de4-129">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="89de4-130">Informações sobre o processo de estabelecimento de conectividade interativa (ICE) descrito em sinalizadores de bits.</span><span class="sxs-lookup"><span data-stu-id="89de4-130">Information about Interactive Connectivity Establishment (ICE) process described in bits flags.</span></span> <span data-ttu-id="89de4-131">Para obter detalhes, consulte a <em>especificação de protocolo do Monitoring Server de qualidade da experiência</em>, disponível para download.</span><span class="sxs-lookup"><span data-stu-id="89de4-131">For details, refer to the <em>Quality of Experience Monitoring Server Protocol Specification</em>, available for download.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="89de4-132"><strong>CalleeIceWarningFlags</strong></span><span class="sxs-lookup"><span data-stu-id="89de4-132"><strong>CalleeIceWarningFlags</strong></span></span></p></td>
<td><p><span data-ttu-id="89de4-133">int</span><span class="sxs-lookup"><span data-stu-id="89de4-133">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="89de4-134">O mesmo que CallerIceWarningFlags, mas no lado do receptor.</span><span class="sxs-lookup"><span data-stu-id="89de4-134">Same as CallerIceWarningFlags, but on the callee side.</span></span> <span data-ttu-id="89de4-135">Para obter detalhes, consulte a <em>especificação de protocolo do Monitoring Server de qualidade da experiência</em>, disponível para download.</span><span class="sxs-lookup"><span data-stu-id="89de4-135">For details, refer to the <em>Quality of Experience Monitoring Server Protocol Specification</em>, available for download.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="89de4-136"><strong>Segurança</strong></span><span class="sxs-lookup"><span data-stu-id="89de4-136"><strong>Security</strong></span></span></p></td>
<td><p><span data-ttu-id="89de4-137">tinyint</span><span class="sxs-lookup"><span data-stu-id="89de4-137">tinyint</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="89de4-138">O perfil de segurança em uso.</span><span class="sxs-lookup"><span data-stu-id="89de4-138">The security profile in use.</span></span> <span data-ttu-id="89de4-139">0 é NONE (nenhum), 1 é SRTP, 2 é V1.</span><span class="sxs-lookup"><span data-stu-id="89de4-139">0 is NONE, 1 is SRTP, 2 is V1.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="89de4-140"><strong>Transport</strong></span><span class="sxs-lookup"><span data-stu-id="89de4-140"><strong>Transport</strong></span></span></p></td>
<td><p><span data-ttu-id="89de4-141">tinyint</span><span class="sxs-lookup"><span data-stu-id="89de4-141">tinyint</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="89de4-142">0 é UDP, 1 é TCP.</span><span class="sxs-lookup"><span data-stu-id="89de4-142">0 is UDP, 1 is TCP.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="89de4-143"><strong>CallerIPAddr</strong></span><span class="sxs-lookup"><span data-stu-id="89de4-143"><strong>CallerIPAddr</strong></span></span></p></td>
<td><p><span data-ttu-id="89de4-144">int</span><span class="sxs-lookup"><span data-stu-id="89de4-144">int</span></span></p></td>
<td><p><span data-ttu-id="89de4-145">Estrangeira</span><span class="sxs-lookup"><span data-stu-id="89de4-145">Foreign</span></span></p></td>
<td><p><span data-ttu-id="89de4-146">Endereço IP do chamador.</span><span class="sxs-lookup"><span data-stu-id="89de4-146">IP Address of the caller.</span></span> <span data-ttu-id="89de4-147">Consulte a <a href="lync-server-2013-ipaddress-table.md">tabela IPAddress no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="89de4-147">See the <a href="lync-server-2013-ipaddress-table.md">IPAddress table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="89de4-148"><strong>CallerPort</strong></span><span class="sxs-lookup"><span data-stu-id="89de4-148"><strong>CallerPort</strong></span></span></p></td>
<td><p><span data-ttu-id="89de4-149">int</span><span class="sxs-lookup"><span data-stu-id="89de4-149">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="89de4-150">Porta usada pelo chamador.</span><span class="sxs-lookup"><span data-stu-id="89de4-150">Port used by the caller.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="89de4-151"><strong>CallerSubnet</strong></span><span class="sxs-lookup"><span data-stu-id="89de4-151"><strong>CallerSubnet</strong></span></span></p></td>
<td><p><span data-ttu-id="89de4-152">int</span><span class="sxs-lookup"><span data-stu-id="89de4-152">int</span></span></p></td>
<td><p><span data-ttu-id="89de4-153"> Estrangeira</span><span class="sxs-lookup"><span data-stu-id="89de4-153"> Foreign</span></span></p></td>
<td><p><span data-ttu-id="89de4-154">A sub-rede do chamador.</span><span class="sxs-lookup"><span data-stu-id="89de4-154">The subnet of the caller.</span></span> <span data-ttu-id="89de4-155">Consulte a <a href="lync-server-2013-ipaddress-table.md">tabela IPAddress no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="89de4-155">See the <a href="lync-server-2013-ipaddress-table.md">IPAddress table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="89de4-156"><strong>CallerInside</strong></span><span class="sxs-lookup"><span data-stu-id="89de4-156"><strong>CallerInside</strong></span></span></p></td>
<td><p><span data-ttu-id="89de4-157">bits</span><span class="sxs-lookup"><span data-stu-id="89de4-157">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="89de4-158">1 significa que o chamador está dentro da rede da empresa, 0 significa que o chamador está fora da rede.</span><span class="sxs-lookup"><span data-stu-id="89de4-158">1 means caller is inside the enterprise network, 0 means the caller is outside the network.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="89de4-159"><strong>CallerMacAddress</strong></span><span class="sxs-lookup"><span data-stu-id="89de4-159"><strong>CallerMacAddress</strong></span></span></p></td>
<td><p><span data-ttu-id="89de4-160">int</span><span class="sxs-lookup"><span data-stu-id="89de4-160">int</span></span></p></td>
<td><p><span data-ttu-id="89de4-161">Estrangeira</span><span class="sxs-lookup"><span data-stu-id="89de4-161">Foreign</span></span></p></td>
<td><p><span data-ttu-id="89de4-162">Endereço MAC do chamador, referenciado da <a href="lync-server-2013-macaddress-table.md">tabela MACAddress no Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="89de4-162">Caller’s mac address, referenced from <a href="lync-server-2013-macaddress-table.md">MacAddress table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="89de4-163"><strong>CallerRelayIPAddr</strong></span><span class="sxs-lookup"><span data-stu-id="89de4-163"><strong>CallerRelayIPAddr</strong></span></span></p></td>
<td><p><span data-ttu-id="89de4-164">int</span><span class="sxs-lookup"><span data-stu-id="89de4-164">int</span></span></p></td>
<td><p><span data-ttu-id="89de4-165">Estrangeira</span><span class="sxs-lookup"><span data-stu-id="89de4-165">Foreign</span></span></p></td>
<td><p><span data-ttu-id="89de4-166">Endereço IP do serviço de borda a/V do Lync Server usado pelo chamador.</span><span class="sxs-lookup"><span data-stu-id="89de4-166">IP Address of the Lync Server A/V Edge service used by the caller.</span></span> <span data-ttu-id="89de4-167">Consulte a <a href="lync-server-2013-ipaddress-table.md">tabela IPAddress no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="89de4-167">See the <a href="lync-server-2013-ipaddress-table.md">IPAddress table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="89de4-168"><strong>CallerRelayPort</strong></span><span class="sxs-lookup"><span data-stu-id="89de4-168"><strong>CallerRelayPort</strong></span></span></p></td>
<td><p><span data-ttu-id="89de4-169">int</span><span class="sxs-lookup"><span data-stu-id="89de4-169">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="89de4-170">Porta usada no serviço de borda A/V pelo chamador.</span><span class="sxs-lookup"><span data-stu-id="89de4-170">Port used on the A/V Edge service by the caller.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="89de4-171"><strong>CallerCaptureDev</strong></span><span class="sxs-lookup"><span data-stu-id="89de4-171"><strong>CallerCaptureDev</strong></span></span></p></td>
<td><p><span data-ttu-id="89de4-172">int</span><span class="sxs-lookup"><span data-stu-id="89de4-172">int</span></span></p></td>
<td><p><span data-ttu-id="89de4-173">Estrangeira</span><span class="sxs-lookup"><span data-stu-id="89de4-173">Foreign</span></span></p></td>
<td><p><span data-ttu-id="89de4-174">Dispositivo de captura usado pelo chamador.</span><span class="sxs-lookup"><span data-stu-id="89de4-174">Capture device used by the caller.</span></span> <span data-ttu-id="89de4-175">Referenciado da <a href="lync-server-2013-device-table.md">tabela Device no Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="89de4-175">Referenced from the <a href="lync-server-2013-device-table.md">Device table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="89de4-176"><strong>CallerRenderDev</strong></span><span class="sxs-lookup"><span data-stu-id="89de4-176"><strong>CallerRenderDev</strong></span></span></p></td>
<td><p><span data-ttu-id="89de4-177">int</span><span class="sxs-lookup"><span data-stu-id="89de4-177">int</span></span></p></td>
<td><p><span data-ttu-id="89de4-178">Estrangeira</span><span class="sxs-lookup"><span data-stu-id="89de4-178">Foreign</span></span></p></td>
<td><p><span data-ttu-id="89de4-179">Dispositivo de renderização usado pelo chamador.</span><span class="sxs-lookup"><span data-stu-id="89de4-179">Render device used by caller.</span></span> <span data-ttu-id="89de4-180">Referenciado da <a href="lync-server-2013-device-table.md">tabela Device no Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="89de4-180">Referenced from the <a href="lync-server-2013-device-table.md">Device table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="89de4-181"><strong>CallerCaptureDevDriver</strong></span><span class="sxs-lookup"><span data-stu-id="89de4-181"><strong>CallerCaptureDevDriver</strong></span></span></p></td>
<td><p><span data-ttu-id="89de4-182">int</span><span class="sxs-lookup"><span data-stu-id="89de4-182">int</span></span></p></td>
<td><p><span data-ttu-id="89de4-183">Estrangeira</span><span class="sxs-lookup"><span data-stu-id="89de4-183">Foreign</span></span></p></td>
<td><p><span data-ttu-id="89de4-184">Driver do dispositivo de captura do chamador, referenciado na <a href="lync-server-2013-devicedriver-table.md">tabela DeviceDriver no Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="89de4-184">Driver for the caller’s capture device, referenced from the <a href="lync-server-2013-devicedriver-table.md">DeviceDriver table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="89de4-185"><strong>CallerRenderDevDriver</strong></span><span class="sxs-lookup"><span data-stu-id="89de4-185"><strong>CallerRenderDevDriver</strong></span></span></p></td>
<td><p><span data-ttu-id="89de4-186">int</span><span class="sxs-lookup"><span data-stu-id="89de4-186">int</span></span></p></td>
<td><p><span data-ttu-id="89de4-187">Estrangeira</span><span class="sxs-lookup"><span data-stu-id="89de4-187">Foreign</span></span></p></td>
<td><p><span data-ttu-id="89de4-188">Driver do dispositivo de renderização do chamador, referenciado da <a href="lync-server-2013-devicedriver-table.md">tabela DeviceDriver no Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="89de4-188">Driver for the caller’s render device, referenced from the <a href="lync-server-2013-devicedriver-table.md">DeviceDriver table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="89de4-189"><strong>CallerNetworkConnectionType</strong></span><span class="sxs-lookup"><span data-stu-id="89de4-189"><strong>CallerNetworkConnectionType</strong></span></span></p></td>
<td><p><span data-ttu-id="89de4-190">tinyint</span><span class="sxs-lookup"><span data-stu-id="89de4-190">tinyint</span></span></p></td>
<td><p><span data-ttu-id="89de4-191">Estrangeira</span><span class="sxs-lookup"><span data-stu-id="89de4-191">Foreign</span></span></p></td>
<td><p><span data-ttu-id="89de4-192">Indica como o chamador se conectou à rede.</span><span class="sxs-lookup"><span data-stu-id="89de4-192">Indicates how the caller connected to the network.</span></span> <span data-ttu-id="89de4-193">Os valores são obtidos da <a href="lync-server-2013-networkconnectiondetail-table.md">tabela NetworkConnectionDetail no Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="89de4-193">Values are obtained from the <a href="lync-server-2013-networkconnectiondetail-table.md">NetworkConnectionDetail table in Lync Server 2013</a>.</span></span> <span data-ttu-id="89de4-194">Os valores típicos são 0 para uma conexão com fio ' 1 para uma conexão WiFi; e 3 para uma conexão Ethernet.</span><span class="sxs-lookup"><span data-stu-id="89de4-194">Typical values are 0 for a wired connection’ 1 for a WiFi connection; and 3 for an Ethernet connection.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="89de4-195"><strong>CallerBssid</strong></span><span class="sxs-lookup"><span data-stu-id="89de4-195"><strong>CallerBssid</strong></span></span></p></td>
<td><p><span data-ttu-id="89de4-196">int</span><span class="sxs-lookup"><span data-stu-id="89de4-196">int</span></span></p></td>
<td><p><span data-ttu-id="89de4-197">Estrangeira</span><span class="sxs-lookup"><span data-stu-id="89de4-197">Foreign</span></span></p></td>
<td><p><span data-ttu-id="89de4-198">BSSID do chamador se for usado sem fio.</span><span class="sxs-lookup"><span data-stu-id="89de4-198">Caller’s BSSID if wireless is used.</span></span> <span data-ttu-id="89de4-199">Referenciado da <a href="lync-server-2013-macaddress-table.md">tabela MACAddress no Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="89de4-199">Referenced from <a href="lync-server-2013-macaddress-table.md">MacAddress table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="89de4-200"><strong>CallerVPN</strong></span><span class="sxs-lookup"><span data-stu-id="89de4-200"><strong>CallerVPN</strong></span></span></p></td>
<td><p><span data-ttu-id="89de4-201">bits</span><span class="sxs-lookup"><span data-stu-id="89de4-201">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="89de4-202">O link do chamador.</span><span class="sxs-lookup"><span data-stu-id="89de4-202">The caller's link.</span></span> <span data-ttu-id="89de4-203">1 é para rede virtual privada (VPN), 0 é para não-VPN.</span><span class="sxs-lookup"><span data-stu-id="89de4-203">1 is virtual private network (VPN), 0 is non-VPN.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="89de4-204"><strong>CallerLinkSpeed</strong></span><span class="sxs-lookup"><span data-stu-id="89de4-204"><strong>CallerLinkSpeed</strong></span></span></p></td>
<td><p><span data-ttu-id="89de4-205">decimal (18, 0)</span><span class="sxs-lookup"><span data-stu-id="89de4-205">decimal(18,0)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="89de4-206">A velocidade do link de rede, em bps, para o ponto de extremidade do chamador.</span><span class="sxs-lookup"><span data-stu-id="89de4-206">The network link speed, in bps, for the caller's endpoint.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="89de4-207"><strong>CalleeIPAddr</strong></span><span class="sxs-lookup"><span data-stu-id="89de4-207"><strong>CalleeIPAddr</strong></span></span></p></td>
<td><p><span data-ttu-id="89de4-208">int</span><span class="sxs-lookup"><span data-stu-id="89de4-208">int</span></span></p></td>
<td><p><span data-ttu-id="89de4-209">Estrangeira</span><span class="sxs-lookup"><span data-stu-id="89de4-209">Foreign</span></span></p></td>
<td><p><span data-ttu-id="89de4-210">Endereço IP do receptor de chamada.</span><span class="sxs-lookup"><span data-stu-id="89de4-210">IP Address of the call receiver.</span></span> <span data-ttu-id="89de4-211">Consulte a <a href="lync-server-2013-ipaddress-table.md">tabela IPAddress no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="89de4-211">See the <a href="lync-server-2013-ipaddress-table.md">IPAddress table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="89de4-212"><strong>CalleePort</strong></span><span class="sxs-lookup"><span data-stu-id="89de4-212"><strong>CalleePort</strong></span></span></p></td>
<td><p><span data-ttu-id="89de4-213">bits</span><span class="sxs-lookup"><span data-stu-id="89de4-213">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="89de4-214">Porta usada pelo receptor de chamada.</span><span class="sxs-lookup"><span data-stu-id="89de4-214">Port used by the call receiver.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="89de4-215"><strong>CalleeSubnet</strong></span><span class="sxs-lookup"><span data-stu-id="89de4-215"><strong>CalleeSubnet</strong></span></span></p></td>
<td><p><span data-ttu-id="89de4-216">int</span><span class="sxs-lookup"><span data-stu-id="89de4-216">int</span></span></p></td>
<td><p><span data-ttu-id="89de4-217">Estrangeira</span><span class="sxs-lookup"><span data-stu-id="89de4-217">Foreign</span></span></p></td>
<td><p><span data-ttu-id="89de4-218">Sub-rede do receptor.</span><span class="sxs-lookup"><span data-stu-id="89de4-218">Subnet of callee.</span></span> <span data-ttu-id="89de4-219">Consulte a <a href="lync-server-2013-ipaddress-table.md">tabela IPAddress no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="89de4-219">See the <a href="lync-server-2013-ipaddress-table.md">IPAddress table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="89de4-220"><strong>CalleeInside</strong></span><span class="sxs-lookup"><span data-stu-id="89de4-220"><strong>CalleeInside</strong></span></span></p></td>
<td><p><span data-ttu-id="89de4-221">bits</span><span class="sxs-lookup"><span data-stu-id="89de4-221">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="89de4-222">1 significa que o receptor de chamada está dentro da rede corporativa, 0 significa que o receptor de chamadas está fora da rede.</span><span class="sxs-lookup"><span data-stu-id="89de4-222">1 means call receiver is inside the enterprise network, 0 means the call receiver is outside the network.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="89de4-223"><strong>CalleeMacAddress</strong></span><span class="sxs-lookup"><span data-stu-id="89de4-223"><strong>CalleeMacAddress</strong></span></span></p></td>
<td><p><span data-ttu-id="89de4-224">int</span><span class="sxs-lookup"><span data-stu-id="89de4-224">int</span></span></p></td>
<td><p><span data-ttu-id="89de4-225">Estrangeira</span><span class="sxs-lookup"><span data-stu-id="89de4-225">Foreign</span></span></p></td>
<td><p><span data-ttu-id="89de4-226">Endereço MAC do receptor.</span><span class="sxs-lookup"><span data-stu-id="89de4-226">Callee Mac address.</span></span> <span data-ttu-id="89de4-227">Referenciado da <a href="lync-server-2013-macaddress-table.md">tabela MACAddress no Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="89de4-227">Referenced from the <a href="lync-server-2013-macaddress-table.md">MacAddress table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="89de4-228"><strong>CalleeRelayIPAddr</strong></span><span class="sxs-lookup"><span data-stu-id="89de4-228"><strong>CalleeRelayIPAddr</strong></span></span></p></td>
<td><p><span data-ttu-id="89de4-229">int</span><span class="sxs-lookup"><span data-stu-id="89de4-229">int</span></span></p></td>
<td><p><span data-ttu-id="89de4-230">Estrangeira</span><span class="sxs-lookup"><span data-stu-id="89de4-230">Foreign</span></span></p></td>
<td><p><span data-ttu-id="89de4-231">Endereço IP do serviço de borda A/V usado pelo receptor de chamada.</span><span class="sxs-lookup"><span data-stu-id="89de4-231">IP Address of the A/V Edge service used by the call receiver.</span></span> <span data-ttu-id="89de4-232">Consulte a <a href="lync-server-2013-ipaddress-table.md">tabela IPAddress no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="89de4-232">See the <a href="lync-server-2013-ipaddress-table.md">IPAddress table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="89de4-233"><strong>CalleeRelayPort</strong></span><span class="sxs-lookup"><span data-stu-id="89de4-233"><strong>CalleeRelayPort</strong></span></span></p></td>
<td><p><span data-ttu-id="89de4-234">int</span><span class="sxs-lookup"><span data-stu-id="89de4-234">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="89de4-235">Porta usada no serviço de borda A/V pelo receptor de chamada.</span><span class="sxs-lookup"><span data-stu-id="89de4-235">Port used on the A/V Edge Service by the call receiver.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="89de4-236"><strong>CalleeCaptureDev</strong></span><span class="sxs-lookup"><span data-stu-id="89de4-236"><strong>CalleeCaptureDev</strong></span></span></p></td>
<td><p><span data-ttu-id="89de4-237">int</span><span class="sxs-lookup"><span data-stu-id="89de4-237">int</span></span></p></td>
<td><p><span data-ttu-id="89de4-238">estrangeira</span><span class="sxs-lookup"><span data-stu-id="89de4-238">foreign</span></span></p></td>
<td><p><span data-ttu-id="89de4-239">Dispositivo de captura usado pelo receptor de chamada.</span><span class="sxs-lookup"><span data-stu-id="89de4-239">Capture device used by the call receiver.</span></span> <span data-ttu-id="89de4-240">Referenciado da <a href="lync-server-2013-device-table.md">tabela Device no Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="89de4-240">Referenced from the <a href="lync-server-2013-device-table.md">Device table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="89de4-241"><strong>CalleeRenderDev</strong></span><span class="sxs-lookup"><span data-stu-id="89de4-241"><strong>CalleeRenderDev</strong></span></span></p></td>
<td><p><span data-ttu-id="89de4-242">int</span><span class="sxs-lookup"><span data-stu-id="89de4-242">int</span></span></p></td>
<td><p><span data-ttu-id="89de4-243">Estrangeira</span><span class="sxs-lookup"><span data-stu-id="89de4-243">Foreign</span></span></p></td>
<td><p><span data-ttu-id="89de4-244">Dispositivo de renderização usado pelo receptor de chamada.</span><span class="sxs-lookup"><span data-stu-id="89de4-244">Render device used by the call receiver.</span></span> <span data-ttu-id="89de4-245">Referenciado da <a href="lync-server-2013-device-table.md">tabela Device no Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="89de4-245">Referenced from the <a href="lync-server-2013-device-table.md">Device table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="89de4-246"><strong>CalleeCaptureDevDriver</strong></span><span class="sxs-lookup"><span data-stu-id="89de4-246"><strong>CalleeCaptureDevDriver</strong></span></span></p></td>
<td><p><span data-ttu-id="89de4-247">int</span><span class="sxs-lookup"><span data-stu-id="89de4-247">int</span></span></p></td>
<td><p><span data-ttu-id="89de4-248">Estrangeira</span><span class="sxs-lookup"><span data-stu-id="89de4-248">Foreign</span></span></p></td>
<td><p><span data-ttu-id="89de4-249">Driver do dispositivo de captura do receptor de chamada.</span><span class="sxs-lookup"><span data-stu-id="89de4-249">Driver for the call receiver’s capture device.</span></span> <span data-ttu-id="89de4-250">Referenciado da <a href="lync-server-2013-devicedriver-table.md">tabela DeviceDriver no Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="89de4-250">Referenced from <a href="lync-server-2013-devicedriver-table.md">DeviceDriver table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="89de4-251"><strong>CalleeRenderDevDriver</strong></span><span class="sxs-lookup"><span data-stu-id="89de4-251"><strong>CalleeRenderDevDriver</strong></span></span></p></td>
<td><p><span data-ttu-id="89de4-252">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="89de4-252">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="89de4-253">Estrangeira</span><span class="sxs-lookup"><span data-stu-id="89de4-253">Foreign</span></span></p></td>
<td><p><span data-ttu-id="89de4-254">Driver para o dispositivo de renderização do receptor de chamada.</span><span class="sxs-lookup"><span data-stu-id="89de4-254">Driver for the call receiver’s render device.</span></span> <span data-ttu-id="89de4-255">Referenciado da <a href="lync-server-2013-devicedriver-table.md">tabela DeviceDriver no Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="89de4-255">Referenced from <a href="lync-server-2013-devicedriver-table.md">DeviceDriver table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="89de4-256"><strong>CalleeNetworkConnectionType</strong></span><span class="sxs-lookup"><span data-stu-id="89de4-256"><strong>CalleeNetworkConnectionType</strong></span></span></p></td>
<td><p><span data-ttu-id="89de4-257">tinyint</span><span class="sxs-lookup"><span data-stu-id="89de4-257">tinyint</span></span></p></td>
<td><p><span data-ttu-id="89de4-258">Estrangeira</span><span class="sxs-lookup"><span data-stu-id="89de4-258">Foreign</span></span></p></td>
<td><p><span data-ttu-id="89de4-259">Indica como o receptor está conectado à rede.</span><span class="sxs-lookup"><span data-stu-id="89de4-259">Indicates how the callee connected to the network.</span></span> <span data-ttu-id="89de4-260">Os valores são obtidos da <a href="lync-server-2013-networkconnectiondetail-table.md">tabela NetworkConnectionDetail no Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="89de4-260">Values are obtained from the <a href="lync-server-2013-networkconnectiondetail-table.md">NetworkConnectionDetail table in Lync Server 2013</a>.</span></span> <span data-ttu-id="89de4-261">Os valores típicos são 0 para uma conexão com fio ' 1 para uma conexão WiFi; e 3 para uma conexão Ethernet.</span><span class="sxs-lookup"><span data-stu-id="89de4-261">Typical values are 0 for a wired connection’ 1 for a WiFi connection; and 3 for an Ethernet connection.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="89de4-262"><strong>CalleeBssid</strong></span><span class="sxs-lookup"><span data-stu-id="89de4-262"><strong>CalleeBssid</strong></span></span></p></td>
<td><p><span data-ttu-id="89de4-263">int</span><span class="sxs-lookup"><span data-stu-id="89de4-263">int</span></span></p></td>
<td><p><span data-ttu-id="89de4-264">Estrangeira</span><span class="sxs-lookup"><span data-stu-id="89de4-264">Foreign</span></span></p></td>
<td><p><span data-ttu-id="89de4-265">BSSID do receptor da chamada se for usado sem fio.</span><span class="sxs-lookup"><span data-stu-id="89de4-265">Callee’s BSSID if wireless is used.</span></span> <span data-ttu-id="89de4-266">Referenciado da <a href="lync-server-2013-macaddress-table.md">tabela MACAddress no Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="89de4-266">Referenced from <a href="lync-server-2013-macaddress-table.md">MacAddress table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="89de4-267"><strong>CalleeVPN</strong></span><span class="sxs-lookup"><span data-stu-id="89de4-267"><strong>CalleeVPN</strong></span></span></p></td>
<td><p><span data-ttu-id="89de4-268">bits</span><span class="sxs-lookup"><span data-stu-id="89de4-268">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="89de4-269">O link do receptor de chamada; 1 é VPN (rede virtual privada), 0 não é VPN.</span><span class="sxs-lookup"><span data-stu-id="89de4-269">The call receiver’s link; 1 is virtual private network (VPN), 0 is non-VPN.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="89de4-270"><strong>CalleeLinkSpeed</strong></span><span class="sxs-lookup"><span data-stu-id="89de4-270"><strong>CalleeLinkSpeed</strong></span></span></p></td>
<td><p><span data-ttu-id="89de4-271">decimal (18, 0)</span><span class="sxs-lookup"><span data-stu-id="89de4-271">decimal(18,0)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="89de4-272">A velocidade do link de rede, em bps, para o ponto de extremidade do receptor de chamada.</span><span class="sxs-lookup"><span data-stu-id="89de4-272">The network link speed, in bps, for the call receiver’s endpoint.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="89de4-273"><strong>ConversationalMOS</strong></span><span class="sxs-lookup"><span data-stu-id="89de4-273"><strong>ConversationalMOS</strong></span></span></p></td>
<td><p><span data-ttu-id="89de4-274">decimal (3, 2)</span><span class="sxs-lookup"><span data-stu-id="89de4-274">decimal(3,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="89de4-275">MOS da Conversa de Banda Estreita das sessões de áudio (com base nos dois fluxos de áudio).</span><span class="sxs-lookup"><span data-stu-id="89de4-275">Narrowband Conversational MOS of the audio sessions (based on both audio streams).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="89de4-276"><strong>AppliedBandwidthLimit</strong></span><span class="sxs-lookup"><span data-stu-id="89de4-276"><strong>AppliedBandwidthLimit</strong></span></span></p></td>
<td><p><span data-ttu-id="89de4-277">int</span><span class="sxs-lookup"><span data-stu-id="89de4-277">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="89de4-278">Esta é a largura de banda real aplicada ao fluxo de envio enviado fornecido por várias configurações de política (TURN, API, SDP, servidor de política e assim por diante).</span><span class="sxs-lookup"><span data-stu-id="89de4-278">This is the actual bandwidth applied to the given send side stream given various policy settings (TURN, API, SDP, Policy Server, and so on).</span></span> <span data-ttu-id="89de4-279">Isso não deve ser confundido com a largura de banda efetiva porque pode haver uma largura de banda efetiva menor com base na estimativa de largura de banda.</span><span class="sxs-lookup"><span data-stu-id="89de4-279">This is not to be confused with the effective bandwidth because there can be a lower effective bandwidth based on the bandwidth estimate.</span></span> <span data-ttu-id="89de4-280">Esta é basicamente a largura de banda máxima que o stream de envio pode utilizar dos limites impostos pela estimativa de largura de banda.</span><span class="sxs-lookup"><span data-stu-id="89de4-280">This is basically the maximum bandwidth the send stream can take barring limits imposed by the bandwidth estimate.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="89de4-281"><strong>AppliedBandwidthSourceKey</strong></span><span class="sxs-lookup"><span data-stu-id="89de4-281"><strong>AppliedBandwidthSourceKey</strong></span></span></p></td>
<td><p><span data-ttu-id="89de4-282">smallint</span><span class="sxs-lookup"><span data-stu-id="89de4-282">smallint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="89de4-283">Essa é a origem do cap de largura de banda que está sendo imposto.</span><span class="sxs-lookup"><span data-stu-id="89de4-283">This is the source of the bandwidth cap being imposed.</span></span> <span data-ttu-id="89de4-284">Descreve de onde o limite de largura de banda está vindo ("servidor de política", "Ativar servidor", "modalidade" e assim por diante).</span><span class="sxs-lookup"><span data-stu-id="89de4-284">It describes where the bandwidth limit is coming from (“Policy Server”, “TURN Server”, “Modality”, and so on).</span></span> <span data-ttu-id="89de4-285">Referenciado da <a href="lync-server-2013-appliedbandwidthsource-table.md">tabela AppliedBandwidthSource no Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="89de4-285">Referenced from the <a href="lync-server-2013-appliedbandwidthsource-table.md">AppliedBandwidthSource table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="89de4-286"><strong>Caller</strong></span><span class="sxs-lookup"><span data-stu-id="89de4-286"><strong>Caller</strong></span></span></p></td>
<td><p><span data-ttu-id="89de4-287">bits</span><span class="sxs-lookup"><span data-stu-id="89de4-287">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="89de4-288">Indica se as métricas do chamador foram recebidas; 1 é sim, um valor nulo é não.</span><span class="sxs-lookup"><span data-stu-id="89de4-288">Indicates whether metrics from the caller were received; 1 is yes, a null value is no.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="89de4-289"><strong>Receptor</strong></span><span class="sxs-lookup"><span data-stu-id="89de4-289"><strong>Callee</strong></span></span></p></td>
<td><p><span data-ttu-id="89de4-290">bits</span><span class="sxs-lookup"><span data-stu-id="89de4-290">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="89de4-291">Indica se as métricas do receptor de chamada foram recebidas; 1 é sim, um valor nulo é não.</span><span class="sxs-lookup"><span data-stu-id="89de4-291">Indicates whether metrics from the call receiver were received; 1 is yes, a null value is no.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="89de4-292"><strong>MidCallReport</strong></span><span class="sxs-lookup"><span data-stu-id="89de4-292"><strong>MidCallReport</strong></span></span></p></td>
<td><p><span data-ttu-id="89de4-293">bits</span><span class="sxs-lookup"><span data-stu-id="89de4-293">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="89de4-294">Indica se o relatório é para uma parte da sessão ou para a sessão completa.</span><span class="sxs-lookup"><span data-stu-id="89de4-294">Indicates whether the report is for a portion of the session or for the complete session.</span></span></p>
<p><span data-ttu-id="89de4-295">Esta coluna foi introduzida no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="89de4-295">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="89de4-296"><strong>ClassifiedPoorCall</strong></span><span class="sxs-lookup"><span data-stu-id="89de4-296"><strong>ClassifiedPoorCall</strong></span></span></p></td>
<td><p><span data-ttu-id="89de4-297">bits</span><span class="sxs-lookup"><span data-stu-id="89de4-297">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="89de4-298">Indica se uma chamada foi classificada como uma chamada ruim (valor 1) ou como uma boa chamada (0).</span><span class="sxs-lookup"><span data-stu-id="89de4-298">Indicates whether a call was classified as a poor call (value of 1) or as a good call (0).</span></span></p>
<p><span data-ttu-id="89de4-299">Esta coluna foi introduzida no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="89de4-299">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="89de4-300"><strong>CallerConnectivityICE</strong></span><span class="sxs-lookup"><span data-stu-id="89de4-300"><strong>CallerConnectivityICE</strong></span></span></p></td>
<td><p><span data-ttu-id="89de4-301">tinyInt</span><span class="sxs-lookup"><span data-stu-id="89de4-301">tinyInt</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="89de4-302">Indica se o chamador se conectou à rede usando o protocolo ICE (Internet Connectivity Establishment).</span><span class="sxs-lookup"><span data-stu-id="89de4-302">Indicates whether the caller connected to the network using the ICE protocol (Internet Connectivity Establishment).</span></span></p>
<p><span data-ttu-id="89de4-303">Esta coluna foi introduzida no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="89de4-303">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="89de4-304"><strong>CalleeConnectivityICE</strong></span><span class="sxs-lookup"><span data-stu-id="89de4-304"><strong>CalleeConnectivityICE</strong></span></span></p></td>
<td><p><span data-ttu-id="89de4-305">tinyint</span><span class="sxs-lookup"><span data-stu-id="89de4-305">tinyint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="89de4-306">Indica se o chamador se conectou à rede usando o protocolo ICE (Internet Connectivity Establishment).</span><span class="sxs-lookup"><span data-stu-id="89de4-306">Indicates whether the caller connected to the network using the ICE protocol (Internet Connectivity Establishment).</span></span></p>
<p><span data-ttu-id="89de4-307">Esta coluna foi introduzida no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="89de4-307">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="89de4-308"><strong>CallerReflexiveLocalIPAddr</strong></span><span class="sxs-lookup"><span data-stu-id="89de4-308"><strong>CallerReflexiveLocalIPAddr</strong></span></span></p></td>
<td><p><span data-ttu-id="89de4-309">int</span><span class="sxs-lookup"><span data-stu-id="89de4-309">int</span></span></p></td>
<td><p><span data-ttu-id="89de4-310">Estrangeira</span><span class="sxs-lookup"><span data-stu-id="89de4-310">Foreign</span></span></p></td>
<td><p><span data-ttu-id="89de4-311">Endereço IP reflexivo do usuário que fez a chamada.</span><span class="sxs-lookup"><span data-stu-id="89de4-311">Reflexive IP address of the user who placed the call.</span></span> <span data-ttu-id="89de4-312">Nas organizações que usam o NAT (conversão de endereço de rede), o endereço IP reflexivo é o endereço IP do servidor proxy.</span><span class="sxs-lookup"><span data-stu-id="89de4-312">In organizations that use NAT (network address translation), the reflexive IP address is the IP address of the proxy server.</span></span></p>
<p><span data-ttu-id="89de4-313">Esta coluna foi introduzida no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="89de4-313">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="89de4-314"><strong>CallerWiFiDriverDevicesDesc</strong></span><span class="sxs-lookup"><span data-stu-id="89de4-314"><strong>CallerWiFiDriverDevicesDesc</strong></span></span></p></td>
<td><p><span data-ttu-id="89de4-315">int</span><span class="sxs-lookup"><span data-stu-id="89de4-315">int</span></span></p></td>
<td><p><span data-ttu-id="89de4-316">Estrangeira</span><span class="sxs-lookup"><span data-stu-id="89de4-316">Foreign</span></span></p></td>
<td><p><span data-ttu-id="89de4-317">Descrição do dispositivo para o driver WiFi empregado pelo usuário que fez a chamada.</span><span class="sxs-lookup"><span data-stu-id="89de4-317">Device description for the WiFi driver employed by the user who placed the call.</span></span></p>
<p><span data-ttu-id="89de4-318">Esta coluna foi introduzida no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="89de4-318">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="89de4-319"><strong>CallerWiFiDriverVersion</strong></span><span class="sxs-lookup"><span data-stu-id="89de4-319"><strong>CallerWiFiDriverVersion</strong></span></span></p></td>
<td><p><span data-ttu-id="89de4-320">int</span><span class="sxs-lookup"><span data-stu-id="89de4-320">int</span></span></p></td>
<td><p><span data-ttu-id="89de4-321">Estrangeira</span><span class="sxs-lookup"><span data-stu-id="89de4-321">Foreign</span></span></p></td>
<td><p><span data-ttu-id="89de4-322">Número de versão para o driver WiFi empregado pelo usuário que fez a chamada.</span><span class="sxs-lookup"><span data-stu-id="89de4-322">Version number for the WiFi driver employed by the user who placed the call.</span></span></p>
<p><span data-ttu-id="89de4-323">Esta coluna foi introduzida no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="89de4-323">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="89de4-324"><strong>CalleReflexiveLocalIPAddr</strong></span><span class="sxs-lookup"><span data-stu-id="89de4-324"><strong>CalleReflexiveLocalIPAddr</strong></span></span></p></td>
<td><p><span data-ttu-id="89de4-325">int</span><span class="sxs-lookup"><span data-stu-id="89de4-325">int</span></span></p></td>
<td><p><span data-ttu-id="89de4-326">Estrangeira</span><span class="sxs-lookup"><span data-stu-id="89de4-326">Foreign</span></span></p></td>
<td><p><span data-ttu-id="89de4-327">Endereço IP reflexivo do usuário que recebeu a chamada.</span><span class="sxs-lookup"><span data-stu-id="89de4-327">Reflexive IP address of the user who received the call.</span></span> <span data-ttu-id="89de4-328">Nas organizações que usam o NAT (conversão de endereço de rede), o endereço IP reflexivo é o endereço IP do servidor proxy.</span><span class="sxs-lookup"><span data-stu-id="89de4-328">In organizations that use NAT (network address translation), the reflexive IP address is the IP address of the proxy server.</span></span></p>
<p><span data-ttu-id="89de4-329">Esta coluna foi introduzida no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="89de4-329">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="89de4-330"><strong>CalleeWiFiDriverDevicesDesc</strong></span><span class="sxs-lookup"><span data-stu-id="89de4-330"><strong>CalleeWiFiDriverDevicesDesc</strong></span></span></p></td>
<td><p><span data-ttu-id="89de4-331">int</span><span class="sxs-lookup"><span data-stu-id="89de4-331">int</span></span></p></td>
<td><p><span data-ttu-id="89de4-332">Estrangeira</span><span class="sxs-lookup"><span data-stu-id="89de4-332">Foreign</span></span></p></td>
<td><p><span data-ttu-id="89de4-333">Descrição do dispositivo para o driver WiFi empregado pelo usuário que recebeu a chamada.</span><span class="sxs-lookup"><span data-stu-id="89de4-333">Device description for the WiFi driver employed by the user who received the call.</span></span></p>
<p><span data-ttu-id="89de4-334">Esta coluna foi introduzida no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="89de4-334">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="89de4-335"><strong>CalleeWiFiDriverVersion</strong></span><span class="sxs-lookup"><span data-stu-id="89de4-335"><strong>CalleeWiFiDriverVersion</strong></span></span></p></td>
<td><p><span data-ttu-id="89de4-336">int</span><span class="sxs-lookup"><span data-stu-id="89de4-336">int</span></span></p></td>
<td><p><span data-ttu-id="89de4-337">Estrangeira</span><span class="sxs-lookup"><span data-stu-id="89de4-337">Foreign</span></span></p></td>
<td><p><span data-ttu-id="89de4-338">Número de versão para o driver WiFi empregado pelo usuário que recebeu a chamada.</span><span class="sxs-lookup"><span data-stu-id="89de4-338">Version number for the WiFi driver employed by the user who received the call.</span></span></p>
<p><span data-ttu-id="89de4-339">Esta coluna foi introduzida no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="89de4-339">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

