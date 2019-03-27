---
title: Mover o servidor de gerenciamento Central
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Após migrar para o Skype para Business Server 2019, você precisa mover o servidor de gerenciamento Central para o Skype para Business Server 2019 servidor Front-End ou pool, antes de poder remover o servidor herdado.
ms.openlocfilehash: dc85548a3c81e55267bc0ed3a32e53860e4bce09
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/27/2019
ms.locfileid: "30894744"
---
# <a name="move-the-legacy-central-management-server-to-skype-for-business-server-2019"></a><span data-ttu-id="fa8ee-103">Mover o servidor de gerenciamento Central herdado para Skype para Business Server 2019</span><span class="sxs-lookup"><span data-stu-id="fa8ee-103">Move the legacy Central Management Server to Skype for Business Server 2019</span></span>

<span data-ttu-id="fa8ee-104">Após migrar para o Skype para Business Server 2019 e antes de poder remover o servidor herdado, você precisa mover o servidor de gerenciamento Central para o Skype para Business Server 2019 servidor Front-End ou pool.</span><span class="sxs-lookup"><span data-stu-id="fa8ee-104">After migrating to Skype for Business Server 2019, and before you can remove the legacy server, you need to move the Central Management Server to the Skype for Business Server 2019 Front End Server or pool.</span></span> 
  
<span data-ttu-id="fa8ee-105">O servidor de gerenciamento Central é um sistema de única réplica mestre/múltiplo, onde a cópia de leitura/gravação do banco de dados é mantida por servidor Front-End que contém o servidor de gerenciamento Central.</span><span class="sxs-lookup"><span data-stu-id="fa8ee-105">The Central Management Server is a single master/multiple replica system, where the read/write copy of the database is held by the Front End Server that contains the Central Management Server.</span></span> <span data-ttu-id="fa8ee-106">Cada computador na topologia, incluindo o servidor Front-End que contém o servidor de gerenciamento Central, tem uma cópia somente leitura dos dados do repositório de gerenciamento Central em dados do SQL Server (chamado RTCLOCAL por padrão) instalado no computador durante a instalação e implantação.</span><span class="sxs-lookup"><span data-stu-id="fa8ee-106">Each computer in the topology, including the Front End Server that contains the Central Management Server, has a read-only copy of the Central Management store data in the SQL Server database (named RTCLOCAL by default) installed on the computer during setup and deployment.</span></span> <span data-ttu-id="fa8ee-107">O banco de dados local recebe atualizações de réplica por meio do Skype para agente replicador de réplica de servidor de negócios que é executado como um serviço em todos os computadores.</span><span class="sxs-lookup"><span data-stu-id="fa8ee-107">The local database receives replica updates by way of the Skype for Business Server Replica Replicator Agent that runs as a service on all computers.</span></span> <span data-ttu-id="fa8ee-108">O nome do banco de dados real no servidor de gerenciamento Central e da réplica local é XDS, que é composta dos arquivos XDS. mdf e xds.ldf.</span><span class="sxs-lookup"><span data-stu-id="fa8ee-108">The name of the actual database on the Central Management Server and the local replica is XDS, which is made up of the xds.mdf and xds.ldf files.</span></span> <span data-ttu-id="fa8ee-109">O local do banco de dados mestre é referenciado por um ponto de controle de serviço (SCP) nos serviços de domínio Active Directory.</span><span class="sxs-lookup"><span data-stu-id="fa8ee-109">The master database location is referenced by a service control point (SCP) in Active Directory Domain Services.</span></span> <span data-ttu-id="fa8ee-110">Todas as ferramentas que usam o servidor de gerenciamento Central para gerenciar e configurar o Skype para Business Server usam o SCP para localizar o repositório de gerenciamento Central.</span><span class="sxs-lookup"><span data-stu-id="fa8ee-110">All tools that use the Central Management Server to manage and configure Skype for Business Server use the SCP to locate the Central Management store.</span></span>
  
