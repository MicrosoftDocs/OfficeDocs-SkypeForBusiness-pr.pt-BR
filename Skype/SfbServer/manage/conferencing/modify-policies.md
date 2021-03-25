---
title: Modificar políticas de conferência no Skype for Business Server
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
description: 'Resumo: Saiba como modificar políticas de conferência no Skype for Business Server.'
ms.openlocfilehash: 6bbba82c9785e074da492eb66cbdd943dc0cea35
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51119420"
---
# <a name="modify-conferencing-policies-in-skype-for-business-server"></a>Modificar políticas de conferência no Skype for Business Server
 
**Resumo:** Saiba como modificar políticas de conferência no Skype for Business Server.
  
Você pode modificar políticas de conferência usando o Painel de Controle do Skype for Business Server ou usando o Shell de Gerenciamento do Skype for Business Server.
  
## <a name="modify-conferencing-policies-by-using-skype-for-business-server-control-panel"></a>Modificar políticas de conferência usando o Painel de Controle do Skype for Business Server

1. Por uma conta de usuário atribuída à função CsUserAdministrator role ou CsAdministrator, faça o login em qualquer computador na sua implantação interna.
    
2.  Abra o Painel de Controle do Skype for Business Server.
    
3. Na barra de navegação esquerda, clique **em Conferência** e em Política **de Conferência.**
    
4. Na lista de políticas de conferência, clique na política que você deseja alterar, clique em **Editar** e em **Mostrar detalhes.**
    
5. Em **Editar Política de Conferências**, modifique qualquer uma das configurações de política, exceto seu nome, que não pode ser modificado.
    
6. Clique em **Confirmar**.
    
## <a name="modify-conferencing-policies-by-using-skype-for-business-server-management-shell"></a>Modificar políticas de conferência usando o Shell de Gerenciamento do Skype for Business Server

Para modificar políticas de conferência, use o cmdlet **Set-CsConferencingPolicy.**
  
O exemplo a seguir modifica um valor de propriedade da política de conferência SalesConferencingPolicy. O comando define o valor da propriedade AllowConferenceRecording como False:
  
```PowerShell
Set-CsConferencingPolicy -Identity SalesConferencingPolicy -AllowConferenceRecording $False
```

Para obter mais informações, incluindo sintaxe completa e uma lista de parâmetros, consulte [Set-CsConferencingPolicy](/powershell/module/skype/set-csconferencingpolicy?view=skype-ps).
