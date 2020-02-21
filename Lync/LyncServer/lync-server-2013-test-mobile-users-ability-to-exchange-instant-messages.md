---
title: 'Lync Server 2013: testar a capacidade dos usuários móveis de trocar mensagens instantâneas'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Test mobile users' ability to exchange instant messages
ms:assetid: a78a048f-d413-4bee-8626-d62b8b74f811
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn767950(v=OCS.15)
ms:contentKeyID: 63969638
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f3536e7bc95aced3a8bd68cab15b8994aa9e697c
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42194544"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="test-mobile-users-ability-to-exchange-instant-messages-in-lync-server-2013"></a><span data-ttu-id="dd3a1-102">Testar a capacidade dos usuários móveis de trocar mensagens instantâneas no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="dd3a1-102">Test mobile users' ability to exchange instant messages in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="dd3a1-103">_**Última modificação do tópico:** 2014-06-07_</span><span class="sxs-lookup"><span data-stu-id="dd3a1-103">_**Topic Last Modified:** 2014-06-07_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="dd3a1-104">Agenda de verificação</span><span class="sxs-lookup"><span data-stu-id="dd3a1-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="dd3a1-105">Mensal</span><span class="sxs-lookup"><span data-stu-id="dd3a1-105">Monthly</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dd3a1-106">Ferramenta de teste</span><span class="sxs-lookup"><span data-stu-id="dd3a1-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="dd3a1-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="dd3a1-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dd3a1-108">Permissões obrigatórias</span><span class="sxs-lookup"><span data-stu-id="dd3a1-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="dd3a1-109">Ao executar localmente usando o Shell de gerenciamento do Lync Server, os usuários devem ser membros do grupo de segurança RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="dd3a1-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="dd3a1-110">Quando executado usando uma instância remota do Windows PowerShell, os usuários devem receber uma função RBAC que tenha permissão para executar o cmdlet Test-CsMcxP2PIM.</span><span class="sxs-lookup"><span data-stu-id="dd3a1-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsMcxP2PIM cmdlet.</span></span> <span data-ttu-id="dd3a1-111">Para ver uma lista de todas as funções RBAC que podem usar este cmdlet, execute o seguinte comando no prompt do Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="dd3a1-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsMcxP2PIM&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="dd3a1-112">Descrição</span><span class="sxs-lookup"><span data-stu-id="dd3a1-112">Description</span></span>

<span data-ttu-id="dd3a1-113">O serviço de mobilidade permite que os usuários de dispositivos móveis façam coisas como:</span><span class="sxs-lookup"><span data-stu-id="dd3a1-113">The Mobility Service enables mobile device users to do such things as:</span></span>

1.  <span data-ttu-id="dd3a1-114">Informações de presença e mensagens instantâneas do Exchange.</span><span class="sxs-lookup"><span data-stu-id="dd3a1-114">Exchange instant messages and presence information.</span></span>

2.  <span data-ttu-id="dd3a1-115">Armazenar e recuperar a caixa postal internamente em vez de com seu provedor sem fio.</span><span class="sxs-lookup"><span data-stu-id="dd3a1-115">Store and retrieve voice mail internally instead of with their wireless provider.</span></span>

3.  <span data-ttu-id="dd3a1-116">Aproveite os recursos do Lync Server, como ligar via trabalho e conferência discada.</span><span class="sxs-lookup"><span data-stu-id="dd3a1-116">Take advantage of Lync Server capabilities such as Call via Work and dial-out conferencing.</span></span>

<span data-ttu-id="dd3a1-117">O cmdlet Test-CsMxcP2PIM fornece uma maneira rápida e fácil de verificar se os usuários podem usar o serviço de mobilidade para trocar mensagens instantâneas.</span><span class="sxs-lookup"><span data-stu-id="dd3a1-117">The Test-CsMxcP2PIM cmdlet provides a quick and easy way to verify that users can use the Mobility Service to exchange instant messages.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="dd3a1-118">Executar o teste</span><span class="sxs-lookup"><span data-stu-id="dd3a1-118">Running the test</span></span>

