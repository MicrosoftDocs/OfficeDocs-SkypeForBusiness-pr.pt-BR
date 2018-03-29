---
title: Excluir políticas de conferência no Skype for Business Server 2015
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 497e6ca0-7a49-4f3e-9804-14414cf87b57
description: 'Resumo: Saiba como excluir políticas de conferência do Skype para Business Server 2015.'
ms.openlocfilehash: 783e2ef4c1bc0732fd93949427cea21c5ca165ea
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/28/2018
---
# <a name="delete-conferencing-policies-in-skype-for-business-server-2015"></a>Excluir políticas de conferência no Skype for Business Server 2015
 
**Resumo:** Aprenda a excluir políticas de conferência do Skype para Business Server 2015.
  
Você pode excluir diretivas de conferência usando Skype para o painel de controle do Business Server ou usando o Skype do Shell de gerenciamento do servidor de negócios.
  
## <a name="delete-conferencing-policies-by-using-skype-for-business-server-control-panel"></a>Excluir diretivas de conferência usando o Skype para painel de controle do servidor de negócios

1. Usando uma conta de usuário atribuída à função CsUserAdministrator ou CsAdministrator, faça logon em qualquer computador de sua implantação interna.
    
2.  Abra o Skype para painel de controle do servidor de negócios.
    
3. Na barra de navegação esquerda, clique em **Conferência** e, então, clique em **Política de Conferência**.
    
4. Na lista de políticas de conferência, clique na política de site ou usuário que deseja excluir, clique em **Editar** e em **Excluir**.
    
## <a name="delete-conferencing-policies-by-using-skype-for-business-server-management-shell"></a>Excluir diretivas de conferência usando o Skype do Shell de gerenciamento do servidor de negócios

Para excluir as políticas de conferência, use o cmdlet **Remove-CsConferencingPolicy**:
  
O comando a seguir remove a política de conferência com a identidade RedmondConferencingPolicy:
  
```
Remove-CsConferencingPolicy -Identity "RedmondConferencingPolicy"
```

O comando a seguir exclui todas as políticas de conferência que permitem que os usuários externos registrem a conferência:
  
```
Get-CsConferencingPolicy | Where-Object {$_.AllowExternalUsersToRecordMeetings -eq $True} | Remove-CsConferencingPolicy
```

Para obter mais informações, incluindo a sintaxe completa e uma lista de parâmetros, consulte [Remove-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/remove-csconferencingpolicy?view=skype-ps).
  

