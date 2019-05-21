---
title: Mover o servidor central de gerenciamento
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Depois de migrar para o Skype for Business Server 2019, você precisa mover o servidor de gerenciamento central para o servidor ou pool de front-end do Skype for Business Server 2019 para poder remover o servidor herdado.
ms.openlocfilehash: 5e16145b6695a9ee7006ab7d5321af9e478d7c37
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34291295"
---
# <a name="move-the-legacy-central-management-server-to-skype-for-business-server-2019"></a><span data-ttu-id="ad508-103">Mover o servidor de gerenciamento central herdado para o Skype for Business Server 2019</span><span class="sxs-lookup"><span data-stu-id="ad508-103">Move the legacy Central Management Server to Skype for Business Server 2019</span></span>

<span data-ttu-id="ad508-104">Depois de migrar para o Skype for Business Server 2019 e antes de remover o servidor herdado, você precisará mover o servidor de gerenciamento central para o servidor ou o pool de front-end do Skype for Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="ad508-104">After migrating to Skype for Business Server 2019, and before you can remove the legacy server, you need to move the Central Management Server to the Skype for Business Server 2019 Front End Server or pool.</span></span> 
  
<span data-ttu-id="ad508-105">O servidor de gerenciamento central é um único sistema de réplica mestra/múltipla, em que a cópia de leitura/gravação do banco de dados é mantida pelo servidor front-end que contém o servidor de gerenciamento central.</span><span class="sxs-lookup"><span data-stu-id="ad508-105">The Central Management Server is a single master/multiple replica system, where the read/write copy of the database is held by the Front End Server that contains the Central Management Server.</span></span> <span data-ttu-id="ad508-106">Cada computador na topologia, incluindo o servidor front-end que contém o servidor de gerenciamento central, tem uma cópia somente leitura dos dados do repositório de gerenciamento central no banco de dados do SQL Server (chamado RTCLOCAL por padrão) instalados no computador durante a instalação e implementação.</span><span class="sxs-lookup"><span data-stu-id="ad508-106">Each computer in the topology, including the Front End Server that contains the Central Management Server, has a read-only copy of the Central Management store data in the SQL Server database (named RTCLOCAL by default) installed on the computer during setup and deployment.</span></span> <span data-ttu-id="ad508-107">O banco de dados local recebe atualizações de réplica por meio do agente duplicador de réplica do servidor do Skype for Business que é executado como um serviço em todos os computadores.</span><span class="sxs-lookup"><span data-stu-id="ad508-107">The local database receives replica updates by way of the Skype for Business Server Replica Replicator Agent that runs as a service on all computers.</span></span> <span data-ttu-id="ad508-108">O nome do banco de dados real no servidor de gerenciamento central e na réplica local é XDS, que é composto pelos arquivos XDS. MDF e XDS. ldf.</span><span class="sxs-lookup"><span data-stu-id="ad508-108">The name of the actual database on the Central Management Server and the local replica is XDS, which is made up of the xds.mdf and xds.ldf files.</span></span> <span data-ttu-id="ad508-109">O local do banco de dados mestre é referenciado por um ponto de controle de serviço (SCP) nos serviços de domínio Active Directory.</span><span class="sxs-lookup"><span data-stu-id="ad508-109">The master database location is referenced by a service control point (SCP) in Active Directory Domain Services.</span></span> <span data-ttu-id="ad508-110">Todas as ferramentas que usam o servidor de gerenciamento central para gerenciar e configurar o Skype for Business Server usam o SCP para localizar o repositório de gerenciamento central.</span><span class="sxs-lookup"><span data-stu-id="ad508-110">All tools that use the Central Management Server to manage and configure Skype for Business Server use the SCP to locate the Central Management store.</span></span>
  
<span data-ttu-id="ad508-111">Depois de mover com êxito o servidor de gerenciamento central, você deve remover os bancos de dados do servidor de gerenciamento central do servidor front-end original.</span><span class="sxs-lookup"><span data-stu-id="ad508-111">After you have successfully moved the Central Management Server, you should remove the Central Management Server databases from the original Front End Server.</span></span> <span data-ttu-id="ad508-112">Para obter informações sobre como remover os bancos de dados do servidor de gerenciamento central, consulte [remover o banco de dados do SQL Server de um pool de front-ends](remove-the-sql-server-database-for-a-front-end-pool.md).</span><span class="sxs-lookup"><span data-stu-id="ad508-112">For information on removing the Central Management Server databases, see [Remove the SQL Server database for a Front End pool](remove-the-sql-server-database-for-a-front-end-pool.md).</span></span>
  
