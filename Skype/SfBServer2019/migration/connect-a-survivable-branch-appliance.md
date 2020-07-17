---
title: Conectar um aparelho de filial persistente
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
description: 'Cada aparelho de filial persistente (SBA) é associado a um pool de front-ends que serve como um registrador de backup para o SBA. Quando o pool de front-ends é migrado para o Skype for Business Server 2019, o SBA deve ser desassociado do pool de front-ends enquanto o pool é atualizado, após o pool ter sido migrado para o Skype for Business Server 2019, o SBA pode ser associado novamente ao pool de front-ends atualizado. Isso envolve excluir o SBA da topologia herdada no construtor de topologia e, em seguida, adicionar o SBA à topologia do Skype for Business Server 2019. Os usuários hospedados no SBA herdado devem ser movidos primeiro para outro pool de front-ends antes da remoção do SBA da topologia. Após a adição da SBA à topologia do Skype for Business Server 2019, esses usuários podem ser movidos de volta para o SBA. Essas etapas estão resumidas abaixo:'
ms.openlocfilehash: 23fea7694a754b82ecad684d2ea02b603a6c7299
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/16/2020
ms.locfileid: "44751543"
---
# <a name="connect-a-survivable-branch-appliance"></a><span data-ttu-id="90923-108">Conectar um aparelho de filial persistente</span><span class="sxs-lookup"><span data-stu-id="90923-108">Connect a Survivable Branch Appliance</span></span>

<span data-ttu-id="90923-109">Cada aparelho de filial persistente (SBA) é associado a um pool de front-ends que funciona como um registrador de backup para o SBA.</span><span class="sxs-lookup"><span data-stu-id="90923-109">Every Survivable Branch Appliance (SBA) is associated with a Front End pool that serves as a backup registrar for the SBA.</span></span> <span data-ttu-id="90923-110">Quando o pool de front-ends é migrado para o Skype for Business Server 2019, o SBA deve ser desassociado do pool de front-ends enquanto o pool é atualizado.</span><span class="sxs-lookup"><span data-stu-id="90923-110">When the Front End pool is migrated to Skype for Business Server 2019, the SBA must be disassociated from the Front End pool while the pool is upgraded.</span></span> <span data-ttu-id="90923-111">Após o pool ter sido migrado para o Skype for Business Server 2019, o SBA pode ser novamente associado ao pool de front-ends atualizado.</span><span class="sxs-lookup"><span data-stu-id="90923-111">After the pool has been migrated to Skype for Business Server 2019, the SBA can be re-associated with the upgraded Front End pool.</span></span> <span data-ttu-id="90923-112">Isso envolve excluir o SBA da topologia herdada no construtor de topologia e, em seguida, adicionar o SBA à topologia do Skype for Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="90923-112">This involves deleting the SBA from the legacy topology in Topology Builder and then adding the SBA to the Skype for Business Server 2019 topology.</span></span> <span data-ttu-id="90923-113">Os usuários hospedados no SBA herdado devem ser movidos primeiro para outro pool de front-ends antes da remoção do SBA da topologia.</span><span class="sxs-lookup"><span data-stu-id="90923-113">Users homed on the legacy SBA must first be moved to another Front End pool before removing the SBA from the topology.</span></span> <span data-ttu-id="90923-114">Depois que o SBA é adicionado à topologia do Skype for Business Server 2019, esses usuários podem ser movidos de volta para o SBA.</span><span class="sxs-lookup"><span data-stu-id="90923-114">After the SBA is added to the Skype for Business Server 2019 topology, those users can be moved back to the SBA.</span></span> <span data-ttu-id="90923-115">Essas etapas estão resumidas abaixo:</span><span class="sxs-lookup"><span data-stu-id="90923-115">These steps are summarized below:</span></span>
  
1. <span data-ttu-id="90923-116">Mova usuários de filial hospedados no SBA herdado para outro pool de front-ends.</span><span class="sxs-lookup"><span data-stu-id="90923-116">Move branch users homed on the legacy SBA to another Front End pool.</span></span>
    
2. <span data-ttu-id="90923-117">Remova o SBA da topologia herdada para desconectar o pool de front-ends existente como um registrador de backup.</span><span class="sxs-lookup"><span data-stu-id="90923-117">Remove SBA from the legacy topology to disconnect the existing Front End pool as a backup registrar.</span></span>
    
3. <span data-ttu-id="90923-118">Adicione SBA à topologia do Skype for Business Server 2019 e configure esse novo pool de front-ends como o registrador de backup.</span><span class="sxs-lookup"><span data-stu-id="90923-118">Add SBA to the Skype for Business Server 2019 topology and configure this new Front End pool as the backup registrar.</span></span> 
    
4. <span data-ttu-id="90923-119">Mova os usuários da filial para o novo Skype for Business Server 2019 SBA.</span><span class="sxs-lookup"><span data-stu-id="90923-119">Move the branch users to the new Skype for Business Server 2019 SBA.</span></span>
    
### <a name="add-legacy-sba-branch-site-to-your-topology"></a><span data-ttu-id="90923-120">Adicionar site de filial herdado do SBA à sua topologia</span><span class="sxs-lookup"><span data-stu-id="90923-120">Add legacy SBA branch site to your topology</span></span>

1. <span data-ttu-id="90923-121">Abra o **Construtor de Topologia**.</span><span class="sxs-lookup"><span data-stu-id="90923-121">Open **Topology Builder**.</span></span>
    
