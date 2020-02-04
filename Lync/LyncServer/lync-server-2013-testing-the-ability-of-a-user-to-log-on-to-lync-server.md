---
title: 'Lync Server 2013: testando a capacidade de um usuário para fazer logon no Lync Server'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing the ability of a user to log on to Lync Server
ms:assetid: d9cd0f9b-6ef2-4050-a4ca-263c5afa93ee
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn743841(v=OCS.15)
ms:contentKeyID: 63969655
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4fb1d0af8a5191c7e0af1ffe3319c426c116b586
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41745461"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="testing-the-ability-of-a-user-to-log-on-to-lync-server-2013"></a><span data-ttu-id="c56bf-102">Testar a capacidade de um usuário para fazer logon no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c56bf-102">Testing the ability of a user to log on to Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c56bf-103">_**Tópico da última modificação:** 2014-06-05_</span><span class="sxs-lookup"><span data-stu-id="c56bf-103">_**Topic Last Modified:** 2014-06-05_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c56bf-104">Cronograma de verificação</span><span class="sxs-lookup"><span data-stu-id="c56bf-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="c56bf-105">Diário</span><span class="sxs-lookup"><span data-stu-id="c56bf-105">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c56bf-106">Ferramenta de teste</span><span class="sxs-lookup"><span data-stu-id="c56bf-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="c56bf-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="c56bf-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c56bf-108">Permissões necessárias</span><span class="sxs-lookup"><span data-stu-id="c56bf-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="c56bf-109">Quando executado localmente usando o Shell de gerenciamento do Lync Server, os usuários devem ser membros do grupo de segurança RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="c56bf-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="c56bf-110">Quando executado usando uma instância remota do Windows PowerShell, os usuários devem receber uma função RBAC que tenha permissão para executar o cmdlet Test-CsRegistration.</span><span class="sxs-lookup"><span data-stu-id="c56bf-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsRegistration cmdlet.</span></span> <span data-ttu-id="c56bf-111">Para ver uma lista de todas as funções RBAC que podem usar esse cmdlet, execute o seguinte comando no prompt do Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="c56bf-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsRegistration&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="c56bf-112">Descrição</span><span class="sxs-lookup"><span data-stu-id="c56bf-112">Description</span></span>

<span data-ttu-id="c56bf-113">O cmdlet Test-CsRegistration permite que você verifique se os usuários em sua organização podem fazer logon no Lync Server.</span><span class="sxs-lookup"><span data-stu-id="c56bf-113">The Test-CsRegistration cmdlet enables you to verify that users in your organization can log on to Lync Server.</span></span> <span data-ttu-id="c56bf-114">Ao executar Test-CsRegistration, o cmdlet tenta se conectar a um usuário de teste ao Lync Server e, se tiver êxito, desconectará o usuário de teste do sistema.</span><span class="sxs-lookup"><span data-stu-id="c56bf-114">When you run Test-CsRegistration, the cmdlet attempts to sign in a test user to Lync Server and then, if it is successful, disconnects that test user from the system.</span></span> <span data-ttu-id="c56bf-115">Tudo isso acontece sem qualquer interação do usuário e sem afetar os usuários reais.</span><span class="sxs-lookup"><span data-stu-id="c56bf-115">All of this happens without any user interaction, and without affecting any actual users.</span></span> <span data-ttu-id="c56bf-116">Por exemplo, suponha que o sip:kenmyer@litwareinc.com da conta de teste corresponda a um usuário real que tenha uma conta real do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="c56bf-116">For example, suppose that the test account sip:kenmyer@litwareinc.com corresponds to a real user who has a real Lync Server account.</span></span> <span data-ttu-id="c56bf-117">Nesse caso, o teste será realizado sem qualquer interrupção no Ken Myer verdadeiro.</span><span class="sxs-lookup"><span data-stu-id="c56bf-117">In that case, the test will be conducted without any disruption to the real Ken Myer.</span></span> <span data-ttu-id="c56bf-118">Quando a conta de teste de Ken Myer é desconectada do sistema, Ken Myer a pessoa permanecerá conectada.</span><span class="sxs-lookup"><span data-stu-id="c56bf-118">When the Ken Myer test account logs off from the system, Ken Myer the person will remain logged on.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="c56bf-119">Executar o teste</span><span class="sxs-lookup"><span data-stu-id="c56bf-119">Running the test</span></span>

