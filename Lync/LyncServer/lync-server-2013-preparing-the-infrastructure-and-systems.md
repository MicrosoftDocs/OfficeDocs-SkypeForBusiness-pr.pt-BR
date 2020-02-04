---
title: 'Lync Server 2013: Preparando a infraestrutura e os sistemas'
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
ms.openlocfilehash: 3fc49f5e246e69f600506d990ace7362d9666f1c
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41747301"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="preparing-the-infrastructure-and-systems-for-lync-server-2013"></a><span data-ttu-id="da579-102">Preparando a infraestrutura e os sistemas para o Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="da579-102">Preparing the infrastructure and systems for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="da579-103">_**Tópico da última modificação:** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="da579-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="da579-104">A implantação do Lync Server 2013 requer o uso do construtor de topologias para definir e publicar o design da topologia.</span><span class="sxs-lookup"><span data-stu-id="da579-104">Deployment of Lync Server 2013 requires the use of Topology Builder to define and publish the topology design.</span></span> <span data-ttu-id="da579-105">Para identificar os componentes necessários para a sua topologia, use o construtor de topologias para criar e salvar um design de topologia.</span><span class="sxs-lookup"><span data-stu-id="da579-105">To identify the components required for your topology, you use Topology Builder to create and save a topology design.</span></span> <span data-ttu-id="da579-106">Antes de publicar sua topologia no construtor de topologias, faça o seguinte:</span><span class="sxs-lookup"><span data-stu-id="da579-106">Prior to publishing your topology in Topology Builder, you do the following:</span></span>

  - <span data-ttu-id="da579-107">Adquirir e instalar o hardware para cada componente no design de topologia que você criou e salvou usando o construtor de topologias, incluindo todos os computadores obrigatórios (servidores que executam o Lync Server 2013, servidores de banco de dados, servidores que executam serviços de informações da Internet ( IIS) e servidores proxy inversos, conforme apropriado), adaptadores de rede, balanceadores de carga de hardware e dispositivos de armazenamento (como servidores de arquivos).</span><span class="sxs-lookup"><span data-stu-id="da579-107">Acquire and install the hardware for each component in the topology design that you created and saved by using Topology Builder, including all required computers (servers running Lync Server 2013, database servers, servers running Internet Information Services (IIS), and reverse proxy servers, as appropriate), network adapters, hardware load balancers, and storage devices (such as file servers).</span></span> <span data-ttu-id="da579-108">Para obter detalhes sobre como definir uma topologia que especifica os componentes necessários para sua implantação, consulte [definindo e configurando a topologia no Lync Server 2013](lync-server-2013-defining-and-configuring-the-topology.md).</span><span class="sxs-lookup"><span data-stu-id="da579-108">For details about how to define a topology that specifies the components needed for your deployment, see [Defining and configuring the topology in Lync Server 2013](lync-server-2013-defining-and-configuring-the-topology.md).</span></span> <span data-ttu-id="da579-109">Para obter detalhes sobre os requisitos de hardware para servidores, consulte [hardware com suporte para o Lync Server 2013](lync-server-2013-supported-hardware.md) na documentação de suporte.</span><span class="sxs-lookup"><span data-stu-id="da579-109">For details about hardware requirements for servers, see [Supported hardware for Lync Server 2013](lync-server-2013-supported-hardware.md) in the Supportability documentation.</span></span>

  - <span data-ttu-id="da579-110">Certifique-se de que a infraestrutura de rede atenda aos requisitos.</span><span class="sxs-lookup"><span data-stu-id="da579-110">Make sure that the networking infrastructure meets requirements.</span></span> <span data-ttu-id="da579-111">Para obter detalhes, consulte [requisitos de infraestrutura de rede para o Lync Server 2013](lync-server-2013-network-infrastructure-requirements.md) na documentação de planejamento.</span><span class="sxs-lookup"><span data-stu-id="da579-111">For details, see [Network infrastructure requirements for Lync Server 2013](lync-server-2013-network-infrastructure-requirements.md) in the Planning documentation.</span></span>

  - <span data-ttu-id="da579-112">Configurar os serviços de domínio do Active Directory.</span><span class="sxs-lookup"><span data-stu-id="da579-112">Set up Active Directory Domain Services.</span></span> <span data-ttu-id="da579-113">Para publicar e habilitar a topologia, você precisa que os servidores internos sejam representados por contas de computador no AD DS.</span><span class="sxs-lookup"><span data-stu-id="da579-113">To publish and enable the topology, you need the internal servers to be represented by computer accounts in AD DS.</span></span> <span data-ttu-id="da579-114">Isso é feito por meio da junção dos computadores com o AD DS.</span><span class="sxs-lookup"><span data-stu-id="da579-114">This is accomplished by joining the computers to AD DS.</span></span> <span data-ttu-id="da579-115">Para obter detalhes sobre como preparar o AD DS, consulte [preparando os serviços de domínio do Active Directory para o Lync Server 2013](lync-server-2013-preparing-active-directory-domain-services.md).</span><span class="sxs-lookup"><span data-stu-id="da579-115">For details about preparing AD DS, see [Preparing Active Directory Domain Services for Lync Server 2013](lync-server-2013-preparing-active-directory-domain-services.md).</span></span>

  - <span data-ttu-id="da579-116">Crie um compartilhamento de arquivos.</span><span class="sxs-lookup"><span data-stu-id="da579-116">Create a file share.</span></span> <span data-ttu-id="da579-117">Os servidores de edição padrão podem hospedar o compartilhamento de arquivos para o arquivo necessário, enquanto em uma implantação empresarial, o compartilhamento de arquivos não pode ser hospedado no servidor front-end.</span><span class="sxs-lookup"><span data-stu-id="da579-117">Standard Edition servers can host the file share for the required file, while in an Enterprise deployment the file share cannot be hosted on the front end server.</span></span> <span data-ttu-id="da579-118">As permissões e associações de grupo necessárias para implantar e configurar a ACL (lista de controle de acesso) na pasta e o compartilhamento devem ser definidas corretamente para que o construtor de topologias seja concluído com êxito.</span><span class="sxs-lookup"><span data-stu-id="da579-118">The permissions and group memberships required for deploying and setting the access control list (ACL) on the folder and the share must be set correctly for Topology Builder to complete successfully.</span></span> <span data-ttu-id="da579-119">Verifique se a pessoa que está executando o construtor de topologia tem as seguintes permissões e associações de Grupo:</span><span class="sxs-lookup"><span data-stu-id="da579-119">You should make sure that the person running Topology Builder has the following permissions and group memberships:</span></span>
    
      - <span data-ttu-id="da579-120">Membro de administradores locais</span><span class="sxs-lookup"><span data-stu-id="da579-120">Member of Local Administrators</span></span>
    
      - <span data-ttu-id="da579-121">Membro de usuários do domínio</span><span class="sxs-lookup"><span data-stu-id="da579-121">Member of Domain Users</span></span>
    
      - <span data-ttu-id="da579-122">Controle total sobre o compartilhamento e a pasta do armazenamento de arquivos</span><span class="sxs-lookup"><span data-stu-id="da579-122">Full Control on share and folder of file store</span></span>

  - <span data-ttu-id="da579-123">Para a edição Enterprise, instale e configure o SQL Server.</span><span class="sxs-lookup"><span data-stu-id="da579-123">For Enterprise Edition, install and configure SQL Server.</span></span> <span data-ttu-id="da579-124">Para que a configuração do SQL Server seja bem-sucedida, o servidor baseado no SQL Server deve estar online e a pessoa que publica a topologia é um administrador local no SQL Server e deve ser um membro do grupo sysadmin do SQL Server na instância do SQL Server.</span><span class="sxs-lookup"><span data-stu-id="da579-124">For SQL Server setup to succeed the SQL Server-based server must be online and the person publishing the topology be a local admin on the SQL Server and must be a member of the SQL Server sysadmin group on the SQL Server instance.</span></span>

