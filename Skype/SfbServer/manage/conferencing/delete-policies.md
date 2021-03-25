---
title: Excluir políticas de conferência no Skype for Business Server
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
ms.assetid: 497e6ca0-7a49-4f3e-9804-14414cf87b57
description: 'Resumo: Saiba como excluir políticas de conferência no Skype for Business Server.'
ms.openlocfilehash: 9aadaf82aea7f057cf1969f06d4257992b64a86a
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51119500"
---
# <a name="delete-conferencing-policies-in-skype-for-business-server"></a>Excluir políticas de conferência no Skype for Business Server
 
**Resumo:** Saiba como excluir políticas de conferência no Skype for Business Server.
  
Você pode excluir políticas de conferência usando o Painel de Controle do Skype for Business Server ou usando o Shell de Gerenciamento do Skype for Business Server.
  
## <a name="delete-conferencing-policies-by-using-skype-for-business-server-control-panel"></a>Excluir políticas de conferência usando o Painel de Controle do Skype for Business Server

1. Por uma conta de usuário atribuída à função CsUserAdministrator role ou CsAdministrator, faça o login em qualquer computador na sua implantação interna.
    
2.  Abra o Painel de Controle do Skype for Business Server.
    
3. Na barra de navegação esquerda, clique **em Conferência** e em Política **de Conferência.**
    
4. Na lista de políticas de conferência, clique no site ou na política de usuário que você deseja **excluir,** clique em **Editar** e clique em Excluir .
    
## <a name="delete-conferencing-policies-by-using-skype-for-business-server-management-shell"></a>Excluir políticas de conferência usando o Shell de Gerenciamento do Skype for Business Server

Para excluir políticas de conferência, use o cmdlet **Remove-CsConferencingPolicy.**
  
O comando a seguir remove a política de conferência com a identidade RedmondConferencingPolicy:
  
```PowerShell
Remove-CsConferencingPolicy -Identity "RedmondConferencingPolicy"
```

O próximo comando exclui todas as políticas de conferência que permitem que usuários externos gravem a conferência:
  
```PowerShell
Get-CsConferencingPolicy | Where-Object {$_.AllowExternalUsersToRecordMeetings -eq $True} | Remove-CsConferencingPolicy
```

Para obter mais informações, incluindo sintaxe completa e uma lista de parâmetros, consulte [Remove-CsConferencingPolicy](/powershell/module/skype/remove-csconferencingpolicy?view=skype-ps).
