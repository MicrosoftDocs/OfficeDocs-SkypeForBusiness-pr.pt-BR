---
title: 'Lync Server 2013: back-end servidor back-up alta disponibilidade'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Back End Server high availability
ms:assetid: c559aacb-4e1d-4e78-9582-41f966ad418d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205248(v=OCS.15)
ms:contentKeyID: 48185358
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f65ae3f476e81868619fa8d8d92ed60c71ce767d
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34836899"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="back-end-server-high-availability-in-lync-server-2013"></a><span data-ttu-id="db461-102">Back-end Server alta disponibilidade no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="db461-102">Back End Server high availability in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="db461-103">_**Tópico da última modificação:** 2013-08-12_</span><span class="sxs-lookup"><span data-stu-id="db461-103">_**Topic Last Modified:** 2013-08-12_</span></span>

<span data-ttu-id="db461-104">Para garantir alta disponibilidade para seus servidores back-end, você pode usar o espelhamento do SQL síncrono ou o agrupamento do SQL.</span><span class="sxs-lookup"><span data-stu-id="db461-104">To ensure high availability for your Back End Servers, you can use either synchronous SQL mirroring or SQL clustering.</span></span> <span data-ttu-id="db461-105">Usar uma dessas soluções opcional, mas é recomendável manter a continuidade de negócios da sua organização.</span><span class="sxs-lookup"><span data-stu-id="db461-105">Using one of these solutions optional, but is recommended to maintain your organization's business continuity.</span></span> <span data-ttu-id="db461-106">O espelhamento SQL assíncrono não é compatível com o back-end do servidor back-end no Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="db461-106">Asynchronous SQL mirroring is not supported for Back End Server high availability in Lync Server 2013.</span></span> <span data-ttu-id="db461-107">No restante deste documento, o espelhamento do SQL significa o espelhamento síncrono do SQL, a menos que explicitamente declarado de outra forma.</span><span class="sxs-lookup"><span data-stu-id="db461-107">In the rest of this document, SQL mirroring means synchronous SQL mirroring, unless otherwise explicitly stated.</span></span>

<span data-ttu-id="db461-108">Você pode facilmente configurar o espelhamento do SQL com o construtor de topologias.</span><span class="sxs-lookup"><span data-stu-id="db461-108">You can easily set up SQL mirroring with Topology Builder.</span></span> <span data-ttu-id="db461-109">Para o cluster de failover SQK, você deve usar o SQL Server para a configuração.</span><span class="sxs-lookup"><span data-stu-id="db461-109">For SQL failover clustering, you must use SQL Server for setup.</span></span>

<span data-ttu-id="db461-110">Se você usa o SQL Mirroring ou SQL cluster em um pool que está emparelhado com outro pool de front-end para recuperação de desastres, você deve usar a mesma solução de alta disponibilidade de back-end nos dois pools.</span><span class="sxs-lookup"><span data-stu-id="db461-110">If you use either SQL mirroring or SQL clustering in a pool which is paired with another Front End pool for disaster recovery, you should use the same Back End high availability solution in both pools.</span></span> <span data-ttu-id="db461-111">Você não deve emparelhar um pool usando o espelhamento do SQL com um pool usando o agrupamento do SQL.</span><span class="sxs-lookup"><span data-stu-id="db461-111">You should not pair a pool using SQL mirroring with a pool using SQL clustering.</span></span>

<span data-ttu-id="db461-112">Quando você implanta o espelhamento do SQL, todos os bancos de dados do Lync Server no pool são espelhados, incluindo o repositório de gerenciamento central, se estiverem localizados nesse pool, bem como o banco de dados de aplicativo do grupo de resposta e o banco de dados do aplicativo de estacionamento de chamadas, se esses aplicativos estão em execução no pool.</span><span class="sxs-lookup"><span data-stu-id="db461-112">When you deploy SQL mirroring, all Lync Server databases in the pool are mirrored, including the Central Management store, if it is located in this pool, as well as the Response Group application database and the Call Park application database, if those applications are running in the pool.</span></span>

