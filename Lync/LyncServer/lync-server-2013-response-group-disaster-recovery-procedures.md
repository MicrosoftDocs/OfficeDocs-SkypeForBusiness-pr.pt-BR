---
title: 'Lync Server 2013: Procedimento de recuperação de desastre do grupo de resposta'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Response group disaster recovery procedures
ms:assetid: b49577b7-0ca3-4f20-b614-f3a2a0046b58
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205186(v=OCS.15)
ms:contentKeyID: 48185171
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e7f28f13d1acdbdae58b1aadd6f73871af270b7d
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34823284"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="response-group-disaster-recovery-procedures-in-lync-server-2013"></a><span data-ttu-id="c1407-102">Procedimento de recuperação de desastre do grupo de resposta no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c1407-102">Response group disaster recovery procedures in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c1407-103">_**Tópico da última modificação:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="c1407-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="c1407-104">Durante a fase de failover da recuperação de desastres, os grupos de resposta residem em vários pools: no pool primário (que não está disponível) e no pool de backup.</span><span class="sxs-lookup"><span data-stu-id="c1407-104">During the failover phase of disaster recovery, the response groups reside in multiple pools: in the primary pool (which is unavailable) and in the backup pool.</span></span> <span data-ttu-id="c1407-105">Os grupos de resposta em ambos os pools têm o mesmo nome e o mesmo proprietário (o pool primário), mas têm pais diferentes.</span><span class="sxs-lookup"><span data-stu-id="c1407-105">The response groups in both pools have the same name and the same owner (the primary pool), but they have different parents.</span></span> <span data-ttu-id="c1407-106">Durante esse tempo, os cmdlets do grupo de resposta funcionam de maneira um pouco diferente.</span><span class="sxs-lookup"><span data-stu-id="c1407-106">During this time, Response Group cmdlets work a little differently.</span></span> <span data-ttu-id="c1407-107">Certifique-se de usar parâmetros conforme especificado no procedimento a seguir.</span><span class="sxs-lookup"><span data-stu-id="c1407-107">Be sure to use parameters as specified in the following procedure.</span></span> <span data-ttu-id="c1407-108">Para obter detalhes sobre como os cmdlets funcionam durante a fase de failover, consulte artigo do blog NextHop "Lync Server 2013: Recuperando grupos de respostas durante [http://go.microsoft.com/fwlink/p/?LinkId=263957](http://go.microsoft.com/fwlink/p/?linkid=263957)a recuperação de desastres" em.</span><span class="sxs-lookup"><span data-stu-id="c1407-108">For details about how cmdlets work during the failover phase, see NextHop blog article "Lync Server 2013: Recovering Response Groups During Disaster Recovery" at [http://go.microsoft.com/fwlink/p/?LinkId=263957](http://go.microsoft.com/fwlink/p/?linkid=263957).</span></span> <span data-ttu-id="c1407-109">Este artigo de blog também se aplica à versão de lançamento do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="c1407-109">This blog article also applies to the released version of Lync Server 2013.</span></span>

<span data-ttu-id="c1407-110">Use as etapas do procedimento a seguir para se preparar e executar a recuperação de desastres para o serviço do grupo de resposta do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="c1407-110">Use the steps in the following procedure to prepare for and perform disaster recovery for Lync Server Response Group service.</span></span>

<div>

## <a name="to-fail-over-and-fail-back-response-group"></a><span data-ttu-id="c1407-111">Para fazer failover e failback do grupo de resposta</span><span class="sxs-lookup"><span data-stu-id="c1407-111">To fail over and fail back Response Group</span></span>

1.  <span data-ttu-id="c1407-112">Inicie o Shell de gerenciamento do Lync Server: clique em **Iniciar**, em **todos os programas**, em **Microsoft Lync Server 2013**e, em seguida, clique em **Shell de gerenciamento do Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="c1407-112">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="c1407-113">Fazer backups rotineiramente.</span><span class="sxs-lookup"><span data-stu-id="c1407-113">Routinely perform backups.</span></span> <span data-ttu-id="c1407-114">Na linha de comando, digite:</span><span class="sxs-lookup"><span data-stu-id="c1407-114">At the command line, type:</span></span>
    
        Export-CsRgsConfiguration -Source "service:ApplicationServer:<primary pool FQDN>" -FileName "<backup path and file name>"
    
    <span data-ttu-id="c1407-115">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="c1407-115">For example:</span></span>
    
        Export-CsRgsConfiguration -Source "service:ApplicationServer:primary.contoso.com" -FileName "C:\RgsExportPrimary.zip"

3.  <span data-ttu-id="c1407-116">Durante uma interrupção, após o failover do pool de backup, importe os grupos de resposta para o pool de backup.</span><span class="sxs-lookup"><span data-stu-id="c1407-116">During an outage, after failover to the backup pool, import the response groups to the backup pool.</span></span> <span data-ttu-id="c1407-117">Na linha de comando, digite:</span><span class="sxs-lookup"><span data-stu-id="c1407-117">At the command line, type:</span></span>
    
        Import-CsRgsConfiguration -Destination "service:ApplicationServer:<backup pool FQDN>" -FileName "<backup path and file name>"
    
    <span data-ttu-id="c1407-118">Se você quiser substituir as configurações no nível do aplicativo no pool de backup pelas configurações do pool primário, inclua o parâmetro – ReplaceExistingSettings.</span><span class="sxs-lookup"><span data-stu-id="c1407-118">If you want to replace the application-level settings in the backup pool with the settings from the primary pool, include the –ReplaceExistingSettings parameter.</span></span> <span data-ttu-id="c1407-119">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="c1407-119">For example:</span></span>
    
        Import-CsRgsConfiguration -Destination "service:ApplicationServer:backup.contoso.com" -FileName "C:\RgsExportPrimary.zip" -ReplaceExistingSettings
    
    <div>
    

    > [!WARNING]  
    > <span data-ttu-id="c1407-120">Se você não substituir as configurações no pool de backup e o pool primário não puder ser recuperado, as configurações do pool primário serão perdidas.</span><span class="sxs-lookup"><span data-stu-id="c1407-120">If you do not replace the settings in the backup pool and the primary pool can't be recovered, the primary pool settings will be lost.</span></span> <span data-ttu-id="c1407-121">Para obter detalhes, consulte <A href="lync-server-2013-planning-for-response-group-disaster-recovery.md">planejando a recuperação de desastres do grupo de resposta no Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="c1407-121">For details, see <A href="lync-server-2013-planning-for-response-group-disaster-recovery.md">Planning for response group disaster recovery in Lync Server 2013</A>.</span></span>

    
    </div>

4.  <span data-ttu-id="c1407-122">Verifique se a importação foi bem-sucedida exibindo os grupos de resposta importados.</span><span class="sxs-lookup"><span data-stu-id="c1407-122">Verify that the import was successful by displaying the imported response groups.</span></span> <span data-ttu-id="c1407-123">Os grupos de resposta importados ainda são pertencentes ao pool primário.</span><span class="sxs-lookup"><span data-stu-id="c1407-123">The imported response groups are still owned by the primary pool.</span></span> <span data-ttu-id="c1407-124">Do the following:</span><span class="sxs-lookup"><span data-stu-id="c1407-124">Do the following:</span></span>
    
      - <span data-ttu-id="c1407-125">Exiba todos os fluxos de trabalho do pool de backup que pertencem ao pool primário e verifique se todos os fluxos de trabalho do pool primário estão incluídos.</span><span class="sxs-lookup"><span data-stu-id="c1407-125">Display all the workflows in the backup pool that are owned by the primary pool, and verify that all the primary pool workflows are included.</span></span> <span data-ttu-id="c1407-126">Na linha de comando, digite:</span><span class="sxs-lookup"><span data-stu-id="c1407-126">At the command line, type:</span></span>
        
            Get-CsRgsWorkflow -Identity "service:ApplicationServer:<backup pool FQDN>" -Owner "service:ApplicationServer"<primary pool FQDN>
        
        <span data-ttu-id="c1407-127">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="c1407-127">For example:</span></span>
        
            Get-CsRgsWorkflow -Identity "service:ApplicationServer:backup.contoso.com" -Owner "service:ApplicationServer:primary.contoso.com"
    
      - <span data-ttu-id="c1407-128">Exiba todas as filas do pool de backup que são Propriedade do pool primário e verifique se todas as filas do pool primário estão incluídas.</span><span class="sxs-lookup"><span data-stu-id="c1407-128">Display all the queues in the backup pool that are owned by the primary pool, and verify that all the primary pool queues are included.</span></span> <span data-ttu-id="c1407-129">Na linha de comando, digite:</span><span class="sxs-lookup"><span data-stu-id="c1407-129">At the command line, type:</span></span>
        
            Get-CsRgsQueue -Identity "service:ApplicationServer:<backup pool FQDN>" -Owner "service:ApplicationServer"<primary pool FQDN>
        
        <span data-ttu-id="c1407-130">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="c1407-130">For example:</span></span>
        
            Get-CsRgsQueue -Identity "service:ApplicationServer:backup.contoso.com" -Owner "service:ApplicationServer"primary.contoso.com"
    
      - <span data-ttu-id="c1407-131">Exiba todos os grupos de agente no pool de backup que pertencem ao pool primário e verifique se todos os grupos de agente de pool primário estão incluídos.</span><span class="sxs-lookup"><span data-stu-id="c1407-131">Display all the agent groups in the backup pool that are owned by the primary pool, and verify that all the primary pool agent groups are included.</span></span> <span data-ttu-id="c1407-132">Na linha de comando, digite:</span><span class="sxs-lookup"><span data-stu-id="c1407-132">At the command line, type:</span></span>
        
            Get-CsRgsAgentGroup -Identity "service:ApplicationServer:<backup pool FQDN>" -Owner "service:ApplicationServer"<primary pool FQDN>
        
        <span data-ttu-id="c1407-133">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="c1407-133">For example:</span></span>
        
            Get-CsRgsAgentGroup -Identity "service:ApplicationServer:backup.contoso.com" -Owner "service:ApplicationServer"primary.contoso.com"
    
      - <span data-ttu-id="c1407-134">Exiba todas as horas de negócios no pool de backup que são Propriedade do pool primário e verifique se todas as horas de trabalho do pool primário estão incluídas.</span><span class="sxs-lookup"><span data-stu-id="c1407-134">Display all the hours of business in the backup pool that are owned by the primary pool, and verify that all the primary pool hours of business are included.</span></span> <span data-ttu-id="c1407-135">Na linha de comando, digite:</span><span class="sxs-lookup"><span data-stu-id="c1407-135">At the command line, type:</span></span>
        
            Get-CsRgsHoursOfBusiness -Identity "service:ApplicationServer:<backup pool FQDN>" -Owner "service:ApplicationServer"<primary pool FQDN>
        
        <span data-ttu-id="c1407-136">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="c1407-136">For example:</span></span>
        
            Get-CsRgsHoursOfBusiness -Identity "service:ApplicationServer:backup.contoso.com" -Owner "service:ApplicationServer"primary.contoso.com"
    
      - <span data-ttu-id="c1407-137">Exiba todos os conjuntos de feriados no pool de backup que pertencem ao pool primário e verifique se todos os conjuntos de feriados do pool primário estão incluídos.</span><span class="sxs-lookup"><span data-stu-id="c1407-137">Display all the holiday sets in the backup pool that are owned by the primary pool, and verify that all the primary pool holiday sets are included.</span></span> <span data-ttu-id="c1407-138">Na linha de comando, digite:</span><span class="sxs-lookup"><span data-stu-id="c1407-138">At the command line, type:</span></span>
        
            Get-CsRgsHolidaySet -Identity "service:ApplicationServer:<backup pool FQDN>" -Owner "service:ApplicationServer"<primary pool FQDN>
        
        <span data-ttu-id="c1407-139">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="c1407-139">For example:</span></span>
        
            Get-CsRgsHolidaySet -Identity "service:ApplicationServer:backup.contoso.com" -Owner "service:ApplicationServer"primary.contoso.com"
    
    <span data-ttu-id="c1407-140">Como alternativa, você pode exibir todos os grupos de resposta no pool de backup, incluindo aqueles pertencentes ao pool primário e àqueles pertencentes ao pool de backup usando o parâmetro – ShowAll em vez do parâmetro – Owner.</span><span class="sxs-lookup"><span data-stu-id="c1407-140">Alternatively, you can display all the response groups in the backup pool, including the ones owned by the primary pool and the ones owned by the backup pool by using the –ShowAll parameter instead of the –Owner parameter.</span></span> <span data-ttu-id="c1407-141">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="c1407-141">For example:</span></span>
    
        Get-CsRgsWorkflow -Identity "service:ApplicationServer:<backup pool FQDN>" -ShowAll
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="c1407-142">Você deve usar o parâmetro – ShowAll ou o parâmetro – Owner.</span><span class="sxs-lookup"><span data-stu-id="c1407-142">You must use either the –ShowAll parameter or the –Owner parameter.</span></span> <span data-ttu-id="c1407-143">Se você não usar nenhum desses parâmetros, os grupos de resposta que você importou para o pool de backup não serão listados nos resultados retornados pelos cmdlets.</span><span class="sxs-lookup"><span data-stu-id="c1407-143">If you do not use either of these parameters, the response groups that you imported to the backup pool will not be listed in the results returned by the cmdlets.</span></span>

    
    </div>

5.  <span data-ttu-id="c1407-144">Verifique se a importação foi bem-sucedida fazendo uma chamada para um grupo de resposta importada e verificando se a chamada foi manipulada corretamente.</span><span class="sxs-lookup"><span data-stu-id="c1407-144">Verify that the import was successful by placing a call to an imported response group and verifying that the call is handled correctly.</span></span>

6.  <span data-ttu-id="c1407-145">Solicite aos agentes que são membros de grupos de agentes formais para entrar em seus grupos de agente no pool de backup.</span><span class="sxs-lookup"><span data-stu-id="c1407-145">Request agents who are members of formal agent groups to sign in to their agent groups in the backup pool.</span></span>

7.  <span data-ttu-id="c1407-146">Gerencie e modifique os grupos de resposta importados normalmente.</span><span class="sxs-lookup"><span data-stu-id="c1407-146">Manage and modify the imported response groups as usual.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="c1407-147">Enquanto os grupos de resposta estiverem no pool de backup, você precisará usar o Shell de gerenciamento do Lync Server para gerenciá-los.</span><span class="sxs-lookup"><span data-stu-id="c1407-147">While the response groups are in the backup pool, you need to use Lync Server Management Shell to manage them.</span></span> <span data-ttu-id="c1407-148">Você não pode usar o painel de controle do Lync Server para gerenciar os grupos de resposta importados para o pool de backup.</span><span class="sxs-lookup"><span data-stu-id="c1407-148">You cannot use Lync Server Control Panel to manage the response groups that you imported to the backup pool.</span></span>

    
    </div>

8.  <span data-ttu-id="c1407-149">Depois que o pool primário for restaurado e o failback estiver concluído, exporte os grupos de resposta de pool primário que foram importados para o pool de backup.</span><span class="sxs-lookup"><span data-stu-id="c1407-149">After the primary pool is restored and failback is complete, export the primary pool response groups that were imported to the backup pool.</span></span> <span data-ttu-id="c1407-150">Na linha de comando, digite:</span><span class="sxs-lookup"><span data-stu-id="c1407-150">At the command line, type:</span></span>
    
        Export-CsRgsConfiguration -Source ApplicationServer:<backup pool FQDN> -Owner ApplicationServer:<primary pool FQDN> -FileName "<backup path and file name>"

9.  <span data-ttu-id="c1407-151">Importe os grupos de resposta de volta para o pool primário.</span><span class="sxs-lookup"><span data-stu-id="c1407-151">Import the response groups back to the primary pool.</span></span> <span data-ttu-id="c1407-152">Na linha de comando, digite:</span><span class="sxs-lookup"><span data-stu-id="c1407-152">At the command line, type:</span></span>
    
        Import-CsRgsConfiguration -Destination "service:ApplicationServer:<primary pool FQDN>" -OverwriteOwner -FileName "<exported path and file name>"
    
    <span data-ttu-id="c1407-153">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="c1407-153">For example:</span></span>
    
        Import-CsRgsConfiguration -Destination "service:ApplicationServer:primary.contoso.com" -OverwriteOwner -FileName "C:\RgsExportPrimaryUpdated.zip"
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="c1407-154">Se você recriar um pool durante a recuperação, seja com o mesmo ou um nome de domínio totalmente qualificado (FQDN) diferente, será necessário usar o parâmetro – OverwriteOwner.</span><span class="sxs-lookup"><span data-stu-id="c1407-154">If you rebuild a pool during recovery, whether with the same or a different fully qualified domain name (FQDN), you need to use the –OverwriteOwner parameter.</span></span> <span data-ttu-id="c1407-155">Como regra geral, você sempre pode usar o parâmetro – OverwriteOwner ao importar grupos de resposta de volta para o pool primário.</span><span class="sxs-lookup"><span data-stu-id="c1407-155">As a rule of thumb, you can always use the –OverwriteOwner parameter when you import response groups back to the primary pool.</span></span>

    
    </div>
    
    <span data-ttu-id="c1407-156">Se você implantou um novo pool (com o mesmo ou um FQDN diferente) para substituir o pool primário e deseja usar as configurações no nível do aplicativo a partir do pool de backup para o novo pool, inclua o parâmetro – ReplaceExistingSettings.</span><span class="sxs-lookup"><span data-stu-id="c1407-156">If you deployed a new pool (with the same or a different FQDN) to replace the primary pool, and you want to use the application-level settings from the backup pool for the new pool, include the –ReplaceExistingSettings parameter.</span></span> <span data-ttu-id="c1407-157">Na linha de comando, digite:</span><span class="sxs-lookup"><span data-stu-id="c1407-157">At the command line, type:</span></span>
    
        Import-CsRgsConfiguration -Destination "service:ApplicationServer:<new primary pool FQDN>" -OverwriteOwner -FileName "<exported path and file name>" -ReplaceExistingSettings
    
    <span data-ttu-id="c1407-158">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="c1407-158">For example:</span></span>
    
        Import-CsRgsConfiguration -Destination "service:ApplicationServer:newprimary.contoso.com" -OverwriteOwner -FileName "C:\RgsExportPrimaryUpdated.zip" -ReplaceExistingSettings
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="c1407-159">Se você não quiser substituir as configurações no nível do aplicativo e o arquivo de áudio de música em espera padrão para o novo pool com as configurações do pool de backup, o novo pool usará as configurações padrão do aplicativo no nível do aplicativo.</span><span class="sxs-lookup"><span data-stu-id="c1407-159">If you don't want to replace the application-level settings and default music-on-hold audio file for the new pool with the settings from the backup pool, the new pool will use the default application-level settings.</span></span>

    
    </div>

10. <span data-ttu-id="c1407-160">Verifique se a importação de volta para o pool primário foi bem-sucedida exibindo a configuração do grupo de resposta importado.</span><span class="sxs-lookup"><span data-stu-id="c1407-160">Verify that the import back to the primary pool was successful by displaying the imported response group configuration.</span></span> <span data-ttu-id="c1407-161">Do the following:</span><span class="sxs-lookup"><span data-stu-id="c1407-161">Do the following:</span></span>
    
      - <span data-ttu-id="c1407-162">Exiba todos os fluxos de trabalho no pool primário e verifique se todos os fluxos de trabalho importados estão incluídos.</span><span class="sxs-lookup"><span data-stu-id="c1407-162">Display all the workflows in the primary pool, and verify that all the imported workflows are included.</span></span> <span data-ttu-id="c1407-163">Na linha de comando, digite:</span><span class="sxs-lookup"><span data-stu-id="c1407-163">At the command line, type:</span></span>
        
            Get-CsRgsWorkflow -Identity "service:ApplicationServer:<primary pool FQDN>" -ShowAll
        
        <span data-ttu-id="c1407-164">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="c1407-164">For example:</span></span>
        
            Get-CsRgsWorkflow -Identity "service:ApplicationServer: primary.contoso.com" -ShowAll
    
      - <span data-ttu-id="c1407-165">Exiba todas as filas no pool primário e verifique se todas as filas importadas estão incluídas.</span><span class="sxs-lookup"><span data-stu-id="c1407-165">Display all the queues in the primary pool, and verify that all the imported queues are included.</span></span> <span data-ttu-id="c1407-166">Na linha de comando, digite:</span><span class="sxs-lookup"><span data-stu-id="c1407-166">At the command line, type:</span></span>
        
            Get-CsRgsQueue -Identity "service:ApplicationServer:<primary pool FQDN>" -ShowAll
        
        <span data-ttu-id="c1407-167">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="c1407-167">For example:</span></span>
        
            Get-CsRgsQueue -Identity "service:ApplicationServer:primary.contoso.com" -ShowAll
    
      - <span data-ttu-id="c1407-168">Exiba todos os grupos de agente no pool primário e verifique se todos os grupos de agentes importados estão incluídos.</span><span class="sxs-lookup"><span data-stu-id="c1407-168">Display all the agent groups in the primary pool, and verify that all the imported agent groups are included.</span></span> <span data-ttu-id="c1407-169">Na linha de comando, digite:</span><span class="sxs-lookup"><span data-stu-id="c1407-169">At the command line, type:</span></span>
        
            Get-CsRgsAgentGroup -Identity "service:ApplicationServer: <primary pool FQDN>" -ShowAll
        
        <span data-ttu-id="c1407-170">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="c1407-170">For example:</span></span>
        
            Get-CsRgsAgentGroup -Identity "service:ApplicationServer:primary.contoso.com" -ShowAll
    
      - <span data-ttu-id="c1407-171">Exiba todas as horas de negócios no pool principal e verifique se todas as horas de trabalho importadas estão incluídas.</span><span class="sxs-lookup"><span data-stu-id="c1407-171">Display all the hours of business in the primary pool, and verify that all the imported hours of business are included.</span></span> <span data-ttu-id="c1407-172">Na linha de comando, digite:</span><span class="sxs-lookup"><span data-stu-id="c1407-172">At the command line, type:</span></span>
        
            Get-CsRgsHoursOfBusiness -Identity "service:ApplicationServer:<primary pool FQDN>" -ShowAll
        
        <span data-ttu-id="c1407-173">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="c1407-173">For example:</span></span>
        
            Get-CsRgsHoursOfBusiness -Identity "service:ApplicationServer:primary.contoso.com" -ShowAll
    
      - <span data-ttu-id="c1407-174">Exiba todos os conjuntos de feriados no pool primário e verifique se todos os conjuntos de feriados importados estão incluídos.</span><span class="sxs-lookup"><span data-stu-id="c1407-174">Display all the holiday sets in the primary pool, and verify that all the imported holiday sets are included.</span></span> <span data-ttu-id="c1407-175">Na linha de comando, digite:</span><span class="sxs-lookup"><span data-stu-id="c1407-175">At the command line, type:</span></span>
        
            Get-CsRgsHolidaySet -Identity "service:ApplicationServer:<primary pool FQDN>" -ShowAll
        
        <span data-ttu-id="c1407-176">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="c1407-176">For example:</span></span>
        
            Get-CsRgsHolidaySet -Identity "service:ApplicationServer:primary.contoso.com" -ShowAll

11. <span data-ttu-id="c1407-177">Verifique se a importação foi bem-sucedida fazendo uma chamada para um grupo de resposta importada e verificando se a chamada foi manipulada corretamente.</span><span class="sxs-lookup"><span data-stu-id="c1407-177">Verify that the import was successful by placing a call to an imported response group and verifying that the call is handled correctly.</span></span>

12. <span data-ttu-id="c1407-178">Opcionalmente, remova os grupos de resposta pertencentes ao pool principal do pool de backup.</span><span class="sxs-lookup"><span data-stu-id="c1407-178">Optionally, remove the response groups owned by the primary pool from the backup pool.</span></span> <span data-ttu-id="c1407-179">Na linha de comando, digite:</span><span class="sxs-lookup"><span data-stu-id="c1407-179">At the command line, type:</span></span>
    
        Export-CsRgsConfiguration -Source "service:ApplicationServer:<backup pool FQDN>" -Owner "service:ApplicationServer:<primary pool FQDN>" -FileName "<backup path and file name>" -RemoveExportedConfiguration
    
    <span data-ttu-id="c1407-180">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="c1407-180">For example:</span></span>
    
        Export-CsRgsConfiguration -Source "service:ApplicationServer:backup.contoso.com" -Owner "service:ApplicationServer:primary.contoso.com" -FileName "C:\RgsExportPrimaryUpdated.zip" -RemoveExportedConfiguration
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="c1407-181">Esta etapa cria um novo arquivo com a configuração exportada e, em seguida, remove-o do pool de backup.</span><span class="sxs-lookup"><span data-stu-id="c1407-181">This step creates a new file with the exported configuration, and then removes it from the backup pool.</span></span>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

