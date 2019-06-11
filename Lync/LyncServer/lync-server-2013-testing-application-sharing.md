---
title: 'Lync Server 2013: testando o compartilhamento de aplicativos'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Testing application sharing
ms:assetid: 8d21db9b-10d1-4b43-b057-0deb1df1c205
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn727310(v=OCS.15)
ms:contentKeyID: 63969629
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 77a65e2dbea8ca0df01fab37c08f47c8e7d0c5b6
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34844644"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="testing-application-sharing-in-lync-server-2013"></a><span data-ttu-id="07ea5-102">Testando o compartilhamento de aplicativos no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="07ea5-102">Testing application sharing in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="07ea5-103">_**Tópico da última modificação:** 2014-11-01_</span><span class="sxs-lookup"><span data-stu-id="07ea5-103">_**Topic Last Modified:** 2014-11-01_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="07ea5-104">Cronograma de verificação</span><span class="sxs-lookup"><span data-stu-id="07ea5-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="07ea5-105">Diário</span><span class="sxs-lookup"><span data-stu-id="07ea5-105">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="07ea5-106">Ferramenta de teste</span><span class="sxs-lookup"><span data-stu-id="07ea5-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="07ea5-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="07ea5-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="07ea5-108">Permissões necessárias</span><span class="sxs-lookup"><span data-stu-id="07ea5-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="07ea5-109">Quando executado localmente usando o Shell de gerenciamento do Lync Server, os usuários devem ser membros do grupo de segurança RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="07ea5-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="07ea5-110">Quando executado usando uma instância remota do Windows PowerShell, os usuários devem receber uma função RBAC que tenha permissão para executar o cmdlet Test-CsASConference.</span><span class="sxs-lookup"><span data-stu-id="07ea5-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsASConference cmdlet.</span></span> <span data-ttu-id="07ea5-111">Para ver uma lista de todas as funções RBAC que podem usar esse cmdlet, execute o seguinte comando no prompt do Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="07ea5-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsASConference&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="07ea5-112">Descrição</span><span class="sxs-lookup"><span data-stu-id="07ea5-112">Description</span></span>

<span data-ttu-id="07ea5-113">O cmdlet **Test-CsASConference** verifica se um par de usuários de teste podem participar de uma conferência online que inclui compartilhamento de aplicativos.</span><span class="sxs-lookup"><span data-stu-id="07ea5-113">The **Test-CsASConference** cmdlet verifies that a pair of test users can participate in an online conference that includes application sharing.</span></span> <span data-ttu-id="07ea5-114">Para fazer isso, o cmdlet registra os dois usuários com o Lync Server 2013 e, em seguida, usa uma das contas de usuário para criar uma nova conferência que inclua o compartilhamento de aplicativos.</span><span class="sxs-lookup"><span data-stu-id="07ea5-114">To do this, the cmdlet registers the two users with Lync Server 2013, and then it uses one of the user accounts to create a new conference that includes applications sharing.</span></span> <span data-ttu-id="07ea5-115">Em seguida, o cmdlet verifica se o segundo usuário consegue ingressar na conferência.</span><span class="sxs-lookup"><span data-stu-id="07ea5-115">The cmdlet then verifies that the second user is able to join that conference.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="07ea5-116">Executar o teste</span><span class="sxs-lookup"><span data-stu-id="07ea5-116">Running the test</span></span>

<span data-ttu-id="07ea5-117">O comando mostrado no exemplo 1 verifica se uma conferência de compartilhamento de aplicativo pode ser conduzida na atl-cs-001.litwareinc.com do pool.</span><span class="sxs-lookup"><span data-stu-id="07ea5-117">The command shown in Example 1 verifies that an Application Sharing conference can be conducted on the pool atl-cs-001.litwareinc.com.</span></span> <span data-ttu-id="07ea5-118">Esse comando pressupõe que você configurou um par de usuários de teste para o pool especificado.</span><span class="sxs-lookup"><span data-stu-id="07ea5-118">This command assumes that you have configured a pair of test users for the specified pool.</span></span> <span data-ttu-id="07ea5-119">Se não houver esses usuários de teste, o comando falhará.</span><span class="sxs-lookup"><span data-stu-id="07ea5-119">If no such test users exist, the command will fail.</span></span>

    Test-CsASConference -TargetFqdn "atl-cs-001.litwareinc.com"

