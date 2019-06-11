---
title: 'Lync Server 2013: testando a política de localização'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Testing location policy
ms:assetid: 23d06fd3-31ee-4480-ba1e-d179a55b8b14
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn690127(v=OCS.15)
ms:contentKeyID: 63969591
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e034be609bfe773a15935d7f0875e0155b57df75
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34844631"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="testing-location-policy-in-lync-server-2013"></a><span data-ttu-id="9dbe0-102">Testando a política de localização no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9dbe0-102">Testing location policy in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9dbe0-103">_**Tópico da última modificação:** 2014-06-05_</span><span class="sxs-lookup"><span data-stu-id="9dbe0-103">_**Topic Last Modified:** 2014-06-05_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="9dbe0-104">Cronograma de verificação</span><span class="sxs-lookup"><span data-stu-id="9dbe0-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="9dbe0-105">Diário</span><span class="sxs-lookup"><span data-stu-id="9dbe0-105">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9dbe0-106">Ferramenta de teste</span><span class="sxs-lookup"><span data-stu-id="9dbe0-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="9dbe0-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="9dbe0-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9dbe0-108">Permissões necessárias</span><span class="sxs-lookup"><span data-stu-id="9dbe0-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="9dbe0-109">Quando executado localmente usando o Shell de gerenciamento do Lync Server, os usuários devem ser membros do grupo de segurança RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="9dbe0-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="9dbe0-110">Quando executado usando uma instância remota do Windows PowerShell, os usuários devem receber uma função RBAC que tenha permissão para executar o cmdlet Test-CsLocationPolicy.</span><span class="sxs-lookup"><span data-stu-id="9dbe0-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsLocationPolicy cmdlet.</span></span> <span data-ttu-id="9dbe0-111">Para ver uma lista de todas as funções RBAC que podem usar esse cmdlet, execute o seguinte comando no prompt do Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="9dbe0-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsLocationPolicy&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="9dbe0-112">Descrição</span><span class="sxs-lookup"><span data-stu-id="9dbe0-112">Description</span></span>

<span data-ttu-id="9dbe0-113">O cmdlet Test-CsLocationPolicy verifica se uma política de localização é atribuída a um usuário.</span><span class="sxs-lookup"><span data-stu-id="9dbe0-113">The Test-CsLocationPolicy cmdlet verifies that a location policy is assigned to a user.</span></span> <span data-ttu-id="9dbe0-114">A política de localização é usada para aplicar configurações relacionadas à funcionalidade do E9-1-1 e ao local do cliente.</span><span class="sxs-lookup"><span data-stu-id="9dbe0-114">The location policy is used to apply settings that relate to E9-1-1 functionality and client location.</span></span> <span data-ttu-id="9dbe0-115">A política de localização determina se um usuário está habilitado para E9-1-1 e, se a resposta for "Sim", qual é o comportamento de uma chamada de emergência.</span><span class="sxs-lookup"><span data-stu-id="9dbe0-115">The location policy determines whether a user is enabled for E9-1-1, and, if the answer is "yes,", what the behavior is of an emergency call.</span></span> <span data-ttu-id="9dbe0-116">Por exemplo, você pode usar a política de localização para definir qual número constitui uma chamada de emergência (911 nos Estados Unidos), se a segurança corporativa deve ser notificada automaticamente e como a chamada deve ser roteada.</span><span class="sxs-lookup"><span data-stu-id="9dbe0-116">For example, you can use the location policy to define what number makes up an emergency call (911 in the United States), whether corporate security should be automatically notified, and how the call should be routed.</span></span>

<span data-ttu-id="9dbe0-117">Você pode testar políticas de localização em usuários ou em sub-redes de rede.</span><span class="sxs-lookup"><span data-stu-id="9dbe0-117">You can test location policies on users or on network subnets.</span></span> <span data-ttu-id="9dbe0-118">Se você executar o teste em uma sub-rede (especificando um valor para o parâmetro de sub-rede), o cmdlet tentará resolver a política de localização dessa sub-rede.</span><span class="sxs-lookup"><span data-stu-id="9dbe0-118">If you run the test against a subnet (by specifying a value for the Subnet parameter), the cmdlet will attempt to resolve the location policy for that subnet.</span></span> <span data-ttu-id="9dbe0-119">Se nenhuma política de localização for atribuída à sub-rede, a política de localização para o usuário configurado será recuperada.</span><span class="sxs-lookup"><span data-stu-id="9dbe0-119">If no location policy is assigned to the subnet, the location policy for the configured user will be retrieved.</span></span> <span data-ttu-id="9dbe0-120">Se a política de sub-rede for recuperada com êxito, a saída incluirá um valor LocationPolicyTagID que começa com subnet-TagId.</span><span class="sxs-lookup"><span data-stu-id="9dbe0-120">If the subnet policy is retrieved successfully, the output will include a LocationPolicyTagID value that begins with subnet-tagid.</span></span> <span data-ttu-id="9dbe0-121">Se uma política de localização para a sub-rede não for encontrada, o LocationPolicyTagID começará com o User-TagId.</span><span class="sxs-lookup"><span data-stu-id="9dbe0-121">If a location policy for the subnet was not found, the LocationPolicyTagID will begin with user-tagid.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="9dbe0-122">Executar o teste</span><span class="sxs-lookup"><span data-stu-id="9dbe0-122">Running the test</span></span>

