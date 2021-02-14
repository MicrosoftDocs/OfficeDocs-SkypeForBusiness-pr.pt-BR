---
title: Política de conferência para contas do Sistema de Sala do Skype
ms.author: v-cichur
author: cichur
manager: serdars
ms.reviewer: sohailta
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 4dd8be28-5156-411b-8ccd-eff7f75cb897
description: Leia este tópico para saber como atribuir políticas de conferência para contas do Sistema de Sala do Skype.
ms.openlocfilehash: 3fb462168bd4121f5feef365f881ed9f02620e25
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49812721"
---
# <a name="conferencing-policy-for-skype-room-system-accounts"></a>Política de conferência para contas do Sistema de Sala do Skype
 
Leia este tópico para saber como atribuir políticas de conferência para contas do Sistema de Sala do Skype.
  
## <a name="conferencing-policy-features"></a>Recursos de política de conferência

A política de conferência atribuída à conta do Sistema de Sala do Skype deve ter determinadas características. Na maioria das vezes, o cliente do Sistema de Sala do Skype participa de uma reunião agendada e, portanto, a política de conferência do organizador da reunião afetará a conferência. No entanto, no Skype for Business Server, determinados recursos dependem da configuração do participante. Por exemplo, se a política do participante permitir uma resolução máxima de vídeo de 1080p, os participantes experimentarão essa capacidade de vídeo de resolução mais alta na conferência, mesmo se a política do organizador não permitir. A tabela a seguir descreve várias configurações que você deve estar ciente ao configurar políticas de conferência para contas do Sistema de Sala do Skype em sua organização. 
  
