---
title: 'Lync Server 2013: publicar a topologia'
description: 'Lync Server 2013: publicar a topologia.'
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
ms.openlocfilehash: 453fe186a02c88a5dcd7308096b661058fc04aa6
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48547717"
---
# <a name="publish-the-topology-in-lync-server-2013"></a><span data-ttu-id="0ab5e-103">Publicar a topologia no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0ab5e-103">Publish the topology in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0ab5e-104">_**Última modificação do tópico:** 2013-10-01_</span><span class="sxs-lookup"><span data-stu-id="0ab5e-104">_**Topic Last Modified:** 2013-10-01_</span></span>

<span data-ttu-id="0ab5e-105">Para publicar com sucesso, habilite ou desabilite uma topologia ao adicionar ou remover uma função do servidor, você deve estar conectado como um usuário que é um membro do RTCUniversalServerAdmins e dos grupos Administradores do Domínio.</span><span class="sxs-lookup"><span data-stu-id="0ab5e-105">To successfully publish, enable, or disable a topology when adding or removing a server role, you should be logged in as a user who is a member of the RTCUniversalServerAdmins and Domain Admins groups.</span></span> <span data-ttu-id="0ab5e-106">Também é possível delegar as permissões e direitos de administrador adequadas.</span><span class="sxs-lookup"><span data-stu-id="0ab5e-106">It is also possible to delegate the proper administrator rights and permissions.</span></span> <span data-ttu-id="0ab5e-107">Para obter detalhes, consulte [delegar permissões de configuração no Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span><span class="sxs-lookup"><span data-stu-id="0ab5e-107">For details, see [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span> <span data-ttu-id="0ab5e-108">Para obter as alterações de configuração, somente a associação no grupo RTCUniversalServerAdmins é exigida.</span><span class="sxs-lookup"><span data-stu-id="0ab5e-108">For other configuration changes, only membership in the RTCUniversalServerAdmins group is required.</span></span>

<span data-ttu-id="0ab5e-109">Depois de definir sua topologia no construtor de topologias, você deve publicar a topologia no repositório de gerenciamento central.</span><span class="sxs-lookup"><span data-stu-id="0ab5e-109">After you define your topology in Topology Builder, you must publish the topology to the Central Management store.</span></span> <span data-ttu-id="0ab5e-110">O repositório de gerenciamento central fornece um armazenamento robusto, esquematizado dos dados necessários para definir, configurar, manter, administrar, descrever e operar uma implantação do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="0ab5e-110">The Central Management store provides a robust, schematized storage of the data needed to define, set up, maintain, administer, describe, and operate a Lync Server 2013 deployment.</span></span> <span data-ttu-id="0ab5e-111">Ele também valida os dados para ajudar a garantir a consistência da configuração.</span><span class="sxs-lookup"><span data-stu-id="0ab5e-111">It also validates the data to help ensure configuration consistency.</span></span> <span data-ttu-id="0ab5e-112">Todas as alterações feitas nesses dados de configuração acontecem no repositório de gerenciamento central, eliminando problemas de "fora de sincronização".</span><span class="sxs-lookup"><span data-stu-id="0ab5e-112">All changes to this configuration data happen at the Central Management store, eliminating “out-of-sync” issues.</span></span> <span data-ttu-id="0ab5e-113">Cópias somente leitura dos dados são replicadas para todos os servidores na topologia, incluindo os servidores de borda.</span><span class="sxs-lookup"><span data-stu-id="0ab5e-113">Read-only copies of the data are replicated to all servers in the topology, including Edge Servers.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="0ab5e-114">O SQL Server precisa de um mínimo de 20 GB de espaço livre em disco para publicar a topologia inicial com êxito e criar o servidor de gerenciamento central.</span><span class="sxs-lookup"><span data-stu-id="0ab5e-114">SQL Server needs a minimum of 20 GB of free disk space to successfully publish the initial topology and create the Central Management Server.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="0ab5e-115">Somente para o Enterprise Edition: para publicar a topologia, o servidor back-end baseado em SQL Server deve estar online e acessível com exceções de firewall no local.</span><span class="sxs-lookup"><span data-stu-id="0ab5e-115">For Enterprise Edition only: In order to publish the topology, the SQL Server-based Back End Server must be online and accessible with firewall exceptions in place.</span></span> <span data-ttu-id="0ab5e-116">Para obter detalhes sobre como especificar exceções de firewall, consulte <A href="lync-server-2013-understanding-firewall-requirements-for-sql-server.md">Understanding firewall Requirements for SQL Server with Lync server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="0ab5e-116">For details about specifying firewall exceptions, see <A href="lync-server-2013-understanding-firewall-requirements-for-sql-server.md">Understanding firewall requirements for SQL Server with Lync Server 2013</A>.</span></span> <span data-ttu-id="0ab5e-117">Para obter detalhes sobre como configurar o SQL Server, consulte <A href="lync-server-2013-configure-sql-server-for-lync-server.md">Configurar o SQL Server para o Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="0ab5e-117">For details about configuring SQL Server, see <A href="lync-server-2013-configure-sql-server-for-lync-server.md">Configure SQL Server for Lync Server 2013</A>.</span></span>



</div>

<div>

## <a name="to-publish-a-topology"></a><span data-ttu-id="0ab5e-118">Para publicar uma topologia</span><span class="sxs-lookup"><span data-stu-id="0ab5e-118">To publish a topology</span></span>

1.  <span data-ttu-id="0ab5e-119">Inicie o construtor de topologias: clique em **Iniciar**, em **todos os programas**, em **Microsoft Lync Server 2013**e em **Construtor de topologias do Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="0ab5e-119">Start Topology Builder: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Topology Builder**.</span></span>

2.  <span data-ttu-id="0ab5e-120">Selecione para abrir a topologia de um arquivo local.</span><span class="sxs-lookup"><span data-stu-id="0ab5e-120">Select to open the topology from a local file.</span></span> <span data-ttu-id="0ab5e-121">Se você estiver no computador em que você definiu a topologia, ela estará no local onde você a salvou nas etapas anteriores.</span><span class="sxs-lookup"><span data-stu-id="0ab5e-121">If you are on the computer where you defined the topology, this will be in the location where you saved it in earlier steps.</span></span> <span data-ttu-id="0ab5e-122">Normalmente, essa será a pasta de documentos do usuário que configurou a topologia.</span><span class="sxs-lookup"><span data-stu-id="0ab5e-122">Typically, this will be the Documents folder of the user who configured the topology.</span></span>

3.  <span data-ttu-id="0ab5e-123">Clique com o botão direito do mouse no nó **Lync Server 2013** e clique em **publicar topologia**.</span><span class="sxs-lookup"><span data-stu-id="0ab5e-123">Right-click the **Lync Server 2013** node, and then click **Publish Topology**.</span></span>

4.  <span data-ttu-id="0ab5e-124">Na página **Publicar a Topologia**, clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="0ab5e-124">On the **Publish the topology** page, click **Next**.</span></span>

5.  <span data-ttu-id="0ab5e-125">Na página **criar bancos de dados** , selecione os bancos de dados que você deseja publicar.</span><span class="sxs-lookup"><span data-stu-id="0ab5e-125">On the **Create databases** page, select the databases you want to publish.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="0ab5e-126">Se você não tiver os direitos apropriados para criar os bancos de dados, você pode desmarcar as caixas de seleção ao lado desses bancos de dados e alguém com direitos apropriados pode criar os bancos de dados mais tarde.</span><span class="sxs-lookup"><span data-stu-id="0ab5e-126">If you don’t have the appropriate rights to create the databases, you can clear the check boxes next to those databases, and someone with appropriate rights can later create the databases.</span></span> <span data-ttu-id="0ab5e-127">Para obter detalhes, consulte <A href="lync-server-2013-deployment-permissions-for-sql-server.md">Deployment Permissions for SQL Server in Lync server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="0ab5e-127">For details, see <A href="lync-server-2013-deployment-permissions-for-sql-server.md">Deployment permissions for SQL Server in Lync Server 2013</A>.</span></span>

    
    </div>

6.  <span data-ttu-id="0ab5e-128">Opcionalmente, clique em **avançado**.</span><span class="sxs-lookup"><span data-stu-id="0ab5e-128">Optionally click **Advanced**.</span></span> <span data-ttu-id="0ab5e-129">As opções avançadas de posicionamento do arquivo de dados do SQL Server permitem que você selecione entre as seguintes opções:</span><span class="sxs-lookup"><span data-stu-id="0ab5e-129">The Advanced SQL Server data file placement options let you select between the following options:</span></span>
    
      - <span data-ttu-id="0ab5e-130">**Determinar automaticamente o local do arquivo de banco de dados** – essa opção determinará o melhor desempenho operacional com base na configuração do disco no servidor baseado em SQL Server, distribuindo os arquivos de log e de dados para o melhor local.</span><span class="sxs-lookup"><span data-stu-id="0ab5e-130">**Automatically determine database file location** – This option will determine the best operational performance based on the disk configuration on your SQL Server-based server by distributing the log and data files to the best location.</span></span>
    
      - <span data-ttu-id="0ab5e-131">**Usar padrões de instância do SQL Server** – essa opção coloca os arquivos de log e de dados no servidor baseado em SQL Server usando as configurações da instância.</span><span class="sxs-lookup"><span data-stu-id="0ab5e-131">**Use SQL Server instance defaults** – This option puts log and data files onto the SQL Server-based server by using the instance settings.</span></span> <span data-ttu-id="0ab5e-132">Essa opção não usa a funcionalidade operacional do servidor baseado em SQL Server para determinar os locais ideais para logs e dados.</span><span class="sxs-lookup"><span data-stu-id="0ab5e-132">This option does not use the operational functionality of the SQL Server-based server to determine optimal locations for logs and data.</span></span> <span data-ttu-id="0ab5e-133">O administrador do SQL Server normalmente moveria os arquivos de log e de dados para locais apropriados para os procedimentos de gerenciamento de organização e servidor baseados no SQL Server.</span><span class="sxs-lookup"><span data-stu-id="0ab5e-133">The SQL Server administrator would typically move the log and data files to locations that are appropriate for the SQL Server-based server and organization management procedures.</span></span>
    
    <span data-ttu-id="0ab5e-134">Clique em **OK**, e depois clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="0ab5e-134">Click **OK**, and then click **Next**.</span></span>

7.  <span data-ttu-id="0ab5e-135">Na página **selecionar servidor de gerenciamento central** , selecione um pool de front-ends.</span><span class="sxs-lookup"><span data-stu-id="0ab5e-135">On the **Select Central Management Server** page, select a Front End pool.</span></span>

8.  <span data-ttu-id="0ab5e-136">Opcionalmente, clique em **avançado**.</span><span class="sxs-lookup"><span data-stu-id="0ab5e-136">Optionally click **Advanced**.</span></span> <span data-ttu-id="0ab5e-137">As opções avançadas de posicionamento do arquivo de dados do SQL Server permitem que você selecione entre as seguintes opções:</span><span class="sxs-lookup"><span data-stu-id="0ab5e-137">The Advanced SQL Server data file placement options enables you to select between the following options:</span></span>
    
      - <span data-ttu-id="0ab5e-138">**Determinar automaticamente o local do arquivo de banco de dados** – essa opção determinará o melhor desempenho operacional com base na configuração do disco no servidor baseado em SQL Server, distribuindo os arquivos de log e de dados para o melhor local.</span><span class="sxs-lookup"><span data-stu-id="0ab5e-138">**Automatically determine database file location** – This option will determine the best operational performance based on the disk configuration on your SQL Server-based server by distributing the log and data files to the best location.</span></span>
    
      - <span data-ttu-id="0ab5e-139">**Usar padrões de instância do SQL Server** – essa opção coloca os arquivos de log e de dados no servidor baseado em SQL Server usando as configurações da instância.</span><span class="sxs-lookup"><span data-stu-id="0ab5e-139">**Use SQL Server instance defaults** – This option puts log and data files onto the SQL Server-based server by using the instance settings.</span></span> <span data-ttu-id="0ab5e-140">Essa opção não usa a funcionalidade operacional do servidor baseado em SQL Server para determinar os locais ideais para logs e dados.</span><span class="sxs-lookup"><span data-stu-id="0ab5e-140">This option does not use the operational functionality of the SQL Server-based server to determine optimal locations for logs and data.</span></span> <span data-ttu-id="0ab5e-141">O administrador do SQL Server normalmente moveria os arquivos de log e de dados para locais apropriados para os procedimentos de gerenciamento de organização e servidor baseados no SQL Server.</span><span class="sxs-lookup"><span data-stu-id="0ab5e-141">The SQL Server administrator would typically move the log and data files to locations that are appropriate for the SQL Server-based server and organization management procedures.</span></span>
    
    <span data-ttu-id="0ab5e-142">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="0ab5e-142">Click **OK**.</span></span>

9.  <span data-ttu-id="0ab5e-143">Clique em **Avançar** para concluir o processo de publicação.</span><span class="sxs-lookup"><span data-stu-id="0ab5e-143">Click **Next** to complete the publishing process.</span></span>

10. <span data-ttu-id="0ab5e-144">Quando o processo de publicação for concluído, clique em **Finalizar**.</span><span class="sxs-lookup"><span data-stu-id="0ab5e-144">When the publish process has completed, click **Finish**.</span></span>
    
    <span data-ttu-id="0ab5e-145">Quando a topologia foi publicada com êxito, você pode começar a instalar uma réplica local do repositório de gerenciamento central em cada servidor que executa o Lync Server 2013 em sua topologia.</span><span class="sxs-lookup"><span data-stu-id="0ab5e-145">When the topology has been published successfully, you can begin installing a local replica of the Central Management store on each server running Lync Server 2013 in your topology.</span></span> <span data-ttu-id="0ab5e-146">Recomendamos que você comece com o primeiro pool de front-ends.</span><span class="sxs-lookup"><span data-stu-id="0ab5e-146">We recommend that you begin with the first Front End pool.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="0ab5e-147">Confira também</span><span class="sxs-lookup"><span data-stu-id="0ab5e-147">See Also</span></span>


[<span data-ttu-id="0ab5e-148">Configurando servidores front-end e pools de front-ends para o Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0ab5e-148">Setting up Front End Servers and Front End pools for Lync Server 2013</span></span>](lync-server-2013-setting-up-front-end-servers-and-front-end-pools.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

