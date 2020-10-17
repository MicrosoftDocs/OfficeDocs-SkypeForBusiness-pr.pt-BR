---
title: 'Lync Server 2013: como validar conferências de áudio/vídeo'
description: 'Lync Server 2013: como validar conferências de áudio/vídeo.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Validating audio/video conferences
ms:assetid: 6c8c422a-d501-42cb-820b-b002f9b2250b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720915(v=OCS.15)
ms:contentKeyID: 63969615
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ad12611e928a64b934252ec21c18b98366e0912b
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48547197"
---
# <a name="validating-audiovideo-conferences-in-lync-server-2013"></a><span data-ttu-id="1569a-103">Validar conferências de áudio/vídeo no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1569a-103">Validating audio/video conferences in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1569a-104">_**Última modificação do tópico:** 2014-06-05_</span><span class="sxs-lookup"><span data-stu-id="1569a-104">_**Topic Last Modified:** 2014-06-05_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1569a-105">Agenda de verificação</span><span class="sxs-lookup"><span data-stu-id="1569a-105">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="1569a-106">Diariamente</span><span class="sxs-lookup"><span data-stu-id="1569a-106">Daily</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1569a-107">Ferramenta de teste</span><span class="sxs-lookup"><span data-stu-id="1569a-107">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="1569a-108">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="1569a-108">Windows PowerShell</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1569a-109">Permissões obrigatórias</span><span class="sxs-lookup"><span data-stu-id="1569a-109">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="1569a-110">Ao executar localmente usando o Shell de gerenciamento do Lync Server, os usuários devem ser membros do grupo de segurança RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="1569a-110">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="1569a-111">Quando executado usando uma instância remota do Windows PowerShell, os usuários devem receber uma função RBAC que tenha permissão para executar o cmdlet Test-CsAVConference.</span><span class="sxs-lookup"><span data-stu-id="1569a-111">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsAVConference cmdlet.</span></span> <span data-ttu-id="1569a-112">Para ver uma lista de todas as funções RBAC que podem usar este cmdlet, execute o seguinte comando no prompt do Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="1569a-112">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsAVConference&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="1569a-113">Descrição</span><span class="sxs-lookup"><span data-stu-id="1569a-113">Description</span></span>

<span data-ttu-id="1569a-114">O cmdlet Test-CsAVConference verifica se dois usuários de teste podem participar de uma conferência de áudio/vídeo (A/V).</span><span class="sxs-lookup"><span data-stu-id="1569a-114">The Test-CsAVConference cmdlet checks whether two test users can participate in an audio/video (A/V) conference.</span></span> <span data-ttu-id="1569a-115">Quando o cmdlet for executado, os dois usuários serão registrados no sistema.</span><span class="sxs-lookup"><span data-stu-id="1569a-115">When the cmdlet runs, the two users are logged on to the system.</span></span> <span data-ttu-id="1569a-116">Após enfrentar o logon bem-sucedido, o primeiro usuário cria uma conferência de A/V e, em seguida, aguarda o segundo usuário ingressar nessa conferência.</span><span class="sxs-lookup"><span data-stu-id="1569a-116">After they face successfully logged on, the first user creates an A/V conference, and then waits for the second user to join that conference.</span></span> <span data-ttu-id="1569a-117">Depois de uma breve troca de dados, a conferência é excluída e os dois usuários de teste fazem logoff.</span><span class="sxs-lookup"><span data-stu-id="1569a-117">After a brief exchange of data, the conference is deleted and the two tests users are logged off.</span></span>

<span data-ttu-id="1569a-118">Observe que Test-CsAVConference não realiza uma conferência A/V real entre os dois usuários de teste.</span><span class="sxs-lookup"><span data-stu-id="1569a-118">Note that Test-CsAVConference does not conduct an actual A/V conference between the two test users.</span></span> <span data-ttu-id="1569a-119">Em vez disso, o cmdlet verifica se os dois usuários podem fazer todas as conexões necessárias para a realização de uma conferência.</span><span class="sxs-lookup"><span data-stu-id="1569a-119">Instead, the cmdlet verifies that the two users can make all the connections necessary to conduct such a conference.</span></span>

