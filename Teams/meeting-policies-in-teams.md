---
title: Gerenciar políticas de reunião
author: tonysmit
ms.author: tonysmit
manager: serdars
ms.date: 05/14/2019
ms.topic: article
ms.service: msteams
ms.reviewer: sonua
localization_priority: Normal
search.appverid: MET150
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
f1keywords:
- ms.teamsadmincenter.meetingpolicies.overview
- ms.teamsadmincenter.meetingpolicies.audioandvideo
- ms.teamsadmincenter.meetingpolicies.contentsharing
- ms.teamsadmincenter.meetingpolicies.general
- ms.teamsadmincenter.meetingpolicies.participantandguests
description: Saiba como gerenciar as configurações de política de reunião no Teams.
ms.openlocfilehash: bdad8f852855c8f87eb62851ddc3082026bcc0ed
ms.sourcegitcommit: f5b6270e64752298687a1abff49da58acde8e107
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/12/2019
ms.locfileid: "34912868"
---
# <a name="manage-meeting-policies-in-teams"></a>Gerenciar políticas de reunião no Teams

::: zone target="docs"
As políticas de reunião são usadas para controlar os recursos que estão disponíveis para os participantes da reunião em reuniões agendadas pelos usuários da sua organização. Depois de criar uma política e fazer suas alterações, você pode atribuir usuários à política. Você gerencia políticas de reunião no centro de administração do Microsoft Teams ou [usando o PowerShell](teams-powershell-overview.md).

Você pode implementar políticas das seguintes maneiras, que afetam a experiência de reunião para os usuários antes de iniciar uma reunião, durante uma reunião ou após uma reunião. 

|Tipo de implementação  |Descrição  |
|---------|---------|
|Por organizador    |Quando você implementa uma política por organizador, todos os participantes da reunião herdam a política do organizador. Por exemplo, **admitir pessoas automaticamente** é uma política por organizador e controla se os usuários ingressam na reunião diretamente ou esperam no lobby para reuniões agendadas pelo usuário ao qual a política é atribuída.          |
|Por usuário    |Quando você implementa uma política por usuário, somente a política por usuário se aplica para restringir determinados recursos para o organizador e/ou participantes da reunião. Por exemplo, **permitir reunião agora** é uma política por usuário.     |
|Por organização e por usuário     |Quando você implementa uma combinação de uma política por organização e por usuário, certos recursos são restritos para participantes da reunião com base em sua política e na política do organizador. Por exemplo, **permitir gravação na nuvem** é uma política por organização e por usuário. Ative essa configuração para permitir que o organizador da reunião e os participantes iniciem e parem de gravar. 

Por padrão, uma política chamada global (padrão para toda a organização) é criada. Por padrão, todos os usuários de sua organização serão atribuídos a essa política de reunião. Você pode fazer alterações nessa política ou criar uma ou mais políticas personalizadas e atribuir usuários a elas. Quando você cria uma política personalizada, pode permitir ou impedir que determinados recursos sejam disponibilizados para seus usuários e, em seguida, atribuí-los a um ou mais usuários que terão as configurações aplicadas a eles. 

## <a name="change-or-create-a-meeting-policy"></a>Alterar ou criar uma política de reunião

Para alterar ou criar uma política de reunião, vá para o centro de administração do Microsoft Teams >**políticas de reunião**de **reuniões** > . Selecione uma política na lista ou selecione **nova política**. Se você estiver criando uma nova política, adicione um nome e uma descrição. O nome não pode conter caracteres especiais ou ter mais de 64 caracteres. Escolha as configurações e, em seguida, selecione **salvar**.

Por exemplo, digamos que você tenha um grupo de usuários e deseja limitar a quantidade de largura de banda que a reunião exigiria. Crie uma nova política personalizada chamada "largura de banda limitada" e desabilite as seguintes configurações:

Em **áudio & vídeo**:
- Desativar a gravação na nuvem
- Desativar permitir vídeo de IP

