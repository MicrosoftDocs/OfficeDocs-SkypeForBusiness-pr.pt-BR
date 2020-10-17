---
title: 'Lync Server 2013: lista de tabelas CDR'
description: 'Lync Server 2013: lista de tabelas CDR.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: List of CDR tables
ms:assetid: 031843fd-c7ff-4534-9b02-8847aad70807
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398084(v=OCS.15)
ms:contentKeyID: 48183254
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 21d0f683ffeb0f5f1cbba5db4c45d248aa14e8e4
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48558697"
---
# <a name="list-of-cdr-tables-in-lync-server-2013"></a><span data-ttu-id="99d8d-103">Lista de tabelas CDR no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="99d8d-103">List of CDR tables in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="99d8d-104">_**Última modificação do tópico:** 2012-10-18_</span><span class="sxs-lookup"><span data-stu-id="99d8d-104">_**Topic Last Modified:** 2012-10-18_</span></span>

<span data-ttu-id="99d8d-105">O esquema de banco de dados de registro de detalhes das chamadas (CDR) consiste nas seguintes tabelas.</span><span class="sxs-lookup"><span data-stu-id="99d8d-105">The call detail recording (CDR) database schema consists of the following tables.</span></span>

<div>

## <a name="static-tables"></a><span data-ttu-id="99d8d-106">Tabelas Estáticas</span><span class="sxs-lookup"><span data-stu-id="99d8d-106">Static Tables</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="99d8d-107">Tabela</span><span class="sxs-lookup"><span data-stu-id="99d8d-107">Table</span></span></th>
<th><span data-ttu-id="99d8d-108">Descrição</span><span class="sxs-lookup"><span data-stu-id="99d8d-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="99d8d-109"><a href="lync-server-2013-callpriorities-table.md">Tabela CallPriorities no Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="99d8d-109"><a href="lync-server-2013-callpriorities-table.md">CallPriorities table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="99d8d-110">Armazena a lista de prioridade de chamadas possíveis, tais como emergência, urgente, normal, não urgente e outras.</span><span class="sxs-lookup"><span data-stu-id="99d8d-110">Stores the list of possible call priorities, such as emergency, urgent, normal, non-urgent, and more.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="99d8d-111"><a href="lync-server-2013-conferencejointimethresholds-table.md">Tabela ConferenceJoinTimeThresholds no Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="99d8d-111"><a href="lync-server-2013-conferencejointimethresholds-table.md">ConferenceJoinTimeThresholds table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="99d8d-112">Armazena os limites de classificação utilizados pelo Relatório de resumo de tempo de participação na conferência.</span><span class="sxs-lookup"><span data-stu-id="99d8d-112">Stores the classification boundaries used by the Conference Join Time Summary Report.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="99d8d-113"><a href="lync-server-2013-deregistertype-table.md">Tabela deregistertype no Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="99d8d-113"><a href="lync-server-2013-deregistertype-table.md">DeRegisterType table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="99d8d-114">Armazena a lista de possíveis razões de cancelamento de registro do usuário, como o &quot; cliente iniciado, o &quot; &quot; registro expirado, &quot; &quot; falha do cliente &quot; e muito mais.</span><span class="sxs-lookup"><span data-stu-id="99d8d-114">Stores the list of possible user de-register reasons, such as &quot;client initiated,&quot; &quot;registration expired,&quot; &quot;client crash,&quot; and more.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="99d8d-115"><a href="lync-server-2013-medialist-table.md">Tabela medialist no Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="99d8d-115"><a href="lync-server-2013-medialist-table.md">MediaList table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="99d8d-116">Armazena a lista de tipos de mídia que podem gerar as entradas no banco de dados (por exemplo IM, áudio, vídeo e transferência de arquivos).</span><span class="sxs-lookup"><span data-stu-id="99d8d-116">Stores the list of media types that can generate entries in the database (for example, IM, audio, video, and file transfer).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="99d8d-117"><a href="lync-server-2013-purgesettings-table.md">Tabela PurgeSettings no Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="99d8d-117"><a href="lync-server-2013-purgesettings-table.md">PurgeSettings table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="99d8d-118">Armazena informação que especifica se (e quando) registros de detalhes de chamada desatualizada serão excluídas automaticamente do banco de dados CDR.</span><span class="sxs-lookup"><span data-stu-id="99d8d-118">Stores information that specifies if (and when) outdated call detail records will automatically be deleted from the CDR database.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="99d8d-119"><a href="lync-server-2013-roles-table.md">Tabela de funções no Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="99d8d-119"><a href="lync-server-2013-roles-table.md">Roles table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="99d8d-120">Armazena a lista de funções de conferência possíveis (por exemplo, participantes e apresentadores).</span><span class="sxs-lookup"><span data-stu-id="99d8d-120">Stores the list of possible conference roles (for example, attendee and presenter).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="99d8d-121"><a href="lync-server-2013-sipresponsemetadata-table.md">Tabela SIPResponseMetaData no Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="99d8d-121"><a href="lync-server-2013-sipresponsemetadata-table.md">SIPResponseMetaData table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="99d8d-122">Stores a list of SIP response codes and the classification and definition of each of those codes.</span><span class="sxs-lookup"><span data-stu-id="99d8d-122">Stores a list of SIP response codes and the classification and definition of each of those codes.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="supporting-tables"></a><span data-ttu-id="99d8d-123">Tabelas de Suporte</span><span class="sxs-lookup"><span data-stu-id="99d8d-123">Supporting Tables</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="99d8d-124">Tabela</span><span class="sxs-lookup"><span data-stu-id="99d8d-124">Table</span></span></th>
<th><span data-ttu-id="99d8d-125">Descrição</span><span class="sxs-lookup"><span data-stu-id="99d8d-125">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="99d8d-126"><a href="lync-server-2013-clientversions-table.md">Tabela ClientVersions no Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="99d8d-126"><a href="lync-server-2013-clientversions-table.md">ClientVersions table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="99d8d-127">Armazena os clientes (tanto o tipo de cliente quanto o número de versão) de cada cliente envolvido em uma chamada com informações capturadas neste banco de dados.</span><span class="sxs-lookup"><span data-stu-id="99d8d-127">Stores the clients (both client type and version number) of each client involved in a call with information captured in this database.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="99d8d-128"><a href="lync-server-2013-conferenceuris-table.md">Tabela ConferenceUris no Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="99d8d-128"><a href="lync-server-2013-conferenceuris-table.md">ConferenceUris table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="99d8d-129">Armazena uma lista de ConferenceURIs que são utilizadas em chamadas relacionadas a conferências.</span><span class="sxs-lookup"><span data-stu-id="99d8d-129">Stores a list of ConferenceURIs that are used in conference related calls.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="99d8d-130"><a href="lync-server-2013-contenttypes-table.md">Tabela ContentTypes no Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="99d8d-130"><a href="lync-server-2013-contenttypes-table.md">ContentTypes table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="99d8d-131">Armazena uma lista de tipos de conteúdo SIP (Session Initiation Protocol) que são usadas tanto em chamadas ponto-a-ponto quanto em chamadas de conferência.</span><span class="sxs-lookup"><span data-stu-id="99d8d-131">Stores a list of Session Initiation Protocol (SIP) content types that are used in both peer-to-peer calls and conference calls.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="99d8d-132"><a href="lync-server-2013-devices-table.md">Tabela de dispositivos no Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="99d8d-132"><a href="lync-server-2013-devices-table.md">Devices table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="99d8d-133">Armazena uma lista de dispositivos, incluindo a versão de hardware, fabricante e endereço MAC.</span><span class="sxs-lookup"><span data-stu-id="99d8d-133">Stores a list of devices, including their manufacturer, hardware version, and MAC address.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="99d8d-134"><a href="lync-server-2013-dialogs-table.md">Tabela Dialogs no Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="99d8d-134"><a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="99d8d-135">Armazena informações sobre o ID de Diálogo para cada sessão no banco de dados.</span><span class="sxs-lookup"><span data-stu-id="99d8d-135">Stores information about the Dialog ID for each session in the database.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="99d8d-136"><a href="lync-server-2013-edgeservers-table.md">Tabela EdgeServers no Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="99d8d-136"><a href="lync-server-2013-edgeservers-table.md">EdgeServers table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="99d8d-137">Armazena uma lista de Servidores de Borda  usados para chamadas externas.</span><span class="sxs-lookup"><span data-stu-id="99d8d-137">Stores a list of Edge Servers that are used for external calls.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="99d8d-138"><a href="lync-server-2013-gateways-table.md">Tabela gateways no Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="99d8d-138"><a href="lync-server-2013-gateways-table.md">Gateways table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="99d8d-139">Armazena uma lista de Gateways usados para chamadas VoIP (Voice over Internet Protocol).</span><span class="sxs-lookup"><span data-stu-id="99d8d-139">Stores a list of Gateways that are used for Voice over Internet Protocol (VoIP) calls.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="99d8d-140"><a href="lync-server-2013-hardwareversions-table.md">Tabela HardwareVersions no Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="99d8d-140"><a href="lync-server-2013-hardwareversions-table.md">HardwareVersions table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="99d8d-141">Armazena uma lista de versões de hardware de dispositivos (telefone de mesa).</span><span class="sxs-lookup"><span data-stu-id="99d8d-141">Stores a list of hardware versions of devices (desk phone).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="99d8d-142"><a href="lync-server-2013-manufacturers-table.md">Tabela de fabricantes no Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="99d8d-142"><a href="lync-server-2013-manufacturers-table.md">Manufacturers table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="99d8d-143">Armazena uma lista de fabricantes de dispositivos (telefone de mesa).</span><span class="sxs-lookup"><span data-stu-id="99d8d-143">Stores a list of manufacturers of devices (desk phone).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="99d8d-144"><a href="lync-server-2013-mcus-table.md">Tabela MCUs no Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="99d8d-144"><a href="lync-server-2013-mcus-table.md">Mcus table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="99d8d-145">Armazena informações sobre os vários Servidores de Conferência A/V e seus URIs.</span><span class="sxs-lookup"><span data-stu-id="99d8d-145">Stores information about the various A/V Conferencing Servers and their URIs.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="99d8d-146"><a href="lync-server-2013-mediationservers-table.md">Tabela MediationServers no Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="99d8d-146"><a href="lync-server-2013-mediationservers-table.md">MediationServers table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="99d8d-147">Armazena uma lista de Servidores de Mediação usados para chamadas VoIP.</span><span class="sxs-lookup"><span data-stu-id="99d8d-147">Stores a list of Mediation Servers that are used for VoIP calls.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="99d8d-148"><a href="lync-server-2013-phones-table.md">Tabela phones no Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="99d8d-148"><a href="lync-server-2013-phones-table.md">Phones table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="99d8d-149">Armazena todos os números de telefone usados em chamadas VoIP que foram arquivadas ou que tiveram os detalhes da chamadas gravados.</span><span class="sxs-lookup"><span data-stu-id="99d8d-149">Stores all the phone numbers used in VoIP calls that were archived or whose call details were recorded.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="99d8d-150"><a href="lync-server-2013-pools-table.md">Tabela de pools no Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="99d8d-150"><a href="lync-server-2013-pools-table.md">Pools table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="99d8d-151">Armazena os nomes do pool no qual as mensagens de IM são capturadas.</span><span class="sxs-lookup"><span data-stu-id="99d8d-151">Stores the names of the pool on which IM messages are captured.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="99d8d-152"><a href="lync-server-2013-servers-table.md">Tabela de servidores no Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="99d8d-152"><a href="lync-server-2013-servers-table.md">Servers table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="99d8d-153">Armazena o nome de servidores envolvidos em chamadas.</span><span class="sxs-lookup"><span data-stu-id="99d8d-153">Stores the name of servers involved in calls.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="99d8d-154"><a href="lync-server-2013-tenants-table.md">Tabela de locatários no Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="99d8d-154"><a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="99d8d-155">Armazena os locatários suportados pela implantação atual.</span><span class="sxs-lookup"><span data-stu-id="99d8d-155">Stores the tenants supported by current deployment.</span></span> <span data-ttu-id="99d8d-156">Existem alguns locatários integrados para os usuários Enterprise, Federado, de conectividade de IM público e Anônimos.</span><span class="sxs-lookup"><span data-stu-id="99d8d-156">There some build-in tenants for Enterprise user, Federated User, public IM connectivity user, and Anonymous users.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="99d8d-157"><a href="lync-server-2013-useragentdef-table.md">Tabela UserAgentDef no Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="99d8d-157"><a href="lync-server-2013-useragentdef-table.md">UserAgentDef table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="99d8d-158">Mapeia os identificadores de agente do usuário aos nomes descritivos dos agentes.</span><span class="sxs-lookup"><span data-stu-id="99d8d-158">Maps user agent identifiers to the agent’s descriptive names.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="99d8d-159"><a href="lync-server-2013-users-table.md">Tabela Users no Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="99d8d-159"><a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="99d8d-160">Armazena o os URIs de usuários que tenham participado em sessões gravadas ou arquivadas neste banco de dados.</span><span class="sxs-lookup"><span data-stu-id="99d8d-160">Stores the user URIs of users who have participated in sessions recorded or archived in this database.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="99d8d-161"><a href="lync-server-2013-userstatistics-table.md">Tabela userstatistics no Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="99d8d-161"><a href="lync-server-2013-userstatistics-table.md">UserStatistics table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="99d8d-162">Stores information about an individual user’s usage of the system.</span><span class="sxs-lookup"><span data-stu-id="99d8d-162">Stores information about an individual user’s usage of the system.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="tables-specific-to-conference-cdr-records"></a><span data-ttu-id="99d8d-163">Tabelas Específicas para Registros de CDR de Conferências</span><span class="sxs-lookup"><span data-stu-id="99d8d-163">Tables Specific to Conference CDR Records</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="99d8d-164">Tabela</span><span class="sxs-lookup"><span data-stu-id="99d8d-164">Table</span></span></th>
<th><span data-ttu-id="99d8d-165">Descrição</span><span class="sxs-lookup"><span data-stu-id="99d8d-165">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="99d8d-166"><a href="lync-server-2013-conferences-table.md">Tabela de conferências no Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="99d8d-166"><a href="lync-server-2013-conferences-table.md">Conferences table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="99d8d-167">Armazena informações sobre todas as conferências que foram arquivadas ou que tiveram seus detalhes gravados, incluindo ConferenceUI e hora de início e término.</span><span class="sxs-lookup"><span data-stu-id="99d8d-167">Stores information about all conferences that were archived or whose details were recorded, including ConferenceURI, and start and end time.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="99d8d-168"><a href="lync-server-2013-conferencesessiondetails-table.md">Tabela ConferenceSessionDetails no Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="99d8d-168"><a href="lync-server-2013-conferencesessiondetails-table.md">ConferenceSessionDetails table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="99d8d-169">Armazena informações sobre todas as sessões de conferência baseada em SIP, incluindo hora de início e término, ID de usuário, código de resposta e ID de diagnóstico para cada sessão.</span><span class="sxs-lookup"><span data-stu-id="99d8d-169">Stores information about every SIP-based conference session, including start and end time, user ID, response code, and diagnostic ID for each session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="99d8d-170"><a href="lync-server-2013-focusjoinsandleaves-table.md">Tabela FocusJoinsAndLeaves no Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="99d8d-170"><a href="lync-server-2013-focusjoinsandleaves-table.md">FocusJoinsAndLeaves table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="99d8d-171">Armazena informações sobre entradas e saídas de conferências, incluindo as funções e versões de cliente dos usuários.</span><span class="sxs-lookup"><span data-stu-id="99d8d-171">Stores information about conference joins and leaves, including users’ role and client version.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="99d8d-172"><a href="lync-server-2013-mcujoinsandleaves-table.md">Tabela McuJoinsAndLeaves no Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="99d8d-172"><a href="lync-server-2013-mcujoinsandleaves-table.md">McuJoinsAndLeaves table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="99d8d-173">Armazena informações sobre os Servidores de Conferência A/V que estão envolvidos em uma conferência e os horários de ingresso e saída de usuário.</span><span class="sxs-lookup"><span data-stu-id="99d8d-173">Stores information about the A/V Conferencing Servers that are involved in a conference and the user join and leave times.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="tables-for-messages-in-im-conferences"></a><span data-ttu-id="99d8d-174">Tabelas para Mensagens em Conferências IM</span><span class="sxs-lookup"><span data-stu-id="99d8d-174">Tables for Messages in IM Conferences</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="99d8d-175">Tabela</span><span class="sxs-lookup"><span data-stu-id="99d8d-175">Table</span></span></th>
<th><span data-ttu-id="99d8d-176">Descrição</span><span class="sxs-lookup"><span data-stu-id="99d8d-176">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="99d8d-177"><a href="lync-server-2013-conferencemessagecount-table.md">Tabela ConferenceMessageCount no Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="99d8d-177"><a href="lync-server-2013-conferencemessagecount-table.md">ConferenceMessageCount table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="99d8d-178">Armazena, para cada conferência IM, o número de mensagem que foram enviadas por cada usuário.</span><span class="sxs-lookup"><span data-stu-id="99d8d-178">For each IM conference, stores the number of messages that were sent by each user.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="99d8d-179"><a href="lync-server-2013-imreportsummary-table.md">Tabela IMReportSummary no Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="99d8d-179"><a href="lync-server-2013-imreportsummary-table.md">IMReportSummary table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="99d8d-180">Provides an overall report on the instant messaging sessions held in an organization.</span><span class="sxs-lookup"><span data-stu-id="99d8d-180">Provides an overall report on the instant messaging sessions held in an organization.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="tables-for-peer-to-peer-sessions"></a><span data-ttu-id="99d8d-181">Tabelas para Sessões Ponto-a-Ponto</span><span class="sxs-lookup"><span data-stu-id="99d8d-181">Tables for Peer-to-Peer Sessions</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="99d8d-182">Tabela</span><span class="sxs-lookup"><span data-stu-id="99d8d-182">Table</span></span></th>
<th><span data-ttu-id="99d8d-183">Descrição</span><span class="sxs-lookup"><span data-stu-id="99d8d-183">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="99d8d-184"><a href="lync-server-2013-sessiondetails-table.md">Tabela SessionDetails no Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="99d8d-184"><a href="lync-server-2013-sessiondetails-table.md">SessionDetails table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="99d8d-185">Armazena informações sobre cada sessão ponto-a-ponto, incluindo horário de início e término, ID de usuário, código de resposta e a contagem de mensagem para cada usuário.</span><span class="sxs-lookup"><span data-stu-id="99d8d-185">Stores information about every peer-to-peer session, including start and end time, user ID, response code, and message count for each user.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="99d8d-186"><a href="lync-server-2013-filetransfers-table.md">Tabela filetransfers no Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="99d8d-186"><a href="lync-server-2013-filetransfers-table.md">FileTransfers table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="99d8d-187">Armazena informações sobre sessões de transferência de arquivo, incluindo nome de arquivo e resultado (aceita, rejeitada ou cancelada).</span><span class="sxs-lookup"><span data-stu-id="99d8d-187">Stores information about file transfer sessions, including file name and result (accepted, rejected, or canceled).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="99d8d-188"><a href="lync-server-2013-media-table.md">Tabela de mídia no Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="99d8d-188"><a href="lync-server-2013-media-table.md">Media table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="99d8d-189">Armazena informações sobre os diferentes tipos de mídia envolvidos em sessões ponto-a-ponto.</span><span class="sxs-lookup"><span data-stu-id="99d8d-189">Stores information about the different media types involved in peer-to-peer sessions.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="table-for-voip-call-details"></a><span data-ttu-id="99d8d-190">Tabela para Detalhes de Chamadas VoIP</span><span class="sxs-lookup"><span data-stu-id="99d8d-190">Table for VoIP Call Details</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="99d8d-191">Tabela</span><span class="sxs-lookup"><span data-stu-id="99d8d-191">Table</span></span></th>
<th><span data-ttu-id="99d8d-192">Descrição</span><span class="sxs-lookup"><span data-stu-id="99d8d-192">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="99d8d-193"><a href="lync-server-2013-voipdetails-table.md">Tabela VoipDetails no Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="99d8d-193"><a href="lync-server-2013-voipdetails-table.md">VoipDetails table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="99d8d-194">Armazena, para cada chamada VoIP/PSTN de duas partes, informações sobre a chamada, tais como ID de telefone do telefone VoIP, gateway usado e qual parte desconectou.</span><span class="sxs-lookup"><span data-stu-id="99d8d-194">For each two-party VoIP/PSTN call, stores information about the call, such as the phone ID of VoIP phone, gateway used, and which party disconnected.</span></span> <span data-ttu-id="99d8d-195">Refere-se à <a href="lync-server-2013-sessiondetails-table.md">tabela SessionDetails no Lync Server 2013</a> para horários de início/término de chamadas e código de resposta.</span><span class="sxs-lookup"><span data-stu-id="99d8d-195">Refers to the <a href="lync-server-2013-sessiondetails-table.md">SessionDetails table in Lync Server 2013</a> for call start/end times and response code.</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="99d8d-196">Se uma parte em uma chamada é um usuário VoIP ou se um Servidor de Mediação esteve envolvido na chamada, um registro será criado nesta tabela.</span><span class="sxs-lookup"><span data-stu-id="99d8d-196">If one party on a call is a VoIP user or if a Mediation Server was involved in the call, a record will be created in this table.</span></span> <span data-ttu-id="99d8d-197">As informações sobre chamadas VoIP/VoIP que não envolvem um telefone PSTN (rede telefônica pública comutada) é capturadas na <A href="lync-server-2013-sessiondetails-table.md">tabela SessionDetails no Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="99d8d-197">Information about VoIP/VoIP calls not involving a public switched telephone network (PSTN) phone is captured in the <A href="lync-server-2013-sessiondetails-table.md">SessionDetails table in Lync Server 2013</A>.</span></span>


