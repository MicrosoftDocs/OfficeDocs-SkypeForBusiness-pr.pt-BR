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
# <a name="block-inbound-calls"></a><span data-ttu-id="5c41d-102">Bloquear chamadas recebidas</span><span class="sxs-lookup"><span data-stu-id="5c41d-102">Block inbound calls</span></span>

<span data-ttu-id="5c41d-103">Agora, os planos de chamadas do Skype for Business online dão suporte ao bloqueio de chamadas recebidas da PSTN (rede telefônica pública comutada).</span><span class="sxs-lookup"><span data-stu-id="5c41d-103">Skype for Business Online Calling Plans now supports blocking of inbound calls from the public switched telephone network (PSTN).</span></span> <span data-ttu-id="5c41d-104">Esse recurso permite que uma lista global de locatários de padrões de número seja definida para que a identificação de chamadas de todas as chamadas PSTN de entrada para o locatário possa ser verificada na lista para uma correspondência.</span><span class="sxs-lookup"><span data-stu-id="5c41d-104">This feature allows a tenant global list of number patterns to be defined so that the caller ID of every incoming PSTN call to the tenant can be checked against the list for a match.</span></span> <span data-ttu-id="5c41d-105">Se for feita uma correspondência, uma chamada de entrada será rejeitada.</span><span class="sxs-lookup"><span data-stu-id="5c41d-105">If a match is made, an incoming call is rejected.</span></span>

<span data-ttu-id="5c41d-106">Esse recurso de bloqueio de chamadas de entrada funciona apenas em chamadas de entrada que se originam da PSTN e só funciona em uma base global de locatários.</span><span class="sxs-lookup"><span data-stu-id="5c41d-106">This inbound call blocking feature only works on inbound calls that originate from the PSTN and only works on a tenant-global basis.</span></span> <span data-ttu-id="5c41d-107">Ele não está disponível para cada usuário.</span><span class="sxs-lookup"><span data-stu-id="5c41d-107">It's not available on a per-user basis.</span></span>  

<span data-ttu-id="5c41d-108">Este recurso ainda não está disponível para roteamento direto.</span><span class="sxs-lookup"><span data-stu-id="5c41d-108">This feature isn't yet available for Direct Routing.</span></span>

>[!NOTE]
> <span data-ttu-id="5c41d-109">Os chamadores bloqueados podem experimentar comportamentos ligeiramente diferentes quando foram bloqueados.</span><span class="sxs-lookup"><span data-stu-id="5c41d-109">Blocked callers may experience slightly different behaviors when they have been blocked.</span></span> <span data-ttu-id="5c41d-110">O comportamento é baseado em como a operadora do chamador bloqueado manipula a notificação de que a chamada não pode ser concluída com êxito.</span><span class="sxs-lookup"><span data-stu-id="5c41d-110">The behavior is based on how the blocked caller’s carrier handles the notification that the call isn't allowed to be successfully completed.</span></span> <span data-ttu-id="5c41d-111">Os exemplos podem incluir uma mensagem de portadora informando que a chamada não pode ser concluída como discada ou simplesmente descartando a chamada.</span><span class="sxs-lookup"><span data-stu-id="5c41d-111">Examples may include a carrier message stating the call can't be completed as dialed, or simply dropping the call.</span></span>

## <a name="call-blocking-admin-controls-and-information"></a><span data-ttu-id="5c41d-112">Informações e controles de administração do bloqueio de chamadas</span><span class="sxs-lookup"><span data-stu-id="5c41d-112">Call blocking admin controls and information</span></span>

<span data-ttu-id="5c41d-113">Os controles de administrador para bloquear números são fornecidos somente com o uso do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="5c41d-113">Admin controls for blocking numbers are provided using PowerShell only.</span></span> <span data-ttu-id="5c41d-114">Padrões de blocos de números são definidos como padrões de expressão regular.</span><span class="sxs-lookup"><span data-stu-id="5c41d-114">Number block patterns are defined as regular expression patterns.</span></span> <span data-ttu-id="5c41d-115">A ordem das expressões é não importante – o primeiro padrão correspondido na lista resulta na bloqueio da chamada.</span><span class="sxs-lookup"><span data-stu-id="5c41d-115">The order of the expressions is unimportant – the first pattern matched in the list results in the call being blocked.</span></span> <span data-ttu-id="5c41d-116">Um novo número ou padrão que é adicionado ou removido na lista de chamadores bloqueados pode levar até 24 horas para que o padrão se torne ativo.</span><span class="sxs-lookup"><span data-stu-id="5c41d-116">A new number or pattern that's added or removed in the blocked callers list may take up to 24 hours for the pattern to become active.</span></span>

