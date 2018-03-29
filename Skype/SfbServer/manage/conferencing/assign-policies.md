---
title: Atribuir políticas de conferência no Skype for Business Server 2015
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: f384d19b-0950-4ec6-9d93-2c5958b83e71
description: 'Resumo: Saiba como atribuir políticas de conferência do Skype para Business Server 2015.'
ms.openlocfilehash: 532065bee6f33b492639f5bcf949e29b082c5e84
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/28/2018
---
# <a name="assign-conferencing-policies-in-skype-for-business-server-2015"></a><span data-ttu-id="07df5-103">Atribuir políticas de conferência no Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="07df5-103">Assign conferencing policies in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="07df5-104">**Resumo:** Saiba como atribuir políticas de conferência do Skype para Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="07df5-104">**Summary:** Learn how to assign conferencing policies in Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="07df5-105">Você pode atribuir políticas de conferência aos usuários usando o Skype para o Shell de gerenciamento de servidor de negócios e o cmdlet **Grant-CsConferencingPolicy** .</span><span class="sxs-lookup"><span data-stu-id="07df5-105">You can assign conferencing policies to users by using Skype for Business Server Management Shell and the **Grant-CsConferencingPolicy** cmdlet.</span></span>
  
## <a name="assign-conferencing-policies-by-using-skype-for-business-server-management-shell"></a><span data-ttu-id="07df5-106">Atribuir políticas de conferência usando Skype do Shell de gerenciamento do servidor de negócios</span><span class="sxs-lookup"><span data-stu-id="07df5-106">Assign conferencing policies by using Skype for Business Server Management Shell</span></span>

<span data-ttu-id="07df5-107">No exemplo a seguir, a política SalesConferencingPolicy é atribuída ao usuário com a Identidade "Ken Myer":</span><span class="sxs-lookup"><span data-stu-id="07df5-107">In the following example, the policy SalesConferencingPolicy is assigned to the user with the Identity "Ken Myer":</span></span>
  
```
Grant-CsConferencingPolicy -identity "Ken Myer" -PolicyName SalesConferencingPolicy

```

<span data-ttu-id="07df5-p101">Neste exemplo, a política de conferência FinanceConferencingPolicy é atribuída a todos os usuários que tenham contas na unidade organizacional Finance. Para atribuir a mesma política a todos os usuários em uma OU (unidade organizacional) específica, o cmdlet Get-CsUser é usado para recuperar todas as contas dessa OU. Depois que todas as contas de usuário são recuperadas, essas informações são canalizadas para o cmdlet Grant-CsConferencingPolicy, que atribui a política FinanceConferencingPolicy a todos os usuários da coleção.</span><span class="sxs-lookup"><span data-stu-id="07df5-p101">In the next example, the conferencing policy FinanceConferencingPolicy is assigned to all the users who have accounts in the Finance organizational unit. To assign the same policy to all the users in a given organizational unit (OU), the Get-CsUser cmdlet is used to retrieve all the accounts in that OU. After the user accounts have been retrieved, that information is then piped to the Grant-CsConferencingPolicy cmdlet, which assigns the FinanceConferencingPolicy policy to each user in the collection:</span></span>
  
```
Get-CsUser -OU "ou=Finance,dc=litwareinc,dc=com" | Grant-CsConferencingPolicy -PolicyName FinanceConferencingPolicy

```

<span data-ttu-id="07df5-111">Para obter mais informações, incluindo a sintaxe completa e uma lista de parâmetros, consulte [Grant-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csconferencingpolicy?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="07df5-111">For more information, including complete syntax and a list of parameters, see [Grant-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csconferencingpolicy?view=skype-ps).</span></span>
  

