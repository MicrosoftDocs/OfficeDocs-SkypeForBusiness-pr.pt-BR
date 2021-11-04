---
title: Bloquear chamadas de entrada em Microsoft Teams
ms.author: v-mahoffman
author: cichur
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
ms.custom: Learn how to use PowerShell to manage inbound call blocking.
ms.openlocfilehash: 4e7e6d40173bb5917a6cf540481257b21253eeaa
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/04/2021
ms.locfileid: "60766219"
---
# <a name="block-inbound-calls"></a>Bloquear chamadas de entrada

Planos de Chamadas da Microsoft, Roteamento Direto e Operador Conexão todos suportam o bloqueio de chamadas de entrada da PSTN (Rede Telefônica Pública Comucionária). Esse recurso permite que um administrador defina uma lista de padrões de números no nível global do locatário para que a ID do chamador de cada chamada PSTN de entrada para o locatário possa ser verificada na lista para uma combinação. Se uma combinação for feita, uma chamada de entrada será rejeitada.

Esse recurso de bloqueio de chamada de entrada só funciona em chamadas de entrada que se originam da PSTN e só funcionam em um nível global do locatário. Usuários Teams individuais não podem manipular essa lista. O Teams cliente permite que usuários individuais bloqueiem chamadas PSTN. Para obter informações sobre como os usuários finais podem implementar o bloqueio de chamada, consulte [Manage call settings in Teams](https://support.microsoft.com/office/manage-your-call-settings-in-teams-456cb611-3477-496f-b31a-6ab752a7595f).

>[!NOTE]
> Os chamadores bloqueados podem ter comportamentos ligeiramente diferentes quando foram bloqueados. O comportamento se baseia em como a operadora do chamador bloqueado lida com a notificação de que a chamada não tem permissão para ser concluída com êxito. Exemplos podem incluir uma mensagem de operadora informando que a chamada não pode ser concluída como discada ou simplesmente soltando a chamada.

## <a name="call-blocking-admin-controls-and-information"></a>Informações e controles de administrador de bloqueio de chamada

Os controles de administrador para números de bloqueio são fornecidos usando apenas o PowerShell. Padrões de bloco de números são definidos como padrões de expressão regulares. A ordem das expressões não é importante – o primeiro padrão que é matched na lista resulta no bloqueio da chamada. Um novo número ou padrão adicionado ou removido na lista de chamadores bloqueados pode levar até 24 horas para que o padrão se torne ativo.

## <a name="call-blocking-powershell-commands"></a>Comandos de bloqueio de chamada do PowerShell

Você gerencia padrões de números usando os cmdlets **New-**, **Get-,** **Set-** e **Remove-CsInboundBlockedNumberPattern.** Você pode gerenciar um determinado padrão usando esses cmdlets, incluindo a capacidade de alternar a ativação de um determinado padrão.

- [Get-CsInboundBlockedNumberPattern](/powershell/module/skype/get-csinboundblockednumberpattern) retorna uma lista de todos os padrões de números bloqueados adicionados à lista de locatários, incluindo Nome, Descrição, Habilitado (True/False) e Padrão para cada um.
- [New-CsInboundBlockedNumberPattern](/powershell/module/skype/new-csinboundblockednumberpattern) adiciona um padrão de número bloqueado à lista de locatários.
- [Remove-CsInboundBlockedNumberPattern](/powershell/module/skype/remove-csinboundblockednumberpattern) remove um padrão de número bloqueado da lista de locatários.
- [Set-CsInboundBlockedNumberPattern](/powershell/module/skype/set-csinboundblockednumberpattern) modifica um ou mais parâmetros de um padrão de número bloqueado na lista de locatários.

A exibição e a ativação de todo o recurso de bloqueio de chamadas é gerenciada por meio dos cmdlets **Get e** **Set-CsTenantBlockingCallingNumbers.**

- [Get-CsTenantBlockedCallingNumbers](/powershell/module/skype/get-cstenantblockedcallingnumbers) retorna os padrões de número de bloco de entrada e os parâmetros de padrões de número isentos de entrada para a lista de números bloqueados global. Este cmdlet também retorna se o bloqueio foi habilitado (True ou False). Há uma única política de locatário global que não pode ser modificada manualmente, além de ativar ou desativar o recurso.
- [Set-CsTenantBlockedCallingNumbers](/powershell/module/skype/set-cstenantblockedcallingnumbers) permite modificar as chamadas de locatário global bloqueadas para serem ativas e desligadas no nível do locatário.

### <a name="examples"></a>Exemplos

#### <a name="block-a-number"></a>Bloquear um número

No exemplo a seguir, o administrador de locatários deseja bloquear todas as chamadas provenientes do intervalo de números 1 (312) 555-0000 a 1 (312) 555-9999. O padrão de número é criado para que ambos os números no intervalo com + prefixados e números no intervalo sem + prefixados sejam matched. Você não precisa incluir os símbolos – e () nos números de telefone porque o sistema tira esses símbolos antes de corresponder.  Para ativar o padrão de número, o **parâmetro Enabled** é definido como True. Para desabilitar esse padrão de número específico, de definir o parâmetro como False.

```PowerShell
New-CsInboundBlockedNumberPattern -Name "BlockRange1" -Enabled $True -Description "Block Contoso" -Pattern "^\+?1312555\d{4}$"
```

No próximo exemplo, o administrador de locatários deseja bloquear todas as chamadas provenientes do número 1 (412) 555-1234. Para ativar o padrão de número, o **parâmetro Enabled** é definido como True.

```PowerShell
New-CsInboundBlockedNumberPattern -Name "BlockNumber1" -Enabled $True -Description "Block Fabrikam" -Pattern "^\+?14125551234$"
```

A criação de um novo padrão adiciona o padrão conforme habilitado por padrão. A descrição é um campo opcional para fornecer mais informações.

Recomendamos que você forneça um nome significativo para entender facilmente por que o padrão foi adicionado. No caso de simplesmente bloquear números de spam, considere nomear a regra da mesma forma que o padrão de número que está sendo corresponder e adicionar informações adicionais na descrição conforme necessário.

Os padrões são corresponderem usando Expressões Regulares (Regex). Para obter mais informações, consulte [Using Regex](#using-regex).

Permitir tempo para replicação antes de testar e validar. 

#### <a name="allow-a-number"></a>Permitir um número

Você pode permitir que um número chame removendo o padrão de número bloqueado. No exemplo a seguir, o administrador de locatários deseja permitir que 1 (412) 555-1234 faça chamadas novamente.

```PowerShell
Remove-CsInboundBlockedNumberPattern -Identity "BlockNumber1"
```
 
Se a identidade não for conhecida, use o cmdlet **Get-CsInboundBlockedNumberPattern** para localizar primeiro o padrão adequado e observar a identidade. Em seguida, execute o cmdlet **Remove-CsInboundBlockedNumberPattern** e passe o valor de identidade apropriado.

Permitir tempo para replicação antes de testar e validar.

#### <a name="view-all-number-patterns"></a>Exibir todos os padrões de números

Executar este cmdlet retorna uma lista de todos os números bloqueados inseridos para um locatário:

```powershell
Get-CsInboundBlockedNumberPattern
```

Use as habilidades de filtragem do PowerShell integrados para analisar os valores retornados conforme necessário.

## <a name="add-number-exceptions"></a>Adicionar exceções de número

Você pode adicionar exceções a padrões de números bloqueados usando os cmdlets **New-**, **Get-**, **Set-** e **Remove-CsInboundExemptNumberPattern.**

- [New-CsInboundExemptNumberPattern](/powershell/module/skype/New-CsInboundExemptNumberPattern) adiciona um padrão de exceção de número à lista de locatários. 
- [Get-CsInboundExemptNumberPattern](/powershell/module/skype/Get-CsInboundExemptNumberPattern) retorna uma lista de todos os padrões de exceção de número adicionados à lista de locatários.
- [Set-CsInboundExemptNumberPattern](/powershell/module/skype/Set-CsInboundExemptNumberPattern) modifica um ou mais parâmetros para um padrão de exceção de número na lista de locatários.
- [Remove-CsInboundExemptNumberPattern](/powershell/module/skype/Remove-CsInboundExemptNumberPattern) remove um padrão de exceção de número da lista de locatários.

### <a name="examples"></a>Exemplos

#### <a name="add-a-number-exception"></a>Adicionar uma exceção de número

No exemplo a seguir, o administrador de locatários deseja permitir que os números de telefone 1 (312) 555-8882 e 1 (312) 555-8883 façam chamadas para o locatário, mesmo que esses dois números de telefone estão no intervalo bloqueado no exemplo acima. Para habilitar isso, um novo padrão de exceção de número é criado da seguinte forma:

```PowerShell
New-CsInboundExemptNumberPattern  -Identity "AllowContoso1" -Pattern "^\+?1312555888[2|3]$" -Description "Allow Contoso helpdesk" -Enabled $True
```

Para ativar o padrão de número, o **parâmetro Enabled** é definido como True. Para desabilitar esse padrão de número específico, de definir o parâmetro como False.


#### <a name="view-all-number-exceptions"></a>Exibir todas as exceções de número

Neste exemplo, o parâmetro **Identity** é opcional. Se o **parâmetro Identity** não for especificado, este cmdlet retornará uma lista de todos os padrões de exceção de número inseridos para um locatário.
 
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

O cmdlet **Remove-CsInboundExemptNumberPattern** removerá o padrão de número determinado da lista de locatários. Neste exemplo, o **parâmetro Identity** é necessário. 

Se a identidade não for conhecida, use o cmdlet **Get-CsInboundExemptNumberPattern** para primeiro localizar o padrão adequado e observar a identidade. Em seguida, execute o cmdlet **Remove-CsInboundExemptNumberPattern** e passe o valor de identidade apropriado.Permitir tempo para replicação antes de testar e validar.  

```powershell
Remove-CsInboundExemptNumberPattern -Identity <String>
```

```powershell
Remove-CsInboundExemptNumberPattern -Identity "AllowContoso1"
```

## <a name="test-whether-a-number-is-blocked"></a>Testar se um número está bloqueado

Use o cmdlet **Test-CsInboundBlockedNumberPattern** para verificar se um número está bloqueado no locatário.
 
O **parâmetro PhoneNumber** é necessário e deve ser uma cadeia de caracteres numérica sem caracteres adicionais, como +, - ou (). O parâmetro **IsNumberBlocked** resultante retornará um valor True se o número for bloqueado no locatário; o parâmetro retorna False se não estiver bloqueado.

```powershell
Test-CsInboundBlockedNumberPattern –Tenant <GUID> -PhoneNumber <String>
```

### <a name="examples"></a>Exemplos

Nesses exemplos, você pode ver que o número de telefone 1 (312) 555-8884 está bloqueado, pois ele deve estar no intervalo bloqueado acima, enquanto o número de telefone 1 (312) 555-8883 tem permissão para chamar, pois deve ser baseado na isenção criada acima.

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

## <a name="using-regex"></a>Usando Regex

A correspondência de padrão para os chamadores de bloqueio é feita usando Regex. Várias ferramentas estão disponíveis online para ajudar a validar uma combinação de padrão regex. Se você não estiver familiarizado com os padrões Regex, recomendamos que você leve algum tempo para se familiarizar com os conceitos básicos. Para garantir que você receba os resultados esperados, use uma ferramenta para validar as correspondeções de padrão antes de adicionar novas combinações de número bloqueado ao seu locatário.