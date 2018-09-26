---
title: Migrar grupos de resposta
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Depois que os usuários são movidos para Skype para Business Server 2019 pools, você pode migrar seus grupos de resposta. Migrando de resposta grupos inclui copiando os grupos de operadores, filas, fluxos de trabalho, arquivos de áudio e mover objetos de contato do grupo de resposta da implantação herdada para o Skype para Business Server 2019 pool. Após migrar seus grupos de resposta de legado, as chamadas para os grupos de resposta são manipuladas pelo aplicativo grupo de resposta no Skype para Business Server 2019 pool. Chamadas para grupos de resposta não são processadas pelo pool herdado.
ms.openlocfilehash: bdff9b96b73e925fb68b4a2f9bebb9b23edb4b56
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/24/2018
ms.locfileid: "25028016"
---
# <a name="migrate-response-groups"></a><span data-ttu-id="027bd-106">Migrar grupos de resposta</span><span class="sxs-lookup"><span data-stu-id="027bd-106">Migrate response groups</span></span>

<span data-ttu-id="027bd-107">Depois que os usuários são movidos para Skype para Business Server 2019 pools, você pode migrar seus grupos de resposta.</span><span class="sxs-lookup"><span data-stu-id="027bd-107">After your users are moved to Skype for Business Server 2019 pools, you can migrate your response groups.</span></span> <span data-ttu-id="027bd-108">Migrando de resposta grupos inclui copiando os grupos de operadores, filas, fluxos de trabalho, arquivos de áudio e mover objetos de contato do grupo de resposta da implantação herdada para o Skype para Business Server 2019 pool.</span><span class="sxs-lookup"><span data-stu-id="027bd-108">Migrating response groups includes copying agent groups, queues, workflows, audio files, and moving Response Group contact objects from the legacy deployment to the Skype for Business Server 2019 pool.</span></span> <span data-ttu-id="027bd-109">Após migrar seus grupos de resposta de legado, as chamadas para os grupos de resposta são manipuladas pelo aplicativo grupo de resposta no Skype para Business Server 2019 pool.</span><span class="sxs-lookup"><span data-stu-id="027bd-109">After you migrate your legacy response groups, calls to the response groups are handled by the Response Group application in the Skype for Business Server 2019 pool.</span></span> <span data-ttu-id="027bd-110">Chamadas para grupos de resposta não são processadas pelo pool herdado.</span><span class="sxs-lookup"><span data-stu-id="027bd-110">Calls to response groups are no longer handled by the legacy pool.</span></span>
  
> [!NOTE]
> <span data-ttu-id="027bd-111">Embora você possa migrar grupos de resposta antes de mover todos os usuários para o Skype para Business Server 2019 pool, é recomendável que você mova todos os usuários pela primeira vez.</span><span class="sxs-lookup"><span data-stu-id="027bd-111">Although you can migrate response groups before you move all users to the Skype for Business Server 2019 pool, we recommend that you move all users first.</span></span> <span data-ttu-id="027bd-112">Especificamente, os usuários que são os operadores do grupo de resposta não terá funcionalidade completa dos novos recursos até que eles serão movidos para o Skype para Business Server 2019 pool.</span><span class="sxs-lookup"><span data-stu-id="027bd-112">In particular, users who are response group agents will not have full functionality of new features until they are moved to the Skype for Business Server 2019 pool.</span></span> 
  
<span data-ttu-id="027bd-113">Antes de migrar os grupos de resposta, você deve ter implantado um Skype para Business Server 2019 pool que inclui o aplicativo grupo de resposta.</span><span class="sxs-lookup"><span data-stu-id="027bd-113">Before you migrate response groups, you must have deployed a Skype for Business Server 2019 pool that includes the Response Group application.</span></span> <span data-ttu-id="027bd-114">Aplicativo grupo de resposta é instalado e ativado por padrão ao implantar o Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="027bd-114">The Response Group application is installed and activated by default when you deploy Enterprise Voice.</span></span> <span data-ttu-id="027bd-115">Você pode garantir que o aplicativo de grupo de resposta está instalado, executando o cmdlet **Get-CsService-ApplicationServer** .</span><span class="sxs-lookup"><span data-stu-id="027bd-115">You can ensure that the Response Group application is installed by running the **Get-CsService -ApplicationServer** cmdlet.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="027bd-116">Você pode criar novo Skype para grupos de resposta Business Server 2019 no Skype para Business Server 2019 pool antes de migrar seus grupos de resposta de legado.</span><span class="sxs-lookup"><span data-stu-id="027bd-116">You can create new Skype for Business Server 2019 response groups in the Skype for Business Server 2019 pool before you migrate your legacy response groups.</span></span> 
  