<span data-ttu-id="1569a-120">Outros exemplos para este comando podem ser encontrados em [Test-CsAVConference](https://docs.microsoft.com/powershell/module/skype/Test-CsAVConference).</span><span class="sxs-lookup"><span data-stu-id="1569a-120">Further examples for this command can be found at [Test-CsAVConference](https://docs.microsoft.com/powershell/module/skype/Test-CsAVConference).</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="1569a-121">Executar o teste</span><span class="sxs-lookup"><span data-stu-id="1569a-121">Running the test</span></span>

<span data-ttu-id="1569a-122">O cmdlet Test-CsAVConference pode ser executado usando um par de contas de teste pré-configuradas (Confira Configurando contas de teste para executar testes do Lync Server) ou as contas de dois usuários que estão habilitados para o Lync Server.</span><span class="sxs-lookup"><span data-stu-id="1569a-122">The Test-CsAVConference cmdlet can be run using either a pair of preconfigured test accounts (see Setting Up Test Accounts for Running Lync Server Tests) or the accounts of any two users who are enabled for Lync Server.</span></span> <span data-ttu-id="1569a-123">Para executar essa verificação usando contas de teste, basta especificar o FQDN do pool do Lync Server que está sendo testado.</span><span class="sxs-lookup"><span data-stu-id="1569a-123">To run this check using test accounts, you just have to specify the FQDN of the Lync Server pool being tested.</span></span> <span data-ttu-id="1569a-124">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="1569a-124">For example:</span></span>

    Test-CsAVConference -TargetFqdn "atl-cs-001.litwareinc.com"

<span data-ttu-id="1569a-125">Para executar essa verificação usando contas de usuário reais, você deve criar dois objetos de credenciais do Windows PowerShell (objetos que contêm o nome da conta e a senha) para cada conta.</span><span class="sxs-lookup"><span data-stu-id="1569a-125">To run this check using actual user accounts, you must create two Windows PowerShell credentials objects (objects that contain the account name and password) for each account.</span></span> <span data-ttu-id="1569a-126">Em seguida, você deve incluir esses objetos de credenciais e os endereços SIP das duas contas ao chamar Test-CsAVConference:</span><span class="sxs-lookup"><span data-stu-id="1569a-126">You must then include those credentials objects and the SIP addresses of the two accounts when they call Test-CsAVConference:</span></span>

    $credential1 = Get-Credential "litwareinc\kenmyer"
    $credential2 = Get-Credential "litwareinc\davidlongmire"
    Test-CsAVConference -TargetFqdn "atl-cs-001.litwareinc.com" -SenderSipAddress "sip:kenmyer@litwareinc.com" -SenderCredential $credential1 -ReceiverSipAddress "sip:davidlongmire@litwareinc.com" -ReceiverCredential $credential2

<span data-ttu-id="1569a-127">Para obter mais informações, consulte a documentação de ajuda para o cmdlet [Test-CsAVConference](https://docs.microsoft.com/powershell/module/skype/Test-CsAVConference) .</span><span class="sxs-lookup"><span data-stu-id="1569a-127">For more information, see the Help documentation for the [Test-CsAVConference](https://docs.microsoft.com/powershell/module/skype/Test-CsAVConference) cmdlet.</span></span>

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="1569a-128">Determinando o sucesso ou a falha</span><span class="sxs-lookup"><span data-stu-id="1569a-128">Determining Success or Failure</span></span>

<span data-ttu-id="1569a-129">Se os usuários especificados puderem concluir com êxito uma conferência A/V, você receberá uma saída semelhante a esta, com a propriedade Result marcada como **Success:**</span><span class="sxs-lookup"><span data-stu-id="1569a-129">If the specified users can successfully complete an A/V conference, you'll receive output similar to this, with the Result property marked as **Success:**</span></span>

<span data-ttu-id="1569a-130">TargetFqdn: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="1569a-130">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="1569a-131">Resultado: êxito</span><span class="sxs-lookup"><span data-stu-id="1569a-131">Result : Success</span></span>

<span data-ttu-id="1569a-132">Latência: 00:00:02.6841765</span><span class="sxs-lookup"><span data-stu-id="1569a-132">Latency : 00:00:02.6841765</span></span>

<span data-ttu-id="1569a-133">Erros</span><span class="sxs-lookup"><span data-stu-id="1569a-133">Error :</span></span>

<span data-ttu-id="1569a-134">Diagnóstico</span><span class="sxs-lookup"><span data-stu-id="1569a-134">Diagnosis :</span></span>

<span data-ttu-id="1569a-135">Se os usuários não puderem concluir a conferência, o resultado será mostrado como falha, e informações adicionais serão registradas nas propriedades de erro e diagnóstico:</span><span class="sxs-lookup"><span data-stu-id="1569a-135">If the users can not complete the conference, then the Result will be shown as Failure, and additional information will be recorded in the Error and Diagnosis properties:</span></span>

<span data-ttu-id="1569a-136">TargetFqdn: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="1569a-136">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="1569a-137">Resultado: falha</span><span class="sxs-lookup"><span data-stu-id="1569a-137">Result : Failure</span></span>

<span data-ttu-id="1569a-138">Latência: 00:00:00</span><span class="sxs-lookup"><span data-stu-id="1569a-138">Latency : 00:00:00</span></span>

<span data-ttu-id="1569a-139">Erro: 404, não encontrado</span><span class="sxs-lookup"><span data-stu-id="1569a-139">Error : 404, Not Found</span></span>

<span data-ttu-id="1569a-140">Diagnóstico: ErrorCode = 4005, Source = ATL-cs-001.litwareinc.com,</span><span class="sxs-lookup"><span data-stu-id="1569a-140">Diagnosis : ErrorCode=4005,Source=atl-cs-001.litwareinc.com,</span></span>

<span data-ttu-id="1569a-141">Razão = o URI de destino não está habilitado para SIP ou não</span><span class="sxs-lookup"><span data-stu-id="1569a-141">Reason=Destination URI either not enabled for SIP or does not</span></span>

<span data-ttu-id="1569a-142">existente.</span><span class="sxs-lookup"><span data-stu-id="1569a-142">exist.</span></span>

<span data-ttu-id="1569a-143">Microsoft. RTC. Signaling. DiagnosticHeader</span><span class="sxs-lookup"><span data-stu-id="1569a-143">Microsoft.Rtc.Signaling.DiagnosticHeader</span></span>

<span data-ttu-id="1569a-144">Por exemplo, a saída anterior diz que o teste falhou porque pelo menos uma das duas contas de usuário não era válida porque a conta não existe ou porque a conta não foi habilitada para o Lync Server.</span><span class="sxs-lookup"><span data-stu-id="1569a-144">For example, the previous output states that the test failed because at least one of the two user accounts was not valid, either because the account does not exist or because the account has not been enabled for Lync Server.</span></span> <span data-ttu-id="1569a-145">Você pode verificar a existência das duas contas de teste e se elas foram habilitadas para o Lync Server, executando um comando semelhante ao seguinte:</span><span class="sxs-lookup"><span data-stu-id="1569a-145">You can verify the existence of the two test accounts, and whether they were enabled for Lync Server, by running a command similar to the following:</span></span>

    "sip:kenmyer@litwareinc.com","sip:davidlongmire@litwareinc.com" | Get-CsUser | Select-Object SipAddress, enabled

<span data-ttu-id="1569a-146">Se Test-CsAVConference falhar, talvez você queira executar novamente o teste, desta vez, incluindo o parâmetro Verbose:</span><span class="sxs-lookup"><span data-stu-id="1569a-146">If Test-CsAVConference fails, then you might want to rerun the test, this time including the Verbose parameter:</span></span>

    Test-CsAVConference -TargetFqdn "atl-cs-001.litwareinc.com" -Verbose

<span data-ttu-id="1569a-147">Quando o parâmetro Verbose é incluído Test-CsAVConference retornará uma conta passo a passo de cada ação que tentou quando verificou a capacidade dos usuários especificados de participar de uma conferência AV.</span><span class="sxs-lookup"><span data-stu-id="1569a-147">When the Verbose parameter is included Test-CsAVConference will return a step-by-step account of each action it tried when it checked the ability of the specified users to participate in an AV conference.</span></span> <span data-ttu-id="1569a-148">Por exemplo, suponha que o teste falhe e que você receba o seguinte diagnóstico:</span><span class="sxs-lookup"><span data-stu-id="1569a-148">For example, suppose that your test fails and you receive the following Diagnosis:</span></span>

<span data-ttu-id="1569a-149">ErrorCode = 1008, Source = accessproxy. litwareinc. com, Reason = não é possível resolver o registro SRV de DNS</span><span class="sxs-lookup"><span data-stu-id="1569a-149">ErrorCode=1008,Source=accessproxy.litwareinc.com,Reason=Unable to resolve DNS SRV record</span></span>

<span data-ttu-id="1569a-150">Se você executar novamente o teste usando o parâmetro Verbose, as informações passo a passo retornadas incluirão uma saída semelhante a esta:</span><span class="sxs-lookup"><span data-stu-id="1569a-150">If you rerun the test using the Verbose parameter, the step-by-step information returned will include output similar to this:</span></span>

<span data-ttu-id="1569a-151">VERBOse: atividade de ' registro ' iniciada.</span><span class="sxs-lookup"><span data-stu-id="1569a-151">VERBOSE: 'Register' activity started.</span></span>

<span data-ttu-id="1569a-152">Enviando solicitação de registro:</span><span class="sxs-lookup"><span data-stu-id="1569a-152">Sending Registration request:</span></span>

<span data-ttu-id="1569a-153">FQDN de destino = atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="1569a-153">Target Fqdn = atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="1569a-154">Endereço SIP do usuário = sip:davidlongmire@litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="1569a-154">User Sip Address = sip:davidlongmire@litwareinc.com</span></span>

<span data-ttu-id="1569a-155">Porta do registrador = 5061.</span><span class="sxs-lookup"><span data-stu-id="1569a-155">Registrar Port = 5061.</span></span>

<span data-ttu-id="1569a-156">O tipo de autenticação ' confiável ' é selecionado.</span><span class="sxs-lookup"><span data-stu-id="1569a-156">Auth Type 'Trusted' is selected.</span></span>

<span data-ttu-id="1569a-157">Atividade de ' Register ' iniciada.</span><span class="sxs-lookup"><span data-stu-id="1569a-157">'Register' activity started.</span></span>

<span data-ttu-id="1569a-158">Enviando solicitação de registro:</span><span class="sxs-lookup"><span data-stu-id="1569a-158">Sending Registration request:</span></span>

<span data-ttu-id="1569a-159">FQDN de destino = atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="1569a-159">Target Fqdn = atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="1569a-160">Endereço SIP do usuário = sip:kenmyer@litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="1569a-160">User Sip Address = sip:kenmyer@litwareinc.com</span></span>

<span data-ttu-id="1569a-161">Porta do registrador = 5061.</span><span class="sxs-lookup"><span data-stu-id="1569a-161">Registrar Port = 5061.</span></span>

<span data-ttu-id="1569a-162">O tipo de autenticação ' confiável ' é selecionado.</span><span class="sxs-lookup"><span data-stu-id="1569a-162">Auth Type 'Trusted' is selected.</span></span>

<span data-ttu-id="1569a-163">Uma exceção ' o ponto de extremidade não pôde ser registrado.</span><span class="sxs-lookup"><span data-stu-id="1569a-163">An exception 'The endpoint was unable to register.</span></span> <span data-ttu-id="1569a-164">Consulte ErrorCode por motivo específico. "</span><span class="sxs-lookup"><span data-stu-id="1569a-164">See the ErrorCode for specific reason.'</span></span> <span data-ttu-id="1569a-165">ocorreu durante o fluxo de trabalho</span><span class="sxs-lookup"><span data-stu-id="1569a-165">occurred during Workflow</span></span>

<span data-ttu-id="1569a-166">A última linha desse resultado indica que o usuário sip:kenmyer@litwareinc.com não pôde se registrar no Lync Server.</span><span class="sxs-lookup"><span data-stu-id="1569a-166">The last line in that output indicates that the user sip:kenmyer@litwareinc.com was unable to register with Lync Server.</span></span> <span data-ttu-id="1569a-167">Isso significa que você deve verificar se o endereço SIP sip:kenmyer@litwareinc.com é válido e se o usuário associado está habilitado para o Lync Server.</span><span class="sxs-lookup"><span data-stu-id="1569a-167">That means that you should verify that the SIP address sip:kenmyer@litwareinc.com is valid, and that the associated user is enabled for Lync Server.</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="1569a-168">Motivos pelos quais o teste pode ter falhado</span><span class="sxs-lookup"><span data-stu-id="1569a-168">Reasons why the test might have failed</span></span>

<span data-ttu-id="1569a-169">Aqui estão alguns motivos comuns para que Test-CsAVConference possa falhar:</span><span class="sxs-lookup"><span data-stu-id="1569a-169">Here are some common reasons why Test-CsAVConference might fail:</span></span>

  - <span data-ttu-id="1569a-170">Você especificou uma conta de usuário que não é válida.</span><span class="sxs-lookup"><span data-stu-id="1569a-170">You specified a user account that is not valid.</span></span> <span data-ttu-id="1569a-171">Você pode verificar se uma conta de usuário existe executando um comando semelhante a este:</span><span class="sxs-lookup"><span data-stu-id="1569a-171">You can verify that a user account exists by running a command similar to this:</span></span>
    
        Get-CsUser "sip:kenmyer@litwareinc.com"

  - <span data-ttu-id="1569a-172">A conta de usuário é válida, mas a conta não está habilitada no momento para o Lync Server.</span><span class="sxs-lookup"><span data-stu-id="1569a-172">The user account is valid, but the account is currently not enabled for Lync Server.</span></span> <span data-ttu-id="1569a-173">Para verificar se uma conta de usuário está habilitada para o Lync Server, execute um comando semelhante ao seguinte:</span><span class="sxs-lookup"><span data-stu-id="1569a-173">To verify that a user account is enabled for Lync Server, run a command similar to the following:</span></span>
    
        Get-CsUser "sip:kenmyer@litwareinc.com" | Select-Object Enabled
    
    <span data-ttu-id="1569a-174">Se a propriedade Enabled estiver definida como false, isso significa que o usuário não está habilitado para o Lync Server no momento.</span><span class="sxs-lookup"><span data-stu-id="1569a-174">If the Enabled property is set to False that means that the user is currently not enabled for Lync Server.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

