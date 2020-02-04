---
title: 'Lync Server 2013: componentes e topologias do servidor de chat persistente'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Components and topologies for Persistent Chat Server
ms:assetid: 6a0a14a0-baad-44e9-b26e-4d192c0a0e70
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398500(v=OCS.15)
ms:contentKeyID: 48184420
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 862635d091a216df61058c0f0ff00eaa9d32a0c2
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41742571"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="components-and-topologies-for-persistent-chat-server-in-lync-server-2013"></a><span data-ttu-id="f6cfc-102">Componentes e topologias do servidor de chat persistente no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f6cfc-102">Components and topologies for Persistent Chat Server in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f6cfc-103">_**Tópico da última modificação:** 2012-10-05_</span><span class="sxs-lookup"><span data-stu-id="f6cfc-103">_**Topic Last Modified:** 2012-10-05_</span></span>

<span data-ttu-id="f6cfc-104">O servidor de chat persistente tem suporte para configurações de servidor único e de vários servidores.</span><span class="sxs-lookup"><span data-stu-id="f6cfc-104">Persistent Chat Server supports both single-server configurations and multiple-server configurations.</span></span> <span data-ttu-id="f6cfc-105">O servidor de chat persistente também pode ser executado em um servidor do Lync Server 2013 Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="f6cfc-105">Persistent Chat Server can also run on a Lync Server 2013 Standard Edition server.</span></span> <span data-ttu-id="f6cfc-106">Essas configurações consistem nos seguintes componentes e topologias de servidor de chat persistente.</span><span class="sxs-lookup"><span data-stu-id="f6cfc-106">These configurations consist of the following Persistent Chat Server components and topologies.</span></span>

<div>

## <a name="persistent-chat-server-components"></a><span data-ttu-id="f6cfc-107">Componentes persistentes do servidor de chat</span><span class="sxs-lookup"><span data-stu-id="f6cfc-107">Persistent Chat Server Components</span></span>

<span data-ttu-id="f6cfc-108">A instalação da versão mais recente do servidor de chat persistente exige os seguintes componentes:</span><span class="sxs-lookup"><span data-stu-id="f6cfc-108">Installing the latest version of Persistent Chat Server requires the following components:</span></span>

  - <span data-ttu-id="f6cfc-109">Um ou mais computadores que executam o servidor de chat persistente e fornecimento dos seguintes serviços:</span><span class="sxs-lookup"><span data-stu-id="f6cfc-109">One or more computers running Persistent Chat Server and providing the following services:</span></span>
    
      - <span data-ttu-id="f6cfc-110">Serviço de chat persistente</span><span class="sxs-lookup"><span data-stu-id="f6cfc-110">Persistent Chat service</span></span>
    
      - <span data-ttu-id="f6cfc-111">Serviço de conformidade, que é ativado quando a conformidade é habilitada</span><span class="sxs-lookup"><span data-stu-id="f6cfc-111">Compliance service, which is turned on if compliance is enabled</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="f6cfc-112">No Lync Server 2013, os serviços Web de chat persistente para carregamento/download de arquivo agora são posicionados com o&nbsp;servidor front-end do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="f6cfc-112">In Lync Server 2013, the Persistent Chat Web Services for File Upload/Download is now collocated with Lync Server 2013&nbsp;Front End Server.</span></span><BR><span data-ttu-id="f6cfc-113">Os serviços Web de chat persistente para gerenciamento de sala de chat também são posicionados com&nbsp;o servidor front-end do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="f6cfc-113">The Persistent Chat Web Services for Chat Room Management is also collocated with Lync Server 2013&nbsp;Front End Server.</span></span>

    
    </div>

  - <span data-ttu-id="f6cfc-114">Servidor (es) (s) (mais de um servidor, se o espelhamento for usado) que hospedam o banco de dados back-end do SQL Server para hospedar o banco de dados de conteúdo de chat persistente no qual o conteúdo da sala de chat, salas e categorias são armazenados.</span><span class="sxs-lookup"><span data-stu-id="f6cfc-114">Server(s) (more than one server if mirroring is used) that host the SQL Server back-end database for hosting the Persistent Chat content database where chat room content, rooms, and categories are stored.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="f6cfc-115">O banco de dados back-end armazena dados do histórico do chat, incluindo informações sobre categorias e salas de chat persistentes que são criadas.</span><span class="sxs-lookup"><span data-stu-id="f6cfc-115">The back-end database stores chat history data, including information about categories and Persistent Chat rooms that are created.</span></span>

    
    </div>

  - <span data-ttu-id="f6cfc-116">Se a conformidade foi habilitada, um (s) servidor (es) (mais de um servidor se o espelhamento for usado) que hospeda o banco de dados back-end do SQL Server para hospedar o banco de dados de conformidade de chat persistente, em que os eventos de conformidade e o conteúdo de chat com a finalidade de conformidade são armazenados.</span><span class="sxs-lookup"><span data-stu-id="f6cfc-116">If compliance was enabled, a server(s) (more than one server if mirroring is used) that host the SQL Server back-end database for hosting the Persistent Chat Compliance database, where compliance events and chat content for the purpose of compliance are stored.</span></span>

