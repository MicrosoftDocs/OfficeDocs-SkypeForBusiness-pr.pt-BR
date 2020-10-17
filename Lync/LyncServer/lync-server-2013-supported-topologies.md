---
title: As topologias do Lync Server 2013 suportadas
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Supported topologies
ms:assetid: 3475d430-0394-491b-a09b-ba85bd62be70
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425833(v=OCS.15)
ms:contentKeyID: 48183832
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4754881d2ed3205c4f06d5468001c6e45880278c
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48523958"
---
# <a name="supported-topologies-in-lync-server-2013"></a><span data-ttu-id="83064-102">Topologias com suporte no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="83064-102">Supported topologies in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="83064-103">_**Última modificação do tópico:** 2014-01-14_</span><span class="sxs-lookup"><span data-stu-id="83064-103">_**Topic Last Modified:** 2014-01-14_</span></span>

<span data-ttu-id="83064-104">O Lync Server 2013 oferece suporte à implantação de sites no local em uma organização e à integração de implantações locais com implantações do Lync Online, que é conhecido como implantação híbrida.</span><span class="sxs-lookup"><span data-stu-id="83064-104">Lync Server 2013 supports deployment of sites on premises in an organization and integration of on-premises deployments with Lync Online deployments, which is known as a hybrid deployment.</span></span> <span data-ttu-id="83064-105">Em uma implantação híbrida, alguns usuários são hospedados no local e outros, online.</span><span class="sxs-lookup"><span data-stu-id="83064-105">In a hybrid deployment, some users are homed on-premises and some users are homed online.</span></span>

<span data-ttu-id="83064-106">Para implantações locais, o Lync Server 2013 oferece suporte à implantação de um ou mais sites que podem ser dimensionados para atender aos requisitos de alta disponibilidade e local.</span><span class="sxs-lookup"><span data-stu-id="83064-106">For on-premises deployments, Lync Server 2013 supports deployment of one or more sites that can be scaled to meet high availability and location requirements.</span></span> <span data-ttu-id="83064-107">É possível estruturar esses sites e seus componentes para atender aos requisitos de acesso e resiliência de sua organização.</span><span class="sxs-lookup"><span data-stu-id="83064-107">You can structure these sites and their components to meet the access and resiliency requirements of your organization.</span></span>

