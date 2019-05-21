---
title: Conectar um aparelho de filial persistente
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 'Cada aplicativo de ramificação sobreviventes (SBA) está associado a um pool de front-end que serve como registrador de backup para o SBA. Quando o pool de front-ends é migrado para o Skype for Business Server 2019, o SBA deve ser desassociado do pool de front-ends enquanto o pool é atualizado, assim que o pool é migrado para o Skype for Business Server 2019, o SBA pode ser reassociado ao E frontal atualizado nd pool. Isso envolve excluir o SBA da topologia herdada no construtor de topologias e, em seguida, adicionar o SBA à topologia do Skype for Business Server 2019. Os usuários hospedados no SBA herdado devem primeiro ser movidos para outro pool de front-end antes de remover SBA da topologia. Depois que o SBA é adicionado à topologia do Skype for Business Server 2019, esses usuários podem ser movidos de volta para o SBA. Estas etapas estão resumidas abaixo:'
ms.openlocfilehash: 7cb933018d24dafb978464338f01f97b25e15539
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34275542"
---
# <a name="connect-a-survivable-branch-appliance"></a><span data-ttu-id="f5c02-108">Conectar um aparelho de filial persistente</span><span class="sxs-lookup"><span data-stu-id="f5c02-108">Connect a Survivable Branch Appliance</span></span>

<span data-ttu-id="f5c02-109">Cada aplicativo de ramificação sobreviventes (SBA) está associado a um pool de front-end que funciona como registrador de backup para o SBA.</span><span class="sxs-lookup"><span data-stu-id="f5c02-109">Every Survivable Branch Appliance (SBA) is associated with a Front End pool that serves as a backup registrar for the SBA.</span></span> <span data-ttu-id="f5c02-110">Quando o pool de front-ends é migrado para o Skype for Business Server 2019, o SBA deve ser desassociado do pool de front-ends enquanto o pool é atualizado.</span><span class="sxs-lookup"><span data-stu-id="f5c02-110">When the Front End pool is migrated to Skype for Business Server 2019, the SBA must be disassociated from the Front End pool while the pool is upgraded.</span></span> <span data-ttu-id="f5c02-111">Após a migração do pool para o Skype for Business Server 2019, o SBA pode ser associado novamente ao pool de front-end atualizado.</span><span class="sxs-lookup"><span data-stu-id="f5c02-111">After the pool has been migrated to Skype for Business Server 2019, the SBA can be re-associated with the upgraded Front End pool.</span></span> <span data-ttu-id="f5c02-112">Isso envolve excluir o SBA da topologia herdada no construtor de topologias e, em seguida, adicionar o SBA à topologia do Skype for Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="f5c02-112">This involves deleting the SBA from the legacy topology in Topology Builder and then adding the SBA to the Skype for Business Server 2019 topology.</span></span> <span data-ttu-id="f5c02-113">Os usuários hospedados no SBA herdado devem primeiro ser movidos para outro pool de front-end antes de remover SBA da topologia.</span><span class="sxs-lookup"><span data-stu-id="f5c02-113">Users homed on the legacy SBA must first be moved to another Front End pool before removing the SBA from the topology.</span></span> <span data-ttu-id="f5c02-114">Após a SBA ser adicionada à topologia do Skype for Business Server 2019, esses usuários podem ser removidas para o SBA.</span><span class="sxs-lookup"><span data-stu-id="f5c02-114">After the SBA is added to the Skype for Business Server 2019 topology, those users can be moved back to the SBA.</span></span> <span data-ttu-id="f5c02-115">Estas etapas estão resumidas abaixo:</span><span class="sxs-lookup"><span data-stu-id="f5c02-115">These steps are summarized below:</span></span>
  
1. <span data-ttu-id="f5c02-116">Mova os usuários da ramificação na SBA herdada para outro pool de front-ends.</span><span class="sxs-lookup"><span data-stu-id="f5c02-116">Move branch users homed on the legacy SBA to another Front End pool.</span></span>
    
2. <span data-ttu-id="f5c02-117">Remova o SBA da topologia herdada para desconectar o pool de front-end existente como um registrador de backup.</span><span class="sxs-lookup"><span data-stu-id="f5c02-117">Remove SBA from the legacy topology to disconnect the existing Front End pool as a backup registrar.</span></span>
    
3. <span data-ttu-id="f5c02-118">Adicione SBA à topologia do Skype for Business Server 2019 e configure esse novo pool de front-end como o registrador de backup.</span><span class="sxs-lookup"><span data-stu-id="f5c02-118">Add SBA to the Skype for Business Server 2019 topology and configure this new Front End pool as the backup registrar.</span></span> 
    
4. <span data-ttu-id="f5c02-119">Mova os usuários da filial para o novo Skype for Business Server 2019 SBA.</span><span class="sxs-lookup"><span data-stu-id="f5c02-119">Move the branch users to the new Skype for Business Server 2019 SBA.</span></span>
    
### <a name="add-legacy-sba-branch-site-to-your-topology"></a><span data-ttu-id="f5c02-120">Adicionar site de ramificação SBA herdada à sua topologia</span><span class="sxs-lookup"><span data-stu-id="f5c02-120">Add legacy SBA branch site to your topology</span></span>

1. <span data-ttu-id="f5c02-121">Abrir o **Construtor**de topologias.</span><span class="sxs-lookup"><span data-stu-id="f5c02-121">Open **Topology Builder**.</span></span>
    
2. <span data-ttu-id="f5c02-122">No painel esquerdo, clique com o botão direito do mouse em **sites**de ramificação e clique em **novo site de filial**.</span><span class="sxs-lookup"><span data-stu-id="f5c02-122">In the left pane, right-click **Branch sites**, and then click **New Branch Site**.</span></span>
    
