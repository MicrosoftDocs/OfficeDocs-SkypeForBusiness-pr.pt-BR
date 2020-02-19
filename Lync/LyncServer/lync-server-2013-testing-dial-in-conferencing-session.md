---
title: 'Lync Server 2013: testar sessão de conferência discada'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing dial-in conferencing session
ms:assetid: 6c505be5-5af7-450c-b3ca-10d9122bee5c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn743834(v=OCS.15)
ms:contentKeyID: 63969613
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 11a5126d0555e39c5e0c4637a70939227c787299
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42141437"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="testing-dial-in-conferencing-session-in-lync-server-2013"></a><span data-ttu-id="34ab0-102">Testando a sessão de conferência discada no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="34ab0-102">Testing dial-in conferencing session in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="34ab0-103">_**Última modificação do tópico:** 2014-06-05_</span><span class="sxs-lookup"><span data-stu-id="34ab0-103">_**Topic Last Modified:** 2014-06-05_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="34ab0-104">Agenda de verificação</span><span class="sxs-lookup"><span data-stu-id="34ab0-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="34ab0-105">Diariamente</span><span class="sxs-lookup"><span data-stu-id="34ab0-105">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="34ab0-106">Ferramenta de teste</span><span class="sxs-lookup"><span data-stu-id="34ab0-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="34ab0-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="34ab0-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="34ab0-108">Permissões obrigatórias</span><span class="sxs-lookup"><span data-stu-id="34ab0-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="34ab0-109">Ao executar localmente usando o Shell de gerenciamento do Lync Server, os usuários devem ser membros do grupo de segurança RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="34ab0-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="34ab0-110">Quando executado usando uma instância remota do Windows PowerShell, os usuários devem receber uma função RBAC que tenha permissão para executar o cmdlet Test-CsDialInConferencing.</span><span class="sxs-lookup"><span data-stu-id="34ab0-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsDialInConferencing cmdlet.</span></span> <span data-ttu-id="34ab0-111">Para ver uma lista de todas as funções RBAC que podem usar este cmdlet, execute o seguinte comando no prompt do Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="34ab0-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsDialInConferencing&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="34ab0-112">Descrição</span><span class="sxs-lookup"><span data-stu-id="34ab0-112">Description</span></span>

<span data-ttu-id="34ab0-113">O cmdlet Test-CsDialInConferencing verifica se um usuário pode participar de uma conferência discada.</span><span class="sxs-lookup"><span data-stu-id="34ab0-113">The Test-CsDialInConferencing cmdlet verifies whether a user can participate in a dial-in conference.</span></span> <span data-ttu-id="34ab0-114">O Test-CsDialInConferencing funciona tentando registrar um usuário de teste no sistema.</span><span class="sxs-lookup"><span data-stu-id="34ab0-114">Test-CsDialInConferencing works by trying to log a test user onto the system.</span></span> <span data-ttu-id="34ab0-115">Se o logon for bem-sucedido, o cmdlet usará as credenciais do usuário e as permissões para tentar todos os números de acesso de conferência discada disponíveis.</span><span class="sxs-lookup"><span data-stu-id="34ab0-115">If the logon succeeds, the cmdlet will then use the user’s credentials and permissions to try all of the available dial-in conferencing access numbers.</span></span> <span data-ttu-id="34ab0-116">O sucesso ou a falha de cada tentativa de discagem será observado e, em seguida, o usuário de teste será desconectado do Lync Server. Test-CsDialInConferencing verifica apenas se as conexões apropriadas podem ser feitas.</span><span class="sxs-lookup"><span data-stu-id="34ab0-116">The success or failure of each dial-in try will be noted, then the test user will be logged off from Lync Server.Test-CsDialInConferencing only verifies that the appropriate connections can be made.</span></span> <span data-ttu-id="34ab0-117">No entanto, o cmdlet não faz chamadas telefônicas nem cria conferências discadas que outros usuários podem participar.</span><span class="sxs-lookup"><span data-stu-id="34ab0-117">The cmdlet does not actually make any phone calls or create any dial-in conferences that other users can join.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="34ab0-118">Executar o teste</span><span class="sxs-lookup"><span data-stu-id="34ab0-118">Running the test</span></span>

