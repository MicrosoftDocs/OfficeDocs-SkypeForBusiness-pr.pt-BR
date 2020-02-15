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
ms.openlocfilehash: 1a13a7d618b7d7f8883d43e6aed7ac456bb5ab6c
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/14/2020
ms.locfileid: "42008837"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="add-or-remove-a-front-end-server-in-lync-server-2013"></a><span data-ttu-id="18e9c-102">Adicionar ou remover um servidor front-end no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="18e9c-102">Add or remove a Front End Server in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="18e9c-103">_**Última modificação do tópico:** 2016-01-21_</span><span class="sxs-lookup"><span data-stu-id="18e9c-103">_**Topic Last Modified:** 2016-01-21_</span></span>

<span data-ttu-id="18e9c-p101">Ao adicionar um servidor de Front End a um pool, ou remover um servidor de Front End de um pool, você precisará reiniciar o pool. Para evitar interrupção do serviço aos usuários, siga o procedimento a seguir ao remover ou adicionar um servidor de Front End.</span><span class="sxs-lookup"><span data-stu-id="18e9c-p101">When you add a Front End Server to a pool, or remove a Front End Server from a pool, you then need to restart the pool. To prevent any interruption of service to users, use the following procedure when adding or removing a Front End Server.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="18e9c-106">Se você estiver adicionando novos servidores ao pool, atualize seus servidores de pool novos para que estejam no mesmo nível de atualização cumulativa que os servidores existentes no pool.</span><span class="sxs-lookup"><span data-stu-id="18e9c-106">If you're adding new servers to the pool, update your new pool servers to be at the same Cumulative Update level as the existing servers in the Pool.</span></span>



</div>

<div>

## <a name="to-add-or-remove-front-end-servers"></a><span data-ttu-id="18e9c-107">Para adicionar ou remover servidores de front-end</span><span class="sxs-lookup"><span data-stu-id="18e9c-107">To add or remove Front End servers</span></span>

1.  <span data-ttu-id="18e9c-p102">Se estiver removendo servidores de Front End, primeiro interrompa novas conexões a esses servidores. Para fazer isso, é possível usar o seguinte cmdlet:</span><span class="sxs-lookup"><span data-stu-id="18e9c-p102">If you are removing any Front End Servers, first stop new connections to those servers. To do so, you can use the following cmdlet:</span></span>
    
        Stop-CsWindowsServices -Graceful

2.  <span data-ttu-id="18e9c-110">Quando os servidores sendo removidos não têm sessões atuais, interrompa os serviços do Lync Server neles.</span><span class="sxs-lookup"><span data-stu-id="18e9c-110">When the servers being removed have no current sessions, stop Lync Server services on them.</span></span>

3.  <span data-ttu-id="18e9c-111">Abra o Construtor de Topologias, e adiciona ou remova os servidores necessários.</span><span class="sxs-lookup"><span data-stu-id="18e9c-111">Open Topology Builder, and add or remove the necessary servers.</span></span>

4.  <span data-ttu-id="18e9c-112">Publique a topologia.</span><span class="sxs-lookup"><span data-stu-id="18e9c-112">Publish the topology.</span></span>

5.  <span data-ttu-id="18e9c-113">Se o pool saiu de dois servidores front-end para mais de dois ou de mais de dois servidores para exatamente dois, você precisará digitar o seguinte cmdlet:</span><span class="sxs-lookup"><span data-stu-id="18e9c-113">If the pool has gone from having two Front End Servers to more than two, or gone from more than two servers to exactly two, you need to type the following cmdlet:</span></span>
    
        Reset-CsPoolRegistrarState-ResetType FullReset -PoolFqdn <PoolFqdn>
    
    <span data-ttu-id="18e9c-114">Se o pool tinha três ou mais servidores, então pelo menos três desses servidores deve ser executado ao digitar esse cmdlet.</span><span class="sxs-lookup"><span data-stu-id="18e9c-114">If the pool has three or more servers, then at least three of those servers must be running when you type this cmdlet.</span></span>

6.  <span data-ttu-id="18e9c-115">Reinicie todos os servidores front-end no pool, um de cada vez.</span><span class="sxs-lookup"><span data-stu-id="18e9c-115">Restart all Front End Servers in the pool, one at a time.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

