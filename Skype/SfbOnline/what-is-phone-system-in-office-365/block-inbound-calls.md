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
ms.openlocfilehash: dae0d585df2f67904712e9220f16213a2f925369
ms.sourcegitcommit: 7ebcff93ecbdc064414d7110e182b29371ca4f1f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/06/2021
ms.locfileid: "52238027"
---
# <a name="block-inbound-calls"></a><span data-ttu-id="3e03a-102">Bloquear chamadas de entrada</span><span class="sxs-lookup"><span data-stu-id="3e03a-102">Block inbound calls</span></span>

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

<span data-ttu-id="3e03a-103">Skype for Business Os Planos de Chamadas Online agora suportam o bloqueio de chamadas de entrada da PSTN (rede telefônica pública comutado).</span><span class="sxs-lookup"><span data-stu-id="3e03a-103">Skype for Business Online Calling Plans now supports blocking of inbound calls from the public switched telephone network (PSTN).</span></span> <span data-ttu-id="3e03a-104">Esse recurso permite que uma lista global de locatários de padrões de números seja definida para que a ID do chamador de cada chamada PSTN de entrada para o locatário possa ser verificada na lista para uma combinação.</span><span class="sxs-lookup"><span data-stu-id="3e03a-104">This feature allows a tenant global list of number patterns to be defined so that the caller ID of every incoming PSTN call to the tenant can be checked against the list for a match.</span></span> <span data-ttu-id="3e03a-105">Se uma combinação for feita, uma chamada de entrada será rejeitada.</span><span class="sxs-lookup"><span data-stu-id="3e03a-105">If a match is made, an incoming call is rejected.</span></span>

<span data-ttu-id="3e03a-106">Esse recurso de bloqueio de chamadas de entrada só funciona em chamadas de entrada que se originam da PSTN e só funcionam em uma base global do locatário.</span><span class="sxs-lookup"><span data-stu-id="3e03a-106">This inbound call blocking feature only works on inbound calls that originate from the PSTN and only works on a tenant-global basis.</span></span> <span data-ttu-id="3e03a-107">Ele não está disponível por usuário.</span><span class="sxs-lookup"><span data-stu-id="3e03a-107">It's not available on a per-user basis.</span></span>  

<span data-ttu-id="3e03a-108">Esse recurso ainda não está disponível para Roteamento Direto.</span><span class="sxs-lookup"><span data-stu-id="3e03a-108">This feature isn't yet available for Direct Routing.</span></span>

>[!NOTE]
> <span data-ttu-id="3e03a-109">Os chamadores bloqueados podem ter comportamentos ligeiramente diferentes quando foram bloqueados.</span><span class="sxs-lookup"><span data-stu-id="3e03a-109">Blocked callers may experience slightly different behaviors when they have been blocked.</span></span> <span data-ttu-id="3e03a-110">O comportamento se baseia em como a operadora do chamador bloqueado lida com a notificação de que a chamada não tem permissão para ser concluída com êxito.</span><span class="sxs-lookup"><span data-stu-id="3e03a-110">The behavior is based on how the blocked caller’s carrier handles the notification that the call isn't allowed to be successfully completed.</span></span> <span data-ttu-id="3e03a-111">Exemplos podem incluir uma mensagem de operadora informando que a chamada não pode ser concluída como discada ou simplesmente soltando a chamada.</span><span class="sxs-lookup"><span data-stu-id="3e03a-111">Examples may include a carrier message stating the call can't be completed as dialed, or simply dropping the call.</span></span>

## <a name="call-blocking-admin-controls-and-information"></a><span data-ttu-id="3e03a-112">Informações e controles de administrador de bloqueio de chamada</span><span class="sxs-lookup"><span data-stu-id="3e03a-112">Call blocking admin controls and information</span></span>

