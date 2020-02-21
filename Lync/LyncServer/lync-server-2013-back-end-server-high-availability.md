---
title: 'Lync Server 2013: alta disponibilidade do servidor back-end'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Back End Server high availability
ms:assetid: c559aacb-4e1d-4e78-9582-41f966ad418d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205248(v=OCS.15)
ms:contentKeyID: 48185358
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 335f7680a98eb53414a8b438975d79327b515946
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42196964"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="back-end-server-high-availability-in-lync-server-2013"></a><span data-ttu-id="1c26c-102">Alta disponibilidade de servidor back-end no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1c26c-102">Back End Server high availability in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1c26c-103">_**Última modificação do tópico:** 2013-08-12_</span><span class="sxs-lookup"><span data-stu-id="1c26c-103">_**Topic Last Modified:** 2013-08-12_</span></span>

<span data-ttu-id="1c26c-104">Para garantir a alta disponibilidade para seus servidores de back-end, você pode usar o espelhamento síncrono do SQL ou o cluster SQL.</span><span class="sxs-lookup"><span data-stu-id="1c26c-104">To ensure high availability for your Back End Servers, you can use either synchronous SQL mirroring or SQL clustering.</span></span> <span data-ttu-id="1c26c-105">Usando uma dessas soluções opcional, mas é recomendável manter a continuidade de negócios da sua organização.</span><span class="sxs-lookup"><span data-stu-id="1c26c-105">Using one of these solutions optional, but is recommended to maintain your organization's business continuity.</span></span> <span data-ttu-id="1c26c-106">O espelhamento SQL assíncrono não tem suporte para alta disponibilidade do servidor back-end no Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="1c26c-106">Asynchronous SQL mirroring is not supported for Back End Server high availability in Lync Server 2013.</span></span> <span data-ttu-id="1c26c-107">No resto deste documento, o espelhamento SQL significa espelhamento SQL sincronizado, a não ser explicitamente declarado.</span><span class="sxs-lookup"><span data-stu-id="1c26c-107">In the rest of this document, SQL mirroring means synchronous SQL mirroring, unless otherwise explicitly stated.</span></span>

<span data-ttu-id="1c26c-108">Você pode configurar facilmente o espelhamento do SQL com o construtor de topologias.</span><span class="sxs-lookup"><span data-stu-id="1c26c-108">You can easily set up SQL mirroring with Topology Builder.</span></span> <span data-ttu-id="1c26c-109">Para o cluster de failover do SQL, você deve usar o SQL Server para configuração.</span><span class="sxs-lookup"><span data-stu-id="1c26c-109">For SQL failover clustering, you must use SQL Server for setup.</span></span>

<span data-ttu-id="1c26c-110">Se você usar o espelhamento de SQL ou SQL em um pool que esteja emparelhado com outro pool de front-ends para recuperação de desastres, deverá usar a mesma solução de alta disponibilidade de back-end em ambos os pools.</span><span class="sxs-lookup"><span data-stu-id="1c26c-110">If you use either SQL mirroring or SQL clustering in a pool which is paired with another Front End pool for disaster recovery, you should use the same Back End high availability solution in both pools.</span></span> <span data-ttu-id="1c26c-111">Você não deve emparelhar um pool usando o espelhamento SQL com um pool usando o cluster do SQL.</span><span class="sxs-lookup"><span data-stu-id="1c26c-111">You should not pair a pool using SQL mirroring with a pool using SQL clustering.</span></span>

<span data-ttu-id="1c26c-112">Quando você implanta o espelhamento do SQL, todos os bancos de dados do Lync Server no pool são espelhados, incluindo o repositório de gerenciamento central, se ele estiver localizado nesse pool, bem como o banco de dados de aplicativo do grupo de resposta e o banco de dados do aplicativo de estacionamento de chamada, se esses aplicativos estão em execução no pool.</span><span class="sxs-lookup"><span data-stu-id="1c26c-112">When you deploy SQL mirroring, all Lync Server databases in the pool are mirrored, including the Central Management store, if it is located in this pool, as well as the Response Group application database and the Call Park application database, if those applications are running in the pool.</span></span>

