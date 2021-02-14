---
title: Bloquear chamadas de entrada no Skype for Business Online
ms.author: v-cichur
author: cichur
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
ms.openlocfilehash: 16a646af3e456bb68a2a582cad7d6b742100c650
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49820911"
---
# <a name="block-inbound-calls"></a>Bloquear chamadas de entrada

Os Planos de Chamada do Skype for Business Online agora são compatíveis com o bloqueio de chamadas de entrada da PSTN (rede telefônica pública comutado). Esse recurso permite que uma lista global de padrões de número do locatário seja definida para que a ID de chamadas de cada chamada PSTN recebida para o locatário possa ser verificada na lista para uma combinação. Se uma combinação for feita, uma chamada de entrada será rejeitada.

Esse recurso de bloqueio de chamada de entrada só funciona em chamadas de entrada que se originam do PSTN e só funcionam no nível global do locatário. Ele não está disponível por usuário.  

Este recurso ainda não está disponível para Roteamento Direto.

>[!NOTE]
> Os chamadores bloqueados podem ter comportamentos ligeiramente diferentes quando foram bloqueados. O comportamento se baseia em como a operadora do chamador bloqueado lida com a notificação de que a chamada não tem permissão para ser concluída com êxito. Exemplos podem incluir uma mensagem de operadora informando que a chamada não pode ser concluída como discada ou simplesmente soltando a chamada.

## <a name="call-blocking-admin-controls-and-information"></a>Informações e controles de administração de bloqueio de chamada

Os controles de administração para bloquear números são fornecidos apenas usando o PowerShell. Os padrões de blocos de números são definidos como padrões de expressão regulares. A ordem das expressões não é importante: o primeiro padrão que é corresponder à lista faz com que a chamada seja bloqueada. Um novo número ou padrão adicionado ou removido na lista de chamadores bloqueados pode levar até 24 horas para que o padrão se torne ativo.

## <a name="call-blocking-powershell-commands"></a>Comandos de bloqueio de chamada do PowerShell

