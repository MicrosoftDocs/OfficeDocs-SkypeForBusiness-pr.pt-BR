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
ms.sourcegitcommit: 70d3a3b162fdbca1cf2c2713d6bce54c3cbad3bd
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/02/2019
ms.locfileid: "31026178"
---
# <a name="manage-front-end-servers-in-skype-for-business-server"></a>Gerenciar servidores de Front-End em Skype para Business Server
 
Este artigo explica como adicionar ou remover servidores Front-End e como aplicar atualizações ou patches para servidores Front-End.

## <a name="add-or-remove-front-end-servers"></a>Adicionar ou remover servidores Front-End
  
Quando você adicionar um servidor Front-End a um pool ou remove um servidor Front-End de um pool, em seguida, você precisará reiniciar o pool. 
  
> [!IMPORTANT]
> Ao adicionar ou remover um servidor do pool em sua topologia e depois publicar a topologia atualizada, todos os servidores no pool serão reiniciados ao mesmo tempo. Durante a reinicialização dos servidores, o pool permanece offline, o que interrompe o serviço para os usuários conectados a esse pool. Para evitar a interrupção do serviço para os usuários, planeje a publicação da topologia com o novo servidor no pool fora do horário comercial. 
  
Você pode usar o procedimento a seguir, quando a adição ou remoção de um servidor Front-End.
  
> [!NOTE]
> Se estiver adicionando novos servidores ao pool, atualize os novos servidores do pool no mesmo nível de Atualização Cumulativa dos servidores existentes no Pool. 
  
### <a name="to-add-or-remove-front-end-servers"></a>Para adicionar ou remover servidores Front-End

1. Se você estiver removendo quaisquer servidores Front-End, primeiro interrompa novas conexões para esses servidores. Para fazer isso, é possível usar o seguinte cmdlet:
    
   ```
   Stop-CsWindowsService -Graceful
   ```

2. Abra o construtor de topologias e adicionar ou remover os servidores necessários. 
    
3. Publique a topologia.
    
    > [!IMPORTANT]
    > Ao adicionar ou remover um servidor do pool em sua topologia e depois publicar a topologia atualizada, todos os servidores no pool serão reiniciados ao mesmo tempo. Durante a reinicialização dos servidores, o pool permanece offline, o que interrompe o serviço para os usuários conectados a esse pool. Para evitar a interrupção do serviço para os usuários, planeje a publicação da topologia com o novo servidor no pool fora do horário comercial. 
  
  > [!NOTE]
> Além disso, quando você adicionar ou remove um servidor ao pool, você deve executar o Skype para o Assistente de implantação de servidor de negócios em cada computador adicionado ou removido, para obter mais informações, consulte [Instalar Skype para Business Server nos servidores na topologia](https://docs.microsoft.com/skypeforbusiness/deploy/install/install-skype-for-business-server)
  
4. Se você tiver alterado o número de servidores em seu pool de Front-End em qualquer uma das seguintes maneiras, redefinir o pool com digitando o seguinte cmdlet: Reset-CsPoolRegistrarState - ResetType FullReset - PoolFqdn 
    
   ```
    Reset-CsPoolRegistrarState -ResetType FullReset -PoolFqdn  <PoolFQDN>
   ```

     - 2 para qualquer número
    
     - Qualquer número para 2
    
     - 3 para qualquer número
    
     - Qualquer número para 3
    
5. Reinicie o pool digitando o seguinte cmdlet
    
   ```
   Start-CsPool
   ```

## <a name="patch-or-update-front-end-servers"></a>Corrigir ou atualizar Servidores Front-End

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
    