<span data-ttu-id="db461-113">Com o espelhamento do SQL, você não precisa usar o armazenamento compartilhado para os servidores.</span><span class="sxs-lookup"><span data-stu-id="db461-113">With SQL mirroring, you do not need to use shared storage for the servers.</span></span> <span data-ttu-id="db461-114">Cada servidor mantém sua cópia dos bancos de dados no armazenamento local.</span><span class="sxs-lookup"><span data-stu-id="db461-114">Each server keeps its copy of the databases in local storage.</span></span>

<span data-ttu-id="db461-115">Você pode optar por implantar o espelhamento do SQL com ou sem uma testemunha.</span><span class="sxs-lookup"><span data-stu-id="db461-115">You may choose to deploy SQL mirroring with or without a witness.</span></span> <span data-ttu-id="db461-116">Recomendamos usar uma testemunha porque isso habilita o failover do Servidor Back-End como automático.</span><span class="sxs-lookup"><span data-stu-id="db461-116">We recommend using a witness because it enables failover of the Back End Server to be automatic.</span></span> <span data-ttu-id="db461-117">Caso contrário, um administrador terá que invocar manualmente o failover.</span><span class="sxs-lookup"><span data-stu-id="db461-117">Otherwise, an administrator must manually invoke failover.</span></span> <span data-ttu-id="db461-118">Observe que mesmo se uma testemunha for implantada, um administrador pode invocar manualmente o failover do Servidor Back-End, se necessário.</span><span class="sxs-lookup"><span data-stu-id="db461-118">Note that even if a witness is deployed, an administrator can manually invoke Back End Server failover, if necessary.</span></span>

<span data-ttu-id="db461-p106">Se você usar uma testemunha, poderá utilizar uma única testemunha para vários pares de Servidores Back-End. Não há correspondência exata entre testemunhas e pares de Servidores Back-End. As implantações que usam uma única testemunha para vários pares de Servidores Back-End não são tão resilientes quanto as topologias com uma testemunha separada para cada par de Servidores Back-End.</span><span class="sxs-lookup"><span data-stu-id="db461-p106">If you use a witness, you can use a single witness for multiple pairs of Back End Servers. There is no strict 1:1 correspondence between witnesses and pairs of Back End Servers. Deployments that use a single witness for multiple pairs of Back End Servers are not quite as resilient as topologies with a separate witness for each Back End Server pair.</span></span>

<span data-ttu-id="db461-122">Para obter mais informações sobre o suporte a agrupamento do SQL, consulte [suporte a software de banco de dados no Lync Server 2013](lync-server-2013-database-software-support.md).</span><span class="sxs-lookup"><span data-stu-id="db461-122">For more information about SQL clustering support, see [Database software support in Lync Server 2013](lync-server-2013-database-software-support.md).</span></span> <span data-ttu-id="db461-123">Para obter detalhes sobre a implantação do SQL clustering, consulte [Configurar o cluster do SQL Server para o Lync Server 2013](lync-server-2013-configure-sql-server-clustering.md).</span><span class="sxs-lookup"><span data-stu-id="db461-123">For details on deploying SQL clustering, see [Configure SQL Server clustering for Lync Server 2013](lync-server-2013-configure-sql-server-clustering.md).</span></span>

<div>

## <a name="recovery-time-for-automatic-back-end-server-failover-with-sql-mirroring"></a><span data-ttu-id="db461-124">Tempo de recuperação para failover automático do servidor back-end com espelhamento do SQL</span><span class="sxs-lookup"><span data-stu-id="db461-124">Recovery Time for Automatic Back End Server Failover with SQL Mirroring</span></span>

