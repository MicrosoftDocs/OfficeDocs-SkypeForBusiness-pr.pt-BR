---
title: 'Lync Server 2013: Configuração do Envio de Logs do Servidor SQL entre o espelho primário e o banco de dados secundário de Envio de Logs'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Setting up SQL Server Log Shipping between the primary mirror and the Log Shipping secondary database
ms:assetid: 4e8e9ce9-4301-47f2-a0c3-669afeb53295
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204887(v=OCS.15)
ms:contentKeyID: 48184119
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3758e654826de42f6bf6bed8ead29ce03adb6ca5
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34844954"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="setting-up-sql-server-log-shipping-between-the-primary-mirror-and-the-log-shipping-secondary-database-in-lync-server-2013"></a><span data-ttu-id="4d8c9-102">Configuração do Envio de Logs do Servidor SQL entre o espelho primário e o banco de dados secundário de Envio de Logs no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4d8c9-102">Setting up SQL Server Log Shipping between the primary mirror and the Log Shipping secondary database in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4d8c9-103">_**Tópico da última modificação:** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="4d8c9-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="4d8c9-104">Execute as etapas a seguir para envio de log para continuar se o banco de dados de chat persistente principal tiver falhado em seu banco de dados de espelho.</span><span class="sxs-lookup"><span data-stu-id="4d8c9-104">Perform the following steps for log shipping to continue if the primary Persistent Chat database is failed over to its mirror database.</span></span>

1.  <span data-ttu-id="4d8c9-105">Failover manual do banco de dados persistente de chat primário para o espelho.</span><span class="sxs-lookup"><span data-stu-id="4d8c9-105">Manually fail over the primary Persistent Chat database to the mirror.</span></span> <span data-ttu-id="4d8c9-106">Isso é feito por meio do Shell de gerenciamento do Lync Server e do cmdlet **Invoke-CsDatabaseFailover** .</span><span class="sxs-lookup"><span data-stu-id="4d8c9-106">This is done by using the Lync Server Management Shell and the **Invoke-CsDatabaseFailover** cmdlet.</span></span> <span data-ttu-id="4d8c9-107">Para obter detalhes, consulte "usando cmdlets do Shell de gerenciamento do Lync Server" em Implantando [SQL Mirroring para back-end Server High Availability no Lync Server 2013](lync-server-2013-deploying-sql-mirroring-for-back-end-server-high-availability.md).</span><span class="sxs-lookup"><span data-stu-id="4d8c9-107">For details, see "Using Lync Server Management Shell Cmdlets" in [Deploying SQL mirroring for Back End Server high availability in Lync Server 2013](lync-server-2013-deploying-sql-mirroring-for-back-end-server-high-availability.md).</span></span>

2.  <span data-ttu-id="4d8c9-108">Usando o SQL Server Management Studio, conecte-se à instância principal do espelho do servidor de chat persistente.</span><span class="sxs-lookup"><span data-stu-id="4d8c9-108">Using the SQL Server Management Studio, connect to the primary Persistent Chat Server mirror instance.</span></span>

3.  <span data-ttu-id="4d8c9-109">Certifique-se de que o agente do SQL Server esteja em execução.</span><span class="sxs-lookup"><span data-stu-id="4d8c9-109">Be sure that the SQL Server Agent is running.</span></span>

4.  <span data-ttu-id="4d8c9-110">Clique com o botão direito do mouse no banco de dados mgc e, em seguida, clique em **Propriedades**.</span><span class="sxs-lookup"><span data-stu-id="4d8c9-110">Right-click the mgc database, and then click **Properties**.</span></span>

5.  <span data-ttu-id="4d8c9-111">Em **Selecionar uma página**, clique em **Envio de Logs de Transação**.</span><span class="sxs-lookup"><span data-stu-id="4d8c9-111">Under **Select a page**, click **Transaction Log Shipping**.</span></span>

6.  <span data-ttu-id="4d8c9-112">Marque a caixa de seleção **Habilitar como banco de dados primário em uma configuração de envio de logs**.</span><span class="sxs-lookup"><span data-stu-id="4d8c9-112">Select the **Enable this as a primary database in a log shipping configuration** check box.</span></span>

7.  <span data-ttu-id="4d8c9-113">Em **Backups de log de transação**, clique em **Configurações de Backup**.</span><span class="sxs-lookup"><span data-stu-id="4d8c9-113">Under **Transaction log backups**, click **Backup Settings**.</span></span>