</div></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="table-for-e9-1-1-call-auditing"></a><span data-ttu-id="99d8d-198">Tabela para Auditoria de Chamada E9-1-1</span><span class="sxs-lookup"><span data-stu-id="99d8d-198">Table for E9-1-1 Call Auditing</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="99d8d-199">Tabela</span><span class="sxs-lookup"><span data-stu-id="99d8d-199">Table</span></span></th>
<th><span data-ttu-id="99d8d-200">Descrição</span><span class="sxs-lookup"><span data-stu-id="99d8d-200">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="99d8d-201"><a href="lync-server-2013-locations-table.md">Tabela Locations no Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="99d8d-201"><a href="lync-server-2013-locations-table.md">Locations table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="99d8d-202">Armazena, para cada chamada de emergência, tal como uma chamada Enhanced 9-1-1 (E9-1-1), informações locais sobre a chamada.</span><span class="sxs-lookup"><span data-stu-id="99d8d-202">For each emergency call, such as an Enhanced 9-1-1 (E9-1-1) call, stores location information about the call.</span></span> <span data-ttu-id="99d8d-203">Refere-se à <a href="lync-server-2013-sessiondetails-table.md">tabela SessionDetails no Lync Server 2013</a> para horários de início/término de chamadas e código de resposta.</span><span class="sxs-lookup"><span data-stu-id="99d8d-203">Refers to the <a href="lync-server-2013-sessiondetails-table.md">SessionDetails table in Lync Server 2013</a> for call start/end times and response code.</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="99d8d-p105">Esta tabela contém apenas o blob de local para a chamada E9-1-1. Consulte a tabela SessionDetails para outras informações detalhadas sobre a chamada.</span><span class="sxs-lookup"><span data-stu-id="99d8d-p105">This table only contains the location blob for the E9-1-1 call. Refers to the SessionDetails table for other detailed information about the call.</span></span>


