---
title: Implantar um Grupo de Disponibilidade AlwaysOn em um Servidor Back-End no Skype for Business Server 2015
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.date: 2/14/2018
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: c93c01e6-626c-40ad-92dd-373b0fe9189f
description: Implante a implantação de um grupo de disponibilidade do AlwaysOn no seu Skype (instalação) para o servidor de negócios.
ms.openlocfilehash: 858f8cd317ecccde315475bc6489c74d79bf72c6
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/28/2018
---
# <a name="deploy-an-alwayson-availability-group-on-a-back-end-server-in-skype-for-business-server-2015"></a><span data-ttu-id="94040-103">Implantar um Grupo de Disponibilidade AlwaysOn em um Servidor Back-End no Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="94040-103">Deploy an AlwaysOn Availability Group on a Back End Server in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="94040-104">Implante a implantação de um grupo de disponibilidade do AlwaysOn no seu Skype (instalação) para o servidor de negócios.</span><span class="sxs-lookup"><span data-stu-id="94040-104">Deploy (install) an AlwaysOn Availability Group in your Skype for Business Server deployment.</span></span>
  
<span data-ttu-id="94040-105">Como você implanta um grupo de disponibilidade do AlwaysOn depende se você estiver implantando em um novo pool, um pool existente que usa espelhamento ou um pool existente que tem atualmente sem alta disponibilidade para o banco de dados de Back-End.</span><span class="sxs-lookup"><span data-stu-id="94040-105">How you deploy an AlwaysOn Availability Group depends on whether you are deploying it in a new pool, an existing pool that uses mirroring, or an existing pool that currently has no high availability for the Back End database.</span></span>
  
> [!NOTE]
> <span data-ttu-id="94040-106">Usar um grupo de disponibilidade do AlwaysOn com uma função de servidor de Chat persistente não é suportado.</span><span class="sxs-lookup"><span data-stu-id="94040-106">Using an AlwaysOn Availability Group with a Persistent Chat Server role is not supported.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="94040-107">Nomes de instância para várias instâncias do grupo de disponibilidade do AlwaysOn devem ser o mesmo.</span><span class="sxs-lookup"><span data-stu-id="94040-107">Instance names for multiple AlwaysOn Availability Group instances must be the same.</span></span> 
  
