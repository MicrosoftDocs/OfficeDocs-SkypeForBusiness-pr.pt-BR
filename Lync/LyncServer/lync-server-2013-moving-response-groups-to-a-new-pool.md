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
ms.openlocfilehash: 96740d8937f1548952d41d5674ef3e66cd29e2b6
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41756705"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="moving-response-groups-to-a-new-pool-in-lync-server-2013"></a><span data-ttu-id="d1968-102">Movendo grupos de resposta para um novo pool no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d1968-102">Moving response groups to a new pool in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d1968-103">_**Tópico da última modificação:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="d1968-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="d1968-104">O Lync Server 2013 introduz novo cmdlet support para mover grupos de resposta de um pool para outro pool, mesmo quando o FQDN (nome de domínio totalmente qualificado) for diferente.</span><span class="sxs-lookup"><span data-stu-id="d1968-104">Lync Server 2013 introduces new cmdlet support for moving response groups from one pool to another pool, even when the fully qualified domain name (FQDN) is different.</span></span>

<span data-ttu-id="d1968-105">Use as etapas do procedimento a seguir para mover grupos de resposta de um pool de front-ends para outro pool de front-end com um FQDN diferente.</span><span class="sxs-lookup"><span data-stu-id="d1968-105">Use the steps in the following procedure to move response groups from one Front End pool to another Front End pool with a different FQDN.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="d1968-106">Em um ambiente de coexistência, você pode mover grupos de resposta somente entre os&nbsp;pools de front-end do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="d1968-106">In a coexistence environment, you can move response groups only between Lync Server 2013&nbsp;Front End pools.</span></span>



</div>

<div>

## <a name="to-move-response-groups-to-a-pool-with-a-different-fqdn"></a><span data-ttu-id="d1968-107">Para mover grupos de resposta para um pool com um FQDN diferente</span><span class="sxs-lookup"><span data-stu-id="d1968-107">To move response groups to a pool with a different FQDN</span></span>

1.  <span data-ttu-id="d1968-108">Inicie o Shell de gerenciamento do Lync Server: clique em **Iniciar**, em **todos os programas**, em **Microsoft Lync Server 2013**e, em seguida, clique em **Shell de gerenciamento do Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="d1968-108">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="d1968-109">Exporte os grupos de resposta no pool de origem.</span><span class="sxs-lookup"><span data-stu-id="d1968-109">Export the response groups in the source pool.</span></span> <span data-ttu-id="d1968-110">Na linha de comando, digite:</span><span class="sxs-lookup"><span data-stu-id="d1968-110">At the command line, type:</span></span>
    
        Export-CsRgsConfiguration -Source "service:ApplicationServer:<source FQDN>" -FileName "<export file name>"
    
    <span data-ttu-id="d1968-111">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="d1968-111">For example:</span></span>
    
        Export-CsRgsConfiguration -Source "service:ApplicationServer:source.contoso.com" -FileName "C:\RgsExportSource.zip"
    
    <span data-ttu-id="d1968-112">Para remover os grupos de resposta do pool de origem durante a exportação, inclua o parâmetro – RemoveExportedConfiguration.</span><span class="sxs-lookup"><span data-stu-id="d1968-112">To remove the response groups from the source pool during the export, include the –RemoveExportedConfiguration parameter.</span></span> <span data-ttu-id="d1968-113">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="d1968-113">For example:</span></span>
    
        Export-CsRgsConfiguration -Source ApplicationServer:source.contoso.com -FileName "C:\RgsExportSource.zip" -RemoveExportedConfiguration

