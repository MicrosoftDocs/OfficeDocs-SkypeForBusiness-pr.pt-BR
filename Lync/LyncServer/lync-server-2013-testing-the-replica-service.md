---
title: 'Lync Server 2013: testando o serviço de réplica'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing the replica service
ms:assetid: 4ff2cc91-0036-4c5a-9792-7bf43d8ce18d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn727303(v=OCS.15)
ms:contentKeyID: 63969600
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c955da727a4213098a5b6af4f6fbb348bb60dd21
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41745431"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="testing-the-replica-service-in-lync-server-2013"></a><span data-ttu-id="9e9a1-102">Testando o serviço de réplica no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9e9a1-102">Testing the replica service in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9e9a1-103">_**Tópico da última modificação:** 2014-11-03_</span><span class="sxs-lookup"><span data-stu-id="9e9a1-103">_**Topic Last Modified:** 2014-11-03_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="9e9a1-104">Cronograma de verificação</span><span class="sxs-lookup"><span data-stu-id="9e9a1-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="9e9a1-105">Diário</span><span class="sxs-lookup"><span data-stu-id="9e9a1-105">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9e9a1-106">Ferramenta de teste</span><span class="sxs-lookup"><span data-stu-id="9e9a1-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="9e9a1-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="9e9a1-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9e9a1-108">Permissões necessárias</span><span class="sxs-lookup"><span data-stu-id="9e9a1-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="9e9a1-109">Quando executado localmente usando o Shell de gerenciamento do Lync Server, os usuários devem ser membros do grupo de segurança RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="9e9a1-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="9e9a1-110">Quando executado usando uma instância remota do Windows PowerShell, os usuários devem receber uma função RBAC que tenha permissão para executar o cmdlet <strong>Test-CsReplica</strong> .</span><span class="sxs-lookup"><span data-stu-id="9e9a1-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the <strong>Test-CsReplica</strong> cmdlet.</span></span> <span data-ttu-id="9e9a1-111">Para ver uma lista de todas as funções RBAC que podem usar esse cmdlet, execute o seguinte comando no prompt do Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="9e9a1-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsReplica&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="9e9a1-112">Descrição</span><span class="sxs-lookup"><span data-stu-id="9e9a1-112">Description</span></span>

<span data-ttu-id="9e9a1-113">O cmdlet **Test-CsReplica** verifica se o serviço de réplica do Lync Server 2013 está em execução no computador local.</span><span class="sxs-lookup"><span data-stu-id="9e9a1-113">The **Test-CsReplica** cmdlet verifies that the Lync Server 2013 replica service is running on the local computer.</span></span> <span data-ttu-id="9e9a1-114">O cmdlet **Test-CsReplica** executa tarefas como:</span><span class="sxs-lookup"><span data-stu-id="9e9a1-114">The **Test-CsReplica** cmdlet performs such tasks as:</span></span>

  - <span data-ttu-id="9e9a1-115">Verificando o status do agente do Replicator e dos serviços de agente de log centralizado</span><span class="sxs-lookup"><span data-stu-id="9e9a1-115">checking the status of the Replicator Agent and Centralized Logging Agent services</span></span>

  - <span data-ttu-id="9e9a1-116">verificar se as portas necessárias foram abertas no firewall do Windows</span><span class="sxs-lookup"><span data-stu-id="9e9a1-116">verifying that the required ports were opened in the Windows Firewall</span></span>

  - <span data-ttu-id="9e9a1-117">Certifique-se de que os grupos de segurança do Active Directory e do computador local necessários estão presentes.</span><span class="sxs-lookup"><span data-stu-id="9e9a1-117">making sure that the necessary Active Directory and local computer security groups exist.</span></span>

