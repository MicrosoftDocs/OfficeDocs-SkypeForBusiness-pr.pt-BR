---
title: 'Lync Server 2013: Instalação de banco de dados usando o Shell de Gerenciamento do Lync Server'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Database installation using Lync Server Management Shell
ms:assetid: c90a6449-4dd5-4b18-b21c-ea2c2a64dc3c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398832(v=OCS.15)
ms:contentKeyID: 48185401
ms.date: 06/16/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: deac68fb5f20066632bc48a9e9b6244a9bd34fe9
ms.sourcegitcommit: 30ed4457d7004ba732372fee11a6f0b1baf48e05
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/08/2020
ms.locfileid: "40971174"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="database-installation-using-lync-server-management-shell-in-lync-server-2013"></a>Instalação de banco de dados usando o Shell de Gerenciamento do Lync Server no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2016-06-16_

A separação de funções e responsabilidades entre os administradores do servidor e os administradores do SQL Server podem resultar em atrasos na implementação. O Lync Server 2013 usa o controle de acesso baseado em função (RBAC) para atenuar essas dificuldades. Em alguns casos, o administrador do SQL Server deve gerenciar a instalação de bancos de dados no servidor baseado no SQL Server fora de RBAC. O Shell de gerenciamento do Lync Server 2013 fornece uma maneira para o administrador do SQL Server executar cmdlets do Windows PowerShell projetados para configurar os bancos de dados com os dados e arquivos de log corretos. Para obter detalhes, consulte [permissões de implantação do SQL Server no Lync Server 2013](lync-server-2013-deployment-permissions-for-sql-server.md).

<div class=" ">


> [!IMPORTANT]  
> O procedimento a seguir pressupõe que pelo menos o Lync Server 2013 OCSCore. msi, o cliente nativo do SQL Server (sqlncli. msi) objetos de gerenciamento do Microsoft SQL Server 2012, tipos CLR para Microsoft SQL Server 2012 e Microsoft SQL Server 2012 ADOMD.NET sejam instalados. O OCSCore. msi está localizado na mídia de instalação no diretório \Setup\AMD64\Setup. Os componentes restantes estão localizados no \setup\amd64. Além disso, a preparação do Active Directory para o Lync Server 2013 foi concluída com êxito.



</div>

**Install-CsDatabase** é o cmdlet do Windows PowerShell usado para instalar os bancos de dados. O cmdlet **install-CsDatabase** tem um grande número de parâmetros, apenas alguns são discutidos aqui. Para obter detalhes sobre os parâmetros possíveis, consulte a documentação do Shell de gerenciamento do Lync Server 2013.

<div class=" ">


> [!WARNING]  
> Para evitar o desempenho e possíveis problemas de tempo limite, use sempre os FQDNs (nomes de domínio totalmente qualificados) ao se referir a servidores baseados no SQL Server. Evite o uso de referências somente a nomes de host. Por exemplo, use sqlbe01.contoso.net, mas evite usar SQLBE01.



</div>

Para a instalação de bancos de dados, **install-CsDatabase** usa três métodos principais para colocar os bancos de dados no servidor do SQL Server preparado:

  - Execute **install-CsDatabase** sem databasepaths ou UseDefaultSqlPath. O cmdlet usa um algoritmo interno para determinar o melhor posicionamento para os arquivos de log e de dados. O algoritmo só funciona em implementações de SQL Server autônomos.

  - Execute **install-CsDatabase** com o parâmetro databasepaths. O algoritmo interno para otimizar locais de arquivos de log e dados não será usado se o parâmetro databasepaths for definido. Usar esse parâmetro permite que você defina os locais onde os arquivos de log e de dados serão implantados.

  - Execute **install-CsDatabase** com UseDefaultSqlPaths. Essa opção não usa o algoritmo interno para otimizar os locais dos arquivos de log e de dados. O log e o arquivo de dados são implantados de acordo com os padrões definidos pelo administrador do SQL Server. Esses caminhos geralmente são definidos para a finalidade da Administração automática de arquivos de log e de dados no SQL Server com antecedência e não são associados à configuração do Lync Server 2013.

  - O parâmetro DatabasePathMap também pode ser usado para especificar explicitamente um local para cada banco de dados e seu respectivo arquivo de log.

<div>

## <a name="to-use-windows-powershell-cmdlets-to-configure-the-sql-server-central-management-store"></a>Para usar cmdlets do Windows PowerShell para configurar o repositório de gerenciamento central do SQL Server

