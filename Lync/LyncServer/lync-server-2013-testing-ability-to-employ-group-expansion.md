---
title: 'Lync Server 2013: testar a capacidade de empregar expansão de grupo'
description: 'Lync Server 2013: testar a capacidade de empregar expansão de grupo.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing ability to employ group expansion
ms:assetid: 9b0fc954-6f9c-411a-ab32-94ebabc42de2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn743836(v=OCS.15)
ms:contentKeyID: 63969634
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6267bc2099fc420c5c57e1ef80f4bf4491334938
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48560787"
---
# <a name="testing-ability-to-employ-group-expansion-in-lync-server-2013"></a><span data-ttu-id="cee0c-103">Testando a capacidade de empregar expansão de grupo no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="cee0c-103">Testing ability to employ group expansion in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="cee0c-104">_**Última modificação do tópico:** 2014-06-05_</span><span class="sxs-lookup"><span data-stu-id="cee0c-104">_**Topic Last Modified:** 2014-06-05_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="cee0c-105">Agenda de verificação</span><span class="sxs-lookup"><span data-stu-id="cee0c-105">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="cee0c-106">Diariamente</span><span class="sxs-lookup"><span data-stu-id="cee0c-106">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cee0c-107">Ferramenta de teste</span><span class="sxs-lookup"><span data-stu-id="cee0c-107">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="cee0c-108">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="cee0c-108">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cee0c-109">Permissões obrigatórias</span><span class="sxs-lookup"><span data-stu-id="cee0c-109">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="cee0c-110">Ao executar localmente usando o Shell de gerenciamento do Lync Server, os usuários devem ser membros do grupo de segurança RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="cee0c-110">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="cee0c-111">Quando executado usando uma instância remota do Windows PowerShell, os usuários devem receber uma função RBAC que tenha permissão para executar o cmdlet Test-CsGroupExpansion.</span><span class="sxs-lookup"><span data-stu-id="cee0c-111">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsGroupExpansion cmdlet.</span></span> <span data-ttu-id="cee0c-112">Para ver uma lista de todas as funções RBAC que podem usar este cmdlet, execute o seguinte comando no prompt do Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="cee0c-112">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsGroupExpansion&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="cee0c-113">Descrição</span><span class="sxs-lookup"><span data-stu-id="cee0c-113">Description</span></span>

<span data-ttu-id="cee0c-114">O cmdlet Test-CsGroupExpansion permite determinar se a expansão de grupo está funcionando dentro da sua organização.</span><span class="sxs-lookup"><span data-stu-id="cee0c-114">The Test-CsGroupExpansion cmdlet lets you determine whether group expansion is working within your organization.</span></span> <span data-ttu-id="cee0c-115">Quando a expansão de grupo é habilitada, os usuários configuram grupos de distribuição como um contato.</span><span class="sxs-lookup"><span data-stu-id="cee0c-115">When group expansion is enabled, users configure distribution groups as a contact.</span></span> <span data-ttu-id="cee0c-116">Isso significa que esses usuários podem enviar a mesma mensagem instantânea a todos os membros do grupo endereçando a mensagem para o grupo em vez de para membros individuais desse grupo.</span><span class="sxs-lookup"><span data-stu-id="cee0c-116">That means that those users can then send the same instant message to all the group members by addressing the message to the group instead of to individual members of that group.</span></span> <span data-ttu-id="cee0c-117">A expansão de grupo permite exibir de forma rápida e fácil todos os membros do grupo e seu status atual.</span><span class="sxs-lookup"><span data-stu-id="cee0c-117">Group expansion enables you to quickly and easily view all the group members and their current status.</span></span>

<span data-ttu-id="cee0c-118">Com o cmdlet Test-CsGroupExpansion, você especifica um grupo de distribuição do Active Directory usando o endereço de email do grupo.</span><span class="sxs-lookup"><span data-stu-id="cee0c-118">With the Test-CsGroupExpansion cmdlet, you specify an Active Directory distribution group by using the group’s email address.</span></span> <span data-ttu-id="cee0c-119">Test-CsGroupExpansion, em seguida, usa a expansão de grupo para recuperar a associação de grupo e comparar a lista recuperada com a associação do endereço de email do grupo que você forneceu.</span><span class="sxs-lookup"><span data-stu-id="cee0c-119">Test-CsGroupExpansion then uses group expansion to retrieve the group membership and compare the retrieved list to the membership of the group email address that you supplied.</span></span> <span data-ttu-id="cee0c-120">Se as duas listas corresponderem, a expansão de grupo estará funcionando corretamente.</span><span class="sxs-lookup"><span data-stu-id="cee0c-120">If the two lists match, then group expansion is working correctly.</span></span> <span data-ttu-id="cee0c-121">Observe que você pode testar a expansão de grupo de duas maneiras: testando o próprio serviço ou testando o serviço Web associado.</span><span class="sxs-lookup"><span data-stu-id="cee0c-121">Note that you can test group expansion in two ways: by testing the service itself or by testing the associated web service.</span></span>

