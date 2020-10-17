---
title: 'Lync Server 2013: failover de um pool'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Failing over a pool
ms:assetid: 10b13732-bc80-4cb2-a71c-56b1d6cb5bbb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204678(v=OCS.15)
ms:contentKeyID: 48183432
ms.date: 10/10/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1bf54f1949627c39291388be248e0029077e9278
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48530958"
---
# <a name="failing-over-a-pool-in-lync-server-2013"></a><span data-ttu-id="a9682-102">Failover de um pool no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a9682-102">Failing over a pool in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a9682-103">_**Última modificação do tópico:** 2014-10-10_</span><span class="sxs-lookup"><span data-stu-id="a9682-103">_**Topic Last Modified:** 2014-10-10_</span></span>

<span data-ttu-id="a9682-p101">Se um único pool de Front End falhar e for necessário fazer failover, use o procedimento a seguir. Neste procedimento, o Datacenter1 contém o Pool1, que falhou. Você fará failover no Pool2 localizado no Datacenter2.</span><span class="sxs-lookup"><span data-stu-id="a9682-p101">If a single Front End pool has failed and needs to be failed over, use the following procedure. In this procedure, Datacenter1 contains Pool1, and Pool1 has failed. You are failing over to Pool2 located in Datacenter2.</span></span>

<span data-ttu-id="a9682-107">A maior parte do trabalho do failover de pool envolve a falha do repositório de gerenciamento central, se for necessário.</span><span class="sxs-lookup"><span data-stu-id="a9682-107">Most of the work for the pool failover involves failing over the Central Management store, if it is required.</span></span> <span data-ttu-id="a9682-108">Isso é importante porque o repositório de gerenciamento central deve estar funcional quando os usuários do pool têm failover.</span><span class="sxs-lookup"><span data-stu-id="a9682-108">This is important because the Central Management store must be functional when the pool’s users are failed over.</span></span>

<span data-ttu-id="a9682-p103">Além disso, se um pool de Front End falhar mas o pool de Borda no local ainda estiver em execução, você deve saber se o pool de Borda usa o pool com falha como pool do próximo salto. Se usar, você deve alterar o pool de Borda para usar um pool de Front End diferente antes de fazer o failover do pool de Front End com falha. Como a configuração do próximo salto será alterada dependerá de a Borda usar um pool no mesmo local do pool de Borda ou em um local diferente.</span><span class="sxs-lookup"><span data-stu-id="a9682-p103">Additionally, if a Front End pool fails but the Edge pool at that site is still running, you must know whether the Edge pool uses the failed pool as a next hop pool. If it does, you must change the Edge pool to use a different Front End pool before failing over the failed Front End pool. How you change the next hop setting depends on whether the Edge will use a pool at the same site as the Edge pool, or a different site.</span></span>

<span data-ttu-id="a9682-112">**Para definir um pool de Borda para usar um pool do próximo salto no mesmo local**</span><span class="sxs-lookup"><span data-stu-id="a9682-112">**To Set an Edge Pool to Use a Next Hop Pool at the Same Site**</span></span>

1.  <span data-ttu-id="a9682-113">Abra o construtor de topologias, clique com o botão direito do mouse no pool de borda que precisa ser alterado e clique em **Editar propriedades**.</span><span class="sxs-lookup"><span data-stu-id="a9682-113">Open Topology Builder, right-click the Edge pool that needs to be changed, and click **Edit Properties**.</span></span>

2.  <span data-ttu-id="a9682-p104">Clique em **Próximo Salto**. Na lista **Pool do próximo salto:**, selecione o pool que servirá como pool do próximo salto.</span><span class="sxs-lookup"><span data-stu-id="a9682-p104">Click **Next Hop**. From the **Next hop pool:** list, select the pool which will now serve as the next hop pool.</span></span>

3.  <span data-ttu-id="a9682-116">Clique em **OK** e publique as alterações.</span><span class="sxs-lookup"><span data-stu-id="a9682-116">Click **OK**, and then publish the changes.</span></span>

<span data-ttu-id="a9682-117">**Para definir um pool de Borda para usar um pool do próximo salto em um local diferente**</span><span class="sxs-lookup"><span data-stu-id="a9682-117">**To Set an Edge Pool to Use a Next Hop Pool at a Different Site**</span></span>

1.  <span data-ttu-id="a9682-118">Abra uma janela do Shell de gerenciamento do Lync Server e digite o seguinte cmdlet:</span><span class="sxs-lookup"><span data-stu-id="a9682-118">Open a Lync Server Management Shell window and type the following cmdlet:</span></span>
    
        Set-CsEdgeServer -Identity EdgeServer:<Edge Server pool FQDN> -Registrar Registrar:<NextHopPoolFQDN>

