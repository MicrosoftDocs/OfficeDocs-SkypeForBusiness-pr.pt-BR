---
title: 'Lync Server 2013: Lista de tabelas CDR'
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
ms.openlocfilehash: b0c620eaf6b54a89604071a18f445d20816178bf
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41765429"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="list-of-cdr-tables-in-lync-server-2013"></a><span data-ttu-id="f0c70-102">Lista de tabelas do CDR no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f0c70-102">List of CDR tables in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f0c70-103">_**Tópico da última modificação:** 2012-10-18_</span><span class="sxs-lookup"><span data-stu-id="f0c70-103">_**Topic Last Modified:** 2012-10-18_</span></span>

<span data-ttu-id="f0c70-104">O esquema de banco de dados de registro de detalhes de chamadas (CDR) consiste nas tabelas a seguir.</span><span class="sxs-lookup"><span data-stu-id="f0c70-104">The call detail recording (CDR) database schema consists of the following tables.</span></span>

<div>

## <a name="static-tables"></a><span data-ttu-id="f0c70-105">Tabelas estáticas</span><span class="sxs-lookup"><span data-stu-id="f0c70-105">Static Tables</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="f0c70-106">Tabela</span><span class="sxs-lookup"><span data-stu-id="f0c70-106">Table</span></span></th>
<th><span data-ttu-id="f0c70-107">Descrição</span><span class="sxs-lookup"><span data-stu-id="f0c70-107">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f0c70-108"><a href="lync-server-2013-callpriorities-table.md">Tabela CallPriorities no Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="f0c70-108"><a href="lync-server-2013-callpriorities-table.md">CallPriorities table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="f0c70-109">Armazena a lista de prioridades de chamadas possíveis, como emergência, urgente, normal, não urgente e muito mais.</span><span class="sxs-lookup"><span data-stu-id="f0c70-109">Stores the list of possible call priorities, such as emergency, urgent, normal, non-urgent, and more.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f0c70-110"><a href="lync-server-2013-conferencejointimethresholds-table.md">Tabela ConferenceJoinTimeThresholds no Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="f0c70-110"><a href="lync-server-2013-conferencejointimethresholds-table.md">ConferenceJoinTimeThresholds table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="f0c70-111">Armazena os limites de classificação usados pelo relatório de Resumo de tempo de ingresso em conferência.</span><span class="sxs-lookup"><span data-stu-id="f0c70-111">Stores the classification boundaries used by the Conference Join Time Summary Report.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f0c70-112"><a href="lync-server-2013-deregistertype-table.md">Tabela DeRegisterType no Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="f0c70-112"><a href="lync-server-2013-deregistertype-table.md">DeRegisterType table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="f0c70-113">Armazena a lista de possíveis motivos de descadastramento do usuário, &quot;como o cliente&quot; &quot;iniciado, o&quot; &quot;registro expirou,&quot; a falha do cliente e muito mais.</span><span class="sxs-lookup"><span data-stu-id="f0c70-113">Stores the list of possible user de-register reasons, such as &quot;client initiated,&quot; &quot;registration expired,&quot; &quot;client crash,&quot; and more.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f0c70-114"><a href="lync-server-2013-medialist-table.md">Tabela MediaList no Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="f0c70-114"><a href="lync-server-2013-medialist-table.md">MediaList table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="f0c70-115">Armazena a lista de tipos de mídia que podem gerar entradas no banco de dados (por exemplo, mensagens instantâneas, áudio, vídeo e transferência de arquivos).</span><span class="sxs-lookup"><span data-stu-id="f0c70-115">Stores the list of media types that can generate entries in the database (for example, IM, audio, video, and file transfer).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f0c70-116"><a href="lync-server-2013-purgesettings-table.md">Tabela PurgeSettings no Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="f0c70-116"><a href="lync-server-2013-purgesettings-table.md">PurgeSettings table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="f0c70-117">Armazena informações que especificam se (e quando) registros de detalhes de chamadas desatualizadas serão automaticamente excluídos do banco de dados CDR.</span><span class="sxs-lookup"><span data-stu-id="f0c70-117">Stores information that specifies if (and when) outdated call detail records will automatically be deleted from the CDR database.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f0c70-118"><a href="lync-server-2013-roles-table.md">Tabela Roles no Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="f0c70-118"><a href="lync-server-2013-roles-table.md">Roles table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="f0c70-119">Armazena a lista de possíveis funções de conferência (por exemplo, participante e apresentador).</span><span class="sxs-lookup"><span data-stu-id="f0c70-119">Stores the list of possible conference roles (for example, attendee and presenter).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f0c70-120"><a href="lync-server-2013-sipresponsemetadata-table.md">Tabela SIPResponseMetaData no Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="f0c70-120"><a href="lync-server-2013-sipresponsemetadata-table.md">SIPResponseMetaData table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="f0c70-121">Armazena uma lista de códigos de resposta SIP e a classificação e definição de cada um desses códigos.</span><span class="sxs-lookup"><span data-stu-id="f0c70-121">Stores a list of SIP response codes and the classification and definition of each of those codes.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="supporting-tables"></a><span data-ttu-id="f0c70-122">Tabelas de suporte</span><span class="sxs-lookup"><span data-stu-id="f0c70-122">Supporting Tables</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="f0c70-123">Tabela</span><span class="sxs-lookup"><span data-stu-id="f0c70-123">Table</span></span></th>
<th><span data-ttu-id="f0c70-124">Descrição</span><span class="sxs-lookup"><span data-stu-id="f0c70-124">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f0c70-125"><a href="lync-server-2013-clientversions-table.md">Tabela ClientVersions no Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="f0c70-125"><a href="lync-server-2013-clientversions-table.md">ClientVersions table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="f0c70-126">Armazena os clientes (o tipo de cliente e o número da versão) de cada cliente envolvido em uma chamada com informações capturadas nesse banco de dados.</span><span class="sxs-lookup"><span data-stu-id="f0c70-126">Stores the clients (both client type and version number) of each client involved in a call with information captured in this database.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f0c70-127"><a href="lync-server-2013-conferenceuris-table.md">Tabela ConferenceUris no Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="f0c70-127"><a href="lync-server-2013-conferenceuris-table.md">ConferenceUris table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="f0c70-128">Armazena uma lista de ConferenceURIs que são usadas em chamadas relacionadas à conferência.</span><span class="sxs-lookup"><span data-stu-id="f0c70-128">Stores a list of ConferenceURIs that are used in conference related calls.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f0c70-129"><a href="lync-server-2013-contenttypes-table.md">Tabela ContentTypes no Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="f0c70-129"><a href="lync-server-2013-contenttypes-table.md">ContentTypes table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="f0c70-130">Armazena uma lista de tipos de conteúdo de protocolo SIP que são usados em chamadas ponto a ponto e em chamadas em conferência.</span><span class="sxs-lookup"><span data-stu-id="f0c70-130">Stores a list of Session Initiation Protocol (SIP) content types that are used in both peer-to-peer calls and conference calls.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f0c70-131"><a href="lync-server-2013-devices-table.md">Tabela Devices no Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="f0c70-131"><a href="lync-server-2013-devices-table.md">Devices table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="f0c70-132">Armazena uma lista de dispositivos, incluindo o fabricante, a versão de hardware e o endereço MAC.</span><span class="sxs-lookup"><span data-stu-id="f0c70-132">Stores a list of devices, including their manufacturer, hardware version, and MAC address.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f0c70-133"><a href="lync-server-2013-dialogs-table.md">Tabela Dialogs no Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="f0c70-133"><a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="f0c70-134">Armazena informações sobre a ID da caixa de diálogo para cada sessão do banco de dados.</span><span class="sxs-lookup"><span data-stu-id="f0c70-134">Stores information about the Dialog ID for each session in the database.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f0c70-135"><a href="lync-server-2013-edgeservers-table.md">Tabela EdgeServers no Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="f0c70-135"><a href="lync-server-2013-edgeservers-table.md">EdgeServers table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="f0c70-136">Armazena uma lista de servidores de borda que são usados para chamadas externas.</span><span class="sxs-lookup"><span data-stu-id="f0c70-136">Stores a list of Edge Servers that are used for external calls.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f0c70-137"><a href="lync-server-2013-gateways-table.md">Tabela Gateways no Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="f0c70-137"><a href="lync-server-2013-gateways-table.md">Gateways table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="f0c70-138">Armazena uma lista de gateways que são usados para chamadas de protocolo de voz por Internet (VoIP).</span><span class="sxs-lookup"><span data-stu-id="f0c70-138">Stores a list of Gateways that are used for Voice over Internet Protocol (VoIP) calls.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f0c70-139"><a href="lync-server-2013-hardwareversions-table.md">Tabela HardwareVersions no Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="f0c70-139"><a href="lync-server-2013-hardwareversions-table.md">HardwareVersions table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="f0c70-140">Armazena uma lista de versões de hardware de dispositivos (telefone de mesa).</span><span class="sxs-lookup"><span data-stu-id="f0c70-140">Stores a list of hardware versions of devices (desk phone).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f0c70-141"><a href="lync-server-2013-manufacturers-table.md">Tabela Manufacturers no Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="f0c70-141"><a href="lync-server-2013-manufacturers-table.md">Manufacturers table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="f0c70-142">Armazena uma lista de fabricantes de dispositivos (telefone de mesa).</span><span class="sxs-lookup"><span data-stu-id="f0c70-142">Stores a list of manufacturers of devices (desk phone).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f0c70-143"><a href="lync-server-2013-mcus-table.md">Tabela Mcus no Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="f0c70-143"><a href="lync-server-2013-mcus-table.md">Mcus table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="f0c70-144">Armazena informações sobre os vários servidores de conferência A/V e seus URIs.</span><span class="sxs-lookup"><span data-stu-id="f0c70-144">Stores information about the various A/V Conferencing Servers and their URIs.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f0c70-145"><a href="lync-server-2013-mediationservers-table.md">Tabela MediationServers no Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="f0c70-145"><a href="lync-server-2013-mediationservers-table.md">MediationServers table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="f0c70-146">Armazena uma lista de servidores de mediação que são usados para chamadas VoIP.</span><span class="sxs-lookup"><span data-stu-id="f0c70-146">Stores a list of Mediation Servers that are used for VoIP calls.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f0c70-147"><a href="lync-server-2013-phones-table.md">Tabela Phones no Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="f0c70-147"><a href="lync-server-2013-phones-table.md">Phones table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="f0c70-148">Armazena todos os números de telefone usados em chamadas VoIP que foram arquivadas ou cujos detalhes da chamada foram registrados.</span><span class="sxs-lookup"><span data-stu-id="f0c70-148">Stores all the phone numbers used in VoIP calls that were archived or whose call details were recorded.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f0c70-149"><a href="lync-server-2013-pools-table.md">Tabela Pools no Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="f0c70-149"><a href="lync-server-2013-pools-table.md">Pools table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="f0c70-150">Armazena os nomes do pool no qual as mensagens INSTANTÂNEAs são capturadas.</span><span class="sxs-lookup"><span data-stu-id="f0c70-150">Stores the names of the pool on which IM messages are captured.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f0c70-151"><a href="lync-server-2013-servers-table.md">Tabela de servidores no Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="f0c70-151"><a href="lync-server-2013-servers-table.md">Servers table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="f0c70-152">Armazena o nome dos servidores envolvidos nas chamadas.</span><span class="sxs-lookup"><span data-stu-id="f0c70-152">Stores the name of servers involved in calls.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f0c70-153"><a href="lync-server-2013-tenants-table.md">Tabela Tenants no Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="f0c70-153"><a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="f0c70-154">Armazena os locatários compatíveis com a implantação atual.</span><span class="sxs-lookup"><span data-stu-id="f0c70-154">Stores the tenants supported by current deployment.</span></span> <span data-ttu-id="f0c70-155">Há alguns locatários de compilação para usuários corporativos, usuários federados, usuários de conectividade de mensagens de chat públicas e usuários anônimos.</span><span class="sxs-lookup"><span data-stu-id="f0c70-155">There some build-in tenants for Enterprise user, Federated User, public IM connectivity user, and Anonymous users.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f0c70-156"><a href="lync-server-2013-useragentdef-table.md">Tabela UserAgentDef no Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="f0c70-156"><a href="lync-server-2013-useragentdef-table.md">UserAgentDef table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="f0c70-157">Mapeia identificadores de agente de usuário para os nomes descritivos do agente.</span><span class="sxs-lookup"><span data-stu-id="f0c70-157">Maps user agent identifiers to the agent’s descriptive names.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f0c70-158"><a href="lync-server-2013-users-table.md">Tabela Users no Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="f0c70-158"><a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="f0c70-159">Armazena o usuário URIs de usuários que participaram de sessões registradas ou arquivadas neste banco de dados.</span><span class="sxs-lookup"><span data-stu-id="f0c70-159">Stores the user URIs of users who have participated in sessions recorded or archived in this database.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f0c70-160"><a href="lync-server-2013-userstatistics-table.md">Tabela userstatistics no Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="f0c70-160"><a href="lync-server-2013-userstatistics-table.md">UserStatistics table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="f0c70-161">Armazena informações sobre o uso de um usuário individual do sistema.</span><span class="sxs-lookup"><span data-stu-id="f0c70-161">Stores information about an individual user’s usage of the system.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="tables-specific-to-conference-cdr-records"></a><span data-ttu-id="f0c70-162">Tabelas específicas para registros de CDR em conferência</span><span class="sxs-lookup"><span data-stu-id="f0c70-162">Tables Specific to Conference CDR Records</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="f0c70-163">Tabela</span><span class="sxs-lookup"><span data-stu-id="f0c70-163">Table</span></span></th>
<th><span data-ttu-id="f0c70-164">Descrição</span><span class="sxs-lookup"><span data-stu-id="f0c70-164">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f0c70-165"><a href="lync-server-2013-conferences-table.md">Tabela Conferences no Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="f0c70-165"><a href="lync-server-2013-conferences-table.md">Conferences table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="f0c70-166">Armazena informações sobre todas as conferências que foram arquivadas ou cujos detalhes foram registrados, incluindo ConferenceURI e hora de início e de término.</span><span class="sxs-lookup"><span data-stu-id="f0c70-166">Stores information about all conferences that were archived or whose details were recorded, including ConferenceURI, and start and end time.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f0c70-167"><a href="lync-server-2013-conferencesessiondetails-table.md">Tabela ConferenceSessionDetails no Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="f0c70-167"><a href="lync-server-2013-conferencesessiondetails-table.md">ConferenceSessionDetails table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="f0c70-168">Armazena informações sobre cada sessão de conferência baseada em SIP, incluindo hora de início e de término, ID de usuário, código de resposta e identificação de diagnóstico para cada sessão.</span><span class="sxs-lookup"><span data-stu-id="f0c70-168">Stores information about every SIP-based conference session, including start and end time, user ID, response code, and diagnostic ID for each session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f0c70-169"><a href="lync-server-2013-focusjoinsandleaves-table.md">Tabela FocusJoinsAndLeaves no Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="f0c70-169"><a href="lync-server-2013-focusjoinsandleaves-table.md">FocusJoinsAndLeaves table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="f0c70-170">Armazena informações sobre junções e folhas de conferência, incluindo a função do usuário e a versão do cliente.</span><span class="sxs-lookup"><span data-stu-id="f0c70-170">Stores information about conference joins and leaves, including users’ role and client version.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f0c70-171"><a href="lync-server-2013-mcujoinsandleaves-table.md">Tabela McuJoinsAndLeaves no Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="f0c70-171"><a href="lync-server-2013-mcujoinsandleaves-table.md">McuJoinsAndLeaves table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="f0c70-172">Armazena informações sobre os servidores de conferência A/V envolvidos em uma conferência e o usuário ingressa e sai do tempo.</span><span class="sxs-lookup"><span data-stu-id="f0c70-172">Stores information about the A/V Conferencing Servers that are involved in a conference and the user join and leave times.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="tables-for-messages-in-im-conferences"></a><span data-ttu-id="f0c70-173">Tabelas de mensagens em conferências de mensagens INSTANTÂNEAs</span><span class="sxs-lookup"><span data-stu-id="f0c70-173">Tables for Messages in IM Conferences</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="f0c70-174">Tabela</span><span class="sxs-lookup"><span data-stu-id="f0c70-174">Table</span></span></th>
<th><span data-ttu-id="f0c70-175">Descrição</span><span class="sxs-lookup"><span data-stu-id="f0c70-175">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f0c70-176"><a href="lync-server-2013-conferencemessagecount-table.md">Tabela ConferenceMessageCount no Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="f0c70-176"><a href="lync-server-2013-conferencemessagecount-table.md">ConferenceMessageCount table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="f0c70-177">Para cada conferência de mensagem instantânea, armazena o número de mensagens enviadas por cada usuário.</span><span class="sxs-lookup"><span data-stu-id="f0c70-177">For each IM conference, stores the number of messages that were sent by each user.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f0c70-178"><a href="lync-server-2013-imreportsummary-table.md">Tabela IMReportSummary no Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="f0c70-178"><a href="lync-server-2013-imreportsummary-table.md">IMReportSummary table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="f0c70-179">Fornece um relatório geral sobre as sessões de mensagens instantâneas contidas em uma organização.</span><span class="sxs-lookup"><span data-stu-id="f0c70-179">Provides an overall report on the instant messaging sessions held in an organization.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="tables-for-peer-to-peer-sessions"></a><span data-ttu-id="f0c70-180">Tabelas para sessões ponto a ponto</span><span class="sxs-lookup"><span data-stu-id="f0c70-180">Tables for Peer-to-Peer Sessions</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="f0c70-181">Tabela</span><span class="sxs-lookup"><span data-stu-id="f0c70-181">Table</span></span></th>
<th><span data-ttu-id="f0c70-182">Descrição</span><span class="sxs-lookup"><span data-stu-id="f0c70-182">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f0c70-183"><a href="lync-server-2013-sessiondetails-table.md">Tabela SessionDetails no Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="f0c70-183"><a href="lync-server-2013-sessiondetails-table.md">SessionDetails table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="f0c70-184">Armazena informações sobre cada sessão ponto a ponto, incluindo a hora de início e de término, a ID de usuário, o código de resposta e a contagem de mensagens para cada usuário.</span><span class="sxs-lookup"><span data-stu-id="f0c70-184">Stores information about every peer-to-peer session, including start and end time, user ID, response code, and message count for each user.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f0c70-185"><a href="lync-server-2013-filetransfers-table.md">Tabela FileTransfers no Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="f0c70-185"><a href="lync-server-2013-filetransfers-table.md">FileTransfers table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="f0c70-186">Armazena informações sobre sessões de transferência de arquivos, incluindo o resultado e o resultado (aceito, rejeitado ou cancelado).</span><span class="sxs-lookup"><span data-stu-id="f0c70-186">Stores information about file transfer sessions, including file name and result (accepted, rejected, or canceled).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f0c70-187"><a href="lync-server-2013-media-table.md">Tabela Media no Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="f0c70-187"><a href="lync-server-2013-media-table.md">Media table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="f0c70-188">Armazena informações sobre os diferentes tipos de mídia envolvidos em sessões ponto a ponto.</span><span class="sxs-lookup"><span data-stu-id="f0c70-188">Stores information about the different media types involved in peer-to-peer sessions.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="table-for-voip-call-details"></a><span data-ttu-id="f0c70-189">Tabela para detalhes da chamada VoIP</span><span class="sxs-lookup"><span data-stu-id="f0c70-189">Table for VoIP Call Details</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="f0c70-190">Tabela</span><span class="sxs-lookup"><span data-stu-id="f0c70-190">Table</span></span></th>
<th><span data-ttu-id="f0c70-191">Descrição</span><span class="sxs-lookup"><span data-stu-id="f0c70-191">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f0c70-192"><a href="lync-server-2013-voipdetails-table.md">Tabela VoipDetails no Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="f0c70-192"><a href="lync-server-2013-voipdetails-table.md">VoipDetails table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="f0c70-193">Para cada chamada VoIP/PSTN de dois participantes, armazena informações sobre a chamada, como a ID do telefone de VoIP, o gateway usado e a parte desconectada.</span><span class="sxs-lookup"><span data-stu-id="f0c70-193">For each two-party VoIP/PSTN call, stores information about the call, such as the phone ID of VoIP phone, gateway used, and which party disconnected.</span></span> <span data-ttu-id="f0c70-194">Refere-se à <a href="lync-server-2013-sessiondetails-table.md">tabela SessionDetails no Lync Server 2013</a> para tempo de início/término e código de resposta de chamada.</span><span class="sxs-lookup"><span data-stu-id="f0c70-194">Refers to the <a href="lync-server-2013-sessiondetails-table.md">SessionDetails table in Lync Server 2013</a> for call start/end times and response code.</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="f0c70-195">Se um participante de uma chamada for um usuário de VoIP ou se um servidor de mediação estiver envolvido na chamada, um registro será criado nessa tabela.</span><span class="sxs-lookup"><span data-stu-id="f0c70-195">If one party on a call is a VoIP user or if a Mediation Server was involved in the call, a record will be created in this table.</span></span> <span data-ttu-id="f0c70-196">As informações sobre chamadas VoIP/VoIP que não envolvem um telefone PSTN (rede telefônica pública comutada) são capturadas na <A href="lync-server-2013-sessiondetails-table.md">tabela SessionDetails no Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="f0c70-196">Information about VoIP/VoIP calls not involving a public switched telephone network (PSTN) phone is captured in the <A href="lync-server-2013-sessiondetails-table.md">SessionDetails table in Lync Server 2013</A>.</span></span>


