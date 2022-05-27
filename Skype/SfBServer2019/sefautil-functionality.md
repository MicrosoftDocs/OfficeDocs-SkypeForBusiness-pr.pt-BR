---
title: Suporte para o uso da funcionalidade SEFAUtil no Skype PowerShell no Skype for Business Server 2019
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
ms.localizationpriority: medium
ms.collection: IT_Skype16
description: 'Resumo: saiba como usar o PowerShell para obter a funcionalidade SEFAUtil no Skype for Business Server 2019 após a instalação da Atualização Cumulativa 1.'
ms.openlocfilehash: 07d05ef1687fa9ca14f7e90108ae8b5c0e7e3bb9
ms.sourcegitcommit: 296862e02b548f0212c9c70504e65b467d459cc3
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/25/2022
ms.locfileid: "65676533"
---
# <a name="using-sefautil-functionality-via-powershell-in-skype-for-business-server-2019"></a>Usando a funcionalidade SEFAUtil por meio do PowerShell Skype for Business Server 2019

O SEFAUtil (Ativação de Recursos de Extensão Secundária) permite que administradores e agentes de suporte ajuda do Skype for Business Server configurem configurações de toque de representante, encaminhamento de chamadas e Recebimento de Chamadas em Grupo em nome de Skype for Business Server usuários. O SEFAUtil também permite que os administradores consultem as configurações de roteamento de chamadas para um usuário específico.

Depois de instalar a atualização cumulativa de julho de 2019 do Skype for Business Server 2019, a seguinte funcionalidade disponível somente por meio do SEFAUtil também estará disponível no Skype PowerShell:

