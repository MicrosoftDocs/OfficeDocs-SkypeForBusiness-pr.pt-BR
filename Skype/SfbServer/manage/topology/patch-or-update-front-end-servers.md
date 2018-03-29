---
title: Corrigir ou atualizar Servidores Front-End no Skype for Business Server 2015
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 4/4/2016
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 20fa39ae-ecfb-4c72-9cc4-8e183d3c752f
description: 'Resumo: Saiba como aplicar atualizações ou patches a servidores Front-End do Skype para Business Server.'
ms.openlocfilehash: 1f5ccd6531338d1e6b47dd8363b9386bcbeba0fc
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/28/2018
---
# <a name="patch-or-update-front-end-servers-in-skype-for-business-server-2015"></a>Corrigir ou atualizar Servidores Front-End no Skype for Business Server 2015
 
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
    