<span data-ttu-id="9dbe0-123">O cmdlet Test-CsLocationPolicy pode ser executado usando uma conta de teste pré-configurada (consulte Configurando contas de teste para executar testes do Lync Server) ou a conta de qualquer usuário habilitado para o Lync Server.</span><span class="sxs-lookup"><span data-stu-id="9dbe0-123">The Test-CsLocationPolicy cmdlet can be run using either a preconfigured test account (see Setting Up Test Accounts for Running Lync Server Tests) or the account of any user who is enabled for Lync Server.</span></span> <span data-ttu-id="9dbe0-124">Para executar essa verificação usando uma conta de teste, basta especificar o FQDN do pool do servidor do Lync que está sendo testado.</span><span class="sxs-lookup"><span data-stu-id="9dbe0-124">To run this check using a test account, you just have to specify the FQDN of the Lync Server pool being tested.</span></span> <span data-ttu-id="9dbe0-125">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="9dbe0-125">For example:</span></span>

    Test-CsLocationPolicy -TargetFqdn "atl-cs-001.litwareinc.com"

<span data-ttu-id="9dbe0-126">Para executar essa verificação usando uma conta de usuário real, primeiro você deve criar um objeto de credenciais do Windows PowerShell que contenha o nome da conta e a senha.</span><span class="sxs-lookup"><span data-stu-id="9dbe0-126">To run this check using an actual user account, you must first create a Windows PowerShell credentials object that contains the account name and password.</span></span> <span data-ttu-id="9dbe0-127">Em seguida, você deve incluir esse objeto de credenciais e o endereço SIP atribuído à conta ao chamar Test-CsLocationPolicy:</span><span class="sxs-lookup"><span data-stu-id="9dbe0-127">You must then include that credentials object and the SIP address assigned to the account when you call Test-CsLocationPolicy:</span></span>

    $credential = Get-Credential "litwareinc\kenmyer"
    Test-CsLocationPolicy -TargetFqdn "atl-cs-001.litwareinc.com"-UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential

<span data-ttu-id="9dbe0-128">Para obter mais informações, consulte a documentação da ajuda para o cmdlet [Test-CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/Test-CsLocationPolicy) .</span><span class="sxs-lookup"><span data-stu-id="9dbe0-128">For more information, see the Help documentation for the [Test-CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/Test-CsLocationPolicy) cmdlet.</span></span>

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="9dbe0-129">Determinação do sucesso ou falha</span><span class="sxs-lookup"><span data-stu-id="9dbe0-129">Determining success or failure</span></span>

<span data-ttu-id="9dbe0-130">Se o usuário especificado tiver uma política de local válida, você receberá uma saída semelhante a essa, com a propriedade Result marcada como **Success:**</span><span class="sxs-lookup"><span data-stu-id="9dbe0-130">If the specified user has a valid location policy, then you'll receive output similar to this, with the Result property marked as **Success:**</span></span>

<span data-ttu-id="9dbe0-131">EnhancedEmergencyServicesEnabled: true</span><span class="sxs-lookup"><span data-stu-id="9dbe0-131">EnhancedEmergencyServicesEnabled : true</span></span>

<span data-ttu-id="9dbe0-132">LocationPolicyTagID: user-TagId</span><span class="sxs-lookup"><span data-stu-id="9dbe0-132">LocationPolicyTagID : user-tagid</span></span>

<span data-ttu-id="9dbe0-133">TargetFqdn: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="9dbe0-133">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="9dbe0-134">Resultado: êxito</span><span class="sxs-lookup"><span data-stu-id="9dbe0-134">Result : Success</span></span>

