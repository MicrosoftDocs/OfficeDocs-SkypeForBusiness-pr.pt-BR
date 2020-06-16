---
title: Migrar grupos de resposta
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Migrate response groups
ms:assetid: 5c07bf4b-ad8a-4b83-b970-7d933bb7c4ef
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204931(v=OCS.15)
ms:contentKeyID: 48184250
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: de012d0886c51cd70d5003beb24053ff86af05b7
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/16/2020
ms.locfileid: "44756932"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="migrate-response-groups"></a><span data-ttu-id="83615-102">Migrar grupos de resposta</span><span class="sxs-lookup"><span data-stu-id="83615-102">Migrate response groups</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="83615-103">_**Última modificação do tópico:** 2012-10-19_</span><span class="sxs-lookup"><span data-stu-id="83615-103">_**Topic Last Modified:** 2012-10-19_</span></span>

<span data-ttu-id="83615-104">Depois que os usuários forem movidos para pools do Lync Server 2013, você poderá migrar seus grupos de resposta.</span><span class="sxs-lookup"><span data-stu-id="83615-104">After your users are moved to Lync Server 2013 pools, you can migrate your response groups.</span></span> <span data-ttu-id="83615-105">Migrar grupos de resposta inclui copiar grupos de agente, filas, fluxos de trabalho e arquivos de áudio e mover objetos de contato de grupo de resposta da implantação herdada para o pool do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="83615-105">Migrating response groups includes copying agent groups, queues, workflows, and audio files, and moving Response Group contact objects from the legacy deployment to the Lync Server 2013 pool.</span></span> <span data-ttu-id="83615-106">Depois de migrar seus grupos de resposta herdados, as chamadas para os grupos de resposta são tratadas pelo aplicativo grupo de resposta no pool do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="83615-106">After you migrate your legacy response groups, calls to the response groups are handled by the Response Group application in the Lync Server 2013 pool.</span></span> <span data-ttu-id="83615-107">As chamadas aos grupos de resposta não serão mais processadas pelo pool antigo.</span><span class="sxs-lookup"><span data-stu-id="83615-107">Calls to response groups are no longer handled by the legacy pool.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="83615-108">Embora você possa migrar grupos de resposta antes de mover todos os usuários para o pool do Lync Server 2013, recomendamos que você mova todos os usuários primeiro.</span><span class="sxs-lookup"><span data-stu-id="83615-108">Although you can migrate response groups before you move all users to the Lync Server 2013 pool, we recommend that you move all users first.</span></span> <span data-ttu-id="83615-109">Em particular, os usuários que são agentes de grupo de resposta não terão a funcionalidade completa dos novos recursos até que sejam movidos para o pool do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="83615-109">In particular, users who are response group agents will not have full functionality of new features until they are moved to the Lync Server 2013 pool.</span></span>



</div>

<span data-ttu-id="83615-110">Antes de migrar grupos de resposta, você deve ter implantado um pool do Lync Server 2013 que inclui o aplicativo grupo de resposta.</span><span class="sxs-lookup"><span data-stu-id="83615-110">Before you migrate response groups, you must have deployed a Lync Server 2013 pool that includes the Response Group application.</span></span> <span data-ttu-id="83615-111">O aplicativo grupo de resposta é instalado e ativado por padrão ao implantar o Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="83615-111">The Response Group application is installed and activated by default when you deploy Enterprise Voice.</span></span> <span data-ttu-id="83615-112">Você pode garantir que o aplicativo grupo de resposta seja instalado executando o cmdlet **Get-CsService – ApplicationServer** .</span><span class="sxs-lookup"><span data-stu-id="83615-112">You can ensure that the Response Group application is installed by running the **Get-CsService–ApplicationServer** cmdlet.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="83615-113">Você pode criar novos grupos de resposta do Lync Server 2013 no pool do Lync Server 2013 antes de migrar seus grupos de resposta herdados.</span><span class="sxs-lookup"><span data-stu-id="83615-113">You can create new Lync Server 2013 response groups in the Lync Server 2013 pool before you migrate your legacy response groups.</span></span>



</div>

