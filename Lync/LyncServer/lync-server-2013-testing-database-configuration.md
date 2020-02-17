---
title: 'Lync Server 2013: testar configuração de banco de dados'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing database configuration
ms:assetid: 60f7fcd2-5efe-4791-b159-b0f9bf39a41b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn727307(v=OCS.15)
ms:contentKeyID: 63969606
ms.date: 07/07/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 45781238f7fb8aa461e050f2e8f0cbf04e45a950
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42038173"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="testing-database-configuration-in-lync-server-2013"></a><span data-ttu-id="d4713-102">Testando a configuração do banco de dados no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d4713-102">Testing database configuration in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d4713-103">_**Última modificação do tópico:** 2016-07-07_</span><span class="sxs-lookup"><span data-stu-id="d4713-103">_**Topic Last Modified:** 2016-07-07_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d4713-104">Agenda de verificação</span><span class="sxs-lookup"><span data-stu-id="d4713-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="d4713-105">Diariamente</span><span class="sxs-lookup"><span data-stu-id="d4713-105">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d4713-106">Ferramenta de teste</span><span class="sxs-lookup"><span data-stu-id="d4713-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="d4713-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="d4713-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d4713-108">Permissões obrigatórias</span><span class="sxs-lookup"><span data-stu-id="d4713-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="d4713-109">Ao executar localmente usando o Shell de gerenciamento do Lync Server, os usuários devem ser membros do grupo de segurança RTCUniversalServerAdmins e ter privilégios de administrador no SQL Server.</span><span class="sxs-lookup"><span data-stu-id="d4713-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group, and need to have Administrator privileges on the SQL server.</span></span></p>
<p><span data-ttu-id="d4713-110">Quando executado usando uma instância remota do Windows PowerShell, os usuários devem receber uma função RBAC que tenha permissão para executar o cmdlet <strong>Test-CsDatabase</strong> .</span><span class="sxs-lookup"><span data-stu-id="d4713-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the <strong>Test-CsDatabase</strong> cmdlet.</span></span> <span data-ttu-id="d4713-111">Para ver uma lista de todas as funções RBAC que podem usar este cmdlet, execute o seguinte comando no prompt do Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="d4713-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsDatabase&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="d4713-112">Descrição</span><span class="sxs-lookup"><span data-stu-id="d4713-112">Description</span></span>

<span data-ttu-id="d4713-113">O cmdlet **Test-CsDatabase** verifica a conectividade para um ou mais bancos de dados do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="d4713-113">The **Test-CsDatabase** cmdlet verifies connectivity to one or more Lync Server 2013 databases.</span></span> <span data-ttu-id="d4713-114">Quando executado, o cmdlet **Test-CsDatabase** lê a topologia do Lync Server, tenta se conectar a bancos de dados relevantes e, em seguida, relata o êxito ou falha de cada tentativa.</span><span class="sxs-lookup"><span data-stu-id="d4713-114">When run, the **Test-CsDatabase** cmdlet reads the Lync Server topology, attempts to connect to relevant databases, and then reports back the success or failure of each try.</span></span> <span data-ttu-id="d4713-115">Se uma conexão pode ser realizada, o cmdlet também relatará tal informação como o nome do banco de dados, a informação de versão do SQL Server e o local de qualquer banco de dados espelho instalado.</span><span class="sxs-lookup"><span data-stu-id="d4713-115">If a connection can be made, the cmdlet will also report back such information as the database name, SQL Server version information, and the location of any installed mirror databases.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="d4713-116">Executar o teste</span><span class="sxs-lookup"><span data-stu-id="d4713-116">Running the test</span></span>

<span data-ttu-id="d4713-117">O comando mostrado no Exemplo 1 verifica a configuração do banco de dados de Gerenciamento Central.</span><span class="sxs-lookup"><span data-stu-id="d4713-117">The command shown in Example 1 verifies the configuration of the Central Management database.</span></span>

    Test-CsDatabase -CentralManagementDatabase

<span data-ttu-id="d4713-118">O exemplo 2 verifica todos os bancos de dados do Lync Server instalados no computador atl-sql-001.litwareinc.com.</span><span class="sxs-lookup"><span data-stu-id="d4713-118">Example 2 verifies all the Lync Server databases installed on the computer atl-sql-001.litwareinc.com.</span></span>

    Test-CsDatabase -ConfiguredDatabases -SqlServerFqdn "atl-sql-001.litwareinc.com"

