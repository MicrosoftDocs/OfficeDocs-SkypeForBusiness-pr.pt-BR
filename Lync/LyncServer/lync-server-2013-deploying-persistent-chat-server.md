---
title: 'Lync Server 2013: Implantando servidor de chat persistente'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deploying Persistent Chat Server
ms:assetid: e3b930fb-6855-47f0-b6b3-7dfae386540d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205357(v=OCS.15)
ms:contentKeyID: 48185717
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 83a23190033bca9047a3d1a6d70b914d02017db8
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42153973"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="deploying-persistent-chat-server-in-lync-server-2013"></a><span data-ttu-id="368f5-102">Implantando o servidor de chat persistente no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="368f5-102">Deploying Persistent Chat Server in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="368f5-103">_**Última modificação do tópico:** 2014-03-31_</span><span class="sxs-lookup"><span data-stu-id="368f5-103">_**Topic Last Modified:** 2014-03-31_</span></span>

<span data-ttu-id="368f5-104">Lync Server 2013, servidor de chat persistente é parte da infraestrutura 2013 do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="368f5-104">Lync Server 2013, Persistent Chat Server is part of the Lync Server 2013 infrastructure.</span></span>

<span data-ttu-id="368f5-105">A implantação do servidor de chat persistente requer que você:</span><span class="sxs-lookup"><span data-stu-id="368f5-105">Deploying Persistent Chat Server requires that you:</span></span>

  - <span data-ttu-id="368f5-106">Use o construtor de topologias para definir ou importar e, em seguida, publicar sua topologia e os componentes que você deseja implantar.</span><span class="sxs-lookup"><span data-stu-id="368f5-106">Use Topology Builder to define, or import, and subsequently publish your topology and the components that you want to deploy.</span></span>

  - <span data-ttu-id="368f5-107">Prepare seu ambiente para a implantação de componentes do servidor de chat persistente.</span><span class="sxs-lookup"><span data-stu-id="368f5-107">Prepare your environment for deploying Persistent Chat Server components.</span></span>

  - <span data-ttu-id="368f5-108">Instale e configure os componentes do servidor de chat persistente para sua implantação.</span><span class="sxs-lookup"><span data-stu-id="368f5-108">Install and configure Persistent Chat Server components for your deployment.</span></span>

<span data-ttu-id="368f5-109">O servidor de chat persistente está disponível com o Lync Server 2013 Enterprise Edition como um pool separado (não colocado com os servidores de front-end Enterprise Edition).</span><span class="sxs-lookup"><span data-stu-id="368f5-109">Persistent Chat Server is available with Lync Server 2013 Enterprise Edition as a separate pool (not collocated with the Enterprise Edition Front End Servers).</span></span> <span data-ttu-id="368f5-110">O servidor de chat persistente requer um servidor back-end do SQL Server em seu pool Enterprise Edition para armazenar o conteúdo da sala de chat e outros metadados relevantes.</span><span class="sxs-lookup"><span data-stu-id="368f5-110">Persistent Chat Server requires a SQL Server Back End Server in your Enterprise Edition pool to store the chat room content and other relevant metadata.</span></span> <span data-ttu-id="368f5-111">Recomendamos que você instale o **PersistentChatStore** em um servidor back-end do SQL Server dedicado, embora o servidor de back-end do Lync Server 2013 e o **PersistentChatStore** na mesma instância do SQL Server sejam posicionados.</span><span class="sxs-lookup"><span data-stu-id="368f5-111">We recommend that you install the **PersistentChatStore** on a dedicated SQL Server Back End Server, although collocating Lync Server 2013 Back End Server and **PersistentChatStore** on the same SQL Server instance is supported.</span></span>

<span data-ttu-id="368f5-112">O servidor de chat persistente também pode ser implantado com o Lync Server 2013 Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="368f5-112">Persistent Chat Server can also be deployed with Lync Server 2013 Standard Edition.</span></span> <span data-ttu-id="368f5-113">Nesse caso, o servidor front-end do **PersistentChatService** é colocado no computador Standard Edition, e o servidor back-end do **PersistentChatStore** pode ser implantado na instância local do SQL Server Express.</span><span class="sxs-lookup"><span data-stu-id="368f5-113">In this case, the **PersistentChatService** Front End Server is collocated on the Standard Edition computer, and the **PersistentChatStore** Back End Server can be deployed on the local SQL Server Express instance.</span></span>

