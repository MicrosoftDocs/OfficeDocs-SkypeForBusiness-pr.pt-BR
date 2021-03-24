---
title: Exibir configurações de reunião no Skype for Business Server
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
ms.assetid: 932c7e2d-6de3-4176-ac6e-ec230f8230f2
description: 'Resumo: Saiba como exibir as configurações de reunião no Skype for Business Server.'
ms.openlocfilehash: 81f5ef1bc0ce28c7741aa99529e7ba107ff4127f
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51096697"
---
# <a name="view-meeting-configuration-settings-in-skype-for-business-server"></a>Exibir configurações de reunião no Skype for Business Server
 
**Resumo:** Saiba como exibir as configurações de reunião no Skype for Business Server.
  
Você pode exibir as configurações de reunião usando o Painel de Controle do Skype for Business Server ou usando o Shell de Gerenciamento do Skype for Business Server.
  
## <a name="view-meeting-configuration-settings-by-using-skype-for-business-server-control-panel"></a>Exibir configurações de reunião usando o Painel de Controle do Skype for Business Server
<a name="BKMK_ViewJoinSettings"> </a>

1. Por uma conta de usuário atribuída à função CsUserAdministrator role ou CsAdministrator, faça o login em qualquer computador na sua implantação interna.
    
2.  Abra o Painel de Controle do Skype for Business Server.
    
3. Na barra de navegação esquerda, clique **em Conferência** e em **Configuração de Reunião.**
    
4. Na página **Configuração de Reunião**, clique na configuração de reunião que você deseja exibir.
    
5. Em **Editar Filtro de Arquivo,** marque a caixa de seleção Mostrar **Detalhes.**
    
    **Editar Configuração \<policy\> de Reunião -** abre exibindo as configurações da política selecionada.
    
    Para obter detalhes sobre como configurar as configurações, consulte [Create meeting configuration settings in Skype for Business Server](create-settings.md).
    
## <a name="view-meeting-configuration-settings-by-using-skype-for-business-server-management-shell"></a>Exibir configurações de reunião usando o Shell de Gerenciamento do Skype for Business Server
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
