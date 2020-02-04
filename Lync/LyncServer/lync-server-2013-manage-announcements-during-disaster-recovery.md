---
title: 'Lync Server 2013: Gerenciar comunicados durante recuperação de desastre'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Manage announcements during disaster recovery
ms:assetid: c33e51ea-421f-42d2-826b-b73968f6bd5b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721874(v=OCS.15)
ms:contentKeyID: 49733807
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: dfc987ea579bef4e2b02c8da210efe9a707c5900
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41733421"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="manage-announcements-during-disaster-recovery-in-lync-server-2013"></a><span data-ttu-id="e4d0b-102">Gerenciar comunicados durante recuperação de desastre no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e4d0b-102">Manage announcements during disaster recovery in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e4d0b-103">_**Tópico da última modificação:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="e4d0b-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="e4d0b-104">O Lync Server 2013 dá suporte a anúncios para chamadas para números não atribuídos durante paralisações.</span><span class="sxs-lookup"><span data-stu-id="e4d0b-104">Lync Server 2013 supports announcements for calls to unassigned numbers during outages.</span></span> <span data-ttu-id="e4d0b-105">A restauração da funcionalidade do anúncio durante uma interrupção é opcional.</span><span class="sxs-lookup"><span data-stu-id="e4d0b-105">Restoring announcement functionality during an outage is optional.</span></span> <span data-ttu-id="e4d0b-106">Se você optar por restaurar os comunicados durante uma interrupção, será necessário recriar a configuração do comunicado no pool de backup.</span><span class="sxs-lookup"><span data-stu-id="e4d0b-106">If you choose to restore announcements during an outage, you need recreate your announcement configuration in the backup pool.</span></span> <span data-ttu-id="e4d0b-107">Esta seção descreve o que você precisa fazer se optar por restaurar os comunicados durante a recuperação de desastres.</span><span class="sxs-lookup"><span data-stu-id="e4d0b-107">This section describes what you need to do if you choose to restore announcements during disaster recovery.</span></span>

<span data-ttu-id="e4d0b-108">Esta seção se aplica a intervalos de números não atribuídos que usam o aplicativo de anúncio.</span><span class="sxs-lookup"><span data-stu-id="e4d0b-108">This section applies to unassigned number ranges that use the Announcement application.</span></span> <span data-ttu-id="e4d0b-109">Esta seção não se aplica a intervalos de números não atribuídos que usam o atendedor automático de UM (Unificação de mensagens) do Exchange.</span><span class="sxs-lookup"><span data-stu-id="e4d0b-109">This section does not apply to unassigned number ranges that use Exchange Unified Messaging (UM) Auto Attendant.</span></span>

<div>

## <a name="before-an-outage"></a><span data-ttu-id="e4d0b-110">Antes de uma interrupção</span><span class="sxs-lookup"><span data-stu-id="e4d0b-110">Before an Outage</span></span>

<span data-ttu-id="e4d0b-111">Independentemente de você optar por usar comunicados durante paralisações, você deve fazer backups separados de todos os arquivos de áudio personalizados que você configurou para o aplicativo de anúncio.</span><span class="sxs-lookup"><span data-stu-id="e4d0b-111">Regardless of whether you choose to use announcements during outages, you should take separate backups of any customized audio files that you configured for the Announcement application.</span></span> <span data-ttu-id="e4d0b-112">Anúncios personalizados não são incluídos no backup como parte do processo de recuperação de desastres do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="e4d0b-112">Customized announcements are not backed up as part of the Lync Server disaster recovery process.</span></span> <span data-ttu-id="e4d0b-113">Se você não fizer backups separados dos arquivos e os arquivos que você carregou no servidor ou pool estiverem danificados, corrompidos ou apagados, os arquivos serão perdidos.</span><span class="sxs-lookup"><span data-stu-id="e4d0b-113">If you do not take separate backups of the files and the files that you uploaded to the server or pool are damaged, corrupted, or erased, the files will be lost.</span></span>

<span data-ttu-id="e4d0b-114">Se você não tiver cópias de backup de arquivos de áudio personalizados e os arquivos de áudio originais não estiverem mais disponíveis, você poderá localizar os arquivos de áudio que você configurou para um aplicativo de anúncio, procurando no repositório de arquivos do servidor ou pool em que você originalmente importado os arquivos.</span><span class="sxs-lookup"><span data-stu-id="e4d0b-114">If you do not have backup copies of customized audio files, and the original audio files are no longer available, you can find the audio files that you configured for an Announcement application by looking in the File Store for the server or pool where you originally imported the files.</span></span> <span data-ttu-id="e4d0b-115">Você pode copiar todos os arquivos de áudio que você configurou para o aplicativo de anúncio do repositório de arquivos.</span><span class="sxs-lookup"><span data-stu-id="e4d0b-115">You can copy all the audio files that you configured for the Announcement application from the File Store.</span></span>

