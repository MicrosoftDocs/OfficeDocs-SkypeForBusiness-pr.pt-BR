---
title: 'Lync Server 2013: preparando a infraestrutura e os sistemas'
description: 'Lync Server 2013: preparando a infraestrutura e os sistemas.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Preparing the infrastructure and systems
ms:assetid: 1254ee38-0679-4714-b293-1050f107c158
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398205(v=OCS.15)
ms:contentKeyID: 48183458
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: bfabdda9d117af1534578c8543f9ce72808d5a53
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48579987"
---
# <a name="preparing-the-infrastructure-and-systems-for-lync-server-2013"></a><span data-ttu-id="31733-103">Preparando a infraestrutura e os sistemas para o Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="31733-103">Preparing the infrastructure and systems for Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="31733-104">_**Última modificação do tópico:** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="31733-104">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="31733-105">A implantação do Lync Server 2013 requer o uso do construtor de topologias para definir e publicar o design de topologia.</span><span class="sxs-lookup"><span data-stu-id="31733-105">Deployment of Lync Server 2013 requires the use of Topology Builder to define and publish the topology design.</span></span> <span data-ttu-id="31733-106">Para identificar os componentes necessários para sua topologia, use o construtor de topologias para criar e salvar um design de topologia.</span><span class="sxs-lookup"><span data-stu-id="31733-106">To identify the components required for your topology, you use Topology Builder to create and save a topology design.</span></span> <span data-ttu-id="31733-107">Antes de publicar sua topologia no construtor de topologias, faça o seguinte:</span><span class="sxs-lookup"><span data-stu-id="31733-107">Prior to publishing your topology in Topology Builder, you do the following:</span></span>

  - <span data-ttu-id="31733-108">Adquirir e instalar o hardware para cada componente no design de topologia que você criou e salvou usando o construtor de topologias, incluindo todos os computadores necessários (servidores que executam o Lync Server 2013, servidores de banco de dados, servidores executando serviços de informações da Internet (IIS) e servidores de proxy reverso, conforme apropriado), adaptadores de rede, balanceadores de carga de hardware</span><span class="sxs-lookup"><span data-stu-id="31733-108">Acquire and install the hardware for each component in the topology design that you created and saved by using Topology Builder, including all required computers (servers running Lync Server 2013, database servers, servers running Internet Information Services (IIS), and reverse proxy servers, as appropriate), network adapters, hardware load balancers, and storage devices (such as file servers).</span></span> <span data-ttu-id="31733-109">Para obter detalhes sobre como definir uma topologia que especifica os componentes necessários para sua implantação, consulte [definindo e configurando a topologia no Lync Server 2013](lync-server-2013-defining-and-configuring-the-topology.md).</span><span class="sxs-lookup"><span data-stu-id="31733-109">For details about how to define a topology that specifies the components needed for your deployment, see [Defining and configuring the topology in Lync Server 2013](lync-server-2013-defining-and-configuring-the-topology.md).</span></span> <span data-ttu-id="31733-110">Para obter detalhes sobre os requisitos de hardware para servidores, consulte [hardware suportado para o Lync Server 2013](lync-server-2013-supported-hardware.md) na documentação de suporte.</span><span class="sxs-lookup"><span data-stu-id="31733-110">For details about hardware requirements for servers, see [Supported hardware for Lync Server 2013](lync-server-2013-supported-hardware.md) in the Supportability documentation.</span></span>

  - <span data-ttu-id="31733-111">Certifique-se de que a infraestrutura de rede atende aos requisitos.</span><span class="sxs-lookup"><span data-stu-id="31733-111">Make sure that the networking infrastructure meets requirements.</span></span> <span data-ttu-id="31733-112">Para obter detalhes, consulte [Network Infrastructure Requirements for Lync Server 2013](lync-server-2013-network-infrastructure-requirements.md) na documentação de planejamento.</span><span class="sxs-lookup"><span data-stu-id="31733-112">For details, see [Network infrastructure requirements for Lync Server 2013](lync-server-2013-network-infrastructure-requirements.md) in the Planning documentation.</span></span>

  - <span data-ttu-id="31733-113">Configurar os serviços de domínio do Active Directory.</span><span class="sxs-lookup"><span data-stu-id="31733-113">Set up Active Directory Domain Services.</span></span> <span data-ttu-id="31733-114">Para publicar e habilitar a topologia, é necessário que os servidores internos sejam representados por contas de computador no AD DS.</span><span class="sxs-lookup"><span data-stu-id="31733-114">To publish and enable the topology, you need the internal servers to be represented by computer accounts in AD DS.</span></span> <span data-ttu-id="31733-115">Para isso, é preciso unir os computadores ao AD DS.</span><span class="sxs-lookup"><span data-stu-id="31733-115">This is accomplished by joining the computers to AD DS.</span></span> <span data-ttu-id="31733-116">Para obter detalhes sobre como preparar o AD DS, consulte [preparação de serviços de domínio do Active Directory para o Lync Server 2013](lync-server-2013-preparing-active-directory-domain-services.md).</span><span class="sxs-lookup"><span data-stu-id="31733-116">For details about preparing AD DS, see [Preparing Active Directory Domain Services for Lync Server 2013](lync-server-2013-preparing-active-directory-domain-services.md).</span></span>

  - <span data-ttu-id="31733-117">Crie um compartilhamento de arquivos.</span><span class="sxs-lookup"><span data-stu-id="31733-117">Create a file share.</span></span> <span data-ttu-id="31733-118">Servidores Standard Edition podem hospedar o compartilhamento de arquivos para o arquivo necessário, enquanto em uma implantação do Enterprise o compartilhamento de arquivos não pode ser hospedada no servidor de front end.</span><span class="sxs-lookup"><span data-stu-id="31733-118">Standard Edition servers can host the file share for the required file, while in an Enterprise deployment the file share cannot be hosted on the front end server.</span></span> <span data-ttu-id="31733-119">As permissões e associações de grupo necessárias para implantar e configurar a lista de controle de acesso (ACL) na pasta e o compartilhamento devem ser definidos corretamente para que o Construtor de Topologias seja concluído com sucesso.</span><span class="sxs-lookup"><span data-stu-id="31733-119">The permissions and group memberships required for deploying and setting the access control list (ACL) on the folder and the share must be set correctly for Topology Builder to complete successfully.</span></span> <span data-ttu-id="31733-120">Você deve verificar se a pessoa que está executando o construtor de topologia tem as seguintes permissões e associações de Grupo:</span><span class="sxs-lookup"><span data-stu-id="31733-120">You should make sure that the person running Topology Builder has the following permissions and group memberships:</span></span>
    
      - <span data-ttu-id="31733-121">Membro de Administradores Locais</span><span class="sxs-lookup"><span data-stu-id="31733-121">Member of Local Administrators</span></span>
    
      - <span data-ttu-id="31733-122">Membro de Usuários do Domínio</span><span class="sxs-lookup"><span data-stu-id="31733-122">Member of Domain Users</span></span>
    
      - <span data-ttu-id="31733-123">Controle total sobre o compartilhamento e a pasta do repositório de arquivos</span><span class="sxs-lookup"><span data-stu-id="31733-123">Full Control on share and folder of file store</span></span>

  - <span data-ttu-id="31733-p106">Para o Enterprise Edition, instale e configure o SQL Server. Para que a instalação do SQL Server seja concluída com sucesso, o servidor com base no SQL Server deve estar online e a pessoa que estiver publicando a topologia deve ser administradora local no SQL Server e membro do grupo sysadmin na instância do SQL Server.</span><span class="sxs-lookup"><span data-stu-id="31733-p106">For Enterprise Edition, install and configure SQL Server. For SQL Server setup to succeed the SQL Server-based server must be online and the person publishing the topology be a local admin on the SQL Server and must be a member of the SQL Server sysadmin group on the SQL Server instance.</span></span>

