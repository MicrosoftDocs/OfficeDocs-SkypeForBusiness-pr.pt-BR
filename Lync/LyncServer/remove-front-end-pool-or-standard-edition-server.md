---
title: Remover um pool Front-End ou um servidor Standard Edition
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Remove Front End pool or Standard Edition server
ms:assetid: 83c39a36-49a1-4ac6-9cc5-b0e441b1fdec
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688115(v=OCS.15)
ms:contentKeyID: 49733713
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 69a1c36de9aa3cbd4a46dc0bba4c862734b382ef
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48500048"
---
# <a name="remove-front-end-pool-or-standard-edition-server"></a><span data-ttu-id="0f1fb-102">Remover um pool Front-End ou um servidor Standard Edition</span><span class="sxs-lookup"><span data-stu-id="0f1fb-102">Remove Front End pool or Standard Edition server</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0f1fb-103">_**Última modificação do tópico:** 2012-10-04_</span><span class="sxs-lookup"><span data-stu-id="0f1fb-103">_**Topic Last Modified:** 2012-10-04_</span></span>

<span data-ttu-id="0f1fb-104">Este tópico orienta você durante o processo de remoção de um pool de front-ends ou de um servidor front-end Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="0f1fb-104">This topic guides you through the process of removing a Front End pool or a Standard Edition Front End Server.</span></span> <span data-ttu-id="0f1fb-105">Ao remover um pool de front-ends, você remove cada servidor de front-end que pertence ao pool como parte do processo de remoção do pool.</span><span class="sxs-lookup"><span data-stu-id="0f1fb-105">When you remove a Front End pool, you remove each Front End Server that belongs to the pool as a part of the pool removal process.</span></span> <span data-ttu-id="0f1fb-106">Ao remover um servidor front-end Standard Edition, você deve remover a definição do repositório SQL do construtor de topologias.</span><span class="sxs-lookup"><span data-stu-id="0f1fb-106">When you remove a Standard Edition Front End Server, you must remove the SQL Store definition from Topology Builder.</span></span>

<div>

## <a name="to-remove-a-front-end-server-pool"></a><span data-ttu-id="0f1fb-107">Para remover um pool de Servidor Front-End</span><span class="sxs-lookup"><span data-stu-id="0f1fb-107">To remove a Front End Server pool</span></span>

1.  <span data-ttu-id="0f1fb-108">Abra o Construtor de Topologia.</span><span class="sxs-lookup"><span data-stu-id="0f1fb-108">Open Topology Builder.</span></span>

2.  <span data-ttu-id="0f1fb-109">Navegue até o nó do Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="0f1fb-109">Navigate to the Lync Server 2010 node.</span></span>

3.  <span data-ttu-id="0f1fb-110">Expanda **pools de front-ends Enterprise Edition**, expanda o pool de front-ends, clique com o botão direito do mouse no pool de front-ends que você deseja remover e clique em **excluir**.</span><span class="sxs-lookup"><span data-stu-id="0f1fb-110">Expand **Enterprise Edition Front End pools**, expand the Front End pool, right-click the Front End pool that you want to remove, and then click **Delete**.</span></span>

4.  <span data-ttu-id="0f1fb-111">Publique a topologia, verifique o status da replicação e execute o assistente de implantação do Lync Server conforme necessário.</span><span class="sxs-lookup"><span data-stu-id="0f1fb-111">Publish the topology, check replication status, and then run the Lync Server Deployment Wizard as needed.</span></span>

</div>

<div>

## <a name="to-remove-a-standard-edition-front-end-server"></a><span data-ttu-id="0f1fb-112">Para remover um Servidor Front-End Standard Edition</span><span class="sxs-lookup"><span data-stu-id="0f1fb-112">To remove a Standard Edition Front End server</span></span>

1.  <span data-ttu-id="0f1fb-113">Abra o Construtor de Topologia.</span><span class="sxs-lookup"><span data-stu-id="0f1fb-113">Open Topology Builder.</span></span>

2.  <span data-ttu-id="0f1fb-114">Navegue até o nó do Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="0f1fb-114">Navigate to the Lync Server 2010 node.</span></span>

3.  <span data-ttu-id="0f1fb-115">Expanda **servidores front-end Standard Edition**, clique com o botão direito do mouse no servidor front-end que você deseja remover e clique em **excluir**.</span><span class="sxs-lookup"><span data-stu-id="0f1fb-115">Expand **Standard Edition Front End servers**, right-click the Front End Server that you want to remove, and then click **Delete**.</span></span>

4.  <span data-ttu-id="0f1fb-116">Expanda **repositórios SQL**, clique com o botão direito do mouse no banco de dados do SQL Server que está associado ao servidor front-end Standard Edition e clique em **excluir**.</span><span class="sxs-lookup"><span data-stu-id="0f1fb-116">Expand **SQL stores**, right-click the SQL Server database that is associated with the Standard Edition Front End Server, and then click **Delete**.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="0f1fb-117">Você deve remover a definição dos bancos de dados do SQL Server posicionados do servidor front-end Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="0f1fb-117">You must remove the definition of the collocated SQL Server databases from the Standard Edition Front End Server.</span></span>

    
    </div>

5.  <span data-ttu-id="0f1fb-118">Publique a topologia, verifique o status da replicação e execute o assistente de implantação do Lync Server conforme necessário.</span><span class="sxs-lookup"><span data-stu-id="0f1fb-118">Publish the topology, check replication status, and then run the Lync Server Deployment Wizard as needed.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