<span data-ttu-id="d4713-p103">No Exemplo 3, a verificação é realizada apenas para o banco de dados de Arquivamento instalado no computador atl-sql-001.litwareinc.com. Observe que o parâmetro SqlInstanceName está incluído para especificar a instância do SQL Server (Archinst) onde o banco de dados de Arquivamento está localizado.</span><span class="sxs-lookup"><span data-stu-id="d4713-p103">In Example 3, verification is performed only for the Archiving database installed on the computer atl-sql-001.litwareinc.com. Note that the SqlInstanceName parameter is included to specify the SQL Server instance (Archinst) where the Archiving database is located.</span></span>

    Test-CsDatabase -DatabaseType "Archiving" -SqlServerFqdn "atl-sql-001.litwareinc.com" -SqlInstanceName "archinst"

<span data-ttu-id="d4713-121">O comando mostrado no Exemplo 4 verifica os bancos de dados instalados no computador local.</span><span class="sxs-lookup"><span data-stu-id="d4713-121">The command shown in Example 4 verifies the databases installed on the local computer.</span></span>

    Test-CsDatabase -LocalService

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="d4713-122">Determinando o sucesso ou a falha</span><span class="sxs-lookup"><span data-stu-id="d4713-122">Determining success or failure</span></span>

<span data-ttu-id="d4713-123">Se a conectividade do banco de dados estiver configurada corretamente, você receberá uma saída semelhante a essa, com a propriedade sucede marcada como **true**:</span><span class="sxs-lookup"><span data-stu-id="d4713-123">If database connectivity is configured correctly, you'll receive output similar to this, with the Succeed property marked as **True**:</span></span>

<span data-ttu-id="d4713-124">SqlServerFqdn: atl-sql-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="d4713-124">SqlServerFqdn : atl-sql-001.litwareinc.com</span></span>

<span data-ttu-id="d4713-125">SQLINSTANCENAME: RTC</span><span class="sxs-lookup"><span data-stu-id="d4713-125">SqlInstanceName : rtc</span></span>

<span data-ttu-id="d4713-126">MirrorSqlServerFqdn :</span><span class="sxs-lookup"><span data-stu-id="d4713-126">MirrorSqlServerFqdn :</span></span>

<span data-ttu-id="d4713-127">MirrorSqlInstanceName :</span><span class="sxs-lookup"><span data-stu-id="d4713-127">MirrorSqlInstanceName :</span></span>

<span data-ttu-id="d4713-128">DatabaseName: XDS</span><span class="sxs-lookup"><span data-stu-id="d4713-128">DatabaseName : xds</span></span>

<span data-ttu-id="d4713-129">DataSource</span><span class="sxs-lookup"><span data-stu-id="d4713-129">DataSource :</span></span>

<span data-ttu-id="d4713-130">SQLServerVersion :</span><span class="sxs-lookup"><span data-stu-id="d4713-130">SQLServerVersion :</span></span>

<span data-ttu-id="d4713-131">ExpectedVersion : 10.13.2</span><span class="sxs-lookup"><span data-stu-id="d4713-131">ExpectedVersion : 10.13.2</span></span>

<span data-ttu-id="d4713-132">InstalledVersion :</span><span class="sxs-lookup"><span data-stu-id="d4713-132">InstalledVersion :</span></span>

<span data-ttu-id="d4713-133">Êxito: true</span><span class="sxs-lookup"><span data-stu-id="d4713-133">Succeed : True</span></span>

<span data-ttu-id="d4713-134">SqlServerFqdn: atl-sql-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="d4713-134">SqlServerFqdn : atl-sql-001.litwareinc.com</span></span>

<span data-ttu-id="d4713-135">SQLINSTANCENAME: RTC</span><span class="sxs-lookup"><span data-stu-id="d4713-135">SqlInstanceName : rtc</span></span>

<span data-ttu-id="d4713-136">MirrorSqlServerFqdn :</span><span class="sxs-lookup"><span data-stu-id="d4713-136">MirrorSqlServerFqdn :</span></span>

<span data-ttu-id="d4713-137">MirrorSqlInstanceName :</span><span class="sxs-lookup"><span data-stu-id="d4713-137">MirrorSqlInstanceName :</span></span>

<span data-ttu-id="d4713-138">DatabaseName: Lis</span><span class="sxs-lookup"><span data-stu-id="d4713-138">DatabaseName : lis</span></span>

