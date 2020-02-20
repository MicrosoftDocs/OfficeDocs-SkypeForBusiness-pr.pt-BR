---
title: 'Lync Server 2013: failback do servidor de chat persistente'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Failing back Persistent Chat Server
ms:assetid: 67b91de4-6ddc-43e6-9812-5e1aa84a7980
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204970(v=OCS.15)
ms:contentKeyID: 48184396
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6847f4002204c270b5978df2cab2851eeb912b20
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42151321"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="failing-back-persistent-chat-server-in-lync-server-2013"></a><span data-ttu-id="6e2c4-102">Failback do servidor de chat persistente no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6e2c4-102">Failing back Persistent Chat Server in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6e2c4-103">_**Última modificação do tópico:** 2014-02-05_</span><span class="sxs-lookup"><span data-stu-id="6e2c4-103">_**Topic Last Modified:** 2014-02-05_</span></span>

<span data-ttu-id="6e2c4-104">Este procedimento descreve as etapas necessárias para se recuperar de uma falha de servidor de chat persistente e para restabelecer as operações do data center principal.</span><span class="sxs-lookup"><span data-stu-id="6e2c4-104">This procedure outlines the steps necessary to recover from a Persistent Chat Server failure, and to reestablish operations from the primary data center.</span></span>

<span data-ttu-id="6e2c4-105">Durante uma falha de servidor de chat persistente, o data center principal sofre uma interrupção completa e os bancos de dados primário e espelho ficam indisponíveis.</span><span class="sxs-lookup"><span data-stu-id="6e2c4-105">During Persistent Chat Server failure, the primary data center suffers complete outage, and the primary and mirror databases become unavailable.</span></span> <span data-ttu-id="6e2c4-106">O data center primário faz failover para o servidor de backup.</span><span class="sxs-lookup"><span data-stu-id="6e2c4-106">The primary data center fails over to the backup server.</span></span>

<span data-ttu-id="6e2c4-107">O procedimento a seguir restaura a operação normal após o backup do data center primário e a recomposição dos servidores.</span><span class="sxs-lookup"><span data-stu-id="6e2c4-107">The following procedure restores normal operation after the primary data center is back up, and the servers have been rebuilt.</span></span> <span data-ttu-id="6e2c4-108">O procedimento pressupõe que o data center principal tenha sido recuperado da interrupção total e que o banco de dados do MGC e o banco de dados do mgccomp tenham sido recriados e reinstalados usando o construtor de topologias.</span><span class="sxs-lookup"><span data-stu-id="6e2c4-108">The procedure assumes that the primary data center has been recovered from total outage, and that the mgc database and the mgccomp database have been rebuilt and reinstalled by using Topology Builder.</span></span>

<span data-ttu-id="6e2c4-109">O procedimento também pressupõe que nenhum novo servidor de espelhamento e backup foi implantado durante o período de failover e que o único servidor implantado é o servidor de backup e seu servidor de espelhamento, conforme definido no [servidor de chat persistente com failover no Lync server 2013](lync-server-2013-failing-over-persistent-chat-server.md).</span><span class="sxs-lookup"><span data-stu-id="6e2c4-109">The procedure also assumes that no new mirror and backup servers were deployed during the failover period, and that the only server deployed is the backup server and its mirror server, as defined in [Failing over Persistent Chat Server in Lync Server 2013](lync-server-2013-failing-over-persistent-chat-server.md).</span></span>

<span data-ttu-id="6e2c4-110">Estas etapas foram criadas para recuperar a configuração como ela se encontrava antes do desastre que resultou no failover do servidor primário para o servidor de backup.</span><span class="sxs-lookup"><span data-stu-id="6e2c4-110">These steps are designed to recover configuration as it existed prior to the disaster, resulting in failover from the primary server to the backup server.</span></span>

<div>

## <a name="to-fail-back-persistent-chat-server"></a><span data-ttu-id="6e2c4-111">Para fazer failback do servidor de chat persistente</span><span class="sxs-lookup"><span data-stu-id="6e2c4-111">To fail back Persistent Chat Server</span></span>

