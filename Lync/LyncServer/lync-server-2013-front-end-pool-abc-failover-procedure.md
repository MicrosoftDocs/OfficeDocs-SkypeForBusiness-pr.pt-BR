---
title: 'Lync Server 2013: Procedimento de failover ABC do pool Front-End'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Front End pool ABC failover procedure
ms:assetid: 67763ad3-6796-45eb-a486-901f21ac1a95
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945635(v=OCS.15)
ms:contentKeyID: 51541486
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 87b6cb610d153374f6f4c9ba8a3c2798c50b88ad
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34829149"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="front-end-pool-abc-failover-procedure-in-lync-server-2013"></a><span data-ttu-id="e21c0-102">Procedimento de failover ABC do pool Front-End no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e21c0-102">Front End pool ABC failover procedure in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e21c0-103">_**Tópico da última modificação:** 2014-05-22_</span><span class="sxs-lookup"><span data-stu-id="e21c0-103">_**Topic Last Modified:** 2014-05-22_</span></span>

<span data-ttu-id="e21c0-104">Use as etapas a seguir para executar o procedimento de failover do ABC.</span><span class="sxs-lookup"><span data-stu-id="e21c0-104">Use the following steps to perform the ABC failover procedure.</span></span> <span data-ttu-id="e21c0-105">Este procedimento contém uma descrição de alto nível de cada etapa, seguida por comandos e cmdlets a serem executados para cada etapa.</span><span class="sxs-lookup"><span data-stu-id="e21c0-105">This procedure contains a high-level description of each step, followed by commands and cmdlets to be run for each step.</span></span>

<span data-ttu-id="e21c0-106">Para executar os cmdlets, abra um shell de gerenciamento do Lync Server usando executar como administrador.</span><span class="sxs-lookup"><span data-stu-id="e21c0-106">To run the cmdlets, open a Lync Server Management Shell using Run as Administrator.</span></span>

<div>

## <a name="to-perform-an-abc-failover"></a><span data-ttu-id="e21c0-107">Para executar um failover de ABC</span><span class="sxs-lookup"><span data-stu-id="e21c0-107">To Perform an ABC Failover</span></span>

1.  <span data-ttu-id="e21c0-108">Verifique se o pool A é o host do servidor de gerenciamento central (CMS).</span><span class="sxs-lookup"><span data-stu-id="e21c0-108">Check whether the pool A is the host for the Central Management Server (CMS).</span></span>
    
      - <span data-ttu-id="e21c0-109">Execute o seguinte cmdlet:</span><span class="sxs-lookup"><span data-stu-id="e21c0-109">Run the following cmdlet:</span></span>
        
            Get-CsService -CentralManagement
        
        <span data-ttu-id="e21c0-110">Se o campo de identidade do CMS ativo apontar para o nome de domínio totalmente qualificado (FQDN) do pool A, use as etapas 2 e 3 deste procedimento para fazer o failover do servidor de gerenciamento central primeiro.</span><span class="sxs-lookup"><span data-stu-id="e21c0-110">If the Identity field of the active CMS points to the fully qualified domain name (FQDN) of Pool A, then you use steps 2 and 3 of this procedure to fail over the Central Management Server first.</span></span> <span data-ttu-id="e21c0-111">Caso contrário, pule para a etapa 4.</span><span class="sxs-lookup"><span data-stu-id="e21c0-111">Otherwise, skip to step 4.</span></span>

