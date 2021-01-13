---
title: Configurar alta disponibilidade e recuperação de desastre para o Servidor de Chat Persistente no Skype for Business Server 2015
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 2/7/2018
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 5fb5b189-56c1-49cf-92c8-e4fd6e2fdd5c
description: 'Resumo: Leia este tópico para saber como configurar a alta disponibilidade e a recuperação de desastres para o Servidor de Chat Persistente no Skype for Business Server 2015.'
ms.openlocfilehash: 0b58f820c1157da8ff36f8dcc68d9e08465bcddc
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49830621"
---
# <a name="configure-high-availability-and-disaster-recovery-for-persistent-chat-server-in-skype-for-business-server-2015"></a><span data-ttu-id="dc40e-103">Configurar alta disponibilidade e recuperação de desastre para o Servidor de Chat Persistente no Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="dc40e-103">Configure high availability and disaster recovery for Persistent Chat Server in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="dc40e-104">**Resumo:** Leia este tópico para saber como configurar a alta disponibilidade e a recuperação de desastres para o Servidor de Chat Persistente no Skype for Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="dc40e-104">**Summary:** Read this topic to learn how to configure high availability and disaster recovery for Persistent Chat Server in Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="dc40e-105">O Skype for Business Server oferece suporte a vários modos de alta disponibilidade para seus Servidores Back-End, incluindo espelhamento de banco de dados.</span><span class="sxs-lookup"><span data-stu-id="dc40e-105">Skype for Business Server supports multiple modes of high availability for your Back End Servers, including database mirroring.</span></span> <span data-ttu-id="dc40e-106">Para obter mais informações, [consulte Plan for high availability and disaster recovery in Skype for Business Server 2015.](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md)</span><span class="sxs-lookup"><span data-stu-id="dc40e-106">For more information, see [Plan for high availability and disaster recovery in Skype for Business Server 2015](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="dc40e-107">Os Grupos de Disponibilidade AlwaysOn não são suportados com Servidores de Chat Persistente.</span><span class="sxs-lookup"><span data-stu-id="dc40e-107">AlwaysOn Availability Groups are not supported with Persistent Chat Servers.</span></span> 
  
<span data-ttu-id="dc40e-108">Antes de configurar sua implantação de Chat Persistente para alta disponibilidade e recuperação de desastre, certifique-se de estar familiarizado com os conceitos em Planejar alta disponibilidade e recuperação de desastre para o Servidor de Chat Persistente no [Skype for Business Server 2015.](../../plan-your-deployment/persistent-chat-server/high-availability-and-disaster-recovery.md)</span><span class="sxs-lookup"><span data-stu-id="dc40e-108">Before you configure your Persistent Chat deployment for high availability and disaster recovery, be sure you are familiar with the concepts in [Plan for high availability and disaster recovery for Persistent Chat Server in Skype for Business Server 2015](../../plan-your-deployment/persistent-chat-server/high-availability-and-disaster-recovery.md).</span></span> <span data-ttu-id="dc40e-109">A solução de recuperação de desastre para o Servidor de Chat Persistente descrito nestes tópicos é criada em um pool estendido de Servidor de Chat Persistente.</span><span class="sxs-lookup"><span data-stu-id="dc40e-109">The disaster recovery solution for Persistent Chat Server described in these topics is built on a stretched Persistent Chat Server pool.</span></span> <span data-ttu-id="dc40e-110">O conteúdo de planejamento descreve os requisitos de recursos e a topologia de pool estendido que permite alta disponibilidade e recuperação de desastres para o Servidor de Chat Persistente, incluindo o uso do espelhamento do SQL Server para alta disponibilidade e envio de log do SQL Server para recuperação de desastres.</span><span class="sxs-lookup"><span data-stu-id="dc40e-110">The planning content describes resource requirements, and the stretched pool topology that enables high availability and disaster recovery for Persistent Chat Server, including using SQL Server mirroring for high availability and SQL Server log shipping for disaster recovery.</span></span>
  
