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
ms.openlocfilehash: 7de00de8361ac8bc5827fd76ea2486ae790a66d4
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42048014"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="failing-over-a-pool-in-lync-server-2013"></a>Failover de um pool no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2014-10-10_

Se um único pool de Front End falhar e for necessário fazer failover, use o procedimento a seguir. Neste procedimento, o Datacenter1 contém o Pool1, que falhou. Você fará failover no Pool2 localizado no Datacenter2.

A maior parte do trabalho do failover de pool envolve a falha do repositório de gerenciamento central, se for necessário. Isso é importante porque o repositório de gerenciamento central deve estar funcional quando os usuários do pool têm failover.

Além disso, se um pool de Front End falhar mas o pool de Borda no local ainda estiver em execução, você deve saber se o pool de Borda usa o pool com falha como pool do próximo salto. Se usar, você deve alterar o pool de Borda para usar um pool de Front End diferente antes de fazer o failover do pool de Front End com falha. Como a configuração do próximo salto será alterada dependerá de a Borda usar um pool no mesmo local do pool de Borda ou em um local diferente.

**Para definir um pool de Borda para usar um pool do próximo salto no mesmo local**

1.  Abra o construtor de topologias, clique com o botão direito do mouse no pool de borda que precisa ser alterado e clique em **Editar propriedades**.

2.  Clique em **Próximo Salto**. Na lista **Pool do próximo salto:**, selecione o pool que servirá como pool do próximo salto.

3.  Clique em **OK** e publique as alterações.

**Para definir um pool de Borda para usar um pool do próximo salto em um local diferente**

1.  Abra uma janela do Shell de gerenciamento do Lync Server e digite o seguinte cmdlet:
    
        Set-CsEdgeServer -Identity EdgeServer:<Edge Server pool FQDN> -Registrar Registrar:<NextHopPoolFQDN>

**Para fazer failover de um pool em um desastre**

1.  Encontre o pool do servidor de gerenciamento central digitando o seguinte cmdlet em um servidor front-end no Pool2:
    
        Invoke-CsManagementServerFailover -Whatif
    
    Os resultados deste cmdlet mostram qual pool atualmente hospeda o servidor de gerenciamento central. No restante deste procedimento, esse pool é conhecido como pool de CMS\_.

2.  Use o construtor de topologias para localizar a versão do Lync Server em\_execução no pool do CMS. Se ele estiver executando o Lync Server 2013, use o cmdlet a seguir para localizar o pool de backup do pool 1.
    
        Get-CsPoolBackupRelationship -PoolFQDN <CMS_Pool FQDN>
    
    Permite que\_o pool de backup seja o pool de backup.

3.  Verifique o status do repositório de gerenciamento central com o seguinte cmdlet:
    
        Get-CsManagementStoreReplicationStatus -CentralManagementStoreStatus 
    
    Este cmdlet deve mostrar que tanto ActiveMasterFQDN quanto ActiveFileTransferAgents estão apontando para o FQDN do pool\_CMS. Se eles estiverem vazios, o servidor de gerenciamento central não estará disponível e você deverá fazer o failover.

4.  Se o repositório de gerenciamento central não estiver disponível ou se o repositório de gerenciamento central estiver em execução no Pool1 (ou seja, o pool com falha), você deverá fazer failover do servidor de gerenciamento central antes de realizar o failover do pool. Se você precisar fazer failover do servidor de gerenciamento central hospedado em um pool executando o Lync Server 2013, use o cmdlet na etapa 5 deste procedimento. Se você precisar fazer failover do servidor de gerenciamento central hospedado em um pool executando o Lync Server 2010, use o cmdlet na etapa 6 deste procedimento. Se você não precisar fazer failover do servidor de gerenciamento central, pule para a etapa 7 deste procedimento.

