---
title: Failover e Failback em um pool
ms.reviewer: ''
author: cichur
ms.author: v-cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: .
ms.openlocfilehash: 1ebd4e8110b8783c869530d95eda0646a895b88e
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49826561"
---
# <a name="failing-over-and-failing-back-a-pool-in-skype-for-business-server"></a><span data-ttu-id="4927f-103">Fazer o failing over e fazer o failing back de um pool no Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="4927f-103">Failing over and failing back a pool in Skype for Business Server</span></span> 

<span data-ttu-id="4927f-104">Use os procedimentos a seguir se um único pool de Front-End falhar e precisar de um failed over ou se o pool que teve o desastre estiver novamente online e você precisar restaurar sua implantação para o status de trabalho regular.</span><span class="sxs-lookup"><span data-stu-id="4927f-104">Use the following procedures if a single Front End pool has failed and needs to be failed over, or the pool that experienced the disaster is back online and you need to restore your deployment to regular working status.</span></span> <span data-ttu-id="4927f-105">Saiba também como fazer fail over e fail back do pool de Borda usado para federação do Skype for Business ou federação XMPP ou alterar o pool de Borda associado a um pool de Front-End.</span><span class="sxs-lookup"><span data-stu-id="4927f-105">Also  learn how to fail over and fail back the Edge pool used for Skype for Business federation or XMPP federation, or change the Edge pool associated with a Front End pool.</span></span>

