---
title: 'Lync Server 2013: testar a publicação de presença do usuário e inscrever-se'
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
ms.openlocfilehash: b76cd47ccfe35cecf7b7e9182aeadccc37436bc5
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42141197"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="testing-user-presence-publishing-and-subscribing-in-lync-server-2013"></a><span data-ttu-id="b3d5a-102">Testar a publicação de presença do usuário e inscrever-se no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b3d5a-102">Testing user presence publishing and subscribing in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b3d5a-103">_**Última modificação do tópico:** 2014-06-05_</span><span class="sxs-lookup"><span data-stu-id="b3d5a-103">_**Topic Last Modified:** 2014-06-05_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b3d5a-104">Agenda de verificação</span><span class="sxs-lookup"><span data-stu-id="b3d5a-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="b3d5a-105">Diariamente</span><span class="sxs-lookup"><span data-stu-id="b3d5a-105">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b3d5a-106">Ferramenta de teste</span><span class="sxs-lookup"><span data-stu-id="b3d5a-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="b3d5a-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="b3d5a-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b3d5a-108">Permissões obrigatórias</span><span class="sxs-lookup"><span data-stu-id="b3d5a-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="b3d5a-109">Ao executar localmente usando o Shell de gerenciamento do Lync Server, os usuários devem ser membros do grupo de segurança RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="b3d5a-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="b3d5a-110">Quando executado usando uma instância remota do Windows PowerShell, os usuários devem receber uma função RBAC que tenha permissão para executar o cmdlet Test-CsPresence.</span><span class="sxs-lookup"><span data-stu-id="b3d5a-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsPresence cmdlet.</span></span> <span data-ttu-id="b3d5a-111">Para ver uma lista de todas as funções RBAC que podem usar este cmdlet, execute o seguinte comando no prompt do Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="b3d5a-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsPresence&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="b3d5a-112">Descrição</span><span class="sxs-lookup"><span data-stu-id="b3d5a-112">Description</span></span>

<span data-ttu-id="b3d5a-113">Test-CsPresence é usado para determinar se um par de usuários de teste pode fazer logon no Lync Server e, em seguida, trocar informações de presença.</span><span class="sxs-lookup"><span data-stu-id="b3d5a-113">Test-CsPresence is used to determine whether a pair of test users can log on to Lync Server and then exchange presence information.</span></span> <span data-ttu-id="b3d5a-114">Para fazer isso, o cmdlet primeiro faz logon dos dois usuários no sistema.</span><span class="sxs-lookup"><span data-stu-id="b3d5a-114">To do this, the cmdlet first logs the two users on to the system.</span></span> <span data-ttu-id="b3d5a-115">Se o logon de ambos tiver êxito, o primeiro usuário de testes solicita o recebimento de informações de presença do segundo usuário.</span><span class="sxs-lookup"><span data-stu-id="b3d5a-115">If both logons succeed, the first test user then asks to receive presence information from the second user.</span></span> <span data-ttu-id="b3d5a-116">O segundo usuário publica essas informações, e Test-CsPresence verifica se as informações foram transmitidas com êxito para o primeiro usuário.</span><span class="sxs-lookup"><span data-stu-id="b3d5a-116">The second user publishes this information, and Test-CsPresence verifies that the information was successfully transmitted to the first user.</span></span> <span data-ttu-id="b3d5a-117">Após a troca de informações de presença, os dois usuários de teste são então desconectados do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="b3d5a-117">After the exchange of presence information, the two test users are then logged off from Lync Server.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="b3d5a-118">Executar o teste</span><span class="sxs-lookup"><span data-stu-id="b3d5a-118">Running the test</span></span>

