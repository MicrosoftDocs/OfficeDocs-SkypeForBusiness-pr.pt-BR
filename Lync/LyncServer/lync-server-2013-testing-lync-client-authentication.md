---
title: 'Lync Server 2013: testando a autenticação do cliente do Lync'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing Lync Client authentication
ms:assetid: e22114cb-4456-4e5f-93ab-51592c4a8209
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn689120(v=OCS.15)
ms:contentKeyID: 63969659
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9e24f579a4fcaca2651c0225b515241db00ff990
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41745701"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="testing-lync-client-authentication-in-lync-server-2013"></a><span data-ttu-id="2b062-102">Testando a autenticação do cliente do Lync no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2b062-102">Testing Lync Client authentication in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2b062-103">_**Tópico da última modificação:** 2014-06-05_</span><span class="sxs-lookup"><span data-stu-id="2b062-103">_**Topic Last Modified:** 2014-06-05_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="2b062-104">Cronograma de verificação</span><span class="sxs-lookup"><span data-stu-id="2b062-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="2b062-105">Diário</span><span class="sxs-lookup"><span data-stu-id="2b062-105">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2b062-106">Ferramenta de teste</span><span class="sxs-lookup"><span data-stu-id="2b062-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="2b062-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="2b062-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2b062-108">Permissões necessárias</span><span class="sxs-lookup"><span data-stu-id="2b062-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="2b062-109">Quando executado localmente usando o Shell de gerenciamento do Lync Server, os usuários devem ser membros do grupo de segurança RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="2b062-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="2b062-110">Quando executado usando uma instância remota do Windows PowerShell, os usuários devem receber uma função RBAC que tenha permissão para executar o cmdlet Test-CsClientAuth.</span><span class="sxs-lookup"><span data-stu-id="2b062-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsClientAuth cmdlet.</span></span> <span data-ttu-id="2b062-111">Para ver uma lista de todas as funções RBAC que podem usar esse cmdlet, execute o seguinte comando no prompt do Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="2b062-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsClientAuth&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="2b062-112">Descrição</span><span class="sxs-lookup"><span data-stu-id="2b062-112">Description</span></span>

<span data-ttu-id="2b062-113">O cmdlet Test-CsClientAuth permite que você determine se um usuário pode fazer logon no Lync Server usando um certificado de cliente, você pode executar o cmdlet Test-CsClientAuth.</span><span class="sxs-lookup"><span data-stu-id="2b062-113">The Test-CsClientAuth cmdlet enables you to determine whether a user can log on to the Lync Server by using a client certificate, you can run the Test-CsClientAuth cmdlet.</span></span> <span data-ttu-id="2b062-114">Depois de chamar Test-CsClientAuth, o cmdlet entrará em contato com o serviço de provisionamento de certificado e baixará uma cópia de qualquer certificado de cliente para o usuário especificado.</span><span class="sxs-lookup"><span data-stu-id="2b062-114">After calling Test-CsClientAuth, the cmdlet will contact the certificate provisioning service and download a copy of any client certificates for the specified user.</span></span> <span data-ttu-id="2b062-115">Se um certificado de cliente pode ser encontrado e baixado, o Test-CsClientAuth tentará fazer logon usando esse certificado.</span><span class="sxs-lookup"><span data-stu-id="2b062-115">If a client certificate can be found and downloaded, Test-CsClientAuth will then attempt to log on by using that certificate.</span></span> <span data-ttu-id="2b062-116">Se o logon for bem-sucedido, Test-CsClientAuth fará logoff e relatará que o teste foi bem-sucedido.</span><span class="sxs-lookup"><span data-stu-id="2b062-116">If logon succeeds, Test-CsClientAuth will log off and report that the test succeeded.</span></span> <span data-ttu-id="2b062-117">Se não for possível localizar ou baixar um certificado, ou se o cmdlet não conseguir fazer logon usando esse certificado, o teste-CsClientAuth reportará que o teste falhou.</span><span class="sxs-lookup"><span data-stu-id="2b062-117">If a certificate cannot be found or downloaded, or if the cmdlet is unable to logon using that certificate, then Test-CsClientAuth will report that the test failed.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="2b062-118">Executar o teste</span><span class="sxs-lookup"><span data-stu-id="2b062-118">Running the test</span></span>

<span data-ttu-id="2b062-119">O cmdlet Test-CsClientAuth é executado usando a conta de qualquer usuário habilitado para o Lync Server.</span><span class="sxs-lookup"><span data-stu-id="2b062-119">The Test-CsClientAuth cmdlet is run by using the account of any user who is enabled for Lync Server.</span></span> <span data-ttu-id="2b062-120">Para executar essa verificação usando uma conta de usuário real, primeiro você deve criar um objeto de credenciais do Windows PowerShell que contenha o nome da conta e a senha.</span><span class="sxs-lookup"><span data-stu-id="2b062-120">To run this check using an actual user account, you must first create a Windows PowerShell credentials object that contains the account name and password.</span></span> <span data-ttu-id="2b062-121">Em seguida, você deve incluir esse objeto de credenciais e o endereço SIP atribuído à conta quando o sistema chamar Test-CsClientAuth:</span><span class="sxs-lookup"><span data-stu-id="2b062-121">You must then include that credentials object and the SIP address assigned to the account when the system calls Test-CsClientAuth:</span></span>

    $credential = Get-Credential "litwareinc\kenmyer"
    Test-CsClientAuth -TargetFqdn "atl-cs-001.litwareinc.com"-UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential

<span data-ttu-id="2b062-122">Para obter mais informações, consulte a documentação da ajuda para o cmdlet [Test-CsClientAuth](http://technet.microsoft.com/en-us/library/gg398712\(v=ocs.14\).aspx) .</span><span class="sxs-lookup"><span data-stu-id="2b062-122">For more information, see the Help documentation for the [Test-CsClientAuth](http://technet.microsoft.com/en-us/library/gg398712\(v=ocs.14\).aspx) cmdlet.</span></span>

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="2b062-123">Determinação do sucesso ou falha</span><span class="sxs-lookup"><span data-stu-id="2b062-123">Determining success or failure</span></span>

<span data-ttu-id="2b062-124">Se o usuário especificado puder fazer logon no Lync Server usando um certificado de cliente, você receberá uma saída semelhante a isso, com a propriedade Result marcada como **Success:**</span><span class="sxs-lookup"><span data-stu-id="2b062-124">If the specified user can log on to Lync Server by using a client certificate, you will receive output similar to this, with the Result property marked as **Success:**</span></span>

<span data-ttu-id="2b062-125">TargetFqdn: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="2b062-125">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="2b062-126">Resultado: êxito</span><span class="sxs-lookup"><span data-stu-id="2b062-126">Result : Success</span></span>

<span data-ttu-id="2b062-127">Latência: 00:00:06.8630376</span><span class="sxs-lookup"><span data-stu-id="2b062-127">Latency : 00:00:06.8630376</span></span>

<span data-ttu-id="2b062-128">Erros</span><span class="sxs-lookup"><span data-stu-id="2b062-128">Error :</span></span>

<span data-ttu-id="2b062-129">Correto</span><span class="sxs-lookup"><span data-stu-id="2b062-129">Diagnosis :</span></span>

<span data-ttu-id="2b062-130">Se o usuário especificado não puder fazer logon, o resultado será mostrado como uma falha e informações adicionais serão gravadas nas propriedades de erro e diagnóstico:</span><span class="sxs-lookup"><span data-stu-id="2b062-130">If the specified user can not log on, the Result will be shown as Failure and additional information will be recorded in the Error and Diagnosis properties:</span></span>

<span data-ttu-id="2b062-131">TargetFqdn: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="2b062-131">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="2b062-132">Resultado: falha</span><span class="sxs-lookup"><span data-stu-id="2b062-132">Result : Failure</span></span>

<span data-ttu-id="2b062-133">Latência: 00:00:03.3645259</span><span class="sxs-lookup"><span data-stu-id="2b062-133">Latency : 00:00:03.3645259</span></span>

<span data-ttu-id="2b062-134">Erro: não foi possível baixar um certificado de CS para o usuário fornecido.</span><span class="sxs-lookup"><span data-stu-id="2b062-134">Error : Could not download a CS Certificate for the given user.</span></span> <span data-ttu-id="2b062-135">Verifique se</span><span class="sxs-lookup"><span data-stu-id="2b062-135">Check if</span></span>

<span data-ttu-id="2b062-136">as credenciais e o URI fornecidos estão corretos.</span><span class="sxs-lookup"><span data-stu-id="2b062-136">provided uri and credentials are correct.</span></span>

<span data-ttu-id="2b062-137">Correto</span><span class="sxs-lookup"><span data-stu-id="2b062-137">Diagnosis :</span></span>

<span data-ttu-id="2b062-138">Por exemplo, a saída anterior informa que o teste falhou porque um certificado de cliente válido não pôde ser localizado para o usuário especificado.</span><span class="sxs-lookup"><span data-stu-id="2b062-138">For example, the previous output states that the test failed because a valid client certificate couldn't be located for the specified user.</span></span> <span data-ttu-id="2b062-139">Você pode retornar uma lista dos certificados de cliente emitidos para um usuário executando um comando da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="2b062-139">You can return a list of the client certificates issued to a user by running a command as follows:</span></span>

    Get-CsClientCertificate -Identity "sip:kenmyer@litwareinc.com"

<span data-ttu-id="2b062-140">Se Test-CsClientAuth falhar, talvez você queira executar novamente o teste, desta vez, incluindo o parâmetro Verbose:</span><span class="sxs-lookup"><span data-stu-id="2b062-140">If Test-CsClientAuth fails, then you might want to rerun the test, this time including the Verbose parameter:</span></span>

    $credential = Get-Credential "litwareinc\kenmyer"
    Test-CsClientAuth -TargetFqdn "atl-cs-001.litwareinc.com"-UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential -Verbose

<span data-ttu-id="2b062-141">Quando o parâmetro Verbose estiver incluído, Test-CsClientAuth retornará uma conta passo a passo de cada ação que tentou verificar quando verificou a capacidade do usuário especificado para fazer logon no Lync Server.</span><span class="sxs-lookup"><span data-stu-id="2b062-141">When the Verbose parameter is included, Test-CsClientAuth will return a step-by-step account of each action it tried when it checked the ability of the specified user to log on to Lync Server.</span></span> <span data-ttu-id="2b062-142">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="2b062-142">For example:</span></span>

<span data-ttu-id="2b062-143">Tentando baixar um certificado de CS para o usuário: kenmyer@litwareinc.com Endpoint: STEpid</span><span class="sxs-lookup"><span data-stu-id="2b062-143">Trying to download a CS certificate for User : kenmyer@litwareinc.com endpoint : STEpid</span></span>

<span data-ttu-id="2b062-144">URL do serviço Web:https://atl-cs-001.litwareinc.com:443/CertProv/CertprovisioningService.svc</span><span class="sxs-lookup"><span data-stu-id="2b062-144">Web Service url : https://atl-cs-001.litwareinc.com:443/CertProv/CertprovisioningService.svc</span></span>

<span data-ttu-id="2b062-145">Não foi possível baixar um certificado de CS do serviço Web.</span><span class="sxs-lookup"><span data-stu-id="2b062-145">Could not download a CS certificate from web service.</span></span>

<span data-ttu-id="2b062-146">SELECIONAR</span><span class="sxs-lookup"><span data-stu-id="2b062-146">CHECK:</span></span>

<span data-ttu-id="2b062-147">\-A URL do serviço Web é válida e os serviços Web são funcionais</span><span class="sxs-lookup"><span data-stu-id="2b062-147">\- Web service url is valid and the web services are functional</span></span>

<span data-ttu-id="2b062-148">\-Se estiver usando\\\\o pino PhoneNo para autenticar, certifique-se de que correspondam ao URI do usuário</span><span class="sxs-lookup"><span data-stu-id="2b062-148">\- If using PhoneNo\\\\Pin to authenticate, make sure they match the user uri</span></span>

<span data-ttu-id="2b062-149">\-Se estiver usando\\a autenticação Kerberos NTLM, certifique-se de que você forneceu credenciais válidas</span><span class="sxs-lookup"><span data-stu-id="2b062-149">\- If using NTLM\\Kerberos auth, make sure you provided valid credentials</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="2b062-150">Motivos pelos quais o teste pode ter falhado</span><span class="sxs-lookup"><span data-stu-id="2b062-150">Reasons why the test might have failed</span></span>

<span data-ttu-id="2b062-151">Aqui estão alguns motivos comuns pelos quais Test-CsClientAuth pode falhar:</span><span class="sxs-lookup"><span data-stu-id="2b062-151">Here are some common reasons why Test-CsClientAuth might fail:</span></span>

  - <span data-ttu-id="2b062-152">Você especificou uma conta de usuário que não era válida.</span><span class="sxs-lookup"><span data-stu-id="2b062-152">You specified a user account that was not valid.</span></span> <span data-ttu-id="2b062-153">Você pode verificar se existe uma conta de usuário executando um comando semelhante a este:</span><span class="sxs-lookup"><span data-stu-id="2b062-153">You can verify that a user account exists by running a command similar to this:</span></span>
    
        Get-CsUser "sip:kenmyer@litwareinc.com"

  - <span data-ttu-id="2b062-154">A conta de usuário é válida, mas a conta não está habilitada no momento para o Lync Server.</span><span class="sxs-lookup"><span data-stu-id="2b062-154">The user account is valid, but the account is currently not enabled for Lync Server.</span></span> <span data-ttu-id="2b062-155">Para verificar se uma conta de usuário está habilitada para o Lync Server, execute um comando semelhante ao seguinte:</span><span class="sxs-lookup"><span data-stu-id="2b062-155">To verify that a user account is enabled for Lync Server, run a command similar to the following:</span></span>
    
        Get-CsUser "sip:kenmyer@litwareinc.com" | Select-Object Enabled
    
    <span data-ttu-id="2b062-156">Se a propriedade Enabled estiver definida como false, isso significa que o usuário não está habilitado no momento para o Lync Server.</span><span class="sxs-lookup"><span data-stu-id="2b062-156">If the Enabled property is set to False, that means that the user is currently not enabled for Lync Server.</span></span>

  - <span data-ttu-id="2b062-157">O usuário de teste pode não ter um certificado de cliente válido.</span><span class="sxs-lookup"><span data-stu-id="2b062-157">The test user might not have a valid client certificate.</span></span> <span data-ttu-id="2b062-158">Você pode retornar informações sobre os certificados de cliente atribuídos a um usuário usando um comando semelhante a este:</span><span class="sxs-lookup"><span data-stu-id="2b062-158">You can return information about the client certificates assigned to a user by using a command similar to this:</span></span>
    
        Get-CsClientCertificate -Identity "sip:kenmyer@litwareinc.com"

</div>

</div>

<span> </span>

</div>

</div>

</div>