8.  <span data-ttu-id="4d8c9-114">Na caixa **Caminho de rede para a pasta de backup**, digite o caminho de rede para compartilhamento que você criou para a pasta de backup de log de transação.</span><span class="sxs-lookup"><span data-stu-id="4d8c9-114">In the **Network path to the backup folder** box, type the network path to the share you created for the transaction log backup folder.</span></span>

9.  <span data-ttu-id="4d8c9-p102">Se a pasta de backup estiver no servidor primário, digite o caminho local para a pasta de backup na caixa **Se a pasta de backup estiver localizada no servidor primário, digite um caminho local para a pasta**. (Se a pasta de backup não estiver no servidor primário, você pode deixar essa caixa de diálogo em branco.)</span><span class="sxs-lookup"><span data-stu-id="4d8c9-p102">If the backup folder is located on the primary server, type the local path to the backup folder in the **If the backup folder is located on the primary server, type a local path to the folder** box. (If the backup folder is not on the primary server, you can leave this box empty.)</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="4d8c9-117">Se a conta de serviço do SQL Server em seu servidor primário for executada na conta do sistema local, você deverá criar a pasta de backup no servidor primário e especificar um caminho local para essa pasta.</span><span class="sxs-lookup"><span data-stu-id="4d8c9-117">If the SQL Server service account on your primary server runs under the local system account, you must create your backup folder on the primary server and specify a local path to that folder.</span></span>

    
    </div>

10. <span data-ttu-id="4d8c9-118">Configure os parâmetros **Excluir arquivos com mais de** e **Alertar se nenhum backup ocorrer em**.</span><span class="sxs-lookup"><span data-stu-id="4d8c9-118">Configure the **Delete files older than** and **Alert if no backup occurs within** parameters.</span></span>

11. <span data-ttu-id="4d8c9-119">Observe a agenda de backup listada na caixa **Agenda** em **Trabalho de backup**.</span><span class="sxs-lookup"><span data-stu-id="4d8c9-119">Look at the backup schedule listed in the **Schedule** box under **Backup job**.</span></span> <span data-ttu-id="4d8c9-120">Para personalizar o cronograma da instalação, clique em **agendar**e ajuste o cronograma do agente do SQL Server, conforme necessário.</span><span class="sxs-lookup"><span data-stu-id="4d8c9-120">To customize the schedule for your installation, click **Schedule**, and adjust the SQL Server Agent schedule, as required.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="4d8c9-121">Use as mesmas configurações que você usou para o banco de dados primário.</span><span class="sxs-lookup"><span data-stu-id="4d8c9-121">Use the same settings that you used for the primary database.</span></span>

    
    </div>

12. <span data-ttu-id="4d8c9-122">Em **Compactação**, selecione **Usar a configuração padrão do servidor** e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="4d8c9-122">Under **Compression**, select **Use the default server setting**, and click **OK**.</span></span>

13. <span data-ttu-id="4d8c9-123">Em **Instâncias e bancos de dados do servidor secundário**, clique em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="4d8c9-123">Under **Secondary server instances and databases**, click **Add**.</span></span>

14. <span data-ttu-id="4d8c9-124">Clique em **Conectar** e conecte-se à instância do SQL Server que você configurou como servidor secundário.</span><span class="sxs-lookup"><span data-stu-id="4d8c9-124">Click **Connect**, and connect to the instance of SQL Server that you have configured as your secondary server.</span></span>

15. <span data-ttu-id="4d8c9-125">Na caixa **Banco de dados secundário**, selecione o banco de dados **mgc** da lista.</span><span class="sxs-lookup"><span data-stu-id="4d8c9-125">In the **Secondary Database** box, select the **mgc** database from the list.</span></span>

16. <span data-ttu-id="4d8c9-126">Na guia **Inicializar Banco de Dados Secundário**, selecione a opção **Não, o banco de dados secundário é inicializado**.</span><span class="sxs-lookup"><span data-stu-id="4d8c9-126">On the **Initialize Secondary database** tab, select the option **No, the secondary database is initialized**.</span></span>

17. <span data-ttu-id="4d8c9-p104">Na guia **Copiar Arquivos**, em **Pasta de destino dos arquivos copiados**, digite o caminho da pasta à qual os backups de logs de transação devem ser copiados e clique em **OK**. Essa pasta normalmente se encontra no servidor secundário.</span><span class="sxs-lookup"><span data-stu-id="4d8c9-p104">On the **Copy Files** tab, in **Destination folder for copied files**, type the path of the folder into which the transaction logs backups should be copied, and click **OK**. This folder is often located on the secondary server.</span></span>

