---
title: Implantando espelhamento SQL para alta disponibilidade de Servidor Back-End
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Deploying SQL mirroring for Back End Server high availability
ms:assetid: 70224520-b5c8-4940-a08e-7fb9b1adde8d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204992(v=OCS.15)
ms:contentKeyID: 48184451
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8eb8c9647c24f326b1a2a51c99e7fa4ee5eafa23
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34829539"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deploying-sql-mirroring-for-back-end-server-high-availability-in-lync-server-2013"></a><span data-ttu-id="6545d-102">Implantando espelhamento SQL para alta disponibilidade de Servidor Back-End no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6545d-102">Deploying SQL mirroring for Back End Server high availability in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6545d-103">_**Tópico da última modificação:** 2014-01-08_</span><span class="sxs-lookup"><span data-stu-id="6545d-103">_**Topic Last Modified:** 2014-01-08_</span></span>

<span data-ttu-id="6545d-104">Para que seja possível implantar o espelhamento de SQL, os servidores devem executar no mínimo o SQL Server 2008 R2.</span><span class="sxs-lookup"><span data-stu-id="6545d-104">To be able to deploy SQL mirroring, your servers must run a minimum of SQL Server 2008 R2.</span></span> <span data-ttu-id="6545d-105">Essa versão deve ser executada em todos os servidores envolvidos: o principal, o espelho e a testemunha.</span><span class="sxs-lookup"><span data-stu-id="6545d-105">This version must run on all the involved servers: the primary, mirror, and the witness.</span></span> <span data-ttu-id="6545d-106">Para obter detalhes, [http://go.microsoft.com/fwlink/p/?linkid=3052\&kbid=2083921](http://go.microsoft.com/fwlink/p/?linkid=3052%26kbid=2083921)consulte.</span><span class="sxs-lookup"><span data-stu-id="6545d-106">For details, see [http://go.microsoft.com/fwlink/p/?linkid=3052\&kbid=2083921](http://go.microsoft.com/fwlink/p/?linkid=3052%26kbid=2083921).</span></span>

<span data-ttu-id="6545d-107">Em geral, a configuração do espelhamento SQL entre os dois Servidores Back-End com uma testemunha requer:</span><span class="sxs-lookup"><span data-stu-id="6545d-107">In general, setting up SQL mirroring between the two Back End Servers with a witness requires the following:</span></span>

  - <span data-ttu-id="6545d-108">Que a versão do SQL Server do servidor principal ofereça suporte a espelhamento SQL.</span><span class="sxs-lookup"><span data-stu-id="6545d-108">The primary server’s version of SQL Server must support SQL mirroring.</span></span>

  - <span data-ttu-id="6545d-109">Que o principal, o espelho e a testemunha (se implantada) tenham a mesma versão do SQL Server.</span><span class="sxs-lookup"><span data-stu-id="6545d-109">The primary, mirror, and the witness (if deployed) must have the same version of SQL Server.</span></span>

  - <span data-ttu-id="6545d-p102">Que o principal e o espelho tenham a mesma edição do SQL Server. A testemunha pode ter uma edição diferente.</span><span class="sxs-lookup"><span data-stu-id="6545d-p102">The primary and the mirror must have the same edition of SQL Server. The witness may have a different edition.</span></span>

<span data-ttu-id="6545d-112">Para as práticas recomendadas do SQL em termos de quais versões do SQL são compatíveis com uma função de testemunha, consulte "testemunha de espelhamento de [http://go.microsoft.com/fwlink/p/?LinkId=247345](http://go.microsoft.com/fwlink/p/?linkid=247345)banco de dados" na biblioteca MSDN em.</span><span class="sxs-lookup"><span data-stu-id="6545d-112">For SQL best practices in terms of what SQL versions are supported for a Witness role, see "Database Mirroring Witness" in the MSDN Library at [http://go.microsoft.com/fwlink/p/?LinkId=247345](http://go.microsoft.com/fwlink/p/?linkid=247345).</span></span>

<span data-ttu-id="6545d-113">Você usa o construtor de topologias para implantar o espelhamento do SQL.</span><span class="sxs-lookup"><span data-stu-id="6545d-113">You use Topology Builder to deploy SQL mirroring.</span></span> <span data-ttu-id="6545d-114">Você seleciona uma opção no construtor de topologias para espelhar os bancos de dados, e o construtor de topologias configura o espelhamento (incluindo a configuração de uma testemunha, se desejar) quando você publica a topologia.</span><span class="sxs-lookup"><span data-stu-id="6545d-114">You select an option in Topology Builder to mirror the databases, and Topology Builder sets up the mirroring (including setting up a witness, if you want) when you publish the topology.</span></span> <span data-ttu-id="6545d-115">Observe que a testemunha é configurada ou removida ao mesmo tempo que o espelho.</span><span class="sxs-lookup"><span data-stu-id="6545d-115">Note that you set up or remove the witness at the same time you set up or remove the mirror.</span></span> <span data-ttu-id="6545d-116">Não há um comando separado para implantar ou remover somente uma testemunha.</span><span class="sxs-lookup"><span data-stu-id="6545d-116">There is no separate command to deploy or remove only a witness.</span></span>

<span data-ttu-id="6545d-117">Antes de configurar o espelhamento do servidor, você deve configurar as permissões do banco de dados SQL corretamente.</span><span class="sxs-lookup"><span data-stu-id="6545d-117">To configure server mirroring, you must first set up SQL database permissions correctly.</span></span> <span data-ttu-id="6545d-118">Para obter detalhes, consulte "configurar contas de logon para o espelhamento de banco de dados ou grupos de disponibilidade AlwaysOn [http://go.microsoft.com/fwlink/p/?LinkId=268454](http://go.microsoft.com/fwlink/p/?linkid=268454)(SQL Server)" em.</span><span class="sxs-lookup"><span data-stu-id="6545d-118">For details, see "Set Up Login Accounts for Database Mirroring or AlwaysOn Availability Groups (SQL Server)" at [http://go.microsoft.com/fwlink/p/?LinkId=268454](http://go.microsoft.com/fwlink/p/?linkid=268454).</span></span>

<span data-ttu-id="6545d-p105">Com o espelhamento SQL, o modo de recuperação de banco de dados fica sempre definido como **Completo**, o que significa que você deve monitorar de perto o tamanho dos logs de transações, fazendo backup regular para evitar o esgotamento do espaço em disco dos Servidores Back-End. A frequência dos backups dos logs de transações depende da taxa de expansão dos logs, que, por sua vez, depende das transações do banco de dados provenientes de atividades de usuários no Pool de Front-Ends. Recomendamos que você determine a expansão dos logs de transação que é esperada para a carga de trabalho de implantação do Lync para que seja possível realizar um planejamento adequado. Os artigos a seguir fornecem mais informações sobre o gerenciamento de logs e backups do SQL:</span><span class="sxs-lookup"><span data-stu-id="6545d-p105">With SQL mirroring, database recovery mode is always set to **Full**, which means you must closely monitor transaction log size and back up transaction logs on a regular basis to avoid running out of disk space on the Back End Servers. The frequency of transaction log backups depends on the log growth rate, which in turn depends on database transactions incurred by user activities on the Front End pool. We recommend that you determine how much transaction log growth is expected for your Lync deployment workload so that you can do the planning accordingly. The following articles provide additional information on SQL backup and log management:</span></span>

  - <span data-ttu-id="6545d-123">Modelos de recuperação de banco de dados: "modelos de recuperação (SQL Server)" em[http://go.microsoft.com/fwlink/p/?LinkId=268446](http://go.microsoft.com/fwlink/p/?linkid=268446)</span><span class="sxs-lookup"><span data-stu-id="6545d-123">Database recovery models: "Recovery Models (SQL Server)" at [http://go.microsoft.com/fwlink/p/?LinkId=268446](http://go.microsoft.com/fwlink/p/?linkid=268446)</span></span>

  - <span data-ttu-id="6545d-124">Visão geral do backup: "visão geral do backup (SQL Server)" em[http://go.microsoft.com/fwlink/p/?LinkId=268449](http://go.microsoft.com/fwlink/p/?linkid=268449)</span><span class="sxs-lookup"><span data-stu-id="6545d-124">Backup overview: "Backup Overview (SQL Server)" at [http://go.microsoft.com/fwlink/p/?LinkId=268449](http://go.microsoft.com/fwlink/p/?linkid=268449)</span></span>

  - <span data-ttu-id="6545d-125">Log de transação de backup: "fazer backup de um log de transação (SQL Server)" em[http://go.microsoft.com/fwlink/p/?LinkId=268452](http://go.microsoft.com/fwlink/p/?linkid=268452)</span><span class="sxs-lookup"><span data-stu-id="6545d-125">Backup transaction log: "Backup a Transaction Log (SQL Server)" at [http://go.microsoft.com/fwlink/p/?LinkId=268452](http://go.microsoft.com/fwlink/p/?linkid=268452)</span></span>

<span data-ttu-id="6545d-126">Com o espelhamento de SQL, você pode configurar a topologia do espelhamento quando criar pools ou depois que eles forem criados.</span><span class="sxs-lookup"><span data-stu-id="6545d-126">With SQL mirroring, you can either configure the topology for mirroring when you create the pools, or after the pools are already created.</span></span>



> [!IMPORTANT]
> <span data-ttu-id="6545d-127">Usar o construtor de topologias ou cmdlets para configurar e remover o espelhamento do SQL só tem suporte quando os servidores primário, espelho e testemunha (se desejado) pertencem ao mesmo domínio.</span><span class="sxs-lookup"><span data-stu-id="6545d-127">Using Topology Builder or cmdlets to set up and remove SQL mirroring is supported only when the primary, mirror, and witness (if desired) servers all belong to the same domain.</span></span> <span data-ttu-id="6545d-128">Se quiser configurar o espelhamento SQL entre servidores de domínios diferentes, consulte a documentação do SQL Server.</span><span class="sxs-lookup"><span data-stu-id="6545d-128">If you want to set up SQL mirroring among servers in different domains, see your SQL Server documentation.</span></span>





> [!IMPORTANT]
> <span data-ttu-id="6545d-129">Sempre que fizer uma alteração em uma relação de espelhamento de banco de dados back-end, você deverá reiniciar todos os servidores front-end do pool. </span><span class="sxs-lookup"><span data-stu-id="6545d-129">Whenever you make a change to a Back End Database mirroring relationship, you must restart all the Front End Servers in the pool.</span></span><BR><span data-ttu-id="6545d-130">Para uma alteração no espelhamento, (como alterar a localização de um espelho), você deve usar o construtor de topologias para executar estas três etapas:</span><span class="sxs-lookup"><span data-stu-id="6545d-130">For a change in mirroring, (such as changing the location of a mirror), you must use Topology Builder to perform these three steps:</span></span> 
> <OL>
> <LI>
> <P><span data-ttu-id="6545d-131">Remova o espelhamento do servidor espelho antigo.</span><span class="sxs-lookup"><span data-stu-id="6545d-131">Remove mirroring from the old mirror server.</span></span></P>
> <LI>
> <P><span data-ttu-id="6545d-132">Adicione espelhamento ao novo servidor espelho.</span><span class="sxs-lookup"><span data-stu-id="6545d-132">Add mirroring to the new mirror server.</span></span></P>
> <LI>
> <P><span data-ttu-id="6545d-133">Publique a topologia.</span><span class="sxs-lookup"><span data-stu-id="6545d-133">Publish the topology.</span></span></P></LI></OL>




> [!NOTE]
> <span data-ttu-id="6545d-134">Um compartilhamento de arquivos deve ser criado para os arquivos espelho a serem gravados, e o serviço no qual o SQL Server e o SQL Agent estão sendo executados precisam de acesso de leitura/gravação.</span><span class="sxs-lookup"><span data-stu-id="6545d-134">A file share has to be created for the mirror files to be written to, and the service that SQL Server and SQL Agent are running under needs read/write access.</span></span> <span data-ttu-id="6545d-135">Se o serviço do SQL Server estiver sendo executado no contexto do serviço de rede, você &lt;poderá&gt; adicionar &lt;o domínio&#92;&gt;SqlServerName $ dos servidores principal e espelho do SQL às permissões de compartilhamento.</span><span class="sxs-lookup"><span data-stu-id="6545d-135">If the SQL Server service is running under the context of Network Service, you can add &lt;Domain&gt;&#92;&lt;SQLSERVERNAME&gt;$ of both the Principal and Mirror SQL Servers to the share permissions.</span></span> <span data-ttu-id="6545d-136">O $ é importante para identificar que esta é uma conta de computador.</span><span class="sxs-lookup"><span data-stu-id="6545d-136">The $ is important to identify that this is a computer account.</span></span>


<div>

## <a name="to-configure-sql-mirroring-while-creating-a-pool-in-topology-builder"></a><span data-ttu-id="6545d-137">Para configurar o espelhamento do SQL durante a criação de um pool no construtor de topologias</span><span class="sxs-lookup"><span data-stu-id="6545d-137">To configure SQL mirroring while creating a pool in Topology Builder</span></span>

1.  <span data-ttu-id="6545d-138">Na página **Definir o Repositório SQL**, clique em **Novo** ao lado da caixa **Repositório SQL**. </span><span class="sxs-lookup"><span data-stu-id="6545d-138">On the **Define the SQL Store** page, click **New** next to the **SQL store** box.</span></span>

2.  <span data-ttu-id="6545d-139">Na página **Definir Novo Repositório SQL**, especifique o repositório principal, selecione **Esta instância SQL está em relação de espelhamento**, especifique o número da porta de espelhamento de SQL (o padrão é 5022) e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="6545d-139">On the **Define new SQL Store** page, specify the primary store, select **This SQL instance is in mirroring relation**, specify the SQL mirroring port number (the default is 5022), and then click **OK**.</span></span>

3.  <span data-ttu-id="6545d-140">De volta à página **Definir o Repositório SQL**, selecione **Habilitar espelhamento do repositório SQL**. </span><span class="sxs-lookup"><span data-stu-id="6545d-140">Back on the **Define the SQL store** page, select **Enable SQL Store mirroring**.</span></span>

4.  <span data-ttu-id="6545d-p108">Na página **Definir Novo Repositório SQL**, especifique o repositório SQL a ser usado como espelho. Selecione **Esta instância SQL está em relação de espelhamento**, especifique o número da porta (o padrão é 5022) e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="6545d-p108">In the **Define new SQL Store** page, specify the SQL store to be used as the mirror. Select **This SQL instance is in mirroring relation**, specify the port number (the default is 5022), and then click **OK**.</span></span>

5.  <span data-ttu-id="6545d-143">Caso deseje uma testemunha para esse espelho, faça o seguinte: </span><span class="sxs-lookup"><span data-stu-id="6545d-143">If you want a witness for this mirror, do the following:</span></span>
    
    1.  <span data-ttu-id="6545d-144">Selecione **Usar testemunha de espelhamento do SQL para habilitar failover automático**. </span><span class="sxs-lookup"><span data-stu-id="6545d-144">Select **Use SQL mirroring witness to enable automatic failover**.</span></span>
    
    2.  <span data-ttu-id="6545d-145">Na página **Definir o repositório SQL**, selecione **Usar testemunha de espelhamento do SQL para habilitar failover automático** e especifique o repositório SQL a ser usado como testemunha. </span><span class="sxs-lookup"><span data-stu-id="6545d-145">In the **Define the SQL Store** page, select **Use SQL mirroring witness to enable automatic failover**, and specify the SQL store to be used as the witness.</span></span>
    
    3.  <span data-ttu-id="6545d-146">Especifique o número da porta (o padrão é 7022) e clique em **OK**. </span><span class="sxs-lookup"><span data-stu-id="6545d-146">Specify the port number (the default is 7022) and click **OK**.</span></span>

6.  <span data-ttu-id="6545d-147">Depois de definir o pool de front-end e todas as outras funções em sua topologia, use o construtor de topologias para publicar a topologia.</span><span class="sxs-lookup"><span data-stu-id="6545d-147">After you are done defining your Front End pool and all other roles in your topology, use Topology Builder to publish the topology.</span></span> <span data-ttu-id="6545d-148">Quando a topologia for publicada, se o pool de front-ends que hospeda o repositório de gerenciamento central tiver o SQL Mirroring habilitado, você verá uma opção para criar bancos de dados principais e espelho do SQL Store.</span><span class="sxs-lookup"><span data-stu-id="6545d-148">When the topology is published, if the Front End pool that hosts Central Management store has SQL mirroring enabled, you will see an option to create both primary and mirror SQL store databases.</span></span>
    
    <span data-ttu-id="6545d-149">Clique em **Configurações** e digite o caminho que será usado como compartilhamento de arquivos para o backup de espelhamento.</span><span class="sxs-lookup"><span data-stu-id="6545d-149">Click **Settings**, and type the path to use as the file share for the mirroring backup.</span></span>
    
    <span data-ttu-id="6545d-p110">Clique em **OK** e em **Avançar** para criar os bancos de dados e publicar a topologia. O espelhamento e a testemunha (se especificada) serão implantados.</span><span class="sxs-lookup"><span data-stu-id="6545d-p110">Click **OK** and then **Next** to create the databases and publish the topology. The mirroring and the witness (if specified) will be deployed.</span></span>

<span data-ttu-id="6545d-152">Você pode usar o construtor de topologias para editar as propriedades de um pool já existente para habilitar o espelhamento do SQL.</span><span class="sxs-lookup"><span data-stu-id="6545d-152">You can use Topology Builder to edit the properties of an already existing pool to enable SQL mirroring.</span></span>

</div>

<div>

## <a name="to-add-sql-mirroring-to-an-existing-front-end-pool-in-topology-builder"></a><span data-ttu-id="6545d-153">Para adicionar o espelhamento do SQL a um pool de front-ends existente no construtor de topologias</span><span class="sxs-lookup"><span data-stu-id="6545d-153">To add SQL mirroring to an existing Front End pool in Topology Builder</span></span>

1.  <span data-ttu-id="6545d-154">No construtor de topologias, clique com o botão direito do mouse no pool e clique em **Editar propriedades**.</span><span class="sxs-lookup"><span data-stu-id="6545d-154">In Topology Builder, right-click the pool and then click **Edit Properties**.</span></span>

2.  <span data-ttu-id="6545d-155">Selecione **Habilitar Espelhamento do Repositório SQL** e clique em **Novo** ao lado de **Repositório SQL de Espelhamento**. </span><span class="sxs-lookup"><span data-stu-id="6545d-155">Select **Enable SQL Store Mirroring**, and then click **New** next to **Mirroring SQL Store**.</span></span>

3.  <span data-ttu-id="6545d-156">Especifique o repositório SQL que você deseja usar como espelho. </span><span class="sxs-lookup"><span data-stu-id="6545d-156">Specify the SQL store that you want to use as the mirror.</span></span>

4.  <span data-ttu-id="6545d-157">Selecione **Esta instância SQL está em relação de espelhamento**, especifique o número da porta de espelhamento SQL (o padrão é 5022) e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="6545d-157">Select **This SQL instance is in mirroring relation**, specify the SQL mirroring port number the default port is 5022), and then click **OK**.</span></span>

5.  <span data-ttu-id="6545d-158">Caso deseje configurar uma testemunha, selecione **Usar testemunha de espelhamento SQL para habilitar failover automático** e clique em **Novo**. </span><span class="sxs-lookup"><span data-stu-id="6545d-158">If you want to configure a witness, select **Use SQL mirroring witness to enable automatic failover**, and click **New**.</span></span>

6.  <span data-ttu-id="6545d-159">Especifique o repositório SQL que você deseja usar como testemunha. </span><span class="sxs-lookup"><span data-stu-id="6545d-159">Specify the SQL store that you want to use as the witness.</span></span>

7.  <span data-ttu-id="6545d-160">Selecione **Esta instância SQL está em relação de espelhamento**, especifique o número da porta de espelhamento SQL (o padrão é 7022) e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="6545d-160">Select **This SQL instance is in mirroring relation**, specify the SQL mirroring port number (the default port is 7022), and then click **OK**.</span></span>

8.  <span data-ttu-id="6545d-161">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="6545d-161">Click **OK**.</span></span>

9.  <span data-ttu-id="6545d-p111">Publique a topologia. Quando você fizer isso, o sistema solicitará a instalação do banco de dados. </span><span class="sxs-lookup"><span data-stu-id="6545d-p111">Publish the topology. When you do so, you will be prompted to install the database.</span></span>
    
    <span data-ttu-id="6545d-p112">Durante o processo de publicação da topologia, você deverá definir um caminho de compartilhamento de arquivos. Os SQL Servers que participam do espelhamento devem ter acesso de leitura/gravação a esse compartilhamento de arquivos para que o espelhamento seja estabelecido.</span><span class="sxs-lookup"><span data-stu-id="6545d-p112">During the topology publishing process, you will be asked to define a file share path. The SQL Servers that participate in the mirroring must have read/write access to this file share for the mirror to be established.</span></span>

<span data-ttu-id="6545d-166">Instale o banco de dados antes de ir para o próximo procedimento.</span><span class="sxs-lookup"><span data-stu-id="6545d-166">You must then install the database before going on to the next procedure.</span></span>

<span data-ttu-id="6545d-167">Lembre-se disto ao configurar o espelhamento de SQL:</span><span class="sxs-lookup"><span data-stu-id="6545d-167">You should keep the following in mind when setting up SQL mirroring:</span></span>

  - <span data-ttu-id="6545d-168">Caso já exista um ponto de extremidade de espelhamento, ele será reutilizado usando as portas definidas nele e irá ignorar aquelas especificadas na topologia.</span><span class="sxs-lookup"><span data-stu-id="6545d-168">If a mirroring endpoint already exists, it will be reused using the ports defined there, and will ignore the ones you specify in the topology.</span></span>

  - <span data-ttu-id="6545d-p113">Todas as portas já alocadas para outros aplicativos no mesmo servidor (inclusive de outras instâncias SQL) não deverão ser usadas para as instâncias SQL instaladas atualmente. Isso significa que, se você tiver mais de uma instância SQL instalada no mesmo servidor, elas não poderão usar a mesma porta para espelhamento. Para saber mais, veja os seguintes artigos:</span><span class="sxs-lookup"><span data-stu-id="6545d-p113">Any port already allocated for other applications on the same server, including those for other SQL instances, should not be used for the installed SQL instances at hand. This implies that if you have more than one SQL instance installed on the same server, they must not use the same port for mirroring. For details, see the following articles:</span></span>
    
      - <span data-ttu-id="6545d-172">"Especifique um endereço de rede de servidor (espelhamento de banco de dados)" na biblioteca MSDN em[http://go.microsoft.com/fwlink/p/?LinkId=247346](http://go.microsoft.com/fwlink/p/?linkid=247346)</span><span class="sxs-lookup"><span data-stu-id="6545d-172">"Specify a Server Network Address (Database Mirroring)" in the MSDN Library at [http://go.microsoft.com/fwlink/p/?LinkId=247346](http://go.microsoft.com/fwlink/p/?linkid=247346)</span></span>
    
      - <span data-ttu-id="6545d-173">"O ponto de extremidade do espelhamento do banco de dados (SQL Server)" em[http://go.microsoft.com/fwlink/p/?LinkId=247347](http://go.microsoft.com/fwlink/p/?linkid=247347)</span><span class="sxs-lookup"><span data-stu-id="6545d-173">"The Database Mirroring Endpoint (SQL Server)" at [http://go.microsoft.com/fwlink/p/?LinkId=247347](http://go.microsoft.com/fwlink/p/?linkid=247347)</span></span>

</div>

<div>

## <a name="using-lync-server-management-shell-cmdlets-to-set-up-sql-mirroring"></a><span data-ttu-id="6545d-174">Usar cmdlets do Shell de gerenciamento do Lync Server para configurar o espelhamento do SQL</span><span class="sxs-lookup"><span data-stu-id="6545d-174">Using Lync Server Management Shell Cmdlets to Set Up SQL Mirroring</span></span>

<span data-ttu-id="6545d-175">A maneira mais fácil de configurar o espelhamento é usando o construtor de topologias, mas você também pode fazer isso usando cmdlets.</span><span class="sxs-lookup"><span data-stu-id="6545d-175">The easiest way to set up mirroring is by using Topology Builder, but you can also do so using cmdlets.</span></span>

1.  <span data-ttu-id="6545d-176">Abra uma janela do Shell de gerenciamento do Lync Server e execute o seguinte cmdlet:</span><span class="sxs-lookup"><span data-stu-id="6545d-176">Open a Lync Server Management Shell window and run the following cmdlet:</span></span>
    
        Install-CsMirrorDatabase [-ConfiguredDatabases] [-ForInstance] [-ForDefaultInstance] [-DatabaseType <Application | Archiving | CentralMgmt | Monitoring | User | BIStaging | PersistentChat | PersistentChatCompliance >] -FileShare <fileshare> -SqlServerFqdn <primarySqlserverFqdn> [-SqlInstanceName] [-DatabasePathMap] [-ExcludeDatabaseList] [-DropExistingDatabasesOnMirror] -Verbose 
    
    <span data-ttu-id="6545d-177">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="6545d-177">For example:</span></span>
    
        Install-CsMirrorDatabase -ConfiguredDatabases -FileShare \\PRIMARYBE\csdatabackup -SqlServerFqdn primaryBE.contoso.com -DropExistingDatabasesOnMirror -Verbose 
    
    <span data-ttu-id="6545d-178">Você verá:</span><span class="sxs-lookup"><span data-stu-id="6545d-178">You will see the following:</span></span>
    
        Database Name:rtcxds 
                Data File:D:\CsData\BackendStore\rtc\DbPath\rtcxds.mdf 
                 Log File:D:\CsData\BackendStore\rtc\LogPath\rtcxds.ldf 
              Primary SQL: e04-ocs.los_a.lsipt.local\rtc 
                  Account: LOS_A\e04-ocs$ 
               Mirror SQL: K16-ocs.los_a.lsipt.local\rtc 
                  Account: LOS_A\K16-ocs$ 
             Witness SQL : AB14-lct.los_a.lsipt.local\rtc 
                  Account: LOS_A\AB14-lct$ 
            Database Name:rtcshared 
                Data File:D:\CsData\BackendStore\rtc\DbPath\rtcshared.mdf 
                 Log File:D:\CsData\BackendStore\rtc\LogPath\rtcshared.ldf 
              Primary SQL: e04-ocs.los_a.lsipt.local\rtc 
                  Account: LOS_A\e04-ocs$ 
               Mirror SQL: K16-ocs.los_a.lsipt.local\rtc 
                  Account: LOS_A\K16-ocs$ 
             Witness SQL : AB14-lct.los_a.lsipt.local\rtc 
                  Account: LOS_A\AB14-lct$ 
            Database Name:rtcab 
                Data File:D:\CsData\ABSStore\rtc\DbPath\rtcab.mdf 
                 Log File:D:\CsData\ABSStore\rtc\LogPath\rtcab.ldf 
              Primary SQL: e04-ocs.los_a.lsipt.local\rtc 
                  Account: LOS_A\e04-ocs$ 
               Mirror SQL: K16-ocs.los_a.lsipt.local\rtc 
                  Account: LOS_A\K16-ocs$ 
             Witness SQL : AB14-lct.los_a.lsipt.local\rtc 
                  Account: LOS_A\AB14-lct$ 
            Database Name:rgsconfig 
                Data File:D:\CsData\ApplicationStore\rtc\DbPath\rgsconfig.mdf 
                 Log File:D:\CsData\ApplicationStore\rtc\LogPath\rgsconfig.ldf 
              Primary SQL: e04-ocs.los_a.lsipt.local\rtc 
                  Account: LOS_A\e04-ocs$ 
               Mirror SQL: K16-ocs.los_a.lsipt.local\rtc 
                  Account: LOS_A\K16-ocs$ 
             Witness SQL : AB14-lct.los_a.lsipt.local\rtc 
                  Account: LOS_A\AB14-lct$ 
            Database Name:rgsdyn 
                Data File:D:\CsData\ApplicationStore\rtc\DbPath\rgsdyn.mdf 
                 Log File:D:\CsData\ApplicationStore\rtc\LogPath\rgsdyn.ldf 
              Primary SQL: e04-ocs.los_a.lsipt.local\rtc 
                  Account: LOS_A\e04-ocs$ 
               Mirror SQL: K16-ocs.los_a.lsipt.local\rtc 
                  Account: LOS_A\K16-ocs$ 
             Witness SQL : AB14-lct.los_a.lsipt.local\rtc 
                  Account: LOS_A\AB14-lct$ 
            Database Name:cpsdyn 
                Data File:D:\CsData\ApplicationStore\rtc\DbPath\cpsdyn.mdf 
                 Log File:D:\CsData\ApplicationStore\rtc\LogPath\cpsdyn.ldf 
              Primary SQL: e04-ocs.los_a.lsipt.local\rtc 
                  Account: LOS_A\e04-ocs$ 
               Mirror SQL: K16-ocs.los_a.lsipt.local\rtc 
                  Account: LOS_A\K16-ocs$ 
             Witness SQL : AB14-lct.los_a.lsipt.local\rtc 
                  Account: LOS_A\AB14-lct$ 
            Database Name:xds 
                Data File:D:\CsData\CentralMgmtStore\rtc\DbPath\xds.mdf 
                 Log File:D:\CsData\CentralMgmtStore\rtc\LogPath\xds.ldf 
              Primary SQL: e04-ocs.los_a.lsipt.local\rtc 
                  Account: LOS_A\e04-ocs$ 
               Mirror SQL: K16-ocs.los_a.lsipt.local\rtc 
                  Account: LOS_A\K16-ocs$ 
             Witness SQL : AB14-lct.los_a.lsipt.local\rtc 
                  Account: LOS_A\AB14-lct$ 
            Database Name:lis 
                Data File:D:\CsData\CentralMgmtStore\rtc\DbPath\lis.mdf 
                 Log File:D:\CsData\CentralMgmtStore\rtc\LogPath\lis.ldf 
              Primary SQL: e04-ocs.los_a.lsipt.local\rtc 
                  Account: LOS_A\e04-ocs$ 
               Mirror SQL: K16-ocs.los_a.lsipt.local\rtc 
                  Account: LOS_A\K16-ocs$ 
             Witness SQL : AB14-lct.los_a.lsipt.local\rtc 
                  Account: LOS_A\AB14-lct$
        [Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend  [?] Help (default is "Y"): 

2.  <span data-ttu-id="6545d-179">Verifique se:</span><span class="sxs-lookup"><span data-stu-id="6545d-179">Verify the following:</span></span>
    
      - <span data-ttu-id="6545d-180">A porta 5022 pode ser acessada por meio do firewall se o Firewall do Windows estiver habilitado no\_RTC primário do SQL Server\\E04-OCS. los a. lsipt. RTC local.</span><span class="sxs-lookup"><span data-stu-id="6545d-180">Port 5022 is accessible through the firewall if Windows Firewall is enabled in the primary SQL Server e04-ocs.los\_a.lsipt.local\\rtc.</span></span>
    
      - <span data-ttu-id="6545d-181">A porta 5022 pode ser acessada por meio do firewall se o Firewall do Windows estiver habilitado no\_RTC do SQL Server K16-OCS\\. los a. lsipt. local.</span><span class="sxs-lookup"><span data-stu-id="6545d-181">Port 5022 is accessible through the firewall if Windows Firewall is enabled in the mirror SQL Server K16-ocs.los\_a.lsipt.local\\rtc.</span></span>
    
      - <span data-ttu-id="6545d-182">A porta 7022 pode ser acessada por meio do firewall se o Firewall do Windows estiver habilitado no\_RTC do SQL Server AB14-LCT\\. los a. lsipt. RTC local.</span><span class="sxs-lookup"><span data-stu-id="6545d-182">Port 7022 is accessible through the firewall if Windows Firewall is enabled in the witness SQL Server AB14-lct.los\_a.lsipt.local\\rtc.</span></span>
    
      - <span data-ttu-id="6545d-183">As contas que executam os servidores SQL em todos os servidores SQL primários e espelhados têm permissão de \\ \\leitura/gravação\\para o compartilhamento de arquivos E04-OCS csdatabackup</span><span class="sxs-lookup"><span data-stu-id="6545d-183">Accounts running the SQL Servers on all primary and mirror SQL servers have read/write permission to the file share \\\\E04-OCS\\csdatabackup</span></span>
    
      - <span data-ttu-id="6545d-p114">Verifique se o provedor WMI (Instrumentação de Gerenciamento do Windows) está em execução em todos esses servidores. O cmdlet usa esse provedor para encontrar informações da conta relativas aos serviços do SQL Server em execução em todos os servidores principais, espelho e testemunha. </span><span class="sxs-lookup"><span data-stu-id="6545d-p114">Verify that the Windows Management Instrumentation (WMI) provider is running on all these servers. The cmdlet uses this provider to find the account information for SQL Server services running on all primary, mirror and witness servers.</span></span>
    
      - <span data-ttu-id="6545d-186">Verifique se a conta que executa esse cmdlet tem permissão para criar as pastas de dados e de arquivos de log para todos os servidores espelho. </span><span class="sxs-lookup"><span data-stu-id="6545d-186">Verify that the account running this cmdlet has permission to create the folders for the data and log files for all the mirror servers.</span></span>
    
      - <span data-ttu-id="6545d-p115">Observe que a conta de usuário usada pela instância SQL para execução deve ter permissão de leitura/gravação no compartilhamento de arquivos. Se o compartilhamento de arquivos estiver em um servidor diferente e a instância SQL for executada em uma conta do sistema local, você deverá conceder permissões de compartilhamento de arquivos ao servidor que hospeda a instância SQL.</span><span class="sxs-lookup"><span data-stu-id="6545d-p115">Note that the user account that the SQL instance uses to run must have read/write permission to the file share. If the file share is on a different server, and the SQL instance runs a local system account, you must grant file share permissions to the server that hosts the SQL instance.</span></span>

3.  <span data-ttu-id="6545d-189">Digite A e pressione ENTER.</span><span class="sxs-lookup"><span data-stu-id="6545d-189">Type A and press ENTER.</span></span>
    
    <span data-ttu-id="6545d-190">O espelhamento será configurado.</span><span class="sxs-lookup"><span data-stu-id="6545d-190">The mirroring will be configured.</span></span>

<span data-ttu-id="6545d-191">**Install-CsMirrorDatabase** instala o espelhamento e configura o espelhamento para todos os bancos de dados que estão presentes no repositório SQL principal.</span><span class="sxs-lookup"><span data-stu-id="6545d-191">**Install-CsMirrorDatabase** installs the mirror and configures mirroring for all the databases that are present on the primary SQL store.</span></span> <span data-ttu-id="6545d-192">Se você quiser configurar o espelhamento somente para bancos de dados específicos, poderá usar a opção – DatabaseType ou se quiser configurar o espelhamento para todos os bancos de dados, exceto para alguns, você pode usar a opção-ExcludeDatabaseList, juntamente com uma lista de banco de dados separada por vírgulas nomes a serem excluídos.</span><span class="sxs-lookup"><span data-stu-id="6545d-192">If you want to configure mirroring for only specific databases, you can use the –DatabaseType option, or if you want to configure mirroring for all databases except for a few, you can use the -ExcludeDatabaseList option, along with a comma-separated list of database names to exclude.</span></span>

<span data-ttu-id="6545d-193">Por exemplo, caso você adicione a opção a seguir a **Install-CsMirrorDatabase**, todos os bancos de dados serão espelhados, com exceção de rtcab e rtcxds.</span><span class="sxs-lookup"><span data-stu-id="6545d-193">For example, if you add the following option to **Install-CsMirrorDatabase**, all databases except rtcab and rtcxds will be mirrored.</span></span>

`-ExcludeDatabaseList rtcab,rtcxds`

<span data-ttu-id="6545d-194">Por exemplo, caso você adicione a opção a seguir a **Install-CsMirrorDatabase**, somente os bancos de dados rtcab, rtcshared e rtcxds serão espelhados.</span><span class="sxs-lookup"><span data-stu-id="6545d-194">For example, if you add the following option to **Install-CsMirrorDatabase**, only the rtcab, rtcshared, and rtcxds databases will be mirrored.</span></span>

`-DatabaseType User`

</div>

<div>

## <a name="removing-or-changing-sql-mirroring"></a><span data-ttu-id="6545d-195">Remoção ou alteração do espelhamento SQL</span><span class="sxs-lookup"><span data-stu-id="6545d-195">Removing or Changing SQL Mirroring</span></span>

<span data-ttu-id="6545d-p117">Para remover o espelhamento de SQL de um pool no Construtor de Topologias, primeiro use um cmdlet para remover o espelho no SQL Server. Em seguida, você poderá usar o Construtor de Topologias para remover o espelho da topologia. Para remover o espelho no SQL Server, use o cmdlet a seguir:</span><span class="sxs-lookup"><span data-stu-id="6545d-p117">To remove the SQL mirroring of a pool in Topology Builder, you must first use a cmdlet to remove the mirror in SQL Server. You can then use Topology Builder to remove the mirror from the topology. To remove the mirror in SQL Server, use the following cmdlet:</span></span>

    Uninstall-CsMirrorDatabase -SqlServerFqdn <SQLServer FQDN> [-SqlInstanceName <SQLServer instance name>] -DatabaseType <Application | Archiving | CentralMgmt | Monitoring | User | BIStaging | PersistentChat | PersistentChatCompliance> [-DropExistingDatabasesOnMirror] [-Verbose]

<span data-ttu-id="6545d-199">Por exemplo, para remover o espelhamento e os bancos de dados de usuários, digite:</span><span class="sxs-lookup"><span data-stu-id="6545d-199">For example, to remove mirroring and drop the databases for the User databases, type the following:</span></span>

    Uninstall-CsMirrorDatabase -SqlServerFqdn primaryBE.contoso.com -SqlInstanceName rtc -Verbose -DatabaseType User -DropExistingDatabasesOnMirror

<span data-ttu-id="6545d-200">A `-DropExistingDatabasesOnMirror` opção faz com que os bancos de dados afetados sejam excluídos do espelho.</span><span class="sxs-lookup"><span data-stu-id="6545d-200">The `-DropExistingDatabasesOnMirror` option causes the affected databases to be deleted from the mirror.</span></span>

<span data-ttu-id="6545d-201">Depois, para remover o espelho da topologia, faça o seguinte:</span><span class="sxs-lookup"><span data-stu-id="6545d-201">Then, to remove the mirror from the topology, do the following:</span></span>

1.  <span data-ttu-id="6545d-202">No Construtor de Topologias, clique com o botão direito do mouse no pool e clique em **Editar Propriedades**.</span><span class="sxs-lookup"><span data-stu-id="6545d-202">In Topology Builder, right-click the pool and click **Edit Properties**.</span></span>

2.  <span data-ttu-id="6545d-203">Desmarque **Habilitar Espelhamento do Repositório SQL** e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="6545d-203">Uncheck **Enable SQL Store Mirroring** and click **OK**.</span></span>

3.  <span data-ttu-id="6545d-204">Publique a topologia.</span><span class="sxs-lookup"><span data-stu-id="6545d-204">Publish the topology.</span></span>

</div>

<div>

## <a name="removing-a-mirroring-witness"></a><span data-ttu-id="6545d-205">Remoção de uma testemunha de espelhamento</span><span class="sxs-lookup"><span data-stu-id="6545d-205">Removing a Mirroring Witness</span></span>

<span data-ttu-id="6545d-206">Use esse procedimento se você precisar remover a testemunha de uma configuração de espelhamento de servidor back-end.</span><span class="sxs-lookup"><span data-stu-id="6545d-206">Use this procedure if you need to remove the witness from a Back End Server mirroring configuration.</span></span>

1.  <span data-ttu-id="6545d-207">No Construtor de Topologias, clique com o botão direito do mouse no pool e clique em **Editar Propriedades**.</span><span class="sxs-lookup"><span data-stu-id="6545d-207">In Topology Builder, right-click the pool and click **Edit Properties**.</span></span>

2.  <span data-ttu-id="6545d-208">Desmarque **Usar testemunha de espelhamento do SQL Server para habilitar failover automático** e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="6545d-208">Uncheck **Use SQL Server mirroring witness to enable automatic failover** and click **OK**.</span></span>

3.  <span data-ttu-id="6545d-209">Publique a topologia.</span><span class="sxs-lookup"><span data-stu-id="6545d-209">Publish the topology.</span></span>
    
    <span data-ttu-id="6545d-210">Depois de publicar a topologia, o construtor de topologias será exibida uma mensagem que inclui os seguintes</span><span class="sxs-lookup"><span data-stu-id="6545d-210">After publishing the topology, Topology Builder you will see a message that includes the following</span></span>
    
        Run the Uninstall-CsMirrorDatabase cmdlet to remove databases that are paired with following primary databases.
    
    <span data-ttu-id="6545d-211">No entanto, não siga essa etapa e não digite `Uninstall-CsMirrorDatabase` como isso desinstalaria toda a configuração de espelhamento.</span><span class="sxs-lookup"><span data-stu-id="6545d-211">However, do not follow that step, and do not type `Uninstall-CsMirrorDatabase` as that would uninstall the entire mirroring configuration.</span></span>

4.  <span data-ttu-id="6545d-212">Para remover apenas a testemunha da configuração do SQL Server, siga as instruções em "remover a testemunha de uma sessão de espelhamento de banco de dados (SQL [http://go.microsoft.com/fwlink/p/?LinkId=268456](http://go.microsoft.com/fwlink/p/?linkid=268456)Server)" em.</span><span class="sxs-lookup"><span data-stu-id="6545d-212">To remove just the witness from the SQL Server configuration, follow the instructions in "Remove the Witness from a Database Mirroring Session (SQL Server)" at [http://go.microsoft.com/fwlink/p/?LinkId=268456](http://go.microsoft.com/fwlink/p/?linkid=268456).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

