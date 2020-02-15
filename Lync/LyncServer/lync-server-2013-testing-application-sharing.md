---
title: 'Lync Server 2013: testar compartilhamento de aplicativos'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing application sharing
ms:assetid: 8d21db9b-10d1-4b43-b057-0deb1df1c205
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn727310(v=OCS.15)
ms:contentKeyID: 63969629
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2797a116bddb73543a27553faa55650b9ad16e8d
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42036641"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="testing-application-sharing-in-lync-server-2013"></a><span data-ttu-id="32d77-102">Testando o compartilhamento de aplicativos no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="32d77-102">Testing application sharing in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="32d77-103">_**Última modificação do tópico:** 2014-11-01_</span><span class="sxs-lookup"><span data-stu-id="32d77-103">_**Topic Last Modified:** 2014-11-01_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="32d77-104">Agenda de verificação</span><span class="sxs-lookup"><span data-stu-id="32d77-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="32d77-105">Diariamente</span><span class="sxs-lookup"><span data-stu-id="32d77-105">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="32d77-106">Ferramenta de teste</span><span class="sxs-lookup"><span data-stu-id="32d77-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="32d77-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="32d77-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="32d77-108">Permissões obrigatórias</span><span class="sxs-lookup"><span data-stu-id="32d77-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="32d77-109">Ao executar localmente usando o Shell de gerenciamento do Lync Server, os usuários devem ser membros do grupo de segurança RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="32d77-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="32d77-110">Quando executado usando uma instância remota do Windows PowerShell, os usuários devem receber uma função RBAC que tenha permissão para executar o cmdlet Test-CsASConference.</span><span class="sxs-lookup"><span data-stu-id="32d77-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsASConference cmdlet.</span></span> <span data-ttu-id="32d77-111">Para ver uma lista de todas as funções RBAC que podem usar este cmdlet, execute o seguinte comando no prompt do Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="32d77-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsASConference&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="32d77-112">Descrição</span><span class="sxs-lookup"><span data-stu-id="32d77-112">Description</span></span>

<span data-ttu-id="32d77-113">O cmdlet **Test-CsASConference** verifica se um par de usuários de teste pode participar de uma conferência online que inclui o compartilhamento de aplicativos.</span><span class="sxs-lookup"><span data-stu-id="32d77-113">The **Test-CsASConference** cmdlet verifies that a pair of test users can participate in an online conference that includes application sharing.</span></span> <span data-ttu-id="32d77-114">Para fazer isso, o cmdlet registra os dois usuários com o Lync Server 2013 e, em seguida, usa uma das contas de usuário para criar uma nova conferência que inclui o compartilhamento de aplicativos.</span><span class="sxs-lookup"><span data-stu-id="32d77-114">To do this, the cmdlet registers the two users with Lync Server 2013, and then it uses one of the user accounts to create a new conference that includes applications sharing.</span></span> <span data-ttu-id="32d77-115">O cmdlet verifica que o segundo usuário é capaz de ingressar na conferência.</span><span class="sxs-lookup"><span data-stu-id="32d77-115">The cmdlet then verifies that the second user is able to join that conference.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="32d77-116">Executar o teste</span><span class="sxs-lookup"><span data-stu-id="32d77-116">Running the test</span></span>

<span data-ttu-id="32d77-p103">O comando mostrado no Exemplo 1 verifica se uma conferência de Compartilhamento de Aplicativos pode ser conduzida no pool atl-cs-001.litwareinc.com. Este comando assume que você configurou um par de usuários de testes para o pool especificado. Se nenhum usuário de teste existir, o comando falhará.</span><span class="sxs-lookup"><span data-stu-id="32d77-p103">The command shown in Example 1 verifies that an Application Sharing conference can be conducted on the pool atl-cs-001.litwareinc.com. This command assumes that you have configured a pair of test users for the specified pool. If no such test users exist, the command will fail.</span></span>

    Test-CsASConference -TargetFqdn "atl-cs-001.litwareinc.com"

