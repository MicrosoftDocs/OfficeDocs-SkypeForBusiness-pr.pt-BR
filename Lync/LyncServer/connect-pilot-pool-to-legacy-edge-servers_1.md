---
title: Conectar o pool piloto aos servidores de borda herdados
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Connect pilot pool to legacy Edge Servers
ms:assetid: 9ed13c41-f3ab-4e1d-beb6-a00152c541e2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205136(v=OCS.15)
ms:contentKeyID: 48185003
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 540ed4ae4b8714a4bd8e8969748fb62fa9f6bc5a
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42136528"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="connect-pilot-pool-to-legacy-edge-servers"></a><span data-ttu-id="dd514-102">Conectar o pool piloto aos servidores de borda herdados</span><span class="sxs-lookup"><span data-stu-id="dd514-102">Connect pilot pool to legacy Edge Servers</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="dd514-103">_**Última modificação do tópico:** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="dd514-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="dd514-104">Após implantar o Lync Server 2013, uma rota de Federação para este site não é configurada.</span><span class="sxs-lookup"><span data-stu-id="dd514-104">After deploying Lync Server 2013, a federation route for this site is not configured.</span></span> <span data-ttu-id="dd514-105">Para usar a rota federada que está sendo usada pelo Office Communications Server 2007 R2, o Lync Server 2013 deve ser configurado para usar essa rota.</span><span class="sxs-lookup"><span data-stu-id="dd514-105">In order to use the federated route that is being used by Office Communications Server 2007 R2, Lync Server 2013 must be configured to use this route.</span></span>

<span data-ttu-id="dd514-106">Para habilitar o site do Lync Server 2013 para usar o diretor e o servidor de borda do BackCompatSite, use o construtor de topologia para associar o pool de borda herdado.</span><span class="sxs-lookup"><span data-stu-id="dd514-106">To enable the Lync Server 2013 site to use the Director and Edge Server of the BackCompatSite, use Topology Builder to associate the legacy Edge pool.</span></span>

<div>

## <a name="to-associate-the-legacy-edge-pool-by-using-topology-builder"></a><span data-ttu-id="dd514-107">Para associar o pool de Borda herdado usando o Construtor de Topologia</span><span class="sxs-lookup"><span data-stu-id="dd514-107">To associate the legacy Edge pool by using Topology Builder</span></span>

1.  <span data-ttu-id="dd514-108">Abra a topologia do pool piloto no construtor de topologias.</span><span class="sxs-lookup"><span data-stu-id="dd514-108">Open the pilot pool topology in Topology Builder.</span></span>

2.  <span data-ttu-id="dd514-109">Selecione seu site do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="dd514-109">Select your Lync Server 2013 site.</span></span>

3.  <span data-ttu-id="dd514-110">No menu **ação** , clique em **Editar propriedades**.</span><span class="sxs-lookup"><span data-stu-id="dd514-110">On the **Action** menu, click **Edit Properties**.</span></span>

4.  <span data-ttu-id="dd514-111">Em **atribuição de rota de Federação do site**, selecione **habilitar Federação SIP**e, em seguida, selecione o diretor do office Communications Server 2007 R2 ou o servidor de borda do office Communications Server 2007 R2 se nenhum diretor estiver listado.</span><span class="sxs-lookup"><span data-stu-id="dd514-111">Under **Site federation route assignment**, select **Enable SIP federation**, and then select the Office Communications Server 2007 R2 Director, or the Office Communications Server 2007 R2 Edge Server if no Director is listed.</span></span>
    
    <span data-ttu-id="dd514-112">![Caixa de diálogo Editar propriedades, página rota de Federação](images/JJ205136.bc13014b-3578-4d9e-9ff7-bdd09130b676(OCS.15).jpg "Caixa de diálogo Editar propriedades, página rota de Federação")</span><span class="sxs-lookup"><span data-stu-id="dd514-112">![Edit Properties dialog, Federation route page](images/JJ205136.bc13014b-3578-4d9e-9ff7-bdd09130b676(OCS.15).jpg "Edit Properties dialog, Federation route page")</span></span>  

5.  <span data-ttu-id="dd514-113">Clique em **OK** para fechar a página **Editar Propriedades**.</span><span class="sxs-lookup"><span data-stu-id="dd514-113">Click **OK** to close the **Edit Properties** page.</span></span>

6.  <span data-ttu-id="dd514-114">No construtor de topologias, no nó Lync Server 2013, navegue até o **servidor Standard Edition** ou **pools de front-ends Enterprise Edition**, clique com o botão direito do mouse no pool e clique em **Editar propriedades**.</span><span class="sxs-lookup"><span data-stu-id="dd514-114">In Topology Builder, under the Lync Server 2013 node, navigate to the **Standard Edition server** or **Enterprise Edition Front End pools**, right-click the pool, and then click **Edit Properties**.</span></span>

7.  <span data-ttu-id="dd514-115">Em **Associações**, marque a caixa de seleção próxima ao **Associar pool de Borda (para componentes de mídia)**.</span><span class="sxs-lookup"><span data-stu-id="dd514-115">Under **Associations**, select the check box next to **Associate Edge pool (for media components)**.</span></span>

8.  <span data-ttu-id="dd514-116">Na lista, selecione a interface do servidor de borda para o BackCompatSite.</span><span class="sxs-lookup"><span data-stu-id="dd514-116">From the list, select the Edge Server interface for the BackCompatSite.</span></span>
    
    <span data-ttu-id="dd514-117">![Caixa de diálogo Editar propriedades, página Geral](images/JJ205136.75045212-03ca-4b82-8337-5dacb487094f(OCS.15).jpg "Caixa de diálogo Editar propriedades, página Geral")</span><span class="sxs-lookup"><span data-stu-id="dd514-117">![Edit Properties dialog, General page](images/JJ205136.75045212-03ca-4b82-8337-5dacb487094f(OCS.15).jpg "Edit Properties dialog, General page")</span></span>  

9.  <span data-ttu-id="dd514-118">Clique em **OK** para fechar a página **Editar Propriedades**.</span><span class="sxs-lookup"><span data-stu-id="dd514-118">Click **OK** to close the **Edit Properties** page.</span></span>

10. <span data-ttu-id="dd514-119">No **Construtor de Topologias**, selecione o nó superior, **Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="dd514-119">In **Topology Builder**, select the top-most node, **Lync Server**.</span></span>

11. <span data-ttu-id="dd514-120">No painel **Ações**, no menu **Publicar topologia** e em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="dd514-120">From the **Action** menu, click **Publish Topology**, and then click **Next**.</span></span>

12. <span data-ttu-id="dd514-121">Quando o **Assistente de publicação** for concluído, clique em **Finalizar**.</span><span class="sxs-lookup"><span data-stu-id="dd514-121">When the **Publishing wizard** completes, click **Finish**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