<span data-ttu-id="9e9a1-118">Observe que esse cmdlet deve ser executado localmente.</span><span class="sxs-lookup"><span data-stu-id="9e9a1-118">Note that this cmdlet must be run locally.</span></span> <span data-ttu-id="9e9a1-119">Ou seja, ele deve ser executado no mesmo computador em que o serviço de réplica está em execução.</span><span class="sxs-lookup"><span data-stu-id="9e9a1-119">That is, it must be run on the same computer where the replica service is running.</span></span> <span data-ttu-id="9e9a1-120">Não há nenhuma opção para executar o cmdlet **Test-CsReplica** em um servidor remoto.</span><span class="sxs-lookup"><span data-stu-id="9e9a1-120">There are no options for running the **Test-CsReplica** cmdlet against a remote server.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="9e9a1-121">Executar o teste</span><span class="sxs-lookup"><span data-stu-id="9e9a1-121">Running the test</span></span>

<span data-ttu-id="9e9a1-122">O comando mostrado no exemplo 1 testa o serviço de réplica do Lync Server 2013 no computador local.</span><span class="sxs-lookup"><span data-stu-id="9e9a1-122">The command shown in Example 1 tests the Lync Server 2013 replica service on the local computer.</span></span> <span data-ttu-id="9e9a1-123">Neste exemplo, o parâmetro Verbose é usado para garantir que as informações sobre o teste, incluindo a falha eventual ou o sucesso do teste e a localização do relatório gerado pelo teste – sejam exibidas na tela.</span><span class="sxs-lookup"><span data-stu-id="9e9a1-123">In this example the Verbose parameter is used to guarantee that information about the test – including the eventual failure or success of the test and the location of the report generated by the test – is displayed on screen.</span></span>

    Test-CsReplica -Verbose

<span data-ttu-id="9e9a1-124">O exemplo 2 é uma variação do comando mostrado no exemplo 1.</span><span class="sxs-lookup"><span data-stu-id="9e9a1-124">Example 2 is a variation of the command shown in Example 1.</span></span> <span data-ttu-id="9e9a1-125">Nesse caso, o parâmetro do relatório é incluído para especificar o nome e o caminho da pasta para o relatório gerado pelo teste.</span><span class="sxs-lookup"><span data-stu-id="9e9a1-125">In this case, the Report parameter is included to specify a folder path and name for the report generated by the test.</span></span> <span data-ttu-id="9e9a1-126">Se você não especificar um caminho de relatório, o relatório receberá um nome gerado automaticamente semelhante a este:</span><span class="sxs-lookup"><span data-stu-id="9e9a1-126">If you do not specify a report path the report will be given an auto-generated name similar to this:</span></span>

<span data-ttu-id="9e9a1-127">C:\\Users\\Administrator\\.\\litwareinc\\AppData\\local\\Temp 1 Test-CS-CS-3db40ee0-4b5d-4f58-8d3d-b1e61253129e. html</span><span class="sxs-lookup"><span data-stu-id="9e9a1-127">C:\\Users\\Administrator.Litwareinc\\AppData\\Local\\Temp\\1\\Test-Cs-Replica-3db40ee0-4b5d-4f58-8d3d-b1e61253129e.html</span></span>

    Test-CsReplica -Verbose -Report C:\Logs\ReplicaTest.html

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="9e9a1-128">Determinação do sucesso ou falha</span><span class="sxs-lookup"><span data-stu-id="9e9a1-128">Determining success or failure</span></span>

<span data-ttu-id="9e9a1-129">Inserir o corpo da seção aqui.</span><span class="sxs-lookup"><span data-stu-id="9e9a1-129">Insert section body here.</span></span>

<span data-ttu-id="9e9a1-130">VERBOse: Criando novo arquivo de log "\\C\\:\\usuários\\testando\\os arquivos de log temporários locais\\-CsReplica-3cb066b3-dd23-411A-8932-99f01c0f940c. xml".</span><span class="sxs-lookup"><span data-stu-id="9e9a1-130">VERBOSE: Creating new log file "C:\\Users\\Testing\\AppData\\Local\\Temp\\Test-CsReplica-3cb066b3-dd23-411a-8932-99f01c0f940c.xml".</span></span>

<span data-ttu-id="9e9a1-131">VERBOse: Criando novo arquivo de log "\\C\\:\\usuários\\testando\\os arquivos de log temporários locais\\-CsReplica-3cb066b3-dd23-411A-8932-99f01c0f940c. xml".</span><span class="sxs-lookup"><span data-stu-id="9e9a1-131">VERBOSE: Creating new log file "C:\\Users\\Testing\\AppData\\Local\\Temp\\Test-CsReplica-3cb066b3-dd23-411a-8932-99f01c0f940c.xml".</span></span>