<span data-ttu-id="da579-125">Depois de concluir todas as tarefas de preparação conforme descrito neste tópico, mas antes de publicar a topologia, você também precisará executar as outras tarefas de preparação, incluindo a instalação dos sistemas operacionais Windows e outros softwares de pré-requisito, a configuração IIS e Configurando o DNS.</span><span class="sxs-lookup"><span data-stu-id="da579-125">After you complete all of the preparation tasks as described in this topic, but prior to publishing the topology, you also need to perform the other preparation tasks, including installing the Windows operating systems and other prerequisite software, setting up IIS, and configuring DNS.</span></span> <span data-ttu-id="da579-126">Para obter detalhes sobre essas tarefas, consulte [requisitos do sistema para servidores que executam o Lync Server 2013](lync-server-2013-system-requirements-for-servers-running-lync-server-2013.md), [Configurar o IIS para o Lync Server 2013](lync-server-2013-configure-iis.md)e [preparar a infraestrutura e os sistemas para o Lync Server 2013](lync-server-2013-preparing-the-infrastructure-and-systems.md).</span><span class="sxs-lookup"><span data-stu-id="da579-126">For details about these tasks, see [System requirements for servers running Lync Server 2013](lync-server-2013-system-requirements-for-servers-running-lync-server-2013.md), [Configure IIS for Lync Server 2013](lync-server-2013-configure-iis.md), and [Preparing the infrastructure and systems for Lync Server 2013](lync-server-2013-preparing-the-infrastructure-and-systems.md).</span></span> <span data-ttu-id="da579-127">Além disso, você deve se familiarizar com os requisitos do cliente e clientes.</span><span class="sxs-lookup"><span data-stu-id="da579-127">Additionally, you should familiarize yourself with the clients and client requirements.</span></span> <span data-ttu-id="da579-128">Para obter detalhes, consulte [implantando clientes e dispositivos no Lync Server 2013](lync-server-2013-deploying-clients-and-devices.md).</span><span class="sxs-lookup"><span data-stu-id="da579-128">For details, see [Deploying clients and devices in Lync Server 2013](lync-server-2013-deploying-clients-and-devices.md).</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="da579-129">Nesta seção</span><span class="sxs-lookup"><span data-stu-id="da579-129">In This Section</span></span>

  - [<span data-ttu-id="da579-130">Configuração de hardware para Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="da579-130">Hardware setup for Lync Server 2013</span></span>](lync-server-2013-hardware-setup.md)

  - [<span data-ttu-id="da579-131">Configuração de software no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="da579-131">Software setup for Lync Server 2013</span></span>](lync-server-2013-software-setup.md)

  - [<span data-ttu-id="da579-132">Preparando Serviços de Domínio do Active Directory para o Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="da579-132">Preparing Active Directory Domain Services for Lync Server 2013</span></span>](lync-server-2013-preparing-active-directory-domain-services.md)

  - [<span data-ttu-id="da579-133">Configurar o SQL Server para Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="da579-133">Configure SQL Server for Lync Server 2013</span></span>](lync-server-2013-configure-sql-server-for-lync-server.md)

  - [<span data-ttu-id="da579-134">Configurar registros DNS no Lync Server 2013 para um pool de Front-Ends ou servidor Standard Edition</span><span class="sxs-lookup"><span data-stu-id="da579-134">Configure DNS records in Lync Server 2013 for a Front End pool or Standard Edition server</span></span>](lync-server-2013-configure-dns-records-for-a-front-end-pool-or-standard-edition-server.md)

  - [<span data-ttu-id="da579-135">Instalar ferramentas administrativas do Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="da579-135">Install Lync Server 2013 administrative tools</span></span>](lync-server-2013-install-lync-server-administrative-tools.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

