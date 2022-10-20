---
title: Atendimento de chamada de grupo e compartilhamento de chamada
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 02/19/2019
ms.reviewer: jenstr
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
audience: Admin
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.users.voice.groupcallpickup.tooltip
- ms.teamsadmincenter.users.voice.callorderanddelay.tooltip
- Phone System
- seo-marvel-mar2020
description: O compartilhamento de chamadas e o recebimento de chamadas em grupo no Microsoft Teams permitem que os usuários compartilhem chamadas de entrada com colegas para que as chamadas possam ser capturadas quando o usuário não estiver disponível.
ms.openlocfilehash: 420378ce6d75523bf51b18c17e733d13a76ad877
ms.sourcegitcommit: f0e2a5928e9b959daf45202b9f256f65c2087195
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/20/2022
ms.locfileid: "68613843"
---
# <a name="call-sharing-and-group-call-pickup"></a>Atendimento de chamada de grupo e compartilhamento de chamada

Os recursos de compartilhamento de chamadas e recebimento de chamadas em grupo do Microsoft Teams permitem que os usuários compartilhem suas chamadas de entrada com colegas para que os colegas possam atender chamadas que ocorrem enquanto o usuário não está disponível.

O recebimento de chamadas em grupo é menos prejudicial para os destinatários do que outras formas de compartilhamento de chamadas, pois os usuários podem configurar como eles querem ser notificados sobre uma chamada compartilhada de entrada e podem decidir se a atenderão. A ordem na qual os membros do grupo de chamadas são notificados sobre a chamada de entrada pode ser especificada como simultânea ou em ordem (com 5 ou menos membros).

> [!IMPORTANT]
> Os usuários, o proprietário do grupo de chamadas e os membros do grupo de chamadas devem estar no modo de implantação somente do Teams. Para obter mais detalhes sobre os modos de implantação do Teams, consulte [Entender o Microsoft Teams e Skype for Business coexistência e interoperabilidade](teams-and-skypeforbusiness-coexistence-and-interoperability.md).

## <a name="license-required"></a>Licença necessária

Os usuários devem receber uma licença Telefonia do Microsoft Teams System para configurar e usar o compartilhamento de chamadas e o recebimento de chamadas em grupo. Para obter detalhes adicionais sobre o modelo de licenciamento, [consulte Aqui está o que você obtém com o Sistema de Telefonia](/MicrosoftTeams/here-s-what-you-get-with-phone-system).

## <a name="limitations"></a>Limitações

Um usuário só pode ser o proprietário de um grupo de chamadas. Cada grupo de chamadas configurado pode ter no máximo 25 usuários ou 32.768 caracteres. Um usuário pode ser membro de no máximo 25 grupos de chamadas.

Observe que os dispositivos móveis só serão notificados se estiverem definidos para faixa e toque.

## <a name="enable-the-use-of-group-call-pickup"></a>Habilitar o uso do recebimento de chamadas em grupo

Habilite grupos de chamadas definindo a **configuração TeamsCallingPolicy AllowCallGroups** para um usuário. Você pode usar o Centro de administração do Teams ou o PowerShell. Quando habilitado, o usuário pode configurar seus grupos de chamadas no cliente do Teams. 

Importante: ao desativar grupos de chamadas para usuários, você deve limpar as relações do grupo de chamadas para usuários no centro de administração do Teams para evitar o roteamento de chamadas incorreto. 

## <a name="use-teams-admin-center"></a>Usar o Centro de administração do Teams

Para configurar o recebimento de chamadas em grupo para usuários usando o Centro de administração do Teams, consulte Definir configurações [de chamada para seus usuários](/MicrosoftTeams/user-call-settings).

## <a name="use-powershell"></a>Usar o PowerShell

Para configurar grupos de chamadas para usuários, use os seguintes cmdlets do Módulo do PowerShell do Teams:

- [Set-CsUserCallingSettings](/powershell/module/teams/set-csusercallingsettings)

- [Get-CsUserCallingSettings](/powershell/module/teams/get-csusercallingsettings)

### <a name="examples"></a>Exemplos

O exemplo a seguir cria um grupo de chamadas para user1@contoso.com com os membros user2@contoso.com e user3@contoso.com e define o encaminhamento imediato de chamadas para o grupo de chamadas para user1@contoso.com:

```powershell
$cgm = @("sip:user2@contoso.com","sip:user3@contoso.com")
Set-CsUserCallingSettings -Identity user1@contoso.com -CallGroupOrder InOrder -CallGroupTargets $cgm
Set-CsUserCallingSettings -Identity user1@contoso.com -IsForwardingEnabled $true -ForwardingType Immediate -ForwardingTargetType Group
```

O próximo exemplo mostra como atualizar o grupo de chamadas de user1@contoso.com para adicionar user5@contoso.com e remover user6@contoso.com:

```powershell
$ucs = Get-CsUserCallingSettings -Identity user1@contoso.com
$cgt = {$ucs.CallGroupTargets}.Invoke()
$cgt.Add("sip:user5@contoso.com")
$cgt.Remove("sip:user6@contoso.com")
Set-CsUserCallingSettings -Identity user1@contoso.com -CallGroupOrder $ucs.CallGroupOrder -CallGroupTargets $cgt
```

## <a name="more-information"></a>Mais informações

[Encaminhamento de chamadas e toque simultâneo no Teams](https://support.office.com/article/call-forwarding-and-simultaneous-ring-in-teams-a88da9e8-1343-4d3c-9bda-4b9615e4183e)

[Política de chamada do Teams](/MicrosoftTeams/teams-calling-policy)

[New-CsTeamsCallingPolicy](/powershell/module/skype/new-csteamscallingpolicy)

[Set-CsTeamsCallingPolicy](/powershell/module/skype/set-csteamscallingpolicy)
