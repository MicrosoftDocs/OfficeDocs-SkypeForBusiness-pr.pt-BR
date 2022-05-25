---
title: Bloquear chamadas de entrada no Skype for Business Online
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
audience: Admin
ms.reviewer: roykuntz
appliesto:
- Skype for Business
ms.localizationpriority: medium
ms.custom: Learn how to use PowerShell to manage inbound call blocking in Skype for Business Online.
description: Os administradores podem aprender a bloquear chamadas de entrada no Skype for Business Online.
ms.openlocfilehash: 40b43f669ededf7ac334c25c79b5af09140c075d
ms.sourcegitcommit: c53c22069b1babce7a2364de631057ff501ca1c0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/25/2022
ms.locfileid: "65671647"
---
# <a name="block-inbound-calls"></a>Bloquear chamadas de entrada

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

Skype for Business Planos de Chamadas Online agora dá suporte ao bloqueio de chamadas de entrada da rede telefônica pública comunada (PSTN). Esse recurso permite que uma lista global de padrões de número de locatário seja definida para que a ID do chamador de cada chamada PSTN de entrada para o locatário possa ser verificada na lista quanto a uma correspondência. Se uma correspondência for feita, uma chamada de entrada será rejeitada.

Esse recurso de bloqueio de chamada de entrada só funciona em chamadas de entrada originadas do PSTN e só funciona em uma base global do locatário. Ele não está disponível por usuário.

Esse recurso ainda não está disponível para Roteamento Direto.

>[!NOTE]
> Os chamadores bloqueados podem ter comportamentos ligeiramente diferentes quando foram bloqueados. O comportamento se baseia em como a operadora do chamador bloqueado manipula a notificação de que a chamada não tem permissão para ser concluída com êxito. Os exemplos podem incluir uma mensagem da operadora informando que a chamada não pode ser concluída como discada ou simplesmente descartando a chamada.

## <a name="call-blocking-admin-controls-and-information"></a>Informações e controles de administrador de bloqueio de chamadas

Administração controles para números de bloqueio são fornecidos usando apenas o PowerShell. Os padrões de bloco numérico são definidos como padrões de expressão regular. A ordem das expressões não é importante – o primeiro padrão correspondido na lista faz com que a chamada seja bloqueada. Um novo número ou padrão adicionado ou removido na lista de chamadores bloqueados pode levar até 24 horas para que o padrão se torne ativo.

## <a name="call-blocking-powershell-commands"></a>Comandos do PowerShell de bloqueio de chamada

Os padrões de número são gerenciados ```CsInboundBlockedNumberPattern``` por meio ```New```dos comandos ```Get```, ```Set```e ```Remove```. Você pode gerenciar um determinado padrão usando esses cmdlets, incluindo a capacidade de alternar a ativação de um determinado padrão.
- [Get-CsInboundBlockedNumberPattern](/powershell/module/skype/get-csinboundblockednumberpattern) retorna uma lista de todos os padrões de número bloqueado adicionados à lista de locatários, incluindo Nome, Descrição, Habilitado (True/False) e Padrão para cada um.
- [New-CsInboundBlockedNumberPattern](/powershell/module/skype/new-csinboundblockednumberpattern) adiciona um padrão de número bloqueado à lista de locatários.
- [Remove-CsInboundBlockedNumberPattern](/powershell/module/skype/remove-csinboundblockednumberpattern) remove um padrão de número bloqueado da lista de locatários.
- [Set-CsInboundBlockedNumberPattern](/powershell/module/skype/set-csinboundblockednumberpattern) modifica um ou mais parâmetros de um padrão de número bloqueado na lista de locatários.

A exibição e a ativação de todo o recurso de bloqueio de chamada é gerenciada por meio dos ```CsTenantBlockingCallingNumbers``` comandos e ```Get``` ```Set```.

- [Get-CsTenantBlockedCallingNumbers](/powershell/module/skype/get-cstenantblockedcallingnumbers) retorna os parâmetros para a lista de números bloqueados global, incluindo Enabled (True/False). Há uma única política de locatário global que não pode ser modificada manualmente além de ativar ou desativar o recurso.
- [Set-CsTenantBlockedCallingNumbers](/powershell/module/skype/set-cstenantblockedcallingnumbers) permite modificar as chamadas de locatário global bloqueadas para serem ativadas e desativadas no nível do locatário.

