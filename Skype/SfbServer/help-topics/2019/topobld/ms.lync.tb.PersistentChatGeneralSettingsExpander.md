---
title: Expansor de Configurações Gerais de Chat Persistente
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.date: 3/27/2015
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.PersistentChatGeneralSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 275ee1ae-ca58-4963-bc95-523319f90d96
description: 'Você pode editar as configurações gerais para o servidor de Chat persistente ou o pool de servidor de Chat persistente configurando ou definindo essas propriedades:'
ms.openlocfilehash: 7124839f0b3869ecc6f5589359727ac141a054d9
ms.sourcegitcommit: 9d816453083c26fd24f8a1cdc0f53f3d218c43b3
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/25/2018
---
# <a name="persistent-chat-general-settings-expander"></a><span data-ttu-id="6656c-103">Expansor de Configurações Gerais de Chat Persistente</span><span class="sxs-lookup"><span data-stu-id="6656c-103">Persistent Chat General Settings Expander</span></span>
 
<span data-ttu-id="6656c-104">Você pode editar as configurações **gerais** para o servidor de Chat persistente ou o pool de servidor de Chat persistente configurando ou definindo essas propriedades:</span><span class="sxs-lookup"><span data-stu-id="6656c-104">You edit the **General** settings for the Persistent Chat Server or Persistent Chat Server pool by configuring or defining these properties:</span></span>
  
 <span data-ttu-id="6656c-105">**Geral**</span><span class="sxs-lookup"><span data-stu-id="6656c-105">**General**</span></span>
  
- <span data-ttu-id="6656c-106">**FQDN**: edite essa configuração para definir o nome de domínio totalmente qualificado do seu servidor de Chat persistente ou o pool do servidor de Chat persistente</span><span class="sxs-lookup"><span data-stu-id="6656c-106">**FQDN**: Edit this setting to define the fully qualified domain name of your Persistent Chat Server or Persistent Chat Server pool</span></span>
    
- <span data-ttu-id="6656c-107">**Nome de exibição do pool de Chat Persistente**: defina essa configuração para fornecer uma configuração simples e legível do servidor ou pool.</span><span class="sxs-lookup"><span data-stu-id="6656c-107">**Display name of the Persistent Chat pool**: Define this setting to provide a user friendly and user readable setting for the server or pool.</span></span> <span data-ttu-id="6656c-108">Essa configuração será facilitam para os usuários associar a um determinado servidor de Chat persistente ou o pool de servidor de Chat persistente com base no nome para exibição, em vez de um mais difíceis de entender o nome de domínio totalmente qualificado.</span><span class="sxs-lookup"><span data-stu-id="6656c-108">This setting will make it easier for your users to associate a given Persistent Chat Server or Persistent Chat Server pool based on the display name instead of a more difficult to understand fully qualified domain name.</span></span>
    
- <span data-ttu-id="6656c-109">**Porta de Chat Persistente**: especifique a porta a ser usada para o Chat Persistente.</span><span class="sxs-lookup"><span data-stu-id="6656c-109">**Persistent Chat port**: Specify the port to use for Persistent Chat.</span></span>
    
<span data-ttu-id="6656c-110">Você pode editar as configurações de **associações** para o servidor de Chat persistente ou o pool de servidor de Chat persistente configurando ou definindo essas propriedades:</span><span class="sxs-lookup"><span data-stu-id="6656c-110">You edit the **Associations** settings for the Persistent Chat Server or Persistent Chat Server pool by configuring or defining these properties:</span></span>
  
 <span data-ttu-id="6656c-111">**Associações**</span><span class="sxs-lookup"><span data-stu-id="6656c-111">**Associations**</span></span>
  
- <span data-ttu-id="6656c-112">**Repositório do SQL Server**: escolha o repositório do SQL Server e a instância nomeada opcional na lista.</span><span class="sxs-lookup"><span data-stu-id="6656c-112">**SQL Server store**: Select the SQL Server store and optional named instance from the list.</span></span>
    
    <span data-ttu-id="6656c-113">Clique em **Novo** para definir um novo repositório do SQL Server e instância opcional.</span><span class="sxs-lookup"><span data-stu-id="6656c-113">Click **New** to define a new SQL Server store and optional instance.</span></span>
    
