---
title: 'Lync Server 2013: testando mensagens usando o XMPP'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Testing messaging using XMPP
ms:assetid: ae5305ba-e5fc-4ca0-a805-872b4ebaf981
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn727312(v=OCS.15)
ms:contentKeyID: 63969641
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: acd03cdf2a5215c980b788dbaffafc5936fe5b5e
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34844633"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="testing-messaging-using-xmpp-in-lync-server-2013"></a><span data-ttu-id="c2b06-102">Testando mensagens usando o XMPP no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c2b06-102">Testing messaging using XMPP in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c2b06-103">_**Tópico da última modificação:** 2014-11-03_</span><span class="sxs-lookup"><span data-stu-id="c2b06-103">_**Topic Last Modified:** 2014-11-03_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c2b06-104">Cronograma de verificação</span><span class="sxs-lookup"><span data-stu-id="c2b06-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="c2b06-105">Diário</span><span class="sxs-lookup"><span data-stu-id="c2b06-105">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c2b06-106">Ferramenta de teste</span><span class="sxs-lookup"><span data-stu-id="c2b06-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="c2b06-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="c2b06-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c2b06-108">Permissões necessárias</span><span class="sxs-lookup"><span data-stu-id="c2b06-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="c2b06-109">Quando executado localmente usando o Shell de gerenciamento do Lync Server, os usuários devem ser membros do grupo de segurança RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="c2b06-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="c2b06-110">Quando executado usando uma instância remota do Windows PowerShell, os usuários devem receber uma função RBAC que tenha permissão para executar o cmdlet <strong>Test-CsXmppIM</strong> .</span><span class="sxs-lookup"><span data-stu-id="c2b06-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the <strong>Test-CsXmppIM</strong> cmdlet.</span></span> <span data-ttu-id="c2b06-111">Para ver uma lista de todas as funções RBAC que podem usar esse cmdlet, execute o seguinte comando no prompt do Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="c2b06-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsXmppIM&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="c2b06-112">Descrição</span><span class="sxs-lookup"><span data-stu-id="c2b06-112">Description</span></span>

<span data-ttu-id="c2b06-113">O protocolo de comunicação e mensagens extensíveis (XMPP) é um protocolo de comunicação padrão (baseado em XML) usado para enviar mensagens pela Internet.</span><span class="sxs-lookup"><span data-stu-id="c2b06-113">The Extensible Messaging and Presence Protocol (XMPP) is a standard communications protocol (based on XML) used for sending messages across the Internet.</span></span> <span data-ttu-id="c2b06-114">O XMPP foi nomeado originalmente como Jabber e é compatível com diversos aplicativos de comunicação e mensagens pela Internet, como Google Talk e chat do Facebook.</span><span class="sxs-lookup"><span data-stu-id="c2b06-114">XMPP was originally named Jabber, and is supported by several Internet messaging and communication applications, such as Google Talk and Facebook Chat.</span></span> <span data-ttu-id="c2b06-115">O cmdlet **Test-CsXmppIM** verifica se um usuário pode trocar mensagens de chat com um usuário em uma rede do XMPP.</span><span class="sxs-lookup"><span data-stu-id="c2b06-115">The **Test-CsXmppIM** cmdlet verifies that a user can exchange instant messages with a user on an XMPP network.</span></span> <span data-ttu-id="c2b06-116">Observe que, para esse teste ter êxito, você deve ter um endereço SIP válido para o usuário do XMPP e esse endereço SIP deve estar em uma rede que foi configurada como um parceiro de XMPP permitido.</span><span class="sxs-lookup"><span data-stu-id="c2b06-116">Note that, for this test to succeed, you must have a valid SIP address for the XMPP user, and that SIP address must be on a network that was configured as an allowed XMPP partner.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="c2b06-117">Executar o teste</span><span class="sxs-lookup"><span data-stu-id="c2b06-117">Running the test</span></span>

