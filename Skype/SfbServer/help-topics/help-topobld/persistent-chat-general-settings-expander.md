---
title: Expansor de Configurações Gerais de Chat Persistente
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/27/2015
audience: ITPro
ms.topic: article
f1.keywords:
- NOCSH
ms.custom:
- ms.lync.tb.PersistentChatGeneralSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 275ee1ae-ca58-4963-bc95-523319f90d96
description: 'Edite as configurações gerais do servidor de chat persistente ou do pool do servidor de chat persistente Configurando ou definindo essas propriedades:'
ms.openlocfilehash: d44818efa1909e0fd90e4c80fcd88b3d11a616ea
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41819473"
---
# <a name="persistent-chat-general-settings-expander"></a><span data-ttu-id="2f117-103">Expansor de Configurações Gerais de Chat Persistente</span><span class="sxs-lookup"><span data-stu-id="2f117-103">Persistent Chat General Settings Expander</span></span>
 
<span data-ttu-id="2f117-104">Edite as configurações **gerais** do servidor de chat persistente ou do pool do servidor de chat persistente Configurando ou definindo essas propriedades:</span><span class="sxs-lookup"><span data-stu-id="2f117-104">You edit the **General** settings for the Persistent Chat Server or Persistent Chat Server pool by configuring or defining these properties:</span></span>
  
 <span data-ttu-id="2f117-105">**Geral**</span><span class="sxs-lookup"><span data-stu-id="2f117-105">**General**</span></span>
  
- <span data-ttu-id="2f117-106">**FQDN**: Edite essa configuração para definir o nome de domínio totalmente qualificado do seu servidor de chat persistente ou pool de servidor de chat persistente</span><span class="sxs-lookup"><span data-stu-id="2f117-106">**FQDN**: Edit this setting to define the fully qualified domain name of your Persistent Chat Server or Persistent Chat Server pool</span></span>
    
- <span data-ttu-id="2f117-107">**Nome de exibição do pool de Chat Persistente**: defina essa configuração para fornecer uma configuração simples e legível do servidor ou pool.</span><span class="sxs-lookup"><span data-stu-id="2f117-107">**Display name of the Persistent Chat pool**: Define this setting to provide a user friendly and user readable setting for the server or pool.</span></span> <span data-ttu-id="2f117-108">Essa configuração torna mais fácil para os usuários associarem um determinado servidor de chat persistente ou pool persistente do servidor de chat com base no nome para exibição em vez de ser mais difícil compreender o nome de domínio totalmente qualificado.</span><span class="sxs-lookup"><span data-stu-id="2f117-108">This setting will make it easier for your users to associate a given Persistent Chat Server or Persistent Chat Server pool based on the display name instead of a more difficult to understand fully qualified domain name.</span></span>
    
- <span data-ttu-id="2f117-109">**Porta de Chat Persistente**: especifique a porta a ser usada para o Chat Persistente.</span><span class="sxs-lookup"><span data-stu-id="2f117-109">**Persistent Chat port**: Specify the port to use for Persistent Chat.</span></span>
    
<span data-ttu-id="2f117-110">Edite as configurações de **associações** para o servidor de chat persistente ou o pool de servidores de chat persistente Configurando ou definindo essas propriedades:</span><span class="sxs-lookup"><span data-stu-id="2f117-110">You edit the **Associations** settings for the Persistent Chat Server or Persistent Chat Server pool by configuring or defining these properties:</span></span>
  
 <span data-ttu-id="2f117-111">**Associações**</span><span class="sxs-lookup"><span data-stu-id="2f117-111">**Associations**</span></span>
  
- <span data-ttu-id="2f117-112">**Repositório do SQL Server**: escolha o repositório do SQL Server e a instância nomeada opcional na lista.</span><span class="sxs-lookup"><span data-stu-id="2f117-112">**SQL Server store**: Select the SQL Server store and optional named instance from the list.</span></span>
    
    <span data-ttu-id="2f117-113">Clique em **Novo** para definir um novo repositório do SQL Server e instância opcional.</span><span class="sxs-lookup"><span data-stu-id="2f117-113">Click **New** to define a new SQL Server store and optional instance.</span></span>
    
