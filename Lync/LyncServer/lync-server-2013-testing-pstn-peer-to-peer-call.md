---
title: 'Lync Server 2013: testando chamada ponto a ponto PSTN'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing PSTN peer to peer call
ms:assetid: 7e128eef-9ada-49b4-940f-97d7d13f1e4a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn690131(v=OCS.15)
ms:contentKeyID: 63969622
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9f120747eb50e8c1c52bb14d0a8883db8133022c
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41745611"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="testing-pstn-peer-to-peer-call-in-lync-server-2013"></a><span data-ttu-id="bb859-102">Testando chamada ponto a ponto PSTN no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="bb859-102">Testing PSTN peer to peer call in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="bb859-103">_**Tópico da última modificação:** 2014-06-05_</span><span class="sxs-lookup"><span data-stu-id="bb859-103">_**Topic Last Modified:** 2014-06-05_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="bb859-104">Cronograma de verificação</span><span class="sxs-lookup"><span data-stu-id="bb859-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="bb859-105">Diário</span><span class="sxs-lookup"><span data-stu-id="bb859-105">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bb859-106">Ferramenta de teste</span><span class="sxs-lookup"><span data-stu-id="bb859-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="bb859-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="bb859-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bb859-108">Permissões necessárias</span><span class="sxs-lookup"><span data-stu-id="bb859-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="bb859-109">Quando executado localmente usando o Shell de gerenciamento do Lync Server, os usuários devem ser membros do grupo de segurança RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="bb859-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="bb859-110">Quando executado usando uma instância remota do Windows PowerShell, os usuários devem receber uma função RBAC que tenha permissão para executar o cmdlet Test-CsPstnPeerToPeerCall.</span><span class="sxs-lookup"><span data-stu-id="bb859-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsPstnPeerToPeerCall cmdlet.</span></span> <span data-ttu-id="bb859-111">Para ver uma lista de todas as funções RBAC que podem usar esse cmdlet, execute o seguinte comando no prompt do Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="bb859-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsPstnPeerToPeerCall&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="bb859-112">Descrição</span><span class="sxs-lookup"><span data-stu-id="bb859-112">Description</span></span>

<span data-ttu-id="bb859-113">O cmdlet Test-CsPstnPeerToPeerCall verifica a capacidade de um par de usuários realizar uma chamada ponto a ponto pelo gateway PSTN (rede telefônica pública comutada).</span><span class="sxs-lookup"><span data-stu-id="bb859-113">The Test-CsPstnPeerToPeerCall cmdlet verifies the ability a pair of users has to conduct a peer-to-peer call over the public switched telephone network (PSTN) gateway.</span></span> <span data-ttu-id="bb859-114">Quando você chama Test-CsPstnPeerToPeerCall, o cmdlet tenta primeiro fazer logon dois usuários de teste no Lync Server.</span><span class="sxs-lookup"><span data-stu-id="bb859-114">When you call Test-CsPstnPeerToPeerCall, the cmdlet will first attempt to log on two test users to Lync Server.</span></span> <span data-ttu-id="bb859-115">Pressupondo que os logons sejam bem-sucedidos, o cmdlet terá o usuário 1 tentando chamar o usuário 2 pelo gateway PSTN.</span><span class="sxs-lookup"><span data-stu-id="bb859-115">Assuming that the logons succeed, the cmdlet will then have user 1 attempt to call user 2 over the PSTN gateway.</span></span> <span data-ttu-id="bb859-116">Test-CsPstnPeerToPeerCall fará essa chamada usando o plano de discagem, a política de voz e outras configurações de política e configuração atribuídas ao usuário de teste.</span><span class="sxs-lookup"><span data-stu-id="bb859-116">Test-CsPstnPeerToPeerCall will make this call using the dial plan, voice policy, and other policy and configuration settings assigned to the test user.</span></span> <span data-ttu-id="bb859-117">Se o teste for planejado, o cmdlet verificará se o usuário 2 pôde atender a chamada e, em seguida, fazer logoff de ambas as contas de teste do sistema.</span><span class="sxs-lookup"><span data-stu-id="bb859-117">If the test goes as planned, the cmdlet will verify that user 2 was able to answer the call, and then log off both test accounts from the system.</span></span>