<span data-ttu-id="cee0c-122">Para obter mais informações, consulte a documentação de ajuda para o cmdlet [Test-CsGroupExpansion](https://docs.microsoft.com/powershell/module/skype/Test-CsGroupExpansion) .</span><span class="sxs-lookup"><span data-stu-id="cee0c-122">For more information, see the Help documentation for the [Test-CsGroupExpansion](https://docs.microsoft.com/powershell/module/skype/Test-CsGroupExpansion) cmdlet.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="cee0c-123">Executar o teste</span><span class="sxs-lookup"><span data-stu-id="cee0c-123">Running the test</span></span>

<span data-ttu-id="cee0c-124">O cmdlet Test-CsGroupExpansion pode ser executado usando uma conta de teste pré-configurada (Confira Configurando contas de teste para executar testes do Lync Server) ou a conta de qualquer usuário que tenha sido habilitado para o Lync Server.</span><span class="sxs-lookup"><span data-stu-id="cee0c-124">The Test-CsGroupExpansion cmdlet can be run using either a preconfigured test account (see Setting Up Test Accounts for Running Lync Server Tests) or the account of any user who was enabled for Lync Server.</span></span> <span data-ttu-id="cee0c-125">Para executar essa verificação usando uma conta de teste, basta especificar o FQDN do pool do Lync Server que está sendo testado e o endereço de email de um grupo de distribuição válido.</span><span class="sxs-lookup"><span data-stu-id="cee0c-125">To run this check using a test account, you just have to specify the FQDN of the Lync Server pool being tested and the email address for a valid distribution group.</span></span> <span data-ttu-id="cee0c-126">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="cee0c-126">For example:</span></span>

    Test-CsGroupExpansion -TargetFqdn "atl-cs-001.litwareinc.com" -GroupEmailAddress "Sales@litwareinc.com"

<span data-ttu-id="cee0c-127">Para executar essa verificação usando uma conta de usuário real, você deve primeiro criar um objeto de credenciais do Lync Server que contenha o nome da conta e a senha.</span><span class="sxs-lookup"><span data-stu-id="cee0c-127">To run this check using an actual user account, you must first create a Lync Server credentials object that contains the account name and password.</span></span> <span data-ttu-id="cee0c-128">Em seguida, você deve incluir o objeto Credentials e o endereço SIP atribuído à conta quando o sistema chama Test-CsGroupExpansion:</span><span class="sxs-lookup"><span data-stu-id="cee0c-128">You must then include that credentials object and the SIP address assigned to the account when the system calls Test-CsGroupExpansion:</span></span>

    $credential = Get-Credential "litwareinc\kenmyer"
    Test-CsGroupExpansion -TargetFqdn "atl-cs-001.litwareinc.com" -GroupEmailAddress "Sales@litwareinc.com" -UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential

<span data-ttu-id="cee0c-129">Para obter mais informações, consulte a documentação de ajuda para o cmdlet [Test-CsGroupExpansion](https://docs.microsoft.com/powershell/module/skype/Test-CsGroupExpansion) .</span><span class="sxs-lookup"><span data-stu-id="cee0c-129">For more information, see the Help documentation for the [Test-CsGroupExpansion](https://docs.microsoft.com/powershell/module/skype/Test-CsGroupExpansion) cmdlet.</span></span>

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="cee0c-130">Determinando o sucesso ou a falha</span><span class="sxs-lookup"><span data-stu-id="cee0c-130">Determining success or failure</span></span>

<span data-ttu-id="cee0c-131">Se o usuário especificado pode usar expansão de grupo, você receberá uma saída semelhante a esta com a propriedade Result marcada como **Success:**</span><span class="sxs-lookup"><span data-stu-id="cee0c-131">If the specified user can use group expansion, you'll receive output similar to this with the Result property marked as **Success:**</span></span>

<span data-ttu-id="cee0c-132">TargetUri https://atl-cs-001.litwareinc.com:443/groupexpansion/service.svc</span><span class="sxs-lookup"><span data-stu-id="cee0c-132">TargetUri : https://atl-cs-001.litwareinc.com:443/groupexpansion/service.svc</span></span>

<span data-ttu-id="cee0c-133">TargetFqdn: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="cee0c-133">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="cee0c-134">Resultado: êxito</span><span class="sxs-lookup"><span data-stu-id="cee0c-134">Result : Success</span></span>

<span data-ttu-id="cee0c-135">Latência: 00:00:01.1234976</span><span class="sxs-lookup"><span data-stu-id="cee0c-135">Latency : 00:00:01.1234976</span></span>

<span data-ttu-id="cee0c-136">Erros</span><span class="sxs-lookup"><span data-stu-id="cee0c-136">Error :</span></span>

<span data-ttu-id="cee0c-137">Diagnóstico</span><span class="sxs-lookup"><span data-stu-id="cee0c-137">Diagnosis :</span></span>

<span data-ttu-id="cee0c-138">Se o usuário especificado não puder usar expansão de grupo, o resultado será mostrado como falha e informações adicionais serão registradas nas propriedades de erro e diagnóstico:</span><span class="sxs-lookup"><span data-stu-id="cee0c-138">If the specified user can't use group expansion, then the Result will be shown as Failure and additional information will be recorded in the Error and Diagnosis properties:</span></span>

<span data-ttu-id="cee0c-139">TargetUri https://atl-cs-001.litwareinc.com:443/groupexpansion/service.svc</span><span class="sxs-lookup"><span data-stu-id="cee0c-139">TargetUri : https://atl-cs-001.litwareinc.com:443/groupexpansion/service.svc</span></span>

<span data-ttu-id="cee0c-140">TargetFqdn: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="cee0c-140">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="cee0c-141">Resultado: falha</span><span class="sxs-lookup"><span data-stu-id="cee0c-141">Result : Failure</span></span>

<span data-ttu-id="cee0c-142">Latência: 00:00:00</span><span class="sxs-lookup"><span data-stu-id="cee0c-142">Latency : 00:00:00</span></span>

<span data-ttu-id="cee0c-143">Erros</span><span class="sxs-lookup"><span data-stu-id="cee0c-143">Error :</span></span>

<span data-ttu-id="cee0c-144">Diagnóstico</span><span class="sxs-lookup"><span data-stu-id="cee0c-144">Diagnosis :</span></span>

<span data-ttu-id="cee0c-145">Test-CsGroupExpansion: não foi possível registrar o ponto de extremidade.</span><span class="sxs-lookup"><span data-stu-id="cee0c-145">Test-CsGroupExpansion : The endpoint was unable to register.</span></span> <span data-ttu-id="cee0c-146">Consulte ErrorCode por motivo específico.</span><span class="sxs-lookup"><span data-stu-id="cee0c-146">See the ErrorCode for specific reason.</span></span>

<span data-ttu-id="cee0c-147">A saída anterior diz que o teste falhou porque o usuário especificado não pôde se registrar no Lync Server.</span><span class="sxs-lookup"><span data-stu-id="cee0c-147">The previous output states that the test failed because the specified user was unable to register with Lync Server.</span></span> <span data-ttu-id="cee0c-148">Isso normalmente ocorrerá se a conta de teste não existir ou se não tiver sido habilitada para o Lync Server.</span><span class="sxs-lookup"><span data-stu-id="cee0c-148">This will typically occur if the test account does not exist or has not enabled for Lync Server.</span></span> <span data-ttu-id="cee0c-149">Você pode verificar se a conta existe e determinar se a conta foi habilitada para o nm-OCS-14-3ª executando um comando semelhante ao seguinte:</span><span class="sxs-lookup"><span data-stu-id="cee0c-149">You can verify that the account exists, and determine whether or not the account has been enabled for nm-ocs-14-3rd by running a command similar to the following:</span></span>

    Get-CsUser -Identity "sip:kenmyer@litwareinc.com" | Select-Object SipAddress, Enabled

<span data-ttu-id="cee0c-150">Se Test-CsGroupExpansion falhar, talvez você queira executar novamente o teste, desta vez, incluindo o parâmetro Verbose:</span><span class="sxs-lookup"><span data-stu-id="cee0c-150">If Test-CsGroupExpansion fails, then you might want to rerun the test, this time including the Verbose parameter:</span></span>

    Test-CsGroupExpansion -TargetFqdn "atl-cs-001.litwareinc.com" -GroupEmailAddress "Sales@litwareinc.com" -Verbose

<span data-ttu-id="cee0c-151">Quando o parâmetro Verbose é incluído Test-CsGroupExpansion retornará uma conta passo a passo de cada ação que tentou quando verificou a capacidade do usuário especificado fazer logon no Lync Server.</span><span class="sxs-lookup"><span data-stu-id="cee0c-151">When the Verbose parameter is included Test-CsGroupExpansion will return a step-by-step account of each action it tried when it checked the ability of the specified user to log on to Lync Server.</span></span> <span data-ttu-id="cee0c-152">Por exemplo, essa saída indica que o grupo de distribuição especificado não pôde ser encontrado:</span><span class="sxs-lookup"><span data-stu-id="cee0c-152">For example, this output indicates that the specified distribution group couldn't be found:</span></span>

<span data-ttu-id="cee0c-153">Tentando obter tíquete da Web.</span><span class="sxs-lookup"><span data-stu-id="cee0c-153">Trying to get web ticket.</span></span>

<span data-ttu-id="cee0c-154">URL do serviço Web: https://atl-cs-001.litwareinc.com:443/WebTicket/WebTicketService.svc</span><span class="sxs-lookup"><span data-stu-id="cee0c-154">Web Service url : https://atl-cs-001.litwareinc.com:443/WebTicket/WebTicketService.svc</span></span>

<span data-ttu-id="cee0c-155">Usando autenticação NTLM/Kerb.</span><span class="sxs-lookup"><span data-stu-id="cee0c-155">Using NTLM/Kerb auth.</span></span>

<span data-ttu-id="cee0c-156">GetWebTicketActivity concluído.</span><span class="sxs-lookup"><span data-stu-id="cee0c-156">GetWebTicketActivity completed.</span></span>

<span data-ttu-id="cee0c-157">Atividade ' VerifyDistributionList ' iniciada.</span><span class="sxs-lookup"><span data-stu-id="cee0c-157">'VerifyDistributionList' activity started.</span></span>

<span data-ttu-id="cee0c-158">O status da resposta do serviço Web do DLX é: não encontrado.</span><span class="sxs-lookup"><span data-stu-id="cee0c-158">DLX Web Service Response Status is: NotFound.</span></span>

<span data-ttu-id="cee0c-159">Atividade ' VerifyDistributionList ' concluída em ' 0,2597923 ' segundos.</span><span class="sxs-lookup"><span data-stu-id="cee0c-159">'VerifyDistributionList' activity completed in '0.2597923' secs.</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="cee0c-160">Motivos pelos quais o teste pode ter falhado</span><span class="sxs-lookup"><span data-stu-id="cee0c-160">Reasons why the test might have failed</span></span>

<span data-ttu-id="cee0c-161">Aqui estão alguns motivos comuns para que Test-CsGroupExpansion possa falhar:</span><span class="sxs-lookup"><span data-stu-id="cee0c-161">Here are some common reasons why Test-CsGroupExpansion might fail:</span></span>

  - <span data-ttu-id="cee0c-162">Você especificou uma conta de usuário inválida.</span><span class="sxs-lookup"><span data-stu-id="cee0c-162">You specified an invalid user account.</span></span> <span data-ttu-id="cee0c-163">Você pode verificar se uma conta de usuário existe executando um comando semelhante a este:</span><span class="sxs-lookup"><span data-stu-id="cee0c-163">You can verify that a user account exists by running a command similar to this:</span></span>
    
        Get-CsUser "sip:kenmyer@litwareinc.com"

  - <span data-ttu-id="cee0c-164">A conta de usuário é válida, mas a conta não está habilitada no momento para o Lync Server.</span><span class="sxs-lookup"><span data-stu-id="cee0c-164">The user account is valid, but the account is currently not enabled for Lync Server.</span></span> <span data-ttu-id="cee0c-165">Para verificar se uma conta de usuário foi habilitada para o Lync Server, execute um comando semelhante ao seguinte:</span><span class="sxs-lookup"><span data-stu-id="cee0c-165">To verify that a user account was enabled for Lync Server, run a command similar to the following:</span></span>
    
        Get-CsUser "sip:kenmyer@litwareinc.com" | Select-Object Enabled
    
    <span data-ttu-id="cee0c-166">Se a propriedade Enabled estiver definida como false, isso significa que o usuário não está atualmente habilitado para o Lync Server.</span><span class="sxs-lookup"><span data-stu-id="cee0c-166">If the Enabled property is set to False, that means that the user is currently not enabled for Lync Server.</span></span>

  - <span data-ttu-id="cee0c-167">A expansão de grupo pode ser desabilitada.</span><span class="sxs-lookup"><span data-stu-id="cee0c-167">Group expansion might be disabled.</span></span> <span data-ttu-id="cee0c-168">É possível desativar a expansão de grupo.</span><span class="sxs-lookup"><span data-stu-id="cee0c-168">It is possible to turn off group expansion.</span></span> <span data-ttu-id="cee0c-169">Se a expansão de grupo tiver sido desabilitada, o cmdlet Test-CsGroupExpansion falhará.</span><span class="sxs-lookup"><span data-stu-id="cee0c-169">If group expansion was disabled then the Test-CsGroupExpansion cmdlet will fail.</span></span> <span data-ttu-id="cee0c-170">Para determinar se a expansão de grupo está habilitada, use um comando semelhante ao seguinte:</span><span class="sxs-lookup"><span data-stu-id="cee0c-170">To determine whether group expansion is enabled, use a command similar to this:</span></span>
    
        Get-CsWebServiceConfiguration | Select-Object Identity, EnableGroupExpansion

</div>

</div>

<span> </span>

</div>

</div>

</div>

