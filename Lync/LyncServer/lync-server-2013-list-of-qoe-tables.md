---
title: 'Lync Server 2013: Lista de tabelas QoE'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: List of QoE tables
ms:assetid: 176194d7-d184-4e23-94bb-cb62b4db47f5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398236(v=OCS.15)
ms:contentKeyID: 48183512
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 51c82c38a995fd9e847057fedbbce1422085332b
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34828944"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="list-of-qoe-tables-in-lync-server-2013"></a><span data-ttu-id="e3173-102">Lista de tabelas QoE no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e3173-102">List of QoE tables in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e3173-103">_**Tópico da última modificação:** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="e3173-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="e3173-104">O esquema de banco de dados consiste nas tabelas a seguir.</span><span class="sxs-lookup"><span data-stu-id="e3173-104">The database schema consists of the following tables.</span></span>

<span data-ttu-id="e3173-105">**Tabelas de suporte**</span><span class="sxs-lookup"><span data-stu-id="e3173-105">**Supporting Tables**</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e3173-106"><strong>Tabela</strong></span><span class="sxs-lookup"><span data-stu-id="e3173-106"><strong>Table</strong></span></span></th>
<th><span data-ttu-id="e3173-107"><strong>Descrição</strong></span><span class="sxs-lookup"><span data-stu-id="e3173-107"><strong>Description</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e3173-108"><a href="lync-server-2013-appsharingmetricsthreshold-table.md">Tabela AppSharingMetricsThreshold no Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="e3173-108"><a href="lync-server-2013-appsharingmetricsthreshold-table.md">AppSharingMetricsThreshold table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="e3173-109">Armazena valores satisfatórios e satisfatórios para as métricas de qualidade da experiência usadas com o compartilhamento de aplicativos.</span><span class="sxs-lookup"><span data-stu-id="e3173-109">Stores optimal and acceptable values for the Quality of Experience metrics used with application sharing.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e3173-110"><a href="lync-server-2013-codecdescription-table.md">Tabela CodecDescription no Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="e3173-110"><a href="lync-server-2013-codecdescription-table.md">CodecDescription table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="e3173-111">Mapeia identificadores de codec exclusivos para o codec correspondente.</span><span class="sxs-lookup"><span data-stu-id="e3173-111">Maps unique codec identifiers to their corresponding codec.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e3173-112"><a href="lync-server-2013-ipaddress-table.md">Tabela IPAddress no Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="e3173-112"><a href="lync-server-2013-ipaddress-table.md">IPAddress table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="e3173-113">Mapeia endereços IP para os identificadores de endereços IP exclusivos usados em outro lugar no banco de dados de qualidade da experiência.</span><span class="sxs-lookup"><span data-stu-id="e3173-113">Maps IP addresses to the unique IP address identifiers used elsewhere in the Quality of Experience database.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e3173-114"><a href="lync-server-2013-networkconnectiondetail-table.md">Tabela NetworkConnectionDetail no Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="e3173-114"><a href="lync-server-2013-networkconnectiondetail-table.md">NetworkConnectionDetail table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="e3173-115">Mapeia tipos de conexão de rede para os identificadores de conexão de rede usados em outro lugar no banco de dados de qualidade da experiência.</span><span class="sxs-lookup"><span data-stu-id="e3173-115">Maps network connection types to the network connection identifiers used elsewhere in the Quality of Experience database.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e3173-116"><a href="lync-server-2013-purgesettings-table-qoe.md">Tabela PurgeSettings (QoE) no Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="e3173-116"><a href="lync-server-2013-purgesettings-table-qoe.md">PurgeSettings table (QoE) in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="e3173-117">Armazena informações que especificam se (e quando) registros de qualidade de experiência desatualizados serão excluídos automaticamente do banco de dados de QoE.</span><span class="sxs-lookup"><span data-stu-id="e3173-117">Stores information that specifies if (and when) outdated Quality of Experience records will automatically be deleted from the QoE database.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e3173-118"><a href="lync-server-2013-traceroute-table.md">Tabela TraceRoute no Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="e3173-118"><a href="lync-server-2013-traceroute-table.md">TraceRoute table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="e3173-119">Armazena informações de roteamento para chamadas.</span><span class="sxs-lookup"><span data-stu-id="e3173-119">Stores routing information for calls.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e3173-120"><a href="lync-server-2013-useragentdef-table-qoe.md">Tabela UserAgentDef (QoE) no Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="e3173-120"><a href="lync-server-2013-useragentdef-table-qoe.md">UserAgentDef table (QoE) in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="e3173-121">Mapeia identificadores de agente de usuário para os nomes descritivos do agente.</span><span class="sxs-lookup"><span data-stu-id="e3173-121">Maps user agent identifiers to the agent’s descriptive names.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e3173-122"><a href="lync-server-2013-videometricsthreshold-table.md">Tabela VideoMetricsThreshold no Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="e3173-122"><a href="lync-server-2013-videometricsthreshold-table.md">VideoMetricsThreshold table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="e3173-123">Armazena valores satisfatórios e satisfatórios para as métricas de qualidade da experiência usadas com chamadas com vídeo.</span><span class="sxs-lookup"><span data-stu-id="e3173-123">Stores optimal and acceptable values for the Quality of Experience metrics used with video calls.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e3173-124"><a href="lync-server-2013-useragent-table.md">Tabela UserAgent no Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="e3173-124"><a href="lync-server-2013-useragent-table.md">UserAgent table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="e3173-125">Armazena cadeias de caracteres de UA (protocolo de início de sessão) do SIP e tipos de UA usados em sessões de áudio e vídeo.</span><span class="sxs-lookup"><span data-stu-id="e3173-125">Stores Session Initiation Protocol (SIP) User Agent (UA) strings and UA types used in audio and video sessions.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e3173-126"><a href="lync-server-2013-user-table.md">Tabela User no Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="e3173-126"><a href="lync-server-2013-user-table.md">User table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="e3173-127">Armazena URIs de usuário, conferência e telefone usados em sessões de áudio e vídeo.</span><span class="sxs-lookup"><span data-stu-id="e3173-127">Stores user, conference, and phone URIs used in audio and video sessions.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e3173-128"><a href="lync-server-2013-endpoint-table.md">Tabela Endpoint no Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="e3173-128"><a href="lync-server-2013-endpoint-table.md">Endpoint table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="e3173-129">Armazena nomes de computador FQDN de pontos de extremidade que participam de sessões de áudio e vídeo.</span><span class="sxs-lookup"><span data-stu-id="e3173-129">Stores FQDN computer names of endpoints participating in audio and video sessions.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e3173-130"><a href="lync-server-2013-pool-table.md">Tabela Pool no Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="e3173-130"><a href="lync-server-2013-pool-table.md">Pool table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="e3173-131">Armazena os nomes dos pools aos quais os dados de métricas pertencem.</span><span class="sxs-lookup"><span data-stu-id="e3173-131">Stores the names of pools to which metrics data belongs.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e3173-132"><a href="lync-server-2013-device-table.md">Tabela Device no Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="e3173-132"><a href="lync-server-2013-device-table.md">Device table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="e3173-133">Armazena dispositivos de captura e renderiza dispositivos que são usados em chamadas de áudio/vídeo.</span><span class="sxs-lookup"><span data-stu-id="e3173-133">Stores capture devices and render devices which are used in an audio/video calls.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e3173-134"><a href="lync-server-2013-devicedriver-table.md">Tabela DeviceDriver no Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="e3173-134"><a href="lync-server-2013-devicedriver-table.md">DeviceDriver table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="e3173-135">Armazena o driver para o dispositivo de captura e o dispositivo de renderização que são usados em chamadas de áudio/vídeo.</span><span class="sxs-lookup"><span data-stu-id="e3173-135">Stores driver for the capture device and the render device which are used in audio/video calls.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e3173-136"><a href="lync-server-2013-conference-table.md">Tabela Conference no Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="e3173-136"><a href="lync-server-2013-conference-table.md">Conference table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="e3173-137">Armazena URIs de conferência para cenários de conferência ou caixa de diálogo para outros cenários.</span><span class="sxs-lookup"><span data-stu-id="e3173-137">Stores Conference URIs for conference scenarios or DialogID for other scenarios.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e3173-138"><a href="lync-server-2013-sessioncorrelation-table.md">Tabela SessionCorrelation no Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="e3173-138"><a href="lync-server-2013-sessioncorrelation-table.md">SessionCorrelation table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="e3173-139">Armazena CorrelationId para chamadas PSTN.</span><span class="sxs-lookup"><span data-stu-id="e3173-139">Stores CorrelationID for PSTN calls.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e3173-140"><a href="lync-server-2013-payloaddescription-table.md">Tabela PayloadDescription no Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="e3173-140"><a href="lync-server-2013-payloaddescription-table.md">PayloadDescription table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="e3173-141">Armazena o codec usado em chamadas de áudio/vídeo.</span><span class="sxs-lookup"><span data-stu-id="e3173-141">Stores the Codec used in audio/video calls.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e3173-142"><a href="lync-server-2013-appliedbandwidthsource-table.md">Tabela AppliedBandwidthSource no Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="e3173-142"><a href="lync-server-2013-appliedbandwidthsource-table.md">AppliedBandwidthSource table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="e3173-143">Armazena a fonte de largura de banda usada em chamadas de áudio/vídeo.</span><span class="sxs-lookup"><span data-stu-id="e3173-143">Stores the bandwidth source used in audio/video calls.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e3173-144"><a href="lync-server-2013-macaddress-table.md">Tabela MacAddress no Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="e3173-144"><a href="lync-server-2013-macaddress-table.md">MacAddress table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="e3173-145">Armazena o endereço MAC dos pontos de extremidade que participam de sessões de áudio e vídeo.</span><span class="sxs-lookup"><span data-stu-id="e3173-145">Stores the MAC address of the endpoints participating in audio and video sessions.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e3173-146"><a href="lync-server-2013-dialog-table.md">Tabela Dialog no Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="e3173-146"><a href="lync-server-2013-dialog-table.md">Dialog table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="e3173-147">Armazena a ID da caixa de diálogo de sessões de áudio e vídeo.</span><span class="sxs-lookup"><span data-stu-id="e3173-147">Stores the Dialog ID of audio and video sessions.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e3173-148"><a href="lync-server-2013-region-table.md">Tabela de regiões no Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="e3173-148"><a href="lync-server-2013-region-table.md">Region table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="e3173-149">Armazena a região de rede definida na configuração NCS.</span><span class="sxs-lookup"><span data-stu-id="e3173-149">Stores the network region defined in NCS setting.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e3173-150"><a href="lync-server-2013-usersite-table.md">Tabela UserSite no Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="e3173-150"><a href="lync-server-2013-usersite-table.md">UserSite table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="e3173-151">Armazena o site de rede definido na configuração NCS.</span><span class="sxs-lookup"><span data-stu-id="e3173-151">Stores the network site defined in NCS setting.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e3173-152"><a href="lync-server-2013-subnet-table.md">Tabela Subnet no Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="e3173-152"><a href="lync-server-2013-subnet-table.md">Subnet table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="e3173-153">Armazena a sub-rede definida na configuração NCS.</span><span class="sxs-lookup"><span data-stu-id="e3173-153">Stores the subnet defined in NCS setting.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e3173-154"><a href="lync-server-2013-monitoredregionlink-table.md">Tabela MonitoredRegionLink no Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="e3173-154"><a href="lync-server-2013-monitoredregionlink-table.md">MonitoredRegionLink table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="e3173-155">Armazena o link de região definido na configuração NCS.</span><span class="sxs-lookup"><span data-stu-id="e3173-155">Stores the region link defined in NCS setting.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e3173-156"><a href="monitoredusersitelink-table.md">Tabela MonitoredUserSiteLink</a></span><span class="sxs-lookup"><span data-stu-id="e3173-156"><a href="monitoredusersitelink-table.md">MonitoredUserSiteLink table</a></span></span></p></td>
<td><p><span data-ttu-id="e3173-157">Armazena os links de sites de rede definidos na configuração NCS.</span><span class="sxs-lookup"><span data-stu-id="e3173-157">Stores the network site links defined in NCS setting.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e3173-158"><a href="lync-server-2013-endpointsubnet-table.md">Tabela EndpointSubnet no Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="e3173-158"><a href="lync-server-2013-endpointsubnet-table.md">EndpointSubnet table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="e3173-159">Armazena a sub-rede do ponto de extremidade que participa de uma sessão de áudio e vídeo.</span><span class="sxs-lookup"><span data-stu-id="e3173-159">Stores the subnet of the endpoint participating in an audio and video session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e3173-160"><a href="lync-server-2013-server-table.md">Tabela Server no Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="e3173-160"><a href="lync-server-2013-server-table.md">Server table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="e3173-161">Armazena o FQDN ou endereço IP do servidor ao qual a mídia vai.</span><span class="sxs-lookup"><span data-stu-id="e3173-161">Stores the FQDN or IP address of the server the media goes through.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="e3173-162">**Tabelas para dados de métricas**</span><span class="sxs-lookup"><span data-stu-id="e3173-162">**Tables for metrics data**</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e3173-163"><strong>Tabela</strong></span><span class="sxs-lookup"><span data-stu-id="e3173-163"><strong>Table</strong></span></span></th>
<th><span data-ttu-id="e3173-164"><strong>Descrição</strong></span><span class="sxs-lookup"><span data-stu-id="e3173-164"><strong>Description</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e3173-165"><a href="lync-server-2013-appsharingstream-table.md">Tabela AppSharingStream no Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="e3173-165"><a href="lync-server-2013-appsharingstream-table.md">AppSharingStream table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="e3173-166">Armazena métricas de qualidade de experiência para os fluxos de rede usados para compartilhamento de aplicativos.</span><span class="sxs-lookup"><span data-stu-id="e3173-166">Stores Quality of Experience metrics for the network streams used for application sharing.</span></span> <span data-ttu-id="e3173-167">Métricas de qualidade de experiência para os fluxos de rede usados para compartilhamento de aplicativos.</span><span class="sxs-lookup"><span data-stu-id="e3173-167">Quality of Experience metrics for the network streams used for application sharing.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e3173-168"><a href="lync-server-2013-session-table.md">Tabela Session no Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="e3173-168"><a href="lync-server-2013-session-table.md">Session table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="e3173-169">Armazena informações gerais sobre uma sessão de áudio ou de áudio/vídeo.</span><span class="sxs-lookup"><span data-stu-id="e3173-169">Stores overall information about an audio or audio/video session.</span></span> <span data-ttu-id="e3173-170">Uma sessão é definida como uma caixa de diálogo de áudio ou vídeo SIP entre dois pontos de extremidade.</span><span class="sxs-lookup"><span data-stu-id="e3173-170">A session is defined as an audio or video SIP dialog between two endpoints.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e3173-171"><a href="lync-server-2013-medialine-table.md">Tabela MediaLine no Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="e3173-171"><a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="e3173-172">Armazena informações sobre cada linha de mídia em uma sessão.</span><span class="sxs-lookup"><span data-stu-id="e3173-172">Stores information about each media line in a session.</span></span> <span data-ttu-id="e3173-173">Uma linha de mídia é uma coleção de um ou mais fluxos de áudio e vídeo.</span><span class="sxs-lookup"><span data-stu-id="e3173-173">A media line is a collection of one or more audio and video streams.</span></span> <span data-ttu-id="e3173-174">Geralmente, uma única linha de mídia terá dois fluxos, áudio ou vídeo.</span><span class="sxs-lookup"><span data-stu-id="e3173-174">Typically, a single media line will have two streams, either audio or video.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e3173-175"><a href="lync-server-2013-audiostream-table.md">Tabela AudioStream no Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="e3173-175"><a href="lync-server-2013-audiostream-table.md">AudioStream table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="e3173-176">Armazena métricas de qualidade de mídia de áudio para cada fluxo de áudio na linha de mídia.</span><span class="sxs-lookup"><span data-stu-id="e3173-176">Stores audio media quality metrics for each audio stream in the media line.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e3173-177"><a href="lync-server-2013-audiosignal-table.md">Tabela AudioSignal no Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="e3173-177"><a href="lync-server-2013-audiosignal-table.md">AudioSignal table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="e3173-178">Armazena métricas de qualidade de mídia de áudio na linha de mídia.</span><span class="sxs-lookup"><span data-stu-id="e3173-178">Stores audio media quality metrics in the media line.</span></span> <span data-ttu-id="e3173-179">Isso inclui as métricas de cancelamento de eco acústico (AEC) e controle automático de ganho (AGC).</span><span class="sxs-lookup"><span data-stu-id="e3173-179">This includes acoustic echo cancellation (AEC) and automatic gain control (AGC) metrics.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e3173-180"><a href="lync-server-2013-videostream-table.md">Tabela VideoStream no Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="e3173-180"><a href="lync-server-2013-videostream-table.md">VideoStream table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="e3173-181">Armazena as métricas de qualidade de mídia de vídeo para cada fluxo de áudio na linha de mídia.</span><span class="sxs-lookup"><span data-stu-id="e3173-181">Stores video media quality metrics for each audio stream in the media line.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e3173-182"><a href="lync-server-2013-audioclientevent-table.md">Tabela AudioClientEvent no Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="e3173-182"><a href="lync-server-2013-audioclientevent-table.md">AudioClientEvent table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="e3173-183">Armazena métricas de qualidade da mídia de áudio coletadas do evento do cliente.</span><span class="sxs-lookup"><span data-stu-id="e3173-183">Stores audio media quality metrics collected from the client event.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e3173-184"><a href="lync-server-2013-videoclientevent-table.md">Tabela VideoClientEvent no Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="e3173-184"><a href="lync-server-2013-videoclientevent-table.md">VideoClientEvent table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="e3173-185">Armazena as métricas de qualidade da mídia de vídeo coletadas do evento do cliente.</span><span class="sxs-lookup"><span data-stu-id="e3173-185">Stores video media quality metrics collected from the client event.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e3173-186"><strong>Tabela DiagnosticData</strong></span><span class="sxs-lookup"><span data-stu-id="e3173-186"><strong>DiagnosticData Table</strong></span></span></p></td>
<td><p><span data-ttu-id="e3173-187">Armazena dados de diagnóstico que são somente para uso interno.</span><span class="sxs-lookup"><span data-stu-id="e3173-187">Stores diagnostic data which is for internal use only.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="e3173-188">**Tabelas para dados de resumo**</span><span class="sxs-lookup"><span data-stu-id="e3173-188">**Tables for summary data**</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e3173-189"><strong>Tabela</strong></span><span class="sxs-lookup"><span data-stu-id="e3173-189"><strong>Table</strong></span></span></th>
<th><span data-ttu-id="e3173-190"><strong>Descrição</strong></span><span class="sxs-lookup"><span data-stu-id="e3173-190"><strong>Description</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e3173-191"><strong>Tabela ServerSummary</strong></span><span class="sxs-lookup"><span data-stu-id="e3173-191"><strong>ServerSummary Table</strong></span></span></p></td>
<td><p><span data-ttu-id="e3173-192">Armazena dados de resumo para os servidores, esses dados são usados apenas para relatórios de qualidade da experiência (QoE).</span><span class="sxs-lookup"><span data-stu-id="e3173-192">Stores summary data for the servers, these data is used for Quality of Experience (QoE) reporting only.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e3173-193"><strong>Tabela do usersummary</strong></span><span class="sxs-lookup"><span data-stu-id="e3173-193"><strong>UserSummary Table</strong></span></span></p></td>
<td><p><span data-ttu-id="e3173-194">Armazena dados de resumo para os usuários, esses dados são usados somente para relatórios de QoE.</span><span class="sxs-lookup"><span data-stu-id="e3173-194">Stores summary data for users, these data is used for QoE reporting only.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e3173-195"><strong>Tabela CallTypeSummary</strong></span><span class="sxs-lookup"><span data-stu-id="e3173-195"><strong>CallTypeSummary Table</strong></span></span></p></td>
<td><p><span data-ttu-id="e3173-196">Armazenar dados de resumo para tipos de chamadas, esses dados são usados somente para relatórios de QoE.</span><span class="sxs-lookup"><span data-stu-id="e3173-196">Store summary data for call types, these data is used for QoE reporting only.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="e3173-197">**Tabelas para uso interno pelo Monitoring Server**</span><span class="sxs-lookup"><span data-stu-id="e3173-197">**Tables for Internal Use by Monitoring Server**</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e3173-198"><strong>Tabela</strong></span><span class="sxs-lookup"><span data-stu-id="e3173-198"><strong>Table</strong></span></span></th>
<th><span data-ttu-id="e3173-199"><strong>Descrição</strong></span><span class="sxs-lookup"><span data-stu-id="e3173-199"><strong>Description</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e3173-200"><strong>DbConfigDateTime</strong></span><span class="sxs-lookup"><span data-stu-id="e3173-200"><strong>DbConfigDateTime</strong></span></span></p></td>
<td><p><span data-ttu-id="e3173-201">Somente para uso interno.</span><span class="sxs-lookup"><span data-stu-id="e3173-201">For internal use only.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e3173-202"><strong>DbConfigInt</strong></span><span class="sxs-lookup"><span data-stu-id="e3173-202"><strong>DbConfigInt</strong></span></span></p></td>
<td><p><span data-ttu-id="e3173-203">Somente para uso interno.</span><span class="sxs-lookup"><span data-stu-id="e3173-203">For internal use only.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e3173-204"><strong>Tabela de front-end</strong></span><span class="sxs-lookup"><span data-stu-id="e3173-204"><strong>FrontEnd Table</strong></span></span></p></td>
<td><p><span data-ttu-id="e3173-205">Somente para uso interno.</span><span class="sxs-lookup"><span data-stu-id="e3173-205">For internal use only.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e3173-206"><strong>Tabela de tarefas</strong></span><span class="sxs-lookup"><span data-stu-id="e3173-206"><strong>Task Table</strong></span></span></p></td>
<td><p><span data-ttu-id="e3173-207">Somente para uso interno.</span><span class="sxs-lookup"><span data-stu-id="e3173-207">For internal use only.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e3173-208"><strong>SummaryTableConfiguration</strong></span><span class="sxs-lookup"><span data-stu-id="e3173-208"><strong>SummaryTableConfiguration</strong></span></span></p></td>
<td><p><span data-ttu-id="e3173-209">Somente para uso interno.</span><span class="sxs-lookup"><span data-stu-id="e3173-209">For internal use only.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e3173-210"><strong>DbErrorMessage</strong></span><span class="sxs-lookup"><span data-stu-id="e3173-210"><strong>DbErrorMessage</strong></span></span></p></td>
<td><p><span data-ttu-id="e3173-211">Somente para uso interno.</span><span class="sxs-lookup"><span data-stu-id="e3173-211">For internal use only.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e3173-212"><strong>MetricsThreshold</strong></span><span class="sxs-lookup"><span data-stu-id="e3173-212"><strong>MetricsThreshold</strong></span></span></p></td>
<td><p><span data-ttu-id="e3173-213">Somente para uso interno.</span><span class="sxs-lookup"><span data-stu-id="e3173-213">For internal use only.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e3173-214"><strong>DaylightSavingYears</strong></span><span class="sxs-lookup"><span data-stu-id="e3173-214"><strong>DaylightSavingYears</strong></span></span></p></td>
<td><p><span data-ttu-id="e3173-215">Somente para uso interno.</span><span class="sxs-lookup"><span data-stu-id="e3173-215">For internal use only.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e3173-216"><strong>TimeZoneConfiguration</strong></span><span class="sxs-lookup"><span data-stu-id="e3173-216"><strong>TimeZoneConfiguration</strong></span></span></p></td>
<td><p><span data-ttu-id="e3173-217">Somente para uso interno.</span><span class="sxs-lookup"><span data-stu-id="e3173-217">For internal use only.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e3173-218"><strong>Fusos horários</strong></span><span class="sxs-lookup"><span data-stu-id="e3173-218"><strong>TimeZones</strong></span></span></p></td>
<td><p><span data-ttu-id="e3173-219">Somente para uso interno.</span><span class="sxs-lookup"><span data-stu-id="e3173-219">For internal use only.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e3173-220"><strong>Tabela CallSummary</strong></span><span class="sxs-lookup"><span data-stu-id="e3173-220"><strong>CallSummary Table</strong></span></span></p></td>
<td><p><span data-ttu-id="e3173-221">Somente para uso interno.</span><span class="sxs-lookup"><span data-stu-id="e3173-221">For internal use only.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e3173-222"><strong>Tabela DeviceCallSumary</strong></span><span class="sxs-lookup"><span data-stu-id="e3173-222"><strong>DeviceCallSumary Table</strong></span></span></p></td>
<td><p><span data-ttu-id="e3173-223">Somente para uso interno.</span><span class="sxs-lookup"><span data-stu-id="e3173-223">For internal use only.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e3173-224"><strong>Tabela de locatários</strong></span><span class="sxs-lookup"><span data-stu-id="e3173-224"><strong>Tenant Table</strong></span></span></p></td>
<td><p><span data-ttu-id="e3173-225">Somente para uso interno.</span><span class="sxs-lookup"><span data-stu-id="e3173-225">For internal use only.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e3173-226"><strong>VideoCallSummaryTable</strong></span><span class="sxs-lookup"><span data-stu-id="e3173-226"><strong>VideoCallSummaryTable</strong></span></span></p></td>
<td><p><span data-ttu-id="e3173-227">Somente para uso interno.</span><span class="sxs-lookup"><span data-stu-id="e3173-227">For internal use only.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e3173-228"><strong>ASCallSummaryTable</strong></span><span class="sxs-lookup"><span data-stu-id="e3173-228"><strong>ASCallSummaryTable</strong></span></span></p></td>
<td><p><span data-ttu-id="e3173-229">Somente para uso interno.</span><span class="sxs-lookup"><span data-stu-id="e3173-229">For internal use only.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

