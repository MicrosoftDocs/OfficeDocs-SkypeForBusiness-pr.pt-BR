---
title: 'Lync Server 2013: testar o acesso ao aplicativo Web'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Test Web App access
ms:assetid: 17d67ea3-f74d-4952-ac2b-92c0dacc8014
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn767944(v=OCS.15)
ms:contentKeyID: 63969584
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1fc6c9f3ef4a89fd1e4698cd8dc456ecb34e4304
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42194344"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="test-web-app-access-in-lync-server-2013"></a><span data-ttu-id="67508-102">Testar o acesso do aplicativo Web no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="67508-102">Test Web App access in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="67508-103">_**Última modificação do tópico:** 2014-06-07_</span><span class="sxs-lookup"><span data-stu-id="67508-103">_**Topic Last Modified:** 2014-06-07_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="67508-104">Agenda de verificação</span><span class="sxs-lookup"><span data-stu-id="67508-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="67508-105">Mensal</span><span class="sxs-lookup"><span data-stu-id="67508-105">Monthly</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="67508-106">Ferramenta de teste</span><span class="sxs-lookup"><span data-stu-id="67508-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="67508-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="67508-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="67508-108">Permissões obrigatórias</span><span class="sxs-lookup"><span data-stu-id="67508-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="67508-109">Ao executar localmente usando o Shell de gerenciamento do Lync Server, os usuários devem ser membros do grupo de segurança RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="67508-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="67508-110">Quando executado usando uma instância remota do Windows PowerShell, os usuários devem receber uma função RBAC que tenha permissão para executar o cmdlet Test-CsWebApp.</span><span class="sxs-lookup"><span data-stu-id="67508-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsWebApp cmdlet.</span></span> <span data-ttu-id="67508-111">Para ver uma lista de todas as funções RBAC que podem usar este cmdlet, execute o seguinte comando no prompt do Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="67508-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsWebApp&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="67508-112">Descrição</span><span class="sxs-lookup"><span data-stu-id="67508-112">Description</span></span>

<span data-ttu-id="67508-113">O cmdlet Test-CsWebApp verifica se os usuários autenticados podem participar de conferências do Lync Server usando o Lync Web App.</span><span class="sxs-lookup"><span data-stu-id="67508-113">The Test-CsWebApp cmdlet verifies that authenticated users can join Lync Server conferences by using the Lync Web App.</span></span> <span data-ttu-id="67508-114">Quando você executa o cmdlet, Test-CsWebApp contata o serviço de tíquete da Web para obter tíquetes da Web para os usuários especificados.</span><span class="sxs-lookup"><span data-stu-id="67508-114">When you run the cmdlet, Test-CsWebApp contacts the Web Ticket service to obtain web tickets for the specified users.</span></span> <span data-ttu-id="67508-115">Essas permissões agem efetivamente como "tíquetes de admissão" para a conferência do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="67508-115">These tickets effectively act as ‘admission tickets” to the Lync Server conference.</span></span> <span data-ttu-id="67508-116">Se as permissões puderem ser recuperadas e se os usuários puderem ser autenticados, o Test-CsWebApp entrará em contato com o Lync Server e tentará estabelecer conferências separadas para mensagens instantâneas, compartilhamento de aplicativos e colaboração de dados.</span><span class="sxs-lookup"><span data-stu-id="67508-116">If the tickets can be retrieved, and if the users can be authenticated, Test-CsWebApp will then contact Lync Server and attempt to establish separate conferences for instant messaging, application sharing, and data collaboration.</span></span>

<span data-ttu-id="67508-117">Observe que Test-CsWebApp apenas verifica as APIs e conexões usadas para criar essas conferências.</span><span class="sxs-lookup"><span data-stu-id="67508-117">Note that Test-CsWebApp just verifies the APIs and connections used to create these conferences.</span></span> <span data-ttu-id="67508-118">O cmdlet é projetado para verificar se o Lync Web App pode ser usado para criar e participar de conferências.</span><span class="sxs-lookup"><span data-stu-id="67508-118">The cmdlet is designed to verify that Lync Web App could be used to create and join conferences.</span></span> <span data-ttu-id="67508-119">No entanto, ele não cria e conduz uma conferência.</span><span class="sxs-lookup"><span data-stu-id="67508-119">However,, it does not actually create and conduct a conference.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="67508-120">Executar o teste</span><span class="sxs-lookup"><span data-stu-id="67508-120">Running the test</span></span>

