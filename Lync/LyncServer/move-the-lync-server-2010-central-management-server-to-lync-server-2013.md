---
title: Mover o servidor de gerenciamento central do Lync Server 2010 para o Lync Server 2013
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Move the Lync Server 2010 Central Management Server to Lync Server 2013
ms:assetid: 30cc98f2-1916-4dbe-99d0-8df5368ed3ec
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688013(v=OCS.15)
ms:contentKeyID: 49733602
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 29bdf9a5956dfec0dd35703aaf7a7606da63595b
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42034461"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="move-the-lync-server-2010-central-management-server-to-lync-server-2013"></a><span data-ttu-id="3548b-102">Mover o servidor de gerenciamento central do Lync Server 2010 para o Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3548b-102">Move the Lync Server 2010 Central Management Server to Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3548b-103">_**Última modificação do tópico:** 2013-11-25_</span><span class="sxs-lookup"><span data-stu-id="3548b-103">_**Topic Last Modified:** 2013-11-25_</span></span>

<span data-ttu-id="3548b-104">Após a migração do Lync Server 2010 para o Lync Server 2013, você precisa mover o servidor de gerenciamento central do Lync Server 2010 para o servidor front-end do Lync Server 2013 ou pool, antes de poder remover o servidor herdado do Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="3548b-104">After migrating from Lync Server 2010 to Lync Server 2013, you need to move the Lync Server 2010 Central Management Server to the Lync Server 2013 Front End Server or pool, before you can remove the legacy Lync Server 2010 server.</span></span>

<span data-ttu-id="3548b-105">O servidor de gerenciamento central é um único sistema de réplicas/mestres, onde a cópia de leitura/gravação do banco de dados é mantida pelo servidor de front-end que contém o servidor de gerenciamento central.</span><span class="sxs-lookup"><span data-stu-id="3548b-105">The Central Management Server is a single master/multiple replica system, where the read/write copy of the database is held by the Front End Server that contains the Central Management Server.</span></span> <span data-ttu-id="3548b-106">Cada computador na topologia, incluindo o servidor front-end que contém o servidor de gerenciamento central, tem uma cópia somente leitura do repositório de gerenciamento central no banco de dados do SQL Server (chamado RTCLOCAL por padrão) instalado no computador durante a instalação e instalação.</span><span class="sxs-lookup"><span data-stu-id="3548b-106">Each computer in the topology, including the Front End Server that contains the Central Management Server, has a read-only copy of the Central Management store data in the SQL Server database (named RTCLOCAL by default) installed on the computer during setup and deployment.</span></span> <span data-ttu-id="3548b-107">O banco de dados local recebe atualizações de réplica por meio do agente replicador de réplica do Lync Server que é executado como um serviço em todos os computadores.</span><span class="sxs-lookup"><span data-stu-id="3548b-107">The local database receives replica updates by way of the Lync Server Replica Replicator Agent that runs as a service on all computers.</span></span> <span data-ttu-id="3548b-108">O nome do banco de dados real no servidor de gerenciamento central e na réplica local é XDS, que é composto pelos arquivos XDS. MDF e XDS. ldf.</span><span class="sxs-lookup"><span data-stu-id="3548b-108">The name of the actual database on the Central Management Server and the local replica is XDS, which is made up of the xds.mdf and xds.ldf files.</span></span> <span data-ttu-id="3548b-109">O local do banco de dados mestre é referenciado por um ponto de controle de serviço (SCP) nos serviços de domínio do Active Directory.</span><span class="sxs-lookup"><span data-stu-id="3548b-109">The master database location is referenced by a service control point (SCP) in Active Directory Domain Services.</span></span> <span data-ttu-id="3548b-110">Todas as ferramentas que usam o servidor de gerenciamento central para gerenciar e configurar o Lync Server usam o SCP para localizar o repositório de gerenciamento central.</span><span class="sxs-lookup"><span data-stu-id="3548b-110">All tools that use the Central Management Server to manage and configure Lync Server use the SCP to locate the Central Management store.</span></span>

<span data-ttu-id="3548b-111">Depois de mover com êxito o servidor de gerenciamento central, você deve remover os bancos de dados do servidor de gerenciamento central do servidor front-end original.</span><span class="sxs-lookup"><span data-stu-id="3548b-111">After you have successfully moved the Central Management Server, you should remove the Central Management Server databases from the original Front End Server.</span></span> <span data-ttu-id="3548b-112">Para obter informações sobre como remover os bancos de dados do servidor de gerenciamento central, consulte [remover o banco de dados do SQL Server para um pool de front-ends](remove-the-sql-server-database-for-a-front-end-pool.md).</span><span class="sxs-lookup"><span data-stu-id="3548b-112">For information on removing the Central Management Server databases, see [Remove the SQL Server database for a Front End pool](remove-the-sql-server-database-for-a-front-end-pool.md).</span></span>

