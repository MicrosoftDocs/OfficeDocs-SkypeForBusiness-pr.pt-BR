---
title: Expansor de Configurações Gerais de Bate-papo Persistente
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/27/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.PersistentChatGeneralSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 275ee1ae-ca58-4963-bc95-523319f90d96
description: 'Edite as configurações Gerais para o Servidor de Chat Persistente ou pool de Servidor de Chat Persistente configurando ou definindo estas propriedades:'
ms.openlocfilehash: 5c0884f4877e622a82b58ea914ffa934eecc3291
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49823844"
---
# <a name="persistent-chat-general-settings-expander"></a><span data-ttu-id="c46d5-103">Expansor de Configurações Gerais de Chat Persistente</span><span class="sxs-lookup"><span data-stu-id="c46d5-103">Persistent Chat General Settings Expander</span></span>
 
<span data-ttu-id="c46d5-104">Edite as **configurações** Gerais para o Servidor de Chat Persistente ou pool de Servidor de Chat Persistente definindo ou definindo estas propriedades:</span><span class="sxs-lookup"><span data-stu-id="c46d5-104">You edit the **General** settings for the Persistent Chat Server or Persistent Chat Server pool by configuring or defining these properties:</span></span>
  
 <span data-ttu-id="c46d5-105">**Geral**</span><span class="sxs-lookup"><span data-stu-id="c46d5-105">**General**</span></span>
  
- <span data-ttu-id="c46d5-106">**FQDN:** Edite essa configuração para definir o nome de domínio totalmente qualificado do seu Servidor de Chat Persistente ou pool de Servidor de Chat Persistente</span><span class="sxs-lookup"><span data-stu-id="c46d5-106">**FQDN**: Edit this setting to define the fully qualified domain name of your Persistent Chat Server or Persistent Chat Server pool</span></span>
    
- <span data-ttu-id="c46d5-107">**Nome de exibição do pool de Chat Persistente**: defina essa configuração para fornecer uma configuração simples e legível do servidor ou pool.</span><span class="sxs-lookup"><span data-stu-id="c46d5-107">**Display name of the Persistent Chat pool**: Define this setting to provide a user friendly and user readable setting for the server or pool.</span></span> <span data-ttu-id="c46d5-108">Essa configuração facilitará para os usuários associar um determinado Servidor de Chat Persistente ou pool de Servidor de Chat Persistente com base no nome de exibição, em vez de um mais difícil de entender o nome de domínio totalmente qualificado.</span><span class="sxs-lookup"><span data-stu-id="c46d5-108">This setting will make it easier for your users to associate a given Persistent Chat Server or Persistent Chat Server pool based on the display name instead of a more difficult to understand fully qualified domain name.</span></span>
    
- <span data-ttu-id="c46d5-109">**Porta de Chat Persistente**: especifique a porta a ser usada para o Chat Persistente.</span><span class="sxs-lookup"><span data-stu-id="c46d5-109">**Persistent Chat port**: Specify the port to use for Persistent Chat.</span></span>
    
<span data-ttu-id="c46d5-110">Edite as **configurações de Associações** para o Servidor de Chat Persistente ou pool de Servidor de Chat Persistente definindo ou definindo estas propriedades:</span><span class="sxs-lookup"><span data-stu-id="c46d5-110">You edit the **Associations** settings for the Persistent Chat Server or Persistent Chat Server pool by configuring or defining these properties:</span></span>
  
 <span data-ttu-id="c46d5-111">**Associações**</span><span class="sxs-lookup"><span data-stu-id="c46d5-111">**Associations**</span></span>
  
- <span data-ttu-id="c46d5-112">**Sql Server store:** selecione o armazenamento do SQL Server e a instância nomeada opcional na lista.</span><span class="sxs-lookup"><span data-stu-id="c46d5-112">**SQL Server store**: Select the SQL Server store and optional named instance from the list.</span></span>
    
    <span data-ttu-id="c46d5-113">Clique em **Novo** para definir um novo SQL Server store e instância opcional.</span><span class="sxs-lookup"><span data-stu-id="c46d5-113">Click **New** to define a new SQL Server store and optional instance.</span></span>
    
