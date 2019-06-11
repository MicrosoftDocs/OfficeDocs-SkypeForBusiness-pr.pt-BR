---
title: 'Lync Server 2013: associando um repositório de monitoramento a um pool de front-end'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Associating a monitoring store with a Front End pool
ms:assetid: d3a20d5e-3f24-4cff-bc9b-4f84fea30e6b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205271(v=OCS.15)
ms:contentKeyID: 48185439
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4c1153d0d20cf5a3855a36f8d7aa24a8d9d4680b
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34836907"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="associating-a-monitoring-store-with-a-front-end-pool-in-lync-server-2013"></a><span data-ttu-id="5271d-102">Associando um armazenamento de monitoramento a um pool de front-end no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5271d-102">Associating a monitoring store with a Front End pool in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5271d-103">_**Tópico da última modificação:** 2013-04-22_</span><span class="sxs-lookup"><span data-stu-id="5271d-103">_**Topic Last Modified:** 2013-04-22_</span></span>

<span data-ttu-id="5271d-104">No Microsoft Lync Server 2013, os dados de monitoramento só podem ser coletados em pools front-ends que foram associados a uma loja de monitoramento, uma tarefa geralmente realizada para você definir um pool de front-end no construtor de topologias.</span><span class="sxs-lookup"><span data-stu-id="5271d-104">In Microsoft Lync Server 2013 monitoring data can only be collected on Front End pools that have been associated with a monitoring store, a task typically carried out you define a Front End pool in Topology Builder.</span></span> <span data-ttu-id="5271d-105">Para associar um repositório de monitoramento a um novo pool de front-end, verifique se você selecionou o monitoramento de opções **(a gravação de detalhes da chamada e o registro em log de métricas de qualidade de experiência)** na página **selecionar recursos** do assistente para definir novo pool de front-ends.</span><span class="sxs-lookup"><span data-stu-id="5271d-105">To associate a monitoring store with a new Front End pool, make sure that you select the option **Monitoring (call detail recording and logging of quality of experience metrics)** on the **Select Features** page of the Define New Front End Pool wizard.</span></span> <span data-ttu-id="5271d-106">Observe que, se você selecionar essa opção, também deverá especificar um repositório SQL para concluir o assistente; no entanto, essa loja não precisa existir no momento em que você executar o assistente.</span><span class="sxs-lookup"><span data-stu-id="5271d-106">Note that, if you select this option, you must also specify a SQL store in order to complete the wizard; however, this store does not have to exist at the time you run the wizard.</span></span> <span data-ttu-id="5271d-107">Isso significa que você pode primeiro associar um pool a um armazenamento de monitoramento e depois configurar posteriormente e configurar essa loja.</span><span class="sxs-lookup"><span data-stu-id="5271d-107">That means that you can first associate a pool with a monitoring store, then later setup and configure that store.</span></span>

<span data-ttu-id="5271d-108">Em alternativa, é possível associar um pool de front-ends existente com um repositório de monitoramento novo ou diferente ao concluir o seguinte procedimento:</span><span class="sxs-lookup"><span data-stu-id="5271d-108">Alternatively, you can associate an existing Front End pool with a new or different monitoring store by completing the following procedure:</span></span>

1.  <span data-ttu-id="5271d-109">Clique em **Iniciar**, em **todos os programas**, em **Microsoft Lync Server 2013**e, em seguida, clique em **Construtor de topologias do Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="5271d-109">Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Topology Builder**.</span></span>

2.  <span data-ttu-id="5271d-110">Na caixa de diálogo **Construtor de Topologias**, selecione **Baixar topologia da implantação existente** e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="5271d-110">In the **Topology Builder** dialog box, select **Download Topology from existing deployment** and then click **OK**.</span></span>

3.  <span data-ttu-id="5271d-p102">Na caixa de diálogo **Salvar como**, insira um nome de arquivo para sua topologia atual e clique em **Salvar**. A topologia salva poderá ser recuperada posteriormente e republicada em caso que haja problemas com a nova topologia.</span><span class="sxs-lookup"><span data-stu-id="5271d-p102">In the **Save As** dialog box, enter a file name for your current topology and then click **Save**. The saved topology can later be retrieved and re-published in case there are problems with the new topology.</span></span>

4.  <span data-ttu-id="5271d-113">No construtor de topologias, expanda o **Lync Server 2013**, expanda o nome do site que contém o pool de front-end e clique em expandir **grupos de front-end do Enterprise Edition**.</span><span class="sxs-lookup"><span data-stu-id="5271d-113">In Topology Builder, expand **Lync Server 2013**, expand the name of the site containing the Front End pool, then click expand **Enterprise Edition Front End pools**.</span></span>

5.  <span data-ttu-id="5271d-114">Clique com o botão direito no nome do pool a ser associado com o repositório de monitoramento e clique em **Editar propriedades**.</span><span class="sxs-lookup"><span data-stu-id="5271d-114">Right-click the name of the pool to be associated with the monitoring store and then click **Edit Properties**.</span></span>

