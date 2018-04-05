---
title: Política de conferência das contas do Sistema de Salas do Skype
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 3/4/2016
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 4dd8be28-5156-411b-8ccd-eff7f75cb897
description: Leia este tópico para aprender como atribuir as políticas de conferência às contas do Sistema de Salas do Skype.
ms.openlocfilehash: 07ce5031bd053837d69d3ed3da27aabb344c3a65
ms.sourcegitcommit: ffca287cf70db2cab14cc1a6cb7cea68317bedd1
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/05/2018
---
# <a name="conferencing-policy-for-skype-room-system-accounts"></a>Política de conferência das contas do Sistema de Salas do Skype
 
Leia este tópico para aprender como atribuir as políticas de conferência às contas do Sistema de Salas do Skype.
  
## <a name="conferencing-policy-features"></a>Recursos da política de conferência

A política de conferência atribuída à conta de sistema do Skype sala deve ter determinadas características. Na maioria das vezes, o cliente do sistema de sala Skype ingressa em uma reunião agendada e, portanto, a política de conferência do organizador da reunião afetará a conferência. No entanto, em Skype para Business Server, determinados recursos dependem configuração do participante. Por exemplo, se a política do participante permite uma resolução de vídeo máxima de 1080p, os participantes observarão esse recurso de vídeo de resolução superior na conferência, mesmo se a política do organizador não permite a ele. A tabela a seguir descreve as várias configurações que você deve estar ciente ao configurar políticas de conferência para contas de sistema do Skype sala em sua organização. 
  
