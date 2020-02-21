---
title: 'Lync Server 2013: testar política de local'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing location policy
ms:assetid: 23d06fd3-31ee-4480-ba1e-d179a55b8b14
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn690127(v=OCS.15)
ms:contentKeyID: 63969591
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c676247eabbce1d6453308bdbba5a7df0754caf1
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42194104"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="testing-location-policy-in-lync-server-2013"></a><span data-ttu-id="978a8-102">Testando a política de local no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="978a8-102">Testing location policy in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="978a8-103">_**Última modificação do tópico:** 2014-06-05_</span><span class="sxs-lookup"><span data-stu-id="978a8-103">_**Topic Last Modified:** 2014-06-05_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="978a8-104">Agenda de verificação</span><span class="sxs-lookup"><span data-stu-id="978a8-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="978a8-105">Diariamente</span><span class="sxs-lookup"><span data-stu-id="978a8-105">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="978a8-106">Ferramenta de teste</span><span class="sxs-lookup"><span data-stu-id="978a8-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="978a8-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="978a8-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="978a8-108">Permissões obrigatórias</span><span class="sxs-lookup"><span data-stu-id="978a8-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="978a8-109">Ao executar localmente usando o Shell de gerenciamento do Lync Server, os usuários devem ser membros do grupo de segurança RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="978a8-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="978a8-110">Quando executado usando uma instância remota do Windows PowerShell, os usuários devem receber uma função RBAC que tenha permissão para executar o cmdlet Test-CsLocationPolicy.</span><span class="sxs-lookup"><span data-stu-id="978a8-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsLocationPolicy cmdlet.</span></span> <span data-ttu-id="978a8-111">Para ver uma lista de todas as funções RBAC que podem usar este cmdlet, execute o seguinte comando no prompt do Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="978a8-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsLocationPolicy&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="978a8-112">Descrição</span><span class="sxs-lookup"><span data-stu-id="978a8-112">Description</span></span>

<span data-ttu-id="978a8-113">O cmdlet Test-CsLocationPolicy verifica se uma política de local é atribuída a um usuário.</span><span class="sxs-lookup"><span data-stu-id="978a8-113">The Test-CsLocationPolicy cmdlet verifies that a location policy is assigned to a user.</span></span> <span data-ttu-id="978a8-114">A diretiva de local é usada para aplicar configurações que tenham relação com a funcionalidade E9-1-1 e o local do cliente.</span><span class="sxs-lookup"><span data-stu-id="978a8-114">The location policy is used to apply settings that relate to E9-1-1 functionality and client location.</span></span> <span data-ttu-id="978a8-115">A política de local determina se um usuário está habilitado para o E9-1-1 e, se a resposta for "Sim", qual é o comportamento de uma chamada de emergência.</span><span class="sxs-lookup"><span data-stu-id="978a8-115">The location policy determines whether a user is enabled for E9-1-1, and, if the answer is "yes,", what the behavior is of an emergency call.</span></span> <span data-ttu-id="978a8-116">Por exemplo, você pode usar a política de local para definir o número que constitui uma chamada de emergência (911 nos Estados Unidos), se a segurança corporativa deve ser notificada automaticamente e como a chamada deve ser encaminhada.</span><span class="sxs-lookup"><span data-stu-id="978a8-116">For example, you can use the location policy to define what number makes up an emergency call (911 in the United States), whether corporate security should be automatically notified, and how the call should be routed.</span></span>

<span data-ttu-id="978a8-117">É possível testar diretivas de local em usuários ou sub-redes.</span><span class="sxs-lookup"><span data-stu-id="978a8-117">You can test location policies on users or on network subnets.</span></span> <span data-ttu-id="978a8-118">Se o teste for executado contra uma sub-rede (especificando-se um valor para o parâmetro Subnet), o cmdlet tentará resolver a diretiva de local para essa sub-rede.</span><span class="sxs-lookup"><span data-stu-id="978a8-118">If you run the test against a subnet (by specifying a value for the Subnet parameter), the cmdlet will attempt to resolve the location policy for that subnet.</span></span> <span data-ttu-id="978a8-119">Se nenhuma diretiva de local for atribuída à sub-rede, a diretiva de local do usuário configurado será recuperada.</span><span class="sxs-lookup"><span data-stu-id="978a8-119">If no location policy is assigned to the subnet, the location policy for the configured user will be retrieved.</span></span> <span data-ttu-id="978a8-120">Se a política de sub-rede for recuperada com êxito, a saída incluirá um valor LocationPolicyTagID que começa com subnet-TagId.</span><span class="sxs-lookup"><span data-stu-id="978a8-120">If the subnet policy is retrieved successfully, the output will include a LocationPolicyTagID value that begins with subnet-tagid.</span></span> <span data-ttu-id="978a8-121">Se uma diretiva de local para a sub-rede não for encontrada, LocationPolicyTagID começará com user-tagid.</span><span class="sxs-lookup"><span data-stu-id="978a8-121">If a location policy for the subnet was not found, the LocationPolicyTagID will begin with user-tagid.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="978a8-122">Executar o teste</span><span class="sxs-lookup"><span data-stu-id="978a8-122">Running the test</span></span>

