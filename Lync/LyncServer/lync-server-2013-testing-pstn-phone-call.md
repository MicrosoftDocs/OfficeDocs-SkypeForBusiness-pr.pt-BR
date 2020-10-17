---
title: 'Lync Server 2013: testar chamadas telefônicas PSTN'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing PSTN phone call
ms:assetid: dc7d319d-a627-45b6-a978-6111901251e3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn690133(v=OCS.15)
ms:contentKeyID: 63969656
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: abc46703118d27533ac2afd2b4b448ad9516bdd6
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48503967"
---
# <a name="testing-pstn-phone-call-in-lync-server-2013"></a><span data-ttu-id="aa9b3-102">Testando chamada telefônica PSTN no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="aa9b3-102">Testing PSTN phone call in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="aa9b3-103">_**Última modificação do tópico:** 2014-06-05_</span><span class="sxs-lookup"><span data-stu-id="aa9b3-103">_**Topic Last Modified:** 2014-06-05_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="aa9b3-104">Agenda de verificação</span><span class="sxs-lookup"><span data-stu-id="aa9b3-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="aa9b3-105">Diariamente</span><span class="sxs-lookup"><span data-stu-id="aa9b3-105">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="aa9b3-106">Ferramenta de teste</span><span class="sxs-lookup"><span data-stu-id="aa9b3-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="aa9b3-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="aa9b3-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="aa9b3-108">Permissões obrigatórias</span><span class="sxs-lookup"><span data-stu-id="aa9b3-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="aa9b3-109">Ao executar localmente usando o Shell de gerenciamento do Lync Server, os usuários devem ser membros do grupo de segurança RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="aa9b3-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="aa9b3-110">Quando executado usando uma instância remota do Windows PowerShell, os usuários devem receber uma função RBAC que tenha permissão para executar o cmdlet Test-CsRegistration.</span><span class="sxs-lookup"><span data-stu-id="aa9b3-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsRegistration cmdlet.</span></span> <span data-ttu-id="aa9b3-111">Para ver uma lista de todas as funções RBAC que podem usar este cmdlet, execute o seguinte comando no prompt do Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="aa9b3-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsPstnOutboundCall&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="aa9b3-112">Descrição</span><span class="sxs-lookup"><span data-stu-id="aa9b3-112">Description</span></span>

<span data-ttu-id="aa9b3-113">O cmdlet Test-CsPstnOutboundCall testa a capacidade de um usuário fazer uma chamada para um número de telefone localizado no PSTN.</span><span class="sxs-lookup"><span data-stu-id="aa9b3-113">The Test-CsPstnOutboundCall cmdlet tests the ability of a user to make a call to a phone number located on the PSTN.</span></span> <span data-ttu-id="aa9b3-114">Quando você executa o Test-CsPstnOutboundCall, o cmdlet tenta primeiro registrar o usuário de teste no Lync Server.</span><span class="sxs-lookup"><span data-stu-id="aa9b3-114">When you run Test-CsPstnOutboundCall, the cmdlet first attempts to log the test user on to Lync Server.</span></span> <span data-ttu-id="aa9b3-115">Se o logon for bem-sucedido, o cmdlet tentará fazer uma chamada telefônica no gateway PSTN.</span><span class="sxs-lookup"><span data-stu-id="aa9b3-115">If the logon succeeds, the cmdlet will then try to make a phone call across the PSTN gateway.</span></span> <span data-ttu-id="aa9b3-116">Este telefonema será feito usando o plano de discagem, a política de voz e outras políticas e configurações atribuídas à conta de teste.</span><span class="sxs-lookup"><span data-stu-id="aa9b3-116">This phone call will be made using the dial plan, voice policy, and other policies and settings assigned to the test account.</span></span> <span data-ttu-id="aa9b3-117">Quando a chamada é atendida, o cmdlet envia códigos DTMF (multifrequência de tom dual) pela rede para verificar a conectividade de mídia.</span><span class="sxs-lookup"><span data-stu-id="aa9b3-117">When the call is answered, the cmdlet sends dual-tone multi-frequency (DTMF) codes over the network to verify media connectivity.</span></span>