<span data-ttu-id="e4d0b-116">**Para copiar arquivos de áudio do repositório de arquivos**</span><span class="sxs-lookup"><span data-stu-id="e4d0b-116">**To copy audio files from the file store**</span></span>

1.  <span data-ttu-id="e4d0b-117">Na linha de comando, execute:</span><span class="sxs-lookup"><span data-stu-id="e4d0b-117">At the command line, run:</span></span>
    
        Xcopy <Source: Pool Announcement Service File Store path> <Destination>
    
    <span data-ttu-id="e4d0b-118">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="e4d0b-118">For example:</span></span>
    
        Xcopy "<Pool File Store Path>\X-ApplicationServer-X\AppServerFiles\RGS\AS" "<Destination: Backup location>"
    
    <span data-ttu-id="e4d0b-119">Em que X-ApplicationServer-X se refere à ID de serviço do servidor de aplicativos do pool (por exemplo, 1-ApplicationServer-1 ")</span><span class="sxs-lookup"><span data-stu-id="e4d0b-119">Where X-ApplicationServer-X refers to the service ID of the Application Server of the pool (for example, 1-ApplicationServer-1")</span></span>


</div>

<div>

## <a name="during-an-outage"></a><span data-ttu-id="e4d0b-120">Durante uma interrupção</span><span class="sxs-lookup"><span data-stu-id="e4d0b-120">During an Outage</span></span>

<span data-ttu-id="e4d0b-121">Para usar o aplicativo de anúncio durante uma interrupção, você precisa recriar a configuração do anúncio no pool de backup executando as tarefas descritas nesta seção.</span><span class="sxs-lookup"><span data-stu-id="e4d0b-121">To use the Announcement application during an outage, you need to recreate the announcement configuration in the backup pool by performing the tasks described in this section.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="e4d0b-122">Recomendamos que você execute essas tarefas depois de fazer failover para o pool de backup, porque assim que executar a etapa 2, o pool de backup apropria-se dos intervalos de números não atribuídos.</span><span class="sxs-lookup"><span data-stu-id="e4d0b-122">We recommend that you perform these tasks after you fail over to the backup pool, because as soon as you perform step 2, the backup pool takes ownership of the unassigned number ranges.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="e4d0b-123">Essas etapas não são necessárias para intervalos de números que usam um número de telefone de atendedor automático do Exchange UM.</span><span class="sxs-lookup"><span data-stu-id="e4d0b-123">These steps are not required for number ranges that use an Exchange UM Auto Attendant phone number.</span></span>



</div>

<span data-ttu-id="e4d0b-124">**Para recriar a configuração do anúncio no pool de backup**</span><span class="sxs-lookup"><span data-stu-id="e4d0b-124">**To recreate the announcement configuration in the backup pool**</span></span>

1.  <span data-ttu-id="e4d0b-125">Recrie os comunicados que você implantou no pool primário do pool de backup fazendo o seguinte:</span><span class="sxs-lookup"><span data-stu-id="e4d0b-125">Recreate the announcements that you deployed in the primary pool in the backup pool by doing the following:</span></span>
    
    1.  <span data-ttu-id="e4d0b-126">Importe todos os arquivos de áudio usados no pool primário para o pool de backup usando o cmdlet **Import-CsAnnouncementFile** e especificando o pool de backup para o parâmetro pai.</span><span class="sxs-lookup"><span data-stu-id="e4d0b-126">Import any audio files used in the primary pool to the backup pool by using the **Import-CsAnnouncementFile** cmdlet and specifying the backup pool for the Parent parameter.</span></span>
    
    2.  <span data-ttu-id="e4d0b-127">Recrie cada anúncio usando o cmdlet **New-CsAnnouncement** e especificando o pool de backup para o parâmetro pai.</span><span class="sxs-lookup"><span data-stu-id="e4d0b-127">Recreate each announcement by using the **New-CsAnnouncement** cmdlet and specifying the backup pool for the Parent parameter.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="e4d0b-128">Para obter detalhes sobre como usar esses parâmetros para criar anúncios no pool de backup, consulte <A href="lync-server-2013-create-an-announcement.md">criar um anúncio no Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="e4d0b-128">For details about using these parameters to create announcements in the backup pool, see <A href="lync-server-2013-create-an-announcement.md">Create an announcement in Lync Server 2013</A>.</span></span>

    
    </div>

