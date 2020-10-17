---
title: 'Lync Server 2013: testar sessão de conferência discada'
description: 'Lync Server 2013: testar sessão de conferência discada.'
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
ms.openlocfilehash: 4d0c51b16df674dbf8bf7f0a2c6c4c93c2606d95
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48560627"
---
# <a name="testing-dial-in-conferencing-session-in-lync-server-2013"></a><span data-ttu-id="d17cf-103">Testando a sessão de conferência discada no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d17cf-103">Testing dial-in conferencing session in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d17cf-104">_**Última modificação do tópico:** 2014-06-05_</span><span class="sxs-lookup"><span data-stu-id="d17cf-104">_**Topic Last Modified:** 2014-06-05_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d17cf-105">Agenda de verificação</span><span class="sxs-lookup"><span data-stu-id="d17cf-105">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="d17cf-106">Diariamente</span><span class="sxs-lookup"><span data-stu-id="d17cf-106">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d17cf-107">Ferramenta de teste</span><span class="sxs-lookup"><span data-stu-id="d17cf-107">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="d17cf-108">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="d17cf-108">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d17cf-109">Permissões obrigatórias</span><span class="sxs-lookup"><span data-stu-id="d17cf-109">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="d17cf-110">Ao executar localmente usando o Shell de gerenciamento do Lync Server, os usuários devem ser membros do grupo de segurança RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="d17cf-110">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="d17cf-111">Quando executado usando uma instância remota do Windows PowerShell, os usuários devem receber uma função RBAC que tenha permissão para executar o cmdlet Test-CsDialInConferencing.</span><span class="sxs-lookup"><span data-stu-id="d17cf-111">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsDialInConferencing cmdlet.</span></span> <span data-ttu-id="d17cf-112">Para ver uma lista de todas as funções RBAC que podem usar este cmdlet, execute o seguinte comando no prompt do Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="d17cf-112">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsDialInConferencing&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="d17cf-113">Descrição</span><span class="sxs-lookup"><span data-stu-id="d17cf-113">Description</span></span>

<span data-ttu-id="d17cf-114">O cmdlet Test-CsDialInConferencing verifica se um usuário pode participar de uma conferência discada.</span><span class="sxs-lookup"><span data-stu-id="d17cf-114">The Test-CsDialInConferencing cmdlet verifies whether a user can participate in a dial-in conference.</span></span> <span data-ttu-id="d17cf-115">Test-CsDialInConferencing funciona tentando registrar um usuário de teste no sistema.</span><span class="sxs-lookup"><span data-stu-id="d17cf-115">Test-CsDialInConferencing works by trying to log a test user onto the system.</span></span> <span data-ttu-id="d17cf-116">Se o logon for bem-sucedido, o cmdlet usará as credenciais do usuário e as permissões para tentar todos os números de acesso de conferência discada disponíveis.</span><span class="sxs-lookup"><span data-stu-id="d17cf-116">If the logon succeeds, the cmdlet will then use the user’s credentials and permissions to try all of the available dial-in conferencing access numbers.</span></span> <span data-ttu-id="d17cf-117">O sucesso ou a falha de cada tentativa de discagem será observado e, em seguida, o usuário de teste será desconectado do Lync Server. Test-CsDialInConferencing verifica apenas se as conexões apropriadas podem ser feitas.</span><span class="sxs-lookup"><span data-stu-id="d17cf-117">The success or failure of each dial-in try will be noted, then the test user will be logged off from Lync Server.Test-CsDialInConferencing only verifies that the appropriate connections can be made.</span></span> <span data-ttu-id="d17cf-118">No entanto, o cmdlet não faz chamadas telefônicas nem cria conferências discadas que outros usuários podem participar.</span><span class="sxs-lookup"><span data-stu-id="d17cf-118">The cmdlet does not actually make any phone calls or create any dial-in conferences that other users can join.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="d17cf-119">Executar o teste</span><span class="sxs-lookup"><span data-stu-id="d17cf-119">Running the test</span></span>

<span data-ttu-id="d17cf-120">O cmdlet Test-CsDialInConferencing pode ser executado usando uma conta de teste pré-configurada (Confira Configurando contas de teste para executar testes do Lync Server) ou a conta de qualquer usuário habilitado para o Lync Server.</span><span class="sxs-lookup"><span data-stu-id="d17cf-120">The Test-CsDialInConferencing cmdlet can be run using either a preconfigured test account (see Setting Up Test Accounts for Running Lync Server Tests) or the account of any user who is enabled for Lync Server.</span></span> <span data-ttu-id="d17cf-121">Para executar esta verificação usando uma conta de teste, basta especificar o FQDN do pool do Lync Server que está sendo testado.</span><span class="sxs-lookup"><span data-stu-id="d17cf-121">To run this check using a test account, you just have to specify the FQDN of the Lync Server pool being tested.</span></span> <span data-ttu-id="d17cf-122">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="d17cf-122">For example:</span></span>

    Test-CsDialInConferencing -TargetFqdn "atl-cs-001.litwareinc.com" 

