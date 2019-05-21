---
title: Configurar a alta disponibilidade e a recuperação de desastres para o Servidor de Chat Persistente no Skype for Business Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/7/2018
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 5fb5b189-56c1-49cf-92c8-e4fd6e2fdd5c
description: 'Resumo: Leia este tópico para saber como configurar a alta disponibilidade e a recuperação de desastres para o servidor de chat persistente no Skype for Business Server 2015.'
ms.openlocfilehash: 152797229dc02bfcd1991a9ac6f67370c9154593
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34282291"
---
# <a name="configure-high-availability-and-disaster-recovery-for-persistent-chat-server-in-skype-for-business-server-2015"></a><span data-ttu-id="7ea4e-103">Configurar a alta disponibilidade e a recuperação de desastres para o Servidor de Chat Persistente no Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="7ea4e-103">Configure high availability and disaster recovery for Persistent Chat Server in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="7ea4e-104">**Resumo:** Leia este tópico para saber como configurar a alta disponibilidade e a recuperação de desastres para o servidor de chat persistente no Skype for Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="7ea4e-104">**Summary:** Read this topic to learn how to configure high availability and disaster recovery for Persistent Chat Server in Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="7ea4e-105">O Skype for Business Server oferece suporte a vários modos de alta disponibilidade para seus servidores back-end, incluindo o espelhamento de banco de dados.</span><span class="sxs-lookup"><span data-stu-id="7ea4e-105">Skype for Business Server supports multiple modes of high availability for your Back End Servers, including database mirroring.</span></span> <span data-ttu-id="7ea4e-106">Para obter mais informações, veja [Plan for high availability and disaster recovery in Skype for Business Server 2015](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md).</span><span class="sxs-lookup"><span data-stu-id="7ea4e-106">For more information, see [Plan for high availability and disaster recovery in Skype for Business Server 2015](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="7ea4e-107">Os grupos de disponibilidade AlwaysOn não são compatíveis com servidores de chat persistentes.</span><span class="sxs-lookup"><span data-stu-id="7ea4e-107">AlwaysOn Availability Groups are not supported with Persistent Chat Servers.</span></span> 

> [!NOTE] 
> <span data-ttu-id="7ea4e-108">O chat persistente está disponível no Skype for Business Server 2015, mas não é mais compatível com o Skype for Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="7ea4e-108">Persistent chat is available in Skype for Business Server 2015 but is no longer supported in Skype for Business Server 2019.</span></span> <span data-ttu-id="7ea4e-109">A mesma funcionalidade está disponível no Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="7ea4e-109">The same functionality is available in Teams.</span></span> <span data-ttu-id="7ea4e-110">Para obter mais informações, consulte [jornada do Skype for Business para o Microsoft Teams](/microsoftteams/journey-skypeforbusiness-teams).</span><span class="sxs-lookup"><span data-stu-id="7ea4e-110">For more information, see [Journey from Skype for Business to Microsoft Teams](/microsoftteams/journey-skypeforbusiness-teams).</span></span> <span data-ttu-id="7ea4e-111">Se você precisar usar chats persistentes, suas opções serão migrar os usuários que exigem essa funcionalidade para o Microsoft Teams ou para continuar usando o Skype for Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="7ea4e-111">If you need to use Persistent chat, your choices are to either migrate users requiring this functionality to Teams, or to continue using Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="7ea4e-112">Antes de configurar a implantação de chat persistente para alta disponibilidade e recuperação de desastres, certifique-se de que você esteja familiarizado com os conceitos do [plano para alta disponibilidade e recuperação de desastres para servidor de chat persistente no Skype for Business Server 2015](../../plan-your-deployment/persistent-chat-server/high-availability-and-disaster-recovery.md).</span><span class="sxs-lookup"><span data-stu-id="7ea4e-112">Before you configure your Persistent Chat deployment for high availability and disaster recovery, be sure you are familiar with the concepts in [Plan for high availability and disaster recovery for Persistent Chat Server in Skype for Business Server 2015](../../plan-your-deployment/persistent-chat-server/high-availability-and-disaster-recovery.md).</span></span> <span data-ttu-id="7ea4e-113">A solução de recuperação de desastres para servidor de chat persistente descrito nestes tópicos foi criada em um pool de servidores de chat persistentes ampliados.</span><span class="sxs-lookup"><span data-stu-id="7ea4e-113">The disaster recovery solution for Persistent Chat Server described in these topics is built on a stretched Persistent Chat Server pool.</span></span> <span data-ttu-id="7ea4e-114">O conteúdo de planejamento descreve os requisitos do recurso e a topologia de pool ampliada que permite alta disponibilidade e recuperação de desastre para o servidor de chat persistente, incluindo o uso do espelhamento do SQL Server para alta disponibilidade e envio de log do SQL Server para recuperação de desastres.</span><span class="sxs-lookup"><span data-stu-id="7ea4e-114">The planning content describes resource requirements, and the stretched pool topology that enables high availability and disaster recovery for Persistent Chat Server, including using SQL Server mirroring for high availability and SQL Server log shipping for disaster recovery.</span></span>
  