<span data-ttu-id="978a8-123">O cmdlet Test-CsLocationPolicy pode ser executado usando uma conta de teste pré-configurada (consulte Configurando contas de teste para executar testes do Lync Server) ou a conta de qualquer usuário habilitado para o Lync Server.</span><span class="sxs-lookup"><span data-stu-id="978a8-123">The Test-CsLocationPolicy cmdlet can be run using either a preconfigured test account (see Setting Up Test Accounts for Running Lync Server Tests) or the account of any user who is enabled for Lync Server.</span></span> <span data-ttu-id="978a8-124">Para executar esta verificação usando uma conta de teste, basta especificar o FQDN do pool do Lync Server que está sendo testado.</span><span class="sxs-lookup"><span data-stu-id="978a8-124">To run this check using a test account, you just have to specify the FQDN of the Lync Server pool being tested.</span></span> <span data-ttu-id="978a8-125">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="978a8-125">For example:</span></span>

    Test-CsLocationPolicy -TargetFqdn "atl-cs-001.litwareinc.com"

<span data-ttu-id="978a8-126">Para executar essa verificação usando uma conta de usuário real, você deve primeiro criar um objeto de credenciais do Windows PowerShell que contenha o nome da conta e a senha.</span><span class="sxs-lookup"><span data-stu-id="978a8-126">To run this check using an actual user account, you must first create a Windows PowerShell credentials object that contains the account name and password.</span></span> <span data-ttu-id="978a8-127">Em seguida, você deve incluir o objeto Credentials e o endereço SIP atribuído à conta quando chamar Test-CsLocationPolicy:</span><span class="sxs-lookup"><span data-stu-id="978a8-127">You must then include that credentials object and the SIP address assigned to the account when you call Test-CsLocationPolicy:</span></span>

    $credential = Get-Credential "litwareinc\kenmyer"
    Test-CsLocationPolicy -TargetFqdn "atl-cs-001.litwareinc.com"-UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential

<span data-ttu-id="978a8-128">Para obter mais informações, consulte a documentação de ajuda para o cmdlet [Test-CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/Test-CsLocationPolicy) .</span><span class="sxs-lookup"><span data-stu-id="978a8-128">For more information, see the Help documentation for the [Test-CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/Test-CsLocationPolicy) cmdlet.</span></span>

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="978a8-129">Determinando o sucesso ou a falha</span><span class="sxs-lookup"><span data-stu-id="978a8-129">Determining success or failure</span></span>

<span data-ttu-id="978a8-130">Se o usuário especificado tiver uma política de local válida, você receberá uma saída semelhante a esta, com a propriedade Result marcada como **Success:**</span><span class="sxs-lookup"><span data-stu-id="978a8-130">If the specified user has a valid location policy, then you'll receive output similar to this, with the Result property marked as **Success:**</span></span>

<span data-ttu-id="978a8-131">EnhancedEmergencyServicesEnabled: true</span><span class="sxs-lookup"><span data-stu-id="978a8-131">EnhancedEmergencyServicesEnabled : true</span></span>

<span data-ttu-id="978a8-132">LocationPolicyTagID: user-TagId</span><span class="sxs-lookup"><span data-stu-id="978a8-132">LocationPolicyTagID : user-tagid</span></span>

<span data-ttu-id="978a8-133">TargetFqdn: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="978a8-133">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="978a8-134">Resultado: êxito</span><span class="sxs-lookup"><span data-stu-id="978a8-134">Result : Success</span></span>

