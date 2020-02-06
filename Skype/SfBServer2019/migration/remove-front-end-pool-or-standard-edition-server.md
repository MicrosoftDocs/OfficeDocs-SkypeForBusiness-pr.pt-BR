---
title: Remover um pool Front-End ou um servidor Standard Edition
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Este tópico fornece orientações sobre o processo de remoção de um pool de front-end ou um servidor front-end Standard Edition. Quando você remove um pool de front-end, Remove cada servidor front-end que pertence ao pool como parte do processo de remoção de pool. Quando você remove um servidor front-end padrão da edição, deve remover a definição do SQL Store do construtor de topologias.
ms.openlocfilehash: d3397b47f94a96cde3326b2479a9e5c6ffd365e6
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41812999"
---
# <a name="remove-front-end-pool-or-standard-edition-server"></a><span data-ttu-id="4c2dd-105">Remover um pool Front-End ou um servidor Standard Edition</span><span class="sxs-lookup"><span data-stu-id="4c2dd-105">Remove Front End pool or Standard Edition server</span></span>

<span data-ttu-id="4c2dd-106">Este artigo orienta você pelo processo de remoção de um pool de front-end ou um servidor front-end Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="4c2dd-106">This article guides you through the process of removing a Front End pool or a Standard Edition Front End Server.</span></span> <span data-ttu-id="4c2dd-107">Quando você remove um pool de front-end, Remove cada servidor front-end que pertence ao pool como parte do processo de remoção de pool.</span><span class="sxs-lookup"><span data-stu-id="4c2dd-107">When you remove a Front End pool, you remove each Front End Server that belongs to the pool as a part of the pool removal process.</span></span> <span data-ttu-id="4c2dd-108">Quando você remove um servidor front-end padrão da edição, deve remover a definição do SQL Store do construtor de topologias.</span><span class="sxs-lookup"><span data-stu-id="4c2dd-108">When you remove a Standard Edition Front End Server, you must remove the SQL Store definition from Topology Builder.</span></span>
  
## <a name="to-remove-a-front-end-server-pool"></a><span data-ttu-id="4c2dd-109">Para remover um pool de servidores front-end</span><span class="sxs-lookup"><span data-stu-id="4c2dd-109">To remove a Front End Server pool</span></span>

1. <span data-ttu-id="4c2dd-110">Abrir o construtor de topologias.</span><span class="sxs-lookup"><span data-stu-id="4c2dd-110">Open Topology Builder.</span></span>
    
2. <span data-ttu-id="4c2dd-111">Navegue até o nó herdado.</span><span class="sxs-lookup"><span data-stu-id="4c2dd-111">Navigate to the legacy node.</span></span>
    
3. <span data-ttu-id="4c2dd-112">Expanda **pools de front-end do Enterprise Edition**, expanda o pool de front-ends, clique com o botão direito do mouse no pool de front-ends que você deseja remover e clique em **excluir**.</span><span class="sxs-lookup"><span data-stu-id="4c2dd-112">Expand **Enterprise Edition Front End pools**, expand the Front End pool, right-click the Front End pool that you want to remove, and then click **Delete**.</span></span>
    
4. <span data-ttu-id="4c2dd-113">Publique a topologia, verifique o status da replicação e execute o assistente de implantação herdado conforme necessário.</span><span class="sxs-lookup"><span data-stu-id="4c2dd-113">Publish the topology, check replication status, and then run the legacy Deployment Wizard as needed.</span></span> 
    
## <a name="to-remove-a-standard-edition-front-end-server"></a><span data-ttu-id="4c2dd-114">Para remover um servidor front-end padrão da edição</span><span class="sxs-lookup"><span data-stu-id="4c2dd-114">To remove a Standard Edition Front End server</span></span>

1. <span data-ttu-id="4c2dd-115">Abrir o construtor de topologias.</span><span class="sxs-lookup"><span data-stu-id="4c2dd-115">Open Topology Builder.</span></span>
    
2. <span data-ttu-id="4c2dd-116">Navegue até o nó instalações herdadas.</span><span class="sxs-lookup"><span data-stu-id="4c2dd-116">Navigate to the legacy installs node.</span></span>
    
3. <span data-ttu-id="4c2dd-117">Expanda **servidores front-end padrão da edição**, clique com o botão direito do mouse no servidor front-end que você deseja remover e, em seguida, clique em **excluir**.</span><span class="sxs-lookup"><span data-stu-id="4c2dd-117">Expand **Standard Edition Front End servers**, right-click the Front End Server that you want to remove, and then click **Delete**.</span></span>
    
4. <span data-ttu-id="4c2dd-118">Expanda **repositórios SQL**, clique com o botão direito do mouse no banco de dados do SQL Server associado ao servidor front-end Standard Edition e clique em **excluir**.</span><span class="sxs-lookup"><span data-stu-id="4c2dd-118">Expand **SQL stores**, right-click the SQL Server database that is associated with the Standard Edition Front End Server, and then click **Delete**.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="4c2dd-119">Você deve remover a definição dos bancos de dados do SQL Server posicionado do servidor front-end da Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="4c2dd-119">You must remove the definition of the collocated SQL Server databases from the Standard Edition Front End Server.</span></span> 
  
5. <span data-ttu-id="4c2dd-120">Publique a topologia, verifique o status da replicação e execute o assistente de implantação conforme necessário.</span><span class="sxs-lookup"><span data-stu-id="4c2dd-120">Publish the topology, check replication status, and then run the Deployment Wizard as needed.</span></span> 
    

