---
title: Implantando espelhamento SQL para alta disponibilidade de Servidor Back-End
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Deploying SQL mirroring for Back End Server high availability
ms:assetid: 70224520-b5c8-4940-a08e-7fb9b1adde8d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204992(v=OCS.15)
ms:contentKeyID: 48184451
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8eb8c9647c24f326b1a2a51c99e7fa4ee5eafa23
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34829539"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deploying-sql-mirroring-for-back-end-server-high-availability-in-lync-server-2013"></a>Implantando espelhamento SQL para alta disponibilidade de Servidor Back-End no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2014-01-08_

Para que seja possível implantar o espelhamento de SQL, os servidores devem executar no mínimo o SQL Server 2008 R2. Essa versão deve ser executada em todos os servidores envolvidos: o principal, o espelho e a testemunha. Para obter detalhes, [http://go.microsoft.com/fwlink/p/?linkid=3052\&kbid=2083921](http://go.microsoft.com/fwlink/p/?linkid=3052%26kbid=2083921)consulte.

Em geral, a configuração do espelhamento SQL entre os dois Servidores Back-End com uma testemunha requer:

  - Que a versão do SQL Server do servidor principal ofereça suporte a espelhamento SQL.

  - Que o principal, o espelho e a testemunha (se implantada) tenham a mesma versão do SQL Server.

  - Que o principal e o espelho tenham a mesma edição do SQL Server. A testemunha pode ter uma edição diferente.

Para as práticas recomendadas do SQL em termos de quais versões do SQL são compatíveis com uma função de testemunha, consulte "testemunha de espelhamento de [http://go.microsoft.com/fwlink/p/?LinkId=247345](http://go.microsoft.com/fwlink/p/?linkid=247345)banco de dados" na biblioteca MSDN em.

Você usa o construtor de topologias para implantar o espelhamento do SQL. Você seleciona uma opção no construtor de topologias para espelhar os bancos de dados, e o construtor de topologias configura o espelhamento (incluindo a configuração de uma testemunha, se desejar) quando você publica a topologia. Observe que a testemunha é configurada ou removida ao mesmo tempo que o espelho. Não há um comando separado para implantar ou remover somente uma testemunha.

Antes de configurar o espelhamento do servidor, você deve configurar as permissões do banco de dados SQL corretamente. Para obter detalhes, consulte "configurar contas de logon para o espelhamento de banco de dados ou grupos de disponibilidade AlwaysOn [http://go.microsoft.com/fwlink/p/?LinkId=268454](http://go.microsoft.com/fwlink/p/?linkid=268454)(SQL Server)" em.

Com o espelhamento SQL, o modo de recuperação de banco de dados fica sempre definido como **Completo**, o que significa que você deve monitorar de perto o tamanho dos logs de transações, fazendo backup regular para evitar o esgotamento do espaço em disco dos Servidores Back-End. A frequência dos backups dos logs de transações depende da taxa de expansão dos logs, que, por sua vez, depende das transações do banco de dados provenientes de atividades de usuários no Pool de Front-Ends. Recomendamos que você determine a expansão dos logs de transação que é esperada para a carga de trabalho de implantação do Lync para que seja possível realizar um planejamento adequado. Os artigos a seguir fornecem mais informações sobre o gerenciamento de logs e backups do SQL:

  - Modelos de recuperação de banco de dados: "modelos de recuperação (SQL Server)" em[http://go.microsoft.com/fwlink/p/?LinkId=268446](http://go.microsoft.com/fwlink/p/?linkid=268446)

  - Visão geral do backup: "visão geral do backup (SQL Server)" em[http://go.microsoft.com/fwlink/p/?LinkId=268449](http://go.microsoft.com/fwlink/p/?linkid=268449)

  - Log de transação de backup: "fazer backup de um log de transação (SQL Server)" em[http://go.microsoft.com/fwlink/p/?LinkId=268452](http://go.microsoft.com/fwlink/p/?linkid=268452)

Com o espelhamento de SQL, você pode configurar a topologia do espelhamento quando criar pools ou depois que eles forem criados.



> [!IMPORTANT]
> Usar o construtor de topologias ou cmdlets para configurar e remover o espelhamento do SQL só tem suporte quando os servidores primário, espelho e testemunha (se desejado) pertencem ao mesmo domínio. Se quiser configurar o espelhamento SQL entre servidores de domínios diferentes, consulte a documentação do SQL Server.





> [!IMPORTANT]
> Sempre que fizer uma alteração em uma relação de espelhamento de banco de dados back-end, você deverá reiniciar todos os servidores front-end do pool. <BR>Para uma alteração no espelhamento, (como alterar a localização de um espelho), você deve usar o construtor de topologias para executar estas três etapas: 
> <OL>
> <LI>
> <P>Remova o espelhamento do servidor espelho antigo.</P>
> <LI>
> <P>Adicione espelhamento ao novo servidor espelho.</P>
> <LI>
> <P>Publique a topologia.</P></LI></OL>




> [!NOTE]
> Um compartilhamento de arquivos deve ser criado para os arquivos espelho a serem gravados, e o serviço no qual o SQL Server e o SQL Agent estão sendo executados precisam de acesso de leitura/gravação. Se o serviço do SQL Server estiver sendo executado no contexto do serviço de rede, você &lt;poderá&gt; adicionar &lt;o domínio&#92;&gt;SqlServerName $ dos servidores principal e espelho do SQL às permissões de compartilhamento. O $ é importante para identificar que esta é uma conta de computador.


<div>

## <a name="to-configure-sql-mirroring-while-creating-a-pool-in-topology-builder"></a>Para configurar o espelhamento do SQL durante a criação de um pool no construtor de topologias

1.  Na página **Definir o Repositório SQL**, clique em **Novo** ao lado da caixa **Repositório SQL**. 

2.  Na página **Definir Novo Repositório SQL**, especifique o repositório principal, selecione **Esta instância SQL está em relação de espelhamento**, especifique o número da porta de espelhamento de SQL (o padrão é 5022) e clique em **OK**.

3.  De volta à página **Definir o Repositório SQL**, selecione **Habilitar espelhamento do repositório SQL**. 

4.  Na página **Definir Novo Repositório SQL**, especifique o repositório SQL a ser usado como espelho. Selecione **Esta instância SQL está em relação de espelhamento**, especifique o número da porta (o padrão é 5022) e clique em **OK**.

5.  Caso deseje uma testemunha para esse espelho, faça o seguinte: 
    
    1.  Selecione **Usar testemunha de espelhamento do SQL para habilitar failover automático**. 
    
    2.  Na página **Definir o repositório SQL**, selecione **Usar testemunha de espelhamento do SQL para habilitar failover automático** e especifique o repositório SQL a ser usado como testemunha. 
    
    3.  Especifique o número da porta (o padrão é 7022) e clique em **OK**. 

6.  Depois de definir o pool de front-end e todas as outras funções em sua topologia, use o construtor de topologias para publicar a topologia. Quando a topologia for publicada, se o pool de front-ends que hospeda o repositório de gerenciamento central tiver o SQL Mirroring habilitado, você verá uma opção para criar bancos de dados principais e espelho do SQL Store.
    
    Clique em **Configurações** e digite o caminho que será usado como compartilhamento de arquivos para o backup de espelhamento.
    
    Clique em **OK** e em **Avançar** para criar os bancos de dados e publicar a topologia. O espelhamento e a testemunha (se especificada) serão implantados.

Você pode usar o construtor de topologias para editar as propriedades de um pool já existente para habilitar o espelhamento do SQL.

</div>

<div>

## <a name="to-add-sql-mirroring-to-an-existing-front-end-pool-in-topology-builder"></a>Para adicionar o espelhamento do SQL a um pool de front-ends existente no construtor de topologias

1.  No construtor de topologias, clique com o botão direito do mouse no pool e clique em **Editar propriedades**.

2.  Selecione **Habilitar Espelhamento do Repositório SQL** e clique em **Novo** ao lado de **Repositório SQL de Espelhamento**. 

3.  Especifique o repositório SQL que você deseja usar como espelho. 

4.  Selecione **Esta instância SQL está em relação de espelhamento**, especifique o número da porta de espelhamento SQL (o padrão é 5022) e clique em **OK**.

5.  Caso deseje configurar uma testemunha, selecione **Usar testemunha de espelhamento SQL para habilitar failover automático** e clique em **Novo**. 

6.  Especifique o repositório SQL que você deseja usar como testemunha. 

7.  Selecione **Esta instância SQL está em relação de espelhamento**, especifique o número da porta de espelhamento SQL (o padrão é 7022) e clique em **OK**.

8.  Clique em **OK**.

9.  Publique a topologia. Quando você fizer isso, o sistema solicitará a instalação do banco de dados. 
    
    Durante o processo de publicação da topologia, você deverá definir um caminho de compartilhamento de arquivos. Os SQL Servers que participam do espelhamento devem ter acesso de leitura/gravação a esse compartilhamento de arquivos para que o espelhamento seja estabelecido.

Instale o banco de dados antes de ir para o próximo procedimento.

Lembre-se disto ao configurar o espelhamento de SQL:

  - Caso já exista um ponto de extremidade de espelhamento, ele será reutilizado usando as portas definidas nele e irá ignorar aquelas especificadas na topologia.

  - Todas as portas já alocadas para outros aplicativos no mesmo servidor (inclusive de outras instâncias SQL) não deverão ser usadas para as instâncias SQL instaladas atualmente. Isso significa que, se você tiver mais de uma instância SQL instalada no mesmo servidor, elas não poderão usar a mesma porta para espelhamento. Para saber mais, veja os seguintes artigos:
    
      - "Especifique um endereço de rede de servidor (espelhamento de banco de dados)" na biblioteca MSDN em[http://go.microsoft.com/fwlink/p/?LinkId=247346](http://go.microsoft.com/fwlink/p/?linkid=247346)
    
      - "O ponto de extremidade do espelhamento do banco de dados (SQL Server)" em[http://go.microsoft.com/fwlink/p/?LinkId=247347](http://go.microsoft.com/fwlink/p/?linkid=247347)

</div>

<div>

## <a name="using-lync-server-management-shell-cmdlets-to-set-up-sql-mirroring"></a>Usar cmdlets do Shell de gerenciamento do Lync Server para configurar o espelhamento do SQL

A maneira mais fácil de configurar o espelhamento é usando o construtor de topologias, mas você também pode fazer isso usando cmdlets.

1.  Abra uma janela do Shell de gerenciamento do Lync Server e execute o seguinte cmdlet:
    
        Install-CsMirrorDatabase [-ConfiguredDatabases] [-ForInstance] [-ForDefaultInstance] [-DatabaseType <Application | Archiving | CentralMgmt | Monitoring | User | BIStaging | PersistentChat | PersistentChatCompliance >] -FileShare <fileshare> -SqlServerFqdn <primarySqlserverFqdn> [-SqlInstanceName] [-DatabasePathMap] [-ExcludeDatabaseList] [-DropExistingDatabasesOnMirror] -Verbose 
    
    Por exemplo:
    
        Install-CsMirrorDatabase -ConfiguredDatabases -FileShare \\PRIMARYBE\csdatabackup -SqlServerFqdn primaryBE.contoso.com -DropExistingDatabasesOnMirror -Verbose 
    
    Você verá:
    
        Database Name:rtcxds 
                Data File:D:\CsData\BackendStore\rtc\DbPath\rtcxds.mdf 
                 Log File:D:\CsData\BackendStore\rtc\LogPath\rtcxds.ldf 
              Primary SQL: e04-ocs.los_a.lsipt.local\rtc 
                  Account: LOS_A\e04-ocs$ 
               Mirror SQL: K16-ocs.los_a.lsipt.local\rtc 
                  Account: LOS_A\K16-ocs$ 
             Witness SQL : AB14-lct.los_a.lsipt.local\rtc 
                  Account: LOS_A\AB14-lct$ 
            Database Name:rtcshared 
                Data File:D:\CsData\BackendStore\rtc\DbPath\rtcshared.mdf 
                 Log File:D:\CsData\BackendStore\rtc\LogPath\rtcshared.ldf 
              Primary SQL: e04-ocs.los_a.lsipt.local\rtc 
                  Account: LOS_A\e04-ocs$ 
               Mirror SQL: K16-ocs.los_a.lsipt.local\rtc 
                  Account: LOS_A\K16-ocs$ 
             Witness SQL : AB14-lct.los_a.lsipt.local\rtc 
                  Account: LOS_A\AB14-lct$ 
            Database Name:rtcab 
                Data File:D:\CsData\ABSStore\rtc\DbPath\rtcab.mdf 
                 Log File:D:\CsData\ABSStore\rtc\LogPath\rtcab.ldf 
              Primary SQL: e04-ocs.los_a.lsipt.local\rtc 
                  Account: LOS_A\e04-ocs$ 
               Mirror SQL: K16-ocs.los_a.lsipt.local\rtc 
                  Account: LOS_A\K16-ocs$ 
             Witness SQL : AB14-lct.los_a.lsipt.local\rtc 
                  Account: LOS_A\AB14-lct$ 
            Database Name:rgsconfig 
                Data File:D:\CsData\ApplicationStore\rtc\DbPath\rgsconfig.mdf 
                 Log File:D:\CsData\ApplicationStore\rtc\LogPath\rgsconfig.ldf 
              Primary SQL: e04-ocs.los_a.lsipt.local\rtc 
                  Account: LOS_A\e04-ocs$ 
               Mirror SQL: K16-ocs.los_a.lsipt.local\rtc 
                  Account: LOS_A\K16-ocs$ 
             Witness SQL : AB14-lct.los_a.lsipt.local\rtc 
                  Account: LOS_A\AB14-lct$ 
            Database Name:rgsdyn 
                Data File:D:\CsData\ApplicationStore\rtc\DbPath\rgsdyn.mdf 
                 Log File:D:\CsData\ApplicationStore\rtc\LogPath\rgsdyn.ldf 
              Primary SQL: e04-ocs.los_a.lsipt.local\rtc 
                  Account: LOS_A\e04-ocs$ 
               Mirror SQL: K16-ocs.los_a.lsipt.local\rtc 
                  Account: LOS_A\K16-ocs$ 
             Witness SQL : AB14-lct.los_a.lsipt.local\rtc 
                  Account: LOS_A\AB14-lct$ 
            Database Name:cpsdyn 
                Data File:D:\CsData\ApplicationStore\rtc\DbPath\cpsdyn.mdf 
                 Log File:D:\CsData\ApplicationStore\rtc\LogPath\cpsdyn.ldf 
              Primary SQL: e04-ocs.los_a.lsipt.local\rtc 
                  Account: LOS_A\e04-ocs$ 
               Mirror SQL: K16-ocs.los_a.lsipt.local\rtc 
                  Account: LOS_A\K16-ocs$ 
             Witness SQL : AB14-lct.los_a.lsipt.local\rtc 
                  Account: LOS_A\AB14-lct$ 
            Database Name:xds 
                Data File:D:\CsData\CentralMgmtStore\rtc\DbPath\xds.mdf 
                 Log File:D:\CsData\CentralMgmtStore\rtc\LogPath\xds.ldf 
              Primary SQL: e04-ocs.los_a.lsipt.local\rtc 
                  Account: LOS_A\e04-ocs$ 
               Mirror SQL: K16-ocs.los_a.lsipt.local\rtc 
                  Account: LOS_A\K16-ocs$ 
             Witness SQL : AB14-lct.los_a.lsipt.local\rtc 
                  Account: LOS_A\AB14-lct$ 
            Database Name:lis 
                Data File:D:\CsData\CentralMgmtStore\rtc\DbPath\lis.mdf 
                 Log File:D:\CsData\CentralMgmtStore\rtc\LogPath\lis.ldf 
              Primary SQL: e04-ocs.los_a.lsipt.local\rtc 
                  Account: LOS_A\e04-ocs$ 
               Mirror SQL: K16-ocs.los_a.lsipt.local\rtc 
                  Account: LOS_A\K16-ocs$ 
             Witness SQL : AB14-lct.los_a.lsipt.local\rtc 
                  Account: LOS_A\AB14-lct$
        [Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend  [?] Help (default is "Y"): 

2.  Verifique se:
    
      - A porta 5022 pode ser acessada por meio do firewall se o Firewall do Windows estiver habilitado no\_RTC primário do SQL Server\\E04-OCS. los a. lsipt. RTC local.
    
      - A porta 5022 pode ser acessada por meio do firewall se o Firewall do Windows estiver habilitado no\_RTC do SQL Server K16-OCS\\. los a. lsipt. local.
    
      - A porta 7022 pode ser acessada por meio do firewall se o Firewall do Windows estiver habilitado no\_RTC do SQL Server AB14-LCT\\. los a. lsipt. RTC local.
    
      - As contas que executam os servidores SQL em todos os servidores SQL primários e espelhados têm permissão de \\ \\leitura/gravação\\para o compartilhamento de arquivos E04-OCS csdatabackup
    
      - Verifique se o provedor WMI (Instrumentação de Gerenciamento do Windows) está em execução em todos esses servidores. O cmdlet usa esse provedor para encontrar informações da conta relativas aos serviços do SQL Server em execução em todos os servidores principais, espelho e testemunha. 
    
      - Verifique se a conta que executa esse cmdlet tem permissão para criar as pastas de dados e de arquivos de log para todos os servidores espelho. 
    
      - Observe que a conta de usuário usada pela instância SQL para execução deve ter permissão de leitura/gravação no compartilhamento de arquivos. Se o compartilhamento de arquivos estiver em um servidor diferente e a instância SQL for executada em uma conta do sistema local, você deverá conceder permissões de compartilhamento de arquivos ao servidor que hospeda a instância SQL.

3.  Digite A e pressione ENTER.
    
    O espelhamento será configurado.

**Install-CsMirrorDatabase** instala o espelhamento e configura o espelhamento para todos os bancos de dados que estão presentes no repositório SQL principal. Se você quiser configurar o espelhamento somente para bancos de dados específicos, poderá usar a opção – DatabaseType ou se quiser configurar o espelhamento para todos os bancos de dados, exceto para alguns, você pode usar a opção-ExcludeDatabaseList, juntamente com uma lista de banco de dados separada por vírgulas nomes a serem excluídos.

Por exemplo, caso você adicione a opção a seguir a **Install-CsMirrorDatabase**, todos os bancos de dados serão espelhados, com exceção de rtcab e rtcxds.

`-ExcludeDatabaseList rtcab,rtcxds`

Por exemplo, caso você adicione a opção a seguir a **Install-CsMirrorDatabase**, somente os bancos de dados rtcab, rtcshared e rtcxds serão espelhados.

`-DatabaseType User`

</div>

<div>

## <a name="removing-or-changing-sql-mirroring"></a>Remoção ou alteração do espelhamento SQL

Para remover o espelhamento de SQL de um pool no Construtor de Topologias, primeiro use um cmdlet para remover o espelho no SQL Server. Em seguida, você poderá usar o Construtor de Topologias para remover o espelho da topologia. Para remover o espelho no SQL Server, use o cmdlet a seguir:

    Uninstall-CsMirrorDatabase -SqlServerFqdn <SQLServer FQDN> [-SqlInstanceName <SQLServer instance name>] -DatabaseType <Application | Archiving | CentralMgmt | Monitoring | User | BIStaging | PersistentChat | PersistentChatCompliance> [-DropExistingDatabasesOnMirror] [-Verbose]

Por exemplo, para remover o espelhamento e os bancos de dados de usuários, digite:

    Uninstall-CsMirrorDatabase -SqlServerFqdn primaryBE.contoso.com -SqlInstanceName rtc -Verbose -DatabaseType User -DropExistingDatabasesOnMirror

A `-DropExistingDatabasesOnMirror` opção faz com que os bancos de dados afetados sejam excluídos do espelho.

Depois, para remover o espelho da topologia, faça o seguinte:

1.  No Construtor de Topologias, clique com o botão direito do mouse no pool e clique em **Editar Propriedades**.

2.  Desmarque **Habilitar Espelhamento do Repositório SQL** e clique em **OK**.

3.  Publique a topologia.

</div>

<div>

## <a name="removing-a-mirroring-witness"></a>Remoção de uma testemunha de espelhamento

Use esse procedimento se você precisar remover a testemunha de uma configuração de espelhamento de servidor back-end.

1.  No Construtor de Topologias, clique com o botão direito do mouse no pool e clique em **Editar Propriedades**.

2.  Desmarque **Usar testemunha de espelhamento do SQL Server para habilitar failover automático** e clique em **OK**.

3.  Publique a topologia.
    
    Depois de publicar a topologia, o construtor de topologias será exibida uma mensagem que inclui os seguintes
    
        Run the Uninstall-CsMirrorDatabase cmdlet to remove databases that are paired with following primary databases.
    
    No entanto, não siga essa etapa e não digite `Uninstall-CsMirrorDatabase` como isso desinstalaria toda a configuração de espelhamento.

4.  Para remover apenas a testemunha da configuração do SQL Server, siga as instruções em "remover a testemunha de uma sessão de espelhamento de banco de dados (SQL [http://go.microsoft.com/fwlink/p/?LinkId=268456](http://go.microsoft.com/fwlink/p/?linkid=268456)Server)" em.

</div>

</div>

<span> </span>

</div>

</div>

</div>

