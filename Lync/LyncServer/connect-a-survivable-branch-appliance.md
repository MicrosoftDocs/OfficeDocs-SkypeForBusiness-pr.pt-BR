---
title: Conectar um aparelho de filial persistente
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Connect a Survivable Branch Appliance
ms:assetid: fe3167e2-d1b1-4cd4-bf30-262e0e7d14e8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721948(v=OCS.15)
ms:contentKeyID: 49733886
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5ef6294deba25998c5ad16254e464b6f682fa660
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41723161"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="connect-a-survivable-branch-appliance"></a><span data-ttu-id="6c943-102">Conectar um aparelho de filial persistente</span><span class="sxs-lookup"><span data-stu-id="6c943-102">Connect a Survivable Branch Appliance</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6c943-103">_**Tópico da última modificação:** 2012-10-19_</span><span class="sxs-lookup"><span data-stu-id="6c943-103">_**Topic Last Modified:** 2012-10-19_</span></span>

<span data-ttu-id="6c943-104">Cada aplicativo de ramificação sobreviventes (SBA) está associado a um pool de front-end que serve como registrador de backup para o SBA.</span><span class="sxs-lookup"><span data-stu-id="6c943-104">Every Survivable Branch Appliance (SBA) is associated with a Front End pool which serves as a backup registrar for the SBA.</span></span> <span data-ttu-id="6c943-105">Quando o pool de front-ends é migrado para o Lync Server 2013, o SBA deve ser desassociado do pool de front-end do Lync Server 2010 enquanto o pool é atualizado, após a migração do pool para o Lync Server 2013, o SBA pode ser novamente associado ao pool de front-end atualizado.</span><span class="sxs-lookup"><span data-stu-id="6c943-105">When the Front End pool is migrated to Lync Server 2013, the SBA must be disassociated from the Lync Server 2010 Front End pool while the pool is upgraded, Once the pool has been migrated to Lync Server 2013, the SBA can be re-associated with the upgraded Front End pool.</span></span> <span data-ttu-id="6c943-106">Isso envolve excluir o SBA da topologia herdada do Lync Server 2010 no construtor de topologias e, em seguida, adicionar SBA à topologia 2013 do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="6c943-106">This involves deleting the SBA from the legacy Lync Server 2010 topology in Topology Builder and then adding the SBA to the Lync Server 2013 topology.</span></span> <span data-ttu-id="6c943-107">Os usuários hospedados no Lync Server 2010 herdado SBA devem ser movidos para outro pool de front-end antes de remover SBA da topologia.</span><span class="sxs-lookup"><span data-stu-id="6c943-107">Users homed on the legacy Lync Server 2010 SBA must first be moved to another Front End pool before removing the SBA from the topology.</span></span> <span data-ttu-id="6c943-108">Depois que o SBA é adicionado à topologia do Lync Server 2013, esses usuários podem ser movidos de volta para o SBA.</span><span class="sxs-lookup"><span data-stu-id="6c943-108">Once the SBA is added to the Lync Server 2013 topology, those users can then be moved back to the SBA.</span></span> <span data-ttu-id="6c943-109">Estas etapas estão resumidas abaixo:</span><span class="sxs-lookup"><span data-stu-id="6c943-109">These steps are summarized below:</span></span>

1.  <span data-ttu-id="6c943-110">Mova os usuários da ramificação hospedados no SBA do Lync Server 2010 para outro pool de front-ends.</span><span class="sxs-lookup"><span data-stu-id="6c943-110">Move branch users homed on the legacy SBA Lync Server 2010 to another Front End pool.</span></span>

2.  <span data-ttu-id="6c943-111">Remova o SBA da topologia herdada do Lync Server 2010 para desconectar o pool de front-ends existente como um registrador de backup.</span><span class="sxs-lookup"><span data-stu-id="6c943-111">Remove SBA from the legacy Lync Server 2010 topology to disconnect the existing Front End pool as a backup registrar.</span></span>

3.  <span data-ttu-id="6c943-112">Adicione SBA à topologia do Lync Server 2013 e configure esse novo pool de front-end como o registrador de backup.</span><span class="sxs-lookup"><span data-stu-id="6c943-112">Add SBA to the Lync Server 2013 topology and configure this new Front End pool as the backup registrar.</span></span>

4.  <span data-ttu-id="6c943-113">Mova os usuários da ramificação para o novo Lync Server 2013 SBA.</span><span class="sxs-lookup"><span data-stu-id="6c943-113">Move the branch users to the new Lync Server 2013 SBA.</span></span>

<span data-ttu-id="6c943-114">**Adicionar site de ramificação do Lync Server 2010 SBA à sua topologia**</span><span class="sxs-lookup"><span data-stu-id="6c943-114">**Add Lync Server 2010 SBA Branch Site to Your Topology**</span></span>

1.  <span data-ttu-id="6c943-115">Abrir o **Construtor de topologias**.</span><span class="sxs-lookup"><span data-stu-id="6c943-115">Open **Topology Builder**.</span></span>

2.  <span data-ttu-id="6c943-116">No painel esquerdo, clique com o botão direito do mouse em **sites de ramificação**e clique em **novo site de filial**.</span><span class="sxs-lookup"><span data-stu-id="6c943-116">In the left pane right-click **Branch sites**, and then click **New Branch Site**.</span></span>

3.  <span data-ttu-id="6c943-117">Na caixa de diálogo **definir novo site de filial** , clique em **nome**e digite o nome do site de filial.</span><span class="sxs-lookup"><span data-stu-id="6c943-117">In the **Define New Branch Site** dialog box, click **Name**, and then type the name of the branch site.</span></span>

