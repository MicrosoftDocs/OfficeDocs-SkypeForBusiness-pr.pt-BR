---
title: Conectar pool piloto aos Servidores de Borda herdados
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
ms.openlocfilehash: 09858b03c787af034790c94bcbf12ca6ea7ceecf
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41723141"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="connect-pilot-pool-to-legacy-edge-servers"></a><span data-ttu-id="0b33f-102">Conectar pool piloto aos Servidores de Borda herdados</span><span class="sxs-lookup"><span data-stu-id="0b33f-102">Connect pilot pool to legacy Edge Servers</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0b33f-103">_**Tópico da última modificação:** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="0b33f-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="0b33f-104">Após implantar o Lync Server 2013, uma rota de Federação para este site não é configurada.</span><span class="sxs-lookup"><span data-stu-id="0b33f-104">After deploying Lync Server 2013, a federation route for this site is not configured.</span></span> <span data-ttu-id="0b33f-105">Para usar a rota federada que está sendo usada pelo Office Communications Server 2007 R2, o Lync Server 2013 deve ser configurado para usar essa rota.</span><span class="sxs-lookup"><span data-stu-id="0b33f-105">In order to use the federated route that is being used by Office Communications Server 2007 R2, Lync Server 2013 must be configured to use this route.</span></span>

<span data-ttu-id="0b33f-106">Para habilitar o site do Lync Server 2013 a usar o diretor e o servidor de borda da BackCompatSite, use o construtor de topologias para associar o pool de bordas herdado.</span><span class="sxs-lookup"><span data-stu-id="0b33f-106">To enable the Lync Server 2013 site to use the Director and Edge Server of the BackCompatSite, use Topology Builder to associate the legacy Edge pool.</span></span>

<div>

## <a name="to-associate-the-legacy-edge-pool-by-using-topology-builder"></a><span data-ttu-id="0b33f-107">Para associar o pool de bordas herdado usando o construtor de topologias</span><span class="sxs-lookup"><span data-stu-id="0b33f-107">To associate the legacy Edge pool by using Topology Builder</span></span>

1.  <span data-ttu-id="0b33f-108">Abra a topologia do pool piloto no construtor de topologias.</span><span class="sxs-lookup"><span data-stu-id="0b33f-108">Open the pilot pool topology in Topology Builder.</span></span>

2.  <span data-ttu-id="0b33f-109">Selecione seu site do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="0b33f-109">Select your Lync Server 2013 site.</span></span>

3.  <span data-ttu-id="0b33f-110">No menu **ação** , clique em **Editar propriedades**.</span><span class="sxs-lookup"><span data-stu-id="0b33f-110">On the **Action** menu, click **Edit Properties**.</span></span>

4.  <span data-ttu-id="0b33f-111">Em **atribuição de rota de Federação do site**, selecione **habilitar Federação SIP**e, em seguida, selecione o diretor do office Communications Server 2007 R2 ou o servidor de borda do office Communications Server 2007 R2 se nenhum diretor estiver listado.</span><span class="sxs-lookup"><span data-stu-id="0b33f-111">Under **Site federation route assignment**, select **Enable SIP federation**, and then select the Office Communications Server 2007 R2 Director, or the Office Communications Server 2007 R2 Edge Server if no Director is listed.</span></span>
    
    <span data-ttu-id="0b33f-112">![Caixa de diálogo Editar propriedades, página rota de Federação](images/JJ205136.bc13014b-3578-4d9e-9ff7-bdd09130b676(OCS.15).jpg "Caixa de diálogo Editar propriedades, página rota de Federação")</span><span class="sxs-lookup"><span data-stu-id="0b33f-112">![Edit Properties dialog, Federation route page](images/JJ205136.bc13014b-3578-4d9e-9ff7-bdd09130b676(OCS.15).jpg "Edit Properties dialog, Federation route page")</span></span>  

5.  <span data-ttu-id="0b33f-113">Clique em **OK** para fechar a página **Editar propriedades** .</span><span class="sxs-lookup"><span data-stu-id="0b33f-113">Click **OK** to close the **Edit Properties** page.</span></span>

6.  <span data-ttu-id="0b33f-114">No construtor de topologias, no nó do Lync Server 2013, navegue até os pools do **servidor Standard Edition** ou do **front-end da edição Enterprise**, clique com o botão direito do mouse no pool e, em seguida, clique em **Editar propriedades**.</span><span class="sxs-lookup"><span data-stu-id="0b33f-114">In Topology Builder, under the Lync Server 2013 node, navigate to the **Standard Edition server** or **Enterprise Edition Front End pools**, right-click the pool, and then click **Edit Properties**.</span></span>

7.  <span data-ttu-id="0b33f-115">Em **associações**, marque a caixa de seleção ao lado de **associar o pool de bordas (para componentes de mídia)**.</span><span class="sxs-lookup"><span data-stu-id="0b33f-115">Under **Associations**, select the check box next to **Associate Edge pool (for media components)**.</span></span>

8.  <span data-ttu-id="0b33f-116">Na lista, selecione a interface do servidor de borda para o BackCompatSite.</span><span class="sxs-lookup"><span data-stu-id="0b33f-116">From the list, select the Edge Server interface for the BackCompatSite.</span></span>
    
    <span data-ttu-id="0b33f-117">![Caixa de diálogo Editar propriedades, página Geral](images/JJ205136.75045212-03ca-4b82-8337-5dacb487094f(OCS.15).jpg "Caixa de diálogo Editar propriedades, página Geral")</span><span class="sxs-lookup"><span data-stu-id="0b33f-117">![Edit Properties dialog, General page](images/JJ205136.75045212-03ca-4b82-8337-5dacb487094f(OCS.15).jpg "Edit Properties dialog, General page")</span></span>  

9.  <span data-ttu-id="0b33f-118">Clique em **OK** para fechar a página **Editar propriedades** .</span><span class="sxs-lookup"><span data-stu-id="0b33f-118">Click **OK** to close the **Edit Properties** page.</span></span>

10. <span data-ttu-id="0b33f-119">No **Construtor de topologias**, selecione o nó mais alto, **Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="0b33f-119">In **Topology Builder**, select the top-most node, **Lync Server**.</span></span>

11. <span data-ttu-id="0b33f-120">No menu **ação** , clique em **publicar topologia**e, em seguida, clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="0b33f-120">From the **Action** menu, click **Publish Topology**, and then click **Next**.</span></span>

12. <span data-ttu-id="0b33f-121">Quando o **Assistente de publicação** for concluído, clique em **concluir**.</span><span class="sxs-lookup"><span data-stu-id="0b33f-121">When the **Publishing wizard** completes, click **Finish**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

