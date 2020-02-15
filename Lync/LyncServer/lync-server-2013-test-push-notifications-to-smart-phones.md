---
title: 'Lync Server 2013: testar notificações por push para telefones inteligentes'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Test push notifications to smart phones
ms:assetid: 8f5ca7d1-1ccb-4cb0-b417-730559e79b6e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn767948(v=OCS.15)
ms:contentKeyID: 63969626
ms.date: 03/15/2017
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 858c1ad3ad5776453a4a48505672c69083de1cc2
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42021212"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="test-push-notifications-to-smart-phones-in-lync-server-2013"></a><span data-ttu-id="ae8b0-102">Testar notificações por push para telefones inteligentes no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ae8b0-102">Test push notifications to smart phones in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ae8b0-103">_**Última modificação do tópico:** 2017-03-15_</span><span class="sxs-lookup"><span data-stu-id="ae8b0-103">_**Topic Last Modified:** 2017-03-15_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ae8b0-104">Agenda de verificação</span><span class="sxs-lookup"><span data-stu-id="ae8b0-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="ae8b0-105">Mensal</span><span class="sxs-lookup"><span data-stu-id="ae8b0-105">Monthly</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ae8b0-106">Ferramenta de teste</span><span class="sxs-lookup"><span data-stu-id="ae8b0-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="ae8b0-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="ae8b0-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ae8b0-108">Permissões obrigatórias</span><span class="sxs-lookup"><span data-stu-id="ae8b0-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="ae8b0-109">Ao executar localmente usando o Shell de gerenciamento do Lync Server, os usuários devem ser membros do grupo de segurança RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="ae8b0-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="ae8b0-110">Quando executado usando uma instância remota do Windows PowerShell, os usuários devem receber uma função RBAC que tenha permissão para executar o cmdlet Test-CsMcxPushNotification.</span><span class="sxs-lookup"><span data-stu-id="ae8b0-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsMcxPushNotification cmdlet.</span></span> <span data-ttu-id="ae8b0-111">Para ver uma lista de todas as funções RBAC que podem usar este cmdlet, execute o seguinte comando no prompt do Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="ae8b0-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsMcxPushNotification&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="ae8b0-112">Descrição</span><span class="sxs-lookup"><span data-stu-id="ae8b0-112">Description</span></span>

<span data-ttu-id="ae8b0-113">O serviço de notificação por push (Apple Push Notification Service e o serviço de notificação por push da Microsoft) pode enviar notificações sobre eventos como novas mensagens instantâneas ou nova caixa postal para dispositivos móveis, como iPhones e telefones Windows, mesmo que o cliente do Lync nesses dispositivos estão atualmente suspensos ou em execução em segundo plano.</span><span class="sxs-lookup"><span data-stu-id="ae8b0-113">The push notification service (Apple Push Notification Service and Microsoft Push Notification Service) can send notifications about events such as new instant messages or new voice mail to mobile devices such as iPhones and Windows Phones, even if the Lync client on those devices is currently suspended or running in the background.</span></span> <span data-ttu-id="ae8b0-114">O serviço de notificação por push é um serviço baseado em nuvem que é executado em servidores Microsoft.</span><span class="sxs-lookup"><span data-stu-id="ae8b0-114">The push notification service is a cloud-based service that is running on Microsoft servers.</span></span> <span data-ttu-id="ae8b0-115">Para aproveitar as notificações por push, você deve ser capaz de se conectar a e ser autenticado por uma notificação de envio por push.</span><span class="sxs-lookup"><span data-stu-id="ae8b0-115">In order to take advantage of push notifications, you must be able to connect to, and be authenticated by, the push notification clearinghouse.</span></span> <span data-ttu-id="ae8b0-116">O cmdlet Test-CsMcxPushNotification permite que os administradores verifiquem se as solicitações de notificação por push podem ser roteadas pelo servidor de borda para a Clearinghouse de notificação por push.</span><span class="sxs-lookup"><span data-stu-id="ae8b0-116">The Test-CsMcxPushNotification cmdlet enables administrators to verify that push notification requests can be routed through your Edge server to the push notification clearinghouse.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="ae8b0-117">Executar o teste</span><span class="sxs-lookup"><span data-stu-id="ae8b0-117">Running the test</span></span>

<span data-ttu-id="ae8b0-118">Para testar o serviço de notificação por push, chame o cmdlet Test-CsMcxPushNotification.</span><span class="sxs-lookup"><span data-stu-id="ae8b0-118">To test the push notification service, call the Test-CsMcxPushNotification cmdlet.</span></span> <span data-ttu-id="ae8b0-119">Certifique-se de especificar o nome de domínio totalmente qualificado do servidor de borda:</span><span class="sxs-lookup"><span data-stu-id="ae8b0-119">Make sure that you specify the fully qualified domain name of your Edge server:</span></span>

    Test-CsMcxPushNotification -AccessEdgeFqdn "atl-edge-001.litwareinc.com"

