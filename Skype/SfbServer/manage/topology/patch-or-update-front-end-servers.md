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
# <a name="patch-or-update-front-end-servers-in-skype-for-business-server"></a>Patch ou atualização de servidores Front-End do Skype para Business Server
 
**Resumo:** Saiba como aplicar atualizações ou patches para servidores Front-End do Skype para Business Server.
  
Quando você os servidores em um pool de Front-End de patch, você fazer isso um servidor de cada vez. 
  
### <a name="to-apply-an-upgrade-to-the-front-end-servers-in-a-pool"></a>Para aplicar uma atualização aos servidores Front-End em um pool

1. Digite o seguinte cmdlet:
    
   ```
   Get-CsPoolFabricState -PoolFqdn <PoolFQDN>
   ```

     Se este cmdlet mostrar qualquer réplica ausente, execute o seguinte cmdlet para recuperar o pool antes de aplicar qualquer patch.
    
   ```
   Reset-CsPoolRegistrarState -ResetType QuorumLossRecovery
   ```

2. No primeiro servidor a ser corrigido, execute o seguinte cmdlet:
    
   ```
   Invoke-CsComputerFailOver -ComputerName <Front End Server to be patched>
   ```

    Este cmdlet Move todos os serviços para outros servidores Front-End no pool e deixa este servidor offline.
    
3. Aplique a atualização ou correção neste servidor.
    
4. No servidor atualizado, execute o seguinte cmdlet:
    
   ```
   Invoke-CsComputerFailBack -ComputerName <Front End Server to be patched>
   ```

    O servidor voltará ao serviço.
    
5. Repita as etapas 2 a 4 para cada servidor que precisar ser atualizado.
    

