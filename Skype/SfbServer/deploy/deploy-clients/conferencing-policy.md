---
title: Política de conferência das contas do Sistema de Salas do Skype
ms.author: v-lanac
author: lanachin
manager: serdars
ms.reviewer: sohailta
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 4dd8be28-5156-411b-8ccd-eff7f75cb897
description: Leia este tópico para aprender como atribuir as políticas de conferência às contas do Sistema de Salas do Skype.
ms.openlocfilehash: 1ffa0065f6df27edb4b5e0bfd39564728ee0a582
ms.sourcegitcommit: dd3a3ab4ddbdcfe772f30fb01ba3b97c45c43dd4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41769094"
---
# <a name="conferencing-policy-for-skype-room-system-accounts"></a>Política de conferência das contas do Sistema de Salas do Skype
 
Leia este tópico para aprender como atribuir as políticas de conferência às contas do Sistema de Salas do Skype.
  
## <a name="conferencing-policy-features"></a>Recursos da política de conferência

A política de conferência atribuída à conta do sistema de sala do Skype deve ter determinadas características. Na maioria das vezes, o cliente do sistema de sala do Skype se une a uma reunião agendada e, portanto, a política de conferência do organizador da reunião afetará a conferência. No entanto, no Skype for Business Server, certos recursos dependem da configuração do participante. Por exemplo, se a política do participante permitir uma resolução máxima de vídeo de 1080p, os participantes terão esse recurso de vídeo de resolução mais alta na conferência, mesmo que a política do organizador não a permita. A tabela a seguir descreve várias configurações das quais você deve estar ciente ao configurar políticas de conferência para contas de sistema de sala do Skype em sua organização. 
  