<span data-ttu-id="83615-114">Para migrar grupos de resposta de um pool herdado para o Lync Server 2013, execute o cmdlet **move-CsRgsConfiguration** .</span><span class="sxs-lookup"><span data-stu-id="83615-114">To migrate response groups from a legacy pool to the Lync Server 2013, you run the **Move-CsRgsConfiguration** cmdlet.</span></span> <span data-ttu-id="83615-115">Para poder executar o **Move-CsRgsConfiguration**, primeiro você precisa instalar o pacote de interfaces de compatibilidade com versões anteriores WMI (Instrumentação de Gerenciamento do Windows).</span><span class="sxs-lookup"><span data-stu-id="83615-115">Before you can run **Move-CsRgsConfiguration**, you must first install the Windows Management Instrumentation (WMI) Backward Compatibility interfaces package.</span></span> <span data-ttu-id="83615-116">Instale esse aplicativo executando o OCSWMIBC.msi.</span><span class="sxs-lookup"><span data-stu-id="83615-116">Install this application by running OCSWMIBC.msi.</span></span> <span data-ttu-id="83615-117">Você pode encontrar o OCSWMIBC.msi na pasta Setup da mídia de instalação.</span><span class="sxs-lookup"><span data-stu-id="83615-117">You can find OCSWMIBC.msi on the installation media in the Setup folder.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="83615-118">O cmdlet de migração do grupo de resposta move a configuração do grupo de resposta para todo o pool.</span><span class="sxs-lookup"><span data-stu-id="83615-118">The Response Group migration cmdlet moves the Response Group configuration for the entire pool.</span></span> <span data-ttu-id="83615-119">Não é possível selecionar grupos, filas e fluxos de trabalho específicos para migração.</span><span class="sxs-lookup"><span data-stu-id="83615-119">You cannot select specific groups, queues, or workflows to migrate.</span></span>



</div>

<span data-ttu-id="83615-120">Após migrar os grupos de resposta, você precisará atualizar a URL que os agentes formais usam para entrar e sair de seus grupos de resposta e usar o painel de controle do Lync Server ou cmdlets do Shell de gerenciamento do Lync Server para verificar se todos os grupos de agentes, filas e fluxos de trabalho foram movidos com êxito.</span><span class="sxs-lookup"><span data-stu-id="83615-120">After you migrate the response groups, you need to update the URL that formal agents use to sign into and out of their response groups, and use Lync Server Control Panel or Lync Server Management Shell cmdlets to verify that all agent groups, queues, and workflows moved successfully.</span></span>

<div>


> [!WARNING]  
> <span data-ttu-id="83615-121">Ao migrar grupos de resposta, os grupos de resposta do Office Communications Server 2007 R2 não são removidos.</span><span class="sxs-lookup"><span data-stu-id="83615-121">When you migrate response groups, the Office Communications Server 2007 R2 response groups are not removed.</span></span> <span data-ttu-id="83615-122">Não remova os grupos de resposta do Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="83615-122">Do not remove Office Communications Server 2007 R2 response groups.</span></span> <span data-ttu-id="83615-123">Se você remover um grupo de resposta do Office Communications Server 2007 R2, os grupos de resposta no Lync Server 2013 param de funcionar.</span><span class="sxs-lookup"><span data-stu-id="83615-123">If you remove an Office Communications Server 2007 R2 response group, the response groups in Lync Server 2013 stop working.</span></span>



</div>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="83615-124">Recomendamos que você não remova dados da sua implantação anterior até suspender o pool.</span><span class="sxs-lookup"><span data-stu-id="83615-124">We recommend that you do not remove any data from your previous deployment until you decommission the pool.</span></span> <span data-ttu-id="83615-125">Além disso, é altamente recomendável que você exporte os grupos de resposta imediatamente após a migração.</span><span class="sxs-lookup"><span data-stu-id="83615-125">In addition, we strongly recommend that you export response groups immediately after you migrate.</span></span> <span data-ttu-id="83615-126">Se um grupo de resposta do Office Communications Server 2007 R2 for removido, você poderá restaurar seus grupos de resposta do backup para obter os grupos de resposta do Lync Server 2013 em execução novamente.</span><span class="sxs-lookup"><span data-stu-id="83615-126">If an Office Communications Server 2007 R2 response group gets removed, you can then restore your response groups from the backup to get Lync Server 2013 response groups running again.</span></span>



</div>

<span data-ttu-id="83615-127">Quando você executa o cmdlet **Move-CsRgsConfiguration**, as filas, os fluxos de trabalho, os arquivos de áudio e os grupos de agente continuam no pool antigo para fins de reversão.</span><span class="sxs-lookup"><span data-stu-id="83615-127">When you run the **Move-CsRgsConfiguration** cmdlet, the agent groups, queues, workflows, and audio files remain in the legacy pool for rollback purposes.</span></span> <span data-ttu-id="83615-128">Entretanto, se for necessária uma reversão para o pool antigo, você precisará executar o cmdlet **Move-CsApplicationEndpoint** para transferir objetos de contato de volta para o pool antigo.</span><span class="sxs-lookup"><span data-stu-id="83615-128">If you do need to roll back to the legacy pool, however, you need to run the **Move-CsApplicationEndpoint** cmdlet to move contact objects back to the legacy pool.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="83615-129">Recomendamos que você não exclua dados de grupos de resposta do pool antigo até suspendê-lo.</span><span class="sxs-lookup"><span data-stu-id="83615-129">We recommend that you don't delete any response group data from the legacy pool until you decommission the pool.</span></span>



