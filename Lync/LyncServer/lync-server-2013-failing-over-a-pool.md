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

# <a name="failing-over-a-pool-in-lync-server-2013"></a>Fazendo failover de um pool no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2014-10-10_

Se um único pool de front-end tiver falhado e precisar de failover, use o procedimento a seguir. Neste procedimento, Datacenter1 contém Pool1, e Pool1 falhou. Você está falhando no Pool2 localizado no Datacenter2.

A maior parte do trabalho do failover de pool envolve a falha em relação ao repositório de gerenciamento central, se for necessário. Isso é importante porque o repositório de gerenciamento central deve ser funcional quando os usuários do pool tiverem failover.

Além disso, se um pool de front-ends falhar, mas o pool de bordas nesse site ainda estiver em execução, você deverá saber se o pool de bordas usa o pool com falha como um próximo pool de saltos. Em caso afirmativo, você deve alterar o pool de bordas para usar um pool de front-end diferente antes de falhar sobre o pool de front-ends com falha. A maneira como você altera a próxima configuração de salto depende se a borda usará um pool no mesmo site que o pool de bordas ou um site diferente.

**Para definir um pool de bordas para usar um próximo pool de saltos no mesmo site**

1.  Abra o construtor de topologias, clique com o botão direito do mouse no pool de bordas que precisa ser alterado e clique em **Editar propriedades**.

2.  Clique em **próximo salto**. Na lista **próximo pool de saltos:** , selecione o pool que agora funcionará como o próximo pool de saltos.

3.  Clique em **OK**e, em seguida, publique as alterações.

**Para definir um pool de bordas para usar um próximo pool de saltos em um site diferente**

1.  Abra uma janela do Shell de gerenciamento do Lync Server e digite o seguinte cmdlet:
    
        Set-CsEdgeServer -Identity EdgeServer:<Edge Server pool FQDN> -Registrar Registrar:<NextHopPoolFQDN>

**Para causar failover em um pool em um desastre**

1.  Localize o pool que é o host do servidor de gerenciamento central, digitando o cmdlet a seguir em um servidor front-end no Pool2:
    
        Invoke-CsManagementServerFailover -Whatif
    
    Os resultados deste cmdlet mostram qual pool atualmente hospeda o servidor central de gerenciamento. No restante deste procedimento, esse pool é conhecido como o pool de\_CMS.

2.  Use o construtor de topologias para localizar a versão do Lync Server em\_execução no pool de CMS. Se ele estiver executando o Lync Server 2013, use o cmdlet a seguir para localizar o pool de backup do pool 1.
    
        Get-CsPoolBackupRelationship -PoolFQDN <CMS_Pool FQDN>
    
    Permitir que\_o pool de backup seja o pool de backup.

3.  Verifique o status do repositório central de gerenciamento com o seguinte cmdlet:
    
        Get-CsManagementStoreReplicationStatus -CentralManagementStoreStatus 
    
    Este cmdlet deve mostrar que ambos ActiveMasterFQDN e ActiveFileTransferAgents estão apontando para o FQDN do pool\_de CMS. Se estiverem vazios, o servidor central de gerenciamento não está disponível e você deve fazer o failover.

4.  Se o repositório de gerenciamento central não estiver disponível ou se o repositório de gerenciamento central estiver em execução no Pool1 (ou seja, o pool com falha), você deverá fazer failover do servidor de gerenciamento central antes de falhar sobre o pool. Se você precisar fazer failover do servidor de gerenciamento central hospedado em um pool que executa o Lync Server 2013, use o cmdlet na etapa 5 deste procedimento. Se você precisar fazer failover do servidor de gerenciamento central hospedado em um pool que executa o Lync Server 2010, use o cmdlet na etapa 6 deste procedimento. Se você não precisar fazer failover do servidor de gerenciamento central, pule para a etapa 7 deste procedimento.

