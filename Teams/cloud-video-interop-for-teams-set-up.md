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
description: Este artigo explica como você pode planejar e configurar a Interoperabilidade de Vídeo na Nuvem para usuários em sua organização.
ms.localizationpriority: medium
ms.collection:
- M365-voice
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 1b76e7c5e79b3928c7fb19ad9c5f5fb8f241b29a
ms.sourcegitcommit: 296862e02b548f0212c9c70504e65b467d459cc3
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/25/2022
ms.locfileid: "65674733"
---
# <a name="set-up-cloud-video-interop-for-microsoft-teams"></a>Configurar a interoperabilidade de vídeo na nuvem para o Microsoft Teams

Depois de escolher seus parceiros de Interoperabilidade de Vídeo na Nuvem [, você](cloud-video-interop.md) precisará planejar sua implantação, configurar com detalhes de provisionamento e chave de locatário do parceiro e consentir com o aplicativo de interoperabilidade de vídeo em sua organização. O diagrama a seguir descreve o processo.

![Implantando o CVI em sua organização.](media/deploying-cvi.png)

## <a name="plan"></a>Plano

Consulte [Cloud Video Interop para Microsoft Teams](cloud-video-interop.md) para obter informações sobre como identificar um parceiro ou parceiros a serem usado em sua organização.

Para planejar a habilitação de todo o site/baseado em usuário/simultâneo:

- Escolha um modelo de implantação/modelo hospedado para seu uso
- Selecione o plano de licença ideal para sua organização.
- O plano para a capacidade das VMs é que você está hospedando sua infraestrutura de vídeo.

## <a name="configure"></a>Configuração

Para configurar a Interoperabilidade de Vídeo na Nuvem, siga estas etapas.

1. Obtenha informações de configuração dos parceiros/parceiros escolhidos (chave de locatário, appIds...). Você pode usar um ou mais parceiros de interoperabilidade de vídeo em sua organização

2. Verifique se a rede está configurada corretamente. Configure o firewall de vídeo baseado em padrões para a passagem de rede de perímetro para dar suporte. Por exemplo:
    - Cisco VCS-e
    - Polycom RPAD

3. Configurar salas integradas com o Exchange e o OTD. Na maioria dos casos, a retransmissão adicional precisaria ser configurada e configurada em seu ambiente.

## <a name="provision"></a>Disposição

A chave de locatário será a discagem para o serviço de parceiro. No exemplo a seguir, 813878896@t.plcm.vc é a chave de locatário.

![Exemplo de chave de locatário.](media/tenant-key-example.png)

Você precisará executar os cmdlets a seguir para provisionar a chave de locatário e também permitir que usuários selecionados ou toda a organização criem reuniões com coordenadas de interoperabilidade de vídeo.

- **[Get-CsTeamsVideoInteropServicepolicy](/powershell/module/skype/get-csteamsvideointeropservicepolicy):** A Microsoft fornece políticas predefinidas para cada um de nossos parceiros com suporte que permitem designar quais parceiros usar para interoperabilidade de vídeo na nuvem.

    Esse cmdlet permite identificar as políticas pré-construídas que você pode usar em sua organização. Você pode atribuir essa política a um ou mais de seus usuários aproveitando o cmdlet Grant-CsTeamsVideoInteropServicePolicy aplicativo.

- **[Grant-CsTeamsVideoInteropServicePolicy](/powershell/module/skype/grant-csteamsvideointeropservicepolicy):** O Grant-CsTeamsVideoInteropServicePolicy cmdlet permite que você atribua uma política predefinida para uso em sua organização ou atribua a política a usuários específicos.

- **[New-CsVideoInteropServiceProvider](/powershell/module/skype/new-csvideointeropserviceprovider):** Use o New-CsVideoInteropServiceProvider para especificar informações sobre um parceiro CVI com suporte que sua organização gostaria de usar.

- **[Set-CsVideoInteropServiceProvider](/powershell/module/skype/set-csvideointeropserviceprovider):** Use o Set-CsVideoInteropServiceProvider para atualizar informações sobre um parceiro CVI com suporte que sua organização usa.

- **[Get-CsVideoInteropServiceProvider](/powershell/module/skype/get-csvideointeropserviceprovider):** Obtenha todos os provedores que foram configurados para uso na organização.

- **[Remove-CsVideoInteropServiceProvider](/powershell/module/skype/remove-csvideointeropserviceprovider):** Use Remove-CsVideoInteropServiceProvider para remover todas as informações do provedor sobre um provedor que sua organização não usa mais.

## <a name="consent"></a>Consentimento

Você precisará fornecer consentimento de permissão para os VTCs (dispositivos de teleconferência de vídeo) ingressarem nas reuniões de suas organizações por meio do serviço de parceiro. Esse link de consentimento também será fornecido pelo seu parceiro.

Quando essas etapas forem concluídas, os usuários habilitados individualmente por meio do cmdlet Grant acima ou todos os usuários na organização, se o locatário estiver habilitado, terão coordenadas VTC em todas as reuniões do Teams agendadas. Qualquer VTC pode ingressar nessas reuniões por meio dessas coordenadas.

|Nome|Descrição abreviada da permissão do aplicativo| Descrição|
|---|---|---|
|Calls.JoinGroupCall.All|Ingressar em Chamadas e Reuniões de Grupo como um aplicativo (versão prévia)|Permite que o aplicativo ingresse em chamadas em grupo e reuniões agendadas em sua organização, sem um usuário conectado.  O aplicativo será ingressado com os privilégios de um usuário de diretório para reuniões em seu locatário.|
|Calls.JoinGroupCallasGuest.All|Ingressar em Chamadas de Grupo e Reuniões como um usuário convidado (versão prévia)|Permite que o aplicativo ingresse anonimamente em chamadas em grupo e reuniões agendadas em sua organização, sem um usuário conectado.  O aplicativo será ingressado como convidado para reuniões em seu locatário.|
|Calls.AccessMedia.All|Acessar fluxos de mídia em uma chamada como um aplicativo (versão prévia)|Permite que o aplicativo obtenha acesso direto a fluxos de mídia em uma chamada, sem um usuário conectado.|
|OnlineMeetings.Read.All|Ler detalhes da Reunião Online (versão prévia)|Permite que o aplicativo leia os detalhes da Reunião Online em sua organização, sem um usuário conectado.|

## <a name="schedule"></a>Agenda

Em seguida, agende Teams reunião com coordenadas de interoperabilidade de vídeo. O usuário habilitado pode agendar reuniões de equipes por meio de:

- [Teams de Reunião para Outlook](teams-add-in-for-outlook.md)
- Teams desktop e móvel do cliente

## <a name="join"></a>Ingressar

Você pode ingressar Teams reuniões com seus dispositivos VTC das seguintes maneiras:

- IVR (Resposta de voz interativa)
  - Você pode discar para a IVR do parceiro usando o tenantkey@domain.
  - Quando estiver no IVR do parceiro, você será solicitado a inserir a conferenceId do VTC, que conectará você à Teams reunião.
- Discagem direta
  - Você pode discar diretamente para a reunião Teams sem interagir com a IVR do parceiro usando o recurso de discagem direta usando a cadeia de caracteres completa de tenantkey. VTC ConferenceId@domain.
- Discagem de um toque
  - Se você tiver uma sala Teams, poderá usar os recursos de discagem de um toque oferecidos pelo parceiro (sem a necessidade de digitar nenhuma cadeia de caracteres de discagem).

Por fim, envolva-Teams usuários em suas reuniões usando áudio, vídeo e compartilhamento de conteúdo.
