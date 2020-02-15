---
title: Procedimentos de recuperação de desastre do grupo de resposta do Lync Server 2013
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Response group disaster recovery procedures
ms:assetid: b49577b7-0ca3-4f20-b614-f3a2a0046b58
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205186(v=OCS.15)
ms:contentKeyID: 48185171
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 73b5dba010da09fb20c96ca6b14de2f881e32b60
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42051695"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="response-group-disaster-recovery-procedures-in-lync-server-2013"></a><span data-ttu-id="c36fd-102">Procedimentos de recuperação de desastre do grupo de resposta no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c36fd-102">Response group disaster recovery procedures in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c36fd-103">_**Última modificação do tópico:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="c36fd-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="c36fd-104">Durante a fase de failover ou de recuperação de desastres, o grupo de resposta reside em vários pools: no pool principal (que está indisponível) e no de backup.</span><span class="sxs-lookup"><span data-stu-id="c36fd-104">During the failover phase of disaster recovery, the response groups reside in multiple pools: in the primary pool (which is unavailable) and in the backup pool.</span></span> <span data-ttu-id="c36fd-105">Os grupos de resposta em ambos os pools têm o mesmo nome e proprietário (o pool principal), mas têm pais diferentes.</span><span class="sxs-lookup"><span data-stu-id="c36fd-105">The response groups in both pools have the same name and the same owner (the primary pool), but they have different parents.</span></span> <span data-ttu-id="c36fd-106">Durante esse tempo, os cmdlets do grupo de resposta funcionam de forma um pouco diferente.</span><span class="sxs-lookup"><span data-stu-id="c36fd-106">During this time, Response Group cmdlets work a little differently.</span></span> <span data-ttu-id="c36fd-107">Certifique-se de usar parâmetros como especificado no seguinte procedimento.</span><span class="sxs-lookup"><span data-stu-id="c36fd-107">Be sure to use parameters as specified in the following procedure.</span></span> <span data-ttu-id="c36fd-108">Para obter detalhes sobre como os cmdlets funcionam durante a fase de failover, consulte o artigo de blog NextHop "Lync Server 2013: Recuperando grupos de resposta [http://go.microsoft.com/fwlink/p/?LinkId=263957](http://go.microsoft.com/fwlink/p/?linkid=263957)durante a recuperação de desastres" em.</span><span class="sxs-lookup"><span data-stu-id="c36fd-108">For details about how cmdlets work during the failover phase, see NextHop blog article "Lync Server 2013: Recovering Response Groups During Disaster Recovery" at [http://go.microsoft.com/fwlink/p/?LinkId=263957](http://go.microsoft.com/fwlink/p/?linkid=263957).</span></span> <span data-ttu-id="c36fd-109">Este artigo do blog também se aplica à versão lançada do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="c36fd-109">This blog article also applies to the released version of Lync Server 2013.</span></span>

<span data-ttu-id="c36fd-110">Use as etapas do procedimento a seguir para preparar e executar a recuperação de desastres para o serviço de grupo de resposta do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="c36fd-110">Use the steps in the following procedure to prepare for and perform disaster recovery for Lync Server Response Group service.</span></span>

<div>

## <a name="to-fail-over-and-fail-back-response-group"></a><span data-ttu-id="c36fd-111">Execução de failover e failback do grupo de resposta</span><span class="sxs-lookup"><span data-stu-id="c36fd-111">To fail over and fail back Response Group</span></span>

1.  <span data-ttu-id="c36fd-112">Inicie o Shell de Gerenciamento do Lync Server: clique em **Iniciar**, em **Todos os Programas**, em **Microsoft Lync Server 2013** e em **Shell de Gerenciamento do Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="c36fd-112">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="c36fd-p102">Execute backups de rotina. Na linha de comando, digite:</span><span class="sxs-lookup"><span data-stu-id="c36fd-p102">Routinely perform backups. At the command line, type:</span></span>
    
        Export-CsRgsConfiguration -Source "service:ApplicationServer:<primary pool FQDN>" -FileName "<backup path and file name>"
    
    <span data-ttu-id="c36fd-115">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="c36fd-115">For example:</span></span>
    
        Export-CsRgsConfiguration -Source "service:ApplicationServer:primary.contoso.com" -FileName "C:\RgsExportPrimary.zip"

3.  <span data-ttu-id="c36fd-p103">Durante uma falha, depois do failover do pool de backup, importe os grupos de resposta para o pool de backup. Na linha de comando, digite:</span><span class="sxs-lookup"><span data-stu-id="c36fd-p103">During an outage, after failover to the backup pool, import the response groups to the backup pool. At the command line, type:</span></span>
    
        Import-CsRgsConfiguration -Destination "service:ApplicationServer:<backup pool FQDN>" -FileName "<backup path and file name>"
    
    <span data-ttu-id="c36fd-p104">Se deseja substituir as configuração de nível do aplicativo no pool de backup pelas configurações do pool principal, inclua o parâmetro –ReplaceExistingSettings. Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="c36fd-p104">If you want to replace the application-level settings in the backup pool with the settings from the primary pool, include the –ReplaceExistingSettings parameter. For example:</span></span>
    
        Import-CsRgsConfiguration -Destination "service:ApplicationServer:backup.contoso.com" -FileName "C:\RgsExportPrimary.zip" -ReplaceExistingSettings
    
    <div>
    

    > [!WARNING]  
    > <span data-ttu-id="c36fd-120">Se não substituir as configurações no pool de backup e não for possível recuperar o pool principal, então as configurações do pool principal serão perdidas.</span><span class="sxs-lookup"><span data-stu-id="c36fd-120">If you do not replace the settings in the backup pool and the primary pool can't be recovered, the primary pool settings will be lost.</span></span> <span data-ttu-id="c36fd-121">Para obter detalhes, consulte <A href="lync-server-2013-planning-for-response-group-disaster-recovery.md">Planning for Response Group Disaster Recovery in Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="c36fd-121">For details, see <A href="lync-server-2013-planning-for-response-group-disaster-recovery.md">Planning for response group disaster recovery in Lync Server 2013</A>.</span></span>

    
    </div>

4.  <span data-ttu-id="c36fd-p106">Verifique se a importação ocorreu exibindo os grupos de resposta importados. Os grupos de resposta importados ainda são de propriedade do pool principal. Faça o seguinte:</span><span class="sxs-lookup"><span data-stu-id="c36fd-p106">Verify that the import was successful by displaying the imported response groups. The imported response groups are still owned by the primary pool. Do the following:</span></span>
    
      - <span data-ttu-id="c36fd-p107">Visualize todos os fluxos de trabalho no pool de backup que são de propriedade do pool principal e verifique se todos os fluxos de trabalho do pool principal estão incluídos. Na linha de comando, digite:</span><span class="sxs-lookup"><span data-stu-id="c36fd-p107">Display all the workflows in the backup pool that are owned by the primary pool, and verify that all the primary pool workflows are included. At the command line, type:</span></span>
        
            Get-CsRgsWorkflow -Identity "service:ApplicationServer:<backup pool FQDN>" -Owner "service:ApplicationServer"<primary pool FQDN>
        
        <span data-ttu-id="c36fd-127">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="c36fd-127">For example:</span></span>
        
            Get-CsRgsWorkflow -Identity "service:ApplicationServer:backup.contoso.com" -Owner "service:ApplicationServer:primary.contoso.com"
    
      - <span data-ttu-id="c36fd-p108">Visualize todas as filas no pool de backup que são de propriedade do pool principal e verifique se todas as filas do pool principal foram incluídas. Na linha de comando, digite:</span><span class="sxs-lookup"><span data-stu-id="c36fd-p108">Display all the queues in the backup pool that are owned by the primary pool, and verify that all the primary pool queues are included. At the command line, type:</span></span>
        
            Get-CsRgsQueue -Identity "service:ApplicationServer:<backup pool FQDN>" -Owner "service:ApplicationServer"<primary pool FQDN>
        
        <span data-ttu-id="c36fd-130">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="c36fd-130">For example:</span></span>
        
            Get-CsRgsQueue -Identity "service:ApplicationServer:backup.contoso.com" -Owner "service:ApplicationServer"primary.contoso.com"
    
      - <span data-ttu-id="c36fd-p109">Visualize todos os grupos de agentes no pool de backup que são de propriedade do pool principal e verifique se todos os grupos de agentes do pool principal foram incluídos. Na linha de comando, digite:</span><span class="sxs-lookup"><span data-stu-id="c36fd-p109">Display all the agent groups in the backup pool that are owned by the primary pool, and verify that all the primary pool agent groups are included. At the command line, type:</span></span>
        
            Get-CsRgsAgentGroup -Identity "service:ApplicationServer:<backup pool FQDN>" -Owner "service:ApplicationServer"<primary pool FQDN>
        
        <span data-ttu-id="c36fd-133">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="c36fd-133">For example:</span></span>
        
            Get-CsRgsAgentGroup -Identity "service:ApplicationServer:backup.contoso.com" -Owner "service:ApplicationServer"primary.contoso.com"
    
      - <span data-ttu-id="c36fd-p110">Visualize todos os horários comerciais no pool de backup que são de propriedade do pool principal e verifique se todas as horas comerciais do pool principal foram incluídas. Na linha de comando, digite:</span><span class="sxs-lookup"><span data-stu-id="c36fd-p110">Display all the hours of business in the backup pool that are owned by the primary pool, and verify that all the primary pool hours of business are included. At the command line, type:</span></span>
        
            Get-CsRgsHoursOfBusiness -Identity "service:ApplicationServer:<backup pool FQDN>" -Owner "service:ApplicationServer"<primary pool FQDN>
        
        <span data-ttu-id="c36fd-136">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="c36fd-136">For example:</span></span>
        
            Get-CsRgsHoursOfBusiness -Identity "service:ApplicationServer:backup.contoso.com" -Owner "service:ApplicationServer"primary.contoso.com"
    
      - <span data-ttu-id="c36fd-p111">Visualize todos os conjuntos de feriados no pool de backup que são de propriedade do pool principal e verifique se todos os conjuntos de feriados do pool principal estão incluídos. Na linha de comando, digite:</span><span class="sxs-lookup"><span data-stu-id="c36fd-p111">Display all the holiday sets in the backup pool that are owned by the primary pool, and verify that all the primary pool holiday sets are included. At the command line, type:</span></span>
        
            Get-CsRgsHolidaySet -Identity "service:ApplicationServer:<backup pool FQDN>" -Owner "service:ApplicationServer"<primary pool FQDN>
        
        <span data-ttu-id="c36fd-139">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="c36fd-139">For example:</span></span>
        
            Get-CsRgsHolidaySet -Identity "service:ApplicationServer:backup.contoso.com" -Owner "service:ApplicationServer"primary.contoso.com"
    
    <span data-ttu-id="c36fd-p112">Como alternativa, você pode exibir todos os grupos de resposta no pool de backup, incluindo os de propriedade do pool principal e os do pool de backup usando o parâmetro –ShowAll em vez de –Owner. Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="c36fd-p112">Alternatively, you can display all the response groups in the backup pool, including the ones owned by the primary pool and the ones owned by the backup pool by using the –ShowAll parameter instead of the –Owner parameter. For example:</span></span>
    
        Get-CsRgsWorkflow -Identity "service:ApplicationServer:<backup pool FQDN>" -ShowAll
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="c36fd-p113">Você deve usar o parâmetro –ShowAll ou –Owner. Se não usar nenhum deles, os grupos de resposta importados para o pool de backup não serão listado nos resultados retornados pelos cmdlets.</span><span class="sxs-lookup"><span data-stu-id="c36fd-p113">You must use either the –ShowAll parameter or the –Owner parameter. If you do not use either of these parameters, the response groups that you imported to the backup pool will not be listed in the results returned by the cmdlets.</span></span>

    
    </div>

5.  <span data-ttu-id="c36fd-144">Verifique se a importação teve êxito fazendo uma chamada para um grupo de resposta importado e verificando se a chamada foi manipulada corretamente.</span><span class="sxs-lookup"><span data-stu-id="c36fd-144">Verify that the import was successful by placing a call to an imported response group and verifying that the call is handled correctly.</span></span>

6.  <span data-ttu-id="c36fd-145">Solicite que agentes membros de grupos de agentes formais se conectem a seus grupos de agentes no pool de backup.</span><span class="sxs-lookup"><span data-stu-id="c36fd-145">Request agents who are members of formal agent groups to sign in to their agent groups in the backup pool.</span></span>

7.  <span data-ttu-id="c36fd-146">Gerencie e modifique os grupos de resposta importados normalmente.</span><span class="sxs-lookup"><span data-stu-id="c36fd-146">Manage and modify the imported response groups as usual.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="c36fd-147">Enquanto os grupos de resposta estão no pool de backup, você precisa usar o Shell de gerenciamento do Lync Server para gerenciá-los.</span><span class="sxs-lookup"><span data-stu-id="c36fd-147">While the response groups are in the backup pool, you need to use Lync Server Management Shell to manage them.</span></span> <span data-ttu-id="c36fd-148">Você não pode usar o painel de controle do Lync Server para gerenciar os grupos de resposta importados para o pool de backup.</span><span class="sxs-lookup"><span data-stu-id="c36fd-148">You cannot use Lync Server Control Panel to manage the response groups that you imported to the backup pool.</span></span>

    
    </div>

8.  <span data-ttu-id="c36fd-p115">Depois que o pool principal é restaurado e o failback for concluído, exporte os grupos de resposta de pool principal que foram importados para o pool de backup. Na linha de comando, digite:</span><span class="sxs-lookup"><span data-stu-id="c36fd-p115">After the primary pool is restored and failback is complete, export the primary pool response groups that were imported to the backup pool. At the command line, type:</span></span>
    
        Export-CsRgsConfiguration -Source ApplicationServer:<backup pool FQDN> -Owner ApplicationServer:<primary pool FQDN> -FileName "<backup path and file name>"

9.  <span data-ttu-id="c36fd-p116">Importe os grupos de resposta para o pool principal. Na linha de comando, digite:</span><span class="sxs-lookup"><span data-stu-id="c36fd-p116">Import the response groups back to the primary pool. At the command line, type:</span></span>
    
        Import-CsRgsConfiguration -Destination "service:ApplicationServer:<primary pool FQDN>" -OverwriteOwner -FileName "<exported path and file name>"
    
    <span data-ttu-id="c36fd-153">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="c36fd-153">For example:</span></span>
    
        Import-CsRgsConfiguration -Destination "service:ApplicationServer:primary.contoso.com" -OverwriteOwner -FileName "C:\RgsExportPrimaryUpdated.zip"
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="c36fd-p117">Se reconstruir um pool durante a recuperação, com o mesmo nome de domínio qualificado (FQDN) ou um diferente, será necessário usar o parâmetro –OverwriteOwner. Como regra, você sempre pode usar o parâmetro –OverwriteOwner ao importar grupos de resposta para o pool primário.</span><span class="sxs-lookup"><span data-stu-id="c36fd-p117">If you rebuild a pool during recovery, whether with the same or a different fully qualified domain name (FQDN), you need to use the –OverwriteOwner parameter. As a rule of thumb, you can always use the –OverwriteOwner parameter when you import response groups back to the primary pool.</span></span>

    
    </div>
    
    <span data-ttu-id="c36fd-p118">Se você implantou um novo pool (como um FQDN igual ou diferente) para substituir o pool principal e deseja usar as configurações de nível de aplicativo do pool de backup para o novo pool, inclua o parâmetro –ReplaceExistingSettings. Na linha de comando, digite:</span><span class="sxs-lookup"><span data-stu-id="c36fd-p118">If you deployed a new pool (with the same or a different FQDN) to replace the primary pool, and you want to use the application-level settings from the backup pool for the new pool, include the –ReplaceExistingSettings parameter. At the command line, type:</span></span>
    
        Import-CsRgsConfiguration -Destination "service:ApplicationServer:<new primary pool FQDN>" -OverwriteOwner -FileName "<exported path and file name>" -ReplaceExistingSettings
    
    <span data-ttu-id="c36fd-158">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="c36fd-158">For example:</span></span>
    
        Import-CsRgsConfiguration -Destination "service:ApplicationServer:newprimary.contoso.com" -OverwriteOwner -FileName "C:\RgsExportPrimaryUpdated.zip" -ReplaceExistingSettings
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="c36fd-159">Se não deseja substituir as configurações de nível de aplicativo e o arquivo de música de espera padrão do novo pool pelas configurações do pool de backup, então o novo pool usará as configurações de aplicativo padrão.</span><span class="sxs-lookup"><span data-stu-id="c36fd-159">If you don't want to replace the application-level settings and default music-on-hold audio file for the new pool with the settings from the backup pool, the new pool will use the default application-level settings.</span></span>

    
    </div>

10. <span data-ttu-id="c36fd-p119">Verifique se a importação para o pool principal teve êxito exibindo a configuração do grupo de resposta importado. Faça o seguinte:</span><span class="sxs-lookup"><span data-stu-id="c36fd-p119">Verify that the import back to the primary pool was successful by displaying the imported response group configuration. Do the following:</span></span>
    
      - <span data-ttu-id="c36fd-p120">Visualize todos os fluxos de trabalho no pool principal e verifique se todos os fluxos de trabalho importados foram incluídos. Na linha de comando, digite:</span><span class="sxs-lookup"><span data-stu-id="c36fd-p120">Display all the workflows in the primary pool, and verify that all the imported workflows are included. At the command line, type:</span></span>
        
            Get-CsRgsWorkflow -Identity "service:ApplicationServer:<primary pool FQDN>" -ShowAll
        
        <span data-ttu-id="c36fd-164">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="c36fd-164">For example:</span></span>
        
            Get-CsRgsWorkflow -Identity "service:ApplicationServer: primary.contoso.com" -ShowAll
    
      - <span data-ttu-id="c36fd-p121">Visualize todas as filas no pool principal e verifique se todas as filas importadas foram incluídas. Na linha de comando, digite:</span><span class="sxs-lookup"><span data-stu-id="c36fd-p121">Display all the queues in the primary pool, and verify that all the imported queues are included. At the command line, type:</span></span>
        
            Get-CsRgsQueue -Identity "service:ApplicationServer:<primary pool FQDN>" -ShowAll
        
        <span data-ttu-id="c36fd-167">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="c36fd-167">For example:</span></span>
        
            Get-CsRgsQueue -Identity "service:ApplicationServer:primary.contoso.com" -ShowAll
    
      - <span data-ttu-id="c36fd-p122">Visualize todos os grupos de agentes no pool principal e verifique se todos os grupos de agentes importados foram incluídos. Na linha de comando, digite:</span><span class="sxs-lookup"><span data-stu-id="c36fd-p122">Display all the agent groups in the primary pool, and verify that all the imported agent groups are included. At the command line, type:</span></span>
        
            Get-CsRgsAgentGroup -Identity "service:ApplicationServer: <primary pool FQDN>" -ShowAll
        
        <span data-ttu-id="c36fd-170">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="c36fd-170">For example:</span></span>
        
            Get-CsRgsAgentGroup -Identity "service:ApplicationServer:primary.contoso.com" -ShowAll
    
      - <span data-ttu-id="c36fd-p123">Visualize todas as horas comerciais no pool principal e verifique se todas as horas comerciais importadas foram incluídas. Na linha de comando, digite:</span><span class="sxs-lookup"><span data-stu-id="c36fd-p123">Display all the hours of business in the primary pool, and verify that all the imported hours of business are included. At the command line, type:</span></span>
        
            Get-CsRgsHoursOfBusiness -Identity "service:ApplicationServer:<primary pool FQDN>" -ShowAll
        
        <span data-ttu-id="c36fd-173">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="c36fd-173">For example:</span></span>
        
            Get-CsRgsHoursOfBusiness -Identity "service:ApplicationServer:primary.contoso.com" -ShowAll
    
      - <span data-ttu-id="c36fd-p124">Visualize todos os conjuntos de feriados no pool principal e verifique se todos os conjuntos de feriados importados foram incluídos. Na linha de comando, digite:</span><span class="sxs-lookup"><span data-stu-id="c36fd-p124">Display all the holiday sets in the primary pool, and verify that all the imported holiday sets are included. At the command line, type:</span></span>
        
            Get-CsRgsHolidaySet -Identity "service:ApplicationServer:<primary pool FQDN>" -ShowAll
        
        <span data-ttu-id="c36fd-176">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="c36fd-176">For example:</span></span>
        
            Get-CsRgsHolidaySet -Identity "service:ApplicationServer:primary.contoso.com" -ShowAll

11. <span data-ttu-id="c36fd-177">Verifique se a importação teve êxito fazendo uma chamada para um grupo de resposta importado e verificando se a chamada foi manipulada corretamente.</span><span class="sxs-lookup"><span data-stu-id="c36fd-177">Verify that the import was successful by placing a call to an imported response group and verifying that the call is handled correctly.</span></span>

12. <span data-ttu-id="c36fd-p125">Como opção, remova os grupos de resposta do pool principal do pool de backup. Na linha de comando, digite:</span><span class="sxs-lookup"><span data-stu-id="c36fd-p125">Optionally, remove the response groups owned by the primary pool from the backup pool. At the command line, type:</span></span>
    
        Export-CsRgsConfiguration -Source "service:ApplicationServer:<backup pool FQDN>" -Owner "service:ApplicationServer:<primary pool FQDN>" -FileName "<backup path and file name>" -RemoveExportedConfiguration
    
    <span data-ttu-id="c36fd-180">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="c36fd-180">For example:</span></span>
    
        Export-CsRgsConfiguration -Source "service:ApplicationServer:backup.contoso.com" -Owner "service:ApplicationServer:primary.contoso.com" -FileName "C:\RgsExportPrimaryUpdated.zip" -RemoveExportedConfiguration
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="c36fd-181">Esta etapa crie um novo arquivo com a configuração exportada e o remove do pool de backup.</span><span class="sxs-lookup"><span data-stu-id="c36fd-181">This step creates a new file with the exported configuration, and then removes it from the backup pool.</span></span>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

