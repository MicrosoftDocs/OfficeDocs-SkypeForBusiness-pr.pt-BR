---
title: Configurar opções de arquivamento para o Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 2f534697-ac7f-45b7-8cdc-ba67f052223b
description: 'Resumo: Leia este tópico para saber como configurar as opções iniciais de arquivamento para o Skype for Business Server. Inicialmente, você configura as configurações de arquivamento ao implantar o arquivamento, mas pode alterar, adicionar e excluir configurações após a implantação.'
ms.openlocfilehash: 0a4803b821ee082a548b9f429b9596fd8019500f
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49815531"
---
# <a name="configure-archiving-options-for-skype-for-business-server"></a><span data-ttu-id="e54c0-104">Configurar opções de arquivamento para o Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="e54c0-104">Configure archiving options for Skype for Business Server</span></span>
 
<span data-ttu-id="e54c0-105">**Resumo:** Leia este tópico para saber como configurar as opções iniciais de arquivamento para o Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="e54c0-105">**Summary:** Read this topic to learn how to configure initial archiving options for Skype for Business Server.</span></span> <span data-ttu-id="e54c0-106">Inicialmente, você configura as configurações de arquivamento ao implantar o arquivamento, mas pode alterar, adicionar e excluir configurações após a implantação.</span><span class="sxs-lookup"><span data-stu-id="e54c0-106">You initially set up archiving configurations when you deploy archiving, but you can change, add, and delete configurations after deployment.</span></span>
  
<span data-ttu-id="e54c0-107">Para configurar as configurações iniciais de arquivamento, use o Painel de Controle do Skype for Business Server para especificar o seguinte:</span><span class="sxs-lookup"><span data-stu-id="e54c0-107">To configure initial archiving configurations, you use Skype for Business Server Control Panel to specify the following:</span></span>
  
- <span data-ttu-id="e54c0-108">Configuração de nível global criada por padrão ao implantar o Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="e54c0-108">Global-level configuration that is created by default when you deploy Skype for Business Server</span></span>
    
- <span data-ttu-id="e54c0-109">Configurações opcionais no nível do site que especificam como o arquivamento é implementado para um site específico</span><span class="sxs-lookup"><span data-stu-id="e54c0-109">Optional site-level configurations that specify how archiving is implemented for a specific site</span></span>
    
- <span data-ttu-id="e54c0-110">Configurações opcionais no nível do pool que especificam como o arquivamento é implementado para um pool específico</span><span class="sxs-lookup"><span data-stu-id="e54c0-110">Optional pool-level configurations that specify how archiving is implemented for a specific pool</span></span>
    
<span data-ttu-id="e54c0-111">Você precisará configurar opções para o seguinte:</span><span class="sxs-lookup"><span data-stu-id="e54c0-111">You will need to configure options for the following:</span></span>
  
- <span data-ttu-id="e54c0-112">Se o arquivamento será habilitado ou desabilitado</span><span class="sxs-lookup"><span data-stu-id="e54c0-112">Whether to enable or disable archiving</span></span>
    
- <span data-ttu-id="e54c0-113">Arquivar sessões de IM</span><span class="sxs-lookup"><span data-stu-id="e54c0-113">Whether to archive IM sessions</span></span>
    
- <span data-ttu-id="e54c0-114">Arquivar sessões de webconferência</span><span class="sxs-lookup"><span data-stu-id="e54c0-114">Whether to archive web conferencing sessions</span></span>
    
- <span data-ttu-id="e54c0-115">Se a atividade será ou não block quando o arquivamento não estiver disponível</span><span class="sxs-lookup"><span data-stu-id="e54c0-115">Whether to block activity when archiving is not available</span></span>
    
- <span data-ttu-id="e54c0-116">Usar ou não a integração com o Exchange</span><span class="sxs-lookup"><span data-stu-id="e54c0-116">Whether to use Exchange integration</span></span>
    
- <span data-ttu-id="e54c0-117">Como configurar a purging e a exportação de dados</span><span class="sxs-lookup"><span data-stu-id="e54c0-117">How to set up purging and exporting of data</span></span>
    
> [!NOTE]
> <span data-ttu-id="e54c0-118">Você deve especificar todas as opções apropriadas antes de ativar o arquivamento.</span><span class="sxs-lookup"><span data-stu-id="e54c0-118">You should specify all appropriate options before enabling archiving.</span></span> 
  
