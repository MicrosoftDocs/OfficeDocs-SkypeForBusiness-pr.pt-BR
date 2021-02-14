---
title: Migrar grupos de resposta
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Depois que seus usuários são movidos para pools do Skype for Business Server 2019, você pode migrar seus grupos de resposta. A migração de grupos de resposta inclui copiar grupos de agentes, filas, fluxos de trabalho, arquivos de áudio e mover objetos de contato do Grupo de Resposta da implantação herdada para o pool do Skype for Business Server 2019. Depois de migrar seus grupos de resposta herdados, as chamadas para os grupos de resposta são tratadas pelo aplicativo Grupo de Resposta no pool do Skype for Business Server 2019. As chamadas aos grupos de resposta não serão mais processadas pelo pool antigo.
ms.openlocfilehash: 03b0ffd900b5d7c23dd6ff680d56c0c4db53d8dc
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/16/2020
ms.locfileid: "44752673"
---
# <a name="migrate-response-groups"></a><span data-ttu-id="39ee8-106">Migrar grupos de resposta</span><span class="sxs-lookup"><span data-stu-id="39ee8-106">Migrate response groups</span></span>

<span data-ttu-id="39ee8-107">Depois que seus usuários são movidos para pools do Skype for Business Server 2019, você pode migrar seus grupos de resposta.</span><span class="sxs-lookup"><span data-stu-id="39ee8-107">After your users are moved to Skype for Business Server 2019 pools, you can migrate your response groups.</span></span> <span data-ttu-id="39ee8-108">A migração de grupos de resposta inclui copiar grupos de agentes, filas, fluxos de trabalho, arquivos de áudio e mover objetos de contato do Grupo de Resposta da implantação herdada para o pool do Skype for Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="39ee8-108">Migrating response groups includes copying agent groups, queues, workflows, audio files, and moving Response Group contact objects from the legacy deployment to the Skype for Business Server 2019 pool.</span></span> <span data-ttu-id="39ee8-109">Depois de migrar seus grupos de resposta herdados, as chamadas para os grupos de resposta são tratadas pelo aplicativo Grupo de Resposta no pool do Skype for Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="39ee8-109">After you migrate your legacy response groups, calls to the response groups are handled by the Response Group application in the Skype for Business Server 2019 pool.</span></span> <span data-ttu-id="39ee8-110">As chamadas aos grupos de resposta não serão mais processadas pelo pool antigo.</span><span class="sxs-lookup"><span data-stu-id="39ee8-110">Calls to response groups are no longer handled by the legacy pool.</span></span>
  
> [!NOTE]
> <span data-ttu-id="39ee8-111">Embora seja possível migrar grupos de resposta antes de mover todos os usuários para o pool do Skype for Business Server 2019, recomendamos que você mova todos os usuários primeiro.</span><span class="sxs-lookup"><span data-stu-id="39ee8-111">Although you can migrate response groups before you move all users to the Skype for Business Server 2019 pool, we recommend that you move all users first.</span></span> <span data-ttu-id="39ee8-112">Em particular, os usuários que são agentes do grupo de resposta não terão a funcionalidade completa dos novos recursos até que sejam movidos para o pool do Skype for Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="39ee8-112">In particular, users who are response group agents will not have full functionality of new features until they are moved to the Skype for Business Server 2019 pool.</span></span> 
  
<span data-ttu-id="39ee8-113">Antes de migrar grupos de resposta, você deve ter implantado um pool do Skype for Business Server 2019 que inclui o aplicativo Grupo de Resposta.</span><span class="sxs-lookup"><span data-stu-id="39ee8-113">Before you migrate response groups, you must have deployed a Skype for Business Server 2019 pool that includes the Response Group application.</span></span> <span data-ttu-id="39ee8-114">O aplicativo Grupo de Resposta é instalado e ativado por padrão quando você implanta o Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="39ee8-114">The Response Group application is installed and activated by default when you deploy Enterprise Voice.</span></span> <span data-ttu-id="39ee8-115">Você pode garantir que o aplicativo grupo de resposta está instalado executando **o cmdlet Get-CsService -ApplicationServer.**</span><span class="sxs-lookup"><span data-stu-id="39ee8-115">You can ensure that the Response Group application is installed by running the **Get-CsService -ApplicationServer** cmdlet.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="39ee8-116">Você pode criar novos grupos de resposta do Skype for Business Server 2019 no pool do Skype for Business Server 2019 antes de migrar seus grupos de resposta herdados.</span><span class="sxs-lookup"><span data-stu-id="39ee8-116">You can create new Skype for Business Server 2019 response groups in the Skype for Business Server 2019 pool before you migrate your legacy response groups.</span></span> 
  
