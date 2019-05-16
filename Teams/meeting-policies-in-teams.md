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
description: Saiba como gerenciar as configurações de diretiva em equipes de reunião.
ms.openlocfilehash: 99458e71ae02eb6307b3f363dbf7e060e1b4ed5b
ms.sourcegitcommit: 85b135cf622c9e9eb1857ef953bc618dc2cdb51e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/15/2019
ms.locfileid: "34036625"
---
# <a name="manage-meeting-policies-in-teams"></a>Gerenciar políticas de reunião em equipes

::: zone target="docs"
Políticas de reunião são usadas para controlar os recursos disponíveis aos participantes para reuniões agendadas por usuários em sua organização da reunião. Depois de criar uma política e faça as alterações, você pode atribuir usuários à diretiva. Você gerenciar políticas de reunião no Centro de administração do Microsoft Teams ou usando o [PowerShell](teams-powershell-overview.md).

Você pode implantar políticas das seguintes maneiras, que afetam a experiência de reunião para usuários antes de uma reunião é iniciado, durante uma reunião ou após uma reunião. 

|Tipo de implementação  |Descrição  |
|---------|---------|
|Por organizador    |Quando você implementa uma diretiva por organizador, todos os participantes da reunião herdam a política do organizador. Por exemplo, **automaticamente admitir pessoas** é uma política por organizador e controles se os usuários ingressem na reunião diretamente ou aguardam no lobby para reuniões agendadas pelo usuário que recebeu a política.          |
|Por usuário    |Quando você implementa uma diretiva por usuário, somente a diretiva por usuário é aplicada para restringir determinados recursos para os participantes do organizador e/ou reunião. Por exemplo, se você **Permitir reunir agora** , é uma política por usuário.     |
|Por organizador e por usuário     |Quando você implementa uma combinação de uma diretiva por organizador e por usuário, alguns recursos são restritos para os participantes com base em sua política e política do organizador da reunião. Por exemplo, a **gravação de nuvem permitir** é uma política por organizador e por usuário. Ative essa configuração para permitir que o organizador da reunião e os participantes para iniciar e parar uma gravação. 

Por padrão, uma política de chamada Global (toda a organização padrão) é criada. Todos os usuários em sua organização serão atribuídos a política de reunião por padrão. Você pode fazer alterações para esta política ou criar uma ou mais políticas personalizadas e atribuir usuários a eles. Quando você cria uma política personalizada, você pode permitir ou impedir que certos recursos disponíveis para os usuários e atribuí-la a um ou mais usuários com as configurações aplicadas a eles. 

## <a name="change-or-create-a-meeting-policy"></a>Alterar ou criar uma política de reunião

Para alterar ou criar uma política de reunião, vá para a administração de Teams Microsoft center gt _ **reuniões** > **políticas de reunião**. Selecione uma política na lista ou selecione **nova política**. Se você estiver criando uma nova política, adicione um nome e descrição. O nome não pode conter caracteres especiais ou ter mais de 64 caracteres. Escolher as configurações e selecione **Salvar**.

Por exemplo, digamos que você tem um monte de usuários e deseja limitar a quantidade de largura de banda que exigiria sua reunião. Crie uma nova política personalizada denominada "Largura de banda limitada" e desabilitar as configurações a seguir:

Em **áudio & vídeo**:
- Desative a nuvem de gravação
- Desativar vídeo IP permitidos

Em **compartilhamento de conteúdo**:
- Desabilitar o modo de compartilhamento de tela
- Desativar o quadro de comunicações
- Desativar anotações compartilhadas

Em seguida, atribua a política aos usuários.

> [!NOTE] 
> Um usuário pode ser atribuído a política de reunião de apenas um por vez. 

## <a name="assign-a-meeting-policy-to-users"></a>Atribuir uma política de reunião aos usuários

Se você estiver aplicando a política a um usuário, selecione **os usuários** no painel de navegação à esquerda e clique em nome para exibição do usuário. Na página do usuário, ao lado de **políticas atribuído**, selecione **Editar**. Em seguida, no painel **Editar políticas de usuário** , em **política de reunião**, selecione a política de reunião na lista suspensa e selecione **Salvar**. Você também pode atribuir políticas da lista de usuários. Para fazer isso, selecione o usuário clicando à esquerda do nome para exibição do usuário. Selecione **Editar configurações**. Em seguida, no painel **Editar configurações** , em **política de reunião**, selecione a política na lista suspensa e selecione **Salvar**. 
 
