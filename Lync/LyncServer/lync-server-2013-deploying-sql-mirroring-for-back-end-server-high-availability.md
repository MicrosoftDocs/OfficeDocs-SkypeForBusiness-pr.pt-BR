---
title: Implantando o espelhamento SQL para alta disponibilidade do servidor back-end
description: Implantação de espelhamento SQL para alta disponibilidade de servidor back-end.
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deploying SQL mirroring for Back End Server high availability
ms:assetid: 70224520-b5c8-4940-a08e-7fb9b1adde8d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204992(v=OCS.15)
ms:contentKeyID: 48184451
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4a2ab2d598249c12231668a888b442f830c5d65f
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48565997"
---
# <a name="deploying-sql-mirroring-for-back-end-server-high-availability-in-lync-server-2013"></a><span data-ttu-id="62328-103">Implantando o espelhamento SQL para alta disponibilidade do servidor back-end no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="62328-103">Deploying SQL mirroring for Back End Server high availability in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="62328-104">_**Última modificação do tópico:** 2014-01-08_</span><span class="sxs-lookup"><span data-stu-id="62328-104">_**Topic Last Modified:** 2014-01-08_</span></span>

<span data-ttu-id="62328-105">Para que seja possível implantar o espelhamento SQL, os servidores devem executar no mínimo o SQL Server 2008 R2.</span><span class="sxs-lookup"><span data-stu-id="62328-105">To be able to deploy SQL mirroring, your servers must run a minimum of SQL Server 2008 R2.</span></span> <span data-ttu-id="62328-106">Essa versão deve ser executada em todos os servidores envolvidos: principal, espelho e testemunha.</span><span class="sxs-lookup"><span data-stu-id="62328-106">This version must run on all the involved servers: the primary, mirror, and the witness.</span></span> <span data-ttu-id="62328-107">Para obter detalhes, consulte [https://go.microsoft.com/fwlink/p/?linkid=3052\&kbid=2083921](https://go.microsoft.com/fwlink/p/?linkid=3052%26kbid=2083921) .</span><span class="sxs-lookup"><span data-stu-id="62328-107">For details, see [https://go.microsoft.com/fwlink/p/?linkid=3052\&kbid=2083921](https://go.microsoft.com/fwlink/p/?linkid=3052%26kbid=2083921).</span></span>

<span data-ttu-id="62328-108">Em geral, a configuração do espelhamento SQL entre os dois servidores back-end com uma testemunha requer:</span><span class="sxs-lookup"><span data-stu-id="62328-108">In general, setting up SQL mirroring between the two Back End Servers with a witness requires the following:</span></span>

  - <span data-ttu-id="62328-109">Que a versão do SQL Server do servidor principal ofereça suporte a espelhamento SQL.</span><span class="sxs-lookup"><span data-stu-id="62328-109">The primary server’s version of SQL Server must support SQL mirroring.</span></span>

  - <span data-ttu-id="62328-110">Que o principal, o espelho e a testemunha (se implantada) tenham a mesma versão do SQL Server.</span><span class="sxs-lookup"><span data-stu-id="62328-110">The primary, mirror, and the witness (if deployed) must have the same version of SQL Server.</span></span>

  - <span data-ttu-id="62328-p102">Que o principal e o espelho tenham a mesma edição do SQL Server. A testemunha pode ter uma edição diferente.</span><span class="sxs-lookup"><span data-stu-id="62328-p102">The primary and the mirror must have the same edition of SQL Server. The witness may have a different edition.</span></span>

<span data-ttu-id="62328-113">Para práticas recomendadas de SQL em termos de quais versões SQL são compatíveis com uma função testemunha, consulte "testemunha de espelhamento de banco de dados" na biblioteca MSDN em [https://go.microsoft.com/fwlink/p/?LinkId=247345](https://go.microsoft.com/fwlink/p/?linkid=247345) .</span><span class="sxs-lookup"><span data-stu-id="62328-113">For SQL best practices in terms of what SQL versions are supported for a Witness role, see "Database Mirroring Witness" in the MSDN Library at [https://go.microsoft.com/fwlink/p/?LinkId=247345](https://go.microsoft.com/fwlink/p/?linkid=247345).</span></span>

<span data-ttu-id="62328-114">Você usa o construtor de topologias para implantar o espelhamento do SQL.</span><span class="sxs-lookup"><span data-stu-id="62328-114">You use Topology Builder to deploy SQL mirroring.</span></span> <span data-ttu-id="62328-115">Você seleciona uma opção no construtor de topologias para espelhar os bancos de dados e o construtor de topologias configura o espelhamento (incluindo a configuração de uma testemunha, se você quiser) ao publicar a topologia.</span><span class="sxs-lookup"><span data-stu-id="62328-115">You select an option in Topology Builder to mirror the databases, and Topology Builder sets up the mirroring (including setting up a witness, if you want) when you publish the topology.</span></span> <span data-ttu-id="62328-116">Observe que a testemunha é configurada ou removida ao mesmo tempo que o espelho.</span><span class="sxs-lookup"><span data-stu-id="62328-116">Note that you set up or remove the witness at the same time you set up or remove the mirror.</span></span> <span data-ttu-id="62328-117">Não há um comando separado para implantar ou remover somente a testemunha.</span><span class="sxs-lookup"><span data-stu-id="62328-117">There is no separate command to deploy or remove only a witness.</span></span>

<span data-ttu-id="62328-118">Para configurar o espelhamento do servidor, primeiro você deve configurar as permissões do banco de dados SQL corretamente.</span><span class="sxs-lookup"><span data-stu-id="62328-118">To configure server mirroring, you must first set up SQL database permissions correctly.</span></span> <span data-ttu-id="62328-119">Para obter detalhes, consulte "configurar contas de logon para espelhamento de banco de dados ou grupos de disponibilidade AlwaysOn (SQL Server)" em [https://go.microsoft.com/fwlink/p/?LinkId=268454](https://go.microsoft.com/fwlink/p/?linkid=268454) .</span><span class="sxs-lookup"><span data-stu-id="62328-119">For details, see "Set Up Login Accounts for Database Mirroring or AlwaysOn Availability Groups (SQL Server)" at [https://go.microsoft.com/fwlink/p/?LinkId=268454](https://go.microsoft.com/fwlink/p/?linkid=268454).</span></span>

<span data-ttu-id="62328-p105">Com o espelhamento SQL, o modo de recuperação de banco de dados fica sempre definido como **Completo**, o que significa que você deve monitorar de perto o tamanho dos logs de transações, fazendo backup regular deles para evitar o esgotamento do espaço em disco dos servidores back-end. A frequência dos backups dos logs de transações depende da taxa de expansão dos logs, que, por sua vez, depende das transações do banco de dados provenientes de atividades de usuários no pool front-end. Recomendamos que você determine a expansão dos logs de transação esperada para a carga de trabalho de implantação do Lync, de modo que seja possível realizar um planejamento adequado. Os artigos a seguir fornecem mais informações sobre o gerenciamento de logs e backups do SQL:</span><span class="sxs-lookup"><span data-stu-id="62328-p105">With SQL mirroring, database recovery mode is always set to **Full**, which means you must closely monitor transaction log size and back up transaction logs on a regular basis to avoid running out of disk space on the Back End Servers. The frequency of transaction log backups depends on the log growth rate, which in turn depends on database transactions incurred by user activities on the Front End pool. We recommend that you determine how much transaction log growth is expected for your Lync deployment workload so that you can do the planning accordingly. The following articles provide additional information on SQL backup and log management:</span></span>

  - <span data-ttu-id="62328-124">Modelos de recuperação de banco de dados: "modelos de recuperação (SQL Server)" em [https://go.microsoft.com/fwlink/p/?LinkId=268446](https://go.microsoft.com/fwlink/p/?linkid=268446)</span><span class="sxs-lookup"><span data-stu-id="62328-124">Database recovery models: "Recovery Models (SQL Server)" at [https://go.microsoft.com/fwlink/p/?LinkId=268446](https://go.microsoft.com/fwlink/p/?linkid=268446)</span></span>

  - <span data-ttu-id="62328-125">Visão geral do backup: "visão geral do backup (SQL Server)" em [https://go.microsoft.com/fwlink/p/?LinkId=268449](https://go.microsoft.com/fwlink/p/?linkid=268449)</span><span class="sxs-lookup"><span data-stu-id="62328-125">Backup overview: "Backup Overview (SQL Server)" at [https://go.microsoft.com/fwlink/p/?LinkId=268449](https://go.microsoft.com/fwlink/p/?linkid=268449)</span></span>

  - <span data-ttu-id="62328-126">Log de transações de backup: "fazer backup de um log de transações (SQL Server)" em [https://go.microsoft.com/fwlink/p/?LinkId=268452](https://go.microsoft.com/fwlink/p/?linkid=268452)</span><span class="sxs-lookup"><span data-stu-id="62328-126">Backup transaction log: "Backup a Transaction Log (SQL Server)" at [https://go.microsoft.com/fwlink/p/?LinkId=268452](https://go.microsoft.com/fwlink/p/?linkid=268452)</span></span>

<span data-ttu-id="62328-127">Com o espelhamento SQL, você pode configurar a topologia do espelhamento no momento da criação dos pools ou após isso.</span><span class="sxs-lookup"><span data-stu-id="62328-127">With SQL mirroring, you can either configure the topology for mirroring when you create the pools, or after the pools are already created.</span></span>



> [!IMPORTANT]
> <span data-ttu-id="62328-128">O uso do construtor de topologias ou cmdlets para configurar e remover o espelhamento de SQL é suportado somente quando os servidores primário, espelho e testemunha (se desejado) pertencem ao mesmo domínio.</span><span class="sxs-lookup"><span data-stu-id="62328-128">Using Topology Builder or cmdlets to set up and remove SQL mirroring is supported only when the primary, mirror, and witness (if desired) servers all belong to the same domain.</span></span> <span data-ttu-id="62328-129">Caso deseje configurar o espelhamento SQL entre servidores de domínios diferentes, consulte a documentação do SQL Server.</span><span class="sxs-lookup"><span data-stu-id="62328-129">If you want to set up SQL mirroring among servers in different domains, see your SQL Server documentation.</span></span>





> [!IMPORTANT]
> <span data-ttu-id="62328-130">Sempre que fizer uma alteração em um relacionamento de espelhamento de banco de dados back-end, você deverá reiniciar todos os servidores front-end do pool.</span><span class="sxs-lookup"><span data-stu-id="62328-130">Whenever you make a change to a Back End Database mirroring relationship, you must restart all the Front End Servers in the pool.</span></span><BR><span data-ttu-id="62328-131">Para uma alteração no espelhamento (como alterar o local de um espelho), você deve usar o construtor de topologias para executar estas três etapas:</span><span class="sxs-lookup"><span data-stu-id="62328-131">For a change in mirroring, (such as changing the location of a mirror), you must use Topology Builder to perform these three steps:</span></span> 
> <OL>
> <LI>
> <P><span data-ttu-id="62328-132">Remova o espelhamento do servidor espelho antigo.</span><span class="sxs-lookup"><span data-stu-id="62328-132">Remove mirroring from the old mirror server.</span></span></P>
> <LI>
> <P><span data-ttu-id="62328-133">Adicione espelhamento ao novo servidor espelho.</span><span class="sxs-lookup"><span data-stu-id="62328-133">Add mirroring to the new mirror server.</span></span></P>
> <LI>
> <P><span data-ttu-id="62328-134">Publique a topologia.</span><span class="sxs-lookup"><span data-stu-id="62328-134">Publish the topology.</span></span></P></LI></OL>




> [!NOTE]
> <span data-ttu-id="62328-135">Um compartilhamento de arquivos deve ser criado para que os arquivos espelhados sejam gravados e o serviço que o SQL Server e o SQL Agent estão executando em precisa de acesso de leitura/gravação.</span><span class="sxs-lookup"><span data-stu-id="62328-135">A file share has to be created for the mirror files to be written to, and the service that SQL Server and SQL Agent are running under needs read/write access.</span></span> <span data-ttu-id="62328-136">Se o serviço do SQL Server estiver sendo executado no contexto do serviço de rede, você poderá adicionar &lt; &gt; o domínio&#92;&lt; SqlServerName &gt; $ dos servidores SQL principal e espelho às permissões de compartilhamento.</span><span class="sxs-lookup"><span data-stu-id="62328-136">If the SQL Server service is running under the context of Network Service, you can add &lt;Domain&gt;&#92;&lt;SQLSERVERNAME&gt;$ of both the Principal and Mirror SQL Servers to the share permissions.</span></span> <span data-ttu-id="62328-137">$ É importante identificar que esta é uma conta de computador.</span><span class="sxs-lookup"><span data-stu-id="62328-137">The $ is important to identify that this is a computer account.</span></span>


<div>

## <a name="to-configure-sql-mirroring-while-creating-a-pool-in-topology-builder"></a><span data-ttu-id="62328-138">Para configurar o espelhamento do SQL durante a criação de um pool no construtor de topologia</span><span class="sxs-lookup"><span data-stu-id="62328-138">To configure SQL mirroring while creating a pool in Topology Builder</span></span>

1.  <span data-ttu-id="62328-139">Na página **Definir o Repositório do SQL**, clique em **Novo** ao lado da caixa **Repositório do SQL**.</span><span class="sxs-lookup"><span data-stu-id="62328-139">On the **Define the SQL Store** page, click **New** next to the **SQL store** box.</span></span>

2.  <span data-ttu-id="62328-140">Na página **Definir Novo Repositório do SQL**, especifique o repositório principal, selecione **Esta instância SQL está em relação de espelhamento**, especifique o número da porta de espelhamento SQL (o padrão é 5022) e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="62328-140">On the **Define new SQL Store** page, specify the primary store, select **This SQL instance is in mirroring relation**, specify the SQL mirroring port number (the default is 5022), and then click **OK**.</span></span>

3.  <span data-ttu-id="62328-141">De volta à página **Definir o Repositório do SQL**, selecione **Habilitar Espelhamento do Repositório do SQL**.</span><span class="sxs-lookup"><span data-stu-id="62328-141">Back on the **Define the SQL store** page, select **Enable SQL Store mirroring**.</span></span>

4.  <span data-ttu-id="62328-p108">Na página **Definir Novo Repositório do SQL**, especifique o repositório do SQL a ser usado como espelho, selecione **Esta instância SQL está em relação de espelhamento**, especifique o número da porta de espelhamento SQL (o padrão é 5022) e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="62328-p108">In the **Define new SQL Store** page, specify the SQL store to be used as the mirror. Select **This SQL instance is in mirroring relation**, specify the port number (the default is 5022), and then click **OK**.</span></span>

5.  <span data-ttu-id="62328-144">Caso deseje uma testemunha para este espelho, faça o seguinte:</span><span class="sxs-lookup"><span data-stu-id="62328-144">If you want a witness for this mirror, do the following:</span></span>
    
    1.  <span data-ttu-id="62328-145">Selecione **Usar testemunha de espelhamento do SQL para habilitar failover automático**.</span><span class="sxs-lookup"><span data-stu-id="62328-145">Select **Use SQL mirroring witness to enable automatic failover**.</span></span>
    
    2.  <span data-ttu-id="62328-146">Na página **Definir o Repositório do SQL**, selecione **Usar testemunha de espelhamento do SQL para habilitar failover automático** e especifique o repositório do SQL a ser usado como testemunha.</span><span class="sxs-lookup"><span data-stu-id="62328-146">In the **Define the SQL Store** page, select **Use SQL mirroring witness to enable automatic failover**, and specify the SQL store to be used as the witness.</span></span>
    
    3.  <span data-ttu-id="62328-147">Especifique o número da porta (o padrão é 7022) e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="62328-147">Specify the port number (the default is 7022) and click **OK**.</span></span>

6.  <span data-ttu-id="62328-148">Após concluir a definição do pool de front-ends e de todas as outras funções em sua topologia, use o construtor de topologias para publicar a topologia.</span><span class="sxs-lookup"><span data-stu-id="62328-148">After you are done defining your Front End pool and all other roles in your topology, use Topology Builder to publish the topology.</span></span> <span data-ttu-id="62328-149">Quando a topologia for publicada, se o pool de front-ends que hospeda o repositório de gerenciamento central tiver o espelhamento de SQL habilitado, você verá uma opção para criar os bancos de dados principais e espelho do SQL Store.</span><span class="sxs-lookup"><span data-stu-id="62328-149">When the topology is published, if the Front End pool that hosts Central Management store has SQL mirroring enabled, you will see an option to create both primary and mirror SQL store databases.</span></span>
    
    <span data-ttu-id="62328-150">Clique em **Configurações** e digite o caminho que será usado como compartilhamento de arquivos para o backup de espelhamento.</span><span class="sxs-lookup"><span data-stu-id="62328-150">Click **Settings**, and type the path to use as the file share for the mirroring backup.</span></span>
    
    <span data-ttu-id="62328-p110">Clique em **OK** e em **Avançar** para criar os bancos de dados e publicar a topologia. O espelhamento e a testemunha (se especificada) serão implantados.</span><span class="sxs-lookup"><span data-stu-id="62328-p110">Click **OK** and then **Next** to create the databases and publish the topology. The mirroring and the witness (if specified) will be deployed.</span></span>

<span data-ttu-id="62328-153">Você pode usar o construtor de topologias para editar as propriedades de um pool já existente a fim de habilitar o espelhamento de SQL.</span><span class="sxs-lookup"><span data-stu-id="62328-153">You can use Topology Builder to edit the properties of an already existing pool to enable SQL mirroring.</span></span>

</div>

<div>

## <a name="to-add-sql-mirroring-to-an-existing-front-end-pool-in-topology-builder"></a><span data-ttu-id="62328-154">Para adicionar o espelhamento de SQL a um pool de front-ends existente no construtor de topologia</span><span class="sxs-lookup"><span data-stu-id="62328-154">To add SQL mirroring to an existing Front End pool in Topology Builder</span></span>

1.  <span data-ttu-id="62328-155">No construtor de topologias, clique com o botão direito do mouse no pool e clique em **Editar propriedades**.</span><span class="sxs-lookup"><span data-stu-id="62328-155">In Topology Builder, right-click the pool and then click **Edit Properties**.</span></span>

2.  <span data-ttu-id="62328-156">Selecione **Habilitar Espelhamento do Repositório do SQL** e clique em **Novo** ao lado de **Repositório do SQL de Espelhamento**.</span><span class="sxs-lookup"><span data-stu-id="62328-156">Select **Enable SQL Store Mirroring**, and then click **New** next to **Mirroring SQL Store**.</span></span>

3.  <span data-ttu-id="62328-157">Especifique o repositório do SQL que deseja usar como espelho.</span><span class="sxs-lookup"><span data-stu-id="62328-157">Specify the SQL store that you want to use as the mirror.</span></span>

4.  <span data-ttu-id="62328-158">Selecione **Esta instância SQL está em relação de espelhamento**, especifique o número da porta de espelhamento (o padrão é 5022) e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="62328-158">Select **This SQL instance is in mirroring relation**, specify the SQL mirroring port number the default port is 5022), and then click **OK**.</span></span>

5.  <span data-ttu-id="62328-159">Caso deseje configurar uma testemunha, selecione **Usar testemunha de espelhamento do SQL para habilitar failover automático** e clique em **Novo**.</span><span class="sxs-lookup"><span data-stu-id="62328-159">If you want to configure a witness, select **Use SQL mirroring witness to enable automatic failover**, and click **New**.</span></span>

6.  <span data-ttu-id="62328-160">Especifique o repositório do SQL que deseja usar como testemunha.</span><span class="sxs-lookup"><span data-stu-id="62328-160">Specify the SQL store that you want to use as the witness.</span></span>

7.  <span data-ttu-id="62328-161">Selecione **Esta instância SQL está em relação de espelhamento**, especifique o número da porta de espelhamento (o padrão é 7022) e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="62328-161">Select **This SQL instance is in mirroring relation**, specify the SQL mirroring port number (the default port is 7022), and then click **OK**.</span></span>

8.  <span data-ttu-id="62328-162">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="62328-162">Click **OK**.</span></span>

9.  <span data-ttu-id="62328-p111">Publique a topologia. Quando você fizer isso, o sistema solicitará a instalação do banco de dados.</span><span class="sxs-lookup"><span data-stu-id="62328-p111">Publish the topology. When you do so, you will be prompted to install the database.</span></span>
    
    <span data-ttu-id="62328-165">Durante o processo de publicação da topologia, você será solicitado a definir um caminho de compartilhamento de arquivos.</span><span class="sxs-lookup"><span data-stu-id="62328-165">During the topology publishing process, you will be asked to define a file share path.</span></span> <span data-ttu-id="62328-166">Os servidores SQL que participam do espelhamento devem ter acesso de leitura/gravação a esse compartilhamento de arquivos para que o espelho seja estabelecido.</span><span class="sxs-lookup"><span data-stu-id="62328-166">The SQL Servers that participate in the mirroring must have read/write access to this file share for the mirror to be established.</span></span>

<span data-ttu-id="62328-167">Instale o banco de dados antes de ir para o próximo procedimento.</span><span class="sxs-lookup"><span data-stu-id="62328-167">You must then install the database before going on to the next procedure.</span></span>

<span data-ttu-id="62328-168">Lembre-se disto ao configurar o espelhamento SQL:</span><span class="sxs-lookup"><span data-stu-id="62328-168">You should keep the following in mind when setting up SQL mirroring:</span></span>

  - <span data-ttu-id="62328-169">Caso já exista um ponto de extremidade de espelhamento, ele será reutilizado usando as portas definidas nele e irá ignorar aquelas especificadas na topologia.</span><span class="sxs-lookup"><span data-stu-id="62328-169">If a mirroring endpoint already exists, it will be reused using the ports defined there, and will ignore the ones you specify in the topology.</span></span>

  - <span data-ttu-id="62328-p113">Todas as portas já alocadas a outros aplicativos no mesmo servidor (inclusive de outras instâncias do SQL) não serão usadas com as instâncias do SQL instaladas atualmente. Isso significa que, se você tiver mais de uma instância do SQL instalada no mesmo servidor, elas não poderão usar a mesma porta para espalhamento. Para obter detalhes, consulte os seguintes artigos:</span><span class="sxs-lookup"><span data-stu-id="62328-p113">Any port already allocated for other applications on the same server, including those for other SQL instances, should not be used for the installed SQL instances at hand. This implies that if you have more than one SQL instance installed on the same server, they must not use the same port for mirroring. For details, see the following articles:</span></span>
    
      - <span data-ttu-id="62328-173">"Especificar um endereço de rede do servidor (espelhamento de banco de dados)" na biblioteca MSDN em [https://go.microsoft.com/fwlink/p/?LinkId=247346](https://go.microsoft.com/fwlink/p/?linkid=247346)</span><span class="sxs-lookup"><span data-stu-id="62328-173">"Specify a Server Network Address (Database Mirroring)" in the MSDN Library at [https://go.microsoft.com/fwlink/p/?LinkId=247346](https://go.microsoft.com/fwlink/p/?linkid=247346)</span></span>
    
      - <span data-ttu-id="62328-174">"O ponto de extremidade de espelhamento de banco de dados (SQL Server)" em [https://go.microsoft.com/fwlink/p/?LinkId=247347](https://go.microsoft.com/fwlink/p/?linkid=247347)</span><span class="sxs-lookup"><span data-stu-id="62328-174">"The Database Mirroring Endpoint (SQL Server)" at [https://go.microsoft.com/fwlink/p/?LinkId=247347](https://go.microsoft.com/fwlink/p/?linkid=247347)</span></span>

</div>

<div>

## <a name="using-lync-server-management-shell-cmdlets-to-set-up-sql-mirroring"></a><span data-ttu-id="62328-175">Usando os cmdlets do Shell de gerenciamento do Lync Server para configurar o espelhamento do SQL</span><span class="sxs-lookup"><span data-stu-id="62328-175">Using Lync Server Management Shell Cmdlets to Set Up SQL Mirroring</span></span>

<span data-ttu-id="62328-176">A maneira mais fácil de configurar o espelhamento é usar o construtor de topologias, mas você também pode fazer isso usando cmdlets.</span><span class="sxs-lookup"><span data-stu-id="62328-176">The easiest way to set up mirroring is by using Topology Builder, but you can also do so using cmdlets.</span></span>

1.  <span data-ttu-id="62328-177">Abra uma janela do Shell de gerenciamento do Lync Server e execute o seguinte cmdlet:</span><span class="sxs-lookup"><span data-stu-id="62328-177">Open a Lync Server Management Shell window and run the following cmdlet:</span></span>
    
        Install-CsMirrorDatabase [-ConfiguredDatabases] [-ForInstance] [-ForDefaultInstance] [-DatabaseType <Application | Archiving | CentralMgmt | Monitoring | User | BIStaging | PersistentChat | PersistentChatCompliance >] -FileShare <fileshare> -SqlServerFqdn <primarySqlserverFqdn> [-SqlInstanceName] [-DatabasePathMap] [-ExcludeDatabaseList] [-DropExistingDatabasesOnMirror] -Verbose 
    
    <span data-ttu-id="62328-178">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="62328-178">For example:</span></span>
    
        Install-CsMirrorDatabase -ConfiguredDatabases -FileShare \\PRIMARYBE\csdatabackup -SqlServerFqdn primaryBE.contoso.com -DropExistingDatabasesOnMirror -Verbose 
    
    <span data-ttu-id="62328-179">Você verá:</span><span class="sxs-lookup"><span data-stu-id="62328-179">You will see the following:</span></span>
    
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

2.  <span data-ttu-id="62328-180">Verifique se:</span><span class="sxs-lookup"><span data-stu-id="62328-180">Verify the following:</span></span>
    
      - <span data-ttu-id="62328-181">A porta 5022 pode ser acessada por meio do firewall se o Firewall do Windows estiver habilitado no principal E04 do SQL Server. \_ lsipt. \\</span><span class="sxs-lookup"><span data-stu-id="62328-181">Port 5022 is accessible through the firewall if Windows Firewall is enabled in the primary SQL Server e04-ocs.los\_a.lsipt.local\\rtc.</span></span>
    
      - <span data-ttu-id="62328-182">A porta 5022 pode ser acessada por meio do firewall se o Firewall do Windows estiver habilitado no RTC do SQL Server espelho K16. los \_ a. lsipt. \\</span><span class="sxs-lookup"><span data-stu-id="62328-182">Port 5022 is accessible through the firewall if Windows Firewall is enabled in the mirror SQL Server K16-ocs.los\_a.lsipt.local\\rtc.</span></span>
    
      - <span data-ttu-id="62328-183">A porta 7022 pode ser acessada por meio do firewall se o Firewall do Windows estiver habilitado no RTC do SQL Server ab14. los \_ a. lsipt. \\</span><span class="sxs-lookup"><span data-stu-id="62328-183">Port 7022 is accessible through the firewall if Windows Firewall is enabled in the witness SQL Server AB14-lct.los\_a.lsipt.local\\rtc.</span></span>
    
      - <span data-ttu-id="62328-184">As contas que executam os SQL Servers em todos os servidores SQL principais e espelhados têm permissão de leitura/gravação para o compartilhamento de arquivos \\ \\ E04-OCS \\ csdatabackup</span><span class="sxs-lookup"><span data-stu-id="62328-184">Accounts running the SQL Servers on all primary and mirror SQL servers have read/write permission to the file share \\\\E04-OCS\\csdatabackup</span></span>
    
      - <span data-ttu-id="62328-p114">Verifique se o provedor WMI (Instrumentação de Gerenciamento do Windows) está em execução em todos esses servidores. O cmdlet usa esse provedor para encontrar informações da conta relativas aos serviços do SQL Server em execução em todos os servidores principais, espelho e testemunha.</span><span class="sxs-lookup"><span data-stu-id="62328-p114">Verify that the Windows Management Instrumentation (WMI) provider is running on all these servers. The cmdlet uses this provider to find the account information for SQL Server services running on all primary, mirror and witness servers.</span></span>
    
      - <span data-ttu-id="62328-187">Verifique se a conta que executa esse cmdlet tem permissão de criação das pastas dos dados e arquivos de log para todos os servidores espelho.</span><span class="sxs-lookup"><span data-stu-id="62328-187">Verify that the account running this cmdlet has permission to create the folders for the data and log files for all the mirror servers.</span></span>
    
      - <span data-ttu-id="62328-p115">Observe que a conta de usuário usada pela instância do SQL para execução deve ter permissão de leitura/gravação do compartilhamento de arquivos. Se o compartilhamento de arquivos estiver em um servidor diferente e a instância do SQL for executada em uma conta do sistema local, você deverá conceder permissões de compartilhamento de arquivos ao servidor que hospeda a instância do SQL.</span><span class="sxs-lookup"><span data-stu-id="62328-p115">Note that the user account that the SQL instance uses to run must have read/write permission to the file share. If the file share is on a different server, and the SQL instance runs a local system account, you must grant file share permissions to the server that hosts the SQL instance.</span></span>

3.  <span data-ttu-id="62328-190">Digite A e pressione ENTER.</span><span class="sxs-lookup"><span data-stu-id="62328-190">Type A and press ENTER.</span></span>
    
    <span data-ttu-id="62328-191">O espelhamento será configurado.</span><span class="sxs-lookup"><span data-stu-id="62328-191">The mirroring will be configured.</span></span>

<span data-ttu-id="62328-192">**Install-CsMirrorDatabase** instala o espelho e configura o espelhamento para todos os bancos de dados que estão presentes no repositório SQL principal.</span><span class="sxs-lookup"><span data-stu-id="62328-192">**Install-CsMirrorDatabase** installs the mirror and configures mirroring for all the databases that are present on the primary SQL store.</span></span> <span data-ttu-id="62328-193">Se quiser configurar o espelhamento somente para bancos de dados específicos, você pode usar a opção – DatabaseType ou se quiser configurar o espelhamento para todos os bancos de dados, exceto alguns, você pode usar a opção-ExcludeDatabaseList, juntamente com uma lista separada por vírgulas de nomes de banco de dados a serem excluídos.</span><span class="sxs-lookup"><span data-stu-id="62328-193">If you want to configure mirroring for only specific databases, you can use the –DatabaseType option, or if you want to configure mirroring for all databases except for a few, you can use the -ExcludeDatabaseList option, along with a comma-separated list of database names to exclude.</span></span>

<span data-ttu-id="62328-194">Por exemplo, caso adicione a opção a seguir a **Install-CsMirrorDatabase**, todos os bancos de dados serão espelhados, com exceção de rtcab e rtcxds.</span><span class="sxs-lookup"><span data-stu-id="62328-194">For example, if you add the following option to **Install-CsMirrorDatabase**, all databases except rtcab and rtcxds will be mirrored.</span></span>

`-ExcludeDatabaseList rtcab,rtcxds`

<span data-ttu-id="62328-195">Por exemplo, caso adicione a opção a seguir a **Install-CsMirrorDatabase**, somente os bancos de dados rtcab, rtcshared e rtcxds databases serão espelhados.</span><span class="sxs-lookup"><span data-stu-id="62328-195">For example, if you add the following option to **Install-CsMirrorDatabase**, only the rtcab, rtcshared, and rtcxds databases will be mirrored.</span></span>

`-DatabaseType User`

</div>

<div>

## <a name="removing-or-changing-sql-mirroring"></a><span data-ttu-id="62328-196">Removendo ou alterando o espelhamento SQL</span><span class="sxs-lookup"><span data-stu-id="62328-196">Removing or Changing SQL Mirroring</span></span>

<span data-ttu-id="62328-p117">Para remover o espelhamento SQL de um pool no Construtor de Topologias, primeiro use um cmdlet para remover o espelho no SQL Server. Em seguida, você poderá usar o Construtor de Topologias para remover o espelho da topologia. Para remover o espelho no SQL Server, use o cmdlet a seguir:</span><span class="sxs-lookup"><span data-stu-id="62328-p117">To remove the SQL mirroring of a pool in Topology Builder, you must first use a cmdlet to remove the mirror in SQL Server. You can then use Topology Builder to remove the mirror from the topology. To remove the mirror in SQL Server, use the following cmdlet:</span></span>

    Uninstall-CsMirrorDatabase -SqlServerFqdn <SQLServer FQDN> [-SqlInstanceName <SQLServer instance name>] -DatabaseType <Application | Archiving | CentralMgmt | Monitoring | User | BIStaging | PersistentChat | PersistentChatCompliance> [-DropExistingDatabasesOnMirror] [-Verbose]

<span data-ttu-id="62328-200">Por exemplo, para remover o espelhamento e descartar os bancos de dados de usuários, digite:</span><span class="sxs-lookup"><span data-stu-id="62328-200">For example, to remove mirroring and drop the databases for the User databases, type the following:</span></span>

    Uninstall-CsMirrorDatabase -SqlServerFqdn primaryBE.contoso.com -SqlInstanceName rtc -Verbose -DatabaseType User -DropExistingDatabasesOnMirror

<span data-ttu-id="62328-201">A `-DropExistingDatabasesOnMirror` opção faz com que os bancos de dados afetados sejam excluídos do espelho.</span><span class="sxs-lookup"><span data-stu-id="62328-201">The `-DropExistingDatabasesOnMirror` option causes the affected databases to be deleted from the mirror.</span></span>

<span data-ttu-id="62328-202">Em seguida, para remover o espelho da topologia, faça o seguinte:</span><span class="sxs-lookup"><span data-stu-id="62328-202">Then, to remove the mirror from the topology, do the following:</span></span>

1.  <span data-ttu-id="62328-203">No Construtor de Topologias, clique com o botão direito do mouse no pool e em **Editar Propriedades**</span><span class="sxs-lookup"><span data-stu-id="62328-203">In Topology Builder, right-click the pool and click **Edit Properties**.</span></span>

2.  <span data-ttu-id="62328-204">Desmarque **Habilitar Espelhamento do Repositório do SQL** e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="62328-204">Uncheck **Enable SQL Store Mirroring** and click **OK**.</span></span>

3.  <span data-ttu-id="62328-205">Publique a topologia.</span><span class="sxs-lookup"><span data-stu-id="62328-205">Publish the topology.</span></span>

</div>

<div>

## <a name="removing-a-mirroring-witness"></a><span data-ttu-id="62328-206">Removendo a testemunha de espelhamento</span><span class="sxs-lookup"><span data-stu-id="62328-206">Removing a Mirroring Witness</span></span>

<span data-ttu-id="62328-207">Use este procedimento se você precisar remover a testemunha de uma configuração de espelhamento de servidor back-end.</span><span class="sxs-lookup"><span data-stu-id="62328-207">Use this procedure if you need to remove the witness from a Back End Server mirroring configuration.</span></span>

1.  <span data-ttu-id="62328-208">No Construtor de Topologias, clique com o botão direito do mouse no pool e em **Editar Propriedades**</span><span class="sxs-lookup"><span data-stu-id="62328-208">In Topology Builder, right-click the pool and click **Edit Properties**.</span></span>

2.  <span data-ttu-id="62328-209">Desmarque **Usar testemunha de espelhamento do SQL Server para habilitar failover automático** e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="62328-209">Uncheck **Use SQL Server mirroring witness to enable automatic failover** and click **OK**.</span></span>

3.  <span data-ttu-id="62328-210">Publique a topologia.</span><span class="sxs-lookup"><span data-stu-id="62328-210">Publish the topology.</span></span>
    
    <span data-ttu-id="62328-211">Após publicar a topologia, o construtor de topologias você verá uma mensagem que inclui o seguinte</span><span class="sxs-lookup"><span data-stu-id="62328-211">After publishing the topology, Topology Builder you will see a message that includes the following</span></span>
    
        Run the Uninstall-CsMirrorDatabase cmdlet to remove databases that are paired with following primary databases.
    
    <span data-ttu-id="62328-212">No entanto, não siga essa etapa e não digite, `Uninstall-CsMirrorDatabase` pois isso desinstalará toda a configuração de espelhamento.</span><span class="sxs-lookup"><span data-stu-id="62328-212">However, do not follow that step, and do not type `Uninstall-CsMirrorDatabase` as that would uninstall the entire mirroring configuration.</span></span>

4.  <span data-ttu-id="62328-213">Para remover apenas a testemunha da configuração do SQL Server, siga as instruções em "remover a testemunha de uma sessão de espelhamento de banco de dados (SQL Server)" em [https://go.microsoft.com/fwlink/p/?LinkId=268456](https://go.microsoft.com/fwlink/p/?linkid=268456) .</span><span class="sxs-lookup"><span data-stu-id="62328-213">To remove just the witness from the SQL Server configuration, follow the instructions in "Remove the Witness from a Database Mirroring Session (SQL Server)" at [https://go.microsoft.com/fwlink/p/?LinkId=268456](https://go.microsoft.com/fwlink/p/?linkid=268456).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

