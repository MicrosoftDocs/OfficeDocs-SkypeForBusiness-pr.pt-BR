---
title: Bloquear chamadas recebidas no Skype for Business Online
ms.author: v-lanac
author: lanachin
manager: serdars
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
audience: Admin
ms.reviewer: roykuntz
appliesto:
- Skype for Business
localization_priority: Normal
ms.custom: Learn how to use PowerShell to manage inbound call blocking in Skype for Business Online.
ms.openlocfilehash: b238d69087c5b29e6d9abc898e91c44fd8053411
ms.sourcegitcommit: bb88ac0c9489bb47957e5ef1074b5df3126b6fdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/25/2020
ms.locfileid: "42266057"
---
# <a name="block-inbound-calls"></a>Bloquear chamadas recebidas

Agora, os planos de chamadas do Skype for Business online dão suporte ao bloqueio de chamadas recebidas da PSTN (rede telefônica pública comutada). Esse recurso permite que uma lista global de locatários de padrões de número seja definida para que a identificação de chamadas de todas as chamadas PSTN de entrada para o locatário possa ser verificada na lista para uma correspondência. Se for feita uma correspondência, uma chamada de entrada será rejeitada.

Esse recurso de bloqueio de chamadas de entrada funciona apenas em chamadas de entrada que se originam da PSTN e só funciona em uma base global de locatários. Ele não está disponível para cada usuário.  

Este recurso ainda não está disponível para roteamento direto.

>[!NOTE]
> Os chamadores bloqueados podem experimentar comportamentos ligeiramente diferentes quando foram bloqueados. O comportamento é baseado em como a operadora do chamador bloqueado manipula a notificação de que a chamada não pode ser concluída com êxito. Os exemplos podem incluir uma mensagem de portadora informando que a chamada não pode ser concluída como discada ou simplesmente descartando a chamada.

## <a name="call-blocking-admin-controls-and-information"></a>Informações e controles de administração do bloqueio de chamadas

Os controles de administrador para bloquear números são fornecidos somente com o uso do PowerShell. Padrões de blocos de números são definidos como padrões de expressão regular. A ordem das expressões é não importante – o primeiro padrão correspondido na lista resulta na bloqueio da chamada. Um novo número ou padrão que é adicionado ou removido na lista de chamadores bloqueados pode levar até 24 horas para que o padrão se torne ativo.

## <a name="call-blocking-powershell-commands"></a>Comandos do PowerShell de bloqueio de chamadas