<span data-ttu-id="32d77-p104">O Exemplo 2 testa a capacidade do serviço Join Launcher participar de uma conferência de Compartilhamento de Aplicativos no pool atl-cs-001.litwareinc.com. Observe que este comando testa apenas o próprio serviço. Você não precisa de qualquer dispositivo móvel para executar o comando.</span><span class="sxs-lookup"><span data-stu-id="32d77-p104">Example 2 tests the ability of the Join Launcher service to participate in an Application Sharing conference on the pool atl-cs-001.litwareinc.com. Note that this command tests only the service itself; you do not need any mobile devices in order to run the command.</span></span>

    Test-CsASConference -TargetFqdn "atl-cs-001.litwareinc.com" -TestJoinLauncher 

<span data-ttu-id="32d77-122">Os comandos mostrados no exemplo 2 testam a capacidade de um par de usuários\\(litwareinc pilar\\e litwareinc kenmyer) para fazer logon no Lync Server 2013 e, em seguida, conduzir uma conferência de compartilhamento de aplicativo.</span><span class="sxs-lookup"><span data-stu-id="32d77-122">The commands shown in Example 2 test the ability of a pair of users (litwareinc\\pilar and litwareinc\\kenmyer) to log on to Lync Server 2013 and then conduct an Application Sharing conference.</span></span> <span data-ttu-id="32d77-123">Para fazer isso, o primeiro comando no exemplo usa o cmdlet Get-Credential para criar um objeto de credencial da interface de linha de comando do Windows PowerShell contendo o nome e a senha do usuário pilar Ackerman.</span><span class="sxs-lookup"><span data-stu-id="32d77-123">To do this, the first command in the example uses the Get-Credential cmdlet to create a Windows PowerShell command-line interface credential object containing the name and password of the user Pilar Ackerman.</span></span> <span data-ttu-id="32d77-124">(Como o nome de logon,\\litwareinc pilar, foi incluído como um parâmetro, a caixa de diálogo de solicitação de credencial do Windows PowerShell só exige que o administrador insira a senha da conta pilar Ackerman.) O objeto Credential resultante é armazenado em uma variável chamada $cred 1.</span><span class="sxs-lookup"><span data-stu-id="32d77-124">(Because the logon name, litwareinc\\pilar, has been included as a parameter, the Windows PowerShell Credential Request dialog box only requires the administrator to enter the password for the Pilar Ackerman account.) The resulting credential object is then stored in a variable named $cred1.</span></span> <span data-ttu-id="32d77-125">O segundo comando fará o mesmo, retornando, desta vez, um objeto de credencial para a conta de Ken Myer.</span><span class="sxs-lookup"><span data-stu-id="32d77-125">The second command does the same thing, this time returning a credential object for the Ken Myer account.</span></span>