<span data-ttu-id="aa9b3-118">Ao conduzir seu teste, Test-CsPstnOutboundCall fará uma chamada telefônica real: o telefone de destino irá tocar e deve ser atendido para que o teste tenha êxito.</span><span class="sxs-lookup"><span data-stu-id="aa9b3-118">When conducting its test, Test-CsPstnOutboundCall will make an actual phone call: the target phone will ring and must be answered for the test to succeed.</span></span> <span data-ttu-id="aa9b3-119">Essa chamada também deve ser finalizada manualmente pelo administrador.</span><span class="sxs-lookup"><span data-stu-id="aa9b3-119">This call must also be manually ended by the administrator.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="aa9b3-120">Executar o teste</span><span class="sxs-lookup"><span data-stu-id="aa9b3-120">Running the test</span></span>

<span data-ttu-id="aa9b3-121">O cmdlet Test-CsPstnOutboundCall pode ser executado usando uma conta de teste pré-configurada (Confira Configurando contas de teste para executar testes do Lync Server) ou a conta de qualquer usuário habilitado para o Lync Server.</span><span class="sxs-lookup"><span data-stu-id="aa9b3-121">The Test-CsPstnOutboundCall cmdlet can be run using either a preconfigured test account (see Setting Up Test Accounts for Running Lync Server Tests) or the account of any user who is enabled for Lync Server.</span></span> <span data-ttu-id="aa9b3-122">Para executar essa verificação usando uma conta de teste, basta especificar o FQDN do pool do Lync Server que está sendo testado e o número de telefone PSTN que está sendo chamado.</span><span class="sxs-lookup"><span data-stu-id="aa9b3-122">To run this check using a test account, you just have to specify the FQDN of the Lync Server pool being tested and the PSTN phone number being called.</span></span> <span data-ttu-id="aa9b3-123">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="aa9b3-123">For example:</span></span>

    Test-CsPstnOutboundCall -TargetFqdn "atl-cs-001.litwareinc.com" -TargetPstnPhoneNumber "+12065551219"

<span data-ttu-id="aa9b3-124">Para executar essa verificação usando uma conta de usuário real, você deve primeiro criar um objeto de credenciais do Windows PowerShell que contenha o nome da conta e a senha.</span><span class="sxs-lookup"><span data-stu-id="aa9b3-124">To run this check using an actual user account, you must first create a Windows PowerShell credentials object that contains the account name and password.</span></span> <span data-ttu-id="aa9b3-125">Em seguida, você deve incluir o objeto Credentials e o endereço SIP atribuído à conta quando chamar Test-CsPstnOutboundCall:</span><span class="sxs-lookup"><span data-stu-id="aa9b3-125">You must then include that credentials object and the SIP address assigned to the account when you call Test-CsPstnOutboundCall:</span></span>

    $credential = Get-Credential "litwareinc\kenmyer"
    Test-CsPstnOutboundCall -TargetFqdn "atl-cs-001.litwareinc.com" -TargetPstnPhoneNumber "+12065551219" -UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential

<span data-ttu-id="aa9b3-126">Para obter mais informações, consulte a documentação de ajuda para o cmdlet [Test-CsPstnOutboundCall](https://docs.microsoft.com/powershell/module/skype/Test-CsPstnOutboundCall) .</span><span class="sxs-lookup"><span data-stu-id="aa9b3-126">For more information, see the Help documentation for the [Test-CsPstnOutboundCall](https://docs.microsoft.com/powershell/module/skype/Test-CsPstnOutboundCall) cmdlet.</span></span>

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="aa9b3-127">Determinando o sucesso ou a falha</span><span class="sxs-lookup"><span data-stu-id="aa9b3-127">Determining success or failure</span></span>

<span data-ttu-id="aa9b3-128">Se o usuário especificado puder fazer a chamada, e se a chamada for atendida, você receberá uma saída semelhante a esta, com a propriedade Result marcada como **êxito:**</span><span class="sxs-lookup"><span data-stu-id="aa9b3-128">If the specified user can make the call, and if the call is answered, you'll receive output similar to this, with the Result property marked as **Success:**</span></span>

<span data-ttu-id="aa9b3-129">TargetFqdn: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="aa9b3-129">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="aa9b3-130">Resultado: êxito</span><span class="sxs-lookup"><span data-stu-id="aa9b3-130">Result : Success</span></span>

<span data-ttu-id="aa9b3-131">Latência: 00:00:06.8630376</span><span class="sxs-lookup"><span data-stu-id="aa9b3-131">Latency : 00:00:06.8630376</span></span>

<span data-ttu-id="aa9b3-132">Erros</span><span class="sxs-lookup"><span data-stu-id="aa9b3-132">Error :</span></span>

<span data-ttu-id="aa9b3-133">Diagnóstico</span><span class="sxs-lookup"><span data-stu-id="aa9b3-133">Diagnosis :</span></span>

<span data-ttu-id="aa9b3-134">Se o usuário especificado não puder fazer a chamada ou se a chamada não for atendida, o resultado será mostrado como falha, e informações adicionais serão registradas nas propriedades de erro e diagnóstico:</span><span class="sxs-lookup"><span data-stu-id="aa9b3-134">If the specified user can't make the call or if the call is not answered, then the Result will be shown as Failure, and additional information will be recorded in the Error and Diagnosis properties:</span></span>

<span data-ttu-id="aa9b3-135">TargetFqdn: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="aa9b3-135">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="aa9b3-136">Resultado: falha</span><span class="sxs-lookup"><span data-stu-id="aa9b3-136">Result : Failure</span></span>

<span data-ttu-id="aa9b3-137">Latência: 00:00:0987365</span><span class="sxs-lookup"><span data-stu-id="aa9b3-137">Latency : 00:00:0987365</span></span>

<span data-ttu-id="aa9b3-138">Erro: 403, proibido</span><span class="sxs-lookup"><span data-stu-id="aa9b3-138">Error : 403, Forbidden</span></span>

<span data-ttu-id="aa9b3-139">Diagnóstico: ErrorCode = 12001, Source = ATL-cs-001. litwareinc. com, Reason = User</span><span class="sxs-lookup"><span data-stu-id="aa9b3-139">Diagnosis : ErrorCode=12001,Source=atl-cs-001.litwareinc.com,Reason=User</span></span>

<span data-ttu-id="aa9b3-140">A política não contém uso de rota de telefone</span><span class="sxs-lookup"><span data-stu-id="aa9b3-140">Policy does not contain phone route usage</span></span>

<span data-ttu-id="aa9b3-141">A saída anterior diz que o teste falhou porque a política de voz atribuída ao usuário especificado não inclui um uso de telefone.</span><span class="sxs-lookup"><span data-stu-id="aa9b3-141">The previous output states that the test failed because the voice policy assigned to the specified user does not include a phone usage.</span></span> <span data-ttu-id="aa9b3-142">(Os usos de telefone unem as políticas de voz para rotas de voz.</span><span class="sxs-lookup"><span data-stu-id="aa9b3-142">(Phone usages tie voice policies to voice routes.</span></span> <span data-ttu-id="aa9b3-143">Sem uma política de voz e uma rota de voz correspondente, você não pode fazer chamadas pela PSTN.</span><span class="sxs-lookup"><span data-stu-id="aa9b3-143">Without both a voice policy and a corresponding voice route you can't make calls over the PSTN.)</span></span>

<span data-ttu-id="aa9b3-144">Se Test-CsPstnOutboundCall falhar, talvez você queira executar novamente o teste, desta vez, incluindo o parâmetro Verbose:</span><span class="sxs-lookup"><span data-stu-id="aa9b3-144">If Test-CsPstnOutboundCall fails then you might want to rerun the test, this time including the Verbose parameter:</span></span>

    Test-CsPstnOutboundCall -TargetFqdn "atl-cs-001.litwareinc.com" -TargetPstnPhoneNumber "+12065551219" -Verbose

<span data-ttu-id="aa9b3-145">Quando o parâmetro Verbose é incluído, Test-CsPstnOutboundCall retornará uma conta passo a passo de cada ação que tentou quando verificou a capacidade do usuário especificado fazer logon no Lync Server.</span><span class="sxs-lookup"><span data-stu-id="aa9b3-145">When the Verbose parameter is included, Test-CsPstnOutboundCall will return a step-by-step account of each action it tried when it checked the ability of the specified user to log on to Lync Server.</span></span> <span data-ttu-id="aa9b3-146">Por exemplo, essa saída indica que problemas de rede estão impedindo uma conexão com o PSTN:</span><span class="sxs-lookup"><span data-stu-id="aa9b3-146">For example, this output indicates that network problems are preventing a connection with the PSTN:</span></span>

<span data-ttu-id="aa9b3-147">Estabelecendo chamada de vídeo de áudio para ' SIP: + 12065551219@litwareinc. com; user = Phone '.</span><span class="sxs-lookup"><span data-stu-id="aa9b3-147">Establishing Audio Video call to 'sip:+12065551219@litwareinc.com;user=phone'.</span></span>

<span data-ttu-id="aa9b3-148">Uma resposta de uma exceção ' A 404 (não encontrada) foi recebida da rede e a operação falhou.</span><span class="sxs-lookup"><span data-stu-id="aa9b3-148">An exception 'A 404 (Not Found) response was received from the network and the operation failed.</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="aa9b3-149">Motivos pelos quais o teste pode ter falhado</span><span class="sxs-lookup"><span data-stu-id="aa9b3-149">Reasons why the test might have failed</span></span>

<span data-ttu-id="aa9b3-150">Aqui estão alguns motivos comuns para que Test-CsPstnOutboundCall possa falhar:</span><span class="sxs-lookup"><span data-stu-id="aa9b3-150">Here are some common reasons why Test-CsPstnOutboundCall might fail:</span></span>

  - <span data-ttu-id="aa9b3-151">Você especificou uma conta de usuário inválida.</span><span class="sxs-lookup"><span data-stu-id="aa9b3-151">You specified an invalid user account.</span></span> <span data-ttu-id="aa9b3-152">Você pode verificar se uma conta de usuário existe executando um comando semelhante a este:</span><span class="sxs-lookup"><span data-stu-id="aa9b3-152">You can verify that a user account exists by running a command similar to this:</span></span>
    
        Get-CsUser "sip:kenmyer@litwareinc.com"

  - <span data-ttu-id="aa9b3-153">A conta de usuário é válida, mas a conta não está habilitada no momento para o Lync Server.</span><span class="sxs-lookup"><span data-stu-id="aa9b3-153">The user account is valid, but the account is currently not enabled for Lync Server.</span></span> <span data-ttu-id="aa9b3-154">Para verificar se uma conta de usuário está habilitada para o Lync Server, execute um comando semelhante ao seguinte:</span><span class="sxs-lookup"><span data-stu-id="aa9b3-154">To verify that a user account is enabled for Lync Server, run a command similar to the following:</span></span>
    
        Get-CsUser "sip:kenmyer@litwareinc.com" | Select-Object Enabled
    
    <span data-ttu-id="aa9b3-155">Se a propriedade Enabled estiver definida como false, isso significa que o usuário não está habilitado para o Lync Server no momento.</span><span class="sxs-lookup"><span data-stu-id="aa9b3-155">If the Enabled property is set to False that means that the user is currently not enabled for Lync Server.</span></span>

  - <span data-ttu-id="aa9b3-156">A política de voz atribuída ao usuário especificado não tem um uso PSTN válido.</span><span class="sxs-lookup"><span data-stu-id="aa9b3-156">The voice policy assigned to the specified user does not have a valid PSTN usage.</span></span> <span data-ttu-id="aa9b3-157">Você pode determinar a política de voz atribuída a um usuário usando um comando semelhante a este:</span><span class="sxs-lookup"><span data-stu-id="aa9b3-157">You can determine the voice policy that is assigned to a user by using a command similar to this:</span></span>
    
        Get-CsUser "sip:kenmyer@litwareinc.com" | Select-Object VoicePolicy
    
    <span data-ttu-id="aa9b3-158">E, em seguida, você pode determinar os usos de PSTN (se houver) atribuídos a essa política usando um comando semelhante ao seguinte, que recupera informações sobre a política de voz por usuário RedmondVoicePolicy:</span><span class="sxs-lookup"><span data-stu-id="aa9b3-158">And then you can determine the PSTN usages (if any) that are assigned to that policy by using a command similar to the following, which retrieves information about the per-user voice policy RedmondVoicePolicy:</span></span>
    
        Get-CsVoicePolicy -Identity "RedmondVoicePolicy"

</div>

</div>

<span> </span>

</div>

</div>

</div>