<span data-ttu-id="34ab0-119">O cmdlet Test-CsDialInConferencing pode ser executado usando uma conta de teste pré-configurada (consulte Configurando contas de teste para executar testes do Lync Server) ou a conta de qualquer usuário habilitado para o Lync Server.</span><span class="sxs-lookup"><span data-stu-id="34ab0-119">The Test-CsDialInConferencing cmdlet can be run using either a preconfigured test account (see Setting Up Test Accounts for Running Lync Server Tests) or the account of any user who is enabled for Lync Server.</span></span> <span data-ttu-id="34ab0-120">Para executar esta verificação usando uma conta de teste, basta especificar o FQDN do pool do Lync Server que está sendo testado.</span><span class="sxs-lookup"><span data-stu-id="34ab0-120">To run this check using a test account, you just have to specify the FQDN of the Lync Server pool being tested.</span></span> <span data-ttu-id="34ab0-121">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="34ab0-121">For example:</span></span>

    Test-CsDialInConferencing -TargetFqdn "atl-cs-001.litwareinc.com" 

<span data-ttu-id="34ab0-122">Para executar essa verificação usando uma conta de usuário real, você deve criar um objeto de credenciais do Windows PowerShell que contenha o nome da conta e a senha.</span><span class="sxs-lookup"><span data-stu-id="34ab0-122">To run this check using an actual user account, you must create a Windows PowerShell credentials object that contains the account name and password.</span></span> <span data-ttu-id="34ab0-123">Em seguida, você deve incluir o objeto Credentials e o endereço SIP da conta na chamada Test-CsDialInConferencing:</span><span class="sxs-lookup"><span data-stu-id="34ab0-123">You must then include that credentials object and the account SIP address the calling Test-CsDialInConferencing:</span></span>

    $credential = Get-Credential "litwareinc\kenmyer"
    Test-CsDialInConferencing -TargetFqdn atl-cs-001.litwareinc.com" -UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential

<span data-ttu-id="34ab0-124">Para obter mais informações, consulte a documentação de ajuda para o cmdlet [Test-CsDialInConferencing](https://docs.microsoft.com/powershell/module/skype/Test-CsDialInConferencing) .</span><span class="sxs-lookup"><span data-stu-id="34ab0-124">For more information, see the Help documentation for the [Test-CsDialInConferencing](https://docs.microsoft.com/powershell/module/skype/Test-CsDialInConferencing) cmdlet.</span></span>

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="34ab0-125">Determinando o sucesso ou a falha</span><span class="sxs-lookup"><span data-stu-id="34ab0-125">Determining success or failure</span></span>

<span data-ttu-id="34ab0-126">Se o usuário especificado puder fazer logon no Lync Server e fizer uma conexão usando um dos números de acesso de conferência discada disponíveis, você receberá uma saída semelhante a esta, com a propriedade Result marcada como **Success:**</span><span class="sxs-lookup"><span data-stu-id="34ab0-126">If the specified user can log on to Lync Server and then make a connection using one of the available dial-in conferencing access numbers, then you'll receive output similar to this, with the Result property marked as **Success:**</span></span>

<span data-ttu-id="34ab0-127">TargetFqdn: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="34ab0-127">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="34ab0-128">Resultado: êxito</span><span class="sxs-lookup"><span data-stu-id="34ab0-128">Result : Success</span></span>

<span data-ttu-id="34ab0-129">Latência: 00:00:06.8630376</span><span class="sxs-lookup"><span data-stu-id="34ab0-129">Latency : 00:00:06.8630376</span></span>

<span data-ttu-id="34ab0-130">Erros</span><span class="sxs-lookup"><span data-stu-id="34ab0-130">Error :</span></span>

<span data-ttu-id="34ab0-131">Diagnóstico</span><span class="sxs-lookup"><span data-stu-id="34ab0-131">Diagnosis :</span></span>

<span data-ttu-id="34ab0-132">Se o usuário especificado não puder fazer essa conexão, o resultado será mostrado como falha, e informações adicionais serão registradas nas propriedades de erro e diagnóstico:</span><span class="sxs-lookup"><span data-stu-id="34ab0-132">If the specified user can't make this connection, then the Result will be shown as Failure, and additional information will be recorded in the Error and Diagnosis properties:</span></span>

<span data-ttu-id="34ab0-133">TargetFqdn: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="34ab0-133">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="34ab0-134">Resultado: falha</span><span class="sxs-lookup"><span data-stu-id="34ab0-134">Result : Failure</span></span>

<span data-ttu-id="34ab0-135">Latência: 00:00:00</span><span class="sxs-lookup"><span data-stu-id="34ab0-135">Latency : 00:00:00</span></span>

<span data-ttu-id="34ab0-136">Erro: o logon foi negado.</span><span class="sxs-lookup"><span data-stu-id="34ab0-136">Error : The log on was denied.</span></span> <span data-ttu-id="34ab0-137">Verifique se as credenciais adequadas estão</span><span class="sxs-lookup"><span data-stu-id="34ab0-137">Check that the proper credentials are</span></span>

<span data-ttu-id="34ab0-138">sendo usado e a conta está ativa.</span><span class="sxs-lookup"><span data-stu-id="34ab0-138">being used and the account is active.</span></span>

<span data-ttu-id="34ab0-139">Exceção interna: NegotiateSecurityAssociation falhou, erro:-</span><span class="sxs-lookup"><span data-stu-id="34ab0-139">Inner Exception:NegotiateSecurityAssociation failed, error: -</span></span>

<span data-ttu-id="34ab0-140">2146893044</span><span class="sxs-lookup"><span data-stu-id="34ab0-140">2146893044</span></span>

<span data-ttu-id="34ab0-141">Diagnóstico</span><span class="sxs-lookup"><span data-stu-id="34ab0-141">Diagnosis :</span></span>

<span data-ttu-id="34ab0-142">A saída anterior indica que o usuário de teste teve o acesso negado ao Lync Server.</span><span class="sxs-lookup"><span data-stu-id="34ab0-142">The previous output indicates that the test user was denied access to Lync Server itself.</span></span> <span data-ttu-id="34ab0-143">Isso normalmente significa que as credenciais do usuário passadas para Test-CsDialInConferencing não eram válidas.</span><span class="sxs-lookup"><span data-stu-id="34ab0-143">This typically means that the user credentials passed to Test-CsDialInConferencing were not valid.</span></span> <span data-ttu-id="34ab0-144">Por sua vez, você deve recriar o objeto de credenciais do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="34ab0-144">In turn, you should re-create the Windows PowerShell credentials object.</span></span> <span data-ttu-id="34ab0-145">Embora seja possível recuperar a senha da conta de usuário, você pode verificar o endereço SIP usando um comando semelhante a este:</span><span class="sxs-lookup"><span data-stu-id="34ab0-145">Although you can retrieve the password for the user account, you can verify the SIP address by using a command similar to this:</span></span>

    Get-CsUser -Identity "sip:kenmyer@litwareinc.com" | Select-Object SipAddress

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="34ab0-146">Motivos pelos quais o teste pode ter falhado</span><span class="sxs-lookup"><span data-stu-id="34ab0-146">Reasons why the test might have failed</span></span>

<span data-ttu-id="34ab0-147">Aqui estão alguns motivos comuns pelos quais Test-CsDialInConferencing pode falhar:</span><span class="sxs-lookup"><span data-stu-id="34ab0-147">Here are some common reasons why Test-CsDialInConferencing might fail:</span></span>

  - <span data-ttu-id="34ab0-148">Você especificou uma conta de usuário que não é válida.</span><span class="sxs-lookup"><span data-stu-id="34ab0-148">You specified a user account that is not valid.</span></span> <span data-ttu-id="34ab0-149">Você pode verificar se uma conta de usuário existe executando um comando semelhante a este:</span><span class="sxs-lookup"><span data-stu-id="34ab0-149">You can verify that a user account exists by running a command similar to this:</span></span>
    
        Get-CsUser "sip:kenmyer@litwareinc.com"

  - <span data-ttu-id="34ab0-150">A conta de usuário é válida, mas a conta não está habilitada no momento para o Lync Server.</span><span class="sxs-lookup"><span data-stu-id="34ab0-150">The user account is valid, but the account is currently not enabled for Lync Server.</span></span> <span data-ttu-id="34ab0-151">Para verificar se uma conta de usuário está habilitada para o Lync Server, execute um comando semelhante ao seguinte:</span><span class="sxs-lookup"><span data-stu-id="34ab0-151">To verify that a user account is enabled for Lync Server, run a command similar to the following:</span></span>
    
        Get-CsUser "sip:kenmyer@litwareinc.com" | Select-Object Enabled
    
    <span data-ttu-id="34ab0-152">Se a propriedade Enabled estiver definida como false, isso significa que o usuário não está atualmente habilitado para o Lync Server.</span><span class="sxs-lookup"><span data-stu-id="34ab0-152">If the Enabled property is set to False, that means that the user is currently not enabled for Lync Server.</span></span>

  - <span data-ttu-id="34ab0-153">Você pode ter um número incorreto de acesso de conferência discada.</span><span class="sxs-lookup"><span data-stu-id="34ab0-153">You might have an incorrect dial-in conferencing access number.</span></span> <span data-ttu-id="34ab0-154">Você pode retornar a lista atualmente configurada de números de acesso de conferência discada usando este comando:</span><span class="sxs-lookup"><span data-stu-id="34ab0-154">You can return your currently-configured list of dial-in conferencing access numbers by using this command:</span></span>
    
        Get-CsDialConferencingAccessNumber

</div>

</div>

<span> </span>

</div>

</div>

</div>

