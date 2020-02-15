---
title: 'Lync Server 2013: componentes e topologias para servidor de chat persistente'
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
ms.openlocfilehash: 320605ab363ff4879811873cc9ce957520b91b29
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42048225"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="components-and-topologies-for-persistent-chat-server-in-lync-server-2013"></a><span data-ttu-id="43bfd-102">Componentes e topologias para servidor de chat persistente no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="43bfd-102">Components and topologies for Persistent Chat Server in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="43bfd-103">_**Última modificação do tópico:** 2012-10-05_</span><span class="sxs-lookup"><span data-stu-id="43bfd-103">_**Topic Last Modified:** 2012-10-05_</span></span>

<span data-ttu-id="43bfd-104">O servidor de chat persistente oferece suporte a configurações de servidor único e de vários servidores.</span><span class="sxs-lookup"><span data-stu-id="43bfd-104">Persistent Chat Server supports both single-server configurations and multiple-server configurations.</span></span> <span data-ttu-id="43bfd-105">O servidor de chat persistente também pode ser executado em um servidor do Lync Server 2013 Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="43bfd-105">Persistent Chat Server can also run on a Lync Server 2013 Standard Edition server.</span></span> <span data-ttu-id="43bfd-106">Essas configurações consistem nos seguintes componentes e topologias do servidor de chat persistente.</span><span class="sxs-lookup"><span data-stu-id="43bfd-106">These configurations consist of the following Persistent Chat Server components and topologies.</span></span>

<div>

## <a name="persistent-chat-server-components"></a><span data-ttu-id="43bfd-107">Componentes do servidor de chat persistente</span><span class="sxs-lookup"><span data-stu-id="43bfd-107">Persistent Chat Server Components</span></span>

<span data-ttu-id="43bfd-108">A instalação da versão mais recente do servidor de chat persistente requer os seguintes componentes:</span><span class="sxs-lookup"><span data-stu-id="43bfd-108">Installing the latest version of Persistent Chat Server requires the following components:</span></span>

  - <span data-ttu-id="43bfd-109">Um ou mais computadores que executam o servidor de chat persistente e fornecem os seguintes serviços:</span><span class="sxs-lookup"><span data-stu-id="43bfd-109">One or more computers running Persistent Chat Server and providing the following services:</span></span>
    
      - <span data-ttu-id="43bfd-110">Serviço de chat persistente</span><span class="sxs-lookup"><span data-stu-id="43bfd-110">Persistent Chat service</span></span>
    
      - <span data-ttu-id="43bfd-111">Serviço de conformidade, que é ativado quando a conformidade é habilitada</span><span class="sxs-lookup"><span data-stu-id="43bfd-111">Compliance service, which is turned on if compliance is enabled</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="43bfd-112">No Lync Server 2013, os serviços Web de chat persistente para upload/download de arquivo agora estão posicionados com o&nbsp;servidor front-end do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="43bfd-112">In Lync Server 2013, the Persistent Chat Web Services for File Upload/Download is now collocated with Lync Server 2013&nbsp;Front End Server.</span></span><BR><span data-ttu-id="43bfd-113">Os serviços Web de chat persistente para gerenciamento de salas de chat também são colocados com o&nbsp;servidor front-end do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="43bfd-113">The Persistent Chat Web Services for Chat Room Management is also collocated with Lync Server 2013&nbsp;Front End Server.</span></span>

    
    </div>

  - <span data-ttu-id="43bfd-114">Servidor (es) (mais de um servidor se o espelhamento for usado) que hospeda o banco de dados de back-end do SQL Server para hospedar o banco de dados de conteúdo de chat persistente onde o conteúdo da sala de chat, salas e categorias são armazenados.</span><span class="sxs-lookup"><span data-stu-id="43bfd-114">Server(s) (more than one server if mirroring is used) that host the SQL Server back-end database for hosting the Persistent Chat content database where chat room content, rooms, and categories are stored.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="43bfd-115">O banco de dados de back-end armazena dados de histórico de chat, incluindo informações sobre categorias e salas de chat persistente criadas.</span><span class="sxs-lookup"><span data-stu-id="43bfd-115">The back-end database stores chat history data, including information about categories and Persistent Chat rooms that are created.</span></span>

    
    </div>

  - <span data-ttu-id="43bfd-116">Se a conformidade foi habilitada, um (s) servidor (es) (mais de um servidor se o espelhamento for usado) que hospeda o banco de dados de back-end do SQL Server para hospedar o banco de dados de conformidade de chat persistente, em que os eventos de conformidade e o conteúdo de chat com o objetivo de conformidade são armazenados.</span><span class="sxs-lookup"><span data-stu-id="43bfd-116">If compliance was enabled, a server(s) (more than one server if mirroring is used) that host the SQL Server back-end database for hosting the Persistent Chat Compliance database, where compliance events and chat content for the purpose of compliance are stored.</span></span>

