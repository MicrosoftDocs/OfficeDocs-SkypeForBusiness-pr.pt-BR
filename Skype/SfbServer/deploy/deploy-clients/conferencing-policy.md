---
title: Política de conferência para Skype do Sistema de Sala
ms.author: v-mahoffman
author: cichur
manager: serdars
ms.reviewer: sohailta
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 4dd8be28-5156-411b-8ccd-eff7f75cb897
description: Leia este tópico para saber como atribuir políticas de conferência para Skype do Sistema de Sala.
ms.openlocfilehash: 9e6bab608ab68b3f0e0d5075ae1caf8cb16d4c0b
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/04/2021
ms.locfileid: "60771673"
---
# <a name="conferencing-policy-for-skype-room-system-accounts"></a>Política de conferência para Skype do Sistema de Sala
 
Leia este tópico para saber como atribuir políticas de conferência para Skype do Sistema de Sala.
  
## <a name="conferencing-policy-features"></a>Recursos de política de conferência

A política de conferência atribuída à conta Skype Room System deve ter determinadas características. Na maioria das vezes, o cliente Skype Room System ins junta uma reunião agendada e, portanto, a política de conferência do organizador da reunião afetará a conferência. No entanto, Skype for Business Server, determinados recursos dependem da configuração do participante. Por exemplo, se a política do participante permitir uma resolução de vídeo máxima de 1080p, os participantes experimentarão esse recurso de vídeo de resolução mais alta na conferência, mesmo se a política do organizador não permitir. A tabela a seguir descreve várias dessas configurações que você deve estar ciente ao configurar políticas de conferência para Skype contas do Sistema de Sala em sua organização. 
  
