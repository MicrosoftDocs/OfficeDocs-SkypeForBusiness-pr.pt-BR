---
title: 'Lync Server 2013: Protegendo os bancos de dados'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Hardening and protecting the databases of Lync Server 2013
ms:assetid: 6953e721-3511-4235-b848-51bab093dc89
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn518330(v=OCS.15)
ms:contentKeyID: 62625490
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 77e02a5fd0f90367f23e7b0fb314f037f7b31e45
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41739581"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="hardening-and-protecting-the-databases-of-lync-server-2013"></a><span data-ttu-id="30781-102">Protegendo os bancos de dados do Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="30781-102">Hardening and protecting the databases of Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="30781-103">_**Tópico da última modificação:** 2013-12-05_</span><span class="sxs-lookup"><span data-stu-id="30781-103">_**Topic Last Modified:** 2013-12-05_</span></span>

<span data-ttu-id="30781-104">O Microsoft Lync Server 2013 também depende dos bancos de dados do SQL Server para armazenar informações do usuário, o estado da conferência, os dados de arquivamento e os registros de detalhes da chamada (CDRs).</span><span class="sxs-lookup"><span data-stu-id="30781-104">Microsoft Lync Server 2013 also depends on SQL Server databases for storing user information, conference state, archiving data, and Call Detail Records (CDRs).</span></span> <span data-ttu-id="30781-105">Você pode maximizar a disponibilidade dos dados do Lync Server 2013 em bancos de dados back-end do Lync Server, Particionando os dados do aplicativo de forma a melhorar a tolerância a falhas e simplificar a solução de problemas.</span><span class="sxs-lookup"><span data-stu-id="30781-105">You can maximize the availability of Lync Server 2013 data on Lync Server back-end databases, by partitioning the application data in a way that improves fault tolerance and simplifies troubleshooting.</span></span> <span data-ttu-id="30781-106">Para alcançar essas metas, Particione os dados do aplicativo:</span><span class="sxs-lookup"><span data-stu-id="30781-106">To achieve these goals, partition the application data by:</span></span>

  - <span data-ttu-id="30781-107">**Usando as práticas**   recomendadas de particionamento do servidor, separe os arquivos de sistema operacional, aplicativo e programas dos arquivos de dados.</span><span class="sxs-lookup"><span data-stu-id="30781-107">**Using server partitioning best practices**   Separate your operating system, application, and program files from your data files.</span></span>

  - <span data-ttu-id="30781-108">**O armazenamento de arquivos de log de transação e arquivos**   de banco de dados armazena esses arquivos separadamente para aumentar a tolerância a falhas e otimizar a recuperação e armazená-los em um disco ou volume criptografado.</span><span class="sxs-lookup"><span data-stu-id="30781-108">**Storing transaction log files and database files**   Store these files separately to increase fault tolerance and optimize recovery, and store them on an encrypted disk or volume.</span></span>

  - <span data-ttu-id="30781-109">**Usar**   cluster de cluster de servidor os servidores back-end para otimizar a disponibilidade do sistema do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="30781-109">**Using server clustering**   Cluster the back-end servers to optimize Lync Server 2013 system availability.</span></span>

  - <span data-ttu-id="30781-110">**Certifique-se de que todos os backups de dados sejam criptografados e devidamente manipulados**   , descartados ou que não tenham sido feitas mídia de backup possam representar uma ameaça significativa à segurança de dados para implantações do Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="30781-110">**Ensure that all data backups are encrypted and properly handled**   Lost, discarded, or misplaced backup media can pose a significant threat to data security for Lync Server 2013 deployments</span></span>