<span data-ttu-id="b3d5a-119">O cmdlet Test-CsPresence pode ser executado usando um par de contas de teste pré-configuradas (consulte Configurando contas de teste para executar testes do Lync Server) ou as contas de dois usuários que estão habilitados para o Lync Server.</span><span class="sxs-lookup"><span data-stu-id="b3d5a-119">The Test-CsPresence cmdlet can be run using either a pair of preconfigured test accounts (see Setting Up Test Accounts for Running Lync Server Tests) or the accounts of any two users who are enabled for Lync Server.</span></span> <span data-ttu-id="b3d5a-120">Para executar essa verificação usando contas de teste, basta especificar o FQDN do pool do Lync Server que está sendo testado.</span><span class="sxs-lookup"><span data-stu-id="b3d5a-120">To run this check using test accounts, you just have to specify the FQDN of the Lync Server pool being tested.</span></span> <span data-ttu-id="b3d5a-121">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="b3d5a-121">For example:</span></span>

    Test-CsPresence -TargetFqdn "atl-cs-001.litwareinc.com"

<span data-ttu-id="b3d5a-122">Para executar essa verificação usando contas de usuário reais, você deve criar dois objetos de credenciais do Windows PowerShell (objetos que contêm o nome da conta e a senha) para cada conta.</span><span class="sxs-lookup"><span data-stu-id="b3d5a-122">To run this check using actual user accounts, you must create two Windows PowerShell credentials objects (objects that contain the account name and password) for each account.</span></span> <span data-ttu-id="b3d5a-123">Em seguida, você deve incluir esses objetos de credenciais e os endereços SIP das duas contas ao chamar Test-CsPresence:</span><span class="sxs-lookup"><span data-stu-id="b3d5a-123">You must then include those credentials objects and the SIP addresses of the two accounts when you call Test-CsPresence:</span></span>

    $credential1 = Get-Credential "litwareinc\kenmyer"
    $credential2 = Get-Credential "litwareinc\davidlongmire"
    Test-CsPresence -TargetFqdn "atl-cs-001.litwareinc.com" -PublisherSipAddress "sip:kenmyer@litwareinc.com" -PublisherCredential $credential1 -SubscriberSipAddress "sip:davidlongmire@litwareinc.com" -SubscriberCredential $credential2