<span data-ttu-id="c56bf-120">O cmdlet Test-CsRegistration pode ser executado usando uma conta de teste pré-configurada (consulte Configurando contas de teste para executar testes do Lync Server) ou a conta de qualquer usuário habilitado para o Lync Server.</span><span class="sxs-lookup"><span data-stu-id="c56bf-120">The Test-CsRegistration cmdlet can be run using either a preconfigured test account (see Setting Up Test Accounts for Running Lync Server Tests) or the account of any user who is enabled for Lync Server.</span></span> <span data-ttu-id="c56bf-121">Para executar essa verificação usando uma conta de teste, basta especificar o FQDN do pool de registradores do Lync Server que está sendo testado.</span><span class="sxs-lookup"><span data-stu-id="c56bf-121">To run this check using a test account, you just have to specify the FQDN of the Lync Server Registrar pool being tested.</span></span> <span data-ttu-id="c56bf-122">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="c56bf-122">For example:</span></span>

    Test-CsRegistration -TargetFqdn "atl-cs-001.litwareinc.com"

<span data-ttu-id="c56bf-123">Para executar essa verificação usando uma conta de usuário real, primeiro você deve criar um objeto de credenciais do Windows PowerShell que contenha o nome da conta e a senha.</span><span class="sxs-lookup"><span data-stu-id="c56bf-123">To run this check using an actual user account, you must first create a Windows PowerShell credentials object that contains the account name and password.</span></span> <span data-ttu-id="c56bf-124">Em seguida, você deve incluir esse objeto de credenciais e o endereço SIP atribuído à conta ao chamar Test-CsRegistration:</span><span class="sxs-lookup"><span data-stu-id="c56bf-124">You must then include that credentials object and the SIP address assigned to the account when you call Test-CsRegistration:</span></span>

    $credential = Get-Credential "litwareinc\kenmyer"
    Test-CsRegistration -TargetFqdn "atl-cs-001.litwareinc.com"-UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential

<span data-ttu-id="c56bf-125">Para obter mais informações, consulte a documentação da ajuda para o cmdlet [Test-CsRegistration](https://docs.microsoft.com/powershell/module/skype/Test-CsRegistration) .</span><span class="sxs-lookup"><span data-stu-id="c56bf-125">For more information, see the Help documentation for the [Test-CsRegistration](https://docs.microsoft.com/powershell/module/skype/Test-CsRegistration) cmdlet.</span></span>

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="c56bf-126">Determinação do sucesso ou falha</span><span class="sxs-lookup"><span data-stu-id="c56bf-126">Determining success or failure</span></span>

<span data-ttu-id="c56bf-127">Se o usuário especificado puder fazer logon (e, em seguida, fazer logoff do) Lync Server, você receberá uma saída semelhante a isso com a propriedade Result marcada como **Success:**</span><span class="sxs-lookup"><span data-stu-id="c56bf-127">If the specified user can log on to (and then log off from) Lync Server, you'll receive output similar to this with the Result property marked as **Success:**</span></span>

<span data-ttu-id="c56bf-128">TargetFqdn: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="c56bf-128">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="c56bf-129">Resultado: êxito</span><span class="sxs-lookup"><span data-stu-id="c56bf-129">Result : Success</span></span>

<span data-ttu-id="c56bf-130">Latência: 00:00:06.8630376</span><span class="sxs-lookup"><span data-stu-id="c56bf-130">Latency : 00:00:06.8630376</span></span>

<span data-ttu-id="c56bf-131">Erros</span><span class="sxs-lookup"><span data-stu-id="c56bf-131">Error :</span></span>

<span data-ttu-id="c56bf-132">Correto</span><span class="sxs-lookup"><span data-stu-id="c56bf-132">Diagnosis :</span></span>

<span data-ttu-id="c56bf-133">Se o usuário especificado não puder entrar ou fazer logoff, o resultado será mostrado como uma falha, e informações adicionais serão gravadas nas propriedades de erro e diagnóstico:</span><span class="sxs-lookup"><span data-stu-id="c56bf-133">If the specified user can't log in or log out, the Result will be shown as Failure, and additional information will be recorded in the Error and Diagnosis properties:</span></span>

<span data-ttu-id="c56bf-134">TargetFqdn: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="c56bf-134">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="c56bf-135">Resultado: falha</span><span class="sxs-lookup"><span data-stu-id="c56bf-135">Result : Failure</span></span>

<span data-ttu-id="c56bf-136">Latência: 00:00:00</span><span class="sxs-lookup"><span data-stu-id="c56bf-136">Latency : 00:00:00</span></span>

<span data-ttu-id="c56bf-137">Erro: 404, não encontrado</span><span class="sxs-lookup"><span data-stu-id="c56bf-137">Error : 404, Not Found</span></span>

<span data-ttu-id="c56bf-138">Diagnóstico: ErrorCode = 1003, Source = ATL-cs-001. litwareinc. com, Reason = o usuário faz</span><span class="sxs-lookup"><span data-stu-id="c56bf-138">Diagnosis : ErrorCode=1003,source=atl-cs-001.litwareinc.com,Reason=User does</span></span>

<span data-ttu-id="c56bf-139">Não existe</span><span class="sxs-lookup"><span data-stu-id="c56bf-139">not exist</span></span>

<span data-ttu-id="c56bf-140">Microsoft. RTC. Signaling. DiagnosticHeader</span><span class="sxs-lookup"><span data-stu-id="c56bf-140">Microsoft.Rtc.Signaling.DiagnosticHeader</span></span>

<span data-ttu-id="c56bf-141">Por exemplo, a saída anterior informa que o teste falhou porque o usuário especificado não foi encontrado.</span><span class="sxs-lookup"><span data-stu-id="c56bf-141">For example, the previous output states that the test failed because the specified user couldn't be found.</span></span> <span data-ttu-id="c56bf-142">Você pode determinar se um endereço SIP é válido (e se o usuário que atribuiu esse endereço SIP está habilitado para o Lync Server) executando este comando:</span><span class="sxs-lookup"><span data-stu-id="c56bf-142">You can determine whether or not a SIP address is valid (and whether the user assigned that SIP address is enabled for Lync Server) by running this command:</span></span>

    Get-CsUser "sip:kenmyer@litwareinc.com"

<span data-ttu-id="c56bf-143">Se Test-CsRegistration falhar, talvez você queira executar novamente o teste, desta vez, incluindo o parâmetro Verbose:</span><span class="sxs-lookup"><span data-stu-id="c56bf-143">If Test-CsRegistration fails, then you might want to rerun the test, this time including the Verbose parameter:</span></span>

    Test-CsRegistration -UserSipAddress "sip:kenmyer@litwareinc.com" -TargetFqdn "atl-cs-001.litwareinc.com" -Verbose

<span data-ttu-id="c56bf-144">Quando o parâmetro Verbose estiver incluído, Test-CsRegistration retornará uma conta passo a passo de cada ação que tentou verificar quando verificou a capacidade do usuário especificado para fazer logon no Lync Server.</span><span class="sxs-lookup"><span data-stu-id="c56bf-144">When the Verbose parameter is included, Test-CsRegistration will return a step-by-step account of each action it tried when it checked the ability of the specified user to log on to Lync Server.</span></span> <span data-ttu-id="c56bf-145">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="c56bf-145">For example:</span></span>

<span data-ttu-id="c56bf-146">VERBOse: atividade de ' registro ' iniciada.</span><span class="sxs-lookup"><span data-stu-id="c56bf-146">VERBOSE: 'Register' activity started.</span></span>

<span data-ttu-id="c56bf-147">Enviando solicitação de registro:</span><span class="sxs-lookup"><span data-stu-id="c56bf-147">Sending Registration request:</span></span>

<span data-ttu-id="c56bf-148">FQDN de destino = atl-cs-011.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="c56bf-148">Target Fqdn = atl-cs-011.litwareinc.com</span></span>

<span data-ttu-id="c56bf-149">Endereço SIP do usuário = sip:kenmyer@litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="c56bf-149">User Sip Address = sip:kenmyer@litwareinc.com</span></span>

<span data-ttu-id="c56bf-150">Porta do registrador = 5061.</span><span class="sxs-lookup"><span data-stu-id="c56bf-150">Registrar Port = 5061.</span></span>

<span data-ttu-id="c56bf-151">O tipo de autenticação "confiável" está selecionado.</span><span class="sxs-lookup"><span data-stu-id="c56bf-151">Auth Type 'Trusted' is selected.</span></span>

<span data-ttu-id="c56bf-152">Uma exceção ' o ponto de extremidade não pode se registrar.</span><span class="sxs-lookup"><span data-stu-id="c56bf-152">An exception 'The endpoint is unable to register.</span></span> <span data-ttu-id="c56bf-153">Veja o código de erro por motivo específico ' durante a execução do fluxo de trabalho Microsoft. RTC. SyntheticTransactions. Workflow. STRegistrerWorkflow.</span><span class="sxs-lookup"><span data-stu-id="c56bf-153">See the ErrorCode for specific reason' occurred during Workflow Microsoft.Rtc.SyntheticTransactions.Workflow.STRegistrerWorkflow execution.</span></span>

<span data-ttu-id="c56bf-154">Pilha de chamadas de exceção: em Microsoft. RTC. Signaling. SipAsyncResult'1. ThrowIfFailed ()</span><span class="sxs-lookup"><span data-stu-id="c56bf-154">Exception Call Stack: at Microsoft.Rtc.Signaling.SipAsyncResult'1.ThrowIfFailed()</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="c56bf-155">Motivos pelos quais o teste pode ter falhado</span><span class="sxs-lookup"><span data-stu-id="c56bf-155">Reasons why the test might have failed</span></span>

<span data-ttu-id="c56bf-156">Aqui estão alguns motivos comuns pelos quais Test-CsRegistration pode falhar:</span><span class="sxs-lookup"><span data-stu-id="c56bf-156">Here are some common reasons why Test-CsRegistration might fail:</span></span>

  - <span data-ttu-id="c56bf-157">Você especificou uma conta de usuário incorreta.</span><span class="sxs-lookup"><span data-stu-id="c56bf-157">You specified an incorrect user account.</span></span> <span data-ttu-id="c56bf-158">Você pode verificar se existe uma conta de usuário executando um comando semelhante a este:</span><span class="sxs-lookup"><span data-stu-id="c56bf-158">You can verify that a user account exists by running a command similar to this:</span></span>
    
        Get-CsUser "sip:kenmyer@litwareinc.com"

  - <span data-ttu-id="c56bf-159">A conta de usuário é válida, mas a conta não está habilitada no momento para o Lync Server.</span><span class="sxs-lookup"><span data-stu-id="c56bf-159">The user account is valid, but the account is currently not enabled for Lync Server.</span></span> <span data-ttu-id="c56bf-160">Para verificar se uma conta de usuário está habilitada para o Lync Server, execute um comando semelhante ao seguinte:</span><span class="sxs-lookup"><span data-stu-id="c56bf-160">To verify that a user account is enabled for Lync Server, run a command similar to the following:</span></span>
    
        Get-CsUser "sip:kenmyer@litwareinc.com" | Select-Object Enabled
    
    <span data-ttu-id="c56bf-161">Se a propriedade Enabled estiver definida como false, isso significa que o usuário não está habilitado no momento para o Lync Server.</span><span class="sxs-lookup"><span data-stu-id="c56bf-161">If the Enabled property is set to False, that means that the user is currently not enabled for Lync Server.</span></span>

  - <span data-ttu-id="c56bf-162">Você especificou um pool de registradores incorreto.</span><span class="sxs-lookup"><span data-stu-id="c56bf-162">You specified an incorrect Registrar pool.</span></span> <span data-ttu-id="c56bf-163">Você pode retornar os FQDNs dos seus pools de registradores usando este comando:</span><span class="sxs-lookup"><span data-stu-id="c56bf-163">You can return the FQDNs of your Registrar pools by using this command:</span></span>
    
        Get-CsService -Registrar | Select-Object PoolFqdn

  - <span data-ttu-id="c56bf-164">No momento, o pool de registradores não está disponível.</span><span class="sxs-lookup"><span data-stu-id="c56bf-164">The Registrar pool is currently not available.</span></span> <span data-ttu-id="c56bf-165">Tente executar o ping no pool para ver se ele responde:</span><span class="sxs-lookup"><span data-stu-id="c56bf-165">Try pinging the pool to see whether it responds:</span></span>
    
        ping atl-cs-001.litwareinc.com

</div>

</div>

<span> </span>

</div>

</div>

</div>