<span data-ttu-id="a9682-119">**Para fazer failover de um pool em um desastre**</span><span class="sxs-lookup"><span data-stu-id="a9682-119">**To Fail Over a Pool in a Disaster**</span></span>

1.  <span data-ttu-id="a9682-120">Encontre o pool do servidor de gerenciamento central digitando o seguinte cmdlet em um servidor front-end no Pool2:</span><span class="sxs-lookup"><span data-stu-id="a9682-120">Find which pool is the host for the Central Management Server by typing the following cmdlet on a Front End server in Pool2:</span></span>
    
        Invoke-CsManagementServerFailover -Whatif
    
    <span data-ttu-id="a9682-121">Os resultados deste cmdlet mostram qual pool atualmente hospeda o servidor de gerenciamento central.</span><span class="sxs-lookup"><span data-stu-id="a9682-121">The results of this cmdlet show which pool currently hosts the Central Management Server.</span></span> <span data-ttu-id="a9682-122">No restante deste procedimento, esse pool é conhecido como pool de CMS \_ .</span><span class="sxs-lookup"><span data-stu-id="a9682-122">In the rest of this procedure, this pool is known as CMS\_Pool.</span></span>

2.  <span data-ttu-id="a9682-123">Use o construtor de topologias para localizar a versão do Lync Server em execução no pool do CMS \_ .</span><span class="sxs-lookup"><span data-stu-id="a9682-123">Use Topology Builder to find the version of Lync Server running on the CMS\_Pool.</span></span> <span data-ttu-id="a9682-124">Se ele estiver executando o Lync Server 2013, use o cmdlet a seguir para localizar o pool de backup do pool 1.</span><span class="sxs-lookup"><span data-stu-id="a9682-124">If it is running Lync Server 2013, use the following cmdlet to find the backup pool of Pool 1.</span></span>
    
        Get-CsPoolBackupRelationship -PoolFQDN <CMS_Pool FQDN>
    
    <span data-ttu-id="a9682-125">Permite que \_ o pool de backup seja o pool de backup.</span><span class="sxs-lookup"><span data-stu-id="a9682-125">Let Backup\_Pool be the backup pool.</span></span>

3.  <span data-ttu-id="a9682-126">Verifique o status do repositório de gerenciamento central com o seguinte cmdlet:</span><span class="sxs-lookup"><span data-stu-id="a9682-126">Check the status of the Central Management store with the following cmdlet:</span></span>
    
        Get-CsManagementStoreReplicationStatus -CentralManagementStoreStatus 
    
    <span data-ttu-id="a9682-127">Este cmdlet deve mostrar que tanto ActiveMasterFQDN quanto ActiveFileTransferAgents estão apontando para o FQDN do \_ pool CMS.</span><span class="sxs-lookup"><span data-stu-id="a9682-127">This cmdlet should show that both ActiveMasterFQDN and ActiveFileTransferAgents are pointing to the FQDN of CMS\_Pool.</span></span> <span data-ttu-id="a9682-128">Se eles estiverem vazios, o servidor de gerenciamento central não estará disponível e você deverá fazer o failover.</span><span class="sxs-lookup"><span data-stu-id="a9682-128">If they are empty, the Central Management Server is not available and you must fail it over.</span></span>

4.  <span data-ttu-id="a9682-129">Se o repositório de gerenciamento central não estiver disponível ou se o repositório de gerenciamento central estiver em execução no Pool1 (ou seja, o pool com falha), você deverá fazer failover do servidor de gerenciamento central antes de realizar o failover do pool.</span><span class="sxs-lookup"><span data-stu-id="a9682-129">If the Central Management store is not available or if the Central Management store was running on Pool1 (that is, the pool that has failed), you must fail over the Central Management Server before failing over the pool.</span></span> <span data-ttu-id="a9682-130">Se você precisar fazer failover do servidor de gerenciamento central hospedado em um pool executando o Lync Server 2013, use o cmdlet na etapa 5 deste procedimento.</span><span class="sxs-lookup"><span data-stu-id="a9682-130">If you need to fail over the Central Management Server that was hosted on a pool running Lync Server 2013, use the cmdlet in step 5 of this procedure.</span></span> <span data-ttu-id="a9682-131">Se você precisar fazer failover do servidor de gerenciamento central hospedado em um pool executando o Lync Server 2010, use o cmdlet na etapa 6 deste procedimento.</span><span class="sxs-lookup"><span data-stu-id="a9682-131">If you need to fail over the Central Management Server that was hosted on a pool running Lync Server 2010, use the cmdlet in step 6 of this procedure.</span></span> <span data-ttu-id="a9682-132">Se você não precisar fazer failover do servidor de gerenciamento central, pule para a etapa 7 deste procedimento.</span><span class="sxs-lookup"><span data-stu-id="a9682-132">If you do not need to fail over the Central Management Server, skip to step 7 of this procedure.</span></span>