- <span data-ttu-id="2f117-114">Marque a caixa de seleção **habilitar o espelhamento da loja do SQL Server** se você quiser habilitar o espelhamento para a loja principal do SQL Server.</span><span class="sxs-lookup"><span data-stu-id="2f117-114">Select the **Enable SQL Server store mirroring** check box if you want to enable mirroring for the primary SQL Server store.</span></span>
    
    <span data-ttu-id="2f117-115">Se você optou por habilitar o espelhamento da loja do SQL Server, selecione a loja e a instância na lista **espelhando o SQL Server Store**.</span><span class="sxs-lookup"><span data-stu-id="2f117-115">If you chose to enable SQL Server store mirroring, select the store and instance from the list **Mirroring SQL Server store**.</span></span>
    
    <span data-ttu-id="2f117-116">Clique em **Novo** para definir um novo repositório do SQL Server e instância opcional.</span><span class="sxs-lookup"><span data-stu-id="2f117-116">Click **New** to define a new SQL Server store and optional instance.</span></span>
    
- <span data-ttu-id="2f117-117">Marque a caixa de seleção **usar a testemunha de espelhamento do SQL Server para habilitar o failover automático** se desejar failover automático da loja principal do SQL Server.</span><span class="sxs-lookup"><span data-stu-id="2f117-117">Select the **Use SQL Server mirroring witness to enable automatic failover** check box if you want automatic failover of the primary SQL Server store.</span></span>
    
    <span data-ttu-id="2f117-118">Se você optou por habilitar a testemunha de espelhamento da loja do SQL Server para habilitar o failover automático, selecione a loja e a instância na lista.</span><span class="sxs-lookup"><span data-stu-id="2f117-118">If you chose to enable SQL Server store mirroring witness to enable automatic failover, select the store and instance from the list.</span></span>
    
    <span data-ttu-id="2f117-119">Clique em **Novo** para definir um novo repositório do SQL Server e instância opcional para o repositório de testemunha.</span><span class="sxs-lookup"><span data-stu-id="2f117-119">Click **New** to define a new SQL Server store and optional instance for the witness store.</span></span>
    
- <span data-ttu-id="2f117-120">Marque a caixa de seleção **usar o backup de repositórios do SQL Server para habilitar a recuperação de desastres** se você quiser habilitar o uso da recuperação de desastre do SQL Server</span><span class="sxs-lookup"><span data-stu-id="2f117-120">Select the **Use backup SQL Server stores to enable disaster recovery** check box if you want to enable the use of SQL Server disaster recovery</span></span>
    
    <span data-ttu-id="2f117-121">Se você escolher habilitar a recuperação de desastre, selecione um repositório e uma instância na lista **Repositório do SQL Server de backup**.</span><span class="sxs-lookup"><span data-stu-id="2f117-121">If you chose to enable disaster recovery, select a store and instance from the **Backup SQL Server store** list.</span></span>
    
    <span data-ttu-id="2f117-122">Clique em **Novo** para definir um novo repositório do SQL Server e instância opcional.</span><span class="sxs-lookup"><span data-stu-id="2f117-122">Click **New** to define a new SQL Server store and optional instance.</span></span>
    
- <span data-ttu-id="2f117-123">Marque a caixa de seleção **habilitar o espelhamento da loja do SQL Server** se você quiser habilitar o espelhamento do armazenamento de espelhamento do SQL Server de backup.</span><span class="sxs-lookup"><span data-stu-id="2f117-123">Select the **Enable SQL Server store mirroring** check box if you want to enable mirroring for the backup SQL Server mirroring store.</span></span>
    
    <span data-ttu-id="2f117-124">Se você optou por habilitar o espelhamento de backup do SQL Server Store, selecione a loja e a instância no espelho da lista **backup do SQL Server Store**.</span><span class="sxs-lookup"><span data-stu-id="2f117-124">If you chose to enable backup SQL Server store mirroring, select the store and instance from the list **Backup SQL Server store mirror**.</span></span>
    
    <span data-ttu-id="2f117-125">Clique em **Novo** para definir um novo repositório do SQL Server e instância opcional.</span><span class="sxs-lookup"><span data-stu-id="2f117-125">Click **New** to define a new SQL Server store and optional instance.</span></span>
    
