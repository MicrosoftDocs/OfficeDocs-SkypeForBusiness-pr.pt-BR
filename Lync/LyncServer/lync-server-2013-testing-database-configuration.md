---
title: 'Lync Server 2013: configuração do banco de dados de teste'
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
ms.openlocfilehash: 6fcf6679481d4f35a457eb72960a8ae999b004d3
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41745821"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="testing-database-configuration-in-lync-server-2013"></a><span data-ttu-id="b9947-102">Testar a configuração do banco de dados no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b9947-102">Testing database configuration in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b9947-103">_**Tópico da última modificação:** 2016-07-07_</span><span class="sxs-lookup"><span data-stu-id="b9947-103">_**Topic Last Modified:** 2016-07-07_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b9947-104">Cronograma de verificação</span><span class="sxs-lookup"><span data-stu-id="b9947-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="b9947-105">Diário</span><span class="sxs-lookup"><span data-stu-id="b9947-105">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b9947-106">Ferramenta de teste</span><span class="sxs-lookup"><span data-stu-id="b9947-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="b9947-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="b9947-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b9947-108">Permissões necessárias</span><span class="sxs-lookup"><span data-stu-id="b9947-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="b9947-109">Quando executado localmente usando o Shell de gerenciamento do Lync Server, os usuários devem ser membros do grupo de segurança RTCUniversalServerAdmins e precisam ter privilégios de administrador no SQL Server.</span><span class="sxs-lookup"><span data-stu-id="b9947-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group, and need to have Administrator privileges on the SQL server.</span></span></p>
<p><span data-ttu-id="b9947-110">Quando executado usando uma instância remota do Windows PowerShell, os usuários devem receber uma função RBAC que tenha permissão para executar o cmdlet <strong>Test-CsDatabase</strong> .</span><span class="sxs-lookup"><span data-stu-id="b9947-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the <strong>Test-CsDatabase</strong> cmdlet.</span></span> <span data-ttu-id="b9947-111">Para ver uma lista de todas as funções RBAC que podem usar esse cmdlet, execute o seguinte comando no prompt do Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="b9947-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsDatabase&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="b9947-112">Descrição</span><span class="sxs-lookup"><span data-stu-id="b9947-112">Description</span></span>

<span data-ttu-id="b9947-113">O cmdlet **Test-CsDatabase** verifica a conectividade de um ou mais bancos de dados do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="b9947-113">The **Test-CsDatabase** cmdlet verifies connectivity to one or more Lync Server 2013 databases.</span></span> <span data-ttu-id="b9947-114">Quando executado, o cmdlet **Test-CsDatabase** lê a topologia do Lync Server, tenta se conectar a bancos de dados relevantes e, em seguida, relata o êxito ou falha de cada tentativa.</span><span class="sxs-lookup"><span data-stu-id="b9947-114">When run, the **Test-CsDatabase** cmdlet reads the Lync Server topology, attempts to connect to relevant databases, and then reports back the success or failure of each try.</span></span> <span data-ttu-id="b9947-115">Se for possível fazer uma conexão, o cmdlet também reportará essas informações como o nome do banco de dados, as informações de versão do SQL Server e o local de todos os bancos de dados espelhados instalados.</span><span class="sxs-lookup"><span data-stu-id="b9947-115">If a connection can be made, the cmdlet will also report back such information as the database name, SQL Server version information, and the location of any installed mirror databases.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="b9947-116">Executar o teste</span><span class="sxs-lookup"><span data-stu-id="b9947-116">Running the test</span></span>

<span data-ttu-id="b9947-117">O comando mostrado no exemplo 1 verifica a configuração do banco de dados de gerenciamento central.</span><span class="sxs-lookup"><span data-stu-id="b9947-117">The command shown in Example 1 verifies the configuration of the Central Management database.</span></span>

    Test-CsDatabase -CentralManagementDatabase

<span data-ttu-id="b9947-118">O exemplo 2 verifica todos os bancos de dados do Lync Server instalados no computador atl-sql-001.litwareinc.com.</span><span class="sxs-lookup"><span data-stu-id="b9947-118">Example 2 verifies all the Lync Server databases installed on the computer atl-sql-001.litwareinc.com.</span></span>

    Test-CsDatabase -ConfiguredDatabases -SqlServerFqdn "atl-sql-001.litwareinc.com"