</div></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="table-for-e9-1-1-call-auditing"></a><span data-ttu-id="f0c70-197">Tabela para auditoria de chamada E9-1-1</span><span class="sxs-lookup"><span data-stu-id="f0c70-197">Table for E9-1-1 Call Auditing</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="f0c70-198">Tabela</span><span class="sxs-lookup"><span data-stu-id="f0c70-198">Table</span></span></th>
<th><span data-ttu-id="f0c70-199">Descrição</span><span class="sxs-lookup"><span data-stu-id="f0c70-199">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f0c70-200"><a href="lync-server-2013-locations-table.md">Tabela Locations no Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="f0c70-200"><a href="lync-server-2013-locations-table.md">Locations table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="f0c70-201">Para cada chamada de emergência, como uma chamada Enhanced 9-1-1 (E9-1-1), armazena informações de localização sobre a chamada.</span><span class="sxs-lookup"><span data-stu-id="f0c70-201">For each emergency call, such as an Enhanced 9-1-1 (E9-1-1) call, stores location information about the call.</span></span> <span data-ttu-id="f0c70-202">Refere-se à <a href="lync-server-2013-sessiondetails-table.md">tabela SessionDetails no Lync Server 2013</a> para tempo de início/término e código de resposta de chamada.</span><span class="sxs-lookup"><span data-stu-id="f0c70-202">Refers to the <a href="lync-server-2013-sessiondetails-table.md">SessionDetails table in Lync Server 2013</a> for call start/end times and response code.</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="f0c70-203">Esta tabela contém apenas o blob de localização para a chamada E9-1-1.</span><span class="sxs-lookup"><span data-stu-id="f0c70-203">This table only contains the location blob for the E9-1-1 call.</span></span> <span data-ttu-id="f0c70-204">Refere-se à tabela SessionDetails para obter outras informações detalhadas sobre a chamada.</span><span class="sxs-lookup"><span data-stu-id="f0c70-204">Refers to the SessionDetails table for other detailed information about the call.</span></span>