|Recurso  <br/> |Valor  <br/> |Comentário  <br/> |
|:-----|:-----|:-----|
|AllowIPAudio  <br/> |TRUE  <br/> |Deve ser verdadeiro para o áudio do Sistema de Sala do Skype  <br/> |
|AllowIPVideo  <br/> |TRUE  <br/> |Deve ser verdadeiro para que o áudio do Sistema de Sala do Skype funcione em sessões do quadro de branco Reunir Agora (ad hoc) no Sistema de Sala do Skype  <br/> |
|AllowMultiView  <br/> |TRUE  <br/> |Permite que o Sistema de Sala do Skype renderizar vários fluxos de vídeo com várias exibições  <br/> |
|AllowParticipantControl  <br/> |TRUE  <br/> |Afeta as sessões do quadro de trabalho Reunir Agora (ad hoc) no Sistema de Sala do Skype  <br/> |
|AllowAnnotations  <br/> |TRUE  <br/> |Afeta as sessões do quadro de trabalho Reunir Agora (ad hoc) no Sistema de Sala do Skype  <br/> |
|DisablePowerPointAnnotations  <br/> |FALSE  <br/> |Afeta as sessões do quadro de trabalho Reunir Agora (ad hoc) no Sistema de Sala do Skype  <br/> |
|AllowUserToScheduleMeetingsWithAppSharing  <br/> |TRUE  <br/> |Afeta as sessões do quadro de trabalho Reunir Agora (ad hoc) no Sistema de Sala do Skype  <br/> |
|AllowNonEnterpriseVoiceUsersToDialOut  <br/> |FALSE  <br/> |Depende se a conta está habilitada para Enterprise Voice (EV) (consulte a seção Habilitando contas do Sistema de Sala do Skype para o Skype for Business)  <br/> |
|AllowAnonymousUsersToDialOut  <br/> |FALSE  <br/> |Depende de a conta ser ou não Enterprise Voice (EV) habilitada  <br/> |
|AllowAnonymousParticipantsInMeetings  <br/> |TRUE  <br/> |Afeta as sessões do quadro de trabalho Reunir Agora (ad hoc) no Sistema de Sala do Skype  <br/> |
|AllowExternalUsersToSaveContent  <br/> |TRUE  <br/> |Afeta as sessões do quadro de trabalho Reunir Agora (ad hoc) no Sistema de Sala do Skype  <br/> |
|AllowExternalUserControl  <br/> |FALSE  <br/> |Afeta as sessões do quadro de trabalho Reunir Agora (ad hoc) no Sistema de Sala do Skype  <br/> |
|AllowExternalUsersToRecordMeeting  <br/> |FALSE  <br/> |Afeta as sessões do quadro de trabalho Reunir Agora (ad hoc) no Sistema de Sala do Skype  <br/> |
|AllowPolls  <br/> |TRUE  <br/> |N/S em reuniões reunir agora (ad hoc), mas o Sistema de Sala skype pode responder a votações na tela na frente da sala  <br/> |
|AllowSharedNotes  <br/> |TRUE  <br/> |N/S em reuniões reunir agora (ad hoc), mas o Sistema de Sala skype pode responder a votações na tela na frente da sala  <br/> |
|EnableDialInConferencing  <br/> |TRUE  <br/> |Afeta as sessões do quadro de trabalho Reunir Agora (ad hoc) no Sistema de Sala do Skype  <br/> |
|EnableAppDesktopSharing  <br/> |Desktop  <br/> |Afeta as sessões do quadro de trabalho Reunir Agora (ad hoc) no Sistema de Sala do Skype  <br/> |
|AllowConferenceRecording  <br/> |FALSE  <br/> |N/A para o Sistema de Sala do Skype. Se for VERDADEIRO, uma parte remota poderá gravar  <br/> |
|EnableP2PRecording  <br/> |FALSE  <br/> |N/A para o Sistema de Sala do Skype. Se for VERDADEIRO, uma parte remota poderá gravar  <br/> |
|EnableFileTransfer  <br/> |TRUE  <br/> |N/D  <br/> |
|EnableP2PFileTransfer  <br/> |TRUE  <br/> |N/D  <br/> |
|EnableP2PVideo  <br/> |TRUE  <br/> |Permite que o cliente do Sistema de Sala do Skype participe de sessões de vídeo ponto a ponto  <br/> |
|AllowLargeMeetings  <br/> |FALSE  <br/> |N/D  <br/> |
|EnableDataCollaboration  <br/> |TRUE  <br/> |Afeta as sessões do quadro de trabalho Reunir Agora (ad hoc) no Sistema de Sala do Skype  <br/> |
|MaxVideoConferenceResolution  <br/> |VGA  <br/> |Ignorado pelo Skype for Business Server, o Sistema de Sala do Skype usa HD1080  <br/> |
|MaxMeetingSize  <br/> |250  <br/> |Afeta as sessões do quadro de trabalho Reunir Agora (ad hoc) no Sistema de Sala do Skype  <br/> |
|AudioBitRateKb  <br/> |200  <br/> |Consulte a observação no final da tabela\*  <br/> |
|VideoBitRateKb  <br/> |5000  <br/> |Essa é a taxa máxima de bits de vídeo de saída permitida. O Sistema de Sala do Skype pode enviar um fluxo de 1080 junto com pano (se RoundTable for usado) nessa taxa de bits. \*  <br/> |
|AppSharingBitRateKb  <br/> |5000  <br/> |Consulte a observação no final da tabela\*  <br/> |
|FileTransferBitRateKb  <br/> |5000  <br/> |N/D  <br/> |
|TotalReceiveVideoBitRateKb  <br/> |20000  <br/> |Recomendamos que você de definir isso o mais alto possível. A largura de banda efetiva depende das condições de rede no momento das conferências.\*  <br/> |
|EnableMultiViewJoin  <br/> |TRUE  <br/> |Deve ser VERDADEIRO para o Sistema de Sala do Skype garantir fluxos de vídeo multivisão  <br/> |
   
* Para obter informações sobre planejamento de largura de banda, consulte [Requisitos de largura de banda de rede para tráfego de mídia.](../../plan-your-deployment/network-requirements/network-requirements.md#network-bandwidth-requirements-for-media-traffic)
  
> [!NOTE]
> Se o cliente do Sistema de Sala do Skype tentar ingressar em uma reunião agendada organizada por um usuário que está em um pool do Lync Server 2010, a política de conferência do organizador da reunião poderá impedir que o cliente do Sistema de Sala do Skype esgonecê-lo. 
  
## <a name="meeting-authentication"></a>Autenticação de reunião

O Sistema de Sala do Skype solicita autenticação aos usuários quando eles usam o link de ingressar na reunião para ingressar em uma reunião restrita; por exemplo, uma reunião para a qual as opções de lobby de reunião foram configuradas no Outlook. Essa configuração está sempre em reuniões personalizadas e os usuários são sempre solicitados. No entanto, para reuniões irrestritas, os usuários podem ingressar na reunião sem autenticação. 
  
O comando a seguir permite aos administradores exigir autenticação para todas as reuniões, incluindo reuniões irrestritas: 
  
```powershell
Set-CsMeetingConfiguration -RequireRoomSystemsAuthorization $TRUE
```

Por padrão, RequireRoomSystemsAuthorization é FALSE. 
  