<span data-ttu-id="43bfd-117">Para administrar o servidor de chat persistente de um computador separado (como um console administrativo), use o painel de controle do Lync Server no computador.</span><span class="sxs-lookup"><span data-stu-id="43bfd-117">To administer Persistent Chat Server from a separate computer (such as an administrative console), use the Lync Server Control Panel on the computer.</span></span> <span data-ttu-id="43bfd-118">Esse computador deve ser implantado em um domínio de serviços de domínio do Active Directory, com pelo menos um servidor de catálogo global na raiz da floresta.</span><span class="sxs-lookup"><span data-stu-id="43bfd-118">This computer must then be deployed in an Active Directory Domain Services domain, with at least one global catalog server in the forest root.</span></span>

<span data-ttu-id="43bfd-119">Para obter detalhes sobre os requisitos de hardware e software do servidor de chat persistente, consulte [Technical Requirements for persistent chat Server in Lync server 2013](lync-server-2013-technical-requirements-for-persistent-chat-server.md), [hardware suportado para o Lync Server 2013](lync-server-2013-supported-hardware.md)e [suporte a infraestrutura e software de servidor no Lync Server 2013](lync-server-2013-server-software-and-infrastructure-support.md) na documentação de suporte.</span><span class="sxs-lookup"><span data-stu-id="43bfd-119">For details about hardware and software requirements for Persistent Chat Server, see [Technical requirements for Persistent Chat Server in Lync Server 2013](lync-server-2013-technical-requirements-for-persistent-chat-server.md), [Supported hardware for Lync Server 2013](lync-server-2013-supported-hardware.md), and [Server software and infrastructure support in Lync Server 2013](lync-server-2013-server-software-and-infrastructure-support.md) in the Supportability documentation.</span></span>

</div>

<div>

## <a name="supported-collocation"></a><span data-ttu-id="43bfd-120">Colocação suportada</span><span class="sxs-lookup"><span data-stu-id="43bfd-120">Supported Collocation</span></span>

<span data-ttu-id="43bfd-121">O Lync Server 2013 oferece suporte a uma variedade de cenários de colocação, fornecendo a flexibilidade para salvar os custos de hardware executando vários componentes em um servidor (se você tiver uma organização pequena) ou para executar componentes individuais em servidores diferentes (se você tiver um organização maior que precisa de escalabilidade e desempenho).</span><span class="sxs-lookup"><span data-stu-id="43bfd-121">Lync Server 2013 supports a variety of collocation scenarios, providing you the flexibility to save hardware costs by running multiple components on one server (if you have a small organization), or to run individual components on different servers (if you have a larger organization that needs scalability and performance).</span></span> <span data-ttu-id="43bfd-122">Os fatores de escalabilidade certamente devem ser considerados antes de você decidir se quer colocar componentes.</span><span class="sxs-lookup"><span data-stu-id="43bfd-122">Scalability factors should certainly be considered before you decide whether to collocate components.</span></span>

<span data-ttu-id="43bfd-123">O serviço de conformidade do chat persistente, se a conformidade estiver habilitada, será colocado com o servidor front-end do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="43bfd-123">The Persistent Chat Compliance service, if compliance is enabled, is collocated with the Lync Server 2013 Front End Server.</span></span>

