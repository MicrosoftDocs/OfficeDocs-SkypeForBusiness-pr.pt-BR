---
title: 'Lync Server 2013: testar a capacidade de mensagens instantâneas entre dois usuários'
description: 'Lync Server 2013: testar a capacidade de mensagens instantâneas entre dois usuários.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing ability to IM between two users
ms:assetid: a0f3f5c6-f115-4c3f-90ac-5fdc932b417e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn743838(v=OCS.15)
ms:contentKeyID: 63969635
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1409cfb58ed435a66dcf61db56660ca760e16422
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48560797"
---
# <a name="testing-ability-to-im-between-two-users-in-lync-server-2013"></a><span data-ttu-id="f63ce-103">Testando a capacidade de mensagens instantâneas entre dois usuários no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f63ce-103">Testing ability to IM between two users in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f63ce-104">_**Última modificação do tópico:** 2014-06-05_</span><span class="sxs-lookup"><span data-stu-id="f63ce-104">_**Topic Last Modified:** 2014-06-05_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f63ce-105">Agenda de verificação</span><span class="sxs-lookup"><span data-stu-id="f63ce-105">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="f63ce-106">Diariamente</span><span class="sxs-lookup"><span data-stu-id="f63ce-106">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f63ce-107">Ferramenta de teste</span><span class="sxs-lookup"><span data-stu-id="f63ce-107">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="f63ce-108">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="f63ce-108">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f63ce-109">Permissões obrigatórias</span><span class="sxs-lookup"><span data-stu-id="f63ce-109">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="f63ce-110">Ao executar localmente usando o Shell de gerenciamento do Lync Server, os usuários devem ser membros do grupo de segurança RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="f63ce-110">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="f63ce-111">Quando executado usando uma instância remota do Windows PowerShell, os usuários devem receber uma função RBAC que tenha permissão para executar o cmdlet Test-CsIM.</span><span class="sxs-lookup"><span data-stu-id="f63ce-111">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsIM cmdlet.</span></span> <span data-ttu-id="f63ce-112">Para ver uma lista de todas as funções RBAC que podem usar este cmdlet, execute o seguinte comando no prompt do Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="f63ce-112">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsIM&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="f63ce-113">Descrição</span><span class="sxs-lookup"><span data-stu-id="f63ce-113">Description</span></span>

<span data-ttu-id="f63ce-114">O cmdlet Test-CsIM verifica se um par de usuários de teste podem trocar mensagens instantâneas.</span><span class="sxs-lookup"><span data-stu-id="f63ce-114">The Test-CsIM cmdlet verifies that a pair of test users can exchange instant messages.</span></span> <span data-ttu-id="f63ce-115">Quando chamado, o cmdlet Test-CsIM começa tentando fazer logon em um par de usuários de teste no Lync Server.</span><span class="sxs-lookup"><span data-stu-id="f63ce-115">When called, the Test-CsIM cmdlet starts off by trying to log on a pair of test users to Lync Server.</span></span> <span data-ttu-id="f63ce-116">Supondo que os dois logons sejam bem-sucedidos, o cmdlet iniciará uma sessão de IM entre os dois usuários de teste.</span><span class="sxs-lookup"><span data-stu-id="f63ce-116">Assuming the two logons are successful, the cmdlet then starts an IM session between the two test users.</span></span> <span data-ttu-id="f63ce-117">(O usuário 1 convida o usuário 2 para uma sessão de IM e o usuário 2 aceita o convite.) Após verificar que as mensagens podem ser trocadas entre os dois usuários, Test-CsIM, em seguida, encerra a sessão de mensagens instantâneas e registra os dois usuários fora do sistema.</span><span class="sxs-lookup"><span data-stu-id="f63ce-117">(User 1 invites User 2 to an IM session, and User 2 accepts the invitation.) After verifying that messages can be exchanged between the two users, Test-CsIM then ends the IM session and logs both users off the system.</span></span>

