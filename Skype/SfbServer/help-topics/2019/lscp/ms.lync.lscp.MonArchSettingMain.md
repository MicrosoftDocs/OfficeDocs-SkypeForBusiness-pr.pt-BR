---
title: Configuração de Arquivamento
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
- ms.lync.lscp.MonArchSettingMain
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
localization_priority: Normal
ms.assetid: 9c2fd164-a9b8-40e6-a1c4-423a7fe34aba
ROBOTS: NOINDEX, NOFOLLOW
description: 'Use as configurações de Arquivamento para controlar as opções de arquivamento para a implantação do Skype for Business Server, incluindo a habilitação e desabilitação das seguintes opções:'
ms.openlocfilehash: 56ab256d79a22ce8b08efc9ad135d4c8309ff5d4
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49833591"
---
# <a name="archiving-configuration"></a><span data-ttu-id="0f3d1-103">Configuração de Arquivamento</span><span class="sxs-lookup"><span data-stu-id="0f3d1-103">Archiving Configuration</span></span>
 
<span data-ttu-id="0f3d1-104">Use as configurações de Arquivamento para controlar as opções de arquivamento para a implantação do Skype for Business Server, incluindo a habilitação e desabilitação das seguintes opções:</span><span class="sxs-lookup"><span data-stu-id="0f3d1-104">You use Archiving configurations to control archiving options for your Skype for Business Server deployment, including enabling and disabling the following options:</span></span>
  
- <span data-ttu-id="0f3d1-105">Bloqueio de mensagens instantâneas (IM) ou sessões de conferência se o arquivamento falhar</span><span class="sxs-lookup"><span data-stu-id="0f3d1-105">Blocking of instant messaging (IM) or conferencing sessions if archiving fails</span></span>
    
- <span data-ttu-id="0f3d1-106">Integração com o armazenamento do Exchange, para usuários que estão no Exchange</span><span class="sxs-lookup"><span data-stu-id="0f3d1-106">Integration with Exchange storage, for users homed on Exchange</span></span>
    
- <span data-ttu-id="0f3d1-107">Limpeza de dados arquivados</span><span class="sxs-lookup"><span data-stu-id="0f3d1-107">Purging of archived data</span></span>
    
<span data-ttu-id="0f3d1-108">As configurações de arquivamento incluem a configuração global e, como opção, uma ou mais configurações de Arquivamento de site e de pool:</span><span class="sxs-lookup"><span data-stu-id="0f3d1-108">Archiving configurations include the global configuration and, optionally, one or more site and pool Archiving configurations:</span></span>
  
- <span data-ttu-id="0f3d1-109">**Configuração global** A configuração global é criada por padrão em todas as implantações do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="0f3d1-109">**Global configuration** The global configuration is created by default in all Skype for Business Server deployments.</span></span> <span data-ttu-id="0f3d1-110">É possível editar a configuração global, mas não é possível excluir essa configuração de Arquivamento.</span><span class="sxs-lookup"><span data-stu-id="0f3d1-110">You edit the global configuration, but you cannot delete this Archiving configuration.</span></span> <span data-ttu-id="0f3d1-111">Se você tentar exclui-la, todas as opções serão redefinidas para o padrão.</span><span class="sxs-lookup"><span data-stu-id="0f3d1-111">If you try to delete it, all options are reset to the defaults.</span></span>
    
- <span data-ttu-id="0f3d1-112">**Configuração do site (opcional)** Você pode especificar uma ou mais configurações de Arquivamento de site, sendo possível configurar cada uma delas para controlar as opções de arquivamento de um site específico.</span><span class="sxs-lookup"><span data-stu-id="0f3d1-112">**Site configuration (optional)** You can specify one or more site Archiving configurations, each of which you can configure to control archiving options for a specific site.</span></span> <span data-ttu-id="0f3d1-113">Uma configuração de site substitui a configuração global, mas somente para os sites especificados nas configurações de site de Arquivamento.</span><span class="sxs-lookup"><span data-stu-id="0f3d1-113">A site configuration overrides the global configuration, but only for the sites specified in the Archiving site configurations.</span></span> <span data-ttu-id="0f3d1-114">É possível editar ou excluir as configurações de site.</span><span class="sxs-lookup"><span data-stu-id="0f3d1-114">You can edit or delete site configurations.</span></span>
    
