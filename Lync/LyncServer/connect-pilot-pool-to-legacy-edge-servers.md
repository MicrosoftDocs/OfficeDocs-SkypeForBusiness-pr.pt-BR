---
title: Conectar pool piloto aos Servidores de Borda herdados
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Connect pilot pool to legacy Edge Servers
ms:assetid: c3b67220-5705-47f6-852e-415204f3626c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721875(v=OCS.15)
ms:contentKeyID: 49733808
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8d12a67b0ba102fdacea66b6196bafe32d89c9d9
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48503098"
---
# <a name="connect-pilot-pool-to-legacy-edge-servers"></a><span data-ttu-id="8fe1a-102">Conectar pool piloto aos Servidores de Borda herdados</span><span class="sxs-lookup"><span data-stu-id="8fe1a-102">Connect pilot pool to legacy Edge Servers</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8fe1a-103">_**Última modificação do tópico:** 2012-09-29_</span><span class="sxs-lookup"><span data-stu-id="8fe1a-103">_**Topic Last Modified:** 2012-09-29_</span></span>

<span data-ttu-id="8fe1a-104">Após implantar o Lync Server 2013, você precisará configurar uma rota de Federação para seu site.</span><span class="sxs-lookup"><span data-stu-id="8fe1a-104">After deploying Lync Server 2013, you need to configure a federation route for your site.</span></span> <span data-ttu-id="8fe1a-105">Para usar a rota federada que está sendo usada pelo Lync Server 2010, o Lync Server 2013 deve ser configurado para usar essa rota.</span><span class="sxs-lookup"><span data-stu-id="8fe1a-105">In order to use the federated route that is being used by Lync Server 2010, Lync Server 2013 must be configured to use this route.</span></span>

<span data-ttu-id="8fe1a-106">Para habilitar o site do Lync Server 2013 para usar o diretor e o servidor de borda da implantação do Lync Server 2010, use o construtor de topologia para associar o pool de borda herdado.</span><span class="sxs-lookup"><span data-stu-id="8fe1a-106">To enable the Lync Server 2013 site to use the Director and Edge Server of the Lync Server 2010 deployment, use Topology Builder to associate the legacy Edge pool.</span></span>

<div>

## <a name="to-associate-the-legacy-edge-pool-by-using-topology-builder"></a><span data-ttu-id="8fe1a-107">Para associar o pool de Borda herdado usando o Construtor de Topologia</span><span class="sxs-lookup"><span data-stu-id="8fe1a-107">To associate the legacy Edge pool by using Topology Builder</span></span>

1.  <span data-ttu-id="8fe1a-108">Abra o **Construtor de Topologia**.</span><span class="sxs-lookup"><span data-stu-id="8fe1a-108">Open **Topology Builder**.</span></span>

2.  <span data-ttu-id="8fe1a-109">Selecione seu local, que está diretamente abaixo do nó do **Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="8fe1a-109">Select your site, which is directly below the **Lync Server** node.</span></span>

3.  <span data-ttu-id="8fe1a-110">No menu **Ações**, clique em **Editar Propriedades**.</span><span class="sxs-lookup"><span data-stu-id="8fe1a-110">On the **Actions** menu, click **Edit Properties**.</span></span>

4.  <span data-ttu-id="8fe1a-111">No painel esquerdo, selecione **Rota de federação**.</span><span class="sxs-lookup"><span data-stu-id="8fe1a-111">In the left pane, select **Federation route**.</span></span>

5.  <span data-ttu-id="8fe1a-112">Em **atribuição de rota de Federação do site**, selecione **habilitar Federação SIP**e, em seguida, selecione o diretor do Lync Server 2010 ou o servidor de borda do Lync Server 2010, se nenhum diretor estiver listado.</span><span class="sxs-lookup"><span data-stu-id="8fe1a-112">Under **Site federation route assignment**, select **Enable SIP federation**, and then select the Lync Server 2010 Director, or the Lync Server 2010 Edge Server if no Director is listed.</span></span>
    
    <span data-ttu-id="8fe1a-113">![Editar propriedades, página de rota de Federação](images/JJ721875.5f1d04c3-c724-426d-b27d-3fe89c6c5cfb(OCS.15).jpg "Editar propriedades, página de rota de Federação")</span><span class="sxs-lookup"><span data-stu-id="8fe1a-113">![Edit Properties, Federation route page](images/JJ721875.5f1d04c3-c724-426d-b27d-3fe89c6c5cfb(OCS.15).jpg "Edit Properties, Federation route page")</span></span>  

6.  <span data-ttu-id="8fe1a-114">Clique em **OK** para fechar a página **Editar Propriedades**.</span><span class="sxs-lookup"><span data-stu-id="8fe1a-114">Click **OK** to close the **Edit Properties** page.</span></span>

7.  <span data-ttu-id="8fe1a-115">No construtor de topologias, no nó Lync Server 2013, navegue até o **servidor Standard Edition** ou **pools de front-ends Enterprise Edition**, clique com o botão direito do mouse no pool e clique em **Editar propriedades**.</span><span class="sxs-lookup"><span data-stu-id="8fe1a-115">In Topology Builder, under the Lync Server 2013 node, navigate to the **Standard Edition server** or **Enterprise Edition Front End pools**, right-click the pool, and then click **Edit Properties**.</span></span>

8.  <span data-ttu-id="8fe1a-116">Em **Associações**, marque a caixa de seleção próxima ao **Associar pool de Borda (para componentes de mídia)**.</span><span class="sxs-lookup"><span data-stu-id="8fe1a-116">Under **Associations**, select the check box next to **Associate Edge pool (for media components)**.</span></span>

9.  <span data-ttu-id="8fe1a-117">Na lista, selecione o Servidor de Borda herdado.</span><span class="sxs-lookup"><span data-stu-id="8fe1a-117">From the list, select the legacy Edge Server.</span></span>
    
    <span data-ttu-id="8fe1a-118">![Caixa de diálogo Editar propriedades, selecionando a borda herdada](images/JJ721875.feae8156-540e-4804-bb0a-2b5736ec2900(OCS.15).jpg "Caixa de diálogo Editar propriedades, selecionando a borda herdada")</span><span class="sxs-lookup"><span data-stu-id="8fe1a-118">![Edit Properties dialog, selecting the legacy Edge](images/JJ721875.feae8156-540e-4804-bb0a-2b5736ec2900(OCS.15).jpg "Edit Properties dialog, selecting the legacy Edge")</span></span>  

10. <span data-ttu-id="8fe1a-119">Clique em **OK** para fechar a página **Editar Propriedades**.</span><span class="sxs-lookup"><span data-stu-id="8fe1a-119">Click **OK** to close the **Edit Properties** page.</span></span>

11. <span data-ttu-id="8fe1a-120">No **Construtor de Topologias**, selecione o nó superior, **Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="8fe1a-120">In **Topology Builder**, select the top-most node, **Lync Server**.</span></span>

12. <span data-ttu-id="8fe1a-121">No painel **Ações**, no menu **Publicar topologia** e em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="8fe1a-121">From the **Action** menu, click **Publish Topology**, and then click **Next**.</span></span>

13. <span data-ttu-id="8fe1a-122">Quando o **Assistente de publicação** for concluído, clique em **Finalizar**.</span><span class="sxs-lookup"><span data-stu-id="8fe1a-122">When the **Publishing wizard** completes, click **Finish**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

