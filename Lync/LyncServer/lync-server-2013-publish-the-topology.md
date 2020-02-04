---
title: 'Lync Server 2013: Publicar a topologia'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Publish the topology
ms:assetid: 3b5a744b-b3a8-4538-a55e-e2e4f72dff47
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425880(v=OCS.15)
ms:contentKeyID: 48183866
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5760315cc60aa53a40457423c2b5402896c2a90c
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41747071"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="publish-the-topology-in-lync-server-2013"></a><span data-ttu-id="48cf4-102">Publicar a topologia no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="48cf4-102">Publish the topology in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="48cf4-103">_**Tópico da última modificação:** 2013-10-01_</span><span class="sxs-lookup"><span data-stu-id="48cf4-103">_**Topic Last Modified:** 2013-10-01_</span></span>

<span data-ttu-id="48cf4-104">Para publicar, habilitar ou desabilitar uma topologia com êxito ao adicionar ou remover uma função de servidor, você deve estar conectado como um usuário que é membro do grupo RTCUniversalServerAdmins e administradores do domínio.</span><span class="sxs-lookup"><span data-stu-id="48cf4-104">To successfully publish, enable, or disable a topology when adding or removing a server role, you should be logged in as a user who is a member of the RTCUniversalServerAdmins and Domain Admins groups.</span></span> <span data-ttu-id="48cf4-105">Também é possível delegar permissões e direitos de administrador adequados.</span><span class="sxs-lookup"><span data-stu-id="48cf4-105">It is also possible to delegate the proper administrator rights and permissions.</span></span> <span data-ttu-id="48cf4-106">Para obter detalhes, consulte [delegar permissões de configuração no Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span><span class="sxs-lookup"><span data-stu-id="48cf4-106">For details, see [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span> <span data-ttu-id="48cf4-107">Para outras alterações de configuração, somente a associação no grupo RTCUniversalServerAdmins é necessária.</span><span class="sxs-lookup"><span data-stu-id="48cf4-107">For other configuration changes, only membership in the RTCUniversalServerAdmins group is required.</span></span>

<span data-ttu-id="48cf4-108">Depois de definir sua topologia no construtor de topologias, você deve publicar a topologia no repositório de gerenciamento central.</span><span class="sxs-lookup"><span data-stu-id="48cf4-108">After you define your topology in Topology Builder, you must publish the topology to the Central Management store.</span></span> <span data-ttu-id="48cf4-109">O repositório de gerenciamento central fornece um armazenamento robusto e schematized dos dados necessários para definir, configurar, manter, administrar, descrever e operar uma implantação do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="48cf4-109">The Central Management store provides a robust, schematized storage of the data needed to define, set up, maintain, administer, describe, and operate a Lync Server 2013 deployment.</span></span> <span data-ttu-id="48cf4-110">Ele também valida os dados para ajudar a garantir a consistência de configuração.</span><span class="sxs-lookup"><span data-stu-id="48cf4-110">It also validates the data to help ensure configuration consistency.</span></span> <span data-ttu-id="48cf4-111">Todas as alterações nestes dados de configuração acontecem nesse repositório, eliminando problemas de "dessincronização".</span><span class="sxs-lookup"><span data-stu-id="48cf4-111">All changes to this configuration data happen at the Central Management store, eliminating “out-of-sync” issues.</span></span> <span data-ttu-id="48cf4-112">Cópias somente leitura dos dados são replicadas para todos os servidores na topologia, incluindo os servidores de borda.</span><span class="sxs-lookup"><span data-stu-id="48cf4-112">Read-only copies of the data are replicated to all servers in the topology, including Edge Servers.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="48cf4-113">O SQL Server precisa de no mínimo 20 GB de espaço livre em disco para a publicação bem-sucedida da topologia inicial e a criação do servidor de gerenciamento central.</span><span class="sxs-lookup"><span data-stu-id="48cf4-113">SQL Server needs a minimum of 20 GB of free disk space to successfully publish the initial topology and create the Central Management Server.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="48cf4-114">Para a Enterprise Edition somente: para publicar a topologia, o servidor back-end baseado em SQL Server deve estar online e acessível com exceções de firewall no lugar.</span><span class="sxs-lookup"><span data-stu-id="48cf4-114">For Enterprise Edition only: In order to publish the topology, the SQL Server-based Back End Server must be online and accessible with firewall exceptions in place.</span></span> <span data-ttu-id="48cf4-115">Para obter detalhes sobre como especificar exceções de firewall, consulte <A href="lync-server-2013-understanding-firewall-requirements-for-sql-server.md">noções básicas sobre requisitos de firewall do SQL Server com o Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="48cf4-115">For details about specifying firewall exceptions, see <A href="lync-server-2013-understanding-firewall-requirements-for-sql-server.md">Understanding firewall requirements for SQL Server with Lync Server 2013</A>.</span></span> <span data-ttu-id="48cf4-116">Para obter detalhes sobre como configurar o SQL Server, consulte <A href="lync-server-2013-configure-sql-server-for-lync-server.md">Configurar o SQL Server para o Lync server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="48cf4-116">For details about configuring SQL Server, see <A href="lync-server-2013-configure-sql-server-for-lync-server.md">Configure SQL Server for Lync Server 2013</A>.</span></span>



</div>

<div>

## <a name="to-publish-a-topology"></a><span data-ttu-id="48cf4-117">Para publicar uma topologia</span><span class="sxs-lookup"><span data-stu-id="48cf4-117">To publish a topology</span></span>

1.  <span data-ttu-id="48cf4-118">Iniciar o construtor de topologias: clique em **Iniciar**, em **todos os programas**, em **Microsoft Lync Server 2013**e, em seguida, clique em **Construtor de topologias do Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="48cf4-118">Start Topology Builder: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Topology Builder**.</span></span>

2.  <span data-ttu-id="48cf4-119">Selecione para abrir a topologia a partir de um arquivo local.</span><span class="sxs-lookup"><span data-stu-id="48cf4-119">Select to open the topology from a local file.</span></span> <span data-ttu-id="48cf4-120">Se estiver no computador em que você definiu a topologia, ela estará no local onde você a salvou nas etapas anteriores.</span><span class="sxs-lookup"><span data-stu-id="48cf4-120">If you are on the computer where you defined the topology, this will be in the location where you saved it in earlier steps.</span></span> <span data-ttu-id="48cf4-121">Geralmente, essa será a pasta documentos do usuário que configurou a topologia.</span><span class="sxs-lookup"><span data-stu-id="48cf4-121">Typically, this will be the Documents folder of the user who configured the topology.</span></span>

3.  <span data-ttu-id="48cf4-122">Clique com o botão direito do mouse no nó do **Lync Server 2013** e, em seguida, clique em **publicar topologia**.</span><span class="sxs-lookup"><span data-stu-id="48cf4-122">Right-click the **Lync Server 2013** node, and then click **Publish Topology**.</span></span>

4.  <span data-ttu-id="48cf4-123">Na página **Publicar a topologia**, clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="48cf4-123">On the **Publish the topology** page, click **Next**.</span></span>

5.  <span data-ttu-id="48cf4-124">Na página **criar bancos de dados** , selecione os bancos de dados que você deseja publicar.</span><span class="sxs-lookup"><span data-stu-id="48cf4-124">On the **Create databases** page, select the databases you want to publish.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="48cf4-125">Se não tiver os direitos apropriados para criar os bancos de dados, você poderá desmarcar as caixas de seleção ao lado desses bancos de dados e, posteriormente, alguém com os direitos apropriados poderá criar os bancos de dados.</span><span class="sxs-lookup"><span data-stu-id="48cf4-125">If you don’t have the appropriate rights to create the databases, you can clear the check boxes next to those databases, and someone with appropriate rights can later create the databases.</span></span> <span data-ttu-id="48cf4-126">Para obter detalhes, consulte <A href="lync-server-2013-deployment-permissions-for-sql-server.md">permissões de implantação do SQL Server no Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="48cf4-126">For details, see <A href="lync-server-2013-deployment-permissions-for-sql-server.md">Deployment permissions for SQL Server in Lync Server 2013</A>.</span></span>

    
    </div>

6.  <span data-ttu-id="48cf4-127">Opcionalmente, clique em  **Avançado**.</span><span class="sxs-lookup"><span data-stu-id="48cf4-127">Optionally click **Advanced**.</span></span> <span data-ttu-id="48cf4-128">As opções avançadas de posicionamento do arquivo de dados do SQL Server permitem que você selecione entre as seguintes opções:</span><span class="sxs-lookup"><span data-stu-id="48cf4-128">The Advanced SQL Server data file placement options let you select between the following options:</span></span>
    
      - <span data-ttu-id="48cf4-129">**Determinar automaticamente o local do arquivo de banco de dados** – essa opção determinará o melhor desempenho operacional com base na configuração de disco do servidor baseado no SQL Server, distribuindo os arquivos de log e de dados para o melhor local.</span><span class="sxs-lookup"><span data-stu-id="48cf4-129">**Automatically determine database file location** – This option will determine the best operational performance based on the disk configuration on your SQL Server-based server by distributing the log and data files to the best location.</span></span>
    
      - <span data-ttu-id="48cf4-p107">**Usar padrões de instância SQL Server**. Essa opção coloca arquivos de log e de dados no servidor baseado em SQL Server usando as configurações de instância. Essa opção não usa a funcionalidade operacional do servidor baseado em SQL Server para determinar locais ideais para logs e dados. O administrador do SQL Server normalmente moverá os arquivos de log e dados para locais apropriados para os procedimentos de gerenciamento de servidor e organização baseados em SQL Server.</span><span class="sxs-lookup"><span data-stu-id="48cf4-p107">**Use SQL Server instance defaults** – This option puts log and data files onto the SQL Server-based server by using the instance settings. This option does not use the operational functionality of the SQL Server-based server to determine optimal locations for logs and data. The SQL Server administrator would typically move the log and data files to locations that are appropriate for the SQL Server-based server and organization management procedures.</span></span>
    
    <span data-ttu-id="48cf4-133">Clique em **OK** e, em seguida, em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="48cf4-133">Click **OK**, and then click **Next**.</span></span>

7.  <span data-ttu-id="48cf4-134">Na página **selecionar servidor de gerenciamento central** , selecione um pool de front-end.</span><span class="sxs-lookup"><span data-stu-id="48cf4-134">On the **Select Central Management Server** page, select a Front End pool.</span></span>

8.  <span data-ttu-id="48cf4-135">Opcionalmente, clique em  **Avançado**.</span><span class="sxs-lookup"><span data-stu-id="48cf4-135">Optionally click **Advanced**.</span></span> <span data-ttu-id="48cf4-136">As opções avançadas de posicionamento de arquivos de dados do SQL Server permitem que você selecione entre as seguintes opções:</span><span class="sxs-lookup"><span data-stu-id="48cf4-136">The Advanced SQL Server data file placement options enables you to select between the following options:</span></span>
    
      - <span data-ttu-id="48cf4-137">**Determinar automaticamente o local do arquivo de banco de dados** – essa opção determinará o melhor desempenho operacional com base na configuração de disco do servidor baseado no SQL Server, distribuindo os arquivos de log e de dados para o melhor local.</span><span class="sxs-lookup"><span data-stu-id="48cf4-137">**Automatically determine database file location** – This option will determine the best operational performance based on the disk configuration on your SQL Server-based server by distributing the log and data files to the best location.</span></span>
    
      - <span data-ttu-id="48cf4-p109">**Usar padrões de instância SQL Server**. Essa opção coloca arquivos de log e de dados no servidor baseado em SQL Server usando as configurações de instância. Essa opção não usa a funcionalidade operacional do servidor baseado em SQL Server para determinar locais ideais para logs e dados. O administrador do SQL Server normalmente moverá os arquivos de log e dados para locais apropriados para os procedimentos de gerenciamento de servidor e organização baseados em SQL Server.</span><span class="sxs-lookup"><span data-stu-id="48cf4-p109">**Use SQL Server instance defaults** – This option puts log and data files onto the SQL Server-based server by using the instance settings. This option does not use the operational functionality of the SQL Server-based server to determine optimal locations for logs and data. The SQL Server administrator would typically move the log and data files to locations that are appropriate for the SQL Server-based server and organization management procedures.</span></span>
    
    <span data-ttu-id="48cf4-141">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="48cf4-141">Click **OK**.</span></span>

9.  <span data-ttu-id="48cf4-142">Clique em **Avançar** para concluir o processo de publicação.</span><span class="sxs-lookup"><span data-stu-id="48cf4-142">Click **Next** to complete the publishing process.</span></span>

10. <span data-ttu-id="48cf4-143">Quando o processo de publicação for concluído, clique em **concluir**.</span><span class="sxs-lookup"><span data-stu-id="48cf4-143">When the publish process has completed, click **Finish**.</span></span>
    
    <span data-ttu-id="48cf4-144">Quando a topologia é publicada com êxito, você pode começar a instalar uma réplica local do repositório de gerenciamento central em cada servidor que executa o Lync Server 2013 na sua topologia.</span><span class="sxs-lookup"><span data-stu-id="48cf4-144">When the topology has been published successfully, you can begin installing a local replica of the Central Management store on each server running Lync Server 2013 in your topology.</span></span> <span data-ttu-id="48cf4-145">É recomendável começar com o primeiro pool de front-ends.</span><span class="sxs-lookup"><span data-stu-id="48cf4-145">We recommend that you begin with the first Front End pool.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="48cf4-146">Confira também</span><span class="sxs-lookup"><span data-stu-id="48cf4-146">See Also</span></span>


[<span data-ttu-id="48cf4-147">Configurand Servidores e pools Front-End para Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="48cf4-147">Setting up Front End Servers and Front End pools for Lync Server 2013</span></span>](lync-server-2013-setting-up-front-end-servers-and-front-end-pools.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

