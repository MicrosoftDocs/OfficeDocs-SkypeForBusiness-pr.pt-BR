---
title: Configurar opções de arquivamento no Skype for Business Server 2015
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 2f534697-ac7f-45b7-8cdc-ba67f052223b
description: 'Resumo: Leia este tópico para saber como configurar opções de arquivamento iniciais para Skype para Business Server 2015. Inicialmente, você define as configurações de arquivamento quando faz a implementação, mas você pode alterar, adicionar e excluir configurações depois da implementação.'
ms.openlocfilehash: 38923d436f2fc5543158dfce6f8bebde27c7c911
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/28/2018
---
# <a name="configure-archiving-options-for-skype-for-business-server-2015"></a><span data-ttu-id="6349a-104">Configurar opções de arquivamento no Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="6349a-104">Configure archiving options for Skype for Business Server 2015</span></span>
 
<span data-ttu-id="6349a-105">**Resumo:** Leia este tópico para saber como configurar opções de arquivamento iniciais para Skype para Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="6349a-105">**Summary:** Read this topic to learn how to configure initial archiving options for Skype for Business Server 2015.</span></span> <span data-ttu-id="6349a-106">Inicialmente, você define as configurações de arquivamento quando faz a implementação, mas você pode alterar, adicionar e excluir configurações depois da implementação.</span><span class="sxs-lookup"><span data-stu-id="6349a-106">You initially set up archiving configurations when you deploy archiving, but you can change, add, and delete configurations after deployment.</span></span>
  
<span data-ttu-id="6349a-107">Para configurar inicial de arquivamento configurações, você use Skype para painel de controle do Business Server para especificar o seguinte:</span><span class="sxs-lookup"><span data-stu-id="6349a-107">To configure initial archiving configurations, you use Skype for Business Server Control Panel to specify the following:</span></span>
  
- <span data-ttu-id="6349a-108">Configuração no nível global criada por padrão quando você implanta o Skype para Business Server</span><span class="sxs-lookup"><span data-stu-id="6349a-108">Global-level configuration that is created by default when you deploy Skype for Business Server</span></span>
    
- <span data-ttu-id="6349a-109">Configurações opcionais em nível de site que especificam como o arquivamento é implementado para um site específico</span><span class="sxs-lookup"><span data-stu-id="6349a-109">Optional site-level configurations that specify how archiving is implemented for a specific site</span></span>
    
- <span data-ttu-id="6349a-110">Configurações opcionais de nível do pool que especificam como o arquivamento é implementado para um pool específico</span><span class="sxs-lookup"><span data-stu-id="6349a-110">Optional pool-level configurations that specify how archiving is implemented for a specific pool</span></span>
    
<span data-ttu-id="6349a-111">Você terá que configurar opções para definir:</span><span class="sxs-lookup"><span data-stu-id="6349a-111">You will need to configure options for the following:</span></span>
  
- <span data-ttu-id="6349a-112">Habilitar ou desabilitar o arquivamento</span><span class="sxs-lookup"><span data-stu-id="6349a-112">Whether to enable or disable archiving</span></span>
    
- <span data-ttu-id="6349a-113">Arquivar ou não sessões de mensagens instantâneas</span><span class="sxs-lookup"><span data-stu-id="6349a-113">Whether to archive IM sessions</span></span>
    
- <span data-ttu-id="6349a-114">Arquivar ou não sessões de webconferência</span><span class="sxs-lookup"><span data-stu-id="6349a-114">Whether to archive web conferencing sessions</span></span>
    
- <span data-ttu-id="6349a-115">Bloquear ou não uma atividade quando o arquivamento não estiver disponível</span><span class="sxs-lookup"><span data-stu-id="6349a-115">Whether to block activity when archiving is not available</span></span>
    
- <span data-ttu-id="6349a-116">Usar ou não integração com o Exchange</span><span class="sxs-lookup"><span data-stu-id="6349a-116">Whether to use Exchange integration</span></span>
    
- <span data-ttu-id="6349a-117">Como configurar a limpeza e exportação de dados</span><span class="sxs-lookup"><span data-stu-id="6349a-117">How to set up purging and exporting of data</span></span>
    
> [!NOTE]
> <span data-ttu-id="6349a-118">Você deve especificar todas as opções apropriadas antes de habilitar o arquivamento.</span><span class="sxs-lookup"><span data-stu-id="6349a-118">You should specify all appropriate options before enabling archiving.</span></span> 
  
