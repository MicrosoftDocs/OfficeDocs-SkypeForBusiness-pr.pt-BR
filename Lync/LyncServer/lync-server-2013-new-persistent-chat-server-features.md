---
title: 'Lync Server 2013: novos recursos do servidor de chat persistente'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: New Persistent Chat Server features
ms:assetid: c3ec6f33-6261-4bf5-aa31-baa8ab2a87d8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412965(v=OCS.15)
ms:contentKeyID: 48185341
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5b8718d5f3dda34b97b4c3e96c2fe9531d6658b9
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42216777"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="new-persistent-chat-server-features-in-lync-server-2013"></a><span data-ttu-id="e5c77-102">Novos recursos do servidor de chat persistente no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e5c77-102">New Persistent Chat Server features in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e5c77-103">_**Última modificação do tópico:** 2012-10-29_</span><span class="sxs-lookup"><span data-stu-id="e5c77-103">_**Topic Last Modified:** 2012-10-29_</span></span>

<span data-ttu-id="e5c77-104">Lync Server 2013, servidor de chat persistente permite que você participe de conversas com vários tópicos, com base em tópico que persistem ao longo do tempo.</span><span class="sxs-lookup"><span data-stu-id="e5c77-104">Lync Server 2013, Persistent Chat Server enables you to participate in multiparty, topic-based conversations that persist over time.</span></span> <span data-ttu-id="e5c77-105">O servidor de chat persistente pode ajudar sua organização a fazer o seguinte:</span><span class="sxs-lookup"><span data-stu-id="e5c77-105">Persistent Chat Server can help your organization do the following:</span></span>

  - <span data-ttu-id="e5c77-106">Melhorar a comunicação entre equipes geograficamente distante e multifuncionais</span><span class="sxs-lookup"><span data-stu-id="e5c77-106">Improve communication between geographically dispersed and cross-functional teams</span></span>

  - <span data-ttu-id="e5c77-107">Ampliar a conscientização e participação da informação</span><span class="sxs-lookup"><span data-stu-id="e5c77-107">Broaden information awareness and participation</span></span>

  - <span data-ttu-id="e5c77-108">Melhorar a comunicação com sua organização estendida</span><span class="sxs-lookup"><span data-stu-id="e5c77-108">Improve communication with your extended organization</span></span>

  - <span data-ttu-id="e5c77-109">Reduzir sobrecarga informacional</span><span class="sxs-lookup"><span data-stu-id="e5c77-109">Reduce information overload</span></span>

  - <span data-ttu-id="e5c77-110">Melhorar a conscientização da informação</span><span class="sxs-lookup"><span data-stu-id="e5c77-110">Improve information awareness</span></span>

  - <span data-ttu-id="e5c77-111">Melhorar a dispersão de informações e conhecimentos importantes</span><span class="sxs-lookup"><span data-stu-id="e5c77-111">Increase dispersion of important knowledge and information</span></span>

<span data-ttu-id="e5c77-112">Lync Server 2013, servidor de chat persistente não está disponível no Microsoft Office 365.</span><span class="sxs-lookup"><span data-stu-id="e5c77-112">Lync Server 2013, Persistent Chat Server is not available in Microsoft Office 365.</span></span> <span data-ttu-id="e5c77-113">No momento, ele está disponível somente para os clientes do Lync 2013 local.</span><span class="sxs-lookup"><span data-stu-id="e5c77-113">At this time, it is available only to on-premise Lync 2013 customers.</span></span>

<span data-ttu-id="e5c77-114">No Lync 2013, a funcionalidade de chat persistente é integrada ao cliente Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="e5c77-114">In Lync 2013, Persistent Chat functionality is integrated into the Lync 2013 client.</span></span> <span data-ttu-id="e5c77-115">Como resultado, os usuários têm acesso a mensagens instantâneas/presença, áudio/vídeo, conferência e chat persistente, tudo no cliente do Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="e5c77-115">As a result, users have access to Instant Messaging/Presence, Audio/Video, Conferencing, and Persistent Chat all in the Lync 2013 client.</span></span> <span data-ttu-id="e5c77-116">Para obter mais informações sobre o cliente Lync 2013, <https://go.microsoft.com/fwlink/p/?linkid=270877>consulte.</span><span class="sxs-lookup"><span data-stu-id="e5c77-116">For more information about the Lync 2013 client, see <https://go.microsoft.com/fwlink/p/?linkid=270877>.</span></span>