- [<span data-ttu-id="94040-108">Implantar um Grupo de Disponibilidade AlwaysOn em um novo Pool de Front-Ends</span><span class="sxs-lookup"><span data-stu-id="94040-108">Deploy an AlwaysOn Availability Group on a new Front End pool</span></span>](alwayson-availability-group.md#BKMK_NewPool_CreateAlwaysOnGroup)
    
- [<span data-ttu-id="94040-109">Implantar um Grupo de disponibilidade AlwaysOn em um pool existente que usa espelhamento de banco de dados</span><span class="sxs-lookup"><span data-stu-id="94040-109">Deploy an AlwaysOn Availability Group on an existing pool that uses database mirroring</span></span>](alwayson-availability-group.md#BKMK_MirroredPool_CreateAlwaysOnGroup)
    
- [<span data-ttu-id="94040-110">Implantar um Grupo de disponibilidade AlwaysOn em um pool existente que não usa espelhamento de banco de dados</span><span class="sxs-lookup"><span data-stu-id="94040-110">Deploy an AlwaysOn Availability Group on an existing pool that does not use database mirroring</span></span>](alwayson-availability-group.md#BKMK_NoHAPool_CreateAlwaysOnGroup)
    
## <a name="deploy-an-alwayson-availability-group-on-a-new-front-end-pool"></a><span data-ttu-id="94040-111">Implantar um Grupo de Disponibilidade AlwaysOn em um novo Pool de Front-Ends</span><span class="sxs-lookup"><span data-stu-id="94040-111">Deploy an AlwaysOn Availability Group on a new Front End pool</span></span>
<span data-ttu-id="94040-112"><a name="BKMK_NewPool_CreateAlwaysOnGroup"> </a></span><span class="sxs-lookup"><span data-stu-id="94040-112"></span></span>

1. <span data-ttu-id="94040-113">Configure o cluster de Failover do Windows Server em todos os servidores de banco de dados que farão parte do grupo de disponibilidade do AlwaysOn.</span><span class="sxs-lookup"><span data-stu-id="94040-113">Set up Windows Server Failover Clustering on all the database servers which will be part of the AlwaysOn Availability Group.</span></span> <span data-ttu-id="94040-114">Em cada servidor, faça o seguinte:</span><span class="sxs-lookup"><span data-stu-id="94040-114">On each server, do the following</span></span>
    
   - <span data-ttu-id="94040-115">Abra o Server Manager e clique em **Adicionar funções e recurso**.</span><span class="sxs-lookup"><span data-stu-id="94040-115">Open Server Manager and click **Add roles and features**.</span></span>
    
   - <span data-ttu-id="94040-p102">Clique em **Avançar** até chegar à caixa **Selecionar recursos**. Aqui, marque a caixa de seleção **Clustering de Failover**.</span><span class="sxs-lookup"><span data-stu-id="94040-p102">Click **Next** until you reach the **Select features** box. Here, select the **Failover Clustering** check box.</span></span>
    
   - <span data-ttu-id="94040-118">Na caixa **Adicionar recursos necessários para o Clustering de Failover?**, clique em **Adicionar Recursos**.</span><span class="sxs-lookup"><span data-stu-id="94040-118">In the **Add features that are required for Failover Clustering?** box, click **Add Features**.</span></span>
    
   - <span data-ttu-id="94040-119">Clique em **Instalar**.</span><span class="sxs-lookup"><span data-stu-id="94040-119">Click **Install**.</span></span>
    
2. <span data-ttu-id="94040-120">Validar a configuração de cluster.</span><span class="sxs-lookup"><span data-stu-id="94040-120">Validate the cluster configuration.</span></span>
    
   - <span data-ttu-id="94040-121">No Server Manager, clique no menu **Ferramentas** e, em seguida, clique em **Gerenciador de Cluster de Failover**.</span><span class="sxs-lookup"><span data-stu-id="94040-121">In Server Manager, click the **Tools** menu and then click **Failover Cluster Manager**.</span></span>
    
   - <span data-ttu-id="94040-122">Em **Ações** no lado direito da tela, clique em **Validar Configuração**.</span><span class="sxs-lookup"><span data-stu-id="94040-122">Under **Actions** on the right side of the screen, click **Validate Configuration**.</span></span>
    
   - <span data-ttu-id="94040-123">Na página **Antes de começar**, clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="94040-123">On the **Before You Begin** page, click **Next**.</span></span>
    
   - <span data-ttu-id="94040-124">Selecione os servidores a serem adicionados ao cluster e clique em **Executar todos os testes**.</span><span class="sxs-lookup"><span data-stu-id="94040-124">Select the servers to add to the cluster, and then click **Run all tests**.</span></span>
    
   - <span data-ttu-id="94040-125">Na caixa de**Resumo** , verifique quaisquer erros que o Assistente de relatórios.</span><span class="sxs-lookup"><span data-stu-id="94040-125">In the**Summary** box, check any errors that the wizard reports.</span></span> <span data-ttu-id="94040-126">Clique em **Concluir** para concluir a validação.</span><span class="sxs-lookup"><span data-stu-id="94040-126">Then click **Finish** to complete the validation.</span></span>
    
    <span data-ttu-id="94040-p104">O assistente provavelmente mostrará diversos avisos, especialmente se você não estiver usando armazenamento compartilhado. Não é necessário usar o armazenamento compartilhado. No entanto, se você vir alguma mensagem de **Erro**, deverá corrigir esses problemas antes de continuar.</span><span class="sxs-lookup"><span data-stu-id="94040-p104">The wizard will probably report several warnings, especially if you are not using shared storage. You are not required to use shared storage. However, if you see any **Error** messages, you must fix those issues before continuing.</span></span>
    
3. <span data-ttu-id="94040-130">Criar o cluster.</span><span class="sxs-lookup"><span data-stu-id="94040-130">Create the cluster.</span></span>
    
   - <span data-ttu-id="94040-131">No assistente de **Gerenciamento de Cluster de Failover**, clique com o botão direito do mouse em **Gerenciamento de Cluster de Failover** e, em seguida, clique em **Criar Cluster**.</span><span class="sxs-lookup"><span data-stu-id="94040-131">In the **Failover Cluster Management** wizard, right-click **Failover Cluster Management**, then click **Create Cluster**.</span></span>
    
   - <span data-ttu-id="94040-132">Na página **Antes de começar**, clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="94040-132">On the **Before You Begin** page, click **Next**.</span></span>
    
   - <span data-ttu-id="94040-p105">Adicione o nome e o endereço IP do cluster. Quando as definições forem validadas, clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="94040-p105">Add the cluster name and IP address. When the settings are validated, click **Next**.</span></span>
    
   - <span data-ttu-id="94040-135">Na página Confirmação, clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="94040-135">On the Confirmation page, click **Next**.</span></span>
    
   - <span data-ttu-id="94040-136">Depois que o cluster for criado, clique em **Concluir**.</span><span class="sxs-lookup"><span data-stu-id="94040-136">After the cluster is created, click **Finish**.</span></span>
    
4. <span data-ttu-id="94040-p106">Recomendamos que você defina as configurações de quorum do cluster para usar uma testemunha de compartilhamento de arquivos. Para isso, siga estas instruções:</span><span class="sxs-lookup"><span data-stu-id="94040-p106">We recommend that you configure the cluster quorum settings to use a file share witness. To do so, use these steps:</span></span>
    
   - <span data-ttu-id="94040-139">Clique com o botão direito do mouse no nome do cluster, em **Mais Ações** e, em seguida, em **Configurar Quorum do Cluster**.</span><span class="sxs-lookup"><span data-stu-id="94040-139">Right-click the cluster name, click **More Actions**, and click **Configure Cluster Quorum Settings**.</span></span>
    
   - <span data-ttu-id="94040-140">Na página **Selecionar Opção de Configuração de Quorum**, clique em **Selecione a testemunha de Quorum**.</span><span class="sxs-lookup"><span data-stu-id="94040-140">In the **Select Quorum Configuration Option** page, click **Select the quorum witness**.</span></span>
    
   - <span data-ttu-id="94040-141">Na página **Selecione a testemunha de Quorum**, clique em **Configurar uma testemunha de compartilhamento de arquivos**.</span><span class="sxs-lookup"><span data-stu-id="94040-141">In the **Select Quorum Witness** page, click **Configure a file share witness**.</span></span>
    
   - <span data-ttu-id="94040-142">Na página **Configurar Testemunha de Compartilhamento de Arquivo**, digite o caminho do compartilhamento de arquivos que você deseja usar e clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="94040-142">In the **Configure File Share Witness** page, type the path of the file share you want to use, and then click **Next**.</span></span>
    
   - <span data-ttu-id="94040-143">Na página **Confirmação**, clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="94040-143">On the **Confirmation** page, click **Next**.</span></span>
    
5. <span data-ttu-id="94040-144">Em cada servidor do cluster, habilite Sempre ativo no SQL Server Configuration Manager.</span><span class="sxs-lookup"><span data-stu-id="94040-144">On each server in the cluster, enable Always On in SQL Server Configuration Manager.</span></span>
    
   - <span data-ttu-id="94040-p107">Abra o SQL Server Configuration Manager. Na árvore no lado esquerdo da tela, clique em **Serviços do SQL Server** e, em seguida, clique duas vezes no serviço SQL Server. </span><span class="sxs-lookup"><span data-stu-id="94040-p107">Open SQL Server Configuration Manager. In the tree on the left side of the screen, click **SQL Server Services**, then double-click the SQL Server service.</span></span> 
    
   - <span data-ttu-id="94040-p108">Na caixa **Propriedades**, selecione a guia **Alta Disponibilidade AlwaysOn**. Marque a caixa de seleção **Habilitar Grupos de Disponibilidade AlwaysOn**. Reinicie o serviço SQL Server quando solicitado.</span><span class="sxs-lookup"><span data-stu-id="94040-p108">In the **Properties** box, select the **AlwaysOn High Availability** tab. Select the **Enable AlwaysOn Availability Groups** check box. Restart the SQL Server service when prompted.</span></span>
    
6. <span data-ttu-id="94040-149">Criar o grupo de disponibilidade.</span><span class="sxs-lookup"><span data-stu-id="94040-149">Create the availability group.</span></span>
    
   - <span data-ttu-id="94040-150">Abra o SQL Server Management Studio e conecte-se à instância do SQL Server.</span><span class="sxs-lookup"><span data-stu-id="94040-150">Open SQL Server Management Studio, and connect to the SQL Server instance.</span></span>
    
   - <span data-ttu-id="94040-p109">No Pesquisador de Objetos, expanda a pasta **Alta Disponibilidade AlwaysOn**. Clique com o botão direito do mouse na pasta **Grupos de Disponibilidade** e clique em **Assistente para Novo Grupo de Disponibilidade**.</span><span class="sxs-lookup"><span data-stu-id="94040-p109">In Object Explorer, expand the **AlwaysOn High Availability** folder. Right-click the **Availability Groups** folder and click **New Availability Group Wizard**.</span></span>
    
   - <span data-ttu-id="94040-153">Se a página **Introdução** for exibida, clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="94040-153">If the **Introduction** page appears, click **Next**.</span></span>
    
   - <span data-ttu-id="94040-154">Na página **Especificar Nome do Grupo de Disponibilidade**, digite o nome do Grupo de disponibilidade e clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="94040-154">In the **Specify Availability Group Name** page, type the name of the Availability group, and click **Next**.</span></span>
    
   - <span data-ttu-id="94040-155">Na página Selecionar bancos de dados, selecione os bancos de dados que você deseja incluir no grupo de disponibilidade do AlwaysOn.</span><span class="sxs-lookup"><span data-stu-id="94040-155">In the Select Databases page, select the databases that you want to include in the AlwaysOn Availability Group.</span></span> <span data-ttu-id="94040-156">Then click **Next**.</span><span class="sxs-lookup"><span data-stu-id="94040-156">Then click **Next**.</span></span>
    
    <span data-ttu-id="94040-157">Não inclua o **ReportServer**, **ReportServerTempDB**ou bancos de dados de Chat persistente no grupo de disponibilidade do AlwaysOn, como eles não são suportados neste cenário.</span><span class="sxs-lookup"><span data-stu-id="94040-157">Do not include the **ReportServer**, **ReportServerTempDB**, or Persistent Chat databases in the AlwaysOn Availability Group, as these are not supported in this scenario.</span></span> <span data-ttu-id="94040-158">Você pode incluir todos os outro Skype para bancos de dados do servidor de negócios no grupo de disponibilidade do AlwaysOn.</span><span class="sxs-lookup"><span data-stu-id="94040-158">You can include all other Skype for Business Server databases in the AlwaysOn Availability Group.</span></span>
    
   - <span data-ttu-id="94040-159">Na página **Especificar Réplicas**, clique na guia **Réplicas**. Clique no botão **Adicionar Réplicas** e conecte-se às outras instâncias do SQL que você incluiu como nós do Clustering de Failover do Windows Server.</span><span class="sxs-lookup"><span data-stu-id="94040-159">In the **Specify Replicas** page, click the **Replicas** tab. Then click the **Add Replicas** button, and connect to the other SQL instances that you joined as nodes of the Windows Server Failover Cluster.</span></span>
    
   - <span data-ttu-id="94040-p112">Para cada instância, selecione as opções **Failover Automático** e **Confirmação Síncrona**. Não selecione a opção **Secundária Legível**.</span><span class="sxs-lookup"><span data-stu-id="94040-p112">For each instance, select the **Automatic Failover** and **Synchronous Commit** options. Do not select the **Readable Secondary** option.</span></span>
    
   - <span data-ttu-id="94040-162">Clique na guia **Pontos de Extremidade** e verifique se o **Número da Porta** está definido como 5022.</span><span class="sxs-lookup"><span data-stu-id="94040-162">Click the **Endpoints** tab and verify that **Port Number** is set to 5022.</span></span>
    
   - <span data-ttu-id="94040-p113">Clique na guia **Ouvinte** e selecione a opção **Criar um ouvinte de grupo de disponibilidade**. Nesta opção, digite um nome para o ouvinte e defina a **Porta** como 1433 (outras portas não são suportadas para esta opção).</span><span class="sxs-lookup"><span data-stu-id="94040-p113">Click the **Listener** tab, and select the **Create an availability group listener** option. Under that option, type a name for the listener, and set the **Port** to 1433 (other ports are not supported for this option).</span></span>
    
   - <span data-ttu-id="94040-165">Clique em **Adicionar** e, na caixa **Endereço IPv4**, forneça o endereço IP virtual de sua preferência e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="94040-165">Click **Add**, and then in the **IPv4 Address** box, provide your preferred virtual IP address, and then click **OK**.</span></span>
    
   - <span data-ttu-id="94040-p114">Na página **Selecionar Sincronização de Dados Inicial**, selecione Completo, especifique uma pasta que possa ser acessada pelas réplicas e para a qual a conta do serviço SQL Server usada por ambas as réplicas tenha permissões de Gravação. Clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="94040-p114">In the **Select Initial Data Synchronization** page, select Full, and specify a folder that is accessible to the replicas, and that the SQL Server service account used by both replicas has Write permissions for. Then click **Next**.</span></span>
    
    <span data-ttu-id="94040-p115">Este compartilhamento de arquivos será usado temporariamente quando você inicializar os bancos de dados. Se você usar bancos de dados grandes, recomendamos que você os inicie manualmente caso a largura de banda de sua rede não possa acomodar o tamanho dos bancos de dados de backup.</span><span class="sxs-lookup"><span data-stu-id="94040-p115">This file share will be used temporarily when you initialize the databases. If you are dealing with large databases, we recommend that you manually initialize them in case your network bandwidth cannot accommodate the size of the database backups.</span></span>
    
   - <span data-ttu-id="94040-170">Na página Validação, confira se as verificações de validação foram bem-sucedidas e, em seguida, clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="94040-170">In the Validation page, verify that all validation checks are successful, then click **Next**.</span></span>
    
   - <span data-ttu-id="94040-171">Na página**Resumo** , verifique se todas as configurações e clique em Concluir.</span><span class="sxs-lookup"><span data-stu-id="94040-171">In the**Summary** page, verify all settings and click Finish.</span></span>
    
7. <span data-ttu-id="94040-172">Use o construtor de topologias para criar o pool de Front-End, conforme explicado em [criar e publicar a nova topologia no Skype para Business Server 2015](../../deploy/install/create-and-publish-new-topology.md).</span><span class="sxs-lookup"><span data-stu-id="94040-172">Use Topology Builder to create the Front End pool, as explained in [Create and publish new topology in Skype for Business Server 2015](../../deploy/install/create-and-publish-new-topology.md).</span></span> <span data-ttu-id="94040-173">Quando você fizer isso, especifique o grupo de disponibilidade do AlwaysOn como o repositório SQL para o pool.</span><span class="sxs-lookup"><span data-stu-id="94040-173">When you do, specify the AlwaysOn Availability Group as the SQL store for the pool.</span></span>
    
8. <span data-ttu-id="94040-174">Após o pool e o grupo de disponibilidade do AlwaysOn são implantados, realize algumas etapas finais para certificar-se de que os logons do SQL estão em cada uma das réplicas no grupo de disponibilidade do AlwaysOn.</span><span class="sxs-lookup"><span data-stu-id="94040-174">After the pool and the AlwaysOn Availability Group are deployed, perform some final steps to make sure that the SQL logins are on each of the replicas in the AlwaysOn Availability Group.</span></span> 
    
   - <span data-ttu-id="94040-175">Abra o construtor de topologia, selecione **Baixar topologia da implantação existente**e clique em **Okey**.</span><span class="sxs-lookup"><span data-stu-id="94040-175">Open Topology Builder, select **Download topology from existing deployment**, and click **OK**.</span></span>
    
   - <span data-ttu-id="94040-176">Expanda o Skype for Business Server, expanda sua topologia e expanda **Repositórios do SQL Server**.</span><span class="sxs-lookup"><span data-stu-id="94040-176">Expand Skype for Business Server, expand your topology, and expand **SQL Server Stores**.</span></span> <span data-ttu-id="94040-177">Clique com o botão o repositório SQL do novo grupo de disponibilidade do AlwaysOn e, em seguida, clique em * * Editar propriedades * *.</span><span class="sxs-lookup"><span data-stu-id="94040-177">Right-click the SQL store of the new AlwaysOn Availability Group, and click ** Edit Properties**.</span></span>
    
    - <span data-ttu-id="94040-178">Na parte inferior da página, na caixa **FQDN do SQL Server** , altere o valor para o FQDN do ouvinte do grupo de disponibilidade do AlwaysOn.</span><span class="sxs-lookup"><span data-stu-id="94040-178">At the bottom of the page, in the **SQL Server FQDN** box, change the value to the FQDN of the Listener of the AlwaysOn Availability Group.</span></span>
    
   - <span data-ttu-id="94040-p118">Publique a topologia. No menu **Ação**, clique em **Topologia** e, em seguida, **Publicar**. Na página de confirmação, clique em **Avançar**. Aguarde alguns minutos para a nova topologia ser replicada.</span><span class="sxs-lookup"><span data-stu-id="94040-p118">Publish the topology. From the **Action** menu click **Topology** and then **Publish**. Then in the confirmation page click **Next**. Then wait a few minutes for the new topology to replicate.</span></span>
    
   - <span data-ttu-id="94040-183">Abra o SQL Server Management Studio e navegue até o grupo de disponibilidade do AlwaysOn.</span><span class="sxs-lookup"><span data-stu-id="94040-183">Open SQL Server Management Studio, and navigate to the AlwaysOn Availability Group.</span></span> <span data-ttu-id="94040-184">Faça failover para uma réplica secundária.</span><span class="sxs-lookup"><span data-stu-id="94040-184">Fail it over to a secondary replica.</span></span>
    
   - <span data-ttu-id="94040-185">Abra o Skype do Shell de gerenciamento do servidor de negócios e digite o seguinte cmdlet para criar logons do SQL nesta réplica:</span><span class="sxs-lookup"><span data-stu-id="94040-185">Open Skype for Business Server Management Shell and type the following cmdlet to create the SQL logins on this replica:</span></span>
    
   ```
   Install-CsDatabase -Update
   ```

   - <span data-ttu-id="94040-186">Repita as duas etapas anteriores (failover no grupo para uma réplica secundária e, em seguida, usar `Install-CsDatabase -Update`) para cada réplica no grupo.</span><span class="sxs-lookup"><span data-stu-id="94040-186">Repeat the previous two steps (fail over the group to a secondary replica, then use  `Install-CsDatabase -Update`) for each replica in the group.</span></span>
    
## <a name="deploy-an-alwayson-availability-group-on-an-existing-pool-that-uses-database-mirroring"></a><span data-ttu-id="94040-187">Implantar um Grupo de disponibilidade AlwaysOn em um pool existente que usa espelhamento de banco de dados</span><span class="sxs-lookup"><span data-stu-id="94040-187">Deploy an AlwaysOn Availability Group on an existing pool that uses database mirroring</span></span>
<span data-ttu-id="94040-188"><a name="BKMK_MirroredPool_CreateAlwaysOnGroup"> </a></span><span class="sxs-lookup"><span data-stu-id="94040-188"></span></span>

> [!NOTE]
> <span data-ttu-id="94040-189">Se o pool que você está atualizando a hosts um grupo de disponibilidade do AlwaysOn Gerenciamento Central armazenar para sua organização, você deve primeiro mover o CMS para outro pool antes de atualizar este pool.</span><span class="sxs-lookup"><span data-stu-id="94040-189">If the pool you are upgrading to an AlwaysOn Availability Group hosts the Central Management store for your organization, you must first move the CMS to another pool before you upgrade this pool.</span></span> <span data-ttu-id="94040-190">Use o cmdlet Move-CsManagementServer para mover o pool.</span><span class="sxs-lookup"><span data-stu-id="94040-190">Use the Move-CsManagementServer cmdlet to move the pool.</span></span> <span data-ttu-id="94040-191">Se você não tiver outro pool em sua organização, você pode implantar um servidor Standard Edition temporariamente e mover o CMS para esse servidor antes de atualizar seu pool para o grupo de disponibilidade do AlwaysOn.</span><span class="sxs-lookup"><span data-stu-id="94040-191">If you do not have another pool in your organization, you can deploy a Standard Edition server temporarily and move the CMS to this server before you upgrade your pool to the AlwaysOn Availability Group.</span></span> 
  
1. <span data-ttu-id="94040-192">Failover de todos os dados do espelho para o nó principal abrindo Skype do Shell de gerenciamento do servidor de negócios e digitando o seguinte cmdlet.</span><span class="sxs-lookup"><span data-stu-id="94040-192">Fail over all data from the mirror to the principal node by opening Skype for Business Server Management Shell and typing the following cmdlet.</span></span>
    
   ```
   Invoke-CsDatabaseFailover -PoolFqdn <Pool FQDN> -DatabaseType <DatabaseType> -NewPrincipal "Primary"
   ```

    <span data-ttu-id="94040-p121">Repita esse cmdlet para cada tipo de banco de dados no pool. Você pode utilizar o seguinte cmdlet para localizar todos os tipos de bancos de dados armazenados neste pool.</span><span class="sxs-lookup"><span data-stu-id="94040-p121">Repeat this cmdlet for each database type in the pool. You can use the following cmdlet to find all the database types stored in this pool.</span></span>
     
   ```
   Get-CsPool -Identity <Pool FQDN>
   ```

2. <span data-ttu-id="94040-195">Usar o Construtor de Topologias para remover o espelhamento de banco de dados do pool</span><span class="sxs-lookup"><span data-stu-id="94040-195">Use Topology Builder to remove database mirroring from the pool</span></span>
    
   - <span data-ttu-id="94040-196">Abra o construtor de topologia.</span><span class="sxs-lookup"><span data-stu-id="94040-196">Open Topology Builder.</span></span> <span data-ttu-id="94040-197">Em sua topologia, expanda **Pools de Front-Ends Enterprise Edition**, clique com o botão direito do mouse no nome do pool e clique em **Editar Propriedades**.</span><span class="sxs-lookup"><span data-stu-id="94040-197">In your topology, expand **Enterprise Edition Front End Pools**, right-click the name of the pool, and click **Edit Properties**.</span></span>
    
   - <span data-ttu-id="94040-198">Para cada tipo de repositório SQL no pool, desmarque a caixa de seleção **Habilitar Espelhamento do Repositório SQL**.</span><span class="sxs-lookup"><span data-stu-id="94040-198">For each type of SQL store in the pool, clear the **Enable SQL Store Mirroring** check box.</span></span>
    
3. <span data-ttu-id="94040-p123">Publique a topologia alterada. No menu **Ação**, clique em **Topologia** e, em seguida, em **Publicar**. Na página de confirmação, clique em **Avançar**</span><span class="sxs-lookup"><span data-stu-id="94040-p123">Publish the changed topology. From the **Action** menu click **Topology** and then **Publish**. Then in the confirmation page click **Next**</span></span>
    
4. <span data-ttu-id="94040-202">Usar o SQL Server Management Studio para quebrar o espelho.</span><span class="sxs-lookup"><span data-stu-id="94040-202">Use SQL Server Management Studio to break the mirror.</span></span>
    
   - <span data-ttu-id="94040-p124">Abra o SQL Server Management Studio, navegue até seus bancos de dados, clique com o botão direito do mouse em **Tarefas** e clique em **Espelho**. Clique em **Remover Espelhamento** e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="94040-p124">Open SQL Server Management Studio, navigate to your databases, right-click **Tasks** and click **Mirror**. Then click **Remove Mirroring** and click **OK**.</span></span>
    
   - <span data-ttu-id="94040-205">Repita esse procedimento para todos os bancos de dados do pool que será convertida em um grupo de disponibilidade do AlwaysOn.</span><span class="sxs-lookup"><span data-stu-id="94040-205">Repeat this for all databases in the pool which will be converted to an AlwaysOn Availability Group.</span></span>
    
5. <span data-ttu-id="94040-206">Configure o cluster de Failover do Windows Server em todos os servidores de banco de dados que farão parte do grupo de disponibilidade do AlwaysOn.</span><span class="sxs-lookup"><span data-stu-id="94040-206">Set up Windows Server Failover Clustering on all the database servers which will be part of the AlwaysOn Availability Group.</span></span> <span data-ttu-id="94040-207">Em cada servidor, faça o seguinte:</span><span class="sxs-lookup"><span data-stu-id="94040-207">On each server, do the following</span></span>
    
   - <span data-ttu-id="94040-208">Abra o Server Manager e clique em **Adicionar funções e recurso**.</span><span class="sxs-lookup"><span data-stu-id="94040-208">Open Server Manager and click **Add roles and features**.</span></span>
    
   - <span data-ttu-id="94040-p126">Clique em **Avançar** até chegar à caixa **Selecionar recursos**. Aqui, marque a caixa de seleção **Clustering de Failover**.</span><span class="sxs-lookup"><span data-stu-id="94040-p126">Click **Next** until you reach the **Select features** box. Here, select the **Failover Clustering** check box.</span></span>
    
   - <span data-ttu-id="94040-211">Na caixa **Adicionar recursos necessários para o Clustering de Failover?**, clique em **Adicionar Recursos**.</span><span class="sxs-lookup"><span data-stu-id="94040-211">In the **Add features that are required for Failover Clustering?** box, click **Add Features**.</span></span>
    
   - <span data-ttu-id="94040-212">Clique em **Instalar**.</span><span class="sxs-lookup"><span data-stu-id="94040-212">Click **Install**.</span></span>
    
6. <span data-ttu-id="94040-213">Validar a configuração de cluster.</span><span class="sxs-lookup"><span data-stu-id="94040-213">Validate the cluster configuration.</span></span>
    
   - <span data-ttu-id="94040-214">No Server Manager, clique no menu **Ferramentas** e, em seguida, clique em **Gerenciador de Cluster de Failover**.</span><span class="sxs-lookup"><span data-stu-id="94040-214">In Server Manager, click the **Tools** menu and then click **Failover Cluster Manager**.</span></span>
    
   - <span data-ttu-id="94040-215">Em **Ações** no lado direito da tela, clique em **Validar Configuração**.</span><span class="sxs-lookup"><span data-stu-id="94040-215">Under **Actions** on the right side of the screen, click **Validate Configuration**.</span></span>
    
   - <span data-ttu-id="94040-216">Na página **Antes de começar**, clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="94040-216">On the **Before You Begin** page, click **Next**.</span></span>
    
   - <span data-ttu-id="94040-217">Selecione os servidores a serem adicionados ao cluster e clique em **Executar todos os testes**.</span><span class="sxs-lookup"><span data-stu-id="94040-217">Select the servers to add to the cluster, and then click **Run all tests**.</span></span>
    
   - <span data-ttu-id="94040-218">Na caixa de**Resumo** , verifique quaisquer erros que o Assistente de relatórios.</span><span class="sxs-lookup"><span data-stu-id="94040-218">In the**Summary** box, check any errors that the wizard reports.</span></span> <span data-ttu-id="94040-219">Clique em **Concluir** para concluir a validação.</span><span class="sxs-lookup"><span data-stu-id="94040-219">Then click **Finish** to complete the validation.</span></span>
    
    <span data-ttu-id="94040-p128">O assistente provavelmente mostrará diversos avisos, especialmente se você não estiver usando armazenamento compartilhado. Não é necessário usar o armazenamento compartilhado. No entanto, se você vir alguma mensagem de **Erro**, deverá corrigir esses problemas antes de continuar.</span><span class="sxs-lookup"><span data-stu-id="94040-p128">The wizard will probably report several warnings, especially if you are not using shared storage. You are not required to use shared storage. However, if you see any **Error** messages, you must fix those issues before continuing.</span></span>
    
7. <span data-ttu-id="94040-223">Criar o cluster.</span><span class="sxs-lookup"><span data-stu-id="94040-223">Create the cluster.</span></span>
    
   - <span data-ttu-id="94040-224">No assistente de **Gerenciamento de Cluster de Failover**, clique com o botão direito do mouse em **Gerenciamento de Cluster de Failover** e, em seguida, clique em **Criar Cluster**.</span><span class="sxs-lookup"><span data-stu-id="94040-224">In the **Failover Cluster Management** wizard, right-click **Failover Cluster Management**, then click **Create Cluster**.</span></span>
    
   - <span data-ttu-id="94040-225">Na página **Antes de começar**, clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="94040-225">On the **Before You Begin** page, click **Next**.</span></span>
    
   - <span data-ttu-id="94040-p129">Adicione o nome e o endereço IP do cluster. Quando as definições forem validadas, clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="94040-p129">Add the cluster name and IP address. When the settings are validated, click **Next**.</span></span>
    
   - <span data-ttu-id="94040-228">Na página Confirmação, clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="94040-228">On the Confirmation page, click **Next**.</span></span>
    
   - <span data-ttu-id="94040-229">Depois que o cluster for criado, clique em **Concluir**.</span><span class="sxs-lookup"><span data-stu-id="94040-229">After the cluster is created, click **Finish**.</span></span>
    
8. <span data-ttu-id="94040-p130">Recomendamos que você defina as configurações de quorum do cluster para usar uma testemunha de compartilhamento de arquivos. Para isso, siga estas instruções:</span><span class="sxs-lookup"><span data-stu-id="94040-p130">We recommend that you configure the cluster quorum settings to use a file share witness. To do so, use these steps:</span></span>
    
   - <span data-ttu-id="94040-232">Clique com o botão direito do mouse no nome do cluster, em **Mais Ações** e, em seguida, em **Configurar Quorum do Cluster**.</span><span class="sxs-lookup"><span data-stu-id="94040-232">Right-click the cluster name, click **More Actions**, and click **Configure Cluster Quorum Settings**.</span></span>
    
   - <span data-ttu-id="94040-233">Na página **Selecionar Opção de Configuração de Quorum**, clique em **Selecione a testemunha de Quorum**.</span><span class="sxs-lookup"><span data-stu-id="94040-233">In the **Select Quorum Configuration Option** page, click **Select the quorum witness**.</span></span>
    
   - <span data-ttu-id="94040-234">Na página **Selecione a testemunha de Quorum**, clique em **Configurar uma testemunha de compartilhamento de arquivos**.</span><span class="sxs-lookup"><span data-stu-id="94040-234">In the **Select Quorum Witness** page, click **Configure a file share witness**.</span></span>
    
   - <span data-ttu-id="94040-235">Na página **Configurar Testemunha de Compartilhamento de Arquivo**, digite o caminho do compartilhamento de arquivos que você deseja usar e clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="94040-235">In the **Configure File Share Witness** page, type the path of the file share you want to use, and then click **Next**.</span></span>
    
   - <span data-ttu-id="94040-236">Na página **Confirmação**, clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="94040-236">On the **Confirmation** page, click **Next**.</span></span>
    
9. <span data-ttu-id="94040-237">Em cada servidor do cluster, habilite Sempre ativo no SQL Server Configuration Manager.</span><span class="sxs-lookup"><span data-stu-id="94040-237">On each server in the cluster, enable Always On in SQL Server Configuration Manager.</span></span>
    
   - <span data-ttu-id="94040-p131">Abra o SQL Server Configuration Manager. Na árvore no lado esquerdo da tela, clique em **Serviços do SQL Server** e, em seguida, clique duas vezes no serviço SQL Server. </span><span class="sxs-lookup"><span data-stu-id="94040-p131">Open SQL Server Configuration Manager. In the tree on the left side of the screen, click **SQL Server Services**, then double-click the SQL Server service.</span></span> 
    
   - <span data-ttu-id="94040-p132">Na caixa **Propriedades**, selecione a guia **Alta Disponibilidade AlwaysOn**. Marque a caixa de seleção **Habilitar Grupos de Disponibilidade AlwaysOn**. Reinicie o serviço SQL Server quando solicitado.</span><span class="sxs-lookup"><span data-stu-id="94040-p132">In the **Properties** box, select the **AlwaysOn High Availability** tab. Select the **Enable AlwaysOn Availability Groups** check box. Restart the SQL Server service when prompted.</span></span>
    
10. <span data-ttu-id="94040-242">Criar o grupo de disponibilidade.</span><span class="sxs-lookup"><span data-stu-id="94040-242">Create the availability group.</span></span>
    
    - <span data-ttu-id="94040-243">Abra o SQL Server Management Studio e conecte-se à instância do SQL Server.</span><span class="sxs-lookup"><span data-stu-id="94040-243">Open SQL Server Management Studio, and connect to the SQL Server instance.</span></span>
    
    - <span data-ttu-id="94040-p133">No Pesquisador de Objetos, expanda a pasta **Alta Disponibilidade AlwaysOn**. Clique com o botão direito do mouse na pasta **Grupos de Disponibilidade** e clique em **Assistente para Novo Grupo de Disponibilidade**.</span><span class="sxs-lookup"><span data-stu-id="94040-p133">In Object Explorer, expand the **AlwaysOn High Availability** folder. Right-click the **Availability Groups** folder and click **New Availability Group Wizard**.</span></span>
    
    - <span data-ttu-id="94040-246">Se a página **Introdução** for exibida, clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="94040-246">If the **Introduction** page appears, click **Next**.</span></span>
    
    - <span data-ttu-id="94040-247">Na página **Especificar Nome do Grupo de Disponibilidade**, digite o nome do Grupo de disponibilidade e clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="94040-247">In the **Specify Availability Group Name** page, type the name of the Availability group, and click **Next**.</span></span>
    
    - <span data-ttu-id="94040-248">Na página Selecionar bancos de dados, selecione os bancos de dados que você deseja incluir no grupo de disponibilidade do AlwaysOn.</span><span class="sxs-lookup"><span data-stu-id="94040-248">In the Select Databases page, select the databases that you want to include in the AlwaysOn Availability Group.</span></span> <span data-ttu-id="94040-249">Then click **Next**.</span><span class="sxs-lookup"><span data-stu-id="94040-249">Then click **Next**.</span></span>
    
    <span data-ttu-id="94040-250">Não inclua o **ReportServer**, **ReportServerTempDB**ou bancos de dados de Chat persistente no grupo de disponibilidade do AlwaysOn, como eles não são suportados neste cenário.</span><span class="sxs-lookup"><span data-stu-id="94040-250">Do not include the **ReportServer**, **ReportServerTempDB**, or Persistent Chat databases in the AlwaysOn Availability Group, as these are not supported in this scenario.</span></span> <span data-ttu-id="94040-251">Você pode incluir todos os outro Skype para bancos de dados do servidor de negócios no grupo de disponibilidade do AlwaysOn.</span><span class="sxs-lookup"><span data-stu-id="94040-251">You can include all other Skype for Business Server databases in the AlwaysOn Availability Group.</span></span>
    
    - <span data-ttu-id="94040-252">Na página **Especificar Réplicas**, clique na guia **Réplicas**. Clique no botão **Adicionar Réplicas** e conecte-se às outras instâncias do SQL que você incluiu como nós do Clustering de Failover do Windows Server.</span><span class="sxs-lookup"><span data-stu-id="94040-252">In the **Specify Replicas** page, click the **Replicas** tab. Then click the **Add Replicas** button, and connect to the other SQL instances that you joined as nodes of the Windows Server Failover Cluster.</span></span>
    
    - <span data-ttu-id="94040-p136">Para cada instância, selecione as opções **Failover Automático** e **Confirmação Síncrona**. Não selecione a opção **Secundária Legível**.</span><span class="sxs-lookup"><span data-stu-id="94040-p136">For each instance, select the **Automatic Failover** and **Synchronous Commit** options. Do not select the **Readable Secondary** option.</span></span>
    
    - <span data-ttu-id="94040-255">Clique na guia **Pontos de Extremidade** e verifique se o **Número da Porta** está definido como 5022.</span><span class="sxs-lookup"><span data-stu-id="94040-255">Click the **Endpoints** tab and verify that **Port Number** is set to 5022.</span></span>
    
     - <span data-ttu-id="94040-p137">Clique na guia **Ouvinte** e selecione a opção **Criar um ouvinte de grupo de disponibilidade**. Nesta opção, digite um nome para o ouvinte e defina a **Porta** como 1433 (outras portas não são suportadas para esta opção).</span><span class="sxs-lookup"><span data-stu-id="94040-p137">Click the **Listener** tab, and select the **Create an availability group listener** option. Under that option, type a name for the listener, and set the **Port** to 1433 (other ports are not supported for this option).</span></span>
    
    - <span data-ttu-id="94040-258">Clique em **Adicionar** e, na caixa **Endereço IPv4**, forneça o endereço IP virtual de sua preferência e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="94040-258">Click **Add**, and then in the **IPv4 Address** box, provide your preferred virtual IP address, and then click **OK**.</span></span>
    
    - <span data-ttu-id="94040-p138">Na página **Selecionar Sincronização de Dados Inicial**, selecione Completo, especifique uma pasta que possa ser acessada pelas réplicas e para a qual a conta do serviço SQL Server usada por ambas as réplicas tenha permissões de Gravação. Clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="94040-p138">In the **Select Initial Data Synchronization** page, select Full, and specify a folder that is accessible to the replicas, and that the SQL Server service account used by both replicas has Write permissions for. Then click **Next**.</span></span>
    
    <span data-ttu-id="94040-p139">Este compartilhamento de arquivos será usado temporariamente quando você inicializar os bancos de dados. Se você usar bancos de dados grandes, recomendamos que você os inicie manualmente caso a largura de banda de sua rede não possa acomodar o tamanho dos bancos de dados de backup.</span><span class="sxs-lookup"><span data-stu-id="94040-p139">This file share will be used temporarily when you initialize the databases. If you are dealing with large databases, we recommend that you manually initialize them in case your network bandwidth cannot accommodate the size of the database backups.</span></span>
    
    - <span data-ttu-id="94040-263">Na página Validação, confira se as verificações de validação foram bem-sucedidas e, em seguida, clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="94040-263">In the Validation page, verify that all validation checks are successful, then click **Next**.</span></span>
    
    - <span data-ttu-id="94040-264">Na página **Resumo**, verifique todas as configurações e clique em Concluir.</span><span class="sxs-lookup"><span data-stu-id="94040-264">In the **Summary** page, verify all settings and click Finish.</span></span>
    
11. <span data-ttu-id="94040-265">Crie um novo repositório especificando o ouvinte do grupo de disponibilidade do AlwaysOn e especificando a entidade de segurança do espelho antigo como o nó primário do grupo de disponibilidade do AlwaysOn.</span><span class="sxs-lookup"><span data-stu-id="94040-265">Create a new store specifying the AlwaysOn Availability Group listener, and specifying the principal of the old mirror as the primary node of the AlwaysOn Availability Group.</span></span>
    
    - <span data-ttu-id="94040-266">Abra o construtor de topologia.</span><span class="sxs-lookup"><span data-stu-id="94040-266">Open Topology Builder.</span></span> <span data-ttu-id="94040-267">Em sua topologia, expanda **Componentes Compartilhados**, clique com o botão direito do mouse em **Repositórios do SQL Server** e clique em **Novo Repositório do SQL Server**.</span><span class="sxs-lookup"><span data-stu-id="94040-267">In your topology, expand **Shared Components**, right-click **SQL Server Stores**, and click **New SQL Server Store**.</span></span>
    
    - <span data-ttu-id="94040-268">Na página **Definir Novo Repositório SQL**, primeiro marque a caixa de seleção **Configurações de Alta Disponibilidade** e, em seguida, certifique-se de que a opção Grupos de Disponibilidade AlwaysOn do SQL aparece na caixa suspensa.</span><span class="sxs-lookup"><span data-stu-id="94040-268">In the **Define New SQL Store** page, first select the **High Availability Settings** check box, and then make sure that SQL AlwaysOn Availability Groups appears in the drop-down box.</span></span>
    
    - <span data-ttu-id="94040-269">Na caixa **FQDN do Ouvinte de Disponibilidade do SQL Server**, digite o FQDN do ouvinte que criou quando criou o grupo de disponibilidade.</span><span class="sxs-lookup"><span data-stu-id="94040-269">In the **SQL Server Availability Listener FQDN** box, type the FQDN of the listener you created when you created the availability group.</span></span>
    
    - <span data-ttu-id="94040-270">Na caixa **FQDN do SQL Server** , digite o FQDN do nó principal do grupo de disponibilidade do AlwaysOn e clique em **Okey**.</span><span class="sxs-lookup"><span data-stu-id="94040-270">In the **SQL Server FQDN** box, type the FQDN of the primary node of the AlwaysOn Availability Group, and then click **OK**.</span></span> <span data-ttu-id="94040-271">Ele deve ser a entidade de segurança do espelho antigo para esse repositório.</span><span class="sxs-lookup"><span data-stu-id="94040-271">This should be the principal of the old mirror for this store.</span></span>
    
12. <span data-ttu-id="94040-272">Associe o novo grupo de disponibilidade do AlwaysOn com o pool de Front-End.</span><span class="sxs-lookup"><span data-stu-id="94040-272">Associate the new AlwaysOn Availability Group with the Front End pool.</span></span>
    
    - <span data-ttu-id="94040-273">No construtor de topologia, clique com botão direito do pool para associar o grupo de disponibilidade do AlwaysOn e clique em **Editar propriedades**.</span><span class="sxs-lookup"><span data-stu-id="94040-273">In Topology Builder, right-click the pool to associate with the AlwaysOn Availability Group, and click **Edit Properties**.</span></span>
    
    - <span data-ttu-id="94040-274">Em **associações**, na caixa **Repositório do SQL Server** , selecione o grupo de disponibilidade do AlwaysOn.</span><span class="sxs-lookup"><span data-stu-id="94040-274">Under **Associations**, in the **SQL Server Store** box, select the AlwaysOn Availability Group.</span></span> <span data-ttu-id="94040-275">Selecione o grupo mesmo para outros bancos de dados no pool que você deseja mover para o grupo de disponibilidade do AlwaysOn.</span><span class="sxs-lookup"><span data-stu-id="94040-275">Select the same group for any other databases in the pool which you want to move to the AlwaysOn Availability Group.</span></span>
    
    - <span data-ttu-id="94040-276">Quando tiver certeza de que todos os bancos de dados necessários estão definidos para o grupo de disponibilidade do AlwaysOn, clique em **Okey**.</span><span class="sxs-lookup"><span data-stu-id="94040-276">When you're sure that all needed databases are set to the AlwaysOn Availability Group, click **OK**.</span></span>
    
13. <span data-ttu-id="94040-p143">Publique a topologia. No menu **Ação**, clique em **Topologia** e, em seguida, em **Publicar**. Na página de confirmação, clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="94040-p143">Publish the topology. From the **Action** menu click **Topology** and then **Publish**. Then in the confirmation page click **Next**.</span></span>
    
14. <span data-ttu-id="94040-280">Execute algumas etapas finais para certificar-se de que os logons do SQL estão em cada uma das réplicas no grupo de disponibilidade do AlwaysOn.</span><span class="sxs-lookup"><span data-stu-id="94040-280">Perform some final steps to make sure that the SQL logins are on each of the replicas in the AlwaysOn Availability Group.</span></span>
    
    - <span data-ttu-id="94040-281">Abra o construtor de topologia, selecione **Baixar topologia da implantação existente**e clique em **Okey**.</span><span class="sxs-lookup"><span data-stu-id="94040-281">Open Topology Builder, select **Download topology from existing deployment**, and click **OK**.</span></span>
    
    - <span data-ttu-id="94040-282">Expanda o Skype for Business Server, expanda sua topologia e expanda **Repositórios do SQL Server**.</span><span class="sxs-lookup"><span data-stu-id="94040-282">Expand Skype for Business Server, expand your topology, and expand **SQL Server Stores**.</span></span> <span data-ttu-id="94040-283">Clique com o botão o repositório SQL do novo grupo de disponibilidade do AlwaysOn e clique em **Editar propriedades**.</span><span class="sxs-lookup"><span data-stu-id="94040-283">Right-click the SQL store of the new AlwaysOn Availability Group, and click **Edit Properties**.</span></span>
    
    - <span data-ttu-id="94040-284">Na parte inferior da página, na caixa **FQDN do SQL Server** , altere o valor para o FQDN do ouvinte do grupo de disponibilidade do AlwaysOn.</span><span class="sxs-lookup"><span data-stu-id="94040-284">At the bottom of the page, in the **SQL Server FQDN** box, change the value to the FQDN of the Listener of the AlwaysOn Availability Group.</span></span>
    
    - <span data-ttu-id="94040-p145">Publique a topologia. No menu **Ação**, clique em **Topologia** e, em seguida, **Publicar**. Na página de confirmação, clique em **Avançar**. Aguarde alguns minutos para a nova topologia ser replicada.</span><span class="sxs-lookup"><span data-stu-id="94040-p145">Publish the topology. From the **Action** menu click **Topology** and then **Publish**. Then in the confirmation page click **Next**. Then wait a few minutes for the new topology to replicate.</span></span>
    
    - <span data-ttu-id="94040-289">Abra o SQL Server Management Studio e navegue até o grupo de disponibilidade do AlwaysOn.</span><span class="sxs-lookup"><span data-stu-id="94040-289">Open SQL Server Management Studio, and navigate to the AlwaysOn Availability Group.</span></span> <span data-ttu-id="94040-290">Faça failover para uma réplica secundária.</span><span class="sxs-lookup"><span data-stu-id="94040-290">Fail it over to a secondary replica.</span></span>
    
    - <span data-ttu-id="94040-291">Abra o Skype do Shell de gerenciamento do servidor de negócios e digite o seguinte cmdlet para criar logons do SQL nesta réplica:</span><span class="sxs-lookup"><span data-stu-id="94040-291">Open Skype for Business Server Management Shell and type the following cmdlet to create the SQL logins on this replica:</span></span>
    
    ```
    Install-CsDatabase -Update
    ```

    - <span data-ttu-id="94040-292">Repita as duas etapas anteriores (failover no grupo para uma réplica secundária e, em seguida, usar `Install-CsDatabase -Update`) para cada réplica no grupo.</span><span class="sxs-lookup"><span data-stu-id="94040-292">Repeat the previous two steps (fail over the group to a secondary replica, then use  `Install-CsDatabase -Update`) for each replica in the group.</span></span>
    
## <a name="deploy-an-alwayson-availability-group-on-an-existing-pool-that-does-not-use-database-mirroring"></a><span data-ttu-id="94040-293">Implantar um Grupo de disponibilidade AlwaysOn em um pool existente que não usa espelhamento de banco de dados</span><span class="sxs-lookup"><span data-stu-id="94040-293">Deploy an AlwaysOn Availability Group on an existing pool that does not use database mirroring</span></span>
<span data-ttu-id="94040-294"><a name="BKMK_NoHAPool_CreateAlwaysOnGroup"> </a></span><span class="sxs-lookup"><span data-stu-id="94040-294"></span></span>

> [!NOTE]
> <span data-ttu-id="94040-295">Se o pool que você está atualizando a hosts um grupo de disponibilidade do AlwaysOn Gerenciamento Central armazenar para sua organização, você deve primeiro mover o CMS para outro pool antes de atualizar este pool.</span><span class="sxs-lookup"><span data-stu-id="94040-295">If the pool you are upgrading to an AlwaysOn Availability Group hosts the Central Management store for your organization, you must first move the CMS to another pool before you upgrade this pool.</span></span> <span data-ttu-id="94040-296">Use o cmdlet Move-CsManagementServer para mover o pool.</span><span class="sxs-lookup"><span data-stu-id="94040-296">Use the Move-CsManagementServer cmdlet to move the pool.</span></span> <span data-ttu-id="94040-297">Se você não tiver outro pool em sua organização, você pode implantar um servidor Standard Edition temporariamente e mover o CMS para esse servidor antes de atualizar seu pool para o grupo de disponibilidade do AlwaysOn.</span><span class="sxs-lookup"><span data-stu-id="94040-297">If you do not have another pool in your organization, you can deploy a Standard Edition server temporarily and move the CMS to this server before you upgrade your pool to the AlwaysOn Availability Group.</span></span> 
  
1. <span data-ttu-id="94040-298">Configure o cluster de Failover do Windows Server em todos os servidores de banco de dados que farão parte do grupo de disponibilidade do AlwaysOn.</span><span class="sxs-lookup"><span data-stu-id="94040-298">Set up Windows Server Failover Clustering on all the database servers which will be part of the AlwaysOn Availability Group.</span></span> <span data-ttu-id="94040-299">Em cada servidor, faça o seguinte:</span><span class="sxs-lookup"><span data-stu-id="94040-299">On each server, do the following</span></span>
    
   - <span data-ttu-id="94040-300">Abra o Server Manager e clique em **Adicionar funções e recurso**.</span><span class="sxs-lookup"><span data-stu-id="94040-300">Open Server Manager and click **Add roles and features**.</span></span>
    
   - <span data-ttu-id="94040-p149">Clique em **Avançar** até chegar à caixa **Selecionar recursos**. Aqui, marque a caixa de seleção **Clustering de Failover**.</span><span class="sxs-lookup"><span data-stu-id="94040-p149">Click **Next** until you reach the **Select features** box. Here, select the **Failover Clustering** check box.</span></span>
    
   - <span data-ttu-id="94040-303">Na caixa **Adicionar recursos necessários para o Clustering de Failover?**, clique em **Adicionar Recursos**.</span><span class="sxs-lookup"><span data-stu-id="94040-303">In the **Add features that are required for Failover Clustering?** box, click **Add Features**.</span></span>
    
   - <span data-ttu-id="94040-304">Clique em **Instalar**.</span><span class="sxs-lookup"><span data-stu-id="94040-304">Click **Install**.</span></span>
    
2. <span data-ttu-id="94040-305">Validar a configuração de cluster.</span><span class="sxs-lookup"><span data-stu-id="94040-305">Validate the cluster configuration.</span></span>
    
   - <span data-ttu-id="94040-306">No Server Manager, clique no menu **Ferramentas** e, em seguida, clique em **Gerenciador de Cluster de Failover**.</span><span class="sxs-lookup"><span data-stu-id="94040-306">In Server Manager, click the **Tools** menu and then click **Failover Cluster Manager**.</span></span>
    
   - <span data-ttu-id="94040-307">Em **Ações** no lado direito da tela, clique em **Validar Configuração**.</span><span class="sxs-lookup"><span data-stu-id="94040-307">Under **Actions** on the right side of the screen, click **Validate Configuration**.</span></span>
    
   - <span data-ttu-id="94040-308">Na página **Antes de começar**, clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="94040-308">On the **Before You Begin** page, click **Next**.</span></span>
    
   - <span data-ttu-id="94040-309">Selecione os servidores a serem adicionados ao cluster e clique em **Executar todos os testes**.</span><span class="sxs-lookup"><span data-stu-id="94040-309">Select the servers to add to the cluster, and then click **Run all tests**.</span></span>
    
   - <span data-ttu-id="94040-310">Na caixa de**Resumo** , verifique quaisquer erros que o Assistente de relatórios.</span><span class="sxs-lookup"><span data-stu-id="94040-310">In the**Summary** box, check any errors that the wizard reports.</span></span> <span data-ttu-id="94040-311">Clique em **Concluir** para concluir a validação.</span><span class="sxs-lookup"><span data-stu-id="94040-311">Then click **Finish** to complete the validation.</span></span>
    
    <span data-ttu-id="94040-p151">O assistente provavelmente mostrará diversos avisos, especialmente se você não estiver usando armazenamento compartilhado. Não é necessário usar o armazenamento compartilhado. No entanto, se você vir alguma mensagem de **Erro**, deverá corrigir esses problemas antes de continuar.</span><span class="sxs-lookup"><span data-stu-id="94040-p151">The wizard will probably report several warnings, especially if you are not using shared storage. You are not required to use shared storage. However, if you see any **Error** messages, you must fix those issues before continuing.</span></span>
    
3. <span data-ttu-id="94040-315">Criar o cluster.</span><span class="sxs-lookup"><span data-stu-id="94040-315">Create the cluster.</span></span>
    
   - <span data-ttu-id="94040-316">No assistente de **Gerenciamento de Cluster de Failover**, clique com o botão direito do mouse em **Gerenciamento de Cluster de Failover** e, em seguida, clique em **Criar Cluster**.</span><span class="sxs-lookup"><span data-stu-id="94040-316">In the **Failover Cluster Management** wizard, right-click **Failover Cluster Management**, then click **Create Cluster**.</span></span>
    
   - <span data-ttu-id="94040-317">Na página **Antes de começar**, clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="94040-317">On the **Before You Begin** page, click **Next**.</span></span>
    
   - <span data-ttu-id="94040-p152">Adicione o nome e o endereço IP do cluster. Quando as definições forem validadas, clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="94040-p152">Add the cluster name and IP address. When the settings are validated, click **Next**.</span></span>
    
   - <span data-ttu-id="94040-320">Na página Confirmação, clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="94040-320">On the Confirmation page, click **Next**.</span></span>
    
   - <span data-ttu-id="94040-321">Depois que o cluster for criado, clique em **Concluir**.</span><span class="sxs-lookup"><span data-stu-id="94040-321">After the cluster is created, click **Finish**.</span></span>
    
4. <span data-ttu-id="94040-p153">Recomendamos que você defina as configurações de quorum do cluster para usar uma testemunha de compartilhamento de arquivos. Para isso, siga estas instruções:</span><span class="sxs-lookup"><span data-stu-id="94040-p153">We recommend that you configure the cluster quorum settings to use a file share witness. To do so, use these steps:</span></span>
    
   - <span data-ttu-id="94040-324">Clique com o botão direito do mouse no nome do cluster, em **Mais Ações** e, em seguida, em **Configurar Quorum do Cluster**.</span><span class="sxs-lookup"><span data-stu-id="94040-324">Right-click the cluster name, click **More Actions**, and click **Configure Cluster Quorum Settings**.</span></span>
    
   - <span data-ttu-id="94040-325">Na página **Selecionar Opção de Configuração de Quorum**, clique em **Selecione a testemunha de Quorum**.</span><span class="sxs-lookup"><span data-stu-id="94040-325">In the **Select Quorum Configuration Option** page, click **Select the quorum witness**.</span></span>
    
   - <span data-ttu-id="94040-326">Na página **Selecione a testemunha de Quorum**, clique em **Configurar uma testemunha de compartilhamento de arquivos**.</span><span class="sxs-lookup"><span data-stu-id="94040-326">In the **Select Quorum Witness** page, click **Configure a file share witness**.</span></span>
    
   - <span data-ttu-id="94040-327">Na página **Configurar Testemunha de Compartilhamento de Arquivo**, digite o caminho do compartilhamento de arquivos que você deseja usar e clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="94040-327">In the **Configure File Share Witness** page, type the path of the file share you want to use, and then click **Next**.</span></span>
    
   - <span data-ttu-id="94040-328">Na página **Confirmação**, clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="94040-328">On the **Confirmation** page, click **Next**.</span></span>
    
5. <span data-ttu-id="94040-329">Em cada servidor do cluster, habilite Sempre ativo no SQL Server Configuration Manager.</span><span class="sxs-lookup"><span data-stu-id="94040-329">On each server in the cluster, enable Always On in SQL Server Configuration Manager.</span></span>
    
   - <span data-ttu-id="94040-p154">Abra o SQL Server Configuration Manager. Na árvore no lado esquerdo da tela, clique em **Serviços do SQL Server** e, em seguida, clique duas vezes no serviço SQL Server. </span><span class="sxs-lookup"><span data-stu-id="94040-p154">Open SQL Server Configuration Manager. In the tree on the left side of the screen, click **SQL Server Services**, then double-click the SQL Server service.</span></span> 
    
   - <span data-ttu-id="94040-p155">Na caixa **Propriedades**, selecione a guia **Alta Disponibilidade AlwaysOn**. Marque a caixa de seleção **Habilitar Grupos de Disponibilidade AlwaysOn**. Reinicie o serviço SQL Server quando solicitado.</span><span class="sxs-lookup"><span data-stu-id="94040-p155">In the **Properties** box, select the **AlwaysOn High Availability** tab. Select the **Enable AlwaysOn Availability Groups** check box. Restart the SQL Server service when prompted.</span></span>
    
6. <span data-ttu-id="94040-334">Criar o grupo de disponibilidade.</span><span class="sxs-lookup"><span data-stu-id="94040-334">Create the availability group.</span></span>
    
   - <span data-ttu-id="94040-335">Abra o SQL Server Management Studio e conecte-se à instância do SQL Server.</span><span class="sxs-lookup"><span data-stu-id="94040-335">Open SQL Server Management Studio, and connect to the SQL Server instance.</span></span>
    
   - <span data-ttu-id="94040-p156">No Pesquisador de Objetos, expanda a pasta **Alta Disponibilidade AlwaysOn**. Clique com o botão direito do mouse na pasta **Grupos de Disponibilidade** e clique em **Assistente para Novo Grupo de Disponibilidade**.</span><span class="sxs-lookup"><span data-stu-id="94040-p156">In Object Explorer, expand the **AlwaysOn High Availability** folder. Right-click the **Availability Groups** folder and click **New Availability Group Wizard**.</span></span>
    
   - <span data-ttu-id="94040-338">Se a página **Introdução** for exibida, clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="94040-338">If the **Introduction** page appears, click **Next**.</span></span>
    
   - <span data-ttu-id="94040-339">Na página **Especificar Nome do Grupo de Disponibilidade**, digite o nome do Grupo de disponibilidade e clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="94040-339">In the **Specify Availability Group Name** page, type the name of the Availability group, and click **Next**.</span></span>
    
   - <span data-ttu-id="94040-340">Na página Selecionar bancos de dados, selecione os bancos de dados que você deseja incluir no grupo de disponibilidade do AlwaysOn.</span><span class="sxs-lookup"><span data-stu-id="94040-340">In the Select Databases page, select the databases that you want to include in the AlwaysOn Availability Group.</span></span> <span data-ttu-id="94040-341">Then click **Next**.</span><span class="sxs-lookup"><span data-stu-id="94040-341">Then click **Next**.</span></span>
    
    <span data-ttu-id="94040-342">Não inclua o **ReportServer**, **ReportServerTempDB**ou bancos de dados de Chat persistente no grupo de disponibilidade do AlwaysOn, como eles não são suportados neste cenário.</span><span class="sxs-lookup"><span data-stu-id="94040-342">Do not include the **ReportServer**, **ReportServerTempDB**, or Persistent Chat databases in the AlwaysOn Availability Group, as these are not supported in this scenario.</span></span> <span data-ttu-id="94040-343">Você pode incluir todos os outro Skype para bancos de dados do servidor de negócios no grupo de disponibilidade do AlwaysOn.</span><span class="sxs-lookup"><span data-stu-id="94040-343">You can include all other Skype for Business Server databases in the AlwaysOn Availability Group.</span></span>
    
   - <span data-ttu-id="94040-344">Na página **Especificar Réplicas**, clique na guia **Réplicas**. Clique no botão **Adicionar Réplicas** e conecte-se às outras instâncias do SQL que você incluiu como nós do Clustering de Failover do Windows Server.</span><span class="sxs-lookup"><span data-stu-id="94040-344">In the **Specify Replicas** page, click the **Replicas** tab. Then click the **Add Replicas** button, and connect to the other SQL instances that you joined as nodes of the Windows Server Failover Cluster.</span></span>
    
   - <span data-ttu-id="94040-p159">Para cada instância, selecione as opções **Failover Automático** e **Confirmação Síncrona**. Não selecione a opção **Secundária Legível**.</span><span class="sxs-lookup"><span data-stu-id="94040-p159">For each instance, select the **Automatic Failover** and **Synchronous Commit** options. Do not select the **Readable Secondary** option.</span></span>
    
   - <span data-ttu-id="94040-347">Clique na guia **Pontos de Extremidade** e verifique se o **Número da Porta** está definido como 5022.</span><span class="sxs-lookup"><span data-stu-id="94040-347">Click the **Endpoints** tab and verify that **Port Number** is set to 5022.</span></span>
    
   - <span data-ttu-id="94040-p160">Clique na guia **Ouvinte** e selecione a opção **Criar um ouvinte de grupo de disponibilidade**. Nesta opção, digite um nome para o ouvinte e defina a **Porta** como 1433 (outras portas não são suportadas para esta opção).</span><span class="sxs-lookup"><span data-stu-id="94040-p160">Click the **Listener** tab, and select the **Create an availability group listener** option. Under that option, type a name for the listener, and set the **Port** to 1433 (other ports are not supported for this option).</span></span>
    
   - <span data-ttu-id="94040-350">Clique em **Adicionar** e, na caixa **Endereço IPv4**, forneça o endereço IP virtual de sua preferência e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="94040-350">Click **Add**, and then in the **IPv4 Address** box, provide your preferred virtual IP address, and then click **OK**.</span></span>
    
   - <span data-ttu-id="94040-p161">Na página **Selecionar Sincronização de Dados Inicial**, selecione Completo, especifique uma pasta que possa ser acessada pelas réplicas e para a qual a conta do serviço SQL Server usada por ambas as réplicas tenha permissões de Gravação. Clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="94040-p161">In the **Select Initial Data Synchronization** page, select Full, and specify a folder that is accessible to the replicas, and that the SQL Server service account used by both replicas has Write permissions for. Then click **Next**.</span></span>
    
    <span data-ttu-id="94040-p162">Este compartilhamento de arquivos será usado temporariamente quando você inicializar os bancos de dados. Se você usar bancos de dados grandes, recomendamos que você os inicie manualmente caso a largura de banda de sua rede não possa acomodar o tamanho dos bancos de dados de backup.</span><span class="sxs-lookup"><span data-stu-id="94040-p162">This file share will be used temporarily when you initialize the databases. If you are dealing with large databases, we recommend that you manually initialize them in case your network bandwidth cannot accommodate the size of the database backups.</span></span>
    
    - <span data-ttu-id="94040-355">Na página Validação, confira se as verificações de validação foram bem-sucedidas e, em seguida, clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="94040-355">In the Validation page, verify that all validation checks are successful, then click **Next**.</span></span>
    
   - <span data-ttu-id="94040-356">Na página **Resumo**, verifique todas as configurações e clique em Concluir.</span><span class="sxs-lookup"><span data-stu-id="94040-356">In the **Summary** page, verify all settings and click Finish.</span></span>
    
7. <span data-ttu-id="94040-357">Crie um novo repositório especificando o ouvinte do grupo de disponibilidade do AlwaysOn.</span><span class="sxs-lookup"><span data-stu-id="94040-357">Create a new store specifying the AlwaysOn Availability Group listener.</span></span>
    
   - <span data-ttu-id="94040-358">Abra o construtor de topologia.</span><span class="sxs-lookup"><span data-stu-id="94040-358">Open Topology Builder.</span></span> <span data-ttu-id="94040-359">Em sua topologia, expanda **Componentes Compartilhados**, clique com o botão direito do mouse em **Repositórios do SQL Server** e clique em **Novo Repositório do SQL Server**.</span><span class="sxs-lookup"><span data-stu-id="94040-359">In your topology, expand **Shared Components**, right-click **SQL Server Stores**, and click **New SQL Server Store**.</span></span>
    
   - <span data-ttu-id="94040-360">Na página **Definir Novo Repositório SQL**, primeiro marque a caixa de seleção **Configurações de Alta Disponibilidade** e, em seguida, certifique-se de que a opção Grupos de Disponibilidade AlwaysOn do SQL aparece na caixa suspensa.</span><span class="sxs-lookup"><span data-stu-id="94040-360">In the **Define New SQL Store** page, first select the **High Availability Settings** check box, and then make sure that SQL AlwaysOn Availability Groups appears in the drop-down box.</span></span>
    
   - <span data-ttu-id="94040-361">Na caixa **FQDN do Ouvinte de Disponibilidade do SQL Server**, digite o FQDN do ouvinte que criou quando criou o grupo de disponibilidade.</span><span class="sxs-lookup"><span data-stu-id="94040-361">In the **SQL Server Availability Listener FQDN** box, type the FQDN of the listener you created when you created the availability group.</span></span>
    
   - <span data-ttu-id="94040-362">Na caixa **FQDN do SQL Server** , digite o FQDN do nó principal do grupo de disponibilidade do AlwaysOn e clique em **Okey**.</span><span class="sxs-lookup"><span data-stu-id="94040-362">In the **SQL Server FQDN** box, type the FQDN of the primary node of the AlwaysOn Availability Group, and then click **OK**.</span></span>
    
8. <span data-ttu-id="94040-363">Associe o novo grupo de disponibilidade do AlwaysOn com o pool de Front-End.</span><span class="sxs-lookup"><span data-stu-id="94040-363">Associate the new AlwaysOn Availability Group with the Front End pool.</span></span>
    
   - <span data-ttu-id="94040-364">No construtor de topologia, clique com botão direito do pool para associar o grupo de disponibilidade do AlwaysOn e clique em **Editar propriedades**.</span><span class="sxs-lookup"><span data-stu-id="94040-364">In Topology Builder, right-click the pool to associate with the AlwaysOn Availability Group, and click **Edit Properties**.</span></span>
    
   - <span data-ttu-id="94040-365">Em **associações**, na caixa **Repositório do SQL Server** , selecione o grupo de disponibilidade do AlwaysOn.</span><span class="sxs-lookup"><span data-stu-id="94040-365">Under **Associations**, in the **SQL Server Store** box, select the AlwaysOn Availability Group.</span></span> <span data-ttu-id="94040-366">Selecione o grupo mesmo para outros bancos de dados no pool que você deseja mover para o grupo de disponibilidade do AlwaysOn.</span><span class="sxs-lookup"><span data-stu-id="94040-366">Select the same group for any other databases in the pool which you want to move to the AlwaysOn Availability Group.</span></span>
    
   - <span data-ttu-id="94040-367">Quando tiver certeza de que todos os bancos de dados necessários estão definidos para o grupo de disponibilidade do AlwaysOn, clique em **Okey**.</span><span class="sxs-lookup"><span data-stu-id="94040-367">When you're sure that all needed databases are set to the AlwaysOn Availability Group, click **OK**.</span></span>
    
9. <span data-ttu-id="94040-p165">Publique a topologia. No menu **Ação**, clique em **Topologia** e, em seguida, em **Publicar**. Na página de confirmação, clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="94040-p165">Publish the topology. From the **Action** menu click **Topology** and then **Publish**. Then in the confirmation page click **Next**.</span></span>
    
10. <span data-ttu-id="94040-371">Execute algumas etapas finais para certificar-se de que os logons do SQL estão em cada uma das réplicas no grupo de disponibilidade do AlwaysOn.</span><span class="sxs-lookup"><span data-stu-id="94040-371">Perform some final steps to make sure that the SQL logins are on each of the replicas in the AlwaysOn Availability Group.</span></span>
    
    - <span data-ttu-id="94040-372">Abra o construtor de topologia, selecione **Baixar topologia da implantação existente**e clique em **Okey**.</span><span class="sxs-lookup"><span data-stu-id="94040-372">Open Topology Builder, select **Download topology from existing deployment**, and click **OK**.</span></span>
    
    - <span data-ttu-id="94040-373">Expanda o Skype for Business Server, expanda sua topologia e expanda **Repositórios do SQL Server**.</span><span class="sxs-lookup"><span data-stu-id="94040-373">Expand Skype for Business Server, expand your topology, and expand **SQL Server Stores**.</span></span> <span data-ttu-id="94040-374">Clique com o botão o repositório SQL do novo grupo de disponibilidade do AlwaysOn e, em seguida, clique em * * Editar propriedades * *.</span><span class="sxs-lookup"><span data-stu-id="94040-374">Right-click the SQL store of the new AlwaysOn Availability Group, and click ** Edit Properties**.</span></span>
    
    - <span data-ttu-id="94040-375">Na parte inferior da página, na caixa **FQDN do SQL Server** , altere o valor para o FQDN do ouvinte do grupo de disponibilidade do AlwaysOn.</span><span class="sxs-lookup"><span data-stu-id="94040-375">At the bottom of the page, in the **SQL Server FQDN** box, change the value to the FQDN of the Listener of the AlwaysOn Availability Group.</span></span>
    
    - <span data-ttu-id="94040-p167">Publique a topologia. No menu **Ação**, clique em **Topologia** e, em seguida, **Publicar**. Na página de confirmação, clique em **Avançar**. Aguarde alguns minutos para a nova topologia ser replicada.</span><span class="sxs-lookup"><span data-stu-id="94040-p167">Publish the topology. From the **Action** menu click **Topology** and then **Publish**. Then in the confirmation page click **Next**. Then wait a few minutes for the new topology to replicate.</span></span>
    
    - <span data-ttu-id="94040-380">Abra o SQL Server Management Studio e navegue até o grupo de disponibilidade do AlwaysOn.</span><span class="sxs-lookup"><span data-stu-id="94040-380">Open SQL Server Management Studio, and navigate to the AlwaysOn Availability Group.</span></span> <span data-ttu-id="94040-381">Faça failover para uma réplica secundária.</span><span class="sxs-lookup"><span data-stu-id="94040-381">Fail it over to a secondary replica.</span></span>
    
    - <span data-ttu-id="94040-382">Abra o Skype do Shell de gerenciamento do servidor de negócios e digite o seguinte cmdlet para criar logons do SQL nesta réplica:</span><span class="sxs-lookup"><span data-stu-id="94040-382">Open Skype for Business Server Management Shell and type the following cmdlet to create the SQL logins on this replica:</span></span>
    
     ```
     Install-CsDatabase -Update
     ```

     - <span data-ttu-id="94040-383">Repita as duas etapas anteriores (failover no grupo para uma réplica secundária e, em seguida, usar `Install-CsDatabase -Update`) para cada réplica no grupo.</span><span class="sxs-lookup"><span data-stu-id="94040-383">Repeat the previous two steps (fail over the group to a secondary replica, then use  `Install-CsDatabase -Update`) for each replica in the group.</span></span>
    

