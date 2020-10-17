---
title: 'Lync Server 2013: testar conferência UCWA'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing UCWA conferencing
ms:assetid: 62b3866a-0759-4b1f-99ec-5a68d6a74f00
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn727306(v=OCS.15)
ms:contentKeyID: 63969610
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5879eaa10b128bedbc1e28fe85cee40aed27dddd
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48503908"
---
# <a name="testing-ucwa-conferencing-in-lync-server-2013"></a><span data-ttu-id="01593-102">Testando a conferência do UCWA no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="01593-102">Testing UCWA conferencing in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="01593-103">_**Última modificação do tópico:** 2014-11-03_</span><span class="sxs-lookup"><span data-stu-id="01593-103">_**Topic Last Modified:** 2014-11-03_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="01593-104">Agenda de verificação</span><span class="sxs-lookup"><span data-stu-id="01593-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="01593-105">Diariamente</span><span class="sxs-lookup"><span data-stu-id="01593-105">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="01593-106">Ferramenta de teste</span><span class="sxs-lookup"><span data-stu-id="01593-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="01593-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="01593-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="01593-108">Permissões obrigatórias</span><span class="sxs-lookup"><span data-stu-id="01593-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="01593-109">Ao executar localmente usando o Shell de gerenciamento do Lync Server, os usuários devem ser membros do grupo de segurança RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="01593-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="01593-110">Quando executado usando uma instância remota do Windows PowerShell, os usuários devem receber uma função RBAC que tenha permissão para executar o cmdlet <strong>Test-CsUcwaConference</strong> .</span><span class="sxs-lookup"><span data-stu-id="01593-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the <strong>Test-CsUcwaConference</strong> cmdlet.</span></span> <span data-ttu-id="01593-111">Para ver uma lista de todas as funções RBAC que podem usar este cmdlet, execute o seguinte comando no prompt do Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="01593-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsUcwaConference&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="01593-112">Descrição</span><span class="sxs-lookup"><span data-stu-id="01593-112">Description</span></span>

<span data-ttu-id="01593-113">O cmdlet **Test-CsUcwaConference** verifica se um par de usuários de teste pode agendar, participar e, em seguida, conduzir uma conferência online usando a API Web de comunicações unificadas (UCWA).</span><span class="sxs-lookup"><span data-stu-id="01593-113">The **Test-CsUcwaConference** cmdlet verifies that a pair of test users can schedule, join, and then conduct an online conference using the Unified Communications Web API (UCWA).</span></span> <span data-ttu-id="01593-114">Para fazer isso, o cmdlet usa o serviço de tíquete da Web do Lync Server para autenticar os dois usuários de teste e registrá-los no Lync Server.</span><span class="sxs-lookup"><span data-stu-id="01593-114">To do this, the cmdlet uses the Lync Server web ticket service to authenticate the two test users and register them with Lync Server.</span></span> <span data-ttu-id="01593-115">O cmdlet então inicia uma conferência usando as credenciais do organizador e convida o participante para entrar na reunião.</span><span class="sxs-lookup"><span data-stu-id="01593-115">The cmdlet then starts a conference using the organizer credentials and invites the participant to join the meeting.</span></span> <span data-ttu-id="01593-116">Depois que a reunião é associada, o cmdlet **Test-CsUcwaConference** verifica se os usuários podem fazer coisas como mensagens instantâneas do Exchange e pools de condução e, em seguida, desconecta a conferência e cancela o registro dos dois usuários de teste.</span><span class="sxs-lookup"><span data-stu-id="01593-116">After the meeting is joined, the **Test-CsUcwaConference** cmdlet verifies that the users can do such things as exchange instant message and conduct pools, then disconnects the conference and unregisters the two test users.</span></span> <span data-ttu-id="01593-117">A conferência agendada também será excluída quando o teste for concluído.</span><span class="sxs-lookup"><span data-stu-id="01593-117">The scheduled conference will also be deleted when the test is finished.</span></span>

