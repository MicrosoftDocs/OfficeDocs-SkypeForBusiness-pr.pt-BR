---
title: 'Lync Server 2013: testar chat persistente'
description: 'Lync Server 2013: testar chat persistente.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing persistent chat
ms:assetid: d351b6f2-bc31-42e0-9e8d-c347713d6b4a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn727313(v=OCS.15)
ms:contentKeyID: 63969651
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a8b1dc4eef1870f1287dacdc1852ab1e24edd169
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48556277"
---
# <a name="testing-persistent-chat-in-lync-server-2013"></a><span data-ttu-id="65c70-103">Testando o chat persistente no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="65c70-103">Testing persistent chat in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="65c70-104">_**Última modificação do tópico:** 2014-11-03_</span><span class="sxs-lookup"><span data-stu-id="65c70-104">_**Topic Last Modified:** 2014-11-03_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="65c70-105">Agenda de verificação</span><span class="sxs-lookup"><span data-stu-id="65c70-105">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="65c70-106">Diariamente</span><span class="sxs-lookup"><span data-stu-id="65c70-106">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="65c70-107">Ferramenta de teste</span><span class="sxs-lookup"><span data-stu-id="65c70-107">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="65c70-108">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="65c70-108">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="65c70-109">Permissões obrigatórias</span><span class="sxs-lookup"><span data-stu-id="65c70-109">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="65c70-110">Ao executar localmente usando o Shell de gerenciamento do Lync Server, os usuários devem ser membros do grupo de segurança RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="65c70-110">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="65c70-111">Quando executado usando uma instância remota do Windows PowerShell, os usuários devem receber uma função RBAC que tenha permissão para executar o cmdlet <strong>Test-CsPersistentChatMessage</strong> .</span><span class="sxs-lookup"><span data-stu-id="65c70-111">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the <strong>Test-CsPersistentChatMessage</strong> cmdlet.</span></span> <span data-ttu-id="65c70-112">Para ver uma lista de todas as funções RBAC que podem usar este cmdlet, execute o seguinte comando no prompt do Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="65c70-112">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsPersistentChatMessage&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="65c70-113">Descrição</span><span class="sxs-lookup"><span data-stu-id="65c70-113">Description</span></span>

<span data-ttu-id="65c70-114">O cmdlet **Test-CsPersistentChatMessage** verifica se um par de usuários de teste podem trocar mensagens usando o serviço de chat persistente.</span><span class="sxs-lookup"><span data-stu-id="65c70-114">The **Test-CsPersistentChatMessage** cmdlet verifies that a pair of test users can exchange messages using the Persistent Chat service.</span></span> <span data-ttu-id="65c70-115">Para fazer isso, o cmdlet registra os dois usuários no Lync Server 2013, conecta os usuários a uma sala de chat persistente, troca um par de mensagens e, em seguida, sai da sala de chat e faz logoff dos dois usuários.</span><span class="sxs-lookup"><span data-stu-id="65c70-115">To do this, the cmdlet logs the two users on to Lync Server 2013, connects the users to a persistent Chat room, exchanges a pair of messages, then exits the chat room and logs off the two users.</span></span> <span data-ttu-id="65c70-116">Observe que as chamadas para este cmdlet falharão se você não tiver criado nenhuma sala de chat ou se as duas contas de usuário de teste não forem atribuídas a uma política de chat persistente que forneça acesso ao serviço de chat persistente.</span><span class="sxs-lookup"><span data-stu-id="65c70-116">Note that calls to this cmdlet will fail if you have not created any chat rooms or if the two test user accounts are not assigned a Persistent Chat policy that gives them access to the Persistent Chat service.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="65c70-117">Executar o teste</span><span class="sxs-lookup"><span data-stu-id="65c70-117">Running the test</span></span>

