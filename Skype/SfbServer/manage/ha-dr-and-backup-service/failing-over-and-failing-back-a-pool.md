---
title: Havendo falha e havendo falha em um pool
ms.reviewer: ''
author: lanachin
ms.author: v-lanac
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: .
ms.openlocfilehash: a51c17e1f7b58e901c943ad8e8e8b9312bad9f74
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "33903359"
---
# <a name="failing-over-and-failing-back-a-pool-in-skype-for-business-server"></a>Com falha over e com falha de volta um pool no Skype para Business Server 

Use os procedimentos a seguir se um único pool de Front-End falhou e precisa ser feito um failover, ou o pool que passou por desastre é online novamente e você precisa restaurar sua implantação ao status funcional normal. Também Saiba como realizar failover e failback do pool de borda usado para Skype para federação de negócios ou federação XMPP ou altere o pool de borda associado a um pool de Front-End.

- [Failover de um pool de Front-End](#fail-over-a-front-end-pool)
- [Failback um pool](#fail-back-a-pool)
- [Failover de pool de borda usado para Skype para federação do servidor de negócios](#fail-over-the-edge-pool-used-for-skype-for-business-server-federation)
- [Failover de pool de borda usado para federação de XMPP no Skype para Business Server](#fail-over-the-edge-pool-used-for-xmpp-federation-in-skype-for-business-server)
- [Failback do pool de borda usado para Skype para federação Business Server ou XMPP](#fail-back-the-edge-pool-used-for-skype-for-business-server-federation-or-xmpp-federation)
- [Alterar o pool de borda associado a um pool de Front-End](#change-the-edge-pool-associated-with-a-front-end-pool)

## <a name="fail-over-a-front-end-pool"></a>Failover de um pool de Front-End

Neste procedimento, Datacenter1 contém Pool1 e Pool1 falhou. Você estiver realizando failover para o Pool2, localizado em Datacenter2.

A maioria do trabalho para o pool de failover envolve o failover do repositório de gerenciamento Central, se for necessário. Isso é importante porque o repositório de gerenciamento Central deve ser funcional quando os usuários do pool são realizou um failover.

Além disso, se um pool de Front-End falha, mas ainda está em execução no pool de borda nesse site, você deve saber se o pool de borda usa o pool que falhou como um pool de próximo salto. Em caso afirmativo, você deverá alterar o pool de borda para usar um pool de Front-End diferente antes de falhar sobre o pool de Front-End com falha. Como você pode alterar a próxima configuração de salto depende se a borda usará um pool no mesmo site que o pool de borda ou um site diferente.

**Para definir um pool de borda para usar um pool de próximo salto no mesmo site**

1.  Abra o construtor de topologia, clique com o botão o pool de borda que precisa ser alterado e clique em **Editar propriedades**.

2.  Clique em **próximo salto**. Da **pool de próximo salto:** lista, selecione o pool que agora servirá como o pool de próximo salto.

3.  Clique em **Okey**e publique as alterações.

**Para definir um pool de borda para usar um pool de próximo salto em um local diferente**

1.  Abra um Skype para a janela do Shell de gerenciamento do servidor de negócios e digite o seguinte cmdlet:
    
        Set-CsEdgeServer -Identity EdgeServer:<Edge Server pool FQDN> -Registrar Registrar:<NextHopPoolFQDN>

**Failover de um pool em um desastre**

1.  Localize qual pool é o host para o servidor de gerenciamento Central, digitando o seguinte cmdlet em um servidor Front-End Pool2:
    
        Invoke-CsManagementServerFailover -Whatif
    
    Os resultados de mostrar este cmdlet que qual pool atualmente hospeda o servidor de gerenciamento Central. No restante desse procedimento, este pool é conhecido como CMS\_Pool.

2.  Use o construtor de topologias para encontrar a versão do Skype para Business Server em execução no CMS\_Pool. Se ele estiver em execução Skype para Business Server, use o seguinte cmdlet para encontrar o pool de backup do Pool 1.
    
        Get-CsPoolBackupRelationship -PoolFQDN <CMS_Pool FQDN>
    
    Permitir que o Backup\_Pool ser o pool de backup.

3.  Verificar o status do repositório de gerenciamento Central com o seguinte cmdlet:
    
        Get-CsManagementStoreReplicationStatus -CentralManagementStoreStatus 
    
    Este cmdlet deve mostrar que ActiveMasterFQDN e activefiletransferagents, está apontando para o FQDN do CMS\_Pool. Se eles estiverem vazios, o servidor de gerenciamento Central não está disponível e ele deve ser realizar failover.

4.  Se o repositório de gerenciamento Central não estiver disponível ou se o repositório de gerenciamento Central estava sendo executada no Pool1 (ou seja, o pool que falhou), você deve fazer o failover do servidor de gerenciamento Central antes de falhar sobre o pool. Se você precisar realizar failover do servidor de gerenciamento Central que foi hospedado em um pool executando o Skype para Business Server, use o cmdlet na etapa 5 deste procedimento. Se você não precisará realizar failover do servidor de gerenciamento Central, pule para a etapa 7 deste procedimento.

5.  Para fazer failover repositório de gerenciamento Central em um pool executando Skype para Business Server, faça o seguinte:
    
      - Primeiro, verifique qual servidor Back-End no Backup\_Pool executa a instância principal do repositório de gerenciamento Central, digitando o seguinte:
        
            Get-CsDatabaseMirrorState -DatabaseType Centralmgmt -PoolFqdn <Backup_Pool Fqdn>
    
      - Se o principal servidor Back-End no Backup\_Pool é o tipo de entidade,:
        
            Invoke-CSManagementServerFailover -BackupSQLServerFqdn <Backup_Pool Primary BackEnd Server FQDN> -BackupSQLInstanceName <Backup_Pool Primary SQL Instance Name>
        
        Se o servidor Back-End no Backup do espelho\_Pool é o tipo de entidade,:
        
            Invoke-CSManagementServerFailover -MirrorSQLServerFqdn <Backup_Pool Mirror BackEnd Server FQDN> -MirrorSQLInstanceName <Backup_Pool Mirror SQL Instance Name>
    
      - Valide que o failover do servidor de gerenciamento Central está concluído. Digite o seguinte:
        
            Get-CsManagementStoreReplicationStatus -CentralManagementStoreStatus 
        
        Verifique se ambos, ActiveMasterFQDN e ActiveFileTransferAgents estão apontando para o FQDN do Backup\_Pool.
    
      - Finalmente, verifique o status da réplica para todos os servidores Front-End digitando o seguinte:
        
            Get-CsManagementStoreReplicationStatus 
        
        Verifique se todas as réplicas tem um valor True.
        
        Vá para a etapa 7 neste procedimento.

6.  Instalar o repositório de gerenciamento Central em Back End Server de Backup\_Pool.
    
      - Primeiro, execute o seguinte comando:
        
        ``` 
        Install-CsDatabase -CentralManagementDatabase -Clean -SqlServerFqdn <Backup_Pool Back End Server FQDN> -SqlInstanceName rtc  
        ```
    
      - Execute o seguinte comando em um dos Front End servidores de Backup\_Pool para forçar a movimentação do repositório de gerenciamento Central:
        
            Move-CsManagementServer -ConfigurationFileName c:\CsConfigurationFile.zip -LisConfigurationFileName c:\CsLisConfigurationFile.zip -Force 
    
      - Validar a movimentação está concluída:
        
            Get-CsManagementStoreReplicationStatus -CentralManagementStoreStatus 
        
        Verifique se ambos, ActiveMasterFQDN e ActiveFileTransferAgents estão apontando para o FQDN do Backup\_Pool.
    
      - Verifique o status da réplica para todos os servidores Front-End digitando o seguinte:
        
            Get-CsManagementStoreReplicationStatus 
        
        Verifique se todas as réplicas tem um valor True.
    
      - Instale o serviço do servidor de gerenciamento Central no restante dos servidores Front-End no Backup\_Pool. Para fazer isso, execute o seguinte comando em todos os servidores Front-End, exceto a que você usou quando forçando Gerenciamento Central repositório mover anteriormente neste procedimento:
        
            Bootstrapper /Setup 

7.  Failover dos usuários do Pool1 para o Pool2 executando o seguinte cmdlet em um Skype para a janela do Shell de gerenciamento do servidor de negócios:
    
        Invoke-CsPoolFailover -PoolFQDN <Pool1 FQDN> -DisasterMode -Verbose
    
    Como as etapas executadas na lista partes anteriores deste procedimento para verificar o status do repositório de gerenciamento Central não são universais, ainda há uma chance que esse cmdlet irá falhar porque o repositório de gerenciamento Central não ainda totalmente realizou um failover. Nesse caso, você deve corrigir o repositório de gerenciamento Central com base em mensagens de erro que você vê e, em seguida, executar esse cmdlet novamente.
    
    Se você vir a seguinte mensagem de erro, você precisará alterar o pool de borda neste site para usar um pool diferente como seu próximo salto antes de falhar sobre o pool. Para obter detalhes, consulte os procedimentos no início deste tópico.
    
        Invoke-CsPoolFailOver : This Front-end pool "pool1.contoso.com" is specified in
        topology as the next hop for the Edge server. Failing over this pool may cause External
        access/Federation/Split-domain/XMPP features to stop working. Please use Topology Builder to
        change the Edge internal next hop setting to point to a different Front-end pool,  before you
        proceed.


## <a name="fail-back-a-pool"></a>Failback um pool

Após o pool que passou por desastre voltar a ficar online (ou seja, o Pool1 neste exemplo), siga estas etapas para restaurar sua implantação para o status funcional normal.

Observe que o processo de failback leva vários minutos para ser concluída.Para referência, a expectativa é de até 60 minutos para um pool de 20.000 usuários.

Failback dos usuários que estavam originalmente hospedados no Pool1 e foi feitos failover para o Pool2, digitando o seguinte cmdlet:
    
    Invoke-CsPoolFailback -PoolFQDN <Pool1 FQDN> -Verbose

Não há outras etapas são necessárias. Se o failover do servidor de gerenciamento Central, você pode deixá-lo no Pool2.

## <a name="fail-over-the-edge-pool-used-for-skype-for-business-server-federation"></a>Failover de pool de borda usado para Skype para federação do servidor de negócios 

Se o pool de borda onde você tinha Skype para federação Business Server configurada ficar inativo, você deve alterar a federação para usar um pool de borda diferente para federação para funcionar.

1.  Em um servidor Front-End, abra o construtor de topologia. Expanda **pools de borda**e clique com o servidor de borda ou pool de servidores de borda que está configurado atualmente para federação. Selecione **Editar propriedades**.

2.  Em **Editar propriedades** , em **Geral**, desmarque **Habilitar federação para este pool de borda (porta 5061)**. Clique em **OK**.

3.  Expanda **pools de borda**e clique com o servidor de borda ou pool de servidores de borda que você deseja usar para federação agora. Selecione **Editar propriedades**.

4.  Em **Editar propriedades** , em **Geral**, selecione **Habilitar federação para este pool de borda (porta 5061)**. Clique em **OK**.

5.  Clique em **ação**, selecione a **topologia**, selecione **Publicar**. Quando solicitado em **publicar a topologia**, clique em **Avançar**. Quando a publicação for concluída, clique em **Concluir**.

6.  No servidor de borda, abra o Skype para o Assistente de implantação de servidor de negócios. Clique em **instalar ou Skype de atualização para o sistema de servidor de negócios**e, em seguida, clique em **instalar ou remover Skype para componentes de servidor de negócios**. Clique em **executar novamente**.

7.  Click **Next**. A tela Resumo mostrará ações como são executadas. Depois que a implantação for concluída, clique em **Exibir Log** para exibir arquivos de log disponíveis. Clique em **Concluir** para concluir a implantação.
    
    Se o site que contém o pool de borda com falha contiver servidores Front-End que ainda estão em execução, você deve atualizar o serviço de webconferência e A / V a serviço de conferência nesses pools de Front-End para usar um pool de borda em um controle remoto ou seja site running ainda. 

 ## <a name="fail-over-the-edge-pool-used-for-xmpp-federation-in-skype-for-business-server"></a>Failover de pool de borda usado para federação de XMPP no Skype para Business Server 

Em sua organização, há um pool de borda designado como o pool a ser usado para federação XMPP. Se esse pool ficar inativo, você deve realizar failover federação XMPP para usar um pool de borda diferente antes de Federação XMPP possa trabalhar novamente.

Quando você primeiro instala pools de borda e habilitar a federação XMPP, você pode simplificar o processo de recuperação de desastres, configurando os registros de SRV de DNS externos para todos os pools de borda para federação XMPP, em vez de apenas um deles. Cada um desses registros SRV deve ter uma prioridade diferente definida. Todo o tráfego de Federação XMPP passa o pool com o registro SRV com a prioridade mais alta. 

No procedimento a seguir, EdgePool1 é o pool que originalmente hospedada federação XMPP e EdgePool2 é o pool que irá hospedar agora a federação XMPP.


### <a name="to-fail-over-the-edge-pool-used-for-xmpp-federation"></a>Para realizar failover do pool de borda usado para federação XMPP

1.  Se você ainda não tiver outro pool de borda implantado (além aquele que está atualmente desativado), implante desse pool. 

2.  Em cada servidor de borda no novo pool de borda irá agora hospedar federação XMPP (EdgePool2), execute o seguinte cmdlet:
    
        Stop-CsWindowsService

3.  Execute o seguinte cmdlet para reapontar a rota de Federação XMPP para o EdgePool2:
    
        Set-CsSite Site2 -XmppExternalFederationRoute EdgeServer2.contoso.com
    
    Neste exemplo, Site2 é o site que contém o pool de borda que irá hospedar agora a rota de Federação XMPP e Edgeserver2 é o FQDN de um servidor de borda nesse pool.

4.  No servidor DNS externo, altere o registro de DNS A para federação XMPP apontar para o Edgeserver2.

5.  Se você ainda não tiver um registro SRV de DNS para federação XMPP que resolve para o pool de borda irá agora hospedar federação XMPP, você deve adicioná-lo, como no exemplo a seguir. Esse registro SRV deve ter um valor de porta de 5269.
    
        _xmpp-server._tcp.contoso.com

6.  Verifique se o pool de borda irá agora hospedar federação XMPP com porta 5269 aberta externamente.

7.  Inicie os serviços em todos os servidores de borda no pool de borda irá agora hospedar federação XMPP:
    
        Start-CsWindowsService


## <a name="fail-back-the-edge-pool-used-for-skype-for-business-server-federation-or-xmpp-federation"></a>Failback do pool de borda usado para Skype para federação Business Server ou XMPP 

Após uma falha borda pool usado para federação de host foi colocado novamente online, use este procedimento para realizar o fail back do Skype para a rota de Federação do servidor de negócios e/ou a rota de Federação XMPP para usar novamente este pool de borda restaurado.

1.  No pool de borda que está agora disponível novamente, inicie os serviços de borda.

2.  Se você deseja realizar o fail back do Skype para a rota de Federação Business Server para usar o servidor de borda restaurado, faça o seguinte:
    
      - Em um servidor Front-End, abra o construtor de topologia. Expanda **pools de borda**, e em seguida, clique com botão direito do servidor de borda ou pool de servidores de borda que está configurado atualmente para federação. Selecione **Editar propriedades**.
    
      - Em **Editar propriedades** , em **Geral**, desmarque **Habilitar federação para este pool de borda (porta 5061)**. Clique em **OK**.
    
      - Expanda **pools de borda**, e em seguida, clique com botão direito original servidor de borda ou pool de servidores de borda que você deseja usar para federação novamente. Selecione **Editar propriedades**.
    
      - Em **Editar propriedades** , em **Geral**, selecione **Habilitar federação para este pool de borda (porta 5061)**. Clique em **OK**.
    
      - Clique em **ação**, selecione a **topologia**, selecione **Publicar**. Quando solicitado em **publicar a topologia**, clique em **Avançar**. Quando a publicação for concluída, clique em **Concluir**.
    
      - No servidor de borda, abra o Skype para o Assistente de implantação de servidor de negócios. Clique em **instalar ou Skype de atualização para o sistema de servidor de negócios**, clique em **instalar ou remover Skype para componentes de servidor de negócios**. Clique em **executar novamente**.
    
      - Click **Next**. A tela Resumo mostrará ações como são executadas. Depois que a implantação for concluída, clique em **Exibir Log** para exibir arquivos de log disponíveis. Clique em **Concluir** para concluir a implantação.

3.  Se você deseja realizar o fail back da rota de Federação XMPP para usar o servidor de borda restaurado, faça o seguinte:
    
      - Execute o seguinte cmdlet para reapontar a rota de Federação XMPP para o pool de borda irá agora hospedar federação XMPP (neste exemplo, EdgeServer1):
        
            Set-CsSite Site1 -XmppExternalFederationRoute EdgeServer1.contoso.com
        
        Neste exemplo, Site1 é o site que contém o pool de borda que irá hospedar agora a rota de Federação XMPP e EdgeServer1.contoso.com é o FQDN de um servidor de borda nesse pool.
    
      - Se você ainda não tiver um registro SRV de DNS para federação XMPP que resolve para o pool de borda irá agora hospedar federação XMPP, você deve adicioná-lo, como no exemplo a seguir. Esse registro SRV deve ter um valor de porta de 5269.
        
            _xmpp-server._tcp.contoso.com
    
      - No servidor DNS externo, altere o registro de DNS A para federação XMPP apontar para o Edgeserver2.
    
      - Verifique se o pool de borda irá agora hospedar federação XMPP com porta 5269 aberta externamente.

4.  Se os pools de Front-End permanecem em execução no site que contém o pool de borda que falharam e foi restaurado, você deverá atualizar o serviço de webconferência e A / V de serviço de conferência nesses Front-End pools para usar novamente os pools de borda em seu site local.

5.  Se o pool de Front-End no mesmo local que o pool de borda com falha também falhou, agora você pode usar Invoke – CsPoolFailback para o failback do pool Front-End.


## <a name="change-the-edge-pool-associated-with-a-front-end-pool"></a>Alterar o pool de borda associado a um pool de Front-End

Se um pool de borda cair, mas o pool de Front-End no mesmo site ainda está em execução, você precisará definir o pool de Front-End para usar um pool de borda em um local diferente, até que o pool de borda com falha é restaurado.

1.  No construtor de topologias, navegue até o nome do pool de Front-End, que você precisa alterar.

2.  Com o botão direito do pool e, em seguida, clique em **Editar propriedades**.

3.  Na seção **associações** , em **Associar Pool de borda (para componentes de mídia)**, use a caixa suspensa para selecionar o pool de borda que você deseja associar a esse pool de Front-End com.

4.  Clique em **OK**.