<span data-ttu-id="39ee8-117">Para migrar grupos de resposta de um pool herdado para o Skype for Business Server 2019, execute o cmdlet **Move-CsRgsConfiguration.**</span><span class="sxs-lookup"><span data-stu-id="39ee8-117">To migrate response groups from a legacy pool to the Skype for Business Server 2019, you run the **Move-CsRgsConfiguration** cmdlet.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="39ee8-118">O cmdlet de migração do Grupo de Resposta move a configuração do Grupo de Resposta para todo o pool.</span><span class="sxs-lookup"><span data-stu-id="39ee8-118">The Response Group migration cmdlet moves the Response Group configuration for the entire pool.</span></span> <span data-ttu-id="39ee8-119">Não é possível selecionar grupos, filas e fluxos de trabalho específicos para migração.</span><span class="sxs-lookup"><span data-stu-id="39ee8-119">You cannot select specific groups, queues, or workflows to migrate.</span></span> 
  
<span data-ttu-id="39ee8-120">Depois de migrar os grupos de resposta, você precisará usar o Painel de Controle do Skype for Business Server ou os cmdlets do Shell de Gerenciamento do Skype for Business Server para verificar se todos os grupos de agentes, filas e fluxos de trabalho foram movidos com êxito.</span><span class="sxs-lookup"><span data-stu-id="39ee8-120">After you migrate the response groups, you need to use Skype for Business Server Control Panel or Skype for Business Server Management Shell cmdlets to verify that all agent groups, queues, and workflows moved successfully.</span></span> 
  
<span data-ttu-id="39ee8-121">Quando você migra grupos de resposta, os grupos de resposta herdados não são removidos.</span><span class="sxs-lookup"><span data-stu-id="39ee8-121">When you migrate response groups, the legacy response groups are not removed.</span></span> <span data-ttu-id="39ee8-122">Ao gerenciar grupos de resposta após a migração usando o Painel de Controle do Skype for Business Server ou o Shell de Gerenciamento do Skype for Business Server, você pode ver os grupos de resposta herdados e os grupos de resposta do Skype for Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="39ee8-122">When you manage response groups after migration by using either Skype for Business Server Control Panel or Skype for Business Server Management Shell, you can see both the legacy response groups and the Skype for Business Server 2019 response groups.</span></span> <span data-ttu-id="39ee8-123">Você deve aplicar atualizações apenas aos grupos de resposta do Skype for Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="39ee8-123">You should apply updates only to the Skype for Business Server 2019 response groups.</span></span> <span data-ttu-id="39ee8-124">Os grupos de resposta herdados são mantidos apenas para fins de reback.</span><span class="sxs-lookup"><span data-stu-id="39ee8-124">The legacy response groups are retained only for rollback purposes.</span></span> 
  