<span data-ttu-id="f63ce-118">Para obter mais informações, consulte a documentação de ajuda para o cmdlet [Test-CsIM](https://docs.microsoft.com/powershell/module/skype/Test-CsIM) .</span><span class="sxs-lookup"><span data-stu-id="f63ce-118">For more information, see the Help documentation for the [Test-CsIM](https://docs.microsoft.com/powershell/module/skype/Test-CsIM) cmdlet.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="f63ce-119">Executar o teste</span><span class="sxs-lookup"><span data-stu-id="f63ce-119">Running the Test</span></span>

<span data-ttu-id="f63ce-120">O cmdlet Test-CsIM pode ser executado usando um par de contas de teste pré-configuradas (Confira Configurando contas de teste para executar testes do Lync Server) ou as contas de dois usuários que estão habilitados para o Lync Server.</span><span class="sxs-lookup"><span data-stu-id="f63ce-120">The Test-CsIM cmdlet can be run using either a pair of preconfigured test accounts (see Setting Up Test Accounts for Running Lync Server Tests) or the accounts of any two users who are enabled for Lync Server.</span></span> <span data-ttu-id="f63ce-121">Para executar essa verificação usando contas de teste, basta especificar o FQDN do pool do Lync Server que está sendo testado.</span><span class="sxs-lookup"><span data-stu-id="f63ce-121">To run this check using test accounts, you just have to specify the FQDN of the Lync Server pool being tested.</span></span> <span data-ttu-id="f63ce-122">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="f63ce-122">For example:</span></span>

    Test-CsIM -TargetFqdn "atl-cs-001.litwareinc.com"

<span data-ttu-id="f63ce-123">Para executar essa verificação usando contas de usuário reais, você deve criar dois objetos de credenciais do Windows PowerShell (objetos que contêm o nome da conta e a senha) para cada conta.</span><span class="sxs-lookup"><span data-stu-id="f63ce-123">To run this check using actual user accounts, you must create two Windows PowerShell credentials objects (objects that contain the account name and password) for each account.</span></span> <span data-ttu-id="f63ce-124">Em seguida, você deve incluir esses objetos de credenciais e os endereços SIP das duas contas ao chamar Test-CsIM:</span><span class="sxs-lookup"><span data-stu-id="f63ce-124">You must then include those credentials objects and the SIP addresses of the two accounts when you call Test-CsIM:</span></span>

    $credential1 = Get-Credential "litwareinc\kenmyer"
    $credential2 = Get-Credential "litwareinc\davidlongmire"
    Test-CsIm -TargetFqdn "atl-cs-001.litwareinc.com" -SenderSipAddress "sip:kenmyer@litwareinc.com" -SenderCredential $credential1 -ReceiverSipAddress "sip:davidlongmire@litwareinc.com" -ReceiverCredential $credential2

<span data-ttu-id="f63ce-125">Para obter mais informações, consulte a documentação de ajuda para o cmdlet [Test-CsIM](https://docs.microsoft.com/powershell/module/skype/Test-CsIM) .</span><span class="sxs-lookup"><span data-stu-id="f63ce-125">For more information, see the Help documentation for the [Test-CsIM](https://docs.microsoft.com/powershell/module/skype/Test-CsIM) cmdlet.</span></span>

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="f63ce-126">Determinando o sucesso ou a falha</span><span class="sxs-lookup"><span data-stu-id="f63ce-126">Determining Success or Failure</span></span>

<span data-ttu-id="f63ce-127">Se os dois usuários podem concluir uma sessão de mensagens instantâneas, você receberá uma saída semelhante a essa, com a propriedade Result marcada como **Success:**</span><span class="sxs-lookup"><span data-stu-id="f63ce-127">If the two users can complete an instant messaging session, you'll receive output similar to this, with the Result property marked as **Success:**</span></span>

<span data-ttu-id="f63ce-128">TargetFqdn: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="f63ce-128">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="f63ce-129">Resultado: êxito</span><span class="sxs-lookup"><span data-stu-id="f63ce-129">Result : Success</span></span>

<span data-ttu-id="f63ce-130">Latência: 00:00:06.6630911</span><span class="sxs-lookup"><span data-stu-id="f63ce-130">Latency : 00:00:06.6630911</span></span>

<span data-ttu-id="f63ce-131">Erros</span><span class="sxs-lookup"><span data-stu-id="f63ce-131">Error :</span></span>

<span data-ttu-id="f63ce-132">Diagnóstico</span><span class="sxs-lookup"><span data-stu-id="f63ce-132">Diagnosis :</span></span>

<span data-ttu-id="f63ce-133">Se os usuários de teste não puderem concluir a sessão, o resultado será mostrado como falha, e informações adicionais serão registradas nas propriedades de erro e diagnóstico:</span><span class="sxs-lookup"><span data-stu-id="f63ce-133">If the test users can't complete the session, the Result will be shown as Failure, and additional information will be recorded in the Error and Diagnosis properties:</span></span>

<span data-ttu-id="f63ce-134">TargetFqdn: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="f63ce-134">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="f63ce-135">Resultado: falha</span><span class="sxs-lookup"><span data-stu-id="f63ce-135">Result : Failure</span></span>

<span data-ttu-id="f63ce-136">Latência: 00:00:00</span><span class="sxs-lookup"><span data-stu-id="f63ce-136">Latency : 00:00:00</span></span>

<span data-ttu-id="f63ce-137">Erro: 504, tempo limite do servidor</span><span class="sxs-lookup"><span data-stu-id="f63ce-137">Error : 504, Server time-out</span></span>

<span data-ttu-id="f63ce-138">Diagnóstico: ErrorCode = 2, Source = ATL-cs-001. litwareinc. com, razão = Confira</span><span class="sxs-lookup"><span data-stu-id="f63ce-138">Diagnosis : ErrorCode=2, Source=atl-cs-001.litwareinc.com,Reason=See</span></span>

<span data-ttu-id="f63ce-139">código de resposta e frase de motivo.</span><span class="sxs-lookup"><span data-stu-id="f63ce-139">response code and reason phrase.</span></span>

<span data-ttu-id="f63ce-140">Microsoft. RTC. Signaling. DiagnosticHeader</span><span class="sxs-lookup"><span data-stu-id="f63ce-140">Microsoft.Rtc.Signaling.DiagnosticHeader</span></span>

<span data-ttu-id="f63ce-141">Por exemplo, a saída anterior diz que o teste falhou porque o usuário especificado não pôde ser encontrado.</span><span class="sxs-lookup"><span data-stu-id="f63ce-141">For example, the previous output states that the test failed because the specified user couldn't be found.</span></span> <span data-ttu-id="f63ce-142">Você pode determinar se um endereço SIP é válido (e se o usuário atribuído ao endereço SIP foi habilitado para o Lync Server) executando este comando:</span><span class="sxs-lookup"><span data-stu-id="f63ce-142">You can determine whether a SIP address is valid (and whether the user assigned that SIP address was enabled for Lync Server) by running this command:</span></span>

    Get-CsUser "Ken Myer" | Select-Object SipAddress, Enabled

<span data-ttu-id="f63ce-143">Se Test-CsIM falhar, talvez você queira executar novamente o teste, desta vez, incluindo o parâmetro Verbose:</span><span class="sxs-lookup"><span data-stu-id="f63ce-143">If Test-CsIM fails, then you might want to rerun the test, this time including the Verbose parameter:</span></span>

    Test-CsIM -TargetFqdn "atl-cs-001.litwareinc.com" -Verbose

<span data-ttu-id="f63ce-144">Quando o parâmetro Verbose é incluído, Test-CsIM retornará uma conta passo a passo de cada ação que tentou quando verificou a capacidade dos dois usuários de teste participarem da sessão de IM.</span><span class="sxs-lookup"><span data-stu-id="f63ce-144">When the Verbose parameter is included, Test-CsIM will return a step-by-step account of each action it tried when it checked the ability of the two test users to take part in an IM session.</span></span> <span data-ttu-id="f63ce-145">Por exemplo, veja a seguir um exemplo de saída que ocorre quando um conjunto incorreto de credenciais de usuário (neste caso, uma senha incorreta) é fornecido para Test-CsIM:</span><span class="sxs-lookup"><span data-stu-id="f63ce-145">For example, here’s sample output that occurs when an incorrect set of user credentials (in this case, an incorrect password) is supplied to Test-CsIM:</span></span>

<span data-ttu-id="f63ce-146">Enviando solicitação de registro:</span><span class="sxs-lookup"><span data-stu-id="f63ce-146">Sending Registration request :</span></span>

<span data-ttu-id="f63ce-147">FQDN de destino = atl-cs-011.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="f63ce-147">Target Fqdn = atl-cs-011.litwareinc.com</span></span>

<span data-ttu-id="f63ce-148">Endereço SIP do usuário = sip:kenmyer@litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="f63ce-148">User Sip Address = sip:kenmyer@litwareinc.com</span></span>

<span data-ttu-id="f63ce-149">Porta do registrador = 5061</span><span class="sxs-lookup"><span data-stu-id="f63ce-149">Registrar Port = 5061</span></span>

<span data-ttu-id="f63ce-150">O tipo de autenticação ' IWA ' é selecionado.</span><span class="sxs-lookup"><span data-stu-id="f63ce-150">Auth Type 'IWA' is selected.</span></span>

<span data-ttu-id="f63ce-151">Acerto de registro em relação ao SIP/ATL-cs-001. litwareinc. com</span><span class="sxs-lookup"><span data-stu-id="f63ce-151">Registration hit against sip/atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="f63ce-152">Atividade ' Register ' concluída em ' 0, 601795 ' segundos.</span><span class="sxs-lookup"><span data-stu-id="f63ce-152">'Register' activity completed in '0.0601795' secs.</span></span>

<span data-ttu-id="f63ce-153">Uma exceção ' o logon foi negado.</span><span class="sxs-lookup"><span data-stu-id="f63ce-153">An exception 'The log on was denied.</span></span> <span data-ttu-id="f63ce-154">Verifique se as credenciais corretas estão sendo usadas e se a conta está ativa.</span><span class="sxs-lookup"><span data-stu-id="f63ce-154">Check that the correct credentials are being used and the account is active.'</span></span> <span data-ttu-id="f63ce-155">ocorrido durante o fluxo de trabalho.</span><span class="sxs-lookup"><span data-stu-id="f63ce-155">occurred during the Workflow.</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="f63ce-156">Motivos pelos quais o teste pode ter falhado</span><span class="sxs-lookup"><span data-stu-id="f63ce-156">Reasons Why the Test Might Have Failed</span></span>

<span data-ttu-id="f63ce-157">Aqui estão alguns motivos comuns para que Test-CsIM possa falhar:</span><span class="sxs-lookup"><span data-stu-id="f63ce-157">Here are some common reasons why Test-CsIM might fail:</span></span>

  - <span data-ttu-id="f63ce-158">Você especificou uma conta de usuário que não é válida.</span><span class="sxs-lookup"><span data-stu-id="f63ce-158">You specified a user account that is not valid.</span></span> <span data-ttu-id="f63ce-159">Você pode verificar se uma conta de usuário existe executando um comando semelhante a este:</span><span class="sxs-lookup"><span data-stu-id="f63ce-159">You can verify that a user account exists by running a command similar to this:</span></span>
    
        Get-CsUser "sip:kenmyer@litwareinc.com"

  - <span data-ttu-id="f63ce-160">A conta de usuário é válida, mas a conta não está habilitada no momento para o Lync Server.</span><span class="sxs-lookup"><span data-stu-id="f63ce-160">The user account is valid, but the account is currently not enabled for Lync Server.</span></span> <span data-ttu-id="f63ce-161">Para verificar se uma conta de usuário está habilitada para o Lync Server, execute um comando semelhante ao seguinte:</span><span class="sxs-lookup"><span data-stu-id="f63ce-161">To verify that a user account is enabled for Lync Server, run a command similar to the following:</span></span>
    
        Get-CsUser "sip:kenmyer@litwareinc.com" | Select-Object Enabled
    
    <span data-ttu-id="f63ce-162">Se a propriedade Enabled estiver definida como false, isso significa que o usuário não está habilitado para o Lync Server no momento.</span><span class="sxs-lookup"><span data-stu-id="f63ce-162">If the Enabled property is set to False that means that the user is currently not enabled for Lync Server.</span></span>

  - <span data-ttu-id="f63ce-163">O serviço de mensagens instantâneas pode não estar disponível.</span><span class="sxs-lookup"><span data-stu-id="f63ce-163">The instant messaging service might not be available.</span></span> <span data-ttu-id="f63ce-164">Com o Lync Server, você pode configurar o sistema para que o IM não fique disponível se o banco de dados de arquivamento não puder ser acessado.</span><span class="sxs-lookup"><span data-stu-id="f63ce-164">With Lync Server, you can configure the system so that IM is not available if the archiving database cannot be accessed.</span></span> <span data-ttu-id="f63ce-165">Você pode verificar se está executando um comando semelhante ao seguinte:</span><span class="sxs-lookup"><span data-stu-id="f63ce-165">You can verify that by running a command similar to the following:</span></span>
    
        Get-CsArchivingConfiguration -Identity "atl-cs-001.litwareinc.com" | Select-Object BlockOnArchiveFailure
    
    <span data-ttu-id="f63ce-166">Se BlockOnArchiveFailure estiver definido como true, você deverá determinar se o banco de dados de arquivamento está disponível ou não.</span><span class="sxs-lookup"><span data-stu-id="f63ce-166">If BlockOnArchiveFailure is set to True, then you should determine whether or not the archiving database is available.</span></span> <span data-ttu-id="f63ce-167">Você pode retornar os locais dos seus bancos de dados de arquivamento usando o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="f63ce-167">You can return the locations of your archiving databases by using the following command:</span></span>
    
        Get-CsService -ArchivingDatabase

  - <span data-ttu-id="f63ce-168">O servidor de arquivamento pode não estar disponível.</span><span class="sxs-lookup"><span data-stu-id="f63ce-168">The Archiving server might not be available.</span></span> <span data-ttu-id="f63ce-169">Você pode recuperar o FQDN dos seus servidores de arquivamento usando este comando:</span><span class="sxs-lookup"><span data-stu-id="f63ce-169">You can retrieve the FQDN of your Archiving servers by using this command:</span></span>
    
        Get-CsService -ArchivingServer
    
    <span data-ttu-id="f63ce-170">Você pode fazer o ping no servidor apropriado para verificar se ele está disponível.</span><span class="sxs-lookup"><span data-stu-id="f63ce-170">You can then ping the appropriate server to verify that it is available.</span></span> <span data-ttu-id="f63ce-171">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="f63ce-171">For example:</span></span>
    
        ping atl-archiving-001.litwareinc.com

</div>

</div>

<span> </span>

</div>

</div>

</div>

