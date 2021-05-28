---
title: Bloquear chamadas de entrada em Microsoft Teams
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
ms.openlocfilehash: e584e9f0c16ef77424121c37ce87c6d63afb4b92
ms.sourcegitcommit: 17e34d2de3d10f1d04929a695e301127db7014bd
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/27/2021
ms.locfileid: "52689759"
---
# <a name="block-inbound-calls"></a><span data-ttu-id="6f5a3-102">Bloquear chamadas de entrada</span><span class="sxs-lookup"><span data-stu-id="6f5a3-102">Block inbound calls</span></span>

<span data-ttu-id="6f5a3-103">Planos de Chamadas da Microsoft, Roteamento Direto e Operador Conexão todos suportam o bloqueio de chamadas de entrada da PSTN (Rede Telefônica Pública Comucionária).</span><span class="sxs-lookup"><span data-stu-id="6f5a3-103">Microsoft Calling Plans, Direct Routing, and Operator Connect all support blocking inbound calls from the Public Switched Telephone Network (PSTN).</span></span> <span data-ttu-id="6f5a3-104">Esse recurso permite que um administrador defina uma lista de padrões de números no nível global do locatário para que a ID do chamador de cada chamada PSTN de entrada para o locatário possa ser verificada na lista para uma combinação.</span><span class="sxs-lookup"><span data-stu-id="6f5a3-104">This feature allows an administrator to define a  list of number patterns at the tenant global level so that the caller ID of every incoming PSTN call to the tenant can be checked against the list for a match.</span></span> <span data-ttu-id="6f5a3-105">Se uma combinação for feita, uma chamada de entrada será rejeitada.</span><span class="sxs-lookup"><span data-stu-id="6f5a3-105">If a match is made, an incoming call is rejected.</span></span>