2. <span data-ttu-id="90923-122">No painel esquerdo, clique com o botão direito do mouse em **sites de filial**e clique em **novo site de filial**.</span><span class="sxs-lookup"><span data-stu-id="90923-122">In the left pane, right-click **Branch sites**, and then click **New Branch Site**.</span></span>
    
3. <span data-ttu-id="90923-123">Na caixa de diálogo **Definir Novo Site de Filial**, clique em **Nome** e digite o nome do site de filial.</span><span class="sxs-lookup"><span data-stu-id="90923-123">In the **Define New Branch Site** dialog box, click **Name**, and then type the name of the branch site.</span></span>
    
4. <span data-ttu-id="90923-124">(Opcional) Clique em **Descrição** e digite uma descrição significativa para o site de filial.</span><span class="sxs-lookup"><span data-stu-id="90923-124">(Optional) Click **Description**, and then type a meaningful description for the branch site.</span></span>
    
5. <span data-ttu-id="90923-125">Clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="90923-125">Click **Next**.</span></span>
    
6. <span data-ttu-id="90923-126">(Opcional) Na próxima caixa de diálogo **Definir Novo Site de Filial**, execute uma das seguintes ações:</span><span class="sxs-lookup"><span data-stu-id="90923-126">(Optional) In the next **Define New Branch Site** dialog box, do any of the following:</span></span> 
    
    1. <span data-ttu-id="90923-127">Clique em **Cidade** e digite o nome da cidade na qual o site de filial está localizado.</span><span class="sxs-lookup"><span data-stu-id="90923-127">Click **City**, and then type the name of the city in which the branch site is located.</span></span>
    
    2. <span data-ttu-id="90923-128">Clique em **Estado/Região** e digite o nome do estado ou região na qual o site de filial está localizado.</span><span class="sxs-lookup"><span data-stu-id="90923-128">Click **State/Region**, and then type the name of the state or region in which the branch site is located.</span></span>
    
    3. <span data-ttu-id="90923-129">Clique em **Código do País** e digite o código de chamada de dois dígitos para o país/região no qual o site de filial está localizado.</span><span class="sxs-lookup"><span data-stu-id="90923-129">Click **Country Code**, and then type the two-digit calling code for the country/region in which the branch site is located.</span></span>
    
7. <span data-ttu-id="90923-130">Clique em **Avançar**e, se você estiver usando um servidor ou aparelho de filial persistente neste site, não deixe de desmarcar a caixa de seleção **abrir o novo assistente persistente quando este assistente fechar** .</span><span class="sxs-lookup"><span data-stu-id="90923-130">Click **Next**, and then, if you are using a Survivable Branch Appliance or Server at this site, be sure to clear the **Open the New Survivable Wizard when this wizard closes** check box.</span></span> <span data-ttu-id="90923-131">Clique em **Concluir**.</span><span class="sxs-lookup"><span data-stu-id="90923-131">Click **Finish**.</span></span>
    
8. <span data-ttu-id="90923-132">Para associar o SBA herdado ao pool de front-ends do Skype for Business Server 2019:</span><span class="sxs-lookup"><span data-stu-id="90923-132">To associate the legacy SBA to the Skype for Business Server 2019 Front End pool:</span></span>
    
    1. <span data-ttu-id="90923-133">Expanda o local ramificado que foi criado.</span><span class="sxs-lookup"><span data-stu-id="90923-133">Expand the branch site that has been created.</span></span> 
    
    2. <span data-ttu-id="90923-134">Clique com o botão direito do mouse em versão legada e clique em **novo**.</span><span class="sxs-lookup"><span data-stu-id="90923-134">Right-click on legacy version, and then click **New**.</span></span>
    
    3. <span data-ttu-id="90923-135">Clique em **aparelho de filial persistente**.</span><span class="sxs-lookup"><span data-stu-id="90923-135">Click **Survivable Branch Appliance**.</span></span>
    
9. <span data-ttu-id="90923-136">Siga as instruções no assistente que abrir.</span><span class="sxs-lookup"><span data-stu-id="90923-136">Follow the directions in the wizard that opens.</span></span> <span data-ttu-id="90923-137">Para obter informações sobre itens de assistente, consulte</span><span class="sxs-lookup"><span data-stu-id="90923-137">For information about wizard items, see</span></span>    
   <!-- [Define a Survivable Branch Appliance or Server in Lync 2013](https://technet.microsoft.com/library/gg398280(v=ocs.15).aspx). -->
   <!-- The above link points to un-rebranded 2013 content we will need to discuss rebrand or bring forward -->
    
    > [!NOTE]
    > <span data-ttu-id="90923-138">Um aparelho de filial persistente só pode ser associado a um repositório de monitoramento.</span><span class="sxs-lookup"><span data-stu-id="90923-138">A Survivable Branch Appliance can only be associated with a Monitoring Store.</span></span> 
  
10. <span data-ttu-id="90923-139">Se você não estiver usando um Aparelho de Filial Persistente ou Servidor nesse site, desmarque a caixa de seleção **Abrir o Novo Assistente Persistente quando este assistente fechar** e clique em **Concluir**.</span><span class="sxs-lookup"><span data-stu-id="90923-139">If you are not using a Survivable Branch Appliance or Server at this site, clear the **Open the New Survivable Wizard when this wizard closes** check box, and then click **Finish**.</span></span>
    
11. <span data-ttu-id="90923-140">Repita as etapas anteriores para cada site de filial que você deseja adicionar à topologia.</span><span class="sxs-lookup"><span data-stu-id="90923-140">Repeat the previous steps for each branch site you want to add to the topology.</span></span>
    