<span data-ttu-id="07ea5-120">O exemplo 2 testa a capacidade do serviço de inicializador de junção participar de uma conferência de compartilhamento de aplicativos no pool atl-cs-001.litwareinc.com.</span><span class="sxs-lookup"><span data-stu-id="07ea5-120">Example 2 tests the ability of the Join Launcher service to participate in an Application Sharing conference on the pool atl-cs-001.litwareinc.com.</span></span> <span data-ttu-id="07ea5-121">Observe que esse comando testa somente o próprio serviço; Você não precisa de dispositivos móveis para executar o comando.</span><span class="sxs-lookup"><span data-stu-id="07ea5-121">Note that this command tests only the service itself; you do not need any mobile devices in order to run the command.</span></span>

    Test-CsASConference -TargetFqdn "atl-cs-001.litwareinc.com" -TestJoinLauncher 

<span data-ttu-id="07ea5-122">Os comandos mostrados no exemplo 2 testam a capacidade de um par de usuários\\(litwareinc pilar\\e litwareinc kenmyer) para fazer logon no Lync Server 2013 e conduzir uma conferência de compartilhamento de aplicativos.</span><span class="sxs-lookup"><span data-stu-id="07ea5-122">The commands shown in Example 2 test the ability of a pair of users (litwareinc\\pilar and litwareinc\\kenmyer) to log on to Lync Server 2013 and then conduct an Application Sharing conference.</span></span> <span data-ttu-id="07ea5-123">Para fazer isso, o primeiro comando do exemplo usa o cmdlet Get-Credential para criar um objeto de credencial da interface de linha de comando do Windows PowerShell contendo o nome e a senha do pilar do usuário Alverca.</span><span class="sxs-lookup"><span data-stu-id="07ea5-123">To do this, the first command in the example uses the Get-Credential cmdlet to create a Windows PowerShell command-line interface credential object containing the name and password of the user Pilar Ackerman.</span></span> <span data-ttu-id="07ea5-124">(Como o nome de logon,\\litwareinc pilar, foi incluído como um parâmetro, a caixa de diálogo solicitação de credenciais do Windows PowerShell exige apenas que o administrador insira a senha da conta pilar Alverca.) O objeto Credential resultante é armazenado em uma variável chamada $cred 1.</span><span class="sxs-lookup"><span data-stu-id="07ea5-124">(Because the logon name, litwareinc\\pilar, has been included as a parameter, the Windows PowerShell Credential Request dialog box only requires the administrator to enter the password for the Pilar Ackerman account.) The resulting credential object is then stored in a variable named $cred1.</span></span> <span data-ttu-id="07ea5-125">O segundo comando faz a mesma coisa, desta vez retornando um objeto Credential para a conta Ken Myer.</span><span class="sxs-lookup"><span data-stu-id="07ea5-125">The second command does the same thing, this time returning a credential object for the Ken Myer account.</span></span>

