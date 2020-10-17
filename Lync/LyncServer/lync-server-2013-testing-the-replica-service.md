---
title: 'Lync Server 2013: testar o serviço de réplica'
description: 'Lync Server 2013: testar o serviço de réplica.'
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
ms.openlocfilehash: a61751b95115da3d6519f20f52262b7159ffcbfe
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48556157"
---
# <a name="testing-the-replica-service-in-lync-server-2013"></a><span data-ttu-id="7bd7a-103">Testando o serviço de réplica no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7bd7a-103">Testing the replica service in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7bd7a-104">_**Última modificação do tópico:** 2014-11-03_</span><span class="sxs-lookup"><span data-stu-id="7bd7a-104">_**Topic Last Modified:** 2014-11-03_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="7bd7a-105">Agenda de verificação</span><span class="sxs-lookup"><span data-stu-id="7bd7a-105">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="7bd7a-106">Diariamente</span><span class="sxs-lookup"><span data-stu-id="7bd7a-106">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7bd7a-107">Ferramenta de teste</span><span class="sxs-lookup"><span data-stu-id="7bd7a-107">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="7bd7a-108">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="7bd7a-108">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7bd7a-109">Permissões obrigatórias</span><span class="sxs-lookup"><span data-stu-id="7bd7a-109">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="7bd7a-110">Ao executar localmente usando o Shell de gerenciamento do Lync Server, os usuários devem ser membros do grupo de segurança RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="7bd7a-110">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="7bd7a-111">Quando executado usando uma instância remota do Windows PowerShell, os usuários devem receber uma função RBAC que tenha permissão para executar o cmdlet <strong>Test-CsReplica</strong> .</span><span class="sxs-lookup"><span data-stu-id="7bd7a-111">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the <strong>Test-CsReplica</strong> cmdlet.</span></span> <span data-ttu-id="7bd7a-112">Para ver uma lista de todas as funções RBAC que podem usar este cmdlet, execute o seguinte comando no prompt do Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="7bd7a-112">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsReplica&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="7bd7a-113">Descrição</span><span class="sxs-lookup"><span data-stu-id="7bd7a-113">Description</span></span>

<span data-ttu-id="7bd7a-114">O cmdlet **Test-CsReplica** verifica se o serviço de réplica do Lync Server 2013 está em execução no computador local.</span><span class="sxs-lookup"><span data-stu-id="7bd7a-114">The **Test-CsReplica** cmdlet verifies that the Lync Server 2013 replica service is running on the local computer.</span></span> <span data-ttu-id="7bd7a-115">O cmdlet **Test-CsReplica** executa tarefas como:</span><span class="sxs-lookup"><span data-stu-id="7bd7a-115">The **Test-CsReplica** cmdlet performs such tasks as:</span></span>

  - <span data-ttu-id="7bd7a-116">Verificando o status do agente do Replicator e dos serviços de agente de registro em log centralizado</span><span class="sxs-lookup"><span data-stu-id="7bd7a-116">checking the status of the Replicator Agent and Centralized Logging Agent services</span></span>

  - <span data-ttu-id="7bd7a-117">verificando se as portas necessárias foram abertas no firewall do Windows</span><span class="sxs-lookup"><span data-stu-id="7bd7a-117">verifying that the required ports were opened in the Windows Firewall</span></span>

  - <span data-ttu-id="7bd7a-118">garantir que exista o Active Directory e os grupos de segurança do computador local necessários.</span><span class="sxs-lookup"><span data-stu-id="7bd7a-118">making sure that the necessary Active Directory and local computer security groups exist.</span></span>

<span data-ttu-id="7bd7a-119">Observe que esse cmdlet deve ser executado localmente.</span><span class="sxs-lookup"><span data-stu-id="7bd7a-119">Note that this cmdlet must be run locally.</span></span> <span data-ttu-id="7bd7a-120">Ou seja, ele deve ser executado no mesmo computador em que o serviço de réplica está em execução.</span><span class="sxs-lookup"><span data-stu-id="7bd7a-120">That is, it must be run on the same computer where the replica service is running.</span></span> <span data-ttu-id="7bd7a-121">Não há opções para executar o cmdlet **Test-CsReplica** em um servidor remoto.</span><span class="sxs-lookup"><span data-stu-id="7bd7a-121">There are no options for running the **Test-CsReplica** cmdlet against a remote server.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="7bd7a-122">Executar o teste</span><span class="sxs-lookup"><span data-stu-id="7bd7a-122">Running the test</span></span>

