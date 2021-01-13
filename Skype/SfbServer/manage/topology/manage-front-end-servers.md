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
# <a name="manage-front-end-servers-in-skype-for-business-server"></a>Gerenciar servidores front-end no Skype for Business Server
 
Este artigo explica como adicionar ou remover servidores front-end e como aplicar atualizações ou patches aos Servidores Front-End.

  > [!NOTE]
> O Skype for Business Server 2019 não dá suporte a pools de Front End Enterprise Edition com dois Servidores Front-End e não permitirá que a topologia seja publicada nesse cenário.

## <a name="add-or-remove-front-end-servers"></a>Adicionar ou remover servidores front-end
  
Ao adicionar um servidor de Front End a um pool, ou remover um servidor de Front End de um pool, você precisará reiniciar o pool. 
  
> [!IMPORTANT]
> Quando você adiciona ou remove um servidor ao pool em sua topologia e publica a topologia atualizada, isso fará com que todos os servidores no pool reiniciem ao mesmo tempo. Enquanto os servidores estão reiniciando o pool está offline, o que interromperá o serviço para os usuários conectados a esse pool. Para evitar qualquer interrupção do serviço para os usuários, planeje publicar a topologia com o novo servidor no pool fora do horário comercial. 
  
Você pode usar o procedimento a seguir ao adicionar ou remover um Servidor Front-End.
  
> [!NOTE]
> Se você estiver adicionando novos servidores ao pool, atualize os novos servidores do pool para que eles sejam atualizados no mesmo nível da Atualização Cumulativa que os servidores existentes no Pool. 
  
### <a name="to-add-or-remove-front-end-servers"></a>Para adicionar ou remover servidores front-end

1. Se estiver removendo servidores de Front End, primeiro interrompa novas conexões a esses servidores. Para fazer isso, é possível usar o seguinte cmdlet:
    
   ```PowerShell
   Stop-CsWindowsService -Graceful
   ```

2. Abra o Construtor de Topologias, e adiciona ou remova os servidores necessários. 
    
3. Publique a topologia.
    
    > [!IMPORTANT]
    > Quando você adiciona ou remove um servidor ao pool em sua topologia e publica a topologia atualizada, isso fará com que todos os servidores no pool reiniciem ao mesmo tempo. Enquanto os servidores estão reiniciando o pool está offline, o que interromperá o serviço para os usuários conectados a esse pool. Para evitar qualquer interrupção do serviço para os usuários, planeje publicar a topologia com o novo servidor no pool fora do horário comercial. 
  
  > [!NOTE]
> Além disso, quando você adiciona ou remove um servidor ao pool, deve executar o Assistente de Implantação do Skype for Business Server em cada computador adicionado ou removido. Para obter mais informações, consulte Instalar o Skype for Business Server em servidores da [topologia](https://docs.microsoft.com/skypeforbusiness/deploy/install/install-skype-for-business-server)
  
4. Se você tiver alterado o número de servidores em seu pool de Front-End de qualquer uma das maneiras a seguir, redefinir o pool digitando o seguinte cmdlet: Reset-CsPoolRegistrarState -ResetType FullReset -PoolFqdn 
    
   ```PowerShell
    Reset-CsPoolRegistrarState -ResetType FullReset -PoolFqdn  <PoolFQDN>
   ```

     - 2 para qualquer um
    
     - Qualquer um para 2
    
     - 3 para qualquer um
    
     - Qualquer um a 3
    
5. Reinicie o pool digitando o cmdlet a seguir
    
   ```PowerShell
   Start-CsPool
   ```

## <a name="patch-or-update-front-end-servers"></a>Corrigir ou atualizar servidores front-end

Ao corrigir os servidores em um pool de Front-End, você faz isso um servidor por vez. 
  
### <a name="to-apply-an-upgrade-to-the-front-end-servers-in-a-pool"></a>Para aplicar uma atualização aos servidores front-end em um pool

1. Digite o seguinte cmdlet:
    
   ```PowerShell
   Get-CsPoolFabricState -PoolFqdn <PoolFQDN>
   ```

     Se esse cmdlet mostrar alguma réplica ausente, execute o cmdlet a seguir para recuperar o pool antes de aplicar quaisquer patches.
    
   ```PowerShell
   Reset-CsPoolRegistrarState -ResetType QuorumLossRecovery
   ```

2. No primeiro servidor que você deseja corrigir, execute o seguinte cmdlet:
    
   ```PowerShell
   Invoke-CsComputerFailOver -ComputerName <Front End Server to be patched>
   ```

    Este cmdlet move todos os serviços para outros Servidores front-end no pool e leva esse servidor offline.
    
3. Aplique a atualização ou o patch a este servidor.
    
4. No servidor atualizado, execute o seguinte cmdlet:
    
   ```PowerShell
   Invoke-CsComputerFailBack -ComputerName <Front End Server to be patched>
   ```

    O servidor é retornado ao serviço.
    
5. Repita as etapas 2 a 4 para cada servidor que precisa ser atualizado.
    