<span data-ttu-id="f6cfc-117">Para administrar o servidor de chat persistente a partir de um computador separado (como um console administrativo), use o painel de controle do Lync Server no computador.</span><span class="sxs-lookup"><span data-stu-id="f6cfc-117">To administer Persistent Chat Server from a separate computer (such as an administrative console), use the Lync Server Control Panel on the computer.</span></span> <span data-ttu-id="f6cfc-118">Esse computador deve ser implantado em um domínio de serviços de domínio Active Directory, com pelo menos um servidor de catálogo global na raiz da floresta.</span><span class="sxs-lookup"><span data-stu-id="f6cfc-118">This computer must then be deployed in an Active Directory Domain Services domain, with at least one global catalog server in the forest root.</span></span>

<span data-ttu-id="f6cfc-119">Para obter detalhes sobre os requisitos de hardware e software para o servidor de chat persistente, consulte [requisitos técnicos para servidor de chat persistente no Lync server 2013](lync-server-2013-technical-requirements-for-persistent-chat-server.md), [hardware com suporte para o Lync Server 2013](lync-server-2013-supported-hardware.md)e [suporte a infraestrutura e software do servidor no Lync Server 2013](lync-server-2013-server-software-and-infrastructure-support.md) na documentação de suporte.</span><span class="sxs-lookup"><span data-stu-id="f6cfc-119">For details about hardware and software requirements for Persistent Chat Server, see [Technical requirements for Persistent Chat Server in Lync Server 2013](lync-server-2013-technical-requirements-for-persistent-chat-server.md), [Supported hardware for Lync Server 2013](lync-server-2013-supported-hardware.md), and [Server software and infrastructure support in Lync Server 2013](lync-server-2013-server-software-and-infrastructure-support.md) in the Supportability documentation.</span></span>

</div>

<div>

## <a name="supported-collocation"></a><span data-ttu-id="f6cfc-120">Colocação compatível</span><span class="sxs-lookup"><span data-stu-id="f6cfc-120">Supported Collocation</span></span>

<span data-ttu-id="f6cfc-121">O Lync Server 2013 oferece suporte a uma variedade de cenários de colocação, oferecendo a flexibilidade para economizar custos de hardware executando vários componentes em um servidor (se você tiver uma pequena organização) ou para executar componentes individuais em servidores diferentes (se você tiver uma organização maior que precisa de escalabilidade e desempenho).</span><span class="sxs-lookup"><span data-stu-id="f6cfc-121">Lync Server 2013 supports a variety of collocation scenarios, providing you the flexibility to save hardware costs by running multiple components on one server (if you have a small organization), or to run individual components on different servers (if you have a larger organization that needs scalability and performance).</span></span> <span data-ttu-id="f6cfc-122">Fatores de escalabilidade certamente devem ser considerados antes de você decidir se deseja posicionar componentes.</span><span class="sxs-lookup"><span data-stu-id="f6cfc-122">Scalability factors should certainly be considered before you decide whether to collocate components.</span></span>

<span data-ttu-id="f6cfc-123">Se a conformidade estiver habilitada, o serviço de conformidade de chat persistente será posicionado com o servidor front-end do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="f6cfc-123">The Persistent Chat Compliance service, if compliance is enabled, is collocated with the Lync Server 2013 Front End Server.</span></span>

