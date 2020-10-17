---
title: 'Lync Server 2013: testar a capacidade dos usuários móveis de trocar mensagens instantâneas'
description: 'Lync Server 2013: testar a capacidade dos usuários móveis de trocar mensagens instantâneas.'
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
ms.openlocfilehash: 675bbeff93fed374d950b2efbdf15b4ea246f861
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48558287"
---
# <a name="test-mobile-users-ability-to-exchange-instant-messages-in-lync-server-2013"></a><span data-ttu-id="725cb-103">Testar a capacidade dos usuários móveis de trocar mensagens instantâneas no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="725cb-103">Test mobile users' ability to exchange instant messages in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="725cb-104">_**Última modificação do tópico:** 2014-06-07_</span><span class="sxs-lookup"><span data-stu-id="725cb-104">_**Topic Last Modified:** 2014-06-07_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="725cb-105">Agenda de verificação</span><span class="sxs-lookup"><span data-stu-id="725cb-105">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="725cb-106">Mensal</span><span class="sxs-lookup"><span data-stu-id="725cb-106">Monthly</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="725cb-107">Ferramenta de teste</span><span class="sxs-lookup"><span data-stu-id="725cb-107">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="725cb-108">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="725cb-108">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="725cb-109">Permissões obrigatórias</span><span class="sxs-lookup"><span data-stu-id="725cb-109">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="725cb-110">Ao executar localmente usando o Shell de gerenciamento do Lync Server, os usuários devem ser membros do grupo de segurança RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="725cb-110">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="725cb-111">Quando executado usando uma instância remota do Windows PowerShell, os usuários devem receber uma função RBAC que tenha permissão para executar o cmdlet Test-CsMcxP2PIM.</span><span class="sxs-lookup"><span data-stu-id="725cb-111">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsMcxP2PIM cmdlet.</span></span> <span data-ttu-id="725cb-112">Para ver uma lista de todas as funções RBAC que podem usar este cmdlet, execute o seguinte comando no prompt do Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="725cb-112">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsMcxP2PIM&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="725cb-113">Descrição</span><span class="sxs-lookup"><span data-stu-id="725cb-113">Description</span></span>

<span data-ttu-id="725cb-114">O serviço de mobilidade permite que os usuários de dispositivos móveis façam coisas como:</span><span class="sxs-lookup"><span data-stu-id="725cb-114">The Mobility Service enables mobile device users to do such things as:</span></span>

1.  <span data-ttu-id="725cb-115">Informações de presença e mensagens instantâneas do Exchange.</span><span class="sxs-lookup"><span data-stu-id="725cb-115">Exchange instant messages and presence information.</span></span>

2.  <span data-ttu-id="725cb-116">Armazenar e recuperar a caixa postal internamente em vez de com seu provedor sem fio.</span><span class="sxs-lookup"><span data-stu-id="725cb-116">Store and retrieve voice mail internally instead of with their wireless provider.</span></span>

3.  <span data-ttu-id="725cb-117">Aproveite os recursos do Lync Server, como ligar via trabalho e conferência discada.</span><span class="sxs-lookup"><span data-stu-id="725cb-117">Take advantage of Lync Server capabilities such as Call via Work and dial-out conferencing.</span></span>

<span data-ttu-id="725cb-118">O cmdlet Test-CsMxcP2PIM oferece uma maneira rápida e fácil de verificar se os usuários podem usar o serviço de mobilidade para trocar mensagens instantâneas.</span><span class="sxs-lookup"><span data-stu-id="725cb-118">The Test-CsMxcP2PIM cmdlet provides a quick and easy way to verify that users can use the Mobility Service to exchange instant messages.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="725cb-119">Executar o teste</span><span class="sxs-lookup"><span data-stu-id="725cb-119">Running the test</span></span>