<span data-ttu-id="d4713-139">DataSource</span><span class="sxs-lookup"><span data-stu-id="d4713-139">DataSource :</span></span>

<span data-ttu-id="d4713-140">SQLServerVersion :</span><span class="sxs-lookup"><span data-stu-id="d4713-140">SQLServerVersion :</span></span>

<span data-ttu-id="d4713-141">ExpectedVersion : 3.1.1</span><span class="sxs-lookup"><span data-stu-id="d4713-141">ExpectedVersion : 3.1.1</span></span>

<span data-ttu-id="d4713-142">InstalledVersion :</span><span class="sxs-lookup"><span data-stu-id="d4713-142">InstalledVersion :</span></span>

<span data-ttu-id="d4713-143">Êxito: true</span><span class="sxs-lookup"><span data-stu-id="d4713-143">Succeed : True</span></span>

<span data-ttu-id="d4713-144">Se o banco de dados estiver configurado corretamente, mas ainda estiver disponível, o campo bem-sucedido será mostrado como **falso**, e avisos e informações adicionais serão fornecidos:</span><span class="sxs-lookup"><span data-stu-id="d4713-144">If the database is configured correctly but still available, the Succeed field will be shown as **False**, and additional warnings and information will be provided:</span></span>

<span data-ttu-id="d4713-145">SqlServerFqdn: atl-sql-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="d4713-145">SqlServerFqdn : atl-sql-001.litwareinc.com</span></span>

<span data-ttu-id="d4713-146">SQLINSTANCENAME: RTC</span><span class="sxs-lookup"><span data-stu-id="d4713-146">SqlInstanceName : rtc</span></span>

<span data-ttu-id="d4713-147">MirrorSqlServerFqdn :</span><span class="sxs-lookup"><span data-stu-id="d4713-147">MirrorSqlServerFqdn :</span></span>

<span data-ttu-id="d4713-148">MirrorSqlInstanceName :</span><span class="sxs-lookup"><span data-stu-id="d4713-148">MirrorSqlInstanceName :</span></span>

<span data-ttu-id="d4713-149">DatabaseName: XDS</span><span class="sxs-lookup"><span data-stu-id="d4713-149">DatabaseName : xds</span></span>

<span data-ttu-id="d4713-150">DataSource</span><span class="sxs-lookup"><span data-stu-id="d4713-150">DataSource :</span></span>

<span data-ttu-id="d4713-151">SQLServerVersion :</span><span class="sxs-lookup"><span data-stu-id="d4713-151">SQLServerVersion :</span></span>

<span data-ttu-id="d4713-152">ExpectedVersion : 10.13.2</span><span class="sxs-lookup"><span data-stu-id="d4713-152">ExpectedVersion : 10.13.2</span></span>

<span data-ttu-id="d4713-153">InstalledVersion :</span><span class="sxs-lookup"><span data-stu-id="d4713-153">InstalledVersion :</span></span>

<span data-ttu-id="d4713-154">Êxito: falso</span><span class="sxs-lookup"><span data-stu-id="d4713-154">Succeed : False</span></span>

<span data-ttu-id="d4713-155">SqlServerFqdn: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="d4713-155">SqlServerFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="d4713-156">SQLINSTANCENAME: RTC</span><span class="sxs-lookup"><span data-stu-id="d4713-156">SqlInstanceName : rtc</span></span>

<span data-ttu-id="d4713-157">MirrorSqlServerFqdn :</span><span class="sxs-lookup"><span data-stu-id="d4713-157">MirrorSqlServerFqdn :</span></span>

<span data-ttu-id="d4713-158">MirrorSqlInstanceName :</span><span class="sxs-lookup"><span data-stu-id="d4713-158">MirrorSqlInstanceName :</span></span>

<span data-ttu-id="d4713-159">DatabaseName: Lis</span><span class="sxs-lookup"><span data-stu-id="d4713-159">DatabaseName : lis</span></span>

<span data-ttu-id="d4713-160">DataSource</span><span class="sxs-lookup"><span data-stu-id="d4713-160">DataSource :</span></span>

<span data-ttu-id="d4713-161">SQLServerVersion :</span><span class="sxs-lookup"><span data-stu-id="d4713-161">SQLServerVersion :</span></span>

