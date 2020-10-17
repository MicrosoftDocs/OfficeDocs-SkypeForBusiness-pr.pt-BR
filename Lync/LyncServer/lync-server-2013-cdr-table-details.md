---
title: 'Lync Server 2013: detalhes da tabela CDR'
description: 'Lync Server 2013: detalhes da tabela CDR.'
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
ms.openlocfilehash: 331a3dfd4ffccac2ac4a442eeb9ad9171defb41c
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48544387"
---
# <a name="cdr-table-details-in-lync-server-2013"></a><span data-ttu-id="12f65-103">Detalhes da tabela CDR no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="12f65-103">CDR table details in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="12f65-104">_**Última modificação do tópico:** 2012-10-18_</span><span class="sxs-lookup"><span data-stu-id="12f65-104">_**Topic Last Modified:** 2012-10-18_</span></span>

<span data-ttu-id="12f65-105">Os tópicos a seguir detalham as colunas de cada tabela de esquema de banco de dados de registro de detalhes das chamadas (CDR).</span><span class="sxs-lookup"><span data-stu-id="12f65-105">The following topics detail the columns in each of the call detail records (CDR) database schema tables.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="12f65-106">Nesta seção</span><span class="sxs-lookup"><span data-stu-id="12f65-106">In This Section</span></span>

  - [<span data-ttu-id="12f65-107">Tabela de aplicativos no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="12f65-107">Application table in Lync Server 2013</span></span>](lync-server-2013-application-table.md)

  - [<span data-ttu-id="12f65-108">Tabela CallPriorities no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="12f65-108">CallPriorities table in Lync Server 2013</span></span>](lync-server-2013-callpriorities-table.md)

  - [<span data-ttu-id="12f65-109">Tabela CallType no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="12f65-109">CallType table in Lync Server 2013</span></span>](lync-server-2013-calltype-table.md)

  - [<span data-ttu-id="12f65-110">Tabela ClientVersions no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="12f65-110">ClientVersions table in Lync Server 2013</span></span>](lync-server-2013-clientversions-table.md)

  - [<span data-ttu-id="12f65-111">Tabela ConferenceJoinTimeThresholds no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="12f65-111">ConferenceJoinTimeThresholds table in Lync Server 2013</span></span>](lync-server-2013-conferencejointimethresholds-table.md)

  - [<span data-ttu-id="12f65-112">Tabela ConferenceMessageCount no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="12f65-112">ConferenceMessageCount table in Lync Server 2013</span></span>](lync-server-2013-conferencemessagecount-table.md)

  - [<span data-ttu-id="12f65-113">Tabela de conferências no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="12f65-113">Conferences table in Lync Server 2013</span></span>](lync-server-2013-conferences-table.md)

  - [<span data-ttu-id="12f65-114">Tabela ConferenceSessionDetails no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="12f65-114">ConferenceSessionDetails table in Lync Server 2013</span></span>](lync-server-2013-conferencesessiondetails-table.md)

  - [<span data-ttu-id="12f65-115">Tabela ConferenceUris no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="12f65-115">ConferenceUris table in Lync Server 2013</span></span>](lync-server-2013-conferenceuris-table.md)

  - [<span data-ttu-id="12f65-116">Tabela ContentTypes no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="12f65-116">ContentTypes table in Lync Server 2013</span></span>](lync-server-2013-contenttypes-table.md)

  - [<span data-ttu-id="12f65-117">Tabela deregistertype no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="12f65-117">DeRegisterType table in Lync Server 2013</span></span>](lync-server-2013-deregistertype-table.md)

  - [<span data-ttu-id="12f65-118">Tabela de dispositivos no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="12f65-118">Devices table in Lync Server 2013</span></span>](lync-server-2013-devices-table.md)

  - [<span data-ttu-id="12f65-119">Tabela Dialogs no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="12f65-119">Dialogs table in Lync Server 2013</span></span>](lync-server-2013-dialogs-table.md)

  - [<span data-ttu-id="12f65-120">Tabela EdgeServers no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="12f65-120">EdgeServers table in Lync Server 2013</span></span>](lync-server-2013-edgeservers-table.md)

  - [<span data-ttu-id="12f65-121">Tabela ErrorCategory no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="12f65-121">ErrorCategory table in Lync Server 2013</span></span>](lync-server-2013-errorcategory-table.md)

  - [<span data-ttu-id="12f65-122">Tabela ErrorDef no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="12f65-122">ErrorDef table in Lync Server 2013</span></span>](lync-server-2013-errordef-table.md)

  - [<span data-ttu-id="12f65-123">Tabela ErrorReport no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="12f65-123">ErrorReport table in Lync Server 2013</span></span>](lync-server-2013-errorreport-table.md)

  - [<span data-ttu-id="12f65-124">Tabela filetransfers no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="12f65-124">FileTransfers table in Lync Server 2013</span></span>](lync-server-2013-filetransfers-table.md)

  - [<span data-ttu-id="12f65-125">Tabela FocusJoinsAndLeaves no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="12f65-125">FocusJoinsAndLeaves table in Lync Server 2013</span></span>](lync-server-2013-focusjoinsandleaves-table.md)

  - [<span data-ttu-id="12f65-126">Tabela de FrontEnd no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="12f65-126">FrontEnd table in Lync Server 2013</span></span>](lync-server-2013-frontend-table.md)

  - [<span data-ttu-id="12f65-127">Tabela gateways no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="12f65-127">Gateways table in Lync Server 2013</span></span>](lync-server-2013-gateways-table.md)

  - [<span data-ttu-id="12f65-128">Tabela HardwareVersions no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="12f65-128">HardwareVersions table in Lync Server 2013</span></span>](lync-server-2013-hardwareversions-table.md)

  - [<span data-ttu-id="12f65-129">Tabela IMReportSummary no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="12f65-129">IMReportSummary table in Lync Server 2013</span></span>](lync-server-2013-imreportsummary-table.md)

  - [<span data-ttu-id="12f65-130">Tabela Locations no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="12f65-130">Locations table in Lync Server 2013</span></span>](lync-server-2013-locations-table.md)

  - [<span data-ttu-id="12f65-131">Tabela de fabricantes no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="12f65-131">Manufacturers table in Lync Server 2013</span></span>](lync-server-2013-manufacturers-table.md)

  - [<span data-ttu-id="12f65-132">Tabela McuJoinsAndLeaves no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="12f65-132">McuJoinsAndLeaves table in Lync Server 2013</span></span>](lync-server-2013-mcujoinsandleaves-table.md)

  - [<span data-ttu-id="12f65-133">Tabela MCUs no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="12f65-133">Mcus table in Lync Server 2013</span></span>](lync-server-2013-mcus-table.md)

  - [<span data-ttu-id="12f65-134">Tabela de mídia no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="12f65-134">Media table in Lync Server 2013</span></span>](lync-server-2013-media-table.md)

  - [<span data-ttu-id="12f65-135">Tabela medialist no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="12f65-135">MediaList table in Lync Server 2013</span></span>](lync-server-2013-medialist-table.md)

  - [<span data-ttu-id="12f65-136">Tabela MediationServers no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="12f65-136">MediationServers table in Lync Server 2013</span></span>](lync-server-2013-mediationservers-table.md)

  - [<span data-ttu-id="12f65-137">Tabela MSMQProcessing no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="12f65-137">MSMQProcessing table in Lync Server 2013</span></span>](lync-server-2013-msmqprocessing-table.md)

  - [<span data-ttu-id="12f65-138">Tabela phones no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="12f65-138">Phones table in Lync Server 2013</span></span>](lync-server-2013-phones-table.md)

  - [<span data-ttu-id="12f65-139">Tabela de pools no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="12f65-139">Pools table in Lync Server 2013</span></span>](lync-server-2013-pools-table.md)

  - [<span data-ttu-id="12f65-140">Tabela ProgressReport no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="12f65-140">ProgressReport table in Lync Server 2013</span></span>](lync-server-2013-progressreport-table.md)

  - [<span data-ttu-id="12f65-141">Tabela PurgeSettings no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="12f65-141">PurgeSettings table in Lync Server 2013</span></span>](lync-server-2013-purgesettings-table.md)

  - [<span data-ttu-id="12f65-142">Tabela de registro no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="12f65-142">Registration table in Lync Server 2013</span></span>](lync-server-2013-registration-table.md)

  - [<span data-ttu-id="12f65-143">Tabela de funções no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="12f65-143">Roles table in Lync Server 2013</span></span>](lync-server-2013-roles-table.md)

  - [<span data-ttu-id="12f65-144">Tabela de servidores no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="12f65-144">Servers table in Lync Server 2013</span></span>](lync-server-2013-servers-table.md)

  - [<span data-ttu-id="12f65-145">Tabela SessionDetails no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="12f65-145">SessionDetails table in Lync Server 2013</span></span>](lync-server-2013-sessiondetails-table.md)

  - [<span data-ttu-id="12f65-146">Tabela SIPResponseMetaData no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="12f65-146">SIPResponseMetaData table in Lync Server 2013</span></span>](lync-server-2013-sipresponsemetadata-table.md)

  - [<span data-ttu-id="12f65-147">Tabela de sindicadores no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="12f65-147">Syndicators table in Lync Server 2013</span></span>](lync-server-2013-syndicators-table.md)

  - [<span data-ttu-id="12f65-148">Tabela SyndicatorsTenantMap no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="12f65-148">SyndicatorsTenantMap table in Lync Server 2013</span></span>](lync-server-2013-syndicatorstenantmap-table.md)

  - [<span data-ttu-id="12f65-149">Tabela de tarefas no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="12f65-149">Task table in Lync Server 2013</span></span>](lync-server-2013-task-table.md)

  - [<span data-ttu-id="12f65-150">Tabela de locatários no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="12f65-150">Tenants table in Lync Server 2013</span></span>](lync-server-2013-tenants-table.md)

  - [<span data-ttu-id="12f65-151">Tabela UriTypes no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="12f65-151">UriTypes table in Lync Server 2013</span></span>](lync-server-2013-uritypes-table.md)

  - [<span data-ttu-id="12f65-152">Tabela Users no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="12f65-152">Users table in Lync Server 2013</span></span>](lync-server-2013-users-table.md)

  - [<span data-ttu-id="12f65-153">Tabela UserAgentDef no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="12f65-153">UserAgentDef table in Lync Server 2013</span></span>](lync-server-2013-useragentdef-table.md)

  - [<span data-ttu-id="12f65-154">Tabela userstatistics no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="12f65-154">UserStatistics table in Lync Server 2013</span></span>](lync-server-2013-userstatistics-table.md)

  - [<span data-ttu-id="12f65-155">Tabela VoipDetails no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="12f65-155">VoipDetails table in Lync Server 2013</span></span>](lync-server-2013-voipdetails-table.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

