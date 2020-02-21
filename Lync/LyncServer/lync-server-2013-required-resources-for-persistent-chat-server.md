---
title: 'Lync Server 2013: recursos necessários para o servidor de chat persistente'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Required resources
ms:assetid: bce50b95-f3c8-407e-963a-d8896ee77fbc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205211(v=OCS.15)
ms:contentKeyID: 48185255
ms.date: 02/05/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3c925a695fd856c4e9c2d272d39f18a7c3d1f78c
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42214967"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="required-resources-for-persistent-chat-server-in-lync-server-2013"></a><span data-ttu-id="fc082-102">Recursos necessários para o servidor de chat persistente no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="fc082-102">Required resources for Persistent Chat Server in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="fc082-103">_**Última modificação do tópico:** 2016-02-05_</span><span class="sxs-lookup"><span data-stu-id="fc082-103">_**Topic Last Modified:** 2016-02-05_</span></span>

<span data-ttu-id="fc082-104">Alta disponibilidade e recuperação de desastre para servidor de chat persistente requer recursos adicionais além do que normalmente é necessário para operação completa.</span><span class="sxs-lookup"><span data-stu-id="fc082-104">High availability and disaster recovery for Persistent Chat Server requires additional resources beyond what is typically needed for full operation.</span></span> <span data-ttu-id="fc082-105">Antes de configurar o servidor de chat persistente para alta disponibilidade e recuperação de desastre, verifique se você tem os seguintes recursos além do que é necessário para a operação padrão de servidor de chat persistente.</span><span class="sxs-lookup"><span data-stu-id="fc082-105">Before configuring Persistent Chat Server for high availability and disaster recovery, ensure that you have the following resources in addition to what is required for standard Persistent Chat Server operation.</span></span> <span data-ttu-id="fc082-106">Para obter informações adicionais sobre a configuração, consulte [Configuring persistent chat Server in Lync Server 2013](lync-server-2013-configuring-persistent-chat-server.md).</span><span class="sxs-lookup"><span data-stu-id="fc082-106">For additional configuration information, see [Configuring Persistent Chat Server in Lync Server 2013](lync-server-2013-configuring-persistent-chat-server.md).</span></span>

  - <span data-ttu-id="fc082-107">Uma instância de banco de dados dedicada localizada no mesmo Data Center físico no qual o front-end do serviço servidor de chat persistente está localizado.</span><span class="sxs-lookup"><span data-stu-id="fc082-107">One dedicated database instance located in the same physical data center in which the home front end of the Persistent Chat Server service is located.</span></span> <span data-ttu-id="fc082-108">Este banco de dados funcionará como o espelho do SQL Server para o banco de dados de chat persistente principal.</span><span class="sxs-lookup"><span data-stu-id="fc082-108">This database will serve as the SQL Server mirror for the primary Persistent Chat database.</span></span> <span data-ttu-id="fc082-109">Opcionalmente, designe um SQL Server adicional para servir como testemunha de espelhamento, se você quiser um failover automatizado para o banco de dados espelho.</span><span class="sxs-lookup"><span data-stu-id="fc082-109">Optionally, designate an additional SQL Server to serve as the mirroring witness if you want an automated failover to the mirror database.</span></span>

  - <span data-ttu-id="fc082-110">Uma instância de banco de dados dedicada localizada no outro data Center físico.</span><span class="sxs-lookup"><span data-stu-id="fc082-110">One dedicated database instance located in the other physical data center.</span></span> <span data-ttu-id="fc082-111">Este banco de dados servirá como banco de dados secundário de envio de logs do SQL Server para o banco de dados no data center primário.</span><span class="sxs-lookup"><span data-stu-id="fc082-111">This database will serve as the SQL Server Log Shipping secondary database for the database in the primary data center.</span></span>

  - <span data-ttu-id="fc082-112">Uma instância de banco de dados dedicada para servir como o espelho do SQL Server para o banco de dados secundário.</span><span class="sxs-lookup"><span data-stu-id="fc082-112">One dedicated database instance to serve as the SQL Server mirror for the secondary database.</span></span> <span data-ttu-id="fc082-113">Opcionalmente, designe um servidor SQL adicional para o servidor como testemunha de espelhamento.</span><span class="sxs-lookup"><span data-stu-id="fc082-113">Optionally, designate an additional SQL Server to server as the mirroring witness.</span></span> <span data-ttu-id="fc082-114">Ambos devem estar localizado no mesmo data Center físico que o banco de dados secundário.</span><span class="sxs-lookup"><span data-stu-id="fc082-114">Both of these must be located in the same physical data center as the secondary database.</span></span>

  - <span data-ttu-id="fc082-115">Se a conformidade do servidor de chat persistente estiver habilitada, serão necessárias mais três instâncias de banco de dados dedicadas.</span><span class="sxs-lookup"><span data-stu-id="fc082-115">If Persistent Chat Server compliance is enabled, an additional three dedicated database instances are required.</span></span> <span data-ttu-id="fc082-116">Suas distribuições são as mesmas descritas anteriormente para o banco de dados de chat persistente.</span><span class="sxs-lookup"><span data-stu-id="fc082-116">Their distribution is the same as those previously outlined for the Persistent Chat database.</span></span> <span data-ttu-id="fc082-117">Embora seja possível que o banco de dados de conformidade compartilhe a mesma instância do SQL Server que o banco de dados de chat persistente, recomendamos instâncias autônomas para alta disponibilidade e recuperação de desastre.</span><span class="sxs-lookup"><span data-stu-id="fc082-117">While it is possible for the compliance database to share the same SQL Server instance as the Persistent Chat database, we recommend standalone instances for high availability and disaster recovery.</span></span>

  - <span data-ttu-id="fc082-118">Um compartilhamento de arquivos deve ser criado e designado para os logs de transação de envio de logs do SQL Server.</span><span class="sxs-lookup"><span data-stu-id="fc082-118">A file share must be created and designated for the SQL Server Log Shipping transaction logs.</span></span> <span data-ttu-id="fc082-119">Todos os SQL Servers em ambos os data centers que executam bancos de dados de chat persistente devem ter acesso de leitura/gravação a esse compartilhamento de arquivos.</span><span class="sxs-lookup"><span data-stu-id="fc082-119">All SQL Servers in both data centers that run Persistent Chat databases must have read/write access to this file share.</span></span> <span data-ttu-id="fc082-120">Este compartilhamento não está definido como parte de uma função FileStore.</span><span class="sxs-lookup"><span data-stu-id="fc082-120">This share is not defined as part of a FileStore role.</span></span>

  - <span data-ttu-id="fc082-121">Um compartilhamento de arquivos no servidor de banco de dados secundário para servir como a pasta de destino dos logs de transação do SQL Server que são copiados do compartilhamento de arquivos do servidor primário.</span><span class="sxs-lookup"><span data-stu-id="fc082-121">A file share on the secondary database server to serve as the destination folder for the SQL Server transaction logs that are copied from the primary server file share.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="fc082-122">Os servidores de chat persistente ativos em um pool de servidores de chat persistente devem residir no mesmo fuso horário que o pool de Lync do próximo salto definido na topologia.</span><span class="sxs-lookup"><span data-stu-id="fc082-122">Active Persistent Chat servers in a Persistent Chat Server pool MUST reside in the same time zone as the next hop Lync Pool defined in the topology.</span></span>