<span data-ttu-id="e5c77-117">Este tópico descreve as alterações de recursos entre a nova versão do Lync Server 2013, o servidor de chat persistente e a versão anterior (Microsoft Lync Server 2010, chat de grupo), incluindo:</span><span class="sxs-lookup"><span data-stu-id="e5c77-117">This topic describes feature changes between the new version of Lync Server 2013, Persistent Chat Server and the previous version (Microsoft Lync Server 2010, Group Chat), including:</span></span>

  - <span data-ttu-id="e5c77-118">Fornecer uma experiência administrativa no painel de controle do Lync Server e eliminar a ferramenta de administração de chat de grupo</span><span class="sxs-lookup"><span data-stu-id="e5c77-118">Provide an administrative experience in Lync Server Control Panel, and eliminate the Group Chat Admin Tool</span></span>

  - <span data-ttu-id="e5c77-119">Integre as definições de configuração para o servidor de chat persistente no construtor de topologias eliminando a ferramenta de configuração de chat de grupo</span><span class="sxs-lookup"><span data-stu-id="e5c77-119">Integrate configuration settings for Persistent Chat Server into Topology Builder by eliminating the Group Chat Configuration tool</span></span>

  - <span data-ttu-id="e5c77-120">Facilitar a migração e a atualização de versões anteriores do servidor de chat persistente</span><span class="sxs-lookup"><span data-stu-id="e5c77-120">Ease migration and upgrade from previous versions of Persistent Chat Server</span></span>

  - <span data-ttu-id="e5c77-121">Fornecer soluções de alta disponibilidade e recuperação de desastre</span><span class="sxs-lookup"><span data-stu-id="e5c77-121">Provide high availability and disaster recovery solutions</span></span>

<span data-ttu-id="e5c77-122">Para obter detalhes adicionais sobre a versão mais recente do servidor de chat persistente, confira o seguinte:</span><span class="sxs-lookup"><span data-stu-id="e5c77-122">For additional details about the latest version of Persistent Chat Server, see the following:</span></span>

  - <span data-ttu-id="e5c77-123">A ajuda de chat persistente <https://go.microsoft.com/fwlink/p/?linkid=270945> em que fornece uma lista detalhada de recursos de chat persistente, como eles funcionam e como usá-los ao executar o servidor de chat persistente.</span><span class="sxs-lookup"><span data-stu-id="e5c77-123">The Persistent Chat Help at <https://go.microsoft.com/fwlink/p/?linkid=270945> which provides a detailed list of Persistent Chat features, how they work, and how to use them while running Persistent Chat Server.</span></span>

  - <span data-ttu-id="e5c77-124">O [planejamento para servidor de chat persistente no Lync Server 2013](lync-server-2013-planning-for-persistent-chat-server.md) na documentação de planejamento [implantando servidor de chat persistente no Lync Server 2013](lync-server-2013-deploying-persistent-chat-server.md) na documentação de implantação, [migração do Lync Server 2010, chat de grupo ou Office Communications Server 2007 R2 group chat to Lync Server 2013, servidor de chat persistente](migration-from-lync-server-2010-group-chat-or-office-communications-server-2007-r2-group-chat-to-lync-server-2013-persistent-chat-server.md) na documentação de migração e [Gerenciando o Lync Server 2013, servidor](managing-lync-server-2013-persistent-chat-server.md) de chat persistente na documentação operações, todos fornecem instruções para configurar Servidor de chat persistente.</span><span class="sxs-lookup"><span data-stu-id="e5c77-124">The [Planning for Persistent Chat Server in Lync Server 2013](lync-server-2013-planning-for-persistent-chat-server.md) in the Planning documentation, [Deploying Persistent Chat Server in Lync Server 2013](lync-server-2013-deploying-persistent-chat-server.md) in the Deployment documentation, [Migration from Lync Server 2010, Group Chat or Office Communications Server 2007 R2 Group Chat to Lync Server 2013, Persistent Chat Server](migration-from-lync-server-2010-group-chat-or-office-communications-server-2007-r2-group-chat-to-lync-server-2013-persistent-chat-server.md) in the Migration documentation, and [Managing Lync Server 2013, Persistent Chat Server](managing-lync-server-2013-persistent-chat-server.md) in the Operations documentation, all of which provide instructions for setting up Persistent Chat Server.</span></span>

  - <span data-ttu-id="e5c77-125">O arquivo. msi da documentação do servidor de chat persistente (arquivo do Windows Installer) permite que os usuários acessem uma documentação offline abrangente sobre o servidor de chat persistente.</span><span class="sxs-lookup"><span data-stu-id="e5c77-125">The Persistent Chat Server Documentation.msi file (Windows Installer file) lets users access comprehensive offline documentation about Persistent Chat Server.</span></span>

<div>

## <a name="key-topology-changes-for-persistent-chat-server"></a><span data-ttu-id="e5c77-126">Alterações de topologia de chave para o servidor de chat persistente</span><span class="sxs-lookup"><span data-stu-id="e5c77-126">Key Topology Changes for Persistent Chat Server</span></span>

<span data-ttu-id="e5c77-127">As seguintes alterações de alto nível para o servidor de chat persistente incluem:</span><span class="sxs-lookup"><span data-stu-id="e5c77-127">The following high-level changes for Persistent Chat Server include:</span></span>

