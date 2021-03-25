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
description: 'Cada Dispositivo de FilialVivível (SBA) está associado a um pool de Front-End que serve como um registrador de backup para o SBA. Quando o pool de Front-End é migrado para o Skype for Business Server 2019, o SBA deve ser desassociado do pool de Front-End enquanto o pool é atualizado, Depois que o pool tiver sido migrado para o Skype for Business Server 2019, o SBA poderá ser reassociado com o pool de Front-End atualizado. Isso envolve excluir o SBA da topologia herdada no Construtor de Topologias e adicionar o SBA à topologia do Skype for Business Server 2019. Os usuários que estão no SBA herdado devem primeiro ser movidos para outro pool de Front-End antes de remover o SBA da topologia. Depois que o SBA for adicionado à topologia do Skype for Business Server 2019, esses usuários poderão ser movidos de volta para o SBA. Essas etapas estão resumidas abaixo:'
ms.openlocfilehash: e56bae1631a315b6f42042fb6a7bedd4f144a1b6
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51113337"
---
# <a name="connect-a-survivable-branch-appliance"></a><span data-ttu-id="f2cef-108">Conectar um aparelho de filial persistente</span><span class="sxs-lookup"><span data-stu-id="f2cef-108">Connect a Survivable Branch Appliance</span></span>

<span data-ttu-id="f2cef-109">Cada Dispositivo de FilialVivível (SBA) está associado a um pool de Front-End que serve como um registrador de backup para o SBA.</span><span class="sxs-lookup"><span data-stu-id="f2cef-109">Every Survivable Branch Appliance (SBA) is associated with a Front End pool that serves as a backup registrar for the SBA.</span></span> <span data-ttu-id="f2cef-110">Quando o pool de Front-End é migrado para o Skype for Business Server 2019, o SBA deve ser desassociado do pool de Front-End enquanto o pool é atualizado.</span><span class="sxs-lookup"><span data-stu-id="f2cef-110">When the Front End pool is migrated to Skype for Business Server 2019, the SBA must be disassociated from the Front End pool while the pool is upgraded.</span></span> <span data-ttu-id="f2cef-111">Depois que o pool for migrado para o Skype for Business Server 2019, o SBA poderá ser reassociado ao pool de Front-End atualizado.</span><span class="sxs-lookup"><span data-stu-id="f2cef-111">After the pool has been migrated to Skype for Business Server 2019, the SBA can be re-associated with the upgraded Front End pool.</span></span> <span data-ttu-id="f2cef-112">Isso envolve excluir o SBA da topologia herdada no Construtor de Topologias e adicionar o SBA à topologia do Skype for Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="f2cef-112">This involves deleting the SBA from the legacy topology in Topology Builder and then adding the SBA to the Skype for Business Server 2019 topology.</span></span> <span data-ttu-id="f2cef-113">Os usuários que estão no SBA herdado devem primeiro ser movidos para outro pool de Front-End antes de remover o SBA da topologia.</span><span class="sxs-lookup"><span data-stu-id="f2cef-113">Users homed on the legacy SBA must first be moved to another Front End pool before removing the SBA from the topology.</span></span> <span data-ttu-id="f2cef-114">Depois que o SBA for adicionado à topologia do Skype for Business Server 2019, esses usuários poderão ser movidos de volta para o SBA.</span><span class="sxs-lookup"><span data-stu-id="f2cef-114">After the SBA is added to the Skype for Business Server 2019 topology, those users can be moved back to the SBA.</span></span> <span data-ttu-id="f2cef-115">Essas etapas estão resumidas abaixo:</span><span class="sxs-lookup"><span data-stu-id="f2cef-115">These steps are summarized below:</span></span>
  
1. <span data-ttu-id="f2cef-116">Mover usuários de filial que estão no SBA herdado para outro pool de Front-End.</span><span class="sxs-lookup"><span data-stu-id="f2cef-116">Move branch users homed on the legacy SBA to another Front End pool.</span></span>
    
2. <span data-ttu-id="f2cef-117">Remova o SBA da topologia herdado para desconectar o pool de Front-End existente como registrador de backup.</span><span class="sxs-lookup"><span data-stu-id="f2cef-117">Remove SBA from the legacy topology to disconnect the existing Front End pool as a backup registrar.</span></span>
    
3. <span data-ttu-id="f2cef-118">Adicione o SBA à topologia do Skype for Business Server 2019 e configure esse novo pool de Front-End como registrador de backup.</span><span class="sxs-lookup"><span data-stu-id="f2cef-118">Add SBA to the Skype for Business Server 2019 topology and configure this new Front End pool as the backup registrar.</span></span> 
    
4. <span data-ttu-id="f2cef-119">Mova os usuários de filial para o novo SBA do Skype for Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="f2cef-119">Move the branch users to the new Skype for Business Server 2019 SBA.</span></span>
    
### <a name="add-legacy-sba-branch-site-to-your-topology"></a><span data-ttu-id="f2cef-120">Adicionar site de filial SBA herddo à sua topologia</span><span class="sxs-lookup"><span data-stu-id="f2cef-120">Add legacy SBA branch site to your topology</span></span>

1. <span data-ttu-id="f2cef-121">Abra o **Construtor de Topologia**.</span><span class="sxs-lookup"><span data-stu-id="f2cef-121">Open **Topology Builder**.</span></span>
    
2. <span data-ttu-id="f2cef-122">No painel esquerdo, clique com o botão direito do mouse em **Sites de Filial** e clique em **Novo Site de Filial.**</span><span class="sxs-lookup"><span data-stu-id="f2cef-122">In the left pane, right-click **Branch sites**, and then click **New Branch Site**.</span></span>
    
