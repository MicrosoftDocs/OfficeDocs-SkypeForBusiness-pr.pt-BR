---
title: 'Lync Server 2013: restaurando dados e configurações'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Restoring data and settings
ms:assetid: b07f5dd7-7bed-4819-8cb5-617f5acd478e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202185(v=OCS.15)
ms:contentKeyID: 51541503
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b7562e0899a5129832ef4651c041b8c7daf545e7
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34822388"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="restoring-data-and-settings-in-lync-server-2013"></a><span data-ttu-id="046f1-102">Restaurando dados e configurações no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="046f1-102">Restoring data and settings in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="046f1-103">_**Tópico da última modificação:** 2013-02-17_</span><span class="sxs-lookup"><span data-stu-id="046f1-103">_**Topic Last Modified:** 2013-02-17_</span></span>

<span data-ttu-id="046f1-104">Se você implementou uma topologia de recuperação de desastres com pools emparelhados e um desses pools de front-ends está desativado e você precisa restaurar rapidamente o serviço para seus usuários, consulte [falha em um pool no Lync Server 2013](lync-server-2013-failing-over-a-pool.md).</span><span class="sxs-lookup"><span data-stu-id="046f1-104">If you have implemented a disaster recovery topology with paired pools, and one of those Front End pools has gone down and you need to quickly restore service to your users, see [Failing over a pool in Lync Server 2013](lync-server-2013-failing-over-a-pool.md).</span></span> <span data-ttu-id="046f1-105">Caso contrário, use as informações contidas nos tópicos a seguir, juntamente com as planilhas nas planilhas de [backup e restauração do Lync server 2013](lync-server-2013-backup-and-restoration-worksheets.md), para restaurar o Lync Server após uma falha ou uma falha.</span><span class="sxs-lookup"><span data-stu-id="046f1-105">Otherwise, use the information in the following topics, along with the worksheets in [Backup and restoration worksheets for Lync Server 2013](lync-server-2013-backup-and-restoration-worksheets.md), to restore Lync Server after a failure or outage.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="046f1-106">Para reduzir o tempo de inatividade e a perda de dados potencial, execute os procedimentos de restauração descritos neste documento apenas se os procedimentos de solução de problemas não forem eficazes para identificar e corrigir o problema.</span><span class="sxs-lookup"><span data-stu-id="046f1-106">To reduce downtime and potential data loss, perform the restoration procedures described in this document only if troubleshooting procedures are not effective in identifying and correcting the problem.</span></span> <span data-ttu-id="046f1-107">Durante a solução de problemas, tente minimizar o impacto em outros servidores e componentes ao desligar e reiniciar os servidores.</span><span class="sxs-lookup"><span data-stu-id="046f1-107">During troubleshooting, try to minimize the impact on other servers and components as you shut down and restart servers.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="046f1-108">Nesta seção</span><span class="sxs-lookup"><span data-stu-id="046f1-108">In This Section</span></span>

  - [<span data-ttu-id="046f1-109">Preparando-se para restaurar o Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="046f1-109">Preparing to restore Lync Server 2013</span></span>](lync-server-2013-preparing-to-restore-lync-server.md)

  - [<span data-ttu-id="046f1-110">Restaurando um servidor Standard Edition no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="046f1-110">Restoring a Standard Edition server in Lync Server 2013</span></span>](lync-server-2013-restoring-a-standard-edition-server.md)

  - [<span data-ttu-id="046f1-111">Restaurando o servidor que hospeda o repositório de gerenciamento central no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="046f1-111">Restoring the server hosting the Central Management store in Lync Server 2013</span></span>](lync-server-2013-restoring-the-server-hosting-the-central-management-store.md)

  - [<span data-ttu-id="046f1-112">Restaurando um servidor back-end do Enterprise Edition no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="046f1-112">Restoring an Enterprise Edition Back End Server in Lync Server 2013</span></span>](lync-server-2013-restoring-an-enterprise-edition-back-end-server.md)

  - [<span data-ttu-id="046f1-113">Restaurando um servidor membro da Enterprise Edition no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="046f1-113">Restoring an Enterprise Edition member server in Lync Server 2013</span></span>](lync-server-2013-restoring-an-enterprise-edition-member-server.md)

  - [<span data-ttu-id="046f1-114">Restaurando um pool do Lync Server no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="046f1-114">Restoring a Lync Server pool in Lync Server 2013</span></span>](lync-server-2013-restoring-a-lync-server-pool.md)

  - [<span data-ttu-id="046f1-115">Executar um failover de pool de front-end da ABC no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="046f1-115">Performing an ABC Front End pool failover in Lync Server 2013</span></span>](lync-server-2013-performing-an-abc-front-end-pool-failover.md)

  - [<span data-ttu-id="046f1-116">Restaurando um armazenamento de arquivos no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="046f1-116">Restoring a file store in Lync Server 2013</span></span>](lync-server-2013-restoring-a-file-store.md)

  - [<span data-ttu-id="046f1-117">Restaurando o monitoramento ou arquivando dados no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="046f1-117">Restoring monitoring or archiving data in Lync Server 2013</span></span>](lync-server-2013-restoring-monitoring-or-archiving-data.md)

  - [<span data-ttu-id="046f1-118">Restaurando dados de chat persistente no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="046f1-118">Restoring Persistent Chat data in Lync Server 2013</span></span>](lync-server-2013-restoring-persistent-chat-data.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

