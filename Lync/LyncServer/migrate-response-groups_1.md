---
title: Migrar grupos de resposta
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Migrate response groups
ms:assetid: 5c07bf4b-ad8a-4b83-b970-7d933bb7c4ef
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204931(v=OCS.15)
ms:contentKeyID: 48184250
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4bf7f0fa04f494eb49a0537011d5f9affcc68065
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34844256"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="migrate-response-groups"></a><span data-ttu-id="1f84e-102">Migrar grupos de resposta</span><span class="sxs-lookup"><span data-stu-id="1f84e-102">Migrate response groups</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1f84e-103">_**Tópico da última modificação:** 2012-10-19_</span><span class="sxs-lookup"><span data-stu-id="1f84e-103">_**Topic Last Modified:** 2012-10-19_</span></span>

<span data-ttu-id="1f84e-104">Depois que os usuários forem movidos para pools do Lync Server 2013, você poderá migrar seus grupos de resposta.</span><span class="sxs-lookup"><span data-stu-id="1f84e-104">After your users are moved to Lync Server 2013 pools, you can migrate your response groups.</span></span> <span data-ttu-id="1f84e-105">Migrar grupos de resposta inclui copiar grupos de agente, filas, fluxos de trabalho e arquivos de áudio, além de mover objetos de contato de grupo de resposta da implantação herdada para o pool do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="1f84e-105">Migrating response groups includes copying agent groups, queues, workflows, and audio files, and moving Response Group contact objects from the legacy deployment to the Lync Server 2013 pool.</span></span> <span data-ttu-id="1f84e-106">Depois de migrar seus grupos de resposta herdados, as chamadas para os grupos de resposta são manipuladas pelo aplicativo grupo de resposta no pool do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="1f84e-106">After you migrate your legacy response groups, calls to the response groups are handled by the Response Group application in the Lync Server 2013 pool.</span></span> <span data-ttu-id="1f84e-107">As chamadas para grupos de resposta não são mais manipuladas pelo pool herdado.</span><span class="sxs-lookup"><span data-stu-id="1f84e-107">Calls to response groups are no longer handled by the legacy pool.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="1f84e-108">Embora seja possível migrar grupos de resposta antes de mover todos os usuários para o pool do Lync Server 2013, recomendamos que você mova todos os usuários primeiro.</span><span class="sxs-lookup"><span data-stu-id="1f84e-108">Although you can migrate response groups before you move all users to the Lync Server 2013 pool, we recommend that you move all users first.</span></span> <span data-ttu-id="1f84e-109">Em particular, os usuários que são agentes de grupo de resposta não terão funcionalidade completa dos novos recursos até serem movidos para o pool do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="1f84e-109">In particular, users who are response group agents will not have full functionality of new features until they are moved to the Lync Server 2013 pool.</span></span>



</div>

<span data-ttu-id="1f84e-110">Antes de migrar grupos de resposta, você deve ter implantado um pool do Lync Server 2013 que inclui o aplicativo do grupo de resposta.</span><span class="sxs-lookup"><span data-stu-id="1f84e-110">Before you migrate response groups, you must have deployed a Lync Server 2013 pool that includes the Response Group application.</span></span> <span data-ttu-id="1f84e-111">O aplicativo grupo de resposta é instalado e ativado por padrão ao implantar o Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="1f84e-111">The Response Group application is installed and activated by default when you deploy Enterprise Voice.</span></span> <span data-ttu-id="1f84e-112">Você pode garantir que o aplicativo do grupo de resposta seja instalado executando o cmdlet **Get-CsService-ApplicationServer** .</span><span class="sxs-lookup"><span data-stu-id="1f84e-112">You can ensure that the Response Group application is installed by running the **Get-CsService–ApplicationServer** cmdlet.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="1f84e-113">Você pode criar novos grupos de resposta do Lync Server 2013 no pool do Lync Server 2013 antes de migrar seus grupos de respostas herdadas.</span><span class="sxs-lookup"><span data-stu-id="1f84e-113">You can create new Lync Server 2013 response groups in the Lync Server 2013 pool before you migrate your legacy response groups.</span></span>



</div>

