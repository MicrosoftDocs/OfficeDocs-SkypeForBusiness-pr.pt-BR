---
title: Remover a associação de Servidor de Arquivamento
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
description: Para remover um Servidor de Arquivamento, você precisa alterar ou limpar a dependência no pool de Front-End associado, servidor front-end, Aparelho de Filial E Servidor de Filial Survivível. Edite as propriedades do pool de Front-End, servidor front-end, Aparelho de Filial Survivável e Servidor de Filial Survivable para remover a dependência. Depois de limpar a dependência e excluir o servidor no Construtor de Topologias, você será notificado de que o objeto de armazenamento de banco de dados associado no Construtor de Topologias também será excluído.
ms.openlocfilehash: bba21dadc70f5c9f62fea5073ef5bf815c8b35a1
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/16/2020
ms.locfileid: "44752133"
---
# <a name="remove-the-archiving-server-association"></a><span data-ttu-id="9ba5a-105">Remover a associação de Servidor de Arquivamento</span><span class="sxs-lookup"><span data-stu-id="9ba5a-105">Remove the Archiving server association</span></span>

<span data-ttu-id="9ba5a-106">Para remover um Servidor de Arquivamento, você precisa alterar ou limpar a dependência no pool de Front-End associado, servidor front-end, Aparelho de Filial Survivável e Servidor de Filial Survivable.</span><span class="sxs-lookup"><span data-stu-id="9ba5a-106">To remove an Archiving Server, you need to change or clear the dependency on the associated Front End pool, Front End Server, Survivable Branch Appliance, and Survivable Branch Server.</span></span> <span data-ttu-id="9ba5a-107">Edite as propriedades do pool de Front-End, servidor front-end, Aparelho de Filial Survivável e Servidor de Filial Survivable para remover a dependência.</span><span class="sxs-lookup"><span data-stu-id="9ba5a-107">You edit the properties of the Front End pool, Front End Server, Survivable Branch Appliance, and Survivable Branch Server to remove the dependency.</span></span> <span data-ttu-id="9ba5a-108">Depois de limpar a dependência e excluir o servidor no Construtor de Topologias, você será notificado de que o objeto de armazenamento de banco de dados associado no Construtor de Topologias também será excluído.</span><span class="sxs-lookup"><span data-stu-id="9ba5a-108">After you clear the dependency and delete the server in Topology Builder, you are notified that the associated database store object in Topology Builder will also be deleted.</span></span>
  
### <a name="to-remove-the-archiving-server-association"></a><span data-ttu-id="9ba5a-109">Para remover a associação de Servidor de Arquivamento</span><span class="sxs-lookup"><span data-stu-id="9ba5a-109">To remove the Archiving Server association</span></span>

1. <span data-ttu-id="9ba5a-110">No Servidor front-end do Skype for Business Server 2019, abra o Construtor de Topologias.</span><span class="sxs-lookup"><span data-stu-id="9ba5a-110">On the Skype for Business Server 2019 Front End Server, open Topology Builder.</span></span>
    
2. <span data-ttu-id="9ba5a-111">Navegue até o nó de instalação herddo.</span><span class="sxs-lookup"><span data-stu-id="9ba5a-111">Navigate to the legacy install node.</span></span>
    
3. <span data-ttu-id="9ba5a-112">No Construtor de Topologias, **expanda pools de front-end** enterprise edition , **servidores de front-end Standard Edition** ou sites de **filial**, dependendo de onde o Servidor de Arquivamento está definido.</span><span class="sxs-lookup"><span data-stu-id="9ba5a-112">In Topology Builder, expand **Enterprise Edition Front End pools**, **Standard Edition Front End Servers**, or **Branch sites**, depending on where the Archiving Server is defined.</span></span>
    
4. <span data-ttu-id="9ba5a-113">Se você tiver um Servidor de Filial Survivable associado, expanda **os sites** de filial, expanda o nome do site de filial e expanda Aparelhos de Filial **Survivable.**</span><span class="sxs-lookup"><span data-stu-id="9ba5a-113">If you have Survivable Branch Server associated, expand **Branch sites**, expand the branch site name, and then expand **Survivable Branch Appliances**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="9ba5a-114">**Os Aparelhos** de FilialVivíveis na interface do usuário se aplica ao Servidor de Filial Survivable e ao Aparelho de Filial Survivable.</span><span class="sxs-lookup"><span data-stu-id="9ba5a-114">**Survivable Branch Appliances** in the user interface applies to both Survivable Branch Server and Survivable Branch Appliance.</span></span> 
  
5. <span data-ttu-id="9ba5a-115">Clique com o botão direito do mouse no pool, servidor ou dispositivo associado ao Servidor de Arquivamento e clique em **Editar Propriedades.**</span><span class="sxs-lookup"><span data-stu-id="9ba5a-115">Right-click the pool, server, or device that is associated with the Archiving Server, and then click **Edit Properties**.</span></span>
    
6. <span data-ttu-id="9ba5a-116">Em **Editar Propriedades**, em **Associações** Gerais ,  >  **des des** clear the Associate **Archiving Server** check box, and then click **OK**.</span><span class="sxs-lookup"><span data-stu-id="9ba5a-116">In **Edit Properties**, under **General** > **Associations**, clear the **Associate Archiving Server** check box, and then click **OK**.</span></span>
    
7. <span data-ttu-id="9ba5a-117">Repita a etapa anterior para qualquer outro pool, servidor ou dispositivo associado ao Servidor de Arquivamento que você deseja remover.</span><span class="sxs-lookup"><span data-stu-id="9ba5a-117">Repeat the previous step for any other pool, server, or device associated with the Archiving Server that you want to remove.</span></span>
    
8. <span data-ttu-id="9ba5a-118">Clique com o botão direito do mouse no Servidor de Arquivamento e clique em **Excluir.**</span><span class="sxs-lookup"><span data-stu-id="9ba5a-118">Right-click the Archiving Server, and then click **Delete**.</span></span>
    
9. <span data-ttu-id="9ba5a-119">Em **Excluir Repositórios Dependentes**, clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="9ba5a-119">On **Delete Dependent Stores**, click **OK**.</span></span>
    
10. <span data-ttu-id="9ba5a-120">Publique a topologia, verifique o status de replicação e execute o Assistente de Implantação do Skype for Business Server conforme necessário.</span><span class="sxs-lookup"><span data-stu-id="9ba5a-120">Publish the topology, check replication status, and then run the Skype for Business Server Deployment Wizard as needed.</span></span> 
    