<span data-ttu-id="83064-108">Uma implantação local do Lync Server 2013 consiste no seguinte:</span><span class="sxs-lookup"><span data-stu-id="83064-108">A Lync Server 2013 on-premises deployment consists of the following:</span></span>

  - <span data-ttu-id="83064-p103">A implantação deve conter pelo menos um site central (também conhecido como data center). Cada site central deve conter pelo menos um pool de Front-Ends Enterprise Edition ou servidor Standard Edition. Isso consiste no seguinte:</span><span class="sxs-lookup"><span data-stu-id="83064-p103">Your deployment must include at least one central site (also known as a data center). Each central site must contain at least one Enterprise Edition Front End pool or one Standard Edition server. These consist of the following:</span></span>
    
      - <span data-ttu-id="83064-112">O pool de Front-Ends Enterprise Edition, que consiste em um ou mais servidores de Front-End  (normalmente, pelo menos dois servidores de Front-End para dimensionamento) e um servidor de Back-End separado.</span><span class="sxs-lookup"><span data-stu-id="83064-112">Enterprise Edition Front End pool, which consists of one or more Front End Servers (typically, at least two Front End Servers for scalability) and a separate Back End Server.</span></span> <span data-ttu-id="83064-113">Um pool de front-ends pode conter no máximo doze servidores front-end.</span><span class="sxs-lookup"><span data-stu-id="83064-113">A Front End pool can contain a maximum of twelve Front End Servers.</span></span> <span data-ttu-id="83064-114">O balanceamento de carga é exigido para servidores de Front-End.</span><span class="sxs-lookup"><span data-stu-id="83064-114">Load balancing is required for multiple Front End Servers.</span></span> <span data-ttu-id="83064-115">Para o tráfego SIP, é recomendável o balanceamento de carga DNS, mas o balanceamento de carga de hardware também é suportado.</span><span class="sxs-lookup"><span data-stu-id="83064-115">For SIP traffic, we recommend DNS load balancing, but hardware load balancing is also supported.</span></span> <span data-ttu-id="83064-116">Se usar o balanceamento de carga DNS para o tráfego SIP, você ainda precisará de um balanceador de carga de hardware para o tráfego HTTP.</span><span class="sxs-lookup"><span data-stu-id="83064-116">If you use DNS load balancing for SIP traffic, you still need a hardware load balancer for HTTP traffic.</span></span> <span data-ttu-id="83064-117">Recomendamos o espelhamento do SQL Server para alta disponibilidade de bancos de dados.</span><span class="sxs-lookup"><span data-stu-id="83064-117">We recommend SQL Server mirroring for high availability of databases.</span></span> <span data-ttu-id="83064-118">O banco de dados de back-end exige uma instância separada, mas você pode colocar o banco de dados de arquivamento, de monitoramento, de chat persistente e de conformidade do chat persistente com ele.</span><span class="sxs-lookup"><span data-stu-id="83064-118">The back-end database requires a separate instance, but you can collocate the archiving database, monitoring database, persistent chat database, and persistent chat compliance database with it.</span></span> <span data-ttu-id="83064-119">O Lync Server 2013 suporta o uso de um cluster compartilhado para os compartilhamentos de arquivos em sua implantação.</span><span class="sxs-lookup"><span data-stu-id="83064-119">Lync Server 2013 supports the use of a shared cluster for the file shares in your deployment.</span></span> <span data-ttu-id="83064-120">Para obter detalhes sobre os requisitos de armazenamento de banco de dados, consulte [Database software support in Lync Server 2013](lync-server-2013-database-software-support.md).</span><span class="sxs-lookup"><span data-stu-id="83064-120">For details about database storage requirements, see [Database software support in Lync Server 2013](lync-server-2013-database-software-support.md).</span></span> <span data-ttu-id="83064-121">Para obter detalhes sobre os requisitos de armazenamento de arquivos, consulte [File Storage support in Lync Server 2013](lync-server-2013-file-storage-support.md).</span><span class="sxs-lookup"><span data-stu-id="83064-121">For details about file storage requirements, see [File storage support in Lync Server 2013](lync-server-2013-file-storage-support.md).</span></span>
        
        <div>
        

        > [!IMPORTANT]  
        > <span data-ttu-id="83064-122">Se você colocar os bancos de dados do Lync Server, é altamente recomendável avaliar todos os fatores que podem afetar a disponibilidade e o desempenho.</span><span class="sxs-lookup"><span data-stu-id="83064-122">If you collocate Lync Server databases, we highly recommend assessing all factors that might affect availability and performance.</span></span> <span data-ttu-id="83064-123">Para verificar os recursos de failover, é recomendável testar todos os cenários de failover.</span><span class="sxs-lookup"><span data-stu-id="83064-123">To verify failover capabilities, we recommend testing all failover scenarios.</span></span>

        
        </div>
    
      - <span data-ttu-id="83064-124">Servidor Standard Edition que inclui um banco de dados do SQL Server Express colocado.</span><span class="sxs-lookup"><span data-stu-id="83064-124">Standard Edition server, which includes a collocated SQL Server Express database.</span></span>

  - <span data-ttu-id="83064-125">A implantação também pode ter uma ou mais filiais associadas a um site central.</span><span class="sxs-lookup"><span data-stu-id="83064-125">Your deployment can also have one or more branch sites associated with a central site.</span></span>

<span data-ttu-id="83064-126">Esta seção descreve os sites e os componentes de uma implantação do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="83064-126">This section describes the sites and components of a Lync Server 2013 deployment.</span></span> <span data-ttu-id="83064-127">Para obter detalhes sobre o site, a topologia e o planejamento de componentes do Lync Server 2013, consulte [noções básicas de topologia que você deve saber antes de planejar o Lync server 2013](lync-server-2013-topology-basics-you-must-know-before-planning.md) e [topologias de referência no Lync Server 2013](lync-server-2013-reference-topologies.md) na documentação de planejamento.</span><span class="sxs-lookup"><span data-stu-id="83064-127">For details about Lync Server 2013 site, topology, and component planning, see [Topology basics you must know before planning for Lync Server 2013](lync-server-2013-topology-basics-you-must-know-before-planning.md) and [Reference topologies in Lync Server 2013](lync-server-2013-reference-topologies.md) in the Planning documentation.</span></span> <span data-ttu-id="83064-128">Para obter detalhes sobre a integração de componentes de versões anteriores, consulte [supported Migration Paths and coexistência Scenarios in Lync Server 2013](lync-server-2013-supported-migration-paths-and-coexistence-scenarios.md).</span><span class="sxs-lookup"><span data-stu-id="83064-128">For details about integration of components of previous releases, see [Supported migration paths and coexistence scenarios in Lync Server 2013](lync-server-2013-supported-migration-paths-and-coexistence-scenarios.md).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="83064-129">Não há suporte para pools estendidos para as funções de servidor front-end, Edge, mediação e diretor.</span><span class="sxs-lookup"><span data-stu-id="83064-129">Stretched pools are not supported for the Front End, Edge, Mediation, and Director server roles.</span></span>



