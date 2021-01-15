---
title: Bloquear chamadas de entrada no Microsoft Teams
ms.author: v-cichur
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
localization_priority: Normal
ms.custom: Learn how to use PowerShell to manage inbound call blocking.
ms.openlocfilehash: ca2f8de5962572a08ab2a0ae7127446d14334c83
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49799901"
---
# <a name="block-inbound-calls"></a>Bloquear chamadas de entrada

Os Planos de Chamadas e Roteamento Direto do Sistema de Telefonia suportam o bloqueio de chamadas de entrada da Rede Telefônica Pública Comutado (PSTN). Esse recurso permite que uma lista global de padrões de números do locatário seja definida para que a ID do chamador de cada chamada PSTN de entrada para o locatário possa ser verificada na lista para uma combinação. Se uma combinação for feita, uma chamada de entrada será rejeitada.

Esse recurso de bloqueio de chamada de entrada só funciona em chamadas de entrada que se originam da PSTN e só funcionam em uma base global do locatário. Ele não está disponível por usuário.  

>[!NOTE]
> Chamadores bloqueados podem ter comportamentos ligeiramente diferentes quando foram bloqueados. O comportamento é baseado em como a operadora do chamador bloqueado lida com a notificação de que a chamada não tem permissão para ser concluída com êxito. Exemplos podem incluir uma mensagem da operadora informando que a chamada não pode ser concluída como discada ou simplesmente soltando a chamada.

## <a name="call-blocking-admin-controls-and-information"></a>Informações e controles de administrador de bloqueio de chamada

Os controles de administrador para números de bloqueio são fornecidos usando apenas o PowerShell. Padrões de bloco de números são definidos como padrões de expressão regular. A ordem das expressões não é importante – o primeiro padrão de acordo com a lista faz com que a chamada seja bloqueada. Um novo número ou padrão adicionado ou removido na lista de chamadores bloqueados pode levar até 24 horas para que o padrão se torne ativo.

## <a name="call-blocking-powershell-commands"></a>Comandos do PowerShell de bloqueio de chamada

Você gerencia padrões de número usando os cmdlets **New**, **Get**, **Set**, **Remove**  - **CsInboundBlockedNumberPattern.** Você pode gerenciar um determinado padrão usando esses cmdlets, incluindo a capacidade de alternar a ativação de um determinado padrão.

