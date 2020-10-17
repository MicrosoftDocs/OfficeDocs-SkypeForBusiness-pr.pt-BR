---
title: 'Lync Server 2013: procedimento de failover ABC do pool Front-end'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Front End pool ABC failover procedure
ms:assetid: 67763ad3-6796-45eb-a486-901f21ac1a95
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945635(v=OCS.15)
ms:contentKeyID: 51541486
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: aa82180853e8835782d1e39d56fe595e5c7b09b2
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48500798"
---
# <a name="front-end-pool-abc-failover-procedure-in-lync-server-2013"></a><span data-ttu-id="5aecd-102">Procedimento de failover ABC do pool de front-ends no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5aecd-102">Front End pool ABC failover procedure in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5aecd-103">_**Última modificação do tópico:** 2014-05-22_</span><span class="sxs-lookup"><span data-stu-id="5aecd-103">_**Topic Last Modified:** 2014-05-22_</span></span>

<span data-ttu-id="5aecd-104">Use as etapas a seguir para executar o procedimento de failover ABC.</span><span class="sxs-lookup"><span data-stu-id="5aecd-104">Use the following steps to perform the ABC failover procedure.</span></span> <span data-ttu-id="5aecd-105">Este procedimento contém uma descrição de alto nível de cada etapa, seguida por comandos e cmdlets a serem executados para cada etapa.</span><span class="sxs-lookup"><span data-stu-id="5aecd-105">This procedure contains a high-level description of each step, followed by commands and cmdlets to be run for each step.</span></span>

<span data-ttu-id="5aecd-106">Para executar os cmdlets, abra um shell de gerenciamento do Lync Server usando executar como administrador.</span><span class="sxs-lookup"><span data-stu-id="5aecd-106">To run the cmdlets, open a Lync Server Management Shell using Run as Administrator.</span></span>

<div>

## <a name="to-perform-an-abc-failover"></a><span data-ttu-id="5aecd-107">Para executar um failover ABC</span><span class="sxs-lookup"><span data-stu-id="5aecd-107">To Perform an ABC Failover</span></span>

1.  <span data-ttu-id="5aecd-108">Verifique se o pool A é o host para o servidor de gerenciamento central (CMS).</span><span class="sxs-lookup"><span data-stu-id="5aecd-108">Check whether the pool A is the host for the Central Management Server (CMS).</span></span>
    
      - <span data-ttu-id="5aecd-109">Execute o seguinte cmdlet:</span><span class="sxs-lookup"><span data-stu-id="5aecd-109">Run the following cmdlet:</span></span>
        
            Get-CsService -CentralManagement
        
        <span data-ttu-id="5aecd-110">Se o campo Identity do CMS ativo apontar para o FQDN (nome de domínio totalmente qualificado) do pool A, você usará as etapas 2 e 3 deste procedimento para fazer o failover do servidor de gerenciamento central primeiro.</span><span class="sxs-lookup"><span data-stu-id="5aecd-110">If the Identity field of the active CMS points to the fully qualified domain name (FQDN) of Pool A, then you use steps 2 and 3 of this procedure to fail over the Central Management Server first.</span></span> <span data-ttu-id="5aecd-111">Caso contrário, pule para a etapa 4.</span><span class="sxs-lookup"><span data-stu-id="5aecd-111">Otherwise, skip to step 4.</span></span>

