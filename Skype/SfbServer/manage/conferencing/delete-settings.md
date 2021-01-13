---
title: Excluir definições de configuração de reunião no Skype for Business Server
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
description: 'Resumo: Saiba como excluir definições de configuração de reunião no Skype for Business Server.'
ms.openlocfilehash: 418ce7418be5a09658626491121dd2e2b3542110
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49828173"
---
# <a name="delete-meeting-configuration-settings-in-skype-for-business-server"></a>Excluir definições de configuração de reunião no Skype for Business Server
 
**Resumo:** Saiba como excluir as definições de configuração de reunião no Skype for Business Server.
  
Você pode excluir as definições de configuração de reunião usando o Painel de Controle do Skype for Business Server ou o Shell de Gerenciamento do Skype for Business Server.
  
Você pode excluir uma configuração de site ou de usuário, mas não pode excluir a configuração global. Se você tentar excluir a configuração global, ela será automaticamente redefinida para os valores padrão.
  
## <a name="delete-meeting-configuration-settings-by-using-skype-for-business-server-control-panel"></a>Excluir definições de configuração de reunião usando o Painel de Controle do Skype for Business Server

1. Por uma conta de usuário atribuída à função CsUserAdministrator role ou CsAdministrator, faça o login em qualquer computador na sua implantação interna.
    
2.  Abra o Painel de Controle do Skype for Business Server.
    
3. Na barra de navegação esquerda, clique **em Conferência e** em Configuração de **Reunião.**
    
4. Na lista de configurações de reunião, clique na configuração de site ou pool que deseja excluir, clique em **Editar** e em **Excluir.**
    
## <a name="delete-meeting-configuration-settings-by-using-skype-for-business-server-management-shell"></a>Excluir definições de configuração de reunião usando o Shell de Gerenciamento do Skype for Business Server

Para excluir as configurações de reunião, use o cmdlet **Remove-CsMeetingConfiguration.**
  
O comando a seguir remove as definições de configuração de reunião aplicadas ao site Redmond:
  
```PowerShell
Remove-CsMeetingConfiguration -Identity "site:Redmond"
```

O próximo comando remove todas as definições de configuração de reunião aplicadas ao escopo do site:
  
```PowerShell
Get-CsMeetingConfiguration -Filter "site:*" | Remove-CsMeetingConfiguration
```

Para obter mais informações, incluindo uma lista completa de parâmetros, consulte [Remove-CsMeetingConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-csmeetingconfiguration?view=skype-ps).
  