- <span data-ttu-id="6656c-114">Marque a caixa de seleção **espelhamento do repositório de habilitar o SQL Server** se desejar habilitar o espelhamento para o SQL Server store principal.</span><span class="sxs-lookup"><span data-stu-id="6656c-114">Select the **Enable SQL Server store mirroring** check box if you want to enable mirroring for the primary SQL Server store.</span></span>
    
    <span data-ttu-id="6656c-115">Se você escolher habilitar o espelhamento do repositório do SQL Server, selecione o repositório e a instância na lista **espelhando o SQL Server store**.</span><span class="sxs-lookup"><span data-stu-id="6656c-115">If you chose to enable SQL Server store mirroring, select the store and instance from the list **Mirroring SQL Server store**.</span></span>
    
    <span data-ttu-id="6656c-116">Clique em **Novo** para definir um novo repositório do SQL Server e instância opcional.</span><span class="sxs-lookup"><span data-stu-id="6656c-116">Click **New** to define a new SQL Server store and optional instance.</span></span>
    
- <span data-ttu-id="6656c-117">Marque a caixa de seleção **usar SQL Server espelhamento testemunha para habilitar o failover automático** se quiser failover automático do repositório do SQL Server principal.</span><span class="sxs-lookup"><span data-stu-id="6656c-117">Select the **Use SQL Server mirroring witness to enable automatic failover** check box if you want automatic failover of the primary SQL Server store.</span></span>
    
    <span data-ttu-id="6656c-118">Se você escolher habilitar a testemunha para habilitar failover automático de espelhamento do SQL Server store, selecione o repositório e a instância na lista.</span><span class="sxs-lookup"><span data-stu-id="6656c-118">If you chose to enable SQL Server store mirroring witness to enable automatic failover, select the store and instance from the list.</span></span>
    
    <span data-ttu-id="6656c-119">Clique em **Novo** para definir um novo repositório do SQL Server e instância opcional para o repositório de testemunha.</span><span class="sxs-lookup"><span data-stu-id="6656c-119">Click **New** to define a new SQL Server store and optional instance for the witness store.</span></span>
    
- <span data-ttu-id="6656c-120">Marque a caixa de seleção **usar backup repositórios do SQL Server para habilitar a recuperação de desastre** se quiser habilitar o uso de recuperação de desastre do SQL Server</span><span class="sxs-lookup"><span data-stu-id="6656c-120">Select the **Use backup SQL Server stores to enable disaster recovery** check box if you want to enable the use of SQL Server disaster recovery</span></span>
    
    <span data-ttu-id="6656c-121">Se você escolher habilitar a recuperação de desastre, selecione um repositório e uma instância na lista **Repositório do SQL Server de backup**.</span><span class="sxs-lookup"><span data-stu-id="6656c-121">If you chose to enable disaster recovery, select a store and instance from the **Backup SQL Server store** list.</span></span>
    
    <span data-ttu-id="6656c-122">Clique em **Novo** para definir um novo repositório do SQL Server e instância opcional.</span><span class="sxs-lookup"><span data-stu-id="6656c-122">Click **New** to define a new SQL Server store and optional instance.</span></span>
    
- <span data-ttu-id="6656c-123">Marque a caixa de seleção **espelhamento do repositório de habilitar o SQL Server** se desejar habilitar o espelhamento do SQL Server backup espelhamento do repositório.</span><span class="sxs-lookup"><span data-stu-id="6656c-123">Select the **Enable SQL Server store mirroring** check box if you want to enable mirroring for the backup SQL Server mirroring store.</span></span>
    
    <span data-ttu-id="6656c-124">Se você escolher habilitar o espelhamento do repositório do SQL Server backup, selecione o repositório e a instância na lista **Backup do SQL Server store espelho**.</span><span class="sxs-lookup"><span data-stu-id="6656c-124">If you chose to enable backup SQL Server store mirroring, select the store and instance from the list **Backup SQL Server store mirror**.</span></span>
    
    <span data-ttu-id="6656c-125">Clique em **Novo** para definir um novo repositório do SQL Server e instância opcional.</span><span class="sxs-lookup"><span data-stu-id="6656c-125">Click **New** to define a new SQL Server store and optional instance.</span></span>
    
