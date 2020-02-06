---
title: Atribuir políticas de conferência no Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: f384d19b-0950-4ec6-9d93-2c5958b83e71
description: 'Resumo: saiba como atribuir políticas de conferência no Skype for Business Server.'
ms.openlocfilehash: c5dfb9c2aa186bf199a066c82e3687aade564905
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41818653"
---
# <a name="assign-conferencing-policies-in-skype-for-business-server"></a>Atribuir políticas de conferência no Skype for Business Server
 
**Resumo:** Saiba como atribuir políticas de conferência no Skype for Business Server.
  
Você pode atribuir políticas de conferência aos usuários usando o Shell de gerenciamento do Skype for Business Server e o cmdlet **Grant-CsConferencingPolicy** .
  
## <a name="assign-conferencing-policies-by-using-skype-for-business-server-management-shell"></a>Atribuir políticas de conferência usando o Shell de gerenciamento do Skype for Business Server

No exemplo a seguir, a política SalesConferencingPolicy é atribuída ao usuário com a Identidade "Ken Myer":
  
```PowerShell
Grant-CsConferencingPolicy -identity "Ken Myer" -PolicyName SalesConferencingPolicy
```

Neste exemplo, a política de conferência FinanceConferencingPolicy é atribuída a todos os usuários que tenham contas na unidade organizacional Finance. Para atribuir a mesma política a todos os usuários em uma OU (unidade organizacional) específica, o cmdlet Get-CsUser é usado para recuperar todas as contas dessa OU. Depois que todas as contas de usuário são recuperadas, essas informações são canalizadas para o cmdlet Grant-CsConferencingPolicy, que atribui a política FinanceConferencingPolicy a todos os usuários da coleção.
  
```PowerShell
Get-CsUser -OU "ou=Finance,dc=litwareinc,dc=com" | Grant-CsConferencingPolicy -PolicyName FinanceConferencingPolicy
```

Para obter mais informações, incluindo a sintaxe completa e uma lista de parâmetros, veja [Grant-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csconferencingpolicy?view=skype-ps).
  

