---
title: Habilitar a Coleta de Chamada de Grupo para usuários e atribuir um número de grupo Skype for Business
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: c33bb6c2-d43b-4fb6-a0fa-6d82a7b09abe
description: Habilita os usuários para a Coleta de Chamada de Grupo Skype for Business Server Enterprise Voice e atribua um número de grupo.
ms.openlocfilehash: c053ae4551ea5954f15261755c20afbf8a45f7b5
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/04/2021
ms.locfileid: "60759084"
---
# <a name="enable-group-call-pickup-for-users-and-assign-a-group-number-in-skype-for-business"></a>Habilitar a Coleta de Chamada de Grupo para usuários e atribuir um número de grupo Skype for Business

Habilita os usuários para a Coleta de Chamada de Grupo Skype for Business Server Enterprise Voice e atribua um número de grupo.

Depois de adicionar números de grupo de retirada de chamada à tabela de órbita do estacionamento de chamada, use a ferramenta SEFAUtil para atribuir os números de grupo aos usuários e habilitar a Coleta de Chamada de Grupo para eles.

> [!NOTE]
> Em uma implantação híbrida, não atribua um grupo de Retirada de Chamada de Grupo aos usuários que estão em casa online. Os usuários que estão em casa online não podem participar da Coleta de Chamada de Grupo. Ou seja, suas chamadas não podem ser atendidas por outros usuários e não podem atender chamadas a outros usuários.

### <a name="to-assign-a-group-number-and-enable-group-call-pickup-for-a-user"></a>Para atribuir um número de grupo e habilitar a Coleta de Chamada de Grupo para um usuário

1. Faça logoff no computador onde você instalou a ferramenta SEFAUtil com direitos de administrador.

2. Na linha de comando, execute:

   ```console
   SEFAUtil.exe sip:<sip address of user> /server:<pool FQDN> /enablegrouppickup:<group number>
   ```

    Por exemplo, para atribuir o número de grupo 199 a um usuário:

   ```console
   SEFAUtil.exe katarina@contoso.com /server:pool01.contoso.com /enablegrouppickup:199
   ```

## <a name="see-also"></a>Confira também

[Desabilitar a coleta de grupo para usuários](/previous-versions/office/lync-server-2013/lync-server-2013-disable-group-call-pickup-for-users)