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
# <a name="assign-conferencing-policies-in-skype-for-business-server-2015"></a>Atribuir políticas de conferência no Skype for Business Server 2015
 
**Resumo:** Saiba como atribuir políticas de conferência do Skype para Business Server 2015.
  
Você pode atribuir políticas de conferência aos usuários usando o Skype para o Shell de gerenciamento de servidor de negócios e o cmdlet **Grant-CsConferencingPolicy** .
  
## <a name="assign-conferencing-policies-by-using-skype-for-business-server-management-shell"></a>Atribuir políticas de conferência usando Skype do Shell de gerenciamento do servidor de negócios

No exemplo a seguir, a política SalesConferencingPolicy é atribuída ao usuário com a Identidade "Ken Myer":
  
```
Grant-CsConferencingPolicy -identity "Ken Myer" -PolicyName SalesConferencingPolicy

```

Neste exemplo, a política de conferência FinanceConferencingPolicy é atribuída a todos os usuários que tenham contas na unidade organizacional Finance. Para atribuir a mesma política a todos os usuários em uma OU (unidade organizacional) específica, o cmdlet Get-CsUser é usado para recuperar todas as contas dessa OU. Depois que todas as contas de usuário são recuperadas, essas informações são canalizadas para o cmdlet Grant-CsConferencingPolicy, que atribui a política FinanceConferencingPolicy a todos os usuários da coleção.
  
```
Get-CsUser -OU "ou=Finance,dc=litwareinc,dc=com" | Grant-CsConferencingPolicy -PolicyName FinanceConferencingPolicy

```

Para obter mais informações, incluindo a sintaxe completa e uma lista de parâmetros, consulte [Grant-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csconferencingpolicy?view=skype-ps).
  