<span data-ttu-id="b9947-119">No exemplo 3, a verificação é realizada somente para o banco de dados de arquivamento instalado no computador atl-sql-001.litwareinc.com.</span><span class="sxs-lookup"><span data-stu-id="b9947-119">In Example 3, verification is performed only for the Archiving database installed on the computer atl-sql-001.litwareinc.com.</span></span> <span data-ttu-id="b9947-120">Observe que o parâmetro SQLINSTANCENAME está incluído para especificar a instância do SQL Server (Archinst) em que o banco de dados de arquivamento está localizado.</span><span class="sxs-lookup"><span data-stu-id="b9947-120">Note that the SqlInstanceName parameter is included to specify the SQL Server instance (Archinst) where the Archiving database is located.</span></span>

    Test-CsDatabase -DatabaseType "Archiving" -SqlServerFqdn "atl-sql-001.litwareinc.com" -SqlInstanceName "archinst"

<span data-ttu-id="b9947-121">O comando mostrado no exemplo 4 verifica os bancos de dados instalados no computador local.</span><span class="sxs-lookup"><span data-stu-id="b9947-121">The command shown in Example 4 verifies the databases installed on the local computer.</span></span>

    Test-CsDatabase -LocalService

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="b9947-122">Determinação do sucesso ou falha</span><span class="sxs-lookup"><span data-stu-id="b9947-122">Determining success or failure</span></span>

<span data-ttu-id="b9947-123">Se a conectividade do banco de dados estiver configurada corretamente, você receberá uma saída semelhante a isso, com a propriedade sucede marcada como **verdadeira**:</span><span class="sxs-lookup"><span data-stu-id="b9947-123">If database connectivity is configured correctly, you'll receive output similar to this, with the Succeed property marked as **True**:</span></span>

<span data-ttu-id="b9947-124">SqlServerFqdn: atl-sql-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="b9947-124">SqlServerFqdn : atl-sql-001.litwareinc.com</span></span>

<span data-ttu-id="b9947-125">SQLINSTANCENAME: RTC</span><span class="sxs-lookup"><span data-stu-id="b9947-125">SqlInstanceName : rtc</span></span>

<span data-ttu-id="b9947-126">MirrorSqlServerFqdn :</span><span class="sxs-lookup"><span data-stu-id="b9947-126">MirrorSqlServerFqdn :</span></span>

<span data-ttu-id="b9947-127">MirrorSqlInstanceName :</span><span class="sxs-lookup"><span data-stu-id="b9947-127">MirrorSqlInstanceName :</span></span>

<span data-ttu-id="b9947-128">DatabaseName: XDS</span><span class="sxs-lookup"><span data-stu-id="b9947-128">DatabaseName : xds</span></span>

<span data-ttu-id="b9947-129">Inclusão</span><span class="sxs-lookup"><span data-stu-id="b9947-129">DataSource :</span></span>

<span data-ttu-id="b9947-130">SQLServerVersion :</span><span class="sxs-lookup"><span data-stu-id="b9947-130">SQLServerVersion :</span></span>

<span data-ttu-id="b9947-131">ExpectedVersion : 10.13.2</span><span class="sxs-lookup"><span data-stu-id="b9947-131">ExpectedVersion : 10.13.2</span></span>

<span data-ttu-id="b9947-132">InstalledVersion :</span><span class="sxs-lookup"><span data-stu-id="b9947-132">InstalledVersion :</span></span>

<span data-ttu-id="b9947-133">Êxito: verdadeiro</span><span class="sxs-lookup"><span data-stu-id="b9947-133">Succeed : True</span></span>

<span data-ttu-id="b9947-134">SqlServerFqdn: atl-sql-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="b9947-134">SqlServerFqdn : atl-sql-001.litwareinc.com</span></span>

<span data-ttu-id="b9947-135">SQLINSTANCENAME: RTC</span><span class="sxs-lookup"><span data-stu-id="b9947-135">SqlInstanceName : rtc</span></span>

<span data-ttu-id="b9947-136">MirrorSqlServerFqdn :</span><span class="sxs-lookup"><span data-stu-id="b9947-136">MirrorSqlServerFqdn :</span></span>

<span data-ttu-id="b9947-137">MirrorSqlInstanceName :</span><span class="sxs-lookup"><span data-stu-id="b9947-137">MirrorSqlInstanceName :</span></span>

<span data-ttu-id="b9947-138">DatabaseName: Lis</span><span class="sxs-lookup"><span data-stu-id="b9947-138">DatabaseName : lis</span></span>

