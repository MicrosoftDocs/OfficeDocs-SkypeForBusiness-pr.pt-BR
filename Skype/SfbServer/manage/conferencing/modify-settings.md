---
title: Modificar configurações de reunião no Skype for Business Server
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
ms.assetid: 11d1f9ac-0029-429b-be2b-d7591abfc192
description: 'Resumo: Saiba como modificar as configurações de reunião no Skype for Business Server.'
ms.openlocfilehash: 2f0d1220312ac810d26fdd4691492133e54db9b6
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51119410"
---
# <a name="modify-meeting-configuration-settings-in-skype-for-business-server"></a>Modificar configurações de reunião no Skype for Business Server
 
**Resumo:** Saiba como modificar as configurações de reunião no Skype for Business Server.
  
Você pode modificar as configurações de reunião usando o Painel de Controle do Skype for Business Server ou usando o Shell de Gerenciamento do Skype for Business Server.
  
## <a name="modify-meeting-configuration-settings-by-using-skype-for-business-server-control-panel"></a>Modificar configurações de reunião usando o Painel de Controle do Skype for Business Server

1. Por uma conta de usuário atribuída à função CsUserAdministrator role ou CsAdministrator, faça o login em qualquer computador na sua implantação interna.
    
2.  Abra o Painel de Controle do Skype for Business Server.
    
3. Na barra de navegação esquerda, clique **em Conferência** e em **Configuração de Reunião.**
    
4. Na lista de configurações de reunião, clique na configuração que você deseja alterar, clique em **Editar** e em **Mostrar detalhes.**
    
5. Em **Editar configuração de reunião**, modifique qualquer definição da configuração, exceto o nome da configuração, que não pode ser modificado.
    
6. Clique em **Confirmar**.
    
## <a name="modify-meeting-configuration-settings-by-using-skype-for-business-server-management-shell"></a>Modificar configurações de reunião usando o Shell de Gerenciamento do Skype for Business Server

Para modificar as configurações de reunião, use o cmdlet **Set-CsMeetingConfiguration.**
  
O comando mostrado no exemplo a seguir modifica as configurações de reunião atribuídas ao site redmond (-Identity site:Redmond). Nesse caso, o valor da propriedade DesignateAsPresenter é definido como Todos:
  
```PowerShell
Set-CsMeetingConfiguration -Identity "site:Redmond" -DesignateAsPresenter "Everyone"
```

Para obter mais informações, incluindo uma lista completa de parâmetros, consulte [Set-CsMeetingConfiguration](/powershell/module/skype/set-csmeetingconfiguration?view=skype-ps).
