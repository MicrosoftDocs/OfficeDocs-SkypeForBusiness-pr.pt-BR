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

# <a name="cdr-table-details-in-lync-server-2013"></a>Detalhes da tabela CDR no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2012-10-18_

Os tópicos a seguir detalham as colunas em cada tabela de esquema de banco de dados de registros de detalhes de chamadas (CDR).

<div>

## <a name="in-this-section"></a>Nesta seção

  - [Tabela de aplicativos no Lync Server 2013](lync-server-2013-application-table.md)

  - [Tabela CallPriorities no Lync Server 2013](lync-server-2013-callpriorities-table.md)

  - [Tabela CallType no Lync Server 2013](lync-server-2013-calltype-table.md)

  - [Tabela ClientVersions no Lync Server 2013](lync-server-2013-clientversions-table.md)

  - [Tabela ConferenceJoinTimeThresholds no Lync Server 2013](lync-server-2013-conferencejointimethresholds-table.md)

  - [Tabela ConferenceMessageCount no Lync Server 2013](lync-server-2013-conferencemessagecount-table.md)

  - [Tabela Conferences no Lync Server 2013](lync-server-2013-conferences-table.md)

  - [Tabela ConferenceSessionDetails no Lync Server 2013](lync-server-2013-conferencesessiondetails-table.md)

  - [Tabela ConferenceUris no Lync Server 2013](lync-server-2013-conferenceuris-table.md)

  - [Tabela ContentTypes no Lync Server 2013](lync-server-2013-contenttypes-table.md)

  - [Tabela DeRegisterType no Lync Server 2013](lync-server-2013-deregistertype-table.md)

  - [Tabela Devices no Lync Server 2013](lync-server-2013-devices-table.md)

  - [Tabela Dialogs no Lync Server 2013](lync-server-2013-dialogs-table.md)

  - [Tabela EdgeServers no Lync Server 2013](lync-server-2013-edgeservers-table.md)

  - [Tabela ErrorCategory no Lync Server 2013](lync-server-2013-errorcategory-table.md)

  - [Tabela ErrorDef no Lync Server 2013](lync-server-2013-errordef-table.md)

  - [Tabela ErrorReport no Lync Server 2013](lync-server-2013-errorreport-table.md)

  - [Tabela FileTransfers no Lync Server 2013](lync-server-2013-filetransfers-table.md)

  - [Tabela FocusJoinsAndLeaves no Lync Server 2013](lync-server-2013-focusjoinsandleaves-table.md)

  - [Tabela de front-end no Lync Server 2013](lync-server-2013-frontend-table.md)

  - [Tabela Gateways no Lync Server 2013](lync-server-2013-gateways-table.md)

  - [Tabela HardwareVersions no Lync Server 2013](lync-server-2013-hardwareversions-table.md)

  - [Tabela IMReportSummary no Lync Server 2013](lync-server-2013-imreportsummary-table.md)

  - [Tabela Locations no Lync Server 2013](lync-server-2013-locations-table.md)

  - [Tabela Manufacturers no Lync Server 2013](lync-server-2013-manufacturers-table.md)

  - [Tabela McuJoinsAndLeaves no Lync Server 2013](lync-server-2013-mcujoinsandleaves-table.md)

  - [Tabela Mcus no Lync Server 2013](lync-server-2013-mcus-table.md)

  - [Tabela Media no Lync Server 2013](lync-server-2013-media-table.md)

  - [Tabela MediaList no Lync Server 2013](lync-server-2013-medialist-table.md)

  - [Tabela MediationServers no Lync Server 2013](lync-server-2013-mediationservers-table.md)

  - [Tabela MSMQProcessing no Lync Server 2013](lync-server-2013-msmqprocessing-table.md)

  - [Tabela Phones no Lync Server 2013](lync-server-2013-phones-table.md)

  - [Tabela Pools no Lync Server 2013](lync-server-2013-pools-table.md)

  - [Tabela ProgressReport no Lync Server 2013](lync-server-2013-progressreport-table.md)

  - [Tabela PurgeSettings no Lync Server 2013](lync-server-2013-purgesettings-table.md)

  - [Tabela de registro no Lync Server 2013](lync-server-2013-registration-table.md)

  - [Tabela Roles no Lync Server 2013](lync-server-2013-roles-table.md)

  - [Tabela de servidores no Lync Server 2013](lync-server-2013-servers-table.md)

  - [Tabela SessionDetails no Lync Server 2013](lync-server-2013-sessiondetails-table.md)

  - [Tabela SIPResponseMetaData no Lync Server 2013](lync-server-2013-sipresponsemetadata-table.md)

  - [Tabela sindicadores no Lync Server 2013](lync-server-2013-syndicators-table.md)

  - [Tabela SyndicatorsTenantMap no Lync Server 2013](lync-server-2013-syndicatorstenantmap-table.md)

  - [Tabela de tarefas no Lync Server 2013](lync-server-2013-task-table.md)

  - [Tabela Tenants no Lync Server 2013](lync-server-2013-tenants-table.md)

  - [Tabela UriTypes no Lync Server 2013](lync-server-2013-uritypes-table.md)

  - [Tabela Users no Lync Server 2013](lync-server-2013-users-table.md)

  - [Tabela UserAgentDef no Lync Server 2013](lync-server-2013-useragentdef-table.md)

  - [Tabela userstatistics no Lync Server 2013](lync-server-2013-userstatistics-table.md)

  - [Tabela VoipDetails no Lync Server 2013](lync-server-2013-voipdetails-table.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