<span data-ttu-id="67508-121">O cmdlet Test-CsWebApp pode ser executado usando um par de contas de teste pré-configuradas ou as contas de dois usuários que estão habilitados para o Lync Server.</span><span class="sxs-lookup"><span data-stu-id="67508-121">The Test-CsWebApp cmdlet can be run using either a pair of preconfigured test accounts or the accounts of any two users who are enabled for Lync Server.</span></span> <span data-ttu-id="67508-122">Para executar esta verificação usando contas de teste, basta especificar o nome de domínio totalmente qualificado do pool do Lync Server que está sendo testado.</span><span class="sxs-lookup"><span data-stu-id="67508-122">To run this check using test accounts, you just have to specify the fully qualified domain name of the Lync Server pool being tested.</span></span> <span data-ttu-id="67508-123">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="67508-123">For example:</span></span>

    Test-CsWebApp -TargetFqdn "atl-cs-001.litwareinc.com"

<span data-ttu-id="67508-124">Para executar essa verificação usando contas de usuário reais, você deve criar dois objetos de credenciais do Windows PowerShell (objetos que contêm o nome da conta e a senha) para cada conta.</span><span class="sxs-lookup"><span data-stu-id="67508-124">To run this check using actual user accounts, you must create two Windows PowerShell credentials objects (objects that contain the account name and password) for each account.</span></span> <span data-ttu-id="67508-125">Em seguida, você deve incluir esses objetos de credenciais e os endereços SIP das duas contas ao chamar Test-CsWebApp:</span><span class="sxs-lookup"><span data-stu-id="67508-125">You must then include those credentials objects and the SIP addresses of the two accounts when you call Test-CsWebApp:</span></span>

    $cred1 = Get-Credential "litwareinc\kenmyer"
    $cred2 = Get-Credential "litwareinc\pilar"
    
    Test-CsWebApp -TargetFqdn atl-cs-001.litwareinc.com -UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $cred1 -User2SipAddress "sip:pilar@litwareinc.com" -User2Credential $cred2

