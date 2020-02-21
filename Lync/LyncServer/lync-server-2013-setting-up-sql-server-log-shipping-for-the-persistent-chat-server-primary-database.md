---
title: 'Lync Server 2013: Configurando o envio de logs do SQL Server para o banco de dados de servidor de chat persistente'
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
ms.openlocfilehash: 492d4be1865bdb022736a62a2507c115c892b47b
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42200487"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="setting-up-sql-server-log-shipping-in-lync-server-2013-for-the-persistent-chat-server-primary-database"></a><span data-ttu-id="46539-102">Configurando o envio de logs do SQL Server no Lync Server 2013 para o banco de dados primário do servidor de chat persistente</span><span class="sxs-lookup"><span data-stu-id="46539-102">Setting up SQL Server Log Shipping in Lync Server 2013 for the Persistent Chat Server primary database</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="46539-103">_**Última modificação do tópico:** 2012-11-12_</span><span class="sxs-lookup"><span data-stu-id="46539-103">_**Topic Last Modified:** 2012-11-12_</span></span>

<span data-ttu-id="46539-104">Usando o SQL Server Management Studio, conecte-se à instância do banco de dados de envio de logs do servidor de chat persistente secundário e certifique-se de que o SQL Server Agent esteja em execução.</span><span class="sxs-lookup"><span data-stu-id="46539-104">Using SQL Server Management Studio, connect to the Persistent Chat Server secondary Log Shipping database instance, and be sure that SQL Server Agent is running.</span></span>

<span data-ttu-id="46539-105">Usando o SQL Server Management Studio conectado à instância de banco de dados principal de chat persistente, execute as seguintes etapas:</span><span class="sxs-lookup"><span data-stu-id="46539-105">Using SQL Server Management Studio connected to the Persistent Chat primary database instance, perform the following steps:</span></span>

1.  <span data-ttu-id="46539-106">Certifique-se de que o SQL Server Agent esteja em execução.</span><span class="sxs-lookup"><span data-stu-id="46539-106">Be sure that the SQL Server Agent is running.</span></span>

2.  <span data-ttu-id="46539-107">Clique com o botão direito no banco de dados mgc e, em seguida, clique em **Propriedades**.</span><span class="sxs-lookup"><span data-stu-id="46539-107">Right-click the mgc database, and then click **Properties**.</span></span>

3.  <span data-ttu-id="46539-108">Em **Selecionar uma página**, clique em **Envio de Logs de Transações**.</span><span class="sxs-lookup"><span data-stu-id="46539-108">Under **Select a page**, click **Transaction Log Shipping**.</span></span>

4.  <span data-ttu-id="46539-109">Selecione a caixa de seleção **Habilitar como banco de dados primário em uma configuração de envio de log**.</span><span class="sxs-lookup"><span data-stu-id="46539-109">Select the **Enable this as a primary database in a log shipping configuration** check box.</span></span>

5.  <span data-ttu-id="46539-110">Em **Backups do log de transação**, clique em **Configurações de Backup**.</span><span class="sxs-lookup"><span data-stu-id="46539-110">Under **Transaction log backups**, click **Backup Settings**.</span></span>

6.  <span data-ttu-id="46539-111">Na caixa **Caminho de rede para a pasta Backup**, digite o caminho de rede até o compartilhamento criado para a pasta de backup do log de transação.</span><span class="sxs-lookup"><span data-stu-id="46539-111">In the **Network path to the backup folder** box, type the network path to the share that you created for the transaction log backup folder.</span></span>

7.  <span data-ttu-id="46539-112">Se a pasta de backup estiver localizada no servidor primário, digite o caminho local para a pasta de backup na caixa **se a pasta de backup estiver localizada no servidor primário, digite um caminho local para a pasta (exemplo: c\\: backup)** .</span><span class="sxs-lookup"><span data-stu-id="46539-112">If the backup folder is located on the primary server, type the local path to the backup folder in the **If the backup folder is located on the primary server, type a local path to the folder (example: c:\\backup)** box.</span></span> <span data-ttu-id="46539-113">(Se a pasta de backup não estiver o servidor primário, você pode deixa essa caixa de diálogo vazia.)</span><span class="sxs-lookup"><span data-stu-id="46539-113">(If the backup folder is not on the primary server, you can leave this box empty.)</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="46539-114">Se a conta de serviço do SQL Server em seu servidor principal é executada sob a conta do sistema local, você deve criar sua pasta de backup no servidor primário e especificar um caminho local para essa pasta.</span><span class="sxs-lookup"><span data-stu-id="46539-114">If the SQL Server service account on your primary server runs under the local system account, you must create your backup folder on the primary server and specify a local path to that folder.</span></span>

    
    </div>

8.  <span data-ttu-id="46539-115">Configure os parâmetros **Excluir arquivos com mais de** e **Alertar se nenhum backup ocorrer em**.</span><span class="sxs-lookup"><span data-stu-id="46539-115">Configure the **Delete files older than** and **Alert if no backup occurs within** parameters.</span></span>

