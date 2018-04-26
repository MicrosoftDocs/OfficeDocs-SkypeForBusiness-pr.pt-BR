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
  
## <a name="move-the-skype-room-system-account-between-pools"></a>Move the Skype Room System account between pools

Se for necessário transferir a conta do  de um pool do  para outro (por exemplo, durante upgrades), use o seguinte comando para mover o pool da conta do : 
  
```
Move-CsMeetingRoom -Identity LRS01 -Target "LYNCPool15-2.contoso.com"
```

## <a name="disable-the-skype-room-system-account-for-skype-for-business-services"></a>Disable the Skype Room System account for Skype for Business services

If you need to disable an existing Skype Room System account from Skype for Business services on a Skype for Business Server pool, use the following command to disable the account: 
  
```
Disable-CsMeetingRoom LRS01 -domaincontroller DC-ND-001.contoso.com
```

## <a name="optional-create-a-skype-room-system-administrator-group-in-active-directory"></a>Opcional: criar um grupo de administradores do  no Active Directory

Cada cliente do  que participa do domínio pode ser totalmente gerenciado por um usuário de domínio com direitos de administrador local no PC do cliente . Portanto, você pode criar um grupo administradores dedicados no Active Directory e dar a este grupo direitos administrativos durante a configuração da nova máquina do .
  

