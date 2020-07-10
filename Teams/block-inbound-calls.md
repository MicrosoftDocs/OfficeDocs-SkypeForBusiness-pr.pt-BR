---
title: Bloquear chamadas recebidas no Microsoft Teams
ms.author: v-lanac
author: lanachin
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
ms.openlocfilehash: 3bb1222f0662228e5c0de7b2253cbac162571b1e
ms.sourcegitcommit: a36514c7c8ea47bde4edb09c11ff99061b1f74c0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/10/2020
ms.locfileid: "45094677"
---
# <a name="block-inbound-calls"></a>Bloquear chamadas recebidas

Os planos de roteamento e chamada do sistema telefônico dão suporte ao bloqueio de chamadas recebidas da PSTN (rede telefônica pública comutada). Esse recurso permite que uma lista global de locatários de padrões de número seja definida para que a identificação de chamadas de todas as chamadas PSTN de entrada para o locatário possa ser verificada na lista para uma correspondência. Se for feita uma correspondência, uma chamada de entrada será rejeitada.

Esse recurso de bloqueio de chamadas de entrada funciona apenas em chamadas de entrada que se originam da PSTN e só funciona em uma base global de locatários. Ele não está disponível para cada usuário.  

>[!NOTE]
> Os chamadores bloqueados podem experimentar comportamentos ligeiramente diferentes quando foram bloqueados. O comportamento é baseado em como a operadora do chamador bloqueado manipula a notificação de que a chamada não pode ser concluída com êxito. Os exemplos podem incluir uma mensagem de portadora informando que a chamada não pode ser concluída como discada ou simplesmente descartando a chamada.

## <a name="call-blocking-admin-controls-and-information"></a>Informações e controles de administração do bloqueio de chamadas

Os controles de administrador para bloquear números são fornecidos somente com o uso do PowerShell. Padrões de blocos de números são definidos como padrões de expressão regular. A ordem das expressões é não importante – o primeiro padrão correspondido na lista resulta na bloqueio da chamada. Um novo número ou padrão que é adicionado ou removido na lista de chamadores bloqueados pode levar até 24 horas para que o padrão se torne ativo.

## <a name="call-blocking-powershell-commands"></a>Comandos do PowerShell de bloqueio de chamadas

Você gerencia padrões de número usando os cmdlets **New**, **Get**, **set**, **Remove**  - **CsInboundBlockedNumberPattern** . Você pode gerenciar um determinado padrão usando esses cmdlets, incluindo a capacidade de alternar a ativação de um determinado padrão.