<span data-ttu-id="3548b-113">Você usa o cmdlet **move-CsManagementServer** do Windows PowerShell no Shell de gerenciamento do Lync Server para mover o banco de dados do banco de dados do sql Server 2010 do Lync Server para o banco de dados do lync Server 2013 SQL Server e, em seguida, atualizar o scp para apontar para o local do servidor de gerenciamento central do lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="3548b-113">You use the Windows PowerShell cmdlet **Move-CsManagementServer** in the Lync Server Management Shell to move the database from the Lync Server 2010 SQL Server database to the Lync Server 2013 SQL Server database, and then update the SCP to point to the Lync Server 2013 Central Management Server location.</span></span>

<div>

## <a name="preparing-lync-server-2013front-end-servers-before-moving-the-central-management-server"></a><span data-ttu-id="3548b-114">Preparando servidores de front-end do Lync Server 2013 antes de mover o servidor de gerenciamento central</span><span class="sxs-lookup"><span data-stu-id="3548b-114">Preparing Lync Server 2013 Front End Servers before moving the Central Management Server</span></span>

<span data-ttu-id="3548b-115">Use os procedimentos desta seção para preparar os servidores front-end do Lync Server 2013 antes de mover o servidor de gerenciamento central do Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="3548b-115">Use the procedures in this section to prepare the Lync Server 2013 Front End Servers before you move the Lync Server 2010 Central Management Server.</span></span>

<div>

## <a name="to-prepare-an-enterprise-edition-front-end-pool"></a><span data-ttu-id="3548b-116">Para preparar um pool de front-ends Enterprise Edition</span><span class="sxs-lookup"><span data-stu-id="3548b-116">To prepare an Enterprise Edition Front End pool</span></span>

1.  <span data-ttu-id="3548b-117">No pool de front-ends do Lync Server 2013 Enterprise Edition onde você deseja realocar o servidor de gerenciamento central: faça logon no computador onde o Shell de gerenciamento do Lync Server está instalado como membro do grupo **RTCUniversalServerAdmins** .</span><span class="sxs-lookup"><span data-stu-id="3548b-117">On the Lync Server 2013 Enterprise Edition Front End pool where you want to relocate the Central Management Server: Log on to the computer where the Lync Server Management Shell is installed as a member of the **RTCUniversalServerAdmins** group.</span></span> <span data-ttu-id="3548b-118">Você também deve ter direitos e permissões de usuário sysadmin do SQL Server no banco de dados onde você deseja instalar o repositório de gerenciamento central.</span><span class="sxs-lookup"><span data-stu-id="3548b-118">You must also have SQL Server database sysadmin user rights and permissions on the database where you want to install the Central Management store.</span></span>

2.  <span data-ttu-id="3548b-119">Abra o Shell de Gerenciamento do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="3548b-119">Open the Lync Server Management Shell.</span></span>

3.  <span data-ttu-id="3548b-120">Para criar o novo repositório de gerenciamento central no banco de dados do SQL Server do Lync Server 2013, no Shell de gerenciamento do Lync Server, digite:</span><span class="sxs-lookup"><span data-stu-id="3548b-120">To create the new Central Management store in the Lync Server 2013 SQL Server database, in the Lync Server Management Shell, type:</span></span>
    
        Install-CsDatabase -CentralManagementDatabase -SQLServerFQDN <FQDN of your SQL Server> -SQLInstanceName <name of instance>

4.  <span data-ttu-id="3548b-121">Confirme que o status do serviço do **Front-End do Lync Server** é **Iniciado**.</span><span class="sxs-lookup"><span data-stu-id="3548b-121">Confirm that the status of the **Lync Server Front-End** service is **Started**.</span></span>

</div>

<div>

## <a name="to-prepare-a-standard-edition-front-end-server"></a><span data-ttu-id="3548b-122">Para preparar um servidor front-end Standard Edition</span><span class="sxs-lookup"><span data-stu-id="3548b-122">To prepare a Standard Edition Front End Server</span></span>