> [!CAUTION]
> <span data-ttu-id="39ee8-125">Após a conclusão da migração e a criação dos novos grupos de resposta, o Painel de Controle do Skype for Business Server e o Shell de Gerenciamento do Skype for Business Server exibirão as versões herdadas e do Skype for Business Server 2019 de cada grupo de resposta.</span><span class="sxs-lookup"><span data-stu-id="39ee8-125">After the migration has been completed and the new response groups have been created, the Skype for Business Server Control Panel and the Skype for Business Server Management Shell will display the legacy and Skype for Business Server 2019 versions of each response group.</span></span> <span data-ttu-id="39ee8-126">Não use o Painel de Controle do Skype for Business Server ou o Shell de Gerenciamento do Skype for Business Server para remover os grupos de resposta herdados.</span><span class="sxs-lookup"><span data-stu-id="39ee8-126">Do not use Skype for Business Server Control Panel or Skype for Business Server Management Shell to remove the legacy response groups.</span></span> <span data-ttu-id="39ee8-127">Se você remover um, o grupo de resposta correspondente criado durante a migração irá parar de funcionar.</span><span class="sxs-lookup"><span data-stu-id="39ee8-127">If you do remove one, the corresponding response group that was created during migration will stop working.</span></span> <span data-ttu-id="39ee8-128">Os grupos de resposta herdados serão removidos quando você descomissionar o pool herdados.</span><span class="sxs-lookup"><span data-stu-id="39ee8-128">The legacy response groups will be removed when you decommission the legacy pool.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="39ee8-129">Recomendamos que você não remova dados da sua implantação anterior até suspender o pool.</span><span class="sxs-lookup"><span data-stu-id="39ee8-129">We recommend that you do not remove any data from your previous deployment until you decommission the pool.</span></span> <span data-ttu-id="39ee8-130">Além disso, é altamente recomendável que você exporte os grupos de resposta imediatamente após a migração.</span><span class="sxs-lookup"><span data-stu-id="39ee8-130">In addition, we strongly recommend that you export response groups immediately after you migrate.</span></span> <span data-ttu-id="39ee8-131">Se um grupo de resposta herdado for removido, você poderá restaurar seus grupos de resposta do backup para que os grupos de resposta do Skype for Business Server 2019 possam ser executados novamente.</span><span class="sxs-lookup"><span data-stu-id="39ee8-131">If a legacy response group should get removed, you can then restore your response groups from the backup to get Skype for Business Server 2019 response groups running again.</span></span> 
  
<span data-ttu-id="39ee8-132">O Skype for Business Server 2019 apresenta um novo recurso do Grupo de Resposta chamado Tipo **de Fluxo de Trabalho.**</span><span class="sxs-lookup"><span data-stu-id="39ee8-132">Skype for Business Server 2019 introduces a new Response Group feature called **Workflow Type**.</span></span> <span data-ttu-id="39ee8-133">O **Tipo de fluxo de trabalho** pode ser **Gerenciado** ou **Não gerenciado**.</span><span class="sxs-lookup"><span data-stu-id="39ee8-133">**Workflow Type** can be **Managed** or **Unmanaged**.</span></span> <span data-ttu-id="39ee8-134">Todos os grupos de resposta são migrados com o **Tipo de fluxo de trabalho** definido para **Não gerenciado** e com uma lista Gerenciador vazia.</span><span class="sxs-lookup"><span data-stu-id="39ee8-134">All response groups are migrated with **Workflow Type** set to **Unmanaged** and with an empty Manager list.</span></span> 
  
<span data-ttu-id="39ee8-135">ao executar o cmdlet **Move-CsRgsConfiguration**, os grupos de agente, filas, fluxos de trabalho e arquivos de áudio permanecem no pool de legado para propósitos de reversão.</span><span class="sxs-lookup"><span data-stu-id="39ee8-135">When you run the **Move-CsRgsConfiguration** cmdlet, the agent groups, queues, workflows, and audio files remain in the legacy pool for rollback purposes.</span></span> <span data-ttu-id="39ee8-136">Entretanto, se for necessária uma reversão para o pool antigo, você precisará executar o cmdlet **Move-CsApplicationEndpoint** para transferir objetos de contato de volta para o pool antigo.</span><span class="sxs-lookup"><span data-stu-id="39ee8-136">If you do need to roll back to the legacy pool, however, you need to run the **Move-CsApplicationEndpoint** cmdlet to move contact objects back to the legacy pool.</span></span> 
  
<span data-ttu-id="39ee8-137">O procedimento a seguir para migrar as configurações do Grupo de Resposta presume que você tenha uma relação um-para-um entre seus pools herddos e os pools do Skype for Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="39ee8-137">The following procedure for migrating Response Group configurations assumes that you have a one-to-one relationship between your legacy pools and the Skype for Business Server 2019 pools.</span></span> <span data-ttu-id="39ee8-138">Se você planeja consolidar ou dividir pools durante a migração e implantação, será necessário planejar qual pool herdado é mapeado para qual pool do Skype for Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="39ee8-138">If you plan to consolidate or split up pools during your migration and deployment, you need to plan which legacy pool maps to which Skype for Business Server 2019 pool.</span></span>
  
