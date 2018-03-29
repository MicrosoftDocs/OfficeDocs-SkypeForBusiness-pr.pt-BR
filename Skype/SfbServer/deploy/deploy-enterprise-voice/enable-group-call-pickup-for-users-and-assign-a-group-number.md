---
title: Habilitar o Recebimento de Chamadas em Grupo para usuários e atribuir um número de grupo no Skype for Business 2015
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 8/17/2015
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.custom: Strat_SB_Admin
ms.assetid: c33bb6c2-d43b-4fb6-a0fa-6d82a7b09abe
description: Habilitar usuários para atendimento de chamada do grupo no Skype para Business Server Enterprise Voice e atribua um número de grupo.
ms.openlocfilehash: aaacf080f9e7f7ae7f9bad3f8b13201972d7a72f
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/28/2018
---
# <a name="enable-group-call-pickup-for-users-and-assign-a-group-number-in-skype-for-business-2015"></a>Habilitar o Recebimento de Chamadas em Grupo para usuários e atribuir um número de grupo no Skype for Business 2015
 
Habilitar usuários para atendimento de chamada do grupo no Skype para Business Server Enterprise Voice e atribua um número de grupo.
  
Depois de adicionar os números de retirada de grupo de chamada à tabela de órbita de estacionamento de chamada, você usar a ferramenta de SEFAUtil para atribuir os números de grupo aos usuários e habilitar o atendimento de chamada de grupo para eles.
  
> [!NOTE]
> Em uma implantação híbrida, não atribua um grupo de atendimento de chamada de grupo para usuários hospedados online. Os usuários hospedados online não podem participar de atendimento de chamada do grupo. Isso significa que suas chamadas não podem ser atendidas por outros usuários, e eles não podem responder chamadas no lugar de outros usuários. 
  
### <a name="to-assign-a-group-number-and-enable-group-call-pickup-for-a-user"></a>Para atribuir um número de grupo e habilitar o atendimento de chamada de grupo para um usuário

1. Realize logon no computador em que você instalou a ferramenta SEFAUtil com direitos de administrador.
    
2. Na linha de comando, execute:
    
   ```
   SEFAUtil.exe sip:<sip address of user> /server:<pool FQDN> /enablegrouppickup:<group number>
   ```

    Por exemplo, para atribuir o número de grupo 199 a um usuário:
    
   ```
   SEFAUtil.exe katarina@contoso.com /server:pool01.contoso.com /enablegrouppickup:199 
   ```

## <a name="see-also"></a>Consulte também

#### 

[Desabilitar grupo retirada para usuários](http://technet.microsoft.com/library/91b06f9e-2840-45a2-bbb3-6a29179b9a9f.aspx)

