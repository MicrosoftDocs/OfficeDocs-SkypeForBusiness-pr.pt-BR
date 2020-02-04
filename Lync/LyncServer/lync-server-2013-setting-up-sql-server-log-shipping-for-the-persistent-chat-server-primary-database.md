---
title: 'Lync Server 2013: Configurando o envio de logs do SQL Server ao banco de dados primário do servidor de chat persistente'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Setting up SQL Server Log Shipping for the Persistent Chat Server primary database
ms:assetid: 088ea1c2-d592-4a11-b3b8-f1e2f8beae93
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204653(v=OCS.15)
ms:contentKeyID: 48183337
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ae44d410ef165cdd4f77b877afcfb9349dd0ec00
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41764567"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="setting-up-sql-server-log-shipping-in-lync-server-2013-for-the-persistent-chat-server-primary-database"></a><span data-ttu-id="ccc4a-102">Configurando o envio de logs do SQL Server no Lync Server 2013 ao banco de dados primário do servidor de chat persistente</span><span class="sxs-lookup"><span data-stu-id="ccc4a-102">Setting up SQL Server Log Shipping in Lync Server 2013 for the Persistent Chat Server primary database</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ccc4a-103">_**Tópico da última modificação:** 2012-11-12_</span><span class="sxs-lookup"><span data-stu-id="ccc4a-103">_**Topic Last Modified:** 2012-11-12_</span></span>

<span data-ttu-id="ccc4a-104">Usando o SQL Server Management Studio, conecte-se à instância do banco de dados de envio de log secundário do servidor de chat persistente e certifique-se de que o agente do SQL Server esteja em execução.</span><span class="sxs-lookup"><span data-stu-id="ccc4a-104">Using SQL Server Management Studio, connect to the Persistent Chat Server secondary Log Shipping database instance, and be sure that SQL Server Agent is running.</span></span>

<span data-ttu-id="ccc4a-105">Usando o SQL Server Management Studio conectado à instância do banco de dados primário de chat persistente, execute as seguintes etapas:</span><span class="sxs-lookup"><span data-stu-id="ccc4a-105">Using SQL Server Management Studio connected to the Persistent Chat primary database instance, perform the following steps:</span></span>

1.  <span data-ttu-id="ccc4a-106">Certifique-se de que o agente do SQL Server esteja em execução.</span><span class="sxs-lookup"><span data-stu-id="ccc4a-106">Be sure that the SQL Server Agent is running.</span></span>

2.  <span data-ttu-id="ccc4a-107">Clique com o botão direito do mouse no banco de dados mgc e, em seguida, clique em **Propriedades**.</span><span class="sxs-lookup"><span data-stu-id="ccc4a-107">Right-click the mgc database, and then click **Properties**.</span></span>

3.  <span data-ttu-id="ccc4a-108">Em **Selecionar uma página**, clique em **Envio de Logs de Transação**.</span><span class="sxs-lookup"><span data-stu-id="ccc4a-108">Under **Select a page**, click **Transaction Log Shipping**.</span></span>

4.  <span data-ttu-id="ccc4a-109">Marque a caixa de seleção **Habilitar como banco de dados primário em uma configuração de envio de logs**.</span><span class="sxs-lookup"><span data-stu-id="ccc4a-109">Select the **Enable this as a primary database in a log shipping configuration** check box.</span></span>

5.  <span data-ttu-id="ccc4a-110">Em **Backups de log de transação**, clique em **Configurações de Backup**.</span><span class="sxs-lookup"><span data-stu-id="ccc4a-110">Under **Transaction log backups**, click **Backup Settings**.</span></span>

6.  <span data-ttu-id="ccc4a-111">Na caixa **Caminho de rede para a pasta de backup**, digite o caminho de rede até o compartilhamento criado para a pasta de backup de log de transação.</span><span class="sxs-lookup"><span data-stu-id="ccc4a-111">In the **Network path to the backup folder** box, type the network path to the share that you created for the transaction log backup folder.</span></span>

7.  <span data-ttu-id="ccc4a-112">Se a pasta de backup estiver localizada no servidor primário, digite o caminho local para a pasta de backup na caixa **se a pasta de backup estiver localizada no servidor primário, digite um caminho local para a pasta (exemplo: c\\: backup)** .</span><span class="sxs-lookup"><span data-stu-id="ccc4a-112">If the backup folder is located on the primary server, type the local path to the backup folder in the **If the backup folder is located on the primary server, type a local path to the folder (example: c:\\backup)** box.</span></span> <span data-ttu-id="ccc4a-113">(Se a pasta de backup não estiver no servidor primário, você pode deixar essa caixa de diálogo em branco.)</span><span class="sxs-lookup"><span data-stu-id="ccc4a-113">(If the backup folder is not on the primary server, you can leave this box empty.)</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="ccc4a-114">Se a conta de serviço do SQL Server em seu servidor primário for executada na conta do sistema local, você deverá criar a pasta de backup no servidor primário e especificar um caminho local para essa pasta.</span><span class="sxs-lookup"><span data-stu-id="ccc4a-114">If the SQL Server service account on your primary server runs under the local system account, you must create your backup folder on the primary server and specify a local path to that folder.</span></span>

    
    </div>

8.  <span data-ttu-id="ccc4a-115">Configure os parâmetros **Excluir arquivos com mais de** e **Alertar se nenhum backup ocorrer em**.</span><span class="sxs-lookup"><span data-stu-id="ccc4a-115">Configure the **Delete files older than** and **Alert if no backup occurs within** parameters.</span></span>