1.  <span data-ttu-id="6e2c4-112">Limpe todos os servidores da lista de servidores ativos do servidor de chat persistente `Set-CsPersistentChatActiveServer` usando o cmdlet do Shell de gerenciamento do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="6e2c4-112">Clear all servers from the Persistent Chat Server Active Server list by using the `Set-CsPersistentChatActiveServer` cmdlet from the Lync Server Management Shell.</span></span> <span data-ttu-id="6e2c4-113">Isso impede que todos os servidores de chat persistente se conectem ao banco de dados do MGC e ao banco de dados do mgccomp durante o failback.</span><span class="sxs-lookup"><span data-stu-id="6e2c4-113">This stops all Persistent Chat Servers from connecting to the mgc database and the mgccomp database during failback.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="6e2c4-114">O SQL Server Agent no servidor back-end do servidor de chat persistente secundário deve estar sendo executado sob uma conta privilegiada.</span><span class="sxs-lookup"><span data-stu-id="6e2c4-114">The SQL Server agent on the secondary Persistent Chat Server Back End Server should be running under a privileged account.</span></span> <span data-ttu-id="6e2c4-115">Em termos específicos, a conta deve incluir:</span><span class="sxs-lookup"><span data-stu-id="6e2c4-115">Specifically, the account must include:</span></span> 
    > <UL>
    > <LI>
    > <P><span data-ttu-id="6e2c4-116">Acesso de leitura ao compartilhamento de rede no qual os backups serão colocados.</span><span class="sxs-lookup"><span data-stu-id="6e2c4-116">Read access to the network share that backups are being placed in.</span></span></P>
    > <LI>
    > <P><span data-ttu-id="6e2c4-117">Acesso de gravação ao diretório local específico em que os backups serão copiados.</span><span class="sxs-lookup"><span data-stu-id="6e2c4-117">Write access to the specific local directory that the backups are being copied to.</span></span></P></LI></UL>

    
    </div>

2.  <span data-ttu-id="6e2c4-118">Desabilite o espelhamento no banco de dados mgc de backup:</span><span class="sxs-lookup"><span data-stu-id="6e2c4-118">Disable mirroring on the backup mgc database:</span></span>
    
    1.  <span data-ttu-id="6e2c4-119">Usando o SQL Server Management Studio, conecte-se à instância de backup MGC.</span><span class="sxs-lookup"><span data-stu-id="6e2c4-119">Using SQL Server Management Studio, connect to the backup mgc instance.</span></span>
    
    2.  <span data-ttu-id="6e2c4-120">Clique com o botão direito do mouse no banco de dados mgc, aponte para **Tarefas** e clique em **Espelhar**.</span><span class="sxs-lookup"><span data-stu-id="6e2c4-120">Right-click the mgc database, point to **Tasks**, and then click **Mirror**.</span></span>
    
    3.  <span data-ttu-id="6e2c4-121">Click **Remover Espelhamento**.</span><span class="sxs-lookup"><span data-stu-id="6e2c4-121">Click **Remove Mirroring**.</span></span>
    
    4.  <span data-ttu-id="6e2c4-122">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="6e2c4-122">Click **OK**.</span></span>
    
    5.  <span data-ttu-id="6e2c4-123">Execute as mesmas etapas com o banco de dados mgccomp.</span><span class="sxs-lookup"><span data-stu-id="6e2c4-123">Perform the same steps with the mgccomp database.</span></span>

