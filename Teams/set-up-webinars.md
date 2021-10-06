---
title: Preparar-se para webinars no Microsoft Teams
author: KarliStites
ms.author: kastites
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
description: Saiba como gerenciar políticas do Webinar para Teams reuniões.
ms.openlocfilehash: 35c0cc2ab6c05d123aae45bc0c375cf815db36b4
ms.sourcegitcommit: 74d3ab35c344d70b2399bc46a6ced3ab2762a470
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/06/2021
ms.locfileid: "60138207"
---
# <a name="set-up-for-webinars-in-microsoft-teams"></a>Preparar-se para webinars no Microsoft Teams

Este artigo ajudará você a configurar sua organização para hospedar webinars.

## <a name="what-are-webinars"></a>O que são webinars?

Webinars são reuniões estruturadas em que apresentadores e participantes têm funções claras, geralmente usadas para fins de treinamento ou cenários de geração de leads de vendas e marketing.

Depois de configurar webinars em sua organização, os usuários podem agendar webinars e abrir o registro para os participantes. Ao contrário das reuniões tradicionais que incluem muitas discussões e atribuição de tarefas, os webinars são destinados a apresentações interativas e fornecem ferramentas para análise do participante.

> [!IMPORTANT]
> Para permitir que os usuários configurem webinars, Listas da Microsoft deve ser configurado em SharePoint habilitando a criação de listas pessoais. Para saber mais, confira [Configurações de controle para Listas da Microsoft](/sharepoint/control-lists).

## <a name="allow-users-to-schedule-webinars-in-the-teams-admin-center"></a>Permitir que os usuários agendem webinars no Teams de administração

Você pode usar o Teams de administração para configurar webinars para sua organização. Você encontrará as políticas para configurar webinars no centro de administração Teams reuniões em **políticas**  >  **de reunião.**

### <a name="allow-meeting-registration"></a>Permitir registro de reunião

Se você ativar isso, os usuários poderão agendar webinars. Por padrão, isso está ligado. Se você quiser desativar o registro de reunião, de definir essa política como **Desativar**.

> [!IMPORTANT]
> **Permitir que o agendamento de reuniões** privadas deve estar on para que o registro de reunião funcione. Por padrão, essa política é Teams centro de administração. Para alunos em locatários de educação, essa política é desligada por padrão. Para obter mais informações sobre como habilitar o agendamento de reuniões privadas para alunos, [consulte Teams para Educação políticas e pacotes de política.](policy-packages-edu.md)

### <a name="who-can-register"></a>Who pode se registrar

Se você selecionar **Todos**, todos os usuários, incluindo usuários anônimos, poderão se registrar e participar de webinars. Se você selecionar **Todos na organização**, somente os usuários da sua organização poderão se registrar nos webinars. Se o registro de reunião estiver desligado, essa opção não estará disponível e ninguém poderá se registrar nos webinars.

> [!NOTE]
> O valor padrão para **Who pode se registrar** é Todos na organização **em** locatários de educação. Para obter mais informações, [consulte Teams para Educação Assistente de Política](easy-policy-setup-edu.md).

### <a name="allow-engagement-report"></a>Permitir relatório de envolvimento

Se você ativar isso, os organizadores poderão ver relatórios de quem registrou e participou dos webinars que eles configuraram. Essa política está desligada por padrão. Para obter mais informações, consulte [Políticas de reunião em Teams - Permitir relatório de envolvimento](meeting-policies-in-teams-general.md#allow-engagement-report). Para obter informações sobre a experiência do usuário final, consulte [View and download meeting attendance reports](https://support.microsoft.com/office/view-and-download-meeting-attendance-reports-in-teams-ae7cf170-530c-47d3-84c1-3aedac74d310?ui=en-US&#x26;rs=en-US&#x26;ad=US).

## <a name="allow-users-to-schedule-webinars-using-powershell"></a>Permitir que os usuários agendem webinars usando o PowerShell

Você pode usar os seguintes atributos no cmdlet **set-CsTeamsMeetingPolicy Windows PowerShell set-CsTeamsMeetingPolicy** para configurar para webinars Teams.

- AllowMeetingRegistration
- WhoCanRegister
- AllowPrivateMeetingScheduling

Leia [Set-CsTeamsMeetingPolicy](/powershell/module/skype/set-csteamsmeetingpolicy) para obter mais informações sobre o cmdlet.

> [!NOTE]
> Antes de executar esses cmdlets, você deve estar conectado ao Microsoft Teams PowerShell. Para obter mais informações, consulte [Manage Teams with Microsoft Teams PowerShell](/microsoftteams/teams-powershell-managing-teams).

### <a name="allow-users-to-schedule-webinars"></a>Permitir que os usuários agendem webinars

Você pode restringir o registro aos usuários somente em sua organização ou abri-lo para todos dentro e fora do locatário. Por padrão, **WhoCanRegister** está habilitado e definido como **Todos** para a política **Global (padrão em toda** a organização). Se você quiser desativar o registro de reunião, de definir **AllowMeetingRegistration** como **False**.

> [!IMPORTANT]
> **AllowPrivateMeetingScheduling** deve ser definido como **True** para **AllowMeetingRegistration** funcionar.

1. Ativar o registro de reunião

```powershell
Set-CsTeamsMeetingPolicy -AllowMeetingRegistration $True
```

2. Ativar o agendamento de reuniões privadas

```powershell
Set-CsTeamsMeetingPolicy -AllowPrivateMeetingScheduling $True
```

3. Configurar quem pode se registrar para webinars

**Permitir *que apenas* usuários em sua organização se registrem em webinars**

```powershell
Set-CsTeamsMeetingPolicy -WhoCanRegister EveryoneInCompany
```

**Para permitir que qualquer pessoa, incluindo usuários anônimos, registre-se para webinars, execute:**

```powershell
Set-CsTeamsMeetingPolicy -WhoCanRegister Everyone
```

> [!CAUTION]
> Se a junção anônima estiver desligada nas configurações de reunião, os usuários anônimos não poderão ingressar em webinars. Para saber mais e habilitar essa configuração, consulte [Configurações de reunião em Teams](meeting-settings-in-teams.md).

### <a name="collect-meeting-attendance"></a>Coletar participação na reunião

Se você quiser que os organizadores analisem quem registrou e participou de webinars, você precisará ativar a **política AllowEngagementReport.** Para fazer isso, execute o seguinte comando no PowerShell.

```powershell
Set-CsTeamsMeetingPolicy -AllowEngagementReport Enabled
```

## <a name="configure-webinar-settings"></a>Configurar configurações do webinar

Depois de habiligá-los para webinars, não é necessário mais gerenciamento de administradores. A política controla quais opções aparecem para organizadores do webinar.

## <a name="related-topics"></a>Tópicos relacionados

- [Políticas de reunião em Teams - Geral](meeting-policies-in-teams-general.md)
- [Documentação set-CsTeamsMeetingPolicy](/powershell/module/skype/set-csteamsmeetingpolicy)
- [Teams para Educação Assistente de Política](easy-policy-setup-edu.md)