</div>

<div>

## <a name="central-site-topologies-and-components-on-premises"></a><span data-ttu-id="83064-130">Topologias e componentes do site central (local)</span><span class="sxs-lookup"><span data-stu-id="83064-130">Central Site Topologies and Components (On-Premises)</span></span>

<span data-ttu-id="83064-131">Embora uma topologia de site central deva incluir um pool de Front-Ends ou servidor Standard Edition, cada site central também pode conter o seguinte:</span><span class="sxs-lookup"><span data-stu-id="83064-131">Although a central site topology must include one Front End pool or one Standard Edition server, each central site can also contain the following:</span></span>

  - <span data-ttu-id="83064-p107">Diversos pools de Front-Ends, que podem estar no mesmo domínio ou em domínios diferentes. No entanto, todos os servidores de Front-End de um pool de Front-Ends e o servidor de Back-End desse pool devem estar no mesmo domínio.</span><span class="sxs-lookup"><span data-stu-id="83064-p107">Multiple Front End pools, which can be in the same domain or different domains. However, all Front End Servers in a Front End pool, and the Back End Server for that pool, must be in the same domain.</span></span>

  - <span data-ttu-id="83064-134">Diversos Servidores Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="83064-134">Multiple Standard Edition servers.</span></span>

  - <span data-ttu-id="83064-135">O servidor do Office Web Apps, que é usado com o Office Web Applications no Lync Server 2013 para lidar com o compartilhamento e a renderização de apresentações do Microsoft PowerPoint.</span><span class="sxs-lookup"><span data-stu-id="83064-135">Office Web Apps Server, which is used with Office Web Applications in Lync Server 2013 to handle the sharing and rendering of Microsoft PowerPoint presentations.</span></span>

  - <span data-ttu-id="83064-136">Servidor de borda ou o pool de borda em sua rede de perímetro, se você quiser que sua implantação dê suporte a parceiros federados, conectividade de IM pública, um Gateway XMPP (Extensible Messaging and Presence Protocol), acesso de usuário remoto, participação de usuários anônimos em reuniões ou Unificação de mensagens (UM) do Exchange.</span><span class="sxs-lookup"><span data-stu-id="83064-136">Edge Server or Edge pool in your perimeter network, if you want your deployment to support federated partners, public IM connectivity, an extensible messaging and presence protocol (XMPP) gateway, remote user access, participation of anonymous users in meetings, or Exchange Unified Messaging (UM).</span></span> <span data-ttu-id="83064-137">Não é possível colocar nenhuma outra função de servidor com o servidor de borda.</span><span class="sxs-lookup"><span data-stu-id="83064-137">You cannot collocate any other server role with an Edge Server.</span></span> <span data-ttu-id="83064-138">É recomendável o balanceamento de carga DNS, quando apropriado, mas o balanceamento de carga de hardware também é suportado.</span><span class="sxs-lookup"><span data-stu-id="83064-138">We recommend DNS load balancing, where appropriate, but hardware load balancing is also supported.</span></span> <span data-ttu-id="83064-139">As interfaces de borda interna e externa devem usar o mesmo tipo de balanceamento de carga.</span><span class="sxs-lookup"><span data-stu-id="83064-139">The internal Edge interface and external Edge interface must use the same type of load balancing.</span></span> <span data-ttu-id="83064-140">Não é possível usar o balanceamento de carga DNS na interface de Borda e o balanceamento de carga de hardware na outra interface de Borda.</span><span class="sxs-lookup"><span data-stu-id="83064-140">You cannot use DNS load balancing on one Edge interface and hardware load balancing on the other Edge interface.</span></span> <span data-ttu-id="83064-141">Para obter detalhes sobre os requisitos de balanceamento de carga e suporte, consulte [Planning for External User Access in Lync server 2013](lync-server-2013-planning-for-external-user-access.md) na documentação de planejamento e [implantação de acesso de usuário externo no Lync Server 2013](lync-server-2013-deploying-external-user-access.md) na documentação de implantação.</span><span class="sxs-lookup"><span data-stu-id="83064-141">For details about load balancing requirements and support, see [Planning for external user access in Lync Server 2013](lync-server-2013-planning-for-external-user-access.md) in the Planning documentation and [Deploying external user access in Lync Server 2013](lync-server-2013-deploying-external-user-access.md) in the Deployment documentation.</span></span>

  - <span data-ttu-id="83064-142">Servidor ou pool de mediação, se você quiser dar suporte à conferência de discagem ou voz corporativa em um pool de front-ends no site central.</span><span class="sxs-lookup"><span data-stu-id="83064-142">Mediation Server or pool, if you want to support Enterprise Voice or dial-in conferencing in a Front End pool at the central site.</span></span> <span data-ttu-id="83064-143">Dependendo de como você implantou o suporte do Enterprise Voice, pode colocar o servidor de mediação em um pool de front-ends (o padrão) ou implantar um servidor ou pool de mediação autônomo.</span><span class="sxs-lookup"><span data-stu-id="83064-143">Depending on how you deploy Enterprise Voice support, you can collocate the Mediation Server in a Front End pool (the default) or deploy a stand-alone Mediation Server or pool.</span></span> <span data-ttu-id="83064-144">Você pode usar o balanceamento de carga de aplicativo, de hardware ou de DNS (quando apropriado) para distribuir o tráfego de um ponto de gateway de um pool de servidores de mediação, incluindo um gateway PSTN, IP-PBX ou controle de borda de sessão de tronco SIP (SBC). Para obter detalhes sobre como planejar a topologia do servidor de mediação apropriada, consulte [Deployment Guidelines for Mediation Server in Lync server 2013](lync-server-2013-deployment-guidelines-for-mediation-server.md) na documentação de planejamento.</span><span class="sxs-lookup"><span data-stu-id="83064-144">You can use DNS, hardware, or application load balancing (when appropriate) to distribute traffic from a Mediation Server pool’s gateway peer, including a PSTN gateway, IP-PBX, or SIP trunk Session Border Control (SBC).For details about planning the appropriate Mediation Server topology, see [Deployment guidelines for Mediation Server in Lync Server 2013](lync-server-2013-deployment-guidelines-for-mediation-server.md) in the Planning documentation.</span></span>

  - <span data-ttu-id="83064-145">Servidor de chat persistente, se você quiser que os usuários sejam capazes de participar de conversas com base em um tópico que persistem ao longo do tempo.</span><span class="sxs-lookup"><span data-stu-id="83064-145">Persistent Chat Server, if you want to users to be able to participate in multiparty, topic-based conversations that persist over time.</span></span> <span data-ttu-id="83064-146">Para fornecer mais capacidade e maior confiabilidade, sua topologia pode incluir vários computadores que executam o servidor de chat persistente.</span><span class="sxs-lookup"><span data-stu-id="83064-146">To provide more capacity and increased reliability, your topology can include multiple computers running Persistent Chat Server.</span></span> <span data-ttu-id="83064-147">Não é possível colocar o servidor de chat persistente com outras funções de servidor em um pool corporativo.</span><span class="sxs-lookup"><span data-stu-id="83064-147">You cannot collocate Persistent Chat Server with other server roles in an Enterprise pool.</span></span> <span data-ttu-id="83064-148">No entanto, você pode colocar o servidor de chat persistente em um servidor Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="83064-148">However, you can collocate Persistent Chat Server on a Standard Edition server.</span></span> <span data-ttu-id="83064-149">O chat persistente exige um banco de dados e, se você implementar a conformidade de chat persistente, um banco de dados de conformidade de chat persistente, porém os bancos de dados poderão ser colocados com o banco de dados de arquivamento, de monitoramento ou no servidor de Back-End de um pool de Front-Ends Enterprise Edition.</span><span class="sxs-lookup"><span data-stu-id="83064-149">Persistent chat requires a database and, if you implement persistent chat compliance, a persistent chat compliance database, but the databases can be collocated with the Archiving database, Monitoring database, or on the Back End Server of an Enterprise Edition Front End pool.</span></span> <span data-ttu-id="83064-150">Para obter detalhes sobre como planejar a topologia do servidor de chat persistente apropriada, consulte [Planning for persistent chat Server in Lync server 2013](lync-server-2013-planning-for-persistent-chat-server.md) na documentação de planejamento.</span><span class="sxs-lookup"><span data-stu-id="83064-150">For details about planning the appropriate Persistent Chat Server topology, see [Planning for Persistent Chat Server in Lync Server 2013](lync-server-2013-planning-for-persistent-chat-server.md) in the Planning documentation.</span></span>

  - <span data-ttu-id="83064-151">Monitoramento, se quiser oferecer suporte à coleta de dados sobre sua QoE (experiência de qualidade) de áudio/vídeo e CDR (gravação de detalhes da chamada) para o Enterprise Voice e as conferências de áudio/vídeo de sua implantação.</span><span class="sxs-lookup"><span data-stu-id="83064-151">Monitoring, if you want to support data collection for audio/video Quality of Experience (QoE) and call detail recording (CDR) for Enterprise Voice and A/V conferences in your deployment.</span></span> <span data-ttu-id="83064-152">Opcionalmente, você pode instalar o Microsoft System Center Operations Manager (anteriormente Microsoft Operations Manager), que usa o monitoramento de dados de CDR e QoE para gerar alertas quase em tempo real que mostram a integridade da chamada e a qualidade da mídia.</span><span class="sxs-lookup"><span data-stu-id="83064-152">Optionally, you can install the Microsoft System Center Operations Manager (formerly Microsoft Operations Manager), which uses Monitoring CDR and QoE data to generate near real-time alerts that show the health of call reliability and media quality.</span></span> <span data-ttu-id="83064-153">O monitoramento, quando implantado, é colocado em servidores Fron-End ou um servidor Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="83064-153">Monitoring, when deployed, is collocated on Front End Servers or a Standard Edition server.</span></span> <span data-ttu-id="83064-154">O monitoramento exige um banco de dados, mas o banco de dados pode ser colocado com o banco de dados de arquivamento, de chat persistente, do conformidade de chat persistente ou no servidor Back-End de um pool de Front-Ends Enterprise Edition.</span><span class="sxs-lookup"><span data-stu-id="83064-154">Monitoring requires a database, but the database can be collocated with the Archiving database, persistent chat database, persistent chat compliance database, or on the Back End Server of an Enterprise Edition Front End pool.</span></span>

  - <span data-ttu-id="83064-155">Arquivamento, se quiser arquivar comunicações de mensagens instantâneas e conteúdo de reuniões (por motivos de conformidade) em sua implantação.</span><span class="sxs-lookup"><span data-stu-id="83064-155">Archiving, if you want to archive IM communications and meeting content (for compliance reasons) in your deployment.</span></span> <span data-ttu-id="83064-156">O arquivamento, quando implantado, é colocado em servidores de Front-End ou em um servidor Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="83064-156">Archiving, when deployed, is collocated on Front End Servers or a Standard Edition server.</span></span> <span data-ttu-id="83064-157">O armazenamento de arquivamento requer a implantação de um banco de dados de arquivamento ou integração com o armazenamento do Exchange 2013.</span><span class="sxs-lookup"><span data-stu-id="83064-157">Archiving storage requires either deployment of an Archiving database or integration with Exchange 2013 storage.</span></span> <span data-ttu-id="83064-158">Se você usar ambos, que é conhecido como *modo misto*, o armazenamento 2013 do Exchange é usado para armazenar dados de arquivamento para usuários hospedados no Exchange 2013, e o banco de dados de arquivamento é usado para arquivar dados de todos os outros usuários em sua implantação.</span><span class="sxs-lookup"><span data-stu-id="83064-158">If you use both, which is known as *mixed mode*, Exchange 2013 storage is used to store archive data for users who are homed on Exchange 2013, and the Archiving database is used to archive data for all other users in your deployment.</span></span> <span data-ttu-id="83064-159">Se precisar de uma banco de dados de arquivamento, ele poderá ser colocado no banco de dados de monitoramento, de chat persistente, de conformidade do chat persistente ou no servidor de Back-End de um pool de Front-Ends.</span><span class="sxs-lookup"><span data-stu-id="83064-159">If you require an Archiving database, the database can be collocated on the Monitoring database, persistent chat database, persistent chat compliance database, or on the Back End Server of a Front End pool.</span></span> <span data-ttu-id="83064-160">Para obter detalhes sobre como planejar a topologia de arquivamento adequada, consulte [Planning for Archiving in Lync Server 2013](lync-server-2013-planning-for-archiving.md) na documentação de planejamento.</span><span class="sxs-lookup"><span data-stu-id="83064-160">For details about planning the appropriate Archiving topology, see [Planning for Archiving in Lync Server 2013](lync-server-2013-planning-for-archiving.md) in the Planning documentation.</span></span>

  - <span data-ttu-id="83064-161">Pool de diretor ou diretor, se você quiser facilitar a resiliência e o redirecionamento de solicitações de usuário do Lync Server 2013 para o pool de local do usuário, que pode ser um pool de front-ends Enterprise Edition ou um servidor Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="83064-161">Director or Director pool, if you want to facilitate resiliency and redirection of Lync Server 2013 user requests to the user’s home pool, which can be either an Enterprise Edition Front End pool or a Standard Edition server.</span></span> <span data-ttu-id="83064-162">É recomendável que seja implantado um diretor ou pool de diretores em cada site central que ofereça suporte ao acesso de usuários externos e em cada site central no qual é feita a implantação de um ou mais pools de Front-Ends.</span><span class="sxs-lookup"><span data-stu-id="83064-162">We recommend that you deploy a Director or Director pool in each central site that supports external user access and in each central site in which you deploy one or more Front End pools.</span></span> <span data-ttu-id="83064-163">Cada pool de diretores pode conter um máximo de dez diretores.</span><span class="sxs-lookup"><span data-stu-id="83064-163">Each Director pool can contain a maximum of ten Directors.</span></span> <span data-ttu-id="83064-164">Um diretor não pode ser colocado com nenhuma outra função de servidor.</span><span class="sxs-lookup"><span data-stu-id="83064-164">A Director cannot be collocated with any other server role.</span></span> <span data-ttu-id="83064-165">Para obter detalhes sobre como planejar a topologia de diretor apropriada, consulte [cenários para o diretor no Lync Server 2013](lync-server-2013-scenarios-for-the-director.md) na documentação de planejamento.</span><span class="sxs-lookup"><span data-stu-id="83064-165">For details about planning the appropriate Director topology, see [Scenarios for the Director in Lync Server 2013](lync-server-2013-scenarios-for-the-director.md) in the Planning documentation.</span></span>

  - <span data-ttu-id="83064-166">O proxy reverso, que não é um componente do Lync Server 2013, mas será necessário se você quiser dar suporte ao compartilhamento de conteúdo da Web para usuários federados ou para oferecer suporte ao tráfego de mobilidade.</span><span class="sxs-lookup"><span data-stu-id="83064-166">Reverse proxy, which is not a Lync Server 2013 component, but is required if you want to support sharing of web content for federated users or to support Mobility traffic.</span></span> <span data-ttu-id="83064-167">Não é possível colocar um servidor de proxy reverso com nenhuma função de servidor do Lync Server 2013, mas você pode implementar o suporte de proxy reverso para uma implantação do Lync Server 2013, configurando o suporte em um servidor de proxy reverso existente em sua organização usado para outros aplicativos.</span><span class="sxs-lookup"><span data-stu-id="83064-167">You cannot collocate a reverse proxy server with any Lync Server 2013 server role, but you can implement reverse proxy support for a Lync Server 2013 deployment by configuring the support on an existing reverse proxy server in your organization that is used for other applications.</span></span> <span data-ttu-id="83064-168">Para obter detalhes sobre servidores de proxy reverso, confira [Configurando servidores de proxy reverso para o Lync Server 2013](lync-server-2013-setting-up-reverse-proxy-servers.md) na documentação de implantação.</span><span class="sxs-lookup"><span data-stu-id="83064-168">For details about reverse proxy servers, see [Setting up reverse proxy servers for Lync Server 2013](lync-server-2013-setting-up-reverse-proxy-servers.md) in the Deployment documentation.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="83064-169">No Lync Server 2013, A conferência A/V, o monitoramento e o arquivamento são executados em servidores front-end e não são mais funções de servidor separadas.</span><span class="sxs-lookup"><span data-stu-id="83064-169">In Lync Server 2013, A/V Conferencing, Monitoring, and Archiving run on Front End Servers and are no longer separate server roles.</span></span>



