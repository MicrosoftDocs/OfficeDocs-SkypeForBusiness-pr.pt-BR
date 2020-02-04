---
title: 'Lync Server 2013: testar o acesso anônimo ao aplicativo Web'
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
ms.openlocfilehash: 8aabac9e106c325b7b1b964e6e594bb2b05ef85c
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41746261"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="test-anonymous-web-app-access-in-lync-server-2013"></a><span data-ttu-id="96286-102">Testar o acesso anônimo ao aplicativo Web no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="96286-102">Test anonymous Web App access in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="96286-103">_**Tópico da última modificação:** 2014-06-07_</span><span class="sxs-lookup"><span data-stu-id="96286-103">_**Topic Last Modified:** 2014-06-07_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="96286-104">Cronograma de verificação</span><span class="sxs-lookup"><span data-stu-id="96286-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="96286-105">Mensal</span><span class="sxs-lookup"><span data-stu-id="96286-105">Monthly</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="96286-106">Ferramenta de teste</span><span class="sxs-lookup"><span data-stu-id="96286-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="96286-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="96286-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="96286-108">Permissões necessárias</span><span class="sxs-lookup"><span data-stu-id="96286-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="96286-109">Quando executado localmente usando o Shell de gerenciamento do Lync Server, os usuários devem ser membros do grupo de segurança RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="96286-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="96286-110">Quando executado usando uma instância remota do Windows PowerShell, os usuários devem receber uma função RBAC que tenha permissão para executar o cmdlet Test-CsWebAppAnonymous.</span><span class="sxs-lookup"><span data-stu-id="96286-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsWebAppAnonymous cmdlet.</span></span> <span data-ttu-id="96286-111">Para ver uma lista de todas as funções RBAC que podem usar esse cmdlet, execute o seguinte comando no prompt do Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="96286-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsWebAppAnonymous&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="96286-112">Descrição</span><span class="sxs-lookup"><span data-stu-id="96286-112">Description</span></span>

<span data-ttu-id="96286-113">O cmdlet Test-CsWebAppAnonymous verifica se um usuário anônimo pode ingressar em conferências do Lync Server usando o Lync Web App.</span><span class="sxs-lookup"><span data-stu-id="96286-113">The Test-CsWebAppAnonymous cmdlet verifies that an anonymous user can join Lync Server conferences by using the Lync Web App.</span></span> <span data-ttu-id="96286-114">Quando você executa o cmdlet, Test-CsWebAppAnonymous contata o serviço de tíquete da Web para obter uma permissão da Web para o usuário anônimo.</span><span class="sxs-lookup"><span data-stu-id="96286-114">When you run the cmdlet, Test-CsWebAppAnonymous contacts the Web Ticket service to obtain a web ticket for the anonymous user.</span></span> <span data-ttu-id="96286-115">Se o cmdlet conseguir obter esse bilhete, o Test-CsWebAppAnonymous entrará em contato com o Lync Server e tentará estabelecer conferências separadas para mensagens instantâneas, compartilhamento de aplicativos e colaboração de dados.</span><span class="sxs-lookup"><span data-stu-id="96286-115">If the cmdlet succeeds in obtaining this ticket, Test-CsWebAppAnonymous will then contact Lync Server and attempt to establish separate conferences for instant messaging, application sharing, and data collaboration.</span></span>

<span data-ttu-id="96286-116">Observe que Test-CsWebAppAnonymous somente verifica as APIs e conexões usadas para criar essas conferências.</span><span class="sxs-lookup"><span data-stu-id="96286-116">Note that Test-CsWebAppAnonymous only verifies the APIs and connections used to create these conferences.</span></span> <span data-ttu-id="96286-117">Na verdade, o cmdlet não cria e realiza conferências.</span><span class="sxs-lookup"><span data-stu-id="96286-117">The cmdlet does not actually create and conduct any conferences.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="96286-118">Executar o teste</span><span class="sxs-lookup"><span data-stu-id="96286-118">Running the test</span></span>

<span data-ttu-id="96286-119">O cmdlet Test-CsWebAppAnonymous pode ser executado usando um par de contas de teste pré-configuradas ou as contas de qualquer um dos dois usuários habilitados para o Lync Server.</span><span class="sxs-lookup"><span data-stu-id="96286-119">The Test-CsWebAppAnonymous cmdlet can be run using either a pair of preconfigured test accounts or the accounts of any two users who are enabled for Lync Server.</span></span> <span data-ttu-id="96286-120">Para executar essa verificação usando contas de teste, basta especificar o nome de domínio totalmente qualificado do pool do servidor do Lync que está sendo testado.</span><span class="sxs-lookup"><span data-stu-id="96286-120">To run this check using test accounts, you just have to specify the fully qualified domain name of the Lync Server pool being tested.</span></span> <span data-ttu-id="96286-121">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="96286-121">For example:</span></span>

    Test-CsWebAppAnonymous -TargetFqdn atl-cs-001.litwareinc.com

