---
title: 'Lync Server 2013: lista de tabelas QoE'
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
ms.openlocfilehash: 29ccbf0340a68a1f03908ebe25b86abfc04d0114
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42186564"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="list-of-qoe-tables-in-lync-server-2013"></a><span data-ttu-id="33041-102">Lista de tabelas de QoE no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="33041-102">List of QoE tables in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="33041-103">_**Última modificação do tópico:** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="33041-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="33041-104">O esquema de banco de dados consiste nas tabelas a seguir.</span><span class="sxs-lookup"><span data-stu-id="33041-104">The database schema consists of the following tables.</span></span>

<span data-ttu-id="33041-105">**Tabelas de suporte**</span><span class="sxs-lookup"><span data-stu-id="33041-105">**Supporting Tables**</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="33041-106"><strong>Table</strong></span><span class="sxs-lookup"><span data-stu-id="33041-106"><strong>Table</strong></span></span></th>
<th><span data-ttu-id="33041-107"><strong>Descrição</strong></span><span class="sxs-lookup"><span data-stu-id="33041-107"><strong>Description</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="33041-108"><a href="lync-server-2013-appsharingmetricsthreshold-table.md">Tabela AppSharingMetricsThreshold no Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="33041-108"><a href="lync-server-2013-appsharingmetricsthreshold-table.md">AppSharingMetricsThreshold table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="33041-109">Armazena valores ótimos e aceitáveis para as métricas de Qualidade da Experiência usadas com compartilhamento de aplicativo.</span><span class="sxs-lookup"><span data-stu-id="33041-109">Stores optimal and acceptable values for the Quality of Experience metrics used with application sharing.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="33041-110"><a href="lync-server-2013-codecdescription-table.md">Tabela CodecDescription no Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="33041-110"><a href="lync-server-2013-codecdescription-table.md">CodecDescription table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="33041-111">Mapeia identificadores exclusivos de codec ao codec correspondente.</span><span class="sxs-lookup"><span data-stu-id="33041-111">Maps unique codec identifiers to their corresponding codec.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="33041-112"><a href="lync-server-2013-ipaddress-table.md">Tabela IPAddress no Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="33041-112"><a href="lync-server-2013-ipaddress-table.md">IPAddress table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="33041-113">Mapeia endereços IP aos identificadores de endereços IP exclusivos usados em outros locais no banco de dados de Qualidade da Experiência.</span><span class="sxs-lookup"><span data-stu-id="33041-113">Maps IP addresses to the unique IP address identifiers used elsewhere in the Quality of Experience database.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="33041-114"><a href="lync-server-2013-networkconnectiondetail-table.md">Tabela NetworkConnectionDetail no Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="33041-114"><a href="lync-server-2013-networkconnectiondetail-table.md">NetworkConnectionDetail table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="33041-115">Mapeia os tipos de conexão de rede aos identificadores de conexão de rede usados em outros locais no banco de dados de Qualidade da Experiência.</span><span class="sxs-lookup"><span data-stu-id="33041-115">Maps network connection types to the network connection identifiers used elsewhere in the Quality of Experience database.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="33041-116"><a href="lync-server-2013-purgesettings-table-qoe.md">Tabela PurgeSettings (QoE) no Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="33041-116"><a href="lync-server-2013-purgesettings-table-qoe.md">PurgeSettings table (QoE) in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="33041-117">Armazena informações que especificam se (e quando) registros de Qualidade da Experiência antigos serão automaticamente deletados do banco de dados de QoE (Qualidade da Experiência).</span><span class="sxs-lookup"><span data-stu-id="33041-117">Stores information that specifies if (and when) outdated Quality of Experience records will automatically be deleted from the QoE database.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="33041-118"><a href="lync-server-2013-traceroute-table.md">Tabela de TraceRoute no Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="33041-118"><a href="lync-server-2013-traceroute-table.md">TraceRoute table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="33041-119">Armazena informaçoes de roteamento para chamadas.</span><span class="sxs-lookup"><span data-stu-id="33041-119">Stores routing information for calls.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="33041-120"><a href="lync-server-2013-useragentdef-table-qoe.md">Tabela UserAgentDef (QoE) no Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="33041-120"><a href="lync-server-2013-useragentdef-table-qoe.md">UserAgentDef table (QoE) in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="33041-121">Mapeia os identificadores de agente do usuário aos nomes descritivos dos agentes.</span><span class="sxs-lookup"><span data-stu-id="33041-121">Maps user agent identifiers to the agent’s descriptive names.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="33041-122"><a href="lync-server-2013-videometricsthreshold-table.md">Tabela VideoMetricsThreshold no Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="33041-122"><a href="lync-server-2013-videometricsthreshold-table.md">VideoMetricsThreshold table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="33041-123">Armazena valores ótimos e aceitáveis para as métricas de Qualidade da Experiência usadas com chamadas de vídeo.</span><span class="sxs-lookup"><span data-stu-id="33041-123">Stores optimal and acceptable values for the Quality of Experience metrics used with video calls.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="33041-124"><a href="lync-server-2013-useragent-table.md">Tabela UserAgent no Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="33041-124"><a href="lync-server-2013-useragent-table.md">UserAgent table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="33041-125">Armazena as cadeias de Agente de Usuário (UA) do Protocolo de Iniciação de Sessão (SIP) e tipos de UA usados em sessões de áudio e vídeo.</span><span class="sxs-lookup"><span data-stu-id="33041-125">Stores Session Initiation Protocol (SIP) User Agent (UA) strings and UA types used in audio and video sessions.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="33041-126"><a href="lync-server-2013-user-table.md">Tabela de usuário no Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="33041-126"><a href="lync-server-2013-user-table.md">User table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="33041-127">Armazena URIs de usuário, de conferência, e de telefone usados em sessões de áudio e vídeo.</span><span class="sxs-lookup"><span data-stu-id="33041-127">Stores user, conference, and phone URIs used in audio and video sessions.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="33041-128"><a href="lync-server-2013-endpoint-table.md">Tabela de pontos de extremidade no Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="33041-128"><a href="lync-server-2013-endpoint-table.md">Endpoint table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="33041-129">Armazena nomes de computador FQDN de pontos de extremidade que participam de sessões de áudio e vídeo.</span><span class="sxs-lookup"><span data-stu-id="33041-129">Stores FQDN computer names of endpoints participating in audio and video sessions.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="33041-130"><a href="lync-server-2013-pool-table.md">Tabela de pool no Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="33041-130"><a href="lync-server-2013-pool-table.md">Pool table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="33041-131">Armazena os nomes de pools às quais os dados de métrica pertencem.</span><span class="sxs-lookup"><span data-stu-id="33041-131">Stores the names of pools to which metrics data belongs.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="33041-132"><a href="lync-server-2013-device-table.md">Tabela de dispositivos no Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="33041-132"><a href="lync-server-2013-device-table.md">Device table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="33041-133">Armazena os dispositivos de captura e de renderização que são usados em chamadas de áudio/vídeo.</span><span class="sxs-lookup"><span data-stu-id="33041-133">Stores capture devices and render devices which are used in an audio/video calls.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="33041-134"><a href="lync-server-2013-devicedriver-table.md">Tabela DeviceDriver no Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="33041-134"><a href="lync-server-2013-devicedriver-table.md">DeviceDriver table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="33041-135">Armazena o driver do dispositivo de captura e de renderização que são usados em chamadas de áudio/vídeo.</span><span class="sxs-lookup"><span data-stu-id="33041-135">Stores driver for the capture device and the render device which are used in audio/video calls.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="33041-136"><a href="lync-server-2013-conference-table.md">Tabela de conferência no Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="33041-136"><a href="lync-server-2013-conference-table.md">Conference table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="33041-137">Armazena os URIs da conferência para cenários de conferência ou DialogID para outros cenários.</span><span class="sxs-lookup"><span data-stu-id="33041-137">Stores Conference URIs for conference scenarios or DialogID for other scenarios.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="33041-138"><a href="lync-server-2013-sessioncorrelation-table.md">Tabela SessionCorrelation no Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="33041-138"><a href="lync-server-2013-sessioncorrelation-table.md">SessionCorrelation table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="33041-139">Armazena CorrelationID para chamadas PSTN.</span><span class="sxs-lookup"><span data-stu-id="33041-139">Stores CorrelationID for PSTN calls.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="33041-140"><a href="lync-server-2013-payloaddescription-table.md">Tabela PayloadDescription no Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="33041-140"><a href="lync-server-2013-payloaddescription-table.md">PayloadDescription table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="33041-141">Armazena o Codec usado em chamadas de áudio/vídeo.</span><span class="sxs-lookup"><span data-stu-id="33041-141">Stores the Codec used in audio/video calls.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="33041-142"><a href="lync-server-2013-appliedbandwidthsource-table.md">Tabela AppliedBandwidthSource no Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="33041-142"><a href="lync-server-2013-appliedbandwidthsource-table.md">AppliedBandwidthSource table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="33041-143">Armazena a origem da largura de banda usada em chamadas de áudio/vídeo.</span><span class="sxs-lookup"><span data-stu-id="33041-143">Stores the bandwidth source used in audio/video calls.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="33041-144"><a href="lync-server-2013-macaddress-table.md">Tabela MacAddress no Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="33041-144"><a href="lync-server-2013-macaddress-table.md">MacAddress table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="33041-145">Armazena o endereço MAC dos pontos de extremidade participantes de sessões de áudio e vídeo.</span><span class="sxs-lookup"><span data-stu-id="33041-145">Stores the MAC address of the endpoints participating in audio and video sessions.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="33041-146"><a href="lync-server-2013-dialog-table.md">Tabela Dialog no Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="33041-146"><a href="lync-server-2013-dialog-table.md">Dialog table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="33041-147">Armazena a ID de Diálogo de sessões de áudio e vídeo.</span><span class="sxs-lookup"><span data-stu-id="33041-147">Stores the Dialog ID of audio and video sessions.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="33041-148"><a href="lync-server-2013-region-table.md">Tabela Region no Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="33041-148"><a href="lync-server-2013-region-table.md">Region table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="33041-149">Armazena a região de rede definida na configuração NCS.</span><span class="sxs-lookup"><span data-stu-id="33041-149">Stores the network region defined in NCS setting.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="33041-150"><a href="lync-server-2013-usersite-table.md">Tabela usersite no Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="33041-150"><a href="lync-server-2013-usersite-table.md">UserSite table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="33041-151">Armazena o site de rede definido na configuração NCS.</span><span class="sxs-lookup"><span data-stu-id="33041-151">Stores the network site defined in NCS setting.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="33041-152"><a href="lync-server-2013-subnet-table.md">Tabela de sub-rede no Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="33041-152"><a href="lync-server-2013-subnet-table.md">Subnet table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="33041-153">Armazena a sub-rede definida na configuração NCS.</span><span class="sxs-lookup"><span data-stu-id="33041-153">Stores the subnet defined in NCS setting.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="33041-154"><a href="lync-server-2013-monitoredregionlink-table.md">Tabela MonitoredRegionLink no Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="33041-154"><a href="lync-server-2013-monitoredregionlink-table.md">MonitoredRegionLink table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="33041-155">Armazena o link de região definido na configuração NCS.</span><span class="sxs-lookup"><span data-stu-id="33041-155">Stores the region link defined in NCS setting.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="33041-156"><a href="monitoredusersitelink-table.md">Tabela MonitoredUserSiteLink</a></span><span class="sxs-lookup"><span data-stu-id="33041-156"><a href="monitoredusersitelink-table.md">MonitoredUserSiteLink table</a></span></span></p></td>
<td><p><span data-ttu-id="33041-157">Armazena os links de site de rede definidos na configuração NCS.</span><span class="sxs-lookup"><span data-stu-id="33041-157">Stores the network site links defined in NCS setting.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="33041-158"><a href="lync-server-2013-endpointsubnet-table.md">Tabela EndpointSubnet no Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="33041-158"><a href="lync-server-2013-endpointsubnet-table.md">EndpointSubnet table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="33041-159">Armazena a sub-rede do ponto de extremidade participando em uma sessão de áudio e vídeo.</span><span class="sxs-lookup"><span data-stu-id="33041-159">Stores the subnet of the endpoint participating in an audio and video session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="33041-160"><a href="lync-server-2013-server-table.md">Tabela de servidor no Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="33041-160"><a href="lync-server-2013-server-table.md">Server table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="33041-161">Armazena o FQDN ou endereço IP do servidor pelo qual a mídia passa.</span><span class="sxs-lookup"><span data-stu-id="33041-161">Stores the FQDN or IP address of the server the media goes through.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="33041-162">**Tabelas para dados de métrica**</span><span class="sxs-lookup"><span data-stu-id="33041-162">**Tables for metrics data**</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="33041-163"><strong>Table</strong></span><span class="sxs-lookup"><span data-stu-id="33041-163"><strong>Table</strong></span></span></th>
<th><span data-ttu-id="33041-164"><strong>Descrição</strong></span><span class="sxs-lookup"><span data-stu-id="33041-164"><strong>Description</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="33041-165"><a href="lync-server-2013-appsharingstream-table.md">Tabela AppSharingStream no Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="33041-165"><a href="lync-server-2013-appsharingstream-table.md">AppSharingStream table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="33041-p101">Armazena métricas de Qualidade da Experiência para as transmissões de rede usadas para compartilhamento de aplicativo. Métricas de Qualidade da Experiência para as transmissões de rede usadas para compartilhamento de aplicativo.</span><span class="sxs-lookup"><span data-stu-id="33041-p101">Stores Quality of Experience metrics for the network streams used for application sharing. Quality of Experience metrics for the network streams used for application sharing.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="33041-168"><a href="lync-server-2013-session-table.md">Tabela de sessão no Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="33041-168"><a href="lync-server-2013-session-table.md">Session table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="33041-169">Armazena informações gerais sobre sessões de áudio ou de áudio/vídeo.</span><span class="sxs-lookup"><span data-stu-id="33041-169">Stores overall information about an audio or audio/video session.</span></span> <span data-ttu-id="33041-170">Uma sessão é definida como um diálogo SIP de áudio ou vídeo entre dois pontos de extremidade.</span><span class="sxs-lookup"><span data-stu-id="33041-170">A session is defined as an audio or video SIP dialog between two endpoints.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="33041-171"><a href="lync-server-2013-medialine-table.md">Tabela de mídia no Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="33041-171"><a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="33041-p103">Armazena informações sobre cada linha de mídia de uma sessão. Uma linha de mídia é uma coleção de um ou mais fluxos de áudio e vídeo. Geralmente, uma linha única de mídia terá dois fluxos, áudio ou vídeo.</span><span class="sxs-lookup"><span data-stu-id="33041-p103">Stores information about each media line in a session. A media line is a collection of one or more audio and video streams. Typically, a single media line will have two streams, either audio or video.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="33041-175"><a href="lync-server-2013-audiostream-table.md">Tabela AudioStream no Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="33041-175"><a href="lync-server-2013-audiostream-table.md">AudioStream table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="33041-176">Armazena métricas de qualidade de mídia de áudio para cada fluxo de áudio na linha de mídia.</span><span class="sxs-lookup"><span data-stu-id="33041-176">Stores audio media quality metrics for each audio stream in the media line.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="33041-177"><a href="lync-server-2013-audiosignal-table.md">Tabela AudioSignal no Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="33041-177"><a href="lync-server-2013-audiosignal-table.md">AudioSignal table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="33041-178">Armazena métricas de qualidade de mídia de áudio na linha de mídia.</span><span class="sxs-lookup"><span data-stu-id="33041-178">Stores audio media quality metrics in the media line.</span></span> <span data-ttu-id="33041-179">Inclui cancelamento do eco acústico (AEC) e métricas de controle automático de ganho (AGC).</span><span class="sxs-lookup"><span data-stu-id="33041-179">This includes acoustic echo cancellation (AEC) and automatic gain control (AGC) metrics.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="33041-180"><a href="lync-server-2013-videostream-table.md">Tabela VideoStream no Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="33041-180"><a href="lync-server-2013-videostream-table.md">VideoStream table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="33041-181">Armazena métricas de qualidade de mídia de vídeo para cada fluxo de áudio na linha de mídia.</span><span class="sxs-lookup"><span data-stu-id="33041-181">Stores video media quality metrics for each audio stream in the media line.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="33041-182"><a href="lync-server-2013-audioclientevent-table.md">Tabela AudioClientEvent no Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="33041-182"><a href="lync-server-2013-audioclientevent-table.md">AudioClientEvent table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="33041-183">Armazena métricas de qualidade de mídia de áudio coletadas do evento do cliente.</span><span class="sxs-lookup"><span data-stu-id="33041-183">Stores audio media quality metrics collected from the client event.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="33041-184"><a href="lync-server-2013-videoclientevent-table.md">Tabela VideoClientEvent no Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="33041-184"><a href="lync-server-2013-videoclientevent-table.md">VideoClientEvent table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="33041-185">Armazena métricas de qualidade de mídia de vídeo coletadas do evento do cliente.</span><span class="sxs-lookup"><span data-stu-id="33041-185">Stores video media quality metrics collected from the client event.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="33041-186"><strong>Tabela DiagnosticData</strong></span><span class="sxs-lookup"><span data-stu-id="33041-186"><strong>DiagnosticData Table</strong></span></span></p></td>
<td><p><span data-ttu-id="33041-187">Armazena dados de diagnóstico apenas para uso interno.</span><span class="sxs-lookup"><span data-stu-id="33041-187">Stores diagnostic data which is for internal use only.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="33041-188">**Tabelas para dados de resumo**</span><span class="sxs-lookup"><span data-stu-id="33041-188">**Tables for summary data**</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="33041-189"><strong>Table</strong></span><span class="sxs-lookup"><span data-stu-id="33041-189"><strong>Table</strong></span></span></th>
<th><span data-ttu-id="33041-190"><strong>Descrição</strong></span><span class="sxs-lookup"><span data-stu-id="33041-190"><strong>Description</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="33041-191"><strong>Tabela ServerSummary</strong></span><span class="sxs-lookup"><span data-stu-id="33041-191"><strong>ServerSummary Table</strong></span></span></p></td>
<td><p><span data-ttu-id="33041-192">Armazena dados de resumo para os servidores, esses dados são usados apenas para relatório de Qualidade de Experiência (QoE).</span><span class="sxs-lookup"><span data-stu-id="33041-192">Stores summary data for the servers, these data is used for Quality of Experience (QoE) reporting only.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="33041-193"><strong>Tabela UserSummary</strong></span><span class="sxs-lookup"><span data-stu-id="33041-193"><strong>UserSummary Table</strong></span></span></p></td>
<td><p><span data-ttu-id="33041-194">Armazena dados de resumo para os usuários, esses dados são usados apenas para relatório de QoE.</span><span class="sxs-lookup"><span data-stu-id="33041-194">Stores summary data for users, these data is used for QoE reporting only.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="33041-195"><strong>Tabela CallTypeSummary</strong></span><span class="sxs-lookup"><span data-stu-id="33041-195"><strong>CallTypeSummary Table</strong></span></span></p></td>
<td><p><span data-ttu-id="33041-196">Armazena dados de resumo para tipos de chamadas, esses dados são usados apenas para relatório de QoE.</span><span class="sxs-lookup"><span data-stu-id="33041-196">Store summary data for call types, these data is used for QoE reporting only.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="33041-197">**Tabelas para uso interno de Monitoring Server**</span><span class="sxs-lookup"><span data-stu-id="33041-197">**Tables for Internal Use by Monitoring Server**</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="33041-198"><strong>Table</strong></span><span class="sxs-lookup"><span data-stu-id="33041-198"><strong>Table</strong></span></span></th>
<th><span data-ttu-id="33041-199"><strong>Descrição</strong></span><span class="sxs-lookup"><span data-stu-id="33041-199"><strong>Description</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="33041-200"><strong>DbConfigDateTime</strong></span><span class="sxs-lookup"><span data-stu-id="33041-200"><strong>DbConfigDateTime</strong></span></span></p></td>
<td><p><span data-ttu-id="33041-201">Apenas para uso interno.</span><span class="sxs-lookup"><span data-stu-id="33041-201">For internal use only.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="33041-202"><strong>DbConfigInt</strong></span><span class="sxs-lookup"><span data-stu-id="33041-202"><strong>DbConfigInt</strong></span></span></p></td>
<td><p><span data-ttu-id="33041-203">Apenas para uso interno.</span><span class="sxs-lookup"><span data-stu-id="33041-203">For internal use only.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="33041-204"><strong>Tabela FrontEnd</strong></span><span class="sxs-lookup"><span data-stu-id="33041-204"><strong>FrontEnd Table</strong></span></span></p></td>
<td><p><span data-ttu-id="33041-205">Apenas para uso interno.</span><span class="sxs-lookup"><span data-stu-id="33041-205">For internal use only.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="33041-206"><strong>Tabela Tarefa</strong></span><span class="sxs-lookup"><span data-stu-id="33041-206"><strong>Task Table</strong></span></span></p></td>
<td><p><span data-ttu-id="33041-207">Apenas para uso interno.</span><span class="sxs-lookup"><span data-stu-id="33041-207">For internal use only.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="33041-208"><strong>SummaryTableConfiguration</strong></span><span class="sxs-lookup"><span data-stu-id="33041-208"><strong>SummaryTableConfiguration</strong></span></span></p></td>
<td><p><span data-ttu-id="33041-209">Apenas para uso interno.</span><span class="sxs-lookup"><span data-stu-id="33041-209">For internal use only.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="33041-210"><strong>DbErrorMessage</strong></span><span class="sxs-lookup"><span data-stu-id="33041-210"><strong>DbErrorMessage</strong></span></span></p></td>
<td><p><span data-ttu-id="33041-211">Apenas para uso interno.</span><span class="sxs-lookup"><span data-stu-id="33041-211">For internal use only.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="33041-212"><strong>MetricsThreshold</strong></span><span class="sxs-lookup"><span data-stu-id="33041-212"><strong>MetricsThreshold</strong></span></span></p></td>
<td><p><span data-ttu-id="33041-213">Apenas para uso interno.</span><span class="sxs-lookup"><span data-stu-id="33041-213">For internal use only.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="33041-214"><strong>DaylightSavingYears</strong></span><span class="sxs-lookup"><span data-stu-id="33041-214"><strong>DaylightSavingYears</strong></span></span></p></td>
<td><p><span data-ttu-id="33041-215">Apenas para uso interno.</span><span class="sxs-lookup"><span data-stu-id="33041-215">For internal use only.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="33041-216"><strong>TimeZoneConfiguration</strong></span><span class="sxs-lookup"><span data-stu-id="33041-216"><strong>TimeZoneConfiguration</strong></span></span></p></td>
<td><p><span data-ttu-id="33041-217">Apenas para uso interno.</span><span class="sxs-lookup"><span data-stu-id="33041-217">For internal use only.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="33041-218"><strong>TimeZones</strong></span><span class="sxs-lookup"><span data-stu-id="33041-218"><strong>TimeZones</strong></span></span></p></td>
<td><p><span data-ttu-id="33041-219">For internal use only.</span><span class="sxs-lookup"><span data-stu-id="33041-219">For internal use only.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="33041-220"><strong>Tabela CallSummary</strong></span><span class="sxs-lookup"><span data-stu-id="33041-220"><strong>CallSummary Table</strong></span></span></p></td>
<td><p><span data-ttu-id="33041-221">Apenas para uso interno.</span><span class="sxs-lookup"><span data-stu-id="33041-221">For internal use only.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="33041-222"><strong>Tabela DeviceCallSumary</strong></span><span class="sxs-lookup"><span data-stu-id="33041-222"><strong>DeviceCallSumary Table</strong></span></span></p></td>
<td><p><span data-ttu-id="33041-223">Apenas para uso interno.</span><span class="sxs-lookup"><span data-stu-id="33041-223">For internal use only.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="33041-224"><strong>Tabela Inquilino</strong></span><span class="sxs-lookup"><span data-stu-id="33041-224"><strong>Tenant Table</strong></span></span></p></td>
<td><p><span data-ttu-id="33041-225">Apenas para uso interno.</span><span class="sxs-lookup"><span data-stu-id="33041-225">For internal use only.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="33041-226"><strong>VideoCallSummaryTable</strong></span><span class="sxs-lookup"><span data-stu-id="33041-226"><strong>VideoCallSummaryTable</strong></span></span></p></td>
<td><p><span data-ttu-id="33041-227">Somente para uso interno.</span><span class="sxs-lookup"><span data-stu-id="33041-227">For internal use only.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="33041-228"><strong>ASCallSummaryTable</strong></span><span class="sxs-lookup"><span data-stu-id="33041-228"><strong>ASCallSummaryTable</strong></span></span></p></td>
<td><p><span data-ttu-id="33041-229">Apenas para uso interno.</span><span class="sxs-lookup"><span data-stu-id="33041-229">For internal use only.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