<span data-ttu-id="c2b06-118">O exemplo a seguir verifica os recursos de mensagem instantânea do XMPP para o pool atl-cs-001.litwareinc.com.</span><span class="sxs-lookup"><span data-stu-id="c2b06-118">The following example verifies the XMPP instant messaging capabilities for the pool atl-cs-001.litwareinc.com.</span></span> <span data-ttu-id="c2b06-119">Esse comando funcionará apenas se os usuários de teste estiverem definidos para o pool atl-cs-001.litwareinc.com.</span><span class="sxs-lookup"><span data-stu-id="c2b06-119">This command will work only if test users are defined for the pool atl-cs-001.litwareinc.com.</span></span> <span data-ttu-id="c2b06-120">Se eles tiverem, o comando determinará se o primeiro usuário de teste pode enviar uma mensagem de chat do XMPP para um usuário que tenha o endereço SIP adelaney@contoso.com.</span><span class="sxs-lookup"><span data-stu-id="c2b06-120">If they have, then the command will determine whether the first test user can send an XMPP instant message to a user who has the SIP address adelaney@contoso.com.</span></span>

<span data-ttu-id="c2b06-121">Se os usuários de teste não estiverem definidos, o comando falhará porque não saberá qual usuário deve fazer logon.</span><span class="sxs-lookup"><span data-stu-id="c2b06-121">If test users are not defined, then the command will fail because it won't know which user to log on as.</span></span> <span data-ttu-id="c2b06-122">Se você não definiu usuários de teste para um pool, deve incluir o parâmetro UserSipAddress e as credenciais do usuário que o comando deve usar ao tentar fazer logon.</span><span class="sxs-lookup"><span data-stu-id="c2b06-122">If you have not defined test users for a pool, then you must include the UserSipAddress parameter and the credentials of the user who the command should use when trying to log on.</span></span>

    Test-CsXmppIM -TargetFqdn "atl-cs-001.litwareinc.com" -Receiver "adelany@contoso.com"

<span data-ttu-id="c2b06-123">Os comandos mostrados no próximo exemplo testam a capacidade de um usuário específico (\\litwareinc pilar) para fazer logon para enviar uma mensagem de chat do XMPP para o adelaney@contoso.com do usuário.</span><span class="sxs-lookup"><span data-stu-id="c2b06-123">The commands shown in the next example test the ability of a specific user (litwareinc\\pilar) to log on to send an XMPP instant message to the user adelaney@contoso.com.</span></span> <span data-ttu-id="c2b06-124">Para fazer isso, o primeiro comando do exemplo usa o cmdlet Get-Credential para criar um objeto de credencial da interface de linha de comando do Windows PowerShell que contém o nome e a senha do pilar do usuário Alverca.</span><span class="sxs-lookup"><span data-stu-id="c2b06-124">To do this, the first command in the example uses the Get-Credential cmdlet to create a Windows PowerShell command-line interface credential object that contains the name and password of the user Pilar Ackerman.</span></span> <span data-ttu-id="c2b06-125">(Como o nome de logon\\litwareinc pilar foi incluído como um parâmetro, a caixa de diálogo solicitação de credenciais do Windows PowerShell exige que o administrador insira a senha para a conta pilar Alverca.) O objeto Credential resultante é armazenado em uma variável chamada $cred 1.</span><span class="sxs-lookup"><span data-stu-id="c2b06-125">(Because the logon name litwareinc\\pilar was included as a parameter, the Windows PowerShell Credential Request dialog box only requires the administrator to enter the password for the Pilar Ackerman account.) The resulting credential object is then stored in a variable named $cred1.</span></span>

<span data-ttu-id="c2b06-126">Em seguida, o segundo comando verifica se esse usuário pode fazer logon no pool atl-cs-001.litwareinc.com e envia a mensagem de chat do XMPP.</span><span class="sxs-lookup"><span data-stu-id="c2b06-126">The second command then checks whether this user can log on to the pool atl-cs-001.litwareinc.com and send the XMPP instant message.</span></span> <span data-ttu-id="c2b06-127">Para executar essa tarefa, o cmdlet **Test-CsXmppIm** é chamado, juntamente com quatro parâmetros: TargetFqdn (o FQDN do pool de registrador); Destinatário (o endereço SIP do usuário ao qual a mensagem está sendo endereçada); Usercredential (o objeto do Windows PowerShell que contém as credenciais de usuário de pilar Alverca); e UserSipAddress (o endereço SIP correspondente às credenciais de usuário fornecidas).</span><span class="sxs-lookup"><span data-stu-id="c2b06-127">To run this task, the **Test-CsXmppIm** cmdlet is called, together with four parameters: TargetFqdn (the FQDN of the Registrar pool); Receiver (the SIP address of the user the message is being addressed to); UserCredential (the Windows PowerShell object that contains Pilar Ackerman’s user credentials); and UserSipAddress (the SIP address that corresponds to the supplied user credentials).</span></span>

    $credential = Get-Credential "litwareinc\kenmyer"
    
    Test-CsXmppIM -TargetFqdn "atl-cs-001.litwareinc.com" -Receiver "adelany@contoso.com" -UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="c2b06-128">Determinação do sucesso ou falha</span><span class="sxs-lookup"><span data-stu-id="c2b06-128">Determining success or failure</span></span>

