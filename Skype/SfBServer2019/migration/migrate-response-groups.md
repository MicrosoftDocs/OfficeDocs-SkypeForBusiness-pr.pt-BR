---
title: Migrar grupos de resposta
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Depois que os usuários forem movidos para pools do Skype for Business Server 2019, você poderá migrar seus grupos de resposta. Migrar grupos de resposta inclui copiar grupos de agente, filas, fluxos de trabalho, arquivos de áudio e mover objetos de contato de grupo de resposta da implantação herdada para o pool do Skype for Business Server 2019. Depois de migrar seus grupos de resposta herdados, as chamadas para os grupos de resposta são manipuladas pelo aplicativo grupo de resposta no pool do Skype for Business Server 2019. As chamadas para grupos de resposta não são mais manipuladas pelo pool herdado.
ms.openlocfilehash: b8d49205f4f54ca7c00a9aed0b6ac176c11cd617
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/07/2019
ms.locfileid: "36237967"
---
# <a name="migrate-response-groups"></a><span data-ttu-id="222ca-106">Migrar grupos de resposta</span><span class="sxs-lookup"><span data-stu-id="222ca-106">Migrate response groups</span></span>

<span data-ttu-id="222ca-107">Depois que os usuários forem movidos para pools do Skype for Business Server 2019, você poderá migrar seus grupos de resposta.</span><span class="sxs-lookup"><span data-stu-id="222ca-107">After your users are moved to Skype for Business Server 2019 pools, you can migrate your response groups.</span></span> <span data-ttu-id="222ca-108">Migrar grupos de resposta inclui copiar grupos de agente, filas, fluxos de trabalho, arquivos de áudio e mover objetos de contato de grupo de resposta da implantação herdada para o pool do Skype for Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="222ca-108">Migrating response groups includes copying agent groups, queues, workflows, audio files, and moving Response Group contact objects from the legacy deployment to the Skype for Business Server 2019 pool.</span></span> <span data-ttu-id="222ca-109">Depois de migrar seus grupos de resposta herdados, as chamadas para os grupos de resposta são manipuladas pelo aplicativo grupo de resposta no pool do Skype for Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="222ca-109">After you migrate your legacy response groups, calls to the response groups are handled by the Response Group application in the Skype for Business Server 2019 pool.</span></span> <span data-ttu-id="222ca-110">As chamadas para grupos de resposta não são mais manipuladas pelo pool herdado.</span><span class="sxs-lookup"><span data-stu-id="222ca-110">Calls to response groups are no longer handled by the legacy pool.</span></span>
  
> [!NOTE]
> <span data-ttu-id="222ca-111">Embora seja possível migrar grupos de resposta antes de mover todos os usuários para o pool do Skype for Business Server 2019, recomendamos que você mova todos os usuários primeiro.</span><span class="sxs-lookup"><span data-stu-id="222ca-111">Although you can migrate response groups before you move all users to the Skype for Business Server 2019 pool, we recommend that you move all users first.</span></span> <span data-ttu-id="222ca-112">Em particular, os usuários que são agentes de grupo de resposta não terão funcionalidade completa dos novos recursos até serem movidos para o pool do Skype for Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="222ca-112">In particular, users who are response group agents will not have full functionality of new features until they are moved to the Skype for Business Server 2019 pool.</span></span> 
  
<span data-ttu-id="222ca-113">Antes de migrar grupos de resposta, você deve ter implantado um pool do Skype for Business Server 2019 que inclui o aplicativo de grupo de resposta.</span><span class="sxs-lookup"><span data-stu-id="222ca-113">Before you migrate response groups, you must have deployed a Skype for Business Server 2019 pool that includes the Response Group application.</span></span> <span data-ttu-id="222ca-114">O aplicativo grupo de resposta é instalado e ativado por padrão ao implantar o Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="222ca-114">The Response Group application is installed and activated by default when you deploy Enterprise Voice.</span></span> <span data-ttu-id="222ca-115">Você pode garantir que o aplicativo do grupo de resposta seja instalado executando o cmdlet **Get-CsService-ApplicationServer** .</span><span class="sxs-lookup"><span data-stu-id="222ca-115">You can ensure that the Response Group application is installed by running the **Get-CsService -ApplicationServer** cmdlet.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="222ca-116">Você pode criar novos grupos de resposta do Skype for Business Server 2019 no pool do Skype for Business Server 2019 antes de migrar seus grupos de resposta herdados.</span><span class="sxs-lookup"><span data-stu-id="222ca-116">You can create new Skype for Business Server 2019 response groups in the Skype for Business Server 2019 pool before you migrate your legacy response groups.</span></span> 
  
