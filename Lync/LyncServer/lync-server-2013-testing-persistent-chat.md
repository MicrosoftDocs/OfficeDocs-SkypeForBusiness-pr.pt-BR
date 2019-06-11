---
title: 'Lync Server 2013: testando chat persistente'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Testing persistent chat
ms:assetid: d351b6f2-bc31-42e0-9e8d-c347713d6b4a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn727313(v=OCS.15)
ms:contentKeyID: 63969651
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d4f805984382388fd44904db746d818decb8871a
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34844624"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="testing-persistent-chat-in-lync-server-2013"></a><span data-ttu-id="38761-102">Testando o chat persistente no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="38761-102">Testing persistent chat in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="38761-103">_**Tópico da última modificação:** 2014-11-03_</span><span class="sxs-lookup"><span data-stu-id="38761-103">_**Topic Last Modified:** 2014-11-03_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="38761-104">Cronograma de verificação</span><span class="sxs-lookup"><span data-stu-id="38761-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="38761-105">Diário</span><span class="sxs-lookup"><span data-stu-id="38761-105">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="38761-106">Ferramenta de teste</span><span class="sxs-lookup"><span data-stu-id="38761-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="38761-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="38761-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="38761-108">Permissões necessárias</span><span class="sxs-lookup"><span data-stu-id="38761-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="38761-109">Quando executado localmente usando o Shell de gerenciamento do Lync Server, os usuários devem ser membros do grupo de segurança RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="38761-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="38761-110">Quando executado usando uma instância remota do Windows PowerShell, os usuários devem receber uma função RBAC que tenha permissão para executar o cmdlet <strong>Test-CsPersistentChatMessage</strong> .</span><span class="sxs-lookup"><span data-stu-id="38761-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the <strong>Test-CsPersistentChatMessage</strong> cmdlet.</span></span> <span data-ttu-id="38761-111">Para ver uma lista de todas as funções RBAC que podem usar esse cmdlet, execute o seguinte comando no prompt do Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="38761-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsPersistentChatMessage&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="38761-112">Descrição</span><span class="sxs-lookup"><span data-stu-id="38761-112">Description</span></span>

<span data-ttu-id="38761-113">O cmdlet **Test-CsPersistentChatMessage** verifica se um par de usuários de teste podem trocar mensagens usando o serviço de chat persistente.</span><span class="sxs-lookup"><span data-stu-id="38761-113">The **Test-CsPersistentChatMessage** cmdlet verifies that a pair of test users can exchange messages using the Persistent Chat service.</span></span> <span data-ttu-id="38761-114">Para fazer isso, o cmdlet registra os dois usuários no Lync Server 2013, conecta os usuários a uma sala de chat persistente, troca um par de mensagens e, em seguida, sai da sala de chat e desconecta os dois usuários.</span><span class="sxs-lookup"><span data-stu-id="38761-114">To do this, the cmdlet logs the two users on to Lync Server 2013, connects the users to a persistent Chat room, exchanges a pair of messages, then exits the chat room and logs off the two users.</span></span> <span data-ttu-id="38761-115">Observe que as chamadas para esse cmdlet falharão se você não tiver criado nenhuma sala de chat ou se as duas contas de usuário de teste não forem atribuídas a uma política de chat persistente que lhes conceda acesso ao serviço de chat persistente.</span><span class="sxs-lookup"><span data-stu-id="38761-115">Note that calls to this cmdlet will fail if you have not created any chat rooms or if the two test user accounts are not assigned a Persistent Chat policy that gives them access to the Persistent Chat service.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="38761-116">Executar o teste</span><span class="sxs-lookup"><span data-stu-id="38761-116">Running the test</span></span>