<span data-ttu-id="9e9a1-132">MODO detalhado: o processamento de "Test-CsReplica" foi concluído com êxito.</span><span class="sxs-lookup"><span data-stu-id="9e9a1-132">VERBOSE: "Test-CsReplica" processing has completed successfully.</span></span>

<span data-ttu-id="9e9a1-133">VERBOse: resultados detalhados podem ser encontrados em "\\C\\:\\usuários\\testando os usuários locais\\de\\teste de CsReplica-3cb066b3-dd23-411A-8932-99f01c0f940c. xml".</span><span class="sxs-lookup"><span data-stu-id="9e9a1-133">VERBOSE: Detailed results can be found at "C:\\Users\\Testing\\AppData\\Local\\Temp\\Test-CsReplica-3cb066b3-dd23-411a-8932-99f01c0f940c.xml".</span></span>

<span data-ttu-id="9e9a1-134">VERBOse: Criando um novo arquivo de log</span><span class="sxs-lookup"><span data-stu-id="9e9a1-134">VERBOSE: Creating new log file</span></span>

<span data-ttu-id="9e9a1-135">"C:\\os\\usuários\\testando\\AppData\\\\local\\Temp 2-CsReplica-29fddb35-f56e-4e3c-8f4c-e</span><span class="sxs-lookup"><span data-stu-id="9e9a1-135">"C:\\Users\\Testing\\AppData\\Local\\Temp\\2\\Test-CsReplica-29fddb35-f56e-4e3c-8f4c-e</span></span>

<span data-ttu-id="9e9a1-136">d3bd0e4a083. xml ".</span><span class="sxs-lookup"><span data-stu-id="9e9a1-136">d3bd0e4a083.xml".</span></span>

<span data-ttu-id="9e9a1-137">VERBOse: Criando um novo arquivo de log</span><span class="sxs-lookup"><span data-stu-id="9e9a1-137">VERBOSE: Creating new log file</span></span>

<span data-ttu-id="9e9a1-138">"C:\\os\\usuários\\testando\\AppData\\\\local\\Temp 2-CsReplica-29fddb35-f56e-4e3c-8f4c-e</span><span class="sxs-lookup"><span data-stu-id="9e9a1-138">"C:\\Users\\Testing\\AppData\\Local\\Temp\\2\\Test-CsReplica-29fddb35-f56e-4e3c-8f4c-e</span></span>

<span data-ttu-id="9e9a1-139">d3bd0e4a083. html ".</span><span class="sxs-lookup"><span data-stu-id="9e9a1-139">d3bd0e4a083.html".</span></span>

<span data-ttu-id="9e9a1-140">Aviso: falha de Test-CsReplica.</span><span class="sxs-lookup"><span data-stu-id="9e9a1-140">WARNING: Test-CsReplica failed.</span></span>

<span data-ttu-id="9e9a1-141">Aviso: os resultados detalhados podem ser encontrados em</span><span class="sxs-lookup"><span data-stu-id="9e9a1-141">WARNING: Detailed results can be found at</span></span>

<span data-ttu-id="9e9a1-142">"C:\\os\\usuários\\testando\\AppData\\\\local\\Temp 2-CsReplica-29fddb35-f56e-4e3c-8f4c-e</span><span class="sxs-lookup"><span data-stu-id="9e9a1-142">"C:\\Users\\Testing\\AppData\\Local\\Temp\\2\\Test-CsReplica-29fddb35-f56e-4e3c-8f4c-e</span></span>

<span data-ttu-id="9e9a1-143">d3bd0e4a083. html ".</span><span class="sxs-lookup"><span data-stu-id="9e9a1-143">d3bd0e4a083.html".</span></span>

<span data-ttu-id="9e9a1-144">Test-CsReplica: falha na execução do comando: o acesso do registro solicitado não está</span><span class="sxs-lookup"><span data-stu-id="9e9a1-144">Test-CsReplica : Command execution failed: Requested registry access is not</span></span>