<span data-ttu-id="bb859-118">Test-CsPstnPeerToPeerCall faz uma chamada telefônica real, uma que verifica se uma conexão pode ser feita e também transmite códigos DTMF pela rede para determinar se a mídia pode ser enviada pela conexão.</span><span class="sxs-lookup"><span data-stu-id="bb859-118">Test-CsPstnPeerToPeerCall makes an actual phone call, one that verifies that a connection can be made and that also transmits DTMF codes over the network to determine whether media can be sent over the connection.</span></span> <span data-ttu-id="bb859-119">A chamada é atendida pelo próprio cmdlet e não é necessário encerrar manualmente a chamada.</span><span class="sxs-lookup"><span data-stu-id="bb859-119">The call is answered by the cmdlet itself, and no manual termination of the call is necessary.</span></span> <span data-ttu-id="bb859-120">(Ou seja, ninguém precisa atender e desligar o telefone que foi chamado.)</span><span class="sxs-lookup"><span data-stu-id="bb859-120">(That is, no one must answer and then hang up the phone that was called.)</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="bb859-121">Executar o teste</span><span class="sxs-lookup"><span data-stu-id="bb859-121">Running the test</span></span>

<span data-ttu-id="bb859-122">O cmdlet Test-CsPstnPeerToPeerCall pode ser executado usando um par de contas de teste pré-configuradas (consulte Configurando contas de teste para executar testes do Lync Server) ou das contas de dois usuários que estão habilitados para o Lync Server.</span><span class="sxs-lookup"><span data-stu-id="bb859-122">The Test-CsPstnPeerToPeerCall cmdlet can be run using either a pair of preconfigured test accounts (see Setting Up Test Accounts for Running Lync Server Tests) or the accounts of any two users who are enabled for Lync Server.</span></span> <span data-ttu-id="bb859-123">Para executar essa verificação usando contas de teste, basta especificar o FQDN do pool do servidor do Lync que está sendo testado.</span><span class="sxs-lookup"><span data-stu-id="bb859-123">To run this check using test accounts, you just have to specify the FQDN of the Lync Server pool being tested.</span></span> <span data-ttu-id="bb859-124">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="bb859-124">For example:</span></span>

`Test-CsPstnPeerToPeerCall -TargetFqdn "atl-cs-001.litwareinc.com"`

<span data-ttu-id="bb859-125">Para executar essa verificação usando contas de usuário reais, você deve criar dois objetos de credenciais do Windows PowerShell (objetos que contêm o nome da conta e a senha) para cada conta.</span><span class="sxs-lookup"><span data-stu-id="bb859-125">To run this check using actual user accounts, you must create two Windows PowerShell credentials objects (objects that contain the account name and password) for each account.</span></span> <span data-ttu-id="bb859-126">Em seguida, você deve incluir esses objetos de credenciais e os endereços SIP das duas contas ao chamar Test-CsPstnPeerToPeerCall:</span><span class="sxs-lookup"><span data-stu-id="bb859-126">You must then include those credentials objects and the SIP addresses of the two accounts when you call Test-CsPstnPeerToPeerCall:</span></span>

    $credential1 = Get-Credential "litwareinc\kenmyer"
    $credential2 = Get-Credential "litwareinc\davidlongmire"
    Test-CsPstnPeerToPeerCall -TargetFqdn "atl-cs-001.litwareinc.com" -SenderSipAddress "sip:kenmyer@litwareinc.com" -SenderCredential $credential1 -ReceiverSipAddress "sip:davidlongmire@litwareinc.com" -ReceiverCredential $credential2

