---
title: 'Lync Server 2013: testar a capacidade de empregar expansão de grupo'
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
ms.openlocfilehash: ca5964a31682172bafb0c7d5604aab7f70ad8fbd
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42016152"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="testing-ability-to-employ-group-expansion-in-lync-server-2013"></a><span data-ttu-id="12020-102">Testando a capacidade de empregar expansão de grupo no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="12020-102">Testing ability to employ group expansion in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="12020-103">_**Última modificação do tópico:** 2014-06-05_</span><span class="sxs-lookup"><span data-stu-id="12020-103">_**Topic Last Modified:** 2014-06-05_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="12020-104">Agenda de verificação</span><span class="sxs-lookup"><span data-stu-id="12020-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="12020-105">Diariamente</span><span class="sxs-lookup"><span data-stu-id="12020-105">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="12020-106">Ferramenta de teste</span><span class="sxs-lookup"><span data-stu-id="12020-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="12020-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="12020-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="12020-108">Permissões obrigatórias</span><span class="sxs-lookup"><span data-stu-id="12020-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="12020-109">Ao executar localmente usando o Shell de gerenciamento do Lync Server, os usuários devem ser membros do grupo de segurança RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="12020-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="12020-110">Quando executado usando uma instância remota do Windows PowerShell, os usuários devem receber uma função RBAC que tenha permissão para executar o cmdlet Test-CsGroupExpansion.</span><span class="sxs-lookup"><span data-stu-id="12020-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsGroupExpansion cmdlet.</span></span> <span data-ttu-id="12020-111">Para ver uma lista de todas as funções RBAC que podem usar este cmdlet, execute o seguinte comando no prompt do Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="12020-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsGroupExpansion&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="12020-112">Descrição</span><span class="sxs-lookup"><span data-stu-id="12020-112">Description</span></span>

<span data-ttu-id="12020-113">O cmdlet Test-CsGroupExpansion permite determinar se a expansão de grupo está funcionando em sua organização.</span><span class="sxs-lookup"><span data-stu-id="12020-113">The Test-CsGroupExpansion cmdlet lets you determine whether group expansion is working within your organization.</span></span> <span data-ttu-id="12020-114">Quando a expansão de grupo é habilitada, os usuários configuram grupos de distribuição como um contato.</span><span class="sxs-lookup"><span data-stu-id="12020-114">When group expansion is enabled, users configure distribution groups as a contact.</span></span> <span data-ttu-id="12020-115">Isso significa que esses usuários podem enviar a mesma mensagem instantânea a todos os membros do grupo endereçando a mensagem para o grupo em vez de para membros individuais desse grupo.</span><span class="sxs-lookup"><span data-stu-id="12020-115">That means that those users can then send the same instant message to all the group members by addressing the message to the group instead of to individual members of that group.</span></span> <span data-ttu-id="12020-116">A expansão de grupo permite exibir de forma rápida e fácil todos os membros do grupo e seu status atual.</span><span class="sxs-lookup"><span data-stu-id="12020-116">Group expansion enables you to quickly and easily view all the group members and their current status.</span></span>

<span data-ttu-id="12020-117">Com o cmdlet Test-CsGroupExpansion, você especifica um grupo de distribuição do Active Directory usando o endereço de email do grupo.</span><span class="sxs-lookup"><span data-stu-id="12020-117">With the Test-CsGroupExpansion cmdlet, you specify an Active Directory distribution group by using the group’s email address.</span></span> <span data-ttu-id="12020-118">Test-CsGroupExpansion usa a expansão de grupo para recuperar a associação de grupo e comparar a lista recuperada com a associação do endereço de email do grupo que você forneceu.</span><span class="sxs-lookup"><span data-stu-id="12020-118">Test-CsGroupExpansion then uses group expansion to retrieve the group membership and compare the retrieved list to the membership of the group email address that you supplied.</span></span> <span data-ttu-id="12020-119">Se as duas listas corresponderem, a expansão de grupo estará funcionando corretamente.</span><span class="sxs-lookup"><span data-stu-id="12020-119">If the two lists match, then group expansion is working correctly.</span></span> <span data-ttu-id="12020-120">Observe que você pode testar a expansão de grupo de duas maneiras: testando o próprio serviço ou testando o serviço Web associado.</span><span class="sxs-lookup"><span data-stu-id="12020-120">Note that you can test group expansion in two ways: by testing the service itself or by testing the associated web service.</span></span>

