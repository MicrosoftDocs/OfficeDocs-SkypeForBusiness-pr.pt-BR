---
title: Remover um pool Front-End ou um servidor Standard Edition
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Este tópico o orienta o processo de remoção de um pool de Front-End ou um Standard Edition servidor Front-End. Quando você remover um pool de Front-End, você pode remover cada servidor Front-End que pertence ao pool como parte do processo de remoção do pool. Quando você remove um Standard Edition servidor Front-End, você deve remover a definição de repositório SQL do construtor de topologia.
ms.openlocfilehash: 394edcd6f5c89478ed98abebe0be29720d009107
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32231543"
---
# <a name="remove-front-end-pool-or-standard-edition-server"></a><span data-ttu-id="08aed-105">Remover um pool Front-End ou um servidor Standard Edition</span><span class="sxs-lookup"><span data-stu-id="08aed-105">Remove Front End pool or Standard Edition server</span></span>

<span data-ttu-id="08aed-106">Este artigo o orienta o processo de remoção de um pool de Front-End ou um Standard Edition servidor Front-End.</span><span class="sxs-lookup"><span data-stu-id="08aed-106">This article guides you through the process of removing a Front End pool or a Standard Edition Front End Server.</span></span> <span data-ttu-id="08aed-107">Quando você remover um pool de Front-End, você pode remover cada servidor Front-End que pertence ao pool como parte do processo de remoção do pool.</span><span class="sxs-lookup"><span data-stu-id="08aed-107">When you remove a Front End pool, you remove each Front End Server that belongs to the pool as a part of the pool removal process.</span></span> <span data-ttu-id="08aed-108">Quando você remove um Standard Edition servidor Front-End, você deve remover a definição de repositório SQL do construtor de topologia.</span><span class="sxs-lookup"><span data-stu-id="08aed-108">When you remove a Standard Edition Front End Server, you must remove the SQL Store definition from Topology Builder.</span></span>
  
## <a name="to-remove-a-front-end-server-pool"></a><span data-ttu-id="08aed-109">Para remover um pool de servidor Front-End</span><span class="sxs-lookup"><span data-stu-id="08aed-109">To remove a Front End Server pool</span></span>

1. <span data-ttu-id="08aed-110">Abra o construtor de topologia.</span><span class="sxs-lookup"><span data-stu-id="08aed-110">Open Topology Builder.</span></span>
    
2. <span data-ttu-id="08aed-111">Navegue até o nó herdado.</span><span class="sxs-lookup"><span data-stu-id="08aed-111">Navigate to the legacy node.</span></span>
    
3. <span data-ttu-id="08aed-112">Expanda **pools de Front End do Enterprise Edition**, expanda o pool de Front-End, com o botão direito do pool de Front-End que você deseja remover e clique em **Excluir**.</span><span class="sxs-lookup"><span data-stu-id="08aed-112">Expand **Enterprise Edition Front End pools**, expand the Front End pool, right-click the Front End pool that you want to remove, and then click **Delete**.</span></span>
    
4. <span data-ttu-id="08aed-113">Publique a topologia, verifique o status de replicação e execute o Assistente de implantação herdadas conforme necessário.</span><span class="sxs-lookup"><span data-stu-id="08aed-113">Publish the topology, check replication status, and then run the legacy Deployment Wizard as needed.</span></span> 
    
## <a name="to-remove-a-standard-edition-front-end-server"></a><span data-ttu-id="08aed-114">Para remover um servidor de Front End e Standard Edition</span><span class="sxs-lookup"><span data-stu-id="08aed-114">To remove a Standard Edition Front End server</span></span>

1. <span data-ttu-id="08aed-115">Abra o construtor de topologia.</span><span class="sxs-lookup"><span data-stu-id="08aed-115">Open Topology Builder.</span></span>
    
2. <span data-ttu-id="08aed-116">Navegue até o nó de instalações herdadas.</span><span class="sxs-lookup"><span data-stu-id="08aed-116">Navigate to the legacy installs node.</span></span>
    
3. <span data-ttu-id="08aed-117">Expanda **servidores Standard Edition Front-End**, com o botão direito do servidor Front-End que você deseja remover e clique em **Excluir**.</span><span class="sxs-lookup"><span data-stu-id="08aed-117">Expand **Standard Edition Front End servers**, right-click the Front End Server that you want to remove, and then click **Delete**.</span></span>
    
4. <span data-ttu-id="08aed-118">Expanda **SQL armazena**, clique com o botão o banco de dados do SQL Server que está associado a Standard Edition servidor Front-End e, em seguida, clique em **Excluir**.</span><span class="sxs-lookup"><span data-stu-id="08aed-118">Expand **SQL stores**, right-click the SQL Server database that is associated with the Standard Edition Front End Server, and then click **Delete**.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="08aed-119">Você deve remover a definição dos bancos de dados do SQL Server colocados do Standard Edition servidor Front-End.</span><span class="sxs-lookup"><span data-stu-id="08aed-119">You must remove the definition of the collocated SQL Server databases from the Standard Edition Front End Server.</span></span> 
  
5. <span data-ttu-id="08aed-120">Publique a topologia, verifique o status de replicação e, em seguida, execute o Assistente para implantação, conforme necessário.</span><span class="sxs-lookup"><span data-stu-id="08aed-120">Publish the topology, check replication status, and then run the Deployment Wizard as needed.</span></span> 
    