<span data-ttu-id="3e03a-113">Os controles de administrador para números de bloqueio são fornecidos usando apenas o PowerShell.</span><span class="sxs-lookup"><span data-stu-id="3e03a-113">Admin controls for blocking numbers are provided using PowerShell only.</span></span> <span data-ttu-id="3e03a-114">Padrões de bloco de números são definidos como padrões de expressão regulares.</span><span class="sxs-lookup"><span data-stu-id="3e03a-114">Number block patterns are defined as regular expression patterns.</span></span> <span data-ttu-id="3e03a-115">A ordem das expressões não é importante – o primeiro padrão que é matched na lista resulta no bloqueio da chamada.</span><span class="sxs-lookup"><span data-stu-id="3e03a-115">The order of the expressions is unimportant – the first pattern matched in the list results in the call being blocked.</span></span> <span data-ttu-id="3e03a-116">Um novo número ou padrão adicionado ou removido na lista de chamadores bloqueados pode levar até 24 horas para que o padrão se torne ativo.</span><span class="sxs-lookup"><span data-stu-id="3e03a-116">A new number or pattern that's added or removed in the blocked callers list may take up to 24 hours for the pattern to become active.</span></span>

## <a name="call-blocking-powershell-commands"></a><span data-ttu-id="3e03a-117">Comandos de bloqueio de chamada do PowerShell</span><span class="sxs-lookup"><span data-stu-id="3e03a-117">Call blocking PowerShell commands</span></span>

<span data-ttu-id="3e03a-118">Os padrões de números são ```CsInboundBlockedNumberPattern``` gerenciados por meio dos ```New``` comandos , , e ```Get``` ```Set``` ```Remove``` .</span><span class="sxs-lookup"><span data-stu-id="3e03a-118">Number patterns are managed through the ```CsInboundBlockedNumberPattern``` commands ```New```, ```Get```, ```Set```, and ```Remove```.</span></span> <span data-ttu-id="3e03a-119">Você pode gerenciar um determinado padrão usando esses cmdlets, incluindo a capacidade de alternar a ativação de um determinado padrão.</span><span class="sxs-lookup"><span data-stu-id="3e03a-119">You can manage a given pattern by using these cmdlets, including the ability to toggle the activation of a given pattern.</span></span>
- <span data-ttu-id="3e03a-120">[Get-CsInboundBlockedNumberPattern](/powershell/module/skype/get-csinboundblockednumberpattern) retorna uma lista de todos os padrões de números bloqueados adicionados à lista de locatários, incluindo Nome, Descrição, Habilitado (True/False) e Padrão para cada um.</span><span class="sxs-lookup"><span data-stu-id="3e03a-120">[Get-CsInboundBlockedNumberPattern](/powershell/module/skype/get-csinboundblockednumberpattern) returns a list of all blocked number patterns added to the tenant list including Name, Description, Enabled (True/False), and Pattern for each.</span></span>
- <span data-ttu-id="3e03a-121">[New-CsInboundBlockedNumberPattern](/powershell/module/skype/new-csinboundblockednumberpattern) adiciona um padrão de número bloqueado à lista de locatários.</span><span class="sxs-lookup"><span data-stu-id="3e03a-121">[New-CsInboundBlockedNumberPattern](/powershell/module/skype/new-csinboundblockednumberpattern) adds a blocked number pattern to the tenant list.</span></span>
- <span data-ttu-id="3e03a-122">[Remove-CsInboundBlockedNumberPattern](/powershell/module/skype/remove-csinboundblockednumberpattern) remove um padrão de número bloqueado da lista de locatários.</span><span class="sxs-lookup"><span data-stu-id="3e03a-122">[Remove-CsInboundBlockedNumberPattern](/powershell/module/skype/remove-csinboundblockednumberpattern) removes a blocked number pattern from the tenant list.</span></span>
- <span data-ttu-id="3e03a-123">[Set-CsInboundBlockedNumberPattern](/powershell/module/skype/set-csinboundblockednumberpattern) modifica um ou mais parâmetros de um padrão de número bloqueado na lista de locatários.</span><span class="sxs-lookup"><span data-stu-id="3e03a-123">[Set-CsInboundBlockedNumberPattern](/powershell/module/skype/set-csinboundblockednumberpattern) modifies one or more parameters of a blocked number pattern in the tenant list.</span></span>

<span data-ttu-id="3e03a-124">A exibição e a ativação de todo o recurso de bloqueio de chamada é gerenciada por meio dos ```CsTenantBlockingCallingNumbers``` comandos ```Get``` e ```Set``` .</span><span class="sxs-lookup"><span data-stu-id="3e03a-124">Viewing and activating the entire call blocking feature is managed through the ```CsTenantBlockingCallingNumbers``` commands ```Get``` and ```Set```.</span></span>

