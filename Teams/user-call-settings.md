---
title: Configurar configurações de chamada para usuários
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
- m365initiative-voice
audience: Admin
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.callqueues.overview"
- Phone System - seo-marvel-apr2020
description: Saiba como configurar as configurações do usuário para encaminhamento de chamada e delegação.
ms.openlocfilehash: 5443ad958d23753b1d67d42782ddab41d9d6d080
ms.sourcegitcommit: ff975c21725e1812e6db8fc9fe37de1362f168c3
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/11/2022
ms.locfileid: "63689043"
---
# <a name="configure-call-settings-for-your-users"></a>Configurar configurações de chamada para seus usuários

Este artigo descreve como você, o administrador, pode alterar as configurações de encaminhamento e delegação de chamada para seus usuários. Talvez você queira alterar essas configurações, por exemplo, se:

- Um usuário está de licença por doença e você precisa garantir que as chamadas de entrada para o usuário sejam encaminhadas para um colega.

- Você precisa inspecionar as configurações de encaminhamento de chamada para todos os usuários em um departamento e, potencialmente, corrigi-las conforme apropriado.

- Um novo assistente foi empregado e você precisa adicionar o assistente como representante para um grupo de funcionários.

Você pode usar Teams centro de administração ou Teams cmdlets do PowerShell para exibir e alterar configurações de chamada para usuários.

Para definir configurações de chamada para um usuário, o usuário deve ter uma licença Telefone Microsoft Sistema atribuída.

## <a name="use-the-teams-admin-center"></a>Usar o Teams de administração

Você pode usar o Teams de administração para configurar a delegação de chamada e retirada de chamada de grupo para seus usuários. 

> [!NOTE]
> A opção para configurar configurações de encaminhamento de chamada não está disponível no Teams de administração.

Para configurar o atendimento de chamada de grupo:

1. No centro Teams de administração, acesse **UsersManage**  >  users e selecione um usuário.

2. Na página detalhes do usuário, vá para a **guia Voz** .

3. Em **Retirada de chamada de grupo**, selecione **Adicionar pessoas**. 

4. Especifique configurações para **atraso e ordem de chamada**.

Para configurar a delegação, na mesma página, acesse Delegação **de chamada** e selecione **Adicionar pessoas**.

## <a name="use-powershell"></a>Usar o PowerShell

Você pode usar o PowerShell para configurar configurações de encaminhamento de chamada e delegação para seus usuários.  Você usará os seguintes cmdlets, que estão disponíveis no módulo Teams PowerShell versão 4.0 ou posterior:

- [Get-CsUserCallingSettings](/powershell/module/teams/get-csusercallingsettings?view=teams-ps) - mostra configurações de encaminhamento de chamadas, representantes e informações de delegator para um usuário.

- [Set-CsUserCallingSettings](/powershell/module/teams/set-csusercallingsettings?view=teams-ps) - define as configurações de encaminhamento de chamadas para um usuário.

- [New-CsUserCallingDelegate](/powershell/module/teams/new-csusercallingdelegate?view=teams-ps) - adiciona um novo representante com permissões para um usuário.

-   [Set-CsUserCallingDelegate](/powershell/module/teams/set-csusercallingdelegate?view=teams-ps) - altera as permissões de um representante existente.

-   [Remove-CsUserCallingDelegate](/powershell/module/teams/remove-csusercallingdelegate?view=teams-ps) - remove um representante de um usuário.


### <a name="display-call-forward-and-delegation-settings-for-a-user"></a>Exibir configurações de encaminhamento de chamada e delegação para um usuário

Para exibir as configurações atuais de encaminhamento de chamada e delegação para um usuário, use o cmdlet Get-CsUserCallingSettings, conforme mostrado no exemplo a seguir:

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
Delegates                 : Id:user2@contoso.com
Delegators                : 
CallGroupOrder            : InOrder
CallGroupTargets          : {}
GroupMembershipDetails    :
GroupNotificationOverride : Ring

