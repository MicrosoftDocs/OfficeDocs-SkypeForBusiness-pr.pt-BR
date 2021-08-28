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
ms.localizationpriority: medium
ms.assetid: 497e6ca0-7a49-4f3e-9804-14414cf87b57
description: 'Resumo: saiba como excluir políticas de conferência no Skype for Business Server.'
ms.openlocfilehash: 62fce625133565e7e2ec53b0a5a4e37408f7e49e
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/26/2021
ms.locfileid: "58595553"
---
# <a name="delete-conferencing-policies-in-skype-for-business-server"></a>Excluir políticas de conferência no Skype for Business Server
 
**Resumo:** Saiba como excluir políticas de conferência em Skype for Business Server.
  
Você pode excluir políticas de conferência usando Skype for Business Server Painel de Controle ou usando Skype for Business Server Shell de Gerenciamento.
  
## <a name="delete-conferencing-policies-by-using-skype-for-business-server-control-panel"></a>Excluir políticas de conferência usando Skype for Business Server Painel de Controle

1. Por uma conta de usuário atribuída à função CsUserAdministrator role ou CsAdministrator, faça o login em qualquer computador na sua implantação interna.
    
2.  Abra Skype for Business Server Painel de Controle.
    
3. Na barra de navegação esquerda, clique **em Conferência** e em Política **de Conferência.**
    
4. Na lista de políticas de conferência, clique no site ou na política de usuário que você deseja **excluir,** clique em **Editar** e clique em Excluir .
    
## <a name="delete-conferencing-policies-by-using-skype-for-business-server-management-shell"></a>Excluir políticas de conferência usando Skype for Business Server Shell de Gerenciamento

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
