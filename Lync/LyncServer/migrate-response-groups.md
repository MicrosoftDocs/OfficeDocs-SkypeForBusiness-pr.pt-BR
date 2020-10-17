---
title: Migrar grupos de resposta
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Migrate response groups
ms:assetid: 43741ae7-c871-4573-b660-f2f5febc0856
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204854(v=OCS.15)
ms:contentKeyID: 48184020
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9b51fd9bd16da2f6cf135332d68c70c4b4714cdd
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48527498"
---
# <a name="migrate-response-groups"></a><span data-ttu-id="fdcef-102">Migrar grupos de resposta</span><span class="sxs-lookup"><span data-stu-id="fdcef-102">Migrate response groups</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="fdcef-103">_**Última modificação do tópico:** 2013-09-23_</span><span class="sxs-lookup"><span data-stu-id="fdcef-103">_**Topic Last Modified:** 2013-09-23_</span></span>

<span data-ttu-id="fdcef-104">Depois que os usuários forem movidos para pools do Lync Server 2013, você poderá migrar seus grupos de resposta.</span><span class="sxs-lookup"><span data-stu-id="fdcef-104">After your users are moved to Lync Server 2013 pools, you can migrate your response groups.</span></span> <span data-ttu-id="fdcef-105">Migrar grupos de resposta inclui copiar grupos de agente, filas, fluxos de trabalho, arquivos de áudio e mover objetos de contato de grupo de resposta da implantação herdada para o pool do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="fdcef-105">Migrating response groups includes copying agent groups, queues, workflows, audio files, and moving Response Group contact objects from the legacy deployment to the Lync Server 2013 pool.</span></span> <span data-ttu-id="fdcef-106">Depois de migrar seus grupos de resposta herdados, as chamadas para os grupos de resposta são tratadas pelo aplicativo grupo de resposta no pool do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="fdcef-106">After you migrate your legacy response groups, calls to the response groups are handled by the Response Group application in the Lync Server 2013 pool.</span></span> <span data-ttu-id="fdcef-107">As chamadas aos grupos de resposta não serão mais processadas pelo pool antigo.</span><span class="sxs-lookup"><span data-stu-id="fdcef-107">Calls to response groups are no longer handled by the legacy pool.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="fdcef-108">Embora você possa migrar grupos de resposta antes de mover todos os usuários para o pool do Lync Server 2013, recomendamos que você mova todos os usuários primeiro.</span><span class="sxs-lookup"><span data-stu-id="fdcef-108">Although you can migrate response groups before you move all users to the Lync Server 2013 pool, we recommend that you move all users first.</span></span> <span data-ttu-id="fdcef-109">Em particular, os usuários que são agentes de grupo de resposta não terão a funcionalidade completa dos novos recursos até que sejam movidos para o pool do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="fdcef-109">In particular, users who are response group agents will not have full functionality of new features until they are moved to the Lync Server 2013 pool.</span></span>



</div>

<span data-ttu-id="fdcef-110">Antes de migrar grupos de resposta, você deve ter implantado um pool do Lync Server 2013 que inclui o aplicativo grupo de resposta.</span><span class="sxs-lookup"><span data-stu-id="fdcef-110">Before you migrate response groups, you must have deployed a Lync Server 2013 pool that includes the Response Group application.</span></span> <span data-ttu-id="fdcef-111">O aplicativo grupo de resposta é instalado e ativado por padrão ao implantar o Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="fdcef-111">The Response Group application is installed and activated by default when you deploy Enterprise Voice.</span></span> <span data-ttu-id="fdcef-112">Você pode garantir que o aplicativo grupo de resposta seja instalado executando o cmdlet **Get-CsService – ApplicationServer** .</span><span class="sxs-lookup"><span data-stu-id="fdcef-112">You can ensure that the Response Group application is installed by running the **Get-CsService –ApplicationServer** cmdlet.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="fdcef-113">Você pode criar novos grupos de resposta do Lync Server 2013 no pool do Lync Server 2013 antes de migrar seus grupos de resposta herdados.</span><span class="sxs-lookup"><span data-stu-id="fdcef-113">You can create new Lync Server 2013 response groups in the Lync Server 2013 pool before you migrate your legacy response groups.</span></span>



