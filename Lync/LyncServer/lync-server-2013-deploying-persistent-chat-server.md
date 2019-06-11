---
title: 'Lync Server 2013: Implantando Servidor de Chat Persistente'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Deploying Persistent Chat Server
ms:assetid: e3b930fb-6855-47f0-b6b3-7dfae386540d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205357(v=OCS.15)
ms:contentKeyID: 48185717
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6a730057735f187dc5e5080d532515a4eb9db110
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34829535"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deploying-persistent-chat-server-in-lync-server-2013"></a><span data-ttu-id="b55e9-102">Implantando Servidor de Chat Persistente no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b55e9-102">Deploying Persistent Chat Server in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b55e9-103">_**Tópico da última modificação:** 2014-03-31_</span><span class="sxs-lookup"><span data-stu-id="b55e9-103">_**Topic Last Modified:** 2014-03-31_</span></span>

<span data-ttu-id="b55e9-104">Lync Server 2013, servidor de chat persistente faz parte da infraestrutura do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="b55e9-104">Lync Server 2013, Persistent Chat Server is part of the Lync Server 2013 infrastructure.</span></span>

<span data-ttu-id="b55e9-105">A implantação do servidor de chat persistente exige que você:</span><span class="sxs-lookup"><span data-stu-id="b55e9-105">Deploying Persistent Chat Server requires that you:</span></span>

  - <span data-ttu-id="b55e9-106">Use o construtor de topologias para definir ou importar e publicar subseqüentemente a topologia e os componentes que você deseja implantar.</span><span class="sxs-lookup"><span data-stu-id="b55e9-106">Use Topology Builder to define, or import, and subsequently publish your topology and the components that you want to deploy.</span></span>

  - <span data-ttu-id="b55e9-107">Preparar seu ambiente para a implantação de componentes persistentes do servidor de chat.</span><span class="sxs-lookup"><span data-stu-id="b55e9-107">Prepare your environment for deploying Persistent Chat Server components.</span></span>

  - <span data-ttu-id="b55e9-108">Instalar e configurar componentes do servidor de chat persistente para a sua implantação.</span><span class="sxs-lookup"><span data-stu-id="b55e9-108">Install and configure Persistent Chat Server components for your deployment.</span></span>

<span data-ttu-id="b55e9-109">O servidor de chat persistente está disponível no Lync Server 2013 Enterprise Edition como um pool separado (não vem com os servidores front-end da Enterprise Edition).</span><span class="sxs-lookup"><span data-stu-id="b55e9-109">Persistent Chat Server is available with Lync Server 2013 Enterprise Edition as a separate pool (not collocated with the Enterprise Edition Front End Servers).</span></span> <span data-ttu-id="b55e9-110">O servidor de chat persistente exige um servidor back-end do SQL Server no pool da edição Enterprise para armazenar o conteúdo da sala de chat e outros metadados relevantes.</span><span class="sxs-lookup"><span data-stu-id="b55e9-110">Persistent Chat Server requires a SQL Server Back End Server in your Enterprise Edition pool to store the chat room content and other relevant metadata.</span></span> <span data-ttu-id="b55e9-111">Recomendamos que você instale o **PersistentChatStore** em um servidor back-end do SQL Server dedicado, embora a colocação do servidor back-end do Lync Server 2013 e do **PersistentChatStore** na mesma instância do SQL Server seja compatível.</span><span class="sxs-lookup"><span data-stu-id="b55e9-111">We recommend that you install the **PersistentChatStore** on a dedicated SQL Server Back End Server, although collocating Lync Server 2013 Back End Server and **PersistentChatStore** on the same SQL Server instance is supported.</span></span>

<span data-ttu-id="b55e9-112">O servidor de chat persistente também pode ser implantado com o Lync Server 2013 Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="b55e9-112">Persistent Chat Server can also be deployed with Lync Server 2013 Standard Edition.</span></span> <span data-ttu-id="b55e9-113">Nesse caso, o servidor front-end **PersistentChatService** é posicionado no computador com a Standard Edition, e o servidor back-end do **PersistentChatStore** pode ser implantado na instância local do SQL Server Express.</span><span class="sxs-lookup"><span data-stu-id="b55e9-113">In this case, the **PersistentChatService** Front End Server is collocated on the Standard Edition computer, and the **PersistentChatStore** Back End Server can be deployed on the local SQL Server Express instance.</span></span>

