---
title: Suporte para software de banco de dados do Lync Server 2013
description: Suporte para software de banco de dados do Lync Server 2013.
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Database software support
ms:assetid: e05d0032-bbea-4e61-987d-d07b1c045fd5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398990(v=OCS.15)
ms:contentKeyID: 48185517
ms.date: 12/02/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1c5d7b44e5febc4123dbcdf7072b98fcfd004609
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48558147"
---
# <a name="database-software-support-in-lync-server-2013"></a><span data-ttu-id="37c50-103">Suporte a software de banco de dados no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="37c50-103">Database software support in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="37c50-104">_**Última modificação do tópico:** 2014-12-01_</span><span class="sxs-lookup"><span data-stu-id="37c50-104">_**Topic Last Modified:** 2014-12-01_</span></span>

<span data-ttu-id="37c50-105">O Lync Server 2013 oferece suporte aos seguintes sistemas de gerenciamento de banco de dados:</span><span class="sxs-lookup"><span data-stu-id="37c50-105">Lync Server 2013 supports the following database management systems:</span></span>

  - <span data-ttu-id="37c50-106">**Banco de dados back-end de um pool Front-end, banco de dados de arquivamento, banco de dados de monitoramento, banco de dados de chat persistente e banco de dados de conformidade**</span><span class="sxs-lookup"><span data-stu-id="37c50-106">**Back-end database of a Front End pool, Archiving database, Monitoring database, persistent chat database, and persistent chat compliance database**</span></span>
    
      - <span data-ttu-id="37c50-107">Software de banco de dados corporativo do Microsoft SQL Server 2008 R2 (64-bit Edition).</span><span class="sxs-lookup"><span data-stu-id="37c50-107">Microsoft SQL Server 2008 R2 Enterprise database software (64-bit edition).</span></span> <span data-ttu-id="37c50-108">É recomendável executar adicionalmente o Service Pack mais recente.</span><span class="sxs-lookup"><span data-stu-id="37c50-108">Additionally running the latest service pack is recommended.</span></span>
    
      - <span data-ttu-id="37c50-109">Microsoft SQL Server 2008 R2 Standard (64-bit Edition).</span><span class="sxs-lookup"><span data-stu-id="37c50-109">Microsoft SQL Server 2008 R2 Standard (64-bit edition).</span></span> <span data-ttu-id="37c50-110">É recomendável executar adicionalmente o Service Pack mais recente.</span><span class="sxs-lookup"><span data-stu-id="37c50-110">Additionally running the latest service pack is recommended.</span></span>
    
      - <span data-ttu-id="37c50-111">Microsoft SQL Server 2012 Enterprise (64-bit Edition).</span><span class="sxs-lookup"><span data-stu-id="37c50-111">Microsoft SQL Server 2012 Enterprise (64-bit edition).</span></span> <span data-ttu-id="37c50-112">É recomendável executar adicionalmente o Service Pack mais recente.</span><span class="sxs-lookup"><span data-stu-id="37c50-112">Additionally running the latest service pack is recommended.</span></span>
    
      - <span data-ttu-id="37c50-113">Microsoft SQL Server 2012 Standard (edição de 64 bits).</span><span class="sxs-lookup"><span data-stu-id="37c50-113">Microsoft SQL Server 2012 Standard (64-bit edition).</span></span> <span data-ttu-id="37c50-114">É recomendável executar adicionalmente o Service Pack mais recente.</span><span class="sxs-lookup"><span data-stu-id="37c50-114">Additionally running the latest service pack is recommended.</span></span>

  - <span data-ttu-id="37c50-115">**Bancos de dados do servidor do Standard Edition e do servidor front-end**</span><span class="sxs-lookup"><span data-stu-id="37c50-115">**Standard Edition server database and Front End Server databases**</span></span>
    
      - <span data-ttu-id="37c50-116">Microsoft SQL Server 2012 Express (64-bit Edition).</span><span class="sxs-lookup"><span data-stu-id="37c50-116">Microsoft SQL Server 2012 Express (64-bit edition).</span></span> <span data-ttu-id="37c50-117">É recomendável executar adicionalmente o Service Pack mais recente.</span><span class="sxs-lookup"><span data-stu-id="37c50-117">Additionally running the latest service pack is recommended.</span></span>
        
        <span data-ttu-id="37c50-118">Oferecemos suporte para a aplicação de patch e atualização do Microsoft SQL Server em servidores front-end e servidores Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="37c50-118">We support the patching and upgrade of Microsoft SQL Server on Front End Servers and Standard Edition servers.</span></span> <span data-ttu-id="37c50-119">No entanto, ao fazer qualquer tipo de atualização ou patch em servidores front-end, você deve considerar os requisitos de quorum.</span><span class="sxs-lookup"><span data-stu-id="37c50-119">However, when you make any kind of upgrade or patch on Front End Servers, you must account for quorum requirements.</span></span> <span data-ttu-id="37c50-120">Para obter mais informações, consulte [atualizar ou atualizar servidores front-end no Lync Server 2013](lync-server-2013-upgrade-or-update-front-end-servers.md) e [topologias e componentes para servidores front-end, mensagens instantâneas e presença no Lync Server 2013](lync-server-2013-topologies-and-components-for-front-end-servers-instant-messaging-and-presence.md).</span><span class="sxs-lookup"><span data-stu-id="37c50-120">For more information, see [Upgrade or update Front End Servers in Lync Server 2013](lync-server-2013-upgrade-or-update-front-end-servers.md) and [Topologies and components for Front End Servers, instant messaging, and presence in Lync Server 2013](lync-server-2013-topologies-and-components-for-front-end-servers-instant-messaging-and-presence.md).</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="37c50-121">O Microsoft SQL Server 2012 Express (64-bit Edition) é instalado automaticamente pelo Lync Server 2013 em cada servidor Standard Edition e cada servidor de servidor front-end.</span><span class="sxs-lookup"><span data-stu-id="37c50-121">Microsoft SQL Server 2012 Express (64-bit edition) is automatically installed by Lync Server 2013 on each Standard Edition server and each Front End Server server.</span></span>

    
    </div>