<span data-ttu-id="65c70-118">Os comandos mostrados no exemplo a seguir testam a capacidade de um par de usuários (litwareinc \\ pilar e litwareinc \\ kenmyer) para fazer logon no Lync Server 2013 e, em seguida, trocar mensagens usando o serviço de chat persistente.</span><span class="sxs-lookup"><span data-stu-id="65c70-118">The commands shown in the following example test the ability of a pair of users (litwareinc\\pilar and litwareinc\\kenmyer) to log on to Lync Server 2013 and then exchange messages using the Persistent Chat service.</span></span> <span data-ttu-id="65c70-119">Para fazer isso, o primeiro comando no exemplo usa o cmdlet **Get-Credential** para criar um objeto de credencial da interface de linha de comando do Windows PowerShell que contenha o nome e a senha do usuário pilar Ackerman.</span><span class="sxs-lookup"><span data-stu-id="65c70-119">To do this, the first command in the example uses the **Get-Credential** cmdlet to create a Windows PowerShell command-line interface credential object that contains the name and password of the user Pilar Ackerman.</span></span> <span data-ttu-id="65c70-120">(Como o nome de logon, litwareinc \\ pilar, foi incluído como um parâmetro, a caixa de diálogo de solicitação de credencial do Windows PowerShell só exige que o administrador insira a senha da conta pilar Ackerman.) O objeto de credenciais resultante é armazenado em uma variável chamada $cred 1.</span><span class="sxs-lookup"><span data-stu-id="65c70-120">(Because the logon name, litwareinc\\pilar, was included as a parameter, the Windows PowerShell Credential Request dialog box only requires the administrator to enter the password for the Pilar Ackerman account.) The resulting credentials object is then stored in a variable named $cred1.</span></span> <span data-ttu-id="65c70-121">O segundo comando fará o mesmo, retornando, desta vez, um objeto de credencial para a conta de Ken Myer.</span><span class="sxs-lookup"><span data-stu-id="65c70-121">The second command does the same thing, this time returning a credential object for the Ken Myer account.</span></span>

<span data-ttu-id="65c70-122">Com os objetos de credencial em mãos, o terceiro comando determina se esses dois usuários podem fazer logon no Lync Server 2013 e trocar mensagens usando o chat persistente.</span><span class="sxs-lookup"><span data-stu-id="65c70-122">With the credential objects in hand, the third command determines whether these two users can log on to Lync Server 2013 and exchange messages using Persistent Chat.</span></span> <span data-ttu-id="65c70-123">Para realizar essa tarefa, o cmdlet **Test-CsPersistentChatMessage** é chamado usando os seguintes parâmetros: TargetFqdn (o FQDN do pool de registrador); SenderSipAddress (o endereço SIP para o primeiro usuário de teste); SenderCredential (o objeto Windows PowerShell que contém as credenciais desse mesmo usuário); ReceiverSipAddress (o endereço SIP para o outro usuário de teste); e ReceiverCredential (o objeto Windows PowerShell que contém as credenciais para o outro usuário de teste).</span><span class="sxs-lookup"><span data-stu-id="65c70-123">To perform this task, the **Test-CsPersistentChatMessage** cmdlet is called using the following parameters: TargetFqdn (the FQDN of the Registrar pool); SenderSipAddress (the SIP address for the first test user); SenderCredential (the Windows PowerShell object that contains the credentials for this same user); ReceiverSipAddress (the SIP address for the other test user); and ReceiverCredential (the Windows PowerShell object that contains the credentials for the other test user).</span></span>

    $cred1 = Get-Credential "litwareinc\pilar"
    $cred2 = Get-Credential "litwareinc\kenmyer"
    
    Test-CsPersistentChatMessage -TargetFqdn atl-persistentchat-001.litwareinc.com -SenderSipAddress "sip:pilar@litwareinc.com" -SenderCredential $cred1 -ReceiverSipAddress "sip:kenmyer@litwareinc.com" -ReceiverCredential $cred2

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="65c70-124">Determinando o sucesso ou a falha</span><span class="sxs-lookup"><span data-stu-id="65c70-124">Determining success or failure</span></span>

