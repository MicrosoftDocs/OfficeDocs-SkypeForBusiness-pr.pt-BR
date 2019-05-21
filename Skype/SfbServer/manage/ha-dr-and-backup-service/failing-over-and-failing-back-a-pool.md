---
title: Havendo falha e havendo falha em um pool
ms.reviewer: ''
author: lanachin
ms.author: v-lanac
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: .
ms.openlocfilehash: 2848261164ac568d3db4dd05160b7e50ec3981d3
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34303880"
---
# <a name="failing-over-and-failing-back-a-pool-in-skype-for-business-server"></a><span data-ttu-id="79409-103">Com failover e failback de um pool no Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="79409-103">Failing over and failing back a pool in Skype for Business Server</span></span> 

<span data-ttu-id="79409-104">Use os procedimentos a seguir se um único pool de front-end tiver falhado e precisar de failover, ou se o pool que sofreu o desastre estiver novamente online e você precisar restaurar a implantação para o status de trabalho normal.</span><span class="sxs-lookup"><span data-stu-id="79409-104">Use the following procedures if a single Front End pool has failed and needs to be failed over, or the pool that experienced the disaster is back online and you need to restore your deployment to regular working status.</span></span> <span data-ttu-id="79409-105">Além disso, saiba como fazer failover e failback do pool de bordas usado para a Federação do Skype for Business ou Federação do XMPP ou alterar o pool de bordas associado a um pool de front-ends.</span><span class="sxs-lookup"><span data-stu-id="79409-105">Also  learn how to fail over and fail back the Edge pool used for Skype for Business federation or XMPP federation, or change the Edge pool associated with a Front End pool.</span></span>