<span data-ttu-id="fa8ee-111">Após você moveu com êxito o servidor de gerenciamento Central, você deve remover os bancos de dados do servidor de gerenciamento Central do servidor Front-End original.</span><span class="sxs-lookup"><span data-stu-id="fa8ee-111">After you have successfully moved the Central Management Server, you should remove the Central Management Server databases from the original Front End Server.</span></span> <span data-ttu-id="fa8ee-112">Para obter informações sobre como remover os bancos de dados do servidor de gerenciamento Central, consulte [Remover o banco de dados do SQL Server para um pool de Front-End](remove-the-sql-server-database-for-a-front-end-pool.md).</span><span class="sxs-lookup"><span data-stu-id="fa8ee-112">For information on removing the Central Management Server databases, see [Remove the SQL Server database for a Front End pool](remove-the-sql-server-database-for-a-front-end-pool.md).</span></span>
  
<span data-ttu-id="fa8ee-113">Você usa o cmdlet **Move-CsManagementServer** no Skype para Business Server Management Shell mover o banco de dados do banco de dados de SQL Server instalar herdado para o Skype para banco de dados de negócios Server 2019 SQL Server e atualizar do Windows PowerShell a SCP para apontar para o Skype para o local do servidor de gerenciamento Central do Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="fa8ee-113">You use the Windows PowerShell cmdlet **Move-CsManagementServer** in the Skype for Business Server Management Shell to move the database from the legacy install SQL Server database to the Skype for Business Server 2019 SQL Server database, and then update the SCP to point to the Skype for Business Server 2019 Central Management Server location.</span></span> 
  
<span data-ttu-id="fa8ee-114">Use os procedimentos nesta seção para preparar o Skype Business Server 2019 servidores Front-End antes de mover o servidor de gerenciamento Central.</span><span class="sxs-lookup"><span data-stu-id="fa8ee-114">Use the procedures in this section to prepare the Skype for Business Server 2019 Front End Servers before you move the Central Management Server.</span></span>
  
## <a name="to-prepare-an-enterprise-edition-front-end-pool"></a><span data-ttu-id="fa8ee-115">Para preparar um pool de Front End do Enterprise Edition</span><span class="sxs-lookup"><span data-stu-id="fa8ee-115">To prepare an Enterprise Edition Front End pool</span></span>

1. <span data-ttu-id="fa8ee-116">Em Skype para pool de negócios 2019 Enterprise Edition Front-End Server onde você deseja realocar o servidor de gerenciamento Central, faça logon no computador onde o Skype do Shell de gerenciamento do servidor de negócios está instalado como membro do \*\*RTCUniversalServerAdmins \*\*grupo.</span><span class="sxs-lookup"><span data-stu-id="fa8ee-116">On the Skype for Business Server 2019 Enterprise Edition Front End pool where you want to relocate the Central Management Server, log on to the computer where the Skype for Business Server Management Shell is installed as a member of the **RTCUniversalServerAdmins** group.</span></span> <span data-ttu-id="fa8ee-117">Você também deve ter permissões e direitos de usuário de sysadmin do SQL Server banco de dados no banco de dados onde você deseja instalar o repositório de gerenciamento Central.</span><span class="sxs-lookup"><span data-stu-id="fa8ee-117">You must also have SQL Server database sysadmin user rights and permissions on the database where you want to install the Central Management store.</span></span> 
    
2. <span data-ttu-id="fa8ee-118">Abra o Skype do Shell de gerenciamento do servidor de negócios.</span><span class="sxs-lookup"><span data-stu-id="fa8ee-118">Open the Skype for Business Server Management Shell.</span></span>
    
3. <span data-ttu-id="fa8ee-119">Para criar o novo repositório de gerenciamento Central no Skype para banco de dados corporativos Server 2019 SQL Server, no Skype do Shell de gerenciamento do servidor de negócios, digite:</span><span class="sxs-lookup"><span data-stu-id="fa8ee-119">To create the new Central Management store in the Skype for Business Server 2019 SQL Server database, in the Skype for Business Server Management Shell, type:</span></span>
    
   ```
   Install-CsDatabase -CentralManagementDatabase -SQLServerFQDN <FQDN of your SQL Server> -SQLInstanceName <name of instance>
   ```

