---
title: Política de Arquivamento
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/27/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.lscp.MonArchPolicyMain
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 9b69f1fa-8f3b-450e-aa89-91fd462f198d
description: 'Você usa políticas de arquivamento para habilitar e desabilitar o arquivamento para usuários hospedados no Skype for Business Server. Em cada política de Arquivamento, é possível habilitar ou desabilitar o arquivamento para uma das seguintes opções, ou para ambas:'
ms.openlocfilehash: 230b27a0d87b553f64b209e5aa3d464e88ae370a
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41823184"
---
# <a name="archiving-policy"></a><span data-ttu-id="6057d-104">Política de Arquivamento</span><span class="sxs-lookup"><span data-stu-id="6057d-104">Archiving Policy</span></span>
 
<span data-ttu-id="6057d-105">Você usa políticas de arquivamento para habilitar e desabilitar o arquivamento para usuários hospedados no Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="6057d-105">You use Archiving policies to enable and disable archiving for users homed on Skype for Business Server.</span></span> <span data-ttu-id="6057d-106">Em cada política de Arquivamento, é possível habilitar ou desabilitar o arquivamento para uma das seguintes opções, ou para ambas:</span><span class="sxs-lookup"><span data-stu-id="6057d-106">In each Archiving policy, you can enable or disable archiving for either or both of the following:</span></span>
  
- <span data-ttu-id="6057d-107">Comunicações internas</span><span class="sxs-lookup"><span data-stu-id="6057d-107">Internal communications</span></span>
    
- <span data-ttu-id="6057d-108">Comunicações externas (comunicações que incluem pelo menos um usuário fora de sua rede interna)</span><span class="sxs-lookup"><span data-stu-id="6057d-108">External communications (communications that include at least one user outside your internal network)</span></span>
    
<span data-ttu-id="6057d-109">As políticas de arquivamento incluem a política global, e, como opção, uma ou mais políticas de Arquivamento de site e de usuário:</span><span class="sxs-lookup"><span data-stu-id="6057d-109">Archiving policies include the global policy, and, optionally, one or more site and user Archiving policies:</span></span>
  
- <span data-ttu-id="6057d-110">**Política global** A política global é criada por padrão em todas as implantações.</span><span class="sxs-lookup"><span data-stu-id="6057d-110">**Global policy** The global policy is created by default in all deployments.</span></span> <span data-ttu-id="6057d-111">É possível editar a política global, mas não é possível excluir essa política.</span><span class="sxs-lookup"><span data-stu-id="6057d-111">You can edit the global policy, but you cannot delete this policy.</span></span> <span data-ttu-id="6057d-112">Se você tentar excluí-la, todas as opções serão redefinidas para o padrão.</span><span class="sxs-lookup"><span data-stu-id="6057d-112">If you try to delete it, all options are reset to the defaults.</span></span>
    
- <span data-ttu-id="6057d-113">**Política do site (opcional)** Você pode especificar uma ou mais políticas de arquivamento de site, cada uma que pode ser configurada para habilitar e desabilitar o arquivamento de comunicações internas ou externas para um único site.</span><span class="sxs-lookup"><span data-stu-id="6057d-113">**Site policy (optional)** You can specify one or more site Archiving policies, each of which you can configure to enable and disable archiving of internal or external communications for a single site.</span></span> <span data-ttu-id="6057d-114">Uma política de site substitui a política global, mas somente para os sites especificados em suas políticas de site de Arquivamento.</span><span class="sxs-lookup"><span data-stu-id="6057d-114">A site policy overrides the global policy, but only for the sites specified in your Archiving site policies.</span></span> <span data-ttu-id="6057d-115">É possível editar ou excluir as políticas de site.</span><span class="sxs-lookup"><span data-stu-id="6057d-115">You can edit or delete site policies.</span></span>
    
