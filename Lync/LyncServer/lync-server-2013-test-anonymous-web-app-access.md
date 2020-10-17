---
title: 'Lync Server 2013: testar acesso anônimo ao aplicativo Web'
description: 'Lync Server 2013: testar acesso anônimo ao aplicativo Web.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Test anonymous Web App access
ms:assetid: 92f691cd-e05e-4bab-beb5-251d4b837a19
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn767949(v=OCS.15)
ms:contentKeyID: 63969630
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 11c33840912fefcaeef069e14773cfefd0834a8b
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48547467"
---
# <a name="test-anonymous-web-app-access-in-lync-server-2013"></a><span data-ttu-id="ec05b-103">Testar o acesso ao aplicativo Web anônimo no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ec05b-103">Test anonymous Web App access in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ec05b-104">_**Última modificação do tópico:** 2014-06-07_</span><span class="sxs-lookup"><span data-stu-id="ec05b-104">_**Topic Last Modified:** 2014-06-07_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ec05b-105">Agenda de verificação</span><span class="sxs-lookup"><span data-stu-id="ec05b-105">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="ec05b-106">Mensal</span><span class="sxs-lookup"><span data-stu-id="ec05b-106">Monthly</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ec05b-107">Ferramenta de teste</span><span class="sxs-lookup"><span data-stu-id="ec05b-107">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="ec05b-108">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="ec05b-108">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ec05b-109">Permissões obrigatórias</span><span class="sxs-lookup"><span data-stu-id="ec05b-109">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="ec05b-110">Ao executar localmente usando o Shell de gerenciamento do Lync Server, os usuários devem ser membros do grupo de segurança RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="ec05b-110">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="ec05b-111">Quando executado usando uma instância remota do Windows PowerShell, os usuários devem receber uma função RBAC que tenha permissão para executar o cmdlet Test-CsWebAppAnonymous.</span><span class="sxs-lookup"><span data-stu-id="ec05b-111">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsWebAppAnonymous cmdlet.</span></span> <span data-ttu-id="ec05b-112">Para ver uma lista de todas as funções RBAC que podem usar este cmdlet, execute o seguinte comando no prompt do Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="ec05b-112">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsWebAppAnonymous&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="ec05b-113">Descrição</span><span class="sxs-lookup"><span data-stu-id="ec05b-113">Description</span></span>

<span data-ttu-id="ec05b-114">O cmdlet Test-CsWebAppAnonymous verifica se um usuário anônimo pode ingressar em conferências do Lync Server usando o Lync Web App.</span><span class="sxs-lookup"><span data-stu-id="ec05b-114">The Test-CsWebAppAnonymous cmdlet verifies that an anonymous user can join Lync Server conferences by using the Lync Web App.</span></span> <span data-ttu-id="ec05b-115">Quando você executa o cmdlet, Test-CsWebAppAnonymous contata o serviço de tíquete da Web para obter uma permissão da Web para o usuário anônimo.</span><span class="sxs-lookup"><span data-stu-id="ec05b-115">When you run the cmdlet, Test-CsWebAppAnonymous contacts the Web Ticket service to obtain a web ticket for the anonymous user.</span></span> <span data-ttu-id="ec05b-116">Se o cmdlet for bem-sucedido para obter esse tíquete, Test-CsWebAppAnonymous entrará em contato com o Lync Server e tentará estabelecer conferências separadas para mensagens instantâneas, compartilhamento de aplicativos e colaboração de dados.</span><span class="sxs-lookup"><span data-stu-id="ec05b-116">If the cmdlet succeeds in obtaining this ticket, Test-CsWebAppAnonymous will then contact Lync Server and attempt to establish separate conferences for instant messaging, application sharing, and data collaboration.</span></span>

<span data-ttu-id="ec05b-117">Observe que Test-CsWebAppAnonymous verifica apenas as APIs e conexões usadas para criar essas conferências.</span><span class="sxs-lookup"><span data-stu-id="ec05b-117">Note that Test-CsWebAppAnonymous only verifies the APIs and connections used to create these conferences.</span></span> <span data-ttu-id="ec05b-118">Na verdade, o cmdlet não cria e conduz qualquer conferência.</span><span class="sxs-lookup"><span data-stu-id="ec05b-118">The cmdlet does not actually create and conduct any conferences.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="ec05b-119">Executar o teste</span><span class="sxs-lookup"><span data-stu-id="ec05b-119">Running the test</span></span>

