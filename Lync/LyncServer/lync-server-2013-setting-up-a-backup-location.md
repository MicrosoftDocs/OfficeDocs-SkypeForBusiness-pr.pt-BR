---
title: 'Lync Server 2013: Configurando um local de backup'
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
ms.openlocfilehash: 723bcbc2aeaae5264645d824a9b10a939b6770ab
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41764627"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="setting-up-a-backup-location-for-lync-server-2013"></a><span data-ttu-id="bb093-102">Configurar um local de backup para o Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="bb093-102">Setting up a backup location for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="bb093-103">_**Tópico da última modificação:** 2013-02-17_</span><span class="sxs-lookup"><span data-stu-id="bb093-103">_**Topic Last Modified:** 2013-02-17_</span></span>

<span data-ttu-id="bb093-104">Antes de fazer o primeiro backup do Lync Server, configure o hardware e o software necessários para armazenar e manter os backups.</span><span class="sxs-lookup"><span data-stu-id="bb093-104">Before you take your first backup of Lync Server, set up the hardware and software that you need in order to store and maintain the backups.</span></span> <span data-ttu-id="bb093-105">Você precisa obter acesso à mídia e ao conteúdo, conforme apropriado, e fornecer conectividade de rede entre cada servidor para fazer backup e a mídia de backup.</span><span class="sxs-lookup"><span data-stu-id="bb093-105">You need to obtain access to the media and content, as appropriate, and provide network connectivity between each server to be backed up and the backup media.</span></span> <span data-ttu-id="bb093-106">A mídia e o local que você usa devem ser definidos na estratégia de backup e restauração.</span><span class="sxs-lookup"><span data-stu-id="bb093-106">The media and location that you use should be defined in your backup and restoration strategy.</span></span> <span data-ttu-id="bb093-107">O local que você usa para fazer backups regulares pode ser local ou remoto, mas ele deve ser seguro e deve estar acessível para backup e restauração.</span><span class="sxs-lookup"><span data-stu-id="bb093-107">The location that you use for regular backups can be local or remote, but it must be secure, and it must be accessible for both backup and restoration.</span></span> <span data-ttu-id="bb093-108">Recomendamos usar um local remoto para se proteger contra um evento catastrófico em seu local principal.</span><span class="sxs-lookup"><span data-stu-id="bb093-108">We recommend using a remote location to protect against a catastrophic event at your primary site.</span></span>

<span data-ttu-id="bb093-109">Depois de configurar e testar os componentes individuais, verifique a acessibilidade aos backups de cada servidor.</span><span class="sxs-lookup"><span data-stu-id="bb093-109">After you set up and test the individual components, verify accessibility to the backups from each server.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

