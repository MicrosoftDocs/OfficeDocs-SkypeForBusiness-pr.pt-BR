---
title: Adicionar ou remover um Servidor Front-End no Skype for Business Server 2015
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 7/12/2016
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: ab748733-6bad-4c93-8dda-db8d5271653d
description: 'Resumo: Saiba como adicionar ou remover servidores Front-End no Skype para Business Server.'
ms.openlocfilehash: 80b0dab56d3adfb08856348b7ec749ef2e91079f
ms.sourcegitcommit: a79668bb45b73a63bea5c249d76a4c4c2530a096
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/05/2018
ms.locfileid: "19569003"
---
# <a name="add-or-remove-a-front-end-server-in-skype-for-business-server-2015"></a><span data-ttu-id="52e85-103">Adicionar ou remover um Servidor Front-End no Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="52e85-103">Add or remove a Front End Server in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="52e85-104">**Resumo:** Saiba como adicionar ou remover servidores Front-End no Skype para Business Server.</span><span class="sxs-lookup"><span data-stu-id="52e85-104">**Summary:** Learn how to add or remove Front End Servers in Skype for Business Server.</span></span>
  
<span data-ttu-id="52e85-105">Quando você adicionar um servidor Front-End a um pool ou remove um servidor Front-End de um pool, em seguida, você precisará reiniciar o pool.</span><span class="sxs-lookup"><span data-stu-id="52e85-105">When you add a Front End Server to a pool, or remove a Front End Server from a pool, you then need to restart the pool.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="52e85-p101">Ao adicionar ou remover um servidor do pool em sua topologia e depois publicar a topologia atualizada, todos os servidores no pool serão reiniciados ao mesmo tempo. Durante a reinicialização dos servidores, o pool permanece offline, o que interrompe o serviço para os usuários conectados a esse pool. Para evitar a interrupção do serviço para os usuários, planeje a publicação da topologia com o novo servidor no pool fora do horário comercial.</span><span class="sxs-lookup"><span data-stu-id="52e85-p101">When you add or remove a server to the pool in your topology and then publish the updated topology, it will cause all of the servers in the pool to restart at the same time. While the servers are restarting the pool is offline, which will interrupt service for your users connected to that pool. To prevent any interruption of service to users, plan to publish the topology with the new server in the pool during non-business hours.</span></span> 
  
<span data-ttu-id="52e85-109">Você pode usar o procedimento a seguir, quando a adição ou remoção de um servidor Front-End.</span><span class="sxs-lookup"><span data-stu-id="52e85-109">You can use the following procedure when adding or removing a Front End Server.</span></span>
  
> [!NOTE]
> <span data-ttu-id="52e85-110">Se estiver adicionando novos servidores ao pool, atualize os novos servidores do pool no mesmo nível de Atualização Cumulativa dos servidores existentes no Pool.</span><span class="sxs-lookup"><span data-stu-id="52e85-110">If you're adding new servers to the pool, update your new pool servers to be at the same Cumulative Update level as the existing servers in the Pool.</span></span> 
  
### <a name="to-add-or-remove-front-end-servers"></a><span data-ttu-id="52e85-111">Para adicionar ou remover servidores Front-End</span><span class="sxs-lookup"><span data-stu-id="52e85-111">To add or remove Front End Servers</span></span>

1. <span data-ttu-id="52e85-112">Se você estiver removendo quaisquer servidores Front-End, primeiro interrompa novas conexões para esses servidores.</span><span class="sxs-lookup"><span data-stu-id="52e85-112">If you are removing any Front End Servers, first stop new connections to those servers.</span></span> <span data-ttu-id="52e85-113">Para fazer isso, é possível usar o seguinte cmdlet:</span><span class="sxs-lookup"><span data-stu-id="52e85-113">To do so, you can use the following cmdlet:</span></span>
    
   ```
   Stop-CsWindowsService -Graceful
   ```

2. <span data-ttu-id="52e85-114">Abra o construtor de topologias e adicionar ou remover os servidores necessários.</span><span class="sxs-lookup"><span data-stu-id="52e85-114">Open Topology Builder, and add or remove the necessary servers.</span></span> 
    
3. <span data-ttu-id="52e85-115">Publique a topologia.</span><span class="sxs-lookup"><span data-stu-id="52e85-115">Publish the topology.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="52e85-p103">Ao adicionar ou remover um servidor do pool em sua topologia e depois publicar a topologia atualizada, todos os servidores no pool serão reiniciados ao mesmo tempo. Durante a reinicialização dos servidores, o pool permanece offline, o que interrompe o serviço para os usuários conectados a esse pool. Para evitar a interrupção do serviço para os usuários, planeje a publicação da topologia com o novo servidor no pool fora do horário comercial.</span><span class="sxs-lookup"><span data-stu-id="52e85-p103">When you add or remove a server to the pool in your topology and then publish the updated topology, it will cause all of the servers in the pool to restart at the same time. While the servers are restarting the pool is offline, which will interrupt service for your users connected to that pool. To prevent any interruption of service to users, plan to publish the topology with the new server in the pool during non-business hours.</span></span> 
  
4. <span data-ttu-id="52e85-119">Se você tiver alterado o número de servidores em seu pool de Front-End em qualquer uma das seguintes maneiras, redefinir o pool com digitando o seguinte cmdlet: Reset-CsPoolRegistrarState - ResetType FullReset - PoolFqdn</span><span class="sxs-lookup"><span data-stu-id="52e85-119">If you have changed the number of servers in your Front End pool in any of the following ways, then reset the pool with by typing the following cmdlet: Reset-CsPoolRegistrarState -ResetType FullReset -PoolFqdn</span></span> 
    
   ```
    Reset-CsPoolRegistrarState -ResetType FullReset -PoolFqdn  <PoolFQDN>
   ```

     - <span data-ttu-id="52e85-120">2 para qualquer número</span><span class="sxs-lookup"><span data-stu-id="52e85-120">2 to any</span></span>
    
     - <span data-ttu-id="52e85-121">Qualquer número para 2</span><span class="sxs-lookup"><span data-stu-id="52e85-121">Any to 2</span></span>
    
     - <span data-ttu-id="52e85-122">3 para qualquer número</span><span class="sxs-lookup"><span data-stu-id="52e85-122">3 to any</span></span>
    
     - <span data-ttu-id="52e85-123">Qualquer número para 3</span><span class="sxs-lookup"><span data-stu-id="52e85-123">Any to 3</span></span>
    
5. <span data-ttu-id="52e85-124">Reinicie o pool digitando o seguinte cmdlet</span><span class="sxs-lookup"><span data-stu-id="52e85-124">Restart the pool by typing the following cmdlet</span></span>
    
   ```
   Start-CsPool
   ```