<span data-ttu-id="c2b06-129">Se XMPP mensagem instantânea estiver configurada corretamente, você receberá uma saída semelhante a essa, com a propriedade Result marcada como **Success:**</span><span class="sxs-lookup"><span data-stu-id="c2b06-129">If XMPP instant messaging is correctly configured, you'll receive output similar to this, with the Result property marked as **Success:**</span></span>

<span data-ttu-id="c2b06-130">FQDN de destino: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="c2b06-130">Target Fqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="c2b06-131">Resultado: êxito</span><span class="sxs-lookup"><span data-stu-id="c2b06-131">Result : Success</span></span>

<span data-ttu-id="c2b06-132">Latência: 00:00:02.5361946</span><span class="sxs-lookup"><span data-stu-id="c2b06-132">Latency : 00:00:02.5361946</span></span>

<span data-ttu-id="c2b06-133">Mensagem de erro:</span><span class="sxs-lookup"><span data-stu-id="c2b06-133">Error Message :</span></span>

<span data-ttu-id="c2b06-134">Correto</span><span class="sxs-lookup"><span data-stu-id="c2b06-134">Diagnosis :</span></span>

<span data-ttu-id="c2b06-135">Se os usuários especificados não puderem usar mensagens instantâneas do XMPP, o resultado será mostrado como uma **falha**, e informações adicionais serão gravadas nas propriedades de erro e diagnóstico:</span><span class="sxs-lookup"><span data-stu-id="c2b06-135">If the specified users can't use XMPP instant messaging, the Result will be shown as **Failure**, and additional information will be recorded in the Error and Diagnosis properties:</span></span>

<span data-ttu-id="c2b06-136">Aviso: falha ao ler o número da porta do registrador para o número da porta de dados totalmente qualificado</span><span class="sxs-lookup"><span data-stu-id="c2b06-136">WARNING: Failed to read Registrar port number for the given fully qualified</span></span>

<span data-ttu-id="c2b06-137">FQDN (nome de domínio).</span><span class="sxs-lookup"><span data-stu-id="c2b06-137">domain name (FQDN).</span></span> <span data-ttu-id="c2b06-138">Usando o número da porta do registrador padrão.</span><span class="sxs-lookup"><span data-stu-id="c2b06-138">Using default Registrar port number.</span></span> <span data-ttu-id="c2b06-139">Extremamente</span><span class="sxs-lookup"><span data-stu-id="c2b06-139">Exception:</span></span>

<span data-ttu-id="c2b06-140">System. InvalidOperationException: nenhum cluster correspondente localizado na topologia.</span><span class="sxs-lookup"><span data-stu-id="c2b06-140">System.InvalidOperationException: No matching cluster found in topology.</span></span>

<span data-ttu-id="c2b06-141">como</span><span class="sxs-lookup"><span data-stu-id="c2b06-141">at</span></span>

<span data-ttu-id="c2b06-142">Microsoft. RTC. Management. SyntheticTransactions. SipSyntheticTransaction. TryRetri</span><span class="sxs-lookup"><span data-stu-id="c2b06-142">Microsoft.Rtc.Management.SyntheticTransactions.SipSyntheticTransaction.TryRetri</span></span>

<span data-ttu-id="c2b06-143">eveRegistrarPortFromTopology (Int32& registrarPortNumber)</span><span class="sxs-lookup"><span data-stu-id="c2b06-143">eveRegistrarPortFromTopology(Int32& registrarPortNumber)</span></span>

