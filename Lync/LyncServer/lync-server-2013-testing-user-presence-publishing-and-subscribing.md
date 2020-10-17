---
title: 'Lync Server 2013: testar a publicação de presença do usuário e inscrever-se'
description: 'Lync Server 2013: testar a publicação de presença do usuário e inscrever-se.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing user presence publishing and subscribing
ms:assetid: 27694c71-8e63-4aa4-b49f-fa06ccb81949
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn743832(v=OCS.15)
ms:contentKeyID: 63969587
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 90913f270fbd034ca4d2ea7cf3b93c255fc95c66
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48541847"
---
# <a name="testing-user-presence-publishing-and-subscribing-in-lync-server-2013"></a><span data-ttu-id="3e162-103">Testar a publicação de presença do usuário e inscrever-se no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3e162-103">Testing user presence publishing and subscribing in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3e162-104">_**Última modificação do tópico:** 2014-06-05_</span><span class="sxs-lookup"><span data-stu-id="3e162-104">_**Topic Last Modified:** 2014-06-05_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="3e162-105">Agenda de verificação</span><span class="sxs-lookup"><span data-stu-id="3e162-105">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="3e162-106">Diariamente</span><span class="sxs-lookup"><span data-stu-id="3e162-106">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3e162-107">Ferramenta de teste</span><span class="sxs-lookup"><span data-stu-id="3e162-107">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="3e162-108">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="3e162-108">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3e162-109">Permissões obrigatórias</span><span class="sxs-lookup"><span data-stu-id="3e162-109">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="3e162-110">Ao executar localmente usando o Shell de gerenciamento do Lync Server, os usuários devem ser membros do grupo de segurança RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="3e162-110">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="3e162-111">Quando executado usando uma instância remota do Windows PowerShell, os usuários devem receber uma função RBAC que tenha permissão para executar o cmdlet Test-CsPresence.</span><span class="sxs-lookup"><span data-stu-id="3e162-111">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsPresence cmdlet.</span></span> <span data-ttu-id="3e162-112">Para ver uma lista de todas as funções RBAC que podem usar este cmdlet, execute o seguinte comando no prompt do Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="3e162-112">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsPresence&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="3e162-113">Descrição</span><span class="sxs-lookup"><span data-stu-id="3e162-113">Description</span></span>

<span data-ttu-id="3e162-114">Test-CsPresence é usado para determinar se um par de usuários de teste pode fazer logon no Lync Server e, em seguida, trocar informações de presença.</span><span class="sxs-lookup"><span data-stu-id="3e162-114">Test-CsPresence is used to determine whether a pair of test users can log on to Lync Server and then exchange presence information.</span></span> <span data-ttu-id="3e162-115">Para fazer isso, o cmdlet primeiro faz logon dos dois usuários no sistema.</span><span class="sxs-lookup"><span data-stu-id="3e162-115">To do this, the cmdlet first logs the two users on to the system.</span></span> <span data-ttu-id="3e162-116">Se o logon de ambos tiver êxito, o primeiro usuário de testes solicita o recebimento de informações de presença do segundo usuário.</span><span class="sxs-lookup"><span data-stu-id="3e162-116">If both logons succeed, the first test user then asks to receive presence information from the second user.</span></span> <span data-ttu-id="3e162-117">O segundo usuário publica essas informações, e Test-CsPresence verifica se as informações foram transmitidas com êxito para o primeiro usuário.</span><span class="sxs-lookup"><span data-stu-id="3e162-117">The second user publishes this information, and Test-CsPresence verifies that the information was successfully transmitted to the first user.</span></span> <span data-ttu-id="3e162-118">Após a troca de informações de presença, os dois usuários de teste são então desconectados do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="3e162-118">After the exchange of presence information, the two test users are then logged off from Lync Server.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="3e162-119">Executar o teste</span><span class="sxs-lookup"><span data-stu-id="3e162-119">Running the test</span></span>