|Recurso  <br/> |Valor  <br/> |Comentário  <br/> |
|:-----|:-----|:-----|
|AllowIPAudio  <br/> |TRUE  <br/> |Devem ser verdadeiras para o áudio do sistema de sala do Skype  <br/> |
|AllowIPVideo  <br/> |TRUE  <br/> |Devem ser verdadeiras para o áudio do sistema de sala Skype trabalhar em sessões de quadro de comunicações (ad hoc) reunir agora no sistema de sala do Skype  <br/> |
|AllowMultiView  <br/> |TRUE  <br/> |Permite que o sistema Skype sala renderizar com multi-view, vários fluxos de vídeo  <br/> |
|AllowParticipantControl  <br/> |TRUE  <br/> |Afeta as sessões de quadro de comunicações (ad hoc) reunir agora no sistema de sala do Skype  <br/> |
|AllowAnnotations  <br/> |TRUE  <br/> |Afeta as sessões de quadro de comunicações (ad hoc) reunir agora no sistema de sala do Skype  <br/> |
|DisablePowerPointAnnotations  <br/> |FALSE  <br/> |Afeta as sessões de quadro de comunicações (ad hoc) reunir agora no sistema de sala do Skype  <br/> |
|AllowUserToScheduleMeetingsWithAppSharing  <br/> |TRUE  <br/> |Afeta as sessões de quadro de comunicações (ad hoc) reunir agora no sistema de sala do Skype  <br/> |
|AllowNonEnterpriseVoiceUsersToDialOut  <br/> |FALSE  <br/> |Depende se a conta é o Enterprise Voice (EV) ativada (consulte as contas de sistema de sala Skype habilitando para Skype para a seção de negócios)  <br/> |
|AllowAnonymousUsersToDialOut  <br/> |FALSE  <br/> |Depende do fato da conta ser ou não Enterprise Voice (EV) habilitada  <br/> |
|AllowAnonymousParticipantsInMeetings  <br/> |TRUE  <br/> |Afeta as sessões de quadro de comunicações (ad hoc) reunir agora no sistema de sala do Skype  <br/> |
|AllowExternalUsersToSaveContent  <br/> |TRUE  <br/> |Afeta as sessões de quadro de comunicações (ad hoc) reunir agora no sistema de sala do Skype  <br/> |
|AllowExternalUserControl  <br/> |FALSE  <br/> |Afeta as sessões de quadro de comunicações (ad hoc) reunir agora no sistema de sala do Skype  <br/> |
|AllowExternalUsersToRecordMeeting  <br/> |FALSE  <br/> |Afeta as sessões de quadro de comunicações (ad hoc) reunir agora no sistema de sala do Skype  <br/> |
|AllowPolls  <br/> |TRUE  <br/> |N/d em reunir agora reuniões (ad hoc), mas o sistema de sala Skype podem responder ao votações na tela à frente da sala  <br/> |
|AllowSharedNotes  <br/> |TRUE  <br/> |N/d em reunir agora reuniões (ad hoc), mas o sistema de sala Skype podem responder ao votações na tela à frente da sala  <br/> |
|EnableDialInConferencing  <br/> |TRUE  <br/> |Afeta as sessões de quadro de comunicações (ad hoc) reunir agora no sistema de sala do Skype  <br/> |
|EnableAppDesktopSharing  <br/> |Área de trabalho  <br/> |Afeta as sessões de quadro de comunicações (ad hoc) reunir agora no sistema de sala do Skype  <br/> |
|AllowConferenceRecording  <br/> |FALSE  <br/> |N/d para o sistema de sala Skype. Se estiver definido como TRUE, uma parte remota pode registrar  <br/> |
|EnableP2PRecording  <br/> |FALSE  <br/> |N/d para o sistema de sala Skype. Se estiver definido como TRUE, uma parte remota pode registrar  <br/> |
|EnableFileTransfer  <br/> |TRUE  <br/> |N/D  <br/> |
|EnableP2PFileTransfer  <br/> |TRUE  <br/> |N/D  <br/> |
|EnableP2PVideo  <br/> |TRUE  <br/> |Permite que o cliente do sistema de sala Skype participar de sessões de vídeo ponto a ponto  <br/> |
|AllowLargeMeetings  <br/> |FALSE  <br/> |N/D  <br/> |
|EnableDataCollaboration  <br/> |TRUE  <br/> |Afeta as sessões de quadro de comunicações (ad hoc) reunir agora no sistema de sala do Skype  <br/> |
|MaxVideoConferenceResolution  <br/> |VGA  <br/> |Ignorado pelo Skype para Business Server, o sistema de sala do Skype usa HD1080  <br/> |
|MaxMeetingSize  <br/> |250  <br/> |Afeta as sessões de quadro de comunicações (ad hoc) reunir agora no sistema de sala do Skype  <br/> |
|AudioBitRateKb  <br/> |200  <br/> |Consulte a observação no final da tabela\*  <br/> |
|VideoBitRateKb  <br/> |5000  <br/> |Este é a taxa máxima de bits de vídeo de saída permitida. Sistema de sala Skype poderá enviar uma 1080 stream junto com pano (se for usado o RoundTable) a essa taxa de bits. \*  <br/> |
|AppSharingBitRateKb  <br/> |5000  <br/> |Consulte a observação no final da tabela\*  <br/> |
|FileTransferBitRateKb  <br/> |5000  <br/> |N/D  <br/> |
|TotalReceiveVideoBitRateKb  <br/> |20000  <br/> |Recomendamos que você defina este item o mais alto possível. A largura de banda efetiva depende de condições de rede no momento de conferências.\*  <br/> |
|EnableMultiViewJoin  <br/> |TRUE  <br/> |Deve ser TRUE para o sistema de sala Skype garantir que os fluxos de vídeo de multi-exibição  <br/> |
   
* Para obter informações sobre o planejamento de largura de banda, consulte [Requisitos de largura de banda de rede para tráfego de mídia](https://technet.microsoft.com/en-us/library/jj688118%28v=ocs.15%29.aspx).
  
> [!NOTE]
> Se o cliente do sistema de sala Skype tentar ingressar em uma reunião agendada organizada por um usuário hospedado em um pool do Lync Server 2010, política de conferência do organizador da reunião pode impedir que o cliente do sistema de sala Skype realizando a colaboração. 
  
## <a name="meeting-authentication"></a>Autenticação da reunião

Sistema de sala Skype solicita que os usuários para autenticação quando utilizarem a reunião link de ingresso para ingressar em uma reunião restrita; Por exemplo, uma reunião para a qual lobby de reunião opções tiverem sido configuradas no Outlook. Essa configuração está sempre ativada para reuniões personalizadas e os usuários são sempre avisados. No entanto, para reuniões sem restrições, os usuários podem ingressar na reunião sem autenticação. 
  
O seguinte comando permite que os administradores exijam autenticação para todas as reuniões, incluindo, reuniões sem restrições: 
  
```
Set-CsMeetingConfiguration -RequireRoomSystemsAuthorization $TRUE
```

Por padrão, RequireRoomSystemsAuthorization é FALSE (FALSO). 
  

