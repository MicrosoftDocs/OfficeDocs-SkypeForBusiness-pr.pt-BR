---
title: 'Lync Server 2013: Lista de tabelas QoE'
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
ms.openlocfilehash: c3161415b65c8e85ace7968ab29d86c0d0c5387a
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41765389"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="list-of-qoe-tables-in-lync-server-2013"></a><span data-ttu-id="e9638-102">Lista de tabelas QoE no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e9638-102">List of QoE tables in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e9638-103">_**Tópico da última modificação:** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="e9638-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="e9638-104">O esquema de banco de dados consiste nas tabelas a seguir.</span><span class="sxs-lookup"><span data-stu-id="e9638-104">The database schema consists of the following tables.</span></span>

<span data-ttu-id="e9638-105">**Tabelas de suporte**</span><span class="sxs-lookup"><span data-stu-id="e9638-105">**Supporting Tables**</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e9638-106"><strong>Tabela</strong></span><span class="sxs-lookup"><span data-stu-id="e9638-106"><strong>Table</strong></span></span></th>
<th><span data-ttu-id="e9638-107"><strong>Descrição</strong></span><span class="sxs-lookup"><span data-stu-id="e9638-107"><strong>Description</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e9638-108"><a href="lync-server-2013-appsharingmetricsthreshold-table.md">Tabela AppSharingMetricsThreshold no Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="e9638-108"><a href="lync-server-2013-appsharingmetricsthreshold-table.md">AppSharingMetricsThreshold table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="e9638-109">Armazena valores satisfatórios e satisfatórios para as métricas de qualidade da experiência usadas com o compartilhamento de aplicativos.</span><span class="sxs-lookup"><span data-stu-id="e9638-109">Stores optimal and acceptable values for the Quality of Experience metrics used with application sharing.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e9638-110"><a href="lync-server-2013-codecdescription-table.md">Tabela CodecDescription no Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="e9638-110"><a href="lync-server-2013-codecdescription-table.md">CodecDescription table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="e9638-111">Mapeia identificadores de codec exclusivos para o codec correspondente.</span><span class="sxs-lookup"><span data-stu-id="e9638-111">Maps unique codec identifiers to their corresponding codec.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e9638-112"><a href="lync-server-2013-ipaddress-table.md">Tabela IPAddress no Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="e9638-112"><a href="lync-server-2013-ipaddress-table.md">IPAddress table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="e9638-113">Mapeia endereços IP para os identificadores de endereços IP exclusivos usados em outro lugar no banco de dados de qualidade da experiência.</span><span class="sxs-lookup"><span data-stu-id="e9638-113">Maps IP addresses to the unique IP address identifiers used elsewhere in the Quality of Experience database.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e9638-114"><a href="lync-server-2013-networkconnectiondetail-table.md">Tabela NetworkConnectionDetail no Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="e9638-114"><a href="lync-server-2013-networkconnectiondetail-table.md">NetworkConnectionDetail table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="e9638-115">Mapeia tipos de conexão de rede para os identificadores de conexão de rede usados em outro lugar no banco de dados de qualidade da experiência.</span><span class="sxs-lookup"><span data-stu-id="e9638-115">Maps network connection types to the network connection identifiers used elsewhere in the Quality of Experience database.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e9638-116"><a href="lync-server-2013-purgesettings-table-qoe.md">Tabela PurgeSettings (QoE) no Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="e9638-116"><a href="lync-server-2013-purgesettings-table-qoe.md">PurgeSettings table (QoE) in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="e9638-117">Armazena informações que especificam se (e quando) registros de qualidade de experiência desatualizados serão excluídos automaticamente do banco de dados de QoE.</span><span class="sxs-lookup"><span data-stu-id="e9638-117">Stores information that specifies if (and when) outdated Quality of Experience records will automatically be deleted from the QoE database.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e9638-118"><a href="lync-server-2013-traceroute-table.md">Tabela TraceRoute no Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="e9638-118"><a href="lync-server-2013-traceroute-table.md">TraceRoute table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="e9638-119">Armazena informações de roteamento para chamadas.</span><span class="sxs-lookup"><span data-stu-id="e9638-119">Stores routing information for calls.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e9638-120"><a href="lync-server-2013-useragentdef-table-qoe.md">Tabela UserAgentDef (QoE) no Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="e9638-120"><a href="lync-server-2013-useragentdef-table-qoe.md">UserAgentDef table (QoE) in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="e9638-121">Mapeia identificadores de agente de usuário para os nomes descritivos do agente.</span><span class="sxs-lookup"><span data-stu-id="e9638-121">Maps user agent identifiers to the agent’s descriptive names.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e9638-122"><a href="lync-server-2013-videometricsthreshold-table.md">Tabela VideoMetricsThreshold no Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="e9638-122"><a href="lync-server-2013-videometricsthreshold-table.md">VideoMetricsThreshold table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="e9638-123">Armazena valores satisfatórios e satisfatórios para as métricas de qualidade da experiência usadas com chamadas com vídeo.</span><span class="sxs-lookup"><span data-stu-id="e9638-123">Stores optimal and acceptable values for the Quality of Experience metrics used with video calls.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e9638-124"><a href="lync-server-2013-useragent-table.md">Tabela UserAgent no Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="e9638-124"><a href="lync-server-2013-useragent-table.md">UserAgent table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="e9638-125">Armazena cadeias de caracteres de UA (protocolo de início de sessão) do SIP e tipos de UA usados em sessões de áudio e vídeo.</span><span class="sxs-lookup"><span data-stu-id="e9638-125">Stores Session Initiation Protocol (SIP) User Agent (UA) strings and UA types used in audio and video sessions.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e9638-126"><a href="lync-server-2013-user-table.md">Tabela User no Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="e9638-126"><a href="lync-server-2013-user-table.md">User table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="e9638-127">Armazena URIs de usuário, conferência e telefone usados em sessões de áudio e vídeo.</span><span class="sxs-lookup"><span data-stu-id="e9638-127">Stores user, conference, and phone URIs used in audio and video sessions.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e9638-128"><a href="lync-server-2013-endpoint-table.md">Tabela Endpoint no Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="e9638-128"><a href="lync-server-2013-endpoint-table.md">Endpoint table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="e9638-129">Armazena nomes de computador FQDN de pontos de extremidade que participam de sessões de áudio e vídeo.</span><span class="sxs-lookup"><span data-stu-id="e9638-129">Stores FQDN computer names of endpoints participating in audio and video sessions.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e9638-130"><a href="lync-server-2013-pool-table.md">Tabela Pool no Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="e9638-130"><a href="lync-server-2013-pool-table.md">Pool table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="e9638-131">Armazena os nomes dos pools aos quais os dados de métricas pertencem.</span><span class="sxs-lookup"><span data-stu-id="e9638-131">Stores the names of pools to which metrics data belongs.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e9638-132"><a href="lync-server-2013-device-table.md">Tabela Device no Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="e9638-132"><a href="lync-server-2013-device-table.md">Device table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="e9638-133">Armazena dispositivos de captura e renderiza dispositivos que são usados em chamadas de áudio/vídeo.</span><span class="sxs-lookup"><span data-stu-id="e9638-133">Stores capture devices and render devices which are used in an audio/video calls.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e9638-134"><a href="lync-server-2013-devicedriver-table.md">Tabela DeviceDriver no Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="e9638-134"><a href="lync-server-2013-devicedriver-table.md">DeviceDriver table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="e9638-135">Armazena o driver para o dispositivo de captura e o dispositivo de renderização que são usados em chamadas de áudio/vídeo.</span><span class="sxs-lookup"><span data-stu-id="e9638-135">Stores driver for the capture device and the render device which are used in audio/video calls.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e9638-136"><a href="lync-server-2013-conference-table.md">Tabela Conference no Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="e9638-136"><a href="lync-server-2013-conference-table.md">Conference table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="e9638-137">Armazena URIs de conferência para cenários de conferência ou caixa de diálogo para outros cenários.</span><span class="sxs-lookup"><span data-stu-id="e9638-137">Stores Conference URIs for conference scenarios or DialogID for other scenarios.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e9638-138"><a href="lync-server-2013-sessioncorrelation-table.md">Tabela SessionCorrelation no Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="e9638-138"><a href="lync-server-2013-sessioncorrelation-table.md">SessionCorrelation table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="e9638-139">Armazena CorrelationId para chamadas PSTN.</span><span class="sxs-lookup"><span data-stu-id="e9638-139">Stores CorrelationID for PSTN calls.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e9638-140"><a href="lync-server-2013-payloaddescription-table.md">Tabela PayloadDescription no Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="e9638-140"><a href="lync-server-2013-payloaddescription-table.md">PayloadDescription table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="e9638-141">Armazena o codec usado em chamadas de áudio/vídeo.</span><span class="sxs-lookup"><span data-stu-id="e9638-141">Stores the Codec used in audio/video calls.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e9638-142"><a href="lync-server-2013-appliedbandwidthsource-table.md">Tabela AppliedBandwidthSource no Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="e9638-142"><a href="lync-server-2013-appliedbandwidthsource-table.md">AppliedBandwidthSource table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="e9638-143">Armazena a fonte de largura de banda usada em chamadas de áudio/vídeo.</span><span class="sxs-lookup"><span data-stu-id="e9638-143">Stores the bandwidth source used in audio/video calls.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e9638-144"><a href="lync-server-2013-macaddress-table.md">Tabela MacAddress no Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="e9638-144"><a href="lync-server-2013-macaddress-table.md">MacAddress table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="e9638-145">Armazena o endereço MAC dos pontos de extremidade que participam de sessões de áudio e vídeo.</span><span class="sxs-lookup"><span data-stu-id="e9638-145">Stores the MAC address of the endpoints participating in audio and video sessions.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e9638-146"><a href="lync-server-2013-dialog-table.md">Tabela Dialog no Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="e9638-146"><a href="lync-server-2013-dialog-table.md">Dialog table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="e9638-147">Armazena a ID da caixa de diálogo de sessões de áudio e vídeo.</span><span class="sxs-lookup"><span data-stu-id="e9638-147">Stores the Dialog ID of audio and video sessions.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e9638-148"><a href="lync-server-2013-region-table.md">Tabela de regiões no Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="e9638-148"><a href="lync-server-2013-region-table.md">Region table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="e9638-149">Armazena a região de rede definida na configuração NCS.</span><span class="sxs-lookup"><span data-stu-id="e9638-149">Stores the network region defined in NCS setting.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e9638-150"><a href="lync-server-2013-usersite-table.md">Tabela UserSite no Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="e9638-150"><a href="lync-server-2013-usersite-table.md">UserSite table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="e9638-151">Armazena o site de rede definido na configuração NCS.</span><span class="sxs-lookup"><span data-stu-id="e9638-151">Stores the network site defined in NCS setting.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e9638-152"><a href="lync-server-2013-subnet-table.md">Tabela Subnet no Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="e9638-152"><a href="lync-server-2013-subnet-table.md">Subnet table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="e9638-153">Armazena a sub-rede definida na configuração NCS.</span><span class="sxs-lookup"><span data-stu-id="e9638-153">Stores the subnet defined in NCS setting.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e9638-154"><a href="lync-server-2013-monitoredregionlink-table.md">Tabela MonitoredRegionLink no Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="e9638-154"><a href="lync-server-2013-monitoredregionlink-table.md">MonitoredRegionLink table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="e9638-155">Armazena o link de região definido na configuração NCS.</span><span class="sxs-lookup"><span data-stu-id="e9638-155">Stores the region link defined in NCS setting.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e9638-156"><a href="monitoredusersitelink-table.md">Tabela MonitoredUserSiteLink</a></span><span class="sxs-lookup"><span data-stu-id="e9638-156"><a href="monitoredusersitelink-table.md">MonitoredUserSiteLink table</a></span></span></p></td>
<td><p><span data-ttu-id="e9638-157">Armazena os links de sites de rede definidos na configuração NCS.</span><span class="sxs-lookup"><span data-stu-id="e9638-157">Stores the network site links defined in NCS setting.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e9638-158"><a href="lync-server-2013-endpointsubnet-table.md">Tabela EndpointSubnet no Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="e9638-158"><a href="lync-server-2013-endpointsubnet-table.md">EndpointSubnet table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="e9638-159">Armazena a sub-rede do ponto de extremidade que participa de uma sessão de áudio e vídeo.</span><span class="sxs-lookup"><span data-stu-id="e9638-159">Stores the subnet of the endpoint participating in an audio and video session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e9638-160"><a href="lync-server-2013-server-table.md">Tabela Server no Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="e9638-160"><a href="lync-server-2013-server-table.md">Server table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="e9638-161">Armazena o FQDN ou endereço IP do servidor ao qual a mídia vai.</span><span class="sxs-lookup"><span data-stu-id="e9638-161">Stores the FQDN or IP address of the server the media goes through.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="e9638-162">**Tabelas para dados de métricas**</span><span class="sxs-lookup"><span data-stu-id="e9638-162">**Tables for metrics data**</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e9638-163"><strong>Tabela</strong></span><span class="sxs-lookup"><span data-stu-id="e9638-163"><strong>Table</strong></span></span></th>
<th><span data-ttu-id="e9638-164"><strong>Descrição</strong></span><span class="sxs-lookup"><span data-stu-id="e9638-164"><strong>Description</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e9638-165"><a href="lync-server-2013-appsharingstream-table.md">Tabela AppSharingStream no Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="e9638-165"><a href="lync-server-2013-appsharingstream-table.md">AppSharingStream table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="e9638-166">Armazena métricas de qualidade de experiência para os fluxos de rede usados para compartilhamento de aplicativos.</span><span class="sxs-lookup"><span data-stu-id="e9638-166">Stores Quality of Experience metrics for the network streams used for application sharing.</span></span> <span data-ttu-id="e9638-167">Métricas de qualidade de experiência para os fluxos de rede usados para compartilhamento de aplicativos.</span><span class="sxs-lookup"><span data-stu-id="e9638-167">Quality of Experience metrics for the network streams used for application sharing.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e9638-168"><a href="lync-server-2013-session-table.md">Tabela Session no Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="e9638-168"><a href="lync-server-2013-session-table.md">Session table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="e9638-169">Armazena informações gerais sobre uma sessão de áudio ou de áudio/vídeo.</span><span class="sxs-lookup"><span data-stu-id="e9638-169">Stores overall information about an audio or audio/video session.</span></span> <span data-ttu-id="e9638-170">Uma sessão é definida como uma caixa de diálogo de áudio ou vídeo SIP entre dois pontos de extremidade.</span><span class="sxs-lookup"><span data-stu-id="e9638-170">A session is defined as an audio or video SIP dialog between two endpoints.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e9638-171"><a href="lync-server-2013-medialine-table.md">Tabela MediaLine no Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="e9638-171"><a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="e9638-172">Armazena informações sobre cada linha de mídia em uma sessão.</span><span class="sxs-lookup"><span data-stu-id="e9638-172">Stores information about each media line in a session.</span></span> <span data-ttu-id="e9638-173">Uma linha de mídia é uma coleção de um ou mais fluxos de áudio e vídeo.</span><span class="sxs-lookup"><span data-stu-id="e9638-173">A media line is a collection of one or more audio and video streams.</span></span> <span data-ttu-id="e9638-174">Geralmente, uma única linha de mídia terá dois fluxos, áudio ou vídeo.</span><span class="sxs-lookup"><span data-stu-id="e9638-174">Typically, a single media line will have two streams, either audio or video.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e9638-175"><a href="lync-server-2013-audiostream-table.md">Tabela AudioStream no Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="e9638-175"><a href="lync-server-2013-audiostream-table.md">AudioStream table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="e9638-176">Armazena métricas de qualidade de mídia de áudio para cada fluxo de áudio na linha de mídia.</span><span class="sxs-lookup"><span data-stu-id="e9638-176">Stores audio media quality metrics for each audio stream in the media line.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e9638-177"><a href="lync-server-2013-audiosignal-table.md">Tabela AudioSignal no Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="e9638-177"><a href="lync-server-2013-audiosignal-table.md">AudioSignal table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="e9638-178">Armazena métricas de qualidade de mídia de áudio na linha de mídia.</span><span class="sxs-lookup"><span data-stu-id="e9638-178">Stores audio media quality metrics in the media line.</span></span> <span data-ttu-id="e9638-179">Isso inclui as métricas de cancelamento de eco acústico (AEC) e controle automático de ganho (AGC).</span><span class="sxs-lookup"><span data-stu-id="e9638-179">This includes acoustic echo cancellation (AEC) and automatic gain control (AGC) metrics.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e9638-180"><a href="lync-server-2013-videostream-table.md">Tabela VideoStream no Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="e9638-180"><a href="lync-server-2013-videostream-table.md">VideoStream table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="e9638-181">Armazena as métricas de qualidade de mídia de vídeo para cada fluxo de áudio na linha de mídia.</span><span class="sxs-lookup"><span data-stu-id="e9638-181">Stores video media quality metrics for each audio stream in the media line.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e9638-182"><a href="lync-server-2013-audioclientevent-table.md">Tabela AudioClientEvent no Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="e9638-182"><a href="lync-server-2013-audioclientevent-table.md">AudioClientEvent table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="e9638-183">Armazena métricas de qualidade da mídia de áudio coletadas do evento do cliente.</span><span class="sxs-lookup"><span data-stu-id="e9638-183">Stores audio media quality metrics collected from the client event.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e9638-184"><a href="lync-server-2013-videoclientevent-table.md">Tabela VideoClientEvent no Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="e9638-184"><a href="lync-server-2013-videoclientevent-table.md">VideoClientEvent table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="e9638-185">Armazena as métricas de qualidade da mídia de vídeo coletadas do evento do cliente.</span><span class="sxs-lookup"><span data-stu-id="e9638-185">Stores video media quality metrics collected from the client event.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e9638-186"><strong>Tabela DiagnosticData</strong></span><span class="sxs-lookup"><span data-stu-id="e9638-186"><strong>DiagnosticData Table</strong></span></span></p></td>
<td><p><span data-ttu-id="e9638-187">Armazena dados de diagnóstico que são somente para uso interno.</span><span class="sxs-lookup"><span data-stu-id="e9638-187">Stores diagnostic data which is for internal use only.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="e9638-188">**Tabelas para dados de resumo**</span><span class="sxs-lookup"><span data-stu-id="e9638-188">**Tables for summary data**</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e9638-189"><strong>Tabela</strong></span><span class="sxs-lookup"><span data-stu-id="e9638-189"><strong>Table</strong></span></span></th>
<th><span data-ttu-id="e9638-190"><strong>Descrição</strong></span><span class="sxs-lookup"><span data-stu-id="e9638-190"><strong>Description</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e9638-191"><strong>Tabela ServerSummary</strong></span><span class="sxs-lookup"><span data-stu-id="e9638-191"><strong>ServerSummary Table</strong></span></span></p></td>
<td><p><span data-ttu-id="e9638-192">Armazena dados de resumo para os servidores, esses dados são usados apenas para relatórios de qualidade da experiência (QoE).</span><span class="sxs-lookup"><span data-stu-id="e9638-192">Stores summary data for the servers, these data is used for Quality of Experience (QoE) reporting only.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e9638-193"><strong>Tabela do usersummary</strong></span><span class="sxs-lookup"><span data-stu-id="e9638-193"><strong>UserSummary Table</strong></span></span></p></td>
<td><p><span data-ttu-id="e9638-194">Armazena dados de resumo para os usuários, esses dados são usados somente para relatórios de QoE.</span><span class="sxs-lookup"><span data-stu-id="e9638-194">Stores summary data for users, these data is used for QoE reporting only.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e9638-195"><strong>Tabela CallTypeSummary</strong></span><span class="sxs-lookup"><span data-stu-id="e9638-195"><strong>CallTypeSummary Table</strong></span></span></p></td>
<td><p><span data-ttu-id="e9638-196">Armazenar dados de resumo para tipos de chamadas, esses dados são usados somente para relatórios de QoE.</span><span class="sxs-lookup"><span data-stu-id="e9638-196">Store summary data for call types, these data is used for QoE reporting only.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="e9638-197">**Tabelas para uso interno pelo Monitoring Server**</span><span class="sxs-lookup"><span data-stu-id="e9638-197">**Tables for Internal Use by Monitoring Server**</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e9638-198"><strong>Tabela</strong></span><span class="sxs-lookup"><span data-stu-id="e9638-198"><strong>Table</strong></span></span></th>
<th><span data-ttu-id="e9638-199"><strong>Descrição</strong></span><span class="sxs-lookup"><span data-stu-id="e9638-199"><strong>Description</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e9638-200"><strong>DbConfigDateTime</strong></span><span class="sxs-lookup"><span data-stu-id="e9638-200"><strong>DbConfigDateTime</strong></span></span></p></td>
<td><p><span data-ttu-id="e9638-201">Somente para uso interno.</span><span class="sxs-lookup"><span data-stu-id="e9638-201">For internal use only.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e9638-202"><strong>DbConfigInt</strong></span><span class="sxs-lookup"><span data-stu-id="e9638-202"><strong>DbConfigInt</strong></span></span></p></td>
<td><p><span data-ttu-id="e9638-203">Somente para uso interno.</span><span class="sxs-lookup"><span data-stu-id="e9638-203">For internal use only.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e9638-204"><strong>Tabela de front-end</strong></span><span class="sxs-lookup"><span data-stu-id="e9638-204"><strong>FrontEnd Table</strong></span></span></p></td>
<td><p><span data-ttu-id="e9638-205">Somente para uso interno.</span><span class="sxs-lookup"><span data-stu-id="e9638-205">For internal use only.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e9638-206"><strong>Tabela de tarefas</strong></span><span class="sxs-lookup"><span data-stu-id="e9638-206"><strong>Task Table</strong></span></span></p></td>
<td><p><span data-ttu-id="e9638-207">Somente para uso interno.</span><span class="sxs-lookup"><span data-stu-id="e9638-207">For internal use only.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e9638-208"><strong>SummaryTableConfiguration</strong></span><span class="sxs-lookup"><span data-stu-id="e9638-208"><strong>SummaryTableConfiguration</strong></span></span></p></td>
<td><p><span data-ttu-id="e9638-209">Somente para uso interno.</span><span class="sxs-lookup"><span data-stu-id="e9638-209">For internal use only.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e9638-210"><strong>DbErrorMessage</strong></span><span class="sxs-lookup"><span data-stu-id="e9638-210"><strong>DbErrorMessage</strong></span></span></p></td>
<td><p><span data-ttu-id="e9638-211">Somente para uso interno.</span><span class="sxs-lookup"><span data-stu-id="e9638-211">For internal use only.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e9638-212"><strong>MetricsThreshold</strong></span><span class="sxs-lookup"><span data-stu-id="e9638-212"><strong>MetricsThreshold</strong></span></span></p></td>
<td><p><span data-ttu-id="e9638-213">Somente para uso interno.</span><span class="sxs-lookup"><span data-stu-id="e9638-213">For internal use only.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e9638-214"><strong>DaylightSavingYears</strong></span><span class="sxs-lookup"><span data-stu-id="e9638-214"><strong>DaylightSavingYears</strong></span></span></p></td>
<td><p><span data-ttu-id="e9638-215">Somente para uso interno.</span><span class="sxs-lookup"><span data-stu-id="e9638-215">For internal use only.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e9638-216"><strong>TimeZoneConfiguration</strong></span><span class="sxs-lookup"><span data-stu-id="e9638-216"><strong>TimeZoneConfiguration</strong></span></span></p></td>
<td><p><span data-ttu-id="e9638-217">Somente para uso interno.</span><span class="sxs-lookup"><span data-stu-id="e9638-217">For internal use only.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e9638-218"><strong>Fusos horários</strong></span><span class="sxs-lookup"><span data-stu-id="e9638-218"><strong>TimeZones</strong></span></span></p></td>
<td><p><span data-ttu-id="e9638-219">Somente para uso interno.</span><span class="sxs-lookup"><span data-stu-id="e9638-219">For internal use only.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e9638-220"><strong>Tabela CallSummary</strong></span><span class="sxs-lookup"><span data-stu-id="e9638-220"><strong>CallSummary Table</strong></span></span></p></td>
<td><p><span data-ttu-id="e9638-221">Somente para uso interno.</span><span class="sxs-lookup"><span data-stu-id="e9638-221">For internal use only.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e9638-222"><strong>Tabela DeviceCallSumary</strong></span><span class="sxs-lookup"><span data-stu-id="e9638-222"><strong>DeviceCallSumary Table</strong></span></span></p></td>
<td><p><span data-ttu-id="e9638-223">Somente para uso interno.</span><span class="sxs-lookup"><span data-stu-id="e9638-223">For internal use only.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e9638-224"><strong>Tabela de locatários</strong></span><span class="sxs-lookup"><span data-stu-id="e9638-224"><strong>Tenant Table</strong></span></span></p></td>
<td><p><span data-ttu-id="e9638-225">Somente para uso interno.</span><span class="sxs-lookup"><span data-stu-id="e9638-225">For internal use only.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e9638-226"><strong>VideoCallSummaryTable</strong></span><span class="sxs-lookup"><span data-stu-id="e9638-226"><strong>VideoCallSummaryTable</strong></span></span></p></td>
<td><p><span data-ttu-id="e9638-227">Somente para uso interno.</span><span class="sxs-lookup"><span data-stu-id="e9638-227">For internal use only.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e9638-228"><strong>ASCallSummaryTable</strong></span><span class="sxs-lookup"><span data-stu-id="e9638-228"><strong>ASCallSummaryTable</strong></span></span></p></td>
<td><p><span data-ttu-id="e9638-229">Somente para uso interno.</span><span class="sxs-lookup"><span data-stu-id="e9638-229">For internal use only.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

