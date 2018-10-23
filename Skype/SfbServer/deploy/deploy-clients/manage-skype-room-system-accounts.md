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
description: Leia este tópico para saber como gerenciar as contas do Sistema de Salas do Skype.
ms.openlocfilehash: 715eda137395d2133b6b19dee4a9d2336923c13b
ms.sourcegitcommit: d3c3467320a2928d3bad14a1a44a31ee5a9a988c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/23/2018
ms.locfileid: "25699241"
---
# <a name="manage-skype-room-system-accounts"></a><span data-ttu-id="4c85e-103">Gerenciar contas do Sistema de Salas do Skype</span><span class="sxs-lookup"><span data-stu-id="4c85e-103">Manage Skype Room System accounts</span></span>
 
<span data-ttu-id="4c85e-104">Leia este tópico para saber como gerenciar as contas do Sistema de Salas do Skype.</span><span class="sxs-lookup"><span data-stu-id="4c85e-104">Read this topic to learn how to manage Skype Room System accounts.</span></span> 

> [!NOTE]
> <span data-ttu-id="4c85e-105">Sistemas de sala Skype v2 é um produto diferente com diferentes dependências e procedimentos de implantação.</span><span class="sxs-lookup"><span data-stu-id="4c85e-105">Skype Room Systems v2 is a different product with different dependencies and deployment procedures.</span></span> <span data-ttu-id="4c85e-106">Para obter informações sobre os sistemas de sala Skype v2, consulte sistemas de sala Skype v2 [Visão geral do gerenciamento](../../manage/skype-room-systems-v2/skype-room-systems-v2.md).</span><span class="sxs-lookup"><span data-stu-id="4c85e-106">For information on Skype Room Systems v2, see the Skype Room Systems v2 [management overview](../../manage/skype-room-systems-v2/skype-room-systems-v2.md).</span></span>
  
## <a name="move-the-skype-room-system-account-between-pools"></a><span data-ttu-id="4c85e-107">Mover a conta do sistema do Skype sala entre pools</span><span class="sxs-lookup"><span data-stu-id="4c85e-107">Move the Skype Room System account between pools</span></span>

<span data-ttu-id="4c85e-108">Se você precisar mover a conta do sistema do Skype sala de um Skype para pool de servidores corporativos para outro (por exemplo, durante as atualizações), use o seguinte comando para mover o pool de conta do sistema do Skype sala:</span><span class="sxs-lookup"><span data-stu-id="4c85e-108">If you need to move the Skype Room System account from one Skype for Business Server pool to another (for example, during upgrades), use the following command to move the Skype Room System account pool:</span></span> 
  
```
Move-CsMeetingRoom -Identity LRS01 -Target "LYNCPool15-2.contoso.com"
```

## <a name="disable-the-skype-room-system-account-for-skype-for-business-services"></a><span data-ttu-id="4c85e-109">Desabilitar a conta do sistema do Skype sala para Skype para serviços corporativos</span><span class="sxs-lookup"><span data-stu-id="4c85e-109">Disable the Skype Room System account for Skype for Business services</span></span>

<span data-ttu-id="4c85e-110">Se você precisar desativar uma Skype sala sistema conta existente do Skype para serviços corporativos em um Skype para pool de servidores corporativos, use o seguinte comando para desabilitar a conta:</span><span class="sxs-lookup"><span data-stu-id="4c85e-110">If you need to disable an existing Skype Room System account from Skype for Business services on a Skype for Business Server pool, use the following command to disable the account:</span></span> 
  
```
Disable-CsMeetingRoom LRS01 -domaincontroller DC-ND-001.contoso.com
```

## <a name="optional-create-a-skype-room-system-administrator-group-in-active-directory"></a><span data-ttu-id="4c85e-111">Opcional: Criar um grupo de administrador do sistema do Skype sala no Active Directory</span><span class="sxs-lookup"><span data-stu-id="4c85e-111">Optional: Create a Skype Room System administrator group in Active Directory</span></span>

<span data-ttu-id="4c85e-112">Cada cliente do sistema de sala Skype que ingressa no domínio pode ser totalmente gerenciado por um usuário de domínio com direitos de administrador local no dispositivo do sistema de sala Skype PC.</span><span class="sxs-lookup"><span data-stu-id="4c85e-112">Each Skype Room System client that joins the domain can be fully managed by a domain user with local administrator rights on the Skype Room System appliance PC.</span></span> <span data-ttu-id="4c85e-113">Portanto, você pode criar grupo dos administradores um dedicado no Active Directory e dar este direitos administrativos do grupo durante set up da máquina nova sistema de sala Skype.</span><span class="sxs-lookup"><span data-stu-id="4c85e-113">Therefore, you can create a dedicated administrators' group in Active Directory and give this group administrative rights during set up of the new Skype Room System machine.</span></span>
  

