---
title: 'Lync Server 2013: gerenciar comunicados durante recuperação de desastre'
description: 'Lync Server 2013: gerenciar comunicados durante a recuperação de desastre.'
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
ms.openlocfilehash: d85dfcd15c9c3650bafafa6fa7702e19ac9c4f7d
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48550627"
---
# <a name="manage-announcements-during-disaster-recovery-in-lync-server-2013"></a><span data-ttu-id="d5d4d-103">Gerenciar comunicados durante recuperação de desastre no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d5d4d-103">Manage announcements during disaster recovery in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d5d4d-104">_**Última modificação do tópico:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="d5d4d-104">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="d5d4d-105">O Lync Server 2013 oferece suporte a comunicados para chamadas de números não atribuídos durante interrupções.</span><span class="sxs-lookup"><span data-stu-id="d5d4d-105">Lync Server 2013 supports announcements for calls to unassigned numbers during outages.</span></span> <span data-ttu-id="d5d4d-106">Restaurar a funcionalidade de anúncio durante uma interrupção é opcional.</span><span class="sxs-lookup"><span data-stu-id="d5d4d-106">Restoring announcement functionality during an outage is optional.</span></span> <span data-ttu-id="d5d4d-107">Se você escolher restaurar anúncios durante uma interrupção, é necessário recriar sua configuração de anúncio no pool de backup.</span><span class="sxs-lookup"><span data-stu-id="d5d4d-107">If you choose to restore announcements during an outage, you need recreate your announcement configuration in the backup pool.</span></span> <span data-ttu-id="d5d4d-108">Esta seção descreve o que você precisa fazer se escolher restaurar anúncios durante a recuperação de desastres.</span><span class="sxs-lookup"><span data-stu-id="d5d4d-108">This section describes what you need to do if you choose to restore announcements during disaster recovery.</span></span>

<span data-ttu-id="d5d4d-109">Esta seção se aplica a intervalos de números não atribuídos que usam o aplicativo comunicado.</span><span class="sxs-lookup"><span data-stu-id="d5d4d-109">This section applies to unassigned number ranges that use the Announcement application.</span></span> <span data-ttu-id="d5d4d-110">Esta seção não se aplica ao intervalo de números não atribuídos que usam o Atendedor Automático do Exchange Unified Messaging (UM).</span><span class="sxs-lookup"><span data-stu-id="d5d4d-110">This section does not apply to unassigned number ranges that use Exchange Unified Messaging (UM) Auto Attendant.</span></span>

<div>

## <a name="before-an-outage"></a><span data-ttu-id="d5d4d-111">Antes de uma interrupção</span><span class="sxs-lookup"><span data-stu-id="d5d4d-111">Before an Outage</span></span>

<span data-ttu-id="d5d4d-112">Independentemente de você optar por usar comunicados durante as interrupções, você deve fazer backups separados de qualquer arquivo de áudio personalizado que você configurou para o aplicativo de comunicado.</span><span class="sxs-lookup"><span data-stu-id="d5d4d-112">Regardless of whether you choose to use announcements during outages, you should take separate backups of any customized audio files that you configured for the Announcement application.</span></span> <span data-ttu-id="d5d4d-113">Não é feito backup dos comunicados personalizados como parte do processo de recuperação de desastres do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="d5d4d-113">Customized announcements are not backed up as part of the Lync Server disaster recovery process.</span></span> <span data-ttu-id="d5d4d-114">Se você não realizar backups separados dos arquivos e os arquivos que você carregou ao servidor ou pool estão danificados, corrompidos ou apagados, os arquivos serão perdidos.</span><span class="sxs-lookup"><span data-stu-id="d5d4d-114">If you do not take separate backups of the files and the files that you uploaded to the server or pool are damaged, corrupted, or erased, the files will be lost.</span></span>

<span data-ttu-id="d5d4d-115">Se você não tem cópias de backup de arquivos de áudio personalizados e os arquivos de áudio originais não estão mais disponíveis, você pode encontrar os arquivos de áudio que você configurou para um aplicativo de anúncio, procurando no repositório de arquivos do servidor ou pool em que você importou originalmente os arquivos.</span><span class="sxs-lookup"><span data-stu-id="d5d4d-115">If you do not have backup copies of customized audio files, and the original audio files are no longer available, you can find the audio files that you configured for an Announcement application by looking in the File Store for the server or pool where you originally imported the files.</span></span> <span data-ttu-id="d5d4d-116">Você pode copiar todos os arquivos de áudio que você configurou para o aplicativo de anúncio no repositório de arquivos.</span><span class="sxs-lookup"><span data-stu-id="d5d4d-116">You can copy all the audio files that you configured for the Announcement application from the File Store.</span></span>