<span data-ttu-id="38761-117">Os comandos mostrados no exemplo a seguir testam a capacidade de um par de usuários\\(litwareinc pilar\\e litwareinc kenmyer) para fazer logon no Lync Server 2013 e, em seguida, trocar mensagens usando o serviço de chat persistente.</span><span class="sxs-lookup"><span data-stu-id="38761-117">The commands shown in the following example test the ability of a pair of users (litwareinc\\pilar and litwareinc\\kenmyer) to log on to Lync Server 2013 and then exchange messages using the Persistent Chat service.</span></span> <span data-ttu-id="38761-118">Para fazer isso, o primeiro comando do exemplo usa o cmdlet **Get-Credential** para criar um objeto de credencial da interface de linha de comando do Windows PowerShell que contém o nome e a senha do pilar do usuário Alverca.</span><span class="sxs-lookup"><span data-stu-id="38761-118">To do this, the first command in the example uses the **Get-Credential** cmdlet to create a Windows PowerShell command-line interface credential object that contains the name and password of the user Pilar Ackerman.</span></span> <span data-ttu-id="38761-119">(Como o nome de logon,\\litwareinc pilar, foi incluído como um parâmetro, a caixa de diálogo solicitação de credenciais do Windows PowerShell exige que o administrador insira a senha para a conta pilar Alverca.) O objeto de credenciais resultante é armazenado em uma variável chamada $cred 1.</span><span class="sxs-lookup"><span data-stu-id="38761-119">(Because the logon name, litwareinc\\pilar, was included as a parameter, the Windows PowerShell Credential Request dialog box only requires the administrator to enter the password for the Pilar Ackerman account.) The resulting credentials object is then stored in a variable named $cred1.</span></span> <span data-ttu-id="38761-120">O segundo comando faz a mesma coisa, desta vez retornando um objeto Credential para a conta Ken Myer.</span><span class="sxs-lookup"><span data-stu-id="38761-120">The second command does the same thing, this time returning a credential object for the Ken Myer account.</span></span>

<span data-ttu-id="38761-121">Com os objetos de credenciais em mãos, o terceiro comando determina se esses dois usuários podem fazer logon no Lync Server 2013 e trocar mensagens usando o chat persistente.</span><span class="sxs-lookup"><span data-stu-id="38761-121">With the credential objects in hand, the third command determines whether these two users can log on to Lync Server 2013 and exchange messages using Persistent Chat.</span></span> <span data-ttu-id="38761-122">Para executar essa tarefa, o cmdlet **Test-CsPersistentChatMessage** é chamado usando os seguintes parâmetros: TargetFqdn (o FQDN do pool de registrador); SenderSipAddress (o endereço SIP para o primeiro usuário de teste); SenderCredential (o objeto do Windows PowerShell que contém as credenciais para esse mesmo usuário); ReceiverSipAddress (o endereço SIP para o outro usuário de teste); e ReceiverCredential (o objeto do Windows PowerShell que contém as credenciais do outro usuário de teste).</span><span class="sxs-lookup"><span data-stu-id="38761-122">To perform this task, the **Test-CsPersistentChatMessage** cmdlet is called using the following parameters: TargetFqdn (the FQDN of the Registrar pool); SenderSipAddress (the SIP address for the first test user); SenderCredential (the Windows PowerShell object that contains the credentials for this same user); ReceiverSipAddress (the SIP address for the other test user); and ReceiverCredential (the Windows PowerShell object that contains the credentials for the other test user).</span></span>

    $cred1 = Get-Credential "litwareinc\pilar"
    $cred2 = Get-Credential "litwareinc\kenmyer"
    
    Test-CsPersistentChatMessage -TargetFqdn atl-persistentchat-001.litwareinc.com -SenderSipAddress "sip:pilar@litwareinc.com" -SenderCredential $cred1 -ReceiverSipAddress "sip:kenmyer@litwareinc.com" -ReceiverCredential $cred2

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="38761-123">Determinação do sucesso ou falha</span><span class="sxs-lookup"><span data-stu-id="38761-123">Determining success or failure</span></span>

