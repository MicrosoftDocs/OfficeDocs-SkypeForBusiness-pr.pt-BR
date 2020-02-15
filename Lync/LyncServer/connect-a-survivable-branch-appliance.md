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
ms.openlocfilehash: 77382343fa7736c90ac208f8d13f81bc74969efa
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/14/2020
ms.locfileid: "42006517"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="connect-a-survivable-branch-appliance"></a><span data-ttu-id="d7fa1-102">Conectar um aparelho de filial persistente</span><span class="sxs-lookup"><span data-stu-id="d7fa1-102">Connect a Survivable Branch Appliance</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d7fa1-103">_**Última modificação do tópico:** 2012-10-19_</span><span class="sxs-lookup"><span data-stu-id="d7fa1-103">_**Topic Last Modified:** 2012-10-19_</span></span>

<span data-ttu-id="d7fa1-104">Cada aparelho de filial persistente (SBA) é associado a um pool de front-ends que serve como um registrador de backup para o SBA.</span><span class="sxs-lookup"><span data-stu-id="d7fa1-104">Every Survivable Branch Appliance (SBA) is associated with a Front End pool which serves as a backup registrar for the SBA.</span></span> <span data-ttu-id="d7fa1-105">Quando o pool de front-ends é migrado para o Lync Server 2013, o SBA deve ser desassociado do pool de front-ends do Lync Server 2010 enquanto o pool é atualizado, após o pool ter sido migrado para o Lync Server 2013, o SBA pode ser novamente associado ao pool de front-ends atualizado.</span><span class="sxs-lookup"><span data-stu-id="d7fa1-105">When the Front End pool is migrated to Lync Server 2013, the SBA must be disassociated from the Lync Server 2010 Front End pool while the pool is upgraded, Once the pool has been migrated to Lync Server 2013, the SBA can be re-associated with the upgraded Front End pool.</span></span> <span data-ttu-id="d7fa1-106">Isso envolve excluir o SBA da topologia herdada do Lync Server 2010 no construtor de topologia e, em seguida, adicionar o SBA à topologia 2013 do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="d7fa1-106">This involves deleting the SBA from the legacy Lync Server 2010 topology in Topology Builder and then adding the SBA to the Lync Server 2013 topology.</span></span> <span data-ttu-id="d7fa1-107">Os usuários hospedados no Lync Server 2010 herdado SBA devem ser movidos primeiro para outro pool de front-ends antes da remoção do SBA da topologia.</span><span class="sxs-lookup"><span data-stu-id="d7fa1-107">Users homed on the legacy Lync Server 2010 SBA must first be moved to another Front End pool before removing the SBA from the topology.</span></span> <span data-ttu-id="d7fa1-108">Depois que o SBA é adicionado à topologia do Lync Server 2013, esses usuários podem ser movidos de volta para o SBA.</span><span class="sxs-lookup"><span data-stu-id="d7fa1-108">Once the SBA is added to the Lync Server 2013 topology, those users can then be moved back to the SBA.</span></span> <span data-ttu-id="d7fa1-109">Essas etapas estão resumidas abaixo:</span><span class="sxs-lookup"><span data-stu-id="d7fa1-109">These steps are summarized below:</span></span>

1.  <span data-ttu-id="d7fa1-110">Mover usuários de filial hospedados no SBA Lync Server 2010 herdado para outro pool de front-ends.</span><span class="sxs-lookup"><span data-stu-id="d7fa1-110">Move branch users homed on the legacy SBA Lync Server 2010 to another Front End pool.</span></span>

2.  <span data-ttu-id="d7fa1-111">Remova o SBA da topologia herdada do Lync Server 2010 para desconectar o pool de front-ends existente como um registrador de backup.</span><span class="sxs-lookup"><span data-stu-id="d7fa1-111">Remove SBA from the legacy Lync Server 2010 topology to disconnect the existing Front End pool as a backup registrar.</span></span>

3.  <span data-ttu-id="d7fa1-112">Adicione SBA à topologia do Lync Server 2013 e configure esse novo pool de front-ends como o registrador de backup.</span><span class="sxs-lookup"><span data-stu-id="d7fa1-112">Add SBA to the Lync Server 2013 topology and configure this new Front End pool as the backup registrar.</span></span>

4.  <span data-ttu-id="d7fa1-113">Mova os usuários da filial para o novo Lync Server 2013 SBA.</span><span class="sxs-lookup"><span data-stu-id="d7fa1-113">Move the branch users to the new Lync Server 2013 SBA.</span></span>

<span data-ttu-id="d7fa1-114">**Adicione Lync Server 2010 SBA Branch Site à sua topologia**</span><span class="sxs-lookup"><span data-stu-id="d7fa1-114">**Add Lync Server 2010 SBA Branch Site to Your Topology**</span></span>

1.  <span data-ttu-id="d7fa1-115">Abra o **Construtor de Topologias**.</span><span class="sxs-lookup"><span data-stu-id="d7fa1-115">Open **Topology Builder**.</span></span>

2.  <span data-ttu-id="d7fa1-116">No painel esquerdo, clique com o botão direito do mouse em **Locais ramificados** e clique em **Novo local ramificado**.</span><span class="sxs-lookup"><span data-stu-id="d7fa1-116">In the left pane right-click **Branch sites**, and then click **New Branch Site**.</span></span>

3.  <span data-ttu-id="d7fa1-117">Na caixa de diálogo **Definir Novo Site de Filial**, clique em **Nome** e digite o nome do site de filial.</span><span class="sxs-lookup"><span data-stu-id="d7fa1-117">In the **Define New Branch Site** dialog box, click **Name**, and then type the name of the branch site.</span></span>

