---
title: Gerenciar a alta disponibilidade e a recuperação de desastres para o Servidor de Chat Persistente no Skype for Business Server 2015
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 1/31/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 4346e70b-ac48-4ab9-853e-3cdd6dcfe678
description: 'Resumo: Saiba como gerenciar o servidor de Chat persistente alto disponibilidade e recuperação de desastres em Skype para Business Server 2015.'
ms.openlocfilehash: 8bc80ff6a38238b81b658a7f4d9620dc3a56b9be
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/28/2018
---
# <a name="manage-high-availability-and-disaster-recovery-for-persistent-chat-server-in-skype-for-business-server-2015"></a><span data-ttu-id="c2709-103">Gerenciar a alta disponibilidade e a recuperação de desastres para o Servidor de Chat Persistente no Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="c2709-103">Manage high availability and disaster recovery for Persistent Chat Server in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="c2709-104">**Resumo:** Saiba como gerenciar o servidor de Chat persistente alto disponibilidade e recuperação de desastres em Skype para Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="c2709-104">**Summary:** Learn how to manage Persistent Chat Server high availability and disaster recovery in Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="c2709-105">Este tópico descreve como realizar failover e failback volta Persistent Chat Server.</span><span class="sxs-lookup"><span data-stu-id="c2709-105">This topic describes how to fail over and fail back Persistent Chat Server.</span></span> <span data-ttu-id="c2709-106">Antes de ler este tópico, não deixe de ler [Planejar para alta disponibilidade e recuperação de desastres para o servidor de Chat persistente no Skype para Business Server 2015](../../plan-your-deployment/persistent-chat-server/high-availability-and-disaster-recovery.md) e Configure [alta disponibilidade e recuperação de desastres para o servidor de Chat persistente no Skype para Business 2015 de servidor](../../deploy/deploy-persistent-chat-server/configure-hadr-for-persistent-chat.md).</span><span class="sxs-lookup"><span data-stu-id="c2709-106">Before reading this topic, be sure to read [Plan for high availability and disaster recovery for Persistent Chat Server in Skype for Business Server 2015](../../plan-your-deployment/persistent-chat-server/high-availability-and-disaster-recovery.md) and [Configure high availability and disaster recovery for Persistent Chat Server in Skype for Business Server 2015](../../deploy/deploy-persistent-chat-server/configure-hadr-for-persistent-chat.md).</span></span>
  
## <a name="fail-over-persistent-chat-server"></a><span data-ttu-id="c2709-107">Failover de servidor de Chat persistente</span><span class="sxs-lookup"><span data-stu-id="c2709-107">Fail over Persistent Chat Server</span></span>

<span data-ttu-id="c2709-108">Failover para o servidor de Chat persistente foi projetado para ser principalmente um processo manual.</span><span class="sxs-lookup"><span data-stu-id="c2709-108">Failover for Persistent Chat Server is designed to be mainly a manual process.</span></span>
  
<span data-ttu-id="c2709-109">O procedimento de failover está com base na pressuposição de que o Centro de dados secundário é para cima e em execução, mas os serviços de servidor de Chat persistente onde se encontra o banco de dados primário do Chat persistente não estão completamente disponíveis, incluindo o seguinte:</span><span class="sxs-lookup"><span data-stu-id="c2709-109">The failover procedure is based on the assumption that the secondary data center is up and running, but the Persistent Chat Server services where the primary Persistent Chat database is located are completely unavailable, including the following:</span></span>
  
- <span data-ttu-id="c2709-110">Persistent Chat Server banco de dados primário e o banco de dados de espelho Persistent Chat Server estão desativados.</span><span class="sxs-lookup"><span data-stu-id="c2709-110">Persistent Chat Server primary database and Persistent Chat Server mirror database are down.</span></span>
    
- <span data-ttu-id="c2709-111">Skype para o servidor de Front End Business Server está inoperante.</span><span class="sxs-lookup"><span data-stu-id="c2709-111">Skype for Business Server Front End Server is down.</span></span>
    