3. <span data-ttu-id="f2cef-123">Na caixa de diálogo **Definir Novo Site de Filial**, clique em **Nome** e digite o nome do site de filial.</span><span class="sxs-lookup"><span data-stu-id="f2cef-123">In the **Define New Branch Site** dialog box, click **Name**, and then type the name of the branch site.</span></span>
    
4. <span data-ttu-id="f2cef-124">(Opcional) Clique em **Descrição** e digite uma descrição significativa para o site de filial.</span><span class="sxs-lookup"><span data-stu-id="f2cef-124">(Optional) Click **Description**, and then type a meaningful description for the branch site.</span></span>
    
5. <span data-ttu-id="f2cef-125">Clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="f2cef-125">Click **Next**.</span></span>
    
6. <span data-ttu-id="f2cef-126">(Opcional) Na próxima caixa de diálogo **Definir Novo Site de Filial**, execute uma das seguintes ações:</span><span class="sxs-lookup"><span data-stu-id="f2cef-126">(Optional) In the next **Define New Branch Site** dialog box, do any of the following:</span></span> 
    
    1. <span data-ttu-id="f2cef-127">Clique em **Cidade** e digite o nome da cidade na qual o site de filial está localizado.</span><span class="sxs-lookup"><span data-stu-id="f2cef-127">Click **City**, and then type the name of the city in which the branch site is located.</span></span>
    
    2. <span data-ttu-id="f2cef-128">Clique em **Estado/Região** e digite o nome do estado ou região na qual o site de filial está localizado.</span><span class="sxs-lookup"><span data-stu-id="f2cef-128">Click **State/Region**, and then type the name of the state or region in which the branch site is located.</span></span>
    
    3. <span data-ttu-id="f2cef-129">Clique em **Código do País** e digite o código de chamada de dois dígitos para o país/região no qual o site de filial está localizado.</span><span class="sxs-lookup"><span data-stu-id="f2cef-129">Click **Country Code**, and then type the two-digit calling code for the country/region in which the branch site is located.</span></span>
    
7. <span data-ttu-id="f2cef-130">Clique **em** Próximo e, em seguida, se você estiver usando um Aparelho de Filial Ou Servidor Desavivável neste site, certifique-se de limpar a caixa de seleção **Abrir** o Novo Assistente De Sobrevivência quando esse assistente fechar.</span><span class="sxs-lookup"><span data-stu-id="f2cef-130">Click **Next**, and then, if you are using a Survivable Branch Appliance or Server at this site, be sure to clear the **Open the New Survivable Wizard when this wizard closes** check box.</span></span> <span data-ttu-id="f2cef-131">Clique em **Concluir**.</span><span class="sxs-lookup"><span data-stu-id="f2cef-131">Click **Finish**.</span></span>
    
8. <span data-ttu-id="f2cef-132">Para associar o SBA herdados ao pool de Front-End do Skype for Business Server 2019:</span><span class="sxs-lookup"><span data-stu-id="f2cef-132">To associate the legacy SBA to the Skype for Business Server 2019 Front End pool:</span></span>
    
    1. <span data-ttu-id="f2cef-133">Expanda o local ramificado que foi criado.</span><span class="sxs-lookup"><span data-stu-id="f2cef-133">Expand the branch site that has been created.</span></span> 
    
    2. <span data-ttu-id="f2cef-134">Clique com o botão direito do mouse na versão herdada e clique em **Novo**.</span><span class="sxs-lookup"><span data-stu-id="f2cef-134">Right-click on legacy version, and then click **New**.</span></span>
    
    3. <span data-ttu-id="f2cef-135">Clique **em Aparelho de Filial Suportável.**</span><span class="sxs-lookup"><span data-stu-id="f2cef-135">Click **Survivable Branch Appliance**.</span></span>
    
9. <span data-ttu-id="f2cef-136">Siga as instruções no assistente que abrir.</span><span class="sxs-lookup"><span data-stu-id="f2cef-136">Follow the directions in the wizard that opens.</span></span> <span data-ttu-id="f2cef-137">Para obter informações sobre itens do assistente, consulte</span><span class="sxs-lookup"><span data-stu-id="f2cef-137">For information about wizard items, see</span></span>    
   <!-- [Define a Survivable Branch Appliance or Server in Lync 2013](/previous-versions/office/lync-server-2013/lync-server-2013-define-a-survivable-branch-appliance-or-server). -->
   <!-- The above link points to un-rebranded 2013 content we will need to discuss rebrand or bring forward -->
    
    > [!NOTE]
    > <span data-ttu-id="f2cef-138">Um Aparelho de Filial Desavivável só pode ser associado a um Armazenamento de Monitoramento.</span><span class="sxs-lookup"><span data-stu-id="f2cef-138">A Survivable Branch Appliance can only be associated with a Monitoring Store.</span></span> 
  
10. <span data-ttu-id="f2cef-139">Se você não estiver usando um Aparelho de Filial Persistente ou Servidor nesse site, desmarque a caixa de seleção **Abrir o Novo Assistente Persistente quando este assistente fechar** e clique em **Concluir**.</span><span class="sxs-lookup"><span data-stu-id="f2cef-139">If you are not using a Survivable Branch Appliance or Server at this site, clear the **Open the New Survivable Wizard when this wizard closes** check box, and then click **Finish**.</span></span>
    
11. <span data-ttu-id="f2cef-140">Repita as etapas anteriores para cada site de filial que você deseja adicionar à topologia.</span><span class="sxs-lookup"><span data-stu-id="f2cef-140">Repeat the previous steps for each branch site you want to add to the topology.</span></span>