<span data-ttu-id="96286-122">Para executar essa verificação usando contas de usuário reais, você deve criar dois objetos de credenciais do Shell de gerenciamento do Lync Server (objetos que contêm o nome e a senha da conta) para cada conta.</span><span class="sxs-lookup"><span data-stu-id="96286-122">To run this check using actual user accounts, you must create two Lync Server Management Shell credentials objects (objects that contain the account name and password) for each account.</span></span> <span data-ttu-id="96286-123">Em seguida, você deve incluir esses objetos de credenciais e os endereços SIP das duas contas ao chamar Test-CsWebAppAnonymous:</span><span class="sxs-lookup"><span data-stu-id="96286-123">You must then include those credentials objects and the SIP addresses of the two accounts when you call Test-CsWebAppAnonymous:</span></span>

    $cred1 = Get-Credential "litwareinc\kenmyer"
    
    Test-CsWebApp -TargetFqdn atl-cs-001.litwareinc.com -UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $cred1

<span data-ttu-id="96286-124">Para obter mais informações, consulte o tópico da ajuda para o cmdlet Test-CsWebAppAnonymous.</span><span class="sxs-lookup"><span data-stu-id="96286-124">For more information, see the help topic for the Test-CsWebAppAnonymous cmdlet.</span></span> <span data-ttu-id="96286-125">Observe que Test-CsWebAppAnonymous é preterido para uso no Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="96286-125">Note that Test-CsWebAppAnonymous is deprecated for use on Lync Server 2013.</span></span>

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="96286-126">Determinação do sucesso ou falha</span><span class="sxs-lookup"><span data-stu-id="96286-126">Determining success or failure</span></span>

<span data-ttu-id="96286-127">Se Test-CsWebAppAnonymous puder participar do usuário anônimo em suas conferências, o cmdlet retornará o resultado do teste Success:</span><span class="sxs-lookup"><span data-stu-id="96286-127">If Test-CsWebAppAnonymous can join the anonymous user to his or her conferences, the cmdlet will return the test result Success:</span></span>

<span data-ttu-id="96286-128">FQDN de destino:</span><span class="sxs-lookup"><span data-stu-id="96286-128">Target Fqdn :</span></span>

<span data-ttu-id="96286-129">Resultado: êxito</span><span class="sxs-lookup"><span data-stu-id="96286-129">Result : Success</span></span>

<span data-ttu-id="96286-130">Latência: 00:00:00</span><span class="sxs-lookup"><span data-stu-id="96286-130">Latency : 00:00:00</span></span>

<span data-ttu-id="96286-131">Mensagem de erro:</span><span class="sxs-lookup"><span data-stu-id="96286-131">Error Message :</span></span>

<span data-ttu-id="96286-132">Correto</span><span class="sxs-lookup"><span data-stu-id="96286-132">Diagnosis :</span></span>

<span data-ttu-id="96286-133">Se o usuário anônimo não puder ingressar nas conferências necessárias, o resultado do teste será marcado como uma falha.</span><span class="sxs-lookup"><span data-stu-id="96286-133">If the anonymous user can't join the necessary conferences then the test result will be marked as Failure.</span></span> <span data-ttu-id="96286-134">Geralmente Test-CsWebAppAnonymous também reportará uma mensagem de erro e um diagnóstico detalhados:</span><span class="sxs-lookup"><span data-stu-id="96286-134">Typically Test-CsWebAppAnonymous will also report back a detailed error message and diagnosis:</span></span>

<span data-ttu-id="96286-135">FQDN de destino: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="96286-135">Target Fqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="96286-136">Resultado: falha</span><span class="sxs-lookup"><span data-stu-id="96286-136">Result : Failure</span></span>

<span data-ttu-id="96286-137">Latência: 00:00:05.9746266</span><span class="sxs-lookup"><span data-stu-id="96286-137">Latency : 00:00:05.9746266</span></span>

<span data-ttu-id="96286-138">Mensagem de erro: nenhuma resposta recebida para o serviço Web-ticket</span><span class="sxs-lookup"><span data-stu-id="96286-138">Error Message : No response received for Web-Ticket service</span></span>