<span data-ttu-id="b3d5a-124">Para obter mais informações, consulte a documentação de ajuda para o cmdlet [Test-CsPresence](https://docs.microsoft.com/powershell/module/skype/Test-CsPresence) .</span><span class="sxs-lookup"><span data-stu-id="b3d5a-124">For more information, see the Help documentation for the [Test-CsPresence](https://docs.microsoft.com/powershell/module/skype/Test-CsPresence) cmdlet.</span></span>

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="b3d5a-125">Determinando o sucesso ou a falha</span><span class="sxs-lookup"><span data-stu-id="b3d5a-125">Determining success or failure</span></span>

<span data-ttu-id="b3d5a-126">Se os usuários especificados puderem trocar informações de presença, você receberá uma saída semelhante a esta, com a propriedade Result marcada como **êxito:**</span><span class="sxs-lookup"><span data-stu-id="b3d5a-126">If the specified users can exchange presence information, then you'll receive output similar to this, with the Result property marked as **Success:**</span></span>

<span data-ttu-id="b3d5a-127">TargetFqdn: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="b3d5a-127">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="b3d5a-128">Resultado: êxito</span><span class="sxs-lookup"><span data-stu-id="b3d5a-128">Result : Success</span></span>

<span data-ttu-id="b3d5a-129">Latência: 00:00:06.3280315</span><span class="sxs-lookup"><span data-stu-id="b3d5a-129">Latency : 00:00:06.3280315</span></span>

<span data-ttu-id="b3d5a-130">Erros</span><span class="sxs-lookup"><span data-stu-id="b3d5a-130">Error :</span></span>

<span data-ttu-id="b3d5a-131">Diagnóstico</span><span class="sxs-lookup"><span data-stu-id="b3d5a-131">Diagnosis :</span></span>

<span data-ttu-id="b3d5a-132">Se os dois usuários não puderem trocar informações de presença, o resultado será mostrado como falha, e informações adicionais serão registradas nas propriedades de erro e diagnóstico:</span><span class="sxs-lookup"><span data-stu-id="b3d5a-132">If the two users can't exchange presence information, then the Result will be shown as Failure, and additional information will be recorded in the Error and Diagnosis properties:</span></span>

<span data-ttu-id="b3d5a-133">TargetFqdn: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="b3d5a-133">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="b3d5a-134">Resultado: falha</span><span class="sxs-lookup"><span data-stu-id="b3d5a-134">Result : Failure</span></span>

<span data-ttu-id="b3d5a-135">Latência: 00:00:00</span><span class="sxs-lookup"><span data-stu-id="b3d5a-135">Latency : 00:00:00</span></span>

<span data-ttu-id="b3d5a-136">Erro: 404, não encontrado</span><span class="sxs-lookup"><span data-stu-id="b3d5a-136">Error : 404, Not Found</span></span>

<span data-ttu-id="b3d5a-137">Diagnóstico: ErrorCode = 4005, Source = ATL-cs-001.litwareinc.com,</span><span class="sxs-lookup"><span data-stu-id="b3d5a-137">Diagnosis : ErrorCode=4005,Source=atl-cs-001.litwareinc.com,</span></span>

<span data-ttu-id="b3d5a-138">Razão = o URI de destino não está habilitado para SIP ou não</span><span class="sxs-lookup"><span data-stu-id="b3d5a-138">Reason=Destination URI either not enabled for SIP or does not</span></span>

<span data-ttu-id="b3d5a-139">existente.</span><span class="sxs-lookup"><span data-stu-id="b3d5a-139">exist.</span></span>

<span data-ttu-id="b3d5a-140">Microsoft. RTC. Signaling. DiagnosticHeader</span><span class="sxs-lookup"><span data-stu-id="b3d5a-140">Microsoft.Rtc.Signaling.DiagnosticHeader</span></span>

<span data-ttu-id="b3d5a-141">Por exemplo, a saída anterior diz que o teste falhou porque pelo menos uma das duas contas de usuário não é válida: a conta não existe ou não foi habilitada para o Lync Server.</span><span class="sxs-lookup"><span data-stu-id="b3d5a-141">For example, the previous output states that the test failed because at least one of the two user accounts is not valid: either the account does not exist or it has not been enabled for Lync Server.</span></span> <span data-ttu-id="b3d5a-142">Você pode verificar se as contas existem e determinar se elas estão habilitadas para o Lync Server, executando um comando semelhante a este:</span><span class="sxs-lookup"><span data-stu-id="b3d5a-142">You can verify that the accounts exist, and determine whether they are enabled for Lync Server, by running a command similar to this:</span></span>

    "sip:kenmyer@litwareinc.com", "sip:davidlongmire@litwareinc.com" | Get-CsUser | Select-Object SipAddress, Enabled

<span data-ttu-id="b3d5a-143">Se Test-CsPresence falhar, talvez você queira executar novamente o teste, desta vez, incluindo o parâmetro Verbose:</span><span class="sxs-lookup"><span data-stu-id="b3d5a-143">If Test-CsPresence fails, then you might want to rerun the test, this time including the Verbose parameter:</span></span>

    Test-CsPresence -TargetFqdn "atl-cs-001.litwareinc.com" -Verbose

<span data-ttu-id="b3d5a-144">Quando o parâmetro Verbose é incluído, o Test-CsPresence retornará uma conta passo a passo de cada ação que tentou quando verificou a capacidade do usuário especificado fazer logon no Lync Server.</span><span class="sxs-lookup"><span data-stu-id="b3d5a-144">When the Verbose parameter is included, Test-CsPresence will return a step-by-step account of each action it tried when it checked the ability of the specified user to log on to Lync Server.</span></span> <span data-ttu-id="b3d5a-145">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="b3d5a-145">For example:</span></span>

<span data-ttu-id="b3d5a-146">Acerto de solicitação de registro contra desconhecido</span><span class="sxs-lookup"><span data-stu-id="b3d5a-146">Registration Request hit against Unknown</span></span>

<span data-ttu-id="b3d5a-147">Atividade ' Register ' concluída em ' 0, 345791 ' segundos.</span><span class="sxs-lookup"><span data-stu-id="b3d5a-147">'Register' activity completed in '0.0345791' secs.</span></span>

<span data-ttu-id="b3d5a-148">Atividade ' SelfSubscribeActivity ' iniciada.</span><span class="sxs-lookup"><span data-stu-id="b3d5a-148">'SelfSubscribeActivity' activity started.</span></span>

<span data-ttu-id="b3d5a-149">Atividade ' SelfSubscribeActivity ' concluída em ' 0, 41174 ' segundos.</span><span class="sxs-lookup"><span data-stu-id="b3d5a-149">'SelfSubscribeActivity' activity completed in '0.0041174' secs.</span></span>

<span data-ttu-id="b3d5a-150">Atividade ' SubscribePresence ' iniciada.</span><span class="sxs-lookup"><span data-stu-id="b3d5a-150">'SubscribePresence' activity started.</span></span>

<span data-ttu-id="b3d5a-151">Atividade ' SubscribePresence ' concluída em ' 0, 38764 ' segundos.</span><span class="sxs-lookup"><span data-stu-id="b3d5a-151">'SubscribePresence' activity completed in '0.0038764' secs.</span></span>

<span data-ttu-id="b3d5a-152">Atividade ' PublishPresence ' iniciada.</span><span class="sxs-lookup"><span data-stu-id="b3d5a-152">'PublishPresence' activity started.</span></span>

<span data-ttu-id="b3d5a-153">Uma exceção uma notificação de presença não é recebida em 25 segundos.</span><span class="sxs-lookup"><span data-stu-id="b3d5a-153">An exception 'Presence notification is not received within 25 secs.'</span></span> <span data-ttu-id="b3d5a-154">ocorreu uma execução do fluxo de trabalho ruing Microsoft. RTC. SyntheticTransactions. workflows. STPresenceWorkflow.</span><span class="sxs-lookup"><span data-stu-id="b3d5a-154">occurred ruing Workflow Microsoft.Rtc.SyntheticTransactions.Workflows.STPresenceWorkflow execution.</span></span>

<span data-ttu-id="b3d5a-155">O fato de que a notificação de presença não foi recebida em 25 segundos pode indicar que os problemas de rede estão impedindo que as informações sejam trocadas.</span><span class="sxs-lookup"><span data-stu-id="b3d5a-155">The fact that the presence notification was not received within 25 seconds might indicate that network issues are preventing information from being exchanged.</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="b3d5a-156">Motivos pelos quais o teste pode ter falhado</span><span class="sxs-lookup"><span data-stu-id="b3d5a-156">Reasons why the test might have failed</span></span>

<span data-ttu-id="b3d5a-157">Aqui estão alguns motivos comuns pelos quais Test-CsPresence pode falhar:</span><span class="sxs-lookup"><span data-stu-id="b3d5a-157">Here are some common reasons why Test-CsPresence might fail:</span></span>

  - <span data-ttu-id="b3d5a-158">Você especificou uma conta de usuário incorreta.</span><span class="sxs-lookup"><span data-stu-id="b3d5a-158">You specified an incorrect user account.</span></span> <span data-ttu-id="b3d5a-159">Você pode verificar se uma conta de usuário existe executando um comando semelhante a este:</span><span class="sxs-lookup"><span data-stu-id="b3d5a-159">You can verify that a user account exists by running a command similar to this:</span></span>
    
        Get-CsUser "sip:kenmyer@litwareinc.com"

  - <span data-ttu-id="b3d5a-160">A conta de usuário é válida, mas a conta não está habilitada no momento para o Lync Server.</span><span class="sxs-lookup"><span data-stu-id="b3d5a-160">The user account is valid, but the account is currently not enabled for Lync Server.</span></span> <span data-ttu-id="b3d5a-161">Para verificar se uma conta de usuário está habilitada para o Lync Server, execute um comando semelhante ao seguinte:</span><span class="sxs-lookup"><span data-stu-id="b3d5a-161">To verify that a user account is enabled for Lync Server, run a command similar to the following:</span></span>
    
        Get-CsUser "sip:kenmyer@litwareinc.com" | Select-Object Enabled
    
    <span data-ttu-id="b3d5a-162">Se a propriedade Enabled estiver definida como false, isso significa que o usuário não está habilitado para o Lync Server no momento.</span><span class="sxs-lookup"><span data-stu-id="b3d5a-162">If the Enabled property is set to False that means that the user is currently not enabled for Lync Server.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