1.  Em qualquer computador, faça logon com credenciais administrativas para criar bancos de dados no servidor baseado no SQL Server. Para obter detalhes, consulte [permissões de implantação do SQL Server no Lync Server 2013](lync-server-2013-deployment-permissions-for-sql-server.md).

2.  Abra o Shell de gerenciamento do Lync Server 2013. Se você não tiver ajustado a política de execução do Windows PowerShell, será necessário ajustar a política para permitir que os scripts do Windows PowerShell sejam executados. Para obter detalhes, consulte "examinando a política de [http://go.microsoft.com/fwlink/p/?linkId=203093](http://go.microsoft.com/fwlink/p/?linkid=203093)execução" em.

3.  Use o cmdlet **install-CsDatabase** para instalar o repositório de gerenciamento central.
    
       ```powershell
        Install-CsDatabase -CentralManagementDatabase -SqlServerFqdn <fully qualified domain name of SQL Server> 
        -SqlInstanceName <named instance> -DatabasePaths <logfile path>,<database file path> 
        -Report <path to report file>
       ```
    
       ```powershell
        Install-CsDatabase -CentralManagementDatabase -SqlServerFqdn sqlbe.contoso.net -SqlInstanceName rtc -DatabasePaths "C:\CSDB-Logs","C:\CSDB-CMS" -Report "C:\Logs\InstallDatabases.html"
       ```
    
    <div class=" ">
    

    > [!TIP]  
    > O parâmetro relatório é opcional, mas é útil se você está documentando o processo de instalação.

    
    </div>

4.  **Install-CsDatabase – Databasepaths** podem usar até seis parâmetros de caminho, cada um definindo os caminhos para as unidades definidas nos dados do SQL Server e na colocação de arquivos de log. Pelas regras lógicas da configuração de banco de dados no Lync Server 2013, as unidades são analisadas em buckets de duas, quatro ou seis. Dependendo da configuração do SQL Server e do número de buckets, você fornecerá dois caminhos, quatro caminhos ou seis caminhos.
    
    Se você tiver três unidades, o log terá prioridade e os arquivos de dados serão distribuídos após. Um exemplo de um servidor baseado em SQL Server configurado com seis unidades:
    ```powershell
    Install-CsDatabase -ConfiguredDatases -SqlServerFqdn sqlbe.contoso.net -DatabasePaths "D:\CSDynLogs","E:\CSRtcLogs","F:\MonCdrArcLogs","G:\MonCdrArchData","H:\AbsAppLog","I:\DynRtcAbsAppData" -Report "C:\Logs\InstallDatabases.html"
    ```
5.  Quando a instalação do banco de dados é concluída, você pode fechar o Shell de gerenciamento do Lync Server 2013 ou prosseguir para a instalação dos bancos de dados configurados do Lync Server 2013 definidos no construtor de topologias.

</div>

<div>

## <a name="to-use-windows-powershell-cmdlets-to-configure-the-sql-server-topology-configured-databases"></a>Para usar cmdlets do Windows PowerShell para configurar os bancos de dados configurados para topologia do SQL Server

1.  Para instalar os bancos de dados do construtor de topologias configurados para o Lync Server 2013, o administrador do Lync Server 2013 deve publicar a topologia. Para obter detalhes, consulte [publicar a topologia no Lync Server 2013](lync-server-2013-publish-the-topology.md) na documentação de implantação.

2.  Em qualquer computador, faça logon com credenciais administrativas para criar bancos de dados no servidor baseado no SQL Server. Consulte o tópico [permissões de implantação do SQL Server no Lync Server 2013](lync-server-2013-deployment-permissions-for-sql-server.md).
    
    <div class=" ">
    

    > [!IMPORTANT]  
    > Para poder configurar os bancos de dados baseados no SQL Server, certifique-se de que a conta de administrador do SQL Server usada para executar as etapas descritas aqui também seja um membro do grupo Administradores do sistema (ou equivalente) no servidor que executa o SQL Server e que mantém o gerenciamento central Função de servidor. Isso é especialmente importante para verificar se há pools adicionais do Lync Server 2013 que exijam instalação ou configuração do banco de dados do SQL Server. Por exemplo, se você estiver implantando um segundo pool (pool02), mas a função de servidor de gerenciamento central estiver mantida pela pool01. O grupo sysadmin do SQL Server (ou equivalente) deve ter permissões em bancos de dados baseados no SQL Server.

    
    </div>

3.  Abra o Shell de gerenciamento do Lync Server 2013, se ele ainda não estiver aberto.