<span data-ttu-id="027bd-117">Para migrar grupos de resposta de um pool herdado para o Skype para Business Server 2019, você deve executar o cmdlet **Move-CsRgsConfiguration** .</span><span class="sxs-lookup"><span data-stu-id="027bd-117">To migrate response groups from a legacy pool to the Skype for Business Server 2019, you run the **Move-CsRgsConfiguration** cmdlet.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="027bd-118">O cmdlet de migração do grupo de resposta move a configuração de grupo de resposta para todo o pool.</span><span class="sxs-lookup"><span data-stu-id="027bd-118">The Response Group migration cmdlet moves the Response Group configuration for the entire pool.</span></span> <span data-ttu-id="027bd-119">Você não pode selecionar grupos específicos, filas ou fluxos de trabalho para migrar.</span><span class="sxs-lookup"><span data-stu-id="027bd-119">You cannot select specific groups, queues, or workflows to migrate.</span></span> 
  
<span data-ttu-id="027bd-120">Depois de migrar os grupos de resposta, você precisa usar o Skype para painel de controle do Business Server ou Skype para cmdlets do Shell de gerenciamento do servidor de negócios para verificar se todos os grupos de operadores, filas e fluxos de trabalho foram movidos com êxito.</span><span class="sxs-lookup"><span data-stu-id="027bd-120">After you migrate the response groups, you need to use Skype for Business Server Control Panel or Skype for Business Server Management Shell cmdlets to verify that all agent groups, queues, and workflows moved successfully.</span></span> 
  
<span data-ttu-id="027bd-121">Quando você migra grupos de resposta, os grupos de resposta de legado não serão removidos.</span><span class="sxs-lookup"><span data-stu-id="027bd-121">When you migrate response groups, the legacy response groups are not removed.</span></span> <span data-ttu-id="027bd-122">Quando você gerencia grupos de resposta após a migração usando qualquer um dos Skype para painel de controle do Business Server ou Skype do Shell de gerenciamento do servidor de negócios, você pode ver os grupos de resposta de legado e o Skype Business Server 2019 grupos de resposta.</span><span class="sxs-lookup"><span data-stu-id="027bd-122">When you manage response groups after migration by using either Skype for Business Server Control Panel or Skype for Business Server Management Shell, you can see both the legacy response groups and the Skype for Business Server 2019 response groups.</span></span> <span data-ttu-id="027bd-123">Você deve aplicar atualizações somente do Skype Business Server 2019 grupos de resposta.</span><span class="sxs-lookup"><span data-stu-id="027bd-123">You should apply updates only to the Skype for Business Server 2019 response groups.</span></span> <span data-ttu-id="027bd-124">Os grupos de resposta de legado são mantidos apenas para fins de reversão.</span><span class="sxs-lookup"><span data-stu-id="027bd-124">The legacy response groups are retained only for rollback purposes.</span></span> 
  
