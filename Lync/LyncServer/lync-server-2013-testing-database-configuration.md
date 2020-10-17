---
title: 'Lync Server 2013: testar configuração de banco de dados'
description: 'Lync Server 2013: testar configuração de banco de dados.'
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
ms.openlocfilehash: 2b9f88eee99c4a2d523cc84df401dcc1d7b9fe59
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48560677"
---
# <a name="testing-database-configuration-in-lync-server-2013"></a><span data-ttu-id="b5a15-103">Testando a configuração do banco de dados no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b5a15-103">Testing database configuration in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b5a15-104">_**Última modificação do tópico:** 2016-07-07_</span><span class="sxs-lookup"><span data-stu-id="b5a15-104">_**Topic Last Modified:** 2016-07-07_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b5a15-105">Agenda de verificação</span><span class="sxs-lookup"><span data-stu-id="b5a15-105">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="b5a15-106">Diariamente</span><span class="sxs-lookup"><span data-stu-id="b5a15-106">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b5a15-107">Ferramenta de teste</span><span class="sxs-lookup"><span data-stu-id="b5a15-107">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="b5a15-108">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="b5a15-108">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b5a15-109">Permissões obrigatórias</span><span class="sxs-lookup"><span data-stu-id="b5a15-109">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="b5a15-110">Ao executar localmente usando o Shell de gerenciamento do Lync Server, os usuários devem ser membros do grupo de segurança RTCUniversalServerAdmins e ter privilégios de administrador no SQL Server.</span><span class="sxs-lookup"><span data-stu-id="b5a15-110">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group, and need to have Administrator privileges on the SQL server.</span></span></p>
<p><span data-ttu-id="b5a15-111">Quando executado usando uma instância remota do Windows PowerShell, os usuários devem receber uma função RBAC que tenha permissão para executar o cmdlet <strong>Test-CsDatabase</strong> .</span><span class="sxs-lookup"><span data-stu-id="b5a15-111">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the <strong>Test-CsDatabase</strong> cmdlet.</span></span> <span data-ttu-id="b5a15-112">Para ver uma lista de todas as funções RBAC que podem usar este cmdlet, execute o seguinte comando no prompt do Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="b5a15-112">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsDatabase&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="b5a15-113">Descrição</span><span class="sxs-lookup"><span data-stu-id="b5a15-113">Description</span></span>

<span data-ttu-id="b5a15-114">O cmdlet **Test-CsDatabase** verifica a conectividade para um ou mais bancos de dados do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="b5a15-114">The **Test-CsDatabase** cmdlet verifies connectivity to one or more Lync Server 2013 databases.</span></span> <span data-ttu-id="b5a15-115">Quando executado, o cmdlet **Test-CsDatabase** lê a topologia do Lync Server, tenta se conectar a bancos de dados relevantes e, em seguida, relata o êxito ou falha de cada tentativa.</span><span class="sxs-lookup"><span data-stu-id="b5a15-115">When run, the **Test-CsDatabase** cmdlet reads the Lync Server topology, attempts to connect to relevant databases, and then reports back the success or failure of each try.</span></span> <span data-ttu-id="b5a15-116">Se uma conexão pode ser realizada, o cmdlet também relatará tal informação como o nome do banco de dados, a informação de versão do SQL Server e o local de qualquer banco de dados espelho instalado.</span><span class="sxs-lookup"><span data-stu-id="b5a15-116">If a connection can be made, the cmdlet will also report back such information as the database name, SQL Server version information, and the location of any installed mirror databases.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="b5a15-117">Executar o teste</span><span class="sxs-lookup"><span data-stu-id="b5a15-117">Running the test</span></span>

<span data-ttu-id="b5a15-118">O comando mostrado no Exemplo 1 verifica a configuração do banco de dados de Gerenciamento Central.</span><span class="sxs-lookup"><span data-stu-id="b5a15-118">The command shown in Example 1 verifies the configuration of the Central Management database.</span></span>

    Test-CsDatabase -CentralManagementDatabase

<span data-ttu-id="b5a15-119">O exemplo 2 verifica todos os bancos de dados do Lync Server instalados no computador atl-sql-001.litwareinc.com.</span><span class="sxs-lookup"><span data-stu-id="b5a15-119">Example 2 verifies all the Lync Server databases installed on the computer atl-sql-001.litwareinc.com.</span></span>

    Test-CsDatabase -ConfiguredDatabases -SqlServerFqdn "atl-sql-001.litwareinc.com"