<span data-ttu-id="67508-126">Para obter mais informações, consulte o tópico de ajuda para o cmdlet [Test-CsWebApp](https://docs.microsoft.com/powershell/module/skype/Test-CsWebApp) .</span><span class="sxs-lookup"><span data-stu-id="67508-126">For more information, see the help topic for the [Test-CsWebApp](https://docs.microsoft.com/powershell/module/skype/Test-CsWebApp) cmdlet.</span></span> <span data-ttu-id="67508-127">Observe que Test-CsWebApp foi preterido para uso no Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="67508-127">Note that Test-CsWebApp was deprecated for use on Lync Server 2013.</span></span>

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="67508-128">Determinando o sucesso ou a falha</span><span class="sxs-lookup"><span data-stu-id="67508-128">Determining success or failure</span></span>

<span data-ttu-id="67508-129">Se Test-CsWebApp puder participar dos usuários em suas conferências, o cmdlet retornará o resultado de teste Success:</span><span class="sxs-lookup"><span data-stu-id="67508-129">If Test-CsWebApp can join the users to their conferences, the cmdlet will return the test result Success:</span></span>

<span data-ttu-id="67508-130">FQDN de destino:</span><span class="sxs-lookup"><span data-stu-id="67508-130">Target Fqdn :</span></span>

<span data-ttu-id="67508-131">Resultado: êxito</span><span class="sxs-lookup"><span data-stu-id="67508-131">Result : Success</span></span>

<span data-ttu-id="67508-132">Latência: 00:00:00</span><span class="sxs-lookup"><span data-stu-id="67508-132">Latency : 00:00:00</span></span>

<span data-ttu-id="67508-133">Mensagem de erro:</span><span class="sxs-lookup"><span data-stu-id="67508-133">Error Message :</span></span>

<span data-ttu-id="67508-134">Diagnóstico</span><span class="sxs-lookup"><span data-stu-id="67508-134">Diagnosis :</span></span>

<span data-ttu-id="67508-135">Se os usuários não puderem participar das conferências necessárias, o resultado do teste será marcado como falha.</span><span class="sxs-lookup"><span data-stu-id="67508-135">If the users cannot join the necessary conferences then the test result will be marked as Failure.</span></span> <span data-ttu-id="67508-136">Normalmente, Test-CsWebApp também reportará uma mensagem de erro detalhada e o diagnóstico:</span><span class="sxs-lookup"><span data-stu-id="67508-136">Typically Test-CsWebApp will also report back a detailed error message and diagnosis:</span></span>

<span data-ttu-id="67508-137">FQDN de destino: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="67508-137">Target Fqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="67508-138">Resultado: falha</span><span class="sxs-lookup"><span data-stu-id="67508-138">Result : Failure</span></span>

<span data-ttu-id="67508-139">Latência: 00:00:00</span><span class="sxs-lookup"><span data-stu-id="67508-139">Latency : 00:00:00</span></span>

<span data-ttu-id="67508-140">Mensagem de erro: nenhuma resposta recebida para o serviço de tíquete da Web</span><span class="sxs-lookup"><span data-stu-id="67508-140">Error Message : No response received for Web-Ticket service</span></span>

<span data-ttu-id="67508-141">Diagnóstico: a solicitação HTTP não é autorizada com o cliente</span><span class="sxs-lookup"><span data-stu-id="67508-141">Diagnosis : The HTTP request is unauthorized with client</span></span>

<span data-ttu-id="67508-142">esquema de autenticação ' NTLM '.</span><span class="sxs-lookup"><span data-stu-id="67508-142">authentication scheme 'Ntlm'.</span></span> <span data-ttu-id="67508-143">A autenticação</span><span class="sxs-lookup"><span data-stu-id="67508-143">The authentication</span></span>

<span data-ttu-id="67508-144">o cabeçalho recebido do servidor era ' Negotiate, NTLM '.</span><span class="sxs-lookup"><span data-stu-id="67508-144">header received from the server was 'Negotiate,NTLM'.</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="67508-145">Motivos pelos quais o teste pode ter falhado</span><span class="sxs-lookup"><span data-stu-id="67508-145">Reasons why the test might have failed</span></span>

<span data-ttu-id="67508-146">Falhas de CsWebApp de teste normalmente envolvem erros de autenticação do usuário.</span><span class="sxs-lookup"><span data-stu-id="67508-146">Test-CsWebApp failures typically involve user authentication errors.</span></span> <span data-ttu-id="67508-147">Se Test-CsWebApp falhar, você deve primeiro verificar se os usuários especificados têm contas de usuário válidas e estão habilitados para o Lync Server.</span><span class="sxs-lookup"><span data-stu-id="67508-147">If Test-CsWebApp fails, you should first verify that the specified users have valid user accounts and are enabled for Lync Server.</span></span> <span data-ttu-id="67508-148">Você pode recuperar informações da conta usando um comando semelhante ao seguinte:</span><span class="sxs-lookup"><span data-stu-id="67508-148">You can retrieve account information by using a command similar to this:</span></span>

    Get-CsUser -Identity "sip:kenmyer@litwareinc.com" | Select-Object Enabled

<span data-ttu-id="67508-149">Se a propriedade Enabled não for igual a true ou se o comando falhar, isso significa que o usuário não tem uma conta válida do Lync Server. Você também deve verificar se as senhas que você forneceu ao cmdlet são válidas.</span><span class="sxs-lookup"><span data-stu-id="67508-149">If the Enabled property is not equal to True or if the command fails, that means that the user does not have a valid Lync Server account.You should also verify that the passwords that you supplied to the cmdlet are valid.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