|Recurso  <br/> |Valor  <br/> |Comentário  <br/> |
|:-----|:-----|:-----|
|AllowIPAudio  <br/> |TRUE  <br/> |Deve ser verdadeiro para o áudio do sistema de sala do Skype  <br/> |
|AllowIPVideo  <br/> |TRUE  <br/> |Deve ser verdade para que o áudio do sistema de sala do Skype funcione em reunir sessões do whiteboard (ad hoc) agora no Skype Room System  <br/> |
|AllowMultiView  <br/> |TRUE  <br/> |Permite que o sistema de salas da Skype processe vários fluxos de vídeo e vários vídeos  <br/> |
|AllowParticipantControl  <br/> |TRUE  <br/> |Afeta as sessões de quadro de comunicações agora (ad hoc) no sistema de salas da Skype  <br/> |
|AllowAnnotations  <br/> |TRUE  <br/> |Afeta as sessões de quadro de comunicações agora (ad hoc) no sistema de salas da Skype  <br/> |
|DisablePowerPointAnnotations  <br/> |FALSE  <br/> |Afeta as sessões de quadro de comunicações agora (ad hoc) no sistema de salas da Skype  <br/> |
|AllowUserToScheduleMeetingsWithAppSharing  <br/> |TRUE  <br/> |Afeta as sessões de quadro de comunicações agora (ad hoc) no sistema de salas da Skype  <br/> |
|AllowNonEnterpriseVoiceUsersToDialOut  <br/> |FALSE  <br/> |Depende se a conta é compatível com o Enterprise Voice (EV) (consulte a seção habilitando contas do sistema de salas do Skype para o Skype for Business)  <br/> |
|AllowAnonymousUsersToDialOut  <br/> |FALSE  <br/> |Depende do fato da conta ser ou não Enterprise Voice (EV) habilitada  <br/> |
|AllowAnonymousParticipantsInMeetings  <br/> |TRUE  <br/> |Afeta as sessões de quadro de comunicações agora (ad hoc) no sistema de salas da Skype  <br/> |
|AllowExternalUsersToSaveContent  <br/> |TRUE  <br/> |Afeta as sessões de quadro de comunicações agora (ad hoc) no sistema de salas da Skype  <br/> |
|AllowExternalUserControl  <br/> |FALSE  <br/> |Afeta as sessões de quadro de comunicações agora (ad hoc) no sistema de salas da Skype  <br/> |
|AllowExternalUsersToRecordMeeting  <br/> |FALSE  <br/> |Afeta as sessões de quadro de comunicações agora (ad hoc) no sistema de salas da Skype  <br/> |
|AllowPolls  <br/> |TRUE  <br/> |N/d em reuniões agora (ad hoc), mas o sistema de salas da Skype pode responder às pesquisas na tela, na frente da sala  <br/> |
|AllowSharedNotes  <br/> |TRUE  <br/> |N/d em reuniões agora (ad hoc), mas o sistema de salas da Skype pode responder às pesquisas na tela, na frente da sala  <br/> |
|EnableDialInConferencing  <br/> |TRUE  <br/> |Afeta as sessões de quadro de comunicações agora (ad hoc) no sistema de salas da Skype  <br/> |
|EnableAppDesktopSharing  <br/> |Área de trabalho  <br/> |Afeta as sessões de quadro de comunicações agora (ad hoc) no sistema de salas da Skype  <br/> |
|AllowConferenceRecording  <br/> |FALSE  <br/> |N/d para sistema de sala da Skype. Se estiver definido como TRUE, uma parte remota pode registrar  <br/> |
|EnableP2PRecording  <br/> |FALSE  <br/> |N/d para sistema de sala da Skype. Se estiver definido como TRUE, uma parte remota pode registrar  <br/> |
|EnableFileTransfer  <br/> |TRUE  <br/> |Não disponível  <br/> |
|EnableP2PFileTransfer  <br/> |TRUE  <br/> |Não disponível  <br/> |
|EnableP2PVideo  <br/> |TRUE  <br/> |Permite que o cliente do sistema de sala da Skype participe de sessões de vídeo ponto a ponto  <br/> |
|AllowLargeMeetings  <br/> |FALSE  <br/> |N/D  <br/> |
|EnableDataCollaboration estiver  <br/> |TRUE  <br/> |Afeta as sessões de quadro de comunicações agora (ad hoc) no sistema de salas da Skype  <br/> |
|MaxVideoConferenceResolution  <br/> |VGA  <br/> |Ignorado pelo Skype for Business Server, o sistema de sala Skype usa o HD1080  <br/> |
|MaxMeetingSize  <br/> |250  <br/> |Afeta as sessões de quadro de comunicações agora (ad hoc) no sistema de salas da Skype  <br/> |
|AudioBitRateKb  <br/> |200  <br/> |Veja a observação no final da tabela\*  <br/> |
|VideoBitRateKb  <br/> |5000  <br/> |Este é a taxa máxima de bits de vídeo de saída permitida. O sistema da sala Skype pode enviar 1 1080 Stream juntamente com o pano (se a margem redonda for usada) a essa taxa de bits. \*  <br/> |
|AppSharingBitRateKb  <br/> |5000  <br/> |Veja a observação no final da tabela\*  <br/> |
|FileTransferBitRateKb  <br/> |5000  <br/> |N/D  <br/> |
|TotalReceiveVideoBitRateKb  <br/> |20000  <br/> |Recomendamos que você defina este item o mais alto possível. A largura de banda efetiva depende das condições da rede no momento da conferência.\*  <br/> |
|EnableMultiViewJoin  <br/> |TRUE  <br/> |Deve ser verdadeiro para que o sistema de sala da Skype garanta fluxos de vídeo de várias exibições  <br/> |
   
* Para obter informações sobre planejamento de largura de banda, consulte [requisitos de largura de banda de rede para tráfego de mídia](../../plan-your-deployment/network-requirements/network-requirements.md#network-bandwidth-requirements-for-media-traffic).
  
> [!NOTE]
> Se o cliente do sistema de sala do Skype tentar ingressar em uma reunião agendada organizada por um usuário que está hospedado em um pool do Lync Server 2010, a política de conferência do organizador da reunião poderá impedir que o cliente do sistema da sala do Skype realize a colaboração. 
  
## <a name="meeting-authentication"></a>Autenticação da reunião

O sistema de sala do Skype solicita aos usuários a autenticação quando eles usam o link de ingresso na reunião para ingressar em uma reunião restrita; por exemplo, uma reunião para a qual as opções de lobby de reunião foram configuradas no Outlook. Essa configuração está sempre ativada para reuniões personalizadas e os usuários são sempre avisados. No entanto, para reuniões sem restrições, os usuários podem ingressar na reunião sem autenticação. 
  
O seguinte comando permite que os administradores exijam autenticação para todas as reuniões, incluindo, reuniões sem restrições: 
  
```powershell
Set-CsMeetingConfiguration -RequireRoomSystemsAuthorization $TRUE
```

Por padrão, RequireRoomSystemsAuthorization é FALSE (FALSO). 
  