4. <span data-ttu-id="fa8ee-120">Confirme se o status do serviço do **Skype para Business Server front-end** é **iniciado**.</span><span class="sxs-lookup"><span data-stu-id="fa8ee-120">Confirm that the status of the **Skype for Business Server Front-End** service is **Started**.</span></span>
    
## <a name="to-prepare-a-standard-edition-front-end-server"></a><span data-ttu-id="fa8ee-121">Para preparar um Standard Edition servidor Front-End</span><span class="sxs-lookup"><span data-stu-id="fa8ee-121">To prepare a Standard Edition Front End Server</span></span>

1. <span data-ttu-id="fa8ee-122">Em Skype para Business Server 2019 servidor Standard Edition Front End onde você deseja realocar o servidor de gerenciamento Central, faça logon no computador onde o Skype do Shell de gerenciamento do servidor de negócios está instalado como membro do \*\*RTCUniversalServerAdmins \*\*grupo.</span><span class="sxs-lookup"><span data-stu-id="fa8ee-122">On the Skype for Business Server 2019 Standard Edition Front End Server where you want to relocate the Central Management Server, log on to the computer where the Skype for Business Server Management Shell is installed as a member of the **RTCUniversalServerAdmins** group.</span></span> 
    
2. <span data-ttu-id="fa8ee-123">Abra o Skype do Assistente de implantação de servidor de negócios.</span><span class="sxs-lookup"><span data-stu-id="fa8ee-123">Open the Skype for Business Server Deployment Wizard.</span></span>
    
3. <span data-ttu-id="fa8ee-124">Na Skype para o Assistente de implantação do Business Server, clique em **Preparar primeiro servidor Standard Edition**.</span><span class="sxs-lookup"><span data-stu-id="fa8ee-124">In the Skype for Business Server Deployment Wizard, click **Prepare first Standard Edition server**.</span></span>
    
4. <span data-ttu-id="fa8ee-125">Na página **Executando comandos** , o SQL Server Express está instalado como o servidor de gerenciamento Central.</span><span class="sxs-lookup"><span data-stu-id="fa8ee-125">On the **Executing Commands** page, SQL Server Express is installed as the Central Management Server.</span></span> <span data-ttu-id="fa8ee-126">Regras de firewall necessárias são criadas.</span><span class="sxs-lookup"><span data-stu-id="fa8ee-126">Necessary firewall rules are created.</span></span> <span data-ttu-id="fa8ee-127">Quando a instalação do banco de dados e o software de pré-requisito for concluída, clique em **Concluir**.</span><span class="sxs-lookup"><span data-stu-id="fa8ee-127">When the installation of the database and prerequisite software is completed, click **Finish**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="fa8ee-128">A instalação inicial pode levar algum tempo com nenhuma atualização visível na tela de resumo de saída do comando.</span><span class="sxs-lookup"><span data-stu-id="fa8ee-128">The initial installation may take some time with no visible updates to the command output summary screen.</span></span> <span data-ttu-id="fa8ee-129">Isso acontece devido à instalação do SQL Server Express.</span><span class="sxs-lookup"><span data-stu-id="fa8ee-129">This is due to the installation of SQL Server Express.</span></span> <span data-ttu-id="fa8ee-130">Se você precisa monitorar a instalação do banco de dados, use o Gerenciador de tarefas para monitorar a instalação.</span><span class="sxs-lookup"><span data-stu-id="fa8ee-130">If you need to monitor the installation of the database, use Task Manager to monitor the setup.</span></span> 
  