- <span data-ttu-id="6057d-116">**Política de usuário (opcional)** Você pode especificar uma ou mais políticas de arquivamento do usuário, cada qual você pode configurar para habilitar e desabilitar o arquivamento de comunicações internas ou externas para um usuário ou grupo de usuários específico.</span><span class="sxs-lookup"><span data-stu-id="6057d-116">**User policy (optional)** You can specify one or more user Archiving policies, each of which you can configure to enable and disable archiving of internal or external communications for a specific user or user group.</span></span> <span data-ttu-id="6057d-117">Uma política de usuário substitui a política global e as políticas de site, mas somente para os usuários e grupos de usuário aos quais você atribui políticas de Arquivamento no nível do usuário.</span><span class="sxs-lookup"><span data-stu-id="6057d-117">A user policy overrides the global policy and site policies, but only for the users and user groups to whom you assign user-level Archiving policies.</span></span> <span data-ttu-id="6057d-118">É possível editar ou excluir as políticas de usuário.</span><span class="sxs-lookup"><span data-stu-id="6057d-118">You can edit or delete user policies.</span></span>
    
> [!NOTE]
> <span data-ttu-id="6057d-119">As políticas de arquivamento aplicam-se somente aos usuários hospedados no Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="6057d-119">Archiving policies apply only to users homed on Skype for Business Server.</span></span> <span data-ttu-id="6057d-120">Se você usa a integração do Exchange para armazenar dados de arquivamento no Microsoft Exchange, as políticas do Exchange 2013 controlam o arquivamento para usuários hospedados no Exchange 2013.</span><span class="sxs-lookup"><span data-stu-id="6057d-120">If you use Exchange integration to store archiving data in Microsoft Exchange, then Exchange 2013 policies control archiving for users homed on Exchange 2013.</span></span> <span data-ttu-id="6057d-121">Para habilitar o arquivamento para esses usuários, a caixa de correio do usuário deve ser colocada no bloqueio in-loco.</span><span class="sxs-lookup"><span data-stu-id="6057d-121">To enable archiving for those users, the user's mailbox must be placed on In-Place Hold.</span></span> 
  
<span data-ttu-id="6057d-p107">A página  **Política de Arquivamento** lista cada política de Arquivamento configurada para sua implantação. Também mostra o nome da política, o escopo (global, site ou usuário), e quais opções de arquivamento estão habilitadas para cada política de Arquivamento. Na página  **Política de Arquivamento**, você tem as seguintes opções:</span><span class="sxs-lookup"><span data-stu-id="6057d-p107">The **Archiving Policy** page lists each Archiving policy that is configured for your deployment. It also shows the policy name, scope (global, site, or user), and which archiving options are enabled for each Archiving policy. From the **Archiving Policy** page, you have the following options:</span></span>
- <span data-ttu-id="6057d-125">**Novo** Você pode adicionar uma ou mais das seguintes políticas de arquivamento opcionais:</span><span class="sxs-lookup"><span data-stu-id="6057d-125">**New** You can add one or more of each of the following optional Archiving policies:</span></span>
    
  - <span data-ttu-id="6057d-126">Política de site</span><span class="sxs-lookup"><span data-stu-id="6057d-126">Site policy</span></span>
    
  - <span data-ttu-id="6057d-127">Política de usuário</span><span class="sxs-lookup"><span data-stu-id="6057d-127">User policy</span></span>
    
- <span data-ttu-id="6057d-128">**Editar** Você pode alterar as opções de qualquer uma das políticas de arquivamento listadas na página.</span><span class="sxs-lookup"><span data-stu-id="6057d-128">**Edit** You can change the options of any of the Archiving policies listed on the page.</span></span> <span data-ttu-id="6057d-129">Com essa opção, é possível fazer o seguinte:</span><span class="sxs-lookup"><span data-stu-id="6057d-129">Using this option, you can do the following:</span></span>
    
  - <span data-ttu-id="6057d-130">**Mostrar detalhes** Essa opção abre uma caixa de diálogo na qual é possível alterar as opções de arquivamento de uma política de Arquivamento.</span><span class="sxs-lookup"><span data-stu-id="6057d-130">**Show details** This option opens a dialog box in which you can change the archiving options for an Archiving policy.</span></span>
    
  - <span data-ttu-id="6057d-131">**Selecionar tudo**   Essa opção seleciona todas as políticas de Arquivamento na lista.</span><span class="sxs-lookup"><span data-stu-id="6057d-131">**Select all** This option selects all Archiving policies in the list.</span></span>
    
  - <span data-ttu-id="6057d-132">**Excluir**   Essa opção exclui todas as políticas de Arquivamento selecionadas.</span><span class="sxs-lookup"><span data-stu-id="6057d-132">**Delete** This option deletes all selected Archiving policies.</span></span>
    
