---
title: 'Lync Server 2013: instalação de banco de dados usando o Shell de gerenciamento do Lync Server'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Database installation using Lync Server Management Shell
ms:assetid: c90a6449-4dd5-4b18-b21c-ea2c2a64dc3c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398832(v=OCS.15)
ms:contentKeyID: 48185401
ms.date: 06/16/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b602e29e0f90a49a031c25d6bb919337bef87b8d
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48516538"
---
# <a name="database-installation-using-lync-server-management-shell-in-lync-server-2013"></a>Instalação de banco de dados usando o Shell de gerenciamento do Lync Server no Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2016-06-16_

A separação de funções e responsabilidades entre administradores de servidor e administradores do SQL Server pode resultar em atrasos na implementação. O Lync Server 2013 usa o controle de acesso baseado em função (RBAC) para reduzir essas dificuldades. Em algumas instâncias, o administrador do SQL Server deverá gerenciar a instalação de bancos de dados no servidor baseado em SQL Server fora do RBAC. O Shell de gerenciamento do Lync Server 2013 oferece uma maneira de o administrador do SQL Server executar os cmdlets do Windows PowerShell projetados para configurar os bancos de dados com os arquivos de dados e de log corretos. Para obter detalhes, consulte [Deployment Permissions for SQL Server in Lync server 2013](lync-server-2013-deployment-permissions-for-sql-server.md).

<div class=" ">


> [!IMPORTANT]  
> O procedimento a seguir pressupõe que, no mínimo, o Lync Server 2013 OCSCore.msi, os objetos de gerenciamento do SQL Server Native Client (sqlncli.msi) Microsoft SQL Server 2012, tipos CLR para Microsoft SQL Server 2012 e Microsoft SQL Server 2012 ADOMD.NET estão instalados. O OCSCore.msi está localizado na mídia de instalação, no diretório \Setup\AMD64\Setup. Os componentes restantes estão localizados no \setup\amd64. Além disso, a preparação do Active Directory para o Lync Server 2013 foi concluída com êxito.



</div>

**Install-CsDatabase** é o cmdlet do Windows PowerShell que você usa para instalar os bancos de dados. O cmdlet **Install-CsDatabase** tem muitos parâmetros, somente alguns deles são discutidos aqui. Para obter detalhes sobre os parâmetros possíveis, consulte a documentação do Shell de gerenciamento do Lync Server 2013.

<div class=" ">


> [!WARNING]  
> Para evitar possíveis problemas de tempo limite e de desempenho, sempre use os FQDNs (nomes de domínio totalmente qualificados) ao se referir aos servidores baseados no SQL Server. Evite usar referências somente ao nome do host. Por exemplo, use sqlbe01.contoso.net, mas evite usar o SQLBE01.



</div>

Para a instalação de bancos de dados, **install-CsDatabase** usa três métodos principais para colocar os bancos de dados no servidor baseado em SQL Server preparado:

  - Execute o **Install-CsDatabase** sem DatabasePaths ou UseDefaultSqlPath. O cmdlet usa um algoritmo integrado para determinar o melhor posicionamento dos arquivos de log e de dados. O algoritmo só funciona para implementações autônomas do SQL Server.

  - Execute **Install-CsDatabase** com o parâmetro DatabasePaths. O algoritmo integrado para otimizar os locais de arquivo de log e de dados não é usado se o parâmetro DatabasePaths for definido. O uso desse parâmetro permite que você defina os locais onde os arquivos de log e de dados serão implantados.

  - Execute **Install-CsDatabase** com UseDefaultSqlPaths. Essa opção não usar o algoritmo integrado para otimizar os locais do arquivo de log e de dados. Os arquivos de log e de dados são implantados de acordo com os padrões definidos pelo administrador do SQL Server. Esses caminhos são normalmente definidos para a finalidade da Administração automática de arquivos de log e dados no SQL Server com antecedência e não estão associados à configuração do Lync Server 2013.

  - O parâmetro DatabasePathMap também pode ser usado para especificar explicitamente um local para cada banco de dados e seu respectivo arquivo de log.

<div>

## <a name="to-use-windows-powershell-cmdlets-to-configure-the-sql-server-central-management-store"></a>Para usar os cmdlets do Windows PowerShell para configurar o repositório de Gerenciamento central do SQL Server