9.  <span data-ttu-id="ccc4a-116">Observe a agenda de backup listada na caixa **Agenda** em **Trabalho de backup**.</span><span class="sxs-lookup"><span data-stu-id="ccc4a-116">Look at the backup schedule listed in the **Schedule** box under **Backup job**.</span></span> <span data-ttu-id="ccc4a-117">Para personalizar o cronograma da instalação, clique em **agendar**e ajuste o cronograma do agente do SQL Server conforme necessário.</span><span class="sxs-lookup"><span data-stu-id="ccc4a-117">To customize the schedule for your installation, click **Schedule**, and adjust the SQL Server Agent schedule as required.</span></span>

10. <span data-ttu-id="ccc4a-118">Em **Compactação**, selecione **Usar a configuração padrão do servidor** e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="ccc4a-118">Under **Compression**, select **Use the default server setting**, and then click **OK**.</span></span>

11. <span data-ttu-id="ccc4a-119">Em **Instâncias e bancos de dados do servidor secundário**, clique em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="ccc4a-119">Under **Secondary server instances and databases**, click **Add**.</span></span>

12. <span data-ttu-id="ccc4a-120">Clique em **conectar** e conecte-se à instância do SQL Server que você configurou como seu servidor secundário.</span><span class="sxs-lookup"><span data-stu-id="ccc4a-120">Click **Connect** and connect to the instance of SQL Server that you have configured as your secondary server.</span></span>

13. <span data-ttu-id="ccc4a-121">Na caixa **Banco de dados secundário**, selecione o banco de dados **mgc** da lista.</span><span class="sxs-lookup"><span data-stu-id="ccc4a-121">In the **Secondary Database** box, select the **mgc** database from the list.</span></span>

14. <span data-ttu-id="ccc4a-122">Na guia **Inicializar Banco de Dados Secundário**, escolha a opção **Sim, gerar um backup completo do banco de dados primário e restaurá-lo no banco de dados secundário (e criar o banco de dados secundário caso ele não exista)**.</span><span class="sxs-lookup"><span data-stu-id="ccc4a-122">On the **Initialize Secondary database** tab, choose the option **Yes, generate a full backup of the primary database and restore it into the secondary database (and create the secondary database if it doesn't exist)**.</span></span>

15. <span data-ttu-id="ccc4a-p103">Na guia **Copiar Arquivos**, na caixa **Pasta de destino dos arquivos copiados**, digite o caminho da pasta na qual os backups de logs de transação devem ser copiados. Normalmente, essa pasta está localizada no servidor secundário.</span><span class="sxs-lookup"><span data-stu-id="ccc4a-p103">On the **Copy Files** tab, in the **Destination folder for copied files** box, type the path of the folder into which the transaction logs backups should be copied. This folder is often located on the secondary server.</span></span>

16. <span data-ttu-id="ccc4a-125">Observe a agenda de cópia listada na caixa **Agenda** em **Trabalho de cópia**.</span><span class="sxs-lookup"><span data-stu-id="ccc4a-125">Note the copy schedule listed in the **Schedule** box under **Copy job**.</span></span> <span data-ttu-id="ccc4a-126">Para personalizar o cronograma da instalação, clique em **agendar**e ajuste o cronograma do agente do SQL Server conforme necessário.</span><span class="sxs-lookup"><span data-stu-id="ccc4a-126">To customize the schedule for your installation, click **Schedule**, and adjust the SQL Server Agent schedule as required.</span></span> <span data-ttu-id="ccc4a-127">Essa agenda deve ser praticamente igual à agenda de backup.</span><span class="sxs-lookup"><span data-stu-id="ccc4a-127">This schedule should be approximately the same as the backup schedule.</span></span>

17. <span data-ttu-id="ccc4a-128">Na guia **Restauração**, em **Estado do banco de dados ao restaurar backups**, escolha a opção **Nenhum modo de recuperação**.</span><span class="sxs-lookup"><span data-stu-id="ccc4a-128">On the **Restore** tab, under **Database state when restoring backups**, choose the **No recovery mode** option.</span></span>

18. <span data-ttu-id="ccc4a-129">Em **Atrasar restauração de backups pelo menos:**, selecione **0 minuto**.</span><span class="sxs-lookup"><span data-stu-id="ccc4a-129">Under **Delay restoring backups at least:**, select **0 minutes**.</span></span>

19. <span data-ttu-id="ccc4a-130">Escolha um limite de alerta em **Alertar se nenhuma restauração ocorrer em**.</span><span class="sxs-lookup"><span data-stu-id="ccc4a-130">Choose an alert threshold under **Alert if no restore occurs within**.</span></span>

20. <span data-ttu-id="ccc4a-131">Observe a agenda de restauração listada na caixa **Agenda** em **Trabalho de restauração**.</span><span class="sxs-lookup"><span data-stu-id="ccc4a-131">Look at the restore schedule listed in the **Schedule** box under **Restore job**.</span></span> <span data-ttu-id="ccc4a-132">Para personalizar o cronograma da instalação, clique em **agendar**, ajuste o cronograma do agente do SQL Server conforme necessário e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="ccc4a-132">To customize the schedule for your installation, click **Schedule**, adjust the SQL Server Agent schedule as required, and click **OK**.</span></span> <span data-ttu-id="ccc4a-133">Essa agenda deve ser praticamente igual à agenda de backup.</span><span class="sxs-lookup"><span data-stu-id="ccc4a-133">This schedule should be approximately the same as the backup schedule.</span></span>

21. <span data-ttu-id="ccc4a-134">Na caixa de diálogo **Propriedades do Banco de Dados**, clique em **OK** para começar o processo de configuração.</span><span class="sxs-lookup"><span data-stu-id="ccc4a-134">On the **Database Properties** dialog box, click **OK** to begin the configuration process.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

