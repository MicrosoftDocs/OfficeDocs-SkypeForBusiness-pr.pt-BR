---
title: 'Lync Server 2013: testar a capacidade de mensagens instantâneas entre dois usuários'
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
ms.openlocfilehash: 145a2849d8b87f0f19559583e94edb5e895f89db
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48500488"
---
# <a name="testing-ability-to-im-between-two-users-in-lync-server-2013"></a><span data-ttu-id="d7ac4-102">Testando a capacidade de mensagens instantâneas entre dois usuários no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d7ac4-102">Testing ability to IM between two users in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d7ac4-103">_**Última modificação do tópico:** 2014-06-05_</span><span class="sxs-lookup"><span data-stu-id="d7ac4-103">_**Topic Last Modified:** 2014-06-05_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d7ac4-104">Agenda de verificação</span><span class="sxs-lookup"><span data-stu-id="d7ac4-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="d7ac4-105">Diariamente</span><span class="sxs-lookup"><span data-stu-id="d7ac4-105">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d7ac4-106">Ferramenta de teste</span><span class="sxs-lookup"><span data-stu-id="d7ac4-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="d7ac4-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="d7ac4-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d7ac4-108">Permissões obrigatórias</span><span class="sxs-lookup"><span data-stu-id="d7ac4-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="d7ac4-109">Ao executar localmente usando o Shell de gerenciamento do Lync Server, os usuários devem ser membros do grupo de segurança RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="d7ac4-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="d7ac4-110">Quando executado usando uma instância remota do Windows PowerShell, os usuários devem receber uma função RBAC que tenha permissão para executar o cmdlet Test-CsIM.</span><span class="sxs-lookup"><span data-stu-id="d7ac4-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsIM cmdlet.</span></span> <span data-ttu-id="d7ac4-111">Para ver uma lista de todas as funções RBAC que podem usar este cmdlet, execute o seguinte comando no prompt do Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="d7ac4-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsIM&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="d7ac4-112">Descrição</span><span class="sxs-lookup"><span data-stu-id="d7ac4-112">Description</span></span>

<span data-ttu-id="d7ac4-113">O cmdlet Test-CsIM verifica se um par de usuários de teste podem trocar mensagens instantâneas.</span><span class="sxs-lookup"><span data-stu-id="d7ac4-113">The Test-CsIM cmdlet verifies that a pair of test users can exchange instant messages.</span></span> <span data-ttu-id="d7ac4-114">Quando chamado, o cmdlet Test-CsIM começa tentando fazer logon em um par de usuários de teste no Lync Server.</span><span class="sxs-lookup"><span data-stu-id="d7ac4-114">When called, the Test-CsIM cmdlet starts off by trying to log on a pair of test users to Lync Server.</span></span> <span data-ttu-id="d7ac4-115">Supondo que os dois logons sejam bem-sucedidos, o cmdlet iniciará uma sessão de IM entre os dois usuários de teste.</span><span class="sxs-lookup"><span data-stu-id="d7ac4-115">Assuming the two logons are successful, the cmdlet then starts an IM session between the two test users.</span></span> <span data-ttu-id="d7ac4-116">(O usuário 1 convida o usuário 2 para uma sessão de IM e o usuário 2 aceita o convite.) Após verificar que as mensagens podem ser trocadas entre os dois usuários, Test-CsIM, em seguida, encerra a sessão de mensagens instantâneas e registra os dois usuários fora do sistema.</span><span class="sxs-lookup"><span data-stu-id="d7ac4-116">(User 1 invites User 2 to an IM session, and User 2 accepts the invitation.) After verifying that messages can be exchanged between the two users, Test-CsIM then ends the IM session and logs both users off the system.</span></span>

