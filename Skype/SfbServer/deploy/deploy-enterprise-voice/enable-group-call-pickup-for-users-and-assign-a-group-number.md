---
title: Habilitar o recebimento de chamadas em grupo para usuários e atribuir um número de grupo no Skype for Business
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: c33bb6c2-d43b-4fb6-a0fa-6d82a7b09abe
description: Permita que os usuários façam o recebimento de chamadas em grupo no Skype for Business Server Enterprise Voice e atribua um número de grupo.
ms.openlocfilehash: bebddb5f71612cf23d442366c774d0e8d4b9f500
ms.sourcegitcommit: dd3a3ab4ddbdcfe772f30fb01ba3b97c45c43dd4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41767264"
---
# <a name="enable-group-call-pickup-for-users-and-assign-a-group-number-in-skype-for-business"></a><span data-ttu-id="87f48-103">Habilitar o recebimento de chamadas em grupo para usuários e atribuir um número de grupo no Skype for Business</span><span class="sxs-lookup"><span data-stu-id="87f48-103">Enable Group Call Pickup for users and assign a group number in Skype for Business</span></span>

<span data-ttu-id="87f48-104">Permita que os usuários façam o recebimento de chamadas em grupo no Skype for Business Server Enterprise Voice e atribua um número de grupo.</span><span class="sxs-lookup"><span data-stu-id="87f48-104">Enable users for Group Call Pickup in Skype for Business Server Enterprise Voice, and assign a group number.</span></span>

<span data-ttu-id="87f48-105">Depois de adicionar números de grupo de recebimento de chamada à tabela órbita do parque de chamadas, use a ferramenta SEFAUtil para atribuir os números de grupo aos usuários e habilitar o recebimento de chamadas em grupo para eles.</span><span class="sxs-lookup"><span data-stu-id="87f48-105">After you add call pickup group numbers to the call park orbit table, you use the SEFAUtil tool to assign the group numbers to users and enable Group Call Pickup for them.</span></span>

> [!NOTE]
> <span data-ttu-id="87f48-106">Em uma implantação híbrida, não atribua um grupo de recebimento de chamadas em grupo aos usuários que estiverem em casa online.</span><span class="sxs-lookup"><span data-stu-id="87f48-106">In a hybrid deployment, do not assign a Group Call Pickup group to users who are homed online.</span></span> <span data-ttu-id="87f48-107">Os usuários que estiverem hospedados online não poderão participar da retirada de chamadas em grupo.</span><span class="sxs-lookup"><span data-stu-id="87f48-107">Users who are homed online cannot participate in Group Call Pickup.</span></span> <span data-ttu-id="87f48-108">Isso significa que suas chamadas não podem ser atendidas por outros usuários, e eles não podem responder chamadas no lugar de outros usuários.</span><span class="sxs-lookup"><span data-stu-id="87f48-108">That is, their calls cannot be answered by other users, and they cannot answer calls to other users.</span></span>

### <a name="to-assign-a-group-number-and-enable-group-call-pickup-for-a-user"></a><span data-ttu-id="87f48-109">Para atribuir um número de grupo e habilitar a retirada de chamadas em grupo para um usuário</span><span class="sxs-lookup"><span data-stu-id="87f48-109">To assign a group number and enable Group Call Pickup for a user</span></span>

1. <span data-ttu-id="87f48-110">Realize logon no computador em que você instalou a ferramenta SEFAUtil com direitos de administrador.</span><span class="sxs-lookup"><span data-stu-id="87f48-110">Log on to the computer where you installed the SEFAUtil tool with administrator rights.</span></span>

2. <span data-ttu-id="87f48-111">Na linha de comando, execute:</span><span class="sxs-lookup"><span data-stu-id="87f48-111">At the command line, run:</span></span>

   ```console
   SEFAUtil.exe sip:<sip address of user> /server:<pool FQDN> /enablegrouppickup:<group number>
   ```

    <span data-ttu-id="87f48-112">Por exemplo, para atribuir o número de grupo 199 a um usuário:</span><span class="sxs-lookup"><span data-stu-id="87f48-112">For example, to assign group number 199 to a user:</span></span>

   ```console
   SEFAUtil.exe katarina@contoso.com /server:pool01.contoso.com /enablegrouppickup:199
   ```

## <a name="see-also"></a><span data-ttu-id="87f48-113">Confira também</span><span class="sxs-lookup"><span data-stu-id="87f48-113">See also</span></span>

[<span data-ttu-id="87f48-114">Disable Group Pickup for Users</span><span class="sxs-lookup"><span data-stu-id="87f48-114">Disable Group Pickup for Users</span></span>](https://technet.microsoft.com/library/91b06f9e-2840-45a2-bbb3-6a29179b9a9f.aspx)

