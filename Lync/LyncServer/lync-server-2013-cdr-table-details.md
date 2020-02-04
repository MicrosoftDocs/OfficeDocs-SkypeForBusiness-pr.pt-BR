---
title: 'Lync Server 2013: Detalhes da tabela CDR'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: CDR table details
ms:assetid: 896198f5-672b-48ea-852f-0211c0c90857
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398693(v=OCS.15)
ms:contentKeyID: 48184730
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 650caa5244eaf796c066f1388f2fcbb5d3b0703a
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41736941"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="cdr-table-details-in-lync-server-2013"></a><span data-ttu-id="d98b0-102">Detalhes da tabela CDR no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d98b0-102">CDR table details in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d98b0-103">_**Tópico da última modificação:** 2012-10-18_</span><span class="sxs-lookup"><span data-stu-id="d98b0-103">_**Topic Last Modified:** 2012-10-18_</span></span>

<span data-ttu-id="d98b0-104">Os tópicos a seguir detalham as colunas em cada tabela de esquema de banco de dados de registros de detalhes de chamadas (CDR).</span><span class="sxs-lookup"><span data-stu-id="d98b0-104">The following topics detail the columns in each of the call detail records (CDR) database schema tables.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="d98b0-105">Nesta seção</span><span class="sxs-lookup"><span data-stu-id="d98b0-105">In This Section</span></span>

  - [<span data-ttu-id="d98b0-106">Tabela de aplicativos no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d98b0-106">Application table in Lync Server 2013</span></span>](lync-server-2013-application-table.md)

  - [<span data-ttu-id="d98b0-107">Tabela CallPriorities no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d98b0-107">CallPriorities table in Lync Server 2013</span></span>](lync-server-2013-callpriorities-table.md)

  - [<span data-ttu-id="d98b0-108">Tabela CallType no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d98b0-108">CallType table in Lync Server 2013</span></span>](lync-server-2013-calltype-table.md)

  - [<span data-ttu-id="d98b0-109">Tabela ClientVersions no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d98b0-109">ClientVersions table in Lync Server 2013</span></span>](lync-server-2013-clientversions-table.md)

  - [<span data-ttu-id="d98b0-110">Tabela ConferenceJoinTimeThresholds no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d98b0-110">ConferenceJoinTimeThresholds table in Lync Server 2013</span></span>](lync-server-2013-conferencejointimethresholds-table.md)

  - [<span data-ttu-id="d98b0-111">Tabela ConferenceMessageCount no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d98b0-111">ConferenceMessageCount table in Lync Server 2013</span></span>](lync-server-2013-conferencemessagecount-table.md)

  - [<span data-ttu-id="d98b0-112">Tabela Conferences no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d98b0-112">Conferences table in Lync Server 2013</span></span>](lync-server-2013-conferences-table.md)

  - [<span data-ttu-id="d98b0-113">Tabela ConferenceSessionDetails no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d98b0-113">ConferenceSessionDetails table in Lync Server 2013</span></span>](lync-server-2013-conferencesessiondetails-table.md)

  - [<span data-ttu-id="d98b0-114">Tabela ConferenceUris no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d98b0-114">ConferenceUris table in Lync Server 2013</span></span>](lync-server-2013-conferenceuris-table.md)

  - [<span data-ttu-id="d98b0-115">Tabela ContentTypes no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d98b0-115">ContentTypes table in Lync Server 2013</span></span>](lync-server-2013-contenttypes-table.md)

  - [<span data-ttu-id="d98b0-116">Tabela DeRegisterType no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d98b0-116">DeRegisterType table in Lync Server 2013</span></span>](lync-server-2013-deregistertype-table.md)

  - [<span data-ttu-id="d98b0-117">Tabela Devices no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d98b0-117">Devices table in Lync Server 2013</span></span>](lync-server-2013-devices-table.md)

  - [<span data-ttu-id="d98b0-118">Tabela Dialogs no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d98b0-118">Dialogs table in Lync Server 2013</span></span>](lync-server-2013-dialogs-table.md)

  - [<span data-ttu-id="d98b0-119">Tabela EdgeServers no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d98b0-119">EdgeServers table in Lync Server 2013</span></span>](lync-server-2013-edgeservers-table.md)

  - [<span data-ttu-id="d98b0-120">Tabela ErrorCategory no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d98b0-120">ErrorCategory table in Lync Server 2013</span></span>](lync-server-2013-errorcategory-table.md)

  - [<span data-ttu-id="d98b0-121">Tabela ErrorDef no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d98b0-121">ErrorDef table in Lync Server 2013</span></span>](lync-server-2013-errordef-table.md)

  - [<span data-ttu-id="d98b0-122">Tabela ErrorReport no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d98b0-122">ErrorReport table in Lync Server 2013</span></span>](lync-server-2013-errorreport-table.md)

  - [<span data-ttu-id="d98b0-123">Tabela FileTransfers no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d98b0-123">FileTransfers table in Lync Server 2013</span></span>](lync-server-2013-filetransfers-table.md)

  - [<span data-ttu-id="d98b0-124">Tabela FocusJoinsAndLeaves no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d98b0-124">FocusJoinsAndLeaves table in Lync Server 2013</span></span>](lync-server-2013-focusjoinsandleaves-table.md)

  - [<span data-ttu-id="d98b0-125">Tabela de front-end no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d98b0-125">FrontEnd table in Lync Server 2013</span></span>](lync-server-2013-frontend-table.md)

  - [<span data-ttu-id="d98b0-126">Tabela Gateways no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d98b0-126">Gateways table in Lync Server 2013</span></span>](lync-server-2013-gateways-table.md)

  - [<span data-ttu-id="d98b0-127">Tabela HardwareVersions no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d98b0-127">HardwareVersions table in Lync Server 2013</span></span>](lync-server-2013-hardwareversions-table.md)

  - [<span data-ttu-id="d98b0-128">Tabela IMReportSummary no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d98b0-128">IMReportSummary table in Lync Server 2013</span></span>](lync-server-2013-imreportsummary-table.md)

  - [<span data-ttu-id="d98b0-129">Tabela Locations no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d98b0-129">Locations table in Lync Server 2013</span></span>](lync-server-2013-locations-table.md)

  - [<span data-ttu-id="d98b0-130">Tabela Manufacturers no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d98b0-130">Manufacturers table in Lync Server 2013</span></span>](lync-server-2013-manufacturers-table.md)

  - [<span data-ttu-id="d98b0-131">Tabela McuJoinsAndLeaves no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d98b0-131">McuJoinsAndLeaves table in Lync Server 2013</span></span>](lync-server-2013-mcujoinsandleaves-table.md)

  - [<span data-ttu-id="d98b0-132">Tabela Mcus no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d98b0-132">Mcus table in Lync Server 2013</span></span>](lync-server-2013-mcus-table.md)

  - [<span data-ttu-id="d98b0-133">Tabela Media no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d98b0-133">Media table in Lync Server 2013</span></span>](lync-server-2013-media-table.md)

  - [<span data-ttu-id="d98b0-134">Tabela MediaList no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d98b0-134">MediaList table in Lync Server 2013</span></span>](lync-server-2013-medialist-table.md)

  - [<span data-ttu-id="d98b0-135">Tabela MediationServers no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d98b0-135">MediationServers table in Lync Server 2013</span></span>](lync-server-2013-mediationservers-table.md)

  - [<span data-ttu-id="d98b0-136">Tabela MSMQProcessing no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d98b0-136">MSMQProcessing table in Lync Server 2013</span></span>](lync-server-2013-msmqprocessing-table.md)

  - [<span data-ttu-id="d98b0-137">Tabela Phones no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d98b0-137">Phones table in Lync Server 2013</span></span>](lync-server-2013-phones-table.md)

  - [<span data-ttu-id="d98b0-138">Tabela Pools no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d98b0-138">Pools table in Lync Server 2013</span></span>](lync-server-2013-pools-table.md)

  - [<span data-ttu-id="d98b0-139">Tabela ProgressReport no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d98b0-139">ProgressReport table in Lync Server 2013</span></span>](lync-server-2013-progressreport-table.md)

  - [<span data-ttu-id="d98b0-140">Tabela PurgeSettings no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d98b0-140">PurgeSettings table in Lync Server 2013</span></span>](lync-server-2013-purgesettings-table.md)

  - [<span data-ttu-id="d98b0-141">Tabela de registro no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d98b0-141">Registration table in Lync Server 2013</span></span>](lync-server-2013-registration-table.md)

  - [<span data-ttu-id="d98b0-142">Tabela Roles no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d98b0-142">Roles table in Lync Server 2013</span></span>](lync-server-2013-roles-table.md)

  - [<span data-ttu-id="d98b0-143">Tabela de servidores no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d98b0-143">Servers table in Lync Server 2013</span></span>](lync-server-2013-servers-table.md)

  - [<span data-ttu-id="d98b0-144">Tabela SessionDetails no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d98b0-144">SessionDetails table in Lync Server 2013</span></span>](lync-server-2013-sessiondetails-table.md)

  - [<span data-ttu-id="d98b0-145">Tabela SIPResponseMetaData no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d98b0-145">SIPResponseMetaData table in Lync Server 2013</span></span>](lync-server-2013-sipresponsemetadata-table.md)

  - [<span data-ttu-id="d98b0-146">Tabela sindicadores no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d98b0-146">Syndicators table in Lync Server 2013</span></span>](lync-server-2013-syndicators-table.md)

  - [<span data-ttu-id="d98b0-147">Tabela SyndicatorsTenantMap no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d98b0-147">SyndicatorsTenantMap table in Lync Server 2013</span></span>](lync-server-2013-syndicatorstenantmap-table.md)

  - [<span data-ttu-id="d98b0-148">Tabela de tarefas no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d98b0-148">Task table in Lync Server 2013</span></span>](lync-server-2013-task-table.md)

  - [<span data-ttu-id="d98b0-149">Tabela Tenants no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d98b0-149">Tenants table in Lync Server 2013</span></span>](lync-server-2013-tenants-table.md)

  - [<span data-ttu-id="d98b0-150">Tabela UriTypes no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d98b0-150">UriTypes table in Lync Server 2013</span></span>](lync-server-2013-uritypes-table.md)

  - [<span data-ttu-id="d98b0-151">Tabela Users no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d98b0-151">Users table in Lync Server 2013</span></span>](lync-server-2013-users-table.md)

  - [<span data-ttu-id="d98b0-152">Tabela UserAgentDef no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d98b0-152">UserAgentDef table in Lync Server 2013</span></span>](lync-server-2013-useragentdef-table.md)

  - [<span data-ttu-id="d98b0-153">Tabela userstatistics no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d98b0-153">UserStatistics table in Lync Server 2013</span></span>](lync-server-2013-userstatistics-table.md)

  - [<span data-ttu-id="d98b0-154">Tabela VoipDetails no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d98b0-154">VoipDetails table in Lync Server 2013</span></span>](lync-server-2013-voipdetails-table.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