Os padrões de número são ```CsInboundBlockedNumberPattern``` gerenciados por meio dos ```New``` ```Get``` ```Set``` comandos, e ```Remove``` . Você pode gerenciar um determinado padrão usando esses cmdlets, incluindo a capacidade de alternar a ativação de um determinado padrão.
- [Get-CsInboundBlockedNumberPattern](https://docs.microsoft.com/powershell/module/skype/get-csinboundblockednumberpattern) retorna uma lista de todos os padrões de números bloqueados adicionados à lista de locatários, incluindo Nome, Descrição, Habilitado (Verdadeiro/Falso) e Padrão para cada um.
- [New-CsInboundBlockedNumberPattern adiciona](https://docs.microsoft.com/powershell/module/skype/new-csinboundblockednumberpattern) um padrão de número bloqueado à lista de locatários.
- [Remove-CsInboundBlockedNumberPattern](https://docs.microsoft.com/powershell/module/skype/remove-csinboundblockednumberpattern) remove um padrão de número bloqueado da lista de locatários.
- [Set-CsInboundBlockedNumberPattern](https://docs.microsoft.com/powershell/module/skype/set-csinboundblockednumberpattern) modifica um ou mais parâmetros de um padrão de número bloqueado na lista de locatários.

A exibição e a ativação de todo o recurso de bloqueio de chamada são gerenciados por meio ```CsTenantBlockingCallingNumbers``` dos comandos ```Get``` ```Set``` e.

- [Get-CsTenantBlockedCallingNumbers](https://docs.microsoft.com/powershell/module/skype/get-cstenantblockedcallingnumbers) retorna os parâmetros da lista de números bloqueados global, incluindo Habilitado (Verdadeiro/Falso). Há uma única política global de locatário que não pode ser modificada manualmente além de ativar ou desativar o recurso.
- [O Set-CsTenantBlockedCallingNumbers](https://docs.microsoft.com/powershell/module/skype/set-cstenantblockedcallingnumbers) permite que a modificação das chamadas global bloqueadas pelo locatário sejam 2010 e 2010 no nível do locatário.

### <a name="examples"></a>Exemplos

#### <a name="block-a-number"></a>Bloquear um número

Neste exemplo, os ```-Enabled``` parâmetros e os ```-Description``` parâmetros são opcionais:

```powershell
New-CsInboundBlockedNumberPattern -Name “<name>” -Enabled $True -Description “<description>” -Pattern “^[+]?13125550000”
```

A criação de um novo padrão adiciona o padrão conforme habilitado por padrão. A descrição é um campo opcional para fornecer mais informações.

Recomendamos que você forneça um nome significativo para entender facilmente por que o padrão foi adicionado. No caso de simplesmente bloquear números de spam, considere nomear a regra da mesma forma que o padrão de número que está sendo corresponder e adicionar informações adicionais na descrição conforme necessário.

Os padrões são corresponderem usando Expressões Regulares (Regex). Permitir tempo para replicação antes de testar e validar.

#### <a name="allow-a-number"></a>Permitir um número

Neste exemplo, o ```-Identity``` parâmetro é necessário:

```powershell
Remove-CsInboundBlockedNumberPattern -Identity “<identity>”
```
 
Se a identidade não for conhecida, use o cmdlet para localizar primeiro o padrão ```Get-CsInboundBlockedNumberPattern``` adequado e anote a identidade. Em seguida, execute o ```Remove-CsTenantBlockedNumberPattern``` cmdlet e passe o valor de identidade apropriado.

Permitir tempo para replicação antes de testar e validar.

#### <a name="view-all-number-patterns"></a>Exibir todos os padrões de número

Executar este cmdlet retorna uma lista de todos os números bloqueados inseridos para um locatário:

```powershell
Get-CsInboundBlockedNumberPattern
```

Use as habilidades de filtragem do PowerShell para analisar os valores retornados conforme necessário.

## <a name="add-number-exceptions"></a>Adicionar exceções de número

Você pode adicionar exceções a padrões de números bloqueados por meio dos ```CsTenantBlockNumberExceptionPattern``` ```New``` ```Get``` comandos, , ```Set``` e ```Remove``` .

- [New-CsTenantBlockedNumberExceptionPattern adiciona](https://docs.microsoft.com/powershell/module/skype/new-cstenantblockednumberexceptionpattern) um padrão de exceção de número à lista de locatários. 
- [Get-CsTenantBlockedNumberExceptionPattern](https://docs.microsoft.com/powershell/module/skype/get-cstenantblockednumberexceptionpattern) retorna uma lista de todos os padrões de exceção de número adicionados à lista de locatários.
- [Set-CsTenantBlockedNumberExceptionPattern](https://docs.microsoft.com/powershell/module/skype/set-cstenantblockednumberexceptionpattern) modifica um ou mais parâmetros para um padrão de exceção de número na lista de locatários.
- [Remove-CsTenantBlockedNumberExceptionPattern](https://docs.microsoft.com/powershell/module/skype/remove-cstenantblockednumberexceptionpattern) remove um padrão de exceção de número da lista de locatários.

### <a name="examples"></a>Exemplos

#### <a name="add-a-number-exception"></a>Adicionar uma exceção de número

Neste exemplo, um novo padrão de exceção de número é criado e adicionará por padrão o padrão conforme habilitado. Os ```-Enabled``` ```-Description``` parâmetros e os parâmetros são opcionais.

```powershell
New-CsTenantBlockedNumberExceptionPattern -Identity <XdsGlobalRelativeIdentity> -Tenant <GUID> -Pattern <String> -Enabled <bool> -Description <string>
```

```powershell
New-CsTenantBlockedNumberExceptionPattern -Identity InternationalPrefix -Tenant daacb588-18ef-4f77-8c83-955af9615930 -Pattern "^011(\d*)$" -Description "Allow international prefix in US"  
```

#### <a name="view-all-number-exceptions"></a>Exibir todas as exceções de número

Neste exemplo, o parâmetro -Identity é opcional. Se o parâmetro não for especificado, esse cmdlet retornará uma lista de todos os padrões de exceção de número ```-Identity``` inseridos para um locatário.
 
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

Neste exemplo, o ```-Identity``` parâmetro é necessário. Esse cmdlet removerá o padrão de número determinado da lista de locatários.  Se a identidade não for conhecida, use o cmdlet para localizar primeiro o padrão ```Get-CsInboundBlockedNumberPattern``` adequado e anote a identidade. Em seguida, execute o ```Remove-CsTenantBlockedNumberExceptionPattern``` cmdlet e passe o valor de identidade apropriado.Permitir tempo para replicação antes de testar e validar.  

```powershell
Remove-CsTenantBlockedNumberExceptionPattern -Identity <XdsGlobalRelativeIdentity> -Tenant <GUID>
```

```powershell
Remove-CsTenantBlockedNumberExceptionPattern -Identity InternationalPrefix -Tenant daacb588-18ef-4f77-8c83-955af9615930
```

### <a name="test-whether-a-number-is-blocked"></a>Testar se um número está bloqueado

Use o ```Test-CsInboundBlockedNumberPattern``` cmdlet para verificar se um número está bloqueado no locatário.
 
Neste exemplo, os parâmetros e ```-Phonenumber``` ```-Tenant``` os parâmetros são necessários. O ```-PhoneNumber``` parâmetro deve ser uma cadeia numérica sem caracteres adicionais, como + ou -. Em TRPS, a ```-Tenant parameter``` opção é opcional. O parâmetro resultante retornará um valor verdadeiro se o número for bloqueado no locatário e ```isNumberBlocked``` Falso se ele não estiver bloqueado.

```powershell
Test-CsInboundBlockedNumberPattern –Tenant <GUID> -PhoneNumber <String>
```

```powershell
Test-CsInboundBlockedNumberPattern -Tenant e09ad6bc-1d3c-4650-8cae-02f6c5a04b45 -PhoneNumber 4255550101
```

|httpResponseCode  |isNumberBlocked   |Errormessage |
|---------|---------|---------|
|200    | Verdadeiro        |         |

```powershell
Test-CsInboundBlockedNumberPattern -Tenant e09ad6bc-1d3c-4650-8cae-02f6c5a04b45 -PhoneNumber 6045550188
```

|httpResponseCode  |isNumberBlocked   |Errormessage |
|---------|---------|---------|
|200    | Falso        |         |

## <a name="a-note-about-regex"></a>Uma anotação sobre Regex

Conforme declarado anteriormente, a correspondência de padrões para bloquear chamadores é feita usando Regex. Várias ferramentas estão disponíveis online para ajudar a validar uma combinação de padrões Regex. Se você não estiver familiarizado com padrões Regex, recomendamos que você tire um tempo para se familiarizar com as noções básicas. Para garantir que você receba os resultados esperados, use uma ferramenta para validar as combinações de padrão antes de adicionar novas combinações de números bloqueados ao seu locatário. 

## <a name="related-topics"></a>Tópicos relacionados

- [Configurar seu computador para gerenciar o Skype for Business Online usando o Windows PowerShell](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
