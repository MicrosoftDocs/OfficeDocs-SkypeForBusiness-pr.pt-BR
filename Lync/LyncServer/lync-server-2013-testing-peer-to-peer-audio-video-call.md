---
title: 'Lync Server 2013: testar chamadas de áudio/vídeo ponto a ponto'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing peer to peer audio/video call
ms:assetid: 95eb3693-b866-4652-bc45-9b75fdb40b49
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn743835(v=OCS.15)
ms:contentKeyID: 63969627
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 462442b7afea193866dc96aaf57085d780f43a39
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42050273"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="testing-peer-to-peer-audiovideo-call-in-lync-server-2013"></a><span data-ttu-id="f0836-102">Teste de chamada de áudio/vídeo ponto a ponto no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f0836-102">Testing peer to peer audio/video call in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f0836-103">_**Última modificação do tópico:** 2014-06-05_</span><span class="sxs-lookup"><span data-stu-id="f0836-103">_**Topic Last Modified:** 2014-06-05_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f0836-104">Agenda de verificação</span><span class="sxs-lookup"><span data-stu-id="f0836-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="f0836-105">Diariamente</span><span class="sxs-lookup"><span data-stu-id="f0836-105">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f0836-106">Ferramenta de teste</span><span class="sxs-lookup"><span data-stu-id="f0836-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="f0836-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="f0836-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f0836-108">Permissões obrigatórias</span><span class="sxs-lookup"><span data-stu-id="f0836-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="f0836-109">Ao executar localmente usando o Shell de gerenciamento do Lync Server, os usuários devem ser membros do grupo de segurança RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="f0836-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="f0836-110">Quando executado usando uma instância remota do Windows PowerShell, os usuários devem receber uma função RBAC que tenha permissão para executar o cmdlet Test-CsP2PAV.</span><span class="sxs-lookup"><span data-stu-id="f0836-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsP2PAV cmdlet.</span></span> <span data-ttu-id="f0836-111">Para ver uma lista de todas as funções RBAC que podem usar este cmdlet, execute o seguinte comando no prompt do Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="f0836-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsP2PAV&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="f0836-112">Descrição</span><span class="sxs-lookup"><span data-stu-id="f0836-112">Description</span></span>

<span data-ttu-id="f0836-113">Test-CsP2PAV é usado para determinar se um par de usuários de teste pode participar de uma conversa de A/V ponto a ponto.</span><span class="sxs-lookup"><span data-stu-id="f0836-113">Test-CsP2PAV is used to determine whether a pair of test users can participate in a peer-to-peer A/V conversation.</span></span> <span data-ttu-id="f0836-114">Para testar esse cenário, o cmdlet é iniciado registrando os dois usuários no Lync Server.</span><span class="sxs-lookup"><span data-stu-id="f0836-114">To test this scenario, the cmdlet starts off by logging on the two users to Lync Server.</span></span> <span data-ttu-id="f0836-115">Presumindo-se que os dois logons sejam bem-sucedidos, o primeiro usuário convidará o segundo para participar da chamada de áudio/vídeo.</span><span class="sxs-lookup"><span data-stu-id="f0836-115">Assuming that the two logons succeed, the first user then invites the second user to join an A/V call.</span></span> <span data-ttu-id="f0836-116">O segundo usuário aceitará a chamada, a conexão entre os dois usuários será testada e, em seguida, a chamada será encerrada e os usuários de teste farão o logoff do sistema.</span><span class="sxs-lookup"><span data-stu-id="f0836-116">The second user accepts the call, the connection between the two users is tested, and then the call is ended and the test users are logged off from the system.</span></span>

<span data-ttu-id="f0836-117">Test-CsP2PAV não realiza uma chamada A/V.</span><span class="sxs-lookup"><span data-stu-id="f0836-117">Test-CsP2PAV does not actually conduct an A/V call.</span></span> <span data-ttu-id="f0836-118">As informações de multimídia não são trocadas entre os usuários de teste.</span><span class="sxs-lookup"><span data-stu-id="f0836-118">Multimedia information is not exchanged between the test users.</span></span> <span data-ttu-id="f0836-119">Em vez disso, o cmdlet verifica apenas se as conexões apropriadas podem ser feitas e se os dois usuários podem conduzir essa chamada.</span><span class="sxs-lookup"><span data-stu-id="f0836-119">Instead, the cmdlet merely verifies that the appropriate connections can be made and that the two users can conduct such a call.</span></span>

