---
title: 'Lync Server 2013: Suporte a software de banco de dados'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Database software support
ms:assetid: e05d0032-bbea-4e61-987d-d07b1c045fd5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398990(v=OCS.15)
ms:contentKeyID: 48185517
ms.date: 12/02/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8bc8daef764ce5b15fd8c8b7e29f7031ebcfbafc
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34829737"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="database-software-support-in-lync-server-2013"></a><span data-ttu-id="e5e9b-102">Suporte a software de banco de dados no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e5e9b-102">Database software support in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e5e9b-103">_**Tópico da última modificação:** 2014-12-01_</span><span class="sxs-lookup"><span data-stu-id="e5e9b-103">_**Topic Last Modified:** 2014-12-01_</span></span>

<span data-ttu-id="e5e9b-104">O Lync Server 2013 é compatível com os seguintes sistemas de gerenciamento de banco de dados:</span><span class="sxs-lookup"><span data-stu-id="e5e9b-104">Lync Server 2013 supports the following database management systems:</span></span>

  - <span data-ttu-id="e5e9b-105">**Banco de dados Back-end de um pool de Front-End, banco de dados de Arquivamento, banco de dados de Monitoramento, banco de dados de chat persistente e banco de dados de conformidade do chat persistente**</span><span class="sxs-lookup"><span data-stu-id="e5e9b-105">**Back-end database of a Front End pool, Archiving database, Monitoring database, persistent chat database, and persistent chat compliance database**</span></span>
    
      - <span data-ttu-id="e5e9b-p101">Software do banco de dados do Microsoft SQL Server 2008 R2 Enterprise (edição de 64 bits). Além disso, executar o service pack mais atual é recomendado.</span><span class="sxs-lookup"><span data-stu-id="e5e9b-p101">Microsoft SQL Server 2008 R2 Enterprise database software (64-bit edition). Additionally running the latest service pack is recommended.</span></span>
    
      - <span data-ttu-id="e5e9b-108">Microsoft SQL Server 2008 R2 Standard (edição de 64 bits).</span><span class="sxs-lookup"><span data-stu-id="e5e9b-108">Microsoft SQL Server 2008 R2 Standard (64-bit edition).</span></span> <span data-ttu-id="e5e9b-109">Além disso, executar o service pack mais recente é recomendado.</span><span class="sxs-lookup"><span data-stu-id="e5e9b-109">Additionally running the latest service pack is recommended.</span></span>
    
      - <span data-ttu-id="e5e9b-p103">Microsoft SQL Server 2012 Enterprise (edição de 64 bits). Além disso, executar o service pack mais recente é recomendado.</span><span class="sxs-lookup"><span data-stu-id="e5e9b-p103">Microsoft SQL Server 2012 Enterprise (64-bit edition). Additionally running the latest service pack is recommended.</span></span>
    
      - <span data-ttu-id="e5e9b-p104">Microsoft SQL Server 2012 Standard (edição de 64 bits). Além disso, executar o service pack mais recente é recomendado.</span><span class="sxs-lookup"><span data-stu-id="e5e9b-p104">Microsoft SQL Server 2012 Standard (64-bit edition). Additionally running the latest service pack is recommended.</span></span>

  - <span data-ttu-id="e5e9b-114">**Bancos de dados do servidor do servidor de front-end do Standard Edition**</span><span class="sxs-lookup"><span data-stu-id="e5e9b-114">**Standard Edition server database and Front End Server databases**</span></span>
    
      - <span data-ttu-id="e5e9b-115">Microsoft SQL Server 2012 Express (edição de 64 bits).</span><span class="sxs-lookup"><span data-stu-id="e5e9b-115">Microsoft SQL Server 2012 Express (64-bit edition).</span></span> <span data-ttu-id="e5e9b-116">A execução adicional do service pack mais recente é recomendada</span><span class="sxs-lookup"><span data-stu-id="e5e9b-116">Additionally running the latest service pack is recommended.</span></span>
        
        <span data-ttu-id="e5e9b-117">Oferecemos suporte para o patch e a atualização do Microsoft SQL Server em servidores front-end e servidores Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="e5e9b-117">We support the patching and upgrade of Microsoft SQL Server on Front End Servers and Standard Edition servers.</span></span> <span data-ttu-id="e5e9b-118">No entanto, ao fazer qualquer tipo de atualização ou patch em servidores front end, você deve considerar os requisitos de quorum.</span><span class="sxs-lookup"><span data-stu-id="e5e9b-118">However, when you make any kind of upgrade or patch on Front End Servers, you must account for quorum requirements.</span></span> <span data-ttu-id="e5e9b-119">Para mais informações, veja [Upgrade or update Front End Servers in Lync Server 2013](lync-server-2013-upgrade-or-update-front-end-servers.md) e [Topologies and components for Front End Servers, instant messaging, and presence in Lync Server 2013](lync-server-2013-topologies-and-components-for-front-end-servers-instant-messaging-and-presence.md).</span><span class="sxs-lookup"><span data-stu-id="e5e9b-119">For more information, see [Upgrade or update Front End Servers in Lync Server 2013](lync-server-2013-upgrade-or-update-front-end-servers.md) and [Topologies and components for Front End Servers, instant messaging, and presence in Lync Server 2013](lync-server-2013-topologies-and-components-for-front-end-servers-instant-messaging-and-presence.md).</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="e5e9b-120">O Microsoft SQL Server 2012 Express (64-bit Edition) é instalado automaticamente pelo Lync Server 2013 em cada servidor Standard Edition e cada servidor de servidor front-end.</span><span class="sxs-lookup"><span data-stu-id="e5e9b-120">Microsoft SQL Server 2012 Express (64-bit edition) is automatically installed by Lync Server 2013 on each Standard Edition server and each Front End Server server.</span></span>

    
    </div>