- <span data-ttu-id="3e03a-125">[Get-CsTenantBlockedCallingNumbers](/powershell/module/skype/get-cstenantblockedcallingnumbers) retorna os parâmetros da lista de números bloqueados global, incluindo Enabled (True/False).</span><span class="sxs-lookup"><span data-stu-id="3e03a-125">[Get-CsTenantBlockedCallingNumbers](/powershell/module/skype/get-cstenantblockedcallingnumbers) returns the parameters for the global blocked number list including Enabled (True/False).</span></span> <span data-ttu-id="3e03a-126">Há uma única política de locatário global que não pode ser modificada manualmente, além de ativar ou desativar o recurso.</span><span class="sxs-lookup"><span data-stu-id="3e03a-126">There's a single global tenant policy that can't be modified manually other than to turn the feature on or off.</span></span>
- <span data-ttu-id="3e03a-127">[Set-CsTenantBlockedCallingNumbers](/powershell/module/skype/set-cstenantblockedcallingnumbers) permite modificar as chamadas de locatário global bloqueadas para serem ativas e desligadas no nível do locatário.</span><span class="sxs-lookup"><span data-stu-id="3e03a-127">[Set-CsTenantBlockedCallingNumbers](/powershell/module/skype/set-cstenantblockedcallingnumbers) allows modifying the global tenant blocked calls to be turned on and off at the tenant level.</span></span>

### <a name="examples"></a><span data-ttu-id="3e03a-128">Exemplos</span><span class="sxs-lookup"><span data-stu-id="3e03a-128">Examples</span></span>

#### <a name="block-a-number"></a><span data-ttu-id="3e03a-129">Bloquear um número</span><span class="sxs-lookup"><span data-stu-id="3e03a-129">Block a number</span></span>

<span data-ttu-id="3e03a-130">Neste exemplo, os ```-Enabled``` parâmetros e ```-Description``` são opcionais:</span><span class="sxs-lookup"><span data-stu-id="3e03a-130">In this example, the ```-Enabled``` and ```-Description``` parameters are optional:</span></span>

```powershell
New-CsInboundBlockedNumberPattern -Name “<name>” -Enabled $True -Description “<description>” -Pattern “^[+]?13125550000”
```

<span data-ttu-id="3e03a-131">A criação de um novo padrão adiciona o padrão conforme habilitado por padrão.</span><span class="sxs-lookup"><span data-stu-id="3e03a-131">Creating a new pattern adds the pattern as enabled by default.</span></span> <span data-ttu-id="3e03a-132">A descrição é um campo opcional para fornecer mais informações.</span><span class="sxs-lookup"><span data-stu-id="3e03a-132">The description is an optional field to provide more information.</span></span>

<span data-ttu-id="3e03a-133">Recomendamos que você forneça um nome significativo para entender facilmente por que o padrão foi adicionado.</span><span class="sxs-lookup"><span data-stu-id="3e03a-133">We recommend that you provide a meaningful name to easily understand why the pattern was added.</span></span> <span data-ttu-id="3e03a-134">No caso de simplesmente bloquear números de spam, considere nomear a regra da mesma forma que o padrão de número que está sendo corresponder e adicionar informações adicionais na descrição conforme necessário.</span><span class="sxs-lookup"><span data-stu-id="3e03a-134">In the case of simply blocking spam numbers, consider naming the rule the same as the number pattern that's being matched and add additional information in the description as required.</span></span>

<span data-ttu-id="3e03a-135">Os padrões são corresponderem usando Expressões Regulares (Regex).</span><span class="sxs-lookup"><span data-stu-id="3e03a-135">Patterns are matched using Regular Expressions (Regex).</span></span> <span data-ttu-id="3e03a-136">Permitir tempo para replicação antes de testar e validar.</span><span class="sxs-lookup"><span data-stu-id="3e03a-136">Allow time for replication before you test and validate.</span></span>

#### <a name="allow-a-number"></a><span data-ttu-id="3e03a-137">Permitir um número</span><span class="sxs-lookup"><span data-stu-id="3e03a-137">Allow a number</span></span>

