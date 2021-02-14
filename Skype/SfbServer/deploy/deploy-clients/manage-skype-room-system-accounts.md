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
# <a name="manage-skype-room-system-accounts"></a><span data-ttu-id="7aa45-103">Gerenciar contas do Sistema de Salas Skype</span><span class="sxs-lookup"><span data-stu-id="7aa45-103">Manage Skype Room System accounts</span></span>
 
<span data-ttu-id="7aa45-104">Leia este tópico para saber como gerenciar contas do Sistema de Sala do Skype.</span><span class="sxs-lookup"><span data-stu-id="7aa45-104">Read this topic to learn how to manage Skype Room System accounts.</span></span> 

> [!NOTE]
> <span data-ttu-id="7aa45-105">As Salas do Microsoft Teams são um produto diferente com diferentes dependências e procedimentos de implantação.</span><span class="sxs-lookup"><span data-stu-id="7aa45-105">Microsoft Teams Rooms is a different product with different dependencies and deployment procedures.</span></span> <span data-ttu-id="7aa45-106">Para obter informações sobre salas do Microsoft Teams, consulte a visão geral de gerenciamento de Salas [do](https://docs.microsoft.com/microsoftteams/rooms/rooms-manage)Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="7aa45-106">For information on Microsoft Teams Rooms, see the Microsoft Teams Rooms [management overview](https://docs.microsoft.com/microsoftteams/rooms/rooms-manage).</span></span>
  
## <a name="move-the-skype-room-system-account-between-pools"></a><span data-ttu-id="7aa45-107">Mover a conta do Sistema de Sala do Skype entre pools</span><span class="sxs-lookup"><span data-stu-id="7aa45-107">Move the Skype Room System account between pools</span></span>

<span data-ttu-id="7aa45-108">Se você precisar mover a conta do Sistema de Sala do Skype de um pool do Skype for Business Server para outro (por exemplo, durante atualizações), use o seguinte comando para mover o pool de contas do Sistema de Sala do Skype:</span><span class="sxs-lookup"><span data-stu-id="7aa45-108">If you need to move the Skype Room System account from one Skype for Business Server pool to another (for example, during upgrades), use the following command to move the Skype Room System account pool:</span></span> 
  
```powershell
Move-CsMeetingRoom -Identity LRS01 -Target "LYNCPool15-2.contoso.com"
```

## <a name="disable-the-skype-room-system-account-for-skype-for-business-services"></a><span data-ttu-id="7aa45-109">Desabilitar a conta do Sistema de Sala do Skype para serviços do Skype for Business</span><span class="sxs-lookup"><span data-stu-id="7aa45-109">Disable the Skype Room System account for Skype for Business services</span></span>

<span data-ttu-id="7aa45-110">Se você precisar desabilitar uma conta existente do Sistema de Sala do Skype dos serviços do Skype for Business em um pool do Skype for Business Server, use o seguinte comando para desabilitar a conta:</span><span class="sxs-lookup"><span data-stu-id="7aa45-110">If you need to disable an existing Skype Room System account from Skype for Business services on a Skype for Business Server pool, use the following command to disable the account:</span></span> 
  
```powershell
Disable-CsMeetingRoom LRS01 -domaincontroller DC-ND-001.contoso.com
```

## <a name="optional-create-a-skype-room-system-administrator-group-in-active-directory"></a><span data-ttu-id="7aa45-111">Opcional: criar um grupo de administradores do Sistema de Sala do Skype no Active Directory</span><span class="sxs-lookup"><span data-stu-id="7aa45-111">Optional: Create a Skype Room System administrator group in Active Directory</span></span>

<span data-ttu-id="7aa45-112">Cada cliente do Sistema de Sala do Skype que ingressar no domínio pode ser totalmente gerenciado por um usuário de domínio com direitos de administrador local no PC do dispositivo do Sistema de Sala do Skype.</span><span class="sxs-lookup"><span data-stu-id="7aa45-112">Each Skype Room System client that joins the domain can be fully managed by a domain user with local administrator rights on the Skype Room System appliance PC.</span></span> <span data-ttu-id="7aa45-113">Portanto, você pode criar um grupo de administradores dedicados no Active Directory e dar a esse grupo direitos administrativos durante a configuração da nova máquina do Sistema de Sala do Skype.</span><span class="sxs-lookup"><span data-stu-id="7aa45-113">Therefore, you can create a dedicated administrators' group in Active Directory and give this group administrative rights during set up of the new Skype Room System machine.</span></span>
  

