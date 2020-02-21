---
title: 'Lync Server 2013: modo de exibição de mídia'
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
ms.openlocfilehash: 21fa89b5afe53937ee515dac45053dbd84ae12ef
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42217587"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="medialine-view-in-lync-server-2013"></a><span data-ttu-id="3f032-102">Modo de exibição de mídia no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3f032-102">MediaLine view in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3f032-103">_**Última modificação do tópico:** 2012-10-03_</span><span class="sxs-lookup"><span data-stu-id="3f032-103">_**Topic Last Modified:** 2012-10-03_</span></span>

<span data-ttu-id="3f032-104">O MediaLine View armazena informações sobre cada linha de mídia no banco de dados.</span><span class="sxs-lookup"><span data-stu-id="3f032-104">The MediaLine View stores information about each media line in the database.</span></span> <span data-ttu-id="3f032-105">Uma sessão de áudio normalmente contém uma linha de mídia de áudio.</span><span class="sxs-lookup"><span data-stu-id="3f032-105">One audio session typically contains one audio media line.</span></span> <span data-ttu-id="3f032-106">Uma sessão de áudio e vídeo (A/V) normalmente contém uma linha de mídia de áudio e uma linha de mídia de vídeo; no entanto, a sessão pode conter duas linhas de mídia de vídeo se um dispositivo de conferência ou o modo de exibição de galeria for usado.</span><span class="sxs-lookup"><span data-stu-id="3f032-106">One audio and video (A/V) session typically contains one audio media line and one video media line; however, the session might contain two video media lines if a conferencing device is used or if Gallery View is used.</span></span> <span data-ttu-id="3f032-107">Este modo de exibição foi introduzido no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="3f032-107">This view was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="3f032-108">Coluna</span><span class="sxs-lookup"><span data-stu-id="3f032-108">Column</span></span></th>
<th><span data-ttu-id="3f032-109">Tipo de dado</span><span class="sxs-lookup"><span data-stu-id="3f032-109">Data Type</span></span></th>
<th><span data-ttu-id="3f032-110">detalhes</span><span class="sxs-lookup"><span data-stu-id="3f032-110">details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="3f032-111">ConferenceDateTime</span><span class="sxs-lookup"><span data-stu-id="3f032-111">ConferenceDateTime</span></span></p></td>
<td><p><span data-ttu-id="3f032-112">datetime</span><span class="sxs-lookup"><span data-stu-id="3f032-112">datetime</span></span></p></td>
<td><p><span data-ttu-id="3f032-113">Referenciado da <a href="lync-server-2013-medialine-table.md">tabela de mídia no Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="3f032-113">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3f032-114">SessionSeq</span><span class="sxs-lookup"><span data-stu-id="3f032-114">SessionSeq</span></span></p></td>
<td><p><span data-ttu-id="3f032-115">int</span><span class="sxs-lookup"><span data-stu-id="3f032-115">int</span></span></p></td>
<td><p><span data-ttu-id="3f032-116">Referenciado da <a href="lync-server-2013-medialine-table.md">tabela de mídia no Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="3f032-116">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3f032-117">MediaLineLabel</span><span class="sxs-lookup"><span data-stu-id="3f032-117">MediaLineLabel</span></span></p></td>
<td><p><span data-ttu-id="3f032-118">tinyint</span><span class="sxs-lookup"><span data-stu-id="3f032-118">tinyint</span></span></p></td>
<td><p><span data-ttu-id="3f032-119">Referenciado da <a href="lync-server-2013-medialine-table.md">tabela de mídia no Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="3f032-119">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3f032-120">CallerIceWarningFlags</span><span class="sxs-lookup"><span data-stu-id="3f032-120">CallerIceWarningFlags</span></span></p></td>
<td><p><span data-ttu-id="3f032-121">int</span><span class="sxs-lookup"><span data-stu-id="3f032-121">int</span></span></p></td>
<td><p><span data-ttu-id="3f032-p102">Informações sobre o processo de ICE (Estabelecimento de Conectividade Interativa) descrito em sinalizadores de bits do autor da chamada. Para obter detalhes, consulte a Especificação de protocolo do servidor de monitoramento de Qualidade da Experiência.</span><span class="sxs-lookup"><span data-stu-id="3f032-p102">Information about Interactive Connectivity Establishment (ICE) process described in bits flags for the caller. For details, refer to the Quality of Experience Monitoring Server Protocol Specification.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3f032-124">CalleeIceWarningFlags</span><span class="sxs-lookup"><span data-stu-id="3f032-124">CalleeIceWarningFlags</span></span></p></td>
<td><p><span data-ttu-id="3f032-125">int</span><span class="sxs-lookup"><span data-stu-id="3f032-125">int</span></span></p></td>
<td><p><span data-ttu-id="3f032-p103">Informações sobre o processo do ICE (Estabelecimento de Conectividade Interativa) descrito em sinalizadores de bits para o chamador. Para detalhes, consulte a Especificação do Protocolo de Servidor do Monitoramento da Qualidade da Experiência.</span><span class="sxs-lookup"><span data-stu-id="3f032-p103">Information about Interactive Connectivity Establishment (ICE) process described in bits flags for the callee. For details, refer to the Quality of Experience Monitoring Server Protocol Specification.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3f032-128">Segurança</span><span class="sxs-lookup"><span data-stu-id="3f032-128">Security</span></span></p></td>
<td><p><span data-ttu-id="3f032-129">tinyint</span><span class="sxs-lookup"><span data-stu-id="3f032-129">tinyint</span></span></p></td>
<td><p><span data-ttu-id="3f032-p104">Perfil de segurança em uso. 0 é NONE (nenhum), 1 é SRTP, 2 é V1.</span><span class="sxs-lookup"><span data-stu-id="3f032-p104">Security profile in use. 0 is NONE, 1 is SRTP, 2 is V1.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3f032-132">Transport</span><span class="sxs-lookup"><span data-stu-id="3f032-132">Transport</span></span></p></td>
<td><p><span data-ttu-id="3f032-133">tinyint</span><span class="sxs-lookup"><span data-stu-id="3f032-133">tinyint</span></span></p></td>
<td><p><span data-ttu-id="3f032-p105">Tipo de transporte. 0 é UDP, 1 é TCP.</span><span class="sxs-lookup"><span data-stu-id="3f032-p105">Transport type. 0 is UDP, 1 is TCP.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3f032-136">CallerIPAddr</span><span class="sxs-lookup"><span data-stu-id="3f032-136">CallerIPAddr</span></span></p></td>
<td><p><span data-ttu-id="3f032-137">var (50)</span><span class="sxs-lookup"><span data-stu-id="3f032-137">var(50)</span></span></p></td>
<td><p><span data-ttu-id="3f032-p106">Endereço IP do chamador. Pode ser um endereço IPv4 ou IPv6.</span><span class="sxs-lookup"><span data-stu-id="3f032-p106">IP address of the caller. This can be either an IPv4 or IPv6 address.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3f032-140">CallerPort</span><span class="sxs-lookup"><span data-stu-id="3f032-140">CallerPort</span></span></p></td>
<td><p><span data-ttu-id="3f032-141">int</span><span class="sxs-lookup"><span data-stu-id="3f032-141">int</span></span></p></td>
<td><p><span data-ttu-id="3f032-142">Porta usada pelo chamador.</span><span class="sxs-lookup"><span data-stu-id="3f032-142">Port used by the caller.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3f032-143">CallerInside</span><span class="sxs-lookup"><span data-stu-id="3f032-143">CallerInside</span></span></p></td>
<td><p><span data-ttu-id="3f032-144">bits</span><span class="sxs-lookup"><span data-stu-id="3f032-144">bit</span></span></p></td>
<td><p><span data-ttu-id="3f032-p107">Indica se o chamador está ou não dentro da rede da organização. 1 significa que o chamador está dentro da rede corporativa, 0 significa que está fora.</span><span class="sxs-lookup"><span data-stu-id="3f032-p107">Indicates whether or not the caller is inside the organization network. 1 means that the caller is inside the enterprise network. 0 means that the caller is outside the network.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3f032-148">CallerMacAddress</span><span class="sxs-lookup"><span data-stu-id="3f032-148">CallerMacAddress</span></span></p></td>
<td><p><span data-ttu-id="3f032-149">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="3f032-149">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="3f032-150">Endereço MAC da interface de rede usada pelo chamador.</span><span class="sxs-lookup"><span data-stu-id="3f032-150">MAC address of network interface used by caller.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3f032-151">CallerRelayIPAddr</span><span class="sxs-lookup"><span data-stu-id="3f032-151">CallerRelayIPAddr</span></span></p></td>
<td><p><span data-ttu-id="3f032-152">var (50)</span><span class="sxs-lookup"><span data-stu-id="3f032-152">var(50)</span></span></p></td>
<td><p><span data-ttu-id="3f032-153">Endereço IP do serviço de borda A/V usado pelo chamador.</span><span class="sxs-lookup"><span data-stu-id="3f032-153">IP Address of the A/V Edge service used by the caller.</span></span> <span data-ttu-id="3f032-154">Consulte a <a href="lync-server-2013-ipaddress-table.md">tabela IPAddress no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="3f032-154">See the <a href="lync-server-2013-ipaddress-table.md">IPAddress table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3f032-155">CalleeRelayPort</span><span class="sxs-lookup"><span data-stu-id="3f032-155">CalleeRelayPort</span></span></p></td>
<td><p><span data-ttu-id="3f032-156">int</span><span class="sxs-lookup"><span data-stu-id="3f032-156">int</span></span></p></td>
<td><p><span data-ttu-id="3f032-157">Porta usada no serviço de Borda de A/V usado pelo chamador.</span><span class="sxs-lookup"><span data-stu-id="3f032-157">Port used on the A/V Edge service used by the caller.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3f032-158">CallerReflexiveIPAddr</span><span class="sxs-lookup"><span data-stu-id="3f032-158">CallerReflexiveIPAddr</span></span></p></td>
<td><p><span data-ttu-id="3f032-159">var (50)</span><span class="sxs-lookup"><span data-stu-id="3f032-159">var(50)</span></span></p></td>
<td><p><span data-ttu-id="3f032-160">Endereço IP do chamador conforme reportado pelo serviço de Borda de A/V.</span><span class="sxs-lookup"><span data-stu-id="3f032-160">Caller’s IP address as reported by the A/V Edge service.</span></span> <span data-ttu-id="3f032-161">Este endereço pode ser diferente do endereço na coluna CallerIPAddr se o cliente estiver localizado atrás de uma NAT, por exemplo.</span><span class="sxs-lookup"><span data-stu-id="3f032-161">This address may be different that the CallerIPAddr if the client is located behind a NAT for example.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3f032-162">CallerCaptureDev</span><span class="sxs-lookup"><span data-stu-id="3f032-162">CallerCaptureDev</span></span></p></td>
<td><p><span data-ttu-id="3f032-163">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="3f032-163">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="3f032-164">Nome do dispositivo de captura do chamador.</span><span class="sxs-lookup"><span data-stu-id="3f032-164">Caller’s capture device name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3f032-165">CallerRenderDev</span><span class="sxs-lookup"><span data-stu-id="3f032-165">CallerRenderDev</span></span></p></td>
<td><p><span data-ttu-id="3f032-166">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="3f032-166">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="3f032-167">Nome do dispositivo de renderização do chamador.</span><span class="sxs-lookup"><span data-stu-id="3f032-167">Caller’s render device name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3f032-168">CallerCaptureDevDriver</span><span class="sxs-lookup"><span data-stu-id="3f032-168">CallerCaptureDevDriver</span></span></p></td>
<td><p><span data-ttu-id="3f032-169">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="3f032-169">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="3f032-170">Nome do driver do dispositivo de captura do chamador.</span><span class="sxs-lookup"><span data-stu-id="3f032-170">Caller’s capture device driver name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3f032-171">CallerRenderDevDriver</span><span class="sxs-lookup"><span data-stu-id="3f032-171">CallerRenderDevDriver</span></span></p></td>
<td><p><span data-ttu-id="3f032-172">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="3f032-172">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="3f032-173">Nome da unidade do dispositivo de renderização do chamador.</span><span class="sxs-lookup"><span data-stu-id="3f032-173">Caller’s render device driver name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3f032-174">CallerWifiDriverDeviceDesc</span><span class="sxs-lookup"><span data-stu-id="3f032-174">CallerWifiDriverDeviceDesc</span></span></p></td>
<td><p><span data-ttu-id="3f032-175">varchar (256</span><span class="sxs-lookup"><span data-stu-id="3f032-175">varchar(256</span></span></p></td>
<td><p><span data-ttu-id="3f032-176">Descrição da unidade wifi do chamador.</span><span class="sxs-lookup"><span data-stu-id="3f032-176">Caller’s Wifi driver description.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3f032-177">CallerWifiDriverVersion</span><span class="sxs-lookup"><span data-stu-id="3f032-177">CallerWifiDriverVersion</span></span></p></td>
<td><p><span data-ttu-id="3f032-178">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="3f032-178">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="3f032-179">Versão da unidade wifi do chamador.</span><span class="sxs-lookup"><span data-stu-id="3f032-179">Caller’s Wifi driver version.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3f032-180">CalleeNetworkConnectionDetail</span><span class="sxs-lookup"><span data-stu-id="3f032-180">CalleeNetworkConnectionDetail</span></span></p></td>
<td><p><span data-ttu-id="3f032-181">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="3f032-181">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="3f032-182">Detalhes da conexão de rede do chamador.</span><span class="sxs-lookup"><span data-stu-id="3f032-182">Details of caller’s network connection.</span></span> <span data-ttu-id="3f032-183">Consulte a <a href="lync-server-2013-networkconnectiondetail-table.md">tabela NetworkConnectionDetail no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="3f032-183">See the <a href="lync-server-2013-networkconnectiondetail-table.md">NetworkConnectionDetail table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3f032-184">CallerBssid</span><span class="sxs-lookup"><span data-stu-id="3f032-184">CallerBssid</span></span></p></td>
<td><p><span data-ttu-id="3f032-185">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="3f032-185">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="3f032-186">Identificador SSID usado pela conexão WiFi do chamador.</span><span class="sxs-lookup"><span data-stu-id="3f032-186">Basic Service Set Identifier used by callers WiFi connection.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3f032-187">CallerVPN</span><span class="sxs-lookup"><span data-stu-id="3f032-187">CallerVPN</span></span></p></td>
<td><p><span data-ttu-id="3f032-188">bits</span><span class="sxs-lookup"><span data-stu-id="3f032-188">bit</span></span></p></td>
<td><p><span data-ttu-id="3f032-p111">Indica se o chamador se conectou por uma rede virtual privada. 1 é rede virtual privada (VPN), 0 é não-VPN.</span><span class="sxs-lookup"><span data-stu-id="3f032-p111">Indicates whether the caller connected over a virtual private network. 1 is virtual private network (VPN), 0 is non-VPN.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3f032-191">CalleeIPAddr</span><span class="sxs-lookup"><span data-stu-id="3f032-191">CalleeIPAddr</span></span></p></td>
<td><p><span data-ttu-id="3f032-192">var (50)</span><span class="sxs-lookup"><span data-stu-id="3f032-192">var(50)</span></span></p></td>
<td><p><span data-ttu-id="3f032-193">Endereço IP do receptor da chamada.</span><span class="sxs-lookup"><span data-stu-id="3f032-193">IP address of the callee.</span></span> <span data-ttu-id="3f032-194">Pode ser um endereço IPv4 ou IPv6.</span><span class="sxs-lookup"><span data-stu-id="3f032-194">This can be either an IPv4 or IPv6 address.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3f032-195">CalleePort</span><span class="sxs-lookup"><span data-stu-id="3f032-195">CalleePort</span></span></p></td>
<td><p><span data-ttu-id="3f032-196">int</span><span class="sxs-lookup"><span data-stu-id="3f032-196">int</span></span></p></td>
<td><p><span data-ttu-id="3f032-197">Porta usada pelo receptor.</span><span class="sxs-lookup"><span data-stu-id="3f032-197">Port used by the callee.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3f032-198">CalleeInside</span><span class="sxs-lookup"><span data-stu-id="3f032-198">CalleeInside</span></span></p></td>
<td><p><span data-ttu-id="3f032-199">bits</span><span class="sxs-lookup"><span data-stu-id="3f032-199">bit</span></span></p></td>
<td><p><span data-ttu-id="3f032-p113">Indica se o receptor da chamada está dentro da rede corporativa. 1 significa que o receptor está dentro da rede corporativa, 0 significa que está fora.</span><span class="sxs-lookup"><span data-stu-id="3f032-p113">Indicates whether the callee is inside the enterprise network. 1 means callee is inside the enterprise network, 0 means the callee is outside the network.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3f032-202">CalleeMacAddress</span><span class="sxs-lookup"><span data-stu-id="3f032-202">CalleeMacAddress</span></span></p></td>
<td><p><span data-ttu-id="3f032-203">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="3f032-203">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="3f032-204">Endereço MAC da interface de rede usada pelo receptor da chamada.</span><span class="sxs-lookup"><span data-stu-id="3f032-204">MAC address of network interface used by callee.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3f032-205">CalleeRelayIPAddr</span><span class="sxs-lookup"><span data-stu-id="3f032-205">CalleeRelayIPAddr</span></span></p></td>
<td><p><span data-ttu-id="3f032-206">var (50)</span><span class="sxs-lookup"><span data-stu-id="3f032-206">var(50)</span></span></p></td>
<td><p><span data-ttu-id="3f032-207">Endereço IP do serviço de Borda de A/V usado pelo receptor da chamada.</span><span class="sxs-lookup"><span data-stu-id="3f032-207">IP Address of the A/V Edge service used by the callee.</span></span> <span data-ttu-id="3f032-208">Consulte a <a href="lync-server-2013-ipaddress-table.md">tabela IPAddress no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="3f032-208">See the <a href="lync-server-2013-ipaddress-table.md">IPAddress table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3f032-209">CalleeRelayPort</span><span class="sxs-lookup"><span data-stu-id="3f032-209">CalleeRelayPort</span></span></p></td>
<td><p><span data-ttu-id="3f032-210">int</span><span class="sxs-lookup"><span data-stu-id="3f032-210">int</span></span></p></td>
<td><p><span data-ttu-id="3f032-211">Porta usada no serviço de Borda de A/V usado pelo receptor da chamada.</span><span class="sxs-lookup"><span data-stu-id="3f032-211">Port used on the A/V Edge service used by the callee.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3f032-212">CalleeReflexiveIPAddr</span><span class="sxs-lookup"><span data-stu-id="3f032-212">CalleeReflexiveIPAddr</span></span></p></td>
<td><p><span data-ttu-id="3f032-213">var (50)</span><span class="sxs-lookup"><span data-stu-id="3f032-213">var(50)</span></span></p></td>
<td><p><span data-ttu-id="3f032-214">Endereço IP do receptor da chamada conforme reportado pelo serviço de Borda de A/V.</span><span class="sxs-lookup"><span data-stu-id="3f032-214">Callee’s IP address as reported by the A/V Edge service.</span></span> <span data-ttu-id="3f032-215">Este endereço pode ser diferente do endereço na coluna CalleeIPAddr se o cliente estiver localizado atrás de uma NAT, por exemplo.</span><span class="sxs-lookup"><span data-stu-id="3f032-215">This address may be different that the CalleeIPAddr if the client is located behind a NAT for example.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3f032-216">CalleeCaptureDev</span><span class="sxs-lookup"><span data-stu-id="3f032-216">CalleeCaptureDev</span></span></p></td>
<td><p><span data-ttu-id="3f032-217">var (50)</span><span class="sxs-lookup"><span data-stu-id="3f032-217">var(50)</span></span></p></td>
<td><p><span data-ttu-id="3f032-218">Nome do dispositivo de captura do receptor da chamada.</span><span class="sxs-lookup"><span data-stu-id="3f032-218">Callee’s capture device name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3f032-219">CalleeRenderDev</span><span class="sxs-lookup"><span data-stu-id="3f032-219">CalleeRenderDev</span></span></p></td>
<td><p><span data-ttu-id="3f032-220">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="3f032-220">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="3f032-221">Nome do dispositivo de renderização do receptor.</span><span class="sxs-lookup"><span data-stu-id="3f032-221">Callee’s render device name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3f032-222">CalleeCaptureDevDriver</span><span class="sxs-lookup"><span data-stu-id="3f032-222">CalleeCaptureDevDriver</span></span></p></td>
<td><p><span data-ttu-id="3f032-223">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="3f032-223">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="3f032-224">Nome do driver do dispositivo de captura do receptor.</span><span class="sxs-lookup"><span data-stu-id="3f032-224">Callee’s capture device driver name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3f032-225">CalleeRenderDevDriver</span><span class="sxs-lookup"><span data-stu-id="3f032-225">CalleeRenderDevDriver</span></span></p></td>
<td><p><span data-ttu-id="3f032-226">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="3f032-226">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="3f032-227">Nome da unidade do dispositivo de renderização do receptor da chamada.</span><span class="sxs-lookup"><span data-stu-id="3f032-227">Callee’s render device driver name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3f032-228">CalleeWifiDriverDeviceDesc</span><span class="sxs-lookup"><span data-stu-id="3f032-228">CalleeWifiDriverDeviceDesc</span></span></p></td>
<td><p><span data-ttu-id="3f032-229">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="3f032-229">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="3f032-230">Descrição da unidade wifi do receptor da chamada.</span><span class="sxs-lookup"><span data-stu-id="3f032-230">Callee’s Wifi driver description.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3f032-231">CalleeWifiDriverVersion</span><span class="sxs-lookup"><span data-stu-id="3f032-231">CalleeWifiDriverVersion</span></span></p></td>
<td><p><span data-ttu-id="3f032-232">varchar (256</span><span class="sxs-lookup"><span data-stu-id="3f032-232">varchar(256</span></span></p></td>
<td><p><span data-ttu-id="3f032-233">Versão da unidade wifi do receptor da chamada.</span><span class="sxs-lookup"><span data-stu-id="3f032-233">Callee’s Wifi driver version.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3f032-234">CalleeNetworkConnectionDetail</span><span class="sxs-lookup"><span data-stu-id="3f032-234">CalleeNetworkConnectionDetail</span></span></p></td>
<td><p><span data-ttu-id="3f032-235">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="3f032-235">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="3f032-236">Detalhes da conexão de rede do receptor da chamada.</span><span class="sxs-lookup"><span data-stu-id="3f032-236">Details of callee’s network connection.</span></span> <span data-ttu-id="3f032-237">Consulte a <a href="lync-server-2013-networkconnectiondetail-table.md">tabela NetworkConnectionDetail no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="3f032-237">See the <a href="lync-server-2013-networkconnectiondetail-table.md">NetworkConnectionDetail table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3f032-238">CalleeBssid</span><span class="sxs-lookup"><span data-stu-id="3f032-238">CalleeBssid</span></span></p></td>
<td><p><span data-ttu-id="3f032-239">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="3f032-239">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="3f032-240">Identificador SSID usado pela conexão WiFi do receptor da chamada.</span><span class="sxs-lookup"><span data-stu-id="3f032-240">Basic Service Set Identifier used by callee’s WiFi connection.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3f032-241">CalleeVPN</span><span class="sxs-lookup"><span data-stu-id="3f032-241">CalleeVPN</span></span></p></td>
<td><p><span data-ttu-id="3f032-242">bits</span><span class="sxs-lookup"><span data-stu-id="3f032-242">bit</span></span></p></td>
<td><p><span data-ttu-id="3f032-p117">Indica se o receptor da chamada se conectou por uma rede virtual privada. 1 é rede virtual privada (VPN), 0 é não-VPN.</span><span class="sxs-lookup"><span data-stu-id="3f032-p117">Indicates whether the callee connected over a virtual private network. 1 is virtual private network (VPN), 0 is non-VPN.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3f032-245">ConversationalMOS</span><span class="sxs-lookup"><span data-stu-id="3f032-245">ConversationalMOS</span></span></p></td>
<td><p><span data-ttu-id="3f032-246">decimal (3, 2)</span><span class="sxs-lookup"><span data-stu-id="3f032-246">decimal(3,2)</span></span></p></td>
<td><p><span data-ttu-id="3f032-247">MOS da Conversa de Banda Estreita das sessões de áudio (com base nos dois fluxos de áudio).</span><span class="sxs-lookup"><span data-stu-id="3f032-247">Narrowband Conversational MOS of the audio sessions (based on both audio streams).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3f032-248">AppliedBandwidthLimit</span><span class="sxs-lookup"><span data-stu-id="3f032-248">AppliedBandwidthLimit</span></span></p></td>
<td><p><span data-ttu-id="3f032-249">int</span><span class="sxs-lookup"><span data-stu-id="3f032-249">int</span></span></p></td>
<td><p><span data-ttu-id="3f032-p118">Esta é a largura de banda real aplicada a um dado fluxo de envio, considerando várias configurações de política (TURN, API, SDP, Servidor de Políticas, etc.). Não deve ser confundida com a largura de banda real porque pode haver uma largura de banda real menor com base na estimativa da largura de banda. Esta é basicamente a largura de banda máxima que o fluxo de envio pode usar, salvo limites impostos pela estimativa da largura de banda.</span><span class="sxs-lookup"><span data-stu-id="3f032-p118">This is the actual bandwidth applied to the given send side stream given various policy settings (TURN, API, SDP, Policy Server, etc.). This should not to be confused with the effective bandwidth because there can be a lower effective bandwidth based on the bandwidth estimate. This is basically the maximum bandwidth the send stream can take barring limits imposed by the bandwidth estimate.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3f032-253">AppliedBandwidthSource</span><span class="sxs-lookup"><span data-stu-id="3f032-253">AppliedBandwidthSource</span></span></p></td>
<td><p><span data-ttu-id="3f032-254">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="3f032-254">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="3f032-p119">Origem da capacidade da largura de banda imposta. Descreve de onde o limite da largura de banda está vindo (por exemplo, “Servidor de Políticas”, “Servidor TURN” ou “Modalidade”).</span><span class="sxs-lookup"><span data-stu-id="3f032-p119">Source of the bandwidth cap being imposed. It describes where the bandwidth limit is coming from (for example, “Policy Server”, “TURN Server”, or “Modality”).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3f032-257">Chamador</span><span class="sxs-lookup"><span data-stu-id="3f032-257">Caller</span></span></p></td>
<td><p><span data-ttu-id="3f032-258">bits</span><span class="sxs-lookup"><span data-stu-id="3f032-258">bit</span></span></p></td>
<td><p><span data-ttu-id="3f032-259">Indica se as métricas do chamador foram recebidas; 1 é sim, 0 é não.</span><span class="sxs-lookup"><span data-stu-id="3f032-259">Indicates whether metrics from the caller were received; 1 is yes, 0 is no.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3f032-260">Receptor</span><span class="sxs-lookup"><span data-stu-id="3f032-260">Callee</span></span></p></td>
<td><p><span data-ttu-id="3f032-261">bits</span><span class="sxs-lookup"><span data-stu-id="3f032-261">bit</span></span></p></td>
<td><p><span data-ttu-id="3f032-262">Indica se as métricas do receptor da chamada foram recebidas; 1 é sim, 0 é não.</span><span class="sxs-lookup"><span data-stu-id="3f032-262">Indicates whether metrics from the call receiver were received; 1 is yes, 0 is no.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3f032-263">MidCallReport</span><span class="sxs-lookup"><span data-stu-id="3f032-263">MidCallReport</span></span></p></td>
<td><p><span data-ttu-id="3f032-264">bits</span><span class="sxs-lookup"><span data-stu-id="3f032-264">bit</span></span></p></td>
<td><p><span data-ttu-id="3f032-265">Indica se o relatório refere-se a uma parte da chamada ou à chamada completa.</span><span class="sxs-lookup"><span data-stu-id="3f032-265">Indicates whether the report is for a portion of the call or for the complete call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3f032-266">ClassifiedPoorCall</span><span class="sxs-lookup"><span data-stu-id="3f032-266">ClassifiedPoorCall</span></span></p></td>
<td><p><span data-ttu-id="3f032-267">bits</span><span class="sxs-lookup"><span data-stu-id="3f032-267">bit</span></span></p></td>
<td><p><span data-ttu-id="3f032-268">Indica se uma chamada foi classificada como ruim (1) ou boa (0).</span><span class="sxs-lookup"><span data-stu-id="3f032-268">Indicates whether a call was classified as a poor call (1) or as a good call (0).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3f032-269">CallerConnectivityICE</span><span class="sxs-lookup"><span data-stu-id="3f032-269">CallerConnectivityICE</span></span></p></td>
<td><p><span data-ttu-id="3f032-270">tinyint</span><span class="sxs-lookup"><span data-stu-id="3f032-270">tinyint</span></span></p></td>
<td><p><span data-ttu-id="3f032-271">Indica se o chamador se conectou à rede usando o protocolo ICE (Internet Connectivity Establishment).</span><span class="sxs-lookup"><span data-stu-id="3f032-271">Indicates whether the caller connected to the network using the ICE protocol (Internet Connectivity Establishment).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3f032-272">CalleeConnectivityICE</span><span class="sxs-lookup"><span data-stu-id="3f032-272">CalleeConnectivityICE</span></span></p></td>
<td><p><span data-ttu-id="3f032-273">tinyint</span><span class="sxs-lookup"><span data-stu-id="3f032-273">tinyint</span></span></p></td>
<td><p><span data-ttu-id="3f032-274">Indica se o usuário receptor da chamada se conectou à rede usando o protocolo ICE (Internet Connectivity Establishment).</span><span class="sxs-lookup"><span data-stu-id="3f032-274">Indicates whether the user called connected to the network using the ICE protocol (Internet Connectivity Establishment).</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