<span data-ttu-id="f6cfc-124">O servidor de chat persistente pode ser implantado no servidor Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="f6cfc-124">Persistent Chat Server can be deployed on the Standard Edition server.</span></span> <span data-ttu-id="f6cfc-125">O servidor back-end persistente do servidor de chat e o banco de dados de conformidade de chat persistente podem ser posicionados no servidor Standard Edition no servidor back-end do SQL Server Express local.</span><span class="sxs-lookup"><span data-stu-id="f6cfc-125">The Persistent Chat Server Back End Server and the Persistent Chat Compliance database can be collocated on the Standard Edition server on the local SQL Server Express Back End Server.</span></span> <span data-ttu-id="f6cfc-126">Para obter detalhes sobre os componentes que podem ser posicionados, consulte [colocação do servidor com suporte no Lync server 2013](lync-server-2013-supported-server-collocation.md) na documentação de suporte.</span><span class="sxs-lookup"><span data-stu-id="f6cfc-126">For details about components that can be collocated there, see [Supported server collocation in Lync Server 2013](lync-server-2013-supported-server-collocation.md) in the Supportability documentation.</span></span>

<span data-ttu-id="f6cfc-127">Para o Lync Server 2013 Enterprise Edition, os servidores de chat persistentes não podem ser posicionados no servidor Enterprise Edition.</span><span class="sxs-lookup"><span data-stu-id="f6cfc-127">For Lync Server 2013 Enterprise Edition, Persistent Chat Servers cannot be collocated on the Enterprise Edition server.</span></span> <span data-ttu-id="f6cfc-128">O banco de dados do SQL Server para servidor de chat persistente pode ser posicionado com o banco de dados de servidor back-end de um pool de front-end Enterprise Edition.</span><span class="sxs-lookup"><span data-stu-id="f6cfc-128">The SQL Server database for Persistent Chat Server can be collocated with the Back End Server database of an Enterprise Edition Front End pool.</span></span> <span data-ttu-id="f6cfc-129">O banco de dados do SQL Server para conformidade de chat persistente também pode ser posicionado com o banco de dados de servidor back-end de um pool da edição Enterprise.</span><span class="sxs-lookup"><span data-stu-id="f6cfc-129">The SQL Server database for Persistent Chat compliance can also be collocated with the Back End Server database of an Enterprise Edition pool.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="f6cfc-130">O servidor que hospeda o banco de dados de chat persistente pode hospedar outros bancos de dados.</span><span class="sxs-lookup"><span data-stu-id="f6cfc-130">The server hosting the Persistent Chat database can host other databases.</span></span> <span data-ttu-id="f6cfc-131">No entanto, quando você considera posicionar o banco de dados de chat persistente com outros bancos de dados, lembre-se de que, se você estiver armazenando as mensagens de mais de alguns usuários, o espaço em disco necessário para o banco de dados de chat persistente pode crescer muito grande.</span><span class="sxs-lookup"><span data-stu-id="f6cfc-131">However, when you consider collocating the Persistent Chat database with other databases, be aware that if you are storing the messages of more than a few users, the disk space needed by the Persistent Chat database can grow very large.</span></span> <span data-ttu-id="f6cfc-132">Por esse motivo, não recomendamos posicionar o banco de dados de chat persistente com o banco de dados back-end.</span><span class="sxs-lookup"><span data-stu-id="f6cfc-132">For this reason, we do not recommend collocating the Persistent Chat database with the back-end database.</span></span>



</div>

<span data-ttu-id="f6cfc-133">Se você colocar o banco de dados de chat persistente com o banco de dados back-end, poderá usar uma única instância do SQL Server para qualquer um ou todos os bancos de dados ou poderá usar uma instância separada do SQL Server para cada banco de dados, com a seguinte limitação:</span><span class="sxs-lookup"><span data-stu-id="f6cfc-133">If you collocate the Persistent Chat database with the back-end database, you can either use a single instance of SQL Server for any or all of the databases, or you can use a separate instance of SQL Server for each database, with the following limitation:</span></span>

  - <span data-ttu-id="f6cfc-134">Cada instância do SQL Server pode conter apenas um único banco de dados back-end e um único banco de dados persistente de chat.</span><span class="sxs-lookup"><span data-stu-id="f6cfc-134">Each instance of SQL Server can contain only a single back-end database and a single Persistent Chat database.</span></span>