<span data-ttu-id="ec05b-120">O cmdlet Test-CsWebAppAnonymous pode ser executado usando um par de contas de teste pré-configuradas ou as contas de dois usuários que estão habilitados para o Lync Server.</span><span class="sxs-lookup"><span data-stu-id="ec05b-120">The Test-CsWebAppAnonymous cmdlet can be run using either a pair of preconfigured test accounts or the accounts of any two users who are enabled for Lync Server.</span></span> <span data-ttu-id="ec05b-121">Para executar esta verificação usando contas de teste, basta especificar o nome de domínio totalmente qualificado do pool do Lync Server que está sendo testado.</span><span class="sxs-lookup"><span data-stu-id="ec05b-121">To run this check using test accounts, you just have to specify the fully qualified domain name of the Lync Server pool being tested.</span></span> <span data-ttu-id="ec05b-122">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="ec05b-122">For example:</span></span>

    Test-CsWebAppAnonymous -TargetFqdn atl-cs-001.litwareinc.com

<span data-ttu-id="ec05b-123">Para executar essa verificação usando contas de usuário reais, você deve criar dois objetos de credenciais do Shell de gerenciamento do Lync Server (objetos que contêm o nome da conta e a senha) para cada conta.</span><span class="sxs-lookup"><span data-stu-id="ec05b-123">To run this check using actual user accounts, you must create two Lync Server Management Shell credentials objects (objects that contain the account name and password) for each account.</span></span> <span data-ttu-id="ec05b-124">Em seguida, você deve incluir esses objetos de credenciais e os endereços SIP das duas contas ao chamar Test-CsWebAppAnonymous:</span><span class="sxs-lookup"><span data-stu-id="ec05b-124">You must then include those credentials objects and the SIP addresses of the two accounts when you call Test-CsWebAppAnonymous:</span></span>

    $cred1 = Get-Credential "litwareinc\kenmyer"
    
    Test-CsWebApp -TargetFqdn atl-cs-001.litwareinc.com -UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $cred1

<span data-ttu-id="ec05b-125">Para obter mais informações, consulte o tópico de ajuda para o cmdlet Test-CsWebAppAnonymous.</span><span class="sxs-lookup"><span data-stu-id="ec05b-125">For more information, see the help topic for the Test-CsWebAppAnonymous cmdlet.</span></span> <span data-ttu-id="ec05b-126">Observe que Test-CsWebAppAnonymous é preterida para uso no Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="ec05b-126">Note that Test-CsWebAppAnonymous is deprecated for use on Lync Server 2013.</span></span>

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="ec05b-127">Determinando o sucesso ou a falha</span><span class="sxs-lookup"><span data-stu-id="ec05b-127">Determining success or failure</span></span>

<span data-ttu-id="ec05b-128">Se Test-CsWebAppAnonymous puder ingressar o usuário anônimo em suas conferências, o cmdlet retornará o resultado de teste bem-sucedido:</span><span class="sxs-lookup"><span data-stu-id="ec05b-128">If Test-CsWebAppAnonymous can join the anonymous user to his or her conferences, the cmdlet will return the test result Success:</span></span>

<span data-ttu-id="ec05b-129">FQDN de destino:</span><span class="sxs-lookup"><span data-stu-id="ec05b-129">Target Fqdn :</span></span>

<span data-ttu-id="ec05b-130">Resultado: êxito</span><span class="sxs-lookup"><span data-stu-id="ec05b-130">Result : Success</span></span>

<span data-ttu-id="ec05b-131">Latência: 00:00:00</span><span class="sxs-lookup"><span data-stu-id="ec05b-131">Latency : 00:00:00</span></span>

<span data-ttu-id="ec05b-132">Mensagem de erro:</span><span class="sxs-lookup"><span data-stu-id="ec05b-132">Error Message :</span></span>

<span data-ttu-id="ec05b-133">Diagnóstico</span><span class="sxs-lookup"><span data-stu-id="ec05b-133">Diagnosis :</span></span>

<span data-ttu-id="ec05b-134">Se o usuário anônimo não puder participar das conferências necessárias, o resultado do teste será marcado como falha.</span><span class="sxs-lookup"><span data-stu-id="ec05b-134">If the anonymous user can't join the necessary conferences then the test result will be marked as Failure.</span></span> <span data-ttu-id="ec05b-135">Normalmente Test-CsWebAppAnonymous também relatará uma mensagem de erro detalhada e o diagnóstico:</span><span class="sxs-lookup"><span data-stu-id="ec05b-135">Typically Test-CsWebAppAnonymous will also report back a detailed error message and diagnosis:</span></span>

<span data-ttu-id="ec05b-136">FQDN de destino: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="ec05b-136">Target Fqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="ec05b-137">Resultado: falha</span><span class="sxs-lookup"><span data-stu-id="ec05b-137">Result : Failure</span></span>

<span data-ttu-id="ec05b-138">Latência: 00:00:05.9746266</span><span class="sxs-lookup"><span data-stu-id="ec05b-138">Latency : 00:00:05.9746266</span></span>

