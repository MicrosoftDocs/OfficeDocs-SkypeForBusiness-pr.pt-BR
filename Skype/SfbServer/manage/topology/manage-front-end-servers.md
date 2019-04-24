---
title: Gerenciar servidores de Front-End em Skype para Business Server
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: ab748733-6bad-4c93-8dda-db8d5271653d
description: 'Resumo: Saiba como adicionar, remover, patch ou atualizar os servidores Front-End do Skype para Business Server.'
ms.openlocfilehash: bfd090ab007523ff05795aff012e4a01da4a0175
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32214705"
---
# <a name="manage-front-end-servers-in-skype-for-business-server"></a><span data-ttu-id="9a079-103">Gerenciar servidores de Front-End em Skype para Business Server</span><span class="sxs-lookup"><span data-stu-id="9a079-103">Manage Front End Servers in Skype for Business Server</span></span>
 
<span data-ttu-id="9a079-104">Este artigo explica como adicionar ou remover servidores Front-End e como aplicar atualizações ou patches para servidores Front-End.</span><span class="sxs-lookup"><span data-stu-id="9a079-104">This article explains how to add or remove Front End Servers and how to apply upgrades or patches to Front End Servers.</span></span>

## <a name="add-or-remove-front-end-servers"></a><span data-ttu-id="9a079-105">Adicionar ou remover servidores Front-End</span><span class="sxs-lookup"><span data-stu-id="9a079-105">Add or remove Front End Servers</span></span>
  
<span data-ttu-id="9a079-106">Quando você adicionar um servidor Front-End a um pool ou remove um servidor Front-End de um pool, em seguida, você precisará reiniciar o pool.</span><span class="sxs-lookup"><span data-stu-id="9a079-106">When you add a Front End Server to a pool, or remove a Front End Server from a pool, you then need to restart the pool.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="9a079-p101">Ao adicionar ou remover um servidor do pool em sua topologia e depois publicar a topologia atualizada, todos os servidores no pool serão reiniciados ao mesmo tempo. Durante a reinicialização dos servidores, o pool permanece offline, o que interrompe o serviço para os usuários conectados a esse pool. Para evitar a interrupção do serviço para os usuários, planeje a publicação da topologia com o novo servidor no pool fora do horário comercial.</span><span class="sxs-lookup"><span data-stu-id="9a079-p101">When you add or remove a server to the pool in your topology and then publish the updated topology, it will cause all of the servers in the pool to restart at the same time. While the servers are restarting the pool is offline, which will interrupt service for your users connected to that pool. To prevent any interruption of service to users, plan to publish the topology with the new server in the pool during non-business hours.</span></span> 
  
<span data-ttu-id="9a079-110">Você pode usar o procedimento a seguir, quando a adição ou remoção de um servidor Front-End.</span><span class="sxs-lookup"><span data-stu-id="9a079-110">You can use the following procedure when adding or removing a Front End Server.</span></span>
  
> [!NOTE]
> <span data-ttu-id="9a079-111">Se estiver adicionando novos servidores ao pool, atualize os novos servidores do pool no mesmo nível de Atualização Cumulativa dos servidores existentes no Pool.</span><span class="sxs-lookup"><span data-stu-id="9a079-111">If you're adding new servers to the pool, update your new pool servers to be at the same Cumulative Update level as the existing servers in the Pool.</span></span> 
  
### <a name="to-add-or-remove-front-end-servers"></a><span data-ttu-id="9a079-112">Para adicionar ou remover servidores Front-End</span><span class="sxs-lookup"><span data-stu-id="9a079-112">To add or remove Front End Servers</span></span>

1. <span data-ttu-id="9a079-113">Se você estiver removendo quaisquer servidores Front-End, primeiro interrompa novas conexões para esses servidores.</span><span class="sxs-lookup"><span data-stu-id="9a079-113">If you are removing any Front End Servers, first stop new connections to those servers.</span></span> <span data-ttu-id="9a079-114">Para fazer isso, é possível usar o seguinte cmdlet:</span><span class="sxs-lookup"><span data-stu-id="9a079-114">To do so, you can use the following cmdlet:</span></span>
    
   ```
   Stop-CsWindowsService -Graceful
   ```

2. <span data-ttu-id="9a079-115">Abra o construtor de topologias e adicionar ou remover os servidores necessários.</span><span class="sxs-lookup"><span data-stu-id="9a079-115">Open Topology Builder, and add or remove the necessary servers.</span></span> 
    
3. <span data-ttu-id="9a079-116">Publique a topologia.</span><span class="sxs-lookup"><span data-stu-id="9a079-116">Publish the topology.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="9a079-p103">Ao adicionar ou remover um servidor do pool em sua topologia e depois publicar a topologia atualizada, todos os servidores no pool serão reiniciados ao mesmo tempo. Durante a reinicialização dos servidores, o pool permanece offline, o que interrompe o serviço para os usuários conectados a esse pool. Para evitar a interrupção do serviço para os usuários, planeje a publicação da topologia com o novo servidor no pool fora do horário comercial.</span><span class="sxs-lookup"><span data-stu-id="9a079-p103">When you add or remove a server to the pool in your topology and then publish the updated topology, it will cause all of the servers in the pool to restart at the same time. While the servers are restarting the pool is offline, which will interrupt service for your users connected to that pool. To prevent any interruption of service to users, plan to publish the topology with the new server in the pool during non-business hours.</span></span> 
  
  > [!NOTE]