<span data-ttu-id="d5d4d-117">**Para copiar arquivos de áudio do repositório de arquivos**</span><span class="sxs-lookup"><span data-stu-id="d5d4d-117">**To copy audio files from the file store**</span></span>

1.  <span data-ttu-id="d5d4d-118">Na linha de comando, execute:</span><span class="sxs-lookup"><span data-stu-id="d5d4d-118">At the command line, run:</span></span>
    
        Xcopy <Source: Pool Announcement Service File Store path> <Destination>
    
    <span data-ttu-id="d5d4d-119">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="d5d4d-119">For example:</span></span>
    
        Xcopy "<Pool File Store Path>\X-ApplicationServer-X\AppServerFiles\RGS\AS" "<Destination: Backup location>"
    
    <span data-ttu-id="d5d4d-120">Onde X-ApplicationServer-X refere-se à ID de serviço do Servidor de Aplicativos do pool (por exemplo, 1-ApplicationServer-1")</span><span class="sxs-lookup"><span data-stu-id="d5d4d-120">Where X-ApplicationServer-X refers to the service ID of the Application Server of the pool (for example, 1-ApplicationServer-1")</span></span>


</div>

<div>

## <a name="during-an-outage"></a><span data-ttu-id="d5d4d-121">Durante uma interrupção</span><span class="sxs-lookup"><span data-stu-id="d5d4d-121">During an Outage</span></span>

<span data-ttu-id="d5d4d-122">Para usar o aplicativo de comunicado durante uma interrupção, você precisa recriar a configuração do comunicado no pool de backup executando as tarefas descritas nesta seção.</span><span class="sxs-lookup"><span data-stu-id="d5d4d-122">To use the Announcement application during an outage, you need to recreate the announcement configuration in the backup pool by performing the tasks described in this section.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="d5d4d-123">Recomendamos realizar estas tarefas se você falhar no pool de backup, porque assim que você realizar a etapa 2, o pool de backup tem propriedade dos intervalos de número não atribuídos.</span><span class="sxs-lookup"><span data-stu-id="d5d4d-123">We recommend that you perform these tasks after you fail over to the backup pool, because as soon as you perform step 2, the backup pool takes ownership of the unassigned number ranges.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="d5d4d-124">Estas etapas não são obrigatórias para intervalos de número que usam um número de telefone do Atendedor Automático do Exchange UM.</span><span class="sxs-lookup"><span data-stu-id="d5d4d-124">These steps are not required for number ranges that use an Exchange UM Auto Attendant phone number.</span></span>



</div>

<span data-ttu-id="d5d4d-125">**Para recriar a configuração do comunicado no pool de backup**</span><span class="sxs-lookup"><span data-stu-id="d5d4d-125">**To recreate the announcement configuration in the backup pool**</span></span>

1.  <span data-ttu-id="d5d4d-126">Recrie os anúncios que você implantou no pool primário no pool de backup fazendo o seguinte:</span><span class="sxs-lookup"><span data-stu-id="d5d4d-126">Recreate the announcements that you deployed in the primary pool in the backup pool by doing the following:</span></span>
    
    1.  <span data-ttu-id="d5d4d-127">Importe qualquer arquivo de áudio usado no pool primário para o pool de backup usando o cmdlet **Import-CsAnnouncementFile** e especificando o pool de backup para o parâmetro Parent.</span><span class="sxs-lookup"><span data-stu-id="d5d4d-127">Import any audio files used in the primary pool to the backup pool by using the **Import-CsAnnouncementFile** cmdlet and specifying the backup pool for the Parent parameter.</span></span>
    
    2.  <span data-ttu-id="d5d4d-128">Recriar cada anúncio usando o cmdlet **New-CsAnnouncement** e especificando o pool de backup para o parâmetro Parent.</span><span class="sxs-lookup"><span data-stu-id="d5d4d-128">Recreate each announcement by using the **New-CsAnnouncement** cmdlet and specifying the backup pool for the Parent parameter.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="d5d4d-129">Para obter detalhes sobre como usar esses parâmetros para criar comunicados no pool de backup, consulte <A href="lync-server-2013-create-an-announcement.md">criar um anúncio no Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="d5d4d-129">For details about using these parameters to create announcements in the backup pool, see <A href="lync-server-2013-create-an-announcement.md">Create an announcement in Lync Server 2013</A>.</span></span>

    
    </div>