1.  Em qualquer computador, faça logon com credenciais administrativas para a criação dos bancos de dados no servidor baseado em SQL Server. Para obter detalhes, consulte [Deployment Permissions for SQL Server in Lync server 2013](lync-server-2013-deployment-permissions-for-sql-server.md).

2.  Abra o Shell de gerenciamento do Lync Server 2013. Se você não tiver ajustado a política de execução do Windows PowerShell, você deve ajustar a política para permitir que scripts do Windows PowerShell sejam executados. Para obter detalhes, consulte "examinando a política de execução" em [https://go.microsoft.com/fwlink/p/?linkId=203093](https://go.microsoft.com/fwlink/p/?linkid=203093) .

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
    > O parâmetro Report é opcional, mas é útil se você estiver documentando o processo de instalação.

    
    </div>

4.  **Install-CsDatabase – Databasepaths** podem usar até seis parâmetros de caminho, cada um definindo os caminhos para as unidades, conforme definido nos dados do SQL Server e no posicionamento do arquivo de log. Pelas regras lógicas da configuração do banco de dados no Lync Server 2013, as unidades são analisadas em buckets de dois, quatro ou seis. Dependendo da configuração do SQL Server e do número de buckets, você fornecerá dois caminhos, quatro caminhos ou seis caminhos.
    
    Se você tiver três unidades, o log terá prioridade e os arquivos de dados serão distribuídos em seguida. Um exemplo para um servidor baseado em SQL Server configurado com seis unidades:
    ```powershell
    Install-CsDatabase -ConfiguredDatases -SqlServerFqdn sqlbe.contoso.net -DatabasePaths "D:\CSDynLogs","E:\CSRtcLogs","F:\MonCdrArcLogs","G:\MonCdrArchData","H:\AbsAppLog","I:\DynRtcAbsAppData" -Report "C:\Logs\InstallDatabases.html"
    ```
5.  Quando a instalação do banco de dados for concluída, você poderá fechar o Shell de gerenciamento do Lync Server 2013 ou prosseguir para a instalação dos bancos de dados configurados do Lync Server 2013 definidos no construtor de topologias.

</div>

<div>

## <a name="to-use-windows-powershell-cmdlets-to-configure-the-sql-server-topology-configured-databases"></a>Para usar os cmdlets do Windows PowerShell para configurar os bancos de dados configurados pela topologia do SQL Server

1.  Para instalar os bancos de dados configurados do construtor de topologia para o Lync Server 2013, o administrador do Lync Server 2013 deve publicar a topologia. Para obter detalhes, consulte [publish the Topology in Lync Server 2013](lync-server-2013-publish-the-topology.md) na documentação de implantação.

2.  Em qualquer computador, faça logon com credenciais administrativas para a criação dos bancos de dados no servidor baseado em SQL Server. Consulte o tópico, [Deployment Permissions for SQL Server in Lync server 2013](lync-server-2013-deployment-permissions-for-sql-server.md).
    
    <div class=" ">
    

    > [!IMPORTANT]  
    > Para poder configurar os bancos de dados baseados em SQL Server, certifique-se de que a conta de administrador do SQL Server usada para executar as etapas descritas aqui também é membro do grupo sysadmins (ou equivalente) no servidor que executa o SQL Server e que mantém a função de servidor de gerenciamento central. Isso é especialmente importante para verificar qualquer pool adicional do Lync Server 2013 que exija instalação ou configuração de banco de dados do SQL Server. Por exemplo, se você estiver implantando um segundo pool (pool02), mas a função de servidor de gerenciamento central for mantida pelo pool01. O grupo sysadmin do SQL Server (ou equivalente) deve ter permissões em ambos os bancos de dados baseados no SQL Server.

    
    </div>

3.  Abra o Shell de gerenciamento do Lync Server 2013, se ainda não estiver aberto.

4.  Use o cmdlet **install-CsDatabase** para instalar os bancos de dados configurados do construtor de topologias.
    
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
    > O parâmetro Report é opcional, mas é útil se você estiver documentando o processo de instalação.

    
    </div>

5.  Quando a instalação do banco de dados for concluída, feche o Shell de gerenciamento do Lync Server 2013.

</div>

<div>

## <a name="to-use-windows-powershell-cmdlets-to-configure-the-sql-server-topology-using-the-databasepathmap-parameter"></a>Para usar os cmdlets do Windows PowerShell para configurar a topologia do SQL Server usando o parâmetro DatabasePathMap

1.  Para instalar os bancos de dados do Lync Server 2013, o administrador do Lync Server deve criar os caminhos e implantar os arquivos de banco de dados e os arquivos de log de acordo com um conjunto predefinido de regras.

2.  Em qualquer computador, faça logon com credenciais administrativas para a criação dos bancos de dados no servidor baseado em SQL Server. Consulte o tópico, [Deployment Permissions for SQL Server in Lync server 2013](lync-server-2013-deployment-permissions-for-sql-server.md).
    
    <div class=" ">
    

    > [!IMPORTANT]  
    > Para poder configurar os bancos de dados baseados em SQL Server, certifique-se de que a conta de administrador do SQL Server usada para executar as etapas descritas aqui também é membro do grupo sysadmins (ou equivalente) no servidor que executa o SQL Server e que mantém a função de servidor de gerenciamento central. Isso é especialmente importante para verificar qualquer pool adicional do Lync Server que exija instalação ou configuração de banco de dados do SQL Server. Por exemplo, se você estiver implantando um segundo pool (pool02), mas a função de servidor de gerenciamento central for mantida pelo pool01. O grupo sysadmin do SQL Server (ou equivalente) deve ter permissões em ambos os bancos de dados baseados no SQL Server.

    
    </div>

3.  Abra o Shell de gerenciamento do Lync Server, se ainda não estiver aberto.

4.  Use o cmdlet **install-CsDatabase** com o parâmetro DatabasePathMap e uma tabela de hash do PowerShell para instalar os bancos de dados configurados do construtor de topologias.

5.  No código de exemplo, os caminhos definidos para os bancos de dados podem ser determinados de uma maneira granular usando o parâmetro – DatabasePathMap e uma tabela de hash definida da seguinte maneira (o exemplo usa "C: \\ CSData" para todos os arquivos de banco de dados (. MDF) e "c: \\ CSLogFiles" para todos os arquivos de log (. ldf). A pasta será criada conforme necessário pelo install-CsDatabase):
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
6.  Como o banco de dados e os arquivos de log são nomeados explicitamente com seu local no servidor de banco de dados de destino, você pode definir locais específicos para cada tipo de serviço de banco de dados real e local de log. O exemplo a seguir coloca os bancos de dados de cada tipo de serviço específico em discos separados e os arquivos de log associados em outro. Por exemplo:
    
      - Todos os bancos de dados RTC para "D: \\ RTCDatabase"
    
      - Todos os arquivos de log RTC para "E: \\ RTCLogs"
    
      - Todos os bancos de dados de repositório de aplicativos para "F: \\ CPSDatabases"
    
      - Todos os logs de repositório de aplicativos para "G: \\ CPSLogs"
    
      - Todos os bancos de dados do repositório de grupos de resposta para "H: \\ RGSDatabases"
    
      - Todos os logs do repositório de resposta do grupo para "I: \\ RGSLogs"
    
      - Todos os bancos de dados do repositório de catálogo de endereços para "J: \\ ABSDatabases"
    
      - Todos os arquivos de log do repositório de catálogo de endereços para "K: \\ ABSLogs"
    
      - Todos os bancos de dados de repositório de arquivamento para "L: \\ ArchivingDatabases"
    
      - Todos os logs do repositório de arquivamento para "M: \\ ArchivingLogs"
    
      - Todos os bancos de dados de repositório de monitoramento para "N: \\ MonitoringDatabases"
    
      - Todos os arquivos de log do repositório de monitoramento para "O: \\ MonitoringLogfiles"
    
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
    
    Usando o parâmetro – DatabasePathMap, você pode definir qualquer combinação de mapeamento de letra de unidade lógica que forneça a melhor solução para seus requisitos de desempenho e posicionamento do SQL Server.

Se você configurar seus arquivos de dados de banco de dados e arquivos de log usando o método **DatabasePathMap** , será necessário fazer uma pequena alteração no seu processo normal ao usar o construtor de topologias. Normalmente, você deve definir as opções de topologia, publicar a topologia e optar por implantar as seleções de banco de dados.

Se você usou o **DatabasePathMap** , já realizou a terceira parte do processo do construtor de topologias. No caso de ter um servidor de banco de dados completamente configurado com antecedência da execução do construtor de topologias, você ainda pode definir todas as suas funções e opções de servidor, mas desmarque a opção para criar os bancos de dados.

</div>

</div>

<span> </span>

</div>

</div>

</div>

