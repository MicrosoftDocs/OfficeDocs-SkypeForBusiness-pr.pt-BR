---
title: Implantar espelhamento de SQL para alta disponibilidade do servidor back-end no Skype for Business Server 2015
ms.reviewer: ''
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 70224520-b5c8-4940-a08e-7fb9b1adde8d
description: 'Para que seja possível implantar o espelhamento de SQL, os servidores devem executar no mínimo o SQL Server 2008 R2. Essa versão deve ser executada em todos os servidores envolvidos: o principal, o espelho e a testemunha. Para obter detalhes, consulte cumulativa 9 do pacote de atualização para SQL Server 2008 Service Pack 1.'
ms.openlocfilehash: ebf1d222bff572100fe7824e52acdef2ff85216d
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/27/2019
ms.locfileid: "30886272"
---
# <a name="deploy-sql-mirroring-for-back-end-server-high-availability-in-skype-for-business-server-2015"></a><span data-ttu-id="2fad9-105">Implantar o espelhamento do SQL para servidor Back-End alta disponibilidade em Skype para Business server 2015</span><span class="sxs-lookup"><span data-stu-id="2fad9-105">Deploy SQL mirroring for Back End Server high availability in Skype for Business server 2015</span></span>


<span data-ttu-id="2fad9-106">Para que seja possível implantar o espelhamento de SQL, os servidores devem executar no mínimo o SQL Server 2008 R2.</span><span class="sxs-lookup"><span data-stu-id="2fad9-106">To be able to deploy SQL mirroring, your servers must run a minimum of SQL Server 2008 R2.</span></span> <span data-ttu-id="2fad9-107">Essa versão deve ser executada em todos os servidores envolvidos: o principal, o espelho e a testemunha.</span><span class="sxs-lookup"><span data-stu-id="2fad9-107">This version must run on all the involved servers: the primary, mirror, and the witness.</span></span> <span data-ttu-id="2fad9-108">Para obter detalhes, consulte [cumulativa 9 para SQL Server 2008 Service Pack 1 do pacote de atualização ](https://go.microsoft.com/fwlink/p/?linkid=3052&amp;kbid=2083921).</span><span class="sxs-lookup"><span data-stu-id="2fad9-108">For details, see [Cumulative update package 9 for SQL Server 2008 Service Pack 1 ](https://go.microsoft.com/fwlink/p/?linkid=3052&amp;kbid=2083921).</span></span>

<span data-ttu-id="2fad9-109">Em geral, a configuração do espelhamento SQL entre os dois Servidores Back-End com uma testemunha requer:</span><span class="sxs-lookup"><span data-stu-id="2fad9-109">In general, setting up SQL mirroring between the two Back End Servers with a witness requires the following:</span></span>

- <span data-ttu-id="2fad9-110">Versão do servidor principal do SQL Server deve oferecer suporte a espelhamento SQL.</span><span class="sxs-lookup"><span data-stu-id="2fad9-110">The primary server's version of SQL Server must support SQL mirroring.</span></span>

- <span data-ttu-id="2fad9-111">Que o principal, o espelho e a testemunha (se implantada) tenham a mesma versão do SQL Server.</span><span class="sxs-lookup"><span data-stu-id="2fad9-111">The primary, mirror, and the witness (if deployed) must have the same version of SQL Server.</span></span>

- <span data-ttu-id="2fad9-p103">Que o principal e o espelho tenham a mesma edição do SQL Server. A testemunha pode ter uma edição diferente.</span><span class="sxs-lookup"><span data-stu-id="2fad9-p103">The primary and the mirror must have the same edition of SQL Server. The witness may have a different edition.</span></span>

<span data-ttu-id="2fad9-114">Para as práticas recomendadas do SQL em termos de quais versões do SQL são suportadas para uma função de testemunha, consulte [A testemunha de espelhamento de banco de dados](https://go.microsoft.com/fwlink/p/?LinkId=247345).</span><span class="sxs-lookup"><span data-stu-id="2fad9-114">For SQL best practices in terms of what SQL versions are supported for a Witness role, see [Database Mirroring Witness](https://go.microsoft.com/fwlink/p/?LinkId=247345).</span></span>

<span data-ttu-id="2fad9-115">Use o construtor de topologias para implantar o espelhamento SQL.</span><span class="sxs-lookup"><span data-stu-id="2fad9-115">You use Topology Builder to deploy SQL mirroring.</span></span> <span data-ttu-id="2fad9-116">Selecione uma opção no construtor de topologias para fazer o espelhamento de bancos de dados e o construtor de topologias configura o espelhamento (inclusive configurar uma testemunha, se desejar) quando você publica a topologia.</span><span class="sxs-lookup"><span data-stu-id="2fad9-116">You select an option in Topology Builder to mirror the databases, and Topology Builder sets up the mirroring (including setting up a witness, if you want) when you publish the topology.</span></span> <span data-ttu-id="2fad9-117">Observe que a testemunha é configurada ou removida ao mesmo tempo que o espelho.</span><span class="sxs-lookup"><span data-stu-id="2fad9-117">Note that you set up or remove the witness at the same time you set up or remove the mirror.</span></span> <span data-ttu-id="2fad9-118">Não há um comando separado para implantar ou remover somente uma testemunha.</span><span class="sxs-lookup"><span data-stu-id="2fad9-118">There is no separate command to deploy or remove only a witness.</span></span>

<span data-ttu-id="2fad9-119">Antes de configurar o espelhamento do servidor, você deve configurar as permissões do banco de dados SQL corretamente.</span><span class="sxs-lookup"><span data-stu-id="2fad9-119">To configure server mirroring, you must first set up SQL database permissions correctly.</span></span> <span data-ttu-id="2fad9-120">Para obter detalhes, consulte [Definir backup contas de logon para o espelhamento de banco de dados ou grupos de disponibilidade AlwaysOn (SQL Server)](https://go.microsoft.com/fwlink/p/?LinkId=268454).</span><span class="sxs-lookup"><span data-stu-id="2fad9-120">For details, see [Set Up Login Accounts for Database Mirroring or AlwaysOn Availability Groups (SQL Server)](https://go.microsoft.com/fwlink/p/?LinkId=268454).</span></span>

<span data-ttu-id="2fad9-p106">Com o espelhamento de SQL, o modo de recuperação de banco de dados fica sempre definido como **Completo**, o que significa que você deve monitorar de perto o tamanho dos logs de transações e fazer backups regulares para evitar o esgotamento do espaço em disco dos Servidores Back-End. A frequência de backups de logs de transações depende da taxa de crescimento dos logs, que, por sua vez, depende das transações do banco de dados provenientes de atividades de usuários no pool de front-ends. Recomendamos que você determine o nível esperado de crescimento dos logs de transação para a carga de trabalho da implantação, para que seja possível realizar um planejamento adequado. Os artigos a seguir fornecem mais informações sobre o gerenciamento de logs e backups de SQL:</span><span class="sxs-lookup"><span data-stu-id="2fad9-p106">With SQL mirroring, database recovery mode is always set to **Full**, which means you must closely monitor transaction log size and back up transaction logs on a regular basis to avoid running out of disk space on the Back End Servers. The frequency of transaction log backups depends on the log growth rate, which in turn depends on database transactions incurred by user activities on the Front End pool. We recommend that you determine how much transaction log growth is expected for your deployment workload so that you can do the planning accordingly. The following articles provide additional information on SQL backup and log management:</span></span>

- [<span data-ttu-id="2fad9-125">Modelos de recuperação de banco de dados</span><span class="sxs-lookup"><span data-stu-id="2fad9-125">Database recovery models</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=268446)

- [<span data-ttu-id="2fad9-126">Visão geral de backup</span><span class="sxs-lookup"><span data-stu-id="2fad9-126">Backup overview</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=268449)

- [<span data-ttu-id="2fad9-127">Log de transações de backup</span><span class="sxs-lookup"><span data-stu-id="2fad9-127">Backup transaction log</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=268452)

<span data-ttu-id="2fad9-128">Com o espelhamento de SQL, você pode configurar a topologia do espelhamento quando criar pools ou depois que eles forem criados.</span><span class="sxs-lookup"><span data-stu-id="2fad9-128">With SQL mirroring, you can either configure the topology for mirroring when you create the pools, or after the pools are already created.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="2fad9-129">Usando o construtor de topologia ou cmdlets para configurar e remover SQL espelhamento é aceito somente quando o principal, espelho e servidores de testemunha (se desejar) pertencem ao mesmo domínio.</span><span class="sxs-lookup"><span data-stu-id="2fad9-129">Using Topology Builder or cmdlets to set up and remove SQL mirroring is supported only when the primary, mirror, and witness (if desired) servers all belong to the same domain.</span></span> <span data-ttu-id="2fad9-130">Se quiser configurar o espelhamento SQL entre servidores de domínios diferentes, consulte a documentação do SQL Server.</span><span class="sxs-lookup"><span data-stu-id="2fad9-130">If you want to set up SQL mirroring among servers in different domains, see your SQL Server documentation.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="2fad9-131">Sempre que fizer uma alteração em uma relação de espelhamento de banco de dados back-end, você deverá reiniciar todos os servidores front-end do pool. </span><span class="sxs-lookup"><span data-stu-id="2fad9-131">Whenever you make a change to a Back End Database mirroring relationship, you must restart all the Front End Servers in the pool.</span></span> <span data-ttu-id="2fad9-132">gt _ para uma alteração de espelhamento, (por exemplo, alterando o local de um espelho), você deve usar o construtor de topologias para executar estas três etapas:</span><span class="sxs-lookup"><span data-stu-id="2fad9-132">> For a change in mirroring, (such as changing the location of a mirror), you must use Topology Builder to perform these three steps:</span></span>

1. <span data-ttu-id="2fad9-133">Remova o espelhamento do servidor espelho antigo.</span><span class="sxs-lookup"><span data-stu-id="2fad9-133">Remove mirroring from the old mirror server.</span></span>

2. <span data-ttu-id="2fad9-134">Adicione espelhamento ao novo servidor espelho.</span><span class="sxs-lookup"><span data-stu-id="2fad9-134">Add mirroring to the new mirror server.</span></span>

3. <span data-ttu-id="2fad9-135">Publique a topologia.</span><span class="sxs-lookup"><span data-stu-id="2fad9-135">Publish the topology.</span></span>

> [!NOTE]
> <span data-ttu-id="2fad9-136">Um compartilhamento de arquivos deve ser criado para os arquivos espelho a serem gravados, e o serviço no qual o SQL Server e o SQL Agent estão sendo executados precisam de acesso de leitura/gravação.</span><span class="sxs-lookup"><span data-stu-id="2fad9-136">A file share has to be created for the mirror files to be written to, and the service that SQL Server and SQL Agent are running under needs read/write access.</span></span> <span data-ttu-id="2fad9-137">Se o serviço SQL Server está sendo executado em contexto de serviço de rede, você pode adicionar \<domínio\>\\<SQLSERVERNAME\>$ do Principal e espelho SQL Servers para as permissões de compartilhamento.</span><span class="sxs-lookup"><span data-stu-id="2fad9-137">If the SQL Server service is running under the context of Network Service, you can add \<Domain\>\\<SQLSERVERNAME\>$ of both the Principal and Mirror SQL Servers to the share permissions.</span></span> <span data-ttu-id="2fad9-138">O $ é importante para identificar que esta é uma conta de computador.</span><span class="sxs-lookup"><span data-stu-id="2fad9-138">The $ is important to identify that this is a computer account.</span></span>

## <a name="to-configure-sql-mirroring-while-creating-a-pool-in-topology-builder"></a><span data-ttu-id="2fad9-139">Para configurar o espelhamento SQL durante a criação de um pool no construtor de topologia</span><span class="sxs-lookup"><span data-stu-id="2fad9-139">To configure SQL mirroring while creating a pool in Topology Builder</span></span>

1. <span data-ttu-id="2fad9-140">Na página **Definir o Repositório SQL**, clique em **Novo** ao lado da caixa **Repositório SQL**. </span><span class="sxs-lookup"><span data-stu-id="2fad9-140">On the **Define the SQL Store** page, click **New** next to the **SQL store** box.</span></span>

2. <span data-ttu-id="2fad9-141">Na página **Definir Novo Repositório SQL**, especifique o repositório principal, selecione **Esta instância SQL está em relação de espelhamento**, especifique o número da porta de espelhamento de SQL (o padrão é 5022) e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="2fad9-141">On the **Define new SQL Store** page, specify the primary store, select **This SQL instance is in mirroring relation**, specify the SQL mirroring port number (the default is 5022), and then click **OK**.</span></span>

3. <span data-ttu-id="2fad9-142">De volta à página **Definir o Repositório SQL**, selecione **Habilitar espelhamento do repositório SQL**. </span><span class="sxs-lookup"><span data-stu-id="2fad9-142">Back on the **Define the SQL store** page, select **Enable SQL Store mirroring**.</span></span>

4. <span data-ttu-id="2fad9-p110">Na página **Definir Novo Repositório SQL**, especifique o repositório SQL a ser usado como espelho. Selecione **Esta instância SQL está em relação de espelhamento**, especifique o número da porta (o padrão é 5022) e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="2fad9-p110">In the **Define new SQL Store** page, specify the SQL store to be used as the mirror. Select **This SQL instance is in mirroring relation**, specify the port number (the default is 5022), and then click **OK**.</span></span>

5. <span data-ttu-id="2fad9-145">Caso deseje uma testemunha para esse espelho, faça o seguinte: </span><span class="sxs-lookup"><span data-stu-id="2fad9-145">If you want a witness for this mirror, do the following:</span></span>

    <span data-ttu-id="2fad9-146">a.</span><span class="sxs-lookup"><span data-stu-id="2fad9-146">a.</span></span> <span data-ttu-id="2fad9-147">Selecione **Usar testemunha de espelhamento do SQL para habilitar failover automático**. </span><span class="sxs-lookup"><span data-stu-id="2fad9-147">Select **Use SQL mirroring witness to enable automatic failover**.</span></span>

    <span data-ttu-id="2fad9-148">b.</span><span class="sxs-lookup"><span data-stu-id="2fad9-148">b.</span></span> <span data-ttu-id="2fad9-149">Na página **Definir o repositório SQL**, selecione **Usar testemunha de espelhamento do SQL para habilitar failover automático** e especifique o repositório SQL a ser usado como testemunha. </span><span class="sxs-lookup"><span data-stu-id="2fad9-149">In the **Define the SQL Store** page, select **Use SQL mirroring witness to enable automatic failover**, and specify the SQL store to be used as the witness.</span></span>

    <span data-ttu-id="2fad9-150">c.</span><span class="sxs-lookup"><span data-stu-id="2fad9-150">c.</span></span> <span data-ttu-id="2fad9-151">Especifique o número da porta (o padrão é 7022) e clique em **OK**. </span><span class="sxs-lookup"><span data-stu-id="2fad9-151">Specify the port number (the default is 7022) and click **OK**.</span></span>

6. <span data-ttu-id="2fad9-152">Depois de terminar a definição de seu pool de Front-End e todas as outras funções em sua topologia, use o construtor de topologias para publicar a topologia.</span><span class="sxs-lookup"><span data-stu-id="2fad9-152">After you are done defining your Front End pool and all other roles in your topology, use Topology Builder to publish the topology.</span></span> <span data-ttu-id="2fad9-153">Quando a topologia é publicada, se o pool de Front-End que hospeda o repositório de gerenciamento Central tiver habilitado de espelhamento do SQL, você verá uma opção para criar os dois primário e espelhar bancos de dados de repositório SQL.</span><span class="sxs-lookup"><span data-stu-id="2fad9-153">When the topology is published, if the Front End pool that hosts Central Management store has SQL mirroring enabled, you will see an option to create both primary and mirror SQL store databases.</span></span>

    <span data-ttu-id="2fad9-154">Clique em **Configurações** e digite o caminho que será usado como compartilhamento de arquivos para o backup de espelhamento.</span><span class="sxs-lookup"><span data-stu-id="2fad9-154">Click **Settings**, and type the path to use as the file share for the mirroring backup.</span></span>

    <span data-ttu-id="2fad9-p115">Clique em **OK** e em **Avançar** para criar os bancos de dados e publicar a topologia. O espelhamento e a testemunha (se especificada) serão implantados.</span><span class="sxs-lookup"><span data-stu-id="2fad9-p115">Click **OK** and then **Next** to create the databases and publish the topology. The mirroring and the witness (if specified) will be deployed.</span></span>

<span data-ttu-id="2fad9-157">Você pode usar o construtor de topologias para editar as propriedades de um pool já existente para habilitar o espelhamento do SQL.</span><span class="sxs-lookup"><span data-stu-id="2fad9-157">You can use Topology Builder to edit the properties of an already existing pool to enable SQL mirroring.</span></span>

## <a name="to-add-sql-mirroring-to-an-existing-front-end-pool-in-topology-builder"></a><span data-ttu-id="2fad9-158">Para adicionar o espelhamento SQL a um pool de Front-End existente no construtor de topologia</span><span class="sxs-lookup"><span data-stu-id="2fad9-158">To add SQL mirroring to an existing Front End pool in Topology Builder</span></span>

1. <span data-ttu-id="2fad9-159">No construtor de topologia, clique com botão direito do pool e clique em **Editar propriedades**.</span><span class="sxs-lookup"><span data-stu-id="2fad9-159">In Topology Builder, right-click the pool and then click **Edit Properties**.</span></span>

2. <span data-ttu-id="2fad9-160">Selecione **Habilitar Espelhamento do Repositório SQL** e clique em **Novo** ao lado de **Repositório SQL de Espelhamento**. </span><span class="sxs-lookup"><span data-stu-id="2fad9-160">Select **Enable SQL Store Mirroring**, and then click **New** next to **Mirroring SQL Store**.</span></span>

3. <span data-ttu-id="2fad9-161">Especifique o repositório SQL que você deseja usar como espelho. </span><span class="sxs-lookup"><span data-stu-id="2fad9-161">Specify the SQL store that you want to use as the mirror.</span></span>

4. <span data-ttu-id="2fad9-162">Selecione **Esta instância SQL está em relação de espelhamento**, especifique o número da porta de espelhamento SQL (o padrão é 5022) e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="2fad9-162">Select **This SQL instance is in mirroring relation**, specify the SQL mirroring port number the default port is 5022), and then click **OK**.</span></span>

5. <span data-ttu-id="2fad9-163">Caso deseje configurar uma testemunha, selecione **Usar testemunha de espelhamento SQL para habilitar failover automático** e clique em **Novo**. </span><span class="sxs-lookup"><span data-stu-id="2fad9-163">If you want to configure a witness, select **Use SQL mirroring witness to enable automatic failover**, and click **New**.</span></span>

6. <span data-ttu-id="2fad9-164">Especifique o repositório SQL que você deseja usar como testemunha. </span><span class="sxs-lookup"><span data-stu-id="2fad9-164">Specify the SQL store that you want to use as the witness.</span></span>

7. <span data-ttu-id="2fad9-165">Selecione **Esta instância SQL está em relação de espelhamento**, especifique o número da porta de espelhamento SQL (o padrão é 7022) e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="2fad9-165">Select **This SQL instance is in mirroring relation**, specify the SQL mirroring port number (the default port is 7022), and then click **OK**.</span></span>

8. <span data-ttu-id="2fad9-166">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="2fad9-166">Click **OK**.</span></span>

9. <span data-ttu-id="2fad9-p116">Publique a topologia. Quando você fizer isso, o sistema solicitará a instalação do banco de dados. </span><span class="sxs-lookup"><span data-stu-id="2fad9-p116">Publish the topology. When you do so, you will be prompted to install the database.</span></span>

    <span data-ttu-id="2fad9-p117">Durante o processo de publicação da topologia, você deverá definir um caminho de compartilhamento de arquivos. Os SQL Servers que participam do espelhamento devem ter acesso de leitura/gravação a esse compartilhamento de arquivos para que o espelhamento seja estabelecido.</span><span class="sxs-lookup"><span data-stu-id="2fad9-p117">During the topology publishing process, you will be asked to define a file share path. The SQL Servers that participate in the mirroring must have read/write access to this file share for the mirror to be established.</span></span>

<span data-ttu-id="2fad9-171">Instale o banco de dados antes de ir para o próximo procedimento.</span><span class="sxs-lookup"><span data-stu-id="2fad9-171">You must then install the database before going on to the next procedure.</span></span>

<span data-ttu-id="2fad9-172">Lembre-se disto ao configurar o espelhamento de SQL:</span><span class="sxs-lookup"><span data-stu-id="2fad9-172">You should keep the following in mind when setting up SQL mirroring:</span></span>

- <span data-ttu-id="2fad9-173">Caso já exista um ponto de extremidade de espelhamento, ele será reutilizado usando as portas definidas nele e irá ignorar aquelas especificadas na topologia.</span><span class="sxs-lookup"><span data-stu-id="2fad9-173">If a mirroring endpoint already exists, it will be reused using the ports defined there, and will ignore the ones you specify in the topology.</span></span>

- <span data-ttu-id="2fad9-p118">Todas as portas já alocadas para outros aplicativos no mesmo servidor (inclusive de outras instâncias SQL) não deverão ser usadas para as instâncias SQL instaladas atualmente. Isso significa que, se você tiver mais de uma instância SQL instalada no mesmo servidor, elas não poderão usar a mesma porta para espelhamento. Para saber mais, veja os seguintes artigos:</span><span class="sxs-lookup"><span data-stu-id="2fad9-p118">Any port already allocated for other applications on the same server, including those for other SQL instances, should not be used for the installed SQL instances at hand. This implies that if you have more than one SQL instance installed on the same server, they must not use the same port for mirroring. For details, see the following articles:</span></span>

  - [<span data-ttu-id="2fad9-177">Especificar um endereço de rede do servidor (espelhamento de banco de dados)</span><span class="sxs-lookup"><span data-stu-id="2fad9-177">Specify a Server Network Address (Database Mirroring)</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=247346)

  - [<span data-ttu-id="2fad9-178">O banco de dados (SQL Server) do ponto de extremidade de espelhamento</span><span class="sxs-lookup"><span data-stu-id="2fad9-178">The Database Mirroring Endpoint (SQL Server)</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=247347)

## <a name="using-skype-for-business-server-2015-management-shell-cmdlets-to-set-up-sql-mirroring"></a><span data-ttu-id="2fad9-179">Usando o Skype para Cmdlets do Shell de gerenciamento do Business Server 2015 ao conjunto o espelhamento SQL</span><span class="sxs-lookup"><span data-stu-id="2fad9-179">Using Skype for Business Server 2015 Management Shell Cmdlets to Set Up SQL Mirroring</span></span>

<span data-ttu-id="2fad9-180">A maneira mais fácil de configurar o espelhamento é usando o construtor de topologia, mas você também pode fazer isso usando cmdlets.</span><span class="sxs-lookup"><span data-stu-id="2fad9-180">The easiest way to set up mirroring is by using Topology Builder, but you can also do so using cmdlets.</span></span>

1. <span data-ttu-id="2fad9-181">Abra um Skype para a janela do Shell de gerenciamento do Business Server 2015 e execute o seguinte cmdlet:</span><span class="sxs-lookup"><span data-stu-id="2fad9-181">Open a Skype for Business Server 2015 Management Shell window and run the following cmdlet:</span></span>

   ```
   Install-CsMirrorDatabase [-ConfiguredDatabases] [-ForInstance] [-ForDefaultInstance] [-DatabaseType <Application | Archiving | CentralMgmt | Monitoring | User | BIStaging | PersistentChat | PersistentChatCompliance >] -FileShare <fileshare> -SqlServerFqdn <primarySqlserverFqdn> [-SqlInstanceName] [-DatabasePathMap] [-ExcludeDatabaseList] [-DropExistingDatabasesOnMirror] -Verbose
   ```

    <span data-ttu-id="2fad9-182">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="2fad9-182">For example:</span></span>

   ```
   Install-CsMirrorDatabase -ConfiguredDatabases -FileShare \\PRIMARYBE\csdatabackup -SqlServerFqdn primaryBE.contoso.com -DropExistingDatabasesOnMirror -Verbose
   ```

    <span data-ttu-id="2fad9-183">Você verá:</span><span class="sxs-lookup"><span data-stu-id="2fad9-183">You will see the following:</span></span>

   <pre>
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
   </pre>

2. <span data-ttu-id="2fad9-184">Verifique se:</span><span class="sxs-lookup"><span data-stu-id="2fad9-184">Verify the following:</span></span>

    - <span data-ttu-id="2fad9-185">A porta 5022 pode ser acessada através do firewall se o Firewall do Windows estiver habilitado no SQL Server principal e04-ocs.los_a.lsipt.local\rtc. </span><span class="sxs-lookup"><span data-stu-id="2fad9-185">Port 5022 is accessible through the firewall if Windows Firewall is enabled in the primary SQL Server e04-ocs.los_a.lsipt.local\rtc.</span></span>

    - <span data-ttu-id="2fad9-186">A porta 5022 pode ser acessada através do firewall se o Firewall do Windows estiver habilitado no SQL Server espelho K16-ocs.los_a.lsipt.local\rtc. </span><span class="sxs-lookup"><span data-stu-id="2fad9-186">Port 5022 is accessible through the firewall if Windows Firewall is enabled in the mirror SQL Server K16-ocs.los_a.lsipt.local\rtc.</span></span>

    - <span data-ttu-id="2fad9-187">A porta 7022 pode ser acessada através do firewall se o Firewall do Windows estiver habilitado no SQL Server testemunha AB14-lct.los_a.lsipt.local\rtc. </span><span class="sxs-lookup"><span data-stu-id="2fad9-187">Port 7022 is accessible through the firewall if Windows Firewall is enabled in the witness SQL Server AB14-lct.los_a.lsipt.local\rtc.</span></span>

   - <span data-ttu-id="2fad9-188">Contas executando o SQL Servers em todos os primário e o espelhamento SQL servers têm permissão de leitura/gravação para o compartilhamento de arquivo \\E04-OCS\csdatabackup</span><span class="sxs-lookup"><span data-stu-id="2fad9-188">Accounts running the SQL Servers on all primary and mirror SQL servers have read/write permission to the file share \\E04-OCS\csdatabackup</span></span>

   - <span data-ttu-id="2fad9-p119">Verifique se o provedor WMI (Instrumentação de Gerenciamento do Windows) está em execução em todos esses servidores. O cmdlet usa esse provedor para encontrar informações da conta relativas aos serviços do SQL Server em execução em todos os servidores principais, espelho e testemunha. </span><span class="sxs-lookup"><span data-stu-id="2fad9-p119">Verify that the Windows Management Instrumentation (WMI) provider is running on all these servers. The cmdlet uses this provider to find the account information for SQL Server services running on all primary, mirror and witness servers.</span></span>

   - <span data-ttu-id="2fad9-191">Verifique se a conta que executa esse cmdlet tem permissão para criar as pastas de dados e de arquivos de log para todos os servidores espelho. </span><span class="sxs-lookup"><span data-stu-id="2fad9-191">Verify that the account running this cmdlet has permission to create the folders for the data and log files for all the mirror servers.</span></span>

   - <span data-ttu-id="2fad9-p120">Observe que a conta de usuário usada pela instância SQL para execução deve ter permissão de leitura/gravação no compartilhamento de arquivos. Se o compartilhamento de arquivos estiver em um servidor diferente e a instância SQL for executada em uma conta do sistema local, você deverá conceder permissões de compartilhamento de arquivos ao servidor que hospeda a instância SQL.</span><span class="sxs-lookup"><span data-stu-id="2fad9-p120">Note that the user account that the SQL instance uses to run must have read/write permission to the file share. If the file share is on a different server, and the SQL instance runs a local system account, you must grant file share permissions to the server that hosts the SQL instance.</span></span>

3. <span data-ttu-id="2fad9-194">Digite A e pressione ENTER.</span><span class="sxs-lookup"><span data-stu-id="2fad9-194">Type A and press ENTER.</span></span>

    <span data-ttu-id="2fad9-195">O espelhamento será configurado.</span><span class="sxs-lookup"><span data-stu-id="2fad9-195">The mirroring will be configured.</span></span>

    <span data-ttu-id="2fad9-196">**Install-CsMirrorDatabase** instala o espelho e configura o espelhamento para todos os bancos de dados que estão presentes no repositório de SQL principal.</span><span class="sxs-lookup"><span data-stu-id="2fad9-196">**Install-CsMirrorDatabase** installs the mirror and configures mirroring for all the databases that are present on the primary SQL store.</span></span> <span data-ttu-id="2fad9-197">Se você deseja configurar o espelhamento de bancos de dados somente específicos, você pode usar a opção - DatabaseType, ou se você quiser configurar o espelhamento para todos os bancos de dados, com exceção de alguns, você pode usar a opção - ExcludeDatabaseList, juntamente com uma lista separada por vírgulas de banco de dados nomes a serem excluídos.</span><span class="sxs-lookup"><span data-stu-id="2fad9-197">If you want to configure mirroring for only specific databases, you can use the -DatabaseType option, or if you want to configure mirroring for all databases except for a few, you can use the -ExcludeDatabaseList option, along with a comma-separated list of database names to exclude.</span></span>

    <span data-ttu-id="2fad9-198">Por exemplo, caso você adicione a opção a seguir a **Install-CsMirrorDatabase**, todos os bancos de dados serão espelhados, com exceção de rtcab e rtcxds.</span><span class="sxs-lookup"><span data-stu-id="2fad9-198">For example, if you add the following option to **Install-CsMirrorDatabase**, all databases except rtcab and rtcxds will be mirrored.</span></span>

    `-ExcludeDatabaseList rtcab,rtcxds`

   <span data-ttu-id="2fad9-199">Por exemplo, caso você adicione a opção a seguir a **Install-CsMirrorDatabase**, somente os bancos de dados rtcab, rtcshared e rtcxds serão espelhados.</span><span class="sxs-lookup"><span data-stu-id="2fad9-199">For example, if you add the following option to **Install-CsMirrorDatabase**, only the rtcab, rtcshared, and rtcxds databases will be mirrored.</span></span>

    `-DatabaseType User`

## <a name="removing-or-changing-sql-mirroring"></a><span data-ttu-id="2fad9-200">Remoção ou alteração do espelhamento SQL</span><span class="sxs-lookup"><span data-stu-id="2fad9-200">Removing or Changing SQL Mirroring</span></span>

<span data-ttu-id="2fad9-p122">Para remover o espelhamento de SQL de um pool no Construtor de Topologias, primeiro use um cmdlet para remover o espelho no SQL Server. Em seguida, você poderá usar o Construtor de Topologias para remover o espelho da topologia. Para remover o espelho no SQL Server, use o cmdlet a seguir:</span><span class="sxs-lookup"><span data-stu-id="2fad9-p122">To remove the SQL mirroring of a pool in Topology Builder, you must first use a cmdlet to remove the mirror in SQL Server. You can then use Topology Builder to remove the mirror from the topology. To remove the mirror in SQL Server, use the following cmdlet:</span></span>

```
Uninstall-CsMirrorDatabase -SqlServerFqdn <SQLServer FQDN> [-SqlInstanceName <SQLServer instance name>] -DatabaseType <Application | Archiving | CentralMgmt | Monitoring | User | BIStaging | PersistentChat | PersistentChatCompliance> [-DropExistingDatabasesOnMirror] [-Verbose]
```

<span data-ttu-id="2fad9-204">Por exemplo, para remover o espelhamento e os bancos de dados de usuários, digite:</span><span class="sxs-lookup"><span data-stu-id="2fad9-204">For example, to remove mirroring and drop the databases for the User databases, type the following:</span></span>

```
Uninstall-CsMirrorDatabase -SqlServerFqdn primaryBE.contoso.com -SqlInstanceName rtc -Verbose -DatabaseType User -DropExistingDatabasesOnMirror
```

<span data-ttu-id="2fad9-205">O `-DropExistingDatabasesOnMirror` opção faz com que os bancos de dados afetados sejam excluídas do espelho.</span><span class="sxs-lookup"><span data-stu-id="2fad9-205">The  `-DropExistingDatabasesOnMirror` option causes the affected databases to be deleted from the mirror.</span></span>

<span data-ttu-id="2fad9-206">Depois, para remover o espelho da topologia, faça o seguinte:</span><span class="sxs-lookup"><span data-stu-id="2fad9-206">Then, to remove the mirror from the topology, do the following:</span></span>

1. <span data-ttu-id="2fad9-207">No Construtor de Topologias, clique com o botão direito do mouse no pool e clique em **Editar Propriedades**.</span><span class="sxs-lookup"><span data-stu-id="2fad9-207">In Topology Builder, right-click the pool and click **Edit Properties**.</span></span>

2. <span data-ttu-id="2fad9-208">Desmarque **Habilitar Espelhamento do Repositório SQL** e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="2fad9-208">Uncheck **Enable SQL Store Mirroring** and click **OK**.</span></span>

3. <span data-ttu-id="2fad9-209">Publique a topologia.</span><span class="sxs-lookup"><span data-stu-id="2fad9-209">Publish the topology.</span></span>

## <a name="removing-a-mirroring-witness"></a><span data-ttu-id="2fad9-210">Remoção de uma testemunha de espelhamento</span><span class="sxs-lookup"><span data-stu-id="2fad9-210">Removing a Mirroring Witness</span></span>

<span data-ttu-id="2fad9-211">Use este procedimento se você precisa remover a testemunha de um servidor Back-End configuração de espelhamento.</span><span class="sxs-lookup"><span data-stu-id="2fad9-211">Use this procedure if you need to remove the witness from a Back End Server mirroring configuration.</span></span>

1. <span data-ttu-id="2fad9-212">No Construtor de Topologias, clique com o botão direito do mouse no pool e clique em **Editar Propriedades**.</span><span class="sxs-lookup"><span data-stu-id="2fad9-212">In Topology Builder, right-click the pool and click **Edit Properties**.</span></span>

2. <span data-ttu-id="2fad9-213">Desmarque **Usar testemunha de espelhamento do SQL Server para habilitar failover automático** e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="2fad9-213">Uncheck **Use SQL Server mirroring witness to enable automatic failover** and click **OK**.</span></span>

3. <span data-ttu-id="2fad9-214">Publique a topologia.</span><span class="sxs-lookup"><span data-stu-id="2fad9-214">Publish the topology.</span></span>

    <span data-ttu-id="2fad9-215">Após publicar a topologia, o construtor de topologia você verá uma mensagem que inclui os seguintes</span><span class="sxs-lookup"><span data-stu-id="2fad9-215">After publishing the topology, Topology Builder you will see a message that includes the following</span></span>

   ```
   Run the Uninstall-CsMirrorDatabase cmdlet to remove databases that are paired with following primary databases.
   ```

    <span data-ttu-id="2fad9-216">No entanto, não siga essa etapa e não digite `Uninstall-CsMirrorDatabase` como isso fará a desinstalação toda a configuração do espelhamento.</span><span class="sxs-lookup"><span data-stu-id="2fad9-216">However, do not follow that step, and do not type  `Uninstall-CsMirrorDatabase` as that would uninstall the entire mirroring configuration.</span></span>

4. <span data-ttu-id="2fad9-217">Para remover apenas a testemunha da configuração do SQL Server, siga as instruções em [Remover a testemunha de uma sessão de espelhamento de banco de dados (SQL Server)](https://go.microsoft.com/fwlink/p/?LinkId=268456).</span><span class="sxs-lookup"><span data-stu-id="2fad9-217">To remove just the witness from the SQL Server configuration, follow the instructions in [Remove the Witness from a Database Mirroring Session (SQL Server)](https://go.microsoft.com/fwlink/p/?LinkId=268456).</span></span>


