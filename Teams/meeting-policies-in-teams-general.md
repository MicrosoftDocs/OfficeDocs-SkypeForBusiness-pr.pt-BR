---
title: Gerenciar políticas de reunião geral
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: sonua, shalenc
audience: admin
ms.localizationpriority: medium
search.appverid: MET150
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.meetingpolicies.general
- seo-marvel-apr2020
description: Aprenda a gerenciar as configurações gerais de política de reunião Teams.
ms.openlocfilehash: b7c08799ee9e7c2b1e6239b17abaa66b7d1e3d47
ms.sourcegitcommit: 7cc7e237b0da270c9cf4a3e535db16dd113e4300
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/25/2021
ms.locfileid: "61177932"
---
# <a name="meeting-policy-settings---general"></a>Configurações de política de reunião - Geral

<a name="bkgeneral"> </a>

Este artigo descreve as seguintes configurações gerais de política para reuniões Teams reuniões:

- [Reunir agora em canais](#meet-now-in-channels)
- [Outlook de complemento](#outlook-add-in)
- [Agendamento de reunião do canal](#channel-meeting-scheduling)
- [Agendamento de reuniões particulares](#private-meeting-scheduling)
- [Reunir agora em reuniões privadas](#meet-now-in-private-meetings)
- [Modo de função de apresentador designado](#designated-presenter-role-mode)
- [Relatório de envolvimento](#engagement-report)
- [Registro de reunião](#meeting-registration)
- [Who pode se registrar](#who-can-register)
- [Provedor de reuniões para modo Ilhas](#meeting-provider-for-islands-mode)

## <a name="meet-now-in-channels"></a>Reunir agora em canais

Essa é uma política por usuário e se aplica antes de começar uma reunião. Essa configuração controla se um usuário pode iniciar uma reunião ad hoc em um Teams canal. Se você ativar isso, os usuários poderão clicar no botão **Atender** para iniciar uma reunião ad hoc ou agendar uma reunião no canal. O valor padrão é True.

[![Captura de tela mostrando o ícone Reunir agora abaixo de uma mensagem. ](media/meeting-policies-meet-now.png) ](media/meeting-policies-meet-now.png#lightbox)

## <a name="outlook-add-in"></a>Outlook de complemento

Essa é uma política por usuário e se aplica antes de começar uma reunião. Essa configuração controla se as reuniões do Teams podem ser agendadas a partir do Outlook (Windows, Mac, Web e dispositivo móvel).

![Captura de tela mostrando a capacidade de agendar uma nova reunião.](media/meeting-policies-outlook-add-in.png)

Se você desativar isso, os usuários não poderão agendar Teams reuniões quando criarem uma nova reunião no Outlook. Por exemplo, no Outlook no Windows, a opção **Nova reunião do Teams** não será exibida na faixa de opções.

## <a name="channel-meeting-scheduling"></a>Agendamento de reunião do canal

Use a política existente AllowChannelMeetingScheduling para controlar os tipos de eventos que podem ser criados nos calendários do canal de equipe. Essa é uma política por usuário e se aplica antes de começar uma reunião. Essa configuração controla se os usuários podem agendar uma reunião em um canal do Teams. Por padrão, essa configuração é ativada. 

Se essa política estiver desligada, os usuários não poderão criar novas reuniões de canal. No entanto, as reuniões existentes no canal podem ser editadas pelo organizador do evento.

Agendar uma reunião será desabilitada.

![Captura de tela mostrando a opção Agendar uma reunião Teams.](media/schedule-meeting-option.png)

A seleção de canal está desabilitada.

[Captura de tela mostrando a opção de calendário para selecionar um canal no qual você ![ deseja agendar uma reunião. ](media/meeting-policies-select-a-channel-to-meet-in.png) ](media/meeting-policies-select-a-channel-to-meet-in.png#lightbox)

Na página postagens de canal, o seguinte será desabilitado:

- Botão **Agendar uma reunião** na caixa de texto responder ao canal.
  ![Captura de tela mostrando a opção de calendário para selecionar um canal no qual você deseja agendar uma reunião.](media/schedule-meeting-disabled-in-chat2.png)
  
- Botão **Agendar uma reunião** no cabeçalho do canal.
  ![Captura de tela mostrando a opção de calendário para selecionar um canal pelo qual você deseja agendar uma reunião.](media/schedule-now-in-header.png)

No calendário do canal:

- Botão **Adicionar novo evento** no cabeçalho do calendário do canal será desabilitado.
  ![Captura de tela mostrando a opção de calendário para selecionar um canal que permitirá agendar uma reunião.](media/add-new-event-disabled.png)

- Os usuários não poderão arrastar e selecionar um bloco de tempo no calendário do canal para criar uma reunião de canal.

- Os usuários não podem usar atalhos de teclado para criar uma reunião no calendário do canal.

No Centro de Administração:

O aplicativo de calendário de canal será mostrado na seção **Aplicativos da Microsoft** na página de políticas de permissão do aplicativo.

![Captura de tela mostrando a política de permissões do aplicativo no Teams de administração.](media/manage-microsoft-apps-policy.png)

## <a name="private-meeting-scheduling"></a>Agendamento de reuniões particulares

Essa é uma política por usuário e se aplica antes de começar uma reunião. Essa configuração controla se os usuários podem agendar reuniões particulares no Teams. Uma reunião é particular quando não é publicada em um canal de uma equipe.

Observe que, se você desativar **Permitir agendamento de reuniões particulares** e **Permitir agendamento de reunião de canal**, as opções **Adicionar participantes necessários** e **Adicionar canal** serão desabilitadas para os usuários no Teams. Por padrão, essa configuração é ativada.

## <a name="meet-now-in-private-meetings"></a>Reunir agora em reuniões privadas

Essa é uma política por usuário e se aplica antes de começar uma reunião. Essa configuração controla se um usuário pode iniciar uma reunião privada ad hoc.  Por padrão, essa configuração é ativada.

## <a name="designated-presenter-role-mode"></a>Modo de função de apresentador designado

Essa é uma política por usuário. Essa configuração permite alterar o valor padrão da configuração **Quem pode apresentar?** nas **Opções de reunião** no cliente Teams. Essa configuração de política afeta todas as reuniões, incluindo reuniões Reunir Agora.

A configuração **Quem pode apresentar?** permite que os organizadores de reunião escolham quem pode apresentar na reunião. Para saber mais, confira [Alterar as configurações de participante de uma reunião do Teams](https://support.microsoft.com/article/change-participant-settings-for-a-teams-meeting-53261366-dbd5-45f9-aae9-a70e6354f88e) e [Funções em uma reunião do Teams](https://support.microsoft.com/article/roles-in-a-teams-meeting-c16fa7d0-1666-4dde-8686-0a0bfe16e019).

No momento, você só pode usar o PowerShell para definir essa configuração de política. Você pode editar uma política de reunião do Teams existente usando o cmdlet [Set-CsTeamsMeetingPolicy](/powershell/module/skype/set-csteamsmeetingpolicy). Ou crie uma nova política de reunião do Teams usando o cmdlet [New-CsTeamsMeetingPolicy](/powershell/module/skype/new-csteamsmeetingpolicy) e atribua-a aos usuários.

Para especificar o valor padrão da configuração **Quem pode apresentar?** no Teams, defina o parâmetro **DesignatedPresenterRoleMode** para um dos seguintes:

- **EveryoneUserOverride**: todos os participantes da reunião podem ser apresentadores. Esse é o valor padrão. Esse parâmetro corresponde à configuração **Todos** no Teams.
- **EveryoneInCompanyUserOverride**: os usuários autenticados na organização, incluindo os usuários convidados, podem ser apresentadores. Esse parâmetro corresponde à configuração **Pessoas na minha organização** no Teams.
- **OrganizerOnlyUserOverride**: somente o organizador da reunião pode ser um apresentador e todos os participantes da reunião são designados como participantes. Esse parâmetro corresponde à configuração **Somente eu** no Teams.

Lembre-se de que, depois de definir o valor padrão, os organizadores de reunião ainda poderão alterar essa configuração no Teams e escolher quem poderá apresentar nas reuniões agendadas por eles.

## <a name="engagement-report"></a>Relatório de envolvimento

Essa é uma política por usuário. Essa configuração controla se o organizador da reunião pode baixar o relatório de participação da [Reunião](teams-analytics-and-reports/meeting-attendance-report.md).

Essa política está desligada por padrão e permite que seus organizadores vejam quem registrou e participou das reuniões e webinars que eles configuraram. Para ativar isso no centro de administração Teams, vá para **Políticas** de Reunião de Reuniões e de definir a  >  política como **Habilitado**.

Você pode editar uma política de reunião do Teams existente usando o cmdlet [Set-CsTeamsMeetingPolicy](/powershell/module/skype/set-csteamsmeetingpolicy). Ou crie uma nova política de reunião do Teams usando o cmdlet [New-CsTeamsMeetingPolicy](/powershell/module/skype/new-csteamsmeetingpolicy) e atribua-a aos usuários.

Para permitir que um organizador da reunião baixe o relatório de participação da reunião, de definir o **parâmetro AllowEngagementReport** **como Habilitado**. Quando habilitada, a opção para baixar o relatório é exibida no painel **Participantes**. Por padrão, essa configuração não está habilitada.

Para impedir que o organizador da reunião baixe o relatório, defina o parâmetro como **Desabilitado**.

## <a name="meeting-registration"></a>Registro de reunião

Essa é uma política por usuário. Se você ativar isso, os usuários de sua organização poderão configurar webinars. Essa política é habilitada por padrão.

Para editar essa política no centro de administração Teams, vá para **Políticas de Reunião** de  >  **Reuniões.** Para desativar o registro de reunião, de definir a política como **Desativar**.

Você pode editar uma política de reunião do Teams existente usando o cmdlet [Set-CsTeamsMeetingPolicy](/powershell/module/skype/set-csteamsmeetingpolicy). Ou crie uma nova política de reunião do Teams usando o cmdlet [New-CsTeamsMeetingPolicy](/powershell/module/skype/new-csteamsmeetingpolicy) e atribua-a aos usuários.

Para ativar o registro de reunião, de definir o  **parâmetro MeetingRegistration** como **True**. Isso é definido como **True** por padrão.

Para desativar o registro de reunião e impedir que os usuários agendam webinars, de definir o parâmetro como **False**.

## <a name="who-can-register"></a>Who pode se registrar

Essa política controla quais usuários podem registrar e participar de webinars. Essa política tem duas opções, que só estarão disponíveis se o registro **de reunião** estiver ligado.

- Definir **Who pode** se  registrar em Todos se você quiser permitir que todos, incluindo usuários anônimos, registrem e participem de webinars que os usuários de sua organização configuraram.
- Definir **Who pode** se  registrar em Todos na organização se você quiser permitir que apenas os usuários em sua organização registrem e participem de webinars.

Por padrão, **Who pode se registrar** é definido como **Todos**. Para editar essa política no centro de administração Teams, vá para **Políticas de Reunião** de  >  **Reuniões.**

Você pode editar uma política de reunião do Teams existente usando o cmdlet [Set-CsTeamsMeetingPolicy](/powershell/module/skype/set-csteamsmeetingpolicy). Ou crie uma nova política de reunião do Teams usando o cmdlet [New-CsTeamsMeetingPolicy](/powershell/module/skype/new-csteamsmeetingpolicy) e atribua-a aos usuários.

Para permitir que todos, incluindo usuários anônimos, registrem e participem de webinars, de definir o **parâmetro WhoCanRegister** como **Todos**. Isso é definido como **Todos** por padrão.

Para permitir que apenas usuários em sua organização registrem e participem de webinars, de definir o parâmetro como **EveryoneInCompany**.

## <a name="meeting-provider-for-islands-mode"></a>Provedor de reuniões para modo Ilhas

Essa é uma política por usuário. Essa configuração controla qual suplemento de reunião do Outlook é usado para os *usuários que estão no modo Uso Paralelo*. Você pode especificar se os usuários podem usar apenas o suplemento de reunião do Teams ou os suplementos de reunião do Teams e de reunião do Skype for Business para agendar reuniões no Outlook.

Você só pode aplicar esta política aos usuários que estão no modo Uso Paralelo e possuem o parâmetro **AllowOutlookAddIn** definido como **Verdadeiro** na política de reunião do Teams.

No momento, você só pode usar o PowerShell para definir essa política. Você pode editar uma política de reunião do Teams existente usando o cmdlet [Set-CsTeamsMeetingPolicy](/powershell/module/skype/set-csteamsmeetingpolicy). Ou crie uma nova política de reunião do Teams usando o cmdlet [New-CsTeamsMeetingPolicy](/powershell/module/skype/new-csteamsmeetingpolicy) e atribua-a aos usuários.

Para especificar o suplemento de reunião que você deseja disponibilizar para os usuários, defina o parâmetro **PreferredMeetingProviderForIslandsMode** da seguinte maneira:

- Defina o parâmetro como **TeamsAndSfB** para habilitar o suplemento de reunião do Teams e o suplemento Skype for Business no Outlook. Esse é o valor padrão.
- Defina o parâmetro como **Teams** para habilitar somente o suplemento de reunião do Teams no Outlook. Essa configuração de política garante que todas as reuniões futuras possuam um link de ingresso na reunião do Teams. Ela não migra links de ingresso existentes do Skype for Business para o Teams. Essa configuração de política não afeta a presença, o chat, a chamada PSTN ou qualquer outro recurso no Skype for Business, o que significa que os usuários continuarão a usar o Skype for Business para esses recursos.

  Se você definir o parâmetro para **Teams** e, em seguida, retornar para **TeamsAndSfB**, os suplementos para ambas reuniões serão habilitados. No entanto, lembre-se de links de ingresso existentes da reunião do Teams não serão migradas para o Skype for Business. Somente as reuniões do Skype for Business agendadas depois da alteração terão um link de ingresso na reunião do Skype for Business.

## <a name="meeting-reactions"></a>Reações de reunião

A configuração AllowMeetingReactions só pode ser aplicada usando o PowerShell. Não há nenhuma opção para ativar ou desativar AllowMeetingReactions no Centro de administração do Teams.

As reações de reunião estão ativadas por padrão. Desativar as reações para um usuário não significa que ele não possa usar as reações nas reuniões agendadas por ele. O organizador da reunião ainda pode ativar as reações na página de opção da reunião, independentemente da configuração padrão.


## <a name="related-topics"></a>Tópicos relacionados

- [Visão Geral do PowerShell do Teams](teams-powershell-overview.md)
- [Atribuir políticas em Teams](policy-assignment-overview.md)
- [Remover a política de reunião do Teams RestrictedAnonymousAccess dos usuários](meeting-policies-restricted-anonymous-access.md)