> [!CAUTION]
> <span data-ttu-id="027bd-125">Após a migração foi concluída e os novos grupos de resposta tem sido criados, o Skype para painel de controle do Business Server e do Skype do Shell de gerenciamento do servidor de negócios exibirá o antigo e Skype para as versões Business Server 2019 cada resposta grupo.</span><span class="sxs-lookup"><span data-stu-id="027bd-125">After the migration has been completed and the new response groups have been created, the Skype for Business Server Control Panel and the Skype for Business Server Management Shell will display the legacy and Skype for Business Server 2019 versions of each response group.</span></span> <span data-ttu-id="027bd-126">Não use Skype para painel de controle do Business Server ou Skype para Business Server Management Shell para remover os grupos de resposta de legado.</span><span class="sxs-lookup"><span data-stu-id="027bd-126">Do not use Skype for Business Server Control Panel or Skype for Business Server Management Shell to remove the legacy response groups.</span></span> <span data-ttu-id="027bd-127">Se você remover um, o grupo de resposta correspondente que foi criado durante a migração irá parar de funcionar.</span><span class="sxs-lookup"><span data-stu-id="027bd-127">If you do remove one, the corresponding response group that was created during migration will stop working.</span></span> <span data-ttu-id="027bd-128">Os grupos de respostas antigos serão removidos quando você encerrar o pool herdado.</span><span class="sxs-lookup"><span data-stu-id="027bd-128">The legacy response groups will be removed when you decommission the legacy pool.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="027bd-129">Recomendamos que você não remova todos os dados da sua implantação anterior até que você encerrar o pool.</span><span class="sxs-lookup"><span data-stu-id="027bd-129">We recommend that you do not remove any data from your previous deployment until you decommission the pool.</span></span> <span data-ttu-id="027bd-130">Além disso, é altamente recomendável que você exporte os grupos de resposta imediatamente após migrar.</span><span class="sxs-lookup"><span data-stu-id="027bd-130">In addition, we strongly recommend that you export response groups immediately after you migrate.</span></span> <span data-ttu-id="027bd-131">Se um grupo de resposta de legado deve obter removido, você poderá então restaurar seus grupos de resposta do backup para obter Skype para grupos de resposta Business Server 2019 executar novamente.</span><span class="sxs-lookup"><span data-stu-id="027bd-131">If a legacy response group should get removed, you can then restore your response groups from the backup to get Skype for Business Server 2019 response groups running again.</span></span> 
  
<span data-ttu-id="027bd-132">Skype para Business Server 2019 introduz um novo recurso de grupo de resposta chamado **Tipo de fluxo de trabalho**.</span><span class="sxs-lookup"><span data-stu-id="027bd-132">Skype for Business Server 2019 introduces a new Response Group feature called **Workflow Type**.</span></span> <span data-ttu-id="027bd-133">**Tipo de fluxo de trabalho** pode ser **gerenciado** ou **não gerenciado**.</span><span class="sxs-lookup"><span data-stu-id="027bd-133">**Workflow Type** can be **Managed** or **Unmanaged**.</span></span> <span data-ttu-id="027bd-134">Todos os grupos de resposta são migrados com o **Tipo de fluxo de trabalho** definido como **não gerenciado** e uma lista vazia do gerente.</span><span class="sxs-lookup"><span data-stu-id="027bd-134">All response groups are migrated with **Workflow Type** set to **Unmanaged** and with an empty Manager list.</span></span> 
  
<span data-ttu-id="027bd-135">Quando você executa o cmdlet **Move-CsRgsConfiguration** , os grupos de operadores, filas, fluxos de trabalho e arquivos de áudio permanecem no pool herdado para fins de reversão.</span><span class="sxs-lookup"><span data-stu-id="027bd-135">When you run the **Move-CsRgsConfiguration** cmdlet, the agent groups, queues, workflows, and audio files remain in the legacy pool for rollback purposes.</span></span> <span data-ttu-id="027bd-136">No entanto, se você precisar reverter para o pool herdado, você precisará executar o cmdlet **Move-CsApplicationEndpoint** para mover objetos de contato de volta para o pool herdado.</span><span class="sxs-lookup"><span data-stu-id="027bd-136">If you do need to roll back to the legacy pool, however, you need to run the **Move-CsApplicationEndpoint** cmdlet to move contact objects back to the legacy pool.</span></span> 
  
<span data-ttu-id="027bd-137">O procedimento a seguir para migrar configurações de grupo de resposta pressupõe que você tenha um relacionamento de um para um entre os pools de legado e do Skype para Business Server 2019 pools.</span><span class="sxs-lookup"><span data-stu-id="027bd-137">The following procedure for migrating Response Group configurations assumes that you have a one-to-one relationship between your legacy pools and the Skype for Business Server 2019 pools.</span></span> <span data-ttu-id="027bd-138">Se você pretende consolidar ou dividida até pools durante sua migração e implantação, você precisa planejar qual pool herdado mapeia para o qual Skype para Business Server 2019 pool.</span><span class="sxs-lookup"><span data-stu-id="027bd-138">If you plan to consolidate or split up pools during your migration and deployment, you need to plan which legacy pool maps to which Skype for Business Server 2019 pool.</span></span>
  