</div>

<span data-ttu-id="83064-170">Todos os pools de front-ends e servidores Standard Edition que você implanta em um site central compartilham qualquer um dos seguintes itens implantados para o site central:</span><span class="sxs-lookup"><span data-stu-id="83064-170">All Front End pools and Standard Edition servers that you deploy at a central site share any of the following that you deploy for the central site:</span></span>

  - <span data-ttu-id="83064-171">Diretor ou pool de diretor</span><span class="sxs-lookup"><span data-stu-id="83064-171">Director or Director pool</span></span>

  - <span data-ttu-id="83064-172">Servidor ou pool de mediação autônomo</span><span class="sxs-lookup"><span data-stu-id="83064-172">Stand-alone Mediation Server or pool</span></span>

  - <span data-ttu-id="83064-173">Servidor do Office Web Apps</span><span class="sxs-lookup"><span data-stu-id="83064-173">Office Web Apps Server</span></span>

  - <span data-ttu-id="83064-174">Servidor de borda ou pool de borda</span><span class="sxs-lookup"><span data-stu-id="83064-174">Edge Server or Edge pool</span></span>

  - <span data-ttu-id="83064-175">Servidor ou pool de chat persistente</span><span class="sxs-lookup"><span data-stu-id="83064-175">Persistent Chat Server or pool</span></span>

  - <span data-ttu-id="83064-176">Monitoramento</span><span class="sxs-lookup"><span data-stu-id="83064-176">Monitoring</span></span>

  - <span data-ttu-id="83064-177">Arquivamento</span><span class="sxs-lookup"><span data-stu-id="83064-177">Archiving</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="83064-178">Um servidor de UM do Exchange pode ser implementado com sua implantação do Lync Server 2013 se você deseja oferecer suporte à integração da Unificação de mensagens do Exchange 2013, mas não é um componente do site do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="83064-178">An Exchange UM Server can be implemented with your Lync Server 2013 deployment if you want to support integration of Exchange 2013 Unified Messaging, but it is not a component of the Lync Server 2013 site.</span></span>