- <span data-ttu-id="0f3d1-115">**Configuração de pool (opcional)** Você pode especificar uma ou mais configurações de Arquivamento de pool para controlar as opções de arquivamento para um pool específico.</span><span class="sxs-lookup"><span data-stu-id="0f3d1-115">**Pool configuration (optional)** You can specify one or more pool Archiving configuration, to control archiving options for a specific pool.</span></span> <span data-ttu-id="0f3d1-116">Uma configuração de pool substitui a configuração global e a configuração de site, mas somente para os pools especificados nas configurações de pool de Arquivamento.</span><span class="sxs-lookup"><span data-stu-id="0f3d1-116">A pool configuration overrides the global configuration and site configuration, but only for the pools specified in Archiving pool configurations.</span></span> <span data-ttu-id="0f3d1-117">É possível editar ou excluir as configurações de pool.</span><span class="sxs-lookup"><span data-stu-id="0f3d1-117">You can edit or delete pool configurations.</span></span>
    
> [!NOTE]
> <span data-ttu-id="0f3d1-118">As configurações de arquivamento se aplicam aos usuários que estão no Skype for Business Server e, se você usar o Exchange para armazenar dados de arquivamento no Microsoft Exchange, aos usuários que estão no Exchange, mas são implementados de maneira ligeiramente diferente para usuários que estão no Exchange.</span><span class="sxs-lookup"><span data-stu-id="0f3d1-118">Archiving configurations apply to users homed on Skype for Business Server and, if you use Exchange to store archiving data in Microsoft Exchange, to users homed on Exchange but are implemented slightly differently for users homed on Exchange.</span></span> <span data-ttu-id="0f3d1-119">As diferenças são descritas na próxima seção.</span><span class="sxs-lookup"><span data-stu-id="0f3d1-119">The differences are described in the next section.</span></span> 
  
<span data-ttu-id="0f3d1-p105">A página **Configuração de Arquivamento** lista cada política de Arquivamento configurada para sua implantação. Também mostra o nome da política, o escopo (global, site ou pool), e quais opções de arquivamento estão habilitadas para cada configuração de Arquivamento. Na página **Configuração de Arquivamento**, você tem as seguintes opções:</span><span class="sxs-lookup"><span data-stu-id="0f3d1-p105">The **Archiving Configuration** page lists each Archiving policy that is configured for your deployment. It also shows the policy name, scope (global, site, or pool), and which archiving options are enabled for each Archiving configuration. From the **Archiving Configuration** page, you have the following options:</span></span>
- <span data-ttu-id="0f3d1-123">**Novo** Você pode adicionar uma ou mais de cada uma das seguintes configurações de Arquivamento opcionais.</span><span class="sxs-lookup"><span data-stu-id="0f3d1-123">**New** You can add one or more of each of the following optional Archiving configurations.</span></span>
    
  - <span data-ttu-id="0f3d1-124">Configuração de site</span><span class="sxs-lookup"><span data-stu-id="0f3d1-124">Site configuration</span></span>
    
  - <span data-ttu-id="0f3d1-125">Configuração de pool</span><span class="sxs-lookup"><span data-stu-id="0f3d1-125">Pool configuration</span></span>
    