<span data-ttu-id="e54c0-119">Para obter detalhes sobre como as configurações de arquivamento são implementadas, incluindo quais opções você pode especificar e a hierarquia das configurações de arquivamento, consulte Plano para arquivamento no [Skype for Business Server.](../../plan-your-deployment/archiving/archiving.md)</span><span class="sxs-lookup"><span data-stu-id="e54c0-119">For details about how archiving configurations are implemented, including which options you can specify and the hierarchy of archiving configurations, see [Plan for archiving in Skype for Business Server](../../plan-your-deployment/archiving/archiving.md).</span></span> <span data-ttu-id="e54c0-120">Para obter detalhes sobre como gerenciar configurações após a implantação usando o Painel de Controle ou o Windows PowerShell, consulte Gerenciar opções de arquivamento no [Skype for Business Server.](../../manage/archiving/options.md)</span><span class="sxs-lookup"><span data-stu-id="e54c0-120">For details about how to manage configurations after deployment by using the Control Panel or by using Windows PowerShell, see [Manage archiving options in Skype for Business Server](../../manage/archiving/options.md).</span></span>
  
## <a name="configure-global-level-archiving-options"></a><span data-ttu-id="e54c0-121">Configurar opções de arquivamento de nível global</span><span class="sxs-lookup"><span data-stu-id="e54c0-121">Configure global level archiving options</span></span>

<span data-ttu-id="e54c0-122">Quando você adiciona arquivamento à sua topologia e publica a topologia, o Skype for Business Server cria uma configuração global para arquivamento.</span><span class="sxs-lookup"><span data-stu-id="e54c0-122">When you add archiving to your topology and publish the topology, Skype for Business Server creates a global configuration for archiving.</span></span> <span data-ttu-id="e54c0-123">Por padrão, nenhuma opção de arquivamento está habilitada na configuração global.</span><span class="sxs-lookup"><span data-stu-id="e54c0-123">By default, no archiving options are enabled in the global configuration.</span></span> <span data-ttu-id="e54c0-124">Os controles de configuração global que habilitam configurações para a implantação inteira, a não ser que você defina configurações de site ou pool que substituem a configuração global.</span><span class="sxs-lookup"><span data-stu-id="e54c0-124">The global configuration controls which options are enabled for your entire deployment, unless you set up site or pool configurations, which override the global configuration.</span></span>
  
<span data-ttu-id="e54c0-125">Para configurar opções de arquivamento no nível global:</span><span class="sxs-lookup"><span data-stu-id="e54c0-125">To configure archiving options at the global level:</span></span>
  
1. <span data-ttu-id="e54c0-126">A partir da conta do usuário que foi atribuída à função CsArchivingAdministrator ou CsAdministrator, faça o logon em qualquer computador na sua implantação interna.</span><span class="sxs-lookup"><span data-stu-id="e54c0-126">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="e54c0-127">Abra uma janela do navegador e insira a URL do Administrador para abrir o Painel de Controle do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="e54c0-127">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
    
3. <span data-ttu-id="e54c0-128">Na barra de navegação esquerda, clique em **Monitoramento e Arquivamento** e clique em **Configuração do Arquivamento**.</span><span class="sxs-lookup"><span data-stu-id="e54c0-128">In the left navigation bar, click **Monitoring and Archiving**, and then click **Archiving Configuration**.</span></span>
    
4. <span data-ttu-id="e54c0-129">Na página **Configuração de arquivamento**, clique em **Global**, **Editar** e **Mostrar detalhes**.</span><span class="sxs-lookup"><span data-stu-id="e54c0-129">On the **Archiving Configuration** page, click **Global**, click **Edit**, and then click **Show details**.</span></span>
    
5. <span data-ttu-id="e54c0-130">Em **Editar configuração de arquivamento - global**, na lista suspensa **Configuração de arquivamento**, selecione uma das seguintes opções de arquivamento:</span><span class="sxs-lookup"><span data-stu-id="e54c0-130">In **Edit Archiving Setting - Global**, in the **Archiving setting** drop-down list, select one of the following archiving options:</span></span>
    
   - <span data-ttu-id="e54c0-131">**Desativar arquivamento**</span><span class="sxs-lookup"><span data-stu-id="e54c0-131">**Disable archiving**</span></span>
    
   - <span data-ttu-id="e54c0-132">**Arquivar sessões de IM**</span><span class="sxs-lookup"><span data-stu-id="e54c0-132">**Archive IM sessions**</span></span>
    
   - <span data-ttu-id="e54c0-133">**Arquivar sessões de IM e conferência da Web**</span><span class="sxs-lookup"><span data-stu-id="e54c0-133">**Archive IM and web conferencing sessions**</span></span>
    
