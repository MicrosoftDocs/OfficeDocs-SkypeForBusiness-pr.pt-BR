---
title: Gerenciar contas do Sistema de Salas do Skype
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.reviewer: sohailta
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 7b389efc-9685-42e9-9504-be437d20ff57
ms.collection: M365-voice
description: Leia este tópico para saber como gerenciar as contas do Sistema de Salas do Skype.
ms.openlocfilehash: 7594532e5da42ac9f1b41444052ec51c3779ee2b
ms.sourcegitcommit: fe274303510d07a90b506bfa050c669accef0476
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/09/2020
ms.locfileid: "41001481"
---
# <a name="manage-skype-room-system-accounts"></a><span data-ttu-id="fde37-103">Gerenciar contas do Sistema de Salas do Skype</span><span class="sxs-lookup"><span data-stu-id="fde37-103">Manage Skype Room System accounts</span></span>
 
<span data-ttu-id="fde37-104">Leia este tópico para saber como gerenciar as contas do Sistema de Salas do Skype.</span><span class="sxs-lookup"><span data-stu-id="fde37-104">Read this topic to learn how to manage Skype Room System accounts.</span></span> 

> [!NOTE]
> <span data-ttu-id="fde37-105">As salas do Microsoft Teams é um produto diferente com diferentes dependências e procedimentos de implantação.</span><span class="sxs-lookup"><span data-stu-id="fde37-105">Microsoft Teams Rooms is a different product with different dependencies and deployment procedures.</span></span> <span data-ttu-id="fde37-106">Para obter informações sobre as salas do Microsoft Teams, consulte a [visão geral do gerenciamento](../../manage/skype-room-systems-v2/skype-room-systems-v2.md)de salas do Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="fde37-106">For information on Microsoft Teams Rooms, see the Microsoft Teams Rooms [management overview](../../manage/skype-room-systems-v2/skype-room-systems-v2.md).</span></span>
  
## <a name="move-the-skype-room-system-account-between-pools"></a><span data-ttu-id="fde37-107">Mover a conta do sistema de sala do Skype entre pools</span><span class="sxs-lookup"><span data-stu-id="fde37-107">Move the Skype Room System account between pools</span></span>

<span data-ttu-id="fde37-108">Se você precisar mover a conta do sistema de sala do Skype de um pool do Skype for Business Server para outro (por exemplo, durante as atualizações), use o seguinte comando para mover o pool de contas do sistema de salas do Skype:</span><span class="sxs-lookup"><span data-stu-id="fde37-108">If you need to move the Skype Room System account from one Skype for Business Server pool to another (for example, during upgrades), use the following command to move the Skype Room System account pool:</span></span> 
  
```powershell
Move-CsMeetingRoom -Identity LRS01 -Target "LYNCPool15-2.contoso.com"
```

## <a name="disable-the-skype-room-system-account-for-skype-for-business-services"></a><span data-ttu-id="fde37-109">Desabilitar a conta do sistema de sala do Skype para serviços do Skype for Business</span><span class="sxs-lookup"><span data-stu-id="fde37-109">Disable the Skype Room System account for Skype for Business services</span></span>

<span data-ttu-id="fde37-110">Se você precisar desabilitar uma conta existente do sistema de sala do Skype dos serviços do Skype for Business em um pool de servidores do Skype for Business, use o seguinte comando para desativar a conta:</span><span class="sxs-lookup"><span data-stu-id="fde37-110">If you need to disable an existing Skype Room System account from Skype for Business services on a Skype for Business Server pool, use the following command to disable the account:</span></span> 
  
```powershell
Disable-CsMeetingRoom LRS01 -domaincontroller DC-ND-001.contoso.com
```

## <a name="optional-create-a-skype-room-system-administrator-group-in-active-directory"></a><span data-ttu-id="fde37-111">Opcional: criar um grupo de administradores do sistema de salas do Skype no Active Directory</span><span class="sxs-lookup"><span data-stu-id="fde37-111">Optional: Create a Skype Room System administrator group in Active Directory</span></span>

<span data-ttu-id="fde37-112">Cada cliente do sistema da sala do Skype que une o domínio pode ser totalmente gerenciado por um usuário do domínio com direitos de administrador local no PC Appliance do sistema de sala do Skype.</span><span class="sxs-lookup"><span data-stu-id="fde37-112">Each Skype Room System client that joins the domain can be fully managed by a domain user with local administrator rights on the Skype Room System appliance PC.</span></span> <span data-ttu-id="fde37-113">Portanto, você pode criar um grupo de administradores dedicados no Active Directory e dar a esses direitos administrativos de grupo durante a configuração do novo computador do sistema de sala do Skype.</span><span class="sxs-lookup"><span data-stu-id="fde37-113">Therefore, you can create a dedicated administrators' group in Active Directory and give this group administrative rights during set up of the new Skype Room System machine.</span></span>
  

