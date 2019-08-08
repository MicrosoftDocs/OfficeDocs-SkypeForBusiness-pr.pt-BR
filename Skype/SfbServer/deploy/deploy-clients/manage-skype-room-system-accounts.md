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
# <a name="manage-skype-room-system-accounts"></a><span data-ttu-id="04ded-103">Gerenciar contas do Sistema de Salas do Skype</span><span class="sxs-lookup"><span data-stu-id="04ded-103">Manage Skype Room System accounts</span></span>
 
<span data-ttu-id="04ded-104">Leia este tópico para saber como gerenciar as contas do Sistema de Salas do Skype.</span><span class="sxs-lookup"><span data-stu-id="04ded-104">Read this topic to learn how to manage Skype Room System accounts.</span></span> 

> [!NOTE]
> <span data-ttu-id="04ded-105">As salas do Microsoft Teams é um produto diferente com diferentes dependências e procedimentos de implantação.</span><span class="sxs-lookup"><span data-stu-id="04ded-105">Microsoft Teams Rooms is a different product with different dependencies and deployment procedures.</span></span> <span data-ttu-id="04ded-106">Para obter informações sobre as salas do Microsoft Teams, consulte a [visão geral do gerenciamento](../../manage/skype-room-systems-v2/skype-room-systems-v2.md)de salas do Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="04ded-106">For information on Microsoft Teams Rooms, see the Microsoft Teams Rooms [management overview](../../manage/skype-room-systems-v2/skype-room-systems-v2.md).</span></span>
  
## <a name="move-the-skype-room-system-account-between-pools"></a><span data-ttu-id="04ded-107">Mover a conta do sistema de sala do Skype entre pools</span><span class="sxs-lookup"><span data-stu-id="04ded-107">Move the Skype Room System account between pools</span></span>

<span data-ttu-id="04ded-108">Se você precisar mover a conta do sistema de sala do Skype de um pool do Skype for Business Server para outro (por exemplo, durante as atualizações), use o seguinte comando para mover o pool de contas do sistema de salas do Skype:</span><span class="sxs-lookup"><span data-stu-id="04ded-108">If you need to move the Skype Room System account from one Skype for Business Server pool to another (for example, during upgrades), use the following command to move the Skype Room System account pool:</span></span> 
  
```
Move-CsMeetingRoom -Identity LRS01 -Target "LYNCPool15-2.contoso.com"
```

## <a name="disable-the-skype-room-system-account-for-skype-for-business-services"></a><span data-ttu-id="04ded-109">Desabilitar a conta do sistema de sala do Skype para serviços do Skype for Business</span><span class="sxs-lookup"><span data-stu-id="04ded-109">Disable the Skype Room System account for Skype for Business services</span></span>

<span data-ttu-id="04ded-110">Se você precisar desabilitar uma conta existente do sistema de sala do Skype dos serviços do Skype for Business em um pool de servidores do Skype for Business, use o seguinte comando para desativar a conta:</span><span class="sxs-lookup"><span data-stu-id="04ded-110">If you need to disable an existing Skype Room System account from Skype for Business services on a Skype for Business Server pool, use the following command to disable the account:</span></span> 
  
```
Disable-CsMeetingRoom LRS01 -domaincontroller DC-ND-001.contoso.com
```

## <a name="optional-create-a-skype-room-system-administrator-group-in-active-directory"></a><span data-ttu-id="04ded-111">Opcional: criar um grupo de administradores do sistema de salas do Skype no Active Directory</span><span class="sxs-lookup"><span data-stu-id="04ded-111">Optional: Create a Skype Room System administrator group in Active Directory</span></span>

<span data-ttu-id="04ded-112">Cada cliente do sistema da sala do Skype que une o domínio pode ser totalmente gerenciado por um usuário do domínio com direitos de administrador local no PC Appliance do sistema de sala do Skype.</span><span class="sxs-lookup"><span data-stu-id="04ded-112">Each Skype Room System client that joins the domain can be fully managed by a domain user with local administrator rights on the Skype Room System appliance PC.</span></span> <span data-ttu-id="04ded-113">Portanto, você pode criar um grupo de administradores dedicados no Active Directory e dar a esses direitos administrativos de grupo durante a configuração do novo computador do sistema de sala do Skype.</span><span class="sxs-lookup"><span data-stu-id="04ded-113">Therefore, you can create a dedicated administrators' group in Active Directory and give this group administrative rights during set up of the new Skype Room System machine.</span></span>
  

