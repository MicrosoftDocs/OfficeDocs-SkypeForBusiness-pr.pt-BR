---
title: Implantar um grupo de disponibilidade AlwaysOn em um servidor back-end no Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: c93c01e6-626c-40ad-92dd-373b0fe9189f
description: Implantar (instalar) um grupo de disponibilidade AlwaysOn na implantação do Skype for Business Server.
ms.openlocfilehash: 2cfc75aecd53a82e146feefd944134a4695c21fe
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/07/2019
ms.locfileid: "36240122"
---
# <a name="deploy-an-always-on-availability-group-on-a-back-end-server-in-skype-for-business-server"></a><span data-ttu-id="bc423-103">Implantar um grupo de disponibilidade AlwaysOn em um servidor back-end no Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="bc423-103">Deploy an Always On Availability Group on a Back End Server in Skype for Business Server</span></span>
 
<span data-ttu-id="bc423-104">Implantar (instalar) um AG (grupo de disponibilidade contínua) na implantação do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="bc423-104">Deploy (install) an Always On Availability Group (AG) in your Skype for Business Server deployment.</span></span>
  
<span data-ttu-id="bc423-105">A maneira como você implanta uma AG depende se você a está implantando em um novo pool, um pool existente que usa espelhamento ou um pool existente que atualmente não tem alta disponibilidade para o banco de dados back-end.</span><span class="sxs-lookup"><span data-stu-id="bc423-105">How you deploy an AG depends on whether you are deploying it in a new pool, an existing pool that uses mirroring, or an existing pool that currently has no high availability for the Back End database.</span></span>
  
> [!NOTE]
> <span data-ttu-id="bc423-106">Não há suporte para o uso de uma AG com uma função de servidor de chat persistente.</span><span class="sxs-lookup"><span data-stu-id="bc423-106">Using an AG with a Persistent Chat Server role is not supported.</span></span> 
  