<span data-ttu-id="ad508-113">Você usa o cmdlet **move-CsManagementServer** do Windows PowerShell no Shell de gerenciamento do Skype for Business Server para mover o banco de dados do banco de dados do SQL Server de instalação herdado para o banco de dados do SQL Server do Skype for Business Server 2019 e, em seguida, atualizar o SCP para apontar para o local do servidor de gerenciamento central do Skype for Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="ad508-113">You use the Windows PowerShell cmdlet **Move-CsManagementServer** in the Skype for Business Server Management Shell to move the database from the legacy install SQL Server database to the Skype for Business Server 2019 SQL Server database, and then update the SCP to point to the Skype for Business Server 2019 Central Management Server location.</span></span> 
  
<span data-ttu-id="ad508-114">Use os procedimentos desta seção para preparar os servidores front-end do Skype for Business Server 2019 antes de mover o servidor de gerenciamento central.</span><span class="sxs-lookup"><span data-stu-id="ad508-114">Use the procedures in this section to prepare the Skype for Business Server 2019 Front End Servers before you move the Central Management Server.</span></span>
  
## <a name="to-prepare-an-enterprise-edition-front-end-pool"></a><span data-ttu-id="ad508-115">Para preparar um pool de front-end do Enterprise Edition</span><span class="sxs-lookup"><span data-stu-id="ad508-115">To prepare an Enterprise Edition Front End pool</span></span>

1. <span data-ttu-id="ad508-116">No pool de front-ends do Skype for Business Server 2019 Enterprise Edition onde você deseja realocar o servidor de gerenciamento central, faça logon no computador em que o Shell de gerenciamento do Skype for Business Server está instalado como membro da \*\*RTCUniversalServerAdmins \*\*grupo.</span><span class="sxs-lookup"><span data-stu-id="ad508-116">On the Skype for Business Server 2019 Enterprise Edition Front End pool where you want to relocate the Central Management Server, log on to the computer where the Skype for Business Server Management Shell is installed as a member of the **RTCUniversalServerAdmins** group.</span></span> <span data-ttu-id="ad508-117">Você também deve ter direitos de usuário e permissões do banco de dados do SQL Server sysadmin no banco de dados onde deseja instalar o repositório de gerenciamento central.</span><span class="sxs-lookup"><span data-stu-id="ad508-117">You must also have SQL Server database sysadmin user rights and permissions on the database where you want to install the Central Management store.</span></span> 
    
2. <span data-ttu-id="ad508-118">Abra o Shell de gerenciamento do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="ad508-118">Open the Skype for Business Server Management Shell.</span></span>
    
3. <span data-ttu-id="ad508-119">Para criar o novo repositório de gerenciamento central no banco de dados do Skype for Business Server 2019 do SQL Server, no Shell de gerenciamento do Skype for Business Server, digite:</span><span class="sxs-lookup"><span data-stu-id="ad508-119">To create the new Central Management store in the Skype for Business Server 2019 SQL Server database, in the Skype for Business Server Management Shell, type:</span></span>
    
   ```
   Install-CsDatabase -CentralManagementDatabase -SQLServerFQDN <FQDN of your SQL Server> -SQLInstanceName <name of instance>
   ```

4. <span data-ttu-id="ad508-120">Confirme se o status do serviço de **front-end do Skype for Business Server** foi **iniciado**.</span><span class="sxs-lookup"><span data-stu-id="ad508-120">Confirm that the status of the **Skype for Business Server Front-End** service is **Started**.</span></span>
    
## <a name="to-prepare-a-standard-edition-front-end-server"></a><span data-ttu-id="ad508-121">Para preparar um servidor front-end padrão da edição</span><span class="sxs-lookup"><span data-stu-id="ad508-121">To prepare a Standard Edition Front End Server</span></span>

1. <span data-ttu-id="ad508-122">No servidor front-end do Skype for Business Server 2019 Standard Edition onde você deseja realocar o servidor de gerenciamento central, faça logon no computador em que o Shell de gerenciamento do Skype for Business Server está instalado como membro da \*\*RTCUniversalServerAdmins \*\*grupo.</span><span class="sxs-lookup"><span data-stu-id="ad508-122">On the Skype for Business Server 2019 Standard Edition Front End Server where you want to relocate the Central Management Server, log on to the computer where the Skype for Business Server Management Shell is installed as a member of the **RTCUniversalServerAdmins** group.</span></span> 
    
