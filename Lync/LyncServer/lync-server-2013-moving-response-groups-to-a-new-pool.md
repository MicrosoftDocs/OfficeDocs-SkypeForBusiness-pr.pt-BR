---
title: 'Lync Server 2013: movendo grupos de resposta para um novo pool'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Moving response groups to a new pool
ms:assetid: da0db765-41e5-430b-b5a7-5418ec5ff2a7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205298(v=OCS.15)
ms:contentKeyID: 48185538
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 73138d5cbde1a835ab632fe98bf57ef58f11c0da
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42217147"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="moving-response-groups-to-a-new-pool-in-lync-server-2013"></a><span data-ttu-id="98d59-102">Movendo grupos de resposta para um novo pool no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="98d59-102">Moving response groups to a new pool in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="98d59-103">_**Última modificação do tópico:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="98d59-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="98d59-104">O Lync Server 2013 introduz novo cmdlet support para mover grupos de resposta de um pool para outro pool, mesmo quando o FQDN (nome de domínio totalmente qualificado) for diferente.</span><span class="sxs-lookup"><span data-stu-id="98d59-104">Lync Server 2013 introduces new cmdlet support for moving response groups from one pool to another pool, even when the fully qualified domain name (FQDN) is different.</span></span>

<span data-ttu-id="98d59-105">Use as etapas no procedimento a seguir para mover grupos de resposta de um pool de front-ends para outro pool de front-ends com um FQDN diferente.</span><span class="sxs-lookup"><span data-stu-id="98d59-105">Use the steps in the following procedure to move response groups from one Front End pool to another Front End pool with a different FQDN.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="98d59-106">Em um ambiente de coexistência, você pode mover grupos de resposta somente entre pools de front-ends do Lync Server 2013&nbsp;.</span><span class="sxs-lookup"><span data-stu-id="98d59-106">In a coexistence environment, you can move response groups only between Lync Server 2013&nbsp;Front End pools.</span></span>



</div>

<div>

## <a name="to-move-response-groups-to-a-pool-with-a-different-fqdn"></a><span data-ttu-id="98d59-107">Para mover grupos de resposta para um pool com um FQDN diferente</span><span class="sxs-lookup"><span data-stu-id="98d59-107">To move response groups to a pool with a different FQDN</span></span>

1.  <span data-ttu-id="98d59-108">Inicie o Shell de Gerenciamento do Lync Server: clique em **Iniciar**, em **Todos os Programas**, em **Microsoft Lync Server 2013** e em **Shell de Gerenciamento do Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="98d59-108">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="98d59-p101">Exporte os grupos de resposta no pool de origem. Na linha de comando, digite:</span><span class="sxs-lookup"><span data-stu-id="98d59-p101">Export the response groups in the source pool. At the command line, type:</span></span>
    
        Export-CsRgsConfiguration -Source "service:ApplicationServer:<source FQDN>" -FileName "<export file name>"
    
    <span data-ttu-id="98d59-111">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="98d59-111">For example:</span></span>
    
        Export-CsRgsConfiguration -Source "service:ApplicationServer:source.contoso.com" -FileName "C:\RgsExportSource.zip"
    
    <span data-ttu-id="98d59-p102">Para remover os grupos de resposta de um pool de origem durante a exportação, inclua o parâmetro –RemoveExportedConfiguration. Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="98d59-p102">To remove the response groups from the source pool during the export, include the –RemoveExportedConfiguration parameter. For example:</span></span>
    
        Export-CsRgsConfiguration -Source ApplicationServer:source.contoso.com -FileName "C:\RgsExportSource.zip" -RemoveExportedConfiguration

3.  <span data-ttu-id="98d59-p103">Importe os grupos de resposta para o pool de destino e atribua o pool de destino como o novo proprietário. Na linha de comando, digite:</span><span class="sxs-lookup"><span data-stu-id="98d59-p103">Import the response groups to the destination pool and assign the destination pool as the new owner. At the command line, type:</span></span>
    
        Import-CsRgsConfiguration -Destination "service:ApplicationServer:<destination pool>" -FileName "<export file name>" -OverwriteOwner
    
    <span data-ttu-id="98d59-116">Se você também quiser copiar as configurações de nível de aplicativo do grupo de resposta do pool de origem para o pool de destino, inclua o parâmetro – ReplaceExistingRgsSettings.</span><span class="sxs-lookup"><span data-stu-id="98d59-116">If you also want to copy the Response Group application-level settings from the source pool to the destination pool, include the –ReplaceExistingRgsSettings parameter.</span></span> <span data-ttu-id="98d59-117">É possível definir apenas um conjunto de configurações a nível de aplicativo por pool.</span><span class="sxs-lookup"><span data-stu-id="98d59-117">You can define only one set of application-level settings per pool.</span></span> <span data-ttu-id="98d59-118">Se você copiar as configurações a nível de aplicativo do pool de origem para o pool de destino, as configurações do pool de origem substituem as configurações para o pool de destino.</span><span class="sxs-lookup"><span data-stu-id="98d59-118">If you copy the application-level settings from the source pool to the destination pool, the settings from the source pool replace the settings for the destination pool.</span></span> <span data-ttu-id="98d59-119">Se você não copiar as configurações a nível de aplicativo do pool de origem, as configurações existentes do pool de destino se aplicam aos grupos de resposta importados.</span><span class="sxs-lookup"><span data-stu-id="98d59-119">If you do not copy the application-level settings from the source pool, the existing settings from the destination pool apply to the imported response groups.</span></span>
    
    <span data-ttu-id="98d59-120">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="98d59-120">For example:</span></span>
    
        Import-CsRgsConfiguration -Destination "service:ApplicationServer:destination.contoso.com" -FileName "C:\RgsExportSource.zip" -OverwriteOwner -ReplaceExistingRgsSettings
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="98d59-121">As configurações a nível de aplicativo incluem a configuração de música em espera padrão, o arquivo de áudio de música em espera padrão, o período de espera do agente e a configuração de contexto da chamada.</span><span class="sxs-lookup"><span data-stu-id="98d59-121">Application-level settings include the default music-on-hold configuration, the default music-on-hold audio file, the agent ringback grace period, and the call context configuration.</span></span> <span data-ttu-id="98d59-122">Para exibir estas definições de configuração, execute o cmdlet <STRONG>Get-CsRgsConfiguration</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="98d59-122">To view these configuration settings, run the <STRONG>Get-CsRgsConfiguration</STRONG> cmdlet.</span></span> <span data-ttu-id="98d59-123">Para obter detalhes sobre esse cmdlet, consulte <A href="https://docs.microsoft.com/powershell/module/skype/Get-CsRgsConfiguration">Get-CsRgsConfiguration</A>.</span><span class="sxs-lookup"><span data-stu-id="98d59-123">For details about this cmdlet, see <A href="https://docs.microsoft.com/powershell/module/skype/Get-CsRgsConfiguration">Get-CsRgsConfiguration</A>.</span></span>

    
    </div>

