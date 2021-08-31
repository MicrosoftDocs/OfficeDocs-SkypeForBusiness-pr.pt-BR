---
title: Configurar a interoperabilidade de vídeo na nuvem para o Microsoft Teams
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
search.appverid: MET150
ms.reviewer: srividhc
f1.keywords:
- NOCSH
description: Este artigo explica como você pode planejar e configurar o Cloud Video Interop para usuários em sua organização.
ms.localizationpriority: medium
ms.collection:
- M365-voice
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 0fe0ac66b8d1ff9afe43d4d57783e803f426c23c
ms.sourcegitcommit: 15e90083c47eb5bcb03ca80c2e83feffe67646f2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/30/2021
ms.locfileid: "58732950"
---
# <a name="set-up-cloud-video-interop-for-microsoft-teams"></a>Configurar a interoperabilidade de vídeo na nuvem para o Microsoft Teams

Depois de escolher seus parceiros de [Interop](cloud-video-interop.md)de Vídeo na Nuvem, você precisará planejar sua implantação, configurar-se com detalhes de provisionamento e chave de locatário do parceiro e consentir com o aplicativo de interop de vídeo em sua organização. O diagrama a seguir descreve o processo. 

![Implantando o CVI em sua organização.](media/deploying-cvi.png)

## <a name="plan"></a>Plano

Consulte [Cloud Video Interop for Microsoft Teams](cloud-video-interop.md) para obter informações sobre como identificar um parceiro ou parceiros a ser usado em sua organização. 

Para planejar a habilitação de todo o site/baseada no usuário/simultânea: 

- Escolha um modelo de implantação/modelo hospedado para seu uso
- Selecione o plano de licença ideal para sua organização. 
- O plano para a capacidade das VMs é que você está hospedando sua infraestrutura de vídeo.

## <a name="configure"></a>Configuração 

Para configurar o Cloud Video Interop, siga estas etapas. 

1. Obtenha informações de configuração dos parceiros/parceiros escolhidos (chave de locatário, appIds...). Você pode usar um ou mais parceiros de interop de vídeo em sua organização 

2. Verifique se a rede está configurada corretamente. Configure seu firewall de vídeo baseado em padrões para a transição de rede de perímetro para dar suporte. Por exemplo: 
    - Cisco VCS-e                  
    - Polycom RPAD

3. Configure salas integradas com o Exchange e o OTD. Na maioria dos casos, retransmissão adicional precisaria ser configurada e configurada em seu ambiente.


## <a name="provision"></a>Provisionamento
 
A chave de locatário será a discagem para o serviço parceiro. No exemplo a seguir, 813878896@t.plcm.vc é a chave do locatário. 

![Exemplo de chave de locatário.](media/tenant-key-example.png) 

Você precisará executar os cmdlets a seguir para provisionar a chave de locatário e também habilitar usuários selecionados ou toda a sua organização para criar reuniões com coordenadas de interop de vídeo.

 
- **[Get-CsTeamsVideoInteropServicepolicy](/powershell/module/skype/get-csteamsvideointeropservicepolicy):** A Microsoft fornece políticas pré-construídas para cada um dos nossos parceiros com suporte que permitem que você designe quais parceiros usar para a interop de vídeo na nuvem.

    Este cmdlet permite identificar as políticas pré-construídas que você pode usar em sua organização. Você pode atribuir essa política a um ou mais usuários aproveitando o Grant-CsTeamsVideoInteropServicePolicy cmdlet.
 
- **[Grant-CsTeamsVideoInteropServicePolicy](/powershell/module/skype/grant-csteamsvideointeropservicepolicy):** O Grant-CsTeamsVideoInteropServicePolicy cmdlet permite atribuir uma política pré-construída para uso em sua organização ou atribuir a política a usuários específicos.
 
