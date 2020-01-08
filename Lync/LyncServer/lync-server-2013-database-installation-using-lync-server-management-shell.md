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

# <a name="database-installation-using-lync-server-management-shell-in-lync-server-2013"></a><span data-ttu-id="4deef-102">Instalação de banco de dados usando o Shell de Gerenciamento do Lync Server no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4deef-102">Database installation using Lync Server Management Shell in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4deef-103">_**Tópico da última modificação:** 2016-06-16_</span><span class="sxs-lookup"><span data-stu-id="4deef-103">_**Topic Last Modified:** 2016-06-16_</span></span>

<span data-ttu-id="4deef-104">A separação de funções e responsabilidades entre os administradores do servidor e os administradores do SQL Server podem resultar em atrasos na implementação.</span><span class="sxs-lookup"><span data-stu-id="4deef-104">Separation of roles and responsibilities between server administrators and SQL Server administrators can result in delays in implementation.</span></span> <span data-ttu-id="4deef-105">O Lync Server 2013 usa o controle de acesso baseado em função (RBAC) para atenuar essas dificuldades.</span><span class="sxs-lookup"><span data-stu-id="4deef-105">Lync Server 2013 uses role-based access control (RBAC) to mitigate these difficulties.</span></span> <span data-ttu-id="4deef-106">Em alguns casos, o administrador do SQL Server deve gerenciar a instalação de bancos de dados no servidor baseado no SQL Server fora de RBAC.</span><span class="sxs-lookup"><span data-stu-id="4deef-106">In some instances, the SQL Server administrator must manage the installation of databases on the SQL Server-based server outside RBAC.</span></span> <span data-ttu-id="4deef-107">O Shell de gerenciamento do Lync Server 2013 fornece uma maneira para o administrador do SQL Server executar cmdlets do Windows PowerShell projetados para configurar os bancos de dados com os dados e arquivos de log corretos.</span><span class="sxs-lookup"><span data-stu-id="4deef-107">The Lync Server 2013 Management Shell provides a way for the SQL Server administrator to run Windows PowerShell cmdlets designed to configure the databases with the correct data and log files.</span></span> <span data-ttu-id="4deef-108">Para obter detalhes, consulte [permissões de implantação do SQL Server no Lync Server 2013](lync-server-2013-deployment-permissions-for-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="4deef-108">For details, see [Deployment permissions for SQL Server in Lync Server 2013](lync-server-2013-deployment-permissions-for-sql-server.md).</span></span>

<div class=" ">


> [!IMPORTANT]  
> <span data-ttu-id="4deef-109">O procedimento a seguir pressupõe que pelo menos o Lync Server 2013 OCSCore. msi, o cliente nativo do SQL Server (sqlncli. msi) objetos de gerenciamento do Microsoft SQL Server 2012, tipos CLR para Microsoft SQL Server 2012 e Microsoft SQL Server 2012 ADOMD.NET sejam instalados.</span><span class="sxs-lookup"><span data-stu-id="4deef-109">The following procedure assumes that at a minimum the Lync Server 2013 OCSCore.msi, SQL Server Native Client (sqlncli.msi) Microsoft SQL Server 2012 Management Objects, CLR Types for Microsoft SQL Server 2012 and Microsoft SQL Server 2012 ADOMD.NET are installed.</span></span> <span data-ttu-id="4deef-110">O OCSCore. msi está localizado na mídia de instalação no diretório \Setup\AMD64\Setup.</span><span class="sxs-lookup"><span data-stu-id="4deef-110">The OCSCore.msi is located on the installation media in the \Setup\AMD64\Setup directory.</span></span> <span data-ttu-id="4deef-111">Os componentes restantes estão localizados no \setup\amd64.</span><span class="sxs-lookup"><span data-stu-id="4deef-111">The remaining components are located in \Setup\amd64.</span></span> <span data-ttu-id="4deef-112">Além disso, a preparação do Active Directory para o Lync Server 2013 foi concluída com êxito.</span><span class="sxs-lookup"><span data-stu-id="4deef-112">Additionally, Active Directory preparation for Lync Server 2013 has been successfully completed.</span></span>



</div>

<span data-ttu-id="4deef-113">**Install-CsDatabase** é o cmdlet do Windows PowerShell usado para instalar os bancos de dados.</span><span class="sxs-lookup"><span data-stu-id="4deef-113">**Install-CsDatabase** is the Windows PowerShell cmdlet you use to install the databases.</span></span> <span data-ttu-id="4deef-114">O cmdlet **install-CsDatabase** tem um grande número de parâmetros, apenas alguns são discutidos aqui.</span><span class="sxs-lookup"><span data-stu-id="4deef-114">The **Install-CsDatabase** cmdlet has a large number of parameters, only a few of which are discussed here.</span></span> <span data-ttu-id="4deef-115">Para obter detalhes sobre os parâmetros possíveis, consulte a documentação do Shell de gerenciamento do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="4deef-115">For details about the possible parameters, see the Lync Server 2013 Management Shell documentation.</span></span>

<div class=" ">


> [!WARNING]  
> <span data-ttu-id="4deef-116">Para evitar o desempenho e possíveis problemas de tempo limite, use sempre os FQDNs (nomes de domínio totalmente qualificados) ao se referir a servidores baseados no SQL Server.</span><span class="sxs-lookup"><span data-stu-id="4deef-116">To avoid performance and possible time-out issues, always use fully qualified domain names (FQDNs) when referring to SQL Server-based servers.</span></span> <span data-ttu-id="4deef-117">Evite o uso de referências somente a nomes de host.</span><span class="sxs-lookup"><span data-stu-id="4deef-117">Avoid using host name-only references.</span></span> <span data-ttu-id="4deef-118">Por exemplo, use sqlbe01.contoso.net, mas evite usar SQLBE01.</span><span class="sxs-lookup"><span data-stu-id="4deef-118">For example, use sqlbe01.contoso.net, but avoid using SQLBE01.</span></span>



</div>

<span data-ttu-id="4deef-119">Para a instalação de bancos de dados, **install-CsDatabase** usa três métodos principais para colocar os bancos de dados no servidor do SQL Server preparado:</span><span class="sxs-lookup"><span data-stu-id="4deef-119">For installing databases, **Install-CsDatabase** uses three primary methods for placing the databases onto the prepared SQL Server-based server:</span></span>

  - <span data-ttu-id="4deef-120">Execute **install-CsDatabase** sem databasepaths ou UseDefaultSqlPath.</span><span class="sxs-lookup"><span data-stu-id="4deef-120">Run **Install-CsDatabase** without DatabasePaths or UseDefaultSqlPath.</span></span> <span data-ttu-id="4deef-121">O cmdlet usa um algoritmo interno para determinar o melhor posicionamento para os arquivos de log e de dados.</span><span class="sxs-lookup"><span data-stu-id="4deef-121">The cmdlet uses a built in algorithm to determine the best placement for the log and data files.</span></span> <span data-ttu-id="4deef-122">O algoritmo só funciona em implementações de SQL Server autônomos.</span><span class="sxs-lookup"><span data-stu-id="4deef-122">The algorithm only works for stand-alone SQL Server implementations.</span></span>

  - <span data-ttu-id="4deef-123">Execute **install-CsDatabase** com o parâmetro databasepaths.</span><span class="sxs-lookup"><span data-stu-id="4deef-123">Run **Install-CsDatabase** with the DatabasePaths parameter.</span></span> <span data-ttu-id="4deef-124">O algoritmo interno para otimizar locais de arquivos de log e dados não será usado se o parâmetro databasepaths for definido.</span><span class="sxs-lookup"><span data-stu-id="4deef-124">The built-in algorithm to optimize log and data file locations is not used if the DatabasePaths parameter is defined.</span></span> <span data-ttu-id="4deef-125">Usar esse parâmetro permite que você defina os locais onde os arquivos de log e de dados serão implantados.</span><span class="sxs-lookup"><span data-stu-id="4deef-125">Using this parameter allows you to define the locations where log and data files will be deployed.</span></span>

  - <span data-ttu-id="4deef-126">Execute **install-CsDatabase** com UseDefaultSqlPaths.</span><span class="sxs-lookup"><span data-stu-id="4deef-126">Run **Install-CsDatabase** with UseDefaultSqlPaths.</span></span> <span data-ttu-id="4deef-127">Essa opção não usa o algoritmo interno para otimizar os locais dos arquivos de log e de dados.</span><span class="sxs-lookup"><span data-stu-id="4deef-127">This option does not use the built-in algorithm to optimize the log and data file locations.</span></span> <span data-ttu-id="4deef-128">O log e o arquivo de dados são implantados de acordo com os padrões definidos pelo administrador do SQL Server.</span><span class="sxs-lookup"><span data-stu-id="4deef-128">Log and data file are deployed according to the defaults set by the SQL Server administrator.</span></span> <span data-ttu-id="4deef-129">Esses caminhos geralmente são definidos para a finalidade da Administração automática de arquivos de log e de dados no SQL Server com antecedência e não são associados à configuração do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="4deef-129">These paths are typically set for the purpose of automatic administration of log and data files on the SQL Server in advance, and are not associated with the setup of Lync Server 2013.</span></span>

  - <span data-ttu-id="4deef-130">O parâmetro DatabasePathMap também pode ser usado para especificar explicitamente um local para cada banco de dados e seu respectivo arquivo de log.</span><span class="sxs-lookup"><span data-stu-id="4deef-130">The DatabasePathMap parameter can also be used to explicitly specify a location for each database and its respective log file.</span></span>

<div>

## <a name="to-use-windows-powershell-cmdlets-to-configure-the-sql-server-central-management-store"></a><span data-ttu-id="4deef-131">Para usar cmdlets do Windows PowerShell para configurar o repositório de gerenciamento central do SQL Server</span><span class="sxs-lookup"><span data-stu-id="4deef-131">To use Windows PowerShell cmdlets to configure the SQL Server Central Management store</span></span>

1.  <span data-ttu-id="4deef-132">Em qualquer computador, faça logon com credenciais administrativas para criar bancos de dados no servidor baseado no SQL Server.</span><span class="sxs-lookup"><span data-stu-id="4deef-132">On any computer, log on with administrative credentials for creating the databases on the SQL Server-based server.</span></span> <span data-ttu-id="4deef-133">Para obter detalhes, consulte [permissões de implantação do SQL Server no Lync Server 2013](lync-server-2013-deployment-permissions-for-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="4deef-133">For details, see [Deployment permissions for SQL Server in Lync Server 2013](lync-server-2013-deployment-permissions-for-sql-server.md).</span></span>

2.  <span data-ttu-id="4deef-134">Abra o Shell de gerenciamento do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="4deef-134">Open the Lync Server 2013 Management Shell.</span></span> <span data-ttu-id="4deef-135">Se você não tiver ajustado a política de execução do Windows PowerShell, será necessário ajustar a política para permitir que os scripts do Windows PowerShell sejam executados.</span><span class="sxs-lookup"><span data-stu-id="4deef-135">If you have not adjusted the execution policy for Windows PowerShell, you must adjust the policy to allow Windows PowerShell scripts to run.</span></span> <span data-ttu-id="4deef-136">Para obter detalhes, consulte "examinando a política de [http://go.microsoft.com/fwlink/p/?linkId=203093](http://go.microsoft.com/fwlink/p/?linkid=203093)execução" em.</span><span class="sxs-lookup"><span data-stu-id="4deef-136">For details, see “Examining the Execution Policy” at [http://go.microsoft.com/fwlink/p/?linkId=203093](http://go.microsoft.com/fwlink/p/?linkid=203093).</span></span>

3.  <span data-ttu-id="4deef-137">Use o cmdlet **install-CsDatabase** para instalar o repositório de gerenciamento central.</span><span class="sxs-lookup"><span data-stu-id="4deef-137">Use the **Install-CsDatabase** cmdlet to install the Central Management store.</span></span>
    
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
    > <span data-ttu-id="4deef-138">O parâmetro relatório é opcional, mas é útil se você está documentando o processo de instalação.</span><span class="sxs-lookup"><span data-stu-id="4deef-138">The Report parameter is optional but is useful if you are documenting the installation process.</span></span>

    
    </div>

4.  <span data-ttu-id="4deef-139">**Install-CsDatabase – Databasepaths** podem usar até seis parâmetros de caminho, cada um definindo os caminhos para as unidades definidas nos dados do SQL Server e na colocação de arquivos de log.</span><span class="sxs-lookup"><span data-stu-id="4deef-139">**Install-CsDatabase –DatabasePaths** can use up to six path parameters, each defining the paths for the drives as defined in SQL Server Data and Log File Placement.</span></span> <span data-ttu-id="4deef-140">Pelas regras lógicas da configuração de banco de dados no Lync Server 2013, as unidades são analisadas em buckets de duas, quatro ou seis.</span><span class="sxs-lookup"><span data-stu-id="4deef-140">By the logical rules of the database configuration in Lync Server 2013, drives are parsed out into buckets of two, four, or six.</span></span> <span data-ttu-id="4deef-141">Dependendo da configuração do SQL Server e do número de buckets, você fornecerá dois caminhos, quatro caminhos ou seis caminhos.</span><span class="sxs-lookup"><span data-stu-id="4deef-141">Depending on your SQL Server configuration and the number of buckets, you will supply two paths, four paths, or six paths.</span></span>
    
    <span data-ttu-id="4deef-142">Se você tiver três unidades, o log terá prioridade e os arquivos de dados serão distribuídos após.</span><span class="sxs-lookup"><span data-stu-id="4deef-142">If you have three drives, the log gets priority and the data files are distributed after.</span></span> <span data-ttu-id="4deef-143">Um exemplo de um servidor baseado em SQL Server configurado com seis unidades:</span><span class="sxs-lookup"><span data-stu-id="4deef-143">An example for a SQL Server-based server configured with six drives:</span></span>
    ```powershell
    Install-CsDatabase -ConfiguredDatases -SqlServerFqdn sqlbe.contoso.net -DatabasePaths "D:\CSDynLogs","E:\CSRtcLogs","F:\MonCdrArcLogs","G:\MonCdrArchData","H:\AbsAppLog","I:\DynRtcAbsAppData" -Report "C:\Logs\InstallDatabases.html"
    ```
5.  <span data-ttu-id="4deef-144">Quando a instalação do banco de dados é concluída, você pode fechar o Shell de gerenciamento do Lync Server 2013 ou prosseguir para a instalação dos bancos de dados configurados do Lync Server 2013 definidos no construtor de topologias.</span><span class="sxs-lookup"><span data-stu-id="4deef-144">When the database installation completes, you can close Lync Server 2013 Management Shell or proceed to the installation of the Lync Server 2013 configured databases defined in Topology Builder.</span></span>

</div>

<div>

## <a name="to-use-windows-powershell-cmdlets-to-configure-the-sql-server-topology-configured-databases"></a><span data-ttu-id="4deef-145">Para usar cmdlets do Windows PowerShell para configurar os bancos de dados configurados para topologia do SQL Server</span><span class="sxs-lookup"><span data-stu-id="4deef-145">To use Windows PowerShell cmdlets to configure the SQL Server topology configured databases</span></span>

1.  <span data-ttu-id="4deef-146">Para instalar os bancos de dados do construtor de topologias configurados para o Lync Server 2013, o administrador do Lync Server 2013 deve publicar a topologia.</span><span class="sxs-lookup"><span data-stu-id="4deef-146">To install the Topology Builder configured databases for Lync Server 2013, the Lync Server 2013 administrator must publish the topology.</span></span> <span data-ttu-id="4deef-147">Para obter detalhes, consulte [publicar a topologia no Lync Server 2013](lync-server-2013-publish-the-topology.md) na documentação de implantação.</span><span class="sxs-lookup"><span data-stu-id="4deef-147">For details, see [Publish the topology in Lync Server 2013](lync-server-2013-publish-the-topology.md) in the Deployment documentation.</span></span>

2.  <span data-ttu-id="4deef-148">Em qualquer computador, faça logon com credenciais administrativas para criar bancos de dados no servidor baseado no SQL Server.</span><span class="sxs-lookup"><span data-stu-id="4deef-148">On any computer, log on with administrative credentials for creating the databases on the SQL Server-based server.</span></span> <span data-ttu-id="4deef-149">Consulte o tópico [permissões de implantação do SQL Server no Lync Server 2013](lync-server-2013-deployment-permissions-for-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="4deef-149">See the topic, [Deployment permissions for SQL Server in Lync Server 2013](lync-server-2013-deployment-permissions-for-sql-server.md).</span></span>
    
    <div class=" ">
    

    > [!IMPORTANT]  
    > <span data-ttu-id="4deef-150">Para poder configurar os bancos de dados baseados no SQL Server, certifique-se de que a conta de administrador do SQL Server usada para executar as etapas descritas aqui também seja um membro do grupo Administradores do sistema (ou equivalente) no servidor que executa o SQL Server e que mantém o gerenciamento central Função de servidor.</span><span class="sxs-lookup"><span data-stu-id="4deef-150">To be able to configure the SQL Server-based databases, make sure the SQL Server administrator account used to run the steps described here is also a member of the sysadmins group (or equivalent) on the server running SQL Server and holding the Central Management Server role.</span></span> <span data-ttu-id="4deef-151">Isso é especialmente importante para verificar se há pools adicionais do Lync Server 2013 que exijam instalação ou configuração do banco de dados do SQL Server.</span><span class="sxs-lookup"><span data-stu-id="4deef-151">This is especially important to check for any additional Lync Server 2013 pools which require SQL Server database installation or configuration.</span></span> <span data-ttu-id="4deef-152">Por exemplo, se você estiver implantando um segundo pool (pool02), mas a função de servidor de gerenciamento central estiver mantida pela pool01.</span><span class="sxs-lookup"><span data-stu-id="4deef-152">For example, if you are deploying a second pool (pool02) but the Central Management Server role is held by pool01.</span></span> <span data-ttu-id="4deef-153">O grupo sysadmin do SQL Server (ou equivalente) deve ter permissões em bancos de dados baseados no SQL Server.</span><span class="sxs-lookup"><span data-stu-id="4deef-153">The SQL Server sysadmin group (or equivalent) must have permissions on both SQL Server-based databases.</span></span>

    
    </div>

3.  <span data-ttu-id="4deef-154">Abra o Shell de gerenciamento do Lync Server 2013, se ele ainda não estiver aberto.</span><span class="sxs-lookup"><span data-stu-id="4deef-154">Open Lync Server 2013 Management Shell, if it’s not already open.</span></span>

4.  <span data-ttu-id="4deef-155">Use o cmdlet **install-CsDatabase** para instalar os bancos de dados do construtor de topologias configurados.</span><span class="sxs-lookup"><span data-stu-id="4deef-155">Use the **Install-CsDatabase** cmdlet to install the Topology Builder configured databases.</span></span>
    
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
    > <span data-ttu-id="4deef-156">O parâmetro relatório é opcional, mas é útil se você está documentando o processo de instalação.</span><span class="sxs-lookup"><span data-stu-id="4deef-156">The Report parameter is optional but is useful if you are documenting the installation process.</span></span>

    
    </div>

5.  <span data-ttu-id="4deef-157">Quando a instalação do banco de dados for concluída, feche o Shell de gerenciamento do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="4deef-157">When the database installation completes, close Lync Server 2013 Management Shell.</span></span>

</div>

<div>

## <a name="to-use-windows-powershell-cmdlets-to-configure-the-sql-server-topology-using-the-databasepathmap-parameter"></a><span data-ttu-id="4deef-158">Para usar cmdlets do Windows PowerShell para configurar a topologia do SQL Server usando o parâmetro DatabasePathMap</span><span class="sxs-lookup"><span data-stu-id="4deef-158">To use Windows PowerShell cmdlets to configure the SQL Server topology using the DatabasePathMap parameter</span></span>

1.  <span data-ttu-id="4deef-159">Para instalar bancos de dados do Lync Server 2013, o administrador do Lync Server deve criar os caminhos e implantar os arquivos de banco de dados e os arquivos de log de acordo com um conjunto de regras predefinido.</span><span class="sxs-lookup"><span data-stu-id="4deef-159">To install databases for Lync Server 2013, the Lync Server administrator must create the paths and deploy the databases files and log files according to a predefined set of rules.</span></span>

2.  <span data-ttu-id="4deef-160">Em qualquer computador, faça logon com credenciais administrativas para criar bancos de dados no servidor baseado no SQL Server.</span><span class="sxs-lookup"><span data-stu-id="4deef-160">On any computer, log on with administrative credentials for creating the databases on the SQL Server-based server.</span></span> <span data-ttu-id="4deef-161">Consulte o tópico [permissões de implantação do SQL Server no Lync Server 2013](lync-server-2013-deployment-permissions-for-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="4deef-161">See the topic, [Deployment permissions for SQL Server in Lync Server 2013](lync-server-2013-deployment-permissions-for-sql-server.md).</span></span>
    
    <div class=" ">
    

    > [!IMPORTANT]  
    > <span data-ttu-id="4deef-162">Para poder configurar os bancos de dados baseados no SQL Server, certifique-se de que a conta de administrador do SQL Server usada para executar as etapas descritas aqui também seja um membro do grupo Administradores do sistema (ou equivalente) no servidor que executa o SQL Server e que mantém o gerenciamento central Função de servidor.</span><span class="sxs-lookup"><span data-stu-id="4deef-162">To be able to configure the SQL Server-based databases, make sure the SQL Server administrator account used to run the steps described here is also a member of the sysadmins group (or equivalent) on the server running SQL Server and holding the Central Management Server role.</span></span> <span data-ttu-id="4deef-163">Isso é especialmente importante para verificar se há outros pools do Lync Server que exijam instalação ou configuração do banco de dados do SQL Server.</span><span class="sxs-lookup"><span data-stu-id="4deef-163">This is especially important to check for any additional Lync Server pools which require SQL Server database installation or configuration.</span></span> <span data-ttu-id="4deef-164">Por exemplo, se você estiver implantando um segundo pool (pool02), mas a função de servidor de gerenciamento central estiver mantida pela pool01.</span><span class="sxs-lookup"><span data-stu-id="4deef-164">For example, if you are deploying a second pool (pool02) but the Central Management Server role is held by pool01.</span></span> <span data-ttu-id="4deef-165">O grupo sysadmin do SQL Server (ou equivalente) deve ter permissões em bancos de dados baseados no SQL Server.</span><span class="sxs-lookup"><span data-stu-id="4deef-165">The SQL Server sysadmin group (or equivalent) must have permissions on both SQL Server-based databases.</span></span>

    
    </div>

3.  <span data-ttu-id="4deef-166">Abra o Shell de gerenciamento do Lync Server, se ele ainda não estiver aberto.</span><span class="sxs-lookup"><span data-stu-id="4deef-166">Open Lync Server Management Shell, if it’s not already open.</span></span>

4.  <span data-ttu-id="4deef-167">Use o cmdlet **install-CsDatabase** com o parâmetro DatabasePathMap e uma tabela de hash do PowerShell para instalar os bancos de dados do construtor de topologias configurados.</span><span class="sxs-lookup"><span data-stu-id="4deef-167">Use the **Install-CsDatabase** cmdlet with the DatabasePathMap parameter and a PowerShell hash table to install the Topology Builder configured databases.</span></span>

5.  <span data-ttu-id="4deef-168">No código de exemplo, os caminhos definidos para os bancos de dados podem ser determinados de uma maneira granular usando-se o parâmetro – DatabasePathMap e uma tabela de hash definida da seguinte maneira (o exemplo\\usa "c: CSData" para todos os arquivos de banco de dados (\\. MDF) e "C: CSLogFiles" para todos os arquivos de log (. ldf).</span><span class="sxs-lookup"><span data-stu-id="4deef-168">In the example code, the paths defined for the databases can be determined in a granular manner by using the –DatabasePathMap parameter and a defined hash table as follows (the example uses “C:\\CSData” for all database (.mdf) files, and “C:\\CSLogFiles” for all log (.ldf) files.</span></span> <span data-ttu-id="4deef-169">A pasta será criada conforme necessário pelo install-CsDatabase):</span><span class="sxs-lookup"><span data-stu-id="4deef-169">Folder will be created as needed by Install-CsDatabase):</span></span>
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
6.  <span data-ttu-id="4deef-170">Como o banco de dados e os arquivos de log são explicitamente nomeados com sua localização no servidor de banco de dados de destino, você pode definir locais específicos para cada tipo de serviço de banco de dados real e local de log.</span><span class="sxs-lookup"><span data-stu-id="4deef-170">Because the database and log files are explicitly named with their location on the destination database server, you can define specific locations for each service type’s actual database and log location.</span></span> <span data-ttu-id="4deef-171">O exemplo a seguir coloca os bancos de dados de cada tipo de serviço específico em discos separados e os arquivos de log associados em outro.</span><span class="sxs-lookup"><span data-stu-id="4deef-171">The following example puts databases for each specific service type on separate disks, and associated log files on another.</span></span> <span data-ttu-id="4deef-172">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="4deef-172">For example:</span></span>
    
      - <span data-ttu-id="4deef-173">Todos os bancos de dados RTC para "D\\: RTCDatabase"</span><span class="sxs-lookup"><span data-stu-id="4deef-173">All RTC databases to “D:\\RTCDatabase”</span></span>
    
      - <span data-ttu-id="4deef-174">Todos os arquivos de log RTC para "\\E: RTCLogs"</span><span class="sxs-lookup"><span data-stu-id="4deef-174">All RTC log files to “E:\\RTCLogs”</span></span>
    
      - <span data-ttu-id="4deef-175">Todos os bancos de dados da loja de aplicativos para\\"F: CPSDatabases"</span><span class="sxs-lookup"><span data-stu-id="4deef-175">All application store databases to “F:\\CPSDatabases”</span></span>
    
      - <span data-ttu-id="4deef-176">Todos os logs da loja de aplicativos para\\"G: CPSLogs"</span><span class="sxs-lookup"><span data-stu-id="4deef-176">All application store logs to “G:\\CPSLogs”</span></span>
    
      - <span data-ttu-id="4deef-177">Todos os bancos de dados de repositório do grupo de resposta\\para "H: RGSDatabases"</span><span class="sxs-lookup"><span data-stu-id="4deef-177">All response group store databases to “H:\\RGSDatabases”</span></span>
    
      - <span data-ttu-id="4deef-178">Todos os logs do repositório do grupo de resposta\\para "I: RGSLogs"</span><span class="sxs-lookup"><span data-stu-id="4deef-178">All response group store logs to “I:\\RGSLogs”</span></span>
    
      - <span data-ttu-id="4deef-179">Todos os bancos de dados do catálogo de endereços para "\\J: ABSDatabases"</span><span class="sxs-lookup"><span data-stu-id="4deef-179">All address book store databases to “J:\\ABSDatabases”</span></span>
    
      - <span data-ttu-id="4deef-180">Todos os arquivos de registro do repositório de endereços para\\"K: ABSLogs"</span><span class="sxs-lookup"><span data-stu-id="4deef-180">All address book store log files to “K:\\ABSLogs”</span></span>
    
      - <span data-ttu-id="4deef-181">Todos os bancos de dados do arquivamento da loja para\\"L: ArchivingDatabases"</span><span class="sxs-lookup"><span data-stu-id="4deef-181">All archiving store databases to “L:\\ArchivingDatabases”</span></span>
    
      - <span data-ttu-id="4deef-182">Todos os logs do repositório de arquivamento para\\"M: ArchivingLogs"</span><span class="sxs-lookup"><span data-stu-id="4deef-182">All archiving store logs to “M:\\ArchivingLogs”</span></span>
    
      - <span data-ttu-id="4deef-183">Todos os bancos de dados da loja de monitoramento para\\"N: MonitoringDatabases"</span><span class="sxs-lookup"><span data-stu-id="4deef-183">All monitoring store databases to “N:\\MonitoringDatabases”</span></span>
    
      - <span data-ttu-id="4deef-184">Todos os arquivos de log da loja de monitoramento\\para "O: MonitoringLogfiles"</span><span class="sxs-lookup"><span data-stu-id="4deef-184">All monitoring store log files to “O:\\MonitoringLogfiles”</span></span>
    
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
    
    <span data-ttu-id="4deef-185">Usando o parâmetro – DatabasePathMap, você pode definir qualquer combinação de mapeamento de letras de unidade lógica que forneça a melhor solução para seus requisitos de desempenho e posicionamento do SQL Server.</span><span class="sxs-lookup"><span data-stu-id="4deef-185">Using the –DatabasePathMap parameter, you can define any logical drive letter mapping combination that provides the best solution for your SQL Server performance and placement requirements.</span></span>

<span data-ttu-id="4deef-186">Se você configurar seus arquivos de dados de banco de dados e arquivos de log usando o método **DatabasePathMap** , será necessário fazer uma pequena alteração no processo normal ao usar o construtor de topologias.</span><span class="sxs-lookup"><span data-stu-id="4deef-186">If you configure your database data files and log files by using the **DatabasePathMap** method, you will need to make a slight change to your normal process when using Topology Builder.</span></span> <span data-ttu-id="4deef-187">Normalmente, você define suas opções de topologia, publica a topologia e escolhe implantar as seleções de banco de dados.</span><span class="sxs-lookup"><span data-stu-id="4deef-187">Typically, you would define your topology choices, publish the topology, and choose to deploy the database selections.</span></span>

<span data-ttu-id="4deef-188">Se você usou o **DatabasePathMap** , já realizou a terceira parte do processo do construtor de topologias.</span><span class="sxs-lookup"><span data-stu-id="4deef-188">If you have used **DatabasePathMap** you have already accomplished the third part of the Topology Builder process.</span></span> <span data-ttu-id="4deef-189">No caso de ter um servidor de banco de dados completamente configurado antes do construtor de topologias em execução, você ainda pode definir todas as suas opções e funções de servidor, mas desmarque a opção para criar os bancos de dados.</span><span class="sxs-lookup"><span data-stu-id="4deef-189">In the case of having a completely configured database server in advance of running Topology Builder, you would still define all of your server roles and options, but deselect the option to create the databases.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