<span data-ttu-id="43bfd-124">O servidor de chat persistente pode ser implantado no servidor Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="43bfd-124">Persistent Chat Server can be deployed on the Standard Edition server.</span></span> <span data-ttu-id="43bfd-125">O servidor back-end do servidor de chat persistente e o banco de dados de conformidade de chat persistente podem ser colocados no servidor Standard Edition no servidor back-end do SQL Server Express local.</span><span class="sxs-lookup"><span data-stu-id="43bfd-125">The Persistent Chat Server Back End Server and the Persistent Chat Compliance database can be collocated on the Standard Edition server on the local SQL Server Express Back End Server.</span></span> <span data-ttu-id="43bfd-126">Para obter detalhes sobre os componentes que podem ser colocados no local, consulte [suporte à colocação de servidor no Lync server 2013](lync-server-2013-supported-server-collocation.md) na documentação de suporte.</span><span class="sxs-lookup"><span data-stu-id="43bfd-126">For details about components that can be collocated there, see [Supported server collocation in Lync Server 2013](lync-server-2013-supported-server-collocation.md) in the Supportability documentation.</span></span>

<span data-ttu-id="43bfd-127">Para o Lync Server 2013 Enterprise Edition, os servidores de chat persistente não podem ser colocados no servidor Enterprise Edition.</span><span class="sxs-lookup"><span data-stu-id="43bfd-127">For Lync Server 2013 Enterprise Edition, Persistent Chat Servers cannot be collocated on the Enterprise Edition server.</span></span> <span data-ttu-id="43bfd-128">O banco de dados do SQL Server para servidor de chat persistente pode ser colocado com o banco de dados de servidor back-end de um pool de front-ends Enterprise Edition.</span><span class="sxs-lookup"><span data-stu-id="43bfd-128">The SQL Server database for Persistent Chat Server can be collocated with the Back End Server database of an Enterprise Edition Front End pool.</span></span> <span data-ttu-id="43bfd-129">O banco de dados do SQL Server para conformidade de chat persistente também pode ser colocado com o banco de dados de servidor back-end de um pool Enterprise Edition.</span><span class="sxs-lookup"><span data-stu-id="43bfd-129">The SQL Server database for Persistent Chat compliance can also be collocated with the Back End Server database of an Enterprise Edition pool.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="43bfd-130">O servidor que hospeda o banco de dados de chat persistente pode hospedar outros bancos de dados.</span><span class="sxs-lookup"><span data-stu-id="43bfd-130">The server hosting the Persistent Chat database can host other databases.</span></span> <span data-ttu-id="43bfd-131">No entanto, quando você considerar o posicionamento do banco de dados de chat persistente com outros bancos de dados, lembre-se de que se você estiver armazenando as mensagens de mais de alguns usuários, o espaço em disco necessário para o banco de dados de chat persistente poderá crescer muito grande.</span><span class="sxs-lookup"><span data-stu-id="43bfd-131">However, when you consider collocating the Persistent Chat database with other databases, be aware that if you are storing the messages of more than a few users, the disk space needed by the Persistent Chat database can grow very large.</span></span> <span data-ttu-id="43bfd-132">Por esse motivo, não recomendamos colocar o banco de dados de chat persistente com o banco de dados back-end.</span><span class="sxs-lookup"><span data-stu-id="43bfd-132">For this reason, we do not recommend collocating the Persistent Chat database with the back-end database.</span></span>



</div>

<span data-ttu-id="43bfd-133">Se você colocar o banco de dados de chat persistente com o banco de dados back-end, poderá usar uma única instância do SQL Server para qualquer um ou todos os bancos de dados ou poderá usar uma instância separada do SQL Server para cada banco de dados, com a seguinte limitação:</span><span class="sxs-lookup"><span data-stu-id="43bfd-133">If you collocate the Persistent Chat database with the back-end database, you can either use a single instance of SQL Server for any or all of the databases, or you can use a separate instance of SQL Server for each database, with the following limitation:</span></span>

  - <span data-ttu-id="43bfd-134">Cada instância do SQL Server pode conter apenas um único banco de dados de back-end e um único banco de dados de chat persistente.</span><span class="sxs-lookup"><span data-stu-id="43bfd-134">Each instance of SQL Server can contain only a single back-end database and a single Persistent Chat database.</span></span>

