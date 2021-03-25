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
description: Saiba como usar o Centro de administração do Microsoft Teams ou Windows PowerShell para criar e gerenciar planos de discagem (planos de discagem de chamada PSTN).
ms.openlocfilehash: 0b2c8c64d1e4e01843c6565d43a07e0ebdb24d71
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51120803"
---
# <a name="create-and-manage-dial-plans"></a><span data-ttu-id="7a174-103">Criar e gerenciar planos de discagem</span><span class="sxs-lookup"><span data-stu-id="7a174-103">Create and manage dial plans</span></span>

<span data-ttu-id="7a174-104">Depois de planejar os planos de discagem para sua organização e descobrir todas as regras de normalização que precisam ser criadas para roteamento de chamadas, você estará pronto para criar os planos de discagem.</span><span class="sxs-lookup"><span data-stu-id="7a174-104">After you plan the dial plans for your organization and figured out all the normalization rules that need to be created for call routing, you're ready to create the dial plans.</span></span> <span data-ttu-id="7a174-105">Você pode usar o centro de administração do Microsoft Teams ou Windows PowerShell para criar e gerenciar planos de discagem.</span><span class="sxs-lookup"><span data-stu-id="7a174-105">You can use the Microsoft Teams admin center or Windows PowerShell to create and manage dial plans.</span></span>  

## <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="7a174-106">Usando o centro de administração do Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="7a174-106">Using the Microsoft Teams admin center</span></span>

### <a name="create-a-dial-plan"></a><span data-ttu-id="7a174-107">Criar um plano de discagem</span><span class="sxs-lookup"><span data-stu-id="7a174-107">Create a dial plan</span></span>

1. <span data-ttu-id="7a174-108">Na navegação à esquerda do Centro de administração do Microsoft Teams, vá para **Plano de**  >  **Discagem de Voz**.</span><span class="sxs-lookup"><span data-stu-id="7a174-108">In the left navigation of the Microsoft Teams admin center, go to **Voice** > **Dial plan**.</span></span>
2. <span data-ttu-id="7a174-109">Clique **em Adicionar** e insira um nome e uma descrição para o plano de discagem.</span><span class="sxs-lookup"><span data-stu-id="7a174-109">Click **Add**, and then enter a name and description for the dial plan.</span></span>
    <span data-ttu-id="7a174-110">![Captura de tela mostrando a página Adicionar para criar um plano de discagem](media/create-dial-plan.png)</span><span class="sxs-lookup"><span data-stu-id="7a174-110">![Screenshot showing the Add page for creating a dial plan](media/create-dial-plan.png)</span></span>
