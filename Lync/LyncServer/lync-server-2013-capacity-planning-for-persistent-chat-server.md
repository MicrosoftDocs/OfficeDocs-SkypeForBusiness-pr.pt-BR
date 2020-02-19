---
title: 'Lync Server 2013: planejamento de capacidade para servidor de chat persistente'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Capacity planning for Persistent Chat Server
ms:assetid: 7a850cd5-c789-4795-a8ff-083be21ae784
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615006(v=OCS.15)
ms:contentKeyID: 48184580
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d0cd27f961d3b4857cf13d5786897bd29a657851
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42135558"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="capacity-planning-for-persistent-chat-server-in-lync-server-2013"></a><span data-ttu-id="3f6ab-102">Planejamento de capacidade para servidor de chat persistente no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3f6ab-102">Capacity planning for Persistent Chat Server in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3f6ab-103">_**Última modificação do tópico:** 2012-10-05_</span><span class="sxs-lookup"><span data-stu-id="3f6ab-103">_**Topic Last Modified:** 2012-10-05_</span></span>

<span data-ttu-id="3f6ab-104">O servidor de chat persistente pode executar chat em tempo real de vários usuários que pode persistir em futuras recuperações e pesquisa.</span><span class="sxs-lookup"><span data-stu-id="3f6ab-104">Persistent Chat Server can perform multi-user real-time chat that can persist for future retrieval and search.</span></span> <span data-ttu-id="3f6ab-105">Ao contrário de mensagens instantâneas de grupo (IM) salvas na caixa de correio de um usuário, se o histórico de conversa estiver configurado, uma sessão de servidor de chat persistente permanecerá aberta e o conteúdo será salvo em um servidor, junto com as mensagens, arquivos, URLs e outros dados que fazem parte de um conversa em andamento.</span><span class="sxs-lookup"><span data-stu-id="3f6ab-105">Unlike group instant messaging (IM) that is saved in a user’s mailbox if conversation history is configured, a Persistent Chat Server session stays open longer, and the content is saved on a server, along with the messages, files, URLs, and other data that are part of an ongoing conversation.</span></span>

<span data-ttu-id="3f6ab-106">O planejamento de capacidade é uma parte importante da preparação para implantar o servidor de chat persistente.</span><span class="sxs-lookup"><span data-stu-id="3f6ab-106">Capacity planning is an important part of preparing to deploy Persistent Chat Server.</span></span> <span data-ttu-id="3f6ab-107">Este tópico fornece detalhes sobre topologias de servidor de chat persistente compatíveis e tabelas de planejamento de capacidade que você pode usar para determinar a melhor configuração para sua implantação.</span><span class="sxs-lookup"><span data-stu-id="3f6ab-107">This topic provides details about supported Persistent Chat Server topologies and capacity planning tables that you can use to determine the best configuration for your deployment.</span></span> <span data-ttu-id="3f6ab-108">Também descreve como gerenciar melhor as implantações de servidor de chat persistente que exigem mais capacidade em horários de pico.</span><span class="sxs-lookup"><span data-stu-id="3f6ab-108">It also describes how to best manage Persistent Chat Server deployments that require greater capacity at peak times.</span></span>

