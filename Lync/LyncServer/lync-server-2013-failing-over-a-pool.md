---
title: 'Lync Server 2013: Fazendo failover de um pool'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Failing over a pool
ms:assetid: 10b13732-bc80-4cb2-a71c-56b1d6cb5bbb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204678(v=OCS.15)
ms:contentKeyID: 48183432
ms.date: 10/10/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 512d7bc09d40d7b99cc66970cdd2a5584030fea9
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34829183"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="failing-over-a-pool-in-lync-server-2013"></a><span data-ttu-id="10c72-102">Fazendo failover de um pool no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="10c72-102">Failing over a pool in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="10c72-103">_**Tópico da última modificação:** 2014-10-10_</span><span class="sxs-lookup"><span data-stu-id="10c72-103">_**Topic Last Modified:** 2014-10-10_</span></span>

<span data-ttu-id="10c72-104">Se um único pool de front-end tiver falhado e precisar de failover, use o procedimento a seguir.</span><span class="sxs-lookup"><span data-stu-id="10c72-104">If a single Front End pool has failed and needs to be failed over, use the following procedure.</span></span> <span data-ttu-id="10c72-105">Neste procedimento, Datacenter1 contém Pool1, e Pool1 falhou.</span><span class="sxs-lookup"><span data-stu-id="10c72-105">In this procedure, Datacenter1 contains Pool1, and Pool1 has failed.</span></span> <span data-ttu-id="10c72-106">Você está falhando no Pool2 localizado no Datacenter2.</span><span class="sxs-lookup"><span data-stu-id="10c72-106">You are failing over to Pool2 located in Datacenter2.</span></span>

<span data-ttu-id="10c72-107">A maior parte do trabalho do failover de pool envolve a falha em relação ao repositório de gerenciamento central, se for necessário.</span><span class="sxs-lookup"><span data-stu-id="10c72-107">Most of the work for the pool failover involves failing over the Central Management store, if it is required.</span></span> <span data-ttu-id="10c72-108">Isso é importante porque o repositório de gerenciamento central deve ser funcional quando os usuários do pool tiverem failover.</span><span class="sxs-lookup"><span data-stu-id="10c72-108">This is important because the Central Management store must be functional when the pool’s users are failed over.</span></span>

<span data-ttu-id="10c72-109">Além disso, se um pool de front-ends falhar, mas o pool de bordas nesse site ainda estiver em execução, você deverá saber se o pool de bordas usa o pool com falha como um próximo pool de saltos.</span><span class="sxs-lookup"><span data-stu-id="10c72-109">Additionally, if a Front End pool fails but the Edge pool at that site is still running, you must know whether the Edge pool uses the failed pool as a next hop pool.</span></span> <span data-ttu-id="10c72-110">Em caso afirmativo, você deve alterar o pool de bordas para usar um pool de front-end diferente antes de falhar sobre o pool de front-ends com falha.</span><span class="sxs-lookup"><span data-stu-id="10c72-110">If it does, you must change the Edge pool to use a different Front End pool before failing over the failed Front End pool.</span></span> <span data-ttu-id="10c72-111">A maneira como você altera a próxima configuração de salto depende se a borda usará um pool no mesmo site que o pool de bordas ou um site diferente.</span><span class="sxs-lookup"><span data-stu-id="10c72-111">How you change the next hop setting depends on whether the Edge will use a pool at the same site as the Edge pool, or a different site.</span></span>

<span data-ttu-id="10c72-112">**Para definir um pool de bordas para usar um próximo pool de saltos no mesmo site**</span><span class="sxs-lookup"><span data-stu-id="10c72-112">**To Set an Edge Pool to Use a Next Hop Pool at the Same Site**</span></span>

1.  <span data-ttu-id="10c72-113">Abra o construtor de topologias, clique com o botão direito do mouse no pool de bordas que precisa ser alterado e clique em **Editar propriedades**.</span><span class="sxs-lookup"><span data-stu-id="10c72-113">Open Topology Builder, right-click the Edge pool that needs to be changed, and click **Edit Properties**.</span></span>

2.  <span data-ttu-id="10c72-114">Clique em **próximo salto**.</span><span class="sxs-lookup"><span data-stu-id="10c72-114">Click **Next Hop**.</span></span> <span data-ttu-id="10c72-115">Na lista **próximo pool de saltos:** , selecione o pool que agora funcionará como o próximo pool de saltos.</span><span class="sxs-lookup"><span data-stu-id="10c72-115">From the **Next hop pool:** list, select the pool which will now serve as the next hop pool.</span></span>

3.  <span data-ttu-id="10c72-116">Clique em **OK**e, em seguida, publique as alterações.</span><span class="sxs-lookup"><span data-stu-id="10c72-116">Click **OK**, and then publish the changes.</span></span>

