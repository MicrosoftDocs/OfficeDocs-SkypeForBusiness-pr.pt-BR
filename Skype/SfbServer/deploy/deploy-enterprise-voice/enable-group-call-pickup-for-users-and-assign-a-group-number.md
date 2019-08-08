---
title: Habilitar o recebimento de chamadas em grupo para usuários e atribuir um número de grupo no Skype for Business
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: c33bb6c2-d43b-4fb6-a0fa-6d82a7b09abe
description: Permita que os usuários façam o recebimento de chamadas em grupo no Skype for Business Server Enterprise Voice e atribua um número de grupo.
ms.openlocfilehash: 78bdd78bf7e5bb3a9438a60b54a89664d22666ee
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/07/2019
ms.locfileid: "36240345"
---
# <a name="enable-group-call-pickup-for-users-and-assign-a-group-number-in-skype-for-business"></a>Habilitar o recebimento de chamadas em grupo para usuários e atribuir um número de grupo no Skype for Business

Permita que os usuários façam o recebimento de chamadas em grupo no Skype for Business Server Enterprise Voice e atribua um número de grupo.

Depois de adicionar números de grupo de recebimento de chamada à tabela órbita do parque de chamadas, use a ferramenta SEFAUtil para atribuir os números de grupo aos usuários e habilitar o recebimento de chamadas em grupo para eles.

> [!NOTE]
> Em uma implantação híbrida, não atribua um grupo de recebimento de chamadas em grupo aos usuários que estiverem em casa online. Os usuários que estiverem hospedados online não poderão participar da retirada de chamadas em grupo. Isso significa que suas chamadas não podem ser atendidas por outros usuários, e eles não podem responder chamadas no lugar de outros usuários.

### <a name="to-assign-a-group-number-and-enable-group-call-pickup-for-a-user"></a>Para atribuir um número de grupo e habilitar a retirada de chamadas em grupo para um usuário

1. Realize logon no computador em que você instalou a ferramenta SEFAUtil com direitos de administrador.

2. Na linha de comando, execute:

   ```
   SEFAUtil.exe sip:<sip address of user> /server:<pool FQDN> /enablegrouppickup:<group number>
   ```

    Por exemplo, para atribuir o número de grupo 199 a um usuário:

   ```
   SEFAUtil.exe katarina@contoso.com /server:pool01.contoso.com /enablegrouppickup:199
   ```

## <a name="see-also"></a>Confira também

[Disable Group Pickup for Users](https://technet.microsoft.com/library/91b06f9e-2840-45a2-bbb3-6a29179b9a9f.aspx)