<span data-ttu-id="d7ac4-117">Para obter mais informações, consulte a documentação de ajuda para o cmdlet [Test-CsIM](https://docs.microsoft.com/powershell/module/skype/Test-CsIM) .</span><span class="sxs-lookup"><span data-stu-id="d7ac4-117">For more information, see the Help documentation for the [Test-CsIM](https://docs.microsoft.com/powershell/module/skype/Test-CsIM) cmdlet.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="d7ac4-118">Executar o teste</span><span class="sxs-lookup"><span data-stu-id="d7ac4-118">Running the Test</span></span>

<span data-ttu-id="d7ac4-119">O cmdlet Test-CsIM pode ser executado usando um par de contas de teste pré-configuradas (Confira Configurando contas de teste para executar testes do Lync Server) ou as contas de dois usuários que estão habilitados para o Lync Server.</span><span class="sxs-lookup"><span data-stu-id="d7ac4-119">The Test-CsIM cmdlet can be run using either a pair of preconfigured test accounts (see Setting Up Test Accounts for Running Lync Server Tests) or the accounts of any two users who are enabled for Lync Server.</span></span> <span data-ttu-id="d7ac4-120">Para executar essa verificação usando contas de teste, basta especificar o FQDN do pool do Lync Server que está sendo testado.</span><span class="sxs-lookup"><span data-stu-id="d7ac4-120">To run this check using test accounts, you just have to specify the FQDN of the Lync Server pool being tested.</span></span> <span data-ttu-id="d7ac4-121">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="d7ac4-121">For example:</span></span>

    Test-CsIM -TargetFqdn "atl-cs-001.litwareinc.com"

<span data-ttu-id="d7ac4-122">Para executar essa verificação usando contas de usuário reais, você deve criar dois objetos de credenciais do Windows PowerShell (objetos que contêm o nome da conta e a senha) para cada conta.</span><span class="sxs-lookup"><span data-stu-id="d7ac4-122">To run this check using actual user accounts, you must create two Windows PowerShell credentials objects (objects that contain the account name and password) for each account.</span></span> <span data-ttu-id="d7ac4-123">Em seguida, você deve incluir esses objetos de credenciais e os endereços SIP das duas contas ao chamar Test-CsIM:</span><span class="sxs-lookup"><span data-stu-id="d7ac4-123">You must then include those credentials objects and the SIP addresses of the two accounts when you call Test-CsIM:</span></span>

    $credential1 = Get-Credential "litwareinc\kenmyer"
    $credential2 = Get-Credential "litwareinc\davidlongmire"
    Test-CsIm -TargetFqdn "atl-cs-001.litwareinc.com" -SenderSipAddress "sip:kenmyer@litwareinc.com" -SenderCredential $credential1 -ReceiverSipAddress "sip:davidlongmire@litwareinc.com" -ReceiverCredential $credential2

<span data-ttu-id="d7ac4-124">Para obter mais informações, consulte a documentação de ajuda para o cmdlet [Test-CsIM](https://docs.microsoft.com/powershell/module/skype/Test-CsIM) .</span><span class="sxs-lookup"><span data-stu-id="d7ac4-124">For more information, see the Help documentation for the [Test-CsIM](https://docs.microsoft.com/powershell/module/skype/Test-CsIM) cmdlet.</span></span>

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="d7ac4-125">Determinando o sucesso ou a falha</span><span class="sxs-lookup"><span data-stu-id="d7ac4-125">Determining Success or Failure</span></span>

<span data-ttu-id="d7ac4-126">Se os dois usuários podem concluir uma sessão de mensagens instantâneas, você receberá uma saída semelhante a essa, com a propriedade Result marcada como **Success:**</span><span class="sxs-lookup"><span data-stu-id="d7ac4-126">If the two users can complete an instant messaging session, you'll receive output similar to this, with the Result property marked as **Success:**</span></span>

<span data-ttu-id="d7ac4-127">TargetFqdn: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="d7ac4-127">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="d7ac4-128">Resultado: êxito</span><span class="sxs-lookup"><span data-stu-id="d7ac4-128">Result : Success</span></span>

<span data-ttu-id="d7ac4-129">Latência: 00:00:06.6630911</span><span class="sxs-lookup"><span data-stu-id="d7ac4-129">Latency : 00:00:06.6630911</span></span>

<span data-ttu-id="d7ac4-130">Erros</span><span class="sxs-lookup"><span data-stu-id="d7ac4-130">Error :</span></span>

<span data-ttu-id="d7ac4-131">Diagnóstico</span><span class="sxs-lookup"><span data-stu-id="d7ac4-131">Diagnosis :</span></span>

<span data-ttu-id="d7ac4-132">Se os usuários de teste não puderem concluir a sessão, o resultado será mostrado como falha, e informações adicionais serão registradas nas propriedades de erro e diagnóstico:</span><span class="sxs-lookup"><span data-stu-id="d7ac4-132">If the test users can't complete the session, the Result will be shown as Failure, and additional information will be recorded in the Error and Diagnosis properties:</span></span>

<span data-ttu-id="d7ac4-133">TargetFqdn: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="d7ac4-133">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="d7ac4-134">Resultado: falha</span><span class="sxs-lookup"><span data-stu-id="d7ac4-134">Result : Failure</span></span>

<span data-ttu-id="d7ac4-135">Latência: 00:00:00</span><span class="sxs-lookup"><span data-stu-id="d7ac4-135">Latency : 00:00:00</span></span>

<span data-ttu-id="d7ac4-136">Erro: 504, tempo limite do servidor</span><span class="sxs-lookup"><span data-stu-id="d7ac4-136">Error : 504, Server time-out</span></span>

<span data-ttu-id="d7ac4-137">Diagnóstico: ErrorCode = 2, Source = ATL-cs-001. litwareinc. com, razão = Confira</span><span class="sxs-lookup"><span data-stu-id="d7ac4-137">Diagnosis : ErrorCode=2, Source=atl-cs-001.litwareinc.com,Reason=See</span></span>

<span data-ttu-id="d7ac4-138">código de resposta e frase de motivo.</span><span class="sxs-lookup"><span data-stu-id="d7ac4-138">response code and reason phrase.</span></span>

<span data-ttu-id="d7ac4-139">Microsoft. RTC. Signaling. DiagnosticHeader</span><span class="sxs-lookup"><span data-stu-id="d7ac4-139">Microsoft.Rtc.Signaling.DiagnosticHeader</span></span>

<span data-ttu-id="d7ac4-140">Por exemplo, a saída anterior diz que o teste falhou porque o usuário especificado não pôde ser encontrado.</span><span class="sxs-lookup"><span data-stu-id="d7ac4-140">For example, the previous output states that the test failed because the specified user couldn't be found.</span></span> <span data-ttu-id="d7ac4-141">Você pode determinar se um endereço SIP é válido (e se o usuário atribuído ao endereço SIP foi habilitado para o Lync Server) executando este comando:</span><span class="sxs-lookup"><span data-stu-id="d7ac4-141">You can determine whether a SIP address is valid (and whether the user assigned that SIP address was enabled for Lync Server) by running this command:</span></span>

    Get-CsUser "Ken Myer" | Select-Object SipAddress, Enabled

<span data-ttu-id="d7ac4-142">Se Test-CsIM falhar, talvez você queira executar novamente o teste, desta vez, incluindo o parâmetro Verbose:</span><span class="sxs-lookup"><span data-stu-id="d7ac4-142">If Test-CsIM fails, then you might want to rerun the test, this time including the Verbose parameter:</span></span>

    Test-CsIM -TargetFqdn "atl-cs-001.litwareinc.com" -Verbose

<span data-ttu-id="d7ac4-143">Quando o parâmetro Verbose é incluído, Test-CsIM retornará uma conta passo a passo de cada ação que tentou quando verificou a capacidade dos dois usuários de teste participarem da sessão de IM.</span><span class="sxs-lookup"><span data-stu-id="d7ac4-143">When the Verbose parameter is included, Test-CsIM will return a step-by-step account of each action it tried when it checked the ability of the two test users to take part in an IM session.</span></span> <span data-ttu-id="d7ac4-144">Por exemplo, veja a seguir um exemplo de saída que ocorre quando um conjunto incorreto de credenciais de usuário (neste caso, uma senha incorreta) é fornecido para Test-CsIM:</span><span class="sxs-lookup"><span data-stu-id="d7ac4-144">For example, here’s sample output that occurs when an incorrect set of user credentials (in this case, an incorrect password) is supplied to Test-CsIM:</span></span>

<span data-ttu-id="d7ac4-145">Enviando solicitação de registro:</span><span class="sxs-lookup"><span data-stu-id="d7ac4-145">Sending Registration request :</span></span>

<span data-ttu-id="d7ac4-146">FQDN de destino = atl-cs-011.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="d7ac4-146">Target Fqdn = atl-cs-011.litwareinc.com</span></span>

<span data-ttu-id="d7ac4-147">Endereço SIP do usuário = sip:kenmyer@litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="d7ac4-147">User Sip Address = sip:kenmyer@litwareinc.com</span></span>

<span data-ttu-id="d7ac4-148">Porta do registrador = 5061</span><span class="sxs-lookup"><span data-stu-id="d7ac4-148">Registrar Port = 5061</span></span>

<span data-ttu-id="d7ac4-149">O tipo de autenticação ' IWA ' é selecionado.</span><span class="sxs-lookup"><span data-stu-id="d7ac4-149">Auth Type 'IWA' is selected.</span></span>

<span data-ttu-id="d7ac4-150">Acerto de registro em relação ao SIP/ATL-cs-001. litwareinc. com</span><span class="sxs-lookup"><span data-stu-id="d7ac4-150">Registration hit against sip/atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="d7ac4-151">Atividade ' Register ' concluída em ' 0, 601795 ' segundos.</span><span class="sxs-lookup"><span data-stu-id="d7ac4-151">'Register' activity completed in '0.0601795' secs.</span></span>

<span data-ttu-id="d7ac4-152">Uma exceção ' o logon foi negado.</span><span class="sxs-lookup"><span data-stu-id="d7ac4-152">An exception 'The log on was denied.</span></span> <span data-ttu-id="d7ac4-153">Verifique se as credenciais corretas estão sendo usadas e se a conta está ativa.</span><span class="sxs-lookup"><span data-stu-id="d7ac4-153">Check that the correct credentials are being used and the account is active.'</span></span> <span data-ttu-id="d7ac4-154">ocorrido durante o fluxo de trabalho.</span><span class="sxs-lookup"><span data-stu-id="d7ac4-154">occurred during the Workflow.</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="d7ac4-155">Motivos pelos quais o teste pode ter falhado</span><span class="sxs-lookup"><span data-stu-id="d7ac4-155">Reasons Why the Test Might Have Failed</span></span>

<span data-ttu-id="d7ac4-156">Aqui estão alguns motivos comuns para que Test-CsIM possa falhar:</span><span class="sxs-lookup"><span data-stu-id="d7ac4-156">Here are some common reasons why Test-CsIM might fail:</span></span>

  - <span data-ttu-id="d7ac4-157">Você especificou uma conta de usuário que não é válida.</span><span class="sxs-lookup"><span data-stu-id="d7ac4-157">You specified a user account that is not valid.</span></span> <span data-ttu-id="d7ac4-158">Você pode verificar se uma conta de usuário existe executando um comando semelhante a este:</span><span class="sxs-lookup"><span data-stu-id="d7ac4-158">You can verify that a user account exists by running a command similar to this:</span></span>
    
        Get-CsUser "sip:kenmyer@litwareinc.com"

  - <span data-ttu-id="d7ac4-159">A conta de usuário é válida, mas a conta não está habilitada no momento para o Lync Server.</span><span class="sxs-lookup"><span data-stu-id="d7ac4-159">The user account is valid, but the account is currently not enabled for Lync Server.</span></span> <span data-ttu-id="d7ac4-160">Para verificar se uma conta de usuário está habilitada para o Lync Server, execute um comando semelhante ao seguinte:</span><span class="sxs-lookup"><span data-stu-id="d7ac4-160">To verify that a user account is enabled for Lync Server, run a command similar to the following:</span></span>
    
        Get-CsUser "sip:kenmyer@litwareinc.com" | Select-Object Enabled
    
    <span data-ttu-id="d7ac4-161">Se a propriedade Enabled estiver definida como false, isso significa que o usuário não está habilitado para o Lync Server no momento.</span><span class="sxs-lookup"><span data-stu-id="d7ac4-161">If the Enabled property is set to False that means that the user is currently not enabled for Lync Server.</span></span>

  - <span data-ttu-id="d7ac4-162">O serviço de mensagens instantâneas pode não estar disponível.</span><span class="sxs-lookup"><span data-stu-id="d7ac4-162">The instant messaging service might not be available.</span></span> <span data-ttu-id="d7ac4-163">Com o Lync Server, você pode configurar o sistema para que o IM não fique disponível se o banco de dados de arquivamento não puder ser acessado.</span><span class="sxs-lookup"><span data-stu-id="d7ac4-163">With Lync Server, you can configure the system so that IM is not available if the archiving database cannot be accessed.</span></span> <span data-ttu-id="d7ac4-164">Você pode verificar se está executando um comando semelhante ao seguinte:</span><span class="sxs-lookup"><span data-stu-id="d7ac4-164">You can verify that by running a command similar to the following:</span></span>
    
        Get-CsArchivingConfiguration -Identity "atl-cs-001.litwareinc.com" | Select-Object BlockOnArchiveFailure
    
    <span data-ttu-id="d7ac4-165">Se BlockOnArchiveFailure estiver definido como true, você deverá determinar se o banco de dados de arquivamento está disponível ou não.</span><span class="sxs-lookup"><span data-stu-id="d7ac4-165">If BlockOnArchiveFailure is set to True, then you should determine whether or not the archiving database is available.</span></span> <span data-ttu-id="d7ac4-166">Você pode retornar os locais dos seus bancos de dados de arquivamento usando o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="d7ac4-166">You can return the locations of your archiving databases by using the following command:</span></span>
    
        Get-CsService -ArchivingDatabase

  - <span data-ttu-id="d7ac4-167">O servidor de arquivamento pode não estar disponível.</span><span class="sxs-lookup"><span data-stu-id="d7ac4-167">The Archiving server might not be available.</span></span> <span data-ttu-id="d7ac4-168">Você pode recuperar o FQDN dos seus servidores de arquivamento usando este comando:</span><span class="sxs-lookup"><span data-stu-id="d7ac4-168">You can retrieve the FQDN of your Archiving servers by using this command:</span></span>
    
        Get-CsService -ArchivingServer
    
    <span data-ttu-id="d7ac4-169">Você pode fazer o ping no servidor apropriado para verificar se ele está disponível.</span><span class="sxs-lookup"><span data-stu-id="d7ac4-169">You can then ping the appropriate server to verify that it is available.</span></span> <span data-ttu-id="d7ac4-170">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="d7ac4-170">For example:</span></span>
    
        ping atl-archiving-001.litwareinc.com

</div>

</div>

<span> </span>

</div>

</div>

</div>

