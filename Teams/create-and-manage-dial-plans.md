---
title: Criar e gerenciar planos de discagem
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.reviewer: mikedav, roykuntz, jastark
ms.topic: article
ms.assetid: 7af17c94-5f8f-4452-ae1d-01f495b4dc94
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Calling Plans
- seo-marvel-apr2020
description: Saiba como usar o centro de administração Microsoft Teams ou Windows PowerShell para criar e gerenciar planos de discagem (planos de discagem de chamada PSTN).
ms.openlocfilehash: 59867dfe49436635f690ff9f5d56a2be36e553ec
ms.sourcegitcommit: 127f9fdf05b93ee3af4244224e1c32a45d73d3ee
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/21/2021
ms.locfileid: "53046228"
---
# <a name="create-and-manage-dial-plans"></a><span data-ttu-id="2f589-103">Criar e gerenciar planos de discagem</span><span class="sxs-lookup"><span data-stu-id="2f589-103">Create and manage dial plans</span></span>

<span data-ttu-id="2f589-104">Depois de planejar os planos de discagem para sua organização e descobrir todas as regras de normalização que precisam ser criadas para roteamento de chamadas, você estará pronto para criar os planos de discagem.</span><span class="sxs-lookup"><span data-stu-id="2f589-104">After you plan the dial plans for your organization and figured out all the normalization rules that need to be created for call routing, you're ready to create the dial plans.</span></span> <span data-ttu-id="2f589-105">Com uma conta de administrador com uma licença de Teams válida, você pode usar o centro de administração Microsoft Teams ou Windows PowerShell para criar e gerenciar planos de discagem.</span><span class="sxs-lookup"><span data-stu-id="2f589-105">With an administrator account that has a valid Teams license, you can use the Microsoft Teams admin center or Windows PowerShell to create and manage dial plans.</span></span>  

## <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="2f589-106">Usando o centro de administração do Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="2f589-106">Using the Microsoft Teams admin center</span></span>

### <a name="create-a-dial-plan"></a><span data-ttu-id="2f589-107">Criar um plano de discagem</span><span class="sxs-lookup"><span data-stu-id="2f589-107">Create a dial plan</span></span>

1. <span data-ttu-id="2f589-108">Na navegação à esquerda do centro de administração Microsoft Teams, vá para **Plano de**  >  **Discagem de Voz**.</span><span class="sxs-lookup"><span data-stu-id="2f589-108">In the left navigation of the Microsoft Teams admin center, go to **Voice** > **Dial plan**.</span></span>
2. <span data-ttu-id="2f589-109">Clique **em Adicionar** e insira um nome e uma descrição para o plano de discagem.</span><span class="sxs-lookup"><span data-stu-id="2f589-109">Click **Add**, and then enter a name and description for the dial plan.</span></span>
    <span data-ttu-id="2f589-110">![Captura de tela mostrando a página Adicionar para criar um plano de discagem](media/create-dial-plan.png)</span><span class="sxs-lookup"><span data-stu-id="2f589-110">![Screenshot showing the Add page for creating a dial plan](media/create-dial-plan.png)</span></span>