Se você estiver aplicando uma política a mais de um usuário, selecione os **usuários** no painel de navegação à esquerda e selecione cada usuário clicando à esquerda do nome de usuário e, em seguida, clique em **Editar configurações**. No painel **Editar configurações** , em **política de reunião**, selecione a política na lista suspensa e, em seguida, selecione **Salvar**.
 
Você também pode atribuir uma política de reunião para um ou mais usuários da seguinte maneira:

1. Vá para **o Centro de administração do Microsoft equipes** > **reuniões** > **políticas de reunião**.
2. Selecione a política clicando à esquerda do nome da política.
3. Selecione **Gerenciar usuários**.
4. No painel de **Gerenciar usuários** , procure o usuário pelo nome de exibição ou nome de usuário, selecione o nome e selecione **Adicionar**. Repita essa etapa para cada usuário que você deseja adicionar.
5. Quando você terminar de adicionar usuários, selecione **Salvar**.
 
> [!NOTE] 
> Você não pode excluir uma política, se os usuários são atribuídos a ela. Você deve primeiro atribuir uma política diferente a todos os usuários afetados e, em seguida, você pode excluir a diretiva original.
 
## <a name="meeting-policy-settings"></a>Configurações de política de reunião

Quando você seleciona uma política existente na página de **políticas de reunião** ou selecione **nova política** para adicionar uma nova diretiva, você pode configurar as definições para o seguinte.