- <span data-ttu-id="0f3d1-126">**Editar** Você pode alterar as opções de qualquer uma das configurações de Arquivamento listadas na página.</span><span class="sxs-lookup"><span data-stu-id="0f3d1-126">**Edit** You can change the options of any of the Archiving configurations listed on the page.</span></span> <span data-ttu-id="0f3d1-127">Com essa opção, é possível fazer o seguinte:</span><span class="sxs-lookup"><span data-stu-id="0f3d1-127">Using this option, you can do the following:</span></span>
    
  - <span data-ttu-id="0f3d1-128">**Mostrar detalhes** Essa opção abre uma caixa de diálogo na qual é possível alterar as opções de arquivamento para a configuração de Arquivamento selecionada.</span><span class="sxs-lookup"><span data-stu-id="0f3d1-128">**Show details** This option opens a dialog box in which you can change the archiving options for the selected Archiving configuration.</span></span> <span data-ttu-id="0f3d1-129">É possível mostrar apenas os detalhes de uma configuração de Arquivamento por vez.</span><span class="sxs-lookup"><span data-stu-id="0f3d1-129">You can only show details for one Archiving configuration at a time.</span></span>
    
  - <span data-ttu-id="0f3d1-130">**Selecionar tudo** Essa opção seleciona todas as configurações de Arquivamento na lista.</span><span class="sxs-lookup"><span data-stu-id="0f3d1-130">**Select all** This option selects all Archiving configurations in the list.</span></span>
    
  - <span data-ttu-id="0f3d1-131">**Excluir** Essa opção exclui todas as configurações de Arquivamento selecionadas.</span><span class="sxs-lookup"><span data-stu-id="0f3d1-131">**Delete** This option deletes all selected Archiving configurations.</span></span>
    
- <span data-ttu-id="0f3d1-132">**Ação** Você pode usar essa opção para habilitar ou desabilitar rapidamente o arquivamento de sessões de IM ou sessões de webconferência em qualquer configuração listada na página, em vez de editar a configuração.</span><span class="sxs-lookup"><span data-stu-id="0f3d1-132">**Action** You can use this option to quickly enable or disable archiving of IM sessions or web conferencing sessions in any configuration listed on the page, instead of editing the configuration.</span></span> <span data-ttu-id="0f3d1-133">As opções disponíveis em **Ação** dependem de qual opção está especificada atualmente na configuração de Arquivamento.</span><span class="sxs-lookup"><span data-stu-id="0f3d1-133">The options available under **Action** depend on what option is currently specified in the Archiving configuration.</span></span> <span data-ttu-id="0f3d1-134">Todas as opções estão disponíveis, exceto pela opção atualmente em vigor para a configuração de Arquivamento.</span><span class="sxs-lookup"><span data-stu-id="0f3d1-134">All options are available, except the option currently in effect for the Archiving configuration.</span></span> <span data-ttu-id="0f3d1-135">As opções incluem o seguinte:</span><span class="sxs-lookup"><span data-stu-id="0f3d1-135">Options include the following:</span></span>
    
  - <span data-ttu-id="0f3d1-136">**Arquivar sessões de IM**</span><span class="sxs-lookup"><span data-stu-id="0f3d1-136">**Archive IM sessions**</span></span>
    
  - <span data-ttu-id="0f3d1-137">**Arquivar sessões de IM e webconferências**</span><span class="sxs-lookup"><span data-stu-id="0f3d1-137">**Archive IM and web conferencing sessions**</span></span>
    
  - <span data-ttu-id="0f3d1-138">**Desabilitar arquivamento**</span><span class="sxs-lookup"><span data-stu-id="0f3d1-138">**Disable archiving**</span></span>
    
- <span data-ttu-id="0f3d1-139">**Atualizar** Você pode atualizar a **página Configuração de** Arquivamento para verificar o status das opções de todas as configurações de Arquivamento.</span><span class="sxs-lookup"><span data-stu-id="0f3d1-139">**Refresh** You can refresh the **Archiving Configuration** page to verify the status of the options of all Archiving configurations.</span></span>
    
<span data-ttu-id="0f3d1-140">Para obter detalhes sobre os recursos de Arquivamento, incluindo a integração com o Exchange, consulte [Plan for archiving in Skype for Business Server](../../../plan-your-deployment/archiving/archiving.md), Deploy [archiving for Skype for Business Server](../../../deploy/deploy-archiving/deploy-archiving.md), and Manage [archiving in Skype for Business Server](../../../manage/archiving/archiving.md).</span><span class="sxs-lookup"><span data-stu-id="0f3d1-140">For details about the Archiving feature and capabilities, including Exchange integration, see [Plan for archiving in Skype for Business Server](../../../plan-your-deployment/archiving/archiving.md), [Deploy archiving for Skype for Business Server](../../../deploy/deploy-archiving/deploy-archiving.md), and [Manage archiving in Skype for Business Server](../../../manage/archiving/archiving.md).</span></span>

