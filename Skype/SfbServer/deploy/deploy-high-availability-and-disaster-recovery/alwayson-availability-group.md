---
title: Implantar um grupo de disponibilidade Always On em um servidor back-end no Skype for Business Server
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
ms.collection: IT_Skype16
ms.assetid: c93c01e6-626c-40ad-92dd-373b0fe9189f
description: Implante (instale) um Grupo de Disponibilidade Always On em sua implantação do Skype for Business Server.
ms.openlocfilehash: 83565efe850570ac5ab9a0695757e708f3eae566
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49830651"
---
# <a name="deploy-an-always-on-availability-group-on-a-back-end-server-in-skype-for-business-server"></a><span data-ttu-id="e6b1b-103">Implantar um grupo de disponibilidade Always On em um servidor back-end no Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="e6b1b-103">Deploy an Always On Availability Group on a Back End Server in Skype for Business Server</span></span>
 
<span data-ttu-id="e6b1b-104">Implante (instale) um Grupo de Disponibilidade Always On (AG) em sua implantação do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="e6b1b-104">Deploy (install) an Always On Availability Group (AG) in your Skype for Business Server deployment.</span></span>
  
<span data-ttu-id="e6b1b-105">A maneira como você implanta um AG depende se você o está implantando em um novo pool, em um pool existente que usa espelhamento ou em um pool existente que atualmente não tem alta disponibilidade para o banco de dados back-end.</span><span class="sxs-lookup"><span data-stu-id="e6b1b-105">How you deploy an AG depends on whether you are deploying it in a new pool, an existing pool that uses mirroring, or an existing pool that currently has no high availability for the Back End database.</span></span>
  
> [!NOTE]
> <span data-ttu-id="e6b1b-106">O uso de uma AG com uma função de Servidor de Chat Persistente não é suportado.</span><span class="sxs-lookup"><span data-stu-id="e6b1b-106">Using an AG with a Persistent Chat Server role is not supported.</span></span> 
  
