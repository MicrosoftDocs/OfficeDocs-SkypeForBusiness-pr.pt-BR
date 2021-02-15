---
title: Gerenciar servidores front-end no Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: ab748733-6bad-4c93-8dda-db8d5271653d
description: 'Resumo: saiba como adicionar, remover, corrigir ou atualizar servidores front-end no Skype for Business Server.'
ms.openlocfilehash: 16af245b3c49b21309edd3ee2843f2585814ce9e
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49826321"
---
# <a name="manage-front-end-servers-in-skype-for-business-server"></a><span data-ttu-id="cd509-103">Gerenciar servidores front-end no Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="cd509-103">Manage Front End Servers in Skype for Business Server</span></span>
 
<span data-ttu-id="cd509-104">Este artigo explica como adicionar ou remover servidores front-end e como aplicar atualizações ou patches aos Servidores Front-End.</span><span class="sxs-lookup"><span data-stu-id="cd509-104">This article explains how to add or remove Front End Servers and how to apply upgrades or patches to Front End Servers.</span></span>

  > [!NOTE]
> <span data-ttu-id="cd509-105">O Skype for Business Server 2019 não dá suporte a pools de Front End Enterprise Edition com dois Servidores Front-End e não permitirá que a topologia seja publicada nesse cenário.</span><span class="sxs-lookup"><span data-stu-id="cd509-105">Skype for Business Server 2019 does not support Enterprise Edition Front End pools with two Front End Servers, and will not allow the topology to be published in that scenario.</span></span>

## <a name="add-or-remove-front-end-servers"></a><span data-ttu-id="cd509-106">Adicionar ou remover servidores front-end</span><span class="sxs-lookup"><span data-stu-id="cd509-106">Add or remove Front End Servers</span></span>
  
<span data-ttu-id="cd509-107">Ao adicionar um servidor de Front End a um pool, ou remover um servidor de Front End de um pool, você precisará reiniciar o pool.</span><span class="sxs-lookup"><span data-stu-id="cd509-107">When you add a Front End Server to a pool, or remove a Front End Server from a pool, you then need to restart the pool.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="cd509-108">Quando você adiciona ou remove um servidor ao pool em sua topologia e publica a topologia atualizada, isso fará com que todos os servidores no pool reiniciem ao mesmo tempo.</span><span class="sxs-lookup"><span data-stu-id="cd509-108">When you add or remove a server to the pool in your topology and then publish the updated topology, it will cause all of the servers in the pool to restart at the same time.</span></span> <span data-ttu-id="cd509-109">Enquanto os servidores estão reiniciando o pool está offline, o que interromperá o serviço para os usuários conectados a esse pool.</span><span class="sxs-lookup"><span data-stu-id="cd509-109">While the servers are restarting the pool is offline, which will interrupt service for your users connected to that pool.</span></span> <span data-ttu-id="cd509-110">Para evitar qualquer interrupção do serviço para os usuários, planeje publicar a topologia com o novo servidor no pool fora do horário comercial.</span><span class="sxs-lookup"><span data-stu-id="cd509-110">To prevent any interruption of service to users, plan to publish the topology with the new server in the pool during non-business hours.</span></span> 
  
<span data-ttu-id="cd509-111">Você pode usar o procedimento a seguir ao adicionar ou remover um Servidor Front-End.</span><span class="sxs-lookup"><span data-stu-id="cd509-111">You can use the following procedure when adding or removing a Front End Server.</span></span>
  
> [!NOTE]
> <span data-ttu-id="cd509-112">Se você estiver adicionando novos servidores ao pool, atualize os novos servidores do pool para que eles sejam atualizados no mesmo nível da Atualização Cumulativa que os servidores existentes no Pool.</span><span class="sxs-lookup"><span data-stu-id="cd509-112">If you're adding new servers to the pool, update your new pool servers to be at the same Cumulative Update level as the existing servers in the Pool.</span></span> 
  
