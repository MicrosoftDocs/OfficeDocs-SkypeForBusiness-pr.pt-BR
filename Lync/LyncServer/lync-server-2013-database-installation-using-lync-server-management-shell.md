---
title: 'Lync Server 2013: instalação de banco de dados usando o Shell de gerenciamento do Lync Server'
description: 'Lync Server 2013: instalação de banco de dados usando o Shell de gerenciamento do Lync Server.'
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
ms.openlocfilehash: 2d572984c94d280723b12c5343a92ddfaa12d4f0
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48558177"
---
# <a name="database-installation-using-lync-server-management-shell-in-lync-server-2013"></a><span data-ttu-id="8462f-103">Instalação de banco de dados usando o Shell de gerenciamento do Lync Server no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8462f-103">Database installation using Lync Server Management Shell in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8462f-104">_**Última modificação do tópico:** 2016-06-16_</span><span class="sxs-lookup"><span data-stu-id="8462f-104">_**Topic Last Modified:** 2016-06-16_</span></span>

<span data-ttu-id="8462f-105">A separação de funções e responsabilidades entre administradores de servidor e administradores do SQL Server pode resultar em atrasos na implementação.</span><span class="sxs-lookup"><span data-stu-id="8462f-105">Separation of roles and responsibilities between server administrators and SQL Server administrators can result in delays in implementation.</span></span> <span data-ttu-id="8462f-106">O Lync Server 2013 usa o controle de acesso baseado em função (RBAC) para reduzir essas dificuldades.</span><span class="sxs-lookup"><span data-stu-id="8462f-106">Lync Server 2013 uses role-based access control (RBAC) to mitigate these difficulties.</span></span> <span data-ttu-id="8462f-107">Em algumas instâncias, o administrador do SQL Server deverá gerenciar a instalação de bancos de dados no servidor baseado em SQL Server fora do RBAC.</span><span class="sxs-lookup"><span data-stu-id="8462f-107">In some instances, the SQL Server administrator must manage the installation of databases on the SQL Server-based server outside RBAC.</span></span> <span data-ttu-id="8462f-108">O Shell de gerenciamento do Lync Server 2013 oferece uma maneira de o administrador do SQL Server executar os cmdlets do Windows PowerShell projetados para configurar os bancos de dados com os arquivos de dados e de log corretos.</span><span class="sxs-lookup"><span data-stu-id="8462f-108">The Lync Server 2013 Management Shell provides a way for the SQL Server administrator to run Windows PowerShell cmdlets designed to configure the databases with the correct data and log files.</span></span> <span data-ttu-id="8462f-109">Para obter detalhes, consulte [Deployment Permissions for SQL Server in Lync server 2013](lync-server-2013-deployment-permissions-for-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="8462f-109">For details, see [Deployment permissions for SQL Server in Lync Server 2013](lync-server-2013-deployment-permissions-for-sql-server.md).</span></span>

<div class=" ">


> [!IMPORTANT]  
> <span data-ttu-id="8462f-110">O procedimento a seguir pressupõe que, no mínimo, o Lync Server 2013 OCSCore.msi, os objetos de gerenciamento do SQL Server Native Client (sqlncli.msi) Microsoft SQL Server 2012, tipos CLR para Microsoft SQL Server 2012 e Microsoft SQL Server 2012 ADOMD.NET estão instalados.</span><span class="sxs-lookup"><span data-stu-id="8462f-110">The following procedure assumes that at a minimum the Lync Server 2013 OCSCore.msi, SQL Server Native Client (sqlncli.msi) Microsoft SQL Server 2012 Management Objects, CLR Types for Microsoft SQL Server 2012 and Microsoft SQL Server 2012 ADOMD.NET are installed.</span></span> <span data-ttu-id="8462f-111">O OCSCore.msi está localizado na mídia de instalação, no diretório \Setup\AMD64\Setup.</span><span class="sxs-lookup"><span data-stu-id="8462f-111">The OCSCore.msi is located on the installation media in the \Setup\AMD64\Setup directory.</span></span> <span data-ttu-id="8462f-112">Os componentes restantes estão localizados no \setup\amd64.</span><span class="sxs-lookup"><span data-stu-id="8462f-112">The remaining components are located in \Setup\amd64.</span></span> <span data-ttu-id="8462f-113">Além disso, a preparação do Active Directory para o Lync Server 2013 foi concluída com êxito.</span><span class="sxs-lookup"><span data-stu-id="8462f-113">Additionally, Active Directory preparation for Lync Server 2013 has been successfully completed.</span></span>



</div>

<span data-ttu-id="8462f-114">**Install-CsDatabase** é o cmdlet do Windows PowerShell que você usa para instalar os bancos de dados.</span><span class="sxs-lookup"><span data-stu-id="8462f-114">**Install-CsDatabase** is the Windows PowerShell cmdlet you use to install the databases.</span></span> <span data-ttu-id="8462f-115">O cmdlet **Install-CsDatabase** tem muitos parâmetros, somente alguns deles são discutidos aqui.</span><span class="sxs-lookup"><span data-stu-id="8462f-115">The **Install-CsDatabase** cmdlet has a large number of parameters, only a few of which are discussed here.</span></span> <span data-ttu-id="8462f-116">Para obter detalhes sobre os parâmetros possíveis, consulte a documentação do Shell de gerenciamento do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="8462f-116">For details about the possible parameters, see the Lync Server 2013 Management Shell documentation.</span></span>

<div class=" ">


> [!WARNING]  
> <span data-ttu-id="8462f-117">Para evitar possíveis problemas de tempo limite e de desempenho, sempre use os FQDNs (nomes de domínio totalmente qualificados) ao se referir aos servidores baseados no SQL Server.</span><span class="sxs-lookup"><span data-stu-id="8462f-117">To avoid performance and possible time-out issues, always use fully qualified domain names (FQDNs) when referring to SQL Server-based servers.</span></span> <span data-ttu-id="8462f-118">Evite usar referências somente ao nome do host.</span><span class="sxs-lookup"><span data-stu-id="8462f-118">Avoid using host name-only references.</span></span> <span data-ttu-id="8462f-119">Por exemplo, use sqlbe01.contoso.net, mas evite usar o SQLBE01.</span><span class="sxs-lookup"><span data-stu-id="8462f-119">For example, use sqlbe01.contoso.net, but avoid using SQLBE01.</span></span>



</div>

<span data-ttu-id="8462f-120">Para a instalação de bancos de dados, **install-CsDatabase** usa três métodos principais para colocar os bancos de dados no servidor baseado em SQL Server preparado:</span><span class="sxs-lookup"><span data-stu-id="8462f-120">For installing databases, **Install-CsDatabase** uses three primary methods for placing the databases onto the prepared SQL Server-based server:</span></span>

  - <span data-ttu-id="8462f-121">Execute o **Install-CsDatabase** sem DatabasePaths ou UseDefaultSqlPath.</span><span class="sxs-lookup"><span data-stu-id="8462f-121">Run **Install-CsDatabase** without DatabasePaths or UseDefaultSqlPath.</span></span> <span data-ttu-id="8462f-122">O cmdlet usa um algoritmo integrado para determinar o melhor posicionamento dos arquivos de log e de dados.</span><span class="sxs-lookup"><span data-stu-id="8462f-122">The cmdlet uses a built in algorithm to determine the best placement for the log and data files.</span></span> <span data-ttu-id="8462f-123">O algoritmo só funciona para implementações autônomas do SQL Server.</span><span class="sxs-lookup"><span data-stu-id="8462f-123">The algorithm only works for stand-alone SQL Server implementations.</span></span>

  - <span data-ttu-id="8462f-124">Execute **Install-CsDatabase** com o parâmetro DatabasePaths.</span><span class="sxs-lookup"><span data-stu-id="8462f-124">Run **Install-CsDatabase** with the DatabasePaths parameter.</span></span> <span data-ttu-id="8462f-125">O algoritmo integrado para otimizar os locais de arquivo de log e de dados não é usado se o parâmetro DatabasePaths for definido.</span><span class="sxs-lookup"><span data-stu-id="8462f-125">The built-in algorithm to optimize log and data file locations is not used if the DatabasePaths parameter is defined.</span></span> <span data-ttu-id="8462f-126">O uso desse parâmetro permite que você defina os locais onde os arquivos de log e de dados serão implantados.</span><span class="sxs-lookup"><span data-stu-id="8462f-126">Using this parameter allows you to define the locations where log and data files will be deployed.</span></span>

  - <span data-ttu-id="8462f-127">Execute **Install-CsDatabase** com UseDefaultSqlPaths.</span><span class="sxs-lookup"><span data-stu-id="8462f-127">Run **Install-CsDatabase** with UseDefaultSqlPaths.</span></span> <span data-ttu-id="8462f-128">Essa opção não usar o algoritmo integrado para otimizar os locais do arquivo de log e de dados.</span><span class="sxs-lookup"><span data-stu-id="8462f-128">This option does not use the built-in algorithm to optimize the log and data file locations.</span></span> <span data-ttu-id="8462f-129">Os arquivos de log e de dados são implantados de acordo com os padrões definidos pelo administrador do SQL Server.</span><span class="sxs-lookup"><span data-stu-id="8462f-129">Log and data file are deployed according to the defaults set by the SQL Server administrator.</span></span> <span data-ttu-id="8462f-130">Esses caminhos são normalmente definidos para a finalidade da Administração automática de arquivos de log e dados no SQL Server com antecedência e não estão associados à configuração do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="8462f-130">These paths are typically set for the purpose of automatic administration of log and data files on the SQL Server in advance, and are not associated with the setup of Lync Server 2013.</span></span>

  - <span data-ttu-id="8462f-131">O parâmetro DatabasePathMap também pode ser usado para especificar explicitamente um local para cada banco de dados e seu respectivo arquivo de log.</span><span class="sxs-lookup"><span data-stu-id="8462f-131">The DatabasePathMap parameter can also be used to explicitly specify a location for each database and its respective log file.</span></span>

<div>

## <a name="to-use-windows-powershell-cmdlets-to-configure-the-sql-server-central-management-store"></a><span data-ttu-id="8462f-132">Para usar os cmdlets do Windows PowerShell para configurar o repositório de Gerenciamento central do SQL Server</span><span class="sxs-lookup"><span data-stu-id="8462f-132">To use Windows PowerShell cmdlets to configure the SQL Server Central Management store</span></span>

1.  <span data-ttu-id="8462f-133">Em qualquer computador, faça logon com credenciais administrativas para a criação dos bancos de dados no servidor baseado em SQL Server.</span><span class="sxs-lookup"><span data-stu-id="8462f-133">On any computer, log on with administrative credentials for creating the databases on the SQL Server-based server.</span></span> <span data-ttu-id="8462f-134">Para obter detalhes, consulte [Deployment Permissions for SQL Server in Lync server 2013](lync-server-2013-deployment-permissions-for-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="8462f-134">For details, see [Deployment permissions for SQL Server in Lync Server 2013](lync-server-2013-deployment-permissions-for-sql-server.md).</span></span>

2.  <span data-ttu-id="8462f-135">Abra o Shell de gerenciamento do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="8462f-135">Open the Lync Server 2013 Management Shell.</span></span> <span data-ttu-id="8462f-136">Se você não tiver ajustado a política de execução do Windows PowerShell, você deve ajustar a política para permitir que scripts do Windows PowerShell sejam executados.</span><span class="sxs-lookup"><span data-stu-id="8462f-136">If you have not adjusted the execution policy for Windows PowerShell, you must adjust the policy to allow Windows PowerShell scripts to run.</span></span> <span data-ttu-id="8462f-137">Para obter detalhes, consulte "examinando a política de execução" em [https://go.microsoft.com/fwlink/p/?linkId=203093](https://go.microsoft.com/fwlink/p/?linkid=203093) .</span><span class="sxs-lookup"><span data-stu-id="8462f-137">For details, see “Examining the Execution Policy” at [https://go.microsoft.com/fwlink/p/?linkId=203093](https://go.microsoft.com/fwlink/p/?linkid=203093).</span></span>

3.  <span data-ttu-id="8462f-138">Use o cmdlet **install-CsDatabase** para instalar o repositório de gerenciamento central.</span><span class="sxs-lookup"><span data-stu-id="8462f-138">Use the **Install-CsDatabase** cmdlet to install the Central Management store.</span></span>
    
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
    > <span data-ttu-id="8462f-139">O parâmetro Report é opcional, mas é útil se você estiver documentando o processo de instalação.</span><span class="sxs-lookup"><span data-stu-id="8462f-139">The Report parameter is optional but is useful if you are documenting the installation process.</span></span>

    
    </div>

4.  <span data-ttu-id="8462f-140">**Install-CsDatabase – Databasepaths** podem usar até seis parâmetros de caminho, cada um definindo os caminhos para as unidades, conforme definido nos dados do SQL Server e no posicionamento do arquivo de log.</span><span class="sxs-lookup"><span data-stu-id="8462f-140">**Install-CsDatabase –DatabasePaths** can use up to six path parameters, each defining the paths for the drives as defined in SQL Server Data and Log File Placement.</span></span> <span data-ttu-id="8462f-141">Pelas regras lógicas da configuração do banco de dados no Lync Server 2013, as unidades são analisadas em buckets de dois, quatro ou seis.</span><span class="sxs-lookup"><span data-stu-id="8462f-141">By the logical rules of the database configuration in Lync Server 2013, drives are parsed out into buckets of two, four, or six.</span></span> <span data-ttu-id="8462f-142">Dependendo da configuração do SQL Server e do número de buckets, você fornecerá dois caminhos, quatro caminhos ou seis caminhos.</span><span class="sxs-lookup"><span data-stu-id="8462f-142">Depending on your SQL Server configuration and the number of buckets, you will supply two paths, four paths, or six paths.</span></span>
    
    <span data-ttu-id="8462f-143">Se você tiver três unidades, o log terá prioridade e os arquivos de dados serão distribuídos em seguida.</span><span class="sxs-lookup"><span data-stu-id="8462f-143">If you have three drives, the log gets priority and the data files are distributed after.</span></span> <span data-ttu-id="8462f-144">Um exemplo para um servidor baseado em SQL Server configurado com seis unidades:</span><span class="sxs-lookup"><span data-stu-id="8462f-144">An example for a SQL Server-based server configured with six drives:</span></span>
    ```powershell
    Install-CsDatabase -ConfiguredDatases -SqlServerFqdn sqlbe.contoso.net -DatabasePaths "D:\CSDynLogs","E:\CSRtcLogs","F:\MonCdrArcLogs","G:\MonCdrArchData","H:\AbsAppLog","I:\DynRtcAbsAppData" -Report "C:\Logs\InstallDatabases.html"
    ```
5.  <span data-ttu-id="8462f-145">Quando a instalação do banco de dados for concluída, você poderá fechar o Shell de gerenciamento do Lync Server 2013 ou prosseguir para a instalação dos bancos de dados configurados do Lync Server 2013 definidos no construtor de topologias.</span><span class="sxs-lookup"><span data-stu-id="8462f-145">When the database installation completes, you can close Lync Server 2013 Management Shell or proceed to the installation of the Lync Server 2013 configured databases defined in Topology Builder.</span></span>

</div>

<div>

## <a name="to-use-windows-powershell-cmdlets-to-configure-the-sql-server-topology-configured-databases"></a><span data-ttu-id="8462f-146">Para usar os cmdlets do Windows PowerShell para configurar os bancos de dados configurados pela topologia do SQL Server</span><span class="sxs-lookup"><span data-stu-id="8462f-146">To use Windows PowerShell cmdlets to configure the SQL Server topology configured databases</span></span>

1.  <span data-ttu-id="8462f-147">Para instalar os bancos de dados configurados do construtor de topologia para o Lync Server 2013, o administrador do Lync Server 2013 deve publicar a topologia.</span><span class="sxs-lookup"><span data-stu-id="8462f-147">To install the Topology Builder configured databases for Lync Server 2013, the Lync Server 2013 administrator must publish the topology.</span></span> <span data-ttu-id="8462f-148">Para obter detalhes, consulte [publish the Topology in Lync Server 2013](lync-server-2013-publish-the-topology.md) na documentação de implantação.</span><span class="sxs-lookup"><span data-stu-id="8462f-148">For details, see [Publish the topology in Lync Server 2013](lync-server-2013-publish-the-topology.md) in the Deployment documentation.</span></span>

2.  <span data-ttu-id="8462f-149">Em qualquer computador, faça logon com credenciais administrativas para a criação dos bancos de dados no servidor baseado em SQL Server.</span><span class="sxs-lookup"><span data-stu-id="8462f-149">On any computer, log on with administrative credentials for creating the databases on the SQL Server-based server.</span></span> <span data-ttu-id="8462f-150">Consulte o tópico, [Deployment Permissions for SQL Server in Lync server 2013](lync-server-2013-deployment-permissions-for-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="8462f-150">See the topic, [Deployment permissions for SQL Server in Lync Server 2013](lync-server-2013-deployment-permissions-for-sql-server.md).</span></span>
    
    <div class=" ">
    

    > [!IMPORTANT]  
    > <span data-ttu-id="8462f-151">Para poder configurar os bancos de dados baseados em SQL Server, certifique-se de que a conta de administrador do SQL Server usada para executar as etapas descritas aqui também é membro do grupo sysadmins (ou equivalente) no servidor que executa o SQL Server e que mantém a função de servidor de gerenciamento central.</span><span class="sxs-lookup"><span data-stu-id="8462f-151">To be able to configure the SQL Server-based databases, make sure the SQL Server administrator account used to run the steps described here is also a member of the sysadmins group (or equivalent) on the server running SQL Server and holding the Central Management Server role.</span></span> <span data-ttu-id="8462f-152">Isso é especialmente importante para verificar qualquer pool adicional do Lync Server 2013 que exija instalação ou configuração de banco de dados do SQL Server.</span><span class="sxs-lookup"><span data-stu-id="8462f-152">This is especially important to check for any additional Lync Server 2013 pools which require SQL Server database installation or configuration.</span></span> <span data-ttu-id="8462f-153">Por exemplo, se você estiver implantando um segundo pool (pool02), mas a função de servidor de gerenciamento central for mantida pelo pool01.</span><span class="sxs-lookup"><span data-stu-id="8462f-153">For example, if you are deploying a second pool (pool02) but the Central Management Server role is held by pool01.</span></span> <span data-ttu-id="8462f-154">O grupo sysadmin do SQL Server (ou equivalente) deve ter permissões em ambos os bancos de dados baseados no SQL Server.</span><span class="sxs-lookup"><span data-stu-id="8462f-154">The SQL Server sysadmin group (or equivalent) must have permissions on both SQL Server-based databases.</span></span>

    
    </div>

3.  <span data-ttu-id="8462f-155">Abra o Shell de gerenciamento do Lync Server 2013, se ainda não estiver aberto.</span><span class="sxs-lookup"><span data-stu-id="8462f-155">Open Lync Server 2013 Management Shell, if it’s not already open.</span></span>

4.  <span data-ttu-id="8462f-156">Use o cmdlet **install-CsDatabase** para instalar os bancos de dados configurados do construtor de topologias.</span><span class="sxs-lookup"><span data-stu-id="8462f-156">Use the **Install-CsDatabase** cmdlet to install the Topology Builder configured databases.</span></span>
    
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
    > <span data-ttu-id="8462f-157">O parâmetro Report é opcional, mas é útil se você estiver documentando o processo de instalação.</span><span class="sxs-lookup"><span data-stu-id="8462f-157">The Report parameter is optional but is useful if you are documenting the installation process.</span></span>

    
    </div>

5.  <span data-ttu-id="8462f-158">Quando a instalação do banco de dados for concluída, feche o Shell de gerenciamento do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="8462f-158">When the database installation completes, close Lync Server 2013 Management Shell.</span></span>

</div>

<div>

## <a name="to-use-windows-powershell-cmdlets-to-configure-the-sql-server-topology-using-the-databasepathmap-parameter"></a><span data-ttu-id="8462f-159">Para usar os cmdlets do Windows PowerShell para configurar a topologia do SQL Server usando o parâmetro DatabasePathMap</span><span class="sxs-lookup"><span data-stu-id="8462f-159">To use Windows PowerShell cmdlets to configure the SQL Server topology using the DatabasePathMap parameter</span></span>

1.  <span data-ttu-id="8462f-160">Para instalar os bancos de dados do Lync Server 2013, o administrador do Lync Server deve criar os caminhos e implantar os arquivos de banco de dados e os arquivos de log de acordo com um conjunto predefinido de regras.</span><span class="sxs-lookup"><span data-stu-id="8462f-160">To install databases for Lync Server 2013, the Lync Server administrator must create the paths and deploy the databases files and log files according to a predefined set of rules.</span></span>

2.  <span data-ttu-id="8462f-161">Em qualquer computador, faça logon com credenciais administrativas para a criação dos bancos de dados no servidor baseado em SQL Server.</span><span class="sxs-lookup"><span data-stu-id="8462f-161">On any computer, log on with administrative credentials for creating the databases on the SQL Server-based server.</span></span> <span data-ttu-id="8462f-162">Consulte o tópico, [Deployment Permissions for SQL Server in Lync server 2013](lync-server-2013-deployment-permissions-for-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="8462f-162">See the topic, [Deployment permissions for SQL Server in Lync Server 2013](lync-server-2013-deployment-permissions-for-sql-server.md).</span></span>
    
    <div class=" ">
    

    > [!IMPORTANT]  
    > <span data-ttu-id="8462f-163">Para poder configurar os bancos de dados baseados em SQL Server, certifique-se de que a conta de administrador do SQL Server usada para executar as etapas descritas aqui também é membro do grupo sysadmins (ou equivalente) no servidor que executa o SQL Server e que mantém a função de servidor de gerenciamento central.</span><span class="sxs-lookup"><span data-stu-id="8462f-163">To be able to configure the SQL Server-based databases, make sure the SQL Server administrator account used to run the steps described here is also a member of the sysadmins group (or equivalent) on the server running SQL Server and holding the Central Management Server role.</span></span> <span data-ttu-id="8462f-164">Isso é especialmente importante para verificar qualquer pool adicional do Lync Server que exija instalação ou configuração de banco de dados do SQL Server.</span><span class="sxs-lookup"><span data-stu-id="8462f-164">This is especially important to check for any additional Lync Server pools which require SQL Server database installation or configuration.</span></span> <span data-ttu-id="8462f-165">Por exemplo, se você estiver implantando um segundo pool (pool02), mas a função de servidor de gerenciamento central for mantida pelo pool01.</span><span class="sxs-lookup"><span data-stu-id="8462f-165">For example, if you are deploying a second pool (pool02) but the Central Management Server role is held by pool01.</span></span> <span data-ttu-id="8462f-166">O grupo sysadmin do SQL Server (ou equivalente) deve ter permissões em ambos os bancos de dados baseados no SQL Server.</span><span class="sxs-lookup"><span data-stu-id="8462f-166">The SQL Server sysadmin group (or equivalent) must have permissions on both SQL Server-based databases.</span></span>

    
    </div>

3.  <span data-ttu-id="8462f-167">Abra o Shell de gerenciamento do Lync Server, se ainda não estiver aberto.</span><span class="sxs-lookup"><span data-stu-id="8462f-167">Open Lync Server Management Shell, if it’s not already open.</span></span>

4.  <span data-ttu-id="8462f-168">Use o cmdlet **install-CsDatabase** com o parâmetro DatabasePathMap e uma tabela de hash do PowerShell para instalar os bancos de dados configurados do construtor de topologias.</span><span class="sxs-lookup"><span data-stu-id="8462f-168">Use the **Install-CsDatabase** cmdlet with the DatabasePathMap parameter and a PowerShell hash table to install the Topology Builder configured databases.</span></span>

5.  <span data-ttu-id="8462f-169">No código de exemplo, os caminhos definidos para os bancos de dados podem ser determinados de uma maneira granular usando o parâmetro – DatabasePathMap e uma tabela de hash definida da seguinte maneira (o exemplo usa "C: \\ CSData" para todos os arquivos de banco de dados (. MDF) e "c: \\ CSLogFiles" para todos os arquivos de log (. ldf).</span><span class="sxs-lookup"><span data-stu-id="8462f-169">In the example code, the paths defined for the databases can be determined in a granular manner by using the –DatabasePathMap parameter and a defined hash table as follows (the example uses “C:\\CSData” for all database (.mdf) files, and “C:\\CSLogFiles” for all log (.ldf) files.</span></span> <span data-ttu-id="8462f-170">A pasta será criada conforme necessário pelo install-CsDatabase):</span><span class="sxs-lookup"><span data-stu-id="8462f-170">Folder will be created as needed by Install-CsDatabase):</span></span>
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
6.  <span data-ttu-id="8462f-171">Como o banco de dados e os arquivos de log são nomeados explicitamente com seu local no servidor de banco de dados de destino, você pode definir locais específicos para cada tipo de serviço de banco de dados real e local de log.</span><span class="sxs-lookup"><span data-stu-id="8462f-171">Because the database and log files are explicitly named with their location on the destination database server, you can define specific locations for each service type’s actual database and log location.</span></span> <span data-ttu-id="8462f-172">O exemplo a seguir coloca os bancos de dados de cada tipo de serviço específico em discos separados e os arquivos de log associados em outro.</span><span class="sxs-lookup"><span data-stu-id="8462f-172">The following example puts databases for each specific service type on separate disks, and associated log files on another.</span></span> <span data-ttu-id="8462f-173">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="8462f-173">For example:</span></span>
    
      - <span data-ttu-id="8462f-174">Todos os bancos de dados RTC para "D: \\ RTCDatabase"</span><span class="sxs-lookup"><span data-stu-id="8462f-174">All RTC databases to “D:\\RTCDatabase”</span></span>
    
      - <span data-ttu-id="8462f-175">Todos os arquivos de log RTC para "E: \\ RTCLogs"</span><span class="sxs-lookup"><span data-stu-id="8462f-175">All RTC log files to “E:\\RTCLogs”</span></span>
    
      - <span data-ttu-id="8462f-176">Todos os bancos de dados de repositório de aplicativos para "F: \\ CPSDatabases"</span><span class="sxs-lookup"><span data-stu-id="8462f-176">All application store databases to “F:\\CPSDatabases”</span></span>
    
      - <span data-ttu-id="8462f-177">Todos os logs de repositório de aplicativos para "G: \\ CPSLogs"</span><span class="sxs-lookup"><span data-stu-id="8462f-177">All application store logs to “G:\\CPSLogs”</span></span>
    
      - <span data-ttu-id="8462f-178">Todos os bancos de dados do repositório de grupos de resposta para "H: \\ RGSDatabases"</span><span class="sxs-lookup"><span data-stu-id="8462f-178">All response group store databases to “H:\\RGSDatabases”</span></span>
    
      - <span data-ttu-id="8462f-179">Todos os logs do repositório de resposta do grupo para "I: \\ RGSLogs"</span><span class="sxs-lookup"><span data-stu-id="8462f-179">All response group store logs to “I:\\RGSLogs”</span></span>
    
      - <span data-ttu-id="8462f-180">Todos os bancos de dados do repositório de catálogo de endereços para "J: \\ ABSDatabases"</span><span class="sxs-lookup"><span data-stu-id="8462f-180">All address book store databases to “J:\\ABSDatabases”</span></span>
    
      - <span data-ttu-id="8462f-181">Todos os arquivos de log do repositório de catálogo de endereços para "K: \\ ABSLogs"</span><span class="sxs-lookup"><span data-stu-id="8462f-181">All address book store log files to “K:\\ABSLogs”</span></span>
    
      - <span data-ttu-id="8462f-182">Todos os bancos de dados de repositório de arquivamento para "L: \\ ArchivingDatabases"</span><span class="sxs-lookup"><span data-stu-id="8462f-182">All archiving store databases to “L:\\ArchivingDatabases”</span></span>
    
      - <span data-ttu-id="8462f-183">Todos os logs do repositório de arquivamento para "M: \\ ArchivingLogs"</span><span class="sxs-lookup"><span data-stu-id="8462f-183">All archiving store logs to “M:\\ArchivingLogs”</span></span>
    
      - <span data-ttu-id="8462f-184">Todos os bancos de dados de repositório de monitoramento para "N: \\ MonitoringDatabases"</span><span class="sxs-lookup"><span data-stu-id="8462f-184">All monitoring store databases to “N:\\MonitoringDatabases”</span></span>
    
      - <span data-ttu-id="8462f-185">Todos os arquivos de log do repositório de monitoramento para "O: \\ MonitoringLogfiles"</span><span class="sxs-lookup"><span data-stu-id="8462f-185">All monitoring store log files to “O:\\MonitoringLogfiles”</span></span>
    
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
    
    <span data-ttu-id="8462f-186">Usando o parâmetro – DatabasePathMap, você pode definir qualquer combinação de mapeamento de letra de unidade lógica que forneça a melhor solução para seus requisitos de desempenho e posicionamento do SQL Server.</span><span class="sxs-lookup"><span data-stu-id="8462f-186">Using the –DatabasePathMap parameter, you can define any logical drive letter mapping combination that provides the best solution for your SQL Server performance and placement requirements.</span></span>

<span data-ttu-id="8462f-187">Se você configurar seus arquivos de dados de banco de dados e arquivos de log usando o método **DatabasePathMap** , será necessário fazer uma pequena alteração no seu processo normal ao usar o construtor de topologias.</span><span class="sxs-lookup"><span data-stu-id="8462f-187">If you configure your database data files and log files by using the **DatabasePathMap** method, you will need to make a slight change to your normal process when using Topology Builder.</span></span> <span data-ttu-id="8462f-188">Normalmente, você deve definir as opções de topologia, publicar a topologia e optar por implantar as seleções de banco de dados.</span><span class="sxs-lookup"><span data-stu-id="8462f-188">Typically, you would define your topology choices, publish the topology, and choose to deploy the database selections.</span></span>

<span data-ttu-id="8462f-189">Se você usou o **DatabasePathMap** , já realizou a terceira parte do processo do construtor de topologias.</span><span class="sxs-lookup"><span data-stu-id="8462f-189">If you have used **DatabasePathMap** you have already accomplished the third part of the Topology Builder process.</span></span> <span data-ttu-id="8462f-190">No caso de ter um servidor de banco de dados completamente configurado com antecedência da execução do construtor de topologias, você ainda pode definir todas as suas funções e opções de servidor, mas desmarque a opção para criar os bancos de dados.</span><span class="sxs-lookup"><span data-stu-id="8462f-190">In the case of having a completely configured database server in advance of running Topology Builder, you would still define all of your server roles and options, but deselect the option to create the databases.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