<span data-ttu-id="1f84e-114">Para migrar grupos de resposta de um pool herdado para o Lync Server 2013, execute o cmdlet **move-CsRgsConfiguration** .</span><span class="sxs-lookup"><span data-stu-id="1f84e-114">To migrate response groups from a legacy pool to the Lync Server 2013, you run the **Move-CsRgsConfiguration** cmdlet.</span></span> <span data-ttu-id="1f84e-115">Antes de executar **move-CsRgsConfiguration**, você deve primeiro instalar o pacote de interfaces de compatibilidade com versões anteriores do Windows Management Instrumentation (WMI).</span><span class="sxs-lookup"><span data-stu-id="1f84e-115">Before you can run **Move-CsRgsConfiguration**, you must first install the Windows Management Instrumentation (WMI) Backward Compatibility interfaces package.</span></span> <span data-ttu-id="1f84e-116">Instale esse aplicativo executando OCSWMIBC. msi.</span><span class="sxs-lookup"><span data-stu-id="1f84e-116">Install this application by running OCSWMIBC.msi.</span></span> <span data-ttu-id="1f84e-117">Você pode encontrar o OCSWMIBC. msi na mídia de instalação na pasta de instalação.</span><span class="sxs-lookup"><span data-stu-id="1f84e-117">You can find OCSWMIBC.msi on the installation media in the Setup folder.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="1f84e-118">O cmdlet de migração do grupo de resposta move a configuração do grupo de resposta para o pool inteiro.</span><span class="sxs-lookup"><span data-stu-id="1f84e-118">The Response Group migration cmdlet moves the Response Group configuration for the entire pool.</span></span> <span data-ttu-id="1f84e-119">Não é possível selecionar grupos, filas ou fluxos de trabalho específicos para migrar.</span><span class="sxs-lookup"><span data-stu-id="1f84e-119">You cannot select specific groups, queues, or workflows to migrate.</span></span>



</div>

<span data-ttu-id="1f84e-120">Depois de migrar os grupos de resposta, você precisa atualizar a URL que os agentes formais usam para entrar e sair de seus grupos de resposta e usar o painel de controle do Lync Server ou cmdlets do Shell de gerenciamento do Lync Server para verificar se todos os grupos de agente, filas e fluxos de trabalho foram movidos com êxito.</span><span class="sxs-lookup"><span data-stu-id="1f84e-120">After you migrate the response groups, you need to update the URL that formal agents use to sign into and out of their response groups, and use Lync Server Control Panel or Lync Server Management Shell cmdlets to verify that all agent groups, queues, and workflows moved successfully.</span></span>

<div>


> [!WARNING]  
> <span data-ttu-id="1f84e-121">Quando você migra grupos de resposta, os grupos de resposta do Office Communications Server 2007 R2 não são removidos.</span><span class="sxs-lookup"><span data-stu-id="1f84e-121">When you migrate response groups, the Office Communications Server 2007 R2 response groups are not removed.</span></span> <span data-ttu-id="1f84e-122">Não remova os grupos de resposta do Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="1f84e-122">Do not remove Office Communications Server 2007 R2 response groups.</span></span> <span data-ttu-id="1f84e-123">Se você remover um grupo de resposta do Office Communications Server 2007 R2, os grupos de resposta no Lync Server 2013 param de funcionar.</span><span class="sxs-lookup"><span data-stu-id="1f84e-123">If you remove an Office Communications Server 2007 R2 response group, the response groups in Lync Server 2013 stop working.</span></span>



</div>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="1f84e-124">Recomendamos que você não remova dados de sua implantação anterior até encerrar o pool.</span><span class="sxs-lookup"><span data-stu-id="1f84e-124">We recommend that you do not remove any data from your previous deployment until you decommission the pool.</span></span> <span data-ttu-id="1f84e-125">Além disso, recomendamos enfaticamente que você exporte os grupos de resposta imediatamente após a migração.</span><span class="sxs-lookup"><span data-stu-id="1f84e-125">In addition, we strongly recommend that you export response groups immediately after you migrate.</span></span> <span data-ttu-id="1f84e-126">Se um grupo de resposta do Office Communications Server 2007 R2 for removido, você poderá restaurar seus grupos de resposta do backup para obter os grupos de resposta do Lync Server 2013 sendo executados novamente.</span><span class="sxs-lookup"><span data-stu-id="1f84e-126">If an Office Communications Server 2007 R2 response group gets removed, you can then restore your response groups from the backup to get Lync Server 2013 response groups running again.</span></span>



</div>

<span data-ttu-id="1f84e-127">Quando você executa o cmdlet **move-CsRgsConfiguration** , os grupos de agente, filas, fluxos de trabalho e arquivos de áudio permanecem no pool herdado para fins de reversão.</span><span class="sxs-lookup"><span data-stu-id="1f84e-127">When you run the **Move-CsRgsConfiguration** cmdlet, the agent groups, queues, workflows, and audio files remain in the legacy pool for rollback purposes.</span></span> <span data-ttu-id="1f84e-128">No entanto, se você precisar reverter para o pool herdado, será necessário executar o cmdlet **move-CsApplicationEndpoint** para mover objetos de contato de volta para o pool herdado.</span><span class="sxs-lookup"><span data-stu-id="1f84e-128">If you do need to roll back to the legacy pool, however, you need to run the **Move-CsApplicationEndpoint** cmdlet to move contact objects back to the legacy pool.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="1f84e-129">Recomendamos que você não exclua dos dados do grupo de resposta do pool herdado até encerrar o pool.</span><span class="sxs-lookup"><span data-stu-id="1f84e-129">We recommend that you don't delete any response group data from the legacy pool until you decommission the pool.</span></span>