<span data-ttu-id="368f5-114">Para obter detalhes sobre as configurações de colocal com suporte, consulte [colocação de servidor suportado no Lync server 2013](lync-server-2013-supported-server-collocation.md).</span><span class="sxs-lookup"><span data-stu-id="368f5-114">For details about supported colocation configurations, see [Supported server collocation in Lync Server 2013](lync-server-2013-supported-server-collocation.md).</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="368f5-115">Não há suporte para alta disponibilidade para o servidor&nbsp;de chat persistente Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="368f5-115">We do not support high availability for Persistent Chat Server&nbsp;Standard Edition.</span></span> <span data-ttu-id="368f5-116">Desempenho e escala será limitado.</span><span class="sxs-lookup"><span data-stu-id="368f5-116">Performance and scale will be limited.</span></span> <span data-ttu-id="368f5-117">Além disso, oferecemos suporte somente para o novo&nbsp;servidor do servidor de chat persistente.</span><span class="sxs-lookup"><span data-stu-id="368f5-117">Furthermore, we support only new Persistent Chat Server&nbsp;Standard Edition server.</span></span> <span data-ttu-id="368f5-118">Não há suporte para atualizar o Lync Server 2010, o servidor de chat de grupo para&nbsp;um servidor do&nbsp;Lync Server 2013 persistent chat Server Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="368f5-118">We do not support upgrading Lync Server 2010, Group Chat Server to a Lync Server 2013&nbsp;Persistent Chat Server&nbsp;Standard Edition.</span></span>



</div>

<span data-ttu-id="368f5-119">Se sua organização exigir o suporte de conformidade, você poderá instalar o serviço de conformidade do servidor de chat persistente no servidor front-end do servidor de chat persistente.</span><span class="sxs-lookup"><span data-stu-id="368f5-119">If your organization requires compliance support, you can install the Persistent Chat Server Compliance service on the Persistent Chat Server Front End Server.</span></span> <span data-ttu-id="368f5-120">Um banco de dados separado é exigido para conformidade.</span><span class="sxs-lookup"><span data-stu-id="368f5-120">A separate database is required for compliance.</span></span>

<span data-ttu-id="368f5-121">No mínimo, cada topologia requer um servidor com o Lync Server 2013 instalado e um servidor com o software de banco de dados do SQL Server instalado.</span><span class="sxs-lookup"><span data-stu-id="368f5-121">At a minimum, each topology requires a server with Lync Server 2013 installed and a server with SQL Server database software installed.</span></span>

<span data-ttu-id="368f5-122">Use o construtor de topologias para adicionar o servidor de chat persistente às implantações do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="368f5-122">Use Topology Builder to add Persistent Chat Server to your Lync Server 2013 deployments.</span></span> <span data-ttu-id="368f5-123">Você pode optar por adicionar um ou mais pools de servidores de chat persistentes usando o construtor de topologias.</span><span class="sxs-lookup"><span data-stu-id="368f5-123">You can choose to add one or more Persistent Chat Server pools using Topology Builder.</span></span> <span data-ttu-id="368f5-124">Siga as mesmas instruções de implantação para implantar vários pools de servidores de chat persistentes, como faria para qualquer pool.</span><span class="sxs-lookup"><span data-stu-id="368f5-124">Follow the same deployment instructions for deploying multiple Persistent Chat Server pools as you would for any pool.</span></span> <span data-ttu-id="368f5-125">Para obter detalhes, consulte [Deploying Lync Server 2013](lync-server-2013-deploying-lync-server.md) na documentação de implantação.</span><span class="sxs-lookup"><span data-stu-id="368f5-125">For details, see [Deploying Lync Server 2013](lync-server-2013-deploying-lync-server.md) in the Deployment documentation.</span></span>

<span data-ttu-id="368f5-126">Para obter detalhes sobre topologias disponíveis e os requisitos técnicos e de software para instalar o servidor de chat persistente, consulte [Planning for persistent chat Server in Lync server 2013](lync-server-2013-planning-for-persistent-chat-server.md) na documentação de planejamento, [como o servidor de chat persistente funciona no Lync Server 2013](lync-server-2013-how-persistent-chat-server-works.md) na documentação de planejamento, documentação de implantação ou operações e [hardware com suporte para o Lync Server 2013](lync-server-2013-supported-hardware.md) na documentação de suporte.</span><span class="sxs-lookup"><span data-stu-id="368f5-126">For details about available topologies and the technical and software requirements for installing Persistent Chat Server, see [Planning for Persistent Chat Server in Lync Server 2013](lync-server-2013-planning-for-persistent-chat-server.md) in the Planning documentation, [How Persistent Chat Server works in Lync Server 2013](lync-server-2013-how-persistent-chat-server-works.md) in the Planning documentation, Deployment documentation, or Operations documentation, and [Supported hardware for Lync Server 2013](lync-server-2013-supported-hardware.md) in the Supportability documentation.</span></span>

<span data-ttu-id="368f5-127">Para obter detalhes sobre a aquisição de certificados, criação do banco de dados do SQL Server e criação de repositórios de arquivos, consulte [Deploying Lync Server 2013](lync-server-2013-deploying-lync-server.md) na documentação de implantação.</span><span class="sxs-lookup"><span data-stu-id="368f5-127">For details about acquiring certificates, creating the SQL Server database, and creating file stores, see [Deploying Lync Server 2013](lync-server-2013-deploying-lync-server.md) in the Deployment documentation.</span></span>

