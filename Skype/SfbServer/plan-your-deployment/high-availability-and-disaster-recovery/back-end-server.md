---
title: Back-end Server alta disponibilidade no Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: c559aacb-4e1d-4e78-9582-41f966ad418d
description: Saiba mais sobre as opções de alta disponibilidade do servidor back-end com suporte no Skype for Business Server, incluindo grupos de disponibilidade AlwaysOn, instâncias de cluster de failover AlwaysOn, espelhamento de banco de dados e cluster de failover de SQL.
ms.openlocfilehash: 4c814e525b3a1d0900e7162255ec4d7e86d79605
ms.sourcegitcommit: 1a08ec9069332e19135312d35fc6a6c3247ce2d2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/11/2020
ms.locfileid: "41888610"
---
# <a name="back-end-server-high-availability-in-skype-for-business-server"></a><span data-ttu-id="65e6e-103">Back-end Server alta disponibilidade no Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="65e6e-103">Back End Server high availability in Skype for Business Server</span></span>
 
<span data-ttu-id="65e6e-104">Saiba mais sobre as opções de alta disponibilidade do servidor back-end com suporte no Skype for Business Server, incluindo grupos de disponibilidade AlwaysOn, instâncias de cluster de failover AlwaysOn, espelhamento de banco de dados e cluster de failover de SQL.</span><span class="sxs-lookup"><span data-stu-id="65e6e-104">Learn about the Back End Server high availability options supported in Skype for Business Server, including AlwaysOn Availability Groups, AlwaysOn Failover Cluster Instances, database mirroring, and SQL failover clustering.</span></span>
  
<span data-ttu-id="65e6e-105">Há quatro opções para aumentar a alta disponibilidade dos Servidores Back-End:</span><span class="sxs-lookup"><span data-stu-id="65e6e-105">To enhance high availability for your Back End Servers, you have four options:</span></span>
  
- <span data-ttu-id="65e6e-106">Espelhamento de banco de dados</span><span class="sxs-lookup"><span data-stu-id="65e6e-106">Database mirroring</span></span>
    
- <span data-ttu-id="65e6e-107">Grupos de Disponibilidade Sempre Visíveis</span><span class="sxs-lookup"><span data-stu-id="65e6e-107">AlwaysOn Availability Groups</span></span>
    
- <span data-ttu-id="65e6e-108">Instâncias de cluster de failover do AlwaysOn (FCI)</span><span class="sxs-lookup"><span data-stu-id="65e6e-108">AlwaysOn Failover Cluster Instances (FCI)</span></span>
    
- <span data-ttu-id="65e6e-109">Clustering de failover do SQL</span><span class="sxs-lookup"><span data-stu-id="65e6e-109">SQL failover clustering</span></span>
    
<span data-ttu-id="65e6e-110">O uso de uma dessas soluções é opcional, mas é recomendada para manter a continuidade de negócio da sua organização.</span><span class="sxs-lookup"><span data-stu-id="65e6e-110">Using one of these solutions is optional, but is recommended to maintain your organization's business continuity.</span></span> <span data-ttu-id="65e6e-111">Caso contrário, o uso de um único servidor de banco de dados pode causar perda de dados significativos do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="65e6e-111">Otherwise, having a single database server go down could cause the loss of significant Skype for Business Server data.</span></span> 
  
<span data-ttu-id="65e6e-112">Você pode configurar o espelhamento de banco de dados usando somente o construtor de topologias.</span><span class="sxs-lookup"><span data-stu-id="65e6e-112">You can set up database mirroring using only Topology Builder.</span></span> <span data-ttu-id="65e6e-113">Para grupos de disponibilidade AlwaysOn, instâncias de cluster de failover AlwaysOn ou cluster de failover do SQL, use o SQL Server para criar a solução de alta disponibilidade, então você pode usar o construtor de topologias para associá-lo a um pool de front-ends.</span><span class="sxs-lookup"><span data-stu-id="65e6e-113">For AlwaysOn Availability Groups, AlwaysOn Failover Cluster Instances,or SQL failover clustering, you use SQL Server to create the high availability solution, then you can use Topology Builder to associate it with a Front End pool.</span></span>
  
