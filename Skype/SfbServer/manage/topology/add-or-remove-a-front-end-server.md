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
ms.openlocfilehash: aed52becf5d4cc97307f9788a81f8d6563d1d25d
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/28/2018
---
# <a name="add-or-remove-a-front-end-server-in-skype-for-business-server-2015"></a>Adicionar ou remover um Servidor Front-End no Skype for Business Server 2015
 
**Resumo:** Saiba como adicionar ou remover servidores Front-End no Skype para Business Server.
  
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


