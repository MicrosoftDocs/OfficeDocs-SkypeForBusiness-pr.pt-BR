---
title: Habilitar o Atendimento de Chamadas de Grupo para usuários e atribuir um número de grupo no Skype for Business
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
description: Habilita os usuários para Coleta de Chamadas de Grupo no Skype for Business Server Enterprise Voice e atribua um número de grupo.
ms.openlocfilehash: 5469e9634e16b855993518092114184a2dca7359
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51111827"
---
# <a name="enable-group-call-pickup-for-users-and-assign-a-group-number-in-skype-for-business"></a><span data-ttu-id="b26b1-103">Habilitar o Atendimento de Chamadas de Grupo para usuários e atribuir um número de grupo no Skype for Business</span><span class="sxs-lookup"><span data-stu-id="b26b1-103">Enable Group Call Pickup for users and assign a group number in Skype for Business</span></span>

<span data-ttu-id="b26b1-104">Habilita os usuários para Coleta de Chamadas de Grupo no Skype for Business Server Enterprise Voice e atribua um número de grupo.</span><span class="sxs-lookup"><span data-stu-id="b26b1-104">Enable users for Group Call Pickup in Skype for Business Server Enterprise Voice, and assign a group number.</span></span>

<span data-ttu-id="b26b1-105">Depois de adicionar números de grupo de retirada de chamada à tabela de órbita do estacionamento de chamada, use a ferramenta SEFAUtil para atribuir os números de grupo aos usuários e habilitar a Coleta de Chamada de Grupo para eles.</span><span class="sxs-lookup"><span data-stu-id="b26b1-105">After you add call pickup group numbers to the call park orbit table, you use the SEFAUtil tool to assign the group numbers to users and enable Group Call Pickup for them.</span></span>

> [!NOTE]
> <span data-ttu-id="b26b1-106">Em uma implantação híbrida, não atribua um grupo de Retirada de Chamada de Grupo aos usuários que estão em casa online.</span><span class="sxs-lookup"><span data-stu-id="b26b1-106">In a hybrid deployment, do not assign a Group Call Pickup group to users who are homed online.</span></span> <span data-ttu-id="b26b1-107">Os usuários que estão em casa online não podem participar da Coleta de Chamada de Grupo.</span><span class="sxs-lookup"><span data-stu-id="b26b1-107">Users who are homed online cannot participate in Group Call Pickup.</span></span> <span data-ttu-id="b26b1-108">Ou seja, suas chamadas não podem ser atendidas por outros usuários e não podem atender chamadas a outros usuários.</span><span class="sxs-lookup"><span data-stu-id="b26b1-108">That is, their calls cannot be answered by other users, and they cannot answer calls to other users.</span></span>

### <a name="to-assign-a-group-number-and-enable-group-call-pickup-for-a-user"></a><span data-ttu-id="b26b1-109">Para atribuir um número de grupo e habilitar a Coleta de Chamada de Grupo para um usuário</span><span class="sxs-lookup"><span data-stu-id="b26b1-109">To assign a group number and enable Group Call Pickup for a user</span></span>

1. <span data-ttu-id="b26b1-110">Faça logoff no computador onde você instalou a ferramenta SEFAUtil com direitos de administrador.</span><span class="sxs-lookup"><span data-stu-id="b26b1-110">Log on to the computer where you installed the SEFAUtil tool with administrator rights.</span></span>

2. <span data-ttu-id="b26b1-111">Na linha de comando, execute:</span><span class="sxs-lookup"><span data-stu-id="b26b1-111">At the command line, run:</span></span>

   ```console
   SEFAUtil.exe sip:<sip address of user> /server:<pool FQDN> /enablegrouppickup:<group number>
   ```

    <span data-ttu-id="b26b1-112">Por exemplo, para atribuir o número de grupo 199 a um usuário:</span><span class="sxs-lookup"><span data-stu-id="b26b1-112">For example, to assign group number 199 to a user:</span></span>

   ```console
   SEFAUtil.exe katarina@contoso.com /server:pool01.contoso.com /enablegrouppickup:199
   ```

## <a name="see-also"></a><span data-ttu-id="b26b1-113">Confira também</span><span class="sxs-lookup"><span data-stu-id="b26b1-113">See also</span></span>

[<span data-ttu-id="b26b1-114">Desabilitar a coleta de grupo para usuários</span><span class="sxs-lookup"><span data-stu-id="b26b1-114">Disable Group Pickup for Users</span></span>](/previous-versions/office/lync-server-2013/lync-server-2013-disable-group-call-pickup-for-users)