<span data-ttu-id="01593-118">O cmdlet **Test-CsUcwaConference** também pode ser usado para determinar se os usuários anônimos podem participar de conferências online.</span><span class="sxs-lookup"><span data-stu-id="01593-118">The **Test-CsUcwaConference** cmdlet can also be used to determine whether anonymous users can join online conferences.</span></span>

<span data-ttu-id="01593-119">Observe que o cmdlet **Test-CsUcwaConference** não deve ser executado em um pool do Microsoft Lync Server 2010, a menos que o UCWA tenha sido instalado nesse pool.</span><span class="sxs-lookup"><span data-stu-id="01593-119">Note that the **Test-CsUcwaConference** cmdlet should not be run against a Microsoft Lync Server 2010 pool unless UCWA was installed on that pool.</span></span> <span data-ttu-id="01593-120">Se o UCWA não tiver sido instalado, a chamada para o cmdlet **Test-CsUcwaConference** falhará.</span><span class="sxs-lookup"><span data-stu-id="01593-120">If UCWA has not been installed then the call to the **Test-CsUcwaConference** cmdlet will fail.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="01593-121">Executar o teste</span><span class="sxs-lookup"><span data-stu-id="01593-121">Running the test</span></span>

<span data-ttu-id="01593-p104">O comando mostrado no Exemplo 1 verifica se um par de usuários de teste pode participar de uma conferência de UCWA no pool atl-cs-001.litwareinc.com. Observe que esse comando falha se você não predefinir um par de usuários de teste de configuração de monitoramento de integridade para o atl-cs-001.litwareinc.com.</span><span class="sxs-lookup"><span data-stu-id="01593-p104">The command shown in Example 1 verifies that a pair of test users can participate in an UCWA conference on the pool atl-cs-001.litwareinc.com. Note that this command will fail if you have not predefined a pair of health monitoring configuration test users for atl-cs-001.litwareinc.com.</span></span>

    Test-CsUcwaConference -TargetFqdn "atl-cs-001.litwareinc.com"

<span data-ttu-id="01593-124">Os comandos mostrados no exemplo 2 testam a capacidade de um par de usuários (litwareinc \\ pilar e litwareinc \\ kenmyer) para participar de uma conferência do UCWA.</span><span class="sxs-lookup"><span data-stu-id="01593-124">The commands shown in Example 2 test the ability of a pair of users (litwareinc\\pilar and litwareinc\\kenmyer) to participate in an UCWA conference.</span></span> <span data-ttu-id="01593-125">Para fazer isso, o primeiro comando no exemplo usa o cmdlet Get-Credential para criar um objeto de credencial da interface de linha de comando do Windows PowerShell que contenha o nome e a senha do usuário pilar Ackerman.</span><span class="sxs-lookup"><span data-stu-id="01593-125">To do this, the first command in the example uses the Get-Credential cmdlet to create a Windows PowerShell command-line interface credential object that contains the name and password of the user Pilar Ackerman.</span></span> <span data-ttu-id="01593-126">(Como o nome de logon, litwareinc \\ pilar, foi incluído como um parâmetro, a caixa de diálogo de solicitação de credencial do Windows PowerShell só exige que o administrador insira a senha da conta pilar Ackerman.) O objeto de credenciais resultante é armazenado em uma variável chamada $cred 1.</span><span class="sxs-lookup"><span data-stu-id="01593-126">(Because the logon name, litwareinc\\pilar, was included as a parameter, the Windows PowerShell Credential Request dialog box only requires the administrator to enter the password for the Pilar Ackerman account.) The resulting credentials object is then stored in a variable named $cred1.</span></span> <span data-ttu-id="01593-127">O segundo comando fará o mesmo, retornando, desta vez, um objeto de credencial para a conta de Ken Myer.</span><span class="sxs-lookup"><span data-stu-id="01593-127">The second command does the same thing, this time returning a credential object for the Ken Myer account.</span></span>

