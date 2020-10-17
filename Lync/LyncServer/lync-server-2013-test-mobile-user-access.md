---
title: 'Lync Server 2013: testar acesso de usuário móvel'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Test mobile user access
ms:assetid: 81d97420-428b-41b7-91ef-185d572d3456
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn767947(v=OCS.15)
ms:contentKeyID: 63969624
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 83d5be38ecddad1f9388f5e2efb33994b49e4bfd
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48519208"
---
# <a name="test-mobile-user-access-in-lync-server-2013"></a><span data-ttu-id="7ae51-102">Testar o acesso de usuário móvel no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7ae51-102">Test mobile user access in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7ae51-103">_**Última modificação do tópico:** 2014-06-07_</span><span class="sxs-lookup"><span data-stu-id="7ae51-103">_**Topic Last Modified:** 2014-06-07_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="7ae51-104">Agenda de verificação</span><span class="sxs-lookup"><span data-stu-id="7ae51-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="7ae51-105">Mensal</span><span class="sxs-lookup"><span data-stu-id="7ae51-105">Monthly</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7ae51-106">Ferramenta de teste</span><span class="sxs-lookup"><span data-stu-id="7ae51-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="7ae51-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="7ae51-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7ae51-108">Permissões obrigatórias</span><span class="sxs-lookup"><span data-stu-id="7ae51-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="7ae51-109">Ao executar localmente usando o Shell de gerenciamento do Lync Server, os usuários devem ser membros do grupo de segurança RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="7ae51-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="7ae51-110">Quando executado usando uma instância remota do Windows PowerShell, os usuários devem receber uma função RBAC que tenha permissão para executar o cmdlet Test-CsMcxConference.</span><span class="sxs-lookup"><span data-stu-id="7ae51-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsMcxConference cmdlet.</span></span> <span data-ttu-id="7ae51-111">Para ver uma lista de todas as funções RBAC que podem usar este cmdlet, execute o seguinte comando no prompt do Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="7ae51-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsMcxConference&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="7ae51-112">Descrição</span><span class="sxs-lookup"><span data-stu-id="7ae51-112">Description</span></span>

<span data-ttu-id="7ae51-113">O serviço de mobilidade permite que os usuários de dispositivos móveis façam coisas como:</span><span class="sxs-lookup"><span data-stu-id="7ae51-113">The Mobility Service enables mobile device users to do such things as:</span></span>

1.  <span data-ttu-id="7ae51-114">Informações de presença e mensagens instantâneas do Exchange.</span><span class="sxs-lookup"><span data-stu-id="7ae51-114">Exchange instant messages and presence information.</span></span>

2.  <span data-ttu-id="7ae51-115">Armazenar e recuperar a caixa postal internamente em vez de com seu provedor sem fio.</span><span class="sxs-lookup"><span data-stu-id="7ae51-115">Store and retrieve voice mail internally instead of with their wireless provider.</span></span>

3.  <span data-ttu-id="7ae51-116">Aproveite os recursos do Lync Server, como ligar via trabalho e conferência discada.</span><span class="sxs-lookup"><span data-stu-id="7ae51-116">Take advantage of Lync Server capabilities such as Call via Work and dial-out conferencing.</span></span> <span data-ttu-id="7ae51-117">O cmdlet Test-CsMcxConference oferece uma maneira rápida e fácil de verificar se os usuários podem participar e participar de conferências do Lync Server usando um dispositivo móvel.</span><span class="sxs-lookup"><span data-stu-id="7ae51-117">The Test-CsMcxConference cmdlet provides a quick and easy way to verify that users can join and participate in Lync Server conferences by using a mobile device.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="7ae51-118">Executar o teste</span><span class="sxs-lookup"><span data-stu-id="7ae51-118">Running the test</span></span>