<span data-ttu-id="ec05b-139">Mensagem de erro: nenhuma resposta recebida para o serviço de Web-Ticket</span><span class="sxs-lookup"><span data-stu-id="ec05b-139">Error Message : No response received for Web-Ticket service</span></span>

<span data-ttu-id="ec05b-140">Diagnóstico: a solicitação HTTP não é autorizada com o cliente</span><span class="sxs-lookup"><span data-stu-id="ec05b-140">Diagnosis : The HTTP request is unauthorized with client</span></span>

<span data-ttu-id="ec05b-141">esquema de autenticação ' NTLM '.</span><span class="sxs-lookup"><span data-stu-id="ec05b-141">authentication scheme 'Ntlm'.</span></span> <span data-ttu-id="ec05b-142">A autenticação</span><span class="sxs-lookup"><span data-stu-id="ec05b-142">The authentication</span></span>

<span data-ttu-id="ec05b-143">o cabeçalho recebido do servidor era ' Negotiate, NTLM '.</span><span class="sxs-lookup"><span data-stu-id="ec05b-143">header received from the server was 'Negotiate,NTLM'.</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="ec05b-144">Motivos pelos quais o teste pode ter falhado</span><span class="sxs-lookup"><span data-stu-id="ec05b-144">Reasons why the test might have failed</span></span>

<span data-ttu-id="ec05b-145">As falhas de Test-CsWebAppAnonymous geralmente giram em torno de erros de autenticação do usuário: você deve executar o teste usando uma conta de usuário válida, mesmo que o cmdlet esteja verificando a capacidade de um usuário anônimo se conectar ao Lync Server.</span><span class="sxs-lookup"><span data-stu-id="ec05b-145">Test-CsWebAppAnonymous failures usually revolve around user authentication errors: you must run the test using a valid user account even though the cmdlet is checking the ability of an anonymous user to connect to Lync Server.</span></span> <span data-ttu-id="ec05b-146">Se Test-CsWebAppAnonymous falhar, verifique se o usuário especificado tem uma conta de usuário do Lync Server válida.</span><span class="sxs-lookup"><span data-stu-id="ec05b-146">If Test-CsWebAppAnonymous fails, you should verify that the specified user has valid a Lync Server user account.</span></span> <span data-ttu-id="ec05b-147">Você pode recuperar informações da conta do Lync Server usando um comando semelhante a este:</span><span class="sxs-lookup"><span data-stu-id="ec05b-147">You can retrieve Lync Server account information by using a command similar to this:</span></span>

    Get-CsUser -Identity "sip:kenmyer@litwareinc.com" | Select-Object Enabled

<span data-ttu-id="ec05b-148">Se a propriedade Enabled não for igual a true ou se o comando falhar, isso significa que o usuário não tem uma conta válida do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="ec05b-148">If the Enabled property is not equal to True or if the command fails, that means that the user does not have a valid Lync Server account.</span></span>

<span data-ttu-id="ec05b-149">Você também deve verificar se a senha que você forneceu ao executar o cmdlet é uma senha válida.</span><span class="sxs-lookup"><span data-stu-id="ec05b-149">You should also verify that the password that you supplied when you run the cmdlet is a valid password.</span></span>

<span data-ttu-id="ec05b-150">Problemas de configuração com o servidor do Office Web Apps também podem causar falhas no Test-CsWebAppAnonymous; Isso geralmente será o caso se você receber o seguinte diagnóstico:</span><span class="sxs-lookup"><span data-stu-id="ec05b-150">Configuration problems with Office Web Apps Server can also cause Test-CsWebAppAnonymous to fail; that will often be the case if you receive the following diagnosis:</span></span>

<span data-ttu-id="ec05b-151">A solicitação HTTP não é autorizada com o esquema de autenticação de cliente ' NTLM '.</span><span class="sxs-lookup"><span data-stu-id="ec05b-151">The HTTP request is unauthorized with client authentication scheme 'Ntlm'.</span></span> <span data-ttu-id="ec05b-152">O cabeçalho de autenticação recebido do servidor era ' Negotiate, NTLM '.</span><span class="sxs-lookup"><span data-stu-id="ec05b-152">The authentication header received from the server was 'Negotiate,NTLM'.</span></span>

<span data-ttu-id="ec05b-153">Para obter mais informações sobre como diagnosticar e resolver problemas do servidor do Office Web Apps, consulte o blog post [Office Web Apps server 2013-as máquinas são sempre relatadas como não íntegras](http://www.wictorwilen.se/office-web-apps-server-2013---machines-are-always-reported-as-unhealthy).</span><span class="sxs-lookup"><span data-stu-id="ec05b-153">For more information on diagnosing and resolving Office Web Apps Server problems see the blog post [Office Web Apps Server 2013 - machines are always reported as Unhealthy](http://www.wictorwilen.se/office-web-apps-server-2013---machines-are-always-reported-as-unhealthy).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