</div>

<span data-ttu-id="1f84e-130">O procedimento a seguir para migrar configurações de grupo de resposta pressupõe que você tenha uma relação um-para-um entre seus pools herdados e os pools do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="1f84e-130">The procedure that follows for migrating Response Group configurations assumes that you have a one-to-one relationship between your legacy pools and the Lync Server 2013 pools.</span></span> <span data-ttu-id="1f84e-131">Se você planeja consolidar ou dividir os pools durante a migração e a implantação, será necessário planejar quais pools herdados são mapeados para qual Lync Server 2013 pool.</span><span class="sxs-lookup"><span data-stu-id="1f84e-131">If you plan to consolidate or split up pools during your migration and deployment, you need to plan which legacy pool maps to which Lync Server 2013 pool.</span></span>

<div>

## <a name="to-migrate-response-group-configurations"></a><span data-ttu-id="1f84e-132">Migrar configurações de grupo de resposta</span><span class="sxs-lookup"><span data-stu-id="1f84e-132">To Migrate Response Group Configurations</span></span>

1.  <span data-ttu-id="1f84e-133">Localize OCSWMIBC. msi na pasta Setup da mídia de instalação e instale-o.</span><span class="sxs-lookup"><span data-stu-id="1f84e-133">Locate OCSWMIBC.msi in the Setup folder of the installation media and install it.</span></span>

2.  <span data-ttu-id="1f84e-134">Faça logon no computador com uma conta que seja membro do grupo RTCUniversalServerAdmins ou tenha direitos e permissões de administrador equivalentes.</span><span class="sxs-lookup"><span data-stu-id="1f84e-134">Log on to the computer with an account that is a member of the RTCUniversalServerAdmins group or has equivalent administrator rights and permissions.</span></span>

3.  <span data-ttu-id="1f84e-135">Abra o Shell de gerenciamento do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="1f84e-135">Open the Lync Server Management Shell.</span></span>

4.  <span data-ttu-id="1f84e-136">Na linha de comando, digite o seguinte:</span><span class="sxs-lookup"><span data-stu-id="1f84e-136">At the command line, type the following:</span></span>
    
        Move-CsRgsConfiguration -Source <source pool FQDN> -Destination <destination pool FQDN>
    
    <span data-ttu-id="1f84e-137">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="1f84e-137">For example:</span></span>
    
        Move-CsRgsConfiguration -Source pool01.contoso.net -Destination pool02.contoso.net

5.  <span data-ttu-id="1f84e-138">Se você implantou a guia grupo de resposta do Microsoft Office Communicator 2007 R2 em seu ambiente do Office Communications Server 2007 R2, remova a guia do arquivo tabulares. XML do Office Communicator 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="1f84e-138">If you deployed the Response Group tab for Microsoft Office Communicator 2007 R2 in your Office Communications Server 2007 R2 environment, remove the tab from the Office Communicator 2007 R2 tabs.xml file.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="1f84e-139">Agentes formais usaram a guia grupo de resposta para entrar em seus grupos de resposta antes de poderem receber chamadas.</span><span class="sxs-lookup"><span data-stu-id="1f84e-139">Formal agents used the Response Group tab to sign in to their response groups before they could receive calls.</span></span> <span data-ttu-id="1f84e-140">Se você implantou a guia grupo de resposta, você escolheu o local do arquivo tabular. XML do Office Communicator 2007 R2 quando a implantou.</span><span class="sxs-lookup"><span data-stu-id="1f84e-140">If you deployed the Response Group tab, you chose the location for the Office Communicator 2007 R2 tabs.xml file when you deployed it.</span></span>

    
    </div>

6.  <span data-ttu-id="1f84e-141">Forneça aos usuários a URL atualizada que os agentes precisam entrar e sair de seus grupos de resposta.</span><span class="sxs-lookup"><span data-stu-id="1f84e-141">Provide users with the updated URL that agents need to sign into and out of their response groups.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="1f84e-142">A URL geralmente https://webpoolFQDN/RgsClients/Tab.aspxé, em que webpoolFQDN é o nome de domínio totalmente qualificado (FQDN) do pool da Web que está associado ao pool que você migrau para o Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="1f84e-142">The URL is typically https://webpoolFQDN/RgsClients/Tab.aspx, where webpoolFQDN is the fully qualified domain name (FQDN) of the web pool that is associated with the pool that you just migrated to Lync Server 2013.</span></span>

    
    </div>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="1f84e-143">Esta etapa não é necessária após a atualização dos usuários para o Lync 2013 porque a URL está disponível no menu <STRONG>ferramentas</STRONG> do Lync.</span><span class="sxs-lookup"><span data-stu-id="1f84e-143">This step is not required after users upgrade to Lync 2013 because the URL is available from the <STRONG>Tools</STRONG> menu in Lync.</span></span>

    
    </div>

