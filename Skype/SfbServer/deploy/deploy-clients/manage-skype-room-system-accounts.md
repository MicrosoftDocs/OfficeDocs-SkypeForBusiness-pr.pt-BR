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
# <a name="manage-skype-room-system-accounts"></a><span data-ttu-id="23f61-103">Gerenciar contas do Sistema de Salas do Skype</span><span class="sxs-lookup"><span data-stu-id="23f61-103">Manage Skype Room System accounts</span></span>
 
<span data-ttu-id="23f61-104">Leia este tópico para saber como gerenciar as contas do Sistema de Salas do Skype.</span><span class="sxs-lookup"><span data-stu-id="23f61-104">Read this topic to learn how to manage Skype Room System accounts.</span></span>
  
## <a name="move-the-skype-room-system-account-between-pools"></a><span data-ttu-id="23f61-105">Mover a conta do sistema do Skype sala entre pools</span><span class="sxs-lookup"><span data-stu-id="23f61-105">Move the Skype Room System account between pools</span></span>

<span data-ttu-id="23f61-106">Se você precisar mover a conta do sistema do Skype sala de um Skype para pool de servidores corporativos para outro (por exemplo, durante as atualizações), use o seguinte comando para mover o pool de conta do sistema do Skype sala:</span><span class="sxs-lookup"><span data-stu-id="23f61-106">If you need to move the Skype Room System account from one Skype for Business Server pool to another (for example, during upgrades), use the following command to move the Skype Room System account pool:</span></span> 
  
```
Move-CsMeetingRoom -Identity LRS01 -Target "LYNCPool15-2.contoso.com"
```

## <a name="disable-the-skype-room-system-account-for-skype-for-business-services"></a><span data-ttu-id="23f61-107">Desabilitar a conta do sistema do Skype sala para Skype para serviços corporativos</span><span class="sxs-lookup"><span data-stu-id="23f61-107">Disable the Skype Room System account for Skype for Business services</span></span>

<span data-ttu-id="23f61-108">Se você precisar desativar uma Skype sala sistema conta existente do Skype para serviços corporativos em um Skype para pool de servidores corporativos, use o seguinte comando para desabilitar a conta:</span><span class="sxs-lookup"><span data-stu-id="23f61-108">If you need to disable an existing Skype Room System account from Skype for Business services on a Skype for Business Server pool, use the following command to disable the account:</span></span> 
  
```
Disable-CsMeetingRoom LRS01 -domaincontroller DC-ND-001.contoso.com
```

## <a name="optional-create-a-skype-room-system-administrator-group-in-active-directory"></a><span data-ttu-id="23f61-109">Opcional: Criar um grupo de administrador do sistema do Skype sala no Active Directory</span><span class="sxs-lookup"><span data-stu-id="23f61-109">Optional: Create a Skype Room System administrator group in Active Directory</span></span>

<span data-ttu-id="23f61-110">Cada cliente do sistema de sala Skype que ingressa no domínio pode ser totalmente gerenciado por um usuário de domínio com direitos de administrador local no dispositivo do sistema de sala Skype PC.</span><span class="sxs-lookup"><span data-stu-id="23f61-110">Each Skype Room System client that joins the domain can be fully managed by a domain user with local administrator rights on the Skype Room System appliance PC.</span></span> <span data-ttu-id="23f61-111">Portanto, você pode criar grupo dos administradores um dedicado no Active Directory e dar este direitos administrativos do grupo durante set up da máquina nova sistema de sala Skype.</span><span class="sxs-lookup"><span data-stu-id="23f61-111">Therefore, you can create a dedicated administrators' group in Active Directory and give this group administrative rights during set up of the new Skype Room System machine.</span></span>
  

