---
title: Atribuir políticas de conferência no Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: f384d19b-0950-4ec6-9d93-2c5958b83e71
description: 'Resumo: saiba como atribuir políticas de conferência no Skype for Business Server.'
ms.openlocfilehash: 61082a9189b085c852e7593207fc86dcc6509139
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51099157"
---
# <a name="assign-conferencing-policies-in-skype-for-business-server"></a><span data-ttu-id="63f91-103">Atribuir políticas de conferência no Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="63f91-103">Assign conferencing policies in Skype for Business Server</span></span>
 
<span data-ttu-id="63f91-104">**Resumo:** Saiba como atribuir políticas de conferência no Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="63f91-104">**Summary:** Learn how to assign conferencing policies in Skype for Business Server.</span></span>
  
<span data-ttu-id="63f91-105">Você pode atribuir políticas de conferência aos usuários usando o Shell de Gerenciamento do Skype for Business Server e o cmdlet **Grant-CsConferencingPolicy.**</span><span class="sxs-lookup"><span data-stu-id="63f91-105">You can assign conferencing policies to users by using Skype for Business Server Management Shell and the **Grant-CsConferencingPolicy** cmdlet.</span></span>
  
## <a name="assign-conferencing-policies-by-using-skype-for-business-server-management-shell"></a><span data-ttu-id="63f91-106">Atribuir políticas de conferência usando o Shell de Gerenciamento do Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="63f91-106">Assign conferencing policies by using Skype for Business Server Management Shell</span></span>

<span data-ttu-id="63f91-107">No exemplo a seguir, a política SalesConferencingPolicy é atribuída ao usuário com a identidade "Ken Myer":</span><span class="sxs-lookup"><span data-stu-id="63f91-107">In the following example, the policy SalesConferencingPolicy is assigned to the user with the Identity "Ken Myer":</span></span>
  
```PowerShell
Grant-CsConferencingPolicy -identity "Ken Myer" -PolicyName SalesConferencingPolicy
```

<span data-ttu-id="63f91-108">No próximo exemplo, a política de conferência FinanceConferencingPolicy é atribuída a todos os usuários que têm contas na unidade organizacional Finanças.</span><span class="sxs-lookup"><span data-stu-id="63f91-108">In the next example, the conferencing policy FinanceConferencingPolicy is assigned to all the users who have accounts in the Finance organizational unit.</span></span> <span data-ttu-id="63f91-109">Para atribuir a mesma diretiva a todos os usuários em uma OU (unidade organizacional) específica, o cmdlet Get-CsUser é usado para recuperar todas as contas dessa OU.</span><span class="sxs-lookup"><span data-stu-id="63f91-109">To assign the same policy to all the users in a given organizational unit (OU), the Get-CsUser cmdlet is used to retrieve all the accounts in that OU.</span></span> <span data-ttu-id="63f91-110">Depois que as contas de usuário são recuperadas, essas informações são canalizou para o cmdlet Grant-CsConferencingPolicy, que atribui a política FinanceConferencingPolicy a cada usuário na coleção:</span><span class="sxs-lookup"><span data-stu-id="63f91-110">After the user accounts have been retrieved, that information is then piped to the Grant-CsConferencingPolicy cmdlet, which assigns the FinanceConferencingPolicy policy to each user in the collection:</span></span>
  
```PowerShell
Get-CsUser -OU "ou=Finance,dc=litwareinc,dc=com" | Grant-CsConferencingPolicy -PolicyName FinanceConferencingPolicy
```

<span data-ttu-id="63f91-111">Para obter mais informações, incluindo sintaxe completa e uma lista de parâmetros, [consulte Grant-CsConferencingPolicy](/powershell/module/skype/grant-csconferencingpolicy?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="63f91-111">For more information, including complete syntax and a list of parameters, see [Grant-CsConferencingPolicy](/powershell/module/skype/grant-csconferencingpolicy?view=skype-ps).</span></span>