## <a name="use-topology-builder-to-configure-high-availability-and-disaster-recovery"></a><span data-ttu-id="7ea4e-115">Uso do Construtor de Topologias para configurar alta disponibilidade e recuperação de desastre</span><span class="sxs-lookup"><span data-stu-id="7ea4e-115">Use Topology Builder to configure high availability and disaster recovery</span></span>

<span data-ttu-id="7ea4e-116">No Construtor de Topologias, execute as seguintes etapas para configurar alta disponibilidade e recuperação de desastre para Servidor de Chat Persistente.</span><span class="sxs-lookup"><span data-stu-id="7ea4e-116">Within Topology Builder, perform the following steps to configure high availability and disaster recovery for Persistent Chat Server.</span></span>
  
1. <span data-ttu-id="7ea4e-117">Adicione os bancos de dados espelho e os repositórios secundários do banco de dados do SQL Server de envio de log.</span><span class="sxs-lookup"><span data-stu-id="7ea4e-117">Add the mirror databases and the log shipping secondary database SQL Server stores.</span></span>
    
2. <span data-ttu-id="7ea4e-118">Edite as propriedades do serviço do servidor de chat persistente para:</span><span class="sxs-lookup"><span data-stu-id="7ea4e-118">Edit the Persistent Chat Server service properties to:</span></span>
    
    <span data-ttu-id="7ea4e-119">a.</span><span class="sxs-lookup"><span data-stu-id="7ea4e-119">a.</span></span> <span data-ttu-id="7ea4e-120">Ativar o espelhamento do banco de dados primário.</span><span class="sxs-lookup"><span data-stu-id="7ea4e-120">Enable mirroring for the primary database.</span></span>
    
    <span data-ttu-id="7ea4e-121">b.</span><span class="sxs-lookup"><span data-stu-id="7ea4e-121">b.</span></span> <span data-ttu-id="7ea4e-122">Adicione a loja principal do SQL Server do espelho.</span><span class="sxs-lookup"><span data-stu-id="7ea4e-122">Add the primary mirror SQL Server store.</span></span>
    
    <span data-ttu-id="7ea4e-123">c.</span><span class="sxs-lookup"><span data-stu-id="7ea4e-123">c.</span></span> <span data-ttu-id="7ea4e-124">Habilite o banco de dados de envio de log do SQL Server.</span><span class="sxs-lookup"><span data-stu-id="7ea4e-124">Enable the SQL Server Log Shipping database.</span></span>
    
    <span data-ttu-id="7ea4e-125">d.</span><span class="sxs-lookup"><span data-stu-id="7ea4e-125">d.</span></span> <span data-ttu-id="7ea4e-126">Adicione o repositório do SQL Server secundário de envio de logs do SQL Server.</span><span class="sxs-lookup"><span data-stu-id="7ea4e-126">Add the SQL Server Log Shipping secondary SQL Server store.</span></span>
    
    <span data-ttu-id="7ea4e-127">vocálico.</span><span class="sxs-lookup"><span data-stu-id="7ea4e-127">e.</span></span> <span data-ttu-id="7ea4e-128">Adicione o espelho do SQL Server Store para o banco de dados secundário.</span><span class="sxs-lookup"><span data-stu-id="7ea4e-128">Add the SQL Server store mirror for the secondary database.</span></span>
    
    <span data-ttu-id="7ea4e-129">letra.</span><span class="sxs-lookup"><span data-stu-id="7ea4e-129">f.</span></span> <span data-ttu-id="7ea4e-130">Publique a topologia.</span><span class="sxs-lookup"><span data-stu-id="7ea4e-130">Publish the topology.</span></span>
    