- [Geral](#meeting-policy-settings---general)
- [Áudio & de vídeo](#meeting-policy-settings---audio--video)
- [Compartilhamento de conteúdo](#meeting-policy-settings---content-sharing)
- [Convidados que & participantes](#meeting-policy-settings---participants--guests)

::: zone-end 

<a name="bkgeneral"> </a>

## <a name="meeting-policy-settings---general"></a>Configurações de política de reunião - geral

- [Permitir reunir agora no canais](#allow-meet-now-in-channels)
- [Permitir privado reunir agora (em breve)](#allow-private-meet-now-coming-soon)
- [Permitir que o suplemento do Outlook](#allow-the-outlook-add-in)
- [Permitir o agendamento de reunião de canal](#allow-channel-meeting-scheduling)
- [Permitir o agendamento de reuniões privadas](#allow-scheduling-private-meetings)

### <a name="allow-meet-now-in-channels"></a>Permitir reunir agora no canais

Esta é uma política por usuário e aplica antes de uma reunião é iniciado. Esta configuração controla se um usuário pode iniciar uma reunião ad hoc em um canal de equipes. Se você ativar isso, quando um usuário posta uma mensagem em um canal de equipes, o usuário pode clicar em **Reunir agora** abaixo da caixa de redação para iniciar uma reunião ad hoc no canal.

![políticas de reunião-now.png reunir](media/meeting-policies-meet-now.png)

### <a name="allow-private-meet-now-coming-soon"></a>Permitir privado reunir agora (em breve)

Esta é uma política por usuário e aplica antes de uma reunião é iniciado. Esta configuração controla se um usuário pode iniciar uma reunião privada ad hoc.  

### <a name="allow-the-outlook-add-in"></a>Permitir que o suplemento do Outlook

Esta é uma política por usuário e aplica antes de uma reunião é iniciado. Esta configuração controla se as reuniões de equipes podem ser agendadas de dentro do Outlook (Windows, Mac, web e móveis).

![reunião-políticas-outlook-adicionar-in.png](media/meeting-policies-outlook-add-in.png)

Se você desativar esse recurso, os usuários não conseguem agendar reuniões de equipes, quando eles criam uma nova reunião no Outlook. Por exemplo, no Outlook no Windows, a opção de **Nova reunião de equipes** não mostrada na faixa de opções.

### <a name="allow-channel-meeting-scheduling"></a>Permitir o agendamento de reunião de canal

Esta é uma política por usuário e aplica antes de uma reunião é iniciado. Esta configuração controla se os usuários podem agendar uma reunião em um canal de equipes.  Se você desativar esse recurso, a opção de **Agendar uma reunião** não estarão disponível para o usuário quando eles iniciarem uma reunião em um canal de equipes e a opção de **Selecionar um canal para cumprir** não estarão disponível para o usuário quando eles agendam uma reunião de reuniões em equipes.

![reunião políticas agenda uma meeting.png](media/meeting-policies-schedule-a-meeting.png)

![Meeting-Policies-Select-a-Channel-to-meet-in.PNG](media/meeting-policies-select-a-channel-to-meet-in.png)

### <a name="allow-scheduling-private-meetings"></a>Permitir o agendamento de reuniões privadas

Esta é uma política por usuário e aplica antes de uma reunião é iniciado. Esta configuração controla se os usuários podem agendar reuniões privadas em equipes. Uma reunião é particular, quando ele não é publicado em um canal de uma equipe.

Observe que se você desativar **Permitir o agendamento de reuniões privadas** e **agendamento de reuniões de canal permitir**, a opção de **Agendar uma reunião** não estará disponível e os usuários poderão agendar reuniões em equipes.

<a name="bkaudioandvideo"> </a>

## <a name="meeting-policy-settings---audio--video"></a>Configurações de política de reunião - áudio & vídeo

- [Permitir a transcrição](#allow-transcription)
- [Permitir a nuvem de gravação](#allow-cloud-recording)
- [Permitir IP vídeo](#allow-ip-video)
- [Taxa de bits de mídia (KBs)](#media-bit-rate-kbs)
- [Habilitar legendas live (em breve)](#enable-live-captions-coming-soon)

### <a name="allow-transcription"></a>Permitir a transcrição

Isso é uma combinação de uma política por organizador e por usuário. Esta configuração controla se os recursos de transcrição e legendas estão disponíveis durante a reprodução de reunião gravações. Se você desativar esse recurso, as opções de **pesquisa** e **CC** não estarão disponíveis durante a reprodução de gravação de uma reunião. A pessoa que iniciou a gravação precisa essa configuração ativada para que a gravação também inclui a transcrição. 

Observe que as transcrições de reuniões gravadas está atualmente só tem suporte para usuários que têm o idioma em equipes definidas como inglês e quando inglês é falado na reunião.

![Reunião de políticas-transcription.png](media/meeting-policies-transcription.png)

### <a name="allow-cloud-recording"></a>Permitir a nuvem de gravação

Isso é uma combinação de uma política por organizador e por usuário. Esta configuração controla se as reuniões desse usuário poderão ser registradas. A gravação pode ser iniciada pelo organizador da reunião ou por outro participante de reunião se a configuração de diretiva está ativada para o participante e se elas forem um usuário autenticado da mesma organização.

Pessoas de fora da sua organização, como usuários federados e anônimos, não é possível iniciar a gravação. Usuários convidados não podem iniciar ou parar a gravação. 

![Reunião de políticas-recording.png](media/meeting-policies-recording.png)

Vamos examinar o exemplo a seguir.

|Usuário |Política de reunião  |Permitir a nuvem de gravação |
|---------|---------|---------|
|Daniela | Global   | False |
|Amanda | Location1MeetingPolicy | True|
|John (usuários externos) | Não aplicável | Não aplicável|

Reuniões organizadas por Daniela não podem ser gravadas e Amanda, que tiver habilitada a configuração de política, não é possível gravar reuniões organizadas por Daniela. Reuniões organizadas por Amanda poderão ser registradas, no entanto, Daniela, que tem a configuração de diretiva desabilitada e John quem é um usuário externo, não é possível gravar reuniões organizadas por Amanda.

Para saber mais sobre a gravação de reunião de nuvem, consulte [equipes a gravação de reunião em nuvem](cloud-recording.md).

### <a name="allow-ip-video"></a>Permitir IP vídeo

Isso é uma combinação de uma política por organizador e por usuário. Vídeo é um componente essencial para reuniões. Em algumas organizações, os administradores talvez queira mais controle sobre reuniões dos quais usuários terão o vídeo. Essa configuração controla se o vídeo pode ser ativado em reuniões hospedadas por um usuário e em 1:1 chamadas e chamadas de grupo iniciadas por um usuário. Reuniões organizadas por um usuário que tenha habilitada, permitir o compartilhamento de vídeo na reunião, os participantes da reunião, se os participantes da reunião também tem a diretiva ativada. Os participantes da reunião que não têm nenhuma política atribuída (por exemplo, participantes anônimos e federados) herdam a política do organizador da reunião.

![reunião-políticas-áudio-vídeo-settings.png](media/meeting-policies-audio-video-settings.png)

Vamos examinar o exemplo a seguir.

|Usuário |Política de reunião  |Permitir vídeo IP |
|---------|---------|---------|
|Daniela   | Global   | True        |
|Amanda    | Location1MeetingPolicy        | False      |

Reuniões hospedadas pelo Daniela permitem vídeos para ser ativado. Daniela pode ingressar na reunião e ativar o vídeo. Não é possível ativar Amanda vídeo em Daniela reunião porque a política de Amanda está definida para não permitir vídeo. Amanda pode ver vídeos compartilhados por outros participantes da reunião.

Em reuniões hospedadas pelo Amanda, ninguém pode ativar o vídeo, independentemente da diretiva de vídeo atribuída a eles. Isso significa que não é possível ativar Daniela vídeo em reuniões de Amanda.  

Se Daniela chama Amanda com vídeo em, Amanda pode atender a chamada com apenas de áudio.  Quando a chamada é conectada, Amanda pode ver o vídeo de Daniela, mas não pode ativar o vídeo. Se Amanda chama Daniela, Daniela pode atender a chamada com áudio e vídeo. Quando a chamada é conectada, Daniela pode ativar ou desativar seu vídeo, conforme necessário.

### <a name="media-bit-rate-kbs"></a>Taxa de bits de mídia (KBs)

Esta é uma política por organizador. Essa configuração determina a taxa de bits de mídia de áudio, vídeo e vídeo-based aplicativo compartilhamento transmissões em chamadas e reuniões para o usuário. Ela será aplicada a passagem da mídia de conexão tanto o downlink para usuários na chamada ou reunião. Essa configuração fornece controle granular sobre gerenciamento de largura de banda em sua organização. Dependendo os cenários de reuniões necessários pelos usuários, é recomendável ter largura de banda suficiente no local para uma experiência de boa qualidade. O valor mínimo é 30 Kbps e o valor máximo depende do cenário de reunião. Para saber mais sobre o mínimo recomendado de largura de banda para boa qualidade reuniões, chamadas e eventos ao vivo em equipes, consulte [requisitos de largura de banda](prepare-network.md#bandwidth-requirements).

Se não houver largura de banda suficiente para uma reunião, os participantes veem uma mensagem que indica a baixa qualidade da rede.

Para reuniões que precisam de maior qualidade de experiência de vídeo, como CEO placa para reuniões e eventos ao vivo de equipes, recomendamos que você definir a largura de banda para 10 Mbps. Mesmo quando a experiência máxima for definida, a pilha de mídia de equipes se adapta às condições de baixa largura de banda quando certas condições de rede são detectadas, dependendo do cenário. 

### <a name="enable-live-captions-coming-soon"></a>Habilitar legendas live (em breve)

Esta é uma política por usuário e se aplica durante uma reunião. Se essa configuração estiver ligado, o usuário vê uma opção para exibir as legendas durante uma reunião.

<a name="bkcontentsharing"> </a>

## <a name="meeting-policy-settings---content-sharing"></a>Configurações de política de reunião - compartilhamento de conteúdo

- [Modo de compartilhamento de tela](#screen-sharing-mode)
- [Permitir que um participante dar ou solicitar o controle](#allow-a-participant-to-give-or-request-control)
- [Permitir que um participante externo dar ou solicitar o controle](#allow-an-external-participant-to-give-or-request-control)
- [Permitir o compartilhamento do PowerPoint](#allow-powerpoint-sharing)
- [Permitir que o quadro de comunicações](#allow-whiteboard)
- [Permitir anotações compartilhadas](#allow-shared-notes)
- [Permitir bate-papo em reuniões (em breve)](#allow-chat-in-meetings-coming-soon)

### <a name="screen-sharing-mode"></a>Modo de compartilhamento de tela

Isso é uma combinação de uma política por organizador e por usuário. Esta configuração controla se a área de trabalho e/ou a janela de compartilhamento é permitido em reunião do usuário. Os participantes que não têm nenhuma política atribuída da reunião (por exemplo, anônimo, o convidado, B2B e participantes federados) herdam a política do organizador da reunião.

|Valor da configuração |Comportamento  |
|---------|---------|
|**Tela inteira**    | Compartilhamento de área de trabalho completa e compartilhamento de aplicativos é permitido na reunião |
|**Único aplicativo**   | Compartilhamento de aplicativos é permitido na reunião        |
|**Desabilitado**     |Compartilhamento de tela e aplicativo desativado na reunião.       |

Vamos examinar o exemplo a seguir.

|Usuário |Política de reunião |Modo de compartilhamento de tela |
|---------|---------|---------|
|Daniela  | Global   | Tela inteira |
|Amanda   | Location1MeetingPolicy  | Desabilitado |

Reuniões hospedadas pelo Daniela permitem que os participantes da reunião compartilhar sua tela inteira ou um aplicativo específico. Se Amanda ingressar em reuniões de Daniela, Amanda não pode compartilhar sua tela ou um aplicativo específico como sua configuração de política é desabilitada. Em reuniões hospedadas pelo Amanda, ninguém pode compartilhar sua tela ou um único aplicativo, independentemente da tela do compartilhamento de diretiva de modo a eles atribuídos. Isso significa que Daniela não é possível compartilhar sua tela ou um único aplicativo em reuniões de Amanda.  

Atualmente, os usuários não podem reproduzir vídeos ou compartilhar sua tela em uma reunião de equipes, se estiver usando o Google Chrome.

### <a name="allow-a-participant-to-give-or-request-control"></a>Permitir que um participante dar ou solicitar o controle

Esta é uma diretiva por usuário. Esta configuração controla se o usuário pode assumir o controle da janela ou área de trabalho compartilhada para outros participantes da reunião. Para conceder controle, passe o mouse sobre a parte superior da tela. 

Se essa configuração é ativada para o usuário, a opção **Conceder controle** é exibida na barra superior de uma sessão de compartilhamento. 

![políticas de reunião-control.png conceder](media/meeting-policies-give-control.png)

Se as configurações está desativada para o usuário, a opção **Conceder controle** não está disponível.

![Meeting-Policies-Give-Control-Not-Available.PNG](media/meeting-policies-give-control-not-available.png)

Vamos examinar o exemplo a seguir.

|Usuário |Política de reunião  |Permitir que o participante conceder ou solicitar controle |
|---------|---------|---------|
|Daniela   | Global   | True       |
|Babek    | Location1MeetingPolicy        | False   |

Daniela pode assumir o controle da janela ou área de trabalho compartilhada para outros participantes em uma reunião organizados por Babek enquanto Babek não é possível passar o controle para outros participantes.

### <a name="allow-an-external-participant-to-give-or-request-control"></a>Permitir que um participante externo dar ou solicitar o controle

Esta é uma diretiva por usuário. Esta configuração controla se os participantes externos em uma reunião podem assumir o controle da sua área de trabalho compartilhada ou a janela para outros participantes da reunião. Os participantes externos em reuniões de equipes podem ser categorizados da seguinte maneira:  

   - Usuário anônimo
   - Usuários convidados  
   - Usuário B2B
   - Usuário federado  

Se os usuários federados podem conceder controle a usuários externos durante o compartilhamento é controlada pela configuração de **Permitir que um participante externo dar ou solicitar o controle** em suas organizações.

### <a name="allow-powerpoint-sharing"></a>Permitir o compartilhamento do PowerPoint

Esta é uma diretiva por usuário. Esta configuração controla se o usuário pode compartilhar apresentações de slide do PowerPoint em uma reunião. Usuários externos, inclusive usuários anônimos, convidados e federados, herdam a política do organizador da reunião.

Vamos examinar o exemplo a seguir.

|Usuário |Política de reunião  |Permitir o compartilhamento do PowerPoint |
|---------|---------|---------|
|Daniela   | Global   | True       |
|Amanda   | Location1MeetingPolicy        | False   |

Amanda não pode compartilhar apresentações de slide do PowerPoint em reuniões, mesmo se ele for o organizador da reunião. Daniela podem compartilhar apresentações de slide do PowerPoint, mesmo se a reunião está organizada por Amanda. Amanda pode exibir as apresentações de slide do PowerPoint compartilhadas por outras pessoas na reunião, mesmo que ela não é possível compartilhar apresentações de slide do PowerPoint.

### <a name="allow-whiteboard"></a>Permitir que o quadro de comunicações

Esta é uma diretiva por usuário. Esta configuração controla se um usuário pode compartilhar o quadro de comunicações em uma reunião. Usuários externos, incluindo anônimos, usuários federados e B2B herdam a política do organizador da reunião. 

Vamos examinar o exemplo a seguir.

|Usuário |Política de reunião  |Permitir que o quadro de comunicações|
|---------|---------|---------|
|Daniela   | Global   | True       |
|Amanda   | Location1MeetingPolicy        | False   |

Amanda não pode compartilhar o quadro de comunicações em uma reunião, mesmo se ele for o organizador da reunião. Daniela podem compartilhar o quadro de comunicações, mesmo se uma reunião é organizada por Amanda.  

### <a name="allow-shared-notes"></a>Permitir anotações compartilhadas

Esta é uma diretiva por usuário. Esta configuração controla se um usuário pode criar e compartilhar anotações em uma reunião. Usuários externos, incluindo anônimos, usuários federados e B2B herdam a política do organizador da reunião. Guia **Notas da reunião** está atualmente somente com suporte em reuniões com menos de 20 participantes. 

Vamos examinar o exemplo a seguir.

|Usuário |Política de reunião  |Permitir anotações compartilhadas |
|---------|---------|---------|
|Daniela   | Global   | True       |
|Amanda   | Location1MeetingPolicy | False |

Daniela pode fazer anotações em reuniões de Amanda e Amanda não é possível fazer anotações em qualquer reuniões.

### <a name="allow-chat-in-meetings-coming-soon"></a>Permitir bate-papo em reuniões (em breve)

Esta é uma política por organizador. Esta configuração controla se o bate-papo de reunião é permitida em reunião do usuário. 

<a name="bkparticipantsandguests"> </a>

## <a name="meeting-policy-settings---participants--guests"></a>Configurações de política de reunião - convidados de & participantes

Estas configurações controlam quais os participantes da reunião aguardar no lobby antes que eles são admitidos para a reunião e o nível de participação, elas são permitidas em uma reunião.

- [Automaticamente admitir pessoas](#automatically-admit-people)
- [Permitir que os usuários anônimos iniciar uma reunião](#allow-anonymous-people-to-start-a-meeting)
- [Permitir que usuários de discagem ignoram o lobby](#allow-dial-in-users-to-bypass-the-lobby-coming-soon)
- [Permitir que os organizadores substituir as configurações de lobby](#allow-organizers-to-override-lobby-settings-coming-soon)

### <a name="automatically-admit-people"></a>Automaticamente admitir pessoas

Esta é uma política por organizador. Essa configuração controla se as pessoas a ingressar em uma reunião diretamente ou aguardar no lobby até que eles são admitidos por um usuário autenticado.

![Reunião de políticas-lobby.png](media/meeting-policies-lobby.png)

 Organizadores de reunião podem clicar em **Opções de reunião** no convite da reunião para alterar essa configuração para cada reunião que agendarem a eles. **(em breve)**
  
|Valor da configuração  |Comportamento de ingressar |
|---------|---------|
|**Todos**   |Todos os participantes ingressem na reunião diretamente, sem aguardar no lobby. Isso inclui pessoas que discam por telefone, os usuários federados, convidados, usuários anônimos e usuários autenticados.       |
|**Todas as pessoas da sua organização e organizações federadas**     |Usuários autenticados dentro da organização, inclusive usuários convidados e os usuários de organizações federadas, ingressem na reunião diretamente, sem aguardar no lobby.  Usuários anônimos e usuários que discam por telefone aguardam no lobby.   |
|**Todos em sua organização**    |Usuários autenticados do dentro da organização, incluindo usuários convidados, ingressem na reunião diretamente, sem aguardar no lobby.  Os usuários federados, usuários anônimos e usuários que discam por telefone aguardam no lobby.           |

### <a name="allow-anonymous-people-to-start-a-meeting"></a>Permitir que os usuários anônimos iniciar uma reunião

Esta é uma política por organizador. Esta configuração controla se pessoas anônimas, incluindo B2B e usuários federados, podem ingressar em reunião do usuário sem um usuário autenticado da organização na presença. 

![reunião-políticas-anônimo-usuário-lobby.png](media/meeting-policies-anonymous-user-lobby.png)

Aqui está o comportamento de ingresso de pessoas anônimos quando os usuários autenticados estão presentes na reunião.

|Permitir que os usuários anônimos iniciar uma reunião  |Automaticamente admitir pessoas |Ingressar o comportamento de pessoas anônimos |
|---------|---------|---------|
|True    | Todos      | Ingressar diretamente         |
|   | Todos em sua organização       | Aguardar no lobby        |
|   | Todas as pessoas da sua organização e organizações federadas       | Aguardar no lobby         |
|False    | Todos        | Ingressar diretamente        |
|   | Todos em sua organização     | Aguardar no lobby        |
|   | Todas as pessoas da sua organização e organizações federadas      | Aguardar no lobby         |

Aqui está o comportamento de ingresso de pessoas anônimos quando nenhum usuário autenticado estiverem presente na reunião.

|Permitir que os usuários anônimos iniciar uma reunião |Automaticamente admitir pessoas  |Ingressar o comportamento de pessoas anônimos |
|---------|---------|---------|
|True    | Todos      | Ingressar diretamente         |
|   | Todos em sua organização       | Aguardar no lobby        |
|   | Todas as pessoas da sua organização e organizações federadas       | Aguardar no lobby         |
|False    | Todos        | Aguarde no lobby. Os usuários são admitidos automaticamente quando o usuário autenticado primeiro participa da reunião.        |
|   | Todos em sua organização     |Aguardar no lobby         |
|   | Todas as pessoas da sua organização e organizações federadas      | Aguardar no lobby         |

### <a name="allow-dial-in-users-to-bypass-the-lobby-coming-soon"></a>Permitir que usuários de discagem ignoram o lobby (em breve)

Esta é uma política por organizador. Essa configuração controla se as pessoas que disquem pelo telefone ingressem na reunião diretamente ou aguardam no lobby, independentemente da configuração **automaticamente admitir pessoas** .

Aqui está o comportamento de ingresso de pessoas que disquem pelo telefone.

|Permitir que usuários de discagem ignoram o lobby  |Admitir automaticamente aos usuários  |Comportamento de pessoas que discam de ingressar |
|---------|---------|---------|
|True    | Todos      | Ingressar diretamente         |
|   | Todos em sua organização       | Ingressar diretamente        |
|   | Todas as pessoas da sua organização e organizações federadas       | Ingressar diretamente         |
|False    | Todos        | Ingressar diretamente        |
|   | Todos em sua organização     |Aguardar no lobby         |
|   | Todas as pessoas da sua organização e organizações federadas      | Aguardar no lobby         |

### <a name="allow-organizers-to-override-lobby-settings-coming-soon"></a>Permitir que os organizadores substituir as configurações de lobby (em breve)

Esta é uma política por organizador. Esta configuração controla se o organizador da reunião pode substituir as configurações de lobby que um administrador defina em **automaticamente admitir pessoas** e **Permitir que usuários de discagem ignoram o lobby** quando eles agendam uma nova reunião. 

Organizadores de reunião podem clicar em **Opções de reunião** no convite da reunião para alterar as configurações de lobby para cada reunião que agendarem a eles. 

Aqui está como essa configuração afeta se o organizador da reunião pode alterar a configuração **automaticamente admitir pessoas** para cada as agendas do organizador da reunião.

|Permitir que os organizadores substituir as configurações de lobby  |Automaticamente admitir pessoas  |Comportamento |
|---------|---------|---------|
|True    | Todos      | Organizador pode alterar a configuração para qualquer outro valor. |
|   | Todos em sua organização       | Organizador pode alterar a configuração para qualquer outro valor.|
|   | Todas as pessoas da sua organização e organizações federadas       | Organizador pode alterar isso para qualquer outro valor.         |
|False    | Todos        | Organizador pode alterar a configuração para qualquer outro valor.|
|   | Todos em sua organização     |Organizador pode alterar a configuração para **todos em sua organização**. |
|   | Todas as pessoas da sua organização e organizações federadas      | Organizador não pode substituir a configuração de lobby. |

Aqui está como esta configuração afeta se o organizador da reunião pode alterar a configuração **Permitir que usuários de discagem para ignoram o lobby** para cada as agendas do organizador da reunião.
    
|Permitir que os organizadores substituir as configurações de lobby  |Permitir que usuários de discagem ignoram o lobby  |Comportamento |
|---------|---------|---------|
|True    |  True        | Organizador pode alterar a configuração como False.       |
|True      | False         | Organizador pode alterar a configuração como True.        |
|False     | True        |Organizador pode alterar a configuração como False.         |
|False      |False          |Organizador não pode substituir a configuração de lobby e não pode permitir que usuários de discagem ignoram o lobby da reunião.        |

[Artigo completo](meeting-policies-in-teams.md)

## <a name="related-topics"></a>Tópicos relacionados
[Políticas de mensagens em equipes](messaging-policies-in-teams.md)