## <a name="use-topology-builder-to-configure-high-availability-and-disaster-recovery"></a><span data-ttu-id="dc40e-111">Usar o Construtor de Topologias para configurar alta disponibilidade e recuperação de desastre</span><span class="sxs-lookup"><span data-stu-id="dc40e-111">Use Topology Builder to configure high availability and disaster recovery</span></span>

<span data-ttu-id="dc40e-112">No Construtor de Topologias, execute as seguintes etapas para configurar alta disponibilidade e recuperação de desastre para o Servidor de Chat Persistente.</span><span class="sxs-lookup"><span data-stu-id="dc40e-112">Within Topology Builder, perform the following steps to configure high availability and disaster recovery for Persistent Chat Server.</span></span>
  
1. <span data-ttu-id="dc40e-113">Adicione os bancos de dados espelho e os armazenamentos do SQL Server do banco de dados secundário de envio de log.</span><span class="sxs-lookup"><span data-stu-id="dc40e-113">Add the mirror databases and the log shipping secondary database SQL Server stores.</span></span>
    
2. <span data-ttu-id="dc40e-114">Edite as propriedades do serviço do Servidor de Chat Persistente para:</span><span class="sxs-lookup"><span data-stu-id="dc40e-114">Edit the Persistent Chat Server service properties to:</span></span>
    
    <span data-ttu-id="dc40e-115">a.</span><span class="sxs-lookup"><span data-stu-id="dc40e-115">a.</span></span> <span data-ttu-id="dc40e-116">Ativar espelhamento do banco de dados primário.</span><span class="sxs-lookup"><span data-stu-id="dc40e-116">Enable mirroring for the primary database.</span></span>
    
    <span data-ttu-id="dc40e-117">b.</span><span class="sxs-lookup"><span data-stu-id="dc40e-117">b.</span></span> <span data-ttu-id="dc40e-118">Adicione o armazenamento principal do SQL Server espelho.</span><span class="sxs-lookup"><span data-stu-id="dc40e-118">Add the primary mirror SQL Server store.</span></span>
    
    <span data-ttu-id="dc40e-119">c.</span><span class="sxs-lookup"><span data-stu-id="dc40e-119">c.</span></span> <span data-ttu-id="dc40e-120">Habilita o banco de dados de Envio de Log do SQL Server.</span><span class="sxs-lookup"><span data-stu-id="dc40e-120">Enable the SQL Server Log Shipping database.</span></span>
    
    <span data-ttu-id="dc40e-121">d.</span><span class="sxs-lookup"><span data-stu-id="dc40e-121">d.</span></span> <span data-ttu-id="dc40e-122">Adicione o armazenamento secundário do SQL Server envio de log do SQL Server.</span><span class="sxs-lookup"><span data-stu-id="dc40e-122">Add the SQL Server Log Shipping secondary SQL Server store.</span></span>
    
    <span data-ttu-id="dc40e-123">e.</span><span class="sxs-lookup"><span data-stu-id="dc40e-123">e.</span></span> <span data-ttu-id="dc40e-124">Adicione o espelho do armazenamento do SQL Server ao banco de dados secundário.</span><span class="sxs-lookup"><span data-stu-id="dc40e-124">Add the SQL Server store mirror for the secondary database.</span></span>
    
    <span data-ttu-id="dc40e-125">f.</span><span class="sxs-lookup"><span data-stu-id="dc40e-125">f.</span></span> <span data-ttu-id="dc40e-126">Publique a topologia.</span><span class="sxs-lookup"><span data-stu-id="dc40e-126">Publish the topology.</span></span>
    
## <a name="set-up-sql-server-log-shipping-for-the-persistent-chat-server-primary-database"></a><span data-ttu-id="dc40e-127">Configurar o envio de log do SQL Server para o banco de dados primário do Servidor de Chat Persistente</span><span class="sxs-lookup"><span data-stu-id="dc40e-127">Set up SQL Server log shipping for the Persistent Chat Server primary database</span></span>