<span data-ttu-id="01593-128">Com os dois objetos de credencial em mãos, o terceiro comando no exemplo determina se os dois usuários podem participar de uma conferência do UCWA.</span><span class="sxs-lookup"><span data-stu-id="01593-128">With the two credential objects in hand, the third command in the example determines whether the two users can participate in an UCWA conference.</span></span> <span data-ttu-id="01593-129">Para executar essa tarefa, o cmdlet **Test-CsUcwaConference** é chamado, junto com os seguintes parâmetros: TargetFqdn (o FQDN do pool de registrador); OrganizerSipAddress (o endereço SIP do organizador da reunião); OrganizerCredential (o objeto Windows PowerShell que contém as credenciais desse mesmo usuário); ParticipantSipAddress (o endereço SIP para o outro usuário de teste); e ParticipantCredential (o objeto de interface de linha de comando do Windows PowerShell que contém as credenciais do outro usuário).</span><span class="sxs-lookup"><span data-stu-id="01593-129">To run this task, the **Test-CsUcwaConference** cmdlet is called, together with the following parameters: TargetFqdn (the FQDN of the Registrar pool); OrganizerSipAddress (the SIP address for the meeting organizer); OrganizerCredential (the Windows PowerShell object that contains the credentials for this same user); ParticipantSipAddress (the SIP address for the other test user); and ParticipantCredential (the Windows PowerShell command-line interface object that contains the credentials for the other user).</span></span>

    $cred1 = Get-Credential "litwareinc\pilar"
    $cred2 = Get-Credential "litwareinc\kenmyer"
    Test-CsUcwaConference -TargetFqdn atl-cs-001.litwareinc.com -OrganizerSipAddress "sip:pilar@litwareinc.com" -OrganizerCredential $cred1 -ParticipantSipAddress "sip:kenmyer@litwareinc.com" -ParticipantCredential $cred2

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="01593-130">Determinando o sucesso ou a falha</span><span class="sxs-lookup"><span data-stu-id="01593-130">Determining success or failure</span></span>

<span data-ttu-id="01593-131">Se a conferência estiver configurada corretamente, você receberá uma saída semelhante a esta, com a propriedade Result marcada como **Success:**</span><span class="sxs-lookup"><span data-stu-id="01593-131">If conferencing is correctly configured, you'll receive output similar to this, with the Result property marked as **Success:**</span></span>

<span data-ttu-id="01593-132">FQDN de destino: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="01593-132">Target Fqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="01593-133">URI de destino: https://LyncTest-SE. LyncTest. SelfHost. Corp.</span><span class="sxs-lookup"><span data-stu-id="01593-133">Target Uri : https:// LyncTest-SE.LyncTest.SelfHost.Corp.</span></span>

<span data-ttu-id="01593-134">Microsoft.com:443/CertProv/CertProvisiongService.svc</span><span class="sxs-lookup"><span data-stu-id="01593-134">Microsoft.com:443/CertProv/CertProvisiongService.svc</span></span>

<span data-ttu-id="01593-135">Resultado: êxito</span><span class="sxs-lookup"><span data-stu-id="01593-135">Result : Success</span></span>

<span data-ttu-id="01593-136">Latência: 00:00:14.9862716</span><span class="sxs-lookup"><span data-stu-id="01593-136">Latency : 00:00:14.9862716</span></span>

<span data-ttu-id="01593-137">Mensagem de erro:</span><span class="sxs-lookup"><span data-stu-id="01593-137">Error Message :</span></span>

<span data-ttu-id="01593-138">Diagnóstico</span><span class="sxs-lookup"><span data-stu-id="01593-138">Diagnosis :</span></span>

