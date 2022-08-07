---
title: Definir configurações de chamada para usuários
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.reviewer: jenstr
ms.topic: article
ms.assetid: 67ccda94-1210-43fb-a25b-7b9785f8a061
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
audience: Admin
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.callqueues.overview
- Phone System
- seo-marvel-apr2020
description: Saiba como definir as configurações do usuário para encaminhamento e delegação de chamadas.
ms.openlocfilehash: 64907043448f44ff861ede026d0a4343899ad98b
ms.sourcegitcommit: 173bdbaea41893d39a951d79d050526b897044d5
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/07/2022
ms.locfileid: "67272226"
---
# <a name="configure-call-settings-for-your-users"></a>Definir configurações de chamada para seus usuários

Este artigo descreve como você, o administrador, pode alterar as configurações de encaminhamento e delegação de chamadas para seus usuários. Talvez você queira alterar essas configurações, por exemplo, se:

- Um usuário está de licença por doença e você precisa garantir que as chamadas recebidas para o usuário sejam encaminhadas para um colega.
- Você precisa inspecionar as configurações de encaminhamento de chamadas para todos os usuários em um departamento e, potencialmente, corrigi-las conforme apropriado.
- Um novo assistente foi empregado e você precisa adicionar o assistente como representante para um grupo de funcionários.

Você pode usar o centro de administração do Teams ou os cmdlets do PowerShell do Teams para exibir e alterar as configurações de chamada para os usuários.

Para definir configurações de chamada para um usuário, o usuário deve ter uma licença atribuída do Sistema de Telefonia da Microsoft.

## <a name="use-the-teams-admin-center"></a>Usar o centro de administração do Teams

Você pode usar o Centro de administração do Teams para definir configurações de encaminhamento de chamadas e não respondidas, recebimento de chamadas em grupo e delegação de chamadas para seus usuários.

Para definir configurações imediatas de encaminhamento de chamadas:

1. No centro de administração do Teams, vá para **Usuários** > **Gerenciar usuários** e selecione um usuário.

2. Na página de detalhes do usuário, vá para a **guia** Voz.

3. Em **Regras de atendimento de chamadas**, selecione **Ser encaminhado** imediatamente e selecione o tipo de encaminhamento de chamadas e o destino apropriados.

Para configurar o toque simultâneo, na mesma página, selecione **Tocar nos dispositivos do usuário**. Na lista **suspensa Permitir também** , selecione a configuração de toque simultâneo apropriada.

Para definir as configurações não respondidas, na mesma página, selecione a configuração apropriada **na lista suspensa** Se não respondida. No Anel **para esses muitos segundos antes de redirecionar** a lista suspensa, especifique o número de segundos de espera.

A configuração da delegação de chamadas e do recebimento de chamadas em grupo é integrada às configurações de encaminhamento de chamadas e não respondidas selecionando o tipo apropriado. Por exemplo, para configurar essas chamadas também deve tocar nos representantes do usuário, na mesma página, selecione Delegação **de** chamada em **Também permitir**. Em seguida, adicione os delegados apropriados **selecionando Adicionar pessoas** e clicando em **Salvar**.

## <a name="use-powershell"></a>Usar o PowerShell

Você pode usar o PowerShell para definir as configurações de encaminhamento de chamadas e delegação para seus usuários.  Você usará os seguintes cmdlets, que estão disponíveis no módulo do Teams PowerShell versão 4.0 ou posterior:

- [Get-CsUserCallingSettings](/powershell/module/teams/get-csusercallingsettings) – mostra as configurações de encaminhamento de chamadas, delegados e informações de delegador para um usuário.
- [Set-CsUserCallingSettings](/powershell/module/teams/set-csusercallingsettings) – define as configurações de encaminhamento de chamadas para um usuário.
- [New-CsUserCallingDelegate](/powershell/module/teams/new-csusercallingdelegate) – adiciona um novo delegado com permissões para um usuário.
- [Set-CsUserCallingDelegate](/powershell/module/teams/set-csusercallingdelegate) – altera as permissões de um delegado existente.
- [Remove-CsUserCallingDelegate](/powershell/module/teams/remove-csusercallingdelegate) – remove um delegado de um usuário.

### <a name="display-call-forward-and-delegation-settings-for-a-user"></a>Exibir configurações de encaminhamento de chamadas e delegação para um usuário

Para exibir as configurações atuais de encaminhamento de chamadas e delegação para um usuário, use o cmdlet Get-CsUserCallingSettings, conforme mostrado no exemplo a seguir:

