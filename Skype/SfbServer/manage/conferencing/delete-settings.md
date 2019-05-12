---
title: Excluir configurações de reunião no Skype para Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 8ebafb86-13b9-468e-beda-f85f6786da85
description: 'Resumo: Saiba como excluir configurações de reunião no Skype para Business Server.'
ms.openlocfilehash: 2fbb278745eba392016b163be8f59a3abb07b47d
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "33919378"
---
# <a name="delete-meeting-configuration-settings-in-skype-for-business-server"></a>Excluir configurações de reunião no Skype para Business Server
 
**Resumo:** Saiba como excluir configurações de reunião no Skype para Business Server.
  
Você pode excluir configurações de reunião usando o Skype para painel de controle do Business Server ou usando Skype do Shell de gerenciamento do servidor de negócios.
  
Você pode excluir uma configuração de site ou de usuário, mas não a configuração global. Se você tentar excluir a configuração global, ela será automaticamente redefinida para os valores padrão.
  
## <a name="delete-meeting-configuration-settings-by-using-skype-for-business-server-control-panel"></a>Excluir configurações de reunião usando o Skype para o painel de controle do servidor de negócios

1. Usando uma conta de usuário atribuída à função CsUserAdministrator ou CsAdministrator, faça logon em qualquer computador de sua implantação interna.
    
2.  Abra o Skype para painel de controle do servidor de negócios.
    
3. Na barra de navegação à esquerda, clique em **Conferência** e em **Configuração da reunião**.
    
4. Na lista de configuração de reunião, clique na configuração de site ou pool que deseja excluir, clique em **Editar** e em **Excluir**.
    
## <a name="delete-meeting-configuration-settings-by-using-skype-for-business-server-management-shell"></a>Excluir configurações de reunião usando o Skype do Shell de gerenciamento do servidor de negócios

Para excluir as configurações de reunião, use o cmdlet **Remove-CsMeetingConfiguration**.
  
O comando a seguir remove as definições de configuração de reunião aplicadas ao site de Redmond:
  
```
Remove-CsMeetingConfiguration -Identity "site:Redmond"
```

O próximo comando remove todas as definições de configuração de reunião aplicadas ao escopo do site:
  
```
Get-CsMeetingConfiguration -Filter "site:*" | Remove-CsMeetingConfiguration
```

Para obter mais informações, incluindo uma lista completa de parâmetros, consulte [Remove-CsMeetingConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-csmeetingconfiguration?view=skype-ps).
  

