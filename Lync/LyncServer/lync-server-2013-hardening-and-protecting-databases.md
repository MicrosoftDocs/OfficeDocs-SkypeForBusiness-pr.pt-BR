---
title: 'Lync Server 2013: proteção e proteção de bancos de dados'
description: 'Lync Server 2013: proteção e proteção de bancos de dados.'
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
ms.openlocfilehash: af1ed8f54384e8ecac3b1e4ce6a4253a10bcc2c6
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48577427"
---
# <a name="hardening-and-protecting-the-databases-of-lync-server-2013"></a><span data-ttu-id="8f7a0-103">Proteção e proteção dos bancos de dados do Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8f7a0-103">Hardening and protecting the databases of Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8f7a0-104">_**Última modificação do tópico:** 2013-12-05_</span><span class="sxs-lookup"><span data-stu-id="8f7a0-104">_**Topic Last Modified:** 2013-12-05_</span></span>

<span data-ttu-id="8f7a0-105">O Microsoft Lync Server 2013 também depende dos bancos de dados do SQL Server para armazenar as informações do usuário, o estado da conferência, dados de arquivamento e CDRs (registros de detalhes de chamada).</span><span class="sxs-lookup"><span data-stu-id="8f7a0-105">Microsoft Lync Server 2013 also depends on SQL Server databases for storing user information, conference state, archiving data, and Call Detail Records (CDRs).</span></span> <span data-ttu-id="8f7a0-106">Você pode maximizar a disponibilidade de dados do Lync Server 2013 em bancos de dados de back-end do Lync Server, Particionando os dados do aplicativo de forma a melhorar a tolerância a falhas e simplificar a solução de problemas.</span><span class="sxs-lookup"><span data-stu-id="8f7a0-106">You can maximize the availability of Lync Server 2013 data on Lync Server back-end databases, by partitioning the application data in a way that improves fault tolerance and simplifies troubleshooting.</span></span> <span data-ttu-id="8f7a0-107">Para alcançar essas metas, siga estas diretrizes:</span><span class="sxs-lookup"><span data-stu-id="8f7a0-107">To achieve these goals, partition the application data by:</span></span>

  - <span data-ttu-id="8f7a0-108">**Usando as práticas**     recomendadas de particionamento de servidor Separe seus arquivos de sistema operacional, aplicativos e programas de seus arquivos de dados.</span><span class="sxs-lookup"><span data-stu-id="8f7a0-108">**Using server partitioning best practices**   Separate your operating system, application, and program files from your data files.</span></span>

  - <span data-ttu-id="8f7a0-109">**Armazenar arquivos de log de transações e arquivos**     de banco de dados Armazene esses arquivos separadamente para aumentar a tolerância a falhas e otimizar a recuperação e armazená-los em um disco ou volume criptografado.</span><span class="sxs-lookup"><span data-stu-id="8f7a0-109">**Storing transaction log files and database files**   Store these files separately to increase fault tolerance and optimize recovery, and store them on an encrypted disk or volume.</span></span>

  - <span data-ttu-id="8f7a0-110">**Usando o clustering**     de servidor Agrupa os servidores de back-end para otimizar a disponibilidade do sistema do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="8f7a0-110">**Using server clustering**   Cluster the back-end servers to optimize Lync Server 2013 system availability.</span></span>

  - <span data-ttu-id="8f7a0-111">**Garantir que todos os backups de dados sejam criptografados e devidamente tratados**     As mídias de backup perdidas, descartadas ou colocadas incorreta podem representar uma ameaça significativa à segurança de dados para implantações do Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8f7a0-111">**Ensure that all data backups are encrypted and properly handled**   Lost, discarded, or misplaced backup media can pose a significant threat to data security for Lync Server 2013 deployments</span></span>

