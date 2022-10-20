---
title: Preparar-se para webinars no Microsoft Teams
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
description: Saiba como gerenciar políticas de Webinar para reuniões do Teams.
ms.openlocfilehash: 2c83452a37752745072b8a128f9e0eec8db3d7c0
ms.sourcegitcommit: f0e2a5928e9b959daf45202b9f256f65c2087195
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/20/2022
ms.locfileid: "68614574"
---
# <a name="set-up-for-webinars-in-microsoft-teams"></a>Preparar-se para webinars no Microsoft Teams

Este artigo ajudará você a configurar sua organização para hospedar webinars.

## <a name="what-are-webinars"></a>O que são webinars?

Webinars são reuniões estruturadas em que apresentadores e participantes têm funções claras, geralmente usadas para fins de treinamento ou cenários de geração de clientes potenciais de vendas e marketing.

Depois de configurar webinars em sua organização, os usuários podem agendar webinars e abrir o registro para os participantes. Ao contrário das reuniões tradicionais que incluem muitas discussões e atribuição de tarefas, os webinars destinam-se a apresentações interativas e fornecem ferramentas para análise de participantes.

> [!IMPORTANT]
> Para permitir que os usuários configurem webinars, Listas da Microsoft deve ser configurado no SharePoint habilitando a criação de listas pessoais. Para saber mais, confira [Configurações de controle para Listas da Microsoft](/sharepoint/control-lists).

## <a name="allow-users-to-schedule-webinars-in-the-teams-admin-center"></a>Permitir que os usuários agendem webinars no Centro de administração do Teams

Você pode usar o Centro de administração do Teams para configurar webinars para sua organização. Você encontrará as políticas para configurar webinars no centro de administração do Teams em **Políticas de Reunião** > **.**

### <a name="meeting-registration"></a>Registro de reunião

Se você ativar isso, os usuários poderão agendar webinars. Por padrão, isso é ativado. Se você quiser desativar o registro de reunião, defina essa política como **Desativada**.

> [!IMPORTANT]
> **O agendamento de reunião** privada deve estar ativado para que o registro da reunião funcione. Por padrão, essa política é ativada no centro de administração do Teams. Para alunos em locatários de educação, essa política é desativada por padrão. Para obter mais informações sobre como habilitar o agendamento de reuniões privadas para alunos, [consulte Teams para Educação políticas e pacotes de políticas](policy-packages-edu.md).

### <a name="who-can-register"></a>Quem pode se registrar

Se você selecionar **Todos**, todos os usuários, incluindo usuários anônimos, poderão se registrar e participar de webinars. Se você selecionar **Todos na organização**, somente os usuários em sua organização poderão se registrar para webinars. Se o registro da reunião estiver desativado, essa opção não estará disponível e ninguém poderá se registrar para webinars.

> [!NOTE]
> O valor padrão para **Quem pode se registrar** é **Todos na organização em** locatários de educação. Para obter mais informações, [consulte Teams para Educação Assistente de Política](easy-policy-setup-edu.md).

### <a name="engagement-report"></a>Relatório do Engagement

Quando isso estiver ativado, os organizadores poderão ver relatórios de quem se registrou e participou dos webinars que eles configuraram. Essa política está ativada por padrão. Para obter mais informações, consulte [Políticas de reunião no Teams – Relatório do Engagement](meeting-policies-in-teams-general.md#engagement-report). Para obter informações sobre a experiência do usuário final, consulte [Exibir e baixar relatórios de participação na reunião](https://support.microsoft.com/office/view-and-download-meeting-attendance-reports-in-teams-ae7cf170-530c-47d3-84c1-3aedac74d310?ui=en-US&#x26;rs=en-US&#x26;ad=US).

## <a name="allow-users-to-schedule-webinars-using-powershell"></a>Permitir que os usuários agendem webinars usando o PowerShell

Você pode usar os atributos a seguir no cmdlet **Windows PowerShell Set-CsTeamsMeetingPolicy** para configurar para webinars no Teams.

- AllowMeetingRegistration
- WhoCanRegister
- AllowPrivateMeetingScheduling

Leia [Set-CsTeamsMeetingPolicy para](/powershell/module/skype/set-csteamsmeetingpolicy) obter mais informações sobre o cmdlet.

> [!NOTE]
> Antes de executar esses cmdlets, você deve estar conectado ao Microsoft Teams PowerShell. Para obter mais informações, consulte [Gerenciar o Teams com o Microsoft Teams PowerShell](/microsoftteams/teams-powershell-managing-teams).

### <a name="allow-users-to-schedule-webinars"></a>Permitir que os usuários agendem webinars

Você pode restringir o registro aos usuários somente em sua organização ou abri-lo para todos dentro e fora do seu locatário. Por padrão, **WhoCanRegister** está habilitado e definido como Todos  para a política **Global (padrão em toda a** organização). Se você quiser desativar o registro de reunião, defina **AllowMeetingRegistration** como **False**.

> [!IMPORTANT]
> **AllowPrivateMeetingScheduling** deve ser definido como **True** para **que AllowMeetingRegistration** funcione.

1. Ativar o registro de reunião

```powershell
Set-CsTeamsMeetingPolicy -AllowMeetingRegistration $True
```

2. Ativar o agendamento de reunião privada

```powershell
Set-CsTeamsMeetingPolicy -AllowPrivateMeetingScheduling $True
```

3. Configurar quem pode se registrar para webinars

**Permitir *que somente* usuários em sua organização se registrem em webinars**

```powershell
Set-CsTeamsMeetingPolicy -WhoCanRegister EveryoneInCompany
```

**Para permitir que qualquer pessoa, incluindo usuários anônimos, se registre em webinars, execute:**

```powershell
Set-CsTeamsMeetingPolicy -WhoCanRegister Everyone
```

> [!CAUTION]
> Se o ingresso anônimo estiver desativado nas configurações de reunião, os usuários anônimos não poderão ingressar em webinars. Para saber mais e habilitar essa configuração, consulte [Configurações de reunião no Teams](meeting-settings-in-teams.md).

### <a name="collect-meeting-attendance"></a>Coletar participação na reunião

O **parâmetro AllowEngagementReport** permite ver quem registrou e participou de webinars. Essa política é ativada por padrão. Para desativá-lo, execute o seguinte comando no PowerShell:

```powershell
Set-CsTeamsMeetingPolicy -AllowEngagementReport Disabled
```

## <a name="configure-webinar-settings"></a>Definir configurações de webinar

Depois de habilitar seu ambiente para webinars, nenhum gerenciamento adicional de administrador é necessário. A política controla quais opções aparecem para organizadores de webinar.

## <a name="related-topics"></a>Tópicos relacionados

- [Políticas de reunião no Teams – Geral](meeting-policies-in-teams-general.md)
- [Documentação de Set-CsTeamsMeetingPolicy](/powershell/module/skype/set-csteamsmeetingpolicy)
- [Assistente Teams para Educação Política do Teams para Educação](easy-policy-setup-edu.md)
