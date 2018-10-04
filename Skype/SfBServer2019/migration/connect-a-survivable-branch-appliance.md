---
title: Conectar um aparelho de filial persistente
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 'Cada aparelho de filial persistente (SBA) é associado um pool de Front-End que serve como um registrador de backup para o SBA. Quando o pool é migrado para o Skype para Business Server 2019, o SBA Front-End deve ser removido de pool Front-End, enquanto o pool é atualizado, depois que o pool foi migrado para o Skype para Business Server 2019, o SBA pode ser novamente associado a F Front atualizados pool de término. Isso envolve excluindo o SBA da topologia de legado no construtor de topologia e depois adicionar o SBA para o Skype para Business Server 2019 topologia. Usuários hospedados no SBA primeiro deve ser movido para outro pool de Front-End antes de remover o SBA da topologia de legado. Após o SBA é adicionado ao Skype para Business Server 2019 topologia, esses usuários, em seguida, podem ser movidos volta ao SBA. Essas etapas estão resumidas abaixo:'
ms.openlocfilehash: ff35032d9abc5c1435e44dea7aca83d841b404c6
ms.sourcegitcommit: dd37c12a0312270955755ab2826adcfbae813790
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/04/2018
ms.locfileid: "25373746"
---
# <a name="connect-a-survivable-branch-appliance"></a><span data-ttu-id="05a2f-108">Conectar um aparelho de filial persistente</span><span class="sxs-lookup"><span data-stu-id="05a2f-108">Connect a Survivable Branch Appliance</span></span>

<span data-ttu-id="05a2f-109">Cada aparelho de filial persistente (SBA) é associado um pool de Front-End que serve como um registrador de backup para o SBA.</span><span class="sxs-lookup"><span data-stu-id="05a2f-109">Every Survivable Branch Appliance (SBA) is associated with a Front End pool that serves as a backup registrar for the SBA.</span></span> <span data-ttu-id="05a2f-110">Quando o pool de Front-End é migrado para o Skype para Business Server 2019, o SBA deve ser desassociado do pool de Front-End enquanto o pool é atualizado.</span><span class="sxs-lookup"><span data-stu-id="05a2f-110">When the Front End pool is migrated to Skype for Business Server 2019, the SBA must be disassociated from the Front End pool while the pool is upgraded.</span></span> <span data-ttu-id="05a2f-111">Depois que o pool foi migrado para o Skype para Business Server 2019, o SBA pode ser re-associado com o pool de Front-End atualizado.</span><span class="sxs-lookup"><span data-stu-id="05a2f-111">After the pool has been migrated to Skype for Business Server 2019, the SBA can be re-associated with the upgraded Front End pool.</span></span> <span data-ttu-id="05a2f-112">Isso envolve excluindo o SBA da topologia de legado no construtor de topologia e depois adicionar o SBA para o Skype para Business Server 2019 topologia.</span><span class="sxs-lookup"><span data-stu-id="05a2f-112">This involves deleting the SBA from the legacy topology in Topology Builder and then adding the SBA to the Skype for Business Server 2019 topology.</span></span> <span data-ttu-id="05a2f-113">Usuários hospedados no SBA primeiro deve ser movido para outro pool de Front-End antes de remover o SBA da topologia de legado.</span><span class="sxs-lookup"><span data-stu-id="05a2f-113">Users homed on the legacy SBA must first be moved to another Front End pool before removing the SBA from the topology.</span></span> <span data-ttu-id="05a2f-114">Depois que o SBA é adicionado ao Skype para Business Server 2019 topologia, esses usuários podem ser movidos de volta ao SBA.</span><span class="sxs-lookup"><span data-stu-id="05a2f-114">After the SBA is added to the Skype for Business Server 2019 topology, those users can be moved back to the SBA.</span></span> <span data-ttu-id="05a2f-115">Essas etapas estão resumidas abaixo:</span><span class="sxs-lookup"><span data-stu-id="05a2f-115">These steps are summarized below:</span></span>
  