<div>


> [!IMPORTANT]  
> <UL>
> <LI>
> <P><span data-ttu-id="e5e9b-121">O Lync Server 2013 não é compatível com a edição de 32 bits do SQL Server.</span><span class="sxs-lookup"><span data-stu-id="e5e9b-121">Lync Server 2013 does not support the 32-bit edition of SQL Server.</span></span> <span data-ttu-id="e5e9b-122">Você deve usar a edição de 64 bits.</span><span class="sxs-lookup"><span data-stu-id="e5e9b-122">You must use the 64-bit edition.</span></span></P>
> <LI>
> <P><span data-ttu-id="e5e9b-123">Não há suporte para SQL Server Web Edition e SQL Server Workgroup Edition.</span><span class="sxs-lookup"><span data-stu-id="e5e9b-123">SQL Server Web edition and SQL Server Workgroup edition are not supported.</span></span> <span data-ttu-id="e5e9b-124">Você não pode usá-los com o Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="e5e9b-124">You cannot use them with Lync Server 2013.</span></span></P>
> <LI>
> <P><span data-ttu-id="e5e9b-125">O Lync Server 2013 suporta o espelhamento de banco de dados nativo.</span><span class="sxs-lookup"><span data-stu-id="e5e9b-125">Lync Server 2013 does support native database mirroring.</span></span></P>
> <LI>
> <P><span data-ttu-id="e5e9b-126">Para usar a função de servidor de monitoramento, você deve instalar o SQL Server Reporting Services.</span><span class="sxs-lookup"><span data-stu-id="e5e9b-126">To use the Monitoring Server role, you should install SQL Server Reporting Services.</span></span></P></LI></UL>



</div>

<span data-ttu-id="e5e9b-127">Em um pool de front-ends, o banco de dados back-end pode ser um único computador SQL Server.</span><span class="sxs-lookup"><span data-stu-id="e5e9b-127">In a Front End pool, the back-end database can be a single SQL Server computer.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="e5e9b-128">Se você colocar bancos de dados do Lync Server com outros bancos de dados, é altamente recomendável avaliar todos os fatores que podem afetar a disponibilidade e o desempenho, além de garantir que, se um nó falhar, o nó restante pode manipular a carga.</span><span class="sxs-lookup"><span data-stu-id="e5e9b-128">If you collocate Lync Server databases with other databases, we highly recommend assessing all factors that might affect availability and performance, as well as ensuring that, if one node fails, the remaining node can handle the load.</span></span> <span data-ttu-id="e5e9b-129">Para verificar as capacidades de failover, recomendamos o teste de todos os cenários de failover.</span><span class="sxs-lookup"><span data-stu-id="e5e9b-129">To verify failover capabilities, we recommend testing all failover scenarios.</span></span>



</div>

<div>

## <a name="using-sql-mirroring-and-sql-clustering"></a><span data-ttu-id="e5e9b-130">Usando o espelhamento SQL e o cluster SQL</span><span class="sxs-lookup"><span data-stu-id="e5e9b-130">Using SQL Mirroring and SQL Clustering</span></span>

<span data-ttu-id="e5e9b-131">O Lync Server 2013 oferece suporte ao uso do SQL Mirroring ou do SQL clustering para cada banco de dados do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="e5e9b-131">Lync Server 2013 supports the use of either SQL mirroring or SQL clustering for each Lync Server database.</span></span> <span data-ttu-id="e5e9b-132">Você pode configurar facilmente o espelhamento do SQL com a ferramenta Construtor de topologias no Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="e5e9b-132">You can easily set up SQL mirroring with the Topology Builder tool in Lync Server 2013.</span></span> <span data-ttu-id="e5e9b-133">Para o cluster de failover SQK, você deve usar o SQL Server para a configuração.</span><span class="sxs-lookup"><span data-stu-id="e5e9b-133">For SQL failover clustering, you must use SQL Server for setup.</span></span>