<span data-ttu-id="e5c77-128">O servidor de chat persistente agora é uma função de servidor.</span><span class="sxs-lookup"><span data-stu-id="e5c77-128">Persistent Chat Server is now a server role.</span></span> <span data-ttu-id="e5c77-129">No Microsoft Lync Server 2010, o servidor de chat de grupo era um aplicativo confiável de terceiros para o Microsoft Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="e5c77-129">In Microsoft Lync Server 2010, Group Chat Server was a third-party trusted application for Microsoft Lync Server 2010.</span></span> <span data-ttu-id="e5c77-130">O chat persistente pode ser adicionado à sua topologia do Lync Server 2013 usando o construtor de topologias.</span><span class="sxs-lookup"><span data-stu-id="e5c77-130">Persistent Chat can be added to your Lync Server 2013 topology by using Topology Builder.</span></span> <span data-ttu-id="e5c77-131">No Lync Server 2013, a funcionalidade do servidor de chat persistente é implementada usando três novas funções de servidor:</span><span class="sxs-lookup"><span data-stu-id="e5c77-131">In Lync Server 2013, Persistent Chat Server functionality is implemented by using three new server roles:</span></span>

  - <span data-ttu-id="e5c77-132">**PersistentChatService:** Esta é a função de front-end para chat persistente.</span><span class="sxs-lookup"><span data-stu-id="e5c77-132">**PersistentChatService:** This is the front end role for Persistent Chat.</span></span> <span data-ttu-id="e5c77-133">Nas implantações Standard Edition, a função de serviço servidor de chat persistente é posicionada no servidor Standard Edition implantado pelo bootstrapper, como qualquer outra função do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="e5c77-133">In Standard Edition deployments, Persistent Chat Server Service Role is collocated on the Standard Edition server deployed by Bootstrapper, like any other Lync Server role.</span></span> <span data-ttu-id="e5c77-134">Nas implantações Enterprise Edition, a função de serviço de chat persistente é implantada em computadores autônomos pelo bootstrapper, como qualquer outra função do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="e5c77-134">In Enterprise Edition deployments, Persistent Chat Service Role is deployed on stand-alone computers by Bootstrapper, like any other Lync Server role.</span></span>

  - <span data-ttu-id="e5c77-135">**PersistentChatStore:** Servidor back-end que corresponde ao banco de dados de conteúdo de chat persistente, onde todo o conteúdo de chat é armazenado.</span><span class="sxs-lookup"><span data-stu-id="e5c77-135">**PersistentChatStore:** Back End Server that corresponds to the Persistent Chat content database, where all the chat content is stored.</span></span>

  - <span data-ttu-id="e5c77-136">**PersistentChatComplianceStore:** Função de servidor back-end que corresponde ao banco de dados de conformidade de chat persistente, onde todos os eventos de conformidade são armazenados.</span><span class="sxs-lookup"><span data-stu-id="e5c77-136">**PersistentChatComplianceStore:** Back End Server role that corresponds to the Persistent Chat Compliance database, where all compliance events are stored.</span></span>

<span data-ttu-id="e5c77-137">Essas funções de servidor de chat persistente são opcionais e são instaladas apenas por clientes que desejam uma funcionalidade abrangente de servidor de chat persistente.</span><span class="sxs-lookup"><span data-stu-id="e5c77-137">These Persistent Chat Server roles are optional, and are installed only by customers who want comprehensive Persistent Chat Server functionality.</span></span> <span data-ttu-id="e5c77-138">A função **PersistentChatComplianceStore** é necessária somente se você optar por implantar a conformidade de chat persistente.</span><span class="sxs-lookup"><span data-stu-id="e5c77-138">The **PersistentChatComplianceStore** role is needed only if you choose to deploy Persistent Chat Compliance.</span></span>

<span data-ttu-id="e5c77-139">A função **PersistentChatService** executa dois serviços:</span><span class="sxs-lookup"><span data-stu-id="e5c77-139">The **PersistentChatService** role runs two services:</span></span>

  - <span data-ttu-id="e5c77-140">Serviço de chat persistente</span><span class="sxs-lookup"><span data-stu-id="e5c77-140">Persistent Chat service</span></span>

  - <span data-ttu-id="e5c77-141">Serviço de conformidade de chat persistente</span><span class="sxs-lookup"><span data-stu-id="e5c77-141">Persistent Chat Compliance service</span></span>

<span data-ttu-id="e5c77-142">A execução desses serviços em cada servidor de chat persistente oferece alta disponibilidade para esses serviços em um pool de servidor de chat persistente de muitos servidores.</span><span class="sxs-lookup"><span data-stu-id="e5c77-142">Having these services run on each Persistent Chat Server provides high availability for these services in a multiserver Persistent Chat Server pool.</span></span>