### <a name="to-add-or-remove-front-end-servers"></a><span data-ttu-id="cd509-113">Para adicionar ou remover servidores front-end</span><span class="sxs-lookup"><span data-stu-id="cd509-113">To add or remove Front End Servers</span></span>

1. <span data-ttu-id="cd509-p102">Se estiver removendo servidores de Front End, primeiro interrompa novas conexões a esses servidores. Para fazer isso, é possível usar o seguinte cmdlet:</span><span class="sxs-lookup"><span data-stu-id="cd509-p102">If you are removing any Front End Servers, first stop new connections to those servers. To do so, you can use the following cmdlet:</span></span>
    
   ```PowerShell
   Stop-CsWindowsService -Graceful
   ```

2. <span data-ttu-id="cd509-116">Abra o Construtor de Topologias, e adiciona ou remova os servidores necessários.</span><span class="sxs-lookup"><span data-stu-id="cd509-116">Open Topology Builder, and add or remove the necessary servers.</span></span> 
    
3. <span data-ttu-id="cd509-117">Publique a topologia.</span><span class="sxs-lookup"><span data-stu-id="cd509-117">Publish the topology.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="cd509-118">Quando você adiciona ou remove um servidor ao pool em sua topologia e publica a topologia atualizada, isso fará com que todos os servidores no pool reiniciem ao mesmo tempo.</span><span class="sxs-lookup"><span data-stu-id="cd509-118">When you add or remove a server to the pool in your topology and then publish the updated topology, it will cause all of the servers in the pool to restart at the same time.</span></span> <span data-ttu-id="cd509-119">Enquanto os servidores estão reiniciando o pool está offline, o que interromperá o serviço para os usuários conectados a esse pool.</span><span class="sxs-lookup"><span data-stu-id="cd509-119">While the servers are restarting the pool is offline, which will interrupt service for your users connected to that pool.</span></span> <span data-ttu-id="cd509-120">Para evitar qualquer interrupção do serviço para os usuários, planeje publicar a topologia com o novo servidor no pool fora do horário comercial.</span><span class="sxs-lookup"><span data-stu-id="cd509-120">To prevent any interruption of service to users, plan to publish the topology with the new server in the pool during non-business hours.</span></span> 
  
  > [!NOTE]
