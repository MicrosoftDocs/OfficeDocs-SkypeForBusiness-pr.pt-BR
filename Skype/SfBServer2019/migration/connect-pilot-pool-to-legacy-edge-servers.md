---
title: Conectar pool piloto aos Servidores de Borda herdados
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
description: Depois de implantar o Skype for Business Server 2019, você precisará configurar uma rota de federação para seu site. Para usar a rota federada que está sendo usada pela instalação herdada, o Skype for Business Server 2019 deve ser configurado para usar essa rota.
ms.openlocfilehash: 8243ebbf9540587dedd8e4ae3a51e22f9a315728
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/16/2020
ms.locfileid: "44753921"
---
# <a name="connect-pilot-pool-to-legacy-edge-servers"></a><span data-ttu-id="cc2ba-104">Conectar pool piloto aos Servidores de Borda herdados</span><span class="sxs-lookup"><span data-stu-id="cc2ba-104">Connect pilot pool to legacy Edge Servers</span></span>

<span data-ttu-id="cc2ba-105">Depois de implantar o Skype for Business Server 2019, você precisará configurar uma rota de federação para seu site.</span><span class="sxs-lookup"><span data-stu-id="cc2ba-105">After deploying Skype for Business Server 2019, you need to configure a federation route for your site.</span></span> <span data-ttu-id="cc2ba-106">Para usar a rota federada que está sendo usada pela instalação herdada, o Skype for Business Server 2019 deve ser configurado para usar essa rota.</span><span class="sxs-lookup"><span data-stu-id="cc2ba-106">In order to use the federated route that is being used by the legacy installation, Skype for Business Server 2019 must be configured to use this route.</span></span> 
  
<span data-ttu-id="cc2ba-107">Para habilitar o site do Skype for Business Server 2019 a usar o Diretor e o Servidor de Borda da implantação herdada, use o Construtor de Topologias para associar o pool de Borda herdado.</span><span class="sxs-lookup"><span data-stu-id="cc2ba-107">To enable the Skype for Business Server 2019 site to use the Director and Edge Server of the legacy deployment, use Topology Builder to associate the legacy Edge pool.</span></span>
  
### <a name="to-associate-the-legacy-edge-pool-by-using-topology-builder"></a><span data-ttu-id="cc2ba-108">Para associar o pool de Borda herdado usando o Construtor de Topologia</span><span class="sxs-lookup"><span data-stu-id="cc2ba-108">To associate the legacy Edge pool by using Topology Builder</span></span>

1. <span data-ttu-id="cc2ba-109">Abra o Construtor de Topologia.</span><span class="sxs-lookup"><span data-stu-id="cc2ba-109">Open Topology Builder.</span></span> 
    
2. <span data-ttu-id="cc2ba-110">Selecione seu site, que está diretamente abaixo do **nó do Skype for Business Server.**</span><span class="sxs-lookup"><span data-stu-id="cc2ba-110">Select your site, which is directly below the **Skype for Business Server** node.</span></span> 
    
3. <span data-ttu-id="cc2ba-111">No menu **Ações**, clique em **Editar Propriedades**.</span><span class="sxs-lookup"><span data-stu-id="cc2ba-111">On the **Actions** menu, click **Edit Properties**.</span></span>
    
4. <span data-ttu-id="cc2ba-112">No painel esquerdo, selecione **Rota de federação**.</span><span class="sxs-lookup"><span data-stu-id="cc2ba-112">In the left pane, select **Federation route**.</span></span>
    
5. <span data-ttu-id="cc2ba-113">Em **Atribuição da** rota de federação do site, selecione Habilitar federação **SIP** e selecione o Diretor herdado ou o Servidor de Borda herdado se nenhum Diretor estiver listado.</span><span class="sxs-lookup"><span data-stu-id="cc2ba-113">Under **Site federation route assignment**, select **Enable SIP federation**, and then select the legacy Director, or the legacy Edge Server if no Director is listed.</span></span>
  
6. <span data-ttu-id="cc2ba-114">Clique em **OK** para fechar a página **Editar Propriedades**.</span><span class="sxs-lookup"><span data-stu-id="cc2ba-114">Click **OK** to close the **Edit Properties** page.</span></span> 
    
7. <span data-ttu-id="cc2ba-115">No Construtor de Topologias, no nó Skype for Business Server 2019, navegue até o servidor **Standard Edition** ou pools de **front-end enterprise edition**, clique com o botão direito do mouse no pool e clique em **Editar** propriedades .</span><span class="sxs-lookup"><span data-stu-id="cc2ba-115">In Topology Builder, under the Skype for Business Server 2019 node, navigate to the **Standard Edition server** or **Enterprise Edition Front End pools**, right-click the pool, and then click **Edit Properties**.</span></span>
    
8. <span data-ttu-id="cc2ba-116">Em **Associações**, marque a caixa de seleção próxima ao **Associar pool de Borda (para componentes de mídia)**.</span><span class="sxs-lookup"><span data-stu-id="cc2ba-116">Under **Associations**, select the check box next to **Associate Edge pool (for media components)**.</span></span> 
    
9. <span data-ttu-id="cc2ba-117">Na lista, selecione o Servidor de Borda herdado.</span><span class="sxs-lookup"><span data-stu-id="cc2ba-117">From the list, select the legacy Edge Server.</span></span> 
  
10. <span data-ttu-id="cc2ba-118">Clique em **OK** para fechar a página **Editar Propriedades**.</span><span class="sxs-lookup"><span data-stu-id="cc2ba-118">Click **OK** to close the **Edit Properties** page.</span></span> 
    
11. <span data-ttu-id="cc2ba-119">No **Construtor de Topologias,** selecione o nó superior, **Skype for Business Server**.</span><span class="sxs-lookup"><span data-stu-id="cc2ba-119">In **Topology Builder**, select the top-most node, **Skype for Business Server**.</span></span>
    
12. <span data-ttu-id="cc2ba-120">No painel **Ações**, no menu **Publicar topologia** e em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="cc2ba-120">From the **Action** menu, click **Publish Topology**, and then click **Next**.</span></span>
    
13. <span data-ttu-id="cc2ba-121">Quando o **Assistente de publicação** for concluído, clique em **Finalizar**.</span><span class="sxs-lookup"><span data-stu-id="cc2ba-121">When the **Publishing wizard** completes, click **Finish**.</span></span>
    