<span data-ttu-id="1c26c-p104">Com o espelhamento SQL, você não precisa usar o armazenamento compartilhado para servidores. Cada servidor mantém sua cópia dos bancos de dados no armazenamento local.</span><span class="sxs-lookup"><span data-stu-id="1c26c-p104">With SQL mirroring, you do not need to use shared storage for the servers. Each server keeps its copy of the databases in local storage.</span></span>

<span data-ttu-id="1c26c-p105">Você pode escolher implantar espelhamento SQL com ou sem uma testemunha. Recomendamos usar uma testemunha porque habilita o failover do Servidor de Back-End como automático. De outra forma, um administrador deve invocar manualmente o failover. Observe que mesmo se uma testemunha é implantada, um administrador pode invocar manualmente o failover do Servidor de Back-End, se necessário.</span><span class="sxs-lookup"><span data-stu-id="1c26c-p105">You may choose to deploy SQL mirroring with or without a witness. We recommend using a witness because it enables failover of the Back End Server to be automatic. Otherwise, an administrator must manually invoke failover. Note that even if a witness is deployed, an administrator can manually invoke Back End Server failover, if necessary.</span></span>

<span data-ttu-id="1c26c-p106">Se você usar uma testemunha, é possível utilizar uma única testemunha para vários pares de Servidores de Back-End. Não há correspondência exata entre testemunhas e pares de Servidores de Back-End. As implantações usam uma única testemunha para vários pares de Servidores de Back-End não são tão resilientes quanto topologias com uma testemunha separada para cada par de Servidor de Back-End.</span><span class="sxs-lookup"><span data-stu-id="1c26c-p106">If you use a witness, you can use a single witness for multiple pairs of Back End Servers. There is no strict 1:1 correspondence between witnesses and pairs of Back End Servers. Deployments that use a single witness for multiple pairs of Back End Servers are not quite as resilient as topologies with a separate witness for each Back End Server pair.</span></span>

<span data-ttu-id="1c26c-122">Para obter mais informações sobre o suporte a agrupamento do SQL, confira [suporte a software de banco de dados no Lync Server 2013](lync-server-2013-database-software-support.md).</span><span class="sxs-lookup"><span data-stu-id="1c26c-122">For more information about SQL clustering support, see [Database software support in Lync Server 2013](lync-server-2013-database-software-support.md).</span></span> <span data-ttu-id="1c26c-123">Para obter detalhes sobre como implantar o cluster SQL, consulte [Configure SQL Server clustering for Lync server 2013](lync-server-2013-configure-sql-server-clustering.md).</span><span class="sxs-lookup"><span data-stu-id="1c26c-123">For details on deploying SQL clustering, see [Configure SQL Server clustering for Lync Server 2013](lync-server-2013-configure-sql-server-clustering.md).</span></span>

<div>

## <a name="recovery-time-for-automatic-back-end-server-failover-with-sql-mirroring"></a><span data-ttu-id="1c26c-124">Tempo de recuperação para failover automático do servidor back-end com espelhamento SQL</span><span class="sxs-lookup"><span data-stu-id="1c26c-124">Recovery Time for Automatic Back End Server Failover with SQL Mirroring</span></span>