<span data-ttu-id="978a8-135">Latência: 00:00:06.8630376</span><span class="sxs-lookup"><span data-stu-id="978a8-135">Latency : 00:00:06.8630376</span></span>

<span data-ttu-id="978a8-136">Erros</span><span class="sxs-lookup"><span data-stu-id="978a8-136">Error :</span></span>

<span data-ttu-id="978a8-137">Diagnóstico</span><span class="sxs-lookup"><span data-stu-id="978a8-137">Diagnosis :</span></span>

<span data-ttu-id="978a8-138">Se uma política de local válida não puder ser encontrada para o usuário especificado, o resultado será mostrado como falha, e informações adicionais serão registradas nas propriedades de erro e diagnóstico:</span><span class="sxs-lookup"><span data-stu-id="978a8-138">If a valid location policy cannot be found for the specified user, then Result will be shown as Failure, and additional information will be recorded in the Error and Diagnosis properties:</span></span>

<span data-ttu-id="978a8-139">TargetFqdn: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="978a8-139">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="978a8-140">Resultado: falha</span><span class="sxs-lookup"><span data-stu-id="978a8-140">Result : Failure</span></span>

<span data-ttu-id="978a8-141">Latência: 00:00:00</span><span class="sxs-lookup"><span data-stu-id="978a8-141">Latency : 00:00:00</span></span>

<span data-ttu-id="978a8-142">Erro: 404, não encontrado</span><span class="sxs-lookup"><span data-stu-id="978a8-142">Error : 404, Not Found</span></span>

<span data-ttu-id="978a8-143">Diagnóstico: ErrorCode = 4005, Source = ATL-cs-001.litwareinc.com,</span><span class="sxs-lookup"><span data-stu-id="978a8-143">Diagnosis : ErrorCode=4005,Source=atl-cs-001.litwareinc.com,</span></span>

<span data-ttu-id="978a8-144">Razão = o URI de destino não está habilitado para SIP ou não</span><span class="sxs-lookup"><span data-stu-id="978a8-144">Reason=Destination URI either not enabled for SIP or does not</span></span>

<span data-ttu-id="978a8-145">existente.</span><span class="sxs-lookup"><span data-stu-id="978a8-145">exist.</span></span>

<span data-ttu-id="978a8-146">Microsoft. RTC. Signaling. DiagnosticHeader</span><span class="sxs-lookup"><span data-stu-id="978a8-146">Microsoft.Rtc.Signaling.DiagnosticHeader</span></span>

<span data-ttu-id="978a8-147">A saída anterior indica que o teste falhou porque o usuário especificado não é válido: a conta não existe ou o usuário não foi habilitado para o Lync Server.</span><span class="sxs-lookup"><span data-stu-id="978a8-147">The previous output states that the test failed because the specified user is not valid: either the account does not exist or the user has not been enabled for Lync Server.</span></span> <span data-ttu-id="978a8-148">Você pode verificar a validade de uma conta e determinar se essa conta foi habilitada para o nm-OCS-14-3ª, executando um comando semelhante a este:</span><span class="sxs-lookup"><span data-stu-id="978a8-148">You can verify the validity of an account, and determine whether or not that account has been enabled for nm-ocs-14-3rd, by running a command similar to this:</span></span>

    Get-CsUser "sip:kenmyer@litwareinc.com" | Select-Object SipAddress, Enabled

<span data-ttu-id="978a8-149">Se Test-CsLocationPolicy falhar, talvez você queira executar novamente o teste, desta vez, incluindo o parâmetro Verbose:</span><span class="sxs-lookup"><span data-stu-id="978a8-149">If Test-CsLocationPolicy fails, then you might want to rerun the test, this time including the Verbose parameter:</span></span>

    Test-CsLocationPolicy -TargetFqdn "atl-cs-001.litwareinc.com" -Verbose

<span data-ttu-id="978a8-150">Quando o parâmetro Verbose for incluído, o Test-CsLocationPolicy retornará uma conta passo a passo de cada ação que tentou ao verificar a política de local.</span><span class="sxs-lookup"><span data-stu-id="978a8-150">When the Verbose parameter is included, Test-CsLocationPolicy will return a step-by-step account of each action it tried when verifying the location policy.</span></span> <span data-ttu-id="978a8-151">Por exemplo, essa saída indica que o Lync Server não pôde fazer logon no usuário de teste, provavelmente porque uma senha inválida foi fornecida:</span><span class="sxs-lookup"><span data-stu-id="978a8-151">For example, this output indicates that Lync Server couldn't log on the test user, probably because an invalid password was supplied:</span></span>