<div>


> [!IMPORTANT]  
> <UL>
> <LI>
> <P><span data-ttu-id="37c50-122">O Lync Server 2013 não dá suporte à edição de 32 bits do SQL Server.</span><span class="sxs-lookup"><span data-stu-id="37c50-122">Lync Server 2013 does not support the 32-bit edition of SQL Server.</span></span> <span data-ttu-id="37c50-123">Você deve usar a edição de 64 bits.</span><span class="sxs-lookup"><span data-stu-id="37c50-123">You must use the 64-bit edition.</span></span></P>
> <LI>
> <P><span data-ttu-id="37c50-124">O SQL Server Web Edition e o SQL Server Workgroup Edition não têm suporte.</span><span class="sxs-lookup"><span data-stu-id="37c50-124">SQL Server Web edition and SQL Server Workgroup edition are not supported.</span></span> <span data-ttu-id="37c50-125">Você não pode usá-los com o Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="37c50-125">You cannot use them with Lync Server 2013.</span></span></P>
> <LI>
> <P><span data-ttu-id="37c50-126">O Lync Server 2013 oferece suporte a espelhamento de banco de dados nativo.</span><span class="sxs-lookup"><span data-stu-id="37c50-126">Lync Server 2013 does support native database mirroring.</span></span></P>
> <LI>
> <P><span data-ttu-id="37c50-127">Para usar a função de servidor de monitoramento, você deve instalar o SQL Server Reporting Services.</span><span class="sxs-lookup"><span data-stu-id="37c50-127">To use the Monitoring Server role, you should install SQL Server Reporting Services.</span></span></P></LI></UL>



</div>

<span data-ttu-id="37c50-128">Em um pool de front-ends, o banco de dados back-end pode ser um único computador do SQL Server.</span><span class="sxs-lookup"><span data-stu-id="37c50-128">In a Front End pool, the back-end database can be a single SQL Server computer.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="37c50-129">Se você colocar os bancos de dados do Lync Server com outros bancos de dados, é altamente recomendável avaliar todos os fatores que podem afetar a disponibilidade e o desempenho, além de garantir que, se um nó falhar, o nó restante poderá lidar com a carga.</span><span class="sxs-lookup"><span data-stu-id="37c50-129">If you collocate Lync Server databases with other databases, we highly recommend assessing all factors that might affect availability and performance, as well as ensuring that, if one node fails, the remaining node can handle the load.</span></span> <span data-ttu-id="37c50-130">Para verificar os recursos de failover, é recomendável testar todos os cenários de failover.</span><span class="sxs-lookup"><span data-stu-id="37c50-130">To verify failover capabilities, we recommend testing all failover scenarios.</span></span>



</div>

<div>

## <a name="using-sql-mirroring-and-sql-clustering"></a><span data-ttu-id="37c50-131">Usando o espelhamento do SQL e o cluster SQL</span><span class="sxs-lookup"><span data-stu-id="37c50-131">Using SQL Mirroring and SQL Clustering</span></span>

<span data-ttu-id="37c50-132">O Lync Server 2013 oferece suporte ao uso de espelhamento de SQL ou de SQL para cada banco de dados do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="37c50-132">Lync Server 2013 supports the use of either SQL mirroring or SQL clustering for each Lync Server database.</span></span> <span data-ttu-id="37c50-133">Você pode configurar facilmente o espelhamento do SQL com a ferramenta Construtor de topologia no Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="37c50-133">You can easily set up SQL mirroring with the Topology Builder tool in Lync Server 2013.</span></span> <span data-ttu-id="37c50-134">Para o cluster de failover do SQL, você deve usar o SQL Server para configuração.</span><span class="sxs-lookup"><span data-stu-id="37c50-134">For SQL failover clustering, you must use SQL Server for setup.</span></span>

<span data-ttu-id="37c50-135">O Lync Server 2013 oferece suporte a topologias de espelhamento do SQL e de cluster SQL para todas as implantações, incluindo implantações e organizações do Greenfield que tenham sido atualizadas de versões anteriores do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="37c50-135">Lync Server 2013 supports both SQL mirroring and SQL clustering topologies for all deployments, including greenfield deployments and organizations that have upgraded from previous versions of Lync Server.</span></span>