<span data-ttu-id="368f5-128">Um servidor front-end único de servidor de chat persistente pode oferecer suporte A 20.000 usuários ativos.</span><span class="sxs-lookup"><span data-stu-id="368f5-128">A single Persistent Chat Server Front End Server can support 20,000 active users.</span></span> <span data-ttu-id="368f5-129">Você pode ter um pool de servidores de chat persistente com até quatro servidores front-end ativos suportando um total de 80.000 usuários simultâneos.</span><span class="sxs-lookup"><span data-stu-id="368f5-129">You can have a Persistent Chat Server pool with up to 4 active Front End Servers supporting a total of 80,000 concurrent users.</span></span>

<span data-ttu-id="368f5-130">O servidor de chat persistente também é compatível com um servidor virtual.</span><span class="sxs-lookup"><span data-stu-id="368f5-130">Persistent Chat Server is also supported on a virtual server.</span></span> <span data-ttu-id="368f5-131">O servidor virtual pode suportar até 20.000 usuários simultâneos se ele corresponder às especificações do servidor físico.</span><span class="sxs-lookup"><span data-stu-id="368f5-131">The virtual server can support up to 20,000 concurrent users if it matches the specifications of the physical server.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="368f5-132">O servidor de chat persistente deve ser instalado em um sistema de arquivos NTFS para ajudar a aplicar a segurança do sistema de arquivos.</span><span class="sxs-lookup"><span data-stu-id="368f5-132">Persistent Chat Server must be installed on an NTFS file system to help enforce file system security.</span></span> <span data-ttu-id="368f5-133">FAT32 não é um sistema de arquivos com suporte para o servidor de chat persistente.</span><span class="sxs-lookup"><span data-stu-id="368f5-133">FAT32 is not a supported file system for Persistent Chat Server.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="368f5-134">Nesta seção</span><span class="sxs-lookup"><span data-stu-id="368f5-134">In This Section</span></span>

  - [<span data-ttu-id="368f5-135">Como funciona o servidor de chat persistente no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="368f5-135">How Persistent Chat Server works in Lync Server 2013</span></span>](lync-server-2013-how-persistent-chat-server-works.md)

  - [<span data-ttu-id="368f5-136">Lista de verificação de implantação para o servidor de chat persistente no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="368f5-136">Deployment checklist for Persistent Chat Server in Lync Server 2013</span></span>](lync-server-2013-deployment-checklist-for-persistent-chat-server.md)

  - [<span data-ttu-id="368f5-137">Requisitos técnicos para o servidor de chat persistente no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="368f5-137">Technical requirements for Persistent Chat Server in Lync Server 2013</span></span>](lync-server-2013-technical-requirements-for-persistent-chat-server.md)

  - [<span data-ttu-id="368f5-138">Configurando sistemas e infraestrutura para o servidor de chat persistente no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="368f5-138">Setting up systems and infrastructure for Persistent Chat Server in Lync Server 2013</span></span>](lync-server-2013-setting-up-systems-and-infrastructure-for-persistent-chat-server.md)

  - [<span data-ttu-id="368f5-139">Adicionando servidor de chat persistente à sua implantação no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="368f5-139">Adding Persistent Chat Server to your deployment in Lync Server 2013</span></span>](lync-server-2013-adding-persistent-chat-server-to-your-deployment.md)

  - [<span data-ttu-id="368f5-140">Instalando o servidor de chat persistente no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="368f5-140">Installing Persistent Chat Server in Lync Server 2013</span></span>](lync-server-2013-installing-persistent-chat-server.md)

  - [<span data-ttu-id="368f5-141">Adicionando um administrador de chat persistente no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="368f5-141">Adding a Persistent Chat administrator in Lync Server 2013</span></span>](lync-server-2013-adding-a-persistent-chat-administrator.md)

  - [<span data-ttu-id="368f5-142">Configurando o servidor de chat persistente no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="368f5-142">Configuring Persistent Chat Server in Lync Server 2013</span></span>](lync-server-2013-configuring-persistent-chat-server.md)

  - [<span data-ttu-id="368f5-143">Configurando o servidor de chat persistente usando cmdlets do Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="368f5-143">Configuring Persistent Chat Server by using Windows PowerShell cmdlets</span></span>](configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md)

  - [<span data-ttu-id="368f5-144">Solucionando problemas de configuração do servidor de chat persistente usando cmdlets do Windows PowerShell no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="368f5-144">Troubleshooting Persistent Chat Server configuration using Windows PowerShell cmdlets in Lync Server 2013</span></span>](lync-server-2013-troubleshooting-persistent-chat-server-configuration-using-windows-powershell-cmdlets.md)

  - [<span data-ttu-id="368f5-145">Configurando o servidor de chat persistente para alta disponibilidade e recuperação de desastre no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="368f5-145">Configuring Persistent Chat Server for high availability and disaster recovery in Lync Server 2013</span></span>](lync-server-2013-configuring-persistent-chat-server-for-high-availability-and-disaster-recovery.md)

  - [<span data-ttu-id="368f5-146">Failover e failback do servidor de chat persistente no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="368f5-146">Failing over and failing back Persistent Chat Server in Lync Server 2013</span></span>](lync-server-2013-failing-over-and-failing-back-persistent-chat-server.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

