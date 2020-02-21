---
title: 'Lync Server 2013: configurar clustering do SQL Server'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure SQL Server clustering
ms:assetid: d7b52ef1-573c-48ed-bb94-34e37b49645c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn383982(v=OCS.15)
ms:contentKeyID: 56472032
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 59c02a5ab417a17c7c81b2c495ce96e6948aebc7
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42179888"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configure-sql-server-clustering-for-lync-server-2013"></a><span data-ttu-id="bd224-102">Configurar o cluster do SQL Server para o Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="bd224-102">Configure SQL Server clustering for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="bd224-103">_**Última modificação do tópico:** 2014-01-10_</span><span class="sxs-lookup"><span data-stu-id="bd224-103">_**Topic Last Modified:** 2014-01-10_</span></span>

<span data-ttu-id="bd224-104">O Microsoft Lync Server 2013 suporta clustering para o SQL Server 2012 e o SQL Server 2008 R2.</span><span class="sxs-lookup"><span data-stu-id="bd224-104">Microsoft Lync Server 2013 supports clustering for SQL Server 2012 and SQL Server 2008 R2.</span></span> <span data-ttu-id="bd224-105">Para obter detalhes sobre o que é suportado, confira [suporte a software de banco de dados no Lync Server 2013](lync-server-2013-database-software-support.md).</span><span class="sxs-lookup"><span data-stu-id="bd224-105">For details about what is supported, see [Database software support in Lync Server 2013](lync-server-2013-database-software-support.md).</span></span>

<span data-ttu-id="bd224-106">Você deve configurar e configurar o cluster do SQL Server antes de instalar e implantar o servidor front-end Enterprise Edition e o banco de dados back-end.</span><span class="sxs-lookup"><span data-stu-id="bd224-106">You should set up and configure the SQL Server cluster before you install and deploy the Enterprise Edition Front End Server and back-end database.</span></span> <span data-ttu-id="bd224-107">Para obter as práticas recomendadas e as instruções de instalação do clustering de failover <https://technet.microsoft.com/library/hh231721.aspx>no SQL Server 2012, consulte.</span><span class="sxs-lookup"><span data-stu-id="bd224-107">For best practices and setup instructions for failover clustering in SQL Server 2012, see <https://technet.microsoft.com/library/hh231721.aspx>.</span></span> <span data-ttu-id="bd224-108">Para clustering de failover no SQL Server 2008, <https://technet.microsoft.com/library/ms189134(v=sql.105).aspx>consulte.</span><span class="sxs-lookup"><span data-stu-id="bd224-108">For failover clustering in SQL Server 2008, see <https://technet.microsoft.com/library/ms189134(v=sql.105).aspx>.</span></span>

