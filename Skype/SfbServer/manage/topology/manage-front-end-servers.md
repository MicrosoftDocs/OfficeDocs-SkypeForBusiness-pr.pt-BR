---
title: Gerenciar servidores front-end no Skype for Business Server
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: ab748733-6bad-4c93-8dda-db8d5271653d
description: 'Resumo: saiba como adicionar, remover, corrigir ou atualizar Servidores Front-End no Skype for Business Server.'
ms.openlocfilehash: daa56be66a09d0969c193021aa3b847fc5972413
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/08/2021
ms.locfileid: "60837523"
---
# <a name="manage-front-end-servers-in-skype-for-business-server"></a>Gerenciar servidores front-end no Skype for Business Server
 
Este artigo explica como adicionar ou remover Servidores Front-End e como aplicar atualizações ou patches aos Servidores Front-End.

  > [!NOTE]
> Skype for Business Server 2019 não dá suporte Edição Enterprise pools de Front-End com dois Servidores Front-End e não permitirá que a topologia seja publicada nesse cenário.

## <a name="add-or-remove-front-end-servers"></a>Adicionar ou remover servidores front-end
  
Ao adicionar um servidor de Front End a um pool, ou remover um servidor de Front End de um pool, você precisará reiniciar o pool. 
  
> [!IMPORTANT]
> Quando você adiciona ou remove um servidor ao pool em sua topologia e publica a topologia atualizada, isso fará com que todos os servidores no pool reiniciem ao mesmo tempo. Enquanto os servidores estão reiniciando o pool está offline, o que interromperá o serviço para os usuários conectados a esse pool. Para evitar qualquer interrupção do serviço para os usuários, planeje publicar a topologia com o novo servidor no pool durante o horário não comercial. 
  
Você pode usar o procedimento a seguir ao adicionar ou remover um Servidor Front-End.
  
> [!NOTE]
> Se você estiver adicionando novos servidores ao pool, atualize seus novos servidores de pool para estar no mesmo nível de Atualização Cumulativa que os servidores existentes no Pool. 
  
### <a name="to-add-or-remove-front-end-servers"></a>Para adicionar ou remover servidores front-end

1. Se estiver removendo servidores de Front End, primeiro interrompa novas conexões a esses servidores. Para fazer isso, é possível usar o seguinte cmdlet:
    
   ```PowerShell
   Stop-CsWindowsService -Graceful
   ```

2. Abra o Construtor de Topologias, e adiciona ou remova os servidores necessários. 
    
3. Publique a topologia.
    
    > [!IMPORTANT]
    > Quando você adiciona ou remove um servidor ao pool em sua topologia e publica a topologia atualizada, isso fará com que todos os servidores no pool reiniciem ao mesmo tempo. Enquanto os servidores estão reiniciando o pool está offline, o que interromperá o serviço para os usuários conectados a esse pool. Para evitar qualquer interrupção do serviço para os usuários, planeje publicar a topologia com o novo servidor no pool durante o horário não comercial. 
  
  > [!NOTE]
> Além disso, quando você adiciona ou remove um servidor ao pool, deve executar o Assistente de Implantação Skype for Business Server em cada computador adicionado ou removido, para obter mais informações, consulte Install Skype for Business Server on servers in the [topology](../../deploy/install/install-skype-for-business-server.md)
  
4. Se você tiver alterado o número de servidores em seu pool de Front-End de qualquer uma das seguintes maneiras, redefinir o pool com digitando o seguinte cmdlet: Reset-CsPoolRegistrarState -ResetType FullReset -PoolFqdn 
    
   ```PowerShell
    Reset-CsPoolRegistrarState -ResetType FullReset -PoolFqdn  <PoolFQDN>
   ```

     - 2 para qualquer
    
     - Qualquer a 2
    
     - 3 para qualquer
    
     - Qualquer a 3
    
5. Reinicie o pool digitando o cmdlet a seguir
    
   ```PowerShell
   Start-CsPool
   ```

## <a name="patch-or-update-front-end-servers"></a>Patch ou atualizar servidores front-end

Ao corrigir os servidores em um pool de Front-End, você faz isso um servidor por vez. 
  
### <a name="to-apply-an-upgrade-to-the-front-end-servers-in-a-pool"></a>Para aplicar uma atualização aos servidores Front-End em um pool

1. Digite o seguinte cmdlet:
    
   ```PowerShell
   Get-CsPoolFabricState -PoolFqdn <PoolFQDN>
   ```

     Se este cmdlet mostrar todas as réplicas ausentes, execute o cmdlet a seguir para recuperar o pool antes de aplicar quaisquer patches.
    
   ```PowerShell
   Reset-CsPoolRegistrarState -ResetType QuorumLossRecovery
   ```

2. No primeiro servidor que você deseja corrigir, execute o seguinte cmdlet:
    
   ```PowerShell
   Invoke-CsComputerFailOver -ComputerName <Front End Server to be patched>
   ```

    Esse cmdlet move todos os serviços para outros Servidores Front-End no pool e faz com que esse servidor seja offline.
    
3. Aplique a atualização ou o patch a este servidor.
    
4. No servidor atualizado, execute o seguinte cmdlet:
    
   ```PowerShell
   Invoke-CsComputerFailBack -ComputerName <Front End Server to be patched>
   ```

    O servidor é retornado ao serviço.
    
5. Repita as Etapas 2 a 4 para cada servidor que precisa ser atualizado.
