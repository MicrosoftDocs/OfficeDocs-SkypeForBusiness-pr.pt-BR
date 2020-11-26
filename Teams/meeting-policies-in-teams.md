---
title: Gerenciar políticas de reunião
author: tonysmit
ms.author: tonysmit
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: sonua, shalenc
audience: admin
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
- m365initiative-meetings
appliesto:
- Microsoft Teams
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.meetingpolicies.overview
- ms.teamsadmincenter.meetingpolicies.audioandvideo
- ms.teamsadmincenter.meetingpolicies.contentsharing
- ms.teamsadmincenter.meetingpolicies.general
- ms.teamsadmincenter.meetingpolicies.participantandguests
- seo-marvel-apr2020
description: Saiba como gerenciar as configurações de política de reunião no Teams e usá-las para controlar os recursos disponíveis para os participantes da reunião para reuniões agendadas pelos usuários.
ms.openlocfilehash: 8d701f32cbaf133b03573394d48772b12488b8fe
ms.sourcegitcommit: eaab12a7a760f8a197632e1d28773728b5d1dcef
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/26/2020
ms.locfileid: "49429392"
---
# <a name="manage-meeting-policies-in-teams"></a>Gerenciar políticas de reunião no Teams

::: zone target="docs"
As políticas de reunião são usadas para controlar os recursos disponibilizados para os participantes de reuniões programadas pelos usuários de sua organização. Você pode usar a política global (padrão para toda a organização) que é automaticamente criada ou criada e atribuir políticas personalizadas. Você gerencia políticas de reunião no centro de administração do Microsoft Teams ou usando o [PowerShell](teams-powershell-overview.md).