</div>

<span data-ttu-id="83615-130">O procedimento a seguir para migrar configurações de grupo de resposta pressupõe que você tenha uma relação um-para-um entre seus pools herdados e os pools do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="83615-130">The procedure that follows for migrating Response Group configurations assumes that you have a one-to-one relationship between your legacy pools and the Lync Server 2013 pools.</span></span> <span data-ttu-id="83615-131">Se você planeja consolidar ou dividir pools durante sua migração e implantação, precisa planejar quais pools herdados mapeiam para qual Lync Server 2013 pool.</span><span class="sxs-lookup"><span data-stu-id="83615-131">If you plan to consolidate or split up pools during your migration and deployment, you need to plan which legacy pool maps to which Lync Server 2013 pool.</span></span>

<div>

## <a name="to-migrate-response-group-configurations"></a><span data-ttu-id="83615-132">Para migrar configurações de grupo de resposta</span><span class="sxs-lookup"><span data-stu-id="83615-132">To Migrate Response Group Configurations</span></span>

1.  <span data-ttu-id="83615-133">Localize o OCSWMIBC.msi na pasta Setup da mídia de instalação e instale-o.</span><span class="sxs-lookup"><span data-stu-id="83615-133">Locate OCSWMIBC.msi in the Setup folder of the installation media and install it.</span></span>

2.  <span data-ttu-id="83615-134">Faça logon no computador com uma conta que seja membro do grupo RTCUniversalServerAdmins ou que tenha direitos e permissões de administrador equivalentes.</span><span class="sxs-lookup"><span data-stu-id="83615-134">Log on to the computer with an account that is a member of the RTCUniversalServerAdmins group or has equivalent administrator rights and permissions.</span></span>

3.  <span data-ttu-id="83615-135">Abra o Shell de Gerenciamento do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="83615-135">Open the Lync Server Management Shell.</span></span>

4.  <span data-ttu-id="83615-136">Na linha de comando, digite o seguinte:</span><span class="sxs-lookup"><span data-stu-id="83615-136">At the command line, type the following:</span></span>
    
        Move-CsRgsConfiguration -Source <source pool FQDN> -Destination <destination pool FQDN>
    
    <span data-ttu-id="83615-137">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="83615-137">For example:</span></span>
    
        Move-CsRgsConfiguration -Source pool01.contoso.net -Destination pool02.contoso.net

5.  <span data-ttu-id="83615-138">Se você implantou a guia grupo de resposta para o Microsoft Office Communicator 2007 R2 no seu ambiente do Office Communications Server 2007 R2, remova a guia do arquivo tabs.xml do Office Communicator 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="83615-138">If you deployed the Response Group tab for Microsoft Office Communicator 2007 R2 in your Office Communications Server 2007 R2 environment, remove the tab from the Office Communicator 2007 R2 tabs.xml file.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="83615-139">Agentes formais usavam a guia Grupo de Resposta para fazer logon em seus grupos de resposta antes de poderem receber chamadas.</span><span class="sxs-lookup"><span data-stu-id="83615-139">Formal agents used the Response Group tab to sign in to their response groups before they could receive calls.</span></span> <span data-ttu-id="83615-140">Se você implantou a guia grupo de resposta, você escolheu o local para o arquivo de tabs.xml do Office Communicator 2007 R2 ao implantá-lo.</span><span class="sxs-lookup"><span data-stu-id="83615-140">If you deployed the Response Group tab, you chose the location for the Office Communicator 2007 R2 tabs.xml file when you deployed it.</span></span>

    
    </div>

6.  <span data-ttu-id="83615-141">Forneça aos usuários a URL atualizada que os os agentes precisam para fazer logon e sair de seus grupos de resposta.</span><span class="sxs-lookup"><span data-stu-id="83615-141">Provide users with the updated URL that agents need to sign into and out of their response groups.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="83615-142">A URL normalmente é https://webpoolFQDN/RgsClients/Tab.aspx , onde webpoolFQDN é o nome de domínio totalmente qualificado (FQDN) do pool da Web associado ao pool que você migrou para o Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="83615-142">The URL is typically https://webpoolFQDN/RgsClients/Tab.aspx, where webpoolFQDN is the fully qualified domain name (FQDN) of the web pool that is associated with the pool that you just migrated to Lync Server 2013.</span></span>

    
    </div>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="83615-143">Esta etapa não é necessária depois que os usuários atualizam para o Lync 2013 porque a URL está disponível no menu <STRONG>ferramentas</STRONG> no Lync.</span><span class="sxs-lookup"><span data-stu-id="83615-143">This step is not required after users upgrade to Lync 2013 because the URL is available from the <STRONG>Tools</STRONG> menu in Lync.</span></span>

    
    </div>