<span data-ttu-id="37c50-136">O suporte a clusters do SQL é para uma configuração ativa/passiva.</span><span class="sxs-lookup"><span data-stu-id="37c50-136">SQL Clustering support is for an active/passive configuration.</span></span> <span data-ttu-id="37c50-137">Por motivos de desempenho, o nó passivo não deve ser compartilhado por nenhuma outra instância do SQL.</span><span class="sxs-lookup"><span data-stu-id="37c50-137">For performance reasons, the passive node should not be shared by any other SQL instance.</span></span>

<span data-ttu-id="37c50-138">O suporte a seguir está incluído:</span><span class="sxs-lookup"><span data-stu-id="37c50-138">The following support is included:</span></span>

  - <span data-ttu-id="37c50-139">Clustering de failover de dois nós para o seguinte:</span><span class="sxs-lookup"><span data-stu-id="37c50-139">Two-node failover clustering for the following:</span></span>
    
      - <span data-ttu-id="37c50-140">Microsoft SQL Server 2012 Standard (edição de 64 bits).</span><span class="sxs-lookup"><span data-stu-id="37c50-140">Microsoft SQL Server 2012 Standard (64-bit edition).</span></span> <span data-ttu-id="37c50-141">É recomendável executar adicionalmente o Service Pack mais recente.</span><span class="sxs-lookup"><span data-stu-id="37c50-141">Additionally running the latest service pack is recommended.</span></span>
    
      - <span data-ttu-id="37c50-142">Microsoft SQL Server 2008 R2 Standard (64-bit Edition).</span><span class="sxs-lookup"><span data-stu-id="37c50-142">Microsoft SQL Server 2008 R2 Standard (64-bit edition).</span></span> <span data-ttu-id="37c50-143">É recomendável executar adicionalmente o Service Pack mais recente.</span><span class="sxs-lookup"><span data-stu-id="37c50-143">Additionally running the latest service pack is recommended.</span></span>

  - <span data-ttu-id="37c50-144">Clustering de failover de até dezesseis nós para o seguinte:</span><span class="sxs-lookup"><span data-stu-id="37c50-144">Up to sixteen-node failover clustering for the following:</span></span>
    
      - <span data-ttu-id="37c50-145">Microsoft SQL Server 2012 Enterprise (64-bit Edition).</span><span class="sxs-lookup"><span data-stu-id="37c50-145">Microsoft SQL Server 2012 Enterprise (64-bit edition).</span></span> <span data-ttu-id="37c50-146">É recomendável executar adicionalmente o Service Pack mais recente.</span><span class="sxs-lookup"><span data-stu-id="37c50-146">Additionally running the latest service pack is recommended.</span></span>
    
      - <span data-ttu-id="37c50-147">Software de banco de dados corporativo do Microsoft SQL Server 2008 R2 (64-bit Edition).</span><span class="sxs-lookup"><span data-stu-id="37c50-147">Microsoft SQL Server 2008 R2 Enterprise database software (64-bit edition).</span></span> <span data-ttu-id="37c50-148">É recomendável executar adicionalmente o Service Pack mais recente.</span><span class="sxs-lookup"><span data-stu-id="37c50-148">Additionally running the latest service pack is recommended.</span></span>

<span data-ttu-id="37c50-149">Para obter mais informações sobre o espelhamento do SQL, consulte [back end Server High Availability in Lync Server 2013](lync-server-2013-back-end-server-high-availability.md).</span><span class="sxs-lookup"><span data-stu-id="37c50-149">For more information about SQL mirroring, see [Back End Server high availability in Lync Server 2013](lync-server-2013-back-end-server-high-availability.md).</span></span> <span data-ttu-id="37c50-150">Para obter detalhes sobre como implantar o cluster SQL, consulte [Configure SQL Server clustering for Lync server 2013](lync-server-2013-configure-sql-server-clustering.md).</span><span class="sxs-lookup"><span data-stu-id="37c50-150">For details on how to deploy SQL clustering, see [Configure SQL Server clustering for Lync Server 2013](lync-server-2013-configure-sql-server-clustering.md).</span></span>

<span data-ttu-id="37c50-151">Para obter mais informações e práticas recomendadas para clustering de failover no SQL Server 2012, consulte <https://technet.microsoft.com/library/hh231721.aspx> .</span><span class="sxs-lookup"><span data-stu-id="37c50-151">For more information and best practices for failover clustering in SQL Server 2012, see <https://technet.microsoft.com/library/hh231721.aspx>.</span></span> <span data-ttu-id="37c50-152">Para clustering de failover no SQL Server 2008, consulte <https://technet.microsoft.com/library/ms189134(v=sql.105).aspx> .</span><span class="sxs-lookup"><span data-stu-id="37c50-152">For failover clustering in SQL Server 2008, see <https://technet.microsoft.com/library/ms189134(v=sql.105).aspx>.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