6.  <span data-ttu-id="5271d-p103">Na caixa de diálogo **Editar propriedades**, na guia **Geral**, selecione a opção **Monitoramento (CDR e métricas de QoE)** e selecione um banco de dados existente do SQL Server na lista suspensa **Monitoramento do repositório do SQL Server**. (Você também pode clicar em **Novo** para associar o pool a um novo repositório do banco de dados.) Se você escolher usar um novo repositório do banco de dados, na caixa de diálogo **Definir novo repositório SQL**, insira o FQDN do computador do SQL Server na caixa **FQDN do SQL Server**. Se você deseja usar a instância padrão do SQL Server para esse repositório, selecione **Instância padrão**; caso contrário, selecione **Instância nomeada** e insira o nome da instância na caixa **Instância nomeada**.</span><span class="sxs-lookup"><span data-stu-id="5271d-p103">In the **Edit Properties** dialog box, on the **General** tab, select the option **Monitoring (CDR and QoE metrics)** and then select an existing SQL Server database from the **Monitoring SQL Server store** dropdown list. (Or, click **New** to associate the pool with a new database store.) If you choose to use a new database store then, in the **Define New SQL Store** dialog box, enter the fully qualified domain name of the SQL Server computer in the **Sql Server FQDN** box. If you want to use the default SQL Server instance for that store select **Default Instance**; otherwise select **Named Instance** and enter the instance name in the **Named Instance** box.</span></span>
    
    <span data-ttu-id="5271d-p104">A caixa de diálogo **Editar propriedades** também oferece a opção de criar um espelho SQL para seu banco de dados de monitoramento (um espelho SQL permite manter duas cópias do seu banco de dados de monitoramento, uma cópia armazenada no computador do repositório de monitoramento e outra no computador do espelho SQL). Para habilitar o espelhamento, selecione **Essa instância SQL está na relação de espelho** e insira o número da porta para o servidor-espelho na caixa **Número da porta de espelhamento**.</span><span class="sxs-lookup"><span data-stu-id="5271d-p104">The **Edit Properties** dialog box also gives you the option of creating a SQL mirror for your monitoring database (a SQL mirror enables you to maintain two copies of your monitoring database, one copy stored on the monitoring store computer and the other on the SQL mirror computer). To enable mirroring, select T**his SQL instance is in mirroring relation** and enter the port number for the mirror server in the **Mirroring port number** box.</span></span>

7.  <span data-ttu-id="5271d-120">Na caixa de diálogo **Editar propriedades**, clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="5271d-120">In the **Edit Properties** dialog box, click **OK**.</span></span>

<span data-ttu-id="5271d-121">Após associar o repositório de monitoramento a um pool de front-ends, você deverá publicar a nova topologia antes de as alterações entrarem em vigor.</span><span class="sxs-lookup"><span data-stu-id="5271d-121">After associating the monitoring store with a Front End pool you must publish the new topology before the changes take effect.</span></span> <span data-ttu-id="5271d-122">Para publicar sua nova topologia, complete as seguintes etapas no construtor de topologias:</span><span class="sxs-lookup"><span data-stu-id="5271d-122">To publish your new topology, complete the following steps in Topology Builder:</span></span>

1.  <span data-ttu-id="5271d-123">Clique em **Ação**, aponte para **Topologia** e clique em **Publicar**.</span><span class="sxs-lookup"><span data-stu-id="5271d-123">Click **Action**, point to **Topology**, and then click **Publish**.</span></span>

2.  <span data-ttu-id="5271d-124">No assistente Publicar topologia, na página **Publicar a topologia**, clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="5271d-124">In the Publish Topology wizard, on the **Publish the topology** page, click **Next**.</span></span>

3.  <span data-ttu-id="5271d-125">Na página **Assistente de publicação concluído**, clique em **Concluir**.</span><span class="sxs-lookup"><span data-stu-id="5271d-125">On the **Publishing wizard complete** page, click **Finish**.</span></span>

<span data-ttu-id="5271d-126">Após a topologia ser publicada, é possível instalar o banco de dados de monitoramento no computador que hospedará o repositório de monitoramento.</span><span class="sxs-lookup"><span data-stu-id="5271d-126">After the topology has been published you can then install the monitoring database on the computer that will host the monitoring store.</span></span> <span data-ttu-id="5271d-127">O banco de dados de monitoramento pode ser instalado usando o Shell de gerenciamento do Lync Server e o Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="5271d-127">The monitoring database can be installed by using the Lync Server Management Shell and Windows PowerShell.</span></span> <span data-ttu-id="5271d-128">Para instalar o banco de dados localmente (ou seja, instalar o banco de dados no mesmo computador em que você está executando o Shell de gerenciamento do Lync Server), inicie o Shell de gerenciamento no computador apropriado e, em seguida, digite o seguinte comando e pressione ENTER:</span><span class="sxs-lookup"><span data-stu-id="5271d-128">To install the database locally (that is, to install the database on the same computer where you are running the Lync Server Management Shell), start the Management Shell on the appropriate computer, then type in the following command and press ENTER:</span></span>

    Install-CsDatabase -LocalDatabases