<span data-ttu-id="10c72-117">**Para definir um pool de bordas para usar um próximo pool de saltos em um site diferente**</span><span class="sxs-lookup"><span data-stu-id="10c72-117">**To Set an Edge Pool to Use a Next Hop Pool at a Different Site**</span></span>

1.  <span data-ttu-id="10c72-118">Abra uma janela do Shell de gerenciamento do Lync Server e digite o seguinte cmdlet:</span><span class="sxs-lookup"><span data-stu-id="10c72-118">Open a Lync Server Management Shell window and type the following cmdlet:</span></span>
    
        Set-CsEdgeServer -Identity EdgeServer:<Edge Server pool FQDN> -Registrar Registrar:<NextHopPoolFQDN>

<span data-ttu-id="10c72-119">**Para causar failover em um pool em um desastre**</span><span class="sxs-lookup"><span data-stu-id="10c72-119">**To Fail Over a Pool in a Disaster**</span></span>

1.  <span data-ttu-id="10c72-120">Localize o pool que é o host do servidor de gerenciamento central, digitando o cmdlet a seguir em um servidor front-end no Pool2:</span><span class="sxs-lookup"><span data-stu-id="10c72-120">Find which pool is the host for the Central Management Server by typing the following cmdlet on a Front End server in Pool2:</span></span>
    
        Invoke-CsManagementServerFailover -Whatif
    
    <span data-ttu-id="10c72-121">Os resultados deste cmdlet mostram qual pool atualmente hospeda o servidor central de gerenciamento.</span><span class="sxs-lookup"><span data-stu-id="10c72-121">The results of this cmdlet show which pool currently hosts the Central Management Server.</span></span> <span data-ttu-id="10c72-122">No restante deste procedimento, esse pool é conhecido como o pool de\_CMS.</span><span class="sxs-lookup"><span data-stu-id="10c72-122">In the rest of this procedure, this pool is known as CMS\_Pool.</span></span>

2.  <span data-ttu-id="10c72-123">Use o construtor de topologias para localizar a versão do Lync Server em\_execução no pool de CMS.</span><span class="sxs-lookup"><span data-stu-id="10c72-123">Use Topology Builder to find the version of Lync Server running on the CMS\_Pool.</span></span> <span data-ttu-id="10c72-124">Se ele estiver executando o Lync Server 2013, use o cmdlet a seguir para localizar o pool de backup do pool 1.</span><span class="sxs-lookup"><span data-stu-id="10c72-124">If it is running Lync Server 2013, use the following cmdlet to find the backup pool of Pool 1.</span></span>
    
        Get-CsPoolBackupRelationship -PoolFQDN <CMS_Pool FQDN>
    
    <span data-ttu-id="10c72-125">Permitir que\_o pool de backup seja o pool de backup.</span><span class="sxs-lookup"><span data-stu-id="10c72-125">Let Backup\_Pool be the backup pool.</span></span>

3.  <span data-ttu-id="10c72-126">Verifique o status do repositório central de gerenciamento com o seguinte cmdlet:</span><span class="sxs-lookup"><span data-stu-id="10c72-126">Check the status of the Central Management store with the following cmdlet:</span></span>
    
        Get-CsManagementStoreReplicationStatus -CentralManagementStoreStatus 
    
    <span data-ttu-id="10c72-127">Este cmdlet deve mostrar que ambos ActiveMasterFQDN e ActiveFileTransferAgents estão apontando para o FQDN do pool\_de CMS.</span><span class="sxs-lookup"><span data-stu-id="10c72-127">This cmdlet should show that both ActiveMasterFQDN and ActiveFileTransferAgents are pointing to the FQDN of CMS\_Pool.</span></span> <span data-ttu-id="10c72-128">Se estiverem vazios, o servidor central de gerenciamento não está disponível e você deve fazer o failover.</span><span class="sxs-lookup"><span data-stu-id="10c72-128">If they are empty, the Central Management Server is not available and you must fail it over.</span></span>

