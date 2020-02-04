---
title: 'Lync Server 2013: Restaurando conteúdos de conferência usando o Serviço de Backup'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Restoring conference contents using the Backup Service
ms:assetid: 3e0f18ec-7319-4c07-a59b-2938e7787bc9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688030(v=OCS.15)
ms:contentKeyID: 49733620
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 873ca354ca592eb6bc317b579a0a6f5008e6a172
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41733191"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="restoring-conference-contents-using-the-backup-service-in-lync-server-2013"></a><span data-ttu-id="964d7-102">Restaurando conteúdos de conferência usando o Serviço de Backup no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="964d7-102">Restoring conference contents using the Backup Service in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="964d7-103">_**Tópico da última modificação:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="964d7-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="964d7-104">Se as informações de conferência armazenadas no repositório de arquivos de um pool de front-ends ficarem indisponíveis.</span><span class="sxs-lookup"><span data-stu-id="964d7-104">If the conference information stored in the file store of a Front End pool becomes unavailable.</span></span> <span data-ttu-id="964d7-105">Você deve restaurar essas informações para que os usuários hospedados no pool mantenham seus dados de conferência.</span><span class="sxs-lookup"><span data-stu-id="964d7-105">you must restore this information so that users homed on the pool retain their conference data.</span></span> <span data-ttu-id="964d7-106">Se o pool de front-ends que perdeu dados de conferências estiver emparelhado com outro pool de front-end, você pode usar o serviço de backup para restaurar os dados.</span><span class="sxs-lookup"><span data-stu-id="964d7-106">If the Front End pool which has lost conference data is paired with another Front End pool, you can use the Backup Service to restore the data.</span></span>

<span data-ttu-id="964d7-107">Você também deve realizar essa tarefa se um pool inteiro tiver falhado e tiver que fazer failover de seus usuários para um pool de backup.</span><span class="sxs-lookup"><span data-stu-id="964d7-107">You must also perform this task if an entire pool has failed and you have to fail over its users to a backup pool.</span></span> <span data-ttu-id="964d7-108">Quando esses usuários falham novamente em seu pool original, você deve usar esse procedimento para copiar o conteúdo de conferência de volta para o pool original também.</span><span class="sxs-lookup"><span data-stu-id="964d7-108">When these users are failed back over to their original pool, you must use this procedure to copy their conference content back to their original pool as well.</span></span>

<span data-ttu-id="964d7-109">Suponha que o Pool1 está emparelhado com Pool2, e os dados de conferência no Pool1 são perdidos.</span><span class="sxs-lookup"><span data-stu-id="964d7-109">Assume that Pool1 is paired with Pool2, and the conference data in Pool1 is lost.</span></span> <span data-ttu-id="964d7-110">Você pode usar o cmdlet a seguir para invocar o serviço de backup para restaurar o conteúdo:</span><span class="sxs-lookup"><span data-stu-id="964d7-110">You can use the following cmdlet to invoke the Backup Service to restore the contents:</span></span>

    Invoke-CsBackupServiceSync -PoolFqdn <Pool2 FQDN> -BackupModule ConfServices.DataConf

<span data-ttu-id="964d7-111">A restauração do conteúdo da conferência pode levar algum tempo, dependendo do tamanho.</span><span class="sxs-lookup"><span data-stu-id="964d7-111">Restoring the conference contents may take some time, depending on their size.</span></span> <span data-ttu-id="964d7-112">Você pode usar o cmdlet a seguir para verificar o status do processo:</span><span class="sxs-lookup"><span data-stu-id="964d7-112">You can use the following cmdlet to check the process status:</span></span>

    Get-CsBackupServiceStatus -PoolFqdn <Pool2 FQDN> -BackupModule ConfServices.DataConf

<span data-ttu-id="964d7-113">O processo é feito quando esse cmdlet retorna um valor de estado Steady para o módulo de conferência de dados.</span><span class="sxs-lookup"><span data-stu-id="964d7-113">The process is done when this cmdlet returns a value of Steady State for the data conference module.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