<span data-ttu-id="3e03a-138">Neste exemplo, o ```-Identity``` parâmetro é necessário:</span><span class="sxs-lookup"><span data-stu-id="3e03a-138">In this example, the ```-Identity``` parameter is required:</span></span>

```powershell
Remove-CsInboundBlockedNumberPattern -Identity “<identity>”
```
 
<span data-ttu-id="3e03a-139">Se a identidade não for conhecida, use o ```Get-CsInboundBlockedNumberPattern``` cmdlet para primeiro localizar o padrão adequado e observar a identidade.</span><span class="sxs-lookup"><span data-stu-id="3e03a-139">If the identity isn't known, use the ```Get-CsInboundBlockedNumberPattern``` cmdlet to first locate the proper pattern and note the identity.</span></span> <span data-ttu-id="3e03a-140">Em seguida, execute ```Remove-CsTenantBlockedNumberPattern``` o cmdlet e passe o valor de identidade apropriado.</span><span class="sxs-lookup"><span data-stu-id="3e03a-140">Then, run the ```Remove-CsTenantBlockedNumberPattern``` cmdlet and pass the appropriate identity value.</span></span>

<span data-ttu-id="3e03a-141">Permitir tempo para replicação antes de testar e validar.</span><span class="sxs-lookup"><span data-stu-id="3e03a-141">Allow time for replication before you test and validate.</span></span>

#### <a name="view-all-number-patterns"></a><span data-ttu-id="3e03a-142">Exibir todos os padrões de números</span><span class="sxs-lookup"><span data-stu-id="3e03a-142">View all number patterns</span></span>

<span data-ttu-id="3e03a-143">Executar este cmdlet retorna uma lista de todos os números bloqueados inseridos para um locatário:</span><span class="sxs-lookup"><span data-stu-id="3e03a-143">Running this cmdlet returns a list of all blocked numbers that are entered for a tenant:</span></span>

```powershell
Get-CsInboundBlockedNumberPattern
```

<span data-ttu-id="3e03a-144">Use as habilidades de filtragem do PowerShell integrados para analisar os valores retornados conforme necessário.</span><span class="sxs-lookup"><span data-stu-id="3e03a-144">Use built-in PowerShell filtering abilities to parse the returned values as required.</span></span>

## <a name="add-number-exceptions"></a><span data-ttu-id="3e03a-145">Adicionar exceções de número</span><span class="sxs-lookup"><span data-stu-id="3e03a-145">Add number exceptions</span></span>

<span data-ttu-id="3e03a-146">Você pode adicionar exceções a padrões de números bloqueados por meio dos ```CsTenantBlockNumberExceptionPattern``` ```New``` comandos, ```Get``` , , e ```Set``` ```Remove``` .</span><span class="sxs-lookup"><span data-stu-id="3e03a-146">You can add exceptions to blocked number patterns through the ```CsTenantBlockNumberExceptionPattern``` commands, ```New```, ```Get```, ```Set```, and ```Remove```.</span></span>

- <span data-ttu-id="3e03a-147">[New-CsTenantBlockedNumberExceptionPattern](/powershell/module/skype/new-cstenantblockednumberexceptionpattern) adiciona um padrão de exceção de número à lista de locatários.</span><span class="sxs-lookup"><span data-stu-id="3e03a-147">[New-CsTenantBlockedNumberExceptionPattern](/powershell/module/skype/new-cstenantblockednumberexceptionpattern) adds a number exception pattern to the tenant list.</span></span> 
- <span data-ttu-id="3e03a-148">[Get-CsTenantBlockedNumberExceptionPattern](/powershell/module/skype/get-cstenantblockednumberexceptionpattern) retorna uma lista de todos os padrões de exceção de número adicionados à lista de locatários.</span><span class="sxs-lookup"><span data-stu-id="3e03a-148">[Get-CsTenantBlockedNumberExceptionPattern](/powershell/module/skype/get-cstenantblockednumberexceptionpattern) returns a list of all number exception patterns added to the tenant list.</span></span>
- <span data-ttu-id="3e03a-149">[Set-CsTenantBlockedNumberExceptionPattern](/powershell/module/skype/set-cstenantblockednumberexceptionpattern) modifica um ou mais parâmetros para um padrão de exceção de número na lista de locatários.</span><span class="sxs-lookup"><span data-stu-id="3e03a-149">[Set-CsTenantBlockedNumberExceptionPattern](/powershell/module/skype/set-cstenantblockednumberexceptionpattern) modifies one or more parameters to a number exception pattern in the tenant list.</span></span>
- <span data-ttu-id="3e03a-150">[Remove-CsTenantBlockedNumberExceptionPattern](/powershell/module/skype/remove-cstenantblockednumberexceptionpattern) remove um padrão de exceção de número da lista de locatários.</span><span class="sxs-lookup"><span data-stu-id="3e03a-150">[Remove-CsTenantBlockedNumberExceptionPattern](/powershell/module/skype/remove-cstenantblockednumberexceptionpattern) removes a number exception pattern from the tenant list.</span></span>