<span data-ttu-id="ae8b0-120">Para obter mais informações, consulte o tópico de ajuda para o cmdlet [Test-CsMcxPushNotification](https://docs.microsoft.com/powershell/module/skype/Test-CsMcxPushNotification) .</span><span class="sxs-lookup"><span data-stu-id="ae8b0-120">For more information, see the help topic for the [Test-CsMcxPushNotification](https://docs.microsoft.com/powershell/module/skype/Test-CsMcxPushNotification) cmdlet.</span></span>

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="ae8b0-121">Determinando o sucesso ou a falha</span><span class="sxs-lookup"><span data-stu-id="ae8b0-121">Determining success or failure</span></span>

<span data-ttu-id="ae8b0-122">Se Test-CsMcxPushNotification for bem-sucedido, o cmdlet retornará o resultado de teste bem-sucedido:</span><span class="sxs-lookup"><span data-stu-id="ae8b0-122">If Test-CsMcxPushNotification succeeds the cmdlet will return the test result Success:</span></span>

<span data-ttu-id="ae8b0-123">TargetFqdn: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="ae8b0-123">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="ae8b0-124">Resultado: êxito</span><span class="sxs-lookup"><span data-stu-id="ae8b0-124">Result : Success</span></span>

<span data-ttu-id="ae8b0-125">Latência: 00:00:00</span><span class="sxs-lookup"><span data-stu-id="ae8b0-125">Latency : 00:00:00</span></span>

<span data-ttu-id="ae8b0-126">Erros</span><span class="sxs-lookup"><span data-stu-id="ae8b0-126">Error :</span></span>

<span data-ttu-id="ae8b0-127">Diagnóstico</span><span class="sxs-lookup"><span data-stu-id="ae8b0-127">Diagnosis :</span></span>

<span data-ttu-id="ae8b0-128">Se Test-CsMcxPushNotification não puder se conectar à Clearinghouse de notificação por push, o cmdlet normalmente não retornará um resultado de teste de falha.</span><span class="sxs-lookup"><span data-stu-id="ae8b0-128">If Test-CsMcxPushNotification is unable to connect to the push notification clearinghouse the cmdlet will typically not return a test result of Failure.</span></span> <span data-ttu-id="ae8b0-129">Em vez disso, o comando geralmente falhará completamente.</span><span class="sxs-lookup"><span data-stu-id="ae8b0-129">Instead the command will usually fail completely.</span></span> <span data-ttu-id="ae8b0-130">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="ae8b0-130">For example:</span></span>

<span data-ttu-id="ae8b0-131">Test-CsMcxPushNotification: uma resposta de 504 (tempo limite do servidor) foi recebida da rede e a operação falhou.</span><span class="sxs-lookup"><span data-stu-id="ae8b0-131">Test-CsMcxPushNotification : A 504 (Server time-out) response was received from the network and the operation failed.</span></span> <span data-ttu-id="ae8b0-132">Consulte os detalhes da exceção para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="ae8b0-132">See the exception details for more information.</span></span>

<span data-ttu-id="ae8b0-133">Na linha: 1 caractere: 27</span><span class="sxs-lookup"><span data-stu-id="ae8b0-133">At line:1 char:27</span></span>

<span data-ttu-id="ae8b0-134">\+Test-CsMcxPushNotification \< \< \< \< -AccessEdgeFqdn lyncedge.mydomain.com</span><span class="sxs-lookup"><span data-stu-id="ae8b0-134">\+ Test-CsMcxPushNotification \<\<\<\< -AccessEdgeFqdn lyncedge.mydomain.com</span></span>

<span data-ttu-id="ae8b0-135">\+CategoryInfo: OperationStopped: (:) \[Test-CsMcxPushNotification\], FailureResponseException</span><span class="sxs-lookup"><span data-stu-id="ae8b0-135">\+ CategoryInfo : OperationStopped: (:) \[Test-CsMcxPushNotification\], FailureResponseException</span></span>

<span data-ttu-id="ae8b0-136">\+FullyQualifiedErrorId: WorkflowNotCompleted, Microsoft. RTC. Management. SyntheticTransactions. TestMcxPushNotificationCmdlet</span><span class="sxs-lookup"><span data-stu-id="ae8b0-136">\+ FullyQualifiedErrorId : WorkflowNotCompleted,Microsoft.Rtc.Management.SyntheticTransactions.TestMcxPushNotificationCmdlet</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="ae8b0-137">Motivos pelos quais o teste pode ter falhado</span><span class="sxs-lookup"><span data-stu-id="ae8b0-137">Reasons why the test might have failed</span></span>

<span data-ttu-id="ae8b0-138">Se o serviço de notificação por push falhar, geralmente indica problemas de comunicação com o servidor de borda ou problemas de comunicação com a casa de compensação de notificação por push.</span><span class="sxs-lookup"><span data-stu-id="ae8b0-138">If the push notification service fails that usually indicates either problems communicating with your Edge server, or problems communicating with the Push Notification Clearing House.</span></span> <span data-ttu-id="ae8b0-139">Se você tiver problemas ao executar o Test-CsMcxPushNotification, a primeira coisa a fazer é verificar se o servidor de borda está funcionando corretamente.</span><span class="sxs-lookup"><span data-stu-id="ae8b0-139">If you encounter problems when you run Test-CsMcxPushNotification, the first thing that you should do is verify that your Edge server is working correctly.</span></span> <span data-ttu-id="ae8b0-140">Uma maneira de fazer isso é usar o cmdlet Test-CsAVEdgeConnectivity:</span><span class="sxs-lookup"><span data-stu-id="ae8b0-140">One way to do that is to use the Test-CsAVEdgeConnectivity cmdlet:</span></span>

    $credential = Get-Credential "litwareinc\kenmyer"
    
    Test-CsAVEdgeConnectivity -TargetFqdn "atl-cs-001.litwareinc.com" -UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential

<span data-ttu-id="ae8b0-141">Essa verificação verifica se um usuário especificado pode se conectar ao servidor de borda.</span><span class="sxs-lookup"><span data-stu-id="ae8b0-141">This check verifies that a specified user can connect to the Edge server.</span></span>

<span data-ttu-id="ae8b0-142">Se o servidor de borda parecer estar funcionando corretamente, isso geralmente significa que você não consegue se conectar à Clearinghouse de notificação por push.</span><span class="sxs-lookup"><span data-stu-id="ae8b0-142">If the Edge server seems to be working correctly, that often means that you are unable to connect to the push notification clearinghouse.</span></span> <span data-ttu-id="ae8b0-143">Por sua vez, isso normalmente significa que você não configurou o URI da Clearinghouse corretamente ou que você não tem um registro SRV DNS que aponta para essa URL.</span><span class="sxs-lookup"><span data-stu-id="ae8b0-143">In turn, that typically means that you either have not configured the clearinghouse URI correctly or that you do not have a DNS SRV record that points to this URL.</span></span> <span data-ttu-id="ae8b0-144">Você pode verificar se o URI está definido como o valor correto (sip:push@push.lync.com) executando este comando:</span><span class="sxs-lookup"><span data-stu-id="ae8b0-144">You can verify that the URI is set to the correct value (sip:push@push.lync.com) by running this command:</span></span>

    Get-CsMcxConfiguration

<span data-ttu-id="ae8b0-145">Se a propriedade PushNotificationProxyUri for definida como algo diferente de sip:push@push.lync.com, você poderá corrigir esse problema usando o cmdlet Set-McxConfiguration.</span><span class="sxs-lookup"><span data-stu-id="ae8b0-145">If the PushNotificationProxyUri property is set to anything other than sip:push@push.lync.com then you can correct that problem by using the Set-McxConfiguration cmdlet.</span></span> <span data-ttu-id="ae8b0-146">Por exemplo, este comando define corretamente o URI em toda a sua organização:</span><span class="sxs-lookup"><span data-stu-id="ae8b0-146">For example, this command correctly sets the URI throughout your organization:</span></span>

    Get-CsMcxConfiguration | Set-CsMcxConfiguration -PushNotificationProxyUri "sip:push@push.lync.com"

<span data-ttu-id="ae8b0-147">Para obter mais informações, consulte o tópico de ajuda para o cmdlet [set-CsMcxConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsMcxConfiguration) .</span><span class="sxs-lookup"><span data-stu-id="ae8b0-147">For more information, see the help topic for the [Set-CsMcxConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsMcxConfiguration) cmdlet.</span></span>

<span data-ttu-id="ae8b0-148">Se o URI estiver configurado corretamente, sua próxima etapa deverá ser verificar se você tem um registro SRV de DNS que resolva o domínio SIP e o servidor de borda.</span><span class="sxs-lookup"><span data-stu-id="ae8b0-148">If the URI is configured correctly, your next step should be to verify that you have a DNS SRV record that resolves to your SIP domain and your Edge server.</span></span> <span data-ttu-id="ae8b0-149">Para obter mais informações sobre como configurar esses registros, consulte o tópico de ajuda requisitos de DNS para mobilidade.</span><span class="sxs-lookup"><span data-stu-id="ae8b0-149">For more information about how to configure these records, see the help topic DNS Requirements for Mobility.</span></span> <span data-ttu-id="ae8b0-150">Observe que a seguinte mensagem de erro geralmente indica um problema com registros DNS:</span><span class="sxs-lookup"><span data-stu-id="ae8b0-150">Note that the following error message usually indicates a problem with DNS records:</span></span>

<span data-ttu-id="ae8b0-151">Uma resposta de 504 (tempo limite do servidor) foi recebida da rede e a operação falhou.</span><span class="sxs-lookup"><span data-stu-id="ae8b0-151">A 504 (Server time-out) response was received from the network and the operation failed.</span></span> <span data-ttu-id="ae8b0-152">Consulte os detalhes da exceção para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="ae8b0-152">See the exception details for more information.</span></span>

<span data-ttu-id="ae8b0-153">Também é possível que o Test-CsMcxConfiguration falhe com esta mensagem de erro:</span><span class="sxs-lookup"><span data-stu-id="ae8b0-153">It’s also possible that Test-CsMcxConfiguration will fail with this error message:</span></span>

<span data-ttu-id="ae8b0-154">Test-CsMcxPushNotification: a solicitação de notificação por push foi rejeitada.</span><span class="sxs-lookup"><span data-stu-id="ae8b0-154">Test-CsMcxPushNotification : Push Notification request was rejected.</span></span>

<span data-ttu-id="ae8b0-155">Na linha: 1 caractere: 27</span><span class="sxs-lookup"><span data-stu-id="ae8b0-155">At line:1 char:27</span></span>

<span data-ttu-id="ae8b0-156">\+Test-CsMcxPushNotification\<\<\<\<</span><span class="sxs-lookup"><span data-stu-id="ae8b0-156">\+ Test-CsMcxPushNotification \<\<\<\<</span></span>

<span data-ttu-id="ae8b0-157">\+CategoryInfo: OperationStopped: (:) \[Test-CsMcxPushNotification\], SyntheticTransactionException</span><span class="sxs-lookup"><span data-stu-id="ae8b0-157">\+ CategoryInfo : OperationStopped: (:) \[Test-CsMcxPushNotification\], SyntheticTransactionException</span></span>

<span data-ttu-id="ae8b0-158">\+FullyQualifiedErrorId: WorkflowNotCompleted, Microsoft. RTC. Management. SyntheticTransactions. TestMcxPushNotificationCmdlet</span><span class="sxs-lookup"><span data-stu-id="ae8b0-158">\+ FullyQualifiedErrorId : WorkflowNotCompleted,Microsoft.Rtc.Management.SyntheticTransactions.TestMcxPushNotificationCmdlet</span></span>

<span data-ttu-id="ae8b0-159">A mensagem "solicitação de notificação por push foi rejeitada" geralmente ocorrerá se você tiver habilitado a filtragem de URL e estiver bloqueando os prefixos http: e https:.</span><span class="sxs-lookup"><span data-stu-id="ae8b0-159">The “Push notification request was rejected” message typically occurs if you have enabled URL filtering and are blocking the http: and https: prefixes.</span></span> <span data-ttu-id="ae8b0-160">Você pode determinar quais prefixos estão sendo bloqueados usando um comando semelhante ao seguinte:</span><span class="sxs-lookup"><span data-stu-id="ae8b0-160">You can determine which prefixes are being blocked by using a command similar to the following:</span></span>

```PowerShell 
 (Get-CsImFilterConfiguration -Identity Global).Prefixes
```

<span data-ttu-id="ae8b0-161">Se http: ou https: aparecer nos resultados, você deve removê-los da lista de prefixos bloqueados para que as notificações por push funcionem.</span><span class="sxs-lookup"><span data-stu-id="ae8b0-161">If http: or https: appear in the results, you must remove them from the blocked prefix list for push notifications to work.</span></span> <span data-ttu-id="ae8b0-162">Isso pode ser feito com o uso de comandos semelhantes a estes:</span><span class="sxs-lookup"><span data-stu-id="ae8b0-162">That can be done by using commands similar to these:</span></span>

    Set-CsImFilterConfiguration -Identity site:Redmond -Prefixes @{remove="http:"}
    Set-CsImFilterConfiguration -Identity site:Redmond -Prefixes @{remove="https:"}

<span data-ttu-id="ae8b0-163">Para obter mais informações, consulte o tópico de ajuda para o cmdlet [set-CsImFilterConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsImFilterConfiguration).</span><span class="sxs-lookup"><span data-stu-id="ae8b0-163">For more information, see the help topic for the [Set-CsImFilterConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsImFilterConfiguration)cmdlet.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