<span data-ttu-id="7ae51-119">Para executar essa verificação, você deve criar três objetos de credenciais do Windows PowerShell (objetos que contêm o nome da conta e a senha) para cada conta.</span><span class="sxs-lookup"><span data-stu-id="7ae51-119">To run this check, you must create three Windows PowerShell credentials objects (objects that contain the account name and password) for each account.</span></span> <span data-ttu-id="7ae51-120">Em seguida, você deve incluir esses objetos de credenciais e os endereços SIP das duas contas quando chamar Test-CsMcxConference conforme mostrado no exemplo a seguir:</span><span class="sxs-lookup"><span data-stu-id="7ae51-120">You must then include those credentials objects and the SIP addresses of the two accounts when you call Test-CsMcxConference as shown in the following example:</span></span>

    $organizerCred = Get-Credential "litwareinc\kenmyer"
    $user1Cred = Get-Credential "litwareinc\packerman"
    $user2Cred = Get-Credential "litwareinc\adelaney"
    
    Test-CsMcxConference -TargetFqdn "atl-cs-001.litwareinc.com" -Authentication Negotiate -OrganizerSipAddress "sip:kenmyer@litwareinc.com" -OrganizerCredential $organizerCred -UserSipAddress "sip:pilar@litwareinc.com" -UserCredential $user1Cred -User2SipAddress "sip:adelaney@litwareinc.com" -User2Credential $user2Cred