> <span data-ttu-id="cd509-121">Além disso, quando você adiciona ou remove um servidor ao pool, deve executar o Assistente de Implantação do Skype for Business Server em cada computador adicionado ou removido. Para obter mais informações, consulte Instalar o Skype for Business Server em servidores da [topologia](https://docs.microsoft.com/skypeforbusiness/deploy/install/install-skype-for-business-server)</span><span class="sxs-lookup"><span data-stu-id="cd509-121">Also, when you add or remove a server to the pool, you must run the Skype for Business Server Deployment Wizard on each computer added or removed, for more information, see [Install Skype for Business Server on servers in the topology](https://docs.microsoft.com/skypeforbusiness/deploy/install/install-skype-for-business-server)</span></span>
  
4. <span data-ttu-id="cd509-122">Se você tiver alterado o número de servidores em seu pool de Front-End de qualquer uma das maneiras a seguir, redefinir o pool digitando o seguinte cmdlet: Reset-CsPoolRegistrarState -ResetType FullReset -PoolFqdn</span><span class="sxs-lookup"><span data-stu-id="cd509-122">If you have changed the number of servers in your Front End pool in any of the following ways, then reset the pool with by typing the following cmdlet: Reset-CsPoolRegistrarState -ResetType FullReset -PoolFqdn</span></span> 
    
   ```PowerShell
    Reset-CsPoolRegistrarState -ResetType FullReset -PoolFqdn  <PoolFQDN>
   ```

     - <span data-ttu-id="cd509-123">2 para qualquer um</span><span class="sxs-lookup"><span data-stu-id="cd509-123">2 to any</span></span>
    
     - <span data-ttu-id="cd509-124">Qualquer um para 2</span><span class="sxs-lookup"><span data-stu-id="cd509-124">Any to 2</span></span>
    
     - <span data-ttu-id="cd509-125">3 para qualquer um</span><span class="sxs-lookup"><span data-stu-id="cd509-125">3 to any</span></span>
    
     - <span data-ttu-id="cd509-126">Qualquer um a 3</span><span class="sxs-lookup"><span data-stu-id="cd509-126">Any to 3</span></span>
    
5. <span data-ttu-id="cd509-127">Reinicie o pool digitando o cmdlet a seguir</span><span class="sxs-lookup"><span data-stu-id="cd509-127">Restart the pool by typing the following cmdlet</span></span>
    
   ```PowerShell
   Start-CsPool
   ```

## <a name="patch-or-update-front-end-servers"></a><span data-ttu-id="cd509-128">Corrigir ou atualizar servidores front-end</span><span class="sxs-lookup"><span data-stu-id="cd509-128">Patch or update Front End Servers</span></span>

<span data-ttu-id="cd509-129">Ao corrigir os servidores em um pool de Front-End, você faz isso um servidor por vez.</span><span class="sxs-lookup"><span data-stu-id="cd509-129">When you patch the servers in a Front End pool, you do so one server at a time.</span></span> 
  
### <a name="to-apply-an-upgrade-to-the-front-end-servers-in-a-pool"></a><span data-ttu-id="cd509-130">Para aplicar uma atualização aos servidores front-end em um pool</span><span class="sxs-lookup"><span data-stu-id="cd509-130">To apply an upgrade to the Front End servers in a pool</span></span>

1. <span data-ttu-id="cd509-131">Digite o seguinte cmdlet:</span><span class="sxs-lookup"><span data-stu-id="cd509-131">Type the following cmdlet:</span></span>
    
   ```PowerShell
   Get-CsPoolFabricState -PoolFqdn <PoolFQDN>
   ```

     <span data-ttu-id="cd509-132">Se esse cmdlet mostrar alguma réplica ausente, execute o cmdlet a seguir para recuperar o pool antes de aplicar quaisquer patches.</span><span class="sxs-lookup"><span data-stu-id="cd509-132">If this cmdlet shows any missing replicas, then run the following cmdlet to recover the pool before you apply any patches.</span></span>
    
   ```PowerShell
   Reset-CsPoolRegistrarState -ResetType QuorumLossRecovery
   ```

2. <span data-ttu-id="cd509-133">No primeiro servidor que você deseja corrigir, execute o seguinte cmdlet:</span><span class="sxs-lookup"><span data-stu-id="cd509-133">On the first server you want to patch, run the following cmdlet:</span></span>
    
   ```PowerShell
   Invoke-CsComputerFailOver -ComputerName <Front End Server to be patched>
   ```

    <span data-ttu-id="cd509-134">Este cmdlet move todos os serviços para outros Servidores front-end no pool e leva esse servidor offline.</span><span class="sxs-lookup"><span data-stu-id="cd509-134">This cmdlet moves all services to other Front End Servers in the pool, and takes this server offline.</span></span>
    
3. <span data-ttu-id="cd509-135">Aplique a atualização ou o patch a este servidor.</span><span class="sxs-lookup"><span data-stu-id="cd509-135">Apply the upgrade or patch to this server.</span></span>
    
4. <span data-ttu-id="cd509-136">No servidor atualizado, execute o seguinte cmdlet:</span><span class="sxs-lookup"><span data-stu-id="cd509-136">On the upgraded server, run the following cmdlet:</span></span>
    
   ```PowerShell
   Invoke-CsComputerFailBack -ComputerName <Front End Server to be patched>
   ```

    <span data-ttu-id="cd509-137">O servidor é retornado ao serviço.</span><span class="sxs-lookup"><span data-stu-id="cd509-137">The server is returned to service.</span></span>
    
5. <span data-ttu-id="cd509-138">Repita as etapas 2 a 4 para cada servidor que precisa ser atualizado.</span><span class="sxs-lookup"><span data-stu-id="cd509-138">Repeat Steps 2-4 for each server that needs to be upgraded.</span></span>
    
