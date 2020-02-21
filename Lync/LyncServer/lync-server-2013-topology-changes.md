---
title: Alterações de topologia do Lync Server 2013
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Topology changes
ms:assetid: 9e40ef93-9ab0-498c-9bbf-f94584353e53
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688153(v=OCS.15)
ms:contentKeyID: 49733756
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ac7cf9fe1bdabcba4b0b5fc1134f1835407041a5
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42193524"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="topology-changes-in-lync-server-2013"></a><span data-ttu-id="e3115-102">Alterações de topologia no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e3115-102">Topology changes in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e3115-103">_**Última modificação do tópico:** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="e3115-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="e3115-104">Os requisitos e as considerações de topologia para o Lync Server 2013 são diferentes das versões anteriores, conforme descrito nesta seção.</span><span class="sxs-lookup"><span data-stu-id="e3115-104">Topology requirements and considerations for Lync Server 2013 are different from those for earlier releases, as described in this section.</span></span>

<div>

## <a name="new-front-end-pools-architecture"></a><span data-ttu-id="e3115-105">Nova arquitetura de pools de front end</span><span class="sxs-lookup"><span data-stu-id="e3115-105">New Front End Pools Architecture</span></span>

<span data-ttu-id="e3115-106">No Lync Server 2013, a arquitetura dos pools de front-ends Enterprise Edition foi alterada para uma arquitetura de sistemas distribuídos.</span><span class="sxs-lookup"><span data-stu-id="e3115-106">In Lync Server 2013, the architecture of Enterprise Edition Front End pools has changed to a distributed systems architecture.</span></span>

<span data-ttu-id="e3115-p101">Com essa nova arquitetura, o banco de dados de backend não é mais o armazenamento de dados em tempo real no pool. Informações sobre um usuário específico são mantidas em três servidores de front end no pool. Para cada usuário, um servidor de front end age como o mestre das informações desse usuário, e os outros dois servidores de front end servem como réplicas. Se um servidor de front end cair, outro servidor de front end que servia como réplica será automaticamente promovido a mestre.</span><span class="sxs-lookup"><span data-stu-id="e3115-p101">With this new architecture, the Back End database is no longer the real-time data store in a pool. Information about a particular user is kept on three Front End Servers in the pool. For each user, one Front End Server acts as the master for that user’s information, and two other Front End Servers serve as replicas. If a Front End Server goes down, another Front End Server which served as a replica is automatically promoted to master.</span></span>

<span data-ttu-id="e3115-111">Isso acontece nos bastidores e os administradores não precisam saber quais servidores de front end são os mestres para quais usuários.</span><span class="sxs-lookup"><span data-stu-id="e3115-111">This happens behind the scenes, and administrators do not need to know which Front End Servers are the masters for which users.</span></span> <span data-ttu-id="e3115-112">Essa distribuição de armazenamento de dados melhora o desempenho e a escalabilidade dentro do pool e elimina o ponto único de falha de um único servidor back-end.</span><span class="sxs-lookup"><span data-stu-id="e3115-112">This distribution of data storage improves performance and scalability within the pool, and eliminates the single point of failure of a single Back End Server.</span></span>

<span data-ttu-id="e3115-113">O servidor de back end serve como armazenamento de back up do usuário e dados de conferência, e também é o armazenamento principal de outros bancos de dados, como o banco de dados do Grupo de Resposta.</span><span class="sxs-lookup"><span data-stu-id="e3115-113">The Back End Server serves as backup storage for user and conference data, and is also the primary storage for other databases such as the Response Group database.</span></span>