</div>

<span data-ttu-id="fc082-123">Os seguintes números fornecem exemplos sobre como o pool de servidor de chat persistente inteiro pode ser configurado em duas topologias de pool estendidas diferentes:</span><span class="sxs-lookup"><span data-stu-id="fc082-123">The following figures provide examples about how the entire Persistent Chat Server pool can be configured in the two different stretched pool topologies:</span></span>

  - <span data-ttu-id="fc082-124">Pool de servidor de chat persistente ampliado quando os data centers estão geo-localizados com alta largura de banda/baixa latência.</span><span class="sxs-lookup"><span data-stu-id="fc082-124">Stretched Persistent Chat Server pool when data centers are geo-located with high bandwidth/low latency.</span></span>

  - <span data-ttu-id="fc082-125">Pool de servidor de chat persistente ampliado quando os data centers estão geo-localizados com baixa largura de banda/alta latência.</span><span class="sxs-lookup"><span data-stu-id="fc082-125">Stretched Persistent Chat Server pool when data centers are geo-located with low bandwidth/high latency.</span></span>

<span data-ttu-id="fc082-126">A figura a seguir mostra uma topologia de pool de servidor de chat persistente estendido onde os data centers estão localizados geograficamente com alta largura de banda/baixa latência.</span><span class="sxs-lookup"><span data-stu-id="fc082-126">The following figure shows a stretched Persistent Chat Server pool topology where data centers are geo-located with high bandwidth/low latency.</span></span>

<span data-ttu-id="fc082-127">**Pool de servidor de chat persistente ampliado quando os data centers estão geo-localizados com alta largura de banda/baixa latência.**</span><span class="sxs-lookup"><span data-stu-id="fc082-127">**Stretched Persistent Chat Server pool when data centers are geo-located with high bandwidth/low latency.**</span></span>

<span data-ttu-id="fc082-128">![Exame de configuração do pool do servidor de chat persistente HBW](images/JJ205211.55d10910-c824-41e6-bed2-08d13a2abd65(OCS.15).jpg "Exame de configuração do pool do servidor de chat persistente HBW")</span><span class="sxs-lookup"><span data-stu-id="fc082-128">![Persistent Chat Server pool HBW configuration exam](images/JJ205211.55d10910-c824-41e6-bed2-08d13a2abd65(OCS.15).jpg "Persistent Chat Server pool HBW configuration exam")</span></span>

<span data-ttu-id="fc082-129">A figura a seguir mostra uma topologia de pool de servidor de chat persistente estendido onde os data centers estão localizados geograficamente com baixa largura de banda/alta latência.</span><span class="sxs-lookup"><span data-stu-id="fc082-129">The following figure shows a stretched Persistent Chat Server pool topology where data centers are geo-located with low bandwidth/high latency.</span></span>

<span data-ttu-id="fc082-130">**Pool de servidor de chat persistente ampliado quando os data centers estão geo-localizados com baixa largura de banda/alta latência.**</span><span class="sxs-lookup"><span data-stu-id="fc082-130">**Stretched Persistent Chat Server pool when data centers are geo-located with low bandwidth/high latency.**</span></span>

<span data-ttu-id="fc082-131">![Exame de configuração do pool do servidor de chat persistente LBW](images/JJ205211.586b0a3a-3767-4991-944f-ee54389512aa(OCS.15).jpg "Exame de configuração do pool do servidor de chat persistente LBW")</span><span class="sxs-lookup"><span data-stu-id="fc082-131">![Persistent Chat Server pool LBW configuration exam](images/JJ205211.586b0a3a-3767-4991-944f-ee54389512aa(OCS.15).jpg "Persistent Chat Server pool LBW configuration exam")</span></span>

</div>

<span> </span>

</div>

</div>

</div>