- [<span data-ttu-id="bc423-107">Implantar um grupo de disponibilidade AlwaysOn em um novo pool de front-end</span><span class="sxs-lookup"><span data-stu-id="bc423-107">Deploy an Always On Availability Group on a new Front End pool</span></span>](alwayson-availability-group.md#BKMK_NewPool_CreateAlwaysOnGroup)
    
- [<span data-ttu-id="bc423-108">Implantar um grupo de disponibilidade AlwaysOn em um pool existente que usa o espelhamento de banco de dados</span><span class="sxs-lookup"><span data-stu-id="bc423-108">Deploy an Always On Availability Group on an existing pool that uses database mirroring</span></span>](alwayson-availability-group.md#BKMK_MirroredPool_CreateAlwaysOnGroup)
    
- [<span data-ttu-id="bc423-109">Implantar um grupo de disponibilidade AlwaysOn em um pool existente que não usa o espelhamento de banco de dados</span><span class="sxs-lookup"><span data-stu-id="bc423-109">Deploy an Always On Availability Group on an existing pool that does not use database mirroring</span></span>](alwayson-availability-group.md#BKMK_NoHAPool_CreateAlwaysOnGroup)
    
## <a name="deploy-an-always-on-availability-group-on-a-new-front-end-pool"></a><span data-ttu-id="bc423-110">Implantar um grupo de disponibilidade AlwaysOn em um novo pool de front-end</span><span class="sxs-lookup"><span data-stu-id="bc423-110">Deploy an Always On Availability Group on a new Front End pool</span></span>
<span data-ttu-id="bc423-111"><a name="BKMK_NewPool_CreateAlwaysOnGroup"> </a></span><span class="sxs-lookup"><span data-stu-id="bc423-111"></span></span>

1. <span data-ttu-id="bc423-112">Habilite o recurso de cluster de failover em todos os servidores de banco de dados que farão parte da AG.</span><span class="sxs-lookup"><span data-stu-id="bc423-112">Enable the Failover Clustering feature on all the database servers which will be part of the AG.</span></span> <span data-ttu-id="bc423-113">Em cada servidor, faça o seguinte:</span><span class="sxs-lookup"><span data-stu-id="bc423-113">On each server, do the following</span></span>
    
   - <span data-ttu-id="bc423-114">Abra o Server Manager e clique em **Adicionar funções e recurso**.</span><span class="sxs-lookup"><span data-stu-id="bc423-114">Open Server Manager and click **Add roles and features**.</span></span>
    
   - <span data-ttu-id="bc423-p102">Clique em **Avançar** até chegar à caixa **Selecionar recursos**. Aqui, marque a caixa de seleção **Clustering de Failover**.</span><span class="sxs-lookup"><span data-stu-id="bc423-p102">Click **Next** until you reach the **Select features** box. Here, select the **Failover Clustering** check box.</span></span>
    
   - <span data-ttu-id="bc423-117">Na caixa **Adicionar recursos necessários para o Clustering de Failover?**, clique em **Adicionar Recursos**.</span><span class="sxs-lookup"><span data-stu-id="bc423-117">In the **Add features that are required for Failover Clustering?** box, click **Add Features**.</span></span>
    
   - <span data-ttu-id="bc423-118">Clique em **Instalar**.</span><span class="sxs-lookup"><span data-stu-id="bc423-118">Click **Install**.</span></span>
    
2. <span data-ttu-id="bc423-119">Validar a configuração de cluster.</span><span class="sxs-lookup"><span data-stu-id="bc423-119">Validate the cluster configuration.</span></span>
    
   - <span data-ttu-id="bc423-120">No Server Manager, clique no menu **Ferramentas** e, em seguida, clique em **Gerenciador de Cluster de Failover**.</span><span class="sxs-lookup"><span data-stu-id="bc423-120">In Server Manager, click the **Tools** menu and then click **Failover Cluster Manager**.</span></span>
    
   - <span data-ttu-id="bc423-121">Em **Ações** no lado direito da tela, clique em **Validar Configuração**.</span><span class="sxs-lookup"><span data-stu-id="bc423-121">Under **Actions** on the right side of the screen, click **Validate Configuration**.</span></span>
    
   - <span data-ttu-id="bc423-122">Na página **Antes de começar**, clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="bc423-122">On the **Before You Begin** page, click **Next**.</span></span>
    
   - <span data-ttu-id="bc423-123">Selecione os servidores a serem adicionados ao cluster e clique em **Executar todos os testes**.</span><span class="sxs-lookup"><span data-stu-id="bc423-123">Select the servers to add to the cluster, and then click **Run all tests**.</span></span>
    
   - <span data-ttu-id="bc423-p103">Na caixa **Resumo**, verifique os erros relatados pelo assistente. Clique em **Concluir** para concluir a validação.</span><span class="sxs-lookup"><span data-stu-id="bc423-p103">In the **Summary** box, check any errors that the wizard reports. Then click **Finish** to complete the validation.</span></span>
    
     <span data-ttu-id="bc423-p104">O assistente provavelmente mostrará diversos avisos, especialmente se você não estiver usando armazenamento compartilhado. Não é necessário usar o armazenamento compartilhado. No entanto, se você vir alguma mensagem de **Erro**, deverá corrigir esses problemas antes de continuar.</span><span class="sxs-lookup"><span data-stu-id="bc423-p104">The wizard will probably report several warnings, especially if you are not using shared storage. You are not required to use shared storage. However, if you see any **Error** messages, you must fix those issues before continuing.</span></span>
    
3. <span data-ttu-id="bc423-129">Crie o WSFC (cluster de failover do Windows Server).</span><span class="sxs-lookup"><span data-stu-id="bc423-129">Create the Windows Server Failover Cluster (WSFC).</span></span>
    
   - <span data-ttu-id="bc423-130">No assistente de **Gerenciamento de Cluster de Failover**, clique com o botão direito do mouse em **Gerenciamento de Cluster de Failover** e, em seguida, clique em **Criar Cluster**.</span><span class="sxs-lookup"><span data-stu-id="bc423-130">In the **Failover Cluster Management** wizard, right-click **Failover Cluster Management**, then click **Create Cluster**.</span></span>
    
   - <span data-ttu-id="bc423-131">Na página **Antes de começar**, clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="bc423-131">On the **Before You Begin** page, click **Next**.</span></span>
    
   - <span data-ttu-id="bc423-p105">Adicione o nome e o endereço IP do cluster. Quando as definições forem validadas, clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="bc423-p105">Add the cluster name and IP address. When the settings are validated, click **Next**.</span></span>
    
   - <span data-ttu-id="bc423-134">Na página Confirmação, clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="bc423-134">On the Confirmation page, click **Next**.</span></span>
    
   - <span data-ttu-id="bc423-135">Depois que o cluster for criado, clique em **Concluir**.</span><span class="sxs-lookup"><span data-stu-id="bc423-135">After the cluster is created, click **Finish**.</span></span>
    
4. <span data-ttu-id="bc423-p106">Recomendamos que você defina as configurações de quorum do cluster para usar uma testemunha de compartilhamento de arquivos. Para isso, siga estas instruções:</span><span class="sxs-lookup"><span data-stu-id="bc423-p106">We recommend that you configure the cluster quorum settings to use a file share witness. To do so, use these steps:</span></span>
    
   - <span data-ttu-id="bc423-138">Clique com o botão direito do mouse no nome do cluster, em **Mais Ações** e, em seguida, em **Configurar Quorum do Cluster**.</span><span class="sxs-lookup"><span data-stu-id="bc423-138">Right-click the cluster name, click **More Actions**, and click **Configure Cluster Quorum Settings**.</span></span>
    
   - <span data-ttu-id="bc423-139">Na página **Selecionar Opção de Configuração de Quorum**, clique em **Selecione a testemunha de Quorum**.</span><span class="sxs-lookup"><span data-stu-id="bc423-139">In the **Select Quorum Configuration Option** page, click **Select the quorum witness**.</span></span>
    
   - <span data-ttu-id="bc423-140">Na página **Selecione a testemunha de Quorum**, clique em **Configurar uma testemunha de compartilhamento de arquivos**.</span><span class="sxs-lookup"><span data-stu-id="bc423-140">In the **Select Quorum Witness** page, click **Configure a file share witness**.</span></span>
    
   - <span data-ttu-id="bc423-141">Na página **Configurar Testemunha de Compartilhamento de Arquivo**, digite o caminho do compartilhamento de arquivos que você deseja usar e clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="bc423-141">In the **Configure File Share Witness** page, type the path of the file share you want to use, and then click **Next**.</span></span>
    
   - <span data-ttu-id="bc423-142">Na página **Confirmação**, clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="bc423-142">On the **Confirmation** page, click **Next**.</span></span>
    
5. <span data-ttu-id="bc423-143">Em cada servidor do cluster, habilite o recurso AG no Gerenciador de configuração do SQL Server.</span><span class="sxs-lookup"><span data-stu-id="bc423-143">On each server in the cluster, enable the AG feature in SQL Server Configuration Manager.</span></span>
    
   - <span data-ttu-id="bc423-p107">Abra o SQL Server Configuration Manager. Na árvore no lado esquerdo da tela, clique em **Serviços do SQL Server** e, em seguida, clique duas vezes no serviço SQL Server. </span><span class="sxs-lookup"><span data-stu-id="bc423-p107">Open SQL Server Configuration Manager. In the tree on the left side of the screen, click **SQL Server Services**, then double-click the SQL Server service.</span></span> 
    
   - <span data-ttu-id="bc423-p108">Na caixa **Propriedades**, selecione a guia **Alta Disponibilidade AlwaysOn**. Marque a caixa de seleção **Habilitar Grupos de Disponibilidade AlwaysOn**. Reinicie o serviço SQL Server quando solicitado.</span><span class="sxs-lookup"><span data-stu-id="bc423-p108">In the **Properties** box, select the **AlwaysOn High Availability** tab. Select the **Enable AlwaysOn Availability Groups** check box. Restart the SQL Server service when prompted.</span></span>
   
6. <span data-ttu-id="bc423-148">Use o construtor de topologias para criar o pool de front-end, conforme explicado em [criar e publicar nova topologia no Skype for Business Server](../../deploy/install/create-and-publish-new-topology.md).</span><span class="sxs-lookup"><span data-stu-id="bc423-148">Use Topology Builder to create the Front End pool, as explained in [Create and publish new topology in Skype for Business Server](../../deploy/install/create-and-publish-new-topology.md).</span></span> <span data-ttu-id="bc423-149">Ao fazer isso, especifique AG como o repositório SQL do pool.</span><span class="sxs-lookup"><span data-stu-id="bc423-149">When you do, specify the AG as the SQL store for the pool.</span></span>
    
7. <span data-ttu-id="bc423-150">Criar o grupo de disponibilidade.</span><span class="sxs-lookup"><span data-stu-id="bc423-150">Create the availability group.</span></span>
    
   - <span data-ttu-id="bc423-151">Abra o SQL Server Management Studio e conecte-se à instância do SQL Server.</span><span class="sxs-lookup"><span data-stu-id="bc423-151">Open SQL Server Management Studio, and connect to the SQL Server instance.</span></span>
    
   - <span data-ttu-id="bc423-152">No explorador de objetos, expanda a pasta **sempre na alta disponibilidade** .</span><span class="sxs-lookup"><span data-stu-id="bc423-152">In Object Explorer, expand the **Always On High Availability** folder.</span></span> <span data-ttu-id="bc423-153">Clique com o botão direito do mouse na pasta **Grupos de Disponibilidade** e clique em **Assistente para Novo Grupo de Disponibilidade**.</span><span class="sxs-lookup"><span data-stu-id="bc423-153">Right-click the **Availability Groups** folder and click **New Availability Group Wizard**.</span></span>
    
   - <span data-ttu-id="bc423-154">Se a página **Introdução** for exibida, clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="bc423-154">If the **Introduction** page appears, click **Next**.</span></span>
    
   - <span data-ttu-id="bc423-155">Na página **Especificar Nome do Grupo de Disponibilidade**, digite o nome do Grupo de disponibilidade e clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="bc423-155">In the **Specify Availability Group Name** page, type the name of the Availability group, and click **Next**.</span></span>
    
   - <span data-ttu-id="bc423-156">Na página Selecionar bancos de dados, selecione os bancos de dados que você deseja incluir no grupo de disponibilidade AlwaysOn.</span><span class="sxs-lookup"><span data-stu-id="bc423-156">In the Select Databases page, select the databases that you want to include in the AlwaysOn Availability Group.</span></span> <span data-ttu-id="bc423-157">Then click **Next**.</span><span class="sxs-lookup"><span data-stu-id="bc423-157">Then click **Next**.</span></span>
    
     <span data-ttu-id="bc423-158">Não inclua os bancos de dados de chat **ReportServer**, **ReportServerTempDB**ou persistent no grupo de disponibilidade AlwaysOn, pois eles não têm suporte nesse cenário.</span><span class="sxs-lookup"><span data-stu-id="bc423-158">Do not include the **ReportServer**, **ReportServerTempDB**, or Persistent Chat databases in the AlwaysOn Availability Group, as these are not supported in this scenario.</span></span> <span data-ttu-id="bc423-159">Você pode incluir todos os outros bancos de dados do Skype for Business Server no grupo de disponibilidade AlwaysOn.</span><span class="sxs-lookup"><span data-stu-id="bc423-159">You can include all other Skype for Business Server databases in the AlwaysOn Availability Group.</span></span>
    
   - <span data-ttu-id="bc423-160">Na página **Especificar Réplicas**, clique na guia **Réplicas**. Clique no botão **Adicionar Réplicas** e conecte-se às outras instâncias do SQL que você incluiu como nós do Clustering de Failover do Windows Server.</span><span class="sxs-lookup"><span data-stu-id="bc423-160">In the **Specify Replicas** page, click the **Replicas** tab. Then click the **Add Replicas** button, and connect to the other SQL instances that you joined as nodes of the Windows Server Failover Cluster.</span></span>
    
   - <span data-ttu-id="bc423-p113">Para cada instância, selecione as opções **Failover Automático** e **Confirmação Síncrona**. Não selecione a opção **Secundária Legível**.</span><span class="sxs-lookup"><span data-stu-id="bc423-p113">For each instance, select the **Automatic Failover** and **Synchronous Commit** options. Do not select the **Readable Secondary** option.</span></span>
    
   - <span data-ttu-id="bc423-163">Clique na guia **Pontos de Extremidade** e verifique se o **Número da Porta** está definido como 5022.</span><span class="sxs-lookup"><span data-stu-id="bc423-163">Click the **Endpoints** tab and verify that **Port Number** is set to 5022.</span></span>
    
   - <span data-ttu-id="bc423-p114">Clique na guia **Ouvinte** e selecione a opção **Criar um ouvinte de grupo de disponibilidade**. Nesta opção, digite um nome para o ouvinte e defina a **Porta** como 1433 (outras portas não são suportadas para esta opção).</span><span class="sxs-lookup"><span data-stu-id="bc423-p114">Click the **Listener** tab, and select the **Create an availability group listener** option. Under that option, type a name for the listener, and set the **Port** to 1433 (other ports are not supported for this option).</span></span>
    
   - <span data-ttu-id="bc423-166">Clique em **Adicionar** e, na caixa **Endereço IPv4**, forneça o endereço IP virtual de sua preferência e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="bc423-166">Click **Add**, and then in the **IPv4 Address** box, provide your preferred virtual IP address, and then click **OK**.</span></span>
    
   - <span data-ttu-id="bc423-p115">Na página **Selecionar Sincronização de Dados Inicial**, selecione Completo, especifique uma pasta que possa ser acessada pelas réplicas e para a qual a conta do serviço SQL Server usada por ambas as réplicas tenha permissões de Gravação. Clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="bc423-p115">In the **Select Initial Data Synchronization** page, select Full, and specify a folder that is accessible to the replicas, and that the SQL Server service account used by both replicas has Write permissions for. Then click **Next**.</span></span>
    
     <span data-ttu-id="bc423-p116">Este compartilhamento de arquivos será usado temporariamente quando você inicializar os bancos de dados. Se você usar bancos de dados grandes, recomendamos que você os inicie manualmente caso a largura de banda de sua rede não possa acomodar o tamanho dos bancos de dados de backup.</span><span class="sxs-lookup"><span data-stu-id="bc423-p116">This file share will be used temporarily when you initialize the databases. If you are dealing with large databases, we recommend that you manually initialize them in case your network bandwidth cannot accommodate the size of the database backups.</span></span>
    
   - <span data-ttu-id="bc423-171">Na página Validação, confira se as verificações de validação foram bem-sucedidas e, em seguida, clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="bc423-171">In the Validation page, verify that all validation checks are successful, then click **Next**.</span></span>
    
   - <span data-ttu-id="bc423-172">Na página **Resumo**, verifique todas as configurações e clique em Concluir.</span><span class="sxs-lookup"><span data-stu-id="bc423-172">In the **Summary** page, verify all settings and click Finish.</span></span>
      
8. <span data-ttu-id="bc423-173">Após a implantação do pool e da AG, execute algumas etapas finais para garantir que os logons do SQL estejam em cada uma das réplicas do grupo disponibilidade AlwaysOn.</span><span class="sxs-lookup"><span data-stu-id="bc423-173">After the pool and the AG are deployed, perform some final steps to make sure that the SQL logins are on each of the replicas in the AlwaysOn Availability Group.</span></span> 
    
   - <span data-ttu-id="bc423-174">Abra o construtor de topologias, selecione **baixar topologia de implantação existente**e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="bc423-174">Open Topology Builder, select **Download topology from existing deployment**, and click **OK**.</span></span>
    
   - <span data-ttu-id="bc423-175">Expanda o Skype for Business Server, expanda sua topologia e expanda **Repositórios do SQL Server**.</span><span class="sxs-lookup"><span data-stu-id="bc423-175">Expand Skype for Business Server, expand your topology, and expand **SQL Server Stores**.</span></span> <span data-ttu-id="bc423-176">Clique com o botão direito do mouse no repositório SQL do novo grupo de disponibilidade AlwaysOn e clique em **Editar propriedades**.</span><span class="sxs-lookup"><span data-stu-id="bc423-176">Right-click the SQL store of the new AlwaysOn Availability Group, and click **Edit Properties**.</span></span>
    
     - <span data-ttu-id="bc423-177">Na parte inferior da página, na caixa **FQDN do SQL Server** , altere o valor para o FQDN do ouvinte da AG.</span><span class="sxs-lookup"><span data-stu-id="bc423-177">At the bottom of the page, in the **SQL Server FQDN** box, change the value to the FQDN of the Listener of the AG.</span></span>
    
   - <span data-ttu-id="bc423-p118">Publique a topologia. No menu **Ação**, clique em **Topologia** e, em seguida, **Publicar**. Na página de confirmação, clique em **Avançar**. Aguarde alguns minutos para a nova topologia ser replicada.</span><span class="sxs-lookup"><span data-stu-id="bc423-p118">Publish the topology. From the **Action** menu click **Topology** and then **Publish**. Then in the confirmation page click **Next**. Then wait a few minutes for the new topology to replicate.</span></span>
    
   - <span data-ttu-id="bc423-182">Abra o SQL Server Management Studio e navegue até o AG.</span><span class="sxs-lookup"><span data-stu-id="bc423-182">Open SQL Server Management Studio, and navigate to the AG.</span></span> <span data-ttu-id="bc423-183">Faça failover para uma réplica secundária.</span><span class="sxs-lookup"><span data-stu-id="bc423-183">Fail it over to a secondary replica.</span></span>
    
   - <span data-ttu-id="bc423-184">Abra o Shell de gerenciamento do Skype for Business Server e digite o seguinte cmdlet para criar os logons do SQL nesta réplica:</span><span class="sxs-lookup"><span data-stu-id="bc423-184">Open Skype for Business Server Management Shell and type the following cmdlet to create the SQL logins on this replica:</span></span>
    
   ```
   Install-CsDatabase -Update
   ```

   - <span data-ttu-id="bc423-185">Repita as duas etapas anteriores (failover do grupo para uma réplica secundária e, em seguida `Install-CsDatabase -Update`, use) para cada réplica do grupo.</span><span class="sxs-lookup"><span data-stu-id="bc423-185">Repeat the previous two steps (fail over the group to a secondary replica, then use  `Install-CsDatabase -Update`) for each replica in the group.</span></span>
    
## <a name="deploy-an-always-on-availability-group-on-an-existing-pool-that-uses-database-mirroring"></a><span data-ttu-id="bc423-186">Implantar um grupo de disponibilidade AlwaysOn em um pool existente que usa o espelhamento de banco de dados</span><span class="sxs-lookup"><span data-stu-id="bc423-186">Deploy an Always On Availability Group on an existing pool that uses database mirroring</span></span>
<span data-ttu-id="bc423-187"><a name="BKMK_MirroredPool_CreateAlwaysOnGroup"> </a></span><span class="sxs-lookup"><span data-stu-id="bc423-187"></span></span>

> [!NOTE]
> <span data-ttu-id="bc423-188">Se o pool que você está atualizando para um AG hospeda o repositório central de gerenciamento para a sua organização, você deve primeiro mover o CMS para outro pool antes de atualizar este pool.</span><span class="sxs-lookup"><span data-stu-id="bc423-188">If the pool you are upgrading to an AG hosts the Central Management store for your organization, you must first move the CMS to another pool before you upgrade this pool.</span></span> <span data-ttu-id="bc423-189">Use o cmdlet Move-CsManagementServer para mover o pool.</span><span class="sxs-lookup"><span data-stu-id="bc423-189">Use the Move-CsManagementServer cmdlet to move the pool.</span></span> <span data-ttu-id="bc423-190">Se você não tiver outro pool em sua organização, poderá implantar um servidor Standard Edition temporariamente e mover o CMS para este servidor antes de atualizar o pool para a AG.</span><span class="sxs-lookup"><span data-stu-id="bc423-190">If you do not have another pool in your organization, you can deploy a Standard Edition server temporarily and move the CMS to this server before you upgrade your pool to the AG.</span></span> 
  
1. <span data-ttu-id="bc423-191">Falhe em todos os dados do espelho para o nó principal abrindo o Shell de gerenciamento do Skype for Business Server e digitando o cmdlet a seguir.</span><span class="sxs-lookup"><span data-stu-id="bc423-191">Fail over all data from the mirror to the principal node by opening Skype for Business Server Management Shell and typing the following cmdlet.</span></span>
    
   ```
   Invoke-CsDatabaseFailover -PoolFqdn <Pool FQDN> -DatabaseType <DatabaseType> -NewPrincipal "Primary"
   ```

    <span data-ttu-id="bc423-p121">Repita esse cmdlet para cada tipo de banco de dados no pool. Você pode utilizar o seguinte cmdlet para localizar todos os tipos de bancos de dados armazenados neste pool.</span><span class="sxs-lookup"><span data-stu-id="bc423-p121">Repeat this cmdlet for each database type in the pool. You can use the following cmdlet to find all the database types stored in this pool.</span></span>
     
   ```
   Get-CsPool -Identity <Pool FQDN>
   ```

2. <span data-ttu-id="bc423-194">Use o construtor de topologias para remover o espelhamento de banco de dados do pool.</span><span class="sxs-lookup"><span data-stu-id="bc423-194">Use Topology Builder to remove database mirroring from the pool.</span></span>
    
   - <span data-ttu-id="bc423-195">Abrir o construtor de topologias.</span><span class="sxs-lookup"><span data-stu-id="bc423-195">Open Topology Builder.</span></span> <span data-ttu-id="bc423-196">Em sua topologia, expanda **Pools de Front-Ends Enterprise Edition**, clique com o botão direito do mouse no nome do pool e clique em **Editar Propriedades**.</span><span class="sxs-lookup"><span data-stu-id="bc423-196">In your topology, expand **Enterprise Edition Front End Pools**, right-click the name of the pool, and click **Edit Properties**.</span></span>
    
   - <span data-ttu-id="bc423-197">Para cada tipo de repositório SQL no pool, desmarque a caixa de seleção **Habilitar Espelhamento do Repositório SQL**.</span><span class="sxs-lookup"><span data-stu-id="bc423-197">For each type of SQL store in the pool, clear the **Enable SQL Store Mirroring** check box.</span></span>
    
3. <span data-ttu-id="bc423-p123">Publique a topologia alterada. No menu **Ação**, clique em **Topologia** e, em seguida, em **Publicar**. Na página de confirmação, clique em **Avançar**</span><span class="sxs-lookup"><span data-stu-id="bc423-p123">Publish the changed topology. From the **Action** menu click **Topology** and then **Publish**. Then in the confirmation page click **Next**</span></span>
    
4. <span data-ttu-id="bc423-201">Usar o SQL Server Management Studio para quebrar o espelho.</span><span class="sxs-lookup"><span data-stu-id="bc423-201">Use SQL Server Management Studio to break the mirror.</span></span>
    
   - <span data-ttu-id="bc423-p124">Abra o SQL Server Management Studio, navegue até seus bancos de dados, clique com o botão direito do mouse em **Tarefas** e clique em **Espelho**. Clique em **Remover Espelhamento** e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="bc423-p124">Open SQL Server Management Studio, navigate to your databases, right-click **Tasks** and click **Mirror**. Then click **Remove Mirroring** and click **OK**.</span></span>
    
   - <span data-ttu-id="bc423-204">Repita esse procedimento para todos os bancos de dados no pool que serão convertidos em uma AG.</span><span class="sxs-lookup"><span data-stu-id="bc423-204">Repeat this for all databases in the pool which will be converted to an AG.</span></span>
    
5. <span data-ttu-id="bc423-205">Configure o recurso de cluster de failover em todos os servidores de banco de dados que farão parte da AG.</span><span class="sxs-lookup"><span data-stu-id="bc423-205">Set up the Failover Clustering feature on all the database servers which will be part of the AG.</span></span> <span data-ttu-id="bc423-206">Em cada servidor, faça o seguinte:</span><span class="sxs-lookup"><span data-stu-id="bc423-206">On each server, do the following</span></span>
    
   - <span data-ttu-id="bc423-207">Abra o Server Manager e clique em **Adicionar funções e recurso**.</span><span class="sxs-lookup"><span data-stu-id="bc423-207">Open Server Manager and click **Add roles and features**.</span></span>
    
   - <span data-ttu-id="bc423-p126">Clique em **Avançar** até chegar à caixa **Selecionar recursos**. Aqui, marque a caixa de seleção **Clustering de Failover**.</span><span class="sxs-lookup"><span data-stu-id="bc423-p126">Click **Next** until you reach the **Select features** box. Here, select the **Failover Clustering** check box.</span></span>
    
   - <span data-ttu-id="bc423-210">Na caixa **Adicionar recursos necessários para o Clustering de Failover?**, clique em **Adicionar Recursos**.</span><span class="sxs-lookup"><span data-stu-id="bc423-210">In the **Add features that are required for Failover Clustering?** box, click **Add Features**.</span></span>
    
   - <span data-ttu-id="bc423-211">Clique em **Instalar**.</span><span class="sxs-lookup"><span data-stu-id="bc423-211">Click **Install**.</span></span>
    
6. <span data-ttu-id="bc423-212">Validar a configuração de cluster.</span><span class="sxs-lookup"><span data-stu-id="bc423-212">Validate the cluster configuration.</span></span>
    
   - <span data-ttu-id="bc423-213">No Server Manager, clique no menu **Ferramentas** e, em seguida, clique em **Gerenciador de Cluster de Failover**.</span><span class="sxs-lookup"><span data-stu-id="bc423-213">In Server Manager, click the **Tools** menu and then click **Failover Cluster Manager**.</span></span>
    
   - <span data-ttu-id="bc423-214">Em **Ações** no lado direito da tela, clique em **Validar Configuração**.</span><span class="sxs-lookup"><span data-stu-id="bc423-214">Under **Actions** on the right side of the screen, click **Validate Configuration**.</span></span>
    
   - <span data-ttu-id="bc423-215">Na página **Antes de começar**, clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="bc423-215">On the **Before You Begin** page, click **Next**.</span></span>
    
   - <span data-ttu-id="bc423-216">Selecione os servidores a serem adicionados ao cluster e clique em **Executar todos os testes**.</span><span class="sxs-lookup"><span data-stu-id="bc423-216">Select the servers to add to the cluster, and then click **Run all tests**.</span></span>
    
   - <span data-ttu-id="bc423-p127">Na caixa **Resumo**, verifique os erros relatados pelo assistente. Clique em **Concluir** para concluir a validação.</span><span class="sxs-lookup"><span data-stu-id="bc423-p127">In the **Summary** box, check any errors that the wizard reports. Then click **Finish** to complete the validation.</span></span>
    
     <span data-ttu-id="bc423-p128">O assistente provavelmente mostrará diversos avisos, especialmente se você não estiver usando armazenamento compartilhado. Não é necessário usar o armazenamento compartilhado. No entanto, se você vir alguma mensagem de **Erro**, deverá corrigir esses problemas antes de continuar.</span><span class="sxs-lookup"><span data-stu-id="bc423-p128">The wizard will probably report several warnings, especially if you are not using shared storage. You are not required to use shared storage. However, if you see any **Error** messages, you must fix those issues before continuing.</span></span>
    
7. <span data-ttu-id="bc423-222">Crie o cluster de failover do Windows Server.</span><span class="sxs-lookup"><span data-stu-id="bc423-222">Create the Windows Server Failover Cluster.</span></span>
    
   - <span data-ttu-id="bc423-223">No assistente de **Gerenciamento de Cluster de Failover**, clique com o botão direito do mouse em **Gerenciamento de Cluster de Failover** e, em seguida, clique em **Criar Cluster**.</span><span class="sxs-lookup"><span data-stu-id="bc423-223">In the **Failover Cluster Management** wizard, right-click **Failover Cluster Management**, then click **Create Cluster**.</span></span>
    
   - <span data-ttu-id="bc423-224">Na página **Antes de começar**, clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="bc423-224">On the **Before You Begin** page, click **Next**.</span></span>
    
   - <span data-ttu-id="bc423-p129">Adicione o nome e o endereço IP do cluster. Quando as definições forem validadas, clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="bc423-p129">Add the cluster name and IP address. When the settings are validated, click **Next**.</span></span>
    
   - <span data-ttu-id="bc423-227">Na página Confirmação, clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="bc423-227">On the Confirmation page, click **Next**.</span></span>
    
   - <span data-ttu-id="bc423-228">Depois que o cluster for criado, clique em **Concluir**.</span><span class="sxs-lookup"><span data-stu-id="bc423-228">After the cluster is created, click **Finish**.</span></span>
    
8. <span data-ttu-id="bc423-p130">Recomendamos que você defina as configurações de quorum do cluster para usar uma testemunha de compartilhamento de arquivos. Para isso, siga estas instruções:</span><span class="sxs-lookup"><span data-stu-id="bc423-p130">We recommend that you configure the cluster quorum settings to use a file share witness. To do so, use these steps:</span></span>
    
   - <span data-ttu-id="bc423-231">Clique com o botão direito do mouse no nome do cluster, em **Mais Ações** e, em seguida, em **Configurar Quorum do Cluster**.</span><span class="sxs-lookup"><span data-stu-id="bc423-231">Right-click the cluster name, click **More Actions**, and click **Configure Cluster Quorum Settings**.</span></span>
    
   - <span data-ttu-id="bc423-232">Na página **Selecionar Opção de Configuração de Quorum**, clique em **Selecione a testemunha de Quorum**.</span><span class="sxs-lookup"><span data-stu-id="bc423-232">In the **Select Quorum Configuration Option** page, click **Select the quorum witness**.</span></span>
    
   - <span data-ttu-id="bc423-233">Na página **Selecione a testemunha de Quorum**, clique em **Configurar uma testemunha de compartilhamento de arquivos**.</span><span class="sxs-lookup"><span data-stu-id="bc423-233">In the **Select Quorum Witness** page, click **Configure a file share witness**.</span></span>
    
   - <span data-ttu-id="bc423-234">Na página **Configurar Testemunha de Compartilhamento de Arquivo**, digite o caminho do compartilhamento de arquivos que você deseja usar e clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="bc423-234">In the **Configure File Share Witness** page, type the path of the file share you want to use, and then click **Next**.</span></span>
    
   - <span data-ttu-id="bc423-235">Na página **Confirmação**, clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="bc423-235">On the **Confirmation** page, click **Next**.</span></span>
    
9. <span data-ttu-id="bc423-236">Em cada servidor do cluster, habilite o recurso AG no Gerenciador de configuração do SQL Server.</span><span class="sxs-lookup"><span data-stu-id="bc423-236">On each server in the cluster, enable the AG feature in SQL Server Configuration Manager.</span></span>
    
   - <span data-ttu-id="bc423-p131">Abra o SQL Server Configuration Manager. Na árvore no lado esquerdo da tela, clique em **Serviços do SQL Server** e, em seguida, clique duas vezes no serviço SQL Server. </span><span class="sxs-lookup"><span data-stu-id="bc423-p131">Open SQL Server Configuration Manager. In the tree on the left side of the screen, click **SQL Server Services**, then double-click the SQL Server service.</span></span> 
    
   - <span data-ttu-id="bc423-p132">Na caixa **Propriedades**, selecione a guia **Alta Disponibilidade AlwaysOn**. Marque a caixa de seleção **Habilitar Grupos de Disponibilidade AlwaysOn**. Reinicie o serviço SQL Server quando solicitado.</span><span class="sxs-lookup"><span data-stu-id="bc423-p132">In the **Properties** box, select the **AlwaysOn High Availability** tab. Select the **Enable AlwaysOn Availability Groups** check box. Restart the SQL Server service when prompted.</span></span>
    
10. <span data-ttu-id="bc423-241">Criar o grupo de disponibilidade.</span><span class="sxs-lookup"><span data-stu-id="bc423-241">Create the availability group.</span></span>
    
    - <span data-ttu-id="bc423-242">Abra o SQL Server Management Studio e conecte-se à instância do SQL Server.</span><span class="sxs-lookup"><span data-stu-id="bc423-242">Open SQL Server Management Studio, and connect to the SQL Server instance.</span></span>
    
    - <span data-ttu-id="bc423-243">No explorador de objetos, expanda a pasta **sempre na alta disponibilidade** .</span><span class="sxs-lookup"><span data-stu-id="bc423-243">In Object Explorer, expand the **Always On High Availability** folder.</span></span> <span data-ttu-id="bc423-244">Clique com o botão direito do mouse na pasta **Grupos de Disponibilidade** e clique em **Assistente para Novo Grupo de Disponibilidade**.</span><span class="sxs-lookup"><span data-stu-id="bc423-244">Right-click the **Availability Groups** folder and click **New Availability Group Wizard**.</span></span>
    
    - <span data-ttu-id="bc423-245">Se a página **Introdução** for exibida, clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="bc423-245">If the **Introduction** page appears, click **Next**.</span></span>
    
    - <span data-ttu-id="bc423-246">Na página **Especificar Nome do Grupo de Disponibilidade**, digite o nome do Grupo de disponibilidade e clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="bc423-246">In the **Specify Availability Group Name** page, type the name of the Availability group, and click **Next**.</span></span>
    
    - <span data-ttu-id="bc423-247">Na página Selecionar bancos de dados, selecione os bancos de dados que você deseja incluir no grupo de disponibilidade AlwaysOn.</span><span class="sxs-lookup"><span data-stu-id="bc423-247">In the Select Databases page, select the databases that you want to include in the AlwaysOn Availability Group.</span></span> <span data-ttu-id="bc423-248">Then click **Next**.</span><span class="sxs-lookup"><span data-stu-id="bc423-248">Then click **Next**.</span></span>
    
    <span data-ttu-id="bc423-249">Não inclua os bancos de dados de chat **ReportServer**, **ReportServerTempDB**ou persistent no grupo de disponibilidade AlwaysOn, pois eles não têm suporte nesse cenário.</span><span class="sxs-lookup"><span data-stu-id="bc423-249">Do not include the **ReportServer**, **ReportServerTempDB**, or Persistent Chat databases in the AlwaysOn Availability Group, as these are not supported in this scenario.</span></span> <span data-ttu-id="bc423-250">Você pode incluir todos os outros bancos de dados do Skype for Business Server no grupo de disponibilidade AlwaysOn.</span><span class="sxs-lookup"><span data-stu-id="bc423-250">You can include all other Skype for Business Server databases in the AlwaysOn Availability Group.</span></span>
    
    - <span data-ttu-id="bc423-251">Na página **Especificar Réplicas**, clique na guia **Réplicas**. Clique no botão **Adicionar Réplicas** e conecte-se às outras instâncias do SQL que você incluiu como nós do Clustering de Failover do Windows Server.</span><span class="sxs-lookup"><span data-stu-id="bc423-251">In the **Specify Replicas** page, click the **Replicas** tab. Then click the **Add Replicas** button, and connect to the other SQL instances that you joined as nodes of the Windows Server Failover Cluster.</span></span>
    
    - <span data-ttu-id="bc423-p136">Para cada instância, selecione as opções **Failover Automático** e **Confirmação Síncrona**. Não selecione a opção **Secundária Legível**.</span><span class="sxs-lookup"><span data-stu-id="bc423-p136">For each instance, select the **Automatic Failover** and **Synchronous Commit** options. Do not select the **Readable Secondary** option.</span></span>
    
    - <span data-ttu-id="bc423-254">Clique na guia **Pontos de Extremidade** e verifique se o **Número da Porta** está definido como 5022.</span><span class="sxs-lookup"><span data-stu-id="bc423-254">Click the **Endpoints** tab and verify that **Port Number** is set to 5022.</span></span>
    
      - <span data-ttu-id="bc423-p137">Clique na guia **Ouvinte** e selecione a opção **Criar um ouvinte de grupo de disponibilidade**. Nesta opção, digite um nome para o ouvinte e defina a **Porta** como 1433 (outras portas não são suportadas para esta opção).</span><span class="sxs-lookup"><span data-stu-id="bc423-p137">Click the **Listener** tab, and select the **Create an availability group listener** option. Under that option, type a name for the listener, and set the **Port** to 1433 (other ports are not supported for this option).</span></span>
    
    - <span data-ttu-id="bc423-257">Clique em **Adicionar** e, na caixa **Endereço IPv4**, forneça o endereço IP virtual de sua preferência e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="bc423-257">Click **Add**, and then in the **IPv4 Address** box, provide your preferred virtual IP address, and then click **OK**.</span></span>
    
    - <span data-ttu-id="bc423-p138">Na página **Selecionar Sincronização de Dados Inicial**, selecione Completo, especifique uma pasta que possa ser acessada pelas réplicas e para a qual a conta do serviço SQL Server usada por ambas as réplicas tenha permissões de Gravação. Clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="bc423-p138">In the **Select Initial Data Synchronization** page, select Full, and specify a folder that is accessible to the replicas, and that the SQL Server service account used by both replicas has Write permissions for. Then click **Next**.</span></span>
    
    <span data-ttu-id="bc423-p139">Este compartilhamento de arquivos será usado temporariamente quando você inicializar os bancos de dados. Se você usar bancos de dados grandes, recomendamos que você os inicie manualmente caso a largura de banda de sua rede não possa acomodar o tamanho dos bancos de dados de backup.</span><span class="sxs-lookup"><span data-stu-id="bc423-p139">This file share will be used temporarily when you initialize the databases. If you are dealing with large databases, we recommend that you manually initialize them in case your network bandwidth cannot accommodate the size of the database backups.</span></span>
    
    - <span data-ttu-id="bc423-262">Na página Validação, confira se as verificações de validação foram bem-sucedidas e, em seguida, clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="bc423-262">In the Validation page, verify that all validation checks are successful, then click **Next**.</span></span>
    
    - <span data-ttu-id="bc423-263">Na página **Resumo**, verifique todas as configurações e clique em Concluir.</span><span class="sxs-lookup"><span data-stu-id="bc423-263">In the **Summary** page, verify all settings and click Finish.</span></span>
    
11. <span data-ttu-id="bc423-264">Crie uma nova loja especificando o ouvinte AG e especificando a entidade de segurança do espelho antigo como o nó primário da AG.</span><span class="sxs-lookup"><span data-stu-id="bc423-264">Create a new store specifying the AG listener, and specifying the principal of the old mirror as the primary node of the AG.</span></span>
    
    - <span data-ttu-id="bc423-265">Abrir o construtor de topologias.</span><span class="sxs-lookup"><span data-stu-id="bc423-265">Open Topology Builder.</span></span> <span data-ttu-id="bc423-266">Em sua topologia, expanda **Componentes Compartilhados**, clique com o botão direito do mouse em **Repositórios do SQL Server** e clique em **Novo Repositório do SQL Server**.</span><span class="sxs-lookup"><span data-stu-id="bc423-266">In your topology, expand **Shared Components**, right-click **SQL Server Stores**, and click **New SQL Server Store**.</span></span>
    
    - <span data-ttu-id="bc423-267">Na página **Definir Novo Repositório SQL**, primeiro marque a caixa de seleção **Configurações de Alta Disponibilidade** e, em seguida, certifique-se de que a opção Grupos de Disponibilidade AlwaysOn do SQL aparece na caixa suspensa.</span><span class="sxs-lookup"><span data-stu-id="bc423-267">In the **Define New SQL Store** page, first select the **High Availability Settings** check box, and then make sure that SQL AlwaysOn Availability Groups appears in the drop-down box.</span></span>
    
    - <span data-ttu-id="bc423-268">Na caixa **FQDN do Ouvinte de Disponibilidade do SQL Server**, digite o FQDN do ouvinte que criou quando criou o grupo de disponibilidade.</span><span class="sxs-lookup"><span data-stu-id="bc423-268">In the **SQL Server Availability Listener FQDN** box, type the FQDN of the listener you created when you created the availability group.</span></span>
    
    - <span data-ttu-id="bc423-269">Na caixa **FQDN do SQL Server** , digite o FQDN do nó primário da AG e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="bc423-269">In the **SQL Server FQDN** box, type the FQDN of the primary node of the AG, and then click **OK**.</span></span> <span data-ttu-id="bc423-270">Ele deve ser a entidade de segurança do espelho antigo para esse repositório.</span><span class="sxs-lookup"><span data-stu-id="bc423-270">This should be the principal of the old mirror for this store.</span></span>
    
12. <span data-ttu-id="bc423-271">Associe o novo AG ao pool de front-end.</span><span class="sxs-lookup"><span data-stu-id="bc423-271">Associate the new AG with the Front End pool.</span></span>
    
    - <span data-ttu-id="bc423-272">No construtor de topologias, clique com o botão direito do mouse no pool para associá-lo à AG e clique em **Editar propriedades**.</span><span class="sxs-lookup"><span data-stu-id="bc423-272">In Topology Builder, right-click the pool to associate with the AG, and click **Edit Properties**.</span></span>
    
    - <span data-ttu-id="bc423-273">Em **associações**, na caixa da **loja do SQL Server** , selecione a AG.</span><span class="sxs-lookup"><span data-stu-id="bc423-273">Under **Associations**, in the **SQL Server Store** box, select the AG.</span></span> <span data-ttu-id="bc423-274">Selecione o mesmo grupo para qualquer outro banco de dados no pool que você deseja mover para a AG.</span><span class="sxs-lookup"><span data-stu-id="bc423-274">Select the same group for any other databases in the pool which you want to move to the AG.</span></span>
    
    - <span data-ttu-id="bc423-275">Quando tiver certeza de que todos os bancos de dados necessários estão definidos para a AG, clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="bc423-275">When you're sure that all needed databases are set to the AG, click **OK**.</span></span>
    
13. <span data-ttu-id="bc423-276">Publique a topologia.</span><span class="sxs-lookup"><span data-stu-id="bc423-276">Publish the topology.</span></span> <span data-ttu-id="bc423-277">No menu **Ação**, clique em **Topologia** e, em seguida, **Publicar**.</span><span class="sxs-lookup"><span data-stu-id="bc423-277">From the **Action** menu click **Topology** and then **Publish**.</span></span> <span data-ttu-id="bc423-278">Na página de confirmação, clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="bc423-278">Then in the confirmation page click **Next**.</span></span>
    
14. <span data-ttu-id="bc423-279">Execute algumas etapas finais para garantir que os logons do SQL estejam em cada uma das réplicas do grupo de disponibilidade AlwaysOn.</span><span class="sxs-lookup"><span data-stu-id="bc423-279">Perform some final steps to make sure that the SQL logins are on each of the replicas in the AlwaysOn Availability Group.</span></span>
    
    - <span data-ttu-id="bc423-280">Abra o construtor de topologias, selecione **baixar topologia de implantação existente**e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="bc423-280">Open Topology Builder, select **Download topology from existing deployment**, and click **OK**.</span></span>
    
    - <span data-ttu-id="bc423-281">Expanda o Skype for Business Server, expanda sua topologia e expanda **Repositórios do SQL Server**.</span><span class="sxs-lookup"><span data-stu-id="bc423-281">Expand Skype for Business Server, expand your topology, and expand **SQL Server Stores**.</span></span> <span data-ttu-id="bc423-282">Clique com o botão direito do mouse na loja do SQL da nova AG e clique em **Editar propriedades**.</span><span class="sxs-lookup"><span data-stu-id="bc423-282">Right-click the SQL store of the new AG, and click **Edit Properties**.</span></span>
    
    - <span data-ttu-id="bc423-283">Na parte inferior da página, na caixa **FQDN do SQL Server** , altere o valor para o FQDN do ouvinte da AG.</span><span class="sxs-lookup"><span data-stu-id="bc423-283">At the bottom of the page, in the **SQL Server FQDN** box, change the value to the FQDN of the Listener of the AG.</span></span>
    
    - <span data-ttu-id="bc423-p145">Publique a topologia. No menu **Ação**, clique em **Topologia** e, em seguida, **Publicar**. Na página de confirmação, clique em **Avançar**. Aguarde alguns minutos para a nova topologia ser replicada.</span><span class="sxs-lookup"><span data-stu-id="bc423-p145">Publish the topology. From the **Action** menu click **Topology** and then **Publish**. Then in the confirmation page click **Next**. Then wait a few minutes for the new topology to replicate.</span></span>
    
    - <span data-ttu-id="bc423-288">Abra o SQL Server Management Studio e navegue até o AG.</span><span class="sxs-lookup"><span data-stu-id="bc423-288">Open SQL Server Management Studio, and navigate to the AG.</span></span> <span data-ttu-id="bc423-289">Faça failover para uma réplica secundária.</span><span class="sxs-lookup"><span data-stu-id="bc423-289">Fail it over to a secondary replica.</span></span>
    
    - <span data-ttu-id="bc423-290">Abra o Shell de gerenciamento do Skype for Business Server e digite o seguinte cmdlet para criar os logons do SQL nesta réplica:</span><span class="sxs-lookup"><span data-stu-id="bc423-290">Open Skype for Business Server Management Shell and type the following cmdlet to create the SQL logins on this replica:</span></span>
    
    ```
    Install-CsDatabase -Update
    ```

    - <span data-ttu-id="bc423-291">Repita as duas etapas anteriores (failover do grupo para uma réplica secundária e, em seguida `Install-CsDatabase -Update`, use) para cada réplica do grupo.</span><span class="sxs-lookup"><span data-stu-id="bc423-291">Repeat the previous two steps (fail over the group to a secondary replica, then use  `Install-CsDatabase -Update`) for each replica in the group.</span></span>
    
## <a name="deploy-an-always-on-availability-group-on-an-existing-pool-that-does-not-use-database-mirroring"></a><span data-ttu-id="bc423-292">Implantar um grupo de disponibilidade AlwaysOn em um pool existente que não usa o espelhamento de banco de dados</span><span class="sxs-lookup"><span data-stu-id="bc423-292">Deploy an Always On Availability Group on an existing pool that does not use database mirroring</span></span>
<span data-ttu-id="bc423-293"><a name="BKMK_NoHAPool_CreateAlwaysOnGroup"> </a></span><span class="sxs-lookup"><span data-stu-id="bc423-293"></span></span>

> [!NOTE]
> <span data-ttu-id="bc423-294">Se o pool que você está atualizando para um AG hospeda o repositório central de gerenciamento para a sua organização, você deve primeiro mover o CMS para outro pool antes de atualizar este pool.</span><span class="sxs-lookup"><span data-stu-id="bc423-294">If the pool you are upgrading to an AG hosts the Central Management store for your organization, you must first move the CMS to another pool before you upgrade this pool.</span></span> <span data-ttu-id="bc423-295">Use o cmdlet Move-CsManagementServer para mover o pool.</span><span class="sxs-lookup"><span data-stu-id="bc423-295">Use the Move-CsManagementServer cmdlet to move the pool.</span></span> <span data-ttu-id="bc423-296">Se você não tiver outro pool em sua organização, poderá implantar um servidor Standard Edition temporariamente e mover o CMS para este servidor antes de atualizar o pool para a AG.</span><span class="sxs-lookup"><span data-stu-id="bc423-296">If you do not have another pool in your organization, you can deploy a Standard Edition server temporarily and move the CMS to this server before you upgrade your pool to the AG.</span></span> 
  
1. <span data-ttu-id="bc423-297">Configure o recurso de cluster de failover em todos os servidores de banco de dados que farão parte da AG.</span><span class="sxs-lookup"><span data-stu-id="bc423-297">Set up the Failover Clustering feature on all the database servers which will be part of the AG.</span></span> <span data-ttu-id="bc423-298">Em cada servidor, faça o seguinte:</span><span class="sxs-lookup"><span data-stu-id="bc423-298">On each server, do the following</span></span>
    
   - <span data-ttu-id="bc423-299">Abra o Server Manager e clique em **Adicionar funções e recurso**.</span><span class="sxs-lookup"><span data-stu-id="bc423-299">Open Server Manager and click **Add roles and features**.</span></span>
    
   - <span data-ttu-id="bc423-p149">Clique em **Avançar** até chegar à caixa **Selecionar recursos**. Aqui, marque a caixa de seleção **Clustering de Failover**.</span><span class="sxs-lookup"><span data-stu-id="bc423-p149">Click **Next** until you reach the **Select features** box. Here, select the **Failover Clustering** check box.</span></span>
    
   - <span data-ttu-id="bc423-302">Na caixa **Adicionar recursos necessários para o Clustering de Failover?**, clique em **Adicionar Recursos**.</span><span class="sxs-lookup"><span data-stu-id="bc423-302">In the **Add features that are required for Failover Clustering?** box, click **Add Features**.</span></span>
    
   - <span data-ttu-id="bc423-303">Clique em **Instalar**.</span><span class="sxs-lookup"><span data-stu-id="bc423-303">Click **Install**.</span></span>
    
2. <span data-ttu-id="bc423-304">Validar a configuração de cluster.</span><span class="sxs-lookup"><span data-stu-id="bc423-304">Validate the cluster configuration.</span></span>
    
   - <span data-ttu-id="bc423-305">No Server Manager, clique no menu **Ferramentas** e, em seguida, clique em **Gerenciador de Cluster de Failover**.</span><span class="sxs-lookup"><span data-stu-id="bc423-305">In Server Manager, click the **Tools** menu and then click **Failover Cluster Manager**.</span></span>
    
   - <span data-ttu-id="bc423-306">Em **Ações** no lado direito da tela, clique em **Validar Configuração**.</span><span class="sxs-lookup"><span data-stu-id="bc423-306">Under **Actions** on the right side of the screen, click **Validate Configuration**.</span></span>
    
   - <span data-ttu-id="bc423-307">Na página **Antes de começar**, clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="bc423-307">On the **Before You Begin** page, click **Next**.</span></span>
    
   - <span data-ttu-id="bc423-308">Selecione os servidores a serem adicionados ao cluster e clique em **Executar todos os testes**.</span><span class="sxs-lookup"><span data-stu-id="bc423-308">Select the servers to add to the cluster, and then click **Run all tests**.</span></span>
    
   - <span data-ttu-id="bc423-p150">Na caixa **Resumo**, verifique os erros relatados pelo assistente. Clique em **Concluir** para concluir a validação.</span><span class="sxs-lookup"><span data-stu-id="bc423-p150">In the **Summary** box, check any errors that the wizard reports. Then click **Finish** to complete the validation.</span></span>
    
     <span data-ttu-id="bc423-p151">O assistente provavelmente mostrará diversos avisos, especialmente se você não estiver usando armazenamento compartilhado. Não é necessário usar o armazenamento compartilhado. No entanto, se você vir alguma mensagem de **Erro**, deverá corrigir esses problemas antes de continuar.</span><span class="sxs-lookup"><span data-stu-id="bc423-p151">The wizard will probably report several warnings, especially if you are not using shared storage. You are not required to use shared storage. However, if you see any **Error** messages, you must fix those issues before continuing.</span></span>
    
3. <span data-ttu-id="bc423-314">Crie o WSFC (cluster de failover do Windows Server).</span><span class="sxs-lookup"><span data-stu-id="bc423-314">Create the Windows Server Failover Cluster (WSFC).</span></span>
    
   - <span data-ttu-id="bc423-315">No assistente de **Gerenciamento de Cluster de Failover**, clique com o botão direito do mouse em **Gerenciamento de Cluster de Failover** e, em seguida, clique em **Criar Cluster**.</span><span class="sxs-lookup"><span data-stu-id="bc423-315">In the **Failover Cluster Management** wizard, right-click **Failover Cluster Management**, then click **Create Cluster**.</span></span>
    
   - <span data-ttu-id="bc423-316">Na página **Antes de começar**, clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="bc423-316">On the **Before You Begin** page, click **Next**.</span></span>
    
   - <span data-ttu-id="bc423-p152">Adicione o nome e o endereço IP do cluster. Quando as definições forem validadas, clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="bc423-p152">Add the cluster name and IP address. When the settings are validated, click **Next**.</span></span>
    
   - <span data-ttu-id="bc423-319">Na página Confirmação, clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="bc423-319">On the Confirmation page, click **Next**.</span></span>
    
   - <span data-ttu-id="bc423-320">Depois que o cluster for criado, clique em **Concluir**.</span><span class="sxs-lookup"><span data-stu-id="bc423-320">After the cluster is created, click **Finish**.</span></span>
    
4. <span data-ttu-id="bc423-p153">Recomendamos que você defina as configurações de quorum do cluster para usar uma testemunha de compartilhamento de arquivos. Para isso, siga estas instruções:</span><span class="sxs-lookup"><span data-stu-id="bc423-p153">We recommend that you configure the cluster quorum settings to use a file share witness. To do so, use these steps:</span></span>
    
   - <span data-ttu-id="bc423-323">Clique com o botão direito do mouse no nome do cluster, em **Mais Ações** e, em seguida, em **Configurar Quorum do Cluster**.</span><span class="sxs-lookup"><span data-stu-id="bc423-323">Right-click the cluster name, click **More Actions**, and click **Configure Cluster Quorum Settings**.</span></span>
    
   - <span data-ttu-id="bc423-324">Na página **Selecionar Opção de Configuração de Quorum**, clique em **Selecione a testemunha de Quorum**.</span><span class="sxs-lookup"><span data-stu-id="bc423-324">In the **Select Quorum Configuration Option** page, click **Select the quorum witness**.</span></span>
    
   - <span data-ttu-id="bc423-325">Na página **Selecione a testemunha de Quorum**, clique em **Configurar uma testemunha de compartilhamento de arquivos**.</span><span class="sxs-lookup"><span data-stu-id="bc423-325">In the **Select Quorum Witness** page, click **Configure a file share witness**.</span></span>
    
   - <span data-ttu-id="bc423-326">Na página **Configurar Testemunha de Compartilhamento de Arquivo**, digite o caminho do compartilhamento de arquivos que você deseja usar e clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="bc423-326">In the **Configure File Share Witness** page, type the path of the file share you want to use, and then click **Next**.</span></span>
    
   - <span data-ttu-id="bc423-327">Na página **Confirmação**, clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="bc423-327">On the **Confirmation** page, click **Next**.</span></span>
    
5. <span data-ttu-id="bc423-328">Em cada servidor do cluster, habilite a AG no Gerenciador de configuração do SQL Server.</span><span class="sxs-lookup"><span data-stu-id="bc423-328">On each server in the cluster, enable AG in SQL Server Configuration Manager.</span></span>
    
   - <span data-ttu-id="bc423-p154">Abra o SQL Server Configuration Manager. Na árvore no lado esquerdo da tela, clique em **Serviços do SQL Server** e, em seguida, clique duas vezes no serviço SQL Server. </span><span class="sxs-lookup"><span data-stu-id="bc423-p154">Open SQL Server Configuration Manager. In the tree on the left side of the screen, click **SQL Server Services**, then double-click the SQL Server service.</span></span> 
    
   - <span data-ttu-id="bc423-p155">Na caixa **Propriedades**, selecione a guia **Alta Disponibilidade AlwaysOn**. Marque a caixa de seleção **Habilitar Grupos de Disponibilidade AlwaysOn**. Reinicie o serviço SQL Server quando solicitado.</span><span class="sxs-lookup"><span data-stu-id="bc423-p155">In the **Properties** box, select the **AlwaysOn High Availability** tab. Select the **Enable AlwaysOn Availability Groups** check box. Restart the SQL Server service when prompted.</span></span>
    
6. <span data-ttu-id="bc423-333">Criar o grupo de disponibilidade.</span><span class="sxs-lookup"><span data-stu-id="bc423-333">Create the availability group.</span></span>
    
   - <span data-ttu-id="bc423-334">Abra o SQL Server Management Studio e conecte-se à instância do SQL Server.</span><span class="sxs-lookup"><span data-stu-id="bc423-334">Open SQL Server Management Studio, and connect to the SQL Server instance.</span></span>
    
   - <span data-ttu-id="bc423-335">No explorador de objetos, expanda a pasta **sempre na alta disponibilidade** .</span><span class="sxs-lookup"><span data-stu-id="bc423-335">In Object Explorer, expand the **Always On High Availability** folder.</span></span> <span data-ttu-id="bc423-336">Clique com o botão direito do mouse na pasta **Grupos de Disponibilidade** e clique em **Assistente para Novo Grupo de Disponibilidade**.</span><span class="sxs-lookup"><span data-stu-id="bc423-336">Right-click the **Availability Groups** folder and click **New Availability Group Wizard**.</span></span>
    
   - <span data-ttu-id="bc423-337">Se a página **Introdução** for exibida, clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="bc423-337">If the **Introduction** page appears, click **Next**.</span></span>
    
   - <span data-ttu-id="bc423-338">Na página **Especificar Nome do Grupo de Disponibilidade**, digite o nome do Grupo de disponibilidade e clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="bc423-338">In the **Specify Availability Group Name** page, type the name of the Availability group, and click **Next**.</span></span>
    
   - <span data-ttu-id="bc423-339">Na página Selecionar bancos de dados, selecione os bancos de dados que você deseja incluir na AG.</span><span class="sxs-lookup"><span data-stu-id="bc423-339">In the Select Databases page, select the databases that you want to include in the AG.</span></span> <span data-ttu-id="bc423-340">Then click **Next**.</span><span class="sxs-lookup"><span data-stu-id="bc423-340">Then click **Next**.</span></span>
    
     <span data-ttu-id="bc423-341">Não inclua os bancos de dados de chat **ReportServer**, **ReportServerTempDB**ou persistent na AG, pois eles não têm suporte nesse cenário.</span><span class="sxs-lookup"><span data-stu-id="bc423-341">Do not include the **ReportServer**, **ReportServerTempDB**, or Persistent Chat databases in the AG, as these are not supported in this scenario.</span></span> <span data-ttu-id="bc423-342">Você pode incluir todos os outros bancos de dados do Skype for Business Server na AG.</span><span class="sxs-lookup"><span data-stu-id="bc423-342">You can include all other Skype for Business Server databases in the AG.</span></span>
    
   - <span data-ttu-id="bc423-343">Na página **especificar réplicas** , clique na guia **réplicas** . Em seguida, clique no botão **Adicionar réplicas** e conecte-se às outras instâncias do SQL que você ingressou como nós do WSFC.</span><span class="sxs-lookup"><span data-stu-id="bc423-343">In the **Specify Replicas** page, click the **Replicas** tab. Then click the **Add Replicas** button, and connect to the other SQL instances that you joined as nodes of the WSFC.</span></span>
    
   - <span data-ttu-id="bc423-p159">Para cada instância, selecione as opções **Failover Automático** e **Confirmação Síncrona**. Não selecione a opção **Secundária Legível**.</span><span class="sxs-lookup"><span data-stu-id="bc423-p159">For each instance, select the **Automatic Failover** and **Synchronous Commit** options. Do not select the **Readable Secondary** option.</span></span>
    
   - <span data-ttu-id="bc423-346">Clique na guia **Pontos de Extremidade** e verifique se o **Número da Porta** está definido como 5022.</span><span class="sxs-lookup"><span data-stu-id="bc423-346">Click the **Endpoints** tab and verify that **Port Number** is set to 5022.</span></span>
    
   - <span data-ttu-id="bc423-p160">Clique na guia **Ouvinte** e selecione a opção **Criar um ouvinte de grupo de disponibilidade**. Nesta opção, digite um nome para o ouvinte e defina a **Porta** como 1433 (outras portas não são suportadas para esta opção).</span><span class="sxs-lookup"><span data-stu-id="bc423-p160">Click the **Listener** tab, and select the **Create an availability group listener** option. Under that option, type a name for the listener, and set the **Port** to 1433 (other ports are not supported for this option).</span></span>
    
   - <span data-ttu-id="bc423-349">Clique em **Adicionar** e, na caixa **Endereço IPv4**, forneça o endereço IP virtual de sua preferência e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="bc423-349">Click **Add**, and then in the **IPv4 Address** box, provide your preferred virtual IP address, and then click **OK**.</span></span>
    
   - <span data-ttu-id="bc423-p161">Na página **Selecionar Sincronização de Dados Inicial**, selecione Completo, especifique uma pasta que possa ser acessada pelas réplicas e para a qual a conta do serviço SQL Server usada por ambas as réplicas tenha permissões de Gravação. Clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="bc423-p161">In the **Select Initial Data Synchronization** page, select Full, and specify a folder that is accessible to the replicas, and that the SQL Server service account used by both replicas has Write permissions for. Then click **Next**.</span></span>
    
     <span data-ttu-id="bc423-p162">Este compartilhamento de arquivos será usado temporariamente quando você inicializar os bancos de dados. Se você usar bancos de dados grandes, recomendamos que você os inicie manualmente caso a largura de banda de sua rede não possa acomodar o tamanho dos bancos de dados de backup.</span><span class="sxs-lookup"><span data-stu-id="bc423-p162">This file share will be used temporarily when you initialize the databases. If you are dealing with large databases, we recommend that you manually initialize them in case your network bandwidth cannot accommodate the size of the database backups.</span></span>
    
     - <span data-ttu-id="bc423-354">Na página Validação, confira se as verificações de validação foram bem-sucedidas e, em seguida, clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="bc423-354">In the Validation page, verify that all validation checks are successful, then click **Next**.</span></span>
    
   - <span data-ttu-id="bc423-355">Na página **Resumo**, verifique todas as configurações e clique em Concluir.</span><span class="sxs-lookup"><span data-stu-id="bc423-355">In the **Summary** page, verify all settings and click Finish.</span></span>
    
7. <span data-ttu-id="bc423-356">Crie uma nova loja especificando o ouvinte AG.</span><span class="sxs-lookup"><span data-stu-id="bc423-356">Create a new store specifying the AG listener.</span></span>
    
   - <span data-ttu-id="bc423-357">Abrir o construtor de topologias.</span><span class="sxs-lookup"><span data-stu-id="bc423-357">Open Topology Builder.</span></span> <span data-ttu-id="bc423-358">Em sua topologia, expanda **Componentes Compartilhados**, clique com o botão direito do mouse em **Repositórios do SQL Server** e clique em **Novo Repositório do SQL Server**.</span><span class="sxs-lookup"><span data-stu-id="bc423-358">In your topology, expand **Shared Components**, right-click **SQL Server Stores**, and click **New SQL Server Store**.</span></span>
    
   - <span data-ttu-id="bc423-359">Na página **Definir Novo Repositório SQL**, primeiro marque a caixa de seleção **Configurações de Alta Disponibilidade** e, em seguida, certifique-se de que a opção Grupos de Disponibilidade AlwaysOn do SQL aparece na caixa suspensa.</span><span class="sxs-lookup"><span data-stu-id="bc423-359">In the **Define New SQL Store** page, first select the **High Availability Settings** check box, and then make sure that SQL AlwaysOn Availability Groups appears in the drop-down box.</span></span>
    
   - <span data-ttu-id="bc423-360">Na caixa **FQDN do Ouvinte de Disponibilidade do SQL Server**, digite o FQDN do ouvinte que criou quando criou o grupo de disponibilidade.</span><span class="sxs-lookup"><span data-stu-id="bc423-360">In the **SQL Server Availability Listener FQDN** box, type the FQDN of the listener you created when you created the availability group.</span></span>
    
   - <span data-ttu-id="bc423-361">Na caixa **FQDN do SQL Server** , digite o FQDN do nó primário da AG e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="bc423-361">In the **SQL Server FQDN** box, type the FQDN of the primary node of the AG, and then click **OK**.</span></span>
    
8. <span data-ttu-id="bc423-362">Associe o novo grupo de disponibilidade AlwaysOn ao pool de front-ends.</span><span class="sxs-lookup"><span data-stu-id="bc423-362">Associate the new Always On Availability Group with the Front End pool.</span></span>
    
   - <span data-ttu-id="bc423-363">No construtor de topologias, clique com o botão direito do mouse no pool para associá-lo à AG e clique em **Editar propriedades**.</span><span class="sxs-lookup"><span data-stu-id="bc423-363">In Topology Builder, right-click the pool to associate with the AG, and click **Edit Properties**.</span></span>
    
   - <span data-ttu-id="bc423-364">Em **associações**, na caixa da **loja do SQL Server** , selecione a AG.</span><span class="sxs-lookup"><span data-stu-id="bc423-364">Under **Associations**, in the **SQL Server Store** box, select the AG.</span></span> <span data-ttu-id="bc423-365">Selecione o mesmo grupo para qualquer outro banco de dados no pool que você deseja mover para a AG.</span><span class="sxs-lookup"><span data-stu-id="bc423-365">Select the same group for any other databases in the pool which you want to move to the AG.</span></span>
    
   - <span data-ttu-id="bc423-366">Quando tiver certeza de que todos os bancos de dados necessários estão definidos para a AG, clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="bc423-366">When you're sure that all needed databases are set to the AG, click **OK**.</span></span>
    
9. <span data-ttu-id="bc423-367">Publique a topologia.</span><span class="sxs-lookup"><span data-stu-id="bc423-367">Publish the topology.</span></span> <span data-ttu-id="bc423-368">No menu **Ação**, clique em **Topologia** e, em seguida, **Publicar**.</span><span class="sxs-lookup"><span data-stu-id="bc423-368">From the **Action** menu click **Topology** and then **Publish**.</span></span> <span data-ttu-id="bc423-369">Na página de confirmação, clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="bc423-369">Then in the confirmation page click **Next**.</span></span>
    
10. <span data-ttu-id="bc423-370">Execute algumas etapas finais para garantir que os logons do SQL estejam em cada uma das réplicas da AG.</span><span class="sxs-lookup"><span data-stu-id="bc423-370">Perform some final steps to make sure that the SQL logins are on each of the replicas in the AG.</span></span>
    
    - <span data-ttu-id="bc423-371">Abra o construtor de topologias, selecione **baixar topologia de implantação existente**e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="bc423-371">Open Topology Builder, select **Download topology from existing deployment**, and click **OK**.</span></span>
    
    - <span data-ttu-id="bc423-372">Expanda o Skype for Business Server, expanda sua topologia e expanda **Repositórios do SQL Server**.</span><span class="sxs-lookup"><span data-stu-id="bc423-372">Expand Skype for Business Server, expand your topology, and expand **SQL Server Stores**.</span></span> <span data-ttu-id="bc423-373">Clique com o botão direito do mouse na loja do SQL da nova AG e clique em **Editar propriedades**.</span><span class="sxs-lookup"><span data-stu-id="bc423-373">Right-click the SQL store of the new AG, and click **Edit Properties**.</span></span>
    
    - <span data-ttu-id="bc423-374">Na parte inferior da página, na caixa **FQDN do SQL Server** , altere o valor para o FQDN do ouvinte da AG.</span><span class="sxs-lookup"><span data-stu-id="bc423-374">At the bottom of the page, in the **SQL Server FQDN** box, change the value to the FQDN of the Listener of the AG.</span></span>
    
    - <span data-ttu-id="bc423-p167">Publique a topologia. No menu **Ação**, clique em **Topologia** e, em seguida, **Publicar**. Na página de confirmação, clique em **Avançar**. Aguarde alguns minutos para a nova topologia ser replicada.</span><span class="sxs-lookup"><span data-stu-id="bc423-p167">Publish the topology. From the **Action** menu click **Topology** and then **Publish**. Then in the confirmation page click **Next**. Then wait a few minutes for the new topology to replicate.</span></span>
    
    - <span data-ttu-id="bc423-379">Abra o SQL Server Management Studio e navegue até o AG.</span><span class="sxs-lookup"><span data-stu-id="bc423-379">Open SQL Server Management Studio, and navigate to the AG.</span></span> <span data-ttu-id="bc423-380">Faça failover para uma réplica secundária.</span><span class="sxs-lookup"><span data-stu-id="bc423-380">Fail it over to a secondary replica.</span></span>
    
    - <span data-ttu-id="bc423-381">Abra o Shell de gerenciamento do Skype for Business Server e digite o seguinte cmdlet para criar os logons do SQL nesta réplica:</span><span class="sxs-lookup"><span data-stu-id="bc423-381">Open Skype for Business Server Management Shell and type the following cmdlet to create the SQL logins on this replica:</span></span>
    
      ```
      Install-CsDatabase -Update
      ```

      - <span data-ttu-id="bc423-382">Repita as duas etapas anteriores (failover do grupo para uma réplica secundária e, em seguida `Install-CsDatabase -Update`, use) para cada réplica do grupo.</span><span class="sxs-lookup"><span data-stu-id="bc423-382">Repeat the previous two steps (fail over the group to a secondary replica, then use  `Install-CsDatabase -Update`) for each replica in the group.</span></span>