<span data-ttu-id="7bd7a-123">O comando mostrado no exemplo 1 testa o serviço de réplica do Lync Server 2013 no computador local.</span><span class="sxs-lookup"><span data-stu-id="7bd7a-123">The command shown in Example 1 tests the Lync Server 2013 replica service on the local computer.</span></span> <span data-ttu-id="7bd7a-124">Neste exemplo, o parâmetro Verbose é usado para garantir que as informações sobre o teste – incluindo a falha eventual ou o sucesso do teste e o local do relatório gerado pelo teste – sejam exibidos na tela.</span><span class="sxs-lookup"><span data-stu-id="7bd7a-124">In this example the Verbose parameter is used to guarantee that information about the test – including the eventual failure or success of the test and the location of the report generated by the test – is displayed on screen.</span></span>

    Test-CsReplica -Verbose

<span data-ttu-id="7bd7a-125">O Exemplo 2 é uma variação do comando exibido no Exemplo 1.</span><span class="sxs-lookup"><span data-stu-id="7bd7a-125">Example 2 is a variation of the command shown in Example 1.</span></span> <span data-ttu-id="7bd7a-126">Nesse caso, o parâmetro Report é incluído para especificar um caminho de pasta e nome para o relatório gerado pelo teste.</span><span class="sxs-lookup"><span data-stu-id="7bd7a-126">In this case, the Report parameter is included to specify a folder path and name for the report generated by the test.</span></span> <span data-ttu-id="7bd7a-127">Se você não especificar um caminho de relatório, o relatório receberá um nome gerado automaticamente parecido com o seguinte:</span><span class="sxs-lookup"><span data-stu-id="7bd7a-127">If you do not specify a report path the report will be given an auto-generated name similar to this:</span></span>

<span data-ttu-id="7bd7a-128">C: \\ Users \\ Administrator. litwareinc \\ AppData \\ local \\ temp \\ 1 \\Test-Cs-Replica-3db40ee0-4b5d-4f58-8d3d-b1e61253129e.html</span><span class="sxs-lookup"><span data-stu-id="7bd7a-128">C:\\Users\\Administrator.Litwareinc\\AppData\\Local\\Temp\\1\\Test-Cs-Replica-3db40ee0-4b5d-4f58-8d3d-b1e61253129e.html</span></span>

    Test-CsReplica -Verbose -Report C:\Logs\ReplicaTest.html

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="7bd7a-129">Determinando o sucesso ou a falha</span><span class="sxs-lookup"><span data-stu-id="7bd7a-129">Determining success or failure</span></span>

<span data-ttu-id="7bd7a-130">Insira o corpo da seção aqui.</span><span class="sxs-lookup"><span data-stu-id="7bd7a-130">Insert section body here.</span></span>

<span data-ttu-id="7bd7a-131">VERBOse: Criando novo arquivo de log "C: \\ usuários \\ testando \\ \\ \\Test-CsReplica-3cb066b3-dd23-411a-8932-99f01c0f940c.xml Temp local \\ ".</span><span class="sxs-lookup"><span data-stu-id="7bd7a-131">VERBOSE: Creating new log file "C:\\Users\\Testing\\AppData\\Local\\Temp\\Test-CsReplica-3cb066b3-dd23-411a-8932-99f01c0f940c.xml".</span></span>

<span data-ttu-id="7bd7a-132">VERBOse: Criando novo arquivo de log "C: \\ usuários \\ testando \\ \\ \\Test-CsReplica-3cb066b3-dd23-411a-8932-99f01c0f940c.xml Temp local \\ ".</span><span class="sxs-lookup"><span data-stu-id="7bd7a-132">VERBOSE: Creating new log file "C:\\Users\\Testing\\AppData\\Local\\Temp\\Test-CsReplica-3cb066b3-dd23-411a-8932-99f01c0f940c.xml".</span></span>