<span data-ttu-id="b55e9-114">Para obter detalhes sobre as configurações de colocalização com suporte, consulte [colocação de servidor com suporte no Lync server 2013](lync-server-2013-supported-server-collocation.md).</span><span class="sxs-lookup"><span data-stu-id="b55e9-114">For details about supported colocation configurations, see [Supported server collocation in Lync Server 2013](lync-server-2013-supported-server-collocation.md).</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="b55e9-115">Não oferecemos suporte à alta disponibilidade para o servidor&nbsp;de chat persistente Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="b55e9-115">We do not support high availability for Persistent Chat Server&nbsp;Standard Edition.</span></span> <span data-ttu-id="b55e9-116">O desempenho e a escala serão limitados.</span><span class="sxs-lookup"><span data-stu-id="b55e9-116">Performance and scale will be limited.</span></span> <span data-ttu-id="b55e9-117">Além disso, oferecemos suporte somente para o novo&nbsp;servidor persistente do servidor de chat persistente.</span><span class="sxs-lookup"><span data-stu-id="b55e9-117">Furthermore, we support only new Persistent Chat Server&nbsp;Standard Edition server.</span></span> <span data-ttu-id="b55e9-118">Não oferecemos suporte à atualização do Lync Server 2010, do servidor de chat em grupo para&nbsp;um servidor de&nbsp;chat persistente do Lync Server 2013 Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="b55e9-118">We do not support upgrading Lync Server 2010, Group Chat Server to a Lync Server 2013&nbsp;Persistent Chat Server&nbsp;Standard Edition.</span></span>



</div>

<span data-ttu-id="b55e9-119">Se a sua organização requer suporte à conformidade, você pode instalar o serviço de conformidade do servidor de chat persistente no servidor front-end do servidor de chat persistente.</span><span class="sxs-lookup"><span data-stu-id="b55e9-119">If your organization requires compliance support, you can install the Persistent Chat Server Compliance service on the Persistent Chat Server Front End Server.</span></span> <span data-ttu-id="b55e9-120">Um banco de dados separado é necessário para conformidade.</span><span class="sxs-lookup"><span data-stu-id="b55e9-120">A separate database is required for compliance.</span></span>

<span data-ttu-id="b55e9-121">No mínimo, cada topologia requer um servidor com o Lync Server 2013 instalado e um servidor com software de banco de dados do SQL Server instalado.</span><span class="sxs-lookup"><span data-stu-id="b55e9-121">At a minimum, each topology requires a server with Lync Server 2013 installed and a server with SQL Server database software installed.</span></span>

<span data-ttu-id="b55e9-122">Use o construtor de topologias para adicionar um servidor de chat persistente a suas implantações do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="b55e9-122">Use Topology Builder to add Persistent Chat Server to your Lync Server 2013 deployments.</span></span> <span data-ttu-id="b55e9-123">Você pode optar por adicionar um ou mais pools de servidores de chat persistentes usando o construtor de topologias.</span><span class="sxs-lookup"><span data-stu-id="b55e9-123">You can choose to add one or more Persistent Chat Server pools using Topology Builder.</span></span> <span data-ttu-id="b55e9-124">Siga as mesmas instruções de implantação para implantar vários pools persistentes do servidor de chat como faria com qualquer pool.</span><span class="sxs-lookup"><span data-stu-id="b55e9-124">Follow the same deployment instructions for deploying multiple Persistent Chat Server pools as you would for any pool.</span></span> <span data-ttu-id="b55e9-125">Para obter detalhes, consulte Implantando o [Lync Server 2013](lync-server-2013-deploying-lync-server.md) na documentação de implantação.</span><span class="sxs-lookup"><span data-stu-id="b55e9-125">For details, see [Deploying Lync Server 2013](lync-server-2013-deploying-lync-server.md) in the Deployment documentation.</span></span>

<span data-ttu-id="b55e9-126">Para obter detalhes sobre topologias disponíveis e os requisitos técnicos e de software para a instalação do servidor de chat persistente, consulte [planejando o servidor de chat persistente no Lync Server 2013](lync-server-2013-planning-for-persistent-chat-server.md) na documentação de planejamento, [como funciona o servidor de chat persistente no Lync Server 2013](lync-server-2013-how-persistent-chat-server-works.md) na documentação de planejamento, documentação de implantação ou documentação de operações e [hardware compatível com o Lync Server 2013](lync-server-2013-supported-hardware.md) na documentação de suporte.</span><span class="sxs-lookup"><span data-stu-id="b55e9-126">For details about available topologies and the technical and software requirements for installing Persistent Chat Server, see [Planning for Persistent Chat Server in Lync Server 2013](lync-server-2013-planning-for-persistent-chat-server.md) in the Planning documentation, [How Persistent Chat Server works in Lync Server 2013](lync-server-2013-how-persistent-chat-server-works.md) in the Planning documentation, Deployment documentation, or Operations documentation, and [Supported hardware for Lync Server 2013](lync-server-2013-supported-hardware.md) in the Supportability documentation.</span></span>

<span data-ttu-id="b55e9-127">Para obter detalhes sobre como adquirir certificados, criar o banco de dados do SQL Server e criar armazenamentos de arquivos, consulte Implantando o [Lync Server 2013](lync-server-2013-deploying-lync-server.md) na documentação de implantação.</span><span class="sxs-lookup"><span data-stu-id="b55e9-127">For details about acquiring certificates, creating the SQL Server database, and creating file stores, see [Deploying Lync Server 2013](lync-server-2013-deploying-lync-server.md) in the Deployment documentation.</span></span>

