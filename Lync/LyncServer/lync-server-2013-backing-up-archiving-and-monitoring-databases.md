---
title: 'Lync Server 2013: fazendo backup de bancos de dados de arquivamento e monitoramento'
description: 'Lync Server 2013: fazendo backup de bancos de dados de arquivamento e monitoramento.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Backing up Archiving and Monitoring databases
ms:assetid: c120db81-b02c-4a4c-90cd-8aca6cff64f9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202188(v=OCS.15)
ms:contentKeyID: 51541515
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 49b4fa194bffa27a52f32d61a729eeaa31cc0ad3
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48543757"
---
# <a name="backing-up-archiving-and-monitoring-databases-in-lync-server-2013"></a>Backup de bancos de dados de arquivamento e monitoramento no Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2013-02-17_

Se você implantou o Arquivamento ou Monitoramento, será necessário fazer backup desses bancos de dados de acordo com a política de backup do SQL Server de sua organização.

<div>


> [!NOTE]  
> As configurações de arquivamento e monitoramento são armazenadas em backup quando você faz o backup do repositório de gerenciamento central. Para obter detalhes, consulte <A href="lync-server-2013-backing-up-core-data-and-settings.md">backing up Core Data and Settings in Lync Server 2013</A>.



</div>

Para Arquivamento e Monitoramento, você pode usar uma ferramenta de SQL Server, como SQL Server Management Studio, para executar um backup manual ou pode usar ferramentas de gerenciamento de SQL Server para agendar backups automáticos e regulares.

</div>

<span> </span>

</div>

</div>

</div>