<span data-ttu-id="7bd7a-133">VERBOse: o processamento de "Test-CsReplica" foi concluído com êxito.</span><span class="sxs-lookup"><span data-stu-id="7bd7a-133">VERBOSE: "Test-CsReplica" processing has completed successfully.</span></span>

<span data-ttu-id="7bd7a-134">VERBOse: resultados detalhados podem ser encontrados em "C: \\ Users \\ Testing \\ \\ local \\ temp \\Test-CsReplica-3cb066b3-dd23-411a-8932-99f01c0f940c.xml".</span><span class="sxs-lookup"><span data-stu-id="7bd7a-134">VERBOSE: Detailed results can be found at "C:\\Users\\Testing\\AppData\\Local\\Temp\\Test-CsReplica-3cb066b3-dd23-411a-8932-99f01c0f940c.xml".</span></span>

<span data-ttu-id="7bd7a-135">VERBOse: Criando novo arquivo de log</span><span class="sxs-lookup"><span data-stu-id="7bd7a-135">VERBOSE: Creating new log file</span></span>

<span data-ttu-id="7bd7a-136">"C: \\ os usuários que estão \\ testando o \\ \\ local \\ temp \\ 2 \\ Test-CsReplica-29fddb35-f56e-4e3c-8f4c-e</span><span class="sxs-lookup"><span data-stu-id="7bd7a-136">"C:\\Users\\Testing\\AppData\\Local\\Temp\\2\\Test-CsReplica-29fddb35-f56e-4e3c-8f4c-e</span></span>

<span data-ttu-id="7bd7a-137">d3bd0e4a083.xml ".</span><span class="sxs-lookup"><span data-stu-id="7bd7a-137">d3bd0e4a083.xml".</span></span>

<span data-ttu-id="7bd7a-138">VERBOse: Criando novo arquivo de log</span><span class="sxs-lookup"><span data-stu-id="7bd7a-138">VERBOSE: Creating new log file</span></span>

<span data-ttu-id="7bd7a-139">"C: \\ os usuários que estão \\ testando o \\ \\ local \\ temp \\ 2 \\ Test-CsReplica-29fddb35-f56e-4e3c-8f4c-e</span><span class="sxs-lookup"><span data-stu-id="7bd7a-139">"C:\\Users\\Testing\\AppData\\Local\\Temp\\2\\Test-CsReplica-29fddb35-f56e-4e3c-8f4c-e</span></span>

<span data-ttu-id="7bd7a-140">d3bd0e4a083.html ".</span><span class="sxs-lookup"><span data-stu-id="7bd7a-140">d3bd0e4a083.html".</span></span>

<span data-ttu-id="7bd7a-141">Aviso: falha na Test-CsReplica.</span><span class="sxs-lookup"><span data-stu-id="7bd7a-141">WARNING: Test-CsReplica failed.</span></span>

<span data-ttu-id="7bd7a-142">Aviso: resultados detalhados podem ser encontrados em</span><span class="sxs-lookup"><span data-stu-id="7bd7a-142">WARNING: Detailed results can be found at</span></span>

<span data-ttu-id="7bd7a-143">"C: \\ os usuários que estão \\ testando o \\ \\ local \\ temp \\ 2 \\ Test-CsReplica-29fddb35-f56e-4e3c-8f4c-e</span><span class="sxs-lookup"><span data-stu-id="7bd7a-143">"C:\\Users\\Testing\\AppData\\Local\\Temp\\2\\Test-CsReplica-29fddb35-f56e-4e3c-8f4c-e</span></span>

<span data-ttu-id="7bd7a-144">d3bd0e4a083.html ".</span><span class="sxs-lookup"><span data-stu-id="7bd7a-144">d3bd0e4a083.html".</span></span>

<span data-ttu-id="7bd7a-145">Test-CsReplica: falha na execução do comando: o acesso ao registro solicitado não é</span><span class="sxs-lookup"><span data-stu-id="7bd7a-145">Test-CsReplica : Command execution failed: Requested registry access is not</span></span>

