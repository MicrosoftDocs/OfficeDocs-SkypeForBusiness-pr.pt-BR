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
# <a name="assign-conferencing-policies-in-skype-for-business-server"></a>Atribuir políticas de conferência no Skype for Business Server
 
**Resumo:** Saiba como atribuir políticas de conferência no Skype for Business Server.
  
Você pode atribuir políticas de conferência aos usuários usando o Shell de Gerenciamento do Skype for Business Server e o cmdlet **Grant-CsConferencingPolicy.**
  
## <a name="assign-conferencing-policies-by-using-skype-for-business-server-management-shell"></a>Atribuir políticas de conferência usando o Shell de Gerenciamento do Skype for Business Server

No exemplo a seguir, a política SalesConferencingPolicy é atribuída ao usuário com a identidade "Ken Myer":
  
```PowerShell
Grant-CsConferencingPolicy -identity "Ken Myer" -PolicyName SalesConferencingPolicy
```

No próximo exemplo, a política de conferência FinanceConferencingPolicy é atribuída a todos os usuários que têm contas na unidade organizacional Finanças. Para atribuir a mesma diretiva a todos os usuários em uma OU (unidade organizacional) específica, o cmdlet Get-CsUser é usado para recuperar todas as contas dessa OU. Depois que as contas de usuário são recuperadas, essas informações são canalizou para o cmdlet Grant-CsConferencingPolicy, que atribui a política FinanceConferencingPolicy a cada usuário na coleção:
  
```PowerShell
Get-CsUser -OU "ou=Finance,dc=litwareinc,dc=com" | Grant-CsConferencingPolicy -PolicyName FinanceConferencingPolicy
```

Para obter mais informações, incluindo sintaxe completa e uma lista de parâmetros, [consulte Grant-CsConferencingPolicy](/powershell/module/skype/grant-csconferencingpolicy?view=skype-ps).
