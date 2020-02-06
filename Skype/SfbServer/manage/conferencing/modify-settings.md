---
title: Modificar as configurações de configuração de reunião no Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 11d1f9ac-0029-429b-be2b-d7591abfc192
description: 'Resumo: saiba como modificar as configurações de configuração de uma reunião no Skype for Business Server.'
ms.openlocfilehash: 893e3fb8c9c441f8dc515eaf3a8a4aaa1ff04620
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41818492"
---
# <a name="modify-meeting-configuration-settings-in-skype-for-business-server"></a>Modificar as configurações de configuração de reunião no Skype for Business Server
 
**Resumo:** Saiba como modificar as configurações de configuração de reunião no Skype for Business Server.
  
Você pode modificar as configurações de configuração da reunião usando o painel de controle do Skype for Business Server ou usando o Shell de gerenciamento do Skype for Business Server.
  
## <a name="modify-meeting-configuration-settings-by-using-skype-for-business-server-control-panel"></a>Modificar definições de configuração de reunião usando o painel de controle do Skype for Business Server

1. Usando uma conta de usuário atribuída à função CsUserAdministrator ou CsAdministrator, faça logon em qualquer computador de sua implantação interna.
    
2.  Abra o painel de controle do Skype for Business Server.
    
3. Na barra de navegação à esquerda, clique em **Conferência**e em **Configuração da reunião**.
    
4. Na lista de configurações da reunião, clique na configuração que deseja alterar, em **Editar** e, em seguida, clique em **Exibir detalhes**.
    
5. Em **Editar configuração da reunião**, modifique qualquer definição da configuração, exceto o nome da configuração, que não pode ser modificado.
    
6. Clique em **Confirmar**.
    
## <a name="modify-meeting-configuration-settings-by-using-skype-for-business-server-management-shell"></a>Modificar definições de configuração de reunião usando o Shell de gerenciamento do Skype for Business Server

Para modificar as definições de configuração de reunião, use o cmdlet **Set-CsMeetingConfiguration**.
  
O comando mostrado no exemplo a seguir modifica as definições de configuração de reuniões atribuídas ao site de Redmond (-Identity site:Redmond). Neste caso, o valor da propriedade DesignateAsPresenter é definido como Everyone:
  
```PowerShell
Set-CsMeetingConfiguration -Identity "site:Redmond" -DesignateAsPresenter "Everyone"
```

Para obter mais informações, incluindo uma lista completa de parâmetros, consulte [set-CsMeetingConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csmeetingconfiguration?view=skype-ps).
  

