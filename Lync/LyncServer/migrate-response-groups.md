---
title: Migrar grupos de resposta
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Migrate response groups
ms:assetid: 43741ae7-c871-4573-b660-f2f5febc0856
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204854(v=OCS.15)
ms:contentKeyID: 48184020
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 23ef26b86b1de3fa7f9656cdb2ea82bb7a220948
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41762899"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="migrate-response-groups"></a><span data-ttu-id="aac16-102">Migrar grupos de resposta</span><span class="sxs-lookup"><span data-stu-id="aac16-102">Migrate response groups</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="aac16-103">_**Tópico da última modificação:** 2013-09-23_</span><span class="sxs-lookup"><span data-stu-id="aac16-103">_**Topic Last Modified:** 2013-09-23_</span></span>

<span data-ttu-id="aac16-104">Depois que os usuários forem movidos para pools do Lync Server 2013, você poderá migrar seus grupos de resposta.</span><span class="sxs-lookup"><span data-stu-id="aac16-104">After your users are moved to Lync Server 2013 pools, you can migrate your response groups.</span></span> <span data-ttu-id="aac16-105">Migrar grupos de resposta inclui a cópia de grupos de agente, filas, fluxos de trabalho, arquivos de áudio e movimentação de objetos de contato de grupo de resposta da implantação herdada para o pool do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="aac16-105">Migrating response groups includes copying agent groups, queues, workflows, audio files, and moving Response Group contact objects from the legacy deployment to the Lync Server 2013 pool.</span></span> <span data-ttu-id="aac16-106">Depois de migrar seus grupos de resposta herdados, as chamadas para os grupos de resposta são manipuladas pelo aplicativo grupo de resposta no pool do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="aac16-106">After you migrate your legacy response groups, calls to the response groups are handled by the Response Group application in the Lync Server 2013 pool.</span></span> <span data-ttu-id="aac16-107">As chamadas para grupos de resposta não são mais manipuladas pelo pool herdado.</span><span class="sxs-lookup"><span data-stu-id="aac16-107">Calls to response groups are no longer handled by the legacy pool.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="aac16-108">Embora seja possível migrar grupos de resposta antes de mover todos os usuários para o pool do Lync Server 2013, recomendamos que você mova todos os usuários primeiro.</span><span class="sxs-lookup"><span data-stu-id="aac16-108">Although you can migrate response groups before you move all users to the Lync Server 2013 pool, we recommend that you move all users first.</span></span> <span data-ttu-id="aac16-109">Em particular, os usuários que são agentes de grupo de resposta não terão funcionalidade completa dos novos recursos até serem movidos para o pool do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="aac16-109">In particular, users who are response group agents will not have full functionality of new features until they are moved to the Lync Server 2013 pool.</span></span>



</div>

<span data-ttu-id="aac16-110">Antes de migrar grupos de resposta, você deve ter implantado um pool do Lync Server 2013 que inclui o aplicativo do grupo de resposta.</span><span class="sxs-lookup"><span data-stu-id="aac16-110">Before you migrate response groups, you must have deployed a Lync Server 2013 pool that includes the Response Group application.</span></span> <span data-ttu-id="aac16-111">O aplicativo grupo de resposta é instalado e ativado por padrão ao implantar o Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="aac16-111">The Response Group application is installed and activated by default when you deploy Enterprise Voice.</span></span> <span data-ttu-id="aac16-112">Você pode garantir que o aplicativo do grupo de resposta seja instalado executando o cmdlet **Get-CsService-ApplicationServer** .</span><span class="sxs-lookup"><span data-stu-id="aac16-112">You can ensure that the Response Group application is installed by running the **Get-CsService –ApplicationServer** cmdlet.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="aac16-113">Você pode criar novos grupos de resposta do Lync Server 2013 no pool do Lync Server 2013 antes de migrar seus grupos de respostas herdadas.</span><span class="sxs-lookup"><span data-stu-id="aac16-113">You can create new Lync Server 2013 response groups in the Lync Server 2013 pool before you migrate your legacy response groups.</span></span>



</div>

<span data-ttu-id="aac16-114">Para migrar grupos de resposta de um pool herdado para o Lync Server 2013, execute o cmdlet **move-CsRgsConfiguration** .</span><span class="sxs-lookup"><span data-stu-id="aac16-114">To migrate response groups from a legacy pool to the Lync Server 2013, you run the **Move-CsRgsConfiguration** cmdlet.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="aac16-115">O cmdlet de migração do grupo de resposta move a configuração do grupo de resposta para o pool inteiro.</span><span class="sxs-lookup"><span data-stu-id="aac16-115">The Response Group migration cmdlet moves the Response Group configuration for the entire pool.</span></span> <span data-ttu-id="aac16-116">Não é possível selecionar grupos, filas ou fluxos de trabalho específicos para migrar.</span><span class="sxs-lookup"><span data-stu-id="aac16-116">You cannot select specific groups, queues, or workflows to migrate.</span></span>