<span data-ttu-id="01593-139">Se os usuários especificados não puderem usar conferências, o resultado será mostrado como **falha**, e informações adicionais serão registradas nas propriedades de erro e diagnóstico:</span><span class="sxs-lookup"><span data-stu-id="01593-139">If the specified users can't use conferencing, the Result will be shown as **Failure**, and additional information will be recorded in the Error and Diagnosis properties:</span></span>

<span data-ttu-id="01593-140">Aviso: falha ao ler o número da porta do registrador para o fornecido totalmente qualificado</span><span class="sxs-lookup"><span data-stu-id="01593-140">WARNING: Failed to read Registrar port number for the given fully qualified</span></span>

<span data-ttu-id="01593-141">FQDN (nome de domínio).</span><span class="sxs-lookup"><span data-stu-id="01593-141">domain name (FQDN).</span></span> <span data-ttu-id="01593-142">Usando o número da porta do registrador padrão.</span><span class="sxs-lookup"><span data-stu-id="01593-142">Using default Registrar port number.</span></span> <span data-ttu-id="01593-143">Exceções</span><span class="sxs-lookup"><span data-stu-id="01593-143">Exception:</span></span>

<span data-ttu-id="01593-144">System. InvalidOperationException: nenhum cluster correspondente encontrado na topologia.</span><span class="sxs-lookup"><span data-stu-id="01593-144">System.InvalidOperationException: No matching cluster found in topology.</span></span>

<span data-ttu-id="01593-145">por</span><span class="sxs-lookup"><span data-stu-id="01593-145">at</span></span>

<span data-ttu-id="01593-146">Microsoft. RTC. Management. SyntheticTransactions. SipSyntheticTransaction. TryRetri</span><span class="sxs-lookup"><span data-stu-id="01593-146">Microsoft.Rtc.Management.SyntheticTransactions.SipSyntheticTransaction.TryRetri</span></span>

<span data-ttu-id="01593-147">eveRegistrarPortFromTopology (Int32& registrarPortNumber)</span><span class="sxs-lookup"><span data-stu-id="01593-147">eveRegistrarPortFromTopology(Int32& registrarPortNumber)</span></span>

<span data-ttu-id="01593-148">Test-CsUcwaConference: não há um usuário de teste atribuído para</span><span class="sxs-lookup"><span data-stu-id="01593-148">Test-CsUcwaConference : There is no test user assigned for</span></span>

<span data-ttu-id="01593-149">\[LyncTest.SelfHost.Corp.Microsoft.com \] .</span><span class="sxs-lookup"><span data-stu-id="01593-149">\[LyncTest.SelfHost.Corp.Microsoft.com\].</span></span> <span data-ttu-id="01593-150">Verifique a configuração do usuário de teste.</span><span class="sxs-lookup"><span data-stu-id="01593-150">Verify test user configuration.</span></span>

<span data-ttu-id="01593-151">Na linha: 1 caractere: 1</span><span class="sxs-lookup"><span data-stu-id="01593-151">At line:1 char:1</span></span>

<span data-ttu-id="01593-152">\+ Test-CsUcwaConference-TargetFqdn "LyncTest.SelfHost.Corp.Microsoft.com"</span><span class="sxs-lookup"><span data-stu-id="01593-152">\+ Test-CsUcwaConference -TargetFqdn "LyncTest.SelfHost.Corp.Microsoft.com"</span></span>

\+ ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

<span data-ttu-id="01593-153">\+ CategoryInfo: ResourceUnavailable: (:) \[ Test-CsUcwaConference\]</span><span class="sxs-lookup"><span data-stu-id="01593-153">\+ CategoryInfo : ResourceUnavailable: (:) \[Test-CsUcwaConference\]</span></span>

<span data-ttu-id="01593-154">, InvalidOperationException</span><span class="sxs-lookup"><span data-stu-id="01593-154">, InvalidOperationException</span></span>