<span data-ttu-id="222ca-117">Para migrar grupos de resposta de um pool herdado para o Skype for Business Server 2019, execute o cmdlet **move-CsRgsConfiguration** .</span><span class="sxs-lookup"><span data-stu-id="222ca-117">To migrate response groups from a legacy pool to the Skype for Business Server 2019, you run the **Move-CsRgsConfiguration** cmdlet.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="222ca-118">O cmdlet de migração do grupo de resposta move a configuração do grupo de resposta para o pool inteiro.</span><span class="sxs-lookup"><span data-stu-id="222ca-118">The Response Group migration cmdlet moves the Response Group configuration for the entire pool.</span></span> <span data-ttu-id="222ca-119">Não é possível selecionar grupos, filas ou fluxos de trabalho específicos para migrar.</span><span class="sxs-lookup"><span data-stu-id="222ca-119">You cannot select specific groups, queues, or workflows to migrate.</span></span> 
  
<span data-ttu-id="222ca-120">Depois de migrar os grupos de resposta, você precisa usar o painel de controle do Skype for Business Server ou cmdlets do Shell de gerenciamento do Skype for Business Server para verificar se todos os grupos de agente, filas e fluxos de trabalho foram movidos com êxito.</span><span class="sxs-lookup"><span data-stu-id="222ca-120">After you migrate the response groups, you need to use Skype for Business Server Control Panel or Skype for Business Server Management Shell cmdlets to verify that all agent groups, queues, and workflows moved successfully.</span></span> 
  
<span data-ttu-id="222ca-121">Quando você migra grupos de resposta, os grupos de respostas herdadas não são removidos.</span><span class="sxs-lookup"><span data-stu-id="222ca-121">When you migrate response groups, the legacy response groups are not removed.</span></span> <span data-ttu-id="222ca-122">Ao gerenciar grupos de resposta após a migração usando o painel de controle do Skype for Business Server ou o Shell de gerenciamento do Skype for Business Server, você pode ver os grupos de resposta herdados e os grupos de resposta do Skype for Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="222ca-122">When you manage response groups after migration by using either Skype for Business Server Control Panel or Skype for Business Server Management Shell, you can see both the legacy response groups and the Skype for Business Server 2019 response groups.</span></span> <span data-ttu-id="222ca-123">Você deve aplicar atualizações somente aos grupos de resposta do Skype for Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="222ca-123">You should apply updates only to the Skype for Business Server 2019 response groups.</span></span> <span data-ttu-id="222ca-124">Os grupos de respostas herdadas são mantidos somente para fins de recuperação.</span><span class="sxs-lookup"><span data-stu-id="222ca-124">The legacy response groups are retained only for rollback purposes.</span></span> 
  
