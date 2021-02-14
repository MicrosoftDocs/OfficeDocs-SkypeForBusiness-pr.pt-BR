---
title: Gerenciar contas do Sistema de Salas Skype
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.reviewer: sohailta
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 7b389efc-9685-42e9-9504-be437d20ff57
ms.collection: M365-voice
description: Leia este tópico para saber como gerenciar contas do Sistema de Sala do Skype.
ms.openlocfilehash: fe6438934fa8fffabbc73c96ac00fd7844b51e14
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49805551"
---
# <a name="manage-skype-room-system-accounts"></a>Gerenciar contas do Sistema de Salas Skype
 
Leia este tópico para saber como gerenciar contas do Sistema de Sala do Skype. 

> [!NOTE]
> As Salas do Microsoft Teams são um produto diferente com diferentes dependências e procedimentos de implantação. Para obter informações sobre salas do Microsoft Teams, consulte a visão geral de gerenciamento de Salas [do](https://docs.microsoft.com/microsoftteams/rooms/rooms-manage)Microsoft Teams.
  
## <a name="move-the-skype-room-system-account-between-pools"></a>Mover a conta do Sistema de Sala do Skype entre pools

Se você precisar mover a conta do Sistema de Sala do Skype de um pool do Skype for Business Server para outro (por exemplo, durante atualizações), use o seguinte comando para mover o pool de contas do Sistema de Sala do Skype: 
  
```powershell
Move-CsMeetingRoom -Identity LRS01 -Target "LYNCPool15-2.contoso.com"
```

## <a name="disable-the-skype-room-system-account-for-skype-for-business-services"></a>Desabilitar a conta do Sistema de Sala do Skype para serviços do Skype for Business

Se você precisar desabilitar uma conta existente do Sistema de Sala do Skype dos serviços do Skype for Business em um pool do Skype for Business Server, use o seguinte comando para desabilitar a conta: 
  
```powershell
Disable-CsMeetingRoom LRS01 -domaincontroller DC-ND-001.contoso.com
```

## <a name="optional-create-a-skype-room-system-administrator-group-in-active-directory"></a>Opcional: criar um grupo de administradores do Sistema de Sala do Skype no Active Directory

Cada cliente do Sistema de Sala do Skype que ingressar no domínio pode ser totalmente gerenciado por um usuário de domínio com direitos de administrador local no PC do dispositivo do Sistema de Sala do Skype. Portanto, você pode criar um grupo de administradores dedicados no Active Directory e dar a esse grupo direitos administrativos durante a configuração da nova máquina do Sistema de Sala do Skype.
  