2.  <span data-ttu-id="e4d0b-129">Depois que todos os comunicados forem recriados no pool de backup, redirecione todos os intervalos de números não atribuídos que usam comunicados no pool primário para os anúncios recriados no pool de backup.</span><span class="sxs-lookup"><span data-stu-id="e4d0b-129">After all announcements are recreated in the backup pool, redirect all the unassigned number ranges that use announcements in the primary pool to the recreated announcements in the backup pool.</span></span>
    
    <span data-ttu-id="e4d0b-130">Para cada intervalo de números não atribuído que usa um comunicado no pool primário, execute o seguinte:</span><span class="sxs-lookup"><span data-stu-id="e4d0b-130">For each unassigned number range that uses an announcement in the primary pool, run the following:</span></span>
    
        Set-CsUnassignedNumber -Identity "<name of number range>" -AnnouncementService "<FQDN of backup pool>" -AnnouncementName "<announcement name in backup pool>"

</div>

<div>

## <a name="after-the-outage"></a><span data-ttu-id="e4d0b-131">Após a interrupção</span><span class="sxs-lookup"><span data-stu-id="e4d0b-131">After the Outage</span></span>

<span data-ttu-id="e4d0b-132">Quando o pool primário se torna disponível, você precisa redirecionar os intervalos de números não atribuídos que você alterou para que a falha seja retomada para o pool primário.</span><span class="sxs-lookup"><span data-stu-id="e4d0b-132">When the primary pool becomes available, you need to redirect the unassigned number ranges that you changed for the outage back to the primary pool.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="e4d0b-133">Essas etapas não são necessárias para intervalos de números que usam um número de telefone de atendedor automático do Exchange UM.</span><span class="sxs-lookup"><span data-stu-id="e4d0b-133">These steps are not required for number ranges that use an Exchange UM Auto Attendant phone number.</span></span>



</div>

<span data-ttu-id="e4d0b-134">**Para restaurar anúncios no pool primário**</span><span class="sxs-lookup"><span data-stu-id="e4d0b-134">**To restore announcements in the primary pool**</span></span>

1.  <span data-ttu-id="e4d0b-135">Se você tiver que reconstruir o pool primário durante a recuperação, será necessário recriar os comunicados no pool primário importando os arquivos de áudio e criando anúncios, exatamente como o fez no pool de backup, exceto se você especificar o pool primário para o pai com.</span><span class="sxs-lookup"><span data-stu-id="e4d0b-135">If you had to rebuild the primary pool during the recovery, you need to recreate the announcements in the primary pool by importing the audio files and creating announcements, just as you did in the backup pool, except that you specify the primary pool for the Parent parameter.</span></span> <span data-ttu-id="e4d0b-136">Para obter detalhes, consulte "durante uma falha" anteriormente neste tópico.</span><span class="sxs-lookup"><span data-stu-id="e4d0b-136">For details, see "During an Outage" earlier in this topic.</span></span>

2.  <span data-ttu-id="e4d0b-137">Para cada intervalo de números não atribuído que você alterou para a interrupção, execute o seguinte:</span><span class="sxs-lookup"><span data-stu-id="e4d0b-137">For each unassigned number range that you changed for the outage, run the following:</span></span>
    
        Set-CsUnassignedNumber [-Identity "<name of number range>"] -AnnouncementService "<FQDN of primary pool>" -AnnouncementName "<announcement name in primary pool>"

3.  <span data-ttu-id="e4d0b-138">Opcionalmente, remova os comunicados recriados no pool de backup.</span><span class="sxs-lookup"><span data-stu-id="e4d0b-138">Optionally, remove the announcements that you recreated in the backup pool.</span></span> <span data-ttu-id="e4d0b-139">Obtenha uma lista de comunicados para o aplicativo de anúncio do pool de backup.</span><span class="sxs-lookup"><span data-stu-id="e4d0b-139">Get a list of announcements for the backup pool Announcement application.</span></span> <span data-ttu-id="e4d0b-140">Na linha de comando, execute:</span><span class="sxs-lookup"><span data-stu-id="e4d0b-140">At the command line, run:</span></span>
    
        Get-CsAnnouncement -Identity "<Service:service ID>"
    
    <span data-ttu-id="e4d0b-141">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="e4d0b-141">For example:</span></span>
    
        Get-CsAnnouncement -Identity "ApplicationServer:redmond.contoso.com
    
    <span data-ttu-id="e4d0b-142">Na lista resultante, localize os comunicados que você deseja remover e copie os GUIDs.</span><span class="sxs-lookup"><span data-stu-id="e4d0b-142">In the resulting list, locate the announcements you want to remove and copy the GUIDs.</span></span> <span data-ttu-id="e4d0b-143">Para cada anúncio que você deseja remover, execute:</span><span class="sxs-lookup"><span data-stu-id="e4d0b-143">For each announcement you want to remove, run:</span></span>
    
        Remove-CsAnnouncement -Identity "<Service:service ID/guid>"
    
    <span data-ttu-id="e4d0b-144">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="e4d0b-144">For example:</span></span>
    
        Remove-CsAnnouncement -Identity "ApplicationServer:redmond.contoso.com/1951f734-c80f-4fb2-965d-51807c792b90"


</div>

</div>

<span> </span>

</div>

</div>

</div>

