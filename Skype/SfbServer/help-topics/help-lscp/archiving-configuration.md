---
title: Configuração de Arquivamento
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/27/2015
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.MonArchSettingMain
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 9c2fd164-a9b8-40e6-a1c4-423a7fe34aba
description: 'Use as configurações de arquivamento para controlar as opções de arquivamento para a implantação do Skype for Business Server, incluindo a ativação e a desativação das seguintes opções:'
ms.openlocfilehash: 8f3ed4289d68359cb8eb0d4cb0bfc3a303c53dd3
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34299845"
---
# <a name="archiving-configuration"></a><span data-ttu-id="3caef-103">Configuração de Arquivamento</span><span class="sxs-lookup"><span data-stu-id="3caef-103">Archiving Configuration</span></span>
 
<span data-ttu-id="3caef-104">Use as configurações de arquivamento para controlar as opções de arquivamento para a implantação do Skype for Business Server, incluindo a ativação e a desativação das seguintes opções:</span><span class="sxs-lookup"><span data-stu-id="3caef-104">You use Archiving configurations to control archiving options for your Skype for Business Server deployment, including enabling and disabling the following options:</span></span>
  
- <span data-ttu-id="3caef-105">Bloqueio de mensagens instantâneas (IM) ou sessões de conferência se o arquivamento falhar</span><span class="sxs-lookup"><span data-stu-id="3caef-105">Blocking of instant messaging (IM) or conferencing sessions if archiving fails</span></span>
    
- <span data-ttu-id="3caef-106">Integração com o armazenamento do Exchange 2013 para usuários hospedados no Exchange 2013</span><span class="sxs-lookup"><span data-stu-id="3caef-106">Integration with Exchange 2013 storage, for users homed on Exchange 2013</span></span>
    
- <span data-ttu-id="3caef-107">Limpeza de dados arquivados</span><span class="sxs-lookup"><span data-stu-id="3caef-107">Purging of archived data</span></span>
    
<span data-ttu-id="3caef-108">As configurações de arquivamento incluem a configuração global e, como opção, uma ou mais configurações de Arquivamento de site e de pool:</span><span class="sxs-lookup"><span data-stu-id="3caef-108">Archiving configurations include the global configuration and, optionally, one or more site and pool Archiving configurations:</span></span>
  
- <span data-ttu-id="3caef-109">**Configuração global** A configuração global é criada por padrão em todas as implantações do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="3caef-109">**Global configuration** The global configuration is created by default in all Skype for Business Server deployments.</span></span> <span data-ttu-id="3caef-110">É possível editar a configuração global, mas não é possível excluir essa configuração de Arquivamento.</span><span class="sxs-lookup"><span data-stu-id="3caef-110">You edit the global configuration, but you cannot delete this Archiving configuration.</span></span> <span data-ttu-id="3caef-111">Se você tentar excluí-la, todas as opções serão redefinidas para o padrão.</span><span class="sxs-lookup"><span data-stu-id="3caef-111">If you try to delete it, all options are reset to the defaults.</span></span>
    
- <span data-ttu-id="3caef-112">**Configuração de site (opcional)** Você pode especificar uma ou mais configurações de arquivamento de site, cada uma que pode ser configurada para controlar as opções de arquivamento de um site específico.</span><span class="sxs-lookup"><span data-stu-id="3caef-112">**Site configuration (optional)** You can specify one or more site Archiving configurations, each of which you can configure to control archiving options for a specific site.</span></span> <span data-ttu-id="3caef-113">Uma configuração de site substitui a configuração global, mas somente para os sites especificados nas configurações de site de Arquivamento.</span><span class="sxs-lookup"><span data-stu-id="3caef-113">A site configuration overrides the global configuration, but only for the sites specified in the Archiving site configurations.</span></span> <span data-ttu-id="3caef-114">É possível editar ou excluir as configurações de site.</span><span class="sxs-lookup"><span data-stu-id="3caef-114">You can edit or delete site configurations.</span></span>
    
