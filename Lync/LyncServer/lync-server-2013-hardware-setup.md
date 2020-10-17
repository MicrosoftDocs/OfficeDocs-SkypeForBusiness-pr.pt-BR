---
title: 'Lync Server 2013: configuração de hardware'
description: 'Lync Server 2013: configuração de hardware.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Hardware setup
ms:assetid: 37a9f295-cde3-4beb-9a6a-2580082798ab
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425852(v=OCS.15)
ms:contentKeyID: 48183834
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4e798ce32c1f89bba40ad9245426492b0489e7b4
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48552907"
---
# <a name="hardware-setup-for-lync-server-2013"></a><span data-ttu-id="05dd1-103">Configuração de hardware para o Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="05dd1-103">Hardware setup for Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="05dd1-104">_**Última modificação do tópico:** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="05dd1-104">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="05dd1-105">Configurar o hardware e outros componentes necessários na infraestrutura de que você precisa para implementar sua topologia requer que, antes de publicar sua topologia no construtor de topologias, faça o seguinte:</span><span class="sxs-lookup"><span data-stu-id="05dd1-105">Setting up the hardware and other components required in the infrastructure that you need to implement your topology requires that, prior to publishing your topology in Topology Builder, you do the following:</span></span>

  - <span data-ttu-id="05dd1-106">Instale o hardware para cada componente no design de topologia que você criou e salvou usando o construtor de topologias, incluindo todos os computadores necessários (servidores que executam o Lync Server 2013, servidores de banco de dados, servidores que executam os serviços de informações da Internet (IIS) e servidores de proxy reverso, conforme apropriado), adaptadores de rede, balanceadores de carga de hardware</span><span class="sxs-lookup"><span data-stu-id="05dd1-106">Install the hardware for each component in the topology design that you created and saved by using Topology Builder, including all required computers (servers running Lync Server 2013, database servers, servers running Internet Information Services (IIS), and reverse proxy servers, as appropriate), network adapters, hardware load balancers, and storage devices (such as file servers).</span></span> <span data-ttu-id="05dd1-107">Confirme que seguiu as recomendações de número e velocidade dos adaptadores de rede.</span><span class="sxs-lookup"><span data-stu-id="05dd1-107">Confirm that you have followed the recommendations for the number and speed for network adapters.</span></span> <span data-ttu-id="05dd1-108">Se você for usar balanceadores de carga de hardware, certifique-se de ter as informações corretas do fornecedor para configurá-las para uso com o Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="05dd1-108">If you will be using hardware load balancers, make sure that you have the proper information from the vendor to configure them for use with Lync Server 2013.</span></span> <span data-ttu-id="05dd1-109">Se você estiver usando um servidor de arquivos ou outro servidor para hospedar o compartilhamento de arquivos exigido pelo Lync Server, certifique-se de que o servidor está disponível e pronto para a configuração do compartilhamento de arquivos.</span><span class="sxs-lookup"><span data-stu-id="05dd1-109">If you will be using a file server or other server to house the file share required by Lync Server, make sure that the server is available and ready for the configuration of the file share.</span></span> <span data-ttu-id="05dd1-110">Para obter detalhes sobre como definir uma topologia que especifica os componentes necessários para sua implantação, consulte [definindo e configurando a topologia no Lync Server 2013](lync-server-2013-defining-and-configuring-the-topology.md).</span><span class="sxs-lookup"><span data-stu-id="05dd1-110">For details about how to define a topology that specifies the components needed for your deployment, see [Defining and configuring the topology in Lync Server 2013](lync-server-2013-defining-and-configuring-the-topology.md).</span></span> <span data-ttu-id="05dd1-111">Para obter detalhes sobre os requisitos de hardware para servidores, consulte [hardware suportado para o Lync Server 2013](lync-server-2013-supported-hardware.md) na documentação de suporte.</span><span class="sxs-lookup"><span data-stu-id="05dd1-111">For details about hardware requirements for servers, see [Supported hardware for Lync Server 2013](lync-server-2013-supported-hardware.md) in the Supportability documentation.</span></span>

  - <span data-ttu-id="05dd1-112">Certifique-se de que a infraestrutura de rede atende aos requisitos.</span><span class="sxs-lookup"><span data-stu-id="05dd1-112">Make sure that the networking infrastructure meets requirements.</span></span> <span data-ttu-id="05dd1-113">Para obter detalhes, consulte [Network Infrastructure Requirements for Lync Server 2013](lync-server-2013-network-infrastructure-requirements.md) na documentação de planejamento.</span><span class="sxs-lookup"><span data-stu-id="05dd1-113">For details, see [Network infrastructure requirements for Lync Server 2013](lync-server-2013-network-infrastructure-requirements.md) in the Planning documentation.</span></span>

  - <span data-ttu-id="05dd1-114">Configurar os serviços de domínio do Active Directory.</span><span class="sxs-lookup"><span data-stu-id="05dd1-114">Set up Active Directory Domain Services.</span></span> <span data-ttu-id="05dd1-115">A configuração do AD DS inclui prepará-lo e definir todos os componentes que você deseja implementar nele.</span><span class="sxs-lookup"><span data-stu-id="05dd1-115">Setting up AD DS includes preparing AD DS and defining all components that you want to deploy in AD DS.</span></span> <span data-ttu-id="05dd1-116">Para obter detalhes sobre como preparar o AD DS, consulte [preparação de serviços de domínio do Active Directory para o Lync Server 2013](lync-server-2013-preparing-active-directory-domain-services.md) na documentação de implantação.</span><span class="sxs-lookup"><span data-stu-id="05dd1-116">For details about preparing AD DS, see [Preparing Active Directory Domain Services for Lync Server 2013](lync-server-2013-preparing-active-directory-domain-services.md) in the Deployment documentation.</span></span>

  - <span data-ttu-id="05dd1-117">Configure as permissões exigidas para criar o compartilhamento de arquivo.</span><span class="sxs-lookup"><span data-stu-id="05dd1-117">Set up the required permissions for creating the file share.</span></span> <span data-ttu-id="05dd1-118">As permissões para o uso de compartilhamentos de arquivos pelo Lync Server 2013 são automaticamente configuradas pelo construtor de topologias quando você publica sua topologia.</span><span class="sxs-lookup"><span data-stu-id="05dd1-118">Permissions for use of file shares by Lync Server 2013 are automatically configured by Topology Builder when you publish your topology.</span></span> <span data-ttu-id="05dd1-119">No entanto, a conta de usuário usada para publicar a topologia deve ter controle total (leitura/gravação/modificação) no compartilhamento de arquivos para que o construtor de topologia configure as permissões necessárias.</span><span class="sxs-lookup"><span data-stu-id="05dd1-119">However, the user account used to publish the topology must have full control (read/write/modify) on the file share in order for Topology Builder to configure the required permissions.</span></span> <span data-ttu-id="05dd1-120">Para garantir que o compartilhamento de arquivos possa ser gerenciado corretamente durante o processo de publicação do construtor de topologia, o usuário ou grupo de domínio do qual o usuário é membro deve ser membro do grupo local de administradores no computador onde o compartilhamento de arquivo está localizado.</span><span class="sxs-lookup"><span data-stu-id="05dd1-120">To make sure that the file share can be managed properly during the Topology Builder publishing process, the user or domain group that the user is a member of should be made a member of the local Administrators group on the machine where the file share is located.</span></span> <span data-ttu-id="05dd1-121">Em um cenário com diversos domínios, o usuário o grupo do Domínio A deve ser tornado membro do grupo local de Administradores na máquina no Domínio B em que o compartilhamento de arquivos será localizado.</span><span class="sxs-lookup"><span data-stu-id="05dd1-121">In a multi-domain scenario, Domain A user or group should be made a member of the local Administrators group on the machine in Domain B where the file share will be located.</span></span>
    
    <span data-ttu-id="05dd1-122">Para obter detalhes sobre a atualização usando os compartilhamentos de arquivos em um sistema de arquivos distribuídos (DFS), consulte [Configurar o armazenamento de arquivos para Lync Server 2013](lync-server-2013-configure-dfs-file-storage.md).</span><span class="sxs-lookup"><span data-stu-id="05dd1-122">For details about updating using file shares in a Distributed File System (DFS), see [Configure file storage for Lync Server 2013](lync-server-2013-configure-dfs-file-storage.md).</span></span>
    
    <div>
    

    > [!WARNING]  
    > <span data-ttu-id="05dd1-123">O compartilhamento de arquivos do Lync Server 2013, Enterprise Edition, não pode ser localizado no servidor front-end.</span><span class="sxs-lookup"><span data-stu-id="05dd1-123">The file share for Lync Server 2013, Enterprise Edition cannot be located on the Front End Server.</span></span>

    
    </div>

  - <span data-ttu-id="05dd1-124">Instale e configure o balanceador de carga de hardware para serviços Web.</span><span class="sxs-lookup"><span data-stu-id="05dd1-124">Install and set up the hardware load balancer for Web Services.</span></span> <span data-ttu-id="05dd1-125">Com o balanceamento de carga do Sistema de Nome de Domínio (DNS) implantado, você ainda precisa usar balanceadores de carga de hardware para esses pools, mas somente para o tráfego de HTTP/HTTPS.</span><span class="sxs-lookup"><span data-stu-id="05dd1-125">With Domain Name System (DNS) load balancing deployed, you still need to also use hardware load balancers for these pools, but only for HTTP/HTTPS traffic.</span></span> <span data-ttu-id="05dd1-126">O balanceador de carga de hardware é usado para o tráfego de HTTPS dos clientes pelas portas 443 e 80.</span><span class="sxs-lookup"><span data-stu-id="05dd1-126">The hardware load balancer is used for HTTPS traffic from clients over ports 443 and 80.</span></span> <span data-ttu-id="05dd1-127">Embora você ainda precise de balanceadores de carga de hardware para esses pools, sua configuração e administração será principalmente para o tráfego HTTP/HTTPS, aos quais os administradores dos balanceadores de carga de hardware estão acostumados.</span><span class="sxs-lookup"><span data-stu-id="05dd1-127">Although you still need hardware load balancers for these pools, their setup and administration will be primarily for HTTP/HTTPS traffic, which the administrators of the hardware load balancers are accustomed to.</span></span>