<span data-ttu-id="f6cfc-135">Para obter detalhes sobre a colocação de todas as funções de servidor e bancos de dados, consulte [colocação de servidor com suporte no Lync server 2013](lync-server-2013-supported-server-collocation.md) na documentação de suporte.</span><span class="sxs-lookup"><span data-stu-id="f6cfc-135">For details about collocation of all server roles and databases, see [Supported server collocation in Lync Server 2013](lync-server-2013-supported-server-collocation.md) in the Supportability documentation.</span></span>

</div>

<div>

## <a name="persistent-chat-server-topologies"></a><span data-ttu-id="f6cfc-136">Topologias persistentes do servidor de chat</span><span class="sxs-lookup"><span data-stu-id="f6cfc-136">Persistent Chat Server Topologies</span></span>

<span data-ttu-id="f6cfc-137">O servidor de chat persistente tem suporte para as seguintes topologias:</span><span class="sxs-lookup"><span data-stu-id="f6cfc-137">Persistent Chat Server supports the following topologies:</span></span>

  - <span data-ttu-id="f6cfc-138">Lync Server 2013 Enterprise Edition Single Server persistent chat servidor front end Server</span><span class="sxs-lookup"><span data-stu-id="f6cfc-138">Lync Server 2013 Enterprise Edition single server Persistent Chat Server Front End Server</span></span>

  - <span data-ttu-id="f6cfc-139">Lync Server 2013 Enterprise Edition vários servidores servidor de chat persistente servidor front-end</span><span class="sxs-lookup"><span data-stu-id="f6cfc-139">Lync Server 2013 Enterprise Edition multiple server Persistent Chat Server Front End Server</span></span>

  - <span data-ttu-id="f6cfc-140">Servidor do Lync Server 2013 Standard Edition usando SQL Server Express</span><span class="sxs-lookup"><span data-stu-id="f6cfc-140">Lync Server 2013 Standard Edition server using SQL Server Express</span></span>

  - <span data-ttu-id="f6cfc-141">Lync Server 2013 Standard Edition Server e servidor de chat persistente em um servidor separado usando o Standard Edition Server como o próximo servidor de salto.</span><span class="sxs-lookup"><span data-stu-id="f6cfc-141">Lync Server 2013 Standard Edition server and Persistent Chat Server on a separate server using Standard Edition server as the next hop server.</span></span>

<span data-ttu-id="f6cfc-142">Você pode adicionar um servidor de chat persistente à implantação do Lync Server 2013 usando o construtor de topologias.</span><span class="sxs-lookup"><span data-stu-id="f6cfc-142">You can add Persistent Chat Server to your Lync Server 2013 deployment by using Topology Builder.</span></span> <span data-ttu-id="f6cfc-143">Você pode adicionar um único servidor ou um pool de servidores de chat persistente do servidor múltiplo à sua topologia.</span><span class="sxs-lookup"><span data-stu-id="f6cfc-143">You can add a single server or a multiple server Persistent Chat Server pool to your topology.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="f6cfc-144">Depois de criar um pool de servidores de chat persistentes com um único servidor usando o construtor de topologias, não é possível adicionar mais servidores ao pool.</span><span class="sxs-lookup"><span data-stu-id="f6cfc-144">After you create a Persistent Chat Server pool with a single server by using Topology Builder, you cannot add additional servers to the pool.</span></span>



</div>

<div>

## <a name="single-server-topology"></a><span data-ttu-id="f6cfc-145">Topologia de servidor único</span><span class="sxs-lookup"><span data-stu-id="f6cfc-145">Single-Server Topology</span></span>