<span data-ttu-id="d4713-162">ExpectedVersion : 3.1.1</span><span class="sxs-lookup"><span data-stu-id="d4713-162">ExpectedVersion : 3.1.1</span></span>

<span data-ttu-id="d4713-163">InstalledVersion :</span><span class="sxs-lookup"><span data-stu-id="d4713-163">InstalledVersion :</span></span>

<span data-ttu-id="d4713-164">Êxito: falso</span><span class="sxs-lookup"><span data-stu-id="d4713-164">Succeed : False</span></span>

<span data-ttu-id="d4713-165">Aviso: Test-CsDatabase encontrou erros.</span><span class="sxs-lookup"><span data-stu-id="d4713-165">WARNING: Test-CsDatabase encountered errors.</span></span> <span data-ttu-id="d4713-166">Consulte o arquivo de log para obter um</span><span class="sxs-lookup"><span data-stu-id="d4713-166">Consult the log file for a</span></span>

<span data-ttu-id="d4713-167">análise detalhada e para garantir que todos os erros (2) e avisos (0) sejam tratados</span><span class="sxs-lookup"><span data-stu-id="d4713-167">detailed analysis, and to make sure that all errors (2) and warnings (0) are addressed</span></span>

<span data-ttu-id="d4713-168">antes de continuar.</span><span class="sxs-lookup"><span data-stu-id="d4713-168">before continuing.</span></span>

<span data-ttu-id="d4713-169">Aviso: resultados detalhados podem ser encontrados em</span><span class="sxs-lookup"><span data-stu-id="d4713-169">WARNING: Detailed results can be found at</span></span>

<span data-ttu-id="d4713-170">"C:\\os\\usuários\\que\\estão\\testando o local temp\\2\\Test-CsDatabase-b18d488a-8044-4679-bbf2-</span><span class="sxs-lookup"><span data-stu-id="d4713-170">"C:\\Users\\Testing\\AppData\\Local\\Temp\\2\\Test-CsDatabase-b18d488a-8044-4679-bbf2-</span></span>

<span data-ttu-id="d4713-171">04d593cce8e6. html ".</span><span class="sxs-lookup"><span data-stu-id="d4713-171">04d593cce8e6.html".</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="d4713-172">Motivos pelos quais o teste pode ter falhado</span><span class="sxs-lookup"><span data-stu-id="d4713-172">Reasons why the test might have failed</span></span>

<span data-ttu-id="d4713-173">Aqui estão alguns motivos comuns pelos quais **Test-CsDatabase** pode falhar:</span><span class="sxs-lookup"><span data-stu-id="d4713-173">Here are some common reasons why **Test-CsDatabase** might fail:</span></span>

  - <span data-ttu-id="d4713-174">Um valor de parâmetro incorreto foi fornecido.</span><span class="sxs-lookup"><span data-stu-id="d4713-174">An incorrect parameter value was supplied.</span></span> <span data-ttu-id="d4713-175">Se usado, os parâmetros opcionais devem ser configurados corretamente ou o teste falhará.</span><span class="sxs-lookup"><span data-stu-id="d4713-175">If used, the optional parameters must be configured correctly or the test will fail.</span></span> <span data-ttu-id="d4713-176">Execute novamente o comando sem os parâmetros opcionais e veja se isso é bem-sucedido.</span><span class="sxs-lookup"><span data-stu-id="d4713-176">Rerun the command without the optional parameters and see whether that succeeds.</span></span>

  - <span data-ttu-id="d4713-177">Esse comando falhará se o banco de dados estiver configurado incorretamente ou ainda não tiver sido implantado.</span><span class="sxs-lookup"><span data-stu-id="d4713-177">This command will fail if the database is misconfigured or not yet deployed.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="d4713-178">Confira Também</span><span class="sxs-lookup"><span data-stu-id="d4713-178">See Also</span></span>


[<span data-ttu-id="d4713-179">Get-CsDatabaseMirrorState</span><span class="sxs-lookup"><span data-stu-id="d4713-179">Get-CsDatabaseMirrorState</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsDatabaseMirrorState)  
[<span data-ttu-id="d4713-180">Get-CsService</span><span class="sxs-lookup"><span data-stu-id="d4713-180">Get-CsService</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsService)  
[<span data-ttu-id="d4713-181">Get-CsUserDatabaseState</span><span class="sxs-lookup"><span data-stu-id="d4713-181">Get-CsUserDatabaseState</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsUserDatabaseState)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