<span data-ttu-id="6349a-119">Para obter detalhes sobre como as configurações de arquivamento são implementadas, incluindo as opções que você pode especificar e a hierarquia de arquivamento configurações, consulte [Plan para arquivamento no Skype para Business Server 2015](../../plan-your-deployment/archiving/archiving.md).</span><span class="sxs-lookup"><span data-stu-id="6349a-119">For details about how archiving configurations are implemented, including which options you can specify and the hierarchy of archiving configurations, see [Plan for archiving in Skype for Business Server 2015](../../plan-your-deployment/archiving/archiving.md).</span></span> <span data-ttu-id="6349a-120">Para obter detalhes sobre como gerenciar configurações após a implantação usando o painel de controle ou usando o Windows PowerShell, consulte [Gerenciar opções de arquivamento no Skype para Business Server 2015](../../manage/archiving/options.md).</span><span class="sxs-lookup"><span data-stu-id="6349a-120">For details about how to manage configurations after deployment by using the Control Panel or by using Windows PowerShell, see [Manage archiving options in Skype for Business Server 2015](../../manage/archiving/options.md).</span></span>
  
## <a name="configure-global-level-archiving-options"></a><span data-ttu-id="6349a-121">Configurar opções de arquivamento em nível global</span><span class="sxs-lookup"><span data-stu-id="6349a-121">Configure global level archiving options</span></span>

<span data-ttu-id="6349a-122">Quando você adicionar arquivamento à topologia e publica a topologia, Skype para Business Server cria uma configuração global para arquivamento.</span><span class="sxs-lookup"><span data-stu-id="6349a-122">When you add archiving to your topology and publish the topology, Skype for Business Server creates a global configuration for archiving.</span></span> <span data-ttu-id="6349a-123">Por padrão, nenhuma opção de arquivamento está ativada na configuração global.</span><span class="sxs-lookup"><span data-stu-id="6349a-123">By default, no archiving options are enabled in the global configuration.</span></span> <span data-ttu-id="6349a-124">A configuração global controla quais opções são habilitadas para toda a sua implantação, a não ser que você defina configurações de site ou pool que substituam a configuração global.</span><span class="sxs-lookup"><span data-stu-id="6349a-124">The global configuration controls which options are enabled for your entire deployment, unless you set up site or pool configurations, which override the global configuration.</span></span>
  
<span data-ttu-id="6349a-125">Para configurar opções de arquivamento em nível global:</span><span class="sxs-lookup"><span data-stu-id="6349a-125">To configure archiving options at the global level:</span></span>
  
1. <span data-ttu-id="6349a-126">Usando uma conta de usuário atribuída à função CsArchivingAdministrator ou CsAdministrator, faça logon em qualquer computador de sua implantação interna.</span><span class="sxs-lookup"><span data-stu-id="6349a-126">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="6349a-127">Abra uma janela do navegador e insira a URL do administrador para abrir o Skype para painel de controle do servidor de negócios.</span><span class="sxs-lookup"><span data-stu-id="6349a-127">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
    
3. <span data-ttu-id="6349a-128">Na barra de navegação da esquerda, clique em **Monitoramento e Arquivamento**, e depois, clique em **Configuração de Arquivamento**.</span><span class="sxs-lookup"><span data-stu-id="6349a-128">In the left navigation bar, click **Monitoring and Archiving**, and then click **Archiving Configuration**.</span></span>
    
4. <span data-ttu-id="6349a-129">Na página **Configuração de arquivamento**, clique em **Global**, **Editar** e **Mostrar detalhes**.</span><span class="sxs-lookup"><span data-stu-id="6349a-129">On the **Archiving Configuration** page, click **Global**, click **Edit**, and then click **Show details**.</span></span>
    
5. <span data-ttu-id="6349a-130">Em **Editar configuração de arquivamento - Global**, na lista suspensa **Configuração de arquivamento**, selecione uma das seguintes opções de arquivamento:</span><span class="sxs-lookup"><span data-stu-id="6349a-130">In **Edit Archiving Setting - Global**, in the **Archiving setting** drop-down list, select one of the following archiving options:</span></span>
    
   - <span data-ttu-id="6349a-131">**Desativar arquivamento**</span><span class="sxs-lookup"><span data-stu-id="6349a-131">**Disable archiving**</span></span>
    
   - <span data-ttu-id="6349a-132">**Arquivar sessões de IM**</span><span class="sxs-lookup"><span data-stu-id="6349a-132">**Archive IM sessions**</span></span>
    
   - <span data-ttu-id="6349a-133">**Arquivar sessões de IM e conferência da Web**</span><span class="sxs-lookup"><span data-stu-id="6349a-133">**Archive IM and web conferencing sessions**</span></span>
    