6. <span data-ttu-id="e54c0-134">Também na **página Editar Configuração de Arquivamento - Global,** faça o seguinte:</span><span class="sxs-lookup"><span data-stu-id="e54c0-134">Also on the **Edit Archiving Setting - Global** page, do the following:</span></span>
    
   - <span data-ttu-id="e54c0-135">Para bloquear a atividade quando o arquivamento não estiver disponível, marque a caixa de seleção **Bloquear sessões de mensagem instantânea ou conferência da Web se o arquivamento falhar**.</span><span class="sxs-lookup"><span data-stu-id="e54c0-135">To block activity when archiving is not available, select the **Block instant messaging (IM) or web conferencing sessions if archiving fails** check box.</span></span>
    
   - <span data-ttu-id="e54c0-136">Para usar o Microsoft Exchange Server para armazenar dados de arquivamento, clique na caixa de seleção de integração do **Microsoft Exchange.**</span><span class="sxs-lookup"><span data-stu-id="e54c0-136">To use Microsoft Exchange Server to store archiving data, click the **Microsoft Exchange integration** check box.</span></span>
    
   - <span data-ttu-id="e54c0-137">Para habilitar a exclusão de dados, marque a caixa de seleção **Habilitar exclusão dos dados de arquivamento** e faça um dos seguintes:</span><span class="sxs-lookup"><span data-stu-id="e54c0-137">To enable data purging, select the **Enable purging of archiving data** check box, and then do one of the following:</span></span>
    
   - <span data-ttu-id="e54c0-138">Para especificar a exclusão após um número específico de dias, clique em **Excluir dados de arquivamento exportados e dados de arquivamento armazenados após uma duração máxima (dias)** e especifique o número de dias.</span><span class="sxs-lookup"><span data-stu-id="e54c0-138">To specify purging after a specific number of days, click **Purge exported archiving data and stored archiving data after maximum duration (days)**, and then specify the number of days.</span></span>
    
   - <span data-ttu-id="e54c0-139">Para limitar a exclusão de dados de arquivamento que foram exportados, clique em **Excluir apenas dados de arquivamento exportados**.</span><span class="sxs-lookup"><span data-stu-id="e54c0-139">To limit purging to archiving data that has been exported, click **Purge exported archiving data only**.</span></span>
    
7. <span data-ttu-id="e54c0-140">Clique em **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="e54c0-140">Click **Commit**.</span></span>
    
## <a name="configure-site-level-archiving-options"></a><span data-ttu-id="e54c0-141">Configurar opções de arquivamento no nível do site</span><span class="sxs-lookup"><span data-stu-id="e54c0-141">Configure site level archiving options</span></span>

<span data-ttu-id="e54c0-142">Você pode especificar opções de arquivamento para um site específico.</span><span class="sxs-lookup"><span data-stu-id="e54c0-142">You can specify archiving options for a specific site.</span></span> <span data-ttu-id="e54c0-143">Uma configuração de site substitui a configuração global, mas só se aplica ao site específico definido na configuração de site.</span><span class="sxs-lookup"><span data-stu-id="e54c0-143">A site configuration overrides the global configuration, but only for the site specified in the site configuration.</span></span> 
  
1. <span data-ttu-id="e54c0-144">A partir da conta do usuário que foi atribuída à função CsArchivingAdministrator ou CsAdministrator, faça o logon em qualquer computador na sua implantação interna.</span><span class="sxs-lookup"><span data-stu-id="e54c0-144">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="e54c0-145">Abra uma janela do navegador e insira a URL do Administrador para abrir o Painel de Controle do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="e54c0-145">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
    
3. <span data-ttu-id="e54c0-146">Na barra de navegação esquerda, clique em **Monitoramento e Arquivamento** e clique em **Configuração do Arquivamento**.</span><span class="sxs-lookup"><span data-stu-id="e54c0-146">In the left navigation bar, click **Monitoring and Archiving**, and then click **Archiving Configuration**.</span></span>
    
4. <span data-ttu-id="e54c0-147">Na página **Configuração do Arquivamento**, clique em **Novo** e depois em **Configuração do site**.</span><span class="sxs-lookup"><span data-stu-id="e54c0-147">On the **Archiving Configuration** page, click **New**, and then click **Site Configuration**.</span></span>
    
5. <span data-ttu-id="e54c0-148">Em **Selecionar um Site**, selecione o site a ser configurado para arquivamento.</span><span class="sxs-lookup"><span data-stu-id="e54c0-148">In **Select a Site**, select the site to be configured for archiving.</span></span>
    