<span data-ttu-id="65e6e-114">Se você usa a alta disponibilidade do servidor back-end em um pool de front-ends que está emparelhado com outro pool de front-end para recuperação de desastres, use a mesma solução de alta disponibilidade de back-end nos dois pools.</span><span class="sxs-lookup"><span data-stu-id="65e6e-114">If you use Back End Server high availability on a Front End pool that is paired with another Front End pool for disaster recovery, you should use the same Back End high availability solution in both pools.</span></span> 
  
## <a name="database-mirroring"></a><span data-ttu-id="65e6e-115">Espelhamento de banco de dados</span><span class="sxs-lookup"><span data-stu-id="65e6e-115">Database mirroring</span></span>

<span data-ttu-id="65e6e-116">O Skype for Business Server é compatível com o espelhamento com o seguinte software de banco de dados:</span><span class="sxs-lookup"><span data-stu-id="65e6e-116">Skype for Business Server supports mirroring with the following database software:</span></span>
  
- <span data-ttu-id="65e6e-117">SQL Server 2019, edição Enterprise e Standard Edition</span><span class="sxs-lookup"><span data-stu-id="65e6e-117">SQL Server 2019, both Enterprise Edition and Standard Edition</span></span>

- <span data-ttu-id="65e6e-118">SQL Server 2017, edição Enterprise e Standard Edition</span><span class="sxs-lookup"><span data-stu-id="65e6e-118">SQL Server 2017, both Enterprise Edition and Standard Edition</span></span>

- <span data-ttu-id="65e6e-119">SQL Server 2016, edição Enterprise e Standard Edition</span><span class="sxs-lookup"><span data-stu-id="65e6e-119">SQL Server 2016, both Enterprise Edition and Standard Edition</span></span>

- <span data-ttu-id="65e6e-120">SQL Server 2014, edição Enterprise e Standard Edition</span><span class="sxs-lookup"><span data-stu-id="65e6e-120">SQL Server 2014, both Enterprise Edition and Standard Edition</span></span>
    
- <span data-ttu-id="65e6e-121">SQL Server 2012 SP2 e CU2, edição Enterprise e Standard Edition</span><span class="sxs-lookup"><span data-stu-id="65e6e-121">SQL Server 2012 SP2 and CU2, both Enterprise Edition and Standard Edition</span></span>
    

> [!NOTE]
> <span data-ttu-id="65e6e-122">O espelhamento do SQL está disponível no Skype for Business Server 2015, mas não é mais compatível com o Skype for Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="65e6e-122">SQL Mirroring is available in Skype for Business Server 2015 but is no longer supported in Skype for Business Server 2019.</span></span> <span data-ttu-id="65e6e-123">Os grupos de disponibilidade AlwaysOn, instâncias de cluster de failover AlwaysOn (FCI) e métodos de cluster de failover do SQL são as únicas opções com suporte do Skype for Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="65e6e-123">The AlwaysOn Availability Groups, AlwaysOn Failover Cluster Instances (FCI), and SQL failover clustering methods are the only supported options with Skype for Business Server 2019.</span></span>
    
<span data-ttu-id="65e6e-124">O espelhamento de banco de dados assíncrono não é compatível com o back-end de alta disponibilidade do servidor do Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="65e6e-124">Asynchronous database mirroring is not supported for Back End Server high availability in Skype for Business Server.</span></span> <span data-ttu-id="65e6e-125">No restante deste documento, o termo espelhamento de banco de dados significa espelhamento sincronizado de banco de dados, salvo quando especificado o contrário.</span><span class="sxs-lookup"><span data-stu-id="65e6e-125">In the rest of this document, database mirroring means synchronous database mirroring, unless otherwise explicitly stated.</span></span> 
  