<span data-ttu-id="12020-121">Para obter mais informações, consulte a documentação de ajuda para o cmdlet [Test-CsGroupExpansion](https://docs.microsoft.com/powershell/module/skype/Test-CsGroupExpansion) .</span><span class="sxs-lookup"><span data-stu-id="12020-121">For more information, see the Help documentation for the [Test-CsGroupExpansion](https://docs.microsoft.com/powershell/module/skype/Test-CsGroupExpansion) cmdlet.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="12020-122">Executar o teste</span><span class="sxs-lookup"><span data-stu-id="12020-122">Running the test</span></span>

<span data-ttu-id="12020-123">O cmdlet Test-CsGroupExpansion pode ser executado usando uma conta de teste pré-configurada (Confira Configurando contas de teste para executar testes do Lync Server) ou a conta de qualquer usuário que tenha sido habilitado para o Lync Server.</span><span class="sxs-lookup"><span data-stu-id="12020-123">The Test-CsGroupExpansion cmdlet can be run using either a preconfigured test account (see Setting Up Test Accounts for Running Lync Server Tests) or the account of any user who was enabled for Lync Server.</span></span> <span data-ttu-id="12020-124">Para executar essa verificação usando uma conta de teste, basta especificar o FQDN do pool do Lync Server que está sendo testado e o endereço de email de um grupo de distribuição válido.</span><span class="sxs-lookup"><span data-stu-id="12020-124">To run this check using a test account, you just have to specify the FQDN of the Lync Server pool being tested and the email address for a valid distribution group.</span></span> <span data-ttu-id="12020-125">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="12020-125">For example:</span></span>

    Test-CsGroupExpansion -TargetFqdn "atl-cs-001.litwareinc.com" -GroupEmailAddress "Sales@litwareinc.com"

<span data-ttu-id="12020-126">Para executar essa verificação usando uma conta de usuário real, você deve primeiro criar um objeto de credenciais do Lync Server que contenha o nome da conta e a senha.</span><span class="sxs-lookup"><span data-stu-id="12020-126">To run this check using an actual user account, you must first create a Lync Server credentials object that contains the account name and password.</span></span> <span data-ttu-id="12020-127">Em seguida, você deve incluir o objeto Credentials e o endereço SIP atribuído à conta quando o sistema chama Test-CsGroupExpansion:</span><span class="sxs-lookup"><span data-stu-id="12020-127">You must then include that credentials object and the SIP address assigned to the account when the system calls Test-CsGroupExpansion:</span></span>

    $credential = Get-Credential "litwareinc\kenmyer"
    Test-CsGroupExpansion -TargetFqdn "atl-cs-001.litwareinc.com" -GroupEmailAddress "Sales@litwareinc.com" -UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential

<span data-ttu-id="12020-128">Para obter mais informações, consulte a documentação de ajuda para o cmdlet [Test-CsGroupExpansion](https://docs.microsoft.com/powershell/module/skype/Test-CsGroupExpansion) .</span><span class="sxs-lookup"><span data-stu-id="12020-128">For more information, see the Help documentation for the [Test-CsGroupExpansion](https://docs.microsoft.com/powershell/module/skype/Test-CsGroupExpansion) cmdlet.</span></span>

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="12020-129">Determinando o sucesso ou a falha</span><span class="sxs-lookup"><span data-stu-id="12020-129">Determining success or failure</span></span>

<span data-ttu-id="12020-130">Se o usuário especificado pode usar expansão de grupo, você receberá uma saída semelhante a esta com a propriedade Result marcada como **Success:**</span><span class="sxs-lookup"><span data-stu-id="12020-130">If the specified user can use group expansion, you'll receive output similar to this with the Result property marked as **Success:**</span></span>

<span data-ttu-id="12020-131">TargetUrihttps://atl-cs-001.litwareinc.com:443/groupexpansion/service.svc</span><span class="sxs-lookup"><span data-stu-id="12020-131">TargetUri : https://atl-cs-001.litwareinc.com:443/groupexpansion/service.svc</span></span>

<span data-ttu-id="12020-132">TargetFqdn: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="12020-132">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="12020-133">Resultado: êxito</span><span class="sxs-lookup"><span data-stu-id="12020-133">Result : Success</span></span>

<span data-ttu-id="12020-134">Latência: 00:00:01.1234976</span><span class="sxs-lookup"><span data-stu-id="12020-134">Latency : 00:00:01.1234976</span></span>

<span data-ttu-id="12020-135">Erros</span><span class="sxs-lookup"><span data-stu-id="12020-135">Error :</span></span>

<span data-ttu-id="12020-136">Diagnóstico</span><span class="sxs-lookup"><span data-stu-id="12020-136">Diagnosis :</span></span>

<span data-ttu-id="12020-137">Se o usuário especificado não puder usar expansão de grupo, o resultado será mostrado como falha e informações adicionais serão registradas nas propriedades de erro e diagnóstico:</span><span class="sxs-lookup"><span data-stu-id="12020-137">If the specified user can't use group expansion, then the Result will be shown as Failure and additional information will be recorded in the Error and Diagnosis properties:</span></span>

<span data-ttu-id="12020-138">TargetUrihttps://atl-cs-001.litwareinc.com:443/groupexpansion/service.svc</span><span class="sxs-lookup"><span data-stu-id="12020-138">TargetUri : https://atl-cs-001.litwareinc.com:443/groupexpansion/service.svc</span></span>

<span data-ttu-id="12020-139">TargetFqdn: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="12020-139">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="12020-140">Resultado: falha</span><span class="sxs-lookup"><span data-stu-id="12020-140">Result : Failure</span></span>

<span data-ttu-id="12020-141">Latência: 00:00:00</span><span class="sxs-lookup"><span data-stu-id="12020-141">Latency : 00:00:00</span></span>

<span data-ttu-id="12020-142">Erros</span><span class="sxs-lookup"><span data-stu-id="12020-142">Error :</span></span>

<span data-ttu-id="12020-143">Diagnóstico</span><span class="sxs-lookup"><span data-stu-id="12020-143">Diagnosis :</span></span>

<span data-ttu-id="12020-144">Test-CsGroupExpansion: não foi possível registrar o ponto de extremidade.</span><span class="sxs-lookup"><span data-stu-id="12020-144">Test-CsGroupExpansion : The endpoint was unable to register.</span></span> <span data-ttu-id="12020-145">Consulte ErrorCode por motivo específico.</span><span class="sxs-lookup"><span data-stu-id="12020-145">See the ErrorCode for specific reason.</span></span>

<span data-ttu-id="12020-146">A saída anterior diz que o teste falhou porque o usuário especificado não pôde se registrar no Lync Server.</span><span class="sxs-lookup"><span data-stu-id="12020-146">The previous output states that the test failed because the specified user was unable to register with Lync Server.</span></span> <span data-ttu-id="12020-147">Isso normalmente ocorrerá se a conta de teste não existir ou se não tiver sido habilitada para o Lync Server.</span><span class="sxs-lookup"><span data-stu-id="12020-147">This will typically occur if the test account does not exist or has not enabled for Lync Server.</span></span> <span data-ttu-id="12020-148">Você pode verificar se a conta existe e determinar se a conta foi habilitada para o nm-OCS-14-3ª executando um comando semelhante ao seguinte:</span><span class="sxs-lookup"><span data-stu-id="12020-148">You can verify that the account exists, and determine whether or not the account has been enabled for nm-ocs-14-3rd by running a command similar to the following:</span></span>

    Get-CsUser -Identity "sip:kenmyer@litwareinc.com" | Select-Object SipAddress, Enabled

<span data-ttu-id="12020-149">Se Test-CsGroupExpansion falhar, talvez você queira executar novamente o teste, desta vez, incluindo o parâmetro Verbose:</span><span class="sxs-lookup"><span data-stu-id="12020-149">If Test-CsGroupExpansion fails, then you might want to rerun the test, this time including the Verbose parameter:</span></span>

    Test-CsGroupExpansion -TargetFqdn "atl-cs-001.litwareinc.com" -GroupEmailAddress "Sales@litwareinc.com" -Verbose

<span data-ttu-id="12020-150">Quando o parâmetro Verbose é incluído, o Test-CsGroupExpansion retornará uma conta passo a passo de cada ação que tentou quando verificou a capacidade do usuário especificado fazer logon no Lync Server.</span><span class="sxs-lookup"><span data-stu-id="12020-150">When the Verbose parameter is included Test-CsGroupExpansion will return a step-by-step account of each action it tried when it checked the ability of the specified user to log on to Lync Server.</span></span> <span data-ttu-id="12020-151">Por exemplo, essa saída indica que o grupo de distribuição especificado não pôde ser encontrado:</span><span class="sxs-lookup"><span data-stu-id="12020-151">For example, this output indicates that the specified distribution group couldn't be found:</span></span>

<span data-ttu-id="12020-152">Tentando obter tíquete da Web.</span><span class="sxs-lookup"><span data-stu-id="12020-152">Trying to get web ticket.</span></span>

<span data-ttu-id="12020-153">URL do serviço Web:https://atl-cs-001.litwareinc.com:443/WebTicket/WebTicketService.svc</span><span class="sxs-lookup"><span data-stu-id="12020-153">Web Service url : https://atl-cs-001.litwareinc.com:443/WebTicket/WebTicketService.svc</span></span>

<span data-ttu-id="12020-154">Usando autenticação NTLM/Kerb.</span><span class="sxs-lookup"><span data-stu-id="12020-154">Using NTLM/Kerb auth.</span></span>

<span data-ttu-id="12020-155">GetWebTicketActivity concluído.</span><span class="sxs-lookup"><span data-stu-id="12020-155">GetWebTicketActivity completed.</span></span>

<span data-ttu-id="12020-156">Atividade ' VerifyDistributionList ' iniciada.</span><span class="sxs-lookup"><span data-stu-id="12020-156">'VerifyDistributionList' activity started.</span></span>

<span data-ttu-id="12020-157">O status da resposta do serviço Web do DLX é: não encontrado.</span><span class="sxs-lookup"><span data-stu-id="12020-157">DLX Web Service Response Status is: NotFound.</span></span>

<span data-ttu-id="12020-158">Atividade ' VerifyDistributionList ' concluída em ' 0,2597923 ' segundos.</span><span class="sxs-lookup"><span data-stu-id="12020-158">'VerifyDistributionList' activity completed in '0.2597923' secs.</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="12020-159">Motivos pelos quais o teste pode ter falhado</span><span class="sxs-lookup"><span data-stu-id="12020-159">Reasons why the test might have failed</span></span>

<span data-ttu-id="12020-160">Aqui estão alguns motivos comuns pelos quais Test-CsGroupExpansion pode falhar:</span><span class="sxs-lookup"><span data-stu-id="12020-160">Here are some common reasons why Test-CsGroupExpansion might fail:</span></span>

  - <span data-ttu-id="12020-161">Você especificou uma conta de usuário inválida.</span><span class="sxs-lookup"><span data-stu-id="12020-161">You specified an invalid user account.</span></span> <span data-ttu-id="12020-162">Você pode verificar se uma conta de usuário existe executando um comando semelhante a este:</span><span class="sxs-lookup"><span data-stu-id="12020-162">You can verify that a user account exists by running a command similar to this:</span></span>
    
        Get-CsUser "sip:kenmyer@litwareinc.com"

  - <span data-ttu-id="12020-163">A conta de usuário é válida, mas a conta não está habilitada no momento para o Lync Server.</span><span class="sxs-lookup"><span data-stu-id="12020-163">The user account is valid, but the account is currently not enabled for Lync Server.</span></span> <span data-ttu-id="12020-164">Para verificar se uma conta de usuário foi habilitada para o Lync Server, execute um comando semelhante ao seguinte:</span><span class="sxs-lookup"><span data-stu-id="12020-164">To verify that a user account was enabled for Lync Server, run a command similar to the following:</span></span>
    
        Get-CsUser "sip:kenmyer@litwareinc.com" | Select-Object Enabled
    
    <span data-ttu-id="12020-165">Se a propriedade Enabled estiver definida como false, isso significa que o usuário não está atualmente habilitado para o Lync Server.</span><span class="sxs-lookup"><span data-stu-id="12020-165">If the Enabled property is set to False, that means that the user is currently not enabled for Lync Server.</span></span>

  - <span data-ttu-id="12020-166">A expansão de grupo pode ser desabilitada.</span><span class="sxs-lookup"><span data-stu-id="12020-166">Group expansion might be disabled.</span></span> <span data-ttu-id="12020-167">É possível desativar a expansão de grupo.</span><span class="sxs-lookup"><span data-stu-id="12020-167">It is possible to turn off group expansion.</span></span> <span data-ttu-id="12020-168">Se a expansão de grupo tiver sido desabilitada, o cmdlet Test-CsGroupExpansion falhará.</span><span class="sxs-lookup"><span data-stu-id="12020-168">If group expansion was disabled then the Test-CsGroupExpansion cmdlet will fail.</span></span> <span data-ttu-id="12020-169">Para determinar se a expansão de grupo está habilitada, use um comando semelhante ao seguinte:</span><span class="sxs-lookup"><span data-stu-id="12020-169">To determine whether group expansion is enabled, use a command similar to this:</span></span>
    
        Get-CsWebServiceConfiguration | Select-Object Identity, EnableGroupExpansion

</div>

</div>

<span> </span>

</div>

</div>

</div>