</div></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="tables-for-troubleshooting"></a><span data-ttu-id="99d8d-206">Tabelas para Resolução de Problemas</span><span class="sxs-lookup"><span data-stu-id="99d8d-206">Tables for Troubleshooting</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="99d8d-207">Tabela</span><span class="sxs-lookup"><span data-stu-id="99d8d-207">Table</span></span></th>
<th><span data-ttu-id="99d8d-208">Descrição</span><span class="sxs-lookup"><span data-stu-id="99d8d-208">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="99d8d-209"><a href="lync-server-2013-application-table.md">Tabela de aplicativos no Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="99d8d-209"><a href="lync-server-2013-application-table.md">Application table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="99d8d-210">Armazena informações sobre vários processos no Lync Server 2013 que estão envolvidos em roteamento e conexões.</span><span class="sxs-lookup"><span data-stu-id="99d8d-210">Stores information about various processes within Lync Server 2013 that are involved in routing and connections.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="99d8d-211"><a href="lync-server-2013-calltype-table.md">Tabela CallType no Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="99d8d-211"><a href="lync-server-2013-calltype-table.md">CallType table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="99d8d-212">Armazena informações sobre tipos de chamada, tais como "áudio", "IM", "áudio e vídeo" e "compartilhamento de aplicativos".</span><span class="sxs-lookup"><span data-stu-id="99d8d-212">Stores information about types of the call, such as, “audio”, “Instant Messaging”, “audio and video” and “application sharing”.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="99d8d-213"><a href="lync-server-2013-errorcategory-table.md">Tabela ErrorCategory no Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="99d8d-213"><a href="lync-server-2013-errorcategory-table.md">ErrorCategory table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="99d8d-214">Armazena o nome amigável para cada classificação de diagnóstico 2013 do Microsoft Lync Server.</span><span class="sxs-lookup"><span data-stu-id="99d8d-214">Stores the friendly name for each Microsoft Lync Server 2013 diagnostic classification.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="99d8d-215"><a href="lync-server-2013-errordef-table.md">Tabela ErrorDef no Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="99d8d-215"><a href="lync-server-2013-errordef-table.md">ErrorDef table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="99d8d-216">Armazena informações sobre tipos de erros e suas definições.</span><span class="sxs-lookup"><span data-stu-id="99d8d-216">Stores information about types of errors and their definitions.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="99d8d-217"><a href="lync-server-2013-errorreport-table.md">Tabela ErrorReport no Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="99d8d-217"><a href="lync-server-2013-errorreport-table.md">ErrorReport table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="99d8d-218">Armazena informações sobre erros que ocorreram.</span><span class="sxs-lookup"><span data-stu-id="99d8d-218">Stores information about errors that have occurred.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="99d8d-219"><a href="lync-server-2013-progressreport-table.md">Tabela ProgressReport no Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="99d8d-219"><a href="lync-server-2013-progressreport-table.md">ProgressReport table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="99d8d-220">Armazena informações sobre os relatórios de progresso de várias etapas envolvidas nos processos do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="99d8d-220">Stores information about the progress reports of various steps involved in Lync Server 2013 processes.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="99d8d-221">As tabelas na lista a seguir são usadas internamente pelo Lync Server.</span><span class="sxs-lookup"><span data-stu-id="99d8d-221">The tables in the following list are used internally by Lync Server.</span></span> <span data-ttu-id="99d8d-222">Seus detalhes não são descritos neste documento.</span><span class="sxs-lookup"><span data-stu-id="99d8d-222">Their details are not described in this document.</span></span>