</div></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="tables-for-troubleshooting"></a><span data-ttu-id="f0c70-205">Tabelas para solução de problemas</span><span class="sxs-lookup"><span data-stu-id="f0c70-205">Tables for Troubleshooting</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="f0c70-206">Tabela</span><span class="sxs-lookup"><span data-stu-id="f0c70-206">Table</span></span></th>
<th><span data-ttu-id="f0c70-207">Descrição</span><span class="sxs-lookup"><span data-stu-id="f0c70-207">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f0c70-208"><a href="lync-server-2013-application-table.md">Tabela de aplicativos no Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="f0c70-208"><a href="lync-server-2013-application-table.md">Application table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="f0c70-209">Armazena informações sobre vários processos no Lync Server 2013 que estão envolvidos em roteamento e conexões.</span><span class="sxs-lookup"><span data-stu-id="f0c70-209">Stores information about various processes within Lync Server 2013 that are involved in routing and connections.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f0c70-210"><a href="lync-server-2013-calltype-table.md">Tabela CallType no Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="f0c70-210"><a href="lync-server-2013-calltype-table.md">CallType table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="f0c70-211">Armazena informações sobre tipos de chamada, como "áudio", "mensagens instantâneas", "áudio e vídeo" e "compartilhamento de aplicativos".</span><span class="sxs-lookup"><span data-stu-id="f0c70-211">Stores information about types of the call, such as, “audio”, “Instant Messaging”, “audio and video” and “application sharing”.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f0c70-212"><a href="lync-server-2013-errorcategory-table.md">Tabela ErrorCategory no Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="f0c70-212"><a href="lync-server-2013-errorcategory-table.md">ErrorCategory table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="f0c70-213">Armazena o nome amigável para cada classificação de diagnóstico do Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="f0c70-213">Stores the friendly name for each Microsoft Lync Server 2013 diagnostic classification.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f0c70-214"><a href="lync-server-2013-errordef-table.md">Tabela ErrorDef no Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="f0c70-214"><a href="lync-server-2013-errordef-table.md">ErrorDef table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="f0c70-215">Armazena informações sobre tipos de erros e suas definições.</span><span class="sxs-lookup"><span data-stu-id="f0c70-215">Stores information about types of errors and their definitions.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f0c70-216"><a href="lync-server-2013-errorreport-table.md">Tabela ErrorReport no Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="f0c70-216"><a href="lync-server-2013-errorreport-table.md">ErrorReport table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="f0c70-217">Armazena informações sobre erros ocorridos.</span><span class="sxs-lookup"><span data-stu-id="f0c70-217">Stores information about errors that have occurred.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f0c70-218"><a href="lync-server-2013-progressreport-table.md">Tabela ProgressReport no Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="f0c70-218"><a href="lync-server-2013-progressreport-table.md">ProgressReport table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="f0c70-219">Armazena informações sobre os relatórios de progresso de várias etapas envolvidas nos processos do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="f0c70-219">Stores information about the progress reports of various steps involved in Lync Server 2013 processes.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="f0c70-220">As tabelas na lista a seguir são usadas internamente pelo Lync Server.</span><span class="sxs-lookup"><span data-stu-id="f0c70-220">The tables in the following list are used internally by Lync Server.</span></span> <span data-ttu-id="f0c70-221">Seus detalhes não estão descritos neste documento.</span><span class="sxs-lookup"><span data-stu-id="f0c70-221">Their details are not described in this document.</span></span>