<span data-ttu-id="30781-111">Em qualquer servidor do Lync Server 2013, exceto o Standard Edition Server, a instância do SQL Server Express (instância RTCLOCAL) não é acessível remotamente, e nenhuma exceção de firewall local é criada, exceto para o SQL Server Express em um servidor Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="30781-111">On any Lync Server 2013 server except Standard Edition server, the SQL Server Express instance (RTCLOCAL instance) is not remotely accessible, and no local firewall exceptions are created, except for SQL Server Express on a Standard Edition server.</span></span> <span data-ttu-id="30781-112">Em um servidor Standard Edition, o banco de dados back-end e o repositório de gerenciamento central (CMS) estão configurados para serem acessíveis remotamente.</span><span class="sxs-lookup"><span data-stu-id="30781-112">On a Standard Edition server, both the back-end database and the Central Management store (CMS) are set up to be remotely accessible.</span></span> <span data-ttu-id="30781-113">Para proteger bancos de dados do SQL Server, você pode fazer o seguinte:</span><span class="sxs-lookup"><span data-stu-id="30781-113">To harden SQL Server databases, you can do the following:</span></span>

  - <span data-ttu-id="30781-114">Personalize o Firewall do SQL Server Express nos servidores do Standard Edition, limitando o escopo de servidores que podem acessar o banco de dados remotamente.</span><span class="sxs-lookup"><span data-stu-id="30781-114">Customize the SQL Server Express firewall on Standard Edition servers, limiting the scope of servers that can remotely access the database.</span></span> <span data-ttu-id="30781-115">Por padrão, qualquer endereço IP pode acessar remotamente o banco de dados.</span><span class="sxs-lookup"><span data-stu-id="30781-115">By default, any IP address can remotely access the database.</span></span>

  - <span data-ttu-id="30781-116">Use o Gerenciador de configuração do SQL Server para especificar os protocolos, endereços IP e portas para o acesso remoto do SQL Server:</span><span class="sxs-lookup"><span data-stu-id="30781-116">Use SQL Server Configuration Manager to specify the protocols, IP addresses, and ports for SQL Server remote access:</span></span>
    
      - <span data-ttu-id="30781-117">O Lync Server 2013 usa o protocolo TCP/IP.</span><span class="sxs-lookup"><span data-stu-id="30781-117">Lync Server 2013 uses the TCP/IP protocol.</span></span> <span data-ttu-id="30781-118">Ele dá suporte a IP versão 4 (IPv4), mas não IP versão 6 (IPv6).</span><span class="sxs-lookup"><span data-stu-id="30781-118">It supports IP version 4 (IPv4), but not IP version 6 (IPv6).</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="30781-119">O Lync Server 2013 pode funcionar em uma rede com a pilha de IP duplo habilitada.</span><span class="sxs-lookup"><span data-stu-id="30781-119">Lync Server 2013 can function in a network with dual IP stack enabled.</span></span>

        
        </div>
    
      - <span data-ttu-id="30781-120">O Lync Server 2013 dá suporte a vários endereços IP (cartões de endereço de rede de hospedagem múltipla).</span><span class="sxs-lookup"><span data-stu-id="30781-120">Lync Server 2013 supports multiple IP address (multi-homed network address cards).</span></span> <span data-ttu-id="30781-121">Você pode especificar que o SQL Server escuta apenas em endereços IP específicos (endereço individual ou sub-rede) e usar somente protocolos específicos.</span><span class="sxs-lookup"><span data-stu-id="30781-121">You can specify that SQL Server listen only to specific IP addresses (individual address or by subnet) and only use specific protocols.</span></span>
    
      - <span data-ttu-id="30781-122">O Lync Server 2013 dá suporte a portas estáticas e dinâmicas do SQL Server.</span><span class="sxs-lookup"><span data-stu-id="30781-122">Lync Server 2013 supports static and dynamic SQL Server ports.</span></span>

  - <span data-ttu-id="30781-123">Execute o SQL Server em uma porta estática (não padrão) e não execute o navegador do SQL Server (para que ele não possa relatar a porta de escuta para o cliente).</span><span class="sxs-lookup"><span data-stu-id="30781-123">Run SQL Server on a static (non-default) port, and do not run SQL Server Browser (so it cannot report the listening port to the client).</span></span> <span data-ttu-id="30781-124">Isso requer uma configuração personalizada em cada cliente SQL Server, incluindo servidores front-end, Monitoring Server, servidor de arquivamento e consoles administrativos (executando o Shell de gerenciamento do Lync Server, o painel de controle do Lync Server ou o construtor de topologia) e todos os outros servidores que executam bancos de dados do Lync Server).</span><span class="sxs-lookup"><span data-stu-id="30781-124">This requires a custom configuration on each SQL Server client, including Front End Servers, Monitoring Server, Archiving Server, and administrative consoles (running Lync Server Management Shell, Lync Server Control Panel, or Topology Builder), and all other servers running Lync Server databases).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="30781-125">O acesso a bancos de dados deve estar limitado a administradores de banco de dados confiáveis.</span><span class="sxs-lookup"><span data-stu-id="30781-125">Access to databases must be limited to trusted database administrators.</span></span> <span data-ttu-id="30781-126">Um administrador de banco de dados mal-intencionado pode inserir ou modificar dados em bancos de dados para obter privilégios nos servidores do Lync Server 2013 ou obter informações confidenciais dos serviços, mesmo se o administrador do banco de dados não tiver recebido acesso direto ou controle dos servidores do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="30781-126">A malicious database administrator could insert or modify data into the databases to acquire privileges over the Lync Server 2013 servers or obtain sensitive information from the services, even if the database administrator has not been granted direct access or control of the Lync Server 2013 servers.</span></span>



</div>

<span data-ttu-id="30781-127">Para obter detalhes sobre configurações personalizadas e proteção de bancos de dados do SQL Server, consulte o artigo sobre o blog NextHop, "usando o Lync Server 2010 com uma configuração de rede [http://go.microsoft.com/fwlink/p/?LinkId=214008](http://go.microsoft.com/fwlink/p/?linkid=214008)personalizada do SQL Server" em.</span><span class="sxs-lookup"><span data-stu-id="30781-127">For details about custom configurations and hardening SQL Server databases, see the NextHop blog article, "Using Lync Server 2010 with a Custom SQL Server Network Configuration," at [http://go.microsoft.com/fwlink/p/?LinkId=214008](http://go.microsoft.com/fwlink/p/?linkid=214008).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="30781-128">Você também pode proteger sistemas operacionais e servidores de aplicativos, e pode usar a política de grupo para implementar bloqueios de segurança na implantação do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="30781-128">You can also harden operating systems and applications servers, and you can use Group Policy to implement security lockdowns in your Lync Server deployment.</span></span> <span data-ttu-id="30781-129">Para obter detalhes, consulte <A href="lync-server-2013-hardening-and-protecting-servers-and-applications.md">protegendo e protegendo servidores e aplicativos para o Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="30781-129">For details, see <A href="lync-server-2013-hardening-and-protecting-servers-and-applications.md">Hardening and protecting servers and applications for Lync Server 2013</A>.</span></span>



</div>

</div>

<span> </span>

</div>

</div>

</div>

