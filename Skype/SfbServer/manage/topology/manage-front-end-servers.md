---
title: Gerenciar servidores de front-end no Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: ab748733-6bad-4c93-8dda-db8d5271653d
description: 'Resumo: saiba como adicionar, remover, corrigir ou atualizar servidores front-end no Skype for Business Server.'
ms.openlocfilehash: 13af9198dfb83d14ad1d86885419fc9add29e07d
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34275154"
---
# <a name="manage-front-end-servers-in-skype-for-business-server"></a>Gerenciar servidores de front-end no Skype for Business Server
 
Este artigo explica como adicionar ou remover servidores de front-end e como aplicar atualizações ou patches a servidores front-end.

## <a name="add-or-remove-front-end-servers"></a>Adicionar ou remover servidores de front-end
  
Ao adicionar um servidor front-end a um pool ou remover um servidor front-end de um pool, você precisará reiniciar o pool. 
  
> [!IMPORTANT]
> Ao adicionar ou remover um servidor do pool em sua topologia e depois publicar a topologia atualizada, todos os servidores no pool serão reiniciados ao mesmo tempo. Durante a reinicialização dos servidores, o pool permanece offline, o que interrompe o serviço para os usuários conectados a esse pool. Para evitar a interrupção do serviço para os usuários, planeje a publicação da topologia com o novo servidor no pool fora do horário comercial. 
  
Você pode usar o procedimento a seguir ao adicionar ou remover um servidor front-end.
  
> [!NOTE]
> Se estiver adicionando novos servidores ao pool, atualize os novos servidores do pool no mesmo nível de Atualização Cumulativa dos servidores existentes no Pool. 
  
### <a name="to-add-or-remove-front-end-servers"></a>Para adicionar ou remover servidores de front-end

1. Se você estiver removendo qualquer servidor front-end, primeiro interrompa novas conexões para esses servidores. Para fazer isso, é possível usar o seguinte cmdlet:
    
   ```
   Stop-CsWindowsService -Graceful
   ```

2. Abra o construtor de topologias e adicione ou remova os servidores necessários. 
    
3. Publique a topologia.
    
    > [!IMPORTANT]
    > Ao adicionar ou remover um servidor do pool em sua topologia e depois publicar a topologia atualizada, todos os servidores no pool serão reiniciados ao mesmo tempo. Durante a reinicialização dos servidores, o pool permanece offline, o que interrompe o serviço para os usuários conectados a esse pool. Para evitar a interrupção do serviço para os usuários, planeje a publicação da topologia com o novo servidor no pool fora do horário comercial. 
  
  > [!NOTE]
> Além disso, ao adicionar ou remover um servidor para o pool, você deve executar o assistente de implantação do Skype for Business Server em cada computador adicionado ou removido para obter mais informações, consulte [instalar o Skype for Business Server em servidores na topologia](https://docs.microsoft.com/skypeforbusiness/deploy/install/install-skype-for-business-server)
  
4. Se você alterou o número de servidores em seu pool de front-ends de qualquer uma das seguintes maneiras, redefina o pool com digitando o seguinte cmdlet: Reset-CsPoolRegistrarState-Resettype FullReset-PoolFqdn 
    
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

Ao corrigir os servidores em um pool Front-end, você faz isso em um servidor de cada vez. 
  
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

    Esse cmdlet Move todos os serviços para outros servidores front-end no pool e coloca este servidor offline.
    
3. Aplique a atualização ou correção neste servidor.
    
4. No servidor atualizado, execute o seguinte cmdlet:
    
   ```
   Invoke-CsComputerFailBack -ComputerName <Front End Server to be patched>
   ```

    O servidor voltará ao serviço.
    
5. Repita as etapas 2 a 4 para cada servidor que precisar ser atualizado.
    