</div>

<span data-ttu-id="aac16-117">Depois de migrar os grupos de resposta, você precisará usar o painel de controle do Lync Server ou cmdlets do Shell de gerenciamento do Lync Server para verificar se todos os grupos de agente, filas e fluxos de trabalho foram movidos com êxito.</span><span class="sxs-lookup"><span data-stu-id="aac16-117">After you migrate the response groups, you need to use Lync Server Control Panel or Lync Server Management Shell cmdlets to verify that all agent groups, queues, and workflows moved successfully.</span></span>

<span data-ttu-id="aac16-118">Quando você migra grupos de resposta, os grupos de resposta do Lync Server 2010 não são removidos.</span><span class="sxs-lookup"><span data-stu-id="aac16-118">When you migrate response groups, the Lync Server 2010 response groups are not removed.</span></span> <span data-ttu-id="aac16-119">Ao gerenciar grupos de resposta após a migração usando o painel de controle do Lync Server ou o Shell de gerenciamento do Lync Server, você pode ver os grupos de resposta do Lync Server 2010 e os grupos de resposta do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="aac16-119">When you manage response groups after migration by using either Lync Server Control Panel or Lync Server Management Shell, you can see both the Lync Server 2010 response groups and the Lync Server 2013 response groups.</span></span> <span data-ttu-id="aac16-120">Você deve aplicar atualizações somente aos grupos de resposta do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="aac16-120">You should apply updates only to the Lync Server 2013 response groups.</span></span> <span data-ttu-id="aac16-121">Os grupos de resposta do Lync Server 2010 são mantidos somente para fins de recuperação.</span><span class="sxs-lookup"><span data-stu-id="aac16-121">The Lync Server 2010 response groups are retained only for rollback purposes.</span></span>

<div>


> [!WARNING]  
> <span data-ttu-id="aac16-122">Após a conclusão da migração e os novos grupos de resposta terem sido criados, o painel de controle do Lync Server e o Shell de gerenciamento do Lync Server exibirão as versões do Lync Server 2010 e do Lync Server 2013 de cada grupo de resposta.</span><span class="sxs-lookup"><span data-stu-id="aac16-122">After the migration has been completed and the new response groups have been created, the Lync Server Control Panel and the Lync Server Management Shell will display the Lync Server 2010 and Lync Server 2013 versions of each response group.</span></span> <span data-ttu-id="aac16-123">Não use o painel de controle do Lync Server ou o Shell de gerenciamento do Lync Server para remover os grupos de resposta do Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="aac16-123">Do not use Lync Server Control Panel or Lync Server Management Shell to remove the Lync Server 2010 response groups.</span></span> <span data-ttu-id="aac16-124">Se você remover um, o grupo de resposta correspondente criado durante a migração deixará de funcionar.</span><span class="sxs-lookup"><span data-stu-id="aac16-124">If you do remove one, the corresponding response group that was created during migration will stop working.</span></span> <span data-ttu-id="aac16-125">Os grupos de resposta do Lync Server 2010 serão removidos quando você encerrar o pool do Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="aac16-125">The Lync Server 2010 response groups will be removed when you decommission the Lync Server 2010 pool.</span></span>



</div>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="aac16-126">Recomendamos que você não remova dados de sua implantação anterior até encerrar o pool.</span><span class="sxs-lookup"><span data-stu-id="aac16-126">We recommend that you do not remove any data from your previous deployment until you decommission the pool.</span></span> <span data-ttu-id="aac16-127">Além disso, recomendamos enfaticamente que você exporte os grupos de resposta imediatamente após a migração.</span><span class="sxs-lookup"><span data-stu-id="aac16-127">In addition, we strongly recommend that you export response groups immediately after you migrate.</span></span> <span data-ttu-id="aac16-128">Se um grupo de resposta do Lync Server 2010 deve ser removido, você pode restaurar seus grupos de resposta do backup para obter os grupos de resposta do Lync Server 2013 sendo executados novamente.</span><span class="sxs-lookup"><span data-stu-id="aac16-128">If a Lync Server 2010 response group should get removed, you can then restore your response groups from the backup to get Lync Server 2013 response groups running again.</span></span>



</div>