<span data-ttu-id="e5e9b-134">O Lync Server 2013 oferece suporte ao espelhamento do SQL e às topologias de cluster do SQL para todas as implantações, incluindo implantações e organizações do Greenfield que foram atualizadas a partir de versões anteriores do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="e5e9b-134">Lync Server 2013 supports both SQL mirroring and SQL clustering topologies for all deployments, including greenfield deployments and organizations that have upgraded from previous versions of Lync Server.</span></span>

<span data-ttu-id="e5e9b-p111">O suporte do cluster SQL é para uma configuração ativa/passiva. Por motivos de desempenho, o nó passivo não deve ser compartilhado por nenhuma outra instância SQL.</span><span class="sxs-lookup"><span data-stu-id="e5e9b-p111">SQL Clustering support is for an active/passive configuration. For performance reasons, the passive node should not be shared by any other SQL instance.</span></span>

<span data-ttu-id="e5e9b-137">O suporte a seguir é incluído:</span><span class="sxs-lookup"><span data-stu-id="e5e9b-137">The following support is included:</span></span>

  - <span data-ttu-id="e5e9b-138">Cluster de failover com dois nós para o seguinte:</span><span class="sxs-lookup"><span data-stu-id="e5e9b-138">Two-node failover clustering for the following:</span></span>
    
      - <span data-ttu-id="e5e9b-p112">Microsoft SQL Server 2012 Standard (edição de 64 bits). Além disso, executar o service pack mais recente é recomendado.</span><span class="sxs-lookup"><span data-stu-id="e5e9b-p112">Microsoft SQL Server 2012 Standard (64-bit edition). Additionally running the latest service pack is recommended.</span></span>
    
      - <span data-ttu-id="e5e9b-p113">Microsoft SQL Server 2008 R2 Standard (edição de 64 bits). Além disso, executar o service pack mais recente é recomendado.</span><span class="sxs-lookup"><span data-stu-id="e5e9b-p113">Microsoft SQL Server 2008 R2 Standard (64-bit edition). Additionally running the latest service pack is recommended.</span></span>

  - <span data-ttu-id="e5e9b-143">Cluster de failover com até 16 nós para o seguinte:</span><span class="sxs-lookup"><span data-stu-id="e5e9b-143">Up to sixteen-node failover clustering for the following:</span></span>
    
      - <span data-ttu-id="e5e9b-p114">Microsoft SQL Server 2012 Enterprise (edição de 64 bits). Além disso, executar o service pack mais recente é recomendado.</span><span class="sxs-lookup"><span data-stu-id="e5e9b-p114">Microsoft SQL Server 2012 Enterprise (64-bit edition). Additionally running the latest service pack is recommended.</span></span>
    
      - <span data-ttu-id="e5e9b-p115">Software do banco de dados do Microsoft SQL Server 2008 R2 Enterprise (edição de 64 bits). Além disso, executar o service pack mais atual é recomendado.</span><span class="sxs-lookup"><span data-stu-id="e5e9b-p115">Microsoft SQL Server 2008 R2 Enterprise database software (64-bit edition). Additionally running the latest service pack is recommended.</span></span>

<span data-ttu-id="e5e9b-148">Para obter mais informações sobre o espelhamento do SQL, consulte [back-end Server High Availability in Lync server 2013](lync-server-2013-back-end-server-high-availability.md).</span><span class="sxs-lookup"><span data-stu-id="e5e9b-148">For more information about SQL mirroring, see [Back End Server high availability in Lync Server 2013](lync-server-2013-back-end-server-high-availability.md).</span></span> <span data-ttu-id="e5e9b-149">Para obter detalhes sobre como implantar o SQL clustering, consulte [Configurar o cluster do SQL Server para o Lync Server 2013](lync-server-2013-configure-sql-server-clustering.md).</span><span class="sxs-lookup"><span data-stu-id="e5e9b-149">For details on how to deploy SQL clustering, see [Configure SQL Server clustering for Lync Server 2013](lync-server-2013-configure-sql-server-clustering.md).</span></span>

<span data-ttu-id="e5e9b-150">Para obter mais informações e práticas recomendadas para cluster de failover no SQL Server 2012 <http://technet.microsoft.com/en-us/library/hh231721.aspx>, consulte.</span><span class="sxs-lookup"><span data-stu-id="e5e9b-150">For more information and best practices for failover clustering in SQL Server 2012, see <http://technet.microsoft.com/en-us/library/hh231721.aspx>.</span></span> <span data-ttu-id="e5e9b-151">Para o cluster de failover no SQL Server 2008, <http://technet.microsoft.com/en-us/library/ms189134(v=sql.105).aspx>consulte.</span><span class="sxs-lookup"><span data-stu-id="e5e9b-151">For failover clustering in SQL Server 2008, see <http://technet.microsoft.com/en-us/library/ms189134(v=sql.105).aspx>.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