<span data-ttu-id="b5a15-p103">No Exemplo 3, a verificação é realizada apenas para o banco de dados de Arquivamento instalado no computador atl-sql-001.litwareinc.com. Observe que o parâmetro SqlInstanceName está incluído para especificar a instância do SQL Server (Archinst) onde o banco de dados de Arquivamento está localizado.</span><span class="sxs-lookup"><span data-stu-id="b5a15-p103">In Example 3, verification is performed only for the Archiving database installed on the computer atl-sql-001.litwareinc.com. Note that the SqlInstanceName parameter is included to specify the SQL Server instance (Archinst) where the Archiving database is located.</span></span>

    Test-CsDatabase -DatabaseType "Archiving" -SqlServerFqdn "atl-sql-001.litwareinc.com" -SqlInstanceName "archinst"

<span data-ttu-id="b5a15-122">O comando mostrado no Exemplo 4 verifica os bancos de dados instalados no computador local.</span><span class="sxs-lookup"><span data-stu-id="b5a15-122">The command shown in Example 4 verifies the databases installed on the local computer.</span></span>

    Test-CsDatabase -LocalService

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="b5a15-123">Determinando o sucesso ou a falha</span><span class="sxs-lookup"><span data-stu-id="b5a15-123">Determining success or failure</span></span>

<span data-ttu-id="b5a15-124">Se a conectividade do banco de dados estiver configurada corretamente, você receberá uma saída semelhante a essa, com a propriedade sucede marcada como **true**:</span><span class="sxs-lookup"><span data-stu-id="b5a15-124">If database connectivity is configured correctly, you'll receive output similar to this, with the Succeed property marked as **True**:</span></span>

<span data-ttu-id="b5a15-125">SqlServerFqdn: atl-sql-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="b5a15-125">SqlServerFqdn : atl-sql-001.litwareinc.com</span></span>

<span data-ttu-id="b5a15-126">SQLINSTANCENAME: RTC</span><span class="sxs-lookup"><span data-stu-id="b5a15-126">SqlInstanceName : rtc</span></span>

<span data-ttu-id="b5a15-127">MirrorSqlServerFqdn :</span><span class="sxs-lookup"><span data-stu-id="b5a15-127">MirrorSqlServerFqdn :</span></span>

<span data-ttu-id="b5a15-128">MirrorSqlInstanceName :</span><span class="sxs-lookup"><span data-stu-id="b5a15-128">MirrorSqlInstanceName :</span></span>

<span data-ttu-id="b5a15-129">DatabaseName: XDS</span><span class="sxs-lookup"><span data-stu-id="b5a15-129">DatabaseName : xds</span></span>

<span data-ttu-id="b5a15-130">DataSource</span><span class="sxs-lookup"><span data-stu-id="b5a15-130">DataSource :</span></span>

<span data-ttu-id="b5a15-131">SQLServerVersion :</span><span class="sxs-lookup"><span data-stu-id="b5a15-131">SQLServerVersion :</span></span>

<span data-ttu-id="b5a15-132">ExpectedVersion : 10.13.2</span><span class="sxs-lookup"><span data-stu-id="b5a15-132">ExpectedVersion : 10.13.2</span></span>

<span data-ttu-id="b5a15-133">InstalledVersion :</span><span class="sxs-lookup"><span data-stu-id="b5a15-133">InstalledVersion :</span></span>

<span data-ttu-id="b5a15-134">Êxito: true</span><span class="sxs-lookup"><span data-stu-id="b5a15-134">Succeed : True</span></span>

<span data-ttu-id="b5a15-135">SqlServerFqdn: atl-sql-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="b5a15-135">SqlServerFqdn : atl-sql-001.litwareinc.com</span></span>

<span data-ttu-id="b5a15-136">SQLINSTANCENAME: RTC</span><span class="sxs-lookup"><span data-stu-id="b5a15-136">SqlInstanceName : rtc</span></span>

<span data-ttu-id="b5a15-137">MirrorSqlServerFqdn :</span><span class="sxs-lookup"><span data-stu-id="b5a15-137">MirrorSqlServerFqdn :</span></span>

<span data-ttu-id="b5a15-138">MirrorSqlInstanceName :</span><span class="sxs-lookup"><span data-stu-id="b5a15-138">MirrorSqlInstanceName :</span></span>

<span data-ttu-id="b5a15-139">DatabaseName: Lis</span><span class="sxs-lookup"><span data-stu-id="b5a15-139">DatabaseName : lis</span></span>

