---
title: 'Lync Server 2013: Adicionar ou remover um servidor front-end'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Add or remove a Front End Server
ms:assetid: ab748733-6bad-4c93-8dda-db8d5271653d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205153(v=OCS.15)
ms:contentKeyID: 48185050
ms.date: 01/21/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 078c3d8eed34e7fb6fd98d2d7c12014b87a0497b
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41724011"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="add-or-remove-a-front-end-server-in-lync-server-2013"></a><span data-ttu-id="716e1-102">Add or remove a Front End Server in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="716e1-102">Add or remove a Front End Server in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="716e1-103">_**Tópico da última modificação:** 2016-01-21_</span><span class="sxs-lookup"><span data-stu-id="716e1-103">_**Topic Last Modified:** 2016-01-21_</span></span>

<span data-ttu-id="716e1-104">Ao adicionar um servidor front-end a um pool ou remover um servidor front-end de um pool, você precisará reiniciar o pool.</span><span class="sxs-lookup"><span data-stu-id="716e1-104">When you add a Front End Server to a pool, or remove a Front End Server from a pool, you then need to restart the pool.</span></span> <span data-ttu-id="716e1-105">Para evitar qualquer interrupção do serviço para os usuários, use o procedimento a seguir ao adicionar ou remover um servidor front-end.</span><span class="sxs-lookup"><span data-stu-id="716e1-105">To prevent any interruption of service to users, use the following procedure when adding or removing a Front End Server.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="716e1-106">Se estiver adicionando novos servidores ao pool, atualize os novos servidores do pool no mesmo nível de Atualização Cumulativa dos servidores existentes no Pool.</span><span class="sxs-lookup"><span data-stu-id="716e1-106">If you're adding new servers to the pool, update your new pool servers to be at the same Cumulative Update level as the existing servers in the Pool.</span></span>



</div>

<div>

## <a name="to-add-or-remove-front-end-servers"></a><span data-ttu-id="716e1-107">Para adicionar ou remover servidores de front-end</span><span class="sxs-lookup"><span data-stu-id="716e1-107">To add or remove Front End servers</span></span>

1.  <span data-ttu-id="716e1-108">Se você estiver removendo qualquer servidor front-end, primeiro interrompa novas conexões para esses servidores.</span><span class="sxs-lookup"><span data-stu-id="716e1-108">If you are removing any Front End Servers, first stop new connections to those servers.</span></span> <span data-ttu-id="716e1-109">Para fazer isso, é possível usar o seguinte cmdlet:</span><span class="sxs-lookup"><span data-stu-id="716e1-109">To do so, you can use the following cmdlet:</span></span>
    
        Stop-CsWindowsServices -Graceful

2.  <span data-ttu-id="716e1-110">Quando os servidores que estão sendo removidos não tiverem sessões atuais, interrompa os serviços do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="716e1-110">When the servers being removed have no current sessions, stop Lync Server services on them.</span></span>

3.  <span data-ttu-id="716e1-111">Abra o construtor de topologias e adicione ou remova os servidores necessários.</span><span class="sxs-lookup"><span data-stu-id="716e1-111">Open Topology Builder, and add or remove the necessary servers.</span></span>

4.  <span data-ttu-id="716e1-112">Publique a topologia.</span><span class="sxs-lookup"><span data-stu-id="716e1-112">Publish the topology.</span></span>

5.  <span data-ttu-id="716e1-113">Se o pool deixou de ter dois servidores front-end para mais de dois ou sair de mais de dois servidores para exatamente dois, você precisará digitar o seguinte cmdlet:</span><span class="sxs-lookup"><span data-stu-id="716e1-113">If the pool has gone from having two Front End Servers to more than two, or gone from more than two servers to exactly two, you need to type the following cmdlet:</span></span>
    
        Reset-CsPoolRegistrarState-ResetType FullReset -PoolFqdn <PoolFqdn>
    
    <span data-ttu-id="716e1-114">Se o pool tiver três ou mais servidores, pelo menos três desses servidores deverão estar em execução quando você digitar esse cmdlet.</span><span class="sxs-lookup"><span data-stu-id="716e1-114">If the pool has three or more servers, then at least three of those servers must be running when you type this cmdlet.</span></span>

6.  <span data-ttu-id="716e1-115">Reinicie todos os servidores front-end do pool, um de cada vez.</span><span class="sxs-lookup"><span data-stu-id="716e1-115">Restart all Front End Servers in the pool, one at a time.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

