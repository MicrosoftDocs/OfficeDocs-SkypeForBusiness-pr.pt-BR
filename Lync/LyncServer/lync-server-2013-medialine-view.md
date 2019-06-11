---
title: 'Lync Server 2013: modo de exibição de mídia'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: MediaLine view
ms:assetid: 132eca13-8913-4218-9eff-4960ced8c3dc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ687972(v=OCS.15)
ms:contentKeyID: 49733560
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d930f3beeeddb5c5582f41c44f1c68ff7f21f18d
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34827393"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="medialine-view-in-lync-server-2013"></a><span data-ttu-id="abf4b-102">Modo de exibição de mídia no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="abf4b-102">MediaLine view in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="abf4b-103">_**Tópico da última modificação:** 2012-10-03_</span><span class="sxs-lookup"><span data-stu-id="abf4b-103">_**Topic Last Modified:** 2012-10-03_</span></span>

<span data-ttu-id="abf4b-104">O modo de exibição de mídia armazena informações sobre cada linha de mídia no banco de dados.</span><span class="sxs-lookup"><span data-stu-id="abf4b-104">The MediaLine View stores information about each media line in the database.</span></span> <span data-ttu-id="abf4b-105">Uma sessão de áudio geralmente contém uma linha de mídia de áudio.</span><span class="sxs-lookup"><span data-stu-id="abf4b-105">One audio session typically contains one audio media line.</span></span> <span data-ttu-id="abf4b-106">Uma sessão de áudio e vídeo (A/V) geralmente contém uma linha de mídia de áudio e uma linha de mídia de vídeo; no entanto, a sessão pode conter duas linhas de mídia de vídeo se um dispositivo de conferência for usado ou se o modo de exibição de galeria for usado.</span><span class="sxs-lookup"><span data-stu-id="abf4b-106">One audio and video (A/V) session typically contains one audio media line and one video media line; however, the session might contain two video media lines if a conferencing device is used or if Gallery View is used.</span></span> <span data-ttu-id="abf4b-107">Este modo de exibição foi apresentado no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="abf4b-107">This view was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="abf4b-108">Coluna</span><span class="sxs-lookup"><span data-stu-id="abf4b-108">Column</span></span></th>
<th><span data-ttu-id="abf4b-109">Tipo de dados</span><span class="sxs-lookup"><span data-stu-id="abf4b-109">Data Type</span></span></th>
<th><span data-ttu-id="abf4b-110">os</span><span class="sxs-lookup"><span data-stu-id="abf4b-110">details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="abf4b-111">ConferenceDateTime</span><span class="sxs-lookup"><span data-stu-id="abf4b-111">ConferenceDateTime</span></span></p></td>
<td><p><span data-ttu-id="abf4b-112">datetime</span><span class="sxs-lookup"><span data-stu-id="abf4b-112">datetime</span></span></p></td>
<td><p><span data-ttu-id="abf4b-113">Referenciado da <a href="lync-server-2013-medialine-table.md">tabela de mídias no Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="abf4b-113">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="abf4b-114">SessionSeq</span><span class="sxs-lookup"><span data-stu-id="abf4b-114">SessionSeq</span></span></p></td>
<td><p><span data-ttu-id="abf4b-115">int</span><span class="sxs-lookup"><span data-stu-id="abf4b-115">int</span></span></p></td>
<td><p><span data-ttu-id="abf4b-116">Referenciado da <a href="lync-server-2013-medialine-table.md">tabela de mídias no Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="abf4b-116">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="abf4b-117">MediaLineLabel</span><span class="sxs-lookup"><span data-stu-id="abf4b-117">MediaLineLabel</span></span></p></td>
<td><p><span data-ttu-id="abf4b-118">tinyint</span><span class="sxs-lookup"><span data-stu-id="abf4b-118">tinyint</span></span></p></td>
<td><p><span data-ttu-id="abf4b-119">Referenciado da <a href="lync-server-2013-medialine-table.md">tabela de mídias no Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="abf4b-119">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="abf4b-120">CallerIceWarningFlags</span><span class="sxs-lookup"><span data-stu-id="abf4b-120">CallerIceWarningFlags</span></span></p></td>
<td><p><span data-ttu-id="abf4b-121">int</span><span class="sxs-lookup"><span data-stu-id="abf4b-121">int</span></span></p></td>
<td><p><span data-ttu-id="abf4b-122">Informações sobre o processo de estabelecimento de conectividade interativa (ICE) descrito em sinalizadores de bits para o chamador.</span><span class="sxs-lookup"><span data-stu-id="abf4b-122">Information about Interactive Connectivity Establishment (ICE) process described in bits flags for the caller.</span></span> <span data-ttu-id="abf4b-123">Para obter detalhes, consulte a especificação de protocolo de servidor de monitoração de experiência de qualidade.</span><span class="sxs-lookup"><span data-stu-id="abf4b-123">For details, refer to the Quality of Experience Monitoring Server Protocol Specification.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="abf4b-124">CalleeIceWarningFlags</span><span class="sxs-lookup"><span data-stu-id="abf4b-124">CalleeIceWarningFlags</span></span></p></td>
<td><p><span data-ttu-id="abf4b-125">int</span><span class="sxs-lookup"><span data-stu-id="abf4b-125">int</span></span></p></td>
<td><p><span data-ttu-id="abf4b-126">Informações sobre o processo de estabelecimento de conectividade interativa (ICE) descrito em sinalizadores de bits para o chamador.</span><span class="sxs-lookup"><span data-stu-id="abf4b-126">Information about Interactive Connectivity Establishment (ICE) process described in bits flags for the callee.</span></span> <span data-ttu-id="abf4b-127">Para obter detalhes, consulte a especificação de protocolo de servidor de monitoração de experiência de qualidade.</span><span class="sxs-lookup"><span data-stu-id="abf4b-127">For details, refer to the Quality of Experience Monitoring Server Protocol Specification.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="abf4b-128">Segurança</span><span class="sxs-lookup"><span data-stu-id="abf4b-128">Security</span></span></p></td>
<td><p><span data-ttu-id="abf4b-129">tinyint</span><span class="sxs-lookup"><span data-stu-id="abf4b-129">tinyint</span></span></p></td>
<td><p><span data-ttu-id="abf4b-130">Perfil de segurança em uso.</span><span class="sxs-lookup"><span data-stu-id="abf4b-130">Security profile in use.</span></span> <span data-ttu-id="abf4b-131">0 é nenhum, 1 é SRTP; 2 é v1.</span><span class="sxs-lookup"><span data-stu-id="abf4b-131">0 is NONE, 1 is SRTP, 2 is V1.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="abf4b-132">SMTP</span><span class="sxs-lookup"><span data-stu-id="abf4b-132">Transport</span></span></p></td>
<td><p><span data-ttu-id="abf4b-133">tinyint</span><span class="sxs-lookup"><span data-stu-id="abf4b-133">tinyint</span></span></p></td>
<td><p><span data-ttu-id="abf4b-134">Tipo de transporte.</span><span class="sxs-lookup"><span data-stu-id="abf4b-134">Transport type.</span></span> <span data-ttu-id="abf4b-135">0 é UDP; 1 é TCP.</span><span class="sxs-lookup"><span data-stu-id="abf4b-135">0 is UDP, 1 is TCP.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="abf4b-136">CallerIPAddr</span><span class="sxs-lookup"><span data-stu-id="abf4b-136">CallerIPAddr</span></span></p></td>
<td><p><span data-ttu-id="abf4b-137">var (50)</span><span class="sxs-lookup"><span data-stu-id="abf4b-137">var(50)</span></span></p></td>
<td><p><span data-ttu-id="abf4b-138">Endereço IP do chamador.</span><span class="sxs-lookup"><span data-stu-id="abf4b-138">IP address of the caller.</span></span> <span data-ttu-id="abf4b-139">Pode ser um endereço IPv4 ou IPv6.</span><span class="sxs-lookup"><span data-stu-id="abf4b-139">This can be either an IPv4 or IPv6 address.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="abf4b-140">CallerPort</span><span class="sxs-lookup"><span data-stu-id="abf4b-140">CallerPort</span></span></p></td>
<td><p><span data-ttu-id="abf4b-141">int</span><span class="sxs-lookup"><span data-stu-id="abf4b-141">int</span></span></p></td>
<td><p><span data-ttu-id="abf4b-142">Porta usada pelo chamador.</span><span class="sxs-lookup"><span data-stu-id="abf4b-142">Port used by the caller.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="abf4b-143">CallerInside</span><span class="sxs-lookup"><span data-stu-id="abf4b-143">CallerInside</span></span></p></td>
<td><p><span data-ttu-id="abf4b-144">bit</span><span class="sxs-lookup"><span data-stu-id="abf4b-144">bit</span></span></p></td>
<td><p><span data-ttu-id="abf4b-145">Indica se o chamador está dentro da rede da organização.</span><span class="sxs-lookup"><span data-stu-id="abf4b-145">Indicates whether or not the caller is inside the organization network.</span></span> <span data-ttu-id="abf4b-146">1 significa que o chamador está dentro da rede da empresa.</span><span class="sxs-lookup"><span data-stu-id="abf4b-146">1 means that the caller is inside the enterprise network.</span></span> <span data-ttu-id="abf4b-147">0 significa que o chamador está fora da rede.</span><span class="sxs-lookup"><span data-stu-id="abf4b-147">0 means that the caller is outside the network.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="abf4b-148">CallerMacAddress</span><span class="sxs-lookup"><span data-stu-id="abf4b-148">CallerMacAddress</span></span></p></td>
<td><p><span data-ttu-id="abf4b-149">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="abf4b-149">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="abf4b-150">Endereço MAC da interface de rede usada pelo chamador.</span><span class="sxs-lookup"><span data-stu-id="abf4b-150">MAC address of network interface used by caller.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="abf4b-151">CallerRelayIPAddr</span><span class="sxs-lookup"><span data-stu-id="abf4b-151">CallerRelayIPAddr</span></span></p></td>
<td><p><span data-ttu-id="abf4b-152">var (50)</span><span class="sxs-lookup"><span data-stu-id="abf4b-152">var(50)</span></span></p></td>
<td><p><span data-ttu-id="abf4b-153">Endereço IP do serviço de borda A/V usado pelo chamador.</span><span class="sxs-lookup"><span data-stu-id="abf4b-153">IP Address of the A/V Edge service used by the caller.</span></span> <span data-ttu-id="abf4b-154">Consulte a <a href="lync-server-2013-ipaddress-table.md">tabela IPAddress no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="abf4b-154">See the <a href="lync-server-2013-ipaddress-table.md">IPAddress table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="abf4b-155">CalleeRelayPort</span><span class="sxs-lookup"><span data-stu-id="abf4b-155">CalleeRelayPort</span></span></p></td>
<td><p><span data-ttu-id="abf4b-156">int</span><span class="sxs-lookup"><span data-stu-id="abf4b-156">int</span></span></p></td>
<td><p><span data-ttu-id="abf4b-157">Porta usada no serviço de borda A/V usado pelo chamador.</span><span class="sxs-lookup"><span data-stu-id="abf4b-157">Port used on the A/V Edge service used by the caller.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="abf4b-158">CallerReflexiveIPAddr</span><span class="sxs-lookup"><span data-stu-id="abf4b-158">CallerReflexiveIPAddr</span></span></p></td>
<td><p><span data-ttu-id="abf4b-159">var (50)</span><span class="sxs-lookup"><span data-stu-id="abf4b-159">var(50)</span></span></p></td>
<td><p><span data-ttu-id="abf4b-160">Endereço IP do chamador reportado pelo serviço de borda A/V.</span><span class="sxs-lookup"><span data-stu-id="abf4b-160">Caller’s IP address as reported by the A/V Edge service.</span></span> <span data-ttu-id="abf4b-161">Esse endereço pode ser diferente de CallerIPAddr se o cliente estiver localizado atrás de um NAT por exemplo.</span><span class="sxs-lookup"><span data-stu-id="abf4b-161">This address may be different that the CallerIPAddr if the client is located behind a NAT for example.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="abf4b-162">CallerCaptureDev</span><span class="sxs-lookup"><span data-stu-id="abf4b-162">CallerCaptureDev</span></span></p></td>
<td><p><span data-ttu-id="abf4b-163">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="abf4b-163">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="abf4b-164">Nome do dispositivo de captura do chamador.</span><span class="sxs-lookup"><span data-stu-id="abf4b-164">Caller’s capture device name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="abf4b-165">CallerRenderDev</span><span class="sxs-lookup"><span data-stu-id="abf4b-165">CallerRenderDev</span></span></p></td>
<td><p><span data-ttu-id="abf4b-166">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="abf4b-166">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="abf4b-167">Nome do dispositivo de renderização do chamador.</span><span class="sxs-lookup"><span data-stu-id="abf4b-167">Caller’s render device name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="abf4b-168">CallerCaptureDevDriver</span><span class="sxs-lookup"><span data-stu-id="abf4b-168">CallerCaptureDevDriver</span></span></p></td>
<td><p><span data-ttu-id="abf4b-169">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="abf4b-169">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="abf4b-170">Nome do driver do dispositivo de captura do chamador.</span><span class="sxs-lookup"><span data-stu-id="abf4b-170">Caller’s capture device driver name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="abf4b-171">CallerRenderDevDriver</span><span class="sxs-lookup"><span data-stu-id="abf4b-171">CallerRenderDevDriver</span></span></p></td>
<td><p><span data-ttu-id="abf4b-172">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="abf4b-172">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="abf4b-173">O nome do driver de dispositivo de renderização do chamador.</span><span class="sxs-lookup"><span data-stu-id="abf4b-173">Caller’s render device driver name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="abf4b-174">CallerWifiDriverDeviceDesc</span><span class="sxs-lookup"><span data-stu-id="abf4b-174">CallerWifiDriverDeviceDesc</span></span></p></td>
<td><p><span data-ttu-id="abf4b-175">varchar (256</span><span class="sxs-lookup"><span data-stu-id="abf4b-175">varchar(256</span></span></p></td>
<td><p><span data-ttu-id="abf4b-176">Descrição do driver WiFi do chamador.</span><span class="sxs-lookup"><span data-stu-id="abf4b-176">Caller’s Wifi driver description.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="abf4b-177">CallerWifiDriverVersion</span><span class="sxs-lookup"><span data-stu-id="abf4b-177">CallerWifiDriverVersion</span></span></p></td>
<td><p><span data-ttu-id="abf4b-178">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="abf4b-178">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="abf4b-179">Versão do driver WiFi do chamador.</span><span class="sxs-lookup"><span data-stu-id="abf4b-179">Caller’s Wifi driver version.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="abf4b-180">CalleeNetworkConnectionDetail</span><span class="sxs-lookup"><span data-stu-id="abf4b-180">CalleeNetworkConnectionDetail</span></span></p></td>
<td><p><span data-ttu-id="abf4b-181">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="abf4b-181">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="abf4b-182">Detalhes da conexão de rede do chamador.</span><span class="sxs-lookup"><span data-stu-id="abf4b-182">Details of caller’s network connection.</span></span> <span data-ttu-id="abf4b-183">Consulte a <a href="lync-server-2013-networkconnectiondetail-table.md">tabela NetworkConnectionDetail no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="abf4b-183">See the <a href="lync-server-2013-networkconnectiondetail-table.md">NetworkConnectionDetail table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="abf4b-184">CallerBssid</span><span class="sxs-lookup"><span data-stu-id="abf4b-184">CallerBssid</span></span></p></td>
<td><p><span data-ttu-id="abf4b-185">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="abf4b-185">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="abf4b-186">Identificador do conjunto de serviços básico usado pela conexão WiFi de chamadores.</span><span class="sxs-lookup"><span data-stu-id="abf4b-186">Basic Service Set Identifier used by callers WiFi connection.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="abf4b-187">CallerVPN</span><span class="sxs-lookup"><span data-stu-id="abf4b-187">CallerVPN</span></span></p></td>
<td><p><span data-ttu-id="abf4b-188">bit</span><span class="sxs-lookup"><span data-stu-id="abf4b-188">bit</span></span></p></td>
<td><p><span data-ttu-id="abf4b-189">Indica se o chamador está conectado por meio de uma rede virtual privada.</span><span class="sxs-lookup"><span data-stu-id="abf4b-189">Indicates whether the caller connected over a virtual private network.</span></span> <span data-ttu-id="abf4b-190">1 é uma rede virtual privada (VPN), 0 não é VPN.</span><span class="sxs-lookup"><span data-stu-id="abf4b-190">1 is virtual private network (VPN), 0 is non-VPN.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="abf4b-191">CalleeIPAddr</span><span class="sxs-lookup"><span data-stu-id="abf4b-191">CalleeIPAddr</span></span></p></td>
<td><p><span data-ttu-id="abf4b-192">var (50)</span><span class="sxs-lookup"><span data-stu-id="abf4b-192">var(50)</span></span></p></td>
<td><p><span data-ttu-id="abf4b-193">Endereço IP do chamador.</span><span class="sxs-lookup"><span data-stu-id="abf4b-193">IP address of the callee.</span></span> <span data-ttu-id="abf4b-194">Pode ser um endereço IPv4 ou IPv6.</span><span class="sxs-lookup"><span data-stu-id="abf4b-194">This can be either an IPv4 or IPv6 address.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="abf4b-195">CalleePort</span><span class="sxs-lookup"><span data-stu-id="abf4b-195">CalleePort</span></span></p></td>
<td><p><span data-ttu-id="abf4b-196">int</span><span class="sxs-lookup"><span data-stu-id="abf4b-196">int</span></span></p></td>
<td><p><span data-ttu-id="abf4b-197">Porta usada pelo chamador.</span><span class="sxs-lookup"><span data-stu-id="abf4b-197">Port used by the callee.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="abf4b-198">CalleeInside</span><span class="sxs-lookup"><span data-stu-id="abf4b-198">CalleeInside</span></span></p></td>
<td><p><span data-ttu-id="abf4b-199">bit</span><span class="sxs-lookup"><span data-stu-id="abf4b-199">bit</span></span></p></td>
<td><p><span data-ttu-id="abf4b-200">Indica se a chamada está dentro da rede corporativa.</span><span class="sxs-lookup"><span data-stu-id="abf4b-200">Indicates whether the callee is inside the enterprise network.</span></span> <span data-ttu-id="abf4b-201">1 significa que a chamada está dentro da rede corporativa, 0 significa que o chamador está fora da rede.</span><span class="sxs-lookup"><span data-stu-id="abf4b-201">1 means callee is inside the enterprise network, 0 means the callee is outside the network.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="abf4b-202">CalleeMacAddress</span><span class="sxs-lookup"><span data-stu-id="abf4b-202">CalleeMacAddress</span></span></p></td>
<td><p><span data-ttu-id="abf4b-203">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="abf4b-203">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="abf4b-204">Endereço MAC da interface de rede usada pelo chamador.</span><span class="sxs-lookup"><span data-stu-id="abf4b-204">MAC address of network interface used by callee.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="abf4b-205">CalleeRelayIPAddr</span><span class="sxs-lookup"><span data-stu-id="abf4b-205">CalleeRelayIPAddr</span></span></p></td>
<td><p><span data-ttu-id="abf4b-206">var (50)</span><span class="sxs-lookup"><span data-stu-id="abf4b-206">var(50)</span></span></p></td>
<td><p><span data-ttu-id="abf4b-207">Endereço IP do serviço de borda A/V usado pelo chamador.</span><span class="sxs-lookup"><span data-stu-id="abf4b-207">IP Address of the A/V Edge service used by the callee.</span></span> <span data-ttu-id="abf4b-208">Consulte a <a href="lync-server-2013-ipaddress-table.md">tabela IPAddress no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="abf4b-208">See the <a href="lync-server-2013-ipaddress-table.md">IPAddress table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="abf4b-209">CalleeRelayPort</span><span class="sxs-lookup"><span data-stu-id="abf4b-209">CalleeRelayPort</span></span></p></td>
<td><p><span data-ttu-id="abf4b-210">int</span><span class="sxs-lookup"><span data-stu-id="abf4b-210">int</span></span></p></td>
<td><p><span data-ttu-id="abf4b-211">Porta usada no serviço de borda A/V usado pelo chamador.</span><span class="sxs-lookup"><span data-stu-id="abf4b-211">Port used on the A/V Edge service used by the callee.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="abf4b-212">CalleeReflexiveIPAddr</span><span class="sxs-lookup"><span data-stu-id="abf4b-212">CalleeReflexiveIPAddr</span></span></p></td>
<td><p><span data-ttu-id="abf4b-213">var (50)</span><span class="sxs-lookup"><span data-stu-id="abf4b-213">var(50)</span></span></p></td>
<td><p><span data-ttu-id="abf4b-214">Endereço IP do chamador reportado pelo serviço de borda A/V.</span><span class="sxs-lookup"><span data-stu-id="abf4b-214">Callee’s IP address as reported by the A/V Edge service.</span></span> <span data-ttu-id="abf4b-215">Esse endereço pode ser diferente de CalleeIPAddr se o cliente estiver localizado atrás de um NAT por exemplo.</span><span class="sxs-lookup"><span data-stu-id="abf4b-215">This address may be different that the CalleeIPAddr if the client is located behind a NAT for example.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="abf4b-216">CalleeCaptureDev</span><span class="sxs-lookup"><span data-stu-id="abf4b-216">CalleeCaptureDev</span></span></p></td>
<td><p><span data-ttu-id="abf4b-217">var (50)</span><span class="sxs-lookup"><span data-stu-id="abf4b-217">var(50)</span></span></p></td>
<td><p><span data-ttu-id="abf4b-218">Nome do dispositivo de captura do chamador.</span><span class="sxs-lookup"><span data-stu-id="abf4b-218">Callee’s capture device name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="abf4b-219">CalleeRenderDev</span><span class="sxs-lookup"><span data-stu-id="abf4b-219">CalleeRenderDev</span></span></p></td>
<td><p><span data-ttu-id="abf4b-220">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="abf4b-220">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="abf4b-221">Nome do dispositivo de renderização do Calle.</span><span class="sxs-lookup"><span data-stu-id="abf4b-221">Callee’s render device name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="abf4b-222">CalleeCaptureDevDriver</span><span class="sxs-lookup"><span data-stu-id="abf4b-222">CalleeCaptureDevDriver</span></span></p></td>
<td><p><span data-ttu-id="abf4b-223">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="abf4b-223">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="abf4b-224">Nome do driver do dispositivo de captura do chamador.</span><span class="sxs-lookup"><span data-stu-id="abf4b-224">Callee’s capture device driver name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="abf4b-225">CalleeRenderDevDriver</span><span class="sxs-lookup"><span data-stu-id="abf4b-225">CalleeRenderDevDriver</span></span></p></td>
<td><p><span data-ttu-id="abf4b-226">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="abf4b-226">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="abf4b-227">Chame o nome do driver do dispositivo de processamento do recurso.</span><span class="sxs-lookup"><span data-stu-id="abf4b-227">Callee’s render device driver name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="abf4b-228">CalleeWifiDriverDeviceDesc</span><span class="sxs-lookup"><span data-stu-id="abf4b-228">CalleeWifiDriverDeviceDesc</span></span></p></td>
<td><p><span data-ttu-id="abf4b-229">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="abf4b-229">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="abf4b-230">Descrição do driver WiFi do Calle.</span><span class="sxs-lookup"><span data-stu-id="abf4b-230">Callee’s Wifi driver description.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="abf4b-231">CalleeWifiDriverVersion</span><span class="sxs-lookup"><span data-stu-id="abf4b-231">CalleeWifiDriverVersion</span></span></p></td>
<td><p><span data-ttu-id="abf4b-232">varchar (256</span><span class="sxs-lookup"><span data-stu-id="abf4b-232">varchar(256</span></span></p></td>
<td><p><span data-ttu-id="abf4b-233">Versão do driver WiFi do Calle.</span><span class="sxs-lookup"><span data-stu-id="abf4b-233">Callee’s Wifi driver version.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="abf4b-234">CalleeNetworkConnectionDetail</span><span class="sxs-lookup"><span data-stu-id="abf4b-234">CalleeNetworkConnectionDetail</span></span></p></td>
<td><p><span data-ttu-id="abf4b-235">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="abf4b-235">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="abf4b-236">Detalhes da conexão de rede do Calle.</span><span class="sxs-lookup"><span data-stu-id="abf4b-236">Details of callee’s network connection.</span></span> <span data-ttu-id="abf4b-237">Consulte a <a href="lync-server-2013-networkconnectiondetail-table.md">tabela NetworkConnectionDetail no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="abf4b-237">See the <a href="lync-server-2013-networkconnectiondetail-table.md">NetworkConnectionDetail table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="abf4b-238">CalleeBssid</span><span class="sxs-lookup"><span data-stu-id="abf4b-238">CalleeBssid</span></span></p></td>
<td><p><span data-ttu-id="abf4b-239">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="abf4b-239">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="abf4b-240">Identificador do conjunto de serviços básico usado pela conexão WiFi do chamador.</span><span class="sxs-lookup"><span data-stu-id="abf4b-240">Basic Service Set Identifier used by callee’s WiFi connection.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="abf4b-241">CalleeVPN</span><span class="sxs-lookup"><span data-stu-id="abf4b-241">CalleeVPN</span></span></p></td>
<td><p><span data-ttu-id="abf4b-242">bit</span><span class="sxs-lookup"><span data-stu-id="abf4b-242">bit</span></span></p></td>
<td><p><span data-ttu-id="abf4b-243">Indica se o chamador está conectado por meio de uma rede virtual privada.</span><span class="sxs-lookup"><span data-stu-id="abf4b-243">Indicates whether the callee connected over a virtual private network.</span></span> <span data-ttu-id="abf4b-244">1 é uma rede virtual privada (VPN), 0 não é VPN.</span><span class="sxs-lookup"><span data-stu-id="abf4b-244">1 is virtual private network (VPN), 0 is non-VPN.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="abf4b-245">ConversationalMOS</span><span class="sxs-lookup"><span data-stu-id="abf4b-245">ConversationalMOS</span></span></p></td>
<td><p><span data-ttu-id="abf4b-246">decimal (3; 2)</span><span class="sxs-lookup"><span data-stu-id="abf4b-246">decimal(3,2)</span></span></p></td>
<td><p><span data-ttu-id="abf4b-247">O MOS de conversa de banda estreita das sessões de áudio (com base nos dois fluxos de áudio).</span><span class="sxs-lookup"><span data-stu-id="abf4b-247">Narrowband Conversational MOS of the audio sessions (based on both audio streams).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="abf4b-248">AppliedBandwidthLimit</span><span class="sxs-lookup"><span data-stu-id="abf4b-248">AppliedBandwidthLimit</span></span></p></td>
<td><p><span data-ttu-id="abf4b-249">int</span><span class="sxs-lookup"><span data-stu-id="abf4b-249">int</span></span></p></td>
<td><p><span data-ttu-id="abf4b-250">Esta é a largura de banda real aplicada ao fluxo de envios do lado fornecido com várias configurações de política (ativar, API, SDP, servidor de política etc.).</span><span class="sxs-lookup"><span data-stu-id="abf4b-250">This is the actual bandwidth applied to the given send side stream given various policy settings (TURN, API, SDP, Policy Server, etc.).</span></span> <span data-ttu-id="abf4b-251">Isso não deve ser confundido com a largura de banda efetiva porque pode haver uma largura de banda mais econômica com base na estimativa de largura de banda.</span><span class="sxs-lookup"><span data-stu-id="abf4b-251">This should not to be confused with the effective bandwidth because there can be a lower effective bandwidth based on the bandwidth estimate.</span></span> <span data-ttu-id="abf4b-252">Isso é basicamente a largura de banda máxima que o fluxo de envio pode ter limites de bloqueio impostos pela estimativa da largura de banda.</span><span class="sxs-lookup"><span data-stu-id="abf4b-252">This is basically the maximum bandwidth the send stream can take barring limits imposed by the bandwidth estimate.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="abf4b-253">AppliedBandwidthSource</span><span class="sxs-lookup"><span data-stu-id="abf4b-253">AppliedBandwidthSource</span></span></p></td>
<td><p><span data-ttu-id="abf4b-254">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="abf4b-254">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="abf4b-255">Fonte do limite de largura de banda imposto.</span><span class="sxs-lookup"><span data-stu-id="abf4b-255">Source of the bandwidth cap being imposed.</span></span> <span data-ttu-id="abf4b-256">Ele descreve para onde o limite de largura de banda é proveniente (por exemplo, "servidor de políticas", "Ativar servidor" ou "modalidade").</span><span class="sxs-lookup"><span data-stu-id="abf4b-256">It describes where the bandwidth limit is coming from (for example, “Policy Server”, “TURN Server”, or “Modality”).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="abf4b-257">Chamador</span><span class="sxs-lookup"><span data-stu-id="abf4b-257">Caller</span></span></p></td>
<td><p><span data-ttu-id="abf4b-258">bit</span><span class="sxs-lookup"><span data-stu-id="abf4b-258">bit</span></span></p></td>
<td><p><span data-ttu-id="abf4b-259">Indica se as métricas do autor foram recebidas; 1 é sim, 0 é não.</span><span class="sxs-lookup"><span data-stu-id="abf4b-259">Indicates whether metrics from the caller were received; 1 is yes, 0 is no.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="abf4b-260">Receptor</span><span class="sxs-lookup"><span data-stu-id="abf4b-260">Callee</span></span></p></td>
<td><p><span data-ttu-id="abf4b-261">bit</span><span class="sxs-lookup"><span data-stu-id="abf4b-261">bit</span></span></p></td>
<td><p><span data-ttu-id="abf4b-262">Indica se as métricas do receptor da chamada foram recebidas; 1 é sim, 0 é não.</span><span class="sxs-lookup"><span data-stu-id="abf4b-262">Indicates whether metrics from the call receiver were received; 1 is yes, 0 is no.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="abf4b-263">MidCallReport</span><span class="sxs-lookup"><span data-stu-id="abf4b-263">MidCallReport</span></span></p></td>
<td><p><span data-ttu-id="abf4b-264">bit</span><span class="sxs-lookup"><span data-stu-id="abf4b-264">bit</span></span></p></td>
<td><p><span data-ttu-id="abf4b-265">Indica se o relatório é para uma parte da chamada ou para a chamada completa.</span><span class="sxs-lookup"><span data-stu-id="abf4b-265">Indicates whether the report is for a portion of the call or for the complete call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="abf4b-266">ClassifiedPoorCall</span><span class="sxs-lookup"><span data-stu-id="abf4b-266">ClassifiedPoorCall</span></span></p></td>
<td><p><span data-ttu-id="abf4b-267">bit</span><span class="sxs-lookup"><span data-stu-id="abf4b-267">bit</span></span></p></td>
<td><p><span data-ttu-id="abf4b-268">Indica se uma chamada foi classificada como uma chamada deficiente (1) ou uma boa chamada (0).</span><span class="sxs-lookup"><span data-stu-id="abf4b-268">Indicates whether a call was classified as a poor call (1) or as a good call (0).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="abf4b-269">CallerConnectivityICE</span><span class="sxs-lookup"><span data-stu-id="abf4b-269">CallerConnectivityICE</span></span></p></td>
<td><p><span data-ttu-id="abf4b-270">tinyint</span><span class="sxs-lookup"><span data-stu-id="abf4b-270">tinyint</span></span></p></td>
<td><p><span data-ttu-id="abf4b-271">Indica se o chamador está conectado à rede usando o protocolo ICE (estabelecimento de conectividade com a Internet).</span><span class="sxs-lookup"><span data-stu-id="abf4b-271">Indicates whether the caller connected to the network using the ICE protocol (Internet Connectivity Establishment).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="abf4b-272">CalleeConnectivityICE</span><span class="sxs-lookup"><span data-stu-id="abf4b-272">CalleeConnectivityICE</span></span></p></td>
<td><p><span data-ttu-id="abf4b-273">tinyint</span><span class="sxs-lookup"><span data-stu-id="abf4b-273">tinyint</span></span></p></td>
<td><p><span data-ttu-id="abf4b-274">Indica se o usuário chamou conexão à rede usando o protocolo ICE (estabelecimento de conectividade com a Internet).</span><span class="sxs-lookup"><span data-stu-id="abf4b-274">Indicates whether the user called connected to the network using the ICE protocol (Internet Connectivity Establishment).</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