</div>

<div>

## <a name="tables-for-internal-use-by-lync-server"></a><span data-ttu-id="99d8d-223">Tabelas para Uso Interno do Lync Server</span><span class="sxs-lookup"><span data-stu-id="99d8d-223">Tables for Internal Use by Lync Server</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="99d8d-224">Tabela</span><span class="sxs-lookup"><span data-stu-id="99d8d-224">Table</span></span></th>
<th><span data-ttu-id="99d8d-225">Descrição</span><span class="sxs-lookup"><span data-stu-id="99d8d-225">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="99d8d-226"><strong>DbConfigDateTime</strong></span><span class="sxs-lookup"><span data-stu-id="99d8d-226"><strong>DbConfigDateTime</strong></span></span></p></td>
<td><p><span data-ttu-id="99d8d-227">Apenas para uso interno.</span><span class="sxs-lookup"><span data-stu-id="99d8d-227">For internal use only.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="99d8d-228"><strong>DbConfigInt</strong></span><span class="sxs-lookup"><span data-stu-id="99d8d-228"><strong>DbConfigInt</strong></span></span></p></td>
<td><p><span data-ttu-id="99d8d-229">Apenas para uso interno.</span><span class="sxs-lookup"><span data-stu-id="99d8d-229">For internal use only.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="99d8d-230"><strong>DbErrorMessage</strong></span><span class="sxs-lookup"><span data-stu-id="99d8d-230"><strong>DbErrorMessage</strong></span></span></p></td>
<td><p><span data-ttu-id="99d8d-231">Apenas para uso interno.</span><span class="sxs-lookup"><span data-stu-id="99d8d-231">For internal use only.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="99d8d-232"><strong>Tabela FrontEnd</strong></span><span class="sxs-lookup"><span data-stu-id="99d8d-232"><strong>FrontEnd Table</strong></span></span></p></td>
<td><p><span data-ttu-id="99d8d-233">Apenas para uso interno.</span><span class="sxs-lookup"><span data-stu-id="99d8d-233">For internal use only.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="99d8d-234"><strong>MSMQProcessing Table</strong></span><span class="sxs-lookup"><span data-stu-id="99d8d-234"><strong>MSMQProcessing Table</strong></span></span></p></td>
<td><p><span data-ttu-id="99d8d-235">Apenas para uso interno.</span><span class="sxs-lookup"><span data-stu-id="99d8d-235">For internal use only.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="99d8d-236"><strong>SummaryTableConfiguration</strong></span><span class="sxs-lookup"><span data-stu-id="99d8d-236"><strong>SummaryTableConfiguration</strong></span></span></p></td>
<td><p><span data-ttu-id="99d8d-237">Apenas para uso interno.</span><span class="sxs-lookup"><span data-stu-id="99d8d-237">For internal use only.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="99d8d-238"><strong>Syndicators Table</strong></span><span class="sxs-lookup"><span data-stu-id="99d8d-238"><strong>Syndicators Table</strong></span></span></p></td>
<td><p><span data-ttu-id="99d8d-239">Apenas para uso interno.</span><span class="sxs-lookup"><span data-stu-id="99d8d-239">For internal use only.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="99d8d-240"><strong>SyndicatorsTenantMap Table</strong></span><span class="sxs-lookup"><span data-stu-id="99d8d-240"><strong>SyndicatorsTenantMap Table</strong></span></span></p></td>
<td><p><span data-ttu-id="99d8d-241">Apenas para uso interno.</span><span class="sxs-lookup"><span data-stu-id="99d8d-241">For internal use only.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="99d8d-242"><strong>Tabela Tarefa</strong></span><span class="sxs-lookup"><span data-stu-id="99d8d-242"><strong>Task Table</strong></span></span></p></td>
<td><p><span data-ttu-id="99d8d-243">Apenas para uso interno.</span><span class="sxs-lookup"><span data-stu-id="99d8d-243">For internal use only.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="99d8d-244"><strong>UserStatistics</strong></span><span class="sxs-lookup"><span data-stu-id="99d8d-244"><strong>UserStatistics</strong></span></span></p></td>
<td><p><span data-ttu-id="99d8d-245">Apenas para uso interno.</span><span class="sxs-lookup"><span data-stu-id="99d8d-245">For internal use only.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="99d8d-246"><strong>UsageSummary_UQ</strong></span><span class="sxs-lookup"><span data-stu-id="99d8d-246"><strong>UsageSummary_UQ</strong></span></span></p></td>
<td><p><span data-ttu-id="99d8d-247">Apenas para uso interno.</span><span class="sxs-lookup"><span data-stu-id="99d8d-247">For internal use only.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="99d8d-248"><strong>UsageSummary</strong></span><span class="sxs-lookup"><span data-stu-id="99d8d-248"><strong>UsageSummary</strong></span></span></p></td>
<td><p><span data-ttu-id="99d8d-249">Apenas para uso interno.</span><span class="sxs-lookup"><span data-stu-id="99d8d-249">For internal use only.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="99d8d-250"><strong>DaylightSavingYears</strong></span><span class="sxs-lookup"><span data-stu-id="99d8d-250"><strong>DaylightSavingYears</strong></span></span></p></td>
<td><p><span data-ttu-id="99d8d-251">Apenas para uso interno.</span><span class="sxs-lookup"><span data-stu-id="99d8d-251">For internal use only.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="99d8d-252"><strong>TimeZoneConfiguration</strong></span><span class="sxs-lookup"><span data-stu-id="99d8d-252"><strong>TimeZoneConfiguration</strong></span></span></p></td>
<td><p><span data-ttu-id="99d8d-253">Apenas para uso interno.</span><span class="sxs-lookup"><span data-stu-id="99d8d-253">For internal use only.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="99d8d-254"><strong>TimeZones</strong></span><span class="sxs-lookup"><span data-stu-id="99d8d-254"><strong>TimeZones</strong></span></span></p></td>
<td><p><span data-ttu-id="99d8d-255">For internal use only.</span><span class="sxs-lookup"><span data-stu-id="99d8d-255">For internal use only.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="99d8d-256"><strong>FailureSummary_UQ</strong></span><span class="sxs-lookup"><span data-stu-id="99d8d-256"><strong>FailureSummary_UQ</strong></span></span></p></td>
<td><p><span data-ttu-id="99d8d-257">For internal use only.</span><span class="sxs-lookup"><span data-stu-id="99d8d-257">For internal use only.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="99d8d-258"><strong>FailureSummary</strong></span><span class="sxs-lookup"><span data-stu-id="99d8d-258"><strong>FailureSummary</strong></span></span></p></td>
<td><p><span data-ttu-id="99d8d-259">For internal use only.</span><span class="sxs-lookup"><span data-stu-id="99d8d-259">For internal use only.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="99d8d-260"><strong>ServerSummary</strong></span><span class="sxs-lookup"><span data-stu-id="99d8d-260"><strong>ServerSummary</strong></span></span></p></td>
<td><p><span data-ttu-id="99d8d-261">For internal use only.</span><span class="sxs-lookup"><span data-stu-id="99d8d-261">For internal use only.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="99d8d-262"><strong>MsDiagMetaData</strong></span><span class="sxs-lookup"><span data-stu-id="99d8d-262"><strong>MsDiagMetaData</strong></span></span></p></td>
<td><p><span data-ttu-id="99d8d-263">For internal use only.</span><span class="sxs-lookup"><span data-stu-id="99d8d-263">For internal use only.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