<span data-ttu-id="c2b06-144">FQDN de destino: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="c2b06-144">Target Fqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="c2b06-145">Resultado: falha</span><span class="sxs-lookup"><span data-stu-id="c2b06-145">Result : Failure</span></span>

<span data-ttu-id="c2b06-146">Latência: 00:00:00</span><span class="sxs-lookup"><span data-stu-id="c2b06-146">Latency : 00:00:00</span></span>

<span data-ttu-id="c2b06-147">Mensagem de erro: 10060, falha na tentativa de conexão porque a parte conectada</span><span class="sxs-lookup"><span data-stu-id="c2b06-147">Error Message : 10060, A connection attempt failed because the connected party</span></span>

<span data-ttu-id="c2b06-148">Não respondeu corretamente após um período de tempo ou</span><span class="sxs-lookup"><span data-stu-id="c2b06-148">did not properly respond after a period of time, or</span></span>

<span data-ttu-id="c2b06-149">a conexão estabelecida falhou porque o host conectado tem</span><span class="sxs-lookup"><span data-stu-id="c2b06-149">established connection failed because connected host has</span></span>

<span data-ttu-id="c2b06-150">Falha ao responder 10.188.116.96:5061</span><span class="sxs-lookup"><span data-stu-id="c2b06-150">failed to respond 10.188.116.96:5061</span></span>

<span data-ttu-id="c2b06-151">Exceção interna: falha na tentativa de conexão porque o</span><span class="sxs-lookup"><span data-stu-id="c2b06-151">Inner Exception:A connection attempt failed because the</span></span>

<span data-ttu-id="c2b06-152">a parte conectada não respondeu corretamente após um período de</span><span class="sxs-lookup"><span data-stu-id="c2b06-152">connected party did not properly respond after a period of</span></span>

<span data-ttu-id="c2b06-153">falha na hora ou estabelecida a conexão porque o host conectado</span><span class="sxs-lookup"><span data-stu-id="c2b06-153">time, or established connection failed because connected host</span></span>

<span data-ttu-id="c2b06-154">falhou ao responder 10.188.116.96:5061</span><span class="sxs-lookup"><span data-stu-id="c2b06-154">has failed to respond 10.188.116.96:5061</span></span>

<span data-ttu-id="c2b06-155">Correto</span><span class="sxs-lookup"><span data-stu-id="c2b06-155">Diagnosis :</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="c2b06-156">Motivos pelos quais o teste pode ter falhado</span><span class="sxs-lookup"><span data-stu-id="c2b06-156">Reasons why the test might have failed</span></span>

<span data-ttu-id="c2b06-157">Aqui estão alguns motivos comuns pelos quais **Test-CsXmppIM** pode falhar:</span><span class="sxs-lookup"><span data-stu-id="c2b06-157">Here are some common reasons why **Test-CsXmppIM** might fail:</span></span>

  - <span data-ttu-id="c2b06-158">Um valor de parâmetro incorreto foi fornecido.</span><span class="sxs-lookup"><span data-stu-id="c2b06-158">An incorrect parameter value was supplied.</span></span> <span data-ttu-id="c2b06-159">Se usado, os parâmetros opcionais devem ser configurados corretamente ou o teste falhará.</span><span class="sxs-lookup"><span data-stu-id="c2b06-159">If used, the optional parameters must be configured correctly or the test will fail.</span></span> <span data-ttu-id="c2b06-160">Execute o comando novamente sem os parâmetros opcionais e veja se isso é bem-sucedido.</span><span class="sxs-lookup"><span data-stu-id="c2b06-160">Rerun the command without the optional parameters and see whether that succeeds.</span></span>

  - <span data-ttu-id="c2b06-161">Esse comando falhará se a configuração de gateway do XMPP estiver configurada incorretamente ou ainda não tiver sido implantada.</span><span class="sxs-lookup"><span data-stu-id="c2b06-161">This command will fail if XMPP gateway configuration is misconfigured or not yet deployed.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="c2b06-162">Confira também</span><span class="sxs-lookup"><span data-stu-id="c2b06-162">See Also</span></span>


[<span data-ttu-id="c2b06-163">Set-CsXmppGatewayConfiguration</span><span class="sxs-lookup"><span data-stu-id="c2b06-163">Set-CsXmppGatewayConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsXmppGatewayConfiguration)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