- <span data-ttu-id="c46d5-114">Marque a **caixa de seleção Habilitar** espelhamento do armazenamento do SQL Server se quiser habilitar o espelhamento para o armazenamento principal do SQL Server.</span><span class="sxs-lookup"><span data-stu-id="c46d5-114">Select the **Enable SQL Server store mirroring** check box if you want to enable mirroring for the primary SQL Server store.</span></span>
    
    <span data-ttu-id="c46d5-115">Se você escolher habilitar o espelhamento do armazenamento do SQL Server, selecione o armazenamento e a instância no armazenamento **do SQL Server de espelhamento de lista.**</span><span class="sxs-lookup"><span data-stu-id="c46d5-115">If you chose to enable SQL Server store mirroring, select the store and instance from the list **Mirroring SQL Server store**.</span></span>
    
    <span data-ttu-id="c46d5-116">Clique em **Novo** para definir um novo SQL Server store e instância opcional.</span><span class="sxs-lookup"><span data-stu-id="c46d5-116">Click **New** to define a new SQL Server store and optional instance.</span></span>
    
- <span data-ttu-id="c46d5-117">Marque a caixa de seleção Usar testemunha de espelhamento do SQL Server para habilitar o failover automático se quiser **failover** automático do armazenamento principal do SQL Server.</span><span class="sxs-lookup"><span data-stu-id="c46d5-117">Select the **Use SQL Server mirroring witness to enable automatic failover** check box if you want automatic failover of the primary SQL Server store.</span></span>
    
    <span data-ttu-id="c46d5-118">Se você optar por habilitar a testemunha de espelhamento do armazenamento do SQL Server para habilitar o failover automático, selecione o armazenamento e a instância na lista.</span><span class="sxs-lookup"><span data-stu-id="c46d5-118">If you chose to enable SQL Server store mirroring witness to enable automatic failover, select the store and instance from the list.</span></span>
    
    <span data-ttu-id="c46d5-119">Clique em **Novo** para definir um novo SQL Server store e instância opcional para o repositório de testemunha.</span><span class="sxs-lookup"><span data-stu-id="c46d5-119">Click **New** to define a new SQL Server store and optional instance for the witness store.</span></span>
    
- <span data-ttu-id="c46d5-120">Marque a caixa de seleção Usar **armazenamentos** de backup do SQL Server para habilitar a recuperação de desastres se quiser habilitar o uso da recuperação de desastres do SQL Server</span><span class="sxs-lookup"><span data-stu-id="c46d5-120">Select the **Use backup SQL Server stores to enable disaster recovery** check box if you want to enable the use of SQL Server disaster recovery</span></span>
    
    <span data-ttu-id="c46d5-121">Se você escolher habilitar a recuperação de desastre, selecione um repositório e uma instância na lista **Backup do SQL Server**.</span><span class="sxs-lookup"><span data-stu-id="c46d5-121">If you chose to enable disaster recovery, select a store and instance from the **Backup SQL Server store** list.</span></span>
    
    <span data-ttu-id="c46d5-122">Clique em **Novo** para definir um novo SQL Server store e instância opcional.</span><span class="sxs-lookup"><span data-stu-id="c46d5-122">Click **New** to define a new SQL Server store and optional instance.</span></span>
    
- <span data-ttu-id="c46d5-123">Marque a **caixa de seleção Habilitar** espelhamento do armazenamento do SQL Server se quiser habilitar o espelhamento para o armazenamento de espelhamento do SQL Server de backup.</span><span class="sxs-lookup"><span data-stu-id="c46d5-123">Select the **Enable SQL Server store mirroring** check box if you want to enable mirroring for the backup SQL Server mirroring store.</span></span>
    
    <span data-ttu-id="c46d5-124">Se você escolher habilitar o espelhamento do armazenamento do SQL Server de backup, selecione o armazenamento e a instância no espelho de **armazenamento do SQL Server de backup da lista.**</span><span class="sxs-lookup"><span data-stu-id="c46d5-124">If you chose to enable backup SQL Server store mirroring, select the store and instance from the list **Backup SQL Server store mirror**.</span></span>
    
    <span data-ttu-id="c46d5-125">Clique em **Novo** para definir um novo SQL Server store e instância opcional.</span><span class="sxs-lookup"><span data-stu-id="c46d5-125">Click **New** to define a new SQL Server store and optional instance.</span></span>
    