<span data-ttu-id="8f7a0-112">Em qualquer servidor do Lync Server 2013, exceto servidor Standard Edition, a instância do SQL Server Express (instância do RTCLOCAL) não é acessível remotamente, e nenhuma exceção de firewall local é criada, exceto para o SQL Server Express em um servidor Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="8f7a0-112">On any Lync Server 2013 server except Standard Edition server, the SQL Server Express instance (RTCLOCAL instance) is not remotely accessible, and no local firewall exceptions are created, except for SQL Server Express on a Standard Edition server.</span></span> <span data-ttu-id="8f7a0-113">Em um servidor Standard Edition, o banco de dados back-end e o CMS (Repositório de Gerenciamento Central) são configurados para serem acessados remotamente.</span><span class="sxs-lookup"><span data-stu-id="8f7a0-113">On a Standard Edition server, both the back-end database and the Central Management store (CMS) are set up to be remotely accessible.</span></span> <span data-ttu-id="8f7a0-114">Para proteger os bancos de dados SQL Server, é possível fazer o seguinte:</span><span class="sxs-lookup"><span data-stu-id="8f7a0-114">To harden SQL Server databases, you can do the following:</span></span>

  - <span data-ttu-id="8f7a0-p103">Personalizar o firewall do SQL Server Express nos servidores Standard Edition, limitando o escopo dos servidores que podem acessar remotamente o banco de dados. Por padrão, qualquer endereço IP pode acessar remotamente o banco de dados.</span><span class="sxs-lookup"><span data-stu-id="8f7a0-p103">Customize the SQL Server Express firewall on Standard Edition servers, limiting the scope of servers that can remotely access the database. By default, any IP address can remotely access the database.</span></span>

  - <span data-ttu-id="8f7a0-117">Usar o SQL Server Configuration Manager para especificar os protocolos, os endereços IP e as portas para acesso remoto do SQL Server:</span><span class="sxs-lookup"><span data-stu-id="8f7a0-117">Use SQL Server Configuration Manager to specify the protocols, IP addresses, and ports for SQL Server remote access:</span></span>
    
      - <span data-ttu-id="8f7a0-118">O Lync Server 2013 usa o protocolo TCP/IP.</span><span class="sxs-lookup"><span data-stu-id="8f7a0-118">Lync Server 2013 uses the TCP/IP protocol.</span></span> <span data-ttu-id="8f7a0-119">Ele suporta IP versão 4 (IPv4), mas não IP versão 6 (IPv6).</span><span class="sxs-lookup"><span data-stu-id="8f7a0-119">It supports IP version 4 (IPv4), but not IP version 6 (IPv6).</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="8f7a0-120">O Lync Server 2013 pode funcionar em uma rede com uma pilha de IP Dual habilitada.</span><span class="sxs-lookup"><span data-stu-id="8f7a0-120">Lync Server 2013 can function in a network with dual IP stack enabled.</span></span>

        
        </div>
    
      - <span data-ttu-id="8f7a0-121">O Lync Server 2013 oferece suporte a vários endereços IP (cartões de endereço de rede de hospedagem múltipla).</span><span class="sxs-lookup"><span data-stu-id="8f7a0-121">Lync Server 2013 supports multiple IP address (multi-homed network address cards).</span></span> <span data-ttu-id="8f7a0-122">É possível especificar que o SQL Server escute somente endereços IP específicos (endereço individual ou por sub-rede) e use somente protocolos específicos.</span><span class="sxs-lookup"><span data-stu-id="8f7a0-122">You can specify that SQL Server listen only to specific IP addresses (individual address or by subnet) and only use specific protocols.</span></span>
    
      - <span data-ttu-id="8f7a0-123">O Lync Server 2013 oferece suporte a portas estáticas e dinâmicas do SQL Server.</span><span class="sxs-lookup"><span data-stu-id="8f7a0-123">Lync Server 2013 supports static and dynamic SQL Server ports.</span></span>

  - <span data-ttu-id="8f7a0-124">Executar o SQL Server em uma porta estática (não padrão) e não executar o SQL Server Browser (para que não informe a porta que está escutando ao cliente).</span><span class="sxs-lookup"><span data-stu-id="8f7a0-124">Run SQL Server on a static (non-default) port, and do not run SQL Server Browser (so it cannot report the listening port to the client).</span></span> <span data-ttu-id="8f7a0-125">Isso requer uma configuração personalizada em cada cliente do SQL Server, incluindo servidores front-end, servidor de monitoramento, servidor de arquivamento e consoles administrativos (executando o Shell de gerenciamento do Lync Server, o painel de controle do Lync Server ou o construtor de topologias) e todos os outros servidores que executam os bancos de dados do Lync Server).</span><span class="sxs-lookup"><span data-stu-id="8f7a0-125">This requires a custom configuration on each SQL Server client, including Front End Servers, Monitoring Server, Archiving Server, and administrative consoles (running Lync Server Management Shell, Lync Server Control Panel, or Topology Builder), and all other servers running Lync Server databases).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="8f7a0-126">O acesso aos bancos de dados precisa ser limitado aos administradores de banco de dados confiáveis.</span><span class="sxs-lookup"><span data-stu-id="8f7a0-126">Access to databases must be limited to trusted database administrators.</span></span> <span data-ttu-id="8f7a0-127">Um administrador de banco de dados mal-intencionado pode inserir ou modificar dados nos bancos de dados para adquirir privilégios nos servidores do Lync Server 2013 ou obter informações confidenciais dos serviços, mesmo se o administrador do banco de dados não tiver sido concedido acesso direto ou controle dos servidores do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="8f7a0-127">A malicious database administrator could insert or modify data into the databases to acquire privileges over the Lync Server 2013 servers or obtain sensitive information from the services, even if the database administrator has not been granted direct access or control of the Lync Server 2013 servers.</span></span>



</div>

<span data-ttu-id="8f7a0-128">Para obter detalhes sobre as configurações personalizadas e a proteção de bancos de dados do SQL Server, consulte o artigo de blog NextHop, "using Lync Server 2010 with a Custom SQL Server Network Configuration" em [https://go.microsoft.com/fwlink/p/?LinkId=214008](https://go.microsoft.com/fwlink/p/?linkid=214008) .</span><span class="sxs-lookup"><span data-stu-id="8f7a0-128">For details about custom configurations and hardening SQL Server databases, see the NextHop blog article, "Using Lync Server 2010 with a Custom SQL Server Network Configuration," at [https://go.microsoft.com/fwlink/p/?LinkId=214008](https://go.microsoft.com/fwlink/p/?linkid=214008).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="8f7a0-129">Você também pode otimizar a segurança de sistemas operacionais e servidores de aplicativos e pode usar a política de grupo para implementar bloqueios de segurança em sua implantação do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="8f7a0-129">You can also harden operating systems and applications servers, and you can use Group Policy to implement security lockdowns in your Lync Server deployment.</span></span> <span data-ttu-id="8f7a0-130">Para obter detalhes, consulte <A href="lync-server-2013-hardening-and-protecting-servers-and-applications.md">proteção e proteção de servidores e aplicativos para o Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="8f7a0-130">For details, see <A href="lync-server-2013-hardening-and-protecting-servers-and-applications.md">Hardening and protecting servers and applications for Lync Server 2013</A>.</span></span>



</div>

</div>

<span> </span>

</div>

</div>

</div>