2. <span data-ttu-id="ad508-123">Abra o assistente de implantação do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="ad508-123">Open the Skype for Business Server Deployment Wizard.</span></span>
    
3. <span data-ttu-id="ad508-124">No assistente de implantação do Skype for Business Server, clique em **preparar primeiro servidor Standard Edition**.</span><span class="sxs-lookup"><span data-stu-id="ad508-124">In the Skype for Business Server Deployment Wizard, click **Prepare first Standard Edition server**.</span></span>
    
4. <span data-ttu-id="ad508-125">Na página **comandos em execução** , o SQL Server Express é instalado como o servidor de gerenciamento central.</span><span class="sxs-lookup"><span data-stu-id="ad508-125">On the **Executing Commands** page, SQL Server Express is installed as the Central Management Server.</span></span> <span data-ttu-id="ad508-126">Regras de firewall necessárias são criadas.</span><span class="sxs-lookup"><span data-stu-id="ad508-126">Necessary firewall rules are created.</span></span> <span data-ttu-id="ad508-127">Quando a instalação do banco de dados e do software de pré-requisito estiver concluída, clique em **concluir**.</span><span class="sxs-lookup"><span data-stu-id="ad508-127">When the installation of the database and prerequisite software is completed, click **Finish**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="ad508-128">A instalação inicial pode levar algum tempo sem atualizações visíveis para a tela Resumo da saída do comando.</span><span class="sxs-lookup"><span data-stu-id="ad508-128">The initial installation may take some time with no visible updates to the command output summary screen.</span></span> <span data-ttu-id="ad508-129">Isso se deve à instalação do SQL Server Express.</span><span class="sxs-lookup"><span data-stu-id="ad508-129">This is due to the installation of SQL Server Express.</span></span> <span data-ttu-id="ad508-130">Se você precisar monitorar a instalação do banco de dados, use o Gerenciador de tarefas para monitorar a configuração.</span><span class="sxs-lookup"><span data-stu-id="ad508-130">If you need to monitor the installation of the database, use Task Manager to monitor the setup.</span></span> 
  
5. <span data-ttu-id="ad508-131">Para criar o novo repositório de gerenciamento central no servidor front-end do Skype for Business Server 2019 Standard Edition, no Shell de gerenciamento do Skype for Business Server, digite:</span><span class="sxs-lookup"><span data-stu-id="ad508-131">To create the new Central Management store on the Skype for Business Server 2019 Standard Edition Front End Server, in the Skype for Business Server Management Shell, type:</span></span> 
    
   ```
   Install-CsDatabase -CentralManagementDatabase -SQLServerFQDN <FQDN of your Standard Edition Server> -SQLInstanceName <name of instance - RTC by default>
   ```

6. <span data-ttu-id="ad508-132">Confirme se o status do serviço de **front-end do Skype for Business Server** foi **iniciado**.</span><span class="sxs-lookup"><span data-stu-id="ad508-132">Confirm that the status of the **Skype for Business Server Front-End** service is **Started**.</span></span>
    
## <a name="to-move-the-legacy-installs-central-management-server-to-skype-for-business-server-2019"></a><span data-ttu-id="ad508-133">Para mover o herdado instala o servidor central de gerenciamento para o Skype for Business Server 2019</span><span class="sxs-lookup"><span data-stu-id="ad508-133">To move the legacy installs Central Management Server to Skype for Business Server 2019</span></span>

1. <span data-ttu-id="ad508-134">No servidor do Skype for Business Server 2019 que será o servidor de gerenciamento central, faça logon no computador em que o Shell de gerenciamento do Skype for Business Server está instalado como membro do grupo **RTCUniversalServerAdmins** .</span><span class="sxs-lookup"><span data-stu-id="ad508-134">On the Skype for Business Server 2019 server that will be the Central Management Server, log on to the computer where the Skype for Business Server Management Shell is installed as a member of the **RTCUniversalServerAdmins** group.</span></span> <span data-ttu-id="ad508-135">Você também deve ter direitos de usuário e permissões de administrador de banco de dados do SQL Server.</span><span class="sxs-lookup"><span data-stu-id="ad508-135">You must also have the SQL Server database administrator user rights and permissions.</span></span> 
    
2. <span data-ttu-id="ad508-136">Abrir o Shell de gerenciamento do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="ad508-136">Open Skype for Business Server Management Shell.</span></span>
    