```PowerShell
Get-CsUserCallingSettings -Identity user1@contoso.com
SipUri                    : sip:opr1@contoso.com
IsForwardingEnabled       : True
ForwardingType            : Simultaneous
ForwardingTarget          :
ForwardingTargetType      : MyDelegates
IsUnansweredEnabled       : True
UnansweredTarget          :
UnansweredTargetType      : Voicemail
UnansweredDelay           : 00:00:20
Delegates                 : Id:sip:user2@contoso.com
Delegators                :
CallGroupOrder            : InOrder
CallGroupTargets          : {}
GroupMembershipDetails    :
GroupNotificationOverride : Ring

(Get-CsUserCallingSettings -Identity user1@contoso.com).Delegates

Id             : sip:user2@contoso.com
MakeCalls      : True
ManageSettings : True
ReceiveCalls   : True
```

A saída mostra que user1 tem toque simultâneo para delegados configurados. Chamadas não respondidas são enviadas para a caixa postal após 20 segundos. User2 é definido como o delegado com todas as permissões de delegado.

### <a name="set-call-forward-settings-for-a-user"></a>Definir configurações de encaminhamento de chamadas para um usuário

Para encaminhar todas as chamadas de user1 para user2, use o cmdlet Set-CsUserCallingSettings, conforme mostrado no exemplo a seguir:

```PowerShell
Set-CsUserCallingSettings -Identity user1@contoso.com -IsForwardingEnabled $true -ForwardingType Immediate -ForwardingTargetType SingleTarget -ForwardingTarget user2@contoso.com
```

Para tocar simultaneamente em todos os delegados para user3, use o cmdlet Set-CsUserCallingSettings, conforme mostrado no exemplo a seguir:

```PowerShell
Set-CsUserCallingSettings -Identity user3@contoso.com -IsForwardingEnabled $true -ForwardingType Simultaneous -ForwardingTargetType MyDelegates
```

O exemplo a seguir usa o cmdlet Set-CsUserCallingSettings para configurar um grupo de chamadas para user4 com user5 e user6 como membros. Todas as chamadas aos membros do grupo são encaminhadas na ordem em que são definidas:

```PowerShell
$cgm = @("user5@contoso.com","user6@contoso.com")

Set-CsUserCallingSettings -Identity user4@contoso.com -CallGroupOrder InOrder -CallGroupTargets $cgm

Set-CsUserCallingSettings -Identity user4@contoso.com -IsForwardingEnabled $true -ForwardingType Immediate -ForwardingTargetType Group
```

Para obter mais exemplos, [consulte Set-CsUserCallingSettings](/powershell/module/teams/get-csusercallingsettings).

### <a name="add-a-calling-delegate-for-a-user"></a>Adicionar um representante de chamada para um usuário

Para adicionar user2 como um delegado para user1 com todas as permissões permitidas, use o cmdlet New-CsUserCallingDelegate, conforme mostrado no exemplo a seguir:

```PowerShell
New-CsUserCallingDelegate -Identity user1@contoso.com -Delegate user2@contoso.com -MakeCalls $true -ReceiveCalls $true -ManageSettings $true
```

### <a name="change-calling-delegate-permissions"></a>Alterar as permissões de representante de chamada

Para alterar as permissões de representante, por exemplo, para não permitir que o usuário2 faça chamadas para user1, use o cmdlet Set-CsUserCallingDelegate conforme mostrado no exemplo a seguir:

```PowerShell
Set-CsUserCallingDelegate -Identity user1@contoso.com -Delegate user2@contoso.com -MakeCalls $false
```

### <a name="remove-a-calling-delegate-for-a-user"></a>Remover um representante de chamada para um usuário

Para remover user2 como um delegado para user1, use o cmdlet Remove-CsUserCallingDelegate, conforme mostrado no exemplo a seguir:

```PowerShell
Remove-CsUserCallingDelegate -Identity user1@contoso.com -Delegate user2@contoso.com
```

## <a name="related-topics"></a>Tópicos relacionados

- [Get-CsUserCallingSettings](/powershell/module/teams/get-csusercallingsettings)
- [Set-CsUserCallingSettings](/powershell/module/teams/set-csusercallingsettings)
- [New-CsUserCallingDelegate](/powershell/module/teams/new-csusercallingdelegate)
- [Set-CsUserCallingDelegate](/powershell/module/teams/set-csusercallingdelegate)
- [Remove-CsUserCallingDelegate](/powershell/module/teams/remove-csusercallingdelegate)