</div>

<span data-ttu-id="83064-179">Vários sites centrais também podem compartilhar qualquer um dos seguintes itens implantados em um site central:</span><span class="sxs-lookup"><span data-stu-id="83064-179">Multiple central sites can also share any of the following that you deploy in one central site:</span></span>

  - <span data-ttu-id="83064-180">Servidor ou pool de mediação autônomo</span><span class="sxs-lookup"><span data-stu-id="83064-180">Stand-alone Mediation Server or pool</span></span>

  - <span data-ttu-id="83064-181">Servidor de borda ou pool de borda</span><span class="sxs-lookup"><span data-stu-id="83064-181">Edge Server or Edge pool</span></span>

  - <span data-ttu-id="83064-182">Servidor ou pool de chat persistente</span><span class="sxs-lookup"><span data-stu-id="83064-182">Persistent Chat Server or pool</span></span>

  - <span data-ttu-id="83064-183">Arquivamento</span><span class="sxs-lookup"><span data-stu-id="83064-183">Archiving</span></span>

  - <span data-ttu-id="83064-184">Monitoramento</span><span class="sxs-lookup"><span data-stu-id="83064-184">Monitoring</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="83064-185">Um servidor de UM do Exchange pode ser implementado com sua implantação do Lync Server 2013 e compartilhado por vários sites centrais, mas não é um componente do site do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="83064-185">An Exchange UM Server can be implemented with your Lync Server 2013 deployment and shared by multiple central sites, but it is not a component of the Lync Server 2013 site.</span></span>