<span data-ttu-id="e5c77-143">Além disso, para dar suporte ao upload e download de arquivos em salas de chat persistente, o servidor de chat persistente inclui um serviço Web.</span><span class="sxs-lookup"><span data-stu-id="e5c77-143">Additionally, to support the file upload and download in Persistent Chat rooms, Persistent Chat Server includes a web service.</span></span> <span data-ttu-id="e5c77-144">Anteriormente, esse serviço foi colocado no servidor de chat persistente, servidor front-end e IIS (serviços de informações da Internet) necessários para serem instalados como um pré-requisito.</span><span class="sxs-lookup"><span data-stu-id="e5c77-144">Previously, this service was collocated on the Persistent Chat Server, Front End Server and required Internet Information Services (IIS) to be installed as a prerequisite.</span></span> <span data-ttu-id="e5c77-145">No servidor de chat persistente do Lync Server 2013, o serviço Web de upload/download de arquivos é colocado com o servidor front-end do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="e5c77-145">In Lync Server 2013 Persistent Chat Server, the File Upload/Download web service is collocated with the Lync Server 2013 Front End Server.</span></span> <span data-ttu-id="e5c77-146">Como efeito colateral, o IIS (serviços de informações da Internet) não é mais um pré-requisito para o servidor de chat persistente.</span><span class="sxs-lookup"><span data-stu-id="e5c77-146">As a side effect, Internet Information Services (IIS) is no longer a prerequisite for Persistent Chat Server.</span></span> <span data-ttu-id="e5c77-147">O serviço Web de upload/download de arquivos é identificado como **PersistentChat** no Gerenciador dos serviços de informações da Internet (IIS).</span><span class="sxs-lookup"><span data-stu-id="e5c77-147">The File Upload/Download web service is identified as **PersistentChat** in the Internet Information Services (IIS) Manager.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="e5c77-148">A função <STRONG>PersistentChatService</STRONG> pode ser executada no mesmo servidor que um servidor front-&nbsp;end do Lync Server 2013 somente se esse servidor front-end for&nbsp;um servidor front-end Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="e5c77-148">The <STRONG>PersistentChatService</STRONG> role can run on the same server as a Lync Server 2013&nbsp;Front End Server only if that Front End Server is a Standard Edition&nbsp;Front End Server.</span></span> <span data-ttu-id="e5c77-149">A função <STRONG>PersistentChatService</STRONG> não pode ser executada independentemente de um servidor&nbsp;Front-End do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="e5c77-149">The <STRONG>PersistentChatService</STRONG> role cannot run independently of a Lync Server 2013&nbsp;Front End Server.</span></span> <span data-ttu-id="e5c77-150">Ele só pode ser instalado no contexto de uma implantação do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="e5c77-150">It can be installed only in the context of a Lync Server 2013 deployment.</span></span>



</div>

<span data-ttu-id="e5c77-151">No servidor de chat persistente, o serviço de pesquisa foi eliminado.</span><span class="sxs-lookup"><span data-stu-id="e5c77-151">In Persistent Chat Server, Lookup service has been eliminated.</span></span> <span data-ttu-id="e5c77-152">No Lync Server 2010, chat de grupo, o serviço de pesquisa foi executado em cada servidor de front-end do servidor de chat de grupo e executou o roteamento para um dos servidores de canal.</span><span class="sxs-lookup"><span data-stu-id="e5c77-152">In Lync Server 2010, Group Chat, the Lookup service ran on every Group Chat Server Front End Server, and performed routing to one of the Channel Servers.</span></span> <span data-ttu-id="e5c77-153">O Lync Server 2013 depende do roteamento usando objetos de contato, onde cada pool de servidor de chat persistente é representado por um objeto de contato que é usado pelos servidores front-end do Lync Server para identificar e rotear solicitações para um pool de servidor de chat persistente apropriado e para um dos computadores que executam o servidor de chat persistente no pool.</span><span class="sxs-lookup"><span data-stu-id="e5c77-153">Lync Server 2013 relies on routing by using contact objects, where each Persistent Chat Server pool is represented by a contact object that is used by the Lync Server Front End Servers to identify and route requests to an appropriate Persistent Chat Server pool, and to one of the computers running Persistent Chat Server in the pool.</span></span>

