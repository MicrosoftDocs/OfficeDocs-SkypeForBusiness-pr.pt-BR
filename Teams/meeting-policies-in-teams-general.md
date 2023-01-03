---
title: Gerenciar políticas de reunião geral
ms.author: mabond
author: mkbond007
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: sonua, shalenc
audience: admin
ms.localizationpriority: medium
search.appverid: MET150
ms.collection:
- M365-collaboration
- m365initiative-meetings
appliesto:
- Microsoft Teams
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.meetingpolicies.general
- seo-marvel-apr2020
description: Aprenda a gerenciar configurações de política de reunião geral no Teams.
ms.openlocfilehash: cc0d704c5a78d09da4c1332d48f795cdb611d134
ms.sourcegitcommit: 84a832330c0a9f9fb818bbfb22e534fe035c1837
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/03/2023
ms.locfileid: "69693374"
---
# <a name="meeting-policy-settings---general"></a>Configurações de política de reunião - Geral

<a name="bkgeneral"> </a>

Este artigo descreve as seguintes configurações de política geral para reuniões do Teams:

- [Conheça agora em canais](#meet-now-in-channels)
- [Suplemento do Outlook](#outlook-add-in)
- [Agendamento de reunião do canal](#channel-meeting-scheduling)
- [Agendamento de reunião privada](#private-meeting-scheduling)
- [Relatório de engajamento](#engagement-report)
- [Registro de reunião](#meeting-registration)
- [Seminários via Web](#webinars)
- [Provedor de reunião para o modo Islands](#meeting-provider-for-islands-mode)
- [Reações de reunião](#meeting-reactions)
- [Coach de Alto-Falante](#speaker-coach)

## <a name="meet-now-in-channels"></a>Conheça agora em canais

Essa é uma política por usuário e se aplica antes de começar uma reunião. Essa configuração controla se um usuário pode iniciar uma reunião não planejada em um canal do Teams. Se você ativar essa configuração, os usuários poderão clicar no botão **Atender** para iniciar uma reunião não planejada ou agendar uma reunião no canal. Essa configuração está ativada por padrão.

[![Captura de tela mostrando o ícone Reunir agora abaixo de uma mensagem.](media/meeting-policies-meet-now.png)](media/meeting-policies-meet-now.png#lightbox)

## <a name="outlook-add-in"></a>Suplemento do Outlook

Essa é uma política por usuário e se aplica antes de começar uma reunião. Essa configuração controla se as reuniões do Teams podem ser agendadas a partir do Outlook (Windows, Mac, Web e dispositivo móvel).

![Captura de tela mostrando a capacidade de agendar uma nova reunião.](media/meeting-policies-outlook-add-in.png)

Se você desativar essa configuração, os usuários não poderão agendar reuniões do Teams quando criarem uma nova reunião no Outlook. Por exemplo, no Outlook no Windows, a opção **Nova reunião do Teams** não será exibida na faixa de opções.

## <a name="channel-meeting-scheduling"></a>Agendamento de reunião do canal

Use a política existente AllowChannelMeetingScheduling para controlar os tipos de eventos que podem ser criados nos calendários do canal de equipe. Essa é uma política por usuário e se aplica antes de começar uma reunião. Essa configuração controla se os usuários podem agendar uma reunião em um canal do Teams. Por padrão, essa configuração é ativada.

Se essa política estiver desabilitada, os usuários não conseguirão criar novas reuniões no canal. No entanto, as reuniões existentes no canal podem ser editadas pelo organizador do evento.

Agendar uma reunião será desabilitada.

![Captura de tela mostrando a opção Agendar uma reunião no Teams.](media/schedule-meeting-option.png)

A seleção de canal está desabilitada.

[![Captura de tela mostrando a opção calendário para selecionar um canal no qual você deseja agendar uma reunião.](media/meeting-policies-select-a-channel-to-meet-in.png)](media/meeting-policies-select-a-channel-to-meet-in.png#lightbox)

Na página de postagens do canal, as seguintes funcionalidades serão desabilitadas:

- Botão **Agendar uma reunião** na caixa de texto responder ao canal.
  ![Captura de tela mostrando a opção calendário para selecionar um canal no qual você deseja agendar uma reunião.](media/schedule-meeting-disabled-in-chat2.png)
  
- Botão **Agendar uma reunião** no cabeçalho do canal.
  ![Captura de tela mostrando a opção calendário para selecionar um canal por meio do qual você deseja agendar uma reunião.](media/schedule-now-in-header.png)

No calendário do canal:

- Botão **Adicionar novo evento** no cabeçalho do calendário do canal será desabilitado.
  ![Captura de tela mostrando a opção de calendário para selecionar um canal que permitirá agendar uma reunião.](media/add-new-event-disabled.png)

- Os usuários não poderão arrastar e selecionar um bloco de tempo no calendário do canal para criar uma reunião de canal.

- Os usuários não podem usar atalhos de teclado para criar uma reunião no calendário do canal.

No Centro de Administração:

O aplicativo de calendário de canal será mostrado na seção **Aplicativos da Microsoft** na página de políticas de permissão do aplicativo.

![Captura de tela mostrando a política de permissões do aplicativo no centro de administração do Teams.](media/manage-microsoft-apps-policy.png)

## <a name="private-meeting-scheduling"></a>Agendamento de reunião privada

Essa é uma política por usuário e se aplica antes de começar uma reunião. Essa configuração controla se os usuários podem agendar reuniões particulares no Teams. Uma reunião é particular quando não é publicada em um canal de uma equipe. **O agendamento de reunião privada** é ativado por padrão.

Se você desativar as configurações **de agendamento de reunião privada** e **canal** , as opções **Adicionar participantes necessários** e **Adicionar canal** serão desabilitadas para usuários no Teams.

## <a name="engagement-report"></a>Relatório de engajamento

Essa é uma política por usuário. Essa configuração controla se os organizadores da reunião podem baixar o [relatório de engajamento da reunião](teams-analytics-and-reports/meeting-attendance-report.md).

Essa política está ativada por padrão e permite que seus organizadores vejam quem registrou e participou das reuniões e webinars que eles configuraram. Para desativá-lo no centro de administração do Teams, acesse Políticas de Reunião de Reuniões e defina a configuração do **relatório de engajamento** como **Desativada** > .

Você também pode editar uma política de reunião do Teams existente usando o cmdlet [Set-CsTeamsMeetingPolicy](/powershell/module/skype/set-csteamsmeetingpolicy) . Ou crie uma nova política de reunião do Teams usando o cmdlet [New-CsTeamsMeetingPolicy](/powershell/module/skype/new-csteamsmeetingpolicy) e atribua-a aos usuários.

Por padrão, o parâmetro **AllowEngagementReport** é definido como **Habilitado** no PowerShell. Para impedir que um organizador de reunião baixe o relatório de engajamento da reunião, defina o parâmetro **AllowEngagementReport** como **Desabilitado**.

Quando essa política está habilitada, a opção de baixar o relatório de engajamento da reunião é exibida no painel **Participantes** .

> [!NOTE]
> Como administrador, você não pode exibir o relatório de presença para reuniões que não organiza. No entanto, você pode exibir os detalhes do participante para uma determinada reunião dentro de 24 horas dessa reunião. No centro de administração do Teams, acesse **Usuários** > **Gerenciar usuários**. Escolha o nome de exibição para o organizador da reunião. Selecione a guia **Reuniões & chamadas** e escolha a ID de reunião ou A ID de chamada apropriada. Em seguida, selecione **Detalhes do participante**.

Para obter mais informações, incluindo os limites do relatório de engajamento, consulte [exibindo e baixando relatórios de presença da reunião no Teams](https://support.microsoft.com/office/ae7cf170-530c-47d3-84c1-3aedac74d310).

## <a name="meeting-registration"></a>Registro de reunião

Essa é uma política por usuário. Se você ativar essa configuração, os usuários da sua organização poderão adicionar registro a uma reunião. Essa política está habilitada por padrão.

Para saber mais sobre o registro da reunião, leia [Configurar registro de reunião](set-up-webinars.md#configure-meeting-registration).

## <a name="webinars"></a>Seminários via Web

Essa é uma política por usuário. Se você habilitar webinars, os usuários em sua organização poderão criar webinars com gerenciamento de registro robusto, sites de eventos e registro personalizáveis e opções de reunião padrão orientadas a eventos. Essa política está habilitada por padrão.

Leia mais sobre webinars em [Configurar webinars](set-up-webinars.md).

Para obter mais informações sobre as diferenças entre reuniões, webinars e eventos ao vivo, confira [Reuniões, webinars e eventos ao vivo](quick-start-meetings-live-events.md).

## <a name="meeting-provider-for-islands-mode"></a>Provedor de reunião para o modo Islands

Essa é uma política por usuário. Essa configuração controla qual suplemento de reunião do Outlook é usado para os *usuários que estão no modo Uso Paralelo*. Você pode especificar se os usuários podem usar apenas o suplemento de Reunião do Teams ou os suplementos de Reunião do Teams e de Reunião do Skype for Business para agendar reuniões no Outlook.

Você só pode aplicar esta política aos usuários que estão no modo Uso Paralelo e possuem o parâmetro **AllowOutlookAddIn** definido como **Verdadeiro** na política de reunião do Teams.

No momento, você só pode usar o PowerShell para definir essa política. Você pode editar uma política de reunião do Teams existente usando o cmdlet [Set-CsTeamsMeetingPolicy](/powershell/module/skype/set-csteamsmeetingpolicy). Ou crie uma nova política de reunião do Teams usando o cmdlet [New-CsTeamsMeetingPolicy](/powershell/module/skype/new-csteamsmeetingpolicy) e atribua-a aos usuários.

Para especificar o suplemento de reunião que você deseja disponibilizar para os usuários, defina o parâmetro **PreferredMeetingProviderForIslandsMode** da seguinte maneira:

- Defina o parâmetro como **TeamsAndSfB** para habilitar o suplemento de reunião do Teams e o suplemento Skype for Business no Outlook. **TeamsAndSfB** é o valor padrão.
- Defina o parâmetro como **Teams** para habilitar somente o suplemento de reunião do Teams no Outlook. Essa configuração de política garante que todas as reuniões futuras possuam um link de ingresso na reunião do Teams. Ela não migra links de ingresso existentes do Skype for Business para o Teams. Essa configuração de política não afeta a presença, o chat, a chamada PSTN ou qualquer outro recurso no Skype for Business, o que significa que os usuários continuarão a usar o Skype for Business para esses recursos.

  Se você definir o parâmetro para **Teams** e, em seguida, retornar para **TeamsAndSfB**, os suplementos para ambas reuniões serão habilitados. No entanto, lembre-se de links de ingresso existentes da reunião do Teams não serão migradas para o Skype for Business. Somente as reuniões do Skype for Business agendadas depois da alteração terão um link de ingresso na reunião do Skype for Business.

## <a name="meeting-reactions"></a>Reações de reunião

A disponibilidade de reações de reunião pode ser configurada por meio da interface do centro de administração do Teams ou usando o PowerShell. As reações de reunião são habilitadas por padrão.

No centro de administração do Teams, as reações de reunião podem ser habilitadas ou desabilitadas nas **políticas de Reunião** de **Reuniões** >  na seção **Participantes & convidados** de uma política de reunião.

Para configurar a configuração no PowerShell, use o cmdlet [Set-CsTeamsMeetingPolicy](/powershell/module/skype/set-csteamsmeetingpolicy) . Para desativá-lo, defina **AllowMeetingReactions** como **False**.

Desativar as reações de um usuário não significa que um usuário não possa usar reações em reuniões agendadas. O organizador da reunião ainda pode ativar as reações na página de opção da reunião, independentemente da configuração padrão.

## <a name="speaker-coach"></a>Coach de Alto-Falante

Essa configuração permite que os usuários ativem o Speaker Coach durante uma reunião do Teams. O Speaker Coach escuta o áudio do usuário enquanto ele apresenta e fornece comentários privados em tempo real e sugestões para aprimoramento. O usuário também recebe um relatório de resumo de seus comentários após a reunião.

> [!NOTE]
> O usuário que ligou o Speaker Coach durante a reunião é o único que pode ver o relatório de resumo dos comentários. Os administradores não terão acesso a nenhum desses dados.

Atualmente, você só pode definir e editar essa política no PowerShell. usando o cmdlet [Set-CsTeamsMeetingPolicy](/powershell/module/skype/set-csteamsmeetingpolicy) . Ou crie uma nova política de reunião do Teams usando o cmdlet [New-CsTeamsMeetingPolicy](/powershell/module/skype/new-csteamsmeetingpolicy) e atribua-a aos usuários.

Essa configuração está habilitada por padrão. Para desativá-lo, defina **AllowMeetingCoach** como **False**.

## <a name="related-topics"></a>Tópicos relacionados

- [Visão Geral do PowerShell do Teams](teams-powershell-overview.md)
- [Atribuir políticas no Teams](policy-assignment-overview.md)
- [Remover a política de reunião do Teams RestrictedAnonymousAccess dos usuários](meeting-policies-restricted-anonymous-access.md)
