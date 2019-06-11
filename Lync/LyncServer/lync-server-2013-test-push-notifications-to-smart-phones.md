---
title: 'Lync Server 2013: testar notificações por push em telefones inteligentes'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Test push notifications to smart phones
ms:assetid: 8f5ca7d1-1ccb-4cb0-b417-730559e79b6e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn767948(v=OCS.15)
ms:contentKeyID: 63969626
ms.date: 03/15/2017
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3a0d58c79fcd66229ffda43fa60ab99cedc308ab
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34844699"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="test-push-notifications-to-smart-phones-in-lync-server-2013"></a><span data-ttu-id="1b9b1-102">Testar notificações por push em Smart Phones no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1b9b1-102">Test push notifications to smart phones in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1b9b1-103">_**Tópico da última modificação:** 2017-03-15_</span><span class="sxs-lookup"><span data-stu-id="1b9b1-103">_**Topic Last Modified:** 2017-03-15_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="1b9b1-104">Cronograma de verificação</span><span class="sxs-lookup"><span data-stu-id="1b9b1-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="1b9b1-105">Mensal</span><span class="sxs-lookup"><span data-stu-id="1b9b1-105">Monthly</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1b9b1-106">Ferramenta de teste</span><span class="sxs-lookup"><span data-stu-id="1b9b1-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="1b9b1-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="1b9b1-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1b9b1-108">Permissões necessárias</span><span class="sxs-lookup"><span data-stu-id="1b9b1-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="1b9b1-109">Quando executado localmente usando o Shell de gerenciamento do Lync Server, os usuários devem ser membros do grupo de segurança RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="1b9b1-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="1b9b1-110">Quando executado usando uma instância remota do Windows PowerShell, os usuários devem receber uma função RBAC que tenha permissão para executar o cmdlet Test-CsMcxPushNotification.</span><span class="sxs-lookup"><span data-stu-id="1b9b1-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsMcxPushNotification cmdlet.</span></span> <span data-ttu-id="1b9b1-111">Para ver uma lista de todas as funções RBAC que podem usar esse cmdlet, execute o seguinte comando no prompt do Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="1b9b1-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsMcxPushNotification&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="1b9b1-112">Descrição</span><span class="sxs-lookup"><span data-stu-id="1b9b1-112">Description</span></span>

<span data-ttu-id="1b9b1-113">O serviço de notificação por push (serviço de notificação por push da Apple e o Microsoft Push Notification Service) pode enviar notificações sobre eventos como novas mensagens instantâneas ou nova caixa postal para dispositivos móveis, como iPhones e telefones Windows, mesmo que o cliente do Lync nesses dispositivos, no momento, está suspenso ou em execução em segundo plano.</span><span class="sxs-lookup"><span data-stu-id="1b9b1-113">The push notification service (Apple Push Notification Service and Microsoft Push Notification Service) can send notifications about events such as new instant messages or new voice mail to mobile devices such as iPhones and Windows Phones, even if the Lync client on those devices is currently suspended or running in the background.</span></span> <span data-ttu-id="1b9b1-114">O serviço de notificação por push é um serviço baseado em nuvem que é executado em servidores da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="1b9b1-114">The push notification service is a cloud-based service that is running on Microsoft servers.</span></span> <span data-ttu-id="1b9b1-115">Para aproveitar as notificações por push, você deve ser capaz de se conectar e ser autenticado por meio de uma notificação por push.</span><span class="sxs-lookup"><span data-stu-id="1b9b1-115">In order to take advantage of push notifications, you must be able to connect to, and be authenticated by, the push notification clearinghouse.</span></span> <span data-ttu-id="1b9b1-116">O cmdlet Test-CsMcxPushNotification permite que os administradores verifiquem se as solicitações de notificação por push podem ser roteadas pelo servidor de borda para a Clearinghouse de notificação por push.</span><span class="sxs-lookup"><span data-stu-id="1b9b1-116">The Test-CsMcxPushNotification cmdlet enables administrators to verify that push notification requests can be routed through your Edge server to the push notification clearinghouse.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="1b9b1-117">Executar o teste</span><span class="sxs-lookup"><span data-stu-id="1b9b1-117">Running the test</span></span>

<span data-ttu-id="1b9b1-118">Para testar o serviço de notificação por push, chame o cmdlet Test-CsMcxPushNotification.</span><span class="sxs-lookup"><span data-stu-id="1b9b1-118">To test the push notification service, call the Test-CsMcxPushNotification cmdlet.</span></span> <span data-ttu-id="1b9b1-119">Certifique-se de especificar o nome de domínio totalmente qualificado do seu servidor de borda:</span><span class="sxs-lookup"><span data-stu-id="1b9b1-119">Make sure that you specify the fully qualified domain name of your Edge server:</span></span>

    Test-CsMcxPushNotification -AccessEdgeFqdn "atl-edge-001.litwareinc.com"

