---
title: Gerenciar contas do Sistema de Salas do Skype
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.reviewer: davgroom
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 7b389efc-9685-42e9-9504-be437d20ff57
ms.collection: M365-voice
description: Leia este tópico para saber como gerenciar as contas do Sistema de Salas do Skype.
ms.openlocfilehash: 4c276d4acf0cf15df7689fa5c11a0e6e2cde785b
ms.sourcegitcommit: 4266c1fbd8557bf2bf65447557ee8d597f90ccd3
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/30/2019
ms.locfileid: "31012521"
---
# <a name="manage-skype-room-system-accounts"></a><span data-ttu-id="edb5d-103">Gerenciar contas do Sistema de Salas do Skype</span><span class="sxs-lookup"><span data-stu-id="edb5d-103">Manage Skype Room System accounts</span></span>
 
<span data-ttu-id="edb5d-104">Leia este tópico para saber como gerenciar as contas do Sistema de Salas do Skype.</span><span class="sxs-lookup"><span data-stu-id="edb5d-104">Read this topic to learn how to manage Skype Room System accounts.</span></span> 

> [!NOTE]
> <span data-ttu-id="edb5d-105">Salas de equipes da Microsoft é um produto diferente com diferentes dependências e procedimentos de implantação.</span><span class="sxs-lookup"><span data-stu-id="edb5d-105">Microsoft Teams Rooms is a different product with different dependencies and deployment procedures.</span></span> <span data-ttu-id="edb5d-106">Para obter informações sobre as salas de equipes da Microsoft, consulte Microsoft equipes salas [Visão geral do gerenciamento](../../manage/skype-room-systems-v2/skype-room-systems-v2.md).</span><span class="sxs-lookup"><span data-stu-id="edb5d-106">For information on Microsoft Teams Rooms, see the Microsoft Teams Rooms [management overview](../../manage/skype-room-systems-v2/skype-room-systems-v2.md).</span></span>
  
## <a name="move-the-skype-room-system-account-between-pools"></a><span data-ttu-id="edb5d-107">Mover a conta do sistema do Skype sala entre pools</span><span class="sxs-lookup"><span data-stu-id="edb5d-107">Move the Skype Room System account between pools</span></span>

<span data-ttu-id="edb5d-108">Se você precisar mover a conta do sistema do Skype sala de um Skype para pool de servidores corporativos para outro (por exemplo, durante as atualizações), use o seguinte comando para mover o pool de conta do sistema do Skype sala:</span><span class="sxs-lookup"><span data-stu-id="edb5d-108">If you need to move the Skype Room System account from one Skype for Business Server pool to another (for example, during upgrades), use the following command to move the Skype Room System account pool:</span></span> 
  
```
Move-CsMeetingRoom -Identity LRS01 -Target "LYNCPool15-2.contoso.com"
```

## <a name="disable-the-skype-room-system-account-for-skype-for-business-services"></a><span data-ttu-id="edb5d-109">Desabilitar a conta do sistema do Skype sala para Skype para serviços corporativos</span><span class="sxs-lookup"><span data-stu-id="edb5d-109">Disable the Skype Room System account for Skype for Business services</span></span>

<span data-ttu-id="edb5d-110">Se você precisar desativar uma Skype sala sistema conta existente do Skype para serviços corporativos em um Skype para pool de servidores corporativos, use o seguinte comando para desabilitar a conta:</span><span class="sxs-lookup"><span data-stu-id="edb5d-110">If you need to disable an existing Skype Room System account from Skype for Business services on a Skype for Business Server pool, use the following command to disable the account:</span></span> 
  
```
Disable-CsMeetingRoom LRS01 -domaincontroller DC-ND-001.contoso.com
```

## <a name="optional-create-a-skype-room-system-administrator-group-in-active-directory"></a><span data-ttu-id="edb5d-111">Opcional: Criar um grupo de administrador do sistema do Skype sala no Active Directory</span><span class="sxs-lookup"><span data-stu-id="edb5d-111">Optional: Create a Skype Room System administrator group in Active Directory</span></span>

<span data-ttu-id="edb5d-112">Cada cliente do sistema de sala Skype que ingressa no domínio pode ser totalmente gerenciado por um usuário de domínio com direitos de administrador local no dispositivo do sistema de sala Skype PC.</span><span class="sxs-lookup"><span data-stu-id="edb5d-112">Each Skype Room System client that joins the domain can be fully managed by a domain user with local administrator rights on the Skype Room System appliance PC.</span></span> <span data-ttu-id="edb5d-113">Portanto, você pode criar grupo dos administradores um dedicado no Active Directory e dar este direitos administrativos do grupo durante set up da máquina nova sistema de sala Skype.</span><span class="sxs-lookup"><span data-stu-id="edb5d-113">Therefore, you can create a dedicated administrators' group in Active Directory and give this group administrative rights during set up of the new Skype Room System machine.</span></span>
  