<span data-ttu-id="b55e9-128">Um servidor front-end único de servidor de chat persistente pode oferecer suporte a usuários ativos do 20.000.</span><span class="sxs-lookup"><span data-stu-id="b55e9-128">A single Persistent Chat Server Front End Server can support 20,000 active users.</span></span> <span data-ttu-id="b55e9-129">Você pode ter um pool de servidores de chat persistente com até quatro servidores front-end ativos que dão suporte a um total de 80.000 usuários simultâneos.</span><span class="sxs-lookup"><span data-stu-id="b55e9-129">You can have a Persistent Chat Server pool with up to 4 active Front End Servers supporting a total of 80,000 concurrent users.</span></span>

<span data-ttu-id="b55e9-130">Também há suporte para o servidor de chat persistente em um servidor virtual.</span><span class="sxs-lookup"><span data-stu-id="b55e9-130">Persistent Chat Server is also supported on a virtual server.</span></span> <span data-ttu-id="b55e9-131">O servidor virtual pode oferecer suporte a até 20.000 usuários simultâneos se ele corresponder às especificações do servidor físico.</span><span class="sxs-lookup"><span data-stu-id="b55e9-131">The virtual server can support up to 20,000 concurrent users if it matches the specifications of the physical server.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="b55e9-132">O servidor de chat persistente deve ser instalado em um sistema de arquivos NTFS para ajudar a reforçar a segurança do sistema de arquivos.</span><span class="sxs-lookup"><span data-stu-id="b55e9-132">Persistent Chat Server must be installed on an NTFS file system to help enforce file system security.</span></span> <span data-ttu-id="b55e9-133">FAT32 não é um sistema de arquivos com suporte para o servidor de chat persistente.</span><span class="sxs-lookup"><span data-stu-id="b55e9-133">FAT32 is not a supported file system for Persistent Chat Server.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="b55e9-134">Nesta seção</span><span class="sxs-lookup"><span data-stu-id="b55e9-134">In This Section</span></span>

  - [<span data-ttu-id="b55e9-135">Como o servidor de chat persistente funciona no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b55e9-135">How Persistent Chat Server works in Lync Server 2013</span></span>](lync-server-2013-how-persistent-chat-server-works.md)

  - [<span data-ttu-id="b55e9-136">Lista de verificação de implantação para o Servidor de Chat Persistente no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b55e9-136">Deployment checklist for Persistent Chat Server in Lync Server 2013</span></span>](lync-server-2013-deployment-checklist-for-persistent-chat-server.md)

  - [<span data-ttu-id="b55e9-137">Requisitos técnicos para servidor de chat persistente no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b55e9-137">Technical requirements for Persistent Chat Server in Lync Server 2013</span></span>](lync-server-2013-technical-requirements-for-persistent-chat-server.md)

  - [<span data-ttu-id="b55e9-138">Configurar sistemas e infraestrutura para o Servidor de Chat Persistente no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b55e9-138">Setting up systems and infrastructure for Persistent Chat Server in Lync Server 2013</span></span>](lync-server-2013-setting-up-systems-and-infrastructure-for-persistent-chat-server.md)

  - [<span data-ttu-id="b55e9-139">Adicionando Servidor de Chat Persistente em sua implantação no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b55e9-139">Adding Persistent Chat Server to your deployment in Lync Server 2013</span></span>](lync-server-2013-adding-persistent-chat-server-to-your-deployment.md)

  - [<span data-ttu-id="b55e9-140">Instalando o Servidor de Chat Persistente no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b55e9-140">Installing Persistent Chat Server in Lync Server 2013</span></span>](lync-server-2013-installing-persistent-chat-server.md)

  - [<span data-ttu-id="b55e9-141">Adicionando um administrador de Chat Persistente no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b55e9-141">Adding a Persistent Chat administrator in Lync Server 2013</span></span>](lync-server-2013-adding-a-persistent-chat-administrator.md)

  - [<span data-ttu-id="b55e9-142">Configurando o Servidor de Chat Persistente no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b55e9-142">Configuring Persistent Chat Server in Lync Server 2013</span></span>](lync-server-2013-configuring-persistent-chat-server.md)

  - [<span data-ttu-id="b55e9-143">Configurando Servidor de Chat Persistente usando cmdlets do Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="b55e9-143">Configuring Persistent Chat Server by using Windows PowerShell cmdlets</span></span>](configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md)

  - [<span data-ttu-id="b55e9-144">Configuração de solução de problemas do Servidor de Chat Persistente usando cmdlets do Windows PowerShell no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b55e9-144">Troubleshooting Persistent Chat Server configuration using Windows PowerShell cmdlets in Lync Server 2013</span></span>](lync-server-2013-troubleshooting-persistent-chat-server-configuration-using-windows-powershell-cmdlets.md)

  - [<span data-ttu-id="b55e9-145">Configurando o Servidor de Chat Persistente para alta disponibilidade e recuperação de desastre no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b55e9-145">Configuring Persistent Chat Server for high availability and disaster recovery in Lync Server 2013</span></span>](lync-server-2013-configuring-persistent-chat-server-for-high-availability-and-disaster-recovery.md)

  - [<span data-ttu-id="b55e9-146">Failouver e failback do Servidor de Chat Persistente no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b55e9-146">Failing over and failing back Persistent Chat Server in Lync Server 2013</span></span>](lync-server-2013-failing-over-and-failing-back-persistent-chat-server.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

