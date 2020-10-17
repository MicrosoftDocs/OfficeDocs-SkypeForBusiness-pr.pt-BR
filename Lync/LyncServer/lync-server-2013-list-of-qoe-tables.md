---
title: 'Lync Server 2013: lista de tabelas QoE'
description: 'Lync Server 2013: lista de tabelas QoE.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: List of QoE tables
ms:assetid: 176194d7-d184-4e23-94bb-cb62b4db47f5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398236(v=OCS.15)
ms:contentKeyID: 48183512
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 871babf246f616d306a03f84f9134605dd595999
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48550037"
---
# <a name="list-of-qoe-tables-in-lync-server-2013"></a><span data-ttu-id="e319f-103">Lista de tabelas de QoE no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e319f-103">List of QoE tables in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e319f-104">_**Última modificação do tópico:** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="e319f-104">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="e319f-105">O esquema de banco de dados consiste nas tabelas a seguir.</span><span class="sxs-lookup"><span data-stu-id="e319f-105">The database schema consists of the following tables.</span></span>

<span data-ttu-id="e319f-106">**Tabelas de suporte**</span><span class="sxs-lookup"><span data-stu-id="e319f-106">**Supporting Tables**</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e319f-107"><strong>Table</strong></span><span class="sxs-lookup"><span data-stu-id="e319f-107"><strong>Table</strong></span></span></th>
<th><span data-ttu-id="e319f-108"><strong>Descrição</strong></span><span class="sxs-lookup"><span data-stu-id="e319f-108"><strong>Description</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e319f-109"><a href="lync-server-2013-appsharingmetricsthreshold-table.md">Tabela AppSharingMetricsThreshold no Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="e319f-109"><a href="lync-server-2013-appsharingmetricsthreshold-table.md">AppSharingMetricsThreshold table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="e319f-110">Armazena valores ótimos e aceitáveis para as métricas de Qualidade da Experiência usadas com compartilhamento de aplicativo.</span><span class="sxs-lookup"><span data-stu-id="e319f-110">Stores optimal and acceptable values for the Quality of Experience metrics used with application sharing.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e319f-111"><a href="lync-server-2013-codecdescription-table.md">Tabela CodecDescription no Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="e319f-111"><a href="lync-server-2013-codecdescription-table.md">CodecDescription table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="e319f-112">Mapeia identificadores exclusivos de codec ao codec correspondente.</span><span class="sxs-lookup"><span data-stu-id="e319f-112">Maps unique codec identifiers to their corresponding codec.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e319f-113"><a href="lync-server-2013-ipaddress-table.md">Tabela IPAddress no Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="e319f-113"><a href="lync-server-2013-ipaddress-table.md">IPAddress table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="e319f-114">Mapeia endereços IP aos identificadores de endereços IP exclusivos usados em outros locais no banco de dados de Qualidade da Experiência.</span><span class="sxs-lookup"><span data-stu-id="e319f-114">Maps IP addresses to the unique IP address identifiers used elsewhere in the Quality of Experience database.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e319f-115"><a href="lync-server-2013-networkconnectiondetail-table.md">Tabela NetworkConnectionDetail no Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="e319f-115"><a href="lync-server-2013-networkconnectiondetail-table.md">NetworkConnectionDetail table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="e319f-116">Mapeia os tipos de conexão de rede aos identificadores de conexão de rede usados em outros locais no banco de dados de Qualidade da Experiência.</span><span class="sxs-lookup"><span data-stu-id="e319f-116">Maps network connection types to the network connection identifiers used elsewhere in the Quality of Experience database.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e319f-117"><a href="lync-server-2013-purgesettings-table-qoe.md">Tabela PurgeSettings (QoE) no Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="e319f-117"><a href="lync-server-2013-purgesettings-table-qoe.md">PurgeSettings table (QoE) in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="e319f-118">Armazena informações que especificam se (e quando) registros de Qualidade da Experiência antigos serão automaticamente deletados do banco de dados de QoE (Qualidade da Experiência).</span><span class="sxs-lookup"><span data-stu-id="e319f-118">Stores information that specifies if (and when) outdated Quality of Experience records will automatically be deleted from the QoE database.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e319f-119"><a href="lync-server-2013-traceroute-table.md">Tabela de TraceRoute no Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="e319f-119"><a href="lync-server-2013-traceroute-table.md">TraceRoute table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="e319f-120">Armazena informaçoes de roteamento para chamadas.</span><span class="sxs-lookup"><span data-stu-id="e319f-120">Stores routing information for calls.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e319f-121"><a href="lync-server-2013-useragentdef-table-qoe.md">Tabela UserAgentDef (QoE) no Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="e319f-121"><a href="lync-server-2013-useragentdef-table-qoe.md">UserAgentDef table (QoE) in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="e319f-122">Mapeia os identificadores de agente do usuário aos nomes descritivos dos agentes.</span><span class="sxs-lookup"><span data-stu-id="e319f-122">Maps user agent identifiers to the agent’s descriptive names.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e319f-123"><a href="lync-server-2013-videometricsthreshold-table.md">Tabela VideoMetricsThreshold no Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="e319f-123"><a href="lync-server-2013-videometricsthreshold-table.md">VideoMetricsThreshold table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="e319f-124">Armazena valores ótimos e aceitáveis para as métricas de Qualidade da Experiência usadas com chamadas de vídeo.</span><span class="sxs-lookup"><span data-stu-id="e319f-124">Stores optimal and acceptable values for the Quality of Experience metrics used with video calls.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e319f-125"><a href="lync-server-2013-useragent-table.md">Tabela UserAgent no Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="e319f-125"><a href="lync-server-2013-useragent-table.md">UserAgent table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="e319f-126">Armazena as cadeias de Agente de Usuário (UA) do Protocolo de Iniciação de Sessão (SIP) e tipos de UA usados em sessões de áudio e vídeo.</span><span class="sxs-lookup"><span data-stu-id="e319f-126">Stores Session Initiation Protocol (SIP) User Agent (UA) strings and UA types used in audio and video sessions.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e319f-127"><a href="lync-server-2013-user-table.md">Tabela de usuário no Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="e319f-127"><a href="lync-server-2013-user-table.md">User table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="e319f-128">Armazena URIs de usuário, de conferência, e de telefone usados em sessões de áudio e vídeo.</span><span class="sxs-lookup"><span data-stu-id="e319f-128">Stores user, conference, and phone URIs used in audio and video sessions.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e319f-129"><a href="lync-server-2013-endpoint-table.md">Tabela de pontos de extremidade no Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="e319f-129"><a href="lync-server-2013-endpoint-table.md">Endpoint table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="e319f-130">Armazena nomes de computador FQDN de pontos de extremidade que participam de sessões de áudio e vídeo.</span><span class="sxs-lookup"><span data-stu-id="e319f-130">Stores FQDN computer names of endpoints participating in audio and video sessions.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e319f-131"><a href="lync-server-2013-pool-table.md">Tabela de pool no Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="e319f-131"><a href="lync-server-2013-pool-table.md">Pool table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="e319f-132">Armazena os nomes de pools às quais os dados de métrica pertencem.</span><span class="sxs-lookup"><span data-stu-id="e319f-132">Stores the names of pools to which metrics data belongs.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e319f-133"><a href="lync-server-2013-device-table.md">Tabela de dispositivos no Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="e319f-133"><a href="lync-server-2013-device-table.md">Device table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="e319f-134">Armazena os dispositivos de captura e de renderização que são usados em chamadas de áudio/vídeo.</span><span class="sxs-lookup"><span data-stu-id="e319f-134">Stores capture devices and render devices which are used in an audio/video calls.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e319f-135"><a href="lync-server-2013-devicedriver-table.md">Tabela DeviceDriver no Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="e319f-135"><a href="lync-server-2013-devicedriver-table.md">DeviceDriver table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="e319f-136">Armazena o driver do dispositivo de captura e de renderização que são usados em chamadas de áudio/vídeo.</span><span class="sxs-lookup"><span data-stu-id="e319f-136">Stores driver for the capture device and the render device which are used in audio/video calls.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e319f-137"><a href="lync-server-2013-conference-table.md">Tabela de conferência no Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="e319f-137"><a href="lync-server-2013-conference-table.md">Conference table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="e319f-138">Armazena os URIs da conferência para cenários de conferência ou DialogID para outros cenários.</span><span class="sxs-lookup"><span data-stu-id="e319f-138">Stores Conference URIs for conference scenarios or DialogID for other scenarios.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e319f-139"><a href="lync-server-2013-sessioncorrelation-table.md">Tabela SessionCorrelation no Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="e319f-139"><a href="lync-server-2013-sessioncorrelation-table.md">SessionCorrelation table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="e319f-140">Armazena CorrelationID para chamadas PSTN.</span><span class="sxs-lookup"><span data-stu-id="e319f-140">Stores CorrelationID for PSTN calls.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e319f-141"><a href="lync-server-2013-payloaddescription-table.md">Tabela PayloadDescription no Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="e319f-141"><a href="lync-server-2013-payloaddescription-table.md">PayloadDescription table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="e319f-142">Armazena o Codec usado em chamadas de áudio/vídeo.</span><span class="sxs-lookup"><span data-stu-id="e319f-142">Stores the Codec used in audio/video calls.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e319f-143"><a href="lync-server-2013-appliedbandwidthsource-table.md">Tabela AppliedBandwidthSource no Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="e319f-143"><a href="lync-server-2013-appliedbandwidthsource-table.md">AppliedBandwidthSource table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="e319f-144">Armazena a origem da largura de banda usada em chamadas de áudio/vídeo.</span><span class="sxs-lookup"><span data-stu-id="e319f-144">Stores the bandwidth source used in audio/video calls.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e319f-145"><a href="lync-server-2013-macaddress-table.md">Tabela MacAddress no Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="e319f-145"><a href="lync-server-2013-macaddress-table.md">MacAddress table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="e319f-146">Armazena o endereço MAC dos pontos de extremidade participantes de sessões de áudio e vídeo.</span><span class="sxs-lookup"><span data-stu-id="e319f-146">Stores the MAC address of the endpoints participating in audio and video sessions.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e319f-147"><a href="lync-server-2013-dialog-table.md">Tabela Dialog no Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="e319f-147"><a href="lync-server-2013-dialog-table.md">Dialog table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="e319f-148">Armazena a ID de Diálogo de sessões de áudio e vídeo.</span><span class="sxs-lookup"><span data-stu-id="e319f-148">Stores the Dialog ID of audio and video sessions.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e319f-149"><a href="lync-server-2013-region-table.md">Tabela Region no Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="e319f-149"><a href="lync-server-2013-region-table.md">Region table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="e319f-150">Armazena a região de rede definida na configuração NCS.</span><span class="sxs-lookup"><span data-stu-id="e319f-150">Stores the network region defined in NCS setting.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e319f-151"><a href="lync-server-2013-usersite-table.md">Tabela usersite no Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="e319f-151"><a href="lync-server-2013-usersite-table.md">UserSite table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="e319f-152">Armazena o site de rede definido na configuração NCS.</span><span class="sxs-lookup"><span data-stu-id="e319f-152">Stores the network site defined in NCS setting.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e319f-153"><a href="lync-server-2013-subnet-table.md">Tabela de sub-rede no Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="e319f-153"><a href="lync-server-2013-subnet-table.md">Subnet table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="e319f-154">Armazena a sub-rede definida na configuração NCS.</span><span class="sxs-lookup"><span data-stu-id="e319f-154">Stores the subnet defined in NCS setting.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e319f-155"><a href="lync-server-2013-monitoredregionlink-table.md">Tabela MonitoredRegionLink no Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="e319f-155"><a href="lync-server-2013-monitoredregionlink-table.md">MonitoredRegionLink table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="e319f-156">Armazena o link de região definido na configuração NCS.</span><span class="sxs-lookup"><span data-stu-id="e319f-156">Stores the region link defined in NCS setting.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e319f-157"><a href="monitoredusersitelink-table.md">Tabela MonitoredUserSiteLink</a></span><span class="sxs-lookup"><span data-stu-id="e319f-157"><a href="monitoredusersitelink-table.md">MonitoredUserSiteLink table</a></span></span></p></td>
<td><p><span data-ttu-id="e319f-158">Armazena os links de site de rede definidos na configuração NCS.</span><span class="sxs-lookup"><span data-stu-id="e319f-158">Stores the network site links defined in NCS setting.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e319f-159"><a href="lync-server-2013-endpointsubnet-table.md">Tabela EndpointSubnet no Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="e319f-159"><a href="lync-server-2013-endpointsubnet-table.md">EndpointSubnet table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="e319f-160">Armazena a sub-rede do ponto de extremidade participando em uma sessão de áudio e vídeo.</span><span class="sxs-lookup"><span data-stu-id="e319f-160">Stores the subnet of the endpoint participating in an audio and video session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e319f-161"><a href="lync-server-2013-server-table.md">Tabela de servidor no Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="e319f-161"><a href="lync-server-2013-server-table.md">Server table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="e319f-162">Armazena o FQDN ou endereço IP do servidor pelo qual a mídia passa.</span><span class="sxs-lookup"><span data-stu-id="e319f-162">Stores the FQDN or IP address of the server the media goes through.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="e319f-163">**Tabelas para dados de métrica**</span><span class="sxs-lookup"><span data-stu-id="e319f-163">**Tables for metrics data**</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e319f-164"><strong>Table</strong></span><span class="sxs-lookup"><span data-stu-id="e319f-164"><strong>Table</strong></span></span></th>
<th><span data-ttu-id="e319f-165"><strong>Descrição</strong></span><span class="sxs-lookup"><span data-stu-id="e319f-165"><strong>Description</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e319f-166"><a href="lync-server-2013-appsharingstream-table.md">Tabela AppSharingStream no Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="e319f-166"><a href="lync-server-2013-appsharingstream-table.md">AppSharingStream table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="e319f-p101">Armazena métricas de Qualidade da Experiência para as transmissões de rede usadas para compartilhamento de aplicativo. Métricas de Qualidade da Experiência para as transmissões de rede usadas para compartilhamento de aplicativo.</span><span class="sxs-lookup"><span data-stu-id="e319f-p101">Stores Quality of Experience metrics for the network streams used for application sharing. Quality of Experience metrics for the network streams used for application sharing.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e319f-169"><a href="lync-server-2013-session-table.md">Tabela de sessão no Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="e319f-169"><a href="lync-server-2013-session-table.md">Session table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="e319f-170">Armazena informações gerais sobre sessões de áudio ou de áudio/vídeo.</span><span class="sxs-lookup"><span data-stu-id="e319f-170">Stores overall information about an audio or audio/video session.</span></span> <span data-ttu-id="e319f-171">Uma sessão é definida como um diálogo SIP de áudio ou vídeo entre dois pontos de extremidade.</span><span class="sxs-lookup"><span data-stu-id="e319f-171">A session is defined as an audio or video SIP dialog between two endpoints.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e319f-172"><a href="lync-server-2013-medialine-table.md">Tabela de mídia no Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="e319f-172"><a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="e319f-p103">Armazena informações sobre cada linha de mídia de uma sessão. Uma linha de mídia é uma coleção de um ou mais fluxos de áudio e vídeo. Geralmente, uma linha única de mídia terá dois fluxos, áudio ou vídeo.</span><span class="sxs-lookup"><span data-stu-id="e319f-p103">Stores information about each media line in a session. A media line is a collection of one or more audio and video streams. Typically, a single media line will have two streams, either audio or video.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e319f-176"><a href="lync-server-2013-audiostream-table.md">Tabela AudioStream no Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="e319f-176"><a href="lync-server-2013-audiostream-table.md">AudioStream table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="e319f-177">Armazena métricas de qualidade de mídia de áudio para cada fluxo de áudio na linha de mídia.</span><span class="sxs-lookup"><span data-stu-id="e319f-177">Stores audio media quality metrics for each audio stream in the media line.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e319f-178"><a href="lync-server-2013-audiosignal-table.md">Tabela AudioSignal no Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="e319f-178"><a href="lync-server-2013-audiosignal-table.md">AudioSignal table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="e319f-179">Armazena métricas de qualidade de mídia de áudio na linha de mídia.</span><span class="sxs-lookup"><span data-stu-id="e319f-179">Stores audio media quality metrics in the media line.</span></span> <span data-ttu-id="e319f-180">Inclui cancelamento do eco acústico (AEC) e métricas de controle automático de ganho (AGC).</span><span class="sxs-lookup"><span data-stu-id="e319f-180">This includes acoustic echo cancellation (AEC) and automatic gain control (AGC) metrics.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e319f-181"><a href="lync-server-2013-videostream-table.md">Tabela VideoStream no Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="e319f-181"><a href="lync-server-2013-videostream-table.md">VideoStream table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="e319f-182">Armazena métricas de qualidade de mídia de vídeo para cada fluxo de áudio na linha de mídia.</span><span class="sxs-lookup"><span data-stu-id="e319f-182">Stores video media quality metrics for each audio stream in the media line.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e319f-183"><a href="lync-server-2013-audioclientevent-table.md">Tabela AudioClientEvent no Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="e319f-183"><a href="lync-server-2013-audioclientevent-table.md">AudioClientEvent table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="e319f-184">Armazena métricas de qualidade de mídia de áudio coletadas do evento do cliente.</span><span class="sxs-lookup"><span data-stu-id="e319f-184">Stores audio media quality metrics collected from the client event.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e319f-185"><a href="lync-server-2013-videoclientevent-table.md">Tabela VideoClientEvent no Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="e319f-185"><a href="lync-server-2013-videoclientevent-table.md">VideoClientEvent table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="e319f-186">Armazena métricas de qualidade de mídia de vídeo coletadas do evento do cliente.</span><span class="sxs-lookup"><span data-stu-id="e319f-186">Stores video media quality metrics collected from the client event.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e319f-187"><strong>Tabela DiagnosticData</strong></span><span class="sxs-lookup"><span data-stu-id="e319f-187"><strong>DiagnosticData Table</strong></span></span></p></td>
<td><p><span data-ttu-id="e319f-188">Armazena dados de diagnóstico apenas para uso interno.</span><span class="sxs-lookup"><span data-stu-id="e319f-188">Stores diagnostic data which is for internal use only.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="e319f-189">**Tabelas para dados de resumo**</span><span class="sxs-lookup"><span data-stu-id="e319f-189">**Tables for summary data**</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e319f-190"><strong>Table</strong></span><span class="sxs-lookup"><span data-stu-id="e319f-190"><strong>Table</strong></span></span></th>
<th><span data-ttu-id="e319f-191"><strong>Descrição</strong></span><span class="sxs-lookup"><span data-stu-id="e319f-191"><strong>Description</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e319f-192"><strong>Tabela ServerSummary</strong></span><span class="sxs-lookup"><span data-stu-id="e319f-192"><strong>ServerSummary Table</strong></span></span></p></td>
<td><p><span data-ttu-id="e319f-193">Armazena dados de resumo para os servidores, esses dados são usados apenas para relatório de Qualidade de Experiência (QoE).</span><span class="sxs-lookup"><span data-stu-id="e319f-193">Stores summary data for the servers, these data is used for Quality of Experience (QoE) reporting only.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e319f-194"><strong>Tabela UserSummary</strong></span><span class="sxs-lookup"><span data-stu-id="e319f-194"><strong>UserSummary Table</strong></span></span></p></td>
<td><p><span data-ttu-id="e319f-195">Armazena dados de resumo para os usuários, esses dados são usados apenas para relatório de QoE.</span><span class="sxs-lookup"><span data-stu-id="e319f-195">Stores summary data for users, these data is used for QoE reporting only.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e319f-196"><strong>Tabela CallTypeSummary</strong></span><span class="sxs-lookup"><span data-stu-id="e319f-196"><strong>CallTypeSummary Table</strong></span></span></p></td>
<td><p><span data-ttu-id="e319f-197">Armazena dados de resumo para tipos de chamadas, esses dados são usados apenas para relatório de QoE.</span><span class="sxs-lookup"><span data-stu-id="e319f-197">Store summary data for call types, these data is used for QoE reporting only.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="e319f-198">**Tabelas para uso interno de Monitoring Server**</span><span class="sxs-lookup"><span data-stu-id="e319f-198">**Tables for Internal Use by Monitoring Server**</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e319f-199"><strong>Table</strong></span><span class="sxs-lookup"><span data-stu-id="e319f-199"><strong>Table</strong></span></span></th>
<th><span data-ttu-id="e319f-200"><strong>Descrição</strong></span><span class="sxs-lookup"><span data-stu-id="e319f-200"><strong>Description</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e319f-201"><strong>DbConfigDateTime</strong></span><span class="sxs-lookup"><span data-stu-id="e319f-201"><strong>DbConfigDateTime</strong></span></span></p></td>
<td><p><span data-ttu-id="e319f-202">Apenas para uso interno.</span><span class="sxs-lookup"><span data-stu-id="e319f-202">For internal use only.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e319f-203"><strong>DbConfigInt</strong></span><span class="sxs-lookup"><span data-stu-id="e319f-203"><strong>DbConfigInt</strong></span></span></p></td>
<td><p><span data-ttu-id="e319f-204">Apenas para uso interno.</span><span class="sxs-lookup"><span data-stu-id="e319f-204">For internal use only.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e319f-205"><strong>Tabela FrontEnd</strong></span><span class="sxs-lookup"><span data-stu-id="e319f-205"><strong>FrontEnd Table</strong></span></span></p></td>
<td><p><span data-ttu-id="e319f-206">Apenas para uso interno.</span><span class="sxs-lookup"><span data-stu-id="e319f-206">For internal use only.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e319f-207"><strong>Tabela Tarefa</strong></span><span class="sxs-lookup"><span data-stu-id="e319f-207"><strong>Task Table</strong></span></span></p></td>
<td><p><span data-ttu-id="e319f-208">Apenas para uso interno.</span><span class="sxs-lookup"><span data-stu-id="e319f-208">For internal use only.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e319f-209"><strong>SummaryTableConfiguration</strong></span><span class="sxs-lookup"><span data-stu-id="e319f-209"><strong>SummaryTableConfiguration</strong></span></span></p></td>
<td><p><span data-ttu-id="e319f-210">Apenas para uso interno.</span><span class="sxs-lookup"><span data-stu-id="e319f-210">For internal use only.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e319f-211"><strong>DbErrorMessage</strong></span><span class="sxs-lookup"><span data-stu-id="e319f-211"><strong>DbErrorMessage</strong></span></span></p></td>
<td><p><span data-ttu-id="e319f-212">Apenas para uso interno.</span><span class="sxs-lookup"><span data-stu-id="e319f-212">For internal use only.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e319f-213"><strong>MetricsThreshold</strong></span><span class="sxs-lookup"><span data-stu-id="e319f-213"><strong>MetricsThreshold</strong></span></span></p></td>
<td><p><span data-ttu-id="e319f-214">Apenas para uso interno.</span><span class="sxs-lookup"><span data-stu-id="e319f-214">For internal use only.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e319f-215"><strong>DaylightSavingYears</strong></span><span class="sxs-lookup"><span data-stu-id="e319f-215"><strong>DaylightSavingYears</strong></span></span></p></td>
<td><p><span data-ttu-id="e319f-216">Apenas para uso interno.</span><span class="sxs-lookup"><span data-stu-id="e319f-216">For internal use only.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e319f-217"><strong>TimeZoneConfiguration</strong></span><span class="sxs-lookup"><span data-stu-id="e319f-217"><strong>TimeZoneConfiguration</strong></span></span></p></td>
<td><p><span data-ttu-id="e319f-218">Apenas para uso interno.</span><span class="sxs-lookup"><span data-stu-id="e319f-218">For internal use only.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e319f-219"><strong>TimeZones</strong></span><span class="sxs-lookup"><span data-stu-id="e319f-219"><strong>TimeZones</strong></span></span></p></td>
<td><p><span data-ttu-id="e319f-220">Somente para uso interno.</span><span class="sxs-lookup"><span data-stu-id="e319f-220">For internal use only.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e319f-221"><strong>Tabela CallSummary</strong></span><span class="sxs-lookup"><span data-stu-id="e319f-221"><strong>CallSummary Table</strong></span></span></p></td>
<td><p><span data-ttu-id="e319f-222">Somente para uso interno.</span><span class="sxs-lookup"><span data-stu-id="e319f-222">For internal use only.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e319f-223"><strong>Tabela DeviceCallSumary</strong></span><span class="sxs-lookup"><span data-stu-id="e319f-223"><strong>DeviceCallSumary Table</strong></span></span></p></td>
<td><p><span data-ttu-id="e319f-224">Somente para uso interno.</span><span class="sxs-lookup"><span data-stu-id="e319f-224">For internal use only.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e319f-225"><strong>Tabela Inquilino</strong></span><span class="sxs-lookup"><span data-stu-id="e319f-225"><strong>Tenant Table</strong></span></span></p></td>
<td><p><span data-ttu-id="e319f-226">Somente para uso interno.</span><span class="sxs-lookup"><span data-stu-id="e319f-226">For internal use only.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e319f-227"><strong>VideoCallSummaryTable</strong></span><span class="sxs-lookup"><span data-stu-id="e319f-227"><strong>VideoCallSummaryTable</strong></span></span></p></td>
<td><p><span data-ttu-id="e319f-228">Somente para uso interno.</span><span class="sxs-lookup"><span data-stu-id="e319f-228">For internal use only.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e319f-229"><strong>ASCallSummaryTable</strong></span><span class="sxs-lookup"><span data-stu-id="e319f-229"><strong>ASCallSummaryTable</strong></span></span></p></td>
<td><p><span data-ttu-id="e319f-230">Somente para uso interno.</span><span class="sxs-lookup"><span data-stu-id="e319f-230">For internal use only.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