<span data-ttu-id="65e6e-126">Quando você implanta o espelhamento de banco de dados em um pool de front-end, todos os bancos de dados do Skype for Business Server no pool são espelhados, incluindo o repositório de gerenciamento central, se estiverem localizados nesse pool, bem como o banco de dados do aplicativo de grupo de resposta e o estacionamento de chamada banco de dados do aplicativo, se esses aplicativos estiverem sendo executados no pool.</span><span class="sxs-lookup"><span data-stu-id="65e6e-126">When you deploy database mirroring in a Front End pool, all Skype for Business Server databases in the pool are mirrored, including the Central Management store, if it is located in this pool, as well as the Response Group application database and the Call Park application database, if those applications are running in the pool.</span></span> 
  
<span data-ttu-id="65e6e-p105">Com o espelhamento de banco de dados, não é necessário usar o armazenamento compartilhado para os servidores. Cada servidor mantém sua cópia dos bancos de dados no armazenamento local.</span><span class="sxs-lookup"><span data-stu-id="65e6e-p105">With database mirroring, you do not need to use shared storage for the servers. Each server keeps its copy of the databases in local storage.</span></span> 
  
<span data-ttu-id="65e6e-p106">Você pode escolher implantar espelhamento de banco de dados com ou sem uma testemunha. Recomendamos usar uma testemunha porque isso habilita o failover do Servidor Back-End como automático. Caso contrário, um administrador terá que invocar manualmente o failover. Observe que mesmo se uma testemunha for implantada, um administrador pode invocar manualmente o failover do Servidor Back-End, se necessário.</span><span class="sxs-lookup"><span data-stu-id="65e6e-p106">You may choose to deploy database mirroring with or without a witness. We recommend using a witness because it enables failover of the Back End Server to be automatic. Otherwise, an administrator must manually invoke failover. Note that even if a witness is deployed, an administrator can manually invoke Back End Server failover, if necessary.</span></span>
  
<span data-ttu-id="65e6e-p107">Se você usar uma testemunha, poderá utilizar uma única testemunha para vários pares de Servidores Back-End. Não há correspondência exata entre testemunhas e pares de Servidores Back-End. As implantações que usam uma única testemunha para vários pares de Servidores Back-End não são tão resilientes quanto as topologias com uma testemunha separada para cada par de Servidores Back-End.</span><span class="sxs-lookup"><span data-stu-id="65e6e-p107">If you use a witness, you can use a single witness for multiple pairs of Back End Servers. There is no strict 1:1 correspondence between witnesses and pairs of Back End Servers. Deployments that use a single witness for multiple pairs of Back End Servers are not quite as resilient as topologies with a separate witness for each Back End Server pair.</span></span> 
  
### <a name="guidelines-for-planning-back-end-server-mirroring"></a><span data-ttu-id="65e6e-136">Diretrizes para o planejamento de espelhamento do Servidor Back-End</span><span class="sxs-lookup"><span data-stu-id="65e6e-136">Guidelines for planning Back End Server mirroring</span></span>

<span data-ttu-id="65e6e-137">Em geral, a configuração do espelhamento SQL entre os dois Servidores Back-End com uma testemunha requer:</span><span class="sxs-lookup"><span data-stu-id="65e6e-137">In general, setting up SQL mirroring between the two Back End Servers with a witness requires the following:</span></span>
  
- <span data-ttu-id="65e6e-138">A versão do servidor primário do SQL Server deve dar suporte ao espelhamento do SQL.</span><span class="sxs-lookup"><span data-stu-id="65e6e-138">The primary server's version of SQL Server must support SQL mirroring.</span></span>
    
- <span data-ttu-id="65e6e-139">Que o principal, o espelho e a testemunha (se implantada) tenham a mesma versão do SQL Server.</span><span class="sxs-lookup"><span data-stu-id="65e6e-139">The primary, mirror, and the witness (if deployed) must have the same version of SQL Server.</span></span> 
    
- <span data-ttu-id="65e6e-p108">Que o principal e o espelho tenham a mesma edição do SQL Server. A testemunha pode ter uma edição diferente.</span><span class="sxs-lookup"><span data-stu-id="65e6e-p108">The primary and the mirror must have the same edition of SQL Server. The witness may have a different edition.</span></span>
    