- <span data-ttu-id="6656c-126">Marque a caixa de seleção **usar SQL Server espelhamento testemunha para habilitar o failover automático** se quiser failover automático do repositório do SQL Server backup.</span><span class="sxs-lookup"><span data-stu-id="6656c-126">Select the **Use SQL Server mirroring witness to enable automatic failover** check box if you want automatic failover of the backup SQL Server store.</span></span>
    
    <span data-ttu-id="6656c-127">Se você escolher habilitar a testemunha para habilitar failover automático de espelhamento do SQL Server store, selecione o repositório e a instância na lista.</span><span class="sxs-lookup"><span data-stu-id="6656c-127">If you chose to enable SQL Server store mirroring witness to enable automatic failover, select the store and instance from the list.</span></span>
    
    <span data-ttu-id="6656c-128">Clique em **Novo** para definir um novo repositório do SQL Server e instância opcional para o repositório de testemunha.</span><span class="sxs-lookup"><span data-stu-id="6656c-128">Click **New** to define a new SQL Server store and optional instance for the witness store.</span></span>
    
- <span data-ttu-id="6656c-129">Marque a caixa de seleção **Habilitar conformidade** se quiser habilitar o uso do banco de dados de conformidade</span><span class="sxs-lookup"><span data-stu-id="6656c-129">Select the **Enable compliance** check box if you want to enable the use of a compliance database</span></span>
    
    <span data-ttu-id="6656c-130">Se você escolher habilitar a conformidade, selecione um repositório e uma instância na lista **Repositório do SQL Server de conformidade de backup**.</span><span class="sxs-lookup"><span data-stu-id="6656c-130">If you chose to enable compliance, select a store and instance from the **Compliance SQL Server store** list.</span></span>
    
    <span data-ttu-id="6656c-131">Clique em **Novo** para definir um novo repositório do SQL Server e instância opcional.</span><span class="sxs-lookup"><span data-stu-id="6656c-131">Click **New** to define a new SQL Server store and optional instance.</span></span>
    
- <span data-ttu-id="6656c-132">Marque a caixa de seleção **espelhamento do repositório de habilitar o SQL Server** se desejar habilitar o espelhamento para o SQL Server store de conformidade.</span><span class="sxs-lookup"><span data-stu-id="6656c-132">Select the **Enable SQL Server store mirroring** check box if you want to enable mirroring for the compliance SQL Server store.</span></span>
    
    <span data-ttu-id="6656c-133">Se você escolher habilitar o espelhamento de repositório do SQL Server de conformidade, selecione o repositório e a instância na lista **conformidade SQL Server store espelho**.</span><span class="sxs-lookup"><span data-stu-id="6656c-133">If you chose to enable compliance SQL Server store mirroring, select the store and instance from the list **Compliance SQL Server store mirror**.</span></span>
    
    <span data-ttu-id="6656c-134">Clique em **Novo** para definir um novo repositório do SQL Server e instância opcional.</span><span class="sxs-lookup"><span data-stu-id="6656c-134">Click **New** to define a new SQL Server store and optional instance.</span></span>
    
- <span data-ttu-id="6656c-135">Marque a caixa de seleção **usar SQL Server espelhamento testemunha para habilitar o failover automático** se quiser failover automático do repositório do SQL Server de conformidade.</span><span class="sxs-lookup"><span data-stu-id="6656c-135">Select the **Use SQL Server mirroring witness to enable automatic failover** check box if you want automatic failover of the compliance SQL Server store.</span></span>
    
    <span data-ttu-id="6656c-136">Se você escolher habilitar a testemunha para habilitar failover automático de espelhamento do SQL Server store, selecione o repositório e a instância na lista.</span><span class="sxs-lookup"><span data-stu-id="6656c-136">If you chose to enable SQL Server store mirroring witness to enable automatic failover, select the store and instance from the list.</span></span>
    
    <span data-ttu-id="6656c-137">Clique em **Novo** para definir um novo repositório do SQL Server e instância opcional para o repositório de testemunha.</span><span class="sxs-lookup"><span data-stu-id="6656c-137">Click **New** to define a new SQL Server store and optional instance for the witness store.</span></span>
    
- <span data-ttu-id="6656c-138">Se você escolher habilitar a conformidade, selecione um repositório e uma instância na lista **Repositório do SQL Server de conformidade de backup**.</span><span class="sxs-lookup"><span data-stu-id="6656c-138">If you chose to enable compliance, select a store and instance from the **Backup compliance SQL Server store** list.</span></span>
    
    <span data-ttu-id="6656c-139">Clique em **Novo** para definir um novo repositório do SQL Server e instância opcional.</span><span class="sxs-lookup"><span data-stu-id="6656c-139">Click **New** to define a new SQL Server store and optional instance.</span></span>
    