6. <span data-ttu-id="6349a-134">Também na página **Editar configuração de arquivamento - Global** , faça o seguinte:</span><span class="sxs-lookup"><span data-stu-id="6349a-134">Also on the **Edit Archiving Setting - Global** page, do the following:</span></span>
    
   - <span data-ttu-id="6349a-135">Para bloquear a atividade quando o arquivamento não estiver disponível, marque a caixa de seleção **Bloquear sessões de mensagem instantânea ou webconferência se o arquivamento falhar**.</span><span class="sxs-lookup"><span data-stu-id="6349a-135">To block activity when archiving is not available, select the **Block instant messaging (IM) or web conferencing sessions if archiving fails** check box.</span></span>
    
   - <span data-ttu-id="6349a-136">Para usar o Microsoft Exchange Server para armazenar dados de arquivamento, clique em caixa de seleção **integração do Microsoft Exchange** .</span><span class="sxs-lookup"><span data-stu-id="6349a-136">To use Microsoft Exchange Server to store archiving data, click the **Microsoft Exchange integration** check box.</span></span>
    
   - <span data-ttu-id="6349a-137">Para habilitar a exclusão de dados, marque a caixa de seleção **Habilitar exclusão dos dados de arquivamento** e execute uma das seguintes ações:</span><span class="sxs-lookup"><span data-stu-id="6349a-137">To enable data purging, select the **Enable purging of archiving data** check box, and then do one of the following:</span></span>
    
   - <span data-ttu-id="6349a-138">Para especificar a exclusão após um número específico de dias, clique em **Excluir dados de arquivamento exportados e dados de arquivamento armazenados após uma duração máxima (dias)** e especifique o número de dias.</span><span class="sxs-lookup"><span data-stu-id="6349a-138">To specify purging after a specific number of days, click **Purge exported archiving data and stored archiving data after maximum duration (days)**, and then specify the number of days.</span></span>
    
   - <span data-ttu-id="6349a-139">Para limitar a exclusão de dados de arquivamento que foram exportados, clique em **Excluir apenas dados de arquivamento exportados**.</span><span class="sxs-lookup"><span data-stu-id="6349a-139">To limit purging to archiving data that has been exported, click **Purge exported archiving data only**.</span></span>
    
7. <span data-ttu-id="6349a-140">Clique em **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="6349a-140">Click **Commit**.</span></span>
    
## <a name="configure-site-level-archiving-options"></a><span data-ttu-id="6349a-141">Configurar opções de arquivamento em nível de site</span><span class="sxs-lookup"><span data-stu-id="6349a-141">Configure site level archiving options</span></span>

<span data-ttu-id="6349a-142">Você pode especificar opções de arquivamento para um site específico.</span><span class="sxs-lookup"><span data-stu-id="6349a-142">You can specify archiving options for a specific site.</span></span> <span data-ttu-id="6349a-143">Uma configuração de site substitui a configuração global, mas só se aplica ao site específico definido na configuração de site.</span><span class="sxs-lookup"><span data-stu-id="6349a-143">A site configuration overrides the global configuration, but only for the site specified in the site configuration.</span></span> 
  
1. <span data-ttu-id="6349a-144">Usando uma conta de usuário atribuída à função CsArchivingAdministrator ou CsAdministrator, faça logon em qualquer computador de sua implantação interna.</span><span class="sxs-lookup"><span data-stu-id="6349a-144">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="6349a-145">Abra uma janela do navegador e insira a URL do administrador para abrir o Skype para painel de controle do servidor de negócios.</span><span class="sxs-lookup"><span data-stu-id="6349a-145">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
    
3. <span data-ttu-id="6349a-146">Na barra de navegação da esquerda, clique em **Monitoramento e Arquivamento**, e depois, clique em **Configuração de Arquivamento**.</span><span class="sxs-lookup"><span data-stu-id="6349a-146">In the left navigation bar, click **Monitoring and Archiving**, and then click **Archiving Configuration**.</span></span>
    
4. <span data-ttu-id="6349a-147">Na página **Configuração do Arquivamento**, clique em **Nova** e depois em **Configuração do site**.</span><span class="sxs-lookup"><span data-stu-id="6349a-147">On the **Archiving Configuration** page, click **New**, and then click **Site Configuration**.</span></span>
    
5. <span data-ttu-id="6349a-148">Em **Selecionar um Site**, selecione o site a ser configurado para arquivamento.</span><span class="sxs-lookup"><span data-stu-id="6349a-148">In **Select a Site**, select the site to be configured for archiving.</span></span>
    
