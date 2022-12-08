---
title: Configurar webinars
ms.author: mabond
author: mkbond007
manager: serdars
ms.reviewer: sachung, emryan
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
search.appverid: MET150
f1.keywords:
- CSH
ms.custom: ''
ms.collection:
- M365-collaboration
- m365initiative-meetings
- highpri
description: Saiba como gerenciar políticas de registro de webinar e de reunião no Teams.
ms.openlocfilehash: 37983f8597b9e1a0ed511c2d767c503494447481
ms.sourcegitcommit: aa398950cc2f10b268c72a2b25caa0cf893e8230
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/08/2022
ms.locfileid: "69307576"
---
# <a name="set-up-webinars-in-microsoft-teams"></a>Configurar webinars no Microsoft Teams

> [!NOTE]
> Este artigo descreve alguns recursos em webinars que estão em versão prévia e exigirão uma licença do Teams Premium.

Microsoft agora oferece uma nova experiência webinar; este artigo descreve como atualizar suas configurações para usar esses recursos.

Recomendamos que você use a nova experiência webinar se planeja usar webinars.

O registro da reunião inclui a funcionalidade webinar básica, a capacidade de exigir o registro para reuniões e um relatório de presença. Ao habilitar a nova experiência webinar, você tem a capacidade de usar o registro de reunião e muitos novos recursos webinar, como:

- Página de registro e eventos dedicados para seu webinar
- Co-organizadores
- Biografias do apresentador na página de eventos
- Visão geral e gerenciamento do status de registro