- <span data-ttu-id="6057d-133">**Ação** Você pode usar essa opção para habilitar ou desabilitar rapidamente o arquivamento de comunicações internas ou externas em qualquer política listada na página, em vez de editar a política.</span><span class="sxs-lookup"><span data-stu-id="6057d-133">**Action** You can use this option to quickly enable or disable archiving of internal or external communications in any policy listed on the page, instead of editing the policy.</span></span> <span data-ttu-id="6057d-134">As opções disponíveis em **Ação** dependem de qual opção está especificada atualmente na política de Arquivamento.</span><span class="sxs-lookup"><span data-stu-id="6057d-134">The options available under **Action** depend on what option is currently specified in the Archiving policy.</span></span> <span data-ttu-id="6057d-135">Todas as opções estão disponíveis, exceto pela opção atualmente em vigor para a política de Arquivamento.</span><span class="sxs-lookup"><span data-stu-id="6057d-135">All options are available, except the option currently in effect for the Archiving policy.</span></span> <span data-ttu-id="6057d-136">As opções incluem o seguinte:</span><span class="sxs-lookup"><span data-stu-id="6057d-136">Options include the following:</span></span>
    
  - <span data-ttu-id="6057d-137">**Habilitar arquivamento de comunicações internas**</span><span class="sxs-lookup"><span data-stu-id="6057d-137">**Enable Archiving of internal communications**</span></span>
    
  - <span data-ttu-id="6057d-138">**Desabilitar arquivamento de comunicações internas**</span><span class="sxs-lookup"><span data-stu-id="6057d-138">**Disable Archiving of internal communications**</span></span>
    
  - <span data-ttu-id="6057d-139">**Habilitar arquivamento de comunicações externas**</span><span class="sxs-lookup"><span data-stu-id="6057d-139">**Enable Archiving of external communications**</span></span>
    
  - <span data-ttu-id="6057d-140">**Desabilitar arquivamento de comunicações externas**</span><span class="sxs-lookup"><span data-stu-id="6057d-140">**Disable Archiving of external communications**</span></span>
    
- <span data-ttu-id="6057d-141">**Atualização** Você pode atualizar a página de **política de arquivamento** para verificar o status das opções de todas as políticas de arquivamento.</span><span class="sxs-lookup"><span data-stu-id="6057d-141">**Refresh** You can refresh the **Archiving Policy** page to verify the status of the options of all Archiving policies.</span></span>
    
<span data-ttu-id="6057d-142">Para obter detalhes sobre o recurso de arquivamento e os recursos, incluindo a integração com o Exchange, consulte [planejar o arquivamento no Skype for Business server 2015](../../plan-your-deployment/archiving/archiving.md), [implantar o arquivamento para o Skype for Business Server 2015](../../deploy/deploy-archiving/deploy-archiving.md)e [gerenciar o arquivamento no Skype for Business Server 2015](../../manage/archiving/archiving.md).</span><span class="sxs-lookup"><span data-stu-id="6057d-142">For details about the Archiving feature and capabilities, including Exchange integration, see [Plan for archiving in Skype for Business Server 2015](../../plan-your-deployment/archiving/archiving.md), [Deploy archiving for Skype for Business Server 2015](../../deploy/deploy-archiving/deploy-archiving.md), and [Manage archiving in Skype for Business Server 2015](../../manage/archiving/archiving.md).</span></span>

