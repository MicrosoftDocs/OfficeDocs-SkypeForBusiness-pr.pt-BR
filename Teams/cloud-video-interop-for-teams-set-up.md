---
title: Configurar a interoperabilidade de vídeo na nuvem para o Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.topic: article
ms.service: msteams
search.appverid: MET150
ms.reviewer: srividhc
description: Este artigo explica como planejar e configurar o interoperabilidade de vídeo de nuvem para usuários em sua organização.
localization_priority: Normal
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: b171b3fb5e73561ea5aea54e6e4f25bfabe6b0dc
ms.sourcegitcommit: 920a7dbdc2a0ede94d0a4bd573c01a1ccd838b7e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "31993617"
---
# <a name="set-up-cloud-video-interop-for-microsoft-teams"></a>Configurar a interoperabilidade de vídeo na nuvem para o Microsoft Teams

Depois que você tiver [escolhido em seus parceiros de interoperabilidade de vídeo de nuvem](cloud-video-interop.md), você precisará planejar sua implantação, get configurar com detalhes de provisionamento e chave do locatário de parceiro e consentimento para o aplicativo de interoperabilidade de vídeo em sua organização. O diagrama a seguir destaca o processo. 

![Implantando CVI na sua organização](media/deploying-cvi.png)

## <a name="plan"></a>Plano

Consulte a [Interoperabilidade de vídeo de nuvem para equipes da Microsoft](cloud-video-interop.md) para obter informações sobre como identificar um parceiro ou parceiros para uso na sua organização. 

Planejar a habilitação de ampla de site com base no/simultâneos/usuário: 

- Selecionar um modelo de modelo/hospedados de implantação para uso
- Selecione o plano de licença ideal para sua organização. 
- Planejamento de capacidade de VMs é que você está hospedando sua infra-estrutura de vídeo.

## <a name="configure"></a>Configuração 

Para configurar a interoperabilidade de vídeo de nuvem, siga estas etapas. 

1. Obter informações de configuração dos parceiro/parceiros que você tiver escolhido (chave de locatário, appIds …). Você pode usar um ou mais parceiros interoperabilidade vídeos em sua organização 

2. Certifique-se de que sua rede está configurada corretamente. Configure o firewall de vídeo baseada em padrões para passagem da rede de perímetro dar suporte. Por exemplo: 
    - Cisco VCS-f                  
    - Polycom RPAD

3. Configure salas integradas com o exchange e OTD. Na maioria dos casos, retransmissão adicional precisa ser instalado e configurado em seu ambiente.


## <a name="provision"></a>Provisão
 
A chave do locatário será a discagem externa para o serviço de parceiro. No exemplo a seguir, 813878896@t.plcm.vc é a chave do locatário. 

![Exemplo de chave do locatário](media/tenant-key-example.png) 

