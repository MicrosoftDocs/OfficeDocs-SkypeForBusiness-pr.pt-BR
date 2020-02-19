---
title: 'Lync Server 2013: failback de um pool'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Failing back a pool
ms:assetid: 6232b644-ef57-4c9c-abec-14ff8ffc9fe7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204945(v=OCS.15)
ms:contentKeyID: 48184289
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e14cca1c42e6e8ab6a0b64c883658cfc5c6a5374
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42134577"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="failing-back-a-pool-in-lync-server-2013"></a><span data-ttu-id="68426-102">Failback de um pool no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="68426-102">Failing back a pool in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="68426-103">_**Última modificação do tópico:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="68426-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="68426-104">Depois que o pool que passou por desastre voltar a ficar online (ou seja, o Pool1 neste exemplo), execute as etapas a seguir para restaurar sua implantação para o status funcional normal.</span><span class="sxs-lookup"><span data-stu-id="68426-104">After the pool that experienced the disaster is back online (that is, Pool1 in this example), take the following steps to restore your deployment to regular working status.</span></span>

<span data-ttu-id="68426-p101">O processo de failback leva vários minutos para ser concluído.  Como referência, espera-se que leve até 60 minutos para um pool de 20 mil usuários.</span><span class="sxs-lookup"><span data-stu-id="68426-p101">Note that the failback process takes several minute to complete.  For reference, it is expected to take up to 60 minutes for a pool of 20,000 users.</span></span>

1.  <span data-ttu-id="68426-107">Para fazer failback dos usuários que estavam originalmente hospedados no Pool1 e dos quais foi feito failover para o Pool2, digite o seguinte cmdlet:</span><span class="sxs-lookup"><span data-stu-id="68426-107">Fail back the users who were originally homed in Pool1 and have been failed over to Pool2 by typing the following cmdlet:</span></span>
    
        Invoke-CsPoolFailback -PoolFQDN <Pool1 FQDN> -Verbose

<span data-ttu-id="68426-108">Nenhuma outra etapa é necessária.</span><span class="sxs-lookup"><span data-stu-id="68426-108">No other steps are necessary.</span></span> <span data-ttu-id="68426-109">Se você tiver falhado no servidor de gerenciamento central, você pode deixá-lo no Pool2.</span><span class="sxs-lookup"><span data-stu-id="68426-109">If you failed over the Central Management Server, you can leave it in Pool2.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

