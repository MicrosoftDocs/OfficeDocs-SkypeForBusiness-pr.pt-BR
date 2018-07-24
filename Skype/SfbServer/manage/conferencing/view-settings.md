---
title: Configurações de reunião no Skype para Business Server de modo de exibição
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 932c7e2d-6de3-4176-ac6e-ec230f8230f2
description: 'Resumo: Saiba como exibir configurações de reunião no Skype para Business Server.'
ms.openlocfilehash: 44154b9cdba4743eed9c2a4153545651657d4e72
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/24/2018
ms.locfileid: "20988822"
---
# <a name="view-meeting-configuration-settings-in-skype-for-business-server"></a>Configurações de reunião no Skype para Business Server de modo de exibição
 
**Resumo:** Saiba como exibir configurações de reunião no Skype para Business Server.
  
Você pode exibir configurações de reunião usando o Skype para painel de controle do Business Server ou usando Skype do Shell de gerenciamento do servidor de negócios.
  
## <a name="view-meeting-configuration-settings-by-using-skype-for-business-server-control-panel"></a>Exibir configurações de reunião usando o Skype para o painel de controle do servidor de negócios
<a name="BKMK_ViewJoinSettings"> </a>

1. Usando uma conta de usuário atribuída à função CsUserAdministrator ou CsAdministrator, faça logon em qualquer computador de sua implantação interna.
    
2.  Abra o Skype para painel de controle do servidor de negócios.
    
3. Na barra de navegação à esquerda, clique em **Conferência** e em **Configuração da reunião**.
    
4. Na página **Configuração de Reunião**, clique na configuração de reunião que você deseja exibir.
    
5. Em **Editar Filtro de Arquivo**, marque a caixa de seleção **Mostrar Detalhes**.
    
    **Editar configuração de reunião - \<política\> ** abre exibindo as configurações para a política selecionada.
    
    Para obter detalhes sobre como definir as configurações, consulte [criar definições de configuração do Skype para Business Server da reunião](create-settings.md).
    
## <a name="view-meeting-configuration-settings-by-using-skype-for-business-server-management-shell"></a>Exibir configurações de reunião usando o Skype do Shell de gerenciamento do servidor de negócios
<a name="BKMK_ViewJoinSettings"> </a>

Para visualizar informações sobre todas as definições de configurações de reunião, use o cmdlet **Get-CsMeetingConfiguration**:
  
```
Get-CsMeetingConfiguration
```

Este comando retorna informações semelhantes para o seguinte:
  
<pre>
Identity                        : Global
PstnCallersBypassLobby          : True
EnableAssignedConferenceType    : True
DesignateAsPresenter            : Company
AssignedConferenceTypeByDefault : True
AdmitAnonymousUsersByDefault    : True
RequireRoomSystemsAuthorization : False
LogoURL                         :
LegalURL                        :
HelpURL                         :
CustomFooterText                :
AllowConferenceRecording        : True
</pre>

Para obter mais informações, incluindo uma lista completa de parâmetros, consulte [Get-CsMeetingConfiguration](https://docs.microsoft.com/powershell/module/skype/get-csmeetingconfiguration?view=skype-ps).
  