Em **compartilhamento de conteúdo**:
- Desabilitar o modo de compartilhamento de tela
- Desabilitar o quadro de comunicações
- Desativar anotações compartilhadas

Em seguida, atribua a política aos usuários.

> [!NOTE] 
> Somente uma política de reunião pode ser atribuída a um usuário de cada vez. 

## <a name="assign-a-meeting-policy-to-users"></a>Atribuir uma política de reunião aos usuários

Se você estiver aplicando a política a um usuário, selecione **usuários** no painel de navegação à esquerda e clique no nome de exibição do usuário. Na página do usuário, ao lado de **políticas atribuídas**, selecione **Editar**. Em seguida, no painel **Editar políticas de usuário** , em **política de reunião**, selecione a política de reunião na lista suspensa e, em seguida, selecione **salvar**. Você também pode atribuir políticas da lista de usuários. Para fazer isso, selecione o usuário clicando à esquerda do nome para exibição do usuário. Selecione **Editar configurações**. Em seguida, no painel **Editar configurações** , em **política de reunião**, selecione a política na lista suspensa e, em seguida, selecione **salvar**. 
 
Se você estiver aplicando uma política a mais de um usuário, selecione **usuários** no painel de navegação à esquerda e, em seguida, selecione cada usuário clicando à esquerda do nome do usuário e, em seguida, clique em **Editar configurações**. No painel **Editar configurações** , em **política de reunião**, selecione a política na lista suspensa e, em seguida, selecione **salvar**.
 
Você também pode atribuir uma política de reunião a um ou mais usuários da seguinte maneira:

1. Acesse **o centro** > de administração do Microsoft Teams,**políticas de reunião**de**reuniões** > .
2. Selecione a política clicando à esquerda do nome da política.
3. Selecione **gerenciar usuários**.
4. No painel **gerenciar usuários** , procure pelo usuário por nome para exibição ou por nome de usuário, selecione o nome e, em seguida, selecione **Adicionar**. Repita esta etapa para cada usuário que você deseja adicionar.
5. Quando tiver terminado de adicionar usuários, selecione **salvar**.
 
> [!NOTE] 
> Você não pode excluir uma política se os usuários estiverem atribuídos a ela. Você deve primeiro atribuir uma política diferente para todos os usuários afetados e, em seguida, pode excluir a política original.
 
## <a name="meeting-policy-settings"></a>Configurações da política de reunião

Ao selecionar uma política existente na página **políticas de reunião** ou selecionar **nova política** para adicionar uma nova política, você pode definir as configurações para o seguinte.

