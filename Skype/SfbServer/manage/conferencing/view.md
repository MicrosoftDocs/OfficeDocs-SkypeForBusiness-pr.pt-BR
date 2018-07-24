---
title: Políticas de conferência do modo de exibição do Skype para Business Server
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c1c0976e-2bfb-475b-9255-ed6b093d8798
description: 'Resumo: Saiba como exibir políticas de conferência no Skype para Business Server.'
ms.openlocfilehash: 161b9f172af935b105e01bda88c1c3dbef2e3a9f
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/24/2018
ms.locfileid: "20992333"
---
# <a name="view-conferencing-policies-in-skype-for-business-server"></a>Políticas de conferência do modo de exibição do Skype para Business Server
 
**Resumo:** Saiba como exibir políticas de conferência no Skype para Business Server.
  
Você pode exibir as políticas de conferência usando Skype para o painel de controle do Business Server ou usando o Skype do Shell de gerenciamento do servidor de negócios.
  
## <a name="view-conferencing-policies-by-using-skype-for-business-server-control-panel"></a>Exibir políticas de conferência usando Skype para o painel de controle do servidor de negócios

1. Usando uma conta de usuário atribuída à função CsUserAdministrator ou CsAdministrator, faça logon em qualquer computador de sua implantação interna.
    
2.  Abra o Skype para painel de controle do servidor de negócios.
    
3. Na barra de navegação esquerda, clique em **Conferência** e, em seguida, clique em **Política de Conferência**.
    
4. Na página de **Política de Conferência**, dê um clique duplo na política de conferência que você deseja visualizar.
    
5. Em **Editar Filtro de Arquivo**, marque a caixa de seleção **Mostrar Detalhes**.
    
    **Editar a política de conferência - \<política\> ** abre exibindo as configurações para a política selecionada.
    
    Para obter detalhes sobre como definir as configurações, consulte [criar políticas de conferência no Skype para Business Server](create-policies.md).
    
## <a name="view-conferencing-policies-by-using-skype-for-business-server-management-shell"></a>Exibir políticas de conferência usando Skype do Shell de gerenciamento do servidor de negócios

Para visualizar as políticas de conferência, use o cmdlet **Get-CsConferencingPolicy**:
  
```
Get-CsConferencingPolicy
```

O cmdlet retorna informações como as seguintes:
  
<pre>
Identity                                  : Global
AllowIPAudio                              : True
AllowIPVideo                              : True
AllowMultiView                            : True
Description                               :
AllowParticipantControl                   : True
AllowAnnotations                          : True
DisablePowerPointAnnotations              : False
AllowUserToScheduleMeetingsWithAppSharing : True
AllowNonEnterpriseVoiceUsersToDialOut     : False
AllowAnonymousUsersToDialOut              : False
AllowAnonymousParticipantsInMeetings      : True
AllowExternalUsersToSaveContent           : True
AllowExternalUserControl                  : False
AllowExternalUsersToRecordMeeting         : False
AllowPolls                                : True
AllowSharedNotes                          : True
EnableDialInConferencing                  : True
EnableAppDesktopSharing                   : Desktop
AllowConferenceRecording                  : False
EnableP2PRecording                        : False
EnableFileTransfer                        : True
EnableP2PFileTransfer                     : True
EnableP2PVideo                            : True
AllowLargeMeetings                        : False
EnableDataCollaboration                   : True
MaxVideoConferenceResolution              : VGA
MaxMeetingSize                            : 250
AudioBitRateKb                            : 200
VideoBitRateKb                            : 50000
AppSharingBitRateKb                       : 50000
FileTransferBitRateKb                     : 50000
TotalReceiveVideoBitRateKb                : 6000
EnableMultiViewJoin                       : True
</pre>

Para obter mais informações, incluindo uma descrição de sintaxe completa e a lista de parâmetros, consulte [Get-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/get-csconferencingpolicy?view=skype-ps).
  

