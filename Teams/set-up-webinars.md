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
ms.openlocfilehash: 739c0b5494b0ecc5b9a20fd8db4756313848325b
ms.sourcegitcommit: e5d6a2c3ad45c1285016b93ec4c7afea907d71a1
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/07/2021
ms.locfileid: "52275512"
---
# <a name="set-up-for-webinars-in-microsoft-teams"></a>Configurar para webinars em Microsoft Teams

Este artigo ajudará você a configurar sua organização para hospedar webinars.

## <a name="what-are-webinars"></a>O que são webinars?

Webinars são reuniões estruturadas em que instrutores e participantes têm funções claras, geralmente usadas para fins de treinamento ou cenários de geração de leads de vendas e marketing.

Depois de configurar webinars em sua organização, os usuários podem agendar webinars e abrir o registro para os participantes. Ao contrário das reuniões tradicionais que incluem muitas discussões e atribuição de tarefas, os webinars são destinados a apresentações interativas e fornecem ferramentas para análise do participante.

## <a name="allow-users-to-schedule-webinars-using-powershell"></a>Permitir que os usuários agendem webinars usando o PowerShell

Você pode usar os seguintes atributos no cmdlet **set-CsTeamsMeetingPolicy Windows PowerShell set-CsTeamsMeetingPolicy** para configurar para webinars Teams.

- AllowMeetingRegistration
- WhoCanRegister
- AllowPrivateMeetingScheduling

Leia [Set-CsTeamsMeetingPolicy](/powershell/module/skype/set-csteamsmeetingpolicy) para obter mais informações sobre o cmdlet.

> [!NOTE]
> Antes de executar esses cmdlets, você deve estar conectado ao Skype for Business PowerShell Online. Para obter mais informações, consulte [Manage Skype for Business Online with Microsoft 365 or Office 365 PowerShell](/office365/enterprise/powershell/manage-skype-for-business-online-with-office-365-powershell).

### <a name="allow-users-to-schedule-webinars"></a>Permitir que os usuários agendem webinars

Para permitir que os usuários em sua organização agendem webinars, execute:

```powershell
Set-CsTeamsMeetingPolicy -AllowMeetingRegistration True
```
### <a name="configure-who-can-register-for-webinars"></a>Configurar quem pode se registrar para webinars

Você pode restringir o registro aos usuários somente em sua organização ou abri-lo para todos dentro e fora do locatário. Por padrão, **WhoCanRegister** está habilitado e definido como **Todos**. Se você quiser desativar o registro de reunião, de definir **WhoCanRegister** como **False**.

> [!IMPORTANT]
> Lembre-se de **que AllowPrivateMeetingScheduling** deve ser definido como **True** para **WhoCanRegister** funcionar. Além disso, as Listas da Microsoft precisam ser configuradas SharePoint. Para saber mais, confira [Configurações de controle para Listas da Microsoft.](/sharepoint/control-lists)

**Para permitir *que apenas* usuários em sua organização se registrem para webinars, execute:**

```powershell
Set-CsTeamsMeetingPolicy -AllowPrivateMeetingScheduling True
```

Em seguida, execute:

```powershell
Set-CsTeamsMeetingPolicy -WhoCanRegister EveryoneInCompany
```

**Para permitir que qualquer pessoa, incluindo usuários anônimos, registre-se para webinars, execute:**

```powershell
Set-CsTeamsMeetingPolicy -AllowPrivateMeetingScheduling True
```

Em seguida, execute:

```powershell
Set-CsTeamsMeetingPolicy -WhoCanRegister Everyone
```

> [!IMPORTANT]
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