<span data-ttu-id="dc40e-128">Usando o SQL Server Management Studio, conecte-se à instância secundária do banco de dados de Envio de Log do Servidor de Chat Persistente e certifique-se de que o SQL Server Agent está em execução.</span><span class="sxs-lookup"><span data-stu-id="dc40e-128">Using SQL Server Management Studio, connect to the Persistent Chat Server secondary Log Shipping database instance, and be sure that SQL Server Agent is running.</span></span> <span data-ttu-id="dc40e-129">Em seguida, conecte-se à instância do banco de dados primário de Chat Persistente e execute as seguintes etapas:</span><span class="sxs-lookup"><span data-stu-id="dc40e-129">Then connect to the Persistent Chat primary database instance and perform the following steps:</span></span>
  
1. <span data-ttu-id="dc40e-130">Clique com o botão direito no banco de dados mgc e, em seguida, clique em **Propriedades**.</span><span class="sxs-lookup"><span data-stu-id="dc40e-130">Right-click the mgc database, and then click **Properties**.</span></span>
    
2. <span data-ttu-id="dc40e-131">Em **Selecionar uma página**, clique em **Envio de Logs de Transações**.</span><span class="sxs-lookup"><span data-stu-id="dc40e-131">Under **Select a page**, click **Transaction Log Shipping**.</span></span>
    
3. <span data-ttu-id="dc40e-132">Selecione a caixa de seleção **Habilitar como banco de dados primário em uma configuração de envio de log**.</span><span class="sxs-lookup"><span data-stu-id="dc40e-132">Select the **Enable this as a primary database in a log shipping configuration** check box.</span></span>
    
4. <span data-ttu-id="dc40e-133">Em **Backups do log de transação**, clique em **Configurações de Backup**.</span><span class="sxs-lookup"><span data-stu-id="dc40e-133">Under **Transaction log backups**, click **Backup Settings**.</span></span>
    
5. <span data-ttu-id="dc40e-134">Na caixa **Caminho de rede para a pasta Backup**, digite o caminho de rede até o compartilhamento criado para a pasta de backup do log de transação.</span><span class="sxs-lookup"><span data-stu-id="dc40e-134">In the **Network path to the backup folder** box, type the network path to the share that you created for the transaction log backup folder.</span></span>
    
6. <span data-ttu-id="dc40e-p110">Se a pasta de backup estiver localizada no servidor primário, digite o caminho local até a pasta de backup na caixa **Se a pasta de backup estiver localizada no servidor primário, digite um caminho local para a pasta (exemplo: c:\backup)**. (Se a pasta backup não estiver no servidor primário, deixa essa caixa em branco.)</span><span class="sxs-lookup"><span data-stu-id="dc40e-p110">If the backup folder is located on the primary server, type the local path to the backup folder in the **If the backup folder is located on the primary server, type a local path to the folder (example: c:\backup)** box. (If the backup folder is not on the primary server, you can leave this box empty.)</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="dc40e-137">Se a conta de serviço do SQL Server em seu servidor primário for executado sob a conta do sistema local, você deverá criar sua pasta de backup no servidor primário e especificar um caminho local para essa pasta.</span><span class="sxs-lookup"><span data-stu-id="dc40e-137">If the SQL Server service account on your primary server runs under the local system account, you must create your backup folder on the primary server and specify a local path to that folder.</span></span> 
  
7. <span data-ttu-id="dc40e-138">Configure os parâmetros **Excluir arquivos com mais de** e **Alertar se nenhum backup ocorrer em**.</span><span class="sxs-lookup"><span data-stu-id="dc40e-138">Configure the **Delete files older than** and **Alert if no backup occurs within** parameters.</span></span>
    
8. <span data-ttu-id="dc40e-139">Observe a agenda de backup listada na caixa de diálogo **Agendar** em **Trabalho de backup**.</span><span class="sxs-lookup"><span data-stu-id="dc40e-139">Look at the backup schedule listed in the **Schedule** box under **Backup job**.</span></span> <span data-ttu-id="dc40e-140">Para personalizar a agenda da instalação, clique em **Agendar** e ajuste a agenda do SQL Server Agent conforme necessário.</span><span class="sxs-lookup"><span data-stu-id="dc40e-140">To customize the schedule for your installation, click **Schedule**, and adjust the SQL Server Agent schedule as required.</span></span>
    