<span data-ttu-id="bb859-127">Para obter mais informações, consulte a documentação da ajuda para o cmdlet [Test-CsPstnPeerToPeerCall](https://docs.microsoft.com/powershell/module/skype/Test-CsPstnPeerToPeerCall) .</span><span class="sxs-lookup"><span data-stu-id="bb859-127">For more information, see the Help documentation for the [Test-CsPstnPeerToPeerCall](https://docs.microsoft.com/powershell/module/skype/Test-CsPstnPeerToPeerCall) cmdlet.</span></span>

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="bb859-128">Determinação do sucesso ou falha</span><span class="sxs-lookup"><span data-stu-id="bb859-128">Determining success or failure</span></span>

<span data-ttu-id="bb859-129">Se os usuários especificados puderem concluir uma chamada ponto a ponto, você receberá uma saída semelhante a isso, com a propriedade Result marcada como **Success:**</span><span class="sxs-lookup"><span data-stu-id="bb859-129">If the specified users can complete a peer-to-peer call, you'll receive output similar to this, with the Result property marked as **Success:**</span></span>

<span data-ttu-id="bb859-130">TargetFqdn: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="bb859-130">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="bb859-131">Resultado: êxito</span><span class="sxs-lookup"><span data-stu-id="bb859-131">Result : Success</span></span>

<span data-ttu-id="bb859-132">Latência: 00:00:06.8630376</span><span class="sxs-lookup"><span data-stu-id="bb859-132">Latency : 00:00:06.8630376</span></span>

<span data-ttu-id="bb859-133">Erros</span><span class="sxs-lookup"><span data-stu-id="bb859-133">Error :</span></span>

<span data-ttu-id="bb859-134">Correto</span><span class="sxs-lookup"><span data-stu-id="bb859-134">Diagnosis :</span></span>

<span data-ttu-id="bb859-135">Se os usuários especificados não puderem concluir uma chamada ponto a ponto, o resultado será mostrado como uma falha, e informações adicionais serão gravadas nas propriedades de erro e diagnóstico:</span><span class="sxs-lookup"><span data-stu-id="bb859-135">If the specified users can't complete a peer-to-peer call, then the Result will be shown as Failure, and additional information will be recorded in the Error and Diagnosis properties:</span></span>

<span data-ttu-id="bb859-136">TargetFqdn: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="bb859-136">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="bb859-137">Resultado: falha</span><span class="sxs-lookup"><span data-stu-id="bb859-137">Result : Failure</span></span>

<span data-ttu-id="bb859-138">Latência: 00:00:0182361</span><span class="sxs-lookup"><span data-stu-id="bb859-138">Latency : 00:00:0182361</span></span>

<span data-ttu-id="bb859-139">Erro: 403, proibido</span><span class="sxs-lookup"><span data-stu-id="bb859-139">Error : 403, Forbidden</span></span>

<span data-ttu-id="bb859-140">Diagnóstico: ErrorCode = 12001, Source = ATL-cs-001.litwareinc.com,</span><span class="sxs-lookup"><span data-stu-id="bb859-140">Diagnosis : ErrorCode=12001,Source=atl-cs-001.litwareinc.com,</span></span>

<span data-ttu-id="bb859-141">Razão = a política de usuário não contém uso de rota de telefone</span><span class="sxs-lookup"><span data-stu-id="bb859-141">Reason=User Policy does not contain phone route usage</span></span>

<span data-ttu-id="bb859-142">A saída anterior informa que o teste falhou porque a política de voz atribuída a pelo menos um dos usuários especificados não inclui um uso de telefone.</span><span class="sxs-lookup"><span data-stu-id="bb859-142">The previous output states that the test failed because the voice policy assigned to at least one of the specified users does not include a phone usage.</span></span> <span data-ttu-id="bb859-143">(Os usos de telefone unem as políticas de voz a rotas de voz.</span><span class="sxs-lookup"><span data-stu-id="bb859-143">(Phone usages tie voice policies to voice routes.</span></span> <span data-ttu-id="bb859-144">Sem uma política de voz e uma rota de voz correspondente, você não pode fazer chamadas pela PSTN.)</span><span class="sxs-lookup"><span data-stu-id="bb859-144">Without both a voice policy and a corresponding voice route, you can't make calls over the PSTN.)</span></span>

<span data-ttu-id="bb859-145">Se Test-CsPstnPeerToPeerCall falhar, talvez você queira executar novamente o teste, desta vez, incluindo o parâmetro Verbose:</span><span class="sxs-lookup"><span data-stu-id="bb859-145">If Test-CsPstnPeerToPeerCall fails, then you might want to rerun the test, this time including the Verbose parameter:</span></span>

    Test-CsPstnPeerToPeerCall -TargetFqdn "atl-cs-001.litwareinc.com" -Verbose

<span data-ttu-id="bb859-146">Quando o parâmetro Verbose estiver incluído, Test-CsPstnPeerToPeerCall retornará uma conta passo a passo de cada ação que tentou verificar quando verificou a capacidade do usuário especificado para fazer logon no Lync Server.</span><span class="sxs-lookup"><span data-stu-id="bb859-146">When the Verbose parameter is included, Test-CsPstnPeerToPeerCall will return a step-by-step account of each action it tried when it checked the ability of the specified user to log on to Lync Server.</span></span> <span data-ttu-id="bb859-147">Por exemplo, essa saída indica que problemas de rede estão impedindo uma conexão com o PSTN:</span><span class="sxs-lookup"><span data-stu-id="bb859-147">For example, this output indicates that network problems are preventing a connection with the PSTN:</span></span>

<span data-ttu-id="bb859-148">Como estabelecer uma chamada com vídeo de áudio para ' SIP: + 12065551219@litwareinc. com; user = Phone '.</span><span class="sxs-lookup"><span data-stu-id="bb859-148">Establishing Audio Video call to 'sip:+12065551219@litwareinc.com;user=phone'.</span></span>

<span data-ttu-id="bb859-149">Uma resposta de exceção ' A 404 (não encontrada) foi recebida da rede e a operação falhou.</span><span class="sxs-lookup"><span data-stu-id="bb859-149">An exception 'A 404 (Not Found) response was received from the network and the operation failed.</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="bb859-150">Motivos pelos quais o teste pode ter falhado</span><span class="sxs-lookup"><span data-stu-id="bb859-150">Reasons why the test might have failed</span></span>

<span data-ttu-id="bb859-151">Aqui estão alguns motivos comuns pelos quais Test-CsPstnPeerToPeerCall pode falhar:</span><span class="sxs-lookup"><span data-stu-id="bb859-151">Here are some common reasons why Test-CsPstnPeerToPeerCall might fail:</span></span>

  - <span data-ttu-id="bb859-152">Você especificou uma conta de usuário que não é válida.</span><span class="sxs-lookup"><span data-stu-id="bb859-152">You specified a user account that is not valid.</span></span> <span data-ttu-id="bb859-153">Você pode verificar se existe uma conta de usuário executando um comando semelhante a este:</span><span class="sxs-lookup"><span data-stu-id="bb859-153">You can verify that a user account exists by running a command similar to this:</span></span>
    
        Get-CsUser "sip:kenmyer@litwareinc.com"

  - <span data-ttu-id="bb859-154">A conta de usuário é válida, mas a conta não está habilitada no momento para o Lync Server.</span><span class="sxs-lookup"><span data-stu-id="bb859-154">The user account is valid, but the account is currently not enabled for Lync Server.</span></span> <span data-ttu-id="bb859-155">Para verificar se uma conta de usuário está habilitada para o Lync Server, execute um comando semelhante ao seguinte:</span><span class="sxs-lookup"><span data-stu-id="bb859-155">To verify that a user account is enabled for Lync Server, run a command similar to the following:</span></span>
    
        Get-CsUser "sip:kenmyer@litwareinc.com" | Select-Object Enabled
    
    <span data-ttu-id="bb859-156">Se a propriedade Enabled estiver definida como false, isso significa que o usuário não está habilitado no momento para o Lync Server.</span><span class="sxs-lookup"><span data-stu-id="bb859-156">If the Enabled property is set to False, that means that the user is currently not enabled for Lync Server.</span></span>

  - <span data-ttu-id="bb859-157">A política de voz atribuída ao usuário especificado não tem um uso PSTN válido.</span><span class="sxs-lookup"><span data-stu-id="bb859-157">The voice policy assigned to the specified user does not have a valid PSTN usage.</span></span> <span data-ttu-id="bb859-158">Você pode determinar a política de voz atribuída a um usuário usando um comando semelhante a este:</span><span class="sxs-lookup"><span data-stu-id="bb859-158">You can determine the voice policy that is assigned to a user by using a command similar to this:</span></span>
    
        Get-CsUser "sip:kenmyer@litwareinc.com" | Select-Object VoicePolicy
    
    <span data-ttu-id="bb859-159">Em seguida, você pode determinar os usos PSTN (se houver) atribuídos a essa política usando um comando semelhante ao seguinte, que recupera informações sobre a política de voz por usuário RedmondVoicePolicy:</span><span class="sxs-lookup"><span data-stu-id="bb859-159">And then you can determine the PSTN usages (if any) that are assigned to that policy by using a command similar to the following, which retrieves information about the per-user voice policy RedmondVoicePolicy:</span></span>
    
        Get-CsVoicePolicy -Identity "RedmondVoicePolicy"

</div>

</div>

<span> </span>

</div>

</div>

</div>