<span data-ttu-id="65c70-125">Se o usuário especificado tiver uma política de local válida, você receberá uma saída semelhante a esta, com a propriedade Result marcada como **Success**:</span><span class="sxs-lookup"><span data-stu-id="65c70-125">If the specified user has a valid location policy, then you'll receive output similar to this, with the Result property marked as **Success**:</span></span>

<span data-ttu-id="65c70-126">FQDN de destino: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="65c70-126">Target Fqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="65c70-127">Resultado: êxito</span><span class="sxs-lookup"><span data-stu-id="65c70-127">Result : Success</span></span>

<span data-ttu-id="65c70-128">Latência: 00:00:00</span><span class="sxs-lookup"><span data-stu-id="65c70-128">Latency : 00:00:00</span></span>

<span data-ttu-id="65c70-129">Mensagem de erro:</span><span class="sxs-lookup"><span data-stu-id="65c70-129">Error Message :</span></span>

<span data-ttu-id="65c70-130">Diagnóstico</span><span class="sxs-lookup"><span data-stu-id="65c70-130">Diagnosis :</span></span>

<span data-ttu-id="65c70-131">Se os usuários especificados não puderem trocar mensagens usando o serviço de chat persistente, o resultado será mostrado como **falha**e informações adicionais serão registradas nas propriedades de erro e diagnóstico:</span><span class="sxs-lookup"><span data-stu-id="65c70-131">If the specified users can't exchange messages using the Persistent Chat service, the Result will be shown as **Failure**, and additional information will be recorded in the Error and Diagnosis properties:</span></span>

<span data-ttu-id="65c70-132">Aviso: falha ao ler o número da porta do registrador para o fornecido totalmente qualificado</span><span class="sxs-lookup"><span data-stu-id="65c70-132">WARNING: Failed to read Registrar port number for the given fully qualified</span></span>

<span data-ttu-id="65c70-133">FQDN (nome de domínio).</span><span class="sxs-lookup"><span data-stu-id="65c70-133">domain name (FQDN).</span></span> <span data-ttu-id="65c70-134">Usando o número da porta do registrador padrão.</span><span class="sxs-lookup"><span data-stu-id="65c70-134">Using default Registrar port number.</span></span> <span data-ttu-id="65c70-135">Exceções</span><span class="sxs-lookup"><span data-stu-id="65c70-135">Exception:</span></span>

<span data-ttu-id="65c70-136">System. InvalidOperationException: nenhum cluster correspondente encontrado na topologia.</span><span class="sxs-lookup"><span data-stu-id="65c70-136">System.InvalidOperationException: No matching cluster found in topology.</span></span>

<span data-ttu-id="65c70-137">por</span><span class="sxs-lookup"><span data-stu-id="65c70-137">at</span></span>

<span data-ttu-id="65c70-138">Microsoft. RTC. Management. SyntheticTransactions. SipSyntheticTransaction. TryRetri</span><span class="sxs-lookup"><span data-stu-id="65c70-138">Microsoft.Rtc.Management.SyntheticTransactions.SipSyntheticTransaction.TryRetri</span></span>

<span data-ttu-id="65c70-139">eveRegistrarPortFromTopology (Int32& registrarPortNumber)</span><span class="sxs-lookup"><span data-stu-id="65c70-139">eveRegistrarPortFromTopology(Int32& registrarPortNumber)</span></span>

<span data-ttu-id="65c70-140">FQDN de destino: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="65c70-140">Target Fqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="65c70-141">Resultado: falha</span><span class="sxs-lookup"><span data-stu-id="65c70-141">Result : Failure</span></span>

<span data-ttu-id="65c70-142">Latência: 00:00:00</span><span class="sxs-lookup"><span data-stu-id="65c70-142">Latency : 00:00:00</span></span>

<span data-ttu-id="65c70-143">Mensagem de erro: 10060, uma tentativa de conexão falhou porque a parte conectada</span><span class="sxs-lookup"><span data-stu-id="65c70-143">Error Message : 10060, A connection attempt failed because the connected party</span></span>