> [!CAUTION]
> <span data-ttu-id="222ca-125">Após a conclusão da migração e os novos grupos de resposta terem sido criados, o painel de controle do Skype for Business Server e o Shell de gerenciamento do Skype for Business Server exibirão as versões herdadas e do Skype for Business Server 2019 de cada resposta. grupos.</span><span class="sxs-lookup"><span data-stu-id="222ca-125">After the migration has been completed and the new response groups have been created, the Skype for Business Server Control Panel and the Skype for Business Server Management Shell will display the legacy and Skype for Business Server 2019 versions of each response group.</span></span> <span data-ttu-id="222ca-126">Não use o painel de controle do Skype for Business Server ou o Shell de gerenciamento do Skype for Business Server para remover os grupos de resposta herdados.</span><span class="sxs-lookup"><span data-stu-id="222ca-126">Do not use Skype for Business Server Control Panel or Skype for Business Server Management Shell to remove the legacy response groups.</span></span> <span data-ttu-id="222ca-127">Se você remover um, o grupo de resposta correspondente criado durante a migração deixará de funcionar.</span><span class="sxs-lookup"><span data-stu-id="222ca-127">If you do remove one, the corresponding response group that was created during migration will stop working.</span></span> <span data-ttu-id="222ca-128">Os grupos de respostas herdadas serão removidos quando você encerrar o pool herdado.</span><span class="sxs-lookup"><span data-stu-id="222ca-128">The legacy response groups will be removed when you decommission the legacy pool.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="222ca-129">Recomendamos que você não remova dados de sua implantação anterior até encerrar o pool.</span><span class="sxs-lookup"><span data-stu-id="222ca-129">We recommend that you do not remove any data from your previous deployment until you decommission the pool.</span></span> <span data-ttu-id="222ca-130">Além disso, recomendamos enfaticamente que você exporte os grupos de resposta imediatamente após a migração.</span><span class="sxs-lookup"><span data-stu-id="222ca-130">In addition, we strongly recommend that you export response groups immediately after you migrate.</span></span> <span data-ttu-id="222ca-131">Se um grupo de resposta herdado deve ser removido, você pode restaurar seus grupos de resposta do backup para obter os grupos de resposta do Skype for Business Server 2019 em execução novamente.</span><span class="sxs-lookup"><span data-stu-id="222ca-131">If a legacy response group should get removed, you can then restore your response groups from the backup to get Skype for Business Server 2019 response groups running again.</span></span> 
  
<span data-ttu-id="222ca-132">O Skype for Business Server 2019 apresenta um novo recurso de grupo de resposta chamado **tipo de fluxo de trabalho**.</span><span class="sxs-lookup"><span data-stu-id="222ca-132">Skype for Business Server 2019 introduces a new Response Group feature called **Workflow Type**.</span></span> <span data-ttu-id="222ca-133">O **tipo de fluxo de trabalho** pode ser **gerenciado** ou **não gerenciado**.</span><span class="sxs-lookup"><span data-stu-id="222ca-133">**Workflow Type** can be **Managed** or **Unmanaged**.</span></span> <span data-ttu-id="222ca-134">Todos os grupos de resposta são migrados com o **tipo de fluxo de trabalho** definido como **não gerenciado** e com uma lista de gerentes vazia.</span><span class="sxs-lookup"><span data-stu-id="222ca-134">All response groups are migrated with **Workflow Type** set to **Unmanaged** and with an empty Manager list.</span></span> 
  
<span data-ttu-id="222ca-135">Quando você executa o cmdlet **move-CsRgsConfiguration** , os grupos de agente, filas, fluxos de trabalho e arquivos de áudio permanecem no pool herdado para fins de reversão.</span><span class="sxs-lookup"><span data-stu-id="222ca-135">When you run the **Move-CsRgsConfiguration** cmdlet, the agent groups, queues, workflows, and audio files remain in the legacy pool for rollback purposes.</span></span> <span data-ttu-id="222ca-136">No entanto, se você precisar reverter para o pool herdado, será necessário executar o cmdlet **move-CsApplicationEndpoint** para mover objetos de contato de volta para o pool herdado.</span><span class="sxs-lookup"><span data-stu-id="222ca-136">If you do need to roll back to the legacy pool, however, you need to run the **Move-CsApplicationEndpoint** cmdlet to move contact objects back to the legacy pool.</span></span> 
  
<span data-ttu-id="222ca-137">O procedimento a seguir para migrar configurações de grupo de resposta pressupõe que você tenha uma relação um-para-um entre seus pools herdados e os pools do Skype for Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="222ca-137">The following procedure for migrating Response Group configurations assumes that you have a one-to-one relationship between your legacy pools and the Skype for Business Server 2019 pools.</span></span> <span data-ttu-id="222ca-138">Se você planeja consolidar ou dividir os pools durante a migração e a implantação, será necessário planejar quais pools herdados são mapeados para o pool do Skype for Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="222ca-138">If you plan to consolidate or split up pools during your migration and deployment, you need to plan which legacy pool maps to which Skype for Business Server 2019 pool.</span></span>
  
