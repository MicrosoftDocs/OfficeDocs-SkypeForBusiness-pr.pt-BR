---
title: Implantar um grupo de disponibilidade sempre ativada em um servidor de Back-End no Skype para Business Server
ms.reviewer: ''
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: c93c01e6-626c-40ad-92dd-373b0fe9189f
description: Implante um sempre no grupo de disponibilidade na sua Skype (instalação) para o Business Server deployment.
ms.openlocfilehash: fcdae233e81f7c2dde3f1bdb4a79f06c95f640d0
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32225529"
---
# <a name="deploy-an-always-on-availability-group-on-a-back-end-server-in-skype-for-business-server"></a><span data-ttu-id="8b1bc-103">Implantar um grupo de disponibilidade sempre ativada em um servidor de Back-End no Skype para Business Server</span><span class="sxs-lookup"><span data-stu-id="8b1bc-103">Deploy an Always On Availability Group on a Back End Server in Skype for Business Server</span></span>
 
<span data-ttu-id="8b1bc-104">Implante um sempre na disponibilidade grupo (AG) no seu Skype (instalação) para o Business Server deployment.</span><span class="sxs-lookup"><span data-stu-id="8b1bc-104">Deploy (install) an Always On Availability Group (AG) in your Skype for Business Server deployment.</span></span>
  
<span data-ttu-id="8b1bc-105">Como você implanta uma AG depende se você estiver implantando em um novo pool, um pool existente que usa espelhamento ou um pool existente que tem atualmente sem alta disponibilidade para o banco de dados de Back-End.</span><span class="sxs-lookup"><span data-stu-id="8b1bc-105">How you deploy an AG depends on whether you are deploying it in a new pool, an existing pool that uses mirroring, or an existing pool that currently has no high availability for the Back End database.</span></span>
  
> [!NOTE]
> <span data-ttu-id="8b1bc-106">Usar uma AG com uma função de servidor de Chat persistente não é suportado.</span><span class="sxs-lookup"><span data-stu-id="8b1bc-106">Using an AG with a Persistent Chat Server role is not supported.</span></span> 
  