<span data-ttu-id="5271d-129">Quando você executar o comando anterior, install-CsDatabase lerá a topologia do Lync Server atual, determinará quais bancos de dados precisam ser instalados no computador local e, em seguida, instalar e configurar automaticamente cada um desses bancos de dados.</span><span class="sxs-lookup"><span data-stu-id="5271d-129">When you run the preceding command, Install-CsDatabase will read the current Lync Server topology, determine which databases need to be installed on the local computer, and then automatically install and configure each of those databases.</span></span>

<span data-ttu-id="5271d-130">Para instalar o banco de dados em um computador remoto (isto é, um computador diferente daquele onde o Shell de Gerenciamento está executando), você deve incluir pelo menos dois parâmetros: o parâmetro ConfiguredDatabases e o parâmetro SqlServerFqdn.</span><span class="sxs-lookup"><span data-stu-id="5271d-130">To install the database on a remote computer (that is, a computer other than the computer where the Management Shell is running) you must include at least two parameters: the ConfiguredDatabases parameter and the SqlServerFqdn parameter.</span></span> <span data-ttu-id="5271d-131">Esses parâmetros dizem para o cmdlet Install-CsDatabase recuperar a topologia do Lync Server e instalar e configurar os bancos de dados necessários no computador especificado pelo parâmetro SqlServerFqdn.</span><span class="sxs-lookup"><span data-stu-id="5271d-131">These parameters tell the Install-CsDatabase cmdlet to retrieve the Lync Server topology and then install and configure the required databases on the computer specified by the SqlServerFqdn parameter.</span></span> <span data-ttu-id="5271d-132">O parâmetro SqlServerFqdn deve usar um valor de parâmetro representando o FQDN do computador onde os bancos de dados devem ser instalados.</span><span class="sxs-lookup"><span data-stu-id="5271d-132">The SqlServerFqdn parameter must use a parameter value representing the fully qualified domain name of the computer where the databases are to be installed.</span></span>

<span data-ttu-id="5271d-133">Por exemplo, este comando instala o banco de dados de monitoramento no computador atl-sql-001.litwareinc.com:</span><span class="sxs-lookup"><span data-stu-id="5271d-133">For example, this command installs the monitoring database on the computer atl-sql-001.litwareinc.com:</span></span>

    Install-CsDatabase -ConfiguredDatabases -SqlServerFqdn atl-sql-001.litwareinc.com

<span data-ttu-id="5271d-134">Você também pode instalar o banco de dados de monitoramento executando o assistente de implantação do Lync Server no computador que hospedará a loja de monitoramento.</span><span class="sxs-lookup"><span data-stu-id="5271d-134">Alternatively, you can install the monitoring database by running the Lync Server Deployment Wizard on the computer that will host the monitoring store.</span></span> <span data-ttu-id="5271d-135">Para fazer isso, faça o login no computador em questão e conclua o seguinte procedimento:</span><span class="sxs-lookup"><span data-stu-id="5271d-135">To do this, log on to the appropriate computer and complete the following procedure:</span></span>

1.  <span data-ttu-id="5271d-136">Clique em **Iniciar**, em **todos os programas**, em **Microsoft Lync Server 2013**e, em seguida, clique em **Assistente de implantação do Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="5271d-136">Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Deployment Wizard**.</span></span>

2.  <span data-ttu-id="5271d-137">No assistente de implantação, clique em **instalar ou atualizar o sistema do Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="5271d-137">In the Deployment Wizard, click **Install or Update Lync Server System**.</span></span>

3.  <span data-ttu-id="5271d-138">Na página **implantar** , em **etapa 2: configurar ou remover componentes do Lync Server**, clique **novamente em executar**.</span><span class="sxs-lookup"><span data-stu-id="5271d-138">On the **Deploy** page, under **Step 2: Setup or Remove Lync Server Components**, click **Run Again**.</span></span>

4.  <span data-ttu-id="5271d-139">No assistente de configuração de componentes do Lync Server, na página **configurar componentes do Lync Server** , clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="5271d-139">In the Setup Lync Server components wizard, on the **Setup Lync Server components** page, click **Next**.</span></span>

5.  <span data-ttu-id="5271d-140">Na página **especificar caminho para MSIs** , digite o caminho para o arquivo OCScore. msi (um arquivo incluído na mídia de instalação do Lync Server) e clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="5271d-140">On the **Specify path to MSIs** page, type the path to the file Ocscore.msi (a file included with your Lync Server installation media) and then click **Next**.</span></span>

6.  <span data-ttu-id="5271d-141">Na página **Executando comandos** clique em **Concluir**.</span><span class="sxs-lookup"><span data-stu-id="5271d-141">On the **Executing Commands** page, click **Finish**.</span></span>

<span data-ttu-id="5271d-142">Para garantir que todos os serviços do Lync Server necessários tenham começado, clique em **executar** abaixo do título **etapa 4: Iniciar serviços** na página **implantar**</span><span class="sxs-lookup"><span data-stu-id="5271d-142">To ensure that all the required Lync Server services have started, click **Run** under the heading **Step 4: Start Services** on the **Deploy** page</span></span>

</div>

<span> </span>

</div>

</div>

</div>

