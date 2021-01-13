---
title: Habilitar o Atendimento de Chamadas em Grupo para usuários e atribuir um número de grupo no Skype for Business
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: c33bb6c2-d43b-4fb6-a0fa-6d82a7b09abe
description: Habilitar usuários para o Atendimento de Chamadas em Grupo no Skype for Business Server Enterprise Voice e atribuir um número de grupo.
ms.openlocfilehash: 3467aea1b9671a93cca2f66a2ac73c39f15dc26e
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49830961"
---
# <a name="enable-group-call-pickup-for-users-and-assign-a-group-number-in-skype-for-business"></a>Habilitar o Atendimento de Chamadas em Grupo para usuários e atribuir um número de grupo no Skype for Business

Habilitar usuários para o Atendimento de Chamadas em Grupo no Skype for Business Server Enterprise Voice e atribuir um número de grupo.

Depois de adicionar números de grupo de atendimento de chamada à tabela de órbita de estacionamento de chamada, use a ferramenta SEFAUtil para atribuir os números de grupo aos usuários e habilitar o Atendimento de Chamada em Grupo para eles.

> [!NOTE]
> Em uma implantação híbrida, não atribua um grupo de Atendimento de Chamada em Grupo aos usuários que estão online. Os usuários que estão online não podem participar do Atendimento de Chamada em Grupo. Ou seja, suas chamadas não podem ser atendidas por outros usuários e não podem atender chamadas a outros usuários.

### <a name="to-assign-a-group-number-and-enable-group-call-pickup-for-a-user"></a>Para atribuir um número de grupo e habilitar o Atendimento de Chamada em Grupo para um usuário

1. Faça logoff no computador em que você instalou a ferramenta SEFAUtil com direitos de administrador.

2. Na linha de comando, execute:

   ```console
   SEFAUtil.exe sip:<sip address of user> /server:<pool FQDN> /enablegrouppickup:<group number>
   ```

    Por exemplo, para atribuir o número de grupo 199 a um usuário:

   ```console
   SEFAUtil.exe katarina@contoso.com /server:pool01.contoso.com /enablegrouppickup:199
   ```

## <a name="see-also"></a>Confira também

[Desabilitar o Retirada em Grupo para Usuários](https://technet.microsoft.com/library/91b06f9e-2840-45a2-bbb3-6a29179b9a9f.aspx)

