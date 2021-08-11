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
description: 'Resumo: saiba como usar o PowerShell para obter a funcionalidade SEFAUtil no Skype for Business Server 2019 após a instalação da Atualização Cumulativa 1.'
ms.openlocfilehash: afb0c34afedde91bac40ee90b155809ed3c2b557d88608028b77e0835eb9661d
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2021
ms.locfileid: "54277616"
---
# <a name="using-sefautil-functionality-via-powershell-in-skype-for-business-server-2019"></a>Usando a funcionalidade SEFAUtil por meio do PowerShell no Skype for Business Server 2019

SEFAUtil (Ativação de Recurso de Extensão Secundária) permite que os administradores e agentes auxiliares do Skype for Business Server configurem as configurações de toque de representante, encaminhamento de chamada e Retirada de Chamada de Grupo em nome de um usuário Skype for Business Server. Essa ferramenta também permite que os administradores consultem as configurações de roteamento de chamadas publicadas para um usuário específico. Depois de instalar a atualização cumulativa Skype for Business Server 2019 de julho de 2019, a seguinte funcionalidade que pode ser gerenciada atualmente apenas por meio do SEFAUtil também será gerenciável por meio do PowerShell:

- [Configurações de encaminhamento de chamada](#call-forwarding-settings)
- [Configurações de delegação](#delegation-settings)
- [Membros da equipe e configurações relacionadas](#team-members-and-related-settings)

## <a name="call-forwarding-settings"></a>Configurações de encaminhamento de chamada

Os administradores podem alterar as configurações de encaminhamento de chamada usando o seguinte cmdlet no PowerShell:

- `Get-CsUserCallForwardingSettings -Identity <UserIdParameter>`

Este cmdlet retorna as configurações de encaminhamento de chamada do usuário especificado como um objeto e exibe o mesmo na tela.

- `Set-CsUserCallForwardingSettings -Identity <UserIdParameter> [Param1 <Value>] [Param2 <Value>]…`

Este cmdlet modifica as configurações de encaminhamento de chamada do usuário especificado. Este cmdlet retorna as configurações de encaminhamento de chamada do usuário especificado como um objeto e exibe o mesmo na tela, em caso de sucesso. Em caso de falha, uma mensagem de erro apropriada será mostrada.

- `Set-CsUserCallForwardingSettings [-Identity] <UserIdParameter> -DisableForwarding  [-UnansweredToVoicemail] [-UnansweredWaitTime <TimeSpan>] [-SettingsActiveWorkHours]`
- `Set-CsUserCallForwardingSettings [-Identity] <UserIdParameter> -DisableForwarding  [-UnansweredToOther <String>] [-UnansweredWaitTime <TimeSpan>] [-SettingsActiveWorkHours]`

Esse cmdlet desabilita as configurações de encaminhamento de chamada do usuário (mostramos dois exemplos de parâmetros diferentes aqui).

- `Set-CsUserCallForwardingSettings [-Identity] <UserIdParameter> -EnableForwarding <String> [-Delegates <PSListModifier>] [-DelegateRingWaitTime <TimeSpan>] [-SettingsActiveWorkHours]`

Este cmdlet modifica as configurações de encaminhamento de chamada do usuário.

- `Set-CsUserCallForwardingSettings [-Identity] <UserIdParameter> -EnableSimulRing <String> [-UnansweredToVoicemail]  [-UnansweredWaitTime <TimeSpan>] [-Delegates <PSListModifier>] [-Team <PSListModifier>] [-TeamDelegateRingWaitTime <TimeSpan>] [-SettingsActiveWorkHours]`
- `Set-CsUserCallForwardingSettings [-Identity] <UserIdParameter> -EnableSimulRing <String> [-UnansweredToOther <String>] [-UnansweredWaitTime <TimeSpan>] [-Delegates <PSListModifier>]  [-Team <PSListModifier>]  [-TeamDelegateRingWaitTime <TimeSpan>]  [-SettingsActiveWorkHours]`

Este cmdlet modifica as configurações de anel simultâneo (novamente, com dois exemplos de parâmetro, um para não responder à caixa postal e o segundo sem resposta para outro).

## <a name="delegation-settings"></a>Configurações de delegação

Os administradores podem alterar as configurações de delegação usando o seguinte cmdlet no PowerShell:

- `Get-CsuserDelegates -Identity <UserIdParameter>`

Este cmdlet retorna um objeto de lista de representantes e exibe a lista de representantes do usuário especificado, em caso de sucesso. Em caso de falha, uma mensagem de erro apropriada será mostrada.

- `Set-CsUserDelegates -Identity <UserIdParameter> [-Delegates <PSListModifier>]`

Este cmdlet modifica as configurações de delegação do usuário especificado, retorna um objeto de lista de representantes e exibe a lista de representantes, em caso de êxito. Em caso de falha, uma mensagem de erro apropriada será mostrada. 

- `Set-CsUserDelegates -Identity <UserIdParameter> [-Delegates @{add=[list]}] [-Delegates @{remove=[list]}]`

Este cmdlet adiciona ou remove um representante.

- `Set-CsUserDelegates -Identity <UserIdParameter> [-Delegates @{replace=[list]}]`

Este cmdlet define uma lista de representantes para representantes específicos.

## <a name="team-members-and-related-settings"></a>Membros da equipe e configurações relacionadas

Os administradores podem alterar os membros da equipe e as configurações relacionadas usando o seguinte cmdlet no PowerShell:

- `Get-CsUserTeamMembers -Identity <UserIdParameter>`

Este cmdlet retorna um objeto que contém a lista de membros da equipe e exibe o objeto na tela, em caso de sucesso. Em caso de falha, uma mensagem de erro apropriada será mostrada.

- `Set-CsUserTeamMembers -Identity <UserIdParameter> [-Team <PSListModifier>]`

Este cmdlet modifica a lista de membros da equipe do usuário especificado, retorna um objeto que contém a lista de membros da equipe e exibe o objeto na tela, em caso de sucesso. Em caso de falha, uma mensagem de erro apropriada será mostrada.

- `Set-CsUserTeamMembers -Identity <UserIdParameter> [-Team @{add=[list]}] [-Team @{remove=[list]}]`

Este cmdlet adiciona ou remove membros da equipe.

- `Set-CsUserTeamMembers -Identity <UserIdParameter> [-Team @{replace=[list]}]`

Este cmdlet define uma lista de equipe para membros específicos.

## <a name="more-information"></a>Mais informações

Para implantações locais, os cmdlets introduzidos neste recurso só podem ser executados por membros dos seguintes grupos, de acordo com o nível de acesso especificado abaixo:

- CsAdministrator – Obter e Definir para todos os cmdlets
- CsVoiceAdministrator - Obter e Definir para todos os cmdlets
- CsHelpDesk - Obter para todos os cmdlets

Para obter mais informações sobre essas funções de administrador, consulte [Create Skype for Business Server Control Panel Administrators](../SfbServer/help-topics/help-depwiz/create-skype-for-business-server-control-panel-administrators.md). O administrador pode acessar esses cmdlets fazendo logon diretamente ou remotamente em um computador servidor.
Para uma implantação híbrida, Skype for Business administradores devem ser capazes de chamar Get and Set para todos os cmdlets. Para obter mais informações sobre a lista completa de funções, consulte [Sobre funções de administrador](/microsoft-365/admin/add-users/about-admin-roles).

> [!NOTE]
> A descoberta automática do servidor deve estar habilitada. Nenhum requisito adicional de licenciamento será introduzido para uso dos cmdlets.
