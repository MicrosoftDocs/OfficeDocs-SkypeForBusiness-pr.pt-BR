---
title: 'Lync Server 2013: Failback de pool'
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
ms.openlocfilehash: 91e1dca7ffc210e9b44913f21846726f7a776912
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41756175"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="failing-back-a-pool-in-lync-server-2013"></a><span data-ttu-id="5779a-102">Failback de pool no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5779a-102">Failing back a pool in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5779a-103">_**Tópico da última modificação:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="5779a-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="5779a-104">Após o pool que sofreu o desastre ficar online novamente (ou seja, Pool1 neste exemplo), siga as etapas a seguir para restaurar a implantação para o status de trabalho normal.</span><span class="sxs-lookup"><span data-stu-id="5779a-104">After the pool that experienced the disaster is back online (that is, Pool1 in this example), take the following steps to restore your deployment to regular working status.</span></span>

<span data-ttu-id="5779a-105">Observe que o processo de failback demora vários minutos para ser concluído.</span><span class="sxs-lookup"><span data-stu-id="5779a-105">Note that the failback process takes several minute to complete.</span></span><span data-ttu-id="5779a-106">Para referência, a expectativa é de até 60 minutos para um pool de 20.000 usuários.</span><span class="sxs-lookup"><span data-stu-id="5779a-106">  For reference, it is expected to take up to 60 minutes for a pool of 20,000 users.</span></span>

1.  <span data-ttu-id="5779a-107">Reproduza os usuários que estavam originalmente hospedados no Pool1 e que falharam no Pool2 digitando o seguinte cmdlet:</span><span class="sxs-lookup"><span data-stu-id="5779a-107">Fail back the users who were originally homed in Pool1 and have been failed over to Pool2 by typing the following cmdlet:</span></span>
    
        Invoke-CsPoolFailback -PoolFQDN <Pool1 FQDN> -Verbose

<span data-ttu-id="5779a-108">Nenhuma outra etapa é necessária.</span><span class="sxs-lookup"><span data-stu-id="5779a-108">No other steps are necessary.</span></span> <span data-ttu-id="5779a-109">Se você tiver reprovado o servidor central de gerenciamento, poderá deixá-lo no Pool2.</span><span class="sxs-lookup"><span data-stu-id="5779a-109">If you failed over the Central Management Server, you can leave it in Pool2.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