<span data-ttu-id="725cb-120">Para executar esse teste, você deve criar dois objetos de credenciais do Windows PowerShell (objetos que contêm o nome da conta e a senha) para cada conta.</span><span class="sxs-lookup"><span data-stu-id="725cb-120">To run this test, you must create two Windows PowerShell credentials objects (objects that contain the account name and password) for each account.</span></span> <span data-ttu-id="725cb-121">Em seguida, você deve incluir esses objetos de credenciais e os endereços SIP das duas contas ao chamar Test-CsMcxP2PIM:</span><span class="sxs-lookup"><span data-stu-id="725cb-121">You must then include those credentials objects and the SIP addresses of the two accounts when you call Test-CsMcxP2PIM:</span></span>

    $credential1 = Get-Credential "litwareinc\kenmyer"
    $credential2 = Get-Credential "litwareinc\pilar"
    
    Test-CsMcxP2PIM -TargetFqdn "atl-cs-001.litwareinc.com" -Authentication Negotiate -SenderSipAddres "sip:kenmyer@litwareinc.com" -SenderCredential $credential1 -ReceiverSipAddress "sip:packerman@litwareinc.com" -ReceiverCredential $credential2

<span data-ttu-id="725cb-122">Para obter mais informações, consulte o tópico de ajuda para o cmdlet [Test-CsMcxP2PIM](https://docs.microsoft.com/powershell/module/skype/Test-CsMcxP2PIM) .</span><span class="sxs-lookup"><span data-stu-id="725cb-122">For more information, see the help topic for the [Test-CsMcxP2PIM](https://docs.microsoft.com/powershell/module/skype/Test-CsMcxP2PIM) cmdlet.</span></span>

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="725cb-123">Determinando o sucesso ou a falha</span><span class="sxs-lookup"><span data-stu-id="725cb-123">Determining success or failure</span></span>

<span data-ttu-id="725cb-124">Se os dois usuários de teste puderem trocar mensagens instantâneas usando o serviço de mobilidade, Test-CsMcxP2PIM retornará o êxito do resultado do teste:</span><span class="sxs-lookup"><span data-stu-id="725cb-124">If the two test users can exchange instant messages by using the mobility service then Test-CsMcxP2PIM will return test result Success:</span></span>

<span data-ttu-id="725cb-125">FQDN de destino: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="725cb-125">Target Fqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="725cb-126">URI de destino: http://atl-cs-001.litwareinc.com:443/mcx</span><span class="sxs-lookup"><span data-stu-id="725cb-126">Target Uri : http://atl-cs-001.litwareinc.com:443/mcx</span></span>

<span data-ttu-id="725cb-127">Resultado: êxito</span><span class="sxs-lookup"><span data-stu-id="725cb-127">Result : Success</span></span>

<span data-ttu-id="725cb-128">Latência: 00:00:00</span><span class="sxs-lookup"><span data-stu-id="725cb-128">Latency : 00:00:00</span></span>

<span data-ttu-id="725cb-129">Mensagem de erro:</span><span class="sxs-lookup"><span data-stu-id="725cb-129">Error Message :</span></span>

<span data-ttu-id="725cb-130">Diagnóstico</span><span class="sxs-lookup"><span data-stu-id="725cb-130">Diagnosis :</span></span>

<span data-ttu-id="725cb-131">Se o teste falhar, o resultado será definido como Failure e uma mensagem de erro detalhada e diagnóstico será exibido:</span><span class="sxs-lookup"><span data-stu-id="725cb-131">If the test fails then the Result will be set to Failure and a detailed error message and diagnosis will be displayed:</span></span>

<span data-ttu-id="725cb-132">FQDN de destino: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="725cb-132">Target Fqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="725cb-133">URI de destino: https://atl-cs-001.litwareinc.com:443/mcx</span><span class="sxs-lookup"><span data-stu-id="725cb-133">Target Uri : https://atl-cs-001.litwareinc.com:443/mcx</span></span>

<span data-ttu-id="725cb-134">Resultado: falha</span><span class="sxs-lookup"><span data-stu-id="725cb-134">Result : Failure</span></span>

<span data-ttu-id="725cb-135">Latência: 00:00:00</span><span class="sxs-lookup"><span data-stu-id="725cb-135">Latency : 00:00:00</span></span>

<span data-ttu-id="725cb-136">Mensagem de erro: nenhuma resposta recebida para o serviço de Web-Ticket.</span><span class="sxs-lookup"><span data-stu-id="725cb-136">Error Message : No response received for Web-Ticket service.</span></span>

<span data-ttu-id="725cb-137">Exceção interna: a solicitação HHTP não é autorizada com</span><span class="sxs-lookup"><span data-stu-id="725cb-137">Inner Exception:The HHTP request is unauthorized with</span></span>

<span data-ttu-id="725cb-138">esquema de negociação de cliente ' NTLM '.</span><span class="sxs-lookup"><span data-stu-id="725cb-138">client negotiation scheme 'Ntlm'.</span></span> <span data-ttu-id="725cb-139">A autenticação</span><span class="sxs-lookup"><span data-stu-id="725cb-139">The authentication</span></span>

<span data-ttu-id="725cb-140">o cabeçalho recebido do servidor era ' Negotiate, NTLM '.</span><span class="sxs-lookup"><span data-stu-id="725cb-140">header received from the server was 'Negotiate,NTLM'.</span></span>

<span data-ttu-id="725cb-141">Exceção interna: o servidor remoto retornou um erro:</span><span class="sxs-lookup"><span data-stu-id="725cb-141">Inner Exception:The remote server returned an error:</span></span>

<span data-ttu-id="725cb-142">(401) não autorizado.</span><span class="sxs-lookup"><span data-stu-id="725cb-142">(401) Unauthorized.</span></span>

<span data-ttu-id="725cb-143">Diagnóstico</span><span class="sxs-lookup"><span data-stu-id="725cb-143">Diagnosis :</span></span>

<span data-ttu-id="725cb-144">Diagnóstico interno: X-MS-Server-Fqdb: ATL-cs-</span><span class="sxs-lookup"><span data-stu-id="725cb-144">Inner Diagnosis:X-MS-server-Fqdb : atl-cs-</span></span>

<span data-ttu-id="725cb-145">001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="725cb-145">001.litwareinc.com</span></span>

<span data-ttu-id="725cb-146">Cache-Control: privada</span><span class="sxs-lookup"><span data-stu-id="725cb-146">Cache-Control : private</span></span>

<span data-ttu-id="725cb-147">Content-Type: text/html; charset = utf-8.</span><span class="sxs-lookup"><span data-stu-id="725cb-147">Content-Type : text/html; charset=utf-8.</span></span>

<span data-ttu-id="725cb-148">Servidor: Microsoft-IIS/8.5</span><span class="sxs-lookup"><span data-stu-id="725cb-148">Server : Microsoft-IIS/8.5</span></span>

<span data-ttu-id="725cb-149">WWW-Authenticate: negociar, NTLM</span><span class="sxs-lookup"><span data-stu-id="725cb-149">WWW-Authenticate : Negotiate,NTLM</span></span>

<span data-ttu-id="725cb-150">X-powered-by: ASP.NET</span><span class="sxs-lookup"><span data-stu-id="725cb-150">X-Powered-By : ASP.NET</span></span>

<span data-ttu-id="725cb-151">X-Content-Type-opções: nosniff</span><span class="sxs-lookup"><span data-stu-id="725cb-151">X-Content-Type-Options : nosniff</span></span>

<span data-ttu-id="725cb-152">Date: Qua, 28 de maio de 2014 19:16:05 GMT</span><span class="sxs-lookup"><span data-stu-id="725cb-152">Date : Wed, 28 May 2014 19:16:05 GMT</span></span>

<span data-ttu-id="725cb-153">Content-Length: 6305</span><span class="sxs-lookup"><span data-stu-id="725cb-153">Content-Length : 6305</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="725cb-154">Motivos pelos quais o teste pode ter falhado</span><span class="sxs-lookup"><span data-stu-id="725cb-154">Reasons why the test might have failed</span></span>

<span data-ttu-id="725cb-155">Se Test-CsMcxP2PIM falhar, a primeira etapa deve ser verificar se o serviço de mobilidade está ativo e em execução.</span><span class="sxs-lookup"><span data-stu-id="725cb-155">If Test-CsMcxP2PIM fails your first step should be to verify that the mobility service is up and running.</span></span> <span data-ttu-id="725cb-156">Isso pode ser feito usando um navegador da Web para verificar se a URL do serviço de mobilidade do seu pool do Lync Server pode ser acessada.</span><span class="sxs-lookup"><span data-stu-id="725cb-156">That can be done by using a web browser to verify that the mobility service URL for your Lync Server pool can be accessed.</span></span> <span data-ttu-id="725cb-157">Por exemplo, este comando verifica a URL para o pool atl-cs-001.litwareinc.com:</span><span class="sxs-lookup"><span data-stu-id="725cb-157">For example, this command verifies the URL for the pool atl-cs-001.litwareinc.com:</span></span>

    https://atl-cs-001.litwareinc.com/mcx/mcxservice.svc

<span data-ttu-id="725cb-158">Se o serviço de mobilidade parecer estar em execução, verifique se os dois usuários de teste possuem contas válidas do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="725cb-158">If the mobility service seems to be running then verify that your two test users have valid Lync Server accounts.</span></span> <span data-ttu-id="725cb-159">Você pode recuperar informações da conta usando um comando semelhante ao seguinte:</span><span class="sxs-lookup"><span data-stu-id="725cb-159">You can retrieve account information by using a command similar to this:</span></span>

    Get-CsUser -Identity "sip:kenmyer@litwareinc.com" | Select-Object Enabled

<span data-ttu-id="725cb-160">Se a propriedade Enabled não for igual a true ou se o comando falhar, isso significa que o usuário não tem uma conta válida do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="725cb-160">If the Enabled property is not equal to True or if the command fails, that means that the user does not have a valid Lync Server account.</span></span>

<span data-ttu-id="725cb-161">Você também deve verificar se o usuário está habilitado para mobilidade.</span><span class="sxs-lookup"><span data-stu-id="725cb-161">You should also verify that the user is enabled for mobility.</span></span> <span data-ttu-id="725cb-162">Para fazer isso, primeiro determine a política de mobilidade atribuída à conta:</span><span class="sxs-lookup"><span data-stu-id="725cb-162">To do that, first determine the mobility policy that is assigned to the account:</span></span>

    Get-CsUser -Identity "sip:kenmyer@litwareinc.com" | Select-Object MobilityPolicy

<span data-ttu-id="725cb-163">Após saber o nome da política, use o cmdlet Get-CsMobilityPolicy para verificar se a política em questão (por exemplo, Edmondmobilitypolicy) tem a propriedade EnableMobility definida como true:</span><span class="sxs-lookup"><span data-stu-id="725cb-163">After you know the policy name, use the Get-CsMobilityPolicy cmdlet to verify that the policy in question (for example, RedmondMobilityPolicy) has the EnableMobility property set to True:</span></span>

    Get-CsMobilityPolicy -Identity "RedmondMobilityPolicy"

<span data-ttu-id="725cb-164">Se você receber uma mensagem de erro com cabeçalhos de autenticação, isso geralmente significa que você não especificou uma conta de usuário válida.</span><span class="sxs-lookup"><span data-stu-id="725cb-164">If you receive an error message with authentication headers, that often means that you have not specified a valid user account.</span></span> <span data-ttu-id="725cb-165">Verifique o nome de usuário e a senha e tente o teste novamente.</span><span class="sxs-lookup"><span data-stu-id="725cb-165">Verify the user name and password and then try the test again.</span></span> <span data-ttu-id="725cb-166">Se você estiver convencido de que a conta de usuário é válida, use o cmdlet Get-CsWebServiceConfiguration e verifique o valor da Propriedade UseWindowsAuth.</span><span class="sxs-lookup"><span data-stu-id="725cb-166">If you are convinced that the user account is valid, then use the Get-CsWebServiceConfiguration cmdlet and check the value of the UseWindowsAuth property.</span></span> <span data-ttu-id="725cb-167">Isso indicará quais métodos de autenticação estão habilitados em sua organização. Para obter mais dicas sobre como solucionar problemas do serviço de mobilidade, consulte o blog post [Troubleshooting external Lync Mobility Connectivity issues passo a passo](https://blogs.technet.com/b/nexthop/archive/2012/02/21/troubleshooting-external-lync-mobility-connectivity-issues-step-by-step.aspx).</span><span class="sxs-lookup"><span data-stu-id="725cb-167">That will tell you which authentication methods are enabled in your organization.For more tips about how to troubleshoot the mobility service, see the blog post [Troubleshooting External Lync Mobility Connectivity Issues Step-by-Step](https://blogs.technet.com/b/nexthop/archive/2012/02/21/troubleshooting-external-lync-mobility-connectivity-issues-step-by-step.aspx).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

