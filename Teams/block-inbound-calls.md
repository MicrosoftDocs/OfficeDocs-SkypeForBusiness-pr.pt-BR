---
title: Bloquear chamadas de entrada no Microsoft Teams
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.collection:
- M365-voice
audience: Admin
ms.reviewer: roykuntz
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
ms.custom: ''
description: Saiba como usar o PowerShell para gerenciar o bloqueio de chamadas de entrada.
ms.openlocfilehash: 01d1fb08d0b0cca4bc0a35ca77109e976d63a1f0
ms.sourcegitcommit: f0e2a5928e9b959daf45202b9f256f65c2087195
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/20/2022
ms.locfileid: "68614424"
---
# <a name="block-inbound-calls"></a>Bloquear chamadas de entrada

Os Planos de Chamadas da Microsoft, o Roteamento Direto e o Operador Conectam todos os suportes ao bloqueio de chamadas de entrada da PSTN (Rede Telefônica Pública Comunada). Esse recurso permite que um administrador defina uma lista de padrões de número e exceções no nível global do locatário para que a ID do chamador de cada chamada PSTN de entrada para o locatário possa ser verificada na lista quanto a uma correspondência. Se uma correspondência for feita, uma chamada de entrada será rejeitada.

Esse recurso de bloqueio de chamada de entrada só funciona em chamadas de entrada originadas do PSTN e só funciona em um nível global do locatário. Usuários individuais do Teams não podem manipular essa lista. O cliente do Teams permite que usuários individuais bloqueiem chamadas PSTN. Para obter informações sobre como os usuários finais podem implementar o bloqueio de chamadas, consulte [Gerenciar configurações de chamada no Teams](https://support.microsoft.com/office/manage-your-call-settings-in-teams-456cb611-3477-496f-b31a-6ab752a7595f).

> [!NOTE]
> Os chamadores bloqueados podem ter comportamentos ligeiramente diferentes quando foram bloqueados. O comportamento se baseia em como a operadora do chamador bloqueado manipula a notificação de que a chamada não tem permissão para ser concluída com êxito. Os exemplos podem incluir uma mensagem da operadora informando que a chamada não pode ser concluída como discada ou simplesmente descartando a chamada.

Observe que, no momento, não é possível gerenciar o bloqueio de chamadas usando o Centro de administração do Teams.

## <a name="manage-call-blocking-by-using-powershell"></a>Gerenciar o bloqueio de chamadas usando o PowerShell

Para gerenciar o bloqueio de chamadas, você precisará definir um ou mais padrões numéricos dos quais bloquear chamadas, definir exceções para os padrões de número e habilitar o recurso de bloqueio de chamadas.

Os padrões de bloco numérico são definidos como padrões de expressão regular. A ordem das expressões não é importante– o primeiro padrão correspondido na lista faz com que a chamada seja bloqueada. Um novo número ou padrão adicionado ou removido na lista de chamadores bloqueados pode levar até 24 horas para que o padrão se torne ativo.

### <a name="activate-the-call-blocking-feature"></a>Ativar o recurso de bloqueio de chamada

Para exibir e ativar o recurso de bloqueio de chamada, use os cmdlets **Get-** e **Set-CsTenantBlockingCallingNumbers** teams do PowerShell Module.

- [Get-CsTenantBlockedCallingNumbers](/powershell/module/skype/get-cstenantblockedcallingnumbers) retorna os padrões de número de bloco de entrada e os parâmetros de padrões de número isento de entrada para a lista de números bloqueados global. Esse cmdlet também retorna se o bloqueio foi habilitado (Verdadeiro ou Falso). 

- [Set-CsTenantBlockedCallingNumbers](/powershell/module/skype/set-cstenantblockedcallingnumbers) permite que você especifique se as chamadas de locatário global bloqueadas estão ativadas ou desativadas no nível do locatário.

### <a name="manage-block-number-patterns"></a>Gerenciar padrões de número de bloco

Você gerencia padrões de número usando os cmdlets do Módulo do PowerShell **do PowerShell New-**, **Get-**, **Set-**, **Test e** **Remove-CsInboundBlockedNumberPattern** teams. 

- [Get-CsInboundBlockedNumberPattern](/powershell/module/skype/get-csinboundblockednumberpattern) retorna uma lista de todos os padrões de número bloqueado adicionados à lista de locatários, incluindo Nome, Descrição, Habilitado (True/False) e Padrão.

- [New-CsInboundBlockedNumberPattern](/powershell/module/skype/new-csinboundblockednumberpattern) adiciona um padrão de número bloqueado à lista de locatários.

- [Remove-CsInboundBlockedNumberPattern](/powershell/module/skype/remove-csinboundblockednumberpattern) remove um padrão de número bloqueado da lista de locatários.

- [Set-CsInboundBlockedNumberPattern](/powershell/module/skype/set-csinboundblockednumberpattern) modifica um ou mais parâmetros de um padrão de número bloqueado na lista de locatários.

- [Test-CsInboundBlockedNumberPattern](/powershell/module/skype/set-csinboundblockednumberpattern) testa se as chamadas de um determinado número de telefone serão bloqueadas.


### <a name="examples"></a>Exemplos

#### <a name="block-a-number"></a>Bloquear um número

No exemplo a seguir, o administrador de locatários deseja bloquear todas as chamadas provenientes do intervalo de números 1 (312) 555-0000 a 1 (312) 555-9999. O padrão de número é criado para que ambos os números no intervalo com + prefixados e números no intervalo sem + prefixados sejam correspondidos. Você não precisa incluir os símbolos – e () nos números de telefone porque o sistema remove esses símbolos antes de corresponder.  Para ativar o padrão de número, defina **o parâmetro Enabled** como True. Para desabilitar esse padrão de número específico, defina o parâmetro como False.

```PowerShell
New-CsInboundBlockedNumberPattern -Name "BlockRange1" -Enabled $True -Description "Block Contoso" -Pattern "^\+?1312555\d{4}$"
```

No próximo exemplo, o administrador do locatário deseja bloquear todas as chamadas provenientes do número 1 (412) 555-1234. Para ativar o padrão de número, o **parâmetro Enabled** é definido como True.

```PowerShell
New-CsInboundBlockedNumberPattern -Name "BlockNumber1" -Enabled $True -Description "Block Fabrikam" -Pattern "^\+?14125551234$"
```

A criação de um novo padrão adiciona o padrão conforme habilitado por padrão. A descrição é um campo opcional para fornecer mais informações.

Recomendamos que você forneça um nome significativo para entender facilmente por que o padrão foi adicionado. Para bloquear números de spam, considere nomear a regra da mesma forma que o padrão de número que está sendo correspondido e, em seguida, adicione informações adicionais na descrição, conforme necessário.

Os padrões são correspondidos usando Expressões Regulares (Regex). Para obter mais informações, consulte [Usando Regex](#using-regex).

Aguarde a replicação antes de testar e validar.

#### <a name="allow-a-number"></a>Permitir um número

Você pode permitir que um número chame removendo o padrão de número bloqueado. No exemplo a seguir, o administrador de locatários deseja permitir que 1 (412) 555-1234 faça chamadas novamente.

```PowerShell
Remove-CsInboundBlockedNumberPattern -Identity "BlockNumber1"
```

Se a identidade não for conhecida, use o cmdlet **Get-CsInboundBlockedNumberPattern** para localizar primeiro o padrão adequado e anotar a identidade. Em seguida, execute o cmdlet **Remove-CsInboundBlockedNumberPattern** e passe o valor de identidade apropriado.

Aguarde a replicação antes de testar e validar.

#### <a name="view-all-number-patterns"></a>Exibir todos os padrões de número

O cmdlet a seguir retorna uma lista de todos os números bloqueados inseridos para um locatário:

```powershell
Get-CsInboundBlockedNumberPattern
```

Use as capacidades de filtragem internas do PowerShell para analisar os valores retornados conforme necessário.

#### <a name="test-whether-a-number-is-blocked"></a>Testar se um número está bloqueado

Para verificar se um número está bloqueado no locatário, use o cmdlet **Test-CsInboundBlockedNumberPattern** .

O **parâmetro PhoneNumber** é necessário e deve ser uma cadeia de caracteres numérica sem caracteres adicionais, como +, ou (). O parâmetro **IsNumberBlocked** resultante retornará um valor true se o número estiver bloqueado no locatário; o parâmetro retornará False se não estiver bloqueado.

Nos exemplos a seguir, você pode ver que o número de telefone 1 (312) 555-8884 está bloqueado porque está no intervalo bloqueado acima. O número de telefone 1 (312) 555-8883 é permitido com base na isenção criada abaixo.

```PowerShell
Test-CsInboundBlockedNumberPattern -PhoneNumber 13125558884

RunspaceId      : 09537e45-6f0c-4001-8b85-a79002707b0c
httpStatusCode  : NoContent
IsNumberBlocked : True
errorMessage    :

Test-CsInboundBlockedNumberPattern -PhoneNumber 13125558883

RunspaceId      : 09537e45-6f0c-4001-8b85-a79002707b0c
httpStatusCode  : NoContent
IsNumberBlocked : False
errorMessage    :
```

### <a name="manage-number-exceptions"></a>Gerenciar exceções de número

Você pode adicionar exceções a padrões de número bloqueados usando os cmdlets **New-**, **Get-**, **Set e** **Remove-CsInboundExemptNumberPattern** .

- [New-CsInboundExemptNumberPattern adiciona um](/powershell/module/skype/New-CsInboundExemptNumberPattern) padrão de exceção de número à lista de locatários.

- [Get-CsInboundExemptNumberPattern](/powershell/module/skype/Get-CsInboundExemptNumberPattern) retorna uma lista de todos os padrões de exceção de número adicionados à lista de locatários.

- [Set-CsInboundExemptNumberPattern](/powershell/module/skype/Set-CsInboundExemptNumberPattern) modifica um ou mais parâmetros para um padrão de exceção de número na lista de locatários.

- [Remove-CsInboundExemptNumberPattern](/powershell/module/skype/Remove-CsInboundExemptNumberPattern) remove um padrão de exceção de número da lista de locatários.

### <a name="examples"></a>Exemplos

#### <a name="add-a-number-exception"></a>Adicionar uma exceção de número

No exemplo a seguir, o administrador do locatário deseja permitir que os números de telefone 1 (312) 555-8882 e 1 (312) 555-8883 façam chamadas para o locatário, mesmo que esses dois números de telefone estejam no intervalo bloqueado no exemplo acima. Para habilitar isso, um novo padrão de exceção de número é criado da seguinte maneira:

```PowerShell
New-CsInboundExemptNumberPattern  -Identity "AllowContoso1" -Pattern "^\+?1312555888[2|3]$" -Description "Allow Contoso helpdesk" -Enabled $True
```

Para ativar o padrão de número, o **parâmetro Enabled** é definido como True. Para desabilitar esse padrão de número específico, defina o parâmetro como False.

#### <a name="view-all-number-exceptions"></a>Exibir todas as exceções de número

Neste exemplo, o parâmetro **Identity** é opcional. Se o **parâmetro Identity** não for especificado, esse cmdlet retornará uma lista de todos os padrões de exceção de número inseridos para um locatário.

```powershell
Get-CsInboundExemptNumberPattern -Identity <String>
```

```powershell
Get-CsInboundExemptNumberPattern
```

#### <a name="modify-a-number-exception"></a>Modificar uma exceção de número

O cmdlet **Set-CsInboundExemptNumberPattern** permite modificar um ou mais parâmetros para uma determinada identidade de padrão de número. Neste exemplo, o **parâmetro Identity** é necessário.

```powershell
Set-CsInboundExemptNumberPattern -Identity <String> -Enabled <bool> -Description <string> -Pattern <string>
```

```powershell
Set-CsInboundExemptNumberPattern -Identity "AllowContoso1" -Enabled $False
```

#### <a name="remove-a-number-exception"></a>Remover uma exceção de número

O cmdlet **Remove-CsInboundExemptNumberPattern** removerá o padrão de número fornecido da lista de locatários. Neste exemplo, o **parâmetro Identity** é necessário.

Se a identidade não for conhecida, use o cmdlet **Get-CsInboundExemptNumberPattern** para localizar primeiro o padrão adequado e anotar a identidade. Em seguida, execute o cmdlet **Remove-CsInboundExemptNumberPattern** e passe o valor de identidade apropriado. Aguarde a replicação antes de testar e validar.

```powershell
Remove-CsInboundExemptNumberPattern -Identity <String>
```

```powershell
Remove-CsInboundExemptNumberPattern -Identity "AllowContoso1"
```

## <a name="using-regex"></a>Usando Regex

A correspondência de padrões para bloquear chamadores é feita usando Regex. Várias ferramentas estão disponíveis online para ajudar a validar uma correspondência de padrão regex. Se você não estiver familiarizado com os padrões regex, recomendamos que você reserve algum tempo para se familiarizar com os conceitos básicos. Para garantir que você obtenha os resultados esperados, use uma ferramenta para validar correspondências de padrão antes de adicionar novas correspondências de número bloqueado ao seu locatário.
