---
title: Conectar pool piloto aos Servidores de Borda herdados
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
description: Depois de implantar o Skype for Business Server 2019, você precisa configurar uma rota de Federação para seu site. Para usar a rota federada que está sendo usada pela instalação herdada, o Skype for Business Server 2019 deve ser configurado para usar essa rota.
ms.openlocfilehash: 6cc49da3cb27679ef295c7bbeca122aea5a89d10
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41813699"
---
# <a name="connect-pilot-pool-to-legacy-edge-servers"></a><span data-ttu-id="56e6e-104">Conectar pool piloto aos Servidores de Borda herdados</span><span class="sxs-lookup"><span data-stu-id="56e6e-104">Connect pilot pool to legacy Edge Servers</span></span>

<span data-ttu-id="56e6e-105">Depois de implantar o Skype for Business Server 2019, você precisa configurar uma rota de Federação para seu site.</span><span class="sxs-lookup"><span data-stu-id="56e6e-105">After deploying Skype for Business Server 2019, you need to configure a federation route for your site.</span></span> <span data-ttu-id="56e6e-106">Para usar a rota federada que está sendo usada pela instalação herdada, o Skype for Business Server 2019 deve ser configurado para usar essa rota.</span><span class="sxs-lookup"><span data-stu-id="56e6e-106">In order to use the federated route that is being used by the legacy installation, Skype for Business Server 2019 must be configured to use this route.</span></span> 
  
<span data-ttu-id="56e6e-107">Para habilitar o site do Skype for Business Server 2019 para usar o diretor e o servidor de borda da implantação herdada, use o construtor de topologias para associar o pool de bordas herdado.</span><span class="sxs-lookup"><span data-stu-id="56e6e-107">To enable the Skype for Business Server 2019 site to use the Director and Edge Server of the legacy deployment, use Topology Builder to associate the legacy Edge pool.</span></span>
  
### <a name="to-associate-the-legacy-edge-pool-by-using-topology-builder"></a><span data-ttu-id="56e6e-108">Para associar o pool de bordas herdado usando o construtor de topologias</span><span class="sxs-lookup"><span data-stu-id="56e6e-108">To associate the legacy Edge pool by using Topology Builder</span></span>

1. <span data-ttu-id="56e6e-109">Abrir o construtor de topologias.</span><span class="sxs-lookup"><span data-stu-id="56e6e-109">Open Topology Builder.</span></span> 
    
2. <span data-ttu-id="56e6e-110">Selecione seu site, que está diretamente abaixo do nó do **Skype for Business Server** .</span><span class="sxs-lookup"><span data-stu-id="56e6e-110">Select your site, which is directly below the **Skype for Business Server** node.</span></span> 
    
3. <span data-ttu-id="56e6e-111">No menu **ações** , clique em **Editar propriedades**.</span><span class="sxs-lookup"><span data-stu-id="56e6e-111">On the **Actions** menu, click **Edit Properties**.</span></span>
    
4. <span data-ttu-id="56e6e-112">No painel esquerdo, selecione **roteiro de Federação**.</span><span class="sxs-lookup"><span data-stu-id="56e6e-112">In the left pane, select **Federation route**.</span></span>
    
5. <span data-ttu-id="56e6e-113">Em **atribuição de rota de Federação do site**, selecione **habilitar Federação SIP**e, em seguida, selecione o diretor herdado ou o servidor de borda herdado, se nenhum diretor estiver listado.</span><span class="sxs-lookup"><span data-stu-id="56e6e-113">Under **Site federation route assignment**, select **Enable SIP federation**, and then select the legacy Director, or the legacy Edge Server if no Director is listed.</span></span>
  
6. <span data-ttu-id="56e6e-114">Clique em **OK** para fechar a página **Editar propriedades** .</span><span class="sxs-lookup"><span data-stu-id="56e6e-114">Click **OK** to close the **Edit Properties** page.</span></span> 
    
7. <span data-ttu-id="56e6e-115">No construtor de topologias, no nó Skype for Business Server 2019, navegue até o **servidor Standard Edition** ou **pools front-end do Enterprise Edition**, clique com o botão direito do mouse no pool e, em seguida, clique em **Editar propriedades**.</span><span class="sxs-lookup"><span data-stu-id="56e6e-115">In Topology Builder, under the Skype for Business Server 2019 node, navigate to the **Standard Edition server** or **Enterprise Edition Front End pools**, right-click the pool, and then click **Edit Properties**.</span></span>
    
8. <span data-ttu-id="56e6e-116">Em **associações**, marque a caixa de seleção ao lado de **associar o pool de bordas (para componentes de mídia)**.</span><span class="sxs-lookup"><span data-stu-id="56e6e-116">Under **Associations**, select the check box next to **Associate Edge pool (for media components)**.</span></span> 
    
9. <span data-ttu-id="56e6e-117">Na lista, selecione o servidor de borda herdado.</span><span class="sxs-lookup"><span data-stu-id="56e6e-117">From the list, select the legacy Edge Server.</span></span> 
  
10. <span data-ttu-id="56e6e-118">Clique em **OK** para fechar a página **Editar propriedades** .</span><span class="sxs-lookup"><span data-stu-id="56e6e-118">Click **OK** to close the **Edit Properties** page.</span></span> 
    
11. <span data-ttu-id="56e6e-119">No **Construtor de topologias**, selecione o nó mais superior, **Skype for Business Server**.</span><span class="sxs-lookup"><span data-stu-id="56e6e-119">In **Topology Builder**, select the top-most node, **Skype for Business Server**.</span></span>
    
12. <span data-ttu-id="56e6e-120">No menu **ação** , clique em **publicar topologia**e, em seguida, clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="56e6e-120">From the **Action** menu, click **Publish Topology**, and then click **Next**.</span></span>
    
13. <span data-ttu-id="56e6e-121">Quando o **Assistente de publicação** for concluído, clique em **concluir**.</span><span class="sxs-lookup"><span data-stu-id="56e6e-121">When the **Publishing wizard** completes, click **Finish**.</span></span>
    