<span data-ttu-id="6f5a3-106">Esse recurso de bloqueio de chamada de entrada só funciona em chamadas de entrada que se originam da PSTN e só funcionam em um nível global do locatário.</span><span class="sxs-lookup"><span data-stu-id="6f5a3-106">This inbound call blocking feature only works on inbound calls that originate from the PSTN and only works on a tenant global level.</span></span> <span data-ttu-id="6f5a3-107">Usuários Teams individuais não podem manipular essa lista.</span><span class="sxs-lookup"><span data-stu-id="6f5a3-107">Individual Teams users can’t manipulate this list.</span></span> <span data-ttu-id="6f5a3-108">O Teams cliente permite que usuários individuais bloqueiem chamadas PSTN.</span><span class="sxs-lookup"><span data-stu-id="6f5a3-108">The Teams client does allow individual users to block PSTN calls.</span></span> <span data-ttu-id="6f5a3-109">Para obter informações sobre como os usuários finais podem implementar o bloqueio de chamada, consulte [Manage call settings in Teams](https://support.microsoft.com/office/manage-your-call-settings-in-teams-456cb611-3477-496f-b31a-6ab752a7595f).</span><span class="sxs-lookup"><span data-stu-id="6f5a3-109">For information about how your end users can implement call blocking, see [Manage call settings in Teams](https://support.microsoft.com/office/manage-your-call-settings-in-teams-456cb611-3477-496f-b31a-6ab752a7595f).</span></span>

>[!NOTE]
> <span data-ttu-id="6f5a3-110">Os chamadores bloqueados podem ter comportamentos ligeiramente diferentes quando foram bloqueados.</span><span class="sxs-lookup"><span data-stu-id="6f5a3-110">Blocked callers may experience slightly different behaviors when they've been blocked.</span></span> <span data-ttu-id="6f5a3-111">O comportamento se baseia em como a operadora do chamador bloqueado lida com a notificação de que a chamada não tem permissão para ser concluída com êxito.</span><span class="sxs-lookup"><span data-stu-id="6f5a3-111">The behavior is based on how the blocked caller’s carrier handles the notification that the call isn't allowed to be successfully completed.</span></span> <span data-ttu-id="6f5a3-112">Exemplos podem incluir uma mensagem de operadora informando que a chamada não pode ser concluída como discada ou simplesmente soltando a chamada.</span><span class="sxs-lookup"><span data-stu-id="6f5a3-112">Examples may include a carrier message stating the call can't be completed as dialed, or simply dropping the call.</span></span>

## <a name="call-blocking-admin-controls-and-information"></a><span data-ttu-id="6f5a3-113">Informações e controles de administrador de bloqueio de chamada</span><span class="sxs-lookup"><span data-stu-id="6f5a3-113">Call blocking admin controls and information</span></span>

<span data-ttu-id="6f5a3-114">Os controles de administrador para números de bloqueio são fornecidos usando apenas o PowerShell.</span><span class="sxs-lookup"><span data-stu-id="6f5a3-114">Admin controls for blocking numbers are provided using PowerShell only.</span></span> <span data-ttu-id="6f5a3-115">Padrões de bloco de números são definidos como padrões de expressão regulares.</span><span class="sxs-lookup"><span data-stu-id="6f5a3-115">Number block patterns are defined as regular expression patterns.</span></span> <span data-ttu-id="6f5a3-116">A ordem das expressões não é importante – o primeiro padrão que é matched na lista resulta no bloqueio da chamada.</span><span class="sxs-lookup"><span data-stu-id="6f5a3-116">The order of the expressions is unimportant – the first pattern matched in the list results in the call being blocked.</span></span> <span data-ttu-id="6f5a3-117">Um novo número ou padrão adicionado ou removido na lista de chamadores bloqueados pode levar até 24 horas para que o padrão se torne ativo.</span><span class="sxs-lookup"><span data-stu-id="6f5a3-117">A new number or pattern that's added or removed in the blocked callers list may take up to 24 hours for the pattern to become active.</span></span>

## <a name="call-blocking-powershell-commands"></a><span data-ttu-id="6f5a3-118">Comandos de bloqueio de chamada do PowerShell</span><span class="sxs-lookup"><span data-stu-id="6f5a3-118">Call blocking PowerShell commands</span></span>

<span data-ttu-id="6f5a3-119">Você gerencia padrões de números usando os cmdlets **New-**, **Get-,** **Set-** e **Remove-CsInboundBlockedNumberPattern.**</span><span class="sxs-lookup"><span data-stu-id="6f5a3-119">You manage number patterns by using the **New-**, **Get-**, **Set-**, and **Remove-CsInboundBlockedNumberPattern** cmdlets.</span></span> <span data-ttu-id="6f5a3-120">Você pode gerenciar um determinado padrão usando esses cmdlets, incluindo a capacidade de alternar a ativação de um determinado padrão.</span><span class="sxs-lookup"><span data-stu-id="6f5a3-120">You can manage a given pattern by using these cmdlets, including the ability to toggle the activation of a given pattern.</span></span>

- <span data-ttu-id="6f5a3-121">[Get-CsInboundBlockedNumberPattern](/powershell/module/skype/get-csinboundblockednumberpattern) retorna uma lista de todos os padrões de números bloqueados adicionados à lista de locatários, incluindo Nome, Descrição, Habilitado (True/False) e Padrão para cada um.</span><span class="sxs-lookup"><span data-stu-id="6f5a3-121">[Get-CsInboundBlockedNumberPattern](/powershell/module/skype/get-csinboundblockednumberpattern) returns a list of all blocked number patterns added to the tenant list including Name, Description, Enabled (True/False), and Pattern for each.</span></span>
- <span data-ttu-id="6f5a3-122">[New-CsInboundBlockedNumberPattern](/powershell/module/skype/new-csinboundblockednumberpattern) adiciona um padrão de número bloqueado à lista de locatários.</span><span class="sxs-lookup"><span data-stu-id="6f5a3-122">[New-CsInboundBlockedNumberPattern](/powershell/module/skype/new-csinboundblockednumberpattern) adds a blocked number pattern to the tenant list.</span></span>
- <span data-ttu-id="6f5a3-123">[Remove-CsInboundBlockedNumberPattern](/powershell/module/skype/remove-csinboundblockednumberpattern) remove um padrão de número bloqueado da lista de locatários.</span><span class="sxs-lookup"><span data-stu-id="6f5a3-123">[Remove-CsInboundBlockedNumberPattern](/powershell/module/skype/remove-csinboundblockednumberpattern) removes a blocked number pattern from the tenant list.</span></span>
- <span data-ttu-id="6f5a3-124">[Set-CsInboundBlockedNumberPattern](/powershell/module/skype/set-csinboundblockednumberpattern) modifica um ou mais parâmetros de um padrão de número bloqueado na lista de locatários.</span><span class="sxs-lookup"><span data-stu-id="6f5a3-124">[Set-CsInboundBlockedNumberPattern](/powershell/module/skype/set-csinboundblockednumberpattern) modifies one or more parameters of a blocked number pattern in the tenant list.</span></span>

<span data-ttu-id="6f5a3-125">A exibição e a ativação de todo o recurso de bloqueio de chamadas é gerenciada por meio dos cmdlets **Get e** **Set-CsTenantBlockingCallingNumbers.**</span><span class="sxs-lookup"><span data-stu-id="6f5a3-125">Viewing and activating the entire call blocking feature is managed through the **Get-** and **Set-CsTenantBlockingCallingNumbers** cmdlets.</span></span>

- <span data-ttu-id="6f5a3-126">[Get-CsTenantBlockedCallingNumbers](/powershell/module/skype/get-cstenantblockedcallingnumbers) retorna os padrões de número de bloco de entrada e os parâmetros de padrões de número isentos de entrada para a lista de números bloqueados global.</span><span class="sxs-lookup"><span data-stu-id="6f5a3-126">[Get-CsTenantBlockedCallingNumbers](/powershell/module/skype/get-cstenantblockedcallingnumbers) returns the inbound block number patterns and the inbound exempt number patterns parameters for the global blocked number list.</span></span> <span data-ttu-id="6f5a3-127">Este cmdlet também retorna se o bloqueio foi habilitado (True ou False).</span><span class="sxs-lookup"><span data-stu-id="6f5a3-127">This cmdlet also returns whether blocking has been Enabled (True or False).</span></span> <span data-ttu-id="6f5a3-128">Há uma única política de locatário global que não pode ser modificada manualmente, além de ativar ou desativar o recurso.</span><span class="sxs-lookup"><span data-stu-id="6f5a3-128">There's a single global tenant policy that can't be modified manually other than to turn the feature on or off.</span></span>
- <span data-ttu-id="6f5a3-129">[Set-CsTenantBlockedCallingNumbers](/powershell/module/skype/set-cstenantblockedcallingnumbers) permite modificar as chamadas de locatário global bloqueadas para serem ativas e desligadas no nível do locatário.</span><span class="sxs-lookup"><span data-stu-id="6f5a3-129">[Set-CsTenantBlockedCallingNumbers](/powershell/module/skype/set-cstenantblockedcallingnumbers) allows modifying the global tenant blocked calls to be turned on and off at the tenant level.</span></span>

### <a name="examples"></a><span data-ttu-id="6f5a3-130">Exemplos</span><span class="sxs-lookup"><span data-stu-id="6f5a3-130">Examples</span></span>

#### <a name="block-a-number"></a><span data-ttu-id="6f5a3-131">Bloquear um número</span><span class="sxs-lookup"><span data-stu-id="6f5a3-131">Block a number</span></span>

<span data-ttu-id="6f5a3-132">No exemplo a seguir, o administrador de locatários deseja bloquear todas as chamadas provenientes do intervalo de números 1 (312) 555-0000 a 1 (312) 555-9999.</span><span class="sxs-lookup"><span data-stu-id="6f5a3-132">In the following example, the tenant administrator wants to block all calls coming from the number range 1 (312) 555-0000 to 1 (312) 555-9999.</span></span> <span data-ttu-id="6f5a3-133">O padrão de número é criado para que ambos os números no intervalo com + prefixados e números no intervalo sem + prefixados sejam matched.</span><span class="sxs-lookup"><span data-stu-id="6f5a3-133">The number pattern is created so that both numbers in range with + prefixed and numbers in the range without + prefixed are matched.</span></span> <span data-ttu-id="6f5a3-134">Você não precisa incluir os símbolos – e () nos números de telefone porque o sistema tira esses símbolos antes de corresponder.</span><span class="sxs-lookup"><span data-stu-id="6f5a3-134">You don’t need to include the symbols – and () in the phone numbers because the system strips these symbols before matching.</span></span>  <span data-ttu-id="6f5a3-135">Para ativar o padrão de número, o **parâmetro Enabled** é definido como True.</span><span class="sxs-lookup"><span data-stu-id="6f5a3-135">To turn on the number pattern, the **Enabled** parameter is set to True.</span></span> <span data-ttu-id="6f5a3-136">Para desabilitar esse padrão de número específico, de definir o parâmetro como False.</span><span class="sxs-lookup"><span data-stu-id="6f5a3-136">To disable this specific number pattern, set the parameter to False.</span></span>

```PowerShell
New-CsInboundBlockedNumberPattern -Name "BlockRange1" -Enabled $True -Description "Block Contoso" -Pattern "^\+?1312555\d{4}$"
```

<span data-ttu-id="6f5a3-137">No próximo exemplo, o administrador de locatários deseja bloquear todas as chamadas provenientes do número 1 (412) 555-1234.</span><span class="sxs-lookup"><span data-stu-id="6f5a3-137">In the next example, the tenant administrator wants to block all calls coming from the number 1 (412) 555-1234.</span></span> <span data-ttu-id="6f5a3-138">Para ativar o padrão de número, o **parâmetro Enabled** é definido como True.</span><span class="sxs-lookup"><span data-stu-id="6f5a3-138">To turn on the number pattern, the **Enabled** parameter is set to True.</span></span>

```PowerShell
New-CsInboundBlockedNumberPattern -Name "BlockNumber1" -Enabled $True -Description "Block Fabrikam" -Pattern "^\+?14125551234$"
```

<span data-ttu-id="6f5a3-139">A criação de um novo padrão adiciona o padrão conforme habilitado por padrão.</span><span class="sxs-lookup"><span data-stu-id="6f5a3-139">Creating a new pattern adds the pattern as enabled by default.</span></span> <span data-ttu-id="6f5a3-140">A descrição é um campo opcional para fornecer mais informações.</span><span class="sxs-lookup"><span data-stu-id="6f5a3-140">The description is an optional field to provide more information.</span></span>

<span data-ttu-id="6f5a3-141">Recomendamos que você forneça um nome significativo para entender facilmente por que o padrão foi adicionado.</span><span class="sxs-lookup"><span data-stu-id="6f5a3-141">We recommend that you provide a meaningful name to easily understand why the pattern was added.</span></span> <span data-ttu-id="6f5a3-142">No caso de simplesmente bloquear números de spam, considere nomear a regra da mesma forma que o padrão de número que está sendo corresponder e adicionar informações adicionais na descrição conforme necessário.</span><span class="sxs-lookup"><span data-stu-id="6f5a3-142">In the case of simply blocking spam numbers, consider naming the rule the same as the number pattern that's being matched and add additional information in the description as required.</span></span>

<span data-ttu-id="6f5a3-143">Os padrões são corresponderem usando Expressões Regulares (Regex).</span><span class="sxs-lookup"><span data-stu-id="6f5a3-143">Patterns are matched using Regular Expressions (Regex).</span></span> <span data-ttu-id="6f5a3-144">Para obter mais informações, consulte [Using Regex](#using-regex).</span><span class="sxs-lookup"><span data-stu-id="6f5a3-144">For more information, see [Using Regex](#using-regex).</span></span>

<span data-ttu-id="6f5a3-145">Permitir tempo para replicação antes de testar e validar.</span><span class="sxs-lookup"><span data-stu-id="6f5a3-145">Allow time for replication before you test and validate.</span></span> 

#### <a name="allow-a-number"></a><span data-ttu-id="6f5a3-146">Permitir um número</span><span class="sxs-lookup"><span data-stu-id="6f5a3-146">Allow a number</span></span>

<span data-ttu-id="6f5a3-147">Você pode permitir que um número chame removendo o padrão de número bloqueado.</span><span class="sxs-lookup"><span data-stu-id="6f5a3-147">You can allow a number to call by removing the blocked number pattern.</span></span> <span data-ttu-id="6f5a3-148">No exemplo a seguir, o administrador de locatários deseja permitir que 1 (412) 555-1234 faça chamadas novamente.</span><span class="sxs-lookup"><span data-stu-id="6f5a3-148">In the following example, the tenant administrator wants to allow 1 (412) 555-1234 to make calls again.</span></span>

```PowerShell
Remove-CsInboundBlockedNumberPattern -Identity "BlockNumber1"
```
 
<span data-ttu-id="6f5a3-149">Se a identidade não for conhecida, use o cmdlet **Get-CsInboundBlockedNumberPattern** para localizar primeiro o padrão adequado e observar a identidade.</span><span class="sxs-lookup"><span data-stu-id="6f5a3-149">If the identity isn't known, use the **Get-CsInboundBlockedNumberPattern** cmdlet to first locate the proper pattern and note the identity.</span></span> <span data-ttu-id="6f5a3-150">Em seguida, execute o cmdlet **Remove-CsInboundBlockedNumberPattern** e passe o valor de identidade apropriado.</span><span class="sxs-lookup"><span data-stu-id="6f5a3-150">Then, run the **Remove-CsInboundBlockedNumberPattern** cmdlet and pass the appropriate identity value.</span></span>

<span data-ttu-id="6f5a3-151">Permitir tempo para replicação antes de testar e validar.</span><span class="sxs-lookup"><span data-stu-id="6f5a3-151">Allow time for replication before you test and validate.</span></span>

#### <a name="view-all-number-patterns"></a><span data-ttu-id="6f5a3-152">Exibir todos os padrões de números</span><span class="sxs-lookup"><span data-stu-id="6f5a3-152">View all number patterns</span></span>

<span data-ttu-id="6f5a3-153">Executar este cmdlet retorna uma lista de todos os números bloqueados inseridos para um locatário:</span><span class="sxs-lookup"><span data-stu-id="6f5a3-153">Running this cmdlet returns a list of all blocked numbers that are entered for a tenant:</span></span>

```powershell
Get-CsInboundBlockedNumberPattern
```

<span data-ttu-id="6f5a3-154">Use as habilidades de filtragem do PowerShell integrados para analisar os valores retornados conforme necessário.</span><span class="sxs-lookup"><span data-stu-id="6f5a3-154">Use built-in PowerShell filtering abilities to parse the returned values as required.</span></span>

## <a name="add-number-exceptions"></a><span data-ttu-id="6f5a3-155">Adicionar exceções de número</span><span class="sxs-lookup"><span data-stu-id="6f5a3-155">Add number exceptions</span></span>

<span data-ttu-id="6f5a3-156">Você pode adicionar exceções a padrões de números bloqueados usando os cmdlets **New-**, **Get-**, **Set-** e **Remove-CsInboundExemptNumberPattern.**</span><span class="sxs-lookup"><span data-stu-id="6f5a3-156">You can add exceptions to blocked number patterns by using the **New-**, **Get-**, **Set-**, and **Remove-CsInboundExemptNumberPattern** cmdlets.</span></span>

- <span data-ttu-id="6f5a3-157">[New-CsInboundExemptNumberPattern](/powershell/module/skype/New-CsInboundExemptNumberPattern) adiciona um padrão de exceção de número à lista de locatários.</span><span class="sxs-lookup"><span data-stu-id="6f5a3-157">[New-CsInboundExemptNumberPattern](/powershell/module/skype/New-CsInboundExemptNumberPattern) adds a number exception pattern to the tenant list.</span></span> 
- <span data-ttu-id="6f5a3-158">[Get-CsInboundExemptNumberPattern](/powershell/module/skype/Get-CsInboundExemptNumberPattern) retorna uma lista de todos os padrões de exceção de número adicionados à lista de locatários.</span><span class="sxs-lookup"><span data-stu-id="6f5a3-158">[Get-CsInboundExemptNumberPattern](/powershell/module/skype/Get-CsInboundExemptNumberPattern) returns a list of all number exception patterns added to the tenant list.</span></span>
- <span data-ttu-id="6f5a3-159">[Set-CsInboundExemptNumberPattern](/powershell/module/skype/Set-CsInboundExemptNumberPattern) modifica um ou mais parâmetros para um padrão de exceção de número na lista de locatários.</span><span class="sxs-lookup"><span data-stu-id="6f5a3-159">[Set-CsInboundExemptNumberPattern](/powershell/module/skype/Set-CsInboundExemptNumberPattern) modifies one or more parameters to a number exception pattern in the tenant list.</span></span>
- <span data-ttu-id="6f5a3-160">[Remove-CsInboundExemptNumberPattern](/powershell/module/skype/Remove-CsInboundExemptNumberPattern) remove um padrão de exceção de número da lista de locatários.</span><span class="sxs-lookup"><span data-stu-id="6f5a3-160">[Remove-CsInboundExemptNumberPattern](/powershell/module/skype/Remove-CsInboundExemptNumberPattern) removes a number exception pattern from the tenant list.</span></span>

### <a name="examples"></a><span data-ttu-id="6f5a3-161">Exemplos</span><span class="sxs-lookup"><span data-stu-id="6f5a3-161">Examples</span></span>

#### <a name="add-a-number-exception"></a><span data-ttu-id="6f5a3-162">Adicionar uma exceção de número</span><span class="sxs-lookup"><span data-stu-id="6f5a3-162">Add a number exception</span></span>

<span data-ttu-id="6f5a3-163">No exemplo a seguir, o administrador de locatários deseja permitir que os números de telefone 1 (312) 555-8882 e 1 (312) 555-8883 façam chamadas para o locatário, mesmo que esses dois números de telefone estão no intervalo bloqueado no exemplo acima.</span><span class="sxs-lookup"><span data-stu-id="6f5a3-163">In the following example, the tenant administrator wants to allow the phone numbers 1 (312) 555-8882 and 1 (312) 555-8883 to make calls to the tenant, even if these two phone numbers are in the range that has been blocked in the example above.</span></span> <span data-ttu-id="6f5a3-164">Para habilitar isso, um novo padrão de exceção de número é criado da seguinte forma:</span><span class="sxs-lookup"><span data-stu-id="6f5a3-164">To enable this, a new number exception pattern is created as follows:</span></span>

```PowerShell
New-CsInboundExemptNumberPattern  -Identity "AllowContoso1" -Pattern "^\+?1312555888[2|3]$" -Description "Allow Contoso helpdesk" -Enabled $True
```

<span data-ttu-id="6f5a3-165">Para ativar o padrão de número, o **parâmetro Enabled** é definido como True.</span><span class="sxs-lookup"><span data-stu-id="6f5a3-165">To turn on the number pattern, the **Enabled** parameter is set to True.</span></span> <span data-ttu-id="6f5a3-166">Para desabilitar esse padrão de número específico, de definir o parâmetro como False.</span><span class="sxs-lookup"><span data-stu-id="6f5a3-166">To disable this specific number pattern, set the parameter to False.</span></span>


#### <a name="view-all-number-exceptions"></a><span data-ttu-id="6f5a3-167">Exibir todas as exceções de número</span><span class="sxs-lookup"><span data-stu-id="6f5a3-167">View all number exceptions</span></span>

<span data-ttu-id="6f5a3-168">Neste exemplo, o parâmetro **Identity** é opcional.</span><span class="sxs-lookup"><span data-stu-id="6f5a3-168">In this example, the **Identity** parameter is optional.</span></span> <span data-ttu-id="6f5a3-169">Se o **parâmetro Identity** não for especificado, este cmdlet retornará uma lista de todos os padrões de exceção de número inseridos para um locatário.</span><span class="sxs-lookup"><span data-stu-id="6f5a3-169">If the **Identity** parameter isn't specified, this cmdlet returns a list of all number exception patterns entered for a tenant.</span></span>
 
```powershell
Get-CsInboundExemptNumberPattern -Identity <String>
```
 
```powershell
Get-CsInboundExemptNumberPattern 
```

#### <a name="modify-a-number-exception"></a><span data-ttu-id="6f5a3-170">Modificar uma exceção de número</span><span class="sxs-lookup"><span data-stu-id="6f5a3-170">Modify a number exception</span></span>

<span data-ttu-id="6f5a3-171">O cmdlet **Set-CsInboundExemptNumberPattern** permite modificar um ou mais parâmetros para uma determinada identidade de padrão de número.</span><span class="sxs-lookup"><span data-stu-id="6f5a3-171">The **Set-CsInboundExemptNumberPattern** cmdlet lets you modify one or more parameters for a given number pattern identity.</span></span> <span data-ttu-id="6f5a3-172">Neste exemplo, o **parâmetro Identity** é necessário.</span><span class="sxs-lookup"><span data-stu-id="6f5a3-172">In this example, the **Identity** parameter is required.</span></span>
 
```powershell
Set-CsInboundExemptNumberPattern -Identity <String> -Enabled <bool> -Description <string> -Pattern <string> 
```

```powershell
Set-CsInboundExemptNumberPattern -Identity "AllowContoso1" -Enabled $False
```

#### <a name="remove-a-number-exception"></a><span data-ttu-id="6f5a3-173">Remover uma exceção de número</span><span class="sxs-lookup"><span data-stu-id="6f5a3-173">Remove a number exception</span></span>

<span data-ttu-id="6f5a3-174">O cmdlet **Remove-CsInboundExemptNumberPattern** removerá o padrão de número determinado da lista de locatários.</span><span class="sxs-lookup"><span data-stu-id="6f5a3-174">The **Remove-CsInboundExemptNumberPattern** cmdlet will remove the given number pattern from the tenant list.</span></span> <span data-ttu-id="6f5a3-175">Neste exemplo, o **parâmetro Identity** é necessário.</span><span class="sxs-lookup"><span data-stu-id="6f5a3-175">In this example, the **Identity** parameter is required.</span></span> 

<span data-ttu-id="6f5a3-176">Se a identidade não for conhecida, use o cmdlet **Get-CsInboundExemptNumberPattern** para primeiro localizar o padrão adequado e observar a identidade.</span><span class="sxs-lookup"><span data-stu-id="6f5a3-176">If the identity isn't known, use the **Get-CsInboundExemptNumberPattern** cmdlet to first locate the proper pattern and note the identity.</span></span> <span data-ttu-id="6f5a3-177">Em seguida, execute o cmdlet **Remove-CsInboundExemptNumberPattern** e passe o valor de identidade apropriado.</span><span class="sxs-lookup"><span data-stu-id="6f5a3-177">Then, run the **Remove-CsInboundExemptNumberPattern** cmdlet and pass the appropriate identity value.</span></span><span data-ttu-id="6f5a3-178">Permitir tempo para replicação antes de testar e validar.</span><span class="sxs-lookup"><span data-stu-id="6f5a3-178"> Allow time for replication before you test and validate.</span></span>  

```powershell
Remove-CsInboundExemptNumberPattern -Identity <String>
```

```powershell
Remove-CsInboundExemptNumberPattern -Identity "AllowContoso1"
```

## <a name="test-whether-a-number-is-blocked"></a><span data-ttu-id="6f5a3-179">Testar se um número está bloqueado</span><span class="sxs-lookup"><span data-stu-id="6f5a3-179">Test whether a number is blocked</span></span>

<span data-ttu-id="6f5a3-180">Use o cmdlet **Test-CsInboundBlockedNumberPattern** para verificar se um número está bloqueado no locatário.</span><span class="sxs-lookup"><span data-stu-id="6f5a3-180">Use the **Test-CsInboundBlockedNumberPattern** cmdlet to verify whether a number is blocked in the tenant.</span></span>
 
<span data-ttu-id="6f5a3-181">O **parâmetro PhoneNumber** é necessário e deve ser uma cadeia de caracteres numérica sem caracteres adicionais, como +, - ou ().</span><span class="sxs-lookup"><span data-stu-id="6f5a3-181">The **PhoneNumber** parameter is required, and should be a numeric string without any additional characters, such as +, - or ().</span></span> <span data-ttu-id="6f5a3-182">O parâmetro **IsNumberBlocked** resultante retornará um valor True se o número for bloqueado no locatário; o parâmetro retorna False se não estiver bloqueado.</span><span class="sxs-lookup"><span data-stu-id="6f5a3-182">The resulting **IsNumberBlocked** parameter returns a value of True if the number is blocked in the tenant; the parameter returns False if it's not blocked.</span></span>

```powershell
Test-CsInboundBlockedNumberPattern –Tenant <GUID> -PhoneNumber <String>
```

### <a name="examples"></a><span data-ttu-id="6f5a3-183">Exemplos</span><span class="sxs-lookup"><span data-stu-id="6f5a3-183">Examples</span></span>

<span data-ttu-id="6f5a3-184">Nesses exemplos, você pode ver que o número de telefone 1 (312) 555-8884 está bloqueado, pois ele deve estar no intervalo bloqueado acima, enquanto o número de telefone 1 (312) 555-8883 tem permissão para chamar, pois deve ser baseado na isenção criada acima.</span><span class="sxs-lookup"><span data-stu-id="6f5a3-184">In these examples you can see that the phone number 1 (312) 555-8884 is blocked as it should be due to it being in the blocked range above, while the phone number 1 (312) 555-8883 is allowed to call as it should be based on the exemption created above.</span></span>

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

## <a name="using-regex"></a><span data-ttu-id="6f5a3-185">Usando Regex</span><span class="sxs-lookup"><span data-stu-id="6f5a3-185">Using Regex</span></span>

<span data-ttu-id="6f5a3-186">A correspondência de padrão para os chamadores de bloqueio é feita usando Regex.</span><span class="sxs-lookup"><span data-stu-id="6f5a3-186">The pattern matching for blocking callers is done by using Regex.</span></span> <span data-ttu-id="6f5a3-187">Várias ferramentas estão disponíveis online para ajudar a validar uma combinação de padrão regex.</span><span class="sxs-lookup"><span data-stu-id="6f5a3-187">Multiple tools are available online to help validate a Regex pattern match.</span></span> <span data-ttu-id="6f5a3-188">Se você não estiver familiarizado com os padrões Regex, recomendamos que você leve algum tempo para se familiarizar com os conceitos básicos.</span><span class="sxs-lookup"><span data-stu-id="6f5a3-188">If you aren't familiar with Regex patterns, we recommend that you take some time to familiarize yourself with the basics.</span></span> <span data-ttu-id="6f5a3-189">Para garantir que você receba os resultados esperados, use uma ferramenta para validar as correspondeções de padrão antes de adicionar novas combinações de número bloqueado ao seu locatário.</span><span class="sxs-lookup"><span data-stu-id="6f5a3-189">To make sure you get expected results, use a tool for validating pattern matches before you add new blocked number matches to your tenant.</span></span>