- [<span data-ttu-id="8b1bc-107">Implantar um sempre no grupo de disponibilidade em um novo pool de Front-End</span><span class="sxs-lookup"><span data-stu-id="8b1bc-107">Deploy an Always On Availability Group on a new Front End pool</span></span>](alwayson-availability-group.md#BKMK_NewPool_CreateAlwaysOnGroup)
    
- [<span data-ttu-id="8b1bc-108">Implantar um sempre no grupo de disponibilidade em um pool existente que usa o espelhamento de banco de dados</span><span class="sxs-lookup"><span data-stu-id="8b1bc-108">Deploy an Always On Availability Group on an existing pool that uses database mirroring</span></span>](alwayson-availability-group.md#BKMK_MirroredPool_CreateAlwaysOnGroup)
    
- [<span data-ttu-id="8b1bc-109">Implantar um sempre no grupo de disponibilidade em um pool existente que não usa o espelhamento de banco de dados</span><span class="sxs-lookup"><span data-stu-id="8b1bc-109">Deploy an Always On Availability Group on an existing pool that does not use database mirroring</span></span>](alwayson-availability-group.md#BKMK_NoHAPool_CreateAlwaysOnGroup)
    
## <a name="deploy-an-always-on-availability-group-on-a-new-front-end-pool"></a><span data-ttu-id="8b1bc-110">Implantar um sempre no grupo de disponibilidade em um novo pool de Front-End</span><span class="sxs-lookup"><span data-stu-id="8b1bc-110">Deploy an Always On Availability Group on a new Front End pool</span></span>
<span data-ttu-id="8b1bc-111"><a name="BKMK_NewPool_CreateAlwaysOnGroup"> </a></span><span class="sxs-lookup"><span data-stu-id="8b1bc-111"></span></span>

1. <span data-ttu-id="8b1bc-112">Habilite o recurso de cluster de Failover em todos os servidores de banco de dados que farão parte da AG.</span><span class="sxs-lookup"><span data-stu-id="8b1bc-112">Enable the Failover Clustering feature on all the database servers which will be part of the AG.</span></span> <span data-ttu-id="8b1bc-113">Em cada servidor, faça o seguinte:</span><span class="sxs-lookup"><span data-stu-id="8b1bc-113">On each server, do the following</span></span>
    
   - <span data-ttu-id="8b1bc-114">Abra o Server Manager e clique em **Adicionar funções e recurso**.</span><span class="sxs-lookup"><span data-stu-id="8b1bc-114">Open Server Manager and click **Add roles and features**.</span></span>
    
   - <span data-ttu-id="8b1bc-p102">Clique em **Avançar** até chegar à caixa **Selecionar recursos**. Aqui, marque a caixa de seleção **Clustering de Failover**.</span><span class="sxs-lookup"><span data-stu-id="8b1bc-p102">Click **Next** until you reach the **Select features** box. Here, select the **Failover Clustering** check box.</span></span>
    
   - <span data-ttu-id="8b1bc-117">Na caixa **Adicionar recursos necessários para o Clustering de Failover?**, clique em **Adicionar Recursos**.</span><span class="sxs-lookup"><span data-stu-id="8b1bc-117">In the **Add features that are required for Failover Clustering?** box, click **Add Features**.</span></span>
    
   - <span data-ttu-id="8b1bc-118">Clique em **Instalar**.</span><span class="sxs-lookup"><span data-stu-id="8b1bc-118">Click **Install**.</span></span>
    
2. <span data-ttu-id="8b1bc-119">Validar a configuração de cluster.</span><span class="sxs-lookup"><span data-stu-id="8b1bc-119">Validate the cluster configuration.</span></span>
    
   - <span data-ttu-id="8b1bc-120">No Server Manager, clique no menu **Ferramentas** e, em seguida, clique em **Gerenciador de Cluster de Failover**.</span><span class="sxs-lookup"><span data-stu-id="8b1bc-120">In Server Manager, click the **Tools** menu and then click **Failover Cluster Manager**.</span></span>
    
   - <span data-ttu-id="8b1bc-121">Em **Ações** no lado direito da tela, clique em **Validar Configuração**.</span><span class="sxs-lookup"><span data-stu-id="8b1bc-121">Under **Actions** on the right side of the screen, click **Validate Configuration**.</span></span>
    
   - <span data-ttu-id="8b1bc-122">Na página **Antes de começar**, clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="8b1bc-122">On the **Before You Begin** page, click **Next**.</span></span>
    
   - <span data-ttu-id="8b1bc-123">Selecione os servidores a serem adicionados ao cluster e clique em **Executar todos os testes**.</span><span class="sxs-lookup"><span data-stu-id="8b1bc-123">Select the servers to add to the cluster, and then click **Run all tests**.</span></span>
    
   - <span data-ttu-id="8b1bc-p103">Na caixa **Resumo**, verifique os erros relatados pelo assistente. Clique em **Concluir** para concluir a validação.</span><span class="sxs-lookup"><span data-stu-id="8b1bc-p103">In the **Summary** box, check any errors that the wizard reports. Then click **Finish** to complete the validation.</span></span>
    
     <span data-ttu-id="8b1bc-p104">O assistente provavelmente mostrará diversos avisos, especialmente se você não estiver usando armazenamento compartilhado. Não é necessário usar o armazenamento compartilhado. No entanto, se você vir alguma mensagem de **Erro**, deverá corrigir esses problemas antes de continuar.</span><span class="sxs-lookup"><span data-stu-id="8b1bc-p104">The wizard will probably report several warnings, especially if you are not using shared storage. You are not required to use shared storage. However, if you see any **Error** messages, you must fix those issues before continuing.</span></span>
    
3. <span data-ttu-id="8b1bc-129">Crie o Cluster de Failover do Windows Server (WSFC).</span><span class="sxs-lookup"><span data-stu-id="8b1bc-129">Create the Windows Server Failover Cluster (WSFC).</span></span>
    
   - <span data-ttu-id="8b1bc-130">No assistente de **Gerenciamento de Cluster de Failover**, clique com o botão direito do mouse em **Gerenciamento de Cluster de Failover** e, em seguida, clique em **Criar Cluster**.</span><span class="sxs-lookup"><span data-stu-id="8b1bc-130">In the **Failover Cluster Management** wizard, right-click **Failover Cluster Management**, then click **Create Cluster**.</span></span>
    
   - <span data-ttu-id="8b1bc-131">Na página **Antes de começar**, clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="8b1bc-131">On the **Before You Begin** page, click **Next**.</span></span>
    
   - <span data-ttu-id="8b1bc-p105">Adicione o nome e o endereço IP do cluster. Quando as definições forem validadas, clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="8b1bc-p105">Add the cluster name and IP address. When the settings are validated, click **Next**.</span></span>
    
   - <span data-ttu-id="8b1bc-134">Na página Confirmação, clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="8b1bc-134">On the Confirmation page, click **Next**.</span></span>
    
   - <span data-ttu-id="8b1bc-135">Depois que o cluster for criado, clique em **Concluir**.</span><span class="sxs-lookup"><span data-stu-id="8b1bc-135">After the cluster is created, click **Finish**.</span></span>
    
4. <span data-ttu-id="8b1bc-p106">Recomendamos que você defina as configurações de quorum do cluster para usar uma testemunha de compartilhamento de arquivos. Para isso, siga estas instruções:</span><span class="sxs-lookup"><span data-stu-id="8b1bc-p106">We recommend that you configure the cluster quorum settings to use a file share witness. To do so, use these steps:</span></span>
    
   - <span data-ttu-id="8b1bc-138">Clique com o botão direito do mouse no nome do cluster, em **Mais Ações** e, em seguida, em **Configurar Quorum do Cluster**.</span><span class="sxs-lookup"><span data-stu-id="8b1bc-138">Right-click the cluster name, click **More Actions**, and click **Configure Cluster Quorum Settings**.</span></span>
    
   - <span data-ttu-id="8b1bc-139">Na página **Selecionar Opção de Configuração de Quorum**, clique em **Selecione a testemunha de Quorum**.</span><span class="sxs-lookup"><span data-stu-id="8b1bc-139">In the **Select Quorum Configuration Option** page, click **Select the quorum witness**.</span></span>
    
   - <span data-ttu-id="8b1bc-140">Na página **Selecione a testemunha de Quorum**, clique em **Configurar uma testemunha de compartilhamento de arquivos**.</span><span class="sxs-lookup"><span data-stu-id="8b1bc-140">In the **Select Quorum Witness** page, click **Configure a file share witness**.</span></span>
    
   - <span data-ttu-id="8b1bc-141">Na página **Configurar Testemunha de Compartilhamento de Arquivo**, digite o caminho do compartilhamento de arquivos que você deseja usar e clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="8b1bc-141">In the **Configure File Share Witness** page, type the path of the file share you want to use, and then click **Next**.</span></span>
    
   - <span data-ttu-id="8b1bc-142">Na página **Confirmação**, clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="8b1bc-142">On the **Confirmation** page, click **Next**.</span></span>
    
5. <span data-ttu-id="8b1bc-143">Em cada servidor do cluster, habilite o recurso de AG no SQL Server Configuration Manager.</span><span class="sxs-lookup"><span data-stu-id="8b1bc-143">On each server in the cluster, enable the AG feature in SQL Server Configuration Manager.</span></span>
    
   - <span data-ttu-id="8b1bc-p107">Abra o SQL Server Configuration Manager. Na árvore no lado esquerdo da tela, clique em **Serviços do SQL Server** e, em seguida, clique duas vezes no serviço SQL Server. </span><span class="sxs-lookup"><span data-stu-id="8b1bc-p107">Open SQL Server Configuration Manager. In the tree on the left side of the screen, click **SQL Server Services**, then double-click the SQL Server service.</span></span> 
    
   - <span data-ttu-id="8b1bc-p108">Na caixa **Propriedades**, selecione a guia **Alta Disponibilidade AlwaysOn**. Marque a caixa de seleção **Habilitar Grupos de Disponibilidade AlwaysOn**. Reinicie o serviço SQL Server quando solicitado.</span><span class="sxs-lookup"><span data-stu-id="8b1bc-p108">In the **Properties** box, select the **AlwaysOn High Availability** tab. Select the **Enable AlwaysOn Availability Groups** check box. Restart the SQL Server service when prompted.</span></span>
   
6. <span data-ttu-id="8b1bc-148">Use o construtor de topologias para criar o pool de Front-End, conforme explicado em [criar e publicar a nova topologia no Skype para Business Server](../../deploy/install/create-and-publish-new-topology.md).</span><span class="sxs-lookup"><span data-stu-id="8b1bc-148">Use Topology Builder to create the Front End pool, as explained in [Create and publish new topology in Skype for Business Server](../../deploy/install/create-and-publish-new-topology.md).</span></span> <span data-ttu-id="8b1bc-149">Quando você fizer isso, especifique a AG como o repositório SQL para o pool.</span><span class="sxs-lookup"><span data-stu-id="8b1bc-149">When you do, specify the AG as the SQL store for the pool.</span></span>
    
7. <span data-ttu-id="8b1bc-150">Criar o grupo de disponibilidade.</span><span class="sxs-lookup"><span data-stu-id="8b1bc-150">Create the availability group.</span></span>
    
   - <span data-ttu-id="8b1bc-151">Abra o SQL Server Management Studio e conecte-se à instância do SQL Server.</span><span class="sxs-lookup"><span data-stu-id="8b1bc-151">Open SQL Server Management Studio, and connect to the SQL Server instance.</span></span>
    
   - <span data-ttu-id="8b1bc-152">No Object Explorer, expanda a pasta de **Sempre na alta disponibilidade** .</span><span class="sxs-lookup"><span data-stu-id="8b1bc-152">In Object Explorer, expand the **Always On High Availability** folder.</span></span> <span data-ttu-id="8b1bc-153">Clique com o botão direito do mouse na pasta **Grupos de Disponibilidade** e clique em **Assistente para Novo Grupo de Disponibilidade**.</span><span class="sxs-lookup"><span data-stu-id="8b1bc-153">Right-click the **Availability Groups** folder and click **New Availability Group Wizard**.</span></span>
    
   - <span data-ttu-id="8b1bc-154">Se a página **Introdução** for exibida, clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="8b1bc-154">If the **Introduction** page appears, click **Next**.</span></span>
    
   - <span data-ttu-id="8b1bc-155">Na página **Especificar Nome do Grupo de Disponibilidade**, digite o nome do Grupo de disponibilidade e clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="8b1bc-155">In the **Specify Availability Group Name** page, type the name of the Availability group, and click **Next**.</span></span>
    
   - <span data-ttu-id="8b1bc-156">Na página Selecionar bancos de dados, selecione os bancos de dados que você deseja incluir no grupo de disponibilidade do AlwaysOn.</span><span class="sxs-lookup"><span data-stu-id="8b1bc-156">In the Select Databases page, select the databases that you want to include in the AlwaysOn Availability Group.</span></span> <span data-ttu-id="8b1bc-157">Then click **Next**.</span><span class="sxs-lookup"><span data-stu-id="8b1bc-157">Then click **Next**.</span></span>
    
     <span data-ttu-id="8b1bc-158">Não inclua o **ReportServer**, **ReportServerTempDB**ou bancos de dados de Chat persistente no grupo de disponibilidade do AlwaysOn, como eles não são suportados neste cenário.</span><span class="sxs-lookup"><span data-stu-id="8b1bc-158">Do not include the **ReportServer**, **ReportServerTempDB**, or Persistent Chat databases in the AlwaysOn Availability Group, as these are not supported in this scenario.</span></span> <span data-ttu-id="8b1bc-159">Você pode incluir todos os outro Skype para bancos de dados do servidor de negócios no grupo de disponibilidade do AlwaysOn.</span><span class="sxs-lookup"><span data-stu-id="8b1bc-159">You can include all other Skype for Business Server databases in the AlwaysOn Availability Group.</span></span>
    
   - <span data-ttu-id="8b1bc-160">Na página **Especificar Réplicas**, clique na guia **Réplicas**. Clique no botão **Adicionar Réplicas** e conecte-se às outras instâncias do SQL que você incluiu como nós do Clustering de Failover do Windows Server.</span><span class="sxs-lookup"><span data-stu-id="8b1bc-160">In the **Specify Replicas** page, click the **Replicas** tab. Then click the **Add Replicas** button, and connect to the other SQL instances that you joined as nodes of the Windows Server Failover Cluster.</span></span>
    
   - <span data-ttu-id="8b1bc-p113">Para cada instância, selecione as opções **Failover Automático** e **Confirmação Síncrona**. Não selecione a opção **Secundária Legível**.</span><span class="sxs-lookup"><span data-stu-id="8b1bc-p113">For each instance, select the **Automatic Failover** and **Synchronous Commit** options. Do not select the **Readable Secondary** option.</span></span>
    
   - <span data-ttu-id="8b1bc-163">Clique na guia **Pontos de Extremidade** e verifique se o **Número da Porta** está definido como 5022.</span><span class="sxs-lookup"><span data-stu-id="8b1bc-163">Click the **Endpoints** tab and verify that **Port Number** is set to 5022.</span></span>
    
   - <span data-ttu-id="8b1bc-p114">Clique na guia **Ouvinte** e selecione a opção **Criar um ouvinte de grupo de disponibilidade**. Nesta opção, digite um nome para o ouvinte e defina a **Porta** como 1433 (outras portas não são suportadas para esta opção).</span><span class="sxs-lookup"><span data-stu-id="8b1bc-p114">Click the **Listener** tab, and select the **Create an availability group listener** option. Under that option, type a name for the listener, and set the **Port** to 1433 (other ports are not supported for this option).</span></span>
    
   - <span data-ttu-id="8b1bc-166">Clique em **Adicionar** e, na caixa **Endereço IPv4**, forneça o endereço IP virtual de sua preferência e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="8b1bc-166">Click **Add**, and then in the **IPv4 Address** box, provide your preferred virtual IP address, and then click **OK**.</span></span>
    
   - <span data-ttu-id="8b1bc-p115">Na página **Selecionar Sincronização de Dados Inicial**, selecione Completo, especifique uma pasta que possa ser acessada pelas réplicas e para a qual a conta do serviço SQL Server usada por ambas as réplicas tenha permissões de Gravação. Clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="8b1bc-p115">In the **Select Initial Data Synchronization** page, select Full, and specify a folder that is accessible to the replicas, and that the SQL Server service account used by both replicas has Write permissions for. Then click **Next**.</span></span>
    
     <span data-ttu-id="8b1bc-p116">Este compartilhamento de arquivos será usado temporariamente quando você inicializar os bancos de dados. Se você usar bancos de dados grandes, recomendamos que você os inicie manualmente caso a largura de banda de sua rede não possa acomodar o tamanho dos bancos de dados de backup.</span><span class="sxs-lookup"><span data-stu-id="8b1bc-p116">This file share will be used temporarily when you initialize the databases. If you are dealing with large databases, we recommend that you manually initialize them in case your network bandwidth cannot accommodate the size of the database backups.</span></span>
    
   - <span data-ttu-id="8b1bc-171">Na página Validação, confira se as verificações de validação foram bem-sucedidas e, em seguida, clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="8b1bc-171">In the Validation page, verify that all validation checks are successful, then click **Next**.</span></span>
    
   - <span data-ttu-id="8b1bc-172">Na página **Resumo**, verifique todas as configurações e clique em Concluir.</span><span class="sxs-lookup"><span data-stu-id="8b1bc-172">In the **Summary** page, verify all settings and click Finish.</span></span>
      
8. <span data-ttu-id="8b1bc-173">Após o pool e o AG são implantados, realize algumas etapas finais para certificar-se de que os logons do SQL estão em cada uma das réplicas no grupo de disponibilidade do AlwaysOn.</span><span class="sxs-lookup"><span data-stu-id="8b1bc-173">After the pool and the AG are deployed, perform some final steps to make sure that the SQL logins are on each of the replicas in the AlwaysOn Availability Group.</span></span> 
    
   - <span data-ttu-id="8b1bc-174">Abra o construtor de topologia, selecione **Baixar topologia da implantação existente**e clique em **Okey**.</span><span class="sxs-lookup"><span data-stu-id="8b1bc-174">Open Topology Builder, select **Download topology from existing deployment**, and click **OK**.</span></span>
    
   - <span data-ttu-id="8b1bc-175">Expanda o Skype for Business Server, expanda sua topologia e expanda **Repositórios do SQL Server**.</span><span class="sxs-lookup"><span data-stu-id="8b1bc-175">Expand Skype for Business Server, expand your topology, and expand **SQL Server Stores**.</span></span> <span data-ttu-id="8b1bc-176">Clique com o botão o repositório SQL do novo grupo de disponibilidade do AlwaysOn e clique em **Editar propriedades**.</span><span class="sxs-lookup"><span data-stu-id="8b1bc-176">Right-click the SQL store of the new AlwaysOn Availability Group, and click **Edit Properties**.</span></span>
    
     - <span data-ttu-id="8b1bc-177">Na parte inferior da página, na caixa **FQDN do SQL Server** , altere o valor para o FQDN do ouvinte da AG.</span><span class="sxs-lookup"><span data-stu-id="8b1bc-177">At the bottom of the page, in the **SQL Server FQDN** box, change the value to the FQDN of the Listener of the AG.</span></span>
    
   - <span data-ttu-id="8b1bc-p118">Publique a topologia. No menu **Ação**, clique em **Topologia** e, em seguida, **Publicar**. Na página de confirmação, clique em **Avançar**. Aguarde alguns minutos para a nova topologia ser replicada.</span><span class="sxs-lookup"><span data-stu-id="8b1bc-p118">Publish the topology. From the **Action** menu click **Topology** and then **Publish**. Then in the confirmation page click **Next**. Then wait a few minutes for the new topology to replicate.</span></span>
    
   - <span data-ttu-id="8b1bc-182">Abra o SQL Server Management Studio e navegue até a AG.</span><span class="sxs-lookup"><span data-stu-id="8b1bc-182">Open SQL Server Management Studio, and navigate to the AG.</span></span> <span data-ttu-id="8b1bc-183">Faça failover para uma réplica secundária.</span><span class="sxs-lookup"><span data-stu-id="8b1bc-183">Fail it over to a secondary replica.</span></span>
    
   - <span data-ttu-id="8b1bc-184">Abra o Skype do Shell de gerenciamento do servidor de negócios e digite o seguinte cmdlet para criar logons do SQL nesta réplica:</span><span class="sxs-lookup"><span data-stu-id="8b1bc-184">Open Skype for Business Server Management Shell and type the following cmdlet to create the SQL logins on this replica:</span></span>
    
   ```
   Install-CsDatabase -Update
   ```

   - <span data-ttu-id="8b1bc-185">Repita as duas etapas anteriores (failover no grupo para uma réplica secundária e, em seguida, usar `Install-CsDatabase -Update`) para cada réplica no grupo.</span><span class="sxs-lookup"><span data-stu-id="8b1bc-185">Repeat the previous two steps (fail over the group to a secondary replica, then use  `Install-CsDatabase -Update`) for each replica in the group.</span></span>
    
## <a name="deploy-an-always-on-availability-group-on-an-existing-pool-that-uses-database-mirroring"></a><span data-ttu-id="8b1bc-186">Implantar um sempre no grupo de disponibilidade em um pool existente que usa o espelhamento de banco de dados</span><span class="sxs-lookup"><span data-stu-id="8b1bc-186">Deploy an Always On Availability Group on an existing pool that uses database mirroring</span></span>
<span data-ttu-id="8b1bc-187"><a name="BKMK_MirroredPool_CreateAlwaysOnGroup"> </a></span><span class="sxs-lookup"><span data-stu-id="8b1bc-187"></span></span>

> [!NOTE]
> <span data-ttu-id="8b1bc-188">Se o pool que você estiver atualizando para uma AG hospedar o repositório de gerenciamento Central para sua organização, você deve primeiro mover o CMS para outro pool antes de atualizar este pool.</span><span class="sxs-lookup"><span data-stu-id="8b1bc-188">If the pool you are upgrading to an AG hosts the Central Management store for your organization, you must first move the CMS to another pool before you upgrade this pool.</span></span> <span data-ttu-id="8b1bc-189">Use o cmdlet Move-CsManagementServer para mover o pool.</span><span class="sxs-lookup"><span data-stu-id="8b1bc-189">Use the Move-CsManagementServer cmdlet to move the pool.</span></span> <span data-ttu-id="8b1bc-190">Se você não tiver outro pool em sua organização, você pode implantar um servidor Standard Edition temporariamente e mover o CMS para esse servidor antes de atualizar seu pool para a AG.</span><span class="sxs-lookup"><span data-stu-id="8b1bc-190">If you do not have another pool in your organization, you can deploy a Standard Edition server temporarily and move the CMS to this server before you upgrade your pool to the AG.</span></span> 
  
1. <span data-ttu-id="8b1bc-191">Failover de todos os dados do espelho para o nó principal abrindo Skype do Shell de gerenciamento do servidor de negócios e digitando o seguinte cmdlet.</span><span class="sxs-lookup"><span data-stu-id="8b1bc-191">Fail over all data from the mirror to the principal node by opening Skype for Business Server Management Shell and typing the following cmdlet.</span></span>
    
   ```
   Invoke-CsDatabaseFailover -PoolFqdn <Pool FQDN> -DatabaseType <DatabaseType> -NewPrincipal "Primary"
   ```

    <span data-ttu-id="8b1bc-p121">Repita esse cmdlet para cada tipo de banco de dados no pool. Você pode utilizar o seguinte cmdlet para localizar todos os tipos de bancos de dados armazenados neste pool.</span><span class="sxs-lookup"><span data-stu-id="8b1bc-p121">Repeat this cmdlet for each database type in the pool. You can use the following cmdlet to find all the database types stored in this pool.</span></span>
     
   ```
   Get-CsPool -Identity <Pool FQDN>
   ```

2. <span data-ttu-id="8b1bc-194">Use o construtor de topologias para remover o espelhamento de banco de dados do pool.</span><span class="sxs-lookup"><span data-stu-id="8b1bc-194">Use Topology Builder to remove database mirroring from the pool.</span></span>
    
   - <span data-ttu-id="8b1bc-195">Abra o construtor de topologia.</span><span class="sxs-lookup"><span data-stu-id="8b1bc-195">Open Topology Builder.</span></span> <span data-ttu-id="8b1bc-196">Em sua topologia, expanda **Pools de Front-Ends Enterprise Edition**, clique com o botão direito do mouse no nome do pool e clique em **Editar Propriedades**.</span><span class="sxs-lookup"><span data-stu-id="8b1bc-196">In your topology, expand **Enterprise Edition Front End Pools**, right-click the name of the pool, and click **Edit Properties**.</span></span>
    
   - <span data-ttu-id="8b1bc-197">Para cada tipo de repositório SQL no pool, desmarque a caixa de seleção **Habilitar Espelhamento do Repositório SQL**.</span><span class="sxs-lookup"><span data-stu-id="8b1bc-197">For each type of SQL store in the pool, clear the **Enable SQL Store Mirroring** check box.</span></span>
    
3. <span data-ttu-id="8b1bc-p123">Publique a topologia alterada. No menu **Ação**, clique em **Topologia** e, em seguida, em **Publicar**. Na página de confirmação, clique em **Avançar**</span><span class="sxs-lookup"><span data-stu-id="8b1bc-p123">Publish the changed topology. From the **Action** menu click **Topology** and then **Publish**. Then in the confirmation page click **Next**</span></span>
    
4. <span data-ttu-id="8b1bc-201">Usar o SQL Server Management Studio para quebrar o espelho.</span><span class="sxs-lookup"><span data-stu-id="8b1bc-201">Use SQL Server Management Studio to break the mirror.</span></span>
    
   - <span data-ttu-id="8b1bc-p124">Abra o SQL Server Management Studio, navegue até seus bancos de dados, clique com o botão direito do mouse em **Tarefas** e clique em **Espelho**. Clique em **Remover Espelhamento** e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="8b1bc-p124">Open SQL Server Management Studio, navigate to your databases, right-click **Tasks** and click **Mirror**. Then click **Remove Mirroring** and click **OK**.</span></span>
    
   - <span data-ttu-id="8b1bc-204">Repita esse procedimento para todos os bancos de dados do pool que será convertida em uma AG.</span><span class="sxs-lookup"><span data-stu-id="8b1bc-204">Repeat this for all databases in the pool which will be converted to an AG.</span></span>
    
5. <span data-ttu-id="8b1bc-205">Configure o recurso de cluster de Failover em todos os servidores de banco de dados que farão parte da AG.</span><span class="sxs-lookup"><span data-stu-id="8b1bc-205">Set up the Failover Clustering feature on all the database servers which will be part of the AG.</span></span> <span data-ttu-id="8b1bc-206">Em cada servidor, faça o seguinte:</span><span class="sxs-lookup"><span data-stu-id="8b1bc-206">On each server, do the following</span></span>
    
   - <span data-ttu-id="8b1bc-207">Abra o Server Manager e clique em **Adicionar funções e recurso**.</span><span class="sxs-lookup"><span data-stu-id="8b1bc-207">Open Server Manager and click **Add roles and features**.</span></span>
    
   - <span data-ttu-id="8b1bc-p126">Clique em **Avançar** até chegar à caixa **Selecionar recursos**. Aqui, marque a caixa de seleção **Clustering de Failover**.</span><span class="sxs-lookup"><span data-stu-id="8b1bc-p126">Click **Next** until you reach the **Select features** box. Here, select the **Failover Clustering** check box.</span></span>
    
   - <span data-ttu-id="8b1bc-210">Na caixa **Adicionar recursos necessários para o Clustering de Failover?**, clique em **Adicionar Recursos**.</span><span class="sxs-lookup"><span data-stu-id="8b1bc-210">In the **Add features that are required for Failover Clustering?** box, click **Add Features**.</span></span>
    
   - <span data-ttu-id="8b1bc-211">Clique em **Instalar**.</span><span class="sxs-lookup"><span data-stu-id="8b1bc-211">Click **Install**.</span></span>
    
6. <span data-ttu-id="8b1bc-212">Validar a configuração de cluster.</span><span class="sxs-lookup"><span data-stu-id="8b1bc-212">Validate the cluster configuration.</span></span>
    
   - <span data-ttu-id="8b1bc-213">No Server Manager, clique no menu **Ferramentas** e, em seguida, clique em **Gerenciador de Cluster de Failover**.</span><span class="sxs-lookup"><span data-stu-id="8b1bc-213">In Server Manager, click the **Tools** menu and then click **Failover Cluster Manager**.</span></span>
    
   - <span data-ttu-id="8b1bc-214">Em **Ações** no lado direito da tela, clique em **Validar Configuração**.</span><span class="sxs-lookup"><span data-stu-id="8b1bc-214">Under **Actions** on the right side of the screen, click **Validate Configuration**.</span></span>
    
   - <span data-ttu-id="8b1bc-215">Na página **Antes de começar**, clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="8b1bc-215">On the **Before You Begin** page, click **Next**.</span></span>
    
   - <span data-ttu-id="8b1bc-216">Selecione os servidores a serem adicionados ao cluster e clique em **Executar todos os testes**.</span><span class="sxs-lookup"><span data-stu-id="8b1bc-216">Select the servers to add to the cluster, and then click **Run all tests**.</span></span>
    
   - <span data-ttu-id="8b1bc-p127">Na caixa **Resumo**, verifique os erros relatados pelo assistente. Clique em **Concluir** para concluir a validação.</span><span class="sxs-lookup"><span data-stu-id="8b1bc-p127">In the **Summary** box, check any errors that the wizard reports. Then click **Finish** to complete the validation.</span></span>
    
     <span data-ttu-id="8b1bc-p128">O assistente provavelmente mostrará diversos avisos, especialmente se você não estiver usando armazenamento compartilhado. Não é necessário usar o armazenamento compartilhado. No entanto, se você vir alguma mensagem de **Erro**, deverá corrigir esses problemas antes de continuar.</span><span class="sxs-lookup"><span data-stu-id="8b1bc-p128">The wizard will probably report several warnings, especially if you are not using shared storage. You are not required to use shared storage. However, if you see any **Error** messages, you must fix those issues before continuing.</span></span>
    
7. <span data-ttu-id="8b1bc-222">Crie o Cluster de Failover do Windows Server.</span><span class="sxs-lookup"><span data-stu-id="8b1bc-222">Create the Windows Server Failover Cluster.</span></span>
    
   - <span data-ttu-id="8b1bc-223">No assistente de **Gerenciamento de Cluster de Failover**, clique com o botão direito do mouse em **Gerenciamento de Cluster de Failover** e, em seguida, clique em **Criar Cluster**.</span><span class="sxs-lookup"><span data-stu-id="8b1bc-223">In the **Failover Cluster Management** wizard, right-click **Failover Cluster Management**, then click **Create Cluster**.</span></span>
    
   - <span data-ttu-id="8b1bc-224">Na página **Antes de começar**, clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="8b1bc-224">On the **Before You Begin** page, click **Next**.</span></span>
    
   - <span data-ttu-id="8b1bc-p129">Adicione o nome e o endereço IP do cluster. Quando as definições forem validadas, clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="8b1bc-p129">Add the cluster name and IP address. When the settings are validated, click **Next**.</span></span>
    
   - <span data-ttu-id="8b1bc-227">Na página Confirmação, clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="8b1bc-227">On the Confirmation page, click **Next**.</span></span>
    
   - <span data-ttu-id="8b1bc-228">Depois que o cluster for criado, clique em **Concluir**.</span><span class="sxs-lookup"><span data-stu-id="8b1bc-228">After the cluster is created, click **Finish**.</span></span>
    
8. <span data-ttu-id="8b1bc-p130">Recomendamos que você defina as configurações de quorum do cluster para usar uma testemunha de compartilhamento de arquivos. Para isso, siga estas instruções:</span><span class="sxs-lookup"><span data-stu-id="8b1bc-p130">We recommend that you configure the cluster quorum settings to use a file share witness. To do so, use these steps:</span></span>
    
   - <span data-ttu-id="8b1bc-231">Clique com o botão direito do mouse no nome do cluster, em **Mais Ações** e, em seguida, em **Configurar Quorum do Cluster**.</span><span class="sxs-lookup"><span data-stu-id="8b1bc-231">Right-click the cluster name, click **More Actions**, and click **Configure Cluster Quorum Settings**.</span></span>
    
   - <span data-ttu-id="8b1bc-232">Na página **Selecionar Opção de Configuração de Quorum**, clique em **Selecione a testemunha de Quorum**.</span><span class="sxs-lookup"><span data-stu-id="8b1bc-232">In the **Select Quorum Configuration Option** page, click **Select the quorum witness**.</span></span>
    
   - <span data-ttu-id="8b1bc-233">Na página **Selecione a testemunha de Quorum**, clique em **Configurar uma testemunha de compartilhamento de arquivos**.</span><span class="sxs-lookup"><span data-stu-id="8b1bc-233">In the **Select Quorum Witness** page, click **Configure a file share witness**.</span></span>
    
   - <span data-ttu-id="8b1bc-234">Na página **Configurar Testemunha de Compartilhamento de Arquivo**, digite o caminho do compartilhamento de arquivos que você deseja usar e clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="8b1bc-234">In the **Configure File Share Witness** page, type the path of the file share you want to use, and then click **Next**.</span></span>
    
   - <span data-ttu-id="8b1bc-235">Na página **Confirmação**, clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="8b1bc-235">On the **Confirmation** page, click **Next**.</span></span>
    
9. <span data-ttu-id="8b1bc-236">Em cada servidor do cluster, habilite o recurso de AG no SQL Server Configuration Manager.</span><span class="sxs-lookup"><span data-stu-id="8b1bc-236">On each server in the cluster, enable the AG feature in SQL Server Configuration Manager.</span></span>
    
   - <span data-ttu-id="8b1bc-p131">Abra o SQL Server Configuration Manager. Na árvore no lado esquerdo da tela, clique em **Serviços do SQL Server** e, em seguida, clique duas vezes no serviço SQL Server. </span><span class="sxs-lookup"><span data-stu-id="8b1bc-p131">Open SQL Server Configuration Manager. In the tree on the left side of the screen, click **SQL Server Services**, then double-click the SQL Server service.</span></span> 
    
   - <span data-ttu-id="8b1bc-p132">Na caixa **Propriedades**, selecione a guia **Alta Disponibilidade AlwaysOn**. Marque a caixa de seleção **Habilitar Grupos de Disponibilidade AlwaysOn**. Reinicie o serviço SQL Server quando solicitado.</span><span class="sxs-lookup"><span data-stu-id="8b1bc-p132">In the **Properties** box, select the **AlwaysOn High Availability** tab. Select the **Enable AlwaysOn Availability Groups** check box. Restart the SQL Server service when prompted.</span></span>
    
10. <span data-ttu-id="8b1bc-241">Criar o grupo de disponibilidade.</span><span class="sxs-lookup"><span data-stu-id="8b1bc-241">Create the availability group.</span></span>
    
    - <span data-ttu-id="8b1bc-242">Abra o SQL Server Management Studio e conecte-se à instância do SQL Server.</span><span class="sxs-lookup"><span data-stu-id="8b1bc-242">Open SQL Server Management Studio, and connect to the SQL Server instance.</span></span>
    
    - <span data-ttu-id="8b1bc-243">No Object Explorer, expanda a pasta de **Sempre na alta disponibilidade** .</span><span class="sxs-lookup"><span data-stu-id="8b1bc-243">In Object Explorer, expand the **Always On High Availability** folder.</span></span> <span data-ttu-id="8b1bc-244">Clique com o botão direito do mouse na pasta **Grupos de Disponibilidade** e clique em **Assistente para Novo Grupo de Disponibilidade**.</span><span class="sxs-lookup"><span data-stu-id="8b1bc-244">Right-click the **Availability Groups** folder and click **New Availability Group Wizard**.</span></span>
    
    - <span data-ttu-id="8b1bc-245">Se a página **Introdução** for exibida, clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="8b1bc-245">If the **Introduction** page appears, click **Next**.</span></span>
    
    - <span data-ttu-id="8b1bc-246">Na página **Especificar Nome do Grupo de Disponibilidade**, digite o nome do Grupo de disponibilidade e clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="8b1bc-246">In the **Specify Availability Group Name** page, type the name of the Availability group, and click **Next**.</span></span>
    
    - <span data-ttu-id="8b1bc-247">Na página Selecionar bancos de dados, selecione os bancos de dados que você deseja incluir no grupo de disponibilidade do AlwaysOn.</span><span class="sxs-lookup"><span data-stu-id="8b1bc-247">In the Select Databases page, select the databases that you want to include in the AlwaysOn Availability Group.</span></span> <span data-ttu-id="8b1bc-248">Then click **Next**.</span><span class="sxs-lookup"><span data-stu-id="8b1bc-248">Then click **Next**.</span></span>
    
    <span data-ttu-id="8b1bc-249">Não inclua o **ReportServer**, **ReportServerTempDB**ou bancos de dados de Chat persistente no grupo de disponibilidade do AlwaysOn, como eles não são suportados neste cenário.</span><span class="sxs-lookup"><span data-stu-id="8b1bc-249">Do not include the **ReportServer**, **ReportServerTempDB**, or Persistent Chat databases in the AlwaysOn Availability Group, as these are not supported in this scenario.</span></span> <span data-ttu-id="8b1bc-250">Você pode incluir todos os outro Skype para bancos de dados do servidor de negócios no grupo de disponibilidade do AlwaysOn.</span><span class="sxs-lookup"><span data-stu-id="8b1bc-250">You can include all other Skype for Business Server databases in the AlwaysOn Availability Group.</span></span>
    
    - <span data-ttu-id="8b1bc-251">Na página **Especificar Réplicas**, clique na guia **Réplicas**. Clique no botão **Adicionar Réplicas** e conecte-se às outras instâncias do SQL que você incluiu como nós do Clustering de Failover do Windows Server.</span><span class="sxs-lookup"><span data-stu-id="8b1bc-251">In the **Specify Replicas** page, click the **Replicas** tab. Then click the **Add Replicas** button, and connect to the other SQL instances that you joined as nodes of the Windows Server Failover Cluster.</span></span>
    
    - <span data-ttu-id="8b1bc-p136">Para cada instância, selecione as opções **Failover Automático** e **Confirmação Síncrona**. Não selecione a opção **Secundária Legível**.</span><span class="sxs-lookup"><span data-stu-id="8b1bc-p136">For each instance, select the **Automatic Failover** and **Synchronous Commit** options. Do not select the **Readable Secondary** option.</span></span>
    
    - <span data-ttu-id="8b1bc-254">Clique na guia **Pontos de Extremidade** e verifique se o **Número da Porta** está definido como 5022.</span><span class="sxs-lookup"><span data-stu-id="8b1bc-254">Click the **Endpoints** tab and verify that **Port Number** is set to 5022.</span></span>
    
      - <span data-ttu-id="8b1bc-p137">Clique na guia **Ouvinte** e selecione a opção **Criar um ouvinte de grupo de disponibilidade**. Nesta opção, digite um nome para o ouvinte e defina a **Porta** como 1433 (outras portas não são suportadas para esta opção).</span><span class="sxs-lookup"><span data-stu-id="8b1bc-p137">Click the **Listener** tab, and select the **Create an availability group listener** option. Under that option, type a name for the listener, and set the **Port** to 1433 (other ports are not supported for this option).</span></span>
    
    - <span data-ttu-id="8b1bc-257">Clique em **Adicionar** e, na caixa **Endereço IPv4**, forneça o endereço IP virtual de sua preferência e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="8b1bc-257">Click **Add**, and then in the **IPv4 Address** box, provide your preferred virtual IP address, and then click **OK**.</span></span>
    
    - <span data-ttu-id="8b1bc-p138">Na página **Selecionar Sincronização de Dados Inicial**, selecione Completo, especifique uma pasta que possa ser acessada pelas réplicas e para a qual a conta do serviço SQL Server usada por ambas as réplicas tenha permissões de Gravação. Clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="8b1bc-p138">In the **Select Initial Data Synchronization** page, select Full, and specify a folder that is accessible to the replicas, and that the SQL Server service account used by both replicas has Write permissions for. Then click **Next**.</span></span>
    
    <span data-ttu-id="8b1bc-p139">Este compartilhamento de arquivos será usado temporariamente quando você inicializar os bancos de dados. Se você usar bancos de dados grandes, recomendamos que você os inicie manualmente caso a largura de banda de sua rede não possa acomodar o tamanho dos bancos de dados de backup.</span><span class="sxs-lookup"><span data-stu-id="8b1bc-p139">This file share will be used temporarily when you initialize the databases. If you are dealing with large databases, we recommend that you manually initialize them in case your network bandwidth cannot accommodate the size of the database backups.</span></span>
    
    - <span data-ttu-id="8b1bc-262">Na página Validação, confira se as verificações de validação foram bem-sucedidas e, em seguida, clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="8b1bc-262">In the Validation page, verify that all validation checks are successful, then click **Next**.</span></span>
    
    - <span data-ttu-id="8b1bc-263">Na página **Resumo**, verifique todas as configurações e clique em Concluir.</span><span class="sxs-lookup"><span data-stu-id="8b1bc-263">In the **Summary** page, verify all settings and click Finish.</span></span>
    
11. <span data-ttu-id="8b1bc-264">Crie um novo repositório especificando o ouvinte AG e especificando a entidade de segurança do espelho antigo como o nó principal da AG.</span><span class="sxs-lookup"><span data-stu-id="8b1bc-264">Create a new store specifying the AG listener, and specifying the principal of the old mirror as the primary node of the AG.</span></span>
    
    - <span data-ttu-id="8b1bc-265">Abra o construtor de topologia.</span><span class="sxs-lookup"><span data-stu-id="8b1bc-265">Open Topology Builder.</span></span> <span data-ttu-id="8b1bc-266">Em sua topologia, expanda **Componentes Compartilhados**, clique com o botão direito do mouse em **Repositórios do SQL Server** e clique em **Novo Repositório do SQL Server**.</span><span class="sxs-lookup"><span data-stu-id="8b1bc-266">In your topology, expand **Shared Components**, right-click **SQL Server Stores**, and click **New SQL Server Store**.</span></span>
    
    - <span data-ttu-id="8b1bc-267">Na página **Definir Novo Repositório SQL**, primeiro marque a caixa de seleção **Configurações de Alta Disponibilidade** e, em seguida, certifique-se de que a opção Grupos de Disponibilidade AlwaysOn do SQL aparece na caixa suspensa.</span><span class="sxs-lookup"><span data-stu-id="8b1bc-267">In the **Define New SQL Store** page, first select the **High Availability Settings** check box, and then make sure that SQL AlwaysOn Availability Groups appears in the drop-down box.</span></span>
    
    - <span data-ttu-id="8b1bc-268">Na caixa **FQDN do Ouvinte de Disponibilidade do SQL Server**, digite o FQDN do ouvinte que criou quando criou o grupo de disponibilidade.</span><span class="sxs-lookup"><span data-stu-id="8b1bc-268">In the **SQL Server Availability Listener FQDN** box, type the FQDN of the listener you created when you created the availability group.</span></span>
    
    - <span data-ttu-id="8b1bc-269">Na caixa **FQDN do SQL Server** , digite o FQDN do nó principal do AG e clique em **Okey**.</span><span class="sxs-lookup"><span data-stu-id="8b1bc-269">In the **SQL Server FQDN** box, type the FQDN of the primary node of the AG, and then click **OK**.</span></span> <span data-ttu-id="8b1bc-270">Ele deve ser a entidade de segurança do espelho antigo para esse repositório.</span><span class="sxs-lookup"><span data-stu-id="8b1bc-270">This should be the principal of the old mirror for this store.</span></span>
    
12. <span data-ttu-id="8b1bc-271">Associe a nova AG com o pool de Front-End.</span><span class="sxs-lookup"><span data-stu-id="8b1bc-271">Associate the new AG with the Front End pool.</span></span>
    
    - <span data-ttu-id="8b1bc-272">No construtor de topologia, clique com botão direito do pool para associar a AG e clique em **Editar propriedades**.</span><span class="sxs-lookup"><span data-stu-id="8b1bc-272">In Topology Builder, right-click the pool to associate with the AG, and click **Edit Properties**.</span></span>
    
    - <span data-ttu-id="8b1bc-273">Em **associações**, na caixa **Repositório do SQL Server** , selecione a AG.</span><span class="sxs-lookup"><span data-stu-id="8b1bc-273">Under **Associations**, in the **SQL Server Store** box, select the AG.</span></span> <span data-ttu-id="8b1bc-274">Selecione o grupo mesmo para outros bancos de dados no qual você deseja mover para a AG pool.</span><span class="sxs-lookup"><span data-stu-id="8b1bc-274">Select the same group for any other databases in the pool which you want to move to the AG.</span></span>
    
    - <span data-ttu-id="8b1bc-275">Quando tiver certeza de que todos os bancos de dados necessários são definidos como a AG, clique em **Okey**.</span><span class="sxs-lookup"><span data-stu-id="8b1bc-275">When you're sure that all needed databases are set to the AG, click **OK**.</span></span>
    
13. <span data-ttu-id="8b1bc-276">Publique a topologia.</span><span class="sxs-lookup"><span data-stu-id="8b1bc-276">Publish the topology.</span></span> <span data-ttu-id="8b1bc-277">No menu **Ação**, clique em **Topologia** e, em seguida, **Publicar**.</span><span class="sxs-lookup"><span data-stu-id="8b1bc-277">From the **Action** menu click **Topology** and then **Publish**.</span></span> <span data-ttu-id="8b1bc-278">Na página de confirmação, clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="8b1bc-278">Then in the confirmation page click **Next**.</span></span>
    
14. <span data-ttu-id="8b1bc-279">Execute algumas etapas finais para certificar-se de que os logons do SQL estão em cada uma das réplicas no grupo de disponibilidade do AlwaysOn.</span><span class="sxs-lookup"><span data-stu-id="8b1bc-279">Perform some final steps to make sure that the SQL logins are on each of the replicas in the AlwaysOn Availability Group.</span></span>
    
    - <span data-ttu-id="8b1bc-280">Abra o construtor de topologia, selecione **Baixar topologia da implantação existente**e clique em **Okey**.</span><span class="sxs-lookup"><span data-stu-id="8b1bc-280">Open Topology Builder, select **Download topology from existing deployment**, and click **OK**.</span></span>
    
    - <span data-ttu-id="8b1bc-281">Expanda o Skype for Business Server, expanda sua topologia e expanda **Repositórios do SQL Server**.</span><span class="sxs-lookup"><span data-stu-id="8b1bc-281">Expand Skype for Business Server, expand your topology, and expand **SQL Server Stores**.</span></span> <span data-ttu-id="8b1bc-282">Com o botão direito o repositório SQL da AG novo e clique em **Editar propriedades**.</span><span class="sxs-lookup"><span data-stu-id="8b1bc-282">Right-click the SQL store of the new AG, and click **Edit Properties**.</span></span>
    
    - <span data-ttu-id="8b1bc-283">Na parte inferior da página, na caixa **FQDN do SQL Server** , altere o valor para o FQDN do ouvinte da AG.</span><span class="sxs-lookup"><span data-stu-id="8b1bc-283">At the bottom of the page, in the **SQL Server FQDN** box, change the value to the FQDN of the Listener of the AG.</span></span>
    
    - <span data-ttu-id="8b1bc-p145">Publique a topologia. No menu **Ação**, clique em **Topologia** e, em seguida, **Publicar**. Na página de confirmação, clique em **Avançar**. Aguarde alguns minutos para a nova topologia ser replicada.</span><span class="sxs-lookup"><span data-stu-id="8b1bc-p145">Publish the topology. From the **Action** menu click **Topology** and then **Publish**. Then in the confirmation page click **Next**. Then wait a few minutes for the new topology to replicate.</span></span>
    
    - <span data-ttu-id="8b1bc-288">Abra o SQL Server Management Studio e navegue até a AG.</span><span class="sxs-lookup"><span data-stu-id="8b1bc-288">Open SQL Server Management Studio, and navigate to the AG.</span></span> <span data-ttu-id="8b1bc-289">Faça failover para uma réplica secundária.</span><span class="sxs-lookup"><span data-stu-id="8b1bc-289">Fail it over to a secondary replica.</span></span>
    
    - <span data-ttu-id="8b1bc-290">Abra o Skype do Shell de gerenciamento do servidor de negócios e digite o seguinte cmdlet para criar logons do SQL nesta réplica:</span><span class="sxs-lookup"><span data-stu-id="8b1bc-290">Open Skype for Business Server Management Shell and type the following cmdlet to create the SQL logins on this replica:</span></span>
    
    ```
    Install-CsDatabase -Update
    ```

    - <span data-ttu-id="8b1bc-291">Repita as duas etapas anteriores (failover no grupo para uma réplica secundária e, em seguida, usar `Install-CsDatabase -Update`) para cada réplica no grupo.</span><span class="sxs-lookup"><span data-stu-id="8b1bc-291">Repeat the previous two steps (fail over the group to a secondary replica, then use  `Install-CsDatabase -Update`) for each replica in the group.</span></span>
    
## <a name="deploy-an-always-on-availability-group-on-an-existing-pool-that-does-not-use-database-mirroring"></a><span data-ttu-id="8b1bc-292">Implantar um sempre no grupo de disponibilidade em um pool existente que não usa o espelhamento de banco de dados</span><span class="sxs-lookup"><span data-stu-id="8b1bc-292">Deploy an Always On Availability Group on an existing pool that does not use database mirroring</span></span>
<span data-ttu-id="8b1bc-293"><a name="BKMK_NoHAPool_CreateAlwaysOnGroup"> </a></span><span class="sxs-lookup"><span data-stu-id="8b1bc-293"></span></span>

> [!NOTE]
> <span data-ttu-id="8b1bc-294">Se o pool que você estiver atualizando para uma AG hospedar o repositório de gerenciamento Central para sua organização, você deve primeiro mover o CMS para outro pool antes de atualizar este pool.</span><span class="sxs-lookup"><span data-stu-id="8b1bc-294">If the pool you are upgrading to an AG hosts the Central Management store for your organization, you must first move the CMS to another pool before you upgrade this pool.</span></span> <span data-ttu-id="8b1bc-295">Use o cmdlet Move-CsManagementServer para mover o pool.</span><span class="sxs-lookup"><span data-stu-id="8b1bc-295">Use the Move-CsManagementServer cmdlet to move the pool.</span></span> <span data-ttu-id="8b1bc-296">Se você não tiver outro pool em sua organização, você pode implantar um servidor Standard Edition temporariamente e mover o CMS para esse servidor antes de atualizar seu pool para a AG.</span><span class="sxs-lookup"><span data-stu-id="8b1bc-296">If you do not have another pool in your organization, you can deploy a Standard Edition server temporarily and move the CMS to this server before you upgrade your pool to the AG.</span></span> 
  
1. <span data-ttu-id="8b1bc-297">Configure o recurso de cluster de Failover em todos os servidores de banco de dados que farão parte da AG.</span><span class="sxs-lookup"><span data-stu-id="8b1bc-297">Set up the Failover Clustering feature on all the database servers which will be part of the AG.</span></span> <span data-ttu-id="8b1bc-298">Em cada servidor, faça o seguinte:</span><span class="sxs-lookup"><span data-stu-id="8b1bc-298">On each server, do the following</span></span>
    
   - <span data-ttu-id="8b1bc-299">Abra o Server Manager e clique em **Adicionar funções e recurso**.</span><span class="sxs-lookup"><span data-stu-id="8b1bc-299">Open Server Manager and click **Add roles and features**.</span></span>
    
   - <span data-ttu-id="8b1bc-p149">Clique em **Avançar** até chegar à caixa **Selecionar recursos**. Aqui, marque a caixa de seleção **Clustering de Failover**.</span><span class="sxs-lookup"><span data-stu-id="8b1bc-p149">Click **Next** until you reach the **Select features** box. Here, select the **Failover Clustering** check box.</span></span>
    
   - <span data-ttu-id="8b1bc-302">Na caixa **Adicionar recursos necessários para o Clustering de Failover?**, clique em **Adicionar Recursos**.</span><span class="sxs-lookup"><span data-stu-id="8b1bc-302">In the **Add features that are required for Failover Clustering?** box, click **Add Features**.</span></span>
    
   - <span data-ttu-id="8b1bc-303">Clique em **Instalar**.</span><span class="sxs-lookup"><span data-stu-id="8b1bc-303">Click **Install**.</span></span>
    
2. <span data-ttu-id="8b1bc-304">Validar a configuração de cluster.</span><span class="sxs-lookup"><span data-stu-id="8b1bc-304">Validate the cluster configuration.</span></span>
    
   - <span data-ttu-id="8b1bc-305">No Server Manager, clique no menu **Ferramentas** e, em seguida, clique em **Gerenciador de Cluster de Failover**.</span><span class="sxs-lookup"><span data-stu-id="8b1bc-305">In Server Manager, click the **Tools** menu and then click **Failover Cluster Manager**.</span></span>
    
   - <span data-ttu-id="8b1bc-306">Em **Ações** no lado direito da tela, clique em **Validar Configuração**.</span><span class="sxs-lookup"><span data-stu-id="8b1bc-306">Under **Actions** on the right side of the screen, click **Validate Configuration**.</span></span>
    
   - <span data-ttu-id="8b1bc-307">Na página **Antes de começar**, clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="8b1bc-307">On the **Before You Begin** page, click **Next**.</span></span>
    
   - <span data-ttu-id="8b1bc-308">Selecione os servidores a serem adicionados ao cluster e clique em **Executar todos os testes**.</span><span class="sxs-lookup"><span data-stu-id="8b1bc-308">Select the servers to add to the cluster, and then click **Run all tests**.</span></span>
    
   - <span data-ttu-id="8b1bc-p150">Na caixa **Resumo**, verifique os erros relatados pelo assistente. Clique em **Concluir** para concluir a validação.</span><span class="sxs-lookup"><span data-stu-id="8b1bc-p150">In the **Summary** box, check any errors that the wizard reports. Then click **Finish** to complete the validation.</span></span>
    
     <span data-ttu-id="8b1bc-p151">O assistente provavelmente mostrará diversos avisos, especialmente se você não estiver usando armazenamento compartilhado. Não é necessário usar o armazenamento compartilhado. No entanto, se você vir alguma mensagem de **Erro**, deverá corrigir esses problemas antes de continuar.</span><span class="sxs-lookup"><span data-stu-id="8b1bc-p151">The wizard will probably report several warnings, especially if you are not using shared storage. You are not required to use shared storage. However, if you see any **Error** messages, you must fix those issues before continuing.</span></span>
    
3. <span data-ttu-id="8b1bc-314">Crie o Cluster de Failover do Windows Server (WSFC).</span><span class="sxs-lookup"><span data-stu-id="8b1bc-314">Create the Windows Server Failover Cluster (WSFC).</span></span>
    
   - <span data-ttu-id="8b1bc-315">No assistente de **Gerenciamento de Cluster de Failover**, clique com o botão direito do mouse em **Gerenciamento de Cluster de Failover** e, em seguida, clique em **Criar Cluster**.</span><span class="sxs-lookup"><span data-stu-id="8b1bc-315">In the **Failover Cluster Management** wizard, right-click **Failover Cluster Management**, then click **Create Cluster**.</span></span>
    
   - <span data-ttu-id="8b1bc-316">Na página **Antes de começar**, clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="8b1bc-316">On the **Before You Begin** page, click **Next**.</span></span>
    
   - <span data-ttu-id="8b1bc-p152">Adicione o nome e o endereço IP do cluster. Quando as definições forem validadas, clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="8b1bc-p152">Add the cluster name and IP address. When the settings are validated, click **Next**.</span></span>
    
   - <span data-ttu-id="8b1bc-319">Na página Confirmação, clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="8b1bc-319">On the Confirmation page, click **Next**.</span></span>
    
   - <span data-ttu-id="8b1bc-320">Depois que o cluster for criado, clique em **Concluir**.</span><span class="sxs-lookup"><span data-stu-id="8b1bc-320">After the cluster is created, click **Finish**.</span></span>
    
4. <span data-ttu-id="8b1bc-p153">Recomendamos que você defina as configurações de quorum do cluster para usar uma testemunha de compartilhamento de arquivos. Para isso, siga estas instruções:</span><span class="sxs-lookup"><span data-stu-id="8b1bc-p153">We recommend that you configure the cluster quorum settings to use a file share witness. To do so, use these steps:</span></span>
    
   - <span data-ttu-id="8b1bc-323">Clique com o botão direito do mouse no nome do cluster, em **Mais Ações** e, em seguida, em **Configurar Quorum do Cluster**.</span><span class="sxs-lookup"><span data-stu-id="8b1bc-323">Right-click the cluster name, click **More Actions**, and click **Configure Cluster Quorum Settings**.</span></span>
    
   - <span data-ttu-id="8b1bc-324">Na página **Selecionar Opção de Configuração de Quorum**, clique em **Selecione a testemunha de Quorum**.</span><span class="sxs-lookup"><span data-stu-id="8b1bc-324">In the **Select Quorum Configuration Option** page, click **Select the quorum witness**.</span></span>
    
   - <span data-ttu-id="8b1bc-325">Na página **Selecione a testemunha de Quorum**, clique em **Configurar uma testemunha de compartilhamento de arquivos**.</span><span class="sxs-lookup"><span data-stu-id="8b1bc-325">In the **Select Quorum Witness** page, click **Configure a file share witness**.</span></span>
    
   - <span data-ttu-id="8b1bc-326">Na página **Configurar Testemunha de Compartilhamento de Arquivo**, digite o caminho do compartilhamento de arquivos que você deseja usar e clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="8b1bc-326">In the **Configure File Share Witness** page, type the path of the file share you want to use, and then click **Next**.</span></span>
    
   - <span data-ttu-id="8b1bc-327">Na página **Confirmação**, clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="8b1bc-327">On the **Confirmation** page, click **Next**.</span></span>
    
5. <span data-ttu-id="8b1bc-328">Em cada servidor do cluster, habilite AG no SQL Server Configuration Manager.</span><span class="sxs-lookup"><span data-stu-id="8b1bc-328">On each server in the cluster, enable AG in SQL Server Configuration Manager.</span></span>
    
   - <span data-ttu-id="8b1bc-p154">Abra o SQL Server Configuration Manager. Na árvore no lado esquerdo da tela, clique em **Serviços do SQL Server** e, em seguida, clique duas vezes no serviço SQL Server. </span><span class="sxs-lookup"><span data-stu-id="8b1bc-p154">Open SQL Server Configuration Manager. In the tree on the left side of the screen, click **SQL Server Services**, then double-click the SQL Server service.</span></span> 
    
   - <span data-ttu-id="8b1bc-p155">Na caixa **Propriedades**, selecione a guia **Alta Disponibilidade AlwaysOn**. Marque a caixa de seleção **Habilitar Grupos de Disponibilidade AlwaysOn**. Reinicie o serviço SQL Server quando solicitado.</span><span class="sxs-lookup"><span data-stu-id="8b1bc-p155">In the **Properties** box, select the **AlwaysOn High Availability** tab. Select the **Enable AlwaysOn Availability Groups** check box. Restart the SQL Server service when prompted.</span></span>
    
6. <span data-ttu-id="8b1bc-333">Criar o grupo de disponibilidade.</span><span class="sxs-lookup"><span data-stu-id="8b1bc-333">Create the availability group.</span></span>
    
   - <span data-ttu-id="8b1bc-334">Abra o SQL Server Management Studio e conecte-se à instância do SQL Server.</span><span class="sxs-lookup"><span data-stu-id="8b1bc-334">Open SQL Server Management Studio, and connect to the SQL Server instance.</span></span>
    
   - <span data-ttu-id="8b1bc-335">No Object Explorer, expanda a pasta de **Sempre na alta disponibilidade** .</span><span class="sxs-lookup"><span data-stu-id="8b1bc-335">In Object Explorer, expand the **Always On High Availability** folder.</span></span> <span data-ttu-id="8b1bc-336">Clique com o botão direito do mouse na pasta **Grupos de Disponibilidade** e clique em **Assistente para Novo Grupo de Disponibilidade**.</span><span class="sxs-lookup"><span data-stu-id="8b1bc-336">Right-click the **Availability Groups** folder and click **New Availability Group Wizard**.</span></span>
    
   - <span data-ttu-id="8b1bc-337">Se a página **Introdução** for exibida, clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="8b1bc-337">If the **Introduction** page appears, click **Next**.</span></span>
    
   - <span data-ttu-id="8b1bc-338">Na página **Especificar Nome do Grupo de Disponibilidade**, digite o nome do Grupo de disponibilidade e clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="8b1bc-338">In the **Specify Availability Group Name** page, type the name of the Availability group, and click **Next**.</span></span>
    
   - <span data-ttu-id="8b1bc-339">Na página Selecionar bancos de dados, selecione os bancos de dados que você deseja incluir na AG.</span><span class="sxs-lookup"><span data-stu-id="8b1bc-339">In the Select Databases page, select the databases that you want to include in the AG.</span></span> <span data-ttu-id="8b1bc-340">Then click **Next**.</span><span class="sxs-lookup"><span data-stu-id="8b1bc-340">Then click **Next**.</span></span>
    
     <span data-ttu-id="8b1bc-341">Não inclua o **ReportServer**, **ReportServerTempDB**ou bancos de dados de Chat persistente no AG, como eles não são suportados neste cenário.</span><span class="sxs-lookup"><span data-stu-id="8b1bc-341">Do not include the **ReportServer**, **ReportServerTempDB**, or Persistent Chat databases in the AG, as these are not supported in this scenario.</span></span> <span data-ttu-id="8b1bc-342">Você pode incluir todos os outro Skype para bancos de dados do servidor de negócios na AG.</span><span class="sxs-lookup"><span data-stu-id="8b1bc-342">You can include all other Skype for Business Server databases in the AG.</span></span>
    
   - <span data-ttu-id="8b1bc-343">Na página **Especificar réplicas** , clique na guia de **réplicas** . Em seguida, clique no botão **Adicionar réplicas** e conecte-se para as outras instâncias do SQL que você ingressou como nós o WSFC.</span><span class="sxs-lookup"><span data-stu-id="8b1bc-343">In the **Specify Replicas** page, click the **Replicas** tab. Then click the **Add Replicas** button, and connect to the other SQL instances that you joined as nodes of the WSFC.</span></span>
    
   - <span data-ttu-id="8b1bc-p159">Para cada instância, selecione as opções **Failover Automático** e **Confirmação Síncrona**. Não selecione a opção **Secundária Legível**.</span><span class="sxs-lookup"><span data-stu-id="8b1bc-p159">For each instance, select the **Automatic Failover** and **Synchronous Commit** options. Do not select the **Readable Secondary** option.</span></span>
    
   - <span data-ttu-id="8b1bc-346">Clique na guia **Pontos de Extremidade** e verifique se o **Número da Porta** está definido como 5022.</span><span class="sxs-lookup"><span data-stu-id="8b1bc-346">Click the **Endpoints** tab and verify that **Port Number** is set to 5022.</span></span>
    
   - <span data-ttu-id="8b1bc-p160">Clique na guia **Ouvinte** e selecione a opção **Criar um ouvinte de grupo de disponibilidade**. Nesta opção, digite um nome para o ouvinte e defina a **Porta** como 1433 (outras portas não são suportadas para esta opção).</span><span class="sxs-lookup"><span data-stu-id="8b1bc-p160">Click the **Listener** tab, and select the **Create an availability group listener** option. Under that option, type a name for the listener, and set the **Port** to 1433 (other ports are not supported for this option).</span></span>
    
   - <span data-ttu-id="8b1bc-349">Clique em **Adicionar** e, na caixa **Endereço IPv4**, forneça o endereço IP virtual de sua preferência e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="8b1bc-349">Click **Add**, and then in the **IPv4 Address** box, provide your preferred virtual IP address, and then click **OK**.</span></span>
    
   - <span data-ttu-id="8b1bc-p161">Na página **Selecionar Sincronização de Dados Inicial**, selecione Completo, especifique uma pasta que possa ser acessada pelas réplicas e para a qual a conta do serviço SQL Server usada por ambas as réplicas tenha permissões de Gravação. Clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="8b1bc-p161">In the **Select Initial Data Synchronization** page, select Full, and specify a folder that is accessible to the replicas, and that the SQL Server service account used by both replicas has Write permissions for. Then click **Next**.</span></span>
    
     <span data-ttu-id="8b1bc-p162">Este compartilhamento de arquivos será usado temporariamente quando você inicializar os bancos de dados. Se você usar bancos de dados grandes, recomendamos que você os inicie manualmente caso a largura de banda de sua rede não possa acomodar o tamanho dos bancos de dados de backup.</span><span class="sxs-lookup"><span data-stu-id="8b1bc-p162">This file share will be used temporarily when you initialize the databases. If you are dealing with large databases, we recommend that you manually initialize them in case your network bandwidth cannot accommodate the size of the database backups.</span></span>
    
     - <span data-ttu-id="8b1bc-354">Na página Validação, confira se as verificações de validação foram bem-sucedidas e, em seguida, clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="8b1bc-354">In the Validation page, verify that all validation checks are successful, then click **Next**.</span></span>
    
   - <span data-ttu-id="8b1bc-355">Na página **Resumo**, verifique todas as configurações e clique em Concluir.</span><span class="sxs-lookup"><span data-stu-id="8b1bc-355">In the **Summary** page, verify all settings and click Finish.</span></span>
    
7. <span data-ttu-id="8b1bc-356">Crie um novo repositório especificando o ouvinte AG.</span><span class="sxs-lookup"><span data-stu-id="8b1bc-356">Create a new store specifying the AG listener.</span></span>
    
   - <span data-ttu-id="8b1bc-357">Abra o construtor de topologia.</span><span class="sxs-lookup"><span data-stu-id="8b1bc-357">Open Topology Builder.</span></span> <span data-ttu-id="8b1bc-358">Em sua topologia, expanda **Componentes Compartilhados**, clique com o botão direito do mouse em **Repositórios do SQL Server** e clique em **Novo Repositório do SQL Server**.</span><span class="sxs-lookup"><span data-stu-id="8b1bc-358">In your topology, expand **Shared Components**, right-click **SQL Server Stores**, and click **New SQL Server Store**.</span></span>
    
   - <span data-ttu-id="8b1bc-359">Na página **Definir Novo Repositório SQL**, primeiro marque a caixa de seleção **Configurações de Alta Disponibilidade** e, em seguida, certifique-se de que a opção Grupos de Disponibilidade AlwaysOn do SQL aparece na caixa suspensa.</span><span class="sxs-lookup"><span data-stu-id="8b1bc-359">In the **Define New SQL Store** page, first select the **High Availability Settings** check box, and then make sure that SQL AlwaysOn Availability Groups appears in the drop-down box.</span></span>
    
   - <span data-ttu-id="8b1bc-360">Na caixa **FQDN do Ouvinte de Disponibilidade do SQL Server**, digite o FQDN do ouvinte que criou quando criou o grupo de disponibilidade.</span><span class="sxs-lookup"><span data-stu-id="8b1bc-360">In the **SQL Server Availability Listener FQDN** box, type the FQDN of the listener you created when you created the availability group.</span></span>
    
   - <span data-ttu-id="8b1bc-361">Na caixa **FQDN do SQL Server** , digite o FQDN do nó principal do AG e clique em **Okey**.</span><span class="sxs-lookup"><span data-stu-id="8b1bc-361">In the **SQL Server FQDN** box, type the FQDN of the primary node of the AG, and then click **OK**.</span></span>
    
8. <span data-ttu-id="8b1bc-362">Associe o novo sempre no grupo de disponibilidade com o pool de Front-End.</span><span class="sxs-lookup"><span data-stu-id="8b1bc-362">Associate the new Always On Availability Group with the Front End pool.</span></span>
    
   - <span data-ttu-id="8b1bc-363">No construtor de topologia, clique com botão direito do pool para associar a AG e clique em **Editar propriedades**.</span><span class="sxs-lookup"><span data-stu-id="8b1bc-363">In Topology Builder, right-click the pool to associate with the AG, and click **Edit Properties**.</span></span>
    
   - <span data-ttu-id="8b1bc-364">Em **associações**, na caixa **Repositório do SQL Server** , selecione a AG.</span><span class="sxs-lookup"><span data-stu-id="8b1bc-364">Under **Associations**, in the **SQL Server Store** box, select the AG.</span></span> <span data-ttu-id="8b1bc-365">Selecione o grupo mesmo para outros bancos de dados no qual você deseja mover para a AG pool.</span><span class="sxs-lookup"><span data-stu-id="8b1bc-365">Select the same group for any other databases in the pool which you want to move to the AG.</span></span>
    
   - <span data-ttu-id="8b1bc-366">Quando tiver certeza de que todos os bancos de dados necessários são definidos como a AG, clique em **Okey**.</span><span class="sxs-lookup"><span data-stu-id="8b1bc-366">When you're sure that all needed databases are set to the AG, click **OK**.</span></span>
    
9. <span data-ttu-id="8b1bc-367">Publique a topologia.</span><span class="sxs-lookup"><span data-stu-id="8b1bc-367">Publish the topology.</span></span> <span data-ttu-id="8b1bc-368">No menu **Ação**, clique em **Topologia** e, em seguida, **Publicar**.</span><span class="sxs-lookup"><span data-stu-id="8b1bc-368">From the **Action** menu click **Topology** and then **Publish**.</span></span> <span data-ttu-id="8b1bc-369">Na página de confirmação, clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="8b1bc-369">Then in the confirmation page click **Next**.</span></span>
    
10. <span data-ttu-id="8b1bc-370">Execute algumas etapas finais para certificar-se de que os logons do SQL estão em cada uma das réplicas na AG.</span><span class="sxs-lookup"><span data-stu-id="8b1bc-370">Perform some final steps to make sure that the SQL logins are on each of the replicas in the AG.</span></span>
    
    - <span data-ttu-id="8b1bc-371">Abra o construtor de topologia, selecione **Baixar topologia da implantação existente**e clique em **Okey**.</span><span class="sxs-lookup"><span data-stu-id="8b1bc-371">Open Topology Builder, select **Download topology from existing deployment**, and click **OK**.</span></span>
    
    - <span data-ttu-id="8b1bc-372">Expanda o Skype for Business Server, expanda sua topologia e expanda **Repositórios do SQL Server**.</span><span class="sxs-lookup"><span data-stu-id="8b1bc-372">Expand Skype for Business Server, expand your topology, and expand **SQL Server Stores**.</span></span> <span data-ttu-id="8b1bc-373">Com o botão direito o repositório SQL da AG novo e clique em **Editar propriedades**.</span><span class="sxs-lookup"><span data-stu-id="8b1bc-373">Right-click the SQL store of the new AG, and click **Edit Properties**.</span></span>
    
    - <span data-ttu-id="8b1bc-374">Na parte inferior da página, na caixa **FQDN do SQL Server** , altere o valor para o FQDN do ouvinte da AG.</span><span class="sxs-lookup"><span data-stu-id="8b1bc-374">At the bottom of the page, in the **SQL Server FQDN** box, change the value to the FQDN of the Listener of the AG.</span></span>
    
    - <span data-ttu-id="8b1bc-p167">Publique a topologia. No menu **Ação**, clique em **Topologia** e, em seguida, **Publicar**. Na página de confirmação, clique em **Avançar**. Aguarde alguns minutos para a nova topologia ser replicada.</span><span class="sxs-lookup"><span data-stu-id="8b1bc-p167">Publish the topology. From the **Action** menu click **Topology** and then **Publish**. Then in the confirmation page click **Next**. Then wait a few minutes for the new topology to replicate.</span></span>
    
    - <span data-ttu-id="8b1bc-379">Abra o SQL Server Management Studio e navegue até a AG.</span><span class="sxs-lookup"><span data-stu-id="8b1bc-379">Open SQL Server Management Studio, and navigate to the AG.</span></span> <span data-ttu-id="8b1bc-380">Faça failover para uma réplica secundária.</span><span class="sxs-lookup"><span data-stu-id="8b1bc-380">Fail it over to a secondary replica.</span></span>
    
    - <span data-ttu-id="8b1bc-381">Abra o Skype do Shell de gerenciamento do servidor de negócios e digite o seguinte cmdlet para criar logons do SQL nesta réplica:</span><span class="sxs-lookup"><span data-stu-id="8b1bc-381">Open Skype for Business Server Management Shell and type the following cmdlet to create the SQL logins on this replica:</span></span>
    
      ```
      Install-CsDatabase -Update
      ```

      - <span data-ttu-id="8b1bc-382">Repita as duas etapas anteriores (failover no grupo para uma réplica secundária e, em seguida, usar `Install-CsDatabase -Update`) para cada réplica no grupo.</span><span class="sxs-lookup"><span data-stu-id="8b1bc-382">Repeat the previous two steps (fail over the group to a secondary replica, then use  `Install-CsDatabase -Update`) for each replica in the group.</span></span>