- <span data-ttu-id="3caef-115">**Configuração de pool (opcional)** Você pode especificar uma ou mais configurações de arquivamento de pool para controlar as opções de arquivamento de um pool específico.</span><span class="sxs-lookup"><span data-stu-id="3caef-115">**Pool configuration (optional)** You can specify one or more pool Archiving configuration, to control archiving options for a specific pool.</span></span> <span data-ttu-id="3caef-116">Uma configuração de pool substitui a configuração global e a configuração de site, mas somente para os pools especificados nas configurações de pool de Arquivamento.</span><span class="sxs-lookup"><span data-stu-id="3caef-116">A pool configuration overrides the global configuration and site configuration, but only for the pools specified in Archiving pool configurations.</span></span> <span data-ttu-id="3caef-117">É possível editar ou excluir as configurações de pool.</span><span class="sxs-lookup"><span data-stu-id="3caef-117">You can edit or delete pool configurations.</span></span>
    
> [!NOTE]
> <span data-ttu-id="3caef-118">As configurações de arquivamento aplicam-se aos usuários hospedados no Skype for Business Server e, se você usar o Exchange para armazenar dados de arquivamento no Microsoft Exchange, para os usuários hospedados no Exchange 2013, mas serão implementadas de forma ligeiramente diferente para os usuários hospedados no Exchange 2013.</span><span class="sxs-lookup"><span data-stu-id="3caef-118">Archiving configurations apply to users homed on Skype for Business Server and, if you use Exchange to store archiving data in Microsoft Exchange, to users homed on Exchange 2013 but are implemented slightly differently for users homed on Exchange 2013.</span></span> <span data-ttu-id="3caef-119">As diferenças são descritas na próxima seção.</span><span class="sxs-lookup"><span data-stu-id="3caef-119">The differences are described in the next section.</span></span> 
  
<span data-ttu-id="3caef-p105">A página **Configuração de Arquivamento** lista cada política de Arquivamento configurada para sua implantação. Também mostra o nome da política, o escopo (global, site ou pool), e quais opções de arquivamento estão habilitadas para cada configuração de Arquivamento. Na página  **Configuração de Arquivamento**, você tem as seguintes opções:</span><span class="sxs-lookup"><span data-stu-id="3caef-p105">The **Archiving Configuration** page lists each Archiving policy that is configured for your deployment. It also shows the policy name, scope (global, site, or pool), and which archiving options are enabled for each Archiving configuration. From the **Archiving Configuration** page, you have the following options:</span></span>
- <span data-ttu-id="3caef-123">**Novo** Você pode adicionar uma ou mais de cada uma das configurações de arquivamento opcionais a seguir.</span><span class="sxs-lookup"><span data-stu-id="3caef-123">**New** You can add one or more of each of the following optional Archiving configurations.</span></span>
    
  - <span data-ttu-id="3caef-124">Configuração de site</span><span class="sxs-lookup"><span data-stu-id="3caef-124">Site configuration</span></span>
    
  - <span data-ttu-id="3caef-125">Configuração de pool</span><span class="sxs-lookup"><span data-stu-id="3caef-125">Pool configuration</span></span>
    
- <span data-ttu-id="3caef-126">**Editar** Você pode alterar as opções de qualquer uma das configurações de arquivamento listadas na página.</span><span class="sxs-lookup"><span data-stu-id="3caef-126">**Edit** You can change the options of any of the Archiving configurations listed on the page.</span></span> <span data-ttu-id="3caef-127">Com essa opção, é possível fazer o seguinte:</span><span class="sxs-lookup"><span data-stu-id="3caef-127">Using this option, you can do the following:</span></span>
    
  - <span data-ttu-id="3caef-128">**Mostrar detalhes** Essa opção abre uma caixa de diálogo na qual você pode alterar as opções de arquivamento para a configuração de arquivamento selecionada.</span><span class="sxs-lookup"><span data-stu-id="3caef-128">**Show details** This option opens a dialog box in which you can change the archiving options for the selected Archiving configuration.</span></span> <span data-ttu-id="3caef-129">É possível mostrar apenas os detalhes de uma configuração de Arquivamento por vez.</span><span class="sxs-lookup"><span data-stu-id="3caef-129">You can only show details for one Archiving configuration at a time.</span></span>
    
  - <span data-ttu-id="3caef-130">**Selecionar tudo** Essa opção seleciona todas as configurações de arquivamento na lista.</span><span class="sxs-lookup"><span data-stu-id="3caef-130">**Select all** This option selects all Archiving configurations in the list.</span></span>
    
  - <span data-ttu-id="3caef-131">**Excluir** Esta opção exclui todas as configurações de arquivamento selecionadas.</span><span class="sxs-lookup"><span data-stu-id="3caef-131">**Delete** This option deletes all selected Archiving configurations.</span></span>
    