<span data-ttu-id="9dbe0-135">Latência: 00:00:06.8630376</span><span class="sxs-lookup"><span data-stu-id="9dbe0-135">Latency : 00:00:06.8630376</span></span>

<span data-ttu-id="9dbe0-136">Erros</span><span class="sxs-lookup"><span data-stu-id="9dbe0-136">Error :</span></span>

<span data-ttu-id="9dbe0-137">Correto</span><span class="sxs-lookup"><span data-stu-id="9dbe0-137">Diagnosis :</span></span>

<span data-ttu-id="9dbe0-138">Se não for possível encontrar uma política de local válida para o usuário especificado, o resultado será mostrado como uma falha, e as informações adicionais serão gravadas nas propriedades erro e diagnóstico:</span><span class="sxs-lookup"><span data-stu-id="9dbe0-138">If a valid location policy cannot be found for the specified user, then Result will be shown as Failure, and additional information will be recorded in the Error and Diagnosis properties:</span></span>

<span data-ttu-id="9dbe0-139">TargetFqdn: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="9dbe0-139">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="9dbe0-140">Resultado: falha</span><span class="sxs-lookup"><span data-stu-id="9dbe0-140">Result : Failure</span></span>

<span data-ttu-id="9dbe0-141">Latência: 00:00:00</span><span class="sxs-lookup"><span data-stu-id="9dbe0-141">Latency : 00:00:00</span></span>

<span data-ttu-id="9dbe0-142">Erro: 404, não encontrado</span><span class="sxs-lookup"><span data-stu-id="9dbe0-142">Error : 404, Not Found</span></span>

<span data-ttu-id="9dbe0-143">Diagnóstico: ErrorCode = 4005, Source = ATL-cs-001.litwareinc.com,</span><span class="sxs-lookup"><span data-stu-id="9dbe0-143">Diagnosis : ErrorCode=4005,Source=atl-cs-001.litwareinc.com,</span></span>

<span data-ttu-id="9dbe0-144">Motivo = o URI de destino não está habilitado para SIP ou não</span><span class="sxs-lookup"><span data-stu-id="9dbe0-144">Reason=Destination URI either not enabled for SIP or does not</span></span>

<span data-ttu-id="9dbe0-145">Existem.</span><span class="sxs-lookup"><span data-stu-id="9dbe0-145">exist.</span></span>

<span data-ttu-id="9dbe0-146">Microsoft. RTC. Signaling. DiagnosticHeader</span><span class="sxs-lookup"><span data-stu-id="9dbe0-146">Microsoft.Rtc.Signaling.DiagnosticHeader</span></span>

<span data-ttu-id="9dbe0-147">A saída anterior informa que o teste falhou porque o usuário especificado não é válido: ou a conta não existe ou o usuário não foi habilitado para o Lync Server.</span><span class="sxs-lookup"><span data-stu-id="9dbe0-147">The previous output states that the test failed because the specified user is not valid: either the account does not exist or the user has not been enabled for Lync Server.</span></span> <span data-ttu-id="9dbe0-148">Você pode verificar a validade de uma conta e determinar se essa conta foi habilitada para nm-OCS-14-3º, executando um comando semelhante a este:</span><span class="sxs-lookup"><span data-stu-id="9dbe0-148">You can verify the validity of an account, and determine whether or not that account has been enabled for nm-ocs-14-3rd, by running a command similar to this:</span></span>

    Get-CsUser "sip:kenmyer@litwareinc.com" | Select-Object SipAddress, Enabled

<span data-ttu-id="9dbe0-149">Se Test-CsLocationPolicy falhar, talvez você queira executar novamente o teste, desta vez, incluindo o parâmetro Verbose:</span><span class="sxs-lookup"><span data-stu-id="9dbe0-149">If Test-CsLocationPolicy fails, then you might want to rerun the test, this time including the Verbose parameter:</span></span>

    Test-CsLocationPolicy -TargetFqdn "atl-cs-001.litwareinc.com" -Verbose

<span data-ttu-id="9dbe0-150">Quando o parâmetro Verbose estiver incluído, Test-CsLocationPolicy retornará uma conta passo a passo de cada ação que tentou ao verificar a política de localização.</span><span class="sxs-lookup"><span data-stu-id="9dbe0-150">When the Verbose parameter is included, Test-CsLocationPolicy will return a step-by-step account of each action it tried when verifying the location policy.</span></span> <span data-ttu-id="9dbe0-151">Por exemplo, essa saída indica que o Lync Server não pôde fazer logon no usuário de teste, provavelmente porque foi fornecida uma senha inválida:</span><span class="sxs-lookup"><span data-stu-id="9dbe0-151">For example, this output indicates that Lync Server couldn't log on the test user, probably because an invalid password was supplied:</span></span>

