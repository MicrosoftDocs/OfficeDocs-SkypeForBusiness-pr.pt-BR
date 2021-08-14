---
title: Modificar as configurações de reunião no Skype for Business Server
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
description: 'Resumo: saiba como modificar as configurações de reunião no Skype for Business Server.'
ms.openlocfilehash: e1b283c5d50c955464d4af9b8f92f9e210f60f35a1fad5320c9f6bb8b6ede11d
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2021
ms.locfileid: "54343455"
---
# <a name="modify-meeting-configuration-settings-in-skype-for-business-server"></a>Modificar as configurações de reunião no Skype for Business Server
 
**Resumo:** Saiba como modificar as configurações de reunião no Skype for Business Server.
  
Você pode modificar as definições de configuração de reunião usando Skype for Business Server Painel de Controle ou usando Skype for Business Server Shell de Gerenciamento.
  
## <a name="modify-meeting-configuration-settings-by-using-skype-for-business-server-control-panel"></a>Modificar definições de configuração de reunião usando Skype for Business Server Painel de Controle

1. Por uma conta de usuário atribuída à função CsUserAdministrator role ou CsAdministrator, faça o login em qualquer computador na sua implantação interna.
    
2.  Abra Skype for Business Server Painel de Controle.
    
3. Na barra de navegação esquerda, clique **em Conferência** e em **Configuração de Reunião.**
    
4. Na lista de configurações de reunião, clique na configuração que você deseja alterar, clique em **Editar** e em **Mostrar detalhes.**
    
5. Em **Editar configuração de reunião**, modifique qualquer definição da configuração, exceto o nome da configuração, que não pode ser modificado.
    
6. Clique em **Confirmar**.
    
## <a name="modify-meeting-configuration-settings-by-using-skype-for-business-server-management-shell"></a>Modificar configurações de reunião usando o Shell de Gerenciamento Skype for Business Server Gerenciamento

Para modificar as configurações de reunião, use o cmdlet **Set-CsMeetingConfiguration.**
  
O comando mostrado no exemplo a seguir modifica as configurações de reunião atribuídas ao site redmond (-Identity site:Redmond). Nesse caso, o valor da propriedade DesignateAsPresenter é definido como Todos:
  
```PowerShell
Set-CsMeetingConfiguration -Identity "site:Redmond" -DesignateAsPresenter "Everyone"
```

Para obter mais informações, incluindo uma lista completa de parâmetros, consulte [Set-CsMeetingConfiguration](/powershell/module/skype/set-csmeetingconfiguration?view=skype-ps).