## <a name="set-up-sql-server-log-shipping-for-the-persistent-chat-server-primary-database"></a><span data-ttu-id="7ea4e-131">Configuração do envio de logs do SQL Server para o banco de dados primário do Servidor de Chat Persistente</span><span class="sxs-lookup"><span data-stu-id="7ea4e-131">Set up SQL Server log shipping for the Persistent Chat Server primary database</span></span>

<span data-ttu-id="7ea4e-132">Usando o SQL Server Management Studio, conecte-se à instância do banco de dados de envio de log secundário do servidor de chat persistente e certifique-se de que o agente do SQL Server esteja em execução.</span><span class="sxs-lookup"><span data-stu-id="7ea4e-132">Using SQL Server Management Studio, connect to the Persistent Chat Server secondary Log Shipping database instance, and be sure that SQL Server Agent is running.</span></span> <span data-ttu-id="7ea4e-133">Em seguida, conecte-se à instância do banco de dados primário de chat persistente e execute as seguintes etapas:</span><span class="sxs-lookup"><span data-stu-id="7ea4e-133">Then connect to the Persistent Chat primary database instance and perform the following steps:</span></span>
  
1. <span data-ttu-id="7ea4e-134">Clique com o botão direito do mouse no banco de dados mgc e, em seguida, clique em **Propriedades**.</span><span class="sxs-lookup"><span data-stu-id="7ea4e-134">Right-click the mgc database, and then click **Properties**.</span></span>
    
2. <span data-ttu-id="7ea4e-135">Em **Selecionar uma página**, clique em **Envio de Logs de Transação**.</span><span class="sxs-lookup"><span data-stu-id="7ea4e-135">Under **Select a page**, click **Transaction Log Shipping**.</span></span>
    
3. <span data-ttu-id="7ea4e-136">Marque a caixa de seleção **Habilitar como banco de dados primário em uma configuração de envio de logs**.</span><span class="sxs-lookup"><span data-stu-id="7ea4e-136">Select the **Enable this as a primary database in a log shipping configuration** check box.</span></span>
    
4. <span data-ttu-id="7ea4e-137">Em **Backups de log de transação**, clique em **Configurações de Backup**.</span><span class="sxs-lookup"><span data-stu-id="7ea4e-137">Under **Transaction log backups**, click **Backup Settings**.</span></span>
    
5. <span data-ttu-id="7ea4e-138">Na caixa **Caminho de rede para a pasta de backup**, digite o caminho de rede até o compartilhamento criado para a pasta de backup de log de transação.</span><span class="sxs-lookup"><span data-stu-id="7ea4e-138">In the **Network path to the backup folder** box, type the network path to the share that you created for the transaction log backup folder.</span></span>
    
6. <span data-ttu-id="7ea4e-p111">Se a pasta de backup estiver localizada no servidor primário, digite o caminho local até a pasta de backup na caixa **Se a pasta de backup estiver localizada no servidor primário, digite um caminho local para a pasta (exemplo: c:\backup)**. (Se a pasta de backup não estiver no servidor primário, deixe essa caixa em branco.)</span><span class="sxs-lookup"><span data-stu-id="7ea4e-p111">If the backup folder is located on the primary server, type the local path to the backup folder in the **If the backup folder is located on the primary server, type a local path to the folder (example: c:\backup)** box. (If the backup folder is not on the primary server, you can leave this box empty.)</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="7ea4e-141">Se a conta de serviço do SQL Server em seu servidor primário for executada na conta do sistema local, você deverá criar a pasta de backup no servidor primário e especificar um caminho local para essa pasta.</span><span class="sxs-lookup"><span data-stu-id="7ea4e-141">If the SQL Server service account on your primary server runs under the local system account, you must create your backup folder on the primary server and specify a local path to that folder.</span></span> 
  