3.  <span data-ttu-id="d1968-114">Importe os grupos de resposta para o pool de destino e atribua o pool de destino como o novo proprietário.</span><span class="sxs-lookup"><span data-stu-id="d1968-114">Import the response groups to the destination pool and assign the destination pool as the new owner.</span></span> <span data-ttu-id="d1968-115">Na linha de comando, digite:</span><span class="sxs-lookup"><span data-stu-id="d1968-115">At the command line, type:</span></span>
    
        Import-CsRgsConfiguration -Destination "service:ApplicationServer:<destination pool>" -FileName "<export file name>" -OverwriteOwner
    
    <span data-ttu-id="d1968-116">Se você também quiser copiar as configurações de nível de aplicativo do grupo de resposta do pool de origem para o pool de destino, inclua o parâmetro – ReplaceExistingRgsSettings.</span><span class="sxs-lookup"><span data-stu-id="d1968-116">If you also want to copy the Response Group application-level settings from the source pool to the destination pool, include the –ReplaceExistingRgsSettings parameter.</span></span> <span data-ttu-id="d1968-117">Você pode definir apenas um conjunto de configurações do aplicativo por pool.</span><span class="sxs-lookup"><span data-stu-id="d1968-117">You can define only one set of application-level settings per pool.</span></span> <span data-ttu-id="d1968-118">Se você copiar as configurações no nível do aplicativo do pool de origem para o pool de destino, as configurações do pool de origem substituirão as configurações do pool de destino.</span><span class="sxs-lookup"><span data-stu-id="d1968-118">If you copy the application-level settings from the source pool to the destination pool, the settings from the source pool replace the settings for the destination pool.</span></span> <span data-ttu-id="d1968-119">Se você não copiar as configurações no nível do aplicativo a partir do pool de origem, as configurações existentes do pool de destino serão aplicadas aos grupos de resposta importados.</span><span class="sxs-lookup"><span data-stu-id="d1968-119">If you do not copy the application-level settings from the source pool, the existing settings from the destination pool apply to the imported response groups.</span></span>
    
    <span data-ttu-id="d1968-120">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="d1968-120">For example:</span></span>
    
        Import-CsRgsConfiguration -Destination "service:ApplicationServer:destination.contoso.com" -FileName "C:\RgsExportSource.zip" -OverwriteOwner -ReplaceExistingRgsSettings
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="d1968-121">As configurações de nível de aplicativo incluem a configuração de música em espera padrão, o arquivo de áudio de música em espera padrão, o período de cortesia do agente e a configuração do contexto de chamada.</span><span class="sxs-lookup"><span data-stu-id="d1968-121">Application-level settings include the default music-on-hold configuration, the default music-on-hold audio file, the agent ringback grace period, and the call context configuration.</span></span> <span data-ttu-id="d1968-122">Para exibir essas definições de configuração, execute o cmdlet <STRONG>Get-CsRgsConfiguration</STRONG> .</span><span class="sxs-lookup"><span data-stu-id="d1968-122">To view these configuration settings, run the <STRONG>Get-CsRgsConfiguration</STRONG> cmdlet.</span></span> <span data-ttu-id="d1968-123">Para obter detalhes sobre esse cmdlet, confira <A href="https://docs.microsoft.com/powershell/module/skype/Get-CsRgsConfiguration">Get-CsRgsConfiguration</A>.</span><span class="sxs-lookup"><span data-stu-id="d1968-123">For details about this cmdlet, see <A href="https://docs.microsoft.com/powershell/module/skype/Get-CsRgsConfiguration">Get-CsRgsConfiguration</A>.</span></span>

    
    </div>