- **[New-CsVideoInteropServiceProvider](/powershell/module/skype/new-csvideointeropserviceprovider):** Use o New-CsVideoInteropServiceProvider para especificar informações sobre um parceiro CVI com suporte que sua organização gostaria de usar.
 
- **[Set-CsVideoInteropServiceProvider](/powershell/module/skype/set-csvideointeropserviceprovider):** Use o Set-CsVideoInteropServiceProvider para atualizar informações sobre um parceiro CVI com suporte que sua organização usa.
 
- **[Get-CsVideoInteropServiceProvider](/powershell/module/skype/get-csvideointeropserviceprovider):** Obter todos os provedores que foram configurados para uso na organização.
 
- **[Remove-CsVideoInteropServiceProvider](/powershell/module/skype/remove-csvideointeropserviceprovider):** Use Remove-CsVideoInteropServiceProvider para remover todas as informações do provedor sobre um provedor que sua organização não usa mais.  
 
## <a name="consent"></a>Consentimento

Você precisará fornecer consentimento de permissão para que os dispositivos de teleconferência de vídeo (VTCs) participem de suas reuniões de organizações por meio do serviço de parceiro. Esse link de consentimento também será fornecido pelo seu parceiro.  
 
Quando essas etapas são concluídas, os usuários que estão individualmente habilitados por meio do cmdlet Grant acima ou todos os usuários na organização, se o locatário estiver habilitado, terão coordenadas VTC em todas as reuniões de Teams agendadas. Qualquer VTC pode participar dessas reuniões por meio dessas coordenadas.


|Nome|Descrição curta da permissão do aplicativo| Descrição|
|--|--|---|
|Calls.JoinGroupCall.All|Participar de Chamadas e Reuniões de Grupo como um aplicativo (visualização)|Permite que o aplicativo participe de chamadas de grupo e reuniões agendadas em sua organização, sem um usuário com assinatura.  O aplicativo será unido aos privilégios de um usuário de diretório para reuniões em seu locatário.|
|Calls.JoinGroupCallasGuest.All|Participar de Chamadas e Reuniões de Grupo como usuário convidado (visualização)|Permite ao aplicativo ingressar anonimamente em chamadas de grupo e reuniões agendadas em sua organização, sem um usuário in-locar.  O aplicativo será ingressar como convidado para reuniões em seu locatário.|
|Calls.AccessMedia.All|Acessar fluxos de mídia em uma chamada como um aplicativo (visualização)|Permite que o aplicativo tenha acesso direto a fluxos de mídia em uma chamada, sem um usuário interno.|
|OnlineMeetings.Read.All|Ler detalhes da reunião online (visualização)|Permite que o aplicativo leia os detalhes da Reunião Online em sua organização, sem um usuário com acesso.|

## <a name="schedule"></a>Agendar

Em seguida, agende Teams reunião com coordenadas de interop de vídeo. O usuário habilitado pode agendar reuniões de equipes por meio de:
- [Teams Complemento de reunião para Outlook](teams-add-in-for-outlook.md)
- Teams desktop cliente e celular


## <a name="join"></a>Ingressar

Você pode participar Teams reuniões com seus dispositivos VTC das seguintes maneiras:
 
- IVR (Resposta interativa de voz)
    - Você pode discar para a IVR do parceiro usando o tenantkey@domain. 
    - Depois de estar no IVR do parceiro, você será solicitado a inserir a VTC conferenceId, que o conectará à reunião Teams.
- Discagem direta
    - Você pode discar diretamente para a reunião Teams sem interagir com a IVR do parceiro usando o recurso de discagem direta usando a cadeia de caracteres completa de tenantkey. VTC ConferenceId@domain.
- Discagem por toque único
    - Se você tiver uma sala de Teams integrada, poderá usar os recursos de discagem de um toque oferecidos pelo parceiro (sem precisar digitar qualquer cadeia de caracteres de discagem).

Por fim, envolva-se com Teams usuários em suas reuniões usando áudio, vídeo e compartilhamento de conteúdo.