## <a name="to-migrate-response-group-configurations"></a><span data-ttu-id="39ee8-139">Para migrar as configurações do Grupo de Resposta</span><span class="sxs-lookup"><span data-stu-id="39ee8-139">To migrate Response Group configurations</span></span>

1. <span data-ttu-id="39ee8-140">Faça logon no computador com uma conta membro do grupo RTCUniversalServerAdmins ou com direitos e permissões do administrador equivalentes.</span><span class="sxs-lookup"><span data-stu-id="39ee8-140">Log on to the computer with an account that is a member of the RTCUniversalServerAdmins group or has equivalent administrator rights and permissions.</span></span>
    
2. <span data-ttu-id="39ee8-141">Inicie o Shell de Gerenciamento do Skype for Business Server: Clique em **Iniciar,** Em Todos os **Programas,** clique em **Microsoft Skype for Business Server 2019** e, em seguida, clique no Shell de Gerenciamento do **Skype for Business Server.**</span><span class="sxs-lookup"><span data-stu-id="39ee8-141">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Skype for Business Server 2019**, and then click **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="39ee8-142">Execute:</span><span class="sxs-lookup"><span data-stu-id="39ee8-142">Run:</span></span>
    
   ```PowerShell
   Move-CsRgsConfiguration -Source <source pool FQDN> -Destination <destination pool FQDN>
   ```

    <span data-ttu-id="39ee8-143">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="39ee8-143">For example:</span></span>
    
   ```PowerShell
   Move-CsRgsConfiguration -Source skype-old.contoso.net -Destination skype-new.contoso.net
   ```

4. <span data-ttu-id="39ee8-144">Depois de migrar grupos de resposta e agentes para o pool do Skype for Business Server 2019, a URL que os agentes usam para entrar e sair é uma URL do Skype for Business Server 2019 e está disponível no **menu** Ferramentas.</span><span class="sxs-lookup"><span data-stu-id="39ee8-144">After you migrate response groups and agents to the Skype for Business Server 2019 pool, the URL that agents use to sign in and sign out is a Skype for Business Server 2019 URL and is available from the **Tools** menu.</span></span> <span data-ttu-id="39ee8-145">Lembre os agentes de atualizar qualquer referência, como indicadores, para o novo URL.</span><span class="sxs-lookup"><span data-stu-id="39ee8-145">Remind agents to update any references, such as bookmarks, to the new URL.</span></span> 
    
## <a name="to-verify-response-group-migration-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="39ee8-146">Para verificar a migração do Grupo de Resposta usando o Painel de Controle do Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="39ee8-146">To verify Response Group migration by using Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="39ee8-147">Faça logon no computador com uma conta membro do grupo RTCUniversalReadOnlyAdmins ou que seja pelo menos membro da função CsViewOnlyAdministrator.</span><span class="sxs-lookup"><span data-stu-id="39ee8-147">Log on to the computer with an account that is a member of RTCUniversalReadOnlyAdmins group or is minimally a member of the CsViewOnlyAdministrator role.</span></span>
    