- [<span data-ttu-id="79409-106">Fazer failover em um pool de front-end</span><span class="sxs-lookup"><span data-stu-id="79409-106">Fail over a Front End pool</span></span>](#fail-over-a-front-end-pool)
- [<span data-ttu-id="79409-107">Fazer failback de um pool</span><span class="sxs-lookup"><span data-stu-id="79409-107">Fail back a pool</span></span>](#fail-back-a-pool)
- [<span data-ttu-id="79409-108">Fazer failover do pool de bordas usado para o Skype for Business Server Federation</span><span class="sxs-lookup"><span data-stu-id="79409-108">Fail over the Edge pool used for Skype for Business Server federation</span></span>](#fail-over-the-edge-pool-used-for-skype-for-business-server-federation)
- [<span data-ttu-id="79409-109">Fazer failover do pool de bordas usado para a Federação do XMPP no Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="79409-109">Fail over the Edge pool used for XMPP federation in Skype for Business Server</span></span>](#fail-over-the-edge-pool-used-for-xmpp-federation-in-skype-for-business-server)
- [<span data-ttu-id="79409-110">Fazer failback do pool de bordas usado para Federação do Skype for Business Server ou Federação do XMPP</span><span class="sxs-lookup"><span data-stu-id="79409-110">Fail back the Edge pool used for Skype for Business Server federation or XMPP federation</span></span>](#fail-back-the-edge-pool-used-for-skype-for-business-server-federation-or-xmpp-federation)
- [<span data-ttu-id="79409-111">Alterar o pool de bordas associado a um pool de front-end</span><span class="sxs-lookup"><span data-stu-id="79409-111">Change the Edge pool associated with a Front End pool</span></span>](#change-the-edge-pool-associated-with-a-front-end-pool)

## <a name="fail-over-a-front-end-pool"></a><span data-ttu-id="79409-112">Fazer failover em um pool de front-end</span><span class="sxs-lookup"><span data-stu-id="79409-112">Fail over a Front End pool</span></span>

<span data-ttu-id="79409-113">Neste procedimento, Datacenter1 contém Pool1, e Pool1 falhou.</span><span class="sxs-lookup"><span data-stu-id="79409-113">In this procedure, Datacenter1 contains Pool1, and Pool1 has failed.</span></span> <span data-ttu-id="79409-114">Você está falhando no Pool2 localizado no Datacenter2.</span><span class="sxs-lookup"><span data-stu-id="79409-114">You are failing over to Pool2 located in Datacenter2.</span></span>

<span data-ttu-id="79409-115">A maior parte do trabalho do failover de pool envolve a falha em relação ao repositório de gerenciamento central, se for necessário.</span><span class="sxs-lookup"><span data-stu-id="79409-115">Most of the work for the pool failover involves failing over the Central Management store, if it is required.</span></span> <span data-ttu-id="79409-116">Isso é importante porque o repositório de gerenciamento central deve ser funcional quando os usuários do pool tiverem failover.</span><span class="sxs-lookup"><span data-stu-id="79409-116">This is important because the Central Management store must be functional when the pool’s users are failed over.</span></span>

<span data-ttu-id="79409-117">Além disso, se um pool de front-ends falhar, mas o pool de bordas nesse site ainda estiver em execução, você deverá saber se o pool de bordas usa o pool com falha como um próximo pool de saltos.</span><span class="sxs-lookup"><span data-stu-id="79409-117">Additionally, if a Front End pool fails but the Edge pool at that site is still running, you must know whether the Edge pool uses the failed pool as a next hop pool.</span></span> <span data-ttu-id="79409-118">Em caso afirmativo, você deve alterar o pool de bordas para usar um pool de front-end diferente antes de falhar sobre o pool de front-ends com falha.</span><span class="sxs-lookup"><span data-stu-id="79409-118">If it does, you must change the Edge pool to use a different Front End pool before failing over the failed Front End pool.</span></span> <span data-ttu-id="79409-119">A maneira como você altera a próxima configuração de salto depende se a borda usará um pool no mesmo site que o pool de bordas ou um site diferente.</span><span class="sxs-lookup"><span data-stu-id="79409-119">How you change the next hop setting depends on whether the Edge will use a pool at the same site as the Edge pool, or a different site.</span></span>

<span data-ttu-id="79409-120">**Para definir um pool de bordas para usar um próximo pool de saltos no mesmo site**</span><span class="sxs-lookup"><span data-stu-id="79409-120">**To set an Edge pool to use a next hop pool at the same site**</span></span>

1.  <span data-ttu-id="79409-121">Abra o construtor de topologias, clique com o botão direito do mouse no pool de bordas que precisa ser alterado e clique em **Editar propriedades**.</span><span class="sxs-lookup"><span data-stu-id="79409-121">Open Topology Builder, right-click the Edge pool that needs to be changed, and click **Edit Properties**.</span></span>

2.  <span data-ttu-id="79409-122">Clique em **próximo salto**.</span><span class="sxs-lookup"><span data-stu-id="79409-122">Click **Next Hop**.</span></span> <span data-ttu-id="79409-123">Na lista **próximo pool de saltos:** , selecione o pool que agora funcionará como o próximo pool de saltos.</span><span class="sxs-lookup"><span data-stu-id="79409-123">From the **Next hop pool:** list, select the pool which will now serve as the next hop pool.</span></span>

3.  <span data-ttu-id="79409-124">Clique em **OK**e, em seguida, publique as alterações.</span><span class="sxs-lookup"><span data-stu-id="79409-124">Click **OK**, and then publish the changes.</span></span>

<span data-ttu-id="79409-125">**Para definir um pool de bordas para usar um próximo pool de saltos em um site diferente**</span><span class="sxs-lookup"><span data-stu-id="79409-125">**To set an Edge pool to use a next hop pool at a different site**</span></span>

1.  <span data-ttu-id="79409-126">Abra uma janela do Shell de gerenciamento do Skype for Business Server e digite o seguinte cmdlet:</span><span class="sxs-lookup"><span data-stu-id="79409-126">Open a Skype for Business Server Management Shell window and type the following cmdlet:</span></span>
    
        Set-CsEdgeServer -Identity EdgeServer:<Edge Server pool FQDN> -Registrar Registrar:<NextHopPoolFQDN>

<span data-ttu-id="79409-127">**Para causar failover em um pool em um desastre**</span><span class="sxs-lookup"><span data-stu-id="79409-127">**To fail over a pool in a disaster**</span></span>

1.  <span data-ttu-id="79409-128">Localize o pool que é o host do servidor de gerenciamento central, digitando o cmdlet a seguir em um servidor front-end no Pool2:</span><span class="sxs-lookup"><span data-stu-id="79409-128">Find which pool is the host for the Central Management Server by typing the following cmdlet on a Front End server in Pool2:</span></span>
    
        Invoke-CsManagementServerFailover -Whatif
    
    <span data-ttu-id="79409-129">Os resultados deste cmdlet mostram qual pool atualmente hospeda o servidor central de gerenciamento.</span><span class="sxs-lookup"><span data-stu-id="79409-129">The results of this cmdlet show which pool currently hosts the Central Management Server.</span></span> <span data-ttu-id="79409-130">No restante deste procedimento, esse pool é conhecido como o pool de\_CMS.</span><span class="sxs-lookup"><span data-stu-id="79409-130">In the rest of this procedure, this pool is known as CMS\_Pool.</span></span>

2.  <span data-ttu-id="79409-131">Use o construtor de topologias para localizar a versão do Skype for Business Server em\_execução no pool do CMS.</span><span class="sxs-lookup"><span data-stu-id="79409-131">Use Topology Builder to find the version of Skype for Business Server running on the CMS\_Pool.</span></span> <span data-ttu-id="79409-132">Se ele estiver executando o Skype for Business Server, use o cmdlet a seguir para localizar o pool de backup do pool 1.</span><span class="sxs-lookup"><span data-stu-id="79409-132">If it is running Skype for Business Server, use the following cmdlet to find the backup pool of Pool 1.</span></span>
    
        Get-CsPoolBackupRelationship -PoolFQDN <CMS_Pool FQDN>
    
    <span data-ttu-id="79409-133">Permitir que\_o pool de backup seja o pool de backup.</span><span class="sxs-lookup"><span data-stu-id="79409-133">Let Backup\_Pool be the backup pool.</span></span>

3.  <span data-ttu-id="79409-134">Verifique o status do repositório central de gerenciamento com o seguinte cmdlet:</span><span class="sxs-lookup"><span data-stu-id="79409-134">Check the status of the Central Management store with the following cmdlet:</span></span>
    
        Get-CsManagementStoreReplicationStatus -CentralManagementStoreStatus 
    
    <span data-ttu-id="79409-135">Este cmdlet deve mostrar que ambos ActiveMasterFQDN e ActiveFileTransferAgents estão apontando para o FQDN do pool\_de CMS.</span><span class="sxs-lookup"><span data-stu-id="79409-135">This cmdlet should show that both ActiveMasterFQDN and ActiveFileTransferAgents are pointing to the FQDN of CMS\_Pool.</span></span> <span data-ttu-id="79409-136">Se estiverem vazios, o servidor central de gerenciamento não está disponível e você deve fazer o failover.</span><span class="sxs-lookup"><span data-stu-id="79409-136">If they are empty, the Central Management Server is not available and you must fail it over.</span></span>

4.  <span data-ttu-id="79409-137">Se o repositório de gerenciamento central não estiver disponível ou se o repositório de gerenciamento central estiver em execução no Pool1 (ou seja, o pool com falha), você deverá fazer failover do servidor de gerenciamento central antes de falhar sobre o pool.</span><span class="sxs-lookup"><span data-stu-id="79409-137">If the Central Management store is not available or if the Central Management store was running on Pool1 (that is, the pool that has failed), you must fail over the Central Management Server before failing over the pool.</span></span> <span data-ttu-id="79409-138">Se você precisar fazer failover do servidor de gerenciamento central hospedado em um pool que executa o Skype for Business Server, use o cmdlet na etapa 5 deste procedimento.</span><span class="sxs-lookup"><span data-stu-id="79409-138">If you need to fail over the Central Management Server that was hosted on a pool running Skype for Business Server, use the cmdlet in step 5 of this procedure.</span></span> <span data-ttu-id="79409-139">Se você não precisar fazer failover do servidor de gerenciamento central, pule para a etapa 7 deste procedimento.</span><span class="sxs-lookup"><span data-stu-id="79409-139">If you do not need to fail over the Central Management Server, skip to step 7 of this procedure.</span></span>

5.  <span data-ttu-id="79409-140">Para fazer failover do repositório de gerenciamento central em um pool que executa o Skype for Business Server, faça o seguinte:</span><span class="sxs-lookup"><span data-stu-id="79409-140">To fail over the Central Management store on a pool running Skype for Business Server, do the following:</span></span>
    
      - <span data-ttu-id="79409-141">Primeiro, verifique qual servidor back-end no\_pool de backup executa a instância principal do repositório de gerenciamento central digitando o seguinte:</span><span class="sxs-lookup"><span data-stu-id="79409-141">First, check which Back End Server in Backup\_Pool runs the principal instance of the Central Management store by typing the following:</span></span>
        
            Get-CsDatabaseMirrorState -DatabaseType Centralmgmt -PoolFqdn <Backup_Pool Fqdn>
    
      - <span data-ttu-id="79409-142">Se o servidor back-end principal no\_pool de backup for o principal, digite:</span><span class="sxs-lookup"><span data-stu-id="79409-142">If the primary Back End Server in Backup\_Pool is the principal, type:</span></span>
        
            Invoke-CSManagementServerFailover -BackupSQLServerFqdn <Backup_Pool Primary BackEnd Server FQDN> -BackupSQLInstanceName <Backup_Pool Primary SQL Instance Name>
        
        <span data-ttu-id="79409-143">Se o servidor de back-end do\_espelho no pool de backup for o principal, digite:</span><span class="sxs-lookup"><span data-stu-id="79409-143">If the mirror Back End Server in Backup\_Pool is the principal, type:</span></span>
        
            Invoke-CSManagementServerFailover -MirrorSQLServerFqdn <Backup_Pool Mirror BackEnd Server FQDN> -MirrorSQLInstanceName <Backup_Pool Mirror SQL Instance Name>
    
      - <span data-ttu-id="79409-144">Confirme se o failover do servidor de gerenciamento central está concluído.</span><span class="sxs-lookup"><span data-stu-id="79409-144">Validate that the Central Management Server failover is complete.</span></span> <span data-ttu-id="79409-145">Digite o seguinte:</span><span class="sxs-lookup"><span data-stu-id="79409-145">Type the following:</span></span>
        
            Get-CsManagementStoreReplicationStatus -CentralManagementStoreStatus 
        
        <span data-ttu-id="79409-146">Verifique se ambos ActiveMasterFQDN e ActiveFileTransferAgents estão apontando para o FQDN do pool\_de backup.</span><span class="sxs-lookup"><span data-stu-id="79409-146">Check that both ActiveMasterFQDN and ActiveFileTransferAgents are pointing to the FQDN of Backup\_Pool.</span></span>
    
      - <span data-ttu-id="79409-147">Por fim, verifique o status da réplica de todos os servidores de front-end digitando o seguinte:</span><span class="sxs-lookup"><span data-stu-id="79409-147">Finally, check the replica status for all Front End Servers by typing the following:</span></span>
        
            Get-CsManagementStoreReplicationStatus 
        
        <span data-ttu-id="79409-148">Verifique se todas as réplicas têm um valor de verdadeiro.</span><span class="sxs-lookup"><span data-stu-id="79409-148">Check that all replicas have a value of True.</span></span>
        
        <span data-ttu-id="79409-149">Pule para a etapa 7 deste procedimento.</span><span class="sxs-lookup"><span data-stu-id="79409-149">Skip to step 7 in this procedure.</span></span>

6.  <span data-ttu-id="79409-150">Instale o repositório de gerenciamento central no servidor back-end do\_pool de backup.</span><span class="sxs-lookup"><span data-stu-id="79409-150">Install the Central Management store on the Back End Server of Backup\_Pool.</span></span>
    
      - <span data-ttu-id="79409-151">Primeiro, execute o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="79409-151">First, run the following command:</span></span>
        
        ``` 
        Install-CsDatabase -CentralManagementDatabase -Clean -SqlServerFqdn <Backup_Pool Back End Server FQDN> -SqlInstanceName rtc  
        ```
    
      - <span data-ttu-id="79409-152">Execute o próximo comando em um dos servidores front-end do pool\_de backup para forçar a mudança do repositório de gerenciamento central:</span><span class="sxs-lookup"><span data-stu-id="79409-152">Run the next command on one of the Front End Servers of Backup\_Pool to force the move of the Central Management store:</span></span>
        
            Move-CsManagementServer -ConfigurationFileName c:\CsConfigurationFile.zip -LisConfigurationFileName c:\CsLisConfigurationFile.zip -Force 
    
      - <span data-ttu-id="79409-153">Validar conclusão da mudança:</span><span class="sxs-lookup"><span data-stu-id="79409-153">Validate the move is complete:</span></span>
        
            Get-CsManagementStoreReplicationStatus -CentralManagementStoreStatus 
        
        <span data-ttu-id="79409-154">Verifique se ambos ActiveMasterFQDN e ActiveFileTransferAgents estão apontando para o FQDN do pool\_de backup.</span><span class="sxs-lookup"><span data-stu-id="79409-154">Check that both ActiveMasterFQDN and ActiveFileTransferAgents are pointing to the FQDN of Backup\_Pool.</span></span>
    
      - <span data-ttu-id="79409-155">Verifique o status da réplica de todos os servidores de front-end digitando o seguinte:</span><span class="sxs-lookup"><span data-stu-id="79409-155">Check the replica status for all Front End Servers by typing the following:</span></span>
        
            Get-CsManagementStoreReplicationStatus 
        
        <span data-ttu-id="79409-156">Verifique se todas as réplicas têm um valor de verdadeiro.</span><span class="sxs-lookup"><span data-stu-id="79409-156">Check that all replicas have a value of True.</span></span>
    
      - <span data-ttu-id="79409-157">Instale o serviço central de gerenciamento do servidor no restante dos servidores de front-end\_no pool de backup.</span><span class="sxs-lookup"><span data-stu-id="79409-157">Install the Central Management Server service on the rest of the Front End Servers in Backup\_Pool.</span></span> <span data-ttu-id="79409-158">Para fazer isso, execute o seguinte comando em todos os servidores de front-end, exceto o que você usou ao forçar o repositório de gerenciamento central a se mover anteriormente neste procedimento:</span><span class="sxs-lookup"><span data-stu-id="79409-158">To do so, run the following command on all the Front End Servers, except the one you used when forcing the Central Management store move earlier in this procedure:</span></span>
        
            Bootstrapper /Setup 

7.  <span data-ttu-id="79409-159">Reprovar os usuários do Pool1 para o Pool2 executando o seguinte cmdlet em uma janela do Shell de gerenciamento do Skype for Business Server:</span><span class="sxs-lookup"><span data-stu-id="79409-159">Fail over the users from Pool1 to Pool2 by running the following cmdlet in a Skype for Business Server Management Shell window:</span></span>
    
        Invoke-CsPoolFailover -PoolFQDN <Pool1 FQDN> -DisasterMode -Verbose
    
    <span data-ttu-id="79409-160">Como as etapas executadas nas partes anteriores deste procedimento para verificar o status do repositório de gerenciamento central não são universais, ainda há uma chance de que esse cmdlet falhe porque o repositório de gerenciamento central ainda não passou por failover completo.</span><span class="sxs-lookup"><span data-stu-id="79409-160">Because the steps taken in the previous parts of this procedure to check the Central Management store status are not universal, there is still a chance this cmdlet will fail because the Central Management store is not yet fully failed over.</span></span> <span data-ttu-id="79409-161">Nesse caso, você deve corrigir o repositório de gerenciamento central com base nas mensagens de erro que você vê e executar esse cmdlet novamente.</span><span class="sxs-lookup"><span data-stu-id="79409-161">In this case, you must fix the Central Management store based on the error messages that you see, and then run this cmdlet again.</span></span>
    
    <span data-ttu-id="79409-162">Se você vir a mensagem de erro a seguir, será necessário alterar o pool de bordas neste site para usar um pool diferente como próximo salto antes de falhar sobre o pool.</span><span class="sxs-lookup"><span data-stu-id="79409-162">If you see the following error message, then you need to change the Edge pool at this site to use a different pool as its next hop before failing over the pool.</span></span> <span data-ttu-id="79409-163">Para obter detalhes, consulte os procedimentos no início deste tópico.</span><span class="sxs-lookup"><span data-stu-id="79409-163">For details, see the procedures at the beginning of this topic.</span></span>
    
        Invoke-CsPoolFailOver : This Front-end pool "pool1.contoso.com" is specified in
        topology as the next hop for the Edge server. Failing over this pool may cause External
        access/Federation/Split-domain/XMPP features to stop working. Please use Topology Builder to
        change the Edge internal next hop setting to point to a different Front-end pool,  before you
        proceed.


## <a name="fail-back-a-pool"></a><span data-ttu-id="79409-164">Fazer failback de um pool</span><span class="sxs-lookup"><span data-stu-id="79409-164">Fail back a pool</span></span>

<span data-ttu-id="79409-165">Após o pool que sofreu o desastre ficar online novamente (ou seja, Pool1 neste exemplo), siga as etapas a seguir para restaurar a implantação para o status de trabalho normal.</span><span class="sxs-lookup"><span data-stu-id="79409-165">After the pool that experienced the disaster is back online (that is, Pool1 in this example), take the following steps to restore your deployment to regular working status.</span></span>

<span data-ttu-id="79409-166">Observe que o processo de failback demora vários minutos para ser concluído.</span><span class="sxs-lookup"><span data-stu-id="79409-166">Note that the failback process takes several minute to complete.</span></span><span data-ttu-id="79409-167">Para referência, a expectativa é de até 60 minutos para um pool de 20.000 usuários.</span><span class="sxs-lookup"><span data-stu-id="79409-167">  For reference, it is expected to take up to 60 minutes for a pool of 20,000 users.</span></span>

<span data-ttu-id="79409-168">Reproduza os usuários que estavam originalmente hospedados no Pool1 e que falharam no Pool2 digitando o seguinte cmdlet:</span><span class="sxs-lookup"><span data-stu-id="79409-168">Fail back the users who were originally homed in Pool1 and have been failed over to Pool2 by typing the following cmdlet:</span></span>
    
    Invoke-CsPoolFailback -PoolFQDN <Pool1 FQDN> -Verbose

<span data-ttu-id="79409-169">Nenhuma outra etapa é necessária.</span><span class="sxs-lookup"><span data-stu-id="79409-169">No other steps are necessary.</span></span> <span data-ttu-id="79409-170">Se você tiver reprovado o servidor central de gerenciamento, poderá deixá-lo no Pool2.</span><span class="sxs-lookup"><span data-stu-id="79409-170">If you failed over the Central Management Server, you can leave it in Pool2.</span></span>

## <a name="fail-over-the-edge-pool-used-for-skype-for-business-server-federation"></a><span data-ttu-id="79409-171">Fazer failover do pool de bordas usado para o Skype for Business Server Federation</span><span class="sxs-lookup"><span data-stu-id="79409-171">Fail over the Edge pool used for Skype for Business Server federation</span></span> 

<span data-ttu-id="79409-172">Se o pool de bordas em que você tiver configurado o Skype for Business Server configurado ficar inativo, você deverá alterar a Federação para usar um pool de bordas diferente para o trabalho de Federação.</span><span class="sxs-lookup"><span data-stu-id="79409-172">If the Edge pool where you have Skype for Business Server federation configured goes down, you must change federation to use a different Edge pool for federation to work.</span></span>

1.  <span data-ttu-id="79409-173">Em um servidor front-end, abra o construtor de topologias.</span><span class="sxs-lookup"><span data-stu-id="79409-173">On a Front End server, open Topology Builder.</span></span> <span data-ttu-id="79409-174">Expanda Pools de **bordas**e clique com o botão direito do mouse no servidor de borda ou no pool do servidor de borda atualmente configurado para Federação.</span><span class="sxs-lookup"><span data-stu-id="79409-174">Expand **Edge pools**, and then right-click the Edge server or Edge server pool that is currently configured for Federation.</span></span> <span data-ttu-id="79409-175">Selecione **Editar propriedades**.</span><span class="sxs-lookup"><span data-stu-id="79409-175">Select **Edit properties**.</span></span>

2.  <span data-ttu-id="79409-176">Em **Editar propriedades** em **geral**, desmarque **habilitar Federação para este pool de bordas (porta 5061)**.</span><span class="sxs-lookup"><span data-stu-id="79409-176">In **Edit Properties** under **General**, clear **Enable federation for this Edge pool (Port 5061)**.</span></span> <span data-ttu-id="79409-177">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="79409-177">Click **OK**.</span></span>

3.  <span data-ttu-id="79409-178">Expanda Pools de **bordas**e clique com o botão direito do mouse no servidor de borda ou no pool do servidor de borda que você agora deseja usar para a Federação.</span><span class="sxs-lookup"><span data-stu-id="79409-178">Expand **Edge pools**, and then right-click the Edge server or Edge server pool that you now want to use for Federation.</span></span> <span data-ttu-id="79409-179">Selecione **Editar propriedades**.</span><span class="sxs-lookup"><span data-stu-id="79409-179">Select **Edit properties**.</span></span>

4.  <span data-ttu-id="79409-180">Em **Editar propriedades** em **geral**, selecione **habilitar Federação para este pool de bordas (porta 5061)**.</span><span class="sxs-lookup"><span data-stu-id="79409-180">In **Edit Properties** under **General**, select **Enable federation for this Edge pool (Port 5061)**.</span></span> <span data-ttu-id="79409-181">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="79409-181">Click **OK**.</span></span>

5.  <span data-ttu-id="79409-182">Clique em **ação**, selecione **topologia**, selecione **publicar**.</span><span class="sxs-lookup"><span data-stu-id="79409-182">Click **Action**, select **Topology**, select **Publish**.</span></span> <span data-ttu-id="79409-183">Quando solicitado em **publicar a topologia**, clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="79409-183">When prompted on **Publish the topology**, click **Next**.</span></span> <span data-ttu-id="79409-184">Quando a publicação estiver concluída, clique em **concluir**.</span><span class="sxs-lookup"><span data-stu-id="79409-184">When the Publish is finished, click **Finish**.</span></span>

6.  <span data-ttu-id="79409-185">No servidor de borda, abra o assistente de implantação do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="79409-185">On the Edge server, open the Skype for Business Server Deployment wizard.</span></span> <span data-ttu-id="79409-186">Clique em **instalar ou atualizar o sistema do Skype for Business Server**e, em seguida, clique em **Configurar ou remover componentes do Skype for Business Server**.</span><span class="sxs-lookup"><span data-stu-id="79409-186">Click **Install or Update Skype for Business Server System**, and then click **Setup or Remove Skype for Business Server Components**.</span></span> <span data-ttu-id="79409-187">Clique em **executar novamente**.</span><span class="sxs-lookup"><span data-stu-id="79409-187">Click **Run Again**.</span></span>

7.  <span data-ttu-id="79409-188">Click **Next**.</span><span class="sxs-lookup"><span data-stu-id="79409-188">Click **Next**.</span></span> <span data-ttu-id="79409-189">A tela Resumo mostrará as ações conforme elas são executadas.</span><span class="sxs-lookup"><span data-stu-id="79409-189">The summary screen will show actions as they are executed.</span></span> <span data-ttu-id="79409-190">Depois que a implantação for concluída, clique em **Exibir log** para exibir os arquivos de log disponíveis.</span><span class="sxs-lookup"><span data-stu-id="79409-190">Once the deployment is done, click **View Log** to view available log files.</span></span> <span data-ttu-id="79409-191">Clique em **concluir** para concluir a implantação.</span><span class="sxs-lookup"><span data-stu-id="79409-191">Click **Finish** to complete the deployment.</span></span>
    
    <span data-ttu-id="79409-192">Se o site que contém o pool de bordas com falha contiver servidores front-end que ainda estão em execução, você deve atualizar o serviço de Webconferência e o serviço de conferência A/V nesses pools de front-ends para usar um pool de bordas em um site remoto que ainda esteja em execução.</span><span class="sxs-lookup"><span data-stu-id="79409-192">If the site containing the failed Edge pool contains Front End Servers that are still running, you must update the Web Conferencing Service and A/V Conferencing Service on these Front End pools to use an Edge pool in a remote site that is still running.</span></span> 

 ## <a name="fail-over-the-edge-pool-used-for-xmpp-federation-in-skype-for-business-server"></a><span data-ttu-id="79409-193">Fazer failover do pool de bordas usado para a Federação do XMPP no Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="79409-193">Fail over the Edge pool used for XMPP federation in Skype for Business Server</span></span> 

<span data-ttu-id="79409-194">Em sua organização, há um pool de bordas designado como o pool a ser usado para a Federação do XMPP.</span><span class="sxs-lookup"><span data-stu-id="79409-194">In your organization, there is one Edge pool designated as the pool to use for XMPP federation.</span></span> <span data-ttu-id="79409-195">Se esse pool ficar inativo, você deve fazer failover da Federação do XMPP para usar um pool de bordas diferente antes que o XMPP federado possa funcionar novamente.</span><span class="sxs-lookup"><span data-stu-id="79409-195">If this pool goes down, you must fail over XMPP federation to use a different Edge pool before XMPP federation can work again.</span></span>

<span data-ttu-id="79409-196">Ao instalar primeiro os pools de borda e habilitar a Federação do XMPP, você pode simplificar o processo de recuperação de desastres Configurando os registros SRV DNS externos para todos os seus pools de bordas para a Federação do XMPP, em vez de apenas um.</span><span class="sxs-lookup"><span data-stu-id="79409-196">When you first install Edge pools and enable XMPP Federation, you can simplify the disaster recovery process by setting up external DNS SRV records for all of your Edge pools for XMPP federation, instead of just one.</span></span> <span data-ttu-id="79409-197">Cada um desses registros SRV deve ter um conjunto de prioridades diferente.</span><span class="sxs-lookup"><span data-stu-id="79409-197">Each of these SRV records must have a different priority set.</span></span> <span data-ttu-id="79409-198">Todo o tráfego de Federação do XMPP passa pelo pool com o registro SRV com a prioridade mais alta.</span><span class="sxs-lookup"><span data-stu-id="79409-198">All XMPP federation traffic goes through the pool with the SRV record with the highest priority.</span></span> 

<span data-ttu-id="79409-199">No procedimento a seguir, EdgePool1 é o pool que hospeda originalmente a Federação do XMPP, e EdgePool2 é o pool que agora hospeda XMPP Federação.</span><span class="sxs-lookup"><span data-stu-id="79409-199">In the following procedure, EdgePool1 is the pool which originally hosted XMPP federation, and EdgePool2 is the pool which will now host XMPP federation.</span></span>


### <a name="to-fail-over-the-edge-pool-used-for-xmpp-federation"></a><span data-ttu-id="79409-200">Para fazer failover do pool de bordas usado para a Federação do XMPP</span><span class="sxs-lookup"><span data-stu-id="79409-200">To fail over the Edge pool used for XMPP federation</span></span>

1.  <span data-ttu-id="79409-201">Se você ainda não tiver outro pool de bordas implantado (além do que está indisponível no momento), implante esse pool.</span><span class="sxs-lookup"><span data-stu-id="79409-201">If you don’t already have another Edge pool deployed (besides the one which is currently down), deploy that pool.</span></span> 

2.  <span data-ttu-id="79409-202">Em cada servidor de borda no novo pool de bordas que agora hospeda a Federação do XMPP (EdgePool2), execute o seguinte cmdlet:</span><span class="sxs-lookup"><span data-stu-id="79409-202">On each Edge Server in the new Edge pool which will now host XMPP federation (EdgePool2), run the following cmdlet:</span></span>
    
        Stop-CsWindowsService

3.  <span data-ttu-id="79409-203">Execute o cmdlet a seguir para redirecionar a rota de Federação do XMPP para EdgePool2:</span><span class="sxs-lookup"><span data-stu-id="79409-203">Run the following cmdlet to repoint the XMPP federation route to EdgePool2:</span></span>
    
        Set-CsSite Site2 -XmppExternalFederationRoute EdgeServer2.contoso.com
    
    <span data-ttu-id="79409-204">Neste exemplo, site2 é o site que contém o pool de borda que agora hospeda a rota de Federação do XMPP, e EdgeServer2.contoso.com é o FQDN de um servidor de borda nesse pool.</span><span class="sxs-lookup"><span data-stu-id="79409-204">In this example, Site2 is the site containing the Edge pool which will now host the XMPP federation route, and EdgeServer2.contoso.com is the FQDN of an Edge Server in that pool.</span></span>

4.  <span data-ttu-id="79409-205">No servidor DNS externo, altere o registro DNS a para a Federação XMPP para apontar para EdgeServer2.contoso.com.</span><span class="sxs-lookup"><span data-stu-id="79409-205">On the external DNS server, change the DNS A record for XMPP federation to point to EdgeServer2.contoso.com.</span></span>

5.  <span data-ttu-id="79409-206">Se você ainda não tiver um registro SRV DNS para a Federação do XMPP, que é resolvido para o pool de borda que agora hospedará a Federação do XMPP, você deve adicioná-lo, como no exemplo a seguir.</span><span class="sxs-lookup"><span data-stu-id="79409-206">If you do not already have a DNS SRV record for XMPP federation which resolves to the Edge pool which will now host XMPP federation, you must add it, as in the following example.</span></span> <span data-ttu-id="79409-207">Esse registro SRV deve ter um valor de porta 5269.</span><span class="sxs-lookup"><span data-stu-id="79409-207">This SRV record must have a port value of 5269.</span></span>
    
        _xmpp-server._tcp.contoso.com

6.  <span data-ttu-id="79409-208">Verifique se o pool de bordas que agora hospeda a Federação do XMPP tem a porta 5269 aberta externamente.</span><span class="sxs-lookup"><span data-stu-id="79409-208">Verify that the Edge pool which will now host XMPP federation has port 5269 open externally.</span></span>

7.  <span data-ttu-id="79409-209">Inicie os serviços em todos os servidores de borda do pool de borda que agora hospedarão a Federação do XMPP:</span><span class="sxs-lookup"><span data-stu-id="79409-209">Start the services on all Edge Servers in the Edge pool which will now host XMPP federation:</span></span>
    
        Start-CsWindowsService


## <a name="fail-back-the-edge-pool-used-for-skype-for-business-server-federation-or-xmpp-federation"></a><span data-ttu-id="79409-210">Fazer failback do pool de bordas usado para Federação do Skype for Business Server ou Federação do XMPP</span><span class="sxs-lookup"><span data-stu-id="79409-210">Fail back the Edge pool used for Skype for Business Server federation or XMPP federation</span></span> 

<span data-ttu-id="79409-211">Depois que um pool de borda com falha que foi usado para hospedar a Federação foi colocado online novamente, use este procedimento para fazer failback da rota de Federação do Skype for Business Server e/ou da rota de Federação do XMPP novamente para usar este pool de bordas restaurado.</span><span class="sxs-lookup"><span data-stu-id="79409-211">After a failed Edge pool that used to host federation has been brought back online, use this procedure to fail back the Skype for Business Server federation route and/or the XMPP federation route to again use this restored Edge pool.</span></span>

1.  <span data-ttu-id="79409-212">No pool de bordas que agora está disponível novamente, inicie os serviços de borda.</span><span class="sxs-lookup"><span data-stu-id="79409-212">On the Edge pool that is now available again, start the Edge Services.</span></span>

2.  <span data-ttu-id="79409-213">Se você quiser fazer failback da rota de Federação do Skype for Business Server para usar o servidor de borda restaurado, faça o seguinte:</span><span class="sxs-lookup"><span data-stu-id="79409-213">If you want to fail back the Skype for Business Server federation route to use the restored Edge Server, do the following:</span></span>
    
      - <span data-ttu-id="79409-214">Em um servidor front-end, abra o construtor de topologias.</span><span class="sxs-lookup"><span data-stu-id="79409-214">On a Front End server, open Topology Builder.</span></span> <span data-ttu-id="79409-215">Expanda Pools de **bordas**, clique com o botão direito do mouse no servidor de borda ou no pool do servidor de borda que está atualmente configurado para Federação.</span><span class="sxs-lookup"><span data-stu-id="79409-215">Expand **Edge pools**, then right click the Edge server or Edge server pool that is currently configured for Federation.</span></span> <span data-ttu-id="79409-216">Selecione **Editar propriedades**.</span><span class="sxs-lookup"><span data-stu-id="79409-216">Select **Edit properties**.</span></span>
    
      - <span data-ttu-id="79409-217">Em **Editar propriedades** em **geral**, desmarque **habilitar Federação para este pool de bordas (porta 5061)**.</span><span class="sxs-lookup"><span data-stu-id="79409-217">In **Edit Properties** under **General**, clear **Enable federation for this Edge pool (Port 5061)**.</span></span> <span data-ttu-id="79409-218">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="79409-218">Click **OK**.</span></span>
    
      - <span data-ttu-id="79409-219">Expanda Pools de **bordas**e clique com o botão direito do mouse no servidor de borda original ou no pool do servidor de borda que você deseja usar novamente para a Federação.</span><span class="sxs-lookup"><span data-stu-id="79409-219">Expand **Edge pools**, then right click the original Edge server or Edge server pool that you again want to use for Federation.</span></span> <span data-ttu-id="79409-220">Selecione **Editar propriedades**.</span><span class="sxs-lookup"><span data-stu-id="79409-220">Select **Edit properties**.</span></span>
    
      - <span data-ttu-id="79409-221">Em **Editar propriedades** em **geral**, selecione **habilitar Federação para este pool de bordas (porta 5061)**.</span><span class="sxs-lookup"><span data-stu-id="79409-221">In **Edit Properties** under **General**, select **Enable federation for this Edge pool (Port 5061)**.</span></span> <span data-ttu-id="79409-222">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="79409-222">Click **OK**.</span></span>
    
      - <span data-ttu-id="79409-223">Clique em **ação**, selecione **topologia**, selecione **publicar**.</span><span class="sxs-lookup"><span data-stu-id="79409-223">Click **Action**, select **Topology**, select **Publish**.</span></span> <span data-ttu-id="79409-224">Quando solicitado em **publicar a topologia**, clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="79409-224">When prompted on **Publish the topology**, click **Next**.</span></span> <span data-ttu-id="79409-225">Quando a publicação estiver concluída, clique em **concluir**.</span><span class="sxs-lookup"><span data-stu-id="79409-225">When the Publish is finished, click **Finish**.</span></span>
    
      - <span data-ttu-id="79409-226">No servidor de borda, abra o assistente de implantação do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="79409-226">On the Edge server, open the Skype for Business Server Deployment wizard.</span></span> <span data-ttu-id="79409-227">Clique em **instalar ou atualizar o sistema do Skype for Business Server**, em seguida, clique em **Configurar ou remover componentes do Skype for Business Server**.</span><span class="sxs-lookup"><span data-stu-id="79409-227">Click **Install or Update Skype for Business Server System**, then click **Setup or Remove Skype for Business Server Components**.</span></span> <span data-ttu-id="79409-228">Clique em **executar novamente**.</span><span class="sxs-lookup"><span data-stu-id="79409-228">Click **Run Again**.</span></span>
    
      - <span data-ttu-id="79409-229">Click **Next**.</span><span class="sxs-lookup"><span data-stu-id="79409-229">Click **Next**.</span></span> <span data-ttu-id="79409-230">A tela Resumo mostrará as ações conforme elas são executadas.</span><span class="sxs-lookup"><span data-stu-id="79409-230">The summary screen will show actions as they are executed.</span></span> <span data-ttu-id="79409-231">Depois que a implantação for concluída, clique em **Exibir log** para exibir os arquivos de log disponíveis.</span><span class="sxs-lookup"><span data-stu-id="79409-231">Once the deployment is done, click **View Log** to view available log files.</span></span> <span data-ttu-id="79409-232">Clique em **concluir** para concluir a implantação.</span><span class="sxs-lookup"><span data-stu-id="79409-232">Click **Finish** to complete the deployment.</span></span>

3.  <span data-ttu-id="79409-233">Se você quiser fazer failback na rota de Federação do XMPP para usar o servidor de borda restaurado, faça o seguinte:</span><span class="sxs-lookup"><span data-stu-id="79409-233">If you want to fail back the XMPP federation route to use the restored Edge Server, do the following:</span></span>
    
      - <span data-ttu-id="79409-234">Execute o cmdlet a seguir para redirecionar a rota de Federação do XMPP para o pool de borda que agora hospeda a Federação XMPP (neste exemplo, EdgeServer1):</span><span class="sxs-lookup"><span data-stu-id="79409-234">Run the following cmdlet to repoint the XMPP federation route to the Edge pool which will now host XMPP federation (in this example, EdgeServer1):</span></span>
        
            Set-CsSite Site1 -XmppExternalFederationRoute EdgeServer1.contoso.com
        
        <span data-ttu-id="79409-235">Neste exemplo, site1 é o site que contém o pool de borda que agora hospeda a rota de Federação do XMPP, e EdgeServer1.contoso.com é o FQDN de um servidor de borda nesse pool.</span><span class="sxs-lookup"><span data-stu-id="79409-235">In this example, Site1 is the site containing the Edge pool which will now host the XMPP federation route, and EdgeServer1.contoso.com is the FQDN of an Edge Server in that pool.</span></span>
    
      - <span data-ttu-id="79409-236">Se você ainda não tiver um registro SRV DNS para a Federação do XMPP, que é resolvido para o pool de borda que agora hospedará a Federação do XMPP, você deve adicioná-lo, como no exemplo a seguir.</span><span class="sxs-lookup"><span data-stu-id="79409-236">If you do not already have a DNS SRV record for XMPP federation which resolves to the Edge pool which will now host XMPP federation, you must add it, as in the following example.</span></span> <span data-ttu-id="79409-237">Esse registro SRV deve ter um valor de porta 5269.</span><span class="sxs-lookup"><span data-stu-id="79409-237">This SRV record must have a port value of 5269.</span></span>
        
            _xmpp-server._tcp.contoso.com
    
      - <span data-ttu-id="79409-238">No servidor DNS externo, altere o registro DNS a para a Federação XMPP para apontar para EdgeServer2.contoso.com.</span><span class="sxs-lookup"><span data-stu-id="79409-238">On the external DNS server, change the DNS A record for XMPP federation to point to EdgeServer2.contoso.com.</span></span>
    
      - <span data-ttu-id="79409-239">Verifique se o pool de bordas que agora hospeda a Federação do XMPP tem a porta 5269 aberta externamente.</span><span class="sxs-lookup"><span data-stu-id="79409-239">Verify that the Edge pool which will now host XMPP federation has port 5269 open externally.</span></span>

4.  <span data-ttu-id="79409-240">Se os pools de front-end permanecerem sendo executados no site que contém o pool de borda que falhou e foi restaurado, você deverá atualizar o serviço de Webconferência e o serviço de conferência A/V nesses pools de front-ends para usar novamente os pools de borda em seu site local.</span><span class="sxs-lookup"><span data-stu-id="79409-240">If the Front End pools remained running in the site containing the Edge pool that failed and has been restored, you should update the Web Conferencing Service and A/V Conferencing Service on these Front End pools to again use the Edge pools at their local site.</span></span>

5.  <span data-ttu-id="79409-241">Se o pool de front-ends no mesmo site do pool de borda com falha também falhar, agora você pode usar Invoke – CsPoolFailback para fazer failback do pool de front-ends.</span><span class="sxs-lookup"><span data-stu-id="79409-241">If the Front End pool at the same site as the failed Edge pool also failed, you can now use Invoke–CsPoolFailback to fail back the Front End pool.</span></span>


## <a name="change-the-edge-pool-associated-with-a-front-end-pool"></a><span data-ttu-id="79409-242">Alterar o pool de bordas associado a um pool de front-end</span><span class="sxs-lookup"><span data-stu-id="79409-242">Change the Edge pool associated with a Front End pool</span></span>

<span data-ttu-id="79409-243">Se um pool de bordas ficar inoperante, mas o pool de front-end no mesmo site ainda estiver em execução, será necessário definir o pool de front-ends para usar um pool de bordas em um site diferente até que o pool de bordas com falha seja restaurado.</span><span class="sxs-lookup"><span data-stu-id="79409-243">If an Edge pool goes down but the Front End pool at the same site is still running, you will need to set the Front End pool to use an Edge pool at a different site until the failed Edge pool is restored.</span></span>

1.  <span data-ttu-id="79409-244">No construtor de topologias, navegue até o nome do pool de front-ends que você precisa alterar.</span><span class="sxs-lookup"><span data-stu-id="79409-244">In Topology Builder, navigate to the name of the Front End pool you need to change.</span></span>

2.  <span data-ttu-id="79409-245">Clique com o botão direito do mouse no pool e, em seguida, clique em **Editar propriedades**.</span><span class="sxs-lookup"><span data-stu-id="79409-245">Right-click the pool, and then click **Edit Properties**.</span></span>

3.  <span data-ttu-id="79409-246">Na seção **associações** , em associar a um **pool de bordas (para componentes de mídia)**, use a caixa suspensa para selecionar o pool de bordas ao qual você deseja associar esse pool de front-ends.</span><span class="sxs-lookup"><span data-stu-id="79409-246">In the **Associations** section, under **Associate Edge Pool (for media components)**, use the drop down box to select the Edge pool you want to associate this Front End pool with.</span></span>

4.  <span data-ttu-id="79409-247">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="79409-247">Click **OK**.</span></span>