<span data-ttu-id="db461-125">Para failover automático de back-end com o espelhamento do SQL, o objetivo da engenharia do RTO do tempo de recuperação (RTO) é de cinco minutos.</span><span class="sxs-lookup"><span data-stu-id="db461-125">For automatic Back End failover with SQL mirroring, the engineering target for recovery time objective (RTO) is 5 minutes.</span></span> <span data-ttu-id="db461-126">Devido ao espelhamento síncrono do SQL, não antecipamos a perda de dados durante falhas de servidor back-end, exceto em raras ocasiões em que os servidores front-end e o back-end do servidor back-end simultaneamente enquanto os dados estão sendo movidos entre os servidores.</span><span class="sxs-lookup"><span data-stu-id="db461-126">Because of the synchronous SQL mirroring, we do not anticipate data loss during Back End Server failures except in rare occasions when both the Front End Servers and the Back End Server go down simultaneously while data is being moved between the servers.</span></span> <span data-ttu-id="db461-127">A meta de engenharia para o objetivo do ponto de recuperação (RPO) é de 5 minutos.</span><span class="sxs-lookup"><span data-stu-id="db461-127">The engineering target for recovery point objective (RPO) is 5 minutes.</span></span>

</div>

<div>

## <a name="user-experience-during-back-end-server-failure-with-sql-mirroring"></a><span data-ttu-id="db461-128">Experiência do usuário durante a falha do servidor back-end com o espelhamento do SQL</span><span class="sxs-lookup"><span data-stu-id="db461-128">User Experience During Back End Server Failure with SQL Mirroring</span></span>

<span data-ttu-id="db461-129">A experiência do usuário durante uma falha depende da natureza da falha e da topologia.</span><span class="sxs-lookup"><span data-stu-id="db461-129">User experience during a failure depends on the nature of the failure, and on your topology.</span></span>

<span data-ttu-id="db461-130">Se você usar o espelhamento do SQL e tiver uma testemunha configurada, e o principal falhar, o failover do servidor back-end ocorrerá de forma automática e rápida.</span><span class="sxs-lookup"><span data-stu-id="db461-130">If you use SQL mirroring and have a witness configured, and the principal fails, Back End Server failover happens automatically and quickly.</span></span> <span data-ttu-id="db461-131">Os usuários ativos não devem notar a interrupção em suas sessões contínuas.</span><span class="sxs-lookup"><span data-stu-id="db461-131">Active users should not notice much interruption to their ongoing sessions.</span></span>

<span data-ttu-id="db461-132">Se não houver uma testemunha configurada, pode levar algum tempo para o administrador invocar manualmente o failover.</span><span class="sxs-lookup"><span data-stu-id="db461-132">If there is no witness configured, it will take some time for the administrator to manually invoke the failover.</span></span> <span data-ttu-id="db461-133">Durante este tempo, os usuários ativos podem ser afetados.</span><span class="sxs-lookup"><span data-stu-id="db461-133">During that time, active users may be affected.</span></span> <span data-ttu-id="db461-134">Eles continuam suas sessões normalmente por cerca de 30 minutos.</span><span class="sxs-lookup"><span data-stu-id="db461-134">They will continue their sessions as normal for about 30 minutes.</span></span> <span data-ttu-id="db461-135">Se o principal ainda não for restaurado ou se um administrador não tiver failover para o backup, os usuários terão alternado para o modo de resiliência, o que significa que eles não poderão executar tarefas que exijam uma alteração persistente no Lync Server (como adicionar um contato).</span><span class="sxs-lookup"><span data-stu-id="db461-135">If the primary is still not restored, or an administrator has not failed over to the backup, then users are switched to Resiliency mode, meaning that they are unable to perform tasks that require a persistent change on Lync Server (such as adding a contact).</span></span>

<span data-ttu-id="db461-p111">Se o servidor principal e o Servidor Back-End espelho falharem ou se um desses servidores e a testemunha falharem, o Servidor Back-End se tornará indisponível (mesmo se o servidor principal ainda estiver funcionando). Nesse caso, os usuários ativos serão transferidos para o modo de Resiliência após um certo tempo.</span><span class="sxs-lookup"><span data-stu-id="db461-p111">If both the principal and the mirror Back End Servers fail, or if one of those servers and the witness fails, the Back End Server will become unavailable (even if it is the principal that is still working). In this case, active users are switched to Resiliency mode after some time.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

