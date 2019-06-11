---
title: 'Lync Server 2013: testar a capacidade dos usuários móveis de trocar mensagens instantâneas'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Test mobile users' ability to exchange instant messages
ms:assetid: a78a048f-d413-4bee-8626-d62b8b74f811
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn767950(v=OCS.15)
ms:contentKeyID: 63969638
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b7fd19f6ef2f4a44a61d56848b4bf845c79736ec
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34844695"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="test-mobile-users-ability-to-exchange-instant-messages-in-lync-server-2013"></a><span data-ttu-id="ff274-102">Testar a capacidade dos usuários móveis de trocar mensagens instantâneas no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ff274-102">Test mobile users' ability to exchange instant messages in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ff274-103">_**Tópico da última modificação:** 2014-06-07_</span><span class="sxs-lookup"><span data-stu-id="ff274-103">_**Topic Last Modified:** 2014-06-07_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ff274-104">Cronograma de verificação</span><span class="sxs-lookup"><span data-stu-id="ff274-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="ff274-105">Mensal</span><span class="sxs-lookup"><span data-stu-id="ff274-105">Monthly</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ff274-106">Ferramenta de teste</span><span class="sxs-lookup"><span data-stu-id="ff274-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="ff274-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="ff274-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ff274-108">Permissões necessárias</span><span class="sxs-lookup"><span data-stu-id="ff274-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="ff274-109">Quando executado localmente usando o Shell de gerenciamento do Lync Server, os usuários devem ser membros do grupo de segurança RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="ff274-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="ff274-110">Quando executado usando uma instância remota do Windows PowerShell, os usuários devem receber uma função RBAC que tenha permissão para executar o cmdlet Test-CsMcxP2PIM.</span><span class="sxs-lookup"><span data-stu-id="ff274-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsMcxP2PIM cmdlet.</span></span> <span data-ttu-id="ff274-111">Para ver uma lista de todas as funções RBAC que podem usar esse cmdlet, execute o seguinte comando no prompt do Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="ff274-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsMcxP2PIM&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="ff274-112">Descrição</span><span class="sxs-lookup"><span data-stu-id="ff274-112">Description</span></span>

<span data-ttu-id="ff274-113">O serviço de mobilidade permite que os usuários de dispositivos móveis executem itens como:</span><span class="sxs-lookup"><span data-stu-id="ff274-113">The Mobility Service enables mobile device users to do such things as:</span></span>

1.  <span data-ttu-id="ff274-114">Trocar mensagens instantâneas e informações de presença.</span><span class="sxs-lookup"><span data-stu-id="ff274-114">Exchange instant messages and presence information.</span></span>

2.  <span data-ttu-id="ff274-115">Armazene e recupere a caixa postal internamente em vez de usar o seu provedor sem fio.</span><span class="sxs-lookup"><span data-stu-id="ff274-115">Store and retrieve voice mail internally instead of with their wireless provider.</span></span>

3.  <span data-ttu-id="ff274-116">Aproveite os recursos do Lync Server, como chamada via trabalho e conferência discada.</span><span class="sxs-lookup"><span data-stu-id="ff274-116">Take advantage of Lync Server capabilities such as Call via Work and dial-out conferencing.</span></span>

<span data-ttu-id="ff274-117">O cmdlet Test-CsMxcP2PIM fornece uma maneira rápida e fácil de verificar se os usuários podem usar o serviço de mobilidade para trocar mensagens de chat.</span><span class="sxs-lookup"><span data-stu-id="ff274-117">The Test-CsMxcP2PIM cmdlet provides a quick and easy way to verify that users can use the Mobility Service to exchange instant messages.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="ff274-118">Executar o teste</span><span class="sxs-lookup"><span data-stu-id="ff274-118">Running the test</span></span>

