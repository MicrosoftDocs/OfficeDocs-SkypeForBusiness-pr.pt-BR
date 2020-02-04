---
title: 'Lync Server 2013: testando a capacidade de fazer mensagens instantâneas em grupo'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing ability to do group IM
ms:assetid: ca5545bc-51ac-490f-b96b-917bb742ad04
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn743839(v=OCS.15)
ms:contentKeyID: 63969652
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8552d5caadf26d70265f5538f10c6152eb67dcc8
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41745981"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="testing-ability-to-do-group-im-in-lync-server-2013"></a><span data-ttu-id="cc441-102">Testar a capacidade de fazer mensagens instantâneas em grupo no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="cc441-102">Testing ability to do group IM in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="cc441-103">_**Tópico da última modificação:** 2014-06-05_</span><span class="sxs-lookup"><span data-stu-id="cc441-103">_**Topic Last Modified:** 2014-06-05_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="cc441-104">Cronograma de verificação</span><span class="sxs-lookup"><span data-stu-id="cc441-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="cc441-105">Diário</span><span class="sxs-lookup"><span data-stu-id="cc441-105">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cc441-106">Ferramenta de teste</span><span class="sxs-lookup"><span data-stu-id="cc441-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="cc441-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="cc441-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cc441-108">Permissões necessárias</span><span class="sxs-lookup"><span data-stu-id="cc441-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="cc441-109">Quando executado localmente usando o Shell de gerenciamento do Lync Server, os usuários devem ser membros do grupo de segurança RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="cc441-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="cc441-110">Quando executado usando uma instância remota do Windows PowerShell, os usuários devem receber uma função RBAC que tenha permissão para executar o cmdlet Test-CsGroupIM.</span><span class="sxs-lookup"><span data-stu-id="cc441-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsGroupIM cmdlet.</span></span> <span data-ttu-id="cc441-111">Para ver uma lista de todas as funções RBAC que podem usar esse cmdlet, execute o seguinte comando no prompt do Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="cc441-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsGroupIM&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="cc441-112">Descrição</span><span class="sxs-lookup"><span data-stu-id="cc441-112">Description</span></span>

<span data-ttu-id="cc441-113">O cmdlet Test-CsGroupIM verifica se os usuários em sua organização podem conduzir sessões de mensagens instantâneas em grupo.</span><span class="sxs-lookup"><span data-stu-id="cc441-113">The Test-CsGroupIM cmdlet verifies that users in your organization can conduct group instant messaging sessions.</span></span> <span data-ttu-id="cc441-114">Ao executar Test-CsGroupIM, o cmdlet tenta entrar em um par de usuários de teste para o Lync Server.</span><span class="sxs-lookup"><span data-stu-id="cc441-114">When you run Test-CsGroupIM, the cmdlet attempts to sign in a pair of test users to Lync Server.</span></span> <span data-ttu-id="cc441-115">Se for bem-sucedido, o Test-CsGroupIM criará uma nova conferência usando o primeiro usuário de teste e convidará o segundo usuário para ingressar na conferência.</span><span class="sxs-lookup"><span data-stu-id="cc441-115">If successful, Test-CsGroupIM creates a new conference using the first test user, then invites the second user to join the conference.</span></span> <span data-ttu-id="cc441-116">Após uma troca de mensagens, os dois usuários são desconectados do sistema.</span><span class="sxs-lookup"><span data-stu-id="cc441-116">After an exchange of messages, both users are then disconnected from the system.</span></span> <span data-ttu-id="cc441-117">Observe que tudo isso acontece sem qualquer interação do usuário e sem afetar os usuários reais.</span><span class="sxs-lookup"><span data-stu-id="cc441-117">Note that all of this happens without any user interaction, and without affecting any actual users.</span></span> <span data-ttu-id="cc441-118">Por exemplo, suponha que o sip:kenmyer@litwareinc.com da conta de teste corresponda a um usuário real que tenha uma conta real do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="cc441-118">For example, suppose that the test account sip:kenmyer@litwareinc.com corresponds to a real user who has a real Lync Server account.</span></span> <span data-ttu-id="cc441-119">Nesse caso, o teste será realizado sem qualquer interrupção no Ken Myer verdadeiro.</span><span class="sxs-lookup"><span data-stu-id="cc441-119">In that case, the test will be conducted without any disruption to the real Ken Myer.</span></span> <span data-ttu-id="cc441-120">Por exemplo, mesmo quando a conta de teste de Ken Myer se desconecta do sistema, Ken Myer a pessoa permanecerá conectada.</span><span class="sxs-lookup"><span data-stu-id="cc441-120">For example, even when the Ken Myer test account logs off from the system, Ken Myer the person will remain logged on.</span></span> <span data-ttu-id="cc441-121">Da mesma forma, o "Ken Myer" realmente não receberá um convite para participar da conferência.</span><span class="sxs-lookup"><span data-stu-id="cc441-121">Likewise, the real Ken Myer won't receive an invitation to join the conference.</span></span> <span data-ttu-id="cc441-122">Este convite será enviado para e aceito pela conta de teste.</span><span class="sxs-lookup"><span data-stu-id="cc441-122">That invitation will be sent to, and accepted by, the test account.</span></span>