<span data-ttu-id="1c26c-125">Para failover automático de back-end com espelhamento de SQL, o objetivo da engenharia para o objetivo de tempo de recuperação (RTO) é de 5 minutos.</span><span class="sxs-lookup"><span data-stu-id="1c26c-125">For automatic Back End failover with SQL mirroring, the engineering target for recovery time objective (RTO) is 5 minutes.</span></span> <span data-ttu-id="1c26c-126">Como o espelhamento SQL sincronizado, não antecipamos a perda de dados durante as falhas do Servidor de Back-End, exceto em raras ocasiões quando os Servidores de Front-End e Servidor de Back-End saem simultaneamente enquanto os dados estão sendo movidos entre os servidores.</span><span class="sxs-lookup"><span data-stu-id="1c26c-126">Because of the synchronous SQL mirroring, we do not anticipate data loss during Back End Server failures except in rare occasions when both the Front End Servers and the Back End Server go down simultaneously while data is being moved between the servers.</span></span> <span data-ttu-id="1c26c-127">A meta de engenharia para o objetivo de ponto de recuperação (RPO) é de 5 minutos.</span><span class="sxs-lookup"><span data-stu-id="1c26c-127">The engineering target for recovery point objective (RPO) is 5 minutes.</span></span>

</div>

<div>

## <a name="user-experience-during-back-end-server-failure-with-sql-mirroring"></a><span data-ttu-id="1c26c-128">Experiência do usuário durante falha do servidor back-end com espelhamento de SQL</span><span class="sxs-lookup"><span data-stu-id="1c26c-128">User Experience During Back End Server Failure with SQL Mirroring</span></span>

<span data-ttu-id="1c26c-129">Experiência do usuário durante uma falha depende da natureza falha e da sua topologia.</span><span class="sxs-lookup"><span data-stu-id="1c26c-129">User experience during a failure depends on the nature of the failure, and on your topology.</span></span>

<span data-ttu-id="1c26c-130">Se você usar o espelhamento SQL e tiver uma testemunha configurada e a entidade falhar, o failover do servidor back-end ocorrerá de forma automática e rápida.</span><span class="sxs-lookup"><span data-stu-id="1c26c-130">If you use SQL mirroring and have a witness configured, and the principal fails, Back End Server failover happens automatically and quickly.</span></span> <span data-ttu-id="1c26c-131">Os usuários ativos não devem observar muita interrupção em suas sessões contínuas.</span><span class="sxs-lookup"><span data-stu-id="1c26c-131">Active users should not notice much interruption to their ongoing sessions.</span></span>

<span data-ttu-id="1c26c-132">Se não há uma testemunha configurada, pode levar algum tempo para o administrador invocar manualmente o failover.</span><span class="sxs-lookup"><span data-stu-id="1c26c-132">If there is no witness configured, it will take some time for the administrator to manually invoke the failover.</span></span> <span data-ttu-id="1c26c-133">Durante este tempo, os usuários ativos podem ser afetados.</span><span class="sxs-lookup"><span data-stu-id="1c26c-133">During that time, active users may be affected.</span></span> <span data-ttu-id="1c26c-134">Eles continuam suas sessões normalmente por cerca de 30 minutos.</span><span class="sxs-lookup"><span data-stu-id="1c26c-134">They will continue their sessions as normal for about 30 minutes.</span></span> <span data-ttu-id="1c26c-135">Se o principal ainda não for restaurado ou se um administrador não tiver feito failover para o backup, os usuários serão alternados para o modo de resiliência, significando que eles não podem executar tarefas que exijam uma alteração persistente no Lync Server (como adicionar um contato).</span><span class="sxs-lookup"><span data-stu-id="1c26c-135">If the primary is still not restored, or an administrator has not failed over to the backup, then users are switched to Resiliency mode, meaning that they are unable to perform tasks that require a persistent change on Lync Server (such as adding a contact).</span></span>

<span data-ttu-id="1c26c-p111">Se o diretor e o Servidor de Back-End espelho falharem ou se um destes servidores e a testemunha falharem, o Servidor de Back-End se tornará indisponível (mesmo se o diretor ainda estiver funcionando). Neste caso, os usuários ativos são mudados para o modo Resiliência após algum tempo.</span><span class="sxs-lookup"><span data-stu-id="1c26c-p111">If both the principal and the mirror Back End Servers fail, or if one of those servers and the witness fails, the Back End Server will become unavailable (even if it is the principal that is still working). In this case, active users are switched to Resiliency mode after some time.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

