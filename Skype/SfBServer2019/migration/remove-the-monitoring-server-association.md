---
title: Remover a associação do Servidor de Monitoramento
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
description: Para remover o Monitoring Server, você precisa alterar ou limpar a dependência no pool de front-end, servidor front-end, aparelho de filial e servidor de filial survivível associado. Edite as propriedades do pool de Front-End, servidor front-end, Aparelho de Filial Survivável e Servidor de Filial Survivable para remover a dependência. Depois de limpar a dependência e excluir o servidor no Construtor de Topologias, você será notificado de que o objeto de armazenamento de banco de dados associado no Construtor de Topologias também será excluído.
ms.openlocfilehash: dafbeb88773330164a5daf2144988d1afb2776a8
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/16/2020
ms.locfileid: "44753413"
---
# <a name="remove-the-monitoring-server-association"></a><span data-ttu-id="db2a6-105">Remover a associação do Servidor de Monitoramento</span><span class="sxs-lookup"><span data-stu-id="db2a6-105">Remove the Monitoring server association</span></span>

<span data-ttu-id="db2a6-106">Para remover o Monitoring Server, você precisa alterar ou limpar a dependência no pool de front-end, servidor front-end, aparelho de filial e servidor de filial sobrevivência associado.</span><span class="sxs-lookup"><span data-stu-id="db2a6-106">To remove the Monitoring Server, you need to change or clear the dependency on the associated Front End pool, Front End Server, Survivable Branch Appliance, and Survivable Branch Server.</span></span> <span data-ttu-id="db2a6-107">Edite as propriedades do pool de Front-End, servidor front-end, Aparelho de Filial Survivável e Servidor de Filial Survivable para remover a dependência.</span><span class="sxs-lookup"><span data-stu-id="db2a6-107">You edit the properties of the Front End pool, Front End Server, Survivable Branch Appliance, and Survivable Branch Server to remove the dependency.</span></span> <span data-ttu-id="db2a6-108">Depois de limpar a dependência e excluir o servidor no Construtor de Topologias, você será notificado de que o objeto de armazenamento de banco de dados associado no Construtor de Topologias também será excluído.</span><span class="sxs-lookup"><span data-stu-id="db2a6-108">After you clear the dependency and delete the server in Topology Builder, you are notified that the associated database store object in Topology Builder will also be deleted.</span></span>
  
### <a name="to-remove-the-monitoring-server-association"></a><span data-ttu-id="db2a6-109">Para remover a associação do Servidor de Monitoramento</span><span class="sxs-lookup"><span data-stu-id="db2a6-109">To remove the Monitoring Server association</span></span>

1. <span data-ttu-id="db2a6-110">No Servidor front-end do Skype for Business Server 2019, abra o Construtor de Topologias.</span><span class="sxs-lookup"><span data-stu-id="db2a6-110">On the Skype for Business Server 2019 Front End Server, open Topology Builder.</span></span>
    
2. <span data-ttu-id="db2a6-111">Navegue até o nó de instalação herdam.</span><span class="sxs-lookup"><span data-stu-id="db2a6-111">Navigate to the legacy installs node.</span></span>
    
3. <span data-ttu-id="db2a6-112">No Construtor de Topologias, **expanda pools de Front-End** Enterprise Edition , **Servidores front-end Standard Edition** ou **sites** de filial, dependendo de onde o Monitoring Server está definido.</span><span class="sxs-lookup"><span data-stu-id="db2a6-112">In Topology Builder, expand **Enterprise Edition Front End pools**, **Standard Edition Front End Servers**, or **Branch sites**, depending on where the Monitoring Server is defined.</span></span>
    
4. <span data-ttu-id="db2a6-113">Se você tiver um Servidor de Filial Survivable associado, expanda **os sites** de filial, expanda o nome do site de filial e expanda Aparelhos de Filial **Survivable.**</span><span class="sxs-lookup"><span data-stu-id="db2a6-113">If you have Survivable Branch Server associated, expand **Branch sites**, expand the branch site name, and then expand **Survivable Branch Appliances**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="db2a6-114">**Os Aparelhos** de FilialVivíveis na interface do usuário se aplica ao Servidor de Filial Survivable e ao Aparelho de Filial Survivable.</span><span class="sxs-lookup"><span data-stu-id="db2a6-114">**Survivable Branch Appliances** in the user interface applies to both Survivable Branch Server and Survivable Branch Appliance.</span></span> 
  
5. <span data-ttu-id="db2a6-115">Clique com o botão direito do mouse no pool, servidor ou dispositivo associado ao Monitoring Server e clique em **Editar Propriedades.**</span><span class="sxs-lookup"><span data-stu-id="db2a6-115">Right-click the pool, server, or device that is associated with the Monitoring Server, and then click **Edit Properties**.</span></span>
    
6. <span data-ttu-id="db2a6-116">Em **Editar Propriedades**, em **Associações** Gerais , des marque a caixa de seleção Associar  >   **Monitoring Server** e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="db2a6-116">In **Edit Properties**, under **General** > **Associations**, clear the **Associate Monitoring Server** check box, and then click **OK**.</span></span>
    
7. <span data-ttu-id="db2a6-117">Repita a etapa anterior para qualquer outro pool, servidor ou dispositivo associado ao Monitoring Server.</span><span class="sxs-lookup"><span data-stu-id="db2a6-117">Repeat the previous step for any other pool, server, or device associated with the Monitoring Server.</span></span>
    
8. <span data-ttu-id="db2a6-118">Clique com o botão direito do mouse no Monitoring Server e clique em **Excluir.**</span><span class="sxs-lookup"><span data-stu-id="db2a6-118">Right-click the Monitoring Server, and then click **Delete**.</span></span> 
    
9. <span data-ttu-id="db2a6-119">Em **Excluir Repositórios Dependentes**, clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="db2a6-119">On **Delete Dependent Stores**, click **OK**.</span></span>
    
10. <span data-ttu-id="db2a6-120">Publique a topologia, verifique o status de replicação e execute o Assistente de Implantação do Skype for Business Server conforme necessário.</span><span class="sxs-lookup"><span data-stu-id="db2a6-120">Publish the topology, check replication status, and run the Skype for Business Server Deployment Wizard as needed.</span></span> 
    

