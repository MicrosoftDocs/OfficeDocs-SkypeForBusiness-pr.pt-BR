---
title: 'Lync Server 2013: testar a capacidade de um usuário fazer logon no Lync Server'
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
ms.openlocfilehash: 71629cb844b8f65ab6f54c0d604fad0d152705d6
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42141287"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="testing-the-ability-of-a-user-to-log-on-to-lync-server-2013"></a><span data-ttu-id="eda15-102">Testando a capacidade de um usuário fazer logon no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="eda15-102">Testing the ability of a user to log on to Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="eda15-103">_**Última modificação do tópico:** 2014-06-05_</span><span class="sxs-lookup"><span data-stu-id="eda15-103">_**Topic Last Modified:** 2014-06-05_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="eda15-104">Agenda de verificação</span><span class="sxs-lookup"><span data-stu-id="eda15-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="eda15-105">Diariamente</span><span class="sxs-lookup"><span data-stu-id="eda15-105">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="eda15-106">Ferramenta de teste</span><span class="sxs-lookup"><span data-stu-id="eda15-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="eda15-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="eda15-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="eda15-108">Permissões obrigatórias</span><span class="sxs-lookup"><span data-stu-id="eda15-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="eda15-109">Ao executar localmente usando o Shell de gerenciamento do Lync Server, os usuários devem ser membros do grupo de segurança RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="eda15-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="eda15-110">Quando executado usando uma instância remota do Windows PowerShell, os usuários devem receber uma função RBAC que tenha permissão para executar o cmdlet Test-CsRegistration.</span><span class="sxs-lookup"><span data-stu-id="eda15-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsRegistration cmdlet.</span></span> <span data-ttu-id="eda15-111">Para ver uma lista de todas as funções RBAC que podem usar este cmdlet, execute o seguinte comando no prompt do Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="eda15-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsRegistration&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="eda15-112">Descrição</span><span class="sxs-lookup"><span data-stu-id="eda15-112">Description</span></span>

<span data-ttu-id="eda15-113">O cmdlet Test-CsRegistration permite verificar se os usuários da sua organização podem fazer logon no Lync Server.</span><span class="sxs-lookup"><span data-stu-id="eda15-113">The Test-CsRegistration cmdlet enables you to verify that users in your organization can log on to Lync Server.</span></span> <span data-ttu-id="eda15-114">Quando você executa o Test-CsRegistration, o cmdlet tenta entrar em um usuário de teste no Lync Server e, em seguida, se tiver êxito, desconectará o usuário de teste do sistema.</span><span class="sxs-lookup"><span data-stu-id="eda15-114">When you run Test-CsRegistration, the cmdlet attempts to sign in a test user to Lync Server and then, if it is successful, disconnects that test user from the system.</span></span> <span data-ttu-id="eda15-115">Tudo isso acontece sem nenhuma interação por parte do usuário e sem afetar nenhum usuário real.</span><span class="sxs-lookup"><span data-stu-id="eda15-115">All of this happens without any user interaction, and without affecting any actual users.</span></span> <span data-ttu-id="eda15-116">Por exemplo, suponha que a conta de teste sip:kenmyer@litwareinc.com corresponde a um usuário real que tem uma conta real do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="eda15-116">For example, suppose that the test account sip:kenmyer@litwareinc.com corresponds to a real user who has a real Lync Server account.</span></span> <span data-ttu-id="eda15-117">Nesse caso, o teste será conduzido sem prejuízo algum ao verdadeiro Ken Myer.</span><span class="sxs-lookup"><span data-stu-id="eda15-117">In that case, the test will be conducted without any disruption to the real Ken Myer.</span></span> <span data-ttu-id="eda15-118">Quando a conta de teste de Ken Myer fizer logoff do sistema, a pessoa Ken Myer continuará conectada.</span><span class="sxs-lookup"><span data-stu-id="eda15-118">When the Ken Myer test account logs off from the system, Ken Myer the person will remain logged on.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="eda15-119">Executar o teste</span><span class="sxs-lookup"><span data-stu-id="eda15-119">Running the test</span></span>

