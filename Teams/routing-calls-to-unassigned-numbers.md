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
ms.openlocfilehash: f092cf5501d723dabb4336d648387833dd376e9b
ms.sourcegitcommit: d847256fca80e4e8954f767863c880dc8472ca04
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/10/2022
ms.locfileid: "65304053"
---
# <a name="routing-calls-to-unassigned-numbers"></a>Roteamento de chamadas para números não atribuídos

Como administrador, você pode rotear chamadas para números não atribuídos em sua organização. Por exemplo, talvez você queira rotear chamadas para números não atribuídos da seguinte maneira: 

- Roteie todas as chamadas para um determinado número não atribuído para um comunicado personalizado.

- Roteie todas as chamadas para um determinado número não atribuído para o quadro de controle principal.

Você pode rotear chamadas para números não atribuídos para um usuário, para uma conta de recurso associada a um Atendedor Automático ou a uma Fila de Chamadas ou a um serviço de comunicado que reproduzirá um arquivo de áudio personalizado para o chamador.

## <a name="configuration"></a>Configuração

Para rotear chamadas para um número não atribuído, use o cmdlet New/Get/Set/Remove-CsTeamsUnassignedNumberTreatment disponível no módulo 2.5.1 ou posterior do PowerShell do Teams.

Você precisa especificar o número ou intervalo de números chamado e o roteamento associado para chamadas a esses números. Por exemplo, o comando a seguir especifica que todas as chamadas para o número +1 (555) 222-3333 serão roteados para a conta de recurso aa@contoso.com:

``` PowerShell
$RAObjectId = (Get-CsOnlineApplicationInstance -Identity aa@contoso.com).ObjectId


New-CsTeamsUnassignedNumberTreatment -Identity MainAA -Pattern "^\+15552223333$" -TargetType ResourceAccount -Target $RAObjectId -TreatmentPriority 1
```

O próximo exemplo especifica que todas as chamadas para o intervalo de números +1 (555) 333-0000 a +1 (555) 333-9999 serão roteados para o serviço de comunicado, que reproduzirá o arquivo de áudio MainAnnouncement.wav para o chamador.

```PowerShell
$Content = Get-Content "C:\Media\MainAnnoucement.wav" -Encoding byte -ReadCount 0

$AudioFile = Import-CsOnlineAudioFile -FileName "MainAnnouncement.wav" -Content $Content

$fid = [System.Guid]::Parse($AudioFile.Id)

New-CsTeamsUnassignedNumberTreatment -Identity TR1 -Pattern "^\+1555333\d{4}$" -TargetType Announcement -Target $fid.Guid -TreatmentPriority 2
```

## <a name="notes"></a>Observações

- Se estiver roteando para um comunicado, o arquivo de áudio será reproduzido uma vez para o chamador.

- Para rotear chamadas para números de assinante do Plano de Chamada da Microsoft não atribuídos, seu locatário precisa ter [Créditos de Comunicação disponíveis](what-are-communications-credits.md).

- Para rotear chamadas para números de serviço do Plano de Chamadas da Microsoft não atribuídos, seu locatário precisa ter pelo menos Sistema de Telefonia – licença de Usuário Virtual.

- Os formatos de arquivo de áudio personalizado com suporte são WAV (PCM linear descompactado com profundidade de 8/16/32 bits em mono ou estéreo), WMA (somente mono) e MP3. O conteúdo do arquivo de áudio não pode ter mais de 5 MB.

- As chamadas de entrada para Microsoft Teams chamadas de saída e de Microsoft Teams terão o número chamado verificado em relação ao intervalo de números não atribuído.

- Se um padrão/intervalo especificado contiver números de telefone atribuídos a um usuário ou conta de recurso no locatário, as chamadas a esses números de telefone serão roteadas para o destino apropriado e não roteadas para o tratamento de número não atribuído especificado. Não há outras verificações dos números no intervalo. Se o intervalo contiver um número de telefone externo válido, as chamadas de Microsoft Teams para esse número de telefone serão roteados de acordo com o tratamento.

## <a name="related-topics"></a>Tópicos relacionados

- [Get-CsTeamsUnassignedNumberTreatment](/powershell/module/teams/get-csteamsunassignednumbertreatment)

- [New-CsTeamsUnassignedNumberTreatment](/powershell/module/teams/new-csteamsunassignednumbertreatment)

- [Set-CsTeamsUnassignedNumberTreatment](/powershell/module/teams/set-csteamsunassignednumbertreatment)

- [Remove-CsTeamsUnassignedNumberTreatment](/powershell/module/teams/remove-csteamsunassignednumbertreatment)

- [Test-CsTeamsUnassignedNumberTreatment](/powershell/module/teams/test-csteamsunassignednumbertreatment)