</div>

<div>

## <a name="to-verify-response-group-migration-by-using-lync-server-control-panel"></a><span data-ttu-id="1f84e-144">Para verificar a migração do grupo de resposta usando o painel de controle do Lync Server</span><span class="sxs-lookup"><span data-stu-id="1f84e-144">To Verify Response Group Migration by Using Lync Server Control Panel</span></span>

1.  <span data-ttu-id="1f84e-145">Abra o painel de controle do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="1f84e-145">Open the Lync Server Control Panel.</span></span>

2.  <span data-ttu-id="1f84e-146">No painel de navegação esquerdo, clique em **grupos de resposta**.</span><span class="sxs-lookup"><span data-stu-id="1f84e-146">In the left navigation pane, click **Response Groups**.</span></span>

3.  <span data-ttu-id="1f84e-147">Na guia **fluxo de trabalho** , verifique se todos os fluxos de trabalho no ambiente do Office Communications Server 2007 R2 estão incluídos na lista.</span><span class="sxs-lookup"><span data-stu-id="1f84e-147">On the **Workflow** tab, verify that all the workflows in your Office Communications Server 2007 R2 environment are included in the list.</span></span>

4.  <span data-ttu-id="1f84e-148">Clique na guia **fila** e verifique se todas as filas no ambiente do Office Communications Server 2007 R2 estão incluídas na lista.</span><span class="sxs-lookup"><span data-stu-id="1f84e-148">Click the **Queue** tab, and verify that all the queues in your Office Communications Server 2007 R2 environment are included in the list.</span></span>

5.  <span data-ttu-id="1f84e-149">Clique na guia **grupo** e verifique se todos os grupos de agente no ambiente do Office Communications Server 2007 R2 estão incluídos na lista.</span><span class="sxs-lookup"><span data-stu-id="1f84e-149">Click the **Group** tab, and verify that all the agent groups in your Office Communications Server 2007 R2 environment are included in the list.</span></span>

</div>

<div>

## <a name="to-verify-response-group-migration-by-using-cmdlets"></a><span data-ttu-id="1f84e-150">Para verificar a migração do grupo de resposta usando cmdlets</span><span class="sxs-lookup"><span data-stu-id="1f84e-150">To Verify Response Group Migration by Using Cmdlets</span></span>

1.  <span data-ttu-id="1f84e-151">Abra o Shell de gerenciamento do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="1f84e-151">Open the Lync Server Management Shell.</span></span>
    
    <span data-ttu-id="1f84e-152">Para obter detalhes sobre os seguintes cmdlets, execute:</span><span class="sxs-lookup"><span data-stu-id="1f84e-152">For details about the following cmdlets, run:</span></span>
    
        Get-Help <cmdlet name> -Detailed

2.  <span data-ttu-id="1f84e-153">Na linha de comando, digite o seguinte:</span><span class="sxs-lookup"><span data-stu-id="1f84e-153">At the command line, type the following:</span></span>
    
        Get-CsRgsAgentGroup

3.  <span data-ttu-id="1f84e-154">Verifique se todos os grupos de agente no ambiente do Office Communications Server 2007 R2 estão incluídos na lista.</span><span class="sxs-lookup"><span data-stu-id="1f84e-154">Verify that all the agent groups in your Office Communications Server 2007 R2 environment are included in the list.</span></span>

4.  <span data-ttu-id="1f84e-155">Na linha de comando, digite o seguinte:</span><span class="sxs-lookup"><span data-stu-id="1f84e-155">At the command line, type the following:</span></span>
    
        Get-CsRgsQueue

5.  <span data-ttu-id="1f84e-156">Verifique se todas as filas no ambiente do Office Communications Server 2007 R2 estão incluídas na lista.</span><span class="sxs-lookup"><span data-stu-id="1f84e-156">Verify that all the queues in your Office Communications Server 2007 R2 environment are included in the list.</span></span>

6.  <span data-ttu-id="1f84e-157">Na linha de comando, digite o seguinte:</span><span class="sxs-lookup"><span data-stu-id="1f84e-157">At the command line, type the following:</span></span>
    
        Get-CsRgsWorkflow

7.  <span data-ttu-id="1f84e-158">Verifique se todos os fluxos de trabalho no ambiente do Office Communications Server 2007 R2 estão incluídos na lista.</span><span class="sxs-lookup"><span data-stu-id="1f84e-158">Verify that all the workflows in your Office Communications Server 2007 R2 environment are included in the list.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