3. <span data-ttu-id="7a174-111">Em **Detalhes do plano de** discagem, especifique um prefixo de discagem externa se os usuários precisarem discar um ou mais dígitos principais adicionais (por exemplo, 9) para obter uma linha externa.</span><span class="sxs-lookup"><span data-stu-id="7a174-111">Under **Dial plan details**, specify an external dialing prefix if users need to dial one or more additional leading digits (for example, 9) to get an external line.</span></span> <span data-ttu-id="7a174-112">Para fazer isso:</span><span class="sxs-lookup"><span data-stu-id="7a174-112">To do this:</span></span>
    1. <span data-ttu-id="7a174-113">Na caixa **Prefixo de discagem externa,** insira um prefixo de discagem externa.</span><span class="sxs-lookup"><span data-stu-id="7a174-113">In the **External dialing prefix** box, enter an external dialing prefix.</span></span> <span data-ttu-id="7a174-114">O prefixo pode ter até quatro caracteres (#,\*e 0-9).</span><span class="sxs-lookup"><span data-stu-id="7a174-114">The prefix can be up to four characters (#,\*, and 0-9).</span></span>
    2. <span data-ttu-id="7a174-115">Ativar **a discagem otimizada do dispositivo**.</span><span class="sxs-lookup"><span data-stu-id="7a174-115">Turn on **Optimized device dialing**.</span></span> <span data-ttu-id="7a174-116">Se você especificar um prefixo de discagem externa, também deverá ativar essa configuração para aplicar o prefixo para que as chamadas possam ser feitas fora da sua organização.</span><span class="sxs-lookup"><span data-stu-id="7a174-116">If you specify an external dialing prefix, you must also turn on this setting to apply the prefix so calls can be made outside your organization.</span></span>
4. <span data-ttu-id="7a174-117">Em **Regras de Normalização,** configure e associe uma ou mais regras [de normalização](what-are-dial-plans.md#normalization-rules) para o plano de discagem.</span><span class="sxs-lookup"><span data-stu-id="7a174-117">Under **Normalization rules**, configure and associate one or more [normalization rules](what-are-dial-plans.md#normalization-rules) for the dial plan.</span></span> <span data-ttu-id="7a174-118">Cada plano de discagem deve ter pelo menos uma regra de normalização associada a ele.</span><span class="sxs-lookup"><span data-stu-id="7a174-118">Each dial plan must have at least one normalization rule associated with it.</span></span>  <span data-ttu-id="7a174-119">Para fazer isso, faça um ou mais dos seguintes:</span><span class="sxs-lookup"><span data-stu-id="7a174-119">To do this, do one or more of the following:</span></span>
    - <span data-ttu-id="7a174-120">Para criar uma nova regra de normalização e associá-la ao plano de discagem, clique em **Adicionar** e defina a regra.</span><span class="sxs-lookup"><span data-stu-id="7a174-120">To create a new normalization rule and associate it with the dial plan, click **Add**, and then define the rule.</span></span>
    - <span data-ttu-id="7a174-121">Para editar uma regra de normalização que já está associada ao plano de discagem, selecione a regra clicando à esquerda do nome da regra e clique em **Editar**.</span><span class="sxs-lookup"><span data-stu-id="7a174-121">To edit a normalization rule that's already associated with the dial plan, select the rule by clicking to the left of the rule name, and then click **Edit**.</span></span> <span data-ttu-id="7a174-122">Faça as alterações que você deseja e clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="7a174-122">Make the changes you want, and then click **Save**.</span></span>
    - <span data-ttu-id="7a174-123">Para remover uma regra de normalização do plano de discagem, selecione a regra clicando à esquerda do nome da regra e clique em **Remover**.</span><span class="sxs-lookup"><span data-stu-id="7a174-123">To remove a normalization rule from the dial plan, select the rule by clicking to the left of the rule name, and then click **Remove**.</span></span>
5. <span data-ttu-id="7a174-124">Organize as regras de normalização na ordem que você deseja.</span><span class="sxs-lookup"><span data-stu-id="7a174-124">Arrange the normalization rules in the order that you want.</span></span> <span data-ttu-id="7a174-125">Clique **em Mover para cima** ou Mover **para** baixo para alterar a posição das regras na lista.</span><span class="sxs-lookup"><span data-stu-id="7a174-125">Click **Move up** or **Move down** to change the position of rules in the list.</span></span>

    > [!NOTE]
    > <span data-ttu-id="7a174-126">O Teams percorre a lista de regras de normalização de cima para baixo e usa a primeira regra que corresponde ao número discado.</span><span class="sxs-lookup"><span data-stu-id="7a174-126">Teams traverses the list of normalization rules from the top down and uses the first rule that matches the dialed number.</span></span> <span data-ttu-id="7a174-127">Se você configurar um plano de discagem para que um número discado possa corresponder a mais de uma regra de normalização, certifique-se de que as regras mais restritivas sejam ordenadas acima das menos restritivas.</span><span class="sxs-lookup"><span data-stu-id="7a174-127">If you set up a dial plan so that a dialed number can match more than one normalization rule, make sure the more restrictive rules are sorted above the less restrictive ones.</span></span>

6. <span data-ttu-id="7a174-128">Clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="7a174-128">Click **Save**.</span></span>
7. <span data-ttu-id="7a174-129">Se você quiser testar o plano de discagem, em **Teste** plano de discagem , insira um número de telefone e clique em **Testar**.</span><span class="sxs-lookup"><span data-stu-id="7a174-129">If you want to test the dial plan, under **Test dial plan**, enter a phone number, and then click **Test**.</span></span>

### <a name="edit-a-dial-plan"></a><span data-ttu-id="7a174-130">Editar um plano de discagem</span><span class="sxs-lookup"><span data-stu-id="7a174-130">Edit a dial plan</span></span>

1. <span data-ttu-id="7a174-131">Na navegação à esquerda do Centro de administração do Microsoft Teams, vá para **Plano de**  >  **Discagem de Voz**.</span><span class="sxs-lookup"><span data-stu-id="7a174-131">In the left navigation of the Microsoft Teams admin center, go to **Voice** > **Dial plan**.</span></span>
2. <span data-ttu-id="7a174-132">Selecione o plano de discagem clicando à esquerda do nome do plano de discagem e clique em **Editar**.</span><span class="sxs-lookup"><span data-stu-id="7a174-132">Select the dial plan by clicking to the left of the dial plan name, and then click **Edit**.</span></span>
3. <span data-ttu-id="7a174-133">Faça as alterações que você deseja e clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="7a174-133">Make the changes that you want, and then click **Save**.</span></span>

### <a name="assign-a-dial-plan-to-users"></a><span data-ttu-id="7a174-134">Atribuir um plano de discagem aos usuários</span><span class="sxs-lookup"><span data-stu-id="7a174-134">Assign a dial plan to users</span></span>

<span data-ttu-id="7a174-135">Você atribui um plano de discagem da mesma maneira que atribui políticas.</span><span class="sxs-lookup"><span data-stu-id="7a174-135">You assign a dial plan in the same way you assign policies.</span></span> [!INCLUDE [assign-policy](includes/assign-policy.md)]

## <a name="using-powershell"></a><span data-ttu-id="7a174-136">Usando o Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="7a174-136">Using PowerShell</span></span>
  
### <a name="start-powershell"></a><span data-ttu-id="7a174-137">Iniciar o PowerShell</span><span class="sxs-lookup"><span data-stu-id="7a174-137">Start PowerShell</span></span>
- <span data-ttu-id="7a174-138">Abra um prompt Windows PowerShell de comando e execute os seguintes comandos:</span><span class="sxs-lookup"><span data-stu-id="7a174-138">Open a Windows PowerShell command prompt and run the following commands:</span></span>

```powershell
  # When using Teams PowerShell Module

   Import-Module MicrosoftTeams
   $credential = Get-Credential
   Connect-MicrosoftTeams -Credential $credential
```
  
### <a name="create-and-manage-your-dial-plans"></a><span data-ttu-id="7a174-139">Criar e gerenciar seus planos de discagem</span><span class="sxs-lookup"><span data-stu-id="7a174-139">Create and manage your dial plans</span></span>

<span data-ttu-id="7a174-140">Você pode usar um único cmdlet ou um script do PowerShell para criar e gerenciar planos de discagem de locatários.</span><span class="sxs-lookup"><span data-stu-id="7a174-140">You can either use a single cmdlet or a PowerShell script to create and manage tenant dial plans.</span></span>
  
#### <a name="using-single-cmdlets"></a><span data-ttu-id="7a174-141">Usando cmdlets individuais</span><span class="sxs-lookup"><span data-stu-id="7a174-141">Using single cmdlets</span></span>

- <span data-ttu-id="7a174-142">Para criar um novo plano de discagem, execute:</span><span class="sxs-lookup"><span data-stu-id="7a174-142">To create a new dial plan, run:</span></span>
    
  ```PowerShell
  New-CsTenantDialPlan -Identity RedmondDialPlan -Description "Dial Plan for Redmond" -NormalizationRules <pslistmodifier> -ExternalAccessPrefix 9 -SimpleName "Dial-Plan-for-Redmond"
  ```

    <span data-ttu-id="7a174-143">Para outros exemplos e parâmetros, consulte [New-CsTenantDialPlan](/powershell/module/skype/new-cstenantdialplan).</span><span class="sxs-lookup"><span data-stu-id="7a174-143">For other examples and parameters, see [New-CsTenantDialPlan](/powershell/module/skype/new-cstenantdialplan).</span></span>
    
- <span data-ttu-id="7a174-144">Para editar as configurações de um plano de discagem existente, execute:</span><span class="sxs-lookup"><span data-stu-id="7a174-144">To edit the settings of an existing dial plan, run:</span></span>
    
  ```PowerShell
  Set-CsTenantDialPlan -Identity RedmondDialPlan  -NormalizationRules <pslistmodifier> -ExternalAccessPrefix 9
    -SimpleName "Dial-Plan-for-Redmond"
  ```

    <span data-ttu-id="7a174-145">Para outros exemplos e parâmetros, consulte [Set-CsTenantDialPlan](/powershell/module/skype/set-cstenantdialplan).</span><span class="sxs-lookup"><span data-stu-id="7a174-145">For other examples and parameters, see [Set-CsTenantDialPlan](/powershell/module/skype/set-cstenantdialplan).</span></span>
    
- <span data-ttu-id="7a174-146">Para adicionar usuários a um plano de discagem, execute:</span><span class="sxs-lookup"><span data-stu-id="7a174-146">To add users to a dial plan, run:</span></span>
    
  ```PowerShell
  Grant-CsTenantDialPlan -Identity amos.marble@contoso.com -PolicyName RedmondDialPlan
  ```

    <span data-ttu-id="7a174-147">Para outros exemplos e parâmetros, consulte [Grant-CsTenantDialPlan](/powershell/module/skype/grant-cstenantdialplan).</span><span class="sxs-lookup"><span data-stu-id="7a174-147">For other examples and parameters, see [Grant-CsTenantDialPlan](/powershell/module/skype/grant-cstenantdialplan).</span></span>
    
- <span data-ttu-id="7a174-148">Para exibir as configurações em um plano de discagem, execute:</span><span class="sxs-lookup"><span data-stu-id="7a174-148">To view the settings on a dial plan, run:</span></span>
    
  ```PowerShell
  Get-CsTenantDialPlan -Identity RedmondDialPlan
  ```

    <span data-ttu-id="7a174-149">Para outros exemplos e parâmetros, consulte [Get-CsTenantDialPlan](/powershell/module/skype/get-cstenantdialplan?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="7a174-149">For other examples and parameters, see [Get-CsTenantDialPlan](/powershell/module/skype/get-cstenantdialplan?view=skype-ps).</span></span>
    
- <span data-ttu-id="7a174-150">Para excluir um plano de discagem, execute:</span><span class="sxs-lookup"><span data-stu-id="7a174-150">To delete a dial plan, run:</span></span>
    
  ```PowerShell
  Remove-CsTenantDialPlan -Identity RedmondDialPlan -force
  ```

    <span data-ttu-id="7a174-151">Para outros exemplos e parâmetros, consulte [Remove-CsTenantDialPlan](/powershell/module/skype/remove-cstenantdialplan?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="7a174-151">For other examples and parameters, see [Remove-CsTenantDialPlan](/powershell/module/skype/remove-cstenantdialplan?view=skype-ps).</span></span>
    
- <span data-ttu-id="7a174-152">Para ver as configurações do plano de discagem efetivo, execute:</span><span class="sxs-lookup"><span data-stu-id="7a174-152">To see the settings of the effective dial plan, run:</span></span>
    
  ```PowerShell
  Get-CsEffectiveTenantDialPlan -Identity amos.marble@contoso.com
  ```

    <span data-ttu-id="7a174-153">Para outros exemplos e parâmetros, consulte [Get-CsEffectiveTenantDialPlan](/powershell/module/skype/get-cseffectivetenantdialplan).</span><span class="sxs-lookup"><span data-stu-id="7a174-153">For other examples and parameters, see [Get-CsEffectiveTenantDialPlan](/powershell/module/skype/get-cseffectivetenantdialplan).</span></span>
    
- <span data-ttu-id="7a174-154">Para testar as configurações efetivas de um plano de discagem, execute:</span><span class="sxs-lookup"><span data-stu-id="7a174-154">To test the effective settings of a dial plan, run:</span></span>
    
  ```PowerShell
  Test-CsEffectiveTenantDialPlan -DialedNumber 14255550199 -Identity amos.marble@contoso.com
  ```

    <span data-ttu-id="7a174-155">Para outros exemplos e parâmetros, consulte [Test-CsEffectiveTenantDialPlan](/powershell/module/skype/test-cseffectivetenantdialplan?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="7a174-155">For other examples and parameters, see [Test-CsEffectiveTenantDialPlan](/powershell/module/skype/test-cseffectivetenantdialplan?view=skype-ps).</span></span>
    
#### <a name="using-a-powershell-script"></a><span data-ttu-id="7a174-156">Usando um script do PowerShell</span><span class="sxs-lookup"><span data-stu-id="7a174-156">Using a PowerShell script</span></span>

<span data-ttu-id="7a174-157">Execute isso para excluir uma regra de normalização associada a um plano de discagem de locatário sem precisar excluir primeiro o plano de discagem do locatário:</span><span class="sxs-lookup"><span data-stu-id="7a174-157">Run this to delete a normalization rule that is associated with a tenant dial plan without needing to delete the tenant dial plan first:</span></span>
```PowerShell
$b1=New-CsVoiceNormalizationRule -Identity Global/NR4 -InMemory
Set-CsTenantDialPlan -Identity RedmondDialPlan -NormalizationRules @{add=$b1}
(Get-CsTenantDialPlan -Identity RedmondDialPlan).NormalizationRules
$b2=New-CsVoiceNormalizationRule -Identity Global/NR4 -InMemory
Set-CsTenantDialPlan -Identity RedmondDialPlan -NormalizationRules @{remove=$b2}
```
<span data-ttu-id="7a174-158">Execute isso para adicionar a seguinte regra de normalização ao plano de discagem de locatário existente chamado RedmondDialPlan.</span><span class="sxs-lookup"><span data-stu-id="7a174-158">Run this to add the following normalization rule to the existing tenant dial plan named RedmondDialPlan.</span></span>
```PowerShell
$nr1=New-CsVoiceNormalizationRule -Parent Global -Description 'Organization extension dialing' -Pattern '^(\\d{3})$' -Translation '+14255551$1' -Name NR1 -IsInternalExtension $false -InMemory
Set-CsTenantDialPlan -Identity RedmondDialPlan -NormalizationRules @{add=$nr1}
```
<span data-ttu-id="7a174-159">Execute isso para remover a seguinte regra de normalização do plano de discagem de locatário existente chamado RedmondDialPlan.</span><span class="sxs-lookup"><span data-stu-id="7a174-159">Run this to remove the following normalization rule from the existing tenant dial plan named RedmondDialPlan.</span></span>
```PowerShell
$nr1=New-CsVoiceNormalizationRule -Parent Global/NR1 -InMemory
Set-CsTenantDialPlan -Identity RedmondDialPlan -NormalizationRules @{remove=$nr1}
```

<span data-ttu-id="7a174-160">Execute o seguinte quando quiser examinar também as regras de normalização existentes, determinar qual delas você deseja excluir e, em seguida, usar seu índice para removê-la.</span><span class="sxs-lookup"><span data-stu-id="7a174-160">Run the following when you want to also examine the existing normalization rules, determine which one you want to delete, and then use its index to remove it.</span></span> <span data-ttu-id="7a174-161">A matriz de regras de normalização começa com o índice 0.</span><span class="sxs-lookup"><span data-stu-id="7a174-161">The array of normalization rules starts with index 0.</span></span> <span data-ttu-id="7a174-162">Queremos remover a regra de normalização de 3 dígitos, portanto, esse é o índice 1.</span><span class="sxs-lookup"><span data-stu-id="7a174-162">We would like to remove the 3-digit normalization rule, so that is index 1.</span></span>
  
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

<span data-ttu-id="7a174-163">Execute isso para encontrar todos os usuários que foram concedidos ao plano de discagem de locatário RedmondDialPlan.</span><span class="sxs-lookup"><span data-stu-id="7a174-163">Run this to find all users who have been granted the RedmondDialPlan tenant dial plan.</span></span>
  
```PowerShell
Get-CsOnlineUser | Where-Object {$_.TenantDialPlan -eq "RedmondDialPlan"}
```

<span data-ttu-id="7a174-164">Execute isso para remover qualquer TenantDialPlan atribuído de todos os usuários que tenham um HostingProvider de sipfed.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="7a174-164">Run this to remove any assigned TenantDialPlan from all users who have a HostingProvider of sipfed.online.lync.com.</span></span>
```PowerShell
Get-CsOnlineUser -Filter {HostingProvider -eq "sipfed.online.lync.com"} | Grant-CsTenantDialPlan -policyname $null
```

<span data-ttu-id="7a174-165">Execute-os para adicionar o plano de discagem local existente chamado OPDP1 como um plano de discagem de locatário para sua organização.</span><span class="sxs-lookup"><span data-stu-id="7a174-165">Run these to add the existing on-premises dial plan named OPDP1 as a tenant dial plan for your organization.</span></span> <span data-ttu-id="7a174-166">Primeiro, você precisa salvar o plano de discagem local em um arquivo .xml e usá-lo para criar o novo plano de discagem de locatário.</span><span class="sxs-lookup"><span data-stu-id="7a174-166">You need to first save the on-premises dial plan to an .xml file, and then use it to create the new tenant dial plan.</span></span>
  
<span data-ttu-id="7a174-167">Execute isso para salvar o plano de discagem local no arquivo .xml.</span><span class="sxs-lookup"><span data-stu-id="7a174-167">Run this to save the on-premises dial plan to the .xml file.</span></span>
  
```PowerShell
$DPName = "OPDP1"
$DPFileName = "dialplan.xml"
Get-CsDialplan $DPName | Export-Clixml $DPFileName
```

<span data-ttu-id="7a174-168">Execute isso para criar o novo plano de discagem de locatário.</span><span class="sxs-lookup"><span data-stu-id="7a174-168">Run this to create the new tenant dial plan.</span></span>
  
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
    
## <a name="related-topics"></a><span data-ttu-id="7a174-169">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="7a174-169">Related topics</span></span>

- [<span data-ttu-id="7a174-170">O que são planos de discagem?</span><span class="sxs-lookup"><span data-stu-id="7a174-170">What are dial plans?</span></span>](what-are-dial-plans.md)
- [<span data-ttu-id="7a174-171">Perguntas comuns sobre a transferência de números de telefone</span><span class="sxs-lookup"><span data-stu-id="7a174-171">Transferring phone numbers common questions</span></span>](./phone-number-calling-plans/port-order-overview.md)
- [<span data-ttu-id="7a174-172">Diferentes tipos de números de telefone usados para Planos de Chamadas</span><span class="sxs-lookup"><span data-stu-id="7a174-172">Different kinds of phone numbers used for Calling Plans</span></span>](different-kinds-of-phone-numbers-used-for-calling-plans.md)
- [<span data-ttu-id="7a174-173">Gerenciar os números de telefone de sua organização</span><span class="sxs-lookup"><span data-stu-id="7a174-173">Manage phone numbers for your organization</span></span>](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)
- [<span data-ttu-id="7a174-174">Termos e condições das Chamadas de Emergência</span><span class="sxs-lookup"><span data-stu-id="7a174-174">Emergency calling terms and conditions</span></span>](emergency-calling-terms-and-conditions.md)
- <span data-ttu-id="7a174-175">[Rótulo de aviso de isenção de responsabilidade de chamada de emergência](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)</span><span class="sxs-lookup"><span data-stu-id="7a174-175">[Emergency calling disclaimer label](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)</span></span>
- [<span data-ttu-id="7a174-176">Visão Geral do PowerShell do Teams</span><span class="sxs-lookup"><span data-stu-id="7a174-176">Teams PowerShell overview</span></span>](teams-powershell-overview.md)