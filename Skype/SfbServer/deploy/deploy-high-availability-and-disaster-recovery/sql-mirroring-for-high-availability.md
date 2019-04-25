---
title: Implantar espelhamento de SQL para alta disponibilidade do servidor back-end no Skype for Business Server 2015
ms.reviewer: ''
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 70224520-b5c8-4940-a08e-7fb9b1adde8d
description: 'Para que seja possível implantar o espelhamento de SQL, os servidores devem executar no mínimo o SQL Server 2008 R2. Essa versão deve ser executada em todos os servidores envolvidos: o principal, o espelho e a testemunha. Para obter detalhes, consulte cumulativa 9 do pacote de atualização para SQL Server 2008 Service Pack 1.'
ms.openlocfilehash: ebf1d222bff572100fe7824e52acdef2ff85216d
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32225515"
---
# <a name="deploy-sql-mirroring-for-back-end-server-high-availability-in-skype-for-business-server-2015"></a>Implantar o espelhamento do SQL para servidor Back-End alta disponibilidade em Skype para Business server 2015


Para que seja possível implantar o espelhamento de SQL, os servidores devem executar no mínimo o SQL Server 2008 R2. Essa versão deve ser executada em todos os servidores envolvidos: o principal, o espelho e a testemunha. Para obter detalhes, consulte [cumulativa 9 para SQL Server 2008 Service Pack 1 do pacote de atualização ](https://go.microsoft.com/fwlink/p/?linkid=3052&amp;kbid=2083921).

Em geral, a configuração do espelhamento SQL entre os dois Servidores Back-End com uma testemunha requer:

- Versão do servidor principal do SQL Server deve oferecer suporte a espelhamento SQL.

- Que o principal, o espelho e a testemunha (se implantada) tenham a mesma versão do SQL Server.

- Que o principal e o espelho tenham a mesma edição do SQL Server. A testemunha pode ter uma edição diferente.

Para as práticas recomendadas do SQL em termos de quais versões do SQL são suportadas para uma função de testemunha, consulte [A testemunha de espelhamento de banco de dados](https://go.microsoft.com/fwlink/p/?LinkId=247345).

Use o construtor de topologias para implantar o espelhamento SQL. Selecione uma opção no construtor de topologias para fazer o espelhamento de bancos de dados e o construtor de topologias configura o espelhamento (inclusive configurar uma testemunha, se desejar) quando você publica a topologia. Observe que a testemunha é configurada ou removida ao mesmo tempo que o espelho. Não há um comando separado para implantar ou remover somente uma testemunha.

Antes de configurar o espelhamento do servidor, você deve configurar as permissões do banco de dados SQL corretamente. Para obter detalhes, consulte [Definir backup contas de logon para o espelhamento de banco de dados ou grupos de disponibilidade AlwaysOn (SQL Server)](https://go.microsoft.com/fwlink/p/?LinkId=268454).

Com o espelhamento de SQL, o modo de recuperação de banco de dados fica sempre definido como **Completo**, o que significa que você deve monitorar de perto o tamanho dos logs de transações e fazer backups regulares para evitar o esgotamento do espaço em disco dos Servidores Back-End. A frequência de backups de logs de transações depende da taxa de crescimento dos logs, que, por sua vez, depende das transações do banco de dados provenientes de atividades de usuários no pool de front-ends. Recomendamos que você determine o nível esperado de crescimento dos logs de transação para a carga de trabalho da implantação, para que seja possível realizar um planejamento adequado. Os artigos a seguir fornecem mais informações sobre o gerenciamento de logs e backups de SQL:

- [Modelos de recuperação de banco de dados](https://go.microsoft.com/fwlink/p/?LinkId=268446)

- [Visão geral de backup](https://go.microsoft.com/fwlink/p/?LinkId=268449)

- [Log de transações de backup](https://go.microsoft.com/fwlink/p/?LinkId=268452)

Com o espelhamento de SQL, você pode configurar a topologia do espelhamento quando criar pools ou depois que eles forem criados.

> [!IMPORTANT]
> Usando o construtor de topologia ou cmdlets para configurar e remover SQL espelhamento é aceito somente quando o principal, espelho e servidores de testemunha (se desejar) pertencem ao mesmo domínio. Se quiser configurar o espelhamento SQL entre servidores de domínios diferentes, consulte a documentação do SQL Server.

> [!IMPORTANT]
> Sempre que fizer uma alteração em uma relação de espelhamento de banco de dados back-end, você deverá reiniciar todos os servidores front-end do pool.  gt _ para uma alteração de espelhamento, (por exemplo, alterando o local de um espelho), você deve usar o construtor de topologias para executar estas três etapas:

1. Remova o espelhamento do servidor espelho antigo.

2. Adicione espelhamento ao novo servidor espelho.

3. Publique a topologia.

> [!NOTE]
> Um compartilhamento de arquivos deve ser criado para os arquivos espelho a serem gravados, e o serviço no qual o SQL Server e o SQL Agent estão sendo executados precisam de acesso de leitura/gravação. Se o serviço SQL Server está sendo executado em contexto de serviço de rede, você pode adicionar \<domínio\>\\<SQLSERVERNAME\>$ do Principal e espelho SQL Servers para as permissões de compartilhamento. O $ é importante para identificar que esta é uma conta de computador.

## <a name="to-configure-sql-mirroring-while-creating-a-pool-in-topology-builder"></a>Para configurar o espelhamento SQL durante a criação de um pool no construtor de topologia

1. Na página **Definir o Repositório SQL**, clique em **Novo** ao lado da caixa **Repositório SQL**. 

2. Na página **Definir Novo Repositório SQL**, especifique o repositório principal, selecione **Esta instância SQL está em relação de espelhamento**, especifique o número da porta de espelhamento de SQL (o padrão é 5022) e clique em **OK**.

3. De volta à página **Definir o Repositório SQL**, selecione **Habilitar espelhamento do repositório SQL**. 

4. Na página **Definir Novo Repositório SQL**, especifique o repositório SQL a ser usado como espelho. Selecione **Esta instância SQL está em relação de espelhamento**, especifique o número da porta (o padrão é 5022) e clique em **OK**.

5. Caso deseje uma testemunha para esse espelho, faça o seguinte: 

    a. Selecione **Usar testemunha de espelhamento do SQL para habilitar failover automático**. 

    b. Na página **Definir o repositório SQL**, selecione **Usar testemunha de espelhamento do SQL para habilitar failover automático** e especifique o repositório SQL a ser usado como testemunha. 

    c. Especifique o número da porta (o padrão é 7022) e clique em **OK**. 

6. Depois de terminar a definição de seu pool de Front-End e todas as outras funções em sua topologia, use o construtor de topologias para publicar a topologia. Quando a topologia é publicada, se o pool de Front-End que hospeda o repositório de gerenciamento Central tiver habilitado de espelhamento do SQL, você verá uma opção para criar os dois primário e espelhar bancos de dados de repositório SQL.

    Clique em **Configurações** e digite o caminho que será usado como compartilhamento de arquivos para o backup de espelhamento.

    Clique em **OK** e em **Avançar** para criar os bancos de dados e publicar a topologia. O espelhamento e a testemunha (se especificada) serão implantados.

Você pode usar o construtor de topologias para editar as propriedades de um pool já existente para habilitar o espelhamento do SQL.

## <a name="to-add-sql-mirroring-to-an-existing-front-end-pool-in-topology-builder"></a>Para adicionar o espelhamento SQL a um pool de Front-End existente no construtor de topologia

1. No construtor de topologia, clique com botão direito do pool e clique em **Editar propriedades**.

2. Selecione **Habilitar Espelhamento do Repositório SQL** e clique em **Novo** ao lado de **Repositório SQL de Espelhamento**. 

3. Especifique o repositório SQL que você deseja usar como espelho. 

4. Selecione **Esta instância SQL está em relação de espelhamento**, especifique o número da porta de espelhamento SQL (o padrão é 5022) e clique em **OK**.

5. Caso deseje configurar uma testemunha, selecione **Usar testemunha de espelhamento SQL para habilitar failover automático** e clique em **Novo**. 

6. Especifique o repositório SQL que você deseja usar como testemunha. 

7. Selecione **Esta instância SQL está em relação de espelhamento**, especifique o número da porta de espelhamento SQL (o padrão é 7022) e clique em **OK**.

8. Clique em **OK**.

9. Publique a topologia. Quando você fizer isso, o sistema solicitará a instalação do banco de dados. 

    Durante o processo de publicação da topologia, você deverá definir um caminho de compartilhamento de arquivos. Os SQL Servers que participam do espelhamento devem ter acesso de leitura/gravação a esse compartilhamento de arquivos para que o espelhamento seja estabelecido.

Instale o banco de dados antes de ir para o próximo procedimento.

Lembre-se disto ao configurar o espelhamento de SQL:

- Caso já exista um ponto de extremidade de espelhamento, ele será reutilizado usando as portas definidas nele e irá ignorar aquelas especificadas na topologia.

- Todas as portas já alocadas para outros aplicativos no mesmo servidor (inclusive de outras instâncias SQL) não deverão ser usadas para as instâncias SQL instaladas atualmente. Isso significa que, se você tiver mais de uma instância SQL instalada no mesmo servidor, elas não poderão usar a mesma porta para espelhamento. Para saber mais, veja os seguintes artigos:

  - [Especificar um endereço de rede do servidor (espelhamento de banco de dados)](https://go.microsoft.com/fwlink/p/?LinkId=247346)

  - [O banco de dados (SQL Server) do ponto de extremidade de espelhamento](https://go.microsoft.com/fwlink/p/?LinkId=247347)

## <a name="using-skype-for-business-server-2015-management-shell-cmdlets-to-set-up-sql-mirroring"></a>Usando o Skype para Cmdlets do Shell de gerenciamento do Business Server 2015 ao conjunto o espelhamento SQL

A maneira mais fácil de configurar o espelhamento é usando o construtor de topologia, mas você também pode fazer isso usando cmdlets.

1. Abra um Skype para a janela do Shell de gerenciamento do Business Server 2015 e execute o seguinte cmdlet:

   ```
   Install-CsMirrorDatabase [-ConfiguredDatabases] [-ForInstance] [-ForDefaultInstance] [-DatabaseType <Application | Archiving | CentralMgmt | Monitoring | User | BIStaging | PersistentChat | PersistentChatCompliance >] -FileShare <fileshare> -SqlServerFqdn <primarySqlserverFqdn> [-SqlInstanceName] [-DatabasePathMap] [-ExcludeDatabaseList] [-DropExistingDatabasesOnMirror] -Verbose
   ```

    Por exemplo:

   ```
   Install-CsMirrorDatabase -ConfiguredDatabases -FileShare \\PRIMARYBE\csdatabackup -SqlServerFqdn primaryBE.contoso.com -DropExistingDatabasesOnMirror -Verbose
   ```

    Você verá:

   <pre>
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
   </pre>

2. Verifique se:

    - A porta 5022 pode ser acessada através do firewall se o Firewall do Windows estiver habilitado no SQL Server principal e04-ocs.los_a.lsipt.local\rtc. 

    - A porta 5022 pode ser acessada através do firewall se o Firewall do Windows estiver habilitado no SQL Server espelho K16-ocs.los_a.lsipt.local\rtc. 

    - A porta 7022 pode ser acessada através do firewall se o Firewall do Windows estiver habilitado no SQL Server testemunha AB14-lct.los_a.lsipt.local\rtc. 

   - Contas executando o SQL Servers em todos os primário e o espelhamento SQL servers têm permissão de leitura/gravação para o compartilhamento de arquivo \\E04-OCS\csdatabackup

   - Verifique se o provedor WMI (Instrumentação de Gerenciamento do Windows) está em execução em todos esses servidores. O cmdlet usa esse provedor para encontrar informações da conta relativas aos serviços do SQL Server em execução em todos os servidores principais, espelho e testemunha. 

   - Verifique se a conta que executa esse cmdlet tem permissão para criar as pastas de dados e de arquivos de log para todos os servidores espelho. 

   - Observe que a conta de usuário usada pela instância SQL para execução deve ter permissão de leitura/gravação no compartilhamento de arquivos. Se o compartilhamento de arquivos estiver em um servidor diferente e a instância SQL for executada em uma conta do sistema local, você deverá conceder permissões de compartilhamento de arquivos ao servidor que hospeda a instância SQL.

3. Digite A e pressione ENTER.

    O espelhamento será configurado.

    **Install-CsMirrorDatabase** instala o espelho e configura o espelhamento para todos os bancos de dados que estão presentes no repositório de SQL principal. Se você deseja configurar o espelhamento de bancos de dados somente específicos, você pode usar a opção - DatabaseType, ou se você quiser configurar o espelhamento para todos os bancos de dados, com exceção de alguns, você pode usar a opção - ExcludeDatabaseList, juntamente com uma lista separada por vírgulas de banco de dados nomes a serem excluídos.

    Por exemplo, caso você adicione a opção a seguir a **Install-CsMirrorDatabase**, todos os bancos de dados serão espelhados, com exceção de rtcab e rtcxds.

    `-ExcludeDatabaseList rtcab,rtcxds`

   Por exemplo, caso você adicione a opção a seguir a **Install-CsMirrorDatabase**, somente os bancos de dados rtcab, rtcshared e rtcxds serão espelhados.

    `-DatabaseType User`

## <a name="removing-or-changing-sql-mirroring"></a>Remoção ou alteração do espelhamento SQL

Para remover o espelhamento de SQL de um pool no Construtor de Topologias, primeiro use um cmdlet para remover o espelho no SQL Server. Em seguida, você poderá usar o Construtor de Topologias para remover o espelho da topologia. Para remover o espelho no SQL Server, use o cmdlet a seguir:

```
Uninstall-CsMirrorDatabase -SqlServerFqdn <SQLServer FQDN> [-SqlInstanceName <SQLServer instance name>] -DatabaseType <Application | Archiving | CentralMgmt | Monitoring | User | BIStaging | PersistentChat | PersistentChatCompliance> [-DropExistingDatabasesOnMirror] [-Verbose]
```

Por exemplo, para remover o espelhamento e os bancos de dados de usuários, digite:

```
Uninstall-CsMirrorDatabase -SqlServerFqdn primaryBE.contoso.com -SqlInstanceName rtc -Verbose -DatabaseType User -DropExistingDatabasesOnMirror
```

O `-DropExistingDatabasesOnMirror` opção faz com que os bancos de dados afetados sejam excluídas do espelho.

Depois, para remover o espelho da topologia, faça o seguinte:

1. No Construtor de Topologias, clique com o botão direito do mouse no pool e clique em **Editar Propriedades**.

2. Desmarque **Habilitar Espelhamento do Repositório SQL** e clique em **OK**.

3. Publique a topologia.

## <a name="removing-a-mirroring-witness"></a>Remoção de uma testemunha de espelhamento

Use este procedimento se você precisa remover a testemunha de um servidor Back-End configuração de espelhamento.

1. No Construtor de Topologias, clique com o botão direito do mouse no pool e clique em **Editar Propriedades**.

2. Desmarque **Usar testemunha de espelhamento do SQL Server para habilitar failover automático** e clique em **OK**.

3. Publique a topologia.

    Após publicar a topologia, o construtor de topologia você verá uma mensagem que inclui os seguintes

   ```
   Run the Uninstall-CsMirrorDatabase cmdlet to remove databases that are paired with following primary databases.
   ```

    No entanto, não siga essa etapa e não digite `Uninstall-CsMirrorDatabase` como isso fará a desinstalação toda a configuração do espelhamento.

4. Para remover apenas a testemunha da configuração do SQL Server, siga as instruções em [Remover a testemunha de uma sessão de espelhamento de banco de dados (SQL Server)](https://go.microsoft.com/fwlink/p/?LinkId=268456).