<span data-ttu-id="f6cfc-146">A configuração mínima e a implantação mais simples para o servidor de chat persistente é uma única topologia de servidor front-end persistente do servidor de chat.</span><span class="sxs-lookup"><span data-stu-id="f6cfc-146">The minimum configuration and simplest deployment for Persistent Chat Server is a single Persistent Chat Server Front End Server topology.</span></span> <span data-ttu-id="f6cfc-147">Esta implantação requer um único servidor que executa o servidor de chat persistente (que, opcionalmente, executa o serviço de conformidade, se a conformidade estiver habilitada), um servidor que hospede o banco de dados do SQL Server e se a conformidade for necessária, o banco de dados do SQL Server para armazenar o dados de conformidade.</span><span class="sxs-lookup"><span data-stu-id="f6cfc-147">This deployment requires a single server that runs Persistent Chat Server (which optionally runs the Compliance service, if compliance is enabled), a server that hosts both the SQL Server database, and if compliance is required, the SQL Server database to store the compliance data.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="f6cfc-148">Você não pode adicionar mais servidores a um pool de servidores de chat persistente iniciado como uma implantação de servidor único no construtor de topologias.</span><span class="sxs-lookup"><span data-stu-id="f6cfc-148">You cannot add additional servers to a Persistent Chat Server pool that is started as a single-server deployment in Topology Builder.</span></span> <span data-ttu-id="f6cfc-149">Recomendamos usar a topologia de pool de vários servidores, mesmo se você estiver usando um único servidor, para que você possa adicionar mais servidores mais tarde, se necessário...</span><span class="sxs-lookup"><span data-stu-id="f6cfc-149">We recommend using the multiple-server pool topology, even if you’re using a single server, so that you can add more servers later, if needed..</span></span>



</div>

<span data-ttu-id="f6cfc-150">A figura a seguir mostra todos os componentes obrigatórios e opcionais de uma topologia para um único servidor de front-end do servidor de chat persistente com conformidade.</span><span class="sxs-lookup"><span data-stu-id="f6cfc-150">The following figure shows all required and optional components of a topology for a single Persistent Chat Server Front End Server with compliance.</span></span>

<span data-ttu-id="f6cfc-151">**Único servidor de chat persistente**</span><span class="sxs-lookup"><span data-stu-id="f6cfc-151">**Single Persistent Chat Server**</span></span>

<span data-ttu-id="f6cfc-152">![Topologia de servidor único com serviço de conformidade](images/Gg398500.9168fa52-61e0-4d17-a14d-45fd32e81456(OCS.15).jpg "Topologia de servidor único com serviço de conformidade")</span><span class="sxs-lookup"><span data-stu-id="f6cfc-152">![Single server topology with Compliance service](images/Gg398500.9168fa52-61e0-4d17-a14d-45fd32e81456(OCS.15).jpg "Single server topology with Compliance service")</span></span>

</div>

<div>

## <a name="multiple-server-topology"></a><span data-ttu-id="f6cfc-153">Topologia de vários servidores</span><span class="sxs-lookup"><span data-stu-id="f6cfc-153">Multiple-Server Topology</span></span>

<span data-ttu-id="f6cfc-154">Para fornecer maior capacidade e confiabilidade, você pode implantar uma topologia de vários servidores, conforme descrito em [planejamento para servidor de chat persistente no Lync server 2013](lync-server-2013-planning-for-persistent-chat-server.md).</span><span class="sxs-lookup"><span data-stu-id="f6cfc-154">To provide greater capacity and reliability, you can deploy a multiple-server topology, as described in [Planning for Persistent Chat Server in Lync Server 2013](lync-server-2013-planning-for-persistent-chat-server.md).</span></span> <span data-ttu-id="f6cfc-155">A topologia de vários servidores pode incluir até quatro computadores ativos que executam o servidor de chat persistente (as configurações de alta disponibilidade e recuperação de desastres permitirão até oito, mas apenas quatro podem estar ativas e as quatro restantes em standby).</span><span class="sxs-lookup"><span data-stu-id="f6cfc-155">The multiple-server topology can include as many as four active computers running Persistent Chat Server (high availability and disaster recovery configurations will allow up to eight, but only four can be active and the remaining four on standby).</span></span> <span data-ttu-id="f6cfc-156">Cada servidor pode oferecer suporte a quantos usuários simultâneos do 20.000, para um total de 80.000 usuários simultâneos conectados a um pool de servidores de chat persistente com quatro servidores.</span><span class="sxs-lookup"><span data-stu-id="f6cfc-156">Each server can support as many as 20,000 concurrent users, for a total of 80,000 concurrent users connected to a Persistent Chat Server pool with 4 servers.</span></span> <span data-ttu-id="f6cfc-157">Uma topologia de vários servidores é a mesma que a topologia de servidor único, exceto que vários servidores hospedam o servidor de chat persistente e podem ser dimensionados para maior.</span><span class="sxs-lookup"><span data-stu-id="f6cfc-157">A multiple-server topology is the same as the single-server topology except that multiple servers host Persistent Chat Server, and can scale higher.</span></span> <span data-ttu-id="f6cfc-158">Vários computadores que executam o servidor de chat persistente devem residir no mesmo domínio dos serviços de domínio Active Directory do Lync Server e no serviço de conformidade.</span><span class="sxs-lookup"><span data-stu-id="f6cfc-158">Multiple computers running Persistent Chat Server should reside in the same Active Directory Domain Services domain as Lync Server and the Compliance service.</span></span>

