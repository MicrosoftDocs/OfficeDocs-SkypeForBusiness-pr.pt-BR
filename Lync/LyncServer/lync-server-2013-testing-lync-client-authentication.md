---
title: 'Lync Server 2013: testar a autenticação de cliente do Lync'
description: 'Lync Server 2013: testando a autenticação de cliente do Lync.'
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
ms.openlocfilehash: 03694b7fd56d7847d8d493304b97af335d2a5b4d
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48560577"
---
# <a name="testing-lync-client-authentication-in-lync-server-2013"></a><span data-ttu-id="efbbf-103">Testando a autenticação de cliente do Lync no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="efbbf-103">Testing Lync Client authentication in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="efbbf-104">_**Última modificação do tópico:** 2014-06-05_</span><span class="sxs-lookup"><span data-stu-id="efbbf-104">_**Topic Last Modified:** 2014-06-05_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="efbbf-105">Agenda de verificação</span><span class="sxs-lookup"><span data-stu-id="efbbf-105">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="efbbf-106">Diariamente</span><span class="sxs-lookup"><span data-stu-id="efbbf-106">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="efbbf-107">Ferramenta de teste</span><span class="sxs-lookup"><span data-stu-id="efbbf-107">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="efbbf-108">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="efbbf-108">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="efbbf-109">Permissões obrigatórias</span><span class="sxs-lookup"><span data-stu-id="efbbf-109">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="efbbf-110">Ao executar localmente usando o Shell de gerenciamento do Lync Server, os usuários devem ser membros do grupo de segurança RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="efbbf-110">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="efbbf-111">Quando executado usando uma instância remota do Windows PowerShell, os usuários devem receber uma função RBAC que tenha permissão para executar o cmdlet Test-CsClientAuth.</span><span class="sxs-lookup"><span data-stu-id="efbbf-111">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsClientAuth cmdlet.</span></span> <span data-ttu-id="efbbf-112">Para ver uma lista de todas as funções RBAC que podem usar este cmdlet, execute o seguinte comando no prompt do Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="efbbf-112">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsClientAuth&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="efbbf-113">Descrição</span><span class="sxs-lookup"><span data-stu-id="efbbf-113">Description</span></span>

<span data-ttu-id="efbbf-114">O cmdlet Test-CsClientAuth permite que você determine se um usuário pode fazer logon no Lync Server usando um certificado de cliente, é possível executar o cmdlet Test-CsClientAuth.</span><span class="sxs-lookup"><span data-stu-id="efbbf-114">The Test-CsClientAuth cmdlet enables you to determine whether a user can log on to the Lync Server by using a client certificate, you can run the Test-CsClientAuth cmdlet.</span></span> <span data-ttu-id="efbbf-115">Depois de chamar Test-CsClientAuth, o cmdlet contata o serviço de provisionamento de certificados e baixa uma cópia dos certificados de clientes para o usuário especificado.</span><span class="sxs-lookup"><span data-stu-id="efbbf-115">After calling Test-CsClientAuth, the cmdlet will contact the certificate provisioning service and download a copy of any client certificates for the specified user.</span></span> <span data-ttu-id="efbbf-116">Se um certificado de cliente puder ser encontrado e baixado, Test-CsClientAuth tentará fazer logon usando esse certificado.</span><span class="sxs-lookup"><span data-stu-id="efbbf-116">If a client certificate can be found and downloaded, Test-CsClientAuth will then attempt to log on by using that certificate.</span></span> <span data-ttu-id="efbbf-117">Se o logon for bem sucedido, Test-CsClientAuth irá fazer logoff e relatar se o teste teve êxito.</span><span class="sxs-lookup"><span data-stu-id="efbbf-117">If logon succeeds, Test-CsClientAuth will log off and report that the test succeeded.</span></span> <span data-ttu-id="efbbf-118">Se nenhum certificado for encontrado ou baixado, ou se o cmdlet não conseguir fazer logon usando o certificado, Test-CsClientAuth irá relatar que o teste fracassou.</span><span class="sxs-lookup"><span data-stu-id="efbbf-118">If a certificate cannot be found or downloaded, or if the cmdlet is unable to logon using that certificate, then Test-CsClientAuth will report that the test failed.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="efbbf-119">Executar o teste</span><span class="sxs-lookup"><span data-stu-id="efbbf-119">Running the test</span></span>

<span data-ttu-id="efbbf-120">O cmdlet Test-CsClientAuth é executado usando a conta de qualquer usuário habilitado para o Lync Server.</span><span class="sxs-lookup"><span data-stu-id="efbbf-120">The Test-CsClientAuth cmdlet is run by using the account of any user who is enabled for Lync Server.</span></span> <span data-ttu-id="efbbf-121">Para executar essa verificação usando uma conta de usuário real, você deve primeiro criar um objeto de credenciais do Windows PowerShell que contenha o nome da conta e a senha.</span><span class="sxs-lookup"><span data-stu-id="efbbf-121">To run this check using an actual user account, you must first create a Windows PowerShell credentials object that contains the account name and password.</span></span> <span data-ttu-id="efbbf-122">Em seguida, você deve incluir o objeto Credentials e o endereço SIP atribuído à conta quando o sistema chama Test-CsClientAuth:</span><span class="sxs-lookup"><span data-stu-id="efbbf-122">You must then include that credentials object and the SIP address assigned to the account when the system calls Test-CsClientAuth:</span></span>

    $credential = Get-Credential "litwareinc\kenmyer"
    Test-CsClientAuth -TargetFqdn "atl-cs-001.litwareinc.com"-UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential

<span data-ttu-id="efbbf-123">Para obter mais informações, consulte a documentação de ajuda para o cmdlet [Test-CsClientAuth](https://technet.microsoft.com/library/gg398712\(v=ocs.14\).aspx) .</span><span class="sxs-lookup"><span data-stu-id="efbbf-123">For more information, see the Help documentation for the [Test-CsClientAuth](https://technet.microsoft.com/library/gg398712\(v=ocs.14\).aspx) cmdlet.</span></span>

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="efbbf-124">Determinando o sucesso ou a falha</span><span class="sxs-lookup"><span data-stu-id="efbbf-124">Determining success or failure</span></span>

<span data-ttu-id="efbbf-125">Se o usuário especificado puder fazer logon no Lync Server usando um certificado de cliente, você receberá uma saída semelhante a esta, com a propriedade Result marcada como **êxito:**</span><span class="sxs-lookup"><span data-stu-id="efbbf-125">If the specified user can log on to Lync Server by using a client certificate, you will receive output similar to this, with the Result property marked as **Success:**</span></span>

<span data-ttu-id="efbbf-126">TargetFqdn: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="efbbf-126">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="efbbf-127">Resultado: êxito</span><span class="sxs-lookup"><span data-stu-id="efbbf-127">Result : Success</span></span>

<span data-ttu-id="efbbf-128">Latência: 00:00:06.8630376</span><span class="sxs-lookup"><span data-stu-id="efbbf-128">Latency : 00:00:06.8630376</span></span>

<span data-ttu-id="efbbf-129">Erros</span><span class="sxs-lookup"><span data-stu-id="efbbf-129">Error :</span></span>

<span data-ttu-id="efbbf-130">Diagnóstico</span><span class="sxs-lookup"><span data-stu-id="efbbf-130">Diagnosis :</span></span>

<span data-ttu-id="efbbf-131">Se o usuário especificado não puder fazer logon, o resultado será mostrado como falha e informações adicionais serão registradas nas propriedades de erro e diagnóstico:</span><span class="sxs-lookup"><span data-stu-id="efbbf-131">If the specified user can not log on, the Result will be shown as Failure and additional information will be recorded in the Error and Diagnosis properties:</span></span>

<span data-ttu-id="efbbf-132">TargetFqdn: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="efbbf-132">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="efbbf-133">Resultado: falha</span><span class="sxs-lookup"><span data-stu-id="efbbf-133">Result : Failure</span></span>

<span data-ttu-id="efbbf-134">Latência: 00:00:03.3645259</span><span class="sxs-lookup"><span data-stu-id="efbbf-134">Latency : 00:00:03.3645259</span></span>

<span data-ttu-id="efbbf-135">Erro: não foi possível baixar um certificado de CS para o usuário fornecido.</span><span class="sxs-lookup"><span data-stu-id="efbbf-135">Error : Could not download a CS Certificate for the given user.</span></span> <span data-ttu-id="efbbf-136">Verifique se</span><span class="sxs-lookup"><span data-stu-id="efbbf-136">Check if</span></span>

<span data-ttu-id="efbbf-137">o URI fornecido e as credenciais estão corretos.</span><span class="sxs-lookup"><span data-stu-id="efbbf-137">provided uri and credentials are correct.</span></span>

<span data-ttu-id="efbbf-138">Diagnóstico</span><span class="sxs-lookup"><span data-stu-id="efbbf-138">Diagnosis :</span></span>

<span data-ttu-id="efbbf-139">Por exemplo, a saída anterior diz que o teste falhou porque um certificado de cliente válido não pôde ser localizado para o usuário especificado.</span><span class="sxs-lookup"><span data-stu-id="efbbf-139">For example, the previous output states that the test failed because a valid client certificate couldn't be located for the specified user.</span></span> <span data-ttu-id="efbbf-140">Você pode retornar uma lista de certificados de cliente emitidos para um usuário executando um comando da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="efbbf-140">You can return a list of the client certificates issued to a user by running a command as follows:</span></span>

    Get-CsClientCertificate -Identity "sip:kenmyer@litwareinc.com"

<span data-ttu-id="efbbf-141">Se Test-CsClientAuth falhar, talvez você queira executar novamente o teste, desta vez, incluindo o parâmetro Verbose:</span><span class="sxs-lookup"><span data-stu-id="efbbf-141">If Test-CsClientAuth fails, then you might want to rerun the test, this time including the Verbose parameter:</span></span>

    $credential = Get-Credential "litwareinc\kenmyer"
    Test-CsClientAuth -TargetFqdn "atl-cs-001.litwareinc.com"-UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential -Verbose

<span data-ttu-id="efbbf-142">Quando o parâmetro Verbose é incluído, Test-CsClientAuth retornará uma conta passo a passo de cada ação que tentou quando verificou a capacidade do usuário especificado fazer logon no Lync Server.</span><span class="sxs-lookup"><span data-stu-id="efbbf-142">When the Verbose parameter is included, Test-CsClientAuth will return a step-by-step account of each action it tried when it checked the ability of the specified user to log on to Lync Server.</span></span> <span data-ttu-id="efbbf-143">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="efbbf-143">For example:</span></span>

<span data-ttu-id="efbbf-144">Tentando baixar um certificado CS para o usuário: ponto de extremidade kenmyer@litwareinc.com: STEpid</span><span class="sxs-lookup"><span data-stu-id="efbbf-144">Trying to download a CS certificate for User : kenmyer@litwareinc.com endpoint : STEpid</span></span>

<span data-ttu-id="efbbf-145">URL do serviço Web: https://atl-cs-001.litwareinc.com:443/CertProv/CertprovisioningService.svc</span><span class="sxs-lookup"><span data-stu-id="efbbf-145">Web Service url : https://atl-cs-001.litwareinc.com:443/CertProv/CertprovisioningService.svc</span></span>

<span data-ttu-id="efbbf-146">Não foi possível baixar um certificado de CS do serviço Web.</span><span class="sxs-lookup"><span data-stu-id="efbbf-146">Could not download a CS certificate from web service.</span></span>

<span data-ttu-id="efbbf-147">Fira</span><span class="sxs-lookup"><span data-stu-id="efbbf-147">CHECK:</span></span>

<span data-ttu-id="efbbf-148">\- A URL do serviço Web é válida e os serviços Web são funcionais</span><span class="sxs-lookup"><span data-stu-id="efbbf-148">\- Web service url is valid and the web services are functional</span></span>

<span data-ttu-id="efbbf-149">\-Se estiver usando \\ \\ o PIN PhoneNo para autenticação, certifique-se de que eles correspondam ao URI do usuário</span><span class="sxs-lookup"><span data-stu-id="efbbf-149">\- If using PhoneNo\\\\Pin to authenticate, make sure they match the user uri</span></span>

<span data-ttu-id="efbbf-150">\- Se estiver usando a \\ autenticação Kerberos NTLM, certifique-se de ter fornecido credenciais válidas</span><span class="sxs-lookup"><span data-stu-id="efbbf-150">\- If using NTLM\\Kerberos auth, make sure you provided valid credentials</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="efbbf-151">Motivos pelos quais o teste pode ter falhado</span><span class="sxs-lookup"><span data-stu-id="efbbf-151">Reasons why the test might have failed</span></span>

<span data-ttu-id="efbbf-152">Aqui estão alguns motivos comuns para que Test-CsClientAuth possa falhar:</span><span class="sxs-lookup"><span data-stu-id="efbbf-152">Here are some common reasons why Test-CsClientAuth might fail:</span></span>

  - <span data-ttu-id="efbbf-153">Você especificou uma conta de usuário que não era válida.</span><span class="sxs-lookup"><span data-stu-id="efbbf-153">You specified a user account that was not valid.</span></span> <span data-ttu-id="efbbf-154">Você pode verificar se uma conta de usuário existe executando um comando semelhante a este:</span><span class="sxs-lookup"><span data-stu-id="efbbf-154">You can verify that a user account exists by running a command similar to this:</span></span>
    
        Get-CsUser "sip:kenmyer@litwareinc.com"

  - <span data-ttu-id="efbbf-155">A conta de usuário é válida, mas a conta não está habilitada no momento para o Lync Server.</span><span class="sxs-lookup"><span data-stu-id="efbbf-155">The user account is valid, but the account is currently not enabled for Lync Server.</span></span> <span data-ttu-id="efbbf-156">Para verificar se uma conta de usuário está habilitada para o Lync Server, execute um comando semelhante ao seguinte:</span><span class="sxs-lookup"><span data-stu-id="efbbf-156">To verify that a user account is enabled for Lync Server, run a command similar to the following:</span></span>
    
        Get-CsUser "sip:kenmyer@litwareinc.com" | Select-Object Enabled
    
    <span data-ttu-id="efbbf-157">Se a propriedade Enabled estiver definida como false, isso significa que o usuário não está atualmente habilitado para o Lync Server.</span><span class="sxs-lookup"><span data-stu-id="efbbf-157">If the Enabled property is set to False, that means that the user is currently not enabled for Lync Server.</span></span>

  - <span data-ttu-id="efbbf-158">O usuário de teste pode não ter um certificado de cliente válido.</span><span class="sxs-lookup"><span data-stu-id="efbbf-158">The test user might not have a valid client certificate.</span></span> <span data-ttu-id="efbbf-159">Você pode retornar informações sobre os certificados de cliente atribuídos a um usuário usando um comando semelhante a este:</span><span class="sxs-lookup"><span data-stu-id="efbbf-159">You can return information about the client certificates assigned to a user by using a command similar to this:</span></span>
    
        Get-CsClientCertificate -Identity "sip:kenmyer@litwareinc.com"

</div>

</div>

<span> </span>

</div>

</div>

</div>

