---
title: 'Lync Server 2013: testar compartilhamento de aplicativos'
description: 'Lync Server 2013: testar o compartilhamento de aplicativos.'
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
ms.openlocfilehash: f857908e374239b4054985b88951cd12720ed418
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48560717"
---
# <a name="testing-application-sharing-in-lync-server-2013"></a><span data-ttu-id="3e593-103">Testando o compartilhamento de aplicativos no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3e593-103">Testing application sharing in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3e593-104">_**Última modificação do tópico:** 2014-11-01_</span><span class="sxs-lookup"><span data-stu-id="3e593-104">_**Topic Last Modified:** 2014-11-01_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="3e593-105">Agenda de verificação</span><span class="sxs-lookup"><span data-stu-id="3e593-105">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="3e593-106">Diariamente</span><span class="sxs-lookup"><span data-stu-id="3e593-106">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3e593-107">Ferramenta de teste</span><span class="sxs-lookup"><span data-stu-id="3e593-107">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="3e593-108">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="3e593-108">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3e593-109">Permissões obrigatórias</span><span class="sxs-lookup"><span data-stu-id="3e593-109">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="3e593-110">Ao executar localmente usando o Shell de gerenciamento do Lync Server, os usuários devem ser membros do grupo de segurança RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="3e593-110">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="3e593-111">Quando executado usando uma instância remota do Windows PowerShell, os usuários devem receber uma função RBAC que tenha permissão para executar o cmdlet Test-CsASConference.</span><span class="sxs-lookup"><span data-stu-id="3e593-111">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsASConference cmdlet.</span></span> <span data-ttu-id="3e593-112">Para ver uma lista de todas as funções RBAC que podem usar este cmdlet, execute o seguinte comando no prompt do Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="3e593-112">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsASConference&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="3e593-113">Descrição</span><span class="sxs-lookup"><span data-stu-id="3e593-113">Description</span></span>

<span data-ttu-id="3e593-114">O cmdlet **Test-CsASConference** verifica se um par de usuários de teste pode participar de uma conferência online que inclui o compartilhamento de aplicativos.</span><span class="sxs-lookup"><span data-stu-id="3e593-114">The **Test-CsASConference** cmdlet verifies that a pair of test users can participate in an online conference that includes application sharing.</span></span> <span data-ttu-id="3e593-115">Para fazer isso, o cmdlet registra os dois usuários com o Lync Server 2013 e, em seguida, usa uma das contas de usuário para criar uma nova conferência que inclui o compartilhamento de aplicativos.</span><span class="sxs-lookup"><span data-stu-id="3e593-115">To do this, the cmdlet registers the two users with Lync Server 2013, and then it uses one of the user accounts to create a new conference that includes applications sharing.</span></span> <span data-ttu-id="3e593-116">O cmdlet verifica que o segundo usuário é capaz de ingressar na conferência.</span><span class="sxs-lookup"><span data-stu-id="3e593-116">The cmdlet then verifies that the second user is able to join that conference.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="3e593-117">Executar o teste</span><span class="sxs-lookup"><span data-stu-id="3e593-117">Running the test</span></span>

<span data-ttu-id="3e593-p103">O comando mostrado no Exemplo 1 verifica se uma conferência de Compartilhamento de Aplicativos pode ser conduzida no pool atl-cs-001.litwareinc.com. Este comando assume que você configurou um par de usuários de testes para o pool especificado. Se nenhum usuário de teste existir, o comando falhará.</span><span class="sxs-lookup"><span data-stu-id="3e593-p103">The command shown in Example 1 verifies that an Application Sharing conference can be conducted on the pool atl-cs-001.litwareinc.com. This command assumes that you have configured a pair of test users for the specified pool. If no such test users exist, the command will fail.</span></span>

    Test-CsASConference -TargetFqdn "atl-cs-001.litwareinc.com"

<span data-ttu-id="3e593-p104">O Exemplo 2 testa a capacidade do serviço Join Launcher participar de uma conferência de Compartilhamento de Aplicativos no pool atl-cs-001.litwareinc.com. Observe que este comando testa apenas o próprio serviço. Você não precisa de qualquer dispositivo móvel para executar o comando.</span><span class="sxs-lookup"><span data-stu-id="3e593-p104">Example 2 tests the ability of the Join Launcher service to participate in an Application Sharing conference on the pool atl-cs-001.litwareinc.com. Note that this command tests only the service itself; you do not need any mobile devices in order to run the command.</span></span>

    Test-CsASConference -TargetFqdn "atl-cs-001.litwareinc.com" -TestJoinLauncher 