</div>

<span data-ttu-id="fdcef-114">Para migrar grupos de resposta de um pool herdado para o Lync Server 2013, execute o cmdlet **move-CsRgsConfiguration** .</span><span class="sxs-lookup"><span data-stu-id="fdcef-114">To migrate response groups from a legacy pool to the Lync Server 2013, you run the **Move-CsRgsConfiguration** cmdlet.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="fdcef-115">O cmdlet de migração do grupo de resposta move a configuração do grupo de resposta para todo o pool.</span><span class="sxs-lookup"><span data-stu-id="fdcef-115">The Response Group migration cmdlet moves the Response Group configuration for the entire pool.</span></span> <span data-ttu-id="fdcef-116">Não é possível selecionar grupos, filas e fluxos de trabalho específicos para migração.</span><span class="sxs-lookup"><span data-stu-id="fdcef-116">You cannot select specific groups, queues, or workflows to migrate.</span></span>



</div>

<span data-ttu-id="fdcef-117">Após migrar os grupos de resposta, você precisará usar os cmdlets do painel de controle do Lync Server ou do Shell de gerenciamento do Lync Server para verificar se todos os grupos de agentes, filas e fluxos de trabalho foram movidos com êxito.</span><span class="sxs-lookup"><span data-stu-id="fdcef-117">After you migrate the response groups, you need to use Lync Server Control Panel or Lync Server Management Shell cmdlets to verify that all agent groups, queues, and workflows moved successfully.</span></span>

<span data-ttu-id="fdcef-118">Ao migrar grupos de resposta, os grupos de resposta do Lync Server 2010 não são removidos.</span><span class="sxs-lookup"><span data-stu-id="fdcef-118">When you migrate response groups, the Lync Server 2010 response groups are not removed.</span></span> <span data-ttu-id="fdcef-119">Ao gerenciar grupos de resposta após a migração usando o painel de controle do Lync Server ou o Shell de gerenciamento do Lync Server, você pode ver os grupos de resposta do Lync Server 2010 e os grupos de resposta do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="fdcef-119">When you manage response groups after migration by using either Lync Server Control Panel or Lync Server Management Shell, you can see both the Lync Server 2010 response groups and the Lync Server 2013 response groups.</span></span> <span data-ttu-id="fdcef-120">Você deve aplicar as atualizações somente aos grupos de resposta do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="fdcef-120">You should apply updates only to the Lync Server 2013 response groups.</span></span> <span data-ttu-id="fdcef-121">Os grupos de resposta do Lync Server 2010 são mantidos apenas para fins de recuperação.</span><span class="sxs-lookup"><span data-stu-id="fdcef-121">The Lync Server 2010 response groups are retained only for rollback purposes.</span></span>

<div>


> [!WARNING]  
> <span data-ttu-id="fdcef-122">Após a conclusão da migração e os novos grupos de resposta terem sido criados, o painel de controle do Lync Server e o Shell de gerenciamento do Lync Server exibirão as versões do Lync Server 2010 e do Lync Server 2013 de cada grupo de resposta.</span><span class="sxs-lookup"><span data-stu-id="fdcef-122">After the migration has been completed and the new response groups have been created, the Lync Server Control Panel and the Lync Server Management Shell will display the Lync Server 2010 and Lync Server 2013 versions of each response group.</span></span> <span data-ttu-id="fdcef-123">Não use o painel de controle do Lync Server ou o Shell de gerenciamento do Lync Server para remover os grupos de resposta do Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="fdcef-123">Do not use Lync Server Control Panel or Lync Server Management Shell to remove the Lync Server 2010 response groups.</span></span> <span data-ttu-id="fdcef-124">Se você remover um, o grupo de resposta correspondente criado durante a migração deixará de funcionar.</span><span class="sxs-lookup"><span data-stu-id="fdcef-124">If you do remove one, the corresponding response group that was created during migration will stop working.</span></span> <span data-ttu-id="fdcef-125">Os grupos de resposta do Lync Server 2010 serão removidos quando você encerrar o pool do Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="fdcef-125">The Lync Server 2010 response groups will be removed when you decommission the Lync Server 2010 pool.</span></span>



