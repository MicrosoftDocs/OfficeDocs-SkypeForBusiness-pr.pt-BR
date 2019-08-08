---
title: Gerenciar contas do Sistema de Salas do Skype
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.reviewer: davgroom
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 7b389efc-9685-42e9-9504-be437d20ff57
ms.collection: M365-voice
description: Leia este tópico para saber como gerenciar as contas do Sistema de Salas do Skype.
ms.openlocfilehash: 2a45fc8507b9b09b777e6aa91c47fff2b3dfc3d2
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/07/2019
ms.locfileid: "36234070"
---
# <a name="manage-skype-room-system-accounts"></a>Gerenciar contas do Sistema de Salas do Skype
 
Leia este tópico para saber como gerenciar as contas do Sistema de Salas do Skype. 

> [!NOTE]
> As salas do Microsoft Teams é um produto diferente com diferentes dependências e procedimentos de implantação. Para obter informações sobre as salas do Microsoft Teams, consulte a [visão geral do gerenciamento](../../manage/skype-room-systems-v2/skype-room-systems-v2.md)de salas do Microsoft Teams.
  
## <a name="move-the-skype-room-system-account-between-pools"></a>Mover a conta do sistema de sala do Skype entre pools

Se você precisar mover a conta do sistema de sala do Skype de um pool do Skype for Business Server para outro (por exemplo, durante as atualizações), use o seguinte comando para mover o pool de contas do sistema de salas do Skype: 
  
```
Move-CsMeetingRoom -Identity LRS01 -Target "LYNCPool15-2.contoso.com"
```

## <a name="disable-the-skype-room-system-account-for-skype-for-business-services"></a>Desabilitar a conta do sistema de sala do Skype para serviços do Skype for Business

Se você precisar desabilitar uma conta existente do sistema de sala do Skype dos serviços do Skype for Business em um pool de servidores do Skype for Business, use o seguinte comando para desativar a conta: 
  
```
Disable-CsMeetingRoom LRS01 -domaincontroller DC-ND-001.contoso.com
```

## <a name="optional-create-a-skype-room-system-administrator-group-in-active-directory"></a>Opcional: criar um grupo de administradores do sistema de salas do Skype no Active Directory

Cada cliente do sistema da sala do Skype que une o domínio pode ser totalmente gerenciado por um usuário do domínio com direitos de administrador local no PC Appliance do sistema de sala do Skype. Portanto, você pode criar um grupo de administradores dedicados no Active Directory e dar a esses direitos administrativos de grupo durante a configuração do novo computador do sistema de sala do Skype.
  

