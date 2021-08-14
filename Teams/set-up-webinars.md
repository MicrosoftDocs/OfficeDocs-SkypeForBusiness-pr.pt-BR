---
title: Configurar para webinars em Microsoft Teams
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
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- CSH
ms.custom: ''
ms.collection:
- M365-collaboration
- m365initiative-meetings
description: Saiba como gerenciar políticas do Webinar para Teams reuniões.
ms.openlocfilehash: 8386ef4ea9dd90d60cdc8c891461c3dc1a6b37ad4f3f7c47e42808e3c8f826a3
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2021
ms.locfileid: "54330875"
---
# <a name="set-up-for-webinars-in-microsoft-teams"></a>Configurar para webinars em Microsoft Teams

Este artigo ajudará você a configurar sua organização para hospedar webinars.

## <a name="what-are-webinars"></a>O que são webinars?

Webinars são reuniões estruturadas em que apresentadores e participantes têm funções claras, geralmente usadas para fins de treinamento ou cenários de geração de leads de vendas e marketing.

Depois de configurar webinars em sua organização, os usuários podem agendar webinars e abrir o registro para os participantes. Ao contrário das reuniões tradicionais que incluem muitas discussões e atribuição de tarefas, os webinars são destinados a apresentações interativas e fornecem ferramentas para análise do participante.

## <a name="allow-users-to-schedule-webinars-using-powershell"></a>Permitir que os usuários agendem webinars usando o PowerShell

Você pode usar os seguintes atributos no cmdlet **set-CsTeamsMeetingPolicy Windows PowerShell set-CsTeamsMeetingPolicy** para configurar para webinars Teams.

- AllowMeetingRegistration
- WhoCanRegister
- AllowPrivateMeetingScheduling

Leia [Set-CsTeamsMeetingPolicy](/powershell/module/skype/set-csteamsmeetingpolicy) para obter mais informações sobre o cmdlet.

> [!NOTE]
> Antes de executar esses cmdlets, você deve estar conectado ao Microsoft Teams PowerShell. Para obter mais informações, consulte [Manage Teams with Microsoft Teams PowerShell](/microsoftteams/teams-powershell-managing-teams).

### <a name="allow-users-to-schedule-webinars"></a>Permitir que os usuários agendem webinars

Você pode restringir o registro aos usuários somente em sua organização ou abri-lo para todos dentro e fora do locatário. Por padrão, **WhoCanRegister** está habilitado e definido como **Todos**. Se você quiser desativar o registro de reunião, de definir **AllowMeetingRegistration** como **False**.

> [!IMPORTANT]
> **AllowPrivateMeetingScheduling** deve ser definido como **True** para **AllowMeetingRegistration** funcionar. Além disso, Listas da Microsoft precisa ser configurada em SharePoint. Para saber mais, confira [Configurações de controle para Listas da Microsoft](/sharepoint/control-lists).

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

### <a name="configure-webinar-settings"></a>Configurar configurações do webinar

Depois de habiligá-los para webinars, não é necessário mais gerenciamento de administradores. A política controla quais opções aparecem para organizadores do webinar.

## <a name="related-topics"></a>Tópicos relacionados

- [Políticas de reunião em Teams - Geral](meeting-policies-in-teams-general.md)
- [Documentação set-CsTeamsMeetingPolicy](/powershell/module/skype/set-csteamsmeetingpolicy)