4.  Use o cmdlet **install-CsDatabase** para instalar os bancos de dados do construtor de topologias configurados.
    
       ```powershell
        Install-CsDatabase -ConfiguredDatabases -SqlServerFqdn <fully qualified domain name of SQL Server> 
         -DatabasePaths <logfile path>,<database file path> -Report <path to report file>
       ```
    
       ```powershell
        Install-CsDatabase -ConfiguredDatabases -SqlServerFqdn sqlbe.contoso.net 
        -Report "C:\Logs\InstallDatabases.html"
       ```
    
    <div class=" ">
    

    > [!TIP]  
    > O parâmetro relatório é opcional, mas é útil se você está documentando o processo de instalação.

    
    </div>

5.  Quando a instalação do banco de dados for concluída, feche o Shell de gerenciamento do Lync Server 2013.

</div>

<div>

## <a name="to-use-windows-powershell-cmdlets-to-configure-the-sql-server-topology-using-the-databasepathmap-parameter"></a>Para usar cmdlets do Windows PowerShell para configurar a topologia do SQL Server usando o parâmetro DatabasePathMap

1.  Para instalar bancos de dados do Lync Server 2013, o administrador do Lync Server deve criar os caminhos e implantar os arquivos de banco de dados e os arquivos de log de acordo com um conjunto de regras predefinido.

2.  Em qualquer computador, faça logon com credenciais administrativas para criar bancos de dados no servidor baseado no SQL Server. Consulte o tópico [permissões de implantação do SQL Server no Lync Server 2013](lync-server-2013-deployment-permissions-for-sql-server.md).
    
    <div class=" ">
    

    > [!IMPORTANT]  
    > Para poder configurar os bancos de dados baseados no SQL Server, certifique-se de que a conta de administrador do SQL Server usada para executar as etapas descritas aqui também seja um membro do grupo Administradores do sistema (ou equivalente) no servidor que executa o SQL Server e que mantém o gerenciamento central Função de servidor. Isso é especialmente importante para verificar se há outros pools do Lync Server que exijam instalação ou configuração do banco de dados do SQL Server. Por exemplo, se você estiver implantando um segundo pool (pool02), mas a função de servidor de gerenciamento central estiver mantida pela pool01. O grupo sysadmin do SQL Server (ou equivalente) deve ter permissões em bancos de dados baseados no SQL Server.

    
    </div>

3.  Abra o Shell de gerenciamento do Lync Server, se ele ainda não estiver aberto.

4.  Use o cmdlet **install-CsDatabase** com o parâmetro DatabasePathMap e uma tabela de hash do PowerShell para instalar os bancos de dados do construtor de topologias configurados.

5.  No código de exemplo, os caminhos definidos para os bancos de dados podem ser determinados de uma maneira granular usando-se o parâmetro – DatabasePathMap e uma tabela de hash definida da seguinte maneira (o exemplo\\usa "c: CSData" para todos os arquivos de banco de dados (\\. MDF) e "C: CSLogFiles" para todos os arquivos de log (. ldf). A pasta será criada conforme necessário pelo install-CsDatabase):
    ```powershell
    $pathmap = @{
    "BackendStore:BlobStore:DbPath"="C:\CsData";"BackendStore:BlobStore:LogPath"="C:\CsLogFiles"
    "BackendStore:RtcSharedDatabase:DbPath"="C:\CsData";"BackendStore:RtcSharedDatabase:LogPath"="C:\CsLogFiles"
    "ABSStore:AbsDatabase:DbPath"="C:\CsData";"ABSStore:AbsDatabase:LogPath"="C:\CsLogFiles"
    "ApplicationStore:RgsConfigDatabase:DbPath"="C:\CsData";"ApplicationStore:RgsConfigDatabase:LogPath"="C:\CsLogFiles"
    "ApplicationStore:RgsDynDatabase:DbPath"="C:\CsData";"ApplicationStore:RgsDynDatabase:LogPath"="C:\CsLogFiles"
    "ApplicationStore:CpsDynDatabase:DbPath"="C:\CsData";"ApplicationStore:CpsDynDatabase:LogPath"="C:\CsLogFiles"
    "ArchivingStore:ArchivingDatabase:DbPath"="C:\CsData";"ArchivingStore:ArchivingDatabase:LogPath"="C:\CsLogFiles"
    "MonitoringStore:MonitoringDatabase:DbPath"="C:\CsData";"MonitoringStore:MonitoringDatabase:LogPath"="C:\CsLogFiles"
    "MonitoringStore:QoEMetricsDatabase:DbPath"="C:\CsData";"MonitoringStore:QoEMetricsDatabase:LogPath"="C:\CsLogFiles"
    }
    Install-CsDatabase -ConfigureDatabases -SqlServerFqdn sqlbe01.contoso.net -DatabasePathMap $pathmap
    ```
