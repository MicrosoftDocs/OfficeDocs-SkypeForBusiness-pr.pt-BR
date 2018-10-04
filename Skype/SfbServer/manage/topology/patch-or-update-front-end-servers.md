---
title: Patch ou atualização de servidores Front-End do Skype para Business Server
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 20fa39ae-ecfb-4c72-9cc4-8e183d3c752f
description: 'Resumo: Saiba como aplicar atualizações ou patches a servidores Front-End do Skype para Business Server.'
ms.openlocfilehash: cf209159391ef084d77b5adc639698ed766427ff
ms.sourcegitcommit: dd37c12a0312270955755ab2826adcfbae813790
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/04/2018
ms.locfileid: "25371714"
---
# <a name="patch-or-update-front-end-servers-in-skype-for-business-server"></a><span data-ttu-id="7191b-103">Patch ou atualização de servidores Front-End do Skype para Business Server</span><span class="sxs-lookup"><span data-stu-id="7191b-103">Patch or update Front End Servers in Skype for Business Server</span></span>
 
<span data-ttu-id="7191b-104">**Resumo:** Saiba como aplicar atualizações ou patches para servidores Front-End do Skype para Business Server.</span><span class="sxs-lookup"><span data-stu-id="7191b-104">**Summary:** learn how to apply upgrades or patches to Front End Servers in Skype for Business Server.</span></span>
  
<span data-ttu-id="7191b-105">Quando você os servidores em um pool de Front-End de patch, você fazer isso um servidor de cada vez.</span><span class="sxs-lookup"><span data-stu-id="7191b-105">When you patch the servers in a Front End pool, you do so one server at a time.</span></span> 
  
### <a name="to-apply-an-upgrade-to-the-front-end-servers-in-a-pool"></a><span data-ttu-id="7191b-106">Para aplicar uma atualização aos servidores Front-End em um pool</span><span class="sxs-lookup"><span data-stu-id="7191b-106">To apply an upgrade to the Front End servers in a pool</span></span>

1. <span data-ttu-id="7191b-107">Digite o seguinte cmdlet:</span><span class="sxs-lookup"><span data-stu-id="7191b-107">Type the following cmdlet:</span></span>
    
   ```
   Get-CsPoolFabricState -PoolFqdn <PoolFQDN>
   ```

     <span data-ttu-id="7191b-108">Se este cmdlet mostrar qualquer réplica ausente, execute o seguinte cmdlet para recuperar o pool antes de aplicar qualquer patch.</span><span class="sxs-lookup"><span data-stu-id="7191b-108">If this cmdlet shows any missing replicas, then run the following cmdlet to recover the pool before you apply any patches.</span></span>
    
   ```
   Reset-CsPoolRegistrarState -ResetType QuorumLossRecovery
   ```

2. <span data-ttu-id="7191b-109">No primeiro servidor a ser corrigido, execute o seguinte cmdlet:</span><span class="sxs-lookup"><span data-stu-id="7191b-109">On the first server you want to patch, run the following cmdlet:</span></span>
    
   ```
   Invoke-CsComputerFailOver -ComputerName <Front End Server to be patched>
   ```

    <span data-ttu-id="7191b-110">Este cmdlet Move todos os serviços para outros servidores Front-End no pool e deixa este servidor offline.</span><span class="sxs-lookup"><span data-stu-id="7191b-110">This cmdlet moves all services to other Front End Servers in the pool, and takes this server offline.</span></span>
    
3. <span data-ttu-id="7191b-111">Aplique a atualização ou correção neste servidor.</span><span class="sxs-lookup"><span data-stu-id="7191b-111">Apply the upgrade or patch to this server.</span></span>
    
4. <span data-ttu-id="7191b-112">No servidor atualizado, execute o seguinte cmdlet:</span><span class="sxs-lookup"><span data-stu-id="7191b-112">On the upgraded server, run the following cmdlet:</span></span>
    
   ```
   Invoke-CsComputerFailBack -ComputerName <Front End Server to be patched>
   ```

    <span data-ttu-id="7191b-113">O servidor voltará ao serviço.</span><span class="sxs-lookup"><span data-stu-id="7191b-113">The server is returned to service.</span></span>
    
5. <span data-ttu-id="7191b-114">Repita as etapas 2 a 4 para cada servidor que precisar ser atualizado.</span><span class="sxs-lookup"><span data-stu-id="7191b-114">Repeat Steps 2-4 for each server that needs to be upgraded.</span></span>
    