- <span data-ttu-id="2f117-126">Marque a caixa de seleção **usar a testemunha de espelhamento do SQL Server para habilitar o failover automático** se desejar failover automático do repositório do SQL Server de backup.</span><span class="sxs-lookup"><span data-stu-id="2f117-126">Select the **Use SQL Server mirroring witness to enable automatic failover** check box if you want automatic failover of the backup SQL Server store.</span></span>
    
    <span data-ttu-id="2f117-127">Se você optou por habilitar a testemunha de espelhamento da loja do SQL Server para habilitar o failover automático, selecione a loja e a instância na lista.</span><span class="sxs-lookup"><span data-stu-id="2f117-127">If you chose to enable SQL Server store mirroring witness to enable automatic failover, select the store and instance from the list.</span></span>
    
    <span data-ttu-id="2f117-128">Clique em **Novo** para definir um novo repositório do SQL Server e instância opcional para o repositório de testemunha.</span><span class="sxs-lookup"><span data-stu-id="2f117-128">Click **New** to define a new SQL Server store and optional instance for the witness store.</span></span>
    
- <span data-ttu-id="2f117-129">Marque a caixa de seleção **Habilitar conformidade** se quiser habilitar o uso do banco de dados de conformidade</span><span class="sxs-lookup"><span data-stu-id="2f117-129">Select the **Enable compliance** check box if you want to enable the use of a compliance database</span></span>
    
    <span data-ttu-id="2f117-130">Se você escolher habilitar a conformidade, selecione um repositório e uma instância na lista **Repositório do SQL Server de conformidade de backup**.</span><span class="sxs-lookup"><span data-stu-id="2f117-130">If you chose to enable compliance, select a store and instance from the **Compliance SQL Server store** list.</span></span>
    
    <span data-ttu-id="2f117-131">Clique em **Novo** para definir um novo repositório do SQL Server e instância opcional.</span><span class="sxs-lookup"><span data-stu-id="2f117-131">Click **New** to define a new SQL Server store and optional instance.</span></span>
    
- <span data-ttu-id="2f117-132">Marque a caixa de seleção **habilitar o espelhamento da loja do SQL Server** se você quiser habilitar o espelhamento para a loja do SQL Server de conformidade.</span><span class="sxs-lookup"><span data-stu-id="2f117-132">Select the **Enable SQL Server store mirroring** check box if you want to enable mirroring for the compliance SQL Server store.</span></span>
    
    <span data-ttu-id="2f117-133">Se você optou por habilitar o espelhamento de compatibilidade do SQL Server Store, selecione a loja e a instância no espelho da lista **conformidade do SQL Server Store**.</span><span class="sxs-lookup"><span data-stu-id="2f117-133">If you chose to enable compliance SQL Server store mirroring, select the store and instance from the list **Compliance SQL Server store mirror**.</span></span>
    
    <span data-ttu-id="2f117-134">Clique em **Novo** para definir um novo repositório do SQL Server e instância opcional.</span><span class="sxs-lookup"><span data-stu-id="2f117-134">Click **New** to define a new SQL Server store and optional instance.</span></span>
    
- <span data-ttu-id="2f117-135">Marque a caixa de seleção **usar a testemunha de espelhamento do SQL Server para habilitar o failover automático** se desejar failover automático da loja do SQL Server de conformidade.</span><span class="sxs-lookup"><span data-stu-id="2f117-135">Select the **Use SQL Server mirroring witness to enable automatic failover** check box if you want automatic failover of the compliance SQL Server store.</span></span>
    
    <span data-ttu-id="2f117-136">Se você optou por habilitar a testemunha de espelhamento da loja do SQL Server para habilitar o failover automático, selecione a loja e a instância na lista.</span><span class="sxs-lookup"><span data-stu-id="2f117-136">If you chose to enable SQL Server store mirroring witness to enable automatic failover, select the store and instance from the list.</span></span>
    
    <span data-ttu-id="2f117-137">Clique em **Novo** para definir um novo repositório do SQL Server e instância opcional para o repositório de testemunha.</span><span class="sxs-lookup"><span data-stu-id="2f117-137">Click **New** to define a new SQL Server store and optional instance for the witness store.</span></span>
    
- <span data-ttu-id="2f117-138">Se você escolher habilitar a conformidade, selecione um repositório e uma instância na lista **Repositório do SQL Server de conformidade de backup**.</span><span class="sxs-lookup"><span data-stu-id="2f117-138">If you chose to enable compliance, select a store and instance from the **Backup compliance SQL Server store** list.</span></span>
    
    <span data-ttu-id="2f117-139">Clique em **Novo** para definir um novo repositório do SQL Server e instância opcional.</span><span class="sxs-lookup"><span data-stu-id="2f117-139">Click **New** to define a new SQL Server store and optional instance.</span></span>
    
