---
title: Gerenciar a alta disponibilidade e a recuperação de desastres para o Servidor de Chat Persistente no Skype for Business Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 1/31/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 4346e70b-ac48-4ab9-853e-3cdd6dcfe678
description: 'Resumo: Saiba como gerenciar o servidor de Chat persistente alto disponibilidade e recuperação de desastres em Skype para Business Server 2015.'
ms.openlocfilehash: 8e2b9cecef2a3598c318ab8a758c99eb2caf40e7
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "33910344"
---
# <a name="manage-high-availability-and-disaster-recovery-for-persistent-chat-server-in-skype-for-business-server-2015"></a><span data-ttu-id="0c2e8-103">Gerenciar a alta disponibilidade e a recuperação de desastres para o Servidor de Chat Persistente no Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="0c2e8-103">Manage high availability and disaster recovery for Persistent Chat Server in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="0c2e8-104">**Resumo:** Saiba como gerenciar o servidor de Chat persistente alto disponibilidade e recuperação de desastres em Skype para Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="0c2e8-104">**Summary:** Learn how to manage Persistent Chat Server high availability and disaster recovery in Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="0c2e8-105">Este tópico descreve como realizar failover e failback volta Persistent Chat Server.</span><span class="sxs-lookup"><span data-stu-id="0c2e8-105">This topic describes how to fail over and fail back Persistent Chat Server.</span></span> <span data-ttu-id="0c2e8-106">Antes de ler este tópico, não deixe de ler [Planejar para alta disponibilidade e recuperação de desastres para o servidor de Chat persistente no Skype para Business Server 2015](../../plan-your-deployment/persistent-chat-server/high-availability-and-disaster-recovery.md) e Configure [alta disponibilidade e recuperação de desastres para o servidor de Chat persistente no Skype para Business 2015 de servidor](../../deploy/deploy-persistent-chat-server/configure-hadr-for-persistent-chat.md).</span><span class="sxs-lookup"><span data-stu-id="0c2e8-106">Before reading this topic, be sure to read [Plan for high availability and disaster recovery for Persistent Chat Server in Skype for Business Server 2015](../../plan-your-deployment/persistent-chat-server/high-availability-and-disaster-recovery.md) and [Configure high availability and disaster recovery for Persistent Chat Server in Skype for Business Server 2015](../../deploy/deploy-persistent-chat-server/configure-hadr-for-persistent-chat.md).</span></span>

> [!NOTE]
> <span data-ttu-id="0c2e8-107">Bate-papo persistente está disponível no Skype para Business Server 2015, mas não é mais suportado no Skype para Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="0c2e8-107">Persistent chat is available in Skype for Business Server 2015 but is no longer supported in Skype for Business Server 2019.</span></span> <span data-ttu-id="0c2e8-108">A mesma funcionalidade está disponível em equipes.</span><span class="sxs-lookup"><span data-stu-id="0c2e8-108">The same functionality is available in Teams.</span></span> <span data-ttu-id="0c2e8-109">Para obter mais informações, consulte [jornada do Skype para negócios às equipes da Microsoft](/microsoftteams/journey-skypeforbusiness-teams).</span><span class="sxs-lookup"><span data-stu-id="0c2e8-109">For more information, see [Journey from Skype for Business to Microsoft Teams](/microsoftteams/journey-skypeforbusiness-teams).</span></span> <span data-ttu-id="0c2e8-110">Se você precisar utilizar o chat persistente, suas opções são para migrar tanto os usuários que requerem essa funcionalidade para equipes ou para continuar usando o Skype para Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="0c2e8-110">If you need to use Persistent chat, your choices are to either migrate users requiring this functionality to Teams, or to continue using Skype for Business Server 2015.</span></span> 
  
## <a name="fail-over-persistent-chat-server"></a><span data-ttu-id="0c2e8-111">Failover de servidor de Chat persistente</span><span class="sxs-lookup"><span data-stu-id="0c2e8-111">Fail over Persistent Chat Server</span></span>

<span data-ttu-id="0c2e8-112">Failover para o servidor de Chat persistente foi projetado para ser principalmente um processo manual.</span><span class="sxs-lookup"><span data-stu-id="0c2e8-112">Failover for Persistent Chat Server is designed to be mainly a manual process.</span></span>
  