Você precisará executar os cmdlets a seguir para provisionar a chave do locatário e também permitem selecionar usuários ou em toda sua organização criar reuniões com coordenadas de interoperabilidade de vídeos.

 
- ** [Get-CsTeamsVideoInteropServicepolicy](https://docs.microsoft.com/powershell/module/skype/get-csteamsvideointeropservicepolicy):** A Microsoft fornece diretivas previamente construídas para cada um de nossos parceiros com suporte que permitem que você determine qual parceiros a ser usado para a interoperabilidade de vídeo de nuvem.

    Este cmdlet permite que você identifique as políticas de pré-construídas que você pode usar em sua organização. Você pode atribuir essa política a um ou mais dos seus usuários utilizando o cmdlet Grant-CsTeamsVideoInteropServicePolicy.
 
- ** [Grant-CsTeamsVideoInteropServicePolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsvideointeropservicepolicy):** O cmdlet Grant-CsTeamsVideoInteropServicePolicy permite atribuir uma política previamente construída para uso em sua organização ou atribuir a política a usuários específicos.
 
- ** [Novo-CsVideoInteropServiceProvider](https://docs.microsoft.com/powershell/module/skype/new-csvideointeropserviceprovider):** Use o New-CsVideoInteropServiceProvider para especificar informações sobre um parceiro CVI com suporte que sua organização gostaria de usar.
 
- ** [Set-CsVideoInteropServiceProvider](https://docs.microsoft.com/powershell/module/skype/set-csvideointeropserviceprovider):** Use o Set-CsVideoInteropServiceProvider para atualizar as informações sobre um parceiro CVI com suporte, que sua organização usa.
 
- ** [Get-CsVideoInteropServiceProvider](https://docs.microsoft.com/powershell/module/skype/get-csvideointeropserviceprovider):** Obtenha todos os provedores que tiverem sido configurados para uso dentro da organização.
 
- ** [Remove-CsVideoInteropServiceProvider](https://docs.microsoft.com/powershell/module/skype/remove-csvideointeropserviceprovider):** Use Remove-CsVideoInteropServiceProvider para remover todas as informações do provedor sobre um provedor de sua organização não os utiliza mais.  
 
## <a name="consent"></a>Consentimento

Você precisará fornecer o consentimento de permissão para os dispositivos de videoconferência (VTCs) para participar de reuniões suas organizações por meio do serviço de parceiro. Este link consentimento também será fornecido pelo seu parceiro.  
 
Quando essas etapas forem concluídas, os usuários que são habilitados individualmente por meio do cmdlet Grant acima, ou todos os usuários na organização, se o inquilino estiver habilitado, terá VTC coordenadas em todas as reuniões de equipes que eles agendarem. Qualquer VTC pode ingressar nessas reuniões via naquelas coordenadas.


|Nome|Descrição curta de permissão de aplicativo| Descrição|
|--|--|---|
|Calls.JoinGroupCall.All|Ingressar em reuniões e chamadas de grupo como um aplicativo (preview)|Permite que o aplicativo ingressar em chamadas de grupo e reuniões agendadas em sua organização, sem que um usuário conectado.  O aplicativo ingressarão com os privilégios de um usuário do diretório em reuniões no seu locatário.|
|Calls.JoinGroupCallasGuest.All|Ingressar em reuniões e chamadas de grupo como um usuário convidado (preview)|Permite que o aplicativo ingressar em chamadas de grupo e reuniões agendadas anonimamente em sua organização, sem que um usuário conectado.  O aplicativo ingressarão como convidado em reuniões no seu locatário.|
|Calls.AccessMedia.All|Fluxos de mídia de acesso em uma chamada como um aplicativo (preview)|Permite que o aplicativo obter acesso direto aos fluxos de mídia em uma chamada, sem que um usuário conectado.|
|OnlineMeetings.Read.All|Detalhes da Reunião Online de leitura (preview)|Permite que o aplicativo ler os detalhes da Reunião Online em sua organização, sem que um usuário conectado.|

## <a name="schedule"></a>Agenda

Em seguida, agende reunião de equipes com coordenadas de interoperabilidade de vídeos. O usuário habilitado pode agendar reuniões de equipes via:
- [Suplemento para Outlook reunião de equipes](teams-add-in-for-outlook.md)
- Cliente de equipes desktop e portáteis


## <a name="join"></a>Ingressar

Você pode ingressar em reuniões de equipes com seus dispositivos VTC das seguintes maneiras:
 
- IVR (resposta de voz interativa)
    - Você pode discar para IVR do parceiro usando o tenantkey@domain. 
    - Quando você estiver no parceiro de IVR, você será solicitado para inserir o conferenceId VTC, que, em seguida, o conectará à reunião equipes.
- Discagem direta
    - Diretamente, você poderá discar para a reunião de equipes sem interação com IVR do parceiro usando o recurso de discagem direta interna usando a cadeia completa de tenantkey. VTC ConferenceId@domain.
- Discagem de um toque
    - Se você tiver uma sala de equipes integrada, você pode usar os recursos de discagem de um toque oferecidos pelo seu parceiro (sem precisar digitar qualquer cadeia de caracteres de discagem).

Finalmente, se comprometer com usuários de equipes em suas reuniões usando o compartilhamento de áudio, vídeo e conteúdo. 