<span data-ttu-id="f0836-120">Para obter mais informações, consulte a documentação de ajuda para o cmdlet [Test-CsP2PAV](https://docs.microsoft.com/powershell/module/skype/Test-CsP2PAV) .</span><span class="sxs-lookup"><span data-stu-id="f0836-120">For more information, see the Help documentation for the [Test-CsP2PAV](https://docs.microsoft.com/powershell/module/skype/Test-CsP2PAV) cmdlet.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="f0836-121">Executar o teste</span><span class="sxs-lookup"><span data-stu-id="f0836-121">Running the test</span></span>

<span data-ttu-id="f0836-122">O cmdlet Test-CsP2PAV pode ser executado usando um par de contas de teste pré-configuradas (consulte Configurando contas de teste para executar testes do Lync Server) ou as contas de dois usuários que estão habilitados para o Lync Server.</span><span class="sxs-lookup"><span data-stu-id="f0836-122">The Test-CsP2PAV cmdlet can be run using either a pair of preconfigured test accounts (see Setting Up Test Accounts for Running Lync Server Tests) or the accounts of any two users who are enabled for Lync Server.</span></span> <span data-ttu-id="f0836-123">Para executar essa verificação usando contas de teste, basta especificar o FQDN do pool do Lync Server que está sendo testado.</span><span class="sxs-lookup"><span data-stu-id="f0836-123">To run this check using test accounts, you just have to specify the FQDN of the Lync Server pool being tested.</span></span> <span data-ttu-id="f0836-124">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="f0836-124">For example:</span></span>

    Test-CsP2PAV -TargetFqdn "atl-cs-001.litwareinc.com"

<span data-ttu-id="f0836-125">Para executar essa verificação usando contas de usuário reais, você deve criar dois objetos de credenciais do Lync Server (objetos que contêm o nome da conta e a senha) para cada conta.</span><span class="sxs-lookup"><span data-stu-id="f0836-125">To run this check using actual user accounts, you must create two Lync Server credentials objects (objects that contain the account name and password) for each account.</span></span> <span data-ttu-id="f0836-126">Em seguida, você deve incluir esses objetos de credenciais e os endereços SIP das duas contas ao chamar Test-CsP2PAV:</span><span class="sxs-lookup"><span data-stu-id="f0836-126">You must then include those credentials objects and the SIP addresses of the two accounts when you call Test-CsP2PAV:</span></span>

    $credential1 = Get-Credential "litwareinc\kenmyer"
    $credential2 = Get-Credential "litwareinc\davidlongmire"
    Test-CsP2PAV -TargetFqdn "atl-cs-001.litwareinc.com" -SenderSipAddress "sip:kenmyer@litwareinc.com" -SenderCredential $credential1 -ReceiverSipAddress "sip:davidlongmire@litwareinc.com" -ReceiverCredential $credential2

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="f0836-127">Determinando o sucesso ou a falha</span><span class="sxs-lookup"><span data-stu-id="f0836-127">Determining success or failure</span></span>

<span data-ttu-id="f0836-128">Se os dois usuários de teste puderem concluir uma chamada de A/V ponto a ponto, você receberá uma saída semelhante à propriedade Result marcada como **Success:**</span><span class="sxs-lookup"><span data-stu-id="f0836-128">If the two test users can complete a peer-to-peer A/V call, then you'll receive output similar to this with the Result property marked as **Success:**</span></span>

<span data-ttu-id="f0836-129">TargetFqdn: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="f0836-129">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="f0836-130">Resultado: êxito</span><span class="sxs-lookup"><span data-stu-id="f0836-130">Result : Success</span></span>

<span data-ttu-id="f0836-131">Latência: 00:00:06.8630376</span><span class="sxs-lookup"><span data-stu-id="f0836-131">Latency : 00:00:06.8630376</span></span>

<span data-ttu-id="f0836-132">Erros</span><span class="sxs-lookup"><span data-stu-id="f0836-132">Error :</span></span>

<span data-ttu-id="f0836-133">Diagnóstico</span><span class="sxs-lookup"><span data-stu-id="f0836-133">Diagnosis :</span></span>

<span data-ttu-id="f0836-134">Se os usuários de teste não puderem concluir a chamada, o resultado será mostrado como falha, e informações adicionais serão registradas nas propriedades de erro e diagnóstico:</span><span class="sxs-lookup"><span data-stu-id="f0836-134">If the test users can't complete the call, then the Result will be shown as Failure, and additional information will be recorded in the Error and Diagnosis properties:</span></span>

<span data-ttu-id="f0836-135">TargetFqdn: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="f0836-135">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="f0836-136">Resultado: falha</span><span class="sxs-lookup"><span data-stu-id="f0836-136">Result : Failure</span></span>

<span data-ttu-id="f0836-137">Latência: 00:00:00</span><span class="sxs-lookup"><span data-stu-id="f0836-137">Latency : 00:00:00</span></span>

<span data-ttu-id="f0836-138">Erro: 480, temporariamente indisponível</span><span class="sxs-lookup"><span data-stu-id="f0836-138">Error : 480, Temporarily Unavailable</span></span>

<span data-ttu-id="f0836-139">Diagnóstico: ErrorCode = 15030, Source = ATL-cs-001. litwareinc. com, Reason = Failed</span><span class="sxs-lookup"><span data-stu-id="f0836-139">Diagnosis : ErrorCode=15030,Source=atl-cs-001.litwareinc.com,Reason=Failed</span></span>

<span data-ttu-id="f0836-140">para rotear para o Exchange Server</span><span class="sxs-lookup"><span data-stu-id="f0836-140">to route to Exchange Server</span></span>

<span data-ttu-id="f0836-141">Microsoft. RTC. Signaling. DiagnosticHeader</span><span class="sxs-lookup"><span data-stu-id="f0836-141">Microsoft.Rtc.Signaling.DiagnosticHeader</span></span>

<span data-ttu-id="f0836-142">Por exemplo, a saída anterior diz que o teste falhou porque o Microsoft Exchange Server não pôde ser contatado.</span><span class="sxs-lookup"><span data-stu-id="f0836-142">For example, the previous output states that the test failed because the Microsoft Exchange Server couldn't be contacted.</span></span> <span data-ttu-id="f0836-143">Essa mensagem de erro normalmente indica um problema na configuração da Unificação de mensagens do Exchange.</span><span class="sxs-lookup"><span data-stu-id="f0836-143">This error message typically indicates a problem the configuration of Exchange Unified Messaging.</span></span>

<span data-ttu-id="f0836-144">Se Test-CsP2PAV falhar, talvez você queira executar novamente o teste, desta vez, incluindo o parâmetro Verbose:</span><span class="sxs-lookup"><span data-stu-id="f0836-144">If Test-CsP2PAV fails then you might want to rerun the test, this time including the Verbose parameter:</span></span>

<span data-ttu-id="f0836-145">Test-CsP2PAV-TargetFqdn "atl-cs-001.litwareinc.com"-Verbose</span><span class="sxs-lookup"><span data-stu-id="f0836-145">Test-CsP2PAV -TargetFqdn "atl-cs-001.litwareinc.com" -Verbose</span></span>

<span data-ttu-id="f0836-146">Quando o parâmetro Verbose for incluído, o Test-CsP2PAV retornará uma conta passo a passo de cada ação que tentou que verificou a capacidade do usuário especificado fazer logon no Lync Server.</span><span class="sxs-lookup"><span data-stu-id="f0836-146">When the Verbose parameter is included, Test-CsP2PAV will return a step-by-step account of each action it tried as it checked the ability of the specified user to log on to Lync Server.</span></span> <span data-ttu-id="f0836-147">Por exemplo, suponha que o teste falhou com o seguinte diagnóstico:</span><span class="sxs-lookup"><span data-stu-id="f0836-147">For example, suppose that your test failed with the following Diagnosis:</span></span>

<span data-ttu-id="f0836-148">ErrorCode = 6003, Source = ATL-cs-001. litwareinc. com, razão = não há suporte para a solicitação de diálogo</span><span class="sxs-lookup"><span data-stu-id="f0836-148">ErrorCode=6003,Source=atl-cs-001.litwareinc.com,Reason=Unsupported out of dialog request</span></span>

<span data-ttu-id="f0836-149">Se você executar Test-CsP2PAV novamente e incluir o parâmetro Verbose, receberá uma saída semelhante a esta:</span><span class="sxs-lookup"><span data-stu-id="f0836-149">If you rerun Test-CsP2PAV and include the Verbose parameter, you'll get output similar to this:</span></span>

<span data-ttu-id="f0836-150">VERBOse: atividade de ' registro ' iniciada.</span><span class="sxs-lookup"><span data-stu-id="f0836-150">VERBOSE: 'Register' activity started.</span></span>

<span data-ttu-id="f0836-151">Enviando solicitação de registro:</span><span class="sxs-lookup"><span data-stu-id="f0836-151">Sending Registration request:</span></span>

<span data-ttu-id="f0836-152">FQDN de destino = atl-cs-011.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="f0836-152">Target Fqdn = atl-cs-011.litwareinc.com</span></span>

<span data-ttu-id="f0836-153">Endereço SIP do usuário = sip:kenmyer@litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="f0836-153">User Sip Address = sip:kenmyer@litwareinc.com</span></span>

<span data-ttu-id="f0836-154">Porta do registrador = 5062.</span><span class="sxs-lookup"><span data-stu-id="f0836-154">Registrar Port = 5062.</span></span>

<span data-ttu-id="f0836-155">O tipo de autenticação ' IWA ' é selecionado.</span><span class="sxs-lookup"><span data-stu-id="f0836-155">Auth Type 'IWA' is selected.</span></span>

<span data-ttu-id="f0836-156">Uma exceção ' o ponto de extremidade não pôde ser registrado.</span><span class="sxs-lookup"><span data-stu-id="f0836-156">An exception 'The endpoint was unable to register.</span></span> <span data-ttu-id="f0836-157">Consulte ErrorCode por motivo específico. "</span><span class="sxs-lookup"><span data-stu-id="f0836-157">See the ErrorCode for specific reason.'</span></span> <span data-ttu-id="f0836-158">ocorrido durante a execução do fluxo de trabalho Microsoft. RTC. SyntheticTransactions. workflows. STP2PAVWorkflow.</span><span class="sxs-lookup"><span data-stu-id="f0836-158">occurred during workflow Microsoft.Rtc.SyntheticTransactions.Workflows.STP2PAVWorkflow execution.</span></span>

<span data-ttu-id="f0836-159">Embora ele possa não ser imediatamente óbvio, se você examinar a saída cuidadosamente, verá que uma porta de registrador incorreta (porta 5062) foi especificada.</span><span class="sxs-lookup"><span data-stu-id="f0836-159">Although it might not be immediately obvious, if you examine the output carefully you’ll see that an incorrect Registrar port (port 5062) was specified.</span></span> <span data-ttu-id="f0836-160">Por sua vez, isso causaria falha no teste.</span><span class="sxs-lookup"><span data-stu-id="f0836-160">In turn, that caused the test to fail.</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="f0836-161">Motivos pelos quais o teste pode ter falhado</span><span class="sxs-lookup"><span data-stu-id="f0836-161">Reasons why the test might have failed</span></span>

<span data-ttu-id="f0836-162">Aqui estão alguns motivos comuns pelos quais Test-CsP2PAV pode falhar:</span><span class="sxs-lookup"><span data-stu-id="f0836-162">Here are some common reasons why Test-CsP2PAV might fail:</span></span>

  - <span data-ttu-id="f0836-163">Você especificou uma conta de usuário que não é válida.</span><span class="sxs-lookup"><span data-stu-id="f0836-163">You specified a user account that is not valid.</span></span> <span data-ttu-id="f0836-164">Você pode verificar se uma conta de usuário existe executando um comando semelhante a este:</span><span class="sxs-lookup"><span data-stu-id="f0836-164">You can verify that a user account exists by running a command similar to this:</span></span>
    
    <span data-ttu-id="f0836-165">Get-CsUser "sip:kenmyer@litwareinc.com"</span><span class="sxs-lookup"><span data-stu-id="f0836-165">Get-CsUser "sip:kenmyer@litwareinc.com"</span></span>

  - <span data-ttu-id="f0836-166">A conta de usuário é válida, mas a conta não está habilitada no momento para o Lync Server.</span><span class="sxs-lookup"><span data-stu-id="f0836-166">The user account is valid, but the account is currently not enabled for Lync Server.</span></span> <span data-ttu-id="f0836-167">Para verificar se uma conta de usuário está habilitada para o Lync Server, execute um comando semelhante ao seguinte:</span><span class="sxs-lookup"><span data-stu-id="f0836-167">To verify that a user account is enabled for Lync Server, run a command similar to the following:</span></span>
    
        Get-CsUser "sip:kenmyer@litwareinc.com" | Select-Object Enabled
    
    <span data-ttu-id="f0836-168">Se a propriedade Enabled estiver definida como false, isso significa que o usuário não está atualmente habilitado para o Lync Server.</span><span class="sxs-lookup"><span data-stu-id="f0836-168">If the Enabled property is set to False, that means that the user is currently not enabled for Lync Server.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