- <span data-ttu-id="c46d5-126">Marque a caixa de seleção Usar testemunha de espelhamento do SQL Server para habilitar o failover automático se quiser **failover** automático do armazenamento do SQL Server de backup.</span><span class="sxs-lookup"><span data-stu-id="c46d5-126">Select the **Use SQL Server mirroring witness to enable automatic failover** check box if you want automatic failover of the backup SQL Server store.</span></span>
    
    <span data-ttu-id="c46d5-127">Se você optar por habilitar a testemunha de espelhamento do armazenamento do SQL Server para habilitar o failover automático, selecione o armazenamento e a instância na lista.</span><span class="sxs-lookup"><span data-stu-id="c46d5-127">If you chose to enable SQL Server store mirroring witness to enable automatic failover, select the store and instance from the list.</span></span>
    
    <span data-ttu-id="c46d5-128">Clique em **Novo** para definir um novo SQL Server store e instância opcional para o repositório de testemunha.</span><span class="sxs-lookup"><span data-stu-id="c46d5-128">Click **New** to define a new SQL Server store and optional instance for the witness store.</span></span>
    
- <span data-ttu-id="c46d5-129">Marque a caixa de seleção **Habilitar conformidade** se quiser habilitar o uso do banco de dados de conformidade</span><span class="sxs-lookup"><span data-stu-id="c46d5-129">Select the **Enable compliance** check box if you want to enable the use of a compliance database</span></span>
    
    <span data-ttu-id="c46d5-130">Se você escolher habilitar a conformidade, selecione um repositório e uma instância na lista **SQL Server store de conformidade**.</span><span class="sxs-lookup"><span data-stu-id="c46d5-130">If you chose to enable compliance, select a store and instance from the **Compliance SQL Server store** list.</span></span>
    
    <span data-ttu-id="c46d5-131">Clique em **Novo** para definir um novo SQL Server store e instância opcional.</span><span class="sxs-lookup"><span data-stu-id="c46d5-131">Click **New** to define a new SQL Server store and optional instance.</span></span>
    
- <span data-ttu-id="c46d5-132">Marque a **caixa de seleção Habilitar** espelhamento do armazenamento do SQL Server se quiser habilitar o espelhamento para o armazenamento do SQL Server de conformidade.</span><span class="sxs-lookup"><span data-stu-id="c46d5-132">Select the **Enable SQL Server store mirroring** check box if you want to enable mirroring for the compliance SQL Server store.</span></span>
    
    <span data-ttu-id="c46d5-133">Se você escolher habilitar o espelhamento do armazenamento do SQL Server de conformidade, selecione o armazenamento e a instância no espelho de armazenamento do **SQL Server de conformidade da lista.**</span><span class="sxs-lookup"><span data-stu-id="c46d5-133">If you chose to enable compliance SQL Server store mirroring, select the store and instance from the list **Compliance SQL Server store mirror**.</span></span>
    
    <span data-ttu-id="c46d5-134">Clique em **Novo** para definir um novo SQL Server store e instância opcional.</span><span class="sxs-lookup"><span data-stu-id="c46d5-134">Click **New** to define a new SQL Server store and optional instance.</span></span>
    
- <span data-ttu-id="c46d5-135">Marque a caixa de seleção Usar testemunha de espelhamento do SQL Server para habilitar o failover automático se quiser **failover** automático do armazenamento do SQL Server de conformidade.</span><span class="sxs-lookup"><span data-stu-id="c46d5-135">Select the **Use SQL Server mirroring witness to enable automatic failover** check box if you want automatic failover of the compliance SQL Server store.</span></span>
    
    <span data-ttu-id="c46d5-136">Se você optar por habilitar a testemunha de espelhamento do armazenamento do SQL Server para habilitar o failover automático, selecione o armazenamento e a instância na lista.</span><span class="sxs-lookup"><span data-stu-id="c46d5-136">If you chose to enable SQL Server store mirroring witness to enable automatic failover, select the store and instance from the list.</span></span>
    
    <span data-ttu-id="c46d5-137">Clique em **Novo** para definir um novo SQL Server store e instância opcional para o repositório de testemunha.</span><span class="sxs-lookup"><span data-stu-id="c46d5-137">Click **New** to define a new SQL Server store and optional instance for the witness store.</span></span>
    
- <span data-ttu-id="c46d5-138">Se você escolher habilitar a conformidade, selecione um repositório e uma instância na lista **Backup do SQL Server store de conformidade**.</span><span class="sxs-lookup"><span data-stu-id="c46d5-138">If you chose to enable compliance, select a store and instance from the **Backup compliance SQL Server store** list.</span></span>
    
    <span data-ttu-id="c46d5-139">Clique em **Novo** para definir um novo SQL Server store e instância opcional.</span><span class="sxs-lookup"><span data-stu-id="c46d5-139">Click **New** to define a new SQL Server store and optional instance.</span></span>
    
