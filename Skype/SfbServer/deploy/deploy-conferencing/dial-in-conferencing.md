---
title: Configurar a conferência discada no Skype para Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 38d9f168-80b8-46f2-a1c0-becd84e58e73
description: 'Resumo: Leia este tópico para saber como configurar a conferência discada no Skype para Business Server.'
ms.openlocfilehash: e523c454ed54158ab617d8aa87592614954f32e8
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "33895002"
---
# <a name="configure-dial-in-conferencing-in-skype-for-business-server"></a><span data-ttu-id="b18bc-103">Configurar a conferência discada no Skype para Business Server</span><span class="sxs-lookup"><span data-stu-id="b18bc-103">Configure dial-in conferencing in Skype for Business Server</span></span>
 
<span data-ttu-id="b18bc-104">**Resumo:** Leia este tópico para saber como configurar a conferência discada no Skype para Business Server.</span><span class="sxs-lookup"><span data-stu-id="b18bc-104">**Summary:** Read this topic to learn how to configure dial-in conferencing in Skype for Business Server.</span></span>
  
<span data-ttu-id="b18bc-105">Após ter criado uma topologia que inclua a carga de trabalho de conferência e a conferência discada selecionada, você deve executar etapas adicionais para configurar a conferência discada.</span><span class="sxs-lookup"><span data-stu-id="b18bc-105">After you have created a topology that includes the conferencing workload and selected dial-in conferencing, you must perform additional steps to configure dial-in conferencing.</span></span> <span data-ttu-id="b18bc-106">Antes que você leia este tópico, certifique-se você leu [Planejar a conferência discada no Skype para Business Server](../../plan-your-deployment/conferencing/dial-in-conferencing.md), [requisitos de Hardware e software para conferências no Skype para Business Server](../../plan-your-deployment/conferencing/hardware-and-software-requirements.md)e o fluxograma de implantação de [e lista de verificação para conferência discada](deploy-conferencing.md#deployment-flowchart-and-checklist-for-dial-in-conferencing).</span><span class="sxs-lookup"><span data-stu-id="b18bc-106">Before you read this topic, be sure you have read [Plan for dial-in conferencing in Skype for Business Server](../../plan-your-deployment/conferencing/dial-in-conferencing.md), [Hardware and software requirements for conferencing in Skype for Business Server](../../plan-your-deployment/conferencing/hardware-and-software-requirements.md), and the [Deployment flowchart and checklist for dial-in conferencing](deploy-conferencing.md#deployment-flowchart-and-checklist-for-dial-in-conferencing).</span></span> 
  
<span data-ttu-id="b18bc-107">Para configurar a conferência discada, você deve executar as seguintes tarefas:</span><span class="sxs-lookup"><span data-stu-id="b18bc-107">To configure dial-in conferencing, you must perform the following tasks:</span></span>
  
- [<span data-ttu-id="b18bc-108">Configure dial plans</span><span class="sxs-lookup"><span data-stu-id="b18bc-108">Configure dial plans</span></span>](dial-in-conferencing.md#BKMK_ConfigureDialPlans)
    
- [<span data-ttu-id="b18bc-109">Configure dial-in conferencing regions</span><span class="sxs-lookup"><span data-stu-id="b18bc-109">Configure dial-in conferencing regions</span></span>](dial-in-conferencing.md#BKMK_ConfigureDialInRegions)
    
- [<span data-ttu-id="b18bc-110">Configure dial-in access numbers</span><span class="sxs-lookup"><span data-stu-id="b18bc-110">Configure dial-in access numbers</span></span>](dial-in-conferencing.md#BKMK_ConfigureDialInAccessNumbers)
    
- [<span data-ttu-id="b18bc-111">Configure conferencing policies</span><span class="sxs-lookup"><span data-stu-id="b18bc-111">Configure conferencing policies</span></span>](dial-in-conferencing.md#BKMK_ConfigureConferencingPolicies)
    
- [<span data-ttu-id="b18bc-112">Assign a Line URI to a user account</span><span class="sxs-lookup"><span data-stu-id="b18bc-112">Assign a Line URI to a user account</span></span>](dial-in-conferencing.md#BKMK_AssignaLineURI)
    
<span data-ttu-id="b18bc-113">Além disso, você pode executar as seguintes tarefas opcionais.</span><span class="sxs-lookup"><span data-stu-id="b18bc-113">In addition, you may perform the following optional tasks.</span></span> <span data-ttu-id="b18bc-114">Para obter mais informações sobre essas tarefas opcionais, consulte [Gerenciar a conferência discada no Skype para Business Server](../../manage/conferencing/dial-in-conferencing.md).</span><span class="sxs-lookup"><span data-stu-id="b18bc-114">For more information about these optional tasks, see [Manage dial-in conferencing in Skype for Business Server](../../manage/conferencing/dial-in-conferencing.md).</span></span>
  
- <span data-ttu-id="b18bc-115">Gerenciar políticas de PIN para conferência discada</span><span class="sxs-lookup"><span data-stu-id="b18bc-115">Manage PIN policies for dial-in conferencing</span></span>
    
- <span data-ttu-id="b18bc-116">Gerenciar mapeamento principal de comandos DTMF</span><span class="sxs-lookup"><span data-stu-id="b18bc-116">Manage key mapping for DTMF commands</span></span>
    
- <span data-ttu-id="b18bc-117">Criar diretórios de conferência</span><span class="sxs-lookup"><span data-stu-id="b18bc-117">Create conference directories</span></span>
    
- <span data-ttu-id="b18bc-118">Gerenciar o ingresso na conferência e anúncios de saída</span><span class="sxs-lookup"><span data-stu-id="b18bc-118">Manage conference join and leave announcements</span></span>
    
- <span data-ttu-id="b18bc-119">Testar configurações de conferência discada</span><span class="sxs-lookup"><span data-stu-id="b18bc-119">Test dial-in conferencing settings</span></span>
    
- <span data-ttu-id="b18bc-120">Enviar e-mail de boas-vindas para os usuários de discagem</span><span class="sxs-lookup"><span data-stu-id="b18bc-120">Send welcome mail to dial-in users</span></span>
    
## <a name="configure-dial-plans"></a><span data-ttu-id="b18bc-121">Configure planos de discagem</span><span class="sxs-lookup"><span data-stu-id="b18bc-121">Configure dial plans</span></span>
<span data-ttu-id="b18bc-122"><a name="BKMK_ConfigureDialPlans"> </a></span><span class="sxs-lookup"><span data-stu-id="b18bc-122"></span></span>

<span data-ttu-id="b18bc-123">Ao implantar a conferência discada, você precisa criar ou modificar um ou mais planos de discagem para o roteamento de números de telefone de acesso de discagem.</span><span class="sxs-lookup"><span data-stu-id="b18bc-123">When you deploy dial-in conferencing, you need to create or modify one or more dial plans for routing dial-in access phone numbers.</span></span> <span data-ttu-id="b18bc-124">Você deve também verificar se cada plano de discagem contém pelo menos uma regra de normalização – uma regra que converte ramais em números de telefone completos no formato e. 164.</span><span class="sxs-lookup"><span data-stu-id="b18bc-124">You must also make sure that each dial plan contains at least one normalization rule--a rule that converts telephone extensions into complete phone numbers in E.164 format.</span></span> 
  
<span data-ttu-id="b18bc-p104">Os usuários da conferência discada participam de conferências como usuários corporativos autenticados, digitando seu número de identificação pessoal (PIN) e seu número de telefone. Você precisa de uma regra de normalização para converter ramais em números de telefone completos, de forma que os usuários possam ser autenticados ao inserir somente um ramal telefônico.</span><span class="sxs-lookup"><span data-stu-id="b18bc-p104">Users of dial-in conferencing join conferences as authenticated enterprise users by entering their personal identification number (PIN) and their phone number. You need a normalization rule to convert extensions into complete phone numbers so that users can be authenticated when they enter just a telephone extension.</span></span>
  
<span data-ttu-id="b18bc-127">Para configurar planos de discagem para conferência discada:</span><span class="sxs-lookup"><span data-stu-id="b18bc-127">To set up dial plans for dial-in conferencing:</span></span>
  
- <span data-ttu-id="b18bc-128">Independente de implantar o Enterprise Voice, modifique o plano de discagem global para adicionar uma região de conferência discada e para garantir que uma regra de normalização converta seus números de acesso discado de modo preciso.</span><span class="sxs-lookup"><span data-stu-id="b18bc-128">Whether or not you deploy Enterprise Voice, modify the global dial plan to add a dial-in conferencing region and to make sure that a normalization rule accurately converts your dial-in access numbers.</span></span> <span data-ttu-id="b18bc-129">Para obter instruções detalhadas, consulte [criar ou modificar um plano de discagem no Skype para Business Server](../../deploy/deploy-enterprise-voice/dial-plans.md).</span><span class="sxs-lookup"><span data-stu-id="b18bc-129">For detailed instructions, see [Create or modify a dial plan in Skype for Business Server](../../deploy/deploy-enterprise-voice/dial-plans.md).</span></span>
    
- <span data-ttu-id="b18bc-130">Se você não implantou o Enterprise Voice, crie planos de discagem para todos os seus números de acesso de conferência discada.</span><span class="sxs-lookup"><span data-stu-id="b18bc-130">If you did not deploy Enterprise Voice, create dial plans for your dial-in conferencing access numbers.</span></span> <span data-ttu-id="b18bc-131">Certifique-se de incluir uma região de conferência discada.</span><span class="sxs-lookup"><span data-stu-id="b18bc-131">Be sure to include a dial-in conferencing region.</span></span> <span data-ttu-id="b18bc-132">Para obter instruções detalhadas, consulte [criar ou modificar um plano de discagem no Skype para Business Server](../../deploy/deploy-enterprise-voice/dial-plans.md).</span><span class="sxs-lookup"><span data-stu-id="b18bc-132">For detailed instructions, see [Create or modify a dial plan in Skype for Business Server](../../deploy/deploy-enterprise-voice/dial-plans.md).</span></span>
    
- <span data-ttu-id="b18bc-133">Se você implantou o Enterprise Voice, modifique os planos de discagem do Enterprise Voice conforme necessário para incluir regiões e usar regras de normalização apropriadas para números de acesso de discagem.</span><span class="sxs-lookup"><span data-stu-id="b18bc-133">If you deployed Enterprise Voice, modify Enterprise Voice dial plans as necessary to include regions and use appropriate normalization rules for dial-in access numbers.</span></span> <span data-ttu-id="b18bc-134">Você também pode criar planos de discagem dedicados, usados somente para números de acesso de discagem.</span><span class="sxs-lookup"><span data-stu-id="b18bc-134">You can also create dedicated dial plans that are used only for dial-in access numbers.</span></span> <span data-ttu-id="b18bc-135">Para obter instruções detalhadas, consulte [criar ou modificar um plano de discagem no Skype para Business Server](../../deploy/deploy-enterprise-voice/dial-plans.md).</span><span class="sxs-lookup"><span data-stu-id="b18bc-135">For detailed instructions, see [Create or modify a dial plan in Skype for Business Server](../../deploy/deploy-enterprise-voice/dial-plans.md).</span></span>
    
<span data-ttu-id="b18bc-136">Para obter detalhes sobre como criar regras de normalização, consulte [criar ou modificar uma regra de normalização no Skype para negócios](../../deploy/deploy-enterprise-voice/normalization-rules.md).</span><span class="sxs-lookup"><span data-stu-id="b18bc-136">For details about creating normalization rules, see [Create or modify a normalization rule in Skype for Business](../../deploy/deploy-enterprise-voice/normalization-rules.md).</span></span>
  
## <a name="configure-dial-in-conferencing-regions"></a><span data-ttu-id="b18bc-137">Configurar as regiões de conferência de discagem</span><span class="sxs-lookup"><span data-stu-id="b18bc-137">Configure dial-in conferencing regions</span></span>
<span data-ttu-id="b18bc-138"><a name="BKMK_ConfigureDialInRegions"> </a></span><span class="sxs-lookup"><span data-stu-id="b18bc-138"></span></span>

<span data-ttu-id="b18bc-p108">Ao configurar um plano de discagem, você especifica a região de conferência discada que se aplica ao plano de discagem. A região de conferência discada associa números de acesso de conferência discada ao plano de discagem apropriado. Ao criar o número de acesso de discagem, selecione as regiões que associam o número de acesso aos planos de discagem apropriados.</span><span class="sxs-lookup"><span data-stu-id="b18bc-p108">When you set up a dial plan, you specify the dial-in conferencing region that applies to that dial plan. The dial-in conferencing region associates dial-in conferencing access numbers with the appropriate dial plan. When you create the dial-in access number, you select the regions that associate the access number with the appropriate dial plans.</span></span> 
  
<span data-ttu-id="b18bc-142">Como é importante especificar uma região para todos os planos de discagem, recomendamos usar este procedimento para verificar se todos os planos de discagem têm regiões de conferência.</span><span class="sxs-lookup"><span data-stu-id="b18bc-142">Because it important to specify a region for all dial plans, we recommend that you verify that all dial plans have conferencing regions.</span></span> 
  
<span data-ttu-id="b18bc-143">Para verificar se a região está definida para todos os planos de discagem da conferência discada, use o cmdlet **Get-CsDialPlan**.</span><span class="sxs-lookup"><span data-stu-id="b18bc-143">To verify whether the region is set for all dial-in conferencing dial plans, use the **Get-CsDialPlan** cmdlet.</span></span> <span data-ttu-id="b18bc-144">Se a região não existir nos planos de discagem, você poderá usar o cmdlet **Set-CsDialPlan** para defini-la.</span><span class="sxs-lookup"><span data-stu-id="b18bc-144">If the region is missing from dial plans, you can use the **Set-CsDialPlan** cmdlet to set the region.</span></span> <span data-ttu-id="b18bc-145">Você também pode usar o Skype para painel de controle do Business Server para atualizar a região em planos de discagem existente.</span><span class="sxs-lookup"><span data-stu-id="b18bc-145">You can also use Skype for Business Server Control Panel to update the region in existing dial plans.</span></span> <span data-ttu-id="b18bc-146">Para obter detalhes sobre como usar o Skype para painel de controle do Business Server, consulte [criar ou modificar um plano de discagem no Skype para Business Server](../../deploy/deploy-enterprise-voice/dial-plans.md).</span><span class="sxs-lookup"><span data-stu-id="b18bc-146">For details about using Skype for Business Server Control Panel, see [Create or modify a dial plan in Skype for Business Server](../../deploy/deploy-enterprise-voice/dial-plans.md).</span></span>
  
### <a name="to-verify-whether-dial-plans-have-the-region-property-set"></a><span data-ttu-id="b18bc-147">Para verificar se os planos de discagem têm a propriedade de região definida</span><span class="sxs-lookup"><span data-stu-id="b18bc-147">To verify whether dial plans have the region property set</span></span>

1. <span data-ttu-id="b18bc-148">Efetue logon no computador como membro do grupo RTCUniversalServerAdmins ou como membro da função **Cs-VoiceAdministrator**, **Cs-ServerAdministrator**ou **CsAdministrator**.</span><span class="sxs-lookup"><span data-stu-id="b18bc-148">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the **Cs-VoiceAdministrator**, **Cs-ServerAdministrator**, or **CsAdministrator** role.</span></span>
    
2. <span data-ttu-id="b18bc-149">Inicie o Shell de Gerenciamento do Skype for Business Server: clique em **Iniciar**, em **Todos os Programas**, em **Skype for Business 2015** e em **Shell de Gerenciamento do Skype for Business Server**.</span><span class="sxs-lookup"><span data-stu-id="b18bc-149">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="b18bc-150">Execute o seguinte no prompt de comando:</span><span class="sxs-lookup"><span data-stu-id="b18bc-150">Run the following at the command prompt:</span></span>
    
   ```
   Get-CsDialPlan [-Identity <Identifier of the dial plans to be retrieved>]
   ```

   <span data-ttu-id="b18bc-151">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="b18bc-151">For example:</span></span>
    
   ```
   Get-CsDialPlan
   ```

   <span data-ttu-id="b18bc-152">Neste exemplo, todos os planos de discagem configurados para sua organização são retornados.</span><span class="sxs-lookup"><span data-stu-id="b18bc-152">In this example, all the dial plans configured for your organization are returned.</span></span>
    
4. <span data-ttu-id="b18bc-153">Revise os planos de discagem retornados para identificar todos que estão faltando na região da conferência discada.</span><span class="sxs-lookup"><span data-stu-id="b18bc-153">Review the returned dial plans to identify any that are missing the dial-in conferencing region.</span></span> 
    
<span data-ttu-id="b18bc-154">Para obter mais informações, consulte [Get-CsDialPlan](https://docs.microsoft.com/powershell/module/skype/get-csdialplan?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="b18bc-154">For more information, see [Get-CsDialPlan](https://docs.microsoft.com/powershell/module/skype/get-csdialplan?view=skype-ps).</span></span>
  
### <a name="to-set-the-region-property-for-a-dial-plan"></a><span data-ttu-id="b18bc-155">Para definir a propriedade de região de um plano de discagem</span><span class="sxs-lookup"><span data-stu-id="b18bc-155">To set the region property for a dial plan</span></span>

1. <span data-ttu-id="b18bc-156">Efetue logon no computador como membro do grupo RTCUniversalServerAdmins ou como membro da função **Cs-VoiceAdministrator**, **Cs-ServerAdministrator**ou **CsAdministrator**.</span><span class="sxs-lookup"><span data-stu-id="b18bc-156">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the **Cs-VoiceAdministrator**, **Cs-ServerAdministrator**, or **CsAdministrator** role.</span></span>
    
2. <span data-ttu-id="b18bc-157">Inicie o Shell de Gerenciamento do Skype for Business Server: clique em **Iniciar**, em **Todos os Programas**, em **Skype for Business 2015** e em **Shell de Gerenciamento do Skype for Business Server**.</span><span class="sxs-lookup"><span data-stu-id="b18bc-157">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="b18bc-158">Para todos os planos de discagem que não têm a região de conferência discada, execute:</span><span class="sxs-lookup"><span data-stu-id="b18bc-158">For any dial plans that are missing the dial-in conferencing region, run:</span></span>
    
   ```
   Set-CsDialPlan [-Identity <Identity of the dial plan to be modified>] -DialinConferencingRegion "<new region>"
   ```

   <span data-ttu-id="b18bc-159">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="b18bc-159">For example:</span></span>
    
   ```
   Set-CsDialPlan -Identity Redmond -DialinConferencingRegion "US West Coast"
   ```

   <span data-ttu-id="b18bc-160">Neste exemplo, o plano de discagem com Identidade de Redmond é modificado para definir a propriedade DialinConferencingRegion como "Costa Leste dos EUA".</span><span class="sxs-lookup"><span data-stu-id="b18bc-160">In this example, the dial plan with the Identity of Redmond is modified to set the DialinConferencingRegion property to "US West Coast".</span></span> 
    
<span data-ttu-id="b18bc-161">Para obter mais informações, consulte [Set-CsDialPlan](https://docs.microsoft.com/powershell/module/skype/set-csdialplan?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="b18bc-161">For more information, see [Set-CsDialPlan](https://docs.microsoft.com/powershell/module/skype/set-csdialplan?view=skype-ps).</span></span>
  
## <a name="configure-dial-in-access-numbers"></a><span data-ttu-id="b18bc-162">Configure números de acesso de discagem</span><span class="sxs-lookup"><span data-stu-id="b18bc-162">Configure dial-in access numbers</span></span>
<span data-ttu-id="b18bc-163"><a name="BKMK_ConfigureDialInAccessNumbers"> </a></span><span class="sxs-lookup"><span data-stu-id="b18bc-163"></span></span>

<span data-ttu-id="b18bc-164">Ao implantar uma conferência discada, você precisa configurar números de telefone que os usuários poderão discar da PSTN para participar da parte de áudio das conferências.</span><span class="sxs-lookup"><span data-stu-id="b18bc-164">When you deploy dial-in conferencing, you need to set up phone numbers that users can dial from the public switched telephone network (PSTN) to join the audio portion of conferences.</span></span> <span data-ttu-id="b18bc-165">Esses números de acesso de discagem aparecem nos convites de reunião e na página Configurações de Conferência Discada.</span><span class="sxs-lookup"><span data-stu-id="b18bc-165">These dial-in access numbers appear in meeting invitations and on the Dial-in Conferencing Settings webpage.</span></span>
  
<span data-ttu-id="b18bc-166">Antes de criar números de acesso discado, primeiro você precisa planejar as regiões de conferência discada e, em seguida, configurar os planos de discagem nas regiões.</span><span class="sxs-lookup"><span data-stu-id="b18bc-166">Before you can create dial-in access numbers, you must first plan your dial-in conferencing regions and then configure dial plans with the regions.</span></span> <span data-ttu-id="b18bc-167">Para obter detalhes sobre regiões, consulte [Planejar a conferência discada no Skype para Business Server](../../plan-your-deployment/conferencing/dial-in-conferencing.md).</span><span class="sxs-lookup"><span data-stu-id="b18bc-167">For details about regions, see [Plan for dial-in conferencing in Skype for Business Server](../../plan-your-deployment/conferencing/dial-in-conferencing.md).</span></span> <span data-ttu-id="b18bc-168">Para obter detalhes sobre como configurar discagem planos para conferência discada, consulte [criar ou modificar um plano de discagem no Skype para Business Server](../../deploy/deploy-enterprise-voice/dial-plans.md).</span><span class="sxs-lookup"><span data-stu-id="b18bc-168">For details about configuring dial plans for dial-in conferencing, see [Create or modify a dial plan in Skype for Business Server](../../deploy/deploy-enterprise-voice/dial-plans.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="b18bc-p112">Não é possível usar um novo número de acesso discado até que a replicação dos Serviços de Domínio do Active Directory (AD DS) desse número de acesso seja concluída. A replicação pode demorar algumas horas para ser concluída.</span><span class="sxs-lookup"><span data-stu-id="b18bc-p112">You cannot use a new dial-in access number until Active Directory Domain Services (AD DS) replication of that access number is complete. Replication can take several hours to complete.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="b18bc-171">Após a criação dos números de acesso discado, é possível modificar o nome de exibição dos objetos de contato do Active Directory de modo que os usuários possam identificar com mais facilidade o número de acesso correto.</span><span class="sxs-lookup"><span data-stu-id="b18bc-171">After you create dial-in access numbers, you can modify the display name for the Active Directory contact objects so that users can more easily identify the correct access number.</span></span> <span data-ttu-id="b18bc-172">Para modificar o nome para exibição, use o cmdlet [Set-CsDialInConferencingAccessNumber](https://docs.microsoft.com/powershell/module/skype/set-csdialinconferencingaccessnumber?view=skype-ps) .</span><span class="sxs-lookup"><span data-stu-id="b18bc-172">To modify the display name, use the [Set-CsDialInConferencingAccessNumber](https://docs.microsoft.com/powershell/module/skype/set-csdialinconferencingaccessnumber?view=skype-ps) cmdlet.</span></span> <span data-ttu-id="b18bc-173">Não modifique os objetos do Active Directory manualmente.</span><span class="sxs-lookup"><span data-stu-id="b18bc-173">You should not modify Active Directory objects manually.</span></span>
  
### <a name="to-create-a-dial-in-access-number"></a><span data-ttu-id="b18bc-174">Para criar um número de acesso de discagem</span><span class="sxs-lookup"><span data-stu-id="b18bc-174">To create a dial-in access number</span></span>

1. <span data-ttu-id="b18bc-175">Usando uma conta de usuário atribuída à função CsUserAdministrator ou CsAdministrator, faça logon em qualquer computador de sua implantação interna.</span><span class="sxs-lookup"><span data-stu-id="b18bc-175">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="b18bc-176">Abra o Skype para painel de controle do servidor de negócios.</span><span class="sxs-lookup"><span data-stu-id="b18bc-176">Open Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="b18bc-177">Na barra de navegação à esquerda, clique em **Conferência** e, então, em  **Número de acesso de discagem**.</span><span class="sxs-lookup"><span data-stu-id="b18bc-177">In the left navigation bar, click **Conferencing** and then click **Dial-in Access Number**.</span></span>
    
4. <span data-ttu-id="b18bc-178">Na página **Número de Acesso de Discagem**, realize uma das ações a seguir:</span><span class="sxs-lookup"><span data-stu-id="b18bc-178">On the **Dial-in Access Number** page, do one of the following:</span></span>
    
   - <span data-ttu-id="b18bc-179">Clique em **Novo** para abrir **Novo Número de Acesso de Discagem**.</span><span class="sxs-lookup"><span data-stu-id="b18bc-179">Click **New** to open **New Dial-in Access Number**.</span></span>
    
   - <span data-ttu-id="b18bc-180">Clique em um dos números de acesso de discagem na lista, clique em **Editar**, e clique em **Mostrar detalhes**.</span><span class="sxs-lookup"><span data-stu-id="b18bc-180">Click one of the dial-in access numbers in the list, click **Edit**, and then click **Show details**.</span></span>
    
     > [!NOTE]
     > <span data-ttu-id="b18bc-p114">Usar o campo de busca para buscar pelos conteúdos de uma coluna na lista de números de acesso de discagem pode não apresentar os resultados esperados. Em vez disso, classifique a lista pela coluna de interesse para identificar o número de acesso de discagem a ser visualizado ou modificado.</span><span class="sxs-lookup"><span data-stu-id="b18bc-p114">Using the search field to search for the contents of a column in the list of dial-in access numbers may not yield the results you expect. Instead, sort the list by the column of interest to identify the dial-in access number you want to view or change.</span></span> 
  
5. <span data-ttu-id="b18bc-p115">Em **Número de exibição**, digite o número de telefone que os usuários de telefone da rede telefônica pública comutada (PSTN) digitam para participar de uma conferência. Esse número é exibido em convites de reunião e na página da Web de Configurações de Conferência Discada.</span><span class="sxs-lookup"><span data-stu-id="b18bc-p115">In **Display number**, type the phone number that public switched telephone network (PSTN) phone users dial to join a conference. This number is displayed in meeting invitations and on the Dial-in Conferencing Settings webpage.</span></span>
    
6. <span data-ttu-id="b18bc-185">Em **Nome para exibição**, digite uma descrição para o número de acesso de discagem.</span><span class="sxs-lookup"><span data-stu-id="b18bc-185">In **Display name**, type a description for the dial-in access number.</span></span> <span data-ttu-id="b18bc-186">Este é o nome que está associado ao número de acesso de discagem no Skype para resultados de pesquisa de negócios.</span><span class="sxs-lookup"><span data-stu-id="b18bc-186">This is the name that is associated with the dial-in access number in Skype for Business search results.</span></span> <span data-ttu-id="b18bc-187">Esse nome é exibido no cliente quando um usuário disca o número de acesso.</span><span class="sxs-lookup"><span data-stu-id="b18bc-187">This name is displayed in the client when a user calls the access number.</span></span> 
    
7. <span data-ttu-id="b18bc-p117">Em **URI da Linha**, digite o número E.164 do número de acesso de discagem em formato TEL URI, incluindo o símbolo + antes do número e excluindo espaços. Por exemplo, tel:+14255550200.</span><span class="sxs-lookup"><span data-stu-id="b18bc-p117">In **Line URI**, type the E.164 number of the dial-in access number in TEL URI format, including the + symbol before the number and excluding spaces. For example, tel:+14255550200.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="b18bc-190">O mesmo URI de Linha não pode ser reusada por outro número de acesso de conferência discada.</span><span class="sxs-lookup"><span data-stu-id="b18bc-190">The same Line URI cannot be reused by another dial-in conferencing access number.</span></span> 
  
8. <span data-ttu-id="b18bc-191">Em **URI do SIP**, faça o seguinte:</span><span class="sxs-lookup"><span data-stu-id="b18bc-191">In **SIP URI**, do the following:</span></span>
    
   - <span data-ttu-id="b18bc-192">Na caixa de texto, digite um único URI do SIP para o número de acesso de conferência discada.</span><span class="sxs-lookup"><span data-stu-id="b18bc-192">In the text box, type a unique SIP URI for this dial-in conferencing access number.</span></span> <span data-ttu-id="b18bc-193">O URI do SIP é exibido em vários locais, incluindo, mas não limitado para chamar as mensagens de notificação e versões anteriores dos clientes do Lync.</span><span class="sxs-lookup"><span data-stu-id="b18bc-193">This SIP URI is displayed in various locations including, but not limited to, call notification messages and previous versions of Lync clients.</span></span>
    
     > [!NOTE]
     > <span data-ttu-id="b18bc-p119">O mesmo URI do SIP não pode ser reusado por outro número de acesso de conferência discada. O URI do SIP não pode ser modificado depois de o número de acesso ter sido criado. A única maneira de altera o URI do SIP é excluir e recriar o número de acesso.</span><span class="sxs-lookup"><span data-stu-id="b18bc-p119">The same SIP URI cannot be reused by another dial-in conferencing access number. The SIP URI cannot be modified after the access number is created. The only way to change the SIP URI is to delete and recreate the access number.</span></span> 
  
   - <span data-ttu-id="b18bc-197">Na caixa de listagem suspensa, clique no domínio do aplicativo Atendedor de conferência que ofereça suporte a esse número de acesso de discagem.</span><span class="sxs-lookup"><span data-stu-id="b18bc-197">In the drop-down list box, click the domain of the Conferencing Attendant application that supports this dial-in access number.</span></span>
    
9. <span data-ttu-id="b18bc-198">Em  **Pool**, clique no pool que está executado a instância Atendedor de Conferência que dá suporte ao número de acesso de discagem.</span><span class="sxs-lookup"><span data-stu-id="b18bc-198">In **Pool**, click the pool that is running the instance of Conferencing Attendant that supports this dial-in access number.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="b18bc-199">Se for preciso alterar o pool depois de criar o número de acesso, deve-se usar o cmdlet do [Move-CsApplicationEndpoint](https://docs.microsoft.com/powershell/module/skype/move-csapplicationendpoint?view=skype-ps) ou excluir e recriar o número de acesso.</span><span class="sxs-lookup"><span data-stu-id="b18bc-199">If you need to change the pool after you create the access number, you must use the [Move-CsApplicationEndpoint](https://docs.microsoft.com/powershell/module/skype/move-csapplicationendpoint?view=skype-ps) cmdlet or delete and recreate the access number.</span></span>
  
10. <span data-ttu-id="b18bc-200">Em **Idioma principal**, clique no idioma no qual as solicitações são reproduzidas para esse número de acesso de discagem.</span><span class="sxs-lookup"><span data-stu-id="b18bc-200">In **Primary language**, click the language in which prompts are played for this dial-in access number.</span></span> 
    
    <span data-ttu-id="b18bc-p120">O idioma principal é o idioma que o Atendente de Conferência usa para atender a ligação. Os idiomas suportados são exibidos ao lado de cada número de acesso de discagem na página da Web das Configurações de Conferência Discada.</span><span class="sxs-lookup"><span data-stu-id="b18bc-p120">The primary language is the language that the Conferencing Attendant uses to answer the call. Supported languages are displayed alongside each access phone number on the Dial-in Conferencing Settings webpage.</span></span>
    
11. <span data-ttu-id="b18bc-203">(Opcional) Em **Idiomas secundários (máximo de quatro)**, clique em **Adicionar**, selecione um ou mais idiomas adicionais que você quer oferecer aos chamadores para esse número de acesso de discagem, e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="b18bc-203">(Optional) In **Secondary languages (maximum of four)**, click **Add**, select one or more additional languages that you want to support for callers to this dial-in access number, and then click **OK**.</span></span> 
    
    <span data-ttu-id="b18bc-p121">É possível escolher até quatro idiomas secundários para cada número de acesso de discagem. Os usuários podem selecionar um idioma secundário antes de inserir o ID de conferência ao ligarem para uma.</span><span class="sxs-lookup"><span data-stu-id="b18bc-p121">You can choose up to four secondary languages for each dial-in access number. Users can select a secondary language before entering the conference ID when they dial in to a conference.</span></span>
    
12. <span data-ttu-id="b18bc-206">Para adicionar uma região para o número de acesso de discagem, em **regiões associadas**, clique em **Adicionar**, clique em uma ou mais regiões que estão associados com os planos de discagem para este número de acesso de discagem e clique em **Okey**.</span><span class="sxs-lookup"><span data-stu-id="b18bc-206">To add a region for the dial-in access number, under **Associated regions**, click **Add**, click one or more regions that are associated with the dial plans for this dial-in access number, and then click **OK**.</span></span>
    
13. <span data-ttu-id="b18bc-207">Para excluir uma região do número de acesso de discagem, em **Regiões Associadas**, clique na região a ser excluída e clique em **Remover**.</span><span class="sxs-lookup"><span data-stu-id="b18bc-207">To delete a region from the dial-in access number, under **Associated regions**, click the region you want to delete, and then click **Remove**.</span></span>
    
14. <span data-ttu-id="b18bc-208">Clique em **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="b18bc-208">Click **Commit**.</span></span>
    
## <a name="configure-conferencing-policies"></a><span data-ttu-id="b18bc-209">Configurar políticas de conferência</span><span class="sxs-lookup"><span data-stu-id="b18bc-209">Configure conferencing policies</span></span>
<span data-ttu-id="b18bc-210"><a name="BKMK_ConfigureConferencingPolicies"> </a></span><span class="sxs-lookup"><span data-stu-id="b18bc-210"></span></span>

<span data-ttu-id="b18bc-p122">A política de conferência é uma configuração de conta de usuário que especifica a experiência de conferência para os participantes. Você pode criar políticas de conferência com um escopo de site ou um escopo de usuário. As configurações de política de conferência englobam vários aspectos do agendamento da conferência e da participação. Várias configurações de política de conferência oferecem suporte à conferência discada para participantes. Ao configurar a conferência discada, você deve verificar se estes campos foram definidos adequadamente para sua organização e modificá-los conforme necessário.</span><span class="sxs-lookup"><span data-stu-id="b18bc-p122">Conferencing policy is a user account setting that specifies the conferencing experience for participants. You can create conferencing policies with a site scope or a user scope. Conferencing policy settings encompass many aspects of conference scheduling and participation. Several conferencing policy settings support dial-in conferencing for participants. When you configure dial-in conferencing, you should verify that these fields are set appropriately for your organization, and modify them as necessary.</span></span> 
  
<span data-ttu-id="b18bc-216">Para obter mais informações sobre como configurar políticas de conferência, consulte [Gerenciar políticas de conferência no Skype para Business Server](../../manage/conferencing/conferencing-policies.md).</span><span class="sxs-lookup"><span data-stu-id="b18bc-216">For more information about configuring conferencing policies, see [Manage conferencing policies in Skype for Business Server](../../manage/conferencing/conferencing-policies.md).</span></span>
  
## <a name="assign-a-line-uri-to-a-user-account"></a><span data-ttu-id="b18bc-217">Atribuir um URI da Linha a uma conta de usuário</span><span class="sxs-lookup"><span data-stu-id="b18bc-217">Assign a Line URI to a user account</span></span>
<span data-ttu-id="b18bc-218"><a name="BKMK_AssignaLineURI"> </a></span><span class="sxs-lookup"><span data-stu-id="b18bc-218"></span></span>

<span data-ttu-id="b18bc-219">Os usuários de discagem digitam o número de telefone ou a extensão e um PIN para participar nas conferências como usuários autenticados.</span><span class="sxs-lookup"><span data-stu-id="b18bc-219">Dial-in users enter their phone number or extension and a PIN to join conferences as authenticated users.</span></span> <span data-ttu-id="b18bc-220">A telefonia **URI da linha** especificada no Skype para contas de usuário do Business Server é necessária para autenticação.</span><span class="sxs-lookup"><span data-stu-id="b18bc-220">The telephony **Line URI** specified on Skype for Business Server user accounts is required for authentication.</span></span>
  
<span data-ttu-id="b18bc-221">O procedimento neste tópico descreve como atribuir um **URI da Linha** para uma única conta de usuário.</span><span class="sxs-lookup"><span data-stu-id="b18bc-221">The procedure in this topic describes how to assign a **Line URI** for a single user account.</span></span> <span data-ttu-id="b18bc-222">Se você precisar atribuir um **URI da Linha** para várias contas de usuários, poderá criar um script que usa o cmdlet **Set-CsUser**.</span><span class="sxs-lookup"><span data-stu-id="b18bc-222">If you need to assign a **Line URI** for multiple user accounts, you can create a script that uses the **Set-CsUser** cmdlet.</span></span> <span data-ttu-id="b18bc-223">Para obter detalhes sobre como usar um script de exemplo para atribuir o **URI da linha** a várias contas de usuário, consulte [Atribuir Line URIs a vários usuários](https://go.microsoft.com/fwlink/p/?linkId=196945).</span><span class="sxs-lookup"><span data-stu-id="b18bc-223">For details about using a sample script to assign **Line URI** to multiple user accounts, see [Assign Line URIs to Multiple Users](https://go.microsoft.com/fwlink/p/?linkId=196945).</span></span>
  
1. <span data-ttu-id="b18bc-224">Faça logon no computador como membro do grupo RTCUniversalServerAdmins ou como membro da função **Cs-UserAdministrator** ou **CsAdministrator**.</span><span class="sxs-lookup"><span data-stu-id="b18bc-224">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the **Cs-UserAdministrator** or **CsAdministrator** role.</span></span>
    
2.  <span data-ttu-id="b18bc-225">Abra o Skype para painel de controle do servidor de negócios.</span><span class="sxs-lookup"><span data-stu-id="b18bc-225">Open Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="b18bc-226">Na barra de navegação esquerda, clique em **Usuários**.</span><span class="sxs-lookup"><span data-stu-id="b18bc-226">In the left navigation bar, click **Users**.</span></span>
    
4. <span data-ttu-id="b18bc-227">No campo de pesquisa, digite o nome do usuário que você deseja configurar para conferência discada ou clique em **Adicionar filtro** para especificar os campos de pesquisa e clique em **Localizar**.</span><span class="sxs-lookup"><span data-stu-id="b18bc-227">In the search field, type the name of the user you want to configure for dial-in conferencing or click **Add filter** to specify search fields, and then click **Find**.</span></span>
    
5. <span data-ttu-id="b18bc-228">Clique duas vezes no nome do usuário para abrir a caixa de diálogo **Editar Usuário do Skype for Business Server**.</span><span class="sxs-lookup"><span data-stu-id="b18bc-228">Double-click the user name to open the **Edit Skype for Business Server User** dialog box.</span></span>
    
6. <span data-ttu-id="b18bc-229">Em **Telefonia**, no campo **URI da Linha**, digite um número de telefone exclusivo e normalizado (por exemplo, tel:+14255550200).</span><span class="sxs-lookup"><span data-stu-id="b18bc-229">Under **Telephony**, in the **Line URI** field, type a unique, normalized phone number (for example, tel:+14255550200).</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="b18bc-230">Você pode especificar o **URI de linha** somente se **Telefonia** estiver definida como **Somente PC para PC**, **Enterprise Voice**,  **Controle de chamada remota** ou **Somente controle de chamada remota**.</span><span class="sxs-lookup"><span data-stu-id="b18bc-230">You can specify **Line URI** only if **Telephony** is set to **PC-to-PC only**, **Enterprise Voice**, **Remote call control** or **Remote call control only**.</span></span> 
  
7. <span data-ttu-id="b18bc-231">Clique em **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="b18bc-231">Click **Commit**.</span></span>
    