<span data-ttu-id="32d77-126">Com os objetos de credencial em mãos, o terceiro comando determina se esses dois usuários podem ou não fazer logon no Lync Server 2013 e realizar uma conferência de compartilhamento de aplicativo.</span><span class="sxs-lookup"><span data-stu-id="32d77-126">With the credential objects in hand, the third command determines whether or not these two users can log on to Lync Server 2013 and conduct an Application Sharing conference.</span></span> <span data-ttu-id="32d77-127">Para realizar essa tarefa, o cmdlet **Test-CsASConference** é chamado, junto com os seguintes parâmetros: TargetFqdn (o FQDN do pool de registrador); SenderSipAddress (o endereço SIP para o primeiro usuário de teste); SenderCredential (o objeto Windows PowerShell contendo as credenciais desse mesmo usuário); ReceiverSipAddress (o endereço SIP para o outro usuário de teste); e ReceiverCredential (o objeto Windows PowerShell que contém as credenciais para o outro usuário de teste).</span><span class="sxs-lookup"><span data-stu-id="32d77-127">To carry out this task, the **Test-CsASConference** cmdlet is called, along with the following parameters: TargetFqdn (the FQDN of the Registrar pool); SenderSipAddress (the SIP address for the first test user); SenderCredential (the Windows PowerShell object containing the credentials for this same user); ReceiverSipAddress (the SIP address for the other test user); and ReceiverCredential (the Windows PowerShell object containing the credentials for the other test user).</span></span>

    $cred1 = Get-Credential "litwareinc\pilar" 
    $cred2 = Get-Credential "litwareinc\kenmyer" 
    Test-CsASConference -TargetFqdn atl-cs-001.litwareinc.com -SenderSipAddress "sip:pilar@litwareinc.com" -SenderCredential $cred1 -ReceiverSipAddress "sip:kenmyer@litwareinc.com" -ReceiverCredential $cred2

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="32d77-128">Determinando o sucesso ou a falha</span><span class="sxs-lookup"><span data-stu-id="32d77-128">Determining success or failure</span></span>

<span data-ttu-id="32d77-129">Se o compartilhamento de aplicativos estiver configurado corretamente, você receberá uma saída semelhante a esta, com a propriedade Result marcada como **Success:**</span><span class="sxs-lookup"><span data-stu-id="32d77-129">If application sharing is correctly configured, you'll receive output similar to this, with the Result property marked as **Success:**</span></span>

<span data-ttu-id="32d77-130">FQDN de destino: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="32d77-130">Target Fqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="32d77-131">Resultado: êxito</span><span class="sxs-lookup"><span data-stu-id="32d77-131">Result : Success</span></span>

<span data-ttu-id="32d77-132">Latência: 00:00:01</span><span class="sxs-lookup"><span data-stu-id="32d77-132">Latency : 00:00:01</span></span>

<span data-ttu-id="32d77-133">Mensagem de erro:</span><span class="sxs-lookup"><span data-stu-id="32d77-133">Error Message :</span></span>

<span data-ttu-id="32d77-134">Diagnóstico</span><span class="sxs-lookup"><span data-stu-id="32d77-134">Diagnosis :</span></span>

<span data-ttu-id="32d77-135">Se os usuários especificados não puderem compartilhar aplicativos, o resultado será mostrado como falha, e informações adicionais serão registradas nas propriedades de erro e diagnóstico:</span><span class="sxs-lookup"><span data-stu-id="32d77-135">If the specified users can't share applications, the Result will be shown as Failure, and additional information will be recorded in the Error and Diagnosis properties:</span></span>

<span data-ttu-id="32d77-136">FQDN de destino: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="32d77-136">Target Fqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="32d77-137">Resultado: falha</span><span class="sxs-lookup"><span data-stu-id="32d77-137">Result : Failure</span></span>

<span data-ttu-id="32d77-138">Latência: 00:00:00</span><span class="sxs-lookup"><span data-stu-id="32d77-138">Latency : 00:00:00</span></span>

<span data-ttu-id="32d77-139">Mensagem de erro: 10060, uma tentativa de conexão falhou porque a parte conectada</span><span class="sxs-lookup"><span data-stu-id="32d77-139">Error Message : 10060, A connection attempt failed because the connected party</span></span>

<span data-ttu-id="32d77-140">Não respondeu corretamente após um período de tempo ou</span><span class="sxs-lookup"><span data-stu-id="32d77-140">did not properly respond after a period of time, or</span></span>

<span data-ttu-id="32d77-141">a conexão estabelecida falhou porque o host conectado tem</span><span class="sxs-lookup"><span data-stu-id="32d77-141">established connection failed because connected host has</span></span>

<span data-ttu-id="32d77-142">Falha ao responder 10.188.116.96:5061</span><span class="sxs-lookup"><span data-stu-id="32d77-142">failed to respond 10.188.116.96:5061</span></span>