3. <span data-ttu-id="ad508-137">No Shell de gerenciamento do Skype for Business Server, digite:</span><span class="sxs-lookup"><span data-stu-id="ad508-137">In the Skype for Business Server Management Shell, type:</span></span> 
    
   ```
   Enable-CsTopology
   ```

    > [!CAUTION]
    > <span data-ttu-id="ad508-138">Se `Enable-CsTopology` o problema não for bem-sucedido, resolva o problema para impedir que o comando seja concluído antes de continuar.</span><span class="sxs-lookup"><span data-stu-id="ad508-138">If `Enable-CsTopology` is not successful, resolve the problem preventing the command from completing before continuing.</span></span> <span data-ttu-id="ad508-139">Se **Enable-CsTopology** não for bem-sucedido, a mudança falhará e poderá deixar a sua topologia em um estado em que não haja repositório de gerenciamento central.</span><span class="sxs-lookup"><span data-stu-id="ad508-139">If **Enable-CsTopology** is not successful, the move will fail and it may leave your topology in a state where there is no Central Management store.</span></span> 
  
4. <span data-ttu-id="ad508-140">No servidor front-end do Skype for Business Server 2019 ou no pool de front-end do Shell de gerenciamento do Skype for Business Server, digite:</span><span class="sxs-lookup"><span data-stu-id="ad508-140">On the Skype for Business Server 2019 Front End Server or Front End pool, in the Skype for Business Server Management Shell, type:</span></span> 
    
   ```
   Move-CsManagementServer
   ```

5. <span data-ttu-id="ad508-141">Shell de gerenciamento do Skype for Business Server exibe os servidores, armazenamentos de arquivos, armazenamentos de banco de dados e os pontos de conexão de serviço do estado atual e o Estado proposto.</span><span class="sxs-lookup"><span data-stu-id="ad508-141">Skype for Business Server Management Shell displays the servers, file stores, database stores, and the service connection points of the Current State and the Proposed State.</span></span> <span data-ttu-id="ad508-142">Leia as informações com atenção e confirme se essa é a origem e o destino pretendidos.</span><span class="sxs-lookup"><span data-stu-id="ad508-142">Read the information carefully and confirm that this is the intended source and destination.</span></span> <span data-ttu-id="ad508-143">Digite **Y** para continuar ou **N** para interromper a movimentação.</span><span class="sxs-lookup"><span data-stu-id="ad508-143">Type **Y** to continue, or **N** to stop the move.</span></span> 
    
6. <span data-ttu-id="ad508-144">Revise todos os avisos ou erros gerados pelo comando **mover-CsManagementServer** e resolva-os.</span><span class="sxs-lookup"><span data-stu-id="ad508-144">Review any warnings or errors generated by the **Move-CsManagementServer** command and resolve them.</span></span> 
    
7. <span data-ttu-id="ad508-145">No servidor do Skype for Business Server 2019, abra o assistente de implantação do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="ad508-145">On the Skype for Business Server 2019 server, open the Skype for Business Server Deployment Wizard.</span></span> 
    
8. <span data-ttu-id="ad508-146">No assistente de implantação do Skype for Business Server, clique em **instalar ou atualizar o sistema do Skype for Business Server**, clique em **etapa 2: configurar ou remover componentes do Skype for Business Server**, clique em **Avançar**, revise o resumo e clique em \*\*concluir. \*\*.</span><span class="sxs-lookup"><span data-stu-id="ad508-146">In Skype for Business Server Deployment Wizard, click **Install or Update Skype for Business Server System**, click **Step 2: Setup or Remove Skype for Business Server Components**, click **Next**, review the summary, and then click **Finish**.</span></span> 
    
9. <span data-ttu-id="ad508-147">No servidor de instalação herdado, abra o assistente de implantação.</span><span class="sxs-lookup"><span data-stu-id="ad508-147">On the legacy install server, open the Deployment Wizard.</span></span> 
    
10. <span data-ttu-id="ad508-148">No assistente de implantação do Skype for Business Server, clique em **instalar ou atualizar o sistema do Skype for Business Server**, clique em **etapa 2: configurar ou remover componentes do Skype for Business Server**, clique em **Avançar**, revise o resumo e clique em \*\*concluir. \*\*.</span><span class="sxs-lookup"><span data-stu-id="ad508-148">In Skype for Business Server Deployment Wizard, click **Install or Update Skype for Business Server System**, click **Step 2: Setup or Remove Skype for Business Server Components**, click **Next**, review the summary, and then click **Finish**.</span></span> 
    