<span data-ttu-id="0c2e8-113">O procedimento de failover está com base na pressuposição de que o Centro de dados secundário é para cima e em execução, mas os serviços de servidor de Chat persistente onde se encontra o banco de dados primário do Chat persistente não estão completamente disponíveis, incluindo o seguinte:</span><span class="sxs-lookup"><span data-stu-id="0c2e8-113">The failover procedure is based on the assumption that the secondary data center is up and running, but the Persistent Chat Server services where the primary Persistent Chat database is located are completely unavailable, including the following:</span></span>
  
- <span data-ttu-id="0c2e8-114">Persistent Chat Server banco de dados primário e o banco de dados de espelho Persistent Chat Server estão desativados.</span><span class="sxs-lookup"><span data-stu-id="0c2e8-114">Persistent Chat Server primary database and Persistent Chat Server mirror database are down.</span></span>
    
- <span data-ttu-id="0c2e8-115">Skype para o servidor de Front End Business Server está inoperante.</span><span class="sxs-lookup"><span data-stu-id="0c2e8-115">Skype for Business Server Front End Server is down.</span></span>
    
<span data-ttu-id="0c2e8-116">O procedimento é baseado em duas etapas básicas:</span><span class="sxs-lookup"><span data-stu-id="0c2e8-116">The procedure is based on two basic steps:</span></span>
  
- <span data-ttu-id="0c2e8-117">Recupere o Chat persistente banco de dados primário (mgc).</span><span class="sxs-lookup"><span data-stu-id="0c2e8-117">Recover the primary Persistent Chat database (mgc).</span></span>
    
- <span data-ttu-id="0c2e8-118">Estabelecer o espelhamento para o novo banco de dados primário.</span><span class="sxs-lookup"><span data-stu-id="0c2e8-118">Establish mirroring for the new primary database.</span></span>
    
<span data-ttu-id="0c2e8-119">O Chat persistente conformidade banco de dados (mgccomp) não tiver feito um failover.</span><span class="sxs-lookup"><span data-stu-id="0c2e8-119">The Persistent Chat compliance database (mgccomp) is not failed over.</span></span> <span data-ttu-id="0c2e8-120">O conteúdo deste banco de dados é transitório e é excluído como os processos do adaptador de conformidade dos dados.</span><span class="sxs-lookup"><span data-stu-id="0c2e8-120">The contents of this database are transient and are purged as the compliance adapter processes the data.</span></span> <span data-ttu-id="0c2e8-121">É sua responsabilidade, como administrador de Chat persistente, para gerenciar corretamente a saída do adaptador para evitar a perda de dados.</span><span class="sxs-lookup"><span data-stu-id="0c2e8-121">It is your responsibility, as Persistent Chat Administrator, to correctly manage the adapter output to avoid data loss.</span></span>
  
<span data-ttu-id="0c2e8-122">Para fazer failover do Servidor de Chat Persistente:</span><span class="sxs-lookup"><span data-stu-id="0c2e8-122">To fail over Persistent Chat Server:</span></span>
  
1. <span data-ttu-id="0c2e8-123">Remova o envio de logs do banco de dados Persistent Chat Server Backup envio de Log.</span><span class="sxs-lookup"><span data-stu-id="0c2e8-123">Remove log shipping from the Persistent Chat Server Backup Log Shipping database.</span></span>
    
   - <span data-ttu-id="0c2e8-124">Usando o SQL Server Management Studio, conecte-se à instância do banco de dados onde o banco de dados do servidor de Chat persistente mgc de backup está localizado.</span><span class="sxs-lookup"><span data-stu-id="0c2e8-124">Using SQL Server Management Studio, connect to the database instance where the Persistent Chat Server backup mgc database is located.</span></span>
    
   - <span data-ttu-id="0c2e8-125">Abra uma janela Consulta para o banco de dados mestre.</span><span class="sxs-lookup"><span data-stu-id="0c2e8-125">Open a query window to the master database.</span></span>
    
   - <span data-ttu-id="0c2e8-126">Use o seguinte comando para remover o envio de logs:</span><span class="sxs-lookup"><span data-stu-id="0c2e8-126">Use the following command to drop log shipping:</span></span>
    
   ```
   exec sp_delete_log_shipping_secondary_database mgc
   ```

2. <span data-ttu-id="0c2e8-127">Copie qualquer arquivo de backup não copiado do compartilhamento de backup para a pasta de destino da cópia do servidor de backup.</span><span class="sxs-lookup"><span data-stu-id="0c2e8-127">Copy any uncopied backup files from the backup share to the copy destination folder of the backup server.</span></span>
    
