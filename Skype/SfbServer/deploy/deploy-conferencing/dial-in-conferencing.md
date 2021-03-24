---
title: Configurar conferência discada no Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 38d9f168-80b8-46f2-a1c0-becd84e58e73
description: 'Resumo: leia este tópico para saber como configurar a conferência discada no Skype for Business Server.'
ms.openlocfilehash: 5f618e22cc45585baddf1e8d6090b9e211dc5681
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51103847"
---
# <a name="configure-dial-in-conferencing-in-skype-for-business-server"></a><span data-ttu-id="104f4-103">Configurar conferência discada no Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="104f4-103">Configure dial-in conferencing in Skype for Business Server</span></span>
 
<span data-ttu-id="104f4-104">**Resumo:** Leia este tópico para saber como configurar a conferência discada no Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="104f4-104">**Summary:** Read this topic to learn how to configure dial-in conferencing in Skype for Business Server.</span></span>
  
<span data-ttu-id="104f4-105">Depois de criar uma topologia que inclua a carga de trabalho de conferência e conferência discadas selecionada, você deve executar etapas adicionais para configurar a conferência discadas.</span><span class="sxs-lookup"><span data-stu-id="104f4-105">After you have created a topology that includes the conferencing workload and selected dial-in conferencing, you must perform additional steps to configure dial-in conferencing.</span></span> <span data-ttu-id="104f4-106">Antes de ler este tópico, leia Plan [for dial-in conferencing in Skype for Business Server,](../../plan-your-deployment/conferencing/dial-in-conferencing.md)Hardware and [software requirements for conferencing in Skype for Business Server](../../plan-your-deployment/conferencing/hardware-and-software-requirements.md), and the Deployment [flowchart and checklist for dial-in conferencing](deploy-conferencing.md#deployment-flowchart-and-checklist-for-dial-in-conferencing).</span><span class="sxs-lookup"><span data-stu-id="104f4-106">Before you read this topic, be sure you have read [Plan for dial-in conferencing in Skype for Business Server](../../plan-your-deployment/conferencing/dial-in-conferencing.md), [Hardware and software requirements for conferencing in Skype for Business Server](../../plan-your-deployment/conferencing/hardware-and-software-requirements.md), and the [Deployment flowchart and checklist for dial-in conferencing](deploy-conferencing.md#deployment-flowchart-and-checklist-for-dial-in-conferencing).</span></span> 
  
<span data-ttu-id="104f4-107">Para configurar a conferência discagem, você deve executar as seguintes tarefas:</span><span class="sxs-lookup"><span data-stu-id="104f4-107">To configure dial-in conferencing, you must perform the following tasks:</span></span>
  
- [<span data-ttu-id="104f4-108">Configure planos de discagem</span><span class="sxs-lookup"><span data-stu-id="104f4-108">Configure dial plans</span></span>](dial-in-conferencing.md#BKMK_ConfigureDialPlans)
    
- [<span data-ttu-id="104f4-109">Configurar regiões de conferência discadas</span><span class="sxs-lookup"><span data-stu-id="104f4-109">Configure dial-in conferencing regions</span></span>](dial-in-conferencing.md#BKMK_ConfigureDialInRegions)
    
- [<span data-ttu-id="104f4-110">Configure números de acesso de discagem</span><span class="sxs-lookup"><span data-stu-id="104f4-110">Configure dial-in access numbers</span></span>](dial-in-conferencing.md#BKMK_ConfigureDialInAccessNumbers)
    
- [<span data-ttu-id="104f4-111">Configurar políticas de conferência</span><span class="sxs-lookup"><span data-stu-id="104f4-111">Configure conferencing policies</span></span>](dial-in-conferencing.md#BKMK_ConfigureConferencingPolicies)
    
- [<span data-ttu-id="104f4-112">Atribuir um URI de linha a uma conta de usuário</span><span class="sxs-lookup"><span data-stu-id="104f4-112">Assign a Line URI to a user account</span></span>](dial-in-conferencing.md#BKMK_AssignaLineURI)
    
<span data-ttu-id="104f4-113">Além disso, você pode executar as seguintes tarefas opcionais.</span><span class="sxs-lookup"><span data-stu-id="104f4-113">In addition, you may perform the following optional tasks.</span></span> <span data-ttu-id="104f4-114">Para obter mais informações sobre essas tarefas opcionais, consulte [Manage dial-in conferencing in Skype for Business Server](../../manage/conferencing/dial-in-conferencing.md).</span><span class="sxs-lookup"><span data-stu-id="104f4-114">For more information about these optional tasks, see [Manage dial-in conferencing in Skype for Business Server](../../manage/conferencing/dial-in-conferencing.md).</span></span>
  
- <span data-ttu-id="104f4-115">Gerenciar políticas de PIN para conferência discda</span><span class="sxs-lookup"><span data-stu-id="104f4-115">Manage PIN policies for dial-in conferencing</span></span>
    
- <span data-ttu-id="104f4-116">Gerenciar mapeamento de chaves para comandos DTMF</span><span class="sxs-lookup"><span data-stu-id="104f4-116">Manage key mapping for DTMF commands</span></span>
    
- <span data-ttu-id="104f4-117">Criar diretórios de conferência</span><span class="sxs-lookup"><span data-stu-id="104f4-117">Create conference directories</span></span>
    
- <span data-ttu-id="104f4-118">Gerenciar comunicados de junção e saída de conferência</span><span class="sxs-lookup"><span data-stu-id="104f4-118">Manage conference join and leave announcements</span></span>
    
- <span data-ttu-id="104f4-119">Testar configurações de conferência discagem</span><span class="sxs-lookup"><span data-stu-id="104f4-119">Test dial-in conferencing settings</span></span>
    
- <span data-ttu-id="104f4-120">Enviar emails de boas-vindas para usuários discado</span><span class="sxs-lookup"><span data-stu-id="104f4-120">Send welcome mail to dial-in users</span></span>
    
## <a name="configure-dial-plans"></a><span data-ttu-id="104f4-121">Configure planos de discagem</span><span class="sxs-lookup"><span data-stu-id="104f4-121">Configure dial plans</span></span>
<span data-ttu-id="104f4-122"><a name="BKMK_ConfigureDialPlans"> </a></span><span class="sxs-lookup"><span data-stu-id="104f4-122"><a name="BKMK_ConfigureDialPlans"> </a></span></span>

<span data-ttu-id="104f4-123">Quando você implanta a conferência discada, precisa criar ou modificar um ou mais planos de discagem para o roteamento de números de telefone de acesso de discagem.</span><span class="sxs-lookup"><span data-stu-id="104f4-123">When you deploy dial-in conferencing, you need to create or modify one or more dial plans for routing dial-in access phone numbers.</span></span> <span data-ttu-id="104f4-124">Você também deve garantir que cada plano de discagem contenha pelo menos uma regra de normalização, uma regra que converte extensões telefônicas em números de telefone completos no formato E.164.</span><span class="sxs-lookup"><span data-stu-id="104f4-124">You must also make sure that each dial plan contains at least one normalization rule--a rule that converts telephone extensions into complete phone numbers in E.164 format.</span></span> 
  
<span data-ttu-id="104f4-125">Os usuários da conferência discada ingressam em conferências como usuários corporativos autenticados, digitando seu PIN (número de identificação pessoal) e seu número de telefone.</span><span class="sxs-lookup"><span data-stu-id="104f4-125">Users of dial-in conferencing join conferences as authenticated enterprise users by entering their personal identification number (PIN) and their phone number.</span></span> <span data-ttu-id="104f4-126">Você precisa de uma regra de normalização para converter ramais em números de telefone completos, de forma que os usuários possam ser autenticados ao inserir somente um ramal telefônico.</span><span class="sxs-lookup"><span data-stu-id="104f4-126">You need a normalization rule to convert extensions into complete phone numbers so that users can be authenticated when they enter just a telephone extension.</span></span>
  
<span data-ttu-id="104f4-127">Para configurar planos de discagem para conferência discagem:</span><span class="sxs-lookup"><span data-stu-id="104f4-127">To set up dial plans for dial-in conferencing:</span></span>
  
- <span data-ttu-id="104f4-128">Se você implantar Enterprise Voice, modifique o plano de discagem global para adicionar uma região de conferência discada e certifique-se de que uma regra de normalização converta com precisão seus números de acesso discado.</span><span class="sxs-lookup"><span data-stu-id="104f4-128">Whether or not you deploy Enterprise Voice, modify the global dial plan to add a dial-in conferencing region and to make sure that a normalization rule accurately converts your dial-in access numbers.</span></span> <span data-ttu-id="104f4-129">Para obter instruções detalhadas, consulte [Create or modify a dial plan in Skype for Business Server](../../deploy/deploy-enterprise-voice/dial-plans.md).</span><span class="sxs-lookup"><span data-stu-id="104f4-129">For detailed instructions, see [Create or modify a dial plan in Skype for Business Server](../../deploy/deploy-enterprise-voice/dial-plans.md).</span></span>
    
- <span data-ttu-id="104f4-130">Se você não implantou Enterprise Voice, crie planos de discagem para seus números de acesso de conferência discado.</span><span class="sxs-lookup"><span data-stu-id="104f4-130">If you did not deploy Enterprise Voice, create dial plans for your dial-in conferencing access numbers.</span></span> <span data-ttu-id="104f4-131">Certifique-se de incluir uma região de conferência discada.</span><span class="sxs-lookup"><span data-stu-id="104f4-131">Be sure to include a dial-in conferencing region.</span></span> <span data-ttu-id="104f4-132">Para obter instruções detalhadas, consulte [Create or modify a dial plan in Skype for Business Server](../../deploy/deploy-enterprise-voice/dial-plans.md).</span><span class="sxs-lookup"><span data-stu-id="104f4-132">For detailed instructions, see [Create or modify a dial plan in Skype for Business Server](../../deploy/deploy-enterprise-voice/dial-plans.md).</span></span>
    
- <span data-ttu-id="104f4-133">Se você implantou Enterprise Voice, modifique Enterprise Voice de discagem conforme necessário para incluir regiões e use regras de normalização apropriadas para números de acesso discado.</span><span class="sxs-lookup"><span data-stu-id="104f4-133">If you deployed Enterprise Voice, modify Enterprise Voice dial plans as necessary to include regions and use appropriate normalization rules for dial-in access numbers.</span></span> <span data-ttu-id="104f4-134">Você também pode criar planos de discagem dedicados, usados somente para números de acesso de discagem.</span><span class="sxs-lookup"><span data-stu-id="104f4-134">You can also create dedicated dial plans that are used only for dial-in access numbers.</span></span> <span data-ttu-id="104f4-135">Para obter instruções detalhadas, consulte [Create or modify a dial plan in Skype for Business Server](../../deploy/deploy-enterprise-voice/dial-plans.md).</span><span class="sxs-lookup"><span data-stu-id="104f4-135">For detailed instructions, see [Create or modify a dial plan in Skype for Business Server](../../deploy/deploy-enterprise-voice/dial-plans.md).</span></span>
    
<span data-ttu-id="104f4-136">Para obter detalhes sobre como criar regras de normalização, consulte [Create or modify a normalization rule in Skype for Business](../../deploy/deploy-enterprise-voice/normalization-rules.md).</span><span class="sxs-lookup"><span data-stu-id="104f4-136">For details about creating normalization rules, see [Create or modify a normalization rule in Skype for Business](../../deploy/deploy-enterprise-voice/normalization-rules.md).</span></span>
  
## <a name="configure-dial-in-conferencing-regions"></a><span data-ttu-id="104f4-137">Configurar regiões de conferência discadas</span><span class="sxs-lookup"><span data-stu-id="104f4-137">Configure dial-in conferencing regions</span></span>
<span data-ttu-id="104f4-138"><a name="BKMK_ConfigureDialInRegions"> </a></span><span class="sxs-lookup"><span data-stu-id="104f4-138"><a name="BKMK_ConfigureDialInRegions"> </a></span></span>

<span data-ttu-id="104f4-139">Ao configurar um plano de discagem, especifique a região de conferência discada que se aplica ao plano de discagem.</span><span class="sxs-lookup"><span data-stu-id="104f4-139">When you set up a dial plan, you specify the dial-in conferencing region that applies to that dial plan.</span></span> <span data-ttu-id="104f4-140">A região de conferência discagem associa números de acesso de conferência discado ao plano de discagem apropriado.</span><span class="sxs-lookup"><span data-stu-id="104f4-140">The dial-in conferencing region associates dial-in conferencing access numbers with the appropriate dial plan.</span></span> <span data-ttu-id="104f4-141">Ao criar o número de acesso discado, selecione as regiões que associam o número de acesso aos planos de discagem apropriados.</span><span class="sxs-lookup"><span data-stu-id="104f4-141">When you create the dial-in access number, you select the regions that associate the access number with the appropriate dial plans.</span></span> 
  
<span data-ttu-id="104f4-142">Como é importante especificar uma região para todos os planos de discagem, recomendamos verificar se todos os planos de discagem têm regiões de conferência.</span><span class="sxs-lookup"><span data-stu-id="104f4-142">Because it important to specify a region for all dial plans, we recommend that you verify that all dial plans have conferencing regions.</span></span> 
  
<span data-ttu-id="104f4-143">Para verificar se a região está definida para todos os planos de discagem de conferência discada, use o cmdlet **Get-CsDialPlan.**</span><span class="sxs-lookup"><span data-stu-id="104f4-143">To verify whether the region is set for all dial-in conferencing dial plans, use the **Get-CsDialPlan** cmdlet.</span></span> <span data-ttu-id="104f4-144">Se a região não existir nos planos de discagem, você poderá usar o cmdlet **Set-CsDialPlan** para defini-la.</span><span class="sxs-lookup"><span data-stu-id="104f4-144">If the region is missing from dial plans, you can use the **Set-CsDialPlan** cmdlet to set the region.</span></span> <span data-ttu-id="104f4-145">Você também pode usar o Painel de Controle do Skype for Business Server para atualizar a região em planos de discagem existentes.</span><span class="sxs-lookup"><span data-stu-id="104f4-145">You can also use Skype for Business Server Control Panel to update the region in existing dial plans.</span></span> <span data-ttu-id="104f4-146">Para obter detalhes sobre como usar o Painel de Controle do Skype for Business Server, consulte [Create or modify a dial plan in Skype for Business Server](../../deploy/deploy-enterprise-voice/dial-plans.md).</span><span class="sxs-lookup"><span data-stu-id="104f4-146">For details about using Skype for Business Server Control Panel, see [Create or modify a dial plan in Skype for Business Server](../../deploy/deploy-enterprise-voice/dial-plans.md).</span></span>
  
### <a name="to-verify-whether-dial-plans-have-the-region-property-set"></a><span data-ttu-id="104f4-147">Para verificar se os planos de discagem têm a propriedade de região definida</span><span class="sxs-lookup"><span data-stu-id="104f4-147">To verify whether dial plans have the region property set</span></span>

1. <span data-ttu-id="104f4-148">Efetue logon no computador como membro do grupo RTCUniversalServerAdmins ou como membro da função **Cs-VoiceAdministrator**, **Cs-ServerAdministrator** ou **CsAdministrator**.</span><span class="sxs-lookup"><span data-stu-id="104f4-148">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the **Cs-VoiceAdministrator**, **Cs-ServerAdministrator**, or **CsAdministrator** role.</span></span>
    
2. <span data-ttu-id="104f4-149">Inicie o Shell de Gerenciamento do Skype for Business Server: clique em **Iniciar,** em Todos os **Programas,** em **Skype for Business 2015** e em Shell de Gerenciamento do **Skype for Business Server.**</span><span class="sxs-lookup"><span data-stu-id="104f4-149">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="104f4-150">Execute o seguinte no prompt de comando:</span><span class="sxs-lookup"><span data-stu-id="104f4-150">Run the following at the command prompt:</span></span>
    
   ```powershell
   Get-CsDialPlan [-Identity <Identifier of the dial plans to be retrieved>]
   ```

   <span data-ttu-id="104f4-151">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="104f4-151">For example:</span></span>
    
   ```powershell
   Get-CsDialPlan
   ```

   <span data-ttu-id="104f4-152">Neste exemplo, todos os planos de discagem configurados para sua organização são retornados.</span><span class="sxs-lookup"><span data-stu-id="104f4-152">In this example, all the dial plans configured for your organization are returned.</span></span>
    
4. <span data-ttu-id="104f4-153">Revise os planos de discagem retornados para identificar todos que estão faltando na região da conferência discada.</span><span class="sxs-lookup"><span data-stu-id="104f4-153">Review the returned dial plans to identify any that are missing the dial-in conferencing region.</span></span> 
    
<span data-ttu-id="104f4-154">Para obter mais informações, [consulte Get-CsDialPlan](/powershell/module/skype/get-csdialplan?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="104f4-154">For more information, see [Get-CsDialPlan](/powershell/module/skype/get-csdialplan?view=skype-ps).</span></span>
  
### <a name="to-set-the-region-property-for-a-dial-plan"></a><span data-ttu-id="104f4-155">Para definir a propriedade de região de um plano de discagem</span><span class="sxs-lookup"><span data-stu-id="104f4-155">To set the region property for a dial plan</span></span>

1. <span data-ttu-id="104f4-156">Efetue logon no computador como membro do grupo RTCUniversalServerAdmins ou como membro da função **Cs-VoiceAdministrator**, **Cs-ServerAdministrator** ou **CsAdministrator**.</span><span class="sxs-lookup"><span data-stu-id="104f4-156">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the **Cs-VoiceAdministrator**, **Cs-ServerAdministrator**, or **CsAdministrator** role.</span></span>
    
2. <span data-ttu-id="104f4-157">Inicie o Shell de Gerenciamento do Skype for Business Server: clique em **Iniciar,** em Todos os **Programas,** em **Skype for Business 2015** e em Shell de Gerenciamento do **Skype for Business Server.**</span><span class="sxs-lookup"><span data-stu-id="104f4-157">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="104f4-158">Para todos os planos de discagem que não têm a região de conferência discada, execute:</span><span class="sxs-lookup"><span data-stu-id="104f4-158">For any dial plans that are missing the dial-in conferencing region, run:</span></span>
    
   ```powershell
   Set-CsDialPlan [-Identity <Identity of the dial plan to be modified>] -DialinConferencingRegion "<new region>"
   ```

   <span data-ttu-id="104f4-159">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="104f4-159">For example:</span></span>
    
   ```powershell
   Set-CsDialPlan -Identity Redmond -DialinConferencingRegion "US West Coast"
   ```

   <span data-ttu-id="104f4-160">Neste exemplo, o plano de discagem com Identidade de Redmond é modificado para definir a propriedade DialinConferencingRegion como "Costa Leste dos EUA".</span><span class="sxs-lookup"><span data-stu-id="104f4-160">In this example, the dial plan with the Identity of Redmond is modified to set the DialinConferencingRegion property to "US West Coast".</span></span> 
    
<span data-ttu-id="104f4-161">Para obter mais informações, [consulte Set-CsDialPlan](/powershell/module/skype/set-csdialplan?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="104f4-161">For more information, see [Set-CsDialPlan](/powershell/module/skype/set-csdialplan?view=skype-ps).</span></span>
  
## <a name="configure-dial-in-access-numbers"></a><span data-ttu-id="104f4-162">Configure números de acesso de discagem</span><span class="sxs-lookup"><span data-stu-id="104f4-162">Configure dial-in access numbers</span></span>
<span data-ttu-id="104f4-163"><a name="BKMK_ConfigureDialInAccessNumbers"> </a></span><span class="sxs-lookup"><span data-stu-id="104f4-163"><a name="BKMK_ConfigureDialInAccessNumbers"> </a></span></span>

<span data-ttu-id="104f4-p110">Ao implantar uma conferência discada, você precisa configurar números de telefone que os usuários poderão discar da PSTN para participar da parte de áudio das conferências. Esses números de acesso de discagem aparecem nos convites de reunião e na página Configurações de Conferência Discada.</span><span class="sxs-lookup"><span data-stu-id="104f4-p110">When you deploy dial-in conferencing, you need to set up phone numbers that users can dial from the public switched telephone network (PSTN) to join the audio portion of conferences. These dial-in access numbers appear in meeting invitations and on the Dial-in Conferencing Settings webpage.</span></span>
  
<span data-ttu-id="104f4-166">Antes de criar números de acesso discado, primeiro você precisa planejar as regiões de conferência discada e, em seguida, configurar os planos de discagem nas regiões.</span><span class="sxs-lookup"><span data-stu-id="104f4-166">Before you can create dial-in access numbers, you must first plan your dial-in conferencing regions and then configure dial plans with the regions.</span></span> <span data-ttu-id="104f4-167">Para obter detalhes sobre regiões, consulte [Plan for dial-in conferencing in Skype for Business Server](../../plan-your-deployment/conferencing/dial-in-conferencing.md).</span><span class="sxs-lookup"><span data-stu-id="104f4-167">For details about regions, see [Plan for dial-in conferencing in Skype for Business Server](../../plan-your-deployment/conferencing/dial-in-conferencing.md).</span></span> <span data-ttu-id="104f4-168">Para obter detalhes sobre como configurar planos de discagem para conferência discada, consulte [Create or modify a dial plan in Skype for Business Server](../../deploy/deploy-enterprise-voice/dial-plans.md).</span><span class="sxs-lookup"><span data-stu-id="104f4-168">For details about configuring dial plans for dial-in conferencing, see [Create or modify a dial plan in Skype for Business Server](../../deploy/deploy-enterprise-voice/dial-plans.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="104f4-169">Não é possível usar um novo número de acesso discado até que a replicação dos Serviços de Domínio do Active Directory (AD DS) desse número de acesso seja concluída.</span><span class="sxs-lookup"><span data-stu-id="104f4-169">You cannot use a new dial-in access number until Active Directory Domain Services (AD DS) replication of that access number is complete.</span></span> <span data-ttu-id="104f4-170">A replicação pode demorar algumas horas para ser concluída.</span><span class="sxs-lookup"><span data-stu-id="104f4-170">Replication can take several hours to complete.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="104f4-171">Após a criação dos números de acesso discado, é possível modificar o nome de exibição dos objetos de contato do Active Directory de modo que os usuários possam identificar com mais facilidade o número de acesso correto.</span><span class="sxs-lookup"><span data-stu-id="104f4-171">After you create dial-in access numbers, you can modify the display name for the Active Directory contact objects so that users can more easily identify the correct access number.</span></span> <span data-ttu-id="104f4-172">Para modificar o nome de exibição, use o cmdlet [Set-CsDialInConferencingAccessNumber.](/powershell/module/skype/set-csdialinconferencingaccessnumber?view=skype-ps)</span><span class="sxs-lookup"><span data-stu-id="104f4-172">To modify the display name, use the [Set-CsDialInConferencingAccessNumber](/powershell/module/skype/set-csdialinconferencingaccessnumber?view=skype-ps) cmdlet.</span></span> <span data-ttu-id="104f4-173">Não modifique os objetos do Active Directory manualmente.</span><span class="sxs-lookup"><span data-stu-id="104f4-173">You should not modify Active Directory objects manually.</span></span>
  
### <a name="to-create-a-dial-in-access-number"></a><span data-ttu-id="104f4-174">Para criar um número de acesso discado</span><span class="sxs-lookup"><span data-stu-id="104f4-174">To create a dial-in access number</span></span>

1. <span data-ttu-id="104f4-175">Por uma conta de usuário atribuída à função CsUserAdministrator role ou CsAdministrator, faça o login em qualquer computador na sua implantação interna.</span><span class="sxs-lookup"><span data-stu-id="104f4-175">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="104f4-176">Abra o Painel de Controle do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="104f4-176">Open Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="104f4-177">Na barra de navegação da esquerda, clique em **Conferência**, depois clique em **Número de Acesso de Discagem**.</span><span class="sxs-lookup"><span data-stu-id="104f4-177">In the left navigation bar, click **Conferencing** and then click **Dial-in Access Number**.</span></span>
    
4. <span data-ttu-id="104f4-178">Na página **Número de Acesso de Discagem**, realize uma das ações a seguir:</span><span class="sxs-lookup"><span data-stu-id="104f4-178">On the **Dial-in Access Number** page, do one of the following:</span></span>
    
   - <span data-ttu-id="104f4-179">Clique em **Novo** para abrir **Novo Número de Acesso de Discagem**.</span><span class="sxs-lookup"><span data-stu-id="104f4-179">Click **New** to open **New Dial-in Access Number**.</span></span>
    
   - <span data-ttu-id="104f4-180">Clique em um dos números de acesso de discagem na lista, clique em **Editar**, e clique em **Mostrar detalhes**.</span><span class="sxs-lookup"><span data-stu-id="104f4-180">Click one of the dial-in access numbers in the list, click **Edit**, and then click **Show details**.</span></span>
    
     > [!NOTE]
     > <span data-ttu-id="104f4-p114">Usar o campo de busca para buscar pelos conteúdos de uma coluna na lista de números de acesso de discagem pode não apresentar os resultados esperados. Em vez disso, classifique a lista pela coluna de interesse para identificar o número de acesso de discagem a ser visualizado ou modificado.</span><span class="sxs-lookup"><span data-stu-id="104f4-p114">Using the search field to search for the contents of a column in the list of dial-in access numbers may not yield the results you expect. Instead, sort the list by the column of interest to identify the dial-in access number you want to view or change.</span></span> 
  
5. <span data-ttu-id="104f4-183">Em **Número para exibição**, digite o número de telefone que os usuários de telefone da rede telefônica pública comutada (PSTN) digitam para participar de uma conferência.</span><span class="sxs-lookup"><span data-stu-id="104f4-183">In **Display number**, type the phone number that public switched telephone network (PSTN) phone users dial to join a conference.</span></span> <span data-ttu-id="104f4-184">Esse número é exibido em convites de reunião e na página da Web de Configurações de Conferência Discada.</span><span class="sxs-lookup"><span data-stu-id="104f4-184">This number is displayed in meeting invitations and on the Dial-in Conferencing Settings webpage.</span></span>
    
6. <span data-ttu-id="104f4-185">Em **Nome para exibição**, digite uma descrição para o número de acesso de discagem.</span><span class="sxs-lookup"><span data-stu-id="104f4-185">In **Display name**, type a description for the dial-in access number.</span></span> <span data-ttu-id="104f4-186">Esse é o nome associado ao número de acesso discado nos resultados da pesquisa do Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="104f4-186">This is the name that is associated with the dial-in access number in Skype for Business search results.</span></span> <span data-ttu-id="104f4-187">Esse nome é exibido no cliente quando um usuário disca o número de acesso.</span><span class="sxs-lookup"><span data-stu-id="104f4-187">This name is displayed in the client when a user calls the access number.</span></span> 
    
7. <span data-ttu-id="104f4-p117">Em **URI da Linha**, digite o número E.164 do número de acesso de discagem em formato TEL URI, incluindo o símbolo + antes do número e excluindo espaços. Por exemplo, tel:+14255550200.</span><span class="sxs-lookup"><span data-stu-id="104f4-p117">In **Line URI**, type the E.164 number of the dial-in access number in TEL URI format, including the + symbol before the number and excluding spaces. For example, tel:+14255550200.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="104f4-190">O mesmo URI de Linha não pode ser reusada por outro número de acesso de conferência discada.</span><span class="sxs-lookup"><span data-stu-id="104f4-190">The same Line URI cannot be reused by another dial-in conferencing access number.</span></span> 
  
8. <span data-ttu-id="104f4-191">Em **URI do SIP**, faça o seguinte:</span><span class="sxs-lookup"><span data-stu-id="104f4-191">In **SIP URI**, do the following:</span></span>
    
   - <span data-ttu-id="104f4-192">Na caixa de texto, digite um único URI do SIP para o número de acesso de conferência discada.</span><span class="sxs-lookup"><span data-stu-id="104f4-192">In the text box, type a unique SIP URI for this dial-in conferencing access number.</span></span> <span data-ttu-id="104f4-193">Esse URI SIP é exibido em vários locais, incluindo, mas não se limitando a mensagens de notificação de chamada e versões anteriores de clientes do Lync.</span><span class="sxs-lookup"><span data-stu-id="104f4-193">This SIP URI is displayed in various locations including, but not limited to, call notification messages and previous versions of Lync clients.</span></span>
    
     > [!NOTE]
     > <span data-ttu-id="104f4-p119">O mesmo URI do SIP não pode ser reusado por outro número de acesso de conferência discada. O URI do SIP não pode ser modificado depois de o número de acesso ter sido criado. A única maneira de altera o URI do SIP é excluir e recriar o número de acesso.</span><span class="sxs-lookup"><span data-stu-id="104f4-p119">The same SIP URI cannot be reused by another dial-in conferencing access number. The SIP URI cannot be modified after the access number is created. The only way to change the SIP URI is to delete and recreate the access number.</span></span> 
  
   - <span data-ttu-id="104f4-197">Na caixa lista listada, clique no domínio do aplicativo Atendedor de Conferência que oferece suporte a esse número de acesso discado.</span><span class="sxs-lookup"><span data-stu-id="104f4-197">In the drop-down list box, click the domain of the Conferencing Attendant application that supports this dial-in access number.</span></span>
    
9. <span data-ttu-id="104f4-198">Em **Pool**, clique no pool que está executado a instância Atendedor de Conferência que dá suporte ao número de acesso de discagem.</span><span class="sxs-lookup"><span data-stu-id="104f4-198">In **Pool**, click the pool that is running the instance of Conferencing Attendant that supports this dial-in access number.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="104f4-199">Se foi preciso alterar o pool depois de criar o número de acesso, deve-se usar o cmdlet do [Move-CsApplicationEndpoint](/powershell/module/skype/move-csapplicationendpoint?view=skype-ps) cmdlet ou excluir e recriar o número de acesso.</span><span class="sxs-lookup"><span data-stu-id="104f4-199">If you need to change the pool after you create the access number, you must use the [Move-CsApplicationEndpoint](/powershell/module/skype/move-csapplicationendpoint?view=skype-ps) cmdlet or delete and recreate the access number.</span></span>
  
10. <span data-ttu-id="104f4-200">Em **Idioma principal**, clique no idioma no qual as solicitações são reproduzidas nesse número de acesso.</span><span class="sxs-lookup"><span data-stu-id="104f4-200">In **Primary language**, click the language in which prompts are played for this dial-in access number.</span></span> 
    
    <span data-ttu-id="104f4-p120">O idioma principal é o idioma que o Atendente de Conferência usa para atender a ligação. Os idiomas suportados são exibidos ao lado de cada número de acesso de discagem na página da Web das Configurações de Conferência Discada.</span><span class="sxs-lookup"><span data-stu-id="104f4-p120">The primary language is the language that the Conferencing Attendant uses to answer the call. Supported languages are displayed alongside each access phone number on the Dial-in Conferencing Settings webpage.</span></span>
    
11. <span data-ttu-id="104f4-203">(Opcional) Em **Idiomas secundários (máximo de quatro)**, clique em **Adicionar**, selecione um ou mais idiomas adicionais que você quer oferecer aos chamadores para esse número de acesso de discagem, e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="104f4-203">(Optional) In **Secondary languages (maximum of four)**, click **Add**, select one or more additional languages that you want to support for callers to this dial-in access number, and then click **OK**.</span></span> 
    
    <span data-ttu-id="104f4-p121">É possível escolher até quatro idiomas secundários para cada número de acesso de discagem. Os usuários podem selecionar um idioma secundário antes de inserir o ID de conferência ao ligarem para uma.</span><span class="sxs-lookup"><span data-stu-id="104f4-p121">You can choose up to four secondary languages for each dial-in access number. Users can select a secondary language before entering the conference ID when they dial in to a conference.</span></span>
    
12. <span data-ttu-id="104f4-206">Para adicionar uma região para o número de acesso de discagem, em Regiões Associadas, clique em Adicionar **,** clique em uma ou mais regiões associadas aos planos de discagem para esse número de acesso de discagem e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="104f4-206">To add a region for the dial-in access number, under **Associated regions**, click **Add**, click one or more regions that are associated with the dial plans for this dial-in access number, and then click **OK**.</span></span>
    
13. <span data-ttu-id="104f4-207">Para excluir uma região do número de acesso de discagem, em **Regiões Associadas**, clique na região a ser excluída e clique em **Remover**.</span><span class="sxs-lookup"><span data-stu-id="104f4-207">To delete a region from the dial-in access number, under **Associated regions**, click the region you want to delete, and then click **Remove**.</span></span>
    
14. <span data-ttu-id="104f4-208">Clique em **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="104f4-208">Click **Commit**.</span></span>
    
## <a name="configure-conferencing-policies"></a><span data-ttu-id="104f4-209">Configurar políticas de conferência</span><span class="sxs-lookup"><span data-stu-id="104f4-209">Configure conferencing policies</span></span>
<span data-ttu-id="104f4-210"><a name="BKMK_ConfigureConferencingPolicies"> </a></span><span class="sxs-lookup"><span data-stu-id="104f4-210"><a name="BKMK_ConfigureConferencingPolicies"> </a></span></span>

<span data-ttu-id="104f4-p122">A política de conferência é uma configuração de conta de usuário que especifica a experiência de conferência para os participantes. Você pode criar políticas de conferência com um escopo de site ou um escopo de usuário. As configurações de política de conferência englobam vários aspectos do agendamento da conferência e da participação. Várias configurações de política de conferência oferecem suporte à conferência discada para participantes. Ao configurar a conferência discada, você deve verificar se estes campos foram definidos adequadamente para sua organização e modificá-los conforme necessário.</span><span class="sxs-lookup"><span data-stu-id="104f4-p122">Conferencing policy is a user account setting that specifies the conferencing experience for participants. You can create conferencing policies with a site scope or a user scope. Conferencing policy settings encompass many aspects of conference scheduling and participation. Several conferencing policy settings support dial-in conferencing for participants. When you configure dial-in conferencing, you should verify that these fields are set appropriately for your organization, and modify them as necessary.</span></span> 
  
<span data-ttu-id="104f4-216">Para obter mais informações sobre como configurar políticas de conferência, consulte [Manage conferencing policies in Skype for Business Server](../../manage/conferencing/conferencing-policies.md).</span><span class="sxs-lookup"><span data-stu-id="104f4-216">For more information about configuring conferencing policies, see [Manage conferencing policies in Skype for Business Server](../../manage/conferencing/conferencing-policies.md).</span></span>
  
## <a name="assign-a-line-uri-to-a-user-account"></a><span data-ttu-id="104f4-217">Atribuir um URI de linha a uma conta de usuário</span><span class="sxs-lookup"><span data-stu-id="104f4-217">Assign a Line URI to a user account</span></span>
<span data-ttu-id="104f4-218"><a name="BKMK_AssignaLineURI"> </a></span><span class="sxs-lookup"><span data-stu-id="104f4-218"><a name="BKMK_AssignaLineURI"> </a></span></span>

<span data-ttu-id="104f4-219">Os usuários de discagem digitam o número de telefone ou a extensão e um PIN para ingressar nas conferências como usuários autenticados.</span><span class="sxs-lookup"><span data-stu-id="104f4-219">Dial-in users enter their phone number or extension and a PIN to join conferences as authenticated users.</span></span> <span data-ttu-id="104f4-220">O **URI de linha de** telefonia especificado nas contas de usuário do Skype for Business Server é necessária para autenticação.</span><span class="sxs-lookup"><span data-stu-id="104f4-220">The telephony **Line URI** specified on Skype for Business Server user accounts is required for authentication.</span></span>
  
<span data-ttu-id="104f4-221">O procedimento neste tópico descreve como atribuir um **URI de Linha** para uma única conta de usuário.</span><span class="sxs-lookup"><span data-stu-id="104f4-221">The procedure in this topic describes how to assign a **Line URI** for a single user account.</span></span> <span data-ttu-id="104f4-222">Se você precisar atribuir um **URI da Linha** para várias contas de usuário, poderá criar um script que usa o cmdlet **Set-CsUser**.</span><span class="sxs-lookup"><span data-stu-id="104f4-222">If you need to assign a **Line URI** for multiple user accounts, you can create a script that uses the **Set-CsUser** cmdlet.</span></span> <span data-ttu-id="104f4-223">Para obter detalhes sobre como usar um script de exemplo para atribuir **URI** de linha a várias contas de usuário, consulte [Assign Line URIs to Multiple Users](https://go.microsoft.com/fwlink/p/?linkId=196945).</span><span class="sxs-lookup"><span data-stu-id="104f4-223">For details about using a sample script to assign **Line URI** to multiple user accounts, see [Assign Line URIs to Multiple Users](https://go.microsoft.com/fwlink/p/?linkId=196945).</span></span>
  
1. <span data-ttu-id="104f4-224">Faça logon no computador como membro do grupo RTCUniversalServerAdmins ou como membro da função **Cs-UserAdministrator** ou **CsAdministrator**.</span><span class="sxs-lookup"><span data-stu-id="104f4-224">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the **Cs-UserAdministrator** or **CsAdministrator** role.</span></span>
    
2.  <span data-ttu-id="104f4-225">Abra o Painel de Controle do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="104f4-225">Open Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="104f4-226">Na barra de navegação esquerda, clique em **Usuários**.</span><span class="sxs-lookup"><span data-stu-id="104f4-226">In the left navigation bar, click **Users**.</span></span>
    
4. <span data-ttu-id="104f4-227">No campo de pesquisa, digite o nome do usuário que você deseja configurar para conferência discada ou clique em **Adicionar filtro** para especificar os campos de pesquisa e clique em **Localizar**.</span><span class="sxs-lookup"><span data-stu-id="104f4-227">In the search field, type the name of the user you want to configure for dial-in conferencing or click **Add filter** to specify search fields, and then click **Find**.</span></span>
    
5. <span data-ttu-id="104f4-228">Clique duas vezes no nome de usuário para abrir a caixa **de diálogo Editar Usuário do Skype for Business Server.**</span><span class="sxs-lookup"><span data-stu-id="104f4-228">Double-click the user name to open the **Edit Skype for Business Server User** dialog box.</span></span>
    
6. <span data-ttu-id="104f4-229">Em **Telefonia**, no campo **URI da Linha**, digite um número de telefone exclusivo e normalizado (por exemplo, tel:+14255550200).</span><span class="sxs-lookup"><span data-stu-id="104f4-229">Under **Telephony**, in the **Line URI** field, type a unique, normalized phone number (for example, tel:+14255550200).</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="104f4-230">Você só poderá especificar  **o URI** de linha se a Telefonia estiver definida como **pc-para-pc** somente **,** **Enterprise Voice,** controle de chamada remota ou controle de chamada **remota somente**.</span><span class="sxs-lookup"><span data-stu-id="104f4-230">You can specify **Line URI** only if **Telephony** is set to **PC-to-PC only**, **Enterprise Voice**, **Remote call control** or **Remote call control only**.</span></span> 
  
7. <span data-ttu-id="104f4-231">Clique em **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="104f4-231">Click **Commit**.</span></span>