|Recurso  <br/> |Valor  <br/> |Comment  <br/> |
|:-----|:-----|:-----|
|AllowIPAudio  <br/> |TRUE  <br/> |Deve ser verdadeiro para Skype áudio do Sistema de Sala  <br/> |
|AllowIPVideo  <br/> |TRUE  <br/> |Deve ser verdadeiro para que Skype áudio do Sistema de Sala funcione em sessões de quadro de Skype de Reunião Agora (ad hoc)  <br/> |
|AllowMultiView  <br/> |TRUE  <br/> |Permite que Skype Room System renderizar vários fluxos de vídeo e vários fluxos de vídeo  <br/> |
|AllowParticipantControl  <br/> |TRUE  <br/> |Afeta as sessões de quadro de Skype Reunião Agora (ad hoc)  <br/> |
|AllowAnnotations  <br/> |TRUE  <br/> |Afeta as sessões de quadro de Skype Reunião Agora (ad hoc)  <br/> |
|DisablePowerPointAnnotations  <br/> |FALSE  <br/> |Afeta as sessões de quadro de Skype Reunião Agora (ad hoc)  <br/> |
|AllowUserToScheduleMeetingsWithAppSharing  <br/> |TRUE  <br/> |Afeta as sessões de quadro de Skype Reunião Agora (ad hoc)  <br/> |
|AllowNonEnterpriseVoiceUsersToDialOut  <br/> |FALSE  <br/> |Depende se a conta está Enterprise Voice (EV) habilitada (consulte a seção Habilitar Skype Contas do Sistema de Sala para Skype for Business)  <br/> |
|AllowAnonymousUsersToDialOut  <br/> |FALSE  <br/> |Depende se a conta está Enterprise Voice (EV) habilitada  <br/> |
|AllowAnonymousParticipantsInMeetings  <br/> |TRUE  <br/> |Afeta as sessões de quadro de Skype Reunião Agora (ad hoc)  <br/> |
|AllowExternalUsersToSaveContent  <br/> |TRUE  <br/> |Afeta as sessões de quadro de Skype Reunião Agora (ad hoc)  <br/> |
|AllowExternalUserControl  <br/> |FALSE  <br/> |Afeta as sessões de quadro de Skype Reunião Agora (ad hoc)  <br/> |
|AllowExternalUsersToRecordMeeting  <br/> |FALSE  <br/> |Afeta as sessões de quadro de Skype Reunião Agora (ad hoc)  <br/> |
|AllowPolls  <br/> |TRUE  <br/> |N/A em Reuniões de Reunião Agora (ad hoc), mas Skype Room System pode responder a votações na tela na frente da sala  <br/> |
|AllowSharedNotes  <br/> |TRUE  <br/> |N/A em Reuniões de Reunião Agora (ad hoc), mas Skype Room System pode responder a votações na tela na frente da sala  <br/> |
|EnableDialInConferencing  <br/> |TRUE  <br/> |Afeta as sessões de quadro de Skype Reunião Agora (ad hoc)  <br/> |
|EnableAppDesktopSharing  <br/> |Desktop  <br/> |Afeta as sessões de quadro de Skype Reunião Agora (ad hoc)  <br/> |
|AllowConferenceRecording  <br/> |FALSE  <br/> |N/A para Skype Room System. Se VERDADEIRO, uma parte remota poderia gravar  <br/> |
|EnableP2PRecording  <br/> |FALSE  <br/> |N/A para Skype Room System. Se VERDADEIRO, uma parte remota poderia gravar  <br/> |
|EnableFileTransfer  <br/> |TRUE  <br/> |N/A  <br/> |
|EnableP2PFileTransfer  <br/> |TRUE  <br/> |N/A  <br/> |
|EnableP2PVideo  <br/> |TRUE  <br/> |Permite que o Skype do sistema de sala participe de sessões de vídeo ponto a ponto  <br/> |
|AllowLargeMeetings  <br/> |FALSE  <br/> |N/A  <br/> |
|EnableDataCollaboration  <br/> |TRUE  <br/> |Afeta as sessões de quadro de Skype Reunião Agora (ad hoc)  <br/> |
|MaxVideoConferenceResolution  <br/> |VGA  <br/> |Ignorado por Skype for Business Server, Skype Room System usa HD1080  <br/> |
|MaxMeetingSize  <br/> |250  <br/> |Afeta as sessões de quadro de Skype Reunião Agora (ad hoc)  <br/> |
|AudioBitRateKb  <br/> |200  <br/> |Consulte observação no final da tabela\*  <br/> |
|VideoBitRateKb  <br/> |5000  <br/> |Essa é a taxa de bits de vídeo de saída máxima permitida. Skype O Sistema de Sala pode enviar um fluxo 1080 juntamente com pano (se RoundTable for usado) nessa taxa de bits. \*  <br/> |
|AppSharingBitRateKb  <br/> |5000  <br/> |Consulte observação no final da tabela\*  <br/> |
|FileTransferBitRateKb  <br/> |5000  <br/> |N/A  <br/> |
|TotalReceiveVideoBitRateKb  <br/> |20000  <br/> |É recomendável definir isso o mais alto possível. A largura de banda efetiva depende das condições de rede no momento das conferências.\*  <br/> |
|EnableMultiViewJoin  <br/> |TRUE  <br/> |Deve ser VERDADEIRO para Skype Room System para garantir fluxos de vídeo com vários visualizadores  <br/> |
   
* Para obter informações sobre planejamento de largura de banda, consulte [Requisitos de largura de banda de rede para tráfego de mídia](../../plan-your-deployment/network-requirements/network-requirements.md#network-bandwidth-requirements-for-media-traffic).
  
> [!NOTE]
> Se o cliente do sistema de sala Skype tentar ingressar em uma reunião agendada organizada por um usuário que está em casa em um pool do Lync Server 2010, a política de conferência do organizador da reunião poderá impedir que o cliente do sistema de sala Skype de executar a colaboração. 
  
## <a name="meeting-authentication"></a>Autenticação de reunião

Skype O Sistema de Sala solicita autenticação aos usuários quando eles usam o link de junção de reunião para ingressar em uma reunião restrita; por exemplo, uma reunião para a qual as opções de lobby de reunião foram configuradas Outlook. Essa configuração está sempre em reuniões personalizadas e os usuários sempre são solicitados. No entanto, para reuniões irrestritas, os usuários podem ingressar na reunião sem autenticação. 
  
O comando a seguir permite que os administradores exigirem autenticação para todas as reuniões, incluindo reuniões irrestritas: 
  
```powershell
Set-CsMeetingConfiguration -RequireRoomSystemsAuthorization $TRUE
```

Por padrão, RequireRoomSystemsAuthorization é FALSE. 
  

