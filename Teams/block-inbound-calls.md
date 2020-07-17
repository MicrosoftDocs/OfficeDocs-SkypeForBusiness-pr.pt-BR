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
# <a name="block-inbound-calls"></a><span data-ttu-id="acc23-102">Bloquear chamadas recebidas</span><span class="sxs-lookup"><span data-stu-id="acc23-102">Block inbound calls</span></span>

<span data-ttu-id="acc23-103">Os planos de roteamento e chamada do sistema telefônico dão suporte ao bloqueio de chamadas recebidas da PSTN (rede telefônica pública comutada).</span><span class="sxs-lookup"><span data-stu-id="acc23-103">Phone System Direct Routing and Calling Plans support blocking inbound calls from the Public Switched Telephone Network (PSTN).</span></span> <span data-ttu-id="acc23-104">Esse recurso permite que uma lista global de locatários de padrões de número seja definida para que a identificação de chamadas de todas as chamadas PSTN de entrada para o locatário possa ser verificada na lista para uma correspondência.</span><span class="sxs-lookup"><span data-stu-id="acc23-104">This feature allows a tenant global list of number patterns to be defined so that the caller ID of every incoming PSTN call to the tenant can be checked against the list for a match.</span></span> <span data-ttu-id="acc23-105">Se for feita uma correspondência, uma chamada de entrada será rejeitada.</span><span class="sxs-lookup"><span data-stu-id="acc23-105">If a match is made, an incoming call is rejected.</span></span>

<span data-ttu-id="acc23-106">Esse recurso de bloqueio de chamadas de entrada funciona apenas em chamadas de entrada que se originam da PSTN e só funciona em uma base global de locatários.</span><span class="sxs-lookup"><span data-stu-id="acc23-106">This inbound call blocking feature only works on inbound calls that originate from the PSTN and only works on a tenant-global basis.</span></span> <span data-ttu-id="acc23-107">Ele não está disponível para cada usuário.</span><span class="sxs-lookup"><span data-stu-id="acc23-107">It's not available on a per-user basis.</span></span>  

>[!NOTE]
> <span data-ttu-id="acc23-108">Os chamadores bloqueados podem experimentar comportamentos ligeiramente diferentes quando foram bloqueados.</span><span class="sxs-lookup"><span data-stu-id="acc23-108">Blocked callers may experience slightly different behaviors when they've been blocked.</span></span> <span data-ttu-id="acc23-109">O comportamento é baseado em como a operadora do chamador bloqueado manipula a notificação de que a chamada não pode ser concluída com êxito.</span><span class="sxs-lookup"><span data-stu-id="acc23-109">The behavior is based on how the blocked caller’s carrier handles the notification that the call isn't allowed to be successfully completed.</span></span> <span data-ttu-id="acc23-110">Os exemplos podem incluir uma mensagem de portadora informando que a chamada não pode ser concluída como discada ou simplesmente descartando a chamada.</span><span class="sxs-lookup"><span data-stu-id="acc23-110">Examples may include a carrier message stating the call can't be completed as dialed, or simply dropping the call.</span></span>

## <a name="call-blocking-admin-controls-and-information"></a><span data-ttu-id="acc23-111">Informações e controles de administração do bloqueio de chamadas</span><span class="sxs-lookup"><span data-stu-id="acc23-111">Call blocking admin controls and information</span></span>

<span data-ttu-id="acc23-112">Os controles de administrador para bloquear números são fornecidos somente com o uso do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="acc23-112">Admin controls for blocking numbers are provided using PowerShell only.</span></span> <span data-ttu-id="acc23-113">Padrões de blocos de números são definidos como padrões de expressão regular.</span><span class="sxs-lookup"><span data-stu-id="acc23-113">Number block patterns are defined as regular expression patterns.</span></span> <span data-ttu-id="acc23-114">A ordem das expressões é não importante – o primeiro padrão correspondido na lista resulta na bloqueio da chamada.</span><span class="sxs-lookup"><span data-stu-id="acc23-114">The order of the expressions is unimportant – the first pattern matched in the list results in the call being blocked.</span></span> <span data-ttu-id="acc23-115">Um novo número ou padrão que é adicionado ou removido na lista de chamadores bloqueados pode levar até 24 horas para que o padrão se torne ativo.</span><span class="sxs-lookup"><span data-stu-id="acc23-115">A new number or pattern that's added or removed in the blocked callers list may take up to 24 hours for the pattern to become active.</span></span>

