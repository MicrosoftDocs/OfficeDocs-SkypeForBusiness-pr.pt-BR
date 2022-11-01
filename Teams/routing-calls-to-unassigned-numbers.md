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
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Calling Plans
description: Saiba como rotear chamadas para números não atribuídos em sua organização.
ms.openlocfilehash: 810c6b1547586d5494dbba3d0ddbdfc8d5d3c5e1
ms.sourcegitcommit: ffcc4c7d5688fee28f5fdc8bb8e6b78afb1ee626
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/31/2022
ms.locfileid: "68795513"
---
# <a name="routing-calls-to-unassigned-numbers"></a>Roteamento de chamadas para números não atribuídos

Como administrador, você pode rotear chamadas para números não atribuídos em sua organização. Por exemplo, talvez você queira rotear chamadas para números não atribuídos da seguinte maneira: 

- Encaminhe todas as chamadas para um determinado número não atribuído para um anúncio personalizado.

- Encaminhe todas as chamadas para um determinado número não atribuído para o quadro de opções principal.

Você pode rotear chamadas para números não atribuídos para um usuário, para uma conta de recurso associada a um Atendente Automático ou uma Fila de Chamadas ou a um serviço de anúncio que reproduzirá um arquivo de áudio personalizado para o chamador.

Você pode configurar o roteamento de números não atribuídos usando o centro de administração do Teams ou usando o PowerShell.

## <a name="use-teams-admin-center"></a>Usar o centro de administração do Teams

1. Na navegação à esquerda do centro de administração do Microsoft Teams, acesse **Números de Telefone de** **Voz** > .

2. Na guia **Regras de roteamento** , clique em **Adicionar**.

3. Dê um nome à regra, uma descrição e especifique a ordem de avaliação da regra.

4. Decida qual tipo de regra você deseja adicionar. Você pode selecionar regras em que o tipo de padrão de número de telefone está pré-configurado e você conclui o padrão e a opção de roteamento. Você também pode selecionar configuração avançada, em que insira diretamente a expressão regular para o padrão de número de telefone e a opção de roteamento.

5. Selecione **Salvar**.

Você também pode criar uma regra de roteamento diretamente para um número de telefone não atribuído.

1. Na navegação à esquerda do centro de administração do Microsoft Teams, acesse **Números de Telefone de** **Voz** > .

2. Na guia **Números** , selecione um número de telefone não atribuído e clique em **Rotear** na parte superior da exibição

4. Dê um nome à regra, uma descrição e especifique a ordem de avaliação da regra.

4. Selecione a opção roteamento.

5. Selecione **Salvar**.

Você pode testar suas regras de roteamento usando o recurso Número de teste.

1. Na navegação à esquerda do centro de administração do Microsoft Teams, acesse **Números de Telefone de** **Voz** > .

2. Na guia **Regras de roteamento** , clique em **Número de teste**.

3. Insira um número de telefone diretamente ou clique em **Selecionar um número** e selecione um dos números de telefone não atribuídos na lista suspensa.

4. Selecione **Testar**.


## <a name="use-powershell"></a>Usar o PowerShell

Para rotear chamadas para um número não atribuído, use o cmdlet New/Get/Set/Remove-CsTeamsUnassignedNumberTreatment disponível no módulo 2.5.1 do Teams PowerShell ou posterior.

Você precisa especificar o número ou o intervalo de números chamados e o roteamento associado para chamadas para esses números. Por exemplo, o comando a seguir especifica que todas as chamadas para o número +1 (555) 222-3333 serão roteadas para a conta de recursos aa@contoso.com:

``` PowerShell
$RAObjectId = (Get-CsOnlineApplicationInstance -Identity aa@contoso.com).ObjectId

New-CsTeamsUnassignedNumberTreatment -Identity MainAA -Pattern "^\+15552223333$" -TargetType ResourceAccount -Target $RAObjectId -TreatmentPriority 1
```

O próximo exemplo especifica que todas as chamadas para o intervalo de números +1 (555) 333-0000 a +1 (555) 333-9999 serão roteadas para o serviço de anúncio, que reproduzirá o arquivo de áudio MainAnnouncement.wav para o chamador.

```PowerShell
$Content = [System.IO.File]::ReadAllBytes('C:\Media\MainAnnouncement.wav')

$AudioFile = Import-CsOnlineAudioFile -FileName "MainAnnouncement.wav" -Content $Content

$fid = [System.Guid]::Parse($AudioFile.Id)

New-CsTeamsUnassignedNumberTreatment -Identity TR1 -Pattern "^\+1555333\d{4}$" -TargetType Announcement -Target $fid.Guid -TreatmentPriority 2
```

## <a name="notes"></a>Observações

- Se o roteamento para um anúncio, o arquivo de áudio será reproduzido uma vez para o chamador.

- Para rotear chamadas para números de assinantes não assinados do Plano de Chamada da Microsoft, seu locatário precisa ter [créditos de comunicação](what-are-communications-credits.md) disponíveis.

- Para rotear chamadas para números de serviço não assinados do Plano de Chamada da Microsoft, seu locatário precisa ter pelo menos uma **licença Telefonia do Microsoft Teams Conta de Recursos**.

- Os formatos com suporte ao arquivo de áudio personalizado são WAV (PCM linear não compactado com profundidade de 8/16/32 bits em mono ou estéreo), WMA (somente mono) e MP3. O conteúdo do arquivo de áudio não pode ter mais de 5 MB.

> [!NOTE]
> Você é responsável por limpar e proteger independentemente todos os direitos e permissões necessários para usar qualquer arquivo de música ou áudio com seu serviço do Microsoft Teams. Isso pode incluir propriedade intelectual e outros direitos em qualquer música, efeitos sonoros, áudio, marcas, nomes e outros conteúdos no arquivo de áudio de todos os detentores de direitos relevantes. Os detentores podem incluir artistas, atores, artistas, músicos, compositores, compositores, gravadoras, editores de música, sindicatos, guildas, sociedades de direitos, organizações de gestão coletiva e quaisquer outras partes que possuam, controlam ou licenciam os direitos autorais de música, efeitos sonoros, áudio e outros direitos de propriedade intelectual.

- As chamadas de entrada para o Microsoft Teams e as chamadas de saída do Microsoft Teams terão o número chamado verificado no intervalo de números não atribuído.

- Se um padrão/intervalo especificado contiver números de telefone atribuídos a um usuário ou conta de recurso no locatário, as chamadas para esses números de telefone serão roteadas para o destino apropriado e não roteadas para o tratamento de número não atribuído especificado. Não há outras verificações dos números no intervalo. Se o intervalo contiver um número de telefone externo válido, as chamadas de saída do Microsoft Teams para esse número de telefone serão roteadas de acordo com o tratamento.


## <a name="related-topics"></a>Tópicos relacionados

- [Get-CsTeamsUnassignedNumberTreatment](/powershell/module/teams/get-csteamsunassignednumbertreatment)

- [New-CsTeamsUnassignedNumberTreatment](/powershell/module/teams/new-csteamsunassignednumbertreatment)

- [Set-CsTeamsUnassignedNumberTreatment](/powershell/module/teams/set-csteamsunassignednumbertreatment)

- [Remove-CsTeamsUnassignedNumberTreatment](/powershell/module/teams/remove-csteamsunassignednumbertreatment)

- [Test-CsTeamsUnassignedNumberTreatment](/powershell/module/teams/test-csteamsunassignednumbertreatment)
