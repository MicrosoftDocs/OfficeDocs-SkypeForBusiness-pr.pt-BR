---
title: 'Lync Server 2013: fazendo backup do arquivamento e monitoramento de bancos de dados'
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
ms.openlocfilehash: 4092ddc3c86496053cc0ebbb367188490096de4f
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41740161"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="backing-up-archiving-and-monitoring-databases-in-lync-server-2013"></a><span data-ttu-id="d2ae2-102">Fazer backup do arquivamento e do monitoramento de bancos de dados no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d2ae2-102">Backing up Archiving and Monitoring databases in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d2ae2-103">_**Tópico da última modificação:** 2013-02-17_</span><span class="sxs-lookup"><span data-stu-id="d2ae2-103">_**Topic Last Modified:** 2013-02-17_</span></span>

<span data-ttu-id="d2ae2-104">Se você implantou o arquivamento ou o monitoramento, é preciso fazer backup desses bancos de dados de acordo com a política de backup do SQL Server da sua organização.</span><span class="sxs-lookup"><span data-stu-id="d2ae2-104">If you deployed Archiving or Monitoring, you need to back up these databases according to your organization's SQL Server backup policy.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="d2ae2-105">As configurações de arquivamento e monitoramento são armazenadas em backup quando você fizer backup do repositório de gerenciamento central.</span><span class="sxs-lookup"><span data-stu-id="d2ae2-105">The settings for Archiving and Monitoring are backed up when you back up the Central Management store.</span></span> <span data-ttu-id="d2ae2-106">Para obter detalhes, consulte <A href="lync-server-2013-backing-up-core-data-and-settings.md">fazendo backup de dados principais e configurações no Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="d2ae2-106">For details, see <A href="lync-server-2013-backing-up-core-data-and-settings.md">Backing up core data and settings in Lync Server 2013</A>.</span></span>



</div>

<span data-ttu-id="d2ae2-107">Para arquivamento e monitoramento, você pode usar uma ferramenta do SQL Server como o SQL Server Management Studio para executar um backup manual ou pode usar as ferramentas de gerenciamento do SQL Server para agendar backups automáticos regulares.</span><span class="sxs-lookup"><span data-stu-id="d2ae2-107">For Archiving and Monitoring, you can use a SQL Server tool such as SQL Server Management Studio to perform a manual backup, or you can use SQL Server management tools to schedule regular, automatic backups.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