<span data-ttu-id="7ae51-121">Para obter mais informações, consulte o tópico de ajuda para o cmdlet [Test-CsMcxConference](https://docs.microsoft.com/powershell/module/skype/Test-CsMcxConference) .</span><span class="sxs-lookup"><span data-stu-id="7ae51-121">For more information, see the help topic for the [Test-CsMcxConference](https://docs.microsoft.com/powershell/module/skype/Test-CsMcxConference) cmdlet.</span></span>

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="7ae51-122">Determinando o sucesso ou a falha</span><span class="sxs-lookup"><span data-stu-id="7ae51-122">Determining success or failure</span></span>

<span data-ttu-id="7ae51-123">Se a verificação tiver êxito, Test-CsMcxConference relatará o resultado do teste de êxito:</span><span class="sxs-lookup"><span data-stu-id="7ae51-123">If the check succeeds, Test-CsMcxConference will report a test result of Success:</span></span>

<span data-ttu-id="7ae51-124">FQDN de destino: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="7ae51-124">Target Fqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="7ae51-125">URI de destino: http://atl-cs-001.litwareinc.com:443/mcx</span><span class="sxs-lookup"><span data-stu-id="7ae51-125">Target Uri : http://atl-cs-001.litwareinc.com:443/mcx</span></span>

<span data-ttu-id="7ae51-126">Resultado: êxito</span><span class="sxs-lookup"><span data-stu-id="7ae51-126">Result : Success</span></span>

<span data-ttu-id="7ae51-127">Latência: 00:00:00</span><span class="sxs-lookup"><span data-stu-id="7ae51-127">Latency : 00:00:00</span></span>

<span data-ttu-id="7ae51-128">Mensagem de erro:</span><span class="sxs-lookup"><span data-stu-id="7ae51-128">Error Message :</span></span>

<span data-ttu-id="7ae51-129">Diagnóstico</span><span class="sxs-lookup"><span data-stu-id="7ae51-129">Diagnosis :</span></span>

<span data-ttu-id="7ae51-130">Se a verificação for malsucedida Test-CsMcxConference relatará um resultado de teste de falha.</span><span class="sxs-lookup"><span data-stu-id="7ae51-130">If the check is unsuccessful Test-CsMcxConference will report a test result of Failure.</span></span> <span data-ttu-id="7ae51-131">Esse resultado de teste normalmente será acompanhado por uma mensagem de erro e um diagnóstico detalhados.</span><span class="sxs-lookup"><span data-stu-id="7ae51-131">This test result will typically be accompanied by a detailed error message and diagnosis.</span></span> <span data-ttu-id="7ae51-132">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="7ae51-132">For example:</span></span>

<span data-ttu-id="7ae51-133">FQDN de destino: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="7ae51-133">Target Fqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="7ae51-134">URI de destino: https://atl-cs-001.litwareinc.com:443/mcx</span><span class="sxs-lookup"><span data-stu-id="7ae51-134">Target Uri : https://atl-cs-001.litwareinc.com:443/mcx</span></span>

<span data-ttu-id="7ae51-135">Resultado: falha</span><span class="sxs-lookup"><span data-stu-id="7ae51-135">Result : Failure</span></span>

<span data-ttu-id="7ae51-136">Latência: 00:00:00</span><span class="sxs-lookup"><span data-stu-id="7ae51-136">Latency : 00:00:00</span></span>

<span data-ttu-id="7ae51-137">Mensagem de erro: nenhuma resposta recebida para o serviço de Web-Ticket.</span><span class="sxs-lookup"><span data-stu-id="7ae51-137">Error Message : No response received for Web-Ticket service.</span></span>

<span data-ttu-id="7ae51-138">Exceção interna: a solicitação HHTP não é autorizada com o cliente</span><span class="sxs-lookup"><span data-stu-id="7ae51-138">Inner Exception:The HHTP request is unauthorized with client</span></span>

<span data-ttu-id="7ae51-139">esquema de negociação ' NTLM '.</span><span class="sxs-lookup"><span data-stu-id="7ae51-139">negotiation scheme 'Ntlm'.</span></span> <span data-ttu-id="7ae51-140">O cabeçalho de autenticação recebido</span><span class="sxs-lookup"><span data-stu-id="7ae51-140">The authentication header received</span></span>

<span data-ttu-id="7ae51-141">do servidor foi ' Negotiate '.</span><span class="sxs-lookup"><span data-stu-id="7ae51-141">from the server was 'Negotiate'.</span></span>

<span data-ttu-id="7ae51-142">Exceção interna: o servidor remoto retornou um erro: (401)</span><span class="sxs-lookup"><span data-stu-id="7ae51-142">Inner Exception:The remote server returned an error: (401)</span></span>

<span data-ttu-id="7ae51-143">Não autorizado.</span><span class="sxs-lookup"><span data-stu-id="7ae51-143">Unauthorized.</span></span>

<span data-ttu-id="7ae51-144">Diagnóstico</span><span class="sxs-lookup"><span data-stu-id="7ae51-144">Diagnosis :</span></span>

<span data-ttu-id="7ae51-145">Diagnóstico interno: X-MS-Server-Fqdb: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="7ae51-145">Inner Diagnosis:X-MS-server-Fqdb : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="7ae51-146">Cache-Control: privada</span><span class="sxs-lookup"><span data-stu-id="7ae51-146">Cache-Control : private</span></span>

<span data-ttu-id="7ae51-147">Content-Type: text/html; charset = utf-8.</span><span class="sxs-lookup"><span data-stu-id="7ae51-147">Content-Type : text/html; charset=utf-8.</span></span>

<span data-ttu-id="7ae51-148">Servidor: Microsoft-IIS/8.5</span><span class="sxs-lookup"><span data-stu-id="7ae51-148">Server : Microsoft-IIS/8.5</span></span>

<span data-ttu-id="7ae51-149">WWW-Authenticate: negociar, NTLM</span><span class="sxs-lookup"><span data-stu-id="7ae51-149">WWW-Authenticate : Negotiate,NTLM</span></span>

<span data-ttu-id="7ae51-150">X-powered-by: ASP.NET</span><span class="sxs-lookup"><span data-stu-id="7ae51-150">X-Powered-By : ASP.NET</span></span>

<span data-ttu-id="7ae51-151">X-Content-Type-opções: nosniff</span><span class="sxs-lookup"><span data-stu-id="7ae51-151">X-Content-Type-Options : nosniff</span></span>

<span data-ttu-id="7ae51-152">Date: Qua, 28 de maio de 2014 19:22:19 GMT</span><span class="sxs-lookup"><span data-stu-id="7ae51-152">Date : Wed, 28 May 2014 19:22:19 GMT</span></span>

<span data-ttu-id="7ae51-153">Content-Length: 6305</span><span class="sxs-lookup"><span data-stu-id="7ae51-153">Content-Length : 6305</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="7ae51-154">Motivos pelos quais o teste pode ter falhado</span><span class="sxs-lookup"><span data-stu-id="7ae51-154">Reasons why the test might have failed</span></span>

<span data-ttu-id="7ae51-155">Se Test-CsMcxConference falhar, verifique se o serviço de mobilidade está em execução e se pode ser acessado.</span><span class="sxs-lookup"><span data-stu-id="7ae51-155">If Test-CsMcxConference fails you should begin by verifying that the mobility service is running and can be accessed.</span></span> <span data-ttu-id="7ae51-156">Isso pode ser feito usando um navegador da Web para verificar se a URL do serviço de mobilidade do seu pool do Lync Server pode ser acessada.</span><span class="sxs-lookup"><span data-stu-id="7ae51-156">That can be done by using a web browser to verify that the mobility service URL for your Lync Server pool can be accessed.</span></span> <span data-ttu-id="7ae51-157">Por exemplo, este comando verifica a URL para o pool atl-cs-001.litwareinc.com:</span><span class="sxs-lookup"><span data-stu-id="7ae51-157">For example, this command verifies the URL for the pool atl-cs-001.litwareinc.com:</span></span>

`https://atl-cs-001.litwareinc.com/mcx/mcxservice.svc`

<span data-ttu-id="7ae51-158">Se o serviço de mobilidade puder ser acessado, verifique se os usuários de teste possuem contas válidas do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="7ae51-158">If the mobility service can be accessed you should then verify that your test users have valid Lync Server accounts.</span></span> <span data-ttu-id="7ae51-159">Você pode recuperar informações da conta usando um comando semelhante ao seguinte:</span><span class="sxs-lookup"><span data-stu-id="7ae51-159">You can retrieve account information by using a command similar to this:</span></span>

    Get-CsUser -Identity "sip:kenmyer@litwareinc.com" | Select-Object Enabled

<span data-ttu-id="7ae51-160">Se a propriedade Enabled não for igual a true ou se o comando falhar, isso significa que o usuário não tem uma conta válida do Lync Server. Você também deve verificar se cada conta de usuário está habilitada para mobilidade.</span><span class="sxs-lookup"><span data-stu-id="7ae51-160">If the Enabled property is not equal to True or if the command fails, that means that the user does not have a valid Lync Server account.You should also verify that each user account is enabled for mobility.</span></span> <span data-ttu-id="7ae51-161">Para fazer isso, primeiro determine a política de mobilidade atribuída à conta:</span><span class="sxs-lookup"><span data-stu-id="7ae51-161">To do that, first determine the mobility policy that is assigned to the account:</span></span>

    Get-CsUser -Identity "sip:kenmyer@litwareinc.com" | Select-Object MobilityPolicy

<span data-ttu-id="7ae51-162">Após saber o nome da política, use o cmdlet Get-CsMobilityPolicy para verificar se a política em questão (por exemplo, Edmondmobilitypolicy) tem a propriedade EnableMobility definida como true:</span><span class="sxs-lookup"><span data-stu-id="7ae51-162">After you know the policy name, use the Get-CsMobilityPolicy cmdlet to verify that the policy in question (for example, RedmondMobilityPolicy) has the EnableMobility property set to True:</span></span>

    Get-CsMobilityPolicy -Identity "RedmondMobilityPolicy"

<span data-ttu-id="7ae51-163">Se você receber uma mensagem de erro "cabeçalho de autenticação" ao executar Test-CsMcxConference que normalmente significa que você não especificou uma conta de usuário válida, verifique o nome de usuário e a senha e tente o teste novamente.</span><span class="sxs-lookup"><span data-stu-id="7ae51-163">If you receive an “authentication header” error message when you run Test-CsMcxConference that often means that you have not specified a valid user account, Verify the user name and password and then try the test again.</span></span> <span data-ttu-id="7ae51-164">Se você estiver convencido de que a conta de usuário é válida, use o cmdlet Get-CsWebServiceConfiguration e verifique o valor da Propriedade UseWindowsAuth.</span><span class="sxs-lookup"><span data-stu-id="7ae51-164">If you are convinced that the user account is valid, then use the Get-CsWebServiceConfiguration cmdlet and check the value of the UseWindowsAuth property.</span></span> <span data-ttu-id="7ae51-165">Isso indicará quais métodos de autenticação estão habilitados em sua organização.</span><span class="sxs-lookup"><span data-stu-id="7ae51-165">That will tell you which authentication methods are enabled in your organization.</span></span>

<span data-ttu-id="7ae51-166">Para obter mais dicas sobre como solucionar problemas do serviço de mobilidade, consulte o blog post [Troubleshooting external Lync Mobility Connectivity issues passo a passo](https://blogs.technet.com/b/nexthop/archive/2012/02/21/troubleshooting-external-lync-mobility-connectivity-issues-step-by-step.aspx).</span><span class="sxs-lookup"><span data-stu-id="7ae51-166">For more tips about how to troubleshoot the mobility service, see the blog post [Troubleshooting External Lync Mobility Connectivity Issues Step-by-Step](https://blogs.technet.com/b/nexthop/archive/2012/02/21/troubleshooting-external-lync-mobility-connectivity-issues-step-by-step.aspx).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

