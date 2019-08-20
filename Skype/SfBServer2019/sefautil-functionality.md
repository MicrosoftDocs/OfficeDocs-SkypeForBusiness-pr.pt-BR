---
title: Suporte para o uso da funcionalidade SEFAUtil no PowerShell no Skype for Business Server 2019
ms.reviewer: rogupta
ms.author: heidip
author: MicrosoftHeidi
manager: serdars
ms.date: 07/22/2019
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
description: 'Resumo: saiba como usar o PowerShell para obter a funcionalidade do SEFAUtil no Skype for Business Server 2019 depois de instalar a atualização cumulativa 1.'
ms.openlocfilehash: 6e0f7fc8e4bbb25564faa8107dec81ae3887b360
ms.sourcegitcommit: b914c044c43ff8147f35eea684fec1de01a7bcd2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/19/2019
ms.locfileid: "36464542"
---
# <a name="using-sefautil-functionality-via-powershell-in-skype-for-business-server-2019"></a>Usando a funcionalidade do SEFAUtil pelo PowerShell no Skype for Business Server 2019

SEFAUtil (ativação de recurso de extensão secundária) permite que os administradores do Skype for Business Server e do helpdesk configurem as configurações de toque, encaminhamento de chamadas e recebimento de chamadas em grupo em nome de um usuário do Skype for Business Server. Essa ferramenta também permite aos administradores consultar as configurações de roteamento de chamadas publicadas para determinado usuário. Depois de instalar a atualização cumulativa do Skype for Business Server 2019 de julho, as seguintes funcionalidades que podem ser gerenciadas apenas por meio do SEFAUtil também poderão ser gerenciadas pelo PowerShell:

- [Configurações de encaminhamento de chamadas](#call-forwarding-settings)
- [Configurações de delegação](#delegation-settings)
- [Membros da equipe e configurações relacionadas](#team-members-and-related-settings)

## <a name="call-forwarding-settings"></a>Configurações de encaminhamento de chamadas

Os administradores podem alterar as configurações de encaminhamento de chamadas usando o seguinte cmdlet no PowerShell:

- `Get-CsUserForwardingSettings -Identity <UserIdParameter>`

Esse cmdlet retorna as configurações de encaminhamento de chamadas do usuário especificado como um objeto e exibe o mesmo na tela.

- `Set-CsUserForwardingSettings -Identity <UserIdParameter> [Param1 <Value>] [Param2 <Value>]…`

Esse cmdlet modifica as configurações de encaminhamento de chamadas do usuário especificado. Esse cmdlet retorna as configurações de encaminhamento de chamadas do usuário especificado como um objeto e exibe o mesmo na tela, em caso de sucesso. Em caso de falha, será mostrada uma mensagem de erro adequada.

- `Set-CsUserForwardingSettings [-Identity] <UserIdParameter> -DisableForwarding  [-UnansweredToVoicemail] [-UnansweredWaitTime <TimeSpan>] [-SettingsActiveWorkHours]`
- `Set-CsUserForwardingSettings [-Identity] <UserIdParameter> -DisableForwarding  [-UnansweredToOther <String>] [-UnansweredWaitTime <TimeSpan>] [-SettingsActiveWorkHours]`

Este cmdlet desabilita as configurações de encaminhamento de chamadas do usuário (mostramos dois exemplos de parâmetros diferentes aqui).

- `Set-CsUserForwardingSettings [-Identity] <UserIdParameter> -EnableForwarding <String> [-Delegates <PSListModifier>] [-DelegateRingWaitTime <TimeSpan>] [-SettingsActiveWorkHours]`

Esse cmdlet modifica as configurações de encaminhamento de chamadas do usuário.

- `Set-CsUserForwardingSettings [-Identity] <UserIdParameter> -EnableSimulRing <String> [-UnansweredToVoicemail]  [-UnansweredWaitTime <TimeSpan>] [-Delegates <PSListModifier>] [-Team <PSListModifier>] [-TeamDelegateRingWaitTime <TimeSpan>] [-SettingsActiveWorkHours]`
- `Set-CsUserForwardingSettings [-Identity] <UserIdParameter> -EnableSimulRing <String> [-UnansweredToOther <String>] [-UnansweredWaitTime <TimeSpan>] [-Delegates <PSListModifier>]  [-Team <PSListModifier>]  [-TeamDelegateRingWaitTime <TimeSpan>]  [-SettingsActiveWorkHours]`

Esse cmdlet modifica as configurações de SimulRing (novamente, com dois exemplos de parâmetro, um para não ser respondido ao correio de voz e o segundo não ser respondido a outro).

## <a name="delegation-settings"></a>Configurações de delegação

Os administradores podem alterar as configurações de delegação usando o seguinte cmdlet no PowerShell:

- `Get-CsuserDelegates -Identity <UserIdParameter>`

Esse cmdlet retorna um objeto da lista de representantes e exibe a lista de representantes do usuário especificado em caso de sucesso. Em caso de falha, será mostrada uma mensagem de erro adequada.

- `Set-CsUserDelegates -Identity <UserIdParameter> [-Delegates <PSListModifier>]`

Esse cmdlet modifica as configurações de delegação do usuário especificado, retorna um objeto da lista de representantes e exibe a lista de representantes, em caso de sucesso. Em caso de falha, será mostrada uma mensagem de erro adequada. 

- `Set-CsUserDelegates -Identity <UserIdParameter> [-Delegates @{add=[list]}] [-Delegates @{remove=[list]}]`

Esse cmdlet adiciona ou remove um representante.

- `Set-CsUserDelegates -Identity <UserIdParameter> [-Delegates @{replace=[list]}]`

Esse cmdlet define uma lista de representantes para delegados específicos.

## <a name="team-members-and-related-settings"></a>Membros da equipe e configurações relacionadas

Os administradores podem alterar os membros da equipe e as configurações relacionadas usando o seguinte cmdlet no PowerShell:

- `Get-CsUserTeamMembers -Identity <UserIdParameter>`

Esse cmdlet retorna um objeto que contém a lista de membros da equipe e exibe o objeto na tela, em caso de sucesso. Em caso de falha, será mostrada uma mensagem de erro adequada.

- `Set-CsUserTeamMembers -Identity <UserIdParameter> [-Team <PSListModifier>]`

Esse cmdlet modifica a lista de membros da equipe do usuário especificado, retorna um objeto que contém a lista de membros da equipe e exibe o objeto na tela, em caso de sucesso. Em caso de falha, será mostrada uma mensagem de erro adequada.

- `Set-CsUserTeamMembers -Identity <UserIdParameter> [-Team @{add=[list]}] [-Team @{remove=[list]}]`

Esse cmdlet adiciona ou remove os membros da equipe.

- `Set-CsUserTeamMembers -Identity <UserIdParameter> [-Team @{replace=[list]}]`

Esse cmdlet define uma lista de equipe para membros específicos.

## <a name="more-information"></a>Mais informações

Para implantações locais, os cmdlets introduzidos nesse recurso podem ser executados apenas por membros dos grupos a seguir, de acordo com o nível de acesso especificado abaixo:

- CsAdministrator – obter e definir para todos os cmdlets
- CsVoiceAdministrator-obter e definir para todos os cmdlets
- CsHelpDesk-obter todos os cmdlets

Para obter mais informações sobre essas funções de administrador, consulte [criar administradores do painel de controle do Skype for Business Server](../SfbServer/help-topics/help-depwiz/create-skype-for-business-server-control-panel-administrators.md). O administrador pode acessar esses cmdlets conectando-se direta ou remotamente a um computador servidor.
Para uma implantação híbrida, os administradores do Skype for Business devem poder chamar get e Set para todos os cmdlets. Para obter mais informações sobre a lista completa de funções, consulte [sobre as funções de administrador do Office 365](https://docs.microsoft.com/en-us/office365/admin/add-users/about-admin-roles)

> [!NOTE]
> A descoberta automática do servidor deve estar habilitada. Nenhum requisito de licenciamento adicional será introduzido para uso dos cmdlets.