11. <span data-ttu-id="ad508-149">Reinicie o servidor do Skype for Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="ad508-149">Reboot the Skype for Business Server 2019 server.</span></span> <span data-ttu-id="ad508-150">Isso é necessário devido a uma alteração de associação do grupo para acessar o banco de dados do servidor de gerenciamento central.</span><span class="sxs-lookup"><span data-stu-id="ad508-150">This is required because of a group membership change to access Central Management Server database.</span></span>
    
12. <span data-ttu-id="ad508-151">Para confirmar se a replicação com o novo repositório de gerenciamento central está ocorrendo, no Shell de gerenciamento do Skype for Business Server, digite:</span><span class="sxs-lookup"><span data-stu-id="ad508-151">To confirm that replication with the new Central Management store is occurring, in the Skype for Business Server Management Shell, type:</span></span> 
    
    ```
    Get-CsManagementStoreReplicationStatus
    ```

    > [!NOTE]
    > <span data-ttu-id="ad508-152">A replicação pode levar algum tempo para atualizar todas as réplicas atuais.</span><span class="sxs-lookup"><span data-stu-id="ad508-152">The replication may take some time to update all current replicas.</span></span> 
  
## <a name="to-remove-legacy-install-central-management-store-files-after-a-move"></a><span data-ttu-id="ad508-153">Para remover arquivos do repositório de gerenciamento central de instalação herdada após uma mudança</span><span class="sxs-lookup"><span data-stu-id="ad508-153">To remove legacy install Central Management store files after a move</span></span>

1. <span data-ttu-id="ad508-154">No servidor de instalação herdado, faça logon no computador em que o Shell de gerenciamento do Skype for Business Server está instalado como membro do grupo **RTCUniversalServerAdmins** .</span><span class="sxs-lookup"><span data-stu-id="ad508-154">On the legacy install server, log on to the computer where the Skype for Business Server Management Shell is installed as a member of the **RTCUniversalServerAdmins** group.</span></span> <span data-ttu-id="ad508-155">Você também deve ter direitos de usuário e permissões de administrador de banco de dados do SQL Server.</span><span class="sxs-lookup"><span data-stu-id="ad508-155">You must also have the SQL Server database administrator user rights and permissions.</span></span> 
    
2. <span data-ttu-id="ad508-156">Abrir o Shell de gerenciamento do Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="ad508-156">Open Skype for Business Server Management Shell</span></span>
    
    > [!CAUTION]
    > <span data-ttu-id="ad508-157">Não prossiga com a remoção dos arquivos de banco de dados anteriores até que a replicação seja concluída e seja estável.</span><span class="sxs-lookup"><span data-stu-id="ad508-157">Do not proceed with the removal of the previous database files until replication is complete and is stable.</span></span> <span data-ttu-id="ad508-158">Se você remover os arquivos antes de concluir a replicação, irá interromper o processo de replicação e deixar o servidor de gerenciamento central recentemente movido em um estado desconhecido.</span><span class="sxs-lookup"><span data-stu-id="ad508-158">If you remove the files prior to completing replication, you will disrupt the replication process and leave the newly moved Central Management Server in an unknown state.</span></span> <span data-ttu-id="ad508-159">Use o cmdlet **Get-CsManagementStoreReplicationStatus** para confirmar o status de replicação.</span><span class="sxs-lookup"><span data-stu-id="ad508-159">Use the cmdlet **Get-CsManagementStoreReplicationStatus** to confirm the replication status.</span></span> 
  
3. <span data-ttu-id="ad508-160">Para remover os arquivos de banco de dados do repositório de gerenciamento central do servidor de gerenciamento central de instalação herdada, digite:</span><span class="sxs-lookup"><span data-stu-id="ad508-160">To remove the Central Management store database files from the legacy install Central Management Server, type:</span></span>
    
   ```
   Uninstall-CsDatabase -CentralManagementDatabase -SqlServerFqdn <FQDN of SQL Server> -SqlInstanceName <Name of source server>
   ```

    <span data-ttu-id="ad508-161">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="ad508-161">For example:</span></span>
    
   ```
   Uninstall-CsDatabase -CentralManagementDatabase -SqlServerFqdn sql.contoso.net -SqlInstanceName rtc
   ```

    <span data-ttu-id="ad508-162">Onde o _ \<FQDN do SQL Server\> _ é o servidor back-end de instalação herdada em uma implantação do Enterprise Edition ou o FQDN do servidor Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="ad508-162">Where the  _\<FQDN of SQL Server\>_ is either the legacy install Back End Server in an Enterprise Edition deployment or the FQDN of the Standard Edition server.</span></span> 
    