5.  <span data-ttu-id="a9682-133">Para fazer failover do repositório de gerenciamento central em um pool executando o Lync Server 2013, faça o seguinte:</span><span class="sxs-lookup"><span data-stu-id="a9682-133">To fail over the Central Management store on a pool running Lync Server 2013, do the following:</span></span>
    
      - <span data-ttu-id="a9682-134">Primeiro, verifique o servidor back-end no \_ pool de backup que executa a instância principal do repositório de gerenciamento central digitando o seguinte:</span><span class="sxs-lookup"><span data-stu-id="a9682-134">First, check which Back End Server in Backup\_Pool runs the principal instance of the Central Management store by typing the following:</span></span>
        
            Get-CsDatabaseMirrorState -DatabaseType Centralmgmt -PoolFqdn <Backup_Pool Fqdn>
    
      - <span data-ttu-id="a9682-135">Se o servidor back-end principal no \_ pool de backup for o principal, digite:</span><span class="sxs-lookup"><span data-stu-id="a9682-135">If the primary Back End Server in Backup\_Pool is the principal, type:</span></span>
        
            Invoke-CSManagementServerFailover -BackupSQLServerFqdn <Backup_Pool Primary BackEnd Server FQDN> -BackupSQLInstanceName <Backup_Pool Primary SQL Instance Name>
        
        <span data-ttu-id="a9682-136">Se o servidor de back-end de espelho no pool de backup \_ for o principal, digite:</span><span class="sxs-lookup"><span data-stu-id="a9682-136">If the mirror Back End Server in Backup\_Pool is the principal, type:</span></span>
        
            Invoke-CSManagementServerFailover -MirrorSQLServerFqdn <Backup_Pool Mirror BackEnd Server FQDN> -MirrorSQLInstanceName <Backup_Pool Mirror SQL Instance Name>
    
      - <span data-ttu-id="a9682-137">Valide a conclusão do failover do servidor de gerenciamento central.</span><span class="sxs-lookup"><span data-stu-id="a9682-137">Validate that the Central Management Server failover is complete.</span></span> <span data-ttu-id="a9682-138">Digite:</span><span class="sxs-lookup"><span data-stu-id="a9682-138">Type the following:</span></span>
        
            Get-CsManagementStoreReplicationStatus -CentralManagementStoreStatus 
        
        <span data-ttu-id="a9682-139">Verifique se ActiveMasterFQDN e ActiveFileTransferAgents estão apontando para o FQDN do pool de backup \_ .</span><span class="sxs-lookup"><span data-stu-id="a9682-139">Check that both ActiveMasterFQDN and ActiveFileTransferAgents are pointing to the FQDN of Backup\_Pool.</span></span>
    
      - <span data-ttu-id="a9682-140">Por fim, verifique o status da réplica para todos os servidores front-end digitando o seguinte:</span><span class="sxs-lookup"><span data-stu-id="a9682-140">Finally, check the replica status for all Front End Servers by typing the following:</span></span>
        
            Get-CsManagementStoreReplicationStatus 
        
        <span data-ttu-id="a9682-141">Verifique se todas as réplicas possuem o valor Verdadeiro (True).</span><span class="sxs-lookup"><span data-stu-id="a9682-141">Check that all replicas have a value of True.</span></span>
        
        <span data-ttu-id="a9682-142">Pule para a etapa 7 neste procedimento.</span><span class="sxs-lookup"><span data-stu-id="a9682-142">Skip to step 7 in this procedure.</span></span>