1. <span data-ttu-id="05a2f-116">Mova os usuários ramificados hospedados no SBA herdado para outro pool de Front-End.</span><span class="sxs-lookup"><span data-stu-id="05a2f-116">Move branch users homed on the legacy SBA to another Front End pool.</span></span>
    
2. <span data-ttu-id="05a2f-117">Remova o SBA da topologia de legado para desconectar o pool de Front-End existente como um registrador de backup.</span><span class="sxs-lookup"><span data-stu-id="05a2f-117">Remove SBA from the legacy topology to disconnect the existing Front End pool as a backup registrar.</span></span>
    
3. <span data-ttu-id="05a2f-118">Adicione o SBA ao Skype para Business Server 2019 topologia e configure esse novo pool de Front-End como registrador de backup.</span><span class="sxs-lookup"><span data-stu-id="05a2f-118">Add SBA to the Skype for Business Server 2019 topology and configure this new Front End pool as the backup registrar.</span></span> 
    
4. <span data-ttu-id="05a2f-119">Mova os usuários da filial para o novo Skype para Business Server 2019 SBA.</span><span class="sxs-lookup"><span data-stu-id="05a2f-119">Move the branch users to the new Skype for Business Server 2019 SBA.</span></span>
    
### <a name="add-legacy-sba-branch-site-to-your-topology"></a><span data-ttu-id="05a2f-120">Adicionar o site de filial SBA herdado à sua topologia</span><span class="sxs-lookup"><span data-stu-id="05a2f-120">Add legacy SBA branch site to your topology</span></span>

1. <span data-ttu-id="05a2f-121">Abra o **Construtor de topologia**.</span><span class="sxs-lookup"><span data-stu-id="05a2f-121">Open **Topology Builder**.</span></span>
    
2. <span data-ttu-id="05a2f-122">No painel esquerdo, clique com o botão **sites de filiais**e clique em **Novo Site de filial**.</span><span class="sxs-lookup"><span data-stu-id="05a2f-122">In the left pane, right-click **Branch sites**, and then click **New Branch Site**.</span></span>
    
3. <span data-ttu-id="05a2f-123">Na caixa de diálogo **Definir novo Site de filial** , clique no **nome**e, em seguida, digite o nome do site de filial.</span><span class="sxs-lookup"><span data-stu-id="05a2f-123">In the **Define New Branch Site** dialog box, click **Name**, and then type the name of the branch site.</span></span>
    
4. <span data-ttu-id="05a2f-124">(Opcional) Clique em **Descrição**e digite uma descrição significativa para o site de filial.</span><span class="sxs-lookup"><span data-stu-id="05a2f-124">(Optional) Click **Description**, and then type a meaningful description for the branch site.</span></span>
    
5. <span data-ttu-id="05a2f-125">Clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="05a2f-125">Click **Next**.</span></span>
    
6. <span data-ttu-id="05a2f-126">(Opcional) Na próxima caixa de diálogo **Definir novo Site de filial** , siga um destes procedimentos:</span><span class="sxs-lookup"><span data-stu-id="05a2f-126">(Optional) In the next **Define New Branch Site** dialog box, do any of the following:</span></span> 
    
    1. <span data-ttu-id="05a2f-127">Clique em **Cidade**e digite o nome da cidade na qual o site de filial está localizado.</span><span class="sxs-lookup"><span data-stu-id="05a2f-127">Click **City**, and then type the name of the city in which the branch site is located.</span></span>
    
    2. <span data-ttu-id="05a2f-128">Clique em estado/região do \*\*\*\* e, em seguida, digite o nome do estado ou região na qual o site de filial está localizado.</span><span class="sxs-lookup"><span data-stu-id="05a2f-128">Click **State/Region**, and then type the name of the state or region in which the branch site is located.</span></span>
    
    3. <span data-ttu-id="05a2f-129">Clique em **Código do país**e digite o código de chamada de dois dígitos para o país/região no qual o site de filial está localizado.</span><span class="sxs-lookup"><span data-stu-id="05a2f-129">Click **Country Code**, and then type the two-digit calling code for the country/region in which the branch site is located.</span></span>
    