2.  <span data-ttu-id="d5d4d-130">Após todos os anúncios serem recriados no pool de backup, redirecione todos os intervalos de número não atribuídos que usam anúncios no pool primário para os anúncios recriados no pool de backup.</span><span class="sxs-lookup"><span data-stu-id="d5d4d-130">After all announcements are recreated in the backup pool, redirect all the unassigned number ranges that use announcements in the primary pool to the recreated announcements in the backup pool.</span></span>
    
    <span data-ttu-id="d5d4d-131">Para cada intervalo de número não atribuído que usa um anúncio no pool primário, execute o seguinte:</span><span class="sxs-lookup"><span data-stu-id="d5d4d-131">For each unassigned number range that uses an announcement in the primary pool, run the following:</span></span>
    
        Set-CsUnassignedNumber -Identity "<name of number range>" -AnnouncementService "<FQDN of backup pool>" -AnnouncementName "<announcement name in backup pool>"

</div>

<div>

## <a name="after-the-outage"></a><span data-ttu-id="d5d4d-132">Após a interrupção</span><span class="sxs-lookup"><span data-stu-id="d5d4d-132">After the Outage</span></span>

<span data-ttu-id="d5d4d-133">Quando o pool primário se torna disponível, você precisa redirecionar os intervalos de número não atribuídos que você alterou para a interrupção de volta para o pool primário.</span><span class="sxs-lookup"><span data-stu-id="d5d4d-133">When the primary pool becomes available, you need to redirect the unassigned number ranges that you changed for the outage back to the primary pool.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="d5d4d-134">Estas etapas não são necessárias para intervalos de número que usam um número de telefone do Atendedor Automático do Exchange UM.</span><span class="sxs-lookup"><span data-stu-id="d5d4d-134">These steps are not required for number ranges that use an Exchange UM Auto Attendant phone number.</span></span>



</div>

<span data-ttu-id="d5d4d-135">**Para restaurar comunicados no pool primário**</span><span class="sxs-lookup"><span data-stu-id="d5d4d-135">**To restore announcements in the primary pool**</span></span>

1.  <span data-ttu-id="d5d4d-p105">Se você precisa reconstruir o pool primário durante a recuperação, é necessário recriar os anúncios no pool primário importando os arquivos de áudio e criando anúncios, assim como você faria no pool de backup, exceto que você especifica o pool primário para o parâmetro Parent. Para obter detalhes, consulte "Durante uma interrupção" anteriormente neste tópico.</span><span class="sxs-lookup"><span data-stu-id="d5d4d-p105">If you had to rebuild the primary pool during the recovery, you need to recreate the announcements in the primary pool by importing the audio files and creating announcements, just as you did in the backup pool, except that you specify the primary pool for the Parent parameter. For details, see "During an Outage" earlier in this topic.</span></span>

2.  <span data-ttu-id="d5d4d-138">Para cada intervalo de número não atribuído que você alterou para a interrupção, execute o seguinte:</span><span class="sxs-lookup"><span data-stu-id="d5d4d-138">For each unassigned number range that you changed for the outage, run the following:</span></span>
    
        Set-CsUnassignedNumber [-Identity "<name of number range>"] -AnnouncementService "<FQDN of primary pool>" -AnnouncementName "<announcement name in primary pool>"

3.  <span data-ttu-id="d5d4d-139">Opcionalmente, remova os anúncios recriados no pool de backup.</span><span class="sxs-lookup"><span data-stu-id="d5d4d-139">Optionally, remove the announcements that you recreated in the backup pool.</span></span> <span data-ttu-id="d5d4d-140">Obtenha uma lista de comunicados para o aplicativo de anúncio do pool de backup.</span><span class="sxs-lookup"><span data-stu-id="d5d4d-140">Get a list of announcements for the backup pool Announcement application.</span></span> <span data-ttu-id="d5d4d-141">Na linha de comando, execute:</span><span class="sxs-lookup"><span data-stu-id="d5d4d-141">At the command line, run:</span></span>
    
        Get-CsAnnouncement -Identity "<Service:service ID>"
    
    <span data-ttu-id="d5d4d-142">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="d5d4d-142">For example:</span></span>
    
        Get-CsAnnouncement -Identity "ApplicationServer:redmond.contoso.com
    
    <span data-ttu-id="d5d4d-p107">Na lista resultante, localize os anúncios que deseja remover e copie os GUIDs. Para cada anúncio que deseja remover, execute:</span><span class="sxs-lookup"><span data-stu-id="d5d4d-p107">In the resulting list, locate the announcements you want to remove and copy the GUIDs. For each announcement you want to remove, run:</span></span>
    
        Remove-CsAnnouncement -Identity "<Service:service ID/guid>"
    
    <span data-ttu-id="d5d4d-145">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="d5d4d-145">For example:</span></span>
    
        Remove-CsAnnouncement -Identity "ApplicationServer:redmond.contoso.com/1951f734-c80f-4fb2-965d-51807c792b90"


</div>

</div>

<span> </span>

</div>

</div>

</div>

