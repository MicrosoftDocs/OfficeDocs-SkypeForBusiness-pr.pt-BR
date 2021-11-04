---
title: Exibir configurações de reunião em Skype for Business Server
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 932c7e2d-6de3-4176-ac6e-ec230f8230f2
description: 'Resumo: Saiba como exibir as configurações de reunião no Skype for Business Server.'
ms.openlocfilehash: db374c3db105b0ffcefe9d846c9c4c17904b14ee
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/04/2021
ms.locfileid: "60766539"
---
# <a name="view-meeting-configuration-settings-in-skype-for-business-server"></a>Exibir configurações de reunião em Skype for Business Server
 
**Resumo:** Saiba como exibir as configurações de reunião em Skype for Business Server.
  
Você pode exibir as definições de configuração de reunião usando Skype for Business Server Painel de Controle ou usando Skype for Business Server Shell de Gerenciamento.
  
## <a name="view-meeting-configuration-settings-by-using-skype-for-business-server-control-panel"></a>Exibir configurações de reunião usando Skype for Business Server Painel de Controle
<a name="BKMK_ViewJoinSettings"> </a>

1. Por uma conta de usuário atribuída à função CsUserAdministrator role ou CsAdministrator, faça o login em qualquer computador na sua implantação interna.
    
2.  Abra Skype for Business Server Painel de Controle.
    
3. Na barra de navegação esquerda, clique **em Conferência** e em **Configuração de Reunião.**
    
4. Na página **Configuração de Reunião**, clique na configuração de reunião que você deseja exibir.
    
5. Em **Editar Filtro de Arquivo,** marque a caixa de seleção Mostrar **Detalhes.**
    
    **Editar Configuração \<policy\> de Reunião -** abre exibindo as configurações da política selecionada.
    
    Para obter detalhes sobre como configurar as configurações, consulte [Create meeting configuration settings in Skype for Business Server](create-settings.md).
    
## <a name="view-meeting-configuration-settings-by-using-skype-for-business-server-management-shell"></a>Exibir configurações de reunião usando Skype for Business Server Shell de Gerenciamento
<a name="BKMK_ViewJoinSettings"> </a>

Para exibir informações sobre todas as configurações de reunião, use o cmdlet **Get-CsMeetingConfiguration:**
  
```
Get-CsMeetingConfiguration
```

Este comando retornará informações semelhantes às seguintes:
  
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

Para obter mais informações, incluindo uma lista completa de parâmetros, consulte [Get-CsMeetingConfiguration](/powershell/module/skype/get-csmeetingconfiguration?view=skype-ps).
