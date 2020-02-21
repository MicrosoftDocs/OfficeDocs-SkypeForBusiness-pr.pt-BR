---
title: 'Lync Server 2013: configurar um local de backup'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Setting up a backup location
ms:assetid: 006732eb-3d44-414d-8010-227a855caa93
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202158(v=OCS.15)
ms:contentKeyID: 51541440
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0a5c723f25abe6a5e12833b37b070c543b5db4ac
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42182134"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="setting-up-a-backup-location-for-lync-server-2013"></a><span data-ttu-id="0831f-102">Configurando um local de backup para o Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0831f-102">Setting up a backup location for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0831f-103">_**Última modificação do tópico:** 2013-02-17_</span><span class="sxs-lookup"><span data-stu-id="0831f-103">_**Topic Last Modified:** 2013-02-17_</span></span>

<span data-ttu-id="0831f-104">Antes de fazer o primeiro backup do Lync Server, configure o hardware e o software necessários para armazenar e manter os backups.</span><span class="sxs-lookup"><span data-stu-id="0831f-104">Before you take your first backup of Lync Server, set up the hardware and software that you need in order to store and maintain the backups.</span></span> <span data-ttu-id="0831f-105">Você deve obter acesso à mídia e conteúdo, conforme apropriado, e fornecer conectividade de rede entre cada servidor para backup e a mídia de backup.</span><span class="sxs-lookup"><span data-stu-id="0831f-105">You need to obtain access to the media and content, as appropriate, and provide network connectivity between each server to be backed up and the backup media.</span></span> <span data-ttu-id="0831f-106">A mídia e o local que você usa devem ser definidos em sua estratégia de backup e restauração.</span><span class="sxs-lookup"><span data-stu-id="0831f-106">The media and location that you use should be defined in your backup and restoration strategy.</span></span> <span data-ttu-id="0831f-107">O local usado para backups regulares pode ser local ou remoto, mas deve ser seguro e deve estar acessível para backup e restauração.</span><span class="sxs-lookup"><span data-stu-id="0831f-107">The location that you use for regular backups can be local or remote, but it must be secure, and it must be accessible for both backup and restoration.</span></span> <span data-ttu-id="0831f-108">Recomendamos o uso de um local remoto para proteger contra um evento catastrófico em seu local principal.</span><span class="sxs-lookup"><span data-stu-id="0831f-108">We recommend using a remote location to protect against a catastrophic event at your primary site.</span></span>

<span data-ttu-id="0831f-109">Após configurar e testar os componentes individuais, verifique a acessibilidade aos backups a partir de cada servidor.</span><span class="sxs-lookup"><span data-stu-id="0831f-109">After you set up and test the individual components, verify accessibility to the backups from each server.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