5. <span data-ttu-id="fa8ee-131">Para criar o novo repositório de gerenciamento Central no Skype para Business Server 2019 Standard Edition servidor Front-End no Skype do Shell de gerenciamento do servidor de negócios, digite:</span><span class="sxs-lookup"><span data-stu-id="fa8ee-131">To create the new Central Management store on the Skype for Business Server 2019 Standard Edition Front End Server, in the Skype for Business Server Management Shell, type:</span></span> 
    
   ```
   Install-CsDatabase -CentralManagementDatabase -SQLServerFQDN <FQDN of your Standard Edition Server> -SQLInstanceName <name of instance - RTC by default>
   ```

6. <span data-ttu-id="fa8ee-132">Confirme se o status do serviço do **Skype para Business Server front-end** é **iniciado**.</span><span class="sxs-lookup"><span data-stu-id="fa8ee-132">Confirm that the status of the **Skype for Business Server Front-End** service is **Started**.</span></span>
    
## <a name="to-move-the-legacy-installs-central-management-server-to-skype-for-business-server-2019"></a><span data-ttu-id="fa8ee-133">Para mover o antigo instala o servidor de gerenciamento Central Skype para Business Server 2019</span><span class="sxs-lookup"><span data-stu-id="fa8ee-133">To move the legacy installs Central Management Server to Skype for Business Server 2019</span></span>

1. <span data-ttu-id="fa8ee-134">Sobre o Skype para servidor de Business Server 2019 que será o servidor de gerenciamento Central, faça logon no computador onde o Skype do Shell de gerenciamento do servidor de negócios está instalado como membro do grupo **RTCUniversalServerAdmins** .</span><span class="sxs-lookup"><span data-stu-id="fa8ee-134">On the Skype for Business Server 2019 server that will be the Central Management Server, log on to the computer where the Skype for Business Server Management Shell is installed as a member of the **RTCUniversalServerAdmins** group.</span></span> <span data-ttu-id="fa8ee-135">Você também deve ter as permissões e direitos de usuário de administrador de banco de dados do SQL Server.</span><span class="sxs-lookup"><span data-stu-id="fa8ee-135">You must also have the SQL Server database administrator user rights and permissions.</span></span> 
    
2. <span data-ttu-id="fa8ee-136">Abra o Skype do Shell de gerenciamento do servidor de negócios.</span><span class="sxs-lookup"><span data-stu-id="fa8ee-136">Open Skype for Business Server Management Shell.</span></span>
    
3. <span data-ttu-id="fa8ee-137">Em Skype do Shell de gerenciamento do servidor de negócios, digite:</span><span class="sxs-lookup"><span data-stu-id="fa8ee-137">In the Skype for Business Server Management Shell, type:</span></span> 
    
   ```
   Enable-CsTopology
   ```

    > [!CAUTION]
    > <span data-ttu-id="fa8ee-138">Se `Enable-CsTopology` não for bem-sucedida, resolver o problema, impedindo que o comando concluir antes de continuar.</span><span class="sxs-lookup"><span data-stu-id="fa8ee-138">If `Enable-CsTopology` is not successful, resolve the problem preventing the command from completing before continuing.</span></span> <span data-ttu-id="fa8ee-139">Se **Enable-CsTopology** não for bem-sucedida, a movimentação falhará e ele poderá deixar a sua topologia em um estado onde não há nenhum repositório de gerenciamento Central.</span><span class="sxs-lookup"><span data-stu-id="fa8ee-139">If **Enable-CsTopology** is not successful, the move will fail and it may leave your topology in a state where there is no Central Management store.</span></span> 
  
4. <span data-ttu-id="fa8ee-140">Sobre o Skype para pool Business Server 2019 servidor Front-End ou Front-End, no Skype do Shell de gerenciamento do servidor de negócios, digite:</span><span class="sxs-lookup"><span data-stu-id="fa8ee-140">On the Skype for Business Server 2019 Front End Server or Front End pool, in the Skype for Business Server Management Shell, type:</span></span> 
    
   ```
   Move-CsManagementServer
   ```