3. <span data-ttu-id="f5c02-123">Na caixa de diálogo **definir novo site de filial** , clique em **nome**e digite o nome do site de filial.</span><span class="sxs-lookup"><span data-stu-id="f5c02-123">In the **Define New Branch Site** dialog box, click **Name**, and then type the name of the branch site.</span></span>
    
4. <span data-ttu-id="f5c02-124">Adicionais Clique em **Descrição**e digite uma descrição significativa para o site da filial.</span><span class="sxs-lookup"><span data-stu-id="f5c02-124">(Optional) Click **Description**, and then type a meaningful description for the branch site.</span></span>
    
5. <span data-ttu-id="f5c02-125">Click **Next**.</span><span class="sxs-lookup"><span data-stu-id="f5c02-125">Click **Next**.</span></span>
    
6. <span data-ttu-id="f5c02-126">Adicionais Na caixa de diálogo próximo **definir novo site** de filiais, siga um destes procedimentos:</span><span class="sxs-lookup"><span data-stu-id="f5c02-126">(Optional) In the next **Define New Branch Site** dialog box, do any of the following:</span></span> 
    
    1. <span data-ttu-id="f5c02-127">Clique em **cidade**e digite o nome da cidade na qual o site da filial está localizado.</span><span class="sxs-lookup"><span data-stu-id="f5c02-127">Click **City**, and then type the name of the city in which the branch site is located.</span></span>
    
    2. <span data-ttu-id="f5c02-128">Clique em **estado/região**e, em seguida, digite o nome do Estado ou da região em que o site da filial está localizado.</span><span class="sxs-lookup"><span data-stu-id="f5c02-128">Click **State/Region**, and then type the name of the state or region in which the branch site is located.</span></span>
    
    3. <span data-ttu-id="f5c02-129">Clique em **código do país**e, em seguida, digite o código de chamada de dois dígitos para o país/região no qual o site da filial está localizado.</span><span class="sxs-lookup"><span data-stu-id="f5c02-129">Click **Country Code**, and then type the two-digit calling code for the country/region in which the branch site is located.</span></span>
    
7. <span data-ttu-id="f5c02-130">Clique em **Avançar**e, se você estiver usando um aplicativo ou aplicativo de ramificação sobreviventes neste site, certifique-se de desmarcar a caixa de seleção **abrir o assistente de Nova persistência quando este assistente for fechado** .</span><span class="sxs-lookup"><span data-stu-id="f5c02-130">Click **Next**, and then, if you are using a Survivable Branch Appliance or Server at this site, be sure to clear the **Open the New Survivable Wizard when this wizard closes** check box.</span></span> <span data-ttu-id="f5c02-131">Clique em **Concluir**.</span><span class="sxs-lookup"><span data-stu-id="f5c02-131">Click **Finish**.</span></span>
    
8. <span data-ttu-id="f5c02-132">Para associar o SBA herdado ao pool de front-ends do Skype for Business Server 2019:</span><span class="sxs-lookup"><span data-stu-id="f5c02-132">To associate the legacy SBA to the Skype for Business Server 2019 Front End pool:</span></span>
    
    1. <span data-ttu-id="f5c02-133">Expanda o site de ramificação que foi criado.</span><span class="sxs-lookup"><span data-stu-id="f5c02-133">Expand the branch site that has been created.</span></span> 
    
    2. <span data-ttu-id="f5c02-134">Clique com o botão direito do mouse em versão herdada e clique em **novo**.</span><span class="sxs-lookup"><span data-stu-id="f5c02-134">Right-click on legacy version, and then click **New**.</span></span>
    
    3. <span data-ttu-id="f5c02-135">Clique em **aparelho para ramificação sobreviventes**.</span><span class="sxs-lookup"><span data-stu-id="f5c02-135">Click **Survivable Branch Appliance**.</span></span>
    
9. <span data-ttu-id="f5c02-136">Siga as instruções no assistente que é aberto.</span><span class="sxs-lookup"><span data-stu-id="f5c02-136">Follow the directions in the wizard that opens.</span></span> <span data-ttu-id="f5c02-137">Para obter informações sobre itens do assistente, consulte</span><span class="sxs-lookup"><span data-stu-id="f5c02-137">For information about wizard items, see</span></span>    
   <!-- [Define a Survivable Branch Appliance or Server in Lync 2013](https://technet.microsoft.com/en-us/library/gg398280(v=ocs.15).aspx). -->
   <!-- The above link points to un-rebranded 2013 content we will need to discuss rebrand or bring forward -->
    
    > [!NOTE]
    > <span data-ttu-id="f5c02-138">Um aparelho de ramificação sobreviventes só pode ser associado a uma loja de monitoramento.</span><span class="sxs-lookup"><span data-stu-id="f5c02-138">A Survivable Branch Appliance can only be associated with a Monitoring Store.</span></span> 
  
10. <span data-ttu-id="f5c02-139">Se você não estiver usando um aplicativo ou aplicativo de ramificação sobreviventes neste site, desmarque a caixa de seleção **abrir o assistente de Nova persistência quando este assistente for fechado** e clique em **concluir**.</span><span class="sxs-lookup"><span data-stu-id="f5c02-139">If you are not using a Survivable Branch Appliance or Server at this site, clear the **Open the New Survivable Wizard when this wizard closes** check box, and then click **Finish**.</span></span>
    
11. <span data-ttu-id="f5c02-140">Repita as etapas anteriores para cada site de ramificação que você deseja adicionar à topologia.</span><span class="sxs-lookup"><span data-stu-id="f5c02-140">Repeat the previous steps for each branch site you want to add to the topology.</span></span>
    