2.  <span data-ttu-id="e21c0-112">Reprovar o CMS para o pool B no modo de recuperação de desastre executando o seguinte cmdlet:</span><span class="sxs-lookup"><span data-stu-id="e21c0-112">Fail over the CMS to Pool B in disaster recovery mode by running the following cmdlet:</span></span>
    
        Invoke-CsManagementServerFailover -BackupSqlServerFqdn <Pool B BE FQDN> -BackupSqlInstanceName <Pool B BE instance name> [-BackupMirrorSqlServerFqdn <Pool B Mirror BE FQDN> -BackupMirrorSqlInstanceName <Pool B Mirror BE Instance name>] -Force -Verbose
    
    <span data-ttu-id="e21c0-113">Depois de fazer isso, recomendamos que você mova o CMS do pool B para outro pool emparelhado existente para obter resiliência extra.</span><span class="sxs-lookup"><span data-stu-id="e21c0-113">After you do this, we recommend that you move the CMS from pool B to another existing paired pool for extra resiliency.</span></span> <span data-ttu-id="e21c0-114">Para obter detalhes, consulte [mover-CsManagementServer](https://docs.microsoft.com/powershell/module/skype/Move-CsManagementServer)..</span><span class="sxs-lookup"><span data-stu-id="e21c0-114">For details, see [Move-CsManagementServer](https://docs.microsoft.com/powershell/module/skype/Move-CsManagementServer)..</span></span>

3.  <span data-ttu-id="e21c0-115">Se o pool A contém CMS, importe a configuração de LIS do pool A para o banco de dados LIS do pool B (LIS. MDF).</span><span class="sxs-lookup"><span data-stu-id="e21c0-115">If Pool A contains CMS, import the LIS configuration from pool A into pool B’s LIS database (Lis.mdf).</span></span> <span data-ttu-id="e21c0-116">Isso só funcionará se você tiver feito backup dos dados do LIS regularmente.</span><span class="sxs-lookup"><span data-stu-id="e21c0-116">This will work only if you have been backing up LIS data on a regular basis.</span></span> <span data-ttu-id="e21c0-117">Para importar a configuração de LIS, execute os seguintes cmdlets:</span><span class="sxs-lookup"><span data-stu-id="e21c0-117">To import the LIS configuration, run the following cmdlets:</span></span>
    
        Import-CsLisConfiguration -FileName <String> 
        Publish-CsLisConfiguration

4.  <span data-ttu-id="e21c0-118">Importar fluxos de trabalho do serviço de grupo de resposta do Lync Server de backup do pool A para o pool B.</span><span class="sxs-lookup"><span data-stu-id="e21c0-118">Import backed-up Lync Server Response Group service workflows from pool A into pool B.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="e21c0-119">Atualmente, o cmdlet <STRONG>Import-CsRgsConfiguration</STRONG> requer que os nomes da fila e do fluxo de trabalho no pool A sejam distintos dos nomes da fila e do fluxo de trabalho no pool B. Se os nomes não forem distintos, você receberá um erro ao executar o cmdlet <STRONG>Import-CsRgsConfiguration</STRONG> , e as filas e os fluxos de trabalho precisarão ser renomeados no pool B antes de prosseguir com o cmdlet <STRONG>Import-CsRgsConfiguration</STRONG> .</span><span class="sxs-lookup"><span data-stu-id="e21c0-119">Currently, the <STRONG>Import-CsRgsConfiguration</STRONG> cmdlet requires that the queue and workflow names on pool A are distinct from the queue and workflow names on pool B. If the names are not distinct, you will get an error when running the <STRONG>Import-CsRgsConfiguration</STRONG> cmdlet, and the queues and workflows will need to be renamed in pool B before proceeding with <STRONG>Import-CsRgsConfiguration</STRONG> cmdlet.</span></span>

    
    </div>
    
    <span data-ttu-id="e21c0-120">Você tem duas opções para importar a configuração do grupo de resposta do pool A para o pool B. Qual opção você usa depende se você deseja substituir as configurações de nível de aplicativo do pool B pelas configurações de nível de aplicativo no pool A.</span><span class="sxs-lookup"><span data-stu-id="e21c0-120">You have two options for importing the Response Group configuration from pool A to pool B. Which option you use depends on whether you want to overwrite the application-level settings of pool B with the application-level settings in pool A.</span></span>
    
      - <span data-ttu-id="e21c0-121">Se você deseja substituir as configurações do pool B, execute o cmdlet **Import-CsRgsConfiguration** com a opção **ReplaceExistingSettings** :</span><span class="sxs-lookup"><span data-stu-id="e21c0-121">If you want to overwrite the Pool B settings, run the **Import-CsRgsConfiguration** cmdlet with the **ReplaceExistingSettings** option:</span></span>
        
            Import-CsRgsConfiguration -Destination "service:ApplicationServer:<Pool B FQDN>" -FileName "C:\RgsExportPrimary.zip"  -ReplaceExistingRgsSettings
    
      - <span data-ttu-id="e21c0-122">Se você não quiser substituir as configurações do pool B, use o cmdlet **Import-CsRgsConfiguration** sem a opção **ReplaceExistingSettings** .</span><span class="sxs-lookup"><span data-stu-id="e21c0-122">If you do not want to overwrite the Pool B settings, use the **Import-CsRgsConfiguration** cmdlet without the **ReplaceExistingSettings** option.</span></span>
        
            Import-CsRgsConfiguration -Destination "service:ApplicationServer:<Pool B FQDN>" -FileName "C:\RgsExportPrimary.zip"
    
    <div>
    

    > [!WARNING]  
    > <span data-ttu-id="e21c0-123">Lembre-se de que se você não quiser substituir as configurações de nível de aplicativo do pool de backup (pool B) pelas configurações do pool primário (pool A), as configurações de nível de aplicativo do pool A serão perdidas se o pool A for perdido, porque o aplicativo do grupo de resposta pode armazenar apenas um conjunto de configurações no nível do aplicativo por pool.</span><span class="sxs-lookup"><span data-stu-id="e21c0-123">Keep in mind that if you do not want to overwrite the application-level settings of the backup pool (pool B) with the settings of the primary pool (pool A), pool A’s application-level settings will be lost if pool A is lost, because the Response Group application can store only one set of application-level settings per pool.</span></span> <span data-ttu-id="e21c0-124">Quando o pool C é implantado para substituir o pool A, as configurações do nível do aplicativo devem ser reconfiguradas, incluindo o arquivo de áudio padrão de música em espera.</span><span class="sxs-lookup"><span data-stu-id="e21c0-124">When pool C is deployed to replace pool A, the application-level settings must be reconfigured, including the default music-on-hold audio file.</span></span>

    
    </div>

5.  <span data-ttu-id="e21c0-125">Verifique se a importação de configuração de grupo de resposta foi bem-sucedida executando os seguintes cmdlets para exibir os grupos de resposta importados.</span><span class="sxs-lookup"><span data-stu-id="e21c0-125">Verify that the Response Group configuration import was successful by running the following cmdlets to display the imported response groups.</span></span> <span data-ttu-id="e21c0-126">Observe que os grupos de resposta importados ainda são pertencentes ao pool A.</span><span class="sxs-lookup"><span data-stu-id="e21c0-126">Note that the imported response groups are still owned by pool A.</span></span>
    
        Get-CsRgsWorkflow -Identity "service:ApplicationServer:<Pool B FQDN>" -Owner "service:ApplicationServer:<Pool A FQDN>"
        
        Get-CsRgsQueue -Identity "service:ApplicationServer:<Pool B FQDN>" -Owner "service:ApplicationServer:<Pool A FQDN>"
        
        Get-CsRgsAgentGroup -Identity "service:ApplicationServer:<Pool B FQDN>" -Owner "service:ApplicationServer:<Pool A FQDN>"

6.  <span data-ttu-id="e21c0-127">Para números não atribuídos, mova os intervalos numéricos não atribuídos que estão usando "Announcement" como o serviço de anúncio selecionado do pool A para o pool B. Para fazer isso:</span><span class="sxs-lookup"><span data-stu-id="e21c0-127">For Unassigned Numbers, move the Unassigned Number ranges that are using "Announcement" as the selected announcement service from pool A to pool B. To do so:</span></span>
    
      - <span data-ttu-id="e21c0-128">Crie novamente todos os comunicados que foram implantados no pool A no pool B. Se algum arquivo de áudio foi usado ao implantar os comunicados no pool A, esses arquivos serão necessários para recriar os comunicados no pool B. Para recriar os comunicados no pool B, use os cmdlets **New-CsAnnouncement** , com o pool B como o serviço pai.</span><span class="sxs-lookup"><span data-stu-id="e21c0-128">Re-create all announcements that were deployed in pool A on pool B. If any audio files were used when deploying the announcements in pool A, these files will be needed to re-create the announcements in pool B. To re-create the announcements in pool B, use the **New-CsAnnouncement** cmdlets, with pool B as the Parent service.</span></span>
    
      - <span data-ttu-id="e21c0-129">Redirecione todos os intervalos de números não atribuídos que estão direcionando um comunicado no pool A para os comunicados recém implantados no pool B. Execute o seguinte cmdlet para cada intervalo de números não atribuído direcionando um anúncio do pool A:</span><span class="sxs-lookup"><span data-stu-id="e21c0-129">Retarget all the Unassigned Number ranges that are targeting an announcement in pool A to the newly deployed announcements in pool B. Run the following cmdlet for every Unassigned Number range targeting an announcement of pool A:</span></span>
        
            Set-CsUnassignedNumber -Identity "<Range Name>" -AnnouncementService "<Pool B FQDN>" -AnnouncementName "<New Announcement in pool B>"
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="e21c0-130">Esta etapa não é necessária para intervalos de números não atribuídos que usam "Exchange UM" como o serviço de anúncio selecionado.</span><span class="sxs-lookup"><span data-stu-id="e21c0-130">This step is not required for unassigned number ranges that use "Exchange UM" as the selected announcement service.</span></span>

    
    </div>

7.  <span data-ttu-id="e21c0-131">Failover do pool A para o pool B no modo de recuperação de desastres (DR), executando o seguinte cmdlet:</span><span class="sxs-lookup"><span data-stu-id="e21c0-131">Fail over Pool A to Pool B in Disaster Recovery (DR) mode, by running the following cmdlet:</span></span>
    
        Invoke-CsPoolFailover -PoolFqdn <Pool A FQDN> -DisasterMode

8.  <span data-ttu-id="e21c0-132">Construa o pool C, mas não inicie serviços no pool C.</span><span class="sxs-lookup"><span data-stu-id="e21c0-132">Build pool C, but do not start any services on pool C.</span></span>
    
    <span data-ttu-id="e21c0-133">Observe que esta etapa pode ser executada simultaneamente com as etapas 5 e 6.</span><span class="sxs-lookup"><span data-stu-id="e21c0-133">Note that this step can be carried out concurrently with steps 5 and 6.</span></span>

9.  <span data-ttu-id="e21c0-134">Forçar usuários hospedados no pool A para mover-se para o pool C executando o seguinte cmdlet:</span><span class="sxs-lookup"><span data-stu-id="e21c0-134">Force users homed on pool A to move to pool C by running the following cmdlet:</span></span>
    
        Get-csuser -Filter {RegistrarPool -eq "<Pool A FQDN>"} | Move-CsUser -Target <Pool C FQDN> -Force
    
    <span data-ttu-id="e21c0-135">Nesse momento, os usuários hospedados no pool A começarão a sofrer uma falha de serviço.</span><span class="sxs-lookup"><span data-stu-id="e21c0-135">At this point, users homed on pool A will begin to experience a service outage.</span></span> <span data-ttu-id="e21c0-136">Essa interrupção continuará até a etapa 16, em que os serviços de ponto são iniciados no pool C.</span><span class="sxs-lookup"><span data-stu-id="e21c0-136">This outage will continue until step 16, at which point services are started on pool C.</span></span>

10. <span data-ttu-id="e21c0-137">Force o diretório de conferência do pool A para mover-se para o pool C executando o seguinte cmdlet:</span><span class="sxs-lookup"><span data-stu-id="e21c0-137">Force the conference directory of pool A to move to pool C by running the following cmdlet:</span></span>
    
        Move-CsConferenceDirectory -Identity <Conference Directory ID of Pool A> -TargetPool <Pool C FQDN> -Force

11. <span data-ttu-id="e21c0-138">Force o objeto de contato do atendedor automático da conferência (CAA) para mover do pool A para o pool C executando o seguinte cmdlet:</span><span class="sxs-lookup"><span data-stu-id="e21c0-138">Force the Conference Auto Attendant (CAA) Contact Object to move from pool A to pool C by running the following cmdlet:</span></span>
    
        Move-csApplicationEndpoint -Identity "<Pool A CAA Uri>" -targetApplicationPool <Pool C FQDN> -force

12. <span data-ttu-id="e21c0-139">Copie o conteúdo da conferência do pool B para o pool C.</span><span class="sxs-lookup"><span data-stu-id="e21c0-139">Copy conference content from pool B to pool C.</span></span>

13. <span data-ttu-id="e21c0-140">Exportar dados do usuário do pool B e importar os dados do usuário para o pool C executando os seguintes cmdlets:</span><span class="sxs-lookup"><span data-stu-id="e21c0-140">Export user data from pool B and import the user data into pool C by running the following cmdlets:</span></span>
    
        Export-CsUserData -PoolFqdn <Pool B Fqdn> -FileName <String>
        Import-CsUserData -PoolFqdn <Pool C Fqdn> -FileName <String>

14. <span data-ttu-id="e21c0-141">Restaurar os dados de aplicativo de estacionamento de chamada com backup do pool A no pool C e atribuir os intervalos de estacionamento de chamada do pool A ao pool C.</span><span class="sxs-lookup"><span data-stu-id="e21c0-141">Restore backed-up Call Park application data from pool A into pool C and assign the Call Park orbit ranges of pool A to pool C.</span></span>
    
      - <span data-ttu-id="e21c0-142">Você pode reatribuir um intervalo de linha de estacionamento de chamada do pool a ao pool C por meio do painel de controle do Lync Server ou do Shell de gerenciamento do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="e21c0-142">You can reassign a Call Park orbit range of pool A to pool C either through the Lync Server Control Panel or the Lync Server Management Shell.</span></span> <span data-ttu-id="e21c0-143">Para o Shell de gerenciamento do Lync Server, execute o seguinte cmdlet para cada intervalo de órbita de linha de chamada atribuído ao pool A (Observe que o parâmetro Identity refere-se à faixa de opções de estacionamento em barra de chamada que pertence ao pool A):</span><span class="sxs-lookup"><span data-stu-id="e21c0-143">For the Lync Server Management Shell, run the following cmdlet for every Call Park orbit range assigned to pool A (note that the Identity parameter refers to the Call Park Orbit Ranges that belong to pool A):</span></span>
        
            Set-CsCallParkOrbit -Identity "<Call Park Orbit Identity>" -CallParkService "service:ApplicationServer:<Pool C FQDN>"
    
      - <span data-ttu-id="e21c0-144">Se uma música em espera personalizada tiver sido configurada para estacionamento de chamadas no pool A, restaure o arquivo de música em espera personalizado do parque de chamadas no pool C.</span><span class="sxs-lookup"><span data-stu-id="e21c0-144">If a customized music-on-hold has been configured for Call Park in pool A, restore the Call Park customized music-on-hold file in pool C.</span></span>
        
            Xcopy <Source> <Destination: Pool C CPS File Store Path>
        
        <span data-ttu-id="e21c0-145">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="e21c0-145">For example:</span></span>
        
            Xcopy "Source Path" "<Pool C File Store Path>\OcsFileStore\coX-ApplicationServer-X\AppServerFiles\CPS\"
    
      - <span data-ttu-id="e21c0-146">Por fim, redefina as configurações do estacionamento de chamadas no pool C usando o cmdlet **set-CsCpsConfiguration** .</span><span class="sxs-lookup"><span data-stu-id="e21c0-146">Finally, reconfigure the Call Park settings on pool C by using the **Set-CsCpsConfiguration** cmdlet.</span></span> <span data-ttu-id="e21c0-147">O aplicativo de estacionamento de chamadas pode armazenar apenas um conjunto de configurações e um arquivo de áudio de música em espera personalizado por pool, e essas configurações não são comparadas nem preservadas no caso de um desastre.</span><span class="sxs-lookup"><span data-stu-id="e21c0-147">The Call Park application can store only one set of settings and one customized music-on-hold audio file per pool, and these settings are not backed up or preserved in the event of a disaster.</span></span>

15. <span data-ttu-id="e21c0-148">Se o próximo pool de saltos para chats persistentes estiver apontando para o pool A, faça e publique alterações de topologia para que o servidor de salto seguinte aponte para o pool C.</span><span class="sxs-lookup"><span data-stu-id="e21c0-148">If the next hop pool for Persistent Chat is pointing to pool A, make and publish topology changes so that the next hop server points to pool C.</span></span>
    
      - <span data-ttu-id="e21c0-149">Em Construtor de topologia, altere o pool de chat persistente para apontar para o pool C como o próximo salto.</span><span class="sxs-lookup"><span data-stu-id="e21c0-149">In Topology Builder, change the Persistent Chat pool to point to Pool C as its next hop.</span></span> <span data-ttu-id="e21c0-150">Para fazer isso, clique com o botão direito do mouse no pool de chat persistente e, em seguida, clique na guia **geral** e digite o nome do pool C no **próximo pool de saltos**.</span><span class="sxs-lookup"><span data-stu-id="e21c0-150">To do so, right-click on the Persistent Chat pool, then click the **General** tab, and then type the name of Pool C in **Next Hop Pool**.</span></span>
    
      - <span data-ttu-id="e21c0-151">Inicie os serviços no pool C executando o seguinte cmdlet:</span><span class="sxs-lookup"><span data-stu-id="e21c0-151">Start services on pool C by running the following cmdlet:</span></span>
        
            Start-csWindowsService
    
    <span data-ttu-id="e21c0-152">Nesse ponto, a interrupção do serviço termina para os usuários hospedados originalmente no pool A.</span><span class="sxs-lookup"><span data-stu-id="e21c0-152">At this point, the service outage ends for users originally homed on pool A.</span></span>

16. <span data-ttu-id="e21c0-153">Exportar fluxos de trabalho do serviço de grupo de resposta do Lync Server do pool B pertencentes ao pool A para importação no pool C executando o seguinte cmdlet:</span><span class="sxs-lookup"><span data-stu-id="e21c0-153">Export Lync Server Response Group service workflows from pool B owned by pool A for import into pool C by running the following cmdlet:</span></span>
    
        Export-CsRgsConfiguration -Source "service:ApplicationServer:<Pool B FQDN>" -Owner "service:ApplicationServer:<Pool A FQDN>" -FileName "C:\RgsExportPrimaryUpdated.zip" 

17. <span data-ttu-id="e21c0-154">Importar fluxos de trabalho do serviço de grupo de resposta do Lync Server para o pool C do pool B.</span><span class="sxs-lookup"><span data-stu-id="e21c0-154">Import Lync Server Response Group service workflows into pool C from pool B.</span></span>
    
    <span data-ttu-id="e21c0-155">Você tem duas opções para importar a configuração do grupo de resposta do pool B para o pool C. Qual opção você usa depende se você deseja substituir as configurações de nível de aplicativo do pool C pelas configurações de nível de aplicativo no pool B.</span><span class="sxs-lookup"><span data-stu-id="e21c0-155">You have two options are for importing the Response Group configuration from pool B to pool C. Which option you use depends on whether you want to overwrite the application-level settings of pool C with the application-level settings in pool B.</span></span>
    
      - <span data-ttu-id="e21c0-156">Se você quiser substituir as configurações de grupo C, execute o cmdlet **Import-CsRgsConfiguration** com a opção **ReplaceExistingSettings** :</span><span class="sxs-lookup"><span data-stu-id="e21c0-156">If you want to overwrite the Pool C settings, run the **Import-CsRgsConfiguration** cmdlet with the **ReplaceExistingSettings** option:</span></span>
        
            Import-CsRgsConfiguration -Destination "service:ApplicationServer:<Pool C FQDN>" -FileName "C:\RgsExportPrimary.zip"  -ReplaceExistingRgsSettings
    
      - <span data-ttu-id="e21c0-157">Se você não quiser substituir as configurações de grupo C, use o cmdlet **Import-CsRgsConfiguration** sem a opção **ReplaceExistingSettings** .</span><span class="sxs-lookup"><span data-stu-id="e21c0-157">If you do not want to overwrite the Pool C settings, use the **Import-CsRgsConfiguration** cmdlet without the **ReplaceExistingSettings** option.</span></span>
        
            Import-CsRgsConfiguration -Destination "service:ApplicationServer:<Pool B FQDN>" -FileName "C:\RgsExportPrimary.zip"
    
    <div>
    

    > [!WARNING]  
    > <span data-ttu-id="e21c0-158">Lembre-se de que se você não quiser substituir as configurações de nível de aplicativo do pool C pelas configurações do pool de backup (pool B), as configurações de aplicativo do pool B serão perdidas porque o aplicativo do grupo de resposta pode armazenar apenas um conjunto de nível de aplicativo configurações por pool.</span><span class="sxs-lookup"><span data-stu-id="e21c0-158">Keep in mind that if you do not want to overwrite the application-level settings of Pool C with the settings of the backup pool (pool B), pool B’s application-level settings will be lost because the Response Group application can store only one set of application-level settings per pool.</span></span>

    
    </div>

18. <span data-ttu-id="e21c0-159">Verifique se a importação de configuração de grupo de resposta foi bem-sucedida executando os seguintes cmdlets para exibir os grupos de resposta que foram importados para o pool C.</span><span class="sxs-lookup"><span data-stu-id="e21c0-159">Verify that the Response Group configuration import was successful by running the following cmdlets to display the response groups that have been imported to Pool C.</span></span>
    
        Get-CsRgsWorkflow -Identity "service:ApplicationServer:<Pool C FQDN>" -ShowAll
         Get-CsRgsQueue -Identity "service:ApplicationServer:<Pool C FQDN>" -ShowAll
        Get-CsRgsAgentGroup -Identity "service:ApplicationServer:<Pool C FQDN>" -ShowAll

19. <span data-ttu-id="e21c0-160">Quando a configuração importada tiver sido verificada no pool C, remova os grupos de resposta pertencentes ao pool primário do pool B. Isso minimiza o tempo de inatividade dos grupos de resposta.</span><span class="sxs-lookup"><span data-stu-id="e21c0-160">When the imported configuration has been verified in pool C, remove the response groups owned by the primary pool from pool B. This will minimize the downtime of the response groups.</span></span>
    
    <span data-ttu-id="e21c0-161">Esta etapa cria um novo arquivo com a configuração exportada e, em seguida, remove o arquivo do pool B.</span><span class="sxs-lookup"><span data-stu-id="e21c0-161">This step creates a new file with the exported configuration, and then removes the file from pool B.</span></span>
    
        Export-CsRgsConfiguration -Source "service:ApplicationServer:<Pool B FQDN>" -Owner "service:ApplicationServer:<Pool A FQDN>" -FileName "C:\RgsExportPrimaryUpdated.zip" -RemoveExportedConfiguration

20. <span data-ttu-id="e21c0-162">Mover para o pool C os intervalos de números não atribuídos que foram movidos do pool A para o pool B.</span><span class="sxs-lookup"><span data-stu-id="e21c0-162">Move to pool C the Unassigned Number ranges that were moved from pool A to pool B.</span></span>
    
      - <span data-ttu-id="e21c0-163">Recrie no pool C todos os anúncios que foram recriados do pool A no pool B. Se você tiver usado arquivos de áudio ao implantar os comunicados a serem movidos, será necessário usar esses arquivos para recriar os comunicados no pool C. Para recriar os comunicados no pool C, use os cmdlets **New-CsAnnouncement** , com o pool C como o serviço pai.</span><span class="sxs-lookup"><span data-stu-id="e21c0-163">Re-create in pool C all announcements that were re-created from pool A in pool B. If any audio files were used when deploying the announcements to be moved, you will need to use these files to re-create the announcements in pool C. To re-create the announcements in pool C, use the **New-CsAnnouncement** cmdlets, with pool C as the Parent service.</span></span>
    
      - <span data-ttu-id="e21c0-164">Redirecionar para o pool C todos os intervalos de números não atribuídos que foram redirecionados do pool A para o pool B. Execute o cmdlet a seguir para cada intervalo de números não atribuído que precisa ser redirecionado:</span><span class="sxs-lookup"><span data-stu-id="e21c0-164">Retarget to pool C all the unassigned number ranges that were retargeted from pool A to pool B. Run the following cmdlet for every Unassigned Number range that needs to be retargeted:</span></span>
        
            Set-CsUnassignedNumber -Identity "<Range Name>" -AnnouncementService "<Pool C FQDN>" -AnnouncementName "<New Announcement in pool C>"
    
      - <span data-ttu-id="e21c0-165">Adicionais Remover do pool B os comunicados que foram criados novamente no pool C se não estiverem mais em uso no pool B. Para remover anúncios, use o cmdlet **Remove-CsAnnouncement** .</span><span class="sxs-lookup"><span data-stu-id="e21c0-165">(Optional) Remove from pool B the announcements that were re-created in pool C if they are no longer in use in pool B. To remove announcements, use the **Remove-CsAnnouncement** cmdlet.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="e21c0-166">Esta etapa não é necessária para intervalos de números não atribuídos que usam "Exchange UM" como o serviço de anúncio.</span><span class="sxs-lookup"><span data-stu-id="e21c0-166">This step is not required for unassigned number ranges that use "Exchange UM" as the announcement service.</span></span>

        
        </div>

21. <span data-ttu-id="e21c0-167">Limpe os dados de usuário do pool A no pool B executando o seguinte cmdlet:</span><span class="sxs-lookup"><span data-stu-id="e21c0-167">Clean up user data of pool A in pool B by running the following cmdlet:</span></span>
    
        Remove-CsUserStoreBackupData -PoolFqdn <Pool B FQDN> -Verbose

22. <span data-ttu-id="e21c0-168">Faça o seguinte no construtor de topologias:</span><span class="sxs-lookup"><span data-stu-id="e21c0-168">Do the following in Topology Builder:</span></span>
    
      - <span data-ttu-id="e21c0-169">Desemparelhar o pool A e o pool B. pool de par B e pool C. Em seguida, remova o pool A da topologia e publique-o.</span><span class="sxs-lookup"><span data-stu-id="e21c0-169">Unpair pool A and pool B. Pair pool B and pool C. Then remove Pool A from the topology and publish it.</span></span> <span data-ttu-id="e21c0-170">Para fazer isso:</span><span class="sxs-lookup"><span data-stu-id="e21c0-170">To do so:</span></span>
        
          - <span data-ttu-id="e21c0-171">No construtor de topologias, clique com o botão direito do mouse no pool B e, em seguida, clique em **Editar propriedades**.</span><span class="sxs-lookup"><span data-stu-id="e21c0-171">In Topology Builder, right-click on Pool B, and then click **Edit Properties**.</span></span>
        
          - <span data-ttu-id="e21c0-172">Clique em **resiliência** no painel esquerdo.</span><span class="sxs-lookup"><span data-stu-id="e21c0-172">Click **Resiliency** in the left pane.</span></span>
        
          - <span data-ttu-id="e21c0-173">Na caixa abaixo de **pool de backup associado**, selecione pool C. Observe que a caixa de seleção do pool de backup associado inicialmente exibirá o pool A porque o pool B estava anteriormente associado a esse pool.</span><span class="sxs-lookup"><span data-stu-id="e21c0-173">In the box below **Associated Backup Pool**, select Pool C. Note that the Associated Backup Pool selection box will initially display pool A, because pool B was previously associated with this pool.</span></span>
        
          - <span data-ttu-id="e21c0-174">Selecione **Failback e failover automático para Voz** e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="e21c0-174">Select **Automatic failover and failback for Voice**, and then click **OK**.</span></span>
            
            <span data-ttu-id="e21c0-175">Quando você exibir os detalhes sobre este pool, o pool associado agora aparecerá no painel direito em **Resiliência**. </span><span class="sxs-lookup"><span data-stu-id="e21c0-175">When you view the details about this pool, the associated pool now appears in the right pane under **Resiliency**.</span></span>
        
          - <span data-ttu-id="e21c0-176">Na árvore do console, clique com o botão direito do mouse em pool A e, em seguida, clique em excluir.</span><span class="sxs-lookup"><span data-stu-id="e21c0-176">In the console tree, right-click pool A, and then click Delete.</span></span>
        
          - <span data-ttu-id="e21c0-177">Publique a topologia.</span><span class="sxs-lookup"><span data-stu-id="e21c0-177">Publish the topology.</span></span>

23. <span data-ttu-id="e21c0-178">Execute o aplicativo de inicialização no pool C para instalar o aplicativo de serviço de backup e, em seguida, inicie o aplicativo de serviço de backup executando o seguinte na pasta de implantação em um computador local no pool C:</span><span class="sxs-lookup"><span data-stu-id="e21c0-178">Run the bootstrapping application on pool C to install the backup service application, and then start the backup service application by running the following from the deployment folder on a local machine in pool C:</span></span>
    
        Run "%SYSTEMROOT%\Program Files\Microsoft Lync Server 2013\Deployment\Bootstrapper.exe"
        Start-CsWindowsService -name LyncBackup

24. <span data-ttu-id="e21c0-179">Reinicie o aplicativo de serviço de backup no pool B executando os seguintes cmdlets:</span><span class="sxs-lookup"><span data-stu-id="e21c0-179">Restart the backup service application on pool B by running the following cmdlets:</span></span>
    
        Stop-CsWindowsService -name LyncBackup
        Start-CsWindowsService -name LyncBackup

25. <span data-ttu-id="e21c0-180">Se o pool C for um pool padrão da edição (SE) e o pool B tiver o CMS, instale o banco de dados CMS manualmente no pool C executando o seguinte cmdlet:</span><span class="sxs-lookup"><span data-stu-id="e21c0-180">If pool C is a Standard Edition (SE) Pool and pool B has CMS, install the CMS database manually on pool C by running the following cmdlet:</span></span>
    
        Install-CsDatabase -CentralManagementDatabase -SqlServerFqdn <Pool C FQDN> -SqlInstanceName rtc

26. <span data-ttu-id="e21c0-181">Chame o serviço de backup para sincronizar o conteúdo de conferência antigo do pool B para o pool C que foi gerado antes de emparelhar B e C juntos e sincronizar o novo conteúdo de conferência do pool C com o pool B que foi gerado após iniciar o pool C e antes de B e C terem sido emparelhados juntos.</span><span class="sxs-lookup"><span data-stu-id="e21c0-181">Invoke the backup service to sync old conferencing content from pool B to pool C that was generated before pairing B and C together, and to sync new conferencing content from pool C to pool B that was generated after starting pool C and before B and C were paired together.</span></span> <span data-ttu-id="e21c0-182">Para fazer isso, execute os seguintes cmdlets:</span><span class="sxs-lookup"><span data-stu-id="e21c0-182">To do so, run the following cmdlets:</span></span>
    
        Invoke-CsBackupServiceSync -PoolFqdn <Pool C FQDN>
        Invoke-CsBackupServiceSync -PoolFqdn <Pool B FQDN>

27. <span data-ttu-id="e21c0-183">Para cada aparelho de ramificação sobreviventes X associado ao pool A:</span><span class="sxs-lookup"><span data-stu-id="e21c0-183">For each Survivable Branch Appliance X associated with pool A:</span></span>
    
      - <span data-ttu-id="e21c0-184">Desligue SBA X executando o seguinte cmdlet:</span><span class="sxs-lookup"><span data-stu-id="e21c0-184">Shut down SBA X by running the following cmdlet:</span></span>
        
            Stop-CsWindowsService
    
      - <span data-ttu-id="e21c0-185">Crie um arquivo que contenha uma lista de usuários hospedados no SBA X. A lista será necessária quando os usuários forem movidos de volta para SBA X na etapa 30.</span><span class="sxs-lookup"><span data-stu-id="e21c0-185">Create a file that contains a list of users homed on SBA X. The list will be needed when the users are moved back to SBA X in step 30.</span></span> <span data-ttu-id="e21c0-186">Para fazer isso, execute o seguinte cmdlet:</span><span class="sxs-lookup"><span data-stu-id="e21c0-186">To do so, run the following cmdlet:</span></span>
        
            Get-CsUser -Filter {RegistrarPool -eq "<SBA X FQDN>"} | Export-Csv d:\sbaxusers.txt
    
      - <span data-ttu-id="e21c0-187">Forçar usuários hospedados no SBA X para mover-se para o pool C executando o seguinte cmdlet:</span><span class="sxs-lookup"><span data-stu-id="e21c0-187">Force users homed on SBA X to move to pool C by running the following cmdlet:</span></span>
        
            Get-CsUser -Filter {RegistrarPool -eq "<SBA X FQDN>"} | Move-CsUser -Target <Pool C FQDN> -Force -Verbose
    
      - <span data-ttu-id="e21c0-188">Atualize os dados desses usuários executando primeiro os seguintes cmdlets:</span><span class="sxs-lookup"><span data-stu-id="e21c0-188">Update the data of these users by first running the following cmdlets:</span></span>
        
            Convert-csUserData -InputFile <Data file exported from PoolB> -OutputFile c:\Logs\ExportedUserData.xml -TargetVersionLync2010 
            $a=get-csuser -Filter {RegistrarPool -eq "FQDN of SBA X"} | select SipAddress
            foreach($x in $a) {$x.SipAddress.Substring(4) >> users.txt}
        
        <span data-ttu-id="e21c0-189">Em seguida, execute este script:</span><span class="sxs-lookup"><span data-stu-id="e21c0-189">And then run this script:</span></span>
        
            $users=gc c:\logs\users.txt
            foreach ($user in $users)
            {
            Update-CsUserData -FileName c:\logs\exportedUserDAta.xml -UserFilter $user - 
            }
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="e21c0-190">Ocorrerá uma falha de serviço para os usuários que estiverem hospedados no SBAs associados ao pool A até que esses usuários sejam movidos para o pool C.</span><span class="sxs-lookup"><span data-stu-id="e21c0-190">A service outage will occur for users who are homed on SBAs that are associated with pool A until these users are moved to pool C.</span></span>

        
        </div>

28. <span data-ttu-id="e21c0-191">No construtor de topologia, para cada SBA X associado ao pool A, faça o seguinte:</span><span class="sxs-lookup"><span data-stu-id="e21c0-191">In Topology Builder, for each SBA X previously associated with Pool A, do the following:</span></span>
    
      - <span data-ttu-id="e21c0-192">Altere a associação para o pool C. Para fazer isso, clique no site da ramificação, expanda o nó utensílios ou servidores da ramificação sobreviventes e clique em ramificação da **ramificação sobreviventes**.</span><span class="sxs-lookup"><span data-stu-id="e21c0-192">Change the association to Pool C. To do so, click the branch site, expand the Survivable Branch Appliances or Servers node, and click **Survivable Branch Appliance**.</span></span> <span data-ttu-id="e21c0-193">Em seguida, selecione o **pool de front-end, o pool de serviços do usuário** para o qual este aparelho de ramificação sobreviventes será conectado como pool C e clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="e21c0-193">Then select the **Front End pool, User Services Pool** that this Survivable Branch Appliance will connect to as Pool C, and then click **Next**.</span></span>
    
      - <span data-ttu-id="e21c0-194">Publique a topologia.</span><span class="sxs-lookup"><span data-stu-id="e21c0-194">Publish the topology.</span></span> <span data-ttu-id="e21c0-195">Para fazer isso, na árvore de console, clique com o botão direito do mouse no novo **aplicativo de ramificação sobreviventes**, clique em **topologia**e, em seguida, clique em **publicar**.</span><span class="sxs-lookup"><span data-stu-id="e21c0-195">To do so, in the console tree, right-click the new **Survivable Branch Appliance**, click **Topology**, and then click **Publish**.</span></span>

29. <span data-ttu-id="e21c0-196">Para cada SBA X agora associado ao pool C:</span><span class="sxs-lookup"><span data-stu-id="e21c0-196">For each SBA X now associated with pool C:</span></span>
    
      - <span data-ttu-id="e21c0-197">Inicie o SBA X executando o seguinte cmdlet no aparelho da ramificação sobreviventes:</span><span class="sxs-lookup"><span data-stu-id="e21c0-197">Start SBA X by running the following cmdlet on the survivable branch appliance:</span></span>
        
            Start-CsWindowsService
    
      - <span data-ttu-id="e21c0-198">Mova os usuários que estavam originalmente hospedados no SBA X do pool C para o SBA X executando o cmdlet a seguir.</span><span class="sxs-lookup"><span data-stu-id="e21c0-198">Move users who were originally homed on SBA X from pool C to SBA X by running the following cmdlet.</span></span>
        
            Import-Csv d:\sbaxusers.txt | Move-CsUser -Target <SBA X FQDN> -Force

</div>

</div>

<span> </span>

</div>

</div>

</div>