### <a name="examples"></a><span data-ttu-id="3e03a-151">Exemplos</span><span class="sxs-lookup"><span data-stu-id="3e03a-151">Examples</span></span>

#### <a name="add-a-number-exception"></a><span data-ttu-id="3e03a-152">Adicionar uma exceção de número</span><span class="sxs-lookup"><span data-stu-id="3e03a-152">Add a number exception</span></span>

<span data-ttu-id="3e03a-153">Neste exemplo, um novo padrão de exceção de número é criado e, por padrão, adicionará o padrão conforme habilitado.</span><span class="sxs-lookup"><span data-stu-id="3e03a-153">In this example, a new number exception pattern is created and will by default add the pattern as enabled.</span></span> <span data-ttu-id="3e03a-154">Os ```-Enabled``` ```-Description``` parâmetros e são opcionais.</span><span class="sxs-lookup"><span data-stu-id="3e03a-154">The ```-Enabled``` and ```-Description``` parameters are optional.</span></span>

```powershell
New-CsTenantBlockedNumberExceptionPattern -Identity <XdsGlobalRelativeIdentity> -Tenant <GUID> -Pattern <String> -Enabled <bool> -Description <string>
```

```powershell
New-CsTenantBlockedNumberExceptionPattern -Identity InternationalPrefix -Tenant daacb588-18ef-4f77-8c83-955af9615930 -Pattern "^011(\d*)$" -Description "Allow international prefix in US"  
```

#### <a name="view-all-number-exceptions"></a><span data-ttu-id="3e03a-155">Exibir todas as exceções de número</span><span class="sxs-lookup"><span data-stu-id="3e03a-155">View all number exceptions</span></span>

<span data-ttu-id="3e03a-156">Neste exemplo, o parâmetro -Identity é opcional.</span><span class="sxs-lookup"><span data-stu-id="3e03a-156">In this example, the -Identity parameter is optional.</span></span> <span data-ttu-id="3e03a-157">Se o parâmetro não for especificado, este cmdlet retornará uma lista de todos os padrões de exceção de número ```-Identity``` inseridos para um locatário.</span><span class="sxs-lookup"><span data-stu-id="3e03a-157">If the ```-Identity``` parameter isn't specified, this cmdlet returns a list of all number exception patterns entered for a tenant.</span></span>
 
```powershell
Get-CsTenantBlockedNumberExceptionPattern -Identity <XdsGlobalRelativeIdentity> -Tenant <GUID>
```
 
```powershell
Get-CsTenantBlockedNumberExceptionPattern -Tenant daacb588-18ef-4f77-8c83-955af9615930
```

#### <a name="modify-a-number-exception"></a><span data-ttu-id="3e03a-158">Modificar uma exceção de número</span><span class="sxs-lookup"><span data-stu-id="3e03a-158">Modify a number exception</span></span>

<span data-ttu-id="3e03a-159">Neste exemplo, o parâmetro -Identity é obrigatório.</span><span class="sxs-lookup"><span data-stu-id="3e03a-159">In this example, the -Identity parameter is mandatory.</span></span> <span data-ttu-id="3e03a-160">O ```Set-CsTenantBlockedNumberExceptionPattern``` cmdlet permite modificar um ou mais parâmetros para uma determinada identidade de padrão de número.</span><span class="sxs-lookup"><span data-stu-id="3e03a-160">The ```Set-CsTenantBlockedNumberExceptionPattern``` cmdlet lets you modify one or more parameters for a given number pattern identity.</span></span>
 