5.  Para fazer failover do repositório de gerenciamento central em um pool que executa o Lync Server 2013, faça o seguinte:
    
      - Primeiro, verifique qual servidor back-end no\_pool de backup executa a instância principal do repositório de gerenciamento central digitando o seguinte:
        
            Get-CsDatabaseMirrorState -DatabaseType Centralmgmt -PoolFqdn <Backup_Pool Fqdn>
    
      - Se o servidor back-end principal no\_pool de backup for o principal, digite:
        
            Invoke-CSManagementServerFailover -BackupSQLServerFqdn <Backup_Pool Primary BackEnd Server FQDN> -BackupSQLInstanceName <Backup_Pool Primary SQL Instance Name>
        
        Se o servidor de back-end do\_espelho no pool de backup for o principal, digite:
        
            Invoke-CSManagementServerFailover -MirrorSQLServerFqdn <Backup_Pool Mirror BackEnd Server FQDN> -MirrorSQLInstanceName <Backup_Pool Mirror SQL Instance Name>
    
      - Confirme se o failover do servidor de gerenciamento central está concluído. Digite o seguinte:
        
            Get-CsManagementStoreReplicationStatus -CentralManagementStoreStatus 
        
        Verifique se ambos ActiveMasterFQDN e ActiveFileTransferAgents estão apontando para o FQDN do pool\_de backup.
    
      - Por fim, verifique o status da réplica de todos os servidores de front-end digitando o seguinte:
        
            Get-CsManagementStoreReplicationStatus 
        
        Verifique se todas as réplicas têm um valor de verdadeiro.
        
        Pule para a etapa 7 deste procedimento.

6.  Instale o repositório de gerenciamento central no servidor back-end do\_pool de backup.
    
      - Primeiro, execute o seguinte comando:
        
        ``` 
        Install-CsDatabase -CentralManagementDatabase -Clean -SqlServerFqdn <Backup_Pool Back End Server FQDN> -SqlInstanceName rtc  
        ```
    
      - Execute o próximo comando em um dos servidores front-end do pool\_de backup para forçar a mudança do repositório de gerenciamento central:
        
            Move-CsManagementServer -ConfigurationFileName c:\CsConfigurationFile.zip -LisConfigurationFileName c:\CsLisConfigurationFile.zip -Force 
    
      - Validar conclusão da mudança:
        
            Get-CsManagementStoreReplicationStatus -CentralManagementStoreStatus 
        
        Verifique se ambos ActiveMasterFQDN e ActiveFileTransferAgents estão apontando para o FQDN do pool\_de backup.
    
      - Verifique o status da réplica de todos os servidores de front-end digitando o seguinte:
        
            Get-CsManagementStoreReplicationStatus 
        
        Verifique se todas as réplicas têm um valor de verdadeiro.
    
      - Instale o serviço central de gerenciamento do servidor no restante dos servidores de front-end\_no pool de backup. Para fazer isso, execute o seguinte comando em todos os servidores de front-end, exceto o que você usou ao forçar o repositório de gerenciamento central a se mover anteriormente neste procedimento:
        
            Bootstrapper /Setup 

7.  Reprovar os usuários do Pool1 para o Pool2 executando o seguinte cmdlet em uma janela do Shell de gerenciamento do Lync Server:
    
        Invoke-CsPoolFailover -PoolFQDN <Pool1 FQDN> -DisasterMode -Verbose
    
    Como as etapas executadas nas partes anteriores deste procedimento para verificar o status do repositório de gerenciamento central não são universais, ainda há uma chance de que esse cmdlet falhe porque o repositório de gerenciamento central ainda não passou por failover completo. Nesse caso, você deve corrigir o repositório de gerenciamento central com base nas mensagens de erro que você vê e executar esse cmdlet novamente.
    
    Se você vir a mensagem de erro a seguir, será necessário alterar o pool de bordas neste site para usar um pool diferente como próximo salto antes de falhar sobre o pool. Para obter detalhes, consulte os procedimentos no início deste tópico.
    
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