<span data-ttu-id="3e162-120">O cmdlet Test-CsPresence pode ser executado usando um par de contas de teste pré-configuradas (Confira Configurando contas de teste para executar testes do Lync Server) ou as contas de dois usuários que estão habilitados para o Lync Server.</span><span class="sxs-lookup"><span data-stu-id="3e162-120">The Test-CsPresence cmdlet can be run using either a pair of preconfigured test accounts (see Setting Up Test Accounts for Running Lync Server Tests) or the accounts of any two users who are enabled for Lync Server.</span></span> <span data-ttu-id="3e162-121">Para executar essa verificação usando contas de teste, basta especificar o FQDN do pool do Lync Server que está sendo testado.</span><span class="sxs-lookup"><span data-stu-id="3e162-121">To run this check using test accounts, you just have to specify the FQDN of the Lync Server pool being tested.</span></span> <span data-ttu-id="3e162-122">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="3e162-122">For example:</span></span>

    Test-CsPresence -TargetFqdn "atl-cs-001.litwareinc.com"

<span data-ttu-id="3e162-123">Para executar essa verificação usando contas de usuário reais, você deve criar dois objetos de credenciais do Windows PowerShell (objetos que contêm o nome da conta e a senha) para cada conta.</span><span class="sxs-lookup"><span data-stu-id="3e162-123">To run this check using actual user accounts, you must create two Windows PowerShell credentials objects (objects that contain the account name and password) for each account.</span></span> <span data-ttu-id="3e162-124">Em seguida, você deve incluir esses objetos de credenciais e os endereços SIP das duas contas ao chamar Test-CsPresence:</span><span class="sxs-lookup"><span data-stu-id="3e162-124">You must then include those credentials objects and the SIP addresses of the two accounts when you call Test-CsPresence:</span></span>

    $credential1 = Get-Credential "litwareinc\kenmyer"
    $credential2 = Get-Credential "litwareinc\davidlongmire"
    Test-CsPresence -TargetFqdn "atl-cs-001.litwareinc.com" -PublisherSipAddress "sip:kenmyer@litwareinc.com" -PublisherCredential $credential1 -SubscriberSipAddress "sip:davidlongmire@litwareinc.com" -SubscriberCredential $credential2