## <a name="to-migrate-response-group-configurations"></a><span data-ttu-id="027bd-139">Para migrar as configurações de grupo de resposta</span><span class="sxs-lookup"><span data-stu-id="027bd-139">To migrate Response Group configurations</span></span>

1. <span data-ttu-id="027bd-140">Faça logon no computador com uma conta que seja membro do grupo RTCUniversalServerAdmins ou tenha permissões e direitos de administrador equivalentes.</span><span class="sxs-lookup"><span data-stu-id="027bd-140">Log on to the computer with an account that is a member of the RTCUniversalServerAdmins group or has equivalent administrator rights and permissions.</span></span>
    
2. <span data-ttu-id="027bd-141">Inicie o Skype do Shell de gerenciamento do servidor de negócios: clique em **Iniciar**, clique em **Todos os programas**, clique em **Microsoft Skype para Business Server 2019**e, em seguida, clique em **Skype do Shell de gerenciamento do servidor de negócios**.</span><span class="sxs-lookup"><span data-stu-id="027bd-141">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Skype for Business Server 2019**, and then click **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="027bd-142">Execute:</span><span class="sxs-lookup"><span data-stu-id="027bd-142">Run:</span></span>
    
  ```
  Move-CsRgsConfiguration -Source <source pool FQDN> -Destination <destination pool FQDN>
  ```

    <span data-ttu-id="027bd-143">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="027bd-143">For example:</span></span>
    
  ```
  Move-CsRgsConfiguration -Source skype-old.contoso.net -Destination skype-new.contoso.net
  ```

4. <span data-ttu-id="027bd-144">Após migrar grupos de resposta e operadores para o Skype para Business Server 2019 pool, a URL que os agentes usam para entrar e sair é um Skype para Business Server 2019 URL e está disponível no menu **Ferramentas** .</span><span class="sxs-lookup"><span data-stu-id="027bd-144">After you migrate response groups and agents to the Skype for Business Server 2019 pool, the URL that agents use to sign in and sign out is a Skype for Business Server 2019 URL and is available from the **Tools** menu.</span></span> <span data-ttu-id="027bd-145">Lembre agentes para atualizar todas as referências, como indicadores, para a nova URL.</span><span class="sxs-lookup"><span data-stu-id="027bd-145">Remind agents to update any references, such as bookmarks, to the new URL.</span></span> 
    
## <a name="to-verify-response-group-migration-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="027bd-146">Para verificar a migração do grupo de resposta usando Skype para o painel de controle do servidor de negócios</span><span class="sxs-lookup"><span data-stu-id="027bd-146">To verify Response Group migration by using Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="027bd-147">Faça logon no computador com uma conta que seja membro do grupo RTCUniversalReadOnlyAdmins ou minimamente membro da função CsViewOnlyAdministrator.</span><span class="sxs-lookup"><span data-stu-id="027bd-147">Log on to the computer with an account that is a member of RTCUniversalReadOnlyAdmins group or is minimally a member of the CsViewOnlyAdministrator role.</span></span>
    