<span data-ttu-id="d17cf-123">Para executar essa verificação usando uma conta de usuário real, você deve criar um objeto de credenciais do Windows PowerShell que contenha o nome da conta e a senha.</span><span class="sxs-lookup"><span data-stu-id="d17cf-123">To run this check using an actual user account, you must create a Windows PowerShell credentials object that contains the account name and password.</span></span> <span data-ttu-id="d17cf-124">Em seguida, você deve incluir o objeto Credentials e o endereço SIP da conta na chamada Test-CsDialInConferencing:</span><span class="sxs-lookup"><span data-stu-id="d17cf-124">You must then include that credentials object and the account SIP address the calling Test-CsDialInConferencing:</span></span>

    $credential = Get-Credential "litwareinc\kenmyer"
    Test-CsDialInConferencing -TargetFqdn atl-cs-001.litwareinc.com" -UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential

<span data-ttu-id="d17cf-125">Para obter mais informações, consulte a documentação de ajuda para o cmdlet [Test-CsDialInConferencing](https://docs.microsoft.com/powershell/module/skype/Test-CsDialInConferencing) .</span><span class="sxs-lookup"><span data-stu-id="d17cf-125">For more information, see the Help documentation for the [Test-CsDialInConferencing](https://docs.microsoft.com/powershell/module/skype/Test-CsDialInConferencing) cmdlet.</span></span>

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="d17cf-126">Determinando o sucesso ou a falha</span><span class="sxs-lookup"><span data-stu-id="d17cf-126">Determining success or failure</span></span>

<span data-ttu-id="d17cf-127">Se o usuário especificado puder fazer logon no Lync Server e fizer uma conexão usando um dos números de acesso de conferência discada disponíveis, você receberá uma saída semelhante a esta, com a propriedade Result marcada como **Success:**</span><span class="sxs-lookup"><span data-stu-id="d17cf-127">If the specified user can log on to Lync Server and then make a connection using one of the available dial-in conferencing access numbers, then you'll receive output similar to this, with the Result property marked as **Success:**</span></span>

<span data-ttu-id="d17cf-128">TargetFqdn: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="d17cf-128">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="d17cf-129">Resultado: êxito</span><span class="sxs-lookup"><span data-stu-id="d17cf-129">Result : Success</span></span>

<span data-ttu-id="d17cf-130">Latência: 00:00:06.8630376</span><span class="sxs-lookup"><span data-stu-id="d17cf-130">Latency : 00:00:06.8630376</span></span>

<span data-ttu-id="d17cf-131">Erros</span><span class="sxs-lookup"><span data-stu-id="d17cf-131">Error :</span></span>

<span data-ttu-id="d17cf-132">Diagnóstico</span><span class="sxs-lookup"><span data-stu-id="d17cf-132">Diagnosis :</span></span>

<span data-ttu-id="d17cf-133">Se o usuário especificado não puder fazer essa conexão, o resultado será mostrado como falha, e informações adicionais serão registradas nas propriedades de erro e diagnóstico:</span><span class="sxs-lookup"><span data-stu-id="d17cf-133">If the specified user can't make this connection, then the Result will be shown as Failure, and additional information will be recorded in the Error and Diagnosis properties:</span></span>

<span data-ttu-id="d17cf-134">TargetFqdn: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="d17cf-134">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="d17cf-135">Resultado: falha</span><span class="sxs-lookup"><span data-stu-id="d17cf-135">Result : Failure</span></span>

<span data-ttu-id="d17cf-136">Latência: 00:00:00</span><span class="sxs-lookup"><span data-stu-id="d17cf-136">Latency : 00:00:00</span></span>

<span data-ttu-id="d17cf-137">Erro: o logon foi negado.</span><span class="sxs-lookup"><span data-stu-id="d17cf-137">Error : The log on was denied.</span></span> <span data-ttu-id="d17cf-138">Verifique se as credenciais adequadas estão</span><span class="sxs-lookup"><span data-stu-id="d17cf-138">Check that the proper credentials are</span></span>

<span data-ttu-id="d17cf-139">sendo usado e a conta está ativa.</span><span class="sxs-lookup"><span data-stu-id="d17cf-139">being used and the account is active.</span></span>

<span data-ttu-id="d17cf-140">Exceção interna: NegotiateSecurityAssociation falhou, erro:-</span><span class="sxs-lookup"><span data-stu-id="d17cf-140">Inner Exception:NegotiateSecurityAssociation failed, error: -</span></span>

<span data-ttu-id="d17cf-141">2146893044</span><span class="sxs-lookup"><span data-stu-id="d17cf-141">2146893044</span></span>

<span data-ttu-id="d17cf-142">Diagnóstico</span><span class="sxs-lookup"><span data-stu-id="d17cf-142">Diagnosis :</span></span>

<span data-ttu-id="d17cf-143">A saída anterior indica que o usuário de teste teve o acesso negado ao Lync Server.</span><span class="sxs-lookup"><span data-stu-id="d17cf-143">The previous output indicates that the test user was denied access to Lync Server itself.</span></span> <span data-ttu-id="d17cf-144">Normalmente, isso significa que as credenciais do usuário passadas para Test-CsDialInConferencing não eram válidas.</span><span class="sxs-lookup"><span data-stu-id="d17cf-144">This typically means that the user credentials passed to Test-CsDialInConferencing were not valid.</span></span> <span data-ttu-id="d17cf-145">Por sua vez, você deve recriar o objeto de credenciais do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="d17cf-145">In turn, you should re-create the Windows PowerShell credentials object.</span></span> <span data-ttu-id="d17cf-146">Embora seja possível recuperar a senha da conta de usuário, você pode verificar o endereço SIP usando um comando semelhante a este:</span><span class="sxs-lookup"><span data-stu-id="d17cf-146">Although you can retrieve the password for the user account, you can verify the SIP address by using a command similar to this:</span></span>

    Get-CsUser -Identity "sip:kenmyer@litwareinc.com" | Select-Object SipAddress

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="d17cf-147">Motivos pelos quais o teste pode ter falhado</span><span class="sxs-lookup"><span data-stu-id="d17cf-147">Reasons why the test might have failed</span></span>

<span data-ttu-id="d17cf-148">Aqui estão alguns motivos comuns para que Test-CsDialInConferencing possa falhar:</span><span class="sxs-lookup"><span data-stu-id="d17cf-148">Here are some common reasons why Test-CsDialInConferencing might fail:</span></span>

  - <span data-ttu-id="d17cf-149">Você especificou uma conta de usuário que não é válida.</span><span class="sxs-lookup"><span data-stu-id="d17cf-149">You specified a user account that is not valid.</span></span> <span data-ttu-id="d17cf-150">Você pode verificar se uma conta de usuário existe executando um comando semelhante a este:</span><span class="sxs-lookup"><span data-stu-id="d17cf-150">You can verify that a user account exists by running a command similar to this:</span></span>
    
        Get-CsUser "sip:kenmyer@litwareinc.com"

  - <span data-ttu-id="d17cf-151">A conta de usuário é válida, mas a conta não está habilitada no momento para o Lync Server.</span><span class="sxs-lookup"><span data-stu-id="d17cf-151">The user account is valid, but the account is currently not enabled for Lync Server.</span></span> <span data-ttu-id="d17cf-152">Para verificar se uma conta de usuário está habilitada para o Lync Server, execute um comando semelhante ao seguinte:</span><span class="sxs-lookup"><span data-stu-id="d17cf-152">To verify that a user account is enabled for Lync Server, run a command similar to the following:</span></span>
    
        Get-CsUser "sip:kenmyer@litwareinc.com" | Select-Object Enabled
    
    <span data-ttu-id="d17cf-153">Se a propriedade Enabled estiver definida como false, isso significa que o usuário não está atualmente habilitado para o Lync Server.</span><span class="sxs-lookup"><span data-stu-id="d17cf-153">If the Enabled property is set to False, that means that the user is currently not enabled for Lync Server.</span></span>

  - <span data-ttu-id="d17cf-154">Você pode ter um número incorreto de acesso de conferência discada.</span><span class="sxs-lookup"><span data-stu-id="d17cf-154">You might have an incorrect dial-in conferencing access number.</span></span> <span data-ttu-id="d17cf-155">Você pode retornar a lista atualmente configurada de números de acesso de conferência discada usando este comando:</span><span class="sxs-lookup"><span data-stu-id="d17cf-155">You can return your currently-configured list of dial-in conferencing access numbers by using this command:</span></span>
    
        Get-CsDialConferencingAccessNumber

</div>

</div>

<span> </span>

</div>

</div>

</div>