<span data-ttu-id="bd224-109">Ao instalar o SQL Server, você deve instalar o SQL Server Management Studio para gerenciar os locais para o banco de daods e os locais para o arquivo de log.</span><span class="sxs-lookup"><span data-stu-id="bd224-109">When you install SQL Server, you should install SQL Server Management Studio to manage the locations for database and log file locations.</span></span> <span data-ttu-id="bd224-110">O SQL Server Management Studio é instalado como um componente opcional ao instalar o SQL Server.</span><span class="sxs-lookup"><span data-stu-id="bd224-110">SQL Server Management Studio is installed as an optional component when you install SQL Server.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="bd224-111">Para instalar e implantar os bancos de dados no servidor baseado em SQL Server, é necessário ser um membro do grupo sysadmin do SQL Server para o servidor baseado em SQL Server onde você está instalando os arquivos de banco de dados.</span><span class="sxs-lookup"><span data-stu-id="bd224-111">To install and deploy the databases on the SQL Server-based server, you must be a member of the SQL Server sysadmin group for the SQL Server-based server where you are installing the database files.</span></span> <span data-ttu-id="bd224-112">Se você não for membro do grupo sysadmin do SQL Server, será necessário solicitar sua adição ao grupo até que os arquivos do banco de dados sejam implantados.</span><span class="sxs-lookup"><span data-stu-id="bd224-112">If you are not a member of the SQL Server sysadmin group, you will need to request that you be added to the group until the database files are deployed.</span></span> <span data-ttu-id="bd224-113">Se você não puder se tornar um membro do grupo sysadmin, forneça ao seu administrador de banco de dados do SQL Server o script para configurar e implantar os bancos de dados.</span><span class="sxs-lookup"><span data-stu-id="bd224-113">If you cannot be made a member of the sysadmin group, you should provide your SQL Server database administrator with the script to configure and deploy the databases.</span></span> <span data-ttu-id="bd224-114">Para obter detalhes sobre os direitos e permissões de usuário adequados que você precisa para realizar os procedimentos, consulte <A href="lync-server-2013-deployment-permissions-for-sql-server.md">Deployment Permissions for SQL Server in Lync server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="bd224-114">For details about the proper user rights and permissions that you need to accomplish the procedures, see <A href="lync-server-2013-deployment-permissions-for-sql-server.md">Deployment permissions for SQL Server in Lync Server 2013</A>.</span></span>



</div>

<div>

## <a name="to-configure-sql-server-clustering"></a><span data-ttu-id="bd224-115">Para configurar o cluster de SQL Server</span><span class="sxs-lookup"><span data-stu-id="bd224-115">To configure SQL Server clustering</span></span>

1.  <span data-ttu-id="bd224-116">Depois de concluir a instalação e a configuração do cluster do SQL Server, defina o repositório do SQL Server no construtor de topologias usando o nome de cluster virtual da instância do SQL Server (conforme configurado na configuração para o cluster do SQL Server) e a instância nome do banco de dados do SQL Server.</span><span class="sxs-lookup"><span data-stu-id="bd224-116">After you have completed the installation and configuration of SQL Server clustering, you define the SQL Server store in Topology Builder by using the SQL Server instance virtual cluster name (as configured in the setup for SQL Server clustering) and the instance name of the SQL Server database.</span></span> <span data-ttu-id="bd224-117">Diferente de um servidor único baseado em SQL Server, você usará o FQDN (nome de domínio totalmente qualificado) do nó virtual para um servidor baseado em SQL Server em cluster.</span><span class="sxs-lookup"><span data-stu-id="bd224-117">Different from a single SQL Server-based server, you will use the virtual node fully qualified domain name (FQDN) for a clustered SQL Server-based server.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="bd224-118">Os nós de cluster individuais do Windows Server não precisam ser configurados para o construtor de topologias.</span><span class="sxs-lookup"><span data-stu-id="bd224-118">The individual Windows Server cluster nodes do not have to be configured for Topology Builder.</span></span> <span data-ttu-id="bd224-119">Você usará somente o nome do cluster SQL Server virtual.</span><span class="sxs-lookup"><span data-stu-id="bd224-119">You will use only the virtual SQL Server cluster name.</span></span>

    
    </div>