<span data-ttu-id="43bfd-135">Para obter detalhes sobre a colocação de todas as funções de servidor e bancos de dados, consulte [supported Server Coexistence no Lync server 2013](lync-server-2013-supported-server-collocation.md) na documentação de suporte.</span><span class="sxs-lookup"><span data-stu-id="43bfd-135">For details about collocation of all server roles and databases, see [Supported server collocation in Lync Server 2013](lync-server-2013-supported-server-collocation.md) in the Supportability documentation.</span></span>

</div>

<div>

## <a name="persistent-chat-server-topologies"></a><span data-ttu-id="43bfd-136">Topologias do servidor de chat persistente</span><span class="sxs-lookup"><span data-stu-id="43bfd-136">Persistent Chat Server Topologies</span></span>

<span data-ttu-id="43bfd-137">O servidor de chat persistente suporta as seguintes topologias:</span><span class="sxs-lookup"><span data-stu-id="43bfd-137">Persistent Chat Server supports the following topologies:</span></span>

  - <span data-ttu-id="43bfd-138">Servidor front-end do servidor de chat persistente do Lync Server 2013 Enterprise Edition Single Server</span><span class="sxs-lookup"><span data-stu-id="43bfd-138">Lync Server 2013 Enterprise Edition single server Persistent Chat Server Front End Server</span></span>

  - <span data-ttu-id="43bfd-139">Lync Server 2013 Enterprise Edition servidor de front end do servidor de chat persistente de vários servidores</span><span class="sxs-lookup"><span data-stu-id="43bfd-139">Lync Server 2013 Enterprise Edition multiple server Persistent Chat Server Front End Server</span></span>

  - <span data-ttu-id="43bfd-140">Servidor do Lync Server 2013 Standard Edition usando o SQL Server Express</span><span class="sxs-lookup"><span data-stu-id="43bfd-140">Lync Server 2013 Standard Edition server using SQL Server Express</span></span>

  - <span data-ttu-id="43bfd-141">Lync Server 2013 Standard Edition Server e servidor de chat persistente em um servidor separado usando o Standard Edition Server como servidor de próximo salto.</span><span class="sxs-lookup"><span data-stu-id="43bfd-141">Lync Server 2013 Standard Edition server and Persistent Chat Server on a separate server using Standard Edition server as the next hop server.</span></span>

<span data-ttu-id="43bfd-142">Você pode adicionar o servidor de chat persistente à sua implantação do Lync Server 2013 usando o construtor de topologias.</span><span class="sxs-lookup"><span data-stu-id="43bfd-142">You can add Persistent Chat Server to your Lync Server 2013 deployment by using Topology Builder.</span></span> <span data-ttu-id="43bfd-143">Você pode adicionar um único servidor ou um pool de servidor de chat persistente de vários servidores à sua topologia.</span><span class="sxs-lookup"><span data-stu-id="43bfd-143">You can add a single server or a multiple server Persistent Chat Server pool to your topology.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="43bfd-144">Depois de criar um pool de servidor de chat persistente com um único servidor usando o construtor de topologias, não é possível adicionar mais servidores ao pool.</span><span class="sxs-lookup"><span data-stu-id="43bfd-144">After you create a Persistent Chat Server pool with a single server by using Topology Builder, you cannot add additional servers to the pool.</span></span>



</div>

<div>

## <a name="single-server-topology"></a><span data-ttu-id="43bfd-145">Topologia de servidor único</span><span class="sxs-lookup"><span data-stu-id="43bfd-145">Single-Server Topology</span></span>

