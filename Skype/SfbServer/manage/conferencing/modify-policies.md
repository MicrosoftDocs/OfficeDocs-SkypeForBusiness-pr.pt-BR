---
title: Modificar políticas de conferência em Skype for Business Server
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: b40ba905-e74a-4456-ac94-65471bc2d66d
description: 'Resumo: saiba como modificar políticas de conferência em Skype for Business Server.'
ms.openlocfilehash: 0c9b2f24fac8303a28f4e7408d23e950f5586785
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/08/2021
ms.locfileid: "60852075"
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