9. <span data-ttu-id="dc40e-141">Em **Compactação**, selecione **Usar a configuração padrão do servidor** e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="dc40e-141">Under **Compression**, select **Use the default server setting**, and then click **OK**.</span></span>
    
10. <span data-ttu-id="dc40e-142">Em **Instâncias e bancos de dados do servidor secundário**, clique em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="dc40e-142">Under **Secondary server instances and databases**, click **Add**.</span></span>
    
11. <span data-ttu-id="dc40e-143">Clique **em** Conectar e conecte-se à instância do SQL Server que você configurou como seu servidor secundário.</span><span class="sxs-lookup"><span data-stu-id="dc40e-143">Click **Connect** and connect to the instance of SQL Server that you have configured as your secondary server.</span></span>
    
12. <span data-ttu-id="dc40e-144">Na caixa de diálogo **Banco de dados secundário**, selecione o banco de dados **mgc** da lista.</span><span class="sxs-lookup"><span data-stu-id="dc40e-144">In the **Secondary Database** box, select the **mgc** database from the list.</span></span>
    
13. <span data-ttu-id="dc40e-145">Na guia **Inicializar** banco de dados secundário, escolha a opção Sim, gere um backup completo do banco de dados primário e restaure-o no banco de dados secundário (e crie o banco de dados secundário se ele não **existir).**</span><span class="sxs-lookup"><span data-stu-id="dc40e-145">On the **Initialize Secondary database** tab, choose the option **Yes, generate a full backup of the primary database and restore it into the secondary database (and create the secondary database if it doesn't exist)**.</span></span>
    
14. <span data-ttu-id="dc40e-p112">Na guia **Copiar Arquivos**, na caixa **Pasta de destino dos arquivos copiados**, digite o caminho da pasta na qual os backups de logs de transação devem ser copiadas. Normalmente, essa pasta está localizada no servidor secundário.</span><span class="sxs-lookup"><span data-stu-id="dc40e-p112">On the **Copy Files** tab, in the **Destination folder for copied files** box, type the path of the folder into which the transaction logs backups should be copied. This folder is often located on the secondary server.</span></span>
    
15. <span data-ttu-id="dc40e-148">Observe agenda de cópia listada na caixa **Agenda** em **Trabalho de cópia**.</span><span class="sxs-lookup"><span data-stu-id="dc40e-148">Note the copy schedule listed in the **Schedule** box under **Copy job**.</span></span> <span data-ttu-id="dc40e-149">Para personalizar a agenda da instalação, clique em **Agendar** e ajuste a agenda do SQL Server Agent conforme necessário.</span><span class="sxs-lookup"><span data-stu-id="dc40e-149">To customize the schedule for your installation, click **Schedule**, and adjust the SQL Server Agent schedule as required.</span></span> <span data-ttu-id="dc40e-150">Essa agenda deve ser quase a mesma que a agenda de backup.</span><span class="sxs-lookup"><span data-stu-id="dc40e-150">This schedule should be approximately the same as the backup schedule.</span></span>
    
16. <span data-ttu-id="dc40e-151">Na guia **Restauração**, em **Estado do banco de dados ao restaurar backups**, escolha a opção **Nenhum modo de recuperação**.</span><span class="sxs-lookup"><span data-stu-id="dc40e-151">On the **Restore** tab, under **Database state when restoring backups**, choose the **No recovery mode** option.</span></span>
    
17. <span data-ttu-id="dc40e-152">Em **Atrasar restauração de backups pelo menos:**, selecione **0 minutos**.</span><span class="sxs-lookup"><span data-stu-id="dc40e-152">Under **Delay restoring backups at least:**, select **0 minutes**.</span></span>
    
18. <span data-ttu-id="dc40e-153">Escolha um limite de alerta sob **Alertar se nenhuma restauração ocorrer em**.</span><span class="sxs-lookup"><span data-stu-id="dc40e-153">Choose an alert threshold under **Alert if no restore occurs within**.</span></span>
    
19. <span data-ttu-id="dc40e-154">Observe a agenda de restauração listada na caixa **Agenda** em **Trabalho de restauração**.</span><span class="sxs-lookup"><span data-stu-id="dc40e-154">Look at the restore schedule listed in the **Schedule** box under **Restore job**.</span></span> <span data-ttu-id="dc40e-155">Para personalizar a agenda da instalação, clique **em** Agendar, ajuste a agenda do SQL Server Agent conforme necessário e clique em **OK.**</span><span class="sxs-lookup"><span data-stu-id="dc40e-155">To customize the schedule for your installation, click **Schedule**, adjust the SQL Server Agent schedule as required, and click **OK**.</span></span> <span data-ttu-id="dc40e-156">Essa agenda deve ser quase a mesma que a agenda de backup.</span><span class="sxs-lookup"><span data-stu-id="dc40e-156">This schedule should be approximately the same as the backup schedule.</span></span>
    
20. <span data-ttu-id="dc40e-157">Na caixa de diálogo **Propriedades do Banco de Dados**, clique em **OK** para começar o processo de configuração.</span><span class="sxs-lookup"><span data-stu-id="dc40e-157">On the **Database Properties** dialog box, click **OK** to begin the configuration process.</span></span>
    
## <a name="set-up-sql-server-log-shipping-between-the-primary-mirror-and-the-secondary-database"></a><span data-ttu-id="dc40e-158">Configurar o envio de log do SQL Server entre o espelho primário e o banco de dados secundário</span><span class="sxs-lookup"><span data-stu-id="dc40e-158">Set up SQL Server log shipping between the primary mirror and the secondary database</span></span>

<span data-ttu-id="dc40e-159">Execute as etapas a seguir para que o envio de log continue se o banco de dados de Chat Persistente primário for failed over para seu banco de dados espelho.</span><span class="sxs-lookup"><span data-stu-id="dc40e-159">Perform the following steps for log shipping to continue if the primary Persistent Chat database is failed over to its mirror database.</span></span>
  
1. <span data-ttu-id="dc40e-160">Fail over the primary Persistent Chat database to the mirror.</span><span class="sxs-lookup"><span data-stu-id="dc40e-160">Manually fail over the primary Persistent Chat database to the mirror.</span></span> <span data-ttu-id="dc40e-161">Isso é feito usando o Shell de Gerenciamento do Skype for Business Server e o cmdlet **Invoke-CsDatabaseFailover.**</span><span class="sxs-lookup"><span data-stu-id="dc40e-161">This is done by using the Skype for Business Server Management Shell and the **Invoke-CsDatabaseFailover** cmdlet.</span></span>
    
2. <span data-ttu-id="dc40e-162">Usando o SQL Server Management Studio, conecte-se à instância de espelho principal do Servidor de Chat Persistente.</span><span class="sxs-lookup"><span data-stu-id="dc40e-162">Using the SQL Server Management Studio, connect to the primary Persistent Chat Server mirror instance.</span></span>
    
3. <span data-ttu-id="dc40e-163">Certifique-se de que o SQL Server Agent está em execução.</span><span class="sxs-lookup"><span data-stu-id="dc40e-163">Be sure that the SQL Server Agent is running.</span></span>
    
4. <span data-ttu-id="dc40e-164">Clique com o botão direito no banco de dados mgc e, em seguida, clique em **Propriedades**.</span><span class="sxs-lookup"><span data-stu-id="dc40e-164">Right-click the mgc database, and then click **Properties**.</span></span>
    
5. <span data-ttu-id="dc40e-165">Em **Selecionar uma página**, clique em **Envio de Logs de Transações**.</span><span class="sxs-lookup"><span data-stu-id="dc40e-165">Under **Select a page**, click **Transaction Log Shipping**.</span></span>
    
6. <span data-ttu-id="dc40e-166">Selecione a caixa de seleção **Habilitar como banco de dados primário em uma configuração de envio de log**.</span><span class="sxs-lookup"><span data-stu-id="dc40e-166">Select the **Enable this as a primary database in a log shipping configuration** check box.</span></span>
    
7. <span data-ttu-id="dc40e-167">Em **Backups de log de transações**, clique em **Configurações de Backup**.</span><span class="sxs-lookup"><span data-stu-id="dc40e-167">Under **Transaction log backups**, click **Backup Settings**.</span></span>
    
8. <span data-ttu-id="dc40e-168">Na caixa de diálogo **Caminho de rede para a pasta Backup**, digite o caminho de rede para compartilhamento que você criou para a pasta backup de log de transação.</span><span class="sxs-lookup"><span data-stu-id="dc40e-168">In the **Network path to the backup folder** box, type the network path to the share you created for the transaction log backup folder.</span></span>
    
9. <span data-ttu-id="dc40e-p116">Se a pasta de backup estiver no servidor primário, digite o caminho local na pasta de backup na caixa de diálogo **Se a pasta de backup estiver localizada no servidor primário, digite um caminho local para a pasta**. (Se a pasta de backup não estiver o servidor primário, você pode deixa essa caixa de diálogo vazia.)</span><span class="sxs-lookup"><span data-stu-id="dc40e-p116">If the backup folder is located on the primary server, type the local path to the backup folder in the **If the backup folder is located on the primary server, type a local path to the folder** box. (If the backup folder is not on the primary server, you can leave this box empty.)</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="dc40e-171">Se a conta de serviço do SQL Server em seu servidor primário for executado sob a conta do sistema local, você deverá criar sua pasta de backup no servidor primário e especificar um caminho local para essa pasta.</span><span class="sxs-lookup"><span data-stu-id="dc40e-171">If the SQL Server service account on your primary server runs under the local system account, you must create your backup folder on the primary server and specify a local path to that folder.</span></span> 
  
10. <span data-ttu-id="dc40e-172">Configure os parâmetros **Excluir arquivos com mais de** e **Alertar se nenhum backup ocorrer em**.</span><span class="sxs-lookup"><span data-stu-id="dc40e-172">Configure the **Delete files older than** and **Alert if no backup occurs within** parameters.</span></span>
    
11. <span data-ttu-id="dc40e-173">Observe a agenda de backup listada na caixa de diálogo **Agendar** em **Trabalho de backup**.</span><span class="sxs-lookup"><span data-stu-id="dc40e-173">Look at the backup schedule listed in the **Schedule** box under **Backup job**.</span></span> <span data-ttu-id="dc40e-174">Para personalizar a agenda da instalação, clique em **Agendar** e ajuste a agenda do SQL Server Agent, conforme necessário.</span><span class="sxs-lookup"><span data-stu-id="dc40e-174">To customize the schedule for your installation, click **Schedule**, and adjust the SQL Server Agent schedule, as required.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="dc40e-175">Use as mesmas configurações que você usou para o banco de dados primário.</span><span class="sxs-lookup"><span data-stu-id="dc40e-175">Use the same settings that you used for the primary database.</span></span> 
  
12. <span data-ttu-id="dc40e-176">Em **Compactação**, selecione **Usar a configuração padrão do servidor** e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="dc40e-176">Under **Compression**, select **Use the default server setting**, and click **OK**.</span></span>
    
13. <span data-ttu-id="dc40e-177">Em **Instâncias e bancos de dados do servidor secundário**, clique em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="dc40e-177">Under **Secondary server instances and databases**, click **Add**.</span></span>
    
14. <span data-ttu-id="dc40e-178">Clique **Conectar** e conecte-se na instância do SQL Server que você configurou como servidor secundário.</span><span class="sxs-lookup"><span data-stu-id="dc40e-178">Click **Connect**, and connect to the instance of SQL Server that you have configured as your secondary server.</span></span>
    
15. <span data-ttu-id="dc40e-179">Na caixa de diálogo **Banco de dados secundário**, selecione o banco de dados **mgc** da lista.</span><span class="sxs-lookup"><span data-stu-id="dc40e-179">In the **Secondary Database** box, select the **mgc** database from the list.</span></span>
    
16. <span data-ttu-id="dc40e-180">Na guia **Inicializar Banco de Dados Secundário**, selecione a opção **Não, o banco de dados secundário é inicializado**.</span><span class="sxs-lookup"><span data-stu-id="dc40e-180">On the **Initialize Secondary database** tab, select the option **No, the secondary database is initialized**.</span></span>
    
17. <span data-ttu-id="dc40e-p118">Na guia **Copiar Arquivos**, em **Pasta de destino dos arquivos copiados**, digite o caminho da pasta à qual a o backup de logs de transação deveriam ser copiados e clique em **OK**. Essa pasta normalmente se encontra no servidor secundário.</span><span class="sxs-lookup"><span data-stu-id="dc40e-p118">On the **Copy Files** tab, in **Destination folder for copied files**, type the path of the folder into which the transaction logs backups should be copied, and click **OK**. This folder is often located on the secondary server.</span></span>
    
18. <span data-ttu-id="dc40e-183">Abra a lista suspensa **Configuração do Script** e selecione **Configuração de Script na Janela Nova Consulta**.</span><span class="sxs-lookup"><span data-stu-id="dc40e-183">Open the **Script Configuration** drop-down list, and select **Script Configuration to New Query Window**.</span></span>
    
19. <span data-ttu-id="dc40e-184">Na nova janela de consulta, em **Propriedades do Banco de Dados**, clique em **OK** para iniciar o processo de configuração.</span><span class="sxs-lookup"><span data-stu-id="dc40e-184">In the new query window, in **Database Properties**, click **OK** to begin the configuration process.</span></span>
    
20. <span data-ttu-id="dc40e-185">Selecione e execute a primeira metade da consulta (veja a etapa 18) até a linha: -- Fim: script a ser executado \* \* \* \* \* \* no Primário: \* \* \* \* \* \* .</span><span class="sxs-lookup"><span data-stu-id="dc40e-185">Select and run the first half of the query (see step 18) up to the line: -- \*\*\*\*\*\* End: Script to be run at Primary: \*\*\*\*\*\*.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="dc40e-186">A execução manual desse script é necessária porque o SQL Server Management Studio não dá suporte a vários bancos de dados primários em uma configuração de Envio de Log do SQL Server.</span><span class="sxs-lookup"><span data-stu-id="dc40e-186">Manually running this script is necessary because SQL Server Management Studio does not support multiple primary databases in a SQL Server Log Shipping configuration.</span></span> 
  
21. <span data-ttu-id="dc40e-187">Selecione **Cancelar** para fechar o painel de configuração de envio do Arquivo de Log e para estabelecer uma configuração de trabalho que implemente corretamente o envio do arquivo de log para os bancos de dados primário e espelhado (no case de failover).</span><span class="sxs-lookup"><span data-stu-id="dc40e-187">Select **Cancel** to close the Log File shipping configuration panel and to establish a working setup that correctly implements the log file shipping for both the primary and mirrored database (in case of failover).</span></span>
    
22. <span data-ttu-id="dc40e-188">Fail back manual do banco de dados de Chat Persistente primário para o primário.</span><span class="sxs-lookup"><span data-stu-id="dc40e-188">Manually fail back the primary Persistent Chat database to the primary.</span></span> <span data-ttu-id="dc40e-189">Isso é feito usando o Shell de Gerenciamento do Skype for Business Server e o cmdlet **Invoke-CsDatabaseFailover.**</span><span class="sxs-lookup"><span data-stu-id="dc40e-189">This is done by using the Skype for Business Server Management Shell, and the **Invoke-CsDatabaseFailover** cmdlet.</span></span>
    