<span data-ttu-id="3e162-125">Para obter mais informações, consulte a documentação de ajuda para o cmdlet [Test-CsPresence](https://docs.microsoft.com/powershell/module/skype/Test-CsPresence) .</span><span class="sxs-lookup"><span data-stu-id="3e162-125">For more information, see the Help documentation for the [Test-CsPresence](https://docs.microsoft.com/powershell/module/skype/Test-CsPresence) cmdlet.</span></span>

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="3e162-126">Determinando o sucesso ou a falha</span><span class="sxs-lookup"><span data-stu-id="3e162-126">Determining success or failure</span></span>

<span data-ttu-id="3e162-127">Se os usuários especificados puderem trocar informações de presença, você receberá uma saída semelhante a esta, com a propriedade Result marcada como **êxito:**</span><span class="sxs-lookup"><span data-stu-id="3e162-127">If the specified users can exchange presence information, then you'll receive output similar to this, with the Result property marked as **Success:**</span></span>

<span data-ttu-id="3e162-128">TargetFqdn: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="3e162-128">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="3e162-129">Resultado: êxito</span><span class="sxs-lookup"><span data-stu-id="3e162-129">Result : Success</span></span>

<span data-ttu-id="3e162-130">Latência: 00:00:06.3280315</span><span class="sxs-lookup"><span data-stu-id="3e162-130">Latency : 00:00:06.3280315</span></span>

<span data-ttu-id="3e162-131">Erros</span><span class="sxs-lookup"><span data-stu-id="3e162-131">Error :</span></span>

<span data-ttu-id="3e162-132">Diagnóstico</span><span class="sxs-lookup"><span data-stu-id="3e162-132">Diagnosis :</span></span>

<span data-ttu-id="3e162-133">Se os dois usuários não puderem trocar informações de presença, o resultado será mostrado como falha, e informações adicionais serão registradas nas propriedades de erro e diagnóstico:</span><span class="sxs-lookup"><span data-stu-id="3e162-133">If the two users can't exchange presence information, then the Result will be shown as Failure, and additional information will be recorded in the Error and Diagnosis properties:</span></span>

<span data-ttu-id="3e162-134">TargetFqdn: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="3e162-134">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="3e162-135">Resultado: falha</span><span class="sxs-lookup"><span data-stu-id="3e162-135">Result : Failure</span></span>

<span data-ttu-id="3e162-136">Latência: 00:00:00</span><span class="sxs-lookup"><span data-stu-id="3e162-136">Latency : 00:00:00</span></span>

<span data-ttu-id="3e162-137">Erro: 404, não encontrado</span><span class="sxs-lookup"><span data-stu-id="3e162-137">Error : 404, Not Found</span></span>

<span data-ttu-id="3e162-138">Diagnóstico: ErrorCode = 4005, Source = ATL-cs-001.litwareinc.com,</span><span class="sxs-lookup"><span data-stu-id="3e162-138">Diagnosis : ErrorCode=4005,Source=atl-cs-001.litwareinc.com,</span></span>

<span data-ttu-id="3e162-139">Razão = o URI de destino não está habilitado para SIP ou não</span><span class="sxs-lookup"><span data-stu-id="3e162-139">Reason=Destination URI either not enabled for SIP or does not</span></span>

<span data-ttu-id="3e162-140">existente.</span><span class="sxs-lookup"><span data-stu-id="3e162-140">exist.</span></span>

<span data-ttu-id="3e162-141">Microsoft. RTC. Signaling. DiagnosticHeader</span><span class="sxs-lookup"><span data-stu-id="3e162-141">Microsoft.Rtc.Signaling.DiagnosticHeader</span></span>

<span data-ttu-id="3e162-142">Por exemplo, a saída anterior diz que o teste falhou porque pelo menos uma das duas contas de usuário não é válida: a conta não existe ou não foi habilitada para o Lync Server.</span><span class="sxs-lookup"><span data-stu-id="3e162-142">For example, the previous output states that the test failed because at least one of the two user accounts is not valid: either the account does not exist or it has not been enabled for Lync Server.</span></span> <span data-ttu-id="3e162-143">Você pode verificar se as contas existem e determinar se elas estão habilitadas para o Lync Server, executando um comando semelhante a este:</span><span class="sxs-lookup"><span data-stu-id="3e162-143">You can verify that the accounts exist, and determine whether they are enabled for Lync Server, by running a command similar to this:</span></span>

    "sip:kenmyer@litwareinc.com", "sip:davidlongmire@litwareinc.com" | Get-CsUser | Select-Object SipAddress, Enabled

<span data-ttu-id="3e162-144">Se Test-CsPresence falhar, talvez você queira executar novamente o teste, desta vez, incluindo o parâmetro Verbose:</span><span class="sxs-lookup"><span data-stu-id="3e162-144">If Test-CsPresence fails, then you might want to rerun the test, this time including the Verbose parameter:</span></span>

    Test-CsPresence -TargetFqdn "atl-cs-001.litwareinc.com" -Verbose

<span data-ttu-id="3e162-145">Quando o parâmetro Verbose é incluído, Test-CsPresence retornará uma conta passo a passo de cada ação que tentou quando verificou a capacidade do usuário especificado fazer logon no Lync Server.</span><span class="sxs-lookup"><span data-stu-id="3e162-145">When the Verbose parameter is included, Test-CsPresence will return a step-by-step account of each action it tried when it checked the ability of the specified user to log on to Lync Server.</span></span> <span data-ttu-id="3e162-146">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="3e162-146">For example:</span></span>

<span data-ttu-id="3e162-147">Acerto de solicitação de registro contra desconhecido</span><span class="sxs-lookup"><span data-stu-id="3e162-147">Registration Request hit against Unknown</span></span>

<span data-ttu-id="3e162-148">Atividade ' Register ' concluída em ' 0, 345791 ' segundos.</span><span class="sxs-lookup"><span data-stu-id="3e162-148">'Register' activity completed in '0.0345791' secs.</span></span>

<span data-ttu-id="3e162-149">Atividade ' SelfSubscribeActivity ' iniciada.</span><span class="sxs-lookup"><span data-stu-id="3e162-149">'SelfSubscribeActivity' activity started.</span></span>

<span data-ttu-id="3e162-150">Atividade ' SelfSubscribeActivity ' concluída em ' 0, 41174 ' segundos.</span><span class="sxs-lookup"><span data-stu-id="3e162-150">'SelfSubscribeActivity' activity completed in '0.0041174' secs.</span></span>

<span data-ttu-id="3e162-151">Atividade ' SubscribePresence ' iniciada.</span><span class="sxs-lookup"><span data-stu-id="3e162-151">'SubscribePresence' activity started.</span></span>

<span data-ttu-id="3e162-152">Atividade ' SubscribePresence ' concluída em ' 0, 38764 ' segundos.</span><span class="sxs-lookup"><span data-stu-id="3e162-152">'SubscribePresence' activity completed in '0.0038764' secs.</span></span>

<span data-ttu-id="3e162-153">Atividade ' PublishPresence ' iniciada.</span><span class="sxs-lookup"><span data-stu-id="3e162-153">'PublishPresence' activity started.</span></span>

<span data-ttu-id="3e162-154">Uma exceção uma notificação de presença não é recebida em 25 segundos.</span><span class="sxs-lookup"><span data-stu-id="3e162-154">An exception 'Presence notification is not received within 25 secs.'</span></span> <span data-ttu-id="3e162-155">ocorreu uma execução do fluxo de trabalho ruing Microsoft. RTC. SyntheticTransactions. workflows. STPresenceWorkflow.</span><span class="sxs-lookup"><span data-stu-id="3e162-155">occurred ruing Workflow Microsoft.Rtc.SyntheticTransactions.Workflows.STPresenceWorkflow execution.</span></span>

<span data-ttu-id="3e162-156">O fato de que a notificação de presença não foi recebida em 25 segundos pode indicar que os problemas de rede estão impedindo que as informações sejam trocadas.</span><span class="sxs-lookup"><span data-stu-id="3e162-156">The fact that the presence notification was not received within 25 seconds might indicate that network issues are preventing information from being exchanged.</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="3e162-157">Motivos pelos quais o teste pode ter falhado</span><span class="sxs-lookup"><span data-stu-id="3e162-157">Reasons why the test might have failed</span></span>

<span data-ttu-id="3e162-158">Aqui estão alguns motivos comuns para que Test-CsPresence possa falhar:</span><span class="sxs-lookup"><span data-stu-id="3e162-158">Here are some common reasons why Test-CsPresence might fail:</span></span>

  - <span data-ttu-id="3e162-159">Você especificou uma conta de usuário incorreta.</span><span class="sxs-lookup"><span data-stu-id="3e162-159">You specified an incorrect user account.</span></span> <span data-ttu-id="3e162-160">Você pode verificar se uma conta de usuário existe executando um comando semelhante a este:</span><span class="sxs-lookup"><span data-stu-id="3e162-160">You can verify that a user account exists by running a command similar to this:</span></span>
    
        Get-CsUser "sip:kenmyer@litwareinc.com"

  - <span data-ttu-id="3e162-161">A conta de usuário é válida, mas a conta não está habilitada no momento para o Lync Server.</span><span class="sxs-lookup"><span data-stu-id="3e162-161">The user account is valid, but the account is currently not enabled for Lync Server.</span></span> <span data-ttu-id="3e162-162">Para verificar se uma conta de usuário está habilitada para o Lync Server, execute um comando semelhante ao seguinte:</span><span class="sxs-lookup"><span data-stu-id="3e162-162">To verify that a user account is enabled for Lync Server, run a command similar to the following:</span></span>
    
        Get-CsUser "sip:kenmyer@litwareinc.com" | Select-Object Enabled
    
    <span data-ttu-id="3e162-163">Se a propriedade Enabled estiver definida como false, isso significa que o usuário não está habilitado para o Lync Server no momento.</span><span class="sxs-lookup"><span data-stu-id="3e162-163">If the Enabled property is set to False that means that the user is currently not enabled for Lync Server.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

