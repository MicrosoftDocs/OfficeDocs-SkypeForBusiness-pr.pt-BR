---
title: Gerenciar contas do Sistema de Salas Skype
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
audience: ITPro
ms.reviewer: sohailta
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 7b389efc-9685-42e9-9504-be437d20ff57
ms.collection: M365-voice
description: Leia este tópico para saber como gerenciar as Skype do Sistema de Sala.
ms.openlocfilehash: 2ae91a977a837e2b1b54db8d127551b5f53bb1a8
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/08/2021
ms.locfileid: "60864448"
---
# <a name="manage-skype-room-system-accounts"></a>Gerenciar contas do Sistema de Salas Skype
 
Leia este tópico para saber como gerenciar as Skype do Sistema de Sala. 

> [!NOTE]
> Salas do Microsoft Teams é um produto diferente com diferentes dependências e procedimentos de implantação. Para obter informações sobre Salas do Microsoft Teams, consulte a visão geral Salas do Microsoft Teams [gerenciamento.](/microsoftteams/rooms/rooms-manage)
  
## <a name="move-the-skype-room-system-account-between-pools"></a>Mover a Skype do Sistema de Sala entre pools

Se você precisar mover Skype conta do sistema de sala de um pool de Skype for Business Server para outro (por exemplo, durante atualizações), use o seguinte comando para mover o pool de contas do sistema de sala Skype: 
  
```powershell
Move-CsMeetingRoom -Identity LRS01 -Target "LYNCPool15-2.contoso.com"
```

## <a name="disable-the-skype-room-system-account-for-skype-for-business-services"></a>Desabilitar a Skype do Sistema de Sala para Skype for Business serviços

Se você precisar desabilitar uma conta existente do sistema de Skype de Skype for Business em um pool de Skype for Business Server, use o seguinte comando para desabilitar a conta: 
  
```powershell
Disable-CsMeetingRoom LRS01 -domaincontroller DC-ND-001.contoso.com
```

## <a name="optional-create-a-skype-room-system-administrator-group-in-active-directory"></a>Opcional: criar um grupo Skype de administradores do Sistema de Sala no Active Directory

Cada Skype cliente do Sistema de Sala que ins junta ao domínio pode ser totalmente gerenciado por um usuário de domínio com direitos de administrador local no computador do Skype do sistema de sala. Portanto, você pode criar um grupo de administradores dedicados no Active Directory e dar a esse grupo direitos administrativos durante a configuração do novo computador do sistema de sala Skype sala.