- <span data-ttu-id="2f117-140">Marque a caixa de seleção **habilitar o espelhamento da loja do SQL Server** se você quiser habilitar o espelhamento para a loja do SQL Server de conformidade.</span><span class="sxs-lookup"><span data-stu-id="2f117-140">Select the **Enable SQL Server store mirroring** check box if you want to enable mirroring for the compliance SQL Server store.</span></span>
    
    <span data-ttu-id="2f117-141">Se você optou por habilitar o espelhamento de compatibilidade do SQL Server Store, selecione a loja e a instância no espelho da lista de **conformidade de backup do SQL Server Store**.</span><span class="sxs-lookup"><span data-stu-id="2f117-141">If you chose to enable compliance SQL Server store mirroring, select the store and instance from the list **Backup compliance SQL Server store mirror**.</span></span>
    
    <span data-ttu-id="2f117-142">Clique em **Novo** para definir um novo repositório do SQL Server e instância opcional.</span><span class="sxs-lookup"><span data-stu-id="2f117-142">Click **New** to define a new SQL Server store and optional instance.</span></span>
    
- <span data-ttu-id="2f117-143">Marque a caixa de seleção **usar a testemunha de espelhamento do SQL Server para habilitar o failover automático** se desejar failover automático da loja do SQL Server de conformidade de backup.</span><span class="sxs-lookup"><span data-stu-id="2f117-143">Select the **Use SQL Server mirroring witness to enable automatic failover** check box if you want automatic failover of the backup compliance SQL Server store.</span></span>
    
    <span data-ttu-id="2f117-144">Se você optou por habilitar a testemunha de espelhamento da loja do SQL Server para habilitar o failover automático, selecione a loja e a instância na lista.</span><span class="sxs-lookup"><span data-stu-id="2f117-144">If you chose to enable SQL Server store mirroring witness to enable automatic failover, select the store and instance from the list.</span></span>
    
    <span data-ttu-id="2f117-145">Clique em **Novo** para definir um novo repositório do SQL Server e instância opcional para o repositório de testemunha.</span><span class="sxs-lookup"><span data-stu-id="2f117-145">Click **New** to define a new SQL Server store and optional instance for the witness store.</span></span>
    
- <span data-ttu-id="2f117-146">**Repositório de arquivos** Selecione um local de armazenamento de arquivos na lista ou clique em **novo** para criar um novo repositório de arquivos.</span><span class="sxs-lookup"><span data-stu-id="2f117-146">**File store** Select a file store location from the list, or click **New** to create a new file store.</span></span>
    
  <span data-ttu-id="2f117-147">**OK** Aceita e confirma as alterações na caixa de diálogo.</span><span class="sxs-lookup"><span data-stu-id="2f117-147">**OK** Accepts and commits changes to the dialog.</span></span>
  
  <span data-ttu-id="2f117-148">**Cancelar** Descarta as alterações e fecha a caixa de diálogo.</span><span class="sxs-lookup"><span data-stu-id="2f117-148">**Cancel** Discards changes and closes the dialog.</span></span>
  
  <span data-ttu-id="2f117-149">**Ajuda** Exibe essa tela de ajuda.</span><span class="sxs-lookup"><span data-stu-id="2f117-149">**Help** Displays this help screen.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="2f117-150">Confira também</span><span class="sxs-lookup"><span data-stu-id="2f117-150">See also</span></span>

[<span data-ttu-id="2f117-151">Planejar Servidor de Chat Persistente no Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="2f117-151">Plan for Persistent Chat Server in Skype for Business Server 2015</span></span>](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md)
  
[<span data-ttu-id="2f117-152">Adicionar um servidor de chat persistente à sua topologia do Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="2f117-152">Add Persistent Chat Server to your Skype for Business Server 2015 topology</span></span>](../../deploy/deploy-persistent-chat-server/add-persistent-chat-server.md)
  
[<span data-ttu-id="2f117-153">Configurar a alta disponibilidade e a recuperação de desastres para o Servidor de Chat Persistente no Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="2f117-153">Configure high availability and disaster recovery for Persistent Chat Server in Skype for Business Server 2015</span></span>](../../deploy/deploy-persistent-chat-server/configure-hadr-for-persistent-chat.md)