<span data-ttu-id="dd3a1-119">Para executar esse teste, você deve criar dois objetos de credenciais do Windows PowerShell (objetos que contêm o nome da conta e a senha) para cada conta.</span><span class="sxs-lookup"><span data-stu-id="dd3a1-119">To run this test, you must create two Windows PowerShell credentials objects (objects that contain the account name and password) for each account.</span></span> <span data-ttu-id="dd3a1-120">Em seguida, você deve incluir esses objetos de credenciais e os endereços SIP das duas contas ao chamar Test-CsMcxP2PIM:</span><span class="sxs-lookup"><span data-stu-id="dd3a1-120">You must then include those credentials objects and the SIP addresses of the two accounts when you call Test-CsMcxP2PIM:</span></span>

    $credential1 = Get-Credential "litwareinc\kenmyer"
    $credential2 = Get-Credential "litwareinc\pilar"
    
    Test-CsMcxP2PIM -TargetFqdn "atl-cs-001.litwareinc.com" -Authentication Negotiate -SenderSipAddres "sip:kenmyer@litwareinc.com" -SenderCredential $credential1 -ReceiverSipAddress "sip:packerman@litwareinc.com" -ReceiverCredential $credential2

<span data-ttu-id="dd3a1-121">Para obter mais informações, consulte o tópico de ajuda para o cmdlet [Test-CsMcxP2PIM](https://docs.microsoft.com/powershell/module/skype/Test-CsMcxP2PIM) .</span><span class="sxs-lookup"><span data-stu-id="dd3a1-121">For more information, see the help topic for the [Test-CsMcxP2PIM](https://docs.microsoft.com/powershell/module/skype/Test-CsMcxP2PIM) cmdlet.</span></span>

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="dd3a1-122">Determinando o sucesso ou a falha</span><span class="sxs-lookup"><span data-stu-id="dd3a1-122">Determining success or failure</span></span>

<span data-ttu-id="dd3a1-123">Se os dois usuários de teste puderem trocar mensagens instantâneas usando o serviço de mobilidade, Test-CsMcxP2PIM retornará o resultado de teste Success:</span><span class="sxs-lookup"><span data-stu-id="dd3a1-123">If the two test users can exchange instant messages by using the mobility service then Test-CsMcxP2PIM will return test result Success:</span></span>

<span data-ttu-id="dd3a1-124">FQDN de destino: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="dd3a1-124">Target Fqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="dd3a1-125">URI de destino:http://atl-cs-001.litwareinc.com:443/mcx</span><span class="sxs-lookup"><span data-stu-id="dd3a1-125">Target Uri : http://atl-cs-001.litwareinc.com:443/mcx</span></span>

<span data-ttu-id="dd3a1-126">Resultado: êxito</span><span class="sxs-lookup"><span data-stu-id="dd3a1-126">Result : Success</span></span>

<span data-ttu-id="dd3a1-127">Latência: 00:00:00</span><span class="sxs-lookup"><span data-stu-id="dd3a1-127">Latency : 00:00:00</span></span>

<span data-ttu-id="dd3a1-128">Mensagem de erro:</span><span class="sxs-lookup"><span data-stu-id="dd3a1-128">Error Message :</span></span>

<span data-ttu-id="dd3a1-129">Diagnóstico</span><span class="sxs-lookup"><span data-stu-id="dd3a1-129">Diagnosis :</span></span>

<span data-ttu-id="dd3a1-130">Se o teste falhar, o resultado será definido como Failure e uma mensagem de erro detalhada e diagnóstico será exibido:</span><span class="sxs-lookup"><span data-stu-id="dd3a1-130">If the test fails then the Result will be set to Failure and a detailed error message and diagnosis will be displayed:</span></span>

<span data-ttu-id="dd3a1-131">FQDN de destino: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="dd3a1-131">Target Fqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="dd3a1-132">URI de destino:https://atl-cs-001.litwareinc.com:443/mcx</span><span class="sxs-lookup"><span data-stu-id="dd3a1-132">Target Uri : https://atl-cs-001.litwareinc.com:443/mcx</span></span>

<span data-ttu-id="dd3a1-133">Resultado: falha</span><span class="sxs-lookup"><span data-stu-id="dd3a1-133">Result : Failure</span></span>

<span data-ttu-id="dd3a1-134">Latência: 00:00:00</span><span class="sxs-lookup"><span data-stu-id="dd3a1-134">Latency : 00:00:00</span></span>

<span data-ttu-id="dd3a1-135">Mensagem de erro: nenhuma resposta recebida para o serviço de tíquete da Web.</span><span class="sxs-lookup"><span data-stu-id="dd3a1-135">Error Message : No response received for Web-Ticket service.</span></span>

<span data-ttu-id="dd3a1-136">Exceção interna: a solicitação HHTP não é autorizada com</span><span class="sxs-lookup"><span data-stu-id="dd3a1-136">Inner Exception:The HHTP request is unauthorized with</span></span>

<span data-ttu-id="dd3a1-137">esquema de negociação de cliente ' NTLM '.</span><span class="sxs-lookup"><span data-stu-id="dd3a1-137">client negotiation scheme 'Ntlm'.</span></span> <span data-ttu-id="dd3a1-138">A autenticação</span><span class="sxs-lookup"><span data-stu-id="dd3a1-138">The authentication</span></span>

<span data-ttu-id="dd3a1-139">o cabeçalho recebido do servidor era ' Negotiate, NTLM '.</span><span class="sxs-lookup"><span data-stu-id="dd3a1-139">header received from the server was 'Negotiate,NTLM'.</span></span>

<span data-ttu-id="dd3a1-140">Exceção interna: o servidor remoto retornou um erro:</span><span class="sxs-lookup"><span data-stu-id="dd3a1-140">Inner Exception:The remote server returned an error:</span></span>

<span data-ttu-id="dd3a1-141">(401) não autorizado.</span><span class="sxs-lookup"><span data-stu-id="dd3a1-141">(401) Unauthorized.</span></span>

<span data-ttu-id="dd3a1-142">Diagnóstico</span><span class="sxs-lookup"><span data-stu-id="dd3a1-142">Diagnosis :</span></span>

<span data-ttu-id="dd3a1-143">Diagnóstico interno: X-MS-Server-Fqdb: ATL-cs-</span><span class="sxs-lookup"><span data-stu-id="dd3a1-143">Inner Diagnosis:X-MS-server-Fqdb : atl-cs-</span></span>

<span data-ttu-id="dd3a1-144">001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="dd3a1-144">001.litwareinc.com</span></span>

<span data-ttu-id="dd3a1-145">Cache-Control: Private</span><span class="sxs-lookup"><span data-stu-id="dd3a1-145">Cache-Control : private</span></span>

<span data-ttu-id="dd3a1-146">Content-Type: text/html; charset = utf-8.</span><span class="sxs-lookup"><span data-stu-id="dd3a1-146">Content-Type : text/html; charset=utf-8.</span></span>

<span data-ttu-id="dd3a1-147">Servidor: Microsoft-IIS/8.5</span><span class="sxs-lookup"><span data-stu-id="dd3a1-147">Server : Microsoft-IIS/8.5</span></span>

<span data-ttu-id="dd3a1-148">WWW-Authenticate: Negotiate, NTLM</span><span class="sxs-lookup"><span data-stu-id="dd3a1-148">WWW-Authenticate : Negotiate,NTLM</span></span>

<span data-ttu-id="dd3a1-149">X-powered-by: ASP.NET</span><span class="sxs-lookup"><span data-stu-id="dd3a1-149">X-Powered-By : ASP.NET</span></span>

<span data-ttu-id="dd3a1-150">X-Content-Type-opções: nosniff</span><span class="sxs-lookup"><span data-stu-id="dd3a1-150">X-Content-Type-Options : nosniff</span></span>

<span data-ttu-id="dd3a1-151">Date: Qua, 28 de maio de 2014 19:16:05 GMT</span><span class="sxs-lookup"><span data-stu-id="dd3a1-151">Date : Wed, 28 May 2014 19:16:05 GMT</span></span>

<span data-ttu-id="dd3a1-152">Content-Length: 6305</span><span class="sxs-lookup"><span data-stu-id="dd3a1-152">Content-Length : 6305</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="dd3a1-153">Motivos pelos quais o teste pode ter falhado</span><span class="sxs-lookup"><span data-stu-id="dd3a1-153">Reasons why the test might have failed</span></span>

<span data-ttu-id="dd3a1-154">Se Test-CsMcxP2PIM falhar, a primeira etapa deve ser verificar se o serviço de mobilidade está ativo e em execução.</span><span class="sxs-lookup"><span data-stu-id="dd3a1-154">If Test-CsMcxP2PIM fails your first step should be to verify that the mobility service is up and running.</span></span> <span data-ttu-id="dd3a1-155">Isso pode ser feito usando um navegador da Web para verificar se a URL do serviço de mobilidade do seu pool do Lync Server pode ser acessada.</span><span class="sxs-lookup"><span data-stu-id="dd3a1-155">That can be done by using a web browser to verify that the mobility service URL for your Lync Server pool can be accessed.</span></span> <span data-ttu-id="dd3a1-156">Por exemplo, este comando verifica a URL para o pool atl-cs-001.litwareinc.com:</span><span class="sxs-lookup"><span data-stu-id="dd3a1-156">For example, this command verifies the URL for the pool atl-cs-001.litwareinc.com:</span></span>

    https://atl-cs-001.litwareinc.com/mcx/mcxservice.svc

<span data-ttu-id="dd3a1-157">Se o serviço de mobilidade parecer estar em execução, verifique se os dois usuários de teste possuem contas válidas do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="dd3a1-157">If the mobility service seems to be running then verify that your two test users have valid Lync Server accounts.</span></span> <span data-ttu-id="dd3a1-158">Você pode recuperar informações da conta usando um comando semelhante ao seguinte:</span><span class="sxs-lookup"><span data-stu-id="dd3a1-158">You can retrieve account information by using a command similar to this:</span></span>

    Get-CsUser -Identity "sip:kenmyer@litwareinc.com" | Select-Object Enabled

<span data-ttu-id="dd3a1-159">Se a propriedade Enabled não for igual a true ou se o comando falhar, isso significa que o usuário não tem uma conta válida do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="dd3a1-159">If the Enabled property is not equal to True or if the command fails, that means that the user does not have a valid Lync Server account.</span></span>

<span data-ttu-id="dd3a1-160">Você também deve verificar se o usuário está habilitado para mobilidade.</span><span class="sxs-lookup"><span data-stu-id="dd3a1-160">You should also verify that the user is enabled for mobility.</span></span> <span data-ttu-id="dd3a1-161">Para fazer isso, primeiro determine a política de mobilidade atribuída à conta:</span><span class="sxs-lookup"><span data-stu-id="dd3a1-161">To do that, first determine the mobility policy that is assigned to the account:</span></span>

    Get-CsUser -Identity "sip:kenmyer@litwareinc.com" | Select-Object MobilityPolicy

<span data-ttu-id="dd3a1-162">Depois de saber o nome da política, use o cmdlet Get-CsMobilityPolicy para verificar se a política em questão (por exemplo, Edmondmobilitypolicy) tem a propriedade EnableMobility definida como true:</span><span class="sxs-lookup"><span data-stu-id="dd3a1-162">After you know the policy name, use the Get-CsMobilityPolicy cmdlet to verify that the policy in question (for example, RedmondMobilityPolicy) has the EnableMobility property set to True:</span></span>

    Get-CsMobilityPolicy -Identity "RedmondMobilityPolicy"

<span data-ttu-id="dd3a1-163">Se você receber uma mensagem de erro com cabeçalhos de autenticação, isso geralmente significa que você não especificou uma conta de usuário válida.</span><span class="sxs-lookup"><span data-stu-id="dd3a1-163">If you receive an error message with authentication headers, that often means that you have not specified a valid user account.</span></span> <span data-ttu-id="dd3a1-164">Verifique o nome de usuário e a senha e tente o teste novamente.</span><span class="sxs-lookup"><span data-stu-id="dd3a1-164">Verify the user name and password and then try the test again.</span></span> <span data-ttu-id="dd3a1-165">Se você estiver convencido de que a conta de usuário é válida, use o cmdlet Get-CsWebServiceConfiguration e verifique o valor da Propriedade UseWindowsAuth.</span><span class="sxs-lookup"><span data-stu-id="dd3a1-165">If you are convinced that the user account is valid, then use the Get-CsWebServiceConfiguration cmdlet and check the value of the UseWindowsAuth property.</span></span> <span data-ttu-id="dd3a1-166">Isso indicará quais métodos de autenticação estão habilitados em sua organização. Para obter mais dicas sobre como solucionar problemas do serviço de mobilidade, consulte o blog post [Troubleshooting external Lync Mobility Connectivity issues passo a passo](https://blogs.technet.com/b/nexthop/archive/2012/02/21/troubleshooting-external-lync-mobility-connectivity-issues-step-by-step.aspx).</span><span class="sxs-lookup"><span data-stu-id="dd3a1-166">That will tell you which authentication methods are enabled in your organization.For more tips about how to troubleshoot the mobility service, see the blog post [Troubleshooting External Lync Mobility Connectivity Issues Step-by-Step](https://blogs.technet.com/b/nexthop/archive/2012/02/21/troubleshooting-external-lync-mobility-connectivity-issues-step-by-step.aspx).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

