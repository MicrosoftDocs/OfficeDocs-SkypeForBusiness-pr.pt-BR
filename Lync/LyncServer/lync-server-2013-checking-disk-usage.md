---
title: 'Lync Server 2013: verificando o uso do disco'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Checking disk usage
ms:assetid: 0f0cb9bf-3f11-43ff-be10-5c8e1b5c4f08
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720908(v=OCS.15)
ms:contentKeyID: 63969578
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8532b15ac45033d966c772e6ab23403d709ed790
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42045673"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="checking-disk-usage-in-lync-server-2013"></a><span data-ttu-id="bdbc8-102">Verificar o uso do disco no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="bdbc8-102">Checking disk usage in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="bdbc8-103">_**Última modificação do tópico:** 2014-04-30_</span><span class="sxs-lookup"><span data-stu-id="bdbc8-103">_**Topic Last Modified:** 2014-04-30_</span></span>

<span data-ttu-id="bdbc8-104">Unidades de discos rígidos são um componente importante da implantação do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="bdbc8-104">Hard disks drives are an important component of the Lync Server 2013 deployment.</span></span> <span data-ttu-id="bdbc8-105">Sem um volume de disco livre suficiente, nem os bancos de dados do sistema operacional nem do Lync Server 2013 podem funcionar corretamente.</span><span class="sxs-lookup"><span data-stu-id="bdbc8-105">Without sufficient free disk volume, neither the operating system nor the Lync Server 2013 databases can function correctly.</span></span> <span data-ttu-id="bdbc8-106">Você deve monitorar as estatísticas de banco de dados de back-end do Lync Server 2013 diariamente para ajudar a garantir que os servidores não fique sem espaço em disco e para se preparar para adicionar recursos de armazenamento conforme necessário.</span><span class="sxs-lookup"><span data-stu-id="bdbc8-106">You must monitor the Lync Server 2013 back-end database statistics daily to help to make sure that servers do not run out of disk space, and to prepare to add storage resources as required.</span></span>

<span data-ttu-id="bdbc8-107">Além de verificar o espaço em discos que hospedam o sistema operacional, arquivos de programas, bancos de dados e logs de transações (Lync Server 2013 back-end), você também deve monitorar o uso do sistema de arquivos que inclui o espaço em disco para compartilhamentos de arquivos que contenham as seguintes importantes os</span><span class="sxs-lookup"><span data-stu-id="bdbc8-107">Apart from checking space on disks hosting the operating system, program files, database, and transaction logs (Lync Server 2013 Back End), you should also monitor usage of the file system that includes disk space for file shares that contain the following important data:</span></span>

  - <span data-ttu-id="bdbc8-108">Conteúdo de reunião</span><span class="sxs-lookup"><span data-stu-id="bdbc8-108">Meeting content</span></span>

  - <span data-ttu-id="bdbc8-109">Metadados de conteúdo da reunião</span><span class="sxs-lookup"><span data-stu-id="bdbc8-109">Meeting content metadata</span></span>

  - <span data-ttu-id="bdbc8-110">Cumprir logs de conformidade</span><span class="sxs-lookup"><span data-stu-id="bdbc8-110">Meeting compliance logs</span></span>

  - <span data-ttu-id="bdbc8-111">Arquivos de dados de aplicativo (usados internamente pelo componente de servidor de aplicativos)</span><span class="sxs-lookup"><span data-stu-id="bdbc8-111">Application data files (used internally by the application server component)</span></span>

  - <span data-ttu-id="bdbc8-112">Serviço Web de servidor de chat de grupo e pastas de conformidade (para armazenar arquivos carregados no serviço Web de chat de grupo)</span><span class="sxs-lookup"><span data-stu-id="bdbc8-112">Group Chat Server web service and compliance folders (to store files uploaded to the Group Chat web service)</span></span>

  - <span data-ttu-id="bdbc8-113">Arquivos XML de conformidade de chat de grupo (que contêm registros de conformidade de chat de grupo)</span><span class="sxs-lookup"><span data-stu-id="bdbc8-113">Group Chat compliance XML files (that contain Group Chat compliance records)</span></span>

  - <span data-ttu-id="bdbc8-114">Atualizar arquivos (para o serviço de atualização de dispositivo)</span><span class="sxs-lookup"><span data-stu-id="bdbc8-114">Update files (for Device Update Service)</span></span>

  - <span data-ttu-id="bdbc8-115">Arquivos de Catálogo de endereços</span><span class="sxs-lookup"><span data-stu-id="bdbc8-115">Address Book files</span></span>