3.  <span data-ttu-id="6e2c4-124">Faça backup do banco de dados mgc para que ele possa ser restaurado para o novo banco de dados primário:</span><span class="sxs-lookup"><span data-stu-id="6e2c4-124">Back up the mgc database so that it can be restored to the new primary database:</span></span>
    
    1.  <span data-ttu-id="6e2c4-125">Usando o SQL Server Management Studio, conecte-se à instância de backup MGC.</span><span class="sxs-lookup"><span data-stu-id="6e2c4-125">Using SQL Server Management Studio, connect to the backup mgc instance.</span></span>
    
    2.  <span data-ttu-id="6e2c4-p105">Clique com o botão direito do mouse no banco de dados mgc, aponte para **Tarefas** e clique em **Fazer Backup**. A caixa de diálogo **Backup de Banco de Dados** será exibida.</span><span class="sxs-lookup"><span data-stu-id="6e2c4-p105">Right-click the mgc database, point to **Tasks**, and then click **Back Up**. The **Back Up Database** dialog box appears.</span></span>
    
    3.  <span data-ttu-id="6e2c4-128">Em **Tipo de backup**, selecione **Completo**.</span><span class="sxs-lookup"><span data-stu-id="6e2c4-128">In **Backup type**, select **Full**.</span></span>
    
    4.  <span data-ttu-id="6e2c4-129">Para **Componente de backup**, clique em **Banco de dados**.</span><span class="sxs-lookup"><span data-stu-id="6e2c4-129">For **Backup component**, click **Database**.</span></span>
    
    5.  <span data-ttu-id="6e2c4-130">Aceite o nome de conjunto de backup padrão sugerido em **Nome** ou insira outro nome para o conjunto de backup.</span><span class="sxs-lookup"><span data-stu-id="6e2c4-130">Either accept the default backup set name suggested in **Name**, or enter a different name for the backup set.</span></span>
    
    6.  <span data-ttu-id="6e2c4-131">\* \<Opcional\> \* Em **Descrição**, insira uma descrição do conjunto de backup.</span><span class="sxs-lookup"><span data-stu-id="6e2c4-131">*\<Optional\>* In **Description**, enter a description of the backup set.</span></span>
    
    7.  <span data-ttu-id="6e2c4-132">Remova o local de backup padrão da lista de destinos.</span><span class="sxs-lookup"><span data-stu-id="6e2c4-132">Remove the default backup location from the destination list.</span></span>
    
    8.  <span data-ttu-id="6e2c4-p106">Adicione um arquivo à lista usando o caminho para o local de compartilhamento estabelecido para o envio de logs. Esse caminho está disponível para o banco de dados primário e para o banco de dados de backup.</span><span class="sxs-lookup"><span data-stu-id="6e2c4-p106">Add a file to the list by using the path to the share location that you established for log shipping. This path is available to the primary database and to the backup database.</span></span>
    
    9.  <span data-ttu-id="6e2c4-135">Clique em **OK** para fechar a caixa de diálogo e iniciar o processo de backup.</span><span class="sxs-lookup"><span data-stu-id="6e2c4-135">Click **OK** to close the dialog box and begin the backup process.</span></span>

4.  <span data-ttu-id="6e2c4-136">Restaure o banco de dados primário usando o banco de dados de backup criado na etapa anterior.</span><span class="sxs-lookup"><span data-stu-id="6e2c4-136">Restore the primary database by using the backup database created in the previous step.</span></span>
    
    1.  <span data-ttu-id="6e2c4-137">Usando o SQL Server Management Studio, conecte-se à instância principal do MGC.</span><span class="sxs-lookup"><span data-stu-id="6e2c4-137">Using SQL Server Management Studio, connect to the primary mgc instance.</span></span>
    
    2.  <span data-ttu-id="6e2c4-p107">Clique com o botão direito do mouse no banco de dados mgc, aponte para **Tarefas**, aponte para **Restaurar** e clique em **Banco de Dados**. A caixa de diálogo **Restaurar Banco de Dados** será exibida.</span><span class="sxs-lookup"><span data-stu-id="6e2c4-p107">Right-click the mgc database, point to **Tasks**, point to **Restore**, and then click **Database**. The **Restore Database** dialog box appears.</span></span>
    
    3.  <span data-ttu-id="6e2c4-140">Selecione **Do dispositivo**.</span><span class="sxs-lookup"><span data-stu-id="6e2c4-140">Select **From Device**.</span></span>
    
    4.  <span data-ttu-id="6e2c4-p108">Clique no botão "procurar", que abrirá a caixa de diálogo **Especificar Backup**. Em **Mídia de backup**, selecione **Arquivo**. Clique em **Adicionar**, selecione o arquivo de backup criado na etapa 3 e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="6e2c4-p108">Click the browse button, which opens the **Specify Backup** dialog box. In **Backup media**, select **File**. Click **Add**, select the backup file that you created in step 3, and then click **OK**.</span></span>
    
    5.  <span data-ttu-id="6e2c4-144">Em **Selecione os conjuntos de backup a serem restaurados**, selecione o backup.</span><span class="sxs-lookup"><span data-stu-id="6e2c4-144">In **Select the backup sets to restore**, select the backup.</span></span>
    
    6.  <span data-ttu-id="6e2c4-145">Clique em **Opções** no painel **Selecionar uma página**.</span><span class="sxs-lookup"><span data-stu-id="6e2c4-145">Click **Options** in the **Select a page** pane.</span></span>
    
    7.  <span data-ttu-id="6e2c4-146">Em **Opções de restauração**, selecione **Substituir o banco de dados existente**.</span><span class="sxs-lookup"><span data-stu-id="6e2c4-146">In **Restore options**, select **Overwrite the existing database**.</span></span>
    
    8.  <span data-ttu-id="6e2c4-147">Em **Estado de recuperação**, selecione **Deixar o banco de dados pronto para uso**.</span><span class="sxs-lookup"><span data-stu-id="6e2c4-147">In **Recovery State**, select **Leave the database ready to use**.</span></span>
    
    9.  <span data-ttu-id="6e2c4-148">Clique em **OK** para iniciar o processo de restauração.</span><span class="sxs-lookup"><span data-stu-id="6e2c4-148">Click **OK** to begin the restoration process.</span></span>