1.  <span data-ttu-id="3548b-123">No servidor front-end do Lync Server 2013 Standard Edition onde você deseja realocar o servidor de gerenciamento central: faça logon no computador onde o Shell de gerenciamento do Lync Server está instalado como um membro do grupo **RTCUniversalServerAdmins** .</span><span class="sxs-lookup"><span data-stu-id="3548b-123">On the Lync Server 2013 Standard Edition Front End Server where you want to relocate the Central Management Server: Log on to the computer where the Lync Server Management Shell is installed as a member of the **RTCUniversalServerAdmins** group.</span></span>

2.  <span data-ttu-id="3548b-124">Abra o assistente de implantação do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="3548b-124">Open the Lync Server Deployment Wizard.</span></span>

3.  <span data-ttu-id="3548b-125">No assistente de implantação do Lync Server, clique em **preparar primeiro servidor Standard Edition**.</span><span class="sxs-lookup"><span data-stu-id="3548b-125">In the Lync Server Deployment Wizard, click **Prepare first Standard Edition server**.</span></span>

4.  <span data-ttu-id="3548b-126">Na página **executando comandos** , o SQL Server Express é instalado como o servidor de gerenciamento central.</span><span class="sxs-lookup"><span data-stu-id="3548b-126">On the **Executing Commands** page, SQL Server Express is installed as the Central Management Server.</span></span> <span data-ttu-id="3548b-127">Regras de firewall necessárias são criadas.</span><span class="sxs-lookup"><span data-stu-id="3548b-127">Necessary firewall rules are created.</span></span> <span data-ttu-id="3548b-128">Quando a instalação do banco de dados e software de pré-requisito estiver concluída, clique em **Finalizar**.</span><span class="sxs-lookup"><span data-stu-id="3548b-128">When the installation of the database and prerequisite software is completed, click **Finish**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="3548b-129">A instalação inicial pode levar algum tempo sem nenhuma atualização visível na tela de resumo de saída do comando.</span><span class="sxs-lookup"><span data-stu-id="3548b-129">The initial installation may take some time with no visible updates to the command output summary screen.</span></span> <span data-ttu-id="3548b-130">Isso ocorre devido à instalação do SQL Server Express.</span><span class="sxs-lookup"><span data-stu-id="3548b-130">This is due to the installation of the SQL Server Express.</span></span> <span data-ttu-id="3548b-131">Se você precisa monitorar a instalação do banco de dados, use o Gerenciador de Tarefas para monitorar a configuração.</span><span class="sxs-lookup"><span data-stu-id="3548b-131">If you need to monitor the installation of the database, use Task Manager to monitor the setup.</span></span>

    
    </div>

5.  <span data-ttu-id="3548b-132">Para criar o novo repositório de gerenciamento central no servidor front-end do Lync Server 2013 Standard Edition, no Shell de gerenciamento do Lync Server, digite:</span><span class="sxs-lookup"><span data-stu-id="3548b-132">To create the new Central Management store on the Lync Server 2013 Standard Edition Front End Server, in the Lync Server Management Shell, type:</span></span>
    
        Install-CsDatabase -CentralManagementDatabase -SQLServerFQDN <FQDN of your Standard Edition Server> -SQLInstanceName <name of instance - RTC by default>

6.  <span data-ttu-id="3548b-133">Confirme que o status do serviço do **Front-End do Lync Server** é **Iniciado**.</span><span class="sxs-lookup"><span data-stu-id="3548b-133">Confirm that the status of the **Lync Server Front-End** service is **Started**.</span></span>

</div>

</div>

<div>

## <a name="to-move-the-lync-server-2010central-management-server-to-lync-server-2013"></a><span data-ttu-id="3548b-134">Para mover o servidor de gerenciamento central do Lync Server 2010 para o Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3548b-134">To move the Lync Server 2010 Central Management Server to Lync Server 2013</span></span>

1.  <span data-ttu-id="3548b-135">No servidor do Lync Server 2013 que será o servidor de gerenciamento central: faça logon no computador onde o Shell de gerenciamento do Lync Server está instalado como um membro do grupo **RTCUniversalServerAdmins** .</span><span class="sxs-lookup"><span data-stu-id="3548b-135">On the Lync Server 2013 server that will be the Central Management Server: Log on to the computer where the Lync Server Management Shell is installed as a member of the **RTCUniversalServerAdmins** group.</span></span> <span data-ttu-id="3548b-136">Você também deve ter direitos e permissões do usuário administrador do banco de dados do SQL Server.</span><span class="sxs-lookup"><span data-stu-id="3548b-136">You must also have the SQL Server database administrator user rights and permissions.</span></span>

2.  <span data-ttu-id="3548b-137">Abra o Shell de gerenciamento do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="3548b-137">Open Lync Server Management Shell.</span></span>

