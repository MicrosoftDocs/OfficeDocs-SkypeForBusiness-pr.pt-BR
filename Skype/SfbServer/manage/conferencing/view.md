---
title: Exibir políticas de conferência no Skype for Business Server
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
ms.assetid: c1c0976e-2bfb-475b-9255-ed6b093d8798
description: 'Resumo: Saiba como exibir políticas de conferência no Skype for Business Server.'
ms.openlocfilehash: afe86f0a77e73c3fa7bf96339c4865598a7bc609
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51119400"
---
# <a name="view-conferencing-policies-in-skype-for-business-server"></a>Exibir políticas de conferência no Skype for Business Server
 
**Resumo:** Saiba como exibir políticas de conferência no Skype for Business Server.
  
Você pode exibir políticas de conferência usando o Painel de Controle do Skype for Business Server ou usando o Shell de Gerenciamento do Skype for Business Server.
  
## <a name="view-conferencing-policies-by-using-skype-for-business-server-control-panel"></a>Exibir políticas de conferência usando o Painel de Controle do Skype for Business Server

1. Por uma conta de usuário atribuída à função CsUserAdministrator role ou CsAdministrator, faça o login em qualquer computador na sua implantação interna.
    
2.  Abra o Painel de Controle do Skype for Business Server.
    
3. Na barra de navegação esquerda, clique **em Conferência** e em Política **de Conferência.**
    
4. Na página de **Política de Conferência**, dê um clique duplo na política de conferência que você deseja visualizar.
    
5. Em **Editar Filtro de Arquivo,** marque a caixa de seleção Mostrar **Detalhes.**
    
    **Editar Política de \<policy\> Conferência -** abre exibindo as configurações da política selecionada.
    
    Para obter detalhes sobre como configurar as configurações, consulte [Create conferencing policies in Skype for Business Server](create-policies.md).
    
## <a name="view-conferencing-policies-by-using-skype-for-business-server-management-shell"></a>Exibir políticas de conferência usando o Shell de Gerenciamento do Skype for Business Server

Para exibir políticas de conferência, use o cmdlet **Get-CsConferencingPolicy:**
  
```PowerShell
Get-CsConferencingPolicy
```

O cmdlet retorna informações como:
  
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

Para obter mais informações, incluindo uma descrição de sintaxe completa e uma lista de parâmetros, consulte [Get-CsConferencingPolicy](/powershell/module/skype/get-csconferencingpolicy?view=skype-ps).