</div>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="fdcef-126">Recomendamos que você não remova dados da sua implantação anterior até suspender o pool.</span><span class="sxs-lookup"><span data-stu-id="fdcef-126">We recommend that you do not remove any data from your previous deployment until you decommission the pool.</span></span> <span data-ttu-id="fdcef-127">Além disso, é altamente recomendável que você exporte os grupos de resposta imediatamente após a migração.</span><span class="sxs-lookup"><span data-stu-id="fdcef-127">In addition, we strongly recommend that you export response groups immediately after you migrate.</span></span> <span data-ttu-id="fdcef-128">Se um grupo de resposta do Lync Server 2010 deve ser removido, você pode restaurar seus grupos de resposta do backup para obter os grupos de resposta do Lync Server 2013 em execução novamente.</span><span class="sxs-lookup"><span data-stu-id="fdcef-128">If a Lync Server 2010 response group should get removed, you can then restore your response groups from the backup to get Lync Server 2013 response groups running again.</span></span>



</div>

<span data-ttu-id="fdcef-129">O Lync Server 2013 introduz um novo recurso de grupo de resposta chamado **tipo de fluxo de trabalho**.</span><span class="sxs-lookup"><span data-stu-id="fdcef-129">Lync Server 2013 introduces a new Response Group feature called **Workflow Type**.</span></span> <span data-ttu-id="fdcef-130">O **Tipo de fluxo de trabalho** pode ser **Gerenciado** ou **Não gerenciado**.</span><span class="sxs-lookup"><span data-stu-id="fdcef-130">**Workflow Type** can be **Managed** or **Unmanaged**.</span></span> <span data-ttu-id="fdcef-131">Todos os grupos de resposta são migrados com o **Tipo de fluxo de trabalho** definido para **Não gerenciado** e com uma lista Gerenciador vazia.</span><span class="sxs-lookup"><span data-stu-id="fdcef-131">All response groups are migrated with **Workflow Type** set to **Unmanaged** and with an empty Manager list.</span></span>

<span data-ttu-id="fdcef-132">ao executar o cmdlet **Move-CsRgsConfiguration**, os grupos de agente, filas, fluxos de trabalho e arquivos de áudio permanecem no pool de legado para propósitos de reversão.</span><span class="sxs-lookup"><span data-stu-id="fdcef-132">When you run the **Move-CsRgsConfiguration** cmdlet, the agent groups, queues, workflows, and audio files remain in the legacy pool for rollback purposes.</span></span> <span data-ttu-id="fdcef-133">Entretanto, se for necessária uma reversão para o pool antigo, você precisará executar o cmdlet **Move-CsApplicationEndpoint** para transferir objetos de contato de volta para o pool antigo.</span><span class="sxs-lookup"><span data-stu-id="fdcef-133">If you do need to roll back to the legacy pool, however, you need to run the **Move-CsApplicationEndpoint** cmdlet to move contact objects back to the legacy pool.</span></span>

<span data-ttu-id="fdcef-134">O procedimento a seguir para migrar configurações de grupo de resposta pressupõe que você tenha uma relação um-para-um entre seus pools herdados e os pools do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="fdcef-134">The following procedure for migrating Response Group configurations assumes that you have a one-to-one relationship between your legacy pools and the Lync Server 2013 pools.</span></span> <span data-ttu-id="fdcef-135">Se você planeja consolidar ou dividir pools durante sua migração e implantação, precisa planejar quais pools herdados mapeiam para qual Lync Server 2013 pool.</span><span class="sxs-lookup"><span data-stu-id="fdcef-135">If you plan to consolidate or split up pools during your migration and deployment, you need to plan which legacy pool maps to which Lync Server 2013 pool.</span></span>