</div>

<span data-ttu-id="83064-186">Para obter detalhes sobre funções e funcionalidades de servidor do Lync Server 2013, consulte [Server Roles in Lync server 2013](lync-server-2013-server-roles.md) na documentação de planejamento.</span><span class="sxs-lookup"><span data-stu-id="83064-186">For details about Lync Server 2013 server roles and functionality, see [Server roles in Lync Server 2013](lync-server-2013-server-roles.md) in the Planning documentation.</span></span>

<span data-ttu-id="83064-187">Para obter um resumo do suporte à colocação do servidor do Lync Server 2013, consulte [colocação de servidor suportado no Lync server 2013](lync-server-2013-supported-server-collocation.md).</span><span class="sxs-lookup"><span data-stu-id="83064-187">For a summary of Lync Server 2013 server collocation support, see [Supported server collocation in Lync Server 2013](lync-server-2013-supported-server-collocation.md).</span></span>

<span data-ttu-id="83064-188">Além das funções e funcionalidades de servidor abordadas anteriormente nesta seção, o Lync Server 2013 tem componentes e opções adicionais, que podem incluir alguns ou todos os seguintes itens:</span><span class="sxs-lookup"><span data-stu-id="83064-188">In addition to the server roles and functionality covered previously in this section, Lync Server 2013 has additional components and options, which can include some or all of the following:</span></span>

  - <span data-ttu-id="83064-189">Firewalls</span><span class="sxs-lookup"><span data-stu-id="83064-189">Firewalls</span></span>

  - <span data-ttu-id="83064-190">Gateways PSTN (se estiver implantando o Enterprise Voice)</span><span class="sxs-lookup"><span data-stu-id="83064-190">PSTN gateways (if deploying Enterprise Voice)</span></span>

  - <span data-ttu-id="83064-191">Servidor UM do Exchange</span><span class="sxs-lookup"><span data-stu-id="83064-191">Exchange UM Server</span></span>

  - <span data-ttu-id="83064-192">Balanceamento de carga DNS</span><span class="sxs-lookup"><span data-stu-id="83064-192">DNS load balancing</span></span>

  - <span data-ttu-id="83064-193">Balanceadores de carga de hardware</span><span class="sxs-lookup"><span data-stu-id="83064-193">Hardware load balancers</span></span>

  - <span data-ttu-id="83064-194">Bancos de dados do SQL Server</span><span class="sxs-lookup"><span data-stu-id="83064-194">SQL Server databases</span></span>

  - <span data-ttu-id="83064-195">Compartilhamentos de arquivo</span><span class="sxs-lookup"><span data-stu-id="83064-195">File shares</span></span>

