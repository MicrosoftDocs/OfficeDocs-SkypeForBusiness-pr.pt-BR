---
title: Gerenciar contas do Sistema de Salas do Skype
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 3/4/2016
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 7b389efc-9685-42e9-9504-be437d20ff57
description: Leia este tópico para saber como gerenciar as contas do Sistema de Salas do Skype.
ms.openlocfilehash: c47765b617e0856d1db25c7ed4902fe0af9924f2
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/28/2018
---
# <a name="manage-skype-room-system-accounts"></a>Gerenciar contas do Sistema de Salas do Skype
 
Leia este tópico para saber como gerenciar as contas do Sistema de Salas do Skype.
  
## <a name="move-the-skype-room-system-account-between-pools"></a>Mover a conta do sistema do Skype sala entre pools

Se você precisar mover a conta do sistema do Skype sala de um Skype para pool de servidores corporativos para outro (por exemplo, durante as atualizações), use o seguinte comando para mover o pool de conta do sistema do Skype sala: 
  
```
Move-CsMeetingRoom -Identity LRS01 -Target "LYNCPool15-2.contoso.com"
```

## <a name="disable-the-skype-room-system-account-for-skype-for-business-services"></a>Desabilitar a conta do sistema do Skype sala para Skype para serviços corporativos

Se você precisar desativar uma Skype sala sistema conta existente do Skype para serviços corporativos em um Skype para pool de servidores corporativos, use o seguinte comando para desabilitar a conta: 
  
```
Disable-CsMeetingRoom LRS01 -domaincontroller DC-ND-001.contoso.com
```

## <a name="optional-create-a-skype-room-system-administrator-group-in-active-directory"></a>Opcional: Criar um grupo de administrador do sistema do Skype sala no Active Directory

Cada cliente do sistema de sala Skype que ingressa no domínio pode ser totalmente gerenciado por um usuário de domínio com direitos de administrador local no dispositivo do sistema de sala Skype PC. Portanto, você pode criar grupo dos administradores um dedicado no Active Directory e dar este direitos administrativos do grupo durante set up da máquina nova sistema de sala Skype.
  