<div>

## <a name="to-migrate-response-group-configurations"></a><span data-ttu-id="fdcef-136">Para migrar configurações de grupo de resposta</span><span class="sxs-lookup"><span data-stu-id="fdcef-136">To migrate Response Group configurations</span></span>

1.  <span data-ttu-id="fdcef-137">Faça logon no computador com uma conta membro do grupo RTCUniversalServerAdmins ou com direitos e permissões do administrador equivalentes.</span><span class="sxs-lookup"><span data-stu-id="fdcef-137">Log on to the computer with an account that is a member of the RTCUniversalServerAdmins group or has equivalent administrator rights and permissions.</span></span>

2.  <span data-ttu-id="fdcef-138">Inicie o Shell de Gerenciamento do Lync Server: clique em **Iniciar**, em **Todos os Programas**, em **Microsoft Lync Server 2013** e em **Shell de Gerenciamento do Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="fdcef-138">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="fdcef-139">Sejam</span><span class="sxs-lookup"><span data-stu-id="fdcef-139">Run:</span></span>
    
        Move-CsRgsConfiguration -Source <source pool FQDN> -Destination <destination pool FQDN>
    
    <span data-ttu-id="fdcef-140">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="fdcef-140">For example:</span></span>
    
        Move-CsRgsConfiguration -Source lync-old.contoso.net -Destination lync-new.contoso.net

4.  <span data-ttu-id="fdcef-141">Após migrar grupos de resposta e agentes para o pool do Lync Server 2013, a URL que os agentes usam para entrar e sair é uma URL 2013 do Lync Server e está disponível no menu **ferramentas** .</span><span class="sxs-lookup"><span data-stu-id="fdcef-141">After you migrate response groups and agents to the Lync Server 2013 pool, the URL that agents use to sign in and sign out is a Lync Server 2013 URL and is available from the **Tools** menu.</span></span> <span data-ttu-id="fdcef-142">Lembre os agentes de atualizar qualquer referência, como indicadores, para o novo URL.</span><span class="sxs-lookup"><span data-stu-id="fdcef-142">Remind agents to update any references, such as bookmarks, to the new URL.</span></span>

</div>

<div>

## <a name="to-verify-response-group-migration-by-using-lync-server-control-panel"></a><span data-ttu-id="fdcef-143">Para verificar a migração do Grupo de Resposta usando o Painel de Controle do Lync Server</span><span class="sxs-lookup"><span data-stu-id="fdcef-143">To verify Response Group migration by using Lync Server Control Panel</span></span>

1.  <span data-ttu-id="fdcef-144">Faça logon no computador com uma conta membro do grupo RTCUniversalReadOnlyAdmins ou que seja pelo menos membro da função CsViewOnlyAdministrator.</span><span class="sxs-lookup"><span data-stu-id="fdcef-144">Log on to the computer with an account that is a member of RTCUniversalReadOnlyAdmins group or is minimally a member of the CsViewOnlyAdministrator role.</span></span>

2.  <span data-ttu-id="fdcef-145">Abra uma janela do navegador e insira a URL do Administrador para abrir o Painel de Controle do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="fdcef-145">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="fdcef-146">Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle do Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="fdcef-146">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="fdcef-147">No painel de navegação à esquerda, clique em **Grupos de Resposta**.</span><span class="sxs-lookup"><span data-stu-id="fdcef-147">In the left navigation pane, click **Response Groups**.</span></span>

