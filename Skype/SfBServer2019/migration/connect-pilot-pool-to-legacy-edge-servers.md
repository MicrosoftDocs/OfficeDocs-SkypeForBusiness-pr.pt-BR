---
title: Conectar pool piloto aos Servidores de Borda herdados
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Depois de implantar o Skype for Business Server 2019, você precisa configurar uma rota de Federação para seu site. Para usar a rota federada que está sendo usada pela instalação herdada, o Skype for Business Server 2019 deve ser configurado para usar essa rota.
ms.openlocfilehash: 7a5a65e1488d5a119e3d11affbbaa9995a06626e
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/07/2019
ms.locfileid: "36239221"
---
# <a name="connect-pilot-pool-to-legacy-edge-servers"></a><span data-ttu-id="2e867-104">Conectar pool piloto aos Servidores de Borda herdados</span><span class="sxs-lookup"><span data-stu-id="2e867-104">Connect pilot pool to legacy Edge Servers</span></span>

<span data-ttu-id="2e867-105">Depois de implantar o Skype for Business Server 2019, você precisa configurar uma rota de Federação para seu site.</span><span class="sxs-lookup"><span data-stu-id="2e867-105">After deploying Skype for Business Server 2019, you need to configure a federation route for your site.</span></span> <span data-ttu-id="2e867-106">Para usar a rota federada que está sendo usada pela instalação herdada, o Skype for Business Server 2019 deve ser configurado para usar essa rota.</span><span class="sxs-lookup"><span data-stu-id="2e867-106">In order to use the federated route that is being used by the legacy installation, Skype for Business Server 2019 must be configured to use this route.</span></span> 
  
<span data-ttu-id="2e867-107">Para habilitar o site do Skype for Business Server 2019 para usar o diretor e o servidor de borda da implantação herdada, use o construtor de topologias para associar o pool de bordas herdado.</span><span class="sxs-lookup"><span data-stu-id="2e867-107">To enable the Skype for Business Server 2019 site to use the Director and Edge Server of the legacy deployment, use Topology Builder to associate the legacy Edge pool.</span></span>
  
### <a name="to-associate-the-legacy-edge-pool-by-using-topology-builder"></a><span data-ttu-id="2e867-108">Para associar o pool de bordas herdado usando o construtor de topologias</span><span class="sxs-lookup"><span data-stu-id="2e867-108">To associate the legacy Edge pool by using Topology Builder</span></span>

1. <span data-ttu-id="2e867-109">Abrir o construtor de topologias.</span><span class="sxs-lookup"><span data-stu-id="2e867-109">Open Topology Builder.</span></span> 
    
2. <span data-ttu-id="2e867-110">Selecione seu site, que está diretamente abaixo do nó do **Skype for Business Server** .</span><span class="sxs-lookup"><span data-stu-id="2e867-110">Select your site, which is directly below the **Skype for Business Server** node.</span></span> 
    
3. <span data-ttu-id="2e867-111">No menu **ações** , clique em **Editar propriedades**.</span><span class="sxs-lookup"><span data-stu-id="2e867-111">On the **Actions** menu, click **Edit Properties**.</span></span>
    
4. <span data-ttu-id="2e867-112">No painel esquerdo, selecione **roteiro de Federação**.</span><span class="sxs-lookup"><span data-stu-id="2e867-112">In the left pane, select **Federation route**.</span></span>
    
5. <span data-ttu-id="2e867-113">Em **atribuição de rota de Federação do site**, selecione **habilitar Federação SIP**e, em seguida, selecione o diretor herdado ou o servidor de borda herdado, se nenhum diretor estiver listado.</span><span class="sxs-lookup"><span data-stu-id="2e867-113">Under **Site federation route assignment**, select **Enable SIP federation**, and then select the legacy Director, or the legacy Edge Server if no Director is listed.</span></span>
  
6. <span data-ttu-id="2e867-114">Clique em **OK** para fechar a página **Editar propriedades** .</span><span class="sxs-lookup"><span data-stu-id="2e867-114">Click **OK** to close the **Edit Properties** page.</span></span> 
    
7. <span data-ttu-id="2e867-115">No construtor de topologias, no nó Skype for Business Server 2019, navegue até o **servidor Standard Edition** ou **pools front-end do Enterprise Edition**, clique com o botão direito do mouse no pool e, em seguida, clique em **Editar propriedades**.</span><span class="sxs-lookup"><span data-stu-id="2e867-115">In Topology Builder, under the Skype for Business Server 2019 node, navigate to the **Standard Edition server** or **Enterprise Edition Front End pools**, right-click the pool, and then click **Edit Properties**.</span></span>
    
8. <span data-ttu-id="2e867-116">Em **associações**, marque a caixa de seleção ao lado de **associar o pool de bordas (para componentes de mídia)**.</span><span class="sxs-lookup"><span data-stu-id="2e867-116">Under **Associations**, select the check box next to **Associate Edge pool (for media components)**.</span></span> 
    
9. <span data-ttu-id="2e867-117">Na lista, selecione o servidor de borda herdado.</span><span class="sxs-lookup"><span data-stu-id="2e867-117">From the list, select the legacy Edge Server.</span></span> 
  
10. <span data-ttu-id="2e867-118">Clique em **OK** para fechar a página **Editar propriedades** .</span><span class="sxs-lookup"><span data-stu-id="2e867-118">Click **OK** to close the **Edit Properties** page.</span></span> 
    
11. <span data-ttu-id="2e867-119">No **Construtor**de topologias, selecione o nó mais superior, **Skype for Business Server**.</span><span class="sxs-lookup"><span data-stu-id="2e867-119">In **Topology Builder**, select the top-most node, **Skype for Business Server**.</span></span>
    
12. <span data-ttu-id="2e867-120">No menu **ação** , clique em **publicar topologia**e, em seguida, clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="2e867-120">From the **Action** menu, click **Publish Topology**, and then click **Next**.</span></span>
    
13. <span data-ttu-id="2e867-121">Quando o **Assistente de publicação** for concluído, clique em **concluir**.</span><span class="sxs-lookup"><span data-stu-id="2e867-121">When the **Publishing wizard** completes, click **Finish**.</span></span>
    