(Get-CsUserCallingSettings -Identity user1@contoso.com).Delegates

Id             : user2@contoso.com
MakeCalls      : True
ManageSettings : True
ReceiveCalls   : True
```

A saída mostra que user1 tem toque simultâneo para representantes configurados. Chamadas não respondidas são enviadas para a caixa postal após 20 segundos. User2 é definido como o representante com todas as permissões de representante.


### <a name="set-call-forward-settings-for-a-user"></a>Definir configurações de encaminhamento de chamada para um usuário

Para encaminhar todas as chamadas de user1 para user2, use o cmdlet Set-CsUserCallingSettings, conforme mostrado no exemplo a seguir: 

```PowerShell
Set-CsUserCallingSettings -Identity user1@contoso.com -IsForwardingEnabled $true -ForwardingType Immediate -ForwardingTargetType SingleTarget -ForwardingTarget user2@contoso.com
```

Para tocar simultaneamente todos os representantes para user3, use o cmdlet Set-CsUserCallingSettings, conforme mostrado no exemplo a seguir: 

```PowerShell
Set-CsUserCallingSettings -Identity user3@contoso.com -IsForwardingEnabled $true -ForwardingType Simultaneous -ForwardingTargetType MyDelegates
```

O exemplo a seguir usa o cmdlet Set-CsUserCallingSettings para configurar um grupo de chamada para user4 com user5 e user6 como membros. Todas as chamadas aos membros do grupo são encaminhadas na ordem em que são definidas: 

```PowerShell
$cgm = @("user5@contoso.com","user6@contoso.com")

Set-CsUserCallingSettings -Identity user4@contoso.com -CallGroupOrder InOrder -CallGroupTargets $cgm

Set-CsUserCallingSettings -Identity user4@contoso.com -IsForwardingEnabled $true -ForwardingType Immediate -ForwardingTargetType Group
```

Para obter mais exemplos, consulte [Set-CsUserCallingSettings](/powershell/module/teams/get-csusercallingsettings?view=teams-ps).

### <a name="add-a-calling-delegate-for-a-user"></a>Adicionar um representante de chamada para um usuário

Para adicionar user2 como representante para user1 com todas as permissões permitidas, use o cmdlet New-CsUserCallingDelegate, conforme mostrado no exemplo a seguir: 

```PowerShell
New-CsUserCallingDelegate -Identity user1@contoso.com -Delegate user2@contoso.com -MakeCalls $true -ReceiveCalls $true -ManageSettings $true
```

### <a name="change-calling-delegate-permissions"></a>Alterar permissões de representante de chamada

Para alterar as permissões de representante, por exemplo, para não permitir que o usuário2 faça chamadas para user1-- use o cmdlet Set-CsUserCallingDelegate como mostrado no exemplo a seguir: 

```PowerShell
Set-CsUserCallingDelegate -Identity user1@contoso.com -Delegate user2@contoso.com -MakeCalls $false
```

### <a name="remove-a-calling-delegate-for-a-user"></a>Remover um representante de chamada para um usuário

Para remover user2 como representante para user1, use o cmdlet Remove-CsUserCallingDelegate, conforme mostrado no exemplo a seguir: 

```PowerShell
Remove-CsUserCallingDelegate -Identity user1@contoso.com -Delegate user2@contoso.com
```


## <a name="related-topics"></a>Tópicos relacionados

- [Get-CsUserCallingSettings](/powershell/module/teams/get-csusercallingsettings?view=teams-ps) 

- [Set-CsUserCallingSettings](/powershell/module/teams/set-csusercallingsettings?view=teams-ps) 

- [New-CsUserCallingDelegate](/powershell/module/teams/new-csusercallingdelegate?view=teams-ps) 

-   [Set-CsUserCallingDelegate](/powershell/module/teams/set-csusercallingdelegate?view=teams-ps) 

-   [Remove-CsUserCallingDelegate](/powershell/module/teams/remove-csusercallingdelegate?view=teams-ps) 
