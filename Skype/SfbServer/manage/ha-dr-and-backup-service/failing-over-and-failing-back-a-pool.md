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
ms.openlocfilehash: f2a1970df43aa2fb7becb03319ee6ff5934afe0a
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/08/2020
ms.locfileid: "40991796"
---
# <a name="failing-over-and-failing-back-a-pool-in-skype-for-business-server"></a>Com failover e failback de um pool no Skype for Business Server 

Use os procedimentos a seguir se um único pool de front-end tiver falhado e precisar de failover, ou se o pool que sofreu o desastre estiver novamente online e você precisar restaurar a implantação para o status de trabalho normal. Além disso, saiba como fazer failover e failback do pool de bordas usado para a Federação do Skype for Business ou Federação do XMPP ou alterar o pool de bordas associado a um pool de front-ends.

- [Fazer failover em um pool de front-end](#fail-over-a-front-end-pool)
- [Fazer failback de um pool](#fail-back-a-pool)
- [Fazer failover do pool de bordas usado para o Skype for Business Server Federation](#fail-over-the-edge-pool-used-for-skype-for-business-server-federation)
- [Fazer failover do pool de bordas usado para a Federação do XMPP no Skype for Business Server](#fail-over-the-edge-pool-used-for-xmpp-federation-in-skype-for-business-server)
- [Fazer failback do pool de bordas usado para Federação do Skype for Business Server ou Federação do XMPP](#fail-back-the-edge-pool-used-for-skype-for-business-server-federation-or-xmpp-federation)
- [Alterar o pool de bordas associado a um pool de front-end](#change-the-edge-pool-associated-with-a-front-end-pool)

## <a name="fail-over-a-front-end-pool"></a>Fazer failover em um pool de front-end

Neste procedimento, Datacenter1 contém Pool1, e Pool1 falhou. Você está falhando no Pool2 localizado no Datacenter2.

A maior parte do trabalho do failover de pool envolve a falha em relação ao repositório de gerenciamento central, se for necessário. Isso é importante porque o repositório de gerenciamento central deve ser funcional quando os usuários do pool tiverem failover.

Além disso, se um pool de front-ends falhar, mas o pool de bordas nesse site ainda estiver em execução, você deverá saber se o pool de bordas usa o pool com falha como um próximo pool de saltos. Em caso afirmativo, você deve alterar o pool de bordas para usar um pool de front-end diferente antes de falhar sobre o pool de front-ends com falha. A maneira como você altera a próxima configuração de salto depende se a borda usará um pool no mesmo site que o pool de bordas ou um site diferente.

**Para definir um pool de bordas para usar um próximo pool de saltos no mesmo site**

1.  Abra o construtor de topologias, clique com o botão direito do mouse no pool de bordas que precisa ser alterado e clique em **Editar propriedades**.

2.  Clique em **próximo salto**. Na lista **próximo pool de saltos:** , selecione o pool que agora funcionará como o próximo pool de saltos.

3.  Clique em **OK**e, em seguida, publique as alterações.

**Para definir um pool de bordas para usar um próximo pool de saltos em um site diferente**

1.  Abra uma janela do Shell de gerenciamento do Skype for Business Server e digite o seguinte cmdlet:
    
        Set-CsEdgeServer -Identity EdgeServer:<Edge Server pool FQDN> -Registrar Registrar:<NextHopPoolFQDN>

**Para causar failover em um pool em um desastre**

1.  Localize o pool que é o host do servidor de gerenciamento central, digitando o cmdlet a seguir em um servidor front-end no Pool2:
    
        Invoke-CsManagementServerFailover -Whatif
    
    Os resultados deste cmdlet mostram qual pool atualmente hospeda o servidor central de gerenciamento. No restante deste procedimento, esse pool é conhecido como o pool de\_CMS.

2.  Use o construtor de topologias para localizar a versão do Skype for Business Server em\_execução no pool do CMS. Se ele estiver executando o Skype for Business Server, use o cmdlet a seguir para localizar o pool de backup do pool 1.
    
        Get-CsPoolBackupRelationship -PoolFQDN <CMS_Pool FQDN>
    
    Permitir que\_o pool de backup seja o pool de backup.

3.  Verifique o status do repositório central de gerenciamento com o seguinte cmdlet:
    
        Get-CsManagementStoreReplicationStatus -CentralManagementStoreStatus 
    
    Este cmdlet deve mostrar que ambos ActiveMasterFQDN e ActiveFileTransferAgents estão apontando para o FQDN do pool\_de CMS. Se estiverem vazios, o servidor central de gerenciamento não está disponível e você deve fazer o failover.

4.  Se o repositório de gerenciamento central não estiver disponível ou se o repositório de gerenciamento central estiver em execução no Pool1 (ou seja, o pool com falha), você deverá fazer failover do servidor de gerenciamento central antes de falhar sobre o pool. Se você precisar fazer failover do servidor de gerenciamento central hospedado em um pool que executa o Skype for Business Server, use o cmdlet na etapa 5 deste procedimento. Se você não precisar fazer failover do servidor de gerenciamento central, pule para a etapa 7 deste procedimento.

5.  Para fazer failover do repositório de gerenciamento central em um pool que executa o Skype for Business Server, faça o seguinte:
    
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
        ```PowerShell
         
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

7.  Reprovar os usuários do Pool1 para o Pool2 executando o seguinte cmdlet em uma janela do Shell de gerenciamento do Skype for Business Server:
    
        Invoke-CsPoolFailover -PoolFQDN <Pool1 FQDN> -DisasterMode -Verbose
    
    Como as etapas executadas nas partes anteriores deste procedimento para verificar o status do repositório de gerenciamento central não são universais, ainda há uma chance de que esse cmdlet falhe porque o repositório de gerenciamento central ainda não passou por failover completo. Nesse caso, você deve corrigir o repositório de gerenciamento central com base nas mensagens de erro que você vê e executar esse cmdlet novamente.
    
    Se você vir a mensagem de erro a seguir, será necessário alterar o pool de bordas neste site para usar um pool diferente como próximo salto antes de falhar sobre o pool. Para obter detalhes, consulte os procedimentos no início deste tópico.
    
        Invoke-CsPoolFailOver : This Front-end pool "pool1.contoso.com" is specified in
        topology as the next hop for the Edge server. Failing over this pool may cause External
        access/Federation/Split-domain/XMPP features to stop working. Please use Topology Builder to
        change the Edge internal next hop setting to point to a different Front-end pool,  before you
        proceed.


## <a name="fail-back-a-pool"></a>Fazer failback de um pool

Após o pool que sofreu o desastre ficar online novamente (ou seja, Pool1 neste exemplo), siga as etapas a seguir para restaurar a implantação para o status de trabalho normal.

Observe que o processo de failback demora vários minutos para ser concluído.Para referência, a expectativa é de até 60 minutos para um pool de 20.000 usuários.

Reproduza os usuários que estavam originalmente hospedados no Pool1 e que falharam no Pool2 digitando o seguinte cmdlet:
    
    Invoke-CsPoolFailback -PoolFQDN <Pool1 FQDN> -Verbose

Nenhuma outra etapa é necessária. Se você tiver reprovado o servidor central de gerenciamento, poderá deixá-lo no Pool2.

## <a name="fail-over-the-edge-pool-used-for-skype-for-business-server-federation"></a>Fazer failover do pool de bordas usado para o Skype for Business Server Federation 

Se o pool de bordas em que você tiver configurado o Skype for Business Server configurado ficar inativo, você deverá alterar a Federação para usar um pool de bordas diferente para o trabalho de Federação.

1.  Em um servidor front-end, abra o construtor de topologias. Expanda **pools de bordas**e clique com o botão direito do mouse no servidor de borda ou no pool do servidor de borda atualmente configurado para Federação. Selecione **Editar propriedades**.

2.  Em **Editar propriedades** em **geral**, desmarque **habilitar Federação para este pool de bordas (porta 5061)**. Clique em **OK**.

3.  Expanda **pools de bordas**e clique com o botão direito do mouse no servidor de borda ou no pool do servidor de borda que você agora deseja usar para a Federação. Selecione **Editar propriedades**.

4.  Em **Editar propriedades** em **geral**, selecione **habilitar Federação para este pool de bordas (porta 5061)**. Clique em **OK**.

5.  Clique em **ação**, selecione **topologia**, selecione **publicar**. Quando solicitado em **publicar a topologia**, clique em **Avançar**. Quando a publicação estiver concluída, clique em **concluir**.

6.  No servidor de borda, abra o assistente de implantação do Skype for Business Server. Clique em **instalar ou atualizar o sistema do Skype for Business Server**e, em seguida, clique em **Configurar ou remover componentes do Skype for Business Server**. Clique em **executar novamente**.

7.  Click **Next**. A tela Resumo mostrará as ações conforme elas são executadas. Depois que a implantação for concluída, clique em **Exibir log** para exibir os arquivos de log disponíveis. Clique em **concluir** para concluir a implantação.
    
    Se o site que contém o pool de bordas com falha contiver servidores front-end que ainda estão em execução, você deve atualizar o serviço de Webconferência e o serviço de conferência A/V nesses pools de front-ends para usar um pool de bordas em um site remoto que ainda esteja em execução. 

 ## <a name="fail-over-the-edge-pool-used-for-xmpp-federation-in-skype-for-business-server"></a>Fazer failover do pool de bordas usado para a Federação do XMPP no Skype for Business Server 

Em sua organização, há um pool de bordas designado como o pool a ser usado para a Federação do XMPP. Se esse pool ficar inativo, você deve fazer failover da Federação do XMPP para usar um pool de bordas diferente antes que o XMPP federado possa funcionar novamente.

Ao instalar primeiro os pools de borda e habilitar a Federação do XMPP, você pode simplificar o processo de recuperação de desastres Configurando os registros SRV DNS externos para todos os seus pools de bordas para a Federação do XMPP, em vez de apenas um. Cada um desses registros SRV deve ter um conjunto de prioridades diferente. Todo o tráfego de Federação do XMPP passa pelo pool com o registro SRV com a prioridade mais alta. 

No procedimento a seguir, EdgePool1 é o pool que hospeda originalmente a Federação do XMPP, e EdgePool2 é o pool que agora hospeda XMPP Federação.


### <a name="to-fail-over-the-edge-pool-used-for-xmpp-federation"></a>Para fazer failover do pool de bordas usado para a Federação do XMPP

1.  Se você ainda não tiver outro pool de bordas implantado (além do que está indisponível no momento), implante esse pool. 

2.  Em cada servidor de borda no novo pool de bordas que agora hospeda a Federação do XMPP (EdgePool2), execute o seguinte cmdlet:
    
        Stop-CsWindowsService

3.  Execute o cmdlet a seguir para redirecionar a rota de Federação do XMPP para EdgePool2:
    
        Set-CsSite Site2 -XmppExternalFederationRoute EdgeServer2.contoso.com
    
    Neste exemplo, site2 é o site que contém o pool de borda que agora hospeda a rota de Federação do XMPP, e EdgeServer2.contoso.com é o FQDN de um servidor de borda nesse pool.

4.  No servidor DNS externo, altere o registro DNS a para a Federação XMPP para apontar para EdgeServer2.contoso.com.

5.  Se você ainda não tiver um registro SRV DNS para a Federação do XMPP, que é resolvido para o pool de borda que agora hospedará a Federação do XMPP, você deve adicioná-lo, como no exemplo a seguir. Esse registro SRV deve ter um valor de porta 5269.
    
        _xmpp-server._tcp.contoso.com

6.  Verifique se o pool de bordas que agora hospeda a Federação do XMPP tem a porta 5269 aberta externamente.

7.  Inicie os serviços em todos os servidores de borda do pool de borda que agora hospedarão a Federação do XMPP:
    
        Start-CsWindowsService


## <a name="fail-back-the-edge-pool-used-for-skype-for-business-server-federation-or-xmpp-federation"></a>Fazer failback do pool de bordas usado para Federação do Skype for Business Server ou Federação do XMPP 

Depois que um pool de borda com falha que foi usado para hospedar a Federação foi colocado online novamente, use este procedimento para fazer failback da rota de Federação do Skype for Business Server e/ou da rota de Federação do XMPP novamente para usar este pool de bordas restaurado.

1.  No pool de bordas que agora está disponível novamente, inicie os serviços de borda.

2.  Se você quiser fazer failback da rota de Federação do Skype for Business Server para usar o servidor de borda restaurado, faça o seguinte:
    
      - Em um servidor front-end, abra o construtor de topologias. Expanda **pools de bordas**, clique com o botão direito do mouse no servidor de borda ou no pool do servidor de borda que está atualmente configurado para Federação. Selecione **Editar propriedades**.
    
      - Em **Editar propriedades** em **geral**, desmarque **habilitar Federação para este pool de bordas (porta 5061)**. Clique em **OK**.
    
      - Expanda **pools de bordas**e clique com o botão direito do mouse no servidor de borda original ou no pool do servidor de borda que você deseja usar novamente para a Federação. Selecione **Editar propriedades**.
    
      - Em **Editar propriedades** em **geral**, selecione **habilitar Federação para este pool de bordas (porta 5061)**. Clique em **OK**.
    
      - Clique em **ação**, selecione **topologia**, selecione **publicar**. Quando solicitado em **publicar a topologia**, clique em **Avançar**. Quando a publicação estiver concluída, clique em **concluir**.
    
      - No servidor de borda, abra o assistente de implantação do Skype for Business Server. Clique em **instalar ou atualizar o sistema do Skype for Business Server**, em seguida, clique em **Configurar ou remover componentes do Skype for Business Server**. Clique em **executar novamente**.
    
      - Click **Next**. A tela Resumo mostrará as ações conforme elas são executadas. Depois que a implantação for concluída, clique em **Exibir log** para exibir os arquivos de log disponíveis. Clique em **concluir** para concluir a implantação.

3.  Se você quiser fazer failback na rota de Federação do XMPP para usar o servidor de borda restaurado, faça o seguinte:
    
      - Execute o cmdlet a seguir para redirecionar a rota de Federação do XMPP para o pool de borda que agora hospeda a Federação XMPP (neste exemplo, EdgeServer1):
        
            Set-CsSite Site1 -XmppExternalFederationRoute EdgeServer1.contoso.com
        
        Neste exemplo, site1 é o site que contém o pool de borda que agora hospeda a rota de Federação do XMPP, e EdgeServer1.contoso.com é o FQDN de um servidor de borda nesse pool.
    
      - Se você ainda não tiver um registro SRV DNS para a Federação do XMPP, que é resolvido para o pool de borda que agora hospedará a Federação do XMPP, você deve adicioná-lo, como no exemplo a seguir. Esse registro SRV deve ter um valor de porta 5269.
        
            _xmpp-server._tcp.contoso.com
    
      - No servidor DNS externo, altere o registro DNS a para a Federação XMPP para apontar para EdgeServer2.contoso.com.
    
      - Verifique se o pool de bordas que agora hospeda a Federação do XMPP tem a porta 5269 aberta externamente.

4.  Se os pools de front-end permanecerem sendo executados no site que contém o pool de borda que falhou e foi restaurado, você deverá atualizar o serviço de Webconferência e o serviço de conferência A/V nesses pools de front-ends para usar novamente os pools de borda em seu site local.

5.  Se o pool de front-ends no mesmo site do pool de borda com falha também falhar, agora você pode usar Invoke – CsPoolFailback para fazer failback do pool de front-ends.


## <a name="change-the-edge-pool-associated-with-a-front-end-pool"></a>Alterar o pool de bordas associado a um pool de front-end

Se um pool de bordas ficar inoperante, mas o pool de front-end no mesmo site ainda estiver em execução, será necessário definir o pool de front-ends para usar um pool de bordas em um site diferente até que o pool de bordas com falha seja restaurado.

1.  No construtor de topologias, navegue até o nome do pool de front-ends que você precisa alterar.

2.  Clique com o botão direito do mouse no pool e, em seguida, clique em **Editar propriedades**.

3.  Na seção **associações** , em associar a um **pool de bordas (para componentes de mídia)**, use a caixa suspensa para selecionar o pool de bordas ao qual você deseja associar esse pool de front-ends.

4.  Clique em **OK**.