<span data-ttu-id="cc441-123">Para obter mais informações, consulte a documentação da ajuda para o cmdlet [Test-CsGroupIM](https://docs.microsoft.com/powershell/module/skype/Test-CsGroupIM) .</span><span class="sxs-lookup"><span data-stu-id="cc441-123">For more information, see the Help documentation for the [Test-CsGroupIM](https://docs.microsoft.com/powershell/module/skype/Test-CsGroupIM) cmdlet.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="cc441-124">Executar o teste</span><span class="sxs-lookup"><span data-stu-id="cc441-124">Running the test</span></span>

<span data-ttu-id="cc441-125">O cmdlet Test-CsGroupIM pode ser executado usando um par de contas de teste pré-configuradas (consulte Configurando contas de teste para executar testes do Lync Server) ou das contas de dois usuários que estão habilitados para o Lync Server.</span><span class="sxs-lookup"><span data-stu-id="cc441-125">The Test-CsGroupIM cmdlet can be run using either a pair of preconfigured test accounts (see Setting Up Test Accounts for Running Lync Server Tests) or the accounts of any two users who are enabled for Lync Server.</span></span> <span data-ttu-id="cc441-126">Para executar essa verificação usando contas de teste, basta especificar o FQDN do pool do servidor do Lync que está sendo testado.</span><span class="sxs-lookup"><span data-stu-id="cc441-126">To run this check using test accounts, you just have to specify the FQDN of the Lync Server pool being tested.</span></span> <span data-ttu-id="cc441-127">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="cc441-127">For example:</span></span>

    Test-CsGroupIM -TargetFqdn "atl-cs-001.litwareinc.com"

<span data-ttu-id="cc441-128">Para executar essa verificação usando contas de usuário reais, você deve criar dois objetos de credenciais do Shell de gerenciamento do Lync Server (objetos que contêm o nome e a senha da conta) para cada conta.</span><span class="sxs-lookup"><span data-stu-id="cc441-128">To run this check using actual user accounts, you must create two Lync Server Management Shell credentials objects (objects that contain the account name and password) for each account.</span></span> <span data-ttu-id="cc441-129">Em seguida, você deve incluir esses objetos de credenciais e os endereços SIP das duas contas ao chamar Test-CsGroupIM:</span><span class="sxs-lookup"><span data-stu-id="cc441-129">You must then include those credentials objects and the SIP addresses of the two accounts when you call Test-CsGroupIM:</span></span>

    $credential1 = Get-Credential "litwareinc\kenmyer"
    $credential2 = Get-Credential "litwareinc\davidlongmire"
    Test-CsGroupIm -TargetFqdn "atl-cs-001.litwareinc.com" -SenderSipAddress "sip:kenmyer@litwareinc.com" -SenderCredential $credential1 -ReceiverSipAddress "sip:davidlongmire@litwareinc.com" -ReceiverCredential $credential2

<span data-ttu-id="cc441-130">Para obter mais informações, consulte a documentação da ajuda para o cmdlet [Test-CsGroupIM](https://docs.microsoft.com/powershell/module/skype/Test-CsGroupIM) .</span><span class="sxs-lookup"><span data-stu-id="cc441-130">For more information, see the Help documentation for the [Test-CsGroupIM](https://docs.microsoft.com/powershell/module/skype/Test-CsGroupIM) cmdlet.</span></span>

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="cc441-131">Determinação do sucesso ou falha</span><span class="sxs-lookup"><span data-stu-id="cc441-131">Determining Success or Failure</span></span>

<span data-ttu-id="cc441-132">Se os dois usuários puderem concluir uma sessão de mensagens instantâneas em grupo, você receberá uma saída semelhante a isso com a propriedade Result marcada como **Success:**</span><span class="sxs-lookup"><span data-stu-id="cc441-132">If the two users can complete a group instant messaging session, you'll receive output similar to this with the Result property marked as **Success:**</span></span>

<span data-ttu-id="cc441-133">TargetFqdn: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="cc441-133">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="cc441-134">Resultado: êxito</span><span class="sxs-lookup"><span data-stu-id="cc441-134">Result : Success</span></span>

<span data-ttu-id="cc441-135">Latência: 00:00:06.3812203</span><span class="sxs-lookup"><span data-stu-id="cc441-135">Latency : 00:00:06.3812203</span></span>

<span data-ttu-id="cc441-136">Erros</span><span class="sxs-lookup"><span data-stu-id="cc441-136">Error :</span></span>

<span data-ttu-id="cc441-137">Correto</span><span class="sxs-lookup"><span data-stu-id="cc441-137">Diagnosis :</span></span>

<span data-ttu-id="cc441-138">Se os dois usuários não puderem concluir a sessão de mensagens instantâneas, o resultado será mostrado como uma falha, e informações adicionais serão gravadas nas propriedades de erro e diagnóstico:</span><span class="sxs-lookup"><span data-stu-id="cc441-138">If the two users can't able to complete the instant messaging session, then the Result will be shown as Failure, and additional information will be recorded in the Error and Diagnosis properties:</span></span>

<span data-ttu-id="cc441-139">TargetFqdn: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="cc441-139">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="cc441-140">Resultado: falha</span><span class="sxs-lookup"><span data-stu-id="cc441-140">Result : Failure</span></span>

<span data-ttu-id="cc441-141">Latência: 00:00:00</span><span class="sxs-lookup"><span data-stu-id="cc441-141">Latency : 00:00:00</span></span>

<span data-ttu-id="cc441-142">Erro: 404, não encontrado</span><span class="sxs-lookup"><span data-stu-id="cc441-142">Error : 404, Not Found</span></span>

<span data-ttu-id="cc441-143">Diagnóstico: ErrorCode = 4005, Source = ATL-cs-001.litwareinc.com,</span><span class="sxs-lookup"><span data-stu-id="cc441-143">Diagnosis : ErrorCode=4005,Source=atl-cs-001.litwareinc.com,</span></span>

<span data-ttu-id="cc441-144">Motivo = o URI de destino não está habilitado para SIP ou não</span><span class="sxs-lookup"><span data-stu-id="cc441-144">Reason=Destination URI either not enabled for SIP or does not</span></span>

<span data-ttu-id="cc441-145">Existem.</span><span class="sxs-lookup"><span data-stu-id="cc441-145">exist.</span></span>

<span data-ttu-id="cc441-146">Microsoft. RTC. Signaling. DiagnosticHeader</span><span class="sxs-lookup"><span data-stu-id="cc441-146">Microsoft.Rtc.Signaling.DiagnosticHeader</span></span>

<span data-ttu-id="cc441-147">A saída anterior informa que o teste falhou porque, pelo menos uma das contas de teste não era válida, porque a conta não existe ou porque o usuário não foi habilitado para o Lync Server.</span><span class="sxs-lookup"><span data-stu-id="cc441-147">The previous output states that the test failed because at least one of the test accounts was not valid, either because the account does not exist or because the user has not been enabled for Lync Server.</span></span> <span data-ttu-id="cc441-148">Você pode verificar se a conta existe e se a conta foi habilitada para nm-OCS-14-3ª executando um comando semelhante a este:</span><span class="sxs-lookup"><span data-stu-id="cc441-148">You can verify the account exists, and whether or not the account has been enabled for nm-ocs-14-3rd by running a command similar to this:</span></span>

    "Ken Myer", "David Longmire" | Get-CsUser | Select-Object SipAddress, Enabled

<span data-ttu-id="cc441-149">Se Test-CsGroupIM falhar, talvez você queira executar novamente o teste, desta vez, incluindo o parâmetro Verbose:</span><span class="sxs-lookup"><span data-stu-id="cc441-149">If Test-CsGroupIM fails, then you might want to rerun the test, this time including the Verbose parameter:</span></span>

    Test-CsGroupIM -TargetFqdn "atl-cs-001.litwareinc.com" -Verbose

<span data-ttu-id="cc441-150">Quando o parâmetro Verbose estiver incluído, Test-CsGroupIM retornará uma conta passo a passo de cada ação que tentou verificar quando verificou a capacidade dos usuários especificados para participar de sessões de mensagens instantâneas em grupo.</span><span class="sxs-lookup"><span data-stu-id="cc441-150">When the Verbose parameter is included, Test-CsGroupIM will return a step-by-step account of each action it tried when it checked the ability of the specified users to participate in a group instant messaging sessions.</span></span> <span data-ttu-id="cc441-151">Por exemplo, se o teste falhar e você for informado de que uma ou mais contas de usuário não são válidas, você pode executar novamente o teste usando o parâmetro Verbose e determinar qual conta de usuário não é válida:</span><span class="sxs-lookup"><span data-stu-id="cc441-151">For example, if your test fails and you are told that one or more of the user accounts is not valid, you can rerun the test using the Verbose parameter and determine which user account is not valid:</span></span>

<span data-ttu-id="cc441-152">Enviando solicitação de registro:</span><span class="sxs-lookup"><span data-stu-id="cc441-152">Sending Registration request:</span></span>

 <span data-ttu-id="cc441-153">FQDN de destino = atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="cc441-153">Target Fqdn      = atl-cs-001.litwareinc.com</span></span>

 <span data-ttu-id="cc441-154">Endereço SIP do usuário = sip:kenmyer@litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="cc441-154">User SIP Address = sip:kenmyer@litwareinc.com</span></span>

 <span data-ttu-id="cc441-155">Porta do registro = 5061</span><span class="sxs-lookup"><span data-stu-id="cc441-155">Register Port    = 5061</span></span>

<span data-ttu-id="cc441-156">O tipo de autenticação ' IWA ' é selecionado.</span><span class="sxs-lookup"><span data-stu-id="cc441-156">Auth type 'IWA' is selected.</span></span>

<span data-ttu-id="cc441-157">Uma exceção ' o logon foi negado.</span><span class="sxs-lookup"><span data-stu-id="cc441-157">An exception 'The log on was denied.</span></span> <span data-ttu-id="cc441-158">Verifique se as credenciais corretas estão sendo usadas e se a conta está ativa</span><span class="sxs-lookup"><span data-stu-id="cc441-158">Check that the correct credentials are being used and the account is active'</span></span>

<span data-ttu-id="cc441-159">Como você pode ver, neste exemplo, o usuário que tem o endereço SIP sip:kenmyer@litwareinc.com não pôde fazer logon.</span><span class="sxs-lookup"><span data-stu-id="cc441-159">As you can see, in this example the user who has the SIP address sip:kenmyer@litwareinc.com was not able to log on.</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="cc441-160">Motivos pelos quais o teste pode ter falhado</span><span class="sxs-lookup"><span data-stu-id="cc441-160">Reasons why the test might have failed</span></span>

<span data-ttu-id="cc441-161">Aqui estão alguns motivos comuns pelos quais Test-CsGroupIM pode falhar:</span><span class="sxs-lookup"><span data-stu-id="cc441-161">Here are some common reasons why Test-CsGroupIM might fail:</span></span>

  - <span data-ttu-id="cc441-162">Você especificou uma conta de usuário incorreta.</span><span class="sxs-lookup"><span data-stu-id="cc441-162">You specified an incorrect user account.</span></span> <span data-ttu-id="cc441-163">Você pode verificar se existe uma conta de usuário executando um comando semelhante a este:</span><span class="sxs-lookup"><span data-stu-id="cc441-163">You can verify that a user account exists by running a command similar to this:</span></span>
    
        Get-CsUser "sip:kenmyer@litwareinc.com"

  - <span data-ttu-id="cc441-164">A conta de usuário é válida, mas a conta não está habilitada no momento para o Lync Server.</span><span class="sxs-lookup"><span data-stu-id="cc441-164">The user account is valid, but the account is currently not enabled for Lync Server.</span></span> <span data-ttu-id="cc441-165">Para verificar se uma conta de usuário foi habilitada para o Lync Server, execute um comando semelhante ao seguinte:</span><span class="sxs-lookup"><span data-stu-id="cc441-165">To verify that a user account was enabled for Lync Server, run a command similar to the following:</span></span>
    
    <span data-ttu-id="cc441-166">Get-CsUser "sip:kenmyer@litwareinc.com" | Selecionar-objeto habilitado</span><span class="sxs-lookup"><span data-stu-id="cc441-166">Get-CsUser "sip:kenmyer@litwareinc.com" | Select-Object Enabled</span></span>
    
    <span data-ttu-id="cc441-167">Se a propriedade Enabled estiver definida como false, isso significa que o usuário não está habilitado no momento para o Lync Server.</span><span class="sxs-lookup"><span data-stu-id="cc441-167">If the Enabled property is set to False, that means that the user is currently not enabled for Lync Server.</span></span>

  - <span data-ttu-id="cc441-168">O serviço de mensagem instantânea pode não estar disponível.</span><span class="sxs-lookup"><span data-stu-id="cc441-168">The instant messaging service might not be available.</span></span> <span data-ttu-id="cc441-169">Com o Lync Server, você pode configurar o sistema para que o sistema de mensagens instantâneas não esteja disponível se o banco de dados de arquivamento não puder ser acessado.</span><span class="sxs-lookup"><span data-stu-id="cc441-169">With Lync Server, you can configure the system so that instant messaging is not available if the archiving database cannot be accessed.</span></span> <span data-ttu-id="cc441-170">Você pode verificar se está executando um comando semelhante ao seguinte:</span><span class="sxs-lookup"><span data-stu-id="cc441-170">You can verify that by running a command similar to the following:</span></span>
    
        Get-CsArchivingConfiguration -Identity "atl-cs-001.litwareinc.com" | Select-Object BlockOnArchiveFailure
    
    <span data-ttu-id="cc441-171">Se BlockOnArchiveFailure for definido como true, você deve determinar se o banco de dados de arquivamento está disponível.</span><span class="sxs-lookup"><span data-stu-id="cc441-171">If BlockOnArchiveFailure is set to True, then you should determine whether or not the archiving database is available.</span></span> <span data-ttu-id="cc441-172">Você pode retornar os locais dos bancos de dados de arquivamento usando o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="cc441-172">You can return the locations of your archiving databases by using the following command:</span></span>
    
        Get-CsService -ArchivingDatabase

  - <span data-ttu-id="cc441-173">O servidor de arquivamento pode não estar disponível.</span><span class="sxs-lookup"><span data-stu-id="cc441-173">The Archiving Server might not be available.</span></span> <span data-ttu-id="cc441-174">Você pode recuperar o FQDN dos seus servidores de arquivamento usando este comando:</span><span class="sxs-lookup"><span data-stu-id="cc441-174">You can retrieve the FQDN of your Archiving Servers by using this command:</span></span>
    
        Get-CsService -ArchivingServer
    
    <span data-ttu-id="cc441-175">Em seguida, você pode executar ping no servidor apropriado para verificar se ele está disponível.</span><span class="sxs-lookup"><span data-stu-id="cc441-175">You can then ping the appropriate server to verify that it is available.</span></span> <span data-ttu-id="cc441-176">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="cc441-176">For example:</span></span>
    
        ping atl-archiving-001.litwareinc.com

</div>

</div>

<span> </span>

</div>

</div>

</div>