6.  Como o banco de dados e os arquivos de log são explicitamente nomeados com sua localização no servidor de banco de dados de destino, você pode definir locais específicos para cada tipo de serviço de banco de dados real e local de log. O exemplo a seguir coloca os bancos de dados de cada tipo de serviço específico em discos separados e os arquivos de log associados em outro. Por exemplo:
    
      - Todos os bancos de dados RTC para "D\\: RTCDatabase"
    
      - Todos os arquivos de log RTC para "\\E: RTCLogs"
    
      - Todos os bancos de dados da loja de aplicativos para\\"F: CPSDatabases"
    
      - Todos os logs da loja de aplicativos para\\"G: CPSLogs"
    
      - Todos os bancos de dados de repositório do grupo de resposta\\para "H: RGSDatabases"
    
      - Todos os logs do repositório do grupo de resposta\\para "I: RGSLogs"
    
      - Todos os bancos de dados do catálogo de endereços para "\\J: ABSDatabases"
    
      - Todos os arquivos de registro do repositório de endereços para\\"K: ABSLogs"
    
      - Todos os bancos de dados do arquivamento da loja para\\"L: ArchivingDatabases"
    
      - Todos os logs do repositório de arquivamento para\\"M: ArchivingLogs"
    
      - Todos os bancos de dados da loja de monitoramento para\\"N: MonitoringDatabases"
    
      - Todos os arquivos de log da loja de monitoramento\\para "O: MonitoringLogfiles"
    
    <!-- end list -->
    
    ```powershell    
    $pathmap = @{
    "BackendStore:BlobStore:DbPath"="D:\RTCDatabase";"BackendStore:BlobStore:LogPath"="E:\RTCLogs"
    "BackendStore:RtcSharedDatabase:DbPath"="D:\RTCDatabase";"BackendStore:RtcSharedDatabase:LogPath"="E:\RTCLogs"
    "ABSStore:AbsDatabase:DbPath"="J:\ABSDatabases";"ABSStore:AbsDatabase:LogPath"="K:\ABSLogs"
    "ApplicationStore:RgsConfigDatabase:DbPath"="H:\RGSDatabases";"ApplicationStore:RgsConfigDatabase:LogPath"="G:\CPSLogs"
    "ApplicationStore:RgsDynDatabase:DbPath"="H:\RGSDatabases";"ApplicationStore:RgsDynDatabase:LogPath"="I:\RGSLogs"
    "ApplicationStore:CpsDynDatabase:DbPath"="F:\CPSDatabases";"ApplicationStore:CpsDynDatabase:LogPath"="G:\CsLogFiles"
    "ArchivingStore:ArchivingDatabase:DbPath"="M:\ArchivingLogs";"ArchivingStore:ArchivingDatabase:LogPath"="N:\MonitoringDatabases"
    "MonitoringStore:MonitoringDatabase:DbPath"="N:\MonitoringDatabases";"MonitoringStore:MonitoringDatabase:LogPath"="O:\MonitoringLogfiles"
    "MonitoringStore:QoEMetricsDatabase:DbPath"="N:\MonitoringDatabases";"MonitoringStore:QoEMetricsDatabase:LogPath"="O:\MonitoringLogfiles"
    }
    
    Install-CsDatabase -ConfiguredDatabases -SqlServerFqdn sqlbe01.contoso.net -DatabasePathMap $pathmap
    ```
    
    Usando o parâmetro – DatabasePathMap, você pode definir qualquer combinação de mapeamento de letras de unidade lógica que forneça a melhor solução para seus requisitos de desempenho e posicionamento do SQL Server.

Se você configurar seus arquivos de dados de banco de dados e arquivos de log usando o método **DatabasePathMap** , será necessário fazer uma pequena alteração no processo normal ao usar o construtor de topologias. Normalmente, você define suas opções de topologia, publica a topologia e escolhe implantar as seleções de banco de dados.

Se você usou o **DatabasePathMap** , já realizou a terceira parte do processo do construtor de topologias. No caso de ter um servidor de banco de dados completamente configurado antes do construtor de topologias em execução, você ainda pode definir todas as suas opções e funções de servidor, mas desmarque a opção para criar os bancos de dados.

</div>

</div>

<span> </span>

</div>

</div>

</div>