> <span data-ttu-id="9a079-120">Além disso, quando você adicionar ou remove um servidor ao pool, você deve executar o Skype para o Assistente de implantação de servidor de negócios em cada computador adicionado ou removido, para obter mais informações, consulte [Instalar Skype para Business Server nos servidores na topologia](https://docs.microsoft.com/skypeforbusiness/deploy/install/install-skype-for-business-server)</span><span class="sxs-lookup"><span data-stu-id="9a079-120">Also, when you add or remove a server to the pool, you must run the Skype for Business Server Deployment Wizard on each computer added or removed, for more information, see [Install Skype for Business Server on servers in the topology](https://docs.microsoft.com/skypeforbusiness/deploy/install/install-skype-for-business-server)</span></span>
  
4. <span data-ttu-id="9a079-121">Se você tiver alterado o número de servidores em seu pool de Front-End em qualquer uma das seguintes maneiras, redefinir o pool com digitando o seguinte cmdlet: Reset-CsPoolRegistrarState - ResetType FullReset - PoolFqdn</span><span class="sxs-lookup"><span data-stu-id="9a079-121">If you have changed the number of servers in your Front End pool in any of the following ways, then reset the pool with by typing the following cmdlet: Reset-CsPoolRegistrarState -ResetType FullReset -PoolFqdn</span></span> 
    
   ```
    Reset-CsPoolRegistrarState -ResetType FullReset -PoolFqdn  <PoolFQDN>
   ```

     - <span data-ttu-id="9a079-122">2 para qualquer número</span><span class="sxs-lookup"><span data-stu-id="9a079-122">2 to any</span></span>
    
     - <span data-ttu-id="9a079-123">Qualquer número para 2</span><span class="sxs-lookup"><span data-stu-id="9a079-123">Any to 2</span></span>
    
     - <span data-ttu-id="9a079-124">3 para qualquer número</span><span class="sxs-lookup"><span data-stu-id="9a079-124">3 to any</span></span>
    
     - <span data-ttu-id="9a079-125">Qualquer número para 3</span><span class="sxs-lookup"><span data-stu-id="9a079-125">Any to 3</span></span>
    
5. <span data-ttu-id="9a079-126">Reinicie o pool digitando o seguinte cmdlet</span><span class="sxs-lookup"><span data-stu-id="9a079-126">Restart the pool by typing the following cmdlet</span></span>
    
   ```
   Start-CsPool
   ```

## <a name="patch-or-update-front-end-servers"></a><span data-ttu-id="9a079-127">Corrigir ou atualizar Servidores Front-End</span><span class="sxs-lookup"><span data-stu-id="9a079-127">Patch or update Front End Servers</span></span>

<span data-ttu-id="9a079-128">Quando você os servidores em um pool de Front-End de patch, você fazer isso um servidor de cada vez.</span><span class="sxs-lookup"><span data-stu-id="9a079-128">When you patch the servers in a Front End pool, you do so one server at a time.</span></span> 
  
### <a name="to-apply-an-upgrade-to-the-front-end-servers-in-a-pool"></a><span data-ttu-id="9a079-129">Para aplicar uma atualização aos servidores Front-End em um pool</span><span class="sxs-lookup"><span data-stu-id="9a079-129">To apply an upgrade to the Front End servers in a pool</span></span>

1. <span data-ttu-id="9a079-130">Digite o seguinte cmdlet:</span><span class="sxs-lookup"><span data-stu-id="9a079-130">Type the following cmdlet:</span></span>
    
   ```
   Get-CsPoolFabricState -PoolFqdn <PoolFQDN>
   ```

     <span data-ttu-id="9a079-131">Se este cmdlet mostrar qualquer réplica ausente, execute o seguinte cmdlet para recuperar o pool antes de aplicar qualquer patch.</span><span class="sxs-lookup"><span data-stu-id="9a079-131">If this cmdlet shows any missing replicas, then run the following cmdlet to recover the pool before you apply any patches.</span></span>
    
   ```
   Reset-CsPoolRegistrarState -ResetType QuorumLossRecovery
   ```

2. <span data-ttu-id="9a079-132">No primeiro servidor a ser corrigido, execute o seguinte cmdlet:</span><span class="sxs-lookup"><span data-stu-id="9a079-132">On the first server you want to patch, run the following cmdlet:</span></span>
    
   ```
   Invoke-CsComputerFailOver -ComputerName <Front End Server to be patched>
   ```

    <span data-ttu-id="9a079-133">Este cmdlet Move todos os serviços para outros servidores Front-End no pool e deixa este servidor offline.</span><span class="sxs-lookup"><span data-stu-id="9a079-133">This cmdlet moves all services to other Front End Servers in the pool, and takes this server offline.</span></span>
    
3. <span data-ttu-id="9a079-134">Aplique a atualização ou correção neste servidor.</span><span class="sxs-lookup"><span data-stu-id="9a079-134">Apply the upgrade or patch to this server.</span></span>
    
4. <span data-ttu-id="9a079-135">No servidor atualizado, execute o seguinte cmdlet:</span><span class="sxs-lookup"><span data-stu-id="9a079-135">On the upgraded server, run the following cmdlet:</span></span>
    
   ```
   Invoke-CsComputerFailBack -ComputerName <Front End Server to be patched>
   ```

    <span data-ttu-id="9a079-136">O servidor voltará ao serviço.</span><span class="sxs-lookup"><span data-stu-id="9a079-136">The server is returned to service.</span></span>
    
5. <span data-ttu-id="9a079-137">Repita as etapas 2 a 4 para cada servidor que precisar ser atualizado.</span><span class="sxs-lookup"><span data-stu-id="9a079-137">Repeat Steps 2-4 for each server that needs to be upgraded.</span></span>
    
