---
title: Excluir configurações de reunião no Skype for Business Server
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
ms.assetid: 8ebafb86-13b9-468e-beda-f85f6786da85
description: 'Resumo: saiba como excluir as configurações de reunião no Skype for Business Server.'
ms.openlocfilehash: 95eda4da393f1eb677fc331ffb824e6222e35113
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/08/2021
ms.locfileid: "60830895"
---
# <a name="delete-meeting-configuration-settings-in-skype-for-business-server"></a>Excluir configurações de reunião no Skype for Business Server
 
**Resumo:** Saiba como excluir as configurações de reunião no Skype for Business Server.
  
Você pode excluir as configurações de reunião usando o Painel de Controle Skype for Business Server ou usando Skype for Business Server Shell de Gerenciamento.
  
Você pode excluir uma configuração de site ou usuário, mas não pode excluir a configuração global. Se você tentar excluir a configuração global, ela será redefinida automaticamente para os valores padrão.
  
## <a name="delete-meeting-configuration-settings-by-using-skype-for-business-server-control-panel"></a>Excluir configurações de reunião usando Skype for Business Server Painel de Controle

1. Por uma conta de usuário atribuída à função CsUserAdministrator role ou CsAdministrator, faça o login em qualquer computador na sua implantação interna.
    
2.  Abra Skype for Business Server Painel de Controle.
    
3. Na barra de navegação esquerda, clique **em Conferência** e em **Configuração de Reunião.**
    
4. Na lista de configurações de reunião, clique na configuração do site ou pool que você deseja excluir, clique em **Editar** e clique em **Excluir**.
    
## <a name="delete-meeting-configuration-settings-by-using-skype-for-business-server-management-shell"></a>Excluir configurações de reunião usando o Shell de Gerenciamento Skype for Business Server Gerenciamento

Para excluir as configurações de reunião, use o cmdlet **Remove-CsMeetingConfiguration.**
  
O comando a seguir remove as configurações de reunião aplicadas ao site redmond:
  
```PowerShell
Remove-CsMeetingConfiguration -Identity "site:Redmond"
```

O próximo comando remove todas as configurações de reunião aplicadas ao escopo do site:
  
```PowerShell
Get-CsMeetingConfiguration -Filter "site:*" | Remove-CsMeetingConfiguration
```

Para obter mais informações, incluindo uma lista completa de parâmetros, consulte [Remove-CsMeetingConfiguration](/powershell/module/skype/remove-csmeetingconfiguration?view=skype-ps).