<span data-ttu-id="7bd7a-146">autorizado.</span><span class="sxs-lookup"><span data-stu-id="7bd7a-146">allowed.</span></span>

<span data-ttu-id="7bd7a-147">Na linha: 1 caractere: 1</span><span class="sxs-lookup"><span data-stu-id="7bd7a-147">At line:1 char:1</span></span>

<span data-ttu-id="7bd7a-148">\+ Test-CsReplica-Verbose</span><span class="sxs-lookup"><span data-stu-id="7bd7a-148">\+ Test-CsReplica -Verbose</span></span>

\+ ~~~~~~~~~~~~~~~~~~~~~~~

<span data-ttu-id="7bd7a-149">\+ CategoryInfo: InvalidOperation: (:) \[ Test-CsReplica \] , segurança</span><span class="sxs-lookup"><span data-stu-id="7bd7a-149">\+ CategoryInfo : InvalidOperation: (:) \[Test-CsReplica\], Security</span></span>

<span data-ttu-id="7bd7a-150">Exception</span><span class="sxs-lookup"><span data-stu-id="7bd7a-150">Exception</span></span>

<span data-ttu-id="7bd7a-151">\+ FullyQualifiedErrorId: ProcessingFailed, Microsoft. RTC. Management. Deploy</span><span class="sxs-lookup"><span data-stu-id="7bd7a-151">\+ FullyQualifiedErrorId : ProcessingFailed,Microsoft.Rtc.Management.Deploy</span></span>

<span data-ttu-id="7bd7a-152">atribui. TestReplicaCmdlet</span><span class="sxs-lookup"><span data-stu-id="7bd7a-152">ment.TestReplicaCmdlet</span></span>

<span data-ttu-id="7bd7a-153">PS C: \\ testes de usuários \\\></span><span class="sxs-lookup"><span data-stu-id="7bd7a-153">PS C:\\Users\\Testing\></span></span>

<span data-ttu-id="7bd7a-154">PS C: \\ o \\ teste \> de usuários Test-CsUcwaConference-TargetFqdn "LyncTest. SelfHost. Corp. M</span><span class="sxs-lookup"><span data-stu-id="7bd7a-154">PS C:\\Users\\Testing\> Test-CsUcwaConference -TargetFqdn "LyncTest.SelfHost.Corp.M</span></span>

<span data-ttu-id="7bd7a-155">icrosoft.com "</span><span class="sxs-lookup"><span data-stu-id="7bd7a-155">icrosoft.com"</span></span>

<span data-ttu-id="7bd7a-156">Aviso: falha ao ler o número da porta do registrador para o fornecido totalmente qualificado</span><span class="sxs-lookup"><span data-stu-id="7bd7a-156">WARNING: Failed to read Registrar port number for the given fully qualified</span></span>

<span data-ttu-id="7bd7a-157">FQDN (nome de domínio).</span><span class="sxs-lookup"><span data-stu-id="7bd7a-157">domain name (FQDN).</span></span> <span data-ttu-id="7bd7a-158">Usando o número da porta do registrador padrão.</span><span class="sxs-lookup"><span data-stu-id="7bd7a-158">Using default Registrar port number.</span></span> <span data-ttu-id="7bd7a-159">Exceções</span><span class="sxs-lookup"><span data-stu-id="7bd7a-159">Exception:</span></span>

<span data-ttu-id="7bd7a-160">System. InvalidOperationException: nenhum cluster correspondente encontrado na topologia.</span><span class="sxs-lookup"><span data-stu-id="7bd7a-160">System.InvalidOperationException: No matching cluster found in topology.</span></span>

<span data-ttu-id="7bd7a-161">por</span><span class="sxs-lookup"><span data-stu-id="7bd7a-161">at</span></span>

<span data-ttu-id="7bd7a-162">Microsoft. RTC. Management. SyntheticTransactions. SipSyntheticTransaction. TryRetri</span><span class="sxs-lookup"><span data-stu-id="7bd7a-162">Microsoft.Rtc.Management.SyntheticTransactions.SipSyntheticTransaction.TryRetri</span></span>

