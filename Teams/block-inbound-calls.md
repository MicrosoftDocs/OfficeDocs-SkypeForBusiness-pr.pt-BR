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
# <a name="block-inbound-calls"></a><span data-ttu-id="fb40d-102">Bloquear chamadas de entrada</span><span class="sxs-lookup"><span data-stu-id="fb40d-102">Block inbound calls</span></span>

<span data-ttu-id="fb40d-103">Os Planos de Chamadas e Roteamento Direto do Sistema telefônico suportam o bloqueio de chamadas de entrada da PSTN (Rede Telefônica Pública Comutado).</span><span class="sxs-lookup"><span data-stu-id="fb40d-103">Phone System Direct Routing and Calling Plans support blocking inbound calls from the Public Switched Telephone Network (PSTN).</span></span> <span data-ttu-id="fb40d-104">Esse recurso permite que uma lista global de padrões de número do locatário seja definida para que a ID de chamadas de cada chamada PSTN recebida para o locatário possa ser verificada na lista para uma combinação.</span><span class="sxs-lookup"><span data-stu-id="fb40d-104">This feature allows a tenant global list of number patterns to be defined so that the caller ID of every incoming PSTN call to the tenant can be checked against the list for a match.</span></span> <span data-ttu-id="fb40d-105">Se uma combinação for feita, uma chamada de entrada será rejeitada.</span><span class="sxs-lookup"><span data-stu-id="fb40d-105">If a match is made, an incoming call is rejected.</span></span>

<span data-ttu-id="fb40d-106">Esse recurso de bloqueio de chamada de entrada só funciona em chamadas de entrada que se originam do PSTN e só funcionam no nível global do locatário.</span><span class="sxs-lookup"><span data-stu-id="fb40d-106">This inbound call blocking feature only works on inbound calls that originate from the PSTN and only works on a tenant-global basis.</span></span> <span data-ttu-id="fb40d-107">Ele não está disponível por usuário.</span><span class="sxs-lookup"><span data-stu-id="fb40d-107">It's not available on a per-user basis.</span></span>  

>[!NOTE]
> <span data-ttu-id="fb40d-108">Os chamadores bloqueados podem ter comportamentos ligeiramente diferentes quando foram bloqueados.</span><span class="sxs-lookup"><span data-stu-id="fb40d-108">Blocked callers may experience slightly different behaviors when they've been blocked.</span></span> <span data-ttu-id="fb40d-109">O comportamento se baseia em como a operadora do chamador bloqueado lida com a notificação de que a chamada não tem permissão para ser concluída com êxito.</span><span class="sxs-lookup"><span data-stu-id="fb40d-109">The behavior is based on how the blocked caller’s carrier handles the notification that the call isn't allowed to be successfully completed.</span></span> <span data-ttu-id="fb40d-110">Exemplos podem incluir uma mensagem de operadora informando que a chamada não pode ser concluída como discada ou simplesmente soltando a chamada.</span><span class="sxs-lookup"><span data-stu-id="fb40d-110">Examples may include a carrier message stating the call can't be completed as dialed, or simply dropping the call.</span></span>

## <a name="call-blocking-admin-controls-and-information"></a><span data-ttu-id="fb40d-111">Informações e controles de administração de bloqueio de chamada</span><span class="sxs-lookup"><span data-stu-id="fb40d-111">Call blocking admin controls and information</span></span>

<span data-ttu-id="fb40d-112">Os controles de administração para bloquear números são fornecidos apenas usando o PowerShell.</span><span class="sxs-lookup"><span data-stu-id="fb40d-112">Admin controls for blocking numbers are provided using PowerShell only.</span></span> <span data-ttu-id="fb40d-113">Os padrões de blocos de números são definidos como padrões de expressão regulares.</span><span class="sxs-lookup"><span data-stu-id="fb40d-113">Number block patterns are defined as regular expression patterns.</span></span> <span data-ttu-id="fb40d-114">A ordem das expressões não é importante: o primeiro padrão que é corresponder à lista faz com que a chamada seja bloqueada.</span><span class="sxs-lookup"><span data-stu-id="fb40d-114">The order of the expressions is unimportant – the first pattern matched in the list results in the call being blocked.</span></span> <span data-ttu-id="fb40d-115">Um novo número ou padrão adicionado ou removido na lista de chamadores bloqueados pode levar até 24 horas para que o padrão se torne ativo.</span><span class="sxs-lookup"><span data-stu-id="fb40d-115">A new number or pattern that's added or removed in the blocked callers list may take up to 24 hours for the pattern to become active.</span></span>

