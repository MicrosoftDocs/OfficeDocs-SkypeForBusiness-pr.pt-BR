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
audience: Admin
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.callqueues.overview
- Phone System
- seo-marvel-apr2020
description: Saiba como configurar as configurações do usuário para encaminhamento e delegação de chamadas.
ms.openlocfilehash: 7d1ab3252461d57a99956c90a011a43620c76bea
ms.sourcegitcommit: 18e66d54a9e349d4516253addc85cc12892c69a3
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/04/2022
ms.locfileid: "68851842"
---
# <a name="configure-call-settings-for-your-users"></a>Configurar configurações de chamada para seus usuários

Este artigo descreve como você, o administrador, pode alterar as configurações de encaminhamento de chamadas e delegação para seus usuários. Talvez você queira alterar essas configurações, por exemplo, se:

- Um usuário está fora de licença médica e você precisa garantir que as chamadas de entrada para o usuário sejam encaminhadas a um colega.
- Você precisa inspecionar as configurações de encaminhamento de chamada para todos os usuários em um departamento e, potencialmente, corrigi-las conforme apropriado.
- Um novo assistente foi empregado e você precisa adicionar o assistente como delegado para um grupo de funcionários.

Você pode usar o centro de administração do Teams ou cmdlets do Teams PowerShell para exibir e alterar as configurações de chamada para os usuários.

Para definir as configurações de chamada para um usuário, o usuário deve ter uma licença atribuída do Sistema de Telefone da Microsoft.

## <a name="use-the-teams-admin-center"></a>Usar o centro de administração do Teams

Você pode usar o centro de administração do Teams para configurar configurações de encaminhamento de chamadas e sem resposta, coleta de chamadas em grupo e delegação de chamadas para seus usuários.

Para configurar configurações imediatas de encaminhamento de chamada:

1. No centro de administração do Teams, acesse **Usuários** > **Gerenciar usuários** e selecione um usuário.

2. Na página de detalhes do usuário, acesse a guia **Voz** .

3. Em **Regras de resposta de chamada**, selecione **Ser encaminhado imediatamente** e selecione o tipo e o destino de encaminhamento de chamada apropriados.

Para configurar o toque simultâneo, na mesma página selecione **Tocar os dispositivos do usuário**. Na lista suspensa **Também permitir** , selecione a configuração de toque simultânea apropriada.

Para configurar configurações sem resposta, na mesma página selecione a configuração apropriada na lista suspensa **Se não for respondida** . No **Anel por tantos segundos antes de redirecionar** a lista suspensa, especifique o número de segundos a serem esperados.

A configuração da delegação de chamadas e da coleta de chamadas em grupo são integradas às configurações de encaminhamento de chamada e sem resposta selecionando o tipo apropriado. Por exemplo, para configurar essas chamadas também deve ligar para os delegados do usuário, na mesma página selecione **Delegação de chamadas** em **Também permitir**. Em seguida, adicione os delegados apropriados selecionando **Adicionar pessoas** e clicando em **Salvar**.

Este vídeo mostra as etapas para exibir e editar as configurações de voz de um usuário.

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE546F7?autoplay=false]

## <a name="use-powershell"></a>Usar o PowerShell

Você pode usar o PowerShell para configurar configurações de encaminhamento de chamadas e delegação para seus usuários.  Você usará os seguintes cmdlets, que estão disponíveis no módulo do Teams PowerShell versão 4.0 ou posterior:

- [Get-CsUserCallingSettings](/powershell/module/teams/get-csusercallingsettings) – mostra as configurações de encaminhamento de chamadas, delegados e informações de delegador para um usuário.
- [Set-CsUserCallingSettings](/powershell/module/teams/set-csusercallingsettings) – define as configurações de encaminhamento de chamadas para um usuário.
- [New-CsUserCallingDelegate](/powershell/module/teams/new-csusercallingdelegate) – adiciona um novo delegado com permissões para um usuário.
- [Set-CsUserCallingDelegate](/powershell/module/teams/set-csusercallingdelegate) – altera as permissões para um delegado existente.
- [Remove-CsUserCallingDelegate](/powershell/module/teams/remove-csusercallingdelegate) – remove um delegado de um usuário.

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