<span data-ttu-id="7bd7a-163">eveRegistrarPortFromTopology (Int32& registrarPortNumber)</span><span class="sxs-lookup"><span data-stu-id="7bd7a-163">eveRegistrarPortFromTopology(Int32& registrarPortNumber)</span></span>

<span data-ttu-id="7bd7a-164">Test-CsUcwaConference: não há um usuário de teste atribuído para</span><span class="sxs-lookup"><span data-stu-id="7bd7a-164">Test-CsUcwaConference : There is no test user assigned for</span></span>

<span data-ttu-id="7bd7a-165">\[LyncTest.SelfHost.Corp.Microsoft.com \] .</span><span class="sxs-lookup"><span data-stu-id="7bd7a-165">\[LyncTest.SelfHost.Corp.Microsoft.com\].</span></span> <span data-ttu-id="7bd7a-166">Verifique a configuração do usuário de teste.</span><span class="sxs-lookup"><span data-stu-id="7bd7a-166">Verify test user configuration.</span></span>

<span data-ttu-id="7bd7a-167">Na linha: 1 caractere: 1</span><span class="sxs-lookup"><span data-stu-id="7bd7a-167">At line:1 char:1</span></span>

<span data-ttu-id="7bd7a-168">\+ Test-CsUcwaConference-TargetFqdn "LyncTest.SelfHost.Corp.Microsoft.com"</span><span class="sxs-lookup"><span data-stu-id="7bd7a-168">\+ Test-CsUcwaConference -TargetFqdn "LyncTest.SelfHost.Corp.Microsoft.com"</span></span>

\+ ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

<span data-ttu-id="7bd7a-169">\+ CategoryInfo: ResourceUnavailable: (:) \[ Test-CsUcwaConference\]</span><span class="sxs-lookup"><span data-stu-id="7bd7a-169">\+ CategoryInfo : ResourceUnavailable: (:) \[Test-CsUcwaConference\]</span></span>

<span data-ttu-id="7bd7a-170">, InvalidOperationException</span><span class="sxs-lookup"><span data-stu-id="7bd7a-170">, InvalidOperationException</span></span>

<span data-ttu-id="7bd7a-171">\+ FullyQualifiedErrorId: NotFoundTestUsers, Microsoft. RTC. Management. sintetizador</span><span class="sxs-lookup"><span data-stu-id="7bd7a-171">\+ FullyQualifiedErrorId : NotFoundTestUsers,Microsoft.Rtc.Management.Synth</span></span>

<span data-ttu-id="7bd7a-172">eticTransactions.TestUcwaConferenceCmdlet</span><span class="sxs-lookup"><span data-stu-id="7bd7a-172">eticTransactions.TestUcwaConferenceCmdlet</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="7bd7a-173">Motivos pelos quais o teste pode ter falhado</span><span class="sxs-lookup"><span data-stu-id="7bd7a-173">Reasons why the test might have failed</span></span>

<span data-ttu-id="7bd7a-174">Aqui estão alguns motivos comuns pelos quais **Test-CsReplica** pode falhar:</span><span class="sxs-lookup"><span data-stu-id="7bd7a-174">Here are some common reasons why **Test-CsReplica** might fail:</span></span>

  - <span data-ttu-id="7bd7a-175">Pode haver um problema maior com o agente do Replicator e os serviços de agente de log centralizado</span><span class="sxs-lookup"><span data-stu-id="7bd7a-175">There may be a larger problem with the Replicator Agent and Centralized Logging Agent services</span></span>

  - <span data-ttu-id="7bd7a-176">As portas necessárias podem não estar abertas no firewall do Windows</span><span class="sxs-lookup"><span data-stu-id="7bd7a-176">The required ports may not be open in the Windows Firewall</span></span>

  - <span data-ttu-id="7bd7a-177">Os grupos de segurança do Active Directory e do computador local necessários podem não existir</span><span class="sxs-lookup"><span data-stu-id="7bd7a-177">The necessary Active Directory and local computer security groups may not exist</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