<span data-ttu-id="3f6ab-109">Para baixar o servidor de chat persistente, consulte "Microsoft Lync Server 13 persistent chat Server [https://go.microsoft.com/fwlink/p/?linkId=209539](https://go.microsoft.com/fwlink/p/?linkid=209539)" em.</span><span class="sxs-lookup"><span data-stu-id="3f6ab-109">To download Persistent Chat Server, see "Microsoft Lync Server 13 Persistent Chat Server" at [https://go.microsoft.com/fwlink/p/?linkId=209539](https://go.microsoft.com/fwlink/p/?linkid=209539).</span></span>

<span data-ttu-id="3f6ab-110">Para obter detalhes sobre como instalar o servidor de chat persistente, consulte [instalando o servidor de chat persistente no Lync Server 2013](lync-server-2013-installing-persistent-chat-server.md) e [Configurando o servidor de chat persistente no Lync Server 2013](lync-server-2013-configuring-persistent-chat-server.md) na documentação de implantação.</span><span class="sxs-lookup"><span data-stu-id="3f6ab-110">For details about installing Persistent Chat Server, see [Installing Persistent Chat Server in Lync Server 2013](lync-server-2013-installing-persistent-chat-server.md) and [Configuring Persistent Chat Server in Lync Server 2013](lync-server-2013-configuring-persistent-chat-server.md) in the Deployment documentation.</span></span>

<span data-ttu-id="3f6ab-111">As ferramentas de suporte, como a ferramenta de planejamento do Lync Server, podem ajudá-lo ainda mais no planejamento da capacidade.</span><span class="sxs-lookup"><span data-stu-id="3f6ab-111">Support tools, such as Lync Server Planning Tool, can further assist you with capacity planning.</span></span> <span data-ttu-id="3f6ab-112">Para obter detalhes sobre a ferramenta de planejamento, consulte [iniciando o processo de planejamento do Lync Server 2013](lync-server-2013-beginning-the-planning-process.md) na documentação de planejamento.</span><span class="sxs-lookup"><span data-stu-id="3f6ab-112">For details about the Planning Tool, see [Beginning the planning process for Lync Server 2013](lync-server-2013-beginning-the-planning-process.md) in the Planning documentation.</span></span>

<div>

## <a name="persistent-chat-server-supported-topologies"></a><span data-ttu-id="3f6ab-113">Topologias compatíveis com o servidor de chat persistente</span><span class="sxs-lookup"><span data-stu-id="3f6ab-113">Persistent Chat Server Supported Topologies</span></span>

<span data-ttu-id="3f6ab-114">Você pode implantar o servidor de chat persistente em pools de servidor único ou de vários servidores, com uma topologia de pool único ou de vários pools.</span><span class="sxs-lookup"><span data-stu-id="3f6ab-114">You can deploy Persistent Chat Server in single-server or multiple-server pools, and with single-pool or multiple-pool topology.</span></span>

<span data-ttu-id="3f6ab-115">Agora também há suporte para o servidor de chat persistente no servidor Standard Edition para novas implantações do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="3f6ab-115">We now also support Persistent Chat Server on Standard Edition server for new Lync Server 2013 deployments.</span></span> <span data-ttu-id="3f6ab-116">No entanto, o desempenho e a escala serão afetados, e como não há uma opção de alta disponibilidade para essa nova implantação, esperamos que você use isso principalmente para fins de verificação de conceito, avaliação e assim por diante.</span><span class="sxs-lookup"><span data-stu-id="3f6ab-116">However, performance and scale will be affected, and because there is no high availability option for this new deployment, we expect you to use this primarily for the purposes of proof of concept, evaluation, and so on.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="3f6ab-117">Para obter detalhes adicionais sobre ambas as topologias, consulte <A href="lync-server-2013-planning-for-persistent-chat-server.md">Planning for persistent chat Server in Lync server 2013</A> , neste conjunto de documentação, e <A href="lync-server-2013-deploying-persistent-chat-server.md">implantando o servidor de chat persistente no Lync Server 2013</A> na documentação de implantação.</span><span class="sxs-lookup"><span data-stu-id="3f6ab-117">For additional details about both topologies, see <A href="lync-server-2013-planning-for-persistent-chat-server.md">Planning for Persistent Chat Server in Lync Server 2013</A> in this documentation set and <A href="lync-server-2013-deploying-persistent-chat-server.md">Deploying Persistent Chat Server in Lync Server 2013</A> in the Deployment documentation.</span></span>



</div>

<div>

## <a name="single-server-topology"></a><span data-ttu-id="3f6ab-118">Topologia de servidor único</span><span class="sxs-lookup"><span data-stu-id="3f6ab-118">Single-Server Topology</span></span>

<span data-ttu-id="3f6ab-119">A configuração mínima e a implantação mais simples para o servidor de chat persistente é uma topologia de servidor front-end de servidor de chat persistente única.</span><span class="sxs-lookup"><span data-stu-id="3f6ab-119">The minimum configuration and simplest deployment for Persistent Chat Server is a single Persistent Chat Server Front End Server topology.</span></span> <span data-ttu-id="3f6ab-120">Esta implantação requer um único servidor que executa o servidor de chat persistente (que, opcionalmente, executa o serviço de conformidade, se a conformidade estiver habilitada), um servidor que hospeda o banco de dados do SQL Server e, se a conformidade for necessária, o banco de dados do SQL Server para armazenar o dados de conformidade.</span><span class="sxs-lookup"><span data-stu-id="3f6ab-120">This deployment requires a single server that runs Persistent Chat Server (which optionally runs the Compliance service, if compliance is enabled), a server that hosts both the SQL Server database, and if compliance is required, the SQL Server database to store the compliance data.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="3f6ab-121">Não é possível adicionar mais servidores a um pool de servidores de chat persistente iniciado como uma implantação de servidor único no construtor de topologias.</span><span class="sxs-lookup"><span data-stu-id="3f6ab-121">You cannot add additional servers to a Persistent Chat Server pool that is started as a single-server deployment in Topology Builder.</span></span> <span data-ttu-id="3f6ab-122">É recomendável usar a topologia de pool de vários servidores, mesmo que você esteja usando um único servidor.</span><span class="sxs-lookup"><span data-stu-id="3f6ab-122">We recommend using the multiple-server pool topology, even if you’re using a single server.</span></span> <span data-ttu-id="3f6ab-123">Isso é possível para que você possa adicionar mais servidores posteriormente, se necessário.</span><span class="sxs-lookup"><span data-stu-id="3f6ab-123">This is so that you’ll be able to add more servers later, if it's necessary.</span></span> 


</div>

<span data-ttu-id="3f6ab-124">A figura a seguir mostra todos os componentes obrigatórios e opcionais de uma topologia para um único servidor de front-end do servidor de chat persistente com conformidade.</span><span class="sxs-lookup"><span data-stu-id="3f6ab-124">The following figure shows all required and optional components of a topology for a single Persistent Chat Server Front End Server with compliance.</span></span>

<span data-ttu-id="3f6ab-125">**Servidor de Chat Persistente único**</span><span class="sxs-lookup"><span data-stu-id="3f6ab-125">**Single Persistent Chat Server**</span></span>

<span data-ttu-id="3f6ab-126">![Topologia de servidor único com serviço de conformidade](images/Gg398500.9168fa52-61e0-4d17-a14d-45fd32e81456(OCS.15).jpg "Topologia de servidor único com serviço de conformidade")</span><span class="sxs-lookup"><span data-stu-id="3f6ab-126">![Single server topology with Compliance service](images/Gg398500.9168fa52-61e0-4d17-a14d-45fd32e81456(OCS.15).jpg "Single server topology with Compliance service")</span></span>

</div>

<div>

## <a name="multiple-server-topology"></a><span data-ttu-id="3f6ab-127">Topologia de vários servidores</span><span class="sxs-lookup"><span data-stu-id="3f6ab-127">Multiple-Server Topology</span></span>

<span data-ttu-id="3f6ab-128">Para fornecer maior capacidade e confiabilidade, você pode implantar uma topologia de vários servidores, conforme descrito em [Planning for persistent chat Server in Lync server 2013](lync-server-2013-planning-for-persistent-chat-server.md).</span><span class="sxs-lookup"><span data-stu-id="3f6ab-128">To provide greater capacity and reliability, you can deploy a multiple-server topology, as described in [Planning for Persistent Chat Server in Lync Server 2013](lync-server-2013-planning-for-persistent-chat-server.md).</span></span> <span data-ttu-id="3f6ab-129">A topologia de vários servidores pode incluir até quatro computadores ativos que executam o servidor de chat persistente (as configurações de alta disponibilidade e recuperação de desastre permitirão até oito, mas apenas quatro podem estar ativas e as quatro restantes em espera).</span><span class="sxs-lookup"><span data-stu-id="3f6ab-129">The multiple-server topology can include as many as four active computers running Persistent Chat Server (high availability and disaster recovery configurations will allow up to eight, but only four can be active and the remaining four on standby).</span></span> <span data-ttu-id="3f6ab-130">Cada servidor pode suportar até 20.000 usuários simultâneos, para um total de 80.000 usuários simultâneos conectados a um pool de servidores de chat persistente com quatro servidores.</span><span class="sxs-lookup"><span data-stu-id="3f6ab-130">Each server can support as many as 20,000 concurrent users, for a total of 80,000 concurrent users connected to a Persistent Chat Server pool with 4 servers.</span></span> <span data-ttu-id="3f6ab-131">Uma topologia de vários servidores é o mesmo que a topologia de servidor único, exceto pelo fato de que vários servidores hospedam o servidor de chat persistente e podem ser dimensionados de forma mais alta.</span><span class="sxs-lookup"><span data-stu-id="3f6ab-131">A multiple-server topology is the same as the single-server topology except that multiple servers host Persistent Chat Server, and can scale higher.</span></span> <span data-ttu-id="3f6ab-132">Vários computadores que executam o servidor de chat persistente devem residir no mesmo domínio de serviços de domínio do Active Directory do Lync Server e no serviço de conformidade.</span><span class="sxs-lookup"><span data-stu-id="3f6ab-132">Multiple computers running Persistent Chat Server should reside in the same Active Directory Domain Services domain as Lync Server and the Compliance service.</span></span>

<span data-ttu-id="3f6ab-133">A figura a seguir mostra todos os componentes de uma topologia de vários servidores com vários computadores que executam o servidor de chat persistente, o serviço de conformidade opcional e um banco de dados de conformidade separado.</span><span class="sxs-lookup"><span data-stu-id="3f6ab-133">The following figure shows all the components of a multiple-server topology with multiple computers running Persistent Chat Server, the optional Compliance service, and a separate compliance database.</span></span>

<span data-ttu-id="3f6ab-134">**Vários Servidores de Chat Persistente**</span><span class="sxs-lookup"><span data-stu-id="3f6ab-134">**Multiple Persistent Chat Servers**</span></span>

<span data-ttu-id="3f6ab-135">![Topologia de vários servidores](images/Gg398500.19aea898-28df-4d9b-903c-f72ef062d919(OCS.15).jpg "Topologia de vários servidores")</span><span class="sxs-lookup"><span data-stu-id="3f6ab-135">![Multiple server topology](images/Gg398500.19aea898-28df-4d9b-903c-f72ef062d919(OCS.15).jpg "Multiple server topology")</span></span>

<span data-ttu-id="3f6ab-136">Em uma implantação de servidor de chat persistente de quatro servidores, em que 80.000 os usuários podem estar conectados simultaneamente e usando o chat persistente, a carga é distribuída igualmente em 20.000 usuários por servidor.</span><span class="sxs-lookup"><span data-stu-id="3f6ab-136">In a four-server Persistent Chat Server deployment, where 80,000 users can be simultaneously signed in to and using Persistent Chat, the load is distributed evenly at 20,000 users per server.</span></span> <span data-ttu-id="3f6ab-137">Se um servidor ficar indisponível, os usuários que estiverem conectados a esse servidor perderão o acesso ao servidor de chat persistente.</span><span class="sxs-lookup"><span data-stu-id="3f6ab-137">If one server becomes unavailable, the users who are connected to that server will lose their access to Persistent Chat Server.</span></span> <span data-ttu-id="3f6ab-138">Os usuários desconectados serão automaticamente transferidos para os servidores restantes até que o servidor disponível seja restaurado.</span><span class="sxs-lookup"><span data-stu-id="3f6ab-138">The disconnected users will be automatically transferred to the remaining servers until the unavailable server is restored.</span></span> <span data-ttu-id="3f6ab-139">Dependendo da quantidade de tráfego de chat persistente na rede, essa transferência pode levar alguns minutos ou mais.</span><span class="sxs-lookup"><span data-stu-id="3f6ab-139">Depending on the amount of Persistent Chat traffic on the network, this transfer can take a few minutes or longer.</span></span> <span data-ttu-id="3f6ab-140">Como cada um dos servidores restantes pode hospedar até 30.000 usuários, recomendamos que você restaure o servidor indisponível o mais rápido possível para evitar problemas de desempenho.</span><span class="sxs-lookup"><span data-stu-id="3f6ab-140">Because each of the remaining servers might be hosting as many as 30,000 users, we recommend that you restore the unavailable server as quickly as possible to avoid performance issues.</span></span> <span data-ttu-id="3f6ab-141">Caso contrário, você pode tornar outro servidor de chat persistente disponível usando o construtor de topologias ou o cmdlet do Windows PowerShell, **set-CsPersistentChatActiveServer**.</span><span class="sxs-lookup"><span data-stu-id="3f6ab-141">Otherwise, you can make another Persistent Chat Server available by using the Topology Builder or the Windows PowerShell cmdlet, **set-CsPersistentChatActiveServer**.</span></span>

</div>

</div>

<div>

## <a name="persistent-chat-server-capacity-planning"></a><span data-ttu-id="3f6ab-142">Planejamento da capacidade do servidor de chat persistente</span><span class="sxs-lookup"><span data-stu-id="3f6ab-142">Persistent Chat Server Capacity Planning</span></span>

<span data-ttu-id="3f6ab-143">As tabelas a seguir podem ajudá-lo com o planejamento de capacidade para o servidor de chat persistente.</span><span class="sxs-lookup"><span data-stu-id="3f6ab-143">The following tables can help you with capacity planning for Persistent Chat Server.</span></span> <span data-ttu-id="3f6ab-144">Eles modelam como alterar várias configurações de servidor de chat persistente afetam os recursos de capacidade.</span><span class="sxs-lookup"><span data-stu-id="3f6ab-144">They model how changing various Persistent Chat Server settings affect capacity capabilities.</span></span>

<div>

## <a name="planning-your-maximum-capacity-for-persistent-chat-server"></a><span data-ttu-id="3f6ab-145">Planejar sua capacidade máxima para o servidor de chat persistente</span><span class="sxs-lookup"><span data-stu-id="3f6ab-145">Planning Your Maximum Capacity for Persistent Chat Server</span></span>

<span data-ttu-id="3f6ab-146">Use a seguinte tabela de exemplo para determinar o número de usuários que você será capaz de suportar.</span><span class="sxs-lookup"><span data-stu-id="3f6ab-146">Use the following sample table to determine the number of users you will be able to support.</span></span>

### <a name="persistent-chat-server-pool-maximum-capacity-sample"></a><span data-ttu-id="3f6ab-147">Exemplo de capacidade máxima do pool de servidores de chat persistente</span><span class="sxs-lookup"><span data-stu-id="3f6ab-147">Persistent Chat Server pool Maximum Capacity Sample</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="3f6ab-148">Instâncias ativas do serviço de chat persistente</span><span class="sxs-lookup"><span data-stu-id="3f6ab-148">Active Persistent Chat service instances</span></span></p></td>
<td><p><span data-ttu-id="3f6ab-149"><em>quatro</em></span><span class="sxs-lookup"><span data-stu-id="3f6ab-149"><em>4</em></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3f6ab-150">Instâncias do serviço de chat persistente</span><span class="sxs-lookup"><span data-stu-id="3f6ab-150">Persistent Chat service instances</span></span></p></td>
<td><p><span data-ttu-id="3f6ab-151"><em>8 (4 deve estar inativo; somente um máximo de 4 pode ser ativo)</em></span><span class="sxs-lookup"><span data-stu-id="3f6ab-151"><em>8 (4 must be inactive; only a maximum of 4 can be active)</em></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3f6ab-152">Usuários ativos conectados</span><span class="sxs-lookup"><span data-stu-id="3f6ab-152">Active users connected</span></span></p></td>
<td><p><span data-ttu-id="3f6ab-153"><em>80.000</em></span><span class="sxs-lookup"><span data-stu-id="3f6ab-153"><em>80,000</em></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3f6ab-154">Total de usuários provisionados</span><span class="sxs-lookup"><span data-stu-id="3f6ab-154">Total provisioned users</span></span></p></td>
<td><p><span data-ttu-id="3f6ab-155">150.000</span><span class="sxs-lookup"><span data-stu-id="3f6ab-155">150,000</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3f6ab-156">Número de pontos de extremidade</span><span class="sxs-lookup"><span data-stu-id="3f6ab-156">Number of endpoints</span></span></p></td>
<td><p><span data-ttu-id="3f6ab-157">120.000</span><span class="sxs-lookup"><span data-stu-id="3f6ab-157">120,000</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="3f6ab-158">No exemplo anterior, o plano é suportar o número máximo de usuários que o servidor de chat persistente permite: quatro servidores/instâncias do serviço de chat persistente (pode ter quatro mais servidores passivos executando o servidor de chat persistente para alta disponibilidade e recuperação de desastres) e 20.000 usuários por servidor, para um total de 80.000 usuários ativos.</span><span class="sxs-lookup"><span data-stu-id="3f6ab-158">In the preceding sample, the plan is to support the maximum number of users that Persistent Chat Server allows: four servers/instances of the Persistent Chat service (can have four more passive servers running Persistent Chat Server for high availability and disaster recovery) and 20,000 users per server, for a total of 80,000 active users.</span></span>

</div>

<div>

## <a name="capacity-planning-for-managing-persistent-chat-room-access"></a><span data-ttu-id="3f6ab-159">Planejamento de capacidade para gerenciar o acesso de salas de chat persistente</span><span class="sxs-lookup"><span data-stu-id="3f6ab-159">Capacity Planning for Managing Persistent Chat Room Access</span></span>

<span data-ttu-id="3f6ab-160">A tabela de exemplo a seguir pode ajudá-lo a planejar o gerenciamento do acesso à sala de chat persistente em um pool de servidor de chat persistente.</span><span class="sxs-lookup"><span data-stu-id="3f6ab-160">The following sample table can help you plan for managing Persistent Chat room access in a Persistent Chat Server pool.</span></span>

### <a name="managing-chat-room-access-sample"></a><span data-ttu-id="3f6ab-161">Gerenciando o exemplo de acesso da sala de chat</span><span class="sxs-lookup"><span data-stu-id="3f6ab-161">Managing Chat Room Access Sample</span></span>

<table>
<colgroup>
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
</colgroup>
<thead>
<tr class="header">
<th></th>
<th><span data-ttu-id="3f6ab-162">Salas de chat pequenas</span><span class="sxs-lookup"><span data-stu-id="3f6ab-162">Small Chat Rooms</span></span></th>
<th><span data-ttu-id="3f6ab-163">Salas de chat médias</span><span class="sxs-lookup"><span data-stu-id="3f6ab-163">Medium Chat Rooms</span></span></th>
<th><span data-ttu-id="3f6ab-164">Salas de chat grandes</span><span class="sxs-lookup"><span data-stu-id="3f6ab-164">Large Chat Rooms</span></span></th>
<th><span data-ttu-id="3f6ab-165">Total</span><span class="sxs-lookup"><span data-stu-id="3f6ab-165">Total</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="3f6ab-166">Tamanho de salas de chat (número de usuários conectados)</span><span class="sxs-lookup"><span data-stu-id="3f6ab-166">Size of chat rooms (number of users connected)</span></span></p></td>
<td><p><span data-ttu-id="3f6ab-167">30 por sala</span><span class="sxs-lookup"><span data-stu-id="3f6ab-167">30 per room</span></span></p></td>
<td><p><span data-ttu-id="3f6ab-168">150 por sala</span><span class="sxs-lookup"><span data-stu-id="3f6ab-168">150 per room</span></span></p></td>
<td><p><span data-ttu-id="3f6ab-169">16.000 por sala</span><span class="sxs-lookup"><span data-stu-id="3f6ab-169">16,000 per room</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3f6ab-170">Salas de chat</span><span class="sxs-lookup"><span data-stu-id="3f6ab-170">Chat rooms</span></span></p></td>
<td><p><span data-ttu-id="3f6ab-171">32.000</span><span class="sxs-lookup"><span data-stu-id="3f6ab-171">32,000</span></span></p></td>
<td><p><span data-ttu-id="3f6ab-172">1.067</span><span class="sxs-lookup"><span data-stu-id="3f6ab-172">1,067</span></span></p></td>
<td><p><span data-ttu-id="3f6ab-173">10 </span><span class="sxs-lookup"><span data-stu-id="3f6ab-173">10</span></span></p></td>
<td><p><span data-ttu-id="3f6ab-174">33.077</span><span class="sxs-lookup"><span data-stu-id="3f6ab-174">33,077</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3f6ab-175">% de salas que são auditório</span><span class="sxs-lookup"><span data-stu-id="3f6ab-175">% of rooms that are auditorium</span></span></p></td>
<td><p><span data-ttu-id="3f6ab-176">1</span><span class="sxs-lookup"><span data-stu-id="3f6ab-176">1%</span></span></p></td>
<td><p><span data-ttu-id="3f6ab-177">1</span><span class="sxs-lookup"><span data-stu-id="3f6ab-177">1%</span></span></p></td>
<td><p><span data-ttu-id="3f6ab-178">50%</span><span class="sxs-lookup"><span data-stu-id="3f6ab-178">50%</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3f6ab-179">% de salas abertas</span><span class="sxs-lookup"><span data-stu-id="3f6ab-179">% of rooms that are open</span></span></p></td>
<td><p><span data-ttu-id="3f6ab-180">3D</span><span class="sxs-lookup"><span data-stu-id="3f6ab-180">3%</span></span></p></td>
<td><p><span data-ttu-id="3f6ab-181">3D</span><span class="sxs-lookup"><span data-stu-id="3f6ab-181">3%</span></span></p></td>
<td><p><span data-ttu-id="3f6ab-182">50%</span><span class="sxs-lookup"><span data-stu-id="3f6ab-182">50%</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3f6ab-183">Salas abertas (sem Associação explícita)</span><span class="sxs-lookup"><span data-stu-id="3f6ab-183">Open rooms (no explicit membership)</span></span></p></td>
<td><p><span data-ttu-id="3f6ab-184">960</span><span class="sxs-lookup"><span data-stu-id="3f6ab-184">960</span></span></p></td>
<td><p><span data-ttu-id="3f6ab-185">32</span><span class="sxs-lookup"><span data-stu-id="3f6ab-185">32</span></span></p></td>
<td><p><span data-ttu-id="3f6ab-186">0,5</span><span class="sxs-lookup"><span data-stu-id="3f6ab-186">5</span></span></p></td>
<td><p><span data-ttu-id="3f6ab-187">997</span><span class="sxs-lookup"><span data-stu-id="3f6ab-187">997</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3f6ab-188">Salas não abertas (salas regulares com associação explícita)</span><span class="sxs-lookup"><span data-stu-id="3f6ab-188">Non-open rooms (regular rooms with explicit membership)</span></span></p></td>
<td><p><span data-ttu-id="3f6ab-189">31.040</span><span class="sxs-lookup"><span data-stu-id="3f6ab-189">31,040</span></span></p></td>
<td><p><span data-ttu-id="3f6ab-190">1, 35</span><span class="sxs-lookup"><span data-stu-id="3f6ab-190">1.035</span></span></p></td>
<td><p><span data-ttu-id="3f6ab-191">0,5</span><span class="sxs-lookup"><span data-stu-id="3f6ab-191">5</span></span></p></td>
<td><p><span data-ttu-id="3f6ab-192">32.080</span><span class="sxs-lookup"><span data-stu-id="3f6ab-192">32,080</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3f6ab-193">Salas do auditório (entrada de apresentadores adicionais)</span><span class="sxs-lookup"><span data-stu-id="3f6ab-193">Auditorium rooms (additional presenters entry)</span></span></p></td>
<td><p><span data-ttu-id="3f6ab-194">,0</span><span class="sxs-lookup"><span data-stu-id="3f6ab-194">0</span></span></p></td>
<td><p><span data-ttu-id="3f6ab-195">32</span><span class="sxs-lookup"><span data-stu-id="3f6ab-195">32</span></span></p></td>
<td><p><span data-ttu-id="3f6ab-196">0,5</span><span class="sxs-lookup"><span data-stu-id="3f6ab-196">5</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3f6ab-197">Salas gerenciadas por associação direta</span><span class="sxs-lookup"><span data-stu-id="3f6ab-197">Rooms managed by direct membership</span></span></p></td>
<td><p><span data-ttu-id="3f6ab-198">50%</span><span class="sxs-lookup"><span data-stu-id="3f6ab-198">50%</span></span></p></td>
<td><p><span data-ttu-id="3f6ab-199">254</span><span class="sxs-lookup"><span data-stu-id="3f6ab-199">10%</span></span></p></td>
<td><p><span data-ttu-id="3f6ab-200">0%</span><span class="sxs-lookup"><span data-stu-id="3f6ab-200">0%</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3f6ab-201">Salas gerenciados por grupos de usuários</span><span class="sxs-lookup"><span data-stu-id="3f6ab-201">Rooms managed by user groups</span></span></p></td>
<td><p><span data-ttu-id="3f6ab-202">50%</span><span class="sxs-lookup"><span data-stu-id="3f6ab-202">50%</span></span></p></td>
<td><p><span data-ttu-id="3f6ab-203">90%</span><span class="sxs-lookup"><span data-stu-id="3f6ab-203">90%</span></span></p></td>
<td><p><span data-ttu-id="3f6ab-204">100%</span><span class="sxs-lookup"><span data-stu-id="3f6ab-204">100%</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3f6ab-205">Grupos de usuários na lista de associação de cada sala de chat para salas abertas (não especificado explicitamente)</span><span class="sxs-lookup"><span data-stu-id="3f6ab-205">User groups in each chat room's membership list for open rooms (not specified explicitly)</span></span></p></td>
<td><p><span data-ttu-id="3f6ab-206">,0</span><span class="sxs-lookup"><span data-stu-id="3f6ab-206">0</span></span></p></td>
<td><p><span data-ttu-id="3f6ab-207">,0</span><span class="sxs-lookup"><span data-stu-id="3f6ab-207">0</span></span></p></td>
<td><p><span data-ttu-id="3f6ab-208">,0</span><span class="sxs-lookup"><span data-stu-id="3f6ab-208">0</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3f6ab-209">Usuários na lista de associação de cada sala de chat para salas não abertas</span><span class="sxs-lookup"><span data-stu-id="3f6ab-209">Users in each chat room's membership list for non-open rooms</span></span></p></td>
<td><p><span data-ttu-id="3f6ab-210">até</span><span class="sxs-lookup"><span data-stu-id="3f6ab-210">30</span></span></p></td>
<td><p><span data-ttu-id="3f6ab-211">150</span><span class="sxs-lookup"><span data-stu-id="3f6ab-211">150</span></span></p></td>
<td><p><span data-ttu-id="3f6ab-212">16.000</span><span class="sxs-lookup"><span data-stu-id="3f6ab-212">16,000</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3f6ab-213">Grupos de usuários na lista de associação de cada sala de chat para salas não abertas</span><span class="sxs-lookup"><span data-stu-id="3f6ab-213">User groups in each chat room's membership list for non-open rooms</span></span></p></td>
<td><p><span data-ttu-id="3f6ab-214">3D</span><span class="sxs-lookup"><span data-stu-id="3f6ab-214">3</span></span></p></td>
<td><p><span data-ttu-id="3f6ab-215">0,5</span><span class="sxs-lookup"><span data-stu-id="3f6ab-215">5</span></span></p></td>
<td><p><span data-ttu-id="3f6ab-216">10 </span><span class="sxs-lookup"><span data-stu-id="3f6ab-216">10</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3f6ab-217">Usuários e grupos de usuários na lista de gerentes de cada sala de chat (para salas abertas e não abertas)</span><span class="sxs-lookup"><span data-stu-id="3f6ab-217">Users and user groups in each chat room's manager list (for open and non-open rooms)</span></span></p></td>
<td><p><span data-ttu-id="3f6ab-218">6 </span><span class="sxs-lookup"><span data-stu-id="3f6ab-218">6</span></span></p></td>
<td><p><span data-ttu-id="3f6ab-219">6 </span><span class="sxs-lookup"><span data-stu-id="3f6ab-219">6</span></span></p></td>
<td><p><span data-ttu-id="3f6ab-220">6 </span><span class="sxs-lookup"><span data-stu-id="3f6ab-220">6</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3f6ab-221">Usuários e grupos de usuários em cada lista de apresentadores da sala de chat do auditório (para salas abertas e não abertas)</span><span class="sxs-lookup"><span data-stu-id="3f6ab-221">Users and user groups in each auditorium chat room's presenters list (for open and non-open rooms)</span></span></p></td>
<td><p><span data-ttu-id="3f6ab-222">6 </span><span class="sxs-lookup"><span data-stu-id="3f6ab-222">6</span></span></p></td>
<td><p><span data-ttu-id="3f6ab-223">6 </span><span class="sxs-lookup"><span data-stu-id="3f6ab-223">6</span></span></p></td>
<td><p><span data-ttu-id="3f6ab-224">6 </span><span class="sxs-lookup"><span data-stu-id="3f6ab-224">6</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3f6ab-225">Entidades de associação com base no usuário em todas as salas não abertas</span><span class="sxs-lookup"><span data-stu-id="3f6ab-225">User-based membership entities across all non-open rooms</span></span></p></td>
<td><p><span data-ttu-id="3f6ab-226">465.600</span><span class="sxs-lookup"><span data-stu-id="3f6ab-226">465,600</span></span></p></td>
<td><p><span data-ttu-id="3f6ab-227">15.520</span><span class="sxs-lookup"><span data-stu-id="3f6ab-227">15,520</span></span></p></td>
<td><p>-</p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3f6ab-228">Entidades de associação com base em grupo de usuário em todas as salas não abertas</span><span class="sxs-lookup"><span data-stu-id="3f6ab-228">User-group-based membership entities across all non-open rooms</span></span></p></td>
<td><p><span data-ttu-id="3f6ab-229">46.560</span><span class="sxs-lookup"><span data-stu-id="3f6ab-229">46,560</span></span></p></td>
<td><p><span data-ttu-id="3f6ab-230">4656</span><span class="sxs-lookup"><span data-stu-id="3f6ab-230">4656</span></span></p></td>
<td><p><span data-ttu-id="3f6ab-231">50</span><span class="sxs-lookup"><span data-stu-id="3f6ab-231">50</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3f6ab-232">Entidades de usuários e grupos de usuários em todas as salas de chat do auditório</span><span class="sxs-lookup"><span data-stu-id="3f6ab-232">Users and user groups based entities across all auditorium chat rooms</span></span></p></td>
<td><p><span data-ttu-id="3f6ab-233">,0</span><span class="sxs-lookup"><span data-stu-id="3f6ab-233">0</span></span></p></td>
<td><p><span data-ttu-id="3f6ab-234">192</span><span class="sxs-lookup"><span data-stu-id="3f6ab-234">192</span></span></p></td>
<td><p><span data-ttu-id="3f6ab-235">50</span><span class="sxs-lookup"><span data-stu-id="3f6ab-235">50</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3f6ab-236">Entidades de usuários e grupos de usuários com base em todas as listas de gerentes de salas de chat</span><span class="sxs-lookup"><span data-stu-id="3f6ab-236">Users and user groups based manager entities across all chat rooms manager lists</span></span></p></td>
<td><p><span data-ttu-id="3f6ab-237">192.000</span><span class="sxs-lookup"><span data-stu-id="3f6ab-237">192,000</span></span></p></td>
<td><p><span data-ttu-id="3f6ab-238">6.400</span><span class="sxs-lookup"><span data-stu-id="3f6ab-238">6,400</span></span></p></td>
<td><p><span data-ttu-id="3f6ab-239">60</span><span class="sxs-lookup"><span data-stu-id="3f6ab-239">60</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3f6ab-240">Usuários ativos por sala de chat</span><span class="sxs-lookup"><span data-stu-id="3f6ab-240">Active users per chat room</span></span></p></td>
<td><p><span data-ttu-id="3f6ab-241"><em>até</em></span><span class="sxs-lookup"><span data-stu-id="3f6ab-241"><em>30</em></span></span></p></td>
<td><p><span data-ttu-id="3f6ab-242"><em>150</em></span><span class="sxs-lookup"><span data-stu-id="3f6ab-242"><em>150</em></span></span></p></td>
<td><p><span data-ttu-id="3f6ab-243"><em>16.000</em></span><span class="sxs-lookup"><span data-stu-id="3f6ab-243"><em>16,000</em></span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3f6ab-244">Salas de chat por usuário</span><span class="sxs-lookup"><span data-stu-id="3f6ab-244">Chat rooms per user</span></span></p></td>
<td><p><span data-ttu-id="3f6ab-245"><em>3,6</em></span><span class="sxs-lookup"><span data-stu-id="3f6ab-245"><em>12</em></span></span></p></td>
<td><p><span data-ttu-id="3f6ab-246"><em>duas</em></span><span class="sxs-lookup"><span data-stu-id="3f6ab-246"><em>2</em></span></span></p></td>
<td><p><span data-ttu-id="3f6ab-247"><em>duas</em></span><span class="sxs-lookup"><span data-stu-id="3f6ab-247"><em>2</em></span></span></p></td>
<td><p><span data-ttu-id="3f6ab-248"><em>dezesseis</em></span><span class="sxs-lookup"><span data-stu-id="3f6ab-248"><em>16</em></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3f6ab-249">Grupos de usuário na lista de membros de cada sala de chat</span><span class="sxs-lookup"><span data-stu-id="3f6ab-249">User groups in each chat room’s membership list</span></span></p></td>
<td><p><span data-ttu-id="3f6ab-250"><em>254</em></span><span class="sxs-lookup"><span data-stu-id="3f6ab-250"><em>10</em></span></span></p></td>
<td><p><span data-ttu-id="3f6ab-251"><em>254</em></span><span class="sxs-lookup"><span data-stu-id="3f6ab-251"><em>10</em></span></span></p></td>
<td><p><span data-ttu-id="3f6ab-252"><em>15</em></span><span class="sxs-lookup"><span data-stu-id="3f6ab-252"><em>15</em></span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3f6ab-253">Salas gerenciados por grupos de usuários</span><span class="sxs-lookup"><span data-stu-id="3f6ab-253">Rooms managed by user groups</span></span></p></td>
<td><p><span data-ttu-id="3f6ab-254"><em>50%</em></span><span class="sxs-lookup"><span data-stu-id="3f6ab-254"><em>50%</em></span></span></p></td>
<td><p><span data-ttu-id="3f6ab-255"><em>50%</em></span><span class="sxs-lookup"><span data-stu-id="3f6ab-255"><em>50%</em></span></span></p></td>
<td><p><span data-ttu-id="3f6ab-256"><em>50%</em></span><span class="sxs-lookup"><span data-stu-id="3f6ab-256"><em>50%</em></span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3f6ab-257">Entidades de participação baseadas em grupos de usuário em todas as salas de chat</span><span class="sxs-lookup"><span data-stu-id="3f6ab-257">User-group-based membership entities across all chat rooms</span></span></p></td>
<td><p><span data-ttu-id="3f6ab-258">155.200</span><span class="sxs-lookup"><span data-stu-id="3f6ab-258">155,200</span></span></p></td>
<td><p><span data-ttu-id="3f6ab-259">5173</span><span class="sxs-lookup"><span data-stu-id="3f6ab-259">5173</span></span></p></td>
<td><p><span data-ttu-id="3f6ab-260">68</span><span class="sxs-lookup"><span data-stu-id="3f6ab-260">68</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3f6ab-261">Entidades de participação baseadas em usuários em todas as salas de chat</span><span class="sxs-lookup"><span data-stu-id="3f6ab-261">User-based membership entities across all chat rooms</span></span></p></td>
<td><p><span data-ttu-id="3f6ab-262">465.600</span><span class="sxs-lookup"><span data-stu-id="3f6ab-262">465,600</span></span></p></td>
<td><p><span data-ttu-id="3f6ab-263">77.600</span><span class="sxs-lookup"><span data-stu-id="3f6ab-263">77,600</span></span></p></td>
<td><p><span data-ttu-id="3f6ab-264">72.000</span><span class="sxs-lookup"><span data-stu-id="3f6ab-264">72,000</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3f6ab-265">Usuários e grupos de usuários no gerenciador de cada sala de chat, apresentador e listas de escopo</span><span class="sxs-lookup"><span data-stu-id="3f6ab-265">Users and user groups in each chat room's manager, presenter, and scope lists</span></span></p></td>
<td><p><span data-ttu-id="3f6ab-266">6 </span><span class="sxs-lookup"><span data-stu-id="3f6ab-266">6</span></span></p></td>
<td><p><span data-ttu-id="3f6ab-267">6 </span><span class="sxs-lookup"><span data-stu-id="3f6ab-267">6</span></span></p></td>
<td><p><span data-ttu-id="3f6ab-268">6 </span><span class="sxs-lookup"><span data-stu-id="3f6ab-268">6</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3f6ab-269">Usuários e grupos de usuários em todas as listas de escopos, apresentador e Gerenciador de salas de chat</span><span class="sxs-lookup"><span data-stu-id="3f6ab-269">Users and user groups across all chat rooms' manager, presenter, and scope lists</span></span></p></td>
<td><p><span data-ttu-id="3f6ab-270">192.000</span><span class="sxs-lookup"><span data-stu-id="3f6ab-270">192,000</span></span></p></td>
<td><p><span data-ttu-id="3f6ab-271">6400</span><span class="sxs-lookup"><span data-stu-id="3f6ab-271">6400</span></span></p></td>
<td><p><span data-ttu-id="3f6ab-272">60</span><span class="sxs-lookup"><span data-stu-id="3f6ab-272">60</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3f6ab-273">Entradas de controle de acesso</span><span class="sxs-lookup"><span data-stu-id="3f6ab-273">Access control entries</span></span></p></td>
<td><p><span data-ttu-id="3f6ab-274">704.160</span><span class="sxs-lookup"><span data-stu-id="3f6ab-274">704,160</span></span></p></td>
<td><p><span data-ttu-id="3f6ab-275">26.768</span><span class="sxs-lookup"><span data-stu-id="3f6ab-275">26,768</span></span></p></td>
<td><p><span data-ttu-id="3f6ab-276">160</span><span class="sxs-lookup"><span data-stu-id="3f6ab-276">160</span></span></p></td>
<td><p><span data-ttu-id="3f6ab-277">731.088</span><span class="sxs-lookup"><span data-stu-id="3f6ab-277">731,088</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3f6ab-278">Entradas de controle de máximo acesso</span><span class="sxs-lookup"><span data-stu-id="3f6ab-278">Maximum access control entries</span></span></p></td>
<td></td>
<td></td>
<td></td>
<td><p><span data-ttu-id="3f6ab-279">2 milhões</span><span class="sxs-lookup"><span data-stu-id="3f6ab-279">2,000,000</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="3f6ab-280">No exemplo anterior, quando você implanta os servidores de chat persistente de acordo com as diretrizes recomendadas, eles podem lidar com até 80.000 usuários ativos em um pool de quatro servidores com conformidade habilitada.</span><span class="sxs-lookup"><span data-stu-id="3f6ab-280">In the preceding sample, when you deploy the Persistent Chat Servers according to the recommended guidelines, they can handle up to 80,000 active users across a four-server pool with compliance enabled.</span></span>

<span data-ttu-id="3f6ab-281">Este exemplo mostra as salas de chat categorizadas como pequenas (30 usuários ativos a qualquer momento), média (150 usuários ativos) e grandes (16.000 usuários ativos).</span><span class="sxs-lookup"><span data-stu-id="3f6ab-281">This sample shows chat rooms categorized as small (30 active users at any given time), medium (150 active users), and large (16,000 active users).</span></span> <span data-ttu-id="3f6ab-282">O número de salas de chat de um determinado tamanho é calculado com base no número total de:</span><span class="sxs-lookup"><span data-stu-id="3f6ab-282">The number of chat rooms of a certain size is computed based on the total number of:</span></span>

  - <span data-ttu-id="3f6ab-283">Usuários ativos no sistema</span><span class="sxs-lookup"><span data-stu-id="3f6ab-283">Active users in the system</span></span>

  - <span data-ttu-id="3f6ab-284">Usuários ativos em salas de chat de determinado tamanho</span><span class="sxs-lookup"><span data-stu-id="3f6ab-284">Active users in chat rooms of the given size</span></span>

  - <span data-ttu-id="3f6ab-285">Salas de chat de um tamanho determinado onde ingressa um único usuário</span><span class="sxs-lookup"><span data-stu-id="3f6ab-285">Chat rooms of the given size that a single user joins</span></span>

<span data-ttu-id="3f6ab-286">Para cada sala de chat, a tabela de planejamento de capacidade anterior especifica o número de entradas de controle de acesso associadas à sala de chat, incluindo entradas atribuídas diretamente à sala de chat.</span><span class="sxs-lookup"><span data-stu-id="3f6ab-286">For each chat room, the preceding capacity planning table specifies the number of access control entries that are associated with the chat room, including entries that are assigned directly to the chat room.</span></span> <span data-ttu-id="3f6ab-287">Você pode controlar o acesso a salas de chat individuais usando listas de controle de acesso (ACLs).</span><span class="sxs-lookup"><span data-stu-id="3f6ab-287">You can control access to individual chat rooms by using access control lists (ACLs).</span></span> <span data-ttu-id="3f6ab-288">Você também pode controlar o acesso no nível de categoria.</span><span class="sxs-lookup"><span data-stu-id="3f6ab-288">You can also control access at the category level.</span></span> <span data-ttu-id="3f6ab-289">Em uma ACL, uma entrada de controle de acesso individual pode ser um grupo de usuários — por exemplo, um grupo de segurança, uma lista de distribuição ou um único usuário.</span><span class="sxs-lookup"><span data-stu-id="3f6ab-289">In an ACL, an individual access control entry can be either a user group—for example, a security group, a distribution list, or a single user.</span></span> <span data-ttu-id="3f6ab-290">Você pode definir as entradas de controle de acesso aos membros, aos apresentadores e aos gerentes de sala de chat.</span><span class="sxs-lookup"><span data-stu-id="3f6ab-290">You can define access control entries for chat room managers, presenters, and members.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="3f6ab-291">Ao planejar sua estratégia de gerenciamento de salas de chat, tenha em mente que o número total de entradas de controle de acesso permitido é 2 milhões.</span><span class="sxs-lookup"><span data-stu-id="3f6ab-291">In planning your strategy for managing chat rooms, keep in mind that the total number of allowed access control entries is 2 million.</span></span> <span data-ttu-id="3f6ab-292">Se as entradas de controle de acesso calculadas excederem 2 milhões, o desempenho do servidor pode degradar significativamente.</span><span class="sxs-lookup"><span data-stu-id="3f6ab-292">If the calculated access control entries exceed 2 million, server performance could degrade significantly.</span></span> <span data-ttu-id="3f6ab-293">Para evitar esse problema, sempre que possível, certifique-se de que suas entradas de controle de acesso sejam grupos de usuários, em vez de usuários individuais.</span><span class="sxs-lookup"><span data-stu-id="3f6ab-293">To avoid this issue, whenever possible, be sure that your access control entries are user groups instead of individual users.</span></span>



</div>

</div>

<div>

## <a name="capacity-planning-for-managing-chat-room-access-by-invitation"></a><span data-ttu-id="3f6ab-294">Planejamento de capacidade para gerenciar o acesso de sala de chat por convite</span><span class="sxs-lookup"><span data-stu-id="3f6ab-294">Capacity Planning for Managing Chat Room Access by Invitation</span></span>

<span data-ttu-id="3f6ab-295">Você pode usar a seguinte tabela de planejamento de capacidade para entender o número de convites que o servidor de chat persistente cria e armazena no banco de dados de chat persistente quando ele é configurado para enviar convites.</span><span class="sxs-lookup"><span data-stu-id="3f6ab-295">You can use the following capacity planning table to understand the number of invitations that Persistent Chat Server creates and stores in the Persistent Chat database when it is configured to send invitations.</span></span> <span data-ttu-id="3f6ab-296">Você gerencia convites na categoria usando a página **configurações de categoria de sala de chat** no painel de controle do Lync Server ou usando o cmdlet do Windows PowerShell, **set-csPersistentChatCategory**.</span><span class="sxs-lookup"><span data-stu-id="3f6ab-296">You manage invitations on the Category by using the **Chat Room Category settings** page in the Lync Server Control Panel, or by using the Windows PowerShell cmdlet, **set-csPersistentChatCategory**.</span></span> <span data-ttu-id="3f6ab-297">Você pode gerenciar convites em uma sala de chat (em linha com o que a categoria permite) usando a página de **Gerenciamento de sala** iniciada pelo cliente do Lync ou usando um cmdlet do Windows PowerShell, **set-csPersistentChatRoom**.</span><span class="sxs-lookup"><span data-stu-id="3f6ab-297">You can manage invitations on a chat room (in line with what the category allows) by using the **Room Management** page launched from the Lync client, or by using a Windows PowerShell cmdlet, **set-csPersistentChatRoom**.</span></span>

<span data-ttu-id="3f6ab-298">Os dados de exemplo na tabela a seguir pressupõem que, na página de **configurações de sala de chat** de 50% de todas as salas de chat, a opção de **convites** está definida como **Sim**.</span><span class="sxs-lookup"><span data-stu-id="3f6ab-298">The sample data in the following table assumes that, on the **Chat room settings** page for 50 percent of all chat rooms, the **Invitations** option is set to **Yes**.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="3f6ab-299">Se o valor calculado para o número de convites gerados pelo servidor exceder 1 milhão, o desempenho do servidor pode degradar significativamente.</span><span class="sxs-lookup"><span data-stu-id="3f6ab-299">If the calculated value for the number of invitations that is generated by the server exceeds 1 million, server performance could degrade significantly.</span></span> <span data-ttu-id="3f6ab-300">Para evitar esse problema, certifique-se de minimizar o número de salas de chat que estão configuradas para enviar convites ou restringir o número de usuários que podem participar de salas de chat que foram configuradas para enviar convites.</span><span class="sxs-lookup"><span data-stu-id="3f6ab-300">To avoid this issue, be sure that you minimize the number of chat rooms that are configured to send invitations or restrict the number of users who can join chat rooms that have been configured to send invitations.</span></span>



</div>

### <a name="chat-room-access-by-invitation-sample"></a><span data-ttu-id="3f6ab-301">Acesso à sala de chat por amostra de convite</span><span class="sxs-lookup"><span data-stu-id="3f6ab-301">Chat Room Access by Invitation Sample</span></span>

<table>
<colgroup>
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
</colgroup>
<thead>
<tr class="header">
<th></th>
<th><span data-ttu-id="3f6ab-302">Salas de chat pequenas</span><span class="sxs-lookup"><span data-stu-id="3f6ab-302">Small Chat Rooms</span></span></th>
<th><span data-ttu-id="3f6ab-303">Salas de chat médias</span><span class="sxs-lookup"><span data-stu-id="3f6ab-303">Medium Chat Rooms</span></span></th>
<th><span data-ttu-id="3f6ab-304">Salas de chat grandes</span><span class="sxs-lookup"><span data-stu-id="3f6ab-304">Large Chat Rooms</span></span></th>
<th><span data-ttu-id="3f6ab-305">Total</span><span class="sxs-lookup"><span data-stu-id="3f6ab-305">Total</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="3f6ab-306">Usuários que podem acessar a sala de chat</span><span class="sxs-lookup"><span data-stu-id="3f6ab-306">Users who can access chat room</span></span></p></td>
<td><p><span data-ttu-id="3f6ab-307">30 por sala</span><span class="sxs-lookup"><span data-stu-id="3f6ab-307">30 per room</span></span></p></td>
<td><p><span data-ttu-id="3f6ab-308">150 por sala</span><span class="sxs-lookup"><span data-stu-id="3f6ab-308">150 per room</span></span></p></td>
<td><p><span data-ttu-id="3f6ab-309">16.000 por sala</span><span class="sxs-lookup"><span data-stu-id="3f6ab-309">16,000 per room</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3f6ab-310">Porcentagem de salas que têm convites</span><span class="sxs-lookup"><span data-stu-id="3f6ab-310">Percentage of rooms that have invitations</span></span></p></td>
<td><p><span data-ttu-id="3f6ab-311">50%</span><span class="sxs-lookup"><span data-stu-id="3f6ab-311">50%</span></span></p></td>
<td><p><span data-ttu-id="3f6ab-312">50%</span><span class="sxs-lookup"><span data-stu-id="3f6ab-312">50%</span></span></p></td>
<td><p><span data-ttu-id="3f6ab-313">50%</span><span class="sxs-lookup"><span data-stu-id="3f6ab-313">50%</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3f6ab-314">Salas de chat configuradas para enviar convites</span><span class="sxs-lookup"><span data-stu-id="3f6ab-314">Chat rooms configured to send invitations</span></span></p></td>
<td><p><span data-ttu-id="3f6ab-315"><em>16.000</em></span><span class="sxs-lookup"><span data-stu-id="3f6ab-315"><em>16,000</em></span></span></p></td>
<td><p><span data-ttu-id="3f6ab-316"><em>533</em></span><span class="sxs-lookup"><span data-stu-id="3f6ab-316"><em>533</em></span></span></p></td>
<td><p><span data-ttu-id="3f6ab-317"><em>0,5</em></span><span class="sxs-lookup"><span data-stu-id="3f6ab-317"><em>5</em></span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3f6ab-318">Usuários que podem acessar a sala de chat</span><span class="sxs-lookup"><span data-stu-id="3f6ab-318">Users who can access the chat room</span></span></p></td>
<td><p><span data-ttu-id="3f6ab-319"><em>60</em></span><span class="sxs-lookup"><span data-stu-id="3f6ab-319"><em>60</em></span></span></p></td>
<td><p><span data-ttu-id="3f6ab-320"><em>225</em></span><span class="sxs-lookup"><span data-stu-id="3f6ab-320"><em>225</em></span></span></p></td>
<td><p><span data-ttu-id="3f6ab-321"><em>16.000</em></span><span class="sxs-lookup"><span data-stu-id="3f6ab-321"><em>16,000</em></span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3f6ab-322">Convites gerados pelo servidor de chat persistente</span><span class="sxs-lookup"><span data-stu-id="3f6ab-322">Invitations generated by Persistent Chat Server</span></span></p></td>
<td><p><span data-ttu-id="3f6ab-323">960.000</span><span class="sxs-lookup"><span data-stu-id="3f6ab-323">960,000</span></span></p></td>
<td><p><span data-ttu-id="3f6ab-324">120.000</span><span class="sxs-lookup"><span data-stu-id="3f6ab-324">120,000</span></span></p></td>
<td><p><span data-ttu-id="3f6ab-325">80.000</span><span class="sxs-lookup"><span data-stu-id="3f6ab-325">80,000</span></span></p></td>
<td><p><span data-ttu-id="3f6ab-326">1.160.000</span><span class="sxs-lookup"><span data-stu-id="3f6ab-326">1,160,000</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3f6ab-327">Número de convites máximo permitido</span><span class="sxs-lookup"><span data-stu-id="3f6ab-327">Maximum allowable number of invitations</span></span></p></td>
<td></td>
<td></td>
<td></td>
<td><p><span data-ttu-id="3f6ab-328">2 milhões</span><span class="sxs-lookup"><span data-stu-id="3f6ab-328">2,000,000</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3f6ab-329">Modelo 1-iniciar com o número esperado de mensagens por sala por dia</span><span class="sxs-lookup"><span data-stu-id="3f6ab-329">Model 1 - Start with expected number of messages per room per day</span></span></p></td>
<td></td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3f6ab-330">Taxa de chat por sala (por dia)</span><span class="sxs-lookup"><span data-stu-id="3f6ab-330">Chat Rate Per Room (per day)</span></span></p></td>
<td><p><span data-ttu-id="3f6ab-331">50</span><span class="sxs-lookup"><span data-stu-id="3f6ab-331">50</span></span></p></td>
<td><p><span data-ttu-id="3f6ab-332">500</span><span class="sxs-lookup"><span data-stu-id="3f6ab-332">500</span></span></p></td>
<td><p><span data-ttu-id="3f6ab-333">100</span><span class="sxs-lookup"><span data-stu-id="3f6ab-333">100</span></span></p></td>
<td><p><span data-ttu-id="3f6ab-334">650</span><span class="sxs-lookup"><span data-stu-id="3f6ab-334">650</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3f6ab-335">Taxa de chat (por segundo) em todas as salas</span><span class="sxs-lookup"><span data-stu-id="3f6ab-335">Chat rate (per second) across all rooms</span></span></p></td>
<td><p><span data-ttu-id="3f6ab-336">55,56</span><span class="sxs-lookup"><span data-stu-id="3f6ab-336">55.56</span></span></p></td>
<td><p><span data-ttu-id="3f6ab-337">18,52</span><span class="sxs-lookup"><span data-stu-id="3f6ab-337">18.52</span></span></p></td>
<td><p><span data-ttu-id="3f6ab-338">0, 3</span><span class="sxs-lookup"><span data-stu-id="3f6ab-338">0.03</span></span></p></td>
<td><p><span data-ttu-id="3f6ab-339">74</span><span class="sxs-lookup"><span data-stu-id="3f6ab-339">74</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3f6ab-340">Modelo 2-iniciar com o número de mensagens postadas por usuário por dia</span><span class="sxs-lookup"><span data-stu-id="3f6ab-340">Model 2 - Start with number of messages posted per user per day</span></span></p></td>
<td></td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3f6ab-341">Taxa de chat por usuário por dia</span><span class="sxs-lookup"><span data-stu-id="3f6ab-341">Chat rate per user per day</span></span></p></td>
<td><p><span data-ttu-id="3f6ab-342">15 </span><span class="sxs-lookup"><span data-stu-id="3f6ab-342">15</span></span></p></td>
<td><p><span data-ttu-id="3f6ab-343">0,5</span><span class="sxs-lookup"><span data-stu-id="3f6ab-343">5</span></span></p></td>
<td><p><span data-ttu-id="3f6ab-344">0,1</span><span class="sxs-lookup"><span data-stu-id="3f6ab-344">0.1</span></span></p></td>
<td><p><span data-ttu-id="3f6ab-345">508</span><span class="sxs-lookup"><span data-stu-id="3f6ab-345">20</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3f6ab-346">Taxa de chat por sala (por dia)</span><span class="sxs-lookup"><span data-stu-id="3f6ab-346">Chat rate per room (per day)</span></span></p></td>
<td><p><span data-ttu-id="3f6ab-347">38</span><span class="sxs-lookup"><span data-stu-id="3f6ab-347">38</span></span></p></td>
<td><p><span data-ttu-id="3f6ab-348">375</span><span class="sxs-lookup"><span data-stu-id="3f6ab-348">375</span></span></p></td>
<td><p><span data-ttu-id="3f6ab-349">800</span><span class="sxs-lookup"><span data-stu-id="3f6ab-349">800</span></span></p></td>
<td><p><span data-ttu-id="3f6ab-350">1.213</span><span class="sxs-lookup"><span data-stu-id="3f6ab-350">1,213</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3f6ab-351">Taxa de chat (por segundo) em todas as salas</span><span class="sxs-lookup"><span data-stu-id="3f6ab-351">Chat rate (per second) across all rooms</span></span></p></td>
<td><p><span data-ttu-id="3f6ab-352">41,67</span><span class="sxs-lookup"><span data-stu-id="3f6ab-352">41.67</span></span></p></td>
<td><p><span data-ttu-id="3f6ab-353">13,89</span><span class="sxs-lookup"><span data-stu-id="3f6ab-353">13.89</span></span></p></td>
<td><p><span data-ttu-id="3f6ab-354">0,28</span><span class="sxs-lookup"><span data-stu-id="3f6ab-354">0.28</span></span></p></td>
<td><p><span data-ttu-id="3f6ab-355">56</span><span class="sxs-lookup"><span data-stu-id="3f6ab-355">56</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="persistent-chat-server-performance-user-model"></a><span data-ttu-id="3f6ab-356">Modelo de usuário de desempenho do servidor de chat persistente</span><span class="sxs-lookup"><span data-stu-id="3f6ab-356">Persistent Chat Server Performance User Model</span></span>

<span data-ttu-id="3f6ab-357">A tabela a seguir descreve o modelo de usuário para o servidor de chat persistente.</span><span class="sxs-lookup"><span data-stu-id="3f6ab-357">The following table describes the user model for Persistent Chat Server.</span></span> <span data-ttu-id="3f6ab-358">Ele fornece a base para os requisitos de planejamento de capacidade e representa uma organização típica com 80.000 usuários simultâneos em quatro servidores.</span><span class="sxs-lookup"><span data-stu-id="3f6ab-358">It provides the basis for the capacity planning requirements and represents a typical organization with 80,000 concurrent users on four servers.</span></span>

### <a name="persistent-chat-server-performance-user-model"></a><span data-ttu-id="3f6ab-359">Modelo de usuário de desempenho do servidor de chat persistente</span><span class="sxs-lookup"><span data-stu-id="3f6ab-359">Persistent Chat Server Performance User Model</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="3f6ab-360">Número de usuários ativos conectados</span><span class="sxs-lookup"><span data-stu-id="3f6ab-360">Number of active users connected</span></span></p></td>
<td><p><span data-ttu-id="3f6ab-361">80.000</span><span class="sxs-lookup"><span data-stu-id="3f6ab-361">80,000</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3f6ab-362">Número de instâncias do serviço do servidor de chat persistente</span><span class="sxs-lookup"><span data-stu-id="3f6ab-362">Number of Persistent Chat Server service instances</span></span></p></td>
<td><p><span data-ttu-id="3f6ab-363">quatro</span><span class="sxs-lookup"><span data-stu-id="3f6ab-363">4</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3f6ab-364">Tamanho de salas de chat pequenas</span><span class="sxs-lookup"><span data-stu-id="3f6ab-364">Size of small chat rooms</span></span></p></td>
<td><p><span data-ttu-id="3f6ab-365">30 usuários</span><span class="sxs-lookup"><span data-stu-id="3f6ab-365">30 users</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3f6ab-366">Tamanho médio de salas de chat</span><span class="sxs-lookup"><span data-stu-id="3f6ab-366">Size of medium chat rooms</span></span></p></td>
<td><p><span data-ttu-id="3f6ab-367">150 usuários</span><span class="sxs-lookup"><span data-stu-id="3f6ab-367">150 users</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3f6ab-368">Tamanho grande de salas de chat</span><span class="sxs-lookup"><span data-stu-id="3f6ab-368">Size of large chat rooms</span></span></p></td>
<td><p><span data-ttu-id="3f6ab-369">16.000 usuários</span><span class="sxs-lookup"><span data-stu-id="3f6ab-369">16,000 users</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3f6ab-370">Número total de salas de chat</span><span class="sxs-lookup"><span data-stu-id="3f6ab-370">Total number of chat rooms</span></span></p></td>
<td><p><span data-ttu-id="3f6ab-371">33.077</span><span class="sxs-lookup"><span data-stu-id="3f6ab-371">33,077</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3f6ab-372">Número de salas de chat pequenas</span><span class="sxs-lookup"><span data-stu-id="3f6ab-372">Number of small chat rooms</span></span></p></td>
<td><p><span data-ttu-id="3f6ab-373">32.000</span><span class="sxs-lookup"><span data-stu-id="3f6ab-373">32,000</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3f6ab-374">Número de salas de chat médias</span><span class="sxs-lookup"><span data-stu-id="3f6ab-374">Number of medium chat rooms</span></span></p></td>
<td><p><span data-ttu-id="3f6ab-375">1.067</span><span class="sxs-lookup"><span data-stu-id="3f6ab-375">1,067</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3f6ab-376">Número de salas de chat grandes</span><span class="sxs-lookup"><span data-stu-id="3f6ab-376">Number of large chat rooms</span></span></p></td>
<td><p><span data-ttu-id="3f6ab-377">10 </span><span class="sxs-lookup"><span data-stu-id="3f6ab-377">10</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3f6ab-378">Número total de salas de chat por usuário</span><span class="sxs-lookup"><span data-stu-id="3f6ab-378">Total number of chat rooms per user</span></span></p></td>
<td><p><span data-ttu-id="3f6ab-379">16 </span><span class="sxs-lookup"><span data-stu-id="3f6ab-379">16</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3f6ab-380">Número de salas de chat pequenas por usuário</span><span class="sxs-lookup"><span data-stu-id="3f6ab-380">Number of small chat rooms per user</span></span></p></td>
<td><p><span data-ttu-id="3f6ab-381">12</span><span class="sxs-lookup"><span data-stu-id="3f6ab-381">12</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3f6ab-382">Número de salas de chat médias por usuário</span><span class="sxs-lookup"><span data-stu-id="3f6ab-382">Number of medium chat rooms per user</span></span></p></td>
<td><p><span data-ttu-id="3f6ab-383">duas</span><span class="sxs-lookup"><span data-stu-id="3f6ab-383">2</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3f6ab-384">Número de salas de chat grandes por usuário</span><span class="sxs-lookup"><span data-stu-id="3f6ab-384">Number of large chat rooms per user</span></span></p></td>
<td><p><span data-ttu-id="3f6ab-385">duas</span><span class="sxs-lookup"><span data-stu-id="3f6ab-385">2</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3f6ab-386">Número de salas Unidas por usuário</span><span class="sxs-lookup"><span data-stu-id="3f6ab-386">Number of rooms joined per user</span></span></p></td>
<td><p><span data-ttu-id="3f6ab-387">dia</span><span class="sxs-lookup"><span data-stu-id="3f6ab-387">24</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3f6ab-388">Taxa de pico de associação</span><span class="sxs-lookup"><span data-stu-id="3f6ab-388">Peak join rate</span></span></p></td>
<td><p><span data-ttu-id="3f6ab-389">10/segundo</span><span class="sxs-lookup"><span data-stu-id="3f6ab-389">10/second</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3f6ab-390">Taxa de chat total</span><span class="sxs-lookup"><span data-stu-id="3f6ab-390">Total chat rate</span></span></p></td>
<td><p><span data-ttu-id="3f6ab-391">24/segundo</span><span class="sxs-lookup"><span data-stu-id="3f6ab-391">24/second</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3f6ab-392">Taxa de chat para pequenas salas de chat</span><span class="sxs-lookup"><span data-stu-id="3f6ab-392">Chat rate for small chat rooms</span></span></p></td>
<td><p><span data-ttu-id="3f6ab-393">22.22/segundo</span><span class="sxs-lookup"><span data-stu-id="3f6ab-393">22.22/second</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3f6ab-394">Taxa de chat para salas de chat médias</span><span class="sxs-lookup"><span data-stu-id="3f6ab-394">Chat rate for medium chat rooms</span></span></p></td>
<td><p><span data-ttu-id="3f6ab-395">1.67/segundo</span><span class="sxs-lookup"><span data-stu-id="3f6ab-395">1.67/second</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3f6ab-396">Taxa de chat para salas de chat grandes</span><span class="sxs-lookup"><span data-stu-id="3f6ab-396">Chat rate for large chat rooms</span></span></p></td>
<td><p><span data-ttu-id="3f6ab-397">~ 0,15/segundo</span><span class="sxs-lookup"><span data-stu-id="3f6ab-397">~0.15/second</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3f6ab-398">Porcentagem de salas de chat configuradas para convites</span><span class="sxs-lookup"><span data-stu-id="3f6ab-398">Percentage of chat rooms configured for invitations</span></span></p></td>
<td><p><span data-ttu-id="3f6ab-399">50%</span><span class="sxs-lookup"><span data-stu-id="3f6ab-399">50%</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3f6ab-400">Porcentagem de participação direta em</span><span class="sxs-lookup"><span data-stu-id="3f6ab-400">Percentage of direct memberships</span></span></p></td>
<td><p><span data-ttu-id="3f6ab-401">50%</span><span class="sxs-lookup"><span data-stu-id="3f6ab-401">50%</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3f6ab-402">Porcentagem de membros em grupo</span><span class="sxs-lookup"><span data-stu-id="3f6ab-402">Percentage of group memberships</span></span></p></td>
<td><p><span data-ttu-id="3f6ab-403">50%</span><span class="sxs-lookup"><span data-stu-id="3f6ab-403">50%</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3f6ab-404">Número médio de afiliações ancestrais nos serviços de domínio do Active Directory</span><span class="sxs-lookup"><span data-stu-id="3f6ab-404">Average number of ancestor affiliations in Active Directory Domain Services</span></span></p></td>
<td><p><span data-ttu-id="3f6ab-405">100 - 200</span><span class="sxs-lookup"><span data-stu-id="3f6ab-405">100 - 200</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3f6ab-406">Número de contatos inscritos por usuário</span><span class="sxs-lookup"><span data-stu-id="3f6ab-406">Number of subscribed contacts per user</span></span></p></td>
<td><p><span data-ttu-id="3f6ab-407">80</span><span class="sxs-lookup"><span data-stu-id="3f6ab-407">80</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3f6ab-408">Número médio de pontos de extremidade por usuário</span><span class="sxs-lookup"><span data-stu-id="3f6ab-408">Average number of endpoints per user</span></span></p></td>
<td><p><span data-ttu-id="3f6ab-409">1,5</span><span class="sxs-lookup"><span data-stu-id="3f6ab-409">1.5</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3f6ab-410">Número médio de salas de chat visíveis por ponto de extremidade</span><span class="sxs-lookup"><span data-stu-id="3f6ab-410">Average number of visible chat rooms per endpoint</span></span></p></td>
<td><p><span data-ttu-id="3f6ab-411">1,5</span><span class="sxs-lookup"><span data-stu-id="3f6ab-411">1.5</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3f6ab-412">Número médio de salas de chat visíveis por usuário</span><span class="sxs-lookup"><span data-stu-id="3f6ab-412">Average number of visible chat rooms per user</span></span></p></td>
<td><p><span data-ttu-id="3f6ab-413">2,25 (50% por 1 sala e 50% para 2 salas); Até seis salas abertas, uma por monitor</span><span class="sxs-lookup"><span data-stu-id="3f6ab-413">2.25 (50% for 1 room and 50% for 2 rooms); Up to 6 rooms open, one per monitor</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3f6ab-414">Número de participantes sondados por intervalo</span><span class="sxs-lookup"><span data-stu-id="3f6ab-414">Number of participants polled per interval</span></span></p></td>
<td><p><span data-ttu-id="3f6ab-415">25 por sala de chat visível</span><span class="sxs-lookup"><span data-stu-id="3f6ab-415">25 per visible chat room</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3f6ab-416">Duração do intervalo de sondagem</span><span class="sxs-lookup"><span data-stu-id="3f6ab-416">Length of polling interval</span></span></p></td>
<td><p><span data-ttu-id="3f6ab-417">5 minutos</span><span class="sxs-lookup"><span data-stu-id="3f6ab-417">5 minutes</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3f6ab-418">Número de participantes sondados por segundo</span><span class="sxs-lookup"><span data-stu-id="3f6ab-418">Number of participants polled per second</span></span></p></td>
<td><p><span data-ttu-id="3f6ab-419">15.000</span><span class="sxs-lookup"><span data-stu-id="3f6ab-419">15,000</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3f6ab-420">Número de alterações de presença por hora por usuário</span><span class="sxs-lookup"><span data-stu-id="3f6ab-420">Number of presence changes per hour per user</span></span></p></td>
<td><p><span data-ttu-id="3f6ab-421">6 </span><span class="sxs-lookup"><span data-stu-id="3f6ab-421">6</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3f6ab-422">Número de alterações de presença por segundo</span><span class="sxs-lookup"><span data-stu-id="3f6ab-422">Number of presence changes per second</span></span></p></td>
<td><p><span data-ttu-id="3f6ab-423">133,33</span><span class="sxs-lookup"><span data-stu-id="3f6ab-423">133.33</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