7. <span data-ttu-id="7ea4e-142">Configure os parâmetros **Excluir arquivos com mais de** e **Alertar se nenhum backup ocorrer em**.</span><span class="sxs-lookup"><span data-stu-id="7ea4e-142">Configure the **Delete files older than** and **Alert if no backup occurs within** parameters.</span></span>
    
8. <span data-ttu-id="7ea4e-143">Observe a agenda de backup listada na caixa **Agenda** em **Trabalho de backup**.</span><span class="sxs-lookup"><span data-stu-id="7ea4e-143">Look at the backup schedule listed in the **Schedule** box under **Backup job**.</span></span> <span data-ttu-id="7ea4e-144">Para personalizar o cronograma da instalação, clique em **agendar**e ajuste o cronograma do agente do SQL Server conforme necessário.</span><span class="sxs-lookup"><span data-stu-id="7ea4e-144">To customize the schedule for your installation, click **Schedule**, and adjust the SQL Server Agent schedule as required.</span></span>
    
9. <span data-ttu-id="7ea4e-145">Em **Compactação**, selecione **Usar a configuração padrão do servidor** e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="7ea4e-145">Under **Compression**, select **Use the default server setting**, and then click **OK**.</span></span>
    
10. <span data-ttu-id="7ea4e-146">Em **Instâncias e bancos de dados do servidor secundário**, clique em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="7ea4e-146">Under **Secondary server instances and databases**, click **Add**.</span></span>
    
11. <span data-ttu-id="7ea4e-147">Clique em **conectar** e conecte-se à instância do SQL Server que você configurou como seu servidor secundário.</span><span class="sxs-lookup"><span data-stu-id="7ea4e-147">Click **Connect** and connect to the instance of SQL Server that you have configured as your secondary server.</span></span>
    
12. <span data-ttu-id="7ea4e-148">Na caixa **Banco de dados secundário**, selecione o banco de dados **mgc** da lista.</span><span class="sxs-lookup"><span data-stu-id="7ea4e-148">In the **Secondary Database** box, select the **mgc** database from the list.</span></span>
    
