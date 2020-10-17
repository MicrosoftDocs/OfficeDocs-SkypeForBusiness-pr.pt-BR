---
title: 'Lync Server 2013: testar a capacidade de um usuário fazer logon no Lync Server'
description: 'Lync Server 2013: testar a capacidade de um usuário fazer logon no Lync Server.'
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
ms.openlocfilehash: 8b86ae3e490af0b361799ed5fb3f56ed4de42c82
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48556207"
---
# <a name="testing-the-ability-of-a-user-to-log-on-to-lync-server-2013"></a><span data-ttu-id="5eb37-103">Testando a capacidade de um usuário fazer logon no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5eb37-103">Testing the ability of a user to log on to Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5eb37-104">_**Última modificação do tópico:** 2014-06-05_</span><span class="sxs-lookup"><span data-stu-id="5eb37-104">_**Topic Last Modified:** 2014-06-05_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="5eb37-105">Agenda de verificação</span><span class="sxs-lookup"><span data-stu-id="5eb37-105">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="5eb37-106">Diariamente</span><span class="sxs-lookup"><span data-stu-id="5eb37-106">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5eb37-107">Ferramenta de teste</span><span class="sxs-lookup"><span data-stu-id="5eb37-107">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="5eb37-108">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="5eb37-108">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5eb37-109">Permissões obrigatórias</span><span class="sxs-lookup"><span data-stu-id="5eb37-109">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="5eb37-110">Ao executar localmente usando o Shell de gerenciamento do Lync Server, os usuários devem ser membros do grupo de segurança RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="5eb37-110">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="5eb37-111">Quando executado usando uma instância remota do Windows PowerShell, os usuários devem receber uma função RBAC que tenha permissão para executar o cmdlet Test-CsRegistration.</span><span class="sxs-lookup"><span data-stu-id="5eb37-111">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsRegistration cmdlet.</span></span> <span data-ttu-id="5eb37-112">Para ver uma lista de todas as funções RBAC que podem usar este cmdlet, execute o seguinte comando no prompt do Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="5eb37-112">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsRegistration&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="5eb37-113">Descrição</span><span class="sxs-lookup"><span data-stu-id="5eb37-113">Description</span></span>

<span data-ttu-id="5eb37-114">O cmdlet Test-CsRegistration permite verificar se os usuários da sua organização podem fazer logon no Lync Server.</span><span class="sxs-lookup"><span data-stu-id="5eb37-114">The Test-CsRegistration cmdlet enables you to verify that users in your organization can log on to Lync Server.</span></span> <span data-ttu-id="5eb37-115">Quando você executa o Test-CsRegistration, o cmdlet tenta entrar em um usuário de teste no Lync Server e, em seguida, se tiver êxito, desconectará o usuário de teste do sistema.</span><span class="sxs-lookup"><span data-stu-id="5eb37-115">When you run Test-CsRegistration, the cmdlet attempts to sign in a test user to Lync Server and then, if it is successful, disconnects that test user from the system.</span></span> <span data-ttu-id="5eb37-116">Tudo isso acontece sem nenhuma interação por parte do usuário e sem afetar nenhum usuário real.</span><span class="sxs-lookup"><span data-stu-id="5eb37-116">All of this happens without any user interaction, and without affecting any actual users.</span></span> <span data-ttu-id="5eb37-117">Por exemplo, suponha que a conta de teste sip:kenmyer@litwareinc.com corresponde a um usuário real que tem uma conta real do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="5eb37-117">For example, suppose that the test account sip:kenmyer@litwareinc.com corresponds to a real user who has a real Lync Server account.</span></span> <span data-ttu-id="5eb37-118">Nesse caso, o teste será conduzido sem prejuízo algum ao verdadeiro Ken Myer.</span><span class="sxs-lookup"><span data-stu-id="5eb37-118">In that case, the test will be conducted without any disruption to the real Ken Myer.</span></span> <span data-ttu-id="5eb37-119">Quando a conta de teste de Ken Myer fizer logoff do sistema, a pessoa Ken Myer continuará conectada.</span><span class="sxs-lookup"><span data-stu-id="5eb37-119">When the Ken Myer test account logs off from the system, Ken Myer the person will remain logged on.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="5eb37-120">Executar o teste</span><span class="sxs-lookup"><span data-stu-id="5eb37-120">Running the test</span></span>