5. <span data-ttu-id="fa8ee-141">Skype do Shell de gerenciamento do servidor de negócios exibe os pontos de conexão de serviço do estado atual e o estado de proposto, repositórios de arquivos, repositórios de banco de dados e os servidores.</span><span class="sxs-lookup"><span data-stu-id="fa8ee-141">Skype for Business Server Management Shell displays the servers, file stores, database stores, and the service connection points of the Current State and the Proposed State.</span></span> <span data-ttu-id="fa8ee-142">Leia as informações cuidadosamente e confirme que este é pretendido de origem e de destino.</span><span class="sxs-lookup"><span data-stu-id="fa8ee-142">Read the information carefully and confirm that this is the intended source and destination.</span></span> <span data-ttu-id="fa8ee-143">Digite **Y** para continuar ou **N** para interromper a movimentação.</span><span class="sxs-lookup"><span data-stu-id="fa8ee-143">Type **Y** to continue, or **N** to stop the move.</span></span> 
    
6. <span data-ttu-id="fa8ee-144">Revise quaisquer avisos ou erros gerados pelo comando **Move-CsManagementServer** e resolva-os.</span><span class="sxs-lookup"><span data-stu-id="fa8ee-144">Review any warnings or errors generated by the **Move-CsManagementServer** command and resolve them.</span></span> 
    
7. <span data-ttu-id="fa8ee-145">No Skype para Business Server 2019 server, abra o Skype para o Assistente de implantação de servidor de negócios.</span><span class="sxs-lookup"><span data-stu-id="fa8ee-145">On the Skype for Business Server 2019 server, open the Skype for Business Server Deployment Wizard.</span></span> 
    
8. <span data-ttu-id="fa8ee-146">No Skype para o Assistente de implantação do Business Server, clique em **instalar ou Skype de atualização para o sistema de servidor de negócios**, clique em **etapa 2: instalar ou remover Skype para componentes de servidor de negócios**, clique em **Avançar**, revise o resumo e clique em \*\*Concluir \*\*.</span><span class="sxs-lookup"><span data-stu-id="fa8ee-146">In Skype for Business Server Deployment Wizard, click **Install or Update Skype for Business Server System**, click **Step 2: Setup or Remove Skype for Business Server Components**, click **Next**, review the summary, and then click **Finish**.</span></span> 
    
9. <span data-ttu-id="fa8ee-147">No antigo servidor instalado, abra o Assistente para implantação.</span><span class="sxs-lookup"><span data-stu-id="fa8ee-147">On the legacy install server, open the Deployment Wizard.</span></span> 
    
10. <span data-ttu-id="fa8ee-148">No Skype para o Assistente de implantação do Business Server, clique em **instalar ou Skype de atualização para o sistema de servidor de negócios**, clique em **etapa 2: instalar ou remover Skype para componentes de servidor de negócios**, clique em **Avançar**, revise o resumo e clique em \*\*Concluir \*\*.</span><span class="sxs-lookup"><span data-stu-id="fa8ee-148">In Skype for Business Server Deployment Wizard, click **Install or Update Skype for Business Server System**, click **Step 2: Setup or Remove Skype for Business Server Components**, click **Next**, review the summary, and then click **Finish**.</span></span> 
    
11. <span data-ttu-id="fa8ee-149">Reinicialize o Skype para Business Server 2019 server.</span><span class="sxs-lookup"><span data-stu-id="fa8ee-149">Reboot the Skype for Business Server 2019 server.</span></span> <span data-ttu-id="fa8ee-150">Isso é necessário devido a uma alteração de associação de grupo para acessar o banco de dados do servidor de gerenciamento Central.</span><span class="sxs-lookup"><span data-stu-id="fa8ee-150">This is required because of a group membership change to access Central Management Server database.</span></span>
    
12. <span data-ttu-id="fa8ee-151">Para confirmar que a replicação com o novo repositório está ocorrendo, além de gerenciamento Central do Skype do Shell de gerenciamento do servidor de negócios, digite:</span><span class="sxs-lookup"><span data-stu-id="fa8ee-151">To confirm that replication with the new Central Management store is occurring, in the Skype for Business Server Management Shell, type:</span></span> 
    
    ```
    Get-CsManagementStoreReplicationStatus
    ```

    > [!NOTE]
    > <span data-ttu-id="fa8ee-152">A replicação pode levar algum tempo para atualizar todas as réplicas atuais.</span><span class="sxs-lookup"><span data-stu-id="fa8ee-152">The replication may take some time to update all current replicas.</span></span> 
  
