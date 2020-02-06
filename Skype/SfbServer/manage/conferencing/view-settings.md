---
title: Exibir configurações de reunião no Skype for Business Server
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
ms.assetid: 932c7e2d-6de3-4176-ac6e-ec230f8230f2
description: 'Resumo: saiba como exibir as configurações de configuração de uma reunião no Skype for Business Server.'
ms.openlocfilehash: 858d1a3d786cb9fe3c6b33daaca8667cab2390f8
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41818452"
---
# <a name="view-meeting-configuration-settings-in-skype-for-business-server"></a>Exibir configurações de reunião no Skype for Business Server
 
**Resumo:** Saiba como exibir as configurações de configuração de reunião no Skype for Business Server.
  
Você pode exibir as configurações de reunião usando o painel de controle do Skype for Business Server ou usando o Shell de gerenciamento do Skype for Business Server.
  
## <a name="view-meeting-configuration-settings-by-using-skype-for-business-server-control-panel"></a>Exibir configurações de reunião usando o painel de controle do Skype for Business Server
<a name="BKMK_ViewJoinSettings"> </a>

1. Usando uma conta de usuário atribuída à função CsUserAdministrator ou CsAdministrator, faça logon em qualquer computador de sua implantação interna.
    
2.  Abra o painel de controle do Skype for Business Server.
    
3. Na barra de navegação à esquerda, clique em **Conferência** e em **Configuração da reunião**.
    
4. Na página **Configuração de Reunião**, clique na configuração de reunião que você deseja exibir.
    
5. Em **Editar Filtro de Arquivo**, marque a caixa de seleção **Mostrar Detalhes**.
    
    **Editar configuração de reunião \<–\> a política** é aberta exibindo as configurações da política selecionada.
    
    Para obter detalhes sobre como definir as configurações, consulte [criar definições de configuração de reunião no Skype for Business Server](create-settings.md).
    
## <a name="view-meeting-configuration-settings-by-using-skype-for-business-server-management-shell"></a>Exibir configurações de reunião usando o Shell de gerenciamento do Skype for Business Server
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
  