## <a name="to-migrate-response-group-configurations"></a><span data-ttu-id="222ca-139">Migrar configurações de grupo de resposta</span><span class="sxs-lookup"><span data-stu-id="222ca-139">To migrate Response Group configurations</span></span>

1. <span data-ttu-id="222ca-140">Faça logon no computador com uma conta que seja membro do grupo RTCUniversalServerAdmins ou tenha direitos e permissões de administrador equivalentes.</span><span class="sxs-lookup"><span data-stu-id="222ca-140">Log on to the computer with an account that is a member of the RTCUniversalServerAdmins group or has equivalent administrator rights and permissions.</span></span>
    
2. <span data-ttu-id="222ca-141">Inicie o Shell de gerenciamento do Skype for Business Server: clique em **Iniciar**, em **todos os programas**, em **Microsoft Skype for Business Server 2019**e, em seguida, clique em **Shell de gerenciamento do Skype for Business Server**.</span><span class="sxs-lookup"><span data-stu-id="222ca-141">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Skype for Business Server 2019**, and then click **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="222ca-142">Execute:</span><span class="sxs-lookup"><span data-stu-id="222ca-142">Run:</span></span>
    
   ```
   Move-CsRgsConfiguration -Source <source pool FQDN> -Destination <destination pool FQDN>
   ```

    <span data-ttu-id="222ca-143">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="222ca-143">For example:</span></span>
    
   ```
   Move-CsRgsConfiguration -Source skype-old.contoso.net -Destination skype-new.contoso.net
   ```

4. <span data-ttu-id="222ca-144">Depois de migrar grupos de resposta e agentes para o pool do Skype for Business Server 2019, a URL usada pelos agentes para entrar e sair é uma URL do Skype for Business Server 2019 e está disponível no menu **ferramentas** .</span><span class="sxs-lookup"><span data-stu-id="222ca-144">After you migrate response groups and agents to the Skype for Business Server 2019 pool, the URL that agents use to sign in and sign out is a Skype for Business Server 2019 URL and is available from the **Tools** menu.</span></span> <span data-ttu-id="222ca-145">Lembre os agentes para atualizar todas as referências, como indicadores, para a nova URL.</span><span class="sxs-lookup"><span data-stu-id="222ca-145">Remind agents to update any references, such as bookmarks, to the new URL.</span></span> 
    
## <a name="to-verify-response-group-migration-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="222ca-146">Para verificar a migração do grupo de resposta usando o painel de controle do Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="222ca-146">To verify Response Group migration by using Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="222ca-147">Faça logon no computador com uma conta que seja membro do grupo RTCUniversalReadOnlyAdmins ou que seja minimamente um membro da função CsViewOnlyAdministrator.</span><span class="sxs-lookup"><span data-stu-id="222ca-147">Log on to the computer with an account that is a member of RTCUniversalReadOnlyAdmins group or is minimally a member of the CsViewOnlyAdministrator role.</span></span>
    