2. <span data-ttu-id="027bd-148">Abra uma janela do navegador e insira a URL do administrador para abrir o Skype para painel de controle do servidor de negócios.</span><span class="sxs-lookup"><span data-stu-id="027bd-148">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> <span data-ttu-id="027bd-149">Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o Skype para painel de controle do Business Server, consulte [Open Skype para ferramentas administrativas do Business Server 2019](https://technet.microsoft.com/en-us/library/gg195741(v=ocs.15).aspx).</span><span class="sxs-lookup"><span data-stu-id="027bd-149">For details about the different methods you can use to start Skype for Business Server Control Panel, see [Open Skype for Business Server 2019 administrative tools](https://technet.microsoft.com/en-us/library/gg195741(v=ocs.15).aspx).</span></span> 
    <!-- The above link points to un-rebranded 2013 content we will need to discuss rebrand or bring forward -->
3. <span data-ttu-id="027bd-150">No painel de navegação à esquerda, clique em **Grupos de resposta**.</span><span class="sxs-lookup"><span data-stu-id="027bd-150">In the left navigation pane, click **Response Groups**.</span></span>
    
4. <span data-ttu-id="027bd-151">Na guia **fluxo de trabalho** , verifique se todos os fluxos de trabalho no seu ambiente herdado estão incluídos na lista.</span><span class="sxs-lookup"><span data-stu-id="027bd-151">On the **Workflow** tab, verify that all the workflows in your legacy environment are included in the list.</span></span> 
    
5. <span data-ttu-id="027bd-152">Clique na guia **fila** e verifique se todas as filas em seu ambiente herdado estão incluídas na lista.</span><span class="sxs-lookup"><span data-stu-id="027bd-152">Click the **Queue** tab, and verify that all the queues in your legacy environment are included in the list.</span></span> 
    
6. <span data-ttu-id="027bd-153">Clique na guia **grupo** e verificar se todos os grupos de agente no seu ambiente herdado estão incluídos na lista.</span><span class="sxs-lookup"><span data-stu-id="027bd-153">Click the **Group** tab, and verify that all the agent groups in your legacy environment are included in the list.</span></span> 
    
## <a name="to-verify-response-group-migration-by-using-skype-for-business-server-management-shell"></a><span data-ttu-id="027bd-154">Para verificar a migração do grupo de resposta usando Skype do Shell de gerenciamento do servidor de negócios</span><span class="sxs-lookup"><span data-stu-id="027bd-154">To verify Response Group migration by using Skype for Business Server Management Shell</span></span>

1. <span data-ttu-id="027bd-155">Faça logon no computador com uma conta que seja membro do grupo RTCUniversalReadOnlyAdmins ou minimamente membro da função CsViewOnlyAdministrator.</span><span class="sxs-lookup"><span data-stu-id="027bd-155">Log on to the computer with an account that is a member of RTCUniversalReadOnlyAdmins group or is minimally a member of the CsViewOnlyAdministrator role.</span></span>
    
2. <span data-ttu-id="027bd-156">Inicie o Skype do Shell de gerenciamento do servidor de negócios: clique em **Iniciar**, clique em **Todos os programas**, clique em **Microsoft Skype para Business Server 2019**e, em seguida, clique em **Skype do Shell de gerenciamento do servidor de negócios**.</span><span class="sxs-lookup"><span data-stu-id="027bd-156">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Skype for Business Server 2019**, and then click **Skype for Business Server Management Shell**.</span></span>
    
    <span data-ttu-id="027bd-157">Para obter detalhes sobre os seguintes cmdlets, execute:</span><span class="sxs-lookup"><span data-stu-id="027bd-157">For details about the following cmdlets, run:</span></span>
    
  ```
  Get-Help <cmdlet name> -Detailed
  ```

3. <span data-ttu-id="027bd-158">Execute:</span><span class="sxs-lookup"><span data-stu-id="027bd-158">Run:</span></span>
    
  ```
  Get-CsRgsAgentGroup
  ```

4. <span data-ttu-id="027bd-159">Verifique se todos os grupos de agente no seu ambiente herdado estão incluídos na lista.</span><span class="sxs-lookup"><span data-stu-id="027bd-159">Verify that all the agent groups in your legacy environment are included in the list.</span></span>
    
5. <span data-ttu-id="027bd-160">Execute:</span><span class="sxs-lookup"><span data-stu-id="027bd-160">Run:</span></span>
    
  ```
  Get-CsRgsQueue
  ```

6. <span data-ttu-id="027bd-161">Verifique se todas as filas em seu ambiente herdado estão incluídas na lista.</span><span class="sxs-lookup"><span data-stu-id="027bd-161">Verify that all the queues in your legacy environment are included in the list.</span></span>
    
7. <span data-ttu-id="027bd-162">Execute:</span><span class="sxs-lookup"><span data-stu-id="027bd-162">Run:</span></span>
    
  ```
  Get-CsRgsWorkflow
  ```

8. <span data-ttu-id="027bd-163">Verifique se todos os fluxos de trabalho no seu ambiente herdado estão incluídos na lista.</span><span class="sxs-lookup"><span data-stu-id="027bd-163">Verify that all the workflows in your legacy environment are included in the list.</span></span>
    