<span data-ttu-id="65e6e-142">Para as práticas recomendadas do SQL em termos de quais versões do SQL são compatíveis com uma função de testemunha, consulte ["testemunha de espelhamento de banco de dados"](https://go.microsoft.com/fwlink/p/?LinkId=247345) na biblioteca MSDN.</span><span class="sxs-lookup"><span data-stu-id="65e6e-142">For SQL best practices in terms of what SQL versions are supported for a Witness role, see  ["Database Mirroring Witness"](https://go.microsoft.com/fwlink/p/?LinkId=247345) in the MSDN Library.</span></span>
  
<span data-ttu-id="65e6e-143">Antes de configurar o espelhamento do servidor você deve configurar as permissões do banco de dados SQL corretamente.</span><span class="sxs-lookup"><span data-stu-id="65e6e-143">Before configuring server mirroring, you must first set up SQL database permissions correctly.</span></span> <span data-ttu-id="65e6e-144">Para obter detalhes, consulte ["configurar contas de logon para o espelhamento de banco de dados ou grupos de disponibilidade AlwaysOn (SQL Server)"](https://go.microsoft.com/fwlink/p/?LinkId=268454).</span><span class="sxs-lookup"><span data-stu-id="65e6e-144">For details, see  ["Set Up Login Accounts for Database Mirroring or AlwaysOn Availability Groups (SQL Server)"](https://go.microsoft.com/fwlink/p/?LinkId=268454).</span></span>
  
<span data-ttu-id="65e6e-p110">Com o espelhamento SQL, o modo de recuperação de banco de dados fica sempre definido como **Completo**, o que significa que você deve monitorar de perto o tamanho dos logs de transações, fazendo backup regular para evitar o esgotamento do espaço em disco dos Servidores Back-End. A frequência dos backups dos logs de transações depende da taxa de expansão dos logs, que, por sua vez, depende das transações do banco de dados provenientes de atividades de usuários no Pool de Front-Ends. Recomendamos que você determine a expansão dos logs de transação que é esperada para a carga de trabalho de implantação do Lync para que seja possível realizar um planejamento adequado. Os artigos a seguir fornecem mais informações sobre o gerenciamento de logs e backups do SQL:</span><span class="sxs-lookup"><span data-stu-id="65e6e-p110">With SQL mirroring, database recovery mode is always set to **Full**, which means you must closely monitor transaction log size and back up transaction logs on a regular basis to avoid running out of disk space on the Back End Servers. The frequency of transaction log backups depends on the log growth rate, which in turn depends on database transactions incurred by user activities on the Front End pool. We recommend that you determine how much transaction log growth is expected for your Lync deployment workload so that you can do the planning accordingly. The following articles provide additional information on SQL backup and log management:</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="65e6e-149">Usar o construtor de topologias ou cmdlets para configurar e remover o espelhamento do SQL só tem suporte quando os servidores primário, espelho e testemunha (se desejado) pertencem ao mesmo domínio.</span><span class="sxs-lookup"><span data-stu-id="65e6e-149">Using Topology Builder or cmdlets to set up and remove SQL mirroring is supported only when the primary, mirror, and witness (if desired) servers all belong to the same domain.</span></span> <span data-ttu-id="65e6e-150">Se quiser configurar o espelhamento SQL entre servidores de domínios diferentes, consulte a documentação do SQL Server.</span><span class="sxs-lookup"><span data-stu-id="65e6e-150">If you want to set up SQL mirroring among servers in different domains, see your SQL Server documentation.</span></span> 

> [!NOTE]
> <span data-ttu-id="65e6e-151">O espelhamento do SQL está disponível no Skype for Business Server 2015, mas não é mais compatível com o Skype for Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="65e6e-151">SQL Mirroring is available in Skype for Business Server 2015 but is no longer supported in Skype for Business Server 2019.</span></span> <span data-ttu-id="65e6e-152">Os grupos de disponibilidade AlwaysOn, as instâncias de cluster de failover AlwaysOn (FCI) e os métodos de cluster de failover do SQL são preferidos com o Skype for Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="65e6e-152">The  AlwaysOn Availability Groups, AlwaysOn Failover Cluster Instances (FCI), and SQL failover clustering methods are preferred with Skype for Business Server 2019.</span></span>
  
### <a name="recovery-time-for-automatic-back-end-server-failover-with-database-mirroring"></a><span data-ttu-id="65e6e-153">Tempo de recuperação para failover automático do Servidor Back-End com espelhamento de banco de dados</span><span class="sxs-lookup"><span data-stu-id="65e6e-153">Recovery time for automatic Back End Server failover with database mirroring</span></span>

<span data-ttu-id="65e6e-p113">Para o failover automático do Servidor Back-End com espelhamento de banco de dados, a meta de engenharia para o objetivo de tempo de recuperação (RTO) é de 5 minutos. Como o espelhamento de banco de dados é síncrono, não há previsão de perda de dados durante as falhas do Servidor Back-End, exceto nas raras ocasiões em que tanto os Servidores Front-End como o Servidor Back-End ficam inativos simultaneamente enquanto os dados são movidos entre eles. A meta de engenharia para o objetivo do ponto de recuperação (RPO) é de 5 minutos.</span><span class="sxs-lookup"><span data-stu-id="65e6e-p113">For automatic Back End failover with database mirroring, the engineering target for recovery time objective (RTO) is 5 minutes. Because of the synchronous database mirroring, we do not anticipate data loss during Back End Server failures except in rare occasions when both the Front End Servers and the Back End Server go down simultaneously while data is being moved between the servers. The engineering target for recovery point objective (RPO) is 5 minutes.</span></span>
  
### <a name="user-experience-during-back-end-server-failure-with-database-mirroring"></a><span data-ttu-id="65e6e-157">Experiência do usuário durante falha do Servidor Back-End com espelhamento de banco de dados</span><span class="sxs-lookup"><span data-stu-id="65e6e-157">User experience during Back End Server failure with database mirroring</span></span>

<span data-ttu-id="65e6e-158">A experiência do usuário durante uma falha depende da natureza da falha e da topologia.</span><span class="sxs-lookup"><span data-stu-id="65e6e-158">User experience during a failure depends on the nature of the failure, and on your topology.</span></span>
  
<span data-ttu-id="65e6e-p114">Se você usa o espelhamento de banco de dados com uma testemunha configurada e o servidor principal falhar, o failover do Servidor Back-End é executado rápida e automaticamente. Os usuários ativos não devem notar a interrupção em suas sessões contínuas.</span><span class="sxs-lookup"><span data-stu-id="65e6e-p114">If you use database mirroring and have a witness configured, and the principal fails, Back End Server failover happens automatically and quickly. Active users should not notice much interruption to their ongoing sessions.</span></span>
  
<span data-ttu-id="65e6e-161">Se não houver uma testemunha configurada, pode levar algum tempo para o administrador invocar manualmente o failover.</span><span class="sxs-lookup"><span data-stu-id="65e6e-161">If there is no witness configured, it will take some time for the administrator to manually invoke the failover.</span></span> <span data-ttu-id="65e6e-162">Durante este tempo, os usuários ativos podem ser afetados.</span><span class="sxs-lookup"><span data-stu-id="65e6e-162">During that time, active users may be affected.</span></span> <span data-ttu-id="65e6e-163">Eles continuam suas sessões normalmente por cerca de 30 minutos.</span><span class="sxs-lookup"><span data-stu-id="65e6e-163">They will continue their sessions as normal for about 30 minutes.</span></span> <span data-ttu-id="65e6e-164">Se o principal ainda não for restaurado ou se um administrador não tiver failover para o backup, os usuários terão alternado para o modo de resiliência, o que significa que eles não poderão executar tarefas que exijam uma alteração persistente no Lync Server (como adicionar um contato).</span><span class="sxs-lookup"><span data-stu-id="65e6e-164">If the primary is still not restored, or an administrator has not failed over to the backup, then users are switched to Resiliency mode, meaning that they are unable to perform tasks that require a persistent change on Lync Server (such as adding a contact).</span></span>
  
<span data-ttu-id="65e6e-p116">Se o servidor principal e o Servidor Back-End espelho falharem ou se um desses servidores e a testemunha falharem, o Servidor Back-End se tornará indisponível (mesmo se o servidor principal ainda estiver funcionando). Nesse caso, os usuários ativos serão transferidos para o modo de Resiliência após um certo tempo.</span><span class="sxs-lookup"><span data-stu-id="65e6e-p116">If both the principal and the mirror Back End Servers fail, or if one of those servers and the witness fails, the Back End Server will become unavailable (even if it is the principal that is still working). In this case, active users are switched to Resiliency mode after some time.</span></span>
  
## <a name="alwayson-availability-groups-and-alwayson-failover-cluster-instances"></a><span data-ttu-id="65e6e-167">Grupos de disponibilidade AlwaysOn e instâncias do cluster de failover AlwaysOn</span><span class="sxs-lookup"><span data-stu-id="65e6e-167">AlwaysOn Availability Groups and AlwaysOn Failover Cluster Instances</span></span>

<span data-ttu-id="65e6e-168">O Skype for Business Server é compatível com os grupos de disponibilidade AlwaysOn apenas como ativos/passivos, não ativos/ativos.</span><span class="sxs-lookup"><span data-stu-id="65e6e-168">Skype for Business Server supports AlwaysOn Availability Groups only as active/passive, not active/active.</span></span> 
  
<span data-ttu-id="65e6e-169">Para usar os grupos de disponibilidade AlwaysOn ou instâncias de cluster de failover AlwaysOn, você primeiro usa o SQL Server para configurar e configurar a solução de alta disponibilidade.</span><span class="sxs-lookup"><span data-stu-id="65e6e-169">To use AlwaysOn Availability Groups or AlwaysOn Failover Cluster Instances, you first use SQL Server to set up and configure the high availability solution.</span></span> <span data-ttu-id="65e6e-170">Em seguida, você pode usar o construtor de topologias para associá-lo a um pool de front-end.</span><span class="sxs-lookup"><span data-stu-id="65e6e-170">You can then use Topology Builder to associate it with a Front End pool.</span></span>

<span data-ttu-id="65e6e-171">O Skype for Business Server é compatível com o AlwaysOn com o seguinte software de banco de dados:</span><span class="sxs-lookup"><span data-stu-id="65e6e-171">Skype for Business Server supports AlwaysOn with the following database software:</span></span>

- <span data-ttu-id="65e6e-172">SQL Server 2019 Enterprise Edition</span><span class="sxs-lookup"><span data-stu-id="65e6e-172">SQL Server 2019 Enterprise Edition</span></span>

- <span data-ttu-id="65e6e-173">SQL Server 2019 Standard Edition com limitações, consulte nota abaixo</span><span class="sxs-lookup"><span data-stu-id="65e6e-173">SQL Server 2019 Standard Edition with limitations, see note below</span></span>

- <span data-ttu-id="65e6e-174">SQL Server 2017 Enterprise Edition</span><span class="sxs-lookup"><span data-stu-id="65e6e-174">SQL Server 2017 Enterprise Edition</span></span>

- <span data-ttu-id="65e6e-175">SQL Server 2017 Standard Edition com limitações, consulte nota abaixo</span><span class="sxs-lookup"><span data-stu-id="65e6e-175">SQL Server 2017 Standard Edition with limitations, see note below</span></span>

- <span data-ttu-id="65e6e-176">SQL Server 2016 Enterprise Edition</span><span class="sxs-lookup"><span data-stu-id="65e6e-176">SQL Server 2016 Enterprise Edition</span></span>

- <span data-ttu-id="65e6e-177">SQL Server 2016 Standard Edition com limitações, consulte nota abaixo</span><span class="sxs-lookup"><span data-stu-id="65e6e-177">SQL Server 2016 Standard Edition with limitations, see note below</span></span>

- <span data-ttu-id="65e6e-178">SQL Server 2014 Enterprise Edition</span><span class="sxs-lookup"><span data-stu-id="65e6e-178">SQL Server 2014 Enterprise Edition</span></span>
    
- <span data-ttu-id="65e6e-179">SQL Server 2012 SP2 e CU2 Enterprise Edition</span><span class="sxs-lookup"><span data-stu-id="65e6e-179">SQL Server 2012 SP2 and CU2 Enterprise Edition</span></span>

> [!NOTE]
> <span data-ttu-id="65e6e-180">O SQL Server 2019, o 2017 e o 2016 são as únicas versões aceitas pelo Skype for Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="65e6e-180">SQL Server 2019, 2017, and 2016 are the only versions supported by Skype for Business Server 2019.</span></span>

> [!NOTE]
> <span data-ttu-id="65e6e-181">**Não** há suporte para grupos de disponibilidade AlwaysOn nas edições do SQL 2016, 2017 e 2019 Standard, mas você pode usar instâncias de cluster de failover sempre em failover.</span><span class="sxs-lookup"><span data-stu-id="65e6e-181">Always On Availability Groups is **not** supported in SQL 2016, 2017, and 2019 Standard Editions but you can use Always On Failover Cluster Instances.</span></span> <span data-ttu-id="65e6e-182">Veja as [edições e os recursos com suporte do SQL Server 2016](https://docs.microsoft.com/sql/sql-server/editions-and-components-of-sql-server-2016?view=sql-server-2017) para saber mais.</span><span class="sxs-lookup"><span data-stu-id="65e6e-182">See [Editions and supported features of SQL Server 2016](https://docs.microsoft.com/sql/sql-server/editions-and-components-of-sql-server-2016?view=sql-server-2017) to learn more.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="65e6e-183">Os nomes de instâncias para várias instâncias do grupo de disponibilidade AlwaysOn devem ser iguais.</span><span class="sxs-lookup"><span data-stu-id="65e6e-183">Instance names for multiple AlwaysOn Availability Group instances must be the same.</span></span> 
  
<span data-ttu-id="65e6e-184">Para ver as etapas de implantação dos grupos de disponibilidade AlwaysOn, consulte [implantar um grupo de disponibilidade AlwaysOn em um servidor back-end no Skype for Business Server](../../deploy/deploy-high-availability-and-disaster-recovery/alwayson-availability-group.md).</span><span class="sxs-lookup"><span data-stu-id="65e6e-184">For steps for deploying AlwaysOn Availability Groups, see [Deploy an AlwaysOn Availability Group on a Back End Server in Skype for Business Server](../../deploy/deploy-high-availability-and-disaster-recovery/alwayson-availability-group.md).</span></span>
  
## <a name="sql-server-failover-clustering"></a><span data-ttu-id="65e6e-185">Clustering de Failover do SQL Server</span><span class="sxs-lookup"><span data-stu-id="65e6e-185">SQL Server Failover Clustering</span></span>

<span data-ttu-id="65e6e-186">O Skype for Business Server oferece suporte ao cluster de failover do SQL Server com o seguinte software de banco de dados:</span><span class="sxs-lookup"><span data-stu-id="65e6e-186">Skype for Business Server supports SQL Server failover clustering with the following database software:</span></span>
  
- <span data-ttu-id="65e6e-187">SQL Server 2019, edição Enterprise e Standard Edition</span><span class="sxs-lookup"><span data-stu-id="65e6e-187">SQL Server 2019, both Enterprise Edition and Standard Edition</span></span>

- <span data-ttu-id="65e6e-188">SQL Server 2017, edição Enterprise e Standard Edition</span><span class="sxs-lookup"><span data-stu-id="65e6e-188">SQL Server 2017, both Enterprise Edition and Standard Edition</span></span>

- <span data-ttu-id="65e6e-189">SQL Server 2016, edição Enterprise e Standard Edition</span><span class="sxs-lookup"><span data-stu-id="65e6e-189">SQL Server 2016, both Enterprise Edition and Standard Edition</span></span>

- <span data-ttu-id="65e6e-190">SQL Server 2014, edição Enterprise e Standard Edition</span><span class="sxs-lookup"><span data-stu-id="65e6e-190">SQL Server 2014, both Enterprise Edition and Standard Edition</span></span>
    
- <span data-ttu-id="65e6e-191">SQL Server 2012 SP2 e CU2, edição Enterprise e Standard Edition</span><span class="sxs-lookup"><span data-stu-id="65e6e-191">SQL Server 2012 SP2 and CU2, both Enterprise Edition and Standard Edition</span></span>

<span data-ttu-id="65e6e-192">Para usar o cluster de failover do SQL, você deve primeiro configurar e configurar o cluster do SQL Server antes de implantar seu pool de front-ends.</span><span class="sxs-lookup"><span data-stu-id="65e6e-192">To use SQL failover clustering, you should first set up and configure the SQL Server cluster before deploying your Front End pool.</span></span> <span data-ttu-id="65e6e-193">Para obter práticas recomendadas e instruções de configuração para clustering de failover no SQL [https://technet.microsoft.com/library/hh231721.aspx](https://technet.microsoft.com/library/hh231721.aspx)Server 2012, consulte.</span><span class="sxs-lookup"><span data-stu-id="65e6e-193">For best practices and setup instructions for failover clustering in SQL Server 2012, see [https://technet.microsoft.com/library/hh231721.aspx](https://technet.microsoft.com/library/hh231721.aspx).</span></span>

> [!NOTE]
> <span data-ttu-id="65e6e-194">O SQL Server 2019, o 2017 e o SQL Server 2016 são as únicas versões compatíveis com o Skype for Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="65e6e-194">SQL Server 2019, 2017, and SQL Server 2016 are the only versions supported by Skype for Business Server 2019.</span></span>
    
<span data-ttu-id="65e6e-195">Para usar o cluster de failover do SQL, você deve primeiro configurar e configurar o cluster do SQL Server antes de implantar seu pool de front-ends.</span><span class="sxs-lookup"><span data-stu-id="65e6e-195">To use SQL failover clustering, you should first set up and configure the SQL Server cluster before deploying your Front End pool.</span></span> <span data-ttu-id="65e6e-196">Para obter práticas recomendadas e instruções de configuração para clustering de failover no SQL Server 2014 [https://technet.microsoft.com/library/hh231721.aspx](https://technet.microsoft.com/library/hh231721.aspx)e 2016, consulte.</span><span class="sxs-lookup"><span data-stu-id="65e6e-196">For best practices and setup instructions for failover clustering in SQL Server 2014 and 2016, see [https://technet.microsoft.com/library/hh231721.aspx](https://technet.microsoft.com/library/hh231721.aspx).</span></span> <span data-ttu-id="65e6e-197">Para o cluster de failover no SQL Server 2008, [https://technet.microsoft.com/library/ms189134(v=sql.105).aspx](https://technet.microsoft.com/library/ms189134%28v=sql.105%29.aspx)consulte.</span><span class="sxs-lookup"><span data-stu-id="65e6e-197">For failover clustering in SQL Server 2008, see [https://technet.microsoft.com/library/ms189134(v=sql.105).aspx](https://technet.microsoft.com/library/ms189134%28v=sql.105%29.aspx).</span></span>
  
<span data-ttu-id="65e6e-p121">Ao instalar o SQL Server, o SQL Server Management Studio deve ser instalado para gerenciar os locais de bases de dados e arquivos de log. O SQL Server Management Studio é instalado como componente opcional quando da instalação do SQL Server.</span><span class="sxs-lookup"><span data-stu-id="65e6e-p121">When you install SQL Server, you should install SQL Server Management Studio to manage the locations for database and log file locations. SQL Server Management Studio is installed as an optional component when you install SQL Server.</span></span>
  