4.  <span data-ttu-id="98d59-124">Verifique se a importação teve êxito ao exibir a configuração do grupo de resposta importado fazendo o seguinte:</span><span class="sxs-lookup"><span data-stu-id="98d59-124">Verify that the import was successful by displaying the imported response group configuration by doing the following:</span></span>
    
      - <span data-ttu-id="98d59-p106">Verifique se todos os fluxos de trabalho foram importados. Na linha de comando, digite o seguinte:</span><span class="sxs-lookup"><span data-stu-id="98d59-p106">Verify that all the workflows were imported. At the command line, type the following:</span></span>
        
            Get-CsRgsWorkflow -Identity "service:ApplicationServer:<destination pool FQDN>"
    
      - <span data-ttu-id="98d59-p107">Verifique se todas as filas foram importadas. Na linha de comando, digite o seguinte:</span><span class="sxs-lookup"><span data-stu-id="98d59-p107">Verify that all the queues were imported. At the command line, type the following:</span></span>
        
            Get-CsRgsQueue -Identity "service:ApplicationServer:<destination pool FQDN>"
    
      - <span data-ttu-id="98d59-p108">Verifique se todos os grupos de agente foram importados. Na linha de comando, digite o seguinte:</span><span class="sxs-lookup"><span data-stu-id="98d59-p108">Verify that all the agent groups were imported. At the command line, type the following:</span></span>
        
            Get-CsRgsAgentGroup -Identity "service:ApplicationServer:<destination pool FQDN>"
    
      - <span data-ttu-id="98d59-p109">Verifique se todas as horas comerciais foram importadas. Na linha de comando, digite o seguinte:</span><span class="sxs-lookup"><span data-stu-id="98d59-p109">Verify that all the hours of business were imported. At the command line, type the following:</span></span>
        
            Get-CsRgsHoursOfBusiness -Identity "service:ApplicationServer:<destination pool FQDN>" 
    
      - <span data-ttu-id="98d59-p110">Verifique se todos os conjuntos de feriados foram importados. Na linha de comando, digite o seguinte:</span><span class="sxs-lookup"><span data-stu-id="98d59-p110">Verify that all the holiday sets were imported. At the command line, type the following:</span></span>
        
            Get-CsRgsHolidaySet -Identity "service:ApplicationServer:<destination pool FQDN>" 

5.  <span data-ttu-id="98d59-135">Verifique se a importação teve êxito ao realizar uma chamada para um dos grupos de resposta e verificando se a chamada foi tratada corretamente.</span><span class="sxs-lookup"><span data-stu-id="98d59-135">Verify that the import was successful by placing a call to one of the response groups and verifying that the call is handled correctly.</span></span>

6.  <span data-ttu-id="98d59-136">Agentes de solicitação membros de grupos de agente formais para se conectar em seus grupos de agentes no pool de destino.</span><span class="sxs-lookup"><span data-stu-id="98d59-136">Request agents who are members of formal agent groups to sign in to their agent groups in the destination pool.</span></span>

7.  <span data-ttu-id="98d59-p111">Se você não removeu anteriormente grupos de resposta do pool de origem, remova os grupos de resposta do pool de origem. Na linha de comando, digite:</span><span class="sxs-lookup"><span data-stu-id="98d59-p111">If you did not previously remove response groups from the source pool, remove the response groups from the source pool. At the command line, type:</span></span>
    
        Export-CsRgsConfiguration -Source "service:ApplicationServer:<source pool FQDN> -RemoveExportedConfiguration -FileName "<temporary export file name>"
    
    <span data-ttu-id="98d59-139">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="98d59-139">For example:</span></span>
    
        Export-CsRgsConfiguration -Source "service:ApplicationServer:source.contoso.com" -RemoveExportedConfiguration -FileName "C:\TempRGsConfiguration.zip"

</div>

</div>

<span> </span>

</div>

</div>

</div>