5.  Para fazer failover do repositório de gerenciamento central em um pool executando o Lync Server 2013, faça o seguinte:
    
      - Primeiro, verifique o servidor back-end no\_pool de backup que executa a instância principal do repositório de gerenciamento central digitando o seguinte:
        
            Get-CsDatabaseMirrorState -DatabaseType Centralmgmt -PoolFqdn <Backup_Pool Fqdn>
    
      - Se o servidor back-end principal no\_pool de backup for o principal, digite:
        
            Invoke-CSManagementServerFailover -BackupSQLServerFqdn <Backup_Pool Primary BackEnd Server FQDN> -BackupSQLInstanceName <Backup_Pool Primary SQL Instance Name>
        
        Se o servidor de back-end de\_espelho no pool de backup for o principal, digite:
        
            Invoke-CSManagementServerFailover -MirrorSQLServerFqdn <Backup_Pool Mirror BackEnd Server FQDN> -MirrorSQLInstanceName <Backup_Pool Mirror SQL Instance Name>
    
      - Valide a conclusão do failover do servidor de gerenciamento central. Digite:
        
            Get-CsManagementStoreReplicationStatus -CentralManagementStoreStatus 
        
        Verifique se ActiveMasterFQDN e ActiveFileTransferAgents estão apontando para o FQDN do pool de\_backup.
    
      - Por fim, verifique o status da réplica para todos os servidores front-end digitando o seguinte:
        
            Get-CsManagementStoreReplicationStatus 
        
        Verifique se todas as réplicas possuem o valor Verdadeiro (True).
        
        Pule para a etapa 7 neste procedimento.

6.  Instale o repositório de gerenciamento central no servidor back-end do\_pool de backup.
    
      - Primeiro, execute o seguinte comando:
        
        ```PowerShell 
        Install-CsDatabase -CentralManagementDatabase -Clean -SqlServerFqdn <Backup_Pool Back End Server FQDN> -SqlInstanceName rtc  
        ```
    
      - Execute o próximo comando em um dos servidores de front-end do\_pool de backup para forçar a movimentação do repositório de gerenciamento central:
        
            Move-CsManagementServer -ConfigurationFileName c:\CsConfigurationFile.zip -LisConfigurationFileName c:\CsLisConfigurationFile.zip -Force 
    
      - Valide se a movimentação está concluída:
        
            Get-CsManagementStoreReplicationStatus -CentralManagementStoreStatus 
        
        Verifique se ActiveMasterFQDN e ActiveFileTransferAgents estão apontando para o FQDN do pool de\_backup.
    
      - Verifique o status da réplica para todos os servidores de Front End digitando:
        
            Get-CsManagementStoreReplicationStatus 
        
        Verifique se todas as réplicas possuem o valor Verdadeiro (True).
    
      - Instale o serviço do servidor de gerenciamento central no restante dos servidores de front-end\_no pool de backup. Para fazer isso, execute o seguinte comando em todos os servidores front-end, exceto aquele que você usou ao forçar a movimentação do repositório de gerenciamento central neste procedimento:
        
            Bootstrapper /Setup 

7.  Faça failover dos usuários do Pool1 para o Pool2 executando o seguinte cmdlet em uma janela do Shell de gerenciamento do Lync Server:
    
        Invoke-CsPoolFailover -PoolFQDN <Pool1 FQDN> -DisasterMode -Verbose
    
    Como as etapas executadas nas partes anteriores deste procedimento para verificar o status do repositório de gerenciamento central não são universais, ainda há uma chance de que esse cmdlet falhe porque o repositório de gerenciamento central ainda não foi completamente failover. Nesse caso, você deve corrigir o repositório de gerenciamento central com base nas mensagens de erro exibidas e executar esse cmdlet novamente.
    
    Se a mensagem de erro a seguir for apresentada, será necessário alterar o pool de Borda neste local para usar um pool diferente como próximo salto antes da fazer o failover do pool. Para detalhes, consulte os procedimentos no início deste tópico.
    
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