<span data-ttu-id="3e593-123">Os comandos mostrados no exemplo 2 testam a capacidade de um par de usuários (litwareinc \\ pilar e litwareinc \\ kenmyer) para fazer logon no Lync Server 2013 e, em seguida, conduzir uma conferência de compartilhamento de aplicativo.</span><span class="sxs-lookup"><span data-stu-id="3e593-123">The commands shown in Example 2 test the ability of a pair of users (litwareinc\\pilar and litwareinc\\kenmyer) to log on to Lync Server 2013 and then conduct an Application Sharing conference.</span></span> <span data-ttu-id="3e593-124">Para fazer isso, o primeiro comando no exemplo usa o cmdlet Get-Credential para criar um objeto de credencial da interface de linha de comando do Windows PowerShell contendo o nome e a senha do usuário pilar Ackerman.</span><span class="sxs-lookup"><span data-stu-id="3e593-124">To do this, the first command in the example uses the Get-Credential cmdlet to create a Windows PowerShell command-line interface credential object containing the name and password of the user Pilar Ackerman.</span></span> <span data-ttu-id="3e593-125">(Como o nome de logon, litwareinc \\ pilar, foi incluído como um parâmetro, a caixa de diálogo de solicitação de credencial do Windows PowerShell só exige que o administrador insira a senha da conta pilar Ackerman.) O objeto Credential resultante é armazenado em uma variável chamada $cred 1.</span><span class="sxs-lookup"><span data-stu-id="3e593-125">(Because the logon name, litwareinc\\pilar, has been included as a parameter, the Windows PowerShell Credential Request dialog box only requires the administrator to enter the password for the Pilar Ackerman account.) The resulting credential object is then stored in a variable named $cred1.</span></span> <span data-ttu-id="3e593-126">O segundo comando fará o mesmo, retornando, desta vez, um objeto de credencial para a conta de Ken Myer.</span><span class="sxs-lookup"><span data-stu-id="3e593-126">The second command does the same thing, this time returning a credential object for the Ken Myer account.</span></span>

<span data-ttu-id="3e593-127">Com os objetos de credencial em mãos, o terceiro comando determina se esses dois usuários podem ou não fazer logon no Lync Server 2013 e realizar uma conferência de compartilhamento de aplicativo.</span><span class="sxs-lookup"><span data-stu-id="3e593-127">With the credential objects in hand, the third command determines whether or not these two users can log on to Lync Server 2013 and conduct an Application Sharing conference.</span></span> <span data-ttu-id="3e593-128">Para realizar essa tarefa, o cmdlet **Test-CsASConference** é chamado, junto com os seguintes parâmetros: TargetFqdn (o FQDN do pool de registrador); SenderSipAddress (o endereço SIP para o primeiro usuário de teste); SenderCredential (o objeto Windows PowerShell contendo as credenciais desse mesmo usuário); ReceiverSipAddress (o endereço SIP para o outro usuário de teste); e ReceiverCredential (o objeto Windows PowerShell que contém as credenciais para o outro usuário de teste).</span><span class="sxs-lookup"><span data-stu-id="3e593-128">To carry out this task, the **Test-CsASConference** cmdlet is called, along with the following parameters: TargetFqdn (the FQDN of the Registrar pool); SenderSipAddress (the SIP address for the first test user); SenderCredential (the Windows PowerShell object containing the credentials for this same user); ReceiverSipAddress (the SIP address for the other test user); and ReceiverCredential (the Windows PowerShell object containing the credentials for the other test user).</span></span>

    $cred1 = Get-Credential "litwareinc\pilar" 
    $cred2 = Get-Credential "litwareinc\kenmyer" 
    Test-CsASConference -TargetFqdn atl-cs-001.litwareinc.com -SenderSipAddress "sip:pilar@litwareinc.com" -SenderCredential $cred1 -ReceiverSipAddress "sip:kenmyer@litwareinc.com" -ReceiverCredential $cred2

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="3e593-129">Determinando o sucesso ou a falha</span><span class="sxs-lookup"><span data-stu-id="3e593-129">Determining success or failure</span></span>

<span data-ttu-id="3e593-130">Se o compartilhamento de aplicativos estiver configurado corretamente, você receberá uma saída semelhante a esta, com a propriedade Result marcada como **Success:**</span><span class="sxs-lookup"><span data-stu-id="3e593-130">If application sharing is correctly configured, you'll receive output similar to this, with the Result property marked as **Success:**</span></span>

<span data-ttu-id="3e593-131">FQDN de destino: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="3e593-131">Target Fqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="3e593-132">Resultado: êxito</span><span class="sxs-lookup"><span data-stu-id="3e593-132">Result : Success</span></span>

<span data-ttu-id="3e593-133">Latência: 00:00:01</span><span class="sxs-lookup"><span data-stu-id="3e593-133">Latency : 00:00:01</span></span>

<span data-ttu-id="3e593-134">Mensagem de erro:</span><span class="sxs-lookup"><span data-stu-id="3e593-134">Error Message :</span></span>

<span data-ttu-id="3e593-135">Diagnóstico</span><span class="sxs-lookup"><span data-stu-id="3e593-135">Diagnosis :</span></span>

<span data-ttu-id="3e593-136">Se os usuários especificados não puderem compartilhar aplicativos, o resultado será mostrado como falha, e informações adicionais serão registradas nas propriedades de erro e diagnóstico:</span><span class="sxs-lookup"><span data-stu-id="3e593-136">If the specified users can't share applications, the Result will be shown as Failure, and additional information will be recorded in the Error and Diagnosis properties:</span></span>

