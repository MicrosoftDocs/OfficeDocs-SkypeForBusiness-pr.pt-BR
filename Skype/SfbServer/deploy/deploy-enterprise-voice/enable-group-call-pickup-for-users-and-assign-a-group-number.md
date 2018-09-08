---
title: Habilitar o atendimento de chamada de grupo para usuários e atribuir um número de grupo no Skype para negócios
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: c33bb6c2-d43b-4fb6-a0fa-6d82a7b09abe
description: Habilitar usuários para atendimento de chamada do grupo no Skype para Business Server Enterprise Voice e atribua um número de grupo.
ms.openlocfilehash: 94498732ef9bdc66130a6c15cbf342681c48f036
ms.sourcegitcommit: 940cb253923e3537cb7fb4d7ce875ed9bfbb72db
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/07/2018
ms.locfileid: "23881844"
---
# <a name="enable-group-call-pickup-for-users-and-assign-a-group-number-in-skype-for-business"></a><span data-ttu-id="3aee6-103">Habilitar o atendimento de chamada de grupo para usuários e atribuir um número de grupo no Skype para negócios</span><span class="sxs-lookup"><span data-stu-id="3aee6-103">Enable Group Call Pickup for users and assign a group number in Skype for Business</span></span>

<span data-ttu-id="3aee6-104">Habilitar usuários para atendimento de chamada do grupo no Skype para Business Server Enterprise Voice e atribua um número de grupo.</span><span class="sxs-lookup"><span data-stu-id="3aee6-104">Enable users for Group Call Pickup in Skype for Business Server Enterprise Voice, and assign a group number.</span></span>

<span data-ttu-id="3aee6-105">Depois de adicionar os números de retirada de grupo de chamada à tabela de órbita de estacionamento de chamada, você usar a ferramenta de SEFAUtil para atribuir os números de grupo aos usuários e habilitar o atendimento de chamada de grupo para eles.</span><span class="sxs-lookup"><span data-stu-id="3aee6-105">After you add call pickup group numbers to the call park orbit table, you use the SEFAUtil tool to assign the group numbers to users and enable Group Call Pickup for them.</span></span>

> [!NOTE]
> <span data-ttu-id="3aee6-106">Em uma implantação híbrida, não atribua um grupo de atendimento de chamada de grupo para usuários hospedados online.</span><span class="sxs-lookup"><span data-stu-id="3aee6-106">In a hybrid deployment, do not assign a Group Call Pickup group to users who are homed online.</span></span> <span data-ttu-id="3aee6-107">Os usuários hospedados online não podem participar de atendimento de chamada do grupo.</span><span class="sxs-lookup"><span data-stu-id="3aee6-107">Users who are homed online cannot participate in Group Call Pickup.</span></span> <span data-ttu-id="3aee6-108">Isso significa que suas chamadas não podem ser atendidas por outros usuários, e eles não podem responder chamadas no lugar de outros usuários.</span><span class="sxs-lookup"><span data-stu-id="3aee6-108">That is, their calls cannot be answered by other users, and they cannot answer calls to other users.</span></span>

### <a name="to-assign-a-group-number-and-enable-group-call-pickup-for-a-user"></a><span data-ttu-id="3aee6-109">Para atribuir um número de grupo e habilitar o atendimento de chamada de grupo para um usuário</span><span class="sxs-lookup"><span data-stu-id="3aee6-109">To assign a group number and enable Group Call Pickup for a user</span></span>

1. <span data-ttu-id="3aee6-110">Realize logon no computador em que você instalou a ferramenta SEFAUtil com direitos de administrador.</span><span class="sxs-lookup"><span data-stu-id="3aee6-110">Log on to the computer where you installed the SEFAUtil tool with administrator rights.</span></span>

2. <span data-ttu-id="3aee6-111">Na linha de comando, execute:</span><span class="sxs-lookup"><span data-stu-id="3aee6-111">At the command line, run:</span></span>

   ```
   SEFAUtil.exe sip:<sip address of user> /server:<pool FQDN> /enablegrouppickup:<group number>
   ```

    <span data-ttu-id="3aee6-112">Por exemplo, para atribuir o número de grupo 199 a um usuário:</span><span class="sxs-lookup"><span data-stu-id="3aee6-112">For example, to assign group number 199 to a user:</span></span>

   ```
   SEFAUtil.exe katarina@contoso.com /server:pool01.contoso.com /enablegrouppickup:199
   ```

## <a name="see-also"></a><span data-ttu-id="3aee6-113">Consulte também</span><span class="sxs-lookup"><span data-stu-id="3aee6-113">See also</span></span>

[<span data-ttu-id="3aee6-114">Desabilitar grupo retirada para usuários</span><span class="sxs-lookup"><span data-stu-id="3aee6-114">Disable Group Pickup for Users</span></span>](https://technet.microsoft.com/library/91b06f9e-2840-45a2-bbb3-6a29179b9a9f.aspx)