<span data-ttu-id="b5a15-140">DataSource</span><span class="sxs-lookup"><span data-stu-id="b5a15-140">DataSource :</span></span>

<span data-ttu-id="b5a15-141">SQLServerVersion :</span><span class="sxs-lookup"><span data-stu-id="b5a15-141">SQLServerVersion :</span></span>

<span data-ttu-id="b5a15-142">ExpectedVersion : 3.1.1</span><span class="sxs-lookup"><span data-stu-id="b5a15-142">ExpectedVersion : 3.1.1</span></span>

<span data-ttu-id="b5a15-143">InstalledVersion :</span><span class="sxs-lookup"><span data-stu-id="b5a15-143">InstalledVersion :</span></span>

<span data-ttu-id="b5a15-144">Êxito: true</span><span class="sxs-lookup"><span data-stu-id="b5a15-144">Succeed : True</span></span>

<span data-ttu-id="b5a15-145">Se o banco de dados estiver configurado corretamente, mas ainda estiver disponível, o campo bem-sucedido será mostrado como **falso**, e avisos e informações adicionais serão fornecidos:</span><span class="sxs-lookup"><span data-stu-id="b5a15-145">If the database is configured correctly but still available, the Succeed field will be shown as **False**, and additional warnings and information will be provided:</span></span>

<span data-ttu-id="b5a15-146">SqlServerFqdn: atl-sql-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="b5a15-146">SqlServerFqdn : atl-sql-001.litwareinc.com</span></span>

<span data-ttu-id="b5a15-147">SQLINSTANCENAME: RTC</span><span class="sxs-lookup"><span data-stu-id="b5a15-147">SqlInstanceName : rtc</span></span>

<span data-ttu-id="b5a15-148">MirrorSqlServerFqdn :</span><span class="sxs-lookup"><span data-stu-id="b5a15-148">MirrorSqlServerFqdn :</span></span>

<span data-ttu-id="b5a15-149">MirrorSqlInstanceName :</span><span class="sxs-lookup"><span data-stu-id="b5a15-149">MirrorSqlInstanceName :</span></span>

<span data-ttu-id="b5a15-150">DatabaseName: XDS</span><span class="sxs-lookup"><span data-stu-id="b5a15-150">DatabaseName : xds</span></span>

<span data-ttu-id="b5a15-151">DataSource</span><span class="sxs-lookup"><span data-stu-id="b5a15-151">DataSource :</span></span>

<span data-ttu-id="b5a15-152">SQLServerVersion :</span><span class="sxs-lookup"><span data-stu-id="b5a15-152">SQLServerVersion :</span></span>

<span data-ttu-id="b5a15-153">ExpectedVersion : 10.13.2</span><span class="sxs-lookup"><span data-stu-id="b5a15-153">ExpectedVersion : 10.13.2</span></span>

<span data-ttu-id="b5a15-154">InstalledVersion :</span><span class="sxs-lookup"><span data-stu-id="b5a15-154">InstalledVersion :</span></span>

<span data-ttu-id="b5a15-155">Êxito: falso</span><span class="sxs-lookup"><span data-stu-id="b5a15-155">Succeed : False</span></span>

<span data-ttu-id="b5a15-156">SqlServerFqdn: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="b5a15-156">SqlServerFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="b5a15-157">SQLINSTANCENAME: RTC</span><span class="sxs-lookup"><span data-stu-id="b5a15-157">SqlInstanceName : rtc</span></span>

<span data-ttu-id="b5a15-158">MirrorSqlServerFqdn :</span><span class="sxs-lookup"><span data-stu-id="b5a15-158">MirrorSqlServerFqdn :</span></span>

<span data-ttu-id="b5a15-159">MirrorSqlInstanceName :</span><span class="sxs-lookup"><span data-stu-id="b5a15-159">MirrorSqlInstanceName :</span></span>

<span data-ttu-id="b5a15-160">DatabaseName: Lis</span><span class="sxs-lookup"><span data-stu-id="b5a15-160">DatabaseName : lis</span></span>

<span data-ttu-id="b5a15-161">DataSource</span><span class="sxs-lookup"><span data-stu-id="b5a15-161">DataSource :</span></span>

<span data-ttu-id="b5a15-162">SQLServerVersion :</span><span class="sxs-lookup"><span data-stu-id="b5a15-162">SQLServerVersion :</span></span>