<span data-ttu-id="1b9b1-120">Para obter mais informações, consulte o tópico da ajuda para o cmdlet [Test-CsMcxPushNotification](https://docs.microsoft.com/powershell/module/skype/Test-CsMcxPushNotification) .</span><span class="sxs-lookup"><span data-stu-id="1b9b1-120">For more information, see the help topic for the [Test-CsMcxPushNotification](https://docs.microsoft.com/powershell/module/skype/Test-CsMcxPushNotification) cmdlet.</span></span>

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="1b9b1-121">Determinação do sucesso ou falha</span><span class="sxs-lookup"><span data-stu-id="1b9b1-121">Determining success or failure</span></span>

<span data-ttu-id="1b9b1-122">Se Test-CsMcxPushNotification tiver êxito, o cmdlet retornará o resultado do teste Success:</span><span class="sxs-lookup"><span data-stu-id="1b9b1-122">If Test-CsMcxPushNotification succeeds the cmdlet will return the test result Success:</span></span>

<span data-ttu-id="1b9b1-123">TargetFqdn: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="1b9b1-123">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="1b9b1-124">Resultado: êxito</span><span class="sxs-lookup"><span data-stu-id="1b9b1-124">Result : Success</span></span>

<span data-ttu-id="1b9b1-125">Latência: 00:00:00</span><span class="sxs-lookup"><span data-stu-id="1b9b1-125">Latency : 00:00:00</span></span>

<span data-ttu-id="1b9b1-126">Erros</span><span class="sxs-lookup"><span data-stu-id="1b9b1-126">Error :</span></span>

<span data-ttu-id="1b9b1-127">Correto</span><span class="sxs-lookup"><span data-stu-id="1b9b1-127">Diagnosis :</span></span>

<span data-ttu-id="1b9b1-128">Se Test-CsMcxPushNotification não conseguir se conectar à Clearinghouse de notificação por push, o cmdlet normalmente não retornará um resultado de teste de falha.</span><span class="sxs-lookup"><span data-stu-id="1b9b1-128">If Test-CsMcxPushNotification is unable to connect to the push notification clearinghouse the cmdlet will typically not return a test result of Failure.</span></span> <span data-ttu-id="1b9b1-129">Em vez disso, o comando geralmente será reprovado completamente.</span><span class="sxs-lookup"><span data-stu-id="1b9b1-129">Instead the command will usually fail completely.</span></span> <span data-ttu-id="1b9b1-130">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="1b9b1-130">For example:</span></span>

<span data-ttu-id="1b9b1-131">Test-CsMcxPushNotification: uma resposta do 504 (tempo limite do servidor) foi recebida da rede e a operação falhou.</span><span class="sxs-lookup"><span data-stu-id="1b9b1-131">Test-CsMcxPushNotification : A 504 (Server time-out) response was received from the network and the operation failed.</span></span> <span data-ttu-id="1b9b1-132">Consulte os detalhes da exceção para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="1b9b1-132">See the exception details for more information.</span></span>

<span data-ttu-id="1b9b1-133">Na linha: 1 caractere: 27</span><span class="sxs-lookup"><span data-stu-id="1b9b1-133">At line:1 char:27</span></span>

<span data-ttu-id="1b9b1-134">\+Test-CsMcxPushNotification \< \< \< \< -AccessEdgeFqdn lyncedge.mydomain.com</span><span class="sxs-lookup"><span data-stu-id="1b9b1-134">\+ Test-CsMcxPushNotification \<\<\<\< -AccessEdgeFqdn lyncedge.mydomain.com</span></span>

<span data-ttu-id="1b9b1-135">\+CategoryInfo: OperationStopped: (:) \[Test-CsMcxPushNotification\], FailureResponseException</span><span class="sxs-lookup"><span data-stu-id="1b9b1-135">\+ CategoryInfo : OperationStopped: (:) \[Test-CsMcxPushNotification\], FailureResponseException</span></span>

<span data-ttu-id="1b9b1-136">\+FullyQualifiedErrorId: WorkflowNotCompleted, Microsoft. RTC. Management. SyntheticTransactions. TestMcxPushNotificationCmdlet</span><span class="sxs-lookup"><span data-stu-id="1b9b1-136">\+ FullyQualifiedErrorId : WorkflowNotCompleted,Microsoft.Rtc.Management.SyntheticTransactions.TestMcxPushNotificationCmdlet</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="1b9b1-137">Motivos pelos quais o teste pode ter falhado</span><span class="sxs-lookup"><span data-stu-id="1b9b1-137">Reasons why the test might have failed</span></span>

<span data-ttu-id="1b9b1-138">Se o serviço de notificação por push falhar, geralmente indica problemas de comunicação com o servidor de borda ou problemas de comunicação com a casa de compensação da notificação por push.</span><span class="sxs-lookup"><span data-stu-id="1b9b1-138">If the push notification service fails that usually indicates either problems communicating with your Edge server, or problems communicating with the Push Notification Clearing House.</span></span> <span data-ttu-id="1b9b1-139">Se você tiver problemas ao executar Test-CsMcxPushNotification, a primeira coisa que você deve fazer é verificar se o servidor de borda está funcionando corretamente.</span><span class="sxs-lookup"><span data-stu-id="1b9b1-139">If you encounter problems when you run Test-CsMcxPushNotification, the first thing that you should do is verify that your Edge server is working correctly.</span></span> <span data-ttu-id="1b9b1-140">Uma maneira de fazer isso é usar o cmdlet Test-CsAVEdgeConnectivity:</span><span class="sxs-lookup"><span data-stu-id="1b9b1-140">One way to do that is to use the Test-CsAVEdgeConnectivity cmdlet:</span></span>

    $credential = Get-Credential "litwareinc\kenmyer"
    
    Test-CsAVEdgeConnectivity -TargetFqdn "atl-cs-001.litwareinc.com" -UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential

<span data-ttu-id="1b9b1-141">Essa verificação verifica se um usuário especificado pode se conectar ao servidor de borda.</span><span class="sxs-lookup"><span data-stu-id="1b9b1-141">This check verifies that a specified user can connect to the Edge server.</span></span>

<span data-ttu-id="1b9b1-142">Se o servidor de borda parecer estar funcionando corretamente, isso geralmente significa que você não consegue se conectar à Clearinghouse de notificação por push.</span><span class="sxs-lookup"><span data-stu-id="1b9b1-142">If the Edge server seems to be working correctly, that often means that you are unable to connect to the push notification clearinghouse.</span></span> <span data-ttu-id="1b9b1-143">Geralmente, isso significa que você não configurou o URI da compensação corretamente ou que você não tem um registro SRV DNS que aponta para esta URL.</span><span class="sxs-lookup"><span data-stu-id="1b9b1-143">In turn, that typically means that you either have not configured the clearinghouse URI correctly or that you do not have a DNS SRV record that points to this URL.</span></span> <span data-ttu-id="1b9b1-144">Você pode verificar se o URI está definido com o valor correto (sip:push@push.lync.com) executando este comando:</span><span class="sxs-lookup"><span data-stu-id="1b9b1-144">You can verify that the URI is set to the correct value (sip:push@push.lync.com) by running this command:</span></span>

    Get-CsMcxConfiguration

<span data-ttu-id="1b9b1-145">Se a propriedade PushNotificationProxyUri estiver definida como algo diferente de sip:push@push.lync.com, você poderá corrigir esse problema usando o cmdlet Set-McxConfiguration.</span><span class="sxs-lookup"><span data-stu-id="1b9b1-145">If the PushNotificationProxyUri property is set to anything other than sip:push@push.lync.com then you can correct that problem by using the Set-McxConfiguration cmdlet.</span></span> <span data-ttu-id="1b9b1-146">Por exemplo, este comando define corretamente o URI em toda a sua organização:</span><span class="sxs-lookup"><span data-stu-id="1b9b1-146">For example, this command correctly sets the URI throughout your organization:</span></span>

    Get-CsMcxConfiguration | Set-CsMcxConfiguration -PushNotificationProxyUri "sip:push@push.lync.com"

<span data-ttu-id="1b9b1-147">Para obter mais informações, consulte o tópico da ajuda para o cmdlet [set-CsMcxConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsMcxConfiguration) .</span><span class="sxs-lookup"><span data-stu-id="1b9b1-147">For more information, see the help topic for the [Set-CsMcxConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsMcxConfiguration) cmdlet.</span></span>

<span data-ttu-id="1b9b1-148">Se o URI estiver configurado corretamente, seu próximo passo deve ser verificar se você tem um registro SRV DNS que é resolvido para o seu domínio SIP e para o seu servidor de borda.</span><span class="sxs-lookup"><span data-stu-id="1b9b1-148">If the URI is configured correctly, your next step should be to verify that you have a DNS SRV record that resolves to your SIP domain and your Edge server.</span></span> <span data-ttu-id="1b9b1-149">Para obter mais informações sobre como configurar esses registros, consulte o tópico da ajuda requisitos de DNS para mobilidade.</span><span class="sxs-lookup"><span data-stu-id="1b9b1-149">For more information about how to configure these records, see the help topic DNS Requirements for Mobility.</span></span> <span data-ttu-id="1b9b1-150">Observe que a seguinte mensagem de erro geralmente indica um problema com os registros de DNS:</span><span class="sxs-lookup"><span data-stu-id="1b9b1-150">Note that the following error message usually indicates a problem with DNS records:</span></span>

<span data-ttu-id="1b9b1-151">Uma resposta do 504 (tempo limite do servidor) foi recebida da rede e a operação falhou.</span><span class="sxs-lookup"><span data-stu-id="1b9b1-151">A 504 (Server time-out) response was received from the network and the operation failed.</span></span> <span data-ttu-id="1b9b1-152">Consulte os detalhes da exceção para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="1b9b1-152">See the exception details for more information.</span></span>

<span data-ttu-id="1b9b1-153">Também é possível que Test-CsMcxConfiguration falhe com esta mensagem de erro:</span><span class="sxs-lookup"><span data-stu-id="1b9b1-153">It’s also possible that Test-CsMcxConfiguration will fail with this error message:</span></span>

<span data-ttu-id="1b9b1-154">Test-CsMcxPushNotification: solicitação de notificação por push recusada.</span><span class="sxs-lookup"><span data-stu-id="1b9b1-154">Test-CsMcxPushNotification : Push Notification request was rejected.</span></span>

<span data-ttu-id="1b9b1-155">Na linha: 1 caractere: 27</span><span class="sxs-lookup"><span data-stu-id="1b9b1-155">At line:1 char:27</span></span>

<span data-ttu-id="1b9b1-156">\+Test-CsMcxPushNotification\<\<\<\<</span><span class="sxs-lookup"><span data-stu-id="1b9b1-156">\+ Test-CsMcxPushNotification \<\<\<\<</span></span>

<span data-ttu-id="1b9b1-157">\+CategoryInfo: OperationStopped: (:) \[Test-CsMcxPushNotification\], SyntheticTransactionException</span><span class="sxs-lookup"><span data-stu-id="1b9b1-157">\+ CategoryInfo : OperationStopped: (:) \[Test-CsMcxPushNotification\], SyntheticTransactionException</span></span>

<span data-ttu-id="1b9b1-158">\+FullyQualifiedErrorId: WorkflowNotCompleted, Microsoft. RTC. Management. SyntheticTransactions. TestMcxPushNotificationCmdlet</span><span class="sxs-lookup"><span data-stu-id="1b9b1-158">\+ FullyQualifiedErrorId : WorkflowNotCompleted,Microsoft.Rtc.Management.SyntheticTransactions.TestMcxPushNotificationCmdlet</span></span>

<span data-ttu-id="1b9b1-159">A mensagem "solicitação de notificação por push recusada" geralmente ocorre se você habilitou a filtragem de URL e está bloqueando os prefixos http: e https:.</span><span class="sxs-lookup"><span data-stu-id="1b9b1-159">The “Push notification request was rejected” message typically occurs if you have enabled URL filtering and are blocking the http: and https: prefixes.</span></span> <span data-ttu-id="1b9b1-160">Você pode determinar quais prefixos estão sendo bloqueados usando um comando semelhante ao seguinte:</span><span class="sxs-lookup"><span data-stu-id="1b9b1-160">You can determine which prefixes are being blocked by using a command similar to the following:</span></span>

``` 
 (Get-CsImFilterConfiguration -Identity Global).Prefixes
```

<span data-ttu-id="1b9b1-161">Se http: ou https: aparecer nos resultados, você deve removê-los da lista de prefixos bloqueados para que as notificações por push funcionem.</span><span class="sxs-lookup"><span data-stu-id="1b9b1-161">If http: or https: appear in the results, you must remove them from the blocked prefix list for push notifications to work.</span></span> <span data-ttu-id="1b9b1-162">Isso pode ser feito usando comandos semelhantes aos seguintes:</span><span class="sxs-lookup"><span data-stu-id="1b9b1-162">That can be done by using commands similar to these:</span></span>

    Set-CsImFilterConfiguration -Identity site:Redmond -Prefixes @{remove="http:"}
    Set-CsImFilterConfiguration -Identity site:Redmond -Prefixes @{remove="https:"}

<span data-ttu-id="1b9b1-163">Para obter mais informações, consulte o tópico da ajuda para o cmdlet [set-CsImFilterConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsImFilterConfiguration).</span><span class="sxs-lookup"><span data-stu-id="1b9b1-163">For more information, see the help topic for the [Set-CsImFilterConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsImFilterConfiguration)cmdlet.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