5.  <span data-ttu-id="6e2c4-149">Configure o envio de logs do SQL Server para o banco de dados primário.</span><span class="sxs-lookup"><span data-stu-id="6e2c4-149">Configure SQL Server Log Shipping for the primary database.</span></span> <span data-ttu-id="6e2c4-150">Siga os procedimentos em [Configurando o servidor de chat persistente para alta disponibilidade e recuperação de desastre no Lync Server 2013](lync-server-2013-configuring-persistent-chat-server-for-high-availability-and-disaster-recovery.md) para estabelecer o envio de logs para o banco de dados MGC principal.</span><span class="sxs-lookup"><span data-stu-id="6e2c4-150">Follow the procedures in [Configuring Persistent Chat Server for high availability and disaster recovery in Lync Server 2013](lync-server-2013-configuring-persistent-chat-server-for-high-availability-and-disaster-recovery.md) to establish log shipping for the primary mgc database.</span></span>

6.  <span data-ttu-id="6e2c4-151">Defina os servidores ativos do servidor de chat persistente.</span><span class="sxs-lookup"><span data-stu-id="6e2c4-151">Set the Persistent Chat Server active servers.</span></span> <span data-ttu-id="6e2c4-152">No Shell de gerenciamento do Lync Server, use o cmdlet **set-CsPersistentChatActiveServer** para definir a lista de servidores ativos.</span><span class="sxs-lookup"><span data-stu-id="6e2c4-152">From the Lync Server Management Shell, use the **Set-CsPersistentChatActiveServer** cmdlet to set the list of active servers.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="6e2c4-153">Todos os servidores ativos devem estar localizados dentro do mesmo centro de dados que o novo banco de dados primário ou em um centro de dados que possui uma conexão de baixa latência/alta largura de banda para o banco de dados.</span><span class="sxs-lookup"><span data-stu-id="6e2c4-153">All the active servers must be located within the same data center as the new primary database, or in a data center that has a low latency/high bandwidth connection to the database.</span></span>

    
    </div>

<span data-ttu-id="6e2c4-154">A restauração do pool em seu estado normal execute o seguinte comando do Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="6e2c4-154">The restore the pool to its normal state run the following Windows PowerShell command:</span></span>

    Set-CsPersistentChatState -Identity "service: lyncpc.dci.discovery.com" -PoolState Normal

<span data-ttu-id="6e2c4-155">Consulte o tópico de ajuda para o cmdlet [set-CsPersistentChatState](https://docs.microsoft.com/powershell/module/skype/Set-CsPersistentChatState) para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="6e2c4-155">See the help topic for the [Set-CsPersistentChatState](https://docs.microsoft.com/powershell/module/skype/Set-CsPersistentChatState) cmdlet for more information.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