```powershell
Set-CsTenantBlockedNumberExceptionPattern -Identity <XdsGlobalRelativeIdentity> -Tenant <GUID> -Enabled <bool> -Description <string> -Pattern <string> 
```

```powershell
Set-CsTenantBlockedNumberExceptionPattern -Identity InternationalPrefix -Tenant daacb588-18ef-4f77-8c83-955af9615930  -Pattern "^022(\d*)$" 
```

#### <a name="remove-a-number-exception"></a><span data-ttu-id="3e03a-161">Remover uma exceção de número</span><span class="sxs-lookup"><span data-stu-id="3e03a-161">Remove a number exception</span></span>

<span data-ttu-id="3e03a-162">Neste exemplo, o ```-Identity``` parâmetro é necessário.</span><span class="sxs-lookup"><span data-stu-id="3e03a-162">In this example, the ```-Identity``` parameter is required.</span></span> <span data-ttu-id="3e03a-163">Este cmdlet removerá o padrão de número determinado da lista de locatários.</span><span class="sxs-lookup"><span data-stu-id="3e03a-163">This cmdlet will remove the given number pattern from the tenant list.</span></span>  <span data-ttu-id="3e03a-164">Se a identidade não for conhecida, use o ```Get-CsInboundBlockedNumberPattern``` cmdlet para primeiro localizar o padrão adequado e observar a identidade.</span><span class="sxs-lookup"><span data-stu-id="3e03a-164">If the identity isn't known, use the ```Get-CsInboundBlockedNumberPattern``` cmdlet to first locate the proper pattern and note the identity.</span></span> <span data-ttu-id="3e03a-165">Em seguida, execute ```Remove-CsTenantBlockedNumberExceptionPattern``` o cmdlet e passe o valor de identidade apropriado.</span><span class="sxs-lookup"><span data-stu-id="3e03a-165">Then, run the ```Remove-CsTenantBlockedNumberExceptionPattern``` cmdlet and pass the appropriate identity value.</span></span><span data-ttu-id="3e03a-166">Permitir tempo para replicação antes de testar e validar.</span><span class="sxs-lookup"><span data-stu-id="3e03a-166"> Allow time for replication before you test and validate.</span></span>  

```powershell
Remove-CsTenantBlockedNumberExceptionPattern -Identity <XdsGlobalRelativeIdentity> -Tenant <GUID>
```

```powershell
Remove-CsTenantBlockedNumberExceptionPattern -Identity InternationalPrefix -Tenant daacb588-18ef-4f77-8c83-955af9615930
```

### <a name="test-whether-a-number-is-blocked"></a><span data-ttu-id="3e03a-167">Testar se um número está bloqueado</span><span class="sxs-lookup"><span data-stu-id="3e03a-167">Test whether a number is blocked</span></span>

<span data-ttu-id="3e03a-168">Use o ```Test-CsInboundBlockedNumberPattern``` cmdlet para verificar se um número está bloqueado no locatário.</span><span class="sxs-lookup"><span data-stu-id="3e03a-168">Use the ```Test-CsInboundBlockedNumberPattern``` cmdlet to verify whether a number is blocked in the tenant.</span></span>
 
<span data-ttu-id="3e03a-169">Neste exemplo, os ```-Phonenumber``` ```-Tenant``` parâmetros e são necessários.</span><span class="sxs-lookup"><span data-stu-id="3e03a-169">In this example, the ```-Phonenumber``` and ```-Tenant``` parameters are required.</span></span> <span data-ttu-id="3e03a-170">O ```-PhoneNumber``` parâmetro deve ser uma cadeia de caracteres numérica sem caracteres adicionais, como + ou -.</span><span class="sxs-lookup"><span data-stu-id="3e03a-170">The ```-PhoneNumber``` parameter should be a numeric string without any additional characters such as + or -.</span></span> <span data-ttu-id="3e03a-171">No TRPS, o ```-Tenant parameter``` é opcional.</span><span class="sxs-lookup"><span data-stu-id="3e03a-171">In TRPS, the ```-Tenant parameter``` is optional.</span></span> <span data-ttu-id="3e03a-172">O parâmetro resultante retornará um valor True se o número for bloqueado no locatário e ```isNumberBlocked``` False se ele não estiver bloqueado.</span><span class="sxs-lookup"><span data-stu-id="3e03a-172">The resulting ```isNumberBlocked``` parameter returns a value of True if the number is blocked in the tenant and False if it's not blocked.</span></span>