3. <span data-ttu-id="0c2e8-128">Use qualquer backup de log de transação não aplicado na sequência para o banco de dados secundário.</span><span class="sxs-lookup"><span data-stu-id="0c2e8-128">Apply any unapplied transaction log backups in sequence to the secondary database.</span></span> <span data-ttu-id="0c2e8-129">Para obter detalhes, consulte [como: aplicar um Backup do Log de transações (Transact-SQL)](https://go.microsoft.com/fwlink/p/?linkid=247428).</span><span class="sxs-lookup"><span data-stu-id="0c2e8-129">For details, see [How to: Apply a Transaction Log Backup (Transact-SQL)](https://go.microsoft.com/fwlink/p/?linkid=247428).</span></span>
    
4. <span data-ttu-id="0c2e8-p105">Coloque o banco de dados mgc de backup online. Usando a janela Consulta que é exibida na etapa 1b, faça o seguinte:</span><span class="sxs-lookup"><span data-stu-id="0c2e8-p105">Bring the backup mgc database online. Using the query window that opens in step 1b, do the following:</span></span>
    
   - <span data-ttu-id="0c2e8-132">Encerre todas as conexões com o banco de dados mgc, se houver:</span><span class="sxs-lookup"><span data-stu-id="0c2e8-132">End all connections to the mgc database, if there are any:</span></span>
    
   - <span data-ttu-id="0c2e8-133">**exec sp_who2** para identificar as conexões com o banco de dados mgc.</span><span class="sxs-lookup"><span data-stu-id="0c2e8-133">**exec sp_who2** to identify connections to the mgc database.</span></span>
    
   - <span data-ttu-id="0c2e8-134">\*\*kill \<spid\> \*\* para terminar estas conexões.</span><span class="sxs-lookup"><span data-stu-id="0c2e8-134">**kill \<spid\>** to end these connections.</span></span>
    
   - <span data-ttu-id="0c2e8-135">Coloque o banco de dados online:</span><span class="sxs-lookup"><span data-stu-id="0c2e8-135">Bring the database online:</span></span>
    
   - <span data-ttu-id="0c2e8-136">**Restaurar Banco de Dados mgc com recuperação**.</span><span class="sxs-lookup"><span data-stu-id="0c2e8-136">**restore database mgc with recovery**.</span></span>
    
5. <span data-ttu-id="0c2e8-137">No Skype do Shell de gerenciamento do servidor de negócios, use o comando **Set-CsPersistentChatState-Identity "service: atl-cs-001" - PoolState FailedOver** fazer failover para o banco de dados mgc backup.</span><span class="sxs-lookup"><span data-stu-id="0c2e8-137">In Skype for Business Server Management Shell, use the command **Set-CsPersistentChatState -Identity "service:atl-cs-001.litwareinc.com" -PoolState FailedOver** to fail over to the mgc backup database.</span></span> <span data-ttu-id="0c2e8-138">Não se esqueça de substituir o nome de domínio totalmente qualificado do seu pool de Chat Persistente por atl-cs-001.litwareinc.com.</span><span class="sxs-lookup"><span data-stu-id="0c2e8-138">Be sure to substitute the fully qualified domain name of your Persistent Chat pool for atl-cs-001.litwareinc.com.</span></span>
    
    <span data-ttu-id="0c2e8-139">O banco de dados de backup mgc agora serve como o banco de dados primário.</span><span class="sxs-lookup"><span data-stu-id="0c2e8-139">The mgc backup database now serves as the primary database.</span></span>
    
6. <span data-ttu-id="0c2e8-140">No Skype do Shell de gerenciamento do servidor de negócios, use o cmdlet **Install-CsMirrorDatabase** para estabelecer um espelho de alta disponibilidade para o banco de dados de backup que agora serve como o banco de dados primário.</span><span class="sxs-lookup"><span data-stu-id="0c2e8-140">In Skype for Business Server Management Shell, use the **Install-CsMirrorDatabase** cmdlet to establish a high availability mirror for the backup database that now serves as the primary database.</span></span> <span data-ttu-id="0c2e8-141">Use a instância do banco de dados de backup como o banco de dados primário e a instância do banco de dados de espelho de backup como a instância do espelho.</span><span class="sxs-lookup"><span data-stu-id="0c2e8-141">Use the backup database instance as the primary database and the backup mirror database instance as the mirror instance.</span></span> <span data-ttu-id="0c2e8-142">Este não é o mesmo espelho do que aquele inicialmente configurado para o banco de dados primário durante a configuração.</span><span class="sxs-lookup"><span data-stu-id="0c2e8-142">This is not the same mirror as the one that was initially configured for the primary database during setup.</span></span>
    
7. <span data-ttu-id="0c2e8-143">Defina os servidores ativos do servidor de Chat persistente.</span><span class="sxs-lookup"><span data-stu-id="0c2e8-143">Set the Persistent Chat Server active servers.</span></span> <span data-ttu-id="0c2e8-144">Do Skype do Shell de gerenciamento do servidor de negócios, use o cmdlet **Set-CsPersistentChatActiveServer** para definir a lista de servidores ativos.</span><span class="sxs-lookup"><span data-stu-id="0c2e8-144">From the Skype for Business Server Management Shell, use the **Set-CsPersistentChatActiveServer** cmdlet to set the list of active servers.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="0c2e8-145">Todos os servidores ativos devem estar localizados no mesmo data center que o novo banco de dados primário ou em um data center que tenha uma conexão de baixa latência/alta largura de banda com o banco de dados.</span><span class="sxs-lookup"><span data-stu-id="0c2e8-145">All the active servers must be located within the same data center as the new primary database, or in a data center that has a low latency/high bandwidth connection to the database.</span></span> 
  
    <span data-ttu-id="0c2e8-146">Neste ponto, o failover do banco de dados primário Persistent Chat Server para o banco de dados de backup do servidor de Chat persistente for concluída com êxito.</span><span class="sxs-lookup"><span data-stu-id="0c2e8-146">At this point, the failover from the Persistent Chat Server primary database to the Persistent Chat Server backup database completes successfully.</span></span>
    
## <a name="fail-back-persistent-chat-server"></a><span data-ttu-id="0c2e8-147">Falha do servidor de bate-papo persistente</span><span class="sxs-lookup"><span data-stu-id="0c2e8-147">Fail back Persistent Chat Server</span></span>

<span data-ttu-id="0c2e8-148">Este procedimento descreve as etapas necessárias para recuperar de uma falha do servidor de Chat persistente e restabelecer as operações no data center principal.</span><span class="sxs-lookup"><span data-stu-id="0c2e8-148">This procedure outlines the steps necessary to recover from a Persistent Chat Server failure, and to reestablish operations from the primary data center.</span></span>
  
<span data-ttu-id="0c2e8-149">Durante falha do servidor de Chat persistente, data center principal sofre interrupção completa e a principal e bancos de dados de espelho se tornar indisponíveis.</span><span class="sxs-lookup"><span data-stu-id="0c2e8-149">During Persistent Chat Server failure, the primary data center suffers complete outage, and the primary and mirror databases become unavailable.</span></span> <span data-ttu-id="0c2e8-150">O data center primário faz failover para o servidor de backup.</span><span class="sxs-lookup"><span data-stu-id="0c2e8-150">The primary data center fails over to the backup server.</span></span>
  
<span data-ttu-id="0c2e8-151">O procedimento a seguir restaura a operação normal após o backup do data center primário e a recompilação dos servidores.</span><span class="sxs-lookup"><span data-stu-id="0c2e8-151">The following procedure restores normal operation after the primary data center is back up, and the servers have been rebuilt.</span></span> <span data-ttu-id="0c2e8-152">O procedimento pressupõe que o Centro de dados principal foi recuperado de interrupção total e que o banco de dados mgc e o banco de dados mgccomp foram recriados e reinstalados usando o construtor de topologia.</span><span class="sxs-lookup"><span data-stu-id="0c2e8-152">The procedure assumes that the primary data center has been recovered from total outage, and that the mgc database and the mgccomp database have been rebuilt and reinstalled by using Topology Builder.</span></span>
  
<span data-ttu-id="0c2e8-153">O procedimento também pressupõe que nenhum servidor espelho ou de backup novo tenha sido implantado durante o período de failover e que o único servidor implantado seja o de backup e seu servidor espelho, conforme definido anteriormente em Failover do Servidor de Chat Persistente.</span><span class="sxs-lookup"><span data-stu-id="0c2e8-153">The procedure also assumes that no new mirror and backup servers were deployed during the failover period, and that the only server deployed is the backup server and its mirror server, as defined in Fail over Persistent Chat Server previously.</span></span>
  
<span data-ttu-id="0c2e8-154">Estas etapas foram criadas para recuperar a configuração como ela se encontrava antes do desastre que resultou no failover do servidor primário para o servidor de backup.</span><span class="sxs-lookup"><span data-stu-id="0c2e8-154">These steps are designed to recover configuration as it existed prior to the disaster, resulting in failover from the primary server to the backup server.</span></span>
  
1. <span data-ttu-id="0c2e8-155">Desmarque todos os servidores da lista Persistent Chat Server Active Server usando o cmdlet **Set-CsPersistentChatActiveServer** a partir do Skype do Shell de gerenciamento do servidor de negócios.</span><span class="sxs-lookup"><span data-stu-id="0c2e8-155">Clear all servers from the Persistent Chat Server Active Server list by using the **Set-CsPersistentChatActiveServer** cmdlet from the Skype for Business Server Management Shell.</span></span> <span data-ttu-id="0c2e8-156">Isso interrompe todos os servidores de bate-papo persistente de se conectar ao banco de dados mgc e o banco de dados mgccomp durante o failback.</span><span class="sxs-lookup"><span data-stu-id="0c2e8-156">This stops all Persistent Chat Servers from connecting to the mgc database and the mgccomp database during failback.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="0c2e8-157">O SQL Server agent no secundário Persistent Chat Server servidor Back-End deve estar executando em uma conta privilegiada.</span><span class="sxs-lookup"><span data-stu-id="0c2e8-157">The SQL Server agent on the secondary Persistent Chat Server Back End Server should be running under a privileged account.</span></span> <span data-ttu-id="0c2e8-158">Em termos específicos, a conta deve incluir:</span><span class="sxs-lookup"><span data-stu-id="0c2e8-158">Specifically, the account must include:</span></span> 
  
   - <span data-ttu-id="0c2e8-159">Acesso de leitura ao compartilhamento de rede no qual os backups serão colocados.</span><span class="sxs-lookup"><span data-stu-id="0c2e8-159">Read access to the network share that backups are being placed in.</span></span>
    
   - <span data-ttu-id="0c2e8-160">Acesso para gravação ao diretório local específico em que os backups serão copiados.</span><span class="sxs-lookup"><span data-stu-id="0c2e8-160">Write access to the specific local directory that the backups are being copied to.</span></span>
    
2. <span data-ttu-id="0c2e8-161">Desabilite o espelhamento no banco de dados mgc de backup:</span><span class="sxs-lookup"><span data-stu-id="0c2e8-161">Disable mirroring on the backup mgc database:</span></span>
    
   - <span data-ttu-id="0c2e8-162">Usando o SQL Server Management Studio, conecte-se à instância mgc de backup.</span><span class="sxs-lookup"><span data-stu-id="0c2e8-162">Using SQL Server Management Studio, connect to the backup mgc instance.</span></span>
    
   - <span data-ttu-id="0c2e8-163">Clique com o botão direito do mouse no banco de dados mgc, aponte para **Tarefas** e clique em **Espelhar**.</span><span class="sxs-lookup"><span data-stu-id="0c2e8-163">Right-click the mgc database, point to **Tasks**, and then click **Mirror**.</span></span>
    
   - <span data-ttu-id="0c2e8-164">Clique em **Remover Espelhamento**.</span><span class="sxs-lookup"><span data-stu-id="0c2e8-164">Click **Remove Mirroring**.</span></span>
    
   - <span data-ttu-id="0c2e8-165">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="0c2e8-165">Click **OK**.</span></span>
    
   - <span data-ttu-id="0c2e8-166">Execute as mesmas etapas com o banco de dados mgccomp.</span><span class="sxs-lookup"><span data-stu-id="0c2e8-166">Perform the same steps with the mgccomp database.</span></span>
    
3. <span data-ttu-id="0c2e8-167">Faça backup do banco de dados mgc para que ele possa ser restaurado para o novo banco de dados primário:</span><span class="sxs-lookup"><span data-stu-id="0c2e8-167">Back up the mgc database so that it can be restored to the new primary database:</span></span>
    
   - <span data-ttu-id="0c2e8-168">Usando o SQL Server Management Studio, conecte-se à instância mgc de backup.</span><span class="sxs-lookup"><span data-stu-id="0c2e8-168">Using SQL Server Management Studio, connect to the backup mgc instance.</span></span>
    
   - <span data-ttu-id="0c2e8-p113">Clique com o botão direito do mouse no banco de dados mgc, aponte para **Tarefas** e clique em **Fazer Backup**. A caixa de diálogo **Backup de Banco de Dados** será exibida.</span><span class="sxs-lookup"><span data-stu-id="0c2e8-p113">Right-click the mgc database, point to **Tasks**, and then click **Back Up**. The **Back Up Database** dialog box appears.</span></span>
    
   - <span data-ttu-id="0c2e8-171">Em **Tipo de backup**, selecione **Completo**.</span><span class="sxs-lookup"><span data-stu-id="0c2e8-171">In **Backup type**, select **Full**.</span></span>
    
   - <span data-ttu-id="0c2e8-172">Para **Componente de backup**, clique em **Banco de dados**.</span><span class="sxs-lookup"><span data-stu-id="0c2e8-172">For **Backup component**, click **Database**.</span></span>
    
   - <span data-ttu-id="0c2e8-173">Aceite o nome de conjunto de backup padrão sugerido em **Nome** ou insira outro nome para o conjunto de backup.</span><span class="sxs-lookup"><span data-stu-id="0c2e8-173">Either accept the default backup set name suggested in **Name**, or enter a different name for the backup set.</span></span>
    
   -  <span data-ttu-id="0c2e8-174">\* \<Opcional\> \*  Em **Descrição**, digite uma descrição do conjunto de backup.</span><span class="sxs-lookup"><span data-stu-id="0c2e8-174">*\<Optional\>*  In **Description**, enter a description of the backup set.</span></span>
    
   - <span data-ttu-id="0c2e8-175">Remova o local de backup padrão da lista de destino.</span><span class="sxs-lookup"><span data-stu-id="0c2e8-175">Remove the default backup location from the destination list.</span></span>
    
   - <span data-ttu-id="0c2e8-p114">Adicione um arquivo à lista usando o caminho para o local de compartilhamento estabelecido para o envio de logs. Esse caminho está disponível para o banco de dados primário e para o banco de dados de backup.</span><span class="sxs-lookup"><span data-stu-id="0c2e8-p114">Add a file to the list by using the path to the share location that you established for log shipping. This path is available to the primary database and to the backup database.</span></span>
    
   - <span data-ttu-id="0c2e8-178">Clique em **OK** para fechar a caixa de diálogo e iniciar o processo de backup.</span><span class="sxs-lookup"><span data-stu-id="0c2e8-178">Click **OK** to close the dialog box and begin the backup process.</span></span>
    
4. <span data-ttu-id="0c2e8-179">Restaure o banco de dados primário usando o banco de dados de backup criado na etapa anterior.</span><span class="sxs-lookup"><span data-stu-id="0c2e8-179">Restore the primary database by using the backup database created in the previous step.</span></span>
    
   - <span data-ttu-id="0c2e8-180">Usando o SQL Server Management Studio, conecte-se à instância mgc primária.</span><span class="sxs-lookup"><span data-stu-id="0c2e8-180">Using SQL Server Management Studio, connect to the primary mgc instance.</span></span>
    
   - <span data-ttu-id="0c2e8-p115">Clique com o botão direito do mouse no banco de dados mgc, aponte para **Tarefas**, aponte para **Restaurar** e clique em **Banco de Dados**. A caixa de diálogo **Restaurar Banco de Dados** será exibida.</span><span class="sxs-lookup"><span data-stu-id="0c2e8-p115">Right-click the mgc database, point to **Tasks**, point to **Restore**, and then click **Database**. The **Restore Database** dialog box appears.</span></span>
    
   - <span data-ttu-id="0c2e8-183">Selecione **Do dispositivo**.</span><span class="sxs-lookup"><span data-stu-id="0c2e8-183">Select **From Device**.</span></span>
    
   - <span data-ttu-id="0c2e8-p116">Clique no botão Procurar, que abrirá a caixa de diálogo **Especificar Backup**. Em **Mídia de backup**, selecione **Arquivo**. Clique em **Adicionar**, selecione o arquivo de backup criado na etapa 3 e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="0c2e8-p116">Click the browse button, which opens the **Specify Backup** dialog box. In **Backup media**, select **File**. Click **Add**, select the backup file that you created in step 3, and then click **OK**.</span></span>
    
   - <span data-ttu-id="0c2e8-187">Em **Selecione os conjuntos de backup a serem restaurados**, selecione o backup.</span><span class="sxs-lookup"><span data-stu-id="0c2e8-187">In **Select the backup sets to restore**, select the backup.</span></span>
    
   - <span data-ttu-id="0c2e8-188">Clique em **Opções** no painel **Selecionar uma página**.</span><span class="sxs-lookup"><span data-stu-id="0c2e8-188">Click **Options** in the **Select a page** pane.</span></span>
    
   - <span data-ttu-id="0c2e8-189">Em **Opções de restauração**, selecione **Substituir o banco de dados existente**.</span><span class="sxs-lookup"><span data-stu-id="0c2e8-189">In **Restore options**, select **Overwrite the existing database**.</span></span>
    
   - <span data-ttu-id="0c2e8-190">Em **Estado de recuperação**, selecione **Deixar o banco de dados pronto para uso**.</span><span class="sxs-lookup"><span data-stu-id="0c2e8-190">In **Recovery State**, select **Leave the database ready to use**.</span></span>
    
   - <span data-ttu-id="0c2e8-191">Clique em **OK** para iniciar o processo de restauração.</span><span class="sxs-lookup"><span data-stu-id="0c2e8-191">Click **OK** to begin the restoration process.</span></span>
    
5. <span data-ttu-id="0c2e8-192">Configure o envio de Log do SQL Server para o banco de dados primário.</span><span class="sxs-lookup"><span data-stu-id="0c2e8-192">Configure SQL Server Log Shipping for the primary database.</span></span> <span data-ttu-id="0c2e8-193">Siga os procedimentos em [Configure alta disponibilidade e recuperação de desastres para o servidor de Chat persistente no Skype para Business Server 2015](../../deploy/deploy-persistent-chat-server/configure-hadr-for-persistent-chat.md) para estabelecer o envio de logs do banco de dados mgc primária.</span><span class="sxs-lookup"><span data-stu-id="0c2e8-193">Follow the procedures in [Configure high availability and disaster recovery for Persistent Chat Server in Skype for Business Server 2015](../../deploy/deploy-persistent-chat-server/configure-hadr-for-persistent-chat.md) to establish log shipping for the primary mgc database.</span></span>
    
6. <span data-ttu-id="0c2e8-194">Defina os servidores ativos do servidor de Chat persistente.</span><span class="sxs-lookup"><span data-stu-id="0c2e8-194">Set the Persistent Chat Server active servers.</span></span> <span data-ttu-id="0c2e8-195">Do Skype do Shell de gerenciamento do servidor de negócios, use o cmdlet **Set-CsPersistentChatActiveServer** para definir a lista de servidores ativos.</span><span class="sxs-lookup"><span data-stu-id="0c2e8-195">From the Skype for Business Server Management Shell, use the **Set-CsPersistentChatActiveServer** cmdlet to set the list of active servers.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="0c2e8-196">Todos os servidores ativos devem estar localizados no mesmo data center que o novo banco de dados primário ou em um data center que tenha uma conexão de baixa latência/alta largura de banda com o banco de dados.</span><span class="sxs-lookup"><span data-stu-id="0c2e8-196">All the active servers must be located within the same data center as the new primary database, or in a data center that has a low latency/high bandwidth connection to the database.</span></span> 
  
<span data-ttu-id="0c2e8-197">Para restaurar o pool ao seu estado normal, execute o seguinte comando do Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="0c2e8-197">To restore the pool to its normal state run the following Windows PowerShell command:</span></span>
  
```
Set-CsPersistentChatState -Identity "service: lyncpc.dci.discovery.com" -PoolState Normal
```

<span data-ttu-id="0c2e8-198">Para obter mais informações, consulte o tópico da ajuda referente ao cmdlet do [Set-CsPersistentChatState](https://docs.microsoft.com/powershell/module/skype/set-cspersistentchatstate?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="0c2e8-198">For more information, see the help topic for the [Set-CsPersistentChatState](https://docs.microsoft.com/powershell/module/skype/set-cspersistentchatstate?view=skype-ps) cmdlet.</span></span>
  

