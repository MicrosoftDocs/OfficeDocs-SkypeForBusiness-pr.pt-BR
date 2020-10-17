---
title: 'Lync Server 2013: tabela de mídia'
description: 'Lync Server 2013: tabela de mídia.'
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
ms.openlocfilehash: 2acea8e14ba0608d9ebf72a48f888bfc4501fae3
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48572107"
---
# <a name="medialine-table-in-lync-server-2013"></a><span data-ttu-id="3c57f-103">Tabela de mídia no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3c57f-103">MediaLine table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3c57f-104">_**Última modificação do tópico:** 2014-02-21_</span><span class="sxs-lookup"><span data-stu-id="3c57f-104">_**Topic Last Modified:** 2014-02-21_</span></span>

<span data-ttu-id="3c57f-105">Cada registro representa uma linha de mídia.</span><span class="sxs-lookup"><span data-stu-id="3c57f-105">Each record represents one media line.</span></span> <span data-ttu-id="3c57f-106">(Uma sessão de áudio normalmente contém uma linha de mídia de áudio.</span><span class="sxs-lookup"><span data-stu-id="3c57f-106">(One audio session usually contains one audio media line.</span></span> <span data-ttu-id="3c57f-107">Uma sessão de áudio e vídeo (A/V) normalmente contém uma linha de mídia de áudio e uma linha de mídia de vídeo, embora a sessão possa conter duas linhas de mídia de vídeo se um dispositivo de conferência for usado ou se o modo de exibição de galeria for usado.</span><span class="sxs-lookup"><span data-stu-id="3c57f-107">One audio and video (A/V) session usually contains one audio media line and one video media line, although the session might contain two video media lines if a conferencing device is used or if Gallery View is used.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="3c57f-108"><strong>Coluna</strong></span><span class="sxs-lookup"><span data-stu-id="3c57f-108"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="3c57f-109"><strong>Tipo de dados</strong></span><span class="sxs-lookup"><span data-stu-id="3c57f-109"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="3c57f-110"><strong>Chave/índice</strong></span><span class="sxs-lookup"><span data-stu-id="3c57f-110"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="3c57f-111"><strong>Detalhes</strong></span><span class="sxs-lookup"><span data-stu-id="3c57f-111"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="3c57f-112"><strong>ConferenceDateTime</strong></span><span class="sxs-lookup"><span data-stu-id="3c57f-112"><strong>ConferenceDateTime</strong></span></span></p></td>
<td><p><span data-ttu-id="3c57f-113">datetime</span><span class="sxs-lookup"><span data-stu-id="3c57f-113">datetime</span></span></p></td>
<td><p><span data-ttu-id="3c57f-114">Primário</span><span class="sxs-lookup"><span data-stu-id="3c57f-114">Primary</span></span></p></td>
<td><p><span data-ttu-id="3c57f-115">Referenciado da <a href="lync-server-2013-session-table.md">tabela de sessão no Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="3c57f-115">Referenced from the <a href="lync-server-2013-session-table.md">Session table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3c57f-116"><strong>SessionSeq</strong></span><span class="sxs-lookup"><span data-stu-id="3c57f-116"><strong>SessionSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="3c57f-117">int</span><span class="sxs-lookup"><span data-stu-id="3c57f-117">int</span></span></p></td>
<td><p><span data-ttu-id="3c57f-118">Primário</span><span class="sxs-lookup"><span data-stu-id="3c57f-118">Primary</span></span></p></td>
<td><p><span data-ttu-id="3c57f-119">Referenciado da <a href="lync-server-2013-session-table.md">tabela de sessão no Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="3c57f-119">Referenced from the <a href="lync-server-2013-session-table.md">Session table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3c57f-120"><strong>MediaLineLabel</strong></span><span class="sxs-lookup"><span data-stu-id="3c57f-120"><strong>MediaLineLabel</strong></span></span></p></td>
<td><p><span data-ttu-id="3c57f-121">tinyint</span><span class="sxs-lookup"><span data-stu-id="3c57f-121">tinyint</span></span></p></td>
<td><p><span data-ttu-id="3c57f-122">Primário</span><span class="sxs-lookup"><span data-stu-id="3c57f-122">Primary</span></span></p></td>
<td><p><span data-ttu-id="3c57f-123">0 é o áudio principal, 1 é o vídeo principal e 2 é o vídeo panorâmico, 3 é o compartilhamento de aplicativo/área de trabalho.</span><span class="sxs-lookup"><span data-stu-id="3c57f-123">0 is main audio, 1 is main video, and 2 is panoramic video, 3 is Application/Desktop Sharing.</span></span> <span data-ttu-id="3c57f-124">Este rótulo deve ser exclusivo em uma única sessão.</span><span class="sxs-lookup"><span data-stu-id="3c57f-124">This label must be unique within a single session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3c57f-125"><strong>ConnectivityIce</strong></span><span class="sxs-lookup"><span data-stu-id="3c57f-125"><strong>ConnectivityIce</strong></span></span></p></td>
<td><p><span data-ttu-id="3c57f-126">tinyint</span><span class="sxs-lookup"><span data-stu-id="3c57f-126">tinyint</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="3c57f-127">Esta coluna está presente, mas não é usada no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="3c57f-127">This column is present but not used in Microsoft Lync Server 2013.</span></span> <span data-ttu-id="3c57f-128">As informações sobre a conectividade usada para uma linha de mídia são capturadas nas colunas CallerConnectivityICE e CalleeConnectivityICE.</span><span class="sxs-lookup"><span data-stu-id="3c57f-128">Information about the connectivity used for a media line is captured in the CallerConnectivityICE and CalleeConnectivityICE columns.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3c57f-129"><strong>CallerIceWarningFlags</strong></span><span class="sxs-lookup"><span data-stu-id="3c57f-129"><strong>CallerIceWarningFlags</strong></span></span></p></td>
<td><p><span data-ttu-id="3c57f-130">int</span><span class="sxs-lookup"><span data-stu-id="3c57f-130">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="3c57f-131">Informações sobre o processo de estabelecimento de conectividade interativa (ICE) descrito em sinalizadores de bits.</span><span class="sxs-lookup"><span data-stu-id="3c57f-131">Information about Interactive Connectivity Establishment (ICE) process described in bits flags.</span></span> <span data-ttu-id="3c57f-132">Para obter detalhes, consulte a <em>especificação de protocolo do Monitoring Server de qualidade da experiência</em>, disponível para download.</span><span class="sxs-lookup"><span data-stu-id="3c57f-132">For details, refer to the <em>Quality of Experience Monitoring Server Protocol Specification</em>, available for download.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3c57f-133"><strong>CalleeIceWarningFlags</strong></span><span class="sxs-lookup"><span data-stu-id="3c57f-133"><strong>CalleeIceWarningFlags</strong></span></span></p></td>
<td><p><span data-ttu-id="3c57f-134">int</span><span class="sxs-lookup"><span data-stu-id="3c57f-134">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="3c57f-135">O mesmo que CallerIceWarningFlags, mas no lado do receptor.</span><span class="sxs-lookup"><span data-stu-id="3c57f-135">Same as CallerIceWarningFlags, but on the callee side.</span></span> <span data-ttu-id="3c57f-136">Para obter detalhes, consulte a <em>especificação de protocolo do Monitoring Server de qualidade da experiência</em>, disponível para download.</span><span class="sxs-lookup"><span data-stu-id="3c57f-136">For details, refer to the <em>Quality of Experience Monitoring Server Protocol Specification</em>, available for download.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3c57f-137"><strong>Segurança</strong></span><span class="sxs-lookup"><span data-stu-id="3c57f-137"><strong>Security</strong></span></span></p></td>
<td><p><span data-ttu-id="3c57f-138">tinyint</span><span class="sxs-lookup"><span data-stu-id="3c57f-138">tinyint</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="3c57f-139">O perfil de segurança em uso.</span><span class="sxs-lookup"><span data-stu-id="3c57f-139">The security profile in use.</span></span> <span data-ttu-id="3c57f-140">0 é NONE (nenhum), 1 é SRTP, 2 é V1.</span><span class="sxs-lookup"><span data-stu-id="3c57f-140">0 is NONE, 1 is SRTP, 2 is V1.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3c57f-141"><strong>Transport</strong></span><span class="sxs-lookup"><span data-stu-id="3c57f-141"><strong>Transport</strong></span></span></p></td>
<td><p><span data-ttu-id="3c57f-142">tinyint</span><span class="sxs-lookup"><span data-stu-id="3c57f-142">tinyint</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="3c57f-143">0 é UDP, 1 é TCP.</span><span class="sxs-lookup"><span data-stu-id="3c57f-143">0 is UDP, 1 is TCP.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3c57f-144"><strong>CallerIPAddr</strong></span><span class="sxs-lookup"><span data-stu-id="3c57f-144"><strong>CallerIPAddr</strong></span></span></p></td>
<td><p><span data-ttu-id="3c57f-145">int</span><span class="sxs-lookup"><span data-stu-id="3c57f-145">int</span></span></p></td>
<td><p><span data-ttu-id="3c57f-146">Estrangeira</span><span class="sxs-lookup"><span data-stu-id="3c57f-146">Foreign</span></span></p></td>
<td><p><span data-ttu-id="3c57f-147">Endereço IP do chamador.</span><span class="sxs-lookup"><span data-stu-id="3c57f-147">IP Address of the caller.</span></span> <span data-ttu-id="3c57f-148">Consulte a <a href="lync-server-2013-ipaddress-table.md">tabela IPAddress no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="3c57f-148">See the <a href="lync-server-2013-ipaddress-table.md">IPAddress table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3c57f-149"><strong>CallerPort</strong></span><span class="sxs-lookup"><span data-stu-id="3c57f-149"><strong>CallerPort</strong></span></span></p></td>
<td><p><span data-ttu-id="3c57f-150">int</span><span class="sxs-lookup"><span data-stu-id="3c57f-150">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="3c57f-151">Porta usada pelo chamador.</span><span class="sxs-lookup"><span data-stu-id="3c57f-151">Port used by the caller.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3c57f-152"><strong>CallerSubnet</strong></span><span class="sxs-lookup"><span data-stu-id="3c57f-152"><strong>CallerSubnet</strong></span></span></p></td>
<td><p><span data-ttu-id="3c57f-153">int</span><span class="sxs-lookup"><span data-stu-id="3c57f-153">int</span></span></p></td>
<td><p><span data-ttu-id="3c57f-154"> Estrangeira</span><span class="sxs-lookup"><span data-stu-id="3c57f-154"> Foreign</span></span></p></td>
<td><p><span data-ttu-id="3c57f-155">A sub-rede do chamador.</span><span class="sxs-lookup"><span data-stu-id="3c57f-155">The subnet of the caller.</span></span> <span data-ttu-id="3c57f-156">Consulte a <a href="lync-server-2013-ipaddress-table.md">tabela IPAddress no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="3c57f-156">See the <a href="lync-server-2013-ipaddress-table.md">IPAddress table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3c57f-157"><strong>CallerInside</strong></span><span class="sxs-lookup"><span data-stu-id="3c57f-157"><strong>CallerInside</strong></span></span></p></td>
<td><p><span data-ttu-id="3c57f-158">bits</span><span class="sxs-lookup"><span data-stu-id="3c57f-158">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="3c57f-159">1 significa que o chamador está dentro da rede da empresa, 0 significa que o chamador está fora da rede.</span><span class="sxs-lookup"><span data-stu-id="3c57f-159">1 means caller is inside the enterprise network, 0 means the caller is outside the network.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3c57f-160"><strong>CallerMacAddress</strong></span><span class="sxs-lookup"><span data-stu-id="3c57f-160"><strong>CallerMacAddress</strong></span></span></p></td>
<td><p><span data-ttu-id="3c57f-161">int</span><span class="sxs-lookup"><span data-stu-id="3c57f-161">int</span></span></p></td>
<td><p><span data-ttu-id="3c57f-162">Estrangeira</span><span class="sxs-lookup"><span data-stu-id="3c57f-162">Foreign</span></span></p></td>
<td><p><span data-ttu-id="3c57f-163">Endereço MAC do chamador, referenciado da <a href="lync-server-2013-macaddress-table.md">tabela MACAddress no Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="3c57f-163">Caller’s mac address, referenced from <a href="lync-server-2013-macaddress-table.md">MacAddress table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3c57f-164"><strong>CallerRelayIPAddr</strong></span><span class="sxs-lookup"><span data-stu-id="3c57f-164"><strong>CallerRelayIPAddr</strong></span></span></p></td>
<td><p><span data-ttu-id="3c57f-165">int</span><span class="sxs-lookup"><span data-stu-id="3c57f-165">int</span></span></p></td>
<td><p><span data-ttu-id="3c57f-166">Estrangeira</span><span class="sxs-lookup"><span data-stu-id="3c57f-166">Foreign</span></span></p></td>
<td><p><span data-ttu-id="3c57f-167">Endereço IP do serviço de borda a/V do Lync Server usado pelo chamador.</span><span class="sxs-lookup"><span data-stu-id="3c57f-167">IP Address of the Lync Server A/V Edge service used by the caller.</span></span> <span data-ttu-id="3c57f-168">Consulte a <a href="lync-server-2013-ipaddress-table.md">tabela IPAddress no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="3c57f-168">See the <a href="lync-server-2013-ipaddress-table.md">IPAddress table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3c57f-169"><strong>CallerRelayPort</strong></span><span class="sxs-lookup"><span data-stu-id="3c57f-169"><strong>CallerRelayPort</strong></span></span></p></td>
<td><p><span data-ttu-id="3c57f-170">int</span><span class="sxs-lookup"><span data-stu-id="3c57f-170">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="3c57f-171">Porta usada no serviço de borda A/V pelo chamador.</span><span class="sxs-lookup"><span data-stu-id="3c57f-171">Port used on the A/V Edge service by the caller.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3c57f-172"><strong>CallerCaptureDev</strong></span><span class="sxs-lookup"><span data-stu-id="3c57f-172"><strong>CallerCaptureDev</strong></span></span></p></td>
<td><p><span data-ttu-id="3c57f-173">int</span><span class="sxs-lookup"><span data-stu-id="3c57f-173">int</span></span></p></td>
<td><p><span data-ttu-id="3c57f-174">Estrangeira</span><span class="sxs-lookup"><span data-stu-id="3c57f-174">Foreign</span></span></p></td>
<td><p><span data-ttu-id="3c57f-175">Dispositivo de captura usado pelo chamador.</span><span class="sxs-lookup"><span data-stu-id="3c57f-175">Capture device used by the caller.</span></span> <span data-ttu-id="3c57f-176">Referenciado da <a href="lync-server-2013-device-table.md">tabela Device no Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="3c57f-176">Referenced from the <a href="lync-server-2013-device-table.md">Device table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3c57f-177"><strong>CallerRenderDev</strong></span><span class="sxs-lookup"><span data-stu-id="3c57f-177"><strong>CallerRenderDev</strong></span></span></p></td>
<td><p><span data-ttu-id="3c57f-178">int</span><span class="sxs-lookup"><span data-stu-id="3c57f-178">int</span></span></p></td>
<td><p><span data-ttu-id="3c57f-179">Estrangeira</span><span class="sxs-lookup"><span data-stu-id="3c57f-179">Foreign</span></span></p></td>
<td><p><span data-ttu-id="3c57f-180">Dispositivo de renderização usado pelo chamador.</span><span class="sxs-lookup"><span data-stu-id="3c57f-180">Render device used by caller.</span></span> <span data-ttu-id="3c57f-181">Referenciado da <a href="lync-server-2013-device-table.md">tabela Device no Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="3c57f-181">Referenced from the <a href="lync-server-2013-device-table.md">Device table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3c57f-182"><strong>CallerCaptureDevDriver</strong></span><span class="sxs-lookup"><span data-stu-id="3c57f-182"><strong>CallerCaptureDevDriver</strong></span></span></p></td>
<td><p><span data-ttu-id="3c57f-183">int</span><span class="sxs-lookup"><span data-stu-id="3c57f-183">int</span></span></p></td>
<td><p><span data-ttu-id="3c57f-184">Estrangeira</span><span class="sxs-lookup"><span data-stu-id="3c57f-184">Foreign</span></span></p></td>
<td><p><span data-ttu-id="3c57f-185">Driver do dispositivo de captura do chamador, referenciado na <a href="lync-server-2013-devicedriver-table.md">tabela DeviceDriver no Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="3c57f-185">Driver for the caller’s capture device, referenced from the <a href="lync-server-2013-devicedriver-table.md">DeviceDriver table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3c57f-186"><strong>CallerRenderDevDriver</strong></span><span class="sxs-lookup"><span data-stu-id="3c57f-186"><strong>CallerRenderDevDriver</strong></span></span></p></td>
<td><p><span data-ttu-id="3c57f-187">int</span><span class="sxs-lookup"><span data-stu-id="3c57f-187">int</span></span></p></td>
<td><p><span data-ttu-id="3c57f-188">Estrangeira</span><span class="sxs-lookup"><span data-stu-id="3c57f-188">Foreign</span></span></p></td>
<td><p><span data-ttu-id="3c57f-189">Driver do dispositivo de renderização do chamador, referenciado da <a href="lync-server-2013-devicedriver-table.md">tabela DeviceDriver no Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="3c57f-189">Driver for the caller’s render device, referenced from the <a href="lync-server-2013-devicedriver-table.md">DeviceDriver table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3c57f-190"><strong>CallerNetworkConnectionType</strong></span><span class="sxs-lookup"><span data-stu-id="3c57f-190"><strong>CallerNetworkConnectionType</strong></span></span></p></td>
<td><p><span data-ttu-id="3c57f-191">tinyint</span><span class="sxs-lookup"><span data-stu-id="3c57f-191">tinyint</span></span></p></td>
<td><p><span data-ttu-id="3c57f-192">Estrangeira</span><span class="sxs-lookup"><span data-stu-id="3c57f-192">Foreign</span></span></p></td>
<td><p><span data-ttu-id="3c57f-193">Indica como o chamador se conectou à rede.</span><span class="sxs-lookup"><span data-stu-id="3c57f-193">Indicates how the caller connected to the network.</span></span> <span data-ttu-id="3c57f-194">Os valores são obtidos da <a href="lync-server-2013-networkconnectiondetail-table.md">tabela NetworkConnectionDetail no Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="3c57f-194">Values are obtained from the <a href="lync-server-2013-networkconnectiondetail-table.md">NetworkConnectionDetail table in Lync Server 2013</a>.</span></span> <span data-ttu-id="3c57f-195">Os valores típicos são 0 para uma conexão com fio ' 1 para uma conexão WiFi; e 3 para uma conexão Ethernet.</span><span class="sxs-lookup"><span data-stu-id="3c57f-195">Typical values are 0 for a wired connection’ 1 for a WiFi connection; and 3 for an Ethernet connection.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3c57f-196"><strong>CallerBssid</strong></span><span class="sxs-lookup"><span data-stu-id="3c57f-196"><strong>CallerBssid</strong></span></span></p></td>
<td><p><span data-ttu-id="3c57f-197">int</span><span class="sxs-lookup"><span data-stu-id="3c57f-197">int</span></span></p></td>
<td><p><span data-ttu-id="3c57f-198">Estrangeira</span><span class="sxs-lookup"><span data-stu-id="3c57f-198">Foreign</span></span></p></td>
<td><p><span data-ttu-id="3c57f-199">BSSID do chamador se for usado sem fio.</span><span class="sxs-lookup"><span data-stu-id="3c57f-199">Caller’s BSSID if wireless is used.</span></span> <span data-ttu-id="3c57f-200">Referenciado da <a href="lync-server-2013-macaddress-table.md">tabela MACAddress no Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="3c57f-200">Referenced from <a href="lync-server-2013-macaddress-table.md">MacAddress table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3c57f-201"><strong>CallerVPN</strong></span><span class="sxs-lookup"><span data-stu-id="3c57f-201"><strong>CallerVPN</strong></span></span></p></td>
<td><p><span data-ttu-id="3c57f-202">bits</span><span class="sxs-lookup"><span data-stu-id="3c57f-202">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="3c57f-203">O link do chamador.</span><span class="sxs-lookup"><span data-stu-id="3c57f-203">The caller's link.</span></span> <span data-ttu-id="3c57f-204">1 é para rede virtual privada (VPN), 0 é para não-VPN.</span><span class="sxs-lookup"><span data-stu-id="3c57f-204">1 is virtual private network (VPN), 0 is non-VPN.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3c57f-205"><strong>CallerLinkSpeed</strong></span><span class="sxs-lookup"><span data-stu-id="3c57f-205"><strong>CallerLinkSpeed</strong></span></span></p></td>
<td><p><span data-ttu-id="3c57f-206">decimal (18, 0)</span><span class="sxs-lookup"><span data-stu-id="3c57f-206">decimal(18,0)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="3c57f-207">A velocidade do link de rede, em bps, para o ponto de extremidade do chamador.</span><span class="sxs-lookup"><span data-stu-id="3c57f-207">The network link speed, in bps, for the caller's endpoint.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3c57f-208"><strong>CalleeIPAddr</strong></span><span class="sxs-lookup"><span data-stu-id="3c57f-208"><strong>CalleeIPAddr</strong></span></span></p></td>
<td><p><span data-ttu-id="3c57f-209">int</span><span class="sxs-lookup"><span data-stu-id="3c57f-209">int</span></span></p></td>
<td><p><span data-ttu-id="3c57f-210">Estrangeira</span><span class="sxs-lookup"><span data-stu-id="3c57f-210">Foreign</span></span></p></td>
<td><p><span data-ttu-id="3c57f-211">Endereço IP do receptor de chamada.</span><span class="sxs-lookup"><span data-stu-id="3c57f-211">IP Address of the call receiver.</span></span> <span data-ttu-id="3c57f-212">Consulte a <a href="lync-server-2013-ipaddress-table.md">tabela IPAddress no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="3c57f-212">See the <a href="lync-server-2013-ipaddress-table.md">IPAddress table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3c57f-213"><strong>CalleePort</strong></span><span class="sxs-lookup"><span data-stu-id="3c57f-213"><strong>CalleePort</strong></span></span></p></td>
<td><p><span data-ttu-id="3c57f-214">bits</span><span class="sxs-lookup"><span data-stu-id="3c57f-214">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="3c57f-215">Porta usada pelo receptor de chamada.</span><span class="sxs-lookup"><span data-stu-id="3c57f-215">Port used by the call receiver.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3c57f-216"><strong>CalleeSubnet</strong></span><span class="sxs-lookup"><span data-stu-id="3c57f-216"><strong>CalleeSubnet</strong></span></span></p></td>
<td><p><span data-ttu-id="3c57f-217">int</span><span class="sxs-lookup"><span data-stu-id="3c57f-217">int</span></span></p></td>
<td><p><span data-ttu-id="3c57f-218">Estrangeira</span><span class="sxs-lookup"><span data-stu-id="3c57f-218">Foreign</span></span></p></td>
<td><p><span data-ttu-id="3c57f-219">Sub-rede do receptor.</span><span class="sxs-lookup"><span data-stu-id="3c57f-219">Subnet of callee.</span></span> <span data-ttu-id="3c57f-220">Consulte a <a href="lync-server-2013-ipaddress-table.md">tabela IPAddress no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="3c57f-220">See the <a href="lync-server-2013-ipaddress-table.md">IPAddress table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3c57f-221"><strong>CalleeInside</strong></span><span class="sxs-lookup"><span data-stu-id="3c57f-221"><strong>CalleeInside</strong></span></span></p></td>
<td><p><span data-ttu-id="3c57f-222">bits</span><span class="sxs-lookup"><span data-stu-id="3c57f-222">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="3c57f-223">1 significa que o receptor de chamada está dentro da rede corporativa, 0 significa que o receptor de chamadas está fora da rede.</span><span class="sxs-lookup"><span data-stu-id="3c57f-223">1 means call receiver is inside the enterprise network, 0 means the call receiver is outside the network.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3c57f-224"><strong>CalleeMacAddress</strong></span><span class="sxs-lookup"><span data-stu-id="3c57f-224"><strong>CalleeMacAddress</strong></span></span></p></td>
<td><p><span data-ttu-id="3c57f-225">int</span><span class="sxs-lookup"><span data-stu-id="3c57f-225">int</span></span></p></td>
<td><p><span data-ttu-id="3c57f-226">Estrangeira</span><span class="sxs-lookup"><span data-stu-id="3c57f-226">Foreign</span></span></p></td>
<td><p><span data-ttu-id="3c57f-227">Endereço MAC do receptor.</span><span class="sxs-lookup"><span data-stu-id="3c57f-227">Callee Mac address.</span></span> <span data-ttu-id="3c57f-228">Referenciado da <a href="lync-server-2013-macaddress-table.md">tabela MACAddress no Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="3c57f-228">Referenced from the <a href="lync-server-2013-macaddress-table.md">MacAddress table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3c57f-229"><strong>CalleeRelayIPAddr</strong></span><span class="sxs-lookup"><span data-stu-id="3c57f-229"><strong>CalleeRelayIPAddr</strong></span></span></p></td>
<td><p><span data-ttu-id="3c57f-230">int</span><span class="sxs-lookup"><span data-stu-id="3c57f-230">int</span></span></p></td>
<td><p><span data-ttu-id="3c57f-231">Estrangeira</span><span class="sxs-lookup"><span data-stu-id="3c57f-231">Foreign</span></span></p></td>
<td><p><span data-ttu-id="3c57f-232">Endereço IP do serviço de borda A/V usado pelo receptor de chamada.</span><span class="sxs-lookup"><span data-stu-id="3c57f-232">IP Address of the A/V Edge service used by the call receiver.</span></span> <span data-ttu-id="3c57f-233">Consulte a <a href="lync-server-2013-ipaddress-table.md">tabela IPAddress no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="3c57f-233">See the <a href="lync-server-2013-ipaddress-table.md">IPAddress table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3c57f-234"><strong>CalleeRelayPort</strong></span><span class="sxs-lookup"><span data-stu-id="3c57f-234"><strong>CalleeRelayPort</strong></span></span></p></td>
<td><p><span data-ttu-id="3c57f-235">int</span><span class="sxs-lookup"><span data-stu-id="3c57f-235">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="3c57f-236">Porta usada no serviço de borda A/V pelo receptor de chamada.</span><span class="sxs-lookup"><span data-stu-id="3c57f-236">Port used on the A/V Edge Service by the call receiver.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3c57f-237"><strong>CalleeCaptureDev</strong></span><span class="sxs-lookup"><span data-stu-id="3c57f-237"><strong>CalleeCaptureDev</strong></span></span></p></td>
<td><p><span data-ttu-id="3c57f-238">int</span><span class="sxs-lookup"><span data-stu-id="3c57f-238">int</span></span></p></td>
<td><p><span data-ttu-id="3c57f-239">estrangeira</span><span class="sxs-lookup"><span data-stu-id="3c57f-239">foreign</span></span></p></td>
<td><p><span data-ttu-id="3c57f-240">Dispositivo de captura usado pelo receptor de chamada.</span><span class="sxs-lookup"><span data-stu-id="3c57f-240">Capture device used by the call receiver.</span></span> <span data-ttu-id="3c57f-241">Referenciado da <a href="lync-server-2013-device-table.md">tabela Device no Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="3c57f-241">Referenced from the <a href="lync-server-2013-device-table.md">Device table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3c57f-242"><strong>CalleeRenderDev</strong></span><span class="sxs-lookup"><span data-stu-id="3c57f-242"><strong>CalleeRenderDev</strong></span></span></p></td>
<td><p><span data-ttu-id="3c57f-243">int</span><span class="sxs-lookup"><span data-stu-id="3c57f-243">int</span></span></p></td>
<td><p><span data-ttu-id="3c57f-244">Estrangeira</span><span class="sxs-lookup"><span data-stu-id="3c57f-244">Foreign</span></span></p></td>
<td><p><span data-ttu-id="3c57f-245">Dispositivo de renderização usado pelo receptor de chamada.</span><span class="sxs-lookup"><span data-stu-id="3c57f-245">Render device used by the call receiver.</span></span> <span data-ttu-id="3c57f-246">Referenciado da <a href="lync-server-2013-device-table.md">tabela Device no Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="3c57f-246">Referenced from the <a href="lync-server-2013-device-table.md">Device table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3c57f-247"><strong>CalleeCaptureDevDriver</strong></span><span class="sxs-lookup"><span data-stu-id="3c57f-247"><strong>CalleeCaptureDevDriver</strong></span></span></p></td>
<td><p><span data-ttu-id="3c57f-248">int</span><span class="sxs-lookup"><span data-stu-id="3c57f-248">int</span></span></p></td>
<td><p><span data-ttu-id="3c57f-249">Estrangeira</span><span class="sxs-lookup"><span data-stu-id="3c57f-249">Foreign</span></span></p></td>
<td><p><span data-ttu-id="3c57f-250">Driver do dispositivo de captura do receptor de chamada.</span><span class="sxs-lookup"><span data-stu-id="3c57f-250">Driver for the call receiver’s capture device.</span></span> <span data-ttu-id="3c57f-251">Referenciado da <a href="lync-server-2013-devicedriver-table.md">tabela DeviceDriver no Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="3c57f-251">Referenced from <a href="lync-server-2013-devicedriver-table.md">DeviceDriver table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3c57f-252"><strong>CalleeRenderDevDriver</strong></span><span class="sxs-lookup"><span data-stu-id="3c57f-252"><strong>CalleeRenderDevDriver</strong></span></span></p></td>
<td><p><span data-ttu-id="3c57f-253">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="3c57f-253">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="3c57f-254">Estrangeira</span><span class="sxs-lookup"><span data-stu-id="3c57f-254">Foreign</span></span></p></td>
<td><p><span data-ttu-id="3c57f-255">Driver para o dispositivo de renderização do receptor de chamada.</span><span class="sxs-lookup"><span data-stu-id="3c57f-255">Driver for the call receiver’s render device.</span></span> <span data-ttu-id="3c57f-256">Referenciado da <a href="lync-server-2013-devicedriver-table.md">tabela DeviceDriver no Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="3c57f-256">Referenced from <a href="lync-server-2013-devicedriver-table.md">DeviceDriver table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3c57f-257"><strong>CalleeNetworkConnectionType</strong></span><span class="sxs-lookup"><span data-stu-id="3c57f-257"><strong>CalleeNetworkConnectionType</strong></span></span></p></td>
<td><p><span data-ttu-id="3c57f-258">tinyint</span><span class="sxs-lookup"><span data-stu-id="3c57f-258">tinyint</span></span></p></td>
<td><p><span data-ttu-id="3c57f-259">Estrangeira</span><span class="sxs-lookup"><span data-stu-id="3c57f-259">Foreign</span></span></p></td>
<td><p><span data-ttu-id="3c57f-260">Indica como o receptor está conectado à rede.</span><span class="sxs-lookup"><span data-stu-id="3c57f-260">Indicates how the callee connected to the network.</span></span> <span data-ttu-id="3c57f-261">Os valores são obtidos da <a href="lync-server-2013-networkconnectiondetail-table.md">tabela NetworkConnectionDetail no Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="3c57f-261">Values are obtained from the <a href="lync-server-2013-networkconnectiondetail-table.md">NetworkConnectionDetail table in Lync Server 2013</a>.</span></span> <span data-ttu-id="3c57f-262">Os valores típicos são 0 para uma conexão com fio ' 1 para uma conexão WiFi; e 3 para uma conexão Ethernet.</span><span class="sxs-lookup"><span data-stu-id="3c57f-262">Typical values are 0 for a wired connection’ 1 for a WiFi connection; and 3 for an Ethernet connection.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3c57f-263"><strong>CalleeBssid</strong></span><span class="sxs-lookup"><span data-stu-id="3c57f-263"><strong>CalleeBssid</strong></span></span></p></td>
<td><p><span data-ttu-id="3c57f-264">int</span><span class="sxs-lookup"><span data-stu-id="3c57f-264">int</span></span></p></td>
<td><p><span data-ttu-id="3c57f-265">Estrangeira</span><span class="sxs-lookup"><span data-stu-id="3c57f-265">Foreign</span></span></p></td>
<td><p><span data-ttu-id="3c57f-266">BSSID do receptor da chamada se for usado sem fio.</span><span class="sxs-lookup"><span data-stu-id="3c57f-266">Callee’s BSSID if wireless is used.</span></span> <span data-ttu-id="3c57f-267">Referenciado da <a href="lync-server-2013-macaddress-table.md">tabela MACAddress no Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="3c57f-267">Referenced from <a href="lync-server-2013-macaddress-table.md">MacAddress table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3c57f-268"><strong>CalleeVPN</strong></span><span class="sxs-lookup"><span data-stu-id="3c57f-268"><strong>CalleeVPN</strong></span></span></p></td>
<td><p><span data-ttu-id="3c57f-269">bits</span><span class="sxs-lookup"><span data-stu-id="3c57f-269">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="3c57f-270">O link do receptor de chamada; 1 é VPN (rede virtual privada), 0 não é VPN.</span><span class="sxs-lookup"><span data-stu-id="3c57f-270">The call receiver’s link; 1 is virtual private network (VPN), 0 is non-VPN.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3c57f-271"><strong>CalleeLinkSpeed</strong></span><span class="sxs-lookup"><span data-stu-id="3c57f-271"><strong>CalleeLinkSpeed</strong></span></span></p></td>
<td><p><span data-ttu-id="3c57f-272">decimal (18, 0)</span><span class="sxs-lookup"><span data-stu-id="3c57f-272">decimal(18,0)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="3c57f-273">A velocidade do link de rede, em bps, para o ponto de extremidade do receptor de chamada.</span><span class="sxs-lookup"><span data-stu-id="3c57f-273">The network link speed, in bps, for the call receiver’s endpoint.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3c57f-274"><strong>ConversationalMOS</strong></span><span class="sxs-lookup"><span data-stu-id="3c57f-274"><strong>ConversationalMOS</strong></span></span></p></td>
<td><p><span data-ttu-id="3c57f-275">decimal (3, 2)</span><span class="sxs-lookup"><span data-stu-id="3c57f-275">decimal(3,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="3c57f-276">MOS da Conversa de Banda Estreita das sessões de áudio (com base nos dois fluxos de áudio).</span><span class="sxs-lookup"><span data-stu-id="3c57f-276">Narrowband Conversational MOS of the audio sessions (based on both audio streams).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3c57f-277"><strong>AppliedBandwidthLimit</strong></span><span class="sxs-lookup"><span data-stu-id="3c57f-277"><strong>AppliedBandwidthLimit</strong></span></span></p></td>
<td><p><span data-ttu-id="3c57f-278">int</span><span class="sxs-lookup"><span data-stu-id="3c57f-278">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="3c57f-279">Esta é a largura de banda real aplicada ao fluxo de envio enviado fornecido por várias configurações de política (TURN, API, SDP, servidor de política e assim por diante).</span><span class="sxs-lookup"><span data-stu-id="3c57f-279">This is the actual bandwidth applied to the given send side stream given various policy settings (TURN, API, SDP, Policy Server, and so on).</span></span> <span data-ttu-id="3c57f-280">Isso não deve ser confundido com a largura de banda efetiva porque pode haver uma largura de banda efetiva menor com base na estimativa de largura de banda.</span><span class="sxs-lookup"><span data-stu-id="3c57f-280">This is not to be confused with the effective bandwidth because there can be a lower effective bandwidth based on the bandwidth estimate.</span></span> <span data-ttu-id="3c57f-281">Esta é basicamente a largura de banda máxima que o stream de envio pode utilizar dos limites impostos pela estimativa de largura de banda.</span><span class="sxs-lookup"><span data-stu-id="3c57f-281">This is basically the maximum bandwidth the send stream can take barring limits imposed by the bandwidth estimate.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3c57f-282"><strong>AppliedBandwidthSourceKey</strong></span><span class="sxs-lookup"><span data-stu-id="3c57f-282"><strong>AppliedBandwidthSourceKey</strong></span></span></p></td>
<td><p><span data-ttu-id="3c57f-283">smallint</span><span class="sxs-lookup"><span data-stu-id="3c57f-283">smallint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="3c57f-284">Essa é a origem do cap de largura de banda que está sendo imposto.</span><span class="sxs-lookup"><span data-stu-id="3c57f-284">This is the source of the bandwidth cap being imposed.</span></span> <span data-ttu-id="3c57f-285">Descreve de onde o limite de largura de banda está vindo ("servidor de política", "Ativar servidor", "modalidade" e assim por diante).</span><span class="sxs-lookup"><span data-stu-id="3c57f-285">It describes where the bandwidth limit is coming from (“Policy Server”, “TURN Server”, “Modality”, and so on).</span></span> <span data-ttu-id="3c57f-286">Referenciado da <a href="lync-server-2013-appliedbandwidthsource-table.md">tabela AppliedBandwidthSource no Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="3c57f-286">Referenced from the <a href="lync-server-2013-appliedbandwidthsource-table.md">AppliedBandwidthSource table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3c57f-287"><strong>Caller</strong></span><span class="sxs-lookup"><span data-stu-id="3c57f-287"><strong>Caller</strong></span></span></p></td>
<td><p><span data-ttu-id="3c57f-288">bits</span><span class="sxs-lookup"><span data-stu-id="3c57f-288">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="3c57f-289">Indica se as métricas do chamador foram recebidas; 1 é sim, um valor nulo é não.</span><span class="sxs-lookup"><span data-stu-id="3c57f-289">Indicates whether metrics from the caller were received; 1 is yes, a null value is no.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3c57f-290"><strong>Receptor</strong></span><span class="sxs-lookup"><span data-stu-id="3c57f-290"><strong>Callee</strong></span></span></p></td>
<td><p><span data-ttu-id="3c57f-291">bits</span><span class="sxs-lookup"><span data-stu-id="3c57f-291">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="3c57f-292">Indica se as métricas do receptor de chamada foram recebidas; 1 é sim, um valor nulo é não.</span><span class="sxs-lookup"><span data-stu-id="3c57f-292">Indicates whether metrics from the call receiver were received; 1 is yes, a null value is no.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3c57f-293"><strong>MidCallReport</strong></span><span class="sxs-lookup"><span data-stu-id="3c57f-293"><strong>MidCallReport</strong></span></span></p></td>
<td><p><span data-ttu-id="3c57f-294">bits</span><span class="sxs-lookup"><span data-stu-id="3c57f-294">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="3c57f-295">Indica se o relatório é para uma parte da sessão ou para a sessão completa.</span><span class="sxs-lookup"><span data-stu-id="3c57f-295">Indicates whether the report is for a portion of the session or for the complete session.</span></span></p>
<p><span data-ttu-id="3c57f-296">Esta coluna foi introduzida no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="3c57f-296">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3c57f-297"><strong>ClassifiedPoorCall</strong></span><span class="sxs-lookup"><span data-stu-id="3c57f-297"><strong>ClassifiedPoorCall</strong></span></span></p></td>
<td><p><span data-ttu-id="3c57f-298">bits</span><span class="sxs-lookup"><span data-stu-id="3c57f-298">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="3c57f-299">Indica se uma chamada foi classificada como uma chamada ruim (valor 1) ou como uma boa chamada (0).</span><span class="sxs-lookup"><span data-stu-id="3c57f-299">Indicates whether a call was classified as a poor call (value of 1) or as a good call (0).</span></span></p>
<p><span data-ttu-id="3c57f-300">Esta coluna foi introduzida no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="3c57f-300">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3c57f-301"><strong>CallerConnectivityICE</strong></span><span class="sxs-lookup"><span data-stu-id="3c57f-301"><strong>CallerConnectivityICE</strong></span></span></p></td>
<td><p><span data-ttu-id="3c57f-302">tinyInt</span><span class="sxs-lookup"><span data-stu-id="3c57f-302">tinyInt</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="3c57f-303">Indica se o chamador se conectou à rede usando o protocolo ICE (Internet Connectivity Establishment).</span><span class="sxs-lookup"><span data-stu-id="3c57f-303">Indicates whether the caller connected to the network using the ICE protocol (Internet Connectivity Establishment).</span></span></p>
<p><span data-ttu-id="3c57f-304">Esta coluna foi introduzida no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="3c57f-304">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3c57f-305"><strong>CalleeConnectivityICE</strong></span><span class="sxs-lookup"><span data-stu-id="3c57f-305"><strong>CalleeConnectivityICE</strong></span></span></p></td>
<td><p><span data-ttu-id="3c57f-306">tinyint</span><span class="sxs-lookup"><span data-stu-id="3c57f-306">tinyint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="3c57f-307">Indica se o chamador se conectou à rede usando o protocolo ICE (Internet Connectivity Establishment).</span><span class="sxs-lookup"><span data-stu-id="3c57f-307">Indicates whether the caller connected to the network using the ICE protocol (Internet Connectivity Establishment).</span></span></p>
<p><span data-ttu-id="3c57f-308">Esta coluna foi introduzida no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="3c57f-308">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3c57f-309"><strong>CallerReflexiveLocalIPAddr</strong></span><span class="sxs-lookup"><span data-stu-id="3c57f-309"><strong>CallerReflexiveLocalIPAddr</strong></span></span></p></td>
<td><p><span data-ttu-id="3c57f-310">int</span><span class="sxs-lookup"><span data-stu-id="3c57f-310">int</span></span></p></td>
<td><p><span data-ttu-id="3c57f-311">Estrangeira</span><span class="sxs-lookup"><span data-stu-id="3c57f-311">Foreign</span></span></p></td>
<td><p><span data-ttu-id="3c57f-312">Endereço IP reflexivo do usuário que fez a chamada.</span><span class="sxs-lookup"><span data-stu-id="3c57f-312">Reflexive IP address of the user who placed the call.</span></span> <span data-ttu-id="3c57f-313">Nas organizações que usam o NAT (conversão de endereço de rede), o endereço IP reflexivo é o endereço IP do servidor proxy.</span><span class="sxs-lookup"><span data-stu-id="3c57f-313">In organizations that use NAT (network address translation), the reflexive IP address is the IP address of the proxy server.</span></span></p>
<p><span data-ttu-id="3c57f-314">Esta coluna foi introduzida no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="3c57f-314">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3c57f-315"><strong>CallerWiFiDriverDevicesDesc</strong></span><span class="sxs-lookup"><span data-stu-id="3c57f-315"><strong>CallerWiFiDriverDevicesDesc</strong></span></span></p></td>
<td><p><span data-ttu-id="3c57f-316">int</span><span class="sxs-lookup"><span data-stu-id="3c57f-316">int</span></span></p></td>
<td><p><span data-ttu-id="3c57f-317">Estrangeira</span><span class="sxs-lookup"><span data-stu-id="3c57f-317">Foreign</span></span></p></td>
<td><p><span data-ttu-id="3c57f-318">Descrição do dispositivo para o driver WiFi empregado pelo usuário que fez a chamada.</span><span class="sxs-lookup"><span data-stu-id="3c57f-318">Device description for the WiFi driver employed by the user who placed the call.</span></span></p>
<p><span data-ttu-id="3c57f-319">Esta coluna foi introduzida no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="3c57f-319">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3c57f-320"><strong>CallerWiFiDriverVersion</strong></span><span class="sxs-lookup"><span data-stu-id="3c57f-320"><strong>CallerWiFiDriverVersion</strong></span></span></p></td>
<td><p><span data-ttu-id="3c57f-321">int</span><span class="sxs-lookup"><span data-stu-id="3c57f-321">int</span></span></p></td>
<td><p><span data-ttu-id="3c57f-322">Estrangeira</span><span class="sxs-lookup"><span data-stu-id="3c57f-322">Foreign</span></span></p></td>
<td><p><span data-ttu-id="3c57f-323">Número de versão para o driver WiFi empregado pelo usuário que fez a chamada.</span><span class="sxs-lookup"><span data-stu-id="3c57f-323">Version number for the WiFi driver employed by the user who placed the call.</span></span></p>
<p><span data-ttu-id="3c57f-324">Esta coluna foi introduzida no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="3c57f-324">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3c57f-325"><strong>CalleReflexiveLocalIPAddr</strong></span><span class="sxs-lookup"><span data-stu-id="3c57f-325"><strong>CalleReflexiveLocalIPAddr</strong></span></span></p></td>
<td><p><span data-ttu-id="3c57f-326">int</span><span class="sxs-lookup"><span data-stu-id="3c57f-326">int</span></span></p></td>
<td><p><span data-ttu-id="3c57f-327">Estrangeira</span><span class="sxs-lookup"><span data-stu-id="3c57f-327">Foreign</span></span></p></td>
<td><p><span data-ttu-id="3c57f-328">Endereço IP reflexivo do usuário que recebeu a chamada.</span><span class="sxs-lookup"><span data-stu-id="3c57f-328">Reflexive IP address of the user who received the call.</span></span> <span data-ttu-id="3c57f-329">Nas organizações que usam o NAT (conversão de endereço de rede), o endereço IP reflexivo é o endereço IP do servidor proxy.</span><span class="sxs-lookup"><span data-stu-id="3c57f-329">In organizations that use NAT (network address translation), the reflexive IP address is the IP address of the proxy server.</span></span></p>
<p><span data-ttu-id="3c57f-330">Esta coluna foi introduzida no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="3c57f-330">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3c57f-331"><strong>CalleeWiFiDriverDevicesDesc</strong></span><span class="sxs-lookup"><span data-stu-id="3c57f-331"><strong>CalleeWiFiDriverDevicesDesc</strong></span></span></p></td>
<td><p><span data-ttu-id="3c57f-332">int</span><span class="sxs-lookup"><span data-stu-id="3c57f-332">int</span></span></p></td>
<td><p><span data-ttu-id="3c57f-333">Estrangeira</span><span class="sxs-lookup"><span data-stu-id="3c57f-333">Foreign</span></span></p></td>
<td><p><span data-ttu-id="3c57f-334">Descrição do dispositivo para o driver WiFi empregado pelo usuário que recebeu a chamada.</span><span class="sxs-lookup"><span data-stu-id="3c57f-334">Device description for the WiFi driver employed by the user who received the call.</span></span></p>
<p><span data-ttu-id="3c57f-335">Esta coluna foi introduzida no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="3c57f-335">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3c57f-336"><strong>CalleeWiFiDriverVersion</strong></span><span class="sxs-lookup"><span data-stu-id="3c57f-336"><strong>CalleeWiFiDriverVersion</strong></span></span></p></td>
<td><p><span data-ttu-id="3c57f-337">int</span><span class="sxs-lookup"><span data-stu-id="3c57f-337">int</span></span></p></td>
<td><p><span data-ttu-id="3c57f-338">Estrangeira</span><span class="sxs-lookup"><span data-stu-id="3c57f-338">Foreign</span></span></p></td>
<td><p><span data-ttu-id="3c57f-339">Número de versão para o driver WiFi empregado pelo usuário que recebeu a chamada.</span><span class="sxs-lookup"><span data-stu-id="3c57f-339">Version number for the WiFi driver employed by the user who received the call.</span></span></p>
<p><span data-ttu-id="3c57f-340">Esta coluna foi introduzida no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="3c57f-340">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