2.  <span data-ttu-id="5aecd-112">Faça o failover do CMS para o pool B no modo de recuperação de desastre executando o seguinte cmdlet:</span><span class="sxs-lookup"><span data-stu-id="5aecd-112">Fail over the CMS to Pool B in disaster recovery mode by running the following cmdlet:</span></span>
    
        Invoke-CsManagementServerFailover -BackupSqlServerFqdn <Pool B BE FQDN> -BackupSqlInstanceName <Pool B BE instance name> [-BackupMirrorSqlServerFqdn <Pool B Mirror BE FQDN> -BackupMirrorSqlInstanceName <Pool B Mirror BE Instance name>] -Force -Verbose
    
    <span data-ttu-id="5aecd-113">Depois de fazer isso, recomendamos que você mova o CMS do pool B para outro pool emparelhado existente para obter resiliência extra.</span><span class="sxs-lookup"><span data-stu-id="5aecd-113">After you do this, we recommend that you move the CMS from pool B to another existing paired pool for extra resiliency.</span></span> <span data-ttu-id="5aecd-114">Para obter detalhes, consulte [move-CsManagementServer](https://docs.microsoft.com/powershell/module/skype/Move-CsManagementServer)..</span><span class="sxs-lookup"><span data-stu-id="5aecd-114">For details, see [Move-CsManagementServer](https://docs.microsoft.com/powershell/module/skype/Move-CsManagementServer)..</span></span>

3.  <span data-ttu-id="5aecd-115">Se o pool A contém CMS, importe a configuração do LIS do pool A no banco de dados LIS do pool B (LIS. MDF).</span><span class="sxs-lookup"><span data-stu-id="5aecd-115">If Pool A contains CMS, import the LIS configuration from pool A into pool B’s LIS database (Lis.mdf).</span></span> <span data-ttu-id="5aecd-116">Isso funcionará somente se você tiver feito backup de dados de LIS regularmente.</span><span class="sxs-lookup"><span data-stu-id="5aecd-116">This will work only if you have been backing up LIS data on a regular basis.</span></span> <span data-ttu-id="5aecd-117">Para importar a configuração do LIS, execute os seguintes cmdlets:</span><span class="sxs-lookup"><span data-stu-id="5aecd-117">To import the LIS configuration, run the following cmdlets:</span></span>
    
        Import-CsLisConfiguration -FileName <String> 
        Publish-CsLisConfiguration

4.  <span data-ttu-id="5aecd-118">Importe fluxos de trabalho de serviço do grupo de resposta do Lync Server de backup do pool A no pool B.</span><span class="sxs-lookup"><span data-stu-id="5aecd-118">Import backed-up Lync Server Response Group service workflows from pool A into pool B.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="5aecd-119">Atualmente, o cmdlet <STRONG>Import-CsRgsConfiguration</STRONG> exige que os nomes de fila e fluxo de trabalho no pool A sejam distintos dos nomes de fila e fluxo de trabalho no pool B. Se os nomes não forem distintos, você receberá um erro ao executar o cmdlet <STRONG>Import-CsRgsConfiguration</STRONG> e as filas e fluxos de trabalho precisarão ser renomeados no pool B antes de prosseguir com o cmdlet <STRONG>Import-CsRgsConfiguration</STRONG> .</span><span class="sxs-lookup"><span data-stu-id="5aecd-119">Currently, the <STRONG>Import-CsRgsConfiguration</STRONG> cmdlet requires that the queue and workflow names on pool A are distinct from the queue and workflow names on pool B. If the names are not distinct, you will get an error when running the <STRONG>Import-CsRgsConfiguration</STRONG> cmdlet, and the queues and workflows will need to be renamed in pool B before proceeding with <STRONG>Import-CsRgsConfiguration</STRONG> cmdlet.</span></span>

    
    </div>
    
    <span data-ttu-id="5aecd-120">Você tem duas opções para importar a configuração do grupo de resposta do pool A para o pool B. A opção que você usa depende se você deseja substituir as configurações de nível de aplicativo do pool B pelas configurações de nível de aplicativo do pool A.</span><span class="sxs-lookup"><span data-stu-id="5aecd-120">You have two options for importing the Response Group configuration from pool A to pool B. Which option you use depends on whether you want to overwrite the application-level settings of pool B with the application-level settings in pool A.</span></span>
    
      - <span data-ttu-id="5aecd-121">Se você quiser substituir as configurações do pool B, execute o cmdlet **Import-CsRgsConfiguration** com a opção **ReplaceExistingSettings** :</span><span class="sxs-lookup"><span data-stu-id="5aecd-121">If you want to overwrite the Pool B settings, run the **Import-CsRgsConfiguration** cmdlet with the **ReplaceExistingSettings** option:</span></span>
        
            Import-CsRgsConfiguration -Destination "service:ApplicationServer:<Pool B FQDN>" -FileName "C:\RgsExportPrimary.zip"  -ReplaceExistingRgsSettings
    
      - <span data-ttu-id="5aecd-122">Se você não quiser substituir as configurações do pool B, use o cmdlet **Import-CsRgsConfiguration** sem a opção **ReplaceExistingSettings** .</span><span class="sxs-lookup"><span data-stu-id="5aecd-122">If you do not want to overwrite the Pool B settings, use the **Import-CsRgsConfiguration** cmdlet without the **ReplaceExistingSettings** option.</span></span>
        
            Import-CsRgsConfiguration -Destination "service:ApplicationServer:<Pool B FQDN>" -FileName "C:\RgsExportPrimary.zip"
    
    <div>
    

    > [!WARNING]  
    > <span data-ttu-id="5aecd-123">Lembre-se de que se você não quiser substituir as configurações de nível de aplicativo do pool de backup (pool B) pelas configurações do pool primário (pool A), as configurações de nível de aplicativo do pool A serão perdidas se o pool A for perdido, porque o aplicativo do grupo de resposta pode armazenar somente um conjunto de configurações no nível do aplicativo por pool.</span><span class="sxs-lookup"><span data-stu-id="5aecd-123">Keep in mind that if you do not want to overwrite the application-level settings of the backup pool (pool B) with the settings of the primary pool (pool A), pool A’s application-level settings will be lost if pool A is lost, because the Response Group application can store only one set of application-level settings per pool.</span></span> <span data-ttu-id="5aecd-124">Quando o pool C é implantado para substituir o pool A, as configurações no nível do aplicativo devem ser reconfiguradas, incluindo o arquivo de áudio de música em espera padrão.</span><span class="sxs-lookup"><span data-stu-id="5aecd-124">When pool C is deployed to replace pool A, the application-level settings must be reconfigured, including the default music-on-hold audio file.</span></span>

    
    </div>

5.  <span data-ttu-id="5aecd-125">Verifique se a importação da configuração do grupo de resposta foi bem-sucedida executando os seguintes cmdlets para exibir os grupos de resposta importados.</span><span class="sxs-lookup"><span data-stu-id="5aecd-125">Verify that the Response Group configuration import was successful by running the following cmdlets to display the imported response groups.</span></span> <span data-ttu-id="5aecd-126">Observe que os grupos de resposta importados ainda pertencem ao pool A.</span><span class="sxs-lookup"><span data-stu-id="5aecd-126">Note that the imported response groups are still owned by pool A.</span></span>
    
        Get-CsRgsWorkflow -Identity "service:ApplicationServer:<Pool B FQDN>" -Owner "service:ApplicationServer:<Pool A FQDN>"
        
        Get-CsRgsQueue -Identity "service:ApplicationServer:<Pool B FQDN>" -Owner "service:ApplicationServer:<Pool A FQDN>"
        
        Get-CsRgsAgentGroup -Identity "service:ApplicationServer:<Pool B FQDN>" -Owner "service:ApplicationServer:<Pool A FQDN>"

6.  <span data-ttu-id="5aecd-127">Para números não atribuídos, mova os intervalos de números não atribuídos que estão usando "Announcement" como o serviço de anúncio selecionado do pool A para o pool B. Para fazer isso:</span><span class="sxs-lookup"><span data-stu-id="5aecd-127">For Unassigned Numbers, move the Unassigned Number ranges that are using "Announcement" as the selected announcement service from pool A to pool B. To do so:</span></span>
    
      - <span data-ttu-id="5aecd-128">Recrie todos os comunicados que foram implantados no pool A no pool B. Se qualquer arquivo de áudio foi usado durante a implantação dos comunicados no pool A, esses arquivos serão necessários para recriar os comunicados no pool B. Para recriar os comunicados no pool B, use os cmdlets **New-CsAnnouncement** , com o pool B como o serviço pai.</span><span class="sxs-lookup"><span data-stu-id="5aecd-128">Re-create all announcements that were deployed in pool A on pool B. If any audio files were used when deploying the announcements in pool A, these files will be needed to re-create the announcements in pool B. To re-create the announcements in pool B, use the **New-CsAnnouncement** cmdlets, with pool B as the Parent service.</span></span>
    
      - <span data-ttu-id="5aecd-129">Redirecionar todos os intervalos de números não atribuídos que estão direcionados para um comunicado no pool A para os anúncios recentemente implantados no pool B. Execute o cmdlet a seguir para cada intervalo de números não atribuídos direcionado para um anúncio do pool A:</span><span class="sxs-lookup"><span data-stu-id="5aecd-129">Retarget all the Unassigned Number ranges that are targeting an announcement in pool A to the newly deployed announcements in pool B. Run the following cmdlet for every Unassigned Number range targeting an announcement of pool A:</span></span>
        
            Set-CsUnassignedNumber -Identity "<Range Name>" -AnnouncementService "<Pool B FQDN>" -AnnouncementName "<New Announcement in pool B>"
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="5aecd-130">Esta etapa não é necessária para intervalos de números não atribuídos que usam "UM do Exchange" como o serviço de anúncio selecionado.</span><span class="sxs-lookup"><span data-stu-id="5aecd-130">This step is not required for unassigned number ranges that use "Exchange UM" as the selected announcement service.</span></span>

    
    </div>

7.  <span data-ttu-id="5aecd-131">Failover do pool A para o pool B no modo de recuperação de desastres (DR), executando o seguinte cmdlet:</span><span class="sxs-lookup"><span data-stu-id="5aecd-131">Fail over Pool A to Pool B in Disaster Recovery (DR) mode, by running the following cmdlet:</span></span>
    
        Invoke-CsPoolFailover -PoolFqdn <Pool A FQDN> -DisasterMode

8.  <span data-ttu-id="5aecd-132">Construa o pool C, mas não inicie nenhum serviço no pool C.</span><span class="sxs-lookup"><span data-stu-id="5aecd-132">Build pool C, but do not start any services on pool C.</span></span>
    
    <span data-ttu-id="5aecd-133">Observe que esta etapa pode ser executada simultaneamente com as etapas 5 e 6.</span><span class="sxs-lookup"><span data-stu-id="5aecd-133">Note that this step can be carried out concurrently with steps 5 and 6.</span></span>

9.  <span data-ttu-id="5aecd-134">Forçar usuários hospedados no pool A para mover para o pool C executando o seguinte cmdlet:</span><span class="sxs-lookup"><span data-stu-id="5aecd-134">Force users homed on pool A to move to pool C by running the following cmdlet:</span></span>
    
        Get-csuser -Filter {RegistrarPool -eq "<Pool A FQDN>"} | Move-CsUser -Target <Pool C FQDN> -Force
    
    <span data-ttu-id="5aecd-135">Neste ponto, os usuários hospedados no pool A começarão a enfrentar uma interrupção de serviço.</span><span class="sxs-lookup"><span data-stu-id="5aecd-135">At this point, users homed on pool A will begin to experience a service outage.</span></span> <span data-ttu-id="5aecd-136">Essa interrupção continuará até a etapa 16, em que os serviços de ponto são iniciados no pool C.</span><span class="sxs-lookup"><span data-stu-id="5aecd-136">This outage will continue until step 16, at which point services are started on pool C.</span></span>

10. <span data-ttu-id="5aecd-137">Force o diretório de conferência do pool A para mover para o pool C executando o seguinte cmdlet:</span><span class="sxs-lookup"><span data-stu-id="5aecd-137">Force the conference directory of pool A to move to pool C by running the following cmdlet:</span></span>
    
        Move-CsConferenceDirectory -Identity <Conference Directory ID of Pool A> -TargetPool <Pool C FQDN> -Force

11. <span data-ttu-id="5aecd-138">Force o objeto de contato do atendedor automático da conferência (CAA) para mover do pool A para o pool C executando o seguinte cmdlet:</span><span class="sxs-lookup"><span data-stu-id="5aecd-138">Force the Conference Auto Attendant (CAA) Contact Object to move from pool A to pool C by running the following cmdlet:</span></span>
    
        Move-csApplicationEndpoint -Identity "<Pool A CAA Uri>" -targetApplicationPool <Pool C FQDN> -force

12. <span data-ttu-id="5aecd-139">Copie o conteúdo da conferência do pool B para o pool C.</span><span class="sxs-lookup"><span data-stu-id="5aecd-139">Copy conference content from pool B to pool C.</span></span>

13. <span data-ttu-id="5aecd-140">Exportar dados do usuário do pool B e importar os dados do usuário para o pool C executando os seguintes cmdlets:</span><span class="sxs-lookup"><span data-stu-id="5aecd-140">Export user data from pool B and import the user data into pool C by running the following cmdlets:</span></span>
    
        Export-CsUserData -PoolFqdn <Pool B Fqdn> -FileName <String>
        Import-CsUserData -PoolFqdn <Pool C Fqdn> -FileName <String>

14. <span data-ttu-id="5aecd-141">Restaurar dados de aplicativo de estacionamento de chamada com backup do pool A no pool C e atribuir os intervalos de órbita de estacionamento de chamada do pool A ao pool C.</span><span class="sxs-lookup"><span data-stu-id="5aecd-141">Restore backed-up Call Park application data from pool A into pool C and assign the Call Park orbit ranges of pool A to pool C.</span></span>
    
      - <span data-ttu-id="5aecd-142">Você pode reatribuir um intervalo de órbita de estacionamento de chamada do pool A para o pool C por meio do painel de controle do Lync Server ou do Shell de gerenciamento do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="5aecd-142">You can reassign a Call Park orbit range of pool A to pool C either through the Lync Server Control Panel or the Lync Server Management Shell.</span></span> <span data-ttu-id="5aecd-143">Para o Shell de gerenciamento do Lync Server, execute o seguinte cmdlet para cada intervalo de órbita de estacionamento de chamadas atribuído ao pool A (Observe que o parâmetro Identity se refere aos intervalos de órbita de estacionamento de chamada que pertencem ao pool A):</span><span class="sxs-lookup"><span data-stu-id="5aecd-143">For the Lync Server Management Shell, run the following cmdlet for every Call Park orbit range assigned to pool A (note that the Identity parameter refers to the Call Park Orbit Ranges that belong to pool A):</span></span>
        
            Set-CsCallParkOrbit -Identity "<Call Park Orbit Identity>" -CallParkService "service:ApplicationServer:<Pool C FQDN>"
    
      - <span data-ttu-id="5aecd-144">Se uma música em espera personalizada tiver sido configurada para estacionamento de chamada no pool A, restaure o arquivo de música-em espera personalizado do estacionamento de chamada no pool C.</span><span class="sxs-lookup"><span data-stu-id="5aecd-144">If a customized music-on-hold has been configured for Call Park in pool A, restore the Call Park customized music-on-hold file in pool C.</span></span>
        
            Xcopy <Source> <Destination: Pool C CPS File Store Path>
        
        <span data-ttu-id="5aecd-145">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="5aecd-145">For example:</span></span>
        
            Xcopy "Source Path" "<Pool C File Store Path>\OcsFileStore\coX-ApplicationServer-X\AppServerFiles\CPS\"
    
      - <span data-ttu-id="5aecd-146">Por fim, reconfigure as configurações de estacionamento de chamadas no pool C usando o cmdlet **set-CsCpsConfiguration** .</span><span class="sxs-lookup"><span data-stu-id="5aecd-146">Finally, reconfigure the Call Park settings on pool C by using the **Set-CsCpsConfiguration** cmdlet.</span></span> <span data-ttu-id="5aecd-147">O aplicativo de estacionamento de chamada pode armazenar somente um conjunto de configurações e um arquivo de áudio de música em espera personalizado por pool, e essas configurações não são compartilhadas ou mantidas em caso de desastre.</span><span class="sxs-lookup"><span data-stu-id="5aecd-147">The Call Park application can store only one set of settings and one customized music-on-hold audio file per pool, and these settings are not backed up or preserved in the event of a disaster.</span></span>

15. <span data-ttu-id="5aecd-148">Se o pool de próximo salto para chat persistente estiver apontando para o pool A, faça e publique as alterações de topologia para que o servidor de próximo salto aponte para o pool C.</span><span class="sxs-lookup"><span data-stu-id="5aecd-148">If the next hop pool for Persistent Chat is pointing to pool A, make and publish topology changes so that the next hop server points to pool C.</span></span>
    
      - <span data-ttu-id="5aecd-149">No construtor de topologias, altere o pool de chat persistente para apontar para o pool C como seu próximo salto.</span><span class="sxs-lookup"><span data-stu-id="5aecd-149">In Topology Builder, change the Persistent Chat pool to point to Pool C as its next hop.</span></span> <span data-ttu-id="5aecd-150">Para fazer isso, clique com o botão direito do mouse no pool de chat persistente e, em seguida, clique na guia **geral** e digite o nome do pool C no **pool de próximo salto**.</span><span class="sxs-lookup"><span data-stu-id="5aecd-150">To do so, right-click on the Persistent Chat pool, then click the **General** tab, and then type the name of Pool C in **Next Hop Pool**.</span></span>
    
      - <span data-ttu-id="5aecd-151">Inicie os serviços no pool C executando o seguinte cmdlet:</span><span class="sxs-lookup"><span data-stu-id="5aecd-151">Start services on pool C by running the following cmdlet:</span></span>
        
            Start-csWindowsService
    
    <span data-ttu-id="5aecd-152">Neste ponto, a interrupção do serviço termina para os usuários hospedados originalmente no pool A.</span><span class="sxs-lookup"><span data-stu-id="5aecd-152">At this point, the service outage ends for users originally homed on pool A.</span></span>

16. <span data-ttu-id="5aecd-153">Exportar fluxos de trabalho do serviço grupo de resposta do Lync Server do pool B pertencente ao pool A para importar para o pool C executando o seguinte cmdlet:</span><span class="sxs-lookup"><span data-stu-id="5aecd-153">Export Lync Server Response Group service workflows from pool B owned by pool A for import into pool C by running the following cmdlet:</span></span>
    
        Export-CsRgsConfiguration -Source "service:ApplicationServer:<Pool B FQDN>" -Owner "service:ApplicationServer:<Pool A FQDN>" -FileName "C:\RgsExportPrimaryUpdated.zip" 

17. <span data-ttu-id="5aecd-154">Importe fluxos de trabalho do serviço grupo de resposta do Lync Server no pool C do pool B.</span><span class="sxs-lookup"><span data-stu-id="5aecd-154">Import Lync Server Response Group service workflows into pool C from pool B.</span></span>
    
    <span data-ttu-id="5aecd-155">Você tem duas opções para a importação da configuração do grupo de resposta do pool B para o pool C. A opção que você usa depende se você deseja substituir as configurações de nível de aplicativo do pool C com as configurações no nível do aplicativo no pool B.</span><span class="sxs-lookup"><span data-stu-id="5aecd-155">You have two options are for importing the Response Group configuration from pool B to pool C. Which option you use depends on whether you want to overwrite the application-level settings of pool C with the application-level settings in pool B.</span></span>
    
      - <span data-ttu-id="5aecd-156">Se você quiser substituir as configurações do pool C, execute o cmdlet **Import-CsRgsConfiguration** com a opção **ReplaceExistingSettings** :</span><span class="sxs-lookup"><span data-stu-id="5aecd-156">If you want to overwrite the Pool C settings, run the **Import-CsRgsConfiguration** cmdlet with the **ReplaceExistingSettings** option:</span></span>
        
            Import-CsRgsConfiguration -Destination "service:ApplicationServer:<Pool C FQDN>" -FileName "C:\RgsExportPrimary.zip"  -ReplaceExistingRgsSettings
    
      - <span data-ttu-id="5aecd-157">Se você não quiser substituir as configurações do pool C, use o cmdlet **Import-CsRgsConfiguration** sem a opção **ReplaceExistingSettings** .</span><span class="sxs-lookup"><span data-stu-id="5aecd-157">If you do not want to overwrite the Pool C settings, use the **Import-CsRgsConfiguration** cmdlet without the **ReplaceExistingSettings** option.</span></span>
        
            Import-CsRgsConfiguration -Destination "service:ApplicationServer:<Pool B FQDN>" -FileName "C:\RgsExportPrimary.zip"
    
    <div>
    

    > [!WARNING]  
    > <span data-ttu-id="5aecd-158">Tenha em mente que se você não quiser substituir as configurações de nível de aplicativo do pool C com as configurações do pool de backup (pool B), as configurações de nível de aplicativo do pool B serão perdidas porque o aplicativo de grupo de resposta pode armazenar somente um conjunto de configurações no nível do aplicativo por pool.</span><span class="sxs-lookup"><span data-stu-id="5aecd-158">Keep in mind that if you do not want to overwrite the application-level settings of Pool C with the settings of the backup pool (pool B), pool B’s application-level settings will be lost because the Response Group application can store only one set of application-level settings per pool.</span></span>

    
    </div>

18. <span data-ttu-id="5aecd-159">Verifique se a importação da configuração do grupo de resposta foi bem-sucedida executando os seguintes cmdlets para exibir os grupos de resposta que foram importados para o pool C.</span><span class="sxs-lookup"><span data-stu-id="5aecd-159">Verify that the Response Group configuration import was successful by running the following cmdlets to display the response groups that have been imported to Pool C.</span></span>
    
        Get-CsRgsWorkflow -Identity "service:ApplicationServer:<Pool C FQDN>" -ShowAll
         Get-CsRgsQueue -Identity "service:ApplicationServer:<Pool C FQDN>" -ShowAll
        Get-CsRgsAgentGroup -Identity "service:ApplicationServer:<Pool C FQDN>" -ShowAll

19. <span data-ttu-id="5aecd-160">Quando a configuração importada tiver sido verificada no pool C, remova os grupos de resposta pertencentes ao pool primário do pool B. Isso minimizará o tempo de inatividade dos grupos de resposta.</span><span class="sxs-lookup"><span data-stu-id="5aecd-160">When the imported configuration has been verified in pool C, remove the response groups owned by the primary pool from pool B. This will minimize the downtime of the response groups.</span></span>
    
    <span data-ttu-id="5aecd-161">Esta etapa cria um novo arquivo com a configuração exportada e, em seguida, remove o arquivo do pool B.</span><span class="sxs-lookup"><span data-stu-id="5aecd-161">This step creates a new file with the exported configuration, and then removes the file from pool B.</span></span>
    
        Export-CsRgsConfiguration -Source "service:ApplicationServer:<Pool B FQDN>" -Owner "service:ApplicationServer:<Pool A FQDN>" -FileName "C:\RgsExportPrimaryUpdated.zip" -RemoveExportedConfiguration

20. <span data-ttu-id="5aecd-162">Mover para o pool C os intervalos de números não atribuídos que foram movidos do pool A para o pool B.</span><span class="sxs-lookup"><span data-stu-id="5aecd-162">Move to pool C the Unassigned Number ranges that were moved from pool A to pool B.</span></span>
    
      - <span data-ttu-id="5aecd-163">Recrie no pool C todos os anúncios que foram recriados do pool A no pool B. Se qualquer arquivo de áudio foi usado durante a implantação dos comunicados a serem movidos, será necessário usar esses arquivos para recriar os comunicados no pool C. Para recriar os comunicados no pool C, use os cmdlets **New-CsAnnouncement** , com o pool C como o serviço pai.</span><span class="sxs-lookup"><span data-stu-id="5aecd-163">Re-create in pool C all announcements that were re-created from pool A in pool B. If any audio files were used when deploying the announcements to be moved, you will need to use these files to re-create the announcements in pool C. To re-create the announcements in pool C, use the **New-CsAnnouncement** cmdlets, with pool C as the Parent service.</span></span>
    
      - <span data-ttu-id="5aecd-164">Redirecionar para o pool C todos os intervalos de números não atribuídos que foram redirecionados do pool A para o pool B. Execute o cmdlet a seguir para cada intervalo de número não atribuído que precisa ser redirecionado:</span><span class="sxs-lookup"><span data-stu-id="5aecd-164">Retarget to pool C all the unassigned number ranges that were retargeted from pool A to pool B. Run the following cmdlet for every Unassigned Number range that needs to be retargeted:</span></span>
        
            Set-CsUnassignedNumber -Identity "<Range Name>" -AnnouncementService "<Pool C FQDN>" -AnnouncementName "<New Announcement in pool C>"
    
      - <span data-ttu-id="5aecd-165">Opcion Remover do pool B os anúncios que foram recriados no pool C se não estiverem mais em uso no pool B. Para remover comunicados, use o cmdlet **Remove-CsAnnouncement** .</span><span class="sxs-lookup"><span data-stu-id="5aecd-165">(Optional) Remove from pool B the announcements that were re-created in pool C if they are no longer in use in pool B. To remove announcements, use the **Remove-CsAnnouncement** cmdlet.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="5aecd-166">Esta etapa não é necessária para intervalos de números não atribuídos que usam "UM do Exchange" como serviço de anúncio.</span><span class="sxs-lookup"><span data-stu-id="5aecd-166">This step is not required for unassigned number ranges that use "Exchange UM" as the announcement service.</span></span>

        
        </div>

21. <span data-ttu-id="5aecd-167">Limpe os dados do usuário do pool A no pool B executando o seguinte cmdlet:</span><span class="sxs-lookup"><span data-stu-id="5aecd-167">Clean up user data of pool A in pool B by running the following cmdlet:</span></span>
    
        Remove-CsUserStoreBackupData -PoolFqdn <Pool B FQDN> -Verbose

22. <span data-ttu-id="5aecd-168">No construtor de topologias, faça o seguinte:</span><span class="sxs-lookup"><span data-stu-id="5aecd-168">Do the following in Topology Builder:</span></span>
    
      - <span data-ttu-id="5aecd-169">Desemparelhar pool A e pool B. pool de par B e pool C. Em seguida, remova o pool A da topologia e publique-o.</span><span class="sxs-lookup"><span data-stu-id="5aecd-169">Unpair pool A and pool B. Pair pool B and pool C. Then remove Pool A from the topology and publish it.</span></span> <span data-ttu-id="5aecd-170">Para fazer isso:</span><span class="sxs-lookup"><span data-stu-id="5aecd-170">To do so:</span></span>
        
          - <span data-ttu-id="5aecd-171">No construtor de topologias, clique com o botão direito do mouse no pool B e, em seguida, clique em **Editar propriedades**.</span><span class="sxs-lookup"><span data-stu-id="5aecd-171">In Topology Builder, right-click on Pool B, and then click **Edit Properties**.</span></span>
        
          - <span data-ttu-id="5aecd-172">Clique em **resiliência** no painel esquerdo.</span><span class="sxs-lookup"><span data-stu-id="5aecd-172">Click **Resiliency** in the left pane.</span></span>
        
          - <span data-ttu-id="5aecd-173">Na caixa abaixo **pool de backup associado**, selecione pool C. Observe que a caixa de seleção pool de backup associado exibirá inicialmente o pool A, porque o pool B estava anteriormente associado a esse pool.</span><span class="sxs-lookup"><span data-stu-id="5aecd-173">In the box below **Associated Backup Pool**, select Pool C. Note that the Associated Backup Pool selection box will initially display pool A, because pool B was previously associated with this pool.</span></span>
        
          - <span data-ttu-id="5aecd-174">Selecione **Failover automático e failback para voz** e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="5aecd-174">Select **Automatic failover and failback for Voice**, and then click **OK**.</span></span>
            
            <span data-ttu-id="5aecd-175">Ao exibir os detalhes sobre este pool, o pool associado agora aparece no painel direito em **Resiliência**.</span><span class="sxs-lookup"><span data-stu-id="5aecd-175">When you view the details about this pool, the associated pool now appears in the right pane under **Resiliency**.</span></span>
        
          - <span data-ttu-id="5aecd-176">Na árvore do console, clique com o botão direito do mouse em pool A e clique em excluir.</span><span class="sxs-lookup"><span data-stu-id="5aecd-176">In the console tree, right-click pool A, and then click Delete.</span></span>
        
          - <span data-ttu-id="5aecd-177">Publique a topologia.</span><span class="sxs-lookup"><span data-stu-id="5aecd-177">Publish the topology.</span></span>

23. <span data-ttu-id="5aecd-178">Execute o aplicativo de inicialização no pool C para instalar o aplicativo de serviço de backup e, em seguida, inicie o aplicativo de serviço de backup executando o seguinte na pasta de implantação em um computador local no pool C:</span><span class="sxs-lookup"><span data-stu-id="5aecd-178">Run the bootstrapping application on pool C to install the backup service application, and then start the backup service application by running the following from the deployment folder on a local machine in pool C:</span></span>
    
        Run "%SYSTEMROOT%\Program Files\Microsoft Lync Server 2013\Deployment\Bootstrapper.exe"
        Start-CsWindowsService -name LyncBackup

24. <span data-ttu-id="5aecd-179">Reinicie o aplicativo de serviço de backup no pool B executando os seguintes cmdlets:</span><span class="sxs-lookup"><span data-stu-id="5aecd-179">Restart the backup service application on pool B by running the following cmdlets:</span></span>
    
        Stop-CsWindowsService -name LyncBackup
        Start-CsWindowsService -name LyncBackup

25. <span data-ttu-id="5aecd-180">Se o pool C for um pool Standard Edition (SE) e o pool B tiver o CMS, instale o banco de dados CMS manualmente no pool C executando o seguinte cmdlet:</span><span class="sxs-lookup"><span data-stu-id="5aecd-180">If pool C is a Standard Edition (SE) Pool and pool B has CMS, install the CMS database manually on pool C by running the following cmdlet:</span></span>
    
        Install-CsDatabase -CentralManagementDatabase -SqlServerFqdn <Pool C FQDN> -SqlInstanceName rtc

26. <span data-ttu-id="5aecd-181">Invocar o serviço de backup para sincronizar o conteúdo antigo da conferência do pool B para o pool C que foi gerado antes de emparelhar B e C juntos e sincronizar o novo conteúdo de conferência do pool C para o pool B que foi gerado após iniciar o pool C e antes de o B e o C terem sido emparelhados juntos.</span><span class="sxs-lookup"><span data-stu-id="5aecd-181">Invoke the backup service to sync old conferencing content from pool B to pool C that was generated before pairing B and C together, and to sync new conferencing content from pool C to pool B that was generated after starting pool C and before B and C were paired together.</span></span> <span data-ttu-id="5aecd-182">Para fazer isso, execute os seguintes cmdlets:</span><span class="sxs-lookup"><span data-stu-id="5aecd-182">To do so, run the following cmdlets:</span></span>
    
        Invoke-CsBackupServiceSync -PoolFqdn <Pool C FQDN>
        Invoke-CsBackupServiceSync -PoolFqdn <Pool B FQDN>

27. <span data-ttu-id="5aecd-183">Para cada aparelho de filial persistente X associado ao pool A:</span><span class="sxs-lookup"><span data-stu-id="5aecd-183">For each Survivable Branch Appliance X associated with pool A:</span></span>
    
      - <span data-ttu-id="5aecd-184">Desligue o SBA X executando o seguinte cmdlet:</span><span class="sxs-lookup"><span data-stu-id="5aecd-184">Shut down SBA X by running the following cmdlet:</span></span>
        
            Stop-CsWindowsService
    
      - <span data-ttu-id="5aecd-185">Criar um arquivo que contém uma lista de usuários hospedados no SBA X. A lista será necessária quando os usuários forem movidos de volta para o SBA X na etapa 30.</span><span class="sxs-lookup"><span data-stu-id="5aecd-185">Create a file that contains a list of users homed on SBA X. The list will be needed when the users are moved back to SBA X in step 30.</span></span> <span data-ttu-id="5aecd-186">Para fazer isso, execute o seguinte cmdlet:</span><span class="sxs-lookup"><span data-stu-id="5aecd-186">To do so, run the following cmdlet:</span></span>
        
            Get-CsUser -Filter {RegistrarPool -eq "<SBA X FQDN>"} | Export-Csv d:\sbaxusers.txt
    
      - <span data-ttu-id="5aecd-187">Forçar usuários hospedados no SBA X para mover para o pool C executando o seguinte cmdlet:</span><span class="sxs-lookup"><span data-stu-id="5aecd-187">Force users homed on SBA X to move to pool C by running the following cmdlet:</span></span>
        
            Get-CsUser -Filter {RegistrarPool -eq "<SBA X FQDN>"} | Move-CsUser -Target <Pool C FQDN> -Force -Verbose
    
      - <span data-ttu-id="5aecd-188">Atualize os dados desses usuários primeiro executando os seguintes cmdlets:</span><span class="sxs-lookup"><span data-stu-id="5aecd-188">Update the data of these users by first running the following cmdlets:</span></span>
        
            Convert-csUserData -InputFile <Data file exported from PoolB> -OutputFile c:\Logs\ExportedUserData.xml -TargetVersionLync2010 
            $a=get-csuser -Filter {RegistrarPool -eq "FQDN of SBA X"} | select SipAddress
            foreach($x in $a) {$x.SipAddress.Substring(4) >> users.txt}
        
        <span data-ttu-id="5aecd-189">E, em seguida, execute este script:</span><span class="sxs-lookup"><span data-stu-id="5aecd-189">And then run this script:</span></span>
        
            $users=gc c:\logs\users.txt
            foreach ($user in $users)
            {
            Update-CsUserData -FileName c:\logs\exportedUserDAta.xml -UserFilter $user - 
            }
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="5aecd-190">Ocorrerá uma interrupção de serviço para usuários hospedados no SBAs que estão associados ao pool A até que estes usuários sejam movidos para o pool C.</span><span class="sxs-lookup"><span data-stu-id="5aecd-190">A service outage will occur for users who are homed on SBAs that are associated with pool A until these users are moved to pool C.</span></span>

        
        </div>

28. <span data-ttu-id="5aecd-191">No construtor de topologia, para cada SBA X previamente associado ao pool A, faça o seguinte:</span><span class="sxs-lookup"><span data-stu-id="5aecd-191">In Topology Builder, for each SBA X previously associated with Pool A, do the following:</span></span>
    
      - <span data-ttu-id="5aecd-192">Altere a associação para o pool C. Para fazer isso, clique no site de filial, expanda o nó dispositivos ou servidores de filial persistente e clique em **aparelho de filial persistente**.</span><span class="sxs-lookup"><span data-stu-id="5aecd-192">Change the association to Pool C. To do so, click the branch site, expand the Survivable Branch Appliances or Servers node, and click **Survivable Branch Appliance**.</span></span> <span data-ttu-id="5aecd-193">Em seguida, selecione o **pool de front-ends, o pool de serviços de usuário** ao qual esse aparelho de filial persistente será conectado como pool C e clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="5aecd-193">Then select the **Front End pool, User Services Pool** that this Survivable Branch Appliance will connect to as Pool C, and then click **Next**.</span></span>
    
      - <span data-ttu-id="5aecd-194">Publique a topologia.</span><span class="sxs-lookup"><span data-stu-id="5aecd-194">Publish the topology.</span></span> <span data-ttu-id="5aecd-195">Para fazer isso, na árvore de console, clique com o botão direito do mouse no novo **dispositivo de filial persistente**, clique em **topologia**e em **publicar**.</span><span class="sxs-lookup"><span data-stu-id="5aecd-195">To do so, in the console tree, right-click the new **Survivable Branch Appliance**, click **Topology**, and then click **Publish**.</span></span>

29. <span data-ttu-id="5aecd-196">Para cada SBA X agora associado ao pool C:</span><span class="sxs-lookup"><span data-stu-id="5aecd-196">For each SBA X now associated with pool C:</span></span>
    
      - <span data-ttu-id="5aecd-197">Inicie o SBA X executando o seguinte cmdlet no aparelho de filial persistente:</span><span class="sxs-lookup"><span data-stu-id="5aecd-197">Start SBA X by running the following cmdlet on the survivable branch appliance:</span></span>
        
            Start-CsWindowsService
    
      - <span data-ttu-id="5aecd-198">Mova os usuários que estavam originalmente hospedados no SBA X do pool C para o SBA X executando o seguinte cmdlet.</span><span class="sxs-lookup"><span data-stu-id="5aecd-198">Move users who were originally homed on SBA X from pool C to SBA X by running the following cmdlet.</span></span>
        
            Import-Csv d:\sbaxusers.txt | Move-CsUser -Target <SBA X FQDN> -Force

</div>

</div>

<span> </span>

</div>

</div>

</div>