3. <span data-ttu-id="2f589-111">Em **Detalhes do plano de** discagem, especifique um prefixo de discagem externa se os usuários precisarem discar um ou mais dígitos principais adicionais (por exemplo, 9) para obter uma linha externa.</span><span class="sxs-lookup"><span data-stu-id="2f589-111">Under **Dial plan details**, specify an external dialing prefix if users need to dial one or more additional leading digits (for example, 9) to get an external line.</span></span> <span data-ttu-id="2f589-112">Para fazer isso:</span><span class="sxs-lookup"><span data-stu-id="2f589-112">To do this:</span></span>
    1. <span data-ttu-id="2f589-113">Na caixa **Prefixo de discagem externa,** insira um prefixo de discagem externa.</span><span class="sxs-lookup"><span data-stu-id="2f589-113">In the **External dialing prefix** box, enter an external dialing prefix.</span></span> <span data-ttu-id="2f589-114">O prefixo pode ter até quatro caracteres (#,\*e 0-9).</span><span class="sxs-lookup"><span data-stu-id="2f589-114">The prefix can be up to four characters (#,\*, and 0-9).</span></span>
    2. <span data-ttu-id="2f589-115">Ativar **a discagem otimizada do dispositivo**.</span><span class="sxs-lookup"><span data-stu-id="2f589-115">Turn on **Optimized device dialing**.</span></span> <span data-ttu-id="2f589-116">Se você especificar um prefixo de discagem externa, também deverá ativar essa configuração para aplicar o prefixo para que as chamadas possam ser feitas fora da sua organização.</span><span class="sxs-lookup"><span data-stu-id="2f589-116">If you specify an external dialing prefix, you must also turn on this setting to apply the prefix so calls can be made outside your organization.</span></span>
4. <span data-ttu-id="2f589-117">Em **Regras de Normalização,** configure e associe uma ou mais regras [de normalização](what-are-dial-plans.md#normalization-rules) para o plano de discagem.</span><span class="sxs-lookup"><span data-stu-id="2f589-117">Under **Normalization rules**, configure and associate one or more [normalization rules](what-are-dial-plans.md#normalization-rules) for the dial plan.</span></span> <span data-ttu-id="2f589-118">Cada plano de discagem deve ter pelo menos uma regra de normalização associada a ele.</span><span class="sxs-lookup"><span data-stu-id="2f589-118">Each dial plan must have at least one normalization rule associated with it.</span></span>  <span data-ttu-id="2f589-119">Para fazer isso, faça um ou mais dos seguintes:</span><span class="sxs-lookup"><span data-stu-id="2f589-119">To do this, do one or more of the following:</span></span>
    - <span data-ttu-id="2f589-120">Para criar uma nova regra de normalização e associá-la ao plano de discagem, clique em **Adicionar** e defina a regra.</span><span class="sxs-lookup"><span data-stu-id="2f589-120">To create a new normalization rule and associate it with the dial plan, click **Add**, and then define the rule.</span></span>
    - <span data-ttu-id="2f589-121">Para editar uma regra de normalização que já está associada ao plano de discagem, selecione a regra clicando à esquerda do nome da regra e clique em **Editar**.</span><span class="sxs-lookup"><span data-stu-id="2f589-121">To edit a normalization rule that's already associated with the dial plan, select the rule by clicking to the left of the rule name, and then click **Edit**.</span></span> <span data-ttu-id="2f589-122">Faça as alterações que você deseja e clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="2f589-122">Make the changes you want, and then click **Save**.</span></span>
    - <span data-ttu-id="2f589-123">Para remover uma regra de normalização do plano de discagem, selecione a regra clicando à esquerda do nome da regra e clique em **Remover**.</span><span class="sxs-lookup"><span data-stu-id="2f589-123">To remove a normalization rule from the dial plan, select the rule by clicking to the left of the rule name, and then click **Remove**.</span></span>
5. <span data-ttu-id="2f589-124">Organize as regras de normalização na ordem que você deseja.</span><span class="sxs-lookup"><span data-stu-id="2f589-124">Arrange the normalization rules in the order that you want.</span></span> <span data-ttu-id="2f589-125">Clique **em Mover para cima** ou Mover **para** baixo para alterar a posição das regras na lista.</span><span class="sxs-lookup"><span data-stu-id="2f589-125">Click **Move up** or **Move down** to change the position of rules in the list.</span></span>

    > [!NOTE]
    > <span data-ttu-id="2f589-126">Teams percorre a lista de regras de normalização da parte superior para baixo e usa a primeira regra que corresponde ao número discado.</span><span class="sxs-lookup"><span data-stu-id="2f589-126">Teams traverses the list of normalization rules from the top down and uses the first rule that matches the dialed number.</span></span> <span data-ttu-id="2f589-127">Se você configurar um plano de discagem para que um número discado possa corresponder a mais de uma regra de normalização, certifique-se de que as regras mais restritivas sejam ordenadas acima das menos restritivas.</span><span class="sxs-lookup"><span data-stu-id="2f589-127">If you set up a dial plan so that a dialed number can match more than one normalization rule, make sure the more restrictive rules are sorted above the less restrictive ones.</span></span> <span data-ttu-id="2f589-128">Se você configurar um plano de discagem que normalize um número discado sem um "+", o serviço de chamada tentará normalizar o número novamente usando regras de plano de discagem regional e locatário.</span><span class="sxs-lookup"><span data-stu-id="2f589-128">If you set up a dial plan that normalizes a dialed number without a "+", the calling service will attempt to normalize the number again using Tenant and regional dial plan rules.</span></span> <span data-ttu-id="2f589-129">Para evitar a dupla normalização, é recomendável que todas as regras de normalização resultem em números começando com um "+".</span><span class="sxs-lookup"><span data-stu-id="2f589-129">To avoid double normalization, it's recommended that all normalization rules result in numbers starting with a "+".</span></span> <span data-ttu-id="2f589-130">Os clientes de Roteamento Direto [podem](direct-routing-translate-numbers.md) usar regras de conversão de tronco para remover o "+" se necessário.</span><span class="sxs-lookup"><span data-stu-id="2f589-130">Direct Routing customers can use [trunk translation](direct-routing-translate-numbers.md) rules to remove the "+" if required.</span></span> 

6. <span data-ttu-id="2f589-131">Clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="2f589-131">Click **Save**.</span></span>
7. <span data-ttu-id="2f589-132">Se você quiser testar o plano de discagem, em **Teste** plano de discagem , insira um número de telefone e clique em **Testar**.</span><span class="sxs-lookup"><span data-stu-id="2f589-132">If you want to test the dial plan, under **Test dial plan**, enter a phone number, and then click **Test**.</span></span>

### <a name="edit-a-dial-plan"></a><span data-ttu-id="2f589-133">Editar um plano de discagem</span><span class="sxs-lookup"><span data-stu-id="2f589-133">Edit a dial plan</span></span>

1. <span data-ttu-id="2f589-134">Na navegação à esquerda do centro de administração Microsoft Teams, vá para **Plano de**  >  **Discagem de Voz**.</span><span class="sxs-lookup"><span data-stu-id="2f589-134">In the left navigation of the Microsoft Teams admin center, go to **Voice** > **Dial plan**.</span></span>
2. <span data-ttu-id="2f589-135">Selecione o plano de discagem clicando à esquerda do nome do plano de discagem e clique em **Editar**.</span><span class="sxs-lookup"><span data-stu-id="2f589-135">Select the dial plan by clicking to the left of the dial plan name, and then click **Edit**.</span></span>
3. <span data-ttu-id="2f589-136">Faça as alterações que você deseja e clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="2f589-136">Make the changes that you want, and then click **Save**.</span></span>

### <a name="assign-a-dial-plan-to-users"></a><span data-ttu-id="2f589-137">Atribuir um plano de discagem aos usuários</span><span class="sxs-lookup"><span data-stu-id="2f589-137">Assign a dial plan to users</span></span>

<span data-ttu-id="2f589-138">Você atribui um plano de discagem da mesma maneira que atribui políticas.</span><span class="sxs-lookup"><span data-stu-id="2f589-138">You assign a dial plan in the same way you assign policies.</span></span> [!INCLUDE [assign-policy](includes/assign-policy.md)]

## <a name="using-powershell"></a><span data-ttu-id="2f589-139">Usando o Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="2f589-139">Using PowerShell</span></span>
  
### <a name="start-powershell"></a><span data-ttu-id="2f589-140">Iniciar o PowerShell</span><span class="sxs-lookup"><span data-stu-id="2f589-140">Start PowerShell</span></span>
- <span data-ttu-id="2f589-141">Abra um prompt Windows PowerShell de comando e execute os seguintes comandos:</span><span class="sxs-lookup"><span data-stu-id="2f589-141">Open a Windows PowerShell command prompt and run the following commands:</span></span>

```powershell
  # When using Teams PowerShell Module

   Import-Module MicrosoftTeams
   $credential = Get-Credential
   Connect-MicrosoftTeams -Credential $credential
```
  
### <a name="create-and-manage-your-dial-plans"></a><span data-ttu-id="2f589-142">Criar e gerenciar seus planos de discagem</span><span class="sxs-lookup"><span data-stu-id="2f589-142">Create and manage your dial plans</span></span>

<span data-ttu-id="2f589-143">Você pode usar um único cmdlet ou um script do PowerShell para criar e gerenciar planos de discagem de locatários.</span><span class="sxs-lookup"><span data-stu-id="2f589-143">You can either use a single cmdlet or a PowerShell script to create and manage tenant dial plans.</span></span>
  
#### <a name="using-single-cmdlets"></a><span data-ttu-id="2f589-144">Usando cmdlets individuais</span><span class="sxs-lookup"><span data-stu-id="2f589-144">Using single cmdlets</span></span>

- <span data-ttu-id="2f589-145">Para criar um novo plano de discagem, execute:</span><span class="sxs-lookup"><span data-stu-id="2f589-145">To create a new dial plan, run:</span></span>
    
  ```PowerShell
  New-CsTenantDialPlan -Identity RedmondDialPlan -Description "Dial Plan for Redmond" -NormalizationRules <pslistmodifier> -ExternalAccessPrefix 9 -SimpleName "Dial-Plan-for-Redmond"
  ```

    <span data-ttu-id="2f589-146">Para outros exemplos e parâmetros, consulte [New-CsTenantDialPlan](/powershell/module/skype/new-cstenantdialplan).</span><span class="sxs-lookup"><span data-stu-id="2f589-146">For other examples and parameters, see [New-CsTenantDialPlan](/powershell/module/skype/new-cstenantdialplan).</span></span>
    
- <span data-ttu-id="2f589-147">Para editar as configurações de um plano de discagem existente, execute:</span><span class="sxs-lookup"><span data-stu-id="2f589-147">To edit the settings of an existing dial plan, run:</span></span>
    
  ```PowerShell
  Set-CsTenantDialPlan -Identity RedmondDialPlan  -NormalizationRules <pslistmodifier> -ExternalAccessPrefix 9
    -SimpleName "Dial-Plan-for-Redmond"
  ```

    <span data-ttu-id="2f589-148">Para outros exemplos e parâmetros, consulte [Set-CsTenantDialPlan](/powershell/module/skype/set-cstenantdialplan).</span><span class="sxs-lookup"><span data-stu-id="2f589-148">For other examples and parameters, see [Set-CsTenantDialPlan](/powershell/module/skype/set-cstenantdialplan).</span></span>
    
- <span data-ttu-id="2f589-149">Para adicionar usuários a um plano de discagem, execute:</span><span class="sxs-lookup"><span data-stu-id="2f589-149">To add users to a dial plan, run:</span></span>
    
  ```PowerShell
  Grant-CsTenantDialPlan -Identity amos.marble@contoso.com -PolicyName RedmondDialPlan
  ```

    <span data-ttu-id="2f589-150">Para outros exemplos e parâmetros, consulte [Grant-CsTenantDialPlan](/powershell/module/skype/grant-cstenantdialplan).</span><span class="sxs-lookup"><span data-stu-id="2f589-150">For other examples and parameters, see [Grant-CsTenantDialPlan](/powershell/module/skype/grant-cstenantdialplan).</span></span>
    
- <span data-ttu-id="2f589-151">Para exibir as configurações em um plano de discagem, execute:</span><span class="sxs-lookup"><span data-stu-id="2f589-151">To view the settings on a dial plan, run:</span></span>
    
  ```PowerShell
  Get-CsTenantDialPlan -Identity RedmondDialPlan
  ```

    <span data-ttu-id="2f589-152">Para outros exemplos e parâmetros, consulte [Get-CsTenantDialPlan](/powershell/module/skype/get-cstenantdialplan?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="2f589-152">For other examples and parameters, see [Get-CsTenantDialPlan](/powershell/module/skype/get-cstenantdialplan?view=skype-ps).</span></span>
    
- <span data-ttu-id="2f589-153">Para excluir um plano de discagem, execute:</span><span class="sxs-lookup"><span data-stu-id="2f589-153">To delete a dial plan, run:</span></span>
    
  ```PowerShell
  Remove-CsTenantDialPlan -Identity RedmondDialPlan -force
  ```

    <span data-ttu-id="2f589-154">Para outros exemplos e parâmetros, consulte [Remove-CsTenantDialPlan](/powershell/module/skype/remove-cstenantdialplan?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="2f589-154">For other examples and parameters, see [Remove-CsTenantDialPlan](/powershell/module/skype/remove-cstenantdialplan?view=skype-ps).</span></span>
    
- <span data-ttu-id="2f589-155">Para ver as configurações do plano de discagem efetivo, execute:</span><span class="sxs-lookup"><span data-stu-id="2f589-155">To see the settings of the effective dial plan, run:</span></span>
    
  ```PowerShell
  Get-CsEffectiveTenantDialPlan -Identity amos.marble@contoso.com
  ```

    <span data-ttu-id="2f589-156">Para outros exemplos e parâmetros, consulte [Get-CsEffectiveTenantDialPlan](/powershell/module/skype/get-cseffectivetenantdialplan).</span><span class="sxs-lookup"><span data-stu-id="2f589-156">For other examples and parameters, see [Get-CsEffectiveTenantDialPlan](/powershell/module/skype/get-cseffectivetenantdialplan).</span></span>
    
- <span data-ttu-id="2f589-157">Para testar as configurações efetivas de um plano de discagem, execute:</span><span class="sxs-lookup"><span data-stu-id="2f589-157">To test the effective settings of a dial plan, run:</span></span>
    
  ```PowerShell
  Test-CsEffectiveTenantDialPlan -DialedNumber 14255550199 -Identity amos.marble@contoso.com
  ```

    <span data-ttu-id="2f589-158">Para outros exemplos e parâmetros, consulte [Test-CsEffectiveTenantDialPlan](/powershell/module/skype/test-cseffectivetenantdialplan?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="2f589-158">For other examples and parameters, see [Test-CsEffectiveTenantDialPlan](/powershell/module/skype/test-cseffectivetenantdialplan?view=skype-ps).</span></span>
    
#### <a name="using-a-powershell-script"></a><span data-ttu-id="2f589-159">Usando um script do PowerShell</span><span class="sxs-lookup"><span data-stu-id="2f589-159">Using a PowerShell script</span></span>

<span data-ttu-id="2f589-160">Execute isso para excluir uma regra de normalização associada a um plano de discagem de locatário sem precisar excluir primeiro o plano de discagem do locatário:</span><span class="sxs-lookup"><span data-stu-id="2f589-160">Run this to delete a normalization rule that is associated with a tenant dial plan without needing to delete the tenant dial plan first:</span></span>
```PowerShell
$b1=New-CsVoiceNormalizationRule -Identity Global/NR4 -InMemory
Set-CsTenantDialPlan -Identity RedmondDialPlan -NormalizationRules @{add=$b1}
(Get-CsTenantDialPlan -Identity RedmondDialPlan).NormalizationRules
$b2=New-CsVoiceNormalizationRule -Identity Global/NR4 -InMemory
Set-CsTenantDialPlan -Identity RedmondDialPlan -NormalizationRules @{remove=$b2}
```
<span data-ttu-id="2f589-161">Execute isso para adicionar a seguinte regra de normalização ao plano de discagem de locatário existente chamado RedmondDialPlan.</span><span class="sxs-lookup"><span data-stu-id="2f589-161">Run this to add the following normalization rule to the existing tenant dial plan named RedmondDialPlan.</span></span>
```PowerShell
$nr1=New-CsVoiceNormalizationRule -Parent Global -Description 'Organization extension dialing' -Pattern '^(\\d{3})$' -Translation '+14255551$1' -Name NR1 -IsInternalExtension $false -InMemory
Set-CsTenantDialPlan -Identity RedmondDialPlan -NormalizationRules @{add=$nr1}
```
<span data-ttu-id="2f589-162">Execute isso para remover a seguinte regra de normalização do plano de discagem de locatário existente chamado RedmondDialPlan.</span><span class="sxs-lookup"><span data-stu-id="2f589-162">Run this to remove the following normalization rule from the existing tenant dial plan named RedmondDialPlan.</span></span>
```PowerShell
$nr1=New-CsVoiceNormalizationRule -Parent Global/NR1 -InMemory
Set-CsTenantDialPlan -Identity RedmondDialPlan -NormalizationRules @{remove=$nr1}
```

<span data-ttu-id="2f589-163">Execute o seguinte quando quiser examinar também as regras de normalização existentes, determinar qual delas você deseja excluir e, em seguida, usar seu índice para removê-la.</span><span class="sxs-lookup"><span data-stu-id="2f589-163">Run the following when you want to also examine the existing normalization rules, determine which one you want to delete, and then use its index to remove it.</span></span> <span data-ttu-id="2f589-164">A matriz de regras de normalização começa com o índice 0.</span><span class="sxs-lookup"><span data-stu-id="2f589-164">The array of normalization rules starts with index 0.</span></span> <span data-ttu-id="2f589-165">Queremos remover a regra de normalização de 3 dígitos, portanto, esse é o índice 1.</span><span class="sxs-lookup"><span data-stu-id="2f589-165">We would like to remove the 3-digit normalization rule, so that is index 1.</span></span>
  
```PowerShell
Get-CsTenantDialPlan RedmondDialPlan).NormalizationRules
Description         : 4-digit
Pattern             : ^(\\d{4})$
Translation         : +1426666$1
Name                : NR2
IsInternalExtension : False

Description         : 3-digit
Pattern             : ^(\\d{3})$
Translation         : +14255551$1
Name                : NR12
IsInternalExtension : False

$nr1=(Get-CsTenantDialPlan RedmondDialPlan).NormalizationRules[1]
Set-CsTenantDialPlan -Identity RedmondDialPlan -NormalizationRules @{remove=$nr1}
```

<span data-ttu-id="2f589-166">Execute isso para encontrar todos os usuários que foram concedidos ao plano de discagem de locatário RedmondDialPlan.</span><span class="sxs-lookup"><span data-stu-id="2f589-166">Run this to find all users who have been granted the RedmondDialPlan tenant dial plan.</span></span>
  
```PowerShell
Get-CsOnlineUser | Where-Object {$_.TenantDialPlan -eq "RedmondDialPlan"}
```

<span data-ttu-id="2f589-167">Execute isso para remover qualquer TenantDialPlan atribuído de todos os usuários que tenham um HostingProvider de sipfed.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="2f589-167">Run this to remove any assigned TenantDialPlan from all users who have a HostingProvider of sipfed.online.lync.com.</span></span>
```PowerShell
Get-CsOnlineUser -Filter {HostingProvider -eq "sipfed.online.lync.com"} | Grant-CsTenantDialPlan -policyname $null
```

<span data-ttu-id="2f589-168">Execute-os para adicionar o plano de discagem local existente chamado OPDP1 como um plano de discagem de locatário para sua organização.</span><span class="sxs-lookup"><span data-stu-id="2f589-168">Run these to add the existing on-premises dial plan named OPDP1 as a tenant dial plan for your organization.</span></span> <span data-ttu-id="2f589-169">Primeiro, você precisa salvar o plano de discagem local em um arquivo .xml e usá-lo para criar o novo plano de discagem de locatário.</span><span class="sxs-lookup"><span data-stu-id="2f589-169">You need to first save the on-premises dial plan to an .xml file, and then use it to create the new tenant dial plan.</span></span>
  
<span data-ttu-id="2f589-170">Execute isso para salvar o plano de discagem local no arquivo .xml local.</span><span class="sxs-lookup"><span data-stu-id="2f589-170">Run this to save the on-premises dial plan to the .xml file.</span></span>
  
```PowerShell
$DPName = "OPDP1"
$DPFileName = "dialplan.xml"
Get-CsDialplan $DPName | Export-Clixml $DPFileName
```

<span data-ttu-id="2f589-171">Execute isso para criar o novo plano de discagem de locatário.</span><span class="sxs-lookup"><span data-stu-id="2f589-171">Run this to create the new tenant dial plan.</span></span>
  
```PowerShell
$DPFileName = "dialplan.xml"
$dp = Import-Clixml $DPFileName
$NormRules = @()
ForEach($nr in $dp.NormalizationRules)
{
 $id1 = "Global/" + $nr.Name
 $nr2 = New-CsVoiceNormalizationRule -Identity $id1 -Description $nr.Description -Pattern $nr.Pattern -Translation $nr.Translation -IsInternalExtension $nr.IsInternalExtension -InMemory
 $NormRules += $nr2
}
New-CsTenantDialPlan -Identity $dp.SimpleName -ExternalAccessPrefix $dp.ExternalAccessPrefix -Description $dp.Description -OptimizeDeviceDialing $dp.OptimizeDeviceDialing -SimpleName $dp.SimpleName -NormalizationRules $NormRules
```
    
## <a name="related-topics"></a><span data-ttu-id="2f589-172">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="2f589-172">Related topics</span></span>

- [<span data-ttu-id="2f589-173">O que são planos de discagem?</span><span class="sxs-lookup"><span data-stu-id="2f589-173">What are dial plans?</span></span>](what-are-dial-plans.md)
- [<span data-ttu-id="2f589-174">Perguntas comuns sobre a transferência de números de telefone</span><span class="sxs-lookup"><span data-stu-id="2f589-174">Transferring phone numbers common questions</span></span>](./phone-number-calling-plans/port-order-overview.md)
- [<span data-ttu-id="2f589-175">Diferentes tipos de números de telefone usados para Planos de Chamadas</span><span class="sxs-lookup"><span data-stu-id="2f589-175">Different kinds of phone numbers used for Calling Plans</span></span>](different-kinds-of-phone-numbers-used-for-calling-plans.md)
- [<span data-ttu-id="2f589-176">Gerenciar os números de telefone de sua organização</span><span class="sxs-lookup"><span data-stu-id="2f589-176">Manage phone numbers for your organization</span></span>](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)
- [<span data-ttu-id="2f589-177">Termos e condições das Chamadas de Emergência</span><span class="sxs-lookup"><span data-stu-id="2f589-177">Emergency calling terms and conditions</span></span>](emergency-calling-terms-and-conditions.md)
- <span data-ttu-id="2f589-178">[Rótulo de aviso de isenção de responsabilidade de chamada de emergência](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)</span><span class="sxs-lookup"><span data-stu-id="2f589-178">[Emergency calling disclaimer label](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)</span></span>
- [<span data-ttu-id="2f589-179">Visão Geral do PowerShell do Teams</span><span class="sxs-lookup"><span data-stu-id="2f589-179">Teams PowerShell overview</span></span>](teams-powershell-overview.md)