6. <span data-ttu-id="6349a-149">Em **Nova configuração de arquivamento**, na caixa de lista suspensa **Configuração de arquivamento**, execute uma das seguintes ações:</span><span class="sxs-lookup"><span data-stu-id="6349a-149">In **New Archiving Setting**, in the **Archiving setting** drop-down list box, do one of the following:</span></span>
    
   - <span data-ttu-id="6349a-150">Para habilitar o arquivamento apenas para sessões de IM, clique em **Arquivar sessões de IM**.</span><span class="sxs-lookup"><span data-stu-id="6349a-150">To enable archiving only for instant messaging (IM) sessions, click **Archive IM sessions**.</span></span>
    
   - <span data-ttu-id="6349a-151">Para habilitar o arquivamento para sessões de IM e conferências, clique em **Arquivar sessões de IM e webconferência**.</span><span class="sxs-lookup"><span data-stu-id="6349a-151">To enable archiving for both IM sessions and conferences, click **Archive IM and web conferencing sessions**.</span></span>
    
   - <span data-ttu-id="6349a-152">Para desabilitar o arquivamento da política, clique em **Desabilitar arquivamento**.</span><span class="sxs-lookup"><span data-stu-id="6349a-152">To disable archiving for the policy, click **Disable archiving**.</span></span>
    
7. <span data-ttu-id="6349a-153">Também em **Nova configuração de arquivamento**, execute uma das seguintes ações:</span><span class="sxs-lookup"><span data-stu-id="6349a-153">Also in **New Archiving Setting**, do the following:</span></span>
    
   - <span data-ttu-id="6349a-154">Para bloquear a atividade quando o arquivamento não estiver disponível, marque a caixa de seleção **Bloquear sessões de mensagem instantânea ou webconferência se o arquivamento falhar**.</span><span class="sxs-lookup"><span data-stu-id="6349a-154">To block activity when archiving is not available, select the **Block instant messaging (IM) or web conferencing sessions if archiving fails** check box.</span></span>
    
   - <span data-ttu-id="6349a-155">Para usar o Microsoft Exchange Server para armazenar dados de arquivamento, clique em caixa de seleção **integração do Microsoft Exchange** .</span><span class="sxs-lookup"><span data-stu-id="6349a-155">To use Microsoft Exchange Server to store archiving data, click the **Microsoft Exchange integration** check box.</span></span>
    
   - <span data-ttu-id="6349a-156">Para habilitar a exclusão de dados, marque a caixa de seleção **Habilitar exclusão dos dados de arquivamento** e execute uma das seguintes ações:</span><span class="sxs-lookup"><span data-stu-id="6349a-156">To enable data purging, select the **Enable purging of archiving data** check box, and then do one of the following:</span></span>
    
   - <span data-ttu-id="6349a-157">Para especificar a exclusão após um número específico de dias, clique em **Excluir dados de arquivamento exportados e dados de arquivamento armazenados após uma duração máxima (dias)** e especifique o número de dias.</span><span class="sxs-lookup"><span data-stu-id="6349a-157">To specify purging after a specific number of days, click **Purge exported archiving data and stored archiving data after maximum duration (days)**, and then specify the number of days.</span></span>
    
   - <span data-ttu-id="6349a-158">Para limitar a exclusão de dados de arquivamento que foram exportados, clique em **Excluir apenas dados de arquivamento exportados**.</span><span class="sxs-lookup"><span data-stu-id="6349a-158">To limit purging to archiving data that has been exported, click **Purge exported archiving data only**.</span></span>
    
8. <span data-ttu-id="6349a-159">Clique em **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="6349a-159">Click **Commit**.</span></span>
    
## <a name="configure-pool-level-archiving-options"></a><span data-ttu-id="6349a-160">Configurar opções de arquivamento em nível de pool</span><span class="sxs-lookup"><span data-stu-id="6349a-160">Configure pool level archiving options</span></span>

<span data-ttu-id="6349a-p106">Você pode especificar opções de arquivamento para um pool específico. Uma configuração de pool substitui a configuração global e de site, mas só se aplica ao pool específico definido na configuração de pool.</span><span class="sxs-lookup"><span data-stu-id="6349a-p106">You can specify archiving options for a specific pool. A pool configuration overrides the global configuration and site configuration, but only for the pool specified in the pool configuration.</span></span>
  