<span data-ttu-id="31733-126">Depois de concluir todas as tarefas de preparação conforme descrito neste tópico, mas antes de publicar a topologia, também é necessário executar outras tarefas de preparação, incluindo a instalação dos sistemas operacionais Windows e os demais softwares de pré-requisito, configurar o IIS e o DNS.</span><span class="sxs-lookup"><span data-stu-id="31733-126">After you complete all of the preparation tasks as described in this topic, but prior to publishing the topology, you also need to perform the other preparation tasks, including installing the Windows operating systems and other prerequisite software, setting up IIS, and configuring DNS.</span></span> <span data-ttu-id="31733-127">Para obter detalhes sobre essas tarefas, consulte [requisitos do sistema para servidores que executam o Lync Server 2013](lync-server-2013-system-requirements-for-servers-running-lync-server-2013.md), [Configure o IIS para o Lync Server 2013](lync-server-2013-configure-iis.md)e [preparar a infraestrutura e os sistemas para o Lync Server 2013](lync-server-2013-preparing-the-infrastructure-and-systems.md).</span><span class="sxs-lookup"><span data-stu-id="31733-127">For details about these tasks, see [System requirements for servers running Lync Server 2013](lync-server-2013-system-requirements-for-servers-running-lync-server-2013.md), [Configure IIS for Lync Server 2013](lync-server-2013-configure-iis.md), and [Preparing the infrastructure and systems for Lync Server 2013](lync-server-2013-preparing-the-infrastructure-and-systems.md).</span></span> <span data-ttu-id="31733-128">Além disso, você deve estar familiarizado com os clientes e seus requisitos.</span><span class="sxs-lookup"><span data-stu-id="31733-128">Additionally, you should familiarize yourself with the clients and client requirements.</span></span> <span data-ttu-id="31733-129">Para obter detalhes, consulte [Deploying clients and Devices in Lync Server 2013](lync-server-2013-deploying-clients-and-devices.md).</span><span class="sxs-lookup"><span data-stu-id="31733-129">For details, see [Deploying clients and devices in Lync Server 2013](lync-server-2013-deploying-clients-and-devices.md).</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="31733-130">Nesta seção</span><span class="sxs-lookup"><span data-stu-id="31733-130">In This Section</span></span>

  - [<span data-ttu-id="31733-131">Configuração de hardware para o Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="31733-131">Hardware setup for Lync Server 2013</span></span>](lync-server-2013-hardware-setup.md)

  - [<span data-ttu-id="31733-132">Configuração de software para o Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="31733-132">Software setup for Lync Server 2013</span></span>](lync-server-2013-software-setup.md)

  - [<span data-ttu-id="31733-133">Preparando os Serviços de Domínio do Active Directory para o Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="31733-133">Preparing Active Directory Domain Services for Lync Server 2013</span></span>](lync-server-2013-preparing-active-directory-domain-services.md)

  - [<span data-ttu-id="31733-134">Configurar o SQL Server para o Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="31733-134">Configure SQL Server for Lync Server 2013</span></span>](lync-server-2013-configure-sql-server-for-lync-server.md)

  - [<span data-ttu-id="31733-135">Configurar registros DNS no Lync Server 2013 para um pool de front-ends ou servidor Standard Edition</span><span class="sxs-lookup"><span data-stu-id="31733-135">Configure DNS records in Lync Server 2013 for a Front End pool or Standard Edition server</span></span>](lync-server-2013-configure-dns-records-for-a-front-end-pool-or-standard-edition-server.md)

  - [<span data-ttu-id="31733-136">Instalar ferramentas administrativas do Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="31733-136">Install Lync Server 2013 administrative tools</span></span>](lync-server-2013-install-lync-server-administrative-tools.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