- <span data-ttu-id="c46d5-140">Marque a **caixa de seleção Habilitar** espelhamento do armazenamento do SQL Server se quiser habilitar o espelhamento para o armazenamento do SQL Server de conformidade.</span><span class="sxs-lookup"><span data-stu-id="c46d5-140">Select the **Enable SQL Server store mirroring** check box if you want to enable mirroring for the compliance SQL Server store.</span></span>
    
    <span data-ttu-id="c46d5-141">Se você optar por habilitar o espelhamento do armazenamento do SQL Server de conformidade, selecione o armazenamento e a instância na lista Backup do espelho de armazenamento do **SQL Server de conformidade.**</span><span class="sxs-lookup"><span data-stu-id="c46d5-141">If you chose to enable compliance SQL Server store mirroring, select the store and instance from the list **Backup compliance SQL Server store mirror**.</span></span>
    
    <span data-ttu-id="c46d5-142">Clique em **Novo** para definir um novo SQL Server store e instância opcional.</span><span class="sxs-lookup"><span data-stu-id="c46d5-142">Click **New** to define a new SQL Server store and optional instance.</span></span>
    
- <span data-ttu-id="c46d5-143">Marque a caixa de seleção Usar testemunha de espelhamento do SQL Server para habilitar o failover automático se quiser **failover** automático do armazenamento do SQL Server de conformidade de backup.</span><span class="sxs-lookup"><span data-stu-id="c46d5-143">Select the **Use SQL Server mirroring witness to enable automatic failover** check box if you want automatic failover of the backup compliance SQL Server store.</span></span>
    
    <span data-ttu-id="c46d5-144">Se você optar por habilitar a testemunha de espelhamento do armazenamento do SQL Server para habilitar o failover automático, selecione o armazenamento e a instância na lista.</span><span class="sxs-lookup"><span data-stu-id="c46d5-144">If you chose to enable SQL Server store mirroring witness to enable automatic failover, select the store and instance from the list.</span></span>
    
    <span data-ttu-id="c46d5-145">Clique em **Novo** para definir um novo SQL Server store e instância opcional para o repositório de testemunha.</span><span class="sxs-lookup"><span data-stu-id="c46d5-145">Click **New** to define a new SQL Server store and optional instance for the witness store.</span></span>
    
- <span data-ttu-id="c46d5-146">**Armazenamento de arquivos** Selecione um local de armazenamento de arquivos na lista ou clique em **Novo** para criar um novo armazenamento de arquivos.</span><span class="sxs-lookup"><span data-stu-id="c46d5-146">**File store** Select a file store location from the list, or click **New** to create a new file store.</span></span>
    
  <span data-ttu-id="c46d5-147">**OK** aceita e confirma as alterações na caixa de diálogo.</span><span class="sxs-lookup"><span data-stu-id="c46d5-147">**OK** Accepts and commits changes to the dialog.</span></span>
  
  <span data-ttu-id="c46d5-148">**Cancelar** descarta as alterações e fecha a caixa de diálogo.</span><span class="sxs-lookup"><span data-stu-id="c46d5-148">**Cancel** Discards changes and closes the dialog.</span></span>
  
  <span data-ttu-id="c46d5-149">**Ajuda** exibe essa tela de ajuda.</span><span class="sxs-lookup"><span data-stu-id="c46d5-149">**Help** Displays this help screen.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="c46d5-150">Confira também</span><span class="sxs-lookup"><span data-stu-id="c46d5-150">See also</span></span>

[<span data-ttu-id="c46d5-151">Plano para Servidor de Chat Persistente no Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="c46d5-151">Plan for Persistent Chat Server in Skype for Business Server 2015</span></span>](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md)
  
[<span data-ttu-id="c46d5-152">Adicionar Servidor de Chat Persistente à sua topologia do Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="c46d5-152">Add Persistent Chat Server to your Skype for Business Server 2015 topology</span></span>](../../deploy/deploy-persistent-chat-server/add-persistent-chat-server.md)
  
[<span data-ttu-id="c46d5-153">Configurar alta disponibilidade e recuperação de desastre para o Servidor de Chat Persistente no Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="c46d5-153">Configure high availability and disaster recovery for Persistent Chat Server in Skype for Business Server 2015</span></span>](../../deploy/deploy-persistent-chat-server/configure-hadr-for-persistent-chat.md)