<span data-ttu-id="07ea5-126">Com os objetos de credenciais em mãos, o terceiro comando determina se esses dois usuários podem ou não fazer logon no Lync Server 2013 e conduzir uma conferência de compartilhamento de aplicativos.</span><span class="sxs-lookup"><span data-stu-id="07ea5-126">With the credential objects in hand, the third command determines whether or not these two users can log on to Lync Server 2013 and conduct an Application Sharing conference.</span></span> <span data-ttu-id="07ea5-127">Para executar essa tarefa, o cmdlet **Test-CsASConference** é chamado, juntamente com os seguintes parâmetros: TargetFqdn (o FQDN do pool de registrador); SenderSipAddress (o endereço SIP para o primeiro usuário de teste); SenderCredential (o objeto do Windows PowerShell que contém as credenciais para esse mesmo usuário); ReceiverSipAddress (o endereço SIP para o outro usuário de teste); e ReceiverCredential (o objeto do Windows PowerShell que contém as credenciais do outro usuário de teste).</span><span class="sxs-lookup"><span data-stu-id="07ea5-127">To carry out this task, the **Test-CsASConference** cmdlet is called, along with the following parameters: TargetFqdn (the FQDN of the Registrar pool); SenderSipAddress (the SIP address for the first test user); SenderCredential (the Windows PowerShell object containing the credentials for this same user); ReceiverSipAddress (the SIP address for the other test user); and ReceiverCredential (the Windows PowerShell object containing the credentials for the other test user).</span></span>

    $cred1 = Get-Credential "litwareinc\pilar" 
    $cred2 = Get-Credential "litwareinc\kenmyer" 
    Test-CsASConference -TargetFqdn atl-cs-001.litwareinc.com -SenderSipAddress "sip:pilar@litwareinc.com" -SenderCredential $cred1 -ReceiverSipAddress "sip:kenmyer@litwareinc.com" -ReceiverCredential $cred2

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="07ea5-128">Determinação do sucesso ou falha</span><span class="sxs-lookup"><span data-stu-id="07ea5-128">Determining success or failure</span></span>

<span data-ttu-id="07ea5-129">Se o compartilhamento de aplicativos estiver configurado corretamente, você receberá uma saída semelhante a isso, com a propriedade Result marcada como **Success:**</span><span class="sxs-lookup"><span data-stu-id="07ea5-129">If application sharing is correctly configured, you'll receive output similar to this, with the Result property marked as **Success:**</span></span>

<span data-ttu-id="07ea5-130">FQDN de destino: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="07ea5-130">Target Fqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="07ea5-131">Resultado: êxito</span><span class="sxs-lookup"><span data-stu-id="07ea5-131">Result : Success</span></span>

<span data-ttu-id="07ea5-132">Latência: 00:00:01</span><span class="sxs-lookup"><span data-stu-id="07ea5-132">Latency : 00:00:01</span></span>

<span data-ttu-id="07ea5-133">Mensagem de erro:</span><span class="sxs-lookup"><span data-stu-id="07ea5-133">Error Message :</span></span>

<span data-ttu-id="07ea5-134">Correto</span><span class="sxs-lookup"><span data-stu-id="07ea5-134">Diagnosis :</span></span>

<span data-ttu-id="07ea5-135">Se os usuários especificados não puderem compartilhar aplicativos, o resultado será mostrado como uma falha, e informações adicionais serão gravadas nas propriedades de erro e diagnóstico:</span><span class="sxs-lookup"><span data-stu-id="07ea5-135">If the specified users can't share applications, the Result will be shown as Failure, and additional information will be recorded in the Error and Diagnosis properties:</span></span>

<span data-ttu-id="07ea5-136">FQDN de destino: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="07ea5-136">Target Fqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="07ea5-137">Resultado: falha</span><span class="sxs-lookup"><span data-stu-id="07ea5-137">Result : Failure</span></span>

<span data-ttu-id="07ea5-138">Latência: 00:00:00</span><span class="sxs-lookup"><span data-stu-id="07ea5-138">Latency : 00:00:00</span></span>

<span data-ttu-id="07ea5-139">Mensagem de erro: 10060, falha na tentativa de conexão porque a parte conectada</span><span class="sxs-lookup"><span data-stu-id="07ea5-139">Error Message : 10060, A connection attempt failed because the connected party</span></span>

<span data-ttu-id="07ea5-140">Não respondeu corretamente após um período de tempo ou</span><span class="sxs-lookup"><span data-stu-id="07ea5-140">did not properly respond after a period of time, or</span></span>

<span data-ttu-id="07ea5-141">a conexão estabelecida falhou porque o host conectado tem</span><span class="sxs-lookup"><span data-stu-id="07ea5-141">established connection failed because connected host has</span></span>

