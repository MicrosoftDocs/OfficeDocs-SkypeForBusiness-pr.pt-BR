---
title: 'Lync Server 2013: Configurando o envio de logs do SQL Server para o banco de dados de servidor de chat persistente'
description: 'Lync Server 2013: Configurando o envio de logs do SQL Server para o banco de dados de servidor de chat persistente.'
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
ms.openlocfilehash: 72b7e68bd0cb7b9f544b86a15204d3e832692ec1
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48554257"
---
# <a name="setting-up-sql-server-log-shipping-in-lync-server-2013-for-the-persistent-chat-server-primary-database"></a><span data-ttu-id="8c9c5-103">Configurando o envio de logs do SQL Server no Lync Server 2013 para o banco de dados primário do servidor de chat persistente</span><span class="sxs-lookup"><span data-stu-id="8c9c5-103">Setting up SQL Server Log Shipping in Lync Server 2013 for the Persistent Chat Server primary database</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8c9c5-104">_**Última modificação do tópico:** 2012-11-12_</span><span class="sxs-lookup"><span data-stu-id="8c9c5-104">_**Topic Last Modified:** 2012-11-12_</span></span>

<span data-ttu-id="8c9c5-105">Usando o SQL Server Management Studio, conecte-se à instância do banco de dados de envio de logs do servidor de chat persistente secundário e certifique-se de que o SQL Server Agent esteja em execução.</span><span class="sxs-lookup"><span data-stu-id="8c9c5-105">Using SQL Server Management Studio, connect to the Persistent Chat Server secondary Log Shipping database instance, and be sure that SQL Server Agent is running.</span></span>

<span data-ttu-id="8c9c5-106">Usando o SQL Server Management Studio conectado à instância de banco de dados principal de chat persistente, execute as seguintes etapas:</span><span class="sxs-lookup"><span data-stu-id="8c9c5-106">Using SQL Server Management Studio connected to the Persistent Chat primary database instance, perform the following steps:</span></span>

1.  <span data-ttu-id="8c9c5-107">Certifique-se de que o SQL Server Agent esteja em execução.</span><span class="sxs-lookup"><span data-stu-id="8c9c5-107">Be sure that the SQL Server Agent is running.</span></span>

2.  <span data-ttu-id="8c9c5-108">Clique com o botão direito no banco de dados mgc e, em seguida, clique em **Propriedades**.</span><span class="sxs-lookup"><span data-stu-id="8c9c5-108">Right-click the mgc database, and then click **Properties**.</span></span>

3.  <span data-ttu-id="8c9c5-109">Em **Selecionar uma página**, clique em **Envio de Logs de Transações**.</span><span class="sxs-lookup"><span data-stu-id="8c9c5-109">Under **Select a page**, click **Transaction Log Shipping**.</span></span>

4.  <span data-ttu-id="8c9c5-110">Selecione a caixa de seleção **Habilitar como banco de dados primário em uma configuração de envio de log**.</span><span class="sxs-lookup"><span data-stu-id="8c9c5-110">Select the **Enable this as a primary database in a log shipping configuration** check box.</span></span>

5.  <span data-ttu-id="8c9c5-111">Em **Backups do log de transação**, clique em **Configurações de Backup**.</span><span class="sxs-lookup"><span data-stu-id="8c9c5-111">Under **Transaction log backups**, click **Backup Settings**.</span></span>

6.  <span data-ttu-id="8c9c5-112">Na caixa **Caminho de rede para a pasta Backup**, digite o caminho de rede até o compartilhamento criado para a pasta de backup do log de transação.</span><span class="sxs-lookup"><span data-stu-id="8c9c5-112">In the **Network path to the backup folder** box, type the network path to the share that you created for the transaction log backup folder.</span></span>

7.  <span data-ttu-id="8c9c5-113">Se a pasta de backup estiver localizada no servidor primário, digite o caminho local para a pasta de backup na caixa **se a pasta de backup estiver localizada no servidor primário, digite um caminho local para a pasta (exemplo: c: \\ backup)** .</span><span class="sxs-lookup"><span data-stu-id="8c9c5-113">If the backup folder is located on the primary server, type the local path to the backup folder in the **If the backup folder is located on the primary server, type a local path to the folder (example: c:\\backup)** box.</span></span> <span data-ttu-id="8c9c5-114">(Se a pasta de backup não estiver o servidor primário, você pode deixa essa caixa de diálogo vazia.)</span><span class="sxs-lookup"><span data-stu-id="8c9c5-114">(If the backup folder is not on the primary server, you can leave this box empty.)</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="8c9c5-115">Se a conta de serviço do SQL Server em seu servidor principal é executada sob a conta do sistema local, você deve criar sua pasta de backup no servidor primário e especificar um caminho local para essa pasta.</span><span class="sxs-lookup"><span data-stu-id="8c9c5-115">If the SQL Server service account on your primary server runs under the local system account, you must create your backup folder on the primary server and specify a local path to that folder.</span></span>

    
    </div>

8.  <span data-ttu-id="8c9c5-116">Configure os parâmetros **Excluir arquivos com mais de** e **Alertar se nenhum backup ocorrer em**.</span><span class="sxs-lookup"><span data-stu-id="8c9c5-116">Configure the **Delete files older than** and **Alert if no backup occurs within** parameters.</span></span>