<span data-ttu-id="b9947-139">Inclusão</span><span class="sxs-lookup"><span data-stu-id="b9947-139">DataSource :</span></span>

<span data-ttu-id="b9947-140">SQLServerVersion :</span><span class="sxs-lookup"><span data-stu-id="b9947-140">SQLServerVersion :</span></span>

<span data-ttu-id="b9947-141">ExpectedVersion: 3.1.1</span><span class="sxs-lookup"><span data-stu-id="b9947-141">ExpectedVersion : 3.1.1</span></span>

<span data-ttu-id="b9947-142">InstalledVersion :</span><span class="sxs-lookup"><span data-stu-id="b9947-142">InstalledVersion :</span></span>

<span data-ttu-id="b9947-143">Êxito: verdadeiro</span><span class="sxs-lookup"><span data-stu-id="b9947-143">Succeed : True</span></span>

<span data-ttu-id="b9947-144">Se o banco de dados estiver configurado corretamente, mas ainda estiver disponível, o campo bem-sucedido será mostrado como **falso**, e avisos adicionais e informações serão fornecidos:</span><span class="sxs-lookup"><span data-stu-id="b9947-144">If the database is configured correctly but still available, the Succeed field will be shown as **False**, and additional warnings and information will be provided:</span></span>

<span data-ttu-id="b9947-145">SqlServerFqdn: atl-sql-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="b9947-145">SqlServerFqdn : atl-sql-001.litwareinc.com</span></span>

<span data-ttu-id="b9947-146">SQLINSTANCENAME: RTC</span><span class="sxs-lookup"><span data-stu-id="b9947-146">SqlInstanceName : rtc</span></span>

<span data-ttu-id="b9947-147">MirrorSqlServerFqdn :</span><span class="sxs-lookup"><span data-stu-id="b9947-147">MirrorSqlServerFqdn :</span></span>

<span data-ttu-id="b9947-148">MirrorSqlInstanceName :</span><span class="sxs-lookup"><span data-stu-id="b9947-148">MirrorSqlInstanceName :</span></span>

<span data-ttu-id="b9947-149">DatabaseName: XDS</span><span class="sxs-lookup"><span data-stu-id="b9947-149">DatabaseName : xds</span></span>

<span data-ttu-id="b9947-150">Inclusão</span><span class="sxs-lookup"><span data-stu-id="b9947-150">DataSource :</span></span>

<span data-ttu-id="b9947-151">SQLServerVersion :</span><span class="sxs-lookup"><span data-stu-id="b9947-151">SQLServerVersion :</span></span>

<span data-ttu-id="b9947-152">ExpectedVersion : 10.13.2</span><span class="sxs-lookup"><span data-stu-id="b9947-152">ExpectedVersion : 10.13.2</span></span>

<span data-ttu-id="b9947-153">InstalledVersion :</span><span class="sxs-lookup"><span data-stu-id="b9947-153">InstalledVersion :</span></span>

<span data-ttu-id="b9947-154">Bem-sucedido: falso</span><span class="sxs-lookup"><span data-stu-id="b9947-154">Succeed : False</span></span>

<span data-ttu-id="b9947-155">SqlServerFqdn: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="b9947-155">SqlServerFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="b9947-156">SQLINSTANCENAME: RTC</span><span class="sxs-lookup"><span data-stu-id="b9947-156">SqlInstanceName : rtc</span></span>

<span data-ttu-id="b9947-157">MirrorSqlServerFqdn :</span><span class="sxs-lookup"><span data-stu-id="b9947-157">MirrorSqlServerFqdn :</span></span>

<span data-ttu-id="b9947-158">MirrorSqlInstanceName :</span><span class="sxs-lookup"><span data-stu-id="b9947-158">MirrorSqlInstanceName :</span></span>

<span data-ttu-id="b9947-159">DatabaseName: Lis</span><span class="sxs-lookup"><span data-stu-id="b9947-159">DatabaseName : lis</span></span>

<span data-ttu-id="b9947-160">Inclusão</span><span class="sxs-lookup"><span data-stu-id="b9947-160">DataSource :</span></span>

<span data-ttu-id="b9947-161">SQLServerVersion :</span><span class="sxs-lookup"><span data-stu-id="b9947-161">SQLServerVersion :</span></span>