<span data-ttu-id="96286-139">Diagnóstico: a solicitação de HTTP está não autorizada com o cliente</span><span class="sxs-lookup"><span data-stu-id="96286-139">Diagnosis : The HTTP request is unauthorized with client</span></span>

<span data-ttu-id="96286-140">esquema de autenticação ' NTLM '.</span><span class="sxs-lookup"><span data-stu-id="96286-140">authentication scheme 'Ntlm'.</span></span> <span data-ttu-id="96286-141">A autenticação</span><span class="sxs-lookup"><span data-stu-id="96286-141">The authentication</span></span>

<span data-ttu-id="96286-142">o cabeçalho recebido do servidor era ' Negotiate, NTLM '.</span><span class="sxs-lookup"><span data-stu-id="96286-142">header received from the server was 'Negotiate,NTLM'.</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="96286-143">Motivos pelos quais o teste pode ter falhado</span><span class="sxs-lookup"><span data-stu-id="96286-143">Reasons why the test might have failed</span></span>

<span data-ttu-id="96286-144">Falhas de teste-CsWebAppAnonymous geralmente giram em torno de erros de autenticação do usuário: você deve executar o teste usando uma conta de usuário válida, embora o cmdlet esteja verificando a capacidade de um usuário anônimo se conectar ao Lync Server.</span><span class="sxs-lookup"><span data-stu-id="96286-144">Test-CsWebAppAnonymous failures usually revolve around user authentication errors: you must run the test using a valid user account even though the cmdlet is checking the ability of an anonymous user to connect to Lync Server.</span></span> <span data-ttu-id="96286-145">Se Test-CsWebAppAnonymous falhar, você deve verificar se o usuário especificado tem uma conta de usuário válida do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="96286-145">If Test-CsWebAppAnonymous fails, you should verify that the specified user has valid a Lync Server user account.</span></span> <span data-ttu-id="96286-146">Você pode recuperar informações da conta do Lync Server usando um comando semelhante a este:</span><span class="sxs-lookup"><span data-stu-id="96286-146">You can retrieve Lync Server account information by using a command similar to this:</span></span>

    Get-CsUser -Identity "sip:kenmyer@litwareinc.com" | Select-Object Enabled

<span data-ttu-id="96286-147">Se a propriedade Enabled não for igual a true ou se o comando falhar, isso significará que o usuário não tem uma conta válida do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="96286-147">If the Enabled property is not equal to True or if the command fails, that means that the user does not have a valid Lync Server account.</span></span>

<span data-ttu-id="96286-148">Verifique também se a senha que você forneceu quando você executa o cmdlet é uma senha válida.</span><span class="sxs-lookup"><span data-stu-id="96286-148">You should also verify that the password that you supplied when you run the cmdlet is a valid password.</span></span>

<span data-ttu-id="96286-149">Problemas de configuração com o Office Web Apps Server também podem causar falha de Test-CsWebAppAnonymous; Isso geralmente será o caso se você receber o seguinte diagnóstico:</span><span class="sxs-lookup"><span data-stu-id="96286-149">Configuration problems with Office Web Apps Server can also cause Test-CsWebAppAnonymous to fail; that will often be the case if you receive the following diagnosis:</span></span>

<span data-ttu-id="96286-150">A solicitação HTTP está não autorizada com o esquema de autenticação de cliente ' NTLM '.</span><span class="sxs-lookup"><span data-stu-id="96286-150">The HTTP request is unauthorized with client authentication scheme 'Ntlm'.</span></span> <span data-ttu-id="96286-151">O cabeçalho de autenticação recebido do servidor era ' Negotiate, NTLM '.</span><span class="sxs-lookup"><span data-stu-id="96286-151">The authentication header received from the server was 'Negotiate,NTLM'.</span></span>

<span data-ttu-id="96286-152">Para obter mais informações sobre como diagnosticar e resolver problemas do servidor do Office Web Apps, consulte a postagem no blog [Office Web Apps server 2013-as máquinas são sempre reportadas como não íntegras](http://www.wictorwilen.se/office-web-apps-server-2013---machines-are-always-reported-as-unhealthy).</span><span class="sxs-lookup"><span data-stu-id="96286-152">For more information on diagnosing and resolving Office Web Apps Server problems see the blog post [Office Web Apps Server 2013 - machines are always reported as Unhealthy](http://www.wictorwilen.se/office-web-apps-server-2013---machines-are-always-reported-as-unhealthy).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