<span data-ttu-id="aac16-129">O Lync Server 2013 introduz um novo recurso de grupo de resposta chamado **tipo de fluxo de trabalho**.</span><span class="sxs-lookup"><span data-stu-id="aac16-129">Lync Server 2013 introduces a new Response Group feature called **Workflow Type**.</span></span> <span data-ttu-id="aac16-130">O **tipo de fluxo de trabalho** pode ser **gerenciado** ou **não gerenciado**.</span><span class="sxs-lookup"><span data-stu-id="aac16-130">**Workflow Type** can be **Managed** or **Unmanaged**.</span></span> <span data-ttu-id="aac16-131">Todos os grupos de resposta são migrados com o **tipo de fluxo de trabalho** definido como **não gerenciado** e com uma lista de gerentes vazia.</span><span class="sxs-lookup"><span data-stu-id="aac16-131">All response groups are migrated with **Workflow Type** set to **Unmanaged** and with an empty Manager list.</span></span>

<span data-ttu-id="aac16-132">Quando você executa o cmdlet **move-CsRgsConfiguration** , os grupos de agente, filas, fluxos de trabalho e arquivos de áudio permanecem no pool herdado para fins de reversão.</span><span class="sxs-lookup"><span data-stu-id="aac16-132">When you run the **Move-CsRgsConfiguration** cmdlet, the agent groups, queues, workflows, and audio files remain in the legacy pool for rollback purposes.</span></span> <span data-ttu-id="aac16-133">No entanto, se você precisar reverter para o pool herdado, será necessário executar o cmdlet **move-CsApplicationEndpoint** para mover objetos de contato de volta para o pool herdado.</span><span class="sxs-lookup"><span data-stu-id="aac16-133">If you do need to roll back to the legacy pool, however, you need to run the **Move-CsApplicationEndpoint** cmdlet to move contact objects back to the legacy pool.</span></span>

<span data-ttu-id="aac16-134">O procedimento a seguir para migrar configurações de grupo de resposta pressupõe que você tenha uma relação um-para-um entre seus pools herdados e os pools do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="aac16-134">The following procedure for migrating Response Group configurations assumes that you have a one-to-one relationship between your legacy pools and the Lync Server 2013 pools.</span></span> <span data-ttu-id="aac16-135">Se você planeja consolidar ou dividir os pools durante a migração e a implantação, será necessário planejar quais pools herdados são mapeados para qual Lync Server 2013 pool.</span><span class="sxs-lookup"><span data-stu-id="aac16-135">If you plan to consolidate or split up pools during your migration and deployment, you need to plan which legacy pool maps to which Lync Server 2013 pool.</span></span>

<div>

## <a name="to-migrate-response-group-configurations"></a><span data-ttu-id="aac16-136">Migrar configurações de grupo de resposta</span><span class="sxs-lookup"><span data-stu-id="aac16-136">To migrate Response Group configurations</span></span>

1.  <span data-ttu-id="aac16-137">Faça logon no computador com uma conta que seja membro do grupo RTCUniversalServerAdmins ou tenha direitos e permissões de administrador equivalentes.</span><span class="sxs-lookup"><span data-stu-id="aac16-137">Log on to the computer with an account that is a member of the RTCUniversalServerAdmins group or has equivalent administrator rights and permissions.</span></span>

2.  <span data-ttu-id="aac16-138">Inicie o Shell de gerenciamento do Lync Server: clique em **Iniciar**, em **todos os programas**, em **Microsoft Lync Server 2013**e, em seguida, clique em **Shell de gerenciamento do Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="aac16-138">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="aac16-139">Execute:</span><span class="sxs-lookup"><span data-stu-id="aac16-139">Run:</span></span>
    
        Move-CsRgsConfiguration -Source <source pool FQDN> -Destination <destination pool FQDN>
    
    <span data-ttu-id="aac16-140">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="aac16-140">For example:</span></span>
    
        Move-CsRgsConfiguration -Source lync-old.contoso.net -Destination lync-new.contoso.net

4.  <span data-ttu-id="aac16-141">Depois de migrar grupos de resposta e agentes para o pool do Lync Server 2013, a URL usada pelos agentes para entrar e sair é uma URL do Lync Server 2013 e está disponível no menu **ferramentas** .</span><span class="sxs-lookup"><span data-stu-id="aac16-141">After you migrate response groups and agents to the Lync Server 2013 pool, the URL that agents use to sign in and sign out is a Lync Server 2013 URL and is available from the **Tools** menu.</span></span> <span data-ttu-id="aac16-142">Lembre os agentes para atualizar todas as referências, como indicadores, para a nova URL.</span><span class="sxs-lookup"><span data-stu-id="aac16-142">Remind agents to update any references, such as bookmarks, to the new URL.</span></span>

</div>

<div>

## <a name="to-verify-response-group-migration-by-using-lync-server-control-panel"></a><span data-ttu-id="aac16-143">Para verificar a migração do grupo de resposta usando o painel de controle do Lync Server</span><span class="sxs-lookup"><span data-stu-id="aac16-143">To verify Response Group migration by using Lync Server Control Panel</span></span>

