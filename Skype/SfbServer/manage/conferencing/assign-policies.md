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
ms.openlocfilehash: d13710d2cc4f6edf1cee16cbc9aa77799ceec8a4
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49806471"
---
# <a name="assign-conferencing-policies-in-skype-for-business-server"></a><span data-ttu-id="c35c2-103">Atribuir políticas de conferência no Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="c35c2-103">Assign conferencing policies in Skype for Business Server</span></span>
 
<span data-ttu-id="c35c2-104">**Resumo:** Saiba como atribuir políticas de conferência no Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="c35c2-104">**Summary:** Learn how to assign conferencing policies in Skype for Business Server.</span></span>
  
<span data-ttu-id="c35c2-105">É possível atribuir políticas de conferência aos usuários usando o Shell de Gerenciamento do Skype for Business Server e o cmdlet **Grant-CsConferencingPolicy.**</span><span class="sxs-lookup"><span data-stu-id="c35c2-105">You can assign conferencing policies to users by using Skype for Business Server Management Shell and the **Grant-CsConferencingPolicy** cmdlet.</span></span>
  
## <a name="assign-conferencing-policies-by-using-skype-for-business-server-management-shell"></a><span data-ttu-id="c35c2-106">Atribuir políticas de conferência usando o Shell de Gerenciamento do Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="c35c2-106">Assign conferencing policies by using Skype for Business Server Management Shell</span></span>

<span data-ttu-id="c35c2-107">No exemplo a seguir, a política SalesConferencingPolicy é atribuída ao usuário com a Identidade "Ken Myer":</span><span class="sxs-lookup"><span data-stu-id="c35c2-107">In the following example, the policy SalesConferencingPolicy is assigned to the user with the Identity "Ken Myer":</span></span>
  
```PowerShell
Grant-CsConferencingPolicy -identity "Ken Myer" -PolicyName SalesConferencingPolicy
```

<span data-ttu-id="c35c2-108">No próximo exemplo, a política de conferência FinanceConferencingPolicy é atribuída a todos os usuários que têm contas na unidade organizacional Finance.</span><span class="sxs-lookup"><span data-stu-id="c35c2-108">In the next example, the conferencing policy FinanceConferencingPolicy is assigned to all the users who have accounts in the Finance organizational unit.</span></span> <span data-ttu-id="c35c2-109">Para atribuir a mesma diretiva a todos os usuários em uma OU (unidade organizacional) específica, o cmdlet Get-CsUser é usado para recuperar todas as contas dessa OU.</span><span class="sxs-lookup"><span data-stu-id="c35c2-109">To assign the same policy to all the users in a given organizational unit (OU), the Get-CsUser cmdlet is used to retrieve all the accounts in that OU.</span></span> <span data-ttu-id="c35c2-110">Depois que as contas de usuário são recuperadas, essas informações são canalizar para o cmdlet Grant-CsConferencingPolicy, que atribui a política FinanceConferencingPolicy a cada usuário no conjunto:</span><span class="sxs-lookup"><span data-stu-id="c35c2-110">After the user accounts have been retrieved, that information is then piped to the Grant-CsConferencingPolicy cmdlet, which assigns the FinanceConferencingPolicy policy to each user in the collection:</span></span>
  
```PowerShell
Get-CsUser -OU "ou=Finance,dc=litwareinc,dc=com" | Grant-CsConferencingPolicy -PolicyName FinanceConferencingPolicy
```

<span data-ttu-id="c35c2-111">Para obter mais informações, incluindo sintaxe completa e uma lista de parâmetros, consulte [Grant-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csconferencingpolicy?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="c35c2-111">For more information, including complete syntax and a list of parameters, see [Grant-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csconferencingpolicy?view=skype-ps).</span></span>
  

