---
title: Excluir configurações de reunião no Skype for Business Server
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
ms.assetid: 8ebafb86-13b9-468e-beda-f85f6786da85
description: 'Resumo: saiba como excluir as configurações de reunião no Skype for Business Server.'
ms.openlocfilehash: b0c739f0149b4e28ca23df1437caab0505e1118d
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51119490"
---
# <a name="delete-meeting-configuration-settings-in-skype-for-business-server"></a>Excluir configurações de reunião no Skype for Business Server
 
**Resumo:** Saiba como excluir as configurações de reunião no Skype for Business Server.
  
Você pode excluir as configurações de reunião usando o Painel de Controle do Skype for Business Server ou usando o Shell de Gerenciamento do Skype for Business Server.
  
Você pode excluir uma configuração de site ou usuário, mas não pode excluir a configuração global. Se você tentar excluir a configuração global, ela será redefinida automaticamente para os valores padrão.
  
## <a name="delete-meeting-configuration-settings-by-using-skype-for-business-server-control-panel"></a>Excluir configurações de reunião usando o Painel de Controle do Skype for Business Server

1. Por uma conta de usuário atribuída à função CsUserAdministrator role ou CsAdministrator, faça o login em qualquer computador na sua implantação interna.
    
2.  Abra o Painel de Controle do Skype for Business Server.
    
3. Na barra de navegação esquerda, clique **em Conferência** e em **Configuração de Reunião.**
    
4. Na lista de configurações de reunião, clique na configuração do site ou pool que você deseja excluir, clique em **Editar** e clique em **Excluir**.
    
## <a name="delete-meeting-configuration-settings-by-using-skype-for-business-server-management-shell"></a>Excluir configurações de reunião usando o Shell de Gerenciamento do Skype for Business Server

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