Leia mais sobre os novos recursos disponíveis para seus usuários finais em [Introdução aos webinars do Teams](https://support.microsoft.com/office/42f3f874-22dc-4289-b53f-bbc1a69013e3).

Se sua organização tiver o registro de reunião habilitado, todos os webinars recém-criados terão a nova experiência. Webinars agendados anteriormente usarão a experiência webinar anterior. A nova experiência usa o TeamsEventsPolicy. Se você tiver webinars desligados, eles permanecerão desligados à medida que a nova experiência for distribuída.

Atualmente, a experiência webinar básica é controlada pelo registro de reunião usando a política de Reunião do Teams (Set-CsTeamsMeetingPolicy). No futuro, a configuração de registro de reunião não controlará webinars; os webinars estão em transição para serem controlados pela política de Eventos do Teams (Set-CsTeamsEventsPolicy).

A nova experiência webinar está configurada no PowerShell. Confira exemplos sobre [como configurar a nova experiência de webinar](#set-up-new-webinar-experience).

Para obter mais informações sobre as diferenças entre reuniões, webinars e eventos ao vivo, confira [Reuniões, webinars e eventos ao vivo](quick-start-meetings-live-events.md).

> [!IMPORTANT]
> Para permitir que os usuários configurem webinars, Listas da Microsoft deve ser configurado no SharePoint, permitindo a criação de listas pessoais para fins de descoberta eletrônica. Para saber mais, confira [Configurações de controle para Listas da Microsoft](/sharepoint/control-lists).

## <a name="set-up-new-webinar-experience"></a>Configurar nova experiência de webinar

Você deve usar o PowerShell para configurar a nova experiência webinar para sua organização. A capacidade de configurar a nova experiência webinar no centro de administração do Teams ainda não está disponível.

O registro de reunião deve estar ativado para usar a nova experiência webinar.

### <a name="configure-the-new-webinar-experience-with-powershell"></a>Configurar a nova experiência webinar com o PowerShell

Para configurar a nova experiência webinar, use os seguintes atributos no cmdlet **Set-CsTeamsEventsPolicy** Windows PowerShell.

|Parâmetro|Configuração padrão|Descrição|
|---------|-----------|---------------|
|AllowWebinars|Habilitado|Essa configuração determina se um usuário pode criar webinars.|
|EventAccessType|Todos|Essa configuração determina quais usuários podem acessar a página de registro de eventos ou o site de eventos a serem registrados, bem como qual tipo de usuário pode ingressar nas sessões no evento.|

Antes de executar esses cmdlets, você deve estar conectado ao Microsoft Teams PowerShell. Para obter mais informações, consulte [Gerenciar o Teams com Microsoft Teams PowerShell](/microsoftteams/teams-powershell-managing-teams).

1. Ative o registro da reunião.

    ```powershell
    Set-CsTeamsMeetingPolicy -Identity <policy name> -AllowMeetingRegistration $True
    ```

1. Ative a nova experiência webinar.

    ```powershell
    Set-CsTeamsEventsPolicy -Identity <policy name> -AllowWebinars Enabled
    ```

1. Configure quem pode se registrar para webinars e reuniões.

    - **Permitir que os usuários **_only_* _ em sua organização se registrem em webinars e meetings_*

        ```powershell
        Set-CsTeamsEventsPolicy -Identity <policy name> -EventAccessType EveryoneInCompanyExcludingGuests
        ```

    - **Permitir que todos, incluindo usuários anônimos, se registrem em webinars e reuniões**

        ```powershell
        Set-CsTeamsEventsPolicy -Identity <policy name> -EventAccessType Everyone
        ```

> [!IMPORTANT]
> Se **os usuários anônimos puderem participar de uma reunião** estiver desativado nas **configurações de Reunião, os usuários anônimos** não poderão ingressar em webinars. Para saber mais e habilitar essa configuração, consulte [Configurações de reunião no Teams](meeting-settings-in-teams.md).

## <a name="configure-meeting-registration"></a>Configurar o registro de reunião

Se você quiser usar webinars, o registro da reunião deve ser ativado.

Você pode usar o centro de administração do Teams em **Políticas de Reunião** de **Reuniões** >  para configurar o registro de reunião e webinars.

### <a name="meeting-registration"></a>Registro de reunião

Se você ativar **o registro de reunião**, os usuários da sua organização poderão agendar webinars e reuniões que exigem registro. Por padrão, isso está ativado. Se você quiser desativar o registro de reunião e os webinars, defina essa política como **Desativada**.

**O agendamento de reunião privada** deve estar ativado para que o registro da reunião funcione. Saiba mais sobre [agendamento de reuniões privadas](meeting-policies-in-teams-general.md).

Para alunos em locatários de educação, essa política é desativada por padrão. Para obter mais informações sobre como habilitar o agendamento de reuniões privadas para os alunos, consulte [Teams para Educação políticas e pacotes de políticas](policy-packages-edu.md).

#### <a name="who-can-register"></a>Quem pode se registrar

> [!NOTE]
> Essa política não se aplica à nova experiência de webinar. Para configurar quem pode se registrar para a nova experiência webinar, use `Set-CsTeamsEventsPolicy -EventAccessType`, conforme mostrado na [configuração da nova experiência webinar com o PowerShell](#configure-the-new-webinar-experience-with-powershell).

Essa política controla quais usuários podem registrar e participar de webinars somente com registro de reunião. Essa política tem duas opções, que só estarão disponíveis se **o registro da reunião** estiver ativado. Por padrão, **Quem pode se registrar** é definido como **Todos**.

Se você selecionar **Todos**, todos os usuários, incluindo usuários anônimos, poderão se registrar e participar de webinars. Se você selecionar **Todos na organização**, somente usuários em sua organização poderão se registrar e participar de webinars. Se o registro da reunião estiver desativado, a configuração **Quem pode registrar** não estará disponível e ninguém poderá se registrar para webinars.

O valor padrão para **Quem pode se registrar** é **Todos na organização** em locatários de educação. Para obter mais informações, consulte [assistente de política Teams para Educação](easy-policy-setup-edu.md).

## <a name="collect-webinar-and-meeting-registration-attendance"></a>Coletar webinar e presença de registro de reunião

Você pode usar o centro de administração do Teams em **Políticas de Reunião** de **Reuniões** >  para ativar o **relatório de engajamento**.

Quando isso estiver ativado, os organizadores podem ver relatórios de quem registrou e participou dos webinars ou reuniões que eles configuraram. Essa política está ativada por padrão. Para obter mais informações, consulte [Políticas de reunião no Teams – Relatório de engajamento](meeting-policies-in-teams-general.md#engagement-report). Para obter informações sobre a experiência do usuário final, consulte [Exibir e baixar relatórios de presença da reunião](https://support.microsoft.com/office/ae7cf170-530c-47d3-84c1-3aedac74d310).

No PowerShell, o parâmetro **AllowEngagementReport** pode ser usado para ativar isso. Essa política está ativada por padrão. Para desativá-lo, execute o seguinte comando no PowerShell:

```powershell
Set-CsTeamsMeetingPolicy -Identity <policy name> -AllowEngagementReport Disabled
```

Leia [Set-CsTeamsMeetingPolicy](/powershell/module/skype/set-csteamsmeetingpolicy) para obter mais informações sobre o cmdlet.

## <a name="turn-off-webinars"></a>Desativar webinars

Você pode desativar webinars usando o PowerShell. Isso desativará a nova experiência webinar, bem como os webinars somente com registro de reunião.

Use o seguinte script do PowerShell para desativar webinars:

```powershell
Set-CsTeamsMeetingPolicy -Identity <policy name> -AllowMeetingRegistration $False
Set-CSTeamsEventsPolicy -Identity <policy name> -AllowWebinars Disabled
```

## <a name="related-topics"></a>Tópicos relacionados

- [Políticas de reunião no Teams – Geral](meeting-policies-in-teams-general.md)
- [Set-CsTeamsMeetingPolicy](/powershell/module/skype/set-csteamsmeetingpolicy)
- [Set-CsTeamsEventsPolicy](/powershell/module/teams/set-csteamseventspolicy)