1. <span data-ttu-id="6349a-163">Usando uma conta de usuário atribuída à função CsArchivingAdministrator ou CsAdministrator, faça logon em qualquer computador de sua implantação interna.</span><span class="sxs-lookup"><span data-stu-id="6349a-163">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="6349a-164">Abra uma janela do navegador e insira a URL do administrador para abrir o Skype para painel de controle do servidor de negócios.</span><span class="sxs-lookup"><span data-stu-id="6349a-164">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
    
3. <span data-ttu-id="6349a-165">Na barra de navegação da esquerda, clique em **Monitoramento e Arquivamento**, e depois, clique em **Configuração de Arquivamento**.</span><span class="sxs-lookup"><span data-stu-id="6349a-165">In the left navigation bar, click **Monitoring and Archiving**, and then click **Archiving Configuration**.</span></span>
    
4. <span data-ttu-id="6349a-166">Na página **Configuração de arquivamento**, clique em **Nova** e em **Configuração de pool**.</span><span class="sxs-lookup"><span data-stu-id="6349a-166">On the **Archiving Configuration** page, click **New**, and then click **Pool Configuration**.</span></span>
    
5. <span data-ttu-id="6349a-167">Em **Selecionar um serviço**, selecione o pool que será configurado para arquivamento.</span><span class="sxs-lookup"><span data-stu-id="6349a-167">In **Select a Service**, select the pool to be configured for archiving.</span></span>
    
6. <span data-ttu-id="6349a-168">Em **Nova configuração de arquivamento**, na lista suspensa **Configuração de arquivamento**, selecione uma das seguintes opções de arquivamento:</span><span class="sxs-lookup"><span data-stu-id="6349a-168">In **New Archiving Setting**, in the **Archiving setting** drop-down list, select one of the following archiving options:</span></span>
    
   - <span data-ttu-id="6349a-169">**Desativar arquivamento**</span><span class="sxs-lookup"><span data-stu-id="6349a-169">**Disable archiving**</span></span>
    
   - <span data-ttu-id="6349a-170">**Arquivar sessões de IM**</span><span class="sxs-lookup"><span data-stu-id="6349a-170">**Archive IM sessions**</span></span>
    
   - <span data-ttu-id="6349a-171">**Arquivar sessões de IM e conferência da Web**</span><span class="sxs-lookup"><span data-stu-id="6349a-171">**Archive IM and web conferencing sessions**</span></span>
    
7. <span data-ttu-id="6349a-172">Na página **Nova configuração de arquivamento**, faça o seguinte:</span><span class="sxs-lookup"><span data-stu-id="6349a-172">Also in **New Archiving Setting** page, do the following:</span></span>
    
   - <span data-ttu-id="6349a-173">Para bloquear a atividade quando o arquivamento não estiver disponível, marque a caixa de seleção **Bloquear sessões de mensagem instantânea ou webconferência se o arquivamento falhar**.</span><span class="sxs-lookup"><span data-stu-id="6349a-173">To block activity when archiving is not available, select the **Block instant messaging (IM) or web conferencing sessions if archiving fails** check box.</span></span>
    
   - <span data-ttu-id="6349a-174">Para usar o Microsoft Exchange Server para armazenar dados de arquivamento, clique em caixa de seleção **integração do Microsoft Exchange** .</span><span class="sxs-lookup"><span data-stu-id="6349a-174">To use Microsoft Exchange Server to store archiving data, click the **Microsoft Exchange integration** check box.</span></span>
    
   - <span data-ttu-id="6349a-175">Para habilitar a exclusão de dados, marque a caixa de seleção **Habilitar exclusão dos dados de arquivamento** e execute uma das seguintes ações:</span><span class="sxs-lookup"><span data-stu-id="6349a-175">To enable data purging, select the **Enable purging of archiving data** check box, and then do one of the following:</span></span>
    
   - <span data-ttu-id="6349a-176">Para especificar a exclusão após um número específico de dias, clique em **Excluir dados de arquivamento exportados e dados de arquivamento armazenados após uma duração máxima (dias)** e especifique o número de dias.</span><span class="sxs-lookup"><span data-stu-id="6349a-176">To specify purging after a specific number of days, click **Purge exported archiving data and stored archiving data after maximum duration (days)**, and then specify the number of days.</span></span>
    
   - <span data-ttu-id="6349a-177">Para limitar a exclusão de dados de arquivamento que foram exportados, clique em **Excluir apenas dados de arquivamento exportados**.</span><span class="sxs-lookup"><span data-stu-id="6349a-177">To limit purging to archiving data that has been exported, click **Purge exported archiving data only**.</span></span>
    
8. <span data-ttu-id="6349a-178">Clique em **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="6349a-178">Click **Commit**.</span></span>
    

