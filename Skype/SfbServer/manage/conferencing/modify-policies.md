---
title: Modificar políticas de conferência no Skype for Business Server 2015
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b40ba905-e74a-4456-ac94-65471bc2d66d
description: 'Resumo: Saiba como modificar políticas de conferência do Skype para Business Server 2015.'
ms.openlocfilehash: b0456db5d0c6131b3b3999a87fc824d6ee3b4b30
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/28/2018
---
# <a name="modify-conferencing-policies-in-skype-for-business-server-2015"></a>Modificar políticas de conferência no Skype for Business Server 2015
 
**Resumo:** Saiba como modificar políticas de conferência do Skype para Business Server 2015.
  
Você pode modificar as políticas de conferência usando Skype para o painel de controle do Business Server ou usando o Skype do Shell de gerenciamento do servidor de negócios.
  
## <a name="modify-conferencing-policies-by-using-skype-for-business-server-control-panel"></a>Modificar políticas de conferência usando Skype para o painel de controle do servidor de negócios

1. Usando uma conta de usuário atribuída à função CsUserAdministrator ou CsAdministrator, faça logon em qualquer computador de sua implantação interna.
    
2.  Abra o Skype para painel de controle do servidor de negócios.
    
3. Na barra de navegação esquerda, clique em **Conferência** e, em seguida, clique em **Política de Conferência**.
    
4. Na lista de políticas de conferência, clique na política que deseja alterar, em **Editar** e em **Mostrar detalhes**.
    
5. Em **Editar Política de Conferências**, modifique qualquer uma das configurações de política, exceto seu nome, que não pode ser modificado.
    
6. Clique em **Confirmar**.
    
## <a name="modify-conferencing-policies-by-using-skype-for-business-server-management-shell"></a>Modificar políticas de conferência usando Skype do Shell de gerenciamento do servidor de negócios

Para modificar políticas de conferência, use o cmdlet **Set-CsConferencingPolicy** .
  
O seguinte exemplo modifica um valor de propriedade da política de conferência SalesConferencingPolicy. O comando define o valor da propriedade AllowConferenceRecording como False:
  
```
Set-CsConferencingPolicy -Identity SalesConferencingPolicy -AllowConferenceRecording $False
```

Para obter mais informações, incluindo a sintaxe completa e uma lista de parâmetros, consulte [Set-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csconferencingpolicy?view=skype-ps).
  