2. <span data-ttu-id="222ca-148">Abra uma janela do navegador e, em seguida, insira a URL de administração para abrir o painel de controle do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="222ca-148">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> <span data-ttu-id="222ca-149">Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle do Skype for Business Server, consulte [abrir ferramentas administrativas do Skype for Business server 2019](https://technet.microsoft.com/en-us/library/gg195741(v=ocs.15).aspx).</span><span class="sxs-lookup"><span data-stu-id="222ca-149">For details about the different methods you can use to start Skype for Business Server Control Panel, see [Open Skype for Business Server 2019 administrative tools](https://technet.microsoft.com/en-us/library/gg195741(v=ocs.15).aspx).</span></span> 
    <!-- The above link points to un-rebranded 2013 content we will need to discuss rebrand or bring forward -->
3. <span data-ttu-id="222ca-150">No painel de navegação esquerdo, clique em **grupos de resposta**.</span><span class="sxs-lookup"><span data-stu-id="222ca-150">In the left navigation pane, click **Response Groups**.</span></span>
    
4. <span data-ttu-id="222ca-151">Na guia **fluxo de trabalho** , verifique se todos os fluxos de trabalho em seu ambiente herdado estão incluídos na lista.</span><span class="sxs-lookup"><span data-stu-id="222ca-151">On the **Workflow** tab, verify that all the workflows in your legacy environment are included in the list.</span></span> 
    
5. <span data-ttu-id="222ca-152">Clique na guia **fila** e verifique se todas as filas em seu ambiente herdado estão incluídas na lista.</span><span class="sxs-lookup"><span data-stu-id="222ca-152">Click the **Queue** tab, and verify that all the queues in your legacy environment are included in the list.</span></span> 
    
6. <span data-ttu-id="222ca-153">Clique na guia **grupo** e verifique se todos os grupos de agente em seu ambiente herdado estão incluídos na lista.</span><span class="sxs-lookup"><span data-stu-id="222ca-153">Click the **Group** tab, and verify that all the agent groups in your legacy environment are included in the list.</span></span> 
    
## <a name="to-verify-response-group-migration-by-using-skype-for-business-server-management-shell"></a><span data-ttu-id="222ca-154">Para verificar a migração do grupo de resposta usando o Shell de gerenciamento do Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="222ca-154">To verify Response Group migration by using Skype for Business Server Management Shell</span></span>

1. <span data-ttu-id="222ca-155">Faça logon no computador com uma conta que seja membro do grupo RTCUniversalReadOnlyAdmins ou que seja minimamente um membro da função CsViewOnlyAdministrator.</span><span class="sxs-lookup"><span data-stu-id="222ca-155">Log on to the computer with an account that is a member of RTCUniversalReadOnlyAdmins group or is minimally a member of the CsViewOnlyAdministrator role.</span></span>
    
2. <span data-ttu-id="222ca-156">Inicie o Shell de gerenciamento do Skype for Business Server: clique em **Iniciar**, em **todos os programas**, em **Microsoft Skype for Business Server 2019**e, em seguida, clique em **Shell de gerenciamento do Skype for Business Server**.</span><span class="sxs-lookup"><span data-stu-id="222ca-156">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Skype for Business Server 2019**, and then click **Skype for Business Server Management Shell**.</span></span>
    
    <span data-ttu-id="222ca-157">Para obter detalhes sobre os seguintes cmdlets, execute:</span><span class="sxs-lookup"><span data-stu-id="222ca-157">For details about the following cmdlets, run:</span></span>
    
   ```
   Get-Help <cmdlet name> -Detailed
   ```

3. <span data-ttu-id="222ca-158">Execute:</span><span class="sxs-lookup"><span data-stu-id="222ca-158">Run:</span></span>
    
   ```
   Get-CsRgsAgentGroup
   ```

4. <span data-ttu-id="222ca-159">Verifique se todos os grupos de agente do seu ambiente herdado estão incluídos na lista.</span><span class="sxs-lookup"><span data-stu-id="222ca-159">Verify that all the agent groups in your legacy environment are included in the list.</span></span>
    
5. <span data-ttu-id="222ca-160">Execute:</span><span class="sxs-lookup"><span data-stu-id="222ca-160">Run:</span></span>
    
   ```
   Get-CsRgsQueue
   ```

6. <span data-ttu-id="222ca-161">Verifique se todas as filas em seu ambiente herdado estão incluídas na lista.</span><span class="sxs-lookup"><span data-stu-id="222ca-161">Verify that all the queues in your legacy environment are included in the list.</span></span>
    
7. <span data-ttu-id="222ca-162">Execute:</span><span class="sxs-lookup"><span data-stu-id="222ca-162">Run:</span></span>
    
   ```
   Get-CsRgsWorkflow
   ```

8. <span data-ttu-id="222ca-163">Verifique se todos os fluxos de trabalho em seu ambiente herdado estão incluídos na lista.</span><span class="sxs-lookup"><span data-stu-id="222ca-163">Verify that all the workflows in your legacy environment are included in the list.</span></span>
    