<span data-ttu-id="e5c77-154">No Lync Server 2013, há modificações no serviço de conformidade:</span><span class="sxs-lookup"><span data-stu-id="e5c77-154">In Lync Server 2013, there are Compliance service modifications:</span></span>

  - <span data-ttu-id="e5c77-155">No Lync Server 2010, o serviço de conformidade executou autônomo (não posicionado) e somente em um único servidor.</span><span class="sxs-lookup"><span data-stu-id="e5c77-155">In Lync Server 2010, the Compliance service ran stand-alone (non-collocated), and only on a single server.</span></span> <span data-ttu-id="e5c77-156">O serviço de conformidade agora é executado em todos os servidores de front-end do servidor de chat persistente, junto com o serviço de chat persistente, e, portanto, oferece alta disponibilidade em um pool de servidor de chat persistente de muitos servidores.</span><span class="sxs-lookup"><span data-stu-id="e5c77-156">The Compliance service now runs on all the Persistent Chat Server Front End Servers, alongside the Persistent Chat service, and thereby provides high availability in a multiserver Persistent Chat Server pool.</span></span> <span data-ttu-id="e5c77-157">Um único adaptador de conformidade pode ser configurado para extrair dados do banco de dados de conformidade e para um dos outros sistemas (arquivo XML, arquivos hospedados no Exchange e assim por diante).</span><span class="sxs-lookup"><span data-stu-id="e5c77-157">A single compliance adapter can be configured to extract data from the compliance database and into one of the other systems (XML file, Exchange-hosted archives, and so on).</span></span> <span data-ttu-id="e5c77-158">O servidor de chat persistente inclui um adaptador XML.</span><span class="sxs-lookup"><span data-stu-id="e5c77-158">Persistent Chat Server includes an XML adapter.</span></span>

  - <span data-ttu-id="e5c77-159">A fila de enfileiramento de mensagens (também conhecida como MSMQ) que é compartilhada pelo serviço de chat persistente e o serviço de conformidade em cada servidor de front-end do servidor de chat persistente agora é uma fila privada compartilhada apenas pelos dois serviços.</span><span class="sxs-lookup"><span data-stu-id="e5c77-159">The Message Queuing (also known as MSMQ) queue that is shared by the Persistent Chat service and the Compliance service on each Persistent Chat Server Front End Server is now a private queue shared only by the two services.</span></span> <span data-ttu-id="e5c77-160">Todos os serviços de conformidade gravam no mesmo banco de dados de back-end de conformidade.</span><span class="sxs-lookup"><span data-stu-id="e5c77-160">All compliance services write to the same Compliance Back End database.</span></span> <span data-ttu-id="e5c77-161">Eles também são lidos a partir desse banco de dados, com o objetivo de enviar os dados para sua instância do adaptador.</span><span class="sxs-lookup"><span data-stu-id="e5c77-161">They also all read from that database, for the purpose of sending the data to their instance of the adapter.</span></span> <span data-ttu-id="e5c77-162">O servidor back-end de conformidade é representado como uma nova função de servidor back-end.</span><span class="sxs-lookup"><span data-stu-id="e5c77-162">The Compliance Back End Server is represented as a new Back End Server role.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="e5c77-163">Como nas versões anteriores, todos os dados de conformidade são processados apenas uma vez.</span><span class="sxs-lookup"><span data-stu-id="e5c77-163">As in previous versions, all compliance data is processed only once.</span></span> <span data-ttu-id="e5c77-164">Os dados podem ser processados por qualquer instância do adaptador invocada pelo serviço de conformidade executado nos vários computadores do servidor de chat persistente do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="e5c77-164">The data may be processed by any of the adapter instances invoked by the compliance service running on the various Lync Server 2013, Persistent Chat Server computers.</span></span> <span data-ttu-id="e5c77-165">No servidor de chat persistente, qualquer uma das instâncias de adaptador poderia processar os dados.</span><span class="sxs-lookup"><span data-stu-id="e5c77-165">In Persistent Chat Server, any one of the adapter instances could process the data.</span></span>

    
    </div>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="e5c77-166">Para obter informações sobre como instalar o enfileiramento de mensagens, consulte <A href="lync-server-2013-install-operating-systems-and-prerequisite-software-on-servers.md">instalar sistemas operacionais e software de pré-requisito nos servidores do Lync Server 2013</A> na documentação de implantação.</span><span class="sxs-lookup"><span data-stu-id="e5c77-166">For information about installing Message Queuing, see <A href="lync-server-2013-install-operating-systems-and-prerequisite-software-on-servers.md">Install operating systems and prerequisite software on servers for Lync Server 2013</A> in the Deployment documentation.</span></span>

    
    </div>

