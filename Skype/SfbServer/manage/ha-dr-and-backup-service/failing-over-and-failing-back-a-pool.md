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
ms.openlocfilehash: 547a71f44fa81f9ba12a1c661465c7b8604b3fa1
ms.sourcegitcommit: 414d077b16a0ae4ea6a49e3b3d0082858174cacb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/17/2021
ms.locfileid: "50278671"
---
# <a name="failing-over-and-failing-back-a-pool-in-skype-for-business-server"></a>Falha e falha de um pool no Skype for Business Server

Use os procedimentos a seguir se um único pool de Front-End falhar e precisar de um failed over ou se o pool que passou por esse desastre estiver novamente online e você precisar restaurar sua implantação para o status de trabalho regular. Saiba como fazer fail over e fail back do pool de Borda usado para federação do Skype for Business ou federação XMPP ou alterar o pool de Borda associado a um pool de Front-End.

- [Fail over a Front End pool](#fail-over-a-front-end-pool)
- [Fail back de um pool](#fail-back-a-pool)
- [Fail over the Edge pool used for Skype for Business Server federation](#fail-over-the-edge-pool-used-for-skype-for-business-server-federation)
- [Fail over the Edge pool used for XMPP federation in Skype for Business Server](#fail-over-the-edge-pool-used-for-xmpp-federation-in-skype-for-business-server)
- [Fail back do pool de Borda usado para federação do Skype for Business Server ou federação XMPP](#fail-back-the-edge-pool-used-for-skype-for-business-server-federation-or-xmpp-federation)
- [Alterar o pool de Borda associado a um pool de Front-End](#change-the-edge-pool-associated-with-a-front-end-pool)

## <a name="fail-over-a-front-end-pool"></a>Fail over a Front-End pool

Datacenter1 contém Pool1 e Pool1 falhou. Você está fazendo o failing over para o Pool2 localizado no Datacenter2.

A maior parte do trabalho para o failover do pool envolve o failover do armazenamento de Gerenciamento Central, se necessário. O armazenamento de Gerenciamento Central deve estar funcional quando os usuários do pool são reavariados.

Se um pool Front-End falhar, mas o pool de Borda nesse site ainda estiver em execução, você deverá saber se o pool de Borda usará o pool com falha como pool de próximo salto. Se isso acontecer, você deve alterar o pool de Borda para usar um pool de Front-End diferente antes de fazer o failed Front-End pool. Como a configuração do próximo salto será alterada dependerá de a Borda usar um pool no mesmo local do pool de Borda ou em um local diferente.

**Para definir um pool de Borda para usar um pool de próximo salto no mesmo site**

1. Abra o Construtor de Topologias, clique com o botão direito do mouse no pool de Borda que precisa ser alterado e selecione **Editar Propriedades.**

2. Selecione **Próximo Salto.** No pool **de próximo salto:** lista, selecione o pool que servirá agora como o pool do próximo salto.

3. Selecione **OK** e publique as alterações.

**Para definir um pool de Borda para usar um pool de próximo salto em um site diferente**

1. Abra uma janela do Shell de Gerenciamento do Skype for Business Server e digite o seguinte cmdlet:

        Set-CsEdgeServer -Identity EdgeServer:<Edge Server pool FQDN> -Registrar Registrar:<NextHopPoolFQDN>

**Para fazer fail over de um pool em um desastre**

1. Encontre o pool de host do Servidor de Gerenciamento Central digitando o seguinte cmdlet em um servidor Front-End servidor no Pool2:

        Invoke-CsManagementServerFailover -Whatif

    Os resultados desse cmdlet mostram qual pool hospeda atualmente o Servidor de Gerenciamento Central. No restante deste procedimento, esse pool é conhecido como \_ Pool CMS.

2. Use o Construtor de Topologias para encontrar a versão do Skype for Business Server em execução no Pool DE \_ CMS. Se estiver executando o Skype for Business Server, use o cmdlet a seguir para encontrar o pool de backup do Pool 1.

        Get-CsPoolBackupRelationship -PoolFQDN <CMS_Pool FQDN>

    Deixe o \_ Pool de Backup ser o pool de backup.

3. Verifique o status do armazenamento de Gerenciamento Central com o seguinte cmdlet:

        Get-CsManagementStoreReplicationStatus -CentralManagementStoreStatus 

    Este cmdlet deve mostrar que ActiveMasterFQDN e ActiveFileTransferAgents estão apontando para o FQDN do Pool DE \_ CMS. Se eles estão vazios, o Servidor de Gerenciamento Central não está disponível e você deve fazer fail over.

4.  Se o armazenamento de Gerenciamento Central não estiver disponível ou se o armazenamento de Gerenciamento Central estava em execução no Pool1 (ou seja, o pool que falhou), você deve fazer fail over do Servidor de Gerenciamento Central antes de fazer fail over do pool. Se você precisar fazer o fail over do Servidor de Gerenciamento Central que estava hospedado em um pool executando o Skype for Business Server, use o cmdlet na etapa 5 deste procedimento. Se não for necessário fazer fail over do Servidor de Gerenciamento Central, pule para a etapa 7 deste procedimento.

5.  Para fazer fail over the Central Management store on a pool running Skype for Business Server, do the following:

      - Primeiro, verifique qual Back-End Server no Pool de Backup executa a instância principal do armazenamento de Gerenciamento \_ Central digitando o seguinte:

            Get-CsDatabaseMirrorState -DatabaseType Centralmgmt -PoolFqdn <Backup_Pool Fqdn>
    
      - Se o servidor Back-End servidor primário no Pool de \_ Backup for o principal, digite:
        
            Invoke-CSManagementServerFailover -BackupSQLServerFqdn <Backup_Pool Primary BackEnd Server FQDN> -BackupSQLInstanceName <Backup_Pool Primary SQL Instance Name>
        
        Se o servidor Back-End espelho no Pool de \_ Backup for o principal, digite:
        
            Invoke-CSManagementServerFailover -MirrorSQLServerFqdn <Backup_Pool Mirror BackEnd Server FQDN> -MirrorSQLInstanceName <Backup_Pool Mirror SQL Instance Name>
    
      - Valide se o failover do Servidor de Gerenciamento Central está concluído. Digite o seguinte comando:
        
            Get-CsManagementStoreReplicationStatus -CentralManagementStoreStatus 
        
        Verifique se ActiveMasterFQDN e ActiveFileTransferAgents estão apontando para o FQDN do Pool de \_ Backup.
    
      - Por fim, verifique o status da réplica para todos os Front-End Servidores, digitando o seguinte:
        
            Get-CsManagementStoreReplicationStatus 
        
        Verifique se todas as réplicas possuem o valor Verdadeiro (True).
        
        Pule para a etapa 7 neste procedimento.

6.  Instale o armazenamento de Gerenciamento Central no Servidor back-end do pool de \_ backup.
    
      - Primeiro, execute o seguinte comando:
        ```PowerShell
         
        Install-CsDatabase -CentralManagementDatabase -Clean -SqlServerFqdn <Backup_Pool Back End Server FQDN> -SqlInstanceName rtc  
        ```
    
      - Execute o próximo comando em um dos Servidores Front End do Pool de Backup para forçar a movimentação do \_ armazenamento de Gerenciamento Central:
        
            Move-CsManagementServer -ConfigurationFileName c:\CsConfigurationFile.zip -LisConfigurationFileName c:\CsLisConfigurationFile.zip -Force 
    
      - Valide se a movimentação está concluída:
        
            Get-CsManagementStoreReplicationStatus -CentralManagementStoreStatus 
        
        Verifique se ActiveMasterFQDN e ActiveFileTransferAgents estão apontando para o FQDN do Pool de \_ Backup.
    
      - Verifique o status da réplica para todos os servidores de Front End digitando:
        
            Get-CsManagementStoreReplicationStatus 
        
        Verifique se todas as réplicas possuem o valor Verdadeiro (True).
    
      - Instale o serviço do Servidor de Gerenciamento Central no restante dos Servidores Front-End no Pool de \_ Backup. Para fazer isso, execute o seguinte comando em todos os Servidores front-end, exceto aquele usado ao forçar a movimentação do armazenamento de Gerenciamento Central anteriormente neste procedimento:
        
            Bootstrapper /Setup 

7.  Fail over the users from Pool1 to Pool2 by running the following cmdlet in a Skype for Business Server Management Shell window:
    
        Invoke-CsPoolFailover -PoolFQDN <Pool1 FQDN> -DisasterMode -Verbose
    
    Como as etapas realizadas nas partes anteriores deste procedimento para verificar o status do armazenamento de Gerenciamento Central não são universais, ainda há uma chance de que esse cmdlet falhe porque o armazenamento de Gerenciamento Central ainda não foi totalmente realizado. Nesse caso, você deve corrigir o Armazenamento de Gerenciamento Central com base nas mensagens de erro que vê e executar esse cmdlet novamente.
    
    Se a mensagem de erro a seguir for apresentada, será necessário alterar o pool de Borda neste local para usar um pool diferente como próximo salto antes da fazer o failover do pool. Para detalhes, consulte os procedimentos no início deste tópico.
    
        Invoke-CsPoolFailOver : This Front-end pool "pool1.contoso.com" is specified in
        topology as the next hop for the Edge server. Failing over this pool may cause External
        access/Federation/Split-domain/XMPP features to stop working. Please use Topology Builder to
        change the Edge internal next hop setting to point to a different Front-end pool,  before you
        proceed.


## <a name="fail-back-a-pool"></a>Fail back de um pool

Depois que o pool que passou por desastre voltar a ficar online (ou seja, o Pool1 neste exemplo), execute as etapas a seguir para restaurar sua implantação para o status funcional normal.

O processo de failback leva vários minutos para ser concluído. Para referência, espera-se que leve até 60 minutos para um pool de 20.000 usuários.

Para fazer failback dos usuários que estavam originalmente hospedados no Pool1 e dos quais foi feito failover para o Pool2, digite o seguinte cmdlet:
    
    Invoke-CsPoolFailback -PoolFQDN <Pool1 FQDN> -Verbose

Nenhuma outra etapa é necessária. Se você tiver falhado no Servidor de Gerenciamento Central, poderá deixá-lo no Pool2.

## <a name="fail-over-the-edge-pool-used-for-skype-for-business-server-federation"></a>Fail over the Edge pool used for Skype for Business Server federation 

Se o pool de Borda onde você tem a federação do Skype for Business Server configurada ficar ino mesmo, você deve alterar a federação para usar um pool de Borda diferente para que a federação funcione.

1.  No servidor de front-end, abra o Construtor de Topologia. Expanda **pools de** Borda e clique com o botão direito do mouse no servidor de Borda ou pool de servidores de Borda atualmente configurado para Federação. Selecione **Editar propriedades**.

2.  Em **Editar propriedades**, em **Geral**, desmarque **Habilitar federação para este pool de Borda (Porta 5061)**. Clique em **OK**.

3.  Expanda **pools de** Borda e clique com o botão direito do mouse no servidor de Borda ou pool de servidores de Borda que você agora deseja usar para Federação. Selecione **Editar propriedades**.

4.  Em **Editar propriedades**, em **Geral**, selecione **Habilitar federação para este pool de Borda (Porta 5061)**. Clique em **OK**.

5.  Select **Action**, select **Topology**, select **Publish**. Quando solicitado em **Publicar a topologia,** selecione **Próximo**. Quando Publicar estiver concluído, selecione **Concluir**.

6.  No servidor de Borda, abra o Assistente de Implantação do Skype for Business Server. Selecione **Instalar ou Atualizar o Sistema do Skype for Business Server** e, em seguida, selecione Instalar ou Remover **Componentes do Skype for Business Server.** Selecione **Executar Novamente**.

7.  Selecione **Avançar**. A tela de resumo mostrará ações conforme são executadas. Quando a implantação for realizada, selecione **Exibir Log** para exibir os arquivos de log disponíveis. Selecione **Concluir** para concluir a implantação.
    
    Se o site que contém o pool de Borda com falha contiver Servidores front-end que ainda estão em execução, você deve atualizar o Serviço de Webconferência e o Serviço de Conferência A/V nesses pools de Front-End para usar um pool de Borda em um site remoto que ainda está em execução. 

 ## <a name="fail-over-the-edge-pool-used-for-xmpp-federation-in-skype-for-business-server"></a>Fail over the Edge pool used for XMPP federation in Skype for Business Server 

Na sua organização, há um pool de borda designado como o pool para uso da federação XMPP. Se esse pool parar de funcionar, você deve transferir a federação XMPP para usar um pool de borda diferente antes da federação XMPP poder funcionar novamente.

Quando você instala pools de borda e habilita a Federação XMPP, é possível simplificar o processo de recuperação de desastres configurando a criação de registros do servidor DNS externos para todos os seus pools de Borda para a federação XMPP, em vez de apenas um. Cada um destes registros SRV devem ter um conjunto de prioridade diferente. Todo o tráfego da federação XMPP atravessa o pool com o registro SRV com a mais alta prioridade. 

No procedimento a seguir, EdgePool1 é o pool, que originalmente hospedava a federação XMPP, e EdgePool2 é o pool que agora hospedará a federação XMPP.
### <a name="to-fail-over-the-edge-pool-used-for-xmpp-federation"></a>Para fazer fail over do pool de Borda usado para federação XMPP

1.  Se você ainda não tiver outro pool de Borda implantado (além do que está inocionado no momento), implante esse pool. 

2.  Em cada Servidor de Borda no novo pool de borda no qual a federação XMPP estará hospedada no momento (EdgePool2), execute o seguinte cmdlet:
    
        Stop-CsWindowsService

3.  Execute o seguinte cmdlet para redirecionar a rota da federação XMPP para o EdgePool2:
    
        Set-CsSite Site2 -XmppExternalFederationRoute EdgeServer2.contoso.com
    
    Neste exemplo, o Site2 é o site contendo o pool de borda no qual a rota da federação XMPP estará hospedada no momento e o EdgeServer2.contoso.com é o FQDN de um Servidor de Borda nesse pool.

4.  No servidor DNS externo, altere o registro A de DNS da federação XMPP para apontar para o EdgeServer2.contoso.com.

5.  Se você ainda não tiver um registro DNS SRV para a federação XMPP que resolva o pool de borda no qual a federação XMPP estará hospedada no momento, é necessário adicioná-lo, conforme no exemplo a seguir. O registro SRV deve ter um valor de porta de 5269.
    
        _xmpp-server._tcp.contoso.com

6.  Verifique se o pool de borda no qual a federação XMPP estará hospedada no momento possui uma porta 5269 aberta externamente.

7.  Inicie os serviços em todos os Servidores de Borda no pool de borda no qual a federação XMPP estará hospedada no momento:
    
        Start-CsWindowsService

## <a name="fail-back-the-edge-pool-used-for-skype-for-business-server-federation-or-xmpp-federation"></a>Fail back do pool de Borda usado para federação do Skype for Business Server ou federação XMPP 

Depois que um pool de Borda com falha usado para hospedar a federação foi trazido novamente online, use este procedimento para fazer fail back da rota de federação do Skype for Business Server e/ou a rota de federação XMPP para usar novamente esse pool de Borda restaurado.

1.  No pool de Borda disponível novamente, inicie os Serviços de Borda.

2.  Se você quiser fazer fail back da rota de federação do Skype for Business Server para usar o Servidor de Borda restaurado, faça o seguinte:
    
      - No servidor de front-end, abra o Construtor de Topologia. Expanda **pools de Borda** e clique com o botão direito do mouse no servidor de Borda ou pool de servidores de Borda atualmente configurado para Federação. Selecione **Editar propriedades**.
    
      - Em **Editar propriedades**, em **Geral**, desmarque **Habilitar federação para este pool de Borda (Porta 5061)**. Clique em **OK**.
    
      - Expanda **pools de Borda** e clique com o botão direito do mouse no servidor de Borda original ou pool de servidores de Borda que você deseja usar novamente para Federação. Selecione **Editar propriedades**.
    
      - Em **Editar propriedades**, em **Geral**, selecione **Habilitar federação para este pool de Borda (Porta 5061)**. Clique em **OK**.
    
      - Select **Action**, select **Topology**, select **Publish**. Quando solicitado em **Publicar a topologia,** selecione **Próximo**. Quando Publicar estiver concluído, selecione **Concluir**.
    
      - No servidor de Borda, abra o Assistente de Implantação do Skype for Business Server. Select **Install or Update Skype for Business Server System**, then select Setup or Remove Skype for Business Server **Components**. Selecione **Executar Novamente**.
    
      - Selecione **Avançar**. A tela de resumo mostrará ações conforme são executadas. Quando a implantação for realizada, selecione **Exibir Log** para exibir os arquivos de log disponíveis. Selecione **Concluir** para concluir a implantação.

3.  Se você deseja realizar o fail back da rota de federação XMPP para usar o Servidor de Borda restaurado, faça o seguinte:
    
      - Execute o seguinte cmdlet para reapontar a rota de federação XMPP para o pool de Borda que irá hospedar agora a federação XMPP (neste exemplo, EdgeServer1):
        
            Set-CsSite Site1 -XmppExternalFederationRoute EdgeServer1.contoso.com
        
        Neste exemplo, Site1 é o local contendo o pool de Borda que irá agora hospedar a rota de federação XMPP e EdgeServer1.contoso.com é o FQDN de um Servidor de Borda no pool.
    
      - Se você ainda não tiver um registro DNS SRV para a federação XMPP que resolve o pool de Borda que hospedará a federação XMPP, você deve adicioná-lo, conforme no exemplo a seguir. Este registro SRV deve ter um valor de porta de 5269.
        
            _xmpp-server._tcp.contoso.com
    
      - No servidor DNS externo, altere o registro DNS A para federação XMPP apontar para o EdgeServer2.contoso.com.
    
      - Verifique se o pool de Borda irá agora hospedar federação XMPP com porta 5269 aberta externamente.

4.  Se os pools de front-end permanecem executando no site contendo o pool de Borda que falhou e foi restaurado, você deve atualizar o Serviço de Conferência da Web e o Serviço de Conferência A/V nestes pools de front-end para usar novamente os pools de Borda em seu site local.

5.  Se o pool de front-end no mesmo site possui um pool de Borda em falha que também falhou, é possível agora usar Invoke–CsPoolFailback para fazer o fail back do pool de front-end.


## <a name="change-the-edge-pool-associated-with-a-front-end-pool"></a>Alterar o pool de Borda associado a um pool de Front-End

Se um pool de borda cair, mas o pool de front-ends do mesmo local ainda estiver em execução, será preciso configurar o pool de front-ends para que use o pool de borda de um local diferente até que o pool de borda com falha seja restaurado.

1.  NO Construtor de Topologias, navegue até o nome no pool de front-ends que precisa ser alterado.

2.  Clique com o botão direito do mouse no pool e selecione **Editar Propriedades.**

3.  Na seção **Associações**, em **Associar Pool de Borda (para componentes de mídia)**, use a caixa suspensa para selecionar o pool de borda ao qual deseja associar o pool de front-ends.

4.  Clique em **OK**.
