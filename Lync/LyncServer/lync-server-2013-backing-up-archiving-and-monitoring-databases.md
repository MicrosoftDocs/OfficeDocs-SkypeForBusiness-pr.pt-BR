---
title: 'Lync Server 2013: fazendo backup de bancos de dados de arquivamento e monitoramento'
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
ms.openlocfilehash: 955609f4d012489ba70dbb81f21a38e8261ef7f2
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42045083"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="backing-up-archiving-and-monitoring-databases-in-lync-server-2013"></a><span data-ttu-id="e5027-102">Backup de bancos de dados de arquivamento e monitoramento no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e5027-102">Backing up Archiving and Monitoring databases in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e5027-103">_**Última modificação do tópico:** 2013-02-17_</span><span class="sxs-lookup"><span data-stu-id="e5027-103">_**Topic Last Modified:** 2013-02-17_</span></span>

<span data-ttu-id="e5027-104">Se você implantou o Arquivamento ou Monitoramento, será necessário fazer backup desses bancos de dados de acordo com a política de backup do SQL Server de sua organização.</span><span class="sxs-lookup"><span data-stu-id="e5027-104">If you deployed Archiving or Monitoring, you need to back up these databases according to your organization's SQL Server backup policy.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="e5027-105">As configurações de arquivamento e monitoramento são armazenadas em backup quando você faz o backup do repositório de gerenciamento central.</span><span class="sxs-lookup"><span data-stu-id="e5027-105">The settings for Archiving and Monitoring are backed up when you back up the Central Management store.</span></span> <span data-ttu-id="e5027-106">Para obter detalhes, consulte <A href="lync-server-2013-backing-up-core-data-and-settings.md">backing up Core Data and Settings in Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="e5027-106">For details, see <A href="lync-server-2013-backing-up-core-data-and-settings.md">Backing up core data and settings in Lync Server 2013</A>.</span></span>



</div>

<span data-ttu-id="e5027-107">Para Arquivamento e Monitoramento, você pode usar uma ferramenta de SQL Server, como SQL Server Management Studio, para executar um backup manual ou pode usar ferramentas de gerenciamento de SQL Server para agendar backups automáticos e regulares.</span><span class="sxs-lookup"><span data-stu-id="e5027-107">For Archiving and Monitoring, you can use a SQL Server tool such as SQL Server Management Studio to perform a manual backup, or you can use SQL Server management tools to schedule regular, automatic backups.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

