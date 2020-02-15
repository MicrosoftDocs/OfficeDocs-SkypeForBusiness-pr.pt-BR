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
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
description: 'Resumo: saiba como usar o PowerShell para obter a funcionalidade do SEFAUtil no Skype for Business Server 2019 depois de instalar a atualização cumulativa 1.'
ms.openlocfilehash: 1a18a954e40ba7a0c72e4d87b4b3c943e827f2a1
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42049133"
---
# <a name="using-sefautil-functionality-via-powershell-in-skype-for-business-server-2019"></a>Usando a funcionalidade do SEFAUtil por meio do PowerShell no Skype for Business Server 2019

SEFAUtil (ativação de recurso de extensão secundária) permite que os administradores do Skype for Business Server e os agentes de assistência técnica configurem as configurações de separação de chamada, encaminhamento de chamada e de grupo em nome de um usuário do Skype for Business Server. Essa ferramenta também permite que os administradores consultem as configurações de roteamento de chamadas publicadas para um usuário específico. Após a instalação da atualização cumulativa de julho do Skype for Business Server 2019, as seguintes funcionalidades que podem ser gerenciadas apenas por meio do SEFAUtil também poderão ser gerenciadas por meio do PowerShell:

- [Configurações de encaminhamento de chamadas](#call-forwarding-settings)
- [Configurações de delegação](#delegation-settings)
- [Membros da equipe e configurações relacionadas](#team-members-and-related-settings)

## <a name="call-forwarding-settings"></a>Configurações de encaminhamento de chamadas

Os administradores podem alterar as configurações de encaminhamento de chamadas usando o seguinte cmdlet no PowerShell:

- `Get-CsUserCallForwardingSettings -Identity <UserIdParameter>`

Este cmdlet retorna as configurações de encaminhamento de chamadas do usuário especificado como um objeto e exibe o mesmo na tela.

- `Set-CsUserCallForwardingSettings -Identity <UserIdParameter> [Param1 <Value>] [Param2 <Value>]…`

Este cmdlet modifica as configurações de encaminhamento de chamadas do usuário especificado. Este cmdlet retorna as configurações de encaminhamento de chamadas do usuário especificado como um objeto e exibe o mesmo na tela, em caso de êxito. No caso de falha, uma mensagem de erro apropriada será mostrada.

- `Set-CsUserCallForwardingSettings [-Identity] <UserIdParameter> -DisableForwarding  [-UnansweredToVoicemail] [-UnansweredWaitTime <TimeSpan>] [-SettingsActiveWorkHours]`
- `Set-CsUserCallForwardingSettings [-Identity] <UserIdParameter> -DisableForwarding  [-UnansweredToOther <String>] [-UnansweredWaitTime <TimeSpan>] [-SettingsActiveWorkHours]`

Este cmdlet desabilita as configurações de encaminhamento de chamadas do usuário (mostramos dois exemplos de parâmetros diferentes aqui).

- `Set-CsUserCallForwardingSettings [-Identity] <UserIdParameter> -EnableForwarding <String> [-Delegates <PSListModifier>] [-DelegateRingWaitTime <TimeSpan>] [-SettingsActiveWorkHours]`

Este cmdlet modifica as configurações de encaminhamento de chamadas do usuário.

- `Set-CsUserCallForwardingSettings [-Identity] <UserIdParameter> -EnableSimulRing <String> [-UnansweredToVoicemail]  [-UnansweredWaitTime <TimeSpan>] [-Delegates <PSListModifier>] [-Team <PSListModifier>] [-TeamDelegateRingWaitTime <TimeSpan>] [-SettingsActiveWorkHours]`
- `Set-CsUserCallForwardingSettings [-Identity] <UserIdParameter> -EnableSimulRing <String> [-UnansweredToOther <String>] [-UnansweredWaitTime <TimeSpan>] [-Delegates <PSListModifier>]  [-Team <PSListModifier>]  [-TeamDelegateRingWaitTime <TimeSpan>]  [-SettingsActiveWorkHours]`

Este cmdlet modifica as configurações de toque simultâneo (novamente, com dois exemplos de parâmetro, um para não responder à caixa postal e o segundo que não está respondendo a outros).

## <a name="delegation-settings"></a>Configurações de delegação

Os administradores podem alterar as configurações de delegação usando o seguinte cmdlet no PowerShell:

- `Get-CsuserDelegates -Identity <UserIdParameter>`

Este cmdlet retorna um objeto da lista de representantes e exibe a lista de representante do usuário especificado, em caso de êxito. No caso de falha, uma mensagem de erro apropriada será mostrada.

- `Set-CsUserDelegates -Identity <UserIdParameter> [-Delegates <PSListModifier>]`

Este cmdlet modifica as configurações de delegação do usuário especificado, retorna um objeto da lista de representantes e exibe a lista de representantes, em caso de êxito. No caso de falha, uma mensagem de erro apropriada será mostrada. 

- `Set-CsUserDelegates -Identity <UserIdParameter> [-Delegates @{add=[list]}] [-Delegates @{remove=[list]}]`

Este cmdlet adiciona ou remove um representante.

- `Set-CsUserDelegates -Identity <UserIdParameter> [-Delegates @{replace=[list]}]`

Este cmdlet define uma lista de representantes para delegados específicos.

## <a name="team-members-and-related-settings"></a>Membros da equipe e configurações relacionadas

Os administradores podem alterar os membros da equipe e as configurações relacionadas usando o seguinte cmdlet no PowerShell:

- `Get-CsUserTeamMembers -Identity <UserIdParameter>`

Este cmdlet retorna um objeto que contém uma lista de membros da equipe e exibe o objeto na tela, em caso de êxito. No caso de falha, uma mensagem de erro apropriada será mostrada.

- `Set-CsUserTeamMembers -Identity <UserIdParameter> [-Team <PSListModifier>]`

Este cmdlet modifica a lista de membros da equipe do usuário especificado, retorna um objeto que contém a lista de membros da equipe e exibe o objeto na tela, em caso de êxito. No caso de falha, uma mensagem de erro apropriada será mostrada.

- `Set-CsUserTeamMembers -Identity <UserIdParameter> [-Team @{add=[list]}] [-Team @{remove=[list]}]`

Este cmdlet adiciona ou remove membros da equipe.

- `Set-CsUserTeamMembers -Identity <UserIdParameter> [-Team @{replace=[list]}]`

Este cmdlet define uma lista de equipes para membros específicos.

## <a name="more-information"></a>Mais informações

Para implantações locais, os cmdlets introduzidos neste recurso só podem ser executados por membros dos seguintes grupos, conforme o nível de acesso especificado abaixo:

- CsAdministrator – obter e definir para todos os cmdlets
- CsVoiceAdministrator-Get e Set para todos os cmdlets
- CsHelpDesk-obter todos os cmdlets

Para obter mais informações sobre essas funções de administrador, consulte [criar administradores do painel de controle do Skype for Business Server](../SfbServer/help-topics/help-depwiz/create-skype-for-business-server-control-panel-administrators.md). O administrador pode acessar esses cmdlets de modo direto ou remoto fazendo logon em um computador servidor.
Para uma implantação híbrida, os administradores do Skype for Business devem ser capazes de chamar get e Set para todos os cmdlets. Para obter mais informações sobre a lista completa de funções, consulte [sobre as funções de administrador do Office 365](https://docs.microsoft.com/office365/admin/add-users/about-admin-roles)

> [!NOTE]
> A descoberta automática do servidor deve estar habilitada. Nenhum requisito adicional de licenciamento será introduzido para uso dos cmdlets.