9.  <span data-ttu-id="46539-116">Observe a agenda de backup listada na caixa de diálogo **Agendar** em **Trabalho de backup**.</span><span class="sxs-lookup"><span data-stu-id="46539-116">Look at the backup schedule listed in the **Schedule** box under **Backup job**.</span></span> <span data-ttu-id="46539-117">Para personalizar a agenda da instalação, clique em **agenda**e ajuste a agenda do SQL Server Agent conforme necessário.</span><span class="sxs-lookup"><span data-stu-id="46539-117">To customize the schedule for your installation, click **Schedule**, and adjust the SQL Server Agent schedule as required.</span></span>

10. <span data-ttu-id="46539-118">Em **Compactação**, selecione **Usar a configuração padrão do servidor** e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="46539-118">Under **Compression**, select **Use the default server setting**, and then click **OK**.</span></span>

11. <span data-ttu-id="46539-119">Em **Instâncias e bancos de dados do servidor secundário**, clique em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="46539-119">Under **Secondary server instances and databases**, click **Add**.</span></span>

12. <span data-ttu-id="46539-120">Clique em **conectar** e conecte-se à instância do SQL Server que você configurou como servidor secundário.</span><span class="sxs-lookup"><span data-stu-id="46539-120">Click **Connect** and connect to the instance of SQL Server that you have configured as your secondary server.</span></span>

13. <span data-ttu-id="46539-121">Na caixa de diálogo **Banco de dados secundário**, selecione o banco de dados **mgc** da lista.</span><span class="sxs-lookup"><span data-stu-id="46539-121">In the **Secondary Database** box, select the **mgc** database from the list.</span></span>

14. <span data-ttu-id="46539-122">Na guia **inicializar banco de dados secundário** , escolha a opção **Sim, gere um backup completo do banco de dados primário e restaure-o no banco de dados secundário (e crie o banco de dados secundário, caso não exista)**.</span><span class="sxs-lookup"><span data-stu-id="46539-122">On the **Initialize Secondary database** tab, choose the option **Yes, generate a full backup of the primary database and restore it into the secondary database (and create the secondary database if it doesn't exist)**.</span></span>

15. <span data-ttu-id="46539-p103">Na guia **Copiar Arquivos**, na caixa **Pasta de destino dos arquivos copiados**, digite o caminho da pasta na qual os backups de logs de transação devem ser copiadas. Normalmente, essa pasta está localizada no servidor secundário.</span><span class="sxs-lookup"><span data-stu-id="46539-p103">On the **Copy Files** tab, in the **Destination folder for copied files** box, type the path of the folder into which the transaction logs backups should be copied. This folder is often located on the secondary server.</span></span>

16. <span data-ttu-id="46539-125">Observe agenda de cópia listada na caixa **Agenda** em **Trabalho de cópia**.</span><span class="sxs-lookup"><span data-stu-id="46539-125">Note the copy schedule listed in the **Schedule** box under **Copy job**.</span></span> <span data-ttu-id="46539-126">Para personalizar a agenda da instalação, clique em **agenda**e ajuste a agenda do SQL Server Agent conforme necessário.</span><span class="sxs-lookup"><span data-stu-id="46539-126">To customize the schedule for your installation, click **Schedule**, and adjust the SQL Server Agent schedule as required.</span></span> <span data-ttu-id="46539-127">Essa agenda deve ser quase a mesma que a agenda de backup.</span><span class="sxs-lookup"><span data-stu-id="46539-127">This schedule should be approximately the same as the backup schedule.</span></span>

17. <span data-ttu-id="46539-128">Na guia **Restauração**, em **Estado do banco de dados ao restaurar backups**, escolha a opção **Nenhum modo de recuperação**.</span><span class="sxs-lookup"><span data-stu-id="46539-128">On the **Restore** tab, under **Database state when restoring backups**, choose the **No recovery mode** option.</span></span>

18. <span data-ttu-id="46539-129">Em **Atrasar restauração de backups pelo menos:**, selecione **0 minutos**.</span><span class="sxs-lookup"><span data-stu-id="46539-129">Under **Delay restoring backups at least:**, select **0 minutes**.</span></span>

19. <span data-ttu-id="46539-130">Escolha um limite de alerta sob **Alertar se nenhuma restauração ocorrer em**.</span><span class="sxs-lookup"><span data-stu-id="46539-130">Choose an alert threshold under **Alert if no restore occurs within**.</span></span>

20. <span data-ttu-id="46539-131">Observe a agenda de restauração listada na caixa **Agenda** em **Trabalho de restauração**.</span><span class="sxs-lookup"><span data-stu-id="46539-131">Look at the restore schedule listed in the **Schedule** box under **Restore job**.</span></span> <span data-ttu-id="46539-132">Para personalizar a agenda da instalação, clique em **agenda**, ajuste a agenda do SQL Server Agent conforme necessário e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="46539-132">To customize the schedule for your installation, click **Schedule**, adjust the SQL Server Agent schedule as required, and click **OK**.</span></span> <span data-ttu-id="46539-133">Essa agenda deve ser quase a mesma que a agenda de backup.</span><span class="sxs-lookup"><span data-stu-id="46539-133">This schedule should be approximately the same as the backup schedule.</span></span>

21. <span data-ttu-id="46539-134">Na caixa de diálogo **Propriedades do Banco de Dados**, clique em **OK** para começar o processo de configuração.</span><span class="sxs-lookup"><span data-stu-id="46539-134">On the **Database Properties** dialog box, click **OK** to begin the configuration process.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