- [Geral](#meeting-policy-settings---general)
- [Áudio & vídeo](#meeting-policy-settings---audio--video)
- [Compartilhamento de conteúdo](#meeting-policy-settings---content-sharing)
- [Participantes & convidados](#meeting-policy-settings---participants--guests)

::: zone-end 

<a name="bkgeneral"> </a>

## <a name="meeting-policy-settings---general"></a>Configurações da política de reunião-geral

- [Permitir reunir agora em canais](#allow-meet-now-in-channels)
- [Permitir reunião privada agora (disponível em breve)](#allow-private-meet-now-coming-soon)
- [Permitir o suplemento do Outlook](#allow-the-outlook-add-in)
- [Permitir agendamento de reunião de canal](#allow-channel-meeting-scheduling)
- [Permitir agendamento de reuniões particulares](#allow-scheduling-private-meetings)

### <a name="allow-meet-now-in-channels"></a>Permitir reunir agora em canais

Esta é uma política por usuário e se aplica antes de iniciar uma reunião. Esta configuração controla se um usuário pode iniciar uma reunião ad-hoc em um canal do teams. Se você ativar esta opção, quando um usuário postar uma mensagem em um canal do Teams, o usuário pode clicar em **reunir agora** abaixo da caixa de texto para iniciar uma reunião ad-hoc no canal.

![Captura de tela mostrando o ícone reunir agora abaixo de uma mensagem](media/meeting-policies-meet-now.png)

### <a name="allow-private-meet-now-coming-soon"></a>Permitir reunião privada agora (disponível em breve)

Esta é uma política por usuário e se aplica antes de iniciar uma reunião. Esta configuração controla se um usuário pode iniciar uma reunião privada ad hoc.  

### <a name="allow-the-outlook-add-in"></a>Permitir o suplemento do Outlook

Esta é uma política por usuário e se aplica antes de iniciar uma reunião. Esta configuração controla se as reuniões de equipes podem ser agendadas dentro do Outlook (Windows, Mac, Web e celular).

![Captura de tela mostrando a capacidade de agendar uma nova reunião](media/meeting-policies-outlook-add-in.png)

Se você desativar essa opção, os usuários não poderão agendar reuniões do teams ao criarem uma nova reunião no Outlook. Por exemplo, no Outlook no Windows, a **nova** opção de reunião do Teams não aparece na faixa de opções.

### <a name="allow-channel-meeting-scheduling"></a>Permitir agendamento de reunião de canal

Esta é uma política por usuário e se aplica antes de iniciar uma reunião. Esta configuração controla se os usuários podem agendar uma reunião em um canal do teams.  Se você desativar essa opção, a opção **agendar uma reunião** não estará disponível para o usuário quando ele iniciar uma reunião em um canal do Teams e a opção **selecionar um canal para atender** não estará disponível para o usuário quando eles agendarem uma reunião a partir de reuniões no Microsoft Teams.

![Captura de tela mostrando a opção agendar uma reunião no Microsoft Teams](media/meeting-policies-schedule-a-meeting.png)

![Captura de tela mostrando a opção Selecionar um canal para se reunir](media/meeting-policies-select-a-channel-to-meet-in.png)

### <a name="allow-scheduling-private-meetings"></a>Permitir agendamento de reuniões particulares

Esta é uma política por usuário e se aplica antes de iniciar uma reunião. Esta configuração controla se os usuários podem agendar reuniões privadas no Teams. Uma reunião é particular quando não é publicada em um canal de uma equipe.

Observe que, se você desativar a opção **permitir reuniões privadas de agendamento** e **permitir agendamento de reunião de canal**, a opção agendar **uma reunião** não estará disponível e os usuários não poderão agendar reuniões no Microsoft Teams.

<a name="bkaudioandvideo"> </a>

## <a name="meeting-policy-settings---audio--video"></a>Configurações da política de reunião-áudio & vídeo

- [Permitir transcrição](#allow-transcription)
- [Permitir gravação na nuvem](#allow-cloud-recording)
- [Permitir vídeo IP](#allow-ip-video)
- [Taxa de bits de mídia (KBs)](#media-bit-rate-kbs)
- [Habilitar legendas dinâmicas (em breve)](#enable-live-captions-coming-soon)

### <a name="allow-transcription"></a>Permitir transcrição

Trata-se de uma combinação de uma política por organização e por usuário. Esta configuração controla se as legendas e os recursos de transcrição estão disponíveis durante a reprodução de gravações de reunião. Se você desativar essa opção, as opções de **pesquisa** e **CC** não estarão disponíveis durante a reprodução de uma gravação de reunião. A pessoa que iniciou a gravação precisa desta configuração ativada para que a gravação também inclua transcrição. 

Observe que a transcrição para reuniões gravadas no momento só tem suporte para os usuários que têm o idioma no Microsoft Teams definido como Inglês e quando o inglês está falado na reunião.

![Captura de tela mostrando as opções de transcrição em uma reunião](media/meeting-policies-transcription.png)

### <a name="allow-cloud-recording"></a>Permitir gravação na nuvem

Trata-se de uma combinação de uma política por organização e por usuário. Esta configuração controla se as reuniões deste usuário podem ser registradas. A gravação pode ser iniciada pelo organizador da reunião ou por outro participante da reunião se a configuração de política estiver ativada para o participante e se for um usuário autenticado da mesma organização.

Pessoas de fora da sua organização, como usuários federados e anônimos, não podem iniciar a gravação. Os usuários convidados não podem iniciar ou parar a gravação. 

![Captura de tela mostrando as opções de gravação](media/meeting-policies-recording.png)

Vamos dar uma olhada no exemplo a seguir.

|Usuário |Política de reunião  |Permitir gravação na nuvem |
|---------|---------|---------|
|Daniela | Global   | False |
|Amanda | Location1MeetingPolicy | True|
|John (usuário externo) | Não aplicável | Não aplicável|

Reuniões organizadas por Daniela não podem ser gravadas e Amanda, que tem a configuração de política habilitada, não pode gravar reuniões organizadas por Daniela. Reuniões organizadas por Amanda podem ser registradas, no entanto, Daniela, que têm a configuração de política desabilitada e John, que é um usuário externo, não pode gravar reuniões organizadas por Amanda.

Para saber mais sobre a gravação de reunião em nuvem, consulte [gravação de reunião na nuvem](cloud-recording.md)do teams.

### <a name="allow-ip-video"></a>Permitir vídeo IP

Trata-se de uma combinação de uma política por organização e por usuário. Vídeo é um componente importante para reuniões. Em algumas organizações, os administradores podem querer ter mais controle sobre quais reuniões de usuários têm vídeo. Esta configuração controla se o vídeo pode ser ativado em reuniões hospedadas por um usuário e em chamadas do 1:1 e chamadas em grupo iniciadas por um usuário. Reuniões organizadas por um usuário que tem essa política habilitada, permitir o compartilhamento de vídeo na reunião pelos participantes da reunião, se os participantes da reunião também tiverem a política habilitada. Os participantes da reunião que não têm políticas atribuídas (por exemplo, participantes anônimos e federados) herdam a política do organizador da reunião.

![Captura de tela mostrando uma reunião com configurações de áudio e vídeo](media/meeting-policies-audio-video-settings.png)

Vamos dar uma olhada no exemplo a seguir.

|Usuário |Política de reunião  |Permitir vídeo IP |
|---------|---------|---------|
|Daniela   | Global   | True        |
|Amanda    | Location1MeetingPolicy        | False      |

Reuniões hospedadas pela Daniela permitem que o vídeo seja ativado. Daniela pode ingressar na reunião e ativar o vídeo. O Amanda não pode ativar o vídeo na reunião do Daniela porque a política de Amanda está definida como não permitir vídeo. Amanda pode ver vídeos compartilhados por outros participantes da reunião.

Em reuniões hospedadas pela Amanda, ninguém pode ativar o vídeo, independentemente da política de vídeo atribuída a ele. Isso significa que o Daniela não pode ativar o vídeo nas reuniões do Amanda.  

Se Daniela chama Amanda com vídeo ativado, o Amanda pode atender a chamada somente com áudio.  Quando a chamada estiver conectada, Amanda poderá ver o vídeo do Daniela, mas não poderá ativar o vídeo. Se o Amanda chama Daniela, Daniela pode atender a chamada com vídeo e áudio. Quando a chamada estiver conectada, o Daniela poderá ativar ou desativar o vídeo, conforme necessário.

### <a name="media-bit-rate-kbs"></a>Taxa de bits de mídia (KBs)

Esta é uma política por usuário. Essa configuração determina a taxa de bits de mídia para transmissões de compartilhamento de áudio, vídeo e aplicativos baseados em vídeo em chamadas e reuniões para o usuário. Ela é aplicada à passagem de mídia uplink e de downlink para usuários na chamada ou reunião. Essa configuração lhe dá controle granular sobre o gerenciamento da largura de banda em sua organização. Dependendo dos cenários de reuniões exigidos pelos usuários, recomendamos ter largura de banda suficiente para ter uma boa experiência de qualidade. O valor mínimo é de 30 kbps e o valor máximo depende do cenário da reunião. Para saber mais sobre a largura de banda mínima recomendada para reuniões de boa qualidade, chamadas e eventos dinâmicos no Teams, consulte [requisitos de largura de banda](prepare-network.md#bandwidth-requirements).

Se não houver largura de banda suficiente para uma reunião, os participantes verão uma mensagem indicando uma qualidade de rede ruim.

Para reuniões que precisam de experiência com vídeo de alta qualidade, como reuniões de tabuleiro de CEO e eventos ao vivo da equipe, recomendamos que você defina a largura de banda como 10 Mbps. Mesmo quando a experiência máxima é definida, a pilha de mídia do teams se adapta às condições de pouca largura de banda quando determinadas condições de rede são detectadas, dependendo do cenário. 

### <a name="enable-live-captions-coming-soon"></a>Habilitar legendas dinâmicas (em breve)

Esta é uma política por usuário e aplica-se durante uma reunião. Se essa configuração estiver ativada, o usuário verá uma opção para exibir legendas durante uma reunião.

<a name="bkcontentsharing"> </a>

## <a name="meeting-policy-settings---content-sharing"></a>Configurações da política de reunião – compartilhamento de conteúdo

- [Modo de compartilhamento de tela](#screen-sharing-mode)
- [Permitir que um participante conceda ou solicite o controle](#allow-a-participant-to-give-or-request-control)
- [Permitir que um participante externo conceda ou solicite controle](#allow-an-external-participant-to-give-or-request-control)
- [Permitir compartilhamento do PowerPoint](#allow-powerpoint-sharing)
- [Permitir quadro de comunicações](#allow-whiteboard)
- [Permitir anotações compartilhadas](#allow-shared-notes)
- [Permitir chat em reuniões (disponível em breve)](#allow-chat-in-meetings-coming-soon)

### <a name="screen-sharing-mode"></a>Modo de compartilhamento de tela

Trata-se de uma combinação de uma política por organização e por usuário. Esta configuração controla se a área de trabalho e/ou o compartilhamento de janela é permitida na reunião do usuário. Os participantes da reunião que não têm políticas atribuídas (por exemplo, participantes anônimos, convidados, B2B e federados) herdam a política do organizador da reunião.

|Valor de configuração |Comportamento  |
|---------|---------|
|**Tela inteira**    | Compartilhamento de área de trabalho e compartilhamento de aplicativos completos são permitidos na reunião |
|**Único aplicativo**   | O compartilhamento de aplicativos é permitido na reunião        |
|**Desabilitado**     |Compartilhamento de tela e compartilhamento de aplicativos desativados na reunião.       |

Vamos dar uma olhada no exemplo a seguir.

|Usuário |Política de reunião |Modo de compartilhamento de tela |
|---------|---------|---------|
|Daniela  | Global   | Tela inteira |
|Amanda   | Location1MeetingPolicy  | Desabilitado |

Reuniões hospedadas pela Daniela permitem que os participantes da reunião compartilhem sua tela inteira ou um aplicativo específico. Se o Amanda entrar na reunião do Daniela, o Amanda não poderá compartilhar a tela ou um aplicativo específico, pois a configuração da política estará desabilitada. Em reuniões hospedadas pela Amanda, ninguém tem permissão para compartilhar a tela ou um único aplicativo, independentemente da política do modo de compartilhamento de tela atribuída a eles. Isso significa que o Daniela não pode compartilhar sua tela ou um único aplicativo nas reuniões do Amanda.  

Atualmente, os usuários não podem reproduzir vídeo ou compartilhar sua tela em uma reunião do teams se estiverem usando o Google Chrome.

### <a name="allow-a-participant-to-give-or-request-control"></a>Permitir que um participante conceda ou solicite o controle

Esta é uma política por usuário. Esta configuração controla se o usuário pode dar o controle da área de trabalho ou janela compartilhada para outros participantes da reunião. Para dar controle, passe o mouse sobre a parte superior da tela. 

Se essa configuração estiver ativada para o usuário, a opção **conceder controle** será exibida na barra superior de uma sessão de compartilhamento. 

![Captura de tela mostrando a opção conceder controle](media/meeting-policies-give-control.png)

Se as configurações estiverem desativadas para o usuário, a opção **conceder controle** não estará disponível.

![Captura de tela mostrando que a opção conceder controle não está disponível](media/meeting-policies-give-control-not-available.png)

Vamos dar uma olhada no exemplo a seguir.

|Usuário |Política de reunião  |Permitir que o participante conceda ou solicite o controle |
|---------|---------|---------|
|Daniela   | Global   | True       |
|Babek    | Location1MeetingPolicy        | False   |

O Daniela pode dar ao controle da área de trabalho compartilhada ou janela para outros participantes de uma reunião organizada por Babek, enquanto o Babek não pode conceder ao controle outros participantes.

### <a name="allow-an-external-participant-to-give-or-request-control"></a>Permitir que um participante externo conceda ou solicite controle

Esta é uma política por usuário. Esta configuração controla se os participantes externos em uma reunião podem dar o controle da sua área de trabalho compartilhada ou janela para outros participantes da reunião. Os participantes externos em reuniões de equipes podem ser categorizados da seguinte maneira:  

   - Usuário anônimo
   - Usuários convidados  
   - Usuário B2B
   - Usuário federado  

Se os usuários federados podem dar controle aos usuários externos enquanto o compartilhamento é controlado pela configuração **permitir que um participante externo conceda ou solicite o controle** em sua organização.

### <a name="allow-powerpoint-sharing"></a>Permitir compartilhamento do PowerPoint

Esta é uma política por usuário. Esta configuração controla se o usuário pode compartilhar apresentações de slides do PowerPoint em uma reunião. Usuários externos, incluindo usuários anônimos, convidados e federados, herdam a política do organizador da reunião.

Vamos dar uma olhada no exemplo a seguir.

|Usuário |Política de reunião  |Permitir compartilhamento do PowerPoint |
|---------|---------|---------|
|Daniela   | Global   | True       |
|Amanda   | Location1MeetingPolicy        | False   |

O Amanda não pode compartilhar apresentações de slides do PowerPoint em reuniões, mesmo que ela seja o organizador da reunião. Daniela pode compartilhar decks de slides do PowerPoint mesmo se a reunião for organizada por Amanda. O Amanda pode exibir os decks de slides do PowerPoint compartilhados por outras pessoas na reunião, mesmo que ele não possa compartilhar os slides do PowerPoint.

### <a name="allow-whiteboard"></a>Permitir quadro de comunicações

Esta é uma política por usuário. Esta configuração controla se um usuário pode compartilhar o quadro de comunicações em uma reunião. Usuários externos, incluindo usuários anônimos, B2B e federados, herdam a política do organizador da reunião. 

Vamos dar uma olhada no exemplo a seguir.

|Usuário |Política de reunião  |Permitir quadro de comunicações|
|---------|---------|---------|
|Daniela   | Global   | True       |
|Amanda   | Location1MeetingPolicy        | False   |

O Amanda não pode compartilhar o quadro de comunicações em uma reunião, mesmo que ela seja o organizador da reunião. Daniela pode compartilhar o quadro de comunicações mesmo se uma reunião for organizada por Amanda.  

### <a name="allow-shared-notes"></a>Permitir anotações compartilhadas

Esta é uma política por usuário. Esta configuração controla se um usuário pode criar e compartilhar anotações em uma reunião. Usuários externos, incluindo usuários anônimos, B2B e federados, herdam a política do organizador da reunião. No momento, a guia **anotações da reunião** só tem suporte em reuniões com menos de 20 participantes. 

Vamos dar uma olhada no exemplo a seguir.

|Usuário |Política de reunião  |Permitir anotações compartilhadas |
|---------|---------|---------|
|Daniela   | Global   | True       |
|Amanda   | Location1MeetingPolicy | False |

Daniela pode fazer anotações nas reuniões do Amanda, e o Amanda não pode fazer anotações em nenhuma reunião.

### <a name="allow-chat-in-meetings-coming-soon"></a>Permitir chat em reuniões (disponível em breve)

Esta é uma política por organizador. Esta configuração controla se o chat da reunião é permitido na reunião do usuário. 

<a name="bkparticipantsandguests"> </a>

## <a name="meeting-policy-settings---participants--guests"></a>Configurações de política de reunião-participantes & convidados

Essas configurações controlam quais participantes da reunião aguardam no lobby antes de serem admitidos para a reunião e o nível de participação que eles são permitidos em uma reunião.

- [Admitir pessoas automaticamente](#automatically-admit-people)
- [Permitir que pessoas anônimas iniciem uma reunião](#allow-anonymous-people-to-start-a-meeting)
- [Permitir que os usuários de discagem ignorem o lobby](#allow-dial-in-users-to-bypass-the-lobby-coming-soon)
- [Permitir que os organizadores substituam as configurações de lobby](#allow-organizers-to-override-lobby-settings-coming-soon)

> [!NOTE]
>As opções para ingressar em uma reunião irão variar, dependendo das configurações de cada grupo de equipe e do método de conexão. Se o seu grupo tiver videoconferência e o usar para se conectar, consulte [videoconferência no Office 365](https://docs.microsoft.com/microsoftteams/audio-conferencing-in-office-365). Se o grupo Teams não tiver videoconferências, consulte [ingressar em uma reunião no Teams](https://support.office.com/article/join-a-meeting-in-teams-1613bb53-f3fa-431e-85a9-d6a91e3468c9).

### <a name="automatically-admit-people"></a>Admitir pessoas automaticamente

Esta é uma política por organizador. Esta configuração controla se as pessoas ingressam em uma reunião diretamente ou esperam no lobby até serem admitidas por um usuário autenticado.

![Captura de tela mostrando uma reunião com um usuário no lobby](media/meeting-policies-lobby.png)

 Os organizadores da reunião podem clicar em **Opções de reunião** no convite da reunião para alterar essa configuração para cada reunião agendada. **(disponível em breve)**
  
|Valor de configuração  |Comportamento da junção |
|---------|---------|
|**Todos**   |Todos os participantes da reunião ingressam na reunião diretamente sem esperar no lobby. Isso inclui usuários autenticados, usuários federados, convidados, usuários anônimos e pessoas que discam por telefone.       |
|**Todos em sua organização e organizações federadas**     |Usuários autenticados dentro da organização, incluindo usuários convidados e os usuários de organizações federadas, ingressam na reunião diretamente sem esperar no lobby.  Usuários anônimos e usuários que discam por telefone aguarde no lobby.   |
|**Todos em sua organização**    |Os usuários autenticados de dentro da organização, incluindo os usuários convidados, ingressam na reunião diretamente sem esperar no lobby.  Usuários federados, usuários anônimos e usuários que discam por telefone aguarde no lobby.           |

### <a name="allow-anonymous-people-to-start-a-meeting"></a>Permitir que pessoas anônimas iniciem uma reunião

Esta é uma política por organizador. Essa configuração controla se as pessoas anônimas, incluindo B2B e usuários federados, podem ingressar na reunião do usuário sem um usuário autenticado da organização em participação. 

![Captura de tela mostrando uma mensagem para um usuário em espera](media/meeting-policies-anonymous-user-lobby.png)

Aqui está o comportamento da junção de pessoas anônimas quando os usuários autenticados estão presentes na reunião.

|Permitir que pessoas anônimas iniciem uma reunião  |Admitir pessoas automaticamente |Ingressar no comportamento de pessoas anônimas |
|---------|---------|---------|
|True    | Todos      | Ingressar diretamente         |
|   | Todos em sua organização       | Aguardar no lobby        |
|   | Todos em sua organização e organizações federadas       | Aguardar no lobby         |
|False    | Todos        | Ingressar diretamente        |
|   | Todos em sua organização     | Aguardar no lobby        |
|   | Todos em sua organização e organizações federadas      | Aguardar no lobby         |

Aqui está o comportamento da junção de pessoas anônimas quando nenhum usuário autenticado está presente na reunião.

|Permitir que pessoas anônimas iniciem uma reunião |Admitir pessoas automaticamente  |Ingressar no comportamento de pessoas anônimas |
|---------|---------|---------|
|True    | Todos      | Ingressar diretamente         |
|   | Todos em sua organização       | Aguardar no lobby        |
|   | Todos em sua organização e organizações federadas       | Aguardar no lobby         |
|False    | Todos        | Aguardar no lobby. Os usuários são automaticamente admitidos quando o primeiro usuário autenticado entra na reunião.        |
|   | Todos em sua organização     |Aguardar no lobby         |
|   | Todos em sua organização e organizações federadas      | Aguardar no lobby         |

### <a name="allow-dial-in-users-to-bypass-the-lobby-coming-soon"></a>Permitir que os usuários de discagem ignorem o lobby (em breve)

Esta é uma política por organizador. Esta configuração controla se as pessoas que discam por telefone entram diretamente na reunião ou esperam no lobby, independentemente da configuração de usuário **admitir pessoas automaticamente** .

Aqui está o comportamento da junção de pessoas que discam por telefone.

|Permitir que os usuários de discagem ignorem o lobby  |Admitir usuários automaticamente  |Comportamento de junção de pessoas que discam |
|---------|---------|---------|
|True    | Todos      | Ingressar diretamente         |
|   | Todos em sua organização       | Ingressar diretamente        |
|   | Todos em sua organização e organizações federadas       | Ingressar diretamente         |
|False    | Todos        | Ingressar diretamente        |
|   | Todos em sua organização     |Aguardar no lobby         |
|   | Todos em sua organização e organizações federadas      | Aguardar no lobby         |

### <a name="allow-organizers-to-override-lobby-settings-coming-soon"></a>Permitir que os organizadores substituam as configurações de lobby (disponível em breve)

Esta é uma política por organizador. Esta configuração controla se o organizador da reunião pode substituir as configurações de lobby que um administrador definiu para **admitir automaticamente as pessoas** e **permitir que os usuários de discagem ignorem o lobby** quando eles agendam uma nova reunião. 

Os organizadores da reunião podem clicar em **Opções de reunião** no convite da reunião para alterar as configurações de lobby de cada reunião que elas agendam. 

Veja como essa configuração afeta se o organizador da reunião pode alterar a configuração **admitir pessoas automaticamente** para cada reunião agendada pelo organizador.

|Permitir que os organizadores substituam as configurações de lobby  |Admitir pessoas automaticamente  |Comportamento |
|---------|---------|---------|
|True    | Todos      | O organizador pode alterar a configuração para qualquer outro valor. |
|   | Todos em sua organização       | O organizador pode alterar a configuração para qualquer outro valor.|
|   | Todos em sua organização e organizações federadas       | O organizador pode alterar isso para qualquer outro valor.         |
|False    | Todos        | O organizador pode alterar a configuração para qualquer outro valor.|
|   | Todos em sua organização     |O organizador pode alterar a configuração para **todos em sua organização**. |
|   | Todos em sua organização e organizações federadas      | O organizador não substitui a configuração de lobby. |

Veja como essa configuração afeta se o organizador da reunião pode alterar o **permitir que os usuários de discagem ignorem a** configuração de lobby para cada reunião agendada pelo organizador.
    
|Permitir que os organizadores substituam as configurações de lobby  |Permitir que os usuários de discagem ignorem o lobby  |Comportamento |
|---------|---------|---------|
|True    |  True        | O organizador pode alterar a configuração para false.       |
|True      | False         | O organizador pode alterar a configuração para true.        |
|False     | True        |O organizador pode alterar a configuração para false.         |
|False      |False          |O organizador não substitui a configuração de lobby e não pode permitir que os usuários de discagem ignorem o lobby na reunião.        |

[Artigo completo](meeting-policies-in-teams.md)

## <a name="related-topics"></a>Tópicos relacionados
[Políticas de mensagens no Teams](messaging-policies-in-teams.md)