- [Get-CsInboundBlockedNumberPattern](https://docs.microsoft.com/powershell/module/skype/get-csinboundblockednumberpattern) retorna uma lista de todos os padrões de números bloqueados adicionados à lista de locatários, incluindo Nome, Descrição, Habilitado (True/Falso) e Padrão para cada um.
- [New-CsInboundBlockedNumberPattern](https://docs.microsoft.com/powershell/module/skype/new-csinboundblockednumberpattern) adiciona um padrão de número bloqueado à lista de locatários.
- [Remove-CsInboundBlockedNumberPattern](https://docs.microsoft.com/powershell/module/skype/remove-csinboundblockednumberpattern) remove um padrão de número bloqueado da lista de locatários.
- [Set-CsInboundBlockedNumberPattern](https://docs.microsoft.com/powershell/module/skype/set-csinboundblockednumberpattern) modifica um ou mais parâmetros de um padrão de número bloqueado na lista de locatários.

A exibição e a ativação de todo o recurso de bloqueio de chamadas são gerenciadas por meio dos cmdlets **Get**, **Set**  - **CsTenantBlockingCallingNumbers.**

- [Get-CsTenantBlockedCallingNumbers](https://docs.microsoft.com/powershell/module/skype/get-cstenantblockedcallingnumbers) retorna os parâmetros da lista de números bloqueados global, incluindo Enabled (True/False). Há uma única política de locatário global que não pode ser modificada manualmente além de ativar ou desativar o recurso.
- [Set-CsTenantBlockedCallingNumbers](https://docs.microsoft.com/powershell/module/skype/set-cstenantblockedcallingnumbers) permite que a modificação das chamadas de locatário global bloqueadas sejam 1 ou 100% ativas e desligadas no nível do locatário.

### <a name="examples"></a>Exemplos

#### <a name="block-a-number"></a>Bloquear um número

Neste exemplo, os **parâmetros Enabled** e **Description** são opcionais.

```powershell
New-CsInboundBlockedNumberPattern -Name “<name>” -Enabled $True -Description “<description>” -Pattern “^[+]?13125550000”
```

A criação de um novo padrão adiciona o padrão como habilitado por padrão. A descrição é um campo opcional para fornecer mais informações.

Recomendamos que você forneça um nome significativo para entender facilmente por que o padrão foi adicionado. No caso de simplesmente bloquear números de spam, considere nomear a regra da mesma forma que o padrão de número que está sendo corresponder e adicionar informações adicionais na descrição conforme necessário.

Os padrões são atendidos usando Expressões Regulares (Regex). Permita o tempo de replicação antes de testar e validar.

#### <a name="allow-a-number"></a>Permitir um número

Neste exemplo, o parâmetro **Identity** é necessário.

```powershell
Remove-CsInboundBlockedNumberPattern -Identity “<identity>”
```
 
Se a identidade não for conhecida, use o cmdlet **Get-CsInboundBlockedNumberPattern** para localizar primeiro o padrão apropriado e anote a identidade. Em seguida, execute o cmdlet **Remove-CsTenantBlockedNumberPattern** e passe o valor de identidade apropriado.

Permita o tempo de replicação antes de testar e validar.

#### <a name="view-all-number-patterns"></a>Exibir todos os padrões de números

A execução deste cmdlet retorna uma lista de todos os números bloqueados inseridos para um locatário:

```powershell
Get-CsInboundBlockedNumberPattern
```

Use as capacidades de filtragem do PowerShell integrados para analisar os valores retornados conforme necessário.

## <a name="add-number-exceptions"></a>Adicionar exceções de número

Você pode adicionar exceções a padrões de números bloqueados usando os cmdlets **New**, **Get**, **Set**, **Remove**  - **CsTenantBlockNumberExceptionPattern.**

- [New-CsTenantBlockedNumberExceptionPattern](https://docs.microsoft.com/powershell/module/skype/new-cstenantblockednumberexceptionpattern) adiciona um padrão de exceção de número à lista de locatários. 
- [Get-CsTenantBlockedNumberExceptionPattern](https://docs.microsoft.com/powershell/module/skype/get-cstenantblockednumberexceptionpattern) retorna uma lista de todos os padrões de exceção de número adicionados à lista de locatários.
- [Set-CsTenantBlockedNumberExceptionPattern](https://docs.microsoft.com/powershell/module/skype/set-cstenantblockednumberexceptionpattern) modifica um ou mais parâmetros para um padrão de exceção de número na lista de locatários.
- [Remove-CsTenantBlockedNumberExceptionPattern](https://docs.microsoft.com/powershell/module/skype/remove-cstenantblockednumberexceptionpattern) remove um padrão de exceção de número da lista de locatários.

### <a name="examples"></a>Exemplos

#### <a name="add-a-number-exception"></a>Adicionar uma exceção de número

Neste exemplo, um novo padrão de exceção de número é criado e, por padrão, adicionará o padrão conforme habilitado. Os **parâmetros Enabled** e **Description** são opcionais.

```powershell
New-CsTenantBlockedNumberExceptionPattern -Identity <XdsGlobalRelativeIdentity> -Tenant <GUID> -Pattern <String> -Enabled <bool> -Description <string>
```

```powershell
New-CsTenantBlockedNumberExceptionPattern -Identity InternationalPrefix -Tenant daacb588-18ef-4f77-8c83-955af9615930 -Pattern "^011(\d*)$" -Description "Allow international prefix in US"  
```

#### <a name="view-all-number-exceptions"></a>Exibir todas as exceções de número

Neste exemplo, o parâmetro **Identity** é opcional. Se o **parâmetro Identity** não for especificado, este cmdlet retornará uma lista de todos os padrões de exceção de número inseridos para um locatário.
 
```powershell
Get-CsTenantBlockedNumberExceptionPattern -Identity <XdsGlobalRelativeIdentity> -Tenant <GUID>
```
 
```powershell
Get-CsTenantBlockedNumberExceptionPattern -Tenant daacb588-18ef-4f77-8c83-955af9615930
```

#### <a name="modify-a-number-exception"></a>Modificar uma exceção de número

Neste exemplo, o parâmetro **Identity** é obrigatório. O cmdlet **Set-CsTenantBlockedNumberExceptionPattern** permite modificar um ou mais parâmetros para uma determinada identidade de padrão de número.
 
```powershell
Set-CsTenantBlockedNumberExceptionPattern -Identity <XdsGlobalRelativeIdentity> -Tenant <GUID> -Enabled <bool> -Description <string> -Pattern <string> 
```

```powershell
Set-CsTenantBlockedNumberExceptionPattern -Identity InternationalPrefix -Tenant daacb588-18ef-4f77-8c83-955af9615930  -Pattern "^022(\d*)$" 
```

#### <a name="remove-a-number-exception"></a>Remover uma exceção de número

Neste exemplo, o parâmetro **Identity** é necessário. Este cmdlet removerá o padrão de número determinado da lista de locatários.  Se a identidade não for conhecida, use o cmdlet **Get-CsInboundBlockedNumberPattern** para localizar primeiro o padrão apropriado e anote a identidade. Em seguida, execute o cmdlet **Remove-CsTenantBlockedNumberExceptionPattern** e passe o valor de identidade apropriado.Permita o tempo de replicação antes de testar e validar.  

```powershell
Remove-CsTenantBlockedNumberExceptionPattern -Identity <XdsGlobalRelativeIdentity> -Tenant <GUID>
```

```powershell
Remove-CsTenantBlockedNumberExceptionPattern -Identity InternationalPrefix -Tenant daacb588-18ef-4f77-8c83-955af9615930
```

### <a name="test-whether-a-number-is-blocked"></a>Testar se um número está bloqueado

Use o cmdlet **Test-CsInboundBlockedNumberPattern** para verificar se um número está bloqueado no locatário.
 
Neste exemplo, os **parâmetros PhoneNumber** e **Tenant** são necessários. O **parâmetro PhoneNumber** deve ser uma cadeia de caracteres numérica sem caracteres adicionais, como + ou -. Em TRPS, o parâmetro **Tenant** é opcional. O parâmetro **isNumberBlocked** resultante retornará um valor True se o número for bloqueado no locatário e False se não estiver bloqueado.

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

## <a name="a-note-about-regex"></a>Uma observação sobre a Regex

Conforme indicado anteriormente, a correspondência de padrão para bloquear chamadores é feita usando Regex. Várias ferramentas estão disponíveis online para ajudar a validar uma combinação de padrões Regex. Se você não estiver familiarizado com padrões Regex, recomendamos que você desem algum tempo para se familiarizar com as noções básicas. Para garantir que você receba os resultados esperados, use uma ferramenta para validar as correspondeções de padrão antes de adicionar novas combinações de números bloqueados ao seu locatário.