4.  <span data-ttu-id="10c72-129">Se o repositório de gerenciamento central não estiver disponível ou se o repositório de gerenciamento central estiver em execução no Pool1 (ou seja, o pool com falha), você deverá fazer failover do servidor de gerenciamento central antes de falhar sobre o pool.</span><span class="sxs-lookup"><span data-stu-id="10c72-129">If the Central Management store is not available or if the Central Management store was running on Pool1 (that is, the pool that has failed), you must fail over the Central Management Server before failing over the pool.</span></span> <span data-ttu-id="10c72-130">Se você precisar fazer failover do servidor de gerenciamento central hospedado em um pool que executa o Lync Server 2013, use o cmdlet na etapa 5 deste procedimento.</span><span class="sxs-lookup"><span data-stu-id="10c72-130">If you need to fail over the Central Management Server that was hosted on a pool running Lync Server 2013, use the cmdlet in step 5 of this procedure.</span></span> <span data-ttu-id="10c72-131">Se você precisar fazer failover do servidor de gerenciamento central hospedado em um pool que executa o Lync Server 2010, use o cmdlet na etapa 6 deste procedimento.</span><span class="sxs-lookup"><span data-stu-id="10c72-131">If you need to fail over the Central Management Server that was hosted on a pool running Lync Server 2010, use the cmdlet in step 6 of this procedure.</span></span> <span data-ttu-id="10c72-132">Se você não precisar fazer failover do servidor de gerenciamento central, pule para a etapa 7 deste procedimento.</span><span class="sxs-lookup"><span data-stu-id="10c72-132">If you do not need to fail over the Central Management Server, skip to step 7 of this procedure.</span></span>

5.  <span data-ttu-id="10c72-133">Para fazer failover do repositório de gerenciamento central em um pool que executa o Lync Server 2013, faça o seguinte:</span><span class="sxs-lookup"><span data-stu-id="10c72-133">To fail over the Central Management store on a pool running Lync Server 2013, do the following:</span></span>
    
      - <span data-ttu-id="10c72-134">Primeiro, verifique qual servidor back-end no\_pool de backup executa a instância principal do repositório de gerenciamento central digitando o seguinte:</span><span class="sxs-lookup"><span data-stu-id="10c72-134">First, check which Back End Server in Backup\_Pool runs the principal instance of the Central Management store by typing the following:</span></span>
        
            Get-CsDatabaseMirrorState -DatabaseType Centralmgmt -PoolFqdn <Backup_Pool Fqdn>
    
      - <span data-ttu-id="10c72-135">Se o servidor back-end principal no\_pool de backup for o principal, digite:</span><span class="sxs-lookup"><span data-stu-id="10c72-135">If the primary Back End Server in Backup\_Pool is the principal, type:</span></span>
        
            Invoke-CSManagementServerFailover -BackupSQLServerFqdn <Backup_Pool Primary BackEnd Server FQDN> -BackupSQLInstanceName <Backup_Pool Primary SQL Instance Name>
        
        <span data-ttu-id="10c72-136">Se o servidor de back-end do\_espelho no pool de backup for o principal, digite:</span><span class="sxs-lookup"><span data-stu-id="10c72-136">If the mirror Back End Server in Backup\_Pool is the principal, type:</span></span>
        
            Invoke-CSManagementServerFailover -MirrorSQLServerFqdn <Backup_Pool Mirror BackEnd Server FQDN> -MirrorSQLInstanceName <Backup_Pool Mirror SQL Instance Name>
    
      - <span data-ttu-id="10c72-137">Confirme se o failover do servidor de gerenciamento central está concluído.</span><span class="sxs-lookup"><span data-stu-id="10c72-137">Validate that the Central Management Server failover is complete.</span></span> <span data-ttu-id="10c72-138">Digite o seguinte:</span><span class="sxs-lookup"><span data-stu-id="10c72-138">Type the following:</span></span>
        
            Get-CsManagementStoreReplicationStatus -CentralManagementStoreStatus 
        
        <span data-ttu-id="10c72-139">Verifique se ambos ActiveMasterFQDN e ActiveFileTransferAgents estão apontando para o FQDN do pool\_de backup.</span><span class="sxs-lookup"><span data-stu-id="10c72-139">Check that both ActiveMasterFQDN and ActiveFileTransferAgents are pointing to the FQDN of Backup\_Pool.</span></span>
    
      - <span data-ttu-id="10c72-140">Por fim, verifique o status da réplica de todos os servidores de front-end digitando o seguinte:</span><span class="sxs-lookup"><span data-stu-id="10c72-140">Finally, check the replica status for all Front End Servers by typing the following:</span></span>
        
            Get-CsManagementStoreReplicationStatus 
        
        <span data-ttu-id="10c72-141">Verifique se todas as réplicas têm um valor de verdadeiro.</span><span class="sxs-lookup"><span data-stu-id="10c72-141">Check that all replicas have a value of True.</span></span>
        
        <span data-ttu-id="10c72-142">Pule para a etapa 7 deste procedimento.</span><span class="sxs-lookup"><span data-stu-id="10c72-142">Skip to step 7 in this procedure.</span></span>