<span data-ttu-id="b5a15-163">ExpectedVersion : 3.1.1</span><span class="sxs-lookup"><span data-stu-id="b5a15-163">ExpectedVersion : 3.1.1</span></span>

<span data-ttu-id="b5a15-164">InstalledVersion :</span><span class="sxs-lookup"><span data-stu-id="b5a15-164">InstalledVersion :</span></span>

<span data-ttu-id="b5a15-165">Êxito: falso</span><span class="sxs-lookup"><span data-stu-id="b5a15-165">Succeed : False</span></span>

<span data-ttu-id="b5a15-166">Aviso: Test-CsDatabase encontrou erros.</span><span class="sxs-lookup"><span data-stu-id="b5a15-166">WARNING: Test-CsDatabase encountered errors.</span></span> <span data-ttu-id="b5a15-167">Consulte o arquivo de log para obter um</span><span class="sxs-lookup"><span data-stu-id="b5a15-167">Consult the log file for a</span></span>

<span data-ttu-id="b5a15-168">análise detalhada e para garantir que todos os erros (2) e avisos (0) sejam tratados</span><span class="sxs-lookup"><span data-stu-id="b5a15-168">detailed analysis, and to make sure that all errors (2) and warnings (0) are addressed</span></span>

<span data-ttu-id="b5a15-169">antes de continuar.</span><span class="sxs-lookup"><span data-stu-id="b5a15-169">before continuing.</span></span>

<span data-ttu-id="b5a15-170">Aviso: resultados detalhados podem ser encontrados em</span><span class="sxs-lookup"><span data-stu-id="b5a15-170">WARNING: Detailed results can be found at</span></span>

<span data-ttu-id="b5a15-171">"C: \\ os usuários que estão \\ testando o \\ \\ local \\ temp \\ 2 \\ Test-CsDatabase-b18d488a-8044-4679-bbf2-</span><span class="sxs-lookup"><span data-stu-id="b5a15-171">"C:\\Users\\Testing\\AppData\\Local\\Temp\\2\\Test-CsDatabase-b18d488a-8044-4679-bbf2-</span></span>

<span data-ttu-id="b5a15-172">04d593cce8e6.html ".</span><span class="sxs-lookup"><span data-stu-id="b5a15-172">04d593cce8e6.html".</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="b5a15-173">Motivos pelos quais o teste pode ter falhado</span><span class="sxs-lookup"><span data-stu-id="b5a15-173">Reasons why the test might have failed</span></span>

<span data-ttu-id="b5a15-174">Aqui estão alguns motivos comuns pelos quais **Test-CsDatabase** pode falhar:</span><span class="sxs-lookup"><span data-stu-id="b5a15-174">Here are some common reasons why **Test-CsDatabase** might fail:</span></span>

  - <span data-ttu-id="b5a15-175">Um valor de parâmetro incorreto foi fornecido.</span><span class="sxs-lookup"><span data-stu-id="b5a15-175">An incorrect parameter value was supplied.</span></span> <span data-ttu-id="b5a15-176">Se usado, os parâmetros opcionais devem ser configurados corretamente ou o teste falhará.</span><span class="sxs-lookup"><span data-stu-id="b5a15-176">If used, the optional parameters must be configured correctly or the test will fail.</span></span> <span data-ttu-id="b5a15-177">Execute novamente o comando sem os parâmetros opcionais e veja se isso é bem-sucedido.</span><span class="sxs-lookup"><span data-stu-id="b5a15-177">Rerun the command without the optional parameters and see whether that succeeds.</span></span>

  - <span data-ttu-id="b5a15-178">Esse comando falhará se o banco de dados estiver configurado incorretamente ou ainda não tiver sido implantado.</span><span class="sxs-lookup"><span data-stu-id="b5a15-178">This command will fail if the database is misconfigured or not yet deployed.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="b5a15-179">Confira também</span><span class="sxs-lookup"><span data-stu-id="b5a15-179">See Also</span></span>


[<span data-ttu-id="b5a15-180">Get-CsDatabaseMirrorState</span><span class="sxs-lookup"><span data-stu-id="b5a15-180">Get-CsDatabaseMirrorState</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsDatabaseMirrorState)  
[<span data-ttu-id="b5a15-181">Get-CsService</span><span class="sxs-lookup"><span data-stu-id="b5a15-181">Get-CsService</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsService)  
[<span data-ttu-id="b5a15-182">Get-CsUserDatabaseState</span><span class="sxs-lookup"><span data-stu-id="b5a15-182">Get-CsUserDatabaseState</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsUserDatabaseState)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