<span data-ttu-id="978a8-152">Enviando solicitação de registro:</span><span class="sxs-lookup"><span data-stu-id="978a8-152">Sending Registration request :</span></span>

<span data-ttu-id="978a8-153">FQDN de destino = atl-cs-011.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="978a8-153">Target Fqdn = atl-cs-011.litwareinc.com</span></span>

<span data-ttu-id="978a8-154">Endereço SIP do usuário = sip:kenmyer@litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="978a8-154">User Sip Address = sip:kenmyer@litwareinc.com</span></span>

<span data-ttu-id="978a8-155">Porta do registrador = 5061</span><span class="sxs-lookup"><span data-stu-id="978a8-155">Registrar Port = 5061</span></span>

<span data-ttu-id="978a8-156">O tipo de autenticação ' IWA ' é selecionado.</span><span class="sxs-lookup"><span data-stu-id="978a8-156">Auth Type 'IWA' is selected.</span></span>

<span data-ttu-id="978a8-157">Acerto de registro em relação ao SIP/ATL-cs-001. litwareinc. com</span><span class="sxs-lookup"><span data-stu-id="978a8-157">Registration hit against sip/atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="978a8-158">Atividade ' Register ' concluída em ' 0, 601795 ' segundos.</span><span class="sxs-lookup"><span data-stu-id="978a8-158">'Register' activity completed in '0.0601795' secs.</span></span>

<span data-ttu-id="978a8-159">Uma exceção ' o logon foi negado.</span><span class="sxs-lookup"><span data-stu-id="978a8-159">An exception 'The log on was denied.</span></span> <span data-ttu-id="978a8-160">Verifique se as credenciais corretas estão sendo usadas e se a conta está ativa.</span><span class="sxs-lookup"><span data-stu-id="978a8-160">Check that the correct credentials are being used and the account is active.'</span></span> <span data-ttu-id="978a8-161">ocorrido durante o fluxo de trabalho.</span><span class="sxs-lookup"><span data-stu-id="978a8-161">occurred during the Workflow.</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="978a8-162">Motivos pelos quais o teste pode ter falhado</span><span class="sxs-lookup"><span data-stu-id="978a8-162">Reasons why the test might have failed</span></span>

<span data-ttu-id="978a8-163">Aqui estão alguns motivos comuns pelos quais Test-CsLocationPolicy pode falhar:</span><span class="sxs-lookup"><span data-stu-id="978a8-163">Here are some common reasons why Test-CsLocationPolicy might fail:</span></span>

  - <span data-ttu-id="978a8-164">Você especificou uma conta de usuário que não é válida.</span><span class="sxs-lookup"><span data-stu-id="978a8-164">You specified a user account that is not valid.</span></span> <span data-ttu-id="978a8-165">Você pode verificar se uma conta de usuário existe executando um comando semelhante a este:</span><span class="sxs-lookup"><span data-stu-id="978a8-165">You can verify that a user account exists by running a command similar to this:</span></span>
    
        Get-CsUser "sip:kenmyer@litwareinc.com"

  - <span data-ttu-id="978a8-166">A conta de usuário é válida, mas a conta não está habilitada no momento para o Lync Server.</span><span class="sxs-lookup"><span data-stu-id="978a8-166">The user account is valid, but the account is currently not enabled for Lync Server.</span></span> <span data-ttu-id="978a8-167">Para verificar se uma conta de usuário está habilitada para o Lync Server, execute um comando semelhante ao seguinte:</span><span class="sxs-lookup"><span data-stu-id="978a8-167">To verify that a user account is enabled for Lync Server, run a command similar to the following:</span></span>
    
        Get-CsUser "sip:kenmyer@litwareinc.com" | Select-Object Enabled
    
    <span data-ttu-id="978a8-168">Se a propriedade Enabled estiver definida como false, isso significa que o usuário não está atualmente habilitado para o Lync Server.</span><span class="sxs-lookup"><span data-stu-id="978a8-168">If the Enabled property is set to False, that means that the user is currently not enabled for Lync Server.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

