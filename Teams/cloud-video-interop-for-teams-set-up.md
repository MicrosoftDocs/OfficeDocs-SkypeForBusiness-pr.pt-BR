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
localization_priority: Normal
ms.collection:
- M365-voice
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: a1f45967b3e2737f6e2df74c505932ea69afe37f
ms.sourcegitcommit: 43d66693f6f08d4dcade0095bf613240031fec56
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/06/2020
ms.locfileid: "46582628"
---
# <a name="set-up-cloud-video-interop-for-microsoft-teams"></a>Configurar a interoperabilidade de vídeo na nuvem para o Microsoft Teams

Depois de escolher [seu(s) parceiro(s) Cloud Video Interop(s),](cloud-video-interop.md)você precisará planejar sua implantação, configurar com detalhes de provisionamento e chave de locatário do parceiro e consentir com o aplicativo interop de vídeo em sua organização. O diagrama a seguir descreve o processo. 

![Implantando o CVI em sua organização](media/deploying-cvi.png)

## <a name="plan"></a>Plano

Consulte [Cloud Video Interop para Microsoft Teams](cloud-video-interop.md) para obter informações sobre como identificar um parceiro ou parceiros a usar em sua organização. 

Para planejar a habilitação de usuário baseado/simultâneo/em todo o site: 

- Escolha um modelo de implantação/modelo hospedado para seu uso
- Selecione o plano de licença ideal para sua organização. 
- O plano para a capacidade de VMs é que você está hospedando sua infraestrutura de vídeo.

## <a name="configure"></a>Configuração 

Para configurar o Cloud Video Interop, siga estas etapas. 

1. Obtenha informações de configuração dos parceiros que você escolheu (chave do locatário, appIds...). Você pode usar um ou mais parceiros de interop de vídeo em sua organização 

2. Verifique se sua rede está configurada corretamente. Configure seu firewall de vídeo baseado em padrões para a transição de rede de perímetro para suporte. Por exemplo: 
    - Cisco VCS-e                  
    - Polycom RPAD

3. Configure salas integradas com o Exchange e o OTD. Na maioria dos casos, a retransmissão adicional precisaria ser configurada e configurada em seu ambiente.


## <a name="provision"></a>Disposição
 
A chave do locatário será a discagem para o serviço de parceiro. No exemplo a seguir, 813878896@t.plcm.vc é a chave do locatário. 

![Exemplo de chave do locatário](media/tenant-key-example.png) 

Você precisará executar os cmdlets a seguir para provisionar a chave do locatário e também permitir que usuários selecionados ou toda a organização criem reuniões com coordenadas de interop de vídeo.

 
- **[Get-CsTeamsVideoInteropServicepolicy:](https://docs.microsoft.com/powershell/module/skype/get-csteamsvideointeropservicepolicy)** A Microsoft fornece políticas pré-construídas para cada um dos nossos parceiros com suporte que permitem designar quais parceiros usar para interop de vídeo na nuvem.

    Esse cmdlet permite identificar as políticas pré-construídas que você pode usar em sua organização. Você pode atribuir essa política a um ou mais usuários aproveitando o cmdlet Grant-CsTeamsVideoInteropServicePolicy usuário.
 
- **[Grant-CsTeamsVideoInteropServicePolicy:](https://docs.microsoft.com/powershell/module/skype/grant-csteamsvideointeropservicepolicy)** O Grant-CsTeamsVideoInteropServicePolicy cmdlet permite atribuir uma política pré-construída para uso em sua organização ou atribuir a política a usuários específicos.
 
- **[New-CsVideoInteropServiceProvider:](https://docs.microsoft.com/powershell/module/skype/new-csvideointeropserviceprovider)** Use o New-CsVideoInteropServiceProvider para especificar informações sobre um parceiro CVI com suporte que sua organização gostaria de usar.
 
- **[Set-CsVideoInteropServiceProvider:](https://docs.microsoft.com/powershell/module/skype/set-csvideointeropserviceprovider)** Use a Set-CsVideoInteropServiceProvider para atualizar informações sobre um parceiro CVI com suporte que sua organização usa.
 
- **[Get-CsVideoInteropServiceProvider:](https://docs.microsoft.com/powershell/module/skype/get-csvideointeropserviceprovider)** Obter todos os provedores que foram configurados para uso dentro da organização.
 
- **[Remove-CsVideoInteropServiceProvider:](https://docs.microsoft.com/powershell/module/skype/remove-csvideointeropserviceprovider)** Use Remove-CsVideoInteropServiceProvider para remover todas as informações do provedor sobre um provedor que sua organização não usa mais.  
 
## <a name="consent"></a>Consentimento

Você precisará fornecer o consentimento de permissão para que os dispositivos de teleconferência de vídeo (VTCs) in join your organizations meetings via serviço de parceiro. Este link de consentimento também será fornecido por seu parceiro.  
 
Quando essas etapas são concluídas, os usuários habilitados individualmente por meio do cmdlet Grant acima ou todos os usuários da organização, se o locatário estiver habilitado, terão coordenadas VTC em todas as reuniões do Teams agendadas por eles. Qualquer VTC pode ingressar nessas reuniões por meio dessas coordenadas.


|Nome|Descrição resumida da permissão do aplicativo| Descrição|
|--|--|---|
|Calls.JoinGroupCall.All|Ingressar em Chamadas e Reuniões em Grupo como um aplicativo (visualização)|Permite que o aplicativo in join group calls and scheduled meetings in your organization, without a signed-in user.  O aplicativo será ingressar com os privilégios de um usuário de diretório para reuniões em seu locatário.|
|Calls.JoinGroupCallasGuest.All|Ingressar em Chamadas e Reuniões em Grupo como usuário convidado (visualização)|Permite que o aplicativo inscresse chamadas em grupo e reuniões agendadas anonimamente em sua organização, sem um usuário de acesso.  O aplicativo será ingressar como convidado para reuniões em seu locatário.|
|Calls.AccessMedia.All|Acessar fluxos de mídia em uma chamada como um aplicativo (visualização)|Permite que o aplicativo tenha acesso direto a fluxos de mídia em uma chamada, sem um usuário de entrada.|
|OnlineMeetings.Read.All|Ler detalhes da Reunião Online (visualização)|Permite que o aplicativo leia os detalhes da Reunião Online em sua organização, sem um usuário de acesso.|

## <a name="schedule"></a>Agenda

Em seguida, agende uma reunião do Teams com coordenadas de interop vídeo. O usuário habilitado pode agendar reuniões de equipes por meio de:
- [Add-in de Reunião do Teams para Outlook](teams-add-in-for-outlook.md)
- Área de trabalho e dispositivos móveis do cliente Teams


## <a name="join"></a>Ingressar

Você pode ingressar em reuniões do Teams com seus dispositivos VTC das seguintes maneiras:
 
- IVR (Resposta interativa de voz)
    - Você pode discar para a IVR do parceiro usando o tenantkey@domain. 
    - Depois de entrar no IVR do parceiro, você será solicitado a inserir a ID da conferência VTC, que o conectará à reunião do Teams.
- Discagem direta
    - Você pode discar diretamente para a reunião do Teams sem interagir com o IVR do parceiro usando o recurso de discagem direta usando a cadeia completa de chaves de locatário. VTC ConferenceId@domain.
- Discagem com um toque
    - Se você tiver uma sala integrada do Teams, poderá usar os recursos de discagem de um toque oferecidos por seu parceiro (sem precisar digitar qualquer cadeia de caracteres de discagem).

Por fim, interaja com os usuários do Teams em suas reuniões usando áudio, vídeo e compartilhamento de conteúdo. 