3.  <span data-ttu-id="3548b-138">No Shell de gerenciamento do Lync Server, digite:</span><span class="sxs-lookup"><span data-stu-id="3548b-138">In the Lync Server Management Shell, type:</span></span>
    
        Enable-CsTopology
    
    <div>
    

    > [!WARNING]  
    > <span data-ttu-id="3548b-139">Se <CODE>Enable-CsTopology</CODE> o não for bem-sucedido, resolva o problema que impede o comando de concluir antes de continuar.</span><span class="sxs-lookup"><span data-stu-id="3548b-139">If <CODE>Enable-CsTopology</CODE> is not successful, resolve the problem preventing the command from completing before continuing.</span></span> <span data-ttu-id="3548b-140">Se <STRONG>Enable-CsTopology</STRONG> não for bem-sucedido, a movimentação falhará e poderá deixar sua topologia em um estado em que não haja repositório de gerenciamento central.</span><span class="sxs-lookup"><span data-stu-id="3548b-140">If <STRONG>Enable-CsTopology</STRONG> is not successful, the move will fail and it may leave your topology in a state where there is no Central Management store.</span></span>

    
    </div>

4.  <span data-ttu-id="3548b-141">No servidor front-end do Lync Server 2013 ou no pool de front-ends, no Shell de gerenciamento do Lync Server, digite:</span><span class="sxs-lookup"><span data-stu-id="3548b-141">On the Lync Server 2013 Front End Server or Front End pool, in the Lync Server Management Shell, type:</span></span>
    
        Move-CsManagementServer

5.  <span data-ttu-id="3548b-142">O Shell de gerenciamento do Lync Server exibe os servidores, repositórios de arquivos, repositórios de bancos de dados e os pontos de conexão de serviço do estado atual e o Estado proposto.</span><span class="sxs-lookup"><span data-stu-id="3548b-142">Lync Server Management Shell displays the servers, file stores, database stores, and the service connection points of the Current State and the Proposed State.</span></span> <span data-ttu-id="3548b-143">Leia as informações cuidadosamente e confirme que esta é a origem e o destino pretendido.</span><span class="sxs-lookup"><span data-stu-id="3548b-143">Read the information carefully and confirm that this is the intended source and destination.</span></span> <span data-ttu-id="3548b-144">Digite **Y** para continuar ou **N** para parar a movimentação.</span><span class="sxs-lookup"><span data-stu-id="3548b-144">Type **Y** to continue, or **N** to stop the move.</span></span>

6.  <span data-ttu-id="3548b-145">Revise qualquer aviso ou erro gerado pelo comando **Move-CsManagementServer** e resolva-os.</span><span class="sxs-lookup"><span data-stu-id="3548b-145">Review any warnings or errors generated by the **Move-CsManagementServer** command and resolve them.</span></span>

7.  <span data-ttu-id="3548b-146">No servidor do Lync Server 2013, abra o assistente de implantação do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="3548b-146">On the Lync Server 2013 server, open the Lync Server Deployment Wizard.</span></span>

8.  <span data-ttu-id="3548b-147">No assistente de implantação do Lync Server, clique em **instalar ou atualizar o sistema do Lync Server**, clique em **etapa 2: configurar ou remover componentes do Lync Server**, clique em **Avançar**, revise o resumo e clique em **concluir**.</span><span class="sxs-lookup"><span data-stu-id="3548b-147">In Lync Server Deployment Wizard, click **Install or Update Lync Server System**, click **Step 2: Setup or Remove Lync Server Components**, click **Next**, review the summary, and then click **Finish**.</span></span>

9.  <span data-ttu-id="3548b-148">No servidor do Lync Server 2010, abra o assistente de implantação do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="3548b-148">On the Lync Server 2010 server, open the Lync Server Deployment Wizard.</span></span>

10. <span data-ttu-id="3548b-149">No assistente de implantação do Lync Server, clique em **instalar ou atualizar o sistema do Lync Server**, clique em **etapa 2: configurar ou remover componentes do Lync Server**, clique em **Avançar**, revise o resumo e clique em **concluir**.</span><span class="sxs-lookup"><span data-stu-id="3548b-149">In Lync Server Deployment Wizard, click **Install or Update Lync Server System**, click **Step 2: Setup or Remove Lync Server Components**, click **Next**, review the summary, and then click **Finish**.</span></span>

