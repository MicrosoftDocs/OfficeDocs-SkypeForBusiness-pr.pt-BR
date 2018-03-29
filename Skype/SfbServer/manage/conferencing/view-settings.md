---
title: Exibir definições de configuração de reuniões no Skype for Business Server 2015
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 932c7e2d-6de3-4176-ac6e-ec230f8230f2
description: 'Resumo: Saiba como exibir configurações de reunião no Skype para Business Server 2015.'
ms.openlocfilehash: 382e50a0f41301953f4313c5019d1eb0d27804e5
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/28/2018
---
# <a name="view-meeting-configuration-settings-in-skype-for-business-server-2015"></a>Exibir definições de configuração de reuniões no Skype for Business Server 2015
 
**Resumo:** Saiba como exibir configurações de reunião no Skype para Business Server 2015.
  
Você pode exibir configurações de reunião usando o Skype para painel de controle do Business Server ou usando Skype do Shell de gerenciamento do servidor de negócios.
  
## <a name="view-meeting-configuration-settings-by-using-skype-for-business-server-control-panel"></a>Exibir configurações de reunião usando o Skype para o painel de controle do servidor de negócios
<a name="BKMK_ViewJoinSettings"> </a>

1. Usando uma conta de usuário atribuída à função CsUserAdministrator ou CsAdministrator, faça logon em qualquer computador de sua implantação interna.
    
2.  Abra o Skype para painel de controle do servidor de negócios.
    
3. Na barra de navegação à esquerda, clique em **Conferência** e em **Configuração da reunião**.
    
4. Na página **Configuração de Reunião**, clique na configuração de reunião que você deseja exibir.
    
5. Em **Editar Filtro de Arquivo**, marque a caixa de seleção **Mostrar Detalhes**.
    
    **Editar configuração de reunião - \<política\> ** abre exibindo as configurações para a política selecionada.
    
    Para obter detalhes sobre como definir as configurações, consulte [criar definições de configuração do Skype para Business Server 2015 da reunião](create-settings.md).
    
## <a name="view-meeting-configuration-settings-by-using-skype-for-business-server-management-shell"></a>Exibir configurações de reunião usando o Skype do Shell de gerenciamento do servidor de negócios
<a name="BKMK_ViewJoinSettings"> </a>

Para visualizar informações sobre todas as definições de configurações de reunião, use o cmdlet **Get-CsMeetingConfiguration**:
  
```
Get-CsMeetingConfiguration
```

Este comando retorna informações semelhantes para o seguinte:
  
```
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

```

Para obter mais informações, incluindo uma lista completa de parâmetros, consulte [Get-CsMeetingConfiguration](https://docs.microsoft.com/powershell/module/skype/get-csmeetingconfiguration?view=skype-ps).
  

