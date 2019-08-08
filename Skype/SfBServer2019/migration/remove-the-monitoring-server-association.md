---
title: Remover a associação do Servidor de Monitoramento
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Para remover o Monitoring Server, você precisa alterar ou limpar a dependência do pool de front-ends associado, servidor front-end, aparelho para ramificação sobreviventes e servidor de ramificação sobreviventes. Edite as propriedades do pool de front-end, servidor front-end, appliances para ramificação sobreviventes e servidor de ramificação sobreviventes para remover a dependência. Depois de limpar a dependência e excluir o servidor no construtor de topologias, você será notificado de que o objeto de repositório de banco de dados associado também será excluído.
ms.openlocfilehash: ecad0a447bacacf2a894bdb735b97b3a8593b1c8
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/07/2019
ms.locfileid: "36244120"
---
# <a name="remove-the-monitoring-server-association"></a><span data-ttu-id="dc42b-105">Remover a associação do Servidor de Monitoramento</span><span class="sxs-lookup"><span data-stu-id="dc42b-105">Remove the Monitoring server association</span></span>

<span data-ttu-id="dc42b-106">Para remover o Monitoring Server, você precisa alterar ou limpar a dependência do pool de front-ends associado, servidor front-end, aparelho para ramificação sobreviventes e servidor de ramificação sobreviventes.</span><span class="sxs-lookup"><span data-stu-id="dc42b-106">To remove the Monitoring Server, you need to change or clear the dependency on the associated Front End pool, Front End Server, Survivable Branch Appliance, and Survivable Branch Server.</span></span> <span data-ttu-id="dc42b-107">Edite as propriedades do pool de front-end, do servidor front-end, do Appliance para ramificação sobreviventes e do servidor de ramificação sobreviventes para remover a dependência.</span><span class="sxs-lookup"><span data-stu-id="dc42b-107">You edit the properties of the Front End pool, Front End Server, Survivable Branch Appliance, and Survivable Branch Server to remove the dependency.</span></span> <span data-ttu-id="dc42b-108">Depois de limpar a dependência e excluir o servidor no construtor de topologias, você será notificado de que o objeto de repositório de banco de dados associado também será excluído.</span><span class="sxs-lookup"><span data-stu-id="dc42b-108">After you clear the dependency and delete the server in Topology Builder, you are notified that the associated database store object in Topology Builder will also be deleted.</span></span>
  
### <a name="to-remove-the-monitoring-server-association"></a><span data-ttu-id="dc42b-109">Para remover a associação do Monitoring Server</span><span class="sxs-lookup"><span data-stu-id="dc42b-109">To remove the Monitoring Server association</span></span>

1. <span data-ttu-id="dc42b-110">No servidor front-end do Skype for Business Server 2019, abra o construtor de topologias.</span><span class="sxs-lookup"><span data-stu-id="dc42b-110">On the Skype for Business Server 2019 Front End Server, open Topology Builder.</span></span>
    
2. <span data-ttu-id="dc42b-111">Navegue até o nó instalações herdadas.</span><span class="sxs-lookup"><span data-stu-id="dc42b-111">Navigate to the legacy installs node.</span></span>
    
3. <span data-ttu-id="dc42b-112">No construtor de topologia, expanda Pools de **front-end do Enterprise Edition**, **servidores front-end da edição padrão**ou **sites**de filiais, dependendo de onde o servidor de monitoração está definido.</span><span class="sxs-lookup"><span data-stu-id="dc42b-112">In Topology Builder, expand **Enterprise Edition Front End pools**, **Standard Edition Front End Servers**, or **Branch sites**, depending on where the Monitoring Server is defined.</span></span>
    
4. <span data-ttu-id="dc42b-113">Se você tiver um servidor de ramificação sobreviventes associado, expanda **sites**de ramificação, expanda o nome do site da filial e expanda **aparelhos de ramificação sobreviventes**.</span><span class="sxs-lookup"><span data-stu-id="dc42b-113">If you have Survivable Branch Server associated, expand **Branch sites**, expand the branch site name, and then expand **Survivable Branch Appliances**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="dc42b-114">**Aparelhos de ramificação sobreviventes** na interface do usuário se aplicam ao servidor de ramificação sobreviventes e ao aparelho de ramificação sobreviventes.</span><span class="sxs-lookup"><span data-stu-id="dc42b-114">**Survivable Branch Appliances** in the user interface applies to both Survivable Branch Server and Survivable Branch Appliance.</span></span> 
  
5. <span data-ttu-id="dc42b-115">Clique com o botão direito do mouse no pool, no servidor ou no dispositivo associado ao Monitoring Server e clique em **Editar propriedades**.</span><span class="sxs-lookup"><span data-stu-id="dc42b-115">Right-click the pool, server, or device that is associated with the Monitoring Server, and then click **Edit Properties**.</span></span>
    
6. <span data-ttu-id="dc42b-116">Em **Editar propriedades**, em \*\*\*\* > **associações**gerais, desmarque a caixa de seleção **associar o servidor de monitoramento** e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="dc42b-116">In **Edit Properties**, under **General** > **Associations**, clear the **Associate Monitoring Server** check box, and then click **OK**.</span></span>
    
7. <span data-ttu-id="dc42b-117">Repita a etapa anterior para qualquer outro pool, servidor ou dispositivo associado ao servidor de monitoramento.</span><span class="sxs-lookup"><span data-stu-id="dc42b-117">Repeat the previous step for any other pool, server, or device associated with the Monitoring Server.</span></span>
    
8. <span data-ttu-id="dc42b-118">Clique com o botão direito do mouse no servidor de monitoramento e clique em **excluir**.</span><span class="sxs-lookup"><span data-stu-id="dc42b-118">Right-click the Monitoring Server, and then click **Delete**.</span></span> 
    
9. <span data-ttu-id="dc42b-119">Em **excluir repositórios dependentes**, clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="dc42b-119">On **Delete Dependent Stores**, click **OK**.</span></span>
    
10. <span data-ttu-id="dc42b-120">Publique a topologia, verifique o status da replicação e execute o assistente de implantação do Skype for Business Server conforme necessário.</span><span class="sxs-lookup"><span data-stu-id="dc42b-120">Publish the topology, check replication status, and run the Skype for Business Server Deployment Wizard as needed.</span></span> 
    