<span data-ttu-id="9e9a1-145">autorizados.</span><span class="sxs-lookup"><span data-stu-id="9e9a1-145">allowed.</span></span>

<span data-ttu-id="9e9a1-146">Na linha: 1 caractere: 1</span><span class="sxs-lookup"><span data-stu-id="9e9a1-146">At line:1 char:1</span></span>

<span data-ttu-id="9e9a1-147">\+Test-CsReplica-Verbose</span><span class="sxs-lookup"><span data-stu-id="9e9a1-147">\+ Test-CsReplica -Verbose</span></span>

\+ ~~~~~~~~~~~~~~~~~~~~~~~

<span data-ttu-id="9e9a1-148">\+CategoryInfo: InvalidOperation: (:) \[Test-CsReplica\], segurança</span><span class="sxs-lookup"><span data-stu-id="9e9a1-148">\+ CategoryInfo : InvalidOperation: (:) \[Test-CsReplica\], Security</span></span>

<span data-ttu-id="9e9a1-149">Extremamente</span><span class="sxs-lookup"><span data-stu-id="9e9a1-149">Exception</span></span>

<span data-ttu-id="9e9a1-150">\+FullyQualifiedErrorId: ProcessingFailed, Microsoft. RTC. Management. Deploy</span><span class="sxs-lookup"><span data-stu-id="9e9a1-150">\+ FullyQualifiedErrorId : ProcessingFailed,Microsoft.Rtc.Management.Deploy</span></span>

<span data-ttu-id="9e9a1-151">atribui. TestReplicaCmdlet</span><span class="sxs-lookup"><span data-stu-id="9e9a1-151">ment.TestReplicaCmdlet</span></span>

<span data-ttu-id="9e9a1-152">PS C:\\testes\\de usuários\></span><span class="sxs-lookup"><span data-stu-id="9e9a1-152">PS C:\\Users\\Testing\></span></span>

<span data-ttu-id="9e9a1-153">PS C:\\usuários\\testando\> Test-CsUcwaConference-TargetFqdn "LyncTest. SelfHost. Corp. M</span><span class="sxs-lookup"><span data-stu-id="9e9a1-153">PS C:\\Users\\Testing\> Test-CsUcwaConference -TargetFqdn "LyncTest.SelfHost.Corp.M</span></span>

<span data-ttu-id="9e9a1-154">icrosoft.com "</span><span class="sxs-lookup"><span data-stu-id="9e9a1-154">icrosoft.com"</span></span>

<span data-ttu-id="9e9a1-155">Aviso: falha ao ler o número da porta do registrador para o número da porta de dados totalmente qualificado</span><span class="sxs-lookup"><span data-stu-id="9e9a1-155">WARNING: Failed to read Registrar port number for the given fully qualified</span></span>

<span data-ttu-id="9e9a1-156">FQDN (nome de domínio).</span><span class="sxs-lookup"><span data-stu-id="9e9a1-156">domain name (FQDN).</span></span> <span data-ttu-id="9e9a1-157">Usando o número da porta do registrador padrão.</span><span class="sxs-lookup"><span data-stu-id="9e9a1-157">Using default Registrar port number.</span></span> <span data-ttu-id="9e9a1-158">Extremamente</span><span class="sxs-lookup"><span data-stu-id="9e9a1-158">Exception:</span></span>

<span data-ttu-id="9e9a1-159">System. InvalidOperationException: nenhum cluster correspondente localizado na topologia.</span><span class="sxs-lookup"><span data-stu-id="9e9a1-159">System.InvalidOperationException: No matching cluster found in topology.</span></span>

<span data-ttu-id="9e9a1-160">como</span><span class="sxs-lookup"><span data-stu-id="9e9a1-160">at</span></span>

<span data-ttu-id="9e9a1-161">Microsoft. RTC. Management. SyntheticTransactions. SipSyntheticTransaction. TryRetri</span><span class="sxs-lookup"><span data-stu-id="9e9a1-161">Microsoft.Rtc.Management.SyntheticTransactions.SipSyntheticTransaction.TryRetri</span></span>