<span data-ttu-id="ff274-119">Para executar esse teste, você deve criar dois objetos de credenciais do Windows PowerShell (objetos que contêm o nome e a senha da conta) para cada conta.</span><span class="sxs-lookup"><span data-stu-id="ff274-119">To run this test, you must create two Windows PowerShell credentials objects (objects that contain the account name and password) for each account.</span></span> <span data-ttu-id="ff274-120">Em seguida, você deve incluir esses objetos de credenciais e os endereços SIP das duas contas ao chamar Test-CsMcxP2PIM:</span><span class="sxs-lookup"><span data-stu-id="ff274-120">You must then include those credentials objects and the SIP addresses of the two accounts when you call Test-CsMcxP2PIM:</span></span>

    $credential1 = Get-Credential "litwareinc\kenmyer"
    $credential2 = Get-Credential "litwareinc\pilar"
    
    Test-CsMcxP2PIM -TargetFqdn "atl-cs-001.litwareinc.com" -Authentication Negotiate -SenderSipAddres "sip:kenmyer@litwareinc.com" -SenderCredential $credential1 -ReceiverSipAddress "sip:packerman@litwareinc.com" -ReceiverCredential $credential2

<span data-ttu-id="ff274-121">Para obter mais informações, consulte o tópico da ajuda para o cmdlet [Test-CsMcxP2PIM](https://docs.microsoft.com/powershell/module/skype/Test-CsMcxP2PIM) .</span><span class="sxs-lookup"><span data-stu-id="ff274-121">For more information, see the help topic for the [Test-CsMcxP2PIM](https://docs.microsoft.com/powershell/module/skype/Test-CsMcxP2PIM) cmdlet.</span></span>

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="ff274-122">Determinação do sucesso ou falha</span><span class="sxs-lookup"><span data-stu-id="ff274-122">Determining success or failure</span></span>

<span data-ttu-id="ff274-123">Se os dois usuários de teste puderem trocar mensagens de chat usando o serviço de mobilidade, o teste-CsMcxP2PIM retornará o êxito do resultado do teste:</span><span class="sxs-lookup"><span data-stu-id="ff274-123">If the two test users can exchange instant messages by using the mobility service then Test-CsMcxP2PIM will return test result Success:</span></span>

<span data-ttu-id="ff274-124">FQDN de destino: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="ff274-124">Target Fqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="ff274-125">URI de destino:http://atl-cs-001.litwareinc.com:443/mcx</span><span class="sxs-lookup"><span data-stu-id="ff274-125">Target Uri : http://atl-cs-001.litwareinc.com:443/mcx</span></span>

<span data-ttu-id="ff274-126">Resultado: êxito</span><span class="sxs-lookup"><span data-stu-id="ff274-126">Result : Success</span></span>

<span data-ttu-id="ff274-127">Latência: 00:00:00</span><span class="sxs-lookup"><span data-stu-id="ff274-127">Latency : 00:00:00</span></span>

<span data-ttu-id="ff274-128">Mensagem de erro:</span><span class="sxs-lookup"><span data-stu-id="ff274-128">Error Message :</span></span>

<span data-ttu-id="ff274-129">Correto</span><span class="sxs-lookup"><span data-stu-id="ff274-129">Diagnosis :</span></span>

<span data-ttu-id="ff274-130">Se o teste falhar, o resultado será definido como Failure e uma mensagem de erro detalhada e o diagnóstico serão exibidos:</span><span class="sxs-lookup"><span data-stu-id="ff274-130">If the test fails then the Result will be set to Failure and a detailed error message and diagnosis will be displayed:</span></span>

<span data-ttu-id="ff274-131">FQDN de destino: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="ff274-131">Target Fqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="ff274-132">URI de destino:https://atl-cs-001.litwareinc.com:443/mcx</span><span class="sxs-lookup"><span data-stu-id="ff274-132">Target Uri : https://atl-cs-001.litwareinc.com:443/mcx</span></span>

<span data-ttu-id="ff274-133">Resultado: falha</span><span class="sxs-lookup"><span data-stu-id="ff274-133">Result : Failure</span></span>

<span data-ttu-id="ff274-134">Latência: 00:00:00</span><span class="sxs-lookup"><span data-stu-id="ff274-134">Latency : 00:00:00</span></span>

<span data-ttu-id="ff274-135">Mensagem de erro: nenhuma resposta recebida para o serviço de tíquete na Web.</span><span class="sxs-lookup"><span data-stu-id="ff274-135">Error Message : No response received for Web-Ticket service.</span></span>

<span data-ttu-id="ff274-136">Exceção interna: a solicitação HHTP está não autorizada com</span><span class="sxs-lookup"><span data-stu-id="ff274-136">Inner Exception:The HHTP request is unauthorized with</span></span>

<span data-ttu-id="ff274-137">esquema de negociação do cliente ' NTLM '.</span><span class="sxs-lookup"><span data-stu-id="ff274-137">client negotiation scheme 'Ntlm'.</span></span> <span data-ttu-id="ff274-138">A autenticação</span><span class="sxs-lookup"><span data-stu-id="ff274-138">The authentication</span></span>

<span data-ttu-id="ff274-139">o cabeçalho recebido do servidor era ' Negotiate, NTLM '.</span><span class="sxs-lookup"><span data-stu-id="ff274-139">header received from the server was 'Negotiate,NTLM'.</span></span>

<span data-ttu-id="ff274-140">Exceção interna: o servidor remoto retornou um erro:</span><span class="sxs-lookup"><span data-stu-id="ff274-140">Inner Exception:The remote server returned an error:</span></span>

<span data-ttu-id="ff274-141">(401) não autorizado.</span><span class="sxs-lookup"><span data-stu-id="ff274-141">(401) Unauthorized.</span></span>

<span data-ttu-id="ff274-142">Correto</span><span class="sxs-lookup"><span data-stu-id="ff274-142">Diagnosis :</span></span>

<span data-ttu-id="ff274-143">Diagnóstico interno: X-MS-Server-Fqdb: ATL-cs-</span><span class="sxs-lookup"><span data-stu-id="ff274-143">Inner Diagnosis:X-MS-server-Fqdb : atl-cs-</span></span>

<span data-ttu-id="ff274-144">001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="ff274-144">001.litwareinc.com</span></span>

<span data-ttu-id="ff274-145">Cache-Control: Private</span><span class="sxs-lookup"><span data-stu-id="ff274-145">Cache-Control : private</span></span>

<span data-ttu-id="ff274-146">Tipo de conteúdo: texto/HTML; charset = utf-8.</span><span class="sxs-lookup"><span data-stu-id="ff274-146">Content-Type : text/html; charset=utf-8.</span></span>

<span data-ttu-id="ff274-147">Servidor: Microsoft-IIS/8.5</span><span class="sxs-lookup"><span data-stu-id="ff274-147">Server : Microsoft-IIS/8.5</span></span>

<span data-ttu-id="ff274-148">WWW-Authenticate: Negotiate, NTLM</span><span class="sxs-lookup"><span data-stu-id="ff274-148">WWW-Authenticate : Negotiate,NTLM</span></span>

<span data-ttu-id="ff274-149">X-ativado por: ASP.NET</span><span class="sxs-lookup"><span data-stu-id="ff274-149">X-Powered-By : ASP.NET</span></span>

<span data-ttu-id="ff274-150">X-tipo de conteúdo-opções: nofarejador</span><span class="sxs-lookup"><span data-stu-id="ff274-150">X-Content-Type-Options : nosniff</span></span>

<span data-ttu-id="ff274-151">Data: quarta-feira, 28 de maio de 2014 19:16:05 GMT</span><span class="sxs-lookup"><span data-stu-id="ff274-151">Date : Wed, 28 May 2014 19:16:05 GMT</span></span>

<span data-ttu-id="ff274-152">Content-Length: 6305</span><span class="sxs-lookup"><span data-stu-id="ff274-152">Content-Length : 6305</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="ff274-153">Motivos pelos quais o teste pode ter falhado</span><span class="sxs-lookup"><span data-stu-id="ff274-153">Reasons why the test might have failed</span></span>

<span data-ttu-id="ff274-154">Se Test-CsMcxP2PIM falhar, seu primeiro passo deve ser verificar se o serviço de mobilidade está ativo e em execução.</span><span class="sxs-lookup"><span data-stu-id="ff274-154">If Test-CsMcxP2PIM fails your first step should be to verify that the mobility service is up and running.</span></span> <span data-ttu-id="ff274-155">Isso pode ser feito usando um navegador da Web para verificar se a URL do serviço de mobilidade do seu pool do Lync Server pode ser acessada.</span><span class="sxs-lookup"><span data-stu-id="ff274-155">That can be done by using a web browser to verify that the mobility service URL for your Lync Server pool can be accessed.</span></span> <span data-ttu-id="ff274-156">Por exemplo, esse comando verifica a URL para o conjunto de atl-cs-001.litwareinc.com:</span><span class="sxs-lookup"><span data-stu-id="ff274-156">For example, this command verifies the URL for the pool atl-cs-001.litwareinc.com:</span></span>

    https://atl-cs-001.litwareinc.com/mcx/mcxservice.svc

<span data-ttu-id="ff274-157">Se o serviço de mobilidade parecer estar em execução, verifique se os dois usuários de teste têm contas válidas do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="ff274-157">If the mobility service seems to be running then verify that your two test users have valid Lync Server accounts.</span></span> <span data-ttu-id="ff274-158">Você pode recuperar informações da conta usando um comando semelhante a este:</span><span class="sxs-lookup"><span data-stu-id="ff274-158">You can retrieve account information by using a command similar to this:</span></span>

    Get-CsUser -Identity "sip:kenmyer@litwareinc.com" | Select-Object Enabled

<span data-ttu-id="ff274-159">Se a propriedade Enabled não for igual a true ou se o comando falhar, isso significará que o usuário não tem uma conta válida do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="ff274-159">If the Enabled property is not equal to True or if the command fails, that means that the user does not have a valid Lync Server account.</span></span>

<span data-ttu-id="ff274-160">Você também deve verificar se o usuário está habilitado para mobilidade.</span><span class="sxs-lookup"><span data-stu-id="ff274-160">You should also verify that the user is enabled for mobility.</span></span> <span data-ttu-id="ff274-161">Para isso, primeiro determine a política de mobilidade atribuída à conta:</span><span class="sxs-lookup"><span data-stu-id="ff274-161">To do that, first determine the mobility policy that is assigned to the account:</span></span>

    Get-CsUser -Identity "sip:kenmyer@litwareinc.com" | Select-Object MobilityPolicy

<span data-ttu-id="ff274-162">Depois de saber o nome da política, use o cmdlet Get-CsMobilityPolicy para verificar se a política em questão (por exemplo, RedmondMobilityPolicy) tem a propriedade EnableMobility definida como true:</span><span class="sxs-lookup"><span data-stu-id="ff274-162">After you know the policy name, use the Get-CsMobilityPolicy cmdlet to verify that the policy in question (for example, RedmondMobilityPolicy) has the EnableMobility property set to True:</span></span>

    Get-CsMobilityPolicy -Identity "RedmondMobilityPolicy"

<span data-ttu-id="ff274-163">Se você receber uma mensagem de erro com cabeçalhos de autenticação, isso geralmente significa que você não especificou uma conta de usuário válida.</span><span class="sxs-lookup"><span data-stu-id="ff274-163">If you receive an error message with authentication headers, that often means that you have not specified a valid user account.</span></span> <span data-ttu-id="ff274-164">Verifique o nome de usuário e a senha e tente testar novamente.</span><span class="sxs-lookup"><span data-stu-id="ff274-164">Verify the user name and password and then try the test again.</span></span> <span data-ttu-id="ff274-165">Se você estiver convencido de que a conta de usuário é válida, use o cmdlet Get-CsWebServiceConfiguration e verifique o valor da Propriedade UseWindowsAuth.</span><span class="sxs-lookup"><span data-stu-id="ff274-165">If you are convinced that the user account is valid, then use the Get-CsWebServiceConfiguration cmdlet and check the value of the UseWindowsAuth property.</span></span> <span data-ttu-id="ff274-166">Isso indicará quais métodos de autenticação estão habilitados em sua organização. Para obter mais dicas sobre como solucionar problemas com o serviço de mobilidade, confira a [solução de problemas de solução de problemas de conectividade externa do Lync Mobility passo a passo](http://blogs.technet.com/b/nexthop/archive/2012/02/21/troubleshooting-external-lync-mobility-connectivity-issues-step-by-step.aspx).</span><span class="sxs-lookup"><span data-stu-id="ff274-166">That will tell you which authentication methods are enabled in your organization.For more tips about how to troubleshoot the mobility service, see the blog post [Troubleshooting External Lync Mobility Connectivity Issues Step-by-Step](http://blogs.technet.com/b/nexthop/archive/2012/02/21/troubleshooting-external-lync-mobility-connectivity-issues-step-by-step.aspx).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