### <a name="examples"></a>Exemplos

#### <a name="block-a-number"></a>Bloquear um número

Neste exemplo, os parâmetros ```-Enabled``` e os ```-Description``` parâmetros são opcionais:

```powershell
New-CsInboundBlockedNumberPattern -Name “<name>” -Enabled $True -Description “<description>” -Pattern “^[+]?13125550000”
```

A criação de um novo padrão adiciona o padrão conforme habilitado por padrão. A descrição é um campo opcional para fornecer mais informações.

Recomendamos que você forneça um nome significativo para entender facilmente por que o padrão foi adicionado. No caso de simplesmente bloquear números de spam, considere nomear a regra da mesma forma que o padrão de número que está sendo correspondido e adicione informações adicionais na descrição conforme necessário.

Os padrões são correspondidos usando Expressões Regulares (Regex).
Aguarde a replicação antes de testar e validar.

#### <a name="allow-a-number"></a>Permitir um número

Neste exemplo, o ```-Identity``` parâmetro é necessário:

```powershell
Remove-CsInboundBlockedNumberPattern -Identity “<identity>”
```

Se a identidade não for conhecida, use o ```Get-CsInboundBlockedNumberPattern``` cmdlet para primeiro localizar o padrão adequado e anotar a identidade. Em seguida, execute o ```Remove-CsTenantBlockedNumberPattern``` cmdlet e passe o valor de identidade apropriado.

Aguarde a replicação antes de testar e validar.

#### <a name="view-all-number-patterns"></a>Exibir todos os padrões de número

A execução desse cmdlet retorna uma lista de todos os números bloqueados inseridos para um locatário:

```powershell
Get-CsInboundBlockedNumberPattern
```

Use as capacidades de filtragem internas do PowerShell para analisar os valores retornados conforme necessário.

## <a name="add-number-exceptions"></a>Adicionar exceções de número

Você pode adicionar exceções a padrões de número bloqueados ```CsTenantBlockNumberExceptionPattern``` por meio dos comandos, ```New```, ```Get```e ```Remove``````Set```.

- [New-CsTenantBlockedNumberExceptionPattern](/powershell/module/skype/new-cstenantblockednumberexceptionpattern) adiciona um padrão de exceção de número à lista de locatários.
- [Get-CsTenantBlockedNumberExceptionPattern](/powershell/module/skype/get-cstenantblockednumberexceptionpattern) retorna uma lista de todos os padrões de exceção de número adicionados à lista de locatários.
- [Set-CsTenantBlockedNumberExceptionPattern](/powershell/module/skype/set-cstenantblockednumberexceptionpattern) modifica um ou mais parâmetros para um padrão de exceção de número na lista de locatários.
- [Remove-CsTenantBlockedNumberExceptionPattern](/powershell/module/skype/remove-cstenantblockednumberexceptionpattern) remove um padrão de exceção de número da lista de locatários.

### <a name="examples"></a>Exemplos

#### <a name="add-a-number-exception"></a>Adicionar uma exceção de número

Neste exemplo, um novo padrão de exceção de número é criado e, por padrão, adicionará o padrão conforme habilitado. Os ```-Enabled``` parâmetros ```-Description``` e os parâmetros são opcionais.

```powershell
New-CsTenantBlockedNumberExceptionPattern -Identity <XdsGlobalRelativeIdentity> -Tenant <GUID> -Pattern <String> -Enabled <bool> -Description <string>
```

```powershell
New-CsTenantBlockedNumberExceptionPattern -Identity InternationalPrefix -Tenant daacb588-18ef-4f77-8c83-955af9615930 -Pattern "^011(\d*)$" -Description "Allow international prefix in US"
```

#### <a name="view-all-number-exceptions"></a>Exibir todas as exceções de número

Neste exemplo, o parâmetro -Identity é opcional. Se o ```-Identity``` parâmetro não for especificado, esse cmdlet retornará uma lista de todos os padrões de exceção de número inseridos para um locatário.