- [<span data-ttu-id="e6b1b-107">Implantar um Grupo de Disponibilidade Always On em um novo pool de Front-End</span><span class="sxs-lookup"><span data-stu-id="e6b1b-107">Deploy an Always On Availability Group on a new Front End pool</span></span>](alwayson-availability-group.md#BKMK_NewPool_CreateAlwaysOnGroup)
    
- [<span data-ttu-id="e6b1b-108">Implantar um Grupo de Disponibilidade Always On em um pool existente que usa espelhamento de banco de dados</span><span class="sxs-lookup"><span data-stu-id="e6b1b-108">Deploy an Always On Availability Group on an existing pool that uses database mirroring</span></span>](alwayson-availability-group.md#BKMK_MirroredPool_CreateAlwaysOnGroup)
    
- [<span data-ttu-id="e6b1b-109">Implantar um Grupo de Disponibilidade Always On em um pool existente que não usa espelhamento de banco de dados</span><span class="sxs-lookup"><span data-stu-id="e6b1b-109">Deploy an Always On Availability Group on an existing pool that does not use database mirroring</span></span>](alwayson-availability-group.md#BKMK_NoHAPool_CreateAlwaysOnGroup)
    
## <a name="deploy-an-always-on-availability-group-on-a-new-front-end-pool"></a><span data-ttu-id="e6b1b-110">Implantar um Grupo de Disponibilidade Always On em um novo pool de Front-End</span><span class="sxs-lookup"><span data-stu-id="e6b1b-110">Deploy an Always On Availability Group on a new Front End pool</span></span>
<span data-ttu-id="e6b1b-111"><a name="BKMK_NewPool_CreateAlwaysOnGroup"> </a></span><span class="sxs-lookup"><span data-stu-id="e6b1b-111"><a name="BKMK_NewPool_CreateAlwaysOnGroup"> </a></span></span>

1. <span data-ttu-id="e6b1b-112">Habilita o recurso de Clustering de Failover em todos os servidores de banco de dados que fazem parte do AG.</span><span class="sxs-lookup"><span data-stu-id="e6b1b-112">Enable the Failover Clustering feature on all the database servers which will be part of the AG.</span></span> <span data-ttu-id="e6b1b-113">Em cada servidor, faça o seguinte</span><span class="sxs-lookup"><span data-stu-id="e6b1b-113">On each server, do the following</span></span>
    
   - <span data-ttu-id="e6b1b-114">Abra o Gerenciador do Servidor e clique **em Adicionar funções e recursos.**</span><span class="sxs-lookup"><span data-stu-id="e6b1b-114">Open Server Manager and click **Add roles and features**.</span></span>
    
   - <span data-ttu-id="e6b1b-115">Clique **em Próximo** até chegar à caixa Selecionar **recursos.**</span><span class="sxs-lookup"><span data-stu-id="e6b1b-115">Click **Next** until you reach the **Select features** box.</span></span> <span data-ttu-id="e6b1b-116">Aqui, marque a caixa **de seleção Clustering de Failover.**</span><span class="sxs-lookup"><span data-stu-id="e6b1b-116">Here, select the **Failover Clustering** check box.</span></span>
    
   - <span data-ttu-id="e6b1b-117">Na caixa **Adicionar recursos necessários para Clustering de Failover,** clique em **Adicionar Recursos.**</span><span class="sxs-lookup"><span data-stu-id="e6b1b-117">In the **Add features that are required for Failover Clustering?** box, click **Add Features**.</span></span>
    
   - <span data-ttu-id="e6b1b-118">Clique em **Instalar**.</span><span class="sxs-lookup"><span data-stu-id="e6b1b-118">Click **Install**.</span></span>
    
2. <span data-ttu-id="e6b1b-119">Valide a configuração do cluster.</span><span class="sxs-lookup"><span data-stu-id="e6b1b-119">Validate the cluster configuration.</span></span>
    
   - <span data-ttu-id="e6b1b-120">No Gerenciador do Servidor, clique no menu **Ferramentas** e clique em **Gerenciador de Cluster de Failover.**</span><span class="sxs-lookup"><span data-stu-id="e6b1b-120">In Server Manager, click the **Tools** menu and then click **Failover Cluster Manager**.</span></span>
    
   - <span data-ttu-id="e6b1b-121">Em **Ações** no lado direito da tela, clique em **Validar Configuração.**</span><span class="sxs-lookup"><span data-stu-id="e6b1b-121">Under **Actions** on the right side of the screen, click **Validate Configuration**.</span></span>
    
   - <span data-ttu-id="e6b1b-122">Na página **Antes de começar**, clique em **Seguinte**.</span><span class="sxs-lookup"><span data-stu-id="e6b1b-122">On the **Before You Begin** page, click **Next**.</span></span>
    
   - <span data-ttu-id="e6b1b-123">Selecione os servidores para adicionar ao cluster e clique em **Executar todos os testes.**</span><span class="sxs-lookup"><span data-stu-id="e6b1b-123">Select the servers to add to the cluster, and then click **Run all tests**.</span></span>
    
   - <span data-ttu-id="e6b1b-124">Na caixa **Resumo,** verifique os erros que o assistente relata.</span><span class="sxs-lookup"><span data-stu-id="e6b1b-124">In the **Summary** box, check any errors that the wizard reports.</span></span> <span data-ttu-id="e6b1b-125">Em **seguida, clique em** Concluir para concluir a validação.</span><span class="sxs-lookup"><span data-stu-id="e6b1b-125">Then click **Finish** to complete the validation.</span></span>
    
     <span data-ttu-id="e6b1b-126">O assistente provavelmente relatará vários avisos, especialmente se você não estiver usando o armazenamento compartilhado.</span><span class="sxs-lookup"><span data-stu-id="e6b1b-126">The wizard will probably report several warnings, especially if you are not using shared storage.</span></span> <span data-ttu-id="e6b1b-127">Não é necessário usar o armazenamento compartilhado.</span><span class="sxs-lookup"><span data-stu-id="e6b1b-127">You are not required to use shared storage.</span></span> <span data-ttu-id="e6b1b-128">No entanto, se você vir alguma **mensagem de** erro, deverá corrigir esses problemas antes de continuar.</span><span class="sxs-lookup"><span data-stu-id="e6b1b-128">However, if you see any **Error** messages, you must fix those issues before continuing.</span></span>
    
3. <span data-ttu-id="e6b1b-129">Crie o Cluster de Failover do Windows Server (WSFC).</span><span class="sxs-lookup"><span data-stu-id="e6b1b-129">Create the Windows Server Failover Cluster (WSFC).</span></span>
    
   - <span data-ttu-id="e6b1b-130">No assistente **de Gerenciamento de Cluster de Failover,** clique com o botão direito do mouse em Gerenciamento de Cluster de **Failover** e clique **em Criar Cluster.**</span><span class="sxs-lookup"><span data-stu-id="e6b1b-130">In the **Failover Cluster Management** wizard, right-click **Failover Cluster Management**, then click **Create Cluster**.</span></span>
    
   - <span data-ttu-id="e6b1b-131">Na página **Antes de começar**, clique em **Seguinte**.</span><span class="sxs-lookup"><span data-stu-id="e6b1b-131">On the **Before You Begin** page, click **Next**.</span></span>
    
   - <span data-ttu-id="e6b1b-132">Adicione o nome do cluster e o endereço IP.</span><span class="sxs-lookup"><span data-stu-id="e6b1b-132">Add the cluster name and IP address.</span></span> <span data-ttu-id="e6b1b-133">Quando as configurações são validadas, clique em **Próximo**.</span><span class="sxs-lookup"><span data-stu-id="e6b1b-133">When the settings are validated, click **Next**.</span></span>
    
   - <span data-ttu-id="e6b1b-134">Na página Confirmação, clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="e6b1b-134">On the Confirmation page, click **Next**.</span></span>
    
   - <span data-ttu-id="e6b1b-135">Depois que o cluster for criado, clique em **Concluir.**</span><span class="sxs-lookup"><span data-stu-id="e6b1b-135">After the cluster is created, click **Finish**.</span></span>
    
4. <span data-ttu-id="e6b1b-136">Recomendamos que você configure as configurações de quorum do cluster para usar uma testemunha de compartilhamento de arquivos.</span><span class="sxs-lookup"><span data-stu-id="e6b1b-136">We recommend that you configure the cluster quorum settings to use a file share witness.</span></span> <span data-ttu-id="e6b1b-137">Para fazer isso, use estas etapas:</span><span class="sxs-lookup"><span data-stu-id="e6b1b-137">To do so, use these steps:</span></span>
    
   - <span data-ttu-id="e6b1b-138">Clique com o botão direito do mouse no nome do cluster, clique em **Mais** Ações e clique em **Definir Configurações de Quorum do Cluster.**</span><span class="sxs-lookup"><span data-stu-id="e6b1b-138">Right-click the cluster name, click **More Actions**, and click **Configure Cluster Quorum Settings**.</span></span>
    
   - <span data-ttu-id="e6b1b-139">Na página **Selecionar Opção de Configuração de Quorum,** clique **em Selecionar a testemunha de quórum.**</span><span class="sxs-lookup"><span data-stu-id="e6b1b-139">In the **Select Quorum Configuration Option** page, click **Select the quorum witness**.</span></span>
    
   - <span data-ttu-id="e6b1b-140">Na página **Selecionar Testemunha de Quorum,** clique em **Configurar uma testemunha de compartilhamento de arquivos.**</span><span class="sxs-lookup"><span data-stu-id="e6b1b-140">In the **Select Quorum Witness** page, click **Configure a file share witness**.</span></span>
    
   - <span data-ttu-id="e6b1b-141">Na página **Configurar Testemunha de Compartilhamento de** Arquivos, digite o caminho do compartilhamento de arquivos que você deseja usar e clique em **Próximo.**</span><span class="sxs-lookup"><span data-stu-id="e6b1b-141">In the **Configure File Share Witness** page, type the path of the file share you want to use, and then click **Next**.</span></span>
    
   - <span data-ttu-id="e6b1b-142">Na página **Confirmação**, clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="e6b1b-142">On the **Confirmation** page, click **Next**.</span></span>
    
5. <span data-ttu-id="e6b1b-143">Em cada servidor no cluster, habilita o recurso AG no SQL Server Configuration Manager.</span><span class="sxs-lookup"><span data-stu-id="e6b1b-143">On each server in the cluster, enable the AG feature in SQL Server Configuration Manager.</span></span>
    
   - <span data-ttu-id="e6b1b-144">Abra o Gerente de configuração do SQL Server.</span><span class="sxs-lookup"><span data-stu-id="e6b1b-144">Open SQL Server Configuration Manager.</span></span> <span data-ttu-id="e6b1b-145">Na árvore no lado esquerdo da tela, clique em **SQL Server Services** e, em seguida, clique duas vezes no serviço do SQL Server.</span><span class="sxs-lookup"><span data-stu-id="e6b1b-145">In the tree on the left side of the screen, click **SQL Server Services**, then double-click the SQL Server service.</span></span> 
    
   - <span data-ttu-id="e6b1b-146">Na caixa **Propriedades,** selecione a **guia Alta Disponibilidade AlwaysOn.** Marque a caixa **de seleção Habilitar Grupos de Disponibilidade AlwaysOn.**</span><span class="sxs-lookup"><span data-stu-id="e6b1b-146">In the **Properties** box, select the **AlwaysOn High Availability** tab. Select the **Enable AlwaysOn Availability Groups** check box.</span></span> <span data-ttu-id="e6b1b-147">Reinicie o serviço do SQL Server quando solicitado.</span><span class="sxs-lookup"><span data-stu-id="e6b1b-147">Restart the SQL Server service when prompted.</span></span>
   
6. <span data-ttu-id="e6b1b-148">Use o Construtor de Topologias para criar o pool de Front-End, conforme explicado em Criar e publicar nova [topologia no Skype for Business Server.](../../deploy/install/create-and-publish-new-topology.md)</span><span class="sxs-lookup"><span data-stu-id="e6b1b-148">Use Topology Builder to create the Front End pool, as explained in [Create and publish new topology in Skype for Business Server](../../deploy/install/create-and-publish-new-topology.md).</span></span> <span data-ttu-id="e6b1b-149">Ao fazer isso, especifique o AG como o armazenamento SQL para o pool.</span><span class="sxs-lookup"><span data-stu-id="e6b1b-149">When you do, specify the AG as the SQL store for the pool.</span></span>
    
7. <span data-ttu-id="e6b1b-150">Crie o grupo de disponibilidade.</span><span class="sxs-lookup"><span data-stu-id="e6b1b-150">Create the availability group.</span></span>
    
   - <span data-ttu-id="e6b1b-151">Abra o SQL Server Management Studio e conecte-se à instância do SQL Server.</span><span class="sxs-lookup"><span data-stu-id="e6b1b-151">Open SQL Server Management Studio, and connect to the SQL Server instance.</span></span>
    
   - <span data-ttu-id="e6b1b-152">No Explorador de Objetos, expanda **a pasta Alta Disponibilidade Always On.**</span><span class="sxs-lookup"><span data-stu-id="e6b1b-152">In Object Explorer, expand the **Always On High Availability** folder.</span></span> <span data-ttu-id="e6b1b-153">Clique com o botão direito do mouse na pasta **Grupos de** Disponibilidade e clique em Assistente para Novo Grupo **de Disponibilidade.**</span><span class="sxs-lookup"><span data-stu-id="e6b1b-153">Right-click the **Availability Groups** folder and click **New Availability Group Wizard**.</span></span>
    
   - <span data-ttu-id="e6b1b-154">Se a **página introdução** aparecer, clique em **Próximo**.</span><span class="sxs-lookup"><span data-stu-id="e6b1b-154">If the **Introduction** page appears, click **Next**.</span></span>
    
   - <span data-ttu-id="e6b1b-155">Na página **Especificar Nome do Grupo de Disponibilidade,** digite o nome do grupo de Disponibilidade e clique em **Próximo.**</span><span class="sxs-lookup"><span data-stu-id="e6b1b-155">In the **Specify Availability Group Name** page, type the name of the Availability group, and click **Next**.</span></span>
    
   - <span data-ttu-id="e6b1b-156">Na página Selecionar Bancos de Dados, selecione os bancos de dados que você deseja incluir no Grupo de Disponibilidade AlwaysOn.</span><span class="sxs-lookup"><span data-stu-id="e6b1b-156">In the Select Databases page, select the databases that you want to include in the AlwaysOn Availability Group.</span></span> <span data-ttu-id="e6b1b-157">Em seguida, clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="e6b1b-157">Then click **Next**.</span></span>
    
     <span data-ttu-id="e6b1b-158">Não inclua os bancos de dados **ReportServer**, **ReportServerTempDB** ou Chat Persistente no Grupo de Disponibilidade AlwaysOn, pois eles não são suportados neste cenário.</span><span class="sxs-lookup"><span data-stu-id="e6b1b-158">Do not include the **ReportServer**, **ReportServerTempDB**, or Persistent Chat databases in the AlwaysOn Availability Group, as these are not supported in this scenario.</span></span> <span data-ttu-id="e6b1b-159">Você pode incluir todos os outros bancos de dados do Skype for Business Server no Grupo de Disponibilidade AlwaysOn.</span><span class="sxs-lookup"><span data-stu-id="e6b1b-159">You can include all other Skype for Business Server databases in the AlwaysOn Availability Group.</span></span>
    
   - <span data-ttu-id="e6b1b-160">Na página **Especificar Réplicas,** clique na **guia Réplicas.** Em **seguida, clique** no botão Adicionar Réplicas e conecte-se às outras instâncias SQL que você adicionou como nós do Cluster de Failover do Windows Server.</span><span class="sxs-lookup"><span data-stu-id="e6b1b-160">In the **Specify Replicas** page, click the **Replicas** tab. Then click the **Add Replicas** button, and connect to the other SQL instances that you joined as nodes of the Windows Server Failover Cluster.</span></span>
    
   - <span data-ttu-id="e6b1b-161">Para cada instância, selecione as **opções de Failover Automático** e Confirmação **Síncrona.**</span><span class="sxs-lookup"><span data-stu-id="e6b1b-161">For each instance, select the **Automatic Failover** and **Synchronous Commit** options.</span></span> <span data-ttu-id="e6b1b-162">Não selecione a **opção Secundária Aceitável.**</span><span class="sxs-lookup"><span data-stu-id="e6b1b-162">Do not select the **Readable Secondary** option.</span></span>
    
   - <span data-ttu-id="e6b1b-163">Clique na **guia Pontos de Extremidade e** verifique se o Número **da** Porta está definido como 5022.</span><span class="sxs-lookup"><span data-stu-id="e6b1b-163">Click the **Endpoints** tab and verify that **Port Number** is set to 5022.</span></span>
    
   - <span data-ttu-id="e6b1b-164">Clique na **guia Ouvinte** e selecione a opção Criar um ouvinte do **grupo de** disponibilidade.</span><span class="sxs-lookup"><span data-stu-id="e6b1b-164">Click the **Listener** tab, and select the **Create an availability group listener** option.</span></span> <span data-ttu-id="e6b1b-165">Nessa opção, digite um nome para o  ouvinte e de definir a porta como 1433 (outras portas não são suportadas para essa opção).</span><span class="sxs-lookup"><span data-stu-id="e6b1b-165">Under that option, type a name for the listener, and set the **Port** to 1433 (other ports are not supported for this option).</span></span>
    
   - <span data-ttu-id="e6b1b-166">Clique **em** Adicionar e, em seguida, na caixa **endereço IPv4,** forneça seu endereço IP virtual preferencial e clique em **OK.**</span><span class="sxs-lookup"><span data-stu-id="e6b1b-166">Click **Add**, and then in the **IPv4 Address** box, provide your preferred virtual IP address, and then click **OK**.</span></span>
    
   - <span data-ttu-id="e6b1b-167">Na  página Selecionar Sincronização de Dados Inicial, selecione Completo, especifique uma pasta acessível para as réplicas e para a qual a conta de serviço do SQL Server usada por ambas as réplicas tenha permissões de Gravação.</span><span class="sxs-lookup"><span data-stu-id="e6b1b-167">In the **Select Initial Data Synchronization** page, select Full, and specify a folder that is accessible to the replicas, and that the SQL Server service account used by both replicas has Write permissions for.</span></span> <span data-ttu-id="e6b1b-168">Em seguida, clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="e6b1b-168">Then click **Next**.</span></span>
    
     <span data-ttu-id="e6b1b-169">Esse compartilhamento de arquivos será usado temporariamente quando você inicializar os bancos de dados.</span><span class="sxs-lookup"><span data-stu-id="e6b1b-169">This file share will be used temporarily when you initialize the databases.</span></span> <span data-ttu-id="e6b1b-170">Se você estiver lidando com bancos de dados grandes, recomendamos que você os inicialize manualmente caso sua largura de banda de rede não possa acomodar o tamanho dos backups de banco de dados.</span><span class="sxs-lookup"><span data-stu-id="e6b1b-170">If you are dealing with large databases, we recommend that you manually initialize them in case your network bandwidth cannot accommodate the size of the database backups.</span></span>
    
   - <span data-ttu-id="e6b1b-171">Na página Validação, verifique se todas as verificações de validação foram bem-sucedidas e clique em **Próximo.**</span><span class="sxs-lookup"><span data-stu-id="e6b1b-171">In the Validation page, verify that all validation checks are successful, then click **Next**.</span></span>
    
   - <span data-ttu-id="e6b1b-172">Na página **Resumo,** verifique todas as configurações e clique em Concluir.</span><span class="sxs-lookup"><span data-stu-id="e6b1b-172">In the **Summary** page, verify all settings and click Finish.</span></span>
      
8. <span data-ttu-id="e6b1b-173">Depois que o pool e o AG são implantados, execute algumas etapas finais para garantir que os logons do SQL estão em cada uma das réplicas no Grupo de Disponibilidade AlwaysOn.</span><span class="sxs-lookup"><span data-stu-id="e6b1b-173">After the pool and the AG are deployed, perform some final steps to make sure that the SQL logins are on each of the replicas in the AlwaysOn Availability Group.</span></span> 
    
   - <span data-ttu-id="e6b1b-174">Abra o Construtor de Topologias, **selecione Baixar topologia da implantação existente** e clique em **OK.**</span><span class="sxs-lookup"><span data-stu-id="e6b1b-174">Open Topology Builder, select **Download topology from existing deployment**, and click **OK**.</span></span>
    
   - <span data-ttu-id="e6b1b-175">Expanda o Skype for Business Server, expanda sua topologia e expanda os **Armazenamentos do SQL Server.**</span><span class="sxs-lookup"><span data-stu-id="e6b1b-175">Expand Skype for Business Server, expand your topology, and expand **SQL Server Stores**.</span></span> <span data-ttu-id="e6b1b-176">Clique com o botão direito do mouse no armazenamento SQL do novo Grupo de Disponibilidade AlwaysOn e clique em **Editar Propriedades.**</span><span class="sxs-lookup"><span data-stu-id="e6b1b-176">Right-click the SQL store of the new AlwaysOn Availability Group, and click **Edit Properties**.</span></span>
    
     - <span data-ttu-id="e6b1b-177">Na parte inferior da página, na caixa **FQDN** do SQL Server, altere o valor para o FQDN do Ouvinte do AG.</span><span class="sxs-lookup"><span data-stu-id="e6b1b-177">At the bottom of the page, in the **SQL Server FQDN** box, change the value to the FQDN of the Listener of the AG.</span></span>
    
   - <span data-ttu-id="e6b1b-178">Publique a topologia.</span><span class="sxs-lookup"><span data-stu-id="e6b1b-178">Publish the topology.</span></span> <span data-ttu-id="e6b1b-179">No menu **Ação,** clique **em Topologia** e **publique.**</span><span class="sxs-lookup"><span data-stu-id="e6b1b-179">From the **Action** menu click **Topology** and then **Publish**.</span></span> <span data-ttu-id="e6b1b-180">Em seguida, na página de confirmação, clique em **Próximo**.</span><span class="sxs-lookup"><span data-stu-id="e6b1b-180">Then in the confirmation page click **Next**.</span></span> <span data-ttu-id="e6b1b-181">Aguarde alguns minutos para que a nova topologia seja replicada.</span><span class="sxs-lookup"><span data-stu-id="e6b1b-181">Then wait a few minutes for the new topology to replicate.</span></span>
    
   - <span data-ttu-id="e6b1b-182">Abra o SQL Server Management Studio e navegue até AG.</span><span class="sxs-lookup"><span data-stu-id="e6b1b-182">Open SQL Server Management Studio, and navigate to the AG.</span></span> <span data-ttu-id="e6b1b-183">Fail it over to a secondary replica.</span><span class="sxs-lookup"><span data-stu-id="e6b1b-183">Fail it over to a secondary replica.</span></span>
    
   - <span data-ttu-id="e6b1b-184">Abra o Shell de Gerenciamento do Skype for Business Server e digite o seguinte cmdlet para criar os logons do SQL nesta réplica:</span><span class="sxs-lookup"><span data-stu-id="e6b1b-184">Open Skype for Business Server Management Shell and type the following cmdlet to create the SQL logins on this replica:</span></span>
    
   ```powershell
   Install-CsDatabase -Update
   ```

   - <span data-ttu-id="e6b1b-185">Repita as duas etapas anteriores (fail over the group to a secondary replica, then use  `Install-CsDatabase -Update` ) for each replica in the group.</span><span class="sxs-lookup"><span data-stu-id="e6b1b-185">Repeat the previous two steps (fail over the group to a secondary replica, then use  `Install-CsDatabase -Update`) for each replica in the group.</span></span>
    
## <a name="deploy-an-always-on-availability-group-on-an-existing-pool-that-uses-database-mirroring"></a><span data-ttu-id="e6b1b-186">Implantar um Grupo de Disponibilidade Always On em um pool existente que usa espelhamento de banco de dados</span><span class="sxs-lookup"><span data-stu-id="e6b1b-186">Deploy an Always On Availability Group on an existing pool that uses database mirroring</span></span>
<span data-ttu-id="e6b1b-187"><a name="BKMK_MirroredPool_CreateAlwaysOnGroup"> </a></span><span class="sxs-lookup"><span data-stu-id="e6b1b-187"><a name="BKMK_MirroredPool_CreateAlwaysOnGroup"> </a></span></span>

> [!NOTE]
> <span data-ttu-id="e6b1b-188">Se o pool que você está atualizando para um AG hospeda o armazenamento de Gerenciamento Central da sua organização, primeiro você deve mover o CMS para outro pool antes de atualizar esse pool.</span><span class="sxs-lookup"><span data-stu-id="e6b1b-188">If the pool you are upgrading to an AG hosts the Central Management store for your organization, you must first move the CMS to another pool before you upgrade this pool.</span></span> <span data-ttu-id="e6b1b-189">Use o Move-CsManagementServer cmdlet para mover o pool.</span><span class="sxs-lookup"><span data-stu-id="e6b1b-189">Use the Move-CsManagementServer cmdlet to move the pool.</span></span> <span data-ttu-id="e6b1b-190">Se você não tiver outro pool em sua organização, poderá implantar um servidor Standard Edition temporariamente e mover o CMS para este servidor antes de atualizar seu pool para o AG.</span><span class="sxs-lookup"><span data-stu-id="e6b1b-190">If you do not have another pool in your organization, you can deploy a Standard Edition server temporarily and move the CMS to this server before you upgrade your pool to the AG.</span></span> 
  
1. <span data-ttu-id="e6b1b-191">Fail over all data from the mirror to the principal node by opening Skype for Business Server Management Shell and typing the following cmdlet.</span><span class="sxs-lookup"><span data-stu-id="e6b1b-191">Fail over all data from the mirror to the principal node by opening Skype for Business Server Management Shell and typing the following cmdlet.</span></span>
    
   ```powershell
   Invoke-CsDatabaseFailover -PoolFqdn <Pool FQDN> -DatabaseType <DatabaseType> -NewPrincipal "Primary"
   ```

    <span data-ttu-id="e6b1b-192">Repita esse cmdlet para cada tipo de banco de dados no pool.</span><span class="sxs-lookup"><span data-stu-id="e6b1b-192">Repeat this cmdlet for each database type in the pool.</span></span> <span data-ttu-id="e6b1b-193">Você pode usar o cmdlet a seguir para encontrar todos os tipos de banco de dados armazenados neste pool.</span><span class="sxs-lookup"><span data-stu-id="e6b1b-193">You can use the following cmdlet to find all the database types stored in this pool.</span></span>
     
   ```powershell
   Get-CsPool -Identity <Pool FQDN>
   ```

2. <span data-ttu-id="e6b1b-194">Use o Construtor de Topologias para remover o espelhamento de banco de dados do pool.</span><span class="sxs-lookup"><span data-stu-id="e6b1b-194">Use Topology Builder to remove database mirroring from the pool.</span></span>
    
   - <span data-ttu-id="e6b1b-195">Abra o Construtor de Topologia.</span><span class="sxs-lookup"><span data-stu-id="e6b1b-195">Open Topology Builder.</span></span> <span data-ttu-id="e6b1b-196">Em sua topologia, **expanda pools de front-end** do Enterprise Edition , clique com o botão direito do mouse no nome do pool e clique em **Editar Propriedades**.</span><span class="sxs-lookup"><span data-stu-id="e6b1b-196">In your topology, expand **Enterprise Edition Front End Pools**, right-click the name of the pool, and click **Edit Properties**.</span></span>
    
   - <span data-ttu-id="e6b1b-197">Para cada tipo de armazenamento SQL no pool, des clear the **Enable SQL Store Mirroring** check box.</span><span class="sxs-lookup"><span data-stu-id="e6b1b-197">For each type of SQL store in the pool, clear the **Enable SQL Store Mirroring** check box.</span></span>
    
3. <span data-ttu-id="e6b1b-198">Publique a topologia alterada.</span><span class="sxs-lookup"><span data-stu-id="e6b1b-198">Publish the changed topology.</span></span> <span data-ttu-id="e6b1b-199">No menu **Ação,** clique **em Topologia** e **publique.**</span><span class="sxs-lookup"><span data-stu-id="e6b1b-199">From the **Action** menu click **Topology** and then **Publish**.</span></span> <span data-ttu-id="e6b1b-200">Em seguida, na página de confirmação, clique em **Próximo**</span><span class="sxs-lookup"><span data-stu-id="e6b1b-200">Then in the confirmation page click **Next**</span></span>
    
4. <span data-ttu-id="e6b1b-201">Use o SQL Server Management Studio para quebrar o espelho.</span><span class="sxs-lookup"><span data-stu-id="e6b1b-201">Use SQL Server Management Studio to break the mirror.</span></span>
    
   - <span data-ttu-id="e6b1b-202">Abra o SQL Server Management Studio, navegue até seus bancos de dados, clique com o botão direito do mouse **em Tarefas** e clique em **Espelho.**</span><span class="sxs-lookup"><span data-stu-id="e6b1b-202">Open SQL Server Management Studio, navigate to your databases, right-click **Tasks** and click **Mirror**.</span></span> <span data-ttu-id="e6b1b-203">Em **seguida, clique em Remover Espelhamento** e clique em **OK.**</span><span class="sxs-lookup"><span data-stu-id="e6b1b-203">Then click **Remove Mirroring** and click **OK**.</span></span>
    
   - <span data-ttu-id="e6b1b-204">Repita isso para todos os bancos de dados no pool que serão convertidos em um AG.</span><span class="sxs-lookup"><span data-stu-id="e6b1b-204">Repeat this for all databases in the pool which will be converted to an AG.</span></span>
    
5. <span data-ttu-id="e6b1b-205">Configurar o recurso de Clustering de Failover em todos os servidores de banco de dados que serão parte do AG.</span><span class="sxs-lookup"><span data-stu-id="e6b1b-205">Set up the Failover Clustering feature on all the database servers which will be part of the AG.</span></span> <span data-ttu-id="e6b1b-206">Em cada servidor, faça o seguinte</span><span class="sxs-lookup"><span data-stu-id="e6b1b-206">On each server, do the following</span></span>
    
   - <span data-ttu-id="e6b1b-207">Abra o Gerenciador do Servidor e clique **em Adicionar funções e recursos.**</span><span class="sxs-lookup"><span data-stu-id="e6b1b-207">Open Server Manager and click **Add roles and features**.</span></span>
    
   - <span data-ttu-id="e6b1b-208">Clique **em Próximo** até chegar à caixa Selecionar **recursos.**</span><span class="sxs-lookup"><span data-stu-id="e6b1b-208">Click **Next** until you reach the **Select features** box.</span></span> <span data-ttu-id="e6b1b-209">Aqui, marque a caixa **de seleção Clustering de Failover.**</span><span class="sxs-lookup"><span data-stu-id="e6b1b-209">Here, select the **Failover Clustering** check box.</span></span>
    
   - <span data-ttu-id="e6b1b-210">Na caixa **Adicionar recursos necessários para Clustering de Failover,** clique em **Adicionar Recursos.**</span><span class="sxs-lookup"><span data-stu-id="e6b1b-210">In the **Add features that are required for Failover Clustering?** box, click **Add Features**.</span></span>
    
   - <span data-ttu-id="e6b1b-211">Clique em **Instalar**.</span><span class="sxs-lookup"><span data-stu-id="e6b1b-211">Click **Install**.</span></span>
    
6. <span data-ttu-id="e6b1b-212">Valide a configuração do cluster.</span><span class="sxs-lookup"><span data-stu-id="e6b1b-212">Validate the cluster configuration.</span></span>
    
   - <span data-ttu-id="e6b1b-213">No Gerenciador do Servidor, clique no menu **Ferramentas** e clique em **Gerenciador de Cluster de Failover.**</span><span class="sxs-lookup"><span data-stu-id="e6b1b-213">In Server Manager, click the **Tools** menu and then click **Failover Cluster Manager**.</span></span>
    
   - <span data-ttu-id="e6b1b-214">Em **Ações** no lado direito da tela, clique em **Validar Configuração.**</span><span class="sxs-lookup"><span data-stu-id="e6b1b-214">Under **Actions** on the right side of the screen, click **Validate Configuration**.</span></span>
    
   - <span data-ttu-id="e6b1b-215">Na página **Antes de começar**, clique em **Seguinte**.</span><span class="sxs-lookup"><span data-stu-id="e6b1b-215">On the **Before You Begin** page, click **Next**.</span></span>
    
   - <span data-ttu-id="e6b1b-216">Selecione os servidores para adicionar ao cluster e clique em **Executar todos os testes.**</span><span class="sxs-lookup"><span data-stu-id="e6b1b-216">Select the servers to add to the cluster, and then click **Run all tests**.</span></span>
    
   - <span data-ttu-id="e6b1b-217">Na caixa **Resumo,** verifique os erros que o assistente relata.</span><span class="sxs-lookup"><span data-stu-id="e6b1b-217">In the **Summary** box, check any errors that the wizard reports.</span></span> <span data-ttu-id="e6b1b-218">Em **seguida, clique em** Concluir para concluir a validação.</span><span class="sxs-lookup"><span data-stu-id="e6b1b-218">Then click **Finish** to complete the validation.</span></span>
    
     <span data-ttu-id="e6b1b-219">O assistente provavelmente relatará vários avisos, especialmente se você não estiver usando o armazenamento compartilhado.</span><span class="sxs-lookup"><span data-stu-id="e6b1b-219">The wizard will probably report several warnings, especially if you are not using shared storage.</span></span> <span data-ttu-id="e6b1b-220">Não é necessário usar o armazenamento compartilhado.</span><span class="sxs-lookup"><span data-stu-id="e6b1b-220">You are not required to use shared storage.</span></span> <span data-ttu-id="e6b1b-221">No entanto, se você vir alguma **mensagem de** erro, deverá corrigir esses problemas antes de continuar.</span><span class="sxs-lookup"><span data-stu-id="e6b1b-221">However, if you see any **Error** messages, you must fix those issues before continuing.</span></span>
    
7. <span data-ttu-id="e6b1b-222">Crie o Cluster de Failover do Windows Server.</span><span class="sxs-lookup"><span data-stu-id="e6b1b-222">Create the Windows Server Failover Cluster.</span></span>
    
   - <span data-ttu-id="e6b1b-223">No assistente **de Gerenciamento de Cluster de Failover,** clique com o botão direito do mouse em Gerenciamento de Cluster de **Failover** e clique **em Criar Cluster.**</span><span class="sxs-lookup"><span data-stu-id="e6b1b-223">In the **Failover Cluster Management** wizard, right-click **Failover Cluster Management**, then click **Create Cluster**.</span></span>
    
   - <span data-ttu-id="e6b1b-224">Na página **Antes de começar**, clique em **Seguinte**.</span><span class="sxs-lookup"><span data-stu-id="e6b1b-224">On the **Before You Begin** page, click **Next**.</span></span>
    
   - <span data-ttu-id="e6b1b-225">Adicione o nome do cluster e o endereço IP.</span><span class="sxs-lookup"><span data-stu-id="e6b1b-225">Add the cluster name and IP address.</span></span> <span data-ttu-id="e6b1b-226">Quando as configurações são validadas, clique em **Próximo**.</span><span class="sxs-lookup"><span data-stu-id="e6b1b-226">When the settings are validated, click **Next**.</span></span>
    
   - <span data-ttu-id="e6b1b-227">Na página Confirmação, clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="e6b1b-227">On the Confirmation page, click **Next**.</span></span>
    
   - <span data-ttu-id="e6b1b-228">Depois que o cluster for criado, clique em **Concluir.**</span><span class="sxs-lookup"><span data-stu-id="e6b1b-228">After the cluster is created, click **Finish**.</span></span>
    
8. <span data-ttu-id="e6b1b-229">Recomendamos que você configure as configurações de quorum do cluster para usar uma testemunha de compartilhamento de arquivos.</span><span class="sxs-lookup"><span data-stu-id="e6b1b-229">We recommend that you configure the cluster quorum settings to use a file share witness.</span></span> <span data-ttu-id="e6b1b-230">Para fazer isso, use estas etapas:</span><span class="sxs-lookup"><span data-stu-id="e6b1b-230">To do so, use these steps:</span></span>
    
   - <span data-ttu-id="e6b1b-231">Clique com o botão direito do mouse no nome do cluster, clique em **Mais** Ações e clique em **Definir Configurações de Quorum do Cluster.**</span><span class="sxs-lookup"><span data-stu-id="e6b1b-231">Right-click the cluster name, click **More Actions**, and click **Configure Cluster Quorum Settings**.</span></span>
    
   - <span data-ttu-id="e6b1b-232">Na página **Selecionar Opção de Configuração de Quorum,** clique **em Selecionar a testemunha de quórum.**</span><span class="sxs-lookup"><span data-stu-id="e6b1b-232">In the **Select Quorum Configuration Option** page, click **Select the quorum witness**.</span></span>
    
   - <span data-ttu-id="e6b1b-233">Na página **Selecionar Testemunha de Quorum,** clique em **Configurar uma testemunha de compartilhamento de arquivos.**</span><span class="sxs-lookup"><span data-stu-id="e6b1b-233">In the **Select Quorum Witness** page, click **Configure a file share witness**.</span></span>
    
   - <span data-ttu-id="e6b1b-234">Na página **Configurar Testemunha de Compartilhamento de** Arquivos, digite o caminho do compartilhamento de arquivos que você deseja usar e clique em **Próximo.**</span><span class="sxs-lookup"><span data-stu-id="e6b1b-234">In the **Configure File Share Witness** page, type the path of the file share you want to use, and then click **Next**.</span></span>
    
   - <span data-ttu-id="e6b1b-235">Na página **Confirmação**, clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="e6b1b-235">On the **Confirmation** page, click **Next**.</span></span>
    
9. <span data-ttu-id="e6b1b-236">Em cada servidor no cluster, habilita o recurso AG no SQL Server Configuration Manager.</span><span class="sxs-lookup"><span data-stu-id="e6b1b-236">On each server in the cluster, enable the AG feature in SQL Server Configuration Manager.</span></span>
    
   - <span data-ttu-id="e6b1b-237">Abra o Gerente de configuração do SQL Server.</span><span class="sxs-lookup"><span data-stu-id="e6b1b-237">Open SQL Server Configuration Manager.</span></span> <span data-ttu-id="e6b1b-238">Na árvore no lado esquerdo da tela, clique em **SQL Server Services** e, em seguida, clique duas vezes no serviço do SQL Server.</span><span class="sxs-lookup"><span data-stu-id="e6b1b-238">In the tree on the left side of the screen, click **SQL Server Services**, then double-click the SQL Server service.</span></span> 
    
   - <span data-ttu-id="e6b1b-239">Na caixa **Propriedades,** selecione a **guia Alta Disponibilidade AlwaysOn.** Marque a caixa **de seleção Habilitar Grupos de Disponibilidade AlwaysOn.**</span><span class="sxs-lookup"><span data-stu-id="e6b1b-239">In the **Properties** box, select the **AlwaysOn High Availability** tab. Select the **Enable AlwaysOn Availability Groups** check box.</span></span> <span data-ttu-id="e6b1b-240">Reinicie o serviço do SQL Server quando solicitado.</span><span class="sxs-lookup"><span data-stu-id="e6b1b-240">Restart the SQL Server service when prompted.</span></span>
    
10. <span data-ttu-id="e6b1b-241">Crie o grupo de disponibilidade.</span><span class="sxs-lookup"><span data-stu-id="e6b1b-241">Create the availability group.</span></span>
    
    - <span data-ttu-id="e6b1b-242">Abra o SQL Server Management Studio e conecte-se à instância do SQL Server.</span><span class="sxs-lookup"><span data-stu-id="e6b1b-242">Open SQL Server Management Studio, and connect to the SQL Server instance.</span></span>
    
    - <span data-ttu-id="e6b1b-243">No Explorador de Objetos, expanda **a pasta Alta Disponibilidade Always On.**</span><span class="sxs-lookup"><span data-stu-id="e6b1b-243">In Object Explorer, expand the **Always On High Availability** folder.</span></span> <span data-ttu-id="e6b1b-244">Clique com o botão direito do mouse na pasta **Grupos de** Disponibilidade e clique em Assistente para Novo Grupo **de Disponibilidade.**</span><span class="sxs-lookup"><span data-stu-id="e6b1b-244">Right-click the **Availability Groups** folder and click **New Availability Group Wizard**.</span></span>
    
    - <span data-ttu-id="e6b1b-245">Se a **página introdução** aparecer, clique em **Próximo**.</span><span class="sxs-lookup"><span data-stu-id="e6b1b-245">If the **Introduction** page appears, click **Next**.</span></span>
    
    - <span data-ttu-id="e6b1b-246">Na página **Especificar Nome do Grupo de Disponibilidade,** digite o nome do grupo de Disponibilidade e clique em **Próximo.**</span><span class="sxs-lookup"><span data-stu-id="e6b1b-246">In the **Specify Availability Group Name** page, type the name of the Availability group, and click **Next**.</span></span>
    
    - <span data-ttu-id="e6b1b-247">Na página Selecionar Bancos de Dados, selecione os bancos de dados que você deseja incluir no Grupo de Disponibilidade AlwaysOn.</span><span class="sxs-lookup"><span data-stu-id="e6b1b-247">In the Select Databases page, select the databases that you want to include in the AlwaysOn Availability Group.</span></span> <span data-ttu-id="e6b1b-248">Em seguida, clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="e6b1b-248">Then click **Next**.</span></span>
    
    <span data-ttu-id="e6b1b-249">Não inclua os bancos de dados **ReportServer**, **ReportServerTempDB** ou Chat Persistente no Grupo de Disponibilidade AlwaysOn, pois eles não são suportados neste cenário.</span><span class="sxs-lookup"><span data-stu-id="e6b1b-249">Do not include the **ReportServer**, **ReportServerTempDB**, or Persistent Chat databases in the AlwaysOn Availability Group, as these are not supported in this scenario.</span></span> <span data-ttu-id="e6b1b-250">Você pode incluir todos os outros bancos de dados do Skype for Business Server no Grupo de Disponibilidade AlwaysOn.</span><span class="sxs-lookup"><span data-stu-id="e6b1b-250">You can include all other Skype for Business Server databases in the AlwaysOn Availability Group.</span></span>
    
    - <span data-ttu-id="e6b1b-251">Na página **Especificar Réplicas,** clique na **guia Réplicas.** Em **seguida, clique** no botão Adicionar Réplicas e conecte-se às outras instâncias SQL que você adicionou como nós do Cluster de Failover do Windows Server.</span><span class="sxs-lookup"><span data-stu-id="e6b1b-251">In the **Specify Replicas** page, click the **Replicas** tab. Then click the **Add Replicas** button, and connect to the other SQL instances that you joined as nodes of the Windows Server Failover Cluster.</span></span>
    
    - <span data-ttu-id="e6b1b-252">Para cada instância, selecione as **opções de Failover Automático** e Confirmação **Síncrona.**</span><span class="sxs-lookup"><span data-stu-id="e6b1b-252">For each instance, select the **Automatic Failover** and **Synchronous Commit** options.</span></span> <span data-ttu-id="e6b1b-253">Não selecione a **opção Secundária Aceitável.**</span><span class="sxs-lookup"><span data-stu-id="e6b1b-253">Do not select the **Readable Secondary** option.</span></span>
    
    - <span data-ttu-id="e6b1b-254">Clique na **guia Pontos de Extremidade e** verifique se o Número **da** Porta está definido como 5022.</span><span class="sxs-lookup"><span data-stu-id="e6b1b-254">Click the **Endpoints** tab and verify that **Port Number** is set to 5022.</span></span>
    
      - <span data-ttu-id="e6b1b-255">Clique na **guia Ouvinte** e selecione a opção Criar um ouvinte do **grupo de** disponibilidade.</span><span class="sxs-lookup"><span data-stu-id="e6b1b-255">Click the **Listener** tab, and select the **Create an availability group listener** option.</span></span> <span data-ttu-id="e6b1b-256">Nessa opção, digite um nome para o  ouvinte e de definir a porta como 1433 (outras portas não são suportadas para essa opção).</span><span class="sxs-lookup"><span data-stu-id="e6b1b-256">Under that option, type a name for the listener, and set the **Port** to 1433 (other ports are not supported for this option).</span></span>
    
    - <span data-ttu-id="e6b1b-257">Clique **em** Adicionar e, em seguida, na caixa **endereço IPv4,** forneça seu endereço IP virtual preferencial e clique em **OK.**</span><span class="sxs-lookup"><span data-stu-id="e6b1b-257">Click **Add**, and then in the **IPv4 Address** box, provide your preferred virtual IP address, and then click **OK**.</span></span>
    
    - <span data-ttu-id="e6b1b-258">Na  página Selecionar Sincronização de Dados Inicial, selecione Completo, especifique uma pasta acessível para as réplicas e para a qual a conta de serviço do SQL Server usada por ambas as réplicas tenha permissões de Gravação.</span><span class="sxs-lookup"><span data-stu-id="e6b1b-258">In the **Select Initial Data Synchronization** page, select Full, and specify a folder that is accessible to the replicas, and that the SQL Server service account used by both replicas has Write permissions for.</span></span> <span data-ttu-id="e6b1b-259">Em seguida, clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="e6b1b-259">Then click **Next**.</span></span>
    
    <span data-ttu-id="e6b1b-260">Esse compartilhamento de arquivos será usado temporariamente quando você inicializar os bancos de dados.</span><span class="sxs-lookup"><span data-stu-id="e6b1b-260">This file share will be used temporarily when you initialize the databases.</span></span> <span data-ttu-id="e6b1b-261">Se você estiver lidando com bancos de dados grandes, recomendamos que você os inicialize manualmente caso sua largura de banda de rede não possa acomodar o tamanho dos backups de banco de dados.</span><span class="sxs-lookup"><span data-stu-id="e6b1b-261">If you are dealing with large databases, we recommend that you manually initialize them in case your network bandwidth cannot accommodate the size of the database backups.</span></span>
    
    - <span data-ttu-id="e6b1b-262">Na página Validação, verifique se todas as verificações de validação foram bem-sucedidas e clique em **Próximo.**</span><span class="sxs-lookup"><span data-stu-id="e6b1b-262">In the Validation page, verify that all validation checks are successful, then click **Next**.</span></span>
    
    - <span data-ttu-id="e6b1b-263">Na página **Resumo,** verifique todas as configurações e clique em Concluir.</span><span class="sxs-lookup"><span data-stu-id="e6b1b-263">In the **Summary** page, verify all settings and click Finish.</span></span>
    
11. <span data-ttu-id="e6b1b-264">Crie um novo armazenamento especificando o ouvinte AG e especificando a entidade de entidade do espelho antigo como o nó principal do AG.</span><span class="sxs-lookup"><span data-stu-id="e6b1b-264">Create a new store specifying the AG listener, and specifying the principal of the old mirror as the primary node of the AG.</span></span>
    
    - <span data-ttu-id="e6b1b-265">Abra o Construtor de Topologia.</span><span class="sxs-lookup"><span data-stu-id="e6b1b-265">Open Topology Builder.</span></span> <span data-ttu-id="e6b1b-266">Em sua topologia, **expanda Os Componentes** **Compartilhados,** clique com o botão direito do mouse em Sql Server Store e clique em **Novo Armazenamento do SQL Server.**</span><span class="sxs-lookup"><span data-stu-id="e6b1b-266">In your topology, expand **Shared Components**, right-click **SQL Server Stores**, and click **New SQL Server Store**.</span></span>
    
    - <span data-ttu-id="e6b1b-267">Na página **Definir Novo Armazenamento SQL,** marque primeiro a caixa de seleção Configurações de Alta Disponibilidade e, em seguida, verifique se os Grupos de Disponibilidade AlwaysOn do SQL aparecem na caixa de lista. </span><span class="sxs-lookup"><span data-stu-id="e6b1b-267">In the **Define New SQL Store** page, first select the **High Availability Settings** check box, and then make sure that SQL AlwaysOn Availability Groups appears in the drop-down box.</span></span>
    
    - <span data-ttu-id="e6b1b-268">Na caixa **FQDN** do Ouvinte de Disponibilidade do SQL Server, digite o FQDN do ouvinte que você criou ao criar o grupo de disponibilidade.</span><span class="sxs-lookup"><span data-stu-id="e6b1b-268">In the **SQL Server Availability Listener FQDN** box, type the FQDN of the listener you created when you created the availability group.</span></span>
    
    - <span data-ttu-id="e6b1b-269">Na caixa **FQDN** do SQL Server, digite o FQDN do nó principal do AG e clique em **OK.**</span><span class="sxs-lookup"><span data-stu-id="e6b1b-269">In the **SQL Server FQDN** box, type the FQDN of the primary node of the AG, and then click **OK**.</span></span> <span data-ttu-id="e6b1b-270">Esse deve ser o principal do espelho antigo para esse armazenamento.</span><span class="sxs-lookup"><span data-stu-id="e6b1b-270">This should be the principal of the old mirror for this store.</span></span>
    
12. <span data-ttu-id="e6b1b-271">Associe o novo AG ao pool de Front-End.</span><span class="sxs-lookup"><span data-stu-id="e6b1b-271">Associate the new AG with the Front End pool.</span></span>
    
    - <span data-ttu-id="e6b1b-272">No Construtor de Topologias, clique com o botão direito do mouse no pool a ser associado ao AG e clique em **Editar Propriedades.**</span><span class="sxs-lookup"><span data-stu-id="e6b1b-272">In Topology Builder, right-click the pool to associate with the AG, and click **Edit Properties**.</span></span>
    
    - <span data-ttu-id="e6b1b-273">Em **Associações,** na **caixa Sql Server Store,** selecione AG.</span><span class="sxs-lookup"><span data-stu-id="e6b1b-273">Under **Associations**, in the **SQL Server Store** box, select the AG.</span></span> <span data-ttu-id="e6b1b-274">Selecione o mesmo grupo para quaisquer outros bancos de dados no pool que você deseja mover para o AG.</span><span class="sxs-lookup"><span data-stu-id="e6b1b-274">Select the same group for any other databases in the pool which you want to move to the AG.</span></span>
    
    - <span data-ttu-id="e6b1b-275">Quando você tem certeza de que todos os bancos de dados necessários estão definidos para o AG, clique em **OK.**</span><span class="sxs-lookup"><span data-stu-id="e6b1b-275">When you're sure that all needed databases are set to the AG, click **OK**.</span></span>
    
13. <span data-ttu-id="e6b1b-276">Publique a topologia.</span><span class="sxs-lookup"><span data-stu-id="e6b1b-276">Publish the topology.</span></span> <span data-ttu-id="e6b1b-277">No menu **Ação,** clique **em Topologia** e **publique.**</span><span class="sxs-lookup"><span data-stu-id="e6b1b-277">From the **Action** menu click **Topology** and then **Publish**.</span></span> <span data-ttu-id="e6b1b-278">Em seguida, na página de confirmação, clique em **Próximo**.</span><span class="sxs-lookup"><span data-stu-id="e6b1b-278">Then in the confirmation page click **Next**.</span></span>
    
14. <span data-ttu-id="e6b1b-279">Execute algumas etapas finais para garantir que os logons do SQL estão em cada uma das réplicas no Grupo de Disponibilidade AlwaysOn.</span><span class="sxs-lookup"><span data-stu-id="e6b1b-279">Perform some final steps to make sure that the SQL logins are on each of the replicas in the AlwaysOn Availability Group.</span></span>
    
    - <span data-ttu-id="e6b1b-280">Abra o Construtor de Topologias, **selecione Baixar topologia da implantação existente** e clique em **OK.**</span><span class="sxs-lookup"><span data-stu-id="e6b1b-280">Open Topology Builder, select **Download topology from existing deployment**, and click **OK**.</span></span>
    
    - <span data-ttu-id="e6b1b-281">Expanda o Skype for Business Server, expanda sua topologia e expanda os **Armazenamentos do SQL Server.**</span><span class="sxs-lookup"><span data-stu-id="e6b1b-281">Expand Skype for Business Server, expand your topology, and expand **SQL Server Stores**.</span></span> <span data-ttu-id="e6b1b-282">Clique com o botão direito do mouse no armazenamento SQL do novo AG e clique em **Editar Propriedades.**</span><span class="sxs-lookup"><span data-stu-id="e6b1b-282">Right-click the SQL store of the new AG, and click **Edit Properties**.</span></span>
    
    - <span data-ttu-id="e6b1b-283">Na parte inferior da página, na caixa **FQDN** do SQL Server, altere o valor para o FQDN do Ouvinte do AG.</span><span class="sxs-lookup"><span data-stu-id="e6b1b-283">At the bottom of the page, in the **SQL Server FQDN** box, change the value to the FQDN of the Listener of the AG.</span></span>
    
    - <span data-ttu-id="e6b1b-284">Publique a topologia.</span><span class="sxs-lookup"><span data-stu-id="e6b1b-284">Publish the topology.</span></span> <span data-ttu-id="e6b1b-285">No menu **Ação,** clique **em Topologia** e **publique.**</span><span class="sxs-lookup"><span data-stu-id="e6b1b-285">From the **Action** menu click **Topology** and then **Publish**.</span></span> <span data-ttu-id="e6b1b-286">Em seguida, na página de confirmação, clique em **Próximo**.</span><span class="sxs-lookup"><span data-stu-id="e6b1b-286">Then in the confirmation page click **Next**.</span></span> <span data-ttu-id="e6b1b-287">Aguarde alguns minutos para que a nova topologia seja replicada.</span><span class="sxs-lookup"><span data-stu-id="e6b1b-287">Then wait a few minutes for the new topology to replicate.</span></span>
    
    - <span data-ttu-id="e6b1b-288">Abra o SQL Server Management Studio e navegue até AG.</span><span class="sxs-lookup"><span data-stu-id="e6b1b-288">Open SQL Server Management Studio, and navigate to the AG.</span></span> <span data-ttu-id="e6b1b-289">Fail it over to a secondary replica.</span><span class="sxs-lookup"><span data-stu-id="e6b1b-289">Fail it over to a secondary replica.</span></span>
    
    - <span data-ttu-id="e6b1b-290">Abra o Shell de Gerenciamento do Skype for Business Server e digite o seguinte cmdlet para criar os logons do SQL nesta réplica:</span><span class="sxs-lookup"><span data-stu-id="e6b1b-290">Open Skype for Business Server Management Shell and type the following cmdlet to create the SQL logins on this replica:</span></span>
    
    ```powershell
    Install-CsDatabase -Update
    ```

    - <span data-ttu-id="e6b1b-291">Repita as duas etapas anteriores (fail over the group to a secondary replica, then use  `Install-CsDatabase -Update` ) for each replica in the group.</span><span class="sxs-lookup"><span data-stu-id="e6b1b-291">Repeat the previous two steps (fail over the group to a secondary replica, then use  `Install-CsDatabase -Update`) for each replica in the group.</span></span>
    
## <a name="deploy-an-always-on-availability-group-on-an-existing-pool-that-does-not-use-database-mirroring"></a><span data-ttu-id="e6b1b-292">Implantar um Grupo de Disponibilidade Always On em um pool existente que não usa espelhamento de banco de dados</span><span class="sxs-lookup"><span data-stu-id="e6b1b-292">Deploy an Always On Availability Group on an existing pool that does not use database mirroring</span></span>
<span data-ttu-id="e6b1b-293"><a name="BKMK_NoHAPool_CreateAlwaysOnGroup"> </a></span><span class="sxs-lookup"><span data-stu-id="e6b1b-293"><a name="BKMK_NoHAPool_CreateAlwaysOnGroup"> </a></span></span>

> [!NOTE]
> <span data-ttu-id="e6b1b-294">Se o pool que você está atualizando para um AG hospeda o armazenamento de Gerenciamento Central da sua organização, primeiro você deve mover o CMS para outro pool antes de atualizar esse pool.</span><span class="sxs-lookup"><span data-stu-id="e6b1b-294">If the pool you are upgrading to an AG hosts the Central Management store for your organization, you must first move the CMS to another pool before you upgrade this pool.</span></span> <span data-ttu-id="e6b1b-295">Use o Move-CsManagementServer cmdlet para mover o pool.</span><span class="sxs-lookup"><span data-stu-id="e6b1b-295">Use the Move-CsManagementServer cmdlet to move the pool.</span></span> <span data-ttu-id="e6b1b-296">Se você não tiver outro pool em sua organização, poderá implantar um servidor Standard Edition temporariamente e mover o CMS para este servidor antes de atualizar seu pool para o AG.</span><span class="sxs-lookup"><span data-stu-id="e6b1b-296">If you do not have another pool in your organization, you can deploy a Standard Edition server temporarily and move the CMS to this server before you upgrade your pool to the AG.</span></span> 
  
1. <span data-ttu-id="e6b1b-297">Configurar o recurso de Clustering de Failover em todos os servidores de banco de dados que serão parte do AG.</span><span class="sxs-lookup"><span data-stu-id="e6b1b-297">Set up the Failover Clustering feature on all the database servers which will be part of the AG.</span></span> <span data-ttu-id="e6b1b-298">Em cada servidor, faça o seguinte</span><span class="sxs-lookup"><span data-stu-id="e6b1b-298">On each server, do the following</span></span>
    
   - <span data-ttu-id="e6b1b-299">Abra o Gerenciador do Servidor e clique **em Adicionar funções e recursos.**</span><span class="sxs-lookup"><span data-stu-id="e6b1b-299">Open Server Manager and click **Add roles and features**.</span></span>
    
   - <span data-ttu-id="e6b1b-300">Clique **em Próximo** até chegar à caixa Selecionar **recursos.**</span><span class="sxs-lookup"><span data-stu-id="e6b1b-300">Click **Next** until you reach the **Select features** box.</span></span> <span data-ttu-id="e6b1b-301">Aqui, marque a caixa **de seleção Clustering de Failover.**</span><span class="sxs-lookup"><span data-stu-id="e6b1b-301">Here, select the **Failover Clustering** check box.</span></span>
    
   - <span data-ttu-id="e6b1b-302">Na caixa **Adicionar recursos necessários para Clustering de Failover,** clique em **Adicionar Recursos.**</span><span class="sxs-lookup"><span data-stu-id="e6b1b-302">In the **Add features that are required for Failover Clustering?** box, click **Add Features**.</span></span>
    
   - <span data-ttu-id="e6b1b-303">Clique em **Instalar**.</span><span class="sxs-lookup"><span data-stu-id="e6b1b-303">Click **Install**.</span></span>
    
2. <span data-ttu-id="e6b1b-304">Valide a configuração do cluster.</span><span class="sxs-lookup"><span data-stu-id="e6b1b-304">Validate the cluster configuration.</span></span>
    
   - <span data-ttu-id="e6b1b-305">No Gerenciador do Servidor, clique no menu **Ferramentas** e clique em **Gerenciador de Cluster de Failover.**</span><span class="sxs-lookup"><span data-stu-id="e6b1b-305">In Server Manager, click the **Tools** menu and then click **Failover Cluster Manager**.</span></span>
    
   - <span data-ttu-id="e6b1b-306">Em **Ações** no lado direito da tela, clique em **Validar Configuração.**</span><span class="sxs-lookup"><span data-stu-id="e6b1b-306">Under **Actions** on the right side of the screen, click **Validate Configuration**.</span></span>
    
   - <span data-ttu-id="e6b1b-307">Na página **Antes de começar**, clique em **Seguinte**.</span><span class="sxs-lookup"><span data-stu-id="e6b1b-307">On the **Before You Begin** page, click **Next**.</span></span>
    
   - <span data-ttu-id="e6b1b-308">Selecione os servidores para adicionar ao cluster e clique em **Executar todos os testes.**</span><span class="sxs-lookup"><span data-stu-id="e6b1b-308">Select the servers to add to the cluster, and then click **Run all tests**.</span></span>
    
   - <span data-ttu-id="e6b1b-309">Na caixa **Resumo,** verifique os erros que o assistente relata.</span><span class="sxs-lookup"><span data-stu-id="e6b1b-309">In the **Summary** box, check any errors that the wizard reports.</span></span> <span data-ttu-id="e6b1b-310">Em **seguida, clique em** Concluir para concluir a validação.</span><span class="sxs-lookup"><span data-stu-id="e6b1b-310">Then click **Finish** to complete the validation.</span></span>
    
     <span data-ttu-id="e6b1b-311">O assistente provavelmente relatará vários avisos, especialmente se você não estiver usando o armazenamento compartilhado.</span><span class="sxs-lookup"><span data-stu-id="e6b1b-311">The wizard will probably report several warnings, especially if you are not using shared storage.</span></span> <span data-ttu-id="e6b1b-312">Não é necessário usar o armazenamento compartilhado.</span><span class="sxs-lookup"><span data-stu-id="e6b1b-312">You are not required to use shared storage.</span></span> <span data-ttu-id="e6b1b-313">No entanto, se você vir alguma **mensagem de** erro, deverá corrigir esses problemas antes de continuar.</span><span class="sxs-lookup"><span data-stu-id="e6b1b-313">However, if you see any **Error** messages, you must fix those issues before continuing.</span></span>
    
3. <span data-ttu-id="e6b1b-314">Crie o Cluster de Failover do Windows Server (WSFC).</span><span class="sxs-lookup"><span data-stu-id="e6b1b-314">Create the Windows Server Failover Cluster (WSFC).</span></span>
    
   - <span data-ttu-id="e6b1b-315">No assistente **de Gerenciamento de Cluster de Failover,** clique com o botão direito do mouse em Gerenciamento de Cluster de **Failover** e clique **em Criar Cluster.**</span><span class="sxs-lookup"><span data-stu-id="e6b1b-315">In the **Failover Cluster Management** wizard, right-click **Failover Cluster Management**, then click **Create Cluster**.</span></span>
    
   - <span data-ttu-id="e6b1b-316">Na página **Antes de começar**, clique em **Seguinte**.</span><span class="sxs-lookup"><span data-stu-id="e6b1b-316">On the **Before You Begin** page, click **Next**.</span></span>
    
   - <span data-ttu-id="e6b1b-317">Adicione o nome do cluster e o endereço IP.</span><span class="sxs-lookup"><span data-stu-id="e6b1b-317">Add the cluster name and IP address.</span></span> <span data-ttu-id="e6b1b-318">Quando as configurações são validadas, clique em **Próximo**.</span><span class="sxs-lookup"><span data-stu-id="e6b1b-318">When the settings are validated, click **Next**.</span></span>
    
   - <span data-ttu-id="e6b1b-319">Na página Confirmação, clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="e6b1b-319">On the Confirmation page, click **Next**.</span></span>
    
   - <span data-ttu-id="e6b1b-320">Depois que o cluster for criado, clique em **Concluir.**</span><span class="sxs-lookup"><span data-stu-id="e6b1b-320">After the cluster is created, click **Finish**.</span></span>
    
4. <span data-ttu-id="e6b1b-321">Recomendamos que você configure as configurações de quorum do cluster para usar uma testemunha de compartilhamento de arquivos.</span><span class="sxs-lookup"><span data-stu-id="e6b1b-321">We recommend that you configure the cluster quorum settings to use a file share witness.</span></span> <span data-ttu-id="e6b1b-322">Para fazer isso, use estas etapas:</span><span class="sxs-lookup"><span data-stu-id="e6b1b-322">To do so, use these steps:</span></span>
    
   - <span data-ttu-id="e6b1b-323">Clique com o botão direito do mouse no nome do cluster, clique em **Mais** Ações e clique em **Definir Configurações de Quorum do Cluster.**</span><span class="sxs-lookup"><span data-stu-id="e6b1b-323">Right-click the cluster name, click **More Actions**, and click **Configure Cluster Quorum Settings**.</span></span>
    
   - <span data-ttu-id="e6b1b-324">Na página **Selecionar Opção de Configuração de Quorum,** clique **em Selecionar a testemunha de quórum.**</span><span class="sxs-lookup"><span data-stu-id="e6b1b-324">In the **Select Quorum Configuration Option** page, click **Select the quorum witness**.</span></span>
    
   - <span data-ttu-id="e6b1b-325">Na página **Selecionar Testemunha de Quorum,** clique em **Configurar uma testemunha de compartilhamento de arquivos.**</span><span class="sxs-lookup"><span data-stu-id="e6b1b-325">In the **Select Quorum Witness** page, click **Configure a file share witness**.</span></span>
    
   - <span data-ttu-id="e6b1b-326">Na página **Configurar Testemunha de Compartilhamento de** Arquivos, digite o caminho do compartilhamento de arquivos que você deseja usar e clique em **Próximo.**</span><span class="sxs-lookup"><span data-stu-id="e6b1b-326">In the **Configure File Share Witness** page, type the path of the file share you want to use, and then click **Next**.</span></span>
    
   - <span data-ttu-id="e6b1b-327">Na página **Confirmação**, clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="e6b1b-327">On the **Confirmation** page, click **Next**.</span></span>
    
5. <span data-ttu-id="e6b1b-328">Em cada servidor do cluster, habilita o AG no SQL Server Configuration Manager.</span><span class="sxs-lookup"><span data-stu-id="e6b1b-328">On each server in the cluster, enable AG in SQL Server Configuration Manager.</span></span>
    
   - <span data-ttu-id="e6b1b-329">Abra o Gerente de configuração do SQL Server.</span><span class="sxs-lookup"><span data-stu-id="e6b1b-329">Open SQL Server Configuration Manager.</span></span> <span data-ttu-id="e6b1b-330">Na árvore no lado esquerdo da tela, clique em **SQL Server Services** e, em seguida, clique duas vezes no serviço do SQL Server.</span><span class="sxs-lookup"><span data-stu-id="e6b1b-330">In the tree on the left side of the screen, click **SQL Server Services**, then double-click the SQL Server service.</span></span> 
    
   - <span data-ttu-id="e6b1b-331">Na caixa **Propriedades,** selecione a **guia Alta Disponibilidade AlwaysOn.** Marque a caixa **de seleção Habilitar Grupos de Disponibilidade AlwaysOn.**</span><span class="sxs-lookup"><span data-stu-id="e6b1b-331">In the **Properties** box, select the **AlwaysOn High Availability** tab. Select the **Enable AlwaysOn Availability Groups** check box.</span></span> <span data-ttu-id="e6b1b-332">Reinicie o serviço do SQL Server quando solicitado.</span><span class="sxs-lookup"><span data-stu-id="e6b1b-332">Restart the SQL Server service when prompted.</span></span>
    
6. <span data-ttu-id="e6b1b-333">Crie o grupo de disponibilidade.</span><span class="sxs-lookup"><span data-stu-id="e6b1b-333">Create the availability group.</span></span>
    
   - <span data-ttu-id="e6b1b-334">Abra o SQL Server Management Studio e conecte-se à instância do SQL Server.</span><span class="sxs-lookup"><span data-stu-id="e6b1b-334">Open SQL Server Management Studio, and connect to the SQL Server instance.</span></span>
    
   - <span data-ttu-id="e6b1b-335">No Explorador de Objetos, expanda **a pasta Alta Disponibilidade Always On.**</span><span class="sxs-lookup"><span data-stu-id="e6b1b-335">In Object Explorer, expand the **Always On High Availability** folder.</span></span> <span data-ttu-id="e6b1b-336">Clique com o botão direito do mouse na pasta **Grupos de** Disponibilidade e clique em Assistente para Novo Grupo **de Disponibilidade.**</span><span class="sxs-lookup"><span data-stu-id="e6b1b-336">Right-click the **Availability Groups** folder and click **New Availability Group Wizard**.</span></span>
    
   - <span data-ttu-id="e6b1b-337">Se a **página introdução** aparecer, clique em **Próximo**.</span><span class="sxs-lookup"><span data-stu-id="e6b1b-337">If the **Introduction** page appears, click **Next**.</span></span>
    
   - <span data-ttu-id="e6b1b-338">Na página **Especificar Nome do Grupo de Disponibilidade,** digite o nome do grupo de Disponibilidade e clique em **Próximo.**</span><span class="sxs-lookup"><span data-stu-id="e6b1b-338">In the **Specify Availability Group Name** page, type the name of the Availability group, and click **Next**.</span></span>
    
   - <span data-ttu-id="e6b1b-339">Na página Selecionar Bancos de Dados, selecione os bancos de dados que você deseja incluir no AG.</span><span class="sxs-lookup"><span data-stu-id="e6b1b-339">In the Select Databases page, select the databases that you want to include in the AG.</span></span> <span data-ttu-id="e6b1b-340">Em seguida, clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="e6b1b-340">Then click **Next**.</span></span>
    
     <span data-ttu-id="e6b1b-341">Não inclua os bancos de dados **ReportServer**, **ReportServerTempDB** ou Chat Persistente no AG, pois eles não são suportados neste cenário.</span><span class="sxs-lookup"><span data-stu-id="e6b1b-341">Do not include the **ReportServer**, **ReportServerTempDB**, or Persistent Chat databases in the AG, as these are not supported in this scenario.</span></span> <span data-ttu-id="e6b1b-342">Você pode incluir todos os outros bancos de dados do Skype for Business Server no AG.</span><span class="sxs-lookup"><span data-stu-id="e6b1b-342">You can include all other Skype for Business Server databases in the AG.</span></span>
    
   - <span data-ttu-id="e6b1b-343">Na página **Especificar Réplicas,** clique na **guia Réplicas.** Em **seguida, clique** no botão Adicionar Réplicas e conecte-se às outras instâncias SQL que você adicionou como nós do WSFC.</span><span class="sxs-lookup"><span data-stu-id="e6b1b-343">In the **Specify Replicas** page, click the **Replicas** tab. Then click the **Add Replicas** button, and connect to the other SQL instances that you joined as nodes of the WSFC.</span></span>
    
   - <span data-ttu-id="e6b1b-344">Para cada instância, selecione as **opções de Failover Automático** e Confirmação **Síncrona.**</span><span class="sxs-lookup"><span data-stu-id="e6b1b-344">For each instance, select the **Automatic Failover** and **Synchronous Commit** options.</span></span> <span data-ttu-id="e6b1b-345">Não selecione a **opção Secundária Aceitável.**</span><span class="sxs-lookup"><span data-stu-id="e6b1b-345">Do not select the **Readable Secondary** option.</span></span>
    
   - <span data-ttu-id="e6b1b-346">Clique na **guia Pontos de Extremidade e** verifique se o Número **da** Porta está definido como 5022.</span><span class="sxs-lookup"><span data-stu-id="e6b1b-346">Click the **Endpoints** tab and verify that **Port Number** is set to 5022.</span></span>
    
   - <span data-ttu-id="e6b1b-347">Clique na **guia Ouvinte** e selecione a opção Criar um ouvinte do **grupo de** disponibilidade.</span><span class="sxs-lookup"><span data-stu-id="e6b1b-347">Click the **Listener** tab, and select the **Create an availability group listener** option.</span></span> <span data-ttu-id="e6b1b-348">Nessa opção, digite um nome para o  ouvinte e de definir a porta como 1433 (outras portas não são suportadas para essa opção).</span><span class="sxs-lookup"><span data-stu-id="e6b1b-348">Under that option, type a name for the listener, and set the **Port** to 1433 (other ports are not supported for this option).</span></span>
    
   - <span data-ttu-id="e6b1b-349">Clique **em** Adicionar e, em seguida, na caixa **endereço IPv4,** forneça seu endereço IP virtual preferencial e clique em **OK.**</span><span class="sxs-lookup"><span data-stu-id="e6b1b-349">Click **Add**, and then in the **IPv4 Address** box, provide your preferred virtual IP address, and then click **OK**.</span></span>
    
   - <span data-ttu-id="e6b1b-350">Na  página Selecionar Sincronização de Dados Inicial, selecione Completo, especifique uma pasta acessível para as réplicas e para a qual a conta de serviço do SQL Server usada por ambas as réplicas tenha permissões de Gravação.</span><span class="sxs-lookup"><span data-stu-id="e6b1b-350">In the **Select Initial Data Synchronization** page, select Full, and specify a folder that is accessible to the replicas, and that the SQL Server service account used by both replicas has Write permissions for.</span></span> <span data-ttu-id="e6b1b-351">Em seguida, clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="e6b1b-351">Then click **Next**.</span></span>
    
     <span data-ttu-id="e6b1b-352">Esse compartilhamento de arquivos será usado temporariamente quando você inicializar os bancos de dados.</span><span class="sxs-lookup"><span data-stu-id="e6b1b-352">This file share will be used temporarily when you initialize the databases.</span></span> <span data-ttu-id="e6b1b-353">Se você estiver lidando com bancos de dados grandes, recomendamos que você os inicialize manualmente caso sua largura de banda de rede não possa acomodar o tamanho dos backups de banco de dados.</span><span class="sxs-lookup"><span data-stu-id="e6b1b-353">If you are dealing with large databases, we recommend that you manually initialize them in case your network bandwidth cannot accommodate the size of the database backups.</span></span>
    
     - <span data-ttu-id="e6b1b-354">Na página Validação, verifique se todas as verificações de validação foram bem-sucedidas e clique em **Próximo.**</span><span class="sxs-lookup"><span data-stu-id="e6b1b-354">In the Validation page, verify that all validation checks are successful, then click **Next**.</span></span>
    
   - <span data-ttu-id="e6b1b-355">Na página **Resumo,** verifique todas as configurações e clique em Concluir.</span><span class="sxs-lookup"><span data-stu-id="e6b1b-355">In the **Summary** page, verify all settings and click Finish.</span></span>
    
7. <span data-ttu-id="e6b1b-356">Crie um novo armazenamento especificando o ouvinte AG.</span><span class="sxs-lookup"><span data-stu-id="e6b1b-356">Create a new store specifying the AG listener.</span></span>
    
   - <span data-ttu-id="e6b1b-357">Abra o Construtor de Topologia.</span><span class="sxs-lookup"><span data-stu-id="e6b1b-357">Open Topology Builder.</span></span> <span data-ttu-id="e6b1b-358">Em sua topologia, **expanda Os Componentes** **Compartilhados,** clique com o botão direito do mouse em Sql Server Store e clique em **Novo Armazenamento do SQL Server.**</span><span class="sxs-lookup"><span data-stu-id="e6b1b-358">In your topology, expand **Shared Components**, right-click **SQL Server Stores**, and click **New SQL Server Store**.</span></span>
    
   - <span data-ttu-id="e6b1b-359">Na página **Definir Novo Armazenamento SQL,** marque primeiro a caixa de seleção Configurações de Alta Disponibilidade e, em seguida, verifique se os Grupos de Disponibilidade AlwaysOn do SQL aparecem na caixa de lista. </span><span class="sxs-lookup"><span data-stu-id="e6b1b-359">In the **Define New SQL Store** page, first select the **High Availability Settings** check box, and then make sure that SQL AlwaysOn Availability Groups appears in the drop-down box.</span></span>
    
   - <span data-ttu-id="e6b1b-360">Na caixa **FQDN** do Ouvinte de Disponibilidade do SQL Server, digite o FQDN do ouvinte que você criou ao criar o grupo de disponibilidade.</span><span class="sxs-lookup"><span data-stu-id="e6b1b-360">In the **SQL Server Availability Listener FQDN** box, type the FQDN of the listener you created when you created the availability group.</span></span>
    
   - <span data-ttu-id="e6b1b-361">Na caixa **FQDN** do SQL Server, digite o FQDN do nó principal do AG e clique em **OK.**</span><span class="sxs-lookup"><span data-stu-id="e6b1b-361">In the **SQL Server FQDN** box, type the FQDN of the primary node of the AG, and then click **OK**.</span></span>
    
8. <span data-ttu-id="e6b1b-362">Associe o novo Grupo de Disponibilidade Always On ao pool de Front-End.</span><span class="sxs-lookup"><span data-stu-id="e6b1b-362">Associate the new Always On Availability Group with the Front End pool.</span></span>
    
   - <span data-ttu-id="e6b1b-363">No Construtor de Topologias, clique com o botão direito do mouse no pool a ser associado ao AG e clique em **Editar Propriedades.**</span><span class="sxs-lookup"><span data-stu-id="e6b1b-363">In Topology Builder, right-click the pool to associate with the AG, and click **Edit Properties**.</span></span>
    
   - <span data-ttu-id="e6b1b-364">Em **Associações,** na **caixa Sql Server Store,** selecione AG.</span><span class="sxs-lookup"><span data-stu-id="e6b1b-364">Under **Associations**, in the **SQL Server Store** box, select the AG.</span></span> <span data-ttu-id="e6b1b-365">Selecione o mesmo grupo para quaisquer outros bancos de dados no pool que você deseja mover para o AG.</span><span class="sxs-lookup"><span data-stu-id="e6b1b-365">Select the same group for any other databases in the pool which you want to move to the AG.</span></span>
    
   - <span data-ttu-id="e6b1b-366">Quando você tem certeza de que todos os bancos de dados necessários estão definidos para o AG, clique em **OK.**</span><span class="sxs-lookup"><span data-stu-id="e6b1b-366">When you're sure that all needed databases are set to the AG, click **OK**.</span></span>
    
9. <span data-ttu-id="e6b1b-367">Publique a topologia.</span><span class="sxs-lookup"><span data-stu-id="e6b1b-367">Publish the topology.</span></span> <span data-ttu-id="e6b1b-368">No menu **Ação,** clique **em Topologia** e **publique.**</span><span class="sxs-lookup"><span data-stu-id="e6b1b-368">From the **Action** menu click **Topology** and then **Publish**.</span></span> <span data-ttu-id="e6b1b-369">Em seguida, na página de confirmação, clique em **Próximo**.</span><span class="sxs-lookup"><span data-stu-id="e6b1b-369">Then in the confirmation page click **Next**.</span></span>
    
10. <span data-ttu-id="e6b1b-370">Execute algumas etapas finais para garantir que os logons do SQL estão em cada uma das réplicas no AG.</span><span class="sxs-lookup"><span data-stu-id="e6b1b-370">Perform some final steps to make sure that the SQL logins are on each of the replicas in the AG.</span></span>
    
    - <span data-ttu-id="e6b1b-371">Abra o Construtor de Topologias, **selecione Baixar topologia da implantação existente** e clique em **OK.**</span><span class="sxs-lookup"><span data-stu-id="e6b1b-371">Open Topology Builder, select **Download topology from existing deployment**, and click **OK**.</span></span>
    
    - <span data-ttu-id="e6b1b-372">Expanda o Skype for Business Server, expanda sua topologia e expanda os **Armazenamentos do SQL Server.**</span><span class="sxs-lookup"><span data-stu-id="e6b1b-372">Expand Skype for Business Server, expand your topology, and expand **SQL Server Stores**.</span></span> <span data-ttu-id="e6b1b-373">Clique com o botão direito do mouse no armazenamento SQL do novo AG e clique em **Editar Propriedades.**</span><span class="sxs-lookup"><span data-stu-id="e6b1b-373">Right-click the SQL store of the new AG, and click **Edit Properties**.</span></span>
    
    - <span data-ttu-id="e6b1b-374">Na parte inferior da página, na caixa **FQDN** do SQL Server, altere o valor para o FQDN do Ouvinte do AG.</span><span class="sxs-lookup"><span data-stu-id="e6b1b-374">At the bottom of the page, in the **SQL Server FQDN** box, change the value to the FQDN of the Listener of the AG.</span></span>
    
    - <span data-ttu-id="e6b1b-375">Publique a topologia.</span><span class="sxs-lookup"><span data-stu-id="e6b1b-375">Publish the topology.</span></span> <span data-ttu-id="e6b1b-376">No menu **Ação,** clique **em Topologia** e **publique.**</span><span class="sxs-lookup"><span data-stu-id="e6b1b-376">From the **Action** menu click **Topology** and then **Publish**.</span></span> <span data-ttu-id="e6b1b-377">Em seguida, na página de confirmação, clique em **Próximo**.</span><span class="sxs-lookup"><span data-stu-id="e6b1b-377">Then in the confirmation page click **Next**.</span></span> <span data-ttu-id="e6b1b-378">Aguarde alguns minutos para que a nova topologia seja replicada.</span><span class="sxs-lookup"><span data-stu-id="e6b1b-378">Then wait a few minutes for the new topology to replicate.</span></span>
    
    - <span data-ttu-id="e6b1b-379">Abra o SQL Server Management Studio e navegue até AG.</span><span class="sxs-lookup"><span data-stu-id="e6b1b-379">Open SQL Server Management Studio, and navigate to the AG.</span></span> <span data-ttu-id="e6b1b-380">Fail it over to a secondary replica.</span><span class="sxs-lookup"><span data-stu-id="e6b1b-380">Fail it over to a secondary replica.</span></span>
    
    - <span data-ttu-id="e6b1b-381">Abra o Shell de Gerenciamento do Skype for Business Server e digite o seguinte cmdlet para criar os logons do SQL nesta réplica:</span><span class="sxs-lookup"><span data-stu-id="e6b1b-381">Open Skype for Business Server Management Shell and type the following cmdlet to create the SQL logins on this replica:</span></span>
    
      ```powershell
      Install-CsDatabase -Update
      ```

      - <span data-ttu-id="e6b1b-382">Repita as duas etapas anteriores (fail over the group to a secondary replica, then use  `Install-CsDatabase -Update` ) for each replica in the group.</span><span class="sxs-lookup"><span data-stu-id="e6b1b-382">Repeat the previous two steps (fail over the group to a secondary replica, then use  `Install-CsDatabase -Update`) for each replica in the group.</span></span>