11. <span data-ttu-id="3548b-150">Reinicialize o servidor do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="3548b-150">Reboot the Lync Server 2013 server.</span></span> <span data-ttu-id="3548b-151">Isso é necessário devido a uma alteração na associação de grupo para acessar o banco de dados do servidor de gerenciamento central.</span><span class="sxs-lookup"><span data-stu-id="3548b-151">This is required because of a group membership change to access Central Management Server database.</span></span>

12. <span data-ttu-id="3548b-152">Para confirmar se a replicação com o novo repositório de gerenciamento central está ocorrendo, no Shell de gerenciamento do Lync Server, digite:</span><span class="sxs-lookup"><span data-stu-id="3548b-152">To confirm that replication with the new Central Management store is occurring, in the Lync Server Management Shell, type:</span></span>
    
        Get-CsManagementStoreReplicationStatus
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="3548b-153">A replicação pode levar algum tempo para atualizar todas as réplicas atuais.</span><span class="sxs-lookup"><span data-stu-id="3548b-153">The replication may take some time to update all current replicas.</span></span>

    
    </div>

</div>

<div>

## <a name="to-remove-lync-server-2010central-management-store-files-after-a-move"></a><span data-ttu-id="3548b-154">Para remover os arquivos do repositório de gerenciamento central do Lync Server 2010 após uma movimentação</span><span class="sxs-lookup"><span data-stu-id="3548b-154">To remove Lync Server 2010 Central Management store files after a move</span></span>

1.  <span data-ttu-id="3548b-155">No servidor do Lync Server 2010: faça logon no computador onde o Shell de gerenciamento do Lync Server está instalado como um membro do grupo **RTCUniversalServerAdmins** .</span><span class="sxs-lookup"><span data-stu-id="3548b-155">On the Lync Server 2010 server: Log on to the computer where the Lync Server Management Shell is installed as a member of the **RTCUniversalServerAdmins** group.</span></span> <span data-ttu-id="3548b-156">Você também deve ter direitos e permissões do usuário administrador do banco de dados do SQL Server.</span><span class="sxs-lookup"><span data-stu-id="3548b-156">You must also have the SQL Server database administrator user rights and permissions.</span></span>

2.  <span data-ttu-id="3548b-157">Abrir o Shell de gerenciamento do Lync Server</span><span class="sxs-lookup"><span data-stu-id="3548b-157">Open Lync Server Management Shell</span></span>
    
    <div>
    

    > [!WARNING]  
    > <span data-ttu-id="3548b-158">Não continue com a remoção dos arquivos do banco de dados anteriores até que a replicação esteja concluída e estável.</span><span class="sxs-lookup"><span data-stu-id="3548b-158">Do not proceed with the removal of the previous database files until replication is complete and is stable.</span></span> <span data-ttu-id="3548b-159">Se você remover os arquivos antes de concluir a replicação, interromperá o processo de replicação e deixará o servidor de gerenciamento central recentemente movido em um estado desconhecido.</span><span class="sxs-lookup"><span data-stu-id="3548b-159">If you remove the files prior to completing replication, you will disrupt the replication process and leave the newly moved Central Management Server in an unknown state.</span></span> <span data-ttu-id="3548b-160">Use o cmdlet <STRONG>Get-CsManagementStoreReplicationStatus</STRONG> para confirmar o status da replicação.</span><span class="sxs-lookup"><span data-stu-id="3548b-160">Use the cmdlet <STRONG>Get-CsManagementStoreReplicationStatus</STRONG> to confirm the replication status.</span></span>

    
    </div>

3.  <span data-ttu-id="3548b-161">Para remover os arquivos do banco de dados do repositório de gerenciamento central do servidor de gerenciamento central do Lync Server 2010, digite:</span><span class="sxs-lookup"><span data-stu-id="3548b-161">To remove the Central Management store database files from the Lync Server 2010 Central Management Server, type:</span></span>
    
        Uninstall-CsDatabase -CentralManagementDatabase -SqlServerFqdn <FQDN of SQL Server> -SqlInstanceName <Name of source server>
    
    <span data-ttu-id="3548b-162">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="3548b-162">For example:</span></span>
    
        Uninstall-CsDatabase -CentralManagementDatabase -SqlServerFqdn sql.contoso.net -SqlInstanceName rtc
    
    <span data-ttu-id="3548b-163">Onde o \<FQDN do SQL Server\> é o servidor de Back-End do Lync Server 2010 em uma implantação Enterprise Edition ou o FQDN do servidor Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="3548b-163">Where the \<FQDN of SQL Server\> is either the Lync Server 2010 Back End Server in an Enterprise Edition deployment or the FQDN of the Standard Edition server.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