4.  <span data-ttu-id="d1968-124">Verifique se a importação foi bem-sucedida exibindo a configuração do grupo de resposta importado fazendo o seguinte:</span><span class="sxs-lookup"><span data-stu-id="d1968-124">Verify that the import was successful by displaying the imported response group configuration by doing the following:</span></span>
    
      - <span data-ttu-id="d1968-125">Verifique se todos os fluxos de trabalho foram importados.</span><span class="sxs-lookup"><span data-stu-id="d1968-125">Verify that all the workflows were imported.</span></span> <span data-ttu-id="d1968-126">Na linha de comando, digite o seguinte:</span><span class="sxs-lookup"><span data-stu-id="d1968-126">At the command line, type the following:</span></span>
        
            Get-CsRgsWorkflow -Identity "service:ApplicationServer:<destination pool FQDN>"
    
      - <span data-ttu-id="d1968-127">Verifique se todas as filas foram importadas.</span><span class="sxs-lookup"><span data-stu-id="d1968-127">Verify that all the queues were imported.</span></span> <span data-ttu-id="d1968-128">Na linha de comando, digite o seguinte:</span><span class="sxs-lookup"><span data-stu-id="d1968-128">At the command line, type the following:</span></span>
        
            Get-CsRgsQueue -Identity "service:ApplicationServer:<destination pool FQDN>"
    
      - <span data-ttu-id="d1968-129">Verifique se todos os grupos de agente foram importados.</span><span class="sxs-lookup"><span data-stu-id="d1968-129">Verify that all the agent groups were imported.</span></span> <span data-ttu-id="d1968-130">Na linha de comando, digite o seguinte:</span><span class="sxs-lookup"><span data-stu-id="d1968-130">At the command line, type the following:</span></span>
        
            Get-CsRgsAgentGroup -Identity "service:ApplicationServer:<destination pool FQDN>"
    
      - <span data-ttu-id="d1968-131">Verifique se todas as horas de negócios foram importadas.</span><span class="sxs-lookup"><span data-stu-id="d1968-131">Verify that all the hours of business were imported.</span></span> <span data-ttu-id="d1968-132">Na linha de comando, digite o seguinte:</span><span class="sxs-lookup"><span data-stu-id="d1968-132">At the command line, type the following:</span></span>
        
            Get-CsRgsHoursOfBusiness -Identity "service:ApplicationServer:<destination pool FQDN>" 
    
      - <span data-ttu-id="d1968-133">Verifique se todos os conjuntos de feriados foram importados.</span><span class="sxs-lookup"><span data-stu-id="d1968-133">Verify that all the holiday sets were imported.</span></span> <span data-ttu-id="d1968-134">Na linha de comando, digite o seguinte:</span><span class="sxs-lookup"><span data-stu-id="d1968-134">At the command line, type the following:</span></span>
        
            Get-CsRgsHolidaySet -Identity "service:ApplicationServer:<destination pool FQDN>" 

5.  <span data-ttu-id="d1968-135">Verifique se a importação foi bem-sucedida fazendo uma chamada para um dos grupos de resposta e verificando se a chamada foi manipulada corretamente.</span><span class="sxs-lookup"><span data-stu-id="d1968-135">Verify that the import was successful by placing a call to one of the response groups and verifying that the call is handled correctly.</span></span>

6.  <span data-ttu-id="d1968-136">Solicite aos agentes que são membros de grupos de agentes formais para entrar em seus grupos de agente no pool de destino.</span><span class="sxs-lookup"><span data-stu-id="d1968-136">Request agents who are members of formal agent groups to sign in to their agent groups in the destination pool.</span></span>

7.  <span data-ttu-id="d1968-137">Se você não removeu anteriormente grupos de resposta do pool de origem, remova os grupos de resposta do pool de origem.</span><span class="sxs-lookup"><span data-stu-id="d1968-137">If you did not previously remove response groups from the source pool, remove the response groups from the source pool.</span></span> <span data-ttu-id="d1968-138">Na linha de comando, digite:</span><span class="sxs-lookup"><span data-stu-id="d1968-138">At the command line, type:</span></span>
    
        Export-CsRgsConfiguration -Source "service:ApplicationServer:<source pool FQDN> -RemoveExportedConfiguration -FileName "<temporary export file name>"
    
    <span data-ttu-id="d1968-139">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="d1968-139">For example:</span></span>
    
        Export-CsRgsConfiguration -Source "service:ApplicationServer:source.contoso.com" -RemoveExportedConfiguration -FileName "C:\TempRGsConfiguration.zip"

</div>

</div>

<span> </span>

</div>

</div>

</div>

