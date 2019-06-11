---
title: Conectar pool piloto aos Servidores de Borda herdados
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Connect pilot pool to legacy Edge Servers
ms:assetid: c3b67220-5705-47f6-852e-415204f3626c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721875(v=OCS.15)
ms:contentKeyID: 49733808
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7fc42c645548ea9bad072da5f18643271a9eceeb
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34836840"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="connect-pilot-pool-to-legacy-edge-servers"></a><span data-ttu-id="72798-102">Conectar pool piloto aos Servidores de Borda herdados</span><span class="sxs-lookup"><span data-stu-id="72798-102">Connect pilot pool to legacy Edge Servers</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="72798-103">_**Tópico da última modificação:** 2012-09-29_</span><span class="sxs-lookup"><span data-stu-id="72798-103">_**Topic Last Modified:** 2012-09-29_</span></span>

<span data-ttu-id="72798-104">Após implantar o Lync Server 2013, você precisa configurar uma rota de Federação para seu site.</span><span class="sxs-lookup"><span data-stu-id="72798-104">After deploying Lync Server 2013, you need to configure a federation route for your site.</span></span> <span data-ttu-id="72798-105">Para usar a rota federada que está sendo usada pelo Lync Server 2010, o Lync Server 2013 deve ser configurado para usar essa rota.</span><span class="sxs-lookup"><span data-stu-id="72798-105">In order to use the federated route that is being used by Lync Server 2010, Lync Server 2013 must be configured to use this route.</span></span>

<span data-ttu-id="72798-106">Para habilitar o site do Lync Server 2013 para usar o diretor e o servidor de borda da implantação do Lync Server 2010, use o construtor de topologias para associar o pool de bordas herdado.</span><span class="sxs-lookup"><span data-stu-id="72798-106">To enable the Lync Server 2013 site to use the Director and Edge Server of the Lync Server 2010 deployment, use Topology Builder to associate the legacy Edge pool.</span></span>

<div>

## <a name="to-associate-the-legacy-edge-pool-by-using-topology-builder"></a><span data-ttu-id="72798-107">Para associar o pool de bordas herdado usando o construtor de topologias</span><span class="sxs-lookup"><span data-stu-id="72798-107">To associate the legacy Edge pool by using Topology Builder</span></span>

1.  <span data-ttu-id="72798-108">Abrir o **Construtor**de topologias.</span><span class="sxs-lookup"><span data-stu-id="72798-108">Open **Topology Builder**.</span></span>

2.  <span data-ttu-id="72798-109">Selecione seu site, que está diretamente abaixo do nó do **Lync Server** .</span><span class="sxs-lookup"><span data-stu-id="72798-109">Select your site, which is directly below the **Lync Server** node.</span></span>

3.  <span data-ttu-id="72798-110">No menu **ações** , clique em **Editar propriedades**.</span><span class="sxs-lookup"><span data-stu-id="72798-110">On the **Actions** menu, click **Edit Properties**.</span></span>

4.  <span data-ttu-id="72798-111">No painel esquerdo, selecione **roteiro de Federação**.</span><span class="sxs-lookup"><span data-stu-id="72798-111">In the left pane, select **Federation route**.</span></span>

5.  <span data-ttu-id="72798-112">Em **atribuição de rota de Federação do site**, selecione **habilitar Federação SIP**e, em seguida, selecione o diretor do Lync Server 2010 ou o servidor de borda do Lync Server 2010, se nenhum diretor estiver listado.</span><span class="sxs-lookup"><span data-stu-id="72798-112">Under **Site federation route assignment**, select **Enable SIP federation**, and then select the Lync Server 2010 Director, or the Lync Server 2010 Edge Server if no Director is listed.</span></span>
    
    <span data-ttu-id="72798-113">![Editar propriedades, página de roteiro de Federação] (images/JJ721875.5f1d04c3-c724-426d-b27d-3fe89c6c5cfb(OCS.15).jpg "Editar propriedades, página de roteiro de Federação")</span><span class="sxs-lookup"><span data-stu-id="72798-113">![Edit Properties, Federation route page](images/JJ721875.5f1d04c3-c724-426d-b27d-3fe89c6c5cfb(OCS.15).jpg "Edit Properties, Federation route page")</span></span>  

6.  <span data-ttu-id="72798-114">Clique em **OK** para fechar a página **Editar propriedades** .</span><span class="sxs-lookup"><span data-stu-id="72798-114">Click **OK** to close the **Edit Properties** page.</span></span>

7.  <span data-ttu-id="72798-115">No construtor de topologias, no nó do Lync Server 2013, navegue até os pools do **servidor Standard Edition** ou do **front-end da edição Enterprise**, clique com o botão direito do mouse no pool e, em seguida, clique em **Editar propriedades**.</span><span class="sxs-lookup"><span data-stu-id="72798-115">In Topology Builder, under the Lync Server 2013 node, navigate to the **Standard Edition server** or **Enterprise Edition Front End pools**, right-click the pool, and then click **Edit Properties**.</span></span>

8.  <span data-ttu-id="72798-116">Em **associações**, marque a caixa de seleção ao lado de **associar o pool de bordas (para componentes de mídia)**.</span><span class="sxs-lookup"><span data-stu-id="72798-116">Under **Associations**, select the check box next to **Associate Edge pool (for media components)**.</span></span>

9.  <span data-ttu-id="72798-117">Na lista, selecione o servidor de borda herdado.</span><span class="sxs-lookup"><span data-stu-id="72798-117">From the list, select the legacy Edge Server.</span></span>
    
    <span data-ttu-id="72798-118">![Caixa de diálogo Editar propriedades, selecionando a borda herdada] (images/JJ721875.feae8156-540e-4804-bb0a-2b5736ec2900(OCS.15).jpg "Caixa de diálogo Editar propriedades, selecionando a borda herdada")</span><span class="sxs-lookup"><span data-stu-id="72798-118">![Edit Properties dialog, selecting the legacy Edge](images/JJ721875.feae8156-540e-4804-bb0a-2b5736ec2900(OCS.15).jpg "Edit Properties dialog, selecting the legacy Edge")</span></span>  

10. <span data-ttu-id="72798-119">Clique em **OK** para fechar a página **Editar propriedades** .</span><span class="sxs-lookup"><span data-stu-id="72798-119">Click **OK** to close the **Edit Properties** page.</span></span>

11. <span data-ttu-id="72798-120">No **Construtor**de topologias, selecione o nó mais alto, **Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="72798-120">In **Topology Builder**, select the top-most node, **Lync Server**.</span></span>

12. <span data-ttu-id="72798-121">No menu **ação** , clique em **publicar topologia**e, em seguida, clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="72798-121">From the **Action** menu, click **Publish Topology**, and then click **Next**.</span></span>

13. <span data-ttu-id="72798-122">Quando o **Assistente de publicação** for concluído, clique em **concluir**.</span><span class="sxs-lookup"><span data-stu-id="72798-122">When the **Publishing wizard** completes, click **Finish**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