<span data-ttu-id="3e593-137">FQDN de destino: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="3e593-137">Target Fqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="3e593-138">Resultado: falha</span><span class="sxs-lookup"><span data-stu-id="3e593-138">Result : Failure</span></span>

<span data-ttu-id="3e593-139">Latência: 00:00:00</span><span class="sxs-lookup"><span data-stu-id="3e593-139">Latency : 00:00:00</span></span>

<span data-ttu-id="3e593-140">Mensagem de erro: 10060, uma tentativa de conexão falhou porque a parte conectada</span><span class="sxs-lookup"><span data-stu-id="3e593-140">Error Message : 10060, A connection attempt failed because the connected party</span></span>

<span data-ttu-id="3e593-141">Não respondeu corretamente após um período de tempo ou</span><span class="sxs-lookup"><span data-stu-id="3e593-141">did not properly respond after a period of time, or</span></span>

<span data-ttu-id="3e593-142">a conexão estabelecida falhou porque o host conectado tem</span><span class="sxs-lookup"><span data-stu-id="3e593-142">established connection failed because connected host has</span></span>

<span data-ttu-id="3e593-143">Falha ao responder 10.188.116.96:5061</span><span class="sxs-lookup"><span data-stu-id="3e593-143">failed to respond 10.188.116.96:5061</span></span>

<span data-ttu-id="3e593-144">Exceção interna: falha na tentativa de conexão porque o</span><span class="sxs-lookup"><span data-stu-id="3e593-144">Inner Exception:A connection attempt failed because the</span></span>

<span data-ttu-id="3e593-145">a parte conectada não respondeu corretamente após um período de</span><span class="sxs-lookup"><span data-stu-id="3e593-145">connected party did not properly respond after a period of</span></span>

<span data-ttu-id="3e593-146">a hora ou a conexão estabelecida falhou porque o host conectado</span><span class="sxs-lookup"><span data-stu-id="3e593-146">time, or established connection failed because connected host</span></span>

<span data-ttu-id="3e593-147">Falha ao responder 10.188.116.96:5061</span><span class="sxs-lookup"><span data-stu-id="3e593-147">has failed to respond 10.188.116.96:5061</span></span>

<span data-ttu-id="3e593-148">Diagnóstico</span><span class="sxs-lookup"><span data-stu-id="3e593-148">Diagnosis :</span></span>

<span data-ttu-id="3e593-149">Por exemplo, a saída anterior inclui a anotação "a parte conectada não respondeu corretamente" que geralmente indica um problema com o servidor de borda.</span><span class="sxs-lookup"><span data-stu-id="3e593-149">For example, the previous output includes the note “the connected party did not properly respond” That typically indicates a problem with the Edge Server.</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="3e593-150">Motivos pelos quais o teste pode ter falhado</span><span class="sxs-lookup"><span data-stu-id="3e593-150">Reasons why the test might have failed</span></span>

<span data-ttu-id="3e593-151">Aqui estão alguns motivos comuns pelos quais **Test-CsASConference** pode falhar:</span><span class="sxs-lookup"><span data-stu-id="3e593-151">Here are some common reasons why **Test-CsASConference** might fail:</span></span>

  - <span data-ttu-id="3e593-152">Um valor de parâmetro incorreto foi fornecido.</span><span class="sxs-lookup"><span data-stu-id="3e593-152">An incorrect parameter value was supplied.</span></span> <span data-ttu-id="3e593-153">Se usado, os parâmetros opcionais devem ser configurados corretamente ou o teste falhará.</span><span class="sxs-lookup"><span data-stu-id="3e593-153">If used, the optional parameters must be configured correctly or the test will fail.</span></span> <span data-ttu-id="3e593-154">Execute novamente o comando sem os parâmetros opcionais e veja se isso é bem-sucedido.</span><span class="sxs-lookup"><span data-stu-id="3e593-154">Rerun the command without the optional parameters and see whether that succeeds.</span></span>

  - <span data-ttu-id="3e593-155">Esse comando falhará se os usuários de teste tiverem uma política de conferência atribuída que os impede de usar o compartilhamento de aplicativos.</span><span class="sxs-lookup"><span data-stu-id="3e593-155">This command will fail if the test users were assigned a conferencing policy that prevents them from using application sharing.</span></span>

  - <span data-ttu-id="3e593-156">Esse comando falhará se o servidor de borda estiver configurado incorretamente ou ainda não tiver sido implantado.</span><span class="sxs-lookup"><span data-stu-id="3e593-156">This command will fail if the Edge Server is misconfigured or not yet deployed.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="3e593-157">Confira também</span><span class="sxs-lookup"><span data-stu-id="3e593-157">See Also</span></span>


[<span data-ttu-id="3e593-158">Get-CsConferencingPolicy</span><span class="sxs-lookup"><span data-stu-id="3e593-158">Get-CsConferencingPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsConferencingPolicy)  
[<span data-ttu-id="3e593-159">Test-CsDataConference</span><span class="sxs-lookup"><span data-stu-id="3e593-159">Test-CsDataConference</span></span>](https://docs.microsoft.com/powershell/module/skype/Test-CsDataConference)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

