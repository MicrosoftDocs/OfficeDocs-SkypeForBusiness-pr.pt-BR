---
title: Exibir políticas de conferência no Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c1c0976e-2bfb-475b-9255-ed6b093d8798
description: 'Resumo: saiba como exibir as políticas de conferência no Skype for Business Server.'
ms.openlocfilehash: 1f1545761838cf176abd88fa12abd9ef5a1d8136
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34280317"
---
# <a name="view-conferencing-policies-in-skype-for-business-server"></a>Exibir políticas de conferência no Skype for Business Server
 
**Resumo:** Saiba como exibir as políticas de conferência no Skype for Business Server.
  
Você pode exibir as políticas de conferência usando o painel de controle do Skype for Business Server ou usando o Shell de gerenciamento do Skype for Business Server.
  
## <a name="view-conferencing-policies-by-using-skype-for-business-server-control-panel"></a>Exibir políticas de conferência usando o painel de controle do Skype for Business Server

1. Usando uma conta de usuário atribuída à função CsUserAdministrator ou CsAdministrator, faça logon em qualquer computador de sua implantação interna.
    
2.  Abra o painel de controle do Skype for Business Server.
    
3. Na barra de navegação esquerda, clique em **Conferência** e, em seguida, clique em **Política de Conferência**.
    
4. Na página de **Política de Conferência**, dê um clique duplo na política de conferência que você deseja visualizar.
    
5. Em **Editar Filtro de Arquivo**, marque a caixa de seleção **Mostrar Detalhes**.
    
    **Editar política de conferência \<–\> a política** é aberta exibindo as configurações da política selecionada.
    
    Para obter detalhes sobre como definir as configurações, consulte [criar políticas de conferência no Skype for Business Server](create-policies.md).
    
## <a name="view-conferencing-policies-by-using-skype-for-business-server-management-shell"></a>Exibir políticas de conferência usando o Shell de gerenciamento do Skype for Business Server

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

Para obter mais informações, incluindo uma descrição completa da sintaxe e lista de parâmetros, consulte [Get-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/get-csconferencingpolicy?view=skype-ps).
  

