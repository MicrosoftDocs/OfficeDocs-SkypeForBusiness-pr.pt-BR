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
description: Saiba como usar o centro de administração do Microsoft Teams ou o Windows PowerShell para criar e gerenciar planos de discagem (planos de discagem de chamada PSTN).
ms.openlocfilehash: 966ac2e21d3bc57dd32a0b2732e0be285b9fdf0d
ms.sourcegitcommit: 1807ea5509f8efa6abba8462bce2f3646117e8bf
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/10/2020
ms.locfileid: "44691337"
---
# <a name="create-and-manage-dial-plans"></a><span data-ttu-id="be23a-103">Criar e gerenciar planos de discagem</span><span class="sxs-lookup"><span data-stu-id="be23a-103">Create and manage dial plans</span></span>

<span data-ttu-id="be23a-104">Depois de planejar os planos de discagem para a sua organização e descobrir todas as regras de normalização que precisam ser criadas para o encaminhamento de chamadas, você estará pronto para criar os planos de discagem.</span><span class="sxs-lookup"><span data-stu-id="be23a-104">After you plan the dial plans for your organization and figured out all the normalization rules that need to be created for call routing, you're ready to create the dial plans.</span></span> <span data-ttu-id="be23a-105">Você pode usar o centro de administração do Microsoft Teams ou o Windows PowerShell para criar e gerenciar planos de discagem.</span><span class="sxs-lookup"><span data-stu-id="be23a-105">You can use the Microsoft Teams admin center or Windows PowerShell to create and manage dial plans.</span></span>  

## <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="be23a-106">Usando o centro de administração do Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="be23a-106">Using the Microsoft Teams admin center</span></span>

### <a name="create-a-dial-plan"></a><span data-ttu-id="be23a-107">Criar um plano de discagem</span><span class="sxs-lookup"><span data-stu-id="be23a-107">Create a dial plan</span></span>

1. <span data-ttu-id="be23a-108">Na navegação à esquerda do centro de administração do Microsoft Teams, **Voice**vá para  >  **plano de discagem**por voz.</span><span class="sxs-lookup"><span data-stu-id="be23a-108">In the left navigation of the Microsoft Teams admin center, go to **Voice** > **Dial plan**.</span></span>
2. <span data-ttu-id="be23a-109">Clique em **Adicionar**e, em seguida, insira um nome e uma descrição para o plano de discagem.</span><span class="sxs-lookup"><span data-stu-id="be23a-109">Click **Add**, and then enter a name and description for the dial plan.</span></span>
    <span data-ttu-id="be23a-110">![Captura de tela mostrando a página Adicionar para criar um plano de discagem](media/create-dial-plan.png)</span><span class="sxs-lookup"><span data-stu-id="be23a-110">![Screenshot showing the Add page for creating a dial plan](media/create-dial-plan.png)</span></span>
