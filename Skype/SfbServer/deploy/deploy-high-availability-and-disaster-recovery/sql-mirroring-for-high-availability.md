---
title: Implantar SQL espelhamento para alta disponibilidade do Servidor Back End no Skype for Business Server 2015
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 70224520-b5c8-4940-a08e-7fb9b1adde8d
description: 'Para que seja possível implantar o espelhamento SQL, os servidores devem executar no mínimo o SQL Server 2008 R2. Essa versão deve ser executada em todos os servidores envolvidos: principal, espelho e testemunha. Para obter detalhes, consulte Pacote de atualização cumulativa 9 para SQL Server 2008 Service Pack 1 .'
ms.openlocfilehash: b27fed99cafa109da8c13e369c93985d7bc4cf64
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/08/2021
ms.locfileid: "60849444"
---
# <a name="deploy-sql-mirroring-for-back-end-server-high-availability-in-skype-for-business-server-2015"></a>Implantar SQL espelhamento para alta disponibilidade do Servidor Back End no Skype for Business server 2015


Para que seja possível implantar o espelhamento SQL, os servidores devem executar no mínimo o SQL Server 2008 R2. Essa versão deve ser executada em todos os servidores envolvidos: principal, espelho e testemunha. Para obter detalhes, consulte Pacote de atualização [cumulativa 9 para SQL Server 2008 Service Pack 1](https://go.microsoft.com/fwlink/p/?linkid=3052&amp;kbid=2083921).

Em geral, a configuração do espelhamento SQL entre os dois servidores back-end com uma testemunha requer:

- A versão do servidor principal do SQL Server deve dar suporte SQL espelhamento.

- Que o principal, o espelho e a testemunha (se implantada) tenham a mesma versão do SQL Server.

- Que o principal e o espelho tenham a mesma edição do SQL Server. A testemunha pode ter uma edição diferente.

Para SQL práticas recomendadas em termos de quais versões SQL são suportadas para uma função Testemunha, consulte [Database Mirroring Witness](/sql/database-engine/database-mirroring/database-mirroring-witness).

Você usa o Construtor de Topologias para implantar SQL espelhamento. Você seleciona uma opção no Construtor de Topologias para espelhar os bancos de dados, e o Construtor de Topologia configura o espelhamento (incluindo a configuração de uma testemunha, se quiser) ao publicar a topologia. Observe que a testemunha é configurada ou removida ao mesmo tempo que o espelho. Não há um comando separado para implantar ou remover somente a testemunha.

Para configurar o espelhamento do servidor, primeiro você deve configurar as permissões do banco de dados SQL corretamente. Para obter detalhes, consulte [Set Up Login Accounts for Database Mirroring or AlwaysOn Availability Groups (SQL Server)](/sql/database-engine/database-mirroring/set-up-login-accounts-database-mirroring-always-on-availability).

Com o espelhamento SQL, o modo de recuperação de banco de dados fica sempre definido como **Completo**, o que significa que você deve monitorar de perto o tamanho dos logs de transações, fazendo backup regular deles para evitar o esgotamento do espaço em disco dos servidores back-end. A frequência dos backups dos logs de transações depende da taxa de expansão dos logs, que, por sua vez, depende das transações do banco de dados provenientes de atividades de usuários no pool front-end. Recomendamos que você determine quanto crescimento do log de transações é esperado para sua carga de trabalho de implantação para que você possa fazer o planejamento de acordo. Os artigos a seguir fornecem mais informações sobre o gerenciamento de logs e backups do SQL:

- [Modelos de recuperação de banco de dados](/sql/relational-databases/backup-restore/recovery-models-sql-server)

- [Visão geral do backup](/sql/relational-databases/backup-restore/backup-overview-sql-server)

- [Log de transações de backup](/sql/relational-databases/backup-restore/back-up-a-transaction-log-sql-server)

Com o espelhamento SQL, você pode configurar a topologia do espelhamento no momento da criação dos pools ou após isso.

> [!IMPORTANT]
> Usar o Construtor de Topologias ou cmdlets para configurar e remover SQL espelhamento só é suportado quando os servidores primário, espelho e testemunha (se desejado) pertencem ao mesmo domínio. Caso deseje configurar o espelhamento SQL entre servidores de domínios diferentes, consulte a documentação do SQL Server.

> [!IMPORTANT]
> Sempre que fizer uma alteração em um relacionamento de espelhamento de banco de dados back-end, você deverá reiniciar todos os servidores front-end do pool. > Para uma alteração no espelhamento (como alterar o local de um espelho), você deve usar o Construtor de Topologias para executar estas três etapas:

1. Remova o espelhamento do servidor espelho antigo.

2. Adicione espelhamento ao novo servidor espelho.

3. Publique a topologia.

> [!NOTE]
> Um compartilhamento de arquivos deve ser criado para que os arquivos espelho sejam gravados e o serviço que SQL Server e SQL Agente estão sendo executados em necessidades de acesso de leitura/gravação. Se o serviço SQL Server estiver em execução no contexto do Serviço de Rede, você poderá adicionar<SQLSERVERNAME $ dos Servidores de SQL Principal e Mirror às permissões de \<Domain\> \\ \> compartilhamento. O $ é importante para identificar que essa é uma conta de computador.

## <a name="to-configure-sql-mirroring-while-creating-a-pool-in-topology-builder"></a>Para configurar SQL espelhamento ao criar um pool no Construtor de Topologias

1. Na página **Definir o Repositório do SQL**, clique em **Novo** ao lado da caixa **Repositório do SQL**.

2. Na página **Definir Novo Repositório do SQL**, especifique o repositório principal, selecione **Esta instância SQL está em relação de espelhamento**, especifique o número da porta de espelhamento SQL (o padrão é 5022) e clique em **OK**.

3. De volta à página **Definir o Repositório do SQL**, selecione **Habilitar Espelhamento do Repositório do SQL**.

4. Na página **Definir Novo Repositório do SQL**, especifique o repositório do SQL a ser usado como espelho, selecione **Esta instância SQL está em relação de espelhamento**, especifique o número da porta de espelhamento SQL (o padrão é 5022) e clique em **OK**.

5. Caso deseje uma testemunha para este espelho, faça o seguinte:

    a. Selecione **Usar testemunha de espelhamento do SQL para habilitar failover automático**.

    b. Na página **Definir o Repositório do SQL**, selecione **Usar testemunha de espelhamento do SQL para habilitar failover automático** e especifique o repositório do SQL a ser usado como testemunha.

    c. Especifique o número da porta (o padrão é 7022) e clique em **OK**.

6. Depois de terminar de definir seu pool de Front-End e todas as outras funções em sua topologia, use o Construtor de Topologias para publicar a topologia. Quando a topologia for publicada, se o pool de Front-End que hospeda o armazenamento de Gerenciamento Central tiver SQL espelhamento habilitado, você verá uma opção para criar bancos de dados de armazenamento principal e SQL espelho.

    Clique em **Configurações** e digite o caminho que será usado como compartilhamento de arquivos para o backup de espelhamento.

    Clique em **OK** e em **Avançar** para criar os bancos de dados e publicar a topologia. O espelhamento e a testemunha (se especificada) serão implantados.

Você pode usar o Construtor de Topologias para editar as propriedades de um pool já existente para habilitar SQL espelhamento.

## <a name="to-add-sql-mirroring-to-an-existing-front-end-pool-in-topology-builder"></a>Para adicionar SQL espelhamento a um pool de Front-End existente no Construtor de Topologias

1. No Construtor de Topologias, clique com o botão direito do mouse no pool e clique em **Editar Propriedades**.

2. Selecione **Habilitar Espelhamento do Repositório do SQL** e clique em **Novo** ao lado de **Repositório do SQL de Espelhamento**.

3. Especifique o repositório do SQL que deseja usar como espelho.

4. Selecione **Esta instância SQL está em relação de espelhamento**, especifique o número da porta de espelhamento (o padrão é 5022) e clique em **OK**.

5. Caso deseje configurar uma testemunha, selecione **Usar testemunha de espelhamento do SQL para habilitar failover automático** e clique em **Novo**.

6. Especifique o repositório do SQL que deseja usar como testemunha.

7. Selecione **Esta instância SQL está em relação de espelhamento**, especifique o número da porta de espelhamento (o padrão é 7022) e clique em **OK**.

8. Clique em **OK**.

9. Publique a topologia. Quando você fizer isso, o sistema solicitará a instalação do banco de dados.

    Durante o processo de publicação de topologia, você será solicitado a definir um caminho de compartilhamento de arquivos. Os SQL servidores que participam do espelhamento devem ter acesso de leitura/gravação a esse compartilhamento de arquivos para que o espelho seja estabelecido.

Instale o banco de dados antes de ir para o próximo procedimento.

Lembre-se disto ao configurar o espelhamento SQL:

- Caso já exista um ponto de extremidade de espelhamento, ele será reutilizado usando as portas definidas nele e irá ignorar aquelas especificadas na topologia.

- Todas as portas já alocadas a outros aplicativos no mesmo servidor (inclusive de outras instâncias do SQL) não serão usadas com as instâncias do SQL instaladas atualmente. Isso significa que, se você tiver mais de uma instância do SQL instalada no mesmo servidor, elas não poderão usar a mesma porta para espalhamento. Para obter detalhes, consulte os seguintes artigos:

  - [Especificar um Endereço de Rede do Servidor (Espelhamento de Banco de Dados)](/sql/database-engine/database-mirroring/specify-a-server-network-address-database-mirroring)

  - [O Ponto de Extremidade de Espelhamento de Banco de Dados (SQL Server)](/sql/database-engine/database-mirroring/the-database-mirroring-endpoint-sql-server)

## <a name="using-skype-for-business-server-2015-management-shell-cmdlets-to-set-up-sql-mirroring"></a>Usando Skype for Business Server cmdlets do Shell de Gerenciamento 2015 para configurar SQL espelhamento

A maneira mais fácil de configurar o espelhamento é usando o Construtor de Topologias, mas você também pode fazer isso usando cmdlets.

1. Abra uma Skype for Business Server do Shell de Gerenciamento 2015 e execute o seguinte cmdlet:

   ```powershell
   Install-CsMirrorDatabase [-ConfiguredDatabases] [-ForInstance] [-ForDefaultInstance] [-DatabaseType <Application | Archiving | CentralMgmt | Monitoring | User | BIStaging | PersistentChat | PersistentChatCompliance >] -FileShare <fileshare> -SqlServerFqdn <primarySqlserverFqdn> [-SqlInstanceName] [-DatabasePathMap] [-ExcludeDatabaseList] [-DropExistingDatabasesOnMirror] -Verbose
   ```

    Por exemplo:

   ```powershell
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

    - A porta 5022 pode ser acessada pelo firewall quando o Firewall do Windows está habilitado no SQL Server principal e04-ocs.los_a.lsipt.local\rtc.

    - A porta 5022 pode ser acessada pelo firewall quando o Firewall do Windows está habilitado no SQL Server espelho K16-ocs.los_a.lsipt.local\rtc.

    - A porta 7022 pode ser acessada pelo firewall quando o Firewall do Windows está habilitado no SQL Server testemunha AB14-lct.los_a.lsipt.local\rtc.

   - Contas que executam os servidores SQL em todos os servidores SQL primários e espelhados têm permissão de leitura/gravação para o compartilhamento de arquivos \\ E04-OCS\csdatabackup

   - Verifique se o provedor WMI (Instrumentação de Gerenciamento do Windows) está em execução em todos esses servidores. O cmdlet usa esse provedor para encontrar informações da conta relativas aos serviços do SQL Server em execução em todos os servidores principais, espelho e testemunha.

   - Verifique se a conta que executa esse cmdlet tem permissão de criação das pastas dos dados e arquivos de log para todos os servidores espelho.

   - Observe que a conta de usuário usada pela instância do SQL para execução deve ter permissão de leitura/gravação do compartilhamento de arquivos. Se o compartilhamento de arquivos estiver em um servidor diferente e a instância do SQL for executada em uma conta do sistema local, você deverá conceder permissões de compartilhamento de arquivos ao servidor que hospeda a instância do SQL.

3. Digite A e pressione ENTER.

    O espelhamento será configurado.

    **Install-CsMirrorDatabase** instala o espelho e configura o espelhamento para todos os bancos de dados presentes no SQL principal. Se você quiser configurar o espelhamento apenas para bancos de dados específicos, use a opção -DatabaseType ou se quiser configurar o espelhamento para todos os bancos de dados, exceto para alguns, você pode usar a opção -ExcludeDatabaseList, juntamente com uma lista separada por vírgulas de nomes de banco de dados para excluir.

    Por exemplo, caso adicione a opção a seguir a **Install-CsMirrorDatabase**, todos os bancos de dados serão espelhados, com exceção de rtcab e rtcxds.

    `-ExcludeDatabaseList rtcab,rtcxds`

   Por exemplo, caso adicione a opção a seguir a **Install-CsMirrorDatabase**, somente os bancos de dados rtcab, rtcshared e rtcxds databases serão espelhados.

    `-DatabaseType User`

## <a name="removing-or-changing-sql-mirroring"></a>Removendo ou alterando o espelhamento SQL

Para remover o espelhamento SQL de um pool no Construtor de Topologias, primeiro use um cmdlet para remover o espelho no SQL Server. Em seguida, você poderá usar o Construtor de Topologias para remover o espelho da topologia. Para remover o espelho no SQL Server, use o cmdlet a seguir:

```powershell
Uninstall-CsMirrorDatabase -SqlServerFqdn <SQLServer FQDN> [-SqlInstanceName <SQLServer instance name>] -DatabaseType <Application | Archiving | CentralMgmt | Monitoring | User | BIStaging | PersistentChat | PersistentChatCompliance> [-DropExistingDatabasesOnMirror] [-Verbose]
```

Por exemplo, para remover o espelhamento e descartar os bancos de dados de usuários, digite:

```powershell
Uninstall-CsMirrorDatabase -SqlServerFqdn primaryBE.contoso.com -SqlInstanceName rtc -Verbose -DatabaseType User -DropExistingDatabasesOnMirror
```

A  `-DropExistingDatabasesOnMirror` opção faz com que os bancos de dados afetados sejam excluídos do espelho.

Em seguida, para remover o espelho da topologia, faça o seguinte:

1. No Construtor de Topologias, clique com o botão direito do mouse no pool e em **Editar Propriedades**

2. Desmarque **Habilitar Espelhamento do Repositório do SQL** e clique em **OK**.

3. Publique a topologia.

## <a name="removing-a-mirroring-witness"></a>Removendo a testemunha de espelhamento

Use este procedimento se precisar remover a testemunha de uma configuração de espelhamento do Servidor Back-End.

1. No Construtor de Topologias, clique com o botão direito do mouse no pool e em **Editar Propriedades**

2. Desmarque **Usar testemunha de espelhamento do SQL Server para habilitar failover automático** e clique em **OK**.

3. Publique a topologia.

    Depois de publicar a topologia, o Construtor de Topologias verá uma mensagem que inclui o seguinte

   ```console
   Run the Uninstall-CsMirrorDatabase cmdlet to remove databases that are paired with following primary databases.
   ```

    No entanto, não siga essa etapa e não digite como  `Uninstall-CsMirrorDatabase` se isso desinstale toda a configuração de espelhamento.

4. Para remover apenas a testemunha da configuração SQL Server, siga as instruções em [Remove the Witness from a Database Mirroring Session (SQL Server)](/sql/database-engine/database-mirroring/remove-the-witness-from-a-database-mirroring-session-sql-server).