<span data-ttu-id="c2709-112">O procedimento é baseado em duas etapas básicas:</span><span class="sxs-lookup"><span data-stu-id="c2709-112">The procedure is based on two basic steps:</span></span>
  
- <span data-ttu-id="c2709-113">Recupere o Chat persistente banco de dados primário (mgc).</span><span class="sxs-lookup"><span data-stu-id="c2709-113">Recover the primary Persistent Chat database (mgc).</span></span>
    
- <span data-ttu-id="c2709-114">Estabelecer o espelhamento para o novo banco de dados primário.</span><span class="sxs-lookup"><span data-stu-id="c2709-114">Establish mirroring for the new primary database.</span></span>
    
<span data-ttu-id="c2709-115">O Chat persistente conformidade banco de dados (mgccomp) não tiver feito um failover.</span><span class="sxs-lookup"><span data-stu-id="c2709-115">The Persistent Chat compliance database (mgccomp) is not failed over.</span></span> <span data-ttu-id="c2709-116">O conteúdo deste banco de dados é transitório e é excluído como os processos do adaptador de conformidade dos dados.</span><span class="sxs-lookup"><span data-stu-id="c2709-116">The contents of this database are transient and are purged as the compliance adapter processes the data.</span></span> <span data-ttu-id="c2709-117">É sua responsabilidade, como administrador de Chat persistente, para gerenciar corretamente a saída do adaptador para evitar a perda de dados.</span><span class="sxs-lookup"><span data-stu-id="c2709-117">It is your responsibility, as Persistent Chat Administrator, to correctly manage the adapter output to avoid data loss.</span></span>
  
<span data-ttu-id="c2709-118">Para fazer failover do Servidor de Chat Persistente:</span><span class="sxs-lookup"><span data-stu-id="c2709-118">To fail over Persistent Chat Server:</span></span>
  
1. <span data-ttu-id="c2709-119">Remova o envio de logs do banco de dados Persistent Chat Server Backup envio de Log.</span><span class="sxs-lookup"><span data-stu-id="c2709-119">Remove log shipping from the Persistent Chat Server Backup Log Shipping database.</span></span>
    
  - <span data-ttu-id="c2709-120">Usando o SQL Server Management Studio, conecte-se à instância do banco de dados onde o banco de dados do servidor de Chat persistente mgc de backup está localizado.</span><span class="sxs-lookup"><span data-stu-id="c2709-120">Using SQL Server Management Studio, connect to the database instance where the Persistent Chat Server backup mgc database is located.</span></span>
    
  - <span data-ttu-id="c2709-121">Abra uma janela Consulta para o banco de dados mestre.</span><span class="sxs-lookup"><span data-stu-id="c2709-121">Open a query window to the master database.</span></span>
    
  - <span data-ttu-id="c2709-122">Use o seguinte comando para remover o envio de logs:</span><span class="sxs-lookup"><span data-stu-id="c2709-122">Use the following command to drop log shipping:</span></span>
    
  ```
  exec sp_delete_log_shipping_secondary_database mgc
  ```

2. <span data-ttu-id="c2709-123">Copie qualquer arquivo de backup não copiado do compartilhamento de backup para a pasta de destino da cópia do servidor de backup.</span><span class="sxs-lookup"><span data-stu-id="c2709-123">Copy any uncopied backup files from the backup share to the copy destination folder of the backup server.</span></span>
    
