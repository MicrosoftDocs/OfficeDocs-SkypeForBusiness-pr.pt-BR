---
title: Failover e Failback em um pool
ms.reviewer: ''
author: SerdarSoysal
ms.author: serdars
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
description: .
ms.openlocfilehash: 0b1f79ff40584c82d6da603ede49004f3c0c8968
ms.sourcegitcommit: 296862e02b548f0212c9c70504e65b467d459cc3
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/25/2022
ms.locfileid: "65675033"
---
# <a name="failing-over-and-failing-back-a-pool-in-skype-for-business-server"></a>Failover e failback de um pool no Skype for Business Server

Use os procedimentos a seguir se um único pool de Front-End tiver falhado e precisar de failover ou se o pool que sofreu o desastre estiver online novamente e você precisar restaurar sua implantação para o status de trabalho regular. Saiba como fazer failover e fazer failback do pool de borda usado para federação Skype for Business ou federação XMPP ou alterar o pool de borda associado a um pool Front-End usuário.

- [Fazer failover de um pool de Front-Ends](#fail-over-a-front-end-pool)
- [Fazer failback de um pool](#fail-back-a-pool)
- [Fazer failover do pool de borda usado para Skype for Business Server federação](#fail-over-the-edge-pool-used-for-skype-for-business-server-federation)
- [Fazer failover do pool de borda usado para federação XMPP no Skype for Business Server](#fail-over-the-edge-pool-used-for-xmpp-federation-in-skype-for-business-server)
- [Fazer failback do pool de borda usado para Skype for Business Server federação ou federação XMPP](#fail-back-the-edge-pool-used-for-skype-for-business-server-federation-or-xmpp-federation)
- [Alterar o pool de borda associado a um pool de Front-Ends](#change-the-edge-pool-associated-with-a-front-end-pool)

## <a name="fail-over-a-front-end-pool"></a>Fazer failover de Front-End pool

O Datacenter1 contém Pool1 e o Pool1 falhou. Você está fazendo failover para o Pool2 localizado no Datacenter2.

A maior parte do trabalho para o failover do pool envolve o failover do repositório de Gerenciamento Central, se necessário. O repositório de Gerenciamento Central deve estar funcional quando os usuários do pool forem executados com failover.

Se um pool de Front-End falhar, mas o pool de Borda nesse site ainda estiver em execução, você deverá saber se o pool de borda usa o pool com falha como um pool de próximo salto. Se isso ocorrer, você deverá alterar o pool de borda para usar um pool de Front-End diferente antes de fazer failover do pool de Front-End falha. Como a configuração do próximo salto será alterada dependerá de a Borda usar um pool no mesmo local do pool de Borda ou em um local diferente.

**Para definir um pool de borda para usar um pool de próximo salto no mesmo site**

1. Abra o Construtor de Topologias, clique com o botão direito do mouse no pool de Borda que precisa ser alterado e selecione **Editar Propriedades**.

2. Selecione **Próximo Salto**. No pool **do próximo salto:** lista, selecione o pool que agora servirá como o pool do próximo salto.

3. Selecione **OK** e publique as alterações.

**Para definir um pool de borda para usar um pool de próximo salto em um site diferente**

1. Abra uma Skype for Business Server do Shell de Gerenciamento e digite o seguinte cmdlet:

    ```powershell
    Set-CsEdgeServer -Identity EdgeServer:<Edge Server pool FQDN> -Registrar Registrar:<NextHopPoolFQDN>
    ```

**Para fazer failover de um pool em um desastre**

1. Localize o pool de host para o Servidor de Gerenciamento Central digitando o seguinte cmdlet em um servidor Front-End no Pool2:

    ```powershell
    Invoke-CsManagementServerFailover -Whatif
    ```

    Os resultados desse cmdlet mostram qual pool atualmente hospeda o Servidor de Gerenciamento Central. No restante deste procedimento, esse pool é conhecido como Pool de CMS\_.

2. Use o Construtor de Topologias para localizar a versão Skype for Business Server em execução no Pool de CMS\_. Se ele estiver executando Skype for Business Server, use o cmdlet a seguir para localizar o pool de backup do Pool 1.

    ```powershell
    Get-CsPoolBackupRelationship -PoolFQDN <CMS_Pool FQDN>
    ```

    Deixe Backup\_ o pool de backup.

3. Verifique o status do repositório de Gerenciamento Central com o seguinte cmdlet:

    ```powershell
    Get-CsManagementStoreReplicationStatus -CentralManagementStoreStatus
    ```

    Esse cmdlet deve mostrar que ActiveMasterFQDN e ActiveFileTransferAgents estão apontando para o FQDN do Pool de CMS\_. Se eles estiverem vazios, o Servidor de Gerenciamento Central não estará disponível e você deverá fazer failover.

4.  Se o repositório de Gerenciamento Central não estiver disponível ou se o repositório de Gerenciamento Central estiver em execução no Pool1 (ou seja, o pool que falhou), você deverá fazer failover do Servidor de Gerenciamento Central antes de fazer failover do pool. Se você precisar fazer failover do Servidor de Gerenciamento Central que foi hospedado em um pool executando Skype for Business Server, use o cmdlet na etapa 5 deste procedimento. Se você não precisar fazer failover do Servidor de Gerenciamento Central, vá para a etapa 7 deste procedimento.

5.  Para fazer failover do repositório de Gerenciamento Central em um pool Skype for Business Server, faça o seguinte:

    1. Primeiro, verifique qual Back-End Server no Backup\_ Pool executa a instância principal do repositório de Gerenciamento Central digitando o seguinte:

        ```powershell
        Get-CsDatabaseMirrorState -DatabaseType Centralmgmt -PoolFqdn <Backup_Pool Fqdn>
        ```
    
    1. Se o servidor Back-End primário no Backup\_ Pool for a entidade de segurança, digite:

        ```powershell        
        Invoke-CSManagementServerFailover -BackupSQLServerFqdn <Backup_Pool Primary BackEnd Server FQDN> -BackupSQLInstanceName <Backup_Pool Primary SQL Instance Name>
        ```
        
    1. Se o servidor Back-End espelho no Backup\_ Pool for a entidade de segurança, digite:
    
        ```powershell
        Invoke-CSManagementServerFailover -MirrorSQLServerFqdn <Backup_Pool Mirror BackEnd Server FQDN> -MirrorSQLInstanceName <Backup_Pool Mirror SQL Instance Name>
        ```
    
    1. Valide se o failover do Servidor de Gerenciamento Central foi concluído. Digite o seguinte comando:
    
        ```powershell    
        Get-CsManagementStoreReplicationStatus -CentralManagementStoreStatus
        ```
        
        Verifique se ActiveMasterFQDN e ActiveFileTransferAgents estão apontando para o FQDN do Backup\_ Pool.
    
    1. Por fim, verifique o status da réplica para todos os Front-End Servidores digitando o seguinte:
        
        ```powershell
        Get-CsManagementStoreReplicationStatus 
        ```
        
        Verifique se todas as réplicas possuem o valor Verdadeiro (True).
        
        Pule para a etapa 7 neste procedimento.

6.  Instale o repositório de Gerenciamento Central no Servidor Back-End do Backup\_ Pool.
    
    1. Primeiro, execute o seguinte comando:

        ```powershell
        Install-CsDatabase -CentralManagementDatabase -Clean -SqlServerFqdn <Backup_Pool Back End Server FQDN> -SqlInstanceName rtc  
        ```
    
    1. Execute o próximo comando em um dos Servidores Front-End do Backup\_ Pool para forçar a movimentação do repositório de Gerenciamento Central:

        ```powershell
        Move-CsManagementServer -ConfigurationFileName c:\CsConfigurationFile.zip -LisConfigurationFileName c:\CsLisConfigurationFile.zip -Force
        ```
    
    1. Valide se a movimentação está concluída:

        ```powershell
        Get-CsManagementStoreReplicationStatus -CentralManagementStoreStatus
        ```
        
        Verifique se ActiveMasterFQDN e ActiveFileTransferAgents estão apontando para o FQDN do Backup\_ Pool.
    
    1. Verifique o status da réplica para todos os servidores de Front End digitando:

        ```powershell
        Get-CsManagementStoreReplicationStatus
        ```
        
        Verifique se todas as réplicas possuem o valor Verdadeiro (True).
    
    1. Instale o serviço Servidor de Gerenciamento Central no restante dos Servidores Front-End no Backup\_ Pool. Para fazer isso, execute o seguinte comando em todos os Servidores Front-End, exceto aquele que você usou ao forçar a movimentação do repositório de Gerenciamento Central anteriormente neste procedimento:

        ```console
        Bootstrapper /Setup
        ```

7.  Faça failover dos usuários do Pool1 para o Pool2 executando o seguinte cmdlet em uma janela Skype for Business Server Shell de Gerenciamento:

    ```powershell
    Invoke-CsPoolFailover -PoolFQDN <Pool1 FQDN> -DisasterMode -Verbose
    ```
    
    Como as etapas executadas nas partes anteriores deste procedimento para verificar o status do repositório de Gerenciamento Central não são universais, ainda há uma chance de que esse cmdlet falhe porque o repositório de Gerenciamento Central ainda não está totalmente com failover. Nesse caso, você deve corrigir o repositório de Gerenciamento Central com base nas mensagens de erro que você vê e, em seguida, executar esse cmdlet novamente.
    
    Se a mensagem de erro a seguir for apresentada, será necessário alterar o pool de Borda neste local para usar um pool diferente como próximo salto antes da fazer o failover do pool. Para detalhes, consulte os procedimentos no início deste tópico.
    
    ```console
    Invoke-CsPoolFailOver : This Front-end pool "pool1.contoso.com" is specified in
    topology as the next hop for the Edge server. Failing over this pool may cause External
    access/Federation/Split-domain/XMPP features to stop working. Please use Topology Builder to
    change the Edge internal next hop setting to point to a different Front-end pool,  before you
    proceed.
    ```


## <a name="fail-back-a-pool"></a>Fazer failback de um pool

Depois que o pool que passou por desastre voltar a ficar online (ou seja, o Pool1 neste exemplo), execute as etapas a seguir para restaurar sua implantação para o status funcional normal.

O processo de failback leva vários minutos para ser concluído. Para referência, espera-se que leve até 60 minutos para um pool de 20.000 usuários.

Para fazer failback dos usuários que estavam originalmente hospedados no Pool1 e dos quais foi feito failover para o Pool2, digite o seguinte cmdlet:

```powershell
Invoke-CsPoolFailback -PoolFQDN <Pool1 FQDN> -Verbose
```

Nenhuma outra etapa é necessária. Se você tiver falhado no Servidor de Gerenciamento Central, poderá deixá-lo no Pool2.

## <a name="fail-over-the-edge-pool-used-for-skype-for-business-server-federation"></a>Fazer failover do pool de borda usado para Skype for Business Server federação 

Se o pool de Borda em que Skype for Business Server federação configurada falhar, você deverá alterar a federação para usar um pool de Borda diferente para que a federação funcione.

1.  No servidor de front-end, abra o Construtor de Topologia. **Expanda pools de borda** e clique com o botão direito do mouse no servidor de Borda ou no pool de servidores de Borda que está configurado atualmente para Federação. Selecione **Editar propriedades**.

2.  Em **Editar propriedades**, em **Geral**, desmarque **Habilitar federação para este pool de Borda (Porta 5061)**. Selecione **OK**.

3.  **Expanda pools de borda** e clique com o botão direito do mouse no servidor de Borda ou no pool de servidores de Borda que você deseja usar para Federação. Selecione **Editar propriedades**.

4.  Em **Editar propriedades**, em **Geral**, selecione **Habilitar federação para este pool de Borda (Porta 5061)**. Selecione **OK**.

5.  Selecione **Ação**, **Topologia****, Publicar.** Quando solicitado a publicar **a topologia**, selecione **Avançar**. Quando a publicação for concluída, selecione **Concluir**.

6.  No servidor de Borda, abra o assistente Skype for Business Server Implantação. Selecione **Instalar ou Atualizar Skype for Business Server e**, em seguida, selecione **Configurar ou Remover Skype for Business Server Componentes**. Selecione **Executar Novamente**.

7.  Selecione **Avançar**. A tela de resumo mostrará ações conforme são executadas. Depois que a implantação for concluída, selecione **Exibir Log** para exibir os arquivos de log disponíveis. Selecione **Concluir** para concluir a implantação.
    
    Se o site que contém o pool de Borda com falha contiver Servidores Front-End que ainda estão em execução, você deverá atualizar o Serviço de WebConferência e o Serviço de Conferência A/V nesses pools de Front-End para usar um pool de Borda em um site remoto que ainda está em execução. 

 ## <a name="fail-over-the-edge-pool-used-for-xmpp-federation-in-skype-for-business-server"></a>Fazer failover do pool de borda usado para federação XMPP no Skype for Business Server 

Na sua organização, há um pool de borda designado como o pool para uso da federação XMPP. Se esse pool parar de funcionar, você deve transferir a federação XMPP para usar um pool de borda diferente antes da federação XMPP poder funcionar novamente.

Quando você instala pools de borda e habilita a Federação XMPP, é possível simplificar o processo de recuperação de desastres configurando a criação de registros do servidor DNS externos para todos os seus pools de Borda para a federação XMPP, em vez de apenas um. Cada um destes registros SRV devem ter um conjunto de prioridade diferente. Todo o tráfego da federação XMPP atravessa o pool com o registro SRV com a mais alta prioridade. 

No procedimento a seguir, EdgePool1 é o pool, que hospeda a federação XMPP originalmente, e EdgePool2 é o pool que agora hospedará a federação XMPP.
### <a name="to-fail-over-the-edge-pool-used-for-xmpp-federation"></a>Para fazer failover do pool de borda usado para federação XMPP

1.  Se você ainda não tiver outro pool de Borda implantado (além daquele que está inativo no momento), implante esse pool. 

2.  Em cada Servidor de Borda no novo pool de borda no qual a federação XMPP estará hospedada no momento (EdgePool2), execute o seguinte cmdlet:

    ```powershell
    Stop-CsWindowsService
    ```

3.  Execute o seguinte cmdlet para redirecionar a rota da federação XMPP para o EdgePool2:

    ```powershell
    Set-CsSite Site2 -XmppExternalFederationRoute EdgeServer2.contoso.com
    ```
    
    Neste exemplo, o Site2 é o site contendo o pool de borda no qual a rota da federação XMPP estará hospedada no momento e o EdgeServer2.contoso.com é o FQDN de um Servidor de Borda nesse pool.

4.  No servidor DNS externo, altere o registro A de DNS da federação XMPP para apontar para o EdgeServer2.contoso.com.

5.  Se você ainda não tiver um registro DNS SRV para a federação XMPP que resolva o pool de borda no qual a federação XMPP estará hospedada no momento, é necessário adicioná-lo, conforme no exemplo a seguir. O registro SRV deve ter um valor de porta de 5269.

    ```console
    _xmpp-server._tcp.contoso.com
    ```

6.  Verifique se o pool de borda no qual a federação XMPP estará hospedada no momento possui uma porta 5269 aberta externamente.

7.  Inicie os serviços em todos os Servidores de Borda no pool de borda no qual a federação XMPP estará hospedada no momento:

    ```powershell
    Start-CsWindowsService
    ```

## <a name="fail-back-the-edge-pool-used-for-skype-for-business-server-federation-or-xmpp-federation"></a>Fazer failback do pool de borda usado para Skype for Business Server federação ou federação XMPP 

Depois que um pool de borda com falha que costumava hospedar a federação tiver sido colocado online novamente, use este procedimento para fazer failback da rota de federação do Skype for Business Server e/ou da rota de federação XMPP para usar novamente esse pool de Borda restaurado.

1.  No pool de Borda disponível novamente, inicie os Serviços de Borda.

2.  Se você quiser fazer failback da rota Skype for Business Server federação para usar o Servidor de Borda restaurado, faça o seguinte:
    
    1. No servidor de front-end, abra o Construtor de Topologia. **Expanda pools de borda** e clique com o botão direito do mouse no servidor de Borda ou no pool de servidores de Borda que está configurado atualmente para Federação. Selecione **Editar propriedades**.
    
    1. Em **Editar propriedades**, em **Geral**, desmarque **Habilitar federação para este pool de Borda (Porta 5061)**. Selecione **OK**.
    
    1. **Expanda pools de borda** e clique com o botão direito do mouse no servidor de Borda original ou no pool de servidores de Borda que você deseja usar novamente para Federação. Selecione **Editar propriedades**.
    
    1. Em **Editar propriedades**, em **Geral**, selecione **Habilitar federação para este pool de Borda (Porta 5061)**. Selecione **OK**.
    
    1. Selecione **Ação**, **Topologia****, Publicar.** Quando solicitado a publicar **a topologia**, selecione **Avançar**. Quando a publicação for concluída, selecione **Concluir**.
    
    1. No servidor de Borda, abra o assistente Skype for Business Server Implantação. Selecione **Instalar ou Atualizar Skype for Business Server e**, em seguida, selecione **Configurar ou Remover Skype for Business Server Componentes**. Selecione **Executar Novamente**.
    
    1. Selecione **Avançar**. A tela de resumo mostrará ações conforme são executadas. Depois que a implantação for concluída, selecione **Exibir Log** para exibir os arquivos de log disponíveis. Selecione **Concluir** para concluir a implantação.

3.  Se você deseja realizar o fail back da rota de federação XMPP para usar o Servidor de Borda restaurado, faça o seguinte:
    
    1. Execute o seguinte cmdlet para reapontar a rota de federação XMPP para o pool de Borda que irá hospedar agora a federação XMPP (neste exemplo, EdgeServer1):
  
        ```powershell
        Set-CsSite Site1 -XmppExternalFederationRoute EdgeServer1.contoso.com
        ```
        
        Neste exemplo, Site1 é o local contendo o pool de Borda que irá agora hospedar a rota de federação XMPP e EdgeServer1.contoso.com é o FQDN de um Servidor de Borda no pool.
    
    1. Se você ainda não tiver um registro DNS SRV para a federação XMPP que resolve o pool de Borda que hospedará a federação XMPP, você deve adicioná-lo, conforme no exemplo a seguir. Este registro SRV deve ter um valor de porta de 5269.

        ```console
        _xmpp-server._tcp.contoso.com
        ```
    
    1. No servidor DNS externo, altere o registro DNS A para federação XMPP apontar para o EdgeServer2.contoso.com.
    
    1. Verifique se o pool de Borda irá agora hospedar federação XMPP com porta 5269 aberta externamente.

4.  Se os pools de front-end permanecem executando no site contendo o pool de Borda que falhou e foi restaurado, você deve atualizar o Serviço de Conferência da Web e o Serviço de Conferência A/V nestes pools de front-end para usar novamente os pools de Borda em seu site local.

5.  Se o pool de front-end no mesmo site possui um pool de Borda em falha que também falhou, é possível agora usar Invoke–CsPoolFailback para fazer o fail back do pool de front-end.


## <a name="change-the-edge-pool-associated-with-a-front-end-pool"></a>Alterar o pool de borda associado a um pool de Front-Ends

Se um pool de borda cair, mas o pool de front-ends do mesmo local ainda estiver em execução, será preciso configurar o pool de front-ends para que use o pool de borda de um local diferente até que o pool de borda com falha seja restaurado.

1.  NO Construtor de Topologias, navegue até o nome no pool de front-ends que precisa ser alterado.

2.  Clique com o botão direito do mouse no pool e selecione **Editar Propriedades**.

3.  Na seção **Associações**, em **Associar Pool de Borda (para componentes de mídia)**, use a caixa suspensa para selecionar o pool de borda ao qual deseja associar o pool de front-ends.

4.  Selecione **OK**.