- <span data-ttu-id="3caef-132">**Ação** Você pode usar essa opção para habilitar ou desabilitar rapidamente o arquivamento de sessões de mensagens instantâneas ou de sessões de Webconferência em qualquer configuração listada na página, em vez de editar a configuração.</span><span class="sxs-lookup"><span data-stu-id="3caef-132">**Action** You can use this option to quickly enable or disable archiving of IM sessions or web conferencing sessions in any configuration listed on the page, instead of editing the configuration.</span></span> <span data-ttu-id="3caef-133">As opções disponíveis em **Ação** dependem de qual opção está especificada atualmente na configuração de Arquivamento.</span><span class="sxs-lookup"><span data-stu-id="3caef-133">The options available under **Action** depend on what option is currently specified in the Archiving configuration.</span></span> <span data-ttu-id="3caef-134">Todas as opções estão disponíveis, exceto pela opção atualmente em vigor para a configuração de Arquivamento.</span><span class="sxs-lookup"><span data-stu-id="3caef-134">All options are available, except the option currently in effect for the Archiving configuration.</span></span> <span data-ttu-id="3caef-135">As opções incluem o seguinte:</span><span class="sxs-lookup"><span data-stu-id="3caef-135">Options include the following:</span></span>
    
  - <span data-ttu-id="3caef-136">**Arquivar sessões de IM**</span><span class="sxs-lookup"><span data-stu-id="3caef-136">**Archive IM sessions**</span></span>
    
  - <span data-ttu-id="3caef-137">**Arquivar sessões de IM e conferência da Web**</span><span class="sxs-lookup"><span data-stu-id="3caef-137">**Archive IM and web conferencing sessions**</span></span>
    
  - <span data-ttu-id="3caef-138">**Desativar arquivamento**</span><span class="sxs-lookup"><span data-stu-id="3caef-138">**Disable archiving**</span></span>
    
- <span data-ttu-id="3caef-139">**Atualização** Você pode atualizar a página de **configuração** de arquivamento para verificar o status das opções de todas as configurações de arquivamento.</span><span class="sxs-lookup"><span data-stu-id="3caef-139">**Refresh** You can refresh the **Archiving Configuration** page to verify the status of the options of all Archiving configurations.</span></span>
    
<span data-ttu-id="3caef-140">Para obter detalhes sobre o recurso de arquivamento e os recursos, incluindo a integração com o Exchange, consulte [planejar o arquivamento no Skype for Business server 2015](../../plan-your-deployment/archiving/archiving.md), [implantar o arquivamento para o Skype for Business Server 2015](../../deploy/deploy-archiving/deploy-archiving.md)e [gerenciar o arquivamento no Skype para Business Server 2015](../../manage/archiving/archiving.md).</span><span class="sxs-lookup"><span data-stu-id="3caef-140">For details about the Archiving feature and capabilities, including Exchange integration, see [Plan for archiving in Skype for Business Server 2015](../../plan-your-deployment/archiving/archiving.md), [Deploy archiving for Skype for Business Server 2015](../../deploy/deploy-archiving/deploy-archiving.md), and [Manage archiving in Skype for Business Server 2015](../../manage/archiving/archiving.md).</span></span>

