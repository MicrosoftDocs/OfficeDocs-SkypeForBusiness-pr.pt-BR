---
title: Gerenciar servidores de front-end no Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: ab748733-6bad-4c93-8dda-db8d5271653d
description: 'Resumo: saiba como adicionar, remover, corrigir ou atualizar servidores front-end no Skype for Business Server.'
ms.openlocfilehash: 3d2298711e707ed897b26939fd383dbedcfb3957
ms.sourcegitcommit: 397c4840fb053238de24b8b24ae75588b33b693d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/10/2020
ms.locfileid: "45098409"
---
# <a name="manage-front-end-servers-in-skype-for-business-server"></a>Gerenciar servidores de front-end no Skype for Business Server
 
Este artigo explica como adicionar ou remover servidores de front-end e como aplicar atualizações ou patches a servidores front-end.

  > [!NOTE]
> O Skype for Business Server 2019 não é compatível com os pools de front-ends Enterprise Edition com dois servidores front-end e não permitirá que a topologia seja publicada nesse cenário.

## <a name="add-or-remove-front-end-servers"></a>Adicionar ou remover servidores de front-end
  
Ao adicionar um servidor de Front End a um pool, ou remover um servidor de Front End de um pool, você precisará reiniciar o pool. 
  
> [!IMPORTANT]
> Quando você adiciona ou remove um servidor para o pool na sua topologia e, em seguida, publica a topologia atualizada, ele fará com que todos os servidores do pool reiniciem ao mesmo tempo. Enquanto os servidores estão reiniciando o pool está offline, o que interromperá o serviço de seus usuários conectados a esse pool. Para evitar qualquer interrupção do serviço para os usuários, planeje a publicação da topologia com o novo servidor no pool fora do horário comercial. 
  
Você pode usar o procedimento a seguir ao adicionar ou remover um servidor front-end.
  
> [!NOTE]
> Se você estiver adicionando novos servidores ao pool, atualize seus servidores de pool novos para que estejam no mesmo nível de atualização cumulativa que os servidores existentes no pool. 
  
### <a name="to-add-or-remove-front-end-servers"></a>Para adicionar ou remover servidores de front-end

1. Se estiver removendo servidores de Front End, primeiro interrompa novas conexões a esses servidores. Para fazer isso, é possível usar o seguinte cmdlet:
    
   ```PowerShell
   Stop-CsWindowsService -Graceful
   ```

2. Abra o Construtor de Topologias, e adiciona ou remova os servidores necessários. 
    
3. Publique a topologia.
    
    > [!IMPORTANT]
    > Quando você adiciona ou remove um servidor para o pool na sua topologia e, em seguida, publica a topologia atualizada, ele fará com que todos os servidores do pool reiniciem ao mesmo tempo. Enquanto os servidores estão reiniciando o pool está offline, o que interromperá o serviço de seus usuários conectados a esse pool. Para evitar qualquer interrupção do serviço para os usuários, planeje a publicação da topologia com o novo servidor no pool fora do horário comercial. 
  
  > [!NOTE]
> Além disso, ao adicionar ou remover um servidor para o pool, você deve executar o assistente de implantação do Skype for Business Server em cada computador adicionado ou removido, para obter mais informações, consulte [instalar o Skype for Business Server em servidores na topologia](https://docs.microsoft.com/skypeforbusiness/deploy/install/install-skype-for-business-server)
  
4. Se você tiver alterado o número de servidores em seu pool de front-ends de uma das seguintes maneiras, redefina o pool com digitando o seguinte cmdlet: Reset-CsPoolRegistrarState-Resettype FullReset-PoolFqdn 
    
   ```PowerShell
    Reset-CsPoolRegistrarState -ResetType FullReset -PoolFqdn  <PoolFQDN>
   ```

     - 2 para qualquer
    
     - Qualquer para 2
    
     - 3 para qualquer
    
     - Qualquer para 3
    
5. Reinicie o pool digitando o seguinte cmdlet
    
   ```PowerShell
   Start-CsPool
   ```

## <a name="patch-or-update-front-end-servers"></a>Corrigir ou atualizar servidores front-end

Ao corrigir os servidores em um pool de front-ends, faça isso um servidor de cada vez. 
  
### <a name="to-apply-an-upgrade-to-the-front-end-servers-in-a-pool"></a>Para aplicar uma atualização aos servidores front-end em um pool

1. Digite o seguinte cmdlet:
    
   ```PowerShell
   Get-CsPoolFabricState -PoolFqdn <PoolFQDN>
   ```

     Se este cmdlet mostrar qualquer réplica ausente, execute o seguinte cmdlet para recuperar o pool antes de aplicar qualquer patch.
    
   ```PowerShell
   Reset-CsPoolRegistrarState -ResetType QuorumLossRecovery
   ```

2. No primeiro servidor que você deseja corrigir, execute o seguinte cmdlet:
    
   ```PowerShell
   Invoke-CsComputerFailOver -ComputerName <Front End Server to be patched>
   ```

    Este cmdlet Move todos os serviços para outros servidores front-end no pool e coloca este servidor offline.
    
3. Aplique a atualização ou patch para este servidor.
    
4. No servidor atualizado, execute o seguinte cmdlet:
    
   ```PowerShell
   Invoke-CsComputerFailBack -ComputerName <Front End Server to be patched>
   ```

    O servidor retorna ao serviço.
    
5. Repita as etapas 2-4 para cada servidor que precisa ser atualizado.
    