```powershell
Get-CsTenantBlockedNumberExceptionPattern -Identity <XdsGlobalRelativeIdentity> -Tenant <GUID>
```

```powershell
Get-CsTenantBlockedNumberExceptionPattern -Tenant daacb588-18ef-4f77-8c83-955af9615930
```

#### <a name="modify-a-number-exception"></a>Modificar uma exceção de número

Neste exemplo, o parâmetro -Identity é obrigatório. O ```Set-CsTenantBlockedNumberExceptionPattern``` cmdlet permite modificar um ou mais parâmetros para uma determinada identidade de padrão de número.

```powershell
Set-CsTenantBlockedNumberExceptionPattern -Identity <XdsGlobalRelativeIdentity> -Tenant <GUID> -Enabled <bool> -Description <string> -Pattern <string>
```

```powershell
Set-CsTenantBlockedNumberExceptionPattern -Identity InternationalPrefix -Tenant daacb588-18ef-4f77-8c83-955af9615930  -Pattern "^022(\d*)$"
```

#### <a name="remove-a-number-exception"></a>Remover uma exceção de número

Neste exemplo, o ```-Identity``` parâmetro é necessário. Esse cmdlet removerá o padrão de número fornecido da lista de locatários.  Se a identidade não for conhecida, use o ```Get-CsInboundBlockedNumberPattern``` cmdlet para primeiro localizar o padrão adequado e anotar a identidade. Em seguida, execute o ```Remove-CsTenantBlockedNumberExceptionPattern``` cmdlet e passe o valor de identidade apropriado. Aguarde a replicação antes de testar e validar.

```powershell
Remove-CsTenantBlockedNumberExceptionPattern -Identity <XdsGlobalRelativeIdentity> -Tenant <GUID>
```

```powershell
Remove-CsTenantBlockedNumberExceptionPattern -Identity InternationalPrefix -Tenant daacb588-18ef-4f77-8c83-955af9615930
```

### <a name="test-whether-a-number-is-blocked"></a>Testar se um número está bloqueado

Use o ```Test-CsInboundBlockedNumberPattern``` cmdlet para verificar se um número está bloqueado no locatário.

Neste exemplo, os parâmetros ```-Phonenumber``` ```-Tenant``` e os parâmetros são necessários. O ```-PhoneNumber``` parâmetro deve ser uma cadeia de caracteres numérica sem caracteres adicionais, como + ou -. No TRPS, o ```-Tenant parameter``` é opcional. O parâmetro resultante ```isNumberBlocked``` retornará um valor true se o número estiver bloqueado no locatário e False se ele não estiver bloqueado.

```powershell
Test-CsInboundBlockedNumberPattern –Tenant <GUID> -PhoneNumber <String>
```

```powershell
Test-CsInboundBlockedNumberPattern -Tenant e09ad6bc-1d3c-4650-8cae-02f6c5a04b45 -PhoneNumber 4255550101
```

|httpResponseCode  |isNumberBlocked   |errorMessage |
|---------|---------|---------|
|200    | Verdadeiro        |         |

```powershell
Test-CsInboundBlockedNumberPattern -Tenant e09ad6bc-1d3c-4650-8cae-02f6c5a04b45 -PhoneNumber 6045550188
```

|httpResponseCode  |isNumberBlocked   |errorMessage |
|---------|---------|---------|
|200    | Falso        |         |

## <a name="a-note-about-regex"></a>Uma observação sobre Regex

Conforme mencionado anteriormente, a correspondência de padrões para bloquear chamadores é feita usando Regex. Várias ferramentas estão disponíveis online para ajudar a validar uma correspondência de padrão regex. Se você não estiver familiarizado com os padrões regex, recomendamos que você reserve algum tempo para se familiarizar com os conceitos básicos. Para garantir que você obtenha os resultados esperados, use uma ferramenta para validar correspondências de padrão antes de adicionar novas correspondências de número bloqueado ao seu locatário.

## <a name="related-topics"></a>Tópicos relacionados

- [Configure seu computador para gerenciar o Skype for Business Online usando o Windows PowerShell](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
