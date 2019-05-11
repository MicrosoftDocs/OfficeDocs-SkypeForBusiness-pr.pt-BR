---
title: Gerenciar contas do Sistema de Salas do Skype
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.reviewer: davgroom
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 7b389efc-9685-42e9-9504-be437d20ff57
ms.collection: M365-voice
description: Leia este tópico para saber como gerenciar as contas do Sistema de Salas do Skype.
ms.openlocfilehash: 86fb7356586c006e8d9f0831d98c9ceba5979180
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "33893368"
---
# <a name="manage-skype-room-system-accounts"></a>Gerenciar contas do Sistema de Salas do Skype
 
Leia este tópico para saber como gerenciar as contas do Sistema de Salas do Skype. 

> [!NOTE]
> Salas de equipes da Microsoft é um produto diferente com diferentes dependências e procedimentos de implantação. Para obter informações sobre as salas de equipes da Microsoft, consulte Microsoft equipes salas [Visão geral do gerenciamento](../../manage/skype-room-systems-v2/skype-room-systems-v2.md).
  
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
  