Padrões de número são gerenciados ```CsInboundBlockedNumberPattern``` por ```New```meio ```Get```dos ```Set```comandos, ```Remove```, e. Você pode gerenciar um determinado padrão usando esses cmdlets, incluindo a capacidade de alternar a ativação de um determinado padrão.
- [Get-CsInboundBlockedNumberPattern](https://docs.microsoft.com/powershell/module/skype/get-csinboundblockednumberpattern) retorna uma lista de todos os padrões de número bloqueados adicionados à lista de locatários, incluindo o nome, a descrição, habilitado (verdadeiro/falso) e o padrão para cada um deles.
- [New-CsInboundBlockedNumberPattern](https://docs.microsoft.com/powershell/module/skype/new-csinboundblockednumberpattern) adiciona um padrão de número bloqueado à lista de locatários.
- [Remove-CsInboundBlockedNumberPattern](https://docs.microsoft.com/powershell/module/skype/remove-csinboundblockednumberpattern) remove um padrão de número bloqueado da lista de locatários.
- [Set-CsInboundBlockedNumberPattern](https://docs.microsoft.com/powershell/module/skype/set-csinboundblockednumberpattern) modifica um ou mais parâmetros de um padrão de número bloqueado na lista de locatários.

A exibição e a ativação de todo o recurso de bloqueio de ```CsTenantBlockingCallingNumbers``` chamadas ```Get``` é ```Set```gerenciada pelos comandos e.

- [Get-CsTenantBlockedCallingNumbers](https://docs.microsoft.com/powershell/module/skype/get-cstenantblockedcallingnumbers) retorna os parâmetros da lista de números bloqueados global, incluindo Enabled (true/false). Há uma única política de locatário global que não pode ser modificada manualmente a não ser ativar ou desativar o recurso.
- [Set-CsTenantBlockedCallingNumbers](https://docs.microsoft.com/powershell/module/skype/set-cstenantblockedcallingnumbers) permite modificar as chamadas bloqueadas de locatário global para serem ativadas e desativadas no nível do locatário.

### <a name="examples"></a>Exemplos

#### <a name="block-a-number"></a>Bloquear um número

Neste exemplo, os ```-Enabled``` parâmetros e ```-Description``` são opcionais:

```powershell
New-CsInboundBlockedNumberPattern -Name “<name>” -Enabled $True -Description “<description>” -Pattern “^[+]?13125550000”
```

A criação de um novo padrão adiciona o padrão como habilitado por padrão. A descrição é um campo opcional para fornecer mais informações.

Recomendamos que você forneça um nome significativo para compreender facilmente porque o padrão foi adicionado. No caso de simplesmente bloquear números de spam, considere nomear a regra da mesma forma que o padrão de número que está sendo correspondido e adicionar informações adicionais na descrição, conforme necessário.

Padrões são correspondentes usando-se expressões regulares (Regex). Aguarde tempo para a replicação antes de testar e validar.

#### <a name="allow-a-number"></a>Permitir um número

Neste exemplo, o ```-Identity``` parâmetro é obrigatório:

```powershell
Remove-CsInboundBlockedNumberPattern -Identity “<identity>”
```
 
Se a identidade não for conhecida, use ```Get-CsInboundBlockedNumberPattern``` o cmdlet para primeiro localizar o padrão apropriado e anotar a identidade. Em seguida, execute ```Remove-CsTenantBlockedNumberPattern``` o cmdlet e transmita o valor de identidade apropriado.

Aguarde tempo para a replicação antes de testar e validar.

#### <a name="view-all-number-patterns"></a>Exibir todos os padrões de número

Executar esse cmdlet retorna uma lista de todos os números bloqueados que são inseridos para um locatário:

```powershell
Get-CsInboundBlockedNumberPattern
```

Use as capacidades de filtragem internas do PowerShell para analisar os valores retornados conforme necessário.

## <a name="add-number-exceptions"></a>Adicionar exceções de número

Você pode adicionar exceções a padrões de número bloqueados ```CsTenantBlockNumberExceptionPattern``` por meio ```New```dos ```Get```comandos ```Set```,, ```Remove```, e.

- [New-CsTenantBlockedNumberExceptionPattern](https://docs.microsoft.com/powershell/module/skype/new-cstenantblockednumberexceptionpattern) adiciona um padrão de exceção de número à lista de locatários. 
- [Get-CsTenantBlockedNumberExceptionPattern](https://docs.microsoft.com/powershell/module/skype/get-cstenantblockednumberexceptionpattern) retorna uma lista de todos os padrões de exceção de número adicionados à lista de locatários.
- [Set-CsTenantBlockedNumberExceptionPattern](https://docs.microsoft.com/powershell/module/skype/set-cstenantblockednumberexceptionpattern) modifica um ou mais parâmetros para um padrão de exceção de número na lista de locatários.
- [Remove-CsTenantBlockedNumberExceptionPattern](https://docs.microsoft.com/powershell/module/skype/remove-cstenantblockednumberexceptionpattern) remove um padrão de exceção de número da lista de locatários.

### <a name="examples"></a>Exemplos

#### <a name="add-a-number-exception"></a>Adicionar uma exceção de número

Neste exemplo, um novo padrão de exceção de número é criado e, por padrão, adiciona o padrão como habilitado. Os ```-Enabled``` parâmetros ```-Description``` e são opcionais.

```powershell
New-CsTenantBlockedNumberExceptionPattern -Identity <XdsGlobalRelativeIdentity> -Tenant <GUID> -Pattern <String> -Enabled <bool> -Description <string>
```

```powershell
New-CsTenantBlockedNumberExceptionPattern -Identity InternationalPrefix -Tenant daacb588-18ef-4f77-8c83-955af9615930 -Pattern "^011(\d*)$" -Description "Allow international prefix in US"  
```

#### <a name="view-all-number-exceptions"></a>Exibir todas as exceções de número

Neste exemplo, o parâmetro-Identity é opcional. Se o ```-Identity``` parâmetro não for especificado, esse cmdlet retornará uma lista de todos os padrões de exceção de número inseridos para um locatário.
 
```powershell
Get-CsTenantBlockedNumberExceptionPattern -Identity <XdsGlobalRelativeIdentity> -Tenant <GUID>
```
 
```powershell
Get-CsTenantBlockedNumberExceptionPattern -Tenant daacb588-18ef-4f77-8c83-955af9615930
```

#### <a name="modify-a-number-exception"></a>Modificar uma exceção de número

Neste exemplo, o parâmetro-Identity é obrigatório. O ```Set-CsTenantBlockedNumberExceptionPattern``` cmdlet permite modificar um ou mais parâmetros para uma determinada identidade de padrão de número.
 
```powershell
Set-CsTenantBlockedNumberExceptionPattern -Identity <XdsGlobalRelativeIdentity> -Tenant <GUID> -Enabled <bool> -Description <string> -Pattern <string> 
```

```powershell
Set-CsTenantBlockedNumberExceptionPattern -Identity InternationalPrefix -Tenant daacb588-18ef-4f77-8c83-955af9615930  -Pattern "^022(\d*)$" 
```

#### <a name="remove-a-number-exception"></a>Remover uma exceção de número

Neste exemplo, o ```-Identity``` parâmetro é obrigatório. Esse cmdlet removerá o padrão de número especificado da lista de locatários.  Se a identidade não for conhecida, use ```Get-CsInboundBlockedNumberPattern``` o cmdlet para primeiro localizar o padrão apropriado e anotar a identidade. Em seguida, execute ```Remove-CsTenantBlockedNumberExceptionPattern``` o cmdlet e transmita o valor de identidade apropriado.Aguarde tempo para a replicação antes de testar e validar.  

```powershell
Remove-CsTenantBlockedNumberExceptionPattern -Identity <XdsGlobalRelativeIdentity> -Tenant <GUID>
```

```powershell
Remove-CsTenantBlockedNumberExceptionPattern -Identity InternationalPrefix -Tenant daacb588-18ef-4f77-8c83-955af9615930
```

### <a name="test-whether-a-number-is-blocked"></a>Testar se um número está bloqueado

Use o ```Test-CsInboundBlockedNumberPattern``` cmdlet para verificar se um número está bloqueado no locatário.
 
Neste exemplo, os ```-Phonenumber``` parâmetros e ```-Tenant``` são obrigatórios. O ```-PhoneNumber``` parâmetro deve ser uma cadeia de caracteres numérica sem caracteres adicionais, como + ou-. No TRPS, o ```-Tenant parameter``` é opcional. O parâmetro ```isNumberBlocked``` resultante retornará um valor de true se o número estiver bloqueado no locatário e falso se não estiver bloqueado.

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

## <a name="related-topics"></a>Tópicos relacionados

- [Configurar seu computador para gerenciar o Skype for Business online usando o Windows PowerShell](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