<span data-ttu-id="e5c77-167">No Lync Server 2013, há melhorias na alta disponibilidade e recuperação de desastres:</span><span class="sxs-lookup"><span data-stu-id="e5c77-167">In Lync Server 2013, there are improvements in both high availability and disaster recovery:</span></span>

  - <span data-ttu-id="e5c77-168">Melhorias de alta disponibilidade: o espelhamento do SQL Server é usado para fornecer alta disponibilidade para o banco de dados de conteúdo do servidor de chat persistente e o banco de dados de conformidade de chat persistente em um Data Center (in-site).</span><span class="sxs-lookup"><span data-stu-id="e5c77-168">High availability improvements: SQL Server mirroring is used to provide high availability for the Persistent Chat Server content database and Persistent Chat compliance database within a data center (in-site).</span></span>

  - <span data-ttu-id="e5c77-169">Melhorias de recuperação de desastre: o servidor de chat persistente suporta uma arquitetura de pool estendido que permite que um único pool de servidor de chat persistente seja estendido entre dois sites (ou seja, um único pool lógico na topologia, com os servidores no pool fisicamente localizado em dois sites.</span><span class="sxs-lookup"><span data-stu-id="e5c77-169">Disaster recovery improvements: Persistent Chat Server supports a stretched pool architecture that enables a single Persistent Chat Server pool to be stretched across two sites (that is, a single logical pool in the topology, with servers in the pool physically located across two sites).</span></span> <span data-ttu-id="e5c77-170">O envio de logs do SQL Server é usado para recuperação de desastre entre sites.</span><span class="sxs-lookup"><span data-stu-id="e5c77-170">SQL Server Log Shipping is used for cross-site disaster recovery.</span></span>

<span data-ttu-id="e5c77-171">Para obter mais informações sobre alta disponibilidade e recuperação de desastre, consulte [Configuring persistent chat Server for High Availability and Disaster Recovery in Lync Server 2013](lync-server-2013-configuring-persistent-chat-server-for-high-availability-and-disaster-recovery.md) na documentação de implantação.</span><span class="sxs-lookup"><span data-stu-id="e5c77-171">For more information about high availability and disaster recovery, see [Configuring Persistent Chat Server for high availability and disaster recovery in Lync Server 2013](lync-server-2013-configuring-persistent-chat-server-for-high-availability-and-disaster-recovery.md) in the Deployment documentation.</span></span>

</div>

<div>

## <a name="key-administration-and-management-changes-for-persistent-chat-server"></a><span data-ttu-id="e5c77-172">Chave de administração e gerenciamento de alterações para servidor de chat persistente</span><span class="sxs-lookup"><span data-stu-id="e5c77-172">Key Administration and Management Changes for Persistent Chat Server</span></span>

<span data-ttu-id="e5c77-173">O Lync Server 2013 facilitou a administração e o gerenciamento do servidor de chat persistente fornecendo:</span><span class="sxs-lookup"><span data-stu-id="e5c77-173">Lync Server 2013 has made it easier to administer and manage Persistent Chat Server by providing:</span></span>

  - <span data-ttu-id="e5c77-174">Administração e gerenciamento unificados.</span><span class="sxs-lookup"><span data-stu-id="e5c77-174">Unified administration and management.</span></span> <span data-ttu-id="e5c77-175">O Lync Server 2013 facilita o gerenciamento e a administração do servidor de chat persistente usando ferramentas que já são familiares aos administradores do Lync.</span><span class="sxs-lookup"><span data-stu-id="e5c77-175">Lync Server 2013 makes it easier to manage and administer Persistent Chat Server by using tools that are already familiar to Lync administrators.</span></span> <span data-ttu-id="e5c77-176">Servidor de chat persistente inclui uma experiência de interface de usuário administrativa que é integrada ao painel de controle do Lync Server, que aborda problemas de desempenho com as versões anteriores da interface de usuário do servidor de chat de grupo.</span><span class="sxs-lookup"><span data-stu-id="e5c77-176">Persistent Chat Server includes an administrative user interface experience that is integrated with the Lync Server Control Panel, which addresses performance issues with the previous versions of the Group Chat Server user interface.</span></span> <span data-ttu-id="e5c77-177">Além disso, o servidor de chat persistente inclui uma coleção de cmdlets do Windows PowerShell para administrar e gerenciar categorias de servidor de chat persistente, salas de servidor de chat persistente (incluindo a exclusão de salas e limpeza de conteúdo obsoleto) e suplementos.</span><span class="sxs-lookup"><span data-stu-id="e5c77-177">Also, Persistent Chat Server includes a collection of Windows PowerShell cmdlets to administer and manage Persistent Chat Server categories, Persistent Chat Server rooms (including deleting rooms and purging obsolete content), and add-ins.</span></span>

  - <span data-ttu-id="e5c77-178">Modelo de administração simplificado.</span><span class="sxs-lookup"><span data-stu-id="e5c77-178">Simplified administration model.</span></span> <span data-ttu-id="e5c77-179">O Lync Server 2013 alterou e simplificou o modelo de servidor de chat persistente atendendo aos seguintes requisitos principais do cliente:</span><span class="sxs-lookup"><span data-stu-id="e5c77-179">Lync Server 2013 has changed and simplified the Persistent Chat Server model by addressing the following key customer requirements:</span></span>
    
      - <span data-ttu-id="e5c77-180">Remova as hierarquias complexas aninhadas de escopos e categorias.</span><span class="sxs-lookup"><span data-stu-id="e5c77-180">Remove the complex nested hierarchies of scopes and categories.</span></span>
    
      - <span data-ttu-id="e5c77-181">Suporte para definir listas de negações, bem como listas permitidas (escopos) para os clientes atuais do MindAlign que estão planejando migrar para o servidor de chat persistente.</span><span class="sxs-lookup"><span data-stu-id="e5c77-181">Support to define deny lists as well as allowed lists (scopes) for current MindAlign customers who are planning to migrate to Persistent Chat Server.</span></span>

</div>

<div>

## <a name="whats-different-about-user-roles-from-previous-group-chat-server-versions"></a><span data-ttu-id="e5c77-182">O que há de diferente nas funções de usuário das versões anteriores do servidor de chat de grupo?</span><span class="sxs-lookup"><span data-stu-id="e5c77-182">What’s Different about User Roles from Previous Group Chat Server Versions?</span></span>

<span data-ttu-id="e5c77-183">Lync Server 2010, o chat de grupo tinha uma função de administrador de usuários, uma função de administrador de salas de chat e uma função de administrador do Lync Server que pudesse gerenciar suplementos. o servidor de chat persistente simplesmente fornece uma função de administrador de chat persistente (que é semelhante a outros Lync Funções RBAC (controle de acesso baseado em função) do servidor.</span><span class="sxs-lookup"><span data-stu-id="e5c77-183">Lync Server 2010, Group Chat had a user administrator role, a chat room administrator role and a Lync Server administrator role that could manage add-ins. Persistent Chat Server simply provides a Persistent Chat Administrator role (which is similar to other Lync Server role-based access control (RBAC) roles).</span></span> <span data-ttu-id="e5c77-184">Qualquer pessoa que seja membro dessa função RBAC pode gerenciar salas de chat, suplementos e categorias (e, portanto, obter acesso de usuário para essas categorias) e configuração do pool do servidor de chat persistente.</span><span class="sxs-lookup"><span data-stu-id="e5c77-184">Anyone who is a member of this RBAC role can manage chat rooms, add-ins, and categories (and therefore gain user access for these categories), and configuration of the Persistent Chat Server pool.</span></span>

</div>

<div>

## <a name="whats-different-about-chat-room-categories-from-previous-group-chat-server-versions"></a><span data-ttu-id="e5c77-185">O que há de diferente nas categorias de sala de chat de versões anteriores do servidor de chat de grupo?</span><span class="sxs-lookup"><span data-stu-id="e5c77-185">What’s Different about Chat Room Categories from Previous Group Chat Server Versions?</span></span>

<span data-ttu-id="e5c77-186">As categorias de sala de chat não podem mais ser aninhadas e a categoria raiz não pode mais ser modificada.</span><span class="sxs-lookup"><span data-stu-id="e5c77-186">Chat room categories can no longer be nested, and the root category can no longer be modified.</span></span> <span data-ttu-id="e5c77-187">Membros permitidos/DeniedMembers abrangem o que um escopo costumava ser em versões do servidor de chat de grupo herdado (exceto pelo fato de não suportar a especificação de uma lista negada).</span><span class="sxs-lookup"><span data-stu-id="e5c77-187">AllowedMembers/DeniedMembers comprise what a scope used to be in legacy Group Chat Server versions (except that it didn’t support specifying a Denied list).</span></span> <span data-ttu-id="e5c77-188">Escopos não podem mais ser substituídos, porque não há categorias aninhadas.</span><span class="sxs-lookup"><span data-stu-id="e5c77-188">Scopes can no longer be overridden, because there are no nested categories.</span></span> <span data-ttu-id="e5c77-189">Um administrador de chat persistente no Lync Server 2013 pode criar e gerenciar categorias de sala de chat.</span><span class="sxs-lookup"><span data-stu-id="e5c77-189">A Persistent Chat Administrator in Lync Server 2013 can create and manage chat room categories.</span></span> <span data-ttu-id="e5c77-190">Como parte da criação e gerenciamento de categorias de sala de chat, um administrador de chat persistente pode configurar entidades (grupos/usuários/usuários do Active Directory) que têm acesso a membros/criadores de salas de chat de uma determinada categoria.</span><span class="sxs-lookup"><span data-stu-id="e5c77-190">As part of creating and managing chat room categories, a Persistent Chat Administrator can configure principals (Active Directory groups/containers/users) that have access to be members/creators of chat rooms of a particular category.</span></span> <span data-ttu-id="e5c77-191">Um administrador de chat persistente também pode adicionar DeniedMembers a uma categoria, e essas se tornam exclusões explícitas para a lista de permissões.</span><span class="sxs-lookup"><span data-stu-id="e5c77-191">A Persistent Chat Administrator can also add DeniedMembers to a category, and these become explicit exclusions to the allowed list.</span></span> <span data-ttu-id="e5c77-192">DeniedMembers substitui o que está em AllowedMembers.</span><span class="sxs-lookup"><span data-stu-id="e5c77-192">DeniedMembers override what’s in AllowedMembers.</span></span>

</div>

<div>

## <a name="whats-different-about-chat-room-properties-from-previous-group-chat-server-versions"></a><span data-ttu-id="e5c77-193">O que há de diferente nas propriedades de sala de chat de versões anteriores do servidor de chat de grupo?</span><span class="sxs-lookup"><span data-stu-id="e5c77-193">What’s Different about Chat Room Properties from Previous Group Chat Server Versions?</span></span>

<span data-ttu-id="e5c77-194">Há um novo conceito de salas de chat abertas no Lync Server 2013, servidor de chat persistente.</span><span class="sxs-lookup"><span data-stu-id="e5c77-194">A new concept of open chat rooms exists in Lync Server 2013, Persistent Chat Server.</span></span> <span data-ttu-id="e5c77-195">Todos os membros permitidos podem participar da sala de chat, sem associação exclusiva.</span><span class="sxs-lookup"><span data-stu-id="e5c77-195">All allowed members can join the chat room, without exclusive membership.</span></span>

<span data-ttu-id="e5c77-196">As seguintes propriedades de sala de chat que foram incluídas nas versões anteriores do servidor de chat persistente foram eliminadas:</span><span class="sxs-lookup"><span data-stu-id="e5c77-196">The following chat room properties that were included in previous versions of Persistent Chat Server have been eliminated:</span></span>

  - <span data-ttu-id="e5c77-197">Tópico: uma sala agora tem apenas uma descrição.</span><span class="sxs-lookup"><span data-stu-id="e5c77-197">Topic: A Room now only has a Description.</span></span>

  - <span data-ttu-id="e5c77-198">Criar uma nova lista de membros: no servidor de chat persistente, todas as salas de bate-papo começam com associação vazia (e podem maximizar para uma associação que equivale aos membros permitidos).</span><span class="sxs-lookup"><span data-stu-id="e5c77-198">Create New Member list: In Persistent Chat Server, all chat rooms start with empty membership (and can maximize to a membership equaling the Allowed Members).</span></span>

  - <span data-ttu-id="e5c77-199">Upload de arquivo: usado para ser uma configuração por sala de chat para controlar se o carregamento de arquivos/downloads foram permitidos.</span><span class="sxs-lookup"><span data-stu-id="e5c77-199">File Upload: Used to be a setting per chat room to control whether file upload/downloads were allowed.</span></span> <span data-ttu-id="e5c77-200">Agora, ele é definido somente o nível de categoria e se aplica a todas as salas nessa categoria.</span><span class="sxs-lookup"><span data-stu-id="e5c77-200">This is now set only the category level and applies to all rooms in that category.</span></span>

  - <span data-ttu-id="e5c77-201">Histórico de chat: usado para ser uma configuração por sala de chat para controlar se o histórico de chat foi habilitado, mas agora está definido apenas no nível de categoria e se aplica a todas as salas nessa categoria.</span><span class="sxs-lookup"><span data-stu-id="e5c77-201">Chat History: Used to be a setting per chat room to control if Chat History was enabled, but is now set only at the category level and applies to all rooms in that category.</span></span>

  - <span data-ttu-id="e5c77-202">Convites: uma sala sempre herda a configuração de convites para a categoria; ou pode ser desativado na sala.</span><span class="sxs-lookup"><span data-stu-id="e5c77-202">Invites: A room always inherits the Invites setting for the category; or it can be turned off on the room.</span></span> <span data-ttu-id="e5c77-203">Uma sala não poderá ativar convites se a categoria tiver sido previamente definida para convites.</span><span class="sxs-lookup"><span data-stu-id="e5c77-203">A room cannot turn on Invites if the category was previously set to Invites off.</span></span>

</div>

<div>

## <a name="whats-different-about-policies-from-previous-group-chat-server-versions"></a><span data-ttu-id="e5c77-204">O que há de diferente em relação às políticas de versões anteriores do servidor de chat de grupo?</span><span class="sxs-lookup"><span data-stu-id="e5c77-204">What’s Different about Policies from Previous Group Chat Server Versions?</span></span>

<span data-ttu-id="e5c77-205">O servidor de chat persistente tem uma nova política do Lync habilitada com chat persistente, por usuário/pool/site/definições globais.</span><span class="sxs-lookup"><span data-stu-id="e5c77-205">Persistent Chat Server has a new Lync policy enabled with Persistent Chat, per user/pool/site/global settings.</span></span> <span data-ttu-id="e5c77-206">No cliente do Lync 2013, o ambiente de chat persistente está disponível somente para usuários habilitados pela política para chat persistente (seja diretamente ou por meio da configuração pool/site/global).</span><span class="sxs-lookup"><span data-stu-id="e5c77-206">In the Lync 2013 client, the Persistent Chat environment is available only for users who are enabled by policy for Persistent Chat (either directly or through the pool/site/global setting).</span></span>

<span data-ttu-id="e5c77-207">Versões anteriores do servidor de chat de grupo não tinham nenhuma política integrada às políticas do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="e5c77-207">Previous versions of Group Chat Server did not have any policies integrated into the Lync Server policies.</span></span> <span data-ttu-id="e5c77-208">Em uma base por usuário e por categoria/sala, usando o recurso **pode carregar arquivos** por usuário, você poderia tornar o usuário um administrador de usuário, um administrador de salas de chat ou configurar a capacidade do usuário de carregar arquivos.</span><span class="sxs-lookup"><span data-stu-id="e5c77-208">On a per user and per category/room basis, by using the **Can Upload Files** per user feature, you could make the user a User administrator, a chat room administrator, or configure the user’s ability to upload files.</span></span> <span data-ttu-id="e5c77-209">O recurso de **carregamento de arquivo** do servidor de chat persistente é apenas por categoria.</span><span class="sxs-lookup"><span data-stu-id="e5c77-209">The Persistent Chat Server **File Upload** feature is just per category.</span></span>

</div>

<div>

## <a name="logging"></a><span data-ttu-id="e5c77-210">Registro em log</span><span class="sxs-lookup"><span data-stu-id="e5c77-210">Logging</span></span>

<span data-ttu-id="e5c77-211">O registro em log para o servidor de chat persistente e o System Center Operations Manager é integrado no log de rastreamento do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="e5c77-211">Logging for Persistent Chat Server and System Center Operations Manager is integrated into the Lync Server 2013 trace logging.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="e5c77-212">Confira também</span><span class="sxs-lookup"><span data-stu-id="e5c77-212">See Also</span></span>


[<span data-ttu-id="e5c77-213">Planejando o servidor de chat persistente no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e5c77-213">Planning for Persistent Chat Server in Lync Server 2013</span></span>](lync-server-2013-planning-for-persistent-chat-server.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