7. <span data-ttu-id="05a2f-130">Clique em **Avançar**e, em seguida, se você estiver usando um servidor ou aparelho de filial persistente neste site, não deixe de desmarque a caixa de seleção **Abrir o novo assistente persistente quando este assistente for fechado** .</span><span class="sxs-lookup"><span data-stu-id="05a2f-130">Click **Next**, and then, if you are using a Survivable Branch Appliance or Server at this site, be sure to clear the **Open the New Survivable Wizard when this wizard closes** check box.</span></span> <span data-ttu-id="05a2f-131">Clique em **Concluir**.</span><span class="sxs-lookup"><span data-stu-id="05a2f-131">Click **Finish**.</span></span>
    
8. <span data-ttu-id="05a2f-132">Para associar o SBA herdado para o Skype para pool de negócios 2019 Front-End Server:</span><span class="sxs-lookup"><span data-stu-id="05a2f-132">To associate the legacy SBA to the Skype for Business Server 2019 Front End pool:</span></span>
    
    1. <span data-ttu-id="05a2f-133">Expanda o site da filial que foi criado.</span><span class="sxs-lookup"><span data-stu-id="05a2f-133">Expand the branch site that has been created.</span></span> 
    
    2. <span data-ttu-id="05a2f-134">Com o botão direito na versão de legado e, em seguida, clique em **novo**.</span><span class="sxs-lookup"><span data-stu-id="05a2f-134">Right-click on legacy version, and then click **New**.</span></span>
    
    3. <span data-ttu-id="05a2f-135">Clique em **aparelho de filial persistente**.</span><span class="sxs-lookup"><span data-stu-id="05a2f-135">Click **Survivable Branch Appliance**.</span></span>
    
9. <span data-ttu-id="05a2f-136">Siga as instruções no assistente que é aberta.</span><span class="sxs-lookup"><span data-stu-id="05a2f-136">Follow the directions in the wizard that opens.</span></span> <span data-ttu-id="05a2f-137">Para obter informações sobre os itens do assistente, consulte</span><span class="sxs-lookup"><span data-stu-id="05a2f-137">For information about wizard items, see</span></span>    
   <!-- [Define a Survivable Branch Appliance or Server in Lync 2013](https://technet.microsoft.com/en-us/library/gg398280(v=ocs.15).aspx). -->
   <!-- The above link points to un-rebranded 2013 content we will need to discuss rebrand or bring forward -->
    
    > [!NOTE]
    > <span data-ttu-id="05a2f-138">Um aparelho de filial persistente só pode ser associado um repositório de monitoramento.</span><span class="sxs-lookup"><span data-stu-id="05a2f-138">A Survivable Branch Appliance can only be associated with a Monitoring Store.</span></span> 
  
10. <span data-ttu-id="05a2f-139">Se você não estiver usando um servidor ou aparelho de filial persistente neste site, desmarque a caixa de seleção **Abrir o novo assistente persistente quando este assistente for fechado** e clique em **Concluir**.</span><span class="sxs-lookup"><span data-stu-id="05a2f-139">If you are not using a Survivable Branch Appliance or Server at this site, clear the **Open the New Survivable Wizard when this wizard closes** check box, and then click **Finish**.</span></span>
    
11. <span data-ttu-id="05a2f-140">Repita as etapas anteriores para cada site de filial que você deseja adicionar à topologia.</span><span class="sxs-lookup"><span data-stu-id="05a2f-140">Repeat the previous steps for each branch site you want to add to the topology.</span></span>
    