<span data-ttu-id="bdbc8-116">O Lync Server 2013 precisa de espaço em disco rígido para armazenar seus bancos de dados e logs de transações, além de arquivos em compartilhamentos de arquivos listados anteriormente.</span><span class="sxs-lookup"><span data-stu-id="bdbc8-116">Lync Server 2013 needs hard disk space to store its databases and transaction logs in addition to files on file shares previously listed.</span></span>

<span data-ttu-id="bdbc8-117">Você deve monitorar o espaço em disco regularmente para ajudar a garantir que a implantação do Lync Server 2013 não seja prejudicada devido a recursos de armazenamento insuficientes.</span><span class="sxs-lookup"><span data-stu-id="bdbc8-117">You should monitor the disk space regularly to help to make sure that the Lync Server 2013 deployment is not adversely affected because of insufficient storage resources.</span></span>

<span data-ttu-id="bdbc8-118">Comparar e manter informações estatísticas sobre o espaço em disco disponível em cada volume do Lync Server 2013 e o crescimento esperado dos arquivos de log de transações e bancos de dados.</span><span class="sxs-lookup"><span data-stu-id="bdbc8-118">Compare and maintain statistical information about available disk space on each Lync Server 2013 volume and expected growth of the databases and transaction log files.</span></span> <span data-ttu-id="bdbc8-119">Isso ajuda no planejamento da capacidade e na adição de armazenamento quando os recursos de armazenamento são necessários.</span><span class="sxs-lookup"><span data-stu-id="bdbc8-119">This helps with capacity planning and adding storage when the storage resources are required.</span></span>

<span data-ttu-id="bdbc8-120">Para acomodar as situações de solução de problemas e recuperação de desastre, recomendamos que o espaço disponível no volume seja igual ou maior que 110 por cento do tamanho do banco de dados.</span><span class="sxs-lookup"><span data-stu-id="bdbc8-120">To accommodate troubleshooting and disaster recovery situations, we recommend that available free volume space be equal or greater than 110 percent of the size of database.</span></span>

<span data-ttu-id="bdbc8-121">Você pode verificar o espaço em disco usando os métodos a seguir:</span><span class="sxs-lookup"><span data-stu-id="bdbc8-121">You can check free disk space by using the following methods:</span></span>

1.  <span data-ttu-id="bdbc8-122">**O System Center Operations Manager**   System Center Operations Manager pode ser usado para avisar aos administradores quando o espaço do volume é restrito.</span><span class="sxs-lookup"><span data-stu-id="bdbc8-122">**System Center Operations Manager**   System Center Operations Manager can be used to warn administrators when volume space is constrained.</span></span>

2.  <span data-ttu-id="bdbc8-123">**Executar um script**   monitor Disk Space executando um script que envia uma mensagem se o espaço disponível no disco rígido estiver abaixo de 20 por cento.</span><span class="sxs-lookup"><span data-stu-id="bdbc8-123">**Running a script**   Monitor disk space by running a script that sends you a message if the available hard disk space falls below 20 percent.</span></span> <span data-ttu-id="bdbc8-124">Você pode encontrar um script de exemplo no Microsoft Script Center no TechNet, examinar:[http://gallery.technet.microsoft.com/scriptcenter/site/search?query=hard%20disk%20alert\&f%5B0%5D.Value=hard%20disk%20alert\&f%5B0%5D.Type=SearchText\&ac=5](http://gallery.technet.microsoft.com/scriptcenter/site/search?query=hard+disk+alert%26f%5b0%5d.value=hard+disk+alert%26f%5b0%5d.type=searchtext%26ac=5)</span><span class="sxs-lookup"><span data-stu-id="bdbc8-124">You can find a sample script on Microsoft Script Center on TechNet, examine: [http://gallery.technet.microsoft.com/scriptcenter/site/search?query=hard%20disk%20alert\&f%5B0%5D.Value=hard%20disk%20alert\&f%5B0%5D.Type=SearchText\&ac=5](http://gallery.technet.microsoft.com/scriptcenter/site/search?query=hard+disk+alert%26f%5b0%5d.value=hard+disk+alert%26f%5b0%5d.type=searchtext%26ac=5)</span></span>

3.  <span data-ttu-id="bdbc8-125">**O Windows Explorer**   usa o Windows Explorer para verificar o espaço em disco em volumes que armazenam logs e bancos de dados do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="bdbc8-125">**Windows Explorer**   Use Windows Explorer to check for disk space on volumes that store Lync Server 2013 logs and databases.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