3. <span data-ttu-id="be23a-111">Em **detalhes do plano de discagem**, especifique um prefixo de discagem externo se os usuários precisarem discar um ou mais dígitos iniciais adicionais (por exemplo, 9) para obter uma linha externa.</span><span class="sxs-lookup"><span data-stu-id="be23a-111">Under **Dial plan details**, specify an external dialing prefix if users need to dial one or more additional leading digits (for example, 9) to get an external line.</span></span> <span data-ttu-id="be23a-112">Para fazer isso:</span><span class="sxs-lookup"><span data-stu-id="be23a-112">To do this:</span></span>
    1. <span data-ttu-id="be23a-113">Na caixa **prefixo de discagem externo** , insira um prefixo de discagem externo.</span><span class="sxs-lookup"><span data-stu-id="be23a-113">In the **External dialing prefix** box, enter an external dialing prefix.</span></span> <span data-ttu-id="be23a-114">O prefixo pode ter até quatro caracteres (#, \* e 0-9).</span><span class="sxs-lookup"><span data-stu-id="be23a-114">The prefix can be up to four characters (#,\*, and 0-9).</span></span>
    2. <span data-ttu-id="be23a-115">Ative a **discagem otimizada de dispositivo**.</span><span class="sxs-lookup"><span data-stu-id="be23a-115">Turn on **Optimized device dialing**.</span></span> <span data-ttu-id="be23a-116">Se você especificar um prefixo de discagem externo, também deverá ativar essa configuração para aplicar o prefixo para que as chamadas possam ser feitas fora de sua organização.</span><span class="sxs-lookup"><span data-stu-id="be23a-116">If you specify an external dialing prefix, you must also turn on this setting to apply the prefix so calls can be made outside your organization.</span></span>
4. <span data-ttu-id="be23a-117">Em **regras de normalização**, configure e associe uma ou mais [regras de normalização](what-are-dial-plans.md#normalization-rules) para o plano de discagem.</span><span class="sxs-lookup"><span data-stu-id="be23a-117">Under **Normalization rules**, configure and associate one or more [normalization rules](what-are-dial-plans.md#normalization-rules) for the dial plan.</span></span> <span data-ttu-id="be23a-118">Cada plano de discagem deve ter pelo menos uma regra de normalidade associada a ele.</span><span class="sxs-lookup"><span data-stu-id="be23a-118">Each dial plan must have at least one normalization rule associated with it.</span></span>  <span data-ttu-id="be23a-119">Para fazer isso, siga um ou mais destes procedimentos:</span><span class="sxs-lookup"><span data-stu-id="be23a-119">To do this, do one or more of the following:</span></span>
    - <span data-ttu-id="be23a-120">Para criar uma nova regra de normalização e associá-la ao plano de discagem, clique em **Adicionar**e, em seguida, defina a regra.</span><span class="sxs-lookup"><span data-stu-id="be23a-120">To create a new normalization rule and associate it with the dial plan, click **Add**, and then define the rule.</span></span>
    - <span data-ttu-id="be23a-121">Para editar uma regra de normalização que já esteja associada ao plano de discagem, selecione a regra clicando à esquerda do nome da regra e, em seguida, clique em **Editar**.</span><span class="sxs-lookup"><span data-stu-id="be23a-121">To edit a normalization rule that's already associated with the dial plan, select the rule by clicking to the left of the rule name, and then click **Edit**.</span></span> <span data-ttu-id="be23a-122">Faça as alterações desejadas e clique em **salvar**.</span><span class="sxs-lookup"><span data-stu-id="be23a-122">Make the changes you want, and then click **Save**.</span></span>
    - <span data-ttu-id="be23a-123">Para remover uma regra de normalização do plano de discagem, selecione a regra clicando à esquerda do nome da regra e, em seguida, clique em **remover**.</span><span class="sxs-lookup"><span data-stu-id="be23a-123">To remove a normalization rule from the dial plan, select the rule by clicking to the left of the rule name, and then click **Remove**.</span></span>
5. <span data-ttu-id="be23a-124">Organize as regras de normalização na ordem desejada.</span><span class="sxs-lookup"><span data-stu-id="be23a-124">Arrange the normalization rules in the order that you want.</span></span> <span data-ttu-id="be23a-125">Clique em **mover para cima** ou mover para **baixo** para alterar a posição das regras na lista.</span><span class="sxs-lookup"><span data-stu-id="be23a-125">Click **Move up** or **Move down** to change the position of rules in the list.</span></span>

    > [!NOTE]
    > <span data-ttu-id="be23a-126">O Microsoft Teams percorre a lista de regras de normalização do início e usa a primeira regra que corresponde ao número discado.</span><span class="sxs-lookup"><span data-stu-id="be23a-126">Teams traverses the list of normalization rules from the top down and uses the first rule that matches the dialed number.</span></span> <span data-ttu-id="be23a-127">Se você configurar um plano de discagem para que um número discado possa corresponder a mais de uma regra de normalização, certifique-se de que as regras mais restritivas sejam classificadas acima das menos restritivas.</span><span class="sxs-lookup"><span data-stu-id="be23a-127">If you set up a dial plan so that a dialed number can match more than one normalization rule, make sure the more restrictive rules are sorted above the less restrictive ones.</span></span>

6. <span data-ttu-id="be23a-128">Clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="be23a-128">Click **Save**.</span></span>
7. <span data-ttu-id="be23a-129">Se você quiser testar o plano de discagem, em **testar plano de discagem**, insira um número de telefone e clique em **testar**.</span><span class="sxs-lookup"><span data-stu-id="be23a-129">If you want to test the dial plan, under **Test dial plan**, enter a phone number, and then click **Test**.</span></span>

### <a name="edit-a-dial-plan"></a><span data-ttu-id="be23a-130">Editar um plano de discagem</span><span class="sxs-lookup"><span data-stu-id="be23a-130">Edit a dial plan</span></span>

1. <span data-ttu-id="be23a-131">Na navegação à esquerda do centro de administração do Microsoft Teams, **Voice**vá para  >  **plano de discagem**por voz.</span><span class="sxs-lookup"><span data-stu-id="be23a-131">In the left navigation of the Microsoft Teams admin center, go to **Voice** > **Dial plan**.</span></span>
2. <span data-ttu-id="be23a-132">Selecione o plano de discagem clicando à esquerda do nome do plano de discagem e, em seguida, clique em **Editar**.</span><span class="sxs-lookup"><span data-stu-id="be23a-132">Select the dial plan by clicking to the left of the dial plan name, and then click **Edit**.</span></span>
3. <span data-ttu-id="be23a-133">Faça as alterações desejadas e clique em **salvar**.</span><span class="sxs-lookup"><span data-stu-id="be23a-133">Make the changes that you want, and then click **Save**.</span></span>

### <a name="add-users-to-a-dial-plan"></a><span data-ttu-id="be23a-134">Adicionar usuários a um plano de discagem</span><span class="sxs-lookup"><span data-stu-id="be23a-134">Add users to a dial plan</span></span>

1. <span data-ttu-id="be23a-135">Na navegação à esquerda do centro de administração do Microsoft Teams, vá para **usuários**.</span><span class="sxs-lookup"><span data-stu-id="be23a-135">In the left navigation of the Microsoft Teams admin center, go to **Users**.</span></span>
2. <span data-ttu-id="be23a-136">Selecione o usuário clicando no nome para exibição.</span><span class="sxs-lookup"><span data-stu-id="be23a-136">Select the user by clicking the display name.</span></span>
3. <span data-ttu-id="be23a-137">Selecione a guia **políticas** .</span><span class="sxs-lookup"><span data-stu-id="be23a-137">Select the **Policies** tab.</span></span>
4. <span data-ttu-id="be23a-138">Clique em **Editar** à direita das políticas atribuídas.</span><span class="sxs-lookup"><span data-stu-id="be23a-138">Click **Edit** to the right of Assigned policies.</span></span>
5. <span data-ttu-id="be23a-139">No menu suspenso **plano de discagem** , selecione o plano de discagem que você deseja atribuir ao usuário e clique em **aplicar**.</span><span class="sxs-lookup"><span data-stu-id="be23a-139">From the **Dial plan** drop-down menu, select the dial plan you want to assign to the user and then click **Apply**.</span></span>

## <a name="using-powershell"></a><span data-ttu-id="be23a-140">Usando o PowerShell</span><span class="sxs-lookup"><span data-stu-id="be23a-140">Using PowerShell</span></span>
  
### <a name="verify-and-start-remote-powershell"></a><span data-ttu-id="be23a-141">Verificar e iniciar o PowerShell remoto</span><span class="sxs-lookup"><span data-stu-id="be23a-141">Verify and start Remote PowerShell</span></span>

 <span data-ttu-id="be23a-142">**Verifique se você está executando o Windows PowerShell versão 3,0 ou posterior**</span><span class="sxs-lookup"><span data-stu-id="be23a-142">**Check that you are running Windows PowerShell version 3.0 or later**</span></span>
  
1. <span data-ttu-id="be23a-143">Para verificar se você está executando a versão 3,0 ou superior: **menu iniciar**  >  **Windows PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="be23a-143">To verify that you're running version 3.0 or higher: **Start Menu** > **Windows PowerShell**.</span></span>
    
2. <span data-ttu-id="be23a-144">Verifique a versão digitando  _Get-Host_ na janela do **Windows PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="be23a-144">Check the version by typing  _Get-Host_ in the **Windows PowerShell** window.</span></span>
    
3. <span data-ttu-id="be23a-145">Se você não tiver a versão 3,0 ou posterior, baixe e instale atualizações para o Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="be23a-145">If you don't have version 3.0 or later, download and install updates to Windows PowerShell.</span></span> <span data-ttu-id="be23a-146">Consulte [Windows Management Framework 4,0](https://go.microsoft.com/fwlink/?LinkId=716845) para baixar e atualizar o Windows PowerShell para a versão 4,0.</span><span class="sxs-lookup"><span data-stu-id="be23a-146">See [Windows Management Framework 4.0](https://go.microsoft.com/fwlink/?LinkId=716845) to download and update Windows PowerShell to version 4.0.</span></span> <span data-ttu-id="be23a-147">Reinicie o computador quando for solicitado.</span><span class="sxs-lookup"><span data-stu-id="be23a-147">Restart your computer when you're prompted.</span></span>
    
4. <span data-ttu-id="be23a-148">Você também precisará instalar o módulo do Windows PowerShell para o Skype for Business online que permite que você crie uma sessão remota do Windows PowerShell que se conecta ao Skype for Business online.</span><span class="sxs-lookup"><span data-stu-id="be23a-148">You'll also need to install the Windows PowerShell module for Skype for Business Online that enables you to create a remote Windows PowerShell session that connects to Skype for Business Online.</span></span> <span data-ttu-id="be23a-149">Você pode baixar esse módulo, que tem suporte apenas em computadores de 64 bits, no [módulo do Windows PowerShell para Skype for Business online](https://go.microsoft.com/fwlink/?LinkId=294688).</span><span class="sxs-lookup"><span data-stu-id="be23a-149">You can download this module, which is supported only on 64-bit computers, at [Windows PowerShell Module for Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=294688).</span></span> <span data-ttu-id="be23a-150">Reinicie o computador se for solicitado.</span><span class="sxs-lookup"><span data-stu-id="be23a-150">Restart your computer if you're prompted.</span></span>
    
<span data-ttu-id="be23a-151">Para saber mais, confira [conectar-se a todos os serviços do Microsoft 365 ou do Office 365 em uma única janela do Windows PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-all-office-365-services-in-a-single-windows-powershell-window).</span><span class="sxs-lookup"><span data-stu-id="be23a-151">To learn more, see [Connect to all Microsoft 365 or Office 365 services in a single Windows PowerShell window](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-all-office-365-services-in-a-single-windows-powershell-window).</span></span>
  
 <span data-ttu-id="be23a-152">**Iniciar uma sessão do Windows PowerShell**</span><span class="sxs-lookup"><span data-stu-id="be23a-152">**Start a Windows PowerShell session**</span></span>
  
1. <span data-ttu-id="be23a-153">Clique em **Iniciar**o  >  **Windows PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="be23a-153">Click **Start** > **Windows PowerShell**.</span></span>
    
2. <span data-ttu-id="be23a-154">Na janela do **Windows PowerShell** , conecte-se ao Microsoft 365 ou ao Office 365 executando:</span><span class="sxs-lookup"><span data-stu-id="be23a-154">In the **Windows PowerShell** window, connect to Microsoft 365 or Office 365 by running:</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="be23a-155">[!OBSERVAçãO] Execute o comando **Import-Module** apenas quando usar o módulo do Windows PowerShell do Skype for Business Online pela primeira vez.</span><span class="sxs-lookup"><span data-stu-id="be23a-155">You only have to run the **Import-Module** command the first time you use the Skype for Business Online Windows PowerShell module.</span></span>
  

    ```PowerShell
    Import-Module "C:\\Program Files\\Common Files\\Skype for Business Online\\Modules\\SkypeOnlineConnector\\SkypeOnlineConnector.psd1"
    $credential = Get-Credential
    $session = New-CsOnlineSession -Credential $credential
    Import-PSSession $session
    ```
  
### <a name="create-and-manage-your-dial-plans"></a><span data-ttu-id="be23a-156">Criar e gerenciar seus planos de discagem</span><span class="sxs-lookup"><span data-stu-id="be23a-156">Create and manage your dial plans</span></span>

<span data-ttu-id="be23a-157">Você pode usar um único cmdlet ou um script do PowerShell para criar e gerenciar planos de discagem de locatário.</span><span class="sxs-lookup"><span data-stu-id="be23a-157">You can either use a single cmdlet or a PowerShell script to create and manage tenant dial plans.</span></span>
  
#### <a name="using-single-cmdlets"></a><span data-ttu-id="be23a-158">Usando cmdlets únicos</span><span class="sxs-lookup"><span data-stu-id="be23a-158">Using single cmdlets</span></span>

- <span data-ttu-id="be23a-159">Para criar um novo plano de discagem, execute:</span><span class="sxs-lookup"><span data-stu-id="be23a-159">To create a new dial plan, run:</span></span>
    
  ```PowerShell
  New-CsTenantDialPlan -Identity RedmondDialPlan -Description "Dial Plan for Redmond" -NormalizationRules <pslistmodifier> -ExternalAccessPrefix 9 -SimpleName "Dial-Plan-for-Redmond"
  ```

    <span data-ttu-id="be23a-160">Para obter outros exemplos e parâmetros, veja [New-CsTenantDialPlan](https://docs.microsoft.com/powershell/module/skype/new-cstenantdialplan).</span><span class="sxs-lookup"><span data-stu-id="be23a-160">For other examples and parameters, see [New-CsTenantDialPlan](https://docs.microsoft.com/powershell/module/skype/new-cstenantdialplan).</span></span>
    
- <span data-ttu-id="be23a-161">Para editar as configurações de um plano de discagem existente, execute:</span><span class="sxs-lookup"><span data-stu-id="be23a-161">To edit the settings of an existing dial plan, run:</span></span>
    
  ```PowerShell
  Set-CsTenantDialPlan -Identity RedmondDialPlan  -NormalizationRules <pslistmodifier> -ExternalAccessPrefix 9
    -SimpleName "Dial-Plan-for-Redmond"
  ```

    <span data-ttu-id="be23a-162">Para obter outros exemplos e parâmetros, consulte [set-CsTenantDialPlan](https://docs.microsoft.com/powershell/module/skype/set-cstenantdialplan).</span><span class="sxs-lookup"><span data-stu-id="be23a-162">For other examples and parameters, see [Set-CsTenantDialPlan](https://docs.microsoft.com/powershell/module/skype/set-cstenantdialplan).</span></span>
    
- <span data-ttu-id="be23a-163">Para adicionar usuários a um plano de discagem, execute:</span><span class="sxs-lookup"><span data-stu-id="be23a-163">To add users to a dial plan, run:</span></span>
    
  ```PowerShell
  Grant-CsTenantDialPlan -Identity amos.marble@contoso.com -PolicyName RedmondDialPlan
  ```

    <span data-ttu-id="be23a-164">Para obter outros exemplos e parâmetros, veja [Grant-CsTenantDialPlan](https://docs.microsoft.com/powershell/module/skype/grant-cstenantdialplan).</span><span class="sxs-lookup"><span data-stu-id="be23a-164">For other examples and parameters, see [Grant-CsTenantDialPlan](https://docs.microsoft.com/powershell/module/skype/grant-cstenantdialplan).</span></span>
    
- <span data-ttu-id="be23a-165">Para exibir as configurações em um plano de discagem, execute:</span><span class="sxs-lookup"><span data-stu-id="be23a-165">To view the settings on a dial plan, run:</span></span>
    
  ```PowerShell
  Get-CsTenantDialPlan -Identity RedmondDialPlan
  ```

    <span data-ttu-id="be23a-166">Para obter outros exemplos e parâmetros, veja [Get-CsTenantDialPlan](https://docs.microsoft.com/powershell/module/skype/get-cstenantdialplan?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="be23a-166">For other examples and parameters, see [Get-CsTenantDialPlan](https://docs.microsoft.com/powershell/module/skype/get-cstenantdialplan?view=skype-ps).</span></span>
    
- <span data-ttu-id="be23a-167">Para excluir um plano de discagem, execute:</span><span class="sxs-lookup"><span data-stu-id="be23a-167">To delete a dial plan, run:</span></span>
    
  ```PowerShell
  Remove-CsTenantDialPlan -Identity RedmondDialPlan -force
  ```

    <span data-ttu-id="be23a-168">Para obter outros exemplos e parâmetros, veja [Remove-CsTenantDialPlan](https://docs.microsoft.com/powershell/module/skype/remove-cstenantdialplan?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="be23a-168">For other examples and parameters, see [Remove-CsTenantDialPlan](https://docs.microsoft.com/powershell/module/skype/remove-cstenantdialplan?view=skype-ps).</span></span>
    
- <span data-ttu-id="be23a-169">Para ver as configurações do plano de discagem efetivo, execute:</span><span class="sxs-lookup"><span data-stu-id="be23a-169">To see the settings of the effective dial plan, run:</span></span>
    
  ```PowerShell
  Get-CsEffectiveTenantDialPlan -Identity amos.marble@contoso.com
  ```

    <span data-ttu-id="be23a-170">Para obter outros exemplos e parâmetros, veja [Get-CsEffectiveTenantDialPlan](https://docs.microsoft.com/powershell/module/skype/get-cseffectivetenantdialplan).</span><span class="sxs-lookup"><span data-stu-id="be23a-170">For other examples and parameters, see [Get-CsEffectiveTenantDialPlan](https://docs.microsoft.com/powershell/module/skype/get-cseffectivetenantdialplan).</span></span>
    
- <span data-ttu-id="be23a-171">Para testar as configurações efetivas de um plano de discagem, execute:</span><span class="sxs-lookup"><span data-stu-id="be23a-171">To test the effective settings of a dial plan, run:</span></span>
    
  ```PowerShell
  Test-CsEffectiveTenantDialPlan -DialedNumber 14255550199 -Identity amos.marble@contoso.com
  ```

    <span data-ttu-id="be23a-172">Para obter outros exemplos e parâmetros, veja [Test-CsEffectiveTenantDialPlan](https://docs.microsoft.com/powershell/module/skype/test-cseffectivetenantdialplan?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="be23a-172">For other examples and parameters, see [Test-CsEffectiveTenantDialPlan](https://docs.microsoft.com/powershell/module/skype/test-cseffectivetenantdialplan?view=skype-ps).</span></span>
    
#### <a name="using-a-powershell-script"></a><span data-ttu-id="be23a-173">Usando um script do PowerShell</span><span class="sxs-lookup"><span data-stu-id="be23a-173">Using a PowerShell script</span></span>

<span data-ttu-id="be23a-174">Execute isso para excluir uma regra de normalização associada a um plano de discagem de locatário sem precisar excluir o plano de discagem de locatário primeiro:</span><span class="sxs-lookup"><span data-stu-id="be23a-174">Run this to delete a normalization rule that is associated with a tenant dial plan without needing to delete the tenant dial plan first:</span></span>
```PowerShell
$b1=New-CsVoiceNormalizationRule -Identity Global/NR4 -InMemory
Set-CsTenantDialPlan -Identity RedmondDialPlan -NormalizationRules @{add=$b1}
(Get-CsTenantDialPlan -Identity RedmondDialPlan).NormalizationRules
$b2=New-CsVoiceNormalizationRule -Identity Global/NR4 -InMemory
Set-CsTenantDialPlan -Identity RedmondDialPlan -NormalizationRules @{remove=$b2}
```
<span data-ttu-id="be23a-175">Execute isso para adicionar a seguinte regra de normalização ao plano de discagem de locatário existente chamado RedmondDialPlan.</span><span class="sxs-lookup"><span data-stu-id="be23a-175">Run this to add the following normalization rule to the existing tenant dial plan named RedmondDialPlan.</span></span>
```PowerShell
$nr1=New-CsVoiceNormalizationRule -Parent Global -Description 'Organization extension dialing' -Pattern '^(\\d{3})$' -Translation '+14255551$1' -Name NR1 -IsInternalExtension $false -InMemory
Set-CsTenantDialPlan -Identity RedmondDialPlan -NormalizationRules @{add=$nr1}
```
<span data-ttu-id="be23a-176">Execute esta regra para remover a seguinte regra de normalização do plano de discagem de locatário existente chamado RedmondDialPlan.</span><span class="sxs-lookup"><span data-stu-id="be23a-176">Run this to remove the following normalization rule from the existing tenant dial plan named RedmondDialPlan.</span></span>
```PowerShell
$nr1=New-CsVoiceNormalizationRule -Parent Global/NR1 -InMemory
Set-CsTenantDialPlan -Identity RedmondDialPlan -NormalizationRules @{remove=$nr1}
```

<span data-ttu-id="be23a-177">Execute o seguinte quando você deseja examinar também as regras de normalização existentes, determinar qual delas deseja excluir e, em seguida, use o índice para removê-la.</span><span class="sxs-lookup"><span data-stu-id="be23a-177">Run the following when you want to also examine the existing normalization rules, determine which one you want to delete, and then use its index to remove it.</span></span> <span data-ttu-id="be23a-178">A matriz de regras de normalização começa com o índice 0.</span><span class="sxs-lookup"><span data-stu-id="be23a-178">The array of normalization rules starts with index 0.</span></span> <span data-ttu-id="be23a-179">Gostaríamos de remover a regra de normalização de 3 dígitos, para que seja o índice 1.</span><span class="sxs-lookup"><span data-stu-id="be23a-179">We would like to remove the 3-digit normalization rule, so that is index 1.</span></span>
  
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

<span data-ttu-id="be23a-180">Execute este procedimento para localizar todos os usuários que receberam o plano de discagem de locatários do RedmondDialPlan.</span><span class="sxs-lookup"><span data-stu-id="be23a-180">Run this to find all users who have been granted the RedmondDialPlan tenant dial plan.</span></span>
  
```PowerShell
Get-CsOnlineUser | Where-Object {$_.TenantDialPlan -eq "RedmondDialPlan"}
```

<span data-ttu-id="be23a-181">Execute isso para remover qualquer TenantDialPlan atribuído de todos os usuários que tenham um hostprovider do sipfed.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="be23a-181">Run this to remove any assigned TenantDialPlan from all users who have a HostingProvider of sipfed.online.lync.com.</span></span>
```PowerShell
Get-CsOnlineUser -Filter {HostingProvider -eq "sipfed.online.lync.com"} | Grant-CsTenantDialPlan -policyname $null
```

<span data-ttu-id="be23a-182">Execute-os para adicionar o plano de discagem local existente chamado OPDP1 como um plano de discagem de locatário para a sua organização.</span><span class="sxs-lookup"><span data-stu-id="be23a-182">Run these to add the existing on-premises dial plan named OPDP1 as a tenant dial plan for your organization.</span></span> <span data-ttu-id="be23a-183">Primeiro, você precisa salvar o plano de discagem local em um arquivo. xml e usá-lo para criar o novo plano de discagem de locatário.</span><span class="sxs-lookup"><span data-stu-id="be23a-183">You need to first save the on-premises dial plan to an .xml file, and then use it to create the new tenant dial plan.</span></span>
  
<span data-ttu-id="be23a-184">Execute isso para salvar o plano de discagem local para o arquivo. xml.</span><span class="sxs-lookup"><span data-stu-id="be23a-184">Run this to save the on-premises dial plan to the .xml file.</span></span>
  
```PowerShell
$DPName = "OPDP1"
$DPFileName = "dialplan.xml"
Get-CsDialplan $DPName | Export-Clixml $DPFileName
```

<span data-ttu-id="be23a-185">Execute este procedimento para criar o novo plano de discagem de locatário.</span><span class="sxs-lookup"><span data-stu-id="be23a-185">Run this to create the new tenant dial plan.</span></span>
  
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
    
## <a name="related-topics"></a><span data-ttu-id="be23a-186">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="be23a-186">Related topics</span></span>

- [<span data-ttu-id="be23a-187">O que são planos de discagem?</span><span class="sxs-lookup"><span data-stu-id="be23a-187">What are dial plans?</span></span>](what-are-dial-plans.md)
- [<span data-ttu-id="be23a-188">Perguntas comuns sobre a transferência de números de telefone</span><span class="sxs-lookup"><span data-stu-id="be23a-188">Transferring phone numbers common questions</span></span>](transferring-phone-numbers-common-questions.md)
- [<span data-ttu-id="be23a-189">Diferentes tipos de números de telefone usados para Planos de Chamadas</span><span class="sxs-lookup"><span data-stu-id="be23a-189">Different kinds of phone numbers used for Calling Plans</span></span>](different-kinds-of-phone-numbers-used-for-calling-plans.md)
- [<span data-ttu-id="be23a-190">Gerenciar os números de telefone de sua organização</span><span class="sxs-lookup"><span data-stu-id="be23a-190">Manage phone numbers for your organization</span></span>](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)
- [<span data-ttu-id="be23a-191">Termos e condições das Chamadas de Emergência</span><span class="sxs-lookup"><span data-stu-id="be23a-191">Emergency calling terms and conditions</span></span>](emergency-calling-terms-and-conditions.md)
- <span data-ttu-id="be23a-192">[Rótulo de isenção de isenção de emergência](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)</span><span class="sxs-lookup"><span data-stu-id="be23a-192">[Emergency calling disclaimer label](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)</span></span>
- [<span data-ttu-id="be23a-193">Visão Geral do PowerShell do Teams</span><span class="sxs-lookup"><span data-stu-id="be23a-193">Teams PowerShell overview</span></span>](teams-powershell-overview.md)
