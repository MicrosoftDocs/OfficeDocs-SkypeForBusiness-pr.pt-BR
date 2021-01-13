---
title: Habilitar o Atendimento de Chamadas em Grupo para usuários e atribuir um número de grupo no Skype for Business
ms.reviewer: ''
ms.author: v-cichur
author: cichur
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
description: Habilitar usuários para o Atendimento de Chamadas em Grupo no Skype for Business Server Enterprise Voice e atribuir um número de grupo.
ms.openlocfilehash: 3467aea1b9671a93cca2f66a2ac73c39f15dc26e
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49830961"
---
# <a name="enable-group-call-pickup-for-users-and-assign-a-group-number-in-skype-for-business"></a><span data-ttu-id="3c6a4-103">Habilitar o Atendimento de Chamadas em Grupo para usuários e atribuir um número de grupo no Skype for Business</span><span class="sxs-lookup"><span data-stu-id="3c6a4-103">Enable Group Call Pickup for users and assign a group number in Skype for Business</span></span>

<span data-ttu-id="3c6a4-104">Habilitar usuários para o Atendimento de Chamadas em Grupo no Skype for Business Server Enterprise Voice e atribuir um número de grupo.</span><span class="sxs-lookup"><span data-stu-id="3c6a4-104">Enable users for Group Call Pickup in Skype for Business Server Enterprise Voice, and assign a group number.</span></span>

<span data-ttu-id="3c6a4-105">Depois de adicionar números de grupo de atendimento de chamada à tabela de órbita de estacionamento de chamada, use a ferramenta SEFAUtil para atribuir os números de grupo aos usuários e habilitar o Atendimento de Chamada em Grupo para eles.</span><span class="sxs-lookup"><span data-stu-id="3c6a4-105">After you add call pickup group numbers to the call park orbit table, you use the SEFAUtil tool to assign the group numbers to users and enable Group Call Pickup for them.</span></span>

> [!NOTE]
> <span data-ttu-id="3c6a4-106">Em uma implantação híbrida, não atribua um grupo de Atendimento de Chamada em Grupo aos usuários que estão online.</span><span class="sxs-lookup"><span data-stu-id="3c6a4-106">In a hybrid deployment, do not assign a Group Call Pickup group to users who are homed online.</span></span> <span data-ttu-id="3c6a4-107">Os usuários que estão online não podem participar do Atendimento de Chamada em Grupo.</span><span class="sxs-lookup"><span data-stu-id="3c6a4-107">Users who are homed online cannot participate in Group Call Pickup.</span></span> <span data-ttu-id="3c6a4-108">Ou seja, suas chamadas não podem ser atendidas por outros usuários e não podem atender chamadas a outros usuários.</span><span class="sxs-lookup"><span data-stu-id="3c6a4-108">That is, their calls cannot be answered by other users, and they cannot answer calls to other users.</span></span>

### <a name="to-assign-a-group-number-and-enable-group-call-pickup-for-a-user"></a><span data-ttu-id="3c6a4-109">Para atribuir um número de grupo e habilitar o Atendimento de Chamada em Grupo para um usuário</span><span class="sxs-lookup"><span data-stu-id="3c6a4-109">To assign a group number and enable Group Call Pickup for a user</span></span>

1. <span data-ttu-id="3c6a4-110">Faça logoff no computador em que você instalou a ferramenta SEFAUtil com direitos de administrador.</span><span class="sxs-lookup"><span data-stu-id="3c6a4-110">Log on to the computer where you installed the SEFAUtil tool with administrator rights.</span></span>

2. <span data-ttu-id="3c6a4-111">Na linha de comando, execute:</span><span class="sxs-lookup"><span data-stu-id="3c6a4-111">At the command line, run:</span></span>

   ```console
   SEFAUtil.exe sip:<sip address of user> /server:<pool FQDN> /enablegrouppickup:<group number>
   ```

    <span data-ttu-id="3c6a4-112">Por exemplo, para atribuir o número de grupo 199 a um usuário:</span><span class="sxs-lookup"><span data-stu-id="3c6a4-112">For example, to assign group number 199 to a user:</span></span>

   ```console
   SEFAUtil.exe katarina@contoso.com /server:pool01.contoso.com /enablegrouppickup:199
   ```

## <a name="see-also"></a><span data-ttu-id="3c6a4-113">Confira também</span><span class="sxs-lookup"><span data-stu-id="3c6a4-113">See also</span></span>

[<span data-ttu-id="3c6a4-114">Desabilitar o Retirada em Grupo para Usuários</span><span class="sxs-lookup"><span data-stu-id="3c6a4-114">Disable Group Pickup for Users</span></span>](https://technet.microsoft.com/library/91b06f9e-2840-45a2-bbb3-6a29179b9a9f.aspx)