<span data-ttu-id="07ea5-142">Falha ao responder 10.188.116.96:5061</span><span class="sxs-lookup"><span data-stu-id="07ea5-142">failed to respond 10.188.116.96:5061</span></span>

<span data-ttu-id="07ea5-143">Exceção interna: falha na tentativa de conexão porque o</span><span class="sxs-lookup"><span data-stu-id="07ea5-143">Inner Exception:A connection attempt failed because the</span></span>

<span data-ttu-id="07ea5-144">a parte conectada não respondeu corretamente após um período de</span><span class="sxs-lookup"><span data-stu-id="07ea5-144">connected party did not properly respond after a period of</span></span>

<span data-ttu-id="07ea5-145">falha na hora ou estabelecida a conexão porque o host conectado</span><span class="sxs-lookup"><span data-stu-id="07ea5-145">time, or established connection failed because connected host</span></span>

<span data-ttu-id="07ea5-146">falhou ao responder 10.188.116.96:5061</span><span class="sxs-lookup"><span data-stu-id="07ea5-146">has failed to respond 10.188.116.96:5061</span></span>

<span data-ttu-id="07ea5-147">Correto</span><span class="sxs-lookup"><span data-stu-id="07ea5-147">Diagnosis :</span></span>

<span data-ttu-id="07ea5-148">Por exemplo, a saída anterior inclui a anotação "a parte conectada não respondeu corretamente" que geralmente indica um problema com o servidor de borda.</span><span class="sxs-lookup"><span data-stu-id="07ea5-148">For example, the previous output includes the note “the connected party did not properly respond” That typically indicates a problem with the Edge Server.</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="07ea5-149">Motivos pelos quais o teste pode ter falhado</span><span class="sxs-lookup"><span data-stu-id="07ea5-149">Reasons why the test might have failed</span></span>

<span data-ttu-id="07ea5-150">Aqui estão alguns motivos comuns pelos quais **Test-CsASConference** pode falhar:</span><span class="sxs-lookup"><span data-stu-id="07ea5-150">Here are some common reasons why **Test-CsASConference** might fail:</span></span>

  - <span data-ttu-id="07ea5-151">Um valor de parâmetro incorreto foi fornecido.</span><span class="sxs-lookup"><span data-stu-id="07ea5-151">An incorrect parameter value was supplied.</span></span> <span data-ttu-id="07ea5-152">Se usado, os parâmetros opcionais devem ser configurados corretamente ou o teste falhará.</span><span class="sxs-lookup"><span data-stu-id="07ea5-152">If used, the optional parameters must be configured correctly or the test will fail.</span></span> <span data-ttu-id="07ea5-153">Execute o comando novamente sem os parâmetros opcionais e veja se isso é bem-sucedido.</span><span class="sxs-lookup"><span data-stu-id="07ea5-153">Rerun the command without the optional parameters and see whether that succeeds.</span></span>

  - <span data-ttu-id="07ea5-154">Esse comando falhará se os usuários de teste tiverem sido atribuídos a uma política de conferência que os impeça de usar o compartilhamento de aplicativos.</span><span class="sxs-lookup"><span data-stu-id="07ea5-154">This command will fail if the test users were assigned a conferencing policy that prevents them from using application sharing.</span></span>

  - <span data-ttu-id="07ea5-155">Esse comando falhará se o servidor de borda estiver configurado incorretamente ou ainda não foi implantado.</span><span class="sxs-lookup"><span data-stu-id="07ea5-155">This command will fail if the Edge Server is misconfigured or not yet deployed.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="07ea5-156">Confira também</span><span class="sxs-lookup"><span data-stu-id="07ea5-156">See Also</span></span>


[<span data-ttu-id="07ea5-157">Get-CsConferencingPolicy</span><span class="sxs-lookup"><span data-stu-id="07ea5-157">Get-CsConferencingPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsConferencingPolicy)  
[<span data-ttu-id="07ea5-158">Test-CsDataConference</span><span class="sxs-lookup"><span data-stu-id="07ea5-158">Test-CsDataConference</span></span>](https://docs.microsoft.com/powershell/module/skype/Test-CsDataConference)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