## <a name="to-remove-legacy-install-central-management-store-files-after-a-move"></a><span data-ttu-id="fa8ee-153">Para remover o legacy instalar arquivos do repositório de gerenciamento Central após uma movimentação</span><span class="sxs-lookup"><span data-stu-id="fa8ee-153">To remove legacy install Central Management store files after a move</span></span>

1. <span data-ttu-id="fa8ee-154">Sobre o antigo instalar o servidor, faça logon no computador onde o Skype do Shell de gerenciamento do servidor de negócios está instalado como membro do grupo **RTCUniversalServerAdmins** .</span><span class="sxs-lookup"><span data-stu-id="fa8ee-154">On the legacy install server, log on to the computer where the Skype for Business Server Management Shell is installed as a member of the **RTCUniversalServerAdmins** group.</span></span> <span data-ttu-id="fa8ee-155">Você também deve ter as permissões e direitos de usuário de administrador de banco de dados do SQL Server.</span><span class="sxs-lookup"><span data-stu-id="fa8ee-155">You must also have the SQL Server database administrator user rights and permissions.</span></span> 
    
2. <span data-ttu-id="fa8ee-156">Abra o Skype do Shell de gerenciamento do servidor de negócios</span><span class="sxs-lookup"><span data-stu-id="fa8ee-156">Open Skype for Business Server Management Shell</span></span>
    
    > [!CAUTION]
    > <span data-ttu-id="fa8ee-157">Não prossiga com a remoção dos arquivos de banco de dados anterior até que a replicação seja concluída e esteja estável.</span><span class="sxs-lookup"><span data-stu-id="fa8ee-157">Do not proceed with the removal of the previous database files until replication is complete and is stable.</span></span> <span data-ttu-id="fa8ee-158">Se você remover os arquivos antes de concluir a replicação, você irá interromper o processo de replicação e deixar o recém movido servidor de gerenciamento Central em um estado desconhecido.</span><span class="sxs-lookup"><span data-stu-id="fa8ee-158">If you remove the files prior to completing replication, you will disrupt the replication process and leave the newly moved Central Management Server in an unknown state.</span></span> <span data-ttu-id="fa8ee-159">Use o cmdlet **Get-CsManagementStoreReplicationStatus** para confirmar o status da replicação.</span><span class="sxs-lookup"><span data-stu-id="fa8ee-159">Use the cmdlet **Get-CsManagementStoreReplicationStatus** to confirm the replication status.</span></span> 
  
3. <span data-ttu-id="fa8ee-160">Para remover os arquivos de banco de dados do repositório de gerenciamento Central da herdado instalar servidor de gerenciamento Central, digite:</span><span class="sxs-lookup"><span data-stu-id="fa8ee-160">To remove the Central Management store database files from the legacy install Central Management Server, type:</span></span>
    
   ```
   Uninstall-CsDatabase -CentralManagementDatabase -SqlServerFqdn <FQDN of SQL Server> -SqlInstanceName <Name of source server>
   ```

    <span data-ttu-id="fa8ee-161">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="fa8ee-161">For example:</span></span>
    
   ```
   Uninstall-CsDatabase -CentralManagementDatabase -SqlServerFqdn sql.contoso.net -SqlInstanceName rtc
   ```

    <span data-ttu-id="fa8ee-162">Onde o _ \<FQDN do SQL Server\> _ é o legados instalar o servidor Back-End em uma implantação do Enterprise Edition ou o FQDN do servidor do Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="fa8ee-162">Where the  _\<FQDN of SQL Server\>_ is either the legacy install Back End Server in an Enterprise Edition deployment or the FQDN of the Standard Edition server.</span></span> 
    