4.  <span data-ttu-id="fdcef-148">Na guia **fluxo de trabalho** , verifique se todos os fluxos de trabalho em seu ambiente do Lync Server 2010 estão incluídos na lista.</span><span class="sxs-lookup"><span data-stu-id="fdcef-148">On the **Workflow** tab, verify that all the workflows in your Lync Server 2010 environment are included in the list.</span></span>

5.  <span data-ttu-id="fdcef-149">Clique na guia **fila** e verifique se todas as filas no seu ambiente do Lync Server 2010 estão incluídas na lista.</span><span class="sxs-lookup"><span data-stu-id="fdcef-149">Click the **Queue** tab, and verify that all the queues in your Lync Server 2010 environment are included in the list.</span></span>

6.  <span data-ttu-id="fdcef-150">Clique na guia **grupo** e verifique se todos os grupos de agente no seu ambiente do Lync Server 2010 estão incluídos na lista.</span><span class="sxs-lookup"><span data-stu-id="fdcef-150">Click the **Group** tab, and verify that all the agent groups in your Lync Server 2010 environment are included in the list.</span></span>

</div>

<div>

## <a name="to-verify-response-group-migration-by-using-lync-server-management-shell"></a><span data-ttu-id="fdcef-151">Para verificar a migração do grupo de resposta usando o Shell de gerenciamento do Lync Server</span><span class="sxs-lookup"><span data-stu-id="fdcef-151">To verify Response Group migration by using Lync Server Management Shell</span></span>

1.  <span data-ttu-id="fdcef-152">Faça logon no computador com uma conta membro do grupo RTCUniversalReadOnlyAdmins ou que seja pelo menos membro da função CsViewOnlyAdministrator.</span><span class="sxs-lookup"><span data-stu-id="fdcef-152">Log on to the computer with an account that is a member of RTCUniversalReadOnlyAdmins group or is minimally a member of the CsViewOnlyAdministrator role.</span></span>

2.  <span data-ttu-id="fdcef-153">Inicie o Shell de Gerenciamento do Lync Server: clique em **Iniciar**, em **Todos os Programas**, em **Microsoft Lync Server 2013** e em **Shell de Gerenciamento do Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="fdcef-153">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>
    
    <span data-ttu-id="fdcef-154">Para obter detalhes sobre os seguintes cmdlets, execute:</span><span class="sxs-lookup"><span data-stu-id="fdcef-154">For details about the following cmdlets, run:</span></span>
    
        Get-Help <cmdlet name> -Detailed

3.  <span data-ttu-id="fdcef-155">Sejam</span><span class="sxs-lookup"><span data-stu-id="fdcef-155">Run:</span></span>
    
        Get-CsRgsAgentGroup

4.  <span data-ttu-id="fdcef-156">Verifique se todos os grupos de agente no seu ambiente do Lync Server 2010 estão incluídos na lista.</span><span class="sxs-lookup"><span data-stu-id="fdcef-156">Verify that all the agent groups in your Lync Server 2010 environment are included in the list.</span></span>

5.  <span data-ttu-id="fdcef-157">Sejam</span><span class="sxs-lookup"><span data-stu-id="fdcef-157">Run:</span></span>
    
        Get-CsRgsQueue

6.  <span data-ttu-id="fdcef-158">Verifique se todas as filas no seu ambiente do Lync Server 2010 estão incluídas na lista.</span><span class="sxs-lookup"><span data-stu-id="fdcef-158">Verify that all the queues in your Lync Server 2010 environment are included in the list.</span></span>

7.  <span data-ttu-id="fdcef-159">Sejam</span><span class="sxs-lookup"><span data-stu-id="fdcef-159">Run:</span></span>
    
        Get-CsRgsWorkflow

8.  <span data-ttu-id="fdcef-160">Verifique se todos os fluxos de trabalho em seu ambiente do Lync Server 2010 estão incluídos na lista.</span><span class="sxs-lookup"><span data-stu-id="fdcef-160">Verify that all the workflows in your Lync Server 2010 environment are included in the list.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