4.  <span data-ttu-id="6c943-118">Adicionais Clique em **Descrição**e digite uma descrição significativa para o site da filial.</span><span class="sxs-lookup"><span data-stu-id="6c943-118">(Optional) Click **Description**, and then type a meaningful description for the branch site.</span></span>

5.  <span data-ttu-id="6c943-119">Click **Next**.</span><span class="sxs-lookup"><span data-stu-id="6c943-119">Click **Next**.</span></span>

6.  <span data-ttu-id="6c943-120">Adicionais Na caixa de diálogo próximo **definir novo site de filiais** , siga um destes procedimentos:</span><span class="sxs-lookup"><span data-stu-id="6c943-120">(Optional) In the next **Define New Branch Site** dialog box, do any of the following:</span></span>
    
    1.  <span data-ttu-id="6c943-121">Clique em **cidade**e digite o nome da cidade na qual o site da filial está localizado.</span><span class="sxs-lookup"><span data-stu-id="6c943-121">Click **City**, and then type the name of the city in which the branch site is located.</span></span>
    
    2.  <span data-ttu-id="6c943-122">Clique em **estado/região**e, em seguida, digite o nome do Estado ou da região em que o site da filial está localizado.</span><span class="sxs-lookup"><span data-stu-id="6c943-122">Click **State/Region**, and then type the name of the state or region in which the branch site is located.</span></span>
    
    3.  <span data-ttu-id="6c943-123">Clique em **código do país**e, em seguida, digite o código de chamada de dois dígitos para o país/região no qual o site da filial está localizado.</span><span class="sxs-lookup"><span data-stu-id="6c943-123">Click **Country Code**, and then type the two-digit calling code for the country/region in which the branch site is located.</span></span>

7.  <span data-ttu-id="6c943-124">Clique em **Avançar**e, em seguida, siga um destes procedimentos:</span><span class="sxs-lookup"><span data-stu-id="6c943-124">Click **Next**, and then do one of the following:</span></span>
    
    1.  <span data-ttu-id="6c943-125">Se você estiver usando um aplicativo ou um aplicativo de ramificação do Lync 2010 que não seja o site, desmarque a opção **abrir o novo assistente para sobreviver quando este assistente fechar a** opção.</span><span class="sxs-lookup"><span data-stu-id="6c943-125">If you are using a Lync 2010 Survivable Branch Appliance or Server at this site, be sure to uncheck the **Open the New Survivable Wizard when this wizard closes** option.</span></span> <span data-ttu-id="6c943-126">Clique em **Concluir**.</span><span class="sxs-lookup"><span data-stu-id="6c943-126">Click **Finish**.</span></span>

8.  <span data-ttu-id="6c943-127">Para associar a herdada do Lync Server 2010 SBA ao pool de front-ends do Lync Server 2013:</span><span class="sxs-lookup"><span data-stu-id="6c943-127">To associate the legacy Lync Server 2010 SBA to the Lync Server 2013 Front End pool:</span></span>
    
    1.  <span data-ttu-id="6c943-128">Expanda o site de ramificação que foi criado.</span><span class="sxs-lookup"><span data-stu-id="6c943-128">Expand the branch site that has been created.</span></span>
    
    2.  <span data-ttu-id="6c943-129">Clique com o botão direito do mouse no **Lync Server 2010** e clique em **novo**.</span><span class="sxs-lookup"><span data-stu-id="6c943-129">Right click on **Lync Server 2010** and then click **New**.</span></span>
    
    3.  <span data-ttu-id="6c943-130">Clique em **aparelho para ramificação sobreviventes...**</span><span class="sxs-lookup"><span data-stu-id="6c943-130">Click **Survivable Branch Appliance…**</span></span>

9.  <span data-ttu-id="6c943-131">Siga as instruções no assistente que é aberto.</span><span class="sxs-lookup"><span data-stu-id="6c943-131">Follow the directions in the wizard that opens.</span></span> <span data-ttu-id="6c943-132">Para saber mais sobre os itens do assistente, confira [definir um aplicativo ou aplicativo de ramificação sobreviventes no Lync Server 2013](lync-server-2013-define-a-survivable-branch-appliance-or-server.md).</span><span class="sxs-lookup"><span data-stu-id="6c943-132">For information about wizard items, see [Define a Survivable Branch Appliance or Server in Lync Server 2013](lync-server-2013-define-a-survivable-branch-appliance-or-server.md).</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="6c943-133">Um appliance de ramificação do Lync Server 2010 pode ser associado apenas a uma loja de monitoramento 2010 do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="6c943-133">A Lync Server 2010 Survivable Branch Appliance can only be associated with a Lync Server 2010 Monitoring Store.</span></span>

    
    </div>

10. <span data-ttu-id="6c943-134">Se você não estiver usando um aplicativo ou aplicativo de ramificação sobreviventes neste site, desmarque a caixa de seleção **abrir o assistente de Nova persistência quando este assistente for fechado** e clique em **concluir**.</span><span class="sxs-lookup"><span data-stu-id="6c943-134">If you are not using a Survivable Branch Appliance or Server at this site, clear the **Open the New Survivable Wizard when this wizard closes** check box, and then click **Finish**.</span></span>

11. <span data-ttu-id="6c943-135">Repita as etapas anteriores para cada site de ramificação que você deseja adicionar à topologia.</span><span class="sxs-lookup"><span data-stu-id="6c943-135">Repeat the previous steps for each branch site you want to add to the topology.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