## <a name="call-blocking-powershell-commands"></a><span data-ttu-id="fb40d-116">Comandos de bloqueio de chamada do PowerShell</span><span class="sxs-lookup"><span data-stu-id="fb40d-116">Call blocking PowerShell commands</span></span>

<span data-ttu-id="fb40d-117">Você gerencia padrões de números usando os cmdlets **Novo,** **Obter,** **Definir,** **Remover**  - **CsInboundBlockedNumberPattern.**</span><span class="sxs-lookup"><span data-stu-id="fb40d-117">You manage number patterns by using the **New**, **Get**, **Set**, **Remove** -**CsInboundBlockedNumberPattern** cmdlets.</span></span> <span data-ttu-id="fb40d-118">Você pode gerenciar um determinado padrão usando esses cmdlets, incluindo a capacidade de alternar a ativação de um determinado padrão.</span><span class="sxs-lookup"><span data-stu-id="fb40d-118">You can manage a given pattern by using these cmdlets, including the ability to toggle the activation of a given pattern.</span></span>

- <span data-ttu-id="fb40d-119">[Get-CsInboundBlockedNumberPattern](https://docs.microsoft.com/powershell/module/skype/get-csinboundblockednumberpattern) retorna uma lista de todos os padrões de números bloqueados adicionados à lista de locatários, incluindo Nome, Descrição, Habilitado (Verdadeiro/Falso) e Padrão para cada um.</span><span class="sxs-lookup"><span data-stu-id="fb40d-119">[Get-CsInboundBlockedNumberPattern](https://docs.microsoft.com/powershell/module/skype/get-csinboundblockednumberpattern) returns a list of all blocked number patterns added to the tenant list including Name, Description, Enabled (True/False), and Pattern for each.</span></span>
- <span data-ttu-id="fb40d-120">[New-CsInboundBlockedNumberPattern adiciona](https://docs.microsoft.com/powershell/module/skype/new-csinboundblockednumberpattern) um padrão de número bloqueado à lista de locatários.</span><span class="sxs-lookup"><span data-stu-id="fb40d-120">[New-CsInboundBlockedNumberPattern](https://docs.microsoft.com/powershell/module/skype/new-csinboundblockednumberpattern) adds a blocked number pattern to the tenant list.</span></span>
- <span data-ttu-id="fb40d-121">[Remove-CsInboundBlockedNumberPattern](https://docs.microsoft.com/powershell/module/skype/remove-csinboundblockednumberpattern) remove um padrão de número bloqueado da lista de locatários.</span><span class="sxs-lookup"><span data-stu-id="fb40d-121">[Remove-CsInboundBlockedNumberPattern](https://docs.microsoft.com/powershell/module/skype/remove-csinboundblockednumberpattern) removes a blocked number pattern from the tenant list.</span></span>
- <span data-ttu-id="fb40d-122">[Set-CsInboundBlockedNumberPattern](https://docs.microsoft.com/powershell/module/skype/set-csinboundblockednumberpattern) modifica um ou mais parâmetros de um padrão de número bloqueado na lista de locatários.</span><span class="sxs-lookup"><span data-stu-id="fb40d-122">[Set-CsInboundBlockedNumberPattern](https://docs.microsoft.com/powershell/module/skype/set-csinboundblockednumberpattern) modifies one or more parameters of a blocked number pattern in the tenant list.</span></span>

<span data-ttu-id="fb40d-123">A exibição e a ativação de todo o recurso de bloqueio de chamada é gerenciada por meio dos cmdlets **Get**, **Set**  - **CsTenantBlockingCallingNumbers.**</span><span class="sxs-lookup"><span data-stu-id="fb40d-123">Viewing and activating the entire call blocking feature is managed through the **Get**, **Set** -**CsTenantBlockingCallingNumbers** cmdlets.</span></span>

- <span data-ttu-id="fb40d-124">[Get-CsTenantBlockedCallingNumbers](https://docs.microsoft.com/powershell/module/skype/get-cstenantblockedcallingnumbers) retorna os parâmetros da lista de números bloqueados global, incluindo Habilitado (Verdadeiro/Falso).</span><span class="sxs-lookup"><span data-stu-id="fb40d-124">[Get-CsTenantBlockedCallingNumbers](https://docs.microsoft.com/powershell/module/skype/get-cstenantblockedcallingnumbers) returns the parameters for the global blocked number list including Enabled (True/False).</span></span> <span data-ttu-id="fb40d-125">Há uma única política global de locatário que não pode ser modificada manualmente além de ativar ou desativar o recurso.</span><span class="sxs-lookup"><span data-stu-id="fb40d-125">There's a single global tenant policy that can't be modified manually other than to turn the feature on or off.</span></span>
- <span data-ttu-id="fb40d-126">[O Set-CsTenantBlockedCallingNumbers](https://docs.microsoft.com/powershell/module/skype/set-cstenantblockedcallingnumbers) permite que a modificação das chamadas global bloqueadas pelo locatário sejam 2010 e 2010 no nível do locatário.</span><span class="sxs-lookup"><span data-stu-id="fb40d-126">[Set-CsTenantBlockedCallingNumbers](https://docs.microsoft.com/powershell/module/skype/set-cstenantblockedcallingnumbers) allows modifying the global tenant blocked calls to be turned on and off at the tenant level.</span></span>

### <a name="examples"></a><span data-ttu-id="fb40d-127">Exemplos</span><span class="sxs-lookup"><span data-stu-id="fb40d-127">Examples</span></span>

#### <a name="block-a-number"></a><span data-ttu-id="fb40d-128">Bloquear um número</span><span class="sxs-lookup"><span data-stu-id="fb40d-128">Block a number</span></span>

<span data-ttu-id="fb40d-129">Neste exemplo, os parâmetros **Habilitado** e **Descrição** são opcionais.</span><span class="sxs-lookup"><span data-stu-id="fb40d-129">In this example, the **Enabled** and **Description** parameters are optional.</span></span>

```powershell
New-CsInboundBlockedNumberPattern -Name “<name>” -Enabled $True -Description “<description>” -Pattern “^[+]?13125550000”
```

<span data-ttu-id="fb40d-130">A criação de um novo padrão adiciona o padrão conforme habilitado por padrão.</span><span class="sxs-lookup"><span data-stu-id="fb40d-130">Creating a new pattern adds the pattern as enabled by default.</span></span> <span data-ttu-id="fb40d-131">A descrição é um campo opcional para fornecer mais informações.</span><span class="sxs-lookup"><span data-stu-id="fb40d-131">The description is an optional field to provide more information.</span></span>

<span data-ttu-id="fb40d-132">Recomendamos que você forneça um nome significativo para entender facilmente por que o padrão foi adicionado.</span><span class="sxs-lookup"><span data-stu-id="fb40d-132">We recommend that you provide a meaningful name to easily understand why the pattern was added.</span></span> <span data-ttu-id="fb40d-133">No caso de simplesmente bloquear números de spam, considere nomear a regra da mesma forma que o padrão de número que está sendo corresponder e adicionar informações adicionais na descrição conforme necessário.</span><span class="sxs-lookup"><span data-stu-id="fb40d-133">In the case of simply blocking spam numbers, consider naming the rule the same as the number pattern that's being matched and add additional information in the description as required.</span></span>

<span data-ttu-id="fb40d-134">Os padrões são corresponderem usando Expressões Regulares (Regex).</span><span class="sxs-lookup"><span data-stu-id="fb40d-134">Patterns are matched using Regular Expressions (Regex).</span></span> <span data-ttu-id="fb40d-135">Permitir tempo para replicação antes de testar e validar.</span><span class="sxs-lookup"><span data-stu-id="fb40d-135">Allow time for replication before you test and validate.</span></span>

#### <a name="allow-a-number"></a><span data-ttu-id="fb40d-136">Permitir um número</span><span class="sxs-lookup"><span data-stu-id="fb40d-136">Allow a number</span></span>

<span data-ttu-id="fb40d-137">Neste exemplo, o parâmetro **Identidade** é obrigatório.</span><span class="sxs-lookup"><span data-stu-id="fb40d-137">In this example, the **Identity** parameter is required.</span></span>

```powershell
Remove-CsInboundBlockedNumberPattern -Identity “<identity>”
```
 
<span data-ttu-id="fb40d-138">Se a identidade não for conhecida, use o cmdlet **Get-CsInboundBlockedNumberPattern** para localizar primeiro o padrão adequado e observar a identidade.</span><span class="sxs-lookup"><span data-stu-id="fb40d-138">If the identity isn't known, use the **Get-CsInboundBlockedNumberPattern** cmdlet to first locate the proper pattern and note the identity.</span></span> <span data-ttu-id="fb40d-139">Em seguida, execute **o cmdlet Remove-CsTenantBlockedNumberPattern** e passe o valor de identidade apropriado.</span><span class="sxs-lookup"><span data-stu-id="fb40d-139">Then, run the **Remove-CsTenantBlockedNumberPattern** cmdlet and pass the appropriate identity value.</span></span>

<span data-ttu-id="fb40d-140">Permitir tempo para replicação antes de testar e validar.</span><span class="sxs-lookup"><span data-stu-id="fb40d-140">Allow time for replication before you test and validate.</span></span>

#### <a name="view-all-number-patterns"></a><span data-ttu-id="fb40d-141">Exibir todos os padrões de número</span><span class="sxs-lookup"><span data-stu-id="fb40d-141">View all number patterns</span></span>

<span data-ttu-id="fb40d-142">Executar este cmdlet retorna uma lista de todos os números bloqueados inseridos para um locatário:</span><span class="sxs-lookup"><span data-stu-id="fb40d-142">Running this cmdlet returns a list of all blocked numbers that are entered for a tenant:</span></span>

```powershell
Get-CsInboundBlockedNumberPattern
```

<span data-ttu-id="fb40d-143">Use as habilidades de filtragem do PowerShell para analisar os valores retornados conforme necessário.</span><span class="sxs-lookup"><span data-stu-id="fb40d-143">Use built-in PowerShell filtering abilities to parse the returned values as required.</span></span>

## <a name="add-number-exceptions"></a><span data-ttu-id="fb40d-144">Adicionar exceções de número</span><span class="sxs-lookup"><span data-stu-id="fb40d-144">Add number exceptions</span></span>

<span data-ttu-id="fb40d-145">Você pode adicionar exceções a padrões de números bloqueados usando os cmdlets **Novo,** **Obter,** **Definir,** Remover  - **CsTenantBlockNumberExceptionPattern.**</span><span class="sxs-lookup"><span data-stu-id="fb40d-145">You can add exceptions to blocked number patterns by using the **New**, **Get**, **Set**, **Remove** -**CsTenantBlockNumberExceptionPattern** cmdlets.</span></span>

- <span data-ttu-id="fb40d-146">[New-CsTenantBlockedNumberExceptionPattern adiciona](https://docs.microsoft.com/powershell/module/skype/new-cstenantblockednumberexceptionpattern) um padrão de exceção de número à lista de locatários.</span><span class="sxs-lookup"><span data-stu-id="fb40d-146">[New-CsTenantBlockedNumberExceptionPattern](https://docs.microsoft.com/powershell/module/skype/new-cstenantblockednumberexceptionpattern) adds a number exception pattern to the tenant list.</span></span> 
- <span data-ttu-id="fb40d-147">[Get-CsTenantBlockedNumberExceptionPattern](https://docs.microsoft.com/powershell/module/skype/get-cstenantblockednumberexceptionpattern) retorna uma lista de todos os padrões de exceção de número adicionados à lista de locatários.</span><span class="sxs-lookup"><span data-stu-id="fb40d-147">[Get-CsTenantBlockedNumberExceptionPattern](https://docs.microsoft.com/powershell/module/skype/get-cstenantblockednumberexceptionpattern) returns a list of all number exception patterns added to the tenant list.</span></span>
- <span data-ttu-id="fb40d-148">[Set-CsTenantBlockedNumberExceptionPattern](https://docs.microsoft.com/powershell/module/skype/set-cstenantblockednumberexceptionpattern) modifica um ou mais parâmetros para um padrão de exceção de número na lista de locatários.</span><span class="sxs-lookup"><span data-stu-id="fb40d-148">[Set-CsTenantBlockedNumberExceptionPattern](https://docs.microsoft.com/powershell/module/skype/set-cstenantblockednumberexceptionpattern) modifies one or more parameters to a number exception pattern in the tenant list.</span></span>
- <span data-ttu-id="fb40d-149">[Remove-CsTenantBlockedNumberExceptionPattern](https://docs.microsoft.com/powershell/module/skype/remove-cstenantblockednumberexceptionpattern) remove um padrão de exceção de número da lista de locatários.</span><span class="sxs-lookup"><span data-stu-id="fb40d-149">[Remove-CsTenantBlockedNumberExceptionPattern](https://docs.microsoft.com/powershell/module/skype/remove-cstenantblockednumberexceptionpattern) removes a number exception pattern from the tenant list.</span></span>

### <a name="examples"></a><span data-ttu-id="fb40d-150">Exemplos</span><span class="sxs-lookup"><span data-stu-id="fb40d-150">Examples</span></span>

#### <a name="add-a-number-exception"></a><span data-ttu-id="fb40d-151">Adicionar uma exceção de número</span><span class="sxs-lookup"><span data-stu-id="fb40d-151">Add a number exception</span></span>

<span data-ttu-id="fb40d-152">Neste exemplo, um novo padrão de exceção de número é criado e adicionará por padrão o padrão conforme habilitado.</span><span class="sxs-lookup"><span data-stu-id="fb40d-152">In this example, a new number exception pattern is created and will by default add the pattern as enabled.</span></span> <span data-ttu-id="fb40d-153">Os **parâmetros Habilitado** e **Descrição** são opcionais.</span><span class="sxs-lookup"><span data-stu-id="fb40d-153">The **Enabled** and **Description** parameters are optional.</span></span>

```powershell
New-CsTenantBlockedNumberExceptionPattern -Identity <XdsGlobalRelativeIdentity> -Tenant <GUID> -Pattern <String> -Enabled <bool> -Description <string>
```

```powershell
New-CsTenantBlockedNumberExceptionPattern -Identity InternationalPrefix -Tenant daacb588-18ef-4f77-8c83-955af9615930 -Pattern "^011(\d*)$" -Description "Allow international prefix in US"  
```

#### <a name="view-all-number-exceptions"></a><span data-ttu-id="fb40d-154">Exibir todas as exceções de número</span><span class="sxs-lookup"><span data-stu-id="fb40d-154">View all number exceptions</span></span>

<span data-ttu-id="fb40d-155">Neste exemplo, o parâmetro **Identidade** é opcional.</span><span class="sxs-lookup"><span data-stu-id="fb40d-155">In this example, the **Identity** parameter is optional.</span></span> <span data-ttu-id="fb40d-156">Se o **parâmetro** Identidade não for especificado, esse cmdlet retornará uma lista de todos os padrões de exceção de número inseridos para um locatário.</span><span class="sxs-lookup"><span data-stu-id="fb40d-156">If the **Identity** parameter isn't specified, this cmdlet returns a list of all number exception patterns entered for a tenant.</span></span>
 
```powershell
Get-CsTenantBlockedNumberExceptionPattern -Identity <XdsGlobalRelativeIdentity> -Tenant <GUID>
```
 
```powershell
Get-CsTenantBlockedNumberExceptionPattern -Tenant daacb588-18ef-4f77-8c83-955af9615930
```

#### <a name="modify-a-number-exception"></a><span data-ttu-id="fb40d-157">Modificar uma exceção de número</span><span class="sxs-lookup"><span data-stu-id="fb40d-157">Modify a number exception</span></span>

<span data-ttu-id="fb40d-158">Neste exemplo, o parâmetro **Identidade** é obrigatório.</span><span class="sxs-lookup"><span data-stu-id="fb40d-158">In this example, the **Identity** parameter is mandatory.</span></span> <span data-ttu-id="fb40d-159">O cmdlet **Set-CsTenantBlockedNumberExceptionPattern** permite modificar um ou mais parâmetros para uma determinada identidade de padrão de número.</span><span class="sxs-lookup"><span data-stu-id="fb40d-159">The **Set-CsTenantBlockedNumberExceptionPattern** cmdlet lets you modify one or more parameters for a given number pattern identity.</span></span>
 
```powershell
Set-CsTenantBlockedNumberExceptionPattern -Identity <XdsGlobalRelativeIdentity> -Tenant <GUID> -Enabled <bool> -Description <string> -Pattern <string> 
```

```powershell
Set-CsTenantBlockedNumberExceptionPattern -Identity InternationalPrefix -Tenant daacb588-18ef-4f77-8c83-955af9615930  -Pattern "^022(\d*)$" 
```

#### <a name="remove-a-number-exception"></a><span data-ttu-id="fb40d-160">Remover uma exceção de número</span><span class="sxs-lookup"><span data-stu-id="fb40d-160">Remove a number exception</span></span>

<span data-ttu-id="fb40d-161">Neste exemplo, o parâmetro **Identidade** é obrigatório.</span><span class="sxs-lookup"><span data-stu-id="fb40d-161">In this example, the **Identity** parameter is required.</span></span> <span data-ttu-id="fb40d-162">Esse cmdlet removerá o padrão de número determinado da lista de locatários.</span><span class="sxs-lookup"><span data-stu-id="fb40d-162">This cmdlet will remove the given number pattern from the tenant list.</span></span>  <span data-ttu-id="fb40d-163">Se a identidade não for conhecida, use o cmdlet **Get-CsInboundBlockedNumberPattern** para localizar primeiro o padrão adequado e observar a identidade.</span><span class="sxs-lookup"><span data-stu-id="fb40d-163">If the identity isn't known, use the **Get-CsInboundBlockedNumberPattern** cmdlet to first locate the proper pattern and note the identity.</span></span> <span data-ttu-id="fb40d-164">Em seguida, execute **o cmdlet Remove-CsTenantBlockedNumberExceptionPattern** e passe o valor de identidade apropriado.</span><span class="sxs-lookup"><span data-stu-id="fb40d-164">Then, run the **Remove-CsTenantBlockedNumberExceptionPattern** cmdlet and pass the appropriate identity value.</span></span><span data-ttu-id="fb40d-165">Permitir tempo para replicação antes de testar e validar.</span><span class="sxs-lookup"><span data-stu-id="fb40d-165"> Allow time for replication before you test and validate.</span></span>  

```powershell
Remove-CsTenantBlockedNumberExceptionPattern -Identity <XdsGlobalRelativeIdentity> -Tenant <GUID>
```

```powershell
Remove-CsTenantBlockedNumberExceptionPattern -Identity InternationalPrefix -Tenant daacb588-18ef-4f77-8c83-955af9615930
```

### <a name="test-whether-a-number-is-blocked"></a><span data-ttu-id="fb40d-166">Testar se um número está bloqueado</span><span class="sxs-lookup"><span data-stu-id="fb40d-166">Test whether a number is blocked</span></span>

<span data-ttu-id="fb40d-167">Use o cmdlet **Test-CsInboundBlockedNumberPattern** para verificar se um número está bloqueado no locatário.</span><span class="sxs-lookup"><span data-stu-id="fb40d-167">Use the **Test-CsInboundBlockedNumberPattern** cmdlet to verify whether a number is blocked in the tenant.</span></span>
 
<span data-ttu-id="fb40d-168">Neste exemplo, os parâmetros **PhoneNumber** e **Tenant** são necessários.</span><span class="sxs-lookup"><span data-stu-id="fb40d-168">In this example, the **PhoneNumber** and **Tenant** parameters are required.</span></span> <span data-ttu-id="fb40d-169">O **parâmetro PhoneNumber** deve ser uma cadeia numérica sem caracteres adicionais, como + ou -.</span><span class="sxs-lookup"><span data-stu-id="fb40d-169">The **PhoneNumber** parameter should be a numeric string without any additional characters such as + or -.</span></span> <span data-ttu-id="fb40d-170">Em TRPS, o parâmetro **Tenant** é opcional.</span><span class="sxs-lookup"><span data-stu-id="fb40d-170">In TRPS, the **Tenant parameter** is optional.</span></span> <span data-ttu-id="fb40d-171">O parâmetro **resultante éNumberBlocked** retorna um valor de True se o número for bloqueado no locatário e Falso se ele não estiver bloqueado.</span><span class="sxs-lookup"><span data-stu-id="fb40d-171">The resulting **isNumberBlocked** parameter returns a value of True if the number is blocked in the tenant and False if it's not blocked.</span></span>

```powershell
Test-CsInboundBlockedNumberPattern –Tenant <GUID> -PhoneNumber <String>
```

```powershell
Test-CsInboundBlockedNumberPattern -Tenant e09ad6bc-1d3c-4650-8cae-02f6c5a04b45 -PhoneNumber 4255550101
```

|<span data-ttu-id="fb40d-172">httpResponseCode</span><span class="sxs-lookup"><span data-stu-id="fb40d-172">httpResponseCode</span></span>  |<span data-ttu-id="fb40d-173">isNumberBlocked</span><span class="sxs-lookup"><span data-stu-id="fb40d-173">isNumberBlocked</span></span>   |<span data-ttu-id="fb40d-174">Errormessage</span><span class="sxs-lookup"><span data-stu-id="fb40d-174">errorMessage</span></span> |
|---------|---------|---------|
|<span data-ttu-id="fb40d-175">200</span><span class="sxs-lookup"><span data-stu-id="fb40d-175">200</span></span>    | <span data-ttu-id="fb40d-176">Verdadeiro</span><span class="sxs-lookup"><span data-stu-id="fb40d-176">True</span></span>        |         |

```powershell
Test-CsInboundBlockedNumberPattern -Tenant e09ad6bc-1d3c-4650-8cae-02f6c5a04b45 -PhoneNumber 6045550188
```

|<span data-ttu-id="fb40d-177">httpResponseCode</span><span class="sxs-lookup"><span data-stu-id="fb40d-177">httpResponseCode</span></span>  |<span data-ttu-id="fb40d-178">isNumberBlocked</span><span class="sxs-lookup"><span data-stu-id="fb40d-178">isNumberBlocked</span></span>   |<span data-ttu-id="fb40d-179">Errormessage</span><span class="sxs-lookup"><span data-stu-id="fb40d-179">errorMessage</span></span> |
|---------|---------|---------|
|<span data-ttu-id="fb40d-180">200</span><span class="sxs-lookup"><span data-stu-id="fb40d-180">200</span></span>    | <span data-ttu-id="fb40d-181">Falso</span><span class="sxs-lookup"><span data-stu-id="fb40d-181">False</span></span>        |         |

## <a name="a-note-about-regex"></a><span data-ttu-id="fb40d-182">Uma anotação sobre Regex</span><span class="sxs-lookup"><span data-stu-id="fb40d-182">A note about Regex</span></span>

<span data-ttu-id="fb40d-183">Conforme declarado anteriormente, a correspondência de padrões para bloquear chamadores é feita usando Regex.</span><span class="sxs-lookup"><span data-stu-id="fb40d-183">As stated earlier, the pattern matching for blocking callers is done by using Regex.</span></span> <span data-ttu-id="fb40d-184">Várias ferramentas estão disponíveis online para ajudar a validar uma combinação de padrões Regex.</span><span class="sxs-lookup"><span data-stu-id="fb40d-184">Multiple tools are available online to help validate a Regex pattern match.</span></span> <span data-ttu-id="fb40d-185">Se você não estiver familiarizado com padrões Regex, recomendamos que você tire um tempo para se familiarizar com as noções básicas.</span><span class="sxs-lookup"><span data-stu-id="fb40d-185">If you aren't familiar with Regex patterns, we recommend that you take some time to familiarize yourself with the basics.</span></span> <span data-ttu-id="fb40d-186">Para garantir que você receba os resultados esperados, use uma ferramenta para validar as combinações de padrão antes de adicionar novas combinações de números bloqueados ao seu locatário.</span><span class="sxs-lookup"><span data-stu-id="fb40d-186">To make sure you get expected results, use a tool for validating pattern matches before you add new blocked number matches to your tenant.</span></span>
