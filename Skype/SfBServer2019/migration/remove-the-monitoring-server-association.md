---
title: Remover a associação do Servidor de Monitoramento
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Para remover o Monitoring Server, você precisará alterar ou desmarque a dependência no pool de Front-End associado, servidor Front-End, o aparelho de filial e o servidor de filial persistente. Você editar as propriedades do pool de Front-End, servidor Front-End, servidor de filial persistente e aparelho de filial persistente para remover a dependência. Depois que você desmarcar a dependência e excluir o servidor no construtor de topologia, você será notificado de que o objeto de armazenamento de banco de dados associado no construtor de topologia também será excluído.
ms.openlocfilehash: 854e95969d08d14d626bb374073091ae4ae39630
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32231455"
---
# <a name="remove-the-monitoring-server-association"></a><span data-ttu-id="0d3e7-105">Remover a associação do Servidor de Monitoramento</span><span class="sxs-lookup"><span data-stu-id="0d3e7-105">Remove the Monitoring server association</span></span>

<span data-ttu-id="0d3e7-106">Para remover o Monitoring Server, você precisará alterar ou desmarque a dependência a associado Front End pool, servidor Front-End, aparelho de filial persistente e servidor de filial persistente.</span><span class="sxs-lookup"><span data-stu-id="0d3e7-106">To remove the Monitoring Server, you need to change or clear the dependency on the associated Front End pool, Front End Server, Survivable Branch Appliance, and Survivable Branch Server.</span></span> <span data-ttu-id="0d3e7-107">Você editar as propriedades do pool Front-End, servidor Front-End, aparelho de filial persistente e servidor de filial persistente para remover a dependência.</span><span class="sxs-lookup"><span data-stu-id="0d3e7-107">You edit the properties of the Front End pool, Front End Server, Survivable Branch Appliance, and Survivable Branch Server to remove the dependency.</span></span> <span data-ttu-id="0d3e7-108">Depois que você desmarcar a dependência e excluir o servidor no construtor de topologia, você será notificado de que o objeto de armazenamento de banco de dados associado no construtor de topologia também será excluído.</span><span class="sxs-lookup"><span data-stu-id="0d3e7-108">After you clear the dependency and delete the server in Topology Builder, you are notified that the associated database store object in Topology Builder will also be deleted.</span></span>
  
### <a name="to-remove-the-monitoring-server-association"></a><span data-ttu-id="0d3e7-109">Para remover a associação do Monitoring Server</span><span class="sxs-lookup"><span data-stu-id="0d3e7-109">To remove the Monitoring Server association</span></span>

1. <span data-ttu-id="0d3e7-110">No Skype para Business Server 2019 servidor Front-End, abra o construtor de topologias.</span><span class="sxs-lookup"><span data-stu-id="0d3e7-110">On the Skype for Business Server 2019 Front End Server, open Topology Builder.</span></span>
    
2. <span data-ttu-id="0d3e7-111">Navegue até o nó de instalações herdadas.</span><span class="sxs-lookup"><span data-stu-id="0d3e7-111">Navigate to the legacy installs node.</span></span>
    
3. <span data-ttu-id="0d3e7-112">No construtor de topologia, expanda **pools de Front End do Enterprise Edition**, **Servidores Standard Edition Front End**ou **sites de filiais**, dependendo de onde o Monitoring Server está definido.</span><span class="sxs-lookup"><span data-stu-id="0d3e7-112">In Topology Builder, expand **Enterprise Edition Front End pools**, **Standard Edition Front End Servers**, or **Branch sites**, depending on where the Monitoring Server is defined.</span></span>
    
4. <span data-ttu-id="0d3e7-113">Se você tiver um servidor de filial persistente associado, expanda **sites de filiais**, expanda o nome do site de filial e expanda **Aparelhos de filial persistente**.</span><span class="sxs-lookup"><span data-stu-id="0d3e7-113">If you have Survivable Branch Server associated, expand **Branch sites**, expand the branch site name, and then expand **Survivable Branch Appliances**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="0d3e7-114">**Aparelhos de filial persistente** na interface do usuário aplica-se ao servidor de filial persistente e aparelho de filial persistente.</span><span class="sxs-lookup"><span data-stu-id="0d3e7-114">**Survivable Branch Appliances** in the user interface applies to both Survivable Branch Server and Survivable Branch Appliance.</span></span> 
  
5. <span data-ttu-id="0d3e7-115">Com o botão direito do pool, servidor ou dispositivo que está associado com o Monitoring Server e, em seguida, clique em **Editar propriedades**.</span><span class="sxs-lookup"><span data-stu-id="0d3e7-115">Right-click the pool, server, or device that is associated with the Monitoring Server, and then click **Edit Properties**.</span></span>
    
6. <span data-ttu-id="0d3e7-116">Em **Editar propriedades**, em **Geral** > **associações**, desmarque a caixa de seleção **Associar Monitoring Server** e clique em **Okey**.</span><span class="sxs-lookup"><span data-stu-id="0d3e7-116">In **Edit Properties**, under **General** > **Associations**, clear the **Associate Monitoring Server** check box, and then click **OK**.</span></span>
    
7. <span data-ttu-id="0d3e7-117">Repita a etapa anterior para qualquer outro pool, servidor ou dispositivo associado ao Monitoring Server.</span><span class="sxs-lookup"><span data-stu-id="0d3e7-117">Repeat the previous step for any other pool, server, or device associated with the Monitoring Server.</span></span>
    
8. <span data-ttu-id="0d3e7-118">Com o botão direito no Monitoring Server e, em seguida, clique em **Excluir**.</span><span class="sxs-lookup"><span data-stu-id="0d3e7-118">Right-click the Monitoring Server, and then click **Delete**.</span></span> 
    
9. <span data-ttu-id="0d3e7-119">Em **Excluir armazenamentos dependentes**, clique em **Okey**.</span><span class="sxs-lookup"><span data-stu-id="0d3e7-119">On **Delete Dependent Stores**, click **OK**.</span></span>
    
10. <span data-ttu-id="0d3e7-120">Publique a topologia, verifique o status de replicação e execute o Skype para o Assistente de implantação de servidor de negócios, conforme necessário.</span><span class="sxs-lookup"><span data-stu-id="0d3e7-120">Publish the topology, check replication status, and run the Skype for Business Server Deployment Wizard as needed.</span></span> 
    