<span data-ttu-id="01593-155">\+ FullyQualifiedErrorId: NotFoundTestUsers, Microsoft. RTC. Management. sintetizador</span><span class="sxs-lookup"><span data-stu-id="01593-155">\+ FullyQualifiedErrorId : NotFoundTestUsers,Microsoft.Rtc.Management.Synth</span></span>

<span data-ttu-id="01593-156">eticTransactions.TestUcwaConferenceCmdlet</span><span class="sxs-lookup"><span data-stu-id="01593-156">eticTransactions.TestUcwaConferenceCmdlet</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="01593-157">Motivos pelos quais o teste pode ter falhado</span><span class="sxs-lookup"><span data-stu-id="01593-157">Reasons why the test might have failed</span></span>

<span data-ttu-id="01593-158">Aqui estão alguns motivos comuns pelos quais **Test-CsUcwaConference** pode falhar:</span><span class="sxs-lookup"><span data-stu-id="01593-158">Here are some common reasons why **Test-CsUcwaConference** might fail:</span></span>

  - <span data-ttu-id="01593-159">Um valor de parâmetro incorreto foi fornecido.</span><span class="sxs-lookup"><span data-stu-id="01593-159">An incorrect parameter value was supplied.</span></span> <span data-ttu-id="01593-160">Se usado, os parâmetros opcionais devem ser configurados corretamente ou o teste falhará.</span><span class="sxs-lookup"><span data-stu-id="01593-160">If used, the optional parameters must be configured correctly or the test will fail.</span></span> <span data-ttu-id="01593-161">Execute novamente o comando sem os parâmetros opcionais e veja se isso é bem-sucedido.</span><span class="sxs-lookup"><span data-stu-id="01593-161">Rerun the command without the optional parameters and see whether that succeeds.</span></span>

  - <span data-ttu-id="01593-162">A capacidade de realizar uma conferência depende da política de conferência que foi atribuída ao usuário que organizou a conferência (no caso do cmdlet **Test-CsUcwaConference** , que é o "remetente").</span><span class="sxs-lookup"><span data-stu-id="01593-162">The ability to conduct a conference depends on the conferencing policy that has been assigned to the user who organized the conference (in the case of the **Test-CsUcwaConference** cmdlet, that is the "sender").</span></span> <span data-ttu-id="01593-163">Se o organizador não tiver permissão para incluir atividades colaborativas em sua reunião (por exemplo, se a política de conferência tiver a propriedade EnableDataCollaboration definida como false), o cmdlet **Test-CsUcwaConference** falhará.</span><span class="sxs-lookup"><span data-stu-id="01593-163">If the organizer is not allowed to include collaborative activities in his or her meeting (for example, if his or her conferencing policy has the EnableDataCollaboration property set to False) then the **Test-CsUcwaConference** cmdlet will fail.</span></span>

  - <span data-ttu-id="01593-164">Esse comando falhará se o servidor de borda estiver configurado incorretamente ou ainda não tiver sido implantado.</span><span class="sxs-lookup"><span data-stu-id="01593-164">This command will fail if the Edge Server is misconfigured or not yet deployed.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="01593-165">Confira também</span><span class="sxs-lookup"><span data-stu-id="01593-165">See Also</span></span>


[<span data-ttu-id="01593-166">Test-CsASConference</span><span class="sxs-lookup"><span data-stu-id="01593-166">Test-CsASConference</span></span>](https://docs.microsoft.com/powershell/module/skype/Test-CsASConference)  
[<span data-ttu-id="01593-167">Test-CsDataConference</span><span class="sxs-lookup"><span data-stu-id="01593-167">Test-CsDataConference</span></span>](https://docs.microsoft.com/powershell/module/skype/Test-CsDataConference)  
[<span data-ttu-id="01593-168">Test-CsAVConference</span><span class="sxs-lookup"><span data-stu-id="01593-168">Test-CsAVConference</span></span>](https://docs.microsoft.com/powershell/module/skype/Test-CsAVConference)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