<span data-ttu-id="43bfd-146">A configuração mínima e a implantação mais simples para o servidor de chat persistente é uma topologia de servidor front-end de servidor de chat persistente única.</span><span class="sxs-lookup"><span data-stu-id="43bfd-146">The minimum configuration and simplest deployment for Persistent Chat Server is a single Persistent Chat Server Front End Server topology.</span></span> <span data-ttu-id="43bfd-147">Esta implantação requer um único servidor que executa o servidor de chat persistente (que, opcionalmente, executa o serviço de conformidade, se a conformidade estiver habilitada), um servidor que hospeda o banco de dados do SQL Server e, se a conformidade for necessária, o banco de dados do SQL Server para armazenar o dados de conformidade.</span><span class="sxs-lookup"><span data-stu-id="43bfd-147">This deployment requires a single server that runs Persistent Chat Server (which optionally runs the Compliance service, if compliance is enabled), a server that hosts both the SQL Server database, and if compliance is required, the SQL Server database to store the compliance data.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="43bfd-148">Não é possível adicionar mais servidores a um pool de servidores de chat persistente iniciado como uma implantação de servidor único no construtor de topologias.</span><span class="sxs-lookup"><span data-stu-id="43bfd-148">You cannot add additional servers to a Persistent Chat Server pool that is started as a single-server deployment in Topology Builder.</span></span> <span data-ttu-id="43bfd-149">Recomendamos usar a topologia de pool de vários servidores, mesmo se você for usar um único servidor, para que possa adicionar mais servidores no futuro se for necessário.</span><span class="sxs-lookup"><span data-stu-id="43bfd-149">We recommend using the multiple-server pool topology, even if you’re using a single server, so that you can add more servers later, if needed..</span></span>



</div>

<span data-ttu-id="43bfd-150">A figura a seguir mostra todos os componentes obrigatórios e opcionais de uma topologia para um único servidor de front-end do servidor de chat persistente com conformidade.</span><span class="sxs-lookup"><span data-stu-id="43bfd-150">The following figure shows all required and optional components of a topology for a single Persistent Chat Server Front End Server with compliance.</span></span>

<span data-ttu-id="43bfd-151">**Servidor de Chat Persistente único**</span><span class="sxs-lookup"><span data-stu-id="43bfd-151">**Single Persistent Chat Server**</span></span>

<span data-ttu-id="43bfd-152">![Topologia de servidor único com serviço de conformidade](images/Gg398500.9168fa52-61e0-4d17-a14d-45fd32e81456(OCS.15).jpg "Topologia de servidor único com serviço de conformidade")</span><span class="sxs-lookup"><span data-stu-id="43bfd-152">![Single server topology with Compliance service](images/Gg398500.9168fa52-61e0-4d17-a14d-45fd32e81456(OCS.15).jpg "Single server topology with Compliance service")</span></span>

</div>

<div>

## <a name="multiple-server-topology"></a><span data-ttu-id="43bfd-153">Topologia de vários servidores</span><span class="sxs-lookup"><span data-stu-id="43bfd-153">Multiple-Server Topology</span></span>

<span data-ttu-id="43bfd-154">Para fornecer maior capacidade e confiabilidade, você pode implantar uma topologia de vários servidores, conforme descrito em [Planning for persistent chat Server in Lync server 2013](lync-server-2013-planning-for-persistent-chat-server.md).</span><span class="sxs-lookup"><span data-stu-id="43bfd-154">To provide greater capacity and reliability, you can deploy a multiple-server topology, as described in [Planning for Persistent Chat Server in Lync Server 2013](lync-server-2013-planning-for-persistent-chat-server.md).</span></span> <span data-ttu-id="43bfd-155">A topologia de vários servidores pode incluir até quatro computadores ativos que executam o servidor de chat persistente (as configurações de alta disponibilidade e recuperação de desastre permitirão até oito, mas apenas quatro podem estar ativas e as quatro restantes em espera).</span><span class="sxs-lookup"><span data-stu-id="43bfd-155">The multiple-server topology can include as many as four active computers running Persistent Chat Server (high availability and disaster recovery configurations will allow up to eight, but only four can be active and the remaining four on standby).</span></span> <span data-ttu-id="43bfd-156">Cada servidor pode suportar até 20.000 usuários simultâneos, para um total de 80.000 usuários simultâneos conectados a um pool de servidores de chat persistente com quatro servidores.</span><span class="sxs-lookup"><span data-stu-id="43bfd-156">Each server can support as many as 20,000 concurrent users, for a total of 80,000 concurrent users connected to a Persistent Chat Server pool with 4 servers.</span></span> <span data-ttu-id="43bfd-157">Uma topologia de vários servidores é o mesmo que a topologia de servidor único, exceto pelo fato de que vários servidores hospedam o servidor de chat persistente e podem ser dimensionados de forma mais alta.</span><span class="sxs-lookup"><span data-stu-id="43bfd-157">A multiple-server topology is the same as the single-server topology except that multiple servers host Persistent Chat Server, and can scale higher.</span></span> <span data-ttu-id="43bfd-158">Vários computadores que executam o servidor de chat persistente devem residir no mesmo domínio de serviços de domínio do Active Directory do Lync Server e no serviço de conformidade.</span><span class="sxs-lookup"><span data-stu-id="43bfd-158">Multiple computers running Persistent Chat Server should reside in the same Active Directory Domain Services domain as Lync Server and the Compliance service.</span></span>