- [<span data-ttu-id="4927f-106">Fail over a Front End pool</span><span class="sxs-lookup"><span data-stu-id="4927f-106">Fail over a Front End pool</span></span>](#fail-over-a-front-end-pool)
- [<span data-ttu-id="4927f-107">Fail back de um pool</span><span class="sxs-lookup"><span data-stu-id="4927f-107">Fail back a pool</span></span>](#fail-back-a-pool)
- [<span data-ttu-id="4927f-108">Fail over the Edge pool used for Skype for Business Server federation</span><span class="sxs-lookup"><span data-stu-id="4927f-108">Fail over the Edge pool used for Skype for Business Server federation</span></span>](#fail-over-the-edge-pool-used-for-skype-for-business-server-federation)
- [<span data-ttu-id="4927f-109">Fail over the Edge pool used for XMPP federation in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="4927f-109">Fail over the Edge pool used for XMPP federation in Skype for Business Server</span></span>](#fail-over-the-edge-pool-used-for-xmpp-federation-in-skype-for-business-server)
- [<span data-ttu-id="4927f-110">Fail back do pool de Borda usado para federação do Skype for Business Server ou federação XMPP</span><span class="sxs-lookup"><span data-stu-id="4927f-110">Fail back the Edge pool used for Skype for Business Server federation or XMPP federation</span></span>](#fail-back-the-edge-pool-used-for-skype-for-business-server-federation-or-xmpp-federation)
- [<span data-ttu-id="4927f-111">Alterar o pool de Borda associado a um pool de Front-End</span><span class="sxs-lookup"><span data-stu-id="4927f-111">Change the Edge pool associated with a Front End pool</span></span>](#change-the-edge-pool-associated-with-a-front-end-pool)

## <a name="fail-over-a-front-end-pool"></a><span data-ttu-id="4927f-112">Fail over a Front End pool</span><span class="sxs-lookup"><span data-stu-id="4927f-112">Fail over a Front End pool</span></span>

<span data-ttu-id="4927f-113">Neste procedimento, o Datacenter1 contém o Pool1, que falhou.</span><span class="sxs-lookup"><span data-stu-id="4927f-113">In this procedure, Datacenter1 contains Pool1, and Pool1 has failed.</span></span> <span data-ttu-id="4927f-114">Você fará failover no Pool2 localizado no Datacenter2.</span><span class="sxs-lookup"><span data-stu-id="4927f-114">You are failing over to Pool2 located in Datacenter2.</span></span>

<span data-ttu-id="4927f-115">A maior parte do trabalho para o failover do pool envolve o failover do armazenamento de Gerenciamento Central, se necessário.</span><span class="sxs-lookup"><span data-stu-id="4927f-115">Most of the work for the pool failover involves failing over the Central Management store, if it is required.</span></span> <span data-ttu-id="4927f-116">Isso é importante porque o armazenamento de Gerenciamento Central deve estar funcional quando os usuários do pool são reava passo a passo.</span><span class="sxs-lookup"><span data-stu-id="4927f-116">This is important because the Central Management store must be functional when the pool’s users are failed over.</span></span>

<span data-ttu-id="4927f-p104">Além disso, se um pool de Front End falhar mas o pool de Borda no local ainda estiver em execução, você deve saber se o pool de Borda usa o pool com falha como pool do próximo salto. Se usar, você deve alterar o pool de Borda para usar um pool de Front End diferente antes de fazer o failover do pool de Front End com falha. Como a configuração do próximo salto será alterada dependerá de a Borda usar um pool no mesmo local do pool de Borda ou em um local diferente.</span><span class="sxs-lookup"><span data-stu-id="4927f-p104">Additionally, if a Front End pool fails but the Edge pool at that site is still running, you must know whether the Edge pool uses the failed pool as a next hop pool. If it does, you must change the Edge pool to use a different Front End pool before failing over the failed Front End pool. How you change the next hop setting depends on whether the Edge will use a pool at the same site as the Edge pool, or a different site.</span></span>

<span data-ttu-id="4927f-120">**Para definir um pool de Borda para usar um pool de próximo salto no mesmo site**</span><span class="sxs-lookup"><span data-stu-id="4927f-120">**To set an Edge pool to use a next hop pool at the same site**</span></span>

1.  <span data-ttu-id="4927f-121">Abra o Construtor de Topologias, clique com o botão direito do mouse no pool de Borda que precisa ser alterado e clique em **Editar Propriedades.**</span><span class="sxs-lookup"><span data-stu-id="4927f-121">Open Topology Builder, right-click the Edge pool that needs to be changed, and click **Edit Properties**.</span></span>

2.  <span data-ttu-id="4927f-p105">Clique em **Próximo Salto**. Na lista **Pool do próximo salto:**, selecione o pool que servirá como pool do próximo salto.</span><span class="sxs-lookup"><span data-stu-id="4927f-p105">Click **Next Hop**. From the **Next hop pool:** list, select the pool which will now serve as the next hop pool.</span></span>

3.  <span data-ttu-id="4927f-124">Clique em **OK** e publique as alterações.</span><span class="sxs-lookup"><span data-stu-id="4927f-124">Click **OK**, and then publish the changes.</span></span>

<span data-ttu-id="4927f-125">**Para definir um pool de Borda para usar um pool de próximo salto em um site diferente**</span><span class="sxs-lookup"><span data-stu-id="4927f-125">**To set an Edge pool to use a next hop pool at a different site**</span></span>

1.  <span data-ttu-id="4927f-126">Abra uma janela do Shell de Gerenciamento do Skype for Business Server e digite o seguinte cmdlet:</span><span class="sxs-lookup"><span data-stu-id="4927f-126">Open a Skype for Business Server Management Shell window and type the following cmdlet:</span></span>
    
        Set-CsEdgeServer -Identity EdgeServer:<Edge Server pool FQDN> -Registrar Registrar:<NextHopPoolFQDN>

<span data-ttu-id="4927f-127">**Para fazer fail over de um pool em um desastre**</span><span class="sxs-lookup"><span data-stu-id="4927f-127">**To fail over a pool in a disaster**</span></span>

1.  <span data-ttu-id="4927f-128">Encontre qual pool é o host do Servidor de Gerenciamento Central digitando o seguinte cmdlet em um servidor front-end no Pool2:</span><span class="sxs-lookup"><span data-stu-id="4927f-128">Find which pool is the host for the Central Management Server by typing the following cmdlet on a Front End server in Pool2:</span></span>
    
        Invoke-CsManagementServerFailover -Whatif
    
    <span data-ttu-id="4927f-129">Os resultados desse cmdlet mostram qual pool hospeda atualmente o Servidor de Gerenciamento Central.</span><span class="sxs-lookup"><span data-stu-id="4927f-129">The results of this cmdlet show which pool currently hosts the Central Management Server.</span></span> <span data-ttu-id="4927f-130">No restante deste procedimento, esse pool é conhecido como \_ Pool CMS.</span><span class="sxs-lookup"><span data-stu-id="4927f-130">In the rest of this procedure, this pool is known as CMS\_Pool.</span></span>

2.  <span data-ttu-id="4927f-131">Use o Construtor de Topologias para encontrar a versão do Skype for Business Server em execução no \_ Pool CMS.</span><span class="sxs-lookup"><span data-stu-id="4927f-131">Use Topology Builder to find the version of Skype for Business Server running on the CMS\_Pool.</span></span> <span data-ttu-id="4927f-132">Se estiver executando o Skype for Business Server, use o cmdlet a seguir para encontrar o pool de backup do Pool 1.</span><span class="sxs-lookup"><span data-stu-id="4927f-132">If it is running Skype for Business Server, use the following cmdlet to find the backup pool of Pool 1.</span></span>
    
        Get-CsPoolBackupRelationship -PoolFQDN <CMS_Pool FQDN>
    
    <span data-ttu-id="4927f-133">Deixe o \_ Pool de Backup ser o pool de backup.</span><span class="sxs-lookup"><span data-stu-id="4927f-133">Let Backup\_Pool be the backup pool.</span></span>

3.  <span data-ttu-id="4927f-134">Verifique o status do armazenamento de Gerenciamento Central com o seguinte cmdlet:</span><span class="sxs-lookup"><span data-stu-id="4927f-134">Check the status of the Central Management store with the following cmdlet:</span></span>
    
        Get-CsManagementStoreReplicationStatus -CentralManagementStoreStatus 
    
    <span data-ttu-id="4927f-135">Este cmdlet deve mostrar que ActiveMasterFQDN e ActiveFileTransferAgents estão apontando para o FQDN do Pool DE \_ CMS.</span><span class="sxs-lookup"><span data-stu-id="4927f-135">This cmdlet should show that both ActiveMasterFQDN and ActiveFileTransferAgents are pointing to the FQDN of CMS\_Pool.</span></span> <span data-ttu-id="4927f-136">Se eles estão vazios, o Servidor de Gerenciamento Central não está disponível e você deve fazer fail over.</span><span class="sxs-lookup"><span data-stu-id="4927f-136">If they are empty, the Central Management Server is not available and you must fail it over.</span></span>

4.  <span data-ttu-id="4927f-137">Se o armazenamento de Gerenciamento Central não estiver disponível ou se o armazenamento de Gerenciamento Central estava em execução no Pool1 (ou seja, o pool que falhou), você deve fazer fail over do Servidor de Gerenciamento Central antes de fazer fail over do pool.</span><span class="sxs-lookup"><span data-stu-id="4927f-137">If the Central Management store is not available or if the Central Management store was running on Pool1 (that is, the pool that has failed), you must fail over the Central Management Server before failing over the pool.</span></span> <span data-ttu-id="4927f-138">Se você precisar fazer o fail over do Servidor de Gerenciamento Central que estava hospedado em um pool executando o Skype for Business Server, use o cmdlet na etapa 5 deste procedimento.</span><span class="sxs-lookup"><span data-stu-id="4927f-138">If you need to fail over the Central Management Server that was hosted on a pool running Skype for Business Server, use the cmdlet in step 5 of this procedure.</span></span> <span data-ttu-id="4927f-139">Se não for necessário fazer fail over do Servidor de Gerenciamento Central, pule para a etapa 7 deste procedimento.</span><span class="sxs-lookup"><span data-stu-id="4927f-139">If you do not need to fail over the Central Management Server, skip to step 7 of this procedure.</span></span>

5.  <span data-ttu-id="4927f-140">Para fazer fail over the Central Management store on a pool running Skype for Business Server, do the following:</span><span class="sxs-lookup"><span data-stu-id="4927f-140">To fail over the Central Management store on a pool running Skype for Business Server, do the following:</span></span>
    
      - <span data-ttu-id="4927f-141">Primeiro, verifique qual Servidor back-end no Pool de Backup executa a instância principal do armazenamento de Gerenciamento \_ Central digitando o seguinte:</span><span class="sxs-lookup"><span data-stu-id="4927f-141">First, check which Back End Server in Backup\_Pool runs the principal instance of the Central Management store by typing the following:</span></span>
        
            Get-CsDatabaseMirrorState -DatabaseType Centralmgmt -PoolFqdn <Backup_Pool Fqdn>
    
      - <span data-ttu-id="4927f-142">Se o servidor back-end primário no \_ Pool de Backup for o principal, digite:</span><span class="sxs-lookup"><span data-stu-id="4927f-142">If the primary Back End Server in Backup\_Pool is the principal, type:</span></span>
        
            Invoke-CSManagementServerFailover -BackupSQLServerFqdn <Backup_Pool Primary BackEnd Server FQDN> -BackupSQLInstanceName <Backup_Pool Primary SQL Instance Name>
        
        <span data-ttu-id="4927f-143">Se o servidor back-end espelho no \_ Pool de Backup for o principal, digite:</span><span class="sxs-lookup"><span data-stu-id="4927f-143">If the mirror Back End Server in Backup\_Pool is the principal, type:</span></span>
        
            Invoke-CSManagementServerFailover -MirrorSQLServerFqdn <Backup_Pool Mirror BackEnd Server FQDN> -MirrorSQLInstanceName <Backup_Pool Mirror SQL Instance Name>
    
      - <span data-ttu-id="4927f-144">Valide se o failover do Servidor de Gerenciamento Central está concluído.</span><span class="sxs-lookup"><span data-stu-id="4927f-144">Validate that the Central Management Server failover is complete.</span></span> <span data-ttu-id="4927f-145">Digite:</span><span class="sxs-lookup"><span data-stu-id="4927f-145">Type the following:</span></span>
        
            Get-CsManagementStoreReplicationStatus -CentralManagementStoreStatus 
        
        <span data-ttu-id="4927f-146">Verifique se ActiveMasterFQDN e ActiveFileTransferAgents estão apontando para o FQDN do Pool de \_ Backup.</span><span class="sxs-lookup"><span data-stu-id="4927f-146">Check that both ActiveMasterFQDN and ActiveFileTransferAgents are pointing to the FQDN of Backup\_Pool.</span></span>
    
      - <span data-ttu-id="4927f-147">Por fim, verifique o status da réplica para todos os Servidores Front-End digitando o seguinte:</span><span class="sxs-lookup"><span data-stu-id="4927f-147">Finally, check the replica status for all Front End Servers by typing the following:</span></span>
        
            Get-CsManagementStoreReplicationStatus 
        
        <span data-ttu-id="4927f-148">Verifique se todas as réplicas possuem o valor Verdadeiro (True).</span><span class="sxs-lookup"><span data-stu-id="4927f-148">Check that all replicas have a value of True.</span></span>
        
        <span data-ttu-id="4927f-149">Pule para a etapa 7 neste procedimento.</span><span class="sxs-lookup"><span data-stu-id="4927f-149">Skip to step 7 in this procedure.</span></span>

6.  <span data-ttu-id="4927f-150">Instale o armazenamento de Gerenciamento Central no Servidor back-end do pool de \_ backup.</span><span class="sxs-lookup"><span data-stu-id="4927f-150">Install the Central Management store on the Back End Server of Backup\_Pool.</span></span>
    
      - <span data-ttu-id="4927f-151">Primeiro, execute o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="4927f-151">First, run the following command:</span></span>
        ```PowerShell
         
        Install-CsDatabase -CentralManagementDatabase -Clean -SqlServerFqdn <Backup_Pool Back End Server FQDN> -SqlInstanceName rtc  
        ```
    
      - <span data-ttu-id="4927f-152">Execute o próximo comando em um dos Servidores Front End do Pool de Backup para forçar a movimentação do \_ armazenamento de Gerenciamento Central:</span><span class="sxs-lookup"><span data-stu-id="4927f-152">Run the next command on one of the Front End Servers of Backup\_Pool to force the move of the Central Management store:</span></span>
        
            Move-CsManagementServer -ConfigurationFileName c:\CsConfigurationFile.zip -LisConfigurationFileName c:\CsLisConfigurationFile.zip -Force 
    
      - <span data-ttu-id="4927f-153">Valide se a movimentação está concluída:</span><span class="sxs-lookup"><span data-stu-id="4927f-153">Validate the move is complete:</span></span>
        
            Get-CsManagementStoreReplicationStatus -CentralManagementStoreStatus 
        
        <span data-ttu-id="4927f-154">Verifique se ActiveMasterFQDN e ActiveFileTransferAgents estão apontando para o FQDN do Pool de \_ Backup.</span><span class="sxs-lookup"><span data-stu-id="4927f-154">Check that both ActiveMasterFQDN and ActiveFileTransferAgents are pointing to the FQDN of Backup\_Pool.</span></span>
    
      - <span data-ttu-id="4927f-155">Verifique o status da réplica para todos os servidores de Front End digitando:</span><span class="sxs-lookup"><span data-stu-id="4927f-155">Check the replica status for all Front End Servers by typing the following:</span></span>
        
            Get-CsManagementStoreReplicationStatus 
        
        <span data-ttu-id="4927f-156">Verifique se todas as réplicas possuem o valor Verdadeiro (True).</span><span class="sxs-lookup"><span data-stu-id="4927f-156">Check that all replicas have a value of True.</span></span>
    
      - <span data-ttu-id="4927f-157">Instale o serviço do Servidor de Gerenciamento Central no restante dos Servidores Front-End no Pool de \_ Backup.</span><span class="sxs-lookup"><span data-stu-id="4927f-157">Install the Central Management Server service on the rest of the Front End Servers in Backup\_Pool.</span></span> <span data-ttu-id="4927f-158">Para fazer isso, execute o seguinte comando em todos os Servidores front-end, exceto aquele usado ao forçar a movimentação do armazenamento de Gerenciamento Central anteriormente neste procedimento:</span><span class="sxs-lookup"><span data-stu-id="4927f-158">To do so, run the following command on all the Front End Servers, except the one you used when forcing the Central Management store move earlier in this procedure:</span></span>
        
            Bootstrapper /Setup 

7.  <span data-ttu-id="4927f-159">Fail over the users from Pool1 to Pool2 by running the following cmdlet in a Skype for Business Server Management Shell window:</span><span class="sxs-lookup"><span data-stu-id="4927f-159">Fail over the users from Pool1 to Pool2 by running the following cmdlet in a Skype for Business Server Management Shell window:</span></span>
    
        Invoke-CsPoolFailover -PoolFQDN <Pool1 FQDN> -DisasterMode -Verbose
    
    <span data-ttu-id="4927f-160">Como as etapas realizadas nas partes anteriores deste procedimento para verificar o status do armazenamento de Gerenciamento Central não são universais, ainda existe a chance de que esse cmdlet falhe porque o armazenamento de Gerenciamento Central ainda não tem fail over completo.</span><span class="sxs-lookup"><span data-stu-id="4927f-160">Because the steps taken in the previous parts of this procedure to check the Central Management store status are not universal, there is still a chance this cmdlet will fail because the Central Management store is not yet fully failed over.</span></span> <span data-ttu-id="4927f-161">Nesse caso, você deve corrigir o Armazenamento de Gerenciamento Central com base nas mensagens de erro que vê e executar esse cmdlet novamente.</span><span class="sxs-lookup"><span data-stu-id="4927f-161">In this case, you must fix the Central Management store based on the error messages that you see, and then run this cmdlet again.</span></span>
    
    <span data-ttu-id="4927f-p113">Se a mensagem de erro a seguir for apresentada, será necessário alterar o pool de Borda neste local para usar um pool diferente como próximo salto antes da fazer o failover do pool. Para detalhes, consulte os procedimentos no início deste tópico.</span><span class="sxs-lookup"><span data-stu-id="4927f-p113">If you see the following error message, then you need to change the Edge pool at this site to use a different pool as its next hop before failing over the pool. For details, see the procedures at the beginning of this topic.</span></span>
    
        Invoke-CsPoolFailOver : This Front-end pool "pool1.contoso.com" is specified in
        topology as the next hop for the Edge server. Failing over this pool may cause External
        access/Federation/Split-domain/XMPP features to stop working. Please use Topology Builder to
        change the Edge internal next hop setting to point to a different Front-end pool,  before you
        proceed.


## <a name="fail-back-a-pool"></a><span data-ttu-id="4927f-164">Fail back de um pool</span><span class="sxs-lookup"><span data-stu-id="4927f-164">Fail back a pool</span></span>

<span data-ttu-id="4927f-165">Depois que o pool que passou por desastre voltar a ficar online (ou seja, o Pool1 neste exemplo), execute as etapas a seguir para restaurar sua implantação para o status funcional normal.</span><span class="sxs-lookup"><span data-stu-id="4927f-165">After the pool that experienced the disaster is back online (that is, Pool1 in this example), take the following steps to restore your deployment to regular working status.</span></span>

<span data-ttu-id="4927f-166">O processo de failback leva vários minutos para ser concluído.</span><span class="sxs-lookup"><span data-stu-id="4927f-166">Note that the failback process takes several minute to complete.</span></span>  <span data-ttu-id="4927f-167">Como referência, espera-se que leve até 60 minutos para um pool de 20 mil usuários.</span><span class="sxs-lookup"><span data-stu-id="4927f-167">For reference, it is expected to take up to 60 minutes for a pool of 20,000 users.</span></span>

<span data-ttu-id="4927f-168">Para fazer failback dos usuários que estavam originalmente hospedados no Pool1 e dos quais foi feito failover para o Pool2, digite o seguinte cmdlet:</span><span class="sxs-lookup"><span data-stu-id="4927f-168">Fail back the users who were originally homed in Pool1 and have been failed over to Pool2 by typing the following cmdlet:</span></span>
    
    Invoke-CsPoolFailback -PoolFQDN <Pool1 FQDN> -Verbose

<span data-ttu-id="4927f-169">Nenhuma outra etapa é necessária.</span><span class="sxs-lookup"><span data-stu-id="4927f-169">No other steps are necessary.</span></span> <span data-ttu-id="4927f-170">Se você tiver falhado no Servidor de Gerenciamento Central, poderá deixá-lo no Pool2.</span><span class="sxs-lookup"><span data-stu-id="4927f-170">If you failed over the Central Management Server, you can leave it in Pool2.</span></span>

## <a name="fail-over-the-edge-pool-used-for-skype-for-business-server-federation"></a><span data-ttu-id="4927f-171">Fail over the Edge pool used for Skype for Business Server federation</span><span class="sxs-lookup"><span data-stu-id="4927f-171">Fail over the Edge pool used for Skype for Business Server federation</span></span> 

<span data-ttu-id="4927f-172">Se o pool de Borda onde você tem a federação do Skype for Business Server configurada ficar ino mesmo, você deve alterar a federação para usar um pool de Borda diferente para que a federação funcione.</span><span class="sxs-lookup"><span data-stu-id="4927f-172">If the Edge pool where you have Skype for Business Server federation configured goes down, you must change federation to use a different Edge pool for federation to work.</span></span>

1.  <span data-ttu-id="4927f-173">No servidor de front-end, abra o Construtor de Topologia.</span><span class="sxs-lookup"><span data-stu-id="4927f-173">On a Front End server, open Topology Builder.</span></span> <span data-ttu-id="4927f-174">Expanda **pools de** Borda e clique com o botão direito do mouse no servidor de Borda ou pool de servidores de Borda atualmente configurado para Federação.</span><span class="sxs-lookup"><span data-stu-id="4927f-174">Expand **Edge pools**, and then right-click the Edge server or Edge server pool that is currently configured for Federation.</span></span> <span data-ttu-id="4927f-175">Selecione **Editar propriedades**.</span><span class="sxs-lookup"><span data-stu-id="4927f-175">Select **Edit properties**.</span></span>

2.  <span data-ttu-id="4927f-176">Em **Editar propriedades**, em **Geral**, desmarque **Habilitar federação para este pool de Borda (Porta 5061)**.</span><span class="sxs-lookup"><span data-stu-id="4927f-176">In **Edit Properties** under **General**, clear **Enable federation for this Edge pool (Port 5061)**.</span></span> <span data-ttu-id="4927f-177">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="4927f-177">Click **OK**.</span></span>

3.  <span data-ttu-id="4927f-178">Expanda **pools de** Borda e clique com o botão direito do mouse no servidor de Borda ou pool de servidores de Borda que você agora deseja usar para Federação.</span><span class="sxs-lookup"><span data-stu-id="4927f-178">Expand **Edge pools**, and then right-click the Edge server or Edge server pool that you now want to use for Federation.</span></span> <span data-ttu-id="4927f-179">Selecione **Editar propriedades**.</span><span class="sxs-lookup"><span data-stu-id="4927f-179">Select **Edit properties**.</span></span>

4.  <span data-ttu-id="4927f-p119">Em **Editar propriedades**, em **Geral**, selecione **Habilitar federação para este pool de Borda (Porta 5061)**. Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="4927f-p119">In **Edit Properties** under **General**, select **Enable federation for this Edge pool (Port 5061)**. Click **OK**.</span></span>

5.  <span data-ttu-id="4927f-p120">Clique em **Ação**, selecione **Topologia**, **Publicar**. Quando solicitado em **Publicar a topologia**, clique em **Avançar**. Quando Publicar é finalizado, clique em **Concluir**.</span><span class="sxs-lookup"><span data-stu-id="4927f-p120">Click **Action**, select **Topology**, select **Publish**. When prompted on **Publish the topology**, click **Next**. When the Publish is finished, click **Finish**.</span></span>

6.  <span data-ttu-id="4927f-185">No servidor de Borda, abra o Assistente de Implantação do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="4927f-185">On the Edge server, open the Skype for Business Server Deployment wizard.</span></span> <span data-ttu-id="4927f-186">Clique **em Instalar ou Atualizar o Sistema do Skype for Business Server** e clique em Instalar ou Remover **Componentes do Skype for Business Server.**</span><span class="sxs-lookup"><span data-stu-id="4927f-186">Click **Install or Update Skype for Business Server System**, and then click **Setup or Remove Skype for Business Server Components**.</span></span> <span data-ttu-id="4927f-187">Clique em **Executar novamente**.</span><span class="sxs-lookup"><span data-stu-id="4927f-187">Click **Run Again**.</span></span>

7.  <span data-ttu-id="4927f-188">Clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="4927f-188">Click **Next**.</span></span> <span data-ttu-id="4927f-189">A tela de resumo mostrará ações conforme são executadas.</span><span class="sxs-lookup"><span data-stu-id="4927f-189">The summary screen will show actions as they are executed.</span></span> <span data-ttu-id="4927f-190">Quando a implantação estiver concluída, clique em **Exibir log** para exibir os arquivos de log disponíveis.</span><span class="sxs-lookup"><span data-stu-id="4927f-190">Once the deployment is done, click **View Log** to view available log files.</span></span> <span data-ttu-id="4927f-191">Clique em **Concluir** para finalizar a implantação.</span><span class="sxs-lookup"><span data-stu-id="4927f-191">Click **Finish** to complete the deployment.</span></span>
    
    <span data-ttu-id="4927f-192">Se o site que contém o pool de borda com falha contiver servidores front-end que ainda estão em execução, você precisará atualizar o Serviço de Webconferência e o Serviço de Conferência A/V nesses pools de frond-ends para usar um pool de borda em um site remoto que ainda esteja ativo.</span><span class="sxs-lookup"><span data-stu-id="4927f-192">If the site containing the failed Edge pool contains Front End Servers that are still running, you must update the Web Conferencing Service and A/V Conferencing Service on these Front End pools to use an Edge pool in a remote site that is still running.</span></span> 

 ## <a name="fail-over-the-edge-pool-used-for-xmpp-federation-in-skype-for-business-server"></a><span data-ttu-id="4927f-193">Fail over the Edge pool used for XMPP federation in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="4927f-193">Fail over the Edge pool used for XMPP federation in Skype for Business Server</span></span> 

<span data-ttu-id="4927f-p123">Na sua organização, há um pool de borda designado como o pool para uso da federação XMPP. Se esse pool parar de funcionar, você deve transferir a federação XMPP para usar um pool de borda diferente antes da federação XMPP poder funcionar novamente.</span><span class="sxs-lookup"><span data-stu-id="4927f-p123">In your organization, there is one Edge pool designated as the pool to use for XMPP federation. If this pool goes down, you must fail over XMPP federation to use a different Edge pool before XMPP federation can work again.</span></span>

<span data-ttu-id="4927f-196">Quando você instala pools de borda e habilita a Federação XMPP, é possível simplificar o processo de recuperação de desastres configurando a criação de registros do servidor DNS externos para todos os seus pools de Borda para a federação XMPP, em vez de apenas um.</span><span class="sxs-lookup"><span data-stu-id="4927f-196">When you first install Edge pools and enable XMPP Federation, you can simplify the disaster recovery process by setting up external DNS SRV records for all of your Edge pools for XMPP federation, instead of just one.</span></span> <span data-ttu-id="4927f-197">Cada um destes registros SRV devem ter um conjunto de prioridade diferente.</span><span class="sxs-lookup"><span data-stu-id="4927f-197">Each of these SRV records must have a different priority set.</span></span> <span data-ttu-id="4927f-198">Todo o tráfego da federação XMPP atravessa o pool com o registro SRV com a mais alta prioridade.</span><span class="sxs-lookup"><span data-stu-id="4927f-198">All XMPP federation traffic goes through the pool with the SRV record with the highest priority.</span></span> 

<span data-ttu-id="4927f-199">No procedimento a seguir, o EdgePool1 é o pool no qual a federação XMPP foi originalmente hospedada e o EdgePool2 é o pool no qual a federação XMPP está hospedada agora.</span><span class="sxs-lookup"><span data-stu-id="4927f-199">In the following procedure, EdgePool1 is the pool which originally hosted XMPP federation, and EdgePool2 is the pool which will now host XMPP federation.</span></span>


### <a name="to-fail-over-the-edge-pool-used-for-xmpp-federation"></a><span data-ttu-id="4927f-200">Para fazer fail over do pool de Borda usado para federação XMPP</span><span class="sxs-lookup"><span data-stu-id="4927f-200">To fail over the Edge pool used for XMPP federation</span></span>

1.  <span data-ttu-id="4927f-201">Se você ainda não possuir outro pool de borda implantado (além de um não estiver funcionando no momento), implante esse pool.</span><span class="sxs-lookup"><span data-stu-id="4927f-201">If you don’t already have another Edge pool deployed (besides the one which is currently down), deploy that pool.</span></span> 

2.  <span data-ttu-id="4927f-202">Em cada Servidor de Borda no novo pool de borda no qual a federação XMPP estará hospedada no momento (EdgePool2), execute o seguinte cmdlet:</span><span class="sxs-lookup"><span data-stu-id="4927f-202">On each Edge Server in the new Edge pool which will now host XMPP federation (EdgePool2), run the following cmdlet:</span></span>
    
        Stop-CsWindowsService

3.  <span data-ttu-id="4927f-203">Execute o seguinte cmdlet para redirecionar a rota da federação XMPP para o EdgePool2:</span><span class="sxs-lookup"><span data-stu-id="4927f-203">Run the following cmdlet to repoint the XMPP federation route to EdgePool2:</span></span>
    
        Set-CsSite Site2 -XmppExternalFederationRoute EdgeServer2.contoso.com
    
    <span data-ttu-id="4927f-204">Neste exemplo, o Site2 é o site contendo o pool de borda no qual a rota da federação XMPP estará hospedada no momento e o EdgeServer2.contoso.com é o FQDN de um Servidor de Borda nesse pool.</span><span class="sxs-lookup"><span data-stu-id="4927f-204">In this example, Site2 is the site containing the Edge pool which will now host the XMPP federation route, and EdgeServer2.contoso.com is the FQDN of an Edge Server in that pool.</span></span>

4.  <span data-ttu-id="4927f-205">No servidor DNS externo, altere o registro A de DNS da federação XMPP para apontar para o EdgeServer2.contoso.com.</span><span class="sxs-lookup"><span data-stu-id="4927f-205">On the external DNS server, change the DNS A record for XMPP federation to point to EdgeServer2.contoso.com.</span></span>

5.  <span data-ttu-id="4927f-p125">Se você ainda não tiver um registro DNS SRV para a federação XMPP que resolva o pool de borda no qual a federação XMPP estará hospedada no momento, é necessário adicioná-lo, conforme no exemplo a seguir. O registro SRV deve ter um valor de porta de 5269.</span><span class="sxs-lookup"><span data-stu-id="4927f-p125">If you do not already have a DNS SRV record for XMPP federation which resolves to the Edge pool which will now host XMPP federation, you must add it, as in the following example. This SRV record must have a port value of 5269.</span></span>
    
        _xmpp-server._tcp.contoso.com

6.  <span data-ttu-id="4927f-208">Verifique se o pool de borda no qual a federação XMPP estará hospedada no momento possui uma porta 5269 aberta externamente.</span><span class="sxs-lookup"><span data-stu-id="4927f-208">Verify that the Edge pool which will now host XMPP federation has port 5269 open externally.</span></span>

7.  <span data-ttu-id="4927f-209">Inicie os serviços em todos os Servidores de Borda no pool de borda no qual a federação XMPP estará hospedada no momento:</span><span class="sxs-lookup"><span data-stu-id="4927f-209">Start the services on all Edge Servers in the Edge pool which will now host XMPP federation:</span></span>
    
        Start-CsWindowsService


## <a name="fail-back-the-edge-pool-used-for-skype-for-business-server-federation-or-xmpp-federation"></a><span data-ttu-id="4927f-210">Fail back do pool de Borda usado para federação do Skype for Business Server ou federação XMPP</span><span class="sxs-lookup"><span data-stu-id="4927f-210">Fail back the Edge pool used for Skype for Business Server federation or XMPP federation</span></span> 

<span data-ttu-id="4927f-211">Depois que um pool de Borda com falha usado para hospedar a federação foi trazido novamente online, use este procedimento para fazer fail back da rota de federação do Skype for Business Server e/ou a rota de federação XMPP para usar novamente esse pool de Borda restaurado.</span><span class="sxs-lookup"><span data-stu-id="4927f-211">After a failed Edge pool that used to host federation has been brought back online, use this procedure to fail back the Skype for Business Server federation route and/or the XMPP federation route to again use this restored Edge pool.</span></span>

1.  <span data-ttu-id="4927f-212">No pool de Borda disponível novamente, inicie os Serviços de Borda.</span><span class="sxs-lookup"><span data-stu-id="4927f-212">On the Edge pool that is now available again, start the Edge Services.</span></span>

2.  <span data-ttu-id="4927f-213">Se você quiser fazer fail back da rota de federação do Skype for Business Server para usar o Servidor de Borda restaurado, faça o seguinte:</span><span class="sxs-lookup"><span data-stu-id="4927f-213">If you want to fail back the Skype for Business Server federation route to use the restored Edge Server, do the following:</span></span>
    
      - <span data-ttu-id="4927f-p126">No servidor de front-end, abra o Construtor de Topologia. Expanda **Pools de borda**, clique com o botão direito no servidor de Borda ou pool do servidor de Borda atualmente configurado para Federação. Selecione **Editar propriedades**.</span><span class="sxs-lookup"><span data-stu-id="4927f-p126">On a Front End server, open Topology Builder. Expand **Edge pools**, then right click the Edge server or Edge server pool that is currently configured for Federation. Select **Edit properties**.</span></span>
    
      - <span data-ttu-id="4927f-p127">Em **Editar propriedades**, em **Geral**, desmarque **Habilitar federação para este pool de Borda (Porta 5061)**. Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="4927f-p127">In **Edit Properties** under **General**, clear **Enable federation for this Edge pool (Port 5061)**. Click **OK**.</span></span>
    
      - <span data-ttu-id="4927f-p128">Expanda **Pools de borda**, clique com o botão direito no servidor de Borda original ou pool de servidor de Borda que você deseja usar novamente para Federação. Selecione **Editar propriedades**.</span><span class="sxs-lookup"><span data-stu-id="4927f-p128">Expand **Edge pools**, then right click the original Edge server or Edge server pool that you again want to use for Federation. Select **Edit properties**.</span></span>
    
      - <span data-ttu-id="4927f-p129">Em **Editar propriedades**, em **Geral**, selecione **Habilitar federação para este pool de Borda (Porta 5061)**. Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="4927f-p129">In **Edit Properties** under **General**, select **Enable federation for this Edge pool (Port 5061)**. Click **OK**.</span></span>
    
      - <span data-ttu-id="4927f-p130">Clique em **Ação**, selecione **Topologia**, **Publicar**. Quando solicitado em **Publicar a topologia**, clique em **Avançar**. Quando Publicar é finalizado, clique em **Concluir**.</span><span class="sxs-lookup"><span data-stu-id="4927f-p130">Click **Action**, select **Topology**, select **Publish**. When prompted on **Publish the topology**, click **Next**. When the Publish is finished, click **Finish**.</span></span>
    
      - <span data-ttu-id="4927f-226">No servidor de Borda, abra o Assistente de Implantação do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="4927f-226">On the Edge server, open the Skype for Business Server Deployment wizard.</span></span> <span data-ttu-id="4927f-227">Click **Install or Update Skype for Business Server System**, then click Setup or Remove Skype for Business Server **Components**.</span><span class="sxs-lookup"><span data-stu-id="4927f-227">Click **Install or Update Skype for Business Server System**, then click **Setup or Remove Skype for Business Server Components**.</span></span> <span data-ttu-id="4927f-228">Clique em **Executar novamente**.</span><span class="sxs-lookup"><span data-stu-id="4927f-228">Click **Run Again**.</span></span>
    
      - <span data-ttu-id="4927f-229">Clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="4927f-229">Click **Next**.</span></span> <span data-ttu-id="4927f-230">A tela de resumo mostrará ações conforme são executadas.</span><span class="sxs-lookup"><span data-stu-id="4927f-230">The summary screen will show actions as they are executed.</span></span> <span data-ttu-id="4927f-231">Quando a implantação estiver concluída, clique em **Exibir log** para exibir os arquivos de log disponíveis.</span><span class="sxs-lookup"><span data-stu-id="4927f-231">Once the deployment is done, click **View Log** to view available log files.</span></span> <span data-ttu-id="4927f-232">Clique em **Concluir** para concluir a implantação.</span><span class="sxs-lookup"><span data-stu-id="4927f-232">Click **Finish** to complete the deployment.</span></span>

3.  <span data-ttu-id="4927f-233">Se você deseja realizar o fail back da rota de federação XMPP para usar o Servidor de Borda restaurado, faça o seguinte:</span><span class="sxs-lookup"><span data-stu-id="4927f-233">If you want to fail back the XMPP federation route to use the restored Edge Server, do the following:</span></span>
    
      - <span data-ttu-id="4927f-234">Execute o seguinte cmdlet para reapontar a rota de federação XMPP para o pool de Borda que irá hospedar agora a federação XMPP (neste exemplo, EdgeServer1):</span><span class="sxs-lookup"><span data-stu-id="4927f-234">Run the following cmdlet to repoint the XMPP federation route to the Edge pool which will now host XMPP federation (in this example, EdgeServer1):</span></span>
        
            Set-CsSite Site1 -XmppExternalFederationRoute EdgeServer1.contoso.com
        
        <span data-ttu-id="4927f-235">Neste exemplo, Site1 é o local contendo o pool de Borda que irá agora hospedar a rota de federação XMPP e EdgeServer1.contoso.com é o FQDN de um Servidor de Borda no pool.</span><span class="sxs-lookup"><span data-stu-id="4927f-235">In this example, Site1 is the site containing the Edge pool which will now host the XMPP federation route, and EdgeServer1.contoso.com is the FQDN of an Edge Server in that pool.</span></span>
    
      - <span data-ttu-id="4927f-p133">Se você ainda não tiver um registro DNS SRV para a federação XMPP que resolve o pool de Borda que hospedará a federação XMPP, você deve adicioná-lo, conforme no exemplo a seguir. Este registro SRV deve ter um valor de porta de 5269.</span><span class="sxs-lookup"><span data-stu-id="4927f-p133">If you do not already have a DNS SRV record for XMPP federation which resolves to the Edge pool which will now host XMPP federation, you must add it, as in the following example. This SRV record must have a port value of 5269.</span></span>
        
            _xmpp-server._tcp.contoso.com
    
      - <span data-ttu-id="4927f-238">No servidor DNS externo, altere o registro DNS A para federação XMPP apontar para o EdgeServer2.contoso.com.</span><span class="sxs-lookup"><span data-stu-id="4927f-238">On the external DNS server, change the DNS A record for XMPP federation to point to EdgeServer2.contoso.com.</span></span>
    
      - <span data-ttu-id="4927f-239">Verifique se o pool de Borda irá agora hospedar federação XMPP com porta 5269 aberta externamente.</span><span class="sxs-lookup"><span data-stu-id="4927f-239">Verify that the Edge pool which will now host XMPP federation has port 5269 open externally.</span></span>

4.  <span data-ttu-id="4927f-240">Se os pools de front-end permanecem executando no site contendo o pool de Borda que falhou e foi restaurado, você deve atualizar o Serviço de Conferência da Web e o Serviço de Conferência A/V nestes pools de front-end para usar novamente os pools de Borda em seu site local.</span><span class="sxs-lookup"><span data-stu-id="4927f-240">If the Front End pools remained running in the site containing the Edge pool that failed and has been restored, you should update the Web Conferencing Service and A/V Conferencing Service on these Front End pools to again use the Edge pools at their local site.</span></span>

5.  <span data-ttu-id="4927f-241">Se o pool de front-end no mesmo site possui um pool de Borda em falha que também falhou, é possível agora usar Invoke–CsPoolFailback para fazer o fail back do pool de front-end.</span><span class="sxs-lookup"><span data-stu-id="4927f-241">If the Front End pool at the same site as the failed Edge pool also failed, you can now use Invoke–CsPoolFailback to fail back the Front End pool.</span></span>


## <a name="change-the-edge-pool-associated-with-a-front-end-pool"></a><span data-ttu-id="4927f-242">Alterar o pool de Borda associado a um pool de Front-End</span><span class="sxs-lookup"><span data-stu-id="4927f-242">Change the Edge pool associated with a Front End pool</span></span>

<span data-ttu-id="4927f-243">Se um pool de borda cair, mas o pool de front-ends do mesmo local ainda estiver em execução, será preciso configurar o pool de front-ends para que use o pool de borda de um local diferente até que o pool de borda com falha seja restaurado.</span><span class="sxs-lookup"><span data-stu-id="4927f-243">If an Edge pool goes down but the Front End pool at the same site is still running, you will need to set the Front End pool to use an Edge pool at a different site until the failed Edge pool is restored.</span></span>

1.  <span data-ttu-id="4927f-244">NO Construtor de Topologias, navegue até o nome no pool de front-ends que precisa ser alterado.</span><span class="sxs-lookup"><span data-stu-id="4927f-244">In Topology Builder, navigate to the name of the Front End pool you need to change.</span></span>

2.  <span data-ttu-id="4927f-245">Clique com o botão direito do mouse no nome do pool e, então, em **Editar Propriedades**</span><span class="sxs-lookup"><span data-stu-id="4927f-245">Right-click the pool, and then click **Edit Properties**.</span></span>

3.  <span data-ttu-id="4927f-246">Na seção **Associações**, em **Associar Pool de Borda (para componentes de mídia)**, use a caixa suspensa para selecionar o pool de borda ao qual deseja associar o pool de front-ends.</span><span class="sxs-lookup"><span data-stu-id="4927f-246">In the **Associations** section, under **Associate Edge Pool (for media components)**, use the drop down box to select the Edge pool you want to associate this Front End pool with.</span></span>

4.  <span data-ttu-id="4927f-247">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="4927f-247">Click **OK**.</span></span>