<span data-ttu-id="eda15-120">O cmdlet Test-CsRegistration pode ser executado usando uma conta de teste pré-configurada (consulte Configurando contas de teste para executar testes do Lync Server) ou a conta de qualquer usuário habilitado para o Lync Server.</span><span class="sxs-lookup"><span data-stu-id="eda15-120">The Test-CsRegistration cmdlet can be run using either a preconfigured test account (see Setting Up Test Accounts for Running Lync Server Tests) or the account of any user who is enabled for Lync Server.</span></span> <span data-ttu-id="eda15-121">Para executar esta verificação usando uma conta de teste, basta especificar o FQDN do pool de registradores do Lync Server que está sendo testado.</span><span class="sxs-lookup"><span data-stu-id="eda15-121">To run this check using a test account, you just have to specify the FQDN of the Lync Server Registrar pool being tested.</span></span> <span data-ttu-id="eda15-122">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="eda15-122">For example:</span></span>

    Test-CsRegistration -TargetFqdn "atl-cs-001.litwareinc.com"

<span data-ttu-id="eda15-123">Para executar essa verificação usando uma conta de usuário real, você deve primeiro criar um objeto de credenciais do Windows PowerShell que contenha o nome da conta e a senha.</span><span class="sxs-lookup"><span data-stu-id="eda15-123">To run this check using an actual user account, you must first create a Windows PowerShell credentials object that contains the account name and password.</span></span> <span data-ttu-id="eda15-124">Em seguida, você deve incluir o objeto Credentials e o endereço SIP atribuído à conta quando chamar Test-CsRegistration:</span><span class="sxs-lookup"><span data-stu-id="eda15-124">You must then include that credentials object and the SIP address assigned to the account when you call Test-CsRegistration:</span></span>

    $credential = Get-Credential "litwareinc\kenmyer"
    Test-CsRegistration -TargetFqdn "atl-cs-001.litwareinc.com"-UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential

<span data-ttu-id="eda15-125">Para obter mais informações, consulte a documentação de ajuda para o cmdlet [Test-CsRegistration](https://docs.microsoft.com/powershell/module/skype/Test-CsRegistration) .</span><span class="sxs-lookup"><span data-stu-id="eda15-125">For more information, see the Help documentation for the [Test-CsRegistration](https://docs.microsoft.com/powershell/module/skype/Test-CsRegistration) cmdlet.</span></span>

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="eda15-126">Determinando o sucesso ou a falha</span><span class="sxs-lookup"><span data-stu-id="eda15-126">Determining success or failure</span></span>

<span data-ttu-id="eda15-127">Se o usuário especificado puder fazer logon (e, em seguida, fazer logoff do) Lync Server, você receberá uma saída semelhante a essa com a propriedade Result marcada como **êxito:**</span><span class="sxs-lookup"><span data-stu-id="eda15-127">If the specified user can log on to (and then log off from) Lync Server, you'll receive output similar to this with the Result property marked as **Success:**</span></span>

<span data-ttu-id="eda15-128">TargetFqdn: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="eda15-128">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="eda15-129">Resultado: êxito</span><span class="sxs-lookup"><span data-stu-id="eda15-129">Result : Success</span></span>

<span data-ttu-id="eda15-130">Latência: 00:00:06.8630376</span><span class="sxs-lookup"><span data-stu-id="eda15-130">Latency : 00:00:06.8630376</span></span>

<span data-ttu-id="eda15-131">Erros</span><span class="sxs-lookup"><span data-stu-id="eda15-131">Error :</span></span>

<span data-ttu-id="eda15-132">Diagnóstico</span><span class="sxs-lookup"><span data-stu-id="eda15-132">Diagnosis :</span></span>

<span data-ttu-id="eda15-133">Se o usuário especificado não puder fazer logon ou logout, o resultado será mostrado como uma falha, e informações adicionais serão registradas nas propriedades de erro e diagnóstico:</span><span class="sxs-lookup"><span data-stu-id="eda15-133">If the specified user can't log in or log out, the Result will be shown as Failure, and additional information will be recorded in the Error and Diagnosis properties:</span></span>

<span data-ttu-id="eda15-134">TargetFqdn: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="eda15-134">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="eda15-135">Resultado: falha</span><span class="sxs-lookup"><span data-stu-id="eda15-135">Result : Failure</span></span>

<span data-ttu-id="eda15-136">Latência: 00:00:00</span><span class="sxs-lookup"><span data-stu-id="eda15-136">Latency : 00:00:00</span></span>

<span data-ttu-id="eda15-137">Erro: 404, não encontrado</span><span class="sxs-lookup"><span data-stu-id="eda15-137">Error : 404, Not Found</span></span>

<span data-ttu-id="eda15-138">Diagnóstico: ErrorCode = 1003, Source = ATL-cs-001. litwareinc. com, Reason = o usuário faz</span><span class="sxs-lookup"><span data-stu-id="eda15-138">Diagnosis : ErrorCode=1003,source=atl-cs-001.litwareinc.com,Reason=User does</span></span>

<span data-ttu-id="eda15-139">Não existe</span><span class="sxs-lookup"><span data-stu-id="eda15-139">not exist</span></span>

<span data-ttu-id="eda15-140">Microsoft. RTC. Signaling. DiagnosticHeader</span><span class="sxs-lookup"><span data-stu-id="eda15-140">Microsoft.Rtc.Signaling.DiagnosticHeader</span></span>

<span data-ttu-id="eda15-141">Por exemplo, a saída anterior diz que o teste falhou porque o usuário especificado não pôde ser encontrado.</span><span class="sxs-lookup"><span data-stu-id="eda15-141">For example, the previous output states that the test failed because the specified user couldn't be found.</span></span> <span data-ttu-id="eda15-142">Você pode determinar se um endereço SIP é ou não válido (e se o usuário atribuído cujo endereço SIP está habilitado para o Lync Server) executando este comando:</span><span class="sxs-lookup"><span data-stu-id="eda15-142">You can determine whether or not a SIP address is valid (and whether the user assigned that SIP address is enabled for Lync Server) by running this command:</span></span>

    Get-CsUser "sip:kenmyer@litwareinc.com"

<span data-ttu-id="eda15-143">Se Test-CsRegistration falhar, talvez você queira executar novamente o teste, desta vez, incluindo o parâmetro Verbose:</span><span class="sxs-lookup"><span data-stu-id="eda15-143">If Test-CsRegistration fails, then you might want to rerun the test, this time including the Verbose parameter:</span></span>

    Test-CsRegistration -UserSipAddress "sip:kenmyer@litwareinc.com" -TargetFqdn "atl-cs-001.litwareinc.com" -Verbose

<span data-ttu-id="eda15-144">Quando o parâmetro Verbose é incluído, o Test-CsRegistration retornará uma conta passo a passo de cada ação que tentou quando verificou a capacidade do usuário especificado fazer logon no Lync Server.</span><span class="sxs-lookup"><span data-stu-id="eda15-144">When the Verbose parameter is included, Test-CsRegistration will return a step-by-step account of each action it tried when it checked the ability of the specified user to log on to Lync Server.</span></span> <span data-ttu-id="eda15-145">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="eda15-145">For example:</span></span>

<span data-ttu-id="eda15-146">VERBOse: atividade de ' registro ' iniciada.</span><span class="sxs-lookup"><span data-stu-id="eda15-146">VERBOSE: 'Register' activity started.</span></span>

<span data-ttu-id="eda15-147">Enviando solicitação de registro:</span><span class="sxs-lookup"><span data-stu-id="eda15-147">Sending Registration request:</span></span>

<span data-ttu-id="eda15-148">FQDN de destino = atl-cs-011.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="eda15-148">Target Fqdn = atl-cs-011.litwareinc.com</span></span>

<span data-ttu-id="eda15-149">Endereço SIP do usuário = sip:kenmyer@litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="eda15-149">User Sip Address = sip:kenmyer@litwareinc.com</span></span>

<span data-ttu-id="eda15-150">Porta do registrador = 5061.</span><span class="sxs-lookup"><span data-stu-id="eda15-150">Registrar Port = 5061.</span></span>

<span data-ttu-id="eda15-151">O tipo de autenticação ' confiável ' é selecionado.</span><span class="sxs-lookup"><span data-stu-id="eda15-151">Auth Type 'Trusted' is selected.</span></span>

<span data-ttu-id="eda15-152">Uma exceção ' o ponto de extremidade não pode ser registrada.</span><span class="sxs-lookup"><span data-stu-id="eda15-152">An exception 'The endpoint is unable to register.</span></span> <span data-ttu-id="eda15-153">Veja o código de erro por motivo específico, durante a execução do fluxo de trabalho Microsoft. RTC. SyntheticTransactions. Workflow. STRegistrerWorkflow.</span><span class="sxs-lookup"><span data-stu-id="eda15-153">See the ErrorCode for specific reason' occurred during Workflow Microsoft.Rtc.SyntheticTransactions.Workflow.STRegistrerWorkflow execution.</span></span>

<span data-ttu-id="eda15-154">Pilha de chamadas de exceção: em Microsoft. RTC. Signaling. SipAsyncResult'1. ThrowIfFailed ()</span><span class="sxs-lookup"><span data-stu-id="eda15-154">Exception Call Stack: at Microsoft.Rtc.Signaling.SipAsyncResult'1.ThrowIfFailed()</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="eda15-155">Motivos pelos quais o teste pode ter falhado</span><span class="sxs-lookup"><span data-stu-id="eda15-155">Reasons why the test might have failed</span></span>

<span data-ttu-id="eda15-156">Aqui estão alguns motivos comuns pelos quais Test-CsRegistration pode falhar:</span><span class="sxs-lookup"><span data-stu-id="eda15-156">Here are some common reasons why Test-CsRegistration might fail:</span></span>

  - <span data-ttu-id="eda15-157">Você especificou uma conta de usuário incorreta.</span><span class="sxs-lookup"><span data-stu-id="eda15-157">You specified an incorrect user account.</span></span> <span data-ttu-id="eda15-158">Você pode verificar se uma conta de usuário existe executando um comando semelhante a este:</span><span class="sxs-lookup"><span data-stu-id="eda15-158">You can verify that a user account exists by running a command similar to this:</span></span>
    
        Get-CsUser "sip:kenmyer@litwareinc.com"

  - <span data-ttu-id="eda15-159">A conta de usuário é válida, mas a conta não está habilitada no momento para o Lync Server.</span><span class="sxs-lookup"><span data-stu-id="eda15-159">The user account is valid, but the account is currently not enabled for Lync Server.</span></span> <span data-ttu-id="eda15-160">Para verificar se uma conta de usuário está habilitada para o Lync Server, execute um comando semelhante ao seguinte:</span><span class="sxs-lookup"><span data-stu-id="eda15-160">To verify that a user account is enabled for Lync Server, run a command similar to the following:</span></span>
    
        Get-CsUser "sip:kenmyer@litwareinc.com" | Select-Object Enabled
    
    <span data-ttu-id="eda15-161">Se a propriedade Enabled estiver definida como false, isso significa que o usuário não está atualmente habilitado para o Lync Server.</span><span class="sxs-lookup"><span data-stu-id="eda15-161">If the Enabled property is set to False, that means that the user is currently not enabled for Lync Server.</span></span>

  - <span data-ttu-id="eda15-162">Você especificou um pool de registradores incorreto.</span><span class="sxs-lookup"><span data-stu-id="eda15-162">You specified an incorrect Registrar pool.</span></span> <span data-ttu-id="eda15-163">Você pode retornar os FQDNs dos pools de registradores usando este comando:</span><span class="sxs-lookup"><span data-stu-id="eda15-163">You can return the FQDNs of your Registrar pools by using this command:</span></span>
    
        Get-CsService -Registrar | Select-Object PoolFqdn

  - <span data-ttu-id="eda15-164">O pool de registradores não está disponível no momento.</span><span class="sxs-lookup"><span data-stu-id="eda15-164">The Registrar pool is currently not available.</span></span> <span data-ttu-id="eda15-165">Tente executar o ping no pool para ver se ele responderá:</span><span class="sxs-lookup"><span data-stu-id="eda15-165">Try pinging the pool to see whether it responds:</span></span>
    
        ping atl-cs-001.litwareinc.com

</div>

</div>

<span> </span>

</div>

</div>

</div>