1.  <span data-ttu-id="aac16-144">Faça logon no computador com uma conta que seja membro do grupo RTCUniversalReadOnlyAdmins ou que seja minimamente um membro da função CsViewOnlyAdministrator.</span><span class="sxs-lookup"><span data-stu-id="aac16-144">Log on to the computer with an account that is a member of RTCUniversalReadOnlyAdmins group or is minimally a member of the CsViewOnlyAdministrator role.</span></span>

2.  <span data-ttu-id="aac16-145">Abra uma janela do navegador e, em seguida, insira a URL de administração para abrir o painel de controle do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="aac16-145">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="aac16-146">Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle do Lync Server, consulte [abrir ferramentas administrativas do Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="aac16-146">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="aac16-147">No painel de navegação esquerdo, clique em **grupos de resposta**.</span><span class="sxs-lookup"><span data-stu-id="aac16-147">In the left navigation pane, click **Response Groups**.</span></span>

4.  <span data-ttu-id="aac16-148">Na guia **fluxo de trabalho** , verifique se todos os fluxos de trabalho no ambiente do Lync Server 2010 estão incluídos na lista.</span><span class="sxs-lookup"><span data-stu-id="aac16-148">On the **Workflow** tab, verify that all the workflows in your Lync Server 2010 environment are included in the list.</span></span>

5.  <span data-ttu-id="aac16-149">Clique na guia **fila** e verifique se todas as filas em seu ambiente do Lync Server 2010 estão incluídas na lista.</span><span class="sxs-lookup"><span data-stu-id="aac16-149">Click the **Queue** tab, and verify that all the queues in your Lync Server 2010 environment are included in the list.</span></span>

6.  <span data-ttu-id="aac16-150">Clique na guia **grupo** e verifique se todos os grupos de agente no ambiente do Lync Server 2010 estão incluídos na lista.</span><span class="sxs-lookup"><span data-stu-id="aac16-150">Click the **Group** tab, and verify that all the agent groups in your Lync Server 2010 environment are included in the list.</span></span>

</div>

<div>

## <a name="to-verify-response-group-migration-by-using-lync-server-management-shell"></a><span data-ttu-id="aac16-151">Para verificar a migração do grupo de resposta usando o Shell de gerenciamento do Lync Server</span><span class="sxs-lookup"><span data-stu-id="aac16-151">To verify Response Group migration by using Lync Server Management Shell</span></span>

1.  <span data-ttu-id="aac16-152">Faça logon no computador com uma conta que seja membro do grupo RTCUniversalReadOnlyAdmins ou que seja minimamente um membro da função CsViewOnlyAdministrator.</span><span class="sxs-lookup"><span data-stu-id="aac16-152">Log on to the computer with an account that is a member of RTCUniversalReadOnlyAdmins group or is minimally a member of the CsViewOnlyAdministrator role.</span></span>

2.  <span data-ttu-id="aac16-153">Inicie o Shell de gerenciamento do Lync Server: clique em **Iniciar**, em **todos os programas**, em **Microsoft Lync Server 2013**e, em seguida, clique em **Shell de gerenciamento do Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="aac16-153">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>
    
    <span data-ttu-id="aac16-154">Para obter detalhes sobre os seguintes cmdlets, execute:</span><span class="sxs-lookup"><span data-stu-id="aac16-154">For details about the following cmdlets, run:</span></span>
    
        Get-Help <cmdlet name> -Detailed

3.  <span data-ttu-id="aac16-155">Execute:</span><span class="sxs-lookup"><span data-stu-id="aac16-155">Run:</span></span>
    
        Get-CsRgsAgentGroup

4.  <span data-ttu-id="aac16-156">Verifique se todos os grupos de agente no ambiente do Lync Server 2010 estão incluídos na lista.</span><span class="sxs-lookup"><span data-stu-id="aac16-156">Verify that all the agent groups in your Lync Server 2010 environment are included in the list.</span></span>

5.  <span data-ttu-id="aac16-157">Execute:</span><span class="sxs-lookup"><span data-stu-id="aac16-157">Run:</span></span>
    
        Get-CsRgsQueue

6.  <span data-ttu-id="aac16-158">Verifique se todas as filas no ambiente do Lync Server 2010 estão incluídas na lista.</span><span class="sxs-lookup"><span data-stu-id="aac16-158">Verify that all the queues in your Lync Server 2010 environment are included in the list.</span></span>

7.  <span data-ttu-id="aac16-159">Execute:</span><span class="sxs-lookup"><span data-stu-id="aac16-159">Run:</span></span>
    
        Get-CsRgsWorkflow

8.  <span data-ttu-id="aac16-160">Verifique se todos os fluxos de trabalho no ambiente do Lync Server 2010 estão incluídos na lista.</span><span class="sxs-lookup"><span data-stu-id="aac16-160">Verify that all the workflows in your Lync Server 2010 environment are included in the list.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