6. <span data-ttu-id="e54c0-149">Em **Nova Configuração de Arquivamento**, na caixa da lista suspensa **Configuração do Arquivamento**, execute um dos seguintes procedimentos:</span><span class="sxs-lookup"><span data-stu-id="e54c0-149">In **New Archiving Setting**, in the **Archiving setting** drop-down list box, do one of the following:</span></span>
    
   - <span data-ttu-id="e54c0-150">Para habilitar o arquivamento apenas para sessões de mensagens instantâneas (IM), clique em **Arquivar sessões de IM**.</span><span class="sxs-lookup"><span data-stu-id="e54c0-150">To enable archiving only for instant messaging (IM) sessions, click **Archive IM sessions**.</span></span>
    
   - <span data-ttu-id="e54c0-151">Para habilitar o arquivamento para as sessões de IM e conferências, clique em **Arquivar sessões de IM e webconferências**.</span><span class="sxs-lookup"><span data-stu-id="e54c0-151">To enable archiving for both IM sessions and conferences, click **Archive IM and web conferencing sessions**.</span></span>
    
   - <span data-ttu-id="e54c0-152">Para desabilitar o arquivamento para a política, clique em **Desabilitar arquivamento**.</span><span class="sxs-lookup"><span data-stu-id="e54c0-152">To disable archiving for the policy, click **Disable archiving**.</span></span>
    
7. <span data-ttu-id="e54c0-153">Também em **Nova configuração de arquivamento**, faça o seguinte:</span><span class="sxs-lookup"><span data-stu-id="e54c0-153">Also in **New Archiving Setting**, do the following:</span></span>
    
   - <span data-ttu-id="e54c0-154">Para bloquear a atividade quando o arquivamento não estiver disponível, marque a caixa de seleção **Bloquear sessões de mensagem instantânea ou conferência da Web se o arquivamento falhar**.</span><span class="sxs-lookup"><span data-stu-id="e54c0-154">To block activity when archiving is not available, select the **Block instant messaging (IM) or web conferencing sessions if archiving fails** check box.</span></span>
    
   - <span data-ttu-id="e54c0-155">Para usar o Microsoft Exchange Server para armazenar dados de arquivamento, clique na caixa de seleção de integração do **Microsoft Exchange.**</span><span class="sxs-lookup"><span data-stu-id="e54c0-155">To use Microsoft Exchange Server to store archiving data, click the **Microsoft Exchange integration** check box.</span></span>
    
   - <span data-ttu-id="e54c0-156">Para habilitar a exclusão de dados, marque a caixa de seleção **Habilitar exclusão dos dados de arquivamento** e faça um dos seguintes:</span><span class="sxs-lookup"><span data-stu-id="e54c0-156">To enable data purging, select the **Enable purging of archiving data** check box, and then do one of the following:</span></span>
    
   - <span data-ttu-id="e54c0-157">Para especificar a exclusão após um número específico de dias, clique em **Excluir dados de arquivamento exportados e dados de arquivamento armazenados após uma duração máxima (dias)** e especifique o número de dias.</span><span class="sxs-lookup"><span data-stu-id="e54c0-157">To specify purging after a specific number of days, click **Purge exported archiving data and stored archiving data after maximum duration (days)**, and then specify the number of days.</span></span>
    
   - <span data-ttu-id="e54c0-158">Para limitar a exclusão de dados de arquivamento que foram exportados, clique em **Excluir apenas dados de arquivamento exportados**.</span><span class="sxs-lookup"><span data-stu-id="e54c0-158">To limit purging to archiving data that has been exported, click **Purge exported archiving data only**.</span></span>
    
8. <span data-ttu-id="e54c0-159">Clique em **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="e54c0-159">Click **Commit**.</span></span>
    
## <a name="configure-pool-level-archiving-options"></a><span data-ttu-id="e54c0-160">Configurar opções de arquivamento no nível do pool</span><span class="sxs-lookup"><span data-stu-id="e54c0-160">Configure pool level archiving options</span></span>

<span data-ttu-id="e54c0-161">Você pode especificar opções de arquivamento para um pool específico.</span><span class="sxs-lookup"><span data-stu-id="e54c0-161">You can specify archiving options for a specific pool.</span></span> <span data-ttu-id="e54c0-162">Uma configuração de pool substitui a configuração global e de site, mas somente para o pool especificado na configuração de pool.</span><span class="sxs-lookup"><span data-stu-id="e54c0-162">A pool configuration overrides the global configuration and site configuration, but only for the pool specified in the pool configuration.</span></span>
  
