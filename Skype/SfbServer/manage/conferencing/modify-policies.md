---
title: Modificar políticas de conferência em Skype for Business Server
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
ms.assetid: b40ba905-e74a-4456-ac94-65471bc2d66d
description: 'Resumo: saiba como modificar políticas de conferência em Skype for Business Server.'
ms.openlocfilehash: 5676a6bc0970a98fa76357deb1403c6b2337920273262c0a76a465b33d5d18c4
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2021
ms.locfileid: "54290349"
---
# <a name="modify-conferencing-policies-in-skype-for-business-server"></a>Modificar políticas de conferência em Skype for Business Server
 
**Resumo:** Saiba como modificar políticas de conferência em Skype for Business Server.
  
Você pode modificar políticas de conferência usando Skype for Business Server Painel de Controle ou usando Skype for Business Server Shell de Gerenciamento.
  
## <a name="modify-conferencing-policies-by-using-skype-for-business-server-control-panel"></a>Modificar políticas de conferência usando Skype for Business Server Painel de Controle

1. Por uma conta de usuário atribuída à função CsUserAdministrator role ou CsAdministrator, faça o login em qualquer computador na sua implantação interna.
    
2.  Abra Skype for Business Server Painel de Controle.
    
3. Na barra de navegação esquerda, clique **em Conferência** e em Política **de Conferência.**
    
4. Na lista de políticas de conferência, clique na política que você deseja alterar, clique em **Editar** e em **Mostrar detalhes.**
    
5. Em **Editar Política de Conferências**, modifique qualquer uma das configurações de política, exceto seu nome, que não pode ser modificado.
    
6. Clique em **Confirmar**.
    
## <a name="modify-conferencing-policies-by-using-skype-for-business-server-management-shell"></a>Modificar políticas de conferência usando o Shell de Gerenciamento Skype for Business Server Gerenciamento

Para modificar políticas de conferência, use o cmdlet **Set-CsConferencingPolicy.**
  
O exemplo a seguir modifica um valor de propriedade da política de conferência SalesConferencingPolicy. O comando define o valor da propriedade AllowConferenceRecording como False:
  
```PowerShell
Set-CsConferencingPolicy -Identity SalesConferencingPolicy -AllowConferenceRecording $False
```

Para obter mais informações, incluindo sintaxe completa e uma lista de parâmetros, consulte [Set-CsConferencingPolicy](/powershell/module/skype/set-csconferencingpolicy?view=skype-ps).