4.  <span data-ttu-id="d7fa1-118">(Opcional) Clique em **Descrição** e digite uma descrição significativa para o site de filial.</span><span class="sxs-lookup"><span data-stu-id="d7fa1-118">(Optional) Click **Description**, and then type a meaningful description for the branch site.</span></span>

5.  <span data-ttu-id="d7fa1-119">Clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="d7fa1-119">Click **Next**.</span></span>

6.  <span data-ttu-id="d7fa1-120">(Opcional) Na próxima caixa de diálogo **Definir Novo Site de Filial**, execute uma das seguintes ações:</span><span class="sxs-lookup"><span data-stu-id="d7fa1-120">(Optional) In the next **Define New Branch Site** dialog box, do any of the following:</span></span>
    
    1.  <span data-ttu-id="d7fa1-121">Clique em **Cidade** e digite o nome da cidade na qual o site de filial está localizado.</span><span class="sxs-lookup"><span data-stu-id="d7fa1-121">Click **City**, and then type the name of the city in which the branch site is located.</span></span>
    
    2.  <span data-ttu-id="d7fa1-122">Clique em **Estado/Região** e digite o nome do estado ou região na qual o site de filial está localizado.</span><span class="sxs-lookup"><span data-stu-id="d7fa1-122">Click **State/Region**, and then type the name of the state or region in which the branch site is located.</span></span>
    
    3.  <span data-ttu-id="d7fa1-123">Clique em **Código do País** e digite o código de chamada de dois dígitos para o país/região no qual o site de filial está localizado.</span><span class="sxs-lookup"><span data-stu-id="d7fa1-123">Click **Country Code**, and then type the two-digit calling code for the country/region in which the branch site is located.</span></span>

7.  <span data-ttu-id="d7fa1-124">Clique em **Avançar** e execute uma das seguintes ações:</span><span class="sxs-lookup"><span data-stu-id="d7fa1-124">Click **Next**, and then do one of the following:</span></span>
    
    1.  <span data-ttu-id="d7fa1-p102">Se você estiver usando um Aparelho de Filial Persistente  Lync 2010 ou Servidor nesse site, certifique-se de desmarcar a caixa de seleção **Abrir o Novo Assistente Persistente quando este assistente fechar** e clique em **Concluir**.</span><span class="sxs-lookup"><span data-stu-id="d7fa1-p102">If you are using a Lync 2010 Survivable Branch Appliance or Server at this site, be sure to uncheck the **Open the New Survivable Wizard when this wizard closes** option. Click **Finish**.</span></span>

8.  <span data-ttu-id="d7fa1-127">Para associar o SBA herdado do Lync Server 2010 ao pool de front-ends do Lync Server 2013:</span><span class="sxs-lookup"><span data-stu-id="d7fa1-127">To associate the legacy Lync Server 2010 SBA to the Lync Server 2013 Front End pool:</span></span>
    
    1.  <span data-ttu-id="d7fa1-128">Expanda o local ramificado que foi criado.</span><span class="sxs-lookup"><span data-stu-id="d7fa1-128">Expand the branch site that has been created.</span></span>
    
    2.  <span data-ttu-id="d7fa1-129">Clique com o botão direito do mouse em **Lync Server 2010** e clique em **Novo**.</span><span class="sxs-lookup"><span data-stu-id="d7fa1-129">Right click on **Lync Server 2010** and then click **New**.</span></span>
    
    3.  <span data-ttu-id="d7fa1-130">Clique em **Aparelho de Filial Persistente**</span><span class="sxs-lookup"><span data-stu-id="d7fa1-130">Click **Survivable Branch Appliance…**</span></span>

9.  <span data-ttu-id="d7fa1-131">Siga as instruções no assistente que abrir.</span><span class="sxs-lookup"><span data-stu-id="d7fa1-131">Follow the directions in the wizard that opens.</span></span> <span data-ttu-id="d7fa1-132">Para obter informações sobre itens de assistente, consulte [definir um aparelho de filial persistente ou servidor no Lync Server 2013](lync-server-2013-define-a-survivable-branch-appliance-or-server.md).</span><span class="sxs-lookup"><span data-stu-id="d7fa1-132">For information about wizard items, see [Define a Survivable Branch Appliance or Server in Lync Server 2013](lync-server-2013-define-a-survivable-branch-appliance-or-server.md).</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="d7fa1-133">Um aparelho de filial persistente do Lync Server 2010 só pode ser associado a um repositório de monitoramento do Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="d7fa1-133">A Lync Server 2010 Survivable Branch Appliance can only be associated with a Lync Server 2010 Monitoring Store.</span></span>

    
    </div>

10. <span data-ttu-id="d7fa1-134">Se você não estiver usando um Aparelho de Filial Persistente ou Servidor nesse site, desmarque a caixa de seleção **Abrir o Novo Assistente Persistente quando este assistente fechar** e clique em **Concluir**.</span><span class="sxs-lookup"><span data-stu-id="d7fa1-134">If you are not using a Survivable Branch Appliance or Server at this site, clear the **Open the New Survivable Wizard when this wizard closes** check box, and then click **Finish**.</span></span>

11. <span data-ttu-id="d7fa1-135">Repita as etapas anteriores para cada site de filial que você deseja adicionar à topologia.</span><span class="sxs-lookup"><span data-stu-id="d7fa1-135">Repeat the previous steps for each branch site you want to add to the topology.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