A saída mostra que o user1 tem toque simultâneo para delegados configurados. Chamadas sem resposta são enviadas para a caixa postal após 20 segundos. User2 é definido como o delegado com todas as permissões de delegado.

### <a name="set-call-forward-settings-for-a-user"></a>Definir configurações de encaminhamento de chamada para um usuário

Para encaminhar todas as chamadas para user1 para user2, use o cmdlet Set-CsUserCallingSettings, conforme mostrado no exemplo a seguir:

```PowerShell
Set-CsUserCallingSettings -Identity user1@contoso.com -IsForwardingEnabled $true -ForwardingType Immediate -ForwardingTargetType SingleTarget -ForwardingTarget user2@contoso.com
```

Para ligar simultaneamente para todos os delegados do user3, use o cmdlet Set-CsUserCallingSettings, conforme mostrado no exemplo a seguir:

```PowerShell
Set-CsUserCallingSettings -Identity user3@contoso.com -IsForwardingEnabled $true -ForwardingType Simultaneous -ForwardingTargetType MyDelegates
```

O exemplo a seguir usa o cmdlet Set-CsUserCallingSettings para configurar um grupo de chamadas para user4 com user5 e user6 como membros. Todas as chamadas para os membros do grupo são encaminhadas na ordem em que são definidas:

```PowerShell
$cgm = @("user5@contoso.com","user6@contoso.com")

Set-CsUserCallingSettings -Identity user4@contoso.com -CallGroupOrder InOrder -CallGroupTargets $cgm

Set-CsUserCallingSettings -Identity user4@contoso.com -IsForwardingEnabled $true -ForwardingType Immediate -ForwardingTargetType Group
```

Para obter mais exemplos, consulte [Set-CsUserCallingSettings](/powershell/module/teams/get-csusercallingsettings).

### <a name="add-a-calling-delegate-for-a-user"></a>Adicionar um delegado de chamada para um usuário

Para adicionar o user2 como delegado para user1 com todas as permissões permitidas, use o cmdlet New-CsUserCallingDelegate, conforme mostrado no exemplo a seguir:

```PowerShell
New-CsUserCallingDelegate -Identity user1@contoso.com -Delegate user2@contoso.com -MakeCalls $true -ReceiveCalls $true -ManageSettings $true
```

### <a name="change-calling-delegate-permissions"></a>Alterar permissões de delegado de chamada

Para alterar as permissões de delegado , por exemplo, para não permitir que o usuário2 faça chamadas para user1 - use o cmdlet Set-CsUserCallingDelegate, conforme mostrado no exemplo a seguir:

```PowerShell
Set-CsUserCallingDelegate -Identity user1@contoso.com -Delegate user2@contoso.com -MakeCalls $false
```

### <a name="remove-a-calling-delegate-for-a-user"></a>Remover um delegado de chamada para um usuário

Para remover o usuário2 como um delegado para user1, use o cmdlet Remove-CsUserCallingDelegate, conforme mostrado no exemplo a seguir:

```PowerShell
Remove-CsUserCallingDelegate -Identity user1@contoso.com -Delegate user2@contoso.com
```

## <a name="additional-notes"></a>Notas adicionais

- O comportamento padrão de um usuário que nunca teve as regras de resposta de chamada modificadas, seja pelo usuário ou por um administrador do Locatário, é que as chamadas sem resposta serão encaminhadas para a caixa postal após 30 segundos. As configurações exibidas para o usuário no Team Administração Center ou no Teams PowerShell mostrarão o destino sem resposta como nenhum e o atraso de 20 segundos.

## <a name="related-topics"></a>Tópicos relacionados

- [Get-CsUserCallingSettings](/powershell/module/teams/get-csusercallingsettings)
- [Set-CsUserCallingSettings](/powershell/module/teams/set-csusercallingsettings)
- [New-CsUserCallingDelegate](/powershell/module/teams/new-csusercallingdelegate)
- [Set-CsUserCallingDelegate](/powershell/module/teams/set-csusercallingdelegate)
- [Remove-CsUserCallingDelegate](/powershell/module/teams/remove-csusercallingdelegate)