```powershell
Test-CsInboundBlockedNumberPattern –Tenant <GUID> -PhoneNumber <String>
```

```powershell
Test-CsInboundBlockedNumberPattern -Tenant e09ad6bc-1d3c-4650-8cae-02f6c5a04b45 -PhoneNumber 4255550101
```

|<span data-ttu-id="3e03a-173">httpResponseCode</span><span class="sxs-lookup"><span data-stu-id="3e03a-173">httpResponseCode</span></span>  |<span data-ttu-id="3e03a-174">isNumberBlocked</span><span class="sxs-lookup"><span data-stu-id="3e03a-174">isNumberBlocked</span></span>   |<span data-ttu-id="3e03a-175">errorMessage</span><span class="sxs-lookup"><span data-stu-id="3e03a-175">errorMessage</span></span> |
|---------|---------|---------|
|<span data-ttu-id="3e03a-176">200</span><span class="sxs-lookup"><span data-stu-id="3e03a-176">200</span></span>    | <span data-ttu-id="3e03a-177">Verdadeiro</span><span class="sxs-lookup"><span data-stu-id="3e03a-177">True</span></span>        |         |

```powershell
Test-CsInboundBlockedNumberPattern -Tenant e09ad6bc-1d3c-4650-8cae-02f6c5a04b45 -PhoneNumber 6045550188
```

|<span data-ttu-id="3e03a-178">httpResponseCode</span><span class="sxs-lookup"><span data-stu-id="3e03a-178">httpResponseCode</span></span>  |<span data-ttu-id="3e03a-179">isNumberBlocked</span><span class="sxs-lookup"><span data-stu-id="3e03a-179">isNumberBlocked</span></span>   |<span data-ttu-id="3e03a-180">errorMessage</span><span class="sxs-lookup"><span data-stu-id="3e03a-180">errorMessage</span></span> |
|---------|---------|---------|
|<span data-ttu-id="3e03a-181">200</span><span class="sxs-lookup"><span data-stu-id="3e03a-181">200</span></span>    | <span data-ttu-id="3e03a-182">Falso</span><span class="sxs-lookup"><span data-stu-id="3e03a-182">False</span></span>        |         |

## <a name="a-note-about-regex"></a><span data-ttu-id="3e03a-183">Uma observação sobre Regex</span><span class="sxs-lookup"><span data-stu-id="3e03a-183">A note about Regex</span></span>

<span data-ttu-id="3e03a-184">Conforme dito anteriormente, a correspondência de padrão para bloquear chamadores é feita usando Regex.</span><span class="sxs-lookup"><span data-stu-id="3e03a-184">As stated earlier, the pattern matching for blocking callers is done by using Regex.</span></span> <span data-ttu-id="3e03a-185">Várias ferramentas estão disponíveis online para ajudar a validar uma combinação de padrão regex.</span><span class="sxs-lookup"><span data-stu-id="3e03a-185">Multiple tools are available online to help validate a Regex pattern match.</span></span> <span data-ttu-id="3e03a-186">Se você não estiver familiarizado com os padrões Regex, recomendamos que você leve algum tempo para se familiarizar com os conceitos básicos.</span><span class="sxs-lookup"><span data-stu-id="3e03a-186">If you aren't familiar with Regex patterns, we recommend that you take some time to familiarize yourself with the basics.</span></span> <span data-ttu-id="3e03a-187">Para garantir que você receba os resultados esperados, use uma ferramenta para validar as correspondeções de padrão antes de adicionar novas combinações de número bloqueado ao seu locatário.</span><span class="sxs-lookup"><span data-stu-id="3e03a-187">To make sure you get expected results, use a tool for validating pattern matches before you add new blocked number matches to your tenant.</span></span> 

## <a name="related-topics"></a><span data-ttu-id="3e03a-188">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="3e03a-188">Related topics</span></span>

- [<span data-ttu-id="3e03a-189">Configurar seu computador para gerenciar o Skype for Business Online usando Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="3e03a-189">Set up your computer to manage Skype for Business Online by using Windows PowerShell</span></span>](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