9.  <span data-ttu-id="8c9c5-117">Observe a agenda de backup listada na caixa de diálogo **Agendar** em **Trabalho de backup**.</span><span class="sxs-lookup"><span data-stu-id="8c9c5-117">Look at the backup schedule listed in the **Schedule** box under **Backup job**.</span></span> <span data-ttu-id="8c9c5-118">Para personalizar a agenda da instalação, clique em **agenda**e ajuste a agenda do SQL Server Agent conforme necessário.</span><span class="sxs-lookup"><span data-stu-id="8c9c5-118">To customize the schedule for your installation, click **Schedule**, and adjust the SQL Server Agent schedule as required.</span></span>

10. <span data-ttu-id="8c9c5-119">Em **Compactação**, selecione **Usar a configuração padrão do servidor** e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="8c9c5-119">Under **Compression**, select **Use the default server setting**, and then click **OK**.</span></span>

11. <span data-ttu-id="8c9c5-120">Em **Instâncias e bancos de dados do servidor secundário**, clique em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="8c9c5-120">Under **Secondary server instances and databases**, click **Add**.</span></span>

12. <span data-ttu-id="8c9c5-121">Clique em **conectar** e conecte-se à instância do SQL Server que você configurou como servidor secundário.</span><span class="sxs-lookup"><span data-stu-id="8c9c5-121">Click **Connect** and connect to the instance of SQL Server that you have configured as your secondary server.</span></span>

13. <span data-ttu-id="8c9c5-122">Na caixa de diálogo **Banco de dados secundário**, selecione o banco de dados **mgc** da lista.</span><span class="sxs-lookup"><span data-stu-id="8c9c5-122">In the **Secondary Database** box, select the **mgc** database from the list.</span></span>

14. <span data-ttu-id="8c9c5-123">Na guia **inicializar banco de dados secundário** , escolha a opção **Sim, gere um backup completo do banco de dados primário e restaure-o no banco de dados secundário (e crie o banco de dados secundário, caso não exista)**.</span><span class="sxs-lookup"><span data-stu-id="8c9c5-123">On the **Initialize Secondary database** tab, choose the option **Yes, generate a full backup of the primary database and restore it into the secondary database (and create the secondary database if it doesn't exist)**.</span></span>

15. <span data-ttu-id="8c9c5-p103">Na guia **Copiar Arquivos**, na caixa **Pasta de destino dos arquivos copiados**, digite o caminho da pasta na qual os backups de logs de transação devem ser copiadas. Normalmente, essa pasta está localizada no servidor secundário.</span><span class="sxs-lookup"><span data-stu-id="8c9c5-p103">On the **Copy Files** tab, in the **Destination folder for copied files** box, type the path of the folder into which the transaction logs backups should be copied. This folder is often located on the secondary server.</span></span>

16. <span data-ttu-id="8c9c5-126">Observe agenda de cópia listada na caixa **Agenda** em **Trabalho de cópia**.</span><span class="sxs-lookup"><span data-stu-id="8c9c5-126">Note the copy schedule listed in the **Schedule** box under **Copy job**.</span></span> <span data-ttu-id="8c9c5-127">Para personalizar a agenda da instalação, clique em **agenda**e ajuste a agenda do SQL Server Agent conforme necessário.</span><span class="sxs-lookup"><span data-stu-id="8c9c5-127">To customize the schedule for your installation, click **Schedule**, and adjust the SQL Server Agent schedule as required.</span></span> <span data-ttu-id="8c9c5-128">Essa agenda deve ser quase a mesma que a agenda de backup.</span><span class="sxs-lookup"><span data-stu-id="8c9c5-128">This schedule should be approximately the same as the backup schedule.</span></span>

17. <span data-ttu-id="8c9c5-129">Na guia **Restauração**, em **Estado do banco de dados ao restaurar backups**, escolha a opção **Nenhum modo de recuperação**.</span><span class="sxs-lookup"><span data-stu-id="8c9c5-129">On the **Restore** tab, under **Database state when restoring backups**, choose the **No recovery mode** option.</span></span>

18. <span data-ttu-id="8c9c5-130">Em **Atrasar restauração de backups pelo menos:**, selecione **0 minutos**.</span><span class="sxs-lookup"><span data-stu-id="8c9c5-130">Under **Delay restoring backups at least:**, select **0 minutes**.</span></span>

19. <span data-ttu-id="8c9c5-131">Escolha um limite de alerta sob **Alertar se nenhuma restauração ocorrer em**.</span><span class="sxs-lookup"><span data-stu-id="8c9c5-131">Choose an alert threshold under **Alert if no restore occurs within**.</span></span>

20. <span data-ttu-id="8c9c5-132">Observe a agenda de restauração listada na caixa **Agenda** em **Trabalho de restauração**.</span><span class="sxs-lookup"><span data-stu-id="8c9c5-132">Look at the restore schedule listed in the **Schedule** box under **Restore job**.</span></span> <span data-ttu-id="8c9c5-133">Para personalizar a agenda da instalação, clique em **agenda**, ajuste a agenda do SQL Server Agent conforme necessário e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="8c9c5-133">To customize the schedule for your installation, click **Schedule**, adjust the SQL Server Agent schedule as required, and click **OK**.</span></span> <span data-ttu-id="8c9c5-134">Essa agenda deve ser quase a mesma que a agenda de backup.</span><span class="sxs-lookup"><span data-stu-id="8c9c5-134">This schedule should be approximately the same as the backup schedule.</span></span>

21. <span data-ttu-id="8c9c5-135">Na caixa de diálogo **Propriedades do Banco de Dados**, clique em **OK** para começar o processo de configuração.</span><span class="sxs-lookup"><span data-stu-id="8c9c5-135">On the **Database Properties** dialog box, click **OK** to begin the configuration process.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

