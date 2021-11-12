---
title: Roteamento de chamadas para números não atribuídos
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.reviewer: jenstr
ms.topic: article
ms.assetid: aa2ec464-3481-4bbb-8c14-e13e18093df5
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
- m365initiative-voice
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Calling Plans
description: Saiba como rotear chamadas para números não atribuídos em sua organização.
ms.openlocfilehash: 93d9ce289820bdcf9bb4a1e13e78bb8794b77dbd
ms.sourcegitcommit: bdca3b5eb35a17b27c5a052d83ab229b7c911dd4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/12/2021
ms.locfileid: "60947498"
---
# <a name="routing-calls-to-unassigned-numbers"></a>Roteamento de chamadas para números não atribuídos

Como administrador, você pode rotear chamadas para números não atribuídos em sua organização. Por exemplo, talvez você queira rotear chamadas para números não atribuídos da seguinte forma: 

- Roteie todas as chamadas para um determinado número não atribuído para um comunicado personalizado.

- Rotee todas as chamadas para um determinado número não atribuído para o quadro de alternados principal.

Você pode rotear chamadas para números não atribuídos para um usuário, para uma conta de recurso associada a um Atendedor Automático ou uma Fila de Chamadas ou para um serviço de anúncio que reproduzirá um arquivo de áudio personalizado para o chamador.

## <a name="configuration"></a>Configuração

Para rotear chamadas para um número não atribuído, use o cmdlet New/Get/Set/Remove-CsTeamsUnassignedNumberTreatment disponível no módulo 2.5.1 ou posterior do Teams PowerShell.

Você precisa especificar o número ou intervalo de números chamado e o roteamento associado para chamadas a esses números. Por exemplo, o seguinte comando especifica que todas as chamadas para o número +1 (555) 222-3333 serão roteados para a conta de recurso aa@contoso.com:

``` PowerShell
$RAObjectId = (Get-CsOnlineApplicationInstance -Identity aa@contoso.com).ObjectId


New-CsTeamsUnassignedNumberTreatment -Identity MainAA -Pattern "^\+15552223333$" -TargetType ResourceAccount -Target $RAObjectId -TreatmentPriority 1
```

O próximo exemplo especifica que todas as chamadas para o intervalo de números +1 (555) 333-0000 a +1 (555) 333-9999 serão roteados para o serviço de anúncio, que reproduzirá o arquivo de áudio MainAnnouncement.wav para o chamador.

```PowerShell
$Content = Get-Content "C:\Media\MainAnnoucement.wav" -Encoding byte -ReadCount 0

$AudioFile = Import-CsOnlineAudioFile -FileName "MainAnnouncement.wav" -Content $Content

$fid = [System.Guid]::Parse($AudioFile.Id)

New-CsTeamsUnassignedNumberTreatment -Identity TR1 -Pattern "^\+1555333\d{4}$" -TargetType Announcement -Target $fid.Guid -TreatmentPriority 2
```

## <a name="notes"></a>Observações

- Se o roteamento para um comunicado, o arquivo de áudio será tocado uma vez para o chamador.

- Para rotear chamadas para números de assinantes do Plano de Chamadas da Microsoft não atribuídos, seu locatário precisa ter créditos de [comunicações disponíveis.](what-are-communications-credits.md)

- Para rotear chamadas para números de serviço do Plano de Chamadas da Microsoft não atribuídos, seu locatário precisa ter pelo menos uma Sistema de Telefonia – licença de usuário virtual.

## <a name="related-topics"></a>Tópicos relacionados

- [Get-CsTeamsUnassignedNumberTreatment](/powershell/module/teams/get-csteamsunassignednumbertreatment)

- [New-CsTeamsUnassignedNumberTreatment](/powershell/module/teams/new-csteamsunassignednumbertreatment)

- [Set-CsTeamsUnassignedNumberTreatment](/powershell/module/teams/set-csteamsunassignednumbertreatment)

- [Remove-CsTeamsUnassignedNumberTreatment](/powershell/module/teams/remove-csteamsunassignednumbertreatment)