18. <span data-ttu-id="4d8c9-129">Abra a lista suspensa **Configuração de Script** e selecione **Configuração de Script para a janela Nova Consulta**.</span><span class="sxs-lookup"><span data-stu-id="4d8c9-129">Open the **Script Configuration** drop-down list, and select **Script Configuration to New Query Window**.</span></span>

19. <span data-ttu-id="4d8c9-130">Na janela Nova Consulta, em **Propriedades do Banco de Dados**, clique em **OK** para iniciar o processo de configuração.</span><span class="sxs-lookup"><span data-stu-id="4d8c9-130">In the new query window, in **Database Properties**, click **OK** to begin the configuration process.</span></span>

20. <span data-ttu-id="4d8c9-131">Selecione e execute a primeira metade da consulta (consulte a etapa 18) até a linha:-- \* \* \* \* \* \* end: script a ser \* \* \* \* \* \*executado no principal:.</span><span class="sxs-lookup"><span data-stu-id="4d8c9-131">Select and run the first half of the query (see step 18) up to the line: -- \*\*\*\*\*\* End: Script to be run at Primary: \*\*\*\*\*\*.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="4d8c9-132">Executar manualmente esse script é necessário porque o SQL Server Management Studio não oferece suporte a vários bancos de dados principais em uma configuração de envio de logs do SQL Server.</span><span class="sxs-lookup"><span data-stu-id="4d8c9-132">Manually running this script is necessary because SQL Server Management Studio does not support multiple primary databases in a SQL Server Log Shipping configuration.</span></span>

    
    </div>

21. <span data-ttu-id="4d8c9-133">Selecione **Cancelar** para fechar o painel de configuração de envio do arquivo de log e para estabelecer uma configuração de trabalho que implemente corretamente o envio do arquivo de log para os bancos de dados primário e espelhado (no caso de failover). </span><span class="sxs-lookup"><span data-stu-id="4d8c9-133">Select **Cancel** to close the Log File shipping configuration panel and to establish a working setup that correctly implements the log file shipping for both the primary and mirrored database (in case of failover).</span></span>

22. <span data-ttu-id="4d8c9-134">Faça o failback manual do banco de dados de chat persistente principal para o principal.</span><span class="sxs-lookup"><span data-stu-id="4d8c9-134">Manually fail back the primary Persistent Chat database to the primary.</span></span> <span data-ttu-id="4d8c9-135">Isso é feito usando o Shell de gerenciamento do Lync Server e o cmdlet **Invoke-CsDatabaseFailover** .</span><span class="sxs-lookup"><span data-stu-id="4d8c9-135">This is done by using the Lync Server Management Shell, and the **Invoke-CsDatabaseFailover** cmdlet.</span></span> <span data-ttu-id="4d8c9-136">Para obter detalhes, consulte "usando cmdlets do Shell de gerenciamento do Lync Server" em Implantando [SQL Mirroring para back-end Server High Availability no Lync Server 2013](lync-server-2013-deploying-sql-mirroring-for-back-end-server-high-availability.md).</span><span class="sxs-lookup"><span data-stu-id="4d8c9-136">For details, see "Using Lync Server Management Shell Cmdlets" in [Deploying SQL mirroring for Back End Server high availability in Lync Server 2013](lync-server-2013-deploying-sql-mirroring-for-back-end-server-high-availability.md).</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="4d8c9-137">Confira também</span><span class="sxs-lookup"><span data-stu-id="4d8c9-137">See Also</span></span>


[<span data-ttu-id="4d8c9-138">Implantando espelhamento SQL para alta disponibilidade de Servidor Back-End no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4d8c9-138">Deploying SQL mirroring for Back End Server high availability in Lync Server 2013</span></span>](lync-server-2013-deploying-sql-mirroring-for-back-end-server-high-availability.md)  
[<span data-ttu-id="4d8c9-139">Implantando espelhamento SQL para alta disponibilidade de Servidor Back-End no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4d8c9-139">Deploying SQL mirroring for Back End Server high availability in Lync Server 2013</span></span>](lync-server-2013-deploying-sql-mirroring-for-back-end-server-high-availability.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

