---
title: 'Lync Server 2013: pré-requisitos de backup para failover do pool ABC'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Backup prerequisites for ABC pool failover
ms:assetid: 652046f5-6086-4592-902d-d5789581977d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945634(v=OCS.15)
ms:contentKeyID: 51541485
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f7cdb228b0a748c830aa488e7b058bf8664360d0
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34836744"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="backup-prerequisites-for-abc-pool-failover-in-lync-server-2013"></a><span data-ttu-id="7deaa-102">Pré-requisitos de backup para failover de pool ABC no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7deaa-102">Backup prerequisites for ABC pool failover in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7deaa-103">_**Tópico da última modificação:** 2013-03-26_</span><span class="sxs-lookup"><span data-stu-id="7deaa-103">_**Topic Last Modified:** 2013-03-26_</span></span>

<span data-ttu-id="7deaa-104">Para obter o máximo de benefícios de usar o procedimento de failover do pool ABC, você deve executar determinados backups antes que ocorra o desastre e o failover:</span><span class="sxs-lookup"><span data-stu-id="7deaa-104">To get the maximum benefit from using the ABC pool failover procedure, you must perform certain backups before the disaster and failover happen:</span></span>

  - <span data-ttu-id="7deaa-105">Você deve fazer regularmente o backup dos dados de configuração do LIS (serviço de informações de localização) do pool A usando o cmdlet **Export-CsLISConfiguration** .</span><span class="sxs-lookup"><span data-stu-id="7deaa-105">You must regularly back up the Location Information Service (LIS) configuration data from pool A by using the **Export-CsLISConfiguration** cmdlet.</span></span>
    
        Export-csLisConfiguration -FileName <C:\LISExportPrimary.zip>

  - <span data-ttu-id="7deaa-106">Você deve fazer regularmente o backup dos dados de configuração do grupo de resposta no pool A usando o cmdlet **Export-CsRgsConfiguration** .</span><span class="sxs-lookup"><span data-stu-id="7deaa-106">You must regularly back up the Response Group configuration data in pool A by using the **Export-CsRgsConfiguration** cmdlet.</span></span>
    
        Export-CsRgsConfiguration -Source "service:ApplicationServer:<Pool A FQDN>" -FileName "C:\RgsExportPrimary.zip"
    
    <span data-ttu-id="7deaa-107">Em geral, recomendamos que você realize backups diários, mas se você tiver um grande volume de alterações, talvez queira agendar backups mais frequentes.</span><span class="sxs-lookup"><span data-stu-id="7deaa-107">In general, we recommend that you perform daily backups, but if you have a high volume of changes, you might want to schedule more frequent backups.</span></span> <span data-ttu-id="7deaa-108">A quantidade de informações que você pode perder no caso de um desastre depende da frequência dos seus backups, bem como da frequência e do volume das alterações.</span><span class="sxs-lookup"><span data-stu-id="7deaa-108">The amount of information that you can lose in the event of a disaster depends on the frequency of your backups, as well as on the frequency and volume of changes.</span></span>
    
    <span data-ttu-id="7deaa-109">O aplicativo grupo de resposta pode armazenar apenas um conjunto de configurações no nível do aplicativo por pool.</span><span class="sxs-lookup"><span data-stu-id="7deaa-109">The Response Group application can store only one set of application-level settings per pool.</span></span> <span data-ttu-id="7deaa-110">Essas configurações podem ser acessadas por meio dos cmdlets **Get-CsRgsConfiguration** .</span><span class="sxs-lookup"><span data-stu-id="7deaa-110">These settings can be accessed through the **Get-CsRgsConfiguration** cmdlets.</span></span> <span data-ttu-id="7deaa-111">As configurações incluem a configuração de música em espera padrão, o arquivo de áudio de música em espera padrão, o período de cortesia de toque do agente e a configuração do contexto de chamada.</span><span class="sxs-lookup"><span data-stu-id="7deaa-111">The settings include the default music-on-hold configuration, the default music-on-hold audio file, the agent ring-back grace period, and the call context configuration.</span></span> <span data-ttu-id="7deaa-112">Essas configurações podem ser transferidas de um pool para outro por meio do cmdlet **Import-CsRgsConfiguration** usando o parâmetro **ReplaceExistingSettings** , mas essa operação substituirá qualquer configuração no nível do aplicativo no destino Grupo.</span><span class="sxs-lookup"><span data-stu-id="7deaa-112">These settings can be transferred from one pool to another through the **Import-CsRgsConfiguration** cmdlet by using the **ReplaceExistingSettings** parameter, but this operation will override any application-level settings in the destination pool.</span></span>
    
    <div>
    

    > [!TIP]  
    > <span data-ttu-id="7deaa-113">Em um local separado, mantenha uma cópia de backup de todos os arquivos de áudio originais que foram usados para configurar o aplicativo do grupo de resposta (ou seja, quaisquer gravações ou arquivos de música em espera).</span><span class="sxs-lookup"><span data-stu-id="7deaa-113">In a separate location, keep a backup copy of all the original audio files that have been used to configure the Response Group application (that is, any recordings or music-on-hold files).</span></span>

    
    </div>
    
    <span data-ttu-id="7deaa-114">Se você tiver qualquer arquivo de música em espera personalizado que tenha sido carregado para o parque de chamadas em um pool, mantenha uma cópia deles em outro local.</span><span class="sxs-lookup"><span data-stu-id="7deaa-114">If you have any customized music-on-hold files that have been uploaded for Call Park in a pool, you should keep a copy of these in another location.</span></span> <span data-ttu-id="7deaa-115">Esses arquivos não são submetidos a backup como parte do processo de recuperação de desastres do Lync Server 2013, e eles serão perdidos se os arquivos carregados no pool estiverem danificados, corrompidos ou apagados.</span><span class="sxs-lookup"><span data-stu-id="7deaa-115">These files are not backed up as part of the Lync Server 2013 disaster recovery process, and they will be lost if the files uploaded to the pool are damaged, corrupted, or erased.</span></span>
    
        Xcopy  <Source: Pool A CPS File Store Path>  <Destination>
        Example: Xcopy  "<Pool A File Store Path>\LyncFileStore\coX-ApplicationServer-X\AppServerFiles\CPS\"  "<Destination:  Backup location 1>"
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="7deaa-116">O aplicativo de estacionamento de chamadas pode armazenar apenas um conjunto de configurações e um arquivo de áudio de música em espera personalizado por pool.</span><span class="sxs-lookup"><span data-stu-id="7deaa-116">The Call Park application can store only one set of settings and one customized music-on-hold audio file per pool.</span></span> <span data-ttu-id="7deaa-117">Essas configurações podem ser acessadas por meio do cmdlet <STRONG>Get-CsCpsConfiguration</STRONG> .</span><span class="sxs-lookup"><span data-stu-id="7deaa-117">These settings can be accessed through the <STRONG>Get-CsCpsConfiguration</STRONG> cmdlet.</span></span> <span data-ttu-id="7deaa-118">Como o mecanismo de recuperação de desastres do parque de chamadas depende do aplicativo parque de chamadas do pool de backup, as configurações do pool primário não são coligadas nem preservadas se ocorrer um desastre.</span><span class="sxs-lookup"><span data-stu-id="7deaa-118">Because the disaster recovery mechanism for Call Park relies on the Call Park application of the backup pool, the settings of the primary pool are not backed up or preserved if a disaster occurs.</span></span> <span data-ttu-id="7deaa-119">Se o pool primário for perdido, essas configurações não poderão ser recuperadas e, quando um novo pool for implantado para substituir o pool primário, as configurações de estacionamento de chamada e qualquer arquivo de áudio personalizado de música em espera precisariam ser reconfigurados.</span><span class="sxs-lookup"><span data-stu-id="7deaa-119">If the primary pool is lost, these settings cannot be recovered, and when a new pool is deployed to replace the primary pool, the Call Park settings and any customized music-on-hold audio file would need to be reconfigured.</span></span>

    
    </div>

  - <span data-ttu-id="7deaa-120">Se você configurar anúncios como parte do recurso de voz número não atribuído, recomendamos que você mantenha em outro local uma cópia de qualquer arquivo de áudio original usado durante a configuração inicial.</span><span class="sxs-lookup"><span data-stu-id="7deaa-120">If you configure any announcements as part of the Unassigned Number Voice Feature, we recommend that you keep in another location a copy of any original audio file used during the initial configuration.</span></span> <span data-ttu-id="7deaa-121">Se você não fez isso, pode obter uma cópia dos arquivos de áudio configurados no repositório de arquivos do servidor ou pool para o qual os arquivos de áudio foram importados.</span><span class="sxs-lookup"><span data-stu-id="7deaa-121">If you did not do that, you can get a copy of the configured audio files in the file store of the server or pool to which the audio files were imported.</span></span> <span data-ttu-id="7deaa-122">Esses arquivos não são submetidos a backup como parte do processo de recuperação de desastres do Lync Server 2013, e eles serão perdidos se os arquivos carregados no pool estiverem danificados, corrompidos ou apagados.</span><span class="sxs-lookup"><span data-stu-id="7deaa-122">These files are not backed up as part of the Lync Server 2013 disaster recovery process, and they will be lost if the files uploaded to the pool are damaged, corrupted, or erased.</span></span> <span data-ttu-id="7deaa-123">Para copiar todos os arquivos de áudio usados para configurar o recurso de voz número não atribuído do repositório de arquivos de um servidor ou de um pool, use:</span><span class="sxs-lookup"><span data-stu-id="7deaa-123">To copy all the audio files used to configure the Unassigned Number Voice Feature from the file store of a server or a pool, use:</span></span>
    
        Use: Xcopy  <Source: Pool A Announcement Service File Store Path>  <Destination>
        Example Usage:  Xcopy  "<Pool A File Store Path>\X-ApplicationServer-X\AppServerFiles\RGS\AS"  "<Destination: Backup location>"

  - <span data-ttu-id="7deaa-124">Se você tiver bancos de dados de monitoramento e arquivamento em um pool, use as ferramentas de gerenciamento do SQL Server para fazer o backup.</span><span class="sxs-lookup"><span data-stu-id="7deaa-124">If you have Monitoring and Archiving databases in a pool, you should use SQL Server management tools to back them up.</span></span> <span data-ttu-id="7deaa-125">No procedimento de failover do ABC, os bancos de dados de monitoramento e arquivamento não são preservados se eles são posicionados no pool A, porque esses bancos de dados não têm backup do serviço de backup do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="7deaa-125">In the ABC failover procedure, Monitoring and Archiving databases are not preserved if they are collocated in pool A, because these databases are not backed up through Lync Server Backup Service.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