6.  <span data-ttu-id="10c72-143">Instale o repositório de gerenciamento central no servidor back-end do\_pool de backup.</span><span class="sxs-lookup"><span data-stu-id="10c72-143">Install the Central Management store on the Back End Server of Backup\_Pool.</span></span>
    
      - <span data-ttu-id="10c72-144">Primeiro, execute o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="10c72-144">First, run the following command:</span></span>
        
        ``` 
        Install-CsDatabase -CentralManagementDatabase -Clean -SqlServerFqdn <Backup_Pool Back End Server FQDN> -SqlInstanceName rtc  
        ```
    
      - <span data-ttu-id="10c72-145">Execute o próximo comando em um dos servidores front-end do pool\_de backup para forçar a mudança do repositório de gerenciamento central:</span><span class="sxs-lookup"><span data-stu-id="10c72-145">Run the next command on one of the Front End Servers of Backup\_Pool to force the move of the Central Management store:</span></span>
        
            Move-CsManagementServer -ConfigurationFileName c:\CsConfigurationFile.zip -LisConfigurationFileName c:\CsLisConfigurationFile.zip -Force 
    
      - <span data-ttu-id="10c72-146">Validar conclusão da mudança:</span><span class="sxs-lookup"><span data-stu-id="10c72-146">Validate the move is complete:</span></span>
        
            Get-CsManagementStoreReplicationStatus -CentralManagementStoreStatus 
        
        <span data-ttu-id="10c72-147">Verifique se ambos ActiveMasterFQDN e ActiveFileTransferAgents estão apontando para o FQDN do pool\_de backup.</span><span class="sxs-lookup"><span data-stu-id="10c72-147">Check that both ActiveMasterFQDN and ActiveFileTransferAgents are pointing to the FQDN of Backup\_Pool.</span></span>
    
      - <span data-ttu-id="10c72-148">Verifique o status da réplica de todos os servidores de front-end digitando o seguinte:</span><span class="sxs-lookup"><span data-stu-id="10c72-148">Check the replica status for all Front End Servers by typing the following:</span></span>
        
            Get-CsManagementStoreReplicationStatus 
        
        <span data-ttu-id="10c72-149">Verifique se todas as réplicas têm um valor de verdadeiro.</span><span class="sxs-lookup"><span data-stu-id="10c72-149">Check that all replicas have a value of True.</span></span>
    
      - <span data-ttu-id="10c72-150">Instale o serviço central de gerenciamento do servidor no restante dos servidores de front-end\_no pool de backup.</span><span class="sxs-lookup"><span data-stu-id="10c72-150">Install the Central Management Server service on the rest of the Front End Servers in Backup\_Pool.</span></span> <span data-ttu-id="10c72-151">Para fazer isso, execute o seguinte comando em todos os servidores de front-end, exceto o que você usou ao forçar o repositório de gerenciamento central a se mover anteriormente neste procedimento:</span><span class="sxs-lookup"><span data-stu-id="10c72-151">To do so, run the following command on all the Front End Servers, except the one you used when forcing the Central Management store move earlier in this procedure:</span></span>
        
            Bootstrapper /Setup 

7.  <span data-ttu-id="10c72-152">Reprovar os usuários do Pool1 para o Pool2 executando o seguinte cmdlet em uma janela do Shell de gerenciamento do Lync Server:</span><span class="sxs-lookup"><span data-stu-id="10c72-152">Fail over the users from Pool1 to Pool2 by running the following cmdlet in a Lync Server Management Shell window:</span></span>
    
        Invoke-CsPoolFailover -PoolFQDN <Pool1 FQDN> -DisasterMode -Verbose
    
    <span data-ttu-id="10c72-153">Como as etapas executadas nas partes anteriores deste procedimento para verificar o status do repositório de gerenciamento central não são universais, ainda há uma chance de que esse cmdlet falhe porque o repositório de gerenciamento central ainda não passou por failover completo.</span><span class="sxs-lookup"><span data-stu-id="10c72-153">Because the steps taken in the previous parts of this procedure to check the Central Management store status are not universal, there is still a chance this cmdlet will fail because the Central Management store is not yet fully failed over.</span></span> <span data-ttu-id="10c72-154">Nesse caso, você deve corrigir o repositório de gerenciamento central com base nas mensagens de erro que você vê e executar esse cmdlet novamente.</span><span class="sxs-lookup"><span data-stu-id="10c72-154">In this case, you must fix the Central Management store based on the error messages that you see, and then run this cmdlet again.</span></span>
    
    <span data-ttu-id="10c72-155">Se você vir a mensagem de erro a seguir, será necessário alterar o pool de bordas neste site para usar um pool diferente como próximo salto antes de falhar sobre o pool.</span><span class="sxs-lookup"><span data-stu-id="10c72-155">If you see the following error message, then you need to change the Edge pool at this site to use a different pool as its next hop before failing over the pool.</span></span> <span data-ttu-id="10c72-156">Para obter detalhes, consulte os procedimentos no início deste tópico.</span><span class="sxs-lookup"><span data-stu-id="10c72-156">For details, see the procedures at the beginning of this topic.</span></span>
    
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