<span data-ttu-id="9dbe0-152">Enviando solicitação de registro:</span><span class="sxs-lookup"><span data-stu-id="9dbe0-152">Sending Registration request :</span></span>

<span data-ttu-id="9dbe0-153">FQDN de destino = atl-cs-011.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="9dbe0-153">Target Fqdn = atl-cs-011.litwareinc.com</span></span>

<span data-ttu-id="9dbe0-154">Endereço SIP do usuário = sip:kenmyer@litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="9dbe0-154">User Sip Address = sip:kenmyer@litwareinc.com</span></span>

<span data-ttu-id="9dbe0-155">Porta do registrador = 5061</span><span class="sxs-lookup"><span data-stu-id="9dbe0-155">Registrar Port = 5061</span></span>

<span data-ttu-id="9dbe0-156">O tipo de autenticação ' IWA ' é selecionado.</span><span class="sxs-lookup"><span data-stu-id="9dbe0-156">Auth Type 'IWA' is selected.</span></span>

<span data-ttu-id="9dbe0-157">Acesso à inscrição em SIP/ATL-cs-001. litwareinc. com</span><span class="sxs-lookup"><span data-stu-id="9dbe0-157">Registration hit against sip/atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="9dbe0-158">Atividade ' Register ' concluída em ' 0, 601795 ' segundos.</span><span class="sxs-lookup"><span data-stu-id="9dbe0-158">'Register' activity completed in '0.0601795' secs.</span></span>

<span data-ttu-id="9dbe0-159">Uma exceção ' o logon foi negado.</span><span class="sxs-lookup"><span data-stu-id="9dbe0-159">An exception 'The log on was denied.</span></span> <span data-ttu-id="9dbe0-160">Verifique se as credenciais corretas estão sendo usadas e se a conta está ativa.</span><span class="sxs-lookup"><span data-stu-id="9dbe0-160">Check that the correct credentials are being used and the account is active.'</span></span> <span data-ttu-id="9dbe0-161">ocorridas durante o fluxo de trabalho.</span><span class="sxs-lookup"><span data-stu-id="9dbe0-161">occurred during the Workflow.</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="9dbe0-162">Motivos pelos quais o teste pode ter falhado</span><span class="sxs-lookup"><span data-stu-id="9dbe0-162">Reasons why the test might have failed</span></span>

<span data-ttu-id="9dbe0-163">Aqui estão alguns motivos comuns pelos quais Test-CsLocationPolicy pode falhar:</span><span class="sxs-lookup"><span data-stu-id="9dbe0-163">Here are some common reasons why Test-CsLocationPolicy might fail:</span></span>

  - <span data-ttu-id="9dbe0-164">Você especificou uma conta de usuário que não é válida.</span><span class="sxs-lookup"><span data-stu-id="9dbe0-164">You specified a user account that is not valid.</span></span> <span data-ttu-id="9dbe0-165">Você pode verificar se existe uma conta de usuário executando um comando semelhante a este:</span><span class="sxs-lookup"><span data-stu-id="9dbe0-165">You can verify that a user account exists by running a command similar to this:</span></span>
    
        Get-CsUser "sip:kenmyer@litwareinc.com"

  - <span data-ttu-id="9dbe0-166">A conta de usuário é válida, mas a conta não está habilitada no momento para o Lync Server.</span><span class="sxs-lookup"><span data-stu-id="9dbe0-166">The user account is valid, but the account is currently not enabled for Lync Server.</span></span> <span data-ttu-id="9dbe0-167">Para verificar se uma conta de usuário está habilitada para o Lync Server, execute um comando semelhante ao seguinte:</span><span class="sxs-lookup"><span data-stu-id="9dbe0-167">To verify that a user account is enabled for Lync Server, run a command similar to the following:</span></span>
    
        Get-CsUser "sip:kenmyer@litwareinc.com" | Select-Object Enabled
    
    <span data-ttu-id="9dbe0-168">Se a propriedade Enabled estiver definida como false, isso significa que o usuário não está habilitado no momento para o Lync Server.</span><span class="sxs-lookup"><span data-stu-id="9dbe0-168">If the Enabled property is set to False, that means that the user is currently not enabled for Lync Server.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