1. <span data-ttu-id="e54c0-163">A partir da conta do usuário que foi atribuída à função CsArchivingAdministrator ou CsAdministrator, faça o logon em qualquer computador na sua implantação interna.</span><span class="sxs-lookup"><span data-stu-id="e54c0-163">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="e54c0-164">Abra uma janela do navegador e insira a URL do Administrador para abrir o Painel de Controle do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="e54c0-164">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
    
3. <span data-ttu-id="e54c0-165">Na barra de navegação esquerda, clique em **Monitoramento e Arquivamento** e clique em **Configuração do Arquivamento**.</span><span class="sxs-lookup"><span data-stu-id="e54c0-165">In the left navigation bar, click **Monitoring and Archiving**, and then click **Archiving Configuration**.</span></span>
    
4. <span data-ttu-id="e54c0-166">Na página **Configuração de arquivamento**, clique em **Nova** e em **Configuração de pool**.</span><span class="sxs-lookup"><span data-stu-id="e54c0-166">On the **Archiving Configuration** page, click **New**, and then click **Pool Configuration**.</span></span>
    
5. <span data-ttu-id="e54c0-167">Em **Selecionar um serviço**, selecione o pool que será configurado para arquivamento.</span><span class="sxs-lookup"><span data-stu-id="e54c0-167">In **Select a Service**, select the pool to be configured for archiving.</span></span>
    
6. <span data-ttu-id="e54c0-168">Em **Nova configuração de arquivamento**, na lista suspensa **Configuração de arquivamento**, selecione uma das seguintes opções de arquivamento:</span><span class="sxs-lookup"><span data-stu-id="e54c0-168">In **New Archiving Setting**, in the **Archiving setting** drop-down list, select one of the following archiving options:</span></span>
    
   - <span data-ttu-id="e54c0-169">**Desativar arquivamento**</span><span class="sxs-lookup"><span data-stu-id="e54c0-169">**Disable archiving**</span></span>
    
   - <span data-ttu-id="e54c0-170">**Arquivar sessões de IM**</span><span class="sxs-lookup"><span data-stu-id="e54c0-170">**Archive IM sessions**</span></span>
    
   - <span data-ttu-id="e54c0-171">**Arquivar sessões de IM e conferência da Web**</span><span class="sxs-lookup"><span data-stu-id="e54c0-171">**Archive IM and web conferencing sessions**</span></span>
    
7. <span data-ttu-id="e54c0-172">Na página **Nova configuração de arquivamento**, faça o seguinte:</span><span class="sxs-lookup"><span data-stu-id="e54c0-172">Also in **New Archiving Setting** page, do the following:</span></span>
    
   - <span data-ttu-id="e54c0-173">Para bloquear a atividade quando o arquivamento não estiver disponível, marque a caixa de seleção **Bloquear sessões de IM (mensagens instantâneas) ou webconferência se ocorrer falha no arquivamento**.</span><span class="sxs-lookup"><span data-stu-id="e54c0-173">To block activity when archiving is not available, select the **Block instant messaging (IM) or web conferencing sessions if archiving fails** check box.</span></span>
    
   - <span data-ttu-id="e54c0-174">Para usar o Microsoft Exchange Server para armazenar dados de arquivamento, clique na caixa de seleção de integração do **Microsoft Exchange.**</span><span class="sxs-lookup"><span data-stu-id="e54c0-174">To use Microsoft Exchange Server to store archiving data, click the **Microsoft Exchange integration** check box.</span></span>
    
   - <span data-ttu-id="e54c0-175">Para habilitar a exclusão de dados, marque a caixa de seleção **Habilitar exclusão dos dados de arquivamento** e faça um dos seguintes:</span><span class="sxs-lookup"><span data-stu-id="e54c0-175">To enable data purging, select the **Enable purging of archiving data** check box, and then do one of the following:</span></span>
    
   - <span data-ttu-id="e54c0-176">Para especificar a exclusão após um número específico de dias, clique em **Excluir dados de arquivamento exportados e dados de arquivamento armazenados após uma duração máxima (dias)** e especifique o número de dias.</span><span class="sxs-lookup"><span data-stu-id="e54c0-176">To specify purging after a specific number of days, click **Purge exported archiving data and stored archiving data after maximum duration (days)**, and then specify the number of days.</span></span>
    
   - <span data-ttu-id="e54c0-177">Para limitar a exclusão de dados de arquivamento que foram exportados, clique em **Excluir apenas dados de arquivamento exportados**.</span><span class="sxs-lookup"><span data-stu-id="e54c0-177">To limit purging to archiving data that has been exported, click **Purge exported archiving data only**.</span></span>
    
8. <span data-ttu-id="e54c0-178">Clique em **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="e54c0-178">Click **Commit**.</span></span>
    

