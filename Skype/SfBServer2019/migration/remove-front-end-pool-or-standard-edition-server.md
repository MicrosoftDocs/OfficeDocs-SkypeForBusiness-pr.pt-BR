---
title: Remover um pool Front-End ou um servidor Standard Edition
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Este tópico orienta você durante o processo de remoção de um pool de front-ends ou de um servidor front-end Standard Edition. Ao remover um pool de front-ends, você remove cada servidor de front-end que pertence ao pool como parte do processo de remoção do pool. Ao remover um servidor front-end Standard Edition, você deve remover a definição do repositório SQL do construtor de topologias.
ms.openlocfilehash: 305a353ced45fe7e21ba479c0c3571df236aa09b
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/16/2020
ms.locfileid: "44752273"
---
# <a name="remove-front-end-pool-or-standard-edition-server"></a><span data-ttu-id="26d85-105">Remover um pool Front-End ou um servidor Standard Edition</span><span class="sxs-lookup"><span data-stu-id="26d85-105">Remove Front End pool or Standard Edition server</span></span>

<span data-ttu-id="26d85-106">Este artigo orienta você durante o processo de remoção de um pool de front-ends ou um servidor front-end Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="26d85-106">This article guides you through the process of removing a Front End pool or a Standard Edition Front End Server.</span></span> <span data-ttu-id="26d85-107">Ao remover um pool de front-ends, você remove cada servidor de front-end que pertence ao pool como parte do processo de remoção do pool.</span><span class="sxs-lookup"><span data-stu-id="26d85-107">When you remove a Front End pool, you remove each Front End Server that belongs to the pool as a part of the pool removal process.</span></span> <span data-ttu-id="26d85-108">Ao remover um servidor front-end Standard Edition, você deve remover a definição do repositório SQL do construtor de topologias.</span><span class="sxs-lookup"><span data-stu-id="26d85-108">When you remove a Standard Edition Front End Server, you must remove the SQL Store definition from Topology Builder.</span></span>
  
## <a name="to-remove-a-front-end-server-pool"></a><span data-ttu-id="26d85-109">Para remover um pool de Servidor Front-End</span><span class="sxs-lookup"><span data-stu-id="26d85-109">To remove a Front End Server pool</span></span>

1. <span data-ttu-id="26d85-110">Abra o Construtor de Topologia.</span><span class="sxs-lookup"><span data-stu-id="26d85-110">Open Topology Builder.</span></span>
    
2. <span data-ttu-id="26d85-111">Navegue até o nó herdado.</span><span class="sxs-lookup"><span data-stu-id="26d85-111">Navigate to the legacy node.</span></span>
    
3. <span data-ttu-id="26d85-112">Expanda **pools de front-ends Enterprise Edition**, expanda o pool de front-ends, clique com o botão direito do mouse no pool de front-ends que você deseja remover e clique em **excluir**.</span><span class="sxs-lookup"><span data-stu-id="26d85-112">Expand **Enterprise Edition Front End pools**, expand the Front End pool, right-click the Front End pool that you want to remove, and then click **Delete**.</span></span>
    
4. <span data-ttu-id="26d85-113">Publique a topologia, verifique o status da replicação e execute o assistente de implantação herdado conforme necessário.</span><span class="sxs-lookup"><span data-stu-id="26d85-113">Publish the topology, check replication status, and then run the legacy Deployment Wizard as needed.</span></span> 
    
## <a name="to-remove-a-standard-edition-front-end-server"></a><span data-ttu-id="26d85-114">Para remover um Servidor Front-End Standard Edition</span><span class="sxs-lookup"><span data-stu-id="26d85-114">To remove a Standard Edition Front End server</span></span>

1. <span data-ttu-id="26d85-115">Abra o Construtor de Topologia.</span><span class="sxs-lookup"><span data-stu-id="26d85-115">Open Topology Builder.</span></span>
    
2. <span data-ttu-id="26d85-116">Navegue até o nó instalações herdadas.</span><span class="sxs-lookup"><span data-stu-id="26d85-116">Navigate to the legacy installs node.</span></span>
    
3. <span data-ttu-id="26d85-117">Expanda **servidores front-end Standard Edition**, clique com o botão direito do mouse no servidor front-end que você deseja remover e clique em **excluir**.</span><span class="sxs-lookup"><span data-stu-id="26d85-117">Expand **Standard Edition Front End servers**, right-click the Front End Server that you want to remove, and then click **Delete**.</span></span>
    
4. <span data-ttu-id="26d85-118">Expanda **repositórios SQL**, clique com o botão direito do mouse no banco de dados do SQL Server que está associado ao servidor front-end Standard Edition e clique em **excluir**.</span><span class="sxs-lookup"><span data-stu-id="26d85-118">Expand **SQL stores**, right-click the SQL Server database that is associated with the Standard Edition Front End Server, and then click **Delete**.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="26d85-119">Você deve remover a definição dos bancos de dados do SQL Server posicionados do servidor front-end Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="26d85-119">You must remove the definition of the collocated SQL Server databases from the Standard Edition Front End Server.</span></span> 
  
5. <span data-ttu-id="26d85-120">Publique a topologia, verifique o status da replicação e execute o assistente de implantação conforme necessário.</span><span class="sxs-lookup"><span data-stu-id="26d85-120">Publish the topology, check replication status, and then run the Deployment Wizard as needed.</span></span> 
    