- [Configurações de encaminhamento de chamadas](#call-forwarding-settings)
- [Configurações de delegação](#delegation-settings)
- [Membros da equipe e configurações relacionadas](#team-members-and-related-settings)

## <a name="call-forwarding-settings"></a>Configurações de encaminhamento de chamadas

Os administradores podem alterar as configurações de encaminhamento de chamadas usando os seguintes comandos no PowerShell:

```powershell
Get-CsUserCallForwardingSettings -Identity <UserIdParameter>
```

Esse comando retorna as configurações de encaminhamento de chamadas do usuário especificado como um objeto e exibe o mesmo na tela.

```powershell
Set-CsUserCallForwardingSettings -Identity <UserIdParameter> [Param1 <Value>] [Param2 <Value>]...
```

Esse comando modifica as configurações de encaminhamento de chamadas do usuário especificado. Esse comando retorna as configurações de encaminhamento de chamadas do usuário especificado como um objeto e exibe o mesmo na tela. Se o comando não for bem-sucedido, uma mensagem de erro apropriada será mostrada.

```powershell
Set-CsUserCallForwardingSettings [-Identity] <UserIdParameter> -DisableForwarding  [-UnansweredToVoicemail] [-UnansweredWaitTime <TimeSpan>] [-SettingsActiveWorkHours]
```

```powershell
Set-CsUserCallForwardingSettings [-Identity] <UserIdParameter> -DisableForwarding  [-UnansweredToOther <String>] [-UnansweredWaitTime <TimeSpan>] [-SettingsActiveWorkHours]
```

Esse comando desabilita as configurações de encaminhamento de chamadas do usuário (mostramos dois exemplos de parâmetros diferentes aqui).

```powershell
Set-CsUserCallForwardingSettings [-Identity] <UserIdParameter> -EnableForwarding <String> [-Delegates <PSListModifier>] [-DelegateRingWaitTime <TimeSpan>] [-SettingsActiveWorkHours]
```

Esse comando modifica as configurações de encaminhamento de chamadas do usuário.

```powershell
Set-CsUserCallForwardingSettings [-Identity] <UserIdParameter> -EnableSimulRing <String> [-UnansweredToVoicemail]  [-UnansweredWaitTime <TimeSpan>] [-Delegates <PSListModifier>] [-Team <PSListModifier>] [-TeamDelegateRingWaitTime <TimeSpan>] [-SettingsActiveWorkHours]
```

```powershell
Set-CsUserCallForwardingSettings [-Identity] <UserIdParameter> -EnableSimulRing <String> [-UnansweredToOther <String>] [-UnansweredWaitTime <TimeSpan>] [-Delegates <PSListModifier>]  [-Team <PSListModifier>]  [-TeamDelegateRingWaitTime <TimeSpan>]  [-SettingsActiveWorkHours]
```

Esse comando modifica as configurações simultâneas de anel (novamente, com dois exemplos de parâmetro, um para não responder à caixa postal e o segundo sem resposta para outro).

## <a name="delegation-settings"></a>Configurações de delegação

Os administradores podem alterar as configurações de delegação usando o seguinte comando no PowerShell:

```powershell
Get-CsuserDelegates -Identity <UserIdParameter>
```

Esse comando retorna um objeto de lista de delegados e exibe a lista de representantes do usuário especificado. Se o comando não for bem-sucedido, uma mensagem de erro apropriada será mostrada.

```powershell
Set-CsUserDelegates -Identity <UserIdParameter> [-Delegates <PSListModifier>]
```

Esse comando modifica as configurações de delegação do usuário especificado, retorna um objeto de lista de delegados e exibe a lista de delegados. Se o comando não for bem-sucedido, uma mensagem de erro apropriada será mostrada.

```powershell
Set-CsUserDelegates -Identity <UserIdParameter> [-Delegates @{add=[list]}] [-Delegates @{remove=[list]}]
```

Esse comando adiciona ou remove um delegado.

```powershell
Set-CsUserDelegates -Identity <UserIdParameter> [-Delegates @{replace=[list]}]
```

Esse comando define uma lista de delegados para delegados específicos.

## <a name="team-members-and-related-settings"></a>Membros da equipe e configurações relacionadas

Os administradores podem alterar os membros da equipe e as configurações relacionadas usando o seguinte comando no PowerShell:

```powershell
Get-CsUserTeamMembers -Identity <UserIdParameter>
```

Esse comando retorna um objeto que contém a lista de membros da equipe e exibe o objeto na tela. Se o comando não for bem-sucedido, uma mensagem de erro apropriada será mostrada.

```powershell
Set-CsUserTeamMembers -Identity <UserIdParameter> [-Team <PSListModifier>]
```

Esse comando modifica a lista de membros da equipe do usuário especificado, retorna um objeto que contém a lista de membros da equipe e exibe o objeto na tela. Se o comando não for bem-sucedido, uma mensagem de erro apropriada será mostrada.

```powershell
Set-CsUserTeamMembers -Identity <UserIdParameter> [-Team @{add=[list]}] [-Team @{remove=[list]}]
```

Esse comando adiciona ou remove membros da equipe.

```powershell
Set-CsUserTeamMembers -Identity <UserIdParameter> [-Team @{replace=[list]}]
```

Esse comando define uma lista de equipe para membros específicos.

## <a name="more-information"></a>Mais informações

Para implantações locais, os cmdlets introduzidos nesse recurso só podem ser executados por membros dos seguintes grupos, de acordo com o nível de acesso especificado abaixo:

- CsAdministrator – Obter e definir para todos os cmdlets
- CsVoiceAdministrator – Obter e definir para todos os cmdlets
- CsHelpDesk – Obter para todos os cmdlets

Para obter mais informações sobre essas funções de administrador, consulte [Criar Skype for Business Server Painel de Controle Administradores](../SfbServer/help-topics/help-depwiz/create-skype-for-business-server-control-panel-administrators.md). O administrador pode acessar esses cmdlets fazendo logon diretamente ou remotamente em um computador servidor.
Para uma implantação híbrida, Skype for Business administradores devem ser capazes de chamar Get e Set para todos os cmdlets. Para obter mais informações sobre a lista completa de funções, consulte [Sobre funções de administrador](/microsoft-365/admin/add-users/about-admin-roles).

> [!NOTE]
> A descoberta automática do servidor deve estar habilitada. Nenhum requisito de licenciamento adicional será introduzido para uso dos cmdlets.