6.  <span data-ttu-id="a9682-143">Instale o repositório de gerenciamento central no servidor back-end do \_ pool de backup.</span><span class="sxs-lookup"><span data-stu-id="a9682-143">Install the Central Management store on the Back End Server of Backup\_Pool.</span></span>
    
      - <span data-ttu-id="a9682-144">Primeiro, execute o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="a9682-144">First, run the following command:</span></span>
        
        ```PowerShell 
        Install-CsDatabase -CentralManagementDatabase -Clean -SqlServerFqdn <Backup_Pool Back End Server FQDN> -SqlInstanceName rtc  
        ```
    
      - <span data-ttu-id="a9682-145">Execute o próximo comando em um dos servidores de front-end do \_ pool de backup para forçar a movimentação do repositório de gerenciamento central:</span><span class="sxs-lookup"><span data-stu-id="a9682-145">Run the next command on one of the Front End Servers of Backup\_Pool to force the move of the Central Management store:</span></span>
        
            Move-CsManagementServer -ConfigurationFileName c:\CsConfigurationFile.zip -LisConfigurationFileName c:\CsLisConfigurationFile.zip -Force 
    
      - <span data-ttu-id="a9682-146">Valide se a movimentação está concluída:</span><span class="sxs-lookup"><span data-stu-id="a9682-146">Validate the move is complete:</span></span>
        
            Get-CsManagementStoreReplicationStatus -CentralManagementStoreStatus 
        
        <span data-ttu-id="a9682-147">Verifique se ActiveMasterFQDN e ActiveFileTransferAgents estão apontando para o FQDN do pool de backup \_ .</span><span class="sxs-lookup"><span data-stu-id="a9682-147">Check that both ActiveMasterFQDN and ActiveFileTransferAgents are pointing to the FQDN of Backup\_Pool.</span></span>
    
      - <span data-ttu-id="a9682-148">Verifique o status da réplica para todos os servidores de Front End digitando:</span><span class="sxs-lookup"><span data-stu-id="a9682-148">Check the replica status for all Front End Servers by typing the following:</span></span>
        
            Get-CsManagementStoreReplicationStatus 
        
        <span data-ttu-id="a9682-149">Verifique se todas as réplicas possuem o valor Verdadeiro (True).</span><span class="sxs-lookup"><span data-stu-id="a9682-149">Check that all replicas have a value of True.</span></span>
    
      - <span data-ttu-id="a9682-150">Instale o serviço do servidor de gerenciamento central no restante dos servidores de front-end no pool de backup \_ .</span><span class="sxs-lookup"><span data-stu-id="a9682-150">Install the Central Management Server service on the rest of the Front End Servers in Backup\_Pool.</span></span> <span data-ttu-id="a9682-151">Para fazer isso, execute o seguinte comando em todos os servidores front-end, exceto aquele que você usou ao forçar a movimentação do repositório de gerenciamento central neste procedimento:</span><span class="sxs-lookup"><span data-stu-id="a9682-151">To do so, run the following command on all the Front End Servers, except the one you used when forcing the Central Management store move earlier in this procedure:</span></span>
        
            Bootstrapper /Setup 

7.  <span data-ttu-id="a9682-152">Faça failover dos usuários do Pool1 para o Pool2 executando o seguinte cmdlet em uma janela do Shell de gerenciamento do Lync Server:</span><span class="sxs-lookup"><span data-stu-id="a9682-152">Fail over the users from Pool1 to Pool2 by running the following cmdlet in a Lync Server Management Shell window:</span></span>
    
        Invoke-CsPoolFailover -PoolFQDN <Pool1 FQDN> -DisasterMode -Verbose
    
    <span data-ttu-id="a9682-153">Como as etapas executadas nas partes anteriores deste procedimento para verificar o status do repositório de gerenciamento central não são universais, ainda há uma chance de que esse cmdlet falhe porque o repositório de gerenciamento central ainda não foi completamente failover.</span><span class="sxs-lookup"><span data-stu-id="a9682-153">Because the steps taken in the previous parts of this procedure to check the Central Management store status are not universal, there is still a chance this cmdlet will fail because the Central Management store is not yet fully failed over.</span></span> <span data-ttu-id="a9682-154">Nesse caso, você deve corrigir o repositório de gerenciamento central com base nas mensagens de erro exibidas e executar esse cmdlet novamente.</span><span class="sxs-lookup"><span data-stu-id="a9682-154">In this case, you must fix the Central Management store based on the error messages that you see, and then run this cmdlet again.</span></span>
    
    <span data-ttu-id="a9682-p112">Se a mensagem de erro a seguir for apresentada, será necessário alterar o pool de Borda neste local para usar um pool diferente como próximo salto antes da fazer o failover do pool. Para detalhes, consulte os procedimentos no início deste tópico.</span><span class="sxs-lookup"><span data-stu-id="a9682-p112">If you see the following error message, then you need to change the Edge pool at this site to use a different pool as its next hop before failing over the pool. For details, see the procedures at the beginning of this topic.</span></span>
    
        Invoke-CsPoolFailOver : This Front-end pool "pool1.contoso.com" is specified in
        topology as the next hop for the Edge server. Failing over this pool may cause External
        access/Federation/Split-domain/XMPP features to stop working. Please use Topology Builder to
        change the Edge internal next hop setting to point to a different Front-end pool,  before you
        proceed.

</div>

<span> </span>

</div>

</div>

</div>