> [!NOTE]
> Para obter informações sobre como usar funções para gerenciar as permissões de apresentadores e participantes da reunião, consulte [funções em uma reunião do teams](https://support.microsoft.com/office/roles-in-a-teams-meeting-c16fa7d0-1666-4dde-8686-0a0bfe16e019?ui=en-us&rs=en-us&ad=us).

Você pode implementar políticas das seguintes maneiras, que afetam a experiência de reunião para os usuários antes de iniciar uma reunião, durante uma reunião ou após uma reunião.

|Tipo de implementação  |Descrição  |
|---------|---------|
|Por organizador    |Quando você implementa uma política por organizador, todos os participantes da reunião herdam a política do organizador. Por exemplo, **admitir pessoas automaticamente** é uma política por organizador e controla se os usuários ingressam na reunião diretamente ou esperam no lobby para reuniões agendadas pelo usuário ao qual a política é atribuída.          |
|Por usuário    |Quando você implementa uma política por usuário, somente a política por usuário se aplica para restringir determinados recursos para o organizador e/ou participantes da reunião. Por exemplo, **permitir reunir agora em canais** é uma política por usuário.     |
|Por organização e por usuário     |Quando você implementa uma combinação de uma política por organização e por usuário, certos recursos são restritos para participantes da reunião com base em sua política e na política do organizador. Por exemplo, **permitir gravação na nuvem** é uma política por organização e por usuário. Ative essa configuração para permitir que o organizador da reunião e os participantes iniciem e parem de gravar.

Você pode editar as configurações na política global ou criar e atribuir uma ou mais políticas personalizadas. Os usuários receberão a política global, a menos que você crie e atribua uma política personalizada.

> [!NOTE]
> O botão detalhes da reunião estará disponível se um usuário tiver as licenças de conferência de áudio habilitadas ou o usuário for permitido para a conferência de áudio, caso contrário, os detalhes da reunião não estarão disponíveis.

## <a name="create-a-custom-meeting-policy"></a>Criar uma política de reunião personalizada

1. Na navegação à esquerda do centro de administração do Microsoft Teams, vá para políticas de reunião de **reuniões**  >  **Meeting policies**.
2. Selecione **Adicionar**.
3. Insira um nome e uma descrição para a política. O nome não pode conter caracteres especiais ou ter mais de 64 caracteres.
4. Escolha as configurações desejadas.
5. Selecione **salvar**.

Por exemplo, digamos que você tenha um grupo de usuários e queira limitar a quantidade de largura de banda que a reunião exigiria. Você criaria uma nova política personalizada chamada "Largura de banda limitada" e desativaria as seguintes configurações:

Em **Áudio e vídeo**:

- Desative a opção Permitir gravação na nuvem.
- Desative a opção Permitir vídeo IP.

Em **Compartilhamento de conteúdo**:

- Desative o modo de compartilhamento de tela.
- Desative a opção Permitir quadro de comunicações.
- Desative a opção Permitir anotações compartilhadas.

Em seguida, atribua a política aos usuários.

## <a name="edit-a-meeting-policy"></a>Editar uma política de reunião

Você pode editar a política global e qualquer política personalizada que criar.

1. Na navegação à esquerda do centro de administração do Microsoft Teams, vá para políticas de reunião de **reuniões**  >  **Meeting policies**.
2. Selecione a política clicando à esquerda do nome da política e, em seguida, selecione **Editar**.
3. Aqui, faça as alterações desejadas.
4. Selecione **salvar**.

> [!NOTE]
> Somente uma política de reunião pode ser atribuída a um usuário de cada vez.

## <a name="assign-a-meeting-policy-to-users"></a>Atribuir uma política de reunião aos usuários

[!INCLUDE [assign-policy](includes/assign-policy.md)]

> [!NOTE]
> Você não pode excluir uma política se usuários estiverem atribuídos a ela. Primeiro, você deve atribuir uma política diferente a todos os usuários afetados. em seguida, é possível excluir a política original.

## <a name="meeting-policy-settings"></a>Configurações da política de reunião

Ao selecionar uma política existente na página **políticas de reunião** ou selecionar **Adicionar** para adicionar uma nova política, você pode definir as configurações para o seguinte.

- [Geral](#meeting-policy-settings---general)
- [Áudio & vídeo](#meeting-policy-settings---audio--video)
- [Compartilhamento de conteúdo](#meeting-policy-settings---content-sharing)
- [Participantes & convidados](#meeting-policy-settings---participants--guests)

::: zone-end

<a name="bkgeneral"> </a>

## <a name="meeting-policy-settings---general"></a>Configurações da política de reunião-geral

- [Permitir reunir agora em canais](#allow-meet-now-in-channels)
- [Permitir o suplemento do Outlook](#allow-the-outlook-add-in)
- [Permitir agendamento de reunião de canal](#allow-channel-meeting-scheduling)
- [Permitir agendamento de reuniões particulares](#allow-scheduling-private-meetings)
- [Permitir reunião agora em reuniões privadas](#allow-meet-now-in-private-meetings)

### <a name="allow-meet-now-in-channels"></a>Permitir reunir agora em canais

Permitir reunião **agora** é uma política por usuário e se aplica antes de iniciar uma reunião. Esta configuração controla se um usuário pode iniciar uma reunião não planejada em um canal do teams. Se você ativar esta configuração, os usuários poderão selecionar o botão **reunir** para iniciar uma reunião não planejada ou agendar uma reunião no canal. O valor padrão é True.

![Captura de tela mostrando o ícone reunir agora abaixo de uma mensagem](media/meeting-policies-meet-now.png) 

### <a name="allow-the-outlook-add-in"></a>Permitir o suplemento do Outlook

Esta é uma política por usuário e se aplica antes de iniciar uma reunião. Esta configuração controla se as reuniões de equipes podem ser agendadas dentro do Outlook (Windows, Mac, Web e celular).

![Captura de tela mostrando a capacidade de agendar uma nova reunião](media/meeting-policies-outlook-add-in.png)

Se você desativar essa opção, os usuários não poderão agendar. Reuniões do teams quando elas criam uma nova reunião no Outlook. Por exemplo, no Outlook no Windows, a **nova opção de reunião do teams** não aparece na faixa de opções.

### <a name="allow-channel-meeting-scheduling"></a>Permitir agendamento de reunião de canal

Use a política AllowChannelMeetingScheduling existente para controlar os tipos de eventos que podem ser criados nos calendários do canal de equipe. Esta é uma política por usuário e se aplica antes de iniciar uma reunião. Esta configuração controla se os usuários podem agendar uma reunião em um canal do teams. Por padrão, essa configuração está ativada.

Se essa política estiver desativada, os usuários não poderão criar novas reuniões de canal. No entanto, as reuniões de canais existentes podem ser editadas pelo organizador do evento.

Agendar uma reunião será desabilitada.

 ![Captura de tela mostrando a opção agendar uma reunião no Teams](media/schedule-meeting-option.png)

A seleção de canal está desabilitada.

![a opção de calendário para selecionar um canal no qual você deseja agendar uma reunião.](media/meeting-policies-select-a-channel-to-meet-in.png)

Na página Postagens de canal, os seguintes recursos serão desabilitados:

- Botão **agendar uma reunião** na caixa de texto responder ao canal.
  ![botão agendar uma reunião responder caixa de texto](media/schedule-meeting-disabled-in-chat2.png)
  
- Botão **agendar uma reunião** no cabeçalho do canal.
  ![botão agendar uma reunião no cabeçalho do canal](media/schedule-now-in-header.png)

No calendário do canal:

- Botão **Adicionar novo evento** no cabeçalho do calendário do canal será desabilitado.
  ![botão no cabeçalho de calendário do canal desabilitado](media/add-new-event-disabled.png)

- Os usuários não poderão arrastar e selecionar um bloco de tempo no calendário do canal para criar uma reunião de canal.

- Os usuários não podem usar atalhos de teclado para criar uma reunião no calendário do canal.

No centro de administração:

O aplicativo de calendário do canal será exibido na seção **aplicativos da Microsoft** na página de políticas de permissão do aplicativo.

 ![a política de permissões do aplicativo no centro de administração do teams](media/manage-microsoft-apps-policy.png)

### <a name="allow-scheduling-private-meetings"></a>Permitir agendamento de reuniões particulares

Esta é uma política por usuário e se aplica antes de iniciar uma reunião. Esta configuração controla se os usuários podem agendar reuniões privadas no Teams. Uma reunião é particular quando não é publicada em um canal de uma equipe.

Observe que, se você desativar a opção **permitir reuniões privadas de agendamento** e **permitir agendamento de reunião de canal**, a opção **Adicionar participantes necessários** e **Adicionar canal** estará desabilitada para os usuários do teams. Por padrão, essa configuração está ativada.

### <a name="allow-meet-now-in-private-meetings"></a>Permitir reunião agora em reuniões privadas

Esta é uma política por usuário e se aplica antes de iniciar uma reunião. Esta configuração controla se um usuário pode iniciar uma reunião privada não planejada.  Por padrão, essa configuração está ativada.

<a name="bkaudioandvideo"> </a>

## <a name="meeting-policy-settings---audio--video"></a>Configurações da política de reunião-áudio & vídeo

- [Permitir transcrição](#allow-transcription)
- [Permitir gravação na nuvem](#allow-cloud-recording)
- [Modo para áudio IP](#mode-for-ip-audio)
- [Modo para vídeo de IP](#mode-for-ip-video)
- [Permitir vídeo IP](#allow-ip-video)
- [Taxa de bits de mídia (KBS)](#media-bit-rate-kbs)

### <a name="allow-transcription"></a>Permitir transcrição

Trata-se de uma combinação de uma política por organização e por usuário. Esta configuração controla se as legendas e os recursos de transcrição estão disponíveis durante a reprodução de gravações de reunião. Se você desativar essa opção, as opções de **pesquisa** e **CC** não estarão disponíveis durante a reprodução de uma gravação de reunião. A pessoa que iniciou a gravação precisa desta configuração ativada para que a gravação também inclua transcrição.

Observe que a transcrição para reuniões gravadas no momento só tem suporte para os usuários que têm o idioma no Microsoft Teams definido como Inglês e quando o inglês está falado na reunião.

![as opções de transcrição em uma reunião](media/meeting-policies-transcription.png)

### <a name="allow-cloud-recording"></a>Permitir gravação na nuvem

Trata-se de uma combinação de uma política por organização e por usuário. Esta configuração controla se as reuniões deste usuário podem ser registradas. A gravação pode ser iniciada pelo organizador da reunião ou por outro participante da reunião se a configuração de política estiver ativada para o participante e se for um usuário autenticado da mesma organização.

Pessoas de fora da sua organização, como usuários federados e anônimos, não podem iniciar a gravação. Os usuários convidados não podem iniciar ou parar a gravação.

![as opções de gravação](media/meeting-policies-recording.png)

Vamos dar uma olhada no exemplo a seguir.

|Usuário |Políticas de reunião  |Permitir gravação na nuvem |
|---------|---------|---------|
|Daniela | Global   | Desativado |
|Amanda | Location1MeetingPolicy | Ativado|
|John (usuário externo) | Não aplicável | Não aplicável|

Reuniões organizadas por Daniela não podem ser gravadas e Amanda, que tem a configuração de política habilitada, não pode gravar reuniões organizadas por Daniela. Reuniões organizadas por Amanda podem ser registradas, no entanto, Daniela, que têm a configuração de política desabilitada e John, que é um usuário externo, não pode gravar reuniões organizadas por Amanda.

Para saber mais sobre a gravação de reunião em nuvem, consulte [gravação de reunião na nuvem do teams](cloud-recording.md).

### <a name="mode-for-ip-audio"></a>Modo para áudio IP

Esta é uma política por usuário. Essa configuração controla se o áudio pode ser ativado em reuniões e chamadas em grupo. Estes são os valores para essa configuração.

|Valor de configuração |Comportamento  |
|---------|---------|
|**Áudio de saída e entrada habilitado**    |O áudio de saída e de entrada é permitido na reunião. Esta é a configuração padrão. |
|**Desabilitado**     |O áudio de saída e de entrada está desativado na reunião.     |

Se definido como **desabilitado** para um usuário, esse usuário ainda poderá agendar e organizar reuniões, mas não poderá usar áudio. Para ingressar em uma reunião, ela precisa discar por meio da rede telefônica pública comutada (PSTN) ou fazer com que a reunião seja chamada e unida por telefone. Os participantes da reunião que não têm políticas atribuídas (por exemplo, participantes anônimos) têm isto definido como **áudio de saída e entrada habilitado** por padrão. Em clientes móveis do Microsoft Teams, se essa configuração estiver desabilitada, o usuário terá de discar para a reunião por meio da PSTN.

Esta configuração não se aplica a chamadas do 1:1. Para restringir chamadas do 1:1, configure uma [política de chamada](teams-calling-policy.md) de equipes e desative a configuração **fazer chamadas privadas** . Essa configuração também não se aplica a dispositivos da sala de conferência, como dispositivos de Surface Hub e salas do Microsoft Teams.

Essa configuração ainda não está disponível para ambientes da Comunidade do Microsoft 365 governo Community Cloud (GCC), GCC High ou Department of Defense (DoD).

Para saber mais, consulte [gerenciar áudio/vídeo para participantes da reunião](#manage-audiovideo-for-meeting-participants).

### <a name="mode-for-ip-video"></a>Modo para vídeo de IP

Esta é uma política por usuário. Esta configuração controla se o vídeo pode ser ativado em reuniões e chamadas em grupo. Estes são os valores para essa configuração.

|Valor de configuração |Comportamento  |
|---------|---------|
|**Vídeo de saída e de entrada habilitado**    | O vídeo de saída e de entrada é permitido na reunião. Esta é a configuração padrão. |
|**Desabilitado**     | O vídeo de saída e de entrada está desativado na reunião. Em clientes móveis do Teams, os usuários não podem compartilhar vídeos ou fotos na reunião. <br><br>Observe que se o **modo de áudio IP** estiver desabilitado, o **modo de vídeo IP** também permanecerá desabilitado.  |

Se definido como **desabilitado** para um usuário, esse usuário não poderá ativar o vídeo ou exibir vídeos compartilhados por outros participantes da reunião. Os participantes da reunião que não têm políticas atribuídas (por exemplo, participantes anônimos) têm isto definido como **vídeo de saída e de entrada habilitado** por padrão.

Essa configuração não se aplica a dispositivos da sala de conferência, como dispositivos de Surface Hub e salas do Microsoft Teams.

Essa configuração ainda não está disponível para ambientes da Comunidade do Microsoft 365 governo Community Cloud (GCC), GCC High ou Department of Defense (DoD).

> [!NOTE]
> Lembre-se de que essa configuração controla o vídeo de saída e de entrada, enquanto a configuração permitir vídeo de **IP** controla o vídeo de saída. Para saber mais, confira [qual configuração de política de vídeo IP tem precedência?](#which-ip-video-policy-setting-takes-precedence) e [gerenciar áudio/vídeo para participantes da reunião](#manage-audiovideo-for-meeting-participants).

Para saber mais, consulte [gerenciar áudio/vídeo para participantes da reunião](#manage-audiovideo-for-meeting-participants).

### <a name="allow-ip-video"></a>Permitir vídeo IP

Trata-se de uma combinação de uma política por organização e por usuário. Vídeo é um componente importante para reuniões. Em algumas organizações, os administradores podem querer ter mais controle sobre quais reuniões de usuários têm vídeo. Esta configuração controla se o vídeo pode ser ativado em reuniões hospedadas por um usuário e no 1:1 e chamadas em grupo iniciadas por um usuário. Em clientes móveis do Microsoft Teams, essa configuração controla se os usuários podem compartilhar fotos e vídeos em uma reunião.

Reuniões organizadas por um usuário que tem essa configuração de política habilitada, permitir o compartilhamento de vídeo na reunião pelos participantes da reunião, se os participantes também tiverem a configuração de política habilitada. Os participantes da reunião que não têm políticas atribuídas (por exemplo, participantes anônimos e federados) herdam a política do organizador da reunião.

> [!NOTE]
> Lembre-se de que essa configuração controla o vídeo de saída, enquanto o **modo de configuração de vídeo IP** controla o vídeo de saída e de entrada. Para saber mais, confira [qual configuração de política de vídeo IP tem precedência?](#which-ip-video-policy-setting-takes-precedence) e [gerenciar áudio/vídeo para participantes da reunião](#manage-audiovideo-for-meeting-participants).

| Cliente de equipe e desktop da equipe |Cliente móvel do teams  |
|:-------:|:-------:|
|![Captura de tela mostrando Associação de reunião com as configurações de áudio/vídeo na área de trabalho](media/meeting-policies-audio-video-settings.png)    |![Captura de tela mostrando a reunião ingressar sreen com as configurações de áudio/vídeo em dispositivos móveis](media/meeting-policies-mobile-join.png)          |

Vamos dar uma olhada no exemplo a seguir.

|Usuário |Políticas de reunião  |Permitir vídeo IP |
|---------|---------|---------|
|Daniela   | Global   | Ativado       |
|Amanda    | Location1MeetingPolicy        | Desativado      |

Reuniões hospedadas pela Daniela permitem que o vídeo seja ativado. Daniela pode ingressar na reunião e ativar o vídeo. O Amanda não pode ativar o vídeo na reunião do Daniela porque a política de Amanda está definida como não permitir vídeo. Amanda pode ver vídeos compartilhados por outros participantes da reunião.

Em reuniões hospedadas pela Amanda, ninguém pode ativar o vídeo, independentemente da política de vídeo atribuída a ele. Isso significa que o Daniela não pode ativar o vídeo nas reuniões do Amanda.  

Se Daniela chama Amanda com vídeo ativado, o Amanda pode atender a chamada somente com áudio.  Quando a chamada estiver conectada, Amanda poderá ver o vídeo do Daniela, mas não poderá ativar o vídeo. Se o Amanda chama Daniela, Daniela pode atender a chamada com vídeo e áudio. Quando a chamada estiver conectada, o Daniela poderá ativar ou desativar o vídeo, conforme necessário.

Para saber mais, consulte [gerenciar áudio/vídeo para participantes da reunião](#manage-audiovideo-for-meeting-participants).

#### <a name="which-ip-video-policy-setting-takes-precedence"></a>Qual configuração de política de vídeo IP tem prioridade

Para um usuário, a configuração de política mais restritiva para o vídeo tem prioridade. Veja alguns exemplos.

|Permitir vídeo IP|Modo para vídeo de IP|Experiência de reunião|
|---------|---------|---------|
|Organizador: **ativado**<br><br>Participante: **ativado** |Participante: **desabilitado**        |O **modo de configuração de vídeo IP** tem precedência. O participante atribuído a essa política não pode ativar ou exibir vídeos compartilhados por outras pessoas.|
|Organizador: **ativado**<br><br>Participante: **ativado** |Participante: **vídeo de saída e de entrada habilitado**          |O participante atribuído a essa política pode ativar ou exibir vídeos compartilhados por outras pessoas.         |
|Organizador: **ativado**<br><br>Participante: **desativado** |Participante: **vídeo de saída e de entrada habilitado**         |A configuração **permitir vídeo IP** tem prioridade. Os participantes só poderão ver o vídeo recebido e não poderão enviar vídeo de saída.         |
|Organizador: **ativado**<br><br>Participante: **desativado** |Participante: **desabilitado**         |O **modo de configuração de vídeo IP** tem precedência. O participante não pode ver o vídeo de entrada ou de saída.|
|Organizador: **desativado**    |       |A configuração **permitir vídeo IP** tem prioridade porque está desativada para o organizador. Ninguém pode ativar o vídeo em reuniões organizadas pelo usuário que está atribuído a essa política.         |

### <a name="manage-audiovideo-for-meeting-participants"></a>Gerenciar áudio/vídeo para participantes da reunião

|Se quiser...  |Definir as seguintes configurações de política  |
|---------|---------|
|Desabilitar áudio e vídeo para participantes em reuniões  |Modo para áudio IP: **desabilitado**<br> Modo para vídeo IP: **desabilitado**<br>Permitir vídeo de IP: N/d       |
|Habilitar somente vídeo e áudio de entrada para participantes em reuniões  |Modo para áudio IP: **áudio de saída e entrada habilitado**<br> Modo para vídeo de IP: **vídeo de saída e de entrada habilitado**<br>Permitir vídeo IP: **desativado**       |
|Desabilitar vídeo para participantes em reuniões (os participantes têm somente áudio)|  Modo para áudio IP: **habilitar áudio de saída e de entrada**<br> Modo para vídeo IP: **desabilitado**<br>Permitir vídeo de IP: N/d
|Habilitar áudio e vídeo para participantes em reuniões    |Modo para áudio IP: **áudio de saída e entrada ativado** (padrão)<br> Modo para vídeo de IP: **vídeo de saída e entrada habilitado** (padrão)<br>Permitir vídeo por IP: **ativado** (padrão)    |

A política mais restritiva entre a política do organizador da reunião e a política do usuário se aplica. Por exemplo, se um organizador tiver uma política que restrinja o vídeo e a política de um usuário não restringir o vídeo, os participantes da reunião herdarão a política do organizador da reunião e não terão acesso ao vídeo em reuniões. Isso significa que eles podem participar da reunião somente com áudio.

> [!NOTE]
> Quando um usuário iniciar uma chamada em grupo para ingressar por telefone, a tela **usar telefone para áudio** não será exibida. Esse é um problema conhecido que estamos trabalhando para resolver. Para contornar esse problema, selecione **áudio telefônico** em **outras opções de junção**.  

#### <a name="teams-mobile-clients"></a>Clientes móveis do Microsoft Teams

Para os usuários de clientes móveis do Microsoft Teams, a capacidade de compartilhar fotos e vídeos durante uma reunião também é determinada pela configuração de **modo** **permitir vídeo** ou vídeo IP. Dependendo de qual configuração de política tem precedência, a capacidade de compartilhar vídeos e fotos não estará disponível. Isso não afeta o compartilhamento de tela, que você configura usando uma configuração de [modo de compartilhamento de tela](#screen-sharing-mode) separada. Além disso, você pode definir uma [política de mobilidade do teams](https://docs.microsoft.com/powershell/module/skype/new-csteamsmobilitypolicy) para impedir que os usuários móveis usem o vídeo IP por meio de uma conexão de celular, o que significa que elas devem usar uma conexão WiFi.

### <a name="media-bit-rate-kbs"></a>Taxa de bits de mídia (KBS)

Esta é uma política por usuário. Essa configuração determina a taxa de bits de mídia para transmissões de compartilhamento de áudio, vídeo e aplicativos baseados em vídeo em chamadas e reuniões para o usuário. Ela é aplicada à passagem de mídia uplink e de downlink para usuários na chamada ou reunião. Essa configuração lhe dá controle granular sobre o gerenciamento da largura de banda em sua organização. Dependendo dos cenários de reuniões exigidos pelos usuários, recomendamos ter largura de banda suficiente para ter uma boa experiência de qualidade. O valor mínimo é de 30 kbps e o valor máximo depende do cenário da reunião. Para saber mais sobre a largura de banda mínima recomendada para reuniões de boa qualidade, chamadas e eventos dinâmicos no Teams, consulte [requisitos de largura de banda](prepare-network.md#bandwidth-requirements).

Se não houver largura de banda suficiente para uma reunião, os participantes verão uma mensagem indicando uma qualidade de rede ruim.

Para reuniões que precisam de experiência com vídeo de alta qualidade, como reuniões de diretoria e eventos ao vivo do Teams, recomendamos que você defina a largura de banda para 10 Mbps. Mesmo quando a experiência máxima é definida, a pilha de mídia do teams se adapta às condições de baixa largura de banda quando determinadas condições de rede são detectadas, dependendo do cenário.

## <a name="meeting-policy-settings---content-sharing"></a>Configurações da política de reunião – compartilhamento de conteúdo

- [Modo de compartilhamento de tela](#screen-sharing-mode)
- [Permitir que um participante conceda ou solicite o controle](#allow-a-participant-to-give-or-request-control)
- [Permitir que um participante externo conceda ou solicite controle](#allow-an-external-participant-to-give-or-request-control)
- [Permitir compartilhamento do PowerPoint](#allow-powerpoint-sharing)
- [Permitir quadro de comunicações](#allow-whiteboard)
- [Permitir anotações compartilhadas](#allow-shared-notes)

### <a name="screen-sharing-mode"></a>Modo de compartilhamento de tela

> [!Note]
> Esse recurso ainda está em desenvolvimento. O compartilhamento de tela é uma política por participante.

Esta configuração controla se a área de trabalho e/ou o compartilhamento de janela é permitida na reunião do usuário. Os participantes da reunião que não têm políticas atribuídas (por exemplo, participantes anônimos, convidados, B2B e federados) herdam a política do organizador da reunião.

|Valor de configuração |Comportamento  |
|---------|---------|
|**Tela inteira**    | Compartilhamento de área de trabalho e compartilhamento de aplicativos completos são permitidos na reunião |
|**Único aplicativo**   | O compartilhamento de aplicativos é permitido na reunião        |
|**Desabilitado**     |Compartilhamento de tela e compartilhamento de aplicativos desativados na reunião.       |

Vamos dar uma olhada no exemplo a seguir.

|Usuário |Políticas de reunião |Modo de compartilhamento de tela |
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

|Usuário |Políticas de reunião  |Permitir que o participante conceda ou solicite o controle |
|---------|---------|---------|
|Daniela   | Global   | Ativado       |
|Babek    | Location1MeetingPolicy        | Desativado   |

O Daniela pode dar ao controle da área de trabalho compartilhada ou janela para outros participantes de uma reunião organizada por Babek, enquanto o Babek não pode conceder ao controle outros participantes.

Para usar o PowerShell para controlar quem pode conceder controle ou aceitar solicitações de controle, use o cmdlet AllowParticipantGiveRequestControl.

> [!NOTE]
> Para dar e assumir o controle do conteúdo compartilhado durante o compartilhamento, ambas as partes devem usar o cliente da área de trabalho do teams. Não há suporte para controle quando ambas as partes estiverem executando o Teams em um navegador. Isso ocorre devido a uma limitação técnica de que estamos planejando corrigir.

### <a name="allow-an-external-participant-to-give-or-request-control"></a>Permitir que um participante externo conceda ou solicite controle

Esta é uma política por usuário. Não importa se uma organização tem essa definição para um usuário não controla o que os participantes externos podem fazer, independentemente do que o organizador da reunião definiu. Esse parâmetro controla se os participantes externos podem receber controle ou solicitação de controle da tela do participante do compartilhamento, dependendo do que o participante do compartilhamento definiu nas políticas de reunião da organização. Os participantes externos em reuniões de equipes podem ser categorizados da seguinte maneira:  

- Usuário anônimo
- Usuários convidados  
- Usuário B2B
- Usuário federado  

Se os usuários federados podem dar controle aos usuários externos enquanto o compartilhamento é controlado pela configuração **permitir que um participante externo conceda ou solicite o controle** em sua organização.

Para usar o PowerShell para controlar se os participantes externos podem conceder controle ou aceitar solicitações de controle, use o cmdlet AllowExternalParticipantGiveRequestControl.

### <a name="allow-powerpoint-sharing"></a>Permitir compartilhamento do PowerPoint

Esta é uma política por usuário. Esta configuração controla se o usuário pode compartilhar apresentações de slides do PowerPoint em uma reunião. Usuários externos, incluindo usuários anônimos, convidados e federados, herdam a política do organizador da reunião.

Vamos dar uma olhada no exemplo a seguir.

|Usuário |Políticas de reunião  |Permitir compartilhamento do PowerPoint |
|---------|---------|---------|
|Daniela   | Global   | Ativado       |
|Amanda   | Location1MeetingPolicy        | Desativado   |

O Amanda não pode compartilhar apresentações de slides do PowerPoint em reuniões, mesmo que ela seja o organizador da reunião. Daniela pode compartilhar decks de slides do PowerPoint mesmo se a reunião for organizada por Amanda. O Amanda pode exibir os decks de slides do PowerPoint compartilhados por outras pessoas na reunião, mesmo que ele não possa compartilhar os slides do PowerPoint.

### <a name="allow-whiteboard"></a>Permitir quadro de comunicações

Esta é uma política por usuário. Esta configuração controla se um usuário pode compartilhar o quadro de comunicações em uma reunião. Usuários externos, incluindo usuários anônimos, B2B e federados, herdam a política do organizador da reunião.

Vamos dar uma olhada no exemplo a seguir.

|Usuário |Políticas de reunião  |Permitir quadro de comunicações|
|---------|---------|---------|
|Daniela   | Global   | Ativado       |
|Amanda   | Location1MeetingPolicy        | Desativado   |

O Amanda não pode compartilhar o quadro de comunicações em uma reunião, mesmo que ela seja o organizador da reunião. Daniela pode compartilhar o quadro de comunicações mesmo se uma reunião for organizada por Amanda.  

### <a name="allow-shared-notes"></a>Permitir anotações compartilhadas

Esta é uma política por usuário. Esta configuração controla se um usuário pode criar e compartilhar anotações em uma reunião. Usuários externos, incluindo usuários anônimos, B2B e federados, herdam a política do organizador da reunião. No momento, a guia **anotações da reunião** tem suporte apenas em reuniões com menos de 20 participantes.

Vamos dar uma olhada no exemplo a seguir.

|Usuário |Políticas de reunião  |Permitir anotações compartilhadas |
|---------|---------|---------|
|Daniela   | Global   | Ativado       |
|Amanda   | Location1MeetingPolicy | Desativado |

Daniela pode fazer anotações nas reuniões do Amanda, e o Amanda não pode fazer anotações em nenhuma reunião.

## <a name="meeting-policy-settings---participants--guests"></a>Configurações de política de reunião-participantes & convidados

Essas configurações controlam quais participantes da reunião aguardam no lobby antes de serem admitidos para a reunião e o nível de participação que eles são permitidos em uma reunião.

- [Permitir que as pessoas anônimas iniciem uma reunião](#let-anonymous-people-start-a-meeting)
- [Admitir pessoas automaticamente](#automatically-admit-people)
- [Permitir que os usuários de discagem ignorem o lobby](#allow-dial-in-users-to-bypass-the-lobby)
- [Habilitar legendas dinâmicas](#enable-live-captions)
- [Permitir chat em reuniões](#allow-chat-in-meetings)

> [!NOTE]
>As opções para ingressar em uma reunião irão variar, dependendo das configurações de cada grupo de equipe e do método de conexão. Se o seu grupo tiver uma videoconferência e usar-a para se conectar, consulte [videoconferências](https://docs.microsoft.com/microsoftteams/audio-conferencing-in-office-365). Se o grupo Teams não tiver uma videoconferência, consulte [ingressar em uma reunião no Teams](https://support.office.com/article/join-a-meeting-in-teams-1613bb53-f3fa-431e-85a9-d6a91e3468c9).

### <a name="let-anonymous-people-start-a-meeting"></a>Permitir que as pessoas anônimas iniciem uma reunião

Trata-se de uma política de um organizador que permite reuniões de conferência discada com preenchimento de discagem. Esta configuração controla se os usuários de discagem podem ingressar na reunião sem um usuário autenticado da organização em participação. Por padrão, essa configuração é desativada, o que significa que os usuários de discagem aguardarão no lobby até que um usuário autenticado da organização ingresse na reunião.

> [!NOTE]
> Se essa configuração estiver desativada e um usuário de discagem ingressar na reunião primeiro e for colocado no lobby, um usuário da organização deverá ingressar na reunião com um cliente do teams para admitir o usuário do lobby. Não há controles de lobby disponíveis para discar em usuários.

### <a name="automatically-admit-people"></a>Admitir pessoas automaticamente

Esta é uma política por organizador. Esta configuração controla se as pessoas ingressam em uma reunião diretamente ou esperam no lobby até serem admitidas por um usuário autenticado. Esta configuração não se aplica a usuários de discagem.

![Captura de tela mostrando uma reunião com um usuário no lobby](media/meeting-policies-lobby.png)

 Os organizadores da reunião podem clicar em **Opções de reunião** no convite da reunião para alterar essa configuração para cada reunião agendada.

> [!NOTE]
> Nas opções de reunião, a configuração é rotulada como "quem pode ignorar o lobby". Se você alterar a configuração padrão de qualquer usuário, ela será aplicada a todas as novas reuniões organizadas por esse usuário e em qualquer reunião anterior em que o usuário não tiver modificado as opções de reunião.
  
|Valor de configuração  |Comportamento da junção |
|---------|---------|
|**Todos**   |Todos os participantes da reunião ingressam na reunião diretamente sem esperar no lobby. Isso inclui usuários autenticados, usuários externos de organizações confiáveis (federadas), convidados e usuários anônimos.     |
|**Todos em sua organização e organizações federadas**     |Usuários autenticados dentro da organização, incluindo usuários convidados e os usuários de organizações confiáveis, ingressam na reunião diretamente sem esperar no lobby.  Usuários anônimos esperam no lobby.   |
|**Todos em sua organização**    |Os usuários autenticados de dentro da organização, incluindo os usuários convidados, ingressam na reunião diretamente sem esperar no lobby.  Os usuários de organizações confiáveis e usuários anônimos esperam no lobby. Esta é a configuração padrão.           |
|**Somente organizador**    |Somente os organizadores da reunião podem ingressar na reunião diretamente sem esperar no lobby. Todos os outros, incluindo usuários autenticados dentro da organização, usuários convidados, usuários de organizações confiáveis e usuários anônimos devem aguardar no lobby.           |

### <a name="allow-dial-in-users-to-bypass-the-lobby"></a>Permitir que os usuários de discagem ignorem o lobby

Esta é uma política por organizador. Esta configuração controla se as pessoas que discam por telefone entram diretamente na reunião ou esperam no lobby, independentemente da configuração de usuário **admitir pessoas automaticamente** . Por padrão, essa configuração está desativada. Quando essa configuração estiver desativada, os usuários de discagem aguardarão no lobby até que o usuário da organização ingresse na reunião com um cliente do Teams e os admite. Quando essa configuração estiver ativada, os usuários de discagem entrarão automaticamente na reunião quando um usuário da organização ingressar na reunião.

> [!NOTE]
> Se um usuário de discagem ingressar em uma reunião antes de um usuário da organização ingressar na reunião, ela será colocada no lobby até que o usuário da organização ingresse na reunião usando um cliente do Team e os admite. Se você alterar a configuração padrão de qualquer usuário, ela será aplicada a todas as novas reuniões organizadas por esse usuário e em qualquer reunião anterior em que o usuário não tiver modificado as opções de reunião.

### <a name="enable-live-captions"></a>Habilitar legendas dinâmicas

Esta é uma política por usuário e aplica-se durante uma reunião. Esta configuração controla se a opção **Ativar legendas dinâmicas** está disponível para o usuário ativar e desativar legendas dinâmicas em reuniões que o usuário participa.  

![Captura de tela mostrando a opção Ativar legendas ao vivo](media/meeting-policies-live-captions.png)

|Valor de configuração |Comportamento  |
|---------|---------|
|**Desabilitado, mas o usuário pode substituir**     | As legendas dinâmicas não são ativadas automaticamente para o usuário durante uma reunião. O usuário vê a opção **Ativar legendas ao vivo** no menu de estouro (**...**) para ativá-las. Esta é a configuração padrão. |
|**Desabilitado**     | As legendas ao vivo são desabilitadas para o usuário durante uma reunião. O usuário não tem a opção de ativá-los.          |

<a name="bkcontentsharing"> </a>

### <a name="allow-chat-in-meetings"></a>Permitir chat em reuniões

Esta é uma configuração por participante. Esta configuração controla se o chat da reunião é permitido na reunião do usuário.

<a name="bkparticipantsandguests"> </a>

## <a name="meeting-policy-settings---designated-presenter-role-mode"></a>Configurações da política da reunião – modo de função do apresentador designado

Esta é uma política por usuário. Essa configuração permite alterar o valor padrão da configuração **quem pode apresentar?** em opções de **reunião** no cliente do teams. Essa configuração de política afeta todas as reuniões, incluindo reunir reuniões agora.

A configuração **quem pode apresentar?** permite que os organizadores da reunião escolham quem pode ser apresentadores em uma reunião. Para saber mais, confira [alterar as configurações de participante de uma reunião](https://support.microsoft.com/article/change-participant-settings-for-a-teams-meeting-53261366-dbd5-45f9-aae9-a70e6354f88e) e funções de equipe [em uma reunião de equipe](https://support.microsoft.com/article/roles-in-a-teams-meeting-c16fa7d0-1666-4dde-8686-0a0bfe16e019).

No momento, você só pode usar o PowerShell para definir essa configuração de política. Você pode editar uma política de reunião do teams existente usando o cmdlet [set-CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy) . Ou crie uma nova política de reunião do teams usando o cmdlet [New-CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csteamsmeetingpolicy) e atribua-a a usuários.

Para especificar o valor padrão da configuração **quem pode apresentar?** no Teams, defina o parâmetro **DesignatedPresenterRoleMode** como um dos seguintes:

- **EveryoneUserOverride**: todos os participantes da reunião podem ser apresentadores. Esse é o valor padrão. Esse parâmetro corresponde à configuração **todos** no Teams.
- **EveryoneInCompanyUserOverride**: os usuários autenticados na organização, incluindo os usuários convidados, podem ser apresentadores. Esse parâmetro corresponde à configuração **pessoas na minha organização** no Teams.
- **OrganizerOnlyUserOverride**: somente o organizador da reunião pode ser um apresentador e todos os participantes da reunião são designados como participantes. Esse parâmetro corresponde à **única configuração eu** do teams.

Lembre-se de que depois de definir o valor padrão, os organizadores da reunião ainda podem alterar essa configuração no Teams e escolher quem pode apresentar nas reuniões agendadas.

## <a name="meeting-policy-settings---meeting-attendance-report"></a>Configurações de política de reunião-relatório de presença de reunião

Esta é uma política por usuário. Esta configuração controla se os organizadores da reunião podem baixar o [relatório de participação da reunião](teams-analytics-and-reports/meeting-attendance-report.md).

No momento, você só pode usar o PowerShell para definir essa configuração de política. Você pode editar uma política de reunião do teams existente usando o cmdlet [set-CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy) . Ou crie uma nova política de reunião do teams usando o cmdlet [New-CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csteamsmeetingpolicy) e atribua-a a usuários.

Para habilitar um organizador da reunião para baixar o relatório de presença de reunião, defina o parâmetro **AllowEngagementReport** como **habilitado**. Quando habilitada, a opção para baixar o relatório é exibida no painel **participantes** .

Para impedir que um organizador da reunião Baixe o relatório, defina o parâmetro como **desabilitado**. Por padrão, essa configuração está desabilitada e a opção de baixar o relatório não está disponível.

## <a name="meeting-policy-settings---meeting-provider-for-islands-mode"></a>Configurações de política de reunião – provedor de reunião para o modo de ilhas

Esta é uma política por usuário. Esta configuração controla qual suplemento de reunião do Outlook é usado para *os usuários que estão no modo de ilhas*. Você pode especificar se os usuários só podem usar o suplemento de reunião do Teams e os suplementos de reunião do Skype for Business para agendar reuniões no Outlook.

Você só pode aplicar essa política a usuários que estão no modo de ilhas e ter o parâmetro **AllowOutlookAddIn** definido como **true** na política de reunião do Microsoft Teams.

No momento, você só pode usar o PowerShell para definir essa política. Você pode editar uma política de reunião do teams existente usando o cmdlet [set-CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy) . Ou crie uma nova política de reunião do teams usando o cmdlet [New-CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csteamsmeetingpolicy) e atribua-a a usuários.

Para especificar o suplemento de reunião que você deseja disponibilizar para os usuários, defina o parâmetro **PreferredMeetingProviderForIslandsMode** da seguinte maneira:

- Defina o parâmetro como **TeamsAndSfB** para habilitar o suplemento de reunião do Teams e o suplemento Skype for Business no Outlook. Esse é o valor padrão.
- Defina o parâmetro como **Teams** para habilitar somente o suplemento de reunião do teams no Outlook. Essa configuração de política garante que todas as reuniões futuras tenham um link de ingressar na reunião do teams. Não migra a reunião do Skype for Business existente para ingressar nos links para o Microsoft Teams. Essa configuração de política não afeta a presença, o chat, as chamadas PSTN ou qualquer outro recurso no Skype for Business, o que significa que os usuários continuarão a usar o Skype for Business para esses recursos.

  Se você definir o parâmetro para o **Teams** e, em seguida, voltar para **TeamsAndSfB**, ambos os suplementos de reunião serão habilitados. No entanto, observe que a reunião de equipes existentes que ingressam em links não será migrada para o Skype for Business. Somente as reuniões do Skype for Business agendadas após a alteração terão o link de ingresso na reunião do Skype for Business.

## <a name="meeting-policy-settings---video-filters-mode"></a>Configurações de política de reunião-modo de filtros de vídeo

Esta é uma política por usuário. Esta configuração controla se os usuários podem personalizar a tela de fundo do vídeo em uma reunião.

No momento, você só pode usar o PowerShell para definir essa política. Você pode editar uma política de reunião do teams existente usando o cmdlet [set-CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy) . Ou crie uma nova política de reunião do teams usando o cmdlet [New-CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csteamsmeetingpolicy) e, em seguida, atribua a política aos usuários.

Para especificar se os usuários podem personalizar a tela de fundo do vídeo em uma reunião, defina o parâmetro **VideoFiltersMode** da seguinte maneira:

|Valor de configuração no PowerShell |Comportamento  |
|---------|---------|
|**Sem filtros**     |O usuário não pode personalizar o plano de fundo do vídeo.|
|**BlurOnly**     |O usuário tem a opção de desfocar a tela de fundo do vídeo. |
|**BlurandDefaultBackgrounds**     |O usuário tem a opção de desfocar o plano de fundo do vídeo ou escolher um conjunto de imagens padrão para usar como plano de fundo. |
|**Filtros**     |Use tem a opção de desfocar a tela de fundo do vídeo, escolher do conjunto de imagens padrão ou carregar imagens personalizadas para usar como plano de fundo. |

> [!NOTE]
> Imagens carregadas pelos usuários não são filtradas pelo Teams. Ao usar a configuração **filtros** , você deve ter políticas de organização internas para impedir que os usuários carreguem imagens ofensivas ou inadequadas, ou imagens que sua organização não tem direitos de usar para planos de fundo de reunião do teams.

## <a name="related-topics"></a>Tópicos relacionados

- [Visão Geral do PowerShell do Teams](teams-powershell-overview.md)
- [Atribuir políticas a seus usuários no Teams](assign-policies.md)
- [Remover a política de reunião do RestrictedAnonymousAccess Teams dos usuários](meeting-policies-restricted-anonymous-access.md)