3. <span data-ttu-id="c2709-124">Use qualquer backup de log de transação não aplicado na sequência para o banco de dados secundário.</span><span class="sxs-lookup"><span data-stu-id="c2709-124">Apply any unapplied transaction log backups in sequence to the secondary database.</span></span> <span data-ttu-id="c2709-125">Para obter detalhes, consulte [como: aplicar um Backup do Log de transações (Transact-SQL)](https://go.microsoft.com/fwlink/p/?linkid=247428).</span><span class="sxs-lookup"><span data-stu-id="c2709-125">For details, see [How to: Apply a Transaction Log Backup (Transact-SQL)](https://go.microsoft.com/fwlink/p/?linkid=247428).</span></span>
    
4. <span data-ttu-id="c2709-p104">Coloque o banco de dados mgc de backup online. Usando a janela Consulta que é exibida na etapa 1b, faça o seguinte:</span><span class="sxs-lookup"><span data-stu-id="c2709-p104">Bring the backup mgc database online. Using the query window that opens in step 1b, do the following:</span></span>
    
  - <span data-ttu-id="c2709-128">Encerre todas as conexões com o banco de dados mgc, se houver:</span><span class="sxs-lookup"><span data-stu-id="c2709-128">End all connections to the mgc database, if there are any:</span></span>
    
  - <span data-ttu-id="c2709-129">**exec sp_who2** para identificar as conexões com o banco de dados mgc.</span><span class="sxs-lookup"><span data-stu-id="c2709-129">**exec sp_who2** to identify connections to the mgc database.</span></span>
    
  - <span data-ttu-id="c2709-130">**kill \<spid\> ** para terminar estas conexões.</span><span class="sxs-lookup"><span data-stu-id="c2709-130">**kill \<spid\>** to end these connections.</span></span>
    
  - <span data-ttu-id="c2709-131">Coloque o banco de dados online:</span><span class="sxs-lookup"><span data-stu-id="c2709-131">Bring the database online:</span></span>
    
  - <span data-ttu-id="c2709-132">**Restaurar Banco de Dados mgc com recuperação**.</span><span class="sxs-lookup"><span data-stu-id="c2709-132">**restore database mgc with recovery**.</span></span>
    
5. <span data-ttu-id="c2709-133">No Skype do Shell de gerenciamento do servidor de negócios, use o comando **Set-CsPersistentChatState-Identity "service: atl-cs-001" - PoolState FailedOver** fazer failover para o banco de dados mgc backup.</span><span class="sxs-lookup"><span data-stu-id="c2709-133">In Skype for Business Server Management Shell, use the command **Set-CsPersistentChatState -Identity "service:atl-cs-001.litwareinc.com" -PoolState FailedOver** to fail over to the mgc backup database.</span></span> <span data-ttu-id="c2709-134">Não se esqueça de substituir o nome de domínio totalmente qualificado do seu pool de Chat Persistente por atl-cs-001.litwareinc.com.</span><span class="sxs-lookup"><span data-stu-id="c2709-134">Be sure to substitute the fully qualified domain name of your Persistent Chat pool for atl-cs-001.litwareinc.com.</span></span>
    
    <span data-ttu-id="c2709-135">O banco de dados de backup mgc agora serve como o banco de dados primário.</span><span class="sxs-lookup"><span data-stu-id="c2709-135">The mgc backup database now serves as the primary database.</span></span>
    
6. <span data-ttu-id="c2709-136">No Skype do Shell de gerenciamento do servidor de negócios, use o cmdlet **Install-CsMirrorDatabase** para estabelecer um espelho de alta disponibilidade para o banco de dados de backup que agora serve como o banco de dados primário.</span><span class="sxs-lookup"><span data-stu-id="c2709-136">In Skype for Business Server Management Shell, use the **Install-CsMirrorDatabase** cmdlet to establish a high availability mirror for the backup database that now serves as the primary database.</span></span> <span data-ttu-id="c2709-137">Use a instância do banco de dados de backup como o banco de dados primário e a instância do banco de dados de espelho de backup como a instância do espelho.</span><span class="sxs-lookup"><span data-stu-id="c2709-137">Use the backup database instance as the primary database and the backup mirror database instance as the mirror instance.</span></span> <span data-ttu-id="c2709-138">Este não é o mesmo espelho do que aquele inicialmente configurado para o banco de dados primário durante a configuração.</span><span class="sxs-lookup"><span data-stu-id="c2709-138">This is not the same mirror as the one that was initially configured for the primary database during setup.</span></span>
    
7. <span data-ttu-id="c2709-139">Defina os servidores ativos do servidor de Chat persistente.</span><span class="sxs-lookup"><span data-stu-id="c2709-139">Set the Persistent Chat Server active servers.</span></span> <span data-ttu-id="c2709-140">Do Skype do Shell de gerenciamento do servidor de negócios, use o cmdlet **Set-CsPersistentChatActiveServer** para definir a lista de servidores ativos.</span><span class="sxs-lookup"><span data-stu-id="c2709-140">From the Skype for Business Server Management Shell, use the **Set-CsPersistentChatActiveServer** cmdlet to set the list of active servers.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="c2709-141">Todos os servidores ativos devem estar localizados no mesmo data center que o novo banco de dados primário ou em um data center que tenha uma conexão de baixa latência/alta largura de banda com o banco de dados.</span><span class="sxs-lookup"><span data-stu-id="c2709-141">All the active servers must be located within the same data center as the new primary database, or in a data center that has a low latency/high bandwidth connection to the database.</span></span> 
  
    <span data-ttu-id="c2709-142">Neste ponto, o failover do banco de dados primário Persistent Chat Server para o banco de dados de backup do servidor de Chat persistente for concluída com êxito.</span><span class="sxs-lookup"><span data-stu-id="c2709-142">At this point, the failover from the Persistent Chat Server primary database to the Persistent Chat Server backup database completes successfully.</span></span>
    
## <a name="fail-back-persistent-chat-server"></a><span data-ttu-id="c2709-143">Falha do servidor de bate-papo persistente</span><span class="sxs-lookup"><span data-stu-id="c2709-143">Fail back Persistent Chat Server</span></span>

<span data-ttu-id="c2709-144">Este procedimento descreve as etapas necessárias para recuperar de uma falha do servidor de Chat persistente e restabelecer as operações no data center principal.</span><span class="sxs-lookup"><span data-stu-id="c2709-144">This procedure outlines the steps necessary to recover from a Persistent Chat Server failure, and to reestablish operations from the primary data center.</span></span>
  
<span data-ttu-id="c2709-145">Durante falha do servidor de Chat persistente, data center principal sofre interrupção completa e a principal e bancos de dados de espelho se tornar indisponíveis.</span><span class="sxs-lookup"><span data-stu-id="c2709-145">During Persistent Chat Server failure, the primary data center suffers complete outage, and the primary and mirror databases become unavailable.</span></span> <span data-ttu-id="c2709-146">O data center primário faz failover para o servidor de backup.</span><span class="sxs-lookup"><span data-stu-id="c2709-146">The primary data center fails over to the backup server.</span></span>
  
<span data-ttu-id="c2709-147">O procedimento a seguir restaura a operação normal após o backup do data center primário e a recompilação dos servidores.</span><span class="sxs-lookup"><span data-stu-id="c2709-147">The following procedure restores normal operation after the primary data center is back up, and the servers have been rebuilt.</span></span> <span data-ttu-id="c2709-148">O procedimento pressupõe que o Centro de dados principal foi recuperado de interrupção total e que o banco de dados mgc e o banco de dados mgccomp foram recriados e reinstalados usando o construtor de topologia.</span><span class="sxs-lookup"><span data-stu-id="c2709-148">The procedure assumes that the primary data center has been recovered from total outage, and that the mgc database and the mgccomp database have been rebuilt and reinstalled by using Topology Builder.</span></span>
  
<span data-ttu-id="c2709-149">O procedimento também pressupõe que nenhum servidor espelho ou de backup novo tenha sido implantado durante o período de failover e que o único servidor implantado seja o de backup e seu servidor espelho, conforme definido anteriormente em Failover do Servidor de Chat Persistente.</span><span class="sxs-lookup"><span data-stu-id="c2709-149">The procedure also assumes that no new mirror and backup servers were deployed during the failover period, and that the only server deployed is the backup server and its mirror server, as defined in Fail over Persistent Chat Server previously.</span></span>
  
<span data-ttu-id="c2709-150">Estas etapas foram criadas para recuperar a configuração como ela se encontrava antes do desastre que resultou no failover do servidor primário para o servidor de backup.</span><span class="sxs-lookup"><span data-stu-id="c2709-150">These steps are designed to recover configuration as it existed prior to the disaster, resulting in failover from the primary server to the backup server.</span></span>
  
1. <span data-ttu-id="c2709-151">Desmarque todos os servidores da lista Persistent Chat Server Active Server usando o cmdlet **Set-CsPersistentChatActiveServer** a partir do Skype do Shell de gerenciamento do servidor de negócios.</span><span class="sxs-lookup"><span data-stu-id="c2709-151">Clear all servers from the Persistent Chat Server Active Server list by using the **Set-CsPersistentChatActiveServer** cmdlet from the Skype for Business Server Management Shell.</span></span> <span data-ttu-id="c2709-152">Isso interrompe todos os servidores de bate-papo persistente de se conectar ao banco de dados mgc e o banco de dados mgccomp durante o failback.</span><span class="sxs-lookup"><span data-stu-id="c2709-152">This stops all Persistent Chat Servers from connecting to the mgc database and the mgccomp database during failback.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="c2709-153">O SQL Server agent no secundário Persistent Chat Server servidor Back-End deve estar executando em uma conta privilegiada.</span><span class="sxs-lookup"><span data-stu-id="c2709-153">The SQL Server agent on the secondary Persistent Chat Server Back End Server should be running under a privileged account.</span></span> <span data-ttu-id="c2709-154">Em termos específicos, a conta deve incluir:</span><span class="sxs-lookup"><span data-stu-id="c2709-154">Specifically, the account must include:</span></span> 
  
   - <span data-ttu-id="c2709-155">Acesso de leitura ao compartilhamento de rede no qual os backups serão colocados.</span><span class="sxs-lookup"><span data-stu-id="c2709-155">Read access to the network share that backups are being placed in.</span></span>
    
   - <span data-ttu-id="c2709-156">Acesso para gravação ao diretório local específico em que os backups serão copiados.</span><span class="sxs-lookup"><span data-stu-id="c2709-156">Write access to the specific local directory that the backups are being copied to.</span></span>
    
2. <span data-ttu-id="c2709-157">Desabilite o espelhamento no banco de dados mgc de backup:</span><span class="sxs-lookup"><span data-stu-id="c2709-157">Disable mirroring on the backup mgc database:</span></span>
    
   - <span data-ttu-id="c2709-158">Usando o SQL Server Management Studio, conecte-se à instância mgc de backup.</span><span class="sxs-lookup"><span data-stu-id="c2709-158">Using SQL Server Management Studio, connect to the backup mgc instance.</span></span>
    
   - <span data-ttu-id="c2709-159">Clique com o botão direito do mouse no banco de dados mgc, aponte para **Tarefas** e clique em **Espelhar**.</span><span class="sxs-lookup"><span data-stu-id="c2709-159">Right-click the mgc database, point to **Tasks**, and then click **Mirror**.</span></span>
    
   - <span data-ttu-id="c2709-160">Clique em **Remover Espelhamento**.</span><span class="sxs-lookup"><span data-stu-id="c2709-160">Click **Remove Mirroring**.</span></span>
    
   - <span data-ttu-id="c2709-161">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="c2709-161">Click **OK**.</span></span>
    
   - <span data-ttu-id="c2709-162">Execute as mesmas etapas com o banco de dados mgccomp.</span><span class="sxs-lookup"><span data-stu-id="c2709-162">Perform the same steps with the mgccomp database.</span></span>
    
3. <span data-ttu-id="c2709-163">Faça backup do banco de dados mgc para que ele possa ser restaurado para o novo banco de dados primário:</span><span class="sxs-lookup"><span data-stu-id="c2709-163">Back up the mgc database so that it can be restored to the new primary database:</span></span>
    
   - <span data-ttu-id="c2709-164">Usando o SQL Server Management Studio, conecte-se à instância mgc de backup.</span><span class="sxs-lookup"><span data-stu-id="c2709-164">Using SQL Server Management Studio, connect to the backup mgc instance.</span></span>
    
   - <span data-ttu-id="c2709-p112">Clique com o botão direito do mouse no banco de dados mgc, aponte para **Tarefas** e clique em **Fazer Backup**. A caixa de diálogo **Backup de Banco de Dados** será exibida.</span><span class="sxs-lookup"><span data-stu-id="c2709-p112">Right-click the mgc database, point to **Tasks**, and then click **Back Up**. The **Back Up Database** dialog box appears.</span></span>
    
   - <span data-ttu-id="c2709-167">Em **Tipo de backup**, selecione **Completo**.</span><span class="sxs-lookup"><span data-stu-id="c2709-167">In **Backup type**, select **Full**.</span></span>
    
   - <span data-ttu-id="c2709-168">Para **Componente de backup**, clique em **Banco de dados**.</span><span class="sxs-lookup"><span data-stu-id="c2709-168">For **Backup component**, click **Database**.</span></span>
    
   - <span data-ttu-id="c2709-169">Aceite o nome de conjunto de backup padrão sugerido em **Nome** ou insira outro nome para o conjunto de backup.</span><span class="sxs-lookup"><span data-stu-id="c2709-169">Either accept the default backup set name suggested in **Name**, or enter a different name for the backup set.</span></span>
    
   -  <span data-ttu-id="c2709-170">* \<Opcional\> *  Em **Descrição**, digite uma descrição do conjunto de backup.</span><span class="sxs-lookup"><span data-stu-id="c2709-170">*\<Optional\>*  In **Description**, enter a description of the backup set.</span></span>
    
   - <span data-ttu-id="c2709-171">Remova o local de backup padrão da lista de destino.</span><span class="sxs-lookup"><span data-stu-id="c2709-171">Remove the default backup location from the destination list.</span></span>
    
   - <span data-ttu-id="c2709-p113">Adicione um arquivo à lista usando o caminho para o local de compartilhamento estabelecido para o envio de logs. Esse caminho está disponível para o banco de dados primário e para o banco de dados de backup.</span><span class="sxs-lookup"><span data-stu-id="c2709-p113">Add a file to the list by using the path to the share location that you established for log shipping. This path is available to the primary database and to the backup database.</span></span>
    
   - <span data-ttu-id="c2709-174">Clique em **OK** para fechar a caixa de diálogo e iniciar o processo de backup.</span><span class="sxs-lookup"><span data-stu-id="c2709-174">Click **OK** to close the dialog box and begin the backup process.</span></span>
    
4. <span data-ttu-id="c2709-175">Restaure o banco de dados primário usando o banco de dados de backup criado na etapa anterior.</span><span class="sxs-lookup"><span data-stu-id="c2709-175">Restore the primary database by using the backup database created in the previous step.</span></span>
    
   - <span data-ttu-id="c2709-176">Usando o SQL Server Management Studio, conecte-se à instância mgc primária.</span><span class="sxs-lookup"><span data-stu-id="c2709-176">Using SQL Server Management Studio, connect to the primary mgc instance.</span></span>
    
   - <span data-ttu-id="c2709-p114">Clique com o botão direito do mouse no banco de dados mgc, aponte para **Tarefas**, aponte para **Restaurar** e clique em **Banco de Dados**. A caixa de diálogo **Restaurar Banco de Dados** será exibida.</span><span class="sxs-lookup"><span data-stu-id="c2709-p114">Right-click the mgc database, point to **Tasks**, point to **Restore**, and then click **Database**. The **Restore Database** dialog box appears.</span></span>
    
   - <span data-ttu-id="c2709-179">Selecione **Do dispositivo**.</span><span class="sxs-lookup"><span data-stu-id="c2709-179">Select **From Device**.</span></span>
    
   - <span data-ttu-id="c2709-p115">Clique no botão Procurar, que abrirá a caixa de diálogo **Especificar Backup**. Em **Mídia de backup**, selecione **Arquivo**. Clique em **Adicionar**, selecione o arquivo de backup criado na etapa 3 e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="c2709-p115">Click the browse button, which opens the **Specify Backup** dialog box. In **Backup media**, select **File**. Click **Add**, select the backup file that you created in step 3, and then click **OK**.</span></span>
    
   - <span data-ttu-id="c2709-183">Em **Selecione os conjuntos de backup a serem restaurados**, selecione o backup.</span><span class="sxs-lookup"><span data-stu-id="c2709-183">In **Select the backup sets to restore**, select the backup.</span></span>
    
   - <span data-ttu-id="c2709-184">Clique em **Opções** no painel **Selecionar uma página**.</span><span class="sxs-lookup"><span data-stu-id="c2709-184">Click **Options** in the **Select a page** pane.</span></span>
    
   - <span data-ttu-id="c2709-185">Em **Opções de restauração**, selecione **Substituir o banco de dados existente**.</span><span class="sxs-lookup"><span data-stu-id="c2709-185">In **Restore options**, select **Overwrite the existing database**.</span></span>
    
   - <span data-ttu-id="c2709-186">Em **Estado de recuperação**, selecione **Deixar o banco de dados pronto para uso**.</span><span class="sxs-lookup"><span data-stu-id="c2709-186">In **Recovery State**, select **Leave the database ready to use**.</span></span>
    
   - <span data-ttu-id="c2709-187">Clique em **OK** para iniciar o processo de restauração.</span><span class="sxs-lookup"><span data-stu-id="c2709-187">Click **OK** to begin the restoration process.</span></span>
    
5. <span data-ttu-id="c2709-188">Configure o envio de Log do SQL Server para o banco de dados primário.</span><span class="sxs-lookup"><span data-stu-id="c2709-188">Configure SQL Server Log Shipping for the primary database.</span></span> <span data-ttu-id="c2709-189">Siga os procedimentos em [Configure alta disponibilidade e recuperação de desastres para o servidor de Chat persistente no Skype para Business Server 2015](../../deploy/deploy-persistent-chat-server/configure-hadr-for-persistent-chat.md) para estabelecer o envio de logs do banco de dados mgc primária.</span><span class="sxs-lookup"><span data-stu-id="c2709-189">Follow the procedures in [Configure high availability and disaster recovery for Persistent Chat Server in Skype for Business Server 2015](../../deploy/deploy-persistent-chat-server/configure-hadr-for-persistent-chat.md) to establish log shipping for the primary mgc database.</span></span>
    
6. <span data-ttu-id="c2709-190">Defina os servidores ativos do servidor de Chat persistente.</span><span class="sxs-lookup"><span data-stu-id="c2709-190">Set the Persistent Chat Server active servers.</span></span> <span data-ttu-id="c2709-191">Do Skype do Shell de gerenciamento do servidor de negócios, use o cmdlet **Set-CsPersistentChatActiveServer** para definir a lista de servidores ativos.</span><span class="sxs-lookup"><span data-stu-id="c2709-191">From the Skype for Business Server Management Shell, use the **Set-CsPersistentChatActiveServer** cmdlet to set the list of active servers.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="c2709-192">Todos os servidores ativos devem estar localizados no mesmo data center que o novo banco de dados primário ou em um data center que tenha uma conexão de baixa latência/alta largura de banda com o banco de dados.</span><span class="sxs-lookup"><span data-stu-id="c2709-192">All the active servers must be located within the same data center as the new primary database, or in a data center that has a low latency/high bandwidth connection to the database.</span></span> 
  
<span data-ttu-id="c2709-193">Para restaurar o pool ao seu estado normal, execute o seguinte comando do Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="c2709-193">To restore the pool to its normal state run the following Windows PowerShell command:</span></span>
  
```
Set-CsPersistentChatState -Identity "service: lyncpc.dci.discovery.com" -PoolState Normal
```

<span data-ttu-id="c2709-194">Para obter mais informações, consulte o tópico de ajuda para o cmdlet [Set-CsPersistentChatState](https://docs.microsoft.com/powershell/module/skype/set-cspersistentchatstate?view=skype-ps) .</span><span class="sxs-lookup"><span data-stu-id="c2709-194">For more information, see the help topic for the [Set-CsPersistentChatState](https://docs.microsoft.com/powershell/module/skype/set-cspersistentchatstate?view=skype-ps) cmdlet.</span></span>
  