2.  <span data-ttu-id="bd224-120">Se você estiver usando o construtor de topologias para implantar seus bancos de dados, você deve ser membro do grupo sysadmin do SQL Server.</span><span class="sxs-lookup"><span data-stu-id="bd224-120">If you are using Topology Builder to deploy your databases, you must be a member of the SQL Server sysadmin group.</span></span> <span data-ttu-id="bd224-121">Se você é membro do grupo sysadmin do SQL Server, mas não tem privilégios no domínio (por exemplo, uma função de administrador de banco de dados do SQL Server), você tem os direitos para criar os bancos de dados, mas não para ler as informações necessárias no Lync Server.</span><span class="sxs-lookup"><span data-stu-id="bd224-121">If you are a member of the SQL Server sysadmin group, but you do not have privileges in the domain (for example, a SQL Server database administrator role), then you have the rights to create the databases but not to read necessary information in Lync Server.</span></span> <span data-ttu-id="bd224-122">Para obter detalhes sobre os direitos e permissões de usuário necessários para implantar o Lync Server, consulte [Deployment Permissions for SQL Server in Lync server 2013](lync-server-2013-deployment-permissions-for-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="bd224-122">For details about the user rights and permissions necessary to deploying Lync Server, see [Deployment permissions for SQL Server in Lync Server 2013](lync-server-2013-deployment-permissions-for-sql-server.md).</span></span>

3.  <span data-ttu-id="bd224-p108">Certifique-se que o padrão de pasta de banco de dados e de pasta de arquivos de log sejam mapeados corretamente para os discos compartilhados no cluster de SQL Server usando o SQL Server Management Studio. Esse é um procedimento necessário se você for criar bancos de dados usando o Construtor de Topologia.</span><span class="sxs-lookup"><span data-stu-id="bd224-p108">Ensure that the database folder and log files folder defaults are mapped correctly to the shared disks in the SQL Server cluster by using SQL Server Management Studio. This is a required procedure if you will create databases by using Topology Builder.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="bd224-125">Se você não tiver instalado o SQL Server Management Studio, poderá instalá-lo executando novamente a instalação do SQL Server e selecionando a ferramenta de gerenciamento como um recurso adicionado para a implantação existente do SQL Server.</span><span class="sxs-lookup"><span data-stu-id="bd224-125">If you did not install SQL Server Management Studio, you can install it by rerunning the SQL Server installation, and then selecting the management tool as an added feature for the existing SQL Server deployment.</span></span>

    
    </div>

4.  <span data-ttu-id="bd224-126">Instale os bancos de dados para o servidor baseado em SQL Server usando o construtor de topologias ou os cmdlets do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="bd224-126">Install the databases for the SQL Server-based server by using either Topology Builder or Windows PowerShell cmdlets.</span></span> <span data-ttu-id="bd224-127">Para usar o construtor de topologias, use o procedimento a seguir.</span><span class="sxs-lookup"><span data-stu-id="bd224-127">To use Topology Builder, use the following procedure.</span></span> <span data-ttu-id="bd224-128">Para usar os cmdlets do Windows PowerShell, consulte [instalação de banco de dados usando o Shell de gerenciamento do Lync Server no Lync server 2013](lync-server-2013-database-installation-using-lync-server-management-shell.md).</span><span class="sxs-lookup"><span data-stu-id="bd224-128">To use Windows PowerShell cmdlets, see [Database installation using Lync Server Management Shell in Lync Server 2013](lync-server-2013-database-installation-using-lync-server-management-shell.md).</span></span>

</div>

<div>

## <a name="to-create-databases-using-topology-builder"></a><span data-ttu-id="bd224-129">Para criar bancos de dados usando o construtor de topologias</span><span class="sxs-lookup"><span data-stu-id="bd224-129">To create databases using Topology Builder</span></span>

1.  <span data-ttu-id="bd224-130">Inicie o construtor de topologias: clique em **Iniciar**, em **todos os programas**, em **Microsoft Lync Server 2013**e em **Construtor de topologias do Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="bd224-130">Start Topology Builder: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Topology Builder**.</span></span>
    
    <div>
    

    > [!WARNING]  
    > <span data-ttu-id="bd224-131">O procedimento a seguir pressupõe que você tenha definido e configurado sua topologia no construtor de topologias.</span><span class="sxs-lookup"><span data-stu-id="bd224-131">The following procedure assumes that you have defined and configured your topology in Topology Builder.</span></span> <span data-ttu-id="bd224-132">Para obter detalhes sobre como definir sua topologia, consulte<A href="lync-server-2013-defining-and-configuring-the-topology.md">definindo e configurando a topologia no Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="bd224-132">For details about defining your topology, see<A href="lync-server-2013-defining-and-configuring-the-topology.md">Defining and configuring the topology in Lync Server 2013</A>.</span></span> <span data-ttu-id="bd224-133">Para usar o Construtor de Topologia para publicar e configurar o banco de dados, faça logon como um usuário com os direitos de usuário e associações de grupo corretas.</span><span class="sxs-lookup"><span data-stu-id="bd224-133">To use Topology Builder to publish the topology and configure the database, you must log on as a user with the correct user rights and group memberships.</span></span> <span data-ttu-id="bd224-134">Para obter detalhes sobre os direitos e associações de grupo necessários, consulte <A href="lync-server-2013-deployment-permissions-for-sql-server.md">Deployment Permissions for SQL Server in Lync server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="bd224-134">For details about the required rights and group memberships, see <A href="lync-server-2013-deployment-permissions-for-sql-server.md">Deployment permissions for SQL Server in Lync Server 2013</A>.</span></span>

    
    </div>

2.  <span data-ttu-id="bd224-135">No construtor de topologias, à medida que você publicar a topologia, na página **criar bancos de dados** , clique em **avançado**.</span><span class="sxs-lookup"><span data-stu-id="bd224-135">In Topology Builder, as you publish the topology, on the **Create databases** page, click **Advanced**.</span></span>

3.  <span data-ttu-id="bd224-p111">A página **Selecionar Local de Arquivo de Banco de Dados** tem duas opções que determinam como os arquivos de banco de dados serão implantados no cluster de SQL Server. Selecione uma das seguintes opções:</span><span class="sxs-lookup"><span data-stu-id="bd224-p111">The **Select Database File Location** page has two options that determine how the database files will be deployed to the SQL Server cluster. Select one of the following:</span></span>
    
      - <span data-ttu-id="bd224-138">**Determina automaticamente o local do arquivo do banco de dados.**</span><span class="sxs-lookup"><span data-stu-id="bd224-138">**Automatically determine the database file location.**</span></span> <span data-ttu-id="bd224-139">Essa seleção usa um algoritmo para determinar os locais de log e arquivo de dados do banco de dados com base na configuração de unidade no servidor baseado em SQL Server.</span><span class="sxs-lookup"><span data-stu-id="bd224-139">This selection uses an algorithm to determine the database log and data file locations based on the drive configuration on the SQL Server-based server.</span></span> <span data-ttu-id="bd224-140">Os arquivos serão distribuídos de uma forma que tenta fornecer o melhor desempenho.</span><span class="sxs-lookup"><span data-stu-id="bd224-140">The files will be distributed in such a way as to attempt to provide optimal performance.</span></span>
    
      - <span data-ttu-id="bd224-141">Usar padrões de instância do SQL Server.</span><span class="sxs-lookup"><span data-stu-id="bd224-141">Use SQL Server instance defaults.</span></span> <span data-ttu-id="bd224-142">Selecionar essa opção instalará os arquivos de log e de dados de acordo com as configurações da instância do SQL Server.</span><span class="sxs-lookup"><span data-stu-id="bd224-142">Selecting this option will install the log and data files according to the SQL Server instance settings.</span></span> <span data-ttu-id="bd224-143">Após a implantação dos arquivos do banco de dados no SQL Server, o administrador do banco de dados do SQL Server pode querer realocar os arquivos para otimizar o desempenho de seus requisitos de configuração do SQL Server específicos.</span><span class="sxs-lookup"><span data-stu-id="bd224-143">After deployment of the database files to the SQL Server, your SQL Server database administrator may want to relocate the files to optimize performance for your particular SQL Server configuration requirements.</span></span>

4.  <span data-ttu-id="bd224-144">Conclua a publicação da topologia e verifique se não ocorreram erros durante a operação.</span><span class="sxs-lookup"><span data-stu-id="bd224-144">Complete the publishing of the topology and confirm that there were no errors during the operation.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