<span data-ttu-id="f6cfc-159">A figura a seguir mostra todos os componentes de uma topologia de vários servidores com vários computadores que executam o servidor de chat persistente, o serviço de conformidade opcional e um banco de dados de conformidade separado.</span><span class="sxs-lookup"><span data-stu-id="f6cfc-159">The following figure shows all the components of a multiple-server topology with multiple computers running Persistent Chat Server, the optional Compliance service, and a separate compliance database.</span></span>

<span data-ttu-id="f6cfc-160">**Vários servidores de chat persistentes**</span><span class="sxs-lookup"><span data-stu-id="f6cfc-160">**Multiple Persistent Chat Servers**</span></span>

<span data-ttu-id="f6cfc-161">![Topologia de vários servidores](images/Gg398500.19aea898-28df-4d9b-903c-f72ef062d919(OCS.15).jpg "Topologia de vários servidores")</span><span class="sxs-lookup"><span data-stu-id="f6cfc-161">![Multiple server topology](images/Gg398500.19aea898-28df-4d9b-903c-f72ef062d919(OCS.15).jpg "Multiple server topology")</span></span>

<span data-ttu-id="f6cfc-162">As topologias de vários servidores fornecem a funcionalidade de pool de servidores.</span><span class="sxs-lookup"><span data-stu-id="f6cfc-162">Multiple-server topologies provide pooling of server functionality.</span></span> <span data-ttu-id="f6cfc-163">Em um pool de servidores, os serviços de chat persistente se comunicam e compartilham dados.</span><span class="sxs-lookup"><span data-stu-id="f6cfc-163">In a server pool, the Persistent Chat services communicate and share data.</span></span> <span data-ttu-id="f6cfc-164">Por exemplo, o histórico de chats originalmente lançado em um serviço de chat persistente está disponível em qualquer serviço de chat persistente do sistema.</span><span class="sxs-lookup"><span data-stu-id="f6cfc-164">For example, chat history that was originally posted to one Persistent Chat service is available from any Persistent Chat service in the system.</span></span> <span data-ttu-id="f6cfc-165">Um arquivo carregado por meio de um serviço de chat persistente pode ser acessado por qualquer serviço de chat persistente.</span><span class="sxs-lookup"><span data-stu-id="f6cfc-165">A file that is uploaded through one Persistent Chat service can be accessed by any Persistent Chat service.</span></span> <span data-ttu-id="f6cfc-166">Os usuários podem ser conectados a diferentes servidores de front-end do servidor de chat persistente e podem ser chats e se comunicar uns com os outros.</span><span class="sxs-lookup"><span data-stu-id="f6cfc-166">Users can be connected to different Persistent Chat Server Front End Servers and can be chatting and communicating with each other.</span></span>

<span data-ttu-id="f6cfc-167">A porta padrão do TCP 8011 conecta um servidor a um pool de servidores e é usada pelo serviço de chat persistente para se comunicar entre si ou para fins administrativos.</span><span class="sxs-lookup"><span data-stu-id="f6cfc-167">The default port of TCP 8011 connects a server to a server pool, and is used by the Persistent Chat service to communicate between themselves, or for administrative purposes.</span></span>

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