</div>

<div>

## <a name="tables-for-internal-use-by-lync-server"></a><span data-ttu-id="f0c70-222">Tabelas para uso interno pelo Lync Server</span><span class="sxs-lookup"><span data-stu-id="f0c70-222">Tables for Internal Use by Lync Server</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="f0c70-223">Tabela</span><span class="sxs-lookup"><span data-stu-id="f0c70-223">Table</span></span></th>
<th><span data-ttu-id="f0c70-224">Descrição</span><span class="sxs-lookup"><span data-stu-id="f0c70-224">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f0c70-225"><strong>DbConfigDateTime</strong></span><span class="sxs-lookup"><span data-stu-id="f0c70-225"><strong>DbConfigDateTime</strong></span></span></p></td>
<td><p><span data-ttu-id="f0c70-226">Somente para uso interno.</span><span class="sxs-lookup"><span data-stu-id="f0c70-226">For internal use only.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f0c70-227"><strong>DbConfigInt</strong></span><span class="sxs-lookup"><span data-stu-id="f0c70-227"><strong>DbConfigInt</strong></span></span></p></td>
<td><p><span data-ttu-id="f0c70-228">Somente para uso interno.</span><span class="sxs-lookup"><span data-stu-id="f0c70-228">For internal use only.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f0c70-229"><strong>DbErrorMessage</strong></span><span class="sxs-lookup"><span data-stu-id="f0c70-229"><strong>DbErrorMessage</strong></span></span></p></td>
<td><p><span data-ttu-id="f0c70-230">Somente para uso interno.</span><span class="sxs-lookup"><span data-stu-id="f0c70-230">For internal use only.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f0c70-231"><strong>Tabela de front-end</strong></span><span class="sxs-lookup"><span data-stu-id="f0c70-231"><strong>FrontEnd Table</strong></span></span></p></td>
<td><p><span data-ttu-id="f0c70-232">Somente para uso interno.</span><span class="sxs-lookup"><span data-stu-id="f0c70-232">For internal use only.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f0c70-233"><strong>Tabela MSMQProcessing</strong></span><span class="sxs-lookup"><span data-stu-id="f0c70-233"><strong>MSMQProcessing Table</strong></span></span></p></td>
<td><p><span data-ttu-id="f0c70-234">Somente para uso interno.</span><span class="sxs-lookup"><span data-stu-id="f0c70-234">For internal use only.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f0c70-235"><strong>SummaryTableConfiguration</strong></span><span class="sxs-lookup"><span data-stu-id="f0c70-235"><strong>SummaryTableConfiguration</strong></span></span></p></td>
<td><p><span data-ttu-id="f0c70-236">Somente para uso interno.</span><span class="sxs-lookup"><span data-stu-id="f0c70-236">For internal use only.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f0c70-237"><strong>Tabela de sindicadores</strong></span><span class="sxs-lookup"><span data-stu-id="f0c70-237"><strong>Syndicators Table</strong></span></span></p></td>
<td><p><span data-ttu-id="f0c70-238">Somente para uso interno.</span><span class="sxs-lookup"><span data-stu-id="f0c70-238">For internal use only.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f0c70-239"><strong>Tabela SyndicatorsTenantMap</strong></span><span class="sxs-lookup"><span data-stu-id="f0c70-239"><strong>SyndicatorsTenantMap Table</strong></span></span></p></td>
<td><p><span data-ttu-id="f0c70-240">Somente para uso interno.</span><span class="sxs-lookup"><span data-stu-id="f0c70-240">For internal use only.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f0c70-241"><strong>Tabela de tarefas</strong></span><span class="sxs-lookup"><span data-stu-id="f0c70-241"><strong>Task Table</strong></span></span></p></td>
<td><p><span data-ttu-id="f0c70-242">Somente para uso interno.</span><span class="sxs-lookup"><span data-stu-id="f0c70-242">For internal use only.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f0c70-243"><strong>UserStatistics</strong></span><span class="sxs-lookup"><span data-stu-id="f0c70-243"><strong>UserStatistics</strong></span></span></p></td>
<td><p><span data-ttu-id="f0c70-244">Somente para uso interno.</span><span class="sxs-lookup"><span data-stu-id="f0c70-244">For internal use only.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f0c70-245"><strong>UsageSummary_UQ</strong></span><span class="sxs-lookup"><span data-stu-id="f0c70-245"><strong>UsageSummary_UQ</strong></span></span></p></td>
<td><p><span data-ttu-id="f0c70-246">Somente para uso interno.</span><span class="sxs-lookup"><span data-stu-id="f0c70-246">For internal use only.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f0c70-247"><strong>UsageSummary</strong></span><span class="sxs-lookup"><span data-stu-id="f0c70-247"><strong>UsageSummary</strong></span></span></p></td>
<td><p><span data-ttu-id="f0c70-248">Somente para uso interno.</span><span class="sxs-lookup"><span data-stu-id="f0c70-248">For internal use only.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f0c70-249"><strong>DaylightSavingYears</strong></span><span class="sxs-lookup"><span data-stu-id="f0c70-249"><strong>DaylightSavingYears</strong></span></span></p></td>
<td><p><span data-ttu-id="f0c70-250">Somente para uso interno.</span><span class="sxs-lookup"><span data-stu-id="f0c70-250">For internal use only.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f0c70-251"><strong>TimeZoneConfiguration</strong></span><span class="sxs-lookup"><span data-stu-id="f0c70-251"><strong>TimeZoneConfiguration</strong></span></span></p></td>
<td><p><span data-ttu-id="f0c70-252">Somente para uso interno.</span><span class="sxs-lookup"><span data-stu-id="f0c70-252">For internal use only.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f0c70-253"><strong>Fusos horários</strong></span><span class="sxs-lookup"><span data-stu-id="f0c70-253"><strong>TimeZones</strong></span></span></p></td>
<td><p><span data-ttu-id="f0c70-254">Somente para uso interno.</span><span class="sxs-lookup"><span data-stu-id="f0c70-254">For internal use only.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f0c70-255"><strong>FailureSummary_UQ</strong></span><span class="sxs-lookup"><span data-stu-id="f0c70-255"><strong>FailureSummary_UQ</strong></span></span></p></td>
<td><p><span data-ttu-id="f0c70-256">Somente para uso interno.</span><span class="sxs-lookup"><span data-stu-id="f0c70-256">For internal use only.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f0c70-257"><strong>FailureSummary</strong></span><span class="sxs-lookup"><span data-stu-id="f0c70-257"><strong>FailureSummary</strong></span></span></p></td>
<td><p><span data-ttu-id="f0c70-258">Somente para uso interno.</span><span class="sxs-lookup"><span data-stu-id="f0c70-258">For internal use only.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f0c70-259"><strong>ServerSummary</strong></span><span class="sxs-lookup"><span data-stu-id="f0c70-259"><strong>ServerSummary</strong></span></span></p></td>
<td><p><span data-ttu-id="f0c70-260">Somente para uso interno.</span><span class="sxs-lookup"><span data-stu-id="f0c70-260">For internal use only.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f0c70-261"><strong>MsDiagMetaData</strong></span><span class="sxs-lookup"><span data-stu-id="f0c70-261"><strong>MsDiagMetaData</strong></span></span></p></td>
<td><p><span data-ttu-id="f0c70-262">Somente para uso interno.</span><span class="sxs-lookup"><span data-stu-id="f0c70-262">For internal use only.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