## <a name="call-blocking-powershell-commands"></a><span data-ttu-id="acc23-116">Comandos do PowerShell de bloqueio de chamadas</span><span class="sxs-lookup"><span data-stu-id="acc23-116">Call blocking PowerShell commands</span></span>

<span data-ttu-id="acc23-117">Você gerencia padrões de número usando os cmdlets **New**, **Get**, **set**, **Remove**  - **CsInboundBlockedNumberPattern** .</span><span class="sxs-lookup"><span data-stu-id="acc23-117">You manage number patterns by using the **New**, **Get**, **Set**, **Remove** -**CsInboundBlockedNumberPattern** cmdlets.</span></span> <span data-ttu-id="acc23-118">Você pode gerenciar um determinado padrão usando esses cmdlets, incluindo a capacidade de alternar a ativação de um determinado padrão.</span><span class="sxs-lookup"><span data-stu-id="acc23-118">You can manage a given pattern by using these cmdlets, including the ability to toggle the activation of a given pattern.</span></span>

- <span data-ttu-id="acc23-119">[Get-CsInboundBlockedNumberPattern](https://docs.microsoft.com/powershell/module/skype/get-csinboundblockednumberpattern) retorna uma lista de todos os padrões de número bloqueados adicionados à lista de locatários, incluindo o nome, a descrição, habilitado (verdadeiro/falso) e o padrão para cada um deles.</span><span class="sxs-lookup"><span data-stu-id="acc23-119">[Get-CsInboundBlockedNumberPattern](https://docs.microsoft.com/powershell/module/skype/get-csinboundblockednumberpattern) returns a list of all blocked number patterns added to the tenant list including Name, Description, Enabled (True/False), and Pattern for each.</span></span>
- <span data-ttu-id="acc23-120">[New-CsInboundBlockedNumberPattern](https://docs.microsoft.com/powershell/module/skype/new-csinboundblockednumberpattern) adiciona um padrão de número bloqueado à lista de locatários.</span><span class="sxs-lookup"><span data-stu-id="acc23-120">[New-CsInboundBlockedNumberPattern](https://docs.microsoft.com/powershell/module/skype/new-csinboundblockednumberpattern) adds a blocked number pattern to the tenant list.</span></span>
- <span data-ttu-id="acc23-121">[Remove-CsInboundBlockedNumberPattern](https://docs.microsoft.com/powershell/module/skype/remove-csinboundblockednumberpattern) remove um padrão de número bloqueado da lista de locatários.</span><span class="sxs-lookup"><span data-stu-id="acc23-121">[Remove-CsInboundBlockedNumberPattern](https://docs.microsoft.com/powershell/module/skype/remove-csinboundblockednumberpattern) removes a blocked number pattern from the tenant list.</span></span>
- <span data-ttu-id="acc23-122">[Set-CsInboundBlockedNumberPattern](https://docs.microsoft.com/powershell/module/skype/set-csinboundblockednumberpattern) modifica um ou mais parâmetros de um padrão de número bloqueado na lista de locatários.</span><span class="sxs-lookup"><span data-stu-id="acc23-122">[Set-CsInboundBlockedNumberPattern](https://docs.microsoft.com/powershell/module/skype/set-csinboundblockednumberpattern) modifies one or more parameters of a blocked number pattern in the tenant list.</span></span>

<span data-ttu-id="acc23-123">A exibição e a ativação de todo o recurso de bloqueio de chamadas é gerenciada pelos cmdlets **Get**, **set**  - **CsTenantBlockingCallingNumbers** .</span><span class="sxs-lookup"><span data-stu-id="acc23-123">Viewing and activating the entire call blocking feature is managed through the **Get**, **Set** -**CsTenantBlockingCallingNumbers** cmdlets.</span></span>

- <span data-ttu-id="acc23-124">[Get-CsTenantBlockedCallingNumbers](https://docs.microsoft.com/powershell/module/skype/get-cstenantblockedcallingnumbers) retorna os parâmetros da lista de números bloqueados global, incluindo Enabled (true/false).</span><span class="sxs-lookup"><span data-stu-id="acc23-124">[Get-CsTenantBlockedCallingNumbers](https://docs.microsoft.com/powershell/module/skype/get-cstenantblockedcallingnumbers) returns the parameters for the global blocked number list including Enabled (True/False).</span></span> <span data-ttu-id="acc23-125">Há uma única política de locatário global que não pode ser modificada manualmente a não ser ativar ou desativar o recurso.</span><span class="sxs-lookup"><span data-stu-id="acc23-125">There's a single global tenant policy that can't be modified manually other than to turn the feature on or off.</span></span>
- <span data-ttu-id="acc23-126">[Set-CsTenantBlockedCallingNumbers](https://docs.microsoft.com/powershell/module/skype/set-cstenantblockedcallingnumbers) permite modificar as chamadas bloqueadas de locatário global para serem ativadas e desativadas no nível do locatário.</span><span class="sxs-lookup"><span data-stu-id="acc23-126">[Set-CsTenantBlockedCallingNumbers](https://docs.microsoft.com/powershell/module/skype/set-cstenantblockedcallingnumbers) allows modifying the global tenant blocked calls to be turned on and off at the tenant level.</span></span>

### <a name="examples"></a><span data-ttu-id="acc23-127">Exemplos</span><span class="sxs-lookup"><span data-stu-id="acc23-127">Examples</span></span>

#### <a name="block-a-number"></a><span data-ttu-id="acc23-128">Bloquear um número</span><span class="sxs-lookup"><span data-stu-id="acc23-128">Block a number</span></span>

<span data-ttu-id="acc23-129">Neste exemplo, os parâmetros **Enabled** e **Description** são opcionais.</span><span class="sxs-lookup"><span data-stu-id="acc23-129">In this example, the **Enabled** and **Description** parameters are optional.</span></span>

```powershell
New-CsInboundBlockedNumberPattern -Name “<name>” -Enabled $True -Description “<description>” -Pattern “^[+]?13125550000”
```

<span data-ttu-id="acc23-130">A criação de um novo padrão adiciona o padrão como habilitado por padrão.</span><span class="sxs-lookup"><span data-stu-id="acc23-130">Creating a new pattern adds the pattern as enabled by default.</span></span> <span data-ttu-id="acc23-131">A descrição é um campo opcional para fornecer mais informações.</span><span class="sxs-lookup"><span data-stu-id="acc23-131">The description is an optional field to provide more information.</span></span>

<span data-ttu-id="acc23-132">Recomendamos que você forneça um nome significativo para compreender facilmente porque o padrão foi adicionado.</span><span class="sxs-lookup"><span data-stu-id="acc23-132">We recommend that you provide a meaningful name to easily understand why the pattern was added.</span></span> <span data-ttu-id="acc23-133">No caso de simplesmente bloquear números de spam, considere nomear a regra da mesma forma que o padrão de número que está sendo correspondido e adicionar informações adicionais na descrição, conforme necessário.</span><span class="sxs-lookup"><span data-stu-id="acc23-133">In the case of simply blocking spam numbers, consider naming the rule the same as the number pattern that's being matched and add additional information in the description as required.</span></span>

<span data-ttu-id="acc23-134">Padrões são correspondentes usando-se expressões regulares (Regex).</span><span class="sxs-lookup"><span data-stu-id="acc23-134">Patterns are matched using Regular Expressions (Regex).</span></span> <span data-ttu-id="acc23-135">Aguarde tempo para a replicação antes de testar e validar.</span><span class="sxs-lookup"><span data-stu-id="acc23-135">Allow time for replication before you test and validate.</span></span>

#### <a name="allow-a-number"></a><span data-ttu-id="acc23-136">Permitir um número</span><span class="sxs-lookup"><span data-stu-id="acc23-136">Allow a number</span></span>

<span data-ttu-id="acc23-137">Neste exemplo, o parâmetro **Identity** é necessário.</span><span class="sxs-lookup"><span data-stu-id="acc23-137">In this example, the **Identity** parameter is required.</span></span>

```powershell
Remove-CsInboundBlockedNumberPattern -Identity “<identity>”
```
 
<span data-ttu-id="acc23-138">Se a identidade não for conhecida, use o cmdlet **Get-CsInboundBlockedNumberPattern** para primeiro localizar o padrão apropriado e anotar a identidade.</span><span class="sxs-lookup"><span data-stu-id="acc23-138">If the identity isn't known, use the **Get-CsInboundBlockedNumberPattern** cmdlet to first locate the proper pattern and note the identity.</span></span> <span data-ttu-id="acc23-139">Em seguida, execute o cmdlet **Remove-CsTenantBlockedNumberPattern** e transmita o valor de identidade apropriado.</span><span class="sxs-lookup"><span data-stu-id="acc23-139">Then, run the **Remove-CsTenantBlockedNumberPattern** cmdlet and pass the appropriate identity value.</span></span>

<span data-ttu-id="acc23-140">Aguarde tempo para a replicação antes de testar e validar.</span><span class="sxs-lookup"><span data-stu-id="acc23-140">Allow time for replication before you test and validate.</span></span>

#### <a name="view-all-number-patterns"></a><span data-ttu-id="acc23-141">Exibir todos os padrões de número</span><span class="sxs-lookup"><span data-stu-id="acc23-141">View all number patterns</span></span>

<span data-ttu-id="acc23-142">Executar esse cmdlet retorna uma lista de todos os números bloqueados que são inseridos para um locatário:</span><span class="sxs-lookup"><span data-stu-id="acc23-142">Running this cmdlet returns a list of all blocked numbers that are entered for a tenant:</span></span>

```powershell
Get-CsInboundBlockedNumberPattern
```

<span data-ttu-id="acc23-143">Use as capacidades de filtragem internas do PowerShell para analisar os valores retornados conforme necessário.</span><span class="sxs-lookup"><span data-stu-id="acc23-143">Use built-in PowerShell filtering abilities to parse the returned values as required.</span></span>

## <a name="add-number-exceptions"></a><span data-ttu-id="acc23-144">Adicionar exceções de número</span><span class="sxs-lookup"><span data-stu-id="acc23-144">Add number exceptions</span></span>

<span data-ttu-id="acc23-145">Você pode adicionar exceções a padrões de número bloqueados usando os cmdlets **New**, **Get**, **set**, **Remove**  - **CsTenantBlockNumberExceptionPattern** .</span><span class="sxs-lookup"><span data-stu-id="acc23-145">You can add exceptions to blocked number patterns by using the **New**, **Get**, **Set**, **Remove** -**CsTenantBlockNumberExceptionPattern** cmdlets.</span></span>

- <span data-ttu-id="acc23-146">[New-CsTenantBlockedNumberExceptionPattern](https://docs.microsoft.com/powershell/module/skype/new-cstenantblockednumberexceptionpattern) adiciona um padrão de exceção de número à lista de locatários.</span><span class="sxs-lookup"><span data-stu-id="acc23-146">[New-CsTenantBlockedNumberExceptionPattern](https://docs.microsoft.com/powershell/module/skype/new-cstenantblockednumberexceptionpattern) adds a number exception pattern to the tenant list.</span></span> 
- <span data-ttu-id="acc23-147">[Get-CsTenantBlockedNumberExceptionPattern](https://docs.microsoft.com/powershell/module/skype/get-cstenantblockednumberexceptionpattern) retorna uma lista de todos os padrões de exceção de número adicionados à lista de locatários.</span><span class="sxs-lookup"><span data-stu-id="acc23-147">[Get-CsTenantBlockedNumberExceptionPattern](https://docs.microsoft.com/powershell/module/skype/get-cstenantblockednumberexceptionpattern) returns a list of all number exception patterns added to the tenant list.</span></span>
- <span data-ttu-id="acc23-148">[Set-CsTenantBlockedNumberExceptionPattern](https://docs.microsoft.com/powershell/module/skype/set-cstenantblockednumberexceptionpattern) modifica um ou mais parâmetros para um padrão de exceção de número na lista de locatários.</span><span class="sxs-lookup"><span data-stu-id="acc23-148">[Set-CsTenantBlockedNumberExceptionPattern](https://docs.microsoft.com/powershell/module/skype/set-cstenantblockednumberexceptionpattern) modifies one or more parameters to a number exception pattern in the tenant list.</span></span>
- <span data-ttu-id="acc23-149">[Remove-CsTenantBlockedNumberExceptionPattern](https://docs.microsoft.com/powershell/module/skype/remove-cstenantblockednumberexceptionpattern) remove um padrão de exceção de número da lista de locatários.</span><span class="sxs-lookup"><span data-stu-id="acc23-149">[Remove-CsTenantBlockedNumberExceptionPattern](https://docs.microsoft.com/powershell/module/skype/remove-cstenantblockednumberexceptionpattern) removes a number exception pattern from the tenant list.</span></span>

### <a name="examples"></a><span data-ttu-id="acc23-150">Exemplos</span><span class="sxs-lookup"><span data-stu-id="acc23-150">Examples</span></span>

#### <a name="add-a-number-exception"></a><span data-ttu-id="acc23-151">Adicionar uma exceção de número</span><span class="sxs-lookup"><span data-stu-id="acc23-151">Add a number exception</span></span>

<span data-ttu-id="acc23-152">Neste exemplo, um novo padrão de exceção de número é criado e, por padrão, adiciona o padrão como habilitado.</span><span class="sxs-lookup"><span data-stu-id="acc23-152">In this example, a new number exception pattern is created and will by default add the pattern as enabled.</span></span> <span data-ttu-id="acc23-153">Os parâmetros **Enabled** e **Description** são opcionais.</span><span class="sxs-lookup"><span data-stu-id="acc23-153">The **Enabled** and **Description** parameters are optional.</span></span>

```powershell
New-CsTenantBlockedNumberExceptionPattern -Identity <XdsGlobalRelativeIdentity> -Tenant <GUID> -Pattern <String> -Enabled <bool> -Description <string>
```

```powershell
New-CsTenantBlockedNumberExceptionPattern -Identity InternationalPrefix -Tenant daacb588-18ef-4f77-8c83-955af9615930 -Pattern "^011(\d*)$" -Description "Allow international prefix in US"  
```

#### <a name="view-all-number-exceptions"></a><span data-ttu-id="acc23-154">Exibir todas as exceções de número</span><span class="sxs-lookup"><span data-stu-id="acc23-154">View all number exceptions</span></span>

<span data-ttu-id="acc23-155">Neste exemplo, o parâmetro **Identity** é opcional.</span><span class="sxs-lookup"><span data-stu-id="acc23-155">In this example, the **Identity** parameter is optional.</span></span> <span data-ttu-id="acc23-156">Se o parâmetro **Identity** não for especificado, esse cmdlet retornará uma lista de todos os padrões de exceção de número inseridos para um locatário.</span><span class="sxs-lookup"><span data-stu-id="acc23-156">If the **Identity** parameter isn't specified, this cmdlet returns a list of all number exception patterns entered for a tenant.</span></span>
 
```powershell
Get-CsTenantBlockedNumberExceptionPattern -Identity <XdsGlobalRelativeIdentity> -Tenant <GUID>
```
 
```powershell
Get-CsTenantBlockedNumberExceptionPattern -Tenant daacb588-18ef-4f77-8c83-955af9615930
```

#### <a name="modify-a-number-exception"></a><span data-ttu-id="acc23-157">Modificar uma exceção de número</span><span class="sxs-lookup"><span data-stu-id="acc23-157">Modify a number exception</span></span>

<span data-ttu-id="acc23-158">Neste exemplo, o parâmetro **Identity** é obrigatório.</span><span class="sxs-lookup"><span data-stu-id="acc23-158">In this example, the **Identity** parameter is mandatory.</span></span> <span data-ttu-id="acc23-159">O cmdlet **set-CsTenantBlockedNumberExceptionPattern** permite modificar um ou mais parâmetros para uma determinada identidade de padrão de número.</span><span class="sxs-lookup"><span data-stu-id="acc23-159">The **Set-CsTenantBlockedNumberExceptionPattern** cmdlet lets you modify one or more parameters for a given number pattern identity.</span></span>
 
```powershell
Set-CsTenantBlockedNumberExceptionPattern -Identity <XdsGlobalRelativeIdentity> -Tenant <GUID> -Enabled <bool> -Description <string> -Pattern <string> 
```

```powershell
Set-CsTenantBlockedNumberExceptionPattern -Identity InternationalPrefix -Tenant daacb588-18ef-4f77-8c83-955af9615930  -Pattern "^022(\d*)$" 
```

#### <a name="remove-a-number-exception"></a><span data-ttu-id="acc23-160">Remover uma exceção de número</span><span class="sxs-lookup"><span data-stu-id="acc23-160">Remove a number exception</span></span>

<span data-ttu-id="acc23-161">Neste exemplo, o parâmetro **Identity** é necessário.</span><span class="sxs-lookup"><span data-stu-id="acc23-161">In this example, the **Identity** parameter is required.</span></span> <span data-ttu-id="acc23-162">Esse cmdlet removerá o padrão de número especificado da lista de locatários.</span><span class="sxs-lookup"><span data-stu-id="acc23-162">This cmdlet will remove the given number pattern from the tenant list.</span></span>  <span data-ttu-id="acc23-163">Se a identidade não for conhecida, use o cmdlet **Get-CsInboundBlockedNumberPattern** para primeiro localizar o padrão apropriado e anotar a identidade.</span><span class="sxs-lookup"><span data-stu-id="acc23-163">If the identity isn't known, use the **Get-CsInboundBlockedNumberPattern** cmdlet to first locate the proper pattern and note the identity.</span></span> <span data-ttu-id="acc23-164">Em seguida, execute o cmdlet **Remove-CsTenantBlockedNumberExceptionPattern** e transmita o valor de identidade apropriado.</span><span class="sxs-lookup"><span data-stu-id="acc23-164">Then, run the **Remove-CsTenantBlockedNumberExceptionPattern** cmdlet and pass the appropriate identity value.</span></span><span data-ttu-id="acc23-165">Aguarde tempo para a replicação antes de testar e validar.</span><span class="sxs-lookup"><span data-stu-id="acc23-165"> Allow time for replication before you test and validate.</span></span>  

```powershell
Remove-CsTenantBlockedNumberExceptionPattern -Identity <XdsGlobalRelativeIdentity> -Tenant <GUID>
```

```powershell
Remove-CsTenantBlockedNumberExceptionPattern -Identity InternationalPrefix -Tenant daacb588-18ef-4f77-8c83-955af9615930
```

### <a name="test-whether-a-number-is-blocked"></a><span data-ttu-id="acc23-166">Testar se um número está bloqueado</span><span class="sxs-lookup"><span data-stu-id="acc23-166">Test whether a number is blocked</span></span>

<span data-ttu-id="acc23-167">Use o cmdlet **Test-CsInboundBlockedNumberPattern** para verificar se um número está bloqueado no locatário.</span><span class="sxs-lookup"><span data-stu-id="acc23-167">Use the **Test-CsInboundBlockedNumberPattern** cmdlet to verify whether a number is blocked in the tenant.</span></span>
 
<span data-ttu-id="acc23-168">Neste exemplo, os parâmetros **intervalo** e **locatário** são obrigatórios.</span><span class="sxs-lookup"><span data-stu-id="acc23-168">In this example, the **PhoneNumber** and **Tenant** parameters are required.</span></span> <span data-ttu-id="acc23-169">O parâmetro **intervalo** deve ser uma cadeia de caracteres numérica sem caracteres adicionais, como + ou-.</span><span class="sxs-lookup"><span data-stu-id="acc23-169">The **PhoneNumber** parameter should be a numeric string without any additional characters such as + or -.</span></span> <span data-ttu-id="acc23-170">No TRPS, o **parâmetro locatário** é opcional.</span><span class="sxs-lookup"><span data-stu-id="acc23-170">In TRPS, the **Tenant parameter** is optional.</span></span> <span data-ttu-id="acc23-171">O parâmetro **isNumberBlocked** resultante retorna um valor de true se o número estiver bloqueado no locatário e false se não estiver bloqueado.</span><span class="sxs-lookup"><span data-stu-id="acc23-171">The resulting **isNumberBlocked** parameter returns a value of True if the number is blocked in the tenant and False if it's not blocked.</span></span>

```powershell
Test-CsInboundBlockedNumberPattern –Tenant <GUID> -PhoneNumber <String>
```

```powershell
Test-CsInboundBlockedNumberPattern -Tenant e09ad6bc-1d3c-4650-8cae-02f6c5a04b45 -PhoneNumber 4255550101
```

|<span data-ttu-id="acc23-172">httpResponseCode</span><span class="sxs-lookup"><span data-stu-id="acc23-172">httpResponseCode</span></span>  |<span data-ttu-id="acc23-173">isNumberBlocked</span><span class="sxs-lookup"><span data-stu-id="acc23-173">isNumberBlocked</span></span>   |<span data-ttu-id="acc23-174">errorMessage</span><span class="sxs-lookup"><span data-stu-id="acc23-174">errorMessage</span></span> |
|---------|---------|---------|
|<span data-ttu-id="acc23-175">200</span><span class="sxs-lookup"><span data-stu-id="acc23-175">200</span></span>    | <span data-ttu-id="acc23-176">Verdadeiro</span><span class="sxs-lookup"><span data-stu-id="acc23-176">True</span></span>        |         |

```powershell
Test-CsInboundBlockedNumberPattern -Tenant e09ad6bc-1d3c-4650-8cae-02f6c5a04b45 -PhoneNumber 6045550188
```

|<span data-ttu-id="acc23-177">httpResponseCode</span><span class="sxs-lookup"><span data-stu-id="acc23-177">httpResponseCode</span></span>  |<span data-ttu-id="acc23-178">isNumberBlocked</span><span class="sxs-lookup"><span data-stu-id="acc23-178">isNumberBlocked</span></span>   |<span data-ttu-id="acc23-179">errorMessage</span><span class="sxs-lookup"><span data-stu-id="acc23-179">errorMessage</span></span> |
|---------|---------|---------|
|<span data-ttu-id="acc23-180">200</span><span class="sxs-lookup"><span data-stu-id="acc23-180">200</span></span>    | <span data-ttu-id="acc23-181">Falso</span><span class="sxs-lookup"><span data-stu-id="acc23-181">False</span></span>        |         |

## <a name="a-note-about-regex"></a><span data-ttu-id="acc23-182">Uma observação sobre Regex</span><span class="sxs-lookup"><span data-stu-id="acc23-182">A note about Regex</span></span>

<span data-ttu-id="acc23-183">Conforme declarado anteriormente, a correspondência de padrão para bloquear chamadores é feita usando Regex.</span><span class="sxs-lookup"><span data-stu-id="acc23-183">As stated earlier, the pattern matching for blocking callers is done by using Regex.</span></span> <span data-ttu-id="acc23-184">Há várias ferramentas disponíveis online para ajudar a validar uma correspondência de padrão de Regex.</span><span class="sxs-lookup"><span data-stu-id="acc23-184">Multiple tools are available online to help validate a Regex pattern match.</span></span> <span data-ttu-id="acc23-185">Se você não estiver familiarizado com padrões de Regex, recomendamos que leve algum tempo para se familiarizar com as noções básicas.</span><span class="sxs-lookup"><span data-stu-id="acc23-185">If you aren't familiar with Regex patterns, we recommend that you take some time to familiarize yourself with the basics.</span></span> <span data-ttu-id="acc23-186">Para garantir que você tenha resultados esperados, use uma ferramenta para validar as correspondências de padrão antes de adicionar um novo número bloqueado correspondente ao seu locatário.</span><span class="sxs-lookup"><span data-stu-id="acc23-186">To make sure you get expected results, use a tool for validating pattern matches before you add new blocked number matches to your tenant.</span></span>