<span data-ttu-id="38761-124">Se o usuário especificado tiver uma política de local válida, você receberá uma saída semelhante a essa, com a propriedade Result marcada como **Success**:</span><span class="sxs-lookup"><span data-stu-id="38761-124">If the specified user has a valid location policy, then you'll receive output similar to this, with the Result property marked as **Success**:</span></span>

<span data-ttu-id="38761-125">FQDN de destino: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="38761-125">Target Fqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="38761-126">Resultado: êxito</span><span class="sxs-lookup"><span data-stu-id="38761-126">Result : Success</span></span>

<span data-ttu-id="38761-127">Latência: 00:00:00</span><span class="sxs-lookup"><span data-stu-id="38761-127">Latency : 00:00:00</span></span>

<span data-ttu-id="38761-128">Mensagem de erro:</span><span class="sxs-lookup"><span data-stu-id="38761-128">Error Message :</span></span>

<span data-ttu-id="38761-129">Correto</span><span class="sxs-lookup"><span data-stu-id="38761-129">Diagnosis :</span></span>

<span data-ttu-id="38761-130">Se os usuários especificados não puderem trocar mensagens usando o serviço de chat persistente, o resultado será mostrado como uma **falha**, e informações adicionais serão gravadas nas propriedades erro e diagnóstico:</span><span class="sxs-lookup"><span data-stu-id="38761-130">If the specified users can't exchange messages using the Persistent Chat service, the Result will be shown as **Failure**, and additional information will be recorded in the Error and Diagnosis properties:</span></span>

<span data-ttu-id="38761-131">Aviso: falha ao ler o número da porta do registrador para o número da porta de dados totalmente qualificado</span><span class="sxs-lookup"><span data-stu-id="38761-131">WARNING: Failed to read Registrar port number for the given fully qualified</span></span>

<span data-ttu-id="38761-132">FQDN (nome de domínio).</span><span class="sxs-lookup"><span data-stu-id="38761-132">domain name (FQDN).</span></span> <span data-ttu-id="38761-133">Usando o número da porta do registrador padrão.</span><span class="sxs-lookup"><span data-stu-id="38761-133">Using default Registrar port number.</span></span> <span data-ttu-id="38761-134">Extremamente</span><span class="sxs-lookup"><span data-stu-id="38761-134">Exception:</span></span>

<span data-ttu-id="38761-135">System. InvalidOperationException: nenhum cluster correspondente localizado na topologia.</span><span class="sxs-lookup"><span data-stu-id="38761-135">System.InvalidOperationException: No matching cluster found in topology.</span></span>

<span data-ttu-id="38761-136">como</span><span class="sxs-lookup"><span data-stu-id="38761-136">at</span></span>

<span data-ttu-id="38761-137">Microsoft. RTC. Management. SyntheticTransactions. SipSyntheticTransaction. TryRetri</span><span class="sxs-lookup"><span data-stu-id="38761-137">Microsoft.Rtc.Management.SyntheticTransactions.SipSyntheticTransaction.TryRetri</span></span>

<span data-ttu-id="38761-138">eveRegistrarPortFromTopology (Int32& registrarPortNumber)</span><span class="sxs-lookup"><span data-stu-id="38761-138">eveRegistrarPortFromTopology(Int32& registrarPortNumber)</span></span>

<span data-ttu-id="38761-139">FQDN de destino: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="38761-139">Target Fqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="38761-140">Resultado: falha</span><span class="sxs-lookup"><span data-stu-id="38761-140">Result : Failure</span></span>

<span data-ttu-id="38761-141">Latência: 00:00:00</span><span class="sxs-lookup"><span data-stu-id="38761-141">Latency : 00:00:00</span></span>

<span data-ttu-id="38761-142">Mensagem de erro: 10060, falha na tentativa de conexão porque a parte conectada</span><span class="sxs-lookup"><span data-stu-id="38761-142">Error Message : 10060, A connection attempt failed because the connected party</span></span>