## <a name="call-blocking-powershell-commands"></a><span data-ttu-id="5c41d-117">Comandos do PowerShell de bloqueio de chamadas</span><span class="sxs-lookup"><span data-stu-id="5c41d-117">Call blocking PowerShell commands</span></span>

<span data-ttu-id="5c41d-118">Padrões de número são gerenciados ```CsInboundBlockedNumberPattern``` por ```New```meio ```Get```dos ```Set```comandos, ```Remove```, e.</span><span class="sxs-lookup"><span data-stu-id="5c41d-118">Number patterns are managed through the ```CsInboundBlockedNumberPattern``` commands ```New```, ```Get```, ```Set```, and ```Remove```.</span></span> <span data-ttu-id="5c41d-119">Você pode gerenciar um determinado padrão usando esses cmdlets, incluindo a capacidade de alternar a ativação de um determinado padrão.</span><span class="sxs-lookup"><span data-stu-id="5c41d-119">You can manage a given pattern by using these cmdlets, including the ability to toggle the activation of a given pattern.</span></span>
- <span data-ttu-id="5c41d-120">[Get-CsInboundBlockedNumberPattern](https://docs.microsoft.com/powershell/module/skype/get-csinboundblockednumberpattern) retorna uma lista de todos os padrões de número bloqueados adicionados à lista de locatários, incluindo o nome, a descrição, habilitado (verdadeiro/falso) e o padrão para cada um deles.</span><span class="sxs-lookup"><span data-stu-id="5c41d-120">[Get-CsInboundBlockedNumberPattern](https://docs.microsoft.com/powershell/module/skype/get-csinboundblockednumberpattern) returns a list of all blocked number patterns added to the tenant list including Name, Description, Enabled (True/False), and Pattern for each.</span></span>
- <span data-ttu-id="5c41d-121">[New-CsInboundBlockedNumberPattern](https://docs.microsoft.com/powershell/module/skype/new-csinboundblockednumberpattern) adiciona um padrão de número bloqueado à lista de locatários.</span><span class="sxs-lookup"><span data-stu-id="5c41d-121">[New-CsInboundBlockedNumberPattern](https://docs.microsoft.com/powershell/module/skype/new-csinboundblockednumberpattern) adds a blocked number pattern to the tenant list.</span></span>
- <span data-ttu-id="5c41d-122">[Remove-CsInboundBlockedNumberPattern](https://docs.microsoft.com/powershell/module/skype/remove-csinboundblockednumberpattern) remove um padrão de número bloqueado da lista de locatários.</span><span class="sxs-lookup"><span data-stu-id="5c41d-122">[Remove-CsInboundBlockedNumberPattern](https://docs.microsoft.com/powershell/module/skype/remove-csinboundblockednumberpattern) removes a blocked number pattern from the tenant list.</span></span>
- <span data-ttu-id="5c41d-123">[Set-CsInboundBlockedNumberPattern](https://docs.microsoft.com/powershell/module/skype/set-csinboundblockednumberpattern) modifica um ou mais parâmetros de um padrão de número bloqueado na lista de locatários.</span><span class="sxs-lookup"><span data-stu-id="5c41d-123">[Set-CsInboundBlockedNumberPattern](https://docs.microsoft.com/powershell/module/skype/set-csinboundblockednumberpattern) modifies one or more parameters of a blocked number pattern in the tenant list.</span></span>

<span data-ttu-id="5c41d-124">A exibição e a ativação de todo o recurso de bloqueio de ```CsTenantBlockingCallingNumbers``` chamadas ```Get``` é ```Set```gerenciada pelos comandos e.</span><span class="sxs-lookup"><span data-stu-id="5c41d-124">Viewing and activating the entire call blocking feature is managed through the ```CsTenantBlockingCallingNumbers``` commands ```Get``` and ```Set```.</span></span>

- <span data-ttu-id="5c41d-125">[Get-CsTenantBlockedCallingNumbers](https://docs.microsoft.com/powershell/module/skype/get-cstenantblockedcallingnumbers) retorna os parâmetros da lista de números bloqueados global, incluindo Enabled (true/false).</span><span class="sxs-lookup"><span data-stu-id="5c41d-125">[Get-CsTenantBlockedCallingNumbers](https://docs.microsoft.com/powershell/module/skype/get-cstenantblockedcallingnumbers) returns the parameters for the global blocked number list including Enabled (True/False).</span></span> <span data-ttu-id="5c41d-126">Há uma única política de locatário global que não pode ser modificada manualmente a não ser ativar ou desativar o recurso.</span><span class="sxs-lookup"><span data-stu-id="5c41d-126">There's a single global tenant policy that can't be modified manually other than to turn the feature on or off.</span></span>
- <span data-ttu-id="5c41d-127">[Set-CsTenantBlockedCallingNumbers](https://docs.microsoft.com/powershell/module/skype/set-cstenantblockedcallingnumbers) permite modificar as chamadas bloqueadas de locatário global para serem ativadas e desativadas no nível do locatário.</span><span class="sxs-lookup"><span data-stu-id="5c41d-127">[Set-CsTenantBlockedCallingNumbers](https://docs.microsoft.com/powershell/module/skype/set-cstenantblockedcallingnumbers) allows modifying the global tenant blocked calls to be turned on and off at the tenant level.</span></span>

### <a name="examples"></a><span data-ttu-id="5c41d-128">Exemplos</span><span class="sxs-lookup"><span data-stu-id="5c41d-128">Examples</span></span>

#### <a name="block-a-number"></a><span data-ttu-id="5c41d-129">Bloquear um número</span><span class="sxs-lookup"><span data-stu-id="5c41d-129">Block a number</span></span>

<span data-ttu-id="5c41d-130">Neste exemplo, os ```-Enabled``` parâmetros e ```-Description``` são opcionais:</span><span class="sxs-lookup"><span data-stu-id="5c41d-130">In this example, the ```-Enabled``` and ```-Description``` parameters are optional:</span></span>

```powershell
New-CsInboundBlockedNumberPattern -Name “<name>” -Enabled $True -Description “<description>” -Pattern “^[+]?13125550000”
```

<span data-ttu-id="5c41d-131">A criação de um novo padrão adiciona o padrão como habilitado por padrão.</span><span class="sxs-lookup"><span data-stu-id="5c41d-131">Creating a new pattern adds the pattern as enabled by default.</span></span> <span data-ttu-id="5c41d-132">A descrição é um campo opcional para fornecer mais informações.</span><span class="sxs-lookup"><span data-stu-id="5c41d-132">The description is an optional field to provide more information.</span></span>

<span data-ttu-id="5c41d-133">Recomendamos que você forneça um nome significativo para compreender facilmente porque o padrão foi adicionado.</span><span class="sxs-lookup"><span data-stu-id="5c41d-133">We recommend that you provide a meaningful name to easily understand why the pattern was added.</span></span> <span data-ttu-id="5c41d-134">No caso de simplesmente bloquear números de spam, considere nomear a regra da mesma forma que o padrão de número que está sendo correspondido e adicionar informações adicionais na descrição, conforme necessário.</span><span class="sxs-lookup"><span data-stu-id="5c41d-134">In the case of simply blocking spam numbers, consider naming the rule the same as the number pattern that's being matched and add additional information in the description as required.</span></span>

<span data-ttu-id="5c41d-135">Padrões são correspondentes usando-se expressões regulares (Regex).</span><span class="sxs-lookup"><span data-stu-id="5c41d-135">Patterns are matched using Regular Expressions (Regex).</span></span> <span data-ttu-id="5c41d-136">Aguarde tempo para a replicação antes de testar e validar.</span><span class="sxs-lookup"><span data-stu-id="5c41d-136">Allow time for replication before you test and validate.</span></span>

#### <a name="allow-a-number"></a><span data-ttu-id="5c41d-137">Permitir um número</span><span class="sxs-lookup"><span data-stu-id="5c41d-137">Allow a number</span></span>

<span data-ttu-id="5c41d-138">Neste exemplo, o ```-Identity``` parâmetro é obrigatório:</span><span class="sxs-lookup"><span data-stu-id="5c41d-138">In this example, the ```-Identity``` parameter is required:</span></span>

```powershell
Remove-CsInboundBlockedNumberPattern -Identity “<identity>”
```
 
<span data-ttu-id="5c41d-139">Se a identidade não for conhecida, use ```Get-CsInboundBlockedNumberPattern``` o cmdlet para primeiro localizar o padrão apropriado e anotar a identidade.</span><span class="sxs-lookup"><span data-stu-id="5c41d-139">If the identity isn't known, use the ```Get-CsInboundBlockedNumberPattern``` cmdlet to first locate the proper pattern and note the identity.</span></span> <span data-ttu-id="5c41d-140">Em seguida, execute ```Remove-CsTenantBlockedNumberPattern``` o cmdlet e transmita o valor de identidade apropriado.</span><span class="sxs-lookup"><span data-stu-id="5c41d-140">Then, run the ```Remove-CsTenantBlockedNumberPattern``` cmdlet and pass the appropriate identity value.</span></span>

<span data-ttu-id="5c41d-141">Aguarde tempo para a replicação antes de testar e validar.</span><span class="sxs-lookup"><span data-stu-id="5c41d-141">Allow time for replication before you test and validate.</span></span>

#### <a name="view-all-number-patterns"></a><span data-ttu-id="5c41d-142">Exibir todos os padrões de número</span><span class="sxs-lookup"><span data-stu-id="5c41d-142">View all number patterns</span></span>

<span data-ttu-id="5c41d-143">Executar esse cmdlet retorna uma lista de todos os números bloqueados que são inseridos para um locatário:</span><span class="sxs-lookup"><span data-stu-id="5c41d-143">Running this cmdlet returns a list of all blocked numbers that are entered for a tenant:</span></span>

```powershell
Get-CsInboundBlockedNumberPattern
```

<span data-ttu-id="5c41d-144">Use as capacidades de filtragem internas do PowerShell para analisar os valores retornados conforme necessário.</span><span class="sxs-lookup"><span data-stu-id="5c41d-144">Use built-in PowerShell filtering abilities to parse the returned values as required.</span></span>

## <a name="add-number-exceptions"></a><span data-ttu-id="5c41d-145">Adicionar exceções de número</span><span class="sxs-lookup"><span data-stu-id="5c41d-145">Add number exceptions</span></span>

<span data-ttu-id="5c41d-146">Você pode adicionar exceções a padrões de número bloqueados ```CsTenantBlockNumberExceptionPattern``` por meio ```New```dos ```Get```comandos ```Set```,, ```Remove```, e.</span><span class="sxs-lookup"><span data-stu-id="5c41d-146">You can add exceptions to blocked number patterns through the ```CsTenantBlockNumberExceptionPattern``` commands, ```New```, ```Get```, ```Set```, and ```Remove```.</span></span>

- <span data-ttu-id="5c41d-147">[New-CsTenantBlockedNumberExceptionPattern](https://docs.microsoft.com/powershell/module/skype/new-cstenantblockednumberexceptionpattern) adiciona um padrão de exceção de número à lista de locatários.</span><span class="sxs-lookup"><span data-stu-id="5c41d-147">[New-CsTenantBlockedNumberExceptionPattern](https://docs.microsoft.com/powershell/module/skype/new-cstenantblockednumberexceptionpattern) adds a number exception pattern to the tenant list.</span></span> 
- <span data-ttu-id="5c41d-148">[Get-CsTenantBlockedNumberExceptionPattern](https://docs.microsoft.com/powershell/module/skype/get-cstenantblockednumberexceptionpattern) retorna uma lista de todos os padrões de exceção de número adicionados à lista de locatários.</span><span class="sxs-lookup"><span data-stu-id="5c41d-148">[Get-CsTenantBlockedNumberExceptionPattern](https://docs.microsoft.com/powershell/module/skype/get-cstenantblockednumberexceptionpattern) returns a list of all number exception patterns added to the tenant list.</span></span>
- <span data-ttu-id="5c41d-149">[Set-CsTenantBlockedNumberExceptionPattern](https://docs.microsoft.com/powershell/module/skype/set-cstenantblockednumberexceptionpattern) modifica um ou mais parâmetros para um padrão de exceção de número na lista de locatários.</span><span class="sxs-lookup"><span data-stu-id="5c41d-149">[Set-CsTenantBlockedNumberExceptionPattern](https://docs.microsoft.com/powershell/module/skype/set-cstenantblockednumberexceptionpattern) modifies one or more parameters to a number exception pattern in the tenant list.</span></span>
- <span data-ttu-id="5c41d-150">[Remove-CsTenantBlockedNumberExceptionPattern](https://docs.microsoft.com/powershell/module/skype/remove-cstenantblockednumberexceptionpattern) remove um padrão de exceção de número da lista de locatários.</span><span class="sxs-lookup"><span data-stu-id="5c41d-150">[Remove-CsTenantBlockedNumberExceptionPattern](https://docs.microsoft.com/powershell/module/skype/remove-cstenantblockednumberexceptionpattern) removes a number exception pattern from the tenant list.</span></span>

### <a name="examples"></a><span data-ttu-id="5c41d-151">Exemplos</span><span class="sxs-lookup"><span data-stu-id="5c41d-151">Examples</span></span>

#### <a name="add-a-number-exception"></a><span data-ttu-id="5c41d-152">Adicionar uma exceção de número</span><span class="sxs-lookup"><span data-stu-id="5c41d-152">Add a number exception</span></span>

<span data-ttu-id="5c41d-153">Neste exemplo, um novo padrão de exceção de número é criado e, por padrão, adiciona o padrão como habilitado.</span><span class="sxs-lookup"><span data-stu-id="5c41d-153">In this example, a new number exception pattern is created and will by default add the pattern as enabled.</span></span> <span data-ttu-id="5c41d-154">Os ```-Enabled``` parâmetros ```-Description``` e são opcionais.</span><span class="sxs-lookup"><span data-stu-id="5c41d-154">The ```-Enabled``` and ```-Description``` parameters are optional.</span></span>

```powershell
New-CsTenantBlockedNumberExceptionPattern -Identity <XdsGlobalRelativeIdentity> -Tenant <GUID> -Pattern <String> -Enabled <bool> -Description <string>
```

```powershell
New-CsTenantBlockedNumberExceptionPattern -Identity InternationalPrefix -Tenant daacb588-18ef-4f77-8c83-955af9615930 -Pattern "^011(\d*)$" -Description "Allow international prefix in US"  
```

#### <a name="view-all-number-exceptions"></a><span data-ttu-id="5c41d-155">Exibir todas as exceções de número</span><span class="sxs-lookup"><span data-stu-id="5c41d-155">View all number exceptions</span></span>

<span data-ttu-id="5c41d-156">Neste exemplo, o parâmetro-Identity é opcional.</span><span class="sxs-lookup"><span data-stu-id="5c41d-156">In this example, the -Identity parameter is optional.</span></span> <span data-ttu-id="5c41d-157">Se o ```-Identity``` parâmetro não for especificado, esse cmdlet retornará uma lista de todos os padrões de exceção de número inseridos para um locatário.</span><span class="sxs-lookup"><span data-stu-id="5c41d-157">If the ```-Identity``` parameter isn't specified, this cmdlet returns a list of all number exception patterns entered for a tenant.</span></span>
 
```powershell
Get-CsTenantBlockedNumberExceptionPattern -Identity <XdsGlobalRelativeIdentity> -Tenant <GUID>
```
 
```powershell
Get-CsTenantBlockedNumberExceptionPattern -Tenant daacb588-18ef-4f77-8c83-955af9615930
```

#### <a name="modify-a-number-exception"></a><span data-ttu-id="5c41d-158">Modificar uma exceção de número</span><span class="sxs-lookup"><span data-stu-id="5c41d-158">Modify a number exception</span></span>

<span data-ttu-id="5c41d-159">Neste exemplo, o parâmetro-Identity é obrigatório.</span><span class="sxs-lookup"><span data-stu-id="5c41d-159">In this example, the -Identity parameter is mandatory.</span></span> <span data-ttu-id="5c41d-160">O ```Set-CsTenantBlockedNumberExceptionPattern``` cmdlet permite modificar um ou mais parâmetros para uma determinada identidade de padrão de número.</span><span class="sxs-lookup"><span data-stu-id="5c41d-160">The ```Set-CsTenantBlockedNumberExceptionPattern``` cmdlet lets you modify one or more parameters for a given number pattern identity.</span></span>
 
```powershell
Set-CsTenantBlockedNumberExceptionPattern -Identity <XdsGlobalRelativeIdentity> -Tenant <GUID> -Enabled <bool> -Description <string> -Pattern <string> 
```

```powershell
Set-CsTenantBlockedNumberExceptionPattern -Identity InternationalPrefix -Tenant daacb588-18ef-4f77-8c83-955af9615930  -Pattern "^022(\d*)$" 
```

#### <a name="remove-a-number-exception"></a><span data-ttu-id="5c41d-161">Remover uma exceção de número</span><span class="sxs-lookup"><span data-stu-id="5c41d-161">Remove a number exception</span></span>

<span data-ttu-id="5c41d-162">Neste exemplo, o ```-Identity``` parâmetro é obrigatório.</span><span class="sxs-lookup"><span data-stu-id="5c41d-162">In this example, the ```-Identity``` parameter is required.</span></span> <span data-ttu-id="5c41d-163">Esse cmdlet removerá o padrão de número especificado da lista de locatários.</span><span class="sxs-lookup"><span data-stu-id="5c41d-163">This cmdlet will remove the given number pattern from the tenant list.</span></span>  <span data-ttu-id="5c41d-164">Se a identidade não for conhecida, use ```Get-CsInboundBlockedNumberPattern``` o cmdlet para primeiro localizar o padrão apropriado e anotar a identidade.</span><span class="sxs-lookup"><span data-stu-id="5c41d-164">If the identity isn't known, use the ```Get-CsInboundBlockedNumberPattern``` cmdlet to first locate the proper pattern and note the identity.</span></span> <span data-ttu-id="5c41d-165">Em seguida, execute ```Remove-CsTenantBlockedNumberExceptionPattern``` o cmdlet e transmita o valor de identidade apropriado.</span><span class="sxs-lookup"><span data-stu-id="5c41d-165">Then, run the ```Remove-CsTenantBlockedNumberExceptionPattern``` cmdlet and pass the appropriate identity value.</span></span><span data-ttu-id="5c41d-166">Aguarde tempo para a replicação antes de testar e validar.</span><span class="sxs-lookup"><span data-stu-id="5c41d-166"> Allow time for replication before you test and validate.</span></span>  

```powershell
Remove-CsTenantBlockedNumberExceptionPattern -Identity <XdsGlobalRelativeIdentity> -Tenant <GUID>
```

```powershell
Remove-CsTenantBlockedNumberExceptionPattern -Identity InternationalPrefix -Tenant daacb588-18ef-4f77-8c83-955af9615930
```

### <a name="test-whether-a-number-is-blocked"></a><span data-ttu-id="5c41d-167">Testar se um número está bloqueado</span><span class="sxs-lookup"><span data-stu-id="5c41d-167">Test whether a number is blocked</span></span>

<span data-ttu-id="5c41d-168">Use o ```Test-CsInboundBlockedNumberPattern``` cmdlet para verificar se um número está bloqueado no locatário.</span><span class="sxs-lookup"><span data-stu-id="5c41d-168">Use the ```Test-CsInboundBlockedNumberPattern``` cmdlet to verify whether a number is blocked in the tenant.</span></span>
 
<span data-ttu-id="5c41d-169">Neste exemplo, os ```-Phonenumber``` parâmetros e ```-Tenant``` são obrigatórios.</span><span class="sxs-lookup"><span data-stu-id="5c41d-169">In this example, the ```-Phonenumber``` and ```-Tenant``` parameters are required.</span></span> <span data-ttu-id="5c41d-170">O ```-PhoneNumber``` parâmetro deve ser uma cadeia de caracteres numérica sem caracteres adicionais, como + ou-.</span><span class="sxs-lookup"><span data-stu-id="5c41d-170">The ```-PhoneNumber``` parameter should be a numeric string without any additional characters such as + or -.</span></span> <span data-ttu-id="5c41d-171">No TRPS, o ```-Tenant parameter``` é opcional.</span><span class="sxs-lookup"><span data-stu-id="5c41d-171">In TRPS, the ```-Tenant parameter``` is optional.</span></span> <span data-ttu-id="5c41d-172">O parâmetro ```isNumberBlocked``` resultante retornará um valor de true se o número estiver bloqueado no locatário e falso se não estiver bloqueado.</span><span class="sxs-lookup"><span data-stu-id="5c41d-172">The resulting ```isNumberBlocked``` parameter returns a value of True if the number is blocked in the tenant and False if it's not blocked.</span></span>

```powershell
Test-CsInboundBlockedNumberPattern –Tenant <GUID> -PhoneNumber <String>
```

```powershell
Test-CsInboundBlockedNumberPattern -Tenant e09ad6bc-1d3c-4650-8cae-02f6c5a04b45 -PhoneNumber 4255550101
```

|<span data-ttu-id="5c41d-173">httpResponseCode</span><span class="sxs-lookup"><span data-stu-id="5c41d-173">httpResponseCode</span></span>  |<span data-ttu-id="5c41d-174">isNumberBlocked</span><span class="sxs-lookup"><span data-stu-id="5c41d-174">isNumberBlocked</span></span>   |<span data-ttu-id="5c41d-175">errorMessage</span><span class="sxs-lookup"><span data-stu-id="5c41d-175">errorMessage</span></span> |
|---------|---------|---------|
|<span data-ttu-id="5c41d-176">200</span><span class="sxs-lookup"><span data-stu-id="5c41d-176">200</span></span>    | <span data-ttu-id="5c41d-177">Verdadeiro</span><span class="sxs-lookup"><span data-stu-id="5c41d-177">True</span></span>        |         |

```powershell
Test-CsInboundBlockedNumberPattern -Tenant e09ad6bc-1d3c-4650-8cae-02f6c5a04b45 -PhoneNumber 6045550188
```

|<span data-ttu-id="5c41d-178">httpResponseCode</span><span class="sxs-lookup"><span data-stu-id="5c41d-178">httpResponseCode</span></span>  |<span data-ttu-id="5c41d-179">isNumberBlocked</span><span class="sxs-lookup"><span data-stu-id="5c41d-179">isNumberBlocked</span></span>   |<span data-ttu-id="5c41d-180">errorMessage</span><span class="sxs-lookup"><span data-stu-id="5c41d-180">errorMessage</span></span> |
|---------|---------|---------|
|<span data-ttu-id="5c41d-181">200</span><span class="sxs-lookup"><span data-stu-id="5c41d-181">200</span></span>    | <span data-ttu-id="5c41d-182">Falso</span><span class="sxs-lookup"><span data-stu-id="5c41d-182">False</span></span>        |         |

## <a name="a-note-about-regex"></a><span data-ttu-id="5c41d-183">Uma observação sobre Regex</span><span class="sxs-lookup"><span data-stu-id="5c41d-183">A note about Regex</span></span>

<span data-ttu-id="5c41d-184">Conforme declarado anteriormente, a correspondência de padrão para bloquear chamadores é feita usando Regex.</span><span class="sxs-lookup"><span data-stu-id="5c41d-184">As stated earlier, the pattern matching for blocking callers is done by using Regex.</span></span> <span data-ttu-id="5c41d-185">Há várias ferramentas disponíveis online para ajudar a validar uma correspondência de padrão de Regex.</span><span class="sxs-lookup"><span data-stu-id="5c41d-185">Multiple tools are available online to help validate a Regex pattern match.</span></span> <span data-ttu-id="5c41d-186">Se você não estiver familiarizado com padrões de Regex, recomendamos que leve algum tempo para se familiarizar com as noções básicas.</span><span class="sxs-lookup"><span data-stu-id="5c41d-186">If you aren't familiar with Regex patterns, we recommend that you take some time to familiarize yourself with the basics.</span></span> <span data-ttu-id="5c41d-187">Para garantir que você tenha resultados esperados, use uma ferramenta para validar as correspondências de padrão antes de adicionar um novo número bloqueado correspondente ao seu locatário.</span><span class="sxs-lookup"><span data-stu-id="5c41d-187">To make sure you get expected results, use a tool for validating pattern matches before you add new blocked number matches to your tenant.</span></span> 

## <a name="related-topics"></a><span data-ttu-id="5c41d-188">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="5c41d-188">Related topics</span></span>

- [<span data-ttu-id="5c41d-189">Configurar seu computador para gerenciar o Skype for Business online usando o Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="5c41d-189">Set up your computer to manage Skype for Business Online by using Windows PowerShell</span></span>](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