<span data-ttu-id="65c70-144">Não respondeu corretamente após um período de tempo ou</span><span class="sxs-lookup"><span data-stu-id="65c70-144">did not properly respond after a period of time, or</span></span>

<span data-ttu-id="65c70-145">a conexão estabelecida falhou porque o host conectado tem</span><span class="sxs-lookup"><span data-stu-id="65c70-145">established connection failed because connected host has</span></span>

<span data-ttu-id="65c70-146">Falha ao responder \[ 2001:4898: E8: f39e: 5c9a: ad83:81b3:9944: \] 5061</span><span class="sxs-lookup"><span data-stu-id="65c70-146">failed to respond \[2001:4898:e8:f39e:5c9a:ad83:81b3:9944\]:5061</span></span>

<span data-ttu-id="65c70-147">Exceção interna: falha na tentativa de conexão porque o</span><span class="sxs-lookup"><span data-stu-id="65c70-147">Inner Exception:A connection attempt failed because the</span></span>

<span data-ttu-id="65c70-148">a parte conectada não respondeu corretamente após um período de</span><span class="sxs-lookup"><span data-stu-id="65c70-148">connected party did not properly respond after a period of</span></span>

<span data-ttu-id="65c70-149">a hora ou a conexão estabelecida falhou porque o host conectado</span><span class="sxs-lookup"><span data-stu-id="65c70-149">time, or established connection failed because connected host</span></span>

<span data-ttu-id="65c70-150">falhou ao responder</span><span class="sxs-lookup"><span data-stu-id="65c70-150">has failed to respond</span></span>

<span data-ttu-id="65c70-151">\[2001:4898: E8: f39e: 5c9a: ad83:81b3: \] 5061</span><span class="sxs-lookup"><span data-stu-id="65c70-151">\[2001:4898:e8:f39e:5c9a:ad83:81b3:9944\]:5061</span></span>

<span data-ttu-id="65c70-152">Diagnóstico</span><span class="sxs-lookup"><span data-stu-id="65c70-152">Diagnosis :</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="65c70-153">Motivos pelos quais o teste pode ter falhado</span><span class="sxs-lookup"><span data-stu-id="65c70-153">Reasons why the test might have failed</span></span>

<span data-ttu-id="65c70-154">Aqui estão alguns motivos comuns pelos quais **Test-CsPersistentChatMessage** pode falhar:</span><span class="sxs-lookup"><span data-stu-id="65c70-154">Here are some common reasons why **Test-CsPersistentChatMessage** might fail:</span></span>

  - <span data-ttu-id="65c70-155">Um valor de parâmetro incorreto foi fornecido.</span><span class="sxs-lookup"><span data-stu-id="65c70-155">An incorrect parameter value was supplied.</span></span> <span data-ttu-id="65c70-156">As contas de teste necessárias podem não existir ou terem sido criadas corretamente.</span><span class="sxs-lookup"><span data-stu-id="65c70-156">The required test accounts may not exist or have been correctly created.</span></span>

  - <span data-ttu-id="65c70-157">Pode ter havido um problema de rede causando um atraso inesperado que esgotou o tempo de teste.</span><span class="sxs-lookup"><span data-stu-id="65c70-157">There may have been a network issue causing an unexpected delay which timed out the test.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="65c70-158">Confira também</span><span class="sxs-lookup"><span data-stu-id="65c70-158">See Also</span></span>


[<span data-ttu-id="65c70-159">Grant-CsPersistentChatPolicy</span><span class="sxs-lookup"><span data-stu-id="65c70-159">Grant-CsPersistentChatPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Grant-CsPersistentChatPolicy)  
[<span data-ttu-id="65c70-160">New-CsPersistentChatPolicy</span><span class="sxs-lookup"><span data-stu-id="65c70-160">New-CsPersistentChatPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsPersistentChatPolicy)  
[<span data-ttu-id="65c70-161">Set-CsPersistentChatPolicy</span><span class="sxs-lookup"><span data-stu-id="65c70-161">Set-CsPersistentChatPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsPersistentChatPolicy)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