<span data-ttu-id="43bfd-159">A figura a seguir mostra todos os componentes de uma topologia de vários servidores com vários computadores que executam o servidor de chat persistente, o serviço de conformidade opcional e um banco de dados de conformidade separado.</span><span class="sxs-lookup"><span data-stu-id="43bfd-159">The following figure shows all the components of a multiple-server topology with multiple computers running Persistent Chat Server, the optional Compliance service, and a separate compliance database.</span></span>

<span data-ttu-id="43bfd-160">**Vários Servidores de Chat Persistente**</span><span class="sxs-lookup"><span data-stu-id="43bfd-160">**Multiple Persistent Chat Servers**</span></span>

<span data-ttu-id="43bfd-161">![Topologia de vários servidores](images/Gg398500.19aea898-28df-4d9b-903c-f72ef062d919(OCS.15).jpg "Topologia de vários servidores")</span><span class="sxs-lookup"><span data-stu-id="43bfd-161">![Multiple server topology](images/Gg398500.19aea898-28df-4d9b-903c-f72ef062d919(OCS.15).jpg "Multiple server topology")</span></span>

<span data-ttu-id="43bfd-162">As topologias de vários servidores fornecem a funcionalidade de pool de servidores.</span><span class="sxs-lookup"><span data-stu-id="43bfd-162">Multiple-server topologies provide pooling of server functionality.</span></span> <span data-ttu-id="43bfd-163">Em um pool de servidores, os serviços de chat persistente se comunicam e compartilham dados.</span><span class="sxs-lookup"><span data-stu-id="43bfd-163">In a server pool, the Persistent Chat services communicate and share data.</span></span> <span data-ttu-id="43bfd-164">Por exemplo, o histórico de chat que foi lançado originalmente em um serviço de chat persistente está disponível em qualquer serviço de chat persistente no sistema.</span><span class="sxs-lookup"><span data-stu-id="43bfd-164">For example, chat history that was originally posted to one Persistent Chat service is available from any Persistent Chat service in the system.</span></span> <span data-ttu-id="43bfd-165">Um arquivo carregado por meio de um serviço de chat persistente pode ser acessado por qualquer serviço de chat persistente.</span><span class="sxs-lookup"><span data-stu-id="43bfd-165">A file that is uploaded through one Persistent Chat service can be accessed by any Persistent Chat service.</span></span> <span data-ttu-id="43bfd-166">Os usuários podem estar conectados a servidores de front-end do servidor de chat persistente diferentes e podem estar batendo papo e se comunicar uns com os outros.</span><span class="sxs-lookup"><span data-stu-id="43bfd-166">Users can be connected to different Persistent Chat Server Front End Servers and can be chatting and communicating with each other.</span></span>

<span data-ttu-id="43bfd-167">A porta padrão do TCP 8011 conecta um servidor a um pool de servidores e é usada pelo serviço de chat persistente para se comunicar entre si ou para fins administrativos.</span><span class="sxs-lookup"><span data-stu-id="43bfd-167">The default port of TCP 8011 connects a server to a server pool, and is used by the Persistent Chat service to communicate between themselves, or for administrative purposes.</span></span>

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