</div>

<div>

## <a name="to-verify-response-group-migration-by-using-lync-server-control-panel"></a><span data-ttu-id="83615-144">Para verificar a migração do grupo de resposta usando o painel de controle do Lync Server</span><span class="sxs-lookup"><span data-stu-id="83615-144">To Verify Response Group Migration by Using Lync Server Control Panel</span></span>

1.  <span data-ttu-id="83615-145">Abra o painel de controle do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="83615-145">Open the Lync Server Control Panel.</span></span>

2.  <span data-ttu-id="83615-146">No painel de navegação à esquerda, clique em **Grupos de Resposta**.</span><span class="sxs-lookup"><span data-stu-id="83615-146">In the left navigation pane, click **Response Groups**.</span></span>

3.  <span data-ttu-id="83615-147">Na guia **fluxo de trabalho** , verifique se todos os fluxos de trabalho em seu ambiente do Office Communications Server 2007 R2 estão incluídos na lista.</span><span class="sxs-lookup"><span data-stu-id="83615-147">On the **Workflow** tab, verify that all the workflows in your Office Communications Server 2007 R2 environment are included in the list.</span></span>

4.  <span data-ttu-id="83615-148">Clique na guia **fila** e verifique se todas as filas em seu ambiente do Office Communications Server 2007 R2 estão incluídas na lista.</span><span class="sxs-lookup"><span data-stu-id="83615-148">Click the **Queue** tab, and verify that all the queues in your Office Communications Server 2007 R2 environment are included in the list.</span></span>

5.  <span data-ttu-id="83615-149">Clique na guia **grupo** e verifique se todos os grupos de agente em seu ambiente do Office Communications Server 2007 R2 estão incluídos na lista.</span><span class="sxs-lookup"><span data-stu-id="83615-149">Click the **Group** tab, and verify that all the agent groups in your Office Communications Server 2007 R2 environment are included in the list.</span></span>

</div>

<div>

## <a name="to-verify-response-group-migration-by-using-cmdlets"></a><span data-ttu-id="83615-150">Para confirmar a migração do grupo de resposta usando o cmdlets</span><span class="sxs-lookup"><span data-stu-id="83615-150">To Verify Response Group Migration by Using Cmdlets</span></span>

1.  <span data-ttu-id="83615-151">Abra o Shell de Gerenciamento do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="83615-151">Open the Lync Server Management Shell.</span></span>
    
    <span data-ttu-id="83615-152">Para obter detalhes sobre os seguintes cmdlets, execute:</span><span class="sxs-lookup"><span data-stu-id="83615-152">For details about the following cmdlets, run:</span></span>
    
        Get-Help <cmdlet name> -Detailed

2.  <span data-ttu-id="83615-153">Na linha de comando, digite o seguinte:</span><span class="sxs-lookup"><span data-stu-id="83615-153">At the command line, type the following:</span></span>
    
        Get-CsRgsAgentGroup

3.  <span data-ttu-id="83615-154">Verifique se todos os grupos de agente em seu ambiente do Office Communications Server 2007 R2 estão incluídos na lista.</span><span class="sxs-lookup"><span data-stu-id="83615-154">Verify that all the agent groups in your Office Communications Server 2007 R2 environment are included in the list.</span></span>

4.  <span data-ttu-id="83615-155">Na linha de comando, digite o seguinte:</span><span class="sxs-lookup"><span data-stu-id="83615-155">At the command line, type the following:</span></span>
    
        Get-CsRgsQueue

5.  <span data-ttu-id="83615-156">Verifique se todas as filas em seu ambiente do Office Communications Server 2007 R2 estão incluídas na lista.</span><span class="sxs-lookup"><span data-stu-id="83615-156">Verify that all the queues in your Office Communications Server 2007 R2 environment are included in the list.</span></span>

6.  <span data-ttu-id="83615-157">Na linha de comando, digite o seguinte:</span><span class="sxs-lookup"><span data-stu-id="83615-157">At the command line, type the following:</span></span>
    
        Get-CsRgsWorkflow

7.  <span data-ttu-id="83615-158">Verifique se todos os fluxos de trabalho em seu ambiente do Office Communications Server 2007 R2 estão incluídos na lista.</span><span class="sxs-lookup"><span data-stu-id="83615-158">Verify that all the workflows in your Office Communications Server 2007 R2 environment are included in the list.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