<span data-ttu-id="5eb37-121">O cmdlet Test-CsRegistration pode ser executado usando uma conta de teste pré-configurada (Confira Configurando contas de teste para executar testes do Lync Server) ou a conta de qualquer usuário habilitado para o Lync Server.</span><span class="sxs-lookup"><span data-stu-id="5eb37-121">The Test-CsRegistration cmdlet can be run using either a preconfigured test account (see Setting Up Test Accounts for Running Lync Server Tests) or the account of any user who is enabled for Lync Server.</span></span> <span data-ttu-id="5eb37-122">Para executar esta verificação usando uma conta de teste, basta especificar o FQDN do pool de registradores do Lync Server que está sendo testado.</span><span class="sxs-lookup"><span data-stu-id="5eb37-122">To run this check using a test account, you just have to specify the FQDN of the Lync Server Registrar pool being tested.</span></span> <span data-ttu-id="5eb37-123">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="5eb37-123">For example:</span></span>

    Test-CsRegistration -TargetFqdn "atl-cs-001.litwareinc.com"

<span data-ttu-id="5eb37-124">Para executar essa verificação usando uma conta de usuário real, você deve primeiro criar um objeto de credenciais do Windows PowerShell que contenha o nome da conta e a senha.</span><span class="sxs-lookup"><span data-stu-id="5eb37-124">To run this check using an actual user account, you must first create a Windows PowerShell credentials object that contains the account name and password.</span></span> <span data-ttu-id="5eb37-125">Em seguida, você deve incluir o objeto Credentials e o endereço SIP atribuído à conta quando chamar Test-CsRegistration:</span><span class="sxs-lookup"><span data-stu-id="5eb37-125">You must then include that credentials object and the SIP address assigned to the account when you call Test-CsRegistration:</span></span>

    $credential = Get-Credential "litwareinc\kenmyer"
    Test-CsRegistration -TargetFqdn "atl-cs-001.litwareinc.com"-UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential

<span data-ttu-id="5eb37-126">Para obter mais informações, consulte a documentação de ajuda para o cmdlet [Test-CsRegistration](https://docs.microsoft.com/powershell/module/skype/Test-CsRegistration) .</span><span class="sxs-lookup"><span data-stu-id="5eb37-126">For more information, see the Help documentation for the [Test-CsRegistration](https://docs.microsoft.com/powershell/module/skype/Test-CsRegistration) cmdlet.</span></span>

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="5eb37-127">Determinando o sucesso ou a falha</span><span class="sxs-lookup"><span data-stu-id="5eb37-127">Determining success or failure</span></span>

<span data-ttu-id="5eb37-128">Se o usuário especificado puder fazer logon (e, em seguida, fazer logoff do) Lync Server, você receberá uma saída semelhante a essa com a propriedade Result marcada como **êxito:**</span><span class="sxs-lookup"><span data-stu-id="5eb37-128">If the specified user can log on to (and then log off from) Lync Server, you'll receive output similar to this with the Result property marked as **Success:**</span></span>

<span data-ttu-id="5eb37-129">TargetFqdn: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="5eb37-129">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="5eb37-130">Resultado: êxito</span><span class="sxs-lookup"><span data-stu-id="5eb37-130">Result : Success</span></span>

<span data-ttu-id="5eb37-131">Latência: 00:00:06.8630376</span><span class="sxs-lookup"><span data-stu-id="5eb37-131">Latency : 00:00:06.8630376</span></span>

<span data-ttu-id="5eb37-132">Erros</span><span class="sxs-lookup"><span data-stu-id="5eb37-132">Error :</span></span>

<span data-ttu-id="5eb37-133">Diagnóstico</span><span class="sxs-lookup"><span data-stu-id="5eb37-133">Diagnosis :</span></span>

<span data-ttu-id="5eb37-134">Se o usuário especificado não puder fazer logon ou logout, o resultado será mostrado como uma falha, e informações adicionais serão registradas nas propriedades de erro e diagnóstico:</span><span class="sxs-lookup"><span data-stu-id="5eb37-134">If the specified user can't log in or log out, the Result will be shown as Failure, and additional information will be recorded in the Error and Diagnosis properties:</span></span>

<span data-ttu-id="5eb37-135">TargetFqdn: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="5eb37-135">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="5eb37-136">Resultado: falha</span><span class="sxs-lookup"><span data-stu-id="5eb37-136">Result : Failure</span></span>

<span data-ttu-id="5eb37-137">Latência: 00:00:00</span><span class="sxs-lookup"><span data-stu-id="5eb37-137">Latency : 00:00:00</span></span>

<span data-ttu-id="5eb37-138">Erro: 404, não encontrado</span><span class="sxs-lookup"><span data-stu-id="5eb37-138">Error : 404, Not Found</span></span>

<span data-ttu-id="5eb37-139">Diagnóstico: ErrorCode = 1003, Source = ATL-cs-001. litwareinc. com, Reason = o usuário faz</span><span class="sxs-lookup"><span data-stu-id="5eb37-139">Diagnosis : ErrorCode=1003,source=atl-cs-001.litwareinc.com,Reason=User does</span></span>

<span data-ttu-id="5eb37-140">Não existe</span><span class="sxs-lookup"><span data-stu-id="5eb37-140">not exist</span></span>

<span data-ttu-id="5eb37-141">Microsoft. RTC. Signaling. DiagnosticHeader</span><span class="sxs-lookup"><span data-stu-id="5eb37-141">Microsoft.Rtc.Signaling.DiagnosticHeader</span></span>

<span data-ttu-id="5eb37-142">Por exemplo, a saída anterior diz que o teste falhou porque o usuário especificado não pôde ser encontrado.</span><span class="sxs-lookup"><span data-stu-id="5eb37-142">For example, the previous output states that the test failed because the specified user couldn't be found.</span></span> <span data-ttu-id="5eb37-143">Você pode determinar se um endereço SIP é ou não válido (e se o usuário atribuído cujo endereço SIP está habilitado para o Lync Server) executando este comando:</span><span class="sxs-lookup"><span data-stu-id="5eb37-143">You can determine whether or not a SIP address is valid (and whether the user assigned that SIP address is enabled for Lync Server) by running this command:</span></span>

    Get-CsUser "sip:kenmyer@litwareinc.com"

<span data-ttu-id="5eb37-144">Se Test-CsRegistration falhar, talvez você queira executar novamente o teste, desta vez, incluindo o parâmetro Verbose:</span><span class="sxs-lookup"><span data-stu-id="5eb37-144">If Test-CsRegistration fails, then you might want to rerun the test, this time including the Verbose parameter:</span></span>

    Test-CsRegistration -UserSipAddress "sip:kenmyer@litwareinc.com" -TargetFqdn "atl-cs-001.litwareinc.com" -Verbose

<span data-ttu-id="5eb37-145">Quando o parâmetro Verbose é incluído, Test-CsRegistration retornará uma conta passo a passo de cada ação que tentou quando verificou a capacidade do usuário especificado fazer logon no Lync Server.</span><span class="sxs-lookup"><span data-stu-id="5eb37-145">When the Verbose parameter is included, Test-CsRegistration will return a step-by-step account of each action it tried when it checked the ability of the specified user to log on to Lync Server.</span></span> <span data-ttu-id="5eb37-146">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="5eb37-146">For example:</span></span>

<span data-ttu-id="5eb37-147">VERBOse: atividade de ' registro ' iniciada.</span><span class="sxs-lookup"><span data-stu-id="5eb37-147">VERBOSE: 'Register' activity started.</span></span>

<span data-ttu-id="5eb37-148">Enviando solicitação de registro:</span><span class="sxs-lookup"><span data-stu-id="5eb37-148">Sending Registration request:</span></span>

<span data-ttu-id="5eb37-149">FQDN de destino = atl-cs-011.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="5eb37-149">Target Fqdn = atl-cs-011.litwareinc.com</span></span>

<span data-ttu-id="5eb37-150">Endereço SIP do usuário = sip:kenmyer@litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="5eb37-150">User Sip Address = sip:kenmyer@litwareinc.com</span></span>

<span data-ttu-id="5eb37-151">Porta do registrador = 5061.</span><span class="sxs-lookup"><span data-stu-id="5eb37-151">Registrar Port = 5061.</span></span>

<span data-ttu-id="5eb37-152">O tipo de autenticação ' confiável ' é selecionado.</span><span class="sxs-lookup"><span data-stu-id="5eb37-152">Auth Type 'Trusted' is selected.</span></span>

<span data-ttu-id="5eb37-153">Uma exceção ' o ponto de extremidade não pode ser registrada.</span><span class="sxs-lookup"><span data-stu-id="5eb37-153">An exception 'The endpoint is unable to register.</span></span> <span data-ttu-id="5eb37-154">Veja o código de erro por motivo específico, durante a execução do fluxo de trabalho Microsoft. RTC. SyntheticTransactions. Workflow. STRegistrerWorkflow.</span><span class="sxs-lookup"><span data-stu-id="5eb37-154">See the ErrorCode for specific reason' occurred during Workflow Microsoft.Rtc.SyntheticTransactions.Workflow.STRegistrerWorkflow execution.</span></span>

<span data-ttu-id="5eb37-155">Pilha de chamadas de exceção: em Microsoft. RTC. Signaling. SipAsyncResult'1. ThrowIfFailed ()</span><span class="sxs-lookup"><span data-stu-id="5eb37-155">Exception Call Stack: at Microsoft.Rtc.Signaling.SipAsyncResult'1.ThrowIfFailed()</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="5eb37-156">Motivos pelos quais o teste pode ter falhado</span><span class="sxs-lookup"><span data-stu-id="5eb37-156">Reasons why the test might have failed</span></span>

<span data-ttu-id="5eb37-157">Aqui estão alguns motivos comuns para que Test-CsRegistration possa falhar:</span><span class="sxs-lookup"><span data-stu-id="5eb37-157">Here are some common reasons why Test-CsRegistration might fail:</span></span>

  - <span data-ttu-id="5eb37-158">Você especificou uma conta de usuário incorreta.</span><span class="sxs-lookup"><span data-stu-id="5eb37-158">You specified an incorrect user account.</span></span> <span data-ttu-id="5eb37-159">Você pode verificar se uma conta de usuário existe executando um comando semelhante a este:</span><span class="sxs-lookup"><span data-stu-id="5eb37-159">You can verify that a user account exists by running a command similar to this:</span></span>
    
        Get-CsUser "sip:kenmyer@litwareinc.com"

  - <span data-ttu-id="5eb37-160">A conta de usuário é válida, mas a conta não está habilitada no momento para o Lync Server.</span><span class="sxs-lookup"><span data-stu-id="5eb37-160">The user account is valid, but the account is currently not enabled for Lync Server.</span></span> <span data-ttu-id="5eb37-161">Para verificar se uma conta de usuário está habilitada para o Lync Server, execute um comando semelhante ao seguinte:</span><span class="sxs-lookup"><span data-stu-id="5eb37-161">To verify that a user account is enabled for Lync Server, run a command similar to the following:</span></span>
    
        Get-CsUser "sip:kenmyer@litwareinc.com" | Select-Object Enabled
    
    <span data-ttu-id="5eb37-162">Se a propriedade Enabled estiver definida como false, isso significa que o usuário não está atualmente habilitado para o Lync Server.</span><span class="sxs-lookup"><span data-stu-id="5eb37-162">If the Enabled property is set to False, that means that the user is currently not enabled for Lync Server.</span></span>

  - <span data-ttu-id="5eb37-163">Você especificou um pool de registradores incorreto.</span><span class="sxs-lookup"><span data-stu-id="5eb37-163">You specified an incorrect Registrar pool.</span></span> <span data-ttu-id="5eb37-164">Você pode retornar os FQDNs dos pools de registradores usando este comando:</span><span class="sxs-lookup"><span data-stu-id="5eb37-164">You can return the FQDNs of your Registrar pools by using this command:</span></span>
    
        Get-CsService -Registrar | Select-Object PoolFqdn

  - <span data-ttu-id="5eb37-165">O pool de registradores não está disponível no momento.</span><span class="sxs-lookup"><span data-stu-id="5eb37-165">The Registrar pool is currently not available.</span></span> <span data-ttu-id="5eb37-166">Tente executar o ping no pool para ver se ele responderá:</span><span class="sxs-lookup"><span data-stu-id="5eb37-166">Try pinging the pool to see whether it responds:</span></span>
    
        ping atl-cs-001.litwareinc.com

</div>

</div>

<span> </span>

</div>

</div>

</div>