<span data-ttu-id="83064-196">Para obter detalhes sobre todos os recursos, componentes e opções do Lync Server 2013, consulte a documentação de planejamento.</span><span class="sxs-lookup"><span data-stu-id="83064-196">For details about all of the Lync Server 2013 features, components, and options, see the Planning documentation.</span></span>

</div>

<div>

## <a name="branch-site-topologies-and-components-on-premises"></a><span data-ttu-id="83064-197">Topologias e componentes do site de filial (local)</span><span class="sxs-lookup"><span data-stu-id="83064-197">Branch Site Topologies and Components (On-Premises)</span></span>

<span data-ttu-id="83064-198">Um site de filial é associado a um site central, e cada aparelho de filial persistente em um site de filial é associado a um pool de front-ends Enterprise Edition ou um servidor Standard Edition no site central associado.</span><span class="sxs-lookup"><span data-stu-id="83064-198">A branch site is associated with a central site, and each Survivable Branch Appliance in a branch site is associated with an Enterprise Edition Front End pool or a Standard Edition server in the associated central site.</span></span> <span data-ttu-id="83064-199">Os sites de filiais dependem do site central para a maioria de suas funcionalidades, de forma que os componentes em um site de filial contenham apenas o seguinte:</span><span class="sxs-lookup"><span data-stu-id="83064-199">Branch sites depend on the central site for most of their functionality, so components at a branch site contain only the following:</span></span>

  - <span data-ttu-id="83064-200">Um aparelho de filial persistente, que combina um gateway PSTN (rede telefônica pública comutada) com algumas funcionalidades do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="83064-200">A Survivable Branch Appliance, which combines a public switched telephone network (PSTN) gateway with some Lync Server functionality.</span></span> <span data-ttu-id="83064-201">Um servidor de mediação pode ser colocado com a instância do registrador no aparelho de filial persistente, e você pode implantar um servidor de mediação autônomo ou pool de servidores de mediação.</span><span class="sxs-lookup"><span data-stu-id="83064-201">A Mediation Server can be collocated with the instance of the Registrar on the Survivable Branch Appliance, and you can deploy a stand-alone Mediation Server or pool of Mediation Servers.</span></span>

  - <span data-ttu-id="83064-202">Um servidor de filial persistente, que é um servidor que executa o Windows Server e que tem o software de servidor de mediação do Lync Server 2013 instalado.</span><span class="sxs-lookup"><span data-stu-id="83064-202">A Survivable Branch Server, which is a server running Windows Server that has Lync Server 2013 Registrar and Mediation Server software installed.</span></span>

  - <span data-ttu-id="83064-203">Um gateway PSTN autônomo (não faz parte do aparelho de filial persistente) e um servidor de mediação autônomo.</span><span class="sxs-lookup"><span data-stu-id="83064-203">A stand-alone PSTN gateway (not part of the Survivable Branch Appliance) and a stand-alone Mediation Server.</span></span>

<span data-ttu-id="83064-204">Os requisitos para servidores de filial persistentes são os mesmos dos requisitos para qualquer função de servidor do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="83064-204">The requirements for Survivable Branch Servers are the same as the requirements for any Lync Server 2013 server role.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