13. <span data-ttu-id="7ea4e-149">Na guia **Inicializar Banco de Dados Secundário**, escolha a opção **Sim, gerar um backup completo do banco de dados primário e restaurá-lo no banco de dados secundário (e criar o banco de dados secundário caso ele não exista)**.</span><span class="sxs-lookup"><span data-stu-id="7ea4e-149">On the **Initialize Secondary database** tab, choose the option **Yes, generate a full backup of the primary database and restore it into the secondary database (and create the secondary database if it doesn't exist)**.</span></span>
    
14. <span data-ttu-id="7ea4e-p113">Na guia **Copiar Arquivos**, na caixa **Pasta de destino dos arquivos copiados**, digite o caminho da pasta na qual os backups de logs de transação devem ser copiados. Normalmente, essa pasta está localizada no servidor secundário.</span><span class="sxs-lookup"><span data-stu-id="7ea4e-p113">On the **Copy Files** tab, in the **Destination folder for copied files** box, type the path of the folder into which the transaction logs backups should be copied. This folder is often located on the secondary server.</span></span>
    
15. <span data-ttu-id="7ea4e-152">Observe a agenda de cópia listada na caixa **Agenda** em **Trabalho de cópia**.</span><span class="sxs-lookup"><span data-stu-id="7ea4e-152">Note the copy schedule listed in the **Schedule** box under **Copy job**.</span></span> <span data-ttu-id="7ea4e-153">Para personalizar o cronograma da instalação, clique em **agendar**e ajuste o cronograma do agente do SQL Server conforme necessário.</span><span class="sxs-lookup"><span data-stu-id="7ea4e-153">To customize the schedule for your installation, click **Schedule**, and adjust the SQL Server Agent schedule as required.</span></span> <span data-ttu-id="7ea4e-154">Essa agenda deve ser praticamente igual à agenda de backup.</span><span class="sxs-lookup"><span data-stu-id="7ea4e-154">This schedule should be approximately the same as the backup schedule.</span></span>
    
16. <span data-ttu-id="7ea4e-155">Na guia **Restauração**, em **Estado do banco de dados ao restaurar backups**, escolha a opção **Nenhum modo de recuperação**.</span><span class="sxs-lookup"><span data-stu-id="7ea4e-155">On the **Restore** tab, under **Database state when restoring backups**, choose the **No recovery mode** option.</span></span>
    
17. <span data-ttu-id="7ea4e-156">Em **Atrasar restauração de backups pelo menos:**, selecione **0 minuto**.</span><span class="sxs-lookup"><span data-stu-id="7ea4e-156">Under **Delay restoring backups at least:**, select **0 minutes**.</span></span>
    
18. <span data-ttu-id="7ea4e-157">Escolha um limite de alerta em **Alertar se nenhuma restauração ocorrer em**.</span><span class="sxs-lookup"><span data-stu-id="7ea4e-157">Choose an alert threshold under **Alert if no restore occurs within**.</span></span>
    
19. <span data-ttu-id="7ea4e-158">Observe a agenda de restauração listada na caixa **Agenda** em **Trabalho de restauração**.</span><span class="sxs-lookup"><span data-stu-id="7ea4e-158">Look at the restore schedule listed in the **Schedule** box under **Restore job**.</span></span> <span data-ttu-id="7ea4e-159">Para personalizar o cronograma da instalação, clique em **agendar**, ajuste o cronograma do agente do SQL Server conforme necessário e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="7ea4e-159">To customize the schedule for your installation, click **Schedule**, adjust the SQL Server Agent schedule as required, and click **OK**.</span></span> <span data-ttu-id="7ea4e-160">Essa agenda deve ser praticamente igual à agenda de backup.</span><span class="sxs-lookup"><span data-stu-id="7ea4e-160">This schedule should be approximately the same as the backup schedule.</span></span>
    
20. <span data-ttu-id="7ea4e-161">Na caixa de diálogo **Propriedades do Banco de Dados**, clique em **OK** para começar o processo de configuração.</span><span class="sxs-lookup"><span data-stu-id="7ea4e-161">On the **Database Properties** dialog box, click **OK** to begin the configuration process.</span></span>
    
## <a name="set-up-sql-server-log-shipping-between-the-primary-mirror-and-the-secondary-database"></a><span data-ttu-id="7ea4e-162">Configuração do envio de logs do SQL Server entre o espelho primário e o banco de dados secundário</span><span class="sxs-lookup"><span data-stu-id="7ea4e-162">Set up SQL Server log shipping between the primary mirror and the secondary database</span></span>

<span data-ttu-id="7ea4e-163">Execute as etapas a seguir para envio de log para continuar se o banco de dados de chat persistente principal tiver falhado em seu banco de dados de espelho.</span><span class="sxs-lookup"><span data-stu-id="7ea4e-163">Perform the following steps for log shipping to continue if the primary Persistent Chat database is failed over to its mirror database.</span></span>
  
1. <span data-ttu-id="7ea4e-164">Failover manual do banco de dados persistente de chat primário para o espelho.</span><span class="sxs-lookup"><span data-stu-id="7ea4e-164">Manually fail over the primary Persistent Chat database to the mirror.</span></span> <span data-ttu-id="7ea4e-165">Isso é feito usando o Shell de gerenciamento do Skype for Business Server e o cmdlet **Invoke-CsDatabaseFailover** .</span><span class="sxs-lookup"><span data-stu-id="7ea4e-165">This is done by using the Skype for Business Server Management Shell and the **Invoke-CsDatabaseFailover** cmdlet.</span></span>
    
2. <span data-ttu-id="7ea4e-166">Usando o SQL Server Management Studio, conecte-se à instância principal do espelho do servidor de chat persistente.</span><span class="sxs-lookup"><span data-stu-id="7ea4e-166">Using the SQL Server Management Studio, connect to the primary Persistent Chat Server mirror instance.</span></span>
    
3. <span data-ttu-id="7ea4e-167">Certifique-se de que o agente do SQL Server esteja em execução.</span><span class="sxs-lookup"><span data-stu-id="7ea4e-167">Be sure that the SQL Server Agent is running.</span></span>
    
4. <span data-ttu-id="7ea4e-168">Clique com o botão direito do mouse no banco de dados mgc e, em seguida, clique em **Propriedades**.</span><span class="sxs-lookup"><span data-stu-id="7ea4e-168">Right-click the mgc database, and then click **Properties**.</span></span>
    
5. <span data-ttu-id="7ea4e-169">Em **Selecionar uma página**, clique em **Envio de Logs de Transação**.</span><span class="sxs-lookup"><span data-stu-id="7ea4e-169">Under **Select a page**, click **Transaction Log Shipping**.</span></span>
    
6. <span data-ttu-id="7ea4e-170">Marque a caixa de seleção **Habilitar como banco de dados primário em uma configuração de envio de logs**.</span><span class="sxs-lookup"><span data-stu-id="7ea4e-170">Select the **Enable this as a primary database in a log shipping configuration** check box.</span></span>
    
7. <span data-ttu-id="7ea4e-171">Em **Backups de log de transação**, clique em **Configurações de Backup**.</span><span class="sxs-lookup"><span data-stu-id="7ea4e-171">Under **Transaction log backups**, click **Backup Settings**.</span></span>
    
8. <span data-ttu-id="7ea4e-172">Na caixa **Caminho de rede para a pasta de backup**, digite o caminho de rede para compartilhamento que você criou para a pasta de backup de log de transação.</span><span class="sxs-lookup"><span data-stu-id="7ea4e-172">In the **Network path to the backup folder** box, type the network path to the share you created for the transaction log backup folder.</span></span>
    
9. <span data-ttu-id="7ea4e-p117">Se a pasta de backup estiver no servidor primário, digite o caminho local para a pasta de backup na caixa **Se a pasta de backup estiver localizada no servidor primário, digite um caminho local para a pasta**. (Se a pasta de backup não estiver no servidor primário, você pode deixar essa caixa de diálogo em branco.)</span><span class="sxs-lookup"><span data-stu-id="7ea4e-p117">If the backup folder is located on the primary server, type the local path to the backup folder in the **If the backup folder is located on the primary server, type a local path to the folder** box. (If the backup folder is not on the primary server, you can leave this box empty.)</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="7ea4e-175">Se a conta de serviço do SQL Server em seu servidor primário for executada na conta do sistema local, você deverá criar a pasta de backup no servidor primário e especificar um caminho local para essa pasta.</span><span class="sxs-lookup"><span data-stu-id="7ea4e-175">If the SQL Server service account on your primary server runs under the local system account, you must create your backup folder on the primary server and specify a local path to that folder.</span></span> 
  
10. <span data-ttu-id="7ea4e-176">Configure os parâmetros **Excluir arquivos com mais de** e **Alertar se nenhum backup ocorrer em**.</span><span class="sxs-lookup"><span data-stu-id="7ea4e-176">Configure the **Delete files older than** and **Alert if no backup occurs within** parameters.</span></span>
    
11. <span data-ttu-id="7ea4e-177">Observe a agenda de backup listada na caixa **Agenda** em **Trabalho de backup**.</span><span class="sxs-lookup"><span data-stu-id="7ea4e-177">Look at the backup schedule listed in the **Schedule** box under **Backup job**.</span></span> <span data-ttu-id="7ea4e-178">Para personalizar o cronograma da instalação, clique em **agendar**e ajuste o cronograma do agente do SQL Server, conforme necessário.</span><span class="sxs-lookup"><span data-stu-id="7ea4e-178">To customize the schedule for your installation, click **Schedule**, and adjust the SQL Server Agent schedule, as required.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="7ea4e-179">Use as mesmas configurações que você usou para o banco de dados primário.</span><span class="sxs-lookup"><span data-stu-id="7ea4e-179">Use the same settings that you used for the primary database.</span></span> 
  
12. <span data-ttu-id="7ea4e-180">Em **Compactação**, selecione **Usar a configuração padrão do servidor** e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="7ea4e-180">Under **Compression**, select **Use the default server setting**, and click **OK**.</span></span>
    
13. <span data-ttu-id="7ea4e-181">Em **Instâncias e bancos de dados do servidor secundário**, clique em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="7ea4e-181">Under **Secondary server instances and databases**, click **Add**.</span></span>
    
14. <span data-ttu-id="7ea4e-182">Clique em **Conectar** e conecte-se à instância do SQL Server que você configurou como servidor secundário.</span><span class="sxs-lookup"><span data-stu-id="7ea4e-182">Click **Connect**, and connect to the instance of SQL Server that you have configured as your secondary server.</span></span>
    
15. <span data-ttu-id="7ea4e-183">Na caixa **Banco de dados secundário**, selecione o banco de dados **mgc** da lista.</span><span class="sxs-lookup"><span data-stu-id="7ea4e-183">In the **Secondary Database** box, select the **mgc** database from the list.</span></span>
    
16. <span data-ttu-id="7ea4e-184">Na guia **Inicializar Banco de Dados Secundário**, selecione a opção **Não, o banco de dados secundário é inicializado**.</span><span class="sxs-lookup"><span data-stu-id="7ea4e-184">On the **Initialize Secondary database** tab, select the option **No, the secondary database is initialized**.</span></span>
    
17. <span data-ttu-id="7ea4e-p119">Na guia **Copiar Arquivos**, em **Pasta de destino dos arquivos copiados**, digite o caminho da pasta à qual os backups de logs de transação devem ser copiados e clique em **OK**. Essa pasta normalmente se encontra no servidor secundário.</span><span class="sxs-lookup"><span data-stu-id="7ea4e-p119">On the **Copy Files** tab, in **Destination folder for copied files**, type the path of the folder into which the transaction logs backups should be copied, and click **OK**. This folder is often located on the secondary server.</span></span>
    
18. <span data-ttu-id="7ea4e-187">Abra a lista suspensa **Configuração de Script** e selecione **Configuração de Script para a janela Nova Consulta**.</span><span class="sxs-lookup"><span data-stu-id="7ea4e-187">Open the **Script Configuration** drop-down list, and select **Script Configuration to New Query Window**.</span></span>
    
19. <span data-ttu-id="7ea4e-188">Na janela Nova Consulta, em **Propriedades do Banco de Dados**, clique em **OK** para iniciar o processo de configuração.</span><span class="sxs-lookup"><span data-stu-id="7ea4e-188">In the new query window, in **Database Properties**, click **OK** to begin the configuration process.</span></span>
    
20. <span data-ttu-id="7ea4e-189">Selecione e execute a primeira metade da consulta (consulte a etapa 18) até a linha:-- \* \* \* \* \* \* end: script a ser \* \* \* \* \* \*executado no principal:.</span><span class="sxs-lookup"><span data-stu-id="7ea4e-189">Select and run the first half of the query (see step 18) up to the line: -- \*\*\*\*\*\* End: Script to be run at Primary: \*\*\*\*\*\*.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="7ea4e-190">Executar manualmente esse script é necessário porque o SQL Server Management Studio não oferece suporte a vários bancos de dados principais em uma configuração de envio de logs do SQL Server.</span><span class="sxs-lookup"><span data-stu-id="7ea4e-190">Manually running this script is necessary because SQL Server Management Studio does not support multiple primary databases in a SQL Server Log Shipping configuration.</span></span> 
  
21. <span data-ttu-id="7ea4e-191">Selecione **Cancelar** para fechar o painel de configuração de envio do arquivo de log e para estabelecer uma configuração de trabalho que implemente corretamente o envio do arquivo de log para os bancos de dados primário e espelhado (no caso de failover). </span><span class="sxs-lookup"><span data-stu-id="7ea4e-191">Select **Cancel** to close the Log File shipping configuration panel and to establish a working setup that correctly implements the log file shipping for both the primary and mirrored database (in case of failover).</span></span>
    
22. <span data-ttu-id="7ea4e-192">Faça o failback manual do banco de dados de chat persistente principal para o principal.</span><span class="sxs-lookup"><span data-stu-id="7ea4e-192">Manually fail back the primary Persistent Chat database to the primary.</span></span> <span data-ttu-id="7ea4e-193">Isso é feito usando o Shell de gerenciamento do Skype for Business Server, e o cmdlet **Invoke-CsDatabaseFailover** .</span><span class="sxs-lookup"><span data-stu-id="7ea4e-193">This is done by using the Skype for Business Server Management Shell, and the **Invoke-CsDatabaseFailover** cmdlet.</span></span>
    

