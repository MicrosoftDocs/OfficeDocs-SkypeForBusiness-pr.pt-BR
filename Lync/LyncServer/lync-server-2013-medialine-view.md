---
title: 'Lync Server 2013: modo de exibição de mídia'
description: 'Lync Server 2013: modo de exibição de mídia.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: MediaLine view
ms:assetid: 132eca13-8913-4218-9eff-4960ced8c3dc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ687972(v=OCS.15)
ms:contentKeyID: 49733560
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4c61fcc15b46958622e6cddd66427255a6def154
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48568677"
---
# <a name="medialine-view-in-lync-server-2013"></a><span data-ttu-id="bca86-103">Modo de exibição de mídia no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="bca86-103">MediaLine view in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="bca86-104">_**Última modificação do tópico:** 2012-10-03_</span><span class="sxs-lookup"><span data-stu-id="bca86-104">_**Topic Last Modified:** 2012-10-03_</span></span>

<span data-ttu-id="bca86-105">O MediaLine View armazena informações sobre cada linha de mídia no banco de dados.</span><span class="sxs-lookup"><span data-stu-id="bca86-105">The MediaLine View stores information about each media line in the database.</span></span> <span data-ttu-id="bca86-106">Uma sessão de áudio normalmente contém uma linha de mídia de áudio.</span><span class="sxs-lookup"><span data-stu-id="bca86-106">One audio session typically contains one audio media line.</span></span> <span data-ttu-id="bca86-107">Uma sessão de áudio e vídeo (A/V) normalmente contém uma linha de mídia de áudio e uma linha de mídia de vídeo; no entanto, a sessão pode conter duas linhas de mídia de vídeo se um dispositivo de conferência ou o modo de exibição de galeria for usado.</span><span class="sxs-lookup"><span data-stu-id="bca86-107">One audio and video (A/V) session typically contains one audio media line and one video media line; however, the session might contain two video media lines if a conferencing device is used or if Gallery View is used.</span></span> <span data-ttu-id="bca86-108">Este modo de exibição foi introduzido no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="bca86-108">This view was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="bca86-109">Coluna</span><span class="sxs-lookup"><span data-stu-id="bca86-109">Column</span></span></th>
<th><span data-ttu-id="bca86-110">Tipo de dado</span><span class="sxs-lookup"><span data-stu-id="bca86-110">Data Type</span></span></th>
<th><span data-ttu-id="bca86-111">detalhes</span><span class="sxs-lookup"><span data-stu-id="bca86-111">details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="bca86-112">ConferenceDateTime</span><span class="sxs-lookup"><span data-stu-id="bca86-112">ConferenceDateTime</span></span></p></td>
<td><p><span data-ttu-id="bca86-113">datetime</span><span class="sxs-lookup"><span data-stu-id="bca86-113">datetime</span></span></p></td>
<td><p><span data-ttu-id="bca86-114">Referenciado da <a href="lync-server-2013-medialine-table.md">tabela de mídia no Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="bca86-114">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bca86-115">SessionSeq</span><span class="sxs-lookup"><span data-stu-id="bca86-115">SessionSeq</span></span></p></td>
<td><p><span data-ttu-id="bca86-116">int</span><span class="sxs-lookup"><span data-stu-id="bca86-116">int</span></span></p></td>
<td><p><span data-ttu-id="bca86-117">Referenciado da <a href="lync-server-2013-medialine-table.md">tabela de mídia no Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="bca86-117">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bca86-118">MediaLineLabel</span><span class="sxs-lookup"><span data-stu-id="bca86-118">MediaLineLabel</span></span></p></td>
<td><p><span data-ttu-id="bca86-119">tinyint</span><span class="sxs-lookup"><span data-stu-id="bca86-119">tinyint</span></span></p></td>
<td><p><span data-ttu-id="bca86-120">Referenciado da <a href="lync-server-2013-medialine-table.md">tabela de mídia no Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="bca86-120">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bca86-121">CallerIceWarningFlags</span><span class="sxs-lookup"><span data-stu-id="bca86-121">CallerIceWarningFlags</span></span></p></td>
<td><p><span data-ttu-id="bca86-122">int</span><span class="sxs-lookup"><span data-stu-id="bca86-122">int</span></span></p></td>
<td><p><span data-ttu-id="bca86-p102">Informações sobre o processo de ICE (Estabelecimento de Conectividade Interativa) descrito em sinalizadores de bits do autor da chamada. Para obter detalhes, consulte a Especificação de protocolo do servidor de monitoramento de Qualidade da Experiência.</span><span class="sxs-lookup"><span data-stu-id="bca86-p102">Information about Interactive Connectivity Establishment (ICE) process described in bits flags for the caller. For details, refer to the Quality of Experience Monitoring Server Protocol Specification.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bca86-125">CalleeIceWarningFlags</span><span class="sxs-lookup"><span data-stu-id="bca86-125">CalleeIceWarningFlags</span></span></p></td>
<td><p><span data-ttu-id="bca86-126">int</span><span class="sxs-lookup"><span data-stu-id="bca86-126">int</span></span></p></td>
<td><p><span data-ttu-id="bca86-p103">Informações sobre o processo do ICE (Estabelecimento de Conectividade Interativa) descrito em sinalizadores de bits para o chamador. Para detalhes, consulte a Especificação do Protocolo de Servidor do Monitoramento da Qualidade da Experiência.</span><span class="sxs-lookup"><span data-stu-id="bca86-p103">Information about Interactive Connectivity Establishment (ICE) process described in bits flags for the callee. For details, refer to the Quality of Experience Monitoring Server Protocol Specification.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bca86-129">Segurança</span><span class="sxs-lookup"><span data-stu-id="bca86-129">Security</span></span></p></td>
<td><p><span data-ttu-id="bca86-130">tinyint</span><span class="sxs-lookup"><span data-stu-id="bca86-130">tinyint</span></span></p></td>
<td><p><span data-ttu-id="bca86-p104">Perfil de segurança em uso. 0 é NONE (nenhum), 1 é SRTP, 2 é V1.</span><span class="sxs-lookup"><span data-stu-id="bca86-p104">Security profile in use. 0 is NONE, 1 is SRTP, 2 is V1.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bca86-133">Transport</span><span class="sxs-lookup"><span data-stu-id="bca86-133">Transport</span></span></p></td>
<td><p><span data-ttu-id="bca86-134">tinyint</span><span class="sxs-lookup"><span data-stu-id="bca86-134">tinyint</span></span></p></td>
<td><p><span data-ttu-id="bca86-p105">Tipo de transporte. 0 é UDP, 1 é TCP.</span><span class="sxs-lookup"><span data-stu-id="bca86-p105">Transport type. 0 is UDP, 1 is TCP.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bca86-137">CallerIPAddr</span><span class="sxs-lookup"><span data-stu-id="bca86-137">CallerIPAddr</span></span></p></td>
<td><p><span data-ttu-id="bca86-138">var (50)</span><span class="sxs-lookup"><span data-stu-id="bca86-138">var(50)</span></span></p></td>
<td><p><span data-ttu-id="bca86-p106">Endereço IP do chamador. Pode ser um endereço IPv4 ou IPv6.</span><span class="sxs-lookup"><span data-stu-id="bca86-p106">IP address of the caller. This can be either an IPv4 or IPv6 address.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bca86-141">CallerPort</span><span class="sxs-lookup"><span data-stu-id="bca86-141">CallerPort</span></span></p></td>
<td><p><span data-ttu-id="bca86-142">int</span><span class="sxs-lookup"><span data-stu-id="bca86-142">int</span></span></p></td>
<td><p><span data-ttu-id="bca86-143">Porta usada pelo chamador.</span><span class="sxs-lookup"><span data-stu-id="bca86-143">Port used by the caller.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bca86-144">CallerInside</span><span class="sxs-lookup"><span data-stu-id="bca86-144">CallerInside</span></span></p></td>
<td><p><span data-ttu-id="bca86-145">bits</span><span class="sxs-lookup"><span data-stu-id="bca86-145">bit</span></span></p></td>
<td><p><span data-ttu-id="bca86-p107">Indica se o chamador está ou não dentro da rede da organização. 1 significa que o chamador está dentro da rede corporativa, 0 significa que está fora.</span><span class="sxs-lookup"><span data-stu-id="bca86-p107">Indicates whether or not the caller is inside the organization network. 1 means that the caller is inside the enterprise network. 0 means that the caller is outside the network.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bca86-149">CallerMacAddress</span><span class="sxs-lookup"><span data-stu-id="bca86-149">CallerMacAddress</span></span></p></td>
<td><p><span data-ttu-id="bca86-150">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="bca86-150">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="bca86-151">Endereço MAC da interface de rede usada pelo chamador.</span><span class="sxs-lookup"><span data-stu-id="bca86-151">MAC address of network interface used by caller.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bca86-152">CallerRelayIPAddr</span><span class="sxs-lookup"><span data-stu-id="bca86-152">CallerRelayIPAddr</span></span></p></td>
<td><p><span data-ttu-id="bca86-153">var (50)</span><span class="sxs-lookup"><span data-stu-id="bca86-153">var(50)</span></span></p></td>
<td><p><span data-ttu-id="bca86-154">Endereço IP do serviço de borda A/V usado pelo chamador.</span><span class="sxs-lookup"><span data-stu-id="bca86-154">IP Address of the A/V Edge service used by the caller.</span></span> <span data-ttu-id="bca86-155">Consulte a <a href="lync-server-2013-ipaddress-table.md">tabela IPAddress no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="bca86-155">See the <a href="lync-server-2013-ipaddress-table.md">IPAddress table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bca86-156">CalleeRelayPort</span><span class="sxs-lookup"><span data-stu-id="bca86-156">CalleeRelayPort</span></span></p></td>
<td><p><span data-ttu-id="bca86-157">int</span><span class="sxs-lookup"><span data-stu-id="bca86-157">int</span></span></p></td>
<td><p><span data-ttu-id="bca86-158">Porta usada no serviço de Borda de A/V usado pelo chamador.</span><span class="sxs-lookup"><span data-stu-id="bca86-158">Port used on the A/V Edge service used by the caller.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bca86-159">CallerReflexiveIPAddr</span><span class="sxs-lookup"><span data-stu-id="bca86-159">CallerReflexiveIPAddr</span></span></p></td>
<td><p><span data-ttu-id="bca86-160">var (50)</span><span class="sxs-lookup"><span data-stu-id="bca86-160">var(50)</span></span></p></td>
<td><p><span data-ttu-id="bca86-161">Endereço IP do chamador conforme reportado pelo serviço de Borda de A/V.</span><span class="sxs-lookup"><span data-stu-id="bca86-161">Caller’s IP address as reported by the A/V Edge service.</span></span> <span data-ttu-id="bca86-162">Este endereço pode ser diferente do endereço na coluna CallerIPAddr se o cliente estiver localizado atrás de uma NAT, por exemplo.</span><span class="sxs-lookup"><span data-stu-id="bca86-162">This address may be different that the CallerIPAddr if the client is located behind a NAT for example.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bca86-163">CallerCaptureDev</span><span class="sxs-lookup"><span data-stu-id="bca86-163">CallerCaptureDev</span></span></p></td>
<td><p><span data-ttu-id="bca86-164">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="bca86-164">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="bca86-165">Nome do dispositivo de captura do chamador.</span><span class="sxs-lookup"><span data-stu-id="bca86-165">Caller’s capture device name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bca86-166">CallerRenderDev</span><span class="sxs-lookup"><span data-stu-id="bca86-166">CallerRenderDev</span></span></p></td>
<td><p><span data-ttu-id="bca86-167">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="bca86-167">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="bca86-168">Nome do dispositivo de renderização do chamador.</span><span class="sxs-lookup"><span data-stu-id="bca86-168">Caller’s render device name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bca86-169">CallerCaptureDevDriver</span><span class="sxs-lookup"><span data-stu-id="bca86-169">CallerCaptureDevDriver</span></span></p></td>
<td><p><span data-ttu-id="bca86-170">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="bca86-170">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="bca86-171">Nome do driver do dispositivo de captura do chamador.</span><span class="sxs-lookup"><span data-stu-id="bca86-171">Caller’s capture device driver name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bca86-172">CallerRenderDevDriver</span><span class="sxs-lookup"><span data-stu-id="bca86-172">CallerRenderDevDriver</span></span></p></td>
<td><p><span data-ttu-id="bca86-173">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="bca86-173">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="bca86-174">Nome da unidade do dispositivo de renderização do chamador.</span><span class="sxs-lookup"><span data-stu-id="bca86-174">Caller’s render device driver name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bca86-175">CallerWifiDriverDeviceDesc</span><span class="sxs-lookup"><span data-stu-id="bca86-175">CallerWifiDriverDeviceDesc</span></span></p></td>
<td><p><span data-ttu-id="bca86-176">varchar (256</span><span class="sxs-lookup"><span data-stu-id="bca86-176">varchar(256</span></span></p></td>
<td><p><span data-ttu-id="bca86-177">Descrição da unidade wifi do chamador.</span><span class="sxs-lookup"><span data-stu-id="bca86-177">Caller’s Wifi driver description.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bca86-178">CallerWifiDriverVersion</span><span class="sxs-lookup"><span data-stu-id="bca86-178">CallerWifiDriverVersion</span></span></p></td>
<td><p><span data-ttu-id="bca86-179">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="bca86-179">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="bca86-180">Versão da unidade wifi do chamador.</span><span class="sxs-lookup"><span data-stu-id="bca86-180">Caller’s Wifi driver version.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bca86-181">CalleeNetworkConnectionDetail</span><span class="sxs-lookup"><span data-stu-id="bca86-181">CalleeNetworkConnectionDetail</span></span></p></td>
<td><p><span data-ttu-id="bca86-182">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="bca86-182">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="bca86-183">Detalhes da conexão de rede do chamador.</span><span class="sxs-lookup"><span data-stu-id="bca86-183">Details of caller’s network connection.</span></span> <span data-ttu-id="bca86-184">Consulte a <a href="lync-server-2013-networkconnectiondetail-table.md">tabela NetworkConnectionDetail no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="bca86-184">See the <a href="lync-server-2013-networkconnectiondetail-table.md">NetworkConnectionDetail table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bca86-185">CallerBssid</span><span class="sxs-lookup"><span data-stu-id="bca86-185">CallerBssid</span></span></p></td>
<td><p><span data-ttu-id="bca86-186">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="bca86-186">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="bca86-187">Identificador SSID usado pela conexão WiFi do chamador.</span><span class="sxs-lookup"><span data-stu-id="bca86-187">Basic Service Set Identifier used by callers WiFi connection.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bca86-188">CallerVPN</span><span class="sxs-lookup"><span data-stu-id="bca86-188">CallerVPN</span></span></p></td>
<td><p><span data-ttu-id="bca86-189">bits</span><span class="sxs-lookup"><span data-stu-id="bca86-189">bit</span></span></p></td>
<td><p><span data-ttu-id="bca86-p111">Indica se o chamador se conectou por uma rede virtual privada. 1 é rede virtual privada (VPN), 0 é não-VPN.</span><span class="sxs-lookup"><span data-stu-id="bca86-p111">Indicates whether the caller connected over a virtual private network. 1 is virtual private network (VPN), 0 is non-VPN.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bca86-192">CalleeIPAddr</span><span class="sxs-lookup"><span data-stu-id="bca86-192">CalleeIPAddr</span></span></p></td>
<td><p><span data-ttu-id="bca86-193">var (50)</span><span class="sxs-lookup"><span data-stu-id="bca86-193">var(50)</span></span></p></td>
<td><p><span data-ttu-id="bca86-194">Endereço IP do receptor da chamada.</span><span class="sxs-lookup"><span data-stu-id="bca86-194">IP address of the callee.</span></span> <span data-ttu-id="bca86-195">Pode ser um endereço IPv4 ou IPv6.</span><span class="sxs-lookup"><span data-stu-id="bca86-195">This can be either an IPv4 or IPv6 address.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bca86-196">CalleePort</span><span class="sxs-lookup"><span data-stu-id="bca86-196">CalleePort</span></span></p></td>
<td><p><span data-ttu-id="bca86-197">int</span><span class="sxs-lookup"><span data-stu-id="bca86-197">int</span></span></p></td>
<td><p><span data-ttu-id="bca86-198">Porta usada pelo receptor.</span><span class="sxs-lookup"><span data-stu-id="bca86-198">Port used by the callee.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bca86-199">CalleeInside</span><span class="sxs-lookup"><span data-stu-id="bca86-199">CalleeInside</span></span></p></td>
<td><p><span data-ttu-id="bca86-200">bits</span><span class="sxs-lookup"><span data-stu-id="bca86-200">bit</span></span></p></td>
<td><p><span data-ttu-id="bca86-p113">Indica se o receptor da chamada está dentro da rede corporativa. 1 significa que o receptor está dentro da rede corporativa, 0 significa que está fora.</span><span class="sxs-lookup"><span data-stu-id="bca86-p113">Indicates whether the callee is inside the enterprise network. 1 means callee is inside the enterprise network, 0 means the callee is outside the network.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bca86-203">CalleeMacAddress</span><span class="sxs-lookup"><span data-stu-id="bca86-203">CalleeMacAddress</span></span></p></td>
<td><p><span data-ttu-id="bca86-204">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="bca86-204">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="bca86-205">Endereço MAC da interface de rede usada pelo receptor da chamada.</span><span class="sxs-lookup"><span data-stu-id="bca86-205">MAC address of network interface used by callee.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bca86-206">CalleeRelayIPAddr</span><span class="sxs-lookup"><span data-stu-id="bca86-206">CalleeRelayIPAddr</span></span></p></td>
<td><p><span data-ttu-id="bca86-207">var (50)</span><span class="sxs-lookup"><span data-stu-id="bca86-207">var(50)</span></span></p></td>
<td><p><span data-ttu-id="bca86-208">Endereço IP do serviço de Borda de A/V usado pelo receptor da chamada.</span><span class="sxs-lookup"><span data-stu-id="bca86-208">IP Address of the A/V Edge service used by the callee.</span></span> <span data-ttu-id="bca86-209">Consulte a <a href="lync-server-2013-ipaddress-table.md">tabela IPAddress no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="bca86-209">See the <a href="lync-server-2013-ipaddress-table.md">IPAddress table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bca86-210">CalleeRelayPort</span><span class="sxs-lookup"><span data-stu-id="bca86-210">CalleeRelayPort</span></span></p></td>
<td><p><span data-ttu-id="bca86-211">int</span><span class="sxs-lookup"><span data-stu-id="bca86-211">int</span></span></p></td>
<td><p><span data-ttu-id="bca86-212">Porta usada no serviço de Borda de A/V usado pelo receptor da chamada.</span><span class="sxs-lookup"><span data-stu-id="bca86-212">Port used on the A/V Edge service used by the callee.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bca86-213">CalleeReflexiveIPAddr</span><span class="sxs-lookup"><span data-stu-id="bca86-213">CalleeReflexiveIPAddr</span></span></p></td>
<td><p><span data-ttu-id="bca86-214">var (50)</span><span class="sxs-lookup"><span data-stu-id="bca86-214">var(50)</span></span></p></td>
<td><p><span data-ttu-id="bca86-215">Endereço IP do receptor da chamada conforme reportado pelo serviço de Borda de A/V.</span><span class="sxs-lookup"><span data-stu-id="bca86-215">Callee’s IP address as reported by the A/V Edge service.</span></span> <span data-ttu-id="bca86-216">Este endereço pode ser diferente do endereço na coluna CalleeIPAddr se o cliente estiver localizado atrás de uma NAT, por exemplo.</span><span class="sxs-lookup"><span data-stu-id="bca86-216">This address may be different that the CalleeIPAddr if the client is located behind a NAT for example.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bca86-217">CalleeCaptureDev</span><span class="sxs-lookup"><span data-stu-id="bca86-217">CalleeCaptureDev</span></span></p></td>
<td><p><span data-ttu-id="bca86-218">var (50)</span><span class="sxs-lookup"><span data-stu-id="bca86-218">var(50)</span></span></p></td>
<td><p><span data-ttu-id="bca86-219">Nome do dispositivo de captura do receptor da chamada.</span><span class="sxs-lookup"><span data-stu-id="bca86-219">Callee’s capture device name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bca86-220">CalleeRenderDev</span><span class="sxs-lookup"><span data-stu-id="bca86-220">CalleeRenderDev</span></span></p></td>
<td><p><span data-ttu-id="bca86-221">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="bca86-221">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="bca86-222">Nome do dispositivo de renderização do receptor.</span><span class="sxs-lookup"><span data-stu-id="bca86-222">Callee’s render device name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bca86-223">CalleeCaptureDevDriver</span><span class="sxs-lookup"><span data-stu-id="bca86-223">CalleeCaptureDevDriver</span></span></p></td>
<td><p><span data-ttu-id="bca86-224">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="bca86-224">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="bca86-225">Nome do driver do dispositivo de captura do receptor.</span><span class="sxs-lookup"><span data-stu-id="bca86-225">Callee’s capture device driver name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bca86-226">CalleeRenderDevDriver</span><span class="sxs-lookup"><span data-stu-id="bca86-226">CalleeRenderDevDriver</span></span></p></td>
<td><p><span data-ttu-id="bca86-227">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="bca86-227">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="bca86-228">Nome da unidade do dispositivo de renderização do receptor da chamada.</span><span class="sxs-lookup"><span data-stu-id="bca86-228">Callee’s render device driver name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bca86-229">CalleeWifiDriverDeviceDesc</span><span class="sxs-lookup"><span data-stu-id="bca86-229">CalleeWifiDriverDeviceDesc</span></span></p></td>
<td><p><span data-ttu-id="bca86-230">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="bca86-230">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="bca86-231">Descrição da unidade wifi do receptor da chamada.</span><span class="sxs-lookup"><span data-stu-id="bca86-231">Callee’s Wifi driver description.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bca86-232">CalleeWifiDriverVersion</span><span class="sxs-lookup"><span data-stu-id="bca86-232">CalleeWifiDriverVersion</span></span></p></td>
<td><p><span data-ttu-id="bca86-233">varchar (256</span><span class="sxs-lookup"><span data-stu-id="bca86-233">varchar(256</span></span></p></td>
<td><p><span data-ttu-id="bca86-234">Versão da unidade wifi do receptor da chamada.</span><span class="sxs-lookup"><span data-stu-id="bca86-234">Callee’s Wifi driver version.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bca86-235">CalleeNetworkConnectionDetail</span><span class="sxs-lookup"><span data-stu-id="bca86-235">CalleeNetworkConnectionDetail</span></span></p></td>
<td><p><span data-ttu-id="bca86-236">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="bca86-236">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="bca86-237">Detalhes da conexão de rede do receptor da chamada.</span><span class="sxs-lookup"><span data-stu-id="bca86-237">Details of callee’s network connection.</span></span> <span data-ttu-id="bca86-238">Consulte a <a href="lync-server-2013-networkconnectiondetail-table.md">tabela NetworkConnectionDetail no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="bca86-238">See the <a href="lync-server-2013-networkconnectiondetail-table.md">NetworkConnectionDetail table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bca86-239">CalleeBssid</span><span class="sxs-lookup"><span data-stu-id="bca86-239">CalleeBssid</span></span></p></td>
<td><p><span data-ttu-id="bca86-240">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="bca86-240">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="bca86-241">Identificador SSID usado pela conexão WiFi do receptor da chamada.</span><span class="sxs-lookup"><span data-stu-id="bca86-241">Basic Service Set Identifier used by callee’s WiFi connection.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bca86-242">CalleeVPN</span><span class="sxs-lookup"><span data-stu-id="bca86-242">CalleeVPN</span></span></p></td>
<td><p><span data-ttu-id="bca86-243">bits</span><span class="sxs-lookup"><span data-stu-id="bca86-243">bit</span></span></p></td>
<td><p><span data-ttu-id="bca86-p117">Indica se o receptor da chamada se conectou por uma rede virtual privada. 1 é rede virtual privada (VPN), 0 é não-VPN.</span><span class="sxs-lookup"><span data-stu-id="bca86-p117">Indicates whether the callee connected over a virtual private network. 1 is virtual private network (VPN), 0 is non-VPN.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bca86-246">ConversationalMOS</span><span class="sxs-lookup"><span data-stu-id="bca86-246">ConversationalMOS</span></span></p></td>
<td><p><span data-ttu-id="bca86-247">decimal (3, 2)</span><span class="sxs-lookup"><span data-stu-id="bca86-247">decimal(3,2)</span></span></p></td>
<td><p><span data-ttu-id="bca86-248">MOS da Conversa de Banda Estreita das sessões de áudio (com base nos dois fluxos de áudio).</span><span class="sxs-lookup"><span data-stu-id="bca86-248">Narrowband Conversational MOS of the audio sessions (based on both audio streams).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bca86-249">AppliedBandwidthLimit</span><span class="sxs-lookup"><span data-stu-id="bca86-249">AppliedBandwidthLimit</span></span></p></td>
<td><p><span data-ttu-id="bca86-250">int</span><span class="sxs-lookup"><span data-stu-id="bca86-250">int</span></span></p></td>
<td><p><span data-ttu-id="bca86-p118">Esta é a largura de banda real aplicada a um dado fluxo de envio, considerando várias configurações de política (TURN, API, SDP, Servidor de Políticas, etc.). Não deve ser confundida com a largura de banda real porque pode haver uma largura de banda real menor com base na estimativa da largura de banda. Esta é basicamente a largura de banda máxima que o fluxo de envio pode usar, salvo limites impostos pela estimativa da largura de banda.</span><span class="sxs-lookup"><span data-stu-id="bca86-p118">This is the actual bandwidth applied to the given send side stream given various policy settings (TURN, API, SDP, Policy Server, etc.). This should not to be confused with the effective bandwidth because there can be a lower effective bandwidth based on the bandwidth estimate. This is basically the maximum bandwidth the send stream can take barring limits imposed by the bandwidth estimate.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bca86-254">AppliedBandwidthSource</span><span class="sxs-lookup"><span data-stu-id="bca86-254">AppliedBandwidthSource</span></span></p></td>
<td><p><span data-ttu-id="bca86-255">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="bca86-255">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="bca86-p119">Origem da capacidade da largura de banda imposta. Descreve de onde o limite da largura de banda está vindo (por exemplo, “Servidor de Políticas”, “Servidor TURN” ou “Modalidade”).</span><span class="sxs-lookup"><span data-stu-id="bca86-p119">Source of the bandwidth cap being imposed. It describes where the bandwidth limit is coming from (for example, “Policy Server”, “TURN Server”, or “Modality”).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bca86-258">Chamador</span><span class="sxs-lookup"><span data-stu-id="bca86-258">Caller</span></span></p></td>
<td><p><span data-ttu-id="bca86-259">bits</span><span class="sxs-lookup"><span data-stu-id="bca86-259">bit</span></span></p></td>
<td><p><span data-ttu-id="bca86-260">Indica se as métricas do chamador foram recebidas; 1 é sim, 0 é não.</span><span class="sxs-lookup"><span data-stu-id="bca86-260">Indicates whether metrics from the caller were received; 1 is yes, 0 is no.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bca86-261">Receptor</span><span class="sxs-lookup"><span data-stu-id="bca86-261">Callee</span></span></p></td>
<td><p><span data-ttu-id="bca86-262">bits</span><span class="sxs-lookup"><span data-stu-id="bca86-262">bit</span></span></p></td>
<td><p><span data-ttu-id="bca86-263">Indica se as métricas do receptor da chamada foram recebidas; 1 é sim, 0 é não.</span><span class="sxs-lookup"><span data-stu-id="bca86-263">Indicates whether metrics from the call receiver were received; 1 is yes, 0 is no.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bca86-264">MidCallReport</span><span class="sxs-lookup"><span data-stu-id="bca86-264">MidCallReport</span></span></p></td>
<td><p><span data-ttu-id="bca86-265">bits</span><span class="sxs-lookup"><span data-stu-id="bca86-265">bit</span></span></p></td>
<td><p><span data-ttu-id="bca86-266">Indica se o relatório refere-se a uma parte da chamada ou à chamada completa.</span><span class="sxs-lookup"><span data-stu-id="bca86-266">Indicates whether the report is for a portion of the call or for the complete call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bca86-267">ClassifiedPoorCall</span><span class="sxs-lookup"><span data-stu-id="bca86-267">ClassifiedPoorCall</span></span></p></td>
<td><p><span data-ttu-id="bca86-268">bits</span><span class="sxs-lookup"><span data-stu-id="bca86-268">bit</span></span></p></td>
<td><p><span data-ttu-id="bca86-269">Indica se uma chamada foi classificada como ruim (1) ou boa (0).</span><span class="sxs-lookup"><span data-stu-id="bca86-269">Indicates whether a call was classified as a poor call (1) or as a good call (0).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bca86-270">CallerConnectivityICE</span><span class="sxs-lookup"><span data-stu-id="bca86-270">CallerConnectivityICE</span></span></p></td>
<td><p><span data-ttu-id="bca86-271">tinyint</span><span class="sxs-lookup"><span data-stu-id="bca86-271">tinyint</span></span></p></td>
<td><p><span data-ttu-id="bca86-272">Indica se o chamador se conectou à rede usando o protocolo ICE (Internet Connectivity Establishment).</span><span class="sxs-lookup"><span data-stu-id="bca86-272">Indicates whether the caller connected to the network using the ICE protocol (Internet Connectivity Establishment).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bca86-273">CalleeConnectivityICE</span><span class="sxs-lookup"><span data-stu-id="bca86-273">CalleeConnectivityICE</span></span></p></td>
<td><p><span data-ttu-id="bca86-274">tinyint</span><span class="sxs-lookup"><span data-stu-id="bca86-274">tinyint</span></span></p></td>
<td><p><span data-ttu-id="bca86-275">Indica se o usuário receptor da chamada se conectou à rede usando o protocolo ICE (Internet Connectivity Establishment).</span><span class="sxs-lookup"><span data-stu-id="bca86-275">Indicates whether the user called connected to the network using the ICE protocol (Internet Connectivity Establishment).</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