<span data-ttu-id="e3115-114">Essas melhorias também significam que há mudanças em como planejar e manter seus pools.</span><span class="sxs-lookup"><span data-stu-id="e3115-114">These improvements also mean there are changes in how you plan and maintain your pools.</span></span> <span data-ttu-id="e3115-115">Recomendamos que todos os pools de front-ends Enterprise Edition incluam pelo menos três servidores front-end, para fornecer o número total de réplicas para as quais a arquitetura do pool de front-ends foi projetada.</span><span class="sxs-lookup"><span data-stu-id="e3115-115">We recommend that all your Enterprise Edition Front End pools include at least three Front End Servers, to provide the full number of replicas that the Front End pool architecture is designed for.</span></span> <span data-ttu-id="e3115-116">Além disso, você deve seguir determinados procedimentos ao adicionar servidores a um pool de front-ends, remover servidores dele ou atualizar servidores.</span><span class="sxs-lookup"><span data-stu-id="e3115-116">Additionally, you must follow certain procedures when adding servers to a Front End pool, removing servers from it, or upgrading servers.</span></span> <span data-ttu-id="e3115-117">Para obter mais informações, consulte [topologias e componentes para servidores front-end, mensagens instantâneas e presença no Lync Server 2013](lync-server-2013-topologies-and-components-for-front-end-servers-instant-messaging-and-presence.md).</span><span class="sxs-lookup"><span data-stu-id="e3115-117">For more information, see [Topologies and components for Front End Servers, instant messaging, and presence in Lync Server 2013](lync-server-2013-topologies-and-components-for-front-end-servers-instant-messaging-and-presence.md).</span></span>

<div>

## <a name="server-role-topology-changes"></a><span data-ttu-id="e3115-118">Alterações na topologia de função do servidor</span><span class="sxs-lookup"><span data-stu-id="e3115-118">Server Role Topology Changes</span></span>

<span data-ttu-id="e3115-119">Algumas funções de servidor que eram executadas antes em servidores separados são agora consolidadas na função de servidor de front end, permitindo economizar em custos de hardware</span><span class="sxs-lookup"><span data-stu-id="e3115-119">Some server roles that previously ran on separate servers are now consolidated into the Front End Server role, enabling you to save on hardware costs</span></span>

  - <span data-ttu-id="e3115-120">No Lync Server 2013, o servidor de conferência A/V é sempre colocado com o servidor front-end.</span><span class="sxs-lookup"><span data-stu-id="e3115-120">In Lync Server 2013, A/V Conferencing Server is always collocated with Front End Server.</span></span>

  - <span data-ttu-id="e3115-p104">Os servidores de front end de Monitoramento e arquivamento são sempre colocados com o servidor de front end. O Monitoramento e arquivamento exigem, cada um deles, um banco de dados de backend separado, que pode ser colocado no mesmo servidor do banco de dados de backend do pool de front end, ou pode ser hospedado em servidores de backend separados.</span><span class="sxs-lookup"><span data-stu-id="e3115-p104">The front ends for both Monitoring and Archiving are now always collocated with Front End Server. Monitoring and Archiving each still require a separate Back-End Database, which can be collocated on the same server as the Front End Pool’s back-end database, or can be hosted on separate Back-End Servers.</span></span>

  - <span data-ttu-id="e3115-123">O servidor de chat persistente agora é uma função de servidor.</span><span class="sxs-lookup"><span data-stu-id="e3115-123">Persistent Chat Server is now a server role.</span></span> <span data-ttu-id="e3115-124">No Microsoft Lync Server 2010, o servidor de chat de grupo era um aplicativo confiável de terceiros para o Microsoft Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="e3115-124">In Microsoft Lync Server 2010, Group Chat Server was a third-party trusted application for Microsoft Lync Server 2010.</span></span> <span data-ttu-id="e3115-125">No Lync Server 2013, a funcionalidade do servidor de chat persistente é implementada usando três novas funções de servidor:</span><span class="sxs-lookup"><span data-stu-id="e3115-125">In Lync Server 2013, Persistent Chat Server functionality is implemented using three new server roles:</span></span>
    
      - <span data-ttu-id="e3115-126">**PersistentChatService:** Principais serviços do servidor de chat persistente implementados como função de front-end</span><span class="sxs-lookup"><span data-stu-id="e3115-126">**PersistentChatService:** Main Persistent Chat Server services implemented as a front end role</span></span>
    
      - <span data-ttu-id="e3115-127">**PersistentChatStore:** Função de servidor back-end</span><span class="sxs-lookup"><span data-stu-id="e3115-127">**PersistentChatStore:** Back End Server role</span></span>
    
      - <span data-ttu-id="e3115-128">**PersistentChatComplianceStore:** Função de servidor back-end para conformidade de chat persistente</span><span class="sxs-lookup"><span data-stu-id="e3115-128">**PersistentChatComplianceStore:** Back End Server role for Persistent Chat Compliance</span></span>

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