<span data-ttu-id="b9947-162">ExpectedVersion: 3.1.1</span><span class="sxs-lookup"><span data-stu-id="b9947-162">ExpectedVersion : 3.1.1</span></span>

<span data-ttu-id="b9947-163">InstalledVersion :</span><span class="sxs-lookup"><span data-stu-id="b9947-163">InstalledVersion :</span></span>

<span data-ttu-id="b9947-164">Bem-sucedido: falso</span><span class="sxs-lookup"><span data-stu-id="b9947-164">Succeed : False</span></span>

<span data-ttu-id="b9947-165">Aviso: Test-CsDatabase encontrou erros.</span><span class="sxs-lookup"><span data-stu-id="b9947-165">WARNING: Test-CsDatabase encountered errors.</span></span> <span data-ttu-id="b9947-166">Consulte o arquivo de log para obter uma</span><span class="sxs-lookup"><span data-stu-id="b9947-166">Consult the log file for a</span></span>

<span data-ttu-id="b9947-167">análise detalhada e para garantir que todos os erros (2) e avisos (0) sejam tratados</span><span class="sxs-lookup"><span data-stu-id="b9947-167">detailed analysis, and to make sure that all errors (2) and warnings (0) are addressed</span></span>

<span data-ttu-id="b9947-168">antes de continuar.</span><span class="sxs-lookup"><span data-stu-id="b9947-168">before continuing.</span></span>

<span data-ttu-id="b9947-169">Aviso: os resultados detalhados podem ser encontrados em</span><span class="sxs-lookup"><span data-stu-id="b9947-169">WARNING: Detailed results can be found at</span></span>

<span data-ttu-id="b9947-170">"C:\\usuários\\\\testando\\AppData\\local\\2\\Test-CsDatabase-b18d488a-8044-4679-bbf2-</span><span class="sxs-lookup"><span data-stu-id="b9947-170">"C:\\Users\\Testing\\AppData\\Local\\Temp\\2\\Test-CsDatabase-b18d488a-8044-4679-bbf2-</span></span>

<span data-ttu-id="b9947-171">04d593cce8e6. html ".</span><span class="sxs-lookup"><span data-stu-id="b9947-171">04d593cce8e6.html".</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="b9947-172">Motivos pelos quais o teste pode ter falhado</span><span class="sxs-lookup"><span data-stu-id="b9947-172">Reasons why the test might have failed</span></span>

<span data-ttu-id="b9947-173">Aqui estão alguns motivos comuns pelos quais **Test-CsDatabase** pode falhar:</span><span class="sxs-lookup"><span data-stu-id="b9947-173">Here are some common reasons why **Test-CsDatabase** might fail:</span></span>

  - <span data-ttu-id="b9947-174">Um valor de parâmetro incorreto foi fornecido.</span><span class="sxs-lookup"><span data-stu-id="b9947-174">An incorrect parameter value was supplied.</span></span> <span data-ttu-id="b9947-175">Se usado, os parâmetros opcionais devem ser configurados corretamente ou o teste falhará.</span><span class="sxs-lookup"><span data-stu-id="b9947-175">If used, the optional parameters must be configured correctly or the test will fail.</span></span> <span data-ttu-id="b9947-176">Execute o comando novamente sem os parâmetros opcionais e veja se isso é bem-sucedido.</span><span class="sxs-lookup"><span data-stu-id="b9947-176">Rerun the command without the optional parameters and see whether that succeeds.</span></span>

  - <span data-ttu-id="b9947-177">Esse comando falhará se o banco de dados estiver configurado incorretamente ou ainda não foi implantado.</span><span class="sxs-lookup"><span data-stu-id="b9947-177">This command will fail if the database is misconfigured or not yet deployed.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="b9947-178">Confira também</span><span class="sxs-lookup"><span data-stu-id="b9947-178">See Also</span></span>


[<span data-ttu-id="b9947-179">Get-CsDatabaseMirrorState</span><span class="sxs-lookup"><span data-stu-id="b9947-179">Get-CsDatabaseMirrorState</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsDatabaseMirrorState)  
[<span data-ttu-id="b9947-180">Get-CsService</span><span class="sxs-lookup"><span data-stu-id="b9947-180">Get-CsService</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsService)  
[<span data-ttu-id="b9947-181">Get-CsUserDatabaseState</span><span class="sxs-lookup"><span data-stu-id="b9947-181">Get-CsUserDatabaseState</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsUserDatabaseState)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

