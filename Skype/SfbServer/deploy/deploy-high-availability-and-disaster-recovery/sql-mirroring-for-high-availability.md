---
title: 'Implantar espelhamento SQL para alta disponibilidade do Servidor #A0 no Skype for Business Server 2015'
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 70224520-b5c8-4940-a08e-7fb9b1adde8d
description: 'Para que seja possível implantar o espelhamento SQL, os servidores devem executar no mínimo o SQL Server 2008 R2. Essa versão deve ser executada em todos os servidores envolvidos: principal, espelho e testemunha. Para obter detalhes, consulte o pacote de atualização cumulativa 9 para SQL Server 2008 Service Pack 1 .'
ms.openlocfilehash: 8a546f65d8ad5c701eea20fb2c9c3bf0e026ff1f
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49830551"
---
# <a name="deploy-sql-mirroring-for-back-end-server-high-availability-in-skype-for-business-server-2015"></a><span data-ttu-id="c0e91-105">Implantar espelhamento SQL para alta disponibilidade do Servidor #A0 no Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="c0e91-105">Deploy SQL mirroring for Back End Server high availability in Skype for Business server 2015</span></span>


<span data-ttu-id="c0e91-106">Para que seja possível implantar o espelhamento SQL, os servidores devem executar no mínimo o SQL Server 2008 R2.</span><span class="sxs-lookup"><span data-stu-id="c0e91-106">To be able to deploy SQL mirroring, your servers must run a minimum of SQL Server 2008 R2.</span></span> <span data-ttu-id="c0e91-107">Essa versão deve ser executada em todos os servidores envolvidos: principal, espelho e testemunha.</span><span class="sxs-lookup"><span data-stu-id="c0e91-107">This version must run on all the involved servers: the primary, mirror, and the witness.</span></span> <span data-ttu-id="c0e91-108">Para obter detalhes, consulte [o pacote de atualização cumulativa 9 para SQL Server 2008 Service Pack 1](https://go.microsoft.com/fwlink/p/?linkid=3052&amp;kbid=2083921).</span><span class="sxs-lookup"><span data-stu-id="c0e91-108">For details, see [Cumulative update package 9 for SQL Server 2008 Service Pack 1](https://go.microsoft.com/fwlink/p/?linkid=3052&amp;kbid=2083921).</span></span>

<span data-ttu-id="c0e91-109">Em geral, a configuração do espelhamento SQL entre os dois servidores back-end com uma testemunha requer:</span><span class="sxs-lookup"><span data-stu-id="c0e91-109">In general, setting up SQL mirroring between the two Back End Servers with a witness requires the following:</span></span>

- <span data-ttu-id="c0e91-110">A versão do SQL Server do servidor primário deve dar suporte ao espelhamento SQL.</span><span class="sxs-lookup"><span data-stu-id="c0e91-110">The primary server's version of SQL Server must support SQL mirroring.</span></span>

- <span data-ttu-id="c0e91-111">Que o principal, o espelho e a testemunha (se implantada) tenham a mesma versão do SQL Server.</span><span class="sxs-lookup"><span data-stu-id="c0e91-111">The primary, mirror, and the witness (if deployed) must have the same version of SQL Server.</span></span>

- <span data-ttu-id="c0e91-p103">Que o principal e o espelho tenham a mesma edição do SQL Server. A testemunha pode ter uma edição diferente.</span><span class="sxs-lookup"><span data-stu-id="c0e91-p103">The primary and the mirror must have the same edition of SQL Server. The witness may have a different edition.</span></span>

<span data-ttu-id="c0e91-114">Para práticas recomendadas do SQL em termos de quais versões SQL são suportadas para uma função testemunha, consulte [Testemunha de espelhamento de banco de dados.](https://go.microsoft.com/fwlink/p/?LinkId=247345)</span><span class="sxs-lookup"><span data-stu-id="c0e91-114">For SQL best practices in terms of what SQL versions are supported for a Witness role, see [Database Mirroring Witness](https://go.microsoft.com/fwlink/p/?LinkId=247345).</span></span>

<span data-ttu-id="c0e91-115">Use o Construtor de Topologias para implantar o espelhamento SQL.</span><span class="sxs-lookup"><span data-stu-id="c0e91-115">You use Topology Builder to deploy SQL mirroring.</span></span> <span data-ttu-id="c0e91-116">Selecione uma opção no Construtor de Topologias para espelhar os bancos de dados, e o Construtor de Topologias configura o espelhamento (incluindo a configuração de uma testemunha, se quiser) ao publicar a topologia.</span><span class="sxs-lookup"><span data-stu-id="c0e91-116">You select an option in Topology Builder to mirror the databases, and Topology Builder sets up the mirroring (including setting up a witness, if you want) when you publish the topology.</span></span> <span data-ttu-id="c0e91-117">Observe que a testemunha é configurada ou removida ao mesmo tempo que o espelho.</span><span class="sxs-lookup"><span data-stu-id="c0e91-117">Note that you set up or remove the witness at the same time you set up or remove the mirror.</span></span> <span data-ttu-id="c0e91-118">Não há um comando separado para implantar ou remover somente a testemunha.</span><span class="sxs-lookup"><span data-stu-id="c0e91-118">There is no separate command to deploy or remove only a witness.</span></span>

<span data-ttu-id="c0e91-119">Para configurar o espelhamento do servidor, primeiro você deve configurar as permissões do banco de dados SQL corretamente.</span><span class="sxs-lookup"><span data-stu-id="c0e91-119">To configure server mirroring, you must first set up SQL database permissions correctly.</span></span> <span data-ttu-id="c0e91-120">Para obter detalhes, consulte Configurar contas de logon para espelhamento de banco de dados ou grupos de disponibilidade [AlwaysOn (SQL Server).](https://go.microsoft.com/fwlink/p/?LinkId=268454)</span><span class="sxs-lookup"><span data-stu-id="c0e91-120">For details, see [Set Up Login Accounts for Database Mirroring or AlwaysOn Availability Groups (SQL Server)](https://go.microsoft.com/fwlink/p/?LinkId=268454).</span></span>

<span data-ttu-id="c0e91-121">Com o espelhamento SQL, o modo de recuperação de banco de dados fica sempre definido como **Completo**, o que significa que você deve monitorar de perto o tamanho dos logs de transações, fazendo backup regular deles para evitar o esgotamento do espaço em disco dos servidores back-end.</span><span class="sxs-lookup"><span data-stu-id="c0e91-121">With SQL mirroring, database recovery mode is always set to **Full**, which means you must closely monitor transaction log size and back up transaction logs on a regular basis to avoid running out of disk space on the Back End Servers.</span></span> <span data-ttu-id="c0e91-122">A frequência dos backups dos logs de transações depende da taxa de expansão dos logs, que, por sua vez, depende das transações do banco de dados provenientes de atividades de usuários no pool front-end.</span><span class="sxs-lookup"><span data-stu-id="c0e91-122">The frequency of transaction log backups depends on the log growth rate, which in turn depends on database transactions incurred by user activities on the Front End pool.</span></span> <span data-ttu-id="c0e91-123">Recomendamos que você determine a expansão esperada do log de transações para a carga de trabalho de implantação para poder fazer o planejamento de acordo.</span><span class="sxs-lookup"><span data-stu-id="c0e91-123">We recommend that you determine how much transaction log growth is expected for your deployment workload so that you can do the planning accordingly.</span></span> <span data-ttu-id="c0e91-124">Os artigos a seguir fornecem mais informações sobre o gerenciamento de logs e backups do SQL:</span><span class="sxs-lookup"><span data-stu-id="c0e91-124">The following articles provide additional information on SQL backup and log management:</span></span>

- [<span data-ttu-id="c0e91-125">Modelos de recuperação de banco de dados</span><span class="sxs-lookup"><span data-stu-id="c0e91-125">Database recovery models</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=268446)

- [<span data-ttu-id="c0e91-126">Visão geral do backup</span><span class="sxs-lookup"><span data-stu-id="c0e91-126">Backup overview</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=268449)

- [<span data-ttu-id="c0e91-127">Log de transações de backup</span><span class="sxs-lookup"><span data-stu-id="c0e91-127">Backup transaction log</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=268452)

<span data-ttu-id="c0e91-128">Com o espelhamento SQL, você pode configurar a topologia do espelhamento no momento da criação dos pools ou após isso.</span><span class="sxs-lookup"><span data-stu-id="c0e91-128">With SQL mirroring, you can either configure the topology for mirroring when you create the pools, or after the pools are already created.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="c0e91-129">O uso do Construtor de Topologias ou cmdlets para configurar e remover o espelhamento SQL é suportado somente quando os servidores primário, espelho e testemunha (se desejado) pertencem ao mesmo domínio.</span><span class="sxs-lookup"><span data-stu-id="c0e91-129">Using Topology Builder or cmdlets to set up and remove SQL mirroring is supported only when the primary, mirror, and witness (if desired) servers all belong to the same domain.</span></span> <span data-ttu-id="c0e91-130">Caso deseje configurar o espelhamento SQL entre servidores de domínios diferentes, consulte a documentação do SQL Server.</span><span class="sxs-lookup"><span data-stu-id="c0e91-130">If you want to set up SQL mirroring among servers in different domains, see your SQL Server documentation.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="c0e91-131">Sempre que fizer uma alteração em um relacionamento de espelhamento de banco de dados back-end, você deverá reiniciar todos os servidores front-end do pool.</span><span class="sxs-lookup"><span data-stu-id="c0e91-131">Whenever you make a change to a Back End Database mirroring relationship, you must restart all the Front End Servers in the pool.</span></span> <span data-ttu-id="c0e91-132">> Para uma alteração no espelhamento (como alterar o local de um espelho), você deve usar o Construtor de Topologias para executar estas três etapas:</span><span class="sxs-lookup"><span data-stu-id="c0e91-132">> For a change in mirroring, (such as changing the location of a mirror), you must use Topology Builder to perform these three steps:</span></span>

1. <span data-ttu-id="c0e91-133">Remova o espelhamento do servidor espelho antigo.</span><span class="sxs-lookup"><span data-stu-id="c0e91-133">Remove mirroring from the old mirror server.</span></span>

2. <span data-ttu-id="c0e91-134">Adicione espelhamento ao novo servidor espelho.</span><span class="sxs-lookup"><span data-stu-id="c0e91-134">Add mirroring to the new mirror server.</span></span>

3. <span data-ttu-id="c0e91-135">Publique a topologia.</span><span class="sxs-lookup"><span data-stu-id="c0e91-135">Publish the topology.</span></span>

> [!NOTE]
> <span data-ttu-id="c0e91-136">Um compartilhamento de arquivos deve ser criado para que os arquivos espelho sejam gravados, e o serviço em que o SQL Server e o SQL Agent estão sendo executados precisam de acesso de leitura/gravação.</span><span class="sxs-lookup"><span data-stu-id="c0e91-136">A file share has to be created for the mirror files to be written to, and the service that SQL Server and SQL Agent are running under needs read/write access.</span></span> <span data-ttu-id="c0e91-137">Se o serviço do SQL Server estiver sendo executado sob o contexto do Serviço de Rede, você poderá adicionar \<Domain\><SQLSERVERNAME $ dos Servidores SQL Principal e Espelho às permissões \\ \> de compartilhamento.</span><span class="sxs-lookup"><span data-stu-id="c0e91-137">If the SQL Server service is running under the context of Network Service, you can add \<Domain\>\\<SQLSERVERNAME\>$ of both the Principal and Mirror SQL Servers to the share permissions.</span></span> <span data-ttu-id="c0e91-138">O $ é importante para identificar que esta é uma conta de computador.</span><span class="sxs-lookup"><span data-stu-id="c0e91-138">The $ is important to identify that this is a computer account.</span></span>

## <a name="to-configure-sql-mirroring-while-creating-a-pool-in-topology-builder"></a><span data-ttu-id="c0e91-139">Para configurar o espelhamento SQL ao criar um pool no Construtor de Topologias</span><span class="sxs-lookup"><span data-stu-id="c0e91-139">To configure SQL mirroring while creating a pool in Topology Builder</span></span>

1. <span data-ttu-id="c0e91-140">Na página **Definir o Repositório do SQL**, clique em **Novo** ao lado da caixa **Repositório do SQL**.</span><span class="sxs-lookup"><span data-stu-id="c0e91-140">On the **Define the SQL Store** page, click **New** next to the **SQL store** box.</span></span>

2. <span data-ttu-id="c0e91-141">Na página **Definir Novo Repositório do SQL**, especifique o repositório principal, selecione **Esta instância SQL está em relação de espelhamento**, especifique o número da porta de espelhamento SQL (o padrão é 5022) e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="c0e91-141">On the **Define new SQL Store** page, specify the primary store, select **This SQL instance is in mirroring relation**, specify the SQL mirroring port number (the default is 5022), and then click **OK**.</span></span>

3. <span data-ttu-id="c0e91-142">De volta à página **Definir o Repositório do SQL**, selecione **Habilitar Espelhamento do Repositório do SQL**.</span><span class="sxs-lookup"><span data-stu-id="c0e91-142">Back on the **Define the SQL store** page, select **Enable SQL Store mirroring**.</span></span>

4. <span data-ttu-id="c0e91-p110">Na página **Definir Novo Repositório do SQL**, especifique o repositório do SQL a ser usado como espelho, selecione **Esta instância SQL está em relação de espelhamento**, especifique o número da porta de espelhamento SQL (o padrão é 5022) e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="c0e91-p110">In the **Define new SQL Store** page, specify the SQL store to be used as the mirror. Select **This SQL instance is in mirroring relation**, specify the port number (the default is 5022), and then click **OK**.</span></span>

5. <span data-ttu-id="c0e91-145">Caso deseje uma testemunha para este espelho, faça o seguinte:</span><span class="sxs-lookup"><span data-stu-id="c0e91-145">If you want a witness for this mirror, do the following:</span></span>

    <span data-ttu-id="c0e91-146">a.</span><span class="sxs-lookup"><span data-stu-id="c0e91-146">a.</span></span> <span data-ttu-id="c0e91-147">Selecione **Usar testemunha de espelhamento do SQL para habilitar failover automático**.</span><span class="sxs-lookup"><span data-stu-id="c0e91-147">Select **Use SQL mirroring witness to enable automatic failover**.</span></span>

    <span data-ttu-id="c0e91-148">b.</span><span class="sxs-lookup"><span data-stu-id="c0e91-148">b.</span></span> <span data-ttu-id="c0e91-149">Na página **Definir o Repositório do SQL**, selecione **Usar testemunha de espelhamento do SQL para habilitar failover automático** e especifique o repositório do SQL a ser usado como testemunha.</span><span class="sxs-lookup"><span data-stu-id="c0e91-149">In the **Define the SQL Store** page, select **Use SQL mirroring witness to enable automatic failover**, and specify the SQL store to be used as the witness.</span></span>

    <span data-ttu-id="c0e91-150">c.</span><span class="sxs-lookup"><span data-stu-id="c0e91-150">c.</span></span> <span data-ttu-id="c0e91-151">Especifique o número da porta (o padrão é 7022) e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="c0e91-151">Specify the port number (the default is 7022) and click **OK**.</span></span>

6. <span data-ttu-id="c0e91-152">Depois de terminar de definir seu pool de Front-End e todas as outras funções em sua topologia, use o Construtor de Topologias para publicar a topologia.</span><span class="sxs-lookup"><span data-stu-id="c0e91-152">After you are done defining your Front End pool and all other roles in your topology, use Topology Builder to publish the topology.</span></span> <span data-ttu-id="c0e91-153">Quando a topologia for publicada, se o pool de #A0 que hospeda o armazenamento de Gerenciamento Central tiver o espelhamento SQL habilitado, você verá uma opção para criar bancos de dados do armazenamento SQL principal e espelho.</span><span class="sxs-lookup"><span data-stu-id="c0e91-153">When the topology is published, if the Front End pool that hosts Central Management store has SQL mirroring enabled, you will see an option to create both primary and mirror SQL store databases.</span></span>

    <span data-ttu-id="c0e91-154">Clique em **Configurações** e digite o caminho que será usado como compartilhamento de arquivos para o backup de espelhamento.</span><span class="sxs-lookup"><span data-stu-id="c0e91-154">Click **Settings**, and type the path to use as the file share for the mirroring backup.</span></span>

    <span data-ttu-id="c0e91-p115">Clique em **OK** e em **Avançar** para criar os bancos de dados e publicar a topologia. O espelhamento e a testemunha (se especificada) serão implantados.</span><span class="sxs-lookup"><span data-stu-id="c0e91-p115">Click **OK** and then **Next** to create the databases and publish the topology. The mirroring and the witness (if specified) will be deployed.</span></span>

<span data-ttu-id="c0e91-157">Você pode usar o Construtor de Topologias para editar as propriedades de um pool já existente para habilitar o espelhamento SQL.</span><span class="sxs-lookup"><span data-stu-id="c0e91-157">You can use Topology Builder to edit the properties of an already existing pool to enable SQL mirroring.</span></span>

## <a name="to-add-sql-mirroring-to-an-existing-front-end-pool-in-topology-builder"></a><span data-ttu-id="c0e91-158">Para adicionar espelhamento SQL a um pool de #A0 existente no Construtor de Topologias</span><span class="sxs-lookup"><span data-stu-id="c0e91-158">To add SQL mirroring to an existing Front End pool in Topology Builder</span></span>

1. <span data-ttu-id="c0e91-159">No Construtor de Topologias, clique com o botão direito do mouse no pool e clique em **Editar Propriedades.**</span><span class="sxs-lookup"><span data-stu-id="c0e91-159">In Topology Builder, right-click the pool and then click **Edit Properties**.</span></span>

2. <span data-ttu-id="c0e91-160">Selecione **Habilitar Espelhamento do Repositório do SQL** e clique em **Novo** ao lado de **Repositório do SQL de Espelhamento**.</span><span class="sxs-lookup"><span data-stu-id="c0e91-160">Select **Enable SQL Store Mirroring**, and then click **New** next to **Mirroring SQL Store**.</span></span>

3. <span data-ttu-id="c0e91-161">Especifique o repositório do SQL que deseja usar como espelho.</span><span class="sxs-lookup"><span data-stu-id="c0e91-161">Specify the SQL store that you want to use as the mirror.</span></span>

4. <span data-ttu-id="c0e91-162">Selecione **Esta instância SQL está em relação de espelhamento**, especifique o número da porta de espelhamento (o padrão é 5022) e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="c0e91-162">Select **This SQL instance is in mirroring relation**, specify the SQL mirroring port number the default port is 5022), and then click **OK**.</span></span>

5. <span data-ttu-id="c0e91-163">Caso deseje configurar uma testemunha, selecione **Usar testemunha de espelhamento do SQL para habilitar failover automático** e clique em **Novo**.</span><span class="sxs-lookup"><span data-stu-id="c0e91-163">If you want to configure a witness, select **Use SQL mirroring witness to enable automatic failover**, and click **New**.</span></span>

6. <span data-ttu-id="c0e91-164">Especifique o repositório do SQL que deseja usar como testemunha.</span><span class="sxs-lookup"><span data-stu-id="c0e91-164">Specify the SQL store that you want to use as the witness.</span></span>

7. <span data-ttu-id="c0e91-165">Selecione **Esta instância SQL está em relação de espelhamento**, especifique o número da porta de espelhamento (o padrão é 7022) e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="c0e91-165">Select **This SQL instance is in mirroring relation**, specify the SQL mirroring port number (the default port is 7022), and then click **OK**.</span></span>

8. <span data-ttu-id="c0e91-166">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="c0e91-166">Click **OK**.</span></span>

9. <span data-ttu-id="c0e91-p116">Publique a topologia. Quando você fizer isso, o sistema solicitará a instalação do banco de dados.</span><span class="sxs-lookup"><span data-stu-id="c0e91-p116">Publish the topology. When you do so, you will be prompted to install the database.</span></span>

    <span data-ttu-id="c0e91-169">Durante o processo de publicação da topologia, você será solicitado a definir um caminho de compartilhamento de arquivos.</span><span class="sxs-lookup"><span data-stu-id="c0e91-169">During the topology publishing process, you will be asked to define a file share path.</span></span> <span data-ttu-id="c0e91-170">Os SQL Servers que participam do espelhamento devem ter acesso de leitura/gravação a esse compartilhamento de arquivos para que o espelho seja estabelecido.</span><span class="sxs-lookup"><span data-stu-id="c0e91-170">The SQL Servers that participate in the mirroring must have read/write access to this file share for the mirror to be established.</span></span>

<span data-ttu-id="c0e91-171">Instale o banco de dados antes de ir para o próximo procedimento.</span><span class="sxs-lookup"><span data-stu-id="c0e91-171">You must then install the database before going on to the next procedure.</span></span>

<span data-ttu-id="c0e91-172">Lembre-se disto ao configurar o espelhamento SQL:</span><span class="sxs-lookup"><span data-stu-id="c0e91-172">You should keep the following in mind when setting up SQL mirroring:</span></span>

- <span data-ttu-id="c0e91-173">Caso já exista um ponto de extremidade de espelhamento, ele será reutilizado usando as portas definidas nele e irá ignorar aquelas especificadas na topologia.</span><span class="sxs-lookup"><span data-stu-id="c0e91-173">If a mirroring endpoint already exists, it will be reused using the ports defined there, and will ignore the ones you specify in the topology.</span></span>

- <span data-ttu-id="c0e91-p118">Todas as portas já alocadas a outros aplicativos no mesmo servidor (inclusive de outras instâncias do SQL) não serão usadas com as instâncias do SQL instaladas atualmente. Isso significa que, se você tiver mais de uma instância do SQL instalada no mesmo servidor, elas não poderão usar a mesma porta para espalhamento. Para obter detalhes, consulte os seguintes artigos:</span><span class="sxs-lookup"><span data-stu-id="c0e91-p118">Any port already allocated for other applications on the same server, including those for other SQL instances, should not be used for the installed SQL instances at hand. This implies that if you have more than one SQL instance installed on the same server, they must not use the same port for mirroring. For details, see the following articles:</span></span>

  - [<span data-ttu-id="c0e91-177">Especificar um endereço de rede do servidor (espelhamento de banco de dados)</span><span class="sxs-lookup"><span data-stu-id="c0e91-177">Specify a Server Network Address (Database Mirroring)</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=247346)

  - [<span data-ttu-id="c0e91-178">O ponto de extremidade de espelhamento de banco de dados (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="c0e91-178">The Database Mirroring Endpoint (SQL Server)</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=247347)

## <a name="using-skype-for-business-server-2015-management-shell-cmdlets-to-set-up-sql-mirroring"></a><span data-ttu-id="c0e91-179">Usando cmdlets do Shell de Gerenciamento do Skype for Business Server 2015 para configurar o espelhamento SQL</span><span class="sxs-lookup"><span data-stu-id="c0e91-179">Using Skype for Business Server 2015 Management Shell Cmdlets to Set Up SQL Mirroring</span></span>

<span data-ttu-id="c0e91-180">A maneira mais fácil de configurar o espelhamento é usando o Construtor de Topologias, mas você também pode fazer isso usando cmdlets.</span><span class="sxs-lookup"><span data-stu-id="c0e91-180">The easiest way to set up mirroring is by using Topology Builder, but you can also do so using cmdlets.</span></span>

1. <span data-ttu-id="c0e91-181">Abra uma janela do Shell de Gerenciamento do Skype for Business Server 2015 e execute o seguinte cmdlet:</span><span class="sxs-lookup"><span data-stu-id="c0e91-181">Open a Skype for Business Server 2015 Management Shell window and run the following cmdlet:</span></span>

   ```powershell
   Install-CsMirrorDatabase [-ConfiguredDatabases] [-ForInstance] [-ForDefaultInstance] [-DatabaseType <Application | Archiving | CentralMgmt | Monitoring | User | BIStaging | PersistentChat | PersistentChatCompliance >] -FileShare <fileshare> -SqlServerFqdn <primarySqlserverFqdn> [-SqlInstanceName] [-DatabasePathMap] [-ExcludeDatabaseList] [-DropExistingDatabasesOnMirror] -Verbose
   ```

    <span data-ttu-id="c0e91-182">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="c0e91-182">For example:</span></span>

   ```powershell
   Install-CsMirrorDatabase -ConfiguredDatabases -FileShare \\PRIMARYBE\csdatabackup -SqlServerFqdn primaryBE.contoso.com -DropExistingDatabasesOnMirror -Verbose
   ```

    <span data-ttu-id="c0e91-183">Você verá:</span><span class="sxs-lookup"><span data-stu-id="c0e91-183">You will see the following:</span></span>

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

2. <span data-ttu-id="c0e91-184">Verifique se:</span><span class="sxs-lookup"><span data-stu-id="c0e91-184">Verify the following:</span></span>

    - <span data-ttu-id="c0e91-185">A porta 5022 pode ser acessada pelo firewall quando o Firewall do Windows está habilitado no SQL Server principal e04-ocs.los_a.lsipt.local\rtc.</span><span class="sxs-lookup"><span data-stu-id="c0e91-185">Port 5022 is accessible through the firewall if Windows Firewall is enabled in the primary SQL Server e04-ocs.los_a.lsipt.local\rtc.</span></span>

    - <span data-ttu-id="c0e91-186">A porta 5022 pode ser acessada pelo firewall quando o Firewall do Windows está habilitado no SQL Server espelho K16-ocs.los_a.lsipt.local\rtc.</span><span class="sxs-lookup"><span data-stu-id="c0e91-186">Port 5022 is accessible through the firewall if Windows Firewall is enabled in the mirror SQL Server K16-ocs.los_a.lsipt.local\rtc.</span></span>

    - <span data-ttu-id="c0e91-187">A porta 7022 pode ser acessada pelo firewall quando o Firewall do Windows está habilitado no SQL Server testemunha AB14-lct.los_a.lsipt.local\rtc.</span><span class="sxs-lookup"><span data-stu-id="c0e91-187">Port 7022 is accessible through the firewall if Windows Firewall is enabled in the witness SQL Server AB14-lct.los_a.lsipt.local\rtc.</span></span>

   - <span data-ttu-id="c0e91-188">Contas que executam os SQL Servers em todos os servidores SQL primários e espelho têm permissão de leitura/gravação para o compartilhamento de arquivos \\ E04-OCS\csdatabackup</span><span class="sxs-lookup"><span data-stu-id="c0e91-188">Accounts running the SQL Servers on all primary and mirror SQL servers have read/write permission to the file share \\E04-OCS\csdatabackup</span></span>

   - <span data-ttu-id="c0e91-p119">Verifique se o provedor WMI (Instrumentação de Gerenciamento do Windows) está em execução em todos esses servidores. O cmdlet usa esse provedor para encontrar informações da conta relativas aos serviços do SQL Server em execução em todos os servidores principais, espelho e testemunha.</span><span class="sxs-lookup"><span data-stu-id="c0e91-p119">Verify that the Windows Management Instrumentation (WMI) provider is running on all these servers. The cmdlet uses this provider to find the account information for SQL Server services running on all primary, mirror and witness servers.</span></span>

   - <span data-ttu-id="c0e91-191">Verifique se a conta que executa esse cmdlet tem permissão de criação das pastas dos dados e arquivos de log para todos os servidores espelho.</span><span class="sxs-lookup"><span data-stu-id="c0e91-191">Verify that the account running this cmdlet has permission to create the folders for the data and log files for all the mirror servers.</span></span>

   - <span data-ttu-id="c0e91-p120">Observe que a conta de usuário usada pela instância do SQL para execução deve ter permissão de leitura/gravação do compartilhamento de arquivos. Se o compartilhamento de arquivos estiver em um servidor diferente e a instância do SQL for executada em uma conta do sistema local, você deverá conceder permissões de compartilhamento de arquivos ao servidor que hospeda a instância do SQL.</span><span class="sxs-lookup"><span data-stu-id="c0e91-p120">Note that the user account that the SQL instance uses to run must have read/write permission to the file share. If the file share is on a different server, and the SQL instance runs a local system account, you must grant file share permissions to the server that hosts the SQL instance.</span></span>

3. <span data-ttu-id="c0e91-194">Digite A e pressione ENTER.</span><span class="sxs-lookup"><span data-stu-id="c0e91-194">Type A and press ENTER.</span></span>

    <span data-ttu-id="c0e91-195">O espelhamento será configurado.</span><span class="sxs-lookup"><span data-stu-id="c0e91-195">The mirroring will be configured.</span></span>

    <span data-ttu-id="c0e91-196">**Install-CsMirrorDatabase** instala o espelho e configura o espelhamento para todos os bancos de dados presentes no armazenamento SQL principal.</span><span class="sxs-lookup"><span data-stu-id="c0e91-196">**Install-CsMirrorDatabase** installs the mirror and configures mirroring for all the databases that are present on the primary SQL store.</span></span> <span data-ttu-id="c0e91-197">Se você deseja configurar o espelhamento apenas para bancos de dados específicos, pode usar a opção -DatabaseType ou configurar o espelhamento para todos os bancos de dados, exceto para alguns, você pode usar a opção -ExcludeDatabaseList, juntamente com uma lista separada por vírgulas de nomes de banco de dados para excluir.</span><span class="sxs-lookup"><span data-stu-id="c0e91-197">If you want to configure mirroring for only specific databases, you can use the -DatabaseType option, or if you want to configure mirroring for all databases except for a few, you can use the -ExcludeDatabaseList option, along with a comma-separated list of database names to exclude.</span></span>

    <span data-ttu-id="c0e91-198">Por exemplo, caso adicione a opção a seguir a **Install-CsMirrorDatabase**, todos os bancos de dados serão espelhados, com exceção de rtcab e rtcxds.</span><span class="sxs-lookup"><span data-stu-id="c0e91-198">For example, if you add the following option to **Install-CsMirrorDatabase**, all databases except rtcab and rtcxds will be mirrored.</span></span>

    `-ExcludeDatabaseList rtcab,rtcxds`

   <span data-ttu-id="c0e91-199">Por exemplo, caso adicione a opção a seguir a **Install-CsMirrorDatabase**, somente os bancos de dados rtcab, rtcshared e rtcxds databases serão espelhados.</span><span class="sxs-lookup"><span data-stu-id="c0e91-199">For example, if you add the following option to **Install-CsMirrorDatabase**, only the rtcab, rtcshared, and rtcxds databases will be mirrored.</span></span>

    `-DatabaseType User`

## <a name="removing-or-changing-sql-mirroring"></a><span data-ttu-id="c0e91-200">Removendo ou alterando o espelhamento SQL</span><span class="sxs-lookup"><span data-stu-id="c0e91-200">Removing or Changing SQL Mirroring</span></span>

<span data-ttu-id="c0e91-p122">Para remover o espelhamento SQL de um pool no Construtor de Topologias, primeiro use um cmdlet para remover o espelho no SQL Server. Em seguida, você poderá usar o Construtor de Topologias para remover o espelho da topologia. Para remover o espelho no SQL Server, use o cmdlet a seguir:</span><span class="sxs-lookup"><span data-stu-id="c0e91-p122">To remove the SQL mirroring of a pool in Topology Builder, you must first use a cmdlet to remove the mirror in SQL Server. You can then use Topology Builder to remove the mirror from the topology. To remove the mirror in SQL Server, use the following cmdlet:</span></span>

```powershell
Uninstall-CsMirrorDatabase -SqlServerFqdn <SQLServer FQDN> [-SqlInstanceName <SQLServer instance name>] -DatabaseType <Application | Archiving | CentralMgmt | Monitoring | User | BIStaging | PersistentChat | PersistentChatCompliance> [-DropExistingDatabasesOnMirror] [-Verbose]
```

<span data-ttu-id="c0e91-204">Por exemplo, para remover o espelhamento e descartar os bancos de dados de usuários, digite:</span><span class="sxs-lookup"><span data-stu-id="c0e91-204">For example, to remove mirroring and drop the databases for the User databases, type the following:</span></span>

```powershell
Uninstall-CsMirrorDatabase -SqlServerFqdn primaryBE.contoso.com -SqlInstanceName rtc -Verbose -DatabaseType User -DropExistingDatabasesOnMirror
```

<span data-ttu-id="c0e91-205">A  `-DropExistingDatabasesOnMirror` opção faz com que os bancos de dados afetados sejam excluídos do espelho.</span><span class="sxs-lookup"><span data-stu-id="c0e91-205">The  `-DropExistingDatabasesOnMirror` option causes the affected databases to be deleted from the mirror.</span></span>

<span data-ttu-id="c0e91-206">Em seguida, para remover o espelho da topologia, faça o seguinte:</span><span class="sxs-lookup"><span data-stu-id="c0e91-206">Then, to remove the mirror from the topology, do the following:</span></span>

1. <span data-ttu-id="c0e91-207">No Construtor de Topologias, clique com o botão direito do mouse no pool e em **Editar Propriedades**</span><span class="sxs-lookup"><span data-stu-id="c0e91-207">In Topology Builder, right-click the pool and click **Edit Properties**.</span></span>

2. <span data-ttu-id="c0e91-208">Desmarque **Habilitar Espelhamento do Repositório do SQL** e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="c0e91-208">Uncheck **Enable SQL Store Mirroring** and click **OK**.</span></span>

3. <span data-ttu-id="c0e91-209">Publique a topologia.</span><span class="sxs-lookup"><span data-stu-id="c0e91-209">Publish the topology.</span></span>

## <a name="removing-a-mirroring-witness"></a><span data-ttu-id="c0e91-210">Removendo a testemunha de espelhamento</span><span class="sxs-lookup"><span data-stu-id="c0e91-210">Removing a Mirroring Witness</span></span>

<span data-ttu-id="c0e91-211">Use este procedimento se precisar remover a testemunha de uma configuração de espelhamento do Servidor back-end.</span><span class="sxs-lookup"><span data-stu-id="c0e91-211">Use this procedure if you need to remove the witness from a Back End Server mirroring configuration.</span></span>

1. <span data-ttu-id="c0e91-212">No Construtor de Topologias, clique com o botão direito do mouse no pool e em **Editar Propriedades**</span><span class="sxs-lookup"><span data-stu-id="c0e91-212">In Topology Builder, right-click the pool and click **Edit Properties**.</span></span>

2. <span data-ttu-id="c0e91-213">Desmarque **Usar testemunha de espelhamento do SQL Server para habilitar failover automático** e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="c0e91-213">Uncheck **Use SQL Server mirroring witness to enable automatic failover** and click **OK**.</span></span>

3. <span data-ttu-id="c0e91-214">Publique a topologia.</span><span class="sxs-lookup"><span data-stu-id="c0e91-214">Publish the topology.</span></span>

    <span data-ttu-id="c0e91-215">Depois de publicar a topologia, o Construtor de Topologias verá uma mensagem que inclui o seguinte</span><span class="sxs-lookup"><span data-stu-id="c0e91-215">After publishing the topology, Topology Builder you will see a message that includes the following</span></span>

   ```console
   Run the Uninstall-CsMirrorDatabase cmdlet to remove databases that are paired with following primary databases.
   ```

    <span data-ttu-id="c0e91-216">No entanto, não siga essa etapa e não digite, pois isso desinstalará  `Uninstall-CsMirrorDatabase` toda a configuração de espelhamento.</span><span class="sxs-lookup"><span data-stu-id="c0e91-216">However, do not follow that step, and do not type  `Uninstall-CsMirrorDatabase` as that would uninstall the entire mirroring configuration.</span></span>

4. <span data-ttu-id="c0e91-217">Para remover apenas a testemunha da configuração do SQL Server, siga as instruções em Remover a testemunha de uma sessão de espelhamento de banco de dados [(SQL Server).](https://go.microsoft.com/fwlink/p/?LinkId=268456)</span><span class="sxs-lookup"><span data-stu-id="c0e91-217">To remove just the witness from the SQL Server configuration, follow the instructions in [Remove the Witness from a Database Mirroring Session (SQL Server)](https://go.microsoft.com/fwlink/p/?LinkId=268456).</span></span>