<span data-ttu-id="9e9a1-162">eveRegistrarPortFromTopology (Int32& registrarPortNumber)</span><span class="sxs-lookup"><span data-stu-id="9e9a1-162">eveRegistrarPortFromTopology(Int32& registrarPortNumber)</span></span>

<span data-ttu-id="9e9a1-163">Test-CsUcwaConference: não há um usuário de teste atribuído para</span><span class="sxs-lookup"><span data-stu-id="9e9a1-163">Test-CsUcwaConference : There is no test user assigned for</span></span>

<span data-ttu-id="9e9a1-164">\[LyncTest.SelfHost.Corp.Microsoft.com\].</span><span class="sxs-lookup"><span data-stu-id="9e9a1-164">\[LyncTest.SelfHost.Corp.Microsoft.com\].</span></span> <span data-ttu-id="9e9a1-165">Verifique a configuração do usuário do teste.</span><span class="sxs-lookup"><span data-stu-id="9e9a1-165">Verify test user configuration.</span></span>

<span data-ttu-id="9e9a1-166">Na linha: 1 caractere: 1</span><span class="sxs-lookup"><span data-stu-id="9e9a1-166">At line:1 char:1</span></span>

<span data-ttu-id="9e9a1-167">\+Test-CsUcwaConference-TargetFqdn "LyncTest.SelfHost.Corp.Microsoft.com"</span><span class="sxs-lookup"><span data-stu-id="9e9a1-167">\+ Test-CsUcwaConference -TargetFqdn "LyncTest.SelfHost.Corp.Microsoft.com"</span></span>

\+ ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

<span data-ttu-id="9e9a1-168">\+CategoryInfo: ResourceUnavailable: (:) \[Test-CsUcwaConference\]</span><span class="sxs-lookup"><span data-stu-id="9e9a1-168">\+ CategoryInfo : ResourceUnavailable: (:) \[Test-CsUcwaConference\]</span></span>

<span data-ttu-id="9e9a1-169">, InvalidOperationException</span><span class="sxs-lookup"><span data-stu-id="9e9a1-169">, InvalidOperationException</span></span>

<span data-ttu-id="9e9a1-170">\+FullyQualifiedErrorId: NotFoundTestUsers, Microsoft. RTC. Management. sintetizador</span><span class="sxs-lookup"><span data-stu-id="9e9a1-170">\+ FullyQualifiedErrorId : NotFoundTestUsers,Microsoft.Rtc.Management.Synth</span></span>

<span data-ttu-id="9e9a1-171">eticTransactions.TestUcwaConferenceCmdlet</span><span class="sxs-lookup"><span data-stu-id="9e9a1-171">eticTransactions.TestUcwaConferenceCmdlet</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="9e9a1-172">Motivos pelos quais o teste pode ter falhado</span><span class="sxs-lookup"><span data-stu-id="9e9a1-172">Reasons why the test might have failed</span></span>

<span data-ttu-id="9e9a1-173">Aqui estão alguns motivos comuns pelos quais **Test-CsReplica** pode falhar:</span><span class="sxs-lookup"><span data-stu-id="9e9a1-173">Here are some common reasons why **Test-CsReplica** might fail:</span></span>

  - <span data-ttu-id="9e9a1-174">Pode haver um problema maior com o agente do Replicator e os serviços de agente de log centralizado</span><span class="sxs-lookup"><span data-stu-id="9e9a1-174">There may be a larger problem with the Replicator Agent and Centralized Logging Agent services</span></span>

  - <span data-ttu-id="9e9a1-175">As portas necessárias podem não estar abertas no firewall do Windows</span><span class="sxs-lookup"><span data-stu-id="9e9a1-175">The required ports may not be open in the Windows Firewall</span></span>

  - <span data-ttu-id="9e9a1-176">Os grupos de segurança do Active Directory e do computador local necessários podem não existir</span><span class="sxs-lookup"><span data-stu-id="9e9a1-176">The necessary Active Directory and local computer security groups may not exist</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