<span data-ttu-id="32d77-143">Exceção interna: falha na tentativa de conexão porque o</span><span class="sxs-lookup"><span data-stu-id="32d77-143">Inner Exception:A connection attempt failed because the</span></span>

<span data-ttu-id="32d77-144">a parte conectada não respondeu corretamente após um período de</span><span class="sxs-lookup"><span data-stu-id="32d77-144">connected party did not properly respond after a period of</span></span>

<span data-ttu-id="32d77-145">a hora ou a conexão estabelecida falhou porque o host conectado</span><span class="sxs-lookup"><span data-stu-id="32d77-145">time, or established connection failed because connected host</span></span>

<span data-ttu-id="32d77-146">Falha ao responder 10.188.116.96:5061</span><span class="sxs-lookup"><span data-stu-id="32d77-146">has failed to respond 10.188.116.96:5061</span></span>

<span data-ttu-id="32d77-147">Diagnóstico</span><span class="sxs-lookup"><span data-stu-id="32d77-147">Diagnosis :</span></span>

<span data-ttu-id="32d77-148">Por exemplo, a saída anterior inclui a anotação "a parte conectada não respondeu corretamente" que geralmente indica um problema com o servidor de borda.</span><span class="sxs-lookup"><span data-stu-id="32d77-148">For example, the previous output includes the note “the connected party did not properly respond” That typically indicates a problem with the Edge Server.</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="32d77-149">Motivos pelos quais o teste pode ter falhado</span><span class="sxs-lookup"><span data-stu-id="32d77-149">Reasons why the test might have failed</span></span>

<span data-ttu-id="32d77-150">Aqui estão alguns motivos comuns pelos quais **Test-CsASConference** pode falhar:</span><span class="sxs-lookup"><span data-stu-id="32d77-150">Here are some common reasons why **Test-CsASConference** might fail:</span></span>

  - <span data-ttu-id="32d77-151">Um valor de parâmetro incorreto foi fornecido.</span><span class="sxs-lookup"><span data-stu-id="32d77-151">An incorrect parameter value was supplied.</span></span> <span data-ttu-id="32d77-152">Se usado, os parâmetros opcionais devem ser configurados corretamente ou o teste falhará.</span><span class="sxs-lookup"><span data-stu-id="32d77-152">If used, the optional parameters must be configured correctly or the test will fail.</span></span> <span data-ttu-id="32d77-153">Execute novamente o comando sem os parâmetros opcionais e veja se isso é bem-sucedido.</span><span class="sxs-lookup"><span data-stu-id="32d77-153">Rerun the command without the optional parameters and see whether that succeeds.</span></span>

  - <span data-ttu-id="32d77-154">Esse comando falhará se os usuários de teste tiverem uma política de conferência atribuída que os impede de usar o compartilhamento de aplicativos.</span><span class="sxs-lookup"><span data-stu-id="32d77-154">This command will fail if the test users were assigned a conferencing policy that prevents them from using application sharing.</span></span>

  - <span data-ttu-id="32d77-155">Esse comando falhará se o servidor de borda estiver configurado incorretamente ou ainda não tiver sido implantado.</span><span class="sxs-lookup"><span data-stu-id="32d77-155">This command will fail if the Edge Server is misconfigured or not yet deployed.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="32d77-156">Confira também</span><span class="sxs-lookup"><span data-stu-id="32d77-156">See Also</span></span>


[<span data-ttu-id="32d77-157">Get-CsConferencingPolicy</span><span class="sxs-lookup"><span data-stu-id="32d77-157">Get-CsConferencingPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsConferencingPolicy)  
[<span data-ttu-id="32d77-158">Test-CsDataConference</span><span class="sxs-lookup"><span data-stu-id="32d77-158">Test-CsDataConference</span></span>](https://docs.microsoft.com/powershell/module/skype/Test-CsDataConference)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