<span data-ttu-id="38761-143">Não respondeu corretamente após um período de tempo ou</span><span class="sxs-lookup"><span data-stu-id="38761-143">did not properly respond after a period of time, or</span></span>

<span data-ttu-id="38761-144">a conexão estabelecida falhou porque o host conectado tem</span><span class="sxs-lookup"><span data-stu-id="38761-144">established connection failed because connected host has</span></span>

<span data-ttu-id="38761-145">Falha ao responder \[2001:4898: E8: f39e: 5c9a: ad83:81b3:9944\]: 5061</span><span class="sxs-lookup"><span data-stu-id="38761-145">failed to respond \[2001:4898:e8:f39e:5c9a:ad83:81b3:9944\]:5061</span></span>

<span data-ttu-id="38761-146">Exceção interna: falha na tentativa de conexão porque o</span><span class="sxs-lookup"><span data-stu-id="38761-146">Inner Exception:A connection attempt failed because the</span></span>

<span data-ttu-id="38761-147">a parte conectada não respondeu corretamente após um período de</span><span class="sxs-lookup"><span data-stu-id="38761-147">connected party did not properly respond after a period of</span></span>

<span data-ttu-id="38761-148">falha na hora ou estabelecida a conexão porque o host conectado</span><span class="sxs-lookup"><span data-stu-id="38761-148">time, or established connection failed because connected host</span></span>

<span data-ttu-id="38761-149">Não respondeu</span><span class="sxs-lookup"><span data-stu-id="38761-149">has failed to respond</span></span>

<span data-ttu-id="38761-150">\[2001:4898: E8: f39e: 5c9a: ad83:81b3:9944\]: 5061</span><span class="sxs-lookup"><span data-stu-id="38761-150">\[2001:4898:e8:f39e:5c9a:ad83:81b3:9944\]:5061</span></span>

<span data-ttu-id="38761-151">Correto</span><span class="sxs-lookup"><span data-stu-id="38761-151">Diagnosis :</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="38761-152">Motivos pelos quais o teste pode ter falhado</span><span class="sxs-lookup"><span data-stu-id="38761-152">Reasons why the test might have failed</span></span>

<span data-ttu-id="38761-153">Aqui estão alguns motivos comuns pelos quais **Test-CsPersistentChatMessage** pode falhar:</span><span class="sxs-lookup"><span data-stu-id="38761-153">Here are some common reasons why **Test-CsPersistentChatMessage** might fail:</span></span>

  - <span data-ttu-id="38761-154">Um valor de parâmetro incorreto foi fornecido.</span><span class="sxs-lookup"><span data-stu-id="38761-154">An incorrect parameter value was supplied.</span></span> <span data-ttu-id="38761-155">As contas de teste necessárias podem não existir ou terem sido criadas corretamente.</span><span class="sxs-lookup"><span data-stu-id="38761-155">The required test accounts may not exist or have been correctly created.</span></span>

  - <span data-ttu-id="38761-156">Pode ser que houve um problema de rede causando um atraso inesperado que esgotou o teste.</span><span class="sxs-lookup"><span data-stu-id="38761-156">There may have been a network issue causing an unexpected delay which timed out the test.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="38761-157">Confira também</span><span class="sxs-lookup"><span data-stu-id="38761-157">See Also</span></span>


[<span data-ttu-id="38761-158">Grant-CsPersistentChatPolicy</span><span class="sxs-lookup"><span data-stu-id="38761-158">Grant-CsPersistentChatPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Grant-CsPersistentChatPolicy)  
[<span data-ttu-id="38761-159">New-CsPersistentChatPolicy</span><span class="sxs-lookup"><span data-stu-id="38761-159">New-CsPersistentChatPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsPersistentChatPolicy)  
[<span data-ttu-id="38761-160">Set-CsPersistentChatPolicy</span><span class="sxs-lookup"><span data-stu-id="38761-160">Set-CsPersistentChatPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsPersistentChatPolicy)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