- <span data-ttu-id="6656c-140">Marque a caixa de seleção **espelhamento do repositório de habilitar o SQL Server** se desejar habilitar o espelhamento para o SQL Server store de conformidade.</span><span class="sxs-lookup"><span data-stu-id="6656c-140">Select the **Enable SQL Server store mirroring** check box if you want to enable mirroring for the compliance SQL Server store.</span></span>
    
    <span data-ttu-id="6656c-141">Se você escolher habilitar o espelhamento de repositório do SQL Server de conformidade, selecione o repositório e a instância na lista **espelho de store de conformidade de Backup do SQL Server**.</span><span class="sxs-lookup"><span data-stu-id="6656c-141">If you chose to enable compliance SQL Server store mirroring, select the store and instance from the list **Backup compliance SQL Server store mirror**.</span></span>
    
    <span data-ttu-id="6656c-142">Clique em **Novo** para definir um novo repositório do SQL Server e instância opcional.</span><span class="sxs-lookup"><span data-stu-id="6656c-142">Click **New** to define a new SQL Server store and optional instance.</span></span>
    
- <span data-ttu-id="6656c-143">Marque a caixa de seleção **usar SQL Server espelhamento testemunha para habilitar o failover automático** se quiser failover automático do repositório do SQL Server de backup de conformidade.</span><span class="sxs-lookup"><span data-stu-id="6656c-143">Select the **Use SQL Server mirroring witness to enable automatic failover** check box if you want automatic failover of the backup compliance SQL Server store.</span></span>
    
    <span data-ttu-id="6656c-144">Se você escolher habilitar a testemunha para habilitar failover automático de espelhamento do SQL Server store, selecione o repositório e a instância na lista.</span><span class="sxs-lookup"><span data-stu-id="6656c-144">If you chose to enable SQL Server store mirroring witness to enable automatic failover, select the store and instance from the list.</span></span>
    
    <span data-ttu-id="6656c-145">Clique em **Novo** para definir um novo repositório do SQL Server e instância opcional para o repositório de testemunha.</span><span class="sxs-lookup"><span data-stu-id="6656c-145">Click **New** to define a new SQL Server store and optional instance for the witness store.</span></span>
    
- <span data-ttu-id="6656c-146">**Repositório de arquivo** Selecione um local do repositório de arquivo na lista ou clique em **novo** para criar um novo repositório de arquivo.</span><span class="sxs-lookup"><span data-stu-id="6656c-146">**File store** Select a file store location from the list, or click **New** to create a new file store.</span></span>
    
 <span data-ttu-id="6656c-147">**OK** Aceita e confirma as alterações na caixa de diálogo.</span><span class="sxs-lookup"><span data-stu-id="6656c-147">**OK** Accepts and commits changes to the dialog.</span></span>
  
 <span data-ttu-id="6656c-148">**Cancelar** Descarta as alterações e fecha a caixa de diálogo.</span><span class="sxs-lookup"><span data-stu-id="6656c-148">**Cancel** Discards changes and closes the dialog.</span></span>
  
 <span data-ttu-id="6656c-149">**Ajuda** Exibe essa tela de ajuda.</span><span class="sxs-lookup"><span data-stu-id="6656c-149">**Help** Displays this help screen.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="6656c-150">Consulte também</span><span class="sxs-lookup"><span data-stu-id="6656c-150">See also</span></span>

#### 

[<span data-ttu-id="6656c-151">Planejar o servidor de Chat persistente no Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="6656c-151">Plan for Persistent Chat Server in Skype for Business Server 2015</span></span>](../../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md)
  
[<span data-ttu-id="6656c-152">Adicionar servidor de Chat persistente à sua Skype para a topologia de negócios Server 2015</span><span class="sxs-lookup"><span data-stu-id="6656c-152">Add Persistent Chat Server to your Skype for Business Server 2015 topology</span></span>](../../../deploy/deploy-persistent-chat-server/add-persistent-chat-server.md)
  
[<span data-ttu-id="6656c-153">Configurar alta disponibilidade e recuperação de desastres para o servidor de Chat persistente no Skype para Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="6656c-153">Configure high availability and disaster recovery for Persistent Chat Server in Skype for Business Server 2015</span></span>](../../../deploy/deploy-persistent-chat-server/configure-hadr-for-persistent-chat.md)