<span data-ttu-id="05dd1-128">Depois de concluir todas as tarefas de preparação descritas neste tópico, mas antes de publicar a topologia, também é necessário:</span><span class="sxs-lookup"><span data-stu-id="05dd1-128">After you complete all of the preparation tasks as described in this topic, but prior to publishing the topology, you also need to:</span></span>

  - [<span data-ttu-id="05dd1-129">Instalar sistemas operacionais e software de pré-requisito nos servidores do Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="05dd1-129">Install operating systems and prerequisite software on servers for Lync Server 2013</span></span>](lync-server-2013-install-operating-systems-and-prerequisite-software-on-servers.md)

  - [<span data-ttu-id="05dd1-130">Configurar o IIS para Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="05dd1-130">Configure IIS for Lync Server 2013</span></span>](lync-server-2013-configure-iis.md)

  - [<span data-ttu-id="05dd1-131">Configurar o SQL Server para o Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="05dd1-131">Configure SQL Server for Lync Server 2013</span></span>](lync-server-2013-configure-sql-server-for-lync-server.md)

  - [<span data-ttu-id="05dd1-132">Configurar registros DNS no Lync Server 2013 para um pool de front-ends ou servidor Standard Edition</span><span class="sxs-lookup"><span data-stu-id="05dd1-132">Configure DNS records in Lync Server 2013 for a Front End pool or Standard Edition server</span></span>](lync-server-2013-configure-dns-records-for-a-front-end-pool-or-standard-edition-server.md)

</div>

<span> </span>

</div>

</div>

</div>

