---
title: Modificar configurações de reunião no Skype para Business Server
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 11d1f9ac-0029-429b-be2b-d7591abfc192
description: 'Resumo: Saiba como modificar configurações de reunião no Skype para Business Server.'
ms.openlocfilehash: b4b8307711fcf7b120c867debe5ab3e2978f6ef7
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/24/2018
ms.locfileid: "20978964"
---
# <a name="modify-meeting-configuration-settings-in-skype-for-business-server"></a>Modificar configurações de reunião no Skype para Business Server
 
**Resumo:** Saiba como modificar configurações de reunião no Skype para Business Server.
  
Você pode modificar configurações de reunião usando o Skype para painel de controle do Business Server ou usando Skype do Shell de gerenciamento do servidor de negócios.
  
## <a name="modify-meeting-configuration-settings-by-using-skype-for-business-server-control-panel"></a>Modificar configurações de reunião usando o Skype para o painel de controle do servidor de negócios

1. Usando uma conta de usuário atribuída à função CsUserAdministrator ou CsAdministrator, faça logon em qualquer computador de sua implantação interna.
    
2.  Abra o Skype para painel de controle do servidor de negócios.
    
3. Na barra de navegação à esquerda, clique em **Conferência**e em **Configuração da reunião**.
    
4. Na lista de configurações da reunião, clique na configuração que deseja alterar, em **Editar** e, em seguida, clique em **Exibir detalhes**.
    
5. Em **Editar configuração da reunião**, modifique qualquer definição da configuração, exceto o nome da configuração, que não pode ser modificado.
    
6. Clique em **Confirmar**.
    
## <a name="modify-meeting-configuration-settings-by-using-skype-for-business-server-management-shell"></a>Modificar configurações de reunião usando o Skype do Shell de gerenciamento do servidor de negócios

Para modificar as definições de configuração de reunião, use o cmdlet **Set-CsMeetingConfiguration**.
  
O comando mostrado no exemplo a seguir modifica as definições de configuração de reuniões atribuídas ao site de Redmond (-Identity site:Redmond). Neste caso, o valor da propriedade DesignateAsPresenter é definido como Everyone:
  
```
Set-CsMeetingConfiguration -Identity "site:Redmond" -DesignateAsPresenter "Everyone"
```

Para obter mais informações, incluindo uma lista completa de parâmetros, consulte [Set-CsMeetingConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csmeetingconfiguration?view=skype-ps).
  