- [Get-CsInboundBlockedNumberPattern](https://docs.microsoft.com/powershell/module/skype/get-csinboundblockednumberpattern) retorna uma lista de todos os padrões de número bloqueados adicionados à lista de locatários, incluindo o nome, a descrição, habilitado (verdadeiro/falso) e o padrão para cada um deles.
- [New-CsInboundBlockedNumberPattern](https://docs.microsoft.com/powershell/module/skype/new-csinboundblockednumberpattern) adiciona um padrão de número bloqueado à lista de locatários.
- [Remove-CsInboundBlockedNumberPattern](https://docs.microsoft.com/powershell/module/skype/remove-csinboundblockednumberpattern) remove um padrão de número bloqueado da lista de locatários.
- [Set-CsInboundBlockedNumberPattern](https://docs.microsoft.com/powershell/module/skype/set-csinboundblockednumberpattern) modifica um ou mais parâmetros de um padrão de número bloqueado na lista de locatários.

A exibição e a ativação de todo o recurso de bloqueio de chamadas é gerenciada pelos cmdlets **Get**, **set**  - **CsTenantBlockingCallingNumbers** .

- [Get-CsTenantBlockedCallingNumbers](https://docs.microsoft.com/powershell/module/skype/get-cstenantblockedcallingnumbers) retorna os parâmetros da lista de números bloqueados global, incluindo Enabled (true/false). Há uma única política de locatário global que não pode ser modificada manualmente a não ser ativar ou desativar o recurso.
- [Set-CsTenantBlockedCallingNumbers](https://docs.microsoft.com/powershell/module/skype/set-cstenantblockedcallingnumbers) permite modificar as chamadas bloqueadas de locatário global para serem ativadas e desativadas no nível do locatário.

### <a name="examples"></a>Exemplos

#### <a name="block-a-number"></a>Bloquear um número

Neste exemplo, os parâmetros **Enabled** e **Description** são opcionais.

```powershell
New-CsInboundBlockedNumberPattern -Name “<name>” -Enabled $True -Description “<description>” -Pattern “^[+]?13125550000”
```

A criação de um novo padrão adiciona o padrão como habilitado por padrão. A descrição é um campo opcional para fornecer mais informações.

Recomendamos que você forneça um nome significativo para compreender facilmente porque o padrão foi adicionado. No caso de simplesmente bloquear números de spam, considere nomear a regra da mesma forma que o padrão de número que está sendo correspondido e adicionar informações adicionais na descrição, conforme necessário.

Padrões são correspondentes usando-se expressões regulares (Regex). Aguarde tempo para a replicação antes de testar e validar.

#### <a name="allow-a-number"></a>Permitir um número

Neste exemplo, o parâmetro **Identity** é necessário.

```powershell
Remove-CsInboundBlockedNumberPattern -Identity “<identity>”
```
 
Se a identidade não for conhecida, use o cmdlet **Get-CsInboundBlockedNumberPattern** para primeiro localizar o padrão apropriado e anotar a identidade. Em seguida, execute o cmdlet **Remove-CsTenantBlockedNumberPattern** e transmita o valor de identidade apropriado.

Aguarde tempo para a replicação antes de testar e validar.

#### <a name="view-all-number-patterns"></a>Exibir todos os padrões de número

Executar esse cmdlet retorna uma lista de todos os números bloqueados que são inseridos para um locatário:

```powershell
Get-CsInboundBlockedNumberPattern
```

Use as capacidades de filtragem internas do PowerShell para analisar os valores retornados conforme necessário.

## <a name="add-number-exceptions"></a>Adicionar exceções de número

Você pode adicionar exceções a padrões de número bloqueados usando os cmdlets **New**, **Get**, **set**, **Remove**  - **CsTenantBlockNumberExceptionPattern** .

- [New-CsTenantBlockedNumberExceptionPattern](https://docs.microsoft.com/powershell/module/skype/new-cstenantblockednumberexceptionpattern) adiciona um padrão de exceção de número à lista de locatários. 
- [Get-CsTenantBlockedNumberExceptionPattern](https://docs.microsoft.com/powershell/module/skype/get-cstenantblockednumberexceptionpattern) retorna uma lista de todos os padrões de exceção de número adicionados à lista de locatários.
- [Set-CsTenantBlockedNumberExceptionPattern](https://docs.microsoft.com/powershell/module/skype/set-cstenantblockednumberexceptionpattern) modifica um ou mais parâmetros para um padrão de exceção de número na lista de locatários.
- [Remove-CsTenantBlockedNumberExceptionPattern](https://docs.microsoft.com/powershell/module/skype/remove-cstenantblockednumberexceptionpattern) remove um padrão de exceção de número da lista de locatários.

### <a name="examples"></a>Exemplos

#### <a name="add-a-number-exception"></a>Adicionar uma exceção de número

Neste exemplo, um novo padrão de exceção de número é criado e, por padrão, adiciona o padrão como habilitado. Os parâmetros **Enabled** e **Description** são opcionais.

```powershell
New-CsTenantBlockedNumberExceptionPattern -Identity <XdsGlobalRelativeIdentity> -Tenant <GUID> -Pattern <String> -Enabled <bool> -Description <string>
```

```powershell
New-CsTenantBlockedNumberExceptionPattern -Identity InternationalPrefix -Tenant daacb588-18ef-4f77-8c83-955af9615930 -Pattern "^011(\d*)$" -Description "Allow international prefix in US"  
```

#### <a name="view-all-number-exceptions"></a>Exibir todas as exceções de número

Neste exemplo, o parâmetro **Identity** é opcional. Se o parâmetro **Identity** não for especificado, esse cmdlet retornará uma lista de todos os padrões de exceção de número inseridos para um locatário.
 
```powershell
Get-CsTenantBlockedNumberExceptionPattern -Identity <XdsGlobalRelativeIdentity> -Tenant <GUID>
```
 
```powershell
Get-CsTenantBlockedNumberExceptionPattern -Tenant daacb588-18ef-4f77-8c83-955af9615930
```

#### <a name="modify-a-number-exception"></a>Modificar uma exceção de número

Neste exemplo, o parâmetro **Identity** é obrigatório. O cmdlet **set-CsTenantBlockedNumberExceptionPattern** permite modificar um ou mais parâmetros para uma determinada identidade de padrão de número.
 
```powershell
Set-CsTenantBlockedNumberExceptionPattern -Identity <XdsGlobalRelativeIdentity> -Tenant <GUID> -Enabled <bool> -Description <string> -Pattern <string> 
```

```powershell
Set-CsTenantBlockedNumberExceptionPattern -Identity InternationalPrefix -Tenant daacb588-18ef-4f77-8c83-955af9615930  -Pattern "^022(\d*)$" 
```

#### <a name="remove-a-number-exception"></a>Remover uma exceção de número

Neste exemplo, o parâmetro **Identity** é necessário. Esse cmdlet removerá o padrão de número especificado da lista de locatários.  Se a identidade não for conhecida, use o cmdlet **Get-CsInboundBlockedNumberPattern** para primeiro localizar o padrão apropriado e anotar a identidade. Em seguida, execute o cmdlet **Remove-CsTenantBlockedNumberExceptionPattern** e transmita o valor de identidade apropriado.Aguarde tempo para a replicação antes de testar e validar.  

```powershell
Remove-CsTenantBlockedNumberExceptionPattern -Identity <XdsGlobalRelativeIdentity> -Tenant <GUID>
```

```powershell
Remove-CsTenantBlockedNumberExceptionPattern -Identity InternationalPrefix -Tenant daacb588-18ef-4f77-8c83-955af9615930
```

### <a name="test-whether-a-number-is-blocked"></a>Testar se um número está bloqueado

Use o cmdlet **Test-CsInboundBlockedNumberPattern** para verificar se um número está bloqueado no locatário.
 
Neste exemplo, os parâmetros **intervalo** e **locatário** são obrigatórios. O parâmetro **intervalo** deve ser uma cadeia de caracteres numérica sem caracteres adicionais, como + ou-. No TRPS, o **parâmetro locatário** é opcional. O parâmetro **isNumberBlocked** resultante retorna um valor de true se o número estiver bloqueado no locatário e false se não estiver bloqueado.

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

Conforme declarado anteriormente, a correspondência de padrão para bloquear chamadores é feita usando Regex. Há várias ferramentas disponíveis online para ajudar a validar uma correspondência de padrão de Regex. Se você não estiver familiarizado com padrões de Regex, recomendamos que leve algum tempo para se familiarizar com as noções básicas. Para garantir que você tenha resultados esperados, use uma ferramenta para validar as correspondências de padrão antes de adicionar um novo número bloqueado correspondente ao seu locatário.