2. <span data-ttu-id="39ee8-148">Abra uma janela do navegador e insira a URL do Administrador para abrir o Painel de Controle do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="39ee8-148">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> <span data-ttu-id="39ee8-149">Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o Painel de Controle do Skype for Business Server, consulte Open [Skype for Business Server 2019 administrative tools.](https://technet.microsoft.com/library/gg195741(v=ocs.15).aspx)</span><span class="sxs-lookup"><span data-stu-id="39ee8-149">For details about the different methods you can use to start Skype for Business Server Control Panel, see [Open Skype for Business Server 2019 administrative tools](https://technet.microsoft.com/library/gg195741(v=ocs.15).aspx).</span></span> 
    <!-- The above link points to un-rebranded 2013 content we will need to discuss rebrand or bring forward -->
3. <span data-ttu-id="39ee8-150">No painel de navegação à esquerda, clique em **Grupos de Resposta**.</span><span class="sxs-lookup"><span data-stu-id="39ee8-150">In the left navigation pane, click **Response Groups**.</span></span>
    
4. <span data-ttu-id="39ee8-151">Na guia **Fluxo de** Trabalho, verifique se todos os fluxos de trabalho em seu ambiente herdável estão incluídos na lista.</span><span class="sxs-lookup"><span data-stu-id="39ee8-151">On the **Workflow** tab, verify that all the workflows in your legacy environment are included in the list.</span></span> 
    
5. <span data-ttu-id="39ee8-152">Clique na **guia Fila** e verifique se todas as filas em seu ambiente herddo estão incluídas na lista.</span><span class="sxs-lookup"><span data-stu-id="39ee8-152">Click the **Queue** tab, and verify that all the queues in your legacy environment are included in the list.</span></span> 
    
6. <span data-ttu-id="39ee8-153">Clique na **guia** Grupo e verifique se todos os grupos de agentes em seu ambiente herdados estão incluídos na lista.</span><span class="sxs-lookup"><span data-stu-id="39ee8-153">Click the **Group** tab, and verify that all the agent groups in your legacy environment are included in the list.</span></span> 
    
## <a name="to-verify-response-group-migration-by-using-skype-for-business-server-management-shell"></a><span data-ttu-id="39ee8-154">Para verificar a migração do Grupo de Resposta usando o Shell de Gerenciamento do Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="39ee8-154">To verify Response Group migration by using Skype for Business Server Management Shell</span></span>

1. <span data-ttu-id="39ee8-155">Faça logon no computador com uma conta membro do grupo RTCUniversalReadOnlyAdmins ou que seja pelo menos membro da função CsViewOnlyAdministrator.</span><span class="sxs-lookup"><span data-stu-id="39ee8-155">Log on to the computer with an account that is a member of RTCUniversalReadOnlyAdmins group or is minimally a member of the CsViewOnlyAdministrator role.</span></span>
    
2. <span data-ttu-id="39ee8-156">Inicie o Shell de Gerenciamento do Skype for Business Server: Clique em **Iniciar,** Em Todos os **Programas,** clique em **Microsoft Skype for Business Server 2019** e, em seguida, clique no Shell de Gerenciamento do **Skype for Business Server.**</span><span class="sxs-lookup"><span data-stu-id="39ee8-156">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Skype for Business Server 2019**, and then click **Skype for Business Server Management Shell**.</span></span>
    
    <span data-ttu-id="39ee8-157">Para obter detalhes sobre os seguintes cmdlets, execute:</span><span class="sxs-lookup"><span data-stu-id="39ee8-157">For details about the following cmdlets, run:</span></span>
    
   ```PowerShell
   Get-Help <cmdlet name> -Detailed
   ```

3. <span data-ttu-id="39ee8-158">Execute:</span><span class="sxs-lookup"><span data-stu-id="39ee8-158">Run:</span></span>
    
   ```PowerShell
   Get-CsRgsAgentGroup
   ```

4. <span data-ttu-id="39ee8-159">Verifique se todos os grupos de agentes em seu ambiente herdados estão incluídos na lista.</span><span class="sxs-lookup"><span data-stu-id="39ee8-159">Verify that all the agent groups in your legacy environment are included in the list.</span></span>
    
5. <span data-ttu-id="39ee8-160">Execute:</span><span class="sxs-lookup"><span data-stu-id="39ee8-160">Run:</span></span>
    
   ```PowerShell
   Get-CsRgsQueue
   ```

6. <span data-ttu-id="39ee8-161">Verifique se todas as filas em seu ambiente herdável estão incluídas na lista.</span><span class="sxs-lookup"><span data-stu-id="39ee8-161">Verify that all the queues in your legacy environment are included in the list.</span></span>
    
7. <span data-ttu-id="39ee8-162">Execute:</span><span class="sxs-lookup"><span data-stu-id="39ee8-162">Run:</span></span>
    
   ```PowerShell
   Get-CsRgsWorkflow
   ```

8. <span data-ttu-id="39ee8-163">Verifique se todos os fluxos de trabalho em seu ambiente herdável estão incluídos na lista.</span><span class="sxs-lookup"><span data-stu-id="39ee8-163">Verify that all the workflows in your legacy environment are included in the list.</span